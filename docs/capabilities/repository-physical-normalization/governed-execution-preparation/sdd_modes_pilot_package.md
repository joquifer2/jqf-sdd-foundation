# SDD Modes Pilot Package - Repository Physical Normalization

## Estado

| Campo | Valor |
| --- | --- |
| Caso piloto | SDD Modes |
| Fase | Development |
| Estado | First controlled movement executed / pending review |
| Development | AUTHORIZED for first wave |
| Normalizacion fisica | Executed for selected SDD Modes artifacts |

## Proposito

SDD Modes sera el primer caso real de aplicacion de `Repository Physical Normalization` porque es una capacidad cerrada con baseline aprobado, expediente historico en raiz y validacion retrospectiva ya producida por Consolidation Agent.

Este paquete piloto registra la primera aplicacion controlada de la normalizacion sobre SDD Modes.

## Entradas del piloto

| Entrada | Ruta | Uso |
| --- | --- | --- |
| Project Brief SDD Modes | `docs/capabilities/sdd-modes/project_brief.md` | Alcance inicial y declaracion SDD Full historica. |
| Context References SDD Modes | `docs/capabilities/sdd-modes/context_refs.md` | Indice de fuentes, validaciones y pendientes. |
| Tasks SDD Modes | `docs/capabilities/sdd-modes/tasks.md` | Decision log historico T-001..T-027. |
| Readiness SDD Modes | `docs/capabilities/sdd-modes/sdd_readiness_assessment.md` | Evidencia de QA, cierre y condiciones. |
| SPEC SDD Modes | `specs/capabilities/sdd-modes/spec-001-sdd-modes.md` | Baseline normativo. |
| ARCH SDD Modes | `specs/spec-001-sdd-modes.architecture.md` | Arquitectura conceptual aprobada. |
| Consolidation report | `docs/capabilities/consolidation-agent/validations/sdd-modes-retrospective/consolidation_report.md` | Propuesta previa no ejecutada y deuda estructural. |
| QA retrospective decision | `docs/capabilities/consolidation-agent/validations/sdd-modes-retrospective/qa_gate_decision.md` | Confirmacion PASS WITH CONDITIONS sin modificar SDD Modes. |
| Residual debt and reentry | `docs/capabilities/consolidation-agent/validations/sdd-modes-retrospective/residual_debt_and_reentry.md` | Deuda estructural y punto de reentrada. |

## Salidas futuras propuestas

| Salida futura | Ruta objetivo | Tipo | Estado actual |
| --- | --- | --- | --- |
| Project Brief | `docs/capabilities/sdd-modes/project_brief.md` | Moved artifact | Executed |
| Context References | `docs/capabilities/sdd-modes/context_refs.md` | Moved artifact | Executed |
| Tasks | `docs/capabilities/sdd-modes/tasks.md` | Moved artifact | Executed |
| Readiness | `docs/capabilities/sdd-modes/sdd_readiness_assessment.md` | Moved artifact | Executed |
| Specification | `specs/capabilities/sdd-modes/spec-001-sdd-modes.md` | Moved baseline | Executed |
| Architecture | `specs/spec-001-sdd-modes.architecture.md` | Legacy canonical retained | Deferred / kept |
| Closure handover | `docs/capabilities/sdd-modes/closure_handover.md` | Derived summary | Not authorized |
| Evidence index | `docs/capabilities/sdd-modes/evidence_index.md` | Derived summary | Not authorized |
| Residual debt | `docs/capabilities/sdd-modes/residual_debt.md` | Derived summary | Not authorized |

## Secuencia piloto futura

1. Confirmar decision humana de Development.
2. Revalidar Reference Map contra rutas legacy de SDD Modes.
3. Decidir explicitamente el tratamiento de `specs/spec-001-sdd-modes.architecture.md`.
4. Preparar compatibilidad legacy antes de mover.
5. Mover expediente documental si esta autorizado.
6. Mover baseline de Specification si esta autorizado.
7. Aplicar decision de Architecture si esta autorizada.
8. Actualizar indices y referencias activas.
9. Validar no ruptura.
10. Registrar resultado para Reviewer y QA.

## Reglas especificas del piloto

- SDD Modes no se reabre funcionalmente.
- El baseline aprobado no cambia en contenido normativo.
- La validacion retrospectiva de Consolidation Agent permanece como evidencia historica.
- VAL-001 y condiciones aceptadas permanecen trazables.
- Rutas transversales de agentes, instrucciones, plantillas, README, AGENTS y glosario no se mueven como parte del piloto.
- La primera ejecucion futura debe ser conservadora y reversible.

## Criterios de aceptacion del piloto futuro

| Criterio | Resultado esperado |
| --- | --- |
| Trazabilidad | Puede reconstruirse origen, destino y decision para cada ruta. |
| Compatibilidad | Rutas legacy criticas no quedan rotas sin tratamiento. |
| Baseline | SDD Modes conserva contenido normativo aprobado. |
| Navegacion | Indices y context refs apuntan a fuentes vigentes. |
| Reversibilidad | Cada ola puede revertirse sin reescribir historia Git. |
| Transferibilidad | La misma estructura puede aplicarse a una capacidad cerrada futura. |

## Transferencia a capacidades futuras

Una vez validado el piloto, cualquier capacidad cerrada futura debe preparar su propio paquete minimo:

- registro de rutas canonicas;
- mapa de referencias;
- plan de movimiento;
- plan de compatibilidad;
- plan de rollback;
- checklist de validacion;
- decision humana explicita antes de Development.