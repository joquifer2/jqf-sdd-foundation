# Template de registro de deuda residual

## Proposito

Este template define la estructura para documentar deuda residual aceptada durante Consolidation o cierre de una capacidad SDD.

La deuda residual debe permanecer visible tras el cierre e incluir responsable, impacto, estado y punto de reentrada.

---

## Metadatos

| Campo | Valor |
| --- | --- |
| Capacidad | |
| SDD Mode | |
| Responsable | |
| Ultima actualizacion | |
| Handover relacionado | |

---

## Registro de deuda

| Debt ID | Descripcion | Tipo | Estado | Impacto | Bloquea avance | Responsable | Punto de reentrada | Evidencia requerida para cerrar |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| | | Tecnica / Metodologica / Gobernanza / Documental / Empirica | Abierta / Aceptada / Cerrada / Diferida | Alto / Medio / Bajo | Si / No | | | |

---

## Reglas de reentrada

- Una deuda no puede cerrarse silenciosamente.
- Una deuda no puede ocultarse marcando una capacidad como `Closed`.
- Una deuda con impacto bloqueante debe indicar el gate o decision humana necesaria antes de continuar.
- Una deuda puede referenciar historial Git, gates, revisiones o evidencia externa, pero su estado actual debe poder leerse desde este registro.
- Development permanece `NOT AUTHORIZED` salvo decision humana explicita futura y gate aplicable.