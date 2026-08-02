# Context References

# Referencias de Contexto del Proyecto

> Este documento define las fuentes de contexto oficiales que deben consultarse antes de generar o modificar cualquier Project Brief, Spec, documento de Arquitectura, Tasks, código o documentación técnica de este proyecto.
>
> No debe duplicar el contenido completo del CCD, decisiones, reuniones, proyectos anteriores o documentación externa.
>
> Su función es actuar como índice de referencias y trazabilidad del contexto utilizado.

---

# 1. Identidad del Proyecto

```yaml
proyecto:
  nombre: JQF SDD Foundation - SDD Modes
  id_proyecto: sdd-modes
  tipo_proyecto: foundation-methodology-improvement
  estado: Completed with conditions - no Development
  fecha_creacion: 2026-07-29
  responsable: Jordi Quiroga

cliente:
  id_cliente: N/A
  nombre_cliente: N/A
  estado_relacion: N/A
```

---

# 2. Contexto de Cliente Requerido

## CCD - Client Context Document

```yaml
ccd:
  requerido: false

  fuente_humana:
    sistema: N/A
    ubicacion: N/A

  fuente_runtime_ia:
    sistema: N/A
    uri: N/A

  version: N/A
  estado: N/A
  ultima_revision: N/A
  fecha_consulta: 2026-07-29
```

## Notas sobre el uso del CCD

Esta iniciativa pertenece a `jqf-sdd-foundation` y no a un proyecto de cliente derivado.

No se requiere CCD para iniciar el contexto de SDD Modes.

Si durante fases posteriores se usan proyectos derivados como casos de validacion, deberan registrarse sus fuentes de contexto especificas antes de extraer conclusiones metodologicas.

---

# 3. Decisiones Relacionadas

> La fuente oficial de decisiones es la base `Decisiones` del SO Profesional.
>
> Esta sección solo referencia decisiones relevantes para este proyecto.

| Fecha | Decisión | Impacto en este proyecto | Fuente |
| --- | --- | --- | --- |
| 2026-07-05 | Nota de Professional OS `[SDD] - SDD Modes` | Fuente de descubrimiento verificada; confirma origen de la iniciativa y remite los artefactos oficiales al repositorio GitHub | Professional OS / Notion: https://app.notion.com/p/3942fcf6211d80e9a9c8cab594ea0a67 |
| PENDING | Documento conceptual consensuado sobre SDD Modes | Fuente de descubrimiento metodologico previa; sin valor normativo hasta verificar ubicacion y version canonica | PENDING - discovery-only; ubicacion y version canonica no verificables desde el repositorio |

## Decisiones pendientes de validar

| Tema | Motivo de la duda | Responsable | Estado |
| --- | --- | --- | --- |
| Ubicacion canonica del documento conceptual consensuado | La referencia existe en el Project Brief, pero el repositorio no contiene URI, version ni fecha verificable tras busqueda local | Jordi Quiroga | PENDING - discovery-only |

---

# 4. Proyectos Relacionados

> Referenciar proyectos anteriores o activos que puedan afectar al diseño, alcance o implementación de este proyecto.

| Proyecto | Relación con este proyecto | Estado | Fuente |
| --- | --- | --- | --- |
| VAL-001 - SDD Minimal | Experimento o utilidad interna de bajo riesgo | PENDING - non-blocking empirical debt | No se ha identificado un repositorio concreto verificable que cumpla claramente bajo riesgo, ausencia de datos sensibles, ausencia de produccion y alta reversibilidad. Por decision humana posterior a T-027, no bloquea el cierre metodologico de SDD Modes ni debilita controles de Minimal. |
| VAL-002 - SDD Lite | Candidato retrospectivo para contrastar si un MVP o primera version con exposicion limitada habria encajado en `SDD Lite` | Formal status: `Undeclared`; validation candidate: verified-local-git | `joquifer_system_agents`; remoto `https://github.com/joquifer2/joquifer_system_agents.git`; rama local `main`; README lo describe como MVP Python manual para analisis modular BigQuery con controles; no declara `SDD Mode` por ser anterior a SDD Modes. |
| VAL-003 - SDD Full | Candidato retrospectivo para contrastar si un producto con integraciones criticas habria requerido `SDD Full` | Formal status: `Undeclared`; validation candidate: verified-local-git-and-notion | `bigquery_mcp_server`; remoto `https://github.com/joquifer2/bigquery-mcp-server.git`; rama local `main`; Professional OS `https://app.notion.com/39c2fcf6211d8098a726e663dace976b`; README declara producto estable, MCP, BigQuery, allowlist, dry run, cuotas, auditoria y validacion real; no declara `SDD Mode` por ser anterior a SDD Modes. |
| VAL-003 - SDD Full | Candidato retrospectivo para contrastar si un producto derivado con cliente, fuentes externas, gates y Development limitado habria requerido `SDD Full` | Formal status: `Undeclared`; validation candidate: verified-notion-github | `neovaultech-system`; repositorio canonico `https://github.com/joquifer2/neovaultech-system`; Professional OS `https://app.notion.com/p/3a82fcf6211d81bc9704fa9c233ef2b2`; ficha verificada indica origen en `jqf-sdd-foundation`, SPEC-001, baseline, plan y Development Readiness Gate publicados; no se verifica declaracion `SDD Mode` porque el proyecto es anterior a SDD Modes. |
| VAL-004 - Undeclared | Candidato retrospectivo para validar compatibilidad de repositorios SDD existentes sin `SDD Mode` declarado | Formal status: `Undeclared`; validation candidate: verified-local-git | `aif-foundation`; remoto `https://github.com/joquifer2/analytical-intelligence-foundation.git`; rama local `main`; contiene artefactos SDD extensos y no se encontro declaracion `SDD Mode` en busqueda local; representa el tratamiento conservador de repositorios anteriores a SDD Modes. |

---

# 5. Reuniones Relacionadas

> Referenciar reuniones relevantes que contengan acuerdos, contexto, decisiones o restricciones aplicables.

| Fecha | Reunión | Información relevante | Fuente |
| --- | --- | --- | --- |
| PENDING | PENDING | No hay reuniones verificables desde el repositorio para esta iniciativa | PENDING |

---

# 6. Conocimiento Reutilizable Relacionado

> Referenciar plantillas, SOPs, frameworks, prompts, documentación técnica o investigaciones que deban consultarse.

| Recurso | Tipo | Motivo de uso | Fuente |
| --- | --- | --- | --- |
| `docs/project_brief.md` | Project Brief | Definicion canonica inicial de la iniciativa SDD Modes | Verificado en repositorio |
| Nota de Professional OS `[SDD] - SDD Modes` | Fuente de descubrimiento no normativa | Contexto inicial externo verificado para identificar problema, oportunidad y tensiones metodologicas; remite los artefactos oficiales al repositorio GitHub | VERIFIED - discovery-only; URI: https://app.notion.com/p/3942fcf6211d80e9a9c8cab594ea0a67; creada: 2026-07-05T18:14:52.857Z; estado Notion: Procesado |
| Documento conceptual consensuado sobre SDD Modes | Fuente de descubrimiento no normativa | Base de consenso previa al Project Brief; sin valor normativo mientras no se verifique URI y version | PENDING - discovery-only; URI y version canonica no verificables desde el repositorio |
| `README.md` | Documentacion general | Describe proposito, estado vigente y limites de `jqf-sdd-foundation` | Verificado en repositorio |
| `.github/instructions/sdd.instructions.md` | Instrucciones SDD | Define fase vigente, restricciones y reglas del SDD Harness | Verificado en repositorio |
| `AGENTS.md` | Catalogo y routing de agentes | Define responsabilidades, limites y flujo de agentes metodologicos | Verificado en repositorio |
| `docs/templates/project_brief.template.md` | Template | Estructura obligatoria utilizada para `docs/project_brief.md` | Verificado en repositorio |
| `docs/templates/context_refs.template.md` | Template | Estructura obligatoria utilizada para este documento | Verificado en repositorio |
| `docs/glosario_terminos.md` | Glosario | Fuente de terminologia SDD y definiciones comunes | Verificado en repositorio |
| `docs/sdd_readiness_assessment.md` | Readiness and closure evidence | Evidencia de readiness, QA y cierre metodologico; no autoriza Development | Verificado en repositorio |

---


## 6.1 Baseline Canonico Vigente

| Artefacto | Estado | Funcion |
| --- | --- | --- |
| `docs/project_brief.md` | Completed | Contexto inicial canonico y declaracion del modo `SDD Full` usado para esta mejora. |
| `specs/spec-001-sdd-modes.md` | Final | Fuente normativa principal de SDD Modes. |
| `specs/spec-001-sdd-modes.architecture.md` | Final | Arquitectura conceptual y documental aprobada. |
| `.github/instructions/sdd.instructions.md` | Current | Reglas operativas vigentes del SDD Harness para modos. |
| `.github/agents/*.agent.md` | Current | Definiciones canonicas de agentes metodologicos. |
| `.codex/agents/` | Current | Adaptadores Codex; no son segunda fuente de verdad. |
| `docs/templates/` y `specs/templates/` | Current | Plantillas vigentes afectadas por SDD Modes. |
| `README.md` | Current | Resumen de alto nivel, no fuente normativa completa. |
| `docs/glosario_terminos.md` | Current | Terminologia aprobada. |
| `docs/tasks.md` | Final | Registro cerrado de tareas y decisiones. |
| `docs/sdd_readiness_assessment.md` | Completed with conditions | Evidencia de cierre metodologico sin Development. |

## 6.2 Fuentes Discovery-Only

| Fuente | Estado | Uso permitido |
| --- | --- | --- |
| Nota de Professional OS `[SDD] - SDD Modes` | VERIFIED - discovery-only | Contexto de origen no normativo; remite los artefactos oficiales al repositorio. |
| Documento conceptual consensuado sobre SDD Modes | PENDING - discovery-only | No normativo hasta verificar URI y version canonica. |

## 6.3 Evidencia Historica

| Evidencia | Estado | Nota |
| --- | --- | --- |
| T-001 a T-027 en `docs/tasks.md` | Closed | Historial de ejecucion y decisiones de la iniciativa. |
| QA Gate Decision T-021 en `docs/sdd_readiness_assessment.md` | Historical gate evidence | Conservada como evidencia de readiness previa al cierre final. |
| Validacion empirica VAL-002/003/004 | Closed with conditions | Candidatos retrospectivos verificados, formalmente `Undeclared`. |

## 6.4 Pendientes Futuros y Punto de Reentrada

| Pendiente | Estado | Reentrada valida |
| --- | --- | --- |
| VAL-001 - repositorio Minimal verificable | PENDING - non-blocking empirical debt | Documentation Agent registra fuente verificable en `docs/context_refs.md`; QA Gate Agent valida si cierra la deuda empirica de Minimal; Specification Agent solo interviene si la evidencia exige cambio normativo. |
| Documento conceptual consensuado | PENDING - discovery-only | Documentation Agent verifica URI/version antes de usarlo como fuente distinta de descubrimiento. |
---

# 7. Fuentes Técnicas Relacionadas

## Repositorios

```yaml
repositorios:
  - nombre: jqf-sdd-foundation
    url: https://github.com/joquifer2/jqf-sdd-foundation.git
    rama: main
    descripcion: Repositorio local verificado en C:\Workspace\JOQUIFER\sdd-foundation con remoto origin y rama actual main.

  - nombre: joquifer_system_agents
    url: https://github.com/joquifer2/joquifer_system_agents.git
    rama: main
    descripcion: Repositorio local verificado en C:\Workspace\JOQUIFER\joquifer_system_agents; estado formal Undeclared por ausencia de SDD Mode declarado; candidato retrospectivo VAL-002 para contrastar SDD Lite por MVP Python manual con BigQuery y controles documentados.

  - nombre: bigquery_mcp_server
    url: https://github.com/joquifer2/bigquery-mcp-server.git
    rama: main
    descripcion: Repositorio local verificado en C:\Workspace\JOQUIFER\bigquery_mcp_server y proyecto Professional OS verificado; estado formal Undeclared por ausencia de SDD Mode declarado; candidato retrospectivo VAL-003 para contrastar SDD Full por producto estable con MCP, BigQuery, seguridad, costes, auditoria e integraciones.

  - nombre: neovaultech-system
    url: https://github.com/joquifer2/neovaultech-system
    rama: main
    descripcion: Repositorio canonico verificado en Professional OS, sin clon local en C:\Workspace\JOQUIFER; estado formal Undeclared por ausencia de SDD Mode declarado verificable; candidato retrospectivo adicional VAL-003 por producto derivado de jqf-sdd-foundation con cliente, decisiones, fuentes externas, gates y Development limitado.

  - nombre: aif-foundation
    url: https://github.com/joquifer2/analytical-intelligence-foundation.git
    rama: main
    descripcion: Repositorio local verificado en C:\Workspace\JOQUIFER\aif-foundation; estado formal Undeclared por ausencia de SDD Mode declarado; candidato retrospectivo VAL-004 para compatibilidad de repositorios SDD existentes anteriores a SDD Modes.
```

## Google Cloud

```yaml
google_cloud:
  proyectos: []

  buckets_gcs: []

  bigquery:
    datasets: []

    tablas: []
```

## Dashboards

```yaml
dashboards: []
```

## APIs / Plataformas Externas

```yaml
apis: []
```

---

# 8. Fuentes Runtime para Agentes IA

> Esta sección indica qué fuentes deben consultar los agentes durante el desarrollo del proyecto.

```yaml
runtime_sources:

  documentos_publicados:
    - nombre: Project Brief - SDD Modes
      tipo: markdown
      uri: docs/project_brief.md
      version: working-tree-2026-07-29
      estado: verified-local

    - nombre: SDD Instructions
      tipo: markdown
      uri: .github/instructions/sdd.instructions.md
      version: working-tree-2026-07-29
      estado: verified-local

    - nombre: AGENTS
      tipo: markdown
      uri: AGENTS.md
      version: working-tree-2026-07-29
      estado: verified-local

    - nombre: README
      tipo: markdown
      uri: README.md
      version: working-tree-2026-07-29
      estado: verified-local

    - nombre: Glosario de terminos SDD
      tipo: markdown
      uri: docs/glosario_terminos.md
      version: working-tree-2026-07-29
      estado: verified-local

    - nombre: Nota de Professional OS [SDD] - SDD Modes
      tipo: external-note
      uri: https://app.notion.com/p/3942fcf6211d80e9a9c8cab594ea0a67
      version: created-2026-07-05T18:14:52.857Z_estado-Procesado
      estado: verified-external-discovery-only

    - nombre: SDD Modes Readiness Assessment
      tipo: markdown
      uri: docs/sdd_readiness_assessment.md
      version: working-tree-2026-07-31
      estado: verified-local

    - nombre: Documento conceptual consensuado sobre SDD Modes
      tipo: external-document
      uri: PENDING
      version: PENDING
      estado: pending-verification-discovery-only

  indices_vectoriales: []

  bases_datos: []
```

---

# 9. Reglas de Carga de Contexto

Antes de crear o modificar cualquier artefacto del proyecto, se deben seguir estas reglas:

1. Consultar el CCD si el trabajo está relacionado con el cliente.
2. Consultar las decisiones relacionadas antes de proponer cambios de alcance, arquitectura, tecnología, metodología o criterios de negocio.
3. Consultar proyectos anteriores si existe relación directa con el alcance actual.
4. Consultar reuniones relacionadas si contienen acuerdos, restricciones o decisiones aplicables.
5. Consultar conocimiento reutilizable antes de crear nuevas plantillas, SOPs, frameworks o prompts.
6. Consultar fuentes técnicas antes de proponer arquitectura, integración, datos, APIs o despliegue.
7. No duplicar el contenido completo del CCD, decisiones o documentación externa dentro del repositorio del proyecto.
8. No depender de memoria informal si existe una fuente publicada y versionada.
9. Si una referencia está pendiente, marcarla como `PENDING`.
10. Si existe conflicto entre fuentes, aplicar la jerarquía definida en este documento.

---

# 10. Jerarquía de Contexto en Caso de Conflicto

Cuando exista conflicto entre fuentes, aplicar este orden:

1. `docs/project_brief.md` como definicion canonica inicial de SDD Modes.
2. Documento conceptual consensuado sobre SDD Modes, solo cuando su ubicacion y version sean verificadas; mientras tanto permanece como discovery-only no normativo.
3. `.github/instructions/sdd.instructions.md`.
4. `AGENTS.md`.
5. `README.md`.
6. `docs/glosario_terminos.md`.
7. Templates oficiales aplicables.
8. Nota de Professional OS `[SDD] - SDD Modes` como fuente de descubrimiento no normativa verificada; no prevalece sobre los artefactos oficiales del repositorio.
9. Proyectos derivados seleccionados como casos de validacion.
10. Notas historicas o no verificadas.

---

# 11. Contexto Pendiente

> Registrar aquí las fuentes que deberían existir o consultarse, pero que todavía no están disponibles.

| Fuente pendiente | Motivo | Impacto | Responsable | Estado |
| --- | --- | --- | --- | --- |
| Nota de Professional OS `[SDD] - SDD Modes` | URI y estado verificados en Notion/Professional OS; creada el 2026-07-05T18:14:52.857Z y estado `Procesado` | Fuente de descubrimiento no normativa; confirma origen y delega artefactos oficiales al repositorio GitHub | Jordi Quiroga | VERIFIED - discovery-only |
| Documento conceptual consensuado sobre SDD Modes | No hay URI, version ni fecha canonica verificable desde el repositorio tras busqueda local | Puede aportar contexto de descubrimiento no normativo para Specification; no condiciona normativamente hasta verificarse | Jordi Quiroga | PENDING - discovery-only |
| Repositorio concreto para VAL-001 - SDD Minimal | No se ha identificado un repositorio verificable que cumpla claramente el perfil bajo riesgo/interno/sin datos sensibles/sin produccion | Bloquea cerrar validacion empirica completa de Minimal sobre repositorio real; no bloquea el cierre metodologico de SDD Modes por decision humana posterior a T-027; debe conservarse como deuda empirica futura | Jordi Quiroga | PENDING - non-blocking empirical debt |

---

# 12. Trazabilidad

```yaml
trazabilidad:
  creado_por: Documentation Agent
  fecha_creacion: 2026-07-29
  ultima_actualizacion: 2026-08-01
  actualizado_por: Documentation Agent
  contexto_validado_por: QA Gate Agent
  fecha_validacion: 2026-08-01
  version_contexto: sdd-modes-final-closure-2026-08-01
```

---

# 13. Instrucción para Agentes IA

Antes de generar o modificar `project_brief.md`, specs, arquitectura, tasks, código o documentación técnica:

1. Leer este archivo.
2. Identificar las fuentes obligatorias.
3. Cargar el CCD si aplica.
4. Revisar decisiones relacionadas.
5. Revisar proyectos relacionados.
6. Revisar reuniones relacionadas.
7. Revisar conocimiento reutilizable.
8. Revisar fuentes técnicas relacionadas.
9. Marcar cualquier ausencia de contexto como `PENDING`.
10. No inventar contexto de cliente, negocio, arquitectura, restricciones o decisiones si no está documentado.
11. Registrar en este archivo cualquier nueva fuente relevante descubierta durante el proyecto.

---