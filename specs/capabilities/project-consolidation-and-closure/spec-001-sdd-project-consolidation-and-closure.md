# Specification

## Metadatos

### Spec ID

SPEC-001

### Title

SDD Project Consolidation and Closure

### Estado

Baseline cerrado

### Responsable

Jordi Quiroga

### Ultima actualizacion

2026-08-01

---

### SDD Mode Reference

Modo declarado para el proyecto o capacidad:

`SDD Full`

Justificacion o referencia canonica:

`docs/capabilities/project-consolidation-and-closure/project_brief.md`

Notas:

- Esta specification no autoriza Development.
- Esta specification no crea Architecture.
- Esta specification no modifica el baseline final de `SDD Modes`.

---

## 1. Proposito

Definir la capacidad metodologica `SDD Project Consolidation and Closure`, responsable de establecer como una capacidad SDD finalizada se consolida dentro de `jqf-sdd-foundation`, que artefactos pasan al baseline canonico, que queda como expediente historico, como se conservan deudas residuales y como se prepara el repositorio para iniciar una nueva capacidad sin sobrescribir la anterior.

---

## 2. Background

La capacidad `SDD Modes` quedo cerrada formalmente con:

- Brief de proyecto `Completed`;
- `SPEC-001 - SDD Modes` en estado `Final`;
- `ARCH-001 - SDD Modes` en estado `Final`;
- `docs/tasks.md` en estado `Final`;
- QA Gate `PASS`;
- readiness `Completed with conditions`;
- Development `NOT AUTHORIZED`;
- tareas T-001 a T-027 cerradas;
- working tree limpio al momento del cierre declarado.

La deuda `VAL-001 - repositorio real para validar SDD Minimal` permanece como `PENDIENTE - non-blocking empirical debt`, con punto de reentrada definido.

El trabajo de `SDD Modes` demostro que los documentos raiz pueden funcionar como expediente de una capacidad concreta, pero tambien evidencio la necesidad de un proceso oficial para cerrar capacidades y separar baseline vigente de historial metodologico.

---

## 3. Objective

La capacidad debe especificar el proceso oficial mediante el cual una capacidad SDD pasa desde su finalizacion hasta su consolidacion definitiva dentro de la Foundation.

El resultado esperado es una definicion suficiente para que futuras fases puedan:

- clasificar artefactos de una capacidad cerrada;
- determinar que pasa al baseline canonico;
- preservar expedientes metodologicos cerrados;
- conservar evidencia historica y deuda residual;
- registrar puntos de reentrada;
- actualizar indices y referencias;
- reducir el contexto necesario para futuras capacidades;
- preparar un handover formal de cierre;
- definir conceptualmente el futuro `Consolidation Agent`.

---

## 4. Alcance

### Included

- Modelo conceptual de consolidacion y cierre.
- Ciclo de vida oficial de una capacidad SDD.
- Estados principales y estados adicionales.
- Actores y responsabilidades.
- Entradas, salidas y reglas de clasificacion documental.
- Definicion conceptual del futuro `Consolidation Agent`.
- Adaptacion del cierre a `SDD Minimal`, `SDD Lite` y `SDD Full`.
- Restricciones, riesgos, dependencias, criterios de aceptacion y decisiones abiertas.
- Backlog inicial para fases posteriores.

### Excluded

- Implementar el `Consolidation Agent`.
- Crear scripts, tools reales, integraciones o workflows ejecutables.
- Crear Architecture.
- Reorganizar fisicamente el repositorio.
- Mover artefactos existentes.
- Modificar el baseline aprobado de `SDD Modes`.
- Eliminar historia Git.
- Ocultar deuda tecnica, metodologica o empirica.
- Redefinir normativa aprobada sin autorizacion.
- Autorizar Development.

---

## 5. Actors

| Actor | Descripcion |
|---------|---------|
| Responsable de Foundation | Aprueba cierre, consolidacion y decisiones de baseline. |
| Maintainer de Foundation | Ejecuta cambios documentales autorizados y preserva coherencia del repositorio. |
| Specification Agent | Define la capacidad y sus limites durante Specification. |
| Architect Agent | Definira posteriormente la estructura documental definitiva si se autoriza Architecture. |
| Tasks Planner Agent | Transformara la spec aprobada en tareas trazables. |
| Reviewer Agent | Revisara coherencia, alcance, contradicciones y calidad documental. |
| Documentation Agent | Actualizara indices, referencias y documentos auxiliares cuando este autorizado. |
| QA Gate Agent | Validara readiness, gates, evidencias y criterios de avance. |
| Implementation Agent | Solo intervendra si una futura fase autoriza Development; no aplica en esta iteracion. |
| Futuro Consolidation Agent | Agente metodologico conceptual responsable de preparar y verificar consolidaciones de capacidades. |

---

## 6. Inputs

| Input | Descripcion |
|----------|----------|
| Brief de proyecto de la capacidad a cerrar | Define alcance, modo, objetivos y criterios de exito originales. |
| Specification final | Define la capacidad aprobada y su fuente normativa principal. |
| Architecture final, si existe | Define estructura conceptual aprobada. |
| Task backlog final | Evidencia tareas cerradas, descartadas, diferidas y decisiones. |
| Readiness / QA Gate | Evidencia decisiones de validacion y condiciones. |
| Referencias de contexto | Indice de fuentes, pendientes, discovery-only y jerarquia. |
| Evidencia historica | Revisiones, gates, decisiones, validaciones y referencias Git. |
| Deuda residual | Pendientes aceptados, no bloqueantes o bloqueantes. |
| Aprobacion humana | Decision explicita para consolidar o cerrar. |

---

## 7. Resultados

| Salida | Descripcion |
|-----------|-----------|
| Baseline canonico actualizado | Conjunto de artefactos vigentes que futuras capacidades deben cargar como referencia principal. |
| Expediente metodologico cerrado | Conjunto de artefactos que explican como se definio, reviso, valido y cerro una capacidad. |
| Inventario de artefactos | Registro de artefactos canonicos, historicos, sustituidos, pendientes y de reentrada. |
| Registro de deuda residual | Deuda aceptada, estado, impacto, responsable y punto de reentrada. |
| Handover formal de cierre | Resumen de estado final, decisiones, condiciones, riesgos residuales y siguiente punto valido. |
| Indices y referencias actualizados | Context references, README, glosario, instrucciones u otros indices cuando Architecture lo autorice. |
| Preparacion para nueva capacidad | Estado documental que permite iniciar nueva capacidad sin sobrescribir el expediente cerrado. |

---

## 8. Fundamental Concepts

Esta seccion actua como glosario normativo local de la capacidad. Architecture debe consumir estas definiciones sin redefinir su semantica salvo decision humana posterior.

### Capacidad

Unidad metodologica de evolucion bajo SDD que puede incluir Brief de proyecto, specifications, architecture, tareas, gates, evidence y documentacion auxiliar.

### Consolidation / Consolidacion

Proceso de clasificar, validar y formalizar el resultado final de una capacidad cerrada para distinguir que queda vigente como baseline y que permanece como historial. Es una fase de gobierno documental; no implica por si misma ejecucion, implementacion, movimiento fisico de archivos ni autorizacion de Development.

### Closure / Cierre

Decision formal que declara que una capacidad no requiere mas trabajo dentro de su alcance actual, conserva sus condiciones o deudas residuales y define sus puntos de reentrada.

### Baseline canonico

Conjunto minimo de artefactos vigentes que representan el estado aprobado de la Foundation despues de una capacidad. Es la referencia que futuras capacidades deben cargar por defecto. No incluye necesariamente todo el expediente historico ni toda la evidencia generada durante la capacidad.

### Closed Methodological Dossier / Expediente Metodologico Cerrado

Expediente historico que conserva el recorrido metodologico de una capacidad: decisiones, tareas, revisiones, gates, evidencia y condiciones. Permanece disponible para auditoria o reentrada, pero no debe confundirse con el baseline canonico vigente.

### Evidencia historica

Material trazable que explica por que una decision fue tomada o aceptada, sin convertirse necesariamente en baseline vigente. Puede incluir gates, revisiones, validaciones, referencias Git, tareas cerradas y decisiones aceptadas.

### Artefacto sustituido

Artefacto sustituido por una version posterior o por un baseline consolidado, conservado como referencia historica cuando aporte trazabilidad. No debe usarse como fuente vigente salvo que una decision posterior lo reactive explicitamente.

### Deuda residual

Pendiente tecnico, metodologico, empirico o documental aceptado explicitamente al cierre, con impacto, estado, responsable y punto de reentrada definidos. Puede ser bloqueante o no bloqueante, pero no puede ocultarse ni eliminarse por el hecho de cerrar la capacidad.

### Punto de reentrada

Condicion o ruta formal mediante la cual una deuda, decision diferida o capacidad cerrada puede reabrirse sin mezclar contextos ni invalidar el cierre anterior. Debe indicar que agente o decision debe intervenir y que evidencia minima se requiere.

### Handover de cierre / Handover Formal de Cierre

Resumen formal que permite transferir una capacidad cerrada a futuras capacidades o agentes sin cargar todo el expediente. Debe incluir estado final, baseline vigente, expediente historico, decisiones finales, condiciones, deuda residual, riesgos residuales, puntos de reentrada y autorizaciones expresamente denegadas o pendientes.

### Operational Product / Producto Operativo

Resultado ejecutable, productivo o funcional que pertenece a Development, Validacion operativa, Active, Operational Harness o a un repositorio derivado. En esta Foundation y en esta capacidad, un producto operativo esta fuera de alcance: la consolidacion definida aqui gobierna documentacion, baseline, evidencia y cierre metodologico, no runtime ni entrega productiva.

---
## 9. Ciclo de vida oficial de capacidad

La Foundation debe utilizar un ciclo de vida unico para capacidades SDD:

```text
Draft
↓
Specification
↓
Architecture
↓
Development
↓
Validacion
↓
Consolidation
↓
Closed
```

### Draft

Idea inicial o necesidad detectada. No autoriza trabajo estructural amplio ni implementacion.

### Specification

Fase de definicion de problema, objetivos, alcance, limites, actores, inputs, outputs, reglas, riesgos y criterios de aceptacion. No autoriza Architecture ni Development por si misma.

### Architecture

Fase de estructura conceptual, documental o tecnica segun el modo y la naturaleza de la capacidad. Solo puede comenzar tras readiness suficiente de Specification.

### Development

Fase de implementacion tecnica o cambios ejecutables. Solo puede comenzar con autorizacion explicita.

### Validacion

Fase de comprobacion de cumplimiento contra specification, architecture, criterios de aceptacion, gates y evidencia.

### Consolidation

Fase de clasificacion final y preparacion de cierre: baseline, expediente, evidencia, deuda residual, indices, decisiones finales y handover.

### Closed

Estado final de una capacidad cerrada. No implica que no existan deudas; implica que las deudas aceptadas tienen tratamiento explicito y punto de reentrada.

### Additional States

| Estado | Funcion |
|---|---|
| On Hold | Trabajo pausado temporalmente sin cancelar la capacidad. Debe conservar motivo, fecha y condicion de reactivacion. |
| Archived | Capacidad conservada solo como historico, sin intencion activa de reentrada. |
| Superseded | Capacidad sustituida por otra decision o capacidad posterior. Debe apuntar al sustituto canonico. |
| Cancelled | Capacidad detenida sin cierre positivo. Debe conservar razon, impacto y artefactos que no deben usarse como baseline. |

---

## 10. Consolidation Model

La consolidacion debe responder, como minimo:

1. Que quedo aprobado.
2. Que queda vigente como baseline.
3. Que queda como expediente historico.
4. Que evidencia debe conservarse.
5. Que artefactos quedan sustituidos o descartados.
6. Que deuda residual permanece abierta.
7. Cual es el punto de reentrada de cada deuda.
8. Que indices y referencias deben actualizarse.
9. Que contexto minimo necesitan futuros agentes.
10. Que aprobacion humana cierra la capacidad.

---

## 11. Document Classification Rules

### Baseline Vigente

Artefactos que futuras capacidades deben tratar como referencia canonica. Deben ser pocos, actuales y estables.

### Expediente Metodologico Cerrado

Artefactos que documentan el proceso de una capacidad cerrada. Se conservan para trazabilidad, pero no deben cargarse completos por defecto si existe un baseline consolidado.

### Evidencia Historica

Revisiones, gates, tareas, decisiones y validaciones que explican el cierre. Puede referenciar Git cuando el detalle cronologico ya vive ahi.

### Artefactos Sustituidos

Documentos reemplazados por baseline posterior. Deben apuntar a la fuente vigente si permanecen en el repo.

### Deuda Residual

Pendientes aceptados con estado, impacto, responsable y reentrada. No puede ocultarse bajo el cierre.

### Puntos de Reentrada

Rutas formales para retomar deuda, reabrir decisiones o iniciar capacidades posteriores.

---

## 12. Consolidation Agent Concept

El futuro `Consolidation Agent` sera un agente metodologico del SDD Harness.

No sera un agente operativo de negocio.

No ejecutara procesos productivos.

No sustituira aprobacion humana.

Responsabilidades conceptuales minimas:

1. Verificar que una capacidad cumple condiciones necesarias para consolidarse.
2. Comprobar gates, aprobaciones y evidencias.
3. Determinar que artefactos pasan al baseline canonico.
4. Distinguir baseline vigente, expediente cerrado, evidencia historica, artefactos sustituidos, deuda residual y puntos de reentrada.
5. Preparar la reorganizacion definitiva del repositorio cuando Architecture lo haya definido y la fase lo autorice.
6. Actualizar o proponer actualizacion de indices y referencias.
7. Consolidar decisiones finales.
8. Reducir el contexto necesario para futuras capacidades.
9. Preparar el repositorio para iniciar una nueva capacidad sin sobrescribir la anterior.
10. Generar un handover formal de cierre.

Limites:

- no implementa runtime;
- no mueve archivos sin autorizacion de fase;
- no elimina evidencia;
- no cambia baseline normativo sin decision humana;
- no cierra deuda ocultandola;
- no autoriza Development.

---

## 13. Adaptation by SDD Mode

### SDD Minimal

Cierre ligero. Debe incluir:

- resultado obtenido;
- decision final;
- ubicacion del output;
- pendientes aceptados;
- decision de archivo o descarte;
- confirmacion de ausencia de riesgos criticos.

### SDD Lite

Consolidacion incremental. Debe incluir:

- baseline vigente del incremento;
- evidencia resumida;
- tareas cerradas o descartadas;
- pendientes y owner;
- riesgos residuales;
- handover minimo;
- referencias a evidencia Git cuando aplique.

### SDD Full

Consolidacion formal. Debe incluir:

- inventario canonico;
- expediente metodologico;
- trazabilidad de decisiones;
- gates y aprobaciones;
- riesgos residuales;
- readiness operativo o decision explicita de no Development;
- handover formal;
- aprobacion humana.

---

## 14. Functional Requirements

### FR-001

La Foundation debe definir un proceso oficial de consolidacion y cierre de capacidades SDD.

### FR-002

El proceso debe distinguir entre baseline vigente, expediente metodologico cerrado, evidencia historica, artefactos sustituidos, deuda residual y puntos de reentrada.

### FR-003

El proceso debe exigir verificacion de gates, aprobaciones y evidencia antes de consolidar.

### FR-004

El proceso debe impedir que una capacidad nueva sobrescriba el expediente de una capacidad cerrada.

### FR-005

El proceso debe reducir el contexto que futuros agentes deben cargar sin eliminar trazabilidad critica.

### FR-006

El proceso debe definir un ciclo de vida oficial de capacidades SDD.

### FR-007

El proceso debe soportar estados adicionales: `On Hold`, `Archived`, `Superseded` y `Cancelled`.

### FR-008

El proceso debe adaptarse a `SDD Minimal`, `SDD Lite` y `SDD Full`.

### FR-009

La capacidad debe definir conceptualmente el futuro `Consolidation Agent`.

### FR-010

El futuro `Consolidation Agent` debe permanecer metodologico y no operativo.

### FR-011

La consolidacion debe generar o preparar un handover formal de cierre.

### FR-012

La consolidacion debe conservar deuda residual con estado, impacto, responsable y punto de reentrada.

### FR-013

La consolidacion debe poder preparar indices y referencias actualizados cuando una fase posterior lo autorice.

### FR-014

La specification no debe implementar reorganizacion, scripts, agentes reales ni workflows ejecutables.

---

## 15. Business Rules

### BR-001

Una capacidad no queda cerrada por ausencia de trabajo pendiente; queda cerrada cuando su estado, baseline, evidencias, deudas y reentradas estan explicitamente clasificados.

### BR-002

El baseline canonico debe ser suficiente para uso futuro, pero no debe absorber todo el expediente historico.

### BR-003

La deuda residual aceptada no bloqueante debe permanecer visible.

### BR-004

Una fuente discovery-only no puede convertirse en normativa durante consolidacion sin decision explicita.

### BR-005

La consolidacion no autoriza Development ni implementacion por si misma.

### BR-006

Toda reorganizacion fisica requiere Architecture aprobada o decision humana equivalente.

### BR-007

El handover de cierre debe ser comprensible sin obligar a cargar todo el historial.

---

## 16. Restricciones

- Estado actual: Specification.
- No crear Architecture.
- No crear `Consolidation Agent` real.
- No mover ni eliminar archivos.
- No modificar baseline cerrado de `SDD Modes`.
- No introducir runtime, scripts, workflows ejecutables, tools o integraciones.
- No redefinir `SDD Modes`.
- Mantener la estructura documental provisional hasta Architecture.

---

## 17. Supuestos

- La consolidacion sera una fase oficial posterior a Validacion y anterior a Closed.
- No todas las capacidades requeriran el mismo nivel de consolidacion.
- La aprobacion humana sigue siendo obligatoria para cierre formal.
- Git puede conservar detalle historico, pero los artefactos canonicos deben apuntar a decisiones finales.
- Architecture definira estructura definitiva de almacenamiento y naming.

---

## 18. Riesgos

| Riesgo | Impacto | Notas |
|--------|--------|--------|
| Consolidacion se interpreta como borrado o limpieza destructiva | Alto | Debe prohibirse eliminar evidencia o historia. |
| Baseline canonico queda demasiado grande | Medio | Se requiere clasificacion y handover. |
| Expedientes cerrados se siguen cargando completos por defecto | Medio | El proceso debe reducir contexto futuro. |
| Deuda residual se oculta | Alto | Debe registrarse con punto de reentrada. |
| Consolidation Agent se implementa prematuramente | Alto | Esta spec solo lo define conceptualmente. |
| Ciclo de vida entra en conflicto con fases actuales del README | Medio | Architecture debe resolver alineacion documental posterior. |

---

## 19. Acceptance Criteria

### AC-001

La specification define el proposito, alcance, objetivos, principios, conceptos, actores, responsabilidades, entradas y salidas.

### AC-002

La specification define un ciclo de vida oficial de capacidad con `Draft`, `Specification`, `Architecture`, `Development`, `Validacion`, `Consolidation` y `Closed`.

### AC-003

La specification define el papel de `On Hold`, `Archived`, `Superseded` y `Cancelled`.

### AC-004

La specification define el modelo conceptual de consolidacion.

### AC-005

La specification define la clasificacion documental requerida.

### AC-006

La specification define conceptualmente el futuro `Consolidation Agent`.

### AC-007

La specification define adaptacion por `SDD Minimal`, `SDD Lite` y `SDD Full`.

### AC-008

La specification registra restricciones que impiden implementacion, reorganizacion fisica o modificacion del baseline de `SDD Modes`.

### AC-009

La specification conserva deuda residual y puntos de reentrada como conceptos obligatorios.

### AC-010

La specification deja decisiones abiertas suficientes para Architecture sin resolverlas prematuramente.

---

## 20. Dependencies

- `docs/capabilities/project-consolidation-and-closure/project_brief.md`
- `docs/capabilities/project-consolidation-and-closure/context_refs.md`
- `docs/project_brief.md`
- `docs/context_refs.md`
- `docs/tasks.md`
- `docs/sdd_readiness_assessment.md`
- `specs/spec-001-sdd-modes.md`
- `specs/spec-001-sdd-modes.architecture.md`
- `.github/instructions/sdd.instructions.md`
- `AGENTS.md`
- `README.md`
- `docs/glosario_terminos.md`

---

## 21. Preguntas abiertas

- Cual sera la estructura definitiva para expedientes metodologicos cerrados?
- Que indice central listara capacidades activas, consolidadas y cerradas?
- Deben existir IDs globales de capacidad independientes de SPEC/ARCH?
- Como se versionara el baseline canonico tras cada consolidacion?
- Que forma exacta tendra el handover formal de cierre?
- Que agente aprueba la entrada a Consolidation?
- Que agente aprueba la transicion de Consolidation a Closed?
- Que partes del cierre pueden automatizarse en el futuro sin sustituir decision humana?
- Como convivira el ciclo `Draft -> ... -> Closed` con el ciclo de trabajo actual descrito en README?

---

## 22. Future Considerations

- Crear Architecture de la capacidad cuando se autorice.
- Definir una matriz de artefactos de consolidacion por modo.
- Definir template de handover de cierre.
- Definir o adaptar indices de capacidades.
- Incorporar el `Consolidation Agent` al catalogo solo en una fase posterior autorizada.
- Evaluar si los documentos raiz actuales deben convertirse en baseline global o expediente historico mediante una consolidacion futura.

---

## 23. Analisis de impacto entre artefactos

| Artefacto | Impacto | Accion requerida |
|------------|------------|------------|
| Brief de proyecto de esta capacidad | Creado como fuente canonica inicial de modo, alcance y restricciones | Revisar durante Reviewer/QA; no requiere cambios adicionales en esta iteracion. |
| Referencias de contexto de esta capacidad | Creado como indice de fuentes y baseline previo | Mantener actualizado si se descubren nuevas fuentes o decisiones. |
| `docs/project_brief.md` de SDD Modes | Baseline cerrado usado como contexto historico | No modificar salvo autorizacion explicita. |
| `docs/context_refs.md` de SDD Modes | Baseline cerrado e indice de deuda VAL-001 | No modificar en esta iteracion; conservar como fuente relacionada. |
| `docs/tasks.md` de SDD Modes | Expediente historico cerrado que motiva la nueva capacidad | No modificar ni reabrir tareas. |
| `docs/sdd_readiness_assessment.md` de SDD Modes | Evidencia de cierre y condiciones | No modificar; usar como referencia de baseline cerrado. |
| `specs/spec-001-sdd-modes.md` | Fuente normativa final de SDD Modes | No modificar ni redefinir SDD Modes. |
| `specs/spec-001-sdd-modes.architecture.md` | Arquitectura final de SDD Modes | No modificar. |
| README | Puede requerir futura actualizacion para explicar el lifecycle oficial | PENDIENTE - Architecture/Documentacion posterior. |
| `.github/instructions/sdd.instructions.md` | Puede requerir futura actualizacion para incorporar Consolidation y Closed | PENDIENTE - Architecture/Documentacion posterior. |
| `AGENTS.md` y `.github/agents/` | Podrian requerir incorporar `Consolidation Agent` cuando se autorice | PENDIENTE - fase futura; no crear agente ahora. |
| Templates | Podrian requerir template de handover o ajustes a readiness/tasks | PENDIENTE - Architecture/Documentacion posterior. |
| Glosario | Podria requerir nuevos terminos: Consolidation, Closed dossier, residual debt | PENDIENTE - Documentacion posterior. |
| Gates | Podrian requerir un gate de entrada/salida de Consolidation | PENDIENTE - Architecture/QA posterior. |
| Skills | Sin impacto inmediato | No action. |

Esta specification no propaga cambios a artefactos existentes porque la iteracion solicitada permanece en Specification y prohibe modificar el baseline cerrado de `SDD Modes`.

---

## 24. Related Artifacts

| Artefacto | Relacion |
|------------|------------|
| Brief de proyecto | `docs/capabilities/project-consolidation-and-closure/project_brief.md` |
| Referencias de contexto | `docs/capabilities/project-consolidation-and-closure/context_refs.md` |
| Readiness | `docs/capabilities/project-consolidation-and-closure/sdd_readiness_assessment.md` |
| Backlog de tareas | `docs/capabilities/project-consolidation-and-closure/tasks.md` |
| Workflow | No creado en esta fase. |
| Eval | No creado en esta fase. |
| Gate | No creado en esta fase. |

---

## Definition of Done

La specification esta completa cuando:

- el objetivo esta definido;
- el alcance esta definido;
- los limites estan definidos;
- los inputs y outputs estan definidos;
- el ciclo de vida oficial esta definido;
- el Consolidation Agent esta definido conceptualmente;
- la adaptacion por modo esta definida;
- las restricciones y riesgos estan documentados;
- existen criterios de aceptacion verificables;
- no existe implementacion ni reorganizacion fisica.
