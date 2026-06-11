# Copilot instructions - jqf-sdd-foundation

## 1. Proposito del repositorio

Este repositorio proporciona una base reutilizable para proyectos construidos mediante Specification Driven Development (SDD).

Contiene y organiza artefactos destinados a apoyar la metodología y la gobernanza SDD:

- metodología y convenciones SDD;
- gobernanza y reglas documentales;
- agentes metodológicos y roles (descritos como specs y plantillas);
- skills y prompts reutilizables orientados a procesos metodológicos;
- plantillas y artefactos de Project Brief y Specification;
- reglas de precedencia y políticas de evolución.

Regla de simplificación documental:

- la spec es el artefacto principal para capacidades o componentes;
- las restricciones, límites y reglas de gobierno deben definirse preferentemente dentro de cada spec;
- evitar contracts separados salvo que sean transversales a múltiples capacidades o proyectos.

## 2. Relacion con Source of Truth

- Cada proyecto derivado define su propia Source of Truth funcional y operativa.
- La foundation no contiene lógica funcional de negocio ni sustituye documentación operativa del proyecto.
- No duplicar reglas funcionales ni mover documentación operativa desde la Source of Truth del proyecto.
 
Cuando exista conflicto entre documentos, prevalece la Source of Truth definida por el proyecto derivado.

## 3. Metodologia SDD

Este repositorio debe evolucionar por fases SDD (Spec Driven Development):

- Specification: definicion de que es cada capacidad, que debe hacer, sus limites, inputs/outputs, riesgos y criterios de avance.
- Structure: organizacion documental y esqueletos minimos no ejecutables.
- Development: implementacion tecnica, solo tras cierre formal de fases previas.

Estado actual esperado:

- SDD -> Specification / Structure.

No se permite saltar a Development sin completar los criterios de salida definidos en specs.

## 4. Precedencia documental

Orden de precedencia:

Project Brief
↓
SDD Instructions
↓
Specifications
↓
Gates
↓
Skills
↓
Prompts
↓
Documentación auxiliar

Ningún artefacto de menor precedencia puede contradecir a uno de mayor precedencia.

Regla de contracts transversales:

Un contract separado solo es valido si define reglas que aplican a varios agentes, varias skills o al repositorio completo. Ejemplos: políticas transversales, precedencia documental, política de memoria, política de tools, human-in-the-loop y resolución de conflictos entre fuentes.

## 5. Restricciones de arquitectura prematura

Hasta nuevo aviso, esta prohibido:

- elegir framework definitivo;
- definir runtime de agentes;
- crear arquitectura multiagente compleja;
- crear orquestacion automatica;
- crear tools reales conectadas a sistemas;
- crear workflows ejecutables.

No se permiten decisiones tecnologicas irreversibles en fase Specification / Structure.

## 6. Filosofia del sistema

El sistema debe ser:

- operacional;
- razonador;
- contextual;
- trazable;
- human-in-the-loop;
- mantenible;
- explicable;
- modular.

El sistema no debe ser:

- autonomo;
- hiperautomatizado;
- sobreingenierizado;
- artificialmente multiagente.

## 7. Enfoque operativo

Este repositorio construye capacidades de asistencia operativa y control documental.

No sustituye:

- el criterio humano;
- la validacion operativa;
- la toma de decision final de negocio.

## 8. Relación con el SDD Harness

Estas instrucciones forman parte del SDD Harness y deben interpretarse conjuntamente con los artefactos principales:

- Project Brief
- Specifications
- Gates
- Skills
- AGENTS.md

Su función es reforzar la gobernanza documental, evitar implementación prematura y servir como guía para la evolución de artefactos desde Specification a Structure.

## 9. Regla de no implementacion prematura

Mientras no se autorice Development:

- no crear codigo ejecutable de agentes;
- no crear runtime;
- no crear integraciones reales;
- no crear automatizacion operativa.

Primero se cierran specs y estructura base.

## 9.1 Regla anti-sobreingenieria documental

Antes de crear un nuevo tipo de artefacto documental, comprobar si la necesidad se puede resolver con una nueva seccion dentro de una spec existente.

No crear contracts separados salvo que la regla afecte a varios agentes, varias skills o al repositorio completo.

## 10. TASKS GOVERNANCE

El archivo `docs/tasks.md` actua como backlog documental y tecnico del repositorio.

Su funcion es mantener trazabilidad de trabajo pendiente relevante dentro del ecosistema SDD.

Antes de cerrar cualquier trabajo significativo, evaluar si dicho cambio afecta al backlog.

Actualizar `docs/tasks.md` unicamente cuando ocurra alguna de las siguientes situaciones:

- se crea un nuevo artefacto relevante;
- se identifica una nueva linea de trabajo futura;
- se detecta una dependencia importante;
- se alcanza un readiness gate;
- se completa una tarea registrada;
- una tarea deja de ser necesaria;
- aparece una nueva necesidad de Specification, Structure o Development futuro.

No registrar:

- commits;
- cambios de formato;
- correcciones menores;
- tareas personales;
- actividad diaria;
- microacciones.

El backlog debe reflejar trabajo significativo del repositorio, no actividad operativa cotidiana.

## 11. Comprobacion de cierre para cambios significativos

Antes de considerar completado un cambio significativo:

1. Revisar si afecta a Specs.
2. Revisar si afecta a Contracts transversales.
3. Revisar si afecta a Skills.
4. Revisar si afecta a Prompts.
5. Revisar si afecta a Gates.
6. Revisar si requiere actualizacion de `docs/tasks.md`.

Si la respuesta es si, actualizar el artefacto correspondiente.
