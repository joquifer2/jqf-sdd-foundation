# Brief de proyecto - Consolidation Agent

## 1. Vision general del proyecto

### Nombre del proyecto

JQF SDD Foundation - Consolidation Agent

### Titulo de trabajo

Agente metodologico de consolidacion

### Estado

Architecture

### Responsable

Jordi Quiroga

### Ultima actualizacion

2026-08-01

---

### SDD Mode

Modo declarado para el proyecto:

- `SDD Full`

Justificacion humana del modo seleccionado:

Esta capacidad define el primer agente metodologico futuro del SDD Harness. Aunque esta iteracion no implementa el agente, afecta el gobierno central de cierre, baseline, deuda residual, puntos de reentrada, gates e interaccion entre agentes metodologicos. Requiere especificacion completa, trazabilidad y limites explicitos antes de autorizar cualquier Architecture o Development.

Responsable de la decision:

Jordi Quiroga

Fecha de declaracion:

2026-08-01

Condiciones relevantes de riesgo:

- no crear el `Consolidation Agent` real sin fase futura autorizada;
- no modificar el baseline cerrado de capacidades previas;
- no reorganizar fisicamente el repositorio;
- no permitir que el agente apruebe Specification, Architecture, QA Gates o cierre humano;
- mantener visible toda deuda residual.

Disparadores de reevaluacion:

- decision humana que autorice una fase posterior;
- propuesta de crear definicion canonica en `.github/agents/`;
- propuesta de crear adaptador Codex en `.codex/agents/`;
- propuesta de scripts, tools, workflows ejecutables o automatizacion;
- cambio de alcance que incluya reorganizacion fisica del repositorio.

---

## 2. Proposito

Definir completamente el comportamiento esperado del futuro `Consolidation Agent`, responsable de ejecutar metodologicamente el proceso definido por la capacidad cerrada `SDD Project Consolidation and Closure`.

---

## 3. Contexto de negocio

La Foundation ya cuenta con baseline cerrado para:

- `SDD Modes`;
- `SDD Project Consolidation and Closure`;
- `Foundation Derivation and Project Initialization`.

La capacidad `SDD Project Consolidation and Closure` definio el modelo de cierre, clasificacion documental, handover, deuda residual y puntos de reentrada. Al inicio de esta capacidad, el agente que aplicaria ese proceso todavia no existia. La decision humana del 2026-08-02 autorizo posteriormente el MVP documental del agente.

---

## 4. Problema

No existe una definicion especifica del comportamiento del `Consolidation Agent` que indique que puede leer, que puede producir, que decisiones puede proponer, que decisiones no puede tomar, como interactua con otros agentes, como debe actuar ante errores recuperables y como debe conservar deuda residual y puntos de reentrada.

Sin esta specification, crear el agente seria prematuro y podria confundir consolidacion documental con aprobacion, implementacion o reorganizacion fisica.

---

## 5. Resultado esperado

Una specification completa y una arquitectura documental conceptual de `Consolidation Agent`, revisadas y validadas por QA Gate de Architecture con condiciones menores. Esta capacidad no crea el agente real ni autoriza Development.

---

## 6. Alcance

### Dentro de alcance

- Definir proposito, responsabilidades y limites del agente.
- Definir entradas y salidas esperadas.
- Definir flujo operativo metodologico.
- Definir decisiones permitidas y prohibidas.
- Definir integracion con otros agentes y con aprobacion humana.
- Definir criterios de aceptacion, riesgos, dependencias, errores recuperables y puntos de reentrada.
- Crear artefactos iniciales de Specification en expediente aislado.

### Fuera de alcance

- Implementar el agente.
- Crear scripts, tools, prompts ejecutables, workflows o automatizaciones.
- Crear archivos canonicos en `.github/agents/` o adaptadores en `.codex/agents/`.
- Modificar normativa aprobada.
- Modificar el baseline cerrado de capacidades previas.
- Ejecutar consolidaciones reales.
- Normalizar fisicamente, mover, eliminar o renombrar artefactos.
- Autorizar Development.

---

## 7. Usuarios y stakeholders

### Usuarios principales

- Responsable de `jqf-sdd-foundation`.
- Mantenedores de la Foundation.
- Agentes metodologicos del SDD Harness.

### Usuarios secundarios

- Propietarios de proyectos derivados.
- Revisores y responsables de QA.
- Futuros operadores del proceso de cierre.

### Stakeholders

- Jordi Quiroga.
- Repositorios derivados que adopten el ciclo SDD.

---

## 8. Supuestos

- Las capacidades de baseline indicadas por la solicitud estan cerradas.
- El `Consolidation Agent` sera metodologico, no operativo de negocio.
- La aprobacion humana sigue siendo obligatoria para cierre y cambios de baseline.
- El agente podra proponer reorganizacion fisica, pero no ejecutarla.
- La ejecucion real del agente requerira una fase futura autorizada.

---

## 9. Restricciones

- Mantener la capacidad en `Architecture` documental tras autorizacion humana explicita.
- No ampliar Architecture fuera del alcance documental autorizado.
- No crear implementacion ni agente real.
- No modificar documentos cerrados de capacidades previas.
- No ejecutar consolidaciones reales.
- No reorganizar fisicamente el repositorio.
- No ocultar deuda ni eliminar historia Git.

---

## 10. Riesgos

| Riesgo | Impacto | Notas |
| --- | --- | --- |
| Confundir especificacion del agente con creacion del agente | Alto | Esta iteracion solo define comportamiento. |
| Convertir recomendaciones del agente en aprobaciones automaticas | Alto | El agente no sustituye Reviewer, QA Gate ni decision humana. |
| Ocultar deuda residual durante cierre | Alto | La deuda debe quedar inventariada y trazada. |
| Ejecutar reorganizacion fisica sin capacidad autorizada | Alto | Solo puede proponerla. |
| Duplicar responsabilidades de Documentation o QA Gate | Medio | La spec debe definir integraciones y limites. |

---

## 11. Fuente de verdad

| Fuente | Proposito |
| --- | --- |
| `docs/capabilities/consolidation-agent/project_brief.md` | Fuente inicial de alcance y modo de esta capacidad. |
| `docs/capabilities/consolidation-agent/context_refs.md` | Indice de fuentes consultadas para esta capacidad. |
| `specs/capabilities/consolidation-agent/spec-001-consolidation-agent.md` | Specification principal de la nueva capacidad. |
| `specs/capabilities/project-consolidation-and-closure/spec-001-sdd-project-consolidation-and-closure.md` | Baseline normativo de proceso de consolidacion. |
| `specs/capabilities/project-consolidation-and-closure/arch-001-sdd-project-consolidation-and-closure.md` | Arquitectura documental del cierre y futura interfaz del agente. |

### Referencias de contexto

Documento de referencias de contexto utilizado:

`docs/capabilities/consolidation-agent/context_refs.md`

---

## 12. Criterios de exito

- Existe `SPEC-001 - Consolidation Agent`.
- El comportamiento del agente esta definido sin implementacion.
- Las entradas, salidas, flujo, errores recuperables y reentradas estan descritos.
- Las decisiones permitidas y prohibidas son explicitas.
- Las integraciones con otros agentes no sustituyen sus responsabilidades.
- Development permanece `NOT AUTHORIZED`.

---

## 13. Preguntas abiertas

- Que forma canonica tendra la futura definicion del agente en `.github/agents/`?
- Que campos exactos usara el agente para reportar propuestas de reorganizacion fisica?
- RESUELTA 2026-08-01: QA Gate T-007 habilito decision humana y Jordi Quiroga autorizo Architecture documental.
- Que partes del comportamiento podran automatizarse en una fase futura sin sustituir decision humana?

---

## 14. Siguiente paso recomendado

```text
Decision humana sobre la siguiente fase documental de `Consolidation Agent`.
```

---

## Definition of Done

El Brief de proyecto esta completo cuando:

- el problema esta definido;
- el objetivo esta definido;
- el alcance y limites estan definidos;
- el modo SDD esta declarado;
- existen riesgos y criterios de exito;
- existe contexto suficiente para sostener la fase vigente y decidir el siguiente paso documental.
---

## 15. Development MVP Authorization and Closure Addendum

Fecha: 2026-08-02.

Decision humana posterior autorizo Development del MVP de `Consolidation Agent` dentro del alcance definido por `SPEC-001`, `ARCH-001` y el Task Plan aprobado.

Resultado:

- definicion canonica creada en `.github/agents/consolidation.agent.md`;
- adaptador Codex creado en `.codex/agents/consolidation.toml`;
- catalogos/routing sincronizados;
- validacion retrospectiva sobre SDD Modes ejecutada sin modificar su baseline;
- Reviewer final `Approved`;
- QA final `Pass with conditions`;
- capacidad cerrada como `Closed with conditions`.

Restricciones que permanecen activas:

- Development adicional no autorizado sin nueva decision y gate;
- no scripts, tools, workflows, runtime ni automatizaciones;
- no Repository Physical Normalization;
- no reorganizacion fisica;
- no modificacion de baselines cerrados.