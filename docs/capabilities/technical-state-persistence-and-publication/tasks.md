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
| T-001 | Realizar impact check final de las superficies candidatas de ARCH-001 y clasificar cada una como `required`, `conditional` o `no-change`. | Planning / Review | Tasks Planner + Reviewer | SPEC-001; ARCH-001 | Existe una lista mínima justificada; ningún archivo se incluye por defecto. | Planned |
| T-002 | Definir el delta exacto de la sección normativa que deberá incorporarse a `.github/instructions/sdd.instructions.md`. | Documentation prep | Documentation Agent | T-001 | El delta cubre State Model, Persistence Decision Point, Publication Decision Point, routing híbrido, PCD y Authorization Boundary sin duplicar SPEC/ARCH. | Planned |
| T-003 | Definir el delta terminológico de `docs/glosario_terminos.md`. | Documentation prep | Documentation Agent | T-001 | Solo se incorporan conceptos estabilizados necesarios para comprensión transversal. | Planned |
| T-004 | Definir el delta mínimo del Implementation Agent y su adaptador Codex, solo si T-001 confirma necesidad. | Development prep | Tasks Planner / Documentation | T-001; T-002 | Queda especificado cómo aplicar `should persist/publish` frente a `may execute`, preservando autorización explícita y sin duplicar policy. | Planned |
| T-005 | Definir deltas de Reviewer, QA Gate y Consolidation únicamente para las superficies clasificadas `required` por T-001. | Development prep | Tasks Planner / Documentation | T-001; T-002 | Cada delta tiene una necesidad verificable; superficies innecesarias quedan explícitamente `no-change`. | Planned |
| T-006 | Preparar casos de validación documentales de la policy. | Validation prep | QA Gate Agent | T-002 a T-005 | Casos cubren al menos: working state no listo; validated increment candidato a commit; commit local suficiente; necesidad de push por handoff remoto; prohibición de publicación prematura; checkpoint ya suficiente sin commit redundante. | Planned |
| T-007 | Verificar trazabilidad SPEC → ARCH → delta propuesto → casos de validación. | Review | Reviewer Agent | T-002 a T-006 | Todos los FR/BR/AC materiales tienen cobertura y no aparece alcance nuevo. | Planned |
| T-008 | Preparar el paquete de Development Readiness con el conjunto exacto de archivos a modificar, validaciones y exclusiones. | Governance | Documentation Agent | T-007 | El paquete permite decidir Development sin diseñar arquitectura adicional y declara explícitamente `NOT AUTHORIZED` hasta gate/decisión. | Planned |
| T-009 | Evaluar Development Readiness. | Validation | QA Gate Agent | T-008 | Resultado `Pass`, `Pass with minor conditions`, `Fail — changes required` o `Blocked`; no equivale por sí solo a ejecución. | Planned |
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

## 7. Development candidate surfaces

Esta tabla no autoriza cambios; es el punto de partida para T-001.

| Surface | Initial classification | Reason |
| --- | --- | --- |
| `.github/instructions/sdd.instructions.md` | Required candidate | Fuente normativa transversal seleccionada por ARCH-001. |
| `docs/glosario_terminos.md` | Required candidate | Taxonomía transversal estabilizada. |
| `.github/agents/implementation.agent.md` | Required candidate | Principal superficie de ejecución del decision model. |
| `.codex/agents/implementation.toml` | Conditional | Ya prohíbe commit/push/publicación sin autorización; puede bastar con la definición canónica. |
| `.github/agents/reviewer.agent.md` | Conditional | Solo si los checks actuales no cubren coherencia/recuperabilidad. |
| `.github/agents/qa-gate.agent.md` | Conditional | Solo si los criterios actuales no permiten evaluar recuperabilidad cuando sea material. |
| `.github/agents/consolidation.agent.md` | Conditional | Solo si baseline/reentry no puede identificar adecuadamente estado publicado con reglas existentes. |
| Tasks Planner Agent | No-change candidate | No necesita aplicar operaciones Git; puede planificar con la policy transversal. |
| Documentation Agent | No-change candidate | Puede mantener documentación usando instrucciones existentes. |
| GitHub Workflow Agent | No change | Permanece planeado. |
| JQF Project Initializer | Downstream-only | Evaluar después de Foundation; no adaptar preventivamente. |

---

## 8. Casos mínimos de validación previstos

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

## 9. Riesgos de planificación

- Convertir candidatos condicionales en cambios obligatorios.
- Duplicar la policy entre instrucciones y agentes.
- Confundir readiness con autorización de ejecución.
- Introducir un agente/skill Git sin evidencia.
- Hacer del gate una obligación automática de push.
- Mezclar adaptación de Initializer con el incremento Foundation.

Mitigación transversal: T-001 debe reducir el scope antes de Development Readiness.

---

## 10. Siguiente paso

Ejecutar T-001 como impact check documental. Development permanece `NOT AUTHORIZED`.
