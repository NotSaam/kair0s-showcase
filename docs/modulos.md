<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="../assets/marca/logo-kair0s-fondo-oscuro.svg">
    <source media="(prefers-color-scheme: light)" srcset="../assets/marca/logo-kair0s-fondo-claro.svg">
    <img src="../assets/marca/logo-kair0s-fondo-claro.svg" alt="KAIR0S" width="260">
  </picture>
</p>

# Módulos

[← Volver al inicio](../README.md) · [Historia](historia.md)

KAIR0S tiene dos pilares: **datos y carga** (GPS, esfuerzo, wellness, asistencia y partidos) y **vídeo** (etiquetar el partido, cortar los clips y sacar el informe). Alrededor de ellos están la plantilla, la gestión del club y la web pública.

Todas las capturas usan **datos de ejemplo** de un club ficticio.

- **Datos y carga:** [Carga interna](#carga-interna) · [GPS](#gps) · [Wellness](#wellness) · [Entrenamientos y asistencia](#entrenamientos-y-asistencia) · [Partidos](#partidos)
- **Plantilla:** [Plantilla y ficha 360](#plantilla-y-ficha-360) · [Lesiones y disponibilidad](#lesiones-y-disponibilidad) · [Alineaciones](#alineaciones)
- **Vídeo:** [Vídeo](#vídeo)
- **Personas y club:** [App de la jugadora o el jugador](#app-de-la-jugadora-o-el-jugador) · [Gestión del club](#gestión-del-club) · [Panel de plataforma](#panel-de-plataforma) · [Web pública](#web-pública)

---

## Carga interna

La jugadora o el jugador marca su esfuerzo (RPE de 0 a 10) en unos 20 segundos. KAIR0S lo multiplica por los minutos efectivos y obtiene la carga de la sesión (sRPE). De ahí salen la carga semanal, el ACWR (EWMA o ratio 7:28) con su tendencia y la monotonía.

- Cada persona registra solo su esfuerzo; los minutos efectivos salen del GPS y, si la sesión no tiene GPS, los mete el staff.
- La carga se recalcula siempre al leerla, así que no importa que el GPS llegue después que el RPE.
- Todo es descriptivo: el ACWR se enseña como número con su tendencia, sin semáforos de riesgo.

<table>
  <tr>
    <td align="center" width="50%">
      <img src="../assets/app/carga-semanal-acwr.webp" alt="Carga semanal en barras y ACWR en su propia escala" width="320"><br>
      <sub>Carga semanal (sRPE) en barras y ACWR en su propia escala.</sub>
    </td>
    <td align="center" width="50%">
      <img src="../assets/app/staff-inicio-carga-semana.webp" alt="Tarjeta de carga del equipo en el inicio del staff, comparada con la semana previa" width="320"><br>
      <sub>Inicio del staff: la carga de la semana frente al mismo tramo de la anterior.</sub>
    </td>
  </tr>
</table>

## GPS

Importa el export del GPS del club: Catapult, STATSports u otro sistema asignando columnas. Un mismo fichero puede traer varias sesiones.

- Lee el título de la sesión del export (microciclo, día de partido y número de sesión) y lo deja confirmar y editar.
- Separa las tareas de la sesión (rondo, posesión, finalización…) y deja renombrar las genéricas.
- Da la distancia, los m/min, las zonas de velocidad 1–5, las aceleraciones y deceleraciones intensas y el % de cada variable frente al partido.
- Antes de guardar, todo se revisa en una vista previa editable.
- Solo aparecen quienes llevaron GPS ese día, y los nombres del export se emparejan con la plantilla aunque vengan escritos de otra forma.

<table>
  <tr>
    <td align="center" width="33%">
      <img src="../assets/app/gps-importacion-semana.webp" alt="Detalle de un entreno con el título del export del GPS separado en microciclo, día de partido y número de sesión, y la lista de entrenos del mes" width="240"><br>
      <sub>Detalle de un entreno: el título del export, leído como microciclo, día de partido y sesión.</sub>
    </td>
    <td align="center" width="33%">
      <img src="../assets/app/gps-perfiles-de-tarea.webp" alt="Perfiles de tarea filtrados por día de partido con minutos, distancia y metros por minuto" width="240"><br>
      <sub>Perfiles de tarea: minutos, distancia y m/min por tarea y día del microciclo.</sub>
    </td>
    <td align="center" width="33%">
      <img src="../assets/app/gps-zonas-de-velocidad.webp" alt="Distancia por zona de velocidad de la Z1 a la Z5" width="240"><br>
      <sub>Distancia por zona de velocidad, con las zonas del GPS del club.</sub>
    </td>
  </tr>
  <tr>
    <td align="center" colspan="3">
      <img src="../assets/app/carga-porcentaje-partido.webp" alt="Porcentaje de cada variable del microciclo frente a su media y frente al partido" width="320"><br>
      <sub>% por variable: el microciclo frente a su media y frente al partido.</sub>
    </td>
  </tr>
</table>

## Wellness

Cuestionario diario de sueño, fatiga, estrés, ánimo, dolor muscular y más, configurable por club: cada club puede ocultar o renombrar preguntas y añadir las suyas.

- Un semáforo por respuesta y, además, la comparación de cada persona con su propio historial de 28 días.
- Sin historial suficiente, la app lo dice con texto en lugar de pintar un color.
- El staff ve las medias del equipo pregunta a pregunta y cuántas personas van por debajo de lo habitual.

<table>
  <tr>
    <td align="center" width="33%">
      <img src="../assets/app/jugador-wellness.webp" alt="Cuestionario de wellness en el móvil con escalas de 1 a 5" width="240"><br>
      <sub>Cuestionario de wellness: escalas de 1 a 5 y el valor elegido en texto.</sub>
    </td>
    <td align="center" width="33%">
      <img src="../assets/app/staff-inicio-wellness-equipo.webp" alt="Medias de wellness del equipo por pregunta y cuántas personas van por debajo de lo habitual" width="240"><br>
      <sub>Inicio del staff: medias de wellness del equipo, pregunta a pregunta.</sub>
    </td>
    <td align="center" width="33%">
      <img src="../assets/app/ficha-wellness-historial.webp" alt="Ficha 360 con el wellness de una persona comparado con su propio historial de 28 días" width="240"><br>
      <sub>Ficha 360: cada respuesta frente al propio historial de 28 días.</sub>
    </td>
  </tr>
</table>

## Entrenamientos y asistencia

Una hoja de sesión única recoge asistencia, RPE, minutos y carga con un solo guardado.

- Se pueden crear entrenos sin GPS y recibir igualmente el RPE de cada uno.
- Matriz de asistencia por microciclo.
- Exportación a CSV preparada para abrirse en Excel.

<p align="center">
  <img src="../assets/app/sesion-asistencia-rpe-carga.webp" alt="Hoja de sesión con asistencia, RPE, minutos y sRPE de cada persona" width="320"><br>
  <sub>Hoja de sesión: asistencia, RPE, minutos y sRPE por persona.</sub>
</p>

## Partidos

Cada partido guarda rival, jornada, campo, competición, resultado, convocatoria y estadísticas individuales.

- La asistencia al partido sale de la convocatoria, sin marcarla dos veces.
- Los minutos jugados nunca pueden superar a los disponibles.
- Cada once guardado y cada lesión pueden quedar ligados a su partido o a su sesión.

## Plantilla y ficha 360

Cada jugadora o jugador tiene una ficha con carga, wellness, asistencia, partidos y lesiones en una sola pantalla.

- La plantilla se da de alta en bloque pegando una lista.
- La ficha enseña la carga de la semana en curso, el wellness respecto a su propio historial y su disponibilidad.

## Lesiones y disponibilidad

Registro ligero, sin datos clínicos: tipo, zona, sesión en la que ocurrió, vuelta estimada e historial.

- La disponibilidad (disponible, readaptación o lesión) se calcula sola a partir de la lesión activa.
- La app marca «Revisar» cuando una vuelta está a 7 días o menos o se ha retrasado.
- El estado nunca cambia sin que el staff lo decida.

<p align="center">
  <img src="../assets/app/staff-disponibilidad-lesiones.webp" alt="Panel de disponibilidad con lesiones activas, vuelta prevista y la marca «Revisar»" width="320"><br>
  <sub>Disponibilidad: lesiones activas, vuelta prevista y la marca «Revisar».</sub>
</p>

## Alineaciones

Fútbol 11 con 10 sistemas (4-3-3, 4-4-2, 4-2-3-1, 3-5-2…).

- Arrastrar y soltar con ratón, con el dedo en la tablet o con el teclado.
- Cualquier persona de la plantilla puede ir en cualquier hueco: la posición de la ficha es solo una ayuda visual.
- Los onces se guardan, se pueden vincular a su partido y llevan un resumen.

## Vídeo

Pensado para la cámara táctica del partido.

- **Etiquetar.** Sobre el vídeo local, sin subirlo, con atajos de teclado: saques de banda y de puerta, córners, faltas, tiros y goles, por equipo y con jugadora o jugador y nota opcionales.
- **Informe.** Línea de tiempo del partido, mapa de tiros y la calidad de cada ocasión (clara, media o lejana). También en PDF A4 para compartirlo desde el iPad o el móvil.
- **Clips.** Se cortan en un ZIP con una carpeta por tipo de evento, con los segundos antes y después que elija cada club.
- **Nada se queda.** El vídeo se borra al terminar; solo se guardan los eventos y el informe.

<p align="center">
  <img src="../assets/app/video-sala-etiquetado.webp" alt="Sala de etiquetado de vídeo con la línea de tiempo, seis botones de evento y la lista de eventos" width="360"><br>
  <sub>Sala de etiquetado: línea de tiempo, seis tipos de evento y lista de eventos.</sub>
</p>

## App de la jugadora o el jugador

Pantallas «Hoy», RPE, wellness, «Mis datos» y asistencia. Se instala como app en el móvil.

- «Hoy» dice qué falta por registrar: el wellness del día y las sesiones sin valorar.
- Cada persona ve solo sus propios datos.

<table>
  <tr>
    <td align="center" width="50%">
      <img src="../assets/app/jugador-hoy.webp" alt="Pantalla «Hoy» en el móvil con el wellness del día pendiente y tres sesiones sin valorar" width="300"><br>
      <sub>«Hoy»: el wellness del día y las sesiones que faltan por valorar.</sub>
    </td>
    <td align="center" width="50%">
      <img src="../assets/app/jugador-rpe-escala.webp" alt="Escala de esfuerzo de 0 a 10 de una sesión pendiente, en el móvil" width="300"><br>
      <sub>RPE de una sesión: escala de 0 a 10 con botones grandes.</sub>
    </td>
  </tr>
</table>

## Gestión del club

- Invitaciones por enlace, pensadas para compartirse por WhatsApp.
- Una cuenta para varios clubes, con selector para cambiar de uno a otro.
- Guía de primeros pasos y ayuda por rol.
- Descarga de los datos del club en un ZIP de CSV con un clic.
- Plantilla femenina o masculina: toda la app concuerda (jugadora o jugador, lesionada o lesionado…).

## Panel de plataforma

Para gestionar KAIR0S: clubes, usuarios y uso agregado (nunca datos individuales).

## Web pública

Landing con arte 3D renderizado en Blender; cómo está hecha se cuenta en [Cómo se ha construido](../README.md#cómo-se-ha-construido).

<table>
  <tr>
    <td align="center" width="50%">
      <img src="../assets/landing/landing-campo-3d.webp" alt="Render 3D del campo visto desde arriba con el círculo central en teal" width="360"><br>
      <sub>La landing: el campo vacío, con el círculo central en teal.</sub>
    </td>
    <td align="center" width="50%">
      <img src="../assets/landing/landing-alineacion-3d.webp" alt="Render 3D de una alineación 4-3-3 vista en cenital con el 8 resaltado" width="360"><br>
      <sub>La alineación 4-3-3 en cenital, con el 8 en su hueco.</sub>
    </td>
  </tr>
</table>

---

<sub>© 2026 Samu (FLK0S). Todos los derechos reservados. Este repositorio no contiene código fuente.</sub>
