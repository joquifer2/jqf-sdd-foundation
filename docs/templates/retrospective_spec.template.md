# Retrospective Specification Template

## Propósito

Este documento captura la especificación funcional reconstruida de un sistema existente.

Su objetivo es describir qué hace actualmente el sistema y qué reglas de negocio implementa, independientemente de cómo esté implementado técnicamente.

Debe servir como punto de partida para futuras specifications SDD.

No debe describir arquitectura.

No debe describir detalles técnicos de implementación.

No debe incluir propuestas futuras.

No debe incluir rediseños.

Debe describir únicamente el comportamiento observado del sistema actual.

---

# Información General

| Campo | Valor |
|---|---|
| Project Name | |
| Repository | |
| Specification Type | Retrospective |
| Last Updated | |
| Owner | |
| Reviewer | |

---

# Resumen Ejecutivo

Describir brevemente:

- qué hace el sistema;
- qué procesos soporta;
- qué valor aporta;
- qué capacidades principales existen.

---

# Contexto de Negocio

## Problema que resuelve

Describir el problema que el sistema resuelve actualmente.

Responder:

- ¿Qué necesidad cubre?
- ¿Qué proceso soporta?
- ¿Qué actividad automatiza?

---

## Usuarios Principales

| Usuario | Descripción |
|---|---|
| | |

Ejemplos:

- Marketing Manager
- Sales Team
- Operations
- Customer
- Internal User

---

# Capacidades Funcionales

Documentar las capacidades principales observadas.

| Capability ID | Nombre | Descripción |
|---|---|---|
| | | |

Ejemplos:

- Lead Capture
- Lead Qualification
- Reporting
- Conversion Upload
- Forecasting
- Data Synchronization

---

# Procesos Principales

## Proceso

### Nombre

### Objetivo

### Trigger

¿Qué inicia el proceso?

### Flujo

Paso 1

Paso 2

Paso 3

### Resultado esperado

### Evidencia

---

# Reglas de Negocio

Documentar únicamente reglas observadas.

Formato:

| Rule ID | Regla | Evidencia |
|---|---|---|
| | | |

Ejemplos:

- Solo se envían leads cualificados.
- Se excluyen duplicados.
- Solo se sincronizan registros activos.
- Solo se procesan eventos con consentimiento.

---

# Entidades de Negocio

| Entidad | Descripción |
|---|---|
| | |

Ejemplos:

- Lead
- Contact
- Deal
- Sale
- Campaign
- Conversion
- Session

---

# Estados y Ciclos de Vida

Documentar estados relevantes.

## Entidad

### Estados

- Estado 1
- Estado 2
- Estado 3

### Transiciones observadas

Estado 1
↓
Estado 2
↓
Estado 3

---

# Inputs

Documentar entradas funcionales.

| Input | Origen | Propósito |
|---|---|---|
| | | |

---

# Outputs

Documentar salidas funcionales.

| Output | Destino | Propósito |
|---|---|---|
| | | |

---

# Restricciones Observadas

Documentar restricciones conocidas.

| Restricción | Evidencia |
|---|---|---|
| | |

Ejemplos:

- Dependencia de CRM.
- Dependencia de BigQuery.
- Ventanas temporales.
- Requisitos de consentimiento.

---

# Suposiciones Identificadas

Documentar inferencias que no han podido verificarse completamente.

| Suposición | Evidencia disponible |
|---|---|---|
| | |

---

# Riesgos Funcionales

| Riesgo | Severidad | Impacto | Evidencia |
|---|---|---|---|
| | | | |

Severidad:

- Critical
- Important
- Minor

---

# Huecos de Conocimiento

| Área | Información faltante | Impacto |
|---|---|---|---|
| | | |

---

# Artefactos Relacionados

- system_overview.md
- architecture_as_is.md
- data_lineage.md
- contracts.md
- sdd_readiness_assessment.md

---

# Definition of Done

Este documento está completo cuando permite responder:

1. ¿Qué hace actualmente el sistema?
2. ¿Qué procesos soporta?
3. ¿Qué reglas de negocio implementa?
4. ¿Qué entidades maneja?
5. ¿Qué estados existen?
6. ¿Qué inputs recibe?
7. ¿Qué outputs genera?
8. ¿Qué restricciones existen?
9. ¿Qué riesgos funcionales existen?
10. ¿Qué conocimiento sigue faltando?

---

# Notas

Este documento describe el comportamiento actual observado.

No representa una especificación futura.

Las futuras specifications deberán partir de este documento como referencia As-Is.
