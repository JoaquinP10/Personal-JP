# Sesión 08 - Exploración del Sistema de Planificación

## Objetivo de la sesión

Continuar el diseño conceptual del sistema de organización personal, entrando en el bloque de **Planificación** después de haber definido el Sistema de Activación.

La pregunta central de esta fase es:

> Una vez que el Sistema de Activación determina qué proyectos están activos, ¿cómo se convierte esa capacidad disponible en trabajo concreto?

La sesión se planteó como una serie de casos de uso para descubrir la lógica natural de decisión, en lugar de imponer inicialmente una metodología de planificación.

---

# 1. Distinción entre Activación y Planificación

Se identificó una separación importante entre ambos sistemas.

## Sistema de Activación

Responde:

> ¿Qué proyectos están autorizados a recibir capacidad?

Por ejemplo:

- Linux
- GitHub
- Fux
- Tesis

El hecho de que un proyecto esté activo no significa que deba trabajarse en cualquier momento.

## Sistema de Planificación

Responde:

> De los proyectos activos, ¿cuál tiene sentido trabajar ahora y cómo utilizar la capacidad disponible?

Por tanto:

```text
Sistema de Activación
        ↓
Proyectos activos
        ↓
Sistema de Planificación
        ↓
Actividad concreta
        ↓
Ejecución
```

---

# 2. La unidad real de planificación

Inicialmente se consideró que la planificación podría consistir en:

```text
Proyecto → Resultado → Tareas → Tiempo
```

Sin embargo, los casos mostraron que el primer problema real es diferente:

> Tengo un bloque de tiempo disponible. ¿Cómo decido qué hacer con él?

Por tanto, la planificación debe comenzar desde la **capacidad disponible**, no exclusivamente desde las tareas existentes.

La capacidad disponible depende principalmente de:

- tiempo;
- energía;
- compromisos;
- restricciones temporales.

---

# 3. Planificación no equivale a llenar el calendario

Se identificó que tener tiempo libre no significa automáticamente que deba asignarse a un proyecto.

El tiempo libre representa:

> Capacidad que todavía debe ser asignada.

Las posibles asignaciones pueden incluir:

- proyectos;
- tareas;
- actividades administrativas;
- descanso;
- tiempo personal.

Por tanto:

> **El objetivo de la planificación no es maximizar las horas productivas.**

Es asignar la capacidad a aquello que tenga sentido dadas las condiciones actuales.

El descanso constituye una alternativa válida incluso cuando existe tiempo y energía disponibles.

---

# 4. Caso: varias opciones y tiempo suficiente

Situación:

- sábado;
- 15:00–20:00;
- energía alta;
- proyectos activos: Linux, GitHub, Tesis y Fux;
- sin deadlines inmediatos.

La lógica natural fue:

1. Fux tendría prioridad inicialmente por tratarse de trabajo y existir feedback reciente.
2. Una vez avanzado Fux, podría aprovecharse el estado de concentración para continuar con Linux o GitHub.
3. Tesis probablemente no sería elegida en ese contexto.

Esto mostró que:

> **La importancia general de un proyecto no determina automáticamente qué proyecto debe ejecutarse en un momento concreto.**

---

# 5. Sesiones dominantes

Cuando existe motivación y flow para trabajar en la tesis, puede convertirse en una sesión dominante:

```text
Tesis
↓
3–5 horas
↓
No necesariamente se introduce otro proyecto
```

En cambio, Linux o GitHub pueden funcionar mejor como sesiones independientes de duración moderada.

Esto muestra que:

> **La duración adecuada de una sesión depende del proyecto y del tipo de trabajo.**

No debe asumirse que todo bloque disponible debe dividirse en múltiples tareas.

---

# 6. Deadlines y urgencia

Se comprobó que la existencia de un deadline modifica fuertemente la planificación.

Sin embargo:

> Tener deadline no constituye una condición binaria de prioridad.

Lo relevante es el **margen real disponible antes del deadline**.

Ejemplo:

### Deadline lunes

Si es sábado y el domingo no se considera día laboral para E2i:

```text
Sábado → domingo no disponible → lunes
```

El margen real es muy pequeño.

Por tanto, Fux prácticamente domina la decisión.

### Deadline martes

Si el lunes existe suficiente capacidad para terminar Fux, entonces el sábado puede existir espacio para trabajar en otro proyecto, como la tesis.

### Conclusión

La planificación debe considerar:

> **Tiempo hasta el deadline + capacidad realmente disponible antes del deadline.**

Por tanto, la urgencia es contextual y aumenta conforme disminuye el margen de cumplimiento.

---

# 7. Restricciones temporales por dominio

Se aclaró que no todos los dominios utilizan el tiempo de la misma manera.

En particular:

- E2i se desarrolla fundamentalmente dentro del horario laboral.
- Es muy poco habitual trasladar trabajo de E2i fuera de dicho horario.
- Docencia y proyectos personales pueden tener deadlines que sí compitan por tiempo personal.

Por tanto, el sistema no debería tratar toda la capacidad temporal como homogénea.

Debe reconocer las restricciones propias de cada dominio.

---

# 8. Ausencia de deadlines

Cuando no existen:

- deadlines;
- compromisos inmediatos;
- tareas urgentes;

la selección depende principalmente de la conveniencia de ejecución.

En un bloque de 3 horas y energía media-alta:

### Linux

- duración razonable;
- siguiente trabajo relativamente claro;
- puede producir avance significativo.

### GitHub

- proyecto relativamente acotado;
- organización sencilla;
- posibilidad de generar progreso visible.

### AWS

- requiere mayor preparación;
- una sesión corta podría consumirse principalmente en preparación.

### Tesis

- puede absorber toda la sesión;
- requiere cierta preparación/cadencia;
- si existe motivación suficiente puede ser una excelente candidata;
- si no existe, su fricción inicial es alta.

Esto llevó a identificar una nueva dimensión:

> **Ejecutabilidad del proyecto en el contexto actual.**

---

# 9. Ejecutabilidad

La planificación no solo debe conocer la importancia de un proyecto.

También importa:

- cuánto tiempo requiere;
- cuánta energía exige;
- si tiene un siguiente paso claro;
- cuánto trabajo preparatorio necesita;
- si puede producir un avance significativo dentro de la ventana disponible.

Ejemplo:

```text
Linux
→ alta ejecutabilidad

GitHub
→ alta ejecutabilidad

AWS
→ menor ejecutabilidad si no está preparado

Tesis
→ menor ejecutabilidad si no existe contexto/cadencia
```

Esto explica por qué un proyecto importante puede perder frente a otro menos importante en una ventana concreta.

---

# 10. Poco tiempo + poca energía

Se analizó una situación especialmente relevante para el problema actual:

- llegada a casa después del trabajo;
- 1 h 30 min disponibles;
- energía baja-media;
- ningún deadline inmediato.

La jerarquía natural identificada fue aproximadamente:

```text
Proyecto simple y realizable
        ↓
Descanso
        ↓
AWS ya planeado
        ↓
GitHub
        ↓
Linux
        ↓
AWS no planeado
        ↓
Tesis
```

Con energía directamente baja:

```text
Descanso
```

se convierte probablemente en la opción dominante.

---

# 11. Energía disponible no equivale a capacidad que deba utilizarse

Se observó que incluso tener energía y tiempo disponible no implica necesariamente que deba ejecutarse un proyecto.

Ejemplo:

- miércoles;
- 20:00;
- 2 horas libres;
- energía alta;
- ningún deadline;
- nada previamente planificado.

Puede ocurrir:

```text
Energía alta
        +
Tiempo disponible
        ↓
¿Existe motivación?
    ↙           ↘
  Sí             No
  ↓               ↓
Trabajar       Descansar
```

Por tanto:

> **La ausencia de presión externa permite que la motivación tenga un papel importante en la selección.**

---

# 12. Motivación y flow

La motivación no parece ser una propiedad fija de la semana.

Puede actuar como un factor local de decisión.

Ejemplo:

- GitHub puede ser elegido si existe motivación para hacer una actividad relativamente poco atractiva pero sencilla.
- Linux puede ser elegido si existe disposición para concentrarse y estudiar.
- Tesis puede ser elegida cuando existe suficiente cadencia o motivación para entrar directamente en ella.

La motivación puede transformar una actividad inicialmente poco atractiva en una opción viable.

---

# 13. Momentum y continuidad

Se identificó el concepto de **momentum/flow** durante la ejecución.

Si una tarea termina antes de lo esperado:

### Situación A

Se terminó la tarea y existe cansancio o sensación de cierre.

→ Puede ser preferible descansar.

### Situación B

Se terminó la tarea y todavía existe energía y flow.

→ Puede ser conveniente continuar con otro proyecto.

Sin embargo, la siguiente actividad debería estar preparada previamente.

Ejemplo:

```text
GitHub
↓
termina antes
↓
flow
↓
Linux preparado
↓
continuar
```

Si Linux no está preparado, la necesidad de decidir qué hacer puede introducir fricción y hacer que se pierda el momentum.

Esto sugiere que la planificación anticipada puede tener una segunda función:

> **Preparar posibles siguientes acciones, no solamente reservar tiempo.**

---

# 14. Planificación como proceso adaptativo

Se descartó la idea de que una planificación deba considerarse un compromiso rígido.

Un bloque planificado representa:

> La mejor decisión conocida en el momento de planificar.

Durante la ejecución puede aparecer nueva información.

Por tanto:

```text
Planificación
      ↓
Ejecución
      ↓
Observación
      ↓
¿La situación cambió?
   ↙             ↘
 No              Sí
 ↓                ↓
Continuar      Reevaluar
```

---

# 15. Cuando falta energía durante una sesión

Si una sesión planificada deja de ser viable:

No existe una obligación automática de terminarla.

La decisión depende de:

- energía restante;
- motivación;
- tiempo necesario para terminar;
- urgencia;
- consecuencias de dejarla incompleta.

Puede ocurrir:

```text
Continuar
→ terminar
→ descansar
```

o:

```text
Detener
→ dejar pendiente
→ descansar
```

Ambas pueden ser decisiones correctas dependiendo del contexto.

---

# 16. Factores identificados

Durante los casos aparecieron los siguientes factores:

### Presión externa

- compromisos;
- deadlines;
- urgencia;
- consecuencias;
- margen disponible antes del deadline.

### Condiciones de ejecución

- tiempo disponible;
- energía;
- duración esperada;
- ejecutabilidad;
- preparación;
- siguiente acción clara.

### Estado interno

- motivación;
- flow;
- momentum;
- cadencia con el proyecto.

### Estado del proyecto

- progreso;
- trabajo pendiente;
- naturaleza de la actividad;
- posibilidad de generar un avance significativo.

Todavía no se ha definido una fórmula ni un sistema de puntuación para estos factores.

La evidencia obtenida sugiere que probablemente la decisión funcionará mejor como una **secuencia de filtros y decisiones contextuales** que como una puntuación única.

---

# 17. Modelo preliminar emergente

La arquitectura preliminar de planificación puede representarse así:

```text
              BLOQUE DISPONIBLE
                     ↓
            Evaluar situación actual
                     │
        ┌────────────┼────────────┐
        ↓            ↓            ↓
      Tiempo       Energía     Compromisos
        │            │            │
        └────────────┼────────────┘
                     ↓
            ¿Existe algo que
             deba atenderse?
                ↙       ↘
              Sí         No
              ↓           ↓
        Priorizar      Buscar
        compromiso    candidatos
                          ↓
               ┌──────────┼──────────┐
               ↓          ↓          ↓
          Importancia  Ejecutabilidad  Energía
               │          │          │
               └──────────┼──────────┘
                          ↓
                  Elegir actividad
                          ↓
                       EJECUTAR
                          ↓
                    Observar estado
                          ↓
                   ¿Cambió la situación?
                     ↙          ↘
                   No            Sí
                   ↓              ↓
               Continuar       Reevaluar
```

El descanso constituye una alternativa transversal en la selección.

---

# 18. Conclusiones de la sesión

La exploración mediante casos permitió identificar que el Sistema de Planificación debe ser:

### Contextual

La mejor actividad depende de la situación concreta, no solamente de la importancia global del proyecto.

### Adaptativo

Una decisión puede revisarse durante la ejecución.

### No maximalista

No debe intentar llenar todo el tiempo disponible con trabajo.

### Sensible a deadlines

Debe considerar el margen real disponible antes de un compromiso.

### Sensible a energía

Una actividad puede ser importante pero inviable con la energía disponible.

### Sensible a ejecutabilidad

Una actividad bien preparada y con un siguiente paso claro puede ser preferible a otra que requiere mucha preparación.

### Compatible con el descanso

Descansar puede ser la decisión correcta incluso cuando existe tiempo disponible.

### Capaz de aprovechar momentum

Una sesión puede extenderse o encadenarse con otra actividad si el estado de ejecución lo favorece y la siguiente actividad está preparada.

---

# Estado del diseño

Con esta sesión se considera terminada la **fase de exploración mediante casos del Sistema de Planificación**.

Todavía no se considera cerrado su diseño formal.

El siguiente paso será una **sesión de síntesis**, donde se deberá:

1. Extraer las reglas generales observadas en los casos.
2. Separar entradas, decisiones, salidas y mecanismos de reevaluación.
3. Distinguir reglas del sistema de preferencias personales.
4. Buscar contradicciones entre los casos.
5. Integrar Planificación con:

```text
Captura
    ↓
Inbox
    ↓
Evaluación
    ↓
Inventario Maestro
    ↓
Contexto
    ↓
Sistema de Activación
    ↓
Planificación
    ↓
Ejecución
    ↓
Reevaluación
```

Si la síntesis resulta consistente, se podrá considerar terminada la fase principal de **diseño conceptual del sistema** y comenzar las pruebas end-to-end utilizando semanas y situaciones reales.