# Plan de carrera

Type: grilling
Status: resolved
Assignee: Facundo Capua
Blocked by: —
Map: [map.md](../map.md)

## Question

¿Qué contiene un Plan de carrera y cómo se ancla al career path del handbook?

Propuesta para discutir:

- objetivo: el próximo nivel de Seniority, o la rama Tech Manager / Expert;
- fecha objetivo;
- estado en cada dimensión (Autonomy, Impact/scope, Mentorship, Technical complexity);
- acciones;
- fecha de última revisión.

¿Hay un solo plan activo por persona o pueden ser varios? ¿Cómo se cierra un plan cuando se logra o se abandona?

**Decidido en [Modelo de Persona](02-modelo-de-persona.md)**:
- la Seniority tiene historial (Movimientos con fecha efectiva), así que el tiempo en el nivel ya está disponible;
- hay externos en la Dirección. Falta decidir si tienen Plan de carrera.

## Answer

Resuelta el 2026-10-16 en una sesión de grilling. Los términos (Plan de carrera, Ítem de roadmap, Revisión) están en [`CONTEXT.md`](../../../CONTEXT.md).

- **Para qué**: que cada persona tenga un próximo paso con fecha y que alguien lo revise. El contenido fino de las conversaciones 1:1 no entra, porque las notas de 1:1 están fuera de alcance.
- **Contenido**: objetivo (el próximo nivel de Seniority o, desde el nivel 8, la rama Tech Manager o Expert), fecha objetivo, nota corta de foco y Estado (En curso, Logrado, Abandonado o Reemplazado, con fecha de cierre). No se guarda el estado en cada dimensión del handbook (Autonomy, Impact/scope, Mentorship, Technical complexity) ni las acciones.
- **Quién tiene**: solo Developers y Tech Leaders empleados. Los externos, los Tech Managers y más arriba no tienen: no hay criterios definidos contra los cuales anclar un plan.
- **Anclaje al roadmap**: el plan elige entre 2 y 5 Ítems de roadmap del Track de la persona como foco. El catálogo (nombre, sección y prioridad) se importa desde el handbook y se vuelve a importar cuando cambie; los planes conservan el nombre del ítem que eligieron. Se pueden agregar o quitar ítems entre revisiones, y un plan puede tener cero (el caso de un Tech Leader que apunta a Tech Manager o Expert). Los ítems de la sección de una Plataforma se ven como evidencia junto a la Skill, sin cambiarla.
- **Revisiones**: una cada trimestre, con historial. Cada una guarda la fecha, una nota corta opcional y el estado de cada ítem de foco en ese momento (Pendiente, En curso o Logrado). Corregir un error edita en el lugar. Un plan se ve vencido si pasaron más de 3 meses sin revisión; la tolerancia la fija [Alertas de riesgo](09-alertas-de-riesgo.md).
- **Un plan y su cierre**: un solo plan En curso por persona. Al cargar un Movimiento de Seniority o de Rol que coincide con el objetivo, la herramienta sugiere cerrarlo como Logrado y abrir el siguiente, sin hacerlo sola. Cambiar de rama (Tech Manager o Expert) lo cierra como Reemplazado. Un cambio de Track no lo cierra. Una Baja lo deja como estaba.
- **Quién propone**: el manager directo de la persona; lo carga el usuario.
