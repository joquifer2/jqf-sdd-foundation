# Brief de proyecto - SDD Project Consolidation and Closure

## 1. Vision general del proyecto

### Nombre del proyecto

JQF SDD Foundation - SDD Project Consolidation and Closure

### Titulo de trabajo

Cierre de capacidad

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

Esta capacidad modifica el gobierno metodologico central de `jqf-sdd-foundation`: define como una capacidad cerrada se consolida, que artefactos pasan al baseline canonico, que queda como expediente historico y como se prepara el repositorio para la siguiente capacidad. Requiere trazabilidad completa, separacion estricta entre fuentes normativas e historicas y aprobacion humana.

Responsable de la decision:

Jordi Quiroga

Fecha de declaracion:

2026-08-01

Condiciones relevantes de riesgo:

- no modificar el baseline final de SDD Modes sin autorizacion explicita;
- no reorganizar fisicamente el repositorio durante Specification;
- no crear ni implementar el Consolidation Agent;
- conservar VAL-001 como deuda empirica futura no bloqueante.

Disparadores de reevaluacion:

- decision humana que autorice Architecture;
- cambio de alcance que incluya reorganizacion fisica de artefactos;
- aparicion de nuevos requisitos sobre repositorios derivados;
- propuesta de automatizacion, scripts o agente ejecutable.

---

## 2. Proposito

Esta capacidad existe para definir el proceso oficial mediante el cual una capacidad SDD finalizada se convierte en baseline consolidado de la Foundation sin sobrescribir su expediente metodologico ni cargar a futuras capacidades con contexto historico innecesario.

---

## 3. Contexto de negocio

La capacidad `SDD Modes` se cerro formalmente con artefactos finales, QA Gate aprobado y una deuda empirica futura no bloqueante. Durante ese trabajo, los documentos raiz del repositorio funcionaron como expediente metodologico concreto.

Ese uso es suficiente para una unica capacidad, pero no escala para una Foundation que debe evolucionar mediante multiples capacidades sucesivas. La Foundation necesita distinguir entre baseline vigente, expediente cerrado, evidencia historica, decisiones finales y puntos de reentrada.

---

## 4. Problema

Actualmente no existe un proceso oficial que determine:

- como cerrar una capacidad;
- que artefactos pasan al baseline canonico;
- que documentacion permanece como expediente historico;
- como se registran deudas residuales y puntos de reentrada;
- como preparar el repositorio para iniciar una nueva capacidad;
- como reducir el contexto que futuros agentes deben cargar.

Sin ese proceso, iniciar una nueva capacidad obligaria a reutilizar, sobrescribir o mezclar documentos que pertenecen a un expediente ya cerrado.

---

## 5. Resultado esperado

La Foundation debera disponer de una specification completa para `SDD Project Consolidation and Closure` que defina el modelo conceptual de consolidacion, el ciclo de vida oficial de una capacidad, la clasificacion documental, las responsabilidades y el futuro `Consolidation Agent`, sin implementar todavia ningun proceso ni reorganizacion.

---

## 6. Alcance

### Dentro de alcance

- Definir proposito, objetivos, alcance, limites y criterios de aceptacion.
- Definir el modelo conceptual de consolidacion y cierre.
- Proponer el ciclo de vida oficial de una capacidad SDD.
- Definir conceptualmente el futuro `Consolidation Agent`.
- Definir clasificacion documental: baseline vigente, expediente cerrado, evidencia historica, artefactos sustituidos, deuda residual y puntos de reentrada.
- Definir adaptacion del cierre para `SDD Minimal`, `SDD Lite` y `SDD Full`.
- Crear artefactos iniciales de Specification para esta nueva capacidad en rutas provisionales aisladas.

### Fuera de alcance

- Implementar el `Consolidation Agent`.
- Crear scripts, tools, workflows ejecutables o automatizaciones.
- Crear Architecture.
- Reorganizar fisicamente el repositorio.
- Mover, eliminar o renombrar artefactos existentes.
- Modificar documentos cerrados de `SDD Modes`.
- Autorizar Development.
- Ocultar deuda tecnica, metodologica o empirica.

---

## 7. Usuarios y stakeholders

### Usuarios principales

- Responsable de `jqf-sdd-foundation`.
- Mantenedores de la Foundation.
- Agentes metodologicos del SDD Harness.

### Usuarios secundarios

- Propietarios de proyectos derivados.
- Revisores y responsables de QA.
- Futuros agentes que trabajen sobre capacidades nuevas.

### Stakeholders

- Jordi Quiroga.
- Repositorios derivados que adopten el ciclo de vida SDD.

---

## 8. Supuestos

- `SDD Modes` esta cerrado y su baseline final no debe modificarse en esta iteracion.
- La consolidacion es una fase documental y de gobierno, no una fase de runtime.
- La estructura provisional de carpetas puede usarse hasta que Architecture defina una estructura definitiva.
- La reduccion de contexto futuro es un objetivo metodologico legitimo, siempre que no elimine trazabilidad.
- Toda decision relevante de cierre requiere validacion humana.

---

## 9. Restricciones

- Mantener el repositorio en Specification.
- No autorizar Development.
- No crear Architecture.
- No crear implementacion, scripts ni workflows.
- No mover artefactos existentes.
- No modificar el baseline aprobado de `SDD Modes`.
- Diferenciar fuentes discovery-only de fuentes normativas.

---

## 10. Riesgos

| Riesgo | Impacto | Notas |
|---|---|---|
| Confundir consolidacion con reorganizacion fisica inmediata | Alto | Esta iteracion solo especifica el proceso. |
| Modificar artefactos finales de SDD Modes | Alto | Deben tratarse como baseline cerrado salvo autorizacion explicita. |
| Ocultar deuda residual bajo la idea de cierre | Alto | La deuda debe conservar estado, responsable y punto de reentrada. |
| Crear un agente real prematuramente | Alto | El Consolidation Agent solo se define conceptualmente. |
| Aumentar la carga documental que se intenta reducir | Medio | La especificacion debe favorecer contexto minimo suficiente. |

---

## 11. Fuente de verdad

| Fuente | Proposito |
|---|---|
| `docs/capabilities/project-consolidation-and-closure/project_brief.md` | Fuente inicial de alcance y modo de esta capacidad. |
| `docs/capabilities/project-consolidation-and-closure/context_refs.md` | Indice de fuentes consultadas para esta capacidad. |
| `specs/capabilities/project-consolidation-and-closure/spec-001-sdd-project-consolidation-and-closure.md` | Specification principal de la nueva capacidad. |
| `docs/tasks.md` | Baseline historico cerrado de SDD Modes; no se modifica. |
| `specs/spec-001-sdd-modes.md` | Baseline normativo final de SDD Modes. |
| `specs/spec-001-sdd-modes.architecture.md` | Arquitectura final de SDD Modes. |

### Referencias de contexto

Documento de referencias de contexto utilizado:

`docs/capabilities/project-consolidation-and-closure/context_refs.md`

---

## 12. Criterios de exito

- Existe una specification completa y coherente de la capacidad.
- El ciclo de vida oficial de capacidades queda definido conceptualmente.
- El futuro Consolidation Agent queda definido sin implementarse.
- La clasificacion documental queda especificada.
- La adaptacion por `SDD Mode` queda especificada.
- Las decisiones abiertas para Architecture quedan registradas.
- No se modifican artefactos cerrados de `SDD Modes`.

---

## 13. Preguntas abiertas

- Cual sera la estructura definitiva de expedientes metodologicos?
- Que artefacto formal registrara la aprobacion humana de consolidacion?
- Debe existir un template especifico de handover de cierre?
- Como se versionara el baseline canonico tras multiples capacidades?
- Como se expondran puntos de reentrada futuros sin cargar todo el expediente historico?

---

## 14. Siguiente paso recomendado

```text
Revision de ARCH-001 y artefactos de soporte por Reviewer Agent, seguida de validacion de readiness de Architecture por QA Gate Agent si la revision pasa.
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
