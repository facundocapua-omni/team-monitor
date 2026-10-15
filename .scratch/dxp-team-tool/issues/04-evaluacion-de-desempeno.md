# Evaluación de desempeño

Type: grilling
Status: resolved
Assignee: Facundo Capua
Blocked by: —
Map: [map.md](../map.md)

## Question

¿Qué forma tiene la Evaluación de desempeño que se carga?

- Escala, frecuencia del ciclo y quién la produce.
- Si se guarda solo la última o también el historial.
- Cómo se usa en el staffing: como filtro, para ordenar, o solo como dato visible.

No debe mezclarse con los Delivery KPIs. El handbook prohíbe atribuírselos a un Developer; en Tech Leaders y Tech Managers ya entran como insumo de su evaluación.

**Restricciones ya decididas** (ver [Restricciones legales](01-restricciones-legales.md)): en el staffing, la evaluación puede ordenar o marcar, pero nunca excluir automáticamente a nadie.

**Decidido en [Modelo de Persona](02-modelo-de-persona.md)**:
- hay externos en la Dirección. Falta decidir si tienen Evaluación de desempeño.

## Answer

Resuelta el 2026-10-15 en una sesión de grilling. Los términos (Evaluación de desempeño, Calificación final, Key player) están en [`CONTEXT.md`](../../../CONTEXT.md).

- **Qué se carga**: la Calificación final, de 1 a 5 con decimales, y nada del cálculo: ni competencias ni componentes. Más la marca de Key player, que vale para ese ciclo.
- **Quién y cuándo**: ciclo anual; la pone el manager directo de la persona.
- **Historial**: se conservan todas, cada una con su ciclo. Vale la última; si no es del ciclo más reciente, se ve como de un ciclo anterior.
- **Sin evaluar**: una persona sin Evaluación no es lo mismo que una con resultado bajo, y la herramienta no las confunde.
- **Externos**: no tienen Evaluación. Su líder les da feedback, que no se registra.
- **Uso en el staffing**: dato visible, nada más. No entra en ningún orden ni filtro calculado; quien decide es el usuario. Esto es más estricto que la regla legal ("ordenar o marcar, nunca excluir"), y deja a [Alertas de riesgo](../issues/09-alertas-de-riesgo.md) la pregunta de si una Calificación baja puede generar una alerta.
- **Delivery KPIs**: siguen fuera. En Tech Leaders y Tech Managers cuentan en la evaluación como insumo, pero la herramienta solo guarda la Calificación final.
