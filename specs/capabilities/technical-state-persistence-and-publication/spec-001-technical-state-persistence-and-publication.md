# Specification

## Metadata

### Spec ID

SPEC-001

### Title

SDD Technical State Persistence & Publication

### Status

Approved

### Owner

Jordi Quiroga

### Last Updated

2026-09-22

---

## 1. Purpose

Definir cuándo el estado técnico de un proyecto gobernado por SDD debe persistirse como checkpoint Git y cuándo debe publicarse en el repositorio remoto para convertirse en un estado recuperable y sincronizable.

La capacidad debe resolver esta necesidad con el mínimo gobierno adicional necesario, preservando el principio de simplicidad y proporcionalidad del PCD.

---

## 2. Background

La Foundation ya gobierna el `incremento gobernado`, validaciones, checks, gates, evidencia, consolidación y baselines. Sin embargo, no establece criterios transversales suficientes para decidir cuándo corresponde crear un `commit` ni cuándo corresponde realizar `push`.

Esta ausencia puede producir checkpoints demasiado frecuentes, acumulación excesiva de cambios o divergencia entre el estado técnico local real y el estado remoto que otras superficies utilizan para recuperar contexto, supervisar el proyecto o continuar un handoff.

El problema es especialmente relevante en routing híbrido, donde una secuencia habitual puede ser:

`VS Code/Codex → trabajo → validación → commit → push → GitHub → ChatGPT`

La capacidad debe gobernar esta secuencia sin convertir SDD en una estrategia Git general.

---

## 3. Objective

Permitir determinar, para cualquier incremento gobernado:

1. si el estado de trabajo es suficientemente coherente y validado para persistirse;
2. si procede crear un commit/checkpoint;
3. si ese checkpoint necesita estar disponible remotamente;
4. si procede push/sincronización.

Principio rector:

> Persistir por significado; publicar por necesidad de recuperabilidad y sincronización, no por frecuencia temporal ni por número de cambios.

---

## 4. Scope

### Included

- Working State.
- Validated Increment.
- Commit / Checkpoint.
- Push / Synchronization.
- Remotely Recoverable State.
- Relación con `incremento gobernado`.
- Proporcionalidad según SDD Mode.
- Routing híbrido y dependencia de estado remoto.
- Evaluación de persistencia/publicación en gates, handoffs y transiciones relevantes.
- Preservación de autorización humana o explícita aplicable.
- Evaluación de impacto sobre proyectos derivados y JQF Project Initializer.

### Excluded

- Branching strategy.
- Convenciones o formato de mensajes de commit.
- Pull Request workflow.
- Releases y versionado.
- CI/CD.
- Sintaxis o comandos Git.
- Automatización Git.
- Materialización del GitHub Workflow Agent.
- Arquitectura o selección de mecanismos concretos de enforcement.

---

## 5. Core Concepts

### Working State

Trabajo en curso que todavía puede permanecer local y no constituye necesariamente un checkpoint recuperable.

### Validated Increment

`Incremento gobernado` suficientemente coherente y validado para su estado y fase como para poder evaluarse como candidato a persistencia.

### Commit / Checkpoint

Persistencia Git de una unidad coherente de estado técnico con significado metodológico suficiente para ser recuperada.

### Push / Synchronization

Publicación de uno o más checkpoints al repositorio remoto cuando existe necesidad material de recuperabilidad, sincronización, colaboración, supervisión, handoff o transición.

### Remotely Recoverable State

Estado técnico publicado que otra superficie o participante puede recuperar razonablemente como representación vigente del checkpoint relevante.

---

## 6. Functional Requirements

### FR-001 — Estados diferenciados

La metodología debe distinguir al menos `Working State`, `Validated Increment`, `Committed Checkpoint` y `Remotely Recoverable State`.

### FR-002 — Commit semántico

La decisión de commit debe basarse en que exista una unidad coherente de trabajo suficientemente validada, no en tiempo transcurrido, número de archivos o cantidad de cambios.

### FR-003 — Separación de unidades

Antes de comenzar una unidad materialmente distinta debe evaluarse si el incremento validado anterior constituye un checkpoint candidato.

### FR-004 — Push independiente

Commit y push deben tratarse como decisiones diferentes. Un commit local no implica automáticamente publicación.

### FR-005 — Criterio de sincronización

Debe evaluarse push cuando un checkpoint necesite estar disponible remotamente por recuperabilidad, colaboración, supervisión, handoff, transición metodológica o necesidad de otra superficie.

### FR-006 — Routing híbrido

Cuando ChatGPT u otra superficie dependa del repositorio remoto para recuperar o evaluar el estado técnico, la necesidad de mantener un estado remoto suficientemente actualizado debe formar parte explícita de la decisión de push.

### FR-007 — No publicación prematura

La necesidad de supervisión o handoff no debe justificar por sí sola commits o pushes de trabajo incoherente, no validado o prematuro.

### FR-008 — Gates y transiciones

Gates, cierres de incremento, cambios de fase y otros hitos materiales deben actuar como puntos obligatorios de evaluación de persistencia/publicación, sin exigir necesariamente un nuevo commit si el estado adecuado ya está persistido.

### FR-009 — Proporcionalidad SDD Mode

Existirá una única estrategia de persistencia y publicación. `SDD Minimal`, `SDD Lite` y `SDD Full` podrán modular proporcionalmente su aplicación según riesgo, complejidad y necesidad de trazabilidad, sin crear políticas Git distintas por modo ni añadir checkpoints o publicaciones que no aporten valor.

### FR-010 — Autorización

Que commit o push sean metodológicamente procedentes no equivale a autorizar su ejecución. Deben mantenerse las reglas vigentes de autorización humana o explícita aplicables a la superficie que actúa.

### FR-011 — Trazabilidad

Un checkpoint relevante debe poder relacionarse con el incremento, artefacto, tarea, gate o decisión que representa cuando corresponda.

### FR-012 — Recuperabilidad remota

La metodología debe permitir determinar si el estado remoto es suficientemente reciente para utilizarlo como evidencia del estado técnico publicado.

### FR-013 — Downstream impact

Todo cambio transversal derivado de esta capability debe evaluar su impacto sobre proyectos derivados y sobre JQF Project Initializer antes de considerarse cerrado, distinguiendo entre `sin impacto`, `requiere validación de compatibilidad` y `requiere adaptación`.

---

## 7. Business Rules

### BR-001 — Simplicidad y proporcionalidad

La estrategia debe introducir el mínimo gobierno adicional necesario para garantizar trazabilidad y recuperabilidad. No debe crear checkpoints, publicaciones, artefactos, gates ni pasos adicionales cuando el estado existente ya sea suficiente para cumplir esos objetivos.

### BR-002 — Separación semántica

`commit ≠ push ≠ PR ≠ release`. Cada mecanismo conserva significado y decisión propios.

### BR-003 — Persistencia por significado

No debe imponerse una frecuencia temporal, número de cambios, número de archivos ni cadencia artificial para crear commits.

### BR-004 — Publicación por necesidad

No todo commit requiere push inmediato. La publicación debe responder a una necesidad material de recuperabilidad o sincronización.

### BR-005 — Estado de trabajo local

El trabajo en curso puede permanecer local mientras no exista un checkpoint suficientemente validado o una necesidad metodológicamente válida de publicación.

### BR-006 — No sobreingeniería

La capacidad no debe introducir una estrategia Git general ni ampliar su alcance hacia branching, PR, releases, CI/CD o automatización salvo evolución posterior expresamente justificada.

---

## 8. Constraints

- La capability define semántica y criterios, no arquitectura de implementación.
- No se materializa el GitHub Workflow Agent en esta fase.
- No se modifica JQF Project Initializer en esta fase.
- No se modifica automáticamente ningún proyecto derivado.
- La capacidad debe reutilizar `incremento gobernado` como unidad normativa existente.
- La aplicación debe respetar SDD Modes y los controles críticos vigentes.
- La ejecución efectiva de commit o push debe respetar las autorizaciones aplicables.

---

## 9. Risks

| Risk | Impact | Mitigation |
| --- | --- | --- |
| Convertir la capacidad en una estrategia Git completa | Alto | Mantener explícitamente el alcance excluido. |
| Crear commits excesivos por microtarea | Medio | Basar persistencia en significado y coherencia del incremento. |
| Acumular demasiado trabajo sin checkpoint | Medio | Evaluar persistencia antes de unidades materialmente distintas y en hitos relevantes. |
| Confundir commit con push | Alto | Mantener decisiones independientes. |
| Publicar trabajo prematuro para facilitar supervisión | Medio | Exigir coherencia y validación suficientes antes del checkpoint. |
| Estado remoto desactualizado en routing híbrido | Alto | Incorporar dependencia remota a la decisión de sincronización. |
| Añadir burocracia SDD | Alto | BR-001 obliga a mínimo gobierno adicional. |
| Romper derivaciones existentes | Medio | Evaluar downstream impact antes del cierre. |

---

## 10. Acceptance Criteria

### AC-001

La metodología permite clasificar un estado como `Working State`, `Validated Increment`, `Committed Checkpoint` o `Remotely Recoverable State`.

### AC-002

Un incremento coherente y suficientemente validado puede evaluarse objetivamente como candidato a commit sin utilizar frecuencia temporal ni cantidad de cambios como criterio principal.

### AC-003

Un checkpoint ya comprometido puede evaluarse de forma independiente como candidato a push.

### AC-004

Un handoff o evaluación híbrida que dependa del repositorio remoto no puede asumir estado sincronizado si el checkpoint relevante no está publicado.

### AC-005

La necesidad de observabilidad remota no obliga a persistir o publicar trabajo incoherente o insuficientemente validado.

### AC-006

Los tres SDD Modes pueden aplicar la misma estrategia con proporcionalidad distinta sin crear políticas Git separadas.

### AC-007

La capability no exige un commit por artefacto, microtarea o gate cuando el estado existente ya proporciona trazabilidad y recuperabilidad suficientes.

### AC-008

La procedencia metodológica de commit o push permanece separada de la autorización para ejecutarlos.

### AC-009

La Specification permite distinguir `estado local actual ≠ último checkpoint ≠ estado remoto recuperable`.

### AC-010

Antes del cierre de la capability se evalúa el impacto sobre proyectos derivados y JQF Project Initializer como `sin impacto`, `requiere validación de compatibilidad` o `requiere adaptación`.

### AC-011

La solución resultante no introduce artefactos, gates ni pasos adicionales que no aporten trazabilidad o recuperabilidad material.

---

## 11. Dependencies

- `.github/instructions/sdd.instructions.md`
- Capability `SDD Modes`.
- Concepto normativo `incremento gobernado`.
- Reglas vigentes de autorización humana y de agentes.
- JQF Project Initializer como consumidor downstream potencial.

---

## 12. Open Questions

No existen preguntas abiertas bloqueantes para iniciar Architecture.

La decisión sobre qué artefacto, instrucción, agente, skill o combinación mínima aplicará estas reglas pertenece a Architecture y no se resuelve en esta Specification.

---

## 13. Future Considerations

- Evaluar el papel del GitHub Workflow Agent una vez exista Architecture aprobada.
- Evaluar si algún mecanismo de automatización aporta valor después de validar primero la política manual.
- Evaluar cambios en JQF Project Initializer únicamente si el análisis downstream demuestra una adaptación necesaria.

---

## Definition of Done

La Specification está completa cuando:

- el problema y objetivo están definidos;
- los conceptos de estado están diferenciados;
- los criterios de commit y push están separados;
- la proporcionalidad y simplicidad están protegidas;
- los límites evitan convertir la capability en una estrategia Git general;
- existen criterios de aceptación verificables;
- el impacto downstream queda exigido antes del cierre;
- existe aprobación humana de la Specification.

## Human Validation

- Specification approved by Jordi Quiroga on 2026-09-22.
