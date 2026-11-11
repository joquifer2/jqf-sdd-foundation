---
name: git-sync-main
description: Sincronización excepcional directa a main, solo con autorización explícita aplicable y verificaciones de integración.
id: SDD-SKILL-005
user-invocable: true
disable-model-invocation: false
---

# Skill - Git Sync Main

## Propósito

Ejecutar una sincronización directa de los cambios locales con GitHub haciendo commit y push a la rama `main`.

Esta skill es una excepcion al [protocolo canonico de integracion y cierre](../../instructions/sdd.instructions.md#13-protocolo-de-integracion-y-cierre-de-desarrollos). Solo se usa con autorizacion explicita de commit y push directo a main para el incremento. La PR sigue siendo el mecanismo ordinario; una solicitud generica de guardar, sincronizar o publicar no autoriza esta excepcion.

## Cuándo usar esta skill

Usar esta skill cuando el mandato cubra expresamente el destino directo a main, por ejemplo:

- "Publica los cambios en main"
- "Haz commit y push a main"

Verificar la autorizacion vigente sin solicitar de nuevo permisos ya concedidos. Si el mandato solo cubre una PR, continuar por ese flujo; no convertirlo en publicacion directa.

## Reglas

- El unico destino de esta excepcion es `main` y debe estar expresamente autorizado.
- No crear ramas.
- No abrir PR.
- No hacer rebase.
- No modificar archivos.
- No incluir archivos sensibles o temporales.
- No hacer push si no hay cambios.
- No ejecutar esta skill si la rama actual no es `main`; usar el flujo de PR aplicable sin cambiar de rama sobre trabajo pendiente.
- No eludir protecciones ni modificar configuracion; si el repositorio exige PR, usarla.
- No usar force push ni incorporar cambios ajenos. Las incidencias independientes se tratan segun el protocolo, sin reparaciones automaticas.

## Flujo operativo

1. Identificar incremento y autorizacion de commit/push directo. Comprobar remoto canonico, PRs relevantes, dependencias, worktrees y operaciones Git pendientes conforme al protocolo. Verificar rama actual:

   ```bash
   git branch --show-current
   ```

2. Si la rama actual no es `main`, detenerse e informar.

3. Revisar cambios pendientes:

   ```bash
   git status --short
   ```

4. Si no hay cambios, detenerse e informar.

5. Comprobar que no hay archivos sensibles o temporales evidentes.

   Bloquear si aparecen patrones como:

   - `.env`
   - `.env.*`
   - `*.key`
   - `*.pem`
   - `credentials.*`
   - `secrets.*`
   - `__pycache__/`
   - `.ipynb_checkpoints/`
   - `.DS_Store`
   - `node_modules/`
   - `.venv/`
   - `dist/`
   - `build/`
   - `*.log`

6. Verificar que HEAD de main local coincide con main remoto consultado ahora, por ejemplo mediante `git ls-remote origin refs/heads/main`; no confiar solo en origin/main local. Si difiere, detener esta publicacion y evaluar la integracion sin resetear ni rebasar automaticamente el trabajo pendiente. Revisar alcance, privacidad y checks proporcionales del incremento. Añadir exclusivamente las rutas revisadas y autorizadas:

   ```bash
   git add -- <rutas-autorizadas>
   ```

   Revisar `git diff --cached` y `git diff --cached --check`; no incluir entradas previas del indice que pertenezcan a otra unidad.

7. Crear commit.

   Mensaje por defecto:

   ```text
   chore(sync): update repository
   ```

   Si el usuario proporciona un mensaje, usar el mensaje del usuario.

8. Reconsultar main remoto y confirmar que sigue siendo la base comprobada. Si ha cambiado, detener el push y evaluar impacto. Subir sin forzar:

   ```bash
   git push origin main
   ```

9. Verificar que main remoto contiene el commit publicado y los cambios esperados; aplicar la evidencia minima del protocolo, declarando PR no aplicable por excepcion autorizada. Verificar estado local:

   ```bash
   git status --short
   ```

## Comandos base

```bash
git branch --show-current
git status --short
git add -- <rutas-autorizadas>
git diff --cached
git diff --cached --check
git commit -m "chore(sync): update repository"
git push origin main
git status --short
```

## Criterios de bloqueo

Detener el flujo si:

- la rama actual no es `main`;
- no hay cambios pendientes;
- aparecen archivos sensibles;
- aparecen archivos temporales evidentes;
- falta autorizacion directa o una proteccion exige PR;
- la base remota no esta verificada o ha cambiado sin contraste suficiente;
- hay cambios ajenos, conflicto funcional o validacion material pendiente;
- el commit falla;
- el push falla.

## Definition of Done

La sincronización se considera completa cuando:

- los cambios locales fueron añadidos;
- se creó un commit;
- el commit fue enviado a `origin/main`;
- main remoto y contenido integrado se verificaron, con evidencia y excepcion de PR registradas;
- `git status --short` queda limpio o explicado.

Este resultado solo acredita cierre tecnico del incremento; no concede cierre SDD, release ni limpieza de ramas, worktrees o evidencia.

## Complementos

Esta skill no tiene complementos definidos actualmente.
