# Plan de tareas - SDD Technical State Persistence & Publication

## Metadata

| Campo | Valor |
| --- | --- |
| Plan ID | TASKPLAN-001 |
| Capacidad | SDD Technical State Persistence & Publication |
| Specification relacionada | `specs/capabilities/technical-state-persistence-and-publication/spec-001-technical-state-persistence-and-publication.md` |
| Architecture relacionada | `specs/capabilities/technical-state-persistence-and-publication/arch-001-technical-state-persistence-and-publication.md` |
| Estado | Draft |
| Fase SDD actual | Tasks Planning |
| SDD Mode | `Undeclared` — baseline conservador equivalente a `SDD Full` |
| Owner | Jordi Quiroga |
| Creado por | Tasks Planner Agent |
| Última actualización | 2026-09-22 |

---

## 1. Objetivo

Transformar SPEC-001 y ARCH-001 en el plan mínimo, trazable y verificable necesario para evaluar Development Readiness.

El plan no autoriza Development. Su objetivo es concretar qué superficies necesitan realmente modificación y evitar convertir la lista de impactos potenciales de Architecture en cambios obligatorios.

---

## 2. Artefactos fuente

| Artefacto | Rol |
| --- | --- |
| SPEC-001 | Define estados, requisitos, reglas, límites y criterios de aceptación. |
| ARCH-001 | Selecciona `Instructions-first + existing agents` y define decision points y frontera de autorización. |
| `.github/instructions/sdd.instructions.md` | Superficie normativa transversal propuesta. |
| `.github/agents/implementation.agent.md` | Superficie principal candidata para aplicación durante ejecución. |
| `.codex/agents/implementation.toml` | Adaptador que ya conserva autorización explícita para commit/push/publicación. |
| `.github/agents/reviewer.agent.md` | Candidato condicional para checks de coherencia/recuperabilidad. |
| `.github/agents/qa-gate.agent.md` | Candidato condicional para gates donde recuperabilidad sea material. |
| `.github/agents/consolidation.agent.md` | Candidato condicional para baseline, evidencia y reentrada. |
| `docs/glosario_terminos.md` | Superficie terminológica transversal. |

---

## 3. Reglas de planificación

- Aplicar cambio mínimo y proporcional.
- No crear contract, policy standalone, skill, runtime, workflow ejecutable ni GitHub Workflow Agent.
- No modificar un agente solo porque aparezca como candidato en Architecture.
- La policy completa debe tener una única fuente normativa en `sdd.instructions.md`; los agentes solo incorporan responsabilidad específica cuando sea necesaria.
- No modificar JQF Project Initializer antes de estabilizar Foundation y evaluar compatibilidad downstream.
- No introducir branching, PR, release, CI/CD, convenciones de commit ni automatización.
- Ninguna tarea de este plan autoriza commit/push automático ni elimina la autorización explícita existente.
- Development permanece `NOT AUTHORIZED` hasta Review, Development Readiness Gate y decisión humana aplicable.

---

## 4. Bloques de trabajo

1. Determinar impacto mínimo real.
2. Preparar cambios Foundation.
3. Validar semántica y comportamiento documental.
4. Evaluar downstream compatibility.
5. Review y Development Readiness.

---

## 5. Tareas

| ID | Tarea | Tipo | Responsable | Dependencias | Criterio de aceptación | Estado |
| --- | --- | --- | --- | --- | --- | --- |
| T-001 | Realizar impact check final de las superficies candidatas de ARCH-001 y clasificar cada una como `required`, `conditional` o `no-change`. | Planning / Review | Tasks Planner + Reviewer | SPEC-001; ARCH-001 | Existe una lista mínima justificada; ningún archivo se incluye por defecto. | Completed |
| T-002 | Definir el delta exacto de la sección normativa que deberá incorporarse a `.github/instructions/sdd.instructions.md`. | Documentation prep | Documentation Agent | T-001 | El delta cubre State Model, Persistence Decision Point, Publication Decision Point, routing híbrido, PCD y Authorization Boundary sin duplicar SPEC/ARCH. | Completed |
| T-003 | Definir el delta terminológico de `docs/glosario_terminos.md`. | Documentation prep | Documentation Agent | T-001 | Solo se incorporan conceptos estabilizados necesarios para comprensión transversal. | Completed |
| T-004 | Definir el delta mínimo del Implementation Agent y su adaptador Codex, solo si T-001 confirma necesidad. | Development prep | Tasks Planner / Documentation | T-001; T-002 | Queda especificado cómo aplicar `should persist/publish` frente a `may execute`, preservando autorización explícita y sin duplicar policy. | Completed |
| T-005 | Definir deltas de Reviewer, QA Gate y Consolidation únicamente para las superficies clasificadas `required` por T-001. | Development prep | Tasks Planner / Documentation | T-001; T-002 | Cada delta tiene una necesidad verificable; superficies innecesarias quedan explícitamente `no-change`. | Completed |
| T-006 | Preparar casos de validación documentales de la policy. | Validation prep | QA Gate Agent | T-002 a T-005 | Casos cubren al menos: working state no listo; validated increment candidato a commit; commit local suficiente; necesidad de push por handoff remoto; prohibición de publicación prematura; checkpoint ya suficiente sin commit redundante. | Completed |
| T-007 | Verificar trazabilidad SPEC → ARCH → delta propuesto → casos de validación. | Review | Reviewer Agent | T-002 a T-006 | Todos los FR/BR/AC materiales tienen cobertura y no aparece alcance nuevo. | Completed |
| T-008 | Preparar el paquete de Development Readiness con el conjunto exacto de archivos a modificar, validaciones y exclusiones. | Governance | Documentation Agent | T-007 | El paquete permite decidir Development sin diseñar arquitectura adicional y declara explícitamente `NOT AUTHORIZED` hasta gate/decisión. | Completed |
| T-009 | Evaluar Development Readiness. | Validation | QA Gate Agent | T-008 | Resultado `Pass`, `Pass with minor conditions`, `Fail — changes required` o `Blocked`; no equivale por sí solo a ejecución. | Completed — PASS |
| T-010 | Decidir autorización humana de Development si T-009 lo permite. | Governance | Jordi Quiroga | T-009 | Existe decisión explícita de autorizar o no Development y queda acotado el incremento autorizado. | Planned |
| T-011 | Implementar el incremento Foundation autorizado. | Development | Implementation Agent | T-010 | Solo se modifican superficies autorizadas; no se materializa GitHub Workflow Agent ni automatización; autorización de commit/push permanece separada. | Not authorized |
| T-012 | Validar el incremento implementado contra los casos de T-006 y SPEC/ARCH. | Validation | QA Gate Agent | T-011 | Casos aplicables pasan y no se detecta regresión metodológica ni sobreingeniería. | Not authorized |
| T-013 | Evaluar impacto downstream sobre proyectos derivados y JQF Project Initializer. | Validation / Governance | Reviewer + QA | T-012 | Impacto clasificado como `sin impacto`, `requiere validación de compatibilidad` o `requiere adaptación`; no se modifica Initializer sin nueva autorización. | Not authorized |
| T-014 | Preparar Review/Consolidation y cierre de la capability. | Review / Governance | Reviewer + Consolidation | T-012; T-013 | Baseline, evidencia, deuda residual y reentrada quedan identificados; cualquier trabajo downstream se separa de esta capability cuando corresponda. | Not authorized |

---

## 6. Orden recomendado

```text
T-001
  ↓
T-002 + T-003
  ↓
T-004 + T-005
  ↓
T-006
  ↓
T-007
  ↓
T-008
  ↓
T-009
  ↓
T-010  [human authorization]
  ↓
T-011 → T-012 → T-013 → T-014
```

T-002 y T-003 pueden prepararse en paralelo después de T-001. T-004 y T-005 solo se preparan para superficies cuya necesidad haya quedado demostrada.

---

## 7. T-001 — Impact check final

T-001 queda completada mediante revisión directa de las superficies candidatas contra SPEC-001, ARCH-001 y sus responsabilidades vigentes.

| Surface | Classification | Finding |
| --- | --- | --- |
| `.github/instructions/sdd.instructions.md` | `required` | Es la fuente normativa transversal seleccionada por ARCH-001 y actualmente no contiene criterios de commit/checkpoint, push/synchronization ni estado remoto recuperable. |
| `docs/glosario_terminos.md` | `required` | Define `incremento gobernado` y evidencia Git, pero no los cuatro estados de persistencia ni la separación commit/push. |
| `.github/agents/implementation.agent.md` | `required` | Ejecuta cambios concretos pero no contiene el decision model de persistencia/publicación; necesita una responsabilidad mínima que remita a la policy canónica. |
| `.codex/agents/implementation.toml` | `no-change` | Ya preserva la frontera crítica: no hacer commit, push o publicación sin autorización explícita. La semántica nueva puede cargarse desde instructions/Implementation Agent sin duplicarla aquí. |
| `.github/agents/reviewer.agent.md` | `no-change` | Su responsabilidad transversal de coherencia, trazabilidad, contradicciones y deuda documental es suficiente; puede revisar la policy canónica sin regla Git específica. |
| `.github/agents/qa-gate.agent.md` | `no-change` | Sus criterios generales ya permiten exigir evidencia suficiente, trazabilidad y coherencia cuando la recuperabilidad sea material. Añadir reglas específicas duplicaría la policy. |
| `.github/agents/consolidation.agent.md` | `no-change` | Ya gobierna baseline, evidencia, deuda residual y reentrada. El estado remoto puede consumirse como evidencia conforme a la policy sin ampliar responsabilidades. |
| `.github/agents/tasks-planner.agent.md` | `no-change` | Puede planificar checkpoints/handoffs desde instrucciones transversales; no ejecuta Git. |
| `.github/agents/documentation.agent.md` | `no-change` | Ya mantiene glosarios, instrucciones y coherencia documental; no necesita responsabilidad Git propia. |
| GitHub Workflow Agent | `no-change` | Permanece planeado; no existe evidencia que justifique materialización. |
| JQF Project Initializer | `downstream-only` | Debe evaluarse después de estabilizar Foundation; no se adapta preventivamente. |

### Resultado de alcance mínimo

El Development candidate scope queda reducido a **tres superficies Foundation**:

1. `.github/instructions/sdd.instructions.md`;
2. `docs/glosario_terminos.md`;
3. `.github/agents/implementation.agent.md`.

No se identifica necesidad actual de modificar adaptador Codex, Reviewer, QA Gate, Consolidation, Tasks Planner, Documentation Agent ni de materializar GitHub Workflow Agent.

Este resultado no autoriza Development. T-002 a T-005 deben definir los deltas documentales exactos y T-009/T-010 siguen siendo necesarios antes de cualquier implementación.

---

## 8. T-002 / T-003 — Deltas normativos preparados

Estos deltas son **proposal-only**. Definen el contenido mínimo del futuro Development y no modifican todavía las superficies objetivo.

### T-002 — Delta de `.github/instructions/sdd.instructions.md`

Añadir una única sección transversal, preferentemente después de `SDD Modes` y antes de `Backlog Governance`, con esta semántica mínima:

#### Technical State Persistence & Publication

- Principio: **persistir por significado y publicar por necesidad de recuperabilidad/sincronización; nunca por frecuencia temporal ni por número de cambios**.
- Aplicar la policy sobre la unidad normativa `incremento gobernado`.
- Distinguir:
  - `Working State`: trabajo en curso que puede permanecer local;
  - `Validated Increment`: incremento coherente y suficientemente validado para fase, riesgo y SDD Mode;
  - `Committed Checkpoint`: Validated Increment persistido en Git;
  - `Remotely Recoverable State`: checkpoint publicado y recuperable por consumidores remotos autorizados.
- Evaluar persistencia cuando se complete una unidad coherente, antes de iniciar una unidad materialmente distinta o en un gate/handoff/transición donde la recuperabilidad sea relevante.
- No crear commits redundantes cuando el estado ya esté suficientemente persistido.
- Evaluar push de forma independiente al commit.
- Considerar push cuando otra superficie o participante necesite recuperar el estado remoto para supervisión, handoff, colaboración o continuación del trabajo.
- En routing híbrido, si ChatGPT u otra superficie depende del repositorio remoto, la vigencia del estado remoto forma parte explícita de la decisión de publicación.
- No publicar trabajo incoherente o insuficientemente validado solo para hacerlo observable.
- `commit ≠ push ≠ PR ≠ release`.
- SDD Minimal/Lite/Full comparten la misma policy; el modo solo ajusta proporcionalmente intensidad y evidencia.
- La conclusión metodológica `procede commit/push` **no equivale** a autorización para ejecutarlo. Deben respetarse las autorizaciones vigentes de la superficie/agente.
- No introducir branching strategy, PR workflow, releases, CI/CD, convenciones de mensajes ni automatización.

No copiar FR/BR/AC completos de SPEC-001 ni las alternativas de ARCH-001.

### T-003 — Delta de `docs/glosario_terminos.md`

Añadir únicamente cinco entradas conceptuales:

**Working State**  
Estado técnico en curso de un incremento gobernado. Puede permanecer local y no constituye por sí mismo un checkpoint recuperable.

**Validated Increment**  
Incremento gobernado suficientemente coherente y validado para su fase, riesgo y SDD Mode como para evaluar su persistencia. No implica automáticamente commit.

**Committed Checkpoint**  
Estado técnico de un Validated Increment persistido mediante Git porque aporta valor de recuperabilidad o trazabilidad. No implica automáticamente push, PR ni release.

**Remotely Recoverable State**  
Committed Checkpoint publicado en el repositorio remoto y razonablemente recuperable por otra superficie o participante autorizado. No sustituye ni presume el Working State local posterior.

**Technical State Persistence & Publication**  
Política SDD transversal que gobierna cuándo evaluar la persistencia de un incremento validado y cuándo evaluar su publicación remota. Se rige por significado, recuperabilidad y sincronización, no por cadencia temporal. Mantiene separadas la procedencia metodológica y la autorización de ejecución.

No añadir entradas separadas para `commit`, `push`, `PR` o `release`: son conceptos Git generales y hacerlo ampliaría innecesariamente el glosario.

### Resultado

T-002 y T-003 dejan cerrado el núcleo normativo previsto sin crear una nueva source of truth. La futura implementación deberá mantener `sdd.instructions.md` como fuente operativa transversal y el glosario como definición terminológica, evitando duplicación.

---

## 9. T-004 / T-005 — Deltas de agentes cerrados

Estos resultados permanecen **proposal-only** y no modifican todavía agentes ni adaptadores.

### T-004 — Implementation Agent

`.github/agents/implementation.agent.md` requiere un único delta mínimo: incorporar, dentro de sus reglas de ejecución, la responsabilidad de consultar y aplicar la sección canónica `Technical State Persistence & Publication` de `.github/instructions/sdd.instructions.md`.

La semántica necesaria es:

- al completar un incremento gobernado suficientemente validado, evaluar si procede un `Committed Checkpoint`;
- antes de un handoff, transición material o dependencia remota, evaluar de forma separada si procede `Push / Synchronization`;
- evitar commit o push redundante cuando el estado ya sea suficiente;
- no convertir observabilidad remota en motivo para persistir/publicar trabajo no validado;
- distinguir siempre:
  - `should persist / should publish` — conclusión metodológica;
  - `may commit / may push` — autorización de ejecución;
- si la acción procede metodológicamente pero no está autorizada, detener la ejecución Git y reportar la necesidad de autorización.

El agente **no debe duplicar** State Model, reglas completas ni criterios de SPEC-001. Debe remitir a la policy transversal.

### T-004 — Codex adapter

`.codex/agents/implementation.toml` queda confirmado como **`no-change`**.

Motivo: ya establece la restricción crítica de no hacer commit, push o publicación sin autorización explícita. Añadir aquí la nueva policy duplicaría la fuente normativa y aumentaría riesgo de divergencia. El adaptador debe seguir delegando el comportamiento metodológico en las instrucciones/agente canónicos.

### T-005 — Agentes condicionales

Tras contrastar responsabilidades vigentes con la policy propuesta:

| Surface | Final decision | Rationale |
| --- | --- | --- |
| `.github/agents/reviewer.agent.md` | `no-change` | Ya revisa coherencia, trazabilidad, contradicciones y riesgos. Puede evaluar cumplimiento de una instrucción transversal sin regla Git propia. |
| `.github/agents/qa-gate.agent.md` | `no-change` | Ya evalúa evidencia, trazabilidad, readiness y suficiencia para transición. La recuperabilidad solo es relevante cuando el contexto/gate la exige. |
| `.github/agents/consolidation.agent.md` | `no-change` | Ya clasifica baseline, evidencia, deuda y reentrada. Puede consumir checkpoints/estado remoto como evidencia conforme a instructions. |
| `.github/agents/tasks-planner.agent.md` | `no-change` | La policy transversal es suficiente para planificar handoffs/checkpoints cuando tengan valor. |
| `.github/agents/documentation.agent.md` | `no-change` | Sus responsabilidades actuales cubren mantenimiento de instructions/glosario sin semántica Git específica. |

### Development scope estabilizado

Si Development Readiness posterior es favorable y existe autorización humana, el incremento previsto queda limitado a:

1. `.github/instructions/sdd.instructions.md`;
2. `docs/glosario_terminos.md`;
3. `.github/agents/implementation.agent.md`.

No se prevé modificación de ningún otro agente o adaptador en este incremento.

---

## 10. Casos mínimos de validación previstos

| Caso | Estado esperado |
| --- | --- |
| Trabajo incoherente/no suficientemente validado | `Working State`; no commit candidate. |
| Incremento coherente y validado con valor de recuperabilidad | `checkpoint-candidate`. |
| Checkpoint válido sin consumidor remoto ni handoff | `local-checkpoint-sufficient`. |
| Handoff a ChatGPT dependiente de GitHub | `remote-sync-candidate` si el checkpoint relevante no está publicado. |
| Handoff remoto con trabajo aún no validado | No crear/publicar checkpoint prematuro. |
| Gate con checkpoint ya suficiente y sincronizado | `already-persisted` / `already-synchronized`; no commit/push redundante. |
| Commit/push metodológicamente procedente pero no autorizado | No ejecutar; reportar necesidad de autorización. |

---

## 11. T-006 — Casos de validación preparados

Los siguientes escenarios son documentales y reutilizables en Validation posterior. No ejecutan operaciones Git.

| ID | Scenario | Preconditions | Expected methodological decision | Authorization expectation |
| --- | --- | --- | --- | --- |
| VAL-001 | Working State no validado | Trabajo parcial, checks pendientes o unidad todavía incoherente. | Mantener `Working State`; no crear checkpoint ni publicar. | No aplica. |
| VAL-002 | Validated Increment con valor de recuperabilidad | Unidad coherente, checks suficientes y cambio significativo completado. | `checkpoint-candidate`. | Commit solo si la superficie está autorizada. |
| VAL-003 | Checkpoint local suficiente | Existe Committed Checkpoint; no hay handoff, consumidor remoto ni necesidad material de sincronización. | `local-checkpoint-sufficient`; no push por defecto. | No solicitar push innecesario. |
| VAL-004 | Handoff a consumidor remoto | Existe checkpoint válido y ChatGPT/u otra superficie necesita recuperar el estado desde GitHub. | `remote-sync-candidate`. | Push solo si está autorizado; en caso contrario reportar necesidad. |
| VAL-005 | Observabilidad remota con trabajo prematuro | Otra superficie necesita visibilidad, pero el trabajo sigue incoherente/no suficientemente validado. | No crear/publicar checkpoint prematuro. | La necesidad de observabilidad no eleva autorización ni readiness. |
| VAL-006 | Estado ya persistido y sincronizado | El checkpoint relevante ya representa el incremento y está publicado. | `already-persisted` / `already-synchronized`; no commit/push redundante. | No aplica nueva autorización. |
| VAL-007 | Procedencia sin autorización | La policy determina que commit y/o push aportaría valor, pero el agente/superficie carece de autorización explícita. | Reportar `checkpoint-candidate` o `remote-sync-candidate` sin ejecutar. | Debe solicitar/esperar autorización. |
| VAL-008 | Gate sin necesidad de nueva persistencia | Gate relevante alcanzado, pero no existe nuevo estado material desde el último checkpoint suficiente. | El gate actúa como punto de evaluación, no como trigger automático de commit/push. | No aplica. |
| VAL-009 | SDD Mode proporcional | Mismo patrón de estado bajo Minimal, Lite y Full, con distinta intensidad de checks/evidencia. | Misma semántica de persistencia/publicación; cambia solo proporcionalidad de validación/evidencia. | Mantener controles y autorización aplicables. |
| VAL-010 | Commit no implica PR/release | Incremento válido requiere checkpoint y quizá push, pero no existe decisión de PR o release. | Persistencia/publicación puede completarse sin inferir PR/release. | PR/release requieren su gobierno propio. |

### Pass criteria

La futura implementación pasa esta validación si:

- los diez escenarios producen el resultado esperado sin reglas ad hoc;
- ningún escenario convierte commit en push automático;
- ningún gate obliga por sí mismo a crear commit;
- ningún consumidor remoto fuerza publicación de trabajo no validado;
- la ausencia de autorización bloquea ejecución Git sin perder la recomendación metodológica;
- los tres SDD Modes comparten la misma policy;
- no se introduce dependencia de GitHub Workflow Agent, contract adicional o automatización.

---

## 12. T-007 — Traceability Review

**Decision: PASS.**

La revisión `SPEC → ARCH → deltas → validation scenarios` no identifica requisitos materiales sin cobertura ni ampliación de alcance.

| Requirement group | Architecture / delta coverage | Validation coverage | Result |
| --- | --- | --- | --- |
| FR-001 / AC-001 / AC-009 — estados diferenciados | State Model + delta instructions/glossary | VAL-001, VAL-002, VAL-003, VAL-004, VAL-006 | PASS |
| FR-002 / BR-003 / AC-002 — commit semántico | Persistence Decision Point + instructions | VAL-001, VAL-002, VAL-008 | PASS |
| FR-003 — separación de unidades | Instructions: evaluar antes de unidad materialmente distinta | VAL-002, VAL-008 | PASS |
| FR-004 / BR-002 / BR-004 / AC-003 — commit/push independientes | Publication Decision Point | VAL-003, VAL-004, VAL-010 | PASS |
| FR-005 / FR-006 / AC-004 — sincronización y routing híbrido | Hybrid Routing Interface + instructions | VAL-004 | PASS |
| FR-007 / AC-005 — no publicación prematura | Policy + Implementation delta | VAL-005 | PASS |
| FR-008 / AC-007 — gates como evaluación, no trigger | Instructions | VAL-006, VAL-008 | PASS |
| FR-009 / AC-006 — proporcionalidad SDD Modes | SDD Mode Interface | VAL-009 | PASS |
| FR-010 / AC-008 — autorización separada | Authorization Boundary + Implementation delta | VAL-007 | PASS |
| FR-011 — trazabilidad de checkpoint | Governed Increment Interface + instructions | VAL-002, VAL-006 | PASS |
| FR-012 — recuperabilidad remota | Publication Decision Point + Hybrid Routing | VAL-004, VAL-006 | PASS |
| FR-013 / AC-010 — downstream impact | Downstream Compatibility Check + T-013 | Post-Development validation prevista | PASS — deferred by design |
| BR-001 / AC-011 — simplicidad/PCD | Alternative A + T-001 scope reduction | VAL-003, VAL-006, VAL-008 | PASS |
| BR-005 — working state local | State Model | VAL-001, VAL-005 | PASS |
| BR-006 — no estrategia Git general | Architecture exclusions + deltas | VAL-010 + pass criteria | PASS |

### Review findings

- No existe gap funcional o metodológico bloqueante.
- No aparece branching, PR workflow, release, CI/CD, automatización o GitHub Workflow Agent.
- El scope sigue limitado a tres superficies.
- FR-013 se valida necesariamente después de estabilizar Foundation; su diferimiento a T-013 es coherente y no bloquea Development Readiness.
- La autorización de ejecución permanece independiente.
- Los casos VAL-001..VAL-010 son suficientes para validar el incremento previsto.

### Minor documentary finding

El propio task plan conserva numeración repetida de secciones (`## 8` y `## 9`) derivada de las ampliaciones incrementales y el apartado final `Siguiente paso` todavía referencia T-001. Es una inconsistencia editorial sin impacto normativo. Debe normalizarse al preparar T-008 para que el paquete de readiness sea limpio, sin crear una tarea adicional.

---

## 13. Riesgos de planificación

- Convertir candidatos condicionales en cambios obligatorios.
- Duplicar la policy entre instrucciones y agentes.
- Confundir readiness con autorización de ejecución.
- Introducir un agente/skill Git sin evidencia.
- Hacer del gate una obligación automática de push.
- Mezclar adaptación de Initializer con el incremento Foundation.

Mitigación transversal: T-001 debe reducir el scope antes de Development Readiness.

---

## 14. Siguiente paso

T-010 — decisión humana de autorización de Development. Development permanece `NOT AUTHORIZED` hasta autorización explícita.
