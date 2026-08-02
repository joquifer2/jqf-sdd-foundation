# Registro de deuda residual - Consolidation Agent

## Proposito

Este documento registra deuda residual aceptada o diferida durante Development del MVP de `Consolidation Agent`.

La deuda residual permanece visible y no queda cerrada por el handover.

---

## Metadatos

| Campo | Valor |
| --- | --- |
| Capacidad | Consolidation Agent |
| SDD Mode | SDD Full |
| Responsable | Jordi Quiroga |
| Ultima actualizacion | 2026-08-02 |
| Handover relacionado | `docs/capabilities/consolidation-agent/closure_handover.md` |

---

## Registro de deuda

| Debt ID | Descripcion | Tipo | Estado | Impacto | Bloquea avance | Responsable | Punto de reentrada | Evidencia requerida para cerrar |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| CA-RD-001 | No existe template standalone de `Consolidation Agent Report`; el MVP usa secciones en handover/evidence/readiness. | Documental | Aceptada / Future | Medio | No | Jordi Quiroga / Documentation Agent | Futura fase Documentation si se decide crear template reutilizable. | Decision humana sobre formato y template creado/revisado. |
| CA-RD-002 | No existen scripts, tools ni automatizaciones de checks de consolidacion. | Tecnica / Gobernanza | Aceptada / Future | Bajo | No | Jordi Quiroga / Implementation Agent futuro | Nueva capacidad Development si se autorizan automatizaciones no sustitutivas de QA/humano. | SPEC/ARCH nuevas, Development Gate y validacion de no sustitucion de QA. |
| CA-RD-003 | Repository Physical Normalization permanece fuera de alcance. | Gobernanza / Documental | Aceptada / Future | Medio | No | Jordi Quiroga / Architect Agent futuro | Nueva capacidad SDD separada para normalizacion fisica. | Autorizacion humana, Architecture/Documentation especifica y QA Gate. |
| CA-RD-004 | Validacion retrospectiva sobre SDD Modes fue no destructiva y no produjo cierre nuevo del expediente SDD Modes. | Empirica / Documental | Aceptada / Condition | Bajo | No | Jordi Quiroga / QA Gate Agent | Reentrada especifica si se desea consolidar fisicamente o generar handover propio de SDD Modes. | Nueva decision de reentrada y evidencia de alcance autorizado. |

---

## Reglas de reentrada

- Una deuda no puede cerrarse silenciosamente.
- Una deuda no puede ocultarse marcando una capacidad como `Closed`.
- Una deuda con impacto bloqueante debe indicar el gate o decision humana necesaria antes de continuar.
- Una deuda puede referenciar historial Git, gates, revisiones o evidencia externa, pero su estado actual debe poder leerse desde este registro.
- Development adicional permanece no autorizado salvo decision humana explicita futura y gate aplicable.