# Sesión 04 - Refinamiento del Sistema de Activación y Gestión de la Capacidad

# Objetivo de la sesión

Continuar la validación conceptual del Sistema de Activación mediante casos de uso.

El objetivo fue comprobar si la arquitectura propuesta describía correctamente el proceso real mediante el cual se decide en qué proyectos trabajar y cómo evolucionan dichos proyectos a lo largo del tiempo.

---

# Punto de partida

Al inicio de la sesión el modelo asumía que:

Inventario Maestro
↓
Sistema de Activación
↓
Proyectos Activos
↓
Planificación Semanal
↓
Tareas

Todavía existían dudas sobre:

- qué significa realmente "activar" un proyecto;
- cuándo un proyecto deja de estar activo;
- cómo afectan los eventos externos;
- cuál es el papel de la capacidad personal.

---

# Caso de validación 001

## Escenario

Miércoles por la noche.

Tiempo disponible:
2 horas.

Energía:
Media.

Proyectos disponibles:

- Linux
- AWS
- GitHub
- Tesis

---

## Descubrimiento

Para decidir no es necesario conocer toda la información del proyecto.

El proceso mental observado fue:

1. ¿Existe alguna urgencia?
2. ¿Mi energía permite trabajar en ese proyecto?
3. ¿Qué avance significativo puedo realizar durante el tiempo disponible?

No se razonó utilizando atributos como "tipo de proyecto" o "sesión ideal".

---

## Conclusión

El Sistema de Activación debe trabajar principalmente con el contexto actual y con el siguiente avance posible de cada proyecto, en lugar de hacerlo únicamente con características estáticas del proyecto.

---

# Caso de validación 002

## Escenario

Durante una semana normal un cliente potencial (Empresa Bud) acepta la propuesta comercial.

El proyecto pasa a requerir preparación para su implementación.

---

## Pregunta

¿Debe activarse automáticamente?

---

## Descubrimiento

La respuesta fue negativa.

Un evento externo no debe modificar directamente el conjunto de proyectos comprometidos.

Su función únicamente es actualizar el contexto.

Posteriormente el Sistema de Activación deberá reevaluar la situación completa y decidir si existe capacidad suficiente para asumir dicho compromiso.

---

## Nueva arquitectura

Evento externo
↓
Actualización del Inventario Maestro
↓
Sistema de Activación
↓
Reevaluación
↓
Proyectos comprometidos

---

# Redefinición del concepto de "activar"

Durante la discusión se observó que activar un proyecto no significa simplemente que exista.

La nueva definición propuesta es:

> Activar un proyecto significa comprometer deliberadamente parte de la capacidad personal para hacerlo avanzar durante el periodo actual de planificación.

Esta definición explica por qué no todos los proyectos existentes deben encontrarse activos simultáneamente.

---

# Caso de validación 003

## Escenario

Se analizaron distintos estados posibles de un proyecto:

- proyecto terminado (Curso de Linux);
- cliente operativo (Bud);
- cliente en mantenimiento (Fux);
- tesis esperando retroalimentación del jurado.

---

## Descubrimiento

Se identificó una diferencia fundamental entre:

- existencia del proyecto;
- necesidad de dedicarle tiempo.

Un proyecto puede seguir existiendo durante meses o años sin requerir dedicación activa.

Ejemplos:

- clientes en operación normal;
- tesis esperando revisión;
- proyectos bloqueados por terceros.

---

## Nueva definición

Un proyecto deja de estar activo cuando deja de requerir una asignación deliberada de tiempo.

No es necesario que haya finalizado.

---

# Gestión de la capacidad

Posteriormente se analizó un escenario con múltiples proyectos simultáneamente:

- Bud
- JS
- Linux
- AWS
- GitHub
- Paper
- Tesis

Todos ellos eran proyectos razonables.

Sin embargo, se concluyó que comprometerse con todos produciría un sistema inviable.

---

## Descubrimiento principal

Se estableció una diferencia entre:

- proyectos que sería conveniente realizar;
- proyectos que realmente pueden sostenerse de manera simultánea.

El recurso limitante no son únicamente las horas disponibles.

También existe una capacidad mental para mantener compromisos activos.

---

# Nuevo principio del Sistema de Activación

El objetivo del sistema no consiste en activar todos los proyectos importantes.

Su objetivo consiste en seleccionar únicamente aquellos compromisos que pueden sostenerse de manera realista sin superar la capacidad disponible.

---

# Pregunta abierta

La sesión terminó identificando la principal incógnita restante del modelo.

Todavía no se conoce cómo medir la capacidad personal.

Se plantearon varias posibilidades:

- número máximo de proyectos;
- horas disponibles;
- carga mental;
- tipo de proyecto;
- combinación de varios factores.

No se llegó a una respuesta definitiva.

---

# Estado del Sistema de Activación

## Aspectos considerados estables

- Activar un proyecto implica comprometer capacidad.
- Desactivar un proyecto no implica necesariamente finalizarlo.
- Los eventos externos actualizan el contexto, pero no modifican directamente los compromisos.
- El Sistema de Activación administra la capacidad disponible, no la existencia de los proyectos.

---

## Aspectos pendientes

Queda pendiente descubrir cómo se asigna el presupuesto de capacidad personal.

Se considera que esta será la pieza fundamental para completar la versión 1.0 del Sistema de Activación.

---

# Próximos pasos

La siguiente etapa consistirá en estudiar el concepto de capacidad personal mediante ejemplos reales e históricos.

El objetivo será responder preguntas como:

- ¿Cuántos compromisos simultáneos puede sostener el sistema?
- ¿Qué factores modifican dicha capacidad?
- ¿Cómo debe repartirse entre las distintas áreas de la vida?

La respuesta a estas preguntas permitirá finalizar el diseño conceptual antes de comenzar la implementación del sistema.