---
name: data-platform-discovery
description: Esta skill ayuda a identificar plataformas de datos, fuentes, transformaciones, lineage y consumidores.
id: SDD-SKILL-002
user-invocable: true
disable-model-invocation: false
---
# Data Platform Discovery Skill

## Proposito

Esta skill define el proceso para identificar y documentar de forma minima una plataforma de datos existente dentro de un proyecto SDD.

Su objetivo es ayudar a reconstruir como se almacenan, transforman y consumen los datos en un proyecto ya desarrollado o parcialmente desarrollado.

No sustituye a una auditoria tecnica completa.

No redisena la plataforma de datos.

No implementa modelos, tablas, pipelines ni automatizaciones.

## Cuando usar esta skill

Usa esta skill cuando el proyecto contenga o pueda contener:

- BigQuery
- dbt
- SQL
- pipelines de datos
- modelos analiticos
- tablas raw, staging, intermediate o marts
- dashboards conectados a datos
- procesos ETL/ELT
- scheduled queries
- stored procedures
- data lineage relevante

## Resultado esperado

Al finalizar esta skill debe quedar claro:

- que sistemas de datos existen;
- que capas de datos existen;
- que tablas, modelos o datasets principales intervienen;
- como fluye el dato de origen a consumo;
- que transformaciones principales existen;
- que riesgos afectan a la evolucion de datos;
- si hace falta generar `data_lineage.md`, `contracts.md` o ampliar `architecture_as_is.md`.

## Principios

- Priorizar trazabilidad sobre exhaustividad.
- Documentar solo lo necesario para continuar bajo SDD.
- Separar evidencia de inferencia.
- No redisenar modelos de datos.
- No modificar queries, tablas ni modelos.
- No asumir granularidad si no esta documentada o visible.
- No inventar dependencias.
- Marcar como UNKNOWN lo que no pueda verificarse.
- Evitar duplicar documentacion dbt, BigQuery o BI ya existente.

## Flujo

### Paso 1 - Detectar tecnologias de datos

Identificar si existen senales de:

- BigQuery
- dbt
- SQL
- Looker Studio
- Power BI
- Google Sheets como salida
- APIs de extraccion
- pipelines Python
- Cloud Functions orientadas a datos
- scheduled queries
- stored procedures

### Paso 2 - Identificar fuentes de datos

Detectar sistemas origen:

- CRM
- GA4
- Google Ads
- Meta Ads
- formularios
- webhooks
- ficheros CSV o Excel
- APIs externas
- bases de datos operacionales
- sistemas SaaS

Para cada fuente, documentar:

- nombre;
- tipo;
- evidencia;
- datos que aporta;
- nivel de certeza.

### Paso 3 - Identificar almacenamiento

Detectar:

- project_id;
- datasets;
- tablas;
- vistas;
- particionamiento;
- clustering;
- convenciones de nombres;
- tablas criticas;
- tablas temporales o staging;
- tablas finales o marts.

No es necesario inventariar todas las tablas si no son relevantes.

Priorizar las tablas que formen parte del flujo principal.

### Paso 4 - Identificar transformaciones

Detectar donde se transforma el dato:

- SQL directo;
- dbt models;
- stored procedures;
- scheduled queries;
- scripts Python;
- notebooks;
- Cloud Functions;
- workflows externos;
- hojas de calculo.

Documentar:

- transformacion principal;
- entrada;
- salida;
- evidencia;
- riesgos.

### Paso 5 - Identificar capas del modelo

Cuando aplique, clasificar capas existentes:

- raw
- staging
- intermediate
- marts
- reporting
- activation

Si el proyecto no usa estas capas, documentar la estructura real observada.

### Paso 6 - Identificar consumidores

Detectar consumidores del dato:

- Looker Studio
- Power BI
- dashboards internos
- Google Sheets
- APIs externas
- Meta CAPI
- Google Ads Offline Conversions
- reporting automatizado
- modelos ML
- procesos de scoring

### Paso 7 - Reconstruir lineage minimo

Reconstruir el flujo principal:

source -> ingestion -> storage -> transformation -> consumption

Ejemplo:

CRM -> BigQuery raw -> dbt staging -> dbt marts -> Looker Studio

Si hay tramos desconocidos, marcar:

UNKNOWN

Required validation: ...

### Paso 8 - Detectar contratos de datos

Identificar si existen interfaces de datos relevantes:

- tabla origen -> tabla destino
- modelo dbt -> modelo dbt
- BigQuery -> API externa
- webhook -> tabla
- CSV -> tabla
- modelo ML -> tabla de inferencias
- dashboard -> tabla final

Recomendar `contracts.md` solo si esos contratos son relevantes para futuras evoluciones.

### Paso 9 - Identificar riesgos de evolucion

Detectar riesgos como:

- lineage incompleto;
- tablas criticas no documentadas;
- granularidad desconocida;
- modelos sin tests;
- queries costosas no controladas;
- scheduled queries no documentadas;
- stored procedures sin owner;
- dashboards conectados directamente a raw;
- cambios en una tabla podrian romper reporting;
- no existe separacion clara entre staging y marts;
- no existe documentacion de campos;
- no existen reglas de calidad de datos.

### Paso 10 - Recomendar artefactos

Recomendar solo si aportan valor real:

- data_lineage.md
- contracts.md
- architecture_as_is.md
- retrospective_spec.md
- sdd_readiness_assessment.md

## Complementos

Esta skill puede apoyarse en complementos especificos:

- .github/skills/data-platform-discovery/complements/bigquery.md -> identifica proyectos, datasets, tablas, vistas, queries, scheduled queries, consumidores y riesgos BigQuery.
- .github/skills/data-platform-discovery/complements/dbt.md -> identifica estructura dbt, modelos, sources, tests, documentacion, lineage y riesgos.
- .github/skills/data-platform-discovery/complements/lineage.md -> reconstruye el flujo minimo del dato desde origen hasta consumo final.

Los complementos deben usarse solo cuando el proyecto contenga evidencia de esas tecnologias o cuando el usuario lo solicite explicitamente.

## Output recomendado

El resultado de esta skill debe poder integrarse dentro de un assessment mayor.

Formato recomendado:

# Data Platform Discovery

## Data Technologies Detected

## Source Systems

## Storage Layer

## Transformation Layer

## Data Layers

## Data Consumers

## Minimum Lineage

## Data Contracts Detected

## Risks

## Recommended Artifacts

## Open Questions

## Definition of Done

La skill se considera completada cuando existe una respuesta clara a estas preguntas:

1. Que tecnologias de datos existen?
2. Que fuentes alimentan el sistema?
3. Donde se almacenan los datos?
4. Donde se transforman?
5. Que capas de datos existen?
6. Quien consume los datos?
7. Cual es el lineage minimo?
8. Que riesgos afectan a futuras evoluciones?
9. Que artefactos SDD deben crearse o actualizarse?

## Comportamiento esperado

Se preciso, conservador y orientado a trazabilidad.

Tu funcion no es mejorar la plataforma de datos.

Tu funcion es entenderla lo suficiente para que el proyecto pueda seguir evolucionando bajo SDD.