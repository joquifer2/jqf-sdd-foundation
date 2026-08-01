# Residual Debt - Foundation Derivation and Project Initialization

## Proposito

Este registro documenta la deuda residual aceptada durante la preparacion de cierre de la capacidad `Foundation Derivation and Project Initialization`.

La deuda residual aqui listada no bloquea el Closure Gate si permanece visible, clasificada y con punto de reentrada.

Development permanece `NOT AUTHORIZED`.

---

## Metadatos

| Campo | Valor |
| --- | --- |
| Capacidad | Foundation Derivation and Project Initialization |
| SDD Mode | SDD Full |
| Responsable | Jordi Quiroga |
| Ultima actualizacion | 2026-08-01 |
| Handover relacionado | `docs/capabilities/foundation-derivation-and-project-initialization/closure_handover.md` |

---

## Registro de deuda

| Debt ID | Descripcion | Tipo | Estado | Impacto | Bloquea cierre | Responsable | Punto de reentrada | Evidencia requerida para cerrar |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| FDR-RES-001 | Versionado formal del baseline exportable no definido. | Gobernanza | Aceptada | Medio | No | Jordi Quiroga | Fase futura autorizada de versionado/documentacion | Decision sobre tag, commit, release note, handover o artefacto dedicado. |
| FDR-RES-002 | Matriz completa por ruta del paquete derivable no definida. | Documental | Aceptada | Alto para implementacion futura | No | Jordi Quiroga | Documentation posterior o Repository Physical Normalization | Matriz por ruta revisada y validada. |
| FDR-RES-003 | Representacion final del origen Foundation (`foundation_origin.yml` vs seccion en `context_refs.md`) pendiente. | Gobernanza | Aceptada | Medio | No | Jordi Quiroga | Fase futura autorizada previa a derivacion real | Decision documentada y trazada. |
| FDR-RES-004 | `Derivation Readiness Gate` real no definido. | Validacion | Aceptada | Alto para aplicacion real | No | Jordi Quiroga | Futura capacidad/gate de derivacion | Gate documentado y revisado antes de usarlo en repositorio real. |
| FDR-RES-005 | Falta validacion empirica con primer repositorio derivado real. | Empirica | Aceptada | Medio | No | Jordi Quiroga | Primer caso real de derivacion | Evidencia de aplicacion y QA Gate correspondiente. |
| FDR-RES-006 | `Consolidation Agent` permanece futuro y no implementado. | Metodologica | Aceptada | Medio | No | Jordi Quiroga | Nueva capacidad SDD separada | Specification y Architecture propias, con autorizacion explicita. |
| FDR-RES-007 | `Repository Physical Normalization` permanece futura y no iniciada. | Estructural | Aceptada | Alto para paquete fisico | No | Jordi Quiroga | Nueva capacidad SDD separada | Specification, Architecture y autorizacion explicita para normalizacion fisica. |

---

## Capacidades futuras relacionadas

| Capacidad futura | Relacion | Estado |
| --- | --- | --- |
| Consolidation Agent | Podria asistir en clasificacion de baseline exportable y expedientes internos. | Future / Not implemented |
| Repository Physical Normalization | Podria definir estructura fisica del paquete derivable y matriz por ruta. | Future / Not started |
| Derivation Readiness Gate | Podria validar una derivacion real antes de aplicarla sobre un repositorio. | Future / Not defined |
| Foundation Upgrade Intake | Podria gobernar adopcion de mejoras desde Foundation hacia derivados. | Future / Conceptual in ARCH-001 |

---

## Reglas de reentrada

- Una deuda no puede cerrarse silenciosamente.
- Una deuda no puede ocultarse marcando la capacidad como `Closed`.
- Una deuda con impacto sobre implementacion futura requiere decision humana y gate aplicable antes de ejecutarse.
- Ninguna deuda residual autoriza Development.
- Ninguna deuda residual autoriza scripts, workflows, asistentes reales ni reorganizacion fisica.
- Las capacidades futuras deben abrirse como capacidades SDD separadas o fases futuras explicitamente autorizadas.