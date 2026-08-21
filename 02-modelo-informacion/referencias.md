# Referencias — Modelo de Información

## Fuentes primarias

| # | Fuente | Descripción |
|---|---|---|
| F1 | Sesión de levantamiento con Johanna Andrea Molina Rodríguez (transcripción, 25 min) | Estructura del directorio de extensiones, incidente de corrupción del archivo, descripción del cruce manual con la nómina. |
| F2 | Cuestionario de seguimiento vía Microsoft Teams | Confirmación de que la nómina contiene Id Empleado y correo; ubicación del directorio en OneDrive; volumen de ≈ 6.400 registros. |
| F3 | Muestra de la estructura del archivo de nómina | Encabezados: Id Empleado, Apellidos y Nombres completos, Departamento, Establecimiento, Nombre puesto/cargo, ID Posición, Dedicación, Estado HR, Clasificación empleado, Relación Organizativa, Código Directivo, Correo-E. |

> Los archivos fuente **no se publican en este repositorio** por contener datos personales de colaboradores de la Universidad.

## Estándar de modelado

- **Diagrama Entidad-Relación (ERD)** — notación de pie de gallo (*crow's foot*) para la representación de cardinalidades.
- **Diagrama de contexto** — representación de fuentes, destinos y flujos de información del sistema en estudio.

## Marco metodológico

- **TOGAF® Standard, Version 9.2** — The Open Group. Fase C: Information Systems Architecture — Data Architecture. Modelo lógico de datos, catálogo de entidades y diagrama de diseminación de datos.

## Marco normativo

- **Ley 1581 de 2012** — Régimen General de Protección de Datos Personales (Colombia).
- **Decreto 1377 de 2013** — Reglamentación parcial de la Ley 1581 de 2012.

## Documentación técnica consultada

- Microsoft Learn — Power Query: `Table.NestedJoin`, `Table.PromoteHeaders`, `Text.Trim`, `Text.Clean`, tipado explícito de columnas.
- Microsoft Learn — Causas frecuentes de fallo en funciones de búsqueda: discrepancia entre tipos numérico y texto, espacios finales y espacios no separables (`U+00A0`).
- Microsoft Learn — Microsoft Lists: tipos de columna, columnas de búsqueda e historial de versiones.

## Herramienta

- **draw.io (diagrams.net)** — Archivos fuente: `modelo-final-er.drawio` y `diagrama-contexto-final.drawio`.
