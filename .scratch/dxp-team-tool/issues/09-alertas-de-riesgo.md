# Alertas de riesgo

Type: grilling
Status: open
Blocked by: 01, 02, 03, 04, 06
Map: [map.md](../map.md)

## Question

¿Qué alertas de riesgo genera la herramienta, con qué reglas y umbrales? ¿Cómo se muestran (una bandeja, el perfil de la persona, o ambos) y cómo se descartan?

Candidatas:

- sobreasignación (más del 100%);
- una Asignación termina sin otra a continuación dentro de N semanas;
- bench durante más de N días;
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
