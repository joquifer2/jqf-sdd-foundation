# Plan de tareas - SDD Modes

## Metadata

| Campo | Valor |
| --- | --- |
| Plan ID | TASKPLAN-001 |
| Capacidad | SDD Modes |
| Project Brief relacionado | `docs/project_brief.md` |
| Context References relacionado | `docs/context_refs.md` |
| Specification relacionada | `specs/spec-001-sdd-modes.md` |
| Architecture relacionada | `specs/capabilities/sdd-modes/arch-001-sdd-modes.md` |
| Estado | Final |
| Fase SDD actual | Specification / Structure |
| Owner | Jordi Quiroga |
| Creado por | Tasks Planner Agent |
| Ultima actualizacion | 2026-08-01 |

---

## 1. Objetivo

Transformar `SPEC-001 - SDD Modes` y `ARCH-001 - SDD Modes Conceptual and Documentary Architecture` en un plan de trabajo trazable para desarrollar la capacidad SDD Modes dentro de `jqf-sdd-foundation`.

Este plan es exclusivamente documental y de gobernanza. No autoriza Development, implementacion, runtime, workflows ejecutables, herramientas, integraciones, infraestructura ni logica de negocio.

---

## 2. Artefactos fuente

| Artefacto | Rol en el plan |
| --- | --- |
| `docs/project_brief.md` | Define proposito, alcance, restricciones, riesgos, criterios de exito y siguientes pasos esperados. |
| `docs/context_refs.md` | Define fuentes obligatorias de contexto y referencias externas pendientes. |
| `specs/spec-001-sdd-modes.md` | Define requisitos, reglas, criterios de aceptacion y preguntas abiertas. |
| `specs/capabilities/sdd-modes/arch-001-sdd-modes.md` | Define componentes conceptuales/documentales, alternativas y areas de impacto. |
| Resultado Reviewer de `SPEC-001` | `PASS` tras incorporar condiciones. |
| Resultado Reviewer de `ARCH-001` | `PASS`; siguiente paso: Tasks Planner Agent. |
| `.github/instructions/sdd.instructions.md` | Define fase actual y gobierno del backlog. |
| `AGENTS.md` | Define responsabilidades y limites de los agentes metodologicos. |

---

## 3. Reglas de planificacion

- Las tareas deben ser significativas, trazables y conectadas con `SPEC-001` o `ARCH-001`.
- Las tareas deben mantenerse alineadas con Specification / Structure.
- Las tareas de decision deben completarse antes de las tareas de actualizacion de artefactos que dependan de ellas.
- Ninguna tarea de este plan autoriza Development.
- Ninguna tarea puede introducir runtime, workflows ejecutables, herramientas, integraciones, infraestructura ni logica de negocio.
- Cualquier fuente externa no resuelta debe permanecer como `PENDING` hasta verificar URI y version.

---

## 4. Bloques de trabajo

1. Cierre de decisiones normativas abiertas.
2. Actualizacion de artefactos de la Foundation.
3. Revision y validacion.
4. Preparacion del gate de entrada a Development.

---

## 5. Orden recomendado de ejecucion

```text
T-001
  ↓
T-002 → T-003 → T-004 → T-005 → T-006 → T-007 → T-008 → T-009
  ↓
T-010 → T-011 → T-012 → T-013 → T-014 → T-015 → T-016
  ↓
T-017 → T-018 → T-019
  ↓
T-020 → T-021
```

Paralelizacion segura:

- `T-003`, `T-004`, `T-005`, `T-006`, `T-007`, `T-008` y `T-009` pueden prepararse en paralelo despues de `T-002`, pero deben reconciliarse antes de `T-010`.
- Las actualizaciones de artefactos de `T-010` a `T-016` deben realizarse despues del cierre de decisiones, porque dependen de terminologia y decisiones de gobernanza aprobadas.

---

## 6. Tareas

### Bloque 1 - Cierre de decisiones

| ID | Tarea | Tipo | Agente responsable | Dependencias | Criterios de aceptación | Estado |
| --- | --- | --- | --- | --- | --- | --- |
| T-001 | Verificar o degradar formalmente las fuentes externas pendientes. Confirmar URI/version de la nota de Professional OS `[SDD] - SDD Modes` y del documento conceptual consensuado, o registrar que permanecen como fuentes de descubrimiento no normativas. | Governance | Documentation Agent | `docs/context_refs.md`; Dependencies de `SPEC-001` | Cada fuente externa queda verificada con URI/version o retenida explícitamente como `PENDING` discovery-only. Si cambia el estado, URI, versión o rol normativo de una fuente, `docs/context_refs.md` queda actualizado como índice canónico de contexto antes de propagar la decisión a otros artefactos. | Completed |
| T-002 | Resolver la terminología normativa final de la capacidad. Decidir entre `SDD Mode`, `SDD Profile`, `Governance Mode`, y si Minimal/Lite/Full permanecen en inglés. | Specification | Specification Agent | T-001; Open Questions de `SPEC-001` | La terminología aprobada queda documentada y puede propagarse de forma consistente a spec, arquitectura, glosario y README. | Completed |
| T-003 | Definir la semántica normativa final de SDD Minimal, SDD Lite y SDD Full. Incluir propósito, contextos recomendados, límites, contextos prohibidos de Minimal y equivalencia de Full con el baseline actual. | Specification | Specification Agent | T-002; `SPEC-001` FR-001, FR-002, AC-017, AC-019 | Cada modo tiene semántica y límites claros; los contextos prohibidos de Minimal y la equivalencia de Full son explícitos y revisables. | Completed |
| T-004 | Decidir la fuente canónica para declarar y justificar el modo seleccionado. Evaluar Project Brief, Context References, sección/artefacto dedicado de gobernanza, specification/frontmatter o una regla híbrida aprobada. | Governance | Specification Agent | T-002; alternativas A-D de `ARCH-001` | Se selecciona una ubicación canónica o una regla deliberada multiubicación; quedan documentadas la precedencia y la responsabilidad de actualización. | Completed |
| T-005 | Definir dimensiones y reglas de selección del modo. Incluir como candidatas riesgo, complejidad, sensibilidad de datos, exposición a producción, cumplimiento, criticidad de integraciones, impacto operacional y auditabilidad. | Specification | Specification Agent | T-003; Mode Selection Criteria de `ARCH-001` | Los criterios orientan el juicio humano sin convertirse en scoring automático; la evidencia requerida queda definida. | Completed |
| T-006 | Definir el tratamiento de proyectos sin modo declarado. Decidir si existe temporalmente `Undeclared` y cómo evitar downgrade silencioso en repositorios existentes. | Governance | Specification Agent | T-004; `SPEC-001` FR-005, FR-022 | Los repositorios existentes y derivados tienen una ruta de compatibilidad documentada; la ausencia de modo no reduce gobierno silenciosamente. | Completed |
| T-007 | Definir el registro de checks ligeros. Decidir cómo registrar checks sin crear un archivo independiente por microtarea y cómo diferenciarlos de gates. | Specification | Specification Agent | T-003; `SPEC-001` FR-015, FR-016, AC-018 | Los checks tienen formato/ubicación de registro o regla de consolidación clara; los gates permanecen diferenciados y formales. | Completed |
| T-008 | Definir reglas de consolidación de evidencia. Decidir dónde vive la evidencia por modo y cuándo el historial Git es suficiente frente a documentación canónica. | Specification | Specification Agent | T-003; T-007; Evidence Policy de `ARCH-001` | Los requisitos de evidencia son claros por modo y no convierten documentos canónicos en historiales exhaustivos. | Completed |
| T-009 | Decidir la unidad de trabajo gobernada: `Implementation Wave` o un incremento gobernado más general. | Specification | Specification Agent | T-002; Open Questions de `SPEC-001` | La unidad queda nombrada y definida con suficiente claridad para soportar tareas, checks, gates y evidencia. | Completed |
| T-010 | Seleccionar proyectos derivados para escenarios de validación. Incluir ejemplos de bajo riesgo/interno, MVP/exposición limitada, producción/cumplimiento y repositorio existente sin modo declarado. | Validation | QA Gate Agent | T-003; Validation Scenarios de `ARCH-001` | Los candidatos de validación quedan nombrados o marcados explícitamente como no disponibles; se documenta la razón de selección. | Completed |

### Bloque 2 - Actualizacion de artefactos Foundation

| ID | Tarea | Tipo | Agente responsable | Dependencias | Criterios de aceptacion | Estado |
| --- | --- | --- | --- | --- | --- | --- |
| T-011 | Actualizar `specs/spec-001-sdd-modes.md` con las decisiones aprobadas de T-002 a T-010. | Specification | Specification Agent | T-002 a T-010 | Las preguntas abiertas resueltas se cierran; la incertidumbre restante queda explicita; no se introduce arquitectura ni implementacion. | Completed |
| T-012 | Actualizar `specs/capabilities/sdd-modes/arch-001-sdd-modes.md` para reflejar decisiones aprobadas sin anadir detalle de implementacion. | Architecture | Architect Agent | T-011 | La arquitectura queda alineada con la spec actualizada; las alternativas seleccionadas por decision humana quedan reflejadas sin aparecer como resueltas por inferencia. | Completed |
| T-013 | Actualizar `.github/instructions/sdd.instructions.md` con reglas de modo aprobadas a nivel de instruccion operativa. | Documentation | Documentation Agent | T-011; T-012 | Las instrucciones definen como el modo afecta fase SDD, checks, gates y carga de contexto sin duplicar todo el texto normativo. | Completed |
| T-014 | Actualizar solo las plantillas afectadas cuando sea necesario. Plantillas candidatas: Project Brief, Specification, Context References y cualquier plantilla de gate/readiness. | Documentation | Documentation Agent | T-011; T-012 | Las plantillas incorporan solo campos o guia necesarios; no se crean plantillas duplicadas salvo justificacion explicita. | Completed |
| T-015 | Actualizar instrucciones o adaptadores de agentes metodologicos para consumir el modo declarado sin crear agentes por modo. | Documentation | Documentation Agent | T-011; T-012; T-013 | Las instrucciones de agentes identifican como usar el modo; el catalogo permanece unico y no operativo. | Completed |
| T-016 | Actualizar `docs/glosario_terminos.md` y la documentacion de alto nivel del README con terminologia aprobada y resumen conceptual. | Documentation | Documentation Agent | T-011; T-013 | El glosario define los terminos aprobados; README se mantiene de alto nivel y no se convierte en la fuente completa de reglas. | Completed |

### Bloque 3 - Revision y validacion

| ID | Tarea | Tipo | Agente responsable | Dependencias | Criterios de aceptacion | Estado |
| --- | --- | --- | --- | --- | --- | --- |
| T-017 | Revision transversal por Reviewer Agent de los artefactos SDD Modes actualizados. | Review | Reviewer Agent | T-011 a T-016 | La revision cubre Project Brief, Context References, Spec, Architecture, SDD Instructions, AGENTS, plantillas, glosario e impactos en README. La decision es `PASS`, `PASS WITH CONDITIONS`, `FAIL` o `BLOCKED`. | Completed |
| T-018 | Validar SDD Modes contra los escenarios de proyectos derivados seleccionados. | Validation | QA Gate Agent | T-010; T-017 | La validacion muestra que Minimal, Lite y Full pueden aplicarse sin debilitar Full ni sobrecargar Lite/Minimal. Los gaps quedan registrados. | Completed |
| T-019 | Resolver hallazgos de revision y validacion. | Specification / Documentation | Agente responsable segun hallazgo | T-017; T-018 | Todos los hallazgos bloqueantes e importantes se resuelven, se difieren con justificacion o se aceptan explicitamente por decision humana. | Completed |

### Bloque 4 - Preparacion del gate de entrada a Development

| ID | Tarea | Tipo | Agente responsable | Dependencias | Criterios de aceptacion | Estado |
| --- | --- | --- | --- | --- | --- | --- |
| T-020 | Preparar el paquete de readiness de SDD Modes para el gate de entrada a Development. | Governance | Documentation Agent | T-019 | El paquete identifica spec final, arquitectura, artefactos actualizados, evidencia de validacion, riesgos no resueltos y solicitud explicita de evaluacion de gate. | Completed |
| T-021 | Evaluar readiness del gate para transicion hacia Development. | Validation | QA Gate Agent | T-020 | La decision del QA Gate queda documentada como `PASS`, `PASS WITH CONDITIONS`, `FAIL` o `BLOCKED`. Development no queda autorizado salvo permiso explicito del gate y aprobacion humana. | Completed |

### Bloque 5 - Resolucion de pendientes empiricos

| ID | Tarea | Tipo | Agente responsable | Dependencias | Criterios de aceptacion | Estado |
| --- | --- | --- | --- | --- | --- | --- |
| T-022 | Inventariar pendientes empiricos posteriores a T-021 y preparar su trazabilidad documental. | Documentation | Documentation Agent | T-021 | Pendientes empiricos identificados; no se promueve ninguna fuente no verificable; plan actualizado para resolverlos. | Completed |
| T-023 | Verificar URI, version y estado de la nota de Professional OS `[SDD] - SDD Modes` y del documento conceptual consensuado. | Documentation | Documentation Agent | T-022 | Cada fuente queda registrada como verificada con URI/version o mantenida como `PENDING - discovery-only` en `docs/context_refs.md`. | Completed |
| T-024 | Registrar repositorios concretos para VAL-001 a VAL-004 con fuente verificable. | Documentation | Documentation Agent | T-022; T-023 si aporta contexto | `docs/context_refs.md` identifica repositorio, URI, relacion con VAL-001..VAL-004, estado y fuente verificable; si no hay fuente, permanece `PENDING`. | Completed |
| T-025 | Revalidar empiricamente SDD Modes contra repositorios concretos registrados. | Validation | QA Gate Agent | T-024 | QA emite `PASS`, `PASS WITH CONDITIONS`, `FAIL` o `BLOCKED` sobre validacion empirica; no autoriza Development por si solo. | Completed |
| T-026 | Ajustar SPEC-001 solo si la validacion empirica detecta cambios normativos necesarios. | Specification | Specification Agent | T-025 | Cambios normativos aplicados o decision explicita de no modificar SPEC; sin arquitectura ni implementacion prematura. | Completed |
| T-027 | Propagar resultados empiricos a artefactos auxiliares y readiness si procede. | Documentation | Documentation Agent | T-025; T-026 si aplica | `docs/context_refs.md`, `docs/tasks.md` y `docs/sdd_readiness_assessment.md` reflejan el resultado empirico; README/glosario/instrucciones solo cambian si hay decision normativa. | Completed |

---

## 7. Dependencias criticas

- T-001 debe aclarar si las fuentes externas pendientes pasan a ser normativas o permanecen discovery-only.
- T-002 debe cerrar la terminologia antes de actualizar documentacion transversal.
- T-003 debe definir la semantica final antes de actualizar plantillas, instrucciones, agentes o gates.
- T-004 debe resolver donde vive la declaracion del modo antes de que la planificacion de implementacion sea fiable.
- T-007 y T-008 deben resolverse antes de actualizar guia de checks, evidencia y gates.
- T-010 debe identificar escenarios de validacion antes de que QA pueda validar la gobernanza proporcional.
- T-017 y T-018 deben completarse antes de preparar cualquier gate de entrada a Development.

---

## 8. Decisiones bloqueantes

| Decision | Impacto bloqueante | Representada por |
| --- | --- | --- |
| Semantica final de Minimal, Lite y Full | Bloquea actualizaciones normativas y validacion. | T-003 |
| Fuente canonica para declarar y justificar el modo | Bloquea routing documental y reglas de consumo por agentes. | T-004 |
| Dimensiones y reglas de seleccion | Bloquea guia de declaracion del modo y escenarios de validacion. | T-005 |
| Tratamiento de proyectos sin modo declarado | Bloquea compatibilidad hacia atras. | T-006 |
| Registro de checks ligeros | Bloquea guia de checks/gates y comportamiento Lite. | T-007 |
| Consolidacion de evidencia | Bloquea reglas de documentacion y validacion. | T-008 |
| `Implementation Wave` vs incremento gobernado | Bloquea lenguaje de unidad de trabajo en tareas, checks, gates y evidencia. | T-009 |
| Proyectos de validacion | Bloquea validacion basada en escenarios. | T-010 |
| Estado de fuentes externas | Bloquea si Professional OS y el documento conceptual consensuado pueden ser normativos. | T-001 |

---

## 9. Agentes responsables por bloque

| Bloque | Agentes principales |
| --- | --- |
| Cierre de decisiones | Specification Agent, Documentation Agent, QA Gate Agent |
| Actualizacion de artefactos Foundation | Specification Agent, Architect Agent, Documentation Agent |
| Revision y validacion | Reviewer Agent, QA Gate Agent, agentes responsables de correccion |
| Preparacion del gate de entrada a Development | Documentation Agent, QA Gate Agent |

---

## 10. Riesgos de planificacion

| Riesgo | Impacto | Mitigacion |
| --- | --- | --- |
| El trabajo de decision se expande hacia arquitectura o implementacion | Alto | Mantener T-001 a T-010 como decisiones normativas/documentales. |
| Las actualizaciones de artefactos empiezan antes de cerrar decisiones | Alto | Respetar dependencias de T-011 a T-016. |
| Se multiplican plantillas innecesarias | Medio | T-014 exige justificacion explicita para nuevas plantillas. |
| Lite queda demasiado debil o demasiado pesado | Alto | Validar con escenarios en T-018. |
| Full queda debilitado | Alto | T-003 y T-018 deben preservar equivalencia de Full. |
| Los repositorios existentes se degradan silenciosamente | Alto | T-006 debe definir tratamiento de modo no declarado. |

---

## 11. Criterios para estar listo para Reviewer y QA Gate

Este plan esta listo para Reviewer Agent y QA Gate Agent cuando:

- cada tarea tiene un objetivo claro;
- cada tarea tiene agente responsable;
- cada tarea tiene dependencias y criterios de aceptacion;
- todas las decisiones abiertas requeridas por `SPEC-001` estan representadas explicitamente;
- las tareas estan separadas en bloques de decision, actualizacion de artefactos, revision/validacion y preparacion de gate;
- ninguna tarea autoriza Development ni implementacion;
- el plan preserva el estado Specification / Structure;
- el plan puede evaluarse contra `docs/project_brief.md`, `docs/context_refs.md`, `specs/spec-001-sdd-modes.md` y `specs/capabilities/sdd-modes/arch-001-sdd-modes.md`.

---

## 12. Siguiente paso recomendado

La iniciativa queda cerrada documentalmente como mejora metodologica completada, sin transicion a Development.

T-027 propaga el resultado empirico a `docs/sdd_readiness_assessment.md`: Professional OS verificado como discovery-only, VAL-002/003/004 como candidatos retrospectivos formalmente `Undeclared`, VAL-001 `PENDING` como deuda empirica futura no bloqueante para cierre metodologico, sin cambios normativos adicionales.

Development sigue `NOT AUTHORIZED` sin aprobacion humana explicita. El punto de reentrada futuro es resolver VAL-001 mediante Documentation Agent y QA Gate Agent, registrando un repositorio Minimal verificable en `docs/context_refs.md`.

---

## 13. Registro de decisiones cerradas

| Tarea | Decision | Alcance | Estado |
| --- | --- | --- | --- |
| T-001 | En la verificacion inicial no habia URI, version ni ubicacion canonica verificable desde el repositorio para Professional OS `[SDD] - SDD Modes` ni para el documento conceptual consensuado sobre SDD Modes. Ambas referencias quedaron provisionalmente como `PENDING - discovery-only`. | Decision de contexto inicial. La nota de Professional OS se reevalua y verifica posteriormente en T-023; el documento conceptual consensuado permanece pendiente. | Completed |
| T-002 | El termino normativo para una configuracion de gobierno proporcional es `SDD Mode`. La capacidad se nombra en plural como `SDD Modes`. Los tres nombres oficiales permanecen en ingles: `SDD Minimal`, `SDD Lite` y `SDD Full`. `SDD Profile` y `Governance Mode` quedan descartados para esta capacidad inicial. | Decision terminologica. No define la semantica de Minimal, Lite o Full; esa decision corresponde a T-003. No selecciona la fuente canonica de declaracion del modo; esa decision corresponde a T-004. | Completed |
| T-003 | `SDD Minimal` es el modo para exploracion, pruebas internas o cambios documentales/acotados de bajo riesgo, sin datos sensibles, sin exposicion a produccion, sin obligaciones de cumplimiento, sin integraciones criticas y sin impacto operacional alto. `SDD Lite` es el modo proporcional para MVPs, herramientas internas o primeras versiones de riesgo controlado: reduce artefactos, revisiones y gates por microtarea, pero conserva justificacion humana, trazabilidad suficiente, checks ligeros, hitos de revision y escalado por riesgo. `SDD Full` es el modo completo y equivale al baseline vigente de gobierno de `jqf-sdd-foundation`: mantiene la profundidad documental, revisiones y gates formales actuales para proyectos criticos, productivos, sensibles, regulados, multiintegracion o de alto impacto. | Decision semantica. Minimal no puede usarse en contextos con datos sensibles, produccion, cumplimiento, integraciones criticas, impacto operacional alto, seguridad/privacy relevantes, multiples stakeholders criticos o baja reversibilidad. Lite no elimina SDD ni validacion humana. Full no queda debilitado y cualquier cambio al baseline requiere decision explicita y trazable. No decide fuente canonica de declaracion; corresponde a T-004. | Completed |
| T-004 | La fuente canonica inicial para declarar y justificar el `SDD Mode` de un proyecto es el `Project Brief`. La declaracion debe incluir modo seleccionado, justificacion humana, owner, fecha, condiciones relevantes de riesgo y disparadores de reevaluacion. `docs/context_refs.md` no es fuente normativa del modo: solo indexa y apunta a la fuente canonica vigente para carga de contexto. En cambios posteriores de modo, la decision canonica debe quedar en el artefacto de decision/gate aprobado que autorice el cambio, y `docs/context_refs.md` debe actualizarse para reflejar la fuente vigente. La specification o frontmatter pueden declarar modo a nivel de capability solo si una decision posterior define precedencia explicita. | Decision de declaracion y precedencia. Evita usar Context References como policy completa, conserva Project Brief como fuente inicial de alto nivel y permite cambios de ciclo de vida mediante decisiones/gates aprobados. No define reglas de seleccion; corresponde a T-005. | Completed |
| T-005 | La seleccion del `SDD Mode` debe evaluarse mediante juicio humano documentado sobre estas dimensiones: sensibilidad de datos, exposicion a produccion, obligaciones de cumplimiento, criticidad de integraciones, impacto operacional, complejidad tecnica/conceptual, numero y criticidad de stakeholders, reversibilidad del cambio, vida esperada del proyecto, auditabilidad requerida y madurez del contexto disponible. Regla de seleccion: cualquier dimension critica o no mitigada obliga a valorar `SDD Full`; riesgo controlado con alcance real de producto suele orientar a `SDD Lite`; solo bajo riesgo, baja exposicion, alta reversibilidad y ausencia de controles criticos permite `SDD Minimal`. La seleccion debe registrar evidencia y justificacion, pero no se calcula mediante puntuacion automatica. | Decision de seleccion. Los controles criticos por privacidad, seguridad, cumplimiento, produccion o integraciones prevalecen sobre el modo general. La ausencia de evidencia suficiente debe elevar prudencialmente el modo o bloquear la reduccion. No decide tratamiento de proyectos sin modo declarado; corresponde a T-006. | Completed |
| T-006 | Los proyectos sin `SDD Mode` declarado quedan temporalmente en estado `Undeclared`. `Undeclared` no es un cuarto modo y no autoriza reducir gobierno. Hasta que exista declaracion aprobada, se aplica el baseline conservador equivalente a `SDD Full` para decisiones de fase, cambios de alcance, riesgos criticos, gates y readiness. Los repositorios existentes no requieren migracion inmediata, pero cualquier cambio significativo debe incluir declaracion o decision explicita de mantener temporalmente `Undeclared` con justificacion. | Decision de compatibilidad. Evita downgrade silencioso y conserva compatibilidad hacia atras sin migracion automatica. La declaracion inicial o cambio posterior debe seguir la fuente canonica definida en T-004. No define checks ligeros; corresponde a T-007. | Completed |
| T-007 | Los checks ligeros se registran de forma consolidada dentro del artefacto de trabajo vigente del incremento o en la evidencia resumida del cambio, no como archivo independiente por microtarea. Cada check debe dejar como minimo: fecha o referencia temporal, alcance revisado, criterio verificado, resultado, responsable y enlace o referencia a evidencia cuando aplique. Un check ligero valida continuidad, coherencia o readiness parcial; no autoriza cambio de fase ni sustituye aprobacion humana. Un gate formal es una decision de avance, bloqueo o readiness que debe quedar registrada como artefacto o seccion formal cuando exista transicion de fase, cambio de alcance relevante, riesgo critico o preparacion para Development. | Decision checks/gates. Lite puede agrupar checks por hito o incremento para evitar revision formal por microtarea. Full conserva gates formales. Riesgos criticos pueden elevar un check a gate con independencia del modo. La consolidacion detallada de evidencia corresponde a T-008. | Completed |
| T-008 | La evidencia debe consolidarse en el artefacto de trabajo o decision que gobierna el incremento, hito o gate, con enlaces o referencias al historial Git cuando el detalle completo ya exista ahi. `SDD Minimal` requiere evidencia minima de decision, alcance y resultado suficiente para reconstruir por que el trabajo era bajo riesgo. `SDD Lite` requiere evidencia resumida por hito o incremento: checks agrupados, decisiones relevantes, riesgos nuevos, cambios de alcance y resultado de validacion. `SDD Full` mantiene evidencia completa equivalente al baseline actual, incluyendo revisiones y gates formales cuando correspondan. `docs/context_refs.md` sigue siendo indice de fuentes, no repositorio de evidencias. | Decision de evidencia. El historial Git puede ser evidencia de detalle tecnico o cronologico cuando esta referenciado desde un artefacto canonico; no sustituye decisiones normativas, justificaciones de modo, gates, riesgos criticos ni aprobaciones humanas. La unidad exacta de trabajo se cierra en T-009. | Completed |
| T-009 | La unidad normativa general es `incremento gobernado`. Un incremento gobernado es una unidad trazable de avance bajo SDD que agrupa alcance, decisiones, tareas, checks, evidencia y, cuando aplique, gates. `Implementation Wave` queda reservado como etiqueta opcional para incrementos de ejecucion dentro de Development, pero no como concepto normativo principal de SDD Modes. Los modos regulan la intensidad documental y de validacion aplicada a cada incremento gobernado. | Decision de unidad de trabajo. El concepto funciona antes de Development y evita asumir implementacion prematura. Las tareas, checks, gates y evidencia deben poder referirse a incrementos gobernados. No autoriza Development. | Completed |
| T-010 | Se seleccionan cuatro escenarios de validacion para SDD Modes: VAL-001, experimento o utilidad interna de bajo riesgo candidato a `SDD Minimal`; VAL-002, MVP o primera version con exposicion limitada candidato a `SDD Lite`; VAL-003, proyecto productivo, sensible, regulado o con integraciones criticas candidato a `SDD Full`; VAL-004, repositorio derivado existente sin `SDD Mode` declarado para validar `Undeclared` y compatibilidad hacia atras. No hay repositorios concretos verificables desde este repo para asignar a cada escenario; `vca-ai` y `aif-foundation` aparecen solo como ejemplos de repositorios derivados que no deben reestructurarse, no como seleccion validada. | Decision de validacion. Los escenarios quedan seleccionados; los proyectos/repos concretos permanecen `PENDING` hasta que se registren fuentes de contexto verificables antes de T-018. La validacion no modifica proyectos derivados ni autoriza Development. | Completed |
| T-019 | Los hallazgos de QA quedan resueltos o diferidos justificadamente: la spec define medicion cualitativa de reduccion documental, evidencia para demostrar que `SDD Full` no se debilita y diferimiento de repositorios concretos hasta fuentes verificables. | Decision normativa posterior a validacion. No cierra validacion empirica sobre repos derivados ni autoriza Development. | Completed |
| T-019D | Documentation Agent propaga T-019 a artefactos auxiliares: `docs/context_refs.md` actualiza el impacto del pendiente de repositorios y `.github/instructions/sdd.instructions.md` incorpora reglas operativas sobre reduccion documental y evidencia de no debilitamiento de Full. | Propagacion documental. No aparecen repositorios/fuentes verificables nuevos; README y glosario no requieren cambios adicionales. | Completed |
| T-020 | Paquete de readiness preparado en `docs/sdd_readiness_assessment.md`. La decision es `Partially Ready` para evaluacion de QA Gate; repositorios concretos y fuentes externas pendientes siguen registrados como `PENDING`. | Preparacion documental de gate. No autoriza Development ni cierra validacion empirica completa sobre repos derivados. | Completed |
| T-021 | QA Gate emite `PASS WITH CONDITIONS` sobre el paquete de readiness. Development queda `NOT AUTHORIZED` sin aprobacion humana explicita; repositorios concretos y fuentes externas siguen pendientes. | Decision de gate. Cierra T-021 pero no autoriza transicion de fase por si sola. | Completed |
| T-023 | La nota de Professional OS `[SDD] - SDD Modes` queda verificada en Notion con URI estable, creada el 2026-07-05T18:14:52.857Z y estado `Procesado`; permanece como fuente de descubrimiento no normativa. El documento conceptual consensuado sigue sin URI/version verificable y permanece `PENDING - discovery-only`. | Decision de contexto. Cierra T-023; habilita T-024 para registrar repositorios concretos de validacion empirica. | Completed |
| T-024 | Se registran repositorios verificables anteriores a SDD Modes como candidatos retrospectivos: `joquifer_system_agents` para contrastar VAL-002, `bigquery_mcp_server` y `neovaultech-system` para contrastar VAL-003, y `aif-foundation` para contrastar VAL-004. Todos mantienen estado formal `Undeclared` porque no declaran `SDD Mode`. VAL-001 permanece sin repositorio concreto verificable. | Decision empirica/documental. `docs/context_refs.md` queda actualizado con remotos Git, rutas locales cuando existen, fuente Professional OS para `neovaultech-system`, estado formal `Undeclared` y rol de validacion retrospectiva. Habilita T-025 como validacion empirica parcial; no cierra validacion completa de Minimal. | Completed |
| T-025 | QA Gate emite `PASS WITH CONDITIONS` sobre la validacion empirica retrospectiva. Todos los repositorios candidatos son formalmente `Undeclared` por ser anteriores a SDD Modes; `joquifer_system_agents` sirve para contrastar criterios de Lite, `bigquery_mcp_server` y `neovaultech-system` sirven para contrastar criterios de Full, y `aif-foundation` sirve para validar compatibilidad conservadora de repositorios existentes sin modo declarado. VAL-001 sigue sin repositorio concreto verificable. | Decision QA. La capacidad es empiricamente plausible para clasificacion retrospectiva de Lite, Full y Undeclared, pero no queda completa para Minimal. No autoriza Development. Siguiente paso: T-026 para decidir si hay ajuste normativo en SPEC-001 o solo condicion documental pendiente. | Completed |
| T-026 | Specification Agent determina que T-025 no exige cambiar la semantica normativa de Minimal, Lite, Full ni Undeclared. Se actualiza `SPEC-001` solo para reflejar el nuevo estado empirico: Professional OS verificado como discovery-only, candidatos retrospectivos VAL-002/003/004 formalmente `Undeclared`, y VAL-001 pendiente. | Decision specification. No introduce arquitectura ni implementacion; no autoriza Development. Habilita T-027 para propagacion documental auxiliar y readiness si procede. | Completed |
| T-027 | Documentation Agent propaga T-026 a artefactos auxiliares: `docs/sdd_readiness_assessment.md` refleja Professional OS verificado, candidatos retrospectivos VAL-002/003/004 formalmente `Undeclared`, VAL-001 pendiente y Development `NOT AUTHORIZED`. README, glosario e instrucciones no cambian porque no hubo decision normativa nueva. | Propagacion documental. Cierra el bloque empirico a nivel documental auxiliar; queda pendiente revision/QA si se requiere confirmacion final. | Completed |
| CIERRE | Decision humana posterior a T-027: se acepta que VAL-001 permanezca PENDING; la ausencia de repositorio real verificable para SDD Minimal no bloquea el cierre metodologico de SDD Modes; VAL-001 queda como deuda de validacion empirica futura. Esta aceptacion no permite debilitar requisitos normativos, controles criticos ni evidencia minima de SDD Minimal. SPEC-001 y ARCH-001 pasan a estado Final. | Decision de cierre metodologico. Cierra SDD Modes sin transicion a Development; Development permanece NOT AUTHORIZED. | Completed |
---

## 14. Baseline final canonico

| Artefacto | Estado final | Funcion |
| --- | --- | --- |
| `docs/project_brief.md` | Completed | Declaracion inicial canonica de la iniciativa y del modo `SDD Full` usado para desarrollarla. |
| `specs/spec-001-sdd-modes.md` | Final | Fuente normativa principal de SDD Modes. |
| `specs/capabilities/sdd-modes/arch-001-sdd-modes.md` | Final | Arquitectura conceptual y documental aprobada. |
| `.github/instructions/sdd.instructions.md` | Current | Reglas operativas vigentes para aplicar SDD Modes dentro del SDD Harness. |
| `.github/agents/*.agent.md` y `.codex/agents/` | Current | Agentes metodologicos y adaptadores que consumen el modo declarado sin duplicarse por modo. |
| `docs/templates/` y `specs/templates/` | Current | Plantillas actualizadas para registrar o referenciar modo cuando aplica. |
| `README.md` y `docs/glosario_terminos.md` | Current | Documentacion de alto nivel y terminologia aprobada. |
| `docs/context_refs.md` | Current | Indice de contexto, fuentes y pendientes futuros. |
| `docs/sdd_readiness_assessment.md` | Completed with conditions | Evidencia de readiness y cierre metodologico sin Development. |

## 15. Punto de reentrada futuro

Si se identifica un repositorio verificable de bajo riesgo para `VAL-001`, la reentrada valida es:

1. Documentation Agent registra la fuente en `docs/context_refs.md`.
2. QA Gate Agent valida si el repositorio cierra la deuda empirica de SDD Minimal.
3. Specification Agent solo interviene si la evidencia exige cambiar la semantica normativa aprobada.
4. Development permanece fuera de alcance salvo decision humana explicita posterior.
