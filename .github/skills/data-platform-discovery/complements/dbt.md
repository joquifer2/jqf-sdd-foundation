# dbt Discovery Complement

## Proposito

Este complemento define el proceso para identificar y documentar el uso de dbt dentro de un proyecto existente.

Su objetivo es reconstruir el conocimiento minimo necesario sobre estructura, modelos, capas, dependencias, tests y documentacion dbt para que el proyecto pueda seguir evolucionando bajo metodologia SDD.

No es una auditoria completa de dbt.

No redisena el modelo de datos.

No crea ni modifica modelos, macros, tests, sources o documentacion.

## Cuando usar este complemento

Usa este complemento cuando el proyecto contenga evidencia de:

- dbt_project.yml
- models/
- sources.yml
- schema.yml
- macros/
- seeds/
- snapshots/
- packages.yml
- profiles.yml o referencia a profiles
- comandos dbt
- llamadas ref()
- llamadas source()
- carpetas staging, intermediate, marts o reference
- modelos con prefijos stg_, int_, fct_, dim_ o agg_

## Resultado esperado

Al finalizar este complemento debe quedar claro:

- si el proyecto usa dbt;
- como esta estructurado el proyecto dbt;
- que capas de modelos existen;
- que modelos principales intervienen;
- que sources existen;
- que dependencias principales hay entre modelos;
- que tests o documentacion existen;
- que riesgos existen para evolucionar modelos dbt;
- si hace falta generar o actualizar data_lineage.md, contracts.md o architecture_as_is.md.

## Principios

- Priorizar lineage y estructura sobre inventario exhaustivo.
- Separar evidencia de inferencia.
- No asumir convenciones si no estan reflejadas en el proyecto.
- No modificar modelos dbt.
- No crear tests.
- No reordenar carpetas.
- No cambiar materializaciones.
- No proponer refactors salvo como riesgo o pregunta abierta.
- Marcar como UNKNOWN todo lo que no pueda verificarse.

## Paso 1 - Confirmar presencia de dbt

Buscar evidencias como:

- dbt_project.yml
- profiles.yml
- packages.yml
- models/
- macros/
- seeds/
- snapshots/
- analyses/
- target/
- dbt run
- dbt test
- dbt docs generate
- ref(
- source(
- config(
- materialized
- schema.yml
- sources.yml

## Paso 2 - Identificar configuracion principal

Revisar dbt_project.yml si existe.

Documentar:

- nombre del proyecto;
- profile usado;
- model-paths;
- seed-paths;
- macro-paths;
- snapshot-paths;
- target-paths;
- configuracion por carpeta;
- materializaciones configuradas;
- tags relevantes;
- datasets o schemas destino si aparecen.

Formato recomendado:

| Config Item | Value | Evidence | Notes |
|---|---|---|---|

## Paso 3 - Identificar estructura de carpetas

Documentar estructura relevante dentro de dbt.

Ejemplos:

- models/staging/
- models/intermediate/
- models/marts/
- models/reference/
- models/sources/
- models/analytics/
- macros/
- seeds/
- snapshots/

Formato recomendado:

| Path | Layer | Purpose Observed | Evidence |
|---|---|---|---|

Si la estructura no sigue capas estandar, documentar la estructura real.

## Paso 4 - Identificar capas del modelo

Clasificar modelos segun evidencia:

- source
- staging
- intermediate
- fact
- dimension
- aggregate
- mart
- reference
- snapshot
- seed
- unknown

Usar naming, ubicacion y dependencias como evidencia.

No asumir capa unicamente por nombre si contradice la ubicacion o el uso.

## Paso 5 - Identificar sources

Buscar y documentar fuentes dbt.

Revisar:

- sources.yml
- schema.yml
- llamadas source()
- definiciones de database
- schema
- table
- freshness si existe

Formato recomendado:

| Source | Database | Schema | Table | Used By | Evidence |
|---|---|---|---|---|---|

## Paso 6 - Identificar modelos principales

Documentar modelos relevantes para entender el flujo principal.

Formato recomendado:

| Model | Layer | Materialization | Depends On | Used By | Evidence |
|---|---|---|---|---|---|

No inventariar todos los modelos si no son necesarios.

Priorizar:

- modelos finales;
- modelos con muchos dependientes;
- modelos usados por reporting;
- modelos que alimentan APIs;
- modelos criticos para metricas;
- modelos que actuan como interfaces estables.

## Paso 7 - Identificar dependencias

Reconstruir lineage minimo usando:

- ref()
- source()
- estructura de carpetas
- documentacion y schema.yml
- nombres de tablas
- modelos finales
- exposures si existen

Formato recomendado:

source -> stg_* -> int_* -> fct_/dim_ -> agg_/mart

Si el proyecto usa otra convencion, documentar la real.

Marcar tramos desconocidos como:

UNKNOWN

Required validation: ...

## Paso 8 - Identificar tests

Buscar tests en:

- schema.yml
- tests genericos
- tests singulares
- not_null
- unique
- relationships
- accepted_values
- dbt_utils
- custom tests

Formato recomendado:

| Model | Column | Test | Purpose | Evidence |
|---|---|---|---|---|

Documentar tambien riesgos por ausencia de tests en modelos criticos.

## Paso 9 - Identificar documentacion dbt

Buscar:

- descriptions en schema.yml
- docs blocks
- exposures
- metrics
- semantic models
- README
- dbt docs
- comentarios en SQL

Formato recomendado:

| Artifact | Documentation Exists | Quality Observed | Evidence |
|---|---|---|---|

## Paso 10 - Identificar macros y logica reutilizable

Si existen macros, documentar:

- nombre;
- proposito observado;
- modelos que la usan;
- riesgo si se modifica;
- evidencia.

Formato recomendado:

| Macro | Used By | Purpose Observed | Risk | Evidence |
|---|---|---|---|---|

## Paso 11 - Identificar seeds y snapshots

Si existen seeds, documentar:

- nombre;
- proposito;
- modelos dependientes;
- si actuan como tablas de referencia.

Si existen snapshots, documentar:

- entidad;
- estrategia;
- clave unica;
- campos tracked;
- riesgo de evolucion.

## Paso 12 - Identificar outputs y consumidores

Detectar que modelos dbt alimentan:

- Looker Studio
- Power BI
- dashboards
- APIs
- BigQuery final tables
- modelos ML
- procesos de scoring
- exports
- activaciones publicitarias
- reporting automatizado

Formato recomendado:

| dbt Model | Consumer | Purpose | Evidence |
|---|---|---|---|

## Paso 13 - Identificar riesgos dbt

Detectar riesgos como:

- falta dbt_project.yml;
- profile no documentado;
- estructura de capas inconsistente;
- modelos criticos sin tests;
- sources sin freshness;
- modelos finales sin descripcion;
- dependencias implicitas fuera de ref() o source();
- SQL hardcoded contra tablas externas;
- materializaciones no documentadas;
- macros criticas sin documentacion;
- seeds usados como logica de negocio sin explicacion;
- snapshots sin estrategia clara;
- reporting conectado a modelos intermedios;
- modelos duplicados o solapados;
- ausencia de documentacion de metricas;
- ausencia de exposures cuando hay BI.

Clasificar severidad:

severity: critical | important | minor

## Paso 14 - Recomendar artefactos

Recomendar data_lineage.md cuando:

- existan multiples capas dbt;
- existan modelos finales usados por reporting o APIs;
- no este claro como viajan las metricas;
- cambiar un modelo pueda afectar outputs relevantes.

Recomendar contracts.md cuando:

- un modelo dbt actue como interfaz estable;
- un dashboard dependa de columnas concretas;
- un proceso externo consuma una tabla generada por dbt;
- un modelo final alimente una API, scoring o activacion.

Recomendar actualizar architecture_as_is.md cuando:

- dbt sea el motor principal de transformacion;
- existan multiples capas;
- existan dependencias criticas con BigQuery, BI o procesos externos.

Recomendar actualizar retrospective_spec.md cuando:

- se detecten reglas de negocio relevantes implementadas en SQL;
- la logica funcional viva principalmente en modelos dbt.

## Output recomendado

El resultado de este complemento debe integrarse dentro de Data Platform Discovery.

Formato recomendado:

# dbt Discovery

## dbt Presence

## dbt Project Configuration

## Folder Structure

## Model Layers

## Sources

## Main Models

## Minimum dbt Lineage

## Tests

## Documentation

## Macros

## Seeds and Snapshots

## Consumers

## Risks

## Recommended Artifacts

## Open Questions

## Definition of Done

Este complemento esta completo cuando existe una respuesta clara a estas preguntas:

1. El proyecto usa dbt?
2. Cual es la configuracion principal?
3. Que capas de modelos existen?
4. Que sources alimentan el proyecto?
5. Que modelos son criticos?
6. Cual es el lineage minimo?
7. Que tests existen?
8. Que documentacion existe?
9. Que consumidores dependen de modelos dbt?
10. Que riesgos afectan a futuras evoluciones?
11. Hace falta documentar lineage, contracts o architecture As-Is?

## Comportamiento esperado

Se conservador, preciso y orientado a trazabilidad.

Tu funcion no es mejorar dbt.

Tu funcion es entender el uso actual de dbt lo suficiente para permitir evolucion controlada bajo SDD.