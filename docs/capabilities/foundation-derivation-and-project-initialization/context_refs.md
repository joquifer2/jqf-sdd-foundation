# Referencias de contexto - Foundation Derivation and Project Initialization

> Este documento indexa el contexto utilizado para la capacidad `Foundation Derivation and Project Initialization`.
>
> No modifica capacidades cerradas ni convierte expedientes internos de Foundation en baseline exportable.

---

# 1. Identidad del Proyecto

```yaml
proyecto:
  nombre: JQF SDD Foundation - Foundation Derivation and Project Initialization
  id_proyecto: foundation-derivation-and-project-initialization
  tipo_proyecto: foundation-methodology-improvement
  estado: Closed
  fecha_creacion: 2026-08-01
  responsable: Jordi Quiroga

cliente:
  id_cliente: N/A
  nombre_cliente: N/A
  estado_relacion: N/A

sdd_mode:
  modo_declarado: SDD Full
  fuente_canonica: docs/capabilities/foundation-derivation-and-project-initialization/project_brief.md
  estado: Verificado
  ultima_revision: 2026-08-01
```

---

## SDD Mode

| Campo | Valor |
| --- | --- |
| Modo indexado | `SDD Full` |
| Fuente canonica | `docs/capabilities/foundation-derivation-and-project-initialization/project_brief.md` |
| Estado de verificacion | Verificado |
| Ultima revision | 2026-08-01 |
| Notas | La capacidad afecta el modelo de derivacion de repositorios y requiere gobierno completo. |

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
| 2026-08-01 | `SDD Modes` se considera capacidad cerrada y baseline metodologico vigente | Define los modos iniciales que debe soportar un proyecto derivado | `specs/spec-001-sdd-modes.md` |
| 2026-08-01 | `SDD Project Consolidation and Closure` se considera capacidad cerrada | Define separacion entre baseline, expediente historico, evidencia y deuda residual | `specs/capabilities/project-consolidation-and-closure/spec-001-sdd-project-consolidation-and-closure.md` |
| 2026-08-01 | `Consolidation Agent` permanece futuro pendiente | La derivacion puede preparar su marco, pero no implementarlo | `docs/capabilities/project-consolidation-and-closure/residual_debt.md` |
| 2026-08-01 | QA Gate T-007: Specification readiness `Pass with minor conditions` | Habilita decision humana sobre Architecture; no autoriza Development | Solicitud humana y evaluacion QA Gate Agent |
| 2026-08-01 | Jordi Quiroga autoriza Architecture mediante `[@Architect Agent] Adelante` | Permite crear `ARCH-001` documental; no autoriza Development ni reorganizacion fisica | Solicitud humana |
| 2026-08-01 | Reviewer Agent revisa `ARCH-001` con decision `Approved with minor changes` | Requiere correcciones menores aplicadas por Architect Agent antes de QA Gate | Revision de Reviewer Agent |
| 2026-08-01 | Reviewer Agent confirma correcciones de Architecture | Habilita QA Gate de Architecture | Confirmacion de Reviewer Agent |
| 2026-08-01 | QA Gate T-011 emite `Pass with minor conditions` | Habilita preparacion documental de cierre; no autoriza Development | Evaluacion QA Gate Agent |
| 2026-08-01 | Documentation Agent prepara expediente para Closure Gate | Crea handover, deuda residual y actualiza indices; no modifica baselines cerrados | Solicitud humana y Documentation Agent |
| 2026-08-01 | QA Gate T-013 emite `Pass with minor conditions` | Cierra documentalmente la capacidad; no autoriza Development | Evaluacion QA Gate Agent |

## Decisiones pendientes de validar

| Tema | Motivo de la duda | Responsable | Estado |
| --- | --- | --- | --- |
| Versionado formal del baseline exportable | Necesario para compatibilidad futura entre Foundation y derivados | Architect Agent / Jordi Quiroga | PENDIENTE - post-Architecture |
| Estructura fisica del paquete derivable | La iteracion actual prohibe reorganizacion fisica | Architect Agent | PENDIENTE - Repository Physical Normalization |
| Mecanismo de actualizacion desde Foundation hacia derivados | Requiere reglas de compatibilidad, diffs y aprobacion humana | Specification Agent / Architect Agent | PENDIENTE |

---

# 4. Proyectos Relacionados

| Proyecto | Relacion con este proyecto | Estado | Fuente |
| --- | --- | --- | --- |
| `SDD Modes` | Baseline de modos que todo derivado debe poder declarar | Cerrado / baseline vigente | `specs/spec-001-sdd-modes.md`; `docs/project_brief.md` |
| `SDD Project Consolidation and Closure` | Baseline para clasificar producto reutilizable frente a expediente interno | Closed | `docs/capabilities/project-consolidation-and-closure/closure_handover.md`; `specs/capabilities/project-consolidation-and-closure/spec-001-sdd-project-consolidation-and-closure.md` |

---

# 5. Conocimiento Reutilizable Relacionado

| Recurso | Tipo | Motivo de uso | Fuente |
| --- | --- | --- | --- |
| `AGENTS.md` | Catalogo metodologico | Define agentes vigentes y limites del SDD Harness | Verificado en repositorio |
| `README.md` | Documentacion general | Describe estado actual de la Foundation | Verificado en repositorio |
| `docs/capabilities/index.md` | Catalogo | Identifica capacidades cerradas y routing | Verificado en repositorio |
| `specs/capabilities/index.md` | Catalogo | Identifica specs y architectures vigentes por capacidad | Verificado en repositorio |
| `docs/templates/project_brief.template.md` | Template | Base para Project Brief inicial de un derivado | Verificado en repositorio |
| `docs/templates/context_refs.template.md` | Template | Base para referencias de contexto iniciales | Verificado en repositorio |
| `docs/templates/sdd_readiness_assessment.template.md` | Template | Base para readiness inicial | Verificado en repositorio |
| `specs/templates/spec.template.md` | Template | Base para specification futura de proyectos derivados | Verificado en repositorio |

---

## 5.1 Baseline metodologico vigente

| Artefacto | Estado | Funcion |
| --- | --- | --- |
| `specs/spec-001-sdd-modes.md` | Final | Fuente normativa principal de SDD Modes. |
| `specs/spec-001-sdd-modes.architecture.md` | Final | Arquitectura conceptual aprobada de SDD Modes. |
| `specs/capabilities/project-consolidation-and-closure/spec-001-sdd-project-consolidation-and-closure.md` | Closed baseline | Fuente normativa de consolidacion y cierre. |
| `specs/capabilities/project-consolidation-and-closure/arch-001-sdd-project-consolidation-and-closure.md` | Closed baseline | Arquitectura documental para expedientes, handover y gates conceptuales. |
| `specs/capabilities/foundation-derivation-and-project-initialization/spec-001-foundation-derivation-and-project-initialization.md` | Specification | Specification de la capacidad actual. |
| `specs/capabilities/foundation-derivation-and-project-initialization/arch-001-foundation-derivation-and-project-initialization.md` | Architecture | Arquitectura documental de derivacion e inicializacion; no autoriza Development. |
| `docs/capabilities/foundation-derivation-and-project-initialization/closure_handover.md` | Closed | Handover de cierre con baseline propuesto, decisiones, gates y reentradas. |
| `docs/capabilities/foundation-derivation-and-project-initialization/residual_debt.md` | Closed / active residual debt | Registro de deuda residual aceptada y capacidades futuras relacionadas. |
| `gates/consolidation_readiness_gate.md` | Documental | Gate conceptual para readiness de Consolidation. |
| `gates/closure_gate.md` | Documental | Gate conceptual para Closure. |

---

# 6. Fuentes Tecnicas Relacionadas

```yaml
repositorios:
  - nombre: jqf-sdd-foundation
    url: https://github.com/joquifer2/jqf-sdd-foundation.git
    rama: main
    descripcion: Repositorio Foundation en fase Specification / Structure.
```

No existen integraciones tecnicas, APIs, datos, dashboards ni runtime en alcance.

---

# 7. Reglas de Carga de Contexto

Antes de modificar artefactos de esta capacidad:

1. Leer este archivo.
2. Leer el Brief de proyecto de esta capacidad.
3. Leer `specs/capabilities/foundation-derivation-and-project-initialization/spec-001-foundation-derivation-and-project-initialization.md` si existe.
4. Leer `specs/capabilities/foundation-derivation-and-project-initialization/arch-001-foundation-derivation-and-project-initialization.md` si existe.
5. Leer `docs/capabilities/foundation-derivation-and-project-initialization/closure_handover.md` si existe.
6. Leer `docs/capabilities/foundation-derivation-and-project-initialization/residual_debt.md` si existe.
7. Tratar `SDD Modes` y `SDD Project Consolidation and Closure` como capacidades cerradas.
8. No modificar baselines cerrados salvo autorizacion explicita.
9. Mantener toda decision fisica, ejecutable o de normalizacion como pendiente de fase futura autorizada.
10. No crear scripts, asistentes, workflows, templates automaticos ni reorganizacion fisica.

---

# 8. Jerarquia de Contexto en Caso de Conflicto

Esta jerarquia local debe interpretarse dentro de la precedencia documental oficial definida en `.github/instructions/sdd.instructions.md`.

1. Brief de proyecto de esta capacidad.
2. `.github/instructions/sdd.instructions.md`.
3. `SPEC-001 - Foundation Derivation and Project Initialization`.
4. `ARCH-001 - Foundation Derivation and Project Initialization` para decisiones de Architecture autorizadas.
5. Baseline vigente de `SDD Modes`.
6. Baseline vigente de `SDD Project Consolidation and Closure`.
7. Gates aplicables, si existieran en una fase posterior autorizada.
8. `AGENTS.md` y definiciones canonicas de agentes metodologicos.
9. README, glosario, indices y templates.
10. Solicitudes humanas operativas dentro de esta capacidad, siempre que no contradigan artefactos de mayor precedencia.
11. Fuentes discovery-only o pendientes.

---

# 9. Contexto Pendiente

| Fuente pendiente | Motivo | Impacto | Responsable | Estado |
| --- | --- | --- | --- | --- |
| Primer proyecto derivado real | Validaria empiricamente el proceso | No bloquea Closure Gate | Jordi Quiroga / futuro QA Gate | PENDIENTE |
| Versionado de baseline exportable | Necesario para actualizaciones futuras | No bloquea Closure Gate | Architect Agent | PENDIENTE |
| Repository Physical Normalization | Definira estructura fisica futura | Fuera de alcance actual | Futuro agente/capacidad | PENDIENTE |

---

# 10. Trazabilidad

```yaml
trazabilidad:
  creado_por: Specification Agent
  fecha_creacion: 2026-08-01
  ultima_actualizacion: 2026-08-01
  actualizado_por: Documentation Agent
  contexto_validado_por: Reviewer Agent - Approved; QA Gate Agent - Pass with minor conditions; Documentation Agent - closure preparation
  fecha_validacion: 2026-08-01
  version_contexto: foundation-derivation-closed-2026-08-01
```