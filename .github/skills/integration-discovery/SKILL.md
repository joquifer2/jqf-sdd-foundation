---
name: integration-discovery
description: Esta skill ayuda a identificar integraciones externas, APIs, webhooks, contratos y dependencias de intercambio.
id: SDD-SKILL-004
user-invocable: true
disable-model-invocation: false
---

# Integration Discovery Skill

## Proposito

Esta skill define el proceso para identificar y documentar integraciones existentes dentro de un proyecto SDD.

Su objetivo es reconstruir como el proyecto intercambia datos o eventos con sistemas externos, con suficiente claridad para permitir evolucion controlada bajo metodologia SDD.

No es una auditoria completa de integraciones.

No modifica APIs.

No crea webhooks.

No cambia credenciales.

No implementa conectores.

## Cuando usar esta skill

Usa esta skill cuando el proyecto contenga o pueda contener:

- APIs externas
- webhooks
- CRMs
- plataformas de marketing
- plataformas publicitarias
- sistemas SaaS
- integraciones ETL/ELT
- llamadas HTTP
- payloads JSON
- tokens o credenciales
- eventos enviados a terceros
- datos recibidos desde terceros
- workers de sincronizacion
- procesos de activacion

## Resultado esperado

Al finalizar esta skill debe quedar claro:

- que sistemas externos estan integrados;
- que direccion tiene cada integracion;
- que datos entran;
- que datos salen;
- que eventos se reciben o envian;
- que contratos existen;
- que credenciales o configuracion son necesarias;
- que riesgos afectan a futuras evoluciones;
- si hace falta generar `contracts.md`, `data_lineage.md` o actualizar `architecture_as_is.md`.

## Principios

- Priorizar trazabilidad de integraciones sobre inventario exhaustivo.
- Separar evidencia de inferencia.
- No documentar secretos reales.
- No asumir endpoints no visibles.
- No asumir payloads no documentados.
- No modificar integraciones.
- No crear nuevos conectores.
- No disenar integraciones To-Be.
- Marcar como UNKNOWN todo lo que no pueda verificarse.

## Flujo

### Paso 1 - Detectar sistemas externos

Identificar referencias a:

- Meta
- Google Ads
- LinkedIn Ads
- TikTok Ads
- GA4
- Bitrix
- GoHighLevel
- Systeme.io
- HubSpot
- Shopify
- MongoDB
- ERP
- CRM
- email providers
- analytics platforms
- APIs HTTP genericas
- SaaS externos

### Paso 2 - Clasificar direccion de integracion

Clasificar cada integracion como:

- inbound
- outbound
- bidirectional
- unknown

Ejemplos:

- webhook externo hacia Cloud Function: inbound
- BigQuery hacia Meta CAPI: outbound
- CRM sincronizado con BigQuery: bidirectional o inbound segun evidencia

### Paso 3 - Identificar mecanismo tecnico

Detectar mecanismo usado:

- REST API
- webhook
- SDK
- client library
- connector
- file export
- manual upload
- scheduled job
- Cloud Function
- Cloud Run
- Pub/Sub
- ETL/ELT script
- unknown

### Paso 4 - Identificar datos intercambiados

Documentar:

- tipo de datos;
- sistema origen;
- sistema destino;
- campos principales si aparecen;
- formato;
- frecuencia;
- evidencia.

### Paso 5 - Identificar eventos

Detectar eventos relevantes:

- conversiones
- leads
- contactos
- formularios
- compras
- sesiones
- scoring
- registros
- actualizaciones de estado
- webhooks de creacion o actualizacion

### Paso 6 - Identificar contratos

Detectar contratos de integracion:

- payload recibido;
- payload enviado;
- schema esperado;
- campos obligatorios;
- headers;
- metodo HTTP;
- endpoint;
- codigos de respuesta;
- reglas de validacion;
- deduplicacion;
- idempotencia.

Recomendar `contracts.md` cuando la integracion dependa de una interfaz estable.

### Paso 7 - Identificar autenticacion y configuracion

Documentar solo metadatos no sensibles:

- tipo de autenticacion;
- nombre de variable de entorno;
- secret esperado;
- service account;
- OAuth;
- access token;
- API key;
- pixel id;
- account id;
- endpoint configurado.

No documentar valores secretos reales.

### Paso 8 - Identificar dependencias operativas

Documentar:

- jobs programados;
- workers;
- Cloud Functions;
- Cloud Run;
- BigQuery;
- Pub/Sub;
- schedulers;
- dashboards;
- tablas de estado;
- logs;
- retries.

### Paso 9 - Aplicar complementos especializados

Aplicar cuando proceda:

- `complements/marketing-apis.md`
- `complements/webhooks.md`
- `complements/etl-elt.md`

Los complementos deben usarse solo cuando exista evidencia suficiente o cuando el usuario lo solicite explicitamente.

## Complementos

Esta skill puede apoyarse en:

- `complements/marketing-apis.md` -> identifica integraciones con APIs de marketing, publicidad y activacion.
- `complements/webhooks.md` -> identifica emisores, receptores, eventos, payloads y validaciones de webhooks.
- `complements/etl-elt.md` -> identifica pipelines ETL/ELT, fuentes, destinos, cargas y transformaciones.

## Output recomendado

El resultado de esta skill debe poder integrarse dentro de un assessment mayor.

Formato recomendado:

# Integration Discovery

## External Systems Detected

## Integration Direction

## Technical Mechanism

## Data Exchanged

## Events Detected

## Integration Contracts

## Authentication and Configuration

## Operational Dependencies

## Specialized Complements Applied

## Risks

## Recommended Artifacts

## Open Questions

## Definition of Done

La skill se considera completada cuando existe una respuesta clara a estas preguntas:

1. Que sistemas externos estan integrados?
2. Que direccion tiene cada integracion?
3. Que mecanismo tecnico se utiliza?
4. Que datos se intercambian?
5. Que eventos se reciben o envian?
6. Que contratos existen o deberian documentarse?
7. Que autenticacion o configuracion no sensible es necesaria?
8. Que dependencias operativas existen?
9. Que riesgos condicionan futuras evoluciones?
10. Que artefactos SDD deben crearse o actualizarse?

## Comportamiento esperado

Se conservador, preciso y orientado a trazabilidad.

Tu funcion no es mejorar las integraciones.

Tu funcion es entenderlas lo suficiente para permitir evolucion controlada bajo metodologia SDD.