# Plan de tareas - Repository Physical Normalization

## Metadatos

| Campo | Valor |
| --- | --- |
| Plan ID | TASKPLAN-001 |
| Capacidad | Repository Physical Normalization |
| Brief de proyecto relacionado | `docs/capabilities/repository-physical-normalization/project_brief.md` |
| Referencias de contexto relacionado | `docs/capabilities/repository-physical-normalization/context_refs.md` |
| Specification relacionada | `specs/capabilities/repository-physical-normalization/spec-001-repository-physical-normalization.md` |
| Estado | Closed with minor conditions |
| Fase SDD actual | Closed |
| Responsable | Jordi Quiroga |
| Creado por | Specification Agent |
| Ultima actualizacion | 2026-08-02 |

---

## 1. Objetivo

Registrar el backlog inicial necesario para revisar, validar y preparar la evolucion controlada de la capacidad `Repository Physical Normalization`.

Este plan registra que Architecture documental fue autorizada por T-008 y que Governed Execution Preparation fue autorizada por T-013. No autoriza Development, scripts, workflows, tools, automatizaciones, movimientos fisicos, renombres, copias, sustituciones, eliminaciones ni modificacion de baselines cerrados.

---

## 2. Artefactos fuente

| Artefacto | Rol en el plan |
| --- | --- |
| `docs/capabilities/repository-physical-normalization/project_brief.md` | Define problema, alcance, modo y restricciones. |
| `docs/capabilities/repository-physical-normalization/context_refs.md` | Indexa fuentes y baseline cerrado relacionado. |
| `specs/capabilities/repository-physical-normalization/spec-001-repository-physical-normalization.md` | Define proceso, reglas, estructura objetivo y limites. |
| `docs/capabilities/repository-physical-normalization/sdd_readiness_assessment.md` | Evalua readiness inicial de Specification. |
| `docs/capabilities/consolidation-agent/validations/sdd-modes-retrospective/consolidation_report.md` | Propuesta no ejecutable de aplicacion sobre `SDD Modes`. |
| `docs/capabilities/project-consolidation-and-closure/closure_handover.md` | Handover de baseline cerrado de consolidacion/cierre. |
| `docs/capabilities/consolidation-agent/closure_handover.md` | Handover que fija frontera con `Consolidation Agent`. |
| `docs/capabilities/repository-physical-normalization/governed-execution-preparation/README.md` | Paquete documental de preparacion de ejecucion gobernada, no ejecutable. |

---

## 3. Reglas de planificacion

- Toda tarea debe permanecer en la fase SDD autorizada.
- Architecture documental solo queda autorizada por T-008; Governed Execution Preparation queda autorizada por T-013 como paquete documental no ejecutable.
- Ninguna tarea autoriza Development.
- Las tareas no deben modificar documentos cerrados de capacidades previas.
- Las tareas no deben crear implementacion ni automatizacion.
- Las tareas no deben mover, copiar, renombrar, eliminar ni reorganizar archivos.
- Cualquier decision fisica, ejecutable u operativa debe quedar como pendiente de fase futura autorizada.

---

## 4. Bloques de trabajo

1. Creacion de artefactos iniciales.
2. Revision de Specification.
3. Validacion inicial de readiness.
4. Decision humana sobre Architecture.
5. Architecture documental futura, si se autoriza.
6. Governed Execution Preparation documental, autorizada por T-013 sin Development.
7. Planificacion/ejecucion futura, solo si gates y decisiones posteriores lo autorizan.

---

## 5. Tareas

| ID | Tarea | Tipo | Agente responsable | Dependencias | Criterios de aceptacion | Estado |
| --- | --- | --- | --- | --- | --- | --- |
| T-001 | Crear Brief de proyecto de la capacidad en estructura aislada. | Specification | Specification Agent | Request inicial | Brief existe, declara `SDD Full` y no modifica baselines cerrados. | Completed |
| T-002 | Crear Referencias de contexto de la capacidad. | Specification / Documentation | Specification Agent | T-001 | Context refs indexa fuentes, baseline cerrado, paquete retrospectivo y restricciones. | Completed |
| T-003 | Crear `SPEC-001 - Repository Physical Normalization`. | Specification | Specification Agent | T-001; T-002 | La spec cubre objetivos, reglas, estructura objetivo, compatibilidad, reversibilidad, SDD Modes y frontera con Consolidation Agent. | Completed |
| T-004 | Crear readiness assessment inicial. | Specification / Validation prep | Specification Agent | T-003 | Readiness inicial existe y declara que Architecture/Development/movimientos no estan autorizados. | Completed |
| T-005 | Crear backlog inicial de tareas. | Planning | Specification Agent | T-001 a T-004 | Backlog inicial existe con tareas trazables y sin autorizacion de Architecture/Development. | Completed |
| T-006 | Revisar coherencia de artefactos iniciales contra baseline cerrado y restricciones. | Review | Reviewer Agent | T-001 a T-005 | Decision `Approved with minor changes` registrada; no hay hallazgos criticos ni importantes; no se autoriza Development. | Completed |
| T-007 | Validar readiness inicial para posible decision de Architecture. | Validation | QA Gate Agent | T-006 | Decision `Pass with minor conditions` registrada; Architecture requiere aprobacion humana explicita; Development permanece no autorizado. | Completed |
| T-008 | Decidir si se autoriza Architecture documental de la capacidad. | Governance | Jordi Quiroga | T-007 | Decision humana explicita `Autorizacion de la Architecture documental` registrada. | Completed |
| T-009 | Crear `ARCH-001 - Repository Physical Normalization`, si se autoriza. | Architecture | Architect Agent | T-008 | Architecture conceptual existe sin ejecutar movimientos ni crear scripts. | Completed |
| T-010 | Definir reference map, movement plan y rollback plan como componentes documentales, si Architecture lo autoriza. | Architecture | Architect Agent | T-009 | Planes definidos en ARCH-001 como futuros no ejecutables. | Completed |
| T-011 | Revisar Architecture y plan documental, si existen. | Review | Reviewer Agent | T-009; T-010 | Decision `Approved with minor changes` registrada; compatibilidad, reversibilidad y ausencia de ejecucion confirmadas. | Completed |
| T-012 | Validar readiness de Architecture. | Validation | QA Gate Agent | T-011 | Decision `Pass with minor conditions` registrada; no autoriza Development ni ejecucion fisica. | Completed |
| T-013 | Autorizar Governed Execution Preparation. | Governance | Jordi Quiroga | T-012 | Decision humana explicita autoriza preparar paquete documental definitivo para evaluar Development futuro. | Completed |
| T-014 | Crear Canonical Route Registry. | Documentation | Documentation Agent | T-013 | Registro canonico de rutas actuales, rutas objetivo, clasificacion, precedencia y estado no ejecutado existe. | Completed |
| T-015 | Crear Reference Map. | Documentation | Documentation Agent | T-013; T-014 | Mapa inicial de referencias conocidas y superficies de compatibilidad existe, con validacion final pendiente antes de Development. | Completed |
| T-016 | Crear Movement Plan. | Documentation | Documentation Agent | T-013; T-014; T-015 | Secuencia futura por olas existe y declara que no se ejecuta. | Completed |
| T-017 | Crear Compatibility Plan. | Documentation | Documentation Agent | T-013; T-015 | Estrategia de enlaces, referencias, handovers, context_refs y proyectos derivados existe sin cambios fisicos. | Completed |
| T-018 | Crear Rollback Plan. | Documentation | Documentation Agent | T-013; T-016 | Triggers y reversibilidad futura por olas quedan definidos. | Completed |
| T-019 | Crear Validation Checklist. | Documentation / QA prep | Documentation Agent | T-013 a T-018 | Checklist previo a Development y futuro post-ejecucion existe. | Completed |
| T-020 | Crear SDD Modes Pilot Package. | Documentation | Documentation Agent | T-013 a T-019 | Paquete piloto sobre SDD Modes existe, reutilizable y no ejecutado. | Completed |
| T-021 | Revisar paquete de Governed Execution Preparation. | Review | Reviewer Agent | T-014 a T-020 | Decision `Approved with minor changes` registrada; no hay hallazgos criticos ni importantes; requiere correcciones menores de trazabilidad historica antes de QA. | Completed |
| T-022 | Validar readiness del paquete para posible autorizacion de Development. | Validation | QA Gate Agent | T-021 | Decision `Pass with minor conditions` registrada; procede decision humana posterior si se desea autorizar Development. QA no autoriza Development por si solo. | Completed |
| T-023 | Decidir si se autoriza Development. | Governance | Jordi Quiroga | T-022 | Decision humana explicita `Autorizo el desarrollo` registrada. | Completed |
| T-024 | Ejecutar primera ola controlada sobre SDD Modes. | Development | Implementation / Documentation | T-023 | Cinco artefactos se mueven a rutas canonicas y rutas legacy quedan como stubs; Architecture legacy se mantiene. | Completed |
| T-025 | Actualizar indices y artefactos activos de Repository Physical Normalization. | Documentation | Documentation Agent | T-024 | Indices y expediente RPN reflejan ejecucion Development; no se reescriben capacidades cerradas no activas. | Completed |
| T-026 | Validar ejecucion local y preparar review post-Development. | Validation prep | Implementation / Documentation | T-024; T-025 | Verificaciones de rutas, stubs, diff y ausencia de automatizacion registradas. | Completed |
| T-027 | Revisar ejecucion Development. | Review | Reviewer Agent | T-026 | Reviewer valida movimiento fisico, compatibilidad y ausencia de cambio normativo. | Completed |
| T-028 | Validar QA post-Development. | Validation | QA Gate Agent | T-027 | QA valida cierre o condiciones de la primera ola ejecutada. | Completed |
| T-029 | Evaluar referencias de `specs/spec-001-sdd-modes.architecture.md`. | Architecture | Architect Agent | T-028 | Reference Map identifica referencias activas, historicas y tratamiento propuesto. | Completed |
| T-030 | Proponer decision final de ruta para Architecture SDD Modes. | Architecture | Architect Agent | T-029 | Decision documentada entre opcion A y B; recomendacion justificada. | Completed |
| T-031 | Actualizar Movement, Compatibility y Rollback Plans para DEV-RPN-010. | Planning / Documentation | Architect Agent / Documentation Agent | T-030 | Planes definen movimiento futuro, stub, compatibilidad, rollback y precondiciones. | Completed |
| T-032 | Actualizar Task Plan para la ola futura DEV-RPN-010. | Planning | Tasks Planner Agent | T-031 | Backlog registra Reviewer, QA, autorizacion humana y ejecucion futura como tareas separadas. | Completed |
| T-033 | Revisar paquete de decision Architecture route. | Review | Reviewer Agent | T-029 a T-032 | Reviewer valida Reference Map, decision, planes y ausencia de ejecucion. | Completed |
| T-034 | Validar QA Gate del paquete DEV-RPN-010. | Validation | QA Gate Agent | T-033 | Decision `Pass with minor conditions` registrada; procede decision humana posterior si se desea autorizar DEV-RPN-010. | Completed |
| T-035 | Decidir si se autoriza ejecucion DEV-RPN-010. | Governance | Jordi Quiroga | T-034 | Decision humana explicita `Autorizo` registrada. | Completed |
| T-036 | Ejecutar DEV-RPN-010, solo si se autoriza. | Development | Implementation / Documentation | T-035 | Architecture movida a ruta objetivo, stub creado, referencias activas actualizadas y rollback listo. | Completed |
| T-037 | Revisar ejecucion DEV-RPN-010. | Review | Reviewer Agent | T-036 | Decision `Approved with minor changes` registrada; ejecucion, stub, referencias activas y ausencia de cambio normativo validadas. | Completed |
| T-038 | Validar QA post-ejecucion DEV-RPN-010. | Validation | QA Gate Agent | T-037 | Decision `Pass with minor conditions` registrada; procede decision humana de cierre o trabajo adicional. | Completed |
| T-039 | Cerrar DEV-RPN-010 por decision humana. | Governance | Jordi Quiroga | T-038 | Decision humana explicita `Autorizo el cierre` registrada; no queda siguiente paso activo para DEV-RPN-010. | Completed |
| T-040 | Validar Closure Gate global de Repository Physical Normalization. | Validation | QA Gate Agent | T-039 | QA valida readiness global de cierre de la capacidad. | Completed |
| T-041 | Cerrar globalmente Repository Physical Normalization por decision humana. | Governance | Jordi Quiroga | T-040 | Decision humana explicita de cierre global registrada. | Completed |

---

## 6. Decisiones abiertas representadas

| Decision | Impacto | Representada por |
| --- | --- | --- |
| Crear o no carpetas `baseline/` | Afecta estructura fisica objetivo | SPEC open questions |
| Estrategia de compatibilidad legacy | Bloquea movimientos seguros | SPEC CP/RV sections |
| Naming final de SDD Modes Architecture | Afecta coste de referencias | SPEC Section 16 |
| Formato de movement/reference/rollback plan | Bloquea Architecture ejecutiva | SPEC future considerations |
| Gate exacto para ejecucion fisica | Bloquea Development/Documentation ejecutiva | Readiness / tasks futuras |
| Agente ejecutor autorizado | Bloquea movimientos | Open questions |

---

## 7. Orden recomendado

```text
T-001
  ↓
T-002
  ↓
T-003
  ↓
T-004
  ↓
T-005
  ↓
T-006
  ↓
T-007
  ↓
T-008
```

T-009 a T-012 solo aplican si T-008 autoriza Architecture. T-013 a T-020 aplican al paquete documental de Governed Execution Preparation. T-021 a T-022 cierran review/QA previos a Development. T-023 autoriza Development y T-024 a T-028 gobiernan la primera ola ejecutada y su validacion post-Development.

---

## 8. Dependencias criticas

| Dependencia | Impacto | Tareas afectadas |
| --- | --- | --- |
| No modificar baselines cerrados | Impide tocar SDD Modes y capacidades cerradas. | Todas |
| No ejecutar normalizacion fisica | Impide movimientos, renombres, copias, sustituciones y eliminaciones. | Todas |
| Architecture documental completada | Bloquea cualquier ejecucion hasta Review, QA y nueva autorizacion futura. | T-011 a T-012 |
| Reference map futuro | Bloquea ejecucion segura. | T-010 a T-012 |
| Reviewer antes de QA | QA depende de revision previa. | T-006; T-007; T-011; T-012 |
| Aprobacion humana explicita | Bloquea Architecture, Governed Execution Preparation, Development y movimientos. | T-008+ |
| Paquete GEP completo | Bloquea decision informada sobre Development futuro. | T-014 a T-020 |

---

## 9. Riesgos de planificacion

| Riesgo | Impacto | Mitigacion |
| --- | --- | --- |
| Interpretar SPEC como permiso de mover archivos | Alto | Reglas explicitas de no ejecucion en Brief, SPEC, Readiness y Tasks. |
| Mezclar Consolidation Agent con ejecucion fisica | Alto | Frontera documentada; agente propone, esta capacidad gobierna ejecucion futura. |
| Saltar reference map | Alto | T-010/T-012 dependen de mapa futuro. |
| Actualizar indices globales prematuramente | Medio | Tratado como impacto futuro, no como cambio automatico. |
| Crear scripts de conveniencia | Alto | Fuera de alcance hasta nueva capacidad Development. |

---

## 10. Siguiente paso recomendado

```text
None.
```


Development adicional permanece `NOT AUTHORIZED` fuera del primer lote ejecutado. No se autoriza normalizacion fisica adicional sin decision/gate aplicable.

---

## Definition of Done

El backlog inicial esta listo cuando:

- registra los artefactos fuente;
- contiene tareas trazables;
- separa tareas completadas, pendientes y no autorizadas;
- identifica siguiente agente recomendado;
- mantiene Development no autorizado y Governed Execution Preparation limitada a lo aprobado en T-013;
- no incluye ejecucion de normalizacion fisica.

---

## 11. Reviewer Decision - T-006

Decision: `Approved with minor changes`.

Fecha: 2026-08-02.

Evaluador: Reviewer Agent.

Artefactos revisados:

- `docs/capabilities/repository-physical-normalization/project_brief.md`
- `docs/capabilities/repository-physical-normalization/context_refs.md`
- `specs/capabilities/repository-physical-normalization/spec-001-repository-physical-normalization.md`
- `docs/capabilities/repository-physical-normalization/sdd_readiness_assessment.md`
- `docs/capabilities/repository-physical-normalization/tasks.md`

Resultado:

- No hay hallazgos criticos.
- No hay hallazgos importantes.
- Hallazgos menores documentales aplicados por Documentation Agent.
- Architecture documental fue autorizada por T-008 y completada en T-009/T-010.
- Development permanece `NOT AUTHORIZED`.
- No se ejecuta normalizacion fisica.

Cambios menores aplicados:

- `docs/capabilities/index.md` indexa `Repository Physical Normalization` como capacidad en `Specification`.
- `specs/capabilities/index.md` indexa `SPEC-001 - Repository Physical Normalization`.
- `sdd_readiness_assessment.md` refleja Reviewer T-006 y siguiente agente recomendado `QA Gate Agent`.

Siguiente paso historico valido:

```text
QA Gate Agent validation of Specification readiness.
```

Estado superado por T-007, T-008, T-012 y T-013.
---

## 12. QA Gate Decision - T-007

Decision: `Pass with minor conditions`.

Fecha: 2026-08-02.

Evaluador: QA Gate Agent.

Gate evaluado:

Specification readiness for `Repository Physical Normalization`.

Resultado:

- Los artefactos de Specification existen y son coherentes.
- Reviewer T-006 fue completado con cambios menores ya aplicados.
- Los indices globales registran la capacidad y la specification como catalogos no normativos.
- No existe implementacion prematura.
- No se modifican baselines cerrados.
- No se ejecuta normalizacion fisica.

Condiciones:

1. Architecture requiere decision humana explicita.
2. Development permanece `NOT AUTHORIZED`.
3. Cualquier movimiento, copia, renombre, sustitucion o eliminacion permanece `NOT AUTHORIZED`.
4. Una Architecture futura debe resolver compatibilidad legacy, reference map, movement plan y rollback plan antes de cualquier ejecucion.

Siguiente paso historico valido:

```text
Human decision on whether to authorize Architecture documental.
```

Estado superado por T-008, T-012 y T-013.
---

## 13. Architecture Authorization - T-008

Decision: `AUTHORIZED` solo para Architecture documental.

Fecha: 2026-08-02.

Fuente: solicitud humana `Autorizacion de la Architecture documental` posterior a QA Gate T-007.

Alcance autorizado:

- crear `ARCH-001 - Repository Physical Normalization`;
- definir estructura conceptual, componentes, interfaces, alternativas y decisiones;
- definir reference map, movement plan y rollback plan como componentes futuros no ejecutables;
- actualizar expediente local e indices no normativos.

Fuera de autorizacion:

- Development;
- normalizacion fisica;
- movimiento, copia, renombre, sustitucion o eliminacion de archivos;
- scripts, tools, workflows, runtime o automatizaciones;
- modificacion de baselines cerrados.

---

## 14. Architecture Execution - T-009/T-010

Estado: `Completed`.

Fecha: 2026-08-02.

Artefacto creado:

- `specs/capabilities/repository-physical-normalization/arch-001-repository-physical-normalization.md`.

Resultado:

- arquitectura documental creada;
- componentes e interfaces definidos;
- reference map, movement plan y rollback plan definidos como artefactos futuros no ejecutables;
- `SDD Modes` definido como piloto futuro sin ejecutar movimientos;
- no se crean scripts, tools, workflows, runtime ni automatizaciones;
- no se modifican baselines cerrados;
- no se mueve, copia, renombra, sustituye ni elimina ningun archivo.

Siguiente paso historico valido:

```text
Reviewer Agent review of Architecture package.
```

Estado superado por T-011, T-012 y T-013.
---

## 15. Architecture Reviewer Decision - T-011

Decision: `Approved with minor changes`.

Fecha: 2026-08-02.

Evaluador: Reviewer Agent.

Artefactos revisados:

- `specs/capabilities/repository-physical-normalization/arch-001-repository-physical-normalization.md`
- `docs/capabilities/repository-physical-normalization/project_brief.md`
- `docs/capabilities/repository-physical-normalization/context_refs.md`
- `specs/capabilities/repository-physical-normalization/spec-001-repository-physical-normalization.md`
- `docs/capabilities/repository-physical-normalization/sdd_readiness_assessment.md`
- `docs/capabilities/repository-physical-normalization/tasks.md`
- `docs/capabilities/index.md`
- `specs/capabilities/index.md`

Resultado:

- No hay hallazgos criticos.
- No hay hallazgos importantes.
- `ARCH-001` respeta `SDD Full`.
- `ARCH-001` esta trazada a `SPEC-001`.
- No introduce implementacion prematura.
- No autoriza Development.
- No ejecuta normalizacion fisica.
- No modifica baselines cerrados.

Cambios menores aplicados por Documentation Agent:

- `ARCH-001` marca como completada la actualizacion de indices globales no normativos.
- Readiness identifica el bloque QA T-007 como historico y superado por T-008.
- Este backlog marca T-011 como completada y T-012 como siguiente paso pendiente.

Siguiente paso historico valido:

```text
QA Gate Agent validation of Architecture readiness.
```

Estado superado por T-012 y T-013.

Development permanece `NOT AUTHORIZED`. No se autoriza normalizacion fisica.
---

## 16. Architecture QA Gate Decision - T-012

Decision: `Pass with minor conditions`.

Fecha: 2026-08-02.

Evaluador: QA Gate Agent.

Gate evaluado:

Architecture readiness for `Repository Physical Normalization`.

Fase actual:

`Architecture`.

Fase destino:

Decision humana futura sobre siguiente fase documental o preparacion ejecutiva. Este gate no autoriza Development ni normalizacion fisica.

Artefactos revisados:

- `docs/capabilities/repository-physical-normalization/project_brief.md`
- `docs/capabilities/repository-physical-normalization/context_refs.md`
- `specs/capabilities/repository-physical-normalization/spec-001-repository-physical-normalization.md`
- `specs/capabilities/repository-physical-normalization/arch-001-repository-physical-normalization.md`
- `docs/capabilities/repository-physical-normalization/sdd_readiness_assessment.md`
- `docs/capabilities/repository-physical-normalization/tasks.md`
- `docs/capabilities/index.md`
- `specs/capabilities/index.md`
- `.github/instructions/sdd.instructions.md`
- `.github/agents/qa-gate.agent.md`

Resultado:

- `SDD Full` verificado desde Project Brief.
- `SPEC-001` existe y paso QA T-007.
- Architecture documental fue autorizada por T-008.
- `ARCH-001` existe, esta trazada a `SPEC-001` y fue revisada por Reviewer Agent en T-011.
- Reference map, movement plan y rollback plan estan definidos como componentes futuros no ejecutables.
- No hay implementacion prematura.
- No se crean scripts, tools, workflows, runtime ni automatizaciones.
- No se mueve, copia, renombra, sustituye ni elimina ningun archivo.
- No se modifican baselines cerrados.

Condiciones:

1. Cualquier ejecucion fisica futura requiere decision humana explicita posterior a este gate.
2. Antes de ejecutar movimientos debe existir reference map completo, canonical route registry, movement plan detallado y rollback plan detallado.
3. `SDD Modes` debe permanecer read-only hasta que exista plan ejecutable aprobado, review y QA especificos.
4. Development permanece `NOT AUTHORIZED`.
5. Normalizacion fisica permanece `NOT AUTHORIZED`.

Siguiente paso historico valido:

```text
Human decision on whether to authorize Governed Execution Preparation.
```

Estado superado por T-013.

Development permanece `NOT AUTHORIZED`. No se autoriza normalizacion fisica.
---

## 17. Governed Execution Preparation Authorization - T-013

Decision: `AUTHORIZED` solo para preparacion documental de ejecucion gobernada.

Fecha: 2026-08-02.

Fuente: decision humana posterior a QA Gate T-012.

Alcance autorizado:

- Canonical Route Registry;
- Reference Map;
- Movement Plan;
- Compatibility Plan;
- Rollback Plan;
- Validation Checklist;
- SDD Modes Pilot Package;
- actualizacion del Task Plan y artefactos documentales necesarios.

Fuera de autorizacion:

- Development;
- movimientos fisicos del repositorio;
- renombrado de archivos;
- creacion de stubs;
- modificacion de baselines cerrados;
- ejecucion del Movement Plan;
- scripts, herramientas, workflows o automatizaciones.

---

## 18. Governed Execution Preparation Package - T-014/T-020

Estado: `Completed for review`.

Fecha: 2026-08-02.

Artefactos creados:

- `docs/capabilities/repository-physical-normalization/governed-execution-preparation/README.md`
- `docs/capabilities/repository-physical-normalization/governed-execution-preparation/canonical_route_registry.md`
- `docs/capabilities/repository-physical-normalization/governed-execution-preparation/reference_map.md`
- `docs/capabilities/repository-physical-normalization/governed-execution-preparation/movement_plan.md`
- `docs/capabilities/repository-physical-normalization/governed-execution-preparation/compatibility_plan.md`
- `docs/capabilities/repository-physical-normalization/governed-execution-preparation/rollback_plan.md`
- `docs/capabilities/repository-physical-normalization/governed-execution-preparation/validation_checklist.md`
- `docs/capabilities/repository-physical-normalization/governed-execution-preparation/sdd_modes_pilot_package.md`

Resultado:

- paquete documental definitivo de preparacion creado;
- `SDD Modes` queda definido como piloto read-only;
- rutas objetivo, referencias, movimientos futuros, compatibilidad, rollback y validacion quedan preparados para review;
- no se ejecuta normalizacion fisica;
- no se crean stubs;
- no se crean scripts, tools, workflows ni automatizaciones;
- no se modifican baselines cerrados.

Siguiente paso historico valido:

```text
Reviewer Agent review of Governed Execution Preparation package.
```

Estado superado por T-021.

Development permanece `NOT AUTHORIZED`. No se autoriza normalizacion fisica.
---

## 19. Governed Execution Preparation Reviewer Decision - T-021

Decision: `Approved with minor changes`.

Fecha: 2026-08-02.

Evaluador: Reviewer Agent.

Artefactos revisados:

- `docs/capabilities/repository-physical-normalization/governed-execution-preparation/README.md`
- `docs/capabilities/repository-physical-normalization/governed-execution-preparation/canonical_route_registry.md`
- `docs/capabilities/repository-physical-normalization/governed-execution-preparation/reference_map.md`
- `docs/capabilities/repository-physical-normalization/governed-execution-preparation/movement_plan.md`
- `docs/capabilities/repository-physical-normalization/governed-execution-preparation/compatibility_plan.md`
- `docs/capabilities/repository-physical-normalization/governed-execution-preparation/rollback_plan.md`
- `docs/capabilities/repository-physical-normalization/governed-execution-preparation/validation_checklist.md`
- `docs/capabilities/repository-physical-normalization/governed-execution-preparation/sdd_modes_pilot_package.md`
- artefactos de trazabilidad de la capacidad e indices globales.

Resultado:

- No hay hallazgos criticos.
- No hay hallazgos importantes.
- El paquete respeta `SDD Full` y la autorizacion T-013.
- No autoriza Development.
- No ejecuta normalizacion fisica.
- No crea stubs, scripts, workflows ni automatizaciones.
- No modifica baselines cerrados.

Cambios menores aplicados por Documentation Agent:

- `ARCH-001` refleja estado vigente `Governed Execution Preparation` y siguiente paso QA del paquete GEP.
- Este backlog preserva next steps historicos y registra T-021 como completada.
- Readiness separa decisiones historicas de la decision vigente del paquete GEP.
- Context refs, checklist e indices enrutan hacia QA Gate T-022.

Siguiente paso valido:

```text
QA Gate Agent validation of Governed Execution Preparation readiness.
```

Development permanece `NOT AUTHORIZED`. No se autoriza normalizacion fisica.
---

## 20. Governed Execution Preparation QA Gate Decision - T-022

Decision: `Pass with minor conditions`.

Fecha: 2026-08-02.

Evaluador: QA Gate Agent.

Gate evaluado:

Governed Execution Preparation readiness for possible future Development authorization.

Fase actual:

`Governed Execution Preparation`.

Fase destino:

Decision humana posterior sobre si se autoriza Development. Este gate no autoriza Development ni normalizacion fisica por si solo.

Artefactos revisados:

- `docs/capabilities/repository-physical-normalization/project_brief.md`
- `docs/capabilities/repository-physical-normalization/context_refs.md`
- `specs/capabilities/repository-physical-normalization/spec-001-repository-physical-normalization.md`
- `specs/capabilities/repository-physical-normalization/arch-001-repository-physical-normalization.md`
- `docs/capabilities/repository-physical-normalization/sdd_readiness_assessment.md`
- `docs/capabilities/repository-physical-normalization/tasks.md`
- `docs/capabilities/repository-physical-normalization/governed-execution-preparation/README.md`
- `docs/capabilities/repository-physical-normalization/governed-execution-preparation/canonical_route_registry.md`
- `docs/capabilities/repository-physical-normalization/governed-execution-preparation/reference_map.md`
- `docs/capabilities/repository-physical-normalization/governed-execution-preparation/movement_plan.md`
- `docs/capabilities/repository-physical-normalization/governed-execution-preparation/compatibility_plan.md`
- `docs/capabilities/repository-physical-normalization/governed-execution-preparation/rollback_plan.md`
- `docs/capabilities/repository-physical-normalization/governed-execution-preparation/validation_checklist.md`
- `docs/capabilities/repository-physical-normalization/governed-execution-preparation/sdd_modes_pilot_package.md`
- `docs/capabilities/index.md`
- `specs/capabilities/index.md`

Evidencias encontradas:

- `SDD Full` verificado desde Project Brief.
- Architecture fue completada y validada por QA Gate T-012 con condiciones menores.
- Governed Execution Preparation fue autorizada por decision humana T-013.
- Canonical Route Registry, Reference Map, Movement Plan, Compatibility Plan, Rollback Plan, Validation Checklist y SDD Modes Pilot Package existen.
- Reviewer Agent T-021 emitio `Approved with minor changes` y las correcciones menores fueron aplicadas por Documentation Agent.
- El paquete declara repetidamente `Development NOT AUTHORIZED` y `normalizacion fisica NOT AUTHORIZED`.
- En el momento de T-022, antes de T-023/T-024, no existian rutas objetivo `docs/capabilities/sdd-modes` ni `specs/capabilities/sdd-modes`.
- El paquete GEP contiene solo archivos Markdown.
- No se crean stubs, scripts, tools, workflows ni automatizaciones.

Criterios cumplidos:

- Fase actual identificada.
- Fase destino justificada como decision humana posterior, no como Development automatico.
- Artefactos obligatorios del paquete GEP existen.
- Los artefactos son coherentes entre si.
- No hay contradicciones documentales criticas.
- No hay implementacion prematura.
- Riesgos y condiciones de ejecucion futura estan documentados.
- El siguiente paso esta claro.

Criterios no cumplidos:

- Development no esta autorizado.
- No existe decision humana posterior sobre Development.
- La Reference Map final inmediatamente previa a ejecucion sigue pendiente para una fase Development futura, si se autorizara.
- La decision final sobre tratamiento de `specs/spec-001-sdd-modes.architecture.md` permanece pendiente para ejecucion futura.

Bloqueos:

- Ningun bloqueo para pasar a decision humana posterior.
- Bloqueo explicito para ejecutar Development, movimientos fisicos, stubs, scripts, workflows o automatizaciones sin decision humana futura.

Condiciones menores:

1. Una decision humana posterior debe autorizar Development de forma explicita antes de cualquier ejecucion.
2. Antes de ejecutar movimientos debe realizarse una Reference Map final actualizada inmediatamente antes de la ejecucion.
3. La decision sobre la ruta/nombre futuro de `specs/spec-001-sdd-modes.architecture.md` debe cerrarse antes de mover o renombrar ese artefacto.
4. `SDD Modes` debe permanecer read-only hasta que Development sea autorizado y se active el Movement Plan.
5. Cualquier ejecucion futura debe conservar rollback, compatibilidad legacy y ausencia de cambio normativo de baseline.

Siguiente paso valido:

```text
Human decision on whether to authorize Development for Repository Physical Normalization.
```

Development permanece `NOT AUTHORIZED`. No se autoriza normalizacion fisica.
---

## 21. Development Authorization - T-023

Decision: `AUTHORIZED`.

Fecha: 2026-08-02.

Fuente: decision humana `Autorizo el desarrollo` posterior a QA Gate T-022.

Alcance aplicado de forma conservadora:

- ejecutar primera ola controlada sobre SDD Modes;
- crear rutas canonicas para expediente documental y specification de SDD Modes;
- preservar compatibilidad legacy mediante stubs;
- mantener `specs/spec-001-sdd-modes.architecture.md` en ruta legacy, sin mover ni renombrar;
- actualizar indices y expediente activo de Repository Physical Normalization;
- registrar evidencia para review y QA post-Development.

No autorizado por esta ejecucion:

- movimientos adicionales fuera de la primera ola;
- borrar rutas legacy;
- mover o renombrar `specs/spec-001-sdd-modes.architecture.md`;
- crear scripts, tools, workflows o automatizaciones;
- modificar contenido normativo de baselines cerrados;
- cerrar deuda residual.

---

## 22. Development First Wave Execution - T-024/T-026

Estado: `Executed / reviewed by Reviewer Agent T-027`.

Fecha: 2026-08-02.

Reporte:

- `docs/capabilities/repository-physical-normalization/governed-execution-preparation/movement_execution_report.md`

Rutas canonicas creadas:

- `docs/capabilities/sdd-modes/project_brief.md`
- `docs/capabilities/sdd-modes/context_refs.md`
- `docs/capabilities/sdd-modes/tasks.md`
- `docs/capabilities/sdd-modes/sdd_readiness_assessment.md`
- `specs/capabilities/sdd-modes/spec-001-sdd-modes.md`

Stubs legacy creados:

- `docs/project_brief.md`
- `docs/context_refs.md`
- `docs/tasks.md`
- `docs/sdd_readiness_assessment.md`
- `specs/spec-001-sdd-modes.md`

Decision sobre Architecture SDD Modes:

`specs/spec-001-sdd-modes.architecture.md` se mantiene en ruta legacy y no se mueve ni renombra en esta ola.

Siguiente paso valido:

```text
None.
```
---

## 23. Local Validation Result - T-026

Estado: `Completed`.

Verificaciones realizadas:

- rutas canonicas existen bajo `docs/capabilities/sdd-modes/` y `specs/capabilities/sdd-modes/`;
- stubs legacy existen en las cinco rutas movidas;
- `specs/spec-001-sdd-modes.architecture.md` permanece disponible;
- el paquete GEP contiene solo archivos Markdown;
- `git diff --check` no reporta errores, solo avisos normales de fin de linea CRLF en Windows;
- no se crean scripts, tools, workflows ni automatizaciones.

Siguiente paso valido:

```text
None.
```
---

## 24. Development Reviewer Decision - T-027

Decision: `Approved with minor changes`.

Fecha: 2026-08-02.

Evaluador: Reviewer Agent.

Artefactos revisados:

- `docs/capabilities/repository-physical-normalization/governed-execution-preparation/movement_execution_report.md`
- `docs/capabilities/repository-physical-normalization/governed-execution-preparation/validation_checklist.md`
- `docs/capabilities/repository-physical-normalization/governed-execution-preparation/reference_map.md`
- `docs/capabilities/index.md`
- `specs/capabilities/index.md`
- rutas canonicas y stubs legacy de SDD Modes.

Resultado:

- No hay hallazgos criticos.
- No hay hallazgos importantes.
- La primera ola ejecutada coincide con la autorizacion humana T-023.
- Los cinco artefactos de SDD Modes existen en rutas canonicas.
- Las cinco rutas legacy movidas existen como stubs no normativos.
- `specs/spec-001-sdd-modes.architecture.md` permanece en ruta legacy, sin mover ni renombrar.
- No se detectan scripts, tools, workflows ni automatizaciones.
- No se detecta cambio normativo del baseline cerrado de SDD Modes.

Hallazgo menor aplicado por Documentation Agent:

- actualizar encabezados y next steps activos de `pending review` a `reviewed / pending QA Gate`.

Siguiente paso valido:

```text
None.
```
---

## 25. Development QA Gate Decision - T-028

Decision: `Pass with minor conditions`.

Fecha: 2026-08-02.

Evaluador: QA Gate Agent.

Gate evaluado:

Repository Physical Normalization Development first wave validation.

Resultado:

- La fase Development fue autorizada por decision humana T-023.
- La ejecucion T-024/T-026 esta registrada en `movement_execution_report.md`.
- Reviewer Agent T-027 emitio `Approved with minor changes`.
- Las rutas canonicas de SDD Modes existen.
- Las rutas legacy movidas existen como stubs no normativos.
- `specs/spec-001-sdd-modes.architecture.md` permanece en ruta legacy.
- No se crearon scripts, tools, workflows ni automatizaciones.
- No se detecta cambio normativo del baseline cerrado de SDD Modes.

Condicion menor aplicada por Documentation Agent:

- actualizar el criterio del checklist para que describa validacion post-ejecucion, no readiness previa a Development.

Siguiente paso valido:

```text
None.
```
---

## 26. SDD Modes Architecture Route Decision Preparation - T-029/T-032

Estado: `Completed` (review T-033, QA T-034, autorizacion T-035, ejecucion T-036 y cierre T-039 completados).

Fecha: 2026-08-02.

Agentes: Architect Agent / Tasks Planner Agent.

Resultado:

- Reference Map completo para `specs/spec-001-sdd-modes.architecture.md` preparado.
- Decision propuesta: `Option A`.
- Ruta objetivo futura: `specs/capabilities/sdd-modes/arch-001-sdd-modes.md`.
- Ruta legacy futura: stub no normativo en `specs/spec-001-sdd-modes.architecture.md`.
- Movement Plan, Compatibility Plan y Rollback Plan actualizados para DEV-RPN-010.
- No se ejecuta movimiento, renombre, stub ni modificacion del baseline cerrado.

Siguiente paso valido:

```text
None.
```
---

## 27. SDD Modes Architecture Route Reviewer Decision - T-033

Decision: `Approved with minor changes`.

Fecha: 2026-08-02.

Evaluador: Reviewer Agent.

Artefactos revisados:

- `docs/capabilities/repository-physical-normalization/governed-execution-preparation/sdd_modes_architecture_route_decision.md`
- `docs/capabilities/repository-physical-normalization/governed-execution-preparation/reference_map.md`
- `docs/capabilities/repository-physical-normalization/governed-execution-preparation/movement_plan.md`
- `docs/capabilities/repository-physical-normalization/governed-execution-preparation/compatibility_plan.md`
- `docs/capabilities/repository-physical-normalization/governed-execution-preparation/rollback_plan.md`
- `docs/capabilities/repository-physical-normalization/governed-execution-preparation/validation_checklist.md`

Resultado:

- No hay hallazgos criticos.
- No hay hallazgos importantes.
- `Option A` queda justificada como decision recomendada.
- No se ejecuta movimiento, renombre ni stub.
- Estado en T-033: la ruta legacy permanecia disponible y la ruta objetivo no existia todavia. Estado superado por T-036.
- Las referencias activas son actualizables y las historicas quedan cubiertas por stub futuro.
- Rollback DEV-RPN-010 es viable.

Hallazgos menores aplicados por Documentation Agent:

- alinear estados de encabezado en planes GEP;
- actualizar checklist VC-ARCH-006.

Siguiente paso valido:

```text
None.
```
---

## 28. SDD Modes Architecture Route QA Gate Decision - T-034

Decision: `Pass with minor conditions`.

Fecha: 2026-08-02.

Evaluador: QA Gate Agent.

Gate evaluado:

DEV-RPN-010 architecture route decision package readiness for possible explicit human authorization.

Fase actual:

`Development`, limitada a preparacion documental de decision de ruta y sin ejecucion adicional autorizada.

Fase destino:

Decision humana explicita sobre si se autoriza ejecutar DEV-RPN-010.

Artefactos requeridos revisados:

- `sdd_modes_architecture_route_decision.md`.
- `reference_map.md`.
- `movement_plan.md`.
- `compatibility_plan.md`.
- `rollback_plan.md`.
- `validation_checklist.md`.
- `sdd_modes_pilot_package.md`.
- `project_brief.md`, `context_refs.md`, `sdd_readiness_assessment.md` y este Task Plan.

Evidencias encontradas:

- Reviewer T-033 emitio `Approved with minor changes` y las correcciones menores fueron aplicadas.
- La decision propuesta es `Option A`: mover `specs/spec-001-sdd-modes.architecture.md` a `specs/capabilities/sdd-modes/arch-001-sdd-modes.md` y dejar stub legacy.
- Reference Map identifica referencias activas, historicas y tratamiento propuesto.
- Movement, Compatibility y Rollback Plans definen DEV-RPN-010 sin ejecutarlo.
- `specs/spec-001-sdd-modes.architecture.md` existe todavia en ruta legacy.
- Estado en T-034: `specs/capabilities/sdd-modes/arch-001-sdd-modes.md` no existia todavia. Estado superado por T-036.
- No se han creado stubs, scripts, tools, workflows ni automatizaciones para DEV-RPN-010.

Criterios cumplidos:

- fase actual y fase destino estan identificadas;
- artefactos obligatorios existen y son coherentes;
- no hay implementacion prematura;
- compatibilidad y rollback estan definidos;
- la autorizacion humana explicita permanece como gate separado T-035.

Criterios no cumplidos:

- ninguno bloqueante.

Condiciones menores:

- T-035 debe registrar autorizacion humana explicita antes de mover, renombrar o crear stub.
- Reference Map debe reejecutarse inmediatamente antes de cualquier ejecucion.
- El worktree debe auditarse antes del movimiento para preservar cambios no relacionados.
- El stub legacy solo puede crearse dentro de una ejecucion autorizada y debe ser no normativo.
- Tras cualquier ejecucion autorizada, deben actualizarse referencias activas y registrarse Review/QA post-ejecucion.

Bloqueos:

- ninguno para pasar a decision humana.
- DEV-RPN-010 permanecio `NOT AUTHORIZED` hasta T-035; T-035 lo autorizo y T-036 lo ejecuto.

Siguiente paso valido:

```text
None.
```
---

## 29. Human Authorization and Execution Result - T-035/T-036

Decision humana: `Autorizo`.

Fecha: 2026-08-02.

Alcance ejecutado:

- mover `specs/spec-001-sdd-modes.architecture.md` a `specs/capabilities/sdd-modes/arch-001-sdd-modes.md`;
- crear stub legacy no normativo en `specs/spec-001-sdd-modes.architecture.md`;
- actualizar referencias activas del expediente SDD Modes, indices y artefactos activos de RPN;
- preservar referencias historicas de capacidades cerradas mediante compatibilidad legacy.

Resultado:

- ruta canonica creada: `specs/capabilities/sdd-modes/arch-001-sdd-modes.md`;
- stub legacy creado: `specs/spec-001-sdd-modes.architecture.md`;
- no se crearon scripts, tools, workflows ni automatizaciones;
- no se elimina historia Git;
- contenido normativo movido sin cambio funcional.

Siguiente paso valido:

```text
None.
```
---

## 30. DEV-RPN-010 Reviewer Decision - T-037

Decision: `Approved with minor changes`.

Fecha: 2026-08-02.

Revisor: Reviewer Agent.

Hallazgos criticos: ninguno.

Hallazgos importantes: ninguno.

Hallazgos menores:

- El paquete mantiene referencias historicas a estados previos de DEV-RPN-010; son aceptables siempre que el estado vivo apunte a QA post-ejecucion.

Evidencias revisadas:

- `specs/capabilities/sdd-modes/arch-001-sdd-modes.md` existe como ruta canonica.
- `specs/spec-001-sdd-modes.architecture.md` existe como stub legacy no normativo.
- Indices activos apuntan a `specs/capabilities/sdd-modes/arch-001-sdd-modes.md`.
- El expediente activo de SDD Modes no conserva referencias a la ruta legacy como ruta canonica.
- `movement_execution_report.md` registra DEV-RPN-010.
- No se crearon scripts, tools, workflows ni automatizaciones.
- `git diff --check` no reporta errores, solo avisos CRLF.

Siguiente paso valido:

```text
None.
```
---

## 31. DEV-RPN-010 QA Gate Decision - T-038

Decision: `Pass with minor conditions`.

Fecha: 2026-08-02.

Evaluador: QA Gate Agent.

Gate evaluado:

DEV-RPN-010 post-execution validation.

Evidencias encontradas:

- `specs/capabilities/sdd-modes/arch-001-sdd-modes.md` existe.
- `specs/spec-001-sdd-modes.architecture.md` existe como stub legacy no normativo.
- Las superficies activas revisadas no conservan `specs/spec-001-sdd-modes.architecture.md` como ruta canonica.
- `movement_execution_report.md`, `canonical_route_registry.md`, `movement_plan.md`, `validation_checklist.md` y este Task Plan registran la ejecucion.
- No hay archivos no Markdown nuevos en GEP.
- `git diff --check` no reporta errores; solo avisos CRLF del entorno Windows/Git.

Criterios cumplidos:

- movimiento autorizado y ejecutado;
- compatibilidad legacy preservada;
- ruta canonica alineada con el modelo fisico aprobado;
- trazabilidad documental actualizada;
- rollback documentado;
- no se detecta cambio funcional o normativo;
- no se crearon scripts, tools, workflows ni automatizaciones.

Condiciones menores:

- Una decision humana debe determinar si DEV-RPN-010 se cierra o si se abre trabajo adicional de RPN.
- Las referencias historicas en capacidades cerradas deben permanecer cubiertas por el stub legacy y no reescribirse sin reentrada explicita.
- Cualquier nueva ola de normalizacion requiere nuevo scope/gate/autorizacion.

Siguiente paso valido:

```text
None.
```
---

## 32. DEV-RPN-010 Human Closure Decision - T-039

Decision humana: `Autorizo el cierre`.

Fecha: 2026-08-02.

Nota: la autorizacion fue expresada dos veces de forma consecutiva y se registra como una unica decision humana de cierre.

Alcance cerrado:

- DEV-RPN-010 ejecutado;
- ruta canonica `specs/capabilities/sdd-modes/arch-001-sdd-modes.md` creada;
- stub legacy no normativo `specs/spec-001-sdd-modes.architecture.md` creado;
- referencias activas actualizadas;
- Reviewer T-037 completado;
- QA Gate T-038 completado con `Pass with minor conditions`.

Condiciones residuales aceptadas:

- referencias historicas de capacidades cerradas permanecen cubiertas por stub legacy;
- cualquier nueva ola de normalizacion requiere nuevo alcance, gate y autorizacion humana;
- no queda autorizacion abierta para movimientos adicionales.

Estado final:

```text
Closed - DEV-RPN-010
```

Siguiente paso activo:

```text
None.
```
---

## 33. Post-Development Reconciliation - Closure Preparation

Estado: `Completed / QA Gate passed with minor conditions`.

Fecha: 2026-08-02.

Agente: Documentation Agent.

Resultado:

- `sdd_readiness_assessment.md` reconciliado con el estado real post-Development.
- `evidence_index.md` creado.
- `residual_debt.md` creado.
- `closure_handover.md` creado.
- Baseline fisico vigente de SDD Modes registrado.
- Stubs raiz registrados como `Temporary compatibility stubs`.
- Reentrada futura para retirada de stubs definida.
- Indices globales actualizados.

Estado de DEV-RPN-010:

```text
Closed
```

Siguiente accion valida:

```text
None.
```

Gate global:

```text
PASS WITH MINOR CONDITIONS - T-040
```

---

## 34. Global Closure Gate Decision - T-040

Decision: `Pass with minor conditions`.

Fecha: 2026-08-02.

Evaluador: QA Gate Agent.

Gate evaluado:

Global Closure Gate de `Repository Physical Normalization`.

Artefacto de decision:

- `docs/capabilities/repository-physical-normalization/global_closure_gate.md`

Resultado:

- no hay bloqueos para decision humana de cierre global;
- DEV-RPN-010 esta cerrado;
- T-001 a T-040 quedan completadas;
- baseline fisico vigente de SDD Modes esta registrado;
- stubs raiz quedan como `Temporary compatibility stubs` no normativos;
- deuda residual y reentrada futura estan documentadas;
- Development adicional permanece `NOT AUTHORIZED`.

Condiciones menores:

- los stubs raiz permanecen como deuda residual aceptada;
- referencias historicas siguen cubiertas por stubs legacy;
- el cierre global requirio decision humana explicita posterior, cumplida por T-041.

Siguiente accion valida:

```text
None.
```
---

## 35. Human Global Closure Decision - T-041

Decision humana: `Adelante con el cierre global`.

Fecha: 2026-08-02.

Resultado:

- `Repository Physical Normalization` queda `Closed with minor conditions`.
- T-001 a T-041 quedan `Completed`.
- QA Gate T-040 queda aceptado con `Pass with minor conditions`.
- DEV-RPN-010 permanece `Closed`.
- SDD Modes Specification y Architecture permanecen en rutas capability-local canonicas.
- Las rutas raiz permanecen como `Temporary compatibility stubs` no normativos.
- La deuda residual de stubs temporales queda aceptada y gobernada.
- Development adicional permanece `NOT AUTHORIZED`.
- No queda siguiente paso activo dentro de la capacidad.

Condiciones de cierre aceptadas:

- permanencia temporal de stubs raiz;
- referencias historicas cubiertas por stubs legacy;
- retirada futura solo mediante auditoria, impacto en derivados, Reviewer, QA y autorizacion humana explicita.

Siguiente paso activo:

```text
None.
```