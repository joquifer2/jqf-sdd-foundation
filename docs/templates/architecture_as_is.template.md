# Architecture As-Is Template

## Propósito

Este documento describe la arquitectura actual del sistema.

Su objetivo es reconstruir cómo está montado el sistema hoy, sin diseñar una arquitectura futura.

Debe servir como base para entender impactos, dependencias y riesgos antes de evolucionar el proyecto bajo metodología SDD.

No debe incluir propuestas To-Be.

No debe incluir rediseños.

No debe incluir tareas de implementación.

---

# Información General

| Campo | Valor |
|---|---|
| Project Name | |
| Repository | |
| Architecture Type | As-Is |
| Project Type | Greenfield / Brownfield / Legacy |
| Last Updated | |
| Owner | |
| Reviewer | |

---

# Resumen Arquitectónico

Describir en pocas líneas cómo está compuesto el sistema actualmente.

Responder:

- ¿Qué componentes principales existen?
- ¿Cómo se comunican?
- ¿Qué sistemas externos intervienen?
- ¿Qué parte es crítica para el funcionamiento?

---

# Diagrama Textual

Representar el flujo principal del sistema en texto.

Ejemplo:

Origen de datos
↓
Ingesta
↓
Procesamiento
↓
Almacenamiento
↓
Consumo

---

# Componentes Runtime

| Componente | Tipo | Responsabilidad | Evidencia |
|---|---|---|---|
| | | | |

Tipos posibles:

- Cloud Function
- Cloud Run
- Worker
- API
- Script
- Scheduler
- Pub/Sub
- Application
- Unknown

---

# Componentes de Datos

| Componente | Tipo | Responsabilidad | Evidencia |
|---|---|---|---|
| | | | |

Tipos posibles:

- BigQuery Dataset
- BigQuery Table
- dbt Model
- Stored Procedure
- Scheduled Query
- Dashboard
- Data Export
- Unknown

---

# Integraciones Externas

| Sistema | Dirección | Propósito | Evidencia |
|---|---|---|---|
| | | | |

Dirección:

- Inbound
- Outbound
- Bidirectional
- Unknown

---

# Dependencias Operativas

| Dependencia | Usada por | Criticidad | Evidencia |
|---|---|---|---|
| | | | |

Criticidad:

- Critical
- Important
- Minor

---

# Flujos Principales

## Flujo 1

Nombre:

Descripción:

Pasos:

1. 
2. 
3. 

Evidencia:

---

# Contratos Relevantes

Listar contratos existentes o candidatos.

| Contrato | Producer | Consumer | Estado |
|---|---|---|---|
| | | | |

Estado:

- Documented
- Inferred
- Missing
- Unknown

---

# Seguridad y Configuración

Documentar únicamente información no sensible.

| Elemento | Descripción | Estado |
|---|---|---|
| Variables de entorno | | Known / Partial / Unknown |
| Secrets | | Known / Partial / Unknown |
| Service Accounts | | Known / Partial / Unknown |
| Permisos | | Known / Partial / Unknown |

No incluir valores secretos reales.

---

# Observabilidad

| Elemento | Estado | Evidencia |
|---|---|---|
| Logs | Known / Partial / Unknown | |
| Monitoring | Known / Partial / Unknown | |
| Alerts | Known / Partial / Unknown | |
| Error Tracking | Known / Partial / Unknown | |

---

# Riesgos Arquitectónicos

| Riesgo | Severidad | Impacto | Evidencia |
|---|---|---|---|
| | | | |

Severidad:

- Critical
- Important
- Minor

---

# Unknowns

Listar información no verificada.

| Unknown | Impacto | Validación requerida |
|---|---|---|
| | | |

---

# Artefactos Relacionados

- system_overview.md
- retrospective_spec.md
- contracts.md
- data_lineage.md
- sdd_readiness_assessment.md

---

# Definition of Done

Este documento está completo cuando permite responder:

1. ¿Qué componentes principales existen?
2. ¿Cómo se comunican?
3. ¿Qué sistemas externos intervienen?
4. ¿Qué dependencias son críticas?
5. ¿Qué flujos principales existen?
6. ¿Qué contratos relevantes existen o faltan?
7. ¿Qué riesgos arquitectónicos condicionan la evolución?
8. ¿Qué información sigue siendo desconocida?

---

# Notas

Este documento describe el estado actual.

Cualquier propuesta futura debe documentarse en una specification o architecture To-Be separada.
