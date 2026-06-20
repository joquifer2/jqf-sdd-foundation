# Skills Index

## Proposito

Este indice documenta las skills disponibles en el repositorio y la convencion para complementar una skill con modulos especializados.

## Convencion de estructura

Cada skill debe vivir en su propia carpeta:

` .github/skills/<skill-id>/SKILL.md `

Si una skill requiere modulos adicionales, usar:

` .github/skills/<skill-id>/complements/<complement-name>.md `

Dentro de `SKILL.md`, incluir una seccion `## Complementos` con la lista de complementos disponibles.

Si no hay complementos, declarar explicitamente:

- Esta skill no tiene complementos definidos actualmente.

## Skills actuales

- git-sync-seguro
  - skill: .github/skills/git-sync-seguro/SKILL.md
  - complementos: ninguno

- legacy-to-sdd
  - skill: .github/skills/legacy-to-sdd/SKILL.md
  - complementos: ninguno

- data-platform-discovery
  - skill: .github/skills/data-platform-discovery/SKILL.md
  - complementos:
    - .github/skills/data-platform-discovery/complements/bigquery.md
    - .github/skills/data-platform-discovery/complements/dbt.md
    - .github/skills/data-platform-discovery/complements/lineage.md

- cloud-runtime-discovery
  - skill: .github/skills/cloud-runtime-discovery/SKILL.md
  - complementos:
    - .github/skills/cloud-runtime-discovery/complements/cloud-functions.md
    - .github/skills/cloud-runtime-discovery/complements/cloud-run.md
    - .github/skills/cloud-runtime-discovery/complements/scheduler-pubsub.md

- integration-discovery
  - skill: .github/skills/integration-discovery/SKILL.md
  - complementos:
    - .github/skills/integration-discovery/complements/marketing-apis.md
    - .github/skills/integration-discovery/complements/webhooks.md
    - .github/skills/integration-discovery/complements/etl-elt.md