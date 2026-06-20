# Cloud Functions Discovery Complement

## Proposito

Este complemento define el proceso para identificar y documentar el uso de Google Cloud Functions dentro de un proyecto existente.

Su objetivo es reconstruir el conocimiento minimo necesario sobre funciones desplegadas, triggers, dependencias, entradas, salidas y responsabilidades para permitir evolucion controlada bajo metodologia SDD.

No es una auditoria completa de infraestructura.

No modifica funciones.

No despliega nuevas funciones.

No cambia configuraciones cloud.

## Cuando usar este complemento

Usa este complemento cuando el proyecto contenga evidencia de:

- Cloud Functions;
- functions-framework;
- main.py;
- requirements.txt;
- pyproject.toml;
- entrypoints;
- Cloud Scheduler;
- Pub/Sub;
- HTTP endpoints;
- despliegues mediante gcloud functions deploy;
- workers serverless;
- integraciones basadas en eventos.

## Resultado esperado

Al finalizar este complemento debe quedar claro:

- que Cloud Functions existen;
- cual es la responsabilidad de cada funcion;
- que activa cada funcion;
- que entradas consume;
- que salidas genera;
- que dependencias utiliza;
- que servicios externos utiliza;
- que riesgos existen para evolucionarlas;
- si es necesario documentar contratos o arquitectura.

## Principios

- Priorizar comprension funcional sobre detalle operativo.
- Separar evidencia de inferencia.
- No asumir triggers no documentados.
- No asumir variables de entorno ocultas.
- No documentar secretos.
- No modificar despliegues.
- No proponer refactors salvo como riesgo.
- Marcar UNKNOWN cuando falte evidencia.

## Paso 1 - Identificar funciones

Buscar evidencia como:

- main.py
- app.py
- functions-framework
- @functions_framework.http
- cloud_event
- gcloud functions deploy
- entry_point
- function_name
- cloudfunctions.googleapis.com

Para cada funcion documentar:

| Function | Entrypoint | Evidence |
|---|---|---|

## Paso 2 - Identificar trigger

Clasificar cada funcion:

- HTTP
- Pub/Sub
- Cloud Event
- Cloud Storage
- Scheduler
- Webhook
- Unknown

Formato:

| Function | Trigger Type | Trigger Source | Evidence |
|---|---|---|---|

## Paso 3 - Identificar responsabilidad

Documentar que hace la funcion.

Ejemplos:

- sincronizar datos;
- cargar BigQuery;
- enviar conversiones;
- procesar formularios;
- ejecutar scoring;
- transformar datos;
- activar APIs externas.

Formato:

| Function | Responsibility | Evidence |
|---|---|---|

## Paso 4 - Identificar entradas

Detectar:

- request body;
- query parameters;
- Pub/Sub payload;
- cloud events;
- tablas BigQuery;
- variables de entorno;
- secrets;
- archivos.

Formato:

| Function | Input | Type | Required | Evidence |
|---|---|---|---|---|

## Paso 5 - Identificar salidas

Detectar:

- escritura BigQuery;
- llamada API;
- respuesta HTTP;
- logs;
- Pub/Sub;
- Cloud Storage;
- actualizacion de estados;
- generacion de archivos.

Formato:

| Function | Output | Destination | Evidence |
|---|---|---|---|

## Paso 6 - Identificar dependencias

Documentar dependencias relevantes:

- BigQuery
- Secret Manager
- Cloud Storage
- Pub/Sub
- APIs externas
- librerias Python
- librerias Node
- datasets
- endpoints

Formato:

| Function | Dependency | Type | Evidence |
|---|---|---|---|

## Paso 7 - Identificar configuracion observable

Buscar evidencia de:

- runtime;
- memory;
- timeout;
- region;
- retries;
- service account;
- variables de entorno;
- scheduler asociado.

Formato:

| Function | Config | Value | Evidence |
|---|---|---|---|

Si no existe evidencia: UNKNOWN

## Paso 8 - Identificar contratos

Detectar contratos relevantes:

- payload HTTP esperado;
- estructura webhook;
- mensaje Pub/Sub;
- schema BigQuery esperado;
- respuesta API requerida.

Formato:

| Function | Contract Candidate | Why It Matters | Evidence |
|---|---|---|---|

Recomendar contracts.md unicamente cuando esos contratos sean relevantes para futuras evoluciones.

## Paso 9 - Identificar riesgos

Detectar riesgos como:

- trigger desconocido;
- payload no documentado;
- variables de entorno no documentadas;
- dependencias externas no documentadas;
- ausencia de validaciones;
- ausencia de manejo de errores;
- falta de idempotencia;
- service account desconocida;
- permisos IAM desconocidos;
- despliegue manual no documentado;
- secretos gestionados fuera de Secret Manager;
- dependencias hardcoded.

Clasificar severidad:

severity: critical | important | minor

## Paso 10 - Recomendar artefactos

Recomendar actualizar `architecture_as_is.md` cuando:

- existan varias funciones conectadas;
- formen parte del flujo principal del sistema;
- tengan dependencias relevantes.

Recomendar `contracts.md` cuando:

- consuman o expongan payloads estables;
- dependan de schemas concretos;
- integren sistemas externos.

Recomendar `data_lineage.md` cuando:

- participen en pipelines de datos.

Recomendar `retrospective_spec.md` cuando:

- contengan reglas de negocio relevantes.

## Output recomendado

El resultado de este complemento debe integrarse dentro de Cloud Runtime Discovery.

Formato recomendado:

# Cloud Functions Discovery

## Functions Detected

## Triggers

## Responsibilities

## Inputs

## Outputs

## Dependencies

## Configuration

## Contract Candidates

## Risks

## Recommended Artifacts

## Open Questions

## Definition of Done

Este complemento esta completo cuando existe una respuesta clara a estas preguntas:

1. Que Cloud Functions existen?
2. Que hace cada una?
3. Que las activa?
4. Que entradas reciben?
5. Que salidas generan?
6. Que dependencias tienen?
7. Que configuracion es conocida?
8. Que contratos existen?
9. Que riesgos afectan a futuras evoluciones?
10. Que artefactos SDD deben actualizarse?

## Comportamiento esperado

Se conservador, preciso y orientado a trazabilidad.

Tu funcion no es mejorar las Cloud Functions.

Tu funcion es entenderlas lo suficiente para permitir evolucion controlada bajo metodologia SDD.
