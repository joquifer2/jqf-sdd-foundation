# Registro de deuda residual - SDD Project Consolidation and Closure

## Proposito

Este registro documenta la deuda residual aceptada en el cierre de `SDD Project Consolidation and Closure`.

La deuda residual permanece visible tras el cierre e incluye responsable, impacto, estado y punto de reentrada.

---

## Metadatos

| Campo | Valor |
| --- | --- |
| Capacidad | SDD Project Consolidation and Closure |
| SDD Mode | SDD Full |
| Responsable | Jordi Quiroga |
| Ultima actualizacion | 2026-08-01 |
| Handover relacionado | `docs/capabilities/project-consolidation-and-closure/closure_handover.md` |

---

## Registro de deuda

| Debt ID | Descripcion | Tipo | Estado | Impacto | Bloquea avance | Responsable | Punto de reentrada | Evidencia requerida para cerrar |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| RD-001 | No existen la definicion canonica del `Consolidation Agent` ni su adaptador Codex. | Gobernanza / Documental | Deuda futura aceptada | Medio | No para cerrar esta capacidad; si para usar un `Consolidation Agent` real mas adelante | Jordi Quiroga | Abrir una capacidad SDD separada para crear el `Consolidation Agent` canonico. | Specification, Architecture, Reviewer y QA Gate aprobados para esa capacidad futura. |
| RD-002 | El cierre final de esta capacidad estaba pendiente antes de Closure Gate T-029. | Gobernanza | Cerrada por Closure Gate T-029 | Medio | No | Jordi Quiroga | No requiere reentrada. | Handover de cierre, indice de evidencias, registro de deuda residual, Reviewer T-028, Closure Gate T-029 y aprobacion humana explicita. |
| RD-003 | No se ha realizado reorganizacion fisica del repositorio ni movimiento de baseline. | Documental / Gobernanza | Restriccion aceptada | Bajo | No | Jordi Quiroga | Abrir una tarea o capacidad Architecture/Documentation separada si se desea movimiento fisico. | Aprobacion humana explicita mas Architecture o decision de gate actualizada. |
| RD-004 | El baseline raiz de `SDD Modes` permanece cerrado y no se consolida en un nuevo paquete fisico por esta capacidad. | Metodologica / Documental | Restriccion aceptada | Bajo | No | Jordi Quiroga | Abrir una capacidad de consolidacion separada para SDD Modes si se desea un paquete fisico de baseline. | Decision explicita de alcance que permita tocar o reclasificar artefactos raiz de SDD Modes. |

---

## Reglas de reentrada

- Una deuda no puede cerrarse silenciosamente.
- Una deuda no puede ocultarse marcando una capacidad como `Closed`.
- Una deuda con impacto bloqueante debe indicar el gate o la decision humana necesaria antes de continuar.
- Una deuda puede referenciar historial Git, gates, revisiones o evidencia externa, pero su estado actual debe poder leerse desde este registro.
- Development permanece `NOT AUTHORIZED` salvo decision humana explicita futura y gate aplicable.