# Arquitectura Empresarial — Universidad de La Sabana

**Equipo:** Adictos al Azucar · Juan Pablo Luna Zuleta, Alejandro Riveros, Martín Ortega
**Curso:** Arquitectura Empresarial — Universidad de La Sabana
**Cliente:** Jefatura de Cultura de Innovación y Servicio — Dirección de Desarrollo Estratégico

---

## 📌 En una frase

Rediseñamos cómo la Jefatura de Cultura de Innovación y Servicio mantiene actualizado su directorio de extensiones telefónicas, para que las llamadas de estudiantes, aspirantes y visitantes lleguen siempre a la persona correcta.

---

## 🩺 El problema

Las gestoras que atienden el teléfono de la Universidad usan un directorio de extensiones para redirigir cada llamada al área competente. Ese directorio se mantiene a mano: cada mes hay que comparar cerca de 6.400 registros contra la nómina para encontrar entre 5 y 10 novedades, y luego coordinar con Tecnología en reuniones que muchas veces se cancelan.

El resultado es que el directorio se actualiza cada dos o tres meses en lugar de cada mes. Cuando eso pasa, la llamada se transfiere a un área equivocada, o a una extensión donde ya no trabaja nadie y nadie contesta.

---

## 💡 Lo que proponemos

- Que el cruce entre la nómina y el directorio se haga solo, y que en lugar de revisar miles de filas la unidad reciba una lista corta con las novedades del mes ya clasificadas: quién entró, quién salió, quién cambió de cargo.
- Que exista un canal directo con Tecnología para pedir una extensión y, sobre todo, para que Tecnología avise de vuelta cuando ya quedó lista. Hoy ese aviso de retorno no existe.
- Que el directorio deje de ser un archivo suelto y pase a ser una fuente de información institucional, con estructura, permisos e historial de cambios.
- Todo construido sobre las herramientas que la Universidad ya tiene licenciadas, para que la unidad pueda implementarlo y mantenerlo sin depender de nosotros ni de aprobaciones externas.

---

## 🗺️ Cómo se implementa

Ver el [Resumen Ejecutivo](ResumenEjecutivo.md) — ahí está el detalle de beneficios esperados, fases de implementación y tiempos, en un solo documento pensado para el negocio, no para el equipo técnico.

---

## 📂 Si quiere ver el detalle técnico completo

Todo el análisis que sustenta esta propuesta está documentado carpeta por carpeta, siguiendo el método usado durante el proyecto:

| Carpeta | Qué contiene | Estado |
|---|---|---|
| `00-preliminary-vision/` | Contexto del cliente y visión de la solución | ✅ Corte 1 |
| `01-bpmn/` | Cómo funciona hoy el proceso de negocio analizado | ✅ Corte 1 |
| `02-modelo-informacion/` | Qué información maneja el negocio y cómo fluye | ✅ Corte 1 |
| `03-arquitectura-c4/` | Los sistemas actuales y cómo están construidos | 🔜 Corte 2 |
| `04-infraestructura/` | Dónde corre todo hoy y qué riesgos técnicos tiene | 🔜 Corte 2 |
| `05-seguridad-stride/` | Análisis de seguridad de la información | 🔜 Corte 2 |
| `06-normatividad/` | Cumplimiento legal y normativo | 🔜 Corte 2 |
| `07-opportunities-solutions/` | La solución propuesta y qué brechas cierra | 🔜 Corte 2 |
| `08-integracion-vistas/` | Cómo se conecta todo lo anterior en una sola arquitectura | 🔜 Corte 3 |
| `09-presentacion-final/` | Presentación ejecutiva, plan de implementación y gobernanza | 🔜 Corte 3 |

---

## 🔒 Nota sobre los datos

Este repositorio **no contiene** el directorio de extensiones ni archivos de nómina. Ambos incluyen datos personales de colaboradores de la Universidad y su tratamiento se rige por la Ley 1581 de 2012. Los modelos y ejemplos publicados aquí usan datos ficticios o estructuras sin contenido real.

---

## 👥 Contacto

Juan Pablo Luna Zuleta — jplz39333@gmail.com — GitHub: [JhonlunKnox](https://github.com/JhonlunKnox)
