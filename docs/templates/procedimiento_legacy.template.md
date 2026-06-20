# Procedimiento para utilizar jqf-sdd-foundation en un proyecto Legacy con GitHub Copilot

## Objetivo

Incorporar un proyecto ya existente al ecosistema SDD utilizando `jqf-sdd-foundation` como fuente única de metodología, agentes, skills y plantillas, sin duplicar contenido.

---

# Paso 1 — Añadir la Foundation como submódulo

Desde la raíz del proyecto legacy:

```bash
git submodule add https://github.com/joquifer2/jqf-sdd-foundation.git .sdd/jqf-sdd-foundation

git submodule update --init --recursive

git add .gitmodules .sdd/jqf-sdd-foundation

git commit -m "Add jqf-sdd-foundation submodule"
```

Verificar estructura:

```text
proyecto-legacy/
├── .sdd/
│   └── jqf-sdd-foundation/
└── ...
```

---

# Paso 2 — Crear bootstrap SDD local

Crear estructura mínima:

```bash
mkdir -p .github/agents
mkdir -p .github/instructions
mkdir -p docs
```

---

# Paso 3 — Crear AGENTS.md

Archivo:

```text
AGENTS.md
```

Contenido:

```markdown
# AGENTS.md

Este proyecto utiliza jqf-sdd-foundation como fuente metodológica SDD.

Foundation:

.sdd/jqf-sdd-foundation

Este proyecto es un proyecto existente y debe tratarse inicialmente como Brownfield o Legacy.

Antes de proponer cambios:

- reconstruir el estado As-Is;
- identificar artefactos SDD existentes;
- identificar artefactos SDD faltantes;
- evaluar readiness SDD.

Agente principal:

.sdd/jqf-sdd-foundation/.github/agents/legacy-to-sdd.agent.md

Skills principales:

.sdd/jqf-sdd-foundation/.github/skills/legacy-to-sdd/SKILL.md

.sdd/jqf-sdd-foundation/.github/skills/data-platform-discovery/SKILL.md

.sdd/jqf-sdd-foundation/.github/skills/cloud-runtime-discovery/SKILL.md
```

---

# Paso 4 — Crear copilot-instructions.md

Archivo:

```text
.github/copilot-instructions.md
```

Contenido:

```markdown
# Copilot Instructions

Este proyecto utiliza jqf-sdd-foundation como referencia metodológica.

Foundation:

.sdd/jqf-sdd-foundation

Antes de crear código, arquitectura, tareas o documentación:

1. Revisar AGENTS.md.
2. Utilizar Legacy to SDD Agent.
3. Utilizar Legacy to SDD Skill.
4. Aplicar Data Platform Discovery cuando existan plataformas de datos.
5. Aplicar Cloud Runtime Discovery cuando existan runtimes cloud.
6. Reconstruir el estado As-Is antes de proponer cambios.
7. No asumir información no verificable.
8. Marcar UNKNOWN cuando falte evidencia.
```

---

# Paso 5 — Crear agente personalizado en Copilot

Abrir Copilot Chat.

Ejecutar:

```text
/create-agent
```

Nombre:

```text
Legacy to SDD Agent
```

Descripción:

```text
Analiza proyectos existentes y los prepara para continuar evolucionando bajo metodología SDD mediante la reconstrucción del conocimiento mínimo necesario.
```

System Prompt:

```text
Eres el Legacy to SDD Agent.

Tu misión es incorporar proyectos existentes al ciclo SDD mediante la reconstrucción del conocimiento mínimo necesario para permitir su evolución controlada.

Utiliza como fuente metodológica:

.sdd/jqf-sdd-foundation

Debes apoyarte especialmente en:

.sdd/jqf-sdd-foundation/.github/skills/legacy-to-sdd/SKILL.md

Cuando proceda, utiliza también:

.sdd/jqf-sdd-foundation/.github/skills/data-platform-discovery/SKILL.md

.sdd/jqf-sdd-foundation/.github/skills/cloud-runtime-discovery/SKILL.md

No implementes cambios.

No diseñes arquitectura To-Be.

No generes tareas de desarrollo.

Prioriza evidencia sobre inferencias.

Reconstruye únicamente el conocimiento necesario para continuar bajo SDD.

Determina:

- qué existe actualmente;
- qué artefactos SDD existen;
- qué artefactos SDD faltan;
- qué riesgos existen;
- qué documentación mínima debe crearse;
- qué agente debe intervenir después.
```

---

# Paso 6 — Ejecutar el primer análisis

Abrir Copilot Chat.

Seleccionar:

```text
Legacy to SDD Agent
```

Prompt inicial:

```text
Analiza este repositorio utilizando Legacy to SDD.

Clasifica:

- repository_type
- project_type

Identifica:

- artefactos SDD existentes
- artefactos SDD faltantes
- componentes principales
- riesgos de evolución
- documentación mínima necesaria

Utiliza las skills de jqf-sdd-foundation cuando sea necesario.

No propongas implementación.

Genera un assessment inicial de readiness SDD.
```

---

# Flujo esperado

```text
Proyecto Legacy
        ↓
Legacy to SDD Agent
        ↓
Legacy to SDD Skill
        ↓
Data Platform Discovery
        ↓
Cloud Runtime Discovery
        ↓
Assessment SDD
        ↓
Specification Agent
        ↓
Architect Agent
        ↓
Tasks Planner Agent
```

---

# Mantenimiento del submódulo

## Actualizar la Foundation dentro del proyecto

Cuando la Foundation publique nuevos agentes, skills o plantillas:

```bash
git submodule update --remote .sdd/jqf-sdd-foundation
git add .sdd/jqf-sdd-foundation
git commit -m "Update jqf-sdd-foundation submodule"
```

## Clonar un proyecto que ya tiene el submódulo

```bash
git clone --recurse-submodules URL_DEL_PROYECTO
```

## Si ya clonaste el proyecto sin submódulos

```bash
git submodule update --init --recursive
```
