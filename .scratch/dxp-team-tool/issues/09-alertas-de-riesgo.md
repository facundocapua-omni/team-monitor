# Alertas de riesgo

Type: grilling
Status: open
Blocked by: —
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

**Decidido en [Evaluación de desempeño](04-evaluacion-de-desempeno.md)**:
- la Calificación final va de 1 a 5, una por ciclo anual, y los externos no tienen. En el staffing no entra en ningún orden ni filtro calculado. Falta decidir si la candidata "Evaluación de desempeño baja" sobrevive como alerta (sería una marca en la bandeja, no un orden) y con qué umbral; una persona sin evaluar no cuenta como baja.

**Decidido en [Skills](05-skills.md)**:
- candidatas nuevas: concentración de riesgo en una Plataforma (por ejemplo, pocas personas con nivel Referente o Autónomo en una Región) y una Skill con la revisión vencida. Los umbrales se fijan acá;
- la Plataforma de un Proyecto es obligatoria en los externos En curso y en Preventa; un Proyecto sin ella podría ser una alerta de datos faltantes.

**Decidido en [Plan de carrera](06-plan-de-carrera.md)**:
- la candidata "persona sin Plan de carrera, o con el plan sin revisar" pasa a ser dos: un Developer o Tech Leader empleado sin plan En curso, y un plan con la última Revisión de más de 3 meses. Falta fijar la tolerancia. Los externos no tienen plan, así que no entran;
- un plan con la fecha objetivo pasada y todavía En curso es otra candidata;
- cuando se carga un Movimiento que coincide con el objetivo, la herramienta sugiere cerrar el plan; eso es una sugerencia, no una alerta.
