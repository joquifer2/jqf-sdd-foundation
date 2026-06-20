# Cloud Run Discovery Complement

## Proposito

Este complemento define el proceso para identificar y documentar el uso de Google Cloud Run dentro de un proyecto existente.

Su objetivo es reconstruir el conocimiento minimo necesario sobre servicios, workers, jobs, contenedores, triggers, dependencias, entradas y salidas para permitir evolucion controlada bajo metodologia SDD.

No es una auditoria completa de infraestructura.

No despliega servicios.

No modifica configuracion cloud.

No crea contenedores ni workflows productivos.

## Cuando usar este complemento

Usa este complemento cuando el proyecto contenga evidencia de:

- Cloud Run;
- Dockerfile;
- cloudbuild.yaml;
- service.yaml;
- gcloud run deploy;
- contenedores;
- workers HTTP;
- jobs serverless;
- servicios expuestos por URL;
- APIs internas;
- servicios que leen o escriben en BigQuery;
- servicios que llaman APIs externas.

## Resultado esperado

Al finalizar este complemento debe quedar claro:

- que servicios Cloud Run existen;
- que responsabilidad tiene cada servicio;
- como se despliega o ejecuta;
- que entradas recibe;
- que salidas produce;
- que dependencias utiliza;
- que configuracion operativa es conocida;
- que riesgos existen para evolucionarlo;
- si hace falta documentar contratos o arquitectura.

## Principios

- Priorizar comprension funcional y operativa minima.
- Separar evidencia de inferencia.
- No asumir configuracion cloud no visible.
- No documentar secretos.
- No modificar despliegues.
- No proponer refactors salvo como riesgo.
- No redisenar arquitectura cloud.
- Marcar UNKNOWN cuando falte evidencia.

## Paso 1 - Identificar servicios o jobs Cloud Run

Buscar evidencia como:

- Dockerfile
- cloudbuild.yaml
- service.yaml
- gcloud run deploy
- run.googleapis.com
- Cloud Run
- container image
- PORT
- CMD
- ENTRYPOINT
- app.py
- main.py
- server.js
- package.json
- requirements.txt
- pyproject.toml

Formato recomendado:

| Service / Job | Type | Entrypoint | Evidence |
|---|---|---|---|

Tipos posibles:

- service
- job
- worker
- unknown

## Paso 2 - Identificar responsabilidad

Documentar que hace cada servicio.

Ejemplos:

- exponer API;
- procesar eventos;
- ejecutar worker;
- enviar conversiones;
- cargar BigQuery;
- transformar datos;
- leer tabla y activar API externa;
- recibir webhooks;
- ejecutar scoring.

Formato recomendado:

| Service / Job | Responsibility | Evidence |
|---|---|---|

## Paso 3 - Identificar modo de activacion

Detectar como se invoca el servicio o job:

- HTTP request;
- Cloud Scheduler;
- Pub/Sub;
- webhook externo;
- ejecucion manual;
- GitHub Actions;
- Cloud Tasks;
- Eventarc;
- otro servicio interno;
- UNKNOWN.

Formato recomendado:

| Service / Job | Trigger / Invocation | Source | Evidence |
|---|---|---|---|

## Paso 4 - Identificar entradas

Detectar:

- request HTTP;
- payload JSON;
- query parameters;
- headers;
- variables de entorno;
- tablas BigQuery;
- mensajes Pub/Sub;
- ficheros;
- secrets;
- configuracion.

Formato recomendado:

| Service / Job | Input | Type | Required | Evidence |
|---|---|---|---|---|

## Paso 5 - Identificar salidas

Detectar:

- respuesta HTTP;
- escritura BigQuery;
- llamada API externa;
- envio de eventos;
- actualizacion de estado;
- logs;
- Pub/Sub;
- Cloud Storage;
- archivos generados.

Formato recomendado:

| Service / Job | Output | Destination | Evidence |
|---|---|---|---|

## Paso 6 - Identificar dependencias

Documentar dependencias relevantes:

- BigQuery;
- Secret Manager;
- Cloud Storage;
- Pub/Sub;
- Cloud Scheduler;
- Cloud Tasks;
- APIs externas;
- librerias;
- datasets;
- endpoints;
- imagenes Docker;
- variables de entorno.

Formato recomendado:

| Service / Job | Dependency | Type | Evidence |
|---|---|---|---|

## Paso 7 - Identificar configuracion observable

Buscar evidencia de:

- runtime base image;
- Dockerfile;
- port;
- region;
- memory;
- CPU;
- timeout;
- concurrency;
- min instances;
- max instances;
- retries;
- service account;
- variables de entorno;
- scheduler asociado;
- build trigger;
- container image.

Formato recomendado:

| Service / Job | Config | Value | Evidence |
|---|---|---|---|

Si no existe evidencia: UNKNOWN

## Paso 8 - Identificar contratos

Detectar contratos relevantes:

- payload HTTP esperado;
- estructura webhook;
- schema de tabla BigQuery;
- respuesta esperada por otro servicio;
- payload enviado a API externa;
- formato de logs estructurados;
- codigos de respuesta.

Formato recomendado:

| Service / Job | Contract Candidate | Why It Matters | Evidence |
|---|---|---|---|

Recomendar contracts.md unicamente cuando esos contratos sean relevantes para futuras evoluciones.

## Paso 9 - Identificar riesgos

Detectar riesgos como:

- trigger desconocido;
- endpoint no documentado;
- payload no documentado;
- variables de entorno no documentadas;
- dependencias externas no documentadas;
- ausencia de manejo de errores;
- falta de idempotencia;
- service account desconocida;
- permisos IAM desconocidos;
- despliegue manual no documentado;
- imagen Docker no trazable;
- configuracion de timeout/concurrency desconocida;
- secretos fuera de Secret Manager;
- dependencias hardcoded;
- ausencia de separacion test/produccion.

Clasificar severidad:

severity: critical | important | minor

## Paso 10 - Recomendar artefactos

Recomendar actualizar `architecture_as_is.md` cuando:

- Cloud Run sea parte central del flujo;
- existan varios servicios conectados;
- existan dependencias relevantes con datos, APIs o schedulers.

Recomendar `contracts.md` cuando:

- el servicio exponga o consuma payloads estables;
- dependa de schemas concretos;
- integre sistemas externos.

Recomendar `data_lineage.md` cuando:

- participe en pipelines de datos.

Recomendar `retrospective_spec.md` cuando:

- contenga reglas de negocio relevantes.

## Output recomendado

El resultado de este complemento debe integrarse dentro de Cloud Runtime Discovery.

Formato recomendado:

# Cloud Run Discovery

## Services / Jobs Detected

## Responsibilities

## Triggers / Invocation

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

1. Que servicios o jobs Cloud Run existen?
2. Que hace cada uno?
3. Como se invoca?
4. Que entradas recibe?
5. Que salidas genera?
6. Que dependencias tiene?
7. Que configuracion es conocida?
8. Que contratos existen?
9. Que riesgos afectan a futuras evoluciones?
10. Que artefactos SDD deben actualizarse?

## Comportamiento esperado

Se conservador, preciso y orientado a trazabilidad.

Tu funcion no es mejorar Cloud Run.

Tu funcion es entenderlo lo suficiente para permitir evolucion controlada bajo metodologia SDD.
