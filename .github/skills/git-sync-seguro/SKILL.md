# Skill - Git Sync Seguro

## Proposito

Guiar el proceso seguro de sincronizacion de cambios locales con GitHub mediante `git status`, `git add`, `git commit` y `git push`.

Esta skill se usa para subir cambios ya realizados en artefactos, documentacion, agentes, specs, gates, workflows, tests o codigo.

## Cuando usar esta skill

Usar esta skill cuando la solicitud sea similar a:

- "Sube los cambios a GitHub"
- "Haz commit y push"
- "Actualiza el repo"
- "Guarda los cambios en GitHub"
- "Publica estos artefactos"
- "Sincroniza el repositorio"
- "Prepara el commit"

## Principio general

No asumir que todos los cambios locales deben subirse.

Antes de commit o push, revisar:

- que archivos cambiaron;
- si los cambios son intencionales;
- si hay archivos sensibles o temporales;
- si los cambios pertenecen al mismo objetivo;
- si el commit debe ir a `main` o a una rama.

## Flujo operativo obligatorio

1. Revisar estado:
   - `git status --short`
   - opcional: `git status`
2. Revisar diffs:
   - `git diff`
   - `git diff --staged`
   - `git diff -- ruta/del/archivo`
3. Bloquear sensibles/no deseados y pedir decision explicita:
   - `.env`, `.env.*`, `*.key`, `*.pem`, `credentials.*`, `secrets.*`
   - `__pycache__/`, `.ipynb_checkpoints/`, `.DS_Store`, `node_modules/`, `.venv/`, `dist/`, `build/`, `*.log`
4. Agrupar cambios por intencion:
   - documentacion, agentes, specs, contracts transversales, skills, prompts, gates, evals, workflows, codigo, configuracion, mantenimiento.
5. Proponer archivos exactos a incluir:
   - preferir `git add ruta/archivo_1 ruta/archivo_2`
   - usar `git add .` solo si todo fue revisado y confirmado.
6. Proponer mensaje de commit:
   - formato: `type(scope): descripcion breve`
   - tipos recomendados: `docs`, `agent`, `spec`, `sdd`, `test`, `workflow`, `refactor`, `fix`, `chore`, `skill`
7. Confirmacion humana antes de commit (obligatoria).
8. Crear commit:
   - `git commit -m "type(scope): descripcion breve"`
9. Verificar rama/remoto y confirmar antes de push (obligatorio):
   - `git branch --show-current`
   - `git remote -v`
10. Subir cambios:
   - `git push`
   - o `git push -u origin nombre-rama` si la rama es nueva.
11. Verificar estado final:
   - `git status --short`

## Reglas para `main`

Commit/push directo a `main` solo si:

- repositorio personal o experimental;
- cambio pequeno;
- cambio principalmente documental;
- bajo riesgo operativo;
- confirmacion explicita del usuario.

Si el cambio es amplio o estructural, recomendar rama + PR.

## Cuando recomendar rama

Recomendar rama si:

- se modifican varios artefactos importantes;
- se anade una nueva capacidad;
- se modifica `.github/`;
- se cambia estructura del repo;
- se actualizan gates o workflows;
- hay riesgo de contradiccion documental;
- conviene revision por PR.

Formato sugerido:

- `tipo/descripcion-corta`

## Criterios de bloqueo

Detener el flujo si:

- aparecen secretos o credenciales;
- hay archivos temporales no deseados;
- hay eliminaciones inesperadas;
- hay demasiados archivos modificados sin explicacion;
- se mezclan cambios no relacionados;
- rama local/remota desincronizada con conflictos;
- no hay confirmacion explicita para commit o push;
- el cambio contradice la fase SDD actual.

## Regla SDD y gobernanza

Esta skill es operativa y transversal.

No sustituye specs ni contracts transversales.

No habilita Development por defecto.

Debe respetar que el repositorio sigue en `Specification / Structure` salvo autorizacion explicita.

## Definition of Done

La sincronizacion se considera completa cuando:

- los cambios fueron revisados;
- los archivos incluidos son intencionales;
- no se incluyeron secretos ni temporales;
- el commit tiene mensaje claro;
- commit y push se ejecutaron con confirmacion humana;
- el remoto contiene los cambios esperados;
- el estado final queda limpio o explicado.

## Complementos

- Esta skill no tiene complementos definidos actualmente.
