# Gate de readiness para Consolidation

## Proposito

Este gate conceptual comprueba si una capacidad SDD puede entrar en `Consolidation`.

Es un gate documental. No es un workflow ejecutable y no sustituye la aprobacion humana.

---

## Inputs requeridos

- Specification aprobada.
- Architecture aprobada, cuando aplique.
- Plan de tareas o registro de decisiones.
- Readiness assessment vigente.
- Decision de Reviewer.
- Indice de evidencias, cuando exista.
- Registro de deuda residual, cuando exista deuda.
- Restricciones de Development, runtime, tools y workflows.

---

## Comprobaciones minimas

| Comprobacion | Resultado esperado |
| --- | --- |
| La fase actual esta identificada | Pass / Partial / Fail |
| La capacidad tiene trazabilidad suficiente | Pass / Partial / Fail |
| Los artefactos obligatorios existen | Pass / Partial / Fail |
| La revision esta completada | Pass / Partial / Fail |
| El expediente historico esta preservado | Pass / Partial / Fail |
| La deuda residual es visible | Pass / Partial / Fail |
| Los puntos de reentrada estan definidos para deuda pendiente | Pass / Partial / Fail |
| No hay Development, runtime, tools, workflows ni agentes reales no autorizados | Pass / Partial / Fail |

---

## Decisiones posibles

- `Pass`: la capacidad puede entrar en Consolidation.
- `Pass with conditions`: la capacidad puede entrar en Consolidation con condiciones documentadas.
- `Changes requested`: se requieren correcciones documentales.
- `Blocked`: faltan evidencias, revision, trazabilidad o decision humana.

---

## Resultado

El resultado del gate debe indicar:

- fase actual;
- fase destino;
- decision;
- condiciones;
- deuda residual;
- si Development permanece no autorizado;
- siguiente agente recomendado.