# Gate de cierre

## Proposito

Este gate conceptual comprueba si una capacidad SDD puede pasar de `Consolidation` a `Closed`.

Es un gate documental. No es un workflow ejecutable y no sustituye la aprobacion humana.

---

## Inputs requeridos

- Handover de cierre.
- Decision o registro de baseline canonico.
- Referencias del expediente historico.
- Indice de evidencias, cuando aplique.
- Registro de deuda residual, cuando exista deuda.
- Indice o seccion de puntos de reentrada.
- Decision de Reviewer.
- Decision de QA Gate.
- Aprobacion humana explicita de cierre.

---

## Comprobaciones minimas

| Comprobacion | Resultado esperado |
| --- | --- |
| El handover de cierre existe y esta completo | Pass / Partial / Fail |
| Los artefactos de baseline estan identificados | Pass / Partial / Fail |
| El expediente historico es discoverable | Pass / Partial / Fail |
| Los artefactos sustituidos estan etiquetados o indexados | Pass / Partial / Fail |
| La deuda residual es visible y tiene puntos de reentrada | Pass / Partial / Fail |
| La guia de carga futura es clara | Pass / Partial / Fail |
| No se elimina ni oculta evidencia | Pass / Partial / Fail |
| No ha ocurrido Development, runtime, tools, workflows ni creacion de agente no autorizados | Pass / Partial / Fail |

---

## Decisiones posibles

- `Pass`: la capacidad puede marcarse como `Closed`.
- `Pass with conditions`: la capacidad puede cerrarse con condiciones residuales explicitas.
- `Changes requested`: el cierre requiere correcciones documentales.
- `Blocked`: faltan evidencias, aprobacion o gestion de deuda.

---

## Resultado

El resultado del gate debe indicar:

- estado final;
- baseline cerrado;
- deuda residual;
- puntos de reentrada;
- restricciones que siguen activas;
- responsable de cualquier seguimiento posterior al cierre.