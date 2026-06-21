# Agents Index

## Propósito

Este directorio contiene agentes metodológicos de `jqf-sdd-foundation`.

Los agentes metodológicos gobiernan el proceso SDD. No son agentes operativos de negocio, no ejecutan procesos productivos y no sustituyen la validación humana.

## Agentes

| ID | Agente | Propósito |
|---|---|---|
| `SDD-AGENT-001` | Specification Agent | Convierte ideas, necesidades o problemas en specifications SDD claras, acotadas y verificables. |
| `SDD-AGENT-002` | Architect Agent | Diseña arquitectura conceptual o técnica a partir de specifications aprobadas. |
| `SDD-AGENT-003` | Tasks Planner Agent | Transforma specifications y arquitectura aprobadas en tareas trazables y secuenciadas. |
| `SDD-AGENT-004` | Reviewer Agent | Revisa artefactos SDD para detectar inconsistencias, ambigüedades, riesgos o implementación prematura. |
| `SDD-AGENT-005` | Documentation Agent | Mantiene documentación clara, coherente, navegable y alineada con los artefactos existentes. |
| `SDD-AGENT-006` | QA Gate Agent | Evalúa gates SDD y determina si una fase puede avanzar según criterios y evidencias. |
| `SDD-AGENT-007` | Implementation Agent | Ejecuta cambios únicamente cuando existen specification, arquitectura, tareas y gates suficientes. |
| `SDD-AGENT-008` | Legacy to SDD Agent | Incorpora proyectos existentes al ciclo SDD mediante discovery mínimo, artefactos As-Is y readiness assessment. |
| `SDD-AGENT-009` | GitHub Workflow Agent | Gestiona trazabilidad entre documentación, issues, ramas, commits y repositorio. |

## Flujo recomendado para proyectos nuevos

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

## Flujo recomendado para proyectos legacy

Legacy to SDD Agent
↓
Legacy to SDD Skill
↓
Discovery Skills según evidencia
↓
Artefactos As-Is
↓
sdd_readiness_assessment.md
↓
Reviewer Agent
↓
Documentation Agent
↓
QA Gate Agent
↓
Specification Agent
↓
Architect Agent
↓
Tasks Planner Agent
↓
Implementation Agent

## Regla de uso

Los agentes deben apoyarse en skills cuando exista un procedimiento reutilizable.

Los agentes definen responsabilidad y límites.

Las skills definen el procedimiento.

Los templates definen el formato de los artefactos.

Documentation Agent es transversal.

Puede ejecutarse en cualquier momento cuando sea necesario:

- actualizar índices;
- normalizar documentación;
- detectar duplicidades;
- corregir referencias;
- aplicar templates;
- mejorar consistencia documental.

Sin embargo, dentro del flujo principal su posición recomendada es posterior al Reviewer Agent y previa al QA Gate Agent.

## Regla de mantenimiento

Cada agente debe tener:

- frontmatter YAML;
- nombre;
- descripción;
- rol;
- objetivo;
- responsabilidades;
- límites;
- forma de trabajo;
- Definition of Done;
- comportamiento esperado.