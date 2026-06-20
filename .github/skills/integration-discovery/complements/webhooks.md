# Webhooks Discovery Complement

## Proposito

Este complemento define el proceso para identificar y documentar el uso de webhooks dentro de un proyecto existente.

Su objetivo es reconstruir el conocimiento minimo necesario sobre eventos recibidos, payloads, endpoints, contratos y dependencias para permitir evolucion controlada bajo metodologia SDD.

No es una auditoria completa de integraciones.

No modifica endpoints.

No crea webhooks.

No cambia payloads.

No implementa nuevas integraciones.

## Cuando usar este complemento

Usa este complemento cuando el proyecto contenga evidencia de:

- webhooks
- HTTP endpoints
- POST requests
- formularios
- eventos CRM
- eventos SaaS
- sistemas de automatizacion
- Cloud Functions HTTP
- Cloud Run HTTP
- Stripe webhooks
- Calendly webhooks
- Systeme.io webhooks
- GoHighLevel webhooks
- HubSpot webhooks
- Meta Lead Ads webhooks
- Bitrix webhooks

## Resultado esperado

Al finalizar este complemento debe quedar claro:

- que webhooks existen;
- que sistemas los envian;
- que endpoints los reciben;
- que eventos se reciben;
- que payloads se esperan;
- que contratos existen;
- que dependencias operativas intervienen;
- que riesgos existen para evolucionar el sistema;
- si es necesario generar contracts.md, data_lineage.md o actualizar architecture_as_is.md.

## Principios

- Priorizar contratos y eventos sobre detalles de infraestructura.
- Separar evidencia de inferencia.
- No documentar secretos.
- No asumir payloads no visibles.
- No asumir eventos no documentados.
- No modificar webhooks.
- No disenar integraciones futuras.
- Marcar UNKNOWN cuando no exista evidencia suficiente.

## Paso 1 - Identificar emisores

Detectar sistemas que envian webhooks.

Ejemplos:

- Meta Lead Ads
- Systeme.io
- GoHighLevel
- Calendly
- Stripe
- HubSpot
- Shopify
- CRM
- ERP
- aplicaciones internas

Formato recomendado:

| Sender | Platform | Evidence |
|----------|----------|----------|

## Paso 2 - Identificar receptores

Detectar componentes que reciben webhooks.

Ejemplos:

- Cloud Function
- Cloud Run
- API Gateway
- Backend propio
- Endpoint REST
- Worker HTTP

Formato recomendado:

| Receiver | Type | Endpoint | Evidence |
|----------|----------|----------|----------|

## Paso 3 - Identificar eventos

Detectar eventos recibidos.

Ejemplos:

- lead.created
- contact.created
- contact.updated
- appointment.created
- payment.succeeded
- form.submitted
- deal.created
- deal.updated
- custom_event

Formato recomendado:

| Event | Sender | Purpose Observed | Evidence |
|----------|----------|----------|----------|

## Paso 4 - Identificar payload

Documentar estructura observable.

Ejemplos:

- event_type
- contact_id
- lead_id
- deal_id
- email
- phone
- amount
- timestamp
- metadata

Formato recomendado:

| Field | Required | Purpose | Evidence |
|----------|----------|----------|----------|

Si no es posible verificar obligatoriedad:

UNKNOWN

## Paso 5 - Identificar validaciones

Detectar:

- webhook secret
- signature validation
- token validation
- IP allowlist
- timestamp validation
- replay protection

Formato recomendado:

| Validation | Purpose | Evidence |
|----------|----------|----------|

## Paso 6 - Identificar procesamiento

Documentar que ocurre tras recibir el webhook.

Ejemplos:

- escritura BigQuery
- actualizacion CRM
- activacion workflow
- llamada API
- scoring
- sincronizacion de datos
- actualizacion de estado

Formato recomendado:

| Event | Processing | Destination | Evidence |
|----------|----------|----------|----------|

## Paso 7 - Identificar dependencias

Documentar:

- BigQuery
- dbt
- Cloud Functions
- Cloud Run
- Scheduler
- Pub/Sub
- CRM
- APIs externas
- tablas de estado
- logs

Formato recomendado:

| Webhook Flow | Dependency | Type | Evidence |
|----------|----------|----------|----------|

## Paso 8 - Identificar contratos

Detectar contratos relevantes:

- estructura payload
- campos obligatorios
- respuesta HTTP esperada
- validacion de firma
- esquema JSON
- comportamiento esperado

Formato recomendado:

| Contract Candidate | Producer | Consumer | Evidence |
|----------|----------|----------|----------|

## Paso 9 - Identificar idempotencia

Detectar mecanismos para evitar duplicados:

- event_id
- webhook_id
- lead_id
- external_id
- unique constraint
- deduplication table
- status tracking

Formato recomendado:

| Mechanism | Purpose | Evidence |
|----------|----------|----------|

## Paso 10 - Identificar riesgos

Detectar riesgos como:

- payload no documentado;
- validacion inexistente;
- endpoint hardcoded;
- ausencia de idempotencia;
- ausencia de logs;
- eventos no trazados;
- dependencia de campos no documentados;
- cambios del proveedor pueden romper el flujo;
- reintentos no documentados;
- errores no persistidos.

Clasificar:

severity: critical | important | minor

## Paso 11 - Recomendar artefactos

Recomendar contracts.md cuando:

- exista un payload estable;
- existan validaciones;
- existan campos obligatorios;
- existan dependencias externas.

Recomendar data_lineage.md cuando:

- el webhook alimente procesos de datos.

Recomendar architecture_as_is.md cuando:

- el webhook sea parte central del sistema.

Recomendar retrospective_spec.md cuando:

- existan reglas de negocio embebidas en el procesamiento.

## Output recomendado

# Webhooks Discovery

## Senders

## Receivers

## Events

## Payload Structure

## Validation

## Processing

## Dependencies

## Contract Candidates

## Idempotency

## Risks

## Recommended Artifacts

## Open Questions

## Definition of Done

Este complemento esta completo cuando existe una respuesta clara a estas preguntas:

1. Que sistemas envian webhooks?
2. Que componentes los reciben?
3. Que eventos se reciben?
4. Que payload se espera?
5. Que validaciones existen?
6. Que procesamiento se ejecuta?
7. Que dependencias operativas existen?
8. Que contratos deben documentarse?
9. Que mecanismos de idempotencia existen?
10. Que riesgos afectan futuras evoluciones?
11. Que artefactos SDD deben actualizarse?

## Comportamiento esperado

Se conservador, preciso y orientado a trazabilidad.

Tu funcion no es mejorar los webhooks.

Tu funcion es entender los flujos actuales lo suficiente para permitir evolucion controlada bajo metodologia SDD.