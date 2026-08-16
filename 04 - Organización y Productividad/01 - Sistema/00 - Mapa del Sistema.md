# Mapa del Sistema de Organización Personal

**Versión:** v1.0  
**Estado:** Arquitectura conceptual vigente  
**Última actualización:** 2026-08-16

---

## 1. Propósito

Este documento define la arquitectura general del sistema de organización y productividad.

Su objetivo es establecer:

- qué módulos existen;
- qué responsabilidad tiene cada uno;
- qué información mantiene cada módulo;
- cómo fluye la información;
- cuándo una decisión debe escalar a otro nivel.

No sustituye las especificaciones particulares de Activación, Gestión de Tareas o Planificación.

---

## 2. Arquitectura general

```text
REALIDAD
   ↓
CAPTURA
   ↓
INBOX
   ↓
EVALUACIÓN ESTRATÉGICA
   ↓
INVENTARIO MAESTRO
   ↓
CONTEXTO
   ↓
ACTIVACIÓN
   ↓
GESTIÓN DE TAREAS / OBJETIVOS
   ↓
PLANIFICACIÓN
   ↓
EJECUCIÓN
   ↓
REALIMENTACIÓN
```

La **Revisión Semanal** sincroniza periódicamente el sistema completo.

---

## 3. Responsabilidad de cada módulo

### Captura

Registra rápidamente nueva información sin decidir qué hacer con ella.

> Capturar no significa decidir.

### Inbox

Contiene temporalmente elementos todavía no integrados al sistema.

Puede recibir:

- ideas;
- trabajo nuevo;
- recordatorios;
- cambios detectados;
- elementos que requieren evaluación.

### Evaluación Estratégica

Decide si un elemento merece convertirse en proyecto o compromiso del sistema.

Criterios principales:

- alineación;
- utilidad;
- viabilidad;
- preparación suficiente;
- horizonte razonable;
- coste y recursos;
- impacto esperado.

### Inventario Maestro

Responde:

> ¿Qué proyectos existen?

Mantiene principalmente:

- proyecto;
- estado general;
- descripción breve.

Puede mostrar metadatos secundarios como área, tipo o progreso resumido.

### Contexto

Representa las condiciones relevantes del período actual.

Se resume en:

- disponibilidad;
- estado relevante de proyectos;
- estado personal.

No duplica el calendario ni el árbol de tareas.

### Activación

Responde:

> ¿Qué proyectos reciben capacidad ahora?

Trabaja con:

- Inventario;
- Contexto;
- estado previo de Activación.

Produce el conjunto de proyectos activos.

### Gestión de Tareas / Objetivos

Responde:

> ¿Qué trabajo existe dentro del proyecto?

Mantiene:

- objetivos;
- jerarquía;
- estado;
- progreso;
- bloqueos;
- información de reentrada cuando sea útil.

### Planificación

Responde:

> ¿Qué conviene hacer con la capacidad disponible?

Opera en dos niveles:

- planificación semanal;
- decisión local de sesión.

Produce sesiones y resultados esperados.

### Ejecución

Realiza el trabajo seleccionado y devuelve el estado real al sistema.

Puede producir:

- avance;
- completado;
- bloqueo;
- nueva información;
- necesidad de replanificación.

### Revisión Semanal

Sincroniza el sistema con la realidad.

No es un repositorio independiente, sino el proceso periódico de integración.

---

## 4. Fuentes maestras de información

| Información | Fuente maestra |
|---|---|
| Proyecto existente | Inventario Maestro |
| Estado general del proyecto | Inventario Maestro |
| Descripción del proyecto | Inventario Maestro |
| Proyecto activo / no activo | Activación |
| Objetivos y subobjetivos | Gestión de Tareas |
| Estado operativo de objetivos | Gestión de Tareas |
| Progreso operativo | Gestión de Tareas |
| Deadline de objetivo | Gestión de Tareas |
| Punto de reentrada | Gestión de Tareas |
| Agenda y eventos | Calendario |
| Disponibilidad resumida | Contexto |
| Estado personal relevante | Contexto |
| Sesión prevista | Planificación |
| Trabajo todavía no integrado | Inbox |

Regla:

> Un dato tiene una fuente maestra. Otros módulos pueden consultarlo o mostrar un resumen, pero no deben mantener una versión paralela.

---

## 5. Flujo de información nueva

```text
Nueva información
      ↓
Captura
      ↓
Inbox
      ↓
Procesamiento
      ├→ descartar
      ├→ referencia
      ├→ objetivo de proyecto existente
      ├→ cambio de Contexto
      └→ nuevo proyecto → Evaluación Estratégica → Inventario
```

Si el elemento no puede esperar a la próxima Revisión Semanal:

```text
Procesamiento ASAP
      ↓
¿solo cambia qué hacer?
      → Replanificación

¿cambia qué proyectos reciben capacidad?
      → Reevaluación de Activación
```

---

## 6. Flujo proyecto → ejecución

```text
Inventario
   ↓
Activación
   ↓
Proyecto activo
   ↓
Gestión de Tareas
   ↓
Objetivos ejecutables
   ↓
Planificación
   ↓
Sesión + resultado esperado
   ↓
Ejecución
   ↓
Actualizar Gestión de Tareas / Capturar novedades
```

---

## 7. Flujo de Contexto

```text
Calendario ───────────┐
Eventos externos ─────┤
Estado de proyectos ──┼→ CONTEXTO SEMANAL
Estado personal ──────┤
Cambios relevantes ───┘
```

El Contexto alimenta dos decisiones distintas:

- **Activación:** qué puede comprometerse.
- **Planificación:** cómo utilizar la capacidad realmente disponible.

---

## 8. Niveles temporales

### Estratégico

Pregunta:

> ¿Esto merece formar parte del sistema?

Módulos:

- Evaluación Estratégica;
- Inventario Maestro.

### Táctico

Pregunta:

> ¿Qué voy a sostener y cómo encaja en este período?

Módulos:

- Contexto;
- Activación;
- Planificación semanal;
- Revisión Semanal.

### Operativo

Pregunta:

> ¿Qué hago ahora y cómo quedó?

Módulos:

- Gestión de Tareas;
- Planificación local;
- Ejecución;
- actualización de estado.

---

## 9. Escalamiento de cambios

### Cambio pequeño

Ejemplo: una tarea termina antes.

→ ajuste local.

### Cambio que afecta el plan

Ejemplo: desaparece una ventana importante.

→ replanificación.

### Cambio que afecta compromisos o capacidad global

Ejemplo: aparece un cliente importante, enfermedad, viaje o nueva obligación fuerte.

→ reevaluación extraordinaria de Activación.

---

## 10. Revisión Semanal

Secuencia:

```text
1. Procesar Inbox
2. Actualizar proyectos y objetivos
3. Actualizar Inventario
4. Construir Contexto Semanal
5. Ejecutar Activación
6. Revisar objetivos de proyectos activos
7. Planificar la semana
8. Preparar sesiones con alta fricción
9. Verificar viabilidad global
```

Al terminar deben quedar coherentes:

- Inbox;
- Inventario;
- Contexto;
- proyectos activos;
- objetivos operativos;
- plan semanal.

---

## 11. Principio general

El sistema no intenta producir una lista perfecta de todo lo que debería hacerse.

Mantiene una cadena coherente:

```text
realidad
→ decisiones estratégicas
→ compromisos
→ trabajo disponible
→ decisiones de uso del tiempo
→ ejecución
→ nueva realidad
```

Su objetivo es reducir la necesidad de reconstruir mentalmente todas las prioridades cada vez que aparece una ventana libre.
