# Informe — Modelado de Procesos (BPMN)

> Fase Business Architecture — TOGAF ADM · Corte 1 (AS-IS)
> Archivo del modelo: [`modelo-final.drawio`](modelo-final.drawio)

---

## 1. Alcance del modelado

Se modelaron dos procesos del frente de atención telefónica de la Jefatura de Cultura de Innovación y Servicio:

| Proceso | Razón para modelarlo |
|---|---|
| **P1 — Atención y transferencia de llamadas** | Es donde se manifiesta el problema ante el usuario final. |
| **P2 — Mantenimiento del directorio de extensiones** | Es la causa del problema y el proceso objeto de intervención. |

El proceso de aprovisionamiento técnico ejecutado por la Dirección de Tecnología no se modeló en detalle porque su ejecución interna queda fuera del alcance; sí se representa su interacción con P2.

---

## 2. Catálogo de actores

| Actor | Rol de negocio | Unidad |
|---|---|---|
| Usuario final | Solicitante de atención | Externo / comunidad universitaria |
| Gestora de servicio (×4) | Operador del canal telefónico | Jefatura de Cultura de Innovación y Servicio |
| Profesional de Experiencia y Servicio | Administrador del directorio | Jefatura de Cultura de Innovación y Servicio |
| Jefe de Cultura de Innovación y Servicio | Responsable del proceso de servicio | Jefatura de Cultura de Innovación y Servicio |
| Analista de aprovisionamiento | Asigna y libera extensiones telefónicas | Dirección de Tecnología |
| Desarrollo Humano | Proveedor de la información de planta | Dirección de Desarrollo Humano |
| Unidad destino | Receptor de la llamada transferida | Facultades y unidades administrativas |

---

## 3. Catálogo de capacidades y funciones

| Capacidad | Función de negocio | Estado AS-IS |
|---|---|---|
| Atención multicanal | Atención telefónica | Operativa — dependiente de la calidad del directorio |
| Atención multicanal | Atención por WhatsApp y correo | Fuera de alcance |
| Gestión de PQRSF | Buzón «Comunícate con Nosotros» | Fuera de alcance |
| Gestión de la información de servicio | Mantenimiento del directorio de extensiones | **Manual, con desfase de 2 a 3 meses** |
| Gestión de la información de servicio | Conciliación con la planta de personal | **Manual, registro por registro** |
| Gestión de recursos de telefonía | Aprovisionamiento y liberación de extensiones | Ejecutada por Tecnología, sin retroalimentación |
| Medición de la experiencia | Encuestas de percepción y satisfacción | Fuera de alcance |

---

## 4. Proceso 1 — Atención y transferencia de llamadas

### 4.1. Descripción

La gestora de servicio contesta la llamada entrante, identifica la necesidad del usuario y consulta el directorio de extensiones para determinar la unidad competente. Si la encuentra, transfiere la llamada; de lo contrario, informa al usuario que no es posible direccionarlo.

### 4.2. Estructura del modelo

**Carriles:** Usuario final · Gestora de servicio · Unidad destino

**Flujo:**

1. `(Inicio)` El usuario realiza la llamada
2. La gestora contesta
3. La gestora identifica la necesidad del usuario
4. La gestora consulta el directorio de extensiones
5. `<Compuerta>` ¿Encuentra la unidad competente?
   - **No** → Informa que no es posible direccionar → `(Fin)`
   - **Sí** → Transfiere la llamada a la extensión
6. `<Compuerta>` ¿Contesta alguien en la unidad destino?
   - **Sí** → Atiende la solicitud → `(Fin)`
   - **No** → `(Fin)` sin atención

### 4.3. Puntos de falla

| ID | Falla | Causa |
|---|---|---|
| **F1** | Transferencia a la unidad equivocada | El directorio contiene información desactualizada. |
| **F2** | Extensión sin responsable asignado | La persona se retiró y la extensión no fue liberada ni reasignada. |

Ninguna de las dos fallas se registra ni se mide, por lo que la unidad no tiene visibilidad de su frecuencia. **Esta ausencia de medición es en sí misma un hallazgo:** no existe indicador que permita dimensionar el impacto del problema sobre el usuario final.

---

## 5. Proceso 2 — Mantenimiento del directorio de extensiones

### 5.1. Descripción

Ciclo mensual (objetivo) de actualización del directorio a partir de la nómina institucional, con coordinación manual con la Dirección de Tecnología para el aprovisionamiento de extensiones.

### 5.2. Estructura del modelo

**Carriles:** Desarrollo Humano · Profesional de Experiencia y Servicio · Dirección de Tecnología · Gestoras de servicio

**Flujo:**

1. `(Inicio · Evento temporal)` Cierre de mes
2. **[Desarrollo Humano]** Publica la nómina del mes vencido (≈ día 15 del mes siguiente)
3. **[Experiencia y Servicio]** Descarga el archivo de nómina
4. **[Experiencia y Servicio]** Compara manualmente registro por registro contra el directorio (≈ 6.400 filas) — **B1**
5. **[Experiencia y Servicio]** Identifica novedades (5 a 10 por mes)
6. **[Experiencia y Servicio]** Solicita reunión con la Dirección de Tecnología — **B2**
7. **[Ambos]** Revisan las novedades en reunión de 2 a 3 horas
8. **[Tecnología]** Aprovisiona o libera la extensión
9. **[Tecnología]** Contacta al usuario y le entrega la extensión
10. **[Experiencia y Servicio]** Marca el registro como «pendiente por aprovisionar» — **B3**
11. **[Experiencia y Servicio]** Actualiza el directorio compartido
12. **[Gestoras]** Consultan el directorio en modo solo lectura
13. `<Compuerta>` ¿El registro está marcado como pendiente?
    - **Sí** → No transfieren llamadas a esa persona
    - **No** → `(Fin)` Transferencia habilitada

### 5.3. Puntos de bloqueo

| ID | Bloqueo | Efecto medible |
|---|---|---|
| **B1** | El archivo de nómina no admite cruce automatizado por funciones de búsqueda | Obliga a revisar ≈ 6.400 registros manualmente para hallar 5–10 novedades |
| **B2** | Dependencia del agendamiento de una reunión entre dos personas | Esperas de hasta 3 semanas; cancelaciones por ambas partes |
| **B3** | Ausencia de confirmación de retorno desde Tecnología | El estado «pendiente por aprovisionar» no tiene transición de salida |
| **B4** | Frecuencia real de ejecución bimensual o trimestral | El directorio permanece desactualizado la mayor parte del tiempo |

### 5.4. Hallazgo: el estado absorbente

El punto **B3** merece atención particular. La secuencia real es:

```
VIGENTE ──solicitud──▶ PENDIENTE POR APROVISIONAR ──✗ no existe transición──▶ ?
```

La Dirección de Tecnología ejecuta el aprovisionamiento y contacta al usuario, pero no informa de vuelta a la unidad. El marcador permanece indefinidamente en el directorio, y las gestoras interpretan que aún no pueden transferir llamadas a esa persona — incluso cuando la extensión ya está operativa.

En términos de modelado de procesos, se trata de un **estado del que no existe transición de salida**. Es la falla estructural más clara del proceso y el fundamento del requerimiento RQ3 del Architecture Vision.

---

## 6. Mapa de interacciones

| Origen | Destino | Intercambio | Medio | Estado |
|---|---|---|---|---|
| Desarrollo Humano | Experiencia y Servicio | Nómina mensual (mes vencido) | Archivo | Operativo, con desfase |
| Experiencia y Servicio | Dirección de Tecnología | Solicitud de aprovisionamiento | Teams / reunión | Operativo, sin registro |
| Dirección de Tecnología | Experiencia y Servicio | Confirmación de aprovisionamiento | — | **Inexistente** |
| Dirección de Tecnología | Unidad destino | Entrega de la extensión al colaborador | Llamada | Operativo |
| Experiencia y Servicio | Gestoras de servicio | Directorio actualizado | OneDrive (solo lectura) | Operativo, desactualizado |
| Usuario final | Gestoras de servicio | Llamada entrante | Telefonía | Operativo |
| Gestoras de servicio | Unidad destino | Transferencia de llamada | Telefonía | Operativo, con fallas |

**El único enlace ausente del mapa es la confirmación de retorno desde Tecnología.** Un solo vínculo faltante explica la mayor parte del desfase acumulado del directorio.

---

## 7. Indicadores del estado actual

| Indicador | Valor | Fuente |
|---|---|---|
| Registros revisados por ciclo | ≈ 6.400 | Declarado por el cliente |
| Novedades reales por mes | 5 a 10 | Declarado por el cliente |
| Relación señal/ruido | ≈ 0,12 % | Cálculo propio sobre los dos anteriores |
| Duración de la revisión conjunta | 2 a 3 h (originalmente 8 h) | Declarado por el cliente |
| Tiempo de espera para agendamiento | Hasta 3 semanas | Declarado por el cliente |
| Latencia de la fuente de datos | Hasta 45 días | Derivado del ciclo de nómina |
| Frecuencia objetivo / real | Mensual / bimensual–trimestral | Declarado por el cliente |
| Fallas de transferencia | **Sin medición** | — |

---

## 8. Conclusiones del modelado

1. El problema visible (llamadas mal transferidas) es un **síntoma**; la causa está en el proceso de mantenimiento del directorio, no en el de atención.
2. Los tres bloqueos de P2 son de naturaleza distinta y requieren tratamientos distintos: **B1** es un problema de formato de datos, **B2** de dependencia de coordinación, **B3** de ausencia de protocolo.
3. La ausencia de medición sobre las fallas de transferencia impide dimensionar el impacto real sobre el usuario. Se recomienda incorporar un mecanismo de registro como parte del TO-BE.
4. La secuencia de bloqueos es acumulativa: aunque se resolviera B1, el ciclo seguiría dependiendo de B2 y B3. Una intervención parcial no recupera la periodicidad mensual.
