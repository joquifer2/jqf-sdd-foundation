# Context References

# Referencias de Contexto del Proyecto

> Este documento define las fuentes de contexto oficiales que deben consultarse antes de generar o modificar cualquier Project Brief, Spec, documento de Arquitectura, Tasks, código o documentación técnica de este proyecto.
> 
> 
> No debe duplicar el contenido completo del CCD, decisiones, reuniones, proyectos anteriores o documentación externa.
> 
> Su función es actuar como índice de referencias y trazabilidad del contexto utilizado.
> 

---

# 1. Identidad del Proyecto

```yaml
proyecto:
  nombre:
  id_proyecto:
  tipo_proyecto:
  estado:
  fecha_creacion:
  responsable:

cliente:
  id_cliente:
  nombre_cliente:
  estado_relacion:
```

---

# 2. Contexto de Cliente Requerido

## CCD — Client Context Document

```yaml
ccd:
  requerido: true

  fuente_humana:
    sistema: Notion
    ubicacion:

  fuente_runtime_ia:
    sistema:
    uri:

  version:
  estado:
  ultima_revision:
  fecha_consulta:
```

## Notas sobre el uso del CCD

Indicar aquí cualquier consideración específica sobre el contexto del cliente que deba tenerse en cuenta en este proyecto.

Ejemplos:

- Respetar las definiciones oficiales de negocio.
- Respetar los KPIs oficiales.
- Revisar restricciones conocidas.
- Revisar el mental model del cliente.
- Revisar el ecosistema tecnológico actual del cliente.
- No asumir información de cliente no documentada.

---

# 3. Decisiones Relacionadas

> La fuente oficial de decisiones es la base `Decisiones` del SO Profesional.
> 
> 
> Esta sección solo referencia decisiones relevantes para este proyecto.
> 

| Fecha | Decisión | Impacto en este proyecto | Fuente |
| --- | --- | --- | --- |
|  |  |  |  |

## Decisiones pendientes de validar

| Tema | Motivo de la duda | Responsable | Estado |
| --- | --- | --- | --- |
|  |  |  |  |

---

# 4. Proyectos Relacionados

> Referenciar proyectos anteriores o activos que puedan afectar al diseño, alcance o implementación de este proyecto.
> 

| Proyecto | Relación con este proyecto | Estado | Fuente |
| --- | --- | --- | --- |
|  |  |  |  |

---

# 5. Reuniones Relacionadas

> Referenciar reuniones relevantes que contengan acuerdos, contexto, decisiones o restricciones aplicables.
> 

| Fecha | Reunión | Información relevante | Fuente |
| --- | --- | --- | --- |
|  |  |  |  |

---

# 6. Conocimiento Reutilizable Relacionado

> Referenciar plantillas, SOPs, frameworks, prompts, documentación técnica o investigaciones que deban consultarse.
> 

| Recurso | Tipo | Motivo de uso | Fuente |
| --- | --- | --- | --- |
|  |  |  |  |

---

# 7. Fuentes Técnicas Relacionadas

## Repositorios

```yaml
repositorios:
  - nombre:
    url:
    rama:
    descripcion:
```

## Google Cloud

```yaml
google_cloud:
  proyectos:
    - project_id:
      descripcion:

  buckets_gcs:
    - uri:
      descripcion:

  bigquery:
    datasets:
      - project_id:
        dataset:
        descripcion:

    tablas:
      - project_id:
        dataset:
        tabla:
        descripcion:
```

## Dashboards

```yaml
dashboards:
  - nombre:
    herramienta:
    url:
    descripcion:
```

## APIs / Plataformas Externas

```yaml
apis:
  - nombre:
    documentacion:
    uso_en_proyecto:
```

---

# 8. Fuentes Runtime para Agentes IA

> Esta sección indica qué fuentes deben consultar los agentes durante el desarrollo del proyecto.
> 

```yaml
runtime_sources:

  documentos_publicados:
    - nombre:
      tipo:
      uri:
      version:
      estado:

  indices_vectoriales:
    - nombre:
      proveedor:
      indice:
      filtros_requeridos:
        client_id:
        project_id:
        document_type:

  bases_datos:
    - nombre:
      tipo:
      uri:
      uso:
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

1. Decisiones recientes documentadas.
2. CCD activo del cliente.
3. Documentación SDD vigente.
4. Specs del proyecto activo.
5. Project Brief del proyecto activo.
6. Proyectos anteriores.
7. Reuniones históricas.
8. Notas históricas o no verificadas.

---

# 11. Contexto Pendiente

> Registrar aquí las fuentes que deberían existir o consultarse, pero que todavía no están disponibles.
> 

| Fuente pendiente | Motivo | Impacto | Responsable | Estado |
| --- | --- | --- | --- | --- |
|  |  |  |  |  |

---

# 12. Trazabilidad

```yaml
trazabilidad:
  creado_por:
  fecha_creacion:
  ultima_actualizacion:
  actualizado_por:
  contexto_validado_por:
  fecha_validacion:
  version_contexto:
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

