# JQF SDD Foundation

## ¿Qué es JQF SDD Foundation?

JQF SDD Foundation es una base reutilizable para diseñar, documentar, gobernar y evolucionar proyectos mediante Specification Driven Development (SDD).

Puede utilizarse para:

- sistemas basados en agentes;
- aplicaciones software;
- proyectos de datos;
- automatizaciones;
- sistemas de IA;
- proyectos híbridos.

Su propósito es proporcionar una estructura común que permita construir proyectos de forma consistente, trazable y mantenible.

No es un framework de ejecución.

No es un runtime de agentes.

No contiene lógica de negocio.

No contiene implementaciones productivas.

Es la capa de diseño, gobierno y documentación sobre la que se construyen proyectos específicos.

---

## ¿Por qué existe?

Muchos proyectos tecnológicos comienzan implementando soluciones antes de definir correctamente:

* el problema a resolver;
* el alcance;
* los límites;
* las responsabilidades;
* los criterios de validación;
* los mecanismos de gobierno.

Esto suele provocar:

* documentación inconsistente;
* agentes difíciles de mantener;
* duplicación de lógica;
* falta de trazabilidad;
* implementación prematura;
* crecimiento desordenado del sistema.

JQF SDD Foundation proporciona una estructura común para evitar estos problemas.

---

## ¿Qué incluye?

### Gobierno SDD (Estado actual)

* Instructions SDD ✓
* Reglas de precedencia documental ✓
* Criterios de readiness ✓
* Context Governance (framework definido, en evolución)
* Context References (framework definido, en evolución)
* Trazabilidad de fuentes de contexto ✓

### Agentes metodológicos (Actuales)

* Legacy to SDD Agent ✓
* Specification Agent ✓
* Architect Agent ✓
* Tasks Planner Agent ✓
* Reviewer Agent ✓
* Documentation Agent ✓
* QA Gate Agent ✓
* Implementation Agent ✓

### Skills reutilizables (Actuales)

* git-sync-main (sync controlado con GitHub) ✓
* legacy-to-sdd (descubrimiento de proyectos existentes) ✓
* cloud-runtime-discovery (discovery metodológico) ✓
* data-platform-discovery (discovery metodológico) ✓
* integration-discovery (discovery metodológico) ✓

### Plantillas (Actuales)

* Project Brief Template ✓
* Specification Template ✓
* Architecture As-Is Template ✓
* Context References Template ✓
* SDD Readiness Assessment Template ✓
* System Overview Template ✓
* Client Context Document (CCD) Template ✓
* Contracts Template ✓
* Copilot Instructions Template ✓
* Data Lineage Template ✓
* Legacy Procedure Template ✓
* Retrospective Spec Template ✓
* AGENTS Template ✓

### Documentación (Actual)

* Glosario SDD (glosario_terminos.md) ✓
* Definiciones de artefactos (incluidas en glosario) ✓
* Convenciones de gobierno (sdd.instructions.md) ✓
* Reglas de trazabilidad (incluidas en instrucciones) ✓

---

## ¿Qué NO incluye?

Esta foundation no incluye:

* lógica de negocio;
* SOPs;
* conocimiento específico de clientes;
* herramientas reales;
* integraciones;
* runtimes de agentes;
* infraestructura;
* despliegues;
* implementaciones productivas.

Todos esos elementos pertenecen a los repositorios construidos a partir de esta foundation.

---

## Conceptos principales

### Project Brief

Define por qué existe un proyecto.

### Specification

Define qué es una capacidad y qué debe hacer.

### Gate

Controla la transición entre fases.

### Eval

Valida calidad y comportamiento esperado.

### Skill

Define conocimiento operativo reutilizable.

### Agent

Representa una responsabilidad estable dentro del sistema.

### SDD Harness

Sistema de gobierno utilizado para diseñar y evolucionar capacidades.

### Operational Harness

Sistema utilizado para gobernar y ejecutar capacidades operativas en producción, incluyendo agentes, herramientas, integraciones y procesos automatizados.

---

## Ciclo de trabajo recomendado

```text
Project Brief
↓
Specification
↓
Structure
↓
Tasks
↓
Development
↓
Validation
↓
Active
```

---

## Estructura actual del repositorio

```text
AGENTS.md
README.md

.github/
├── agents/                    # Agentes metodológicos definidos
├── instructions/              # Instrucciones SDD y gobierno
├── prompts/                   # Prompts reutilizables
├── copilot-instructions.md    # Instrucciones de Copilot
└── skills/                    # Skills metodológicas y de discovery

docs/
├── glosario_terminos.md       # Glosario SDD
└── templates/                 # Plantillas reutilizables

specs/
├── templates/                 # Plantillas de specifications
└── .gitkeep

tests/
├── evals/                     # Evaluaciones
└── .gitkeep

tools/
workflows/
memory/
gates/
```

---

## Cómo utilizar esta Foundation

### Paso 1

Clonar el repositorio.

### Paso 2

Crear un Project Brief utilizando la plantilla base.

### Paso 3

Utilizar el Specification Agent para generar las specifications iniciales.

### Paso 4

Definir las capacidades necesarias para el proyecto.

### Paso 5

Validar la documentación mediante los gates correspondientes.

### Paso 6

Iniciar Development únicamente cuando exista aprobación explícita.

---

## Principios de diseño

* Human-in-the-loop
* No implementación prematura
* Trazabilidad antes que velocidad
* Documentación antes que ejecución
* Evolución controlada
* Separación de responsabilidades
* Source of Truth única
* Simplicidad sobre complejidad

---

## Cómo se utiliza esta Foundation

JQF SDD Foundation no contiene proyectos de negocio.

Su función es proporcionar una base reutilizable para crear nuevos repositorios basados en SDD.

Cada proyecto se desarrolla en su propio repositorio independiente.

```text
JQF SDD Foundation
        ↓ utilizada como base

Repositorio derivado 1

Repositorio derivado 2

Repositorio derivado N
```

La Foundation proporciona:

* metodología;
* gobernanza;
* agentes metodológicos;
* skills reutilizables;
* plantillas;
* reglas de trabajo;
* glosario;
* artefactos SDD.

Cada repositorio derivado define posteriormente:

* su Project Brief;
* sus Specifications;
* sus agentes operativos;
* sus workflows;
* sus evaluaciones;
* sus herramientas;
* sus integraciones.

---

## Alcance actual

El estado vigente del repositorio está en fase **Specification / Structure**. No estamos en Development.

**En scope ahora:**

* Specification de metodología SDD
* Structure de artefactos y gobierno
* Governance documental y procedural
* Documentación y plantillas reutilizables
* Agentes metodológicos (governance, no ejecución)
* Skills de descubrimiento y soporte documental

**Fuera de scope (Roadmap futuro):**

* Ejecución operativa de agentes (pertenece a proyectos derivados)
* Operational Harness (implementación en proyectos derivados)
* GitHub Workflow Agent (planeado, no implementado aún)
* Gates totalmente automatizados (están como estructura documental)
* Workflows ejecutables en producción

---

## Relación con Harness Engineering

JQF SDD Foundation implementa un **SDD Harness** (eje actual).

Un SDD Harness es un sistema de gobierno diseñado para controlar cómo se diseñan, documentan, validan y evolucionan capacidades, componentes y sistemas dentro de un proyecto.

### SDD Harness (Implementado hoy)

Esta foundation proporciona:

* Estados y fases definidas (Specification, Structure, Development)
* Reglas de precedencia documental
* Agentes metodológicos (8 agentes operativos)
* Estructura de gates (framework definido)
* Framework de evaluaciones
* Artefactos base y plantillas
* Criterios de readiness
* Context Governance

### Operational Harness (Roadmap futuro)

No implementado aún en esta foundation.

El Operational Harness pertenecerá a los repositorios derivados y será responsable de:

* Ejecución de agentes funcionales
* Herramientas operativas reales
* Observabilidad y monitoreo
* Evaluaciones automáticas en producción
* Workflows ejecutables
* Integraciones productivas

