# Brief de proyecto - Repository Physical Normalization

## 1. Vision general del proyecto

### Nombre del proyecto

JQF SDD Foundation - Repository Physical Normalization

### Titulo de trabajo

Normalizacion fisica del repositorio

### Estado

Closed with minor conditions

### Responsable

Jordi Quiroga

### Ultima actualizacion

2026-08-02

---

### SDD Mode

Modo declarado para el proyecto:

- `SDD Full`

Justificacion humana del modo seleccionado:

Esta capacidad define el proceso oficial para transformar la estructura fisica de `jqf-sdd-foundation` de forma controlada, trazable, reversible y compatible con baselines cerrados y futuros repositorios derivados. Afecta rutas, referencias, indices, expedientes historicos, baseline canonico y reglas de precedencia documental. Requirio specification completa antes de cualquier Architecture; Development y cualquier movimiento fisico siguen requiriendo autorizacion futura.

Responsable de la decision:

Jordi Quiroga

Fecha de declaracion:

2026-08-02

Condiciones relevantes de riesgo:

- no mover, copiar, renombrar, eliminar ni sustituir archivos durante Specification;
- no modificar el baseline aprobado de capacidades cerradas;
- no convertir propuestas del `Consolidation Agent` en ejecucion automatica;
- mantener compatibilidad de enlaces, referencias cruzadas y contexto de agentes;
- preservar historia Git y trazabilidad documental.

Disparadores de reevaluacion:

- decision humana T-008 que autoriza Architecture documental;
- decision humana que autorice Development o movimiento fisico;
- cambio de alcance que incluya scripts, automatizaciones o workflows;
- evidencia de enlaces rotos o referencias no inventariadas;
- necesidad de aplicar el proceso sobre una capacidad distinta de `SDD Modes`.

---

## 2. Proposito

Definir el proceso oficial de normalizacion fisica del repositorio para alinear la organizacion fisica con el modelo metodologico aprobado por la Foundation.

Esta capacidad especifica que debe ocurrir y bajo que reglas. En la fase `Governed Execution Preparation` prepara el paquete documental definitivo para evaluar una autorizacion futura de Development, pero no ejecuta la reorganizacion.

---

## 3. Contexto de negocio

La Foundation ya cuenta con baseline cerrado para:

- `SDD Modes`;
- `SDD Project Consolidation and Closure`;
- `Foundation Derivation and Project Initialization`;
- `Consolidation Agent`.

El `Consolidation Agent` fue implementado y validado mediante una consolidacion retrospectiva no destructiva sobre `SDD Modes`. El resultado fue `Closed with conditions / PASS WITH CONDITIONS`, sin modificar el baseline aprobado de `SDD Modes`.

La validacion produjo una propuesta suficientemente madura para reorganizar fisicamente el repositorio, pero esa propuesta sigue siendo `proposal-only`.

---

## 4. Problema

La estructura fisica actual del repositorio todavia refleja la evolucion historica del proyecto. Existen diferencias entre:

- organizacion logica;
- organizacion fisica;
- navegacion documental;
- ubicacion definitiva de expedientes;
- ubicacion del baseline canonico;
- referencias cruzadas y rutas usadas por agentes.

Sin un proceso oficial, cualquier movimiento podria romper enlaces, duplicar fuentes de verdad, ocultar deuda residual, invalidar referencias historicas o parecer una modificacion normativa de capacidades cerradas.

---

## 5. Resultado esperado

Una specification completa, una Architecture documental conceptual y un paquete de `Governed Execution Preparation` suficientemente detallados para que Reviewer y QA Gate puedan evaluar si procede solicitar autorizacion humana de Development en una fase posterior.

`SDD Modes` queda definido como primer caso real de aplicacion futura, sin moverlo todavia.

---

## 6. Alcance

### Dentro de alcance

- Definir objetivos, principios, alcance y restricciones del proceso.
- Definir actores, entradas y salidas.
- Definir la organizacion fisica objetivo.
- Definir reglas de movimiento, copia, conservacion, archivo y sustitucion.
- Definir reglas de precedencia y compatibilidad.
- Definir reglas para actualizar indices, enlaces, referencias cruzadas, handovers y `context_refs`.
- Definir reversibilidad y trazabilidad minima.
- Definir criterios de aceptacion y Definition of Done.
- Definir como aplicar el proceso sobre `SDD Modes` como primer caso real futuro.
- Definir como reutilizar el proceso para capacidades futuras cerradas.
- Definir la frontera con `Consolidation Agent`.
- Preparar Canonical Route Registry, Reference Map, Movement Plan, Compatibility Plan, Rollback Plan, Validation Checklist y SDD Modes Pilot Package como artefactos documentales no ejecutables.

### Fuera de alcance

- Mover archivos.
- Copiar archivos como parte de una migracion real.
- Renombrar archivos.
- Eliminar archivos.
- Reorganizar el repositorio.
- Modificar baselines aprobados.
- Modificar capacidades cerradas.
- Crear Architecture sin autorizacion humana explicita.
- Crear stubs, scripts, tools, workflows o automatizaciones.
- Autorizar Development.
- Introducir cambios funcionales.

---

## 7. Usuarios y stakeholders

### Usuarios principales

- Responsable de `jqf-sdd-foundation`.
- Mantenedores de la Foundation.
- Agentes metodologicos del SDD Harness.

### Usuarios secundarios

- Revisores y responsables de QA.
- Propietarios de repositorios derivados.
- Futuros agentes que carguen contexto de capacidades cerradas.

### Stakeholders

- Jordi Quiroga.
- Repositorios derivados que usen la Foundation como baseline metodologico.

---

## 8. Supuestos

- Las capacidades listadas en el contexto estan cerradas o cerradas con condiciones.
- La reorganizacion fisica requerira una fase futura autorizada.
- Git conserva historia, pero los usuarios y agentes necesitan rutas vigentes claras.
- Los indices globales son catalogos de routing, no fuentes normativas.
- `SDD Modes` es el primer caso real porque conserva expediente raiz historico.

---

## 9. Restricciones

- Mantener esta capacidad en `Governed Execution Preparation` tras autorizacion humana T-013, sin avanzar a Development.
- No crear Architecture fuera de la autorizacion documental T-008.
- No autorizar Development.
- No mover, renombrar, eliminar ni sustituir archivos.
- No modificar rutas existentes.
- No modificar baselines aprobados.
- No crear scripts ni automatizaciones.
- No tratar propuestas del `Consolidation Agent` como cambios aplicados.

---

## 10. Riesgos

| Riesgo | Impacto | Notas |
| --- | --- | --- |
| Ejecutar movimientos durante Specification | Alto | Prohibido por alcance y restricciones. |
| Romper enlaces o referencias cruzadas | Alto | La spec debe exigir inventario previo y estrategia de compatibilidad. |
| Crear doble fuente de verdad | Alto | Debe existir una ruta canonica por artefacto y rutas legacy solo como transicion. |
| Confundir relocation fisica con cambio normativo | Alto | Los movimientos futuros no modifican el contenido aprobado. |
| Ocultar deuda residual de SDD Modes | Medio | Debe migrarse o referenciarse explicitamente en el caso futuro. |
| Automatizar sin gates | Alto | Scripts y workflows quedan fuera de alcance. |

---

## 11. Fuente de verdad

| Fuente | Proposito |
| --- | --- |
| `docs/capabilities/repository-physical-normalization/project_brief.md` | Fuente inicial de alcance, modo y restricciones de esta capacidad. |
| `docs/capabilities/repository-physical-normalization/context_refs.md` | Indice de fuentes consultadas para esta capacidad. |
| `specs/capabilities/repository-physical-normalization/spec-001-repository-physical-normalization.md` | Specification principal de la capacidad. |
| `docs/capabilities/consolidation-agent/validations/sdd-modes-retrospective/consolidation_report.md` | Propuesta retrospectiva no ejecutable sobre `SDD Modes`. |
| `specs/capabilities/project-consolidation-and-closure/spec-001-sdd-project-consolidation-and-closure.md` | Baseline de consolidacion y cierre. |
| `specs/capabilities/project-consolidation-and-closure/arch-001-sdd-project-consolidation-and-closure.md` | Arquitectura documental de expedientes por capacidad y cierre. |

### Referencias de contexto

Documento de referencias de contexto utilizado:

`docs/capabilities/repository-physical-normalization/context_refs.md`

---

## 12. Criterios de exito

- Existe `SPEC-001 - Repository Physical Normalization`.
- La estructura fisica objetivo queda definida.
- Las reglas de movimiento, copia, conservacion, archivo y sustitucion quedan definidas.
- La compatibilidad de enlaces, referencias y agentes queda gobernada.
- La reversibilidad y trazabilidad minima quedan especificadas.
- `SDD Modes` queda identificado como primer caso futuro sin ser modificado.
- La frontera con `Consolidation Agent` queda explicita.
- Development permanece `NOT AUTHORIZED`.

---

## 13. Preguntas abiertas

- Que nivel de compatibilidad legacy sera obligatorio: stubs documentales, aliases, indices, o periodo de coexistencia?
- Se aceptara renombrar `spec-001-sdd-modes.architecture.md` a `arch-001-sdd-modes.md` o se mantendra el nombre legacy por compatibilidad?
- Que agente debera ejecutar fisicamente los movimientos si Development/Documentation futura lo autoriza?
- Que evidencia Git minima debera registrarse para cada movimiento autorizado?
- Deben existir templates especificos para movement plan, reference map y rollback plan?

---

## 14. Siguiente paso recomendado

```text
No active next step. Repository Physical Normalization is Closed with minor conditions.
```

Development adicional permanece `NOT AUTHORIZED` fuera del primer lote ejecutado. No se autoriza normalizacion fisica adicional sin decision/gate aplicable.

---

## Definition of Done

El Brief de proyecto esta completo cuando:

- el problema esta definido;
- el objetivo esta definido;
- el alcance y limites estan definidos;
- el modo SDD esta declarado;
- existen riesgos y criterios de exito;
- existe contexto suficiente para crear la specification inicial y, tras T-008, la Architecture documental sin ejecutar normalizacion fisica.

---

## 15. Architecture Authorization Addendum

Fecha: 2026-08-02.

Decision humana: `Autorizacion de la Architecture documental`.

Alcance autorizado:

- crear `ARCH-001 - Repository Physical Normalization`;
- definir componentes, interfaces, alternativas, decisiones y restricciones documentales;
- definir reference map, movement plan y rollback plan como artefactos futuros no ejecutables;
- actualizar el expediente local y catalogos no normativos.

Fuera de autorizacion:

- Development;
- normalizacion fisica;
- movimiento, copia, renombre, sustitucion o eliminacion de archivos;
- scripts, tools, workflows, runtime o automatizaciones;
- modificacion de baselines cerrados;
- cierre de deuda residual.
---

## 16. Governed Execution Preparation Addendum

Fecha: 2026-08-02.

Decision humana: `Governed Execution Preparation` autorizada.

Objetivo autorizado:

Preparar el paquete documental definitivo que permitira a Reviewer Agent y QA Gate Agent decidir si procede recomendar una autorizacion humana posterior de Development para `Repository Physical Normalization`.

Artefactos autorizados:

- `Canonical Route Registry`;
- `Reference Map`;
- `Movement Plan`;
- `Compatibility Plan`;
- `Rollback Plan`;
- `Validation Checklist`;
- `SDD Modes Pilot Package`;
- actualizacion documental del expediente de la capacidad.

Fuera de autorizacion:

- Development;
- movimientos fisicos;
- renombrado de archivos;
- creacion de stubs;
- modificacion de baselines cerrados;
- ejecucion del Movement Plan;
- scripts, herramientas, workflows o automatizaciones.

Siguiente paso recomendado:

```text
No active next step. Repository Physical Normalization is Closed with minor conditions.
```
---

## 17. Governed Execution Preparation Reviewer Addendum

Fecha: 2026-08-02.

Decision de Reviewer Agent: `Approved with minor changes`.

Resultado:

- paquete GEP coherente con T-013 y `SDD Full`;
- sin hallazgos criticos ni importantes;
- correcciones menores de trazabilidad historica aplicadas por Documentation Agent;
- Development y normalizacion fisica permanecen `NOT AUTHORIZED`.

Siguiente paso recomendado:

```text
No active next step. Repository Physical Normalization is Closed with minor conditions.
```
---

## 18. Governed Execution Preparation QA Gate Addendum

Fecha: 2026-08-02.

Decision de QA Gate Agent: `Pass with minor conditions`.

Resultado:

- paquete GEP validado para sostener una decision humana posterior sobre Development;
- no se detecta implementacion prematura;
- no se crearon rutas objetivo de SDD Modes;
- no se crearon stubs, scripts, workflows ni automatizaciones;
- Development y normalizacion fisica permanecen `NOT AUTHORIZED`.

Condiciones menores:

- Development requiere decision humana explicita posterior;
- Reference Map final debe actualizarse inmediatamente antes de cualquier ejecucion futura;
- debe cerrarse la decision sobre la ruta/nombre futuro de `specs/spec-001-sdd-modes.architecture.md` antes de mover o renombrar ese artefacto;
- `SDD Modes` permanece read-only hasta autorizacion futura de Development.

Siguiente paso recomendado:

```text
No active next step. Repository Physical Normalization is Closed with minor conditions.
```
---

## 19. Development Authorization and First Wave Addendum

Fecha: 2026-08-02.

Decision humana: `Autorizo el desarrollo`.

Resultado ejecutado:

- primera ola controlada sobre SDD Modes ejecutada;
- cinco artefactos movidos a rutas canonicas bajo `docs/capabilities/sdd-modes/` y `specs/capabilities/sdd-modes/`;
- cinco stubs legacy creados en las rutas raiz correspondientes;
- `specs/spec-001-sdd-modes.architecture.md` se mantiene en ruta legacy y no se mueve ni renombra en esta ola;
- no se crean scripts, tools, workflows ni automatizaciones;
- no se elimina historia Git;
- no se cierra deuda residual.

Siguiente paso recomendado:

```text
No active next step. Repository Physical Normalization is Closed with minor conditions.
```
---

## 20. Development Reviewer Addendum

Fecha: 2026-08-02.

Decision de Reviewer Agent: `Approved with minor changes`.

Resultado:

- primera ola Development revisada sin hallazgos criticos ni importantes;
- rutas canonicas y stubs legacy verificados;
- `specs/spec-001-sdd-modes.architecture.md` conservada en ruta legacy;
- no se detecta cambio normativo de baseline ni automatizacion nueva;
- correccion menor de estado documental aplicada.

Siguiente paso recomendado:

```text
No active next step. Repository Physical Normalization is Closed with minor conditions.
```
---

## 21. Development QA Gate Addendum

Fecha: 2026-08-02.

Decision de QA Gate Agent: `Pass with minor conditions`.

Resultado:

- primera ola Development validada;
- compatibilidad legacy y stubs confirmados;
- ausencia de cambio normativo de baseline confirmada;
- ausencia de scripts, tools, workflows y automatizaciones confirmada;
- condicion menor documental aplicada en el checklist.

Siguiente paso recomendado:

```text
No active next step. Repository Physical Normalization is Closed with minor conditions.
```
---

## 22. SDD Modes Architecture Route Decision Addendum

Fecha: 2026-08-02.

Agentes: Architect Agent / Tasks Planner Agent.

Decision propuesta:

`Option A` - mover en una futura ola autorizada `specs/spec-001-sdd-modes.architecture.md` a `specs/capabilities/sdd-modes/arch-001-sdd-modes.md` y convertir la ruta raiz en stub de compatibilidad.

Estado:

`Closed - DEV-RPN-010` (estado historico superado: la propuesta fue revisada, validada, autorizada, ejecutada y cerrada).

Evidencia:

- `docs/capabilities/repository-physical-normalization/governed-execution-preparation/sdd_modes_architecture_route_decision.md`
- `docs/capabilities/repository-physical-normalization/governed-execution-preparation/reference_map.md`
- `docs/capabilities/repository-physical-normalization/governed-execution-preparation/movement_plan.md`
- `docs/capabilities/repository-physical-normalization/governed-execution-preparation/compatibility_plan.md`
- `docs/capabilities/repository-physical-normalization/governed-execution-preparation/rollback_plan.md`

Restriccion:

No se ejecuta movimiento, renombre, stub ni actualizacion fisica hasta Reviewer, QA Gate y autorizacion humana explicita.

Siguiente paso recomendado:

```text
No active next step. Repository Physical Normalization is Closed with minor conditions.
```
---

## 23. SDD Modes Architecture Route Reviewer Addendum

Fecha: 2026-08-02.

Decision de Reviewer Agent: `Approved with minor changes`.

Resultado:

- decision `Option A` aprobada para pasar a QA Gate;
- no hay hallazgos criticos ni importantes;
- estado historico superado por T-036: DEV-RPN-010 fue ejecutado tras autorizacion humana;
- estado historico superado por T-036: se creo stub legacy no normativo y no se modifico el baseline cerrado;
- correcciones menores de estado documental aplicadas.

Siguiente paso recomendado:

```text
No active next step. Repository Physical Normalization is Closed with minor conditions.
```
---

## 24. SDD Modes Architecture Route QA Gate Addendum

Fecha: 2026-08-02.

QA Gate Agent emitio `Pass with minor conditions` sobre el paquete DEV-RPN-010.

La decision `Option A` queda lista para decision humana explicita: mover `specs/spec-001-sdd-modes.architecture.md` a `specs/capabilities/sdd-modes/arch-001-sdd-modes.md` y convertir la ruta raiz en stub legacy no normativo.

Este resultado no ejecuta el movimiento, no crea stub, no modifica baselines cerrados y no autoriza por si solo Development adicional.

Siguiente decision requerida historica: T-035, autorizacion humana explicita o rechazo de DEV-RPN-010. Estado superado por T-035/T-036/T-039.

---

## 25. DEV-RPN-010 Closure Addendum

Fecha: 2026-08-02.

Decision humana: `Autorizo el cierre`.

DEV-RPN-010 queda cerrado tras ejecucion, Reviewer T-037 y QA Gate T-038. No queda autorizacion abierta para movimientos adicionales.

---

## 26. Post-Development Reconciliation Addendum

Fecha: 2026-08-02.

Estado real reconciliado:

- DEV-RPN-010: `Closed`.
- T-001 a T-039: `Completed`.
- SDD Modes Specification y Architecture viven en rutas capability-local.
- Rutas raiz conservadas como `Temporary compatibility stubs` no normativos.
- El contenido normativo de SDD Modes no fue modificado.
- Development adicional permanece `NOT AUTHORIZED`.
- No existe siguiente paso activo dentro de DEV-RPN-010.

Artefactos de cierre creados:

- `docs/capabilities/repository-physical-normalization/evidence_index.md`.
- `docs/capabilities/repository-physical-normalization/residual_debt.md`.
- `docs/capabilities/repository-physical-normalization/closure_handover.md`.

Siguiente accion valida:

```text
No active next step. Repository Physical Normalization is Closed with minor conditions.
```

---

## 27. Global Closure Gate Addendum

Fecha: 2026-08-02.

Decision de QA Gate Agent: `Pass with minor conditions`.

Resultado:

- el cierre global de `Repository Physical Normalization` queda validado para decision humana;
- DEV-RPN-010 esta cerrado;
- T-001 a T-041 estan completadas;
- la deuda residual de stubs temporales queda aceptada y gobernada;
- Development adicional permanece `NOT AUTHORIZED`.

Decision humana T-041:

```text
No active next step. Repository Physical Normalization is Closed with minor conditions.
```
---

## 28. Global Closure Human Decision Addendum

Fecha: 2026-08-02.

Decision humana: `Adelante con el cierre global`.

Resultado:

`Repository Physical Normalization` queda `Closed with minor conditions`.

No queda siguiente paso activo dentro de la capacidad. Development adicional permanece `NOT AUTHORIZED`; cualquier reentrada futura requiere decision humana explicita y gates aplicables.