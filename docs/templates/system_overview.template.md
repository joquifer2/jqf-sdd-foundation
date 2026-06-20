# System Overview Template

## Propósito

Este documento proporciona una visión ejecutiva y técnica de alto nivel del sistema actual.

Su objetivo es permitir que cualquier persona comprenda rápidamente:

- qué es el sistema;
- qué problema resuelve;
- cuáles son sus componentes principales;
- qué sistemas externos participan;
- qué datos gestiona;
- qué dependencias existen;
- qué artefactos deben consultarse para profundizar.

No pretende sustituir la arquitectura detallada.

No pretende documentar implementaciones internas.

No pretende describir todos los flujos técnicos.

Para ello existen otros artefactos especializados.

---

# Información General

| Campo | Valor |
|---------|---------|
| Project Name | |
| Repository | |
| Repository Type | Greenfield / Brownfield / Legacy |
| Current Status | Discovery / Active Development / Maintenance / Unknown |
| Last Updated | |
| Owner | |
| Technical Owner | |
| Business Owner | |

---

# Executive Summary

## Qué es el sistema

Descripción breve del sistema.

Responder:

- ¿Qué es?
- ¿Para quién existe?
- ¿Cuál es su propósito principal?

---

## Problema que resuelve

Describir el problema principal que el sistema intenta resolver.

Responder:

- ¿Qué necesidad cubre?
- ¿Qué proceso automatiza?
- ¿Qué limitación elimina?

---

## Objetivo principal

Describir el objetivo principal del sistema.

Responder:

- ¿Qué resultado genera?
- ¿Qué valor aporta al negocio?

---

# Alcance

## Incluido

Listar capacidades principales.

Ejemplos:

- Captación de leads.
- Integración de datos.
- Reporting automatizado.
- Activación publicitaria.
- Scoring.
- Forecasting.

---

## No incluido

Listar explícitamente lo que queda fuera del sistema.

Ejemplos:

- Facturación.
- ERP.
- Atención al cliente.
- Procesamiento de pagos.

---

# Componentes Principales

Documentar únicamente los componentes de alto nivel.

| Componente | Tipo | Propósito |
|------------|------|------------|
| | | |

Tipos habituales:

- Application
- API
- Cloud Function
- Cloud Run
- BigQuery
- dbt
- Dashboard
- CRM
- SaaS
- Worker
- Unknown

---

# Sistemas Externos

Documentar sistemas externos relevantes.

| Sistema | Tipo | Dirección |
|----------|----------|----------|
| | | |

Dirección:

- Inbound
- Outbound
- Bidirectional
- Unknown

---

# Datos Principales

Documentar las entidades principales gestionadas por el sistema.

| Entidad | Descripción |
|----------|----------|
| | |

Ejemplos:

- Lead
- Contact
- Deal
- Sale
- Conversion
- Event
- Campaign
- Session
- Opportunity

---

# Flujo de Alto Nivel

Describir el flujo principal del sistema.

Formato recomendado:

Origen
↓
Procesamiento
↓
Almacenamiento
↓
Consumo

Ejemplo:

Google Ads
Meta Ads
CRM
↓
Cloud Functions
↓
BigQuery
↓
dbt
↓
Looker Studio

---

# Arquitectura General

Resumen textual de la arquitectura actual.

No incluir detalles de implementación.

Si existe:

Consultar:

- architecture_as_is.md

---

# Integraciones Relevantes

Listar integraciones críticas.

| Integración | Propósito |
|-------------|-------------|
| | |

---

# Dependencias Críticas

Documentar dependencias necesarias para que el sistema funcione.

Ejemplos:

- BigQuery
- dbt
- Cloud Functions
- Cloud Run
- Scheduler
- Pub/Sub
- CRM
- APIs externas

| Dependencia | Criticidad |
|-------------|-------------|
| | |

Criticidad:

- Critical
- Important
- Minor

---

# Riesgos Conocidos

Documentar únicamente riesgos de alto nivel.

| Riesgo | Impacto |
|---------|---------|
| | |

---

# Artefactos Relacionados

## Arquitectura

- architecture_as_is.md

## Contratos

- contracts.md

## Trazabilidad

- data_lineage.md

## Especificación retrospectiva

- retrospective_spec.md

## Readiness

- sdd_readiness_assessment.md

---

# Estado de Conocimiento

Evaluar nivel de conocimiento actual.

| Área | Estado |
|--------|--------|
| Funcional | Complete / Partial / Unknown |
| Arquitectura | Complete / Partial / Unknown |
| Datos | Complete / Partial / Unknown |
| Integraciones | Complete / Partial / Unknown |
| Infraestructura | Complete / Partial / Unknown |

---

# Preguntas Abiertas

Documentar dudas pendientes.

- ...
- ...
- ...

---

# Definition of Done

Este documento está completo cuando permite responder:

1. ¿Qué es el sistema?
2. ¿Qué problema resuelve?
3. ¿Qué valor aporta?
4. ¿Cuáles son sus componentes principales?
5. ¿Qué sistemas externos participan?
6. ¿Qué datos gestiona?
7. ¿Cuál es el flujo principal?
8. ¿Qué dependencias son críticas?
9. ¿Qué riesgos principales existen?
10. ¿Qué otros artefactos deben consultarse?

---

# Notas

Este documento debe mantenerse deliberadamente corto.

Su propósito es proporcionar contexto rápido.

Los detalles deben residir en artefactos especializados.
