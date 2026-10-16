# Planificación de contratación

Type: grilling
Status: resolved
Assignee: Facundo Capua
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

## Answer

Resuelta el 2026-10-16 en una sesión de grilling. Los términos (Hueco, Banda de Seniority, Anticipación de contratación) están en [`CONTEXT.md`](../../../CONTEXT.md).

- **Cálculo**: el Hueco se mide por grupo (Región, Track, Plataforma y Banda de Seniority) y en FTE, o sea la dedicación (100% = 1). Cada persona cuenta en un solo grupo, el de su Track y su Plataforma principal, así que no hay doble conteo. La demanda cuenta en la Región del Proyecto y la oferta en la de la persona. Al abrir una Necesidad se ve además cuántos candidatos disponibles tiene, contando todas sus Skills, pero esa cuenta no suma en el Hueco.
- **Oferta**: la Capacidad de Developers y Tech Leaders, Trainees y externos incluidos, fecha por fecha. Suma la Capacidad que no ocupa ninguna Asignación confirmada, lo que liberan las Asignaciones que terminan dentro de la ventana (desde su fecha de fin) y los Ingresos futuros; resta las Bajas anunciadas y las Indisponibilidades. Una Asignación sin fecha de fin no libera nada.
- **Horizonte**: la ventana se elige en pantalla (4, 8, 12 o 26 semanas), con 12 por defecto. La Anticipación de contratación es de 8 semanas, editable y la misma que usa la Regla de Necesidad Abierta cercana a su inicio ([Alertas de riesgo](09-alertas-de-riesgo.md)). Cada Hueco muestra su fecha límite para abrir la búsqueda y se marca urgente si ya pasó.
- **Tentativas**: la Capacidad reservada por una Asignación tentativa sale de la oferta, y la Necesidad que cubre sale de la demanda; ese monto se muestra aparte como pendiente de confirmar. Si la tentativa cae, la Necesidad vuelve a Abierta y la persona a la oferta.
- **Preventa**: sin probabilidad. La demanda firme (Proyectos En curso) y la posible (Preventa) se muestran en columnas aparte, y el Hueco se ve en los dos escenarios.
- **Bandas de Seniority**: Junior (Trainee, Junior y Junior Advanced), Semi Senior (Semi Senior y Semi Senior Advanced), Senior (Senior Level 1 y 2) y Tech Leader (Senior Level 3). Una Necesidad cuenta en la banda de su Seniority mínima; el máximo del rango solo se usa en la lista de candidatos. Una Necesidad sin Plataforma se compara contra toda su Región, Track y banda, en una fila "Cualquier Plataforma" aparte.
- **Huecos estructurales**: no se calcula un número de contratación. Los líderes por encima de su span se listan aparte, con enlace a la Alerta de Estructura.
- **Salida**: una vista (huecos por grupo y por mes dentro de la ventana) y un export a Excel con los Huecos y sus fechas límite, solo agregados y Necesidades, sin datos de personas. No hay seguimiento del pedido de headcount ni de la búsqueda: eso es un proceso de selección, fuera de alcance. Una Necesidad que se cubre con una contratación se pasa a Cubierta enlazando la Asignación del nuevo Ingreso.
