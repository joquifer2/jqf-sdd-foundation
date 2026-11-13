# SDD instructions - jqf-sdd-foundation

## 1. Objetivo de estas instrucciones

Asegurar que el trabajo se mantiene en la metodologia SDD y respeta el plan aprobado del proyecto.

Estas instrucciones aplican a todo trabajo en repositorios basados en jqf-sdd-foundation hasta que se autorice expresamente el paso a Development.

## 2. Estado actual

Estado vigente:

- SDD -> Specification / Structure / Documentation Governance.

No estamos en Development.

## 3. Reglas SDD por fase

### 3.1 Specification

Permitido:

- definir alcance;
- definir limites;
- definir taxonomias;
- definir inputs y outputs dentro de la spec;
- definir restricciones y reglas de gobierno dentro de la spec;
- definir riesgos;
- definir criterios de salida de fase.

No permitido:

- implementar runtime;
- crear codigo de agentes;
- elegir framework;
- crear tools reales;
- crear workflows ejecutables.

### 3.2 Structure

Permitido:

- crear estructura de carpetas minima;
- crear archivos base de instrucciones, prompts y specs;
- normalizar naming y precedencia documental;
- preparar esqueletos no ejecutables.

No permitido:

- convertir estructura en implementacion tecnica;
- introducir automatizacion operativa;
- construir arquitectura distribuida.

### 3.3 Development

Solo permitido cuando exista aprobacion explicita y checklist de salida completado.

Hasta ese momento, cualquier implementacion queda fuera de alcance.

### 3.4 Consolidation

Permitido:

- clasificar baseline canonico, expediente historico, evidencia, deuda residual y puntos de reentrada;
- preparar handover formal de cierre;
- actualizar indices documentales y referencias cuando este autorizado;
- registrar condiciones, gates y aprobaciones finales.

No permitido:

- autorizar Development;
- crear runtime, scripts, tools o workflows ejecutables;
- eliminar evidencia;
- ocultar deuda residual;
- modificar artefactos cerrados sin decision humana explicita.

### 3.5 Closed

Estado final de una capacidad cerrada. Debe conservar baseline vigente, expediente historico, deuda residual y puntos de reentrada cuando existan.

`Closed` no significa ausencia de deuda; significa que la deuda aceptada queda documentada y gobernada.

## 4. Comportamiento esperado durante Specification

- priorizar claridad de spec sobre soluciones tecnicas;
- mantener separación respecto a la Source of Truth funcional del proyecto;
- no duplicar logica funcional;
- no crear decisiones tecnologicas definitivas;
- marcar pendientes y riesgos cuando falte validacion.

Reglas de simplificacion documental:

- antes de crear un nuevo tipo de artefacto, comprobar si puede resolverse como seccion de una spec existente;
- no crear contracts separados salvo que sean transversales a varias capacidades o a todo el repositorio.

### Organización de artefactos desde el origen

En todas las fases SDD, antes de crear o modificar artefactos, el agente debe identificar y reutilizar las estructuras, ubicaciones canónicas y convenciones de nomenclatura vigentes del repositorio y de la metodología aplicable.

Los archivos nuevos deben ubicarse directamente en sus destinos previstos. Evitar duplicidades, documentación dispersa, archivos temporales persistentes y elementos innecesarios en los directorios raíz. La organización documental forma parte de la calidad y verificación del incremento; las desviaciones ordinarias deben corregirse autónomamente dentro del mandato autorizado, sin diferir su limpieza a una consolidación posterior.

Esta regla no altera precedencia documental, gates ni restricciones de fase. Los cambios materiales de arquitectura documental, movimientos destructivos y operaciones fuera del mandato requieren la autorización correspondiente. Las estructuras y verificaciones concretas pertenecen a cada repositorio o capacidad propietaria; no se impone una estructura universal.

## 5. Restricciones actuales obligatorias

No hacer todavia:

- seleccion de framework;
- runtime;
- multiagente complejo;
- tools reales;
- workflows automaticos;
- codigo ejecutable de agentes.

## 6. Regla de control de alcance

Si una propuesta entra en implementacion, debe detenerse y volver a:

- spec;
- limites;
- evidencia documental;
- criterio de fase.

## 7. Criterio de cumplimiento

Estas instrucciones se consideran cumplidas cuando:

- el trabajo producido es documental;
- respeta el plan aprobado;
- mantiene estado Specification / Structure / Documentation Governance, o una fase posterior autorizada;
- no introduce implementacion prematura.

## 8. SDD Modes

`SDD Mode` es la declaracion de intensidad metodologica proporcional definida por `SPEC-001 - SDD Modes`.

La capacidad se denomina `SDD Modes` y los modos oficiales iniciales son:

- `SDD Minimal`;
- `SDD Lite`;
- `SDD Full`.

La fuente canonica inicial para declarar y justificar el `SDD Mode` de un proyecto es el `Project Brief`.

La declaracion debe incluir, como minimo:

- modo seleccionado;
- justificacion humana;
- owner;
- fecha;
- condiciones relevantes de riesgo;
- disparadores de reevaluacion.

`docs/context_refs.md` puede indexar fuentes y referencias relacionadas con SDD Modes, pero no es fuente normativa del modo declarado.

Los proyectos sin `SDD Mode` declarado quedan temporalmente en estado `Undeclared`.

`Undeclared` no es un cuarto modo. Antes de iniciar un incremento material debe declararse el modo con juicio humano proporcional. Hasta entonces se conservan los controles criticos exigibles por el riesgo conocido, sin imponer automaticamente toda la carga de `SDD Full`.

El modo declarado afecta a:

- carga documental esperada;
- intensidad de checks;
- necesidad y cadencia de gates;
- consolidacion de evidencia;
- handover de cierre, cuando aplique;
- criterios de escalado o reevaluacion;
- contexto que deben cargar los agentes metodologicos.

El modo declarado no puede:

- eliminar validacion humana relevante;
- sustituir gates requeridos por riesgo, fase o cambio de alcance;
- debilitar controles criticos de seguridad, privacidad, cumplimiento, produccion, integraciones o impacto operacional;
- crear variantes duplicadas de agentes por modo;
- introducir runtime, herramientas, workflows ejecutables o logica de negocio.

`SDD Minimal` solo puede usarse para exploracion, pruebas internas o cambios documentales/acotados de bajo riesgo. No puede usarse cuando existan datos sensibles, exposicion a produccion, obligaciones de cumplimiento, integraciones criticas, impacto operacional alto, riesgos relevantes de seguridad o privacidad, multiples stakeholders criticos o baja reversibilidad.

`SDD Lite` es el modo ordinario para capacidades, productos e integraciones de riesgo suficientemente controlado, aunque exista complejidad tecnica o uso en produccion. Reduce artefactos, revisiones y gates por microtarea, manteniendo trazabilidad suficiente, checks proporcionales, gates aplicables y validacion humana relevante.

`SDD Full` equivale al baseline completo de `jqf-sdd-foundation` y se reserva para riesgo material elevado que requiera gobierno reforzado. Produccion, sensibilidad, complejidad o numero de integraciones no activan Full automaticamente. Se consideran impacto, probabilidad, reversibilidad, exposicion, obligaciones y mitigaciones; los controles criticos se mantienen en cualquier modo. Cuando el riesgo se concentra en una operacion, se refuerza esa operacion sin elevar necesariamente todo el proyecto.

La reduccion documental solo es valida si elimina baja senal o duplicacion. No puede eliminar decisiones canonicas, justificacion humana del modo, riesgos criticos, gates requeridos, criterios de aceptacion, evidencia de checks ni trazabilidad minima.

La validacion de `SDD Full` debe demostrar que no se debilita el baseline vigente de gobierno: artefactos requeridos por fase, revisiones formales, gates aplicables, evidencia de decisiones/riesgos/criterios/validacion, precedencia documental y aprobacion humana.

La seleccion del modo debe basarse en juicio humano documentado, no en scoring automatico.

Dentro del mandato autorizado, el agente puede planificar, ejecutar, verificar, corregir incidencias ordinarias y reintentar el objetivo sin autorizaciones intermedias por microtarea. Escala decisiones de negocio, cambios materiales de alcance, riesgos no cubiertos y operaciones que requieran autorizacion especifica. La supervision se centra en resultados y excepciones, sin repetir QA suficiente.

La unidad normativa general para alcance, tareas, checks, evidencia y gates es `incremento gobernado`.

`Implementation Wave` queda reservado como etiqueta opcional para incrementos de ejecucion dentro de Development; no es el concepto normativo principal de SDD Modes.

## 9. Technical State Persistence & Publication

La persistencia del estado tecnico se gobierna sobre la unidad normativa `incremento gobernado`.

Principio: **persistir por significado y publicar por necesidad de recuperabilidad o sincronizacion; nunca por frecuencia temporal ni por numero de cambios**.

Estados de persistencia:

- `Working State`: trabajo en curso que puede permanecer local;
- `Validated Increment`: incremento coherente y suficientemente validado para su fase, riesgo y `SDD Mode`;
- `Committed Checkpoint`: `Validated Increment` persistido en Git porque aporta valor de recuperabilidad o trazabilidad;
- `Remotely Recoverable State`: `Committed Checkpoint` publicado y razonablemente recuperable por otra superficie o participante autorizado.

Evaluar si procede un `Committed Checkpoint` cuando:

- se complete una unidad coherente y suficientemente validada;
- vaya a iniciarse una unidad materialmente distinta;
- un gate, handoff o transicion haga relevante la recuperabilidad del estado.

Un gate es un punto de evaluacion, no un trigger automatico de commit. No crear checkpoints redundantes cuando el estado relevante ya este suficientemente persistido.

Evaluar push o sincronizacion de forma independiente al commit. Considerarlo cuando otra superficie o participante necesite recuperar el checkpoint remoto para supervision, handoff, colaboracion o continuacion del trabajo.

En routing hibrido, si ChatGPT u otra superficie depende del repositorio remoto, la vigencia del estado remoto forma parte explicita de la decision de publicacion.

La necesidad de observabilidad remota no justifica persistir ni publicar trabajo incoherente o insuficientemente validado.

`commit ≠ push ≠ PR ≠ release`.

`SDD Minimal`, `SDD Lite` y `SDD Full` comparten esta misma politica. El modo solo ajusta proporcionalmente intensidad de validacion, checks y evidencia; no cambia la semantica de persistencia o publicacion.

La conclusion metodologica de que procede persistir o publicar no equivale a autorizacion para ejecutar commit o push. Deben respetarse siempre las autorizaciones vigentes de la superficie, agente o decision humana aplicable.

Esta politica de persistencia no define por si misma branching, PR, releases, CI/CD, convenciones de mensajes de commit ni automatizacion. El protocolo complementario de integracion y cierre tecnico se define en la seccion 13.

## 10. Backlog Governance

`docs/tasks.md` es un artefacto auxiliar de gobernanza.

No sustituye:

- specs;
- contracts transversales;
- skills;
- prompts;
- gates;
- evals.

Toda tarea registrada debe estar vinculada a:

- una fase SDD;
- un artefacto;
- una decision relevante;
- una futura linea de trabajo.

Las tareas deben representar trabajo significativo.

No deben representar actividad diaria.

Antes de crear nuevas tareas, comprobar si ya existe una tarea equivalente.

Antes de marcar una tarea como completada, verificar que el criterio de cierre se ha cumplido.

Si una tarea pierde relevancia o deja de aplicar, debe marcarse como descartada en lugar de eliminarse silenciosamente.

## 11. Context Governance

`docs/context_refs.md` actúa como el mapa oficial de referencias de contexto del proyecto.

- Antes de crear o modificar cualquiera de los siguientes artefactos, revisar `docs/context_refs.md`:
	- Project Brief
	- Specifications
	- Architecture
	- Tasks
	- Código
	- Documentación técnica

- Si `docs/context_refs.md` existe:
	- utilizarlo como fuente oficial de referencias;
	- consultar las "fuentes obligatorias" indicadas en él;
	- respetar las versiones y estados documentados;
	- no inferir ni sustituir contexto cuando exista una fuente oficial publicada.

- Si `docs/context_refs.md` NO existe:
	- crearlo a partir de `docs/templates/context_refs.template.md`;
	- marcar las referencias faltantes como `PENDING` hasta su verificación.

- `context_refs.md` no debe duplicar contenido completo de CCDs, decisiones, actas de reuniones o documentación externa. Su función es actuar como índice, trazabilidad y mecanismo de carga de contexto, no como repositorio de copias completas.

- Regla explícita: Antes de generar cualquier Project Brief, Specification, Architecture o Tasks, comprobar la existencia de `docs/context_refs.md` y actuar conforme a su contenido.

## 12. SDD Harness

### 12.1 Rol del SDD Harness

El SDD Harness es el sistema de gobierno que define cómo se diseñan, documentan, revisan, validan y evolucionan las capacidades en repositorios basados en jqf-sdd-foundation.

Su función es garantizar que todo trabajo siga un proceso controlado, trazable y verificable antes de llegar a una fase de implementación.

El SDD Harness no define lógica funcional de negocio, no implementa agentes y no gobierna runtime, herramientas o infraestructura técnica.

Su responsabilidad es gobernar el proceso SDD.

Principios fundamentales:

- Human in the Loop.
- No implementación prematura.
- Trazabilidad documental.
- Evolución controlada.
- Source of Truth funcional del proyecto.
- Separación entre diseño e implementación.

---

### 12.2 Agentes metodológicos

El SDD Harness utiliza agentes metodológicos especializados para gobernar la evolución del repositorio.

Actualmente existen:

- Specification Agent
- Architect Agent
- Tasks Planner Agent
- Reviewer Agent
- Documentation Agent
- QA Gate Agent
- Consolidation Agent
- Implementation Agent
- GitHub Workflow Agent

Estos agentes no representan capacidades funcionales de negocio.

Su función es asistir el proceso SDD, asegurar coherencia documental, mantener trazabilidad y reducir el riesgo de implementación prematura.

La definición completa de cada agente se encuentra en:

```text
.github/agents/
```

---

### 12.3 Artefactos por fase

#### Specification

Artefactos permitidos:

- Project Brief
- Specifications
- Taxonomías
- Glosarios
- Instrucciones SDD
- Definición de alcance
- Definición de límites
- Riesgos
- Criterios de salida

Artefactos no requeridos todavía:

- Runtime
- Código
- Herramientas reales
- Workflows ejecutables

#### Structure

Artefactos permitidos:

- AGENTS.md
- Skills
- Prompts
- Gates
- Evals
- Workflows documentales
- Estructura de carpetas
- Reglas de precedencia
- Convenciones de naming

Los artefactos creados en esta fase deben permanecer documentales y no ejecutables.

#### Development

Solo puede iniciarse cuando exista aprobación explícita y se hayan cumplido los criterios de salida de las fases anteriores.

#### Consolidation

Artefactos permitidos:

- Closure Handover
- Evidence Index
- Residual Debt Register
- Re-entry Index o seccion equivalente
- indices documentales de capacidades
- decisiones finales de baseline y cierre

Estos artefactos son documentales. No ejecutan cambios tecnicos ni sustituyen aprobacion humana.

#### Closed

Estado de una capacidad cerrada tras consolidacion y aprobacion. El contexto futuro debe cargarse desde el handover y los indices antes de abrir el expediente historico completo.

---

### 12.4 Gates

Los gates son puntos de control utilizados para determinar si una capacidad puede avanzar a la siguiente fase.

Su objetivo es impedir que el repositorio avance sin suficiente definición, evidencia o validación.

Un gate puede producir una de las siguientes decisiones:

- Pass
- Pass with conditions
- Fail
- Blocked

Un gate debe revisar, como mínimo:

- existencia de artefactos obligatorios;
- coherencia documental;
- trazabilidad;
- alineación con el estado SDD vigente;
- ausencia de implementación prematura.

Los gates nunca sustituyen la validación humana.

Gates documentales reservados para cierre de capacidades:

- `Consolidation Readiness Gate`: evalua si una capacidad puede entrar en Consolidation.
- `Closure Gate`: evalua si una capacidad puede pasar de Consolidation a Closed.

Ambos gates son conceptuales/documentales salvo que una fase futura autorice automatizacion explicita.

---

### 12.5 Precedencia documental

Cuando existan conflictos entre documentos, prevalece el artefacto de mayor nivel.

Orden de precedencia:

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

Ningún artefacto puede contradecir a otro situado por encima en esta jerarquía.

Si se detecta una contradicción, debe resolverse actualizando el artefacto de mayor precedencia o eliminando la inconsistencia en los artefactos inferiores.

---

### 12.6 Definition of Done del SDD Harness

Una capacidad puede considerarse suficientemente madura dentro del SDD Harness cuando:

- existe una specification aprobada;
- el alcance está definido;
- los límites están definidos;
- existe trazabilidad documental;
- los riesgos relevantes están identificados;
- la capacidad puede ser revisada objetivamente;
- no existen contradicciones documentales conocidas;
- se mantiene alineación con la fase SDD vigente.

Hasta que estos criterios se cumplan, la capacidad no debe considerarse lista para Development.

---

### 12.7 Relación con Harness Engineering

El ecosistema "Harness" describe un conjunto de capacidades y responsabilidades relacionadas con la gobernanza, la ingeniería de procesos y la operación de políticas.

- SDD Harness: gobierna el diseño, la especificación, la revisión y la trazabilidad documental de capacidades definidas bajo SDD.
- Governance Harness: añade reglas, contracts y procesos transversales que aseguran coherencia entre proyectos y prácticas organizativas.
- Operational Harness: se ocupa de la ejecución y operación (runtimes, integraciones y fluxos operativos) y queda fuera del alcance de esta foundation.

Este repositorio gobierna diseño, documentación y validación; no contiene runtime, herramientas operativas ni implementaciones técnicas. Las decisiones y artefactos de operación deben residir en el Operational Harness o en proyectos derivados.

## 13. Protocolo de integracion y cierre de desarrollos

### 13.1 Aplicacion y autonomia

Este protocolo transversal gobierna la integracion y el cierre tecnico de un `incremento gobernado`, incluidos los cambios documentales. No autoriza Development ni operaciones Git por si mismo. Complementa las secciones 8 y 9 y utiliza los agentes, artefactos y gates ya aplicables.

La PR es el mecanismo ordinario de integracion. El acceso directo a `main` requiere una excepcion expresamente autorizada para el incremento y compatible con las protecciones existentes; una peticion generica de guardar o publicar no concede esa excepcion.

El mandato puede delegar conjuntamente rama, worktree, commit, push, PR, actualizacion respecto a main, merge y limpieza, indicando las operaciones cubiertas, alcance, condiciones y limites. Cada permiso conserva su significado: publicar una PR no autoriza merge, y merge no autoriza limpieza. Dentro de esa delegacion, ejecutar y verificar sin confirmaciones por microtarea; elevar decisiones materiales, conflictos funcionales y operaciones no cubiertas.

`SDD Minimal`, `SDD Lite` y `SDD Full` comparten las reglas. Lite puede reunir evidencia en la PR o handoff existente; Full mantiene revisiones y gates exigibles por riesgo y fase mediante referencias a esa misma evidencia. No se crean gates universales, agentes o expedientes adicionales por rama.

### 13.2 Inicio y concurrencia

Antes de iniciar un incremento:

- Identificar mandato, fase, modo y autorizaciones; comprobar repositorio y remoto canonicos, rama, HEAD, indice, cambios locales y operaciones Git pendientes.
- Consultar el SHA vigente de `main` remoto y distinguirlo de `main` local y de referencias remotas locales que puedan estar desactualizadas. Consultar PRs abiertas relevantes, sus heads, dependencias y solapamientos de archivos o contratos.
- Usar una rama por unidad coherente de cambio. Cuando haya ejecuciones concurrentes sobre un mismo repositorio local, aislarlas con `git worktree` o un checkout independiente, con destino y rama identificados. No compartir el mismo arbol de trabajo entre desarrollos simultaneos.
- Preservar trabajo ajeno, incluidos archivos sin seguimiento e ignorados. No cambiar de rama, resetear, guardar en stash ni trasladar cambios ajenos automaticamente para obtener un estado limpio. Acordar secuencia o reparto ante archivos compartidos; el aislamiento fisico no elimina conflictos funcionales.

Si el remoto no es consultable, usar otra superficie autorizada de lectura. Si no puede verificarse una base material para la operacion, reportarla como no verificada y detener solo esa operacion.

### 13.3 Preparacion de integracion

La entrada a integracion requiere alcance exacto y sin cambios ajenos o informacion privada, dependencias satisfechas o secuencia aprobada, checks suficientes para el HEAD candidato, revisiones y gates aplicables y autorizacion de integracion verificable. Distinguir autocontrol, revision independiente, aceptacion humana y CI; ausencia de checks publicados no equivale a CI aprobada.

Contrastar el candidato con `main` remoto vigente: registrar ambos SHA y evaluar el impacto de cambios posteriores en archivos, contratos y dependencias. No exigir merge/rebase ni repetir pruebas validas cuando el contraste demuestra que siguen siendo suficientes y las reglas del repositorio no exigen actualizacion. Si hay impacto material, actualizar y revalidar lo afectado dentro del mandato. Un nuevo HEAD exige comprobar que revision, checks y autorizacion siguen cubriendo la delta; no heredar aprobaciones por inferencia.

- Conflicto mecanico: resolucion inequivoca que conserva comportamiento, contratos, decisiones y reservas. Puede corregirse y revalidarse autonomamente si el mandato lo cubre; su simplicidad textual no basta para clasificarlo.
- Conflicto funcional: requiere elegir comportamiento, contrato, alcance, riesgo o decision. Detener la integracion afectada y solicitar decision con evidencia. Ante duda material, tratarlo como funcional.

### 13.4 Integracion secuenciada

Integrar segun dependencias, una PR cada vez. Inmediatamente antes de cada merge, reconsultar `main`, HEAD y estado de la PR, comprobar que no hay conflictos sin resolver ni condiciones bloqueantes pendientes y que las validaciones y la autorizacion siguen siendo aplicables. Conservar las condiciones residuales aceptadas y su seguimiento. Si otra integracion cambia la base, reevaluar el impacto antes de continuar.

Usar un metodo habilitado por el repositorio y respetar protecciones, reviews y checks obligatorios, sin bypass ni cambios de configuracion. Vincular la ejecucion al HEAD revisado mediante el SHA esperado cuando la superficie lo permita. Un rechazo por cambio de HEAD requiere inspeccionar el nuevo estado antes de reintentar. Si la base cambia entre comprobacion y merge, contrastar el resultado contra la base efectivamente integrada y verificar lo afectado.

Solo ejecutar merge con autorizacion humana explicita o delegacion previa que cubra esa PR/incremento y sus condiciones. No interpretar fusionabilidad tecnica, acceso de escritura, un gate favorable o autorizaciones de otra unidad como permiso de merge.

### 13.5 Cierre y evidencia minima

El cierre tecnico requiere confirmar en GitHub el estado final de la PR y el commit resultante, comprobar que este pertenece a `main` y verificar el contenido integrado y los checks afectados. Con squash o rebase, comprobar la correspondencia con el cambio aprobado; no exigir que el SHA original de la rama sea ancestro. Un SHA de merge provisional en una PR abierta no acredita integracion.

Conservar en la PR, handoff o evidencia existente, sin duplicarlos: rama/PR, SHA candidato y base verificada, dependencias, fuente y alcance de autorizacion, checks y sus limites, main anterior/posterior, commit integrado, verificacion posterior, excepciones y proxima accion con responsable. Distinguir comprobaciones actuales de antecedentes. Si no se autoriza merge, entregar la PR y declarar integracion y cierre tecnico pendientes.

Foundation define estos requisitos operativos, pero el formato canonico de `Hybrid Handoff V1` pertenece a Professional OS. Transportar los hechos mediante sus campos vigentes y referencias; no crear aqui una variante ni modificar la SOP propietaria. El handoff no exige commits o publicaciones prematuros.

Distinguir:

- Cierre tecnico: integracion y resultado verificados para la unidad.
- Cierre SDD: decision de lifecycle con Consolidation, gates y aprobacion humana aplicables; no se obtiene automaticamente al fusionar una PR.
- Limpieza del entorno: operacion separada. Antes de eliminar ramas o worktrees, comprobar autorizacion, integracion o sustitucion, commits exclusivos, dependencias, procesos activos, cambios locales, archivos ignorados/sin seguimiento y evidencia unica. No forzar eliminaciones ni asumir que una PR cerrada preserva su contenido en main. Retener recursos y declarar seguimiento cuando falte alguna condicion; no bloquear automaticamente un cierre tecnico ya verificado.

Actualizar solo la documentacion necesaria para mantener el estado reconstruible; conservar reservas, evidencia y puntos de reentrada. No crear un documento de cierre por PR cuando el registro existente sea suficiente.

### 13.6 Excepciones y bloqueos proporcionales

| Situacion | Tratamiento |
| --- | --- |
| PR desactualizada o sin actividad | En la reentrada y antes del cierre del incremento, revisar vigencia del objetivo, base y delta pendiente; proponer actualizar, retener o cerrar con responsable y motivo. La antiguedad por si sola no autoriza cierre ni borrado. |
| Desarrollo sustituido | Identificar sucesor y diferencias residuales, verificar preservacion y proponer cierre autorizado de la PR anterior; no fusionar trabajo obsoleto para resolver su acumulacion. |
| Trabajo local pendiente o archivos concurrentes | Aislar y preservar; integrar exclusivamente el candidato revisado. Los cambios locales no incluidos no deben incorporarse como consecuencia del merge. |
| Integracion fallida o respuesta incierta | Consultar PR y main antes de reintentar para evitar duplicidad. Mantener resultado no confirmado hasta obtener evidencia. |
| Fallo posterior al merge | Registrar incidente, detener integraciones dependientes afectadas y proponer correccion o reversion con autorizacion aplicable; no reescribir historico ni declarar cierre satisfactorio con un fallo material abierto. |
| Incidencia general del entorno | Determinar su relacion con el contenido publicado, integridad de evidencia necesaria, requisitos vigentes y operacion prevista. Clasificar como `BLOCKING`, `NON_BLOCKING_WITH_FOLLOW_UP` o `RESOLVED`, con fundamento y seguimiento. |

Una ACL amplia o un worktree inconsistente no son bloqueos automaticos de una PR independiente. Comprobar alcance efectivo, dependencia y requisito aplicable: si comprometen materialmente el candidato o su evidencia exigible, detener lo afectado; si no, mantener el hallazgo y seguimiento sin convertir la integracion en reparacion general del entorno. Estar ignorado por Git no acredita privacidad y un hash coincidente no certifica custodia autorizada.

Las comprobaciones factuales pueden ejecutarse con herramientas ya autorizadas; el protocolo no instala automatizaciones, altera protecciones ni concede nuevas autorizaciones.
