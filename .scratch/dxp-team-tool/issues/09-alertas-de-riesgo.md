# Alertas de riesgo

Type: grilling
Status: open
Blocked by: 01, 02, 03, 04, 06
Map: [map.md](../map.md)

## Question

¿Qué alertas de riesgo genera la herramienta, con qué reglas y umbrales? ¿Cómo se muestran (una bandeja, el perfil de la persona, o ambos) y cómo se descartan?

Candidatas:

- sobreasignación (Asignaciones confirmadas por encima de la Capacidad);
- una Asignación termina sin otra a continuación dentro de N semanas;
- Dojo durante más de N días;
- span de control fuera de rango (3–6 Tech Leaders por Tech Manager, 3–5 Developers por Tech Leader);
- un "rescate" de más de un mes, es decir, un Tech Manager haciendo de Tech Leader;
- persona sin Plan de carrera, o con el plan sin revisar en N meses;
- Evaluación de desempeño baja;
- marca manual de riesgo de fuga (depende de lo que responda RRHH);
- Nivel de inglés por debajo del que requiere su Asignación.

**Restricciones ya decididas** (ver [Restricciones legales](01-restricciones-legales.md)):
- las alertas sugieren, pero nunca excluyen automáticamente: la decisión es del usuario;
- las reglas tienen que ser explicables, por si hay que informarlas en España;
- la marca de riesgo de fuga depende de lo que responda RRHH (ver [Requisitos de TI](08-requisitos-de-ti.md)). Si entra, nunca se calcula a partir de otros datos.

**Decidido en [Modelo de Persona](02-modelo-de-persona.md)**:
- candidatas nuevas: un Tech Leader por debajo de L8; personas que reportan a alguien con Baja cargada, o sin manager activo pasada la fecha; Líneas de reporte fuera del esquema, como un Developer que reporta a un Tech Manager;
- falta decidir si los externos cuentan en el span de control de su Tech Leader.

**Decidido en [Modelo de Proyecto, Asignación y Necesidad](03-proyecto-asignacion-necesidad.md)**:
- candidatas nuevas: un Proyecto en curso sin Asignación de Liderazgo técnico, o con más de una a la vez; una Asignación que sigue después de la Baja de la persona; una Necesidad todavía Abierta a N semanas de su inicio;
- el rescate se detecta con la Función: un Tech Manager con una Asignación de Liderazgo técnico. El otro caso del handbook es un Expert con Asignaciones de Desarrollo;
- la Capacidad descuenta las Indisponibilidades, así que una Indisponibilidad sobre una Asignación aparece como sobreasignación;
- el Nivel de inglés requerido está en la Necesidad: la alerta compara a la persona con la Necesidad que cubre su Asignación. Una Asignación sin Necesidad no tiene requisito;
- las Asignaciones entre Regiones solo se marcan; no son una alerta;
- solo Developers y Tech Leaders pueden estar en Dojo.
