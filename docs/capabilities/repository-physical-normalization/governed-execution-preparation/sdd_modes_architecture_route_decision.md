# SDD Modes Architecture Route Decision - Repository Physical Normalization

## Estado

| Campo | Valor |
| --- | --- |
| Fase | Architecture / Planning preparation |
| Estado | Closed - DEV-RPN-010 |
| Artefacto evaluado | `specs/spec-001-sdd-modes.architecture.md` |
| Ruta objetivo propuesta | `specs/capabilities/sdd-modes/arch-001-sdd-modes.md` |
| Movimiento fisico | EXECUTED - T-036 |
| Stub legacy | CREATED - T-036 |

## Objetivo

Resolver documentalmente la decision pendiente sobre el tratamiento futuro de `specs/spec-001-sdd-modes.architecture.md` dentro de `Repository Physical Normalization`.

Esta decision preparo el movimiento DEV-RPN-010. La ejecucion autorizada T-035/T-036 movio el contenido canonico, creo stub legacy no normativo y no modifica el baseline cerrado de SDD Modes.

## Opciones evaluadas

| Opcion | Descripcion | Ventajas | Riesgos |
| --- | --- | --- | --- |
| A | Mover a `specs/capabilities/sdd-modes/arch-001-sdd-modes.md` y convertir la ruta raiz en stub. | Alinea la arquitectura con el modelo fisico aprobado, elimina excepcion permanente, mejora simetria con la Specification ya movida. | Requiere actualizar referencias activas y preservar referencias historicas mediante stub. |
| B | Mantener `specs/spec-001-sdd-modes.architecture.md` como excepcion canonica permanente. | Menor cambio inmediato, cero coste de movimiento. | Mantiene deuda fisica, rompe convencion `specs/capabilities/<id>/arch-001-*`, obliga a reglas especiales de carga. |

## Reference Map resumido

Barrido realizado con `rg` sobre la ruta legacy exacta, el nombre de archivo legacy y la ruta objetivo propuesta.

| Superficie | Referencias detectadas | Tratamiento propuesto |
| --- | --- | --- |
| Baseline SDD Modes activo | `docs/capabilities/sdd-modes/tasks.md`, `docs/capabilities/sdd-modes/context_refs.md`, `docs/capabilities/sdd-modes/sdd_readiness_assessment.md`, `specs/capabilities/sdd-modes/spec-001-sdd-modes.md` | Actualizar a ruta objetivo durante la ola autorizada; son artefactos del expediente SDD Modes ya normalizado. |
| Indices globales | `docs/capabilities/index.md`, `specs/capabilities/index.md` | Actualizar a ruta objetivo cuando el movimiento se ejecute. |
| Repository Physical Normalization activo | Project Brief, Context References, SPEC, ARCH, Tasks, GEP package | Actualizar las referencias vivas a la decision propuesta/ejecutada; conservar menciones historicas T-022/T-028 como historicas. |
| Capacidades cerradas no activas | Project Consolidation and Closure, Foundation Derivation and Project Initialization, Consolidation Agent | Mantener referencias historicas; la ruta legacy stub preservara navegacion y trazabilidad. |
| Evidencia retrospectiva | `docs/capabilities/consolidation-agent/validations/sdd-modes-retrospective/*` | Mantener referencias historicas; no reescribir evidencia cerrada. |
| Artefacto legacy en si mismo | `specs/spec-001-sdd-modes.architecture.md` contiene autoreferencia textual. | Tras movimiento, mantener contenido normativo intacto salvo referencias de ruta si Development lo autoriza expresamente; stub legacy cubre autoreferencia historica si se conserva. |

## Decision arquitectonica propuesta

Decision propuesta: `Option A`.

Mover en una futura ola autorizada:

```text
specs/spec-001-sdd-modes.architecture.md
  -> specs/capabilities/sdd-modes/arch-001-sdd-modes.md
```

y convertir la ruta legacy en stub de compatibilidad:

```text
specs/spec-001-sdd-modes.architecture.md
```

## Justificacion

- La Specification de SDD Modes ya fue movida a `specs/capabilities/sdd-modes/spec-001-sdd-modes.md`.
- La arquitectura pertenece a la misma capacidad cerrada y debe compartir el mismo directorio canonico.
- El patron `arch-001-<capability-id>.md` ya se usa para capacidades posteriores.
- Las referencias activas pueden actualizarse en una ola controlada.
- Las referencias historicas no necesitan reescritura si la ruta raiz queda como stub no normativo.
- El rollback es viable porque el cambio es un unico movimiento con un unico stub legacy.

## Precondiciones antes de ejecutar

1. Reviewer Agent debe revisar esta decision, Reference Map y planes actualizados.
2. QA Gate Agent debe validar readiness de la ola Architecture route normalization.
3. Debe existir autorizacion humana explicita posterior.
4. El worktree debe auditarse inmediatamente antes del movimiento.
5. Debe confirmarse que no se crean scripts, tools, workflows ni automatizaciones.

## Movimiento ejecutado

| ID | Accion | Origen | Destino | Compatibilidad |
| --- | --- | --- | --- | --- |
| DEV-RPN-010 | Move + rename | `specs/spec-001-sdd-modes.architecture.md` | `specs/capabilities/sdd-modes/arch-001-sdd-modes.md` | Stub legacy creado en ruta origen. |

## Compatibilidad ejecutada

El stub legacy declara:

- ruta canonica nueva;
- que no es fuente normativa;
- que existe por compatibilidad historica;
- decision humana y gate que autorizaron la ola;
- que el contenido normativo vive en `specs/capabilities/sdd-modes/arch-001-sdd-modes.md`.

## Rollback viable

Rollback de DEV-RPN-010:

1. Restaurar `specs/spec-001-sdd-modes.architecture.md` como archivo canonico completo.
2. Retirar o revertir el stub legacy.
3. Revertir `specs/capabilities/sdd-modes/arch-001-sdd-modes.md` si fue creado por movimiento.
4. Restaurar indices y referencias activas a la ruta legacy.
5. Registrar el rollback en `movement_execution_report.md`, `tasks.md` y checklist.

## Condiciones residuales

- La opcion A fue ejecutada solo tras QA Gate T-034 y autorizacion humana T-035.
- Las referencias historicas de capacidades cerradas no deben reescribirse salvo decision explicita de reentrada.
- El contenido normativo de SDD Modes Architecture no cambia por el movimiento.
- Cualquier ejecucion adicional fuera de DEV-RPN-010 requiere nueva decision/gate.

## Siguiente paso

```text
No active next step. DEV-RPN-010 closed by human decision.
```
---

## Reviewer Result - T-033

Decision: `Approved with minor changes`.

Resultado:

- decision `Option A` aprobada para pasar a QA Gate;
- no hay hallazgos criticos ni importantes;
- DEV-RPN-010 no fue ejecutado durante Reviewer T-033;
- no se crea stub legacy;
- durante Reviewer T-033, la ruta legacy seguia intacta y la ruta objetivo no estaba creada;
- correcciones menores de estado documental aplicadas.

Siguiente paso:

```text
No active next step. DEV-RPN-010 closed by human decision.
```
---

## QA Gate Result - T-034

Decision: `Pass with minor conditions`.

QA Gate valida que la decision `Option A` puede pasar a decision humana explicita. La validacion no ejecuta DEV-RPN-010, no crea stub legacy y no modifica el contenido normativo de SDD Modes Architecture.

Condiciones menores antes de ejecucion:

- autorizacion humana explicita T-035;
- Reference Map final inmediatamente antes de mover;
- auditoria de worktree;
- stub legacy no normativo;
- Review y QA post-ejecucion.

Siguiente paso:

```text
No active next step. DEV-RPN-010 closed by human decision.
```