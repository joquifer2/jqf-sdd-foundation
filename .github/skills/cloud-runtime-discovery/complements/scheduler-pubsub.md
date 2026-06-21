---
name: scheduler-pubsub
description: Complemento para identificar schedulers, topics, subscriptions, mensajes y flujos de activación.
id: SDD-SKILL-COMP-006
parent_skill: cloud-runtime-discovery
user-invocable: false
disable-model-invocation: false
---
# Scheduler and PubSub Discovery Complement

## Proposito

Este complemento define el proceso para identificar y documentar el uso de Cloud Scheduler y Pub/Sub dentro de un proyecto existente.

Su objetivo es reconstruir el conocimiento minimo necesario sobre procesos programados, mensajes, topics, subscriptions, triggers y dependencias para permitir evolucion controlada bajo metodologia SDD.

No es una auditoria completa de infraestructura.

No modifica schedulers.

No crea topics ni subscriptions.

No cambia triggers ni configuraciones cloud.

## Cuando usar este complemento

Usa este complemento cuando el proyecto contenga evidencia de:

- Cloud Scheduler
- Pub/Sub
- topics
- subscriptions
- mensajes programados
- triggers Pub/Sub
- cron jobs
- schedulers HTTP
- schedulers hacia Cloud Functions
- schedulers hacia Cloud Run
- funciones activadas por Pub/Sub
- workers activados de forma programada
- comandos gcloud scheduler
- comandos gcloud pubsub

## Resultado esperado

Al finalizar este complemento debe quedar claro:

- que procesos programados existen;
- que schedulers activan componentes;
- que topics Pub/Sub existen;
- que subscriptions existen;
- que mensajes se publican;
- que consumidores procesan los mensajes;
- que frecuencia tiene cada ejecucion;
- que riesgos existen para evolucionar el sistema;
- si hace falta documentar contratos o arquitectura.

## Principios

- Priorizar comprension del flujo de activacion.
- Separar evidencia de inferencia.
- No asumir frecuencias no documentadas.
- No asumir payloads si no hay evidencia.
- No modificar jobs, topics ni subscriptions.
- No crear automatizaciones nuevas.
- No redisenar la orquestacion.
- Marcar UNKNOWN cuando falte evidencia.

## Paso 1 - Identificar Cloud Scheduler

Buscar evidencia como:

- Cloud Scheduler
- scheduler
- cron
- gcloud scheduler jobs create
- gcloud scheduler jobs update
- schedule:
- cron.yaml
- HTTP target
- Pub/Sub target
- OIDC token
- service account
- jobs programados
- ejecucion diaria, horaria, semanal o mensual

Formato recomendado:

| Scheduler Job | Target Type | Target | Frequency | Evidence |
|---|---|---|---|---|

Target Type puede ser:

- HTTP
- Pub/Sub
- Cloud Function
- Cloud Run
- Unknown

## Paso 2 - Identificar Pub/Sub

Buscar evidencia como:

- Pub/Sub
- pubsub
- topic
- subscription
- google.cloud.pubsub
- gcloud pubsub topics
- gcloud pubsub subscriptions
- publish
- subscribe
- message.data
- base64
- event.data
- attributes

Formato recomendado:

| Topic / Subscription | Type | Purpose Observed | Evidence |
|---|---|---|---|

## Paso 3 - Identificar flujo de activacion

Reconstruir que activa que.

Ejemplos:

Cloud Scheduler
→ Pub/Sub topic
→ Cloud Function

Cloud Scheduler
→ HTTP request
→ Cloud Run

Pub/Sub topic
→ Cloud Function
→ BigQuery

Formato recomendado:

| Trigger Source | Intermediate | Target Component | Evidence |
|---|---|---|---|

Si falta un tramo:

UNKNOWN

Required validation: ...

## Paso 4 - Identificar frecuencia

Detectar frecuencia de ejecucion:

- cada X minutos;
- hourly;
- daily;
- weekly;
- monthly;
- cron expression;
- manual;
- unknown.

Formato recomendado:

| Scheduler Job | Frequency | Timezone | Evidence |
|---|---|---|---|

Si no aparece timezone:

UNKNOWN

## Paso 5 - Identificar payloads

Detectar que mensaje o payload se envia.

Tipos habituales:

- payload vacio;
- JSON;
- mensaje generico de trigger;
- parametros de fecha;
- identificador de proceso;
- event_type;
- datos codificados en base64;
- atributos Pub/Sub.

Formato recomendado:

| Producer | Payload / Message | Consumer | Evidence |
|---|---|---|---|

Si el mensaje es solo un disparador generico, documentarlo explicitamente.

## Paso 6 - Identificar consumidores

Detectar que procesa el mensaje o job:

- Cloud Function;
- Cloud Run service;
- worker;
- script;
- endpoint HTTP;
- API interna;
- proceso ETL/ELT;
- pipeline de datos.

Formato recomendado:

| Consumer | Triggered By | Responsibility | Evidence |
|---|---|---|---|

## Paso 7 - Identificar dependencias operativas

Documentar dependencias relevantes:

- service account;
- permisos IAM;
- OIDC;
- Pub/Sub topic;
- subscription;
- endpoint HTTP;
- Cloud Function;
- Cloud Run;
- BigQuery;
- APIs externas;
- variables de entorno;
- region;
- timezone.

Formato recomendado:

| Process | Dependency | Type | Evidence |
|---|---|---|---|

## Paso 8 - Identificar contratos

Detectar contratos relevantes:

- estructura del mensaje Pub/Sub;
- atributos esperados;
- payload HTTP;
- endpoint destino;
- respuesta esperada;
- codigos HTTP esperados;
- comportamiento ante reintentos.

Formato recomendado:

| Process | Contract Candidate | Why It Matters | Evidence |
|---|---|---|---|

Recomendar contracts.md cuando el scheduler o Pub/Sub dependan de payloads o interfaces estables.

## Paso 9 - Identificar riesgos

Detectar riesgos como:

- scheduler no documentado;
- frecuencia desconocida;
- timezone desconocido;
- payload desconocido;
- topic no documentado;
- subscription no documentada;
- consumidor no identificado;
- reintentos no documentados;
- riesgo de duplicidad;
- falta de idempotencia;
- permisos IAM desconocidos;
- service account desconocida;
- endpoint hardcoded;
- dependencia de orden temporal;
- ausencia de logs;
- ausencia de alertas;
- jobs manuales no trazados.

Clasificar:

severity: critical | important | minor

Formato:

### Risk

#### Severity

#### Description

#### Evidence

#### Impact

## Paso 10 - Recomendar artefactos

Recomendar actualizar:

### architecture_as_is.md

Cuando:

- Scheduler o Pub/Sub sean parte central del flujo;
- existan varios componentes conectados;
- el trigger sea necesario para entender el sistema.

### contracts.md

Cuando:

- existan payloads Pub/Sub;
- existan mensajes esperados;
- el endpoint dependa de una estructura concreta;
- haya reintentos o comportamiento esperado relevante.

### data_lineage.md

Cuando:

- Scheduler o Pub/Sub activen pipelines de datos.

### sdd_readiness_assessment.md

Cuando:

- falte informacion critica sobre cuando o como se ejecutan los procesos.

## Output recomendado

# Scheduler and Pub/Sub Discovery

## Scheduler Jobs Detected

## Pub/Sub Topics and Subscriptions

## Activation Flow

## Frequencies

## Payloads

## Consumers

## Operational Dependencies

## Contract Candidates

## Risks

## Recommended Artifacts

## Open Questions

## Definition of Done

Este complemento esta completo cuando existe una respuesta clara a estas preguntas:

1. Que schedulers existen?
2. Que activa cada scheduler?
3. Que topics o subscriptions existen?
4. Que mensaje o payload se envia?
5. Que componente consume cada mensaje o trigger?
6. Con que frecuencia se ejecuta?
7. Que dependencias operativas existen?
8. Que contratos son relevantes?
9. Que riesgos condicionan futuras evoluciones?
10. Que artefactos SDD deben actualizarse?

## Comportamiento esperado

Se conservador, preciso y orientado a trazabilidad.

Tu funcion no es mejorar la orquestacion.

Tu funcion es entender como se activan los procesos actuales lo suficiente para permitir evolucion controlada bajo metodologia SDD.
