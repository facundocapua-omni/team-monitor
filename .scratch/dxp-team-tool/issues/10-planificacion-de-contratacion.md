# Planificación de contratación

Type: grilling
Status: open
Blocked by: 03
Map: [map.md](../map.md)

## Question

¿Cómo calcula la herramienta los huecos de contratación?

Propuesta: las Necesidades que no cubre la oferta disponible (Dojo más roll-offs) dentro de una ventana de tiempo, agrupadas por Región, Track, Plataforma y Seniority, más los huecos estructurales que surgen de los spans de control.

Queda por decidir:

- qué horizonte de tiempo se mira;
- qué cuenta como "disponible";
- cómo se cuentan las Asignaciones tentativas;
- qué salida hace falta: una vista, o un export para pedir headcount.

**Decidido en [Modelo de Persona](02-modelo-de-persona.md)**:
- los Ingresos y las Bajas pueden ser futuros: un Ingreso futuro suma oferta y una Baja anunciada la resta;
- los externos también son oferta.

**Decidido en [Modelo de Proyecto, Asignación y Necesidad](03-proyecto-asignacion-necesidad.md)**:
- la oferta es la Capacidad de Developers y Tech Leaders (100% menos sus Indisponibilidades), Trainees incluidos: el Dojo actual más lo que liberan las Asignaciones que terminan. La parte cubierta por Asignaciones tentativas se ve como reservada; falta decidir si resta oferta;
- una Necesidad es una posición con Función, Track, rango de Seniority, dedicación, fechas y, opcionalmente, una Plataforma con su Nivel de dominio mínimo, Nivel de inglés mínimo y Países admitidos. Está Abierta, Cubierta o Cancelada. Falta decidir cómo cuenta una Necesidad cubierta por una Asignación tentativa;
- los Proyectos en Preventa también tienen Necesidades; falta decidir si pesan igual que las de un Proyecto en curso;
- la oferta cuenta en la Región de la persona y la demanda en la del Proyecto.

**Decidido en [Skills](05-skills.md)**:
- la oferta por Plataforma sale de las Skills (la Plataforma principal más las otras, cada una con su Nivel de dominio), de modo que un hueco se puede medir también por nivel: por ejemplo, Referentes de una Plataforma en una Región. Falta decidir si la oferta de una Plataforma cuenta solo la principal o también las demás Skills;
- una Necesidad pide una sola Plataforma, así que la agrupación no tiene dobles conteos.
