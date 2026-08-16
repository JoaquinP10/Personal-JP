# Organización y Productividad

Sistema personal para decidir qué merece atención, convertir proyectos en trabajo ejecutable y mantener el sistema sincronizado con la realidad.

## Arquitectura

```text
Realidad
→ Captura
→ Inbox
→ Evaluación Estratégica
→ Inventario Maestro
→ Contexto
→ Activación
→ Gestión de Tareas / Objetivos
→ Planificación
→ Ejecución
→ Realimentación
```

La **Revisión Semanal** sincroniza periódicamente los módulos anteriores.

## Estructura

- `01 - Sistema/`: arquitectura y especificaciones conceptuales de los módulos principales.
- `02 - Hábitos/`: reservado para hábitos y rutinas cuando se formalicen.
- `03 - Procesos/`: procesos de entrada y evaluación, como Captura, Inbox y Evaluación Estratégica.
- `04 - Revisiones/`: procedimientos periódicos de operación del sistema.
- `05 - Inventario Maestro/`: registro vivo de proyectos existentes y su situación general.
- `06 - Inbox/`: punto único de captura de información nueva.
- `07 - Operación/`: estado operativo semanal y pilotos del sistema.
- `99 - Archivo/`: registros históricos de sesiones y decisiones. No constituye la especificación vigente.

## Documentos principales

### Sistema

- `01 - Sistema/00 - Mapa del Sistema.md`: arquitectura general, fuentes maestras e interfaces.
- `01 - Sistema/Sistema de Activacion.md`: decisión sobre qué proyectos reciben capacidad.
- `01 - Sistema/Sistema de Gestion de Tareas y Objetivos.md`: representación del trabajo dentro de los proyectos.
- `01 - Sistema/Sistema de Planificacion.md`: utilización concreta de la capacidad disponible.

### Operación

- `03 - Procesos/Captura e Inbox.md`
- `03 - Procesos/Evaluacion Estrategica.md`
- `04 - Revisiones/Revision Semanal.md`
- `05 - Inventario Maestro/Inventario_Maestro.md`
- `06 - Inbox/Inbox.md`
- `07 - Operación/README.md`

## Empezar ahora

La primera implementación utilizable se encuentra en:

- `06 - Inbox/Inbox.md`: capturar sin decidir.
- `07 - Operación/2026-08-17 - Semana 01.md`: ejecutar el piloto semanal.

El piloto concentra temporalmente Contexto, Activación, objetivos y planificación en un solo tablero para medir la fricción antes de separar datos o elegir herramientas.

## Principio de documentación

Los documentos fuera de `99 - Archivo` son **documentos vivos** y representan el sistema vigente.

Los registros de `99 - Archivo` conservan el razonamiento histórico y no deben modificarse salvo correcciones menores.

## Última actualización

2026-08-16
