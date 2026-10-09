<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/marca/logo-kair0s-fondo-oscuro.svg">
    <source media="(prefers-color-scheme: light)" srcset="assets/marca/logo-kair0s-fondo-claro.svg">
    <img src="assets/marca/logo-kair0s-fondo-claro.svg" alt="KAIR0S" width="340">
  </picture>
</p>

<p align="center">
  <strong>KAIR0S, el momento decisivo.</strong><br>
  Plataforma de rendimiento y vídeo para equipos de fútbol.
</p>

<p align="center">
  Diseñado y desarrollado por <strong>Samu (FLK0S)</strong> en unos cuatro meses: app web instalable, dos servicios de datos, sistema de diseño propio y arte 3D.<br>
  540 commits y más de 4.500 tests automatizados.
</p>

<p align="center">
  <a href="https://kair0s.es/r/web">kair0s.es</a> ·
  <a href="https://kair0s.es/r/instagram">Instagram @kair0s.es</a> ·
  <a href="mailto:info@kair0s.es">info@kair0s.es</a>
</p>

<p align="center">
  <img src="https://kair0s.es/badge/visitas.svg" alt="Visitas al escaparate">
  <a href="https://kair0s.es/r/web"><img src="https://kair0s.es/badge/clics-web.svg" alt="Clics a la web"></a>
  <a href="https://kair0s.es/r/instagram"><img src="https://kair0s.es/badge/clics-instagram.svg" alt="Clics a Instagram"></a>
</p>

<p align="center">
  <img src="assets/marca/banner-kair0s.png" alt="Logo de KAIR0S junto a un campo de fútbol renderizado en 3D: el panel de carga, lesiones y vídeo de tu equipo de fútbol" width="100%">
</p>

> [!NOTE]
> Este repositorio es un **escaparate**: enseña qué es KAIR0S y cómo se ha construido. **No contiene código fuente.** Todas las capturas usan **datos de ejemplo** de un club ficticio.

## Índice

- [El problema](#el-problema)
- [Qué hace](#qué-hace)
- [Para quién](#para-quién)
- [Cómo funciona](#cómo-funciona)
- [Principios](#principios)
- [Cómo se ha construido](#cómo-se-ha-construido)
- [Historia](#historia)
- [Cifras](#cifras)
- [Enlaces y autor](#enlaces-y-autor)
- [In English](#in-english)

## El problema

Un cuerpo técnico de fútbol trabaja cada semana con datos de muchos sitios: el export del GPS, el esfuerzo (RPE) que cada jugadora o jugador da tras el entreno, el cuestionario de wellness de cada mañana, la lista de asistencia, las estadísticas del partido y el vídeo. Lo normal es cruzarlo todo a mano en hojas de cálculo, con fórmulas que se rompen, nombres que no cuadran entre ficheros y horas que deberían ir al campo.

KAIR0S junta todo eso en una sola app. El staff lo trabaja desde el iPad o el ordenador, y la plantilla registra lo suyo desde el móvil en unos segundos.

## Qué hace

Un resumen por áreas. El detalle de cada módulo está en **[docs/modulos.md](docs/modulos.md)**.

### La app de la jugadora o el jugador

Cada mañana, el wellness. Después de cada sesión, el esfuerzo de 0 a 10. En «Hoy» ve qué le falta por registrar y en «Mis datos», su semana. Se instala en el móvil como una app.

<table>
  <tr>
    <td align="center" width="33%">
      <img src="assets/app/jugador-hoy.webp" alt="Pantalla «Hoy» en el móvil con el wellness del día pendiente y tres sesiones sin valorar" width="260"><br>
      <sub>«Hoy»: el wellness del día y las sesiones que faltan por valorar.</sub>
    </td>
    <td align="center" width="33%">
      <img src="assets/app/jugador-rpe-escala.webp" alt="Escala de esfuerzo de 0 a 10 de una sesión pendiente, en el móvil" width="260"><br>
      <sub>RPE de una sesión: escala de 0 a 10 con botones grandes.</sub>
    </td>
    <td align="center" width="33%">
      <img src="assets/app/jugador-wellness.webp" alt="Cuestionario de wellness en el móvil con escalas de 1 a 5" width="260"><br>
      <sub>Cuestionario de wellness: escalas de 1 a 5 y el valor elegido en texto.</sub>
    </td>
  </tr>
</table>

### El día a día del staff

El inicio reúne la carga de la semana, el wellness del equipo y quién está disponible. La hoja de sesión recoge asistencia, RPE, minutos y carga con un solo guardado.

<table>
  <tr>
    <td align="center" width="50%">
      <img src="assets/app/staff-inicio-carga-semana.webp" alt="Tarjeta de carga del equipo en el inicio del staff, comparada con la semana previa" width="340"><br>
      <sub>Inicio del staff: la carga de la semana frente al mismo tramo de la anterior.</sub>
    </td>
    <td align="center" width="50%">
      <img src="assets/app/staff-inicio-wellness-equipo.webp" alt="Medias de wellness del equipo por pregunta y cuántas personas van por debajo de lo habitual" width="340"><br>
      <sub>Inicio del staff: medias de wellness del equipo, pregunta a pregunta.</sub>
    </td>
  </tr>
  <tr>
    <td align="center" width="50%">
      <img src="assets/app/staff-disponibilidad-lesiones.webp" alt="Panel de disponibilidad con lesiones activas, vuelta prevista y la marca «Revisar»" width="340"><br>
      <sub>Disponibilidad: lesiones activas, vuelta prevista y la marca «Revisar».</sub>
    </td>
    <td align="center" width="50%">
      <img src="assets/app/sesion-asistencia-rpe-carga.webp" alt="Hoja de sesión con asistencia, RPE, minutos y sRPE de cada persona" width="340"><br>
      <sub>Hoja de sesión: asistencia, RPE, minutos y sRPE por persona.</sub>
    </td>
  </tr>
</table>

### GPS

El staff sube el export del GPS del club (Catapult, STATSports u otro sistema asignando columnas). KAIR0S lee el título de la sesión, separa las tareas y da distancia, m/min, zonas de velocidad 1–5 y aceleraciones y deceleraciones intensas. Antes de guardar, todo se revisa en una vista previa editable.

<table>
  <tr>
    <td align="center" width="33%">
      <img src="assets/app/gps-importacion-semana.webp" alt="Detalle de un entreno con el título del export del GPS separado en microciclo, día de partido y número de sesión, y la lista de entrenos del mes" width="260"><br>
      <sub>Detalle de un entreno: el título del export, leído como microciclo, día de partido y sesión.</sub>
    </td>
    <td align="center" width="33%">
      <img src="assets/app/gps-perfiles-de-tarea.webp" alt="Perfiles de tarea filtrados por día de partido con minutos, distancia y metros por minuto" width="260"><br>
      <sub>Perfiles de tarea: minutos, distancia y m/min por tarea y día del microciclo.</sub>
    </td>
    <td align="center" width="33%">
      <img src="assets/app/gps-zonas-de-velocidad.webp" alt="Distancia por zona de velocidad de la Z1 a la Z5" width="260"><br>
      <sub>Distancia por zona de velocidad, con las zonas del GPS del club.</sub>
    </td>
  </tr>
</table>

### Carga, wellness y ficha 360

La carga interna sale de multiplicar el esfuerzo por los minutos efectivos (sRPE). De ahí, la carga semanal, el ACWR con su tendencia, la monotonía y el % de cada variable frente al partido. El wellness de cada persona se compara con su propio historial. Y la ficha 360 lo junta todo por persona: carga, wellness, asistencia, partidos y lesiones.

<table>
  <tr>
    <td align="center" width="33%">
      <img src="assets/app/carga-semanal-acwr.webp" alt="Carga semanal en barras y ACWR en su propia escala" width="260"><br>
      <sub>Carga semanal (sRPE) en barras y ACWR en su propia escala.</sub>
    </td>
    <td align="center" width="33%">
      <img src="assets/app/carga-porcentaje-partido.webp" alt="Porcentaje de cada variable del microciclo frente a su media y frente al partido" width="260"><br>
      <sub>% por variable: el microciclo frente a su media y frente al partido.</sub>
    </td>
    <td align="center" width="33%">
      <img src="assets/app/ficha-wellness-historial.webp" alt="Ficha 360 con el wellness de una persona comparado con su propio historial de 28 días" width="260"><br>
      <sub>Ficha 360: cada respuesta frente al propio historial de 28 días.</sub>
    </td>
  </tr>
</table>

### Vídeo y partidos

<table>
  <tr>
    <td width="45%" align="center">
      <img src="assets/app/video-sala-etiquetado.webp" alt="Sala de etiquetado de vídeo con la línea de tiempo, seis botones de evento y la lista de eventos" width="340"><br>
      <sub>Sala de etiquetado: línea de tiempo, seis tipos de evento y lista de eventos.</sub>
    </td>
    <td width="55%" valign="top">
      <p><strong>Vídeo.</strong> El analista etiqueta el partido sobre el vídeo en su propio ordenador, sin subirlo, con atajos de teclado: saques, córners, faltas, tiros y goles. El informe trae línea de tiempo, mapa de tiros y la calidad de cada ocasión, y se descarga también en PDF para compartirlo desde el iPad o el móvil. Los clips se cortan en un ZIP con una carpeta por tipo de evento y el vídeo se borra al terminar.</p>
      <p><strong>Partidos.</strong> Rival, jornada, campo, competición, resultado, convocatoria y estadísticas individuales.</p>
      <p><strong>Alineaciones.</strong> Fútbol 11 con 10 sistemas, arrastrando fichas también en la tablet. Cada once se puede guardar vinculado a su partido.</p>
    </td>
  </tr>
</table>

### Gestión del club

Invitaciones por enlace que se comparten por WhatsApp, alta de la plantilla pegando una lista, una cuenta para varios clubes, primeros pasos y ayuda por rol, plantilla femenina o masculina y descarga de los datos del club en un ZIP de CSV con un clic.

## Para quién

| Quién | Qué hace con KAIR0S |
|---|---|
| **Staff** (preparador físico, entrenador, analista) | Sube el GPS, pasa lista, ve la carga y el wellness del equipo y de cada persona, gestiona lesiones y alineaciones, etiqueta el vídeo y saca el informe del partido. |
| **Jugadoras y jugadores** | Registran su wellness y su esfuerzo desde el móvil y ven solo sus propios datos: su semana y su asistencia. |
| **El club** | Tiene sus datos aislados de los de cualquier otro club e invita a su gente por enlace. |

## Cómo funciona

1. **El club empieza.** El staff da de alta la plantilla pegando una lista e invita a cada jugadora o jugador con un enlace.
2. **Cada día se registra.** La plantilla contesta el wellness y da su RPE desde el móvil. El staff pasa lista y sube el export del GPS.
3. **KAIR0S calcula.** Minutos efectivos, sRPE, carga semanal, ACWR, zonas de velocidad y % frente al partido. Si el GPS llega después que el RPE, la carga se recalcula sola.
4. **El staff decide.** Con el inicio, la ficha 360, el informe del partido y los clips, cada decisión parte de los datos de la semana.

## Principios

- **Los datos de cada club, aislados.** Cada club ve solo lo suyo, y eso lo impone la propia base de datos, no la pantalla. Cada jugadora o jugador ve solo sus propios datos.
- **Alojado en la Unión Europea.**
- **Descriptivo, no predictivo.** KAIR0S enseña lo que ha pasado: el ACWR va como número con su tendencia, sin semáforos de riesgo. El estado de una lesión nunca cambia sin que el staff lo decida.
- **Solo lo necesario.** Las lesiones se registran sin datos clínicos. El vídeo no se sube para etiquetar y se borra al cortar los clips.
- **Móvil e iPad primero.** Se instala como app, los botones y campos táctiles miden 44 px, la hoja de sesión se ve como tabla en el iPad y es compatible con Safari de iOS 15 en adelante.
- **Los datos son del club.** Con un clic, el club descarga sus datos en un ZIP de CSV.

## Cómo se ha construido

KAIR0S es un monorepo con una web, dos servicios de datos y un sistema de diseño propio. A alto nivel:

| Capa | Tecnología |
|---|---|
| Web y PWA | Next.js (App Router), React, TypeScript, Tailwind CSS y Recharts para los gráficos |
| Datos | Supabase (Postgres, autenticación y almacenamiento) con seguridad a nivel de fila: el aislamiento entre clubes lo garantiza la base de datos |
| Servicios | Python con FastAPI: uno importa el GPS y otro gestiona el vídeo (subida reanudable y corte con ffmpeg) |
| Documentos | Informe del partido en PDF vectorial generado en el servidor |
| Arte | Blender (Cycles) para los renders de la web, servidos como AVIF y WebP |
| Infraestructura | Contenedores Docker, alojamiento en la UE y copias diarias de la base de datos |

**Calidad.** Tests automatizados en todas las capas (Vitest en la web, pytest en los servicios y Playwright de extremo a extremo, también en WebKit simulando un iPhone), pruebas de permisos y aislamiento entre clubes en la propia base de datos e integración continua con GitHub Actions. Unas reglas automáticas vigilan el diseño y los textos: colores fuera de la paleta, tamaños de letra, vocabulario prohibido y afirmaciones que el producto no cumple.

**Sistema de diseño propio.** Tokens, componentes y una galería interna con datos ficticios. Un único lenguaje visual para toda la app, con cifras que suben y gráficos que se dibujan al cargar, respetando la opción de reducir movimiento.

**Arte 3D en Blender.** La web pública es una pizarra de partido renderizada en 3D. Una sola toma continua acompaña al scroll y cuenta la semana en cinco historias. Funciona sin JavaScript y con «reducir movimiento», y pesa poco en la primera visita.

<table>
  <tr>
    <td align="center" width="50%">
      <img src="assets/landing/landing-campo-3d.webp" alt="Render 3D del campo visto desde arriba con el círculo central en teal" width="380"><br>
      <sub>La landing: el campo vacío, con el círculo central en teal.</sub>
    </td>
    <td align="center" width="50%">
      <img src="assets/landing/landing-tiros-3d.webp" alt="Render 3D de marcas de tiro sobre el área, con los goles en teal" width="380"><br>
      <sub>Los tiros sobre el área, por calidad de la ocasión; los goles, en teal.</sub>
    </td>
  </tr>
  <tr>
    <td align="center" width="50%">
      <img src="assets/landing/landing-alineacion-3d.webp" alt="Render 3D de una alineación 4-3-3 vista en cenital con el 8 resaltado" width="380"><br>
      <sub>La alineación 4-3-3 en cenital, con el 8 en su hueco.</sub>
    </td>
    <td align="center" width="50%">
      <img src="assets/landing/landing-decisivo-3d.webp" alt="Render 3D en macro de la ficha del 8 con un aro teal" width="380"><br>
      <sub>El cierre de la landing: la ficha del 8 en macro, con su aro teal.</sub>
    </td>
  </tr>
</table>

**Marca.** El logo «Cero de medio campo»: el cero de KAIR0S es el círculo central del campo. Con él salen los favicons, los iconos de la app y la imagen para compartir.

<p align="center">
  <img src="assets/marca/marca-cero-de-medio-campo.png" alt="Lámina de marca con el isotipo, el wordmark, el avatar, los favicons y la versión sobre fondo claro" width="720"><br>
  <sub>Identidad «Cero de medio campo»: isotipo, wordmark, avatar y favicons.</sub>
</p>

## Historia

Desarrollado por Samu (FLK0S) entre junio y octubre de 2026. Los hitos principales:

| Cuándo | Qué llegó |
|---|---|
| Junio 2026 | Arranque: cuentas, roles y clubes aislados. Importación del GPS, carga, wellness y partidos. Plantilla, ficha 360, lesiones y alineaciones. Panel de plataforma. Módulo de vídeo completo. |
| Finales de junio y julio | Zonas de velocidad, compatibilidad con iPhone, minutos efectivos y carga derivada. Rediseño del inicio, la analítica y la ficha 360 tras las primeras rondas de feedback de cuerpo técnico. |
| Agosto | Primer despliegue en producción. La app se puede instalar como PWA. |
| Septiembre | Web pública y base de calidad (tests en CI, copias de la base de datos). Invitaciones, entrenamientos y asistencia. Primeros pasos y exportación de datos. Cuenta multi-club, partidos completos y club demo. Importador GPS de varios fabricantes. Sistema de diseño v2 y rediseño de toda la app. |
| Octubre | Landing con arte 3D en Blender. Auditoría completa y QA en producción. Logo «Cero de medio campo». Experiencia táctil en tablet y móvil. Informe del partido en PDF. Plantilla femenina o masculina. Recuperación de contraseña por correo. |

La historia completa, con fechas, está en **[docs/historia.md](docs/historia.md)**.

## Cifras

| Cifra | Valor |
|---|---|
| **Periodo** | 7 jun – 9 oct 2026, unos 4 meses |
| **Commits** | 540 |
| **Tests automatizados** | Más de 4.500: más de 4.200 de la web y 330 de los servicios Python |
| **Pruebas de extremo a extremo** | 5 suites de Playwright; en la CI corren las que no necesitan cuenta, en Chromium, y la de iPhone, en WebKit |
| **Permisos y aislamiento entre clubes** | Más de 680 comprobaciones en 12 scripts de prueba de la base de datos |
| **Pantallas** | 59: 47 de la app, 5 de la web pública y 7 de acceso |
| **Tamaño** | Unas 143.000 líneas de TypeScript (41.000 de tests) y unas 22.000 de Python |
| **Plataformas** | Web responsive, PWA instalable y uso táctil en iPad, tablet y móvil; compatible con Safari de iOS 15 en adelante (la CI rechaza cualquier código que ese Safari no entienda) |
| **Idioma** | Castellano, con plantilla femenina o masculina por club |

## Enlaces y autor

- **Web:** [kair0s.es](https://kair0s.es/r/web)
- **Instagram:** [@kair0s.es](https://kair0s.es/r/instagram)
- **Contacto:** [info@kair0s.es](mailto:info@kair0s.es)

Diseñado y desarrollado por **Samu · FLK0S**.

---

## In English

**KAIR0S** ("the decisive moment") is a performance and video platform for football teams. It brings together, in one web app and installable PWA, what a coaching staff usually juggles in spreadsheets: GPS exports, session RPE and training load (sRPE, weekly load, ACWR), daily wellness, attendance, match stats, squad and injury management, line-ups and video tagging with clip export and a PDF match report. Players log their wellness and effort from their phone in seconds; the staff works from an iPad or a laptop.

Principles: each club's data is isolated at the database level, hosting is in the EU, the numbers are descriptive rather than predictive, and the app is built mobile and tablet first.

Built by Samu (FLK0S) between June and October 2026: 540 commits, 4,500+ automated tests, 59 screens. Stack: Next.js, TypeScript, Supabase/Postgres with row-level security, Python/FastAPI services, ffmpeg, Docker, and Blender for the 3D artwork of the public site. All screenshots use sample data from a fictional club.

This repository is a showcase only and contains no source code.

---

<sub>© 2026 Samu (FLK0S). Todos los derechos reservados. Este repositorio no contiene código fuente.</sub>
