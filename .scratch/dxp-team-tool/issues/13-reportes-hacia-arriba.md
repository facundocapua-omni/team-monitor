# Reportes hacia arriba

Type: grilling
Status: open
Blocked by: 02, 03
Map: [map.md](../map.md)

## Question

¿Qué reportes hacia arriba incluye el MVP?

Candidatos:

- headcount por Región, Rol, Seniority, Track y Plataforma;
- Utilización y Dojo;
- distribución del Nivel de inglés;
- huecos de contratación;
- cobertura de los Planes de carrera.

También hay que decidir:

- el formato: vista en pantalla, export (Excel o PDF), o ambos;
- si alcanza con una foto del momento o hace falta la evolución en el tiempo (eso exigiría guardar historial).

Entra solo si sale casi gratis de los mismos datos.

**Decidido en [Modelo de Persona](02-modelo-de-persona.md)**:
- los Movimientos ya guardan el historial de Ingresos, Bajas, Rol, Seniority, Track y manager, así que la evolución del headcount y la rotación salen casi gratis.

**Decidido en [Modelo de Proyecto, Asignación y Necesidad](03-proyecto-asignacion-necesidad.md)**:
- Dojo, Utilización y la parte no facturable usan la misma población (Developers y Tech Leaders) y suman su Capacidad, así que se pueden mostrar juntos;
- las Asignaciones cerradas se conservan, así que la evolución de la Utilización y el Dojo también sale casi gratis;
- también se puede agrupar por Cliente y Proyecto, y separar las Asignaciones entre Regiones.

**Decidido en [Skills](05-skills.md)**:
- el headcount por Plataforma usa la Plataforma principal. Hay una segunda vista posible, por Skill y Nivel de dominio, que sale de los mismos datos.

**Decidido en [Plan de carrera](06-plan-de-carrera.md)**:
- la cobertura de los Planes de carrera (cuántos Developers y Tech Leaders empleados tienen un plan En curso, y cuántos están al día con sus Revisiones) sale de los mismos datos. Como las Revisiones tienen historial, la evolución de esa cobertura sale casi gratis.
