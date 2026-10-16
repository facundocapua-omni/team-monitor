# Alertas de riesgo

Type: grilling
Status: resolved
Assignee: Facundo Capua
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

## Answer

Resuelta el 2026-10-16 en una sesión de grilling. Los términos (Alerta, Regla, Silencio) están en [`CONTEXT.md`](../../../CONTEXT.md).

**Mecánica**
- Una Alerta se calcula con los datos de hoy y no se guarda; desaparece sola cuando el dato se arregla. Sugiere, nunca excluye ni ordena a nadie.
- Se ve en una bandeja, agrupada por familia (Staffing, Estructura, Personas) y ordenada por la fecha en que empieza a importar, y en el perfil de la persona o del Proyecto. No hay niveles de severidad.
- Descartar es un **Silencio**: una Regla silenciada para una persona o Proyecto, 30 días por defecto o sin fecha, con una nota opcional sin motivos sensibles. Si vence y la condición sigue, la Alerta vuelve. También se puede silenciar una familia entera, para la carga inicial.
- Una pantalla **Reglas** lista cada Regla en lenguaje simple con sus valores, que se pueden cambiar, y un interruptor para desactivarla. Es una sola para toda la Dirección, no una por Región. Cada Alerta muestra qué Regla la generó y con qué datos, para poder explicarla en España.
- Cada Regla declara a qué Roles aplica. No generan Alertas las personas con Baja pasada, las de Ingreso futuro antes de su fecha ni, en las Reglas de Dojo, las de Indisponibilidad total.

**Reglas y valores por defecto**

| Familia | Regla | Valor por defecto | Aplica a |
|---|---|---|---|
| Staffing | Sobreasignación (incluye una Indisponibilidad sobre una Asignación) | cualquier exceso sobre la Capacidad | todos los Roles |
| Staffing | Asignación posterior a una Baja | | todos los Roles |
| Staffing | Asignación que termina sin continuación | faltan 6 semanas o menos; una tentativa a continuación no la evita, se muestra con la leyenda "con reserva tentativa" | Developers y Tech Leaders |
| Staffing | Dojo prolongado | 30 días seguidos con 50% o más de Capacidad sin Asignación confirmada; las tentativas igual, con la leyenda | Developers y Tech Leaders |
| Staffing | Proyecto En curso sin Liderazgo técnico, o con más de uno a la vez | | Proyectos |
| Staffing | Necesidad Abierta cerca de su inicio | faltan 8 semanas o menos | Necesidades |
| Estructura | Span fuera de rango | 3 a 6 Tech Leaders por Tech Manager; 3 a 5 Developers por Tech Leader; los externos cuentan | Tech Managers y Tech Leaders |
| Estructura | Rescate | más de 30 días seguidos de un Tech Manager con una Asignación de Liderazgo técnico; también un Expert con Asignaciones de Desarrollo | Tech Managers y Experts |
| Estructura | Tech Leader por debajo de L8 | | Tech Leaders |
| Estructura | Persona que reporta a alguien con Baja cargada, o sin manager activo pasada la fecha | | todos los Roles |
| Estructura | Línea de reporte fuera del esquema (por ejemplo, un Developer que reporta a un Tech Manager) | | todos los Roles |
| Personas | Sin Plan de carrera En curso | 60 días de gracia desde el Ingreso | Developers y Tech Leaders empleados |
| Personas | Plan con la última Revisión vencida | 3 meses y 15 días | Planes En curso |
| Personas | Plan En curso con la fecha objetivo pasada | desde el primer día vencida | Planes En curso |
| Personas | Skill con la revisión vencida | 12 meses | Skills |
| Personas | Concentración de riesgo en una Plataforma | menos de 2 personas con nivel Autónomo o Referente en una Región, solo si hay un Proyecto En curso o una Necesidad Abierta de esa Plataforma en esa Región | Plataformas por Región |
| Personas | Proyecto sin Plataforma declarada | | Proyectos En curso y en Preventa de Clientes externos |
| Staffing | Nivel de inglés por debajo del requisito | la persona contra la Necesidad que cubre su Asignación; una Asignación sin Necesidad no tiene requisito | Asignaciones |

**Fuera del MVP**
- Evaluación de desempeño baja: es un dato visible y no un filtro calculado ([Evaluación de desempeño](04-evaluacion-de-desempeno.md)).
- Marca de riesgo de fuga: espera la respuesta de RRHH ([Requisitos de TI](08-requisitos-de-ti.md)); si entra, será manual y nunca calculada.
- Las Asignaciones entre Regiones solo se marcan, no son una Alerta.
