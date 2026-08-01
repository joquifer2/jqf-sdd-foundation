# Architecture

## Metadatos

### Architecture ID

ARCH-001

### Spec relacionada

SPEC-001 - Foundation Derivation and Project Initialization

### Title

Foundation Derivation and Project Initialization Documentary Architecture

### Estado

Architecture

### Responsable

Jordi Quiroga

### Ultima actualizacion

2026-08-01

### Template

No existe una plantilla oficial de arquitectura To-Be en este repositorio. Este artefacto usa una estructura inferida a partir de `.github/agents/architect.agent.md` y permanece en alcance conceptual/documental.

---

## 1. Solution Summary

`Foundation Derivation and Project Initialization` define una arquitectura documental para que `jqf-sdd-foundation` pueda actuar como origen metodologico de repositorios derivados sin transferir expedientes internos, evidencia historica o deuda residual propia de la Foundation.

La solucion no crea runtime, scripts, workflows ejecutables, tools, integraciones, infraestructura, plantillas automaticas ni asistentes. Define componentes documentales, responsabilidades, interfaces, decisiones y restricciones necesarias para una futura implementacion controlada.

---

## 2. Architectural Objective

Definir una estructura conceptual que permita:

- identificar el baseline exportable de la Foundation;
- separar producto reutilizable de expediente interno;
- clasificar artefactos por tratamiento de herencia;
- inicializar un proyecto derivado con expediente propio limpio;
- registrar origen Foundation y modo SDD inicial;
- preservar compatibilidad futura sin sobrescritura automatica;
- preparar futuras capacidades como `Consolidation Agent` y `Repository Physical Normalization` sin implementarlas.

---

## 3. Specification Decisions Reflected

| Specification decision | Architectural reflection |
| --- | --- |
| El derivado debe nacer limpio | Se define `Derived Project Initial Dossier` como expediente nuevo, no heredado. |
| El baseline exportable no equivale al expediente completo | Se separan `Exportable Baseline Registry` y `Foundation Internal Dossier Boundary`. |
| Todo artefacto requiere tratamiento explicito | Se define `Document Inheritance Matrix`. |
| El SDD Mode inicial vive en el Project Brief del derivado | Se define `Initial SDD Mode Declaration Interface`. |
| La compatibilidad futura requiere adopcion explicita | Se define `Foundation Upgrade Intake Interface`. |
| La deuda residual de Foundation no se hereda automaticamente | Se define `Residual Debt Boundary`. |
| Consolidation Agent y Repository Physical Normalization son futuras | Se definen interfaces preparatorias, no componentes ejecutables. |

---

## 4. Main Components

| Componente | Responsabilidad | Estado |
| --- | --- | --- |
| Exportable Baseline Registry | Identificar artefactos reutilizables de Foundation. | Propuesto documentalmente. |
| Foundation Internal Dossier Boundary | Separar expedientes internos, evidencia y deuda no exportable. | Propuesto documentalmente. |
| Document Inheritance Matrix | Clasificar artefactos como copiar, adaptar, reiniciar, regenerar, excluir, retener o referenciar. | Propuesto documentalmente. |
| Derived Project Initial Dossier | Definir el expediente inicial limpio del derivado. | Propuesto documentalmente. |
| Foundation Origin Record | Registrar origen, fecha, version, commit o decision base. | Propuesto documentalmente. |
| Initial SDD Mode Declaration Interface | Asegurar declaracion de modo y justificacion en el Project Brief del derivado. | Propuesto documentalmente. |
| Mode-Specific Initialization Profile | Definir diferencias documentales para Minimal, Lite y Full. | Propuesto documentalmente. |
| Foundation Upgrade Intake Interface | Gobernar adopcion futura de mejoras de Foundation. | Propuesto documentalmente. |
| Residual Debt Boundary | Impedir herencia automatica de deuda de Foundation. | Propuesto documentalmente. |
| Future Automation Boundary | Delimitar que podran hacer futuros asistentes sin sustituir decision humana. | Future, non-implemented. |

---

## 5. Component Responsibilities

### 5.1 Exportable Baseline Registry

Indice conceptual de artefactos reutilizables por un proyecto derivado. Debe distinguir:

- templates reutilizables;
- instrucciones SDD vigentes;
- gates conceptuales vigentes;
- agentes metodologicos canonicos vigentes;
- glosario metodologico;
- specifications de baseline que deben referenciarse o copiarse segun decision futura.

No debe incluir tareas cerradas, readiness historica, handovers internos, evidence indexes ni deuda residual salvo referencia explicita como limitacion conocida.

### 5.2 Foundation Internal Dossier Boundary

Define que permanece solo en Foundation:

- expedientes de capacidades cerradas;
- decisiones internas de evolucion;
- evidencia historica;
- residual debt de Foundation;
- gates ya ejecutados;
- tareas y readiness de capacidades previas.

Este limite protege al derivado de nacer con historial ajeno.

### 5.3 Document Inheritance Matrix

Matriz de tratamiento por artefacto o familia de artefactos.

Estados soportados:

- `Copy`;
- `Adapt`;
- `Reset`;
- `Regenerate`;
- `Exclude`;
- `Retain in Foundation only`;
- `Reference`.

Una fase futura autorizada o Documentation autorizada podra convertir esta matriz conceptual en una matriz por ruta completa. Esta arquitectura no crea esa matriz fisica.

### 5.4 Derived Project Initial Dossier

Expediente inicial del derivado. Debe contener como minimo:

- `project_brief.md` propio;
- `context_refs.md` propio;
- `tasks.md` propio;
- `sdd_readiness_assessment.md` propio;
- referencia a baseline Foundation adoptado;
- estado inicial y siguiente fase esperada.

No debe contener tareas cerradas, gates ejecutados o readiness de Foundation.

### 5.5 Foundation Origin Record

Registro minimo de procedencia. Puede vivir como seccion de `context_refs.md` o como artefacto dedicado futuro si una fase futura autorizada lo justifica.

Campos minimos:

- `foundation_origin_repository`;
- `foundation_origin_reference`;
- `foundation_origin_date`;
- `derived_project_name`;
- `derived_repository`;
- `owner`;
- `sdd_mode`;
- `initial_phase`.

### 5.6 Initial SDD Mode Declaration Interface

Interfaz documental que exige que el Project Brief del derivado declare:

- modo seleccionado;
- justificacion humana;
- owner;
- fecha;
- riesgos relevantes;
- disparadores de reevaluacion.

Si el modo queda `Undeclared`, se aplica baseline conservador equivalente a `SDD Full`.

### 5.7 Mode-Specific Initialization Profile

Define perfiles documentales por modo:

| Modo | Perfil inicial |
| --- | --- |
| `SDD Minimal` | Brief, context refs reducido, tasks ligeras, readiness ligera, referencia a origen. |
| `SDD Lite` | Brief completo, context refs con fuentes principales, backlog incremental, readiness y decisiones iniciales. |
| `SDD Full` | Brief completo, context refs completo, backlog trazable, readiness formal, plan/spec inicial y governance explicita. |

El perfil no puede debilitar controles criticos ni sustituir decision humana.

### 5.8 Foundation Upgrade Intake Interface

Gobierna mejoras futuras desde Foundation hacia derivados.

Proceso conceptual:

```text
Foundation baseline change
  -> Derived project impact review
  -> Adopt / Adapt / Defer / Reject decision
  -> Local documentation update if authorized
  -> Readiness or gate if risk requires
```

No existe actualizacion automatica.

### 5.9 Residual Debt Boundary

Clasifica deuda residual de Foundation antes de que un derivado la vea:

- deuda interna de Foundation;
- limitacion metodologica que afecta al baseline exportable;
- punto de reentrada no aplicable al derivado;
- riesgo informativo para el derivado.

Solo las limitaciones que afecten al baseline exportable deben aparecer como contexto del derivado, y no como deuda propia salvo decision explicita.

### 5.10 Future Automation Boundary

Un futuro asistente o `Consolidation Agent` podra preparar propuestas, matrices o checks documentales, pero no podra:

- crear repositorios derivados sin decision humana;
- mover archivos de Foundation sin autorizacion;
- modificar baselines cerrados;
- elegir el modo SDD por scoring automatico;
- crear runtime, workflows ejecutables o herramientas productivas dentro de esta Foundation.

---

## 6. Relationships and Interfaces

### 6.1 Derivation Preparation Flow

```text
Foundation baseline
  -> Exportable Baseline Registry
  -> Document Inheritance Matrix
  -> Derived Project Initial Dossier
  -> Foundation Origin Record
  -> Initial SDD Mode Declaration
  -> Initial Readiness
```

### 6.2 Context Loading Interface

Para trabajar sobre esta capacidad, futuros agentes deben cargar:

1. Project Brief de esta capacidad.
2. Context References de esta capacidad.
3. `SPEC-001`.
4. `ARCH-001`.
5. Baseline cerrado de `SDD Modes` y `SDD Project Consolidation and Closure` solo como referencia.

### 6.3 Derived Repository Initialization Interface

Una futura implementacion debera producir o validar:

- identidad del derivado;
- origen Foundation;
- expediente inicial propio;
- modo SDD inicial;
- backlog limpio;
- readiness inicial;
- lista de artefactos heredados y excluidos.

### 6.4 Upgrade Interface

La actualizacion futura desde Foundation hacia un derivado requiere:

- baseline de origen del derivado;
- cambio Foundation propuesto;
- impacto local;
- decision humana;
- registro documental;
- gate si cambia riesgo, modo o alcance.

---

## 7. Proposed Documentary Structure

### 7.1 Estructura conceptual del paquete derivable

```text
foundation-derivable-baseline
  reusable-methodology
  reusable-templates
  reusable-gates
  reusable-agent-definitions
  baseline-references
  derivation-guidance
```

Esta estructura es conceptual. No se crea directorio fisico en esta fase.

### 7.2 Estructura inicial recomendada para repositorio derivado

```text
README.md                         # regenerado para el proyecto derivado
AGENTS.md                         # copiado/adaptado con agentes metodologicos vigentes
.github/                          # copiado/adaptado segun baseline exportable
.codex/                           # regenerado/adaptado

docs/
  project_brief.md                # reiniciado
  context_refs.md                 # reiniciado
  tasks.md                        # reiniciado
  sdd_readiness_assessment.md     # regenerado
  templates/                      # copiado si aplica

specs/
  templates/                      # copiado si aplica

gates/                            # copiado como gates conceptuales, no ejecuciones historicas
```

### 7.3 Estructura retenida en Foundation

```text
docs/capabilities/*               # expedientes internos de Foundation
specs/capabilities/*              # expedientes/specs de capacidades Foundation, salvo baseline referenciado
docs/capabilities/*/evidence_index.md
docs/capabilities/*/residual_debt.md
docs/capabilities/*/closure_handover.md
```

---

## 8. Dependencies

- `docs/capabilities/foundation-derivation-and-project-initialization/project_brief.md`
- `docs/capabilities/foundation-derivation-and-project-initialization/context_refs.md`
- `specs/capabilities/foundation-derivation-and-project-initialization/spec-001-foundation-derivation-and-project-initialization.md`
- `docs/capabilities/foundation-derivation-and-project-initialization/tasks.md`
- `docs/capabilities/foundation-derivation-and-project-initialization/sdd_readiness_assessment.md`
- `specs/spec-001-sdd-modes.md`
- `specs/spec-001-sdd-modes.architecture.md`
- `specs/capabilities/project-consolidation-and-closure/spec-001-sdd-project-consolidation-and-closure.md`
- `specs/capabilities/project-consolidation-and-closure/arch-001-sdd-project-consolidation-and-closure.md`
- `.github/instructions/sdd.instructions.md`
- `AGENTS.md`

---

## 9. Restrictions

- No implementar runtime.
- No crear scripts, tools ni workflows ejecutables.
- No crear asistentes reales.
- No crear plantillas automaticas.
- No mover ni eliminar artefactos existentes.
- No reorganizar fisicamente el repositorio.
- No modificar baselines cerrados.
- No crear `Consolidation Agent` real.
- No ejecutar `Repository Physical Normalization`.
- No autorizar Development.
- No sustituir decision humana.

---

## 10. Alternatives Considered

### Alternative A - Copiar todo el repositorio Foundation como punto de partida

Estado: Rechazada.

Pros:

- simple operacionalmente;
- conserva todo el material disponible.

Cons:

- transfiere expedientes internos;
- hereda tareas, readiness y deuda ajena;
- dificulta distinguir producto de historia;
- contradice la specification.

### Alternative B - Paquete derivable conceptual con matriz de herencia

Estado: Seleccionada.

Pros:

- separa producto reutilizable de expediente;
- permite inicializacion limpia;
- conserva trazabilidad;
- no requiere reorganizacion fisica inmediata;
- deja margen a documentacion o normalizacion futura autorizada.

Cons:

- requiere disciplina documental;
- aun necesita versionado formal de baseline.

### Alternative C - Crear carpeta fisica `exportable/` ahora

Estado: Rechazada para esta fase.

Pros:

- clarifica visualmente el producto derivable.

Cons:

- implica reorganizacion fisica no autorizada;
- puede duplicar artefactos;
- requiere Repository Physical Normalization.

### Alternative D - Derivacion solo por instrucciones README

Estado: No seleccionada.

Pros:

- muy ligera.

Cons:

- insuficiente para SDD Full;
- no define interfaces, matrices ni gobernanza de upgrades;
- alto riesgo de herencia accidental.

---

## 11. Architectural Decisions

### AD-001 - Use a conceptual derivable package

Decision: Definir un paquete derivable conceptual, no fisico, hasta que una fase futura autorice normalizacion.

Razonamiento: Cumple el objetivo sin mover archivos ni duplicar baseline.

### AD-002 - Treat internal capability dossiers as non-exportable by default

Decision: `docs/capabilities/*` y expedientes equivalentes quedan excluidos por defecto.

Razonamiento: Evita que el derivado herede historia interna de la Foundation.

### AD-003 - Reset root project artifacts in derived repositories

Decision: Project Brief, Context References, Tasks y Readiness del derivado deben reiniciarse o regenerarse.

Razonamiento: Son identidad y estado propios del proyecto derivado.

### AD-004 - Reference baseline specs unless future authorized decision allows copying

Decision: Las specs de baseline pueden referenciarse como normativa de origen; copiar texto completo queda condicionado a decision futura autorizada.

Razonamiento: Reduce duplicacion y contradicciones entre Foundation y derivados.

### AD-005 - Keep SDD Mode declaration in the derived Project Brief

Decision: El modo inicial del derivado se declara en su Project Brief.

Razonamiento: Alinea con `SDD Modes` y preserva decision humana.

### AD-006 - No automatic upgrades from Foundation

Decision: Las mejoras futuras requieren intake, decision y registro local.

Razonamiento: Protege independencia metodologica del derivado.

### AD-007 - Future automation is advisory

Decision: Futuros asistentes solo podran proponer o verificar, no ejecutar derivacion sin decision humana.

Razonamiento: Mantiene Human in the Loop y evita implementacion prematura.

---

## 12. Risks

| Riesgo | Impacto | Mitigacion |
| --- | --- | --- |
| Paquete conceptual se interpreta como estructura fisica creada | Alto | Repetir que no se crea directorio ni se mueve nada. |
| Matriz de herencia queda incompleta para implementacion | Medio | Tasks Planner/Documentation posterior debe ampliar a matriz por ruta. |
| Baseline specs copiadas crean divergencia | Alto | Preferir referencia hasta decision futura. |
| Upgrade futuro sobrescribe decisiones locales | Alto | Intake explicito y decision humana. |
| Deuda Foundation se invisibiliza aunque afecte al derivado | Medio | Clasificar como limitacion conocida si afecta al baseline exportable. |
| Automation boundary se ignora en fases futuras | Alto | Mantener restricciones en gates y future capability specs. |

---

## 13. Impact on Existing Architecture

Impactos futuros probables, no ejecutados en esta iteracion:

- `docs/capabilities/index.md`: listar esta capacidad cuando Documentation lo autorice.
- `specs/capabilities/index.md`: listar `SPEC-001` y `ARCH-001` de esta capacidad.
- README: explicar derivacion oficial cuando la capacidad avance.
- `docs/templates/`: evaluar si hacen falta templates de `foundation_origin` o matriz de herencia.
- `docs/glosario_terminos.md`: incorporar terminos como baseline exportable, paquete derivable e inicializacion limpia.
- `gates/`: evaluar un futuro `Derivation Readiness Gate`.
- `.github/agents/`: no cambia en esta fase; no se crea agente nuevo.

---

## 14. Open Architectural Questions

- El baseline exportable se versionara por tag Git, commit, release note, handover o artefacto dedicado?
- Debe existir un archivo `foundation_origin.yml` o bastan secciones en `context_refs.md`?
- Que matriz por ruta sera obligatoria para una derivacion real?
- Debe existir un `Derivation Readiness Gate` separado o una extension de readiness inicial?
- Como se gestionaran forks o derivados que modifiquen la metodologia localmente?
- Que artefactos bajo `tools/`, `workflows/`, `tests/` y `memory/` son exportables, si alguno?

---

## 15. Next Recommended Step

```text
QA Gate Agent readiness review of Architecture after Reviewer corrections.
```

Reviewer Agent emitio `Approved with minor changes` y las correcciones menores fueron aplicadas. QA Gate Agent debe evaluar readiness de Architecture antes de cualquier planificacion documental posterior.

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
- no se introduce implementacion, runtime, agente real, workflow ejecutable ni reorganizacion fisica.