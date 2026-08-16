# 2026-08-14 - Diseño y Cierre del Sistema de Gestión de Tareas

**Área:** 04 - Organización y Productividad  
**Tipo:** Registro de sesión  
**Estado:** Cerrada  
**Fecha:** 2026-08-14

---

## 1. Objetivo de la sesión

Iniciar la fase operativa posterior al cierre conceptual del Sistema de Planificación y definir el módulo de **Gestión de Tareas y Objetivos Operativos**.

La pregunta central fue:

> Dentro de un proyecto activo, ¿qué trabajo existe, cuál puede ejecutarse y cómo se conserva el progreso entre sesiones?

El objetivo fue evitar un gestor de tareas excesivamente granular y construir una representación mínima que pudiera alimentar al Sistema de Planificación.

---

## 2. Principio de mínima descomposición

Se descartó imponer siempre una estructura rígida:

```text
Proyecto → Tarea → Subtarea → Próxima acción
```

Se acordó:

> Usar el menor nivel de descomposición que permita ejecutar sin introducir fricción adicional.

En muchos casos basta con un objetivo claro.

Ejemplo:

```text
Tesis
→ Avanzar correcciones del jurado
```

La descomposición adicional solo se utiliza cuando reduce ambigüedad o ayuda a visualizar progreso.

---

## 3. Jerarquía de objetivos

Se definió una estructura flexible y recursiva:

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

Un proyecto puede contener varios objetivos principales y específicos.

Planificación puede recibir distintos objetivos específicos y decidir cuál conviene ejecutar según las condiciones de la sesión.

---

## 4. Información mínima de un objetivo

Información básica:

- nombre o resultado esperado;
- estado.

Información opcional cuando aporte valor:

- deadline;
- estimación aproximada;
- progreso;
- bloqueo o dependencia;
- nota de contexto;
- punto de reentrada.

No se requieren obligatoriamente:

- prioridad numérica;
- puntuaciones;
- energía requerida;
- dificultad;
- duración exacta;
- próxima acción hiperdescompuesta.

Principio:

> Un dato solo debe mantenerse si cambia una decisión o reduce fricción.

---

## 5. Estados acordados

Se definieron únicamente cuatro estados:

### Pendiente
Existe trabajo por realizar, pero no es un frente actualmente en curso.

### En progreso
Es un frente actualmente en curso.

### Bloqueado
No puede avanzar debido a una dependencia o impedimento real.

### Completado
El resultado esperado ya fue cumplido.

No se añadieron estados como `Esperando`, `Pausado` o `Archivado`.

---

## 6. Significado de "En progreso"

Se acordó que:

> `En progreso` representa actividad actual, no simplemente trabajo iniciado alguna vez.

Si un objetivo ya tuvo avance pero deja de ser un frente actual, vuelve a `Pendiente`.

No pierde su historial ni progreso.

La diferencia entre un pendiente nuevo y uno retomado se observa mediante:

- objetivos específicos completados;
- progreso natural;
- una nota de reentrada si resulta útil.

---

## 7. Progreso

Se prefirió representar el progreso de forma natural.

Ejemplo:

```text
Corregir Práctica 4

- [x] Grupo A
- [x] Grupo B
- [ ] Grupo C
```

También pueden utilizarse indicadores naturales como:

```text
20 / 48 corregidos
```

No se exige mantener porcentajes artificiales.

---

## 8. Permanencia y archivo

Los objetivos específicos completados permanecen visibles dentro del objetivo principal.

Esto permite observar el progreso realizado.

Cuando todos los objetivos específicos quedan resueltos y el objetivo principal se completa:

> el bloque completo puede pasar al archivo o historial.

---

## 9. Estado de objetivos principales

Si un objetivo principal tiene hijos, su estado refleja la situación global:

- todos completados → `Completado`;
- alguno en progreso → normalmente `En progreso`;
- todos pendientes → `Pendiente`;
- todo el trabajo restante bloqueado → `Bloqueado`.

Un objetivo específico bloqueado no bloquea al padre mientras existan otros hijos ejecutables.

---

## 10. Interfaz con Planificación

Se acordó que Planificación no necesita recibir todo el árbol.

Debe recibir los **objetivos ejecutables**.

Regla:

```text
¿El objetivo es suficientemente claro para ejecutar?
        ↓
      Sí → candidato
      No → revisar sus hijos
```

Pueden llegar a Planificación:

- `Pendiente`;
- `En progreso`.

No compiten normalmente:

- `Bloqueado`;
- `Completado`.

`En progreso` puede tener menor fricción de reentrada, pero no obtiene prioridad automática.

---

## 11. Trabajo nuevo descubierto durante ejecución

La preferencia establecida fue:

> El trabajo nuevo entra normalmente al Inbox.

Excepción:

- una extensión trivial y evidente del objetivo actual puede integrarse directamente.

Si el nuevo trabajo puede esperar:

- se procesa en la Revisión Semanal.

Si requiere atención rápida:

- se procesa lo antes posible;
- se asigna a un proyecto, objetivo y estado;
- puede provocar replanificación.

Si además cambia los proyectos que deberían recibir capacidad:

- escala al Sistema de Activación.

---

## 12. Actualización después de una sesión

Se buscó minimizar mantenimiento.

Al terminar una sesión basta con revisar:

1. ¿Terminó?
2. Si no terminó, ¿cuál es su estado?
3. ¿Necesito dejar una nota para retomarlo?

Reglas:

```text
Terminó → Completado
Sigue siendo frente actual → En progreso
Deja de ser frente actual → Pendiente
Aparece impedimento → Bloqueado
Aparece trabajo nuevo → Inbox
```

---

## 13. Nota de reentrada

Es opcional.

Se utiliza cuando reduce el coste de volver al proyecto.

Ejemplo:

```text
Retomar desde observación 6 de metodología.
```

Es especialmente útil después de pausas o en proyectos con alto coste de contexto.

---

## 14. Contraste contra la arquitectura completa

El módulo fue contrastado con Inventario, Activación, Inbox, Planificación y Ejecución.

No aparecieron contradicciones estructurales.

La separación quedó:

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

Regla de frontera principal:

> Gestión de Tareas mantiene trabajo y estado; no decide prioridad estratégica ni asignación de capacidad.

---

## 15. Resultado

El modelo conceptual del **Sistema de Gestión de Tareas y Objetivos Operativos se considera cerrado en v1**.

Se generó el documento vivo:

```text
04 - Organización y Productividad/
└── 01 - Sistema/
    └── Sistema_de_Gestion_de_Tareas_y_Objetivos.md
```

El registro de esta sesión debe almacenarse en:

```text
04 - Organización y Productividad/
└── 99 - Archivo/
    └── 2026-08-14 - Diseño y Cierre del Sistema de Gestión de Tareas.md
```

---

## 16. Próxima fase

La siguiente fase debe definir los **datos mínimos e interfaces entre módulos**.

Objetivos:

- identificar qué información vive en cada módulo;
- evitar datos duplicados;
- definir qué recibe y produce cada componente;
- construir el flujo operativo completo de la Revisión Semanal;
- preparar posteriormente la implementación en herramientas reales.

Esta fase debe centrarse en convertir la arquitectura conceptual en un sistema operable, sin reabrir decisiones ya cerradas salvo que aparezca evidencia nueva.
