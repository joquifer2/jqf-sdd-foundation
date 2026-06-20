# Marketing APIs Discovery Skill

## Proposito

Esta skill define el proceso para identificar y documentar integraciones con APIs de marketing, publicidad, analitica o activacion dentro de un proyecto existente.

Su objetivo es reconstruir el conocimiento minimo necesario sobre eventos, payloads, credenciales, endpoints, cuentas, conversiones y dependencias para permitir evolucion controlada bajo metodologia SDD.

No es una auditoria completa de las APIs.

No modifica campanas.

No cambia eventos.

No crea conversiones.

No modifica credenciales.

No implementa llamadas API.

## Cuando usar esta skill

Usa esta skill cuando el proyecto contenga evidencia de integracion con:

- Meta CAPI
- Meta Marketing API
- Google Ads API
- Google Ads Offline Conversions
- Google Analytics 4 Measurement Protocol
- LinkedIn Ads API
- TikTok Ads API
- CRM Ads integrations
- conversion events
- offline conversions
- server-side tracking
- audiences
- lead scoring activation
- BigQuery hacia plataformas publicitarias
- eventos enviados a plataformas de marketing

## Resultado esperado

Al finalizar esta skill debe quedar claro:

- que APIs de marketing aparecen;
- que eventos o recursos se envian o reciben;
- que cuentas, pixeles o conversion actions estan implicados;
- que payloads se construyen;
- que campos obligatorios existen;
- que campos opcionales relevantes existen;
- que reglas de deduplicacion o idempotencia aparecen;
- que datos origen alimentan la integracion;
- que riesgos existen para evolucionarla;
- si hace falta documentar contracts.md, data_lineage.md o architecture_as_is.md.

## Principios

- Priorizar contratos de integracion sobre inventario exhaustivo.
- Separar evidencia de inferencia.
- No documentar secretos reales.
- No asumir eventos no visibles.
- No asumir configuracion de plataforma no documentada.
- No modificar payloads.
- No crear eventos nuevos.
- No proponer cambios de campanas.
- No inferir cumplimiento legal si no esta documentado.
- Marcar como UNKNOWN todo lo que no pueda verificarse.

## Flujo

### Paso 1 - Identificar APIs de marketing

Buscar evidencia de:

- Meta CAPI
- Facebook Graph API
- graph.facebook.com
- pixel_id
- access_token
- event_name
- event_time
- event_id
- user_data
- custom_data
- action_source
- test_event_code
- Google Ads API
- conversion_action_id
- gclid
- gbraid
- wbraid
- offline conversion
- GA4 Measurement Protocol
- api_secret
- measurement_id
- LinkedIn Ads
- TikTok Events API
- OAuth
- API key
- REST endpoint
- requests.post

Formato recomendado:

| API | Provider | Evidence | Confidence |
|---|---|---|---|

## Paso 2 - Identificar direccion de la integracion

Clasificar:

- inbound
- outbound
- bidirectional
- unknown

Ejemplos:

- BigQuery -> Meta CAPI: outbound
- Google Ads API -> BigQuery: inbound
- CRM -> BigQuery -> Ads API: bidirectional o pipeline compuesto

Formato recomendado:

| Integration | Direction | Source | Destination | Evidence |
|---|---|---|---|---|

## Paso 3 - Identificar cuenta, recurso o propiedad

Documentar metadatos no sensibles:

- pixel_id
- dataset_id
- ad_account_id
- conversion_action_id
- customer_id
- measurement_id
- property_id
- account_id
- business_id
- endpoint
- event source

No documentar access tokens, secrets ni API keys reales.

Formato recomendado:

| Provider | Resource Type | Resource Identifier | Evidence |
|---|---|---|---|

Si el identificador es sensible o no debe exponerse, documentar solo el nombre de variable.

## Paso 4 - Identificar eventos o recursos

Detectar eventos o recursos relevantes:

- Lead
- QualifiedLead
- CompleteRegistration
- Purchase
- SubmitApplication
- OfflineConversion
- custom conversion
- audience update
- contact sync
- conversion upload
- measurement event

Formato recomendado:

| Event / Resource | Provider | Purpose Observed | Evidence |
|---|---|---|---|

## Paso 5 - Identificar origen de datos

Detectar que alimenta la integracion:

- BigQuery table
- dbt model
- CRM
- webhook
- lead scoring
- form submission
- GA4
- CSV
- Google Sheets
- database
- Cloud Function
- Cloud Run worker

Formato recomendado:

| Integration | Source Data | Source Object | Evidence |
|---|---|---|---|

## Paso 6 - Identificar payload

Documentar estructura del payload sin secretos.

Campos habituales:

### Meta CAPI

- event_name
- event_time
- event_id
- action_source
- event_source_url
- user_data
- custom_data
- value
- currency
- contents
- content_name
- content_category
- test_event_code

### Google Ads Offline Conversions

- conversion_action
- conversion_date_time
- conversion_value
- currency_code
- gclid
- gbraid
- wbraid
- order_id
- user_identifiers

### GA4 Measurement Protocol

- client_id
- user_id
- events
- params
- timestamp_micros
- engagement_time_msec

Formato recomendado:

| Field | Required | Source | Transformation | Evidence |
|---|---|---|---|---|

Si no esta claro si un campo es obligatorio, marcar UNKNOWN.

## Paso 7 - Identificar hashing, normalizacion y privacidad

Detectar si existen:

- hashing SHA256
- normalizacion de email
- normalizacion de phone
- user identifiers
- consent flags
- IP address
- user agent
- fbp
- fbc
- click identifiers
- enhanced conversions
- consentimiento documentado
- server-side tracking

Formato recomendado:

| Data Element | Processing | Purpose | Evidence |
|---|---|---|---|

No asumir cumplimiento legal si no hay documentacion.

## Paso 8 - Identificar deduplicacion e idempotencia

Buscar evidencia de:

- event_id
- order_id
- conversion_id
- external_id
- lead_id
- unique keys
- estado de enviado
- tabla de logs
- retry control
- sent_at
- response_id
- status column
- idempotency key

Formato recomendado:

| Mechanism | Field / Object | Purpose | Evidence |
|---|---|---|---|

## Paso 9 - Identificar respuestas y errores

Detectar gestion de:

- HTTP status codes
- API response body
- error messages
- retries
- logging
- failed events
- rejected events
- partial success
- rate limits
- validation errors
- test mode

Formato recomendado:

| Response / Error Handling | Behavior Observed | Evidence |
|---|---|---|

## Paso 10 - Identificar dependencias operativas

Documentar:

- Cloud Function
- Cloud Run
- Scheduler
- Pub/Sub
- BigQuery
- dbt
- Secret Manager
- environment variables
- logs
- tables for status tracking
- dashboards
- Events Manager
- Ads UI
- conversion settings

Formato recomendado:

| Integration | Dependency | Type | Evidence |
|---|---|---|---|

## Paso 11 - Identificar contratos

Detectar contratos relevantes:

- tabla BigQuery -> payload API
- dbt model -> worker
- worker -> API externa
- API response -> status table
- event_name esperado por plataforma
- conversion action esperada por Google Ads
- schema de user_data
- schema de custom_data

Formato recomendado:

| Contract Candidate | Producer | Consumer | Why It Matters | Evidence |
|---|---|---|---|---|

Recomendar contracts.md cuando la integracion dependa de estructuras estables.

## Paso 12 - Identificar riesgos

Detectar riesgos como:

- payload no documentado;
- campos obligatorios desconocidos;
- event_id ausente o inconsistente;
- deduplicacion no documentada;
- hashing no documentado;
- consentimiento no documentado;
- token no trazado;
- endpoint hardcoded;
- rate limits desconocidos;
- errores no persistidos;
- no hay tabla de estado;
- no hay reintentos;
- no hay idempotencia;
- evento aparece en plataforma pero no en reporting;
- custom conversion depende de parametros no enviados;
- cambio de schema rompe activacion;
- cambios en tabla origen afectan API;
- dependencia de configuracion manual en plataforma externa.

Clasificar:

severity: critical | important | minor

Formato:

### Risk

#### Severity

#### Description

#### Evidence

#### Impact

## Paso 13 - Recomendar artefactos

Recomendar contracts.md cuando:

- exista payload estable;
- BigQuery o dbt alimenten una API;
- una plataforma externa dependa de campos concretos;
- existan conversion events;
- existan custom conversions;
- existan reglas de deduplicacion.

Recomendar data_lineage.md cuando:

- la integracion forme parte de un flujo de datos;
- los datos viajen desde CRM, BigQuery o dbt hacia una API;
- el origen de eventos sea relevante para reporting o activacion.

Recomendar architecture_as_is.md cuando:

- la integracion sea componente central del sistema;
- existan workers, schedulers, tablas y APIs conectadas.

Recomendar retrospective_spec.md cuando:

- existan reglas de negocio como scoring, cualificacion, seleccion de eventos o reglas de envio.

## Complementos

Esta skill puede apoyarse en complementos especificos:

- .github/skills/marketing-apis-discovery/complements/meta-capi.md
- .github/skills/marketing-apis-discovery/complements/google-ads.md
- .github/skills/marketing-apis-discovery/complements/ga4-measurement.md

## Output recomendado

El resultado de esta skill debe poder integrarse dentro de un assessment mayor.

Formato recomendado:

# Marketing APIs Discovery

## APIs Detected

## Integration Direction

## Accounts / Resources

## Events or Resources

## Source Data

## Payload Structure

## Hashing and Privacy Processing

## Deduplication and Idempotency

## Responses and Error Handling

## Operational Dependencies

## Contract Candidates

## Risks

## Recommended Artifacts

## Open Questions

## Definition of Done

Esta skill esta completa cuando existe una respuesta clara a estas preguntas:

1. Que APIs de marketing aparecen?
2. Que eventos o recursos se envian o reciben?
3. Que datos origen alimentan la integracion?
4. Que payload se construye?
5. Que campos son criticos?
6. Que mecanismos de hashing, privacidad, deduplicacion o idempotencia existen?
7. Como se gestionan respuestas y errores?
8. Que dependencias operativas existen?
9. Que contratos deben documentarse?
10. Que riesgos condicionan futuras evoluciones?
11. Que artefactos SDD deben actualizarse?

## Comportamiento esperado

Se conservador, preciso y orientado a trazabilidad.

Tu funcion no es mejorar las APIs de marketing.

Tu funcion es entender las integraciones actuales lo suficiente para permitir evolucion controlada bajo metodologia SDD.