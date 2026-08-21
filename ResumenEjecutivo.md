# Resumen Ejecutivo

**Cliente:** Jefatura de Cultura de Innovación y Servicio — Universidad de La Sabana
**Proyecto:** Actualización del Directorio de Extensiones Telefónicas
**Documento dirigido a:** el negocio. No requiere conocimientos técnicos para leerse.

---

## 1. La situación hoy

Cuando alguien llama a la Universidad, una gestora de servicio contesta, entiende qué necesita esa persona y la transfiere al área correspondiente. Para saber a dónde transferir, consulta un directorio de extensiones telefónicas.

Ese directorio se mantiene manualmente. Cada mes llega la nómina —con retraso de un mes— y hay que compararla, registro por registro, contra el directorio para detectar quién entró a la Universidad, quién salió y quién cambió de cargo. Después hay que coordinar con la Dirección de Tecnología para pedir que asignen o liberen las extensiones correspondientes.

**El esfuerzo es desproporcionado frente al resultado:**

| | |
|---|---|
| Registros que hay que revisar cada ciclo | ~6.400 |
| Novedades reales que aparecen al mes | 5 a 10 |
| Proporción | Cerca de **800 registros revisados por cada novedad encontrada** |
| Duración de la revisión conjunta con Tecnología | 2 a 3 horas |
| Frecuencia con que debería actualizarse | Mensual |
| Frecuencia con que se logra en la práctica | Cada 2 o 3 meses |

Además de lo anterior, hay dos obstáculos concretos:

**El archivo de nómina no permite hacer el cruce automáticamente.** Aunque contiene la misma información, la forma en que se descarga del sistema impide usar las funciones de búsqueda de Excel, y obliga a la revisión uno a uno.

**Tecnología no avisa cuando termina.** Cuando se pide una extensión nueva, el registro queda marcado como "pendiente por aprovisionar". Tecnología la asigna y llama al colaborador, pero no informa de vuelta a la unidad. La marca se queda ahí indefinidamente y las gestoras no saben si ya pueden transferir llamadas a esa persona.

---

## 2. Por qué importa

El costo no lo asume la unidad: lo asume quien llama.

Cuando el directorio está desactualizado, la llamada se transfiere a un área que no corresponde, o a una extensión donde ya no trabaja nadie y simplemente nadie contesta. Un estudiante, un aspirante o un visitante externo tiene la experiencia de que la Universidad no supo atenderlo.

Hoy esas fallas no se registran ni se miden, por lo que la unidad no tiene visibilidad de cuántas veces ocurren.

---

## 3. Lo que proponemos

### Que el cruce se haga solo

En lugar de revisar 6.400 filas, la unidad recibirá cada mes un reporte corto con las novedades ya clasificadas:

- **Ingresó** una persona que por su cargo debería tener extensión
- **Se retiró** una persona que tenía extensión asignada
- **Cambió de cargo o de unidad** alguien ya registrado
- **Quedó vacante** una extensión sin titular

Todo lo que no cambió, simplemente no aparece.

### Que exista un canal de ida y vuelta con Tecnología

Desde el mismo reporte, la unidad podrá enviar la solicitud a Tecnología sin necesidad de agendar una reunión. Y cuando Tecnología confirme que ya asignó la extensión, esa confirmación actualizará el directorio automáticamente y retirará la marca de "pendiente".

Si una solicitud lleva demasiados días sin respuesta, el sistema lo recuerda por sí solo.

### Que el directorio sea información institucional

Hoy el directorio es un archivo alojado en el espacio personal de una colaboradora, sin historial de cambios y vulnerable a que un error de manipulación lo dañe —algo que ya ocurrió una vez y obligó a reconstruirlo.

Proponemos moverlo a un espacio institucional donde tenga estructura definida, permisos claros, registro de quién cambió qué y cuándo, y consulta cómoda para las gestoras desde el computador o el celular.

### Sin salirse de lo que la Universidad ya tiene

Toda la propuesta se construye sobre las herramientas que la Universidad ya licencia y que Seguridad Informática ya aprobó. No hay software externo, no hay nada que instalar, no hay que pasar por comité.

Esto responde directamente a lo que ocurrió en un semestre anterior, cuando un desarrollo entregado por otro equipo nunca pudo implementarse.

---

## 4. Beneficios esperados

| Situación actual | Situación propuesta |
|---|---|
| Revisión manual de 6.400 registros | Reporte automático con 5 a 10 novedades |
| Reunión de 2 a 3 horas con Tecnología | Validación breve del reporte |
| Solicitudes verbales sin registro | Solicitudes estructuradas y trazables |
| Sin confirmación de Tecnología | Confirmación que actualiza el directorio sola |
| Marca "pendiente" indefinida | Vencimiento y recordatorio automático |
| Actualización cada 2 o 3 meses | Actualización mensual sostenida |
| Archivo personal sin historial | Fuente institucional con trazabilidad |

---

## 5. Lo que esta solución no resuelve

Conviene ser explícitos.

La nómina llega con un mes de retraso y es el único insumo disponible. Eso significa que siempre habrá un desfase de hasta 45 días entre el momento en que alguien cambia de cargo y el momento en que la unidad se entera. Ninguna automatización puede eliminar ese retraso: la información simplemente no existe antes.

Lo que sí se compensa parcialmente es el caso de los ingresos nuevos, porque el canal con Tecnología captura esa novedad en el momento en que ocurre, sin esperar a la nómina.

La recomendación de fondo —que Desarrollo Humano reporte las novedades directamente a la unidad— es un cambio de coordinación entre áreas, no un cambio técnico, y queda planteado como oportunidad de mejora.

---

## 6. Cómo se implementa

### Fase 1 — Preparar la información
Corregir el formato del archivo de nómina para que permita el cruce automático, y agregar al directorio el identificador de empleado que hoy solo existe en la nómina. Este identificador es lo que permite emparejar ambas fuentes de forma confiable, incluso cuando hay varias personas con el mismo cargo en la misma unidad.

### Fase 2 — Trasladar el directorio
Migrar el directorio a un espacio institucional con estructura definida y permisos por rol. Las gestoras mantienen la consulta; la edición queda controlada y registrada.

### Fase 3 — Automatizar el cruce
Configurar el proceso que compara nómina y directorio y produce el reporte mensual de novedades.

### Fase 4 — Conectar con Tecnología
Habilitar el canal de solicitud y el de confirmación de retorno, junto con el recordatorio automático para las solicitudes que se queden sin respuesta.

### Fase 5 — Entregar y acompañar
Documento de configuración paso a paso, acompañamiento en la puesta en marcha y verificación de que la unidad puede operar y mantener la solución por su cuenta.

---

## 7. Qué necesitamos del cliente

- Confirmación de los permisos disponibles en las herramientas de Microsoft 365.
- Una muestra del archivo de nómina para verificar y corregir el problema de formato.
- Aclaración de la correspondencia entre las categorías de unidad que maneja la nómina y las que maneja el directorio.
- El criterio documentado de qué cargos tienen derecho a extensión telefónica.
- Validación de este resumen antes de avanzar al diseño detallado.

---

## 8. Criterio de éxito

El proyecto será exitoso si, tres meses después de terminado, la unidad sigue usando la solución sin necesidad de nuestra intervención.

No buscamos entregar el sistema más sofisticado posible, sino el que la unidad pueda operar y mantener por sí misma dentro de las herramientas que ya tiene.

---

*Documento en elaboración. Las cifras corresponden a lo declarado por el cliente durante el levantamiento de información. Última actualización: agosto de 2026.*
