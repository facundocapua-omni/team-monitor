# Gestión de la Dirección DXP

Herramienta del Tech Director de Americas, que cumple de hecho la función de Global Tech Director, para conocer, asignar y hacer seguimiento de las personas de la Dirección DXP en ambas regiones. Los roles, niveles y tracks siguen el handbook del equipo (`../structure`).

## Organización

**Dirección DXP**:
El conjunto de personas de las dos Regiones (unas 150).
_Avoid_: equipo, área, departamento

**Región**:
Unidad organizativa de la Dirección encabezada por un Tech Director. Hay dos: **Americas** (~100 personas) y **EMEA** (~50). Es una separación solo organizativa: las reglas son las mismas en ambas.
_Avoid_: LATAM, zona, geografía

**Ubicación**:
El país y la ciudad donde vive y trabaja una persona. Es independiente de su Región: alguien que vive en España puede reportar a una línea de Americas.
_Avoid_: Región, sede

**Línea de reporte**:
La cadena jerárquica de la Dirección: Tech Director → Tech Manager → Tech Leader → Developer, más el Expert, que reporta al Tech Director sin gente a cargo. Hoy arranca en los dos Tech Directors; el handbook pone por encima un Global Tech Director. Cada persona tiene un solo manager y pertenece a la Región de su línea de reporte.
_Avoid_: organigrama, jerarquía

## Roles

**Rol**:
La posición de una persona en la Línea de reporte, de una lista cerrada que sale del handbook: Developer, Tech Leader, Tech Manager, Expert, Tech Director y Global Tech Director. Es distinto de su Seniority.
_Avoid_: puesto, cargo

**Global Tech Director**:
Responsable de toda la Dirección DXP. El puesto todavía no está formalizado: hoy cumple esa función el Tech Director de Americas, que es el usuario de la herramienta.

**Tech Director**:
Responsable de una Región; reporta al Global Tech Director.
_Avoid_: Regional Tech Director, Regional Director

**Expert**:
Autoridad técnica de una Región; reporta al Tech Director y no tiene gente a cargo.
_Avoid_: arquitecto

**Tech Manager**:
Gestiona a 3–6 Tech Leaders de su Región y decide las Asignaciones regionales.
_Avoid_: Technical Manager, TM

**Tech Leader**:
Lidera la entrega técnica de uno o más proyectos y gestiona a 3–5 Developers. Para el handbook es el nivel 8 de Seniority, pero alguien puede ocupar el Rol con una Seniority menor mientras se decide su ascenso.
_Avoid_: Technical Leader, TL, Tech Lead

**Developer**:
Contribuidor individual de un Track; reporta a un Tech Leader.
_Avoid_: IC, dev, ingeniero

## Perfil

**Persona**:
Alguien de la Dirección DXP registrado en la herramienta, identificado por su email corporativo.
_Avoid_: empleado, recurso, colaborador

**Vínculo**:
Si una persona es empleada de la empresa o externa (contratista de un proveedor o freelancer). Un externo tiene manager, Seniority equivalente y Track como cualquier Developer, y también se asigna a proyectos.
_Avoid_: tipo de contrato, modalidad

**Movimiento**:
Un hecho fechado en la historia de una persona: su Ingreso, su Baja, o un cambio de Rol, Seniority, Track o manager. Los Movimientos permiten reconstruir la Línea de reporte en cualquier fecha.
_Avoid_: cambio, evento

**Ingreso**:
La entrada de una persona a la Dirección (no a la empresa), con una fecha que puede ser futura. Quien vuelve después de una Baja tiene un nuevo Ingreso y sigue siendo la misma Persona.
_Avoid_: alta, contratación

**Baja**:
La salida de una persona de la Dirección, voluntaria o involuntaria, con una fecha que puede ser futura. La persona no se borra: queda inactiva.
_Avoid_: desvinculación, egreso

**Seniority**:
El nivel de un Developer o un Tech Leader en la escala compartida de 8 niveles: Trainee, Junior, Junior Advanced, Semi Senior, Semi Senior Advanced, Senior Level 1, Senior Level 2, Senior Level 3 (= Tech Leader). Del Tech Manager para arriba, y en el Expert, no hay Seniority: el Rol es el nivel.
_Avoid_: grade, career level, categoría

**Track**:
La disciplina de un Developer: Frontend, Backend, DevOps o QA. Cada Track tiene su roadmap y su career path.
_Avoid_: especialidad, disciplina, perfil

**Plataforma**:
Una de las seis tecnologías sobre las que trabaja la Dirección, tal como las documenta el handbook: Optimizely Cloud, Contentful, AEM EDS, AEM Traditional, Adobe Commerce PaaS y Adobe Commerce SaaS. Las cuatro primeras son CMS; las de Commerce, no.
_Avoid_: CMS, solución, tecnología

**Plataforma principal**:
La Plataforma en la que se especializa una persona; es la que cuenta en el headcount por Plataforma. Es obligatoria en Developers y Tech Leaders, y opcional en el resto. Las demás Plataformas que maneja forman parte de sus Skills.
_Avoid_: CMS principal, CMS actual

**Skill**:
Una Plataforma que maneja una Persona, con su Nivel de dominio y la fecha de su última revisión. La Plataforma principal también es una Skill. Cualquier Persona puede tener Skills, incluidos Experts, Tech Managers y externos. Vale solo la última revisión; la progresión de una persona es tema de su Plan de carrera.
_Avoid_: competencia, habilidad, conocimiento

**Nivel de dominio**:
Lo que una persona puede hacer en un Proyecto de una Plataforma: **Conoce** (apoya con la guía de otra persona), **Autónomo** (trabaja sola en un Proyecto de esa Plataforma) o **Referente** (lidera técnicamente o resuelve problemas a otros). Lo propone el manager directo y se revisa una vez al año, junto con la Evaluación de desempeño; si la revisión es más vieja, se ve vencida. Es independiente de la Seniority.
_Avoid_: nivel de skill, expertise

**Experiencia en Plataforma**:
Los meses que una persona lleva en Asignaciones confirmadas a Proyectos que declaran una Plataforma, con cualquier Función. Se calcula, no se carga. Es evidencia para quien propone y revisa el Nivel de dominio, y no lo cambia sola. Solo cuenta lo que está en la herramienta: lo anterior a la carga inicial no existe en el dato.
_Avoid_: años de experiencia, antigüedad en la tecnología

**Nivel de inglés**:
Nivel de una persona en la escala MCER (A1–C2), evaluado por el profesor de inglés interno. Vale la última evaluación; una persona sin evaluar no es lo mismo que una A1.
_Avoid_: English level, nivel de idioma

**Evaluación de desempeño**:
El resultado anual e individual del rendimiento de una persona empleada, que pone su manager directo. Su resultado es la Calificación final, de 1 a 5, y puede marcarla como Key player. Se conservan todas, cada una con su ciclo, y vale la última; si no es del ciclo más reciente, se ve como de un ciclo anterior. Una persona sin evaluar no es lo mismo que una con resultado bajo. Los externos no tienen: su líder les da feedback, que no se registra. En el staffing se muestra como un dato más, pero no entra en ningún orden ni filtro calculado: quien decide es el usuario.
_Avoid_: KPI, performance score, nota

**Calificación final**:
El resultado de una Evaluación de desempeño, de 1 a 5 con decimales. Es lo único que se guarda del cálculo: ni las competencias ni los componentes que la forman.
_Avoid_: nota, puntaje, score

**Key player**:
Marca que la Evaluación de desempeño de un ciclo pone a una persona considerada clave. Vale para ese ciclo, como la Calificación final.
_Avoid_: talento clave, high performer

**Delivery KPI**:
Una de las cinco métricas de entrega del handbook. Se mide por equipo y nunca se atribuye a un Developer; cuenta en la evaluación de Tech Leaders y Tech Managers.
_Avoid_: KPI de rendimiento, métrica individual

## Staffing

**Cliente**:
Para quién se hace un Proyecto. La propia empresa es un Cliente más, y sus proyectos son los internos.
_Avoid_: cuenta, account

**Proyecto**:
Trabajo para un Cliente que pertenece a una Región: la que lo vendió y lo gestiona, cuyo Tech Manager decide su staffing. La Región del Proyecto se carga y no cambia según quién lo lidere. Su Estado es Preventa, En curso, Cerrado o Perdido. Declara una o más Plataformas (obligatorio en los Proyectos En curso y en Preventa de Clientes externos; lo interno puede declarar "ninguna"). No tiene fechas propias: su duración es la de sus Asignaciones y Necesidades.
_Avoid_: cuenta, iniciativa

**Preventa**:
El Estado de un Proyecto que todavía no se ganó. Si se gana, el mismo Proyecto pasa a En curso con sus Necesidades y Asignaciones, que se confirman una por una. Si se pierde, sus Asignaciones tentativas y sus Necesidades abiertas se cierran.
_Avoid_: oportunidad, pipeline

**Facturable**:
Si el Cliente paga el tiempo de una Asignación. Cada Proyecto tiene un valor por defecto, y una Asignación puede no ser facturable dentro de un Proyecto facturable, por ejemplo en shadowing o en garantía.

**Asignación**:
La dedicación de una Persona a un Proyecto: un porcentaje fijo desde una fecha de inicio, con fecha de fin opcional. Si la dedicación cambia, termina esa Asignación y empieza otra. Es **Tentativa** (una reserva blanda) o **Confirmada**; en un Proyecto en Preventa solo puede ser Tentativa. Cualquier Rol puede tener Asignaciones, pero las de un Tech Manager, un Expert o un Tech Director se distinguen de las de Developers y Tech Leaders. Si la persona tiene una Baja, la parte de la Asignación posterior a esa fecha queda señalada y deja de contar.
_Avoid_: allocation, imputación

**Función**:
Lo que hace una persona en una Asignación, o lo que pide una Necesidad: Liderazgo técnico o Desarrollo. No depende del Rol: un Developer puede tener una Asignación de Liderazgo técnico, y la de un Tech Manager es un rescate.
_Avoid_: rol en el proyecto

**Asignación entre Regiones**:
La Asignación de una persona a un Proyecto de otra Región. Para el Dojo y la Utilización cuenta en la Región de la persona; para la demanda, en la del Proyecto.
_Avoid_: préstamo, cross-region

**Necesidad**:
Una posición que un Proyecto necesita cubrir con una sola persona: Función, Track, rango de Seniority, dedicación y fechas; opcionalmente, una Plataforma con su Nivel de dominio mínimo (Autónomo si no se indica), Nivel de inglés mínimo y Países admitidos. Siempre pertenece a un Proyecto. Está Abierta, Cubierta (por la Asignación que la cubre, tentativa o confirmada) o Cancelada. Puede cubrirse con alguien de la Dirección o con una contratación.
_Avoid_: vacante, posición abierta, requerimiento

**Capacidad**:
La dedicación que una persona puede dar a Asignaciones en una fecha: 100% menos sus Indisponibilidades. Si sus Asignaciones confirmadas la superan, la persona está sobreasignada; eso se muestra, no se bloquea.
_Avoid_: disponibilidad, horas

**Indisponibilidad**:
Un periodo en el que una persona tiene menos Capacidad, con fecha de inicio, fin opcional y un porcentaje. Cubre licencias, jornadas reducidas y externos a tiempo parcial. Nunca registra el motivo, que suele ser de salud o de familia.
_Avoid_: ausencia, licencia, vacaciones

**Dojo**:
La parte de la Capacidad de un Developer o un Tech Leader que no ocupa ninguna Asignación confirmada. Ellos son quienes pueden ser facturables, sin excepciones: Trainees, recién ingresados y externos incluidos. Nadie entra al Dojo: se está en él mientras haya Capacidad sin asignar. La que ocupan las Asignaciones tentativas se muestra aparte, como reservada. Un proyecto interno o el shadowing no son Dojo: se ven en la Utilización.
_Avoid_: bench, bench vendible, capacidad facturable

**Utilización**:
La parte de la Capacidad de los Developers y los Tech Leaders cubierta por Asignaciones confirmadas y facturables. Usa la misma población que el Dojo. Se mira en una fecha o como promedio de un mes.
_Avoid_: ocupación, billability
