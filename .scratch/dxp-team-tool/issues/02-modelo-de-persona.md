# Modelo de Persona

Type: grilling
Status: resolved
Assignee: Facundo Capua
Blocked by: —
Map: [map.md](../map.md)

## Question

¿Qué es una Persona en la herramienta?

- **Atributos**: cuáles son obligatorios y cuáles opcionales (Región, Rol, Seniority, Track, CMS, manager directo, país, fecha de ingreso…).
- **Línea de reporte**: cómo se representa, incluido el Expert, que no tiene gente a cargo, y el Tech Leader, que es a la vez Rol y nivel 8 de Seniority.
- **Cambios en el tiempo**: qué pasa cuando cambian el Rol, la Seniority o la Región, y si se guarda historial.
- **Altas y bajas**: cómo se modelan.

El modelo no debe impedir que más adelante haya permisos por Región.

**Restricciones ya decididas** (ver [Restricciones legales](01-restricciones-legales.md)):
- sin texto libre que pueda revelar datos sensibles, y sin campos de salario, salud, sindicato o familia;
- se puede exportar o borrar a una persona.

## Answer

Resuelta el 2026-10-08 en una sesión de grilling. Los términos nuevos (Persona, Vínculo, Ubicación, CMS principal, Movimiento, Ingreso, Baja) están en [`CONTEXT.md`](../../../CONTEXT.md).

- **Quién es una Persona**: toda la Línea de reporte, incluidos los externos (contratistas de proveedores y freelancers). Hoy la línea tiene dos raíces, los dos Tech Directors: el puesto de Global Tech Director no está formalizado y su función la cumple el Tech Director de Americas, que es el usuario. Cuando se formalice, el Global Tech Director entra como una Persona más y cada Tech Director recibe un Movimiento de cambio de manager.
- **Identidad**: el email corporativo, que también es lo que devolverá Google SSO.
- **Atributos**:

  | Atributo | Obligatoriedad |
  |---|---|
  | Nombre y apellido | obligatorio |
  | Email corporativo | obligatorio, único |
  | Rol | obligatorio; lista cerrada del handbook: Developer, Tech Leader, Tech Manager, Expert, Tech Director, Global Tech Director |
  | Seniority (L1–L8) | obligatoria para Developers y Tech Leaders; vacía para el resto |
  | Track | obligatorio para Developers y Tech Leaders; vacío para el resto |
  | CMS principal | obligatorio para Developers y Tech Leaders; opcional para el resto |
  | Manager | uno solo; vacío solo en los Tech Directors mientras no haya Global Tech Director |
  | País | obligatorio |
  | Ciudad | opcional |
  | Vínculo | obligatorio: empleado o externo, sin el nombre del proveedor |
  | Nivel de inglés | opcional; cada evaluación con su fecha, vale la última; "sin evaluar" no es A1 |

- **Lo que no se guarda**: fecha de nacimiento, género, foto, teléfono, dirección, ni nada de salario, salud o familia.
- **Rol y Seniority**: van por separado y pueden no coincidir. Un Tech Leader puede tener menos de L8 mientras se decide su ascenso, y se ve como un caso visible.
- **Región y Ubicación**: la Región se deriva siempre de la Línea de reporte y no se carga. La Ubicación (País y Ciudad) es dónde vive y trabaja la persona. Sirve para el staffing (la zona horaria sale del País, o de la Ciudad cuando el País tiene más de una) y para las reglas de España. La Ubicación no lleva historial.
- **Línea de reporte**: un solo manager, sin líneas punteadas. No se bloquean combinaciones fuera del esquema, como un Developer que reporta a un Tech Manager; se muestran. La única validación dura es que no haya ciclos.
- **Movimientos**: son el Ingreso, la Baja y los cambios de Rol, Seniority, Track o manager, cada uno con una fecha efectiva que puede no coincidir con la de carga y puede ser futura. El estado (por ingresar, activa o dada de baja) sale de los Movimientos. Con ellos se reconstruye la Línea de reporte en cualquier fecha. Una recontratación es un nuevo Ingreso de la misma Persona, que conserva su historial.
- **Ingreso**: cuenta la entrada a la Dirección, no a la empresa.
- **Baja**: es voluntaria o involuntaria, sin un motivo en texto libre, y no borra a la persona. Si alguien con gente a cargo se va, nada se bloquea: sus reportes aparecen como "reportan a alguien que se va" desde que se carga la Baja, y como "sin manager activo" después de la fecha. No hay retención automática en el MVP; solo se borra a pedido. La política de retención llega con el hosting de TI.
- **Externos**: se cargan como un Developer, con manager (el Tech Leader que los guía), Seniority equivalente en la escala del handbook, Track y CMS principal. El fin de contrato es una Baja.
