# Herramienta de gestión de la Dirección DXP

Label: wayfinder:map
Tickets: [issues/](issues/)

## Destination

**Spec del MVP de la herramienta de gestión de la Dirección DXP**: uso personal del Tech Director de Americas, que cumple de hecho la función de Global Tech Director; ~150 personas en 2 Regiones, centrada en staffing, planificación de contratación y alertas de riesgo (más reportes hacia arriba derivados de los mismos datos), con carga manual. Lista para construir, con la plataforma decidida y viable dentro de las restricciones de TI.

## Notes

- **Dominio**: glosario en [`CONTEXT.md`](../../CONTEXT.md). La fuente canónica de roles, Seniority, Tracks, Plataformas y Delivery KPIs es el handbook en `../structure/src/content/docs/` (sitio local: http://localhost:4322/).
- **Skills**: en cada ticket de decisión, `grilling` + `domain-modeling`; actualizar `CONTEXT.md` cuando un término se resuelve.
- **Idioma**: la conversación es en español.
- **Usuario**: solo el Tech Director de Americas, que cumple de hecho la función de Global Tech Director (el puesto no está formalizado). El modelo no debe impedir permisos por Región ni que más adelante cada Tech Manager cargue lo suyo.
- **Escala**: Americas ~100 personas (Colombia, Panamá, Ecuador, Chile, Argentina); EMEA ~50 (España; posible expansión a EAU, Arabia Saudita, Egipto, Jordania).
- **Prioridades del MVP, en orden**: staffing, planificación de contratación, alertas de riesgo. Reportes hacia arriba solo si salen casi gratis.
- **Carga de datos**: manual por ahora; el import solo sirve para la carga inicial desde planillas existentes.
- **Stack (decidido)**: construcción propia con Next.js + Tailwind + shadcn/ui, SQLite + Drizzle ORM y SheetJS para importar. Auth.js con Google SSO llega más adelante. La construye el propio usuario acelerando con IA; plazo: lo antes posible.
- **Hosting**: local en la máquina del usuario; después, hosting aprobado por TI con Google SSO.
- **Regla dura**: "KPI" significa Delivery KPI de equipo. Nunca se muestran Delivery KPIs en el perfil de un Developer. Lo individual es la Evaluación de desempeño.
- **Datos reales**: nunca se commitean datos de personas en este repo.

## Decisions so far

<!-- one line per closed ticket: [title](link): gist -->

- [Restricciones legales para guardar datos de personas](issues/01-restricciones-legales.md): la herramienta no cambia la base legal, porque reorganiza datos que el usuario ya trata y para los mismos fines. Lo nuevo a cuidar: los datos que se crean (riesgo de fuga), las reglas que ordenan o filtran gente (sugieren, nunca excluyen; consultar a RRHH para España) y la seguridad de la base concentrada.
- [Modelo de Persona](issues/02-modelo-de-persona.md): toda la Línea de reporte, externos incluidos, identificada por email corporativo. La Región se deriva del manager y la Ubicación (País y Ciudad) va aparte. Rol y Seniority van por separado. El historial son Movimientos con fecha efectiva (Ingreso, Baja, Rol, Seniority, Track, manager), que pueden ser futuros.
- [Modelo de Proyecto, Asignación y Necesidad](issues/03-proyecto-asignacion-necesidad.md): el Proyecto pertenece a un Cliente (lo interno es la propia empresa), tiene Región cargada y Estado (Preventa, En curso, Cerrado, Perdido). Las Asignaciones son tramos de dedicación fija, tentativos o confirmados, con Función (Liderazgo técnico o Desarrollo), y cualquier Rol puede tenerlas. Una Necesidad es una posición en un Proyecto. La Capacidad descuenta las Indisponibilidades, que no llevan motivo. El bench se llama Dojo: Developers y Tech Leaders sin Asignación confirmada.
- [Evaluación de desempeño](issues/04-evaluacion-de-desempeno.md): el resultado anual es una Calificación final de 1 a 5 que pone el manager directo, con marca opcional de Key player. Se conservan todas por ciclo y vale la última. Los externos no tienen. En el staffing es un dato visible: no entra en ningún orden ni filtro calculado.
- [Skills de una persona](issues/05-skills.md): la Plataforma (las seis del handbook, que reemplaza a CMS) es la unidad. Cada Skill es una Plataforma con Nivel de dominio (Conoce, Autónomo, Referente) propuesto por el manager y revisado una vez al año. La Experiencia en Plataforma se calcula de las Asignaciones y es solo evidencia. Cualquier Persona tiene Skills; el Proyecto declara sus Plataformas y la Necesidad pide una con nivel mínimo. Sin certificaciones.

## Not yet specified

- **Forma de la spec final**: si se entrega como documento único o por módulos, y en qué orden de construcción se parte para implementarla con IA. Se define cuando el modelo y las pantallas estén claros.

## Out of scope

- **Multiusuario, permisos por Región y carga por los Tech Managers**: el MVP es de uso personal; solo se exige que el modelo no lo impida. Decidido al trazar el mapa.
- **Google SSO y hosting corporativo**: llegan después; la arquitectura solo debe dejar el camino abierto. Al dar ese paso aplica el análisis legal completo (ver [Restricciones legales](issues/01-restricciones-legales.md)).
- **Integraciones con Jira, HRIS u otros sistemas**: no hay un sistema unificado; la carga es manual con import inicial.
- **Delivery KPIs**: los produce el esfuerzo de Delivery Metrics Automation (`../structure/docs/superpowers/specs/2026-10-06-delivery-metrics-automation-design.md`) y nunca se muestran por Developer.
- **Notas de 1:1 y flujo de promociones o calibraciones**: no entraron entre las prioridades del MVP.
- **Vacaciones cortas, feriados y registro de quién cambió qué**: la capacidad neta de ausencias del handbook es para los Delivery KPIs, y el registro de cambios llega con el multiusuario. Las licencias largas sí entran, como Indisponibilidad (ver [Modelo de Proyecto, Asignación y Necesidad](issues/03-proyecto-asignacion-necesidad.md)).
- **Definir la escala de Seniority, los career paths o los criterios de evaluación**: son del handbook, no de la herramienta.
