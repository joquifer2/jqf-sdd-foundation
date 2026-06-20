# ETL / ELT Discovery Complement

## Proposito

Este complemento define el proceso para identificar y documentar procesos ETL y ELT dentro de un proyecto existente.

Su objetivo es reconstruir el conocimiento minimo necesario sobre extraccion, carga, transformacion, sincronizacion y dependencias de datos para permitir evolucion controlada bajo metodologia SDD.

No es una auditoria completa de pipelines.

No modifica procesos ETL/ELT.

No optimiza pipelines.

No redisenia arquitecturas de datos.

## Cuando usar este complemento

Usa este complemento cuando el proyecto contenga evidencia de:

- ETL
- ELT
- pipelines de datos
- sincronizaciones
- procesos batch
- cargas incrementales
- cargas completas
- Cloud Functions ETL
- Cloud Run ETL
- dbt
- BigQuery
- Scheduled Queries
- APIs de extraccion
- webhooks que cargan datos
- scripts Python de integracion
- procesos de staging

## Resultado esperado

Al finalizar este complemento debe quedar claro:

- que pipelines existen;
- que sistemas origen participan;
- que sistemas destino participan;
- como se extraen los datos;
- como se cargan los datos;
- donde se transforman;
- que frecuencia tienen los procesos;
- que dependencias existen;
- que riesgos existen para evolucionarlos;
- que artefactos SDD deben actualizarse.

## Principios

- Priorizar trazabilidad sobre detalle operativo.
- Separar evidencia de inferencia.
- No asumir cargas incrementales si no existe evidencia.
- No asumir logica de transformacion no documentada.
- No modificar pipelines.
- No proponer optimizaciones salvo como riesgo.
- Marcar UNKNOWN cuando no exista evidencia suficiente.

## Paso 1 - Identificar pipelines

Buscar evidencia de:

- ETL
- ELT
- ingestion
- extract
- load
- transform
- sync
- pipeline
- workflow
- scheduler
- batch process

Formato recomendado:

| Pipeline | Purpose | Evidence |
|-----------|-----------|-----------|

## Paso 2 - Identificar sistemas origen

Detectar:

- CRM
- ERP
- Google Ads
- Meta Ads
- GA4
- Bitrix
- Systeme.io
- GoHighLevel
- MongoDB
- APIs
- archivos
- bases de datos

Formato recomendado:

| Source System | Data Type | Evidence |
|-----------|-----------|-----------|

## Paso 3 - Identificar sistemas destino

Detectar:

- BigQuery
- Data Warehouse
- CRM
- APIs externas
- tablas finales
- dashboards
- data marts

Formato recomendado:

| Destination System | Purpose | Evidence |
|-----------|-----------|-----------|

## Paso 4 - Identificar mecanismo de extraccion

Detectar:

- API
- webhook
- export
- conector
- archivo
- query
- CDC
- carga manual

Formato recomendado:

| Source | Extraction Method | Evidence |
|-----------|-----------|-----------|

## Paso 5 - Identificar mecanismo de carga

Detectar:

- insert
- merge
- append
- overwrite
- stream
- batch
- upload

Formato recomendado:

| Destination | Load Method | Evidence |
|-----------|-----------|-----------|

## Paso 6 - Identificar transformaciones

Detectar donde se transforma el dato:

- dbt
- SQL
- Stored Procedures
- Python
- Cloud Functions
- Cloud Run
- notebooks
- ETL tools

Formato recomendado:

| Transformation Layer | Tool | Evidence |
|-----------|-----------|-----------|

## Paso 7 - Identificar frecuencia

Detectar:

- real-time
- near real-time
- hourly
- daily
- weekly
- monthly
- manual
- unknown

Formato recomendado:

| Pipeline | Frequency | Evidence |
|-----------|-----------|-----------|

## Paso 8 - Identificar controles operativos

Detectar:

- logs
- retries
- checkpoints
- status tables
- audit tables
- monitoring
- alerts

Formato recomendado:

| Control | Purpose | Evidence |
|-----------|-----------|-----------|

## Paso 9 - Identificar contratos

Detectar contratos relevantes:

- schema esperado;
- tabla origen;
- tabla destino;
- payload esperado;
- modelo dbt consumido;
- interfaz estable entre componentes.

Formato recomendado:

| Contract Candidate | Producer | Consumer | Evidence |
|-----------|-----------|-----------|

## Paso 10 - Identificar riesgos

Detectar riesgos como:

- origen desconocido;
- frecuencia desconocida;
- carga no documentada;
- transformaciones ocultas;
- ausencia de logs;
- ausencia de monitoring;
- dependencia de tablas no documentadas;
- pipelines manuales;
- falta de idempotencia;
- falta de controles de calidad;
- dependencia de personas concretas.

Clasificar:

severity: critical | important | minor

## Paso 11 - Recomendar artefactos

Recomendar:

### data_lineage.md

Cuando:

- existan varios pasos de transformacion;
- existan multiples sistemas;
- existan dependencias downstream.

### contracts.md

Cuando:

- existan schemas o interfaces estables.

### architecture_as_is.md

Cuando:

- los pipelines formen parte central del sistema.

### retrospective_spec.md

Cuando:

- existan reglas de negocio implementadas en transformaciones.

## Output recomendado

# ETL / ELT Discovery

## Pipelines

## Source Systems

## Destination Systems

## Extraction

## Loading

## Transformations

## Frequencies

## Operational Controls

## Contract Candidates

## Risks

## Recommended Artifacts

## Open Questions

## Definition of Done

Este complemento esta completo cuando existe una respuesta clara a estas preguntas:

1. Que pipelines existen?
2. Que sistemas origen participan?
3. Que sistemas destino participan?
4. Como se extraen los datos?
5. Como se cargan?
6. Donde se transforman?
7. Con que frecuencia se ejecutan?
8. Que controles operativos existen?
9. Que contratos deben documentarse?
10. Que riesgos afectan futuras evoluciones?
11. Que artefactos SDD deben actualizarse?

## Comportamiento esperado

Se conservador, preciso y orientado a trazabilidad.

Tu funcion no es mejorar los pipelines.

Tu funcion es entender los flujos ETL/ELT actuales lo suficiente para permitir evolucion controlada bajo metodologia SDD.