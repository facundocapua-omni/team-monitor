# Carga inicial e importación

Type: grilling
Status: open
Blocked by: 02, 03, 07
Map: [map.md](../map.md)

## Question

¿Cómo entran los datos de 150 personas el primer día?

Ya está decidido que, por ahora, la carga manual es el canal principal. Falta decidir:

- qué se importa una sola vez desde las planillas existentes (ver "Reunir las planillas existentes");
- con qué formato y qué mapeo de columnas;
- cómo se identifica a cada persona para no duplicarla;
- qué validaciones se aplican.

El diseño no debe impedir que más adelante cada Tech Manager cargue lo suyo.

**Decidido en [Modelo de Persona](02-modelo-de-persona.md)**:
- la clave para no duplicar es el email corporativo;
- la Región no se importa: se deriva del manager. La Ciudad es opcional;
- cada persona entra con un Movimiento de Ingreso, con su fecha de entrada a la Dirección. Falta decidir qué se usa si las planillas solo traen la fecha de ingreso a la empresa.

**Decidido en [Modelo de Proyecto, Asignación y Necesidad](03-proyecto-asignacion-necesidad.md)**:
- además de las Personas se cargan Clientes, Proyectos (con Región y Estado), Asignaciones, Necesidades e Indisponibilidades;
- falta decidir si se importa el historial de Asignaciones o solo las vigentes;
- corregir un error de carga edita en el lugar; un cambio con fecha abre una Asignación nueva.

**Decidido en [Skills](05-skills.md)**:
- además de lo anterior se cargan las Skills (Plataforma, Nivel de dominio y fecha de revisión) y las Plataformas de cada Proyecto, que son obligatorias en los externos En curso y en Preventa;
- la Experiencia en Plataforma se calcula con las Asignaciones cargadas, así que importar su historial la mejora desde el primer día; sin él, el dato es pobre al principio. Esto pesa en la decisión de si se importa el historial de Asignaciones o solo las vigentes.
