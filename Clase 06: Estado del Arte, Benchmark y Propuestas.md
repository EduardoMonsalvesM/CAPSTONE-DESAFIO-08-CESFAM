# Clase 06: Estado del Arte, Benchmark y Propuestas Conceptuales

## 1. Análisis del Estado del Arte

**Definición del Problema:** Los usuarios del CESFAM Providencia (Usuario + Contexto) necesitan confirmar, cancelar o reagendar sus citas médicas de forma rápida y autónoma desde sus dispositivos móviles para no perder horas de atención (Necesidad), pero los mecanismos actuales (atención telefónica, presencial y WhatsApp atendido manualmente) generan cuellos de botella operativos que solo logran gestionar entre un 30% y un 40% de las cancelaciones, derivando en un alto porcentaje de horas médicas perdidas.

### Tabla de Análisis: Soluciones Existentes

| N° | Problema que aborda | Nombre de la Solución | Descripción Breve | ¿Quién la hizo / usa? | ¿Cómo soluciona el problema? | Link Fuente |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **1** | Saturación de filas presenciales y necesidad de ingresar solicitudes de forma remota sin desplazarse al consultorio. | **TeleSalud (MINSAL)** | Plataforma web oficial del Ministerio de Salud de Chile para el ingreso remoto de solicitudes de atención médica, matronería y controles en APS. | Creada por el Ministerio de Salud (MINSAL) e implementada en los CESFAM de Providencia (ej. El Aguilucho y Dr. Hernán Alessandri). | Permite ingresar requerimientos de atención de forma online desde celular o computador, reduciendo las filas físicas y organizando la demanda asistencial. | [TeleSalud MINSAL](https://telesalud.gob.cl/) |
| **2** | Pérdida de horas de atención médica debido a inasistencias no notificadas a tiempo por parte de los pacientes en la red local. | **Plataforma PAUS / Call Center** | Canal de atención telefónica centralizada para la asignación, anulación y reprogramación de horas de salud municipal. | Implementado por la Corporación de Desarrollo Social de la Municipalidad de Providencia. | Permite a los usuarios llamar por teléfono para cancelar o reprogramar su cita, liberando el cupo para reasignarlo a otro vecino en lista de espera. | [CDS Providencia](https://www.cdsprovidencia.cl/tomar-cambiar-y-cancelar-horas-de-salud-por-telefono/) |
| **3** | Falta de un canal móvil interactivo y autónomo para la reserva, consulta y anulación de citas 24/7 en atención primaria. | **Hora Salud** | Plataforma SaaS chilena para el agendamiento y confirmación de citas médicas en APS mediante portal web y aplicación móvil. | Creada por la empresa B chilena HoraSalud y utilizada en municipalidades como Recoleta y Peñaflor. | Permite a los usuarios confirmar, cancelar o reagendar sus citas de manera autónoma las 24 horas del día desde sus celulares sin depender de un operador. | [Hora Salud](https://horasalud.cl/) |
| **4** | Falta de integración automática entre la respuesta del paciente y la Ficha Clínica Electrónica del CESFAM para liberar el cupo en tiempo real. | **Rayen Salud (Módulo de Confirmación)** | Sistema de Registro Clínico Electrónico (ERP) especializado en Atención Primaria de Salud (APS) en Chile. | Desarrollado por Rayen Salud y utilizado por la gran mayoría de la red pública de CESFAM en Chile. | Conecta la Ficha Clínica Electrónica con el módulo de agendas para actualizar de forma inmediata las cancelaciones y dejar disponible el cupo en la agenda médica. | [Rayen Salud](https://www.rayenaps.cl/) |
| **5** | Ineficiencia de los recordatorios unilaterales y falta de opciones de confirmación telefónica automatizada. | **Sistema Hora Fácil (Línea 800)** | Servicio automatizado de respuesta de voz e interacción telefónica para agendamiento y confirmación de citas de salud. | Utilizado como sistema complementario en la Dirección de Salud de la Municipalidad de Providencia. | Permite al usuario solicitar, confirmar o liberar horas telefónicamente mediante un sistema automatizado marcando desde su teléfono fijo o móvil. | [Noticias Providencia](https://providencia.cl/provi/explora/noticias/salud/telesalud-abril-2025) |

---

## 2. Matriz de Atributos vs. Soluciones (Benchmark)

Para la evaluación comparativa, se seleccionaron 4 atributos conceptuales clave para el contexto del CESFAM Providencia:
1. **Autonomía 24/7 en Dispositivo Móvil:** Capacidad del usuario para gestionar su cita sin depender de horarios de atención u operadores humanos.
2. **Automatización en Tiempo Real:** Procesamiento inmediato de cancelaciones y liberación de cupos en la agenda.
3. **Baja Barrera de Entrada:** No requiere instalaciones complejas de aplicaciones ni procesos de autenticación difíciles para adultos mayores.
4. **Desacoplamiento / Viabilidad:** Capacidad de prototipado liviano y de bajo costo sin depender de licencias ERP cerradas.

| Atributo Conceptual | 1. TeleSalud (MINSAL) | 2. PAUS / Call Center | 3. Hora Salud | 4. Rayen Salud | 5. Hora Fácil (Línea 800) |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Autonomía 24/7 en Móvil** | 🟢 **Sí** (Portal Web) | ❌ No (Sujeto a horario telefónico) | 🟢 **Sí** (App / Web) | ❌ No (Uso interno administrativo) | 🟢 **Sí** (IVR Telefónico) |
| **Automatización Tiempo Real** | 🟡 Parcial (Ingreso diferido) | ❌ Manual por operador | 🟢 **Sí** | 🟢 **Sí** | 🟡 Parcial |
| **Baja Barrera de Entrada** | 🟡 Requiere ClaveÚnica / Formulario | 🟢 **Alta** (Llamada simple) | ❌ Media (Descarga de App/Registro) | N/A (Uso interno) | 🟢 **Alta** (Llamada telefónica) |
| **Desacoplamiento / Viabilidad** | ❌ Sistema estatal cerrado | ❌ Depende de personal municipal | ❌ Sistema SaaS privado de pago | ❌ ERP propietario de alto costo | 🟡 Plataforma IVR centralizada |

---

## 3. Preguntas del Análisis Comparativo

1. **¿Qué atributos NO están resueltos por ninguna de las soluciones existentes de forma conjunta?**
   * Ninguna solución actual combina la **alta accesibilidad y familiaridad de uso en dispositivos móviles** (como WhatsApp) con una **automatización en tiempo real desacoplada y sin costo de licenciamiento**, que permita al usuario cancelar o reagendar en segundos sin lidiar con formularios complejos o llamadas en espera.

2. **¿Qué atributo parecería ser el más relevante?**
   * La **Autonomía e Inmediatez en Dispositivo Móvil con Baja Barrera de Entrada**: Dado el perfil distinto entre los usuarios de la APS (incluyendo adultos mayores), la solución debe permitir la gestión de la cita en pocos pasos sin requerir descargas de aplicaciones ni claves complejas.

3. **¿Dónde hay oportunidades para mejorar o innovar en nuestra propuesta?**
   * Existe la oportunidad de innovar mediante un **Agente/Bot Automatizado en WhatsApp desacoplado**: Un flujo conversacional simple que procese en tiempo real la confirmación, cancelación y reagendamiento, alimentando una base de datos ligera para liberar la hora de forma inmediata. Aunque no es la única opción.

---

## 4. Lluvia de Ideas 2 & Propuestas Conceptuales

Con base en los hallazgos del Estado del Arte y del Benchmark, se formulan propuestas de solución conceptual:

----------------------------------------------terminar------------------------------------------------------
