# Sistema de Gestión de Tareas y Objetivos Operativos

**Versión:** v1.0  
**Estado:** Especificación conceptual  
**Área:** 04 - Organización y Productividad

---

## 1. Propósito

El Sistema de Gestión de Tareas y Objetivos Operativos representa el trabajo existente dentro de los proyectos activos y conserva su estado entre sesiones.

Responde principalmente a:

> Dentro de un proyecto activo, ¿qué trabajo existe, cuál puede ejecutarse y cómo se conserva el progreso entre sesiones?

Este módulo no decide:

- qué proyectos existen;
- qué proyectos merecen capacidad;
- qué objetivo debe ejecutarse ahora.

Estas responsabilidades pertenecen, respectivamente, al Inventario Maestro, al Sistema de Activación y al Sistema de Planificación.

---

## 2. Posición dentro de la arquitectura

```text
Nueva información
      ↓
Captura
      ↓
Inbox
      ↓
Evaluación Estratégica
      ↓
Inventario Maestro
      ↓
Contexto
      ↓
Sistema de Activación
      ↓
Proyectos activos
      ↓
Gestión de Tareas / Objetivos
      ↓
Sistema de Planificación
      ↓
Ejecución
      ↓
Actualización de estado
      ↓
Revisión / realimentación
```

La Gestión de Tareas funciona como la capa operativa interna de los proyectos.

---

## 3. Principio de mínima descomposición

No se obliga a utilizar siempre una jerarquía rígida del tipo:

```text
Proyecto
→ tarea
→ subtarea
→ próxima acción
```

La regla es:

> Usar el menor nivel de descomposición que permita ejecutar el trabajo sin introducir fricción innecesaria.

Por defecto puede bastar con un objetivo suficientemente claro.

Ejemplo:

```text
Tesis
→ Avanzar correcciones del jurado
```

Solo se descompone más cuando aporta valor real.

---

## 4. Jerarquía flexible

La estructura puede ser recursiva:

```text
Proyecto
└── Objetivo principal
    ├── Objetivo específico A
    ├── Objetivo específico B
    │   ├── Subobjetivo B1
    │   └── Subobjetivo B2
    └── Objetivo específico C
```

No existe una profundidad obligatoria.

La descomposición se utiliza cuando ayuda a:

- visualizar progreso;
- dividir trabajo;
- reducir ambigüedad;
- identificar partes ejecutables;
- preparar futuras sesiones;
- facilitar la reentrada.

---

## 5. Objetivos principales y específicos

Un proyecto puede contener uno o más objetivos principales.

Cada objetivo principal puede contener objetivos específicos.

### Objetivo principal

Representa un frente relevante de avance del proyecto.

### Objetivo específico

Representa una parte concreta del objetivo principal que puede completarse de forma independiente o contribuir directamente a su cierre.

Planificación puede seleccionar objetivos específicos distintos dependiendo de tiempo, energía, presión y ejecutabilidad.

---

## 6. Información mínima

La información básica de un objetivo es:

- nombre o resultado esperado;
- estado.

Información opcional:

- deadline o restricción temporal;
- estimación aproximada;
- progreso;
- bloqueo o dependencia;
- nota de contexto;
- punto de reentrada.

No se consideran obligatorios:

- prioridad numérica;
- puntuaciones;
- energía requerida;
- dificultad;
- duración exacta;
- próxima acción hiperdescompuesta.

Regla:

> Un dato solo debe mantenerse si cambia una decisión o reduce fricción.

---

## 7. Estados

Se utilizarán únicamente cuatro estados operativos.

### Pendiente

Existe trabajo por realizar, pero actualmente no se está trabajando en él.

### En progreso

Es un frente actualmente en curso.

### Bloqueado

No puede avanzar debido a una dependencia o impedimento real.

### Completado

El resultado esperado ya fue cumplido.

No se agregan por ahora estados como:

- esperando;
- pausado;
- archivado;
- cancelado.

Solo se añadirán si la experiencia real demuestra que aportan valor.

---

## 8. Semántica de "En progreso"

`En progreso` no significa que el objetivo haya sido iniciado alguna vez.

Significa:

> El objetivo forma parte del trabajo actualmente en curso.

Si deja de trabajarse activamente pero continúa incompleto, vuelve a `Pendiente`.

Se conserva:

- el progreso realizado;
- los elementos completados;
- una nota de reentrada cuando sea útil.

Esto permite distinguir naturalmente un pendiente nuevo de uno retomado sin crear estados adicionales.

---

## 9. Representación del progreso

El progreso debe representarse de forma natural.

Ejemplo:

```text
Corregir Práctica 4

- [x] Grupo A
- [x] Grupo B
- [ ] Grupo C
```

También pueden utilizarse métricas naturales:

```text
20 / 48 corregidos
```

No se exige calcular porcentajes cuando no aporten información útil.

---

## 10. Permanencia de objetivos completados

Los objetivos específicos completados permanecen visibles dentro de su objetivo principal mientras este siga abierto.

Ejemplo:

```text
Objetivo principal

- [x] Específico A
- [x] Específico B
- [ ] Específico C
```

Esto permite observar progreso y conservar contexto.

Cuando el objetivo principal queda completamente resuelto, el bloque completo puede trasladarse al archivo o historial del proyecto.

---

## 11. Estado del objetivo principal

Si un objetivo principal no tiene hijos, su estado se gestiona directamente.

Si tiene objetivos específicos, su estado refleja la situación global.

Reglas:

- todos los hijos completados → `Completado`;
- existe algún hijo en progreso → normalmente `En progreso`;
- todos los hijos pendientes → `Pendiente`;
- todo el trabajo restante está bloqueado → `Bloqueado`.

Un hijo bloqueado no bloquea al objetivo principal si existen otros objetivos específicos ejecutables.

---

## 12. Interfaz con Planificación

Planificación no necesita procesar todo el árbol.

Debe recibir únicamente los objetivos que pueden convertirse razonablemente en trabajo para una sesión.

Regla recursiva:

```text
¿El objetivo es suficientemente claro para ejecutar?
        ↓
      Sí → candidato
      No → revisar sus hijos
```

Estados que pueden llegar a Planificación:

- `Pendiente`;
- `En progreso`.

Estados excluidos de la competencia normal:

- `Bloqueado`;
- `Completado`.

`En progreso` puede tener menor fricción de reentrada, pero no obtiene prioridad automática.

La decisión de qué objetivo ejecutar pertenece siempre a Planificación.

---

## 13. Aparición de trabajo nuevo

Cuando aparece trabajo nuevo durante una sesión, la ruta normal es:

```text
Trabajo nuevo
      ↓
Inbox
      ↓
Procesamiento
      ↓
Asignación a proyecto / objetivo / estado
```

### Excepción

Una extensión trivial y evidente del objetivo que ya se está ejecutando puede integrarse directamente sin pasar por Inbox.

### Si el trabajo puede esperar

Se procesa durante la siguiente Revisión Semanal.

### Si requiere atención rápida

Se procesa lo antes posible.

Si solo modifica la forma de utilizar la capacidad ya comprometida:

> replanificación local.

Si altera qué proyectos deben recibir capacidad:

> reevaluación del Sistema de Activación.

---

## 14. Actualización después de una sesión

El mantenimiento posterior debe ser mínimo.

Al terminar una sesión basta con responder:

1. ¿Terminó?
2. Si no terminó, ¿cuál es su estado actual?
3. ¿Hace falta dejar información para retomarlo?

Reglas:

```text
Terminó
→ Completado

Sigue siendo frente actual
→ En progreso

Deja de ser frente actual
→ Pendiente

Aparece impedimento
→ Bloqueado

Aparece trabajo nuevo
→ Inbox
```

No se exige registrar horas, porcentajes o métricas adicionales salvo que sean útiles de forma natural.

---

## 15. Nota de reentrada

La nota de reentrada es opcional.

Se utiliza cuando reduce de forma significativa el coste de volver al proyecto.

Ejemplo:

```text
Retomar desde la observación 6 de metodología.
```

Es especialmente útil cuando:

- habrá una pausa;
- el contexto es complejo;
- no resulta evidente dónde continuar;
- el proyecto tiene alto coste de entrada.

---

## 16. Relación con Inventario Maestro

El Inventario Maestro responde:

> ¿Qué proyectos existen?

La Gestión de Tareas responde:

> ¿Qué trabajo existe dentro de esos proyectos?

El Inventario no debe convertirse en una lista detallada de tareas.

---

## 17. Relación con Sistema de Activación

Activación responde:

> ¿Qué proyectos reciben capacidad durante el período actual?

La Gestión de Tareas no puede aumentar por sí sola el conjunto de proyectos activos.

Si aparece trabajo perteneciente a un proyecto no activo y este requiere capacidad real, debe escalarse a Activación.

---

## 18. Relación con Sistema de Planificación

Planificación responde:

> Dadas las condiciones actuales, ¿qué objetivo ejecutable conviene trabajar?

Gestión de Tareas proporciona:

- objetivos disponibles;
- estado;
- progreso;
- deadlines cuando existan;
- bloqueos;
- estimaciones cuando sean útiles;
- información de reentrada.

Planificación decide qué hacer con esa información.

---

## 19. Relación con Inbox

Inbox contiene elementos todavía no integrados en el modelo operativo.

Procesar un elemento implica, cuando corresponda:

- identificar a qué proyecto pertenece;
- decidir qué representa;
- ubicarlo dentro de la jerarquía;
- asignarle un estado;
- determinar si modifica la planificación;
- escalar a Activación si modifica compromisos.

---

## 20. Relación con Ejecución

La Ejecución consume un objetivo seleccionado por Planificación.

Durante la sesión puede:

- avanzar;
- completar;
- descubrir bloqueos;
- producir trabajo nuevo;
- generar información de contexto.

Al cerrar la sesión, el árbol operativo se actualiza con el mínimo mantenimiento necesario.

---

## 21. Contraste con la arquitectura completa

La especificación es compatible con los módulos ya definidos.

La separación queda:

```text
Inventario
→ qué existe

Activación
→ qué recibe capacidad

Gestión de Tareas
→ qué trabajo existe dentro del proyecto

Planificación
→ qué trabajo conviene ejecutar ahora

Ejecución
→ realizar el trabajo

Revisión
→ actualizar y realimentar
```

No se identificaron contradicciones estructurales.

La principal regla de frontera es:

> Gestión de Tareas mantiene trabajo y estado; no decide prioridad estratégica ni asignación de capacidad.

---

## 22. Ciclo operativo resumido

```text
Proyecto activo
      ↓
Objetivos disponibles
      ↓
Filtrar bloqueados y completados
      ↓
Exponer objetivos ejecutables
      ↓
Planificación selecciona
      ↓
Ejecución
      ↓
Actualizar estado / progreso
      ↓
¿Apareció trabajo nuevo?
   ↙              ↘
 No               Sí
 ↓                 ↓
Fin              Inbox
```

---

## 23. Principios del módulo

1. **Descomponer solo cuando ayude.**
2. **Un objetivo suficientemente claro es mejor que una próxima acción artificialmente detallada.**
3. **El progreso debe ser visible sin convertirse en burocracia.**
4. **Los objetivos completados permanecen visibles hasta cerrar su objetivo principal.**
5. **`En progreso` representa actividad actual, no historia.**
6. **Un objetivo puede volver a `Pendiente` conservando progreso previo.**
7. **Planificación recibe objetivos ejecutables, no todo el árbol.**
8. **Trabajo nuevo pasa normalmente por Inbox.**
9. **El mantenimiento después de una sesión debe ser mínimo.**
10. **La herramienta debe adaptarse a la complejidad del proyecto y no imponer una profundidad fija.**
11. **Gestión de Tareas representa trabajo; Planificación decide qué hacer; Activación decide qué proyectos reciben capacidad.**

---

## 24. Estado de la especificación

El modelo conceptual del **Sistema de Gestión de Tareas y Objetivos Operativos se considera cerrado en v1**.

Quedan para fases posteriores:

- decidir cómo se representará físicamente el árbol de objetivos;
- definir las plantillas mínimas por proyecto;
- diseñar la interfaz con la Revisión Semanal;
- elegir herramientas de implementación;
- probar el modelo con proyectos reales y simplificar donde aparezca mantenimiento innecesario.
