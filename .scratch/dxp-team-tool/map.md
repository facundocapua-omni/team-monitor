# Herramienta de gestión de la Dirección DXP

Label: wayfinder:map
Tickets: [issues/](issues/)

## Destination

**Spec del MVP de la herramienta de gestión de la Dirección DXP**: uso personal del Global Tech Director, ~150 personas en 2 Regiones, centrada en staffing, planificación de contratación y alertas de riesgo (más reportes hacia arriba derivados de los mismos datos), con carga manual. Lista para construir, con la plataforma decidida y viable dentro de las restricciones de TI.

## Notes

- **Dominio**: glosario en [`CONTEXT.md`](../../CONTEXT.md). La fuente canónica de roles, Seniority, Tracks, CMS y Delivery KPIs es el handbook en `../structure/src/content/docs/` (sitio local: http://localhost:4322/).
- **Skills**: en cada ticket de decisión, `grilling` + `domain-modeling`; actualizar `CONTEXT.md` cuando un término se resuelve.
- **Idioma**: la conversación es en español.
- **Usuario**: solo el Global Tech Director. El modelo no debe impedir permisos por Región ni que más adelante cada Tech Manager cargue lo suyo.
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

## Not yet specified

- **Ausencias y vacaciones**: el handbook define la capacidad neta de ausencias. Todavía no está claro si el staffing del MVP las necesita ni con qué detalle; se aclara después del modelo de Proyecto, Asignación y Necesidad.
- **Historial y auditoría**: si se guarda la evolución de Seniority, Asignaciones, Evaluaciones de desempeño y Nivel de inglés. Lo van a ir pidiendo los tickets de modelo y los reportes; cuando converja, puede pedir un ticket propio.
- **Forma de la spec final**: si se entrega como documento único o por módulos, y en qué orden de construcción se parte para implementarla con IA. Se define cuando el modelo y las pantallas estén claros.

## Out of scope

- **Multiusuario, permisos por Región y carga por los Tech Managers**: el MVP es de uso personal; solo se exige que el modelo no lo impida. Decidido al trazar el mapa.
- **Google SSO y hosting corporativo**: llegan después; la arquitectura solo debe dejar el camino abierto. Al dar ese paso aplica el análisis legal completo (ver [Restricciones legales](issues/01-restricciones-legales.md)).
- **Integraciones con Jira, HRIS u otros sistemas**: no hay un sistema unificado; la carga es manual con import inicial.
- **Delivery KPIs**: los produce el esfuerzo de Delivery Metrics Automation (`../structure/docs/superpowers/specs/2026-10-06-delivery-metrics-automation-design.md`) y nunca se muestran por Developer.
- **Notas de 1:1 y flujo de promociones o calibraciones**: no entraron entre las prioridades del MVP.
- **Definir la escala de Seniority, los career paths o los criterios de evaluación**: son del handbook, no de la herramienta.
