# Copilot Instructions - JQF SDD Foundation

## Rol del repositorio

Este repositorio es una foundation reutilizable basada en SDD.

No contiene lógica de negocio ni proyectos concretos.

## Reglas obligatorias

- No añadir referencias a clientes o proyectos específicos.
- No introducir runtime, frameworks o tools reales.
- No crear agentes operativos concretos.
- Mantener los artefactos reutilizables.
- Respetar `sdd.instructions.md`.
- Respetar la precedencia documental.
- Priorizar plantillas, agentes metodológicos y governance.

## Cuando trabajes en este repo

- Si se crea un nuevo documento, debe ser reutilizable.
- Si se propone una regla, debe ser genérica.
- Si algo es específico de proyecto, debe ir a una plantilla o quedar fuera.
- Si hay duda, mantenerlo como placeholder o ejemplo genérico.

## Precedencia

1. Project Brief
2. `.github/instructions/sdd.instructions.md`
3. README.md
4. AGENTS.md
5. Templates
6. Skills
7. Docs auxiliares

## Contexto

Antes de generar o modificar artefactos relevantes del proyecto:

- comprobar si existe `docs/context_refs.md`;
- utilizarlo como mapa oficial de contexto;
- consultar las fuentes obligatorias indicadas en él;
- respetar las versiones y estados documentados;
- no inventar contexto de cliente, negocio, restricciones, arquitectura o decisiones si existe una fuente documentada.

Mantener esta sección breve y operativa.
