# Specification

## Metadatos

### Spec ID

SPEC-001

### Title

Foundation Derivation and Project Initialization

### Estado

Specification

### Fase actual de la capacidad

Architecture

### Responsable

Jordi Quiroga

### Ultima actualizacion

2026-08-01

---

### SDD Mode Reference

Modo declarado para el proyecto o capacidad:

`SDD Full`

Justificacion o referencia canonica:

`docs/capabilities/foundation-derivation-and-project-initialization/project_brief.md`

Notas:

- Esta specification no autoriza Development.
- `ARCH-001` existe tras autorizacion humana explicita y QA Gate previo; esta specification no autoriza Architecture adicional por si misma.
- Esta specification no implementa asistentes, scripts, workflows ni plantillas automaticas.
- Esta specification no modifica capacidades cerradas ni baselines aprobados.

---

## 1. Proposito

Definir la capacidad metodologica `Foundation Derivation and Project Initialization`, responsable de especificar como `jqf-sdd-foundation` debe utilizarse como punto de partida oficial para crear nuevos repositorios derivados bajo metodologia SDD.

La capacidad debe separar con precision el producto reutilizable de la Foundation de sus expedientes internos de evolucion, evidencias historicas y deudas residuales.

---

## 2. Background

La Foundation ya cuenta con dos capacidades cerradas consideradas baseline metodologico vigente:

- `SDD Modes`;
- `SDD Project Consolidation and Closure`.

`SDD Modes` define los modos de gobierno metodologico. `SDD Project Consolidation and Closure` define como cerrar capacidades, distinguir baseline canonico de expediente metodologico, conservar evidencia historica y registrar deuda residual.

Aunque ese baseline permite gobernar capacidades, aun falta especificar como un repositorio nuevo debe nacer desde la Foundation sin heredar expedientes internos ni decisiones que pertenecen solo a la evolucion de la Foundation.

---

## 3. Objective

La capacidad debe definir el proceso oficial de creacion de un repositorio derivado desde `jqf-sdd-foundation`.

El resultado debe permitir que una fase posterior pueda:

- identificar el baseline exportable;
- clasificar documentos que se copian, reinician, regeneran o excluyen;
- inicializar contexto minimo del nuevo proyecto;
- declarar el SDD Mode inicial;
- crear un expediente inicial limpio;
- preservar compatibilidad futura con Foundation;
- mantener independencia metodologica del proyecto derivado;
- preparar futuras capacidades de automatizacion o normalizacion sin implementarlas.

---

## 4. Alcance

### Included

- Modelo conceptual de derivacion de Foundation.
- Definicion de baseline exportable.
- Clasificacion documental para herencia, reinicio, regeneracion y exclusion.
- Inicializacion documental por `SDD Minimal`, `SDD Lite` y `SDD Full`.
- Actores, responsabilidades, entradas y salidas.
- Reglas de gobernanza para compatibilidad futura.
- Limites entre decisiones de Foundation y decisiones del proyecto derivado.
- Restricciones, supuestos, riesgos, dependencias, criterios de aceptacion y preguntas abiertas.
- Marco preparatorio para `Consolidation Agent` y `Repository Physical Normalization`.

### Excluded

- Implementar asistentes.
- Implementar scripts.
- Crear workflows ejecutables.
- Crear plantillas automaticas.
- Reorganizar fisicamente el repositorio.
- Copiar o derivar un repositorio real.
- Modificar capacidades cerradas.
- Cambiar el baseline aprobado de `SDD Modes` o `SDD Project Consolidation and Closure`.
- Crear Architecture sin autorizacion humana explicita.
- Autorizar Development.
- Desarrollar el `Consolidation Agent`.
- Ejecutar Repository Physical Normalization.

---

## 5. Principios

### PR-001 - Separacion entre producto y expediente

El producto reutilizable de la Foundation debe distinguirse de los expedientes internos que explican como la Foundation evoluciono.

### PR-002 - Proyecto derivado limpio

Un repositorio derivado debe nacer sin tareas cerradas, readiness historica, gates de capacidades internas ni deuda residual que no le pertenezca.

### PR-003 - Herencia explicita

Ningun artefacto debe heredarse por accidente. Todo documento debe clasificarse como copiado, reiniciado, regenerado, excluido o retenido solo en Foundation.

### PR-004 - Modo declarado temprano

Todo repositorio derivado debe declarar su `SDD Mode` inicial en su Project Brief inicial.

### PR-005 - Compatibilidad sin dependencia rigida

El proyecto derivado debe poder incorporar mejoras futuras de Foundation sin perder autonomia ni sobrescribir sus decisiones propias.

### PR-006 - Trazabilidad minima suficiente

El derivado debe conservar referencia al origen Foundation y version/base de derivacion, pero no debe duplicar todo el historial metodologico.

### PR-007 - No implementacion prematura

La specification define reglas y criterios. No ejecuta derivacion, no crea tools y no normaliza fisicamente el repositorio.

---

## 6. Actors

| Actor | Descripcion |
| --- | --- |
| Responsable de Foundation | Aprueba que baseline es exportable y que restricciones aplican. |
| Maintainer de Foundation | Mantiene artefactos reutilizables y evita mezclar expedientes internos con producto derivable. |
| Propietario del proyecto derivado | Declara proposito, modo SDD inicial y contexto propio del nuevo proyecto. |
| Specification Agent | Define esta capacidad y sus limites durante Specification. |
| Architect Agent | Podra definir estructura documental y paquete derivable si se autoriza Architecture. |
| Tasks Planner Agent | Podra transformar la specification aprobada en backlog trazable. |
| Reviewer Agent | Revisa coherencia, alcance, contradicciones y suficiencia documental. |
| Documentation Agent | Podra actualizar indices, guias o templates cuando una fase posterior lo autorice. |
| QA Gate Agent | Valida readiness y criterios de fase. |
| Futuro Consolidation Agent | Podra asistir en clasificacion de baseline y expedientes, sin sustituir decision humana. |

---

## 7. Responsabilidades

| Area | Foundation | Proyecto derivado |
| --- | --- | --- |
| Metodologia SDD base | Define y mantiene baseline metodologico reutilizable. | Adopta una version/base y registra desviaciones. |
| Expedientes internos | Conserva capacidades, gates, evidencias y deuda de Foundation. | No los hereda como expediente propio. |
| Project Brief | Provee template y reglas. | Crea su propio brief inicial. |
| Context References | Provee template y referencias metodologicas. | Declara fuentes propias de negocio, cliente, repositorio y decisiones. |
| SDD Mode | Define modos disponibles. | Declara modo inicial y justificacion humana. |
| Tasks | Provee estructura. | Reinicia backlog con tareas propias. |
| Readiness | Provee estructura y criterios. | Genera readiness inicial propio. |
| Evolucion futura | Publica mejoras de baseline. | Decide si incorpora mejoras y registra impacto. |

---

## 8. Inputs

| Input | Descripcion |
| --- | --- |
| Baseline metodologico vigente | Conjunto de specs, architectures, gates, templates e instrucciones aprobadas para uso reutilizable. |
| Expedientes cerrados de Foundation | Contexto historico que ayuda a clasificar, pero no se hereda como expediente del derivado. |
| Decision humana de derivacion | Autorizacion para crear un repositorio derivado. |
| Nombre e identidad del proyecto derivado | Nombre, owner, repositorio destino y proposito inicial. |
| SDD Mode inicial propuesto | `SDD Minimal`, `SDD Lite` o `SDD Full`, con justificacion. |
| Contexto inicial del proyecto | Fuentes de negocio, cliente, tecnicas o metodologicas necesarias. |
| Version/base de Foundation | Referencia minima al estado de Foundation usado como origen. |
| Restricciones iniciales | Limites de alcance, tecnologia, cumplimiento, seguridad, integraciones o gobierno. |

---

## 9. Outputs

| Output | Descripcion |
| --- | --- |
| Repositorio derivado inicializado conceptualmente | Estado esperado de un repo nuevo tras aplicar reglas de derivacion, sin implementarlo aqui. |
| Baseline heredado declarado | Lista de artefactos reutilizables adoptados desde Foundation. |
| Expediente inicial limpio | Brief, context refs, tasks y readiness propios del proyecto derivado. |
| Declaracion de SDD Mode | Modo inicial registrado en el Project Brief del derivado. |
| Registro de origen Foundation | Referencia a repositorio, fecha, version o commit base cuando exista. |
| Matriz de herencia documental | Clasificacion de copiar, reiniciar, regenerar, excluir o retener solo en Foundation. |
| Gobernanza de actualizacion | Reglas para incorporar futuras mejoras de Foundation. |

---

## 10. Conceptos fundamentales

### Foundation

Repositorio metodologico que define baseline, templates, gates, agentes metodologicos e instrucciones reutilizables para proyectos SDD.

### Proyecto derivado

Repositorio nuevo o existente que adopta la metodologia Foundation como punto de partida, pero mantiene contexto, decisiones, backlog, readiness y evolucion propios.

### Baseline exportable

Subconjunto del baseline metodologico vigente que puede trasladarse o referenciarse en un derivado como producto reutilizable. No incluye expedientes internos salvo referencia explicita.

### Expediente interno de Foundation

Conjunto historico de artefactos que explican la evolucion de una capacidad de Foundation. Incluye tareas, gates, handovers, evidence indexes y deuda residual. Permanece en Foundation.

### Paquete derivable

Conjunto conceptual de artefactos y reglas que una fase futura podria usar para inicializar un repositorio derivado. En esta specification no se crea un paquete fisico ni automatico.

### Inicializacion limpia

Estado documental inicial en el que el derivado tiene identidad propia, modo declarado, context refs propios, backlog inicial y readiness inicial sin arrastrar expedientes internos de Foundation.

### Baseline de origen

Referencia trazable al estado de Foundation usado para iniciar el derivado. Puede ser commit, version, tag, closure handover o decision equivalente, segun defina una fase futura autorizada.

### Compatibilidad hacia delante

Capacidad del derivado de evaluar e incorporar mejoras futuras de Foundation mediante decision explicita, sin sobrescribir decisiones locales.

---

## 11. Baseline exportable

El baseline exportable debe componerse solo de elementos reutilizables como producto metodologico.

### Exportable por defecto

| Categoria | Regla |
| --- | --- |
| Templates metodologicos | Pueden copiarse como punto de partida si no contienen expedientes concretos. |
| Instrucciones SDD vigentes | Pueden copiarse o referenciarse como marco metodologico. |
| Gates conceptuales vigentes | Pueden heredarse como criterios documentales, no como gates ya ejecutados. |
| Definiciones canonicas de agentes metodologicos vigentes | Pueden copiarse si forman parte del harness reutilizable aprobado. |
| Glosario metodologico vigente | Puede copiarse o referenciarse como vocabulario inicial. |
| Specifications de baseline metodologico | Deben referenciarse como normativa de origen; copiar texto completo solo si una decision futura autorizada lo define. |

### No exportable por defecto

| Categoria | Regla |
| --- | --- |
| Project Briefs de capacidades internas | Permanecen solo en Foundation. |
| Tasks cerradas de capacidades internas | Permanecen solo en Foundation. |
| Readiness assessments de capacidades internas | Permanecen solo en Foundation. |
| Closure handovers de capacidades internas | Permanecen solo en Foundation, salvo referencia de origen. |
| Evidence indexes historicos | Permanecen solo en Foundation. |
| Residual debt de Foundation | No se convierte en deuda del derivado. Puede referenciarse como known limitation si afecta al baseline exportable. |
| Expedientes metodologicos cerrados | Permanecen en Foundation para auditoria y reentrada. |
| Evidencia historica | Permanece en Foundation salvo que una decision humana exija transferir evidencia especifica. |

### Capacidades vigentes

Las capacidades cerradas que forman baseline metodologico deben tratarse como fuente normativa o referencia de origen, no como expediente activo del derivado.

### Capacidades internas de evolucion

Las capacidades destinadas a mejorar la Foundation no deben aparecer en el derivado como trabajo pendiente, tarea activa, readiness pendiente ni decision propia.

### Deuda residual

La deuda residual de Foundation debe clasificarse en:

- deuda solo interna de Foundation;
- limitacion metodologica que afecta al baseline exportable;
- punto de reentrada futuro no aplicable al derivado;
- riesgo que el derivado debe conocer, pero no heredar como backlog propio.

---

## 12. Herencia documental

### Matriz normativa inicial

| Artefacto | Tratamiento en derivado | Regla |
| --- | --- | --- |
| `README.md` | Regenerar | Debe describir el proyecto derivado, no la Foundation, conservando referencia metodologica. |
| `AGENTS.md` | Copiar/adaptar | Debe conservar agentes metodologicos vigentes y eliminar contexto interno no aplicable si existe. |
| `.github/agents/` | Copiar/adaptar | Solo definiciones canonicas vigentes; no agentes futuros no implementados. |
| `.codex/agents/` | Regenerar/adaptar | Adaptadores segun agentes vigentes y entorno del derivado. |
| `.github/instructions/` | Copiar/adaptar | Mantener instrucciones SDD vigentes y ajustar identidad del repo. |
| `docs/templates/` | Copiar | Templates reutilizables sin instancias historicas. |
| `specs/templates/` | Copiar | Templates reutilizables sin instancias historicas. |
| `gates/` | Copiar | Gates conceptuales vigentes, no ejecuciones historicas. |
| `tools/`, `workflows/`, `tests/`, `memory/` | Pendiente de fase futura autorizada | Solo si se clasifican como harness reutilizable y no contienen estado interno. |
| `docs/project_brief.md` raiz de Foundation | Reiniciar | El derivado debe crear su propio Project Brief. |
| `docs/context_refs.md` raiz de Foundation | Reiniciar | El derivado debe declarar fuentes propias y origen Foundation. |
| `docs/tasks.md` raiz de Foundation | Reiniciar | El backlog debe empezar limpio. |
| `docs/sdd_readiness_assessment.md` raiz de Foundation | Regenerar | Debe evaluar readiness inicial del derivado. |
| `docs/capabilities/*` | Excluir por defecto | Expedientes internos de Foundation no se heredan. |
| `specs/capabilities/*` | Referenciar o excluir | Specs de baseline pueden referenciarse; expedientes no se copian como trabajo activo. |
| `specs/spec-001-sdd-modes.md` | Referenciar / copiar segun decision futura autorizada | Fuente normativa del modo; no se modifica. |
| `specs/spec-001-sdd-modes.architecture.md` | Referenciar / copiar segun decision futura autorizada | Arquitectura del baseline SDD Modes; no se modifica. |

### Estados de tratamiento

- `Copiar`: trasladar como artefacto reutilizable sin cambiar semantica.
- `Adaptar`: conservar estructura y ajustar identidad, rutas o contexto del derivado.
- `Reiniciar`: crear una instancia limpia propia del derivado.
- `Regenerar`: producir una nueva version basada en reglas y contexto inicial.
- `Excluir`: no trasladar al derivado.
- `Retener solo en Foundation`: conservar en Foundation como evidencia o expediente historico.
- `Referenciar`: registrar como fuente de origen sin copiar contenido completo.

---

## 13. Inicializacion del proyecto derivado

### Estructura inicial minima

Un derivado debe nacer con:

- identidad del proyecto;
- referencia al origen Foundation;
- Project Brief inicial;
- Context References inicial;
- Task Backlog inicial;
- Readiness Assessment inicial;
- declaracion del SDD Mode;
- metadatos minimos de repositorio, owner y fecha;
- reglas de carga de contexto;
- decision explicita sobre que baseline adopta.

### Project Brief inicial

Debe declarar:

- nombre del proyecto derivado;
- owner;
- proposito;
- problema;
- resultado esperado;
- alcance inicial;
- fuera de alcance;
- stakeholders;
- `SDD Mode`;
- justificacion humana del modo;
- restricciones y riesgos iniciales;
- fuente del baseline Foundation adoptado.

### Context References inicial

Debe declarar:

- origen Foundation;
- version/base de derivacion si existe;
- fuentes propias del proyecto;
- fuentes de cliente si aplican;
- decisiones iniciales;
- reglas de carga de contexto;
- jerarquia de conflicto;
- contexto pendiente.

### Task Backlog inicial

Debe empezar sin tareas cerradas heredadas de Foundation.

Debe incluir solo:

- tareas de inicializacion del derivado;
- tareas de discovery inicial si aplican;
- tareas de specification propias;
- gaps conocidos;
- validaciones iniciales.

### Readiness inicial

Debe evaluar si el derivado esta listo para avanzar a su siguiente fase SDD. No debe reutilizar readiness historica de Foundation como decision propia.

### Metadatos minimos

| Campo | Regla |
| --- | --- |
| `foundation_origin_repository` | Debe identificar `joquifer2/jqf-sdd-foundation` u origen equivalente. |
| `foundation_origin_reference` | Debe registrar commit, tag, fecha o decision de origen cuando exista. |
| `derived_project_name` | Obligatorio. |
| `derived_repository` | Obligatorio si ya existe repositorio destino. |
| `owner` | Obligatorio. |
| `sdd_mode` | Obligatorio o `Undeclared` con baseline conservador equivalente a `SDD Full`. |
| `initial_phase` | Debe declararse explicitamente. |

---

## 14. Compatibilidad con SDD Modes

### SDD Minimal

Uso esperado:

- proyectos de alcance muy pequeno;
- bajo riesgo;
- poca o ninguna integracion;
- cambios reversibles.

Inicializacion documental minima:

- Project Brief inicial;
- Context References inicial reducido;
- Tasks iniciales ligeras;
- Readiness inicial ligera;
- referencia al baseline Foundation;
- decision explicita de no requerir expediente Full.

Restricciones:

- no puede ocultar riesgos criticos;
- si aparece complejidad o riesgo, debe reevaluarse el modo.

### SDD Lite

Uso esperado:

- proyectos incrementales;
- riesgo medio;
- necesidad de trazabilidad razonable sin expediente completo.

Inicializacion documental minima:

- Project Brief inicial completo;
- Context References con fuentes principales;
- Tasks iniciales por incremento;
- Readiness inicial;
- decisiones iniciales;
- baseline Foundation adoptado;
- criterios de gate proporcionados al riesgo.

### SDD Full

Uso esperado:

- proyectos con alto impacto metodologico, operacional, datos, integraciones, cumplimiento o baja reversibilidad;
- derivados que nacen como foundations secundarias o plataformas.

Inicializacion documental minima:

- Project Brief completo;
- Context References completo;
- Task Backlog trazable;
- Readiness Assessment formal;
- Specification inicial o plan para crearla;
- reglas explicitas de governance;
- evidencia de decision humana de modo;
- referencia formal al baseline de origen;
- riesgos, dependencias y decisiones abiertas.

---

## 15. Gobernanza futura

### Actualizacion de baseline

Un proyecto derivado debe poder evaluar mejoras futuras de Foundation mediante:

- identificacion de version/base actual;
- revision de cambios de baseline;
- impacto sobre artefactos locales;
- decision humana de adopcion, adaptacion o rechazo;
- registro en Context References o decision log aplicable.

### Incorporacion de mejoras

Las mejoras de Foundation no deben aplicarse automaticamente si:

- cambian alcance local;
- modifican modo SDD;
- alteran gates o criterios de readiness;
- afectan decisiones locales aprobadas;
- introducen nuevos agentes, scripts o workflows.

### Independencia metodologica

El derivado puede:

- anadir reglas propias;
- adaptar templates;
- crear agentes operativos propios;
- mantener backlog y readiness propios;
- diferir mejoras de Foundation.

El derivado no debe:

- presentar expedientes internos de Foundation como propios;
- modificar historicamente el origen Foundation;
- perder trazabilidad de desviaciones metodologicas relevantes.

### Compatibilidad hacia delante

La compatibilidad debe basarse en comparacion explicita entre baseline de origen y baseline Foundation futuro, no en sobrescritura automatica.

---

## 16. Limites entre Foundation y proyecto derivado

| Decision | Responsabilidad Foundation | Responsabilidad derivado |
| --- | --- | --- |
| Definir metodologia base | Si | No, salvo extension local documentada. |
| Elegir SDD Mode del derivado | No | Si. |
| Definir contexto de negocio del derivado | No | Si. |
| Mantener expedientes internos de Foundation | Si | No. |
| Mantener backlog del derivado | No | Si. |
| Aceptar mejoras futuras | No impone adopcion | Decide y registra. |
| Crear agentes operativos | No dentro de Foundation | Si, si su proyecto lo autoriza. |
| Normalizar fisicamente repo Foundation | Si, en capacidad futura | No aplica. |

---

## 17. Preparacion para futuras capacidades

### Consolidation Agent

Esta specification deja preparado que un futuro `Consolidation Agent` pueda:

- identificar baseline exportable;
- detectar expedientes internos no exportables;
- preparar una matriz de herencia documental;
- verificar que no se heredan tareas, gates o deuda interna;
- generar recomendaciones de inicializacion;
- validar metadatos minimos.

No se crea ni implementa el agente.

### Repository Physical Normalization

Esta specification deja preparado que una futura capacidad pueda:

- definir estructura fisica del paquete derivable;
- separar directories exportables de expedientes internos;
- crear indices de baseline exportable;
- reducir ambiguedad entre raiz del repo y capacidades historicas.

No se mueve ningun archivo en esta iteracion.

---

## 18. Functional Requirements

### FR-001

La Foundation debe definir un proceso oficial de derivacion de repositorios.

### FR-002

El proceso debe distinguir baseline exportable, capacidades vigentes, capacidades internas, expedientes metodologicos, evidencia historica y deuda residual.

### FR-003

El proceso debe definir reglas para copiar, adaptar, reiniciar, regenerar, excluir, retener solo en Foundation o referenciar documentos.

### FR-004

El proceso debe exigir Project Brief inicial propio del derivado.

### FR-005

El proceso debe exigir Context References inicial propio del derivado.

### FR-006

El proceso debe exigir Task Backlog inicial limpio sin tareas cerradas heredadas.

### FR-007

El proceso debe exigir Readiness Assessment inicial propio.

### FR-008

El proceso debe exigir declaracion del SDD Mode inicial o `Undeclared` con baseline conservador equivalente a `SDD Full`.

### FR-009

El proceso debe definir metadatos minimos de origen Foundation y proyecto derivado.

### FR-010

El proceso debe definir inicializacion diferenciada para `SDD Minimal`, `SDD Lite` y `SDD Full`.

### FR-011

El proceso debe definir gobernanza de actualizacion futura desde Foundation hacia derivados.

### FR-012

El proceso debe definir limites de responsabilidad entre Foundation y proyecto derivado.

### FR-013

El proceso debe preparar futuras capacidades como `Consolidation Agent` y `Repository Physical Normalization` sin implementarlas.

---

## 19. Business Rules

### BR-001

Un repositorio derivado no debe heredar expedientes internos de capacidades Foundation como expediente propio.

### BR-002

Las tareas cerradas de Foundation no pueden convertirse en tareas cerradas del derivado.

### BR-003

La readiness historica de Foundation no puede aprobar readiness del derivado.

### BR-004

La deuda residual de Foundation no puede convertirse automaticamente en deuda del derivado.

### BR-005

El Project Brief del derivado es la fuente canonica inicial para su SDD Mode.

### BR-006

Si el SDD Mode inicial esta `Undeclared`, aplica gobierno conservador equivalente a `SDD Full` hasta declaracion aprobada.

### BR-007

Toda adopcion futura de mejoras de Foundation requiere decision explicita del derivado.

### BR-008

Copiar templates no equivale a copiar instancias historicas.

### BR-009

Referenciar un baseline cerrado no autoriza modificarlo.

### BR-010

La derivacion no autoriza Development, runtime, automatizacion ni reorganizacion fisica por si misma.

---

## 20. Restricciones

- Estado actual: Architecture documental autorizada.
- No crear Architecture adicional sin autorizacion humana explicita.
- No autorizar Development.
- No crear asistentes, scripts, workflows, tools ni automatizaciones.
- No crear plantillas automaticas.
- No mover, eliminar ni renombrar archivos.
- No modificar capacidades cerradas.
- No alterar estados de `SDD Modes` ni `SDD Project Consolidation and Closure`.
- No implementar `Consolidation Agent`.
- No ejecutar Repository Physical Normalization.

---

## 21. Supuestos

- Foundation ya dispone de baseline metodologico suficiente para definir una derivacion conceptual.
- La estructura fisica final del paquete derivable sera definida en una fase futura autorizada o capacidad futura.
- No todos los proyectos derivados requeriran el mismo nivel documental.
- La trazabilidad del origen puede representarse por commit, tag, fecha o decision hasta que Architecture defina una regla canonica.
- Los proyectos derivados pueden tener agentes operativos propios fuera de Foundation.

---

## 22. Riesgos

| Riesgo | Impacto | Notas |
| --- | --- | --- |
| Baseline exportable queda ambiguo | Alto | Una fase futura autorizada debe convertir la matriz conceptual en estructura verificable. |
| Expedientes internos se copian por comodidad | Alto | La matriz de herencia debe tratar `docs/capabilities/*` como excluido por defecto. |
| Un derivado nace sin modo SDD claro | Alto | `Undeclared` debe activar gobierno conservador. |
| Actualizaciones futuras sobrescriben decisiones locales | Alto | Se requiere adopcion explicita. |
| Repository Physical Normalization se ejecuta prematuramente | Alto | Esta specification solo prepara el marco. |
| Consolidation Agent se interpreta como disponible | Medio | Se define solo como futuro. |

---

## 23. Acceptance Criteria

### AC-001

La specification define proposito, alcance, objetivos, principios, conceptos, actores y responsabilidades.

### AC-002

La specification define entradas y salidas del proceso de derivacion.

### AC-003

La specification define baseline exportable y distingue capacidades vigentes, internas, expedientes, evidencia historica y deuda residual.

### AC-004

La specification define reglas de herencia documental para copiar, adaptar, reiniciar, regenerar, excluir, retener y referenciar.

### AC-005

La specification define inicializacion del Project Brief, Context References, Tasks, Readiness, SDD Mode y metadatos minimos.

### AC-006

La specification define inicializacion diferenciada para `SDD Minimal`, `SDD Lite` y `SDD Full`.

### AC-007

La specification define gobernanza de compatibilidad futura con Foundation.

### AC-008

La specification define limites entre responsabilidades de Foundation y proyecto derivado.

### AC-009

La specification prepara marco futuro para `Consolidation Agent` y `Repository Physical Normalization` sin implementarlos.

### AC-010

La specification registra restricciones que impiden Development, Architecture adicional no autorizada, reorganizacion fisica, modificacion de baselines cerrados o alteracion de capacidades cerradas.

---

## 24. Dependencies

- `docs/capabilities/foundation-derivation-and-project-initialization/project_brief.md`
- `docs/capabilities/foundation-derivation-and-project-initialization/context_refs.md`
- `specs/spec-001-sdd-modes.md`
- `specs/spec-001-sdd-modes.architecture.md`
- `specs/capabilities/project-consolidation-and-closure/spec-001-sdd-project-consolidation-and-closure.md`
- `specs/capabilities/project-consolidation-and-closure/arch-001-sdd-project-consolidation-and-closure.md`
- `docs/capabilities/project-consolidation-and-closure/closure_handover.md`
- `docs/capabilities/project-consolidation-and-closure/residual_debt.md`
- `docs/templates/project_brief.template.md`
- `docs/templates/context_refs.template.md`
- `docs/templates/sdd_readiness_assessment.template.md`
- `specs/templates/spec.template.md`
- `AGENTS.md`
- `README.md`

---

## 25. Preguntas abiertas

- Que artefacto versionara formalmente el baseline exportable?
- Que estructura fisica separara producto reutilizable de expedientes internos?
- Debe existir un `foundation_origin.yml` o equivalente en proyectos derivados?
- Que granularidad debe tener la matriz de herencia documental en Architecture?
- Como se documentaran desviaciones locales del derivado respecto al baseline Foundation?
- Que proceso permitira incorporar mejoras futuras sin sobrescribir decisiones locales?
- Que agente o gate validara una derivacion real?
- Que evidencia minima debe conservarse del primer caso empirico de derivacion?

---

## 26. Future Considerations

- Revisar y validar `ARCH-001` antes de cualquier planificacion posterior.
- Definir paquete derivable fisico o virtual.
- Definir matriz completa de artefactos por ruta.
- Definir mecanismo de versionado de baseline Foundation.
- Definir guia de upgrade para proyectos derivados.
- Crear futura capacidad para `Consolidation Agent`.
- Crear futura capacidad para `Repository Physical Normalization`.
- Validar el proceso con un repositorio derivado real.

---

## 27. Analisis de impacto entre artefactos

| Artefacto | Impacto | Accion requerida |
| --- | --- | --- |
| Brief de proyecto de esta capacidad | Creado como fuente inicial de modo, alcance y restricciones | Revisar durante Reviewer/QA. |
| Referencias de contexto de esta capacidad | Creado como indice de fuentes y baseline previo | Mantener actualizado si aparecen nuevas decisiones. |
| `SDD Modes` | Baseline cerrado usado como referencia de modos | No modificar. |
| `SDD Project Consolidation and Closure` | Baseline cerrado usado para clasificacion documental | No modificar. |
| Indices globales de capacidades | Podrian requerir futura actualizacion para listar esta capacidad | PENDIENTE - Documentacion posterior autorizada. |
| Templates | Podrian requerir templates de derivacion en fase futura | PENDIENTE - fase futura autorizada / Documentacion posterior. |
| README | Podria requerir explicacion de derivacion tras aprobacion | PENDIENTE - Documentacion posterior. |
| AGENTS.md | Sin impacto inmediato | No modificar en esta iteracion. |

Esta specification no propaga cambios a artefactos existentes fuera del expediente local porque la iteracion no autoriza modificar baselines aprobados ni reorganizar fisicamente el repositorio.

---

## 28. Related Artifacts

| Artefacto | Relacion |
| --- | --- |
| Brief de proyecto | `docs/capabilities/foundation-derivation-and-project-initialization/project_brief.md` |
| Referencias de contexto | `docs/capabilities/foundation-derivation-and-project-initialization/context_refs.md` |
| Readiness | `docs/capabilities/foundation-derivation-and-project-initialization/sdd_readiness_assessment.md` |
| Backlog de tareas | `docs/capabilities/foundation-derivation-and-project-initialization/tasks.md` |
| Architecture | `specs/capabilities/foundation-derivation-and-project-initialization/arch-001-foundation-derivation-and-project-initialization.md` |
| Gate | No creado en esta fase. |

---

## Definition of Done

La specification esta completa cuando:

- el objetivo esta definido;
- el alcance esta definido;
- los limites estan definidos;
- los conceptos estan definidos;
- actores y responsabilidades estan definidos;
- inputs y outputs estan definidos;
- baseline exportable y herencia documental estan definidos;
- inicializacion por SDD Mode esta definida;
- gobernanza futura esta definida;
- riesgos, dependencias y decisiones abiertas estan documentados;
- existen criterios de aceptacion verificables;
- no existe implementacion, Development ni reorganizacion fisica.
