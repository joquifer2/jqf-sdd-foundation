# Movement Plan - Repository Physical Normalization

## Estado

| Campo | Valor |
| --- | --- |
| Fase | Development |
| Estado | Closed - DEV-RPN-010 |
| Development | AUTHORIZED for first SDD Modes wave |
| Ejecucion | DEV-P1, DEV-P3, DEV-P4 and compatibility stubs executed; Closed - DEV-RPN-010 |

## Proposito

Este plan registra la secuencia aplicada en la primera ola Development de normalizacion fisica sobre SDD Modes.

La ejecucion movio cinco artefactos, creo stubs de compatibilidad y mantuvo `specs/spec-001-sdd-modes.architecture.md` en su ruta legacy.

## Reglas de precedencia

1. No hay movimiento sin decision humana explicita de Development.
2. No hay movimiento sin Reviewer Agent sobre este paquete.
3. No hay movimiento sin QA Gate que confirme readiness para Development.
4. No hay movimiento sin Reference Map final actualizado inmediatamente antes de ejecutar.
5. No se modifica baseline cerrado de SDD Modes en contenido normativo.
6. La primera ejecucion futura debe preservar compatibilidad con rutas legacy.
7. Si una ruta presenta riesgo alto no mitigado, se difiere.

## Olas futuras propuestas

| Ola | Nombre | Accion futura | Salida esperada | Estado actual |
| --- | --- | --- | --- | --- |
| GEP-0 | Preparation package | Crear este paquete documental. | Artefactos de preparacion listos para review. | Completed in documentation |
| DEV-P0 | Final preflight | Revalidar Reference Map, alcance, worktree y autorizacion. | Go/no-go de ejecucion. | Executed |
| DEV-P1 | Capability target dossier | Crear rutas objetivo para SDD Modes si no existen. | Directorios objetivo preparados. | Executed |
| DEV-P2 | Derived summaries | Crear `closure_handover.md`, `evidence_index.md` y `residual_debt.md` derivados, si se autoriza. | Resumen local no normativo. | Deferred |
| DEV-P3 | Move documentation dossier | Mover `docs/project_brief.md`, `docs/context_refs.md`, `docs/tasks.md`, `docs/sdd_readiness_assessment.md`. | Expediente documental bajo `docs/capabilities/sdd-modes/`. | Executed |
| DEV-P4 | Move specification baseline | Mover `specs/spec-001-sdd-modes.md`. | Specification bajo `specs/capabilities/sdd-modes/`. | Executed |
| DEV-P5 | Architecture route decision | Mantener ruta legacy, mover sin renombrar o mover/renombrar Architecture segun decision explicita. | Decision aplicada de forma trazable. | Keep/defer executed |
| DEV-P6 | Compatibility update | Actualizar indices y referencias autorizadas; crear stubs si se autoriza. | Navegacion coherente y compatible. | Executed for stubs and active indexes |
| DEV-P7 | Validation and handover | Ejecutar checklist documental/manual y registrar resultado. | Primera ola validada; DEV-RPN-010 queda como ola futura propuesta. | Completed for first wave / DEV-RPN-010 proposed |

## Reglas por tipo de accion

| Accion | Cuando aplicarla en Development futuro | Restriccion |
| --- | --- | --- |
| Mover | Cuando el artefacto pertenece exclusivamente al expediente SDD Modes y la ruta objetivo esta en el registry. | Requiere compatibilidad legacy. |
| Copiar | Solo para crear resumen derivado no normativo desde evidencia cerrada. | La copia no puede presentarse como nueva fuente normativa si deriva de baseline cerrado. |
| Mantener | Cuando el artefacto es transversal, generico del harness o evidencia historica de otra capacidad. | No duplicar como contenido de SDD Modes. |
| Archivar | Solo si una ruta queda obsoleta y hay autorizacion posterior especifica. | No aplicar en primera ejecucion. |
| Sustituir | Solo para reemplazar una ruta legacy por stub de routing autorizado. | No crear stubs en esta fase. |

## Punto de parada obligatorio

La primera ola se detiene tras DEV-P7 para review y QA post-ejecucion. Cualquier movimiento adicional requiere decision/gate aplicable.

---

## Executed Wave DEV-RPN-010 - SDD Modes Architecture Route

| Campo | Valor |
| --- | --- |
| Estado | QA passed with minor conditions - T-038 |
| Decision recomendada | Option A |
| Origen | `specs/spec-001-sdd-modes.architecture.md` |
| Destino | `specs/capabilities/sdd-modes/arch-001-sdd-modes.md` |
| Compatibilidad | Convertir origen en stub legacy no normativo |

Secuencia futura requerida:

1. Revalidar Reference Map inmediatamente antes de ejecutar.
2. Confirmar Reviewer Agent sobre este paquete.
3. Confirmar QA Gate Agent sobre readiness de DEV-RPN-010.
4. Obtener autorizacion humana explicita.
5. Mover/renombrar el archivo mediante mecanismo trazable.
6. Crear stub legacy en `specs/spec-001-sdd-modes.architecture.md`.
7. Actualizar referencias activas autorizadas.
8. Mantener referencias historicas cerradas si describen estado previo.
9. Registrar ejecucion y evidencia.
10. Ejecutar validation checklist post-move.

Criterio de parada:

Si Reviewer, QA o la revalidacion de referencias detectan una referencia activa no compatibilizable, DEV-RPN-010 debe volver a decision arquitectonica antes de ejecucion.