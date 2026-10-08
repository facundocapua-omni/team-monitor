# Arquitectura técnica

Type: grilling
Status: open
Blocked by: 01, 08
Map: [map.md](../map.md)

## Question

El stack ya está decidido: Next.js, Tailwind, shadcn/ui, SQLite + Drizzle, SheetJS, y Auth.js con Google más adelante. A la luz de las restricciones de TI, falta decidir:

- dónde vive el archivo SQLite y cómo se cifra en reposo;
- cómo se hacen los backups;
- cómo se evita que datos reales terminen en git o en nubes personales;
- cuál es el camino de migración al hosting de TI con Google SSO: si pasa a Postgres y qué cambia en el código.

**Restricciones ya decididas** (ver [Restricciones legales](01-restricciones-legales.md)):
- la base vive fuera del repo y fuera de nubes personales, con el disco cifrado;
- se puede exportar o borrar a una persona;
- al pasar al hosting de TI aplica el análisis legal completo; por ejemplo, un log de accesos.
