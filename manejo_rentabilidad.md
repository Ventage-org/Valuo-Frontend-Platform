Para que este módulo de rentabilidad sea **académicamente riguroso, financieramente sólido y visualmente intuitivo en la web**, debe reflejar con total transparencia cómo se conectan tus dos modelos de Machine Learning (Venta y Alquiler) a través del parámetro de gastos operativos (**OER**).

A continuación te detallo la matemática exacta, los datos que deben mostrarse en la interfaz y cómo estructurar el módulo:

---

### 1. La Matemática del Módulo (El "Motor de Cálculo")

A partir de una misma propiedad ingresada (mismo distrito, superficie, habitaciones, etc.):

1. **Entradas de Machine Learning:**
   * $V_{\text{venta}}$ = Valor comercial estimado de venta (ej. S/. 450,000)
   * $P_{\text{alquiler}}$ = Precio mensual estimado de alquiler (ej. S/. 2,200/mes)
2. **Cálculos Financieros:**
   * **Ingreso Bruto Anual ($GSI$):** 
     $$GSI = P_{\text{alquiler}} \times 12$$
     *(Ejemplo: S/. 2,200 × 12 = S/. 26,400/año)*
   * **Gastos Operativos Anuales ($OpEx$):** Regulados por el **OER** (Operating Expense Ratio):
     $$OpEx = GSI \times OER$$
     *(Ejemplo con OER del 15%: S/. 26,400 × 0.15 = S/. 3,960/año)*
   * **Ingreso Operativo Neto Anual ($NOI$):**
     $$NOI = GSI - OpEx = (P_{\text{alquiler}} \times 12) \times (1 - OER)$$
     *(Ejemplo: S/. 26,400 − S/. 3,960 = S/. 22,440/año)*
   * **Cap Rate (Rentabilidad Neta Anual Unlevered):**
     $$\text{Cap Rate} = \left(\frac{NOI}{V_{\text{venta}}}\right) \times 100\%$$
     *(Ejemplo: (22,440 / 450,000) × 100 = **4.99%**)*

---

### 2. Estructura de Datos para la Interfaz Web

Para que el tasador o analista tenga control total y entienda el resultado, el módulo debe dividirse en **4 bloques visuales**:

```
+-------------------------------------------------------------------------+
| [1] TARJETAS PRINCIPALES (KPIs Estrella)                                |
|  - Cap Rate Neto (%)   - NOI Anual (S/.)   - Años de Recuperación (GRM) |
+-------------------------------------------------------------------------+
| [2] PANEL DE PARÁMETROS EDITABLES (Sensibilidad)                        |
|  - Slider OER (Gastos Operativos): [--- 15% ---] (10% a 35%)            |
|  - Switch Moneda: [ S/. Soles ] / [ $ USD ]                             |
+-------------------------------------------------------------------------+
| [3] DESGLOSE EN CASCADA DEL FLUJO ANUAL                                 |
|  (+) Ingreso Bruto Estimado:  S/. 26,400/año (S/. 2,200/mes × 12)       |
|  (-) Gastos Operativos (OER): S/.  3,960/año (15%)                      |
|  (=) NOI (Ingreso Neto):      S/. 22,440/año                            |
|  (/) Valor Comercial Venta:   S/. 450,000                               |
+-------------------------------------------------------------------------+
| [4] BENCHMARK DISTRITAL & NOTA METODOLÓGICA                             |
|  - Semáforo comparativo vs. Cap Rate promedio de Lima / Distrito        |
|  - Nota técnica de supuestos (Unlevered, sin plusvalía)                 |
+-------------------------------------------------------------------------+
```

---

### 3. Detalle de los Campos Específicos a Mostrar

#### A. Tarjetas de Métricas Clave (Top KPI Cards)
* **Cap Rate Neto (%):** Es el número principal (ej. `5.12%`). Debe destacar con tipografía grande.
* **Cap Rate Bruto (Gross Yield %):** $\frac{GSI}{V_{\text{venta}}} \times 100\%$ (ej. `6.02%`). A los tasadores les gusta ver tanto el bruto como el neto.
* **NOI Estimado Anual:** El flujo neto en efectivo estimado que genera la propiedad al año (ej. `S/. 22,440 / año` o `S/. 1,870 / mes neto`).
* **Multiplicador de Alquiler Bruto (GRM / Años de Recuperación simple):**
  $$\text{Años} = \frac{V_{\text{venta}}}{GSI}$$
  *(Ejemplo: 450,000 / 26,400 = **17.0 años**).* Es un indicador estándar que cualquier perito o inversionista comprende de inmediato.

#### B. Control Interactivo del OER (Operating Expense Ratio)
Dado que tu tesis declara que el OER es **parametrizable**:
* Un control deslizable (**Slider**) con valor por defecto sugerido del **15% o 20%** (rango típico en departamentos residenciales en Lima: mantenimiento que asume el dueño, pequeños arreglos, periodos cortos de rotación, arbitrios).
* Rango seleccionable: del **0% al 35%**.
* **Efecto dinámico:** Al mover el slider, el NOI y el Cap Rate se recalculan en tiempo real sin recargar la página.

#### C. Comparativa Contextual de Mercado (Semáforo de Rentabilidad)
Para darle utilidad real al tasador, sitúa el Cap Rate obtenido dentro del rango normal de Lima:
* **Bajo (< 4.5%):** Típico de distritos de ticket alto (San Isidro, Miraflores, Barranco) donde el inmueble vale mucho por m² y la rentabilidad por alquiler se comprime.
* **Promedio (4.5% - 6.5%):** Rango de equilibrio para Lima Moderna (Jesús María, Lince, Magdalena, Surquillo).
* **Atractivo (> 6.5%):** Típico de zonas de expansión o tickets más accesibles donde el ratio alquiler/venta es más alto.

#### D. Cuadro de Supuestos y Limitaciones (Obligatorio por rigor de Tesis)
Un recuadro discreto o tooltip informativo que cite textualmente las limitaciones declaradas en tu metodología:
> **Bases del Cálculo Financiero:**
> * Modelo no apalancado (*Unlevered*): Supone compra 100% con capital propio (sin crédito hipotecario ni costos de deuda).
> * No considera vacancia prolongada ni apreciación de capital (plusvalía futura del terreno).
> * OER estándar parametrizado: No sustituye la contabilidad real de gastos del edificio.

---

### Resumen de valor para tu Tesis
Mostrar el módulo de esta forma cierra el círculo perfecto de tu investigación:
1. Tu **Modelo 1** predice el precio de venta.
2. Tu **Modelo 2** predice el precio de alquiler.
3. El **Módulo Financiero** los fusiona orgánicamente para dar una métrica de decisión de inversión (Cap Rate), dándole al tasador una herramienta completa que no solo dice "cuánto cuesta", sino "qué tan rentable es el activo".