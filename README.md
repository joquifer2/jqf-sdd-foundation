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

### Gobierno SDD

* Instructions SDD
* Control de fases
* Reglas de precedencia documental
* Criterios de readiness
* Gates de validación

### Agentes metodológicos

* Specification Agent
* Architect Agent
* Tasks Planner Agent
* Reviewer Agent
* Documentation Agent
* QA Gate Agent
* Implementation Agent
* GitHub Workflow Agent

### Skills reutilizables

* Skills metodológicas
* Skills de soporte operativo
* Procedimientos reutilizables

### Plantillas

* Project Brief Template
* Specification Template
* Eval Template
* Gate Template
* Workflow Template

### Documentación

* Glosario SDD
* Definiciones de artefactos
* Convenciones de gobierno
* Reglas de trazabilidad

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

## Estructura general del repositorio

```text
.github/
├── agents/
├── instructions/
└── skills/

docs/
├── templates/
└── glossary/

specs/
└── templates/

tests/
├── evals/
└── gates/

workflows/
└── templates/
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

Repositorio de Agentes 1

Repositorio de Agentes 2

Repositorio de Agentes N
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

El alcance actual de esta foundation está centrado en:

* Specification
* Structure
* Governance
* Documentación

La ejecución operativa de agentes queda fuera del alcance de la foundation y pertenece a cada proyecto concreto.

---

## Relación con Harness Engineering

JQF SDD Foundation implementa un SDD Harness.

Un SDD Harness es un sistema de gobierno diseñado para controlar cómo se diseñan, documentan, validan y evolucionan capacidades, componentes y sistemas dentro de un proyecto.

Esta foundation proporciona:

* estados;
* reglas;
* agentes metodológicos;
* gates;
* evaluaciones;
* artefactos;
* precedencia documental;
* criterios de readiness.

No implementa todavía un Operational Harness.

Los Operational Harness pertenecen a los repositorios derivados y son responsables de la ejecución real de agentes, herramientas, observabilidad y evaluaciones automáticas.

