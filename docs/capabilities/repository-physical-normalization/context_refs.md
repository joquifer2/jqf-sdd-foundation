# Referencias de contexto - Repository Physical Normalization

> Este documento indexa el contexto utilizado para la capacidad `Repository Physical Normalization`.
>
> No autoriza movimientos fisicos, cambios de baseline, scripts, workflows ni Development.

---

# 1. Identidad del Proyecto

```yaml
proyecto:
  nombre: JQF SDD Foundation - Repository Physical Normalization
  id_proyecto: repository-physical-normalization
  tipo_proyecto: foundation-repository-governance-specification
  estado: Development first wave executed / pending review
  fecha_creacion: 2026-08-02
  responsable: Jordi Quiroga

cliente:
  id_cliente: N/A
  nombre_cliente: N/A
  estado_relacion: N/A

sdd_mode:
  modo_declarado: SDD Full
  fuente_canonica: docs/capabilities/repository-physical-normalization/project_brief.md
  estado: Verificado
  ultima_revision: 2026-08-02
```

---

## SDD Mode

| Campo | Valor |
| --- | --- |
| Modo indexado | `SDD Full` |
| Fuente canonica | `docs/capabilities/repository-physical-normalization/project_brief.md` |
| Estado de verificacion | Verificado |
| Ultima revision | 2026-08-02 |
| Notas | La capacidad afecta rutas, baseline, expedientes cerrados, compatibilidad y trazabilidad. |

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
  fecha_consulta: 2026-08-02
```

Esta iniciativa pertenece a la Foundation y no a un cliente derivado.

---

# 3. Decisiones Relacionadas

| Fecha | Decision | Impacto en este proyecto | Fuente |
| --- | --- | --- | --- |
| 2026-08-01 | `SDD Project Consolidation and Closure` queda `Closed` | Define baseline, expediente historico, evidencia, deuda y reentrada como categorias previas a cualquier organizacion fisica. | `docs/capabilities/project-consolidation-and-closure/closure_handover.md` |
| 2026-08-01 | Arquitectura de consolidacion selecciona expedientes por capacidad para capacidades nuevas | Proporciona la estructura documental objetivo inicial. | `specs/capabilities/project-consolidation-and-closure/arch-001-sdd-project-consolidation-and-closure.md` |
| 2026-08-02 | `Consolidation Agent` queda `Closed with conditions` | Confirma que el agente puede producir propuestas `proposal-only`, pero no ejecutar cambios fisicos. | `docs/capabilities/consolidation-agent/closure_handover.md`; `docs/capabilities/consolidation-agent/residual_debt.md` |
| 2026-08-02 | Validacion retrospectiva sobre `SDD Modes` queda `Closed with conditions / PASS WITH CONDITIONS` | Proporciona el primer mapa de aplicacion real para normalizacion fisica futura. | `docs/capabilities/consolidation-agent/validations/sdd-modes-retrospective/` |

## Decisiones pendientes de validar

| Tema | Motivo de la duda | Responsable | Estado |
| --- | --- | --- | --- |
| Compatibilidad legacy exacta | Falta decidir si se usaran stubs, aliases, indices o coexistencia temporal. | Jordi Quiroga / Architect Agent futuro | PENDING |
| Naming final de Architecture de SDD Modes | El nombre actual `spec-001-sdd-modes.architecture.md` no sigue el patron `arch-001-*`. Renombrarlo tiene coste de compatibilidad. | Jordi Quiroga / Architect Agent futuro | PENDING |
| Ejecutor autorizado de movimientos | La Specification no debe decidir quien ejecuta fisicamente sin Architecture/Gate. | Jordi Quiroga | PENDING |
| Evidencia Git minima por movimiento | Debe definirse antes de Development/Documentation ejecutiva. | Reviewer Agent / QA Gate Agent futuro | PENDING |

---

# 4. Proyectos Relacionados

| Proyecto | Relacion con este proyecto | Estado | Fuente |
| --- | --- | --- | --- |
| `SDD Modes` | Primer caso real futuro; baseline cerrado con expediente historico en raiz. | Closed with conditions / baseline aprobado | `docs/capabilities/sdd-modes/project_brief.md`; `docs/capabilities/sdd-modes/context_refs.md`; `docs/capabilities/sdd-modes/tasks.md`; `docs/capabilities/sdd-modes/sdd_readiness_assessment.md`; `specs/capabilities/sdd-modes/spec-001-sdd-modes.md`; `specs/spec-001-sdd-modes.architecture.md` |
| `SDD Project Consolidation and Closure` | Define categorias de consolidacion que la normalizacion fisica debe respetar. | Closed | `docs/capabilities/project-consolidation-and-closure/closure_handover.md` |
| `Foundation Derivation and Project Initialization` | Define limites con proyectos derivados y baseline exportable. | Closed | `docs/capabilities/foundation-derivation-and-project-initialization/closure_handover.md` |
| `Consolidation Agent` | Produce propuestas de clasificacion y movimiento, pero no ejecuta normalizacion fisica. | Closed with conditions | `docs/capabilities/consolidation-agent/closure_handover.md` |

---

# 5. Conocimiento Reutilizable Relacionado

| Recurso | Tipo | Motivo de uso | Fuente |
| --- | --- | --- | --- |
| `.github/instructions/sdd.instructions.md` | Instrucciones SDD | Define fases, restricciones, Consolidation, Closed, gates y precedencia documental. | Verificado en repositorio |
| `AGENTS.md` | Catalogo metodologico | Define limites de agentes y confirma que el `Consolidation Agent` no ejecuta cambios fisicos. | Verificado en repositorio |
| `.github/agents/specification.agent.md` | Definicion canonica de agente | Rige la creacion de esta specification. | Verificado en repositorio |
| `docs/templates/project_brief.template.md` | Template | Base estructural del Brief de proyecto. | Verificado en repositorio |
| `docs/templates/context_refs.template.md` | Template | Base estructural de referencias de contexto. | Verificado en repositorio |
| `docs/templates/sdd_readiness_assessment.template.md` | Template | Base estructural del readiness inicial. | Verificado en repositorio |
| `specs/templates/spec.template.md` | Template | Base estructural de `SPEC-001`. | Verificado en repositorio |
| `docs/capabilities/consolidation-agent/validations/sdd-modes-retrospective/consolidation_report.md` | Validacion / propuesta | Contiene propuesta no ejecutable de target structure para `SDD Modes`. | Verificado en repositorio |
| `docs/capabilities/consolidation-agent/validations/sdd-modes-retrospective/qa_gate_decision.md` | QA evidence | Confirma que la propuesta fisica no fue ejecutada. | Verificado en repositorio |

---

# 6. Fuentes Tecnicas Relacionadas

```yaml
repositorios:
  - nombre: jqf-sdd-foundation
    url: https://github.com/joquifer2/jqf-sdd-foundation.git
    rama: main
    descripcion: Repositorio Foundation local en C:\Workspace\JOQUIFER\sdd-foundation. Esta capacidad permanece en Specification y no ejecuta movimientos fisicos.
```

No existen APIs, datos, dashboards, runtime ni integraciones tecnicas en alcance.

---

# 7. Reglas de Carga de Contexto

Antes de modificar artefactos de esta capacidad:

1. Leer este archivo.
2. Leer el Brief de proyecto de esta capacidad.
3. Leer `specs/capabilities/repository-physical-normalization/spec-001-repository-physical-normalization.md` si existe.
4. Leer el paquete retrospectivo `docs/capabilities/consolidation-agent/validations/sdd-modes-retrospective/`.
5. Tratar `SDD Modes` como baseline cerrado y read-only.
6. No mover, copiar, renombrar, eliminar ni sustituir archivos.
7. No ampliar Governed Execution Preparation fuera de T-013 ni crear scripts, workflows, automatizaciones, Development, stubs o normalizacion fisica desde esta fase.

---

# 8. Jerarquia de Contexto en Caso de Conflicto

1. Brief de proyecto de esta capacidad.
2. `.github/instructions/sdd.instructions.md`.
3. `SPEC-001 - Repository Physical Normalization`.
4. Baseline cerrado de `SDD Project Consolidation and Closure`.
5. Baseline cerrado de `Consolidation Agent`.
6. Paquete retrospectivo de SDD Modes, solo como propuesta/evidencia `proposal-only`.
7. Indices globales.
8. README, AGENTS y glosario.
9. Fuentes discovery-only o pendientes.

---

# 9. Contexto Pendiente

| Fuente pendiente | Motivo | Impacto | Responsable | Estado |
| --- | --- | --- | --- | --- |
| Architecture de esta capacidad | Autorizada por decision humana del 2026-08-02, creada como `ARCH-001`, revisada en T-011 y validada en T-012. | Define arquitectura documental no ejecutable; pendiente de decision humana futura. | Architect Agent / Reviewer Agent / QA Gate Agent | Pass with minor conditions T-012 |
| Reference map completo | Definido conceptualmente en `ARCH-001`; no generado como inventario ejecutable. | Necesario antes de cualquier movimiento futuro. | Documentation Agent / Reviewer futuro | PENDING - future execution prep |
| Estrategia de compatibilidad legacy | `ARCH-001` selecciona stubs documentales temporales como estrategia conceptual. | Requiere detalle futuro antes de ejecucion. | Architect Agent / Reviewer futuro | Reviewed conceptually / QA T-012 conditions |
| Rollback plan | Definido conceptualmente en `ARCH-001`; no ejecutado. | Bloquea ejecucion reversible hasta plan detallado futuro. | Documentation / QA futuro | Defined conceptually / Pending detail |

---

# 10. Trazabilidad

```yaml
trazabilidad:
  creado_por: Specification Agent
  fecha_creacion: 2026-08-02
  ultima_actualizacion: 2026-08-02
  actualizado_por: Specification Agent
  contexto_validado_por: QA Gate Agent T-007
  fecha_validacion: 2026-08-02
  version_contexto: repository-physical-normalization-governed-execution-preparation
```

---

## QA Gate References - T-007

| Referencia | Funcion | Estado |
| --- | --- | --- |
| `docs/capabilities/repository-physical-normalization/tasks.md#11-qa-gate-decision---t-007` | Decision de QA Gate de Specification. | Completed |
| `docs/capabilities/repository-physical-normalization/sdd_readiness_assessment.md#qa-gate-decision---t-007` | Readiness actualizado tras gate de Specification. | Pass with minor conditions |

Siguiente contexto a cargar:

- `docs/capabilities/repository-physical-normalization/project_brief.md`
- `docs/capabilities/repository-physical-normalization/context_refs.md`
- `specs/capabilities/repository-physical-normalization/spec-001-repository-physical-normalization.md`
- `docs/capabilities/repository-physical-normalization/sdd_readiness_assessment.md`
- `docs/capabilities/repository-physical-normalization/tasks.md`

Siguiente decision recomendada: decision humana sobre posible fase futura de preparacion ejecutiva gobernada.

Restricciones vigentes:

- Architecture no quedo autorizada por QA Gate T-007; fue autorizada despues por decision humana T-008.
- Development permanece `NOT AUTHORIZED`.
- No se autoriza normalizacion fisica, movimiento, copia, renombre, sustitucion ni eliminacion de archivos.
---

## Architecture References - T-008/T-010

| Referencia | Funcion | Estado |
| --- | --- | --- |
| `docs/capabilities/repository-physical-normalization/tasks.md#13-architecture-authorization---t-008` | Decision humana que autoriza Architecture documental. | Completed |
| `specs/capabilities/repository-physical-normalization/arch-001-repository-physical-normalization.md` | Arquitectura documental conceptual de normalizacion fisica. | Pass with minor conditions T-012 |
| `docs/capabilities/repository-physical-normalization/tasks.md#14-architecture-execution---t-009t-010` | Registro de ejecucion documental de Architecture. | Completed |

Siguiente contexto a cargar:

- `docs/capabilities/repository-physical-normalization/project_brief.md`
- `docs/capabilities/repository-physical-normalization/context_refs.md`
- `specs/capabilities/repository-physical-normalization/spec-001-repository-physical-normalization.md`
- `specs/capabilities/repository-physical-normalization/arch-001-repository-physical-normalization.md`
- `docs/capabilities/repository-physical-normalization/sdd_readiness_assessment.md`
- `docs/capabilities/repository-physical-normalization/tasks.md`

Restricciones vigentes:

- Development permanece `NOT AUTHORIZED`.
- No se autoriza normalizacion fisica, movimiento, copia, renombre, sustitucion ni eliminacion de archivos.
- Baselines cerrados permanecen read-only.
---

## Architecture QA Gate References - T-012

| Referencia | Funcion | Estado |
| --- | --- | --- |
| `docs/capabilities/repository-physical-normalization/tasks.md#16-architecture-qa-gate-decision---t-012` | Decision de QA Gate de Architecture. | Pass with minor conditions |
| `docs/capabilities/repository-physical-normalization/sdd_readiness_assessment.md#architecture-qa-gate-decision---t-012` | Readiness actualizado tras gate de Architecture. | Completed |

Restricciones vigentes:

- Development permanece `NOT AUTHORIZED`.
- No se autoriza normalizacion fisica, movimiento, copia, renombre, sustitucion ni eliminacion de archivos.
- Baselines cerrados permanecen read-only.
---

## Governed Execution Preparation References - T-013/T-020

| Referencia | Funcion | Estado |
| --- | --- | --- |
| `docs/capabilities/repository-physical-normalization/tasks.md#17-governed-execution-preparation-authorization---t-013` | Decision humana que autoriza preparacion documental de ejecucion gobernada. | Completed |
| `docs/capabilities/repository-physical-normalization/governed-execution-preparation/README.md` | Indice del paquete GEP. | Draft for review |
| `docs/capabilities/repository-physical-normalization/governed-execution-preparation/canonical_route_registry.md` | Registro canonico de rutas objetivo futuras. | Draft for review |
| `docs/capabilities/repository-physical-normalization/governed-execution-preparation/reference_map.md` | Mapa inicial de referencias y superficies de compatibilidad. | Draft for review |
| `docs/capabilities/repository-physical-normalization/governed-execution-preparation/movement_plan.md` | Plan de movimientos futuros por olas, no ejecutado. | Draft for review |
| `docs/capabilities/repository-physical-normalization/governed-execution-preparation/compatibility_plan.md` | Plan de continuidad de enlaces, referencias, handovers y derivados. | Draft for review |
| `docs/capabilities/repository-physical-normalization/governed-execution-preparation/rollback_plan.md` | Plan de reversibilidad futura. | Draft for review |
| `docs/capabilities/repository-physical-normalization/governed-execution-preparation/validation_checklist.md` | Checklist de readiness previo a Development y validacion futura. | Draft for review |
| `docs/capabilities/repository-physical-normalization/governed-execution-preparation/sdd_modes_pilot_package.md` | Aplicacion piloto sobre SDD Modes, no ejecutada. | Draft for review |

Siguiente contexto a cargar:

- `docs/capabilities/repository-physical-normalization/project_brief.md`
- `docs/capabilities/repository-physical-normalization/context_refs.md`
- `specs/capabilities/repository-physical-normalization/spec-001-repository-physical-normalization.md`
- `specs/capabilities/repository-physical-normalization/arch-001-repository-physical-normalization.md`
- `docs/capabilities/repository-physical-normalization/sdd_readiness_assessment.md`
- `docs/capabilities/repository-physical-normalization/tasks.md`
- `docs/capabilities/repository-physical-normalization/governed-execution-preparation/README.md`

Siguiente decision recomendada: Reviewer Agent review of Repository Physical Normalization Development first wave.

Restricciones vigentes:

- Development permanece `NOT AUTHORIZED`.
- No se autoriza normalizacion fisica, movimiento, copia, renombre, sustitucion ni eliminacion de archivos.
- No se autoriza creacion de stubs.
- No se autorizan scripts, tools, workflows ni automatizaciones.
- Baselines cerrados permanecen read-only.
---

## Governed Execution Preparation Reviewer References - T-021

| Referencia | Funcion | Estado |
| --- | --- | --- |
| `docs/capabilities/repository-physical-normalization/tasks.md#19-governed-execution-preparation-reviewer-decision---t-021` | Decision de Reviewer Agent sobre el paquete GEP. | Approved with minor changes |
| `docs/capabilities/repository-physical-normalization/sdd_readiness_assessment.md#governed-execution-preparation-reviewer-decision---t-021` | Readiness actualizado tras review T-021. | Ready for QA Gate |
| `docs/capabilities/repository-physical-normalization/governed-execution-preparation/validation_checklist.md` | Checklist actualizado con VC-PRE-012 tras review. | Draft for QA Gate |

Siguiente contexto a cargar:

- `docs/capabilities/repository-physical-normalization/project_brief.md`
- `docs/capabilities/repository-physical-normalization/context_refs.md`
- `specs/capabilities/repository-physical-normalization/spec-001-repository-physical-normalization.md`
- `specs/capabilities/repository-physical-normalization/arch-001-repository-physical-normalization.md`
- `docs/capabilities/repository-physical-normalization/sdd_readiness_assessment.md`
- `docs/capabilities/repository-physical-normalization/tasks.md`
- `docs/capabilities/repository-physical-normalization/governed-execution-preparation/README.md`
- `docs/capabilities/repository-physical-normalization/governed-execution-preparation/validation_checklist.md`

Siguiente decision recomendada: Reviewer Agent review of Repository Physical Normalization Development first wave.

Restricciones vigentes:

- Development permanece `NOT AUTHORIZED`.
- No se autoriza normalizacion fisica, movimiento, copia, renombre, sustitucion ni eliminacion de archivos.
- No se autoriza creacion de stubs.
- No se autorizan scripts, tools, workflows ni automatizaciones.
- Baselines cerrados permanecen read-only.
---

## Governed Execution Preparation QA Gate References - T-022

| Referencia | Funcion | Estado |
| --- | --- | --- |
| `docs/capabilities/repository-physical-normalization/tasks.md#20-governed-execution-preparation-qa-gate-decision---t-022` | Decision de QA Gate sobre readiness del paquete GEP. | Pass with minor conditions |
| `docs/capabilities/repository-physical-normalization/sdd_readiness_assessment.md#governed-execution-preparation-qa-gate-decision---t-022` | Readiness actualizado tras QA T-022. | Pending human Development decision |
| `docs/capabilities/repository-physical-normalization/governed-execution-preparation/validation_checklist.md#qa-gate-result---t-022` | Checklist actualizado con controles VC-PRE-009 a VC-PRE-013. | Pass with minor conditions |

Siguiente contexto a cargar:

- `docs/capabilities/repository-physical-normalization/project_brief.md`
- `docs/capabilities/repository-physical-normalization/context_refs.md`
- `specs/capabilities/repository-physical-normalization/spec-001-repository-physical-normalization.md`
- `specs/capabilities/repository-physical-normalization/arch-001-repository-physical-normalization.md`
- `docs/capabilities/repository-physical-normalization/sdd_readiness_assessment.md`
- `docs/capabilities/repository-physical-normalization/tasks.md`
- `docs/capabilities/repository-physical-normalization/governed-execution-preparation/README.md`

Siguiente decision recomendada: Reviewer Agent review of Repository Physical Normalization Development first wave.

Restricciones vigentes:

- Development permanece `NOT AUTHORIZED` hasta decision humana explicita posterior.
- No se autoriza normalizacion fisica, movimiento, copia, renombre, sustitucion ni eliminacion de archivos.
- No se autoriza creacion de stubs.
- No se autorizan scripts, tools, workflows ni automatizaciones.
- Baselines cerrados permanecen read-only.
---

## Development Execution References - T-023/T-026

| Referencia | Funcion | Estado |
| --- | --- | --- |
| `docs/capabilities/repository-physical-normalization/tasks.md#21-development-authorization---t-023` | Decision humana que autoriza Development. | Completed |
| `docs/capabilities/repository-physical-normalization/tasks.md#22-development-first-wave-execution---t-024t-026` | Registro de ejecucion de primera ola. | Executed / pending review |
| `docs/capabilities/repository-physical-normalization/governed-execution-preparation/movement_execution_report.md` | Reporte de movimientos, stubs y decision de Architecture legacy. | Executed / pending review |
| `docs/capabilities/repository-physical-normalization/governed-execution-preparation/validation_checklist.md#development-execution-result---t-024t-026` | Checklist Development actualizado. | Pending Reviewer/QA |

Rutas canonicas SDD Modes tras primera ola:

- `docs/capabilities/sdd-modes/project_brief.md`
- `docs/capabilities/sdd-modes/context_refs.md`
- `docs/capabilities/sdd-modes/tasks.md`
- `docs/capabilities/sdd-modes/sdd_readiness_assessment.md`
- `specs/capabilities/sdd-modes/spec-001-sdd-modes.md`

Rutas legacy preservadas como stubs:

- `docs/project_brief.md`
- `docs/context_refs.md`
- `docs/tasks.md`
- `docs/sdd_readiness_assessment.md`
- `specs/spec-001-sdd-modes.md`

Ruta legacy canonica temporal retenida:

- `specs/spec-001-sdd-modes.architecture.md`

Siguiente decision recomendada: Reviewer Agent review of Repository Physical Normalization Development first wave.