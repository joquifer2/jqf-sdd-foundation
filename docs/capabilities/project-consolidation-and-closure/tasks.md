# Plan de tareas - SDD Project Consolidation and Closure

## Metadatos

| Campo | Valor |
| --- | --- |
| Plan ID | TASKPLAN-001 |
| Capacidad | SDD Project Consolidation and Closure |
| Brief de proyecto relacionado | `docs/capabilities/project-consolidation-and-closure/project_brief.md` |
| Referencias de contexto relacionado | `docs/capabilities/project-consolidation-and-closure/context_refs.md` |
| Specification relacionada | `specs/capabilities/project-consolidation-and-closure/spec-001-sdd-project-consolidation-and-closure.md` |
| Estado | Closed |
| Fase SDD actual | Closed |
| Responsable | Jordi Quiroga |
| Creado por | Specification Agent |
| Ultima actualizacion | 2026-08-01 |

---

## 1. Objetivo

Registrar el backlog inicial necesario para revisar, validar y preparar la evolucion controlada de la capacidad `SDD Project Consolidation and Closure`.

Este plan registra la autorizacion humana de Architecture para ARCH-001. No autoriza Development, scripts, workflows, tools ni reorganizacion fisica del repositorio.

---

## 2. Artefactos fuente

| Artefacto | Rol en el plan |
| --- | --- |
| `docs/capabilities/project-consolidation-and-closure/project_brief.md` | Define problema, alcance, modo y criterios de exito. |
| `docs/capabilities/project-consolidation-and-closure/context_refs.md` | Indexa fuentes y baseline previo. |
| `specs/capabilities/project-consolidation-and-closure/spec-001-sdd-project-consolidation-and-closure.md` | Define requisitos y reglas conceptuales. |
| `specs/capabilities/project-consolidation-and-closure/arch-001-sdd-project-consolidation-and-closure.md` | Define estructura documental objetivo, componentes, interfaces y decisiones arquitectonicas. |
| `docs/capabilities/project-consolidation-and-closure/sdd_readiness_assessment.md` | Evalua readiness inicial. |
| Baseline final de `SDD Modes` | Contexto normativo previo que no debe modificarse. |

---

## 3. Reglas de planificacion

- Toda tarea debe permanecer en la fase SDD autorizada: Specification para T-001 a T-007, Architecture para T-008 a T-012, Planning/Documentacion/Gobernanza/Revision/Validacion/Consolidation prep documental para T-013 a T-028, y Closure documental para T-029. Ninguna tarea autoriza Development.
- Las tareas no deben modificar documentos cerrados de `SDD Modes`.
- Las tareas no deben crear implementacion ni automatizacion.
- Las decisiones estructurales propuestas por Architecture deben permanecer documentales hasta revision, QA y autorizacion posterior de cualquier reorganizacion fisica.
- Cualquier deuda residual debe conservar estado, impacto y punto de reentrada.

---

## 4. Bloques de trabajo

1. Creacion de artefactos iniciales.
2. Revision de specification.
3. Validacion inicial de readiness.
4. Architecture documental autorizada, sin reorganizacion fisica ni Development.
5. Planificacion post-Architecture de actualizaciones documentales y gates conceptuales.
6. Preparacion documental de Consolidation, sin cierre final ni Development.

---

## 5. Tareas

| ID | Tarea | Tipo | Agente responsable | Dependencias | Criterios de aceptacion | Estado |
| --- | --- | --- | --- | --- | --- | --- |
| T-001 | Crear Brief de proyecto de la capacidad en estructura provisional aislada. | Specification | Specification Agent | Request inicial | Brief de proyecto existe, declara SDD Full y no modifica baseline SDD Modes. | Completed |
| T-002 | Crear Referencias de contexto de la capacidad. | Specification / Documentacion | Specification Agent | T-001 | Context refs indexa fuentes y baseline cerrado sin duplicar contenido completo. | Completed |
| T-003 | Crear `SPEC-001 - SDD Project Consolidation and Closure`. | Specification | Specification Agent | T-001; T-002 | La spec cubre objetivo, alcance, ciclo de vida, clasificacion documental y Consolidation Agent conceptual. | Completed |
| T-004 | Crear readiness assessment inicial. | Specification / Validacion prep | Specification Agent | T-003 | Readiness inicial existe y declara que Architecture/Development no estan autorizados. | Completed |
| T-005 | Crear backlog inicial de tareas. | Planning | Specification Agent | T-001 a T-004 | Backlog inicial existe con tareas trazables y sin autorizacion de Development. | Completed |
| T-006 | Revisar coherencia de los artefactos iniciales contra el baseline cerrado de SDD Modes. | Revision | Reviewer Agent | T-001 a T-005 | Decision `Approved with minor changes`; hallazgos menores corregidos antes de QA. | Completed |
| T-007 | Validar readiness inicial para cerrar fase Specification o preparar Architecture. | Validacion | QA Gate Agent | T-006 | Decision `Pass with minor conditions`; Specification lista para decision humana sobre Architecture. | Completed |
| T-008 | Decidir si se autoriza Architecture de la capacidad. | Gobernanza | Jordi Quiroga / QA Gate Agent | T-007 | Decision humana explicita registrada por solicitud `[@Architect Agent] Adelante`; Development sigue no autorizado. | Completed |
| T-009 | Si se autoriza Architecture, definir estructura definitiva de expedientes metodologicos. | Architecture | Architect Agent | T-008 | `ARCH-001` propone estructura documental objetivo sin mover archivos. | Completed |
| T-010 | Definir template o forma canonica del handover formal de cierre. | Architecture / Documentacion | Architect Agent / Documentation Agent | T-008 | `ARCH-001` define estructura minima de `Handover de cierre`; template queda para Documentacion posterior. | Completed |
| T-011 | Revisar `ARCH-001` contra SPEC-001 y restricciones de fase. | Revision | Reviewer Agent | T-009; T-010 | Decision `Changes requested`; hallazgos menores del backlog corregidos antes de QA. Sin bloqueos restantes. | Completed |
| T-012 | Validar readiness de Architecture para planificacion posterior. | Validacion | QA Gate Agent | T-011 | Decision `Pass with minor conditions`; Architecture lista para Tasks Planner Agent sin autorizar Development. | Completed |
| T-013 | Determinar alcance documental posterior a Architecture y confirmar que no incluye Development ni reorganizacion fisica. | Planning / Gobernanza | Tasks Planner Agent | T-012; `ARCH-001` | Alcance post-Architecture definido como documentacion/gobernanza; cualquier cambio global queda sujeto a review/QA. | Completed |
| T-014 | Decidir si se crean indices globales de capacidades (`docs/capabilities/index.md` y `specs/capabilities/index.md`) como catalogos/routing, no como fuentes normativas. | Gobernanza / Documentacion | Documentation Agent | T-013; `ARCH-001` AD-005 | Decision documentada: se crean como catalogos/routing y no como fuentes normativas. | Completed |
| T-015 | Preparar o actualizar indice global de capacidades en `docs/capabilities/index.md`, si T-014 lo autoriza. | Documentacion | Documentation Agent | T-014 | Indice creado; lista capacidades, estados, artefactos principales y siguiente paso valido sin duplicar contenido canonico. | Completed |
| T-016 | Preparar o actualizar indice global de specs/architectures en `specs/capabilities/index.md`, si T-014 lo autoriza. | Documentacion | Documentation Agent | T-014 | Indice creado; lista specs/architectures por capacidad y estado sin redefinir contenido de SPEC/ARCH. | Completed |
| T-017 | Actualizar README con explicacion de alto nivel sobre ciclo de vida de capacidades y expedientes por capacidad. | Documentacion | Documentation Agent | T-013; `ARCH-001` Impacto en la arquitectura existente | README actualizado a nivel alto; no se convierte en fuente normativa completa. | Completed |
| T-018 | Actualizar `.github/instructions/sdd.instructions.md` para incorporar `Consolidation` y `Closed` como fases/estados documentales, si la revision lo aprueba. | Documentacion / Gobernanza | Documentation Agent | T-013; T-017 si afecta narrativa | Instrucciones actualizadas; reflejan lifecycle sin autorizar Development ni cambiar SDD Modes. | Completed |
| T-019 | Actualizar `docs/glosario_terminos.md` con terminos consolidados definidos en SPEC-001. | Documentacion | Documentation Agent | T-013; SPEC-001 Section 8 | Glosario actualizado con definiciones alineadas: baseline canonico, expediente cerrado, evidencia historica, artefacto sustituido, deuda residual, punto de reentrada, handover, producto operativo. | Completed |
| T-020 | Evaluar si `closure_handover`, `evidence_index` y `residual_debt` requieren templates separados o secciones dentro de artefactos existentes. | Documentacion / Architecture | Documentation Agent | T-013; `ARCH-001` Section 7 | Decision documentada: se crean templates separados por tener responsabilidades distintas; las instancias pueden omitirse si no aplican. | Completed |
| T-021 | Crear o adaptar templates documentales autorizados por T-020. | Documentacion | Documentation Agent | T-020 | Templates creados para handover, evidence index y residual debt; no se crean instancias reales de cierre. | Completed |
| T-022 | Definir documentacion conceptual de `Consolidation Readiness Gate` y `Closure Gate` sin crear automatizaciones. | Documentacion / Validacion | QA Gate Agent / Documentation Agent | T-013; `ARCH-001` Gate Interface | Gates documentales definidos con criterios, inputs, outputs y limites; no workflows ejecutables. | Completed |
| T-023 | Revisar si `AGENTS.md` debe mencionar `Consolidation Agent` como futuro agente metodologico sin crear definicion canonica ni adaptador. | Documentacion / Gobernanza | Documentation Agent | T-013; `ARCH-001` AD-006 | Decision documentada: no se actualiza `AGENTS.md` para evitar presentar como vigente un agente no creado. | Completed |
| T-024 | Decidir si hace falta abrir una futura capacidad separada para crear el `Consolidation Agent` canonico. | Gobernanza / Specification | Jordi Quiroga / Specification Agent | T-023; `ARCH-001` Consolidation Agent Interface | Decision registrada: crear el agente canonico requerira futura capacidad separada y aprobacion humana; no se crea agente real aqui. | Completed |
| T-025 | Revisar transversalmente las actualizaciones documentales post-Architecture. | Revision | Reviewer Agent | T-015 a T-024 segun se ejecuten | Decision `Approved`; se corrigieron hallazgos menores en README y no quedan contradicciones activas. | Completed |
| T-026 | Evaluar QA Gate de documentacion post-Architecture y readiness para Consolidation de esta capacidad. | Validacion | QA Gate Agent | T-025 | Decision `Pass with minor conditions`; la capacidad puede preparar Consolidation documental. Development sigue no autorizado. | Completed |
| T-027 | Preparar paquete documental de Consolidation (`closure_handover.md`, `evidence_index.md`, `residual_debt.md`). | Documentacion / Consolidation prep | Documentation Agent | T-026 | Paquete creado; estado sigue `Consolidation preparation`; cierre final requiere Reviewer, Closure Gate y aprobacion humana. | Completed |
| T-028 | Revisar paquete documental de Consolidation (`closure_handover.md`, `evidence_index.md`, `residual_debt.md`). | Revision | Reviewer Agent | T-027 | Decision `Approved with minor corrections`; el paquete queda listo para posible Closure Gate si existe decision humana explicita de cierre. | Completed |
| T-029 | Ejecutar `Closure Gate` con aprobacion humana explicita y registrar cierre documental de la capacidad. | Validacion / Closure | QA Gate Agent / Jordi Quiroga | T-028 | Decision `Pass with conditions`; capacidad marcada como `Closed`; deuda residual visible y reentradas conservadas; Development permanece no autorizado. | Completed |

---

## 6. Decisiones abiertas representadas

| Decision | Impacto | Representada por |
| --- | --- | --- |
| Estructura definitiva de expedientes metodologicos | Bloquea reorganizacion futura | T-009 |
| Artefacto formal de handover | Bloquea aplicacion repetible de cierre | T-010 |
| Aprobadores de Consolidation y Closed | Bloquea lifecycle operativo futuro | T-007 / T-008 |
| Incorporacion canonica del Consolidation Agent | Bloquea creacion de agente real | Futuro backlog posterior a Architecture |


---

## 8. Orden recomendado post-Architecture

```text
T-013
  ↓
T-014
  ↓
T-015 + T-016
  ↓
T-017 → T-018 → T-019
  ↓
T-020 → T-021
  ↓
T-022 → T-023 → T-024
  ↓
T-025
  ↓
T-026
```

Paralelizacion segura:

- T-015 y T-016 pueden ejecutarse en paralelo despues de T-014.
- T-017, T-018 y T-019 pueden prepararse en paralelo, pero deben reconciliar terminologia antes de T-025.
- T-022 y T-023 pueden avanzar en paralelo si no introducen el `Consolidation Agent` real.

---

## 9. Dependencias criticas post-Architecture

| Dependencia | Impacto | Tareas afectadas |
| --- | --- | --- |
| Decision sobre indices globales | Bloquea creacion de `docs/capabilities/index.md` y `specs/capabilities/index.md` | T-014 a T-016 |
| Decision sobre templates separados vs secciones | Bloquea creacion/adaptacion de templates | T-020 a T-021 |
| Mantener `Consolidation Agent` como futuro conceptual | Bloquea cualquier creacion de agente real o adaptador | T-023 a T-024 |
| No tocar baseline cerrado de SDD Modes | Bloquea propagaciones sobre artefactos raiz cerrados | Todas |
| Development no autorizado | Bloquea cualquier tarea tecnica, script, workflow ejecutable o runtime | Todas |

---

## 10. Riesgos de planificacion post-Architecture

| Riesgo | Impacto | Mitigacion |
| --- | --- | --- |
| Convertir indices propuestos en fuentes normativas | Medio | Definir indices como catalogos/routing y referenciar SPEC/ARCH como fuentes canonicas. |
| Crear demasiados templates | Medio | T-020 exige decision previa y funcion diferenciada. |
| Crear el `Consolidation Agent` antes de tiempo | Alto | T-023/T-024 solo permiten decision futura, no agente real. |
| Reorganizar fisicamente el baseline de SDD Modes | Alto | Todas las tareas deben evitar mover/modificar artefactos cerrados salvo decision humana explicita. |
| Confundir planificacion documental con Development | Alto | Tareas clasificadas como Documentacion/Gobernanza/Validacion/Revision; Development permanece no autorizado. |

---

## 11. Siguiente paso recomendado actualizado

```text
No hay siguiente paso activo; la capacidad esta Closed. El trabajo futuro requiere una nueva capacidad SDD o una decision explicita de reentrada. Development permanece NOT AUTHORIZED.
```

Antes de cualquier propagacion global, mantener trazabilidad con `SPEC-001`, `ARCH-001` y QA Gate T-012.

Development permanece `NOT AUTHORIZED`.

## 12. Documentacion Execution Summary

Documentation Agent completo T-014 a T-024 el 2026-08-01.

Cambios realizados:

- indices globales creados como catalogos/routing, no fuentes normativas;
- README, instrucciones SDD y glosario actualizados;
- templates separados creados para handover, evidence index y residual debt;
- gates conceptuales creados para Consolidation Readiness y Closure;
- AGENTS.md, .github/agents/ y .codex/agents/ no se modifican porque Consolidation Agent no existe aun;
- futura creacion del Consolidation Agent requiere capacidad separada y aprobacion humana.

Siguiente paso:

```text
No hay siguiente paso activo; la capacidad esta Closed. El trabajo futuro requiere una nueva capacidad SDD o una decision explicita de reentrada. Development permanece NOT AUTHORIZED.
```

Development permanece `NOT AUTHORIZED`.

## 13. Reviewer Decision - T-025

Decision: `Approved`.

Fecha: 2026-08-01.

Reviewer Agent reviso las actualizaciones documentales T-014 a T-024 y aplico correcciones menores en `README.md` antes de cerrar la revision.

Resultado:

- indices globales aceptados como catalogos/routing, no fuentes normativas;
- templates aceptados como estructuras reutilizables, no instancias reales de cierre;
- gates aceptados como artefactos conceptuales/documentales, no workflows ejecutables;
- `Consolidation Agent` permanece futuro conceptual y no se crea agente real ni adaptador Codex;
- Development permanece `NOT AUTHORIZED`.

Siguiente paso:

```text
No hay siguiente paso activo; la capacidad esta Closed. El trabajo futuro requiere una nueva capacidad SDD o una decision explicita de reentrada. Development permanece NOT AUTHORIZED.
```

## 14. QA Gate Decision - T-026

Decision: `Pass with minor conditions`.

Fecha: 2026-08-01.

QA Gate Agent valido las actualizaciones documentales post-Architecture y la revision T-025.

Criterios cumplidos:

- T-014 a T-025 estan completadas y trazadas;
- los indices globales existen como catalogos/routing, no fuentes normativas;
- los templates de cierre existen como estructuras reutilizables, no instancias reales;
- `Consolidation Readiness Gate` y `Closure Gate` existen como artefactos documentales/conceptuales;
- `README.md`, `.github/instructions/sdd.instructions.md` y `docs/glosario_terminos.md` reflejan Consolidation y Closed sin autorizar implementacion;
- `Consolidation Agent` permanece conceptual y no se crea agente real ni adaptador Codex;
- Development permanece `NOT AUTHORIZED`.

Condiciones menores:

- la entrada efectiva a Consolidation debe preparar artefactos de cierre como paquete documental, no como reorganizacion fisica;
- cualquier cierre final requerira `Closure Gate` y aprobacion humana explicita;
- la creacion canonica del `Consolidation Agent` requiere una capacidad separada posterior.

Siguiente paso autorizado:

```text
No hay siguiente paso activo; la capacidad esta Closed. El trabajo futuro requiere una nueva capacidad SDD o una decision explicita de reentrada. Development permanece NOT AUTHORIZED.
```

## 15. Documentation Agent Consolidation Package - T-027

Estado: `Completed`.

Fecha: 2026-08-01.

Artefactos preparados:

- `docs/capabilities/project-consolidation-and-closure/closure_handover.md`;
- `docs/capabilities/project-consolidation-and-closure/evidence_index.md`;
- `docs/capabilities/project-consolidation-and-closure/residual_debt.md`.

Limites:

- la capacidad queda en `Consolidation preparation`, no `Closed`;
- no se crea `Consolidation Agent` real ni adaptador Codex;
- no se mueve ni reorganiza el baseline cerrado de `SDD Modes`;
- Development permanece `NOT AUTHORIZED`.

Siguiente paso:

```text
No hay siguiente paso activo; la capacidad esta Closed. El trabajo futuro requiere una nueva capacidad SDD o una decision explicita de reentrada. Development permanece NOT AUTHORIZED.
```

## 16. Reviewer Decision - T-028

Decision: `Approved with minor corrections`.

Fecha: 2026-08-01.

Reviewer Agent reviso el paquete documental de Consolidation y aplico dos correcciones menores:

- el orden recomendado incluye ahora T-027 y T-028;
- `closure_handover.md` aclara que los artefactos de Consolidation ya fueron preparados y que falta review/Closure Gate para cierre final.

Resultado:

- `closure_handover.md`, `evidence_index.md` y `residual_debt.md` son coherentes entre si;
- el paquete no marca la capacidad como `Closed`;
- el cierre final fue completado posteriormente por Closure Gate T-029 con aprobacion humana explicita;
- no se crea `Consolidation Agent` real ni adaptador Codex;
- Development permanece `NOT AUTHORIZED`.

Siguiente paso:

```text
No hay siguiente paso activo; la capacidad esta Closed. El trabajo futuro requiere una nueva capacidad SDD o una decision explicita de reentrada. Development permanece NOT AUTHORIZED.
```

## 17. QA Gate Decision - T-029

Decision: `Pass with conditions`.

Fecha: 2026-08-01.

Evaluador: QA Gate Agent.

Gate evaluado:

`Closure Gate` for `SDD Project Consolidation and Closure`.

Fase actual:

`Consolidation`.

Fase destino:

`Closed`.

Autorizacion humana:

Jordi Quiroga autorizo explicitamente ejecutar el cierre mediante solicitud `[@QA Gate Agent] Adelante lo autorizo`.

Artefactos revisados:

- `docs/capabilities/project-consolidation-and-closure/closure_handover.md`;
- `docs/capabilities/project-consolidation-and-closure/evidence_index.md`;
- `docs/capabilities/project-consolidation-and-closure/residual_debt.md`;
- `docs/capabilities/project-consolidation-and-closure/tasks.md`;
- `docs/capabilities/project-consolidation-and-closure/sdd_readiness_assessment.md`;
- `gates/closure_gate.md`.

Criterios cumplidos:

- El handover de cierre existe y esta completo;
- baseline canonico y expediente historico estan identificados;
- evidencia historica esta indexada;
- deuda residual visible incluye owner, impacto, estado y puntos de reentrada;
- no se elimina ni oculta evidencia;
- Reviewer T-028 aprobo el paquete de Consolidation;
- existe aprobacion humana explicita para cierre;
- no se ha creado Development, runtime, scripts, workflows ejecutables, agente real ni adaptador Codex.

Criterios no cumplidos:

- Ninguno bloqueante.

Condiciones de cierre:

1. `Consolidation Agent` permanece como deuda futura no bloqueante y requiere capacidad SDD separada.
2. No se autoriza reorganizacion fisica ni movimiento del baseline cerrado.
3. El baseline cerrado debe cargarse mediante handover e indices antes de cualquier reentrada futura.
4. Development permanece `NOT AUTHORIZED`.

Resultado:

La capacidad queda marcada como `Closed` con deuda residual aceptada y puntos de reentrada documentados.

Siguiente paso:

```text
No hay siguiente paso activo; la capacidad esta Closed. El trabajo futuro requiere una nueva capacidad SDD o una decision explicita de reentrada. Development permanece NOT AUTHORIZED.
```