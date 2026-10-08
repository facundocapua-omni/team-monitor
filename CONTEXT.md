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

**CMS**:
Plataforma de las que trabaja la Dirección: Optimizely Cloud, Contentful, AEM EDS o AEM Traditional.
_Avoid_: plataforma, solución, tecnología

**CMS principal**:
El CMS en el que se especializa una persona; es el que cuenta en el headcount por CMS. Los otros CMS que maneja forman parte de sus skills.
_Avoid_: CMS actual

**Nivel de inglés**:
Nivel de una persona en la escala MCER (A1–C2), evaluado por el profesor de inglés interno. Vale la última evaluación; una persona sin evaluar no es lo mismo que una A1.
_Avoid_: English level, nivel de idioma

**Evaluación de desempeño**:
Resultado periódico e individual del rendimiento de una persona. La herramienta usa la última para decidir el staffing.
_Avoid_: KPI, performance score

**Delivery KPI**:
Una de las cinco métricas de entrega del handbook. Se mide por equipo y nunca se atribuye a un Developer; cuenta en la evaluación de Tech Leaders y Tech Managers.
_Avoid_: KPI de rendimiento, métrica individual
