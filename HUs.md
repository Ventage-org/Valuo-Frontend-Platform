# 1.5. Gestión del Proyecto y Alcance

## 1.5.1 Alcance del Proyecto

El alcance del proyecto se gestiona mediante un enfoque ágil basado en **Scrum**, utilizando como artefacto principal la **Pila de Producto (Product Backlog)**. Este backlog concentra todos los requerimientos funcionales y técnicos priorizados, permitiendo planificar, ejecutar y controlar el desarrollo del sistema web de valoración inmobiliaria y análisis de rentabilidad (**Valuo**).

El alcance se define por entregables incrementales organizados en **Épicas**, **Historias de Usuario (US)** e **Historias Técnicas (TH)** que aseguran tanto la experiencia funcional de los agentes inmobiliarios y administradores, como la calidad de los pipelines de datos y modelos predictivos.

---

## 1.5.2 Pila de Producto (Product Backlog)

Las funcionalidades y componentes del sistema se estructuran en **10 Épicas**: 8 épicas funcionales (23 Historias de Usuario) y 2 épicas técnicas (14 Historias Técnicas), totalizando **37 historias**.

### Tabla 3. Épicas de la Propuesta

| # | Épica | Tipo | # Historias Estimadas | Detalle |
| :-: | :--- | :---: | :-: | :--- |
| **EP-01** | Gestión de Usuarios y Autenticación | US | **4** | Registro de agentes, inicio de sesión, cierre de sesión y edición de perfil. |
| **EP-02** | Gestión de Cartera de Inmuebles | US | **6** | Registro con mapa, edición, búsqueda/filtros, detalle, cambio de estado y desactivación de inmuebles. |
| **EP-03** | Predicción de Valor Comercial de Venta con ML | US | **3** | Ingreso de datos del inmueble, obtención de estimación de venta y consulta de historial de tasaciones. |
| **EP-04** | Predicción de Alquiler Mensual con ML | US | **2** | Estimación del canon de alquiler mensual y consulta de historial de alquileres. |
| **EP-05** | Explicabilidad de Modelos con SHAP | US | **2** | Visualización de factores y atributos que influyen en el valor de venta y alquiler. |
| **EP-06** | Análisis de Rentabilidad (Cap Rate) | US | **2** | Cálculo automatizado de rentabilidad anual (Cap Rate) y advertencia informativa sobre financiamiento. |
| **EP-07** | Generación de Reportes de Tasación | US | **2** | Generación de informe comercial en PDF y descarga/compartición con clientes. |
| **EP-08** | Supervisión y Monitoreo del Modelo (MLOps) | US | **2** | Panel de métricas de precisión para el administrador y aprobación o reversión de versiones del modelo. |
| **EP-09** | Pipeline de Ingestión ETL y Datos de Entorno | TH | **6** | Ingestión de datos INEI, BCRP, criminalidad, distancias urbanas OpenStreetMap y consolidación analítica. |
| **EP-10** | Modelado Predictivo, Versionado y Reentrenamiento | TH | **8** | Preprocesamiento, entrenamiento y evaluación de modelos, versionado en MLflow y pipeline de reentrenamiento. |

---

## 1.5.3 Resumen Consolidado de Historias de Usuario (US)

### Tabla 4. Historias de Usuario de la Propuesta

| ID | Épica | Historia | Rol | Prioridad |
| :-: | :--- | :--- | :---: | :---: |
| **US-01** | EP-01: Usuarios y Autenticación | Registro de agente inmobiliario | Agente | Alta |
| **US-02** | EP-01: Usuarios y Autenticación | Inicio de sesión en la plataforma | Ambos | Alta |
| **US-03** | EP-01: Usuarios y Autenticación | Cierre de sesión seguro | Ambos | Media |
| **US-04** | EP-01: Usuarios y Autenticación | Edición de perfil profesional | Agente | Baja |
| **US-05** | EP-08: Supervisión y Monitoreo | Visualización del panel de métricas del modelo | Administrador | Alta |
| **US-06** | EP-08: Supervisión y Monitoreo | Aprobación o reversión de versión del modelo | Administrador | Alta |
| **US-07** | EP-02: Cartera de Inmuebles | Registro de inmueble con ubicación en mapa interactivo | Agente | Alta |
| **US-08** | EP-02: Cartera de Inmuebles | Edición de inmueble propio | Agente | Media |
| **US-09** | EP-02: Cartera de Inmuebles | Búsqueda y filtrado de inmuebles en la cartera propia | Agente | Alta |
| **US-10** | EP-02: Cartera de Inmuebles | Visualización de ficha detallada del inmueble | Agente | Alta |
| **US-11** | EP-02: Cartera de Inmuebles | Cambio de estado comercial (Disponible, Vendido, Alquilado) | Agente | Media |
| **US-12** | EP-02: Cartera de Inmuebles | Desactivación de inmueble propio | Agente | Baja |
| **US-13** | EP-03: Predicción Venta | Ingreso de datos del inmueble para tasación de venta | Agente | Alta |
| **US-14** | EP-03: Predicción Venta | Obtención de precio de venta comercial estimado | Agente | Alta |
| **US-15** | EP-03: Predicción Venta | Consulta de historial de tasaciones de venta | Agente | Media |
| **US-16** | EP-04: Predicción Alquiler | Obtención de estimación de alquiler mensual | Agente | Alta |
| **US-17** | EP-04: Predicción Alquiler | Consulta de historial de estimaciones de alquiler | Agente | Media |
| **US-18** | EP-05: Explicabilidad SHAP | Visualización de factores influyentes en el precio de venta | Agente | Alta |
| **US-19** | EP-05: Explicabilidad SHAP | Visualización de factores influyentes en el canon de alquiler | Agente | Media |
| **US-20** | EP-06: Rentabilidad Cap Rate | Cálculo automatizado de rentabilidad anual (Cap Rate) | Agente | Alta |
| **US-21** | EP-06: Rentabilidad Cap Rate | Visualización de aviso informativo sobre financiamiento hipotecario | Agente | Alta |
| **US-22** | EP-07: Reportes | Generación de reporte comercial en formato PDF | Agente | Alta |
| **US-23** | EP-07: Reportes | Descarga y compartición del reporte comercial | Agente | Media |

---

## 1.5.4 Resumen Consolidado de Historias Técnicas (TH)

### Tabla 5. Historias Técnicas de la Propuesta

| ID | Épica | Historia Técnica | Rol Responsable | Prioridad |
| :-: | :--- | :--- | :---: | :---: |
| **TH-01** | EP-10: Modelado Predictivo | Preprocesar datos para modelo de venta | Equipo de Desarrollo/ML | Alta |
| **TH-02** | EP-10: Modelado Predictivo | Entrenar modelo XGBoost para valor de venta | Equipo de Desarrollo/ML | Alta |
| **TH-03** | EP-10: Modelado Predictivo | Evaluar modelo de venta contra métricas objetivo (MAE, RMSE, MAPE) | Equipo de Desarrollo/ML | Alta |
| **TH-04** | EP-10: Modelado Predictivo | Preprocesar datos para modelo de canon de alquiler | Equipo de Desarrollo/ML | Alta |
| **TH-05** | EP-10: Modelado Predictivo | Entrenar modelo XGBoost para alquiler mensual | Equipo de Desarrollo/ML | Alta |
| **TH-06** | EP-10: Modelado Predictivo | Evaluar modelo de alquiler contra métricas objetivo (MAE, RMSE, MAPE) | Equipo de Desarrollo/ML | Alta |
| **TH-07** | EP-10: Modelado Predictivo | Versionado de modelos y tracking de experimentos con MLflow | Equipo de Desarrollo/ML | Alta |
| **TH-08** | EP-09: Ingestión y Geoespacial | Ingesta y consolidación de indicadores sociodemográficos INEI/NSE | Equipo de Desarrollo/Datos | Alta |
| **TH-09** | EP-09: Ingestión y Geoespacial | Ingesta de series macroeconómicas BCRP y datos distritales de criminalidad | Equipo de Desarrollo/Datos | Alta |
| **TH-10** | EP-09: Ingestión y Geoespacial | Cálculo automatizado de distancias geodésicas vía OpenStreetMap | Equipo de Desarrollo/Datos | Alta |
| **TH-11** | EP-09: Ingestión y Geoespacial | Consolidación y validación de calidad en tabla analítica unificada | Equipo de Desarrollo/Datos | Alta |
| **TH-12** | EP-09: Ingestión y Geoespacial | Deduplicación y depuración de calidad de datos inmobiliarios | Equipo de Desarrollo/Datos | Media |
| **TH-13** | EP-09: Ingestión y Geoespacial | Pipeline ETL incremental automatizado para actualización periódica | Equipo de Desarrollo/Datos | Media |
| **TH-14** | EP-10: Modelado Predictivo | Pipeline de reentrenamiento continuo y comparación automática de métricas | Equipo de Desarrollo/ML | Alta |

---

## 1.5.5 Especificación Detallada de Épicas e Historias de Usuario

A continuación se presentan las fichas técnicas detalladas de cada Épica e Historia, siguiendo la estructura formal del proyecto con criterios de aceptación en lenguaje de escenarios (Dado-Cuando-Entonces).

---

### ÉPICA 01: Gestión de Usuarios y Autenticación

| EP: | 01 | Título: | Gestión de Usuarios y Autenticación |
| :--- | :--- | :--- | :--- |
| **Usuario:** | Agente Inmobiliario / Administrador | **Sprint:** | 1 |
| **Descripción** | Como usuario de la plataforma, deseo registrarme, iniciar sesión y administrar mi cuenta de forma segura, para acceder a las herramientas de valoración y gestión inmobiliaria según mis permisos asignados. | | |
| **Criterios de Aceptación** | - | | |
| **Prioridad** | Alta | | |
| **Tiempo Estimado** | 22 horas | | |

#### Historias de Usuario de la Épica 01

| HU: | US-01 | Título: | Registro de Agente Inmobiliario |
| :--- | :--- | :--- | :--- |
| **Usuario:** | Agente Inmobiliario | **Sprint:** | 1 |
| **Descripción** | <td colspan="3">Como agente inmobiliario, quiero crear una cuenta personal en la plataforma con mis datos y contraseña, para poder acceder a los servicios de tasación y gestión de cartera.</td> |
| **Criterios de Aceptación** | <td colspan="3">**Escenario 1: Creación exitosa de cuenta**<br>Dado que soy un agente no registrado y completo el formulario de registro con nombres, correo corporativo y contraseña segura,<br>Cuando confirmo el registro,<br>Entonces el sistema crea mi cuenta con el rol de Agente y me muestra un mensaje de confirmación para poder iniciar sesión.<br><br>**Escenario 2: Correo electrónico ya registrado (Excepción)**<br>Dado que ingreso un correo electrónico que ya existe en el sistema,<br>Cuando intento completar el registro,<br>Entonces el sistema rechaza la solicitud mostrando el mensaje "El correo ya se encuentra registrado".</td> |
| **Prioridad** | <td colspan="3">Alta</td> |
| **Tiempo Estimado** | <td colspan="3">6 horas</td> |

| HU: | US-02 | Título: | Inicio de Sesión en la Plataforma |
| :--- | :--- | :--- | :--- |
| **Usuario:** | Agente Inmobiliario / Administrador | **Sprint:** | 1 |
| **Descripción** | <td colspan="3">Como usuario registrado, quiero iniciar sesión con mi correo y contraseña, para ingresar de forma segura a las opciones disponibles según mi rol.</td> |
| **Criterios de Aceptación** | <td colspan="3">**Escenario 1: Inicio de sesión exitoso**<br>Dado que ingreso mi correo y contraseña correctos,<br>Cuando presiono "Iniciar Sesión",<br>Entonces el sistema valida mis credenciales y me dirige a mi panel principal de trabajo según mi rol de usuario.<br><br>**Escenario 2: Credenciales incorrectas (Excepción)**<br>Dado que ingreso un correo inexistente o una contraseña equivocada,<br>Cuando intento acceder,<br>Entonces el sistema bloquea el ingreso mostrando el mensaje "Usuario o contraseña incorrectos".</td> |
| **Prioridad** | <td colspan="3">Alta</td> |
| **Tiempo Estimado** | <td colspan="3">6 horas</td> |

| HU: | US-03 | Título: | Cierre de Sesión Seguro |
| :--- | :--- | :--- | :--- |
| **Usuario:** | Agente Inmobiliario / Administrador | **Sprint:** | 1 |
| **Descripción** | <td colspan="3">Como usuario con sesión activa, quiero cerrar mi sesión para evitar que terceros accedan a mi información y cartera de propiedades.</td> |
| **Criterios de Aceptación** | <td colspan="3">**Escenario 1: Cierre de sesión voluntario**<br>Dado que me encuentro dentro de la plataforma y selecciono "Cerrar Sesión",<br>Cuando confirmo la acción,<br>Entonces el sistema finaliza mi sesión y me redirige a la pantalla pública de bienvenida.<br><br>**Escenario 2: Sesión expirada por inactividad (Excepción)**<br>Dado que mi sesión ha expirado por tiempo transcurrido,<br>Cuando intento realizar alguna acción dentro del sistema,<br>Entonces el sistema me redirige a la pantalla de inicio mostrando el mensaje "La sesión ya finalizó".</td> |
| **Prioridad** | <td colspan="3">Media</td> |
| **Tiempo Estimado** | <td colspan="3">4 horas</td> |

| HU: | US-04 | Título: | Edición de Perfil Profesional |
| :--- | :--- | :--- | :--- |
| **Usuario:** | Agente Inmobiliario | **Sprint:** | 1 |
| **Descripción** | <td colspan="3">Como agente inmobiliario, quiero actualizar mis datos de contacto profesional para que figuren actualizados en la plataforma y en los reportes que genere.</td> |
| **Criterios de Aceptación** | <td colspan="3">**Escenario 1: Actualización de datos de contacto**<br>Dado que ingreso a la sección de mi perfil y modifico mi teléfono o datos de contacto,<br>Cuando presiono "Guardar Cambios",<br>Entonces el sistema actualiza la información y me muestra una confirmación en pantalla.<br><br>**Escenario 2: Formato de contacto inválido (Excepción)**<br>Dado que ingreso un número de teléfono con caracteres no válidos,<br>Cuando intento guardar los cambios,<br>Entonces el sistema no procesa la actualización y muestra el mensaje "Datos de perfil inválidos".</td> |
| **Prioridad** | <td colspan="3">Baja</td> |
| **Tiempo Estimado** | <td colspan="3">6 horas</td> |

---

### ÉPICA 02: Gestión de Cartera de Inmuebles

| EP: | 02 | Título: | Gestión de Cartera de Inmuebles |
| :--- | :--- | :--- | :--- |
| **Usuario:** | Agente Inmobiliario | **Sprint:** | 2 |
| **Descripción** | Como agente inmobiliario, deseo registrar, editar, buscar y consultar mis inmuebles ubicándolos en un mapa interactivo, para mantener organizada mi propia cartera de captaciones lista para tasación. | | |
| **Criterios de Aceptación** | - | | |
| **Prioridad** | Alta | | |
| **Tiempo Estimado** | 30 horas | | |

#### Historias de Usuario de la Épica 02

| HU: | US-07 | Título: | Registro de Inmueble con Ubicación en Mapa Interactivo |
| :--- | :--- | :--- | :--- |
| **Usuario:** | Agente Inmobiliario | **Sprint:** | 2 |
| **Descripción** | <td colspan="3">Como agente inmobiliario, quiero registrar una propiedad en mi cartera indicando sus características físicas y marcando su ubicación en un mapa, para habilitar su posterior tasación comercial.</td> |
| **Criterios de Aceptación** | <td colspan="3">**Escenario 1: Registro completo de propiedad**<br>Dado que completo los datos del inmueble (área, dormitorios, baños, antigüedad, distrito) y marco la ubicación de la propiedad en el mapa,<br>Cuando presiono "Guardar Inmueble",<br>Entonces el sistema registra la propiedad en mi cartera personal con estado "Disponible" y me muestra la confirmación.<br><br>**Escenario 2: Omisión de datos obligatorios o ubicación (Excepción)**<br>Dado que intento registrar un inmueble sin llenar el área o sin seleccionar el punto en el mapa,<br>Cuando presiono "Guardar Inmueble",<br>Entonces el sistema resalta los campos requeridos mostrando el mensaje "Complete los campos obligatorios del inmueble".</td> |
| **Prioridad** | <td colspan="3">Alta</td> |
| **Tiempo Estimado** | <td colspan="3">8 horas</td> |

| HU: | US-08 | Título: | Edición de Inmueble Propio |
| :--- | :--- | :--- | :--- |
| **Usuario:** | Agente Inmobiliario | **Sprint:** | 2 |
| **Descripción** | <td colspan="3">Como agente inmobiliario, quiero modificar los datos de un inmueble de mi cartera cuando cambie su precio base o alguna de sus características.</td> |
| **Criterios de Aceptación** | <td colspan="3">**Escenario 1: Modificación de inmueble por su propietario**<br>Dado que soy el agente que registró el inmueble y realizo ajustes en su descripción o características,<br>Cuando guardo las modificaciones,<br>Entonces el sistema actualiza la ficha del inmueble y me muestra la confirmación.<br><br>**Escenario 2: Intento de modificar un inmueble ajeno (Excepción de Privacidad)**<br>Dado que un usuario intenta modificar una propiedad registrada por otro agente,<br>Cuando intenta aplicar cambios,<br>Entonces el sistema bloquea la acción mostrando el mensaje "No autorizado para editar este inmueble".</td> |
| **Prioridad** | <td colspan="3">Media</td> |
| **Tiempo Estimado** | <td colspan="3">6 horas</td> |

| HU: | US-09 | Título: | Búsqueda y Filtrado de Inmuebles en la Cartera Propia |
| :--- | :--- | :--- | :--- |
| **Usuario:** | Agente Inmobiliario | **Sprint:** | 2 |
| **Descripción** | <td colspan="3">Como agente inmobiliario, quiero buscar y filtrar dentro de mis inmuebles por distrito, rango de precio o estado, para encontrar rápidamente las propiedades que necesito gestionar.</td> |
| **Criterios de Aceptación** | <td colspan="3">**Escenario 1: Filtrado exitoso de propiedades**<br>Dado que me encuentro en mi catálogo de propiedades e indico criterios como distrito o estado "Disponible",<br>Cuando aplico los filtros,<br>Entonces el sistema me muestra únicamente los inmuebles de mi propia cartera que coinciden con la búsqueda.<br><br>**Escenario 2: Rango de búsqueda inválido (Excepción)**<br>Dado que aplico un rango numérico ilógico donde el precio mínimo es mayor al máximo,<br>Cuando realizo la búsqueda,<br>Entonces el sistema me informa "Filtros inválidos" para que corrija los valores.</td> |
| **Prioridad** | <td colspan="3">Alta</td> |
| **Tiempo Estimado** | <td colspan="3">6 horas</td> |

| HU: | US-10 | Título: | Visualización de Ficha Detallada del Inmueble |
| :--- | :--- | :--- | :--- |
| **Usuario:** | Agente Inmobiliario | **Sprint:** | 2 |
| **Descripción** | <td colspan="3">Como agente inmobiliario, quiero ver la ficha completa de un inmueble de mi cartera para revisar todas sus variables antes de emitir una tasación.</td> |
| **Criterios de Aceptación** | <td colspan="3">**Escenario 1: Consulta de ficha de propiedad**<br>Dado que selecciono una de las propiedades de mi listado,<br>Cuando abro su ficha de detalle,<br>Entonces el sistema presenta todas las características del inmueble, su dirección y el mapa con su ubicación marcada.<br><br>**Escenario 2: Inmueble no disponible (Excepción)**<br>Dado que solicito ver un inmueble inexistente o dado de baja de mi cartera,<br>Cuando carga la pantalla,<br>Entonces el sistema muestra el aviso "Inmueble no encontrado".</td> |
| **Prioridad** | <td colspan="3">Alta</td> |
| **Tiempo Estimado** | <td colspan="3">4 horas</td> |

| HU: | US-11 | Título: | Cambio de Estado Comercial (Disponible, Vendido, Alquilado) |
| :--- | :--- | :--- | :--- |
| **Usuario:** | Agente Inmobiliario | **Sprint:** | 2 |
| **Descripción** | <td colspan="3">Como agente inmobiliario, quiero actualizar el estado comercial de una propiedad cuando se concrete su venta o arrendamiento para mantener mi inventario al día.</td> |
| **Criterios de Aceptación** | <td colspan="3">**Escenario 1: Actualización de estado comercial**<br>Dado que una propiedad disponible de mi cartera concreta su colocación comercial,<br>Cuando cambio su estado a "Vendido" o "Alquilado",<br>Entonces el sistema registra el nuevo estado y retira la propiedad del listado de inmuebles activos.<br><br>**Escenario 2: Estado repetido (Excepción)**<br>Dado que una propiedad ya figura con el estado "Vendido",<br>Cuando se intenta asignar nuevamente el mismo estado,<br>Entonces el sistema avisa "El inmueble ya tiene ese estado".</td> |
| **Prioridad** | <td colspan="3">Media</td> |
| **Tiempo Estimado** | <td colspan="3">3 horas</td> |

| HU: | US-12 | Título: | Desactivación de Inmueble Propio |
| :--- | :--- | :--- | :--- |
| **Usuario:** | Agente Inmobiliario | **Sprint:** | 2 |
| **Descripción** | <td colspan="3">Como agente inmobiliario, quiero retirar de mi vista activa una propiedad que ya no comercializo sin perder el historial de valoraciones pasadas.</td> |
| **Criterios de Aceptación** | <td colspan="3">**Escenario 1: Desactivación voluntaria**<br>Dado que elijo la opción de desactivar o retirar una propiedad de mi cartera,<br>Cuando confirmo el mensaje de advertencia,<br>Entonces la propiedad deja de aparecer en mis listados activos conservando su historial previo de tasaciones y reportes.<br><br>**Escenario 2: Propiedad con procesos activos (Excepción)**<br>Dado que el inmueble tiene una generación de reporte en curso,<br>Cuando intento desactivarlo,<br>Entonces el sistema avisa "No se puede desactivar: existe un proceso activo".</td> |
| **Prioridad** | <td colspan="3">Baja</td> |
| **Tiempo Estimado** | <td colspan="3">3 horas</td> |

---

### ÉPICA 03: Predicción de Valor Comercial de Venta con ML

| EP: | 03 | Título: | Predicción de Valor Comercial de Venta con ML |
| :--- | :--- | :--- | :--- |
| **Usuario:** | Agente Inmobiliario | **Sprint:** | 3 |
| **Descripción** | Como agente inmobiliario, deseo generar una tasación comercial automatizada de venta en dólares para un inmueble con base en sus atributos y variables de entorno, consultando además mi historial de tasaciones realizadas. | | |
| **Criterios de Aceptación** | - | | |
| **Prioridad** | Alta | | |
| **Tiempo Estimado** | 24 horas | | |

#### Historias de Usuario de la Épica 03

| HU: | US-13 | Título: | Ingreso de Datos del Inmueble para Tasación de Venta |
| :--- | :--- | :--- | :--- |
| **Usuario:** | Agente Inmobiliario | **Sprint:** | 3 |
| **Descripción** | <td colspan="3">Como agente inmobiliario, quiero ingresar o precargar los datos de una propiedad para solicitar la estimación de su valor comercial de venta.</td> |
| **Criterios de Aceptación** | <td colspan="3">**Escenario 1: Validación y envío de datos**<br>Dado que cargo las características del inmueble (metraje, ubicación, antigüedad, comodidades),<br>Cuando presiono "Estimar Valor de Venta",<br>Entonces el sistema valida que los datos se encuentren completos y dentro de valores lógicos de mercado para procesar la estimación.<br><br>**Escenario 2: Datos numéricos fuera de rango (Excepción)**<br>Dado que se ingresa un área en cero o una ubicación geográfica no válida,<br>Cuando intento solicitar la tasación,<br>Entonces el sistema detiene el proceso y muestra el mensaje "Datos de entrada inválidos para predicción".</td> |
| **Prioridad** | <td colspan="3">Alta</td> |
| **Tiempo Estimado** | <td colspan="3">6 horas</td> |

| HU: | US-14 | Título: | Obtención de Precio de Venta Comercial Estimado |
| :--- | :--- | :--- | :--- |
| **Usuario:** | Agente Inmobiliario | **Sprint:** | 3 |
| **Descripción** | <td colspan="3">Como agente inmobiliario, quiero visualizar el precio de venta sugerido en dólares y el valor por metro cuadrado estimado para fundamentar mi propuesta con el cliente.</td> |
| **Criterios de Aceptación** | <td colspan="3">**Escenario 1: Presentación del resultado de tasación**<br>Dado que los datos fueron enviados a estimar,<br>Cuando el modelo completa el cálculo,<br>Entonces la pantalla muestra el valor comercial estimado en dólares, el precio por metro cuadrado y registra la tasación en mi historial.<br><br>**Escenario 2: Indisponibilidad del servicio de estimación (Excepción)**<br>Dado que el motor de tasación presenta una interrupción técnica,<br>Cuando intento solicitar la tasación,<br>Entonces el sistema muestra el aviso amigable "Servicio de predicción no disponible, intente más tarde".</td> |
| **Prioridad** | <td colspan="3">Alta</td> |
| **Tiempo Estimado** | <td colspan="3">10 horas</td> |

| HU: | US-15 | Título: | Consulta de Historial de Tasaciones de Venta |
| :--- | :--- | :--- | :--- |
| **Usuario:** | Agente Inmobiliario | **Sprint:** | 3 |
| **Descripción** | <td colspan="3">Como agente inmobiliario, quiero revisar la lista histórica de mis valoraciones de venta previas para hacer seguimiento comercial a mis propiedades.</td> |
| **Criterios de Aceptación** | <td colspan="3">**Escenario 1: Visualización de tasaciones realizadas**<br>Dado que accedo a la sección "Historial de Tasaciones de Venta",<br>Cuando la pantalla carga,<br>Entonces se muestran únicamente las tasaciones que yo he generado, con su fecha, dirección del inmueble y valor estimado.<br><br>**Escenario 2: Historial vacío (Excepción)**<br>Dado que no cuento aún con valoraciones de venta realizadas,<br>Cuando entro al historial,<br>Entonces el sistema muestra el aviso "No hay predicciones registradas".</td> |
| **Prioridad** | <td colspan="3">Media</td> |
| **Tiempo Estimado** | <td colspan="3">8 horas</td> |

---

### ÉPICA 04: Predicción de Alquiler Mensual con ML

| EP: | 04 | Título: | Predicción de Alquiler Mensual con ML |
| :--- | :--- | :--- | :--- |
| **Usuario:** | Agente Inmobiliario | **Sprint:** | 4 |
| **Descripción** | Como agente inmobiliario, deseo estimar el canon de arrendamiento mensual en dólares de una propiedad mediante modelos de Inteligencia Artificial, para evaluar escenarios de renta e integrarlo al análisis de rentabilidad. | | |
| **Criterios de Aceptación** | - | | |
| **Prioridad** | Alta | | |
| **Tiempo Estimado** | 18 horas | | |

#### Historias de Usuario de la Épica 04

| HU: | US-16 | Título: | Obtención de Estimación de Alquiler Mensual |
| :--- | :--- | :--- | :--- |
| **Usuario:** | Agente Inmobiliario | **Sprint:** | 4 |
| **Descripción** | <td colspan="3">Como agente inmobiliario, quiero estimar el valor mensual de arrendamiento en dólares de un inmueble para asesorar a propietarios e inquilinos sobre el precio de renta adecuado.</td> |
| **Criterios de Aceptación** | <td colspan="3">**Escenario 1: Estimación de canon de alquiler**<br>Dado que envío las características de la propiedad para evaluar su renta,<br>Cuando el sistema procesa la estimación,<br>Entonces la pantalla presenta el canon de alquiler mensual estimado en dólares y almacena el resultado en mi historial personal.<br><br>**Escenario 2: Falla en la estimación de renta (Excepción)**<br>Dado que los datos de entrada presentan inconsistencias para el cálculo de alquiler,<br>Cuando se solicita la estimación,<br>Entonces el sistema informa "No se pudo calcular la predicción de alquiler".</td> |
| **Prioridad** | <td colspan="3">Alta</td> |
| **Tiempo Estimado** | <td colspan="3">10 horas</td> |

| HU: | US-17 | Título: | Consulta de Historial de Estimaciones de Alquiler |
| :--- | :--- | :--- | :--- |
| **Usuario:** | Agente Inmobiliario | **Sprint:** | 4 |
| **Descripción** | <td colspan="3">Como agente inmobiliario, quiero consultar el registro histórico de mis estimaciones de alquiler realizadas para revisar las valoraciones emitidas.</td> |
| **Criterios de Aceptación** | <td colspan="3">**Escenario 1: Listado de valoraciones de alquiler propias**<br>Dado que ingreso al historial de estimaciones de alquiler,<br>Cuando carga la vista,<br>Entonces el sistema me muestra la relación de alquileres estimados en mi cuenta, ordenados por fecha.<br><br>**Escenario 2: Historial de alquiler sin registros (Excepción)**<br>Dado que no he realizado valoraciones de alquiler previas,<br>Cuando accedo a la sección,<br>Entonces la interfaz presenta el mensaje "No hay predicciones de alquiler registradas".</td> |
| **Prioridad** | <td colspan="3">Media</td> |
| **Tiempo Estimado** | <td colspan="3">8 horas</td> |

---

### ÉPICA 05: Explicabilidad de Modelos con SHAP

| EP: | 05 | Título: | Explicabilidad de Modelos con SHAP |
| :--- | :--- | :--- | :--- |
| **Usuario:** | Agente Inmobiliario | **Sprint:** | 4 |
| **Descripción** | Como agente inmobiliario, deseo visualizar de forma clara y gráfica qué características del inmueble (área, ubicación, servicios cercanos, antigüedad) sumaron o restaron al precio final estimado, para explicar con transparencia el resultado a mis clientes. | | |
| **Criterios de Aceptación** | - | | |
| **Prioridad** | Alta | | |
| **Tiempo Estimado** | 20 horas | | |

#### Historias de Usuario de la Épica 05

| HU: | US-18 | Título: | Visualización de Factores Influyentes en el Precio de Venta |
| :--- | :--- | :--- | :--- |
| **Usuario:** | Agente Inmobiliario | **Sprint:** | 4 |
| **Descripción** | <td colspan="3">Como agente inmobiliario, quiero observar qué variables incrementaron o disminuyeron el valor de venta estimado para justificar el precio ante el cliente de forma objetiva.</td> |
| **Criterios de Aceptación** | <td colspan="3">**Escenario 1: Gráfico comprensible de factores de precio**<br>Dado que he obtenido una estimación de venta exitosa,<br>Cuando selecciono "Ver Explicación del Precio",<br>Entonces la plataforma me presenta un gráfico claro que muestra el impacto en dólares de las características más influyentes (metraje, cercanía a transporte, antigüedad).<br><br>**Escenario 2: Explicación no disponible (Excepción)**<br>Dado que se consulta una estimación histórica que no cuenta con desglose de factores,<br>Cuando intento abrir la explicación,<br>Entonces el sistema informa "Explicación no disponible para esta predicción".</td> |
| **Prioridad** | <td colspan="3">Alta</td> |
| **Tiempo Estimado** | <td colspan="3">10 horas</td> |

| HU: | US-19 | Título: | Visualización de Factores Influyentes en el Canon de Alquiler |
| :--- | :--- | :--- | :--- |
| **Usuario:** | Agente Inmobiliario | **Sprint:** | 4 |
| **Descripción** | <td colspan="3">Como agente inmobiliario, quiero ver los atributos que más incidieron en el monto de alquiler estimado para sustentar la mensualidad con el arrendador.</td> |
| **Criterios de Aceptación** | <td colspan="3">**Escenario 1: Visualización de factores de alquiler**<br>Dado que se cuenta con una estimación de alquiler vigente,<br>Cuando pulso en consultar el desglose de factores,<br>Entonces la pantalla despliega la lista gráfica de atributos que determinaron el valor de la renta.<br><br>**Escenario 2: Error al cargar el desglose (Excepción)**<br>Dado que ocurre un problema al procesar los datos de explicación de alquiler,<br>Cuando ingreso al panel,<br>Entonces la interfaz muestra "No se pudo cargar la explicación del modelo".</td> |
| **Prioridad** | <td colspan="3">Media</td> |
| **Tiempo Estimado** | <td colspan="3">10 horas</td> |

---

### ÉPICA 06: Análisis de Rentabilidad (Cap Rate)

| EP: | 06 | Título: | Análisis de Rentabilidad (Cap Rate) |
| :--- | :--- | :--- | :--- |
| **Usuario:** | Agente Inmobiliario | **Sprint:** | 5 |
| **Descripción** | Como agente inmobiliario, deseo calcular la tasa de rentabilidad anual neta (Cap Rate) sobre una propiedad considerando el alquiler estimado y los gastos operativos, incluyendo un aviso que aclare la diferencia entre compra al contado y con crédito hipotecario. | | |
| **Criterios de Aceptación** | - | | |
| **Prioridad** | Alta | | |
| **Tiempo Estimado** | 22 horas | | |

#### Historias de Usuario de la Épica 06

| HU: | US-20 | Título: | Cálculo Automatizado de Rentabilidad Anual (Cap Rate) |
| :--- | :--- | :--- | :--- |
| **Usuario:** | Agente Inmobiliario | **Sprint:** | 5 |
| **Descripción** | <td colspan="3">Como agente inmobiliario, quiero calcular el porcentaje de rentabilidad anual neta (Cap Rate) de una propiedad obteniendo automáticamente el alquiler proyectado para asesorar a inversionistas al contado.</td> |
| **Criterios de Aceptación** | <td colspan="3">**Escenario 1: Cálculo exitoso de rentabilidad**<br>Dado que indico el valor de la propiedad y los gastos proyectados (mantenimiento y desocupación anual),<br>Cuando presiono "Calcular Rentabilidad",<br>Entonces el sistema obtiene automáticamente el alquiler mensual proyectado, calcula el porcentaje de rentabilidad anual neta sobre el valor del inmueble y guarda la simulación en mi historial.<br><br>**Escenario 2: Valor del inmueble inválido (Excepción)**<br>Dado que se ingresa un valor de propiedad igual a cero o negativo,<br>Cuando intento calcular el porcentaje,<br>Entonces el sistema bloquea el cálculo y notifica "El valor del inmueble debe ser mayor a cero".</td> |
| **Prioridad** | <td colspan="3">Alta</td> |
| **Tiempo Estimado** | <td colspan="3">12 horas</td> |

| HU: | US-21 | Título: | Visualización de Aviso Informativo sobre Financiamiento Hipotecario |
| :--- | :--- | :--- | :--- |
| **Usuario:** | Agente Inmobiliario | **Sprint:** | 5 |
| **Descripción** | <td colspan="3">Como agente inmobiliario, quiero que en la pantalla de rentabilidad se muestre un aviso explicativo visible indicando que el Cap Rate representa una compra al contado, para no confundir a clientes que compran con crédito hipotecario.</td> |
| **Criterios de Aceptación** | <td colspan="3">**Escenario 1: Aviso visible de compra al contado vs financiamiento**<br>Dado que se presentan los resultados del Cap Rate en pantalla,<br>Cuando el usuario visualiza el porcentaje obtenido,<br>Entonces la interfaz muestra de forma permanente una tarjeta informativa que aclara: *"Este indicador refleja el rendimiento para una compra al contado sin financiamiento; si el comprador utiliza crédito hipotecario, el retorno real de su capital variará de acuerdo a las cuotas de su préstamo"*, junto con el desglose de ingresos y gastos utilizados.<br><br>**Escenario 2: Consulta de ayuda sobre el indicador**<br>Dado que el usuario hace clic en el ícono de ayuda del indicador,<br>Cuando se abre el cuadro explicativo,<br>Entonces se expone la definición práctica del concepto de rentabilidad para orientar la conversación con el cliente.</td> |
| **Prioridad** | <td colspan="3">Alta</td> |
| **Tiempo Estimado** | <td colspan="3">10 horas</td> |

---

### ÉPICA 07: Generación de Reportes de Tasación

| EP: | 07 | Título: | Generación de Reportes de Tasación |
| :--- | :--- | :--- | :--- |
| **Usuario:** | Agente Inmobiliario | **Sprint:** | 5 |
| **Descripción** | Como agente inmobiliario, deseo generar y descargar reportes comerciales profesionales en PDF con la ficha de la propiedad, las tasaciones, la explicación gráfica y la rentabilidad calculada, para entregárselos a mis clientes como sustento. | | |
| **Criterios de Aceptación** | - | | |
| **Prioridad** | Alta | | |
| **Tiempo Estimado** | 20 horas | | |

#### Historias de Usuario de la Épica 07

| HU: | US-22 | Título: | Generación de Reporte Comercial en Formato PDF |
| :--- | :--- | :--- | :--- |
| **Usuario:** | Agente Inmobiliario | **Sprint:** | 5 |
| **Descripción** | <td colspan="3">Como agente inmobiliario, quiero compilar en un documento PDF la información del inmueble, el precio estimado, el análisis de factores y la rentabilidad calculada.</td> |
| **Criterios de Aceptación** | <td colspan="3">**Escenario 1: Generación exitosa de informe PDF**<br>Dado que el inmueble cuenta con tasación y datos de rentabilidad completados,<br>Cuando selecciono "Generar Reporte PDF",<br>Entonces el sistema elabora un documento formal con diseño ejecutivo, fecha de emisión, datos del agente y resumen de la propiedad.<br><br>**Escenario 2: Datos insuficientes para generar informe (Excepción)**<br>Dado que el inmueble aún no cuenta con una tasación de venta realizada,<br>Cuando intento generar el reporte,<br>Entonces el sistema detiene la acción avisando "Información insuficiente para generar el reporte".</td> |
| **Prioridad** | <td colspan="3">Alta</td> |
| **Tiempo Estimado** | <td colspan="3">12 horas</td> |

| HU: | US-23 | Título: | Descarga y Compartición del Reporte Comercial |
| :--- | :--- | :--- | :--- |
| **Usuario:** | Agente Inmobiliario | **Sprint:** | 5 |
| **Descripción** | <td colspan="3">Como agente inmobiliario, quiero descargar el PDF generado o compartirlo directamente para entregarlo a propietarios y compradores interesados.</td> |
| **Criterios de Aceptación** | <td colspan="3">**Escenario 1: Descarga exitosa del archivo**<br>Dado que he generado un reporte propio,<br>Cuando presiono "Descargar PDF",<br>Entonces el sistema descarga el archivo en mi equipo para su impresión o envío.<br><br>**Escenario 2: Reporte no disponible o sin acceso (Excepción)**<br>Dado que se intenta acceder a un reporte que no pertenece a mi cuenta o fue eliminado,<br>Cuando se solicita la descarga,<br>Entonces el sistema deniega el acceso mostrando "Reporte no encontrado o sin permisos".</td> |
| **Prioridad** | <td colspan="3">Media</td> |
| **Tiempo Estimado** | <td colspan="3">8 horas</td> |

---

### ÉPICA 08: Supervisión y Monitoreo del Modelo (MLOps)

| EP: | 08 | Título: | Supervisión y Monitoreo del Modelo (MLOps) |
| :--- | :--- | :--- | :--- |
| **Usuario:** | Administrador del Sistema | **Sprint:** | 6 |
| **Descripción** | Como administrador del sistema, deseo supervisar las métricas de precisión de los modelos de tasación en un panel de control y contar con la potestad de aprobar o revertir reentrenamientos, asegurando la calidad continua de las estimaciones. | | |
| **Criterios de Aceptación** | - | | |
| **Prioridad** | Alta | | |
| **Tiempo Estimado** | 20 horas | | |

#### Historias de Usuario de la Épica 08

| HU: | US-05 | Título: | Visualización del Panel de Métricas del Modelo |
| :--- | :--- | :--- | :--- |
| **Usuario:** | Administrador del Sistema | **Sprint:** | 6 |
| **Descripción** | <td colspan="3">Como administrador, quiero revisar un panel de control con los indicadores de error y desempeño de los modelos de venta y alquiler para supervisar la calidad de las predicciones.</td> |
| **Criterios de Aceptación** | <td colspan="3">**Escenario 1: Consulta del panel de métricas**<br>Dado que he ingresado a la plataforma con rol de Administrador y abro la sección de monitoreo,<br>Cuando la pantalla carga,<br>Entonces se muestran los valores actuales de precisión y error de los modelos activos frente a los umbrales requeridos.<br><br>**Escenario 2: Intento de ingreso por usuario sin privilegios (Excepción)**<br>Dado que un usuario con rol de Agente intenta ingresar al panel de monitoreo,<br>Cuando intenta entrar a la ruta de administración,<br>Entonces el sistema deniega el acceso informando "No tienes permisos para esta acción".</td> |
| **Prioridad** | <td colspan="3">Alta</td> |
| **Tiempo Estimado** | <td colspan="3">10 horas</td> |

| HU: | US-06 | Título: | Aprobación o Reversión de Versión del Modelo |
| :--- | :--- | :--- | :--- |
| **Usuario:** | Administrador del Sistema | **Sprint:** | 6 |
| **Descripción** | <td colspan="3">Como administrador, quiero aprobar la actualización de un modelo reentrenado o revertir a la versión anterior en caso de requerirlo para mantener la estabilidad del sistema.</td> |
| **Criterios de Aceptación** | <td colspan="3">**Escenario 1: Aprobación de nuevo modelo reentrenado**<br>Dado que se ha completado un reentrenamiento que mejora la precisión del modelo actual,<br>Cuando el administrador presiona "Aprobar Versión",<br>Entonces el sistema promueve la nueva versión del modelo para que los agentes coticen con ella de inmediato sin interrumpir el servicio.<br><br>**Escenario 2: Falta de versión candidata (Excepción)**<br>Dado que no existe ningún modelo candidato pendiente de aprobación,<br>Cuando el administrador intenta realizar una actualización,<br>Entonces el sistema deshabilita la opción mostrando "No hay versión de modelo disponible para esta operación".</td> |
| **Prioridad** | <td colspan="3">Alta</td> |
| **Tiempo Estimado** | <td colspan="3">10 horas</td> |

---

### ÉPICA 09: Pipeline de Ingestión ETL y Datos de Entorno

| EP: | 09 | Título: | Pipeline de Ingestión ETL y Datos de Entorno |
| :--- | :--- | :--- | :--- |
| **Usuario:** | Equipo de Desarrollo y Datos | **Sprint:** | 1 - 2 |
| **Descripción** | Como equipo de ingeniería de datos, deseamos implementar procesos de extracción, transformación y carga sobre fuentes oficiales abiertas (INEI, BCRP, distancias OpenStreetMap y criminalidad distrital), consolidando un repositorio analítico limpio y libre de sesgos. | | |
| **Criterios de Aceptación** | - | | |
| **Prioridad** | Alta | | |
| **Tiempo Estimado** | 40 horas | | |

#### Historias Técnicas de la Épica 09

| HU: | TH-08 | Título: | Ingesta y Consolidación de Indicadores Sociodemográficos INEI/NSE |
| :--- | :--- | :--- | :--- |
| **Usuario:** | Equipo de Desarrollo / Datos | **Sprint:** | 1 |
| **Descripción** | <td colspan="3">Como ingeniero de datos, quiero estructurar la información socioeconómica distrital del INEI (estratos NSE, densidad y cobertura) para vincularla a los datos geográficos de los inmuebles.</td> |
| **Criterios de Aceptación** | <td colspan="3">**Escenario 1: Acoplamiento de variables socioeconómicas**<br>Dado el dataset censal del INEI para distritos de Lima Metropolitana,<br>Cuando corre el script de transformación ETL,<br>Entonces se vinculan los porcentajes de nivel socioeconómico por distrito asegurando la consistencia de los registros.<br><br>**Escenario 2: Inconsistencia en catálogo distrital (Excepción)**<br>Dado que se detectan diferencias en nombres o códigos distritales entre fuentes,<br>Cuando corre la validación de llaves geográficas,<br>Entonces el pipeline detiene el proceso informando "Inconsistencia de llaves geográficas en INEI/NSE".</td> |
| **Prioridad** | <td colspan="3">Alta</td> |
| **Tiempo Estimado** | <td colspan="3">6 horas</td> |

| HU: | TH-09 | Título: | Ingesta de Series Macroeconómicas BCRP y Criminalidad Distrital |
| :--- | :--- | :--- | :--- |
| **Usuario:** | Equipo de Desarrollo / Datos | **Sprint:** | 1 |
| **Descripción** | <td colspan="3">Como ingeniero de datos, quiero integrar las series históricas del BCRP (2016–2025) y los índices distritales de seguridad para incorporar el contexto macroeconómico y de criminalidad en los modelos.</td> |
| **Criterios de Aceptación** | <td colspan="3">**Escenario 1: Normalización temporal con IPC y criminalidad**<br>Dado el histórico de precios y series económicas mensuales del BCRP y datos de criminalidad distrital,<br>Cuando se aplica el factor de deflactación por inflación (IPC),<br>Entonces los precios se estandarizan a moneda constante y se integran los índices de criminalidad por zona.<br><br>**Escenario 2: Falta de indicadores en el periodo (Excepción)**<br>Dado que una fuente oficial carece de registros para un periodo determinado,<br>Cuando se intenta procesar el lote,<br>Entonces el sistema detiene la ingesta emitiendo la alerta "Datos de criminalidad no disponibles o desactualizados".</td> |
| **Prioridad** | <td colspan="3">Alta</td> |
| **Tiempo Estimado** | <td colspan="3">8 horas</td> |

| HU: | TH-10 | Título: | Cálculo Automatizado de Distancias Geodésicas vía OpenStreetMap |
| :--- | :--- | :--- | :--- |
| **Usuario:** | Equipo de Desarrollo / Datos | **Sprint:** | 2 |
| **Descripción** | <td colspan="3">Como ingeniero de datos, quiero calcular mediante fórmulas geodésicas las distancias desde cada coordenada hacia estaciones de transporte, colegios y parques usando datos vectoriales abiertos de OpenStreetMap.</td> |
| **Criterios de Aceptación** | <td colspan="3">**Escenario 1: Derivación de distancias a amenidades urbanas**<br>Dado un conjunto de coordenadas geográficas de inmuebles,<br>Cuando corre el procesamiento espacial contra la cartografía de OpenStreetMap,<br>Entonces se generan las columnas de distancias en metros a las amenidades urbanas más cercanas.<br><br>**Escenario 2: Coordenadas geográficas fuera de rango (Excepción)**<br>Dado que una fila presenta coordenadas nulas o fuera del ámbito metropolitano,<br>Cuando el algoritmo calcula distancias,<br>Entonces omite el registro defectuoso y emite el mensaje "Coordenadas inválidas".</td> |
| **Prioridad** | <td colspan="3">Alta</td> |
| **Tiempo Estimado** | <td colspan="3">8 horas</td> |

| HU: | TH-11 | Título: | Consolidación y Validación de Calidad en Tabla Analítica Unificada |
| :--- | :--- | :--- | :--- |
| **Usuario:** | Equipo de Desarrollo / Datos | **Sprint:** | 2 |
| **Descripción** | <td colspan="3">Como ingeniero de datos, quiero unir las variables físicas, macroeconómicas y espaciales en una tabla analítica consolidada asegurando que no existan valores vacíos excesivos.</td> |
| **Criterios de Aceptación** | <td colspan="3">**Escenario 1: Validación exitosa de tabla de entrenamiento**<br>Dado que culminaron las extracciones de fuentes oficiales y espaciales,<br>Cuando se consolida la tabla final de análisis,<br>Entonces se certifica que las columnas clave cumplan las distribuciones estadísticas y los estándares de calidad definidos.<br><br>**Escenario 2: Tasa elevada de desajuste geográfico (Excepción)**<br>Dado que el cruce de tablas espaciales supera el 5% de registros sin coincidencia distrital,<br>Cuando concluye la validación,<br>Entonces el proceso aborta reportando "Falló validación geoespacial: no-match elevado".</td> |
| **Prioridad** | <td colspan="3">Alta</td> |
| **Tiempo Estimado** | <td colspan="3">6 horas</td> |

| HU: | TH-12 | Título: | Deduplicación y Depuración de Calidad de Datos Inmobiliarios |
| :--- | :--- | :--- | :--- |
| **Usuario:** | Equipo de Desarrollo / Datos | **Sprint:** | 2 |
| **Descripción** | <td colspan="3">Como ingeniero de datos, quiero implementar reglas de depuración y deduplicación para garantizar que una misma propiedad no figure duplicada en los conjuntos de datos.</td> |
| **Criterios de Aceptación** | <td colspan="3">**Escenario 1: Detección y depuración de duplicados**<br>Dado un conjunto de registros donde coinciden ubicación espacial cercana, área y características idénticas,<br>Cuando se aplica la rutina de deduplicación,<br>Entonces se conserva la entrada más confiable y se purgan duplicados dejando constancia en los logs del proceso.<br><br>**Escenario 2: Ausencia de identificador unívoco (Excepción)**<br>Dado que no se cuenta con identificador único estandarizado en la fuente,<br>Cuando corre la depuración,<br>Entonces el sistema aplica reglas de similitud geométrica informando "Deduplicación por ID no disponible, se aplicó regla alternativa".</td> |
| **Prioridad** | <td colspan="3">Media</td> |
| **Tiempo Estimado** | <td colspan="3">6 horas</td> |

| HU: | TH-13 | Título: | Pipeline ETL Incremental Automatizado para Actualización Periódica |
| :--- | :--- | :--- | :--- |
| **Usuario:** | Equipo de Desarrollo / Datos | **Sprint:** | 2 |
| **Descripción** | <td colspan="3">Como ingeniero de datos, quiero estructurar el pipeline de carga para incorporar nuevos lotes de información periódica sin sobrescribir ni alterar los datos históricos ya consolidados.</td> |
| **Criterios de Aceptación** | <td colspan="3">**Escenario 1: Carga incremental de nuevos periodos**<br>Dado que se dispone de una nueva actualización periódica de variables macroeconómicas e inmobiliarias,<br>Cuando se ejecuta la rutina ETL,<br>Entonces los registros se agregan al repositorio con su código de versión sin afectar el historial existente.<br><br>**Escenario 2: Estructura de lote incompatible (Excepción)**<br>Dado que un archivo de actualización presenta un formato de columnas distinto al histórico,<br>Cuando el proceso verifica el esquema,<br>Entonces la carga se interrumpe emitiendo la alerta "Incompatibilidad de esquema entre lote nuevo e histórico".</td> |
| **Prioridad** | <td colspan="3">Media</td> |
| **Tiempo Estimado** | <td colspan="3">6 horas</td> |

---

### ÉPICA 10: Modelado Predictivo, Versionado y Reentrenamiento

| EP: | 10 | Título: | Modelado Predictivo, Versionado y Reentrenamiento |
| :--- | :--- | :--- | :--- |
| **Usuario:** | Equipo de Desarrollo y Machine Learning | **Sprint:** | 3 - 6 |
| **Descripción** | Como equipo de Machine Learning, deseamos implementar el preprocesamiento, entrenamiento y evaluación de los algoritmos XGBoost para venta y alquiler, registrando experimentos en MLflow y estructurando el flujo de reentrenamiento periódico. | | |
| **Criterios de Aceptación** | - | | |
| **Prioridad** | Alta | | |
| **Tiempo Estimado** | 46 horas | | |

#### Historias Técnicas de la Épica 10

| HU: | TH-01 | Título: | Preprocesar Datos para Modelo de Venta |
| :--- | :--- | :--- | :--- |
| **Usuario:** | Equipo de Desarrollo / ML | **Sprint:** | 3 |
| **Descripción** | <td colspan="3">Como científico de datos, quiero aplicar rutinas de imputación, codificación de variables categóricas y escalamiento sobre el dataset de venta inmobiliaria.</td> |
| **Criterios de Aceptación** | <td colspan="3">**Escenario 1: Transformación numérica completa**<br>Dado el conjunto de datos de venta depurado,<br>Cuando corre el pipeline de transformación numérica y categórica,<br>Entonces se genera la matriz lista para el entrenamiento del algoritmo y se guarda el transformador serializado.<br><br>**Escenario 2: Faltantes en variables críticas (Excepción)**<br>Dado que se identifican registros sin metraje o sin coordenadas distritales,<br>Cuando el preprocesador valida las columnas mínimas,<br>Entonces descarta las filas inválidas reportando "Esquema inválido: faltan variables requeridas".</td> |
| **Prioridad** | <td colspan="3">Alta</td> |
| **Tiempo Estimado** | <td colspan="3">6 horas</td> |

| HU: | TH-02 | Título: | Entrenar Modelo XGBoost para Valor de Venta |
| :--- | :--- | :--- | :--- |
| **Usuario:** | Equipo de Desarrollo / ML | **Sprint:** | 3 |
| **Descripción** | <td colspan="3">Como científico de datos, quiero optimizar y entrenar el modelo XGBoost Regressor mediante validación cruzada para predecir el valor de venta en dólares.</td> |
| **Criterios de Aceptación** | <td colspan="3">**Escenario 1: Entrenamiento y convergencia satisfactoria**<br>Dado el conjunto de entrenamiento de venta preparado,<br>Cuando se ejecuta el entrenamiento de XGBoost con parada temprana,<br>Entonces el algoritmo converge minimizando la función de error y se genera el modelo entrenado.<br><br>**Escenario 2: Datos insuficientes para entrenar (Excepción)**<br>Dado que el conjunto filtrado queda por debajo de las muestras mínimas representativas,<br>Cuando inicia el proceso de entrenamiento,<br>Entonces el sistema detiene la ejecución mostrando "No hay datos suficientes para entrenar".</td> |
| **Prioridad** | <td colspan="3">Alta</td> |
| **Tiempo Estimado** | <td colspan="3">8 horas</td> |

| HU: | TH-03 | Título: | Evaluar Modelo de Venta contra Métricas Objetivo (MAE, RMSE, MAPE) |
| :--- | :--- | :--- | :--- |
| **Usuario:** | Equipo de Desarrollo / ML | **Sprint:** | 3 |
| **Descripción** | <td colspan="3">Como científico de datos, quiero calcular las métricas cuantitativas de error (MAE, RMSE y MAPE) sobre el conjunto de prueba para verificar que el modelo cumple los estándares esperados.</td> |
| **Criterios de Aceptación** | <td colspan="3">**Escenario 1: Aprobación de métricas de precisión**<br>Dado el modelo de venta entrenado y el conjunto de prueba retenido,<br>Cuando se evalúa el rendimiento predictivo,<br>Entonces se verifica un error porcentual absoluto medio ($MAPE \le 12\%$) y se registran las métricas obtenidas.<br><br>**Escenario 2: Presencia de valores infinitos o nulos (Excepción)**<br>Dado que la evaluación arroja valores numéricos corruptos en las métricas de error,<br>Cuando concluye la evaluación,<br>Entonces el proceso se interrumpe emitiendo la alerta "Métricas inválidas en evaluación".</td> |
| **Prioridad** | <td colspan="3">Alta</td> |
| **Tiempo Estimado** | <td colspan="3">6 horas</td> |

| HU: | TH-04 | Título: | Preprocesar Datos para Modelo de Canon de Alquiler |
| :--- | :--- | :--- | :--- |
| **Usuario:** | Equipo de Desarrollo / ML | **Sprint:** | 4 |
| **Descripción** | <td colspan="3">Como científico de datos, quiero estructurar el proceso de limpieza y transformación de variables para el conjunto de datos enfocado en alquiler mensual.</td> |
| **Criterios de Aceptación** | <td colspan="3">**Escenario 1: Matriz de alquiler preparada**<br>Dado el histórico de operaciones y ofertas de alquiler,<br>Cuando se ejecuta la preparación de datos,<br>Entonces se obtiene la matriz numérica estandarizada para entrenar el modelo de renta.<br><br>**Escenario 2: Formatos incompatibles en alquiler (Excepción)**<br>Dado que ingresan registros con caracteres de texto no procesables en montos de alquiler,<br>Cuando corre la limpieza,<br>Entonces se descartan las filas corruptas reportando "Tipos de datos inválidos en entrada".</td> |
| **Prioridad** | <td colspan="3">Alta</td> |
| **Tiempo Estimado** | <td colspan="3">6 horas</td> |

| HU: | TH-05 | Título: | Entrenar Modelo XGBoost para Alquiler Mensual |
| :--- | :--- | :--- | :--- |
| **Usuario:** | Equipo de Desarrollo / ML | **Sprint:** | 4 |
| **Descripción** | <td colspan="3">Como científico de datos, quiero entrenar el modelo XGBoost especializado en predecir el monto mensual de arrendamiento en dólares.</td> |
| **Criterios de Aceptación** | <td colspan="3">**Escenario 1: Entrenamiento satisfactorio de alquiler**<br>Dado el dataset procesado de alquileres,<br>Cuando se entrena el algoritmo con las configuraciones optimizadas,<br>Entonces se obtiene el artefacto del modelo alcanzando convergencia en validación cruzada.<br><br>**Escenario 2: Límite de recursos excedido (Excepción)**<br>Dado que el proceso de entrenamiento excede los recursos de cómputo configurados,<br>Cuando el monitor del sistema detecta la situación,<br>Entonces se aborta el ciclo registrando "Entrenamiento interrumpido por límite de recursos".</td> |
| **Prioridad** | <td colspan="3">Alta</td> |
| **Tiempo Estimado** | <td colspan="3">8 horas</td> |

| HU: | TH-06 | Título: | Evaluar Modelo de Alquiler contra Métricas Objetivo (MAE, RMSE, MAPE) |
| :--- | :--- | :--- | :--- |
| **Usuario:** | Equipo de Desarrollo / ML | **Sprint:** | 4 |
| **Descripción** | <td colspan="3">Como científico de datos, quiero medir los errores de estimación del modelo de alquiler para comprobar su calidad antes de integrarlo al cálculo de rentabilidad.</td> |
| **Criterios de Aceptación** | <td colspan="3">**Escenario 1: Validación cuantitativa de alquiler**<br>Dado el modelo de renta evaluado en el conjunto de prueba independiente,<br>Cuando se calculan los errores predictivos,<br>Entonces se confirma un $MAPE \le 14\%$ registrando la aprobación técnica del modelo.<br><br>**Escenario 2: Conjunto de prueba ausente (Excepción)**<br>Dado que no se cuenta con datos de prueba etiquetados para alquiler,<br>Cuando se intenta evaluar,<br>Entonces se detiene el proceso emitiendo el mensaje "No hay datos de prueba para evaluar el modelo".</td> |
| **Prioridad** | <td colspan="3">Alta</td> |
| **Tiempo Estimado** | <td colspan="3">4 horas</td> |

| HU: | TH-07 | Título: | Versionado de Modelos y Tracking de Experimentos con MLflow |
| :--- | :--- | :--- | :--- |
| **Usuario:** | Equipo de Desarrollo / ML | **Sprint:** | 3 |
| **Descripción** | <td colspan="3">Como ingeniero de MLOps, quiero registrar parámetros, métricas y archivos binarios de cada entrenamiento en MLflow para garantizar la trazabilidad de cada versión del modelo.</td> |
| **Criterios de Aceptación** | <td colspan="3">**Escenario 1: Registro completo de versión en MLflow**<br>Dado que finaliza una ronda de entrenamiento de venta o alquiler,<br>Cuando el sistema envía las métricas y los modelos al repositorio de MLflow,<br>Entonces el experimento queda registrado con su número de versión, métricas (MAE, RMSE, MAPE) y artefactos listos para su uso.<br><br>**Escenario 2: Falla de comunicación con MLflow (Excepción)**<br>Dado que el servicio de MLflow no responde en la red,<br>Cuando se intenta registrar el experimento,<br>Entonces se genera un respaldo local informando "No se pudo registrar la versión del modelo en MLflow".</td> |
| **Prioridad** | <td colspan="3">Alta</td> |
| **Tiempo Estimado** | <td colspan="3">4 horas</td> |

| HU: | TH-14 | Título: | Pipeline de Reentrenamiento Continuo y Comparación Automática de Métricas |
| :--- | :--- | :--- | :--- |
| **Usuario:** | Equipo de Desarrollo / ML | **Sprint:** | 6 |
| **Descripción** | <td colspan="3">Como ingeniero de MLOps, quiero programar el flujo de reentrenamiento periódico para que compare las métricas del nuevo modelo contra el vigente y permita su promoción sin interrumpir el servicio.</td> |
| **Criterios de Aceptación** | <td colspan="3">**Escenario 1: Reentrenamiento con actualización de modelo sin caída**<br>Dado que finaliza el reentrenamiento y el modelo candidato es aprobado por el Administrador,<br>Cuando se emite la orden de actualización,<br>Entonces el sistema carga la nueva versión del modelo de inmediato manteniendo el servicio disponible para los usuarios.<br><br>**Escenario 2: Modelo candidato con menor precisión (Excepción)**<br>Dado que el nuevo modelo reentrenado presenta un error superior al modelo vigente en producción,<br>Cuando concluye la evaluación comparativa,<br>Entonces el sistema bloquea su promoción emitiendo la alerta "Modelo candidato rechazado por degradación de métricas".</td> |
| **Prioridad** | <td colspan="3">Alta</td> |
| **Tiempo Estimado** | <td colspan="3">4 horas</td> |

---

## 1.5.6 Sprint Backlog 1

El **Sprint 1** constituye el sprint fundacional del proyecto. Su propósito es habilitar la infraestructura base del sistema, implementando tanto el módulo de acceso y gestión de usuarios para los agentes inmobiliarios, como la ingesta y preparación de las primeras fuentes de datos oficiales para el futuro entrenamiento de los modelos predictivos.

### 1. Información General del Sprint 1

| Parámetro | Detalle |
| :--- | :--- |
| **Nombre del Sprint:** | Sprint 1: Fundamentos de Plataforma, Autenticación e Ingesta de Datos Oficiales |
| **Duración:** | 2 semanas (10 días laborables) |
| **Objetivo del Sprint (Sprint Goal):** | Implementar y validar el flujo integral de registro, autenticación y gestión de perfil de agentes inmobiliarios, junto con el pipeline de extracción y deflactación de series macroeconómicas del BCRP y datos sociodemográficos del INEI. |
| **Capacidad Total del Equipo:** | 40 horas laborables |
| **Carga Comprometida:** | 36 horas estimadas |
| **Historias Incluidas:** | 4 Historias de Usuario (US-01 a US-04) + 2 Historias Técnicas (TH-08 y TH-09) |

---

### 2. Tabla Consolidada de Historias del Sprint 1

| ID | Tipo | Título de la Historia | Prioridad | Tiempo Estimado | Responsable |
| :-: | :---: | :--- | :---: | :---: | :--- |
| **US-01** | US | Registro de Agente Inmobiliario | Alta | 6 h | Desarrollador Fullstack |
| **US-02** | US | Inicio de Sesión en la Plataforma | Alta | 6 h | Desarrollador Fullstack |
| **US-03** | US | Cierre de Sesión Seguro | Media | 4 h | Desarrollador Fullstack |
| **US-04** | US | Edición de Perfil Profesional | Baja | 6 h | Desarrollador Fullstack |
| **TH-08** | TH | Ingesta y Consolidación de Indicadores Sociodemográficos INEI/NSE | Alta | 6 h | Ingeniero de Datos |
| **TH-09** | TH | Ingesta de Series Macroeconómicas BCRP y Criminalidad Distrital | Alta | 8 h | Ingeniero de Datos |
| **TOTAL** | - | **6 Historias (4 US + 2 TH)** | - | **36 horas** | - |

---

### 3. Desglose de Tareas Técnicas por Historia (Work Breakdown)

A continuación se detalla la descomposición en tareas de ingeniería de software para cada historia seleccionada en el Sprint 1:

#### US-01: Registro de Agente Inmobiliario (6 h)
* **TSK-01.1 (Backend):** Crear entidad `Usuario`, repositorio JPA y servicio de registro con validación de correo único y encriptación de contraseña (2.5 h).
* **TSK-01.2 (Frontend):** Diseñar formulario reactivo en Angular con validaciones en tiempo real (correo válido, contraseña con longitud mínima y caracteres requeridos) (2.0 h).
* **TSK-01.3 (Testing):** Elaborar pruebas unitarias del servicio de registro y pruebas de integración del endpoint `POST /api/auth/register` (1.5 h).

#### US-02: Inicio de Sesión en la Plataforma (6 h)
* **TSK-02.1 (Backend):** Implementar filtro de autenticación, generación de token JWT con claims de rol/usuario y manejo de excepciones de credenciales (3.0 h).
* **TSK-02.2 (Frontend):** Desarrollar vista de login, almacenamiento seguro del token en el cliente y servicio de interceptor HTTP para adjuntar autorización (2.0 h).
* **TSK-02.3 (Testing):** Ejecutar pruebas de autenticación con credenciales válidas e inválidas, verificando respuestas y códigos de estado (1.0 h).

#### US-03: Cierre de Sesión Seguro (4 h)
* **TSK-03.1 (Frontend):** Implementar botón y acción de logout en la barra de navegación, limpiando estado local y redirigiendo a login (1.5 h).
* **TSK-03.2 (Frontend):** Configurar guardianes de ruta (*AuthGuard*) para impedir el acceso a vistas privadas tras el cierre de sesión (1.5 h).
* **TSK-03.3 (Testing):** Probar el intento de navegación hacia rutas protegidas luego de cerrar sesión (1.0 h).

#### US-04: Edición de Perfil Profesional (6 h)
* **TSK-04.1 (Backend):** Crear endpoint `PUT /api/usuarios/perfil` para actualizar teléfono y nombre del agente autenticado (2.0 h).
* **TSK-04.2 (Frontend):** Diseñar pantalla de "Mi Perfil" con precarga de datos actuales y formulario de actualización editable (2.5 h).
* **TSK-04.3 (Testing):** Validar actualización exitosa y rechazo ante formatos telefónicos inválidos (1.5 h).

#### TH-08: Ingesta y Consolidación de Indicadores Sociodemográficos INEI/NSE (6 h)
* **TSK-08.1 (Datos):** Descargar y estructurar los microdatos censales de estratos socioeconómicos (NSE A, B, C, D) por distrito de Lima Metropolitana (2.5 h).
* **TSK-08.2 (Datos):** Construir script en Python para normalizar ubigeos y realizar el join geográfico con el catálogo distrital maestro (2.0 h).
* **TSK-08.3 (Testing):** Validar completitud de datos distritales y ausencia de valores nulos en el 100% de los 43 distritos (1.5 h).

#### TH-09: Ingesta de Series Macroeconómicas BCRP y Criminalidad Distrital (8 h)
* **TSK-09.1 (Datos):** Extraer series mensuales oficiales del BCRP (2016–2025): tasa de interés de referencia, tipo de cambio e Índice de Precios al Consumidor (IPC) (2.5 h).
* **TSK-09.2 (Datos):** Implementar función de deflactación de precios históricos para convertir series a moneda constante de referencia (3.0 h).
* **TSK-09.3 (Datos):** Recopilar y acoplar las tasas distritales de denuncias por comisión de delitos reportadas en fuentes oficiales (1.5 h).
* **TSK-09.4 (Testing):** Contrastar la serie deflactada con los reportes oficiales del BCRP para certificar la precisión del cálculo inflacionario (1.0 h).

---

### 4. Definición de Terminado (Definition of Done - DoD) del Sprint 1

Para que una historia de usuario o técnica se considere formalmente **Terminada** al cierre del Sprint 1, debe cumplir los siguientes criterios de calidad:
1. **Código y Estilo:** Código fuente escrito siguiendo los estándares de diseño del proyecto, sin errores de compilación ni advertencias críticas de linter.
2. **Pruebas Unitarias:** Cobertura de pruebas unitarias superior al 70% en los servicios de negocio desarrollados.
3. **Criterios de Aceptación Cumplidos:** Todos los escenarios descritos en la ficha de la historia (flujo exitoso y excepciones) superados exitosamente.
4. **Control de Versiones:** Cambios integrados en la rama principal (`main` o `develop`) mediante *Pull Request* revisado y aprobado.
5. **Datos Verificados:** Los datasets de INEI y BCRP procesados se encuentran consolidados y con calidad de esquema validada.

