# Compatibility Plan - Repository Physical Normalization

## Estado

| Campo | Valor |
| --- | --- |
| Fase | Governed Execution Preparation |
| Estado | Draft for review |
| Development | NOT AUTHORIZED |
| Cambios de compatibilidad | NOT AUTHORIZED |

## Objetivo

Garantizar que una normalizacion fisica futura no rompa enlaces, referencias, trazabilidad, handovers ni compatibilidad con proyectos derivados.

## Compatibilidad documental

| Area | Riesgo | Regla futura |
| --- | --- | --- |
| Enlaces markdown internos | Referencias rotas por movimiento de rutas. | Actualizar enlaces en artefactos activos y preservar rutas legacy mediante stubs si se autoriza. |
| Referencias historicas | Reescritura indebida de evidencias cerradas. | Mantener referencias historicas cuando documenten el estado original. |
| Indices globales | Navegacion desalineada. | Actualizar `docs/capabilities/index.md` y `specs/capabilities/index.md` junto con el movimiento futuro. |
| Handovers | Puntos de reentrada apuntan a rutas antiguas. | Actualizar handovers activos; en handovers cerrados, preferir nota historica o stub. |
| `context_refs` | Carga de contexto incompleta. | Actualizar context refs de capacidades activas; conservar semantica de indice, no policy. |
| Agentes | Instrucciones cargan rutas raiz esperadas. | Distinguir convencion generica del harness de rutas historicas de SDD Modes. |
| Proyectos derivados | Foundation derivada espera estructura estable. | Publicar mapa de rutas canonicas y compatibilidad legacy antes de derivar nuevas plantillas. |

## Estrategia futura de compatibilidad legacy

La primera ejecucion futura debe preferir una estrategia no destructiva:

1. Mover artefactos solo con autorizacion de Development.
2. Mantener rutas legacy como stubs de routing si se autoriza explicitamente.
3. No eliminar rutas legacy en la primera pasada.
4. Actualizar indices y referencias activas hacia rutas canonicas.
5. Mantener evidencia cerrada como historica cuando su valor sea precisamente registrar la ruta original.

## Reglas para stubs futuros

Los stubs no se crean en esta fase. Si se autorizan en Development futuro, deben:

- declarar que la ruta canonica se encuentra en el nuevo destino;
- no duplicar contenido normativo completo;
- mantener trazabilidad hacia la decision humana y el movement plan ejecutado;
- ser revisables y eliminables solo por decision posterior;
- no ocultar que la ruta legacy ya no es canonica.

## Compatibilidad con baselines cerrados

La normalizacion fisica futura puede cambiar ubicacion de un baseline cerrado, pero no su contenido normativo.

Cualquier ajuste dentro de un archivo cerrado debe limitarse a navegacion, routing o metadatos de ruta, y debe ser aprobado como parte de Development futuro. Si eso no se autoriza, la compatibilidad debe resolverse por fuera del contenido cerrado.

## Criterio de aceptacion

Reviewer y QA deben poder comprobar que:

- todas las rutas legacy criticas tienen tratamiento definido;
- no hay estrategia basada en eliminar historia Git;
- los proyectos derivados tienen una ruta canonica clara;
- las referencias historicas se distinguen de las referencias activas;
- ningun cambio de compatibilidad se ejecuta antes de Development.