# Skills Index

## Propósito

Este directorio contiene skills metodológicas reutilizables de `jqf-sdd-foundation`.

Una skill define un procedimiento reutilizable. No representa un agente, no implementa runtime y no contiene lógica productiva.

## Convención

Cada skill debe incluir:

- frontmatter YAML;
- propósito;
- cuándo usarla;
- flujo operativo;
- output esperado;
- Definition of Done;
- sección `## Complementos` cuando aplique.

## Skills principales

| Skill | Tipo | Propósito |
|---|---|---|
| `legacy-to-sdd` | Orquestadora | Incorpora proyectos existentes al ciclo SDD reconstruyendo el conocimiento mínimo necesario para continuar su evolución. |
| `data-platform-discovery` | Discovery | Identifica plataformas de datos, fuentes, transformaciones, lineage, consumidores y riesgos asociados. |
| `cloud-runtime-discovery` | Discovery | Identifica runtimes cloud, triggers, entradas, salidas, dependencias operativas y riesgos. |
| `integration-discovery` | Discovery | Identifica integraciones externas, APIs, webhooks, ETL/ELT, contratos y riesgos. |
| `git-sync-main` | Operativa | Ejecuta commit y push directo a `main` con revisión previa de cambios y confirmación humana. |

## Complementos

### Data Platform Discovery

| Complemento | Propósito |
|---|---|
| `bigquery.md` | Identifica proyectos, datasets, tablas, vistas, queries, scheduled queries, consumers y riesgos BigQuery. |
| `dbt.md` | Identifica estructura dbt, modelos, sources, tests, documentación, lineage y riesgos. |
| `lineage.md` | Reconstruye el flujo mínimo del dato desde origen hasta consumo final. |

### Cloud Runtime Discovery

| Complemento | Propósito |
|---|---|
| `cloud-functions.md` | Identifica Cloud Functions, triggers, entradas, salidas, dependencias y riesgos. |
| `cloud-run.md` | Identifica servicios/jobs Cloud Run, contenedores, invocaciones, contratos y riesgos. |
| `scheduler-pubsub.md` | Identifica Scheduler, Pub/Sub, topics, subscriptions, payloads y flujos de activación. |

### Integration Discovery

| Complemento | Propósito |
|---|---|
| `marketing-apis.md` | Identifica integraciones con Meta CAPI, Google Ads API, GA4 MP y otras APIs de marketing. |
| `webhooks.md` | Identifica webhooks, emisores, receptores, eventos, payloads, validaciones e idempotencia. |
| `etl-elt.md` | Identifica procesos ETL/ELT, fuentes, destinos, cargas, transformaciones, controles y riesgos. |

## Regla de reutilización

Las skills orquestadoras pueden utilizar otras skills cuando sea necesario.

Los complementos pertenecen a la skill que los agrupa, pero pueden ser referenciados por otras skills si el caso lo justifica.

## Regla de mantenimiento

Evitar duplicar una skill como complemento y como skill autónoma.

Si una capacidad crece y merece independencia, debe decidirse explícitamente qué versión queda como fuente canónica.


