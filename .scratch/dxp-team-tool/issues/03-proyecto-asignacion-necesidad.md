# Modelo de Proyecto, Asignación y Necesidad

Type: grilling
Status: open
Blocked by: —
Map: [map.md](../map.md)

## Question

¿Cómo se modelan estas tres entidades?

- **Proyecto**: si cuelga de una Cuenta o cliente, su Región, y si es facturable o interno/preventa.
- **Asignación**: persona, proyecto, % de dedicación, fechas, y si es confirmada o tentativa.
- **Necesidad**: una posición abierta, con Track, CMS, Seniority, %, fechas y Nivel de inglés requerido.

También hay que decidir:

- qué es exactamente "bench";
- cómo se calcula la utilización;
- cómo se representan las Asignaciones entre Regiones (según el handbook, las escala el Tech Manager);
- si los roles de liderazgo (Tech Manager, Expert) también tienen Asignaciones.

**Decidido en [Modelo de Persona](02-modelo-de-persona.md)**:
- los externos (Vínculo externo) son Personas y también reciben Asignaciones;
- la Región de una persona se deriva de su Línea de reporte. Una Asignación entre Regiones es la de una persona cuya Región difiere de la del Proyecto;
- la Ubicación (País y Ciudad) está disponible para el staffing: zona horaria, presencialidad, residencia exigida por el cliente.
