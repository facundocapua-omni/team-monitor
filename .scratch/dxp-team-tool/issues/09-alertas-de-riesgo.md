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
- marca manual de riesgo de fuga (depende de lo que permita la parte legal);
- Nivel de inglés por debajo del que requiere su Asignación.

**Restricciones ya decididas** (ver [Restricciones legales](01-restricciones-legales.md)):
- Las alertas se calculan al leer, a partir de reglas versionadas, y solo se guardan los descartes.
- Las reglas tienen que ser explicables: en España alimentan la ficha algorítmica que se entrega a cada persona y al comité de empresa.
- El riesgo de fuga queda pendiente de que Legal lo valide (ver [Requisitos de TI y Legal](08-requisitos-de-ti.md)). Si se incluye, es una entidad propia:
  - valores de una lista cerrada;
  - tiene caducidad;
  - se puede desactivar por jurisdicción;
  - queda fuera de exportes y reportes;
  - nunca se calcula a partir de otros datos.
