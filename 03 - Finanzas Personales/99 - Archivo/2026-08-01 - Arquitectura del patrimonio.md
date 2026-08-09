# Sesión 03 - Arquitectura del patrimonio

## Objetivo de la sesión

Iniciar el diseño del Mapa Financiero Personal, definiendo la función que debe cumplir cada parte del patrimonio antes de seleccionar instrumentos de inversión.

---

# Resumen ejecutivo

Durante la sesión se concluyó que el patrimonio debe organizarse según la función que cumple cada parte del dinero y no según la institución financiera donde se encuentre depositado.

Se decidió mantener una arquitectura simple, evitando categorías innecesarias.

---

# Ideas discutidas

## 1. Separar función e implementación

Se identificó que cuentas bancarias (BBVA, BCP, etc.) representan únicamente la ubicación del dinero.

La organización financiera debe responder a la pregunta:

> ¿Para qué existe este dinero?

y no a:

> ¿Dónde está guardado?

---

## 2. Colchón de seguridad

Se definió el colchón como un fondo de protección del sistema financiero.

Su propósito no es aprovechar oportunidades de inversión ni financiar objetivos planificados.

Se utilizará únicamente en situaciones excepcionales como:

- emergencias médicas;
- problemas familiares graves;
- pérdida de empleo (solo como último recurso).

Para oportunidades planificadas se buscarán otras fuentes de liquidez antes de utilizar este fondo.

---

## 3. Capital de crecimiento

Se definió como el dinero destinado a preservar y aumentar el poder adquisitivo en el largo plazo.

Objetivos:

- superar la inflación;
- generar crecimiento sostenido;
- mantener un riesgo bajo en la etapa inicial;
- evolucionar gradualmente hacia un perfil moderado.

No existe interés en estrategias especulativas ni en dedicar una cantidad significativa de tiempo al seguimiento de inversiones.

---

## 4. Arquitectura preliminar

Se propuso la siguiente estructura funcional del patrimonio:

Patrimonio

- Colchón de seguridad
- Capital para objetivos
    - Maestría
    - Independencia
    - Otros objetivos futuros
- Capital de crecimiento
- AFP

Esta estructura constituye la primera versión conceptual del Mapa Financiero Personal.

---

# Decisiones tomadas

- Organizar el patrimonio por función y no por institución financiera.
- Mantener una arquitectura simple.
- No seleccionar todavía instrumentos de inversión.
- Continuar el diseño cuantitativo en la siguiente sesión.

---

# Pendientes

La siguiente sesión deberá definir:

- monto objetivo del colchón de seguridad;
- monto destinado a objetivos específicos;
- capital disponible para crecimiento;
- reglas para distribuir nuevos ingresos;
- primera asignación cuantitativa del patrimonio.