# Architecture

## Metadata

### Architecture ID

ARCH-001

### Related Spec

SPEC-001 - SDD Technical State Persistence & Publication

### Title

SDD Technical State Persistence & Publication — Conceptual Architecture

### Status

Approved

### Owner

Jordi Quiroga

### Last Updated

2026-09-22

### SDD Mode Reference

`Undeclared`. Conforme a la Specification aprobada y a `.github/instructions/sdd.instructions.md`, se aplica temporalmente un baseline conservador equivalente a `SDD Full`.

### Template

No existe una plantilla oficial de arquitectura To-Be en el repositorio. Este artefacto utiliza una estructura inferida de `.github/agents/architect.agent.md` y de arquitecturas canónicas existentes.

---

## 1. Solution Summary

La solución propuesta introduce una política transversal mínima de persistencia y publicación del estado técnico dentro del SDD Harness existente.

No crea un subsistema Git, runtime, workflow ejecutable, agente nuevo ni skill nueva. La política se integra inicialmente mediante reglas normativas en las instrucciones SDD existentes y mediante la adaptación mínima de los agentes metodológicos que ya intervienen en la evaluación, ejecución y cierre de incrementos.

Flujo conceptual:

```text
Working State
    ↓ validación suficiente para fase/modo/riesgo
Validated Increment
    ↓ decisión de persistencia
Committed Checkpoint
    ↓ necesidad de recuperabilidad/sincronización + autorización
Remotely Recoverable State
```

Principio arquitectónico:

> La Foundation define una única política transversal; los agentes existentes la aplican dentro de sus responsabilidades. No se introduce una capa nueva salvo que evidencia posterior demuestre que es necesaria.

---

## 2. Architectural Objective

Hacer operativos los criterios de SPEC-001 con el mínimo cambio estructural posible, de forma que:

- cualquier incremento gobernado pueda evaluar si procede persistir un checkpoint;
- commit y push permanezcan como decisiones independientes;
- la necesidad de sincronización remota sea explícita en routing híbrido;
- los SDD Modes modulen proporcionalmente la intensidad sin crear políticas Git diferentes;
- la procedencia metodológica permanezca separada de la autorización de ejecución;
- Reviewer, QA y Consolidation puedan verificar que el estado técnico relevante es recuperable;
- JQF Project Initializer pueda heredar la política sin incorporar lógica específica salvo que la validación downstream demuestre lo contrario.

---

## 3. Specification Decisions Reflected

| Specification decision | Architectural reflection |
| --- | --- |
| Persistencia por significado | La política se ancla en `incremento gobernado` y `Validated Increment`, no en cadencias. |
| Commit y push son decisiones distintas | Se definen dos decision points separados. |
| Routing híbrido requiere observabilidad remota | `Remote Dependency Check` forma parte de la decisión de publicación. |
| No publicación prematura | Solo un incremento suficientemente validado puede convertirse en checkpoint candidato. |
| SDD Modes modulan proporcionalidad | Una única policy se aplica con intensidad proporcional, sin variantes por modo. |
| Autorización separada | La policy puede indicar `procede`, pero la ejecución continúa sometida a autorización vigente. |
| PCD / simplicidad | Se reutilizan instrucciones y agentes existentes; no se crea componente ejecutable nuevo. |
| Downstream impact | Initializer se trata como consumidor de Foundation y se valida después de estabilizar el cambio. |

---

## 4. Main Components

| Component | Responsibility | Target surface |
| --- | --- | --- |
| Technical State Persistence & Publication Policy | Fuente normativa transversal de criterios de persistencia/publicación. | `.github/instructions/sdd.instructions.md` |
| State Model | Define Working State, Validated Increment, Committed Checkpoint y Remotely Recoverable State. | Instrucciones + glosario |
| Persistence Decision Point | Determina si un Validated Increment merece checkpoint. | Agentes metodológicos aplicables |
| Publication Decision Point | Determina si un checkpoint necesita sincronización remota. | Agentes metodológicos aplicables |
| Authorization Boundary | Separa procedencia metodológica de permiso de ejecución. | Instrucciones + agentes/adaptadores |
| Verification Interface | Permite a Reviewer/QA/Consolidation comprobar recuperabilidad y trazabilidad. | Agentes existentes |
| Downstream Compatibility Check | Clasifica impacto en Initializer/proyectos derivados. | Validación posterior antes de cierre |

No se crea un archivo policy standalone en la primera solución: la regla es transversal al SDD Harness y cabe de forma compacta en las instrucciones canónicas existentes. Si durante Development esta integración resultara excesivamente densa, deberá volver a Architecture antes de introducir un contract o artefacto nuevo.

---

## 5. Component Responsibilities

### 5.1 Technical State Persistence & Publication Policy

Debe expresar de forma compacta:

- persistir por significado, no por frecuencia;
- evaluar checkpoint al cerrar una unidad coherente suficientemente validada;
- evaluar checkpoint antes de iniciar una unidad materialmente distinta;
- evaluar persistencia/publicación en gates, cierres y transiciones materiales;
- no crear checkpoints redundantes cuando el estado ya esté adecuadamente persistido;
- evaluar push de forma independiente;
- publicar cuando exista necesidad material de recuperabilidad/sincronización;
- considerar explícitamente consumidores remotos en routing híbrido;
- no publicar trabajo prematuro;
- respetar autorización explícita de ejecución.

### 5.2 State Model

Taxonomía mínima:

| State | Meaning |
| --- | --- |
| Working State | Trabajo en curso; puede permanecer local. |
| Validated Increment | Incremento gobernado coherente y suficientemente validado para su fase/modo/riesgo. |
| Committed Checkpoint | Validated Increment persistido en Git. |
| Remotely Recoverable State | Checkpoint publicado y recuperable por consumidores remotos autorizados. |

El modelo no sustituye estados SDD de lifecycle. Describe únicamente el grado de persistencia técnica de un incremento.

### 5.3 Persistence Decision Point

Pregunta normativa:

> ¿Existe una unidad coherente y suficientemente validada cuyo valor de recuperabilidad/trazabilidad justifica persistencia?

Se evalúa especialmente:

- al completar una unidad coherente;
- antes de iniciar una unidad materialmente distinta;
- en gates y transiciones relevantes;
- antes de handoffs cuando el estado deba quedar recuperable.

Resultado conceptual:

- `not-ready`: continúa Working State;
- `checkpoint-candidate`: procede checkpoint cuando exista autorización;
- `already-persisted`: no se añade checkpoint redundante.

No se introduce scoring.

### 5.4 Publication Decision Point

Pregunta normativa:

> ¿Necesita este checkpoint estar disponible remotamente ahora?

Se consideran:

- recuperación por otra superficie;
- handoff;
- supervisión/evaluación remota;
- colaboración;
- transición metodológica material;
- protección razonable frente a pérdida de estado local cuando sea relevante.

Resultado conceptual:

- `local-checkpoint-sufficient`;
- `remote-sync-candidate`;
- `already-synchronized`.

No todo commit implica push.

### 5.5 Authorization Boundary

La arquitectura mantiene dos capas:

```text
Methodological decision: should persist / should publish?
                    ↓
Authorization decision: may this surface execute it now?
```

La primera pertenece a esta capability. La segunda permanece gobernada por instrucciones, agente, gate y autorización humana aplicables.

La Architecture no elimina la restricción actual de `.codex/agents/implementation.toml`: no realizar commit, push o publicación sin autorización explícita.

### 5.6 Verification Interface

Reviewer Agent debe poder detectar:

- checkpoint incoherente con el incremento;
- divergencia relevante entre estado descrito y estado remoto;
- handoff que presupone sincronización inexistente;
- checkpoints/publicaciones redundantes que contradigan PCD.

QA Gate Agent debe poder comprobar, cuando sea relevante para un gate:

- si el incremento requerido está suficientemente persistido;
- si el consumidor de la siguiente fase depende de estado remoto;
- si la evidencia citada es recuperable.

Consolidation Agent debe poder identificar:

- último checkpoint relevante;
- estado remoto recuperable;
- deuda de sincronización, si se acepta explícitamente;
- punto de reentrada.

Estas verificaciones no obligan a crear nuevos artefactos por microtarea.

### 5.7 Downstream Compatibility Check

Antes del cierre de la capability:

1. verificar que un proyecto derivado que hereda Foundation recibe la política;
2. verificar si JQF Project Initializer copia/transforma las superficies afectadas;
3. clasificar impacto:
   - `sin impacto`;
   - `requiere validación de compatibilidad`;
   - `requiere adaptación`;
4. abrir trabajo en Initializer solo si existe delta real.

---

## 6. Relationships and Interfaces

### 6.1 Governed Increment Interface

```text
incremento gobernado
  → trabajo
  → checks / validación exigible
  → Validated Increment
  → Persistence Decision Point
  → [Committed Checkpoint]
  → Publication Decision Point
  → [Remotely Recoverable State]
```

Los corchetes indican que el estado posterior es condicional, no obligatorio en cada incremento.

### 6.2 SDD Mode Interface

Existe una única policy.

- `SDD Minimal`: aplicación ligera, evitando checkpoints/gates adicionales salvo valor real.
- `SDD Lite`: checkpoints alineados con hitos significativos y necesidades de handoff/sincronización.
- `SDD Full`: mayor exigencia de trazabilidad y recuperabilidad en gates/transiciones relevantes.

El modo ajusta intensidad, no cambia la semántica.

### 6.3 Hybrid Routing Interface

```text
Local execution surface
   ↓ validated work
Commit/checkpoint
   ↓ remote dependency?
Push/synchronization
   ↓
GitHub remote
   ↓
ChatGPT / remote reviewer / next surface
```

Un consumidor remoto debe distinguir entre estado local declarado y estado efectivamente publicado.

### 6.4 Agent Interface

| Agent | Architectural responsibility |
| --- | --- |
| Specification Agent | Define requisitos; no ejecuta persistencia. |
| Architect Agent | Define impacto estructural; no ejecuta persistencia. |
| Tasks Planner Agent | Puede identificar checkpoints/handoffs relevantes en planificación sin imponer commit por tarea. |
| Reviewer Agent | Revisa coherencia, recuperabilidad y redundancia. |
| Documentation Agent | Mantiene terminología/referencias cuando esté autorizado. |
| QA Gate Agent | Evalúa suficiencia de persistencia/publicación cuando sea condición real del gate. |
| Implementation Agent | Ejecuta cambios y, solo con autorización, commit/push conforme a la policy. |
| Consolidation Agent | Registra baseline, evidencia y reentrada apoyándose en checkpoints publicados cuando corresponda. |
| GitHub Workflow Agent | Permanece planeado; no es necesario para la primera implementación de esta capability. |

---

## 7. Dependencies

- SPEC-001 — SDD Technical State Persistence & Publication.
- `.github/instructions/sdd.instructions.md`.
- SDD Modes y `incremento gobernado`.
- agentes metodológicos existentes.
- adaptadores Codex que contengan restricciones de commit/push.
- glosario transversal.
- JQF Project Initializer para validación downstream posterior.

---

## 8. Alternatives Considered

### Alternative A — Instructions-first + existing agents

Integrar la policy en `.github/instructions/sdd.instructions.md`, actualizar solo agentes/adaptadores que necesiten consumirla y añadir taxonomía al glosario.

**Advantages**

- mínimo cambio;
- reutiliza superficies canónicas;
- baja carga de mantenimiento;
- compatible con PCD;
- no introduce runtime ni artefactos adicionales.

**Disadvantages**

- requiere disciplina para mantener consistencia entre instrucciones y agentes;
- la policy no tiene un archivo standalone.

**Risk**

- duplicación textual si Development replica la policy completa en cada agente.

### Alternative B — Dedicated transversal contract/policy file

Crear un artefacto canónico específico y hacer que instrucciones/agentes lo referencien.

**Advantages**

- fuente normativa dedicada;
- reduce potencial duplicación.

**Disadvantages**

- introduce una nueva superficie documental y routing;
- aumenta carga de contexto;
- la evidencia actual no demuestra que sea necesaria.

**Risk**

- sobrearquitectura para una policy compacta.

### Alternative C — GitHub Workflow Agent + skill

Materializar el agente planeado y una skill para aplicar la policy.

**Advantages**

- encapsulación explícita de operaciones Git;
- potencial automatización futura.

**Disadvantages**

- amplía notablemente alcance;
- entra en Development;
- puede duplicar responsabilidades del Implementation Agent;
- no existe evidencia de necesidad.

**Risk**

- construir mecanismo antes de validar la política manual.

---

## 9. Architectural Decision

### AD-001 — Select Alternative A: Instructions-first + existing agents

Se propone **Alternative A**.

Rationale:

- satisface todos los FR/BR de SPEC-001;
- minimiza nuevas superficies;
- respeta PCD;
- conserva el catálogo actual de agentes;
- permite validar la política antes de especializar herramientas;
- mantiene reversible una futura evolución hacia un contract o GitHub Workflow Agent si aparece evidencia.

### AD-002 — No standalone policy artifact initially

La primera implementación no crea contract/policy standalone. La fuente transversal será una sección canónica compacta dentro de `.github/instructions/sdd.instructions.md`, respaldada por SPEC-001 y ARCH-001.

### AD-003 — No GitHub Workflow Agent materialization

`SDD-AGENT-009` permanece planeado. Su materialización requiere evidencia posterior y ciclo SDD propio o ampliación explícita autorizada.

### AD-004 — Existing-agent adaptation must be minimal

Development deberá modificar únicamente los agentes/adaptadores cuya responsabilidad necesite conocer o aplicar la policy. No se copia la policy completa en cada agente; se referencia la fuente canónica y se añaden responsabilidades específicas.

### AD-005 — No automatic commit/push authorization

La policy nunca transforma una recomendación metodológica en permiso automático. La autorización de ejecución permanece separada.

### AD-006 — Downstream validation before closure

JQF Project Initializer se evalúa después de estabilizar los cambios Foundation y antes del cierre. No se modifica preventivamente.

---

## 10. Expected Development Impact

Impacto previsto, sujeto a Tasks/Readiness:

| Surface | Expected impact |
| --- | --- |
| `.github/instructions/sdd.instructions.md` | Añadir policy transversal compacta. |
| `docs/glosario_terminos.md` | Añadir taxonomía de estados de persistencia. |
| `.github/agents/implementation.agent.md` | Añadir aplicación de decision points y separación should/may. |
| `.codex/agents/implementation.toml` | Ajuste mínimo para cargar/aplicar policy sin eliminar autorización explícita. |
| `.github/agents/reviewer.agent.md` | Añadir checks de coherencia/recuperabilidad cuando apliquen. |
| `.github/agents/qa-gate.agent.md` | Añadir criterio condicional de estado recuperable cuando sea necesario para transición. |
| `.github/agents/consolidation.agent.md` | Añadir lectura del checkpoint/estado remoto relevante para baseline/reentry. |
| Tasks Planner / Documentation Agent | Solo si Review/Tasks demuestra necesidad; no se presupone cambio. |
| GitHub Workflow Agent | Sin cambio. |
| JQF Project Initializer | Solo evaluación downstream inicialmente. |

La tabla es una previsión arquitectónica, no autorización de Development.

---

## 11. Technical and Methodological Risks

| Risk | Impact | Mitigation |
| --- | --- | --- |
| Duplicar policy entre agentes | Medio | Fuente canónica en instructions; agentes solo añaden responsabilidad específica. |
| Convertir gate en obligación de push | Alto | Publication Decision Point es condicional. |
| Confundir `Validated Increment` con cierre de fase | Medio | Definirlo relativo a fase/modo/riesgo. |
| Aumentar burocracia | Alto | No crear artefactos/checkpoints sin valor material. |
| Diluir autorización explícita | Alto | Authorization Boundary obligatoria. |
| Estado remoto usado como verdad absoluta | Medio | Definirlo como estado publicado recuperable, no como sustituto del working state local. |
| Sobreextender GitHub Workflow Agent | Alto | Mantenerlo planeado y fuera de Development actual. |
| Romper Initializer | Medio | Validación downstream antes de cierre. |

---

## 12. Impact on Existing Architecture

La solución extiende el SDD Harness existente sin crear un subsistema nuevo.

Impacto conceptual:

- `incremento gobernado` gana una dimensión explícita de persistencia técnica;
- Git pasa de ser solo evidencia/historial implícito a tener estados de recuperabilidad definidos;
- routing híbrido puede razonar explícitamente sobre si el estado remoto es suficientemente reciente;
- agentes existentes reciben responsabilidades acotadas;
- no cambia el lifecycle SDD, los SDD Modes, la estrategia de branches, PRs, releases o CI/CD.

No se modifica ningún artefacto cerrado durante Architecture.

---

## 13. Architecture Acceptance Criteria

### AAC-001

La arquitectura implementa los cuatro estados de SPEC-001 sin crear estados de lifecycle SDD alternativos.

### AAC-002

Commit y push tienen decision points independientes.

### AAC-003

La solución no requiere GitHub Workflow Agent, runtime, workflow ejecutable ni automatización.

### AAC-004

Existe una única fuente normativa transversal propuesta y los agentes no necesitan duplicar la policy completa.

### AAC-005

La autorización de ejecución permanece separada de la recomendación metodológica.

### AAC-006

SDD Modes modula intensidad sin crear policies diferentes.

### AAC-007

Routing híbrido puede determinar si necesita un Remotely Recoverable State.

### AAC-008

La solución no introduce checkpoints, artefactos o gates sin valor material.

### AAC-009

Existe ruta explícita para evaluar JQF Project Initializer antes del cierre.

### AAC-010

Existe suficiente detalle para que Tasks Planner pueda preparar un plan sin diseñar arquitectura adicional.

---

## 14. Open Questions

No existen preguntas abiertas bloqueantes para Review.

La lista exacta de archivos de agentes/adaptadores a modificar debe validarse durante Review/Tasks contra necesidad real, aplicando el principio de cambio mínimo.

---

## 15. Next Step

Reviewer Agent debe evaluar ARCH-001 contra SPEC-001, PCD, arquitectura existente y límites de fase.

Development permanece **NOT AUTHORIZED**.
