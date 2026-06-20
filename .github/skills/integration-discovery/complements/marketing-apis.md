# Marketing APIs Discovery Complement

## Proposito

Este complemento define el proceso para identificar y documentar integraciones con APIs de marketing, publicidad, analitica o activacion dentro de un proyecto existente.

Su objetivo es reconstruir el conocimiento minimo necesario sobre eventos, payloads, credenciales, endpoints, cuentas, conversiones y dependencias para permitir evolucion controlada bajo metodologia SDD.

No es una auditoria completa de las APIs.

No modifica campanas.

No cambia eventos.

No crea conversiones.

No modifica credenciales.

No implementa llamadas API.

## Cuando usar este complemento

Usa este complemento cuando el proyecto contenga evidencia de integracion con:

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

Al finalizar este complemento debe quedar claro:

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

### Paso 2 - Identificar direccion de la integracion

Clasificar:

- inbound
- outbound
- bidirectional
- unknown

### Paso 3 - Identificar cuenta, recurso o propiedad

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

### Paso 4 - Identificar eventos o recursos

Detectar eventos o recursos relevantes y su evidencia.

### Paso 5 - Identificar origen de datos

Detectar que alimenta la integracion.

### Paso 6 - Identificar payload

Documentar estructura del payload sin secretos.

### Paso 7 - Identificar hashing, normalizacion y privacidad

Detectar hashing, normalizacion e indicadores de privacidad.

### Paso 8 - Identificar deduplicacion e idempotencia

Detectar mecanismos como event_id, order_id, tablas de estado o claves de idempotencia.

### Paso 9 - Identificar respuestas y errores

Detectar manejo de estados HTTP, reintentos y persistencia de errores.

### Paso 10 - Identificar dependencias operativas

Documentar dependencias como Cloud Functions, Cloud Run, Scheduler, Pub/Sub, BigQuery, dbt, Secret Manager y tablas de seguimiento.

### Paso 11 - Identificar contratos

Detectar contratos relevantes entre productor y consumidor.

Recomendar contracts.md cuando la integracion dependa de estructuras estables.

### Paso 12 - Identificar riesgos

Clasificar riesgos como `critical`, `important` o `minor`.

### Paso 13 - Recomendar artefactos

Recomendar:

- contracts.md
- data_lineage.md
- architecture_as_is.md
- retrospective_spec.md

solo cuando aporten trazabilidad real para evolucion segura.

## Output recomendado

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

Este complemento esta completo cuando existe una respuesta clara a estas preguntas:

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