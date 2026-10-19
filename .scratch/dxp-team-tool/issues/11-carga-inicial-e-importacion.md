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

**Decidido en [Plan de carrera](06-plan-de-carrera.md)**:
- hay que importar el catálogo de Ítems de roadmap desde el handbook (`../structure/src/content/docs/roadmaps/`): nombre, sección y prioridad, por Track. Se vuelve a importar cuando el handbook cambie, y los planes conservan el nombre del ítem elegido. Falta decidir el formato de esa fuente, porque los roadmaps están en Markdown;
- además se cargan los Planes de carrera vigentes (objetivo, fecha objetivo, foco, ítems y la última Revisión). Falta decidir si se importa el historial de Revisiones o solo la última.

**Decidido en [Alertas de riesgo](09-alertas-de-riesgo.md)**:
- tras la carga inicial casi todo estará recién creado, así que habrá muchas Alertas de Planes sin Revisión o sin plan; el Silencio por familia existe para esa etapa. Falta decidir si la carga fija las fechas de Revisión y de última revisión de Skills a la fecha de importación.

**Decidido en [Reportes hacia arriba](13-reportes-hacia-arriba.md)**:
- las series de Utilización, Dojo y la Experiencia en Plataforma solo llegan hasta donde llegue el historial de Asignaciones cargado, así que importarlo (y no solo las vigentes) alarga esas series desde el primer día. El headcount y la rotación dependen de los Movimientos, que arrancan con el Ingreso de cada persona.

**Hallazgos de [Reunir las planillas](07-reunir-planillas.md)** (planilla de capacidad semanal, 2026-10-19):
- la planilla trae nombre, proyecto, dedicación y semanas, pero no email, Rol, Seniority, Track, manager, Plataforma, Cliente, Función, estado tentativa o confirmada, ni Facturable. El email para no duplicar a la persona hay que obtenerlo de otra fuente, o armarse una tabla de equivalencia de nombres (la planilla ya trae una hoja de equivalencias entre sus propias hojas);
- las semanas son relativas (S1 a S25) y hace falta una fecha de ancla; las que terminan en la semana 18, el horizonte, probablemente sean "sin fin";
- hay dedicaciones fraccionarias (6,25%, 5% y 1%), y el modelo de Asignación exige un entero del 1 al 100. Hay que decidir si se redondea al importar, si se admiten decimales o si se agrupan los proyectos de mantenimiento;
- el Cliente y el tipo de proyecto (mantenimiento, infraestructura) están embebidos en el nombre del proyecto, así que el mapeo a Cliente y Proyecto es una decisión de importación;
- 5 recursos están sobreasignados en la propia planilla: la carga debe aceptarlo y marcarlo, no rechazarlo;
- no hay historial de Asignaciones ya terminadas; solo el plan vigente.

**Decidido (2026-10-19)**: la Dedicación de una Asignación admite decimales: un número mayor que 0 y hasta 100, con hasta dos decimales. Así la planilla de capacidad entra sin redondear (6,25% × 16 proyectos de mantenimiento suma 100%). Lo mismo vale para el porcentaje de una Indisponibilidad.

**Hallazgos del listado del equipo ([Reunir las planillas](07-reunir-planillas.md), Fuente 2)**:
- el email está en las 197 filas y no se repite, así que sirve como clave. Los externos tienen el email de su proveedor, no uno corporativo de la empresa: la clave es el email, aunque el glosario hable de "corporativo";
- Vínculo se deduce de la columna `Fuente`: Omni son empleados y Codebay y Globant son externos. En total unas 197 personas, de las cuales 61 son externas;
- hay que decidir cómo se convierte el `Rol` (29 valores de texto libre) en la lista cerrada de Roles del handbook, el Track y la Plataforma principal. Algunos no encajan en ningún Rol del handbook (PM, Content Manager, Consultor, PMO Lead, Analista, Technical Specialist), y hay Tracks fuera de los cuatro del handbook (App Flutter, Python, Salesforce). Falta decidir si esas personas pertenecen a la Dirección en la herramienta;
- la `Seniority` interna (Junior I y II, Semi Senior I y II, Senior I y II, Lead I y II) tiene que mapearse a la escala de 8 niveles del handbook, en particular Lead I y II; y la segunda columna `Seniority` de los externos usa otro vocabulario. Hay 40 empleados sin ninguno de los dos;
- `NivelIngles` trae valores con "+" (A2+, B2+) que no existen en la escala MCER; hay que decidir cómo importarlos. 27 personas no tienen nivel, lo que se carga como sin evaluar;
- `Pais` mezcla "Spain" y "España", y hay países como India, México, Guatemala, Bolivia, El Salvador, Italia, Canadá y Rumania, que no están entre los de las dos Regiones del mapa. La zona horaria (`Timezone`) viene aparte y la herramienta no la guarda, solo la Ubicación (País y Ciudad);
- `Certificaciones` está cargada en 73 filas como texto libre. Las certificaciones quedaron fuera del MVP ([Skills](05-skills.md)), así que no se importan;
- `CapacidadMensual` (160 horas) no se usa: la Capacidad de la herramienta es un porcentaje;
- no hay manager, así que la Línea de reporte y la Región no se pueden derivar de esta fuente, ni la fecha de Ingreso. Hace falta otra fuente;
- el cruce de nombres con la planilla de capacidad coincide exacto en 61 de 97 recursos y casi coincide en unos 22 más. Hace falta una tabla de equivalencias para unir ambas fuentes, usando el email como clave.
