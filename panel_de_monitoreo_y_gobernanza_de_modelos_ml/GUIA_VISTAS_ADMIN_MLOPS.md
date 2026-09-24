# Guía de Arquitectura y Estructura de Vistas — Panel de Administración & MLOps

**Proyecto de Tesis:** ValuaProp AI — Sistema de Valoración Predictiva Inmobiliaria con Machine Learning  
**Módulo:** Gobernanza MLOps, Registro de Modelos (MLflow) y Auditoría  
**Documento Técnico:** Especificación Funcional de Pantallas para el Administrador  
**Archivo de Referencia UI:** [code.html](file:///d:/NuevaCarpetaLool/python_modelo_tesis/code.html) *(Plantilla base Tailwind / Plus Jakarta Sans / Inter)*  
**Fecha:** Septiembre 2026  

---

## 1. Alineación con la Realidad del Modelo y MLflow

Para que la interfaz no muestre datos ficticios o incoherentes con tu investigación, la vista debe adaptarse a los artefactos reales de tu proyecto y al ecosistema de **MLflow**:

### A. Coexistencia de Dos Modelos Independientes (Venta y Alquiler)
Tu solución cuenta con **dos pipelines de Machine Learning separados**:
1. **Modelo de Venta (`ValuaProp-Venta`):** Entrenado con 67,914 registros (BCRP 2016–2025). Métrica real de Test: **MAPE 15.04%**, MAE ~S/. 52,166, R² 0.7470.
2. **Modelo de Alquiler (`ValuaProp-Alquiler`):** Entrenado con 61,603 registros (BCRP 2016–2025). Métrica real de Test: **MAPE 13.85%**, MAE ~S/. 320/mes, R² 0.76.
* **Impacto en UI:** El selector de pestañas superior en `code.html` (`#tab-venta` y `#tab-alquiler`) es indispensable para alternar dinámicamente las métricas de ambos modelos sin mezclar sus escalas monetarias.

### B. Mapeo de Conceptos de MLflow
* **MLflow Tracking (Experiments & Runs):** Cada reentrenamiento manual o programado genera un `run_id` (ej. `run-xgb-v2-test-884b`) donde se registran hiperparámetros (`max_depth`, `learning_rate`, `reg_alpha`) y métricas de validación out-of-time.
* **MLflow Model Registry:** Los modelos se versionan como artefactos registrados (`models:/ValuaProp-Venta/2`). Sus estados normados son:
  * `@champion` o `Production` (Modelo en servicio activo en FastAPI).
  * `@challenger` o `Staging / Candidate` (Modelo recién entrenado que compite por pasar a producción).
  * `@archived` o `Archived` (Modelos previos preservados para rollback).
* **Artefactos Serializados:** Cada versión guarda `model.pkl`, `features_metadata.json`, `distrito_encoder.json` y los gráficos `shap_beeswarm.png` y `feature_importance.png`.

---

## 2. Estructura y Especificación de las 3 Vistas

Se recomienda un diseño unificado de **Dashboard con Pestañas de Navegación** (como está estructurado en el `<header>` de `code.html`), permitiendo al administrador navegar entre:
1. `Monitoreo de Modelos (US-05)`
2. `Gobernanza y Reentrenamiento (US-06)`
3. `Auditoría y Trazabilidad (TH-07)`

---

### Vista 1: Dashboard de Monitoreo MLOps (Ruta `/admin/monitoring`)

**Objetivo:** Supervisar en tiempo real la salud operativa del modelo en producción, la latencia de la API y la degradación predictiva (*Data Drift* y *Concept Drift*).

#### Componente 1.1: Barra de Contexto y Selector de Pipeline
* **Selector Dual:** Botones tipo píldora para conmutar entre `Modelo de Venta (XGBoost)` y `Modelo de Alquiler (XGBoost)`.
* **Badges de Estado:**
  * `Producción: v2.0.0` (Tag MLflow: `Production`).
  * `MLflow Run Hash: #xgboost-prod-884b` (Enlace externo directo a la UI de MLflow).
  * `Última Evaluación: 2026-Q1 (Test Out-of-Time)`.

#### Componente 1.2: Fila Superior de Tarjetas KPI (Métricas Oficiales de Tesis)
Deben mostrar los valores reales de tu evaluación out-of-time:

| Tarjeta | Valor Modelo Venta | Valor Modelo Alquiler | Umbral SLA / Meta de Tesis | Indicador Visual |
| :--- | :--- | :--- | :--- | :--- |
| **MAPE (Margen Porcentual)** | **15.04%** | **13.85%** | $\le 17.89\%$ (Benchmark Oporto et al.) | 🟢 Supera Benchmark |
| **MAE (Error Absoluto Medio)** | **S/. 52,166** *(o USD $13,800)* | **S/. 320 / mes** | Minimizar | 🟢 Estable |
| **$R^2$ Score (Ajuste)** | **0.7470** | **0.7620** | $> 0.70$ (Split Temporal Estricto) | 🟢 Robusto sin leakage |
| **Latencia Inferencia P95** | **42 ms** | **38 ms** | $< 100\text{ ms}$ (SLA FastAPI) | 🟢 Óptima |

#### Componente 1.3: Gráfico de Rendimiento Temporal y Detección de Drift
* **Gráfico de Líneas SVG (como en `code.html`):** Evolución histórica del MAPE semana a semana o mes a mes.
* **Tarjeta de Estabilidad (Drift del Mercado):**
  * **PSI (*Population Stability Index*):** `0.042` (Valor $< 0.1$ indica distribución estable en m² y precios de oferta).
  * **Kolmogorov-Smirnov Test (Target Drift):** `$p\text{-valor} = 0.38$` (Sin cambio estructural brusco de ciclo).

#### Componente 1.4: Estado del Servicio Analítico (`mlService` FastAPI en Docker)
* **Memoria RAM:** `1.15 GB / 2.00 GB` consumidos por los dos modelos XGBoost y el objeto SHAP TreeExplainer.
* **CPU:** `8% - 15%` de utilización.
* **Uptime:** `99.94%` (Activo desde hace 28 días).

---

### Vista 2: Gestión de Versiones y Reentrenamientos (Ruta `/admin/models`)

**Objetivo:** Gobernanza de artefactos, comparación cara a cara entre el modelo actual y un nuevo candidato, y ejecución de acciones de promoción o reentrenamiento.

#### Componente 2.1: Tabla de Modelos Registrados (Conectada a MLflow Model Registry)
Muestra el catálogo histórico de versiones almacenadas en el servidor de artefactos:

```
+---------+--------------------+-----------------------------+---------+---------+--------+------------------+
| Versión | Fecha Registro     | Dataset Base                | MAPE    | MAE     | R²     | Estado MLflow    |
+---------+--------------------+-----------------------------+---------+---------+--------+------------------+
| v2.1.0  | 2026-09-18 03:00   | BCRP 2016-2025 + Distr 2026 | 14.32%  | S/.49k  | 0.758  | 🟡 Candidate     |
| v2.0.0  | 2026-09-01 10:30   | BCRP Maestro (67,914 obs)   | 15.04%  | S/.52k  | 0.747  | 🟢 Production    |
| v1.0.0  | 2026-08-15 16:20   | Baseline 28 features        | 17.10%  | S/.58k  | 0.712  | ⚪ Archived      |
+---------+--------------------+-----------------------------+---------+---------+--------+------------------+
```

#### Componente 2.2: Tarjeta Comparativa Cara a Cara (*Side-by-Side Benchmark*)
Compara el modelo actualmente desplegado frente al nuevo candidato generado por el pipeline:

* **Columna Izquierda (Modelo Vigente en Producción):**
  * Versión: `v2.0.0` (MLflow Run `#prod-884b`).
  * Features: 33 predictoras.
  * MAPE: `15.04%` | MAE: `S/. 52,166`.
* **Columna Derecha (Modelo Candidato Propuesto):**
  * Versión: `v2.1.0-rc1` (MLflow Run `#train-exp-092c`).
  * Features: 33 predictoras + Actualización de Contexto 2026.
  * MAPE: `14.32%` *(Mejora de **+0.72%**)* | MAE: `S/. 49,850` *(Reducción de **-S/. 2,316**)*.
* **Compuertas de Calidad Técnicas (*Quality Gates*):**
  * [x] Supera benchmark de Oporto et al. ($< 17.89\%$).
  * [x] Sin degradación en distritos clave (Miraflores, San Isidro, Surco).
  * [x] Test de latencia de inferencia $< 100\text{ ms}$.

#### Componente 2.3: Panel de Acciones del Administrador
* 🚀 **Botón Verde Principal: "Aprobar y Desplegar Modelo" (`openApprovalModal()`):**
  * Abre el modal de confirmación.
  * **Campo de texto obligatorio:** *"Ingrese motivo técnico o justificación de la aprobación (Requerido para auditoría TH-07)"*.
  * Checkbox: *"Habilitar transición progresiva de tráfico en FastAPI"*.
  * Al confirmar: Invoca a la API de MLflow (`client.transition_model_version_stage(name="ValuaProp-Venta", version=2, stage="Production")`).
* 🔄 **Botón Rojo de Contingencia: "Revertir a Versión Anterior (Rollback)" (`openRollbackModal()`):**
  * Permite restaurar de inmediato la versión previa archivada (`v1.0.0`) ante anomalías imprevistas en producción.
* ⚙️ **Botón Secundario: "Disparar Reentrenamiento Manual":**
  * Permite ejecutar en segundo plano el script `03_entrenamiento_xgboost.py` o `03_entrenamiento_alquiler.py` sobre los datos más recientes.

---

### Vista 3: Registro de Auditoría de Decisiones (Ruta `/admin/audit`)

**Objetivo:** Garantizar trazabilidad fiduciaria inmutable, documentando quién, cuándo y por qué se alteró el modelo productivo.

#### Componente 3.1: Tabla de Auditoría Criptográfica
Registra cada transición de estado realizada desde la UI o el pipeline CI/CD:

```
+--------------------+-------------------+---------------+------------------+-------------------+------------------------------------------+
| Fecha y Hora (UTC) | Administrador     | Versión Modif.| Acción Ejecutada | Métricas Delta    | Motivo / Justificación Registrada        |
+--------------------+-------------------+---------------+------------------+-------------------+------------------------------------------+
| 2026-09-18 11:45   | Ing. Marco Silva  | v2.1.0        | 🟢 PROMOVIDO A   | MAPE: 15.04% ->   | "Incorporación de datos BCRP Q1-2026 y   |
|                    | (ML Lead)         |               |    PRODUCCIÓN    | 14.32% (-0.72%)   | recalibración de ponderación temporal."  |
+--------------------+-------------------+---------------+------------------+-------------------+------------------------------------------+
| 2026-09-02 09:15   | Dra. Sofía Aranda | v2.0.0        | 🟢 PROMOVIDO A   | MAPE: 17.10% ->   | "Modelo definitivo de Tesis: 33 features |
|                    | (Data Scientist)  |               |    PRODUCCIÓN    | 15.04% (-2.06%)   | con ratios espaciales y ponderación E1." |
+--------------------+-------------------+---------------+------------------+-------------------+------------------------------------------+
| 2026-08-20 16:30   | Ing. Marco Silva  | v1.9.8        | 🔴 REVERTIDO A   | MAPE: 18.20% ->   | "Rollback preventivo: anomalía de        |
|                    | (ML Lead)         |               |    V1.9.0        | 16.50% (Rollback) | predicción en tipologías dúplex."        |
+--------------------+-------------------+---------------+------------------+-------------------+------------------------------------------+
```

* **Botón de Descarga:** `Exportar Registro CSV / PDF` (cumple con requerimiento fiduciario de auditoría para peritos y entidades).
* **Firma Hash:** Muestra el hash SHA-256 del artefacto binario para garantizar que el archivo `.pkl` en producción no fue adulterado.

---

## 3. Correspondencia con la Plantilla `code.html`

El archivo [code.html](file:///d:/NuevaCarpetaLool/python_modelo_tesis/code.html) ya posee la base visual y el maquetado CSS necesarios. La siguiente matriz detalla cómo se asigna cada sección del HTML a las 3 vistas funcionales:

| Sección en `code.html` | Líneas de Código | Vista MLOps Correspondiente | Ajuste con Datos Reales de la Tesis |
| :--- | :--- | :--- | :--- |
| **Pipeline Selector Switch** | Líneas 29–42 | Común (Header) | Conservar botones `Venta` y `Alquiler` con función `switchPipeline()`. |
| **Sección 1: Métricas Vigentes** | Líneas 43–140 | **Vista 1 (Dashboard)** | Cambiar los valores de ejemplo a los de tesis: MAPE `15.04%` (Venta) / `13.85%` (Alquiler). |
| **Sección Gráfica: Evolución & Drift** | Líneas 141–213 | **Vista 1 (Dashboard)** | Mantener el gráfico SVG de tendencia temporal y el indicador PSI ($< 0.1$). |
| **Sección 2: Comparación Candidato** | Líneas 214–381 | **Vista 2 (Gobernanza)** | Tabla cara a cara (Production vs Candidate). Los datos provienen del endpoint de MLflow. |
| **Sección 3: Comandos de Despliegue** | Líneas 382–422 | **Vista 2 (Gobernanza)** | Botones de "Aprobar", "Rechazar" y "Rollback", vinculados a los modales. |
| **Sección 4: Registro de Auditoría** | Líneas 423–521 | **Vista 3 (Auditoría)** | Tabla con histórico de promociones, usuario responsable y justificación. |
| **Modales de Aprobación & Rollback** | Líneas 522–614 | **Vista 2 / Vista 3** | Contienen los campos `<textarea id="audit-reason">` requeridos para la justificación. |

---

## 4. Endpoints del Backend Recomendados (FastAPI + MLflow Client)

Para alimentar estas vistas en Angular o Figma, tu microservicio (`mlService`) debe exponer los siguientes endpoints REST:

1. `GET /api/v1/mlops/monitoring/metrics?pipeline={venta|alquiler}`
   * Devuelve: MAPE, MAE, RMSE, R², latencia P95 y memoria RAM actual.
2. `GET /api/v1/mlops/registry/models?pipeline={venta|alquiler}`
   * Devuelve: Lista de versiones registradas desde `MlflowClient().search_model_versions()`.
3. `GET /api/v1/mlops/registry/compare-candidate?pipeline={venta|alquiler}`
   * Devuelve: Comparativa cara a cara entre el stage `Production` y el stage `Candidate`.
4. `POST /api/v1/mlops/governance/promote`
   * Body: `{ "pipeline": "venta", "version": 2, "justification": "...", "admin_user": "Marco Silva" }`.
   * Acción: Transiciona el modelo en MLflow Registry e inserta la fila en la tabla de base de datos de Auditoría.
5. `POST /api/v1/mlops/governance/rollback`
   * Body: `{ "pipeline": "venta", "target_version": 1, "reason": "...", "admin_user": "Marco Silva" }`.
   * Acción: Degrada el modelo actual a `Archived` y promueve la versión anterior a `Production`.
6. `GET /api/v1/mlops/audit/logs`
   * Devuelve: Historial paginado de auditoría con fecha, usuario, acción y justificación.
