# Copilot Instructions - JQF SDD Foundation

## 1. Propósito de este repositorio

Este repositorio proporciona una base reutilizable para proyectos construidos mediante Specification Driven Development (SDD).

Su función es definir:

* metodología SDD;
* gobernanza documental;
* agentes metodológicos;
* skills reutilizables;
* plantillas;
* reglas de trazabilidad;
* criterios de validación;
* convenciones de trabajo.

Este repositorio no contiene lógica funcional de negocio.

Este repositorio no contiene implementaciones productivas.

---

## 2. Relación con proyectos derivados

La Foundation no representa ningún proyecto concreto.

Su función es proporcionar una base común reutilizable.

Cada proyecto derivado deberá definir posteriormente:

* su Project Brief;
* su Source of Truth;
* sus Specifications;
* sus agentes operativos;
* sus workflows;
* sus herramientas;
* sus integraciones.

La Foundation no debe contener información específica de proyectos concretos.

---

## 3. Metodología SDD

Este repositorio evoluciona mediante Specification Driven Development (SDD).

Fases principales:

* Proposed
* Specification
* Structure
* Development
* Validation
* Active
* Deprecated

No se permite saltar fases sin validación explícita.

---

## 4. Relación con el SDD Harness

Estas instrucciones forman parte del SDD Harness.

Deben interpretarse conjuntamente con:

* Project Brief;
* SDD Instructions;
* Specifications;
* Gates;
* Skills;
* AGENTS.md;
* documentación auxiliar.

El objetivo es mantener coherencia documental, trazabilidad y evolución controlada.

---

## 5. Restricciones actuales

Mientras se trabaje en Specification o Structure:

No está permitido:

* implementar runtime;
* seleccionar frameworks definitivos;
* crear herramientas reales;
* crear integraciones reales;
* crear automatizaciones ejecutables;
* introducir código productivo.

---

## 6. Filosofía de diseño

Priorizar:

* claridad;
* simplicidad;
* trazabilidad;
* mantenibilidad;
* validación humana;
* evolución controlada.

Evitar:

* sobreingeniería;
* automatización prematura;
* complejidad innecesaria;
* decisiones tecnológicas irreversibles.

---

## 7. Precedencia documental

Cuando exista conflicto entre artefactos:

```text
Project Brief
↓
SDD Instructions
↓
Specifications
↓
Gates
↓
Skills
↓
Prompts
↓
Documentación auxiliar
```

Ningún artefacto de menor precedencia puede contradecir a uno de mayor precedencia.

---

## 8. Regla anti-sobreingeniería documental

Antes de crear un nuevo artefacto:

* comprobar si puede resolverse mediante una sección en un artefacto existente;
* evitar duplicación documental;
* evitar contracts innecesarios;
* priorizar simplicidad.

---

## 9. Objetivo de estas instrucciones

Garantizar que cualquier evolución de la Foundation siga los principios del SDD Harness y permanezca independiente de proyectos concretos.

