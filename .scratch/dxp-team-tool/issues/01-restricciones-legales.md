# Restricciones legales para guardar datos de personas

Type: research
Status: resolved
Assignee: research subagent
Blocked by: —
Map: [map.md](../map.md)

## Question

¿Qué obligaciones legales aplican cuando el Global Tech Director guarda y usa los siguientes datos de cada persona de la Dirección en una herramienta propia (primero en su laptop, después en un hosting aprobado por TI)?

- Rol, Seniority, Track, CMS y Asignaciones.
- El resultado de la última Evaluación de desempeño.
- El Nivel de inglés.
- El Plan de carrera.
- Las alertas de riesgo, incluida una marca manual de riesgo de fuga.

Jurisdicciones:

- **España**: RGPD, LOPDGDD y los derechos de información y consulta del comité de empresa según el Estatuto de los Trabajadores.
- **Americas**: Colombia, Panamá, Ecuador, Chile y Argentina.
- **A futuro**: EAU, Arabia Saudita, Egipto y Jordania.

Para cada jurisdicción:

- base legal;
- deber de informar a las personas;
- consulta a la representación de los trabajadores;
- minimización y retención;
- medidas de seguridad esperables;
- transferencias internacionales (los datos de Americas se tratan desde España);
- si alguna alerta cuenta como perfilado o decisión automatizada.

**Resultado esperado**: qué datos se pueden guardar tal cual, cuáles con condiciones, y qué hay que hacer antes de cargar datos reales. No es asesoría legal: marcar qué hay que validar con Legal o con el DPO.

## Answer

Reencuadrada el 2026-10-08, tras una aclaración del usuario: la herramienta solo ordena datos a los que ya accede, en la misma máquina y para los mismos fines.

- **La herramienta no cambia la base legal.** La ley mira qué datos se tratan y para qué, no con qué herramienta. Pasar de planillas a una app local, con los mismos datos y los mismos fines, no crea un tratamiento nuevo: la empresa ya es hoy la responsable de esos datos. No hace falta registrar nada ni trabajar con datos ficticios.
- **Lo nuevo, que hay que cuidar en el diseño:**
  - **Datos que se crean.** La marca de riesgo de fuga es información nueva sobre una persona, y cualquiera puede pedir ver lo que hay registrado sobre sí. Criterio: no registrar nada que la persona no debería poder leer. Antes de incluirla, se confirma con RRHH.
  - **Reglas que ordenan o filtran gente.** Son las alertas y el orden del staffing por evaluación. Sugieren, pero nunca excluyen automáticamente: la decisión es del usuario. En España, el art. 64.4.d del ET (y, según la investigación, el RD 723/2026) cubre los algoritmos que influyen en decisiones laborales. Hay que consultar a RRHH antes de usarlas con gente de España.
  - **Concentración.** La base va en un disco cifrado, fuera del repo y fuera de nubes personales.
- **Higiene de datos**: sin texto libre con información sensible (salud, sindicato, familia, salario), y con la posibilidad de exportar o borrar a una persona.
- **Cuándo importa el análisis completo**: al pasar a hosting de TI y a multiusuario, la herramienta se convierte en un sistema nuevo de la empresa. Ahí aplican las obligaciones por país del documento de investigación: rama `research/restricciones-legales`, archivo `research/restricciones-legales.md`. No es asesoría legal.
