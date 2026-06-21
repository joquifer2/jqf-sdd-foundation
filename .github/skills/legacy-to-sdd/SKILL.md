---
name: legacy-to-sdd
description: Esta skill ayuda a transformar proyectos Brownfield o Legacy en proyectos preparados para trabajar bajo metodología SDD.
id: SDD-SKILL-001
user-invocable: true
disable-model-invocation: false
---

# Legacy to SDD

## Propósito

Incorporar proyectos existentes al ciclo SDD mediante la reconstrucción del conocimiento mínimo necesario para permitir su evolución controlada.

Esta skill ayuda a transformar proyectos Brownfield o Legacy en proyectos preparados para trabajar bajo metodología SDD.

No implementa cambios.

No diseña arquitectura futura.

No crea tareas de desarrollo.

No aprueba el paso a Development.

## Cuándo usar esta skill

Usar cuando:

- existe un proyecto ya desarrollado;
- no se siguió SDD desde el inicio;
- la documentación es incompleta o inexistente;
- se necesita evolucionar el sistema de forma segura;
- se requiere reconstruir conocimiento antes de crear nuevas specifications.

## Objetivo

Determinar qué información debe recuperarse para permitir que el proyecto continúe evolucionando bajo SDD.

## Clasificación inicial

Clasificar el proyecto como:

### Greenfield

Proyecto nuevo.

No requiere esta skill.

### Brownfield

Proyecto parcialmente documentado.

Requiere recuperación parcial de conocimiento.

### Legacy

Proyecto existente con conocimiento insuficiente o no estructurado.

Requiere discovery más amplio.

## Flujo operativo

### Paso 1 - Evaluar estado actual

Identificar:

- documentación existente;
- artefactos SDD existentes;
- arquitectura visible;
- componentes principales;
- dependencias relevantes;
- riesgos conocidos.

### Paso 2 - Seleccionar skills necesarias

Aplicar únicamente las skills relevantes según la evidencia encontrada.

### Skills disponibles

- data-platform-discovery -> identifica plataformas de datos, datasets, tablas, modelos y lineage.
- cloud-runtime-discovery -> identifica runtimes cloud, triggers, entradas, salidas y dependencias operativas.
- integration-discovery -> identifica integraciones externas, APIs, webhooks, contratos y dependencias de intercambio.

No ejecutar skills innecesarias.

## Paso 3 - Reconstruir artefactos As-Is

Generar o actualizar cuando sea necesario:

- system_overview.md
- architecture_as_is.md
- retrospective_spec.md

Generar además cuando aporten valor:

- data_lineage.md
- contracts.md

## Paso 4 - Identificar riesgos

Documentar:

- huecos de conocimiento;
- dependencias críticas;
- riesgos de evolución;
- información no verificable.

Marcar como UNKNOWN cualquier información no demostrable.

## Paso 5 - Evaluar readiness

Generar o actualizar:

- sdd_readiness_assessment.md

Clasificar el proyecto como:

- Ready
- Partially Ready
- Not Ready

## Paso 6 - Recomendar siguiente agente

Según el resultado del readiness assessment, recomendar el siguiente agente del flujo SDD.

Ejemplos:

- Reviewer Agent
- Documentation Agent
- QA Gate Agent
- Specification Agent
- Architect Agent
- Tasks Planner Agent

## Artefactos generados

Obligatorios cuando sean necesarios para comprender el sistema:

- system_overview.md
- architecture_as_is.md
- retrospective_spec.md
- sdd_readiness_assessment.md

Condicionales:

- data_lineage.md
- contracts.md

## Uso de templates

Usar los templates canónicos cuando existan:

- docs/templates/system_overview.template.md
- docs/templates/architecture_as_is.template.md
- docs/templates/retrospective_spec.template.md
- docs/templates/sdd_readiness_assessment.template.md
- docs/templates/data_lineage.template.md
- docs/templates/contracts.template.md

## Output esperado

El resultado final debe permitir responder:

- qué existe actualmente;
- qué artefactos SDD existen;
- qué artefactos SDD faltan;
- qué riesgos condicionan la evolución;
- qué documentación mínima debe completarse;
- si el proyecto está Ready, Partially Ready o Not Ready;
- qué agente debe intervenir después.

## Definition of Done

La skill se considera completada cuando:

- existe una descripción clara del sistema actual;
- existe una arquitectura As-Is suficiente;
- existe una retrospective specification mínima;
- existen riesgos identificados;
- existen huecos documentales identificados;
- existe un sdd_readiness_assessment.md;
- el proyecto ha sido clasificado como Ready, Partially Ready o Not Ready;
- se conoce el siguiente paso dentro del flujo SDD.

## Complementos

Esta skill no tiene complementos propios.

Puede utilizar las siguientes skills auxiliares según la evidencia encontrada:

- data-platform-discovery
- cloud-runtime-discovery
- integration-discovery