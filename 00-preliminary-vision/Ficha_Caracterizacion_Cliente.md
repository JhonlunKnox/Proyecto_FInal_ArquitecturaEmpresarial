# Ficha de Caracterización del Cliente

**Nombre del Equipo:** Alejandro Riveros, Juan Pablo Luna, Martin Ortega  
**Fecha:** 21/08/2026  
**Nombre del Cliente (real o simulado):** Universidad de La Sabana  
**Rol/Organización:** Jefatura de Cultura de innovación y servicio  

---

## I. Información General del Negocio

- **Nombre de la empresa o entidad:** Universidad de La Sabana
- **Sector económico:** Académico
- **Número de empleados:** 2
- **Ubicación principal (física o digital):** Campus Puente del Común, Chia (Cundinamarca) Colombia. Presencia digital a través del portal institucional.
- **Tecnologías principales actuales (si aplica):**
  - Buzon institucional de PQRSF
  - Canales de atención, exceptuando redes sociales: Atención telefónica, WhatsApp y correo electrónico institucional
  - Directorio de extensiones telefónicas en hoja de cálculo alojada en OneDrive, compartida en modo solo lectura con las gestoras.
  - Suite Microsoft 365 como plataforma corporativa: Excel, Teams, Outlook, OneDrive y Power Automate con licenciamiento estándar.
  - Plataforma de telefonía institucional (PBX), administrada por la Dirección de Tecnología.
  - Sistema de información de Desarrollo Humano, del cual se exporta mensualmente la nómina.

---

## II. Objetivos estratégicos del cliente

**¿Cuáles son los 2–3 objetivos estratégicos principales del cliente?**

1. **Mejorar la experiencia de servicio de los grupos de interés:** Garantizar que cualquier persona que contacte a la universidad sea atendida y dirigida correctamente en el primer contacto.
2. **Asegurar la vigencia y confiabilidad de la información operativa de servicio:** Mantener actualizada la información que soporta la atención al público, de modo que las decisiones operativas de las gestoras se apoyen en datos confiables.
3. **Optimizar el uso del tiempo del equipo de la unidad:** Liberar al personal de tareas manuales repetitivas de bajo valor agregado, para redirigirlo hacia actividades de mejora de la experiencia de servicio.

---

## III. Problemas o necesidades identificadas

Se nos mencionó que el área de atención Telefónica presentaba un problema en el directorio de extensiones que tenían las personas encargadas de llevar las llamadas al momento de redirigirlas al área encargada, pues el Excel que tienen con el paso de los meses se va desactualizando y muchas veces a Johanna se le dificulta mantener contacto constante con la persona encargada en tecnología, por lo que hay muchas extensiones que o bien son inutilizables ya sea porque la persona que la maneja se retiró de su cargo o bien este cambio.

Al analizar la situación Podemos identificar dos problemas:

### 1. Conciliación manual entre la nómina y el directorio de extensiones

La actualización del directorio exige contrastar manualmente, registro por registro, el archivo de nómina institucional contra el directorio de extensiones. El archivo de nómina, tal como se descarga del sistema de Desarrollo Humano, no admite el cruce mediante funciones de búsqueda, lo que obliga a revisar individualmente cerca de 6.400 registros para identificar entre 5 y 10 novedades mensuales.

### 2. Ausencia de un canal de notificación bidireccional con la Dirección de Tecnología

Cuando se requiere aprovisionar o liberar una extensión, la solicitud se realiza verbalmente o por Teams durante una reunión que debe agendarse previamente, con esperas registradas de hasta tres semanas y cancelaciones por ambas partes. El registro afectado se marca en el directorio como «pendiente por aprovisionar».

La Dirección de Tecnología ejecuta el aprovisionamiento y contacta directamente al usuario, pero no existe ningún mecanismo que informe de vuelta a la unidad que el proceso concluyó. En consecuencia, el marcador «pendiente por aprovisionar» permanece indefinidamente y las gestoras no saben si pueden transferir llamadas a esa persona. En términos de proceso, se trata de un estado del cual no existe transición de salida.

---

## IV. Procesos clave del negocio

**Describa brevemente 2–3 procesos centrales de la organización.**

### Proceso 1: Atención y transfiere de llamadas telefónicas

La gestora de servicio contesta la llamada entrante, identifica la necesidad del usuario y consulta el directorio de extensiones para determinar la unidad competente. Si la encuentra, transfiere la llamada; de lo contrario, informa al usuario que no es posible direccionarlo.

### Proceso 2: Mantenimiento y actualización del director de extensiones

Desarrollo Humano publica la nómina del mes vencido, disponible aproximadamente el día 15 del mes siguiente. La profesional de Experiencia y Servicio la descarga y la contrasta manualmente contra el directorio para identificar ingresos, retiros, cambios de cargo y posiciones vacantes. Posteriormente agenda una reunión con el analista de aprovisionamiento de la Dirección de Tecnología para revisar conjuntamente las novedades, marca los registros afectados como «pendiente por aprovisionar» y actualiza el archivo compartido con las gestoras.

### Proceso 3: Aprovisionamiento y liberación de extensiones telefónicas

Desarrollo Humano determina qué cargos tienen derecho a extensión telefónica, criterio que se aplica a los cargos con atención al público. Cuando ingresa un colaborador que cumple el criterio, la Dirección de Tecnología aprovisiona la extensión y la comunica directamente al usuario. De manera simétrica, ante un retiro debe liberarse la extensión correspondiente.

---

## V. Expectativas frente a la solución

**¿Qué espera el cliente que se resuelva o mejore con la arquitectura propuesta? ¿Hay restricciones técnicas, legales o de tiempo relevantes?**

En este caso Johanna espera que nuestra solución pueda brindarle que al momento de presentarse un cambio en la nómina se le notifique de manera oportuna si se requiere actualizar algún valor del directorio que se tiene en el momento, para de esta manera no tener que depender de reunirse con la persona encargada, para brindar velocidad y el correcto manejo de los datos para que las personas encargadas de las llamadas puedan brindar respuesta de manera correcta y actualizada en todo momento.

En cuanto a las restricciones se nos mencionó que la universidad impone bastante restricción al momento de crear cualquier tipo de arquitectura pues bien el área de tecnología en un caso presentado el semestre pasado no se pudo implementar pues mencionaron que no se conocía bien si podía presentar fugas de información, garantizar al 100% de donde provenía este software, también la universidad en su mayoría se rige por infraestructura proveniente de Microsoft y que tienen que seguir ciertas políticas impuestas para poder ser descargado en un dispositivo brindado por la universidad.

### Restricciones Relevantes

| Tipo | Restricción |
|---|---|
| **Técnica** | La solución debe implementarse exclusivamente sobre la suite Microsoft 365 con que cuenta la Universidad. No se admite software externo ni desarrollos que requieran instalación local: su instalación exige comité, expediente y revisión de código por parte de Seguridad Informática, con un tiempo de aprobación que excede la duración del proyecto. Antecedente: en un semestre anterior, un equipo entregó un desarrollo propio que no pudo ser instalado por esta razón. |
| **Técnica** | Se dispone de licenciamiento estándar de Power Automate; no se garantiza la disponibilidad de conectores premium. Cada conector debe validarse con el cliente antes de ser propuesto. |
| **Operativa** | El entregable debe ser un documento de configuración paso a paso, implementable y mantenible por la propia unidad, cuya responsable es Administradora de Empresas. El criterio de éxito no es la sofisticación del artefacto, sino su viabilidad de implantación y su sostenibilidad. |
| **Legal** | El directorio y la nómina contienen datos personales (nombres, cargos, correos, identificación). Su tratamiento se rige por la Ley 1581 de 2012. El uso es estrictamente académico y restringido a los integrantes del equipo; queda prohibida su divulgación a terceros. |
| **De información** | La nómina es el único insumo de novedades disponible y se entrega mes vencido (≈ día 15 del mes siguiente). Desarrollo Humano no reporta novedades de forma directa. Esto impone un desfase estructural de hasta 45 días entre el evento real y su detección, que ninguna automatización puede eliminar. |
| **De tiempo** | El proyecto se desarrolla en tres cortes académicos, con cierre el 13 de noviembre de 2026. La disponibilidad del cliente está condicionada por su agenda; la comunicación se acordó por Microsoft Teams. |

---

## VI. Persona de contacto

- **Nombre del contacto:** Johanna Andrea Molina Rodríguez
- **Correo electrónico / teléfono (si aplica):** JohannaMR@unisabana.edu.co
- **Rol o vínculo con la solución:** Profesional del frente de Experiencia y Servicio, Dirección de Desarrollo Estratégico. Es la responsable directa del mantenimiento del directorio de extensiones telefónicas: ejecuta la conciliación con la nómina y gestiona las solicitudes de aprovisionamiento ante la Dirección de Tecnología. Será igualmente quien implemente y opere la solución propuesta al interior de la unidad.
