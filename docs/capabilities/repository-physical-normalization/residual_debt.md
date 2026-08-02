# Residual Debt - Repository Physical Normalization

## Estado

| Campo | Valor |
| --- | --- |
| Capacidad | Repository Physical Normalization |
| Estado | Residual debt accepted for closure |
| Ultima actualizacion | 2026-08-02 |
| Development adicional | NOT AUTHORIZED |

---

## Deuda residual aceptada

| ID | Deuda | Estado | Impacto | Mitigacion |
| --- | --- | --- | --- | --- |
| RD-RPN-001 | Stubs root temporales permanecen en el repositorio. | Accepted | Mantiene superficie legacy hasta retirada futura. | Declarados no normativos y apuntando a rutas canonicas. |
| RD-RPN-002 | Referencias historicas en capacidades cerradas pueden seguir apuntando a rutas root. | Accepted | Si se retiran stubs sin auditoria, pueden romper navegacion historica. | Mantener stubs hasta reentrada gobernada. |
| RD-RPN-003 | Impacto en repositorios derivados no auditado para retirada de stubs. | Accepted | Derivados pueden depender de rutas legacy. | Requiere analisis de impacto antes de retirada. |
| RD-RPN-004 | Baseline global todavia no declara una politica automatica de expiracion de stubs. | Accepted | La vida util de stubs queda gobernada manualmente. | Reentrada futura puede definir politica. |

---

## Punto de reentrada para retirada futura de stubs

La retirada futura de cualquier `Temporary compatibility stub` requiere una nueva decision/gate y debe incluir, como minimo:

1. Auditoria de referencias activas con `rg` u otra herramienta equivalente.
2. Clasificacion de referencias activas, historicas y externas conocidas.
3. Analisis de impacto en proyectos derivados.
4. Movement/Removal Plan especifico.
5. Compatibility Plan actualizado.
6. Rollback Plan actualizado.
7. Reviewer Agent.
8. QA Gate Agent.
9. Autorizacion humana explicita.

---

## Fuera de alcance actual

- Eliminar stubs.
- Ejecutar nuevos movimientos.
- Modificar contenido normativo de SDD Modes.
- Autorizar Development adicional.
- Iniciar Project Initializer.
- Iniciar Derived Repository Upgrade and Migration.

---

## Estado para cierre

La deuda residual no bloquea el Closure Gate global porque esta documentada, mitigada mediante stubs no normativos y su reentrada futura esta definida.