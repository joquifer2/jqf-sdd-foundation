# Indice de specifications de capacidades

## Proposito

Este archivo indexa specifications y architectures de capacidades.

Es solo un catalogo. No redefine alcance, requisitos, arquitectura, readiness ni autorizacion de fase.

---

## Specifications y architectures

| Capacidad | Artefacto | Tipo | Estado | Funcion |
| --- | --- | --- | --- | --- |
| SDD Modes | `specs/spec-001-sdd-modes.md` | Specification | Final | Contexto de baseline cerrado para SDD Modes. |
| SDD Modes | `specs/spec-001-sdd-modes.architecture.md` | Architecture | Final | Contexto de arquitectura cerrada para SDD Modes. |
| SDD Project Consolidation and Closure | `specs/capabilities/project-consolidation-and-closure/spec-001-sdd-project-consolidation-and-closure.md` | Specification | Closed baseline | Definicion normativa de la capacidad de consolidacion y cierre. |
| SDD Project Consolidation and Closure | `specs/capabilities/project-consolidation-and-closure/arch-001-sdd-project-consolidation-and-closure.md` | Architecture | Closed baseline | Arquitectura documental para expedientes de capacidad, handover, evidencia, deuda, reentrada e interfaz futura de agente. |
| Foundation Derivation and Project Initialization | `specs/capabilities/foundation-derivation-and-project-initialization/spec-001-foundation-derivation-and-project-initialization.md` | Specification | Closed baseline | Define el proceso oficial conceptual para derivar repositorios desde la Foundation e inicializar proyectos SDD limpios. |
| Foundation Derivation and Project Initialization | `specs/capabilities/foundation-derivation-and-project-initialization/arch-001-foundation-derivation-and-project-initialization.md` | Architecture | Closed baseline | Define arquitectura documental conceptual, componentes, interfaces, alternativas y decisiones de derivacion. |
| Consolidation Agent | `specs/capabilities/consolidation-agent/spec-001-consolidation-agent.md` | Specification | Specification | Define el comportamiento metodologico esperado del futuro Consolidation Agent sin implementarlo. |
| Consolidation Agent | `specs/capabilities/consolidation-agent/arch-001-consolidation-agent.md` | Architecture | Architecture gate passed | Define arquitectura documental conceptual del futuro Consolidation Agent sin crearlo. |
| Consolidation Agent | `.github/agents/consolidation.agent.md` | Agent definition | Closed with conditions | Definicion canonica documental del Consolidation Agent trazada a SPEC-001 y ARCH-001. |

---

## Guia de carga

Para trabajo sobre una nueva capacidad, cargar solo el expediente de la capacidad vigente y los artefactos de baseline explicitamente referenciados por su `context_refs.md`.

Los expedientes historicos cerrados deben cargarse solo para auditoria, reentrada o cuando un handover o gate lo requiera explicitamente.