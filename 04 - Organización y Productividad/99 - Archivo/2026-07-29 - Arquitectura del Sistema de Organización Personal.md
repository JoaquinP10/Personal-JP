# Sesión 05 - Arquitectura del Sistema de Organización Personal

# Objetivo de la sesión

Dar un paso atrás respecto al Sistema de Activación para comenzar a diseñar la arquitectura completa del sistema de organización personal.

En lugar de seguir profundizando únicamente en un componente, el objetivo fue entender cómo fluye la información desde que aparece una nueva idea hasta que finalmente se convierte en trabajo ejecutado.

---

# Cambio de enfoque

Durante las sesiones anteriores el diseño se había realizado principalmente "de abajo hacia arriba", definiendo componentes individuales como:

- Inventario Maestro.
- Sistema de Activación.
- Proyectos.
- Responsabilidades.

En esta sesión se decidió comenzar a diseñar el sistema "de arriba hacia abajo", analizando el flujo completo de información.

---

# Identificación de las entradas del sistema

Se analizaron distintos ejemplos de información que puede aparecer durante el día:

- recomendaciones profesionales;
- oportunidades laborales;
- posibles clientes;
- cursos;
- certificaciones;
- ideas espontáneas;
- mejoras para proyectos existentes.

Se concluyó que todos estos elementos comparten una característica común:

> Son información con potencial de convertirse en un proyecto.

En el momento en que aparecen todavía no constituyen proyectos.

---

# Descubrimiento: separación entre idea y proyecto

Inicialmente se asumía una transición directa:

Información
↓
Proyecto

Durante la discusión se identificó un paso intermedio indispensable.

Información
↓
Idea / Oportunidad
↓
Evaluación Estratégica
↓
Proyecto

Esto evita convertir automáticamente cualquier idea en un nuevo proyecto.

---

# Evaluación Estratégica

Se identificó un nuevo componente dentro de la arquitectura.

Su objetivo consiste en responder la pregunta:

> ¿Esta idea merece convertirse en un proyecto dentro del Inventario Maestro?

Esta decisión es completamente distinta del Sistema de Activación.

Mientras el Sistema de Activación decide cuándo comprometer capacidad, la Evaluación Estratégica decide si la idea merece formar parte del sistema.

---

# Criterios de Evaluación Estratégica

Durante la sesión se identificaron varios criterios utilizados para evaluar una nueva idea.

## Alineación estratégica

El proyecto debe contribuir a los objetivos personales y profesionales.

Debe estar alineado con la línea de carrera y con el desarrollo esperado.

---

## Viabilidad

Debe encontrarse dentro de un nivel razonablemente alcanzable.

Ejemplo discutido:

- aprender Yocto no tenía sentido antes de consolidar conocimientos de Linux;
- actualmente sí podría convertirse en un proyecto viable.

---

## Recursos

Se evalúa si existen recursos suficientes para ejecutar el proyecto.

Ejemplos:

- coste económico;
- tiempo estimado;
- complejidad;
- duración.

No todo proyecto interesante justifica su inversión.

---

## Beneficio esperado

El impacto esperado debe justificar el esfuerzo requerido.

No se busca únicamente un beneficio inmediato, sino una relación razonable entre esfuerzo e impacto.

---

# Separación entre Captura y Decisión

Se identificó uno de los principios fundamentales de la arquitectura.

## Principio

> Capturar nunca implica decidir.

La captura únicamente evita perder información.

Toda evaluación posterior ocurre en otro momento.

---

# Inbox

Como consecuencia de este principio aparece un nuevo componente conceptual.

Información nueva
↓
Captura
↓
Inbox

La Inbox actúa como una cola temporal de procesamiento.

Su función no consiste en almacenar información permanentemente.

Su objetivo es mantener elementos pendientes de evaluación.

Posteriormente cada elemento deberá seguir alguno de estos caminos:

- descartarse;
- archivarse como referencia;
- convertirse en proyecto;
- incorporarse como información permanente del sistema.

---

# Niveles de decisión

Durante la sesión se identificaron tres niveles claramente diferenciados.

## Nivel 1 — Captura

Pregunta:

¿Quiero asegurarme de no olvidar esta información?

Tiempo requerido:

10–30 segundos.

No existe análisis.

---

## Nivel 2 — Evaluación Estratégica

Pregunta:

¿Esta idea merece convertirse en un proyecto?

Aquí intervienen criterios como:

- alineación;
- viabilidad;
- recursos;
- beneficio esperado.

El resultado puede ser la creación de un nuevo proyecto dentro del Inventario Maestro.

---

## Nivel 3 — Sistema de Activación

Pregunta:

¿Este proyecto requiere consumir parte de mi capacidad durante el próximo periodo?

Aquí aparecen factores como:

- capacidad disponible;
- carga de trabajo;
- contexto;
- compromisos actuales.

---

# Arquitectura preliminar

Al finalizar la sesión la arquitectura conceptual quedó representada de la siguiente forma.

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
Proyectos comprometidos
↓
Planificación
↓
Trabajo ejecutado

---

# Nueva línea de investigación

Se identificó una nueva dimensión todavía no explorada.

Hasta ahora se ha definido qué hace cada componente.

Sin embargo, todavía falta responder:

> ¿Cuándo trabaja cada componente?

Se planteó la hipótesis de que cada módulo opera con una frecuencia distinta.

Ejemplos:

- Captura: continua.
- Evaluación Estratégica: periódica.
- Sistema de Activación: revisión periódica.
- Planificación: semanal y diaria.

Esta línea de investigación permitirá definir el funcionamiento temporal completo del sistema.

---

# Estado del proyecto

## Componentes ya identificados

- Captura.
- Inbox.
- Evaluación Estratégica.
- Inventario Maestro.
- Sistema de Activación.
- Planificación.

## Aspectos pendientes

- definir la frecuencia de funcionamiento de cada componente;
- determinar el calendario interno del sistema;
- continuar validando la arquitectura mediante casos de uso reales.

---

# Próximos pasos

La siguiente etapa consistirá en definir el comportamiento temporal del sistema.

En lugar de diseñar nuevos componentes, el objetivo será establecer:

- cuándo se ejecuta cada proceso;
- qué decisiones pertenecen a cada revisión;
- cómo interactúan entre sí los distintos ciclos del sistema.

Esto permitirá completar la arquitectura antes de comenzar el diseño operativo y su futura implementación.