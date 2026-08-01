# Referencias de contexto - Consolidation Agent

> Este documento indexa el contexto utilizado para la capacidad `Consolidation Agent`.
>
> No sustituye el baseline cerrado de capacidades previas ni autoriza crear el agente real.

---

# 1. Identidad del Proyecto

```yaml
proyecto:
  nombre: JQF SDD Foundation - Consolidation Agent
  id_proyecto: consolidation-agent
  tipo_proyecto: foundation-methodological-agent-specification
  estado: Architecture
  fecha_creacion: 2026-08-01
  responsable: Jordi Quiroga

cliente:
  id_cliente: N/A
  nombre_cliente: N/A
  estado_relacion: N/A

sdd_mode:
  modo_declarado: SDD Full
  fuente_canonica: docs/capabilities/consolidation-agent/project_brief.md
  estado: Verificado
  ultima_revision: 2026-08-01
```

---

## SDD Mode

| Campo | Valor |
| --- | --- |
| Modo indexado | `SDD Full` |
| Fuente canonica | `docs/capabilities/consolidation-agent/project_brief.md` |
| Estado de verificacion | Verificado |
| Ultima revision | 2026-08-01 |
| Notas | La capacidad define un futuro agente metodologico del SDD Harness. |

---

# 2. Contexto de Cliente Requerido

```yaml
ccd:
  requerido: false
  fuente_humana:
    sistema: N/A
    ubicacion: N/A
  fuente_runtime_ia:
    sistema: N/A
    uri: N/A
  version: N/A
  estado: N/A
  ultima_revision: N/A
  fecha_consulta: 2026-08-01
```

Esta iniciativa pertenece a la Foundation y no a un cliente derivado.

---

# 3. Decisiones Relacionadas

| Fecha | Decision | Impacto en este proyecto | Fuente |
| --- | --- | --- | --- |
| 2026-08-01 | `SDD Project Consolidation and Closure` queda `Closed` | Proporciona el proceso que el futuro agente debera ejecutar metodologicamente | `docs/capabilities/project-consolidation-and-closure/closure_handover.md`; `specs/capabilities/project-consolidation-and-closure/spec-001-sdd-project-consolidation-and-closure.md` |
| 2026-08-01 | `Foundation Derivation and Project Initialization` queda `Closed` | Confirma que existen multiples capacidades cerradas y necesidad de gobierno de baseline | `docs/capabilities/foundation-derivation-and-project-initialization/closure_handover.md` |
| 2026-08-01 | `SDD Full` para esta capacidad | Mantiene trazabilidad completa antes de definir el primer agente metodologico futuro | `docs/capabilities/consolidation-agent/project_brief.md` |

## Decisiones pendientes de validar

| Tema | Motivo de la duda | Responsable | Estado |
| --- | --- | --- | --- |
| Crear definicion canonica del agente | Requiere decision humana posterior y fase/capacidad autorizada | Jordi Quiroga / fase futura | PENDIENTE |
| Crear adaptador Codex | Depende de definicion canonica aprobada | Jordi Quiroga / Documentation Agent | PENDIENTE |
| Automatizar checks de consolidacion | Seria Development o tooling futuro | Jordi Quiroga / Implementation Agent | PENDIENTE |

---

# 4. Proyectos Relacionados

| Proyecto | Relacion con este proyecto | Estado | Fuente |
| --- | --- | --- | --- |
| `SDD Modes` | Baseline metodologico de modos y controles por intensidad | Closed baseline | `specs/spec-001-sdd-modes.md`; `specs/spec-001-sdd-modes.architecture.md` |
| `SDD Project Consolidation and Closure` | Define el proceso que el agente debe aplicar | Closed | `docs/capabilities/project-consolidation-and-closure/closure_handover.md`; `specs/capabilities/project-consolidation-and-closure/spec-001-sdd-project-consolidation-and-closure.md`; `specs/capabilities/project-consolidation-and-closure/arch-001-sdd-project-consolidation-and-closure.md` |
| `Foundation Derivation and Project Initialization` | Baseline cerrado relacionado con derivacion y futuras capacidades | Closed | `docs/capabilities/foundation-derivation-and-project-initialization/closure_handover.md`; `specs/capabilities/foundation-derivation-and-project-initialization/spec-001-foundation-derivation-and-project-initialization.md` |

---

# 5. Conocimiento Reutilizable Relacionado

| Recurso | Tipo | Motivo de uso | Fuente |
| --- | --- | --- | --- |
| `.github/instructions/sdd.instructions.md` | Instrucciones SDD | Define fases, restricciones, Consolidation, Closed y agentes actuales | Verificado en repositorio |
| `AGENTS.md` | Catalogo metodologico | Confirma agentes vigentes y que `Consolidation Agent` todavia no existe | Verificado en repositorio |
| `.github/agents/specification.agent.md` | Definicion canonica de agente | Rigio la creacion de SPEC-001 | Verificado en repositorio |
| `.github/agents/architect.agent.md` | Definicion canonica de agente | Rige la creacion de ARCH-001 | Verificado en repositorio |
| `docs/templates/project_brief.template.md` | Template | Base estructural del Brief de proyecto | Verificado en repositorio |
| `docs/templates/context_refs.template.md` | Template | Base estructural de referencias de contexto | Verificado en repositorio |
| `docs/templates/sdd_readiness_assessment.template.md` | Template | Base estructural del readiness inicial | Verificado en repositorio |
| `specs/templates/spec.template.md` | Template | Base estructural de SPEC-001 | Verificado en repositorio |
| `docs/templates/closure_handover.template.md` | Template | Define salida futura de handover | Verificado en repositorio |
| `docs/templates/evidence_index.template.md` | Template | Define salida futura de evidencia | Verificado en repositorio |
| `docs/templates/residual_debt.template.md` | Template | Define salida futura de deuda residual | Verificado en repositorio |
| `gates/consolidation_readiness_gate.md` | Gate documental | Fuente de criterios para entrada a Consolidation | Verificado en repositorio |
| `gates/closure_gate.md` | Gate documental | Fuente de criterios para cierre | Verificado en repositorio |

---

# 6. Fuentes Tecnicas Relacionadas

```yaml
repositorios:
  - nombre: jqf-sdd-foundation
    url: https://github.com/joquifer2/jqf-sdd-foundation.git
    rama: main
    descripcion: Repositorio Foundation en fase Specification / Structure / Documentation Governance; esta capacidad esta en Architecture documental validada por QA Gate T-011.
```

No existen integraciones tecnicas, APIs, datos, dashboards ni runtime en alcance.

---

# 7. Reglas de Carga de Contexto

Antes de modificar artefactos de esta capacidad:

1. Leer este archivo.
2. Leer el Brief de proyecto de esta capacidad.
3. Leer `specs/capabilities/consolidation-agent/spec-001-consolidation-agent.md` si existe.
4. Leer el handover de `SDD Project Consolidation and Closure`.
5. Tratar las capacidades cerradas como baseline cerrado.
6. No modificar expedientes cerrados salvo autorizacion explicita.
7. No crear agente real, scripts, tools, workflows, consolidaciones reales ni reorganizacion fisica durante Architecture documental.

---

# 8. Jerarquia de Contexto en Caso de Conflicto

1. Brief de proyecto de esta capacidad.
2. `.github/instructions/sdd.instructions.md`.
3. `SPEC-001 - Consolidation Agent`.
4. `SPEC-001` y `ARCH-001` de `SDD Project Consolidation and Closure`.
5. Gates de consolidacion y cierre.
6. AGENTS y definiciones canonicas de agentes existentes.
7. Templates.
8. Fuentes discovery-only o pendientes.

---

# 9. Contexto Pendiente

| Fuente pendiente | Motivo | Impacto | Responsable | Estado |
| --- | --- | --- | --- | --- |
| Definicion canonica futura en `.github/agents/` | Solo podra crearse tras autorizacion posterior | Bloquea existencia real del agente, no Specification | Jordi Quiroga / fase futura | PENDIENTE |
| Adaptador futuro en `.codex/agents/` | Depende de definicion canonica | Bloquea seleccion operativa en Codex, no Specification | Jordi Quiroga / fase futura | PENDIENTE |
| Architecture de esta capacidad | Autorizada por decision humana posterior a QA Gate T-007, creada como `ARCH-001`, revisada en T-010 y validada en T-011 | Requiere decision humana sobre siguiente fase documental | Architect Agent / Reviewer Agent / QA Gate Agent / Jordi Quiroga | QA PASSED - pending human decision |

---

# 10. Trazabilidad

```yaml
trazabilidad:
  creado_por: Specification Agent
  fecha_creacion: 2026-08-01
  ultima_actualizacion: 2026-08-01
  actualizado_por: QA Gate Agent
  contexto_validado_por: QA Gate Agent T-011
  fecha_validacion: 2026-08-01
  version_contexto: consolidation-agent-architecture-gate-passed
```
---

## Architecture References - T-008/T-009

| Artefacto | Funcion | Estado |
| --- | --- | --- |
| `specs/capabilities/consolidation-agent/arch-001-consolidation-agent.md` | Arquitectura documental conceptual del futuro `Consolidation Agent`. | QA Gate passed with minor conditions |

Restricciones:

- Architecture documental autorizada no equivale a Development.
- No se crea agente real ni adaptador Codex.
- No se crean scripts, tools, workflows ni automatizaciones.
- No se ejecutan consolidaciones reales ni reorganizacion fisica.
---

## Reviewer References - T-010

| Referencia | Funcion | Estado |
| --- | --- | --- |
| `docs/capabilities/consolidation-agent/tasks.md#14-reviewer-decision---t-010` | Decision de review de Architecture. | Completed |
| `specs/capabilities/consolidation-agent/arch-001-consolidation-agent.md` | Architecture revisada y corregida. | Approved with minor corrections |

Siguiente contexto a cargar:

- `docs/capabilities/consolidation-agent/sdd_readiness_assessment.md`
- `docs/capabilities/consolidation-agent/tasks.md`
- `specs/capabilities/consolidation-agent/arch-001-consolidation-agent.md`

Siguiente decision recomendada: decision humana sobre la siguiente fase documental.
---

## QA Gate References - T-011

| Referencia | Funcion | Estado |
| --- | --- | --- |
| `docs/capabilities/consolidation-agent/tasks.md#15-qa-gate-decision---t-011` | Decision de QA Gate de Architecture. | Completed |
| `docs/capabilities/consolidation-agent/sdd_readiness_assessment.md#qa-gate-decision---t-011` | Readiness actualizado tras gate de Architecture. | Pass with minor conditions |

Siguiente contexto a cargar:

- `docs/capabilities/consolidation-agent/project_brief.md`
- `docs/capabilities/consolidation-agent/sdd_readiness_assessment.md`
- `docs/capabilities/consolidation-agent/tasks.md`
- `specs/capabilities/consolidation-agent/spec-001-consolidation-agent.md`
- `specs/capabilities/consolidation-agent/arch-001-consolidation-agent.md`

Siguiente decision recomendada: decision humana sobre la siguiente fase documental.