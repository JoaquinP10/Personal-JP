# Sistema de Planificación

**Versión:** v1.0  
**Estado:** Especificación conceptual  
**Área:** 04 - Organización y Productividad

---

## 1. Propósito

El Sistema de Planificación transforma la capacidad previamente comprometida por el Sistema de Activación en trabajo concreto y ejecutable.

Responde a dos preguntas:

1. **A nivel semanal:** ¿cómo proteger los compromisos activos y preparar oportunidades razonables de avance durante la semana?
2. **A nivel local:** dada una ventana concreta y el estado actual, ¿qué conviene hacer ahora?

Su objetivo no es maximizar horas productivas ni llenar cada espacio disponible, sino utilizar la capacidad de manera razonable, sostenible y compatible con los compromisos existentes.

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
Construcción del Contexto
      ↓
Sistema de Activación
      ↓
Proyectos comprometidos / activos
      ↓
Sistema de Planificación
      ↓
Sesiones / trabajo concreto
      ↓
Ejecución
      ↓
Actualización de estado
      ↓
Revisión / realimentación
```

### Límites de responsabilidad

El Sistema de Planificación:

- no decide si una idea merece convertirse en proyecto;
- no decide qué proyectos existen;
- no activa arbitrariamente proyectos;
- no redefine prioridades estratégicas;
- no obliga a ocupar cada hora libre.

La planificación trabaja exclusivamente con proyectos que ya fueron comprometidos por el Sistema de Activación.

Si un cambio importante hace necesario considerar un proyecto actualmente no activo, primero debe producirse una reevaluación extraordinaria del Sistema de Activación.

---

## 3. Relación con otros módulos

### 3.1 Inventario Maestro

El Inventario Maestro representa lo que existe.

Planificación no consulta el inventario completo para decidir cada sesión. Trabaja principalmente con el subconjunto de proyectos activos.

### 3.2 Sistema de Activación

Activación decide qué proyectos reciben capacidad durante el período actual.

Planificación decide cómo utilizar esa capacidad en el tiempo real disponible.

```text
Activación → qué merece capacidad
Planificación → cómo utilizar esa capacidad
```

### 3.3 Contexto

El módulo de Contexto construye una representación resumida de la situación relevante, especialmente durante la Revisión Semanal.

Planificación consume ese contexto, pero no vuelve a construirlo desde cero.

Durante la semana puede añadir un **contexto local de ejecución**, formado por información dinámica como:

- tiempo realmente disponible;
- energía actual;
- motivación;
- fricción;
- flow;
- cambios ocurridos desde la planificación inicial.

### 3.4 Gestión de tareas / estado del trabajo

Planificación necesita conocer qué trabajo es ejecutable, pero no debería convertirse en el repositorio principal de todas las tareas.

Las próximas acciones, tareas pendientes, estimaciones, bloqueos y avances pertenecen al Sistema de Gestión de Tareas y Objetivos.

Planificación los consume para tomar decisiones.

---

## 4. Dos niveles de planificación

### 4.1 Planificación semanal

Se realiza después de la Activación dentro del ciclo de Revisión Semanal.

Su función es:

- revisar compromisos y deadlines;
- observar la distribución real de disponibilidad;
- comprobar si existe una ruta viable para cumplir las obligaciones;
- reservar o proteger ventanas cuando sea necesario;
- identificar sesiones razonables para proyectos activos;
- preparar proyectos con alta fricción de entrada;
- evitar depender de capacidad futura poco confiable.

La planificación semanal no necesita asignar rígidamente cada hora.

Su producto principal es una estructura de oportunidades, restricciones y sesiones candidatas.

### 4.2 Planificación local o de sesión

Se realiza cuando existe una ventana concreta de ejecución.

Su función es responder:

> ¿Qué conviene hacer ahora?

Utiliza la planificación semanal como referencia, pero incorpora el estado real del momento.

Puede modificar localmente lo previsto cuando las condiciones actuales justifican hacerlo.

---

## 5. Entradas

### 5.1 Proyectos activos

Conjunto de proyectos que actualmente tienen capacidad comprometida.

### 5.2 Disponibilidad

Describe cuándo existe tiempo y cómo está estructurado.

Incluye:

- bloques ocupados;
- trabajo;
- docencia;
- reuniones;
- citas;
- traslados;
- compromisos personales;
- ventanas libres;
- duración y distribución de esas ventanas;
- grado de certeza de ventanas futuras.

La estructura temporal importa:

> cinco horas continuas no equivalen necesariamente a cinco ventanas de una hora.

### 5.3 Estado del trabajo

Cuando sea relevante, el sistema puede necesitar:

- trabajo pendiente;
- siguiente acción;
- estimación aproximada;
- deadline o restricción temporal;
- bloqueos y dependencias;
- grado de preparación;
- divisibilidad del trabajo;
- posibilidad de alcanzar un punto de cierre útil.

No todos estos elementos deben convertirse obligatoriamente en campos permanentes. Solo deben mantenerse cuando cambien decisiones reales.

### 5.4 Estado personal

Información dinámica:

- energía;
- motivación;
- fricción;
- flow;
- continuidad o cadencia reciente.

### 5.5 Contexto relevante

Incluye cambios capaces de modificar una decisión:

- trabajo inesperado;
- cambios de horario;
- respuestas de terceros;
- nuevas urgencias;
- incertidumbre sobre capacidad futura;
- cambios significativos en el estado de un proyecto.

---

## 6. Principio de protección de compromisos

Antes de comparar proyectos por motivación o conveniencia, Planificación comprueba si existen obligaciones temporalmente comprometidas.

Un deadline no produce automáticamente prioridad inmediata.

La presión depende de la combinación de:

```text
deadline
+ trabajo restante
+ capacidad disponible antes del deadline
+ calidad de esa capacidad
+ incertidumbre
+ consecuencias de posponer
```

La pregunta central es:

> Si no hago esto ahora, ¿sigue existiendo una ruta suficientemente segura para cumplir?

---

## 7. Margen de cumplimiento

El margen no se interpreta como un buffer horario rígido, sino como el grado de seguridad de la ruta futura.

### Margen crítico

La capacidad futura apenas cubre el trabajo necesario o resulta insuficiente.

Consecuencia:

> La obligación domina la decisión.

Energía, motivación y preferencias pasan a segundo plano mientras siga siendo razonable ejecutar.

### Margen reducido

Existe cierta tolerancia, pero poca.

Consecuencia:

> Conviene realizar un avance significativo y proteger capacidad futura.

### Margen cómodo

Existe una ruta suficientemente segura.

Consecuencia:

> El trabajo puede distribuirse entre sesiones y compartir capacidad con otros proyectos.

### Margen amplio

El compromiso está bajo control.

Consecuencia:

> La decisión vuelve a depender principalmente de ejecutabilidad, avance posible, estado personal y otros proyectos activos.

No se requieren umbrales numéricos universales.

---

## 8. Capacidad nominal, utilizable y robusta

Las horas disponibles no son equivalentes.

### Capacidad nominal

Tiempo que aparentemente existe.

### Capacidad utilizable

Tiempo que razonablemente puede aprovecharse dadas las condiciones previstas.

### Capacidad robusta

Capacidad que probablemente seguirá siendo utilizable incluso si ocurre una contingencia plausible.

Ejemplo:

```text
Sábado → 3 h continuas, buena energía
Lunes → 1 h después del trabajo, energía baja
```

No deben tratarse como cuatro horas equivalentes.

Planificación administra tanto capacidad como riesgo.

---

## 9. Incertidumbre y contingencia

Cuando existe una probabilidad relevante de perder capacidad futura, el sistema puede adelantar trabajo para comprar margen.

No requiere probabilidades exactas.

Puede utilizar evaluaciones cualitativas como:

- baja;
- moderada;
- alta;
- prácticamente segura.

Una ventana futura incierta puede utilizarse como buffer en lugar de convertirse en la base del cumplimiento.

---

## 10. Varias obligaciones simultáneas

Cuando varias obligaciones presentan presión al mismo tiempo, el sistema no divide automáticamente el tiempo en proporciones iguales.

Primero busca construir una ruta viable para cumplirlas.

Después considera propiedades operativas como:

- margen;
- deadline;
- divisibilidad;
- dependencia de bloques largos;
- calidad de futuras ventanas;
- continuidad;
- dependencias externas.

Una tarea menos divisible o más sensible a interrupciones puede recibir primero una ventana larga, mientras una tarea altamente fragmentable puede distribuirse entre ventanas posteriores.

---

## 11. Ejecutabilidad

Cuando no existe una obligación dominante, la planificación filtra qué opciones son razonables para la ventana actual.

La ejecutabilidad surge de combinar:

```text
tiempo disponible
× energía
× siguiente acción
× preparación
× fricción
× naturaleza y tamaño del trabajo
```

Un proyecto importante puede quedar fuera de una sesión concreta si sus condiciones de ejecución son desfavorables.

Esto no modifica su importancia estratégica.

---

## 12. Importancia, presión y ejecutabilidad

Son conceptos diferentes.

### Importancia

Valor estratégico relativamente estable del proyecto.

### Presión

Necesidad de actuar pronto para proteger un compromiso o deadline.

### Ejecutabilidad

Qué tan razonable es avanzar el proyecto bajo las condiciones actuales.

Ejemplo:

```text
Tesis
Importancia: alta
Presión: baja
Ejecutabilidad actual: baja
```

La decisión de no trabajar en Tesis durante una ventana concreta no implica que sea poco importante.

---

## 13. Avance significativo

Entre varias opciones ejecutables importa cuánto progreso útil puede producirse en la ventana disponible.

Una actividad puede ser preferible si permite:

- cerrar una tarea;
- completar una unidad coherente;
- producir un resultado visible;
- reducir significativamente trabajo pendiente.

La planificación no busca maximizar cantidad de tareas, sino favorecer progreso razonable dentro de las condiciones reales.

---

## 14. Motivación, fricción y flow

Estos factores se consideran principalmente después de identificar opciones razonablemente viables.

Pueden:

- desempatar opciones;
- modificar la conveniencia de una sesión;
- justificar continuidad;
- permitir aprovechar una condición excepcional;
- influir en una transición entre actividades.

La motivación no gobierna el sistema por sí sola, pero tampoco se ignora.

---

## 15. Preparación como avance válido

No toda sesión tiene que producir avance directo.

### Avance directo

Produce resultados dentro del proyecto.

### Avance preparatorio

Reduce materialmente la fricción de una sesión futura.

Ejemplos:

- definir la siguiente acción;
- escoger un recurso;
- preparar el entorno;
- recuperar contexto;
- ordenar materiales;
- dejar claramente definido cómo continuar.

Una ventana corta puede utilizarse para preparar un proyecto de alta fricción si eso aumenta significativamente su ejecutabilidad futura.

---

## 16. Descanso como salida válida

Tiempo libre no equivale automáticamente a capacidad productiva.

Cuando:

- la energía es insuficiente;
- ninguna opción encaja bien;
- el coste de entrada supera el avance posible;
- la carga acumulada ya es alta;

el descanso puede ser la mejor decisión de planificación.

El sistema no debe optimizar el descanso fuera de la vida personal ni tratarlo como un fallo.

---

## 17. Salida de planificación

La unidad principal de salida es:

> **sesión de trabajo + resultado esperado**

Ejemplo:

```text
Sábado 15:00
Proyecto: GitHub

Resultado esperado:
Terminar reorganización de X.

Estimación:
~2 h

Si queda capacidad:
Preparar próxima sesión de AWS.
```

La duración es orientativa.

El punto de cierre y el resultado esperado son más importantes que respetar exactamente el tiempo estimado.

---

## 18. Ejecución adaptativa

Un plan representa la mejor decisión disponible antes de comenzar, no una orden rígida.

```text
Plan
 ↓
Ejecutar
 ↓
Observar
 ↓
Ajustar
```

Durante la ejecución se observan:

- tiempo restante;
- energía;
- flow;
- avance;
- distancia al cierre;
- cambios del contexto.

---

## 19. Reevaluación intrasesión

### 19.1 Si se termina antes

Orden razonable de evaluación:

1. continuación natural del mismo proyecto;
2. adelantar otra actividad ya prevista;
3. utilizar el remanente para preparación;
4. descansar.

La elección depende de tiempo restante, energía y flow.

### 19.2 Si la tarea se alarga

Puede extenderse cuando:

- existe flow;
- falta relativamente poco;
- alcanzar el cierre tiene valor;
- no se perjudica un compromiso superior.

No se corta una sesión únicamente porque terminó la estimación horaria.

### 19.3 Si cae la energía

Cuando sea razonable, se busca un punto de cierre corto antes de detenerse.

Ejemplos:

- terminar una unidad;
- registrar el estado;
- dejar preparada la reanudación.

Después se puede descansar o, excepcionalmente, realizar una actividad ligera con una razón concreta.

### 19.4 Si aparece una oportunidad excepcional

Una condición inusualmente favorable para un proyecto importante puede justificar cambiar el plan.

Antes de cambiar se busca, cuando sea posible, un cierre razonable de la actividad actual.

---

## 20. Principio del punto de cierre

El punto de cierre pesa más que la duración exacta planificada.

Puede ser correcto:

- extender una sesión algunos minutos;
- terminar antes;
- detenerse al alcanzar un estado estable;
- cambiar de actividad después de dejar el contexto preparado.

Las estimaciones orientan; no gobiernan rígidamente la ejecución.

---

## 21. Ajuste local vs replanificación

### Ajuste local

No requiere reconstruir el plan de la semana.

Ejemplos:

- terminar 20 minutos antes;
- extender 30 minutos;
- aprovechar flow;
- realizar una preparación breve.

### Replanificación

Se justifica cuando existe un cambio relevante:

- alteración fuerte de disponibilidad;
- aparición de una urgencia;
- caída significativa de energía;
- cambio importante en un proyecto;
- oportunidad excepcional;
- error de estimación que afecta otros compromisos.

Si el cambio también altera qué proyectos deberían recibir capacidad, debe escalar al Sistema de Activación.

---

## 22. Algoritmo conceptual

```text
VENTANA / SEMANA DISPONIBLE
        +
PROYECTOS ACTIVOS
        +
CONTEXTO
        ↓

1. Detectar obligaciones con presión
        ↓
2. Evaluar margen, capacidad robusta y riesgo
        ↓
3. Proteger una ruta viable de cumplimiento
        ↓
4. Identificar capacidad restante
        ↓
5. Filtrar opciones por ejecutabilidad
        ↓
6. Comparar avance posible
        ↓
7. Considerar energía, motivación,
   fricción y flow
        ↓
8. Elegir sesión y resultado esperado
        ↓
9. Ejecutar
        ↓
10. Observar el estado real
        ↓
11. Continuar / ajustar / cambiar /
    preparar / descansar
        ↓
12. Actualizar estado del trabajo
```

---

## 23. Reglas de escalamiento

El Sistema de Planificación puede resolver cambios locales mientras los proyectos activos sigan siendo válidos.

Debe solicitar una reevaluación de Activación cuando un cambio:

- modifica materialmente la capacidad disponible;
- introduce un nuevo compromiso importante;
- convierte un proyecto inactivo en candidato necesario;
- hace inviable sostener todos los proyectos comprometidos;
- cambia significativamente el conjunto de compromisos.

Esto preserva una única autoridad sobre qué proyectos reciben capacidad.

---

## 24. Principios del sistema

1. **Planificar no es llenar el calendario.**
2. **Un proyecto importante no siempre es el mejor proyecto para una sesión concreta.**
3. **Los deadlines importan por el margen que dejan, no solo por existir.**
4. **Una hora disponible no siempre equivale a una hora utilizable.**
5. **La planificación debe proteger rutas de cumplimiento suficientemente robustas.**
6. **Las tareas divisibles y no divisibles deben tratarse de forma diferente.**
7. **La preparación puede ser progreso válido cuando reduce fricción futura.**
8. **El descanso es una salida válida.**
9. **El punto de cierre pesa más que respetar rígidamente una duración estimada.**
10. **El plan guía; la realidad realimenta y puede corregirlo.**
11. **Planificación administra la capacidad comprometida; Activación decide qué proyectos merecen esa capacidad.**
12. **El objetivo es tomar decisiones suficientemente buenas y sostenibles, no encontrar una asignación matemáticamente perfecta del tiempo.**

---

## 25. Estado de la especificación

La arquitectura conceptual del Sistema de Planificación se considera suficientemente definida para una primera implementación.

Quedan para fases posteriores:

- decidir qué datos deben almacenarse explícitamente y cuáles deben evaluarse de forma informal;
- diseñar la interfaz práctica de planificación semanal;
- definir la herramienta o herramientas de soporte;
- formalizar el sistema de gestión de tareas / próximas acciones;
- validar el modelo completo con semanas reales y ajustar solo donde aparezca fricción real.
