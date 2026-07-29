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
  estado: Specification / Structure
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
| PENDING | Documento conceptual consensuado sobre SDD Modes | Base metodologica previa para iniciar el Project Brief y orientar la futura Specification | PENDING - ubicacion y version canonica no verificables desde el repositorio |

## Decisiones pendientes de validar

| Tema | Motivo de la duda | Responsable | Estado |
| --- | --- | --- | --- |
| Ubicacion canonica del documento conceptual consensuado | La referencia existe en el Project Brief, pero el repositorio no contiene URI, version ni fecha verificable | Jordi Quiroga | PENDING |
| Ubicacion canonica de la nota `[SDD] - SDD Modes` en Professional OS | La referencia existe en el Project Brief, pero el repositorio no contiene URI, version ni fecha verificable | Jordi Quiroga | PENDING |

---

# 4. Proyectos Relacionados

> Referenciar proyectos anteriores o activos que puedan afectar al diseño, alcance o implementación de este proyecto.

| Proyecto | Relación con este proyecto | Estado | Fuente |
| --- | --- | --- | --- |
| Proyectos derivados seleccionados | Casos futuros de validacion y compatibilidad para los modos SDD | PENDING | Mencionados en `docs/project_brief.md`; seleccion pendiente |

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
| Nota de Professional OS `[SDD] - SDD Modes` | Fuente de descubrimiento | Contexto inicial externo para identificar problema, oportunidad y tensiones metodologicas | PENDING - ubicacion y version canonica no verificables desde el repositorio |
| Documento conceptual consensuado sobre SDD Modes | Decision metodologica previa | Base de consenso previa al Project Brief | PENDING - ubicacion y version canonica no verificables desde el repositorio |
| `README.md` | Documentacion general | Describe proposito, estado vigente y limites de `jqf-sdd-foundation` | Verificado en repositorio |
| `.github/instructions/sdd.instructions.md` | Instrucciones SDD | Define fase vigente, restricciones y reglas del SDD Harness | Verificado en repositorio |
| `AGENTS.md` | Catalogo y routing de agentes | Define responsabilidades, limites y flujo de agentes metodologicos | Verificado en repositorio |
| `docs/templates/project_brief.template.md` | Template | Estructura obligatoria utilizada para `docs/project_brief.md` | Verificado en repositorio |
| `docs/templates/context_refs.template.md` | Template | Estructura obligatoria utilizada para este documento | Verificado en repositorio |
| `docs/glosario_terminos.md` | Glosario | Fuente de terminologia SDD y definiciones comunes | Verificado en repositorio |

---

# 7. Fuentes Técnicas Relacionadas

## Repositorios

```yaml
repositorios:
  - nombre: jqf-sdd-foundation
    url: https://github.com/joquifer2/jqf-sdd-foundation.git
    rama: main
    descripcion: Repositorio local verificado en C:\Workspace\JOQUIFER\sdd-foundation con remoto origin y rama actual main.
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
      uri: PENDING
      version: PENDING
      estado: pending-verification

    - nombre: Documento conceptual consensuado sobre SDD Modes
      tipo: external-document
      uri: PENDING
      version: PENDING
      estado: pending-verification

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
2. Documento conceptual consensuado sobre SDD Modes, cuando su ubicacion y version sean verificadas.
3. `.github/instructions/sdd.instructions.md`.
4. `AGENTS.md`.
5. `README.md`.
6. `docs/glosario_terminos.md`.
7. Templates oficiales aplicables.
8. Nota de Professional OS `[SDD] - SDD Modes` como fuente de descubrimiento.
9. Proyectos derivados seleccionados como casos de validacion.
10. Notas historicas o no verificadas.

---

# 11. Contexto Pendiente

> Registrar aquí las fuentes que deberían existir o consultarse, pero que todavía no están disponibles.

| Fuente pendiente | Motivo | Impacto | Responsable | Estado |
| --- | --- | --- | --- | --- |
| Nota de Professional OS `[SDD] - SDD Modes` | No hay URI, version ni fecha canonica verificable desde el repositorio | Puede aportar contexto de descubrimiento para Specification | Jordi Quiroga | PENDING |
| Documento conceptual consensuado sobre SDD Modes | No hay URI, version ni fecha canonica verificable desde el repositorio | Puede contener decisiones metodologicas previas que condicionen la Specification | Jordi Quiroga | PENDING |
| Proyectos derivados seleccionados para validacion | El Project Brief los menciona como evidencia futura, pero no los identifica | Afecta a validacion de compatibilidad y escenarios | Jordi Quiroga | PENDING |

---

# 12. Trazabilidad

```yaml
trazabilidad:
  creado_por: Documentation Agent
  fecha_creacion: 2026-07-29
  ultima_actualizacion: 2026-07-29
  actualizado_por: Documentation Agent
  contexto_validado_por: PENDING
  fecha_validacion: PENDING
  version_contexto: initial-context-2026-07-29
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