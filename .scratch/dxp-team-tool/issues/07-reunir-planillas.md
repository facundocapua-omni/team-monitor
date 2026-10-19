# Reunir las planillas existentes

Type: task (HITL)
Status: open
Assignee: Facundo Capua
Blocked by: —
Map: [map.md](../map.md)

## Question

¿Qué fuentes de datos existen hoy y qué forma tienen? Hace falta saberlo antes de decidir la carga inicial.

Checklist para el usuario (se puede hacer en cualquier momento):

- [ ] Listado de personas (Excel o export del HRIS) con lo que tenga: Región, Rol, Seniority, manager.
- [ ] Resultados de inglés del profesor interno.
- [ ] Resultados de la última Evaluación de desempeño.
- [x] Cualquier planilla de staffing o asignaciones (de la PMO o de los Tech Managers). Ver "Fuente 1" abajo.
- [ ] Guardarlos en una carpeta local **fuera de este repo** y anotar acá, para cada uno, la ruta, el formato y las columnas. Nunca commitear datos reales.

Se resuelve cuando las fuentes están identificadas y sus columnas quedan registradas en la respuesta.

Nota (de [Alertas de riesgo](09-alertas-de-riesgo.md)): al reunirlas, conviene ver si traen la fecha de fin de las Asignaciones, el manager de cada persona y las Plataformas de los Proyectos, porque las Alertas de Staffing y Estructura dependen de esos datos.

## Avance (2026-10-19)

Queda abierto hasta que estén las otras tres fuentes (listado de personas, inglés, Evaluación de desempeño). Acá solo van rutas, formatos y columnas, nunca datos de personas.

### Fuente 1: planilla de capacidad semanal

- **Ruta**: `~/Downloads/Capacity DXP.xlsx` (fuera del repo; conviene moverla a una carpeta de trabajo fuera de Descargas y de nubes personales).
- **Formato**: Excel con cuatro hojas visibles y dos ocultas.

| Hoja | Estado | Qué tiene |
|---|---|---|
| DXP Team | visible | 81 recursos, 134 filas de asignación, 27 nombres de proyecto distintos |
| Soporte | visible | 7 recursos, 112 filas, 16 proyectos "Mantenimiento" |
| DevOps | visible | 9 recursos, 161 filas, 21 nombres distintos |
| Comparacion Recursos | visible | tabla de equivalencias de nombres de recurso entre hojas (80 filas con dos nombres, 20 con tres) |
| Data_Validation | oculta | las listas de la lista desplegable: Recursos, Proyectos, Mantenimiento |
| Capacidad Automatizada | oculta | una plantilla anterior (Enero a Junio) con 2 recursos de ejemplo |

- **Estructura de cada hoja de recursos**: un bloque por recurso.
  - Una fila de cabecera de recurso: `Recurso` (nombre) y `Proyecto / Asignación` = "TOTAL CAPACIDAD", con la suma semanal de sus asignaciones.
  - Debajo, una fila por Asignación: `Proyecto / Asignación` (nombre del proyecto), `Semana Inicio`, `Semana Fin`, `% Asig.`, y una columna por semana (S1 a S24 o S25) con la dedicación de esa semana. Los encabezados de mes (Septiembre a Febrero) agrupan las semanas.
- **Total de recursos en las tres hojas**: 97 filas, con solapamientos entre hojas (los nombres no siempre coinciden, de ahí la hoja de equivalencias).

### Qué hay y qué no hay frente al modelo

- **Hay**: nombre de la persona, proyecto, dedicación y una vigencia en semanas.
- **No hay**: email corporativo, Rol, Seniority, Track, manager, Plataforma, país o ciudad, Vínculo (empleado o externo), Cliente, Función (Liderazgo técnico o Desarrollo), si es Tentativa o Confirmada, si es Facturable, ni Necesidades abiertas. El Cliente y a veces la Plataforma están embebidos en el nombre del proyecto, y los proyectos de mantenimiento se distinguen por el sufijo.
- **Semanas relativas**: S1 a S25 no traen fecha de calendario, solo el mes de cabecera. Hace falta una fecha de ancla para convertirlas en fechas de inicio y de fin.
- **Fin = horizonte**: en la hoja DXP Team, 120 de las 134 asignaciones terminan en la semana 18, que es el final de lo planificado; en las otras dos hojas lo hacen todas. Esa semana 18 casi seguro significa "sin fin conocido" y no una fecha de fin real.
- **Dedicaciones con decimales**: Soporte divide a cada persona en 16 proyectos de mantenimiento a 6,25% cada uno, y DevOps reparte 5% en muchos proyectos de infraestructura. Hay también valores como 1%. El modelo exige un entero del 1 al 100.
- **Sobreasignación real**: 5 recursos de DXP Team superan el 100% en alguna semana, y en 1 el total no coincide con la suma de sus filas.
- **Sin historial**: la planilla es un plan hacia adelante; no trae Asignaciones ya terminadas.
- **Sin Indisponibilidades ni feriados** identificables como filas aparte.
