# Modelo de Proyecto, Asignación y Necesidad

Type: grilling
Status: resolved
Assignee: Facundo Capua
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

## Answer

Resuelta el 2026-10-09 en una sesión de grilling. Los términos nuevos (Cliente, Proyecto, Preventa, Facturable, Asignación, Función, Asignación entre Regiones, Necesidad, Capacidad, Indisponibilidad, Dojo, Utilización) están en [`CONTEXT.md`](../../../CONTEXT.md).

- **Cliente**: una entidad mínima, solo con el nombre. Cada Proyecto pertenece a un Cliente. Lo interno no es un tipo aparte: un proyecto interno es uno cuyo Cliente es la propia empresa. Se dice "Cliente" y no "Cuenta", que se confundiría con la cuenta de Google del SSO.
- **Proyecto**:

  | Atributo | Regla |
  |---|---|
  | Nombre | obligatorio |
  | Cliente | obligatorio |
  | Región | obligatoria y se carga: es la Región que lo vendió y lo gestiona. No se deriva de quien lo lidera |
  | Estado | Preventa, En curso, Cerrado o Perdido |
  | Facturable | sí o no, como valor por defecto para sus Asignaciones |
  | CMS | opcional; uno o más |

  No tiene fechas propias: su duración es la de sus Asignaciones y Necesidades.
- **Preventa** es un Estado, no un tipo. Si se gana, el mismo Proyecto pasa a En curso con sus Necesidades y Asignaciones, que se confirman una por una. **Perdido** cierra solas sus Asignaciones tentativas y sus Necesidades abiertas; quedan en el historial. **Cerrado** pide una fecha de cierre: las Asignaciones que siguen después terminan ese día, y las tentativas y las Necesidades abiertas se cierran.
- **Asignación**:

  | Atributo | Regla |
  |---|---|
  | Persona y Proyecto | obligatorios |
  | Dedicación | entero del 1 al 100 (la pantalla ofrece 25, 50, 75 y 100); fija durante toda la Asignación |
  | Inicio | obligatorio |
  | Fin | opcional; "sin fin" se ve como tal |
  | Estado | Tentativa (reserva blanda) o Confirmada. En un Proyecto en Preventa solo puede ser Tentativa |
  | Función | Liderazgo técnico o Desarrollo |
  | Facturable | hereda el valor del Proyecto y se puede cambiar (shadowing, garantía) |

- **Corregir y cambiar**: un cambio real de dedicación cierra la Asignación y abre otra desde esa fecha, así el historial de Asignaciones sale solo. Corregir un error de carga edita en el lugar, sin historial. El mismo criterio vale para los Movimientos de Persona. En el MVP no hay registro de quién cambió qué: el único usuario es el Tech Director, y el registro llega con el multiusuario.
- **Quién tiene Asignaciones**: cualquier Rol. Las de un Tech Manager, un Expert o un Tech Director se distinguen de las de Developers y Tech Leaders, porque el handbook trata el trabajo de la capa de abajo como un rescate.
- **Función**: dice quién lidera cada Proyecto, con fechas. No depende del Rol: un Developer puede tener Liderazgo técnico, y un Tech Manager con Liderazgo técnico es un rescate. No se exige un único líder por Proyecto; un segundo se muestra.
- **Asignaciones y la vida de la Persona**: una Baja no recorta nada solo. La parte de la Asignación posterior a la Baja queda señalada y deja de contar. Se puede asignar a alguien con Ingreso futuro desde la fecha de Ingreso.
- **Sobreasignación**: si las Asignaciones confirmadas superan la Capacidad, se muestra; no se bloquea.
- **Asignaciones entre Regiones**: la persona es de una Región y el Proyecto de otra. Se marcan y se pueden filtrar, sin flujo de aprobación. Para el Dojo y la Utilización cuentan en la Región de la persona; para la demanda (Necesidades, staffing del Proyecto), en la del Proyecto.
- **Necesidad**: una posición para una sola persona, siempre en un Proyecto. Si un cliente anticipa demanda sin un proyecto definido, se carga como un Proyecto en Preventa de ese Cliente.

  | Atributo | Regla |
  |---|---|
  | Función y Track | obligatorios |
  | Seniority | rango: mínimo obligatorio, máximo opcional |
  | Dedicación, inicio y fin | con las mismas reglas que la Asignación |
  | CMS | opcional |
  | Nivel de inglés mínimo | opcional |
  | Países admitidos | opcional; para cuando el cliente exige residencia |
  | Estado | Abierta, Cubierta (enlazada a la Asignación que la cubre, tentativa o confirmada) o Cancelada. No se borra al cubrirse |

  Cómo cuentan las coberturas tentativas en los huecos de contratación lo decide [Planificación de contratación](10-planificacion-de-contratacion.md).
- **Capacidad**: 100% menos las Indisponibilidades. Una **Indisponibilidad** tiene inicio, fin opcional y un %, y nunca un motivo, porque suele ser de salud o de familia. Cubre licencias, jornadas reducidas y externos a tiempo parcial. Las vacaciones cortas y los feriados no entran en el MVP: la capacidad neta del handbook es para los Delivery KPIs.
- **Dojo** (el nombre que la Dirección usa para el bench): la parte de la Capacidad de un Developer o un Tech Leader sin Asignaciones confirmadas. Todos ellos pueden ser facturables, sin excepciones: Trainees, recién ingresados y externos incluidos. Los Tech Managers, Experts y Tech Directors nunca están en Dojo. Al Dojo no se entra: se está mientras haya Capacidad sin asignar. Lo cubierto por Asignaciones tentativas se ve aparte, como reservado. Un proyecto interno y el shadowing no son Dojo: se ven en la Utilización.
- **Utilización**: la suma de las Asignaciones confirmadas y facturables sobre la Capacidad de la misma población del Dojo. Se agrega por Región, Track, CMS o Seniority, y se mira en una fecha o como promedio de un mes. Dojo, Utilización y la parte no facturable suman siempre la Capacidad de esa población.
