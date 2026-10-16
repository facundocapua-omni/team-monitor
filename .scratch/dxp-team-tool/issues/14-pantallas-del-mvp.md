# Pantallas del MVP

Type: prototype
Status: open
Blocked by: —
Map: [map.md](../map.md)

## Question

¿Qué pantallas tiene el MVP y cómo se ve la vista de staffing?

Un prototipo rápido para reaccionar sobre:

- el directorio por Región;
- el perfil de una persona;
- un timeline o tablero de Asignaciones y Necesidades;
- la bandeja de alertas;
- la vista de huecos de contratación;
- los reportes.

**Decidido en [Modelo de Proyecto, Asignación y Necesidad](03-proyecto-asignacion-necesidad.md)**:
- el Dojo se muestra con ese nombre, y lo cubierto por Asignaciones tentativas aparece como reservado;
- una Asignación ofrece dos acciones distintas: corregir (edita en el lugar) y cambiar desde una fecha (abre otra Asignación);
- cerrar un Proyecto pide una fecha de cierre; perderlo cierra sus tentativas y Necesidades abiertas;
- marcas visibles: Asignaciones de Roles de liderazgo, Asignaciones entre Regiones, Asignaciones que siguen después de una Baja, sobreasignación;
- una Necesidad está Abierta, Cubierta (enlazada a su Asignación) o Cancelada.

**Decidido en [Skills](05-skills.md)**:
- el perfil de una persona muestra sus Skills con Nivel de dominio, fecha de revisión (vencida si pasó un año) y la Experiencia en Plataforma calculada;
- al buscar candidatos para una Necesidad se ve a todos con una marca de qué requisitos cumple cada uno, sin ocultar a nadie; el orden de la lista queda para este prototipo y no puede usar la Evaluación de desempeño.

**Decidido en [Plan de carrera](06-plan-de-carrera.md)**:
- el perfil de una persona muestra su Plan de carrera (objetivo, fecha objetivo, foco e ítems con su estado actual) y el historial de Revisiones, con una marca si la última pasó los 3 meses;
- cargar una Revisión es una acción corta: fecha, nota y el estado de cada ítem de foco;
- al cargar un Movimiento que coincide con el objetivo, la pantalla ofrece cerrar el plan como Logrado y abrir el siguiente.

**Decidido en [Alertas de riesgo](09-alertas-de-riesgo.md)**:
- la bandeja agrupa las Alertas por familia (Staffing, Estructura, Personas), las ordena por la fecha en que empiezan a importar y no tiene niveles de severidad; el perfil de la persona o del Proyecto muestra las suyas;
- una pantalla Reglas lista cada Regla en lenguaje simple, con interruptor y valores editables;
- cada Alerta muestra qué Regla la generó y con qué datos, y se puede silenciar (30 días por defecto o sin fecha, nota opcional), por persona o Proyecto, o por familia entera;
- las Alertas con una Asignación tentativa a continuación llevan la leyenda "con reserva tentativa".

**Decidido en [Planificación de contratación](10-planificacion-de-contratacion.md)**:
- la vista de Huecos tiene una ventana elegible (4, 8, 12 o 26 semanas, con 12 por defecto), muestra los Huecos por grupo y por mes en FTE, con la demanda firme y la de Preventa en columnas aparte, el monto pendiente de confirmar y, por Hueco, la fecha límite para abrir una búsqueda (urgente si ya pasó);
- una fila "Cualquier Plataforma" aparte para las Necesidades sin Plataforma, y una lista de los líderes sobre su span, con enlace a su Alerta;
- cada Necesidad muestra cuántos candidatos disponibles tiene;
- un botón exporta los Huecos a Excel, sin datos de personas.

**Decidido en [Reportes hacia arriba](13-reportes-hacia-arriba.md)**:
- los reportes son una página de resumen por Región, más una vista global, con siete bloques (headcount, Utilización y Dojo, Huecos, Rotación, Nivel de inglés, cobertura de Planes de carrera y cobertura de Plataformas);
- cada bloque se ve en una fecha elegible (hoy por defecto) y, para headcount, Utilización, Dojo y rotación, como una serie mensual de los últimos 12 meses;
- la página exporta a Excel, con una hoja por bloque, y solo lleva agregados, nunca datos de una persona.
