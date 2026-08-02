# Specification

## Metadatos

### Spec ID

SPEC-001

### Title

Repository Physical Normalization

### Estado

Specification gate passed / Architecture authorized

### Responsable

Jordi Quiroga

### Ultima actualizacion

2026-08-02

---

### SDD Mode Reference

Modo declarado para el proyecto o capacidad:

`SDD Full`

Justificacion o referencia canonica:

`docs/capabilities/repository-physical-normalization/project_brief.md`

Notas:

- Esta specification no autoriza por si sola Architecture; Architecture documental fue autorizada posteriormente por decision humana T-008.
- Esta specification no autoriza Development.
- Esta specification no mueve, copia, renombra, elimina ni sustituye archivos.
- Esta specification no modifica baselines cerrados.

---

## 1. Proposito

Definir el proceso oficial de normalizacion fisica del repositorio `jqf-sdd-foundation`, de forma que la estructura fisica pueda alinearse con el modelo metodologico aprobado sin romper trazabilidad, compatibilidad, referencias ni baselines cerrados.

---

## 2. Background

La Foundation evoluciono desde artefactos raiz hacia expedientes por capacidad. Como resultado, `SDD Modes` conserva sus documentos principales en rutas raiz (`docs/` y `specs/`), mientras que capacidades posteriores viven bajo `docs/capabilities/<capability-id>/` y `specs/capabilities/<capability-id>/`.

Las capacidades cerradas `SDD Project Consolidation and Closure`, `Foundation Derivation and Project Initialization` y `Consolidation Agent` establecieron un modelo logico basado en:

- baseline canonico;
- expediente metodologico cerrado;
- evidencia historica;
- deuda residual;
- puntos de reentrada;
- handover de cierre;
- indices ligeros de routing.

El `Consolidation Agent` produjo una validacion retrospectiva sobre `SDD Modes` y una propuesta fisica no ejecutada. Esta specification toma esa propuesta como input, pero no la ejecuta.

---

## 3. Objective

La capacidad debe especificar como transformar, en una fase futura autorizada, la estructura fisica del repositorio para que refleje fielmente el modelo metodologico aprobado.

El resultado debe permitir que una Architecture posterior defina:

- estructura fisica objetivo;
- mapa de movimientos;
- estrategia de compatibilidad;
- plan de actualizacion de referencias;
- plan de reversibilidad;
- gates y evidencias requeridas;
- primer caso de aplicacion sobre `SDD Modes`;
- reutilizacion para capacidades futuras cerradas.

---

## 4. Alcance

### Included

- Objetivos y principios de normalizacion fisica.
- Estructura fisica objetivo del repositorio.
- Categorias documentales: baseline canonico, capacidades, expedientes historicos, evidencias, plantillas, agentes y documentacion transversal.
- Reglas de movimiento, copia, conservacion, archivo y sustitucion.
- Reglas de precedencia documental.
- Reglas de compatibilidad y actualizacion de referencias.
- Reglas de reversibilidad.
- Criterios de aceptacion y Definition of Done.
- Riesgos, dependencias y decisiones abiertas.
- Aplicacion futura inicial sobre `SDD Modes`.
- Aplicacion reutilizable para nuevas capacidades cerradas.
- Frontera con `Consolidation Agent`.
- Analisis de impacto entre artefactos.

### Excluded

- Ejecutar normalizacion fisica.
- Mover, copiar, renombrar, eliminar o sustituir archivos.
- Modificar rutas existentes.
- Crear Architecture sin autorizacion humana explicita.
- Crear scripts, tools, workflows, automatizaciones o runtime.
- Modificar el baseline cerrado de `SDD Modes`.
- Modificar capacidades cerradas.
- Introducir cambios funcionales.
- Autorizar Development.

---

## 5. Actores

| Actor | Descripcion |
| --- | --- |
| Responsable de Foundation | Aprueba decisiones de fase, alcance, movimientos y cierre. |
| Specification Agent | Define esta capacidad, limites, reglas y criterios verificables. |
| Architect Agent | Podra definir estructura fisica detallada, mapa de movimientos y compatibilidad si Architecture se autoriza. |
| Documentation Agent | Podra actualizar indices, referencias, handovers y documentos auxiliares si una fase futura lo autoriza. |
| Reviewer Agent | Revisara coherencia, riesgos, referencias y ausencia de contradicciones. |
| QA Gate Agent | Validara readiness, gates, evidencia y ausencia de cambios no autorizados. |
| Consolidation Agent | Podra producir propuestas de clasificacion y normalizacion `proposal-only`; no ejecuta movimientos. |
| Implementation Agent | Solo podria intervenir si Development futuro se autoriza explicitamente. |
| Futuros repositorios derivados | Consumidores indirectos de la estructura normalizada y reglas de compatibilidad. |

---

## 6. Inputs

| Input | Descripcion |
| --- | --- |
| Baseline cerrado de `SDD Modes` | Artefactos raiz que actuan como primer caso futuro de normalizacion. |
| Paquete retrospectivo `sdd-modes-retrospective` | Propuesta no ejecutable de clasificacion y target structure. |
| Baseline de `SDD Project Consolidation and Closure` | Define categorias de consolidacion, cierre, baseline, expediente y deuda. |
| Baseline de `Foundation Derivation and Project Initialization` | Define limites con baseline reutilizable y proyectos derivados. |
| Baseline de `Consolidation Agent` | Define frontera entre propuesta metodologica y ejecucion fisica. |
| Indices globales actuales | Ayudan a identificar navegacion documental vigente. |
| Reference map futuro | Inventario de referencias antes de mover; no se genera en esta Specification. |
| Aprobacion humana | T-008 autorizo Architecture documental; Development o cualquier movimiento fisico requieren nueva aprobacion futura. |

---

## 7. Outputs

| Output | Descripcion |
| --- | --- |
| Specification de normalizacion fisica | Este documento. Define proceso, reglas y limites. |
| Estructura objetivo conceptual | Definicion de ubicaciones y categorias documentales futuras. |
| Reglas de movimiento | Criterios para decidir mover, copiar, mantener, archivar o sustituir. |
| Reglas de compatibilidad | Criterios para no romper enlaces, referencias, agentes ni repositorios derivados. |
| Reglas de actualizacion de referencias | Criterios para indices, handovers, context refs y cross-references. |
| Reglas de reversibilidad | Criterios para rollback documental y trazabilidad. |
| Caso de aplicacion `SDD Modes` | Guia futura para normalizar una capacidad ya cerrada. |
| Backlog inicial | Tareas de Specification y pasos futuros no autorizados. |

---

## 8. Principios

### P-001 - Movimiento fisico no cambia semantica

Mover o renombrar un artefacto no modifica su estado, autoridad normativa, decision de cierre ni contenido aprobado.

### P-002 - Una fuente canonica por artefacto

Tras una normalizacion futura, cada artefacto debe tener una ruta canonica vigente. Las rutas legacy solo pueden actuar como compatibilidad temporal o referencia historica claramente marcada.

### P-003 - Git conserva historia, el repositorio conserva navegacion

No se elimina historia Git. Aun asi, la estructura vigente debe ser navegable sin depender de investigar commits.

### P-004 - Compatibilidad antes que limpieza

La primera normalizacion debe priorizar enlaces, trazabilidad y rutas de carga de agentes sobre una limpieza estetica completa.

### P-005 - Deuda visible

La normalizacion no puede ocultar deuda residual, condiciones de cierre, discovery-only sources ni puntos de reentrada.

### P-006 - Proposal-only no es ejecucion

Las propuestas del `Consolidation Agent` son inputs para esta capacidad. Solo una fase futura autorizada puede ejecutarlas.

---

## 9. Organizacion fisica objetivo

La estructura objetivo conceptual del repositorio debe distinguir:

```text
AGENTS.md
README.md

.codex/
  agents/                         # Adaptadores Codex subordinados a .github/agents

.github/
  agents/                         # Definiciones canonicas de agentes metodologicos
  instructions/                   # Instrucciones SDD y gobierno transversal
  prompts/                        # Prompts reutilizables, si existen
  skills/                         # Skills metodologicas, si existen

docs/
  baseline/                       # Baseline canonico global, si Architecture futura lo aprueba
  capabilities/
    index.md                      # Catalogo ligero no normativo
    <capability-id>/
      project_brief.md
      context_refs.md
      tasks.md
      sdd_readiness_assessment.md
      closure_handover.md         # cuando aplique
      evidence_index.md           # cuando aplique
      residual_debt.md            # cuando aplique
      validations/                # evidencias de validacion, si aplica
  templates/                      # Plantillas reutilizables
  glosario_terminos.md            # Documentacion transversal

specs/
  baseline/                       # Specs canonicas globales, si Architecture futura lo aprueba
  capabilities/
    index.md                      # Catalogo ligero no normativo
    <capability-id>/
      spec-001-<capability-id>.md
      arch-001-<capability-id>.md # cuando exista
  templates/

gates/                            # Gates documentales transversales
tests/                            # Evals o tests documentales/futuros, no productivos por defecto
tools/                            # Reservado; no crear tools sin Development autorizado
workflows/                        # Reservado; no crear workflows ejecutables sin autorizacion
memory/                           # Reservado segun gobierno vigente
```

Notas:

- `docs/baseline/` y `specs/baseline/` quedan como posibilidad conceptual. Architecture futura debe decidir si son necesarios o si el baseline global permanece distribuido en instrucciones, agentes, templates, gates y specs de capacidades cerradas.
- Los indices `docs/capabilities/index.md` y `specs/capabilities/index.md` siguen siendo catalogos, no fuentes normativas.
- La documentacion transversal no debe moverse dentro de una capacidad concreta salvo que sea realmente capability-local.

---

## 10. Categorias fisicas

### 10.1 Baseline canonico global

Artefactos vigentes que gobiernan toda la Foundation: instrucciones SDD, agentes metodologicos canonicos, glosario, gates documentales, templates y cualquier spec cerrada declarada como baseline global.

### 10.2 Baseline canonico de capacidad

Specification, Architecture y documentos aprobados que representan el resultado vigente de una capacidad cerrada.

### 10.3 Expediente historico de capacidad

Project Brief, Context References, Tasks, Readiness, handovers, evidencia, deuda y validaciones que explican como se llego al cierre.

### 10.4 Evidencias

Gates, reports, validation packages, review decisions, evidence indexes y referencias Git. Deben conservarse y ser localizables, pero no necesariamente cargarse por defecto.

### 10.5 Plantillas

Artefactos reutilizables para nuevos proyectos o capacidades. Son transversales salvo que una template sea experimental o capability-local.

### 10.6 Agentes

Definiciones canonicas en `.github/agents/`; adaptadores en `.codex/agents/`. Los adaptadores no son segunda fuente de verdad.

### 10.7 Documentacion transversal

README, AGENTS, glosario, instrucciones, gates e indices globales. Debe mantenerse separada de expedientes de capacidad.

---

## 11. Reglas de movimiento

### RM-001 - Cuando mover

Mover solo cuando:

- existe ruta objetivo aprobada;
- existe inventario de referencias;
- el movimiento reduce ambiguedad entre baseline, expediente y documentacion transversal;
- existe estrategia de compatibilidad;
- Reviewer y QA han validado el plan;
- hay aprobacion humana explicita para ejecutar.

### RM-002 - Cuando copiar

Copiar solo cuando:

- se necesita crear un artefacto nuevo derivado, como handover, evidence index o residual debt, sin alterar el original;
- se necesita mantener una compatibilidad temporal sin declarar dos fuentes canonicas;
- el contenido copiado se marca claramente como derivado, resumen, stub o referencia.

La copia no debe crear baseline paralelo.

### RM-003 - Cuando mantener

Mantener en su ruta actual cuando:

- el artefacto es transversal;
- moverlo causaria mas riesgo que beneficio;
- no existe mapa completo de referencias;
- la ruta legacy sigue siendo la fuente canonica aprobada;
- la capacidad esta cerrada y no hay autorizacion de reentrada.

### RM-004 - Cuando archivar

Archivar solo cuando:

- el artefacto ya no es fuente vigente;
- existe fuente vigente que lo sustituye;
- el archivo conserva valor historico;
- el estado `Archived` o `Superseded` queda indicado en indice, handover o stub.

Archivar no significa eliminar.

### RM-005 - Cuando sustituir

Sustituir solo cuando:

- existe nueva fuente canonica aprobada;
- la ruta anterior queda como stub, referencia o artefacto historico;
- las referencias han sido actualizadas o explicitamente compatibilizadas;
- la sustitucion esta registrada con fecha, responsable y motivo.

### RM-006 - Nunca eliminar historia Git

La normalizacion no debe usar borrado destructivo para ocultar evolucion historica. Si una ruta legacy deja de ser necesaria, su retirada requiere decision explicita y evidencia de compatibilidad.

---

## 12. Reglas de precedencia

### RP-001 - Precedencia documental vigente

En caso de conflicto, aplica la precedencia general:

```text
Project Brief
↓
SDD Instructions
↓
Specifications
↓
Gates
↓
Skills
↓
Prompts
↓
Documentacion auxiliar
```

### RP-002 - Ruta fisica no altera precedencia

Un artefacto no gana ni pierde autoridad por moverse de ruta. Su autoridad depende de su tipo, estado, aprobacion y referencias canonicas.

### RP-003 - Indices no sustituyen baseline

Los indices ayudan a descubrir artefactos, pero no redefinen el contenido normativo de specs, gates, instrucciones o Project Brief.

### RP-004 - Stubs no son segunda fuente de verdad

Un stub de compatibilidad debe apuntar a la ruta vigente y declarar que no contiene definicion normativa.

---

## 13. Compatibilidad

### CP-001 - Reference map obligatorio

Antes de cualquier movimiento futuro debe existir un mapa de referencias que cubra, como minimo:

- enlaces Markdown;
- rutas inline en documentos;
- tablas de indices;
- handovers;
- context_refs;
- AGENTS y definiciones de agentes;
- instrucciones SDD;
- README;
- templates;
- gates;
- referencias en `.codex/agents/`.

### CP-002 - Compatibilidad con agentes

Los agentes metodologicos deben poder localizar la fuente vigente mediante:

- handover, si existe;
- context_refs de la capacidad;
- indices globales;
- stubs legacy durante transicion;
- reglas de carga documentadas.

### CP-003 - Compatibilidad con repositorios derivados

La normalizacion de la Foundation no debe invalidar proyectos derivados existentes. Cuando una ruta sea parte de una expectativa exportable, debe documentarse:

- ruta anterior;
- ruta nueva;
- periodo o estrategia de compatibilidad;
- instruccion de migracion para derivados, si aplica.

### CP-004 - Enlaces no rotos

Una normalizacion futura solo puede cerrarse si los enlaces y referencias conocidas quedan:

- actualizados;
- compatibilizados mediante stub;
- registrados como deuda residual aceptada con impacto y reentrada.

---

## 14. Actualizacion de referencias

### AR-001 - Indices

Los indices globales deben actualizarse solo cuando el cambio fisico este aprobado. Deben marcar:

- ruta canonica vigente;
- estado;
- relacion con baseline;
- ubicacion de expediente historico;
- restricciones de carga.

### AR-002 - Enlaces y rutas inline

Las rutas textuales deben actualizarse cuando sean referencias operativas o de navegacion. Las menciones historicas pueden conservar la ruta antigua si se etiquetan como historicas.

### AR-003 - Referencias cruzadas

Specs, architectures, handovers, readiness y tasks deben actualizar referencias cruzadas que apunten a rutas movidas, salvo cuando describan historial.

### AR-004 - Handovers

Los handovers deben convertirse en punto de entrada principal para capacidades cerradas. Si una capacidad legacy no tiene handover, la normalizacion futura debe decidir si crea uno como resumen derivado.

### AR-005 - Context refs

Cada `context_refs.md` debe indexar la fuente canonica vigente y, si aplica, rutas legacy, discovery-only sources y deuda pendiente.

### AR-006 - Registro de cambios

Todo lote de normalizacion futura debe registrar:

- fecha;
- responsable;
- decision autorizante;
- mapa antes/despues;
- referencias actualizadas;
- referencias compatibilizadas;
- deuda residual.

---

## 15. Reversibilidad

### RV-001 - Plan de rollback obligatorio

Antes de ejecutar movimientos futuros debe existir un rollback plan que indique:

- como volver a rutas anteriores si se detectan referencias rotas;
- que stubs o indices revertir;
- que commit o lote Git agrupa el cambio;
- que evidencias demuestran reversibilidad.

### RV-002 - Movimientos en lotes pequenos

La normalizacion debe aplicarse por capacidad o por familia documental, no como cambio masivo indiferenciado.

### RV-003 - No borrar en primer paso

La primera aplicacion futura debe preferir mover con compatibilidad o crear stubs, no eliminar rutas legacy.

### RV-004 - Validacion post-movimiento

Todo movimiento futuro requiere validacion posterior de referencias, indices, carga de agentes y ausencia de cambio normativo no autorizado.

---

## 16. Aplicacion sobre SDD Modes

`SDD Modes` sera el primer caso real futuro porque:

- es baseline cerrado;
- predice la tension entre documentos raiz y expedientes por capacidad;
- fue usado en la validacion retrospectiva del `Consolidation Agent`;
- tiene propuesta de normalizacion fisica no ejecutada.

### 16.1 Clasificacion inicial propuesta

| Artefacto actual | Clasificacion futura | Ruta objetivo conceptual |
| --- | --- | --- |
| `docs/project_brief.md` | Expediente de capacidad / fuente inicial de alcance | `docs/capabilities/sdd-modes/project_brief.md` |
| `docs/context_refs.md` | Expediente de capacidad / indice de contexto | `docs/capabilities/sdd-modes/context_refs.md` |
| `docs/tasks.md` | Expediente historico / decision log | `docs/capabilities/sdd-modes/tasks.md` |
| `docs/sdd_readiness_assessment.md` | Evidencia de gate/readiness | `docs/capabilities/sdd-modes/sdd_readiness_assessment.md` |
| `specs/spec-001-sdd-modes.md` | Baseline canonico de capacidad | `specs/capabilities/sdd-modes/spec-001-sdd-modes.md` |
| `specs/spec-001-sdd-modes.architecture.md` | Baseline canonico de capacidad | `specs/capabilities/sdd-modes/arch-001-sdd-modes.md` o ruta legacy mantenida, segun Architecture |

### 16.2 Artefactos derivados posibles

Una fase futura podria crear, sin reescribir decisiones cerradas:

- `docs/capabilities/sdd-modes/closure_handover.md`;
- `docs/capabilities/sdd-modes/evidence_index.md`;
- `docs/capabilities/sdd-modes/residual_debt.md`.

Estos artefactos serian resumen, indice o registro derivado, no nuevo cierre normativo salvo decision humana explicita.

### 16.3 Condiciones especiales para SDD Modes

- No modificar contenido normativo de SPEC o ARCH.
- No cerrar deudas existentes sin QA Gate.
- No promover fuentes discovery-only pendientes.
- No declarar una nueva validacion de `SDD Modes` por el hecho de mover archivos.
- Mantener compatibilidad con las rutas raiz hasta que Architecture y QA acepten la retirada o sustitucion.

---

## 17. Aplicacion futura para capacidades cerradas

Para cualquier nueva capacidad cerrada, el proceso debe ser reutilizable como checklist:

1. Confirmar estado de cierre, modo SDD y gate final.
2. Identificar baseline canonico, expediente, evidencia, deuda y reentradas.
3. Verificar handover y context_refs.
4. Clasificar artefactos transversales vs capability-local.
5. Generar mapa de referencias.
6. Proponer movimientos, copias, stubs o conservacion.
7. Revisar compatibilidad con derivados.
8. Obtener review y QA.
9. Ejecutar solo si existe autorizacion futura.
10. Validar y registrar resultado.

Las capacidades nuevas que ya sigan `docs/capabilities/<id>` y `specs/capabilities/<id>` deberian requerir menos movimiento y mas revision de indices y handover.

---

## 18. Frontera con Consolidation Agent

### Consolidation Agent puede

- cargar una capacidad cerrada;
- clasificar artefactos;
- identificar baseline, expediente, evidencia, deuda y reentrada;
- producir una propuesta de normalizacion fisica;
- registrar riesgos y condiciones;
- preparar handover o reporte `proposal-only`.

### Consolidation Agent no puede

- ejecutar movimientos fisicos;
- cambiar rutas canonicas por si mismo;
- modificar baselines cerrados;
- aprobar gates;
- cerrar deuda residual;
- autorizar Development;
- sustituir decision humana.

### Repository Physical Normalization es responsable de

- definir reglas oficiales de normalizacion fisica;
- convertir propuestas en plan gobernado cuando Architecture futura lo autorice;
- exigir mapa de referencias, compatibilidad y reversibilidad;
- establecer criterios de aceptacion para la ejecucion futura;
- gobernar la aplicacion sobre `SDD Modes` y capacidades posteriores.

---

## 19. Requisitos funcionales

### FR-001

La Foundation debe definir un proceso oficial de normalizacion fisica del repositorio.

### FR-002

El proceso debe definir una estructura objetivo que distinga baseline canonico, capacidades, expedientes historicos, evidencias, plantillas, agentes y documentacion transversal.

### FR-003

El proceso debe definir cuando mover, copiar, mantener, archivar o sustituir artefactos.

### FR-004

El proceso debe impedir eliminacion de historia Git y borrado destructivo no autorizado.

### FR-005

El proceso debe exigir inventario de referencias antes de cualquier movimiento futuro.

### FR-006

El proceso debe definir compatibilidad para enlaces, indices, handovers, context_refs, agentes y repositorios derivados.

### FR-007

El proceso debe definir reglas de actualizacion de referencias cruzadas.

### FR-008

El proceso debe definir reversibilidad y rollback documental.

### FR-009

El proceso debe usar `SDD Modes` como primer caso futuro de aplicacion sin modificarlo durante Specification.

### FR-010

El proceso debe ser reutilizable para cualquier nueva capacidad cerrada.

### FR-011

El proceso debe definir la frontera entre propuestas del `Consolidation Agent` y ejecucion de normalizacion fisica.

### FR-012

La specification debe mantener Development y normalizacion fisica como no autorizados; Architecture documental requiere decision humana explicita externa a la spec.

---

## 20. Business Rules

### BR-001

Ningun movimiento fisico puede ejecutarse sin decision humana explicita y gate aplicable.

### BR-002

Un movimiento fisico no cambia el estado cerrado, condiciones, deuda ni autoridad normativa de un artefacto.

### BR-003

Una ruta legacy puede conservarse temporalmente solo como compatibilidad, no como segunda fuente canonica.

### BR-004

Todo cambio futuro debe mantener o mejorar trazabilidad.

### BR-005

La primera normalizacion real debe aplicarse en lote acotado, preferiblemente sobre `SDD Modes`.

### BR-006

Si no existe mapa completo de referencias, no se puede ejecutar movimiento.

### BR-007

Si una referencia rota no puede corregirse, debe registrarse como deuda residual con impacto, owner y reentrada.

### BR-008

Las rutas de documentacion transversal no deben absorberse en expedientes de capacidad.

---

## 21. Restricciones

- Estado actual: `Specification gate passed / Architecture authorized`.
- No crear Architecture fuera de la autorizacion documental T-008.
- No autorizar Development.
- No ejecutar normalizacion fisica.
- No mover, copiar, renombrar, eliminar ni sustituir archivos.
- No crear scripts, tools, workflows o automatizaciones.
- No modificar baselines cerrados.
- No modificar capacidades cerradas.
- No alterar rutas vigentes.
- No cerrar deuda residual.

---

## 22. Supuestos

- Architecture futura decidira si existen carpetas `baseline/`.
- Los indices globales seguiran siendo catalogos no normativos.
- La compatibilidad legacy sera necesaria al menos durante la primera aplicacion.
- Las capacidades nuevas ya siguen parcialmente la estructura objetivo.
- `SDD Modes` requiere tratamiento especial por haber nacido antes de los expedientes por capacidad.

---

## 23. Riesgos

| Riesgo | Impacto | Notas |
| --- | --- | --- |
| Movimiento prematuro | Alto | Mitigado por prohibicion explicita en esta spec. |
| Ruptura de referencias | Alto | Requiere reference map, stubs o actualizacion validada. |
| Doble fuente de verdad | Alto | Una ruta canonica, rutas legacy solo compatibilidad. |
| Cambio normativo accidental | Alto | Movimiento fisico no reabre baseline. |
| Exceso de alcance hacia automatizacion | Alto | Scripts y workflows fuera de alcance. |
| Complejidad por `baseline/` global | Medio | Architecture futura debe decidir si aporta claridad real. |
| Repositorios derivados quedan desalineados | Medio | Requiere notas de compatibilidad si rutas exportables cambian. |

---

## 24. Acceptance Criteria

### AC-001

La specification define objetivo, problema, alcance, exclusiones, actores, inputs y outputs.

### AC-002

La specification define la estructura fisica objetivo conceptual y distingue las categorias requeridas.

### AC-003

La specification define reglas verificables para mover, copiar, mantener, archivar y sustituir.

### AC-004

La specification define reglas de precedencia, compatibilidad y actualizacion de referencias.

### AC-005

La specification define reversibilidad y condiciones minimas de rollback.

### AC-006

La specification define como aplicar el proceso sobre `SDD Modes` como primer caso futuro.

### AC-007

La specification define como reutilizar el proceso para capacidades futuras cerradas.

### AC-008

La specification define claramente la frontera con `Consolidation Agent`.

### AC-009

La specification no autoriza por si sola Architecture, mantiene Development no autorizado y exige decision humana explicita para cualquier avance de fase.

### AC-010

La specification no modifica, mueve, copia, renombra, elimina ni sustituye artefactos existentes.

---

## 25. Dependencies

- `docs/capabilities/repository-physical-normalization/project_brief.md`
- `docs/capabilities/repository-physical-normalization/context_refs.md`
- `docs/capabilities/consolidation-agent/validations/sdd-modes-retrospective/consolidation_report.md`
- `docs/capabilities/consolidation-agent/validations/sdd-modes-retrospective/qa_gate_decision.md`
- `docs/capabilities/consolidation-agent/closure_handover.md`
- `docs/capabilities/consolidation-agent/residual_debt.md`
- `specs/capabilities/consolidation-agent/spec-001-consolidation-agent.md`
- `specs/capabilities/consolidation-agent/arch-001-consolidation-agent.md`
- `docs/capabilities/project-consolidation-and-closure/closure_handover.md`
- `specs/capabilities/project-consolidation-and-closure/spec-001-sdd-project-consolidation-and-closure.md`
- `specs/capabilities/project-consolidation-and-closure/arch-001-sdd-project-consolidation-and-closure.md`
- `docs/project_brief.md`
- `docs/context_refs.md`
- `docs/tasks.md`
- `docs/sdd_readiness_assessment.md`
- `specs/spec-001-sdd-modes.md`
- `specs/spec-001-sdd-modes.architecture.md`
- `.github/instructions/sdd.instructions.md`
- `AGENTS.md`
- `README.md`

---

## 26. Open Questions

- Debe existir `docs/baseline/` y `specs/baseline/`, o basta con indices y artefactos canonicos distribuidos?
- Que estrategia de compatibilidad legacy se seleccionara para rutas raiz de `SDD Modes`?
- Debe renombrarse `spec-001-sdd-modes.architecture.md` o conservarse por compatibilidad?
- Que formato tendra el future movement plan?
- Que formato tendra el future reference map?
- Que gate exacto aprobara ejecucion fisica?
- Que agente ejecutara los cambios fisicos si una fase futura lo autoriza?
- Durante cuanto tiempo deben conservarse stubs legacy?

---

## 27. Future Considerations

- Revisar la Architecture documental creada bajo autorizacion humana T-008.
- Crear templates para movement plan, reference map y rollback plan si Architecture los requiere.
- Evaluar automatizaciones no destructivas de link checking solo en capacidad futura separada.
- Incorporar reglas de normalizacion en README, instrucciones SDD o glosario solo tras review/QA.
- Aplicar primer piloto sobre `SDD Modes` con lote pequeno y compatibilidad legacy.
- Definir recomendaciones para repositorios derivados si la estructura exportable cambia.

---

## 28. Analisis de impacto entre artefactos

| Artefacto | Impacto | Accion requerida |
| --- | --- | --- |
| Brief de esta capacidad | Creado como fuente canonica inicial de modo, alcance y restricciones. | Revisar por Reviewer/QA. |
| Context refs de esta capacidad | Creado como indice de fuentes y jerarquia. | Mantener actualizado si se descubren fuentes o decisiones. |
| `docs/capabilities/index.md` | Indexa esta capacidad y su Architecture como catalogo no normativo. | Actualizado; no sustituye el expediente de capacidad. |
| `specs/capabilities/index.md` | Indexa esta specification y `ARCH-001` como catalogo no normativo. | Actualizado; no sustituye `SPEC-001` ni `ARCH-001`. |
| Baseline raiz de `SDD Modes` | Primer caso futuro de aplicacion. | No modificar, no mover y no reabrir durante Specification. |
| Paquete retrospectivo SDD Modes | Input principal `proposal-only`. | Usar como evidencia, no como cambio aplicado. |
| `Consolidation Agent` | Frontera definida: propone, no ejecuta. | No modificar capacidad cerrada. |
| `SDD Project Consolidation and Closure` | Baseline metodologico de categorias. | No modificar. |
| README | Puede requerir futura actualizacion para explicar estructura normalizada. | PENDIENTE para Documentation futura. |
| `.github/instructions/sdd.instructions.md` | Puede requerir futura regla de normalizacion fisica. | PENDIENTE para Architecture/Documentation futura. |
| AGENTS y definiciones canonicas | Deben conservar limites de agentes. | No action en esta fase. |
| Templates | Podrian requerir movement plan/reference map/rollback plan. | PENDIENTE. |
| Gates | Podrian requerir gate especifico o extension de Closure/Readiness. | PENDIENTE. |
| Glosario | Podria requerir termino `Repository Physical Normalization`. | PENDIENTE. |

Esta specification solo propaga actualizaciones documentales e indices no normativos de la propia capacidad. Prohibe modificar rutas, ejecutar normalizacion o alterar baselines aprobados.

---

## 29. Related Artifacts

| Artefacto | Relacion |
| --- | --- |
| Brief de proyecto | `docs/capabilities/repository-physical-normalization/project_brief.md` |
| Referencias de contexto | `docs/capabilities/repository-physical-normalization/context_refs.md` |
| Readiness / QA | `docs/capabilities/repository-physical-normalization/sdd_readiness_assessment.md` |
| Architecture | `specs/capabilities/repository-physical-normalization/arch-001-repository-physical-normalization.md` |
| Backlog inicial | docs/capabilities/repository-physical-normalization/tasks.md |
| Propuesta retrospectiva SDD Modes | `docs/capabilities/consolidation-agent/validations/sdd-modes-retrospective/consolidation_report.md` |
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
- la organizacion fisica objetivo esta definida conceptualmente;
- las reglas de movimiento y compatibilidad estan documentadas;
- la reversibilidad esta definida;
- `SDD Modes` queda definido como primer caso futuro;
- la aplicacion futura para capacidades cerradas queda definida;
- la frontera con `Consolidation Agent` queda explicita;
- los riesgos y decisiones abiertas estan documentados;
- existen criterios de aceptacion verificables;
- no existe ejecucion de normalizacion fisica.
