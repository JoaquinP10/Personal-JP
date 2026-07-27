# Sesión 03 - Diseño del Sistema de Activación (Borrador v0.1)

# Objetivo de la sesión

Comenzar el diseño del **Sistema de Activación**, es decir, el mecanismo que determina cuándo un proyecto del Inventario Maestro pasa a formar parte del trabajo activo del usuario.

El objetivo no fue implementar herramientas, sino modelar el comportamiento real del proceso de decisión.

---

# Punto de partida

Hasta esta sesión la arquitectura del sistema era:

Inventario Maestro
↓
Proyecto
↓
Tareas

Durante la discusión se concluyó que este modelo era insuficiente para explicar cómo se eligen realmente los proyectos sobre los que trabajar.

---

# Descubrimiento principal

La selección de proyectos no se realiza únicamente por prioridad.

Durante los ejemplos planteados se observó que la decisión depende de varios factores simultáneamente.

Los principales fueron:

- tiempo disponible;
- nivel de energía;
- coste percibido para comenzar;
- posibilidad de generar progreso significativo;
- continuidad esperada del proyecto.

Se concluyó que la prioridad es solamente uno de varios factores.

---

# Casos analizados

## Caso 1

Miércoles por la noche.

Tiempo disponible:
2 horas.

Proyectos:

- Linux
- AWS
- GitHub
- Tesis

Resultado observado:

Linux fue elegido no por ser el proyecto más importante, sino porque:

- la sesión disponible era suficiente;
- permitía generar progreso;
- el coste de comenzar era bajo.

---

## Caso 2

Sábado libre.

Tiempo disponible:
aproximadamente 8 horas.

Resultado observado:

No necesariamente se eligió el proyecto más importante.

Se observaron nuevos criterios:

- Linux no justificaba dedicarle cinco horas continuas.
- GitHub permitía completar un avance significativo en una única sesión.
- La tesis generaba dudas debido a la necesidad de mantener continuidad durante las semanas siguientes.

---

# Nuevos conceptos descubiertos

## Coste de activación

Se identificó como el esfuerzo psicológico necesario para comenzar un proyecto.

Ejemplos:

GitHub:
Coste bajo.

Linux:
Coste bajo.

AWS:
Coste alto debido a la necesidad de planificar.

Tesis:
Coste muy alto debido a la necesidad de recuperar contexto y mantener continuidad.

---

## Continuidad

Se observó que algunos proyectos requieren mantener una cadencia constante.

Ejemplos:

Tesis:
Muy dependiente de continuidad.

Linux:
Puede pausarse algunos días.

GitHub:
Puede retomarse tras semanas sin consecuencias importantes.

---

## Sesión mínima útil

Cada proyecto parece requerir una duración mínima para que la sesión tenga sentido.

Ejemplos:

Linux:
1 hora aproximadamente.

GitHub:
2–3 horas permiten obtener resultados visibles.

Tesis:
Sesiones largas de alta concentración.

---

# Primera propuesta de arquitectura

Se propuso ampliar la arquitectura original.

Inventario Maestro
↓
Perfil Operativo del Proyecto
↓
Estado Actual
↓
Planificación Semanal
↓
Tareas

---

# Perfil Operativo del Proyecto

Se propuso que cada proyecto posea un conjunto reducido de atributos relativamente estables.

Versión preliminar:

- Tipo de proyecto
- Estado
- Cadencia
- Nivel de energía requerido
- Sesión mínima útil
- Sesión ideal
- Coste de activación
- Dependencias

Se acordó que esta lista es provisional.

Cada atributo deberá justificar su existencia durante la validación.

---

# Filosofía del diseño

Se estableció un principio importante.

No se desea construir un sistema complejo de mantener.

Cada atributo deberá responder dos preguntas:

1. ¿Modifica realmente alguna decisión?
2. ¿Compensa el esfuerzo de mantenerlo actualizado?

Los atributos que no aporten decisiones serán eliminados.

---

# Metodología de desarrollo

Se decidió tratar el sistema como si fuera un proyecto de ingeniería de software.

Etapas:

1. Levantamiento de requisitos.
2. Diseño conceptual.
3. Validación mediante casos de uso.
4. Documentación definitiva.
5. Implementación.
6. Uso y mejora continua.

Actualmente el proyecto se encuentra entre las etapas 2 y 3.

---

# Estrategia de validación

Antes de implementar el sistema se validará mediante escenarios reales.

La validación consistirá en presentar situaciones concretas y comprobar si el modelo propone decisiones razonables.

Ejemplo:

Entrada:

- miércoles;
- 1 hora disponible;
- energía media;
- proyectos activos definidos.

Salida esperada:

Proyecto recomendado.

Posteriormente se analizará el razonamiento utilizado por el sistema.

Si la decisión no coincide con el comportamiento esperado, se modificará el modelo.

---

# Tipos de casos de validación previstos

## Contexto temporal

- Día laboral.
- Fin de semana.
- Vacaciones.

## Trabajo

- Cliente nuevo.
- Cliente bloqueado.
- Entrega urgente.

## Docencia

- Inicio de ciclo.
- Semana de correcciones.
- Reuniones extraordinarias.

## Desarrollo académico

- Inicio de tesis.
- Paper.
- Maestría.

## Aprendizaje

- Finalizar un dominio.
- Activar uno nuevo.

## Contexto personal

- Baja energía.
- Enfermedad.
- Viajes.

---

# Decisión metodológica

No se implementará ninguna herramienta todavía.

Primero se construirá un conjunto suficientemente amplio de casos de uso.

Estos casos servirán como pruebas del modelo.

Solo cuando el sistema produzca decisiones consistentes se documentará la versión 1.0 y posteriormente se implementará en Obsidian, Google Calendar y el gestor de tareas.

---

# Estado al finalizar la sesión

Se dispone ya de un primer borrador conceptual del Sistema de Activación.

La siguiente sesión estará dedicada principalmente a validar este modelo mediante escenarios reales y refinar su arquitectura hasta obtener una versión estable.