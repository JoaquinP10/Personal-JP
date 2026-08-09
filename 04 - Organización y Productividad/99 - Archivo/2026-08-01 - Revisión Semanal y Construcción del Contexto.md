# Sesión 06 - Revisión Semanal y Construcción del Contexto

# Objetivo de la sesión

Continuar el diseño de la arquitectura del sistema de organización personal, centrándose en el funcionamiento de la Revisión Semanal y en la información que necesita el Sistema de Activación para tomar decisiones.

El objetivo principal fue comenzar a definir el calendario interno del sistema, es decir, no solamente qué hace cada componente sino cuándo y con qué información trabaja.

---

# Estado inicial

Se partió de la arquitectura obtenida en la sesión anterior:

Información nueva
↓
Captura
↓
Inbox
↓
Evaluación Estratégica
↓
Inventario Maestro
↓
Sistema de Activación
↓
Planificación

El siguiente paso consistía en definir el comportamiento temporal de estos módulos.

---

# Diseño de la Revisión Semanal

Se planteó el escenario de una revisión realizada antes de comenzar una nueva semana.

A partir de distintos casos de uso se identificó el flujo general que debería seguir esta revisión.

---

## 1. Actualización del estado de los proyectos activos

La revisión comienza sincronizando el sistema con la realidad.

Se actualiza:

- progreso;
- avances;
- bloqueos;
- cambios relevantes;
- contexto propio de cada proyecto.

En esta etapa todavía no se toman decisiones estratégicas.

Su único objetivo es representar correctamente el estado actual del sistema.

---

## 2. Procesamiento de la Inbox

Una vez actualizado el estado de los proyectos, se procesa la Inbox.

Cada elemento pendiente es evaluado mediante el proceso de Evaluación Estratégica.

Cada idea puede:

- descartarse;
- archivarse como referencia;
- convertirse en un nuevo proyecto del Inventario Maestro.

La Inbox actúa únicamente como una cola temporal de procesamiento.

---

## 3. Reevaluación del Inventario Maestro

Con la información ya actualizada se revisa el Inventario Maestro.

No se trata de crear una nueva lista de proyectos, sino de trabajar sobre un inventario ya existente y actualizado.

El resultado de esta etapa constituye la base sobre la que trabajará el Sistema de Activación.

---

## 4. Construcción del Contexto Semanal

Durante la discusión apareció un nuevo concepto dentro de la arquitectura.

El Sistema de Activación no debería consultar directamente múltiples fuentes de información.

En cambio, debería recibir un único objeto denominado:

> Contexto Semanal

Este contexto resume toda la información relevante para tomar decisiones durante la semana siguiente.

---

# Evolución del concepto de Contexto

Inicialmente se propuso dividir el contexto en:

- temporal;
- profesional;
- personal;
- proyectos.

Posteriormente se concluyó que resulta más útil clasificarlo según el efecto que produce sobre el sistema.

La estructura preliminar quedó definida como:

## Disponibilidad

Información que modifica la capacidad disponible.

Ejemplos:

- reuniones;
- clases;
- viajes;
- feriados;
- vacaciones;
- tiempo comprometido.

---

## Estado de proyectos

Información que modifica la prioridad o situación de un proyecto.

Ejemplos:

- recepción de feedback;
- aceptación de propuestas;
- cambios importantes;
- bloqueos;
- esperas.

---

## Estado personal

Información que modifica la capacidad general de trabajo.

Ejemplos:

- salud;
- enfermedad;
- cansancio;
- asuntos personales relevantes.

---

# Entradas del Sistema de Activación

Durante la sesión también se definieron las entradas principales del Sistema de Activación.

Actualmente se considera que el algoritmo recibe:

- Inventario Maestro;
- Estado actual del Sistema de Activación;
- Contexto Semanal.

A partir de estas entradas decide:

- mantener proyectos activos;
- activar nuevos proyectos;
- pausar proyectos;
- desactivar proyectos.

---

# Separación de responsabilidades

Se identificó una distinción importante entre:

## Construcción del Contexto

Su responsabilidad consiste en recopilar y sintetizar toda la información relevante de la semana.

Produce un único Contexto Semanal.

---

## Sistema de Activación

No obtiene información directamente de reuniones, calendario o eventos.

Su única responsabilidad consiste en decidir qué proyectos consumirán capacidad durante la siguiente semana utilizando:

- Inventario Maestro;
- Estado actual;
- Contexto Semanal.

---

# Flujo preliminar de la Revisión Semanal

Al finalizar la sesión el flujo quedó representado de la siguiente manera.

Actualización del estado de proyectos
↓
Procesamiento de Inbox
↓
Construcción del Contexto Semanal
↓
Sistema de Activación
↓
Planificación Semanal

Cada etapa consume exclusivamente la salida de la anterior.

---

# Estado del proyecto

Con esta sesión la arquitectura conceptual del sistema queda prácticamente consolidada.

Actualmente se encuentran definidos:

- Captura.
- Inbox.
- Evaluación Estratégica.
- Inventario Maestro.
- Construcción del Contexto.
- Sistema de Activación.
- Planificación.

La discusión deja de centrarse en descubrir nuevos componentes y comienza a enfocarse en especificar con precisión el funcionamiento de cada uno.

---

# Próxima etapa

La siguiente fase del proyecto consistirá en elaborar una especificación funcional para cada componente.

Para cada módulo se buscará definir:

- objetivo;
- responsabilidades;
- entradas;
- salidas;
- información almacenada;
- reglas de funcionamiento;
- frecuencia de ejecución.

Una vez completadas estas especificaciones, la arquitectura estará lista para comenzar su implementación mediante herramientas concretas (Obsidian, Google Calendar, gestor de tareas, etc.).