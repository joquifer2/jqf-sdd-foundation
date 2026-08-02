# Specification

## Metadata

### Spec ID

SPEC-001

### Title

SDD Modes

### Status

Final

### Owner

Jordi Quiroga

### Last Updated

2026-08-01

---

## 1. Purpose

Definir la capacidad metodologica SDD Modes para que `jqf-sdd-foundation` pueda aplicar el SDD Harness con intensidad proporcional al riesgo, complejidad, criticidad y contexto de cada repositorio derivado.

Esta specification establece que la Foundation debe reconocer tres modos oficiales de gobierno:

- SDD Minimal
- SDD Lite
- SDD Full

El termino normativo para una configuracion de gobierno proporcional es `SDD Mode`. La capacidad se nombra en plural como `SDD Modes`. Los nombres oficiales permanecen en ingles: `SDD Minimal`, `SDD Lite` y `SDD Full`. `SDD Profile` y `Governance Mode` quedan descartados para esta capacidad inicial.

La capacidad no elimina los principios SDD existentes. Define como ajustar artefactos, revisiones, gates, checks, evidencias y trazabilidad sin introducir excepciones informales ni debilitar controles criticos.

---

## 2. Background

El Project Brief de SDD Modes identifica una tension metodologica en `jqf-sdd-foundation`: el gobierno SDD completo aporta trazabilidad, coherencia y control, pero puede resultar excesivo para proyectos pequenos, experimentales o de riesgo bajo.

Actualmente la Foundation define un unico marco general de gobierno. No existe una politica formal para modular:

- documentacion requerida;
- agentes que deben intervenir;
- frecuencia de revision;
- gates aplicables;
- evidencia necesaria;
- nivel de trazabilidad;
- profundidad de artefactos;
- gestion del cambio.

Esta ausencia puede producir sobregobierno o infragobierno informal. SDD Modes debe convertir esa modulacion en una capacidad explicita, trazable y revisable.

Fuentes consultadas:

- `docs/project_brief.md`
- `docs/context_refs.md`
- `README.md`
- `.github/instructions/sdd.instructions.md`
- `AGENTS.md`
- `docs/templates/project_brief.template.md`
- `docs/templates/context_refs.template.md`
- `docs/glosario_terminos.md`
- `specs/templates/spec.template.md`

Fuentes externas y empiricas verificadas o pendientes:

- Nota de Professional OS `[SDD] - SDD Modes`: `VERIFIED - discovery-only`; URI verificada en Professional OS / Notion; sin valor normativo porque remite los artefactos oficiales al repositorio GitHub.
- Documento conceptual consensuado sobre SDD Modes: `PENDING - discovery-only`, sin valor normativo mientras no se verifiquen URI y version.
- Repositorios concretos para escenarios de validacion: candidatos retrospectivos verificados para VAL-002, VAL-003 y VAL-004; todos mantienen estado formal `Undeclared` por ser anteriores a SDD Modes y no declarar `SDD Mode`. VAL-001 permanece `PENDING` como deuda de validacion empirica futura no bloqueante para el cierre metodologico de SDD Modes, por decision humana posterior a T-027.

---

## 3. Objective

La capacidad SDD Modes debe permitir que cada repositorio basado en `jqf-sdd-foundation` declare, justifique, aplique y revise un modo de gobierno SDD proporcional a su contexto.

El resultado esperado es una definicion normativa suficiente para que futuras fases puedan:

- clasificar proyectos bajo SDD Minimal, SDD Lite o SDD Full;
- declarar el modo seleccionado en un artefacto canonico;
- justificar la suficiencia del modo;
- activar controles adicionales por riesgo aunque el modo general sea ligero;
- escalar o reducir el modo cuando cambie el contexto;
- adaptar la intervencion de agentes metodologicos sin duplicar el catalogo de agentes;
- diferenciar checks ligeros de gates formales;
- mantener SDD Full como equivalente al gobierno completo actual.

---

### Decisiones normativas cerradas

Las decisiones T-002 a T-010 de `docs/tasks.md` quedan incorporadas a esta specification como base normativa para fases posteriores.

#### Terminologia

El termino normativo es `SDD Mode`. La capacidad se denomina `SDD Modes`. Los modos oficiales son `SDD Minimal`, `SDD Lite` y `SDD Full`.

#### Semantica de modos

`SDD Minimal` aplica a exploracion, pruebas internas o cambios documentales/acotados de bajo riesgo. No puede usarse en contextos con datos sensibles, exposicion a produccion, obligaciones de cumplimiento, integraciones criticas, impacto operacional alto, riesgos relevantes de seguridad o privacidad, multiples stakeholders criticos o baja reversibilidad.

`SDD Lite` aplica a MVPs, herramientas internas o primeras versiones de riesgo controlado. Reduce artefactos, revisiones y gates por microtarea, pero conserva justificacion humana, trazabilidad suficiente, checks ligeros, hitos de revision y escalado por riesgo.

`SDD Full` equivale al baseline vigente de gobierno de `jqf-sdd-foundation`. Mantiene profundidad documental, revisiones y gates formales para proyectos criticos, productivos, sensibles, regulados, multiintegracion o de alto impacto. Cualquier cambio al baseline Full requiere decision explicita y trazable.

#### Declaracion del modo

La fuente canonica inicial para declarar y justificar el `SDD Mode` de un proyecto es el `Project Brief`. La declaracion debe incluir modo seleccionado, justificacion humana, owner, fecha, condiciones relevantes de riesgo y disparadores de reevaluacion.

`docs/context_refs.md` no es fuente normativa del modo. Su funcion es indexar y apuntar a la fuente canonica vigente para carga de contexto.

Los cambios posteriores de modo deben quedar en el artefacto de decision o gate aprobado que autorice el cambio. `docs/context_refs.md` debe actualizarse para reflejar la fuente vigente.

#### Seleccion del modo

La seleccion del `SDD Mode` debe evaluarse mediante juicio humano documentado. No debe calcularse mediante scoring automatico.

Las dimensiones minimas de seleccion son sensibilidad de datos, exposicion a produccion, obligaciones de cumplimiento, criticidad de integraciones, impacto operacional, complejidad tecnica/conceptual, numero y criticidad de stakeholders, reversibilidad del cambio, vida esperada del proyecto, auditabilidad requerida y madurez del contexto disponible.

Cualquier dimension critica o no mitigada obliga a valorar `SDD Full`. Riesgo controlado con alcance real de producto suele orientar a `SDD Lite`. Solo bajo riesgo, baja exposicion, alta reversibilidad y ausencia de controles criticos permite `SDD Minimal`.

#### Proyectos sin modo declarado

Los proyectos sin `SDD Mode` declarado quedan temporalmente en estado `Undeclared`. `Undeclared` no es un cuarto modo y no autoriza reducir gobierno.

Hasta que exista declaracion aprobada, se aplica un baseline conservador equivalente a `SDD Full` para decisiones de fase, cambios de alcance, riesgos criticos, gates y readiness. Los repositorios existentes no requieren migracion inmediata, pero cualquier cambio significativo debe incluir declaracion de modo o decision explicita de mantener temporalmente `Undeclared` con justificacion.

#### Checks, gates y evidencia

Los checks ligeros se registran de forma consolidada dentro del artefacto de trabajo vigente del incremento o en la evidencia resumida del cambio, no como archivo independiente por microtarea. Cada check debe dejar como minimo fecha o referencia temporal, alcance revisado, criterio verificado, resultado, responsable y enlace o referencia a evidencia cuando aplique.

Un check ligero valida continuidad, coherencia o readiness parcial. No autoriza cambio de fase ni sustituye aprobacion humana. Un gate formal es una decision de avance, bloqueo o readiness que debe quedar registrada como artefacto o seccion formal cuando exista transicion de fase, cambio de alcance relevante, riesgo critico o preparacion para Development.

La evidencia debe consolidarse en el artefacto de trabajo o decision que gobierna el incremento, hito o gate, con enlaces o referencias al historial Git cuando el detalle completo ya exista ahi. `docs/context_refs.md` sigue siendo indice de fuentes, no repositorio de evidencias.

#### Unidad de trabajo

La unidad normativa general es `incremento gobernado`. Un incremento gobernado agrupa alcance, decisiones, tareas, checks, evidencia y, cuando aplique, gates.

`Implementation Wave` queda reservado como etiqueta opcional para incrementos de ejecucion dentro de Development, pero no como concepto normativo principal de SDD Modes.

#### Escenarios de validacion

Los escenarios iniciales de validacion son:

- VAL-001: experimento o utilidad interna de bajo riesgo, candidato a `SDD Minimal`.
- VAL-002: MVP o primera version con exposicion limitada, candidato a `SDD Lite`.
- VAL-003: proyecto productivo, sensible, regulado o con integraciones criticas, candidato a `SDD Full`.
- VAL-004: repositorio derivado existente sin `SDD Mode` declarado, para validar `Undeclared` y compatibilidad hacia atras.

Los repositorios concretos se tratan como casos empiricos cuando existan fuentes verificables desde el repositorio o una fuente externa registrada. Los repositorios anteriores a SDD Modes que no declaran `SDD Mode` mantienen estado formal `Undeclared`; pueden usarse como candidatos retrospectivos para contrastar criterios de Lite, Full o compatibilidad, pero no se consideran declarados en esos modos. VAL-001 permanece `PENDING` hasta identificar un repositorio verificable de bajo riesgo para SDD Minimal. Por decision humana confirmada despues de T-027, esta deuda no bloquea el cierre metodologico de SDD Modes y no autoriza debilitar requisitos normativos, controles criticos ni evidencia minima de SDD Minimal.

#### Medicion de reduccion documental

La reduccion real de carga documental debe medirse de forma comparativa y cualitativa contra el baseline `SDD Full`, sin scoring automatico.

Cada validacion de `SDD Minimal` o `SDD Lite` debe registrar:

- artefactos Full que se mantienen completos por criticidad o fase;
- artefactos que se reducen, agrupan o sustituyen por evidencia consolidada;
- revisiones o gates que se mantienen por riesgo, fase o cambio de alcance;
- revisiones por microtarea que se eliminan o agrupan;
- evidencia minima conservada para reconstruir decisiones, alcance, riesgos, checks y resultado.

La reduccion documental solo es valida si elimina baja senal o duplicacion. No puede eliminar decisiones canonicas, justificacion humana del modo, riesgos criticos, gates requeridos, criterios de aceptacion, evidencia de checks ni trazabilidad minima.

#### Evidencia de no debilitamiento de SDD Full

`SDD Full` se considera no debilitado cuando una validacion demuestra que conserva el baseline vigente de gobierno para:

- artefactos SDD requeridos por fase;
- revisiones formales aplicables;
- gates de transicion, readiness o cambio de alcance relevante;
- evidencia de decisiones, riesgos, criterios de aceptacion y validacion;
- precedencia documental y aprobacion humana.

Cualquier omision, reduccion o sustitucion de controles Full debe quedar registrada como hallazgo bloqueante o decision humana explicita antes de poder considerar valida la capacidad.

---

## 4. Scope

### Included

- Definir los modos oficiales SDD Minimal, SDD Lite y SDD Full.
- Definir el proposito y el caso de uso de cada modo.
- Definir que el modo seleccionado actua como baseline de gobierno, no como excepcion informal.
- Definir criterios de seleccion inicial del modo.
- Definir reglas para escalar el modo cuando aumente el riesgo, criticidad, alcance o exposicion.
- Definir reglas para reducir el modo cuando el riesgo disminuya con evidencia suficiente.
- Definir controles adicionales activables por privacidad, seguridad, produccion, cumplimiento, integraciones o criticidad operacional.
- Definir una clasificacion de artefactos por modo: obligatorios, condicionales, recomendados, opcionales o no habituales.
- Definir una clasificacion de intervencion de agentes por modo.
- Mantener un unico catalogo de agentes metodologicos.
- Definir la diferencia metodologica entre checks ligeros y gates formales.
- Definir hitos que pueden requerir revision o gate en SDD Lite.
- Mantener gates formales para SDD Full.
- Definir como consolidar evidencia en proyectos SDD Lite sin crear historial documental excesivo.
- Mantener `context_refs.md` como indice de fuentes y trazabilidad, no como diario historico.
- Preservar compatibilidad con proyectos derivados existentes.
- Definir criterios de aceptacion y escenarios de validacion para la capacidad.
- Identificar artefactos que probablemente requeriran actualizacion en fases posteriores, sin fijar aun una arquitectura ni lista definitiva de cambios.

### Excluded

- Crear runtime.
- Crear codigo ejecutable.
- Crear agentes operativos de negocio.
- Crear herramientas reales.
- Crear workflows ejecutables.
- Automatizar completamente la seleccion del modo.
- Sustituir la validacion humana por una puntuacion automatica.
- Migrar automaticamente repositorios existentes.
- Modificar proyectos derivados dentro de esta specification inicial.
- Reestructurar repositorios derivados como `vca-ai`, `aif-foundation` u otros.
- Crear variantes duplicadas de cada agente para Minimal, Lite y Full.
- Disenar arquitectura tecnica o estructura definitiva de archivos.
- Crear tareas de desarrollo.
- Aprobar el paso a Development.
- Resolver decisiones abiertas sin respaldo suficiente.

---

## 5. Actors

| Actor | Description |
|---------|---------|
| Owner de `jqf-sdd-foundation` | Responsable humano de aprobar la definicion metodologica y decisiones pendientes. |
| Maintainer de Foundation | Persona que mantiene artefactos, plantillas, agentes e instrucciones de la Foundation. |
| Propietario de proyecto derivado | Persona que declara y justifica el modo aplicable a un repositorio derivado. |
| Specification Agent | Define o revisa specifications compatibles con el modo declarado. |
| Architect Agent | Disena estructura conceptual y documental cuando exista specification suficiente y el modo lo requiera. |
| Tasks Planner Agent | Transforma definiciones aprobadas en tareas trazables con intensidad proporcional al modo. |
| Reviewer Agent | Revisa coherencia, alcance, trazabilidad y riesgos segun la criticidad del modo y los hitos aplicables. |
| Documentation Agent | Mantiene documentacion, indices y referencias sin duplicar fuentes canonicas. |
| QA Gate Agent | Evalua gates formales cuando el modo o el riesgo lo requieran. |
| Implementation Agent | Ejecuta cambios solo cuando el modo, los artefactos y la fase vigente lo autorizan. |
| Proyecto derivado | Repositorio que adopta la Foundation y declara un modo SDD aplicable. |

---

## 6. Inputs

| Input | Description |
|----------|----------|
| Project Brief de SDD Modes | Define proposito, problema, alcance, riesgos y resultado esperado de la mejora. |
| Context References | Indice de fuentes obligatorias y referencias pendientes para la iniciativa. |
| Estado SDD vigente | Indica que el repositorio esta en Specification / Structure y no en Development. |
| Tipo de proyecto derivado | Naturaleza del repositorio o iniciativa que necesita seleccionar un modo. |
| Nivel de riesgo | Evaluacion humana de riesgo, criticidad, privacidad, cumplimiento, produccion, integraciones y alcance. |
| Evidencia disponible | Artefactos, decisiones, contexto y fuentes verificables usados para justificar el modo. |
| Decisiones metodologicas previas | Documento conceptual consensuado y notas de descubrimiento cuando sean verificadas. |
| Artefactos SDD existentes | README, instrucciones, agentes, glosario, templates, specs, gates y docs aplicables. |
| Cambios de contexto | Senales que pueden obligar a escalar, reducir o reevaluar el modo. |

---

## 7. Outputs

| Output | Description |
|-----------|-----------|
| Definicion normativa de SDD Minimal | Modo de gobierno para trabajos de bajo riesgo, alcance acotado o exploracion controlada. |
| Definicion normativa de SDD Lite | Modo de gobierno proporcional para MVPs, herramientas internas o proyectos de riesgo controlado. |
| Definicion normativa de SDD Full | Modo de gobierno completo equivalente al modelo SDD actual para proyectos criticos o complejos. |
| Criterios de seleccion de modo | Reglas que orientan la declaracion inicial del modo. |
| Reglas de escalado y reduccion | Condiciones para aumentar o disminuir la intensidad del gobierno. |
| Clasificacion de artefactos por modo | Matriz conceptual de artefactos obligatorios, condicionales, recomendados, opcionales o no habituales. |
| Reglas de intervencion de agentes | Criterios para adaptar la actuacion de agentes metodologicos sin duplicarlos. |
| Politica de checks y gates | Distincion entre controles ligeros y gates formales. |
| Reglas de evidencia y trazabilidad | Criterios para conservar trazabilidad suficiente sin convertir documentos canonicos en historiales exhaustivos. |
| Open Questions | Decisiones pendientes o de reentrada futura que no bloquean el cierre metodologico aprobado mientras conserven su estado y tratamiento explicitos. |

---

## 8. Functional Requirements

### FR-001

La Foundation debe definir exactamente tres modos oficiales iniciales: SDD Minimal, SDD Lite y SDD Full.

### FR-002

Cada modo debe tener proposito, contexto recomendado, limites y condiciones de uso diferenciadas.

### FR-003

El modo seleccionado debe declararse en una fuente canonica definida por la metodologia SDD.

### FR-004

La declaracion del modo debe incluir una justificacion humana suficiente basada en riesgo, complejidad, criticidad, alcance y contexto disponible.

### FR-005

La ausencia de modo declarado no debe interpretarse como permiso para reducir gobierno de forma implicita.

### FR-006

SDD Full debe preservar el comportamiento equivalente al gobierno completo actual de `jqf-sdd-foundation`.

### FR-007

SDD Lite debe reducir artefactos, revisiones y gates innecesarios sin eliminar trazabilidad critica ni validacion humana relevante.

### FR-008

SDD Minimal debe limitarse a trabajos de bajo riesgo, experimentales o exploratorios, y debe tener condiciones explicitas que impidan su uso en contextos criticos.

### FR-009

La metodologia debe permitir activar controles adicionales por privacidad, seguridad, produccion, cumplimiento, integraciones externas, datos sensibles o criticidad operacional, aunque el modo general sea Minimal o Lite.

### FR-010

La metodologia debe definir senales que obliguen a reevaluar o escalar el modo.

### FR-011

La metodologia debe definir condiciones bajo las cuales un proyecto puede reducir su modo con evidencia suficiente.

### FR-012

La metodologia debe clasificar los artefactos SDD por modo como obligatorios, condicionales, recomendados, opcionales o no habituales.

### FR-013

La metodologia debe definir como se adapta la intervencion de cada agente metodologico al modo declarado.

### FR-014

La metodologia debe mantener un unico catalogo de agentes metodologicos y prohibir la creacion de variantes duplicadas por modo salvo decision futura explicita.

### FR-015

La metodologia debe diferenciar checks ligeros de gates formales.

### FR-016

SDD Lite no debe requerir por defecto revisiones formales por cada microtarea.

### FR-017

SDD Lite debe definir hitos que pueden requerir revision o gate aunque no cada cambio individual lo requiera.

### FR-018

SDD Full debe mantener gates formales cuando existan transiciones de fase o cambios de alcance relevantes.

### FR-019

La metodologia debe definir como consolidar evidencia en proyectos Lite sin generar documentos historicos excesivos.

### FR-020

`context_refs.md` debe mantenerse como indice de fuentes y trazabilidad, no como repositorio completo de historial, decisiones o documentacion externa.

### FR-021

La metodologia debe preservar compatibilidad con proyectos derivados existentes y evitar migraciones automaticas obligatorias.

### FR-022

La metodologia debe identificar como se tratan proyectos existentes sin modo declarado.

### FR-023

La metodologia debe definir escenarios de validacion con proyectos de distinta complejidad antes de considerarse estable.

### FR-024

La capacidad SDD Modes no debe introducir runtime, codigo ejecutable, integraciones productivas ni logica de negocio.

### FR-025

El termino normativo para una configuracion de gobierno proporcional debe ser `SDD Mode`; la capacidad se denomina `SDD Modes`.

### FR-026

La fuente canonica inicial para declarar y justificar el `SDD Mode` de un proyecto debe ser el `Project Brief`.

### FR-027

`docs/context_refs.md` debe indexar y apuntar a la fuente canonica vigente, pero no debe ser fuente normativa del modo.

### FR-028

Los cambios posteriores de modo deben quedar registrados en el artefacto de decision o gate aprobado que autorice el cambio.

### FR-029

Los proyectos sin `SDD Mode` declarado deben quedar temporalmente en estado `Undeclared`, que no constituye un cuarto modo ni autoriza reduccion de gobierno.

### FR-030

La seleccion del modo debe evaluarse mediante juicio humano documentado sobre sensibilidad de datos, exposicion a produccion, cumplimiento, integraciones, impacto operacional, complejidad, stakeholders, reversibilidad, vida esperada, auditabilidad y madurez del contexto.

### FR-031

Los checks ligeros deben registrarse de forma consolidada con fecha o referencia temporal, alcance, criterio, resultado, responsable y referencia a evidencia cuando aplique.

### FR-032

Un check ligero no debe autorizar cambio de fase ni sustituir aprobacion humana.

### FR-033

La evidencia debe consolidarse en el artefacto de trabajo o decision que gobierna el incremento, hito o gate, con referencias al historial Git cuando corresponda.

### FR-034

La unidad normativa general debe ser `incremento gobernado`; `Implementation Wave` queda reservado como etiqueta opcional para incrementos de ejecucion dentro de Development.

### FR-035

Los escenarios iniciales de validacion deben ser VAL-001 bajo riesgo/interno, VAL-002 MVP/exposicion limitada, VAL-003 produccion/cumplimiento/integraciones criticas y VAL-004 repositorio existente sin modo declarado.
---

## 9. Business Rules

### BR-001

SDD Modes gobierna intensidad metodologica, no funcionalidad de negocio.

### BR-002

SDD Lite y SDD Minimal no significan ausencia de SDD.

### BR-003

La seleccion de modo requiere juicio humano y no puede depender exclusivamente de una puntuacion automatica.

### BR-004

Los controles criticos por seguridad, privacidad, cumplimiento, produccion o integraciones prevalecen sobre el modo general si existe conflicto.

### BR-005

Un proyecto puede operar con modo ligero solo si conserva trazabilidad suficiente para reconstruir decisiones relevantes.

### BR-006

La reduccion documental debe eliminar baja senal y duplicacion, no evidencias criticas.

### BR-007

Las reglas de SDD Modes deben tener una fuente normativa principal para evitar duplicacion y contradicciones.

### BR-008

README debe seguir siendo documentacion de alto nivel y no convertirse en la fuente completa de reglas de modo.

### BR-009

Las instrucciones de agentes deben mantenerse breves y operativas, referenciando reglas canonicas cuando existan.

### BR-010

No deben crearse templates nuevos salvo que exista una funcion claramente diferenciada y no pueda resolverse adaptando templates existentes.

### BR-011

Los proyectos derivados existentes no deben quedar rotos ni desalineados por ausencia inmediata de declaracion de modo.

### BR-012

Si existe conflicto documental, se debe aplicar la precedencia vigente: Project Brief, SDD Instructions, Specifications, Gates, Skills, Prompts y documentacion auxiliar.

### BR-013

`Undeclared` debe conservar compatibilidad hacia atras sin migracion automatica y sin downgrade silencioso.

### BR-014

La specification o frontmatter pueden declarar modo a nivel de capability solo si una decision posterior define precedencia explicita.

### BR-015

El historial Git puede aportar detalle tecnico o cronologico cuando este referenciado desde un artefacto canonico, pero no sustituye decisiones normativas, justificaciones de modo, gates, riesgos criticos ni aprobaciones humanas.
---

## 10. Constraints

- El repositorio permanece en fase Specification / Structure.
- No se permite implementar runtime, codigo de agentes, tools reales ni workflows ejecutables.
- No se permite seleccionar tecnologia definitiva.
- No se permite disenar arquitectura tecnica en esta specification.
- No se permite sustituir validacion humana por automatizacion.
- No se permite introducir logica de negocio o reglas especificas de clientes.
- No se permite crear variantes duplicadas de agentes por modo en esta fase.
- No se permite fijar la lista definitiva de archivos a modificar antes del analisis de arquitectura.
- La nota de Professional OS `[SDD] - SDD Modes` esta verificada como fuente de descubrimiento no normativa; el documento conceptual consensuado permanece `PENDING - discovery-only` mientras no se verifiquen su URI y version.
- Architecture no puede decidir ni inventar la semantica de SDD Minimal, SDD Lite o SDD Full; solo puede estructurar alternativas y consecuencias sobre reglas ya definidas o decisiones abiertas.
- Architecture debe reflejar la decision humana de que el `Project Brief` es la fuente canonica inicial de declaracion del modo, sin ampliarla ni sustituirla por inferencia tecnica.
- La specification debe permanecer alineada con `docs/project_brief.md`, `docs/context_refs.md`, `.github/instructions/sdd.instructions.md`, `AGENTS.md`, `README.md` y `docs/glosario_terminos.md`.

---

## 11. Assumptions

- SDD Full sigue siendo necesario para proyectos criticos.
- SDD Lite sera adecuado para una parte relevante de proyectos derivados de riesgo controlado.
- SDD Minimal sera excepcional y limitado a bajo riesgo o exploracion controlada.
- Los agentes metodologicos existentes pueden adaptar su intervencion sin duplicarse.
- La seleccion de modo puede orientarse mediante una matriz, pero requiere aprobacion humana.
- Algunos proyectos Lite necesitaran controles Full en areas concretas.
- Git conserva parte del historial sin obligar a que los documentos canonicos funcionen como diarios cronologicos.
- La Foundation debe seguir siendo generica y reutilizable.
- La primera version debe limitarse a tres modos salvo decision humana posterior.
- La ausencia de URI o version para fuentes externas no impide crear esta specification inicial, pero si impide tratarlas como evidencia verificada.

---

## 12. Risks

| Risk | Impact | Notes |
|--------|--------|--------|
| SDD Lite se interpreta como ausencia de control | Alto | Debe quedar explicitamente prohibido por reglas y criterios de aceptacion. |
| SDD Minimal se usa en proyectos con riesgo no bajo | Alto | Deben definirse condiciones que impidan su uso. |
| La seleccion de modo resulta subjetiva | Medio | Se requiere matriz orientativa y justificacion humana registrada. |
| La matriz se convierte en formula rigida | Medio | Debe mantener Human in the Loop. |
| Las reglas se duplican en demasiados documentos | Medio | Debe definirse una fuente normativa principal. |
| Los agentes se duplican por modo | Medio | Debe mantenerse un unico catalogo. |
| SDD Full queda debilitado | Alto | Full debe preservar el gobierno completo actual. |
| Los checks ligeros no dejan trazabilidad | Medio | Deben definirse criterios minimos de registro. |
| Se confunden checks y gates | Medio | La diferencia debe ser normativa y verificable. |
| Los proyectos existentes quedan desalineados | Alto | Debe existir tratamiento compatible para proyectos sin modo declarado. |
| Se crean demasiados templates | Medio | Debe priorizarse adaptar o extender artefactos existentes. |
| Se disena solo desde casos complejos | Medio | La validacion debe incluir casos simples y medianos. |
| Se disena solo desde MVPs | Alto | La validacion debe demostrar que Full conserva control critico. |
| Fuentes externas no verificadas contienen decisiones relevantes | Medio | Deben permanecer como PENDING hasta verificar URI/version. |

---

## 13. Acceptance Criteria

### AC-001

La specification define SDD Minimal, SDD Lite y SDD Full como los tres modos oficiales iniciales.

### AC-002

Cada modo tiene proposito, contexto recomendado, limites y condiciones de uso diferenciadas.

### AC-003

La specification establece que el modo declarado es un baseline de gobierno y no una excepcion informal.

### AC-004

La specification define requisitos para declarar y justificar el modo inicial con validacion humana.

### AC-005

La specification identifica condiciones que obligan a reevaluar o escalar el modo.

### AC-006

La specification identifica condiciones para reducir el modo con evidencia suficiente.

### AC-007

La specification exige controles adicionales por privacidad, seguridad, cumplimiento, produccion, integraciones o criticidad cuando correspondan.

### AC-008

La specification define que los artefactos se clasificaran por modo como obligatorios, condicionales, recomendados, opcionales o no habituales.

### AC-009

La specification define que los agentes metodologicos existentes adaptaran su intervencion sin duplicarse por modo.

### AC-010

La specification diferencia checks ligeros y gates formales.

### AC-011

La specification evita revisiones formales por microtarea como comportamiento por defecto en SDD Lite.

### AC-012

La specification mantiene gates formales para SDD Full y para hitos o riesgos que lo requieran.

### AC-013

La specification mantiene `context_refs.md` como indice de fuentes, no como historial exhaustivo.

### AC-014

La specification incluye decisiones abiertas para toda informacion sin respaldo suficiente.

### AC-015

La specification no introduce arquitectura, codigo ejecutable, runtime, tools reales, workflows ejecutables ni logica de negocio.

### AC-016

La specification identifica impactos documentales que deberan revisarse en fases posteriores sin modificar automaticamente esos artefactos.

### AC-017

La specification define que SDD Minimal debe incluir contextos prohibidos explicitamente documentados, incluyendo como minimo proyectos con datos sensibles, exposicion a produccion, obligaciones de cumplimiento, integraciones criticas o impacto operacional alto.

### AC-018

La specification define que SDD Lite debe incluir una cadencia o conjunto de hitos de revision y gates, evitando revision formal por microtarea pero manteniendo controles en transiciones, cambios de alcance, riesgos nuevos o preparacion para Development.

### AC-019

La specification define que SDD Full debe mantenerse equivalente al baseline de gobierno actual de `jqf-sdd-foundation`, salvo cambios aprobados de forma explicita y trazable.

### AC-020

La specification define que la fuente canonica inicial de declaracion del `SDD Mode` es el `Project Brief` y que `docs/context_refs.md` no es fuente normativa del modo.

### AC-021

La specification define `Undeclared` como estado temporal, no como cuarto modo, y evita downgrade silencioso.

### AC-022

La specification define que los checks ligeros se registran de forma consolidada y que no sustituyen gates ni aprobacion humana.

### AC-023

La specification define `incremento gobernado` como unidad normativa general y mantiene `Implementation Wave` como etiqueta opcional no normativa principal.

### AC-024

La specification define los escenarios VAL-001 a VAL-004, permite registrar candidatos retrospectivos verificables y mantiene `PENDING` cualquier escenario sin repositorio concreto verificable.

### AC-025

La specification define como medir la reduccion real de carga documental comparando `SDD Minimal` y `SDD Lite` contra el baseline `SDD Full`, sin scoring automatico y sin eliminar trazabilidad critica.

### AC-026

La specification define la evidencia minima necesaria para demostrar que `SDD Full` no se ha debilitado frente al baseline vigente de gobierno.

### AC-027

La specification declara que la validacion empirica no puede considerarse completa para un escenario sin repositorio concreto verificable. T-025 valida retrospectivamente VAL-002, VAL-003 y VAL-004 con repositorios formalmente `Undeclared`, pero VAL-001 permanece pendiente y bloquea cerrar la validacion empirica completa de SDD Minimal. Por decision humana confirmada tras T-027, esta deuda empirica no bloquea el cierre metodologico de la capacidad SDD Modes, siempre que se conserve como pendiente futuro y no se debiliten los requisitos normativos, controles criticos ni evidencia minima de SDD Minimal.

---

## 14. Dependencies

- `docs/project_brief.md`
- `docs/context_refs.md`
- `README.md`
- `.github/instructions/sdd.instructions.md`
- `AGENTS.md`
- `docs/glosario_terminos.md`
- `specs/templates/spec.template.md`
- `docs/templates/project_brief.template.md`
- `docs/templates/context_refs.template.md`
- Nota de Professional OS `[SDD] - SDD Modes`: `VERIFIED - discovery-only`; URI: `https://app.notion.com/p/3942fcf6211d80e9a9c8cab594ea0a67`; creada el 2026-07-05T18:14:52.857Z; estado Notion `Procesado`.
- Documento conceptual consensuado sobre SDD Modes: `PENDING - discovery-only`.
- Escenarios de validacion VAL-001 a VAL-004 seleccionados; candidatos retrospectivos verificados para VAL-002, VAL-003 y VAL-004 en `docs/context_refs.md`; VAL-001 permanece `PENDING` como deuda de validacion empirica futura no bloqueante para el cierre metodologico.
- Revisiones Reviewer y QA Gate completadas con condiciones cerradas o aceptadas.
- Architecture finalizada en `specs/spec-001-sdd-modes.architecture.md`.

---

## 15. Open Questions

- ¿Debe el modo declararse tambien en README, frontmatter u otro artefacto visible como copia informativa o metadata subordinada?
- ¿Que senales especificas obligaran a valorar `SDD Full` ademas de las dimensiones criticas ya definidas?
- ¿Debe `SDD Lite` ser una recomendacion por defecto o un baseline provisional para ciertos proyectos derivados?
- ¿Quien puede aprobar el modo inicial?
- ¿Quien puede aprobar un cambio de modo?
- ¿Cada cuanto debe reevaluarse el modo si no hay eventos de riesgo?
- ¿Minimal necesita un Project Brief reducido o basta con adaptar el template existente?
- ¿Lite necesita un template independiente o conviene adaptar los templates actuales?
- ¿Como recibe cada agente el modo declarado durante su actuacion?
- ¿Las reglas de adaptacion deben vivir en cada agente o en una instruccion comun?
- ¿Cual es la ubicacion y version canonica del documento conceptual consensuado sobre SDD Modes?

---

## 16. Future Considerations

- Definir una estrategia de adopcion para proyectos derivados existentes.
- Registrar un repositorio concreto verificable para VAL-001 antes de cerrar la validacion empirica completa de SDD Minimal; esta deuda no bloquea el cierre metodologico de SDD Modes.
- Resolver la ubicacion y version canonica del documento conceptual consensuado que permanece `PENDING - discovery-only`.
- Evaluar si conviene exponer el `SDD Mode` como metadata informativa subordinada en artefactos visibles, sin sustituir la declaracion canonica inicial del `Project Brief`.

---

## 17. Related Artifacts

| Artifact | Relationship |
|------------|------------|
| `docs/project_brief.md` | Fuente canonica inicial del proposito, alcance y resultado esperado de SDD Modes. |
| `docs/context_refs.md` | Indice oficial de fuentes consultadas, fuentes pendientes y jerarquia de contexto. |
| `README.md` | Documento de alto nivel que describe la Foundation, su estado y sus limites. |
| `.github/instructions/sdd.instructions.md` | Instrucciones vigentes de fase, restricciones, precedencia y SDD Harness. |
| `AGENTS.md` | Catalogo y limites de agentes metodologicos. |
| `docs/glosario_terminos.md` | Vocabulario comun SDD y definiciones de artefactos. |
| `specs/templates/spec.template.md` | Plantilla utilizada para crear esta specification. |
| Nota de Professional OS `[SDD] - SDD Modes` | Fuente de descubrimiento verificada, no normativa, que remite los artefactos oficiales al repositorio GitHub. |
| Documento conceptual consensuado sobre SDD Modes | Decision metodologica previa pendiente de verificacion. |
| Workflow | No creado en esta fase. |
| Eval | No creado en esta fase. |
| Gate | No creado en esta fase. |

### Cross-Artifact Impact Analysis

| Artifact | Status | Notes |
|------------|------------|------------|
| Project Brief | Consistente | La specification deriva del alcance y restricciones ya definidos. |
| README | Current | Explicacion de alto nivel vigente; no es fuente normativa completa. |
| Context References | Consistente | Professional OS esta verificado como discovery-only; el documento conceptual permanece PENDING y VAL-001 queda como deuda empirica futura no bloqueante. |
| Specifications relacionadas | No aplica | No existen otras specifications activas en `specs/`. |
| Contracts | No aplica | No se requiere contract transversal para el cierre metodologico de esta capacidad. |
| Gates | Cerrado con condiciones | Los criterios de checks/gates quedan definidos normativamente; no se crean gates adicionales en esta fase. |
| Templates | Current | Las plantillas vigentes forman parte del baseline final y no requieren cambios adicionales para este cierre. |
| Agentes metodologicos | Current | Los agentes y adaptadores vigentes consumen el modo declarado sin duplicarse por modo. |
| Skills | Fuera de alcance | No se requieren skills nuevas para cerrar SDD Modes como capacidad metodologica. |
| Glosario | Current | Terminologia aprobada incorporada al baseline final. |

---

## Definition of Done

La specification está completa cuando:

- el objetivo está definido;
- el alcance está definido;
- los límites están definidos;
- los inputs están definidos;
- los outputs están definidos;
- los requisitos funcionales están definidos;
- las reglas principales están documentadas;
- los riesgos relevantes están identificados;
- existen criterios de aceptación verificables.