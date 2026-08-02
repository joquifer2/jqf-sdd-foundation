# Rollback Plan - Repository Physical Normalization

## Estado

| Campo | Valor |
| --- | --- |
| Fase | Governed Execution Preparation |
| Estado | Draft for review |
| Development | NOT AUTHORIZED |
| Rollback ejecutable | No, solo definido documentalmente |

## Objetivo

Definir como revertir una ejecucion futura de normalizacion fisica si se detectan referencias rotas, perdida de trazabilidad, incompatibilidad con agentes o incumplimiento de QA.

## Principios

1. Rollback debe ser por olas, no global e indiscriminado.
2. Git history no se elimina ni se reescribe.
3. Cada ola futura debe registrar entradas, salidas y evidencia para poder revertirla.
4. Los stubs o cambios de referencia se revierten despues de restaurar rutas origen.
5. Si hay duda entre conservar trazabilidad y completar normalizacion, prevalece trazabilidad.

## Triggers de rollback futuro

| Trigger | Severidad | Accion |
| --- | --- | --- |
| Ruta canonica incompleta o archivo faltante | Alta | Detener ejecucion y revertir ola afectada. |
| Referencias criticas rotas | Alta | Restaurar ruta anterior o stub, actualizar informe. |
| Baseline cerrado modificado en contenido normativo | Critica | Revertir cambio y escalar a decision humana. |
| Agente metodologico queda sin fuente cargable | Alta | Restaurar compatibilidad legacy. |
| Indices globales inconsistentes | Media | Corregir o revertir ola de indices. |
| QA Gate post-ejecucion falla | Alta | Aplicar rollback segun hallazgo. |

## Matriz de rollback por ola futura

| Ola futura | Elemento afectado | Rollback documental esperado |
| --- | --- | --- |
| DEV-P1 | Directorios objetivo | Eliminar solo directorios nuevos vacios si se autoriza; si contienen artefactos, revertir por commit. |
| DEV-P2 | Resumenes derivados | Retirar o marcar como no canonicos; preservar evidencia original. |
| DEV-P3 | Docs SDD Modes | Restaurar archivos a rutas `docs/*.md` originales o mantener stubs si ya eran necesarios. |
| DEV-P4 | Spec SDD Modes | Restaurar `specs/capabilities/sdd-modes/spec-001-sdd-modes.md` o reforzar stub legacy. |
| DEV-P5 | Architecture SDD Modes | Revertir decision de renombrado/movimiento si rompe compatibilidad. |
| DEV-P6 | Referencias e indices | Revertir referencias a rutas canonicas si las rutas no quedan disponibles. |
| DEV-P7 | Handover post-ejecucion | Registrar fallo, decision y estado restaurado. |

## Evidencia minima futura

Cualquier ejecucion futura debe producir evidencia suficiente para rollback:

- diff antes/despues;
- lista de rutas movidas;
- lista de referencias actualizadas;
- validacion de enlaces o busqueda de referencias pendientes;
- decision humana de ejecucion;
- resultado Reviewer y QA Gate post-ejecucion.

## Limite de esta fase

Este documento no ejecuta rollback porque no se ha ejecutado ningun movimiento. Su funcion es permitir que Reviewer y QA evalúen si el plan futuro seria reversible.

---

## Rollback Addendum - DEV-RPN-010 SDD Modes Architecture Route

Rollback scope:

```text
specs/spec-001-sdd-modes.architecture.md
specs/capabilities/sdd-modes/arch-001-sdd-modes.md
```

Rollback steps:

1. Restaurar `specs/spec-001-sdd-modes.architecture.md` como archivo canonico completo.
2. Retirar o revertir el stub legacy creado durante DEV-RPN-010.
3. Retirar o revertir `specs/capabilities/sdd-modes/arch-001-sdd-modes.md` si fue creado por movimiento.
4. Revertir indices globales a ruta legacy.
5. Revertir referencias activas actualizadas durante la ola.
6. Registrar causa, decision y validacion posterior.

Rollback triggers:

- QA post-ejecucion falla.
- Referencia activa critica no queda resuelta por actualizacion ni stub.
- El stub se interpreta como segunda fuente normativa.
- Se detecta cambio normativo accidental en el contenido de Architecture.
- Un agente metodologico no puede localizar la arquitectura mediante indice, context refs o stub.

Viabilidad:

Rollback viable. DEV-RPN-010 afecta un artefacto principal, un stub legacy y referencias activas catalogables.