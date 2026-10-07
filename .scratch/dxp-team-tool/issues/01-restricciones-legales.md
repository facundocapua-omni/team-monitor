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

El detalle completo, con fuentes, está en la rama `research/restricciones-legales`, archivo `research/restricciones-legales.md` (se lee con `git show research/restricciones-legales:research/restricciones-legales.md`). No es asesoría legal: la lista "Validar con Legal/DPO" está en ese documento.

- **Responsable del tratamiento**: la empresa, es decir, cada entidad empleadora, no el Global Tech Director. La herramienta tiene que registrarse como un tratamiento de la empresa. Hasta cumplir las precondiciones, **solo se usan datos ficticios**.
- **Estándar**: RGPD para las ~150 personas, más los requisitos de cada país:
  - Colombia: autorización previa.
  - Argentina: no admite interés legítimo.
  - Ecuador, el más exigente: exige DPO, cubre decisiones "parcialmente" automatizadas y pide cláusulas RIPD para transferir.
  - Chile: la Ley 21.719 rige desde el 1-dic-2026.
- **Qué se puede guardar**:
  - Tal cual: Rol, Seniority, Track, CMS y Asignaciones.
  - Con condiciones: Nivel de inglés, última Evaluación de desempeño, Plan de carrera y alertas basadas en reglas.
  - Bloqueada hasta que Legal la valide: la marca manual de riesgo de fuga.
- **Evaluación de desempeño y alertas**: ordenan o marcan, pero **nunca excluyen automáticamente** a nadie (TJUE C-634/21).
- **España**: el RD 723/2026 y el art. 64.4.d del ET obligan a entregar una ficha algorítmica, a cada persona y al comité de empresa, antes del primer uso con datos de España. Por eso las reglas de alertas y de ordenamiento tienen que ser explicables y estar documentadas.
- **Datos que no se guardan**: texto libre que pueda revelar categorías especiales, y campos de salario, salud, sindicato o familia.
- **Impacto en el modelo**:
  - país y entidad empleadora obligatorios para cada persona;
  - el riesgo de fuga como entidad propia: lista cerrada de valores, caducidad, desactivable por jurisdicción y excluida de exportes y reportes;
  - alertas calculadas al leer, a partir de reglas versionadas;
  - fecha de salida con purga;
  - export y borrado de una persona;
  - log de accesos cuando haya hosting.
- **Precondiciones antes de cargar datos reales**: la lista de 9 pasos está en el documento. Son trámites con Legal y el DPO, fuera del alcance de la spec.
