# Architecture

## Metadatos

### Architecture ID

ARCH-001

### Spec relacionada

SPEC-001 - SDD Project Consolidation and Closure

### Title

SDD Project Consolidation and Closure Documentary Architecture

### Estado

Baseline cerrado

### Responsable

Jordi Quiroga

### Ultima actualizacion

2026-08-01

### Template

No existe una plantilla oficial de arquitectura To-Be en este repositorio. Este artefacto usa una estructura inferida a partir de `.github/agents/architect.agent.md` y permanece en alcance conceptual/documental.

---

## 1. Solution Summary

`SDD Project Consolidation and Closure` introduce una arquitectura documental para cerrar capacidades SDD sin mezclar baseline vigente, expediente historico, evidencia, deuda residual y puntos de reentrada.

La solucion no crea runtime, scripts, workflows ejecutables, tools, integraciones, infraestructura ni agentes reales. Define componentes documentales, responsabilidades, interfaces y decisiones necesarias para que futuras fases puedan consolidar capacidades de forma repetible.

---

## 2. Architectural Objective

Definir una estructura conceptual y documental que permita:

- mantener un ciclo de vida oficial de capacidades SDD;
- separar baseline canonico de expedientes metodologicos cerrados;
- conservar evidencia historica sin cargarla por defecto en futuras capacidades;
- registrar deuda residual y puntos de reentrada;
- preparar handovers formales de cierre;
- incorporar en el futuro un `Consolidation Agent` metodologico sin implementarlo ahora;
- preservar el baseline cerrado de `SDD Modes`.

---

## 3. Specification Decisions Reflected

| Specification decision | Architectural reflection |
| --- | --- |
| Consolidation es fase documental posterior a Validacion | Se modela un componente `Consolidation Stage` entre `Validacion` y `Closed`. |
| Baseline canonico no equivale a expediente completo | Se separan `Registro de baseline canonico` y `Expediente cerrado`. |
| Deuda residual no puede ocultarse | Se crea `Registro de deuda residual` como componente obligatorio del cierre. |
| Reentrada debe ser formal | Se crea `Indice de reentrada` asociado a deuda y decisiones diferidas. |
| Handover formal reduce contexto futuro | Se crea `Handover de cierre` como resumen de consumo primario. |
| Consolidation Agent es conceptual | Se define interfaz futura, sin crear agente canonico ni adaptador. |
| Architecture no debe mover archivos | Toda estructura fisica se declara como propuesta futura, no como cambio aplicado. |

---

## 4. Main Components

| Componente | Responsabilidad | Estado |
| --- | --- | --- |
| Modelo de ciclo de vida de capacidad | Define estados y transiciones de capacidades SDD. | Definido conceptualmente. |
| Consolidation Stage | Agrupa verificaciones, clasificacion documental, handover y preparacion de cierre. | Definido conceptualmente. |
| Registro de baseline canonico | Identifica artefactos vigentes que futuras capacidades cargan por defecto. | Propuesto. |
| Expediente cerrado | Conserva expediente metodologico completo de una capacidad cerrada. | Propuesto. |
| Indice de evidencia historica | Referencia evidencia historica sin duplicarla completa. | Propuesto. |
| Indice de artefactos sustituidos | Registra artefactos sustituidos y su fuente vigente. | Propuesto. |
| Registro de deuda residual | Mantiene deuda residual con estado, impacto, responsable y reentrada. | Propuesto. |
| Indice de reentrada | Define puntos de reentrada y precondiciones para retomar deuda o decisiones. | Propuesto. |
| Handover de cierre | Resume estado final, decisiones, baseline, condiciones y autorizaciones. | Propuesto. |
| Consolidation Agent Interface | Define inputs/outputs conceptuales del futuro agente. | Future, non-implemented. |

---

## 5. Responsabilidades de componentes

### 5.1 Modelo de ciclo de vida de capacidad

Debe representar el ciclo:

```text
Draft -> Specification -> Architecture -> Development -> Validacion -> Consolidation -> Closed
```

Tambien debe soportar estados adicionales `On Hold`, `Archived`, `Superseded` y `Cancelled` como estados laterales con motivo, fecha, owner y condicion de salida cuando aplique.

### 5.2 Consolidation Stage

Responsable de preparar el cierre formal de una capacidad. Debe verificar:

- artefactos requeridos por modo;
- decisiones finales;
- gates y approvals;
- evidencia disponible;
- clasificacion documental;
- deuda residual;
- puntos de reentrada;
- handover formal;
- autorizaciones denegadas o pendientes.

No ejecuta cambios tecnicos ni reorganizacion fisica por si misma.

### 5.3 Registro de baseline canonico

Indice de artefactos vigentes tras una capacidad. Debe responder:

- que artefactos son canonicos;
- en que estado quedan;
- que funcion cumplen;
- que futuras capacidades deben cargar por defecto;
- que artefactos no deben cargarse salvo reentrada o auditoria.

### 5.4 Expediente cerrado

Contenedor documental del expediente completo de una capacidad cerrada. Debe preservar trazabilidad sin convertirse en baseline por defecto.

Debe incluir o referenciar:

- Brief de proyecto;
- specifications;
- architectures;
- task backlogs;
- readiness assessments;
- gates;
- reviewer findings;
- QA decisions;
- handover;
- evidence indexes;
- residual debt.

### 5.5 Indice de evidencia historica

Indice de evidencia historica. Debe referenciar evidencia, no copiarla exhaustivamente.

Puede apuntar a:

- commits o rangos Git;
- decisiones documentadas;
- tareas cerradas;
- gates;
- validaciones;
- documentos externos verificados;
- fuentes discovery-only claramente etiquetadas.

### 5.6 Indice de artefactos sustituidos

Registra documentos que ya no son fuente vigente. Cada entrada debe indicar:

- artefacto sustituido;
- fuente vigente que lo reemplaza;
- motivo de sustitucion;
- si debe conservarse por trazabilidad;
- prohibicion de uso como baseline salvo decision posterior.

### 5.7 Registro de deuda residual

Registro de deuda residual aceptada al cierre.

Campos minimos:

- ID;
- descripcion;
- tipo: technical / methodological / empirical / documentary / governance;
- estado;
- impacto;
- bloquea avance: yes/no/conditional;
- owner;
- punto de reentrada;
- evidencia requerida para cierre.

### 5.8 Indice de reentrada

Define rutas formales para reabrir deuda o decisiones sin contaminar el baseline vigente.

Cada punto de reentrada debe incluir:

- condicion de activacion;
- agente recomendado;
- artefactos que deben cargarse;
- evidencia minima;
- fase SDD esperada;
- restricciones vigentes.

### 5.9 Handover de cierre

Resumen de cierre orientado a lectura futura. Debe ser el primer artefacto que cargue un agente al retomar una capacidad cerrada.

Estructura minima propuesta:

1. Estado final.
2. Modo SDD aplicado.
3. Baseline vigente resultante.
4. Expediente historico disponible.
5. Decisiones finales.
6. Gates y aprobaciones.
7. Deuda residual.
8. Puntos de reentrada.
9. Autorizaciones no concedidas.
10. Siguiente accion valida.

### 5.10 Consolidation Agent Interface

Interfaz conceptual del futuro agente metodologico.

Inputs:

- Specification final;
- Architecture final si existe;
- task backlog final;
- readiness/gate decisions;
- context references;
- evidence indexes;
- residual debt;
- human approval.

Resultados:

- propuesta de baseline canonico;
- propuesta de expediente cerrado;
- residual debt register;
- re-entry index;
- closure handover;
- lista de actualizaciones documentales propuestas.

El agente no se crea en esta arquitectura.

---

## 6. Relationships and Interfaces

### 6.1 Lifecycle Flow

```text
Specification
    -> Architecture
    -> Development, if authorized
    -> Validacion
    -> Consolidation
    -> Closed
```

Si una capacidad no requiere Development, puede llegar a Consolidation tras Validacion documental o decision humana equivalente.

### 6.2 Consolidation Flow

```text
Final capability artifacts
    -> Consolidation Stage
    -> Classification
    -> Registro de baseline + Expediente cerrado + Indice de evidencias
    -> Deuda residual + Indice de reentrada
    -> Handover de cierre
    -> Closed
```

### 6.3 Context Loading Interface

Futuros agentes deben cargar contexto en este orden:

1. `Handover de cierre`, si existe.
2. `Registro de baseline canonico` o baseline vigente.
3. `Registro de deuda residual` y `Indice de reentrada`, si aplica.
4. Expediente cerrado solo cuando el handover o la deuda lo requieran.

### 6.4 Gate Interface

La entrada a Consolidation requiere evidencia de Validacion o decision humana equivalente. La salida a Closed requiere handover formal y aprobacion humana.

Los nombres definitivos de gates quedan para Documentacion/QA posterior, pero la arquitectura reserva dos puntos:

- `Consolidation Readiness Gate`;
- `Closure Gate`.

### 6.5 Agent Interface

Los agentes existentes siguen siendo el catalogo vigente. `Consolidation Agent` queda como futura incorporacion metodologica, no operativa.

Hasta que exista ese agente, sus responsabilidades pueden ser cubiertas documentalmente por:

- Documentation Agent para indices y handover;
- Reviewer Agent para coherencia;
- QA Gate Agent para gates;
- Responsable humano para decisiones finales.

---

## 7. Proposed Documentary Structure

La estructura definitiva recomendada para nuevas capacidades es:

```text
docs/capabilities/<capability-id>/
  project_brief.md
  context_refs.md
  tasks.md
  sdd_readiness_assessment.md
  closure_handover.md              # futuro, cuando aplique cierre
  evidence_index.md                # futuro, si el modo o riesgo lo requiere
  residual_debt.md                 # futuro, si existe deuda residual

specs/capabilities/<capability-id>/
  spec-001-<capability-id>.md
  arch-001-<capability-id>.md
```

Estructura recomendada para indices globales futuros:

```text
docs/capabilities/index.md         # catalogo de capacidades y estado
specs/capabilities/index.md        # indice de specs/architectures por capacidad
```

Esta arquitectura no crea esos indices globales ni mueve archivos. Solo define la estructura objetivo para trabajo posterior autorizado.

---

## 8. Dependencies

- `docs/capabilities/project-consolidation-and-closure/project_brief.md`
- `docs/capabilities/project-consolidation-and-closure/context_refs.md`
- `docs/capabilities/project-consolidation-and-closure/tasks.md`
- `docs/capabilities/project-consolidation-and-closure/sdd_readiness_assessment.md`
- `specs/capabilities/project-consolidation-and-closure/spec-001-sdd-project-consolidation-and-closure.md`
- Baseline final de `SDD Modes` en artefactos raiz.
- `.github/instructions/sdd.instructions.md`
- `AGENTS.md`

---

## 9. Restricciones

- No implementar runtime.
- No crear scripts ni workflows ejecutables.
- No crear el `Consolidation Agent` real.
- No crear adaptadores Codex del agente.
- No mover ni eliminar artefactos existentes.
- No modificar el baseline final de `SDD Modes`.
- No autorizar Development.
- No sustituir aprobacion humana.

---

## 10. Alternatives Considered

### Alternative A - Keep only root documents as baseline and history

Estado: Rechazada.

Pros:

- menor cambio estructural inmediato;
- no requiere nuevos indices.

Cons:

- mezcla baseline con expediente;
- obliga a futuros agentes a cargar demasiado contexto;
- no escala a multiples capacidades.

### Alternative B - One folder per capability under `docs/capabilities` and `specs/capabilities`

Estado: Seleccionada.

Pros:

- separa expedientes por capacidad;
- preserva trazabilidad;
- evita sobrescribir documentos cerrados;
- permite indices globales ligeros.

Cons:

- requiere convenciones de naming;
- requiere decidir que queda en raiz como baseline global.

### Alternative C - Single `archive/` folder for all closed work

Estado: No seleccionada para la arquitectura inicial.

Pros:

- simple para material historico.

Cons:

- puede convertir capacidades cerradas en material dificil de descubrir;
- no diferencia bien baseline, deuda y reentrada;
- puede sugerir que lo archivado ya no tiene relevancia metodologica.

### Alternative D - Dedicated consolidation package per closed capability

Estado: Reservada.

Pros:

- muy claro para auditoria formal.

Cons:

- puede aumentar carga documental;
- conviene introducirlo solo para SDD Full o capacidades de alto riesgo.

---

## 11. Architectural Decisions

### AD-001 - Use capability-scoped dossiers

Decision: Las capacidades nuevas deben usar carpetas por capacidad bajo `docs/capabilities/<capability-id>/` y `specs/capabilities/<capability-id>/`.

Razonamiento: Evita sobrescribir expedientes cerrados y permite carga de contexto selectiva.

### AD-002 - Keep root SDD Modes artifacts untouched

Decision: Los artefactos raiz de `SDD Modes` permanecen como baseline cerrado hasta una consolidacion posterior especifica.

Razonamiento: La request original prohibe modificar el baseline aprobado.

### AD-003 - Introduce handover as primary closure read

Decision: El `Handover de cierre` sera el primer artefacto recomendado para entender una capacidad cerrada.

Razonamiento: Reduce carga contextual futura sin eliminar trazabilidad.

### AD-004 - Separate residual debt from general tasks

Decision: La deuda residual de cierre debe poder registrarse como componente propio cuando exista.

Razonamiento: Las tareas cerradas no bastan para representar deuda aceptada, impacto y reentrada.

### AD-005 - Reserve global indexes for future documentation work

Decision: Los indices globales `docs/capabilities/index.md` y `specs/capabilities/index.md` son recomendados, pero no creados automaticamente por esta arquitectura.

Razonamiento: Crear indices implica actualizar navegacion global y debe ser una tarea documental posterior.

### AD-006 - Do not create Consolidation Agent yet

Decision: El `Consolidation Agent` queda como interfaz conceptual futura.

Razonamiento: La spec prohibe crear agentes reales durante esta capacidad.

---

## 12. Riesgos

| Riesgo | Impacto | Mitigacion |
| --- | --- | --- |
| La estructura propuesta se interpreta como permiso para mover archivos | Alto | Repetir que esta arquitectura no autoriza reorganizacion fisica. |
| Se duplica informacion entre handover, tasks y readiness | Medio | Handover debe resumir y referenciar, no copiar exhaustivamente. |
| Los indices globales se vuelven baseline normativo accidental | Medio | Definirlos como catalogos/routing, no como specs. |
| Deuda residual queda dispersa | Alto | Usar registro dedicado cuando exista deuda al cierre. |
| Consolidation Agent se crea antes de aprobar su definicion canonica | Alto | Mantenerlo como future consideration hasta fase autorizada. |
| Root baseline y dossiers por capacidad quedan en conflicto | Medio | Aplicar precedencia: Brief de proyecto, SDD Instructions, Specifications, Gates, documentacion auxiliar. |

---

## 13. Impacto en la arquitectura existente

Impactos futuros probables, no ejecutados en esta iteracion:

- README: explicar ciclo de vida oficial y existencia de expedientes por capacidad.
- `.github/instructions/sdd.instructions.md`: incorporar `Consolidation` y `Closed` cuando se apruebe propagacion.
- `AGENTS.md`: incorporar `Consolidation Agent` solo si una fase posterior lo autoriza.
- `.github/agents/`: crear definicion canonica del `Consolidation Agent` solo en fase posterior autorizada.
- `.codex/agents/`: crear adaptador Codex solo despues de definicion canonica.
- `docs/glosario_terminos.md`: incorporar terminos consolidados si Documentation Agent lo autoriza.
- `docs/templates/`: evaluar templates para `closure_handover.md`, `evidence_index.md` y `residual_debt.md`.
- `docs/capabilities/index.md`: crear catalogo global futuro.
- `specs/capabilities/index.md`: crear indice global futuro.

---

## 14. Open Architectural Questions

- Deben los indices globales crearse antes de consolidar esta misma capacidad?
- El `Handover de cierre` debe ser un template obligatorio para SDD Full y condicional para Lite/Minimal?
- `Registro de deuda residual` debe vivir siempre como archivo separado o como seccion del handover cuando sea pequeño?
- Que gate formal exacto aprueba entrada a Consolidation?
- Que gate formal exacto aprueba transicion a Closed?
- Como se nombraran capacidades con multiples specs o architectures?

---

## 15. Siguiente paso recomendado

```text
Reviewer Agent review of ARCH-001 and supporting artifacts.
```

Despues de review, QA Gate Agent debe evaluar si Architecture queda lista para Tasks Planner Agent o si requiere correcciones.

Development permanece `NOT AUTHORIZED`.

---

## Definition of Done

Esta arquitectura esta lista cuando:

- los componentes principales estan identificados;
- las responsabilidades estan claramente definidas;
- las interfaces documentales estan descritas;
- las dependencias y restricciones estan documentadas;
- las alternativas y decisiones arquitectonicas estan justificadas;
- el impacto sobre la arquitectura existente esta identificado;
- no se introduce implementacion, runtime, agente real ni reorganizacion fisica.
