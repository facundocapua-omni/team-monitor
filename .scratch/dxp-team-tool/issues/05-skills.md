# Skills de una persona

Type: grilling
Status: resolved
Assignee: Facundo Capua
Blocked by: —
Map: [map.md](../map.md)

## Question

¿Con qué granularidad se registran las skills de una persona? Opciones:

- Track + CMS, con un nivel de dominio.
- Ítems del roadmap de su Track (Essential, Recommended u Optional en el handbook).
- Certificaciones.

También hay que decidir qué escala de nivel se usa, quién la evalúa y cada cuánto se revisa. Tiene que servir para cruzar la oferta con las Necesidades y para detectar huecos.

**Decidido en [Modelo de Persona](02-modelo-de-persona.md)**:
- cada Developer y Tech Leader tiene un Track y un **CMS principal** en su Persona, y ese CMS es el que cuenta en el headcount. Este ticket decide cómo se registran los otros CMS que maneja y su nivel en cada uno.

## Answer

Resuelta el 2026-10-15 en una sesión de grilling. Los términos (Plataforma, Plataforma principal, Skill, Nivel de dominio, Experiencia en Plataforma) están en [`CONTEXT.md`](../../../CONTEXT.md).

- **Para qué**: encontrar candidatos para una Necesidad, detectar huecos de Plataforma y detectar concentración de riesgo. Seguir el desarrollo de cada persona es del [Plan de carrera](06-plan-de-carrera.md).
- **Plataforma reemplaza a CMS**: son las seis del handbook (Optimizely Cloud, Contentful, AEM EDS, AEM Traditional, Adobe Commerce PaaS y SaaS). La Plataforma principal sigue siendo una sola por persona y la que cuenta en el headcount.
- **Granularidad**: cada Skill es una Plataforma con un Nivel de dominio y la fecha de su última revisión. No se registran los ítems del roadmap. Las certificaciones quedan fuera del MVP, porque no cambian ninguna decisión.
- **Nivel de dominio**: Conoce, Autónomo o Referente, definidos por lo que la persona puede hacer en un Proyecto y no por la Seniority. Lo propone el manager directo, se revisa una vez al año junto con la Evaluación de desempeño y se ve vencido si es más viejo. Vale solo el último, sin historial.
- **Experiencia en Plataforma**: se calcula con los meses en Asignaciones confirmadas a Proyectos de esa Plataforma, con cualquier Función. Es evidencia para el nivel y no lo cambia sola. Una Plataforma con experiencia pero sin Skill se muestra como candidata a agregar. Solo cuenta lo cargado en la herramienta.
- **Quién**: cualquier Persona, externos incluidos. La Plataforma principal es obligatoria en Developers y Tech Leaders.
- **Proyecto**: declara una o más Plataformas, obligatorio en los En curso y en Preventa de Clientes externos; lo interno puede declarar "ninguna".
- **Necesidad**: una Plataforma como máximo, con Nivel de dominio mínimo (Autónomo si no se indica). Al buscar candidatos se marca qué requisitos cumple cada uno, sin ocultar a nadie. El orden de la lista se resuelve en [Pantallas del MVP](14-pantallas-del-mvp.md).
