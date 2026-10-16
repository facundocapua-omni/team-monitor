# Reportes hacia arriba

Type: grilling
Status: resolved
Assignee: Facundo Capua
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

**Decidido en [Planificación de contratación](10-planificacion-de-contratacion.md)**:
- los huecos de contratación ya tienen su cálculo (Hueco por Región, Track, Plataforma y Banda de Seniority, en FTE, con la demanda firme y la de Preventa aparte), y su export a Excel. Este ticket solo decide si entran en un reporte hacia arriba con otro formato; no hace falta recalcularlos.

## Answer

Resuelta el 2026-10-16 en una sesión de grilling. El término nuevo (Rotación) está en [`CONTEXT.md`](../../../CONTEXT.md).

- **Sin destinatario definido**: no se precisó quién lee los reportes ni qué preguntas hace; se diseñó con los candidatos que el handbook y los tickets anticipaban. Todo sale de los mismos datos, así que agregar un bloque después es un cambio chico.
- **Forma**: una página de resumen por Región y una vista global, no una pantalla por reporte.
- **Bloques**:
  1. **Headcount** por Región, Rol, Seniority (con sus Bandas), Track y Plataforma principal, con empleados y externos separados (Vínculo).
  2. **Utilización y Dojo**, con la parte no facturable, por Región, Track, Plataforma o Seniority; también por Cliente y Proyecto, y con las Asignaciones entre Regiones separadas.
  3. **Huecos de contratación**: el cálculo y el export de [Planificación de contratación](10-planificacion-de-contratacion.md), sin recalcular.
  4. **Rotación**: Ingresos y Bajas de un período sobre el headcount medio, con las Bajas voluntarias e involuntarias separadas.
  5. **Nivel de inglés** por Región y Banda de Seniority, con "sin evaluar" aparte.
  6. **Cobertura de Planes de carrera**: cuántos tienen un plan En curso y cuántos están al día con sus Revisiones.
  7. **Cobertura de Plataformas**: personas con nivel Referente y Autónomo por Plataforma y Región.
- **Tiempo**: una foto en una fecha elegible (hoy por defecto) y una serie mensual de los últimos 12 meses para headcount, Utilización, Dojo y rotación. Se reconstruyen de los Movimientos y las Asignaciones, sin guardar nada nuevo. La serie de Utilización y Dojo solo llega hasta donde llegue el historial de Asignaciones cargado.
- **Formato**: vista en pantalla y export a Excel con una hoja por bloque (SheetJS). No hay PDF aparte; el navegador ya imprime la vista.
- **Solo agregados**: números y porcentajes, nunca nombres ni datos de una persona, aunque el grupo sea chico.
- **Fuera**: las distribuciones de la Evaluación de desempeño, que es un dato individual y no se muestra agregado a terceros.
