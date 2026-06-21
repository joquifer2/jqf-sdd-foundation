---
name: cloud-runtime-discovery
description: Esta skill ayuda a identificar runtimes cloud, triggers, entradas, salidas y dependencias operativas.
id: SDD-SKILL-003
user-invocable: true
disable-model-invocation: false
---
# Cloud Runtime Discovery Skill

## Proposito

Esta skill define el proceso para identificar y documentar runtimes cloud existentes dentro de un proyecto SDD.

Su objetivo es reconstruir como se ejecutan procesos, servicios, workers o funciones desplegadas en cloud, con suficiente claridad para permitir evolucion controlada bajo metodologia SDD.

No es una auditoria completa de infraestructura.

No despliega servicios.

No modifica configuracion cloud.

No crea workflows productivos.

## Cuando usar esta skill

Usa esta skill cuando el proyecto contenga o pueda contener:

- Cloud Functions
- Cloud Run
- workers
- servicios serverless
- jobs programados
- Cloud Scheduler
- Pub/Sub
- Cloud Build
- Dockerfile
- scripts de deploy
- variables de entorno
- secrets
- runtimes Python, Node.js u otros
- servicios que leen o escriben en BigQuery
- servicios que llaman APIs externas

## Resultado esperado

Al finalizar esta skill debe quedar claro:

- que runtimes cloud existen;
- que componente se ejecuta donde;
- que triggers activan cada proceso;
- que entradas recibe cada runtime;
- que salidas produce;
- que dependencias externas tiene;
- que riesgos existen para evolucionarlo;
- si hace falta actualizar `architecture_as_is.md`, `contracts.md` o `sdd_readiness_assessment.md`.

## Principios

- Priorizar comprension operativa sobre inventario exhaustivo.
- Separar evidencia de inferencia.
- No asumir triggers si no hay evidencia.
- No asumir variables de entorno no visibles.
- No documentar secretos reales.
- No modificar despliegues.
- No crear nuevos servicios.
- No redisenar arquitectura cloud.
- Marcar como UNKNOWN lo que no pueda verificarse.

## Flujo

### Paso 1 - Detectar runtimes cloud

Buscar evidencia de:

- Cloud Functions
- Cloud Run
- Dockerfile
- cloudbuild.yaml
- functions-framework
- app.py
- main.py
- package.json
- requirements.txt
- pyproject.toml
- deploy.sh
- gcloud functions deploy
- gcloud run deploy
- Cloud Scheduler
- Pub/Sub
- HTTP trigger
- event trigger

### Paso 2 - Identificar componentes ejecutables

Para cada componente ejecutable, documentar:

- nombre;
- tipo;
- runtime;
- entrypoint;
- path;
- proposito observado;
- evidencia.

Formato recomendado:

| Component | Type | Runtime | Entrypoint | Purpose | Evidence |
|---|---|---|---|---|---|

### Paso 3 - Identificar triggers

Detectar como se activa cada componente:

- HTTP request
- Pub/Sub
- Cloud Scheduler
- webhook externo
- evento cloud
- ejecucion manual
- GitHub Actions
- cron
- UNKNOWN

Formato recomendado:

| Component | Trigger | Source | Frequency | Evidence |
|---|---|---|---|---|

### Paso 4 - Identificar entradas

Detectar que recibe cada runtime:

- request HTTP;
- payload JSON;
- Pub/Sub message;
- parametros de query;
- body de webhook;
- variables de entorno;
- tablas BigQuery;
- ficheros;
- secrets;
- configuracion.

Formato recomendado:

| Component | Input | Type | Required | Evidence |
|---|---|---|---|---|

### Paso 5 - Identificar salidas

Detectar que produce cada runtime:

- escritura en BigQuery;
- llamada a API externa;
- respuesta HTTP;
- log;
- actualizacion de estado;
- envio de evento;
- fichero;
- mensaje Pub/Sub;
- email;
- dashboard update.

Formato recomendado:

| Component | Output | Destination | Purpose | Evidence |
|---|---|---|---|---|

### Paso 6 - Identificar dependencias

Documentar dependencias relevantes:

- librerias;
- APIs externas;
- BigQuery;
- Pub/Sub;
- Cloud Scheduler;
- Secret Manager;
- service accounts;
- variables de entorno;
- datasets;
- endpoints;
- servicios internos.

Formato recomendado:

| Component | Dependency | Type | Purpose | Evidence |
|---|---|---|---|---|

### Paso 7 - Identificar configuracion operativa

Detectar configuracion observable:

- runtime version;
- region;
- memory;
- timeout;
- concurrency;
- retries;
- scheduler frequency;
- environment variables;
- service account;
- Docker image;
- build config.

No inventar valores si no aparecen.

Marcar como UNKNOWN cuando sea necesario.

### Paso 8 - Identificar contratos runtime

Detectar interfaces relevantes:

- request esperada;
- payload de webhook;
- mensaje Pub/Sub;
- tabla BigQuery esperada;
- respuesta de API externa;
- formato de salida;
- codigos de error.

Recomendar `contracts.md` cuando un runtime dependa de una estructura estable.

### Paso 9 - Identificar riesgos de evolucion

Detectar riesgos como:

- trigger desconocido;
- variables de entorno no documentadas;
- dependencias externas no documentadas;
- falta de idempotencia;
- retries no documentados;
- errores no gestionados;
- ausencia de logs utiles;
- payload no documentado;
- service account desconocida;
- permisos IAM no documentados;
- timeout insuficiente;
- dependencia de tablas o endpoints hardcoded;
- despliegue manual no documentado;
- falta de separacion entre test y produccion.

Clasificar severidad:

severity: critical | important | minor

### Paso 10 - Recomendar artefactos

Recomendar actualizar `architecture_as_is.md` cuando:

- el runtime sea parte central del sistema;
- existan varios servicios conectados;
- haya triggers o dependencias relevantes.

Recomendar `contracts.md` cuando:

- existan payloads, mensajes o schemas esperados;
- el servicio exponga o consuma una interfaz estable;
- haya integracion con APIs externas o BigQuery.

Recomendar `sdd_readiness_assessment.md` cuando:

- falte contexto operativo critico;
- existan riesgos que bloqueen evolucion segura.

## Complementos

Esta skill puede apoyarse en complementos especificos:

- .github/skills/cloud-runtime-discovery/complements/cloud-functions.md -> identifica funciones Cloud Functions, entrypoints, triggers, entradas, salidas y dependencias.
- .github/skills/cloud-runtime-discovery/complements/cloud-run.md -> identifica servicios y jobs Cloud Run, contenedores, triggers, entradas, salidas y configuracion operativa.
- .github/skills/cloud-runtime-discovery/complements/scheduler-pubsub.md -> identifica schedulers, topics, subscriptions, mensajes y el flujo de activacion asociado.

Los complementos deben usarse solo cuando exista evidencia de esas tecnologias o cuando el usuario lo solicite explicitamente.

## Output recomendado

El resultado de esta skill debe poder integrarse dentro de un assessment mayor.

Formato recomendado:

# Cloud Runtime Discovery

## Runtime Components Detected

## Triggers

## Inputs

## Outputs

## Dependencies

## Operational Configuration

## Runtime Contracts

## Risks

## Recommended Artifacts

## Open Questions

## Definition of Done

La skill se considera completada cuando existe una respuesta clara a estas preguntas:

1. Que runtimes cloud existen?
2. Que componente se ejecuta donde?
3. Que activa cada componente?
4. Que entradas recibe?
5. Que salidas produce?
6. Que dependencias criticas tiene?
7. Que configuracion operativa es conocida?
8. Que contratos runtime existen?
9. Que riesgos condicionan la evolucion?
10. Que artefactos SDD deben crearse o actualizarse?

## Comportamiento esperado

Se conservador, preciso y orientado a trazabilidad.

Tu funcion no es mejorar la infraestructura.

Tu funcion es entender el runtime actual lo suficiente para permitir evolucion controlada bajo SDD.
