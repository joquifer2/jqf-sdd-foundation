# BigQuery Discovery Complement

## Proposito

Este complemento define el proceso para identificar y documentar el uso de BigQuery dentro de un proyecto existente.

Su objetivo es reconstruir el conocimiento minimo necesario sobre datasets, tablas, consultas, procedimientos y dependencias para que el proyecto pueda seguir evolucionando bajo metodologia SDD.

No es una auditoria completa de BigQuery.

No optimiza consultas.

No modifica datasets, tablas, vistas ni scheduled queries.

## Cuando usar este complemento

Usa este complemento cuando el proyecto contenga evidencia de:

- BigQuery;
- SQL de BigQuery;
- project_id de Google Cloud;
- datasets;
- tablas;
- vistas;
- stored procedures;
- scheduled queries;
- Looker Studio conectado a BigQuery;
- Cloud Functions que leen o escriben en BigQuery;
- scripts Python que usan BigQuery;
- procesos de activacion desde BigQuery hacia APIs externas.

## Resultado esperado

Al finalizar este complemento debe quedar claro:

- que proyectos GCP aparecen;
- que datasets aparecen;
- que tablas o vistas principales aparecen;
- que procesos leen datos de BigQuery;
- que procesos escriben datos en BigQuery;
- que transformaciones SQL existen;
- que jobs o scheduled queries parecen relevantes;
- que consumidores dependen de BigQuery;
- que riesgos existen para evolucionar el sistema.

## Principios

- Priorizar tablas y datasets criticos sobre inventarios exhaustivos.
- Separar evidencia de inferencia.
- No asumir granularidad si no esta explicita.
- No asumir ownership si no esta documentado.
- No proponer optimizaciones salvo como riesgo o pregunta abierta.
- No modificar SQL.
- No crear tablas.
- No crear scheduled queries.
- No redisenar el modelo de datos.
- Marcar como UNKNOWN todo lo que no pueda verificarse.

## Paso 1 - Detectar referencias a BigQuery

Buscar evidencias como:

- `google.cloud.bigquery`
- `BigQuery`
- `bq`
- `project_id`
- `dataset_id`
- nombres con formato `project.dataset.table`
- SQL con backticks
- `CREATE TABLE`
- `CREATE OR REPLACE TABLE`
- `CREATE VIEW`
- `CREATE PROCEDURE`
- `MERGE`
- `INSERT INTO`
- `Scheduled Query`
- `Looker Studio`
- `INFORMATION_SCHEMA`

## Paso 2 - Identificar proyectos GCP

Documentar project_ids detectados.

Formato recomendado:

Project ID
Evidence
Usage
Confidence

Si el project_id aparece en variables de entorno, configuracion o codigo, indicarlo.

## Paso 3 - Identificar datasets

Documentar datasets relevantes.

Formato recomendado:

Dataset
Project ID
Purpose Observed
Evidence
Confidence

No inventariar datasets secundarios si no afectan al flujo principal.

## Paso 4 - Identificar tablas y vistas principales

Documentar solo tablas o vistas relevantes para entender el sistema.

Formato recomendado:

Table/View
Dataset
Type
Role
Read/Write
Evidence

Roles posibles:

- source;
- raw;
- staging;
- intermediate;
- mart;
- reporting;
- activation;
- audit;
- unknown.

## Paso 5 - Identificar operaciones SQL relevantes

Buscar operaciones como:

- SELECT;
- JOIN;
- UNION;
- MERGE;
- INSERT;
- UPDATE;
- DELETE;
- CREATE TABLE;
- CREATE VIEW;
- CREATE PROCEDURE;
- CALL procedure;
- QUALIFY;
- WINDOW functions;
- PARTITION BY;
- CLUSTER BY.

Documentar las operaciones que afecten al flujo principal.

Formato recomendado:

Operation
Source
Target
Purpose
Evidence

## Paso 6 - Identificar procesos de lectura

Detectar componentes que leen desde BigQuery:

- scripts Python;
- Cloud Functions;
- Cloud Run services;
- workers;
- notebooks;
- dashboards;
- APIs;
- jobs programados;
- procesos de scoring;
- procesos de activacion publicitaria.

Formato recomendado:

Consumer
Reads From
Purpose
Evidence

## Paso 7 - Identificar procesos de escritura

Detectar componentes que escriben en BigQuery:

- scripts Python;
- Cloud Functions;
- Cloud Run services;
- webhooks;
- APIs;
- scheduled queries;
- stored procedures;
- dbt models;
- manual uploads.

Formato recomendado:

Producer
Writes To
Purpose
Evidence

## Paso 8 - Identificar scheduled queries y stored procedures

Si aparecen scheduled queries o stored procedures, documentar:

- nombre;
- frecuencia si aparece;
- query o procedure asociada;
- tabla origen;
- tabla destino;
- ventana temporal;
- proposito observado;
- evidencia.

Formato recomendado:

Process
Type
Source
Target
Frequency
Evidence

Si la frecuencia no aparece, marcar UNKNOWN.

## Paso 9 - Identificar particionamiento y clustering

Detectar si las tablas estan particionadas o clusterizadas.

Buscar:

- `PARTITION BY`
- `CLUSTER BY`
- campos como `date`, `event_date`, `created_at`, `metric_date`
- documentacion de optimizacion
- configuracion dbt relacionada

Formato recomendado:

Table
Partition Field
Cluster Fields
Evidence
Confidence

No asumir particionamiento solo porque exista un campo fecha.

## Paso 10 - Identificar consumidores finales

Detectar salidas o consumidores:

- Looker Studio;
- Power BI;
- Google Sheets;
- dashboards;
- APIs de marketing;
- Meta CAPI;
- Google Ads Offline Conversions;
- reporting automatizado;
- modelos ML;
- exports CSV;
- sistemas internos.

Formato recomendado:

Consumer
Consumes From
Purpose
Evidence

## Paso 11 - Reconstruir flujo minimo BigQuery

Reconstruir el flujo principal:

source -> BigQuery raw/source -> transformations -> final tables -> consumers

Ejemplo:

CRM -> raw_leads -> stg_leads -> fct_leads -> Looker Studio

Si falta un tramo, marcar:

UNKNOWN

Required validation: ...

## Paso 12 - Identificar riesgos BigQuery

Detectar riesgos como:

- project_id no documentado;
- datasets criticos sin explicacion;
- tablas finales no identificadas;
- tablas raw usadas directamente en reporting;
- ausencia de particionamiento en tablas grandes;
- ausencia de clustering en filtros frecuentes;
- scheduled queries no documentadas;
- stored procedures sin owner;
- MERGE sin clave clara;
- ventanas de reprocesamiento desconocidas;
- dashboards conectados a tablas intermedias;
- queries SQL criticas dispersas en scripts;
- falta de tests o validaciones;
- dependencia de nombres hardcoded;
- credenciales o permisos no documentados.

Clasificar severidad:

severity: critical | important | minor

## Paso 13 - Recomendar artefactos

Recomendar `data_lineage.md` cuando:

- existan varias capas de datos;
- existan transformaciones relevantes;
- existan consumidores downstream;
- no este claro el origen de las metricas;
- cambiar una tabla pueda afectar reporting, APIs o modelos.

Recomendar `contracts.md` cuando:

- BigQuery alimente APIs externas;
- una tabla sea interfaz entre componentes;
- un dashboard dependa de un schema estable;
- un worker espere columnas concretas;
- una scheduled query produzca una tabla consumida por otros procesos.

Recomendar actualizar `architecture_as_is.md` cuando:

- BigQuery sea componente central del sistema;
- existan varios productores y consumidores;
- existan dependencias operativas relevantes.

## Output recomendado

El resultado de este complemento debe integrarse dentro de `Data Platform Discovery`.

Formato recomendado:

# BigQuery Discovery

## Projects Detected

## Datasets Detected

## Main Tables and Views

## SQL Processes

## Read Processes

## Write Processes

## Scheduled Queries and Stored Procedures

## Partitioning and Clustering

## Final Consumers

## Minimum BigQuery Lineage

## Risks

## Recommended Artifacts

## Open Questions

## Definition of Done

Este complemento esta completo cuando existe una respuesta clara a estas preguntas:

1. Que proyectos GCP aparecen?
2. Que datasets relevantes existen?
3. Que tablas o vistas son criticas?
4. Que procesos leen de BigQuery?
5. Que procesos escriben en BigQuery?
6. Que transformaciones SQL son relevantes?
7. Que procesos programados existen?
8. Que consumidores dependen de BigQuery?
9. Que riesgos afectan a futuras evoluciones?
10. Hace falta documentar lineage, contracts o architecture As-Is?

## Comportamiento esperado

Se conservador, preciso y orientado a trazabilidad.

Tu funcion no es mejorar BigQuery.

Tu funcion es entender el uso actual de BigQuery lo suficiente para permitir evolucion controlada bajo SDD.