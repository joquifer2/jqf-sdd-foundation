# Lineage Discovery Complement

## Proposito

Este complemento define el proceso para reconstruir el lineage minimo de datos dentro de un proyecto existente.

Su objetivo es identificar como fluye el dato desde los sistemas origen hasta los consumidores finales, con suficiente claridad para permitir evolucion controlada bajo metodologia SDD.

No es una auditoria exhaustiva de lineage.

No requiere mapear todos los campos.

No redisena el modelo de datos.

No modifica pipelines, modelos, tablas ni dashboards.

## Cuando usar este complemento

Usa este complemento cuando el proyecto contenga:

- multiples fuentes de datos;
- BigQuery;
- dbt;
- pipelines ETL/ELT;
- scheduled queries;
- stored procedures;
- dashboards;
- reporting automatizado;
- APIs que consumen datos;
- procesos de scoring;
- activaciones publicitarias;
- modelos ML;
- tablas intermedias o finales con dependencias.

## Resultado esperado

Al finalizar este complemento debe quedar claro:

- de donde vienen los datos;
- donde se almacenan;
- donde se transforman;
- que tablas o modelos son intermedios;
- que tablas o modelos son finales;
- que consumidores dependen del dato;
- que tramos del lineage estan claros;
- que tramos son desconocidos;
- que riesgos existen al modificar componentes del flujo.

## Principios

- Priorizar el flujo principal sobre el inventario completo.
- Documentar lineage a nivel de sistema, tabla o modelo.
- No bajar a nivel de columna salvo que sea necesario.
- Separar evidencia de inferencia.
- No asumir dependencias sin evidencia.
- No inventar sistemas origen.
- No inventar consumidores.
- Marcar tramos desconocidos como UNKNOWN.
- Evitar duplicar documentacion generada por dbt docs u otras herramientas.
- Mantener el foco en evolucion SDD, no en observabilidad tecnica exhaustiva.

## Paso 1 - Identificar sistemas origen

Detectar sistemas que generan o entregan datos.

Ejemplos:

- CRM;
- GA4;
- Google Ads;
- Meta Ads;
- formularios;
- webhooks;
- hojas de calculo;
- APIs externas;
- bases de datos operacionales;
- ficheros CSV o Excel;
- sistemas SaaS;
- ERP;
- ecommerce;
- herramientas de marketing automation.

Formato recomendado:

| Source System | Data Provided | Ingestion Method | Evidence | Confidence |
|---|---|---|---|---|

## Paso 2 - Identificar mecanismos de ingesta

Detectar como entra el dato al sistema.

Ejemplos:

- export nativo;
- API;
- webhook;
- carga manual;
- conector;
- script Python;
- Cloud Function;
- Cloud Run;
- scheduled query;
- dbt source;
- fichero CSV;
- Google Sheets;
- BigQuery Data Transfer.

Formato recomendado:

| Source | Ingestion Method | Destination | Frequency | Evidence |
|---|---|---|---|---|

Si la frecuencia no aparece, marcar UNKNOWN.

## Paso 3 - Identificar almacenamiento inicial

Detectar donde aterriza el dato primero.

Ejemplos:

- tablas raw;
- datasets source;
- tablas externas;
- buckets;
- hojas de calculo;
- bases operacionales;
- staging inicial;
- tablas temporales.

Formato recomendado:

| Landing Object | Type | Source System | Role | Evidence |
|---|---|---|---|---|

Roles posibles:

- raw;
- source;
- landing;
- temporary;
- staging;
- unknown.

## Paso 4 - Identificar transformaciones

Detectar donde cambia el dato.

Ejemplos:

- modelos dbt;
- SQL manual;
- stored procedures;
- scheduled queries;
- scripts Python;
- notebooks;
- Cloud Functions;
- Cloud Run jobs;
- hojas de calculo;
- herramientas ETL.

Formato recomendado:

| Transformation | Input | Output | Tool | Purpose Observed | Evidence |
|---|---|---|---|---|---|

## Paso 5 - Identificar capas intermedias

Detectar objetos que preparan, limpian, enriquecen o consolidan datos.

Ejemplos:

- stg_*;
- int_*;
- intermediate;
- staging;
- cleaned;
- enriched;
- normalized;
- joined;
- deduplicated.

Formato recomendado:

| Object | Layer | Input | Output / Used By | Purpose Observed | Evidence |
|---|---|---|---|---|---|

## Paso 6 - Identificar objetos finales

Detectar tablas, modelos o vistas que actuan como salida estable.

Ejemplos:

- fct_*;
- dim_*;
- agg_*;
- marts;
- final tables;
- reporting tables;
- activation tables;
- inference tables;
- scoring tables.

Formato recomendado:

| Final Object | Type | Consumers | Purpose Observed | Evidence |
|---|---|---|---|---|

## Paso 7 - Identificar consumidores

Detectar quien o que consume los datos finales o intermedios.

Ejemplos:

- Looker Studio;
- Power BI;
- Google Sheets;
- dashboards internos;
- reporting automatizado;
- APIs externas;
- Meta CAPI;
- Google Ads Offline Conversions;
- modelos ML;
- notebooks;
- exports;
- equipos de negocio;
- tareas programadas.

Formato recomendado:

| Consumer | Consumes From | Usage | Evidence | Risk if Changed |
|---|---|---|---|---|

## Paso 8 - Reconstruir lineage minimo

Reconstruir el flujo principal en formato textual.

Formato recomendado:

Source System
-> Ingestion
-> Raw / Landing
-> Staging
-> Intermediate
-> Mart / Final
-> Consumer

Ejemplo:

CRM
-> API extraction
-> BigQuery raw_deals
-> dbt stg_deals
-> dbt int_sales
-> dbt fct_sales
-> Looker Studio

Si no existe una capa, omitirla.

Si se desconoce un tramo:

UNKNOWN
Required validation: ...

## Paso 9 - Identificar contratos de lineage

Detectar objetos que actuan como frontera estable entre componentes.

Ejemplos:

- tabla final consumida por dashboard;
- tabla consumida por worker;
- modelo dbt consumido por API;
- tabla de scoring usada por activacion publicitaria;
- webhook que carga tabla concreta;
- CSV con schema esperado;
- vista usada como fuente por otro sistema.

Formato recomendado:

| Contract Candidate | Producer | Consumer | Why It Matters | Evidence |
|---|---|---|---|---|

Recomendar `contracts.md` solo si estos contratos son relevantes para futuras evoluciones.

## Paso 10 - Identificar riesgos de lineage

Detectar riesgos como:

- origen del dato desconocido;
- transformacion critica no documentada;
- tabla final sin owner;
- dashboard conectado a tabla intermedia;
- modelo downstream no identificado;
- columnas clave sin definicion;
- reglas de negocio ocultas en SQL;
- dependencia de nombres hardcoded;
- lineage roto o incompleto;
- duplicidad de rutas para una misma metrica;
- consumidores no documentados;
- no existe separacion entre raw y marts;
- no esta claro que tabla es source of truth;
- cambios en una tabla pueden romper consumidores.

Clasificar severidad:

severity: critical | important | minor

## Paso 11 - Recomendar artefactos

Recomendar `data_lineage.md` cuando:

- existan varias capas de datos;
- existan multiples sistemas origen;
- existan consumidores downstream;
- haya riesgo de romper reporting, APIs o modelos;
- no este clara la source of truth;
- se quiera evolucionar el proyecto bajo SDD.

Recomendar `contracts.md` cuando:

- existan tablas o modelos que funcionen como interfaces estables;
- un proceso externo dependa de un schema concreto;
- una API consuma datos desde una tabla;
- un dashboard dependa de campos especificos.

Recomendar actualizar `architecture_as_is.md` cuando:

- el flujo de datos sea parte central del sistema;
- existan varios productores y consumidores;
- existan dependencias operativas relevantes.

## Output recomendado

El resultado de este complemento debe integrarse dentro de `Data Platform Discovery`.

Formato recomendado:

# Lineage Discovery

## Source Systems

## Ingestion Paths

## Landing Layer

## Transformation Layer

## Intermediate Objects

## Final Objects

## Consumers

## Minimum Lineage

## Contract Candidates

## Lineage Risks

## Recommended Artifacts

## Open Questions

## Definition of Done

Este complemento esta completo cuando existe una respuesta clara a estas preguntas:

1. De donde vienen los datos?
2. Como entran en el sistema?
3. Donde aterrizan inicialmente?
4. Donde se transforman?
5. Que objetos son intermedios?
6. Que objetos son finales?
7. Quien consume los datos?
8. Cual es el lineage minimo?
9. Que tramos siguen siendo desconocidos?
10. Que riesgos afectan a futuras evoluciones?
11. Hace falta documentar data_lineage.md o contracts.md?

## Comportamiento esperado

Se conservador, preciso y orientado a trazabilidad.

Tu funcion no es documentar todos los campos.

Tu funcion es reconstruir el flujo de datos minimo necesario para permitir evolucion controlada bajo SDD.