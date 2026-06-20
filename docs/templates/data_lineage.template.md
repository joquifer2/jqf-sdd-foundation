# Data Lineage Template

## Propósito

Este documento describe el recorrido completo de los datos a través del sistema.

Su objetivo es proporcionar trazabilidad desde el origen hasta el consumo final.

Debe permitir comprender:

- de dónde proceden los datos;
- cómo se transforman;
- dónde se almacenan;
- quién los consume;
- qué dependencias existen;
- qué impacto tendría modificar cualquier componente.

No debe incluir propuestas de rediseño.

No debe incluir optimizaciones.

No debe incluir arquitectura futura.

---

# Información General

| Campo | Valor |
|---|---|
| Project Name | |
| Repository | |
| Last Updated | |
| Owner | |

---

# Resumen Ejecutivo

Describir brevemente:

- qué datos principales se gestionan;
- cuáles son los sistemas origen;
- cuáles son los sistemas destino;
- cuáles son los consumidores principales.

---

# Entidades Principales

| Entidad | Descripción |
|---|---|
| | |

Ejemplos:

- Lead
- Contact
- Deal
- Sale
- Conversion
- Session
- Campaign
- Opportunity

---

# Sistemas Origen

| Sistema | Tipo | Datos Proporcionados | Evidencia |
|---|---|---|---|
| | | | |

Tipos habituales:

- CRM
- ERP
- Ads Platform
- Analytics
- API
- Webhook
- Database
- SaaS
- Unknown

---

# Flujo de Datos de Alto Nivel

Representar el flujo principal.

Ejemplo:

Google Ads
↓
Cloud Function
↓
BigQuery Raw
↓
dbt
↓
BigQuery Marts
↓
Looker Studio

---

# Etapas del Lineage

## Etapa 1

### Nombre

### Tipo

- Source
- Ingestion
- Staging
- Transformation
- Aggregation
- Activation
- Consumption

### Descripción

### Input

### Output

### Evidencia

---

# Transformaciones

| Componente | Tipo | Transformación | Evidencia |
|---|---|---|---|
| | | | |

Tipos:

- SQL
- dbt
- Python
- Stored Procedure
- API
- Manual
- Unknown

---

# Almacenamiento

| Componente | Tipo | Propósito | Evidencia |
|---|---|---|---|
| | | | |

Tipos:

- BigQuery Dataset
- BigQuery Table
- Database
- Data Warehouse
- Data Lake
- Unknown

---

# Activaciones

Documentar sistemas que consumen datos para ejecutar acciones.

| Consumer | Acción | Evidencia |
|---|---|---|
| | | |

Ejemplos:

- Meta CAPI
- Google Ads Offline Conversions
- CRM Sync
- Email Automation
- Lead Scoring

---

# Consumidores Finales

| Consumer | Tipo | Propósito | Evidencia |
|---|---|---|---|
| | | | |

Tipos:

- Dashboard
- API
- CRM
- Marketing Platform
- User Application
- Internal Tool
- Unknown

---

# Contratos Relevantes

| Contrato | Producer | Consumer | Estado |
|---|---|---|---|
| | | | |

Estado:

- Documented
- Inferred
- Missing
- Unknown

---

# Dependencias Críticas

| Dependencia | Impacto | Evidencia |
|---|---|---|---|
| | | |

---

# Riesgos de Trazabilidad

| Riesgo | Severidad | Impacto | Evidencia |
|---|---|---|---|
| | | | |

Severidad:

- Critical
- Important
- Minor

---

# Unknowns

| Unknown | Impacto | Validación requerida |
|---|---|---|
| | | |

---

# Artefactos Relacionados

- system_overview.md
- architecture_as_is.md
- contracts.md
- retrospective_spec.md
- sdd_readiness_assessment.md

---

# Definition of Done

Este documento está completo cuando permite responder:

1. ¿Cuáles son los sistemas origen?
2. ¿Qué entidades fluyen por el sistema?
3. ¿Cómo se transforman los datos?
4. ¿Dónde se almacenan?
5. ¿Qué sistemas consumen los datos?
6. ¿Qué activaciones existen?
7. ¿Qué dependencias son críticas?
8. ¿Qué riesgos afectan a la trazabilidad?
9. ¿Qué información sigue siendo desconocida?

---

# Notas

Este documento debe centrarse en la trazabilidad del dato.

Los detalles de infraestructura deben residir en architecture_as_is.md.
