# Brief de proyecto - Foundation Derivation and Project Initialization

## 1. Vision general del proyecto

### Nombre del proyecto

JQF SDD Foundation - Foundation Derivation and Project Initialization

### Titulo de trabajo

Derivacion de Foundation

### Estado

Closed

### Responsable

Jordi Quiroga

### Ultima actualizacion

2026-08-01

---

### SDD Mode

Modo declarado para el proyecto:

- `SDD Full`

Justificacion humana del modo seleccionado:

Esta capacidad define como `jqf-sdd-foundation` se transforma en punto de partida oficial para repositorios derivados. Afecta al producto reutilizable de la Foundation, a la separacion entre baseline exportable y expedientes internos, a la herencia documental y al modo SDD inicial de nuevos proyectos. Requiere trazabilidad completa y limites explicitos para evitar que un proyecto derivado nazca con historia interna, deuda o expedientes metodologicos de la Foundation.

Responsable de la decision:

Jordi Quiroga

Fecha de declaracion:

2026-08-01

Condiciones relevantes de riesgo:

- no modificar capacidades cerradas;
- no reorganizar fisicamente el repositorio;
- no crear scripts, asistentes, templates automaticos ni workflows ejecutables;
- no autorizar Development;
- mantener `Consolidation Agent` como capacidad futura pendiente;
- no crear Architecture adicional sin QA Gate y autorizacion humana explicita.

Disparadores de reevaluacion:

- decision humana que autorice Architecture;
- incorporacion de Repository Physical Normalization al alcance activo;
- decision de crear automatizacion real de derivacion;
- cambio del baseline metodologico vigente;
- necesidad de compatibilidad con un proyecto derivado real.

---

## 2. Proposito

Esta capacidad existe para especificar el proceso oficial de creacion de un repositorio derivado desde `jqf-sdd-foundation`.

El proceso debe permitir que la Foundation actue como producto metodologico reutilizable sin transferir expedientes internos, evidencia historica o deuda residual que pertenecen solo a la evolucion de la Foundation.

---

## 3. Contexto de negocio

Las capacidades `SDD Modes` y `SDD Project Consolidation and Closure` forman el baseline metodologico vigente. Ambas permiten gobernar proyectos por modo y cerrar capacidades sin mezclar baseline con expediente historico.

La Foundation todavia no dispone de una specification que explique como se deriva un repositorio nuevo, que documentos se heredan, cuales se reinician, como se declara el modo inicial y como se prepara el contexto minimo del nuevo proyecto.

---

## 4. Problema

Actualmente un nuevo repositorio derivado podria heredar documentos internos de la Foundation, tareas cerradas, readiness historica, decisiones de capacidades previas o deuda residual que no pertenecen al nuevo proyecto.

Sin un proceso oficial, no existe criterio comun para distinguir producto reutilizable, expediente metodologico, evidencia historica, deuda residual y contexto inicial del proyecto derivado.

---

## 5. Resultado esperado

Al finalizar esta iteracion debe existir una specification completa que defina la capacidad `Foundation Derivation and Project Initialization`, incluyendo reglas de baseline exportable, herencia documental, inicializacion por SDD Mode, gobernanza futura y limites entre Foundation y proyecto derivado.

La iteracion no debe implementar el proceso. El expediente queda preparado para Closure Gate tras Specification, Architecture, Review y QA de Architecture.

---

## 6. Alcance

### Dentro de alcance

- Definir el producto reutilizable de la Foundation.
- Distinguir baseline metodologico, capacidades vigentes, capacidades internas, expedientes, evidencia historica y deuda residual.
- Definir reglas para documentos copiados, reiniciados, regenerados, excluidos y conservados solo en Foundation.
- Definir estructura y contexto inicial del proyecto derivado.
- Definir Project Brief inicial, Context References inicial, Tasks iniciales, Readiness inicial y declaracion de SDD Mode.
- Definir gobernanza de compatibilidad futura con la Foundation.
- Definir limites entre responsabilidades de Foundation y proyecto derivado.
- Definir diferencias de inicializacion para `SDD Minimal`, `SDD Lite` y `SDD Full`.
- Preparar marco conceptual para `Consolidation Agent` y `Repository Physical Normalization` sin implementarlos.

### Fuera de alcance

- Implementar asistentes, scripts, herramientas, comandos o workflows.
- Reorganizar fisicamente el repositorio.
- Crear plantillas automaticas.
- Modificar capacidades cerradas.
- Cambiar el baseline aprobado de `SDD Modes` o `SDD Project Consolidation and Closure`.
- Crear Architecture adicional sin autorizacion humana explicita.
- Autorizar Development.
- Crear o implementar el `Consolidation Agent`.
- Ejecutar la normalizacion fisica del repositorio.

---

## 7. Usuarios y stakeholders

### Usuarios principales

- Responsable de `jqf-sdd-foundation`.
- Mantenedores de la Foundation.
- Propietarios de nuevos proyectos derivados.
- Agentes metodologicos del SDD Harness.

### Usuarios secundarios

- Revisores documentales.
- QA Gate Agent.
- Futuros equipos que adopten la metodologia SDD.

### Stakeholders

- Jordi Quiroga.
- Repositorios derivados que usen `jqf-sdd-foundation` como origen metodologico.

---

## 8. Supuestos

- La Foundation ya dispone de baseline metodologico vigente suficiente para ser reutilizada.
- Los expedientes internos de capacidades cerradas no deben convertirse automaticamente en contenido del proyecto derivado.
- Un proyecto derivado debe declarar su propio SDD Mode durante la inicializacion.
- La compatibilidad futura con Foundation no elimina la independencia metodologica del proyecto derivado.
- La implementation futura requerira Architecture revisada, QA Gate aplicable y autorizacion humana explicita.

---

## 9. Restricciones

- Mantener la capacidad en Architecture documental hasta review y QA Gate aplicables.
- No autorizar Development.
- No crear Architecture adicional sin autorizacion humana explicita.
- No modificar ningun baseline aprobado.
- No mover archivos.
- No reorganizar fisicamente el repositorio.
- No alterar el estado de capacidades cerradas.
- No introducir cambios funcionales ni runtime.

---

## 10. Riesgos

| Riesgo | Impacto | Notas |
| --- | --- | --- |
| El repositorio derivado hereda expedientes internos de Foundation | Alto | La specification debe clasificar exclusions con claridad. |
| La derivacion se interpreta como normalizacion fisica inmediata | Alto | La normalizacion queda futura y no autorizada. |
| Se copia deuda residual de Foundation como si fuera deuda del proyecto | Alto | La deuda residual puede referenciarse, pero no heredarse automaticamente. |
| Se declara un SDD Mode inicial sin decision responsable | Alto | El Project Brief del derivado debe ser fuente canonica inicial. |
| La compatibilidad futura se confunde con dependencia rigida | Medio | El proyecto derivado debe poder evolucionar con independencia controlada. |

---

## 11. Fuente de verdad

| Fuente | Proposito |
| --- | --- |
| `docs/capabilities/foundation-derivation-and-project-initialization/project_brief.md` | Fuente inicial de alcance y modo de esta capacidad. |
| `docs/capabilities/foundation-derivation-and-project-initialization/context_refs.md` | Indice de fuentes consultadas. |
| `specs/capabilities/foundation-derivation-and-project-initialization/spec-001-foundation-derivation-and-project-initialization.md` | Specification principal de la capacidad. |
| `specs/spec-001-sdd-modes.md` | Baseline metodologico vigente de SDD Modes. |
| `specs/capabilities/project-consolidation-and-closure/spec-001-sdd-project-consolidation-and-closure.md` | Baseline vigente para clasificacion de capacidades y expedientes. |

### Referencias de contexto

Documento de referencias de contexto utilizado:

`docs/capabilities/foundation-derivation-and-project-initialization/context_refs.md`

---

## 12. Criterios de exito

- Existe Project Brief de la capacidad.
- Existe Context References de la capacidad.
- Existe `SPEC-001 - Foundation Derivation and Project Initialization`.
- Existe readiness assessment inicial.
- Existe task backlog inicial.
- La specification cubre baseline exportable, herencia documental, inicializacion, gobernanza, limites, modos SDD y preparacion futura.
- No hay implementacion, scripts, agentes reales, Development ni reorganizacion fisica.

---

## 13. Preguntas abiertas

- Que artefacto futuro versionara formalmente el baseline exportable?
- Que estructura fisica final tendra un paquete derivable?
- Como se compararan cambios de Foundation contra proyectos derivados ya inicializados?
- Que partes podra automatizar un futuro asistente sin sustituir decision humana?
- Que evidencia minima debe registrar el primer proyecto derivado real?

---

## 14. Siguiente paso recomendado

```text
No hay siguiente paso activo. Reentrada futura mediante handover y residual debt.
```

---

## Definition of Done

El Brief de proyecto esta completo cuando:

- el problema esta definido;
- el objetivo esta definido;
- el alcance y limites estan definidos;
- el modo SDD esta declarado;
- existen riesgos y criterios de exito;
- existe contexto suficiente para iniciar Specification.
