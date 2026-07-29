# Project Brief

## 1. Project Overview

### Project Name

JQF SDD Foundation — SDD Modes

### Working Title

Adaptive SDD Governance

### Status

Proposed

### Owner

Jordi Quiroga

### Last Updated

2026-07-28

---

## 2. Purpose

Este proyecto existe para permitir que `jqf-sdd-foundation` adapte la intensidad de su gobierno metodológico al riesgo, complejidad, criticidad y contexto de cada proyecto derivado.

Actualmente, la Foundation proporciona un modelo sólido de Specification Driven Development, pero no distingue formalmente entre proyectos pequeños, experimentales o de bajo riesgo y sistemas críticos con requisitos elevados de auditoría, coordinación y trazabilidad.

El propósito de esta mejora es introducir diferentes modos oficiales de aplicación del SDD Harness sin debilitar sus principios fundamentales.

La Foundation deberá permitir que cada proyecto derivado seleccione, justifique y mantenga un nivel de gobierno proporcional a sus necesidades.

---

## 3. Business Context

`jqf-sdd-foundation` se utiliza como base metodológica para crear y evolucionar proyectos relacionados con:

* software;
* datos;
* inteligencia artificial;
* sistemas multiagente;
* automatizaciones;
* integraciones;
* plataformas analíticas;
* sistemas híbridos.

La experiencia acumulada en proyectos derivados ha demostrado que el gobierno SDD completo aporta trazabilidad, coherencia y control, pero también puede generar una carga metodológica excesiva cuando se aplica de forma uniforme a proyectos de alcance reducido.

Entre los síntomas observados se encuentran:

* proliferación de artefactos;
* gates aplicados a cambios pequeños;
* revisión por microtarea;
* crecimiento excesivo de documentos de contexto;
* fragmentación del conocimiento;
* acumulación de evidencias históricas;
* dificultad para distinguir documentos canónicos de artefactos de transición;
* pérdida de velocidad en MVPs y primeras versiones;
* dificultad para mantener y navegar los repositorios.

Al mismo tiempo, eliminar o simplificar indiscriminadamente estos controles podría introducir riesgos de seguridad, trazabilidad, cumplimiento o implementación prematura.

La mejora debe resolver esta tensión mediante una aplicación proporcional del SDD Harness.

---

## 4. Problem Statement

El modelo actual de `jqf-sdd-foundation` define un único marco general de gobierno SDD.

No existe una política formal que determine cómo deben variar, según el riesgo del proyecto:

* la documentación requerida;
* los agentes que deben intervenir;
* la frecuencia de revisión;
* los gates aplicables;
* la evidencia necesaria;
* el nivel de trazabilidad;
* la profundidad de los artefactos;
* la gestión del cambio.

Como resultado, proyectos pequeños o de riesgo controlado pueden heredar una carga metodológica similar a la de proyectos críticos.

Esto produce dos problemas opuestos.

### Sobregobierno

Se crean más artefactos, revisiones, gates y checkpoints de los necesarios para avanzar de forma segura.

### Infragobierno informal

Ante el exceso de carga, algunos proyectos pueden acabar omitiendo controles de manera no documentada, sin criterios claros ni decisión explícita.

La Foundation necesita una forma oficial de reducir o aumentar el nivel de gobierno sin abandonar los principios de SDD.

---

## 5. Desired Outcome

La Foundation deberá soportar tres modos oficiales de aplicación:

* SDD Minimal;
* SDD Lite;
* SDD Full.

Cada proyecto derivado deberá poder:

1. declarar su modo inicial;
2. justificar por qué resulta suficiente;
3. identificar controles adicionales necesarios;
4. definir qué condiciones obligarían a escalar;
5. reevaluar el modo durante su ciclo de vida;
6. reducir el modo cuando el riesgo disminuya de forma demostrable.

El modo seleccionado deberá definir un baseline proporcional para:

* artefactos;
* agentes;
* revisiones;
* gates;
* checks;
* evidencias;
* trazabilidad;
* gestión del cambio.

La mejora deberá conservar SDD Full como modelo de gobierno completo y evitar que SDD Lite o Minimal se interpreten como ausencia de control.

---

## 6. Scope

### In Scope

* Definir formalmente SDD Minimal, SDD Lite y SDD Full.
* Establecer la relación entre los modos y el SDD Harness.
* Definir criterios para seleccionar el modo inicial.
* Definir reglas para escalar o reducir el modo.
* Establecer el modo como baseline de gobierno.
* Permitir controles adicionales activados por riesgo o condición.
* Clasificar los artefactos como obligatorios, condicionales, recomendados, opcionales o no habituales según el modo.
* Incorporar la declaración y justificación del modo en los artefactos canónicos correspondientes.
* Adaptar la intervención de los agentes metodológicos al modo declarado.
* Mantener un único catálogo de agentes metodológicos.
* Evitar revisiones por microtarea en SDD Lite.
* Diferenciar formalmente entre checks ligeros y gates.
* Definir los hitos que pueden requerir revisión o gate en SDD Lite.
* Mantener gates formales para proyectos Full.
* Permitir controles específicos por privacidad, seguridad, producción o cumplimiento con independencia del modo general.
* Definir cómo debe consolidarse la evidencia en proyectos Lite.
* Mantener `context_refs.md` como índice de contexto y trazabilidad, no como historial exhaustivo.
* Actualizar la documentación normativa y las plantillas afectadas.
* Mantener compatibilidad con proyectos derivados existentes.
* Validar la propuesta sobre casos de diferente complejidad.

### Out of Scope

* Crear runtime.
* Crear agentes operativos de negocio.
* Introducir lógica específica de clientes.
* Modificar proyectos derivados como parte de la implementación inicial.
* Migrar automáticamente repositorios existentes.
* Eliminar artefactos históricos de proyectos derivados.
* Construir una herramienta ejecutable de scaffolding.
* Automatizar completamente la selección del modo.
* Sustituir la validación humana por una puntuación automática.
* Reestructurar `vca-ai`, `aif-foundation` u otros repositorios.
* Crear código productivo.
* Diseñar un sistema externo de gestión documental.
* Resolver toda la gobernanza de outputs históricos.
* Crear variantes duplicadas de cada agente para Minimal, Lite y Full.
* Fijar antes del análisis de arquitectura la lista definitiva de archivos que deberán modificarse.

---

## 7. Users and Stakeholders

### Primary Users

* Propietarios de proyectos derivados de `jqf-sdd-foundation`.
* Responsables de metodología SDD.
* Personas que crean MVPs, herramientas internas o primeras versiones funcionales.
* Equipos que mantienen proyectos críticos bajo gobierno completo.
* Agentes metodológicos que trabajan dentro del SDD Harness.

### Secondary Users

* Desarrolladores.
* Arquitectos.
* Data Engineers.
* Analytics Engineers.
* AI Engineers.
* Revisores de calidad.
* Responsables de documentación.
* Colaboradores externos que trabajan sobre repositorios derivados.

### Stakeholders

* Owner de `jqf-sdd-foundation`.
* Maintainers de la Foundation.
* Responsables de proyectos derivados.
* Usuarios de AIF Foundation.
* Usuarios de VCA-AI.
* Usuarios de otros repositorios basados en JQF SDD Foundation.

---

## 8. Assumptions

* El gobierno SDD completo sigue siendo necesario para proyectos críticos.
* No todos los proyectos necesitan la misma profundidad documental.
* La intensidad del gobierno debe ser proporcional al riesgo.
* SDD Lite será adecuado para una parte importante de los proyectos derivados.
* SDD Minimal se limitará a trabajos de bajo riesgo o naturaleza experimental.
* Los agentes existentes pueden adaptar su intervención sin necesidad de duplicarse.
* La selección del modo requiere juicio humano.
* Una matriz de decisión puede orientar, pero no sustituir, la evaluación humana.
* Un proyecto Lite puede necesitar controles formales en áreas específicas.
* Los proyectos derivados existentes deben conservar compatibilidad.
* La primera versión debe limitarse a tres modos.
* La Foundation debe seguir siendo genérica y no incorporar lógica de negocio.
* La reducción documental debe centrarse en artefactos de bajo valor, no en eliminar trazabilidad crítica.
* El versionado Git puede conservar parte del histórico sin que los documentos canónicos actúen como diarios cronológicos.

---

## 9. Constraints

* Mantener Human in the Loop.
* Mantener la prohibición de implementación prematura.
* Mantener trazabilidad suficiente.
* Mantener separación entre diseño e implementación.
* Mantener una Source of Truth identificable.
* No debilitar seguridad, privacidad, contratos o cumplimiento.
* No convertir SDD Lite en una excepción informal a SDD.
* No romper proyectos que actualmente siguen el modelo completo.
* No exigir una migración inmediata de proyectos existentes.
* Conservar SDD Full como comportamiento equivalente al gobierno actual.
* Evitar cambios incompatibles innecesarios en plantillas y agentes.
* Evitar duplicar toda la definición de modos en múltiples archivos.
* Definir una fuente normativa principal.
* Mantener README como documento de alto nivel.
* Mantener las instrucciones de agentes breves y operativas.
* No crear templates sin una función claramente diferenciada.
* Evitar que el nuevo sistema aumente la complejidad que intenta reducir.
* Mantener la mejora dentro del alcance del SDD Harness.
* No introducir runtime ni lógica de negocio.

### Modo SDD aplicado a esta mejora

Esta mejora se desarrollará inicialmente bajo SDD Full.

La razón es que modifica el modelo metodológico central de `jqf-sdd-foundation` y puede afectar a:

* reglas normativas del SDD Harness;
* criterios de readiness;
* intervención de agentes metodológicos;
* gates y checks;
* precedencia documental;
* plantillas reutilizables;
* instrucciones generales del repositorio;
* compatibilidad con proyectos derivados.

El desarrollo requiere trazabilidad completa, revisión formal y validación sobre proyectos representativos antes de considerarse estable.

Una vez implementada y validada la capacidad, podrá evaluarse una reducción del modo aplicable a su mantenimiento.

---

## 10. Risks

| Risk                                                      | Impact | Notes                                                    |
| --------------------------------------------------------- | ------ | -------------------------------------------------------- |
| Lite se interpreta como ausencia de control               | Alto   | Podría reducir seguridad, calidad o trazabilidad         |
| La selección del modo resulta subjetiva                   | Medio  | Proyectos similares podrían aplicar criterios diferentes |
| Los modos aumentan la complejidad metodológica            | Medio  | La solución podría generar más burocracia                |
| Las reglas se duplican en varios archivos                 | Medio  | Aparecerían contradicciones y mayor mantenimiento        |
| Se crean agentes separados por modo                       | Medio  | Fragmentación y duplicación del catálogo                 |
| Los proyectos existentes quedan desalineados              | Alto   | Riesgo de incompatibilidad o deuda documental            |
| Full continúa aplicándose automáticamente                 | Medio  | No se resolvería el problema original                    |
| Lite se aplica con contexto insuficiente                  | Alto   | Podría infravalorarse el riesgo                          |
| La matriz de selección se convierte en una fórmula rígida | Medio  | Sustituiría indebidamente el juicio humano               |
| Se crean demasiados templates                             | Medio  | Mayor carga de navegación y mantenimiento                |
| Los checks ligeros no dejan trazabilidad                  | Medio  | Dificultad para reconstruir decisiones relevantes        |
| Se confunden checks y gates                               | Medio  | Persistiría la proliferación de artefactos               |
| La reducción de modo elimina evidencias anteriores        | Alto   | Pérdida de auditabilidad                                 |
| La mejora se diseña solo desde proyectos complejos        | Medio  | Lite podría seguir siendo demasiado pesado               |
| La mejora se diseña solo desde MVPs                       | Alto   | Full podría quedar debilitado                            |

---

## 11. Source of Truth

| Source                                        | Purpose                                                        |
| --------------------------------------------- | -------------------------------------------------------------- |
| `docs/project_brief.md`                       | Define el propósito, alcance y resultado esperado de la mejora |
| `docs/context_refs.md`                        | Identifica las fuentes oficiales de contexto                   |
| Futura Specification de SDD Modes             | Definirá el comportamiento normativo de la capacidad           |
| `.github/instructions/sdd.instructions.md`    | Contiene las reglas operativas vigentes del SDD Harness        |
| `AGENTS.md`                                   | Define las responsabilidades de los agentes metodológicos      |
| `docs/glosario_terminos.md`                   | Contiene las definiciones oficiales                            |
| Documento conceptual aprobado sobre SDD Modes | Base de consenso previa al Project Brief                       |
| Repositorio `jqf-sdd-foundation`              | Estado real de la Foundation                                   |
| Proyectos derivados seleccionados             | Evidencia para validación y compatibilidad                     |

### Context References

Documento de referencias de contexto utilizado:

`docs/context_refs.md`

Fuentes principales consultadas:

* notas `[SDD] - SDD Modes` de Professional OS;
* documento conceptual aprobado;
* README actual de `jqf-sdd-foundation`;
* instrucciones SDD actuales;
* Project Brief Template;
* Context References Template;
* AGENTS actual;
* experiencia acumulada en proyectos derivados.

Notas relevantes sobre el contexto utilizado:

La propuesta inicial contenida en Notion debe considerarse una fuente de descubrimiento y no una specification normativa.

El documento conceptual aprobado constituye la base de consenso para este Project Brief.

La lista concreta de archivos que deberán crearse o modificarse deberá validarse durante Specification y Architecture.

---

## 12. Success Criteria

* La Foundation define claramente SDD Minimal, SDD Lite y SDD Full.
* Cada modo tiene propósito, alcance y casos de uso diferenciados.
* Todo proyecto derivado puede declarar y justificar su modo.
* Existen criterios comprensibles para seleccionar el modo inicial.
* Existen reglas explícitas para escalar o reducir el modo.
* SDD Lite reduce artefactos, revisiones y gates innecesarios.
* SDD Full mantiene el nivel de gobierno actual.
* SDD Minimal queda limitado a trabajos de bajo riesgo.
* Los controles críticos pueden activarse independientemente del modo general.
* Se diferencian formalmente checks ligeros y gates.
* Los agentes existentes adaptan su intervención sin duplicarse.
* Reviewer y QA no intervienen por defecto en cada microtarea de proyectos Lite.
* `context_refs.md` mantiene su función de índice y trazabilidad.
* La documentación normativa tiene una fuente principal identificable.
* README, instrucciones, agentes, glosario y templates quedan alineados.
* Los proyectos existentes conservan compatibilidad.
* La ausencia de modo no provoca la aplicación silenciosa de un gobierno inadecuado.
* La mejora se valida con casos de diferente complejidad.
* No se introduce runtime ni lógica de negocio.
* La Foundation sigue siendo genérica y reutilizable.

---

## 13. Open Questions

* ¿El nombre normativo debe ser `SDD Mode`, `SDD Profile` o `Governance Mode`?
* ¿Los nombres Minimal, Lite y Full deben mantenerse en inglés?
* ¿Debe utilizarse `Implementation Wave` o el concepto más general de incremento gobernado?
* ¿Cuál debe ser la fuente canónica de la declaración del modo?
* ¿Puede existir temporalmente el estado `Undeclared`?
* ¿Debe el modo aparecer también en README o en frontmatter?
* ¿Qué dimensiones formarán parte de la matriz de selección?
* ¿Qué señales obligarán a valorar SDD Full?
* ¿Qué condiciones impedirán utilizar Minimal?
* ¿Debe Lite ser una recomendación por defecto o un baseline provisional?
* ¿Quién puede aprobar el modo inicial?
* ¿Quién puede aprobar un cambio de modo?
* ¿Cada cuánto debe reevaluarse?
* ¿Minimal necesita un Project Brief reducido?
* ¿Lite necesita un template independiente?
* ¿Conviene adaptar los templates existentes en lugar de crear nuevos?
* ¿Cómo se registran checks sin generar archivos independientes?
* ¿Cómo debe consolidarse la evidencia por incremento?
* ¿Cómo recibe cada agente el modo declarado?
* ¿Las reglas de adaptación deben estar en cada agente o en una instrucción común?
* ¿Qué proyectos servirán como casos de validación?
* ¿Cómo se medirá la reducción real de carga documental?
* ¿Qué evidencia demostrará que SDD Full no se ha debilitado?

---

## 14. Next Recommended Step

```text
Create initial specification for SDD Modes.
```

La specification inicial deberá definir:

* terminología normativa;
* comportamiento de cada modo;
* reglas de selección;
* clasificación de artefactos;
* intervención de agentes;
* checks y gates;
* escalado y reducción;
* compatibilidad;
* criterios de aceptación;
* escenarios de validación.

Antes de cerrar la specification deberá realizarse un análisis de impacto sobre la estructura actual del repositorio.

---

## Definition of Done

El Project Brief está completo cuando:

* el problema está definido;
* el objetivo está definido;
* el alcance está definido;
* los límites están definidos;
* los riesgos principales son conocidos;
* existe contexto suficiente para iniciar Specification.
