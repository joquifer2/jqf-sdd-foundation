# AGENTS.md

## Propósito

Este documento describe los agentes metodológicos que forman parte de JQF SDD Foundation.

Su función es gobernar, documentar, revisar y validar la evolución de proyectos construidos mediante Specification Driven Development (SDD).

Estos agentes forman parte del SDD Harness.

No representan capacidades funcionales de negocio.

No forman un sistema multiagente operativo.

No ejecutan procesos productivos.

---

## Relación con el SDD Harness

Los agentes metodológicos son componentes especializados del SDD Harness.

Su responsabilidad es ayudar a mantener:

* coherencia documental;
* trazabilidad;
* control de alcance;
* readiness;
* validación;
* evolución controlada.

Los agentes metodológicos no sustituyen la validación humana.

Todas las decisiones relevantes permanecen bajo responsabilidad humana.

---

## Clasificación de agentes

### Agentes de definición

Responsables de transformar contexto y necesidades en artefactos estructurados.

* Specification Agent
* Architect Agent

---

### Agentes de planificación

Responsables de transformar definiciones en trabajo estructurado.

* Tasks Planner Agent

---

### Agentes de revisión

Responsables de revisar calidad y coherencia.

* Reviewer Agent
* Documentation Agent

---

### Agentes de validación

Responsables de verificar readiness y criterios de avance.

* QA Gate Agent

---

### Agentes de transición

Responsables de supervisar el paso desde Structure hacia Development.

* Implementation Agent

---

### Agentes de gobernanza GitHub

Responsables de mantener trazabilidad entre documentación y repositorio.

* GitHub Workflow Agent

---

## Catálogo de agentes

| Agente                | Responsabilidad principal                                        |
| --------------------- | ---------------------------------------------------------------- |
| Specification Agent   | Crear y revisar specifications                                   |
| Architect Agent       | Diseñar estructura documental y arquitectura conceptual          |
| Tasks Planner Agent   | Transformar specifications en tareas trazables                   |
| Reviewer Agent        | Revisar coherencia, alcance y calidad documental                 |
| Documentation Agent   | Mantener documentación consistente y actualizada                 |
| QA Gate Agent         | Validar readiness y cumplimiento de criterios de fase            |
| Implementation Agent  | Supervisar la transición controlada hacia Development            |
| GitHub Workflow Agent | Gestionar trazabilidad entre documentación, issues y repositorio |

---

## Flujo metodológico recomendado

```text
Project Brief
        ↓
Specification Agent
        ↓
Architect Agent
        ↓
Tasks Planner Agent
        ↓
Reviewer Agent
        ↓
Documentation Agent
        ↓
QA Gate Agent
        ↓
Implementation Agent
```

La secuencia puede variar según el proyecto.

El objetivo es garantizar que la implementación nunca preceda a la definición.

---

## Relación con proyectos derivados

Los proyectos derivados pueden incorporar agentes operativos propios.

Ejemplos:

* agentes de reporting;
* agentes de forecasting;
* agentes analíticos;
* agentes de automatización;
* asistentes especializados.

Los agentes operativos no forman parte de esta Foundation.

Deben documentarse dentro del repositorio correspondiente.

---

## Principios comunes

Todos los agentes metodológicos deben:

* respetar la metodología SDD;
* respetar la precedencia documental;
* evitar implementación prematura;
* mantener trazabilidad;
* priorizar claridad sobre complejidad;
* favorecer la revisión humana;
* evitar duplicación documental.

---

## Fuera de alcance

Los agentes metodológicos no deben:

* implementar runtime;
* seleccionar tecnologías definitivas;
* crear herramientas reales;
* ejecutar integraciones;
* crear automatizaciones productivas;
* sustituir decisiones humanas.

Estas responsabilidades pertenecen a fases posteriores y a repositorios derivados.
