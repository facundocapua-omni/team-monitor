# Requisitos de TI y Legal para aprobar la herramienta

Type: task (HITL)
Status: open
Blocked by: —
Map: [map.md](../map.md)

## Question

¿Qué necesitan TI y Legal para aprobar una herramienta propia que guarda datos de personas?

Checklist para el usuario (conviene arrancar ya, porque la respuesta tarda):

- [ ] Proceso de aprobación de una herramienta interna construida por un área: quién aprueba y en qué plazos.
- [ ] Opciones de hosting (Google Cloud, servidor interno, otra) y si hay una plataforma estándar.
- [ ] Requisitos para Google SSO: cliente OAuth, dominio, grupos.
- [ ] Clasificación de datos: qué nivel tienen las evaluaciones de desempeño y los planes de carrera, y qué controles exige (cifrado, logs de acceso, backups, retención).
- [ ] Si mientras tanto se pueden tener estos datos en la laptop corporativa, y con qué condiciones (FileVault, sin sincronizar a nubes personales).
- [ ] Legal/DPO: quién es responsable del tratamiento en cada país y si la herramienta se registra como tratamiento de la entidad española.
- [ ] Legal/DPO: si se permite la marca manual de riesgo de fuga, y en qué jurisdicciones.
- [ ] Legal/DPO: la lista "Validar con Legal/DPO" de la investigación legal (`git show research/restricciones-legales:research/restricciones-legales.md`).

Se resuelve cuando TI y Legal respondieron y las respuestas quedan registradas aquí. Los trámites de cumplimiento en sí están fuera del alcance del mapa.
