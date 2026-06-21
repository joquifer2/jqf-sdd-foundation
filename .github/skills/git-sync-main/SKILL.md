---
name: git-sync-main
description: Esta skill ejecuta commit y push directo a main con revisión previa de cambios y confirmación humana.
id: SDD-SKILL-005
user-invocable: true
disable-model-invocation: false
---

# Skill - Git Sync Main

## Propósito

Ejecutar una sincronización directa de los cambios locales con GitHub haciendo commit y push a la rama `main`.

Esta skill se usa cuando el usuario quiere guardar y publicar cambios ya realizados en el repositorio sin abrir una rama ni preparar una PR.

## Cuándo usar esta skill

Usar esta skill cuando la solicitud sea similar a:

- "Haz commit y push"
- "Sube los cambios a GitHub"
- "Publica los cambios en main"
- "Guarda los cambios en GitHub"
- "Sincroniza el repositorio"
- "Haz commit y push a main"

## Reglas

- El destino por defecto es `main`.
- No crear ramas.
- No abrir PR.
- No hacer rebase.
- No modificar archivos.
- No incluir archivos sensibles o temporales.
- No hacer push si no hay cambios.
- No hacer push si la rama actual no es `main`, salvo que el usuario lo autorice explícitamente.

## Flujo operativo

1. Verificar rama actual:

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

6. Añadir cambios:

   ```bash
   git add .
   ```

7. Crear commit.

   Mensaje por defecto:

   ```text
   chore(sync): update repository
   ```

   Si el usuario proporciona un mensaje, usar el mensaje del usuario.

8. Subir cambios a GitHub:

   ```bash
   git push origin main
   ```

9. Verificar estado final:

   ```bash
   git status --short
   ```

## Comandos base

```bash
git branch --show-current
git status --short
git add .
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
- el commit falla;
- el push falla.

## Definition of Done

La sincronización se considera completa cuando:

- los cambios locales fueron añadidos;
- se creó un commit;
- el commit fue enviado a `origin/main`;
- `git status --short` queda limpio o explicado.

## Complementos

Esta skill no tiene complementos definidos actualmente.
