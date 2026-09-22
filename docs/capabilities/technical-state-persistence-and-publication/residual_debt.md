# Residual Debt — SDD Technical State Persistence & Publication

## Metadatos

| Campo | Valor |
| --- | --- |
| Capacidad | SDD Technical State Persistence & Publication |
| SDD Mode | Undeclared — baseline conservador equivalente a SDD Full |
| Responsable | Jordi Quiroga |
| Ultima actualizacion | 2026-09-22 |
| Handover relacionado | `closure_handover.md` |

## Registro

| Debt ID | Descripcion | Tipo | Estado | Impacto | Bloquea cierre Foundation | Responsable | Punto de reentrada | Evidencia requerida |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| TSPP-DEBT-001 | Validar que JQF Project Initializer preserva la nueva policy en futuras derivaciones. | Gobernanza / Compatibilidad | Resuelta | Medio | No | Jordi Quiroga | N/A — validacion downstream completada. | PASS: `sdd-project-initializer` commit `5bcacccf9b2adafa08d668c0276c80ba24d8375e`; `npm test` 76 pass / 0 fail / 0 skipped / 0 cancelled. |

## Reglas

No existe migracion automatica para proyectos derivados ya existentes. Su adopcion, si se desea, debe tratarse como incremento separado.

## Cierre TSPP-DEBT-001

Validacion downstream completada el 2026-09-22. El Initializer no requirio cambios de logica productiva: se añadio exclusivamente una prueba de derivacion que demuestra que la baseline Foundation preserva la policy, la responsabilidad del Implementation Agent y los conceptos de glosario aplicables. Suite completa ejecutada sobre `5bcacccf9b2adafa08d668c0276c80ba24d8375e`: **76 pass / 0 fail / 0 skipped / 0 cancelled**. El fallo inicial `spawn EPERM` dentro del sandbox fue ambiental; la repeticion fuera del sandbox paso completamente.
