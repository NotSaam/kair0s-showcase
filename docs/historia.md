<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="../assets/marca/logo-kair0s-fondo-oscuro.svg">
    <source media="(prefers-color-scheme: light)" srcset="../assets/marca/logo-kair0s-fondo-claro.svg">
    <img src="../assets/marca/logo-kair0s-fondo-claro.svg" alt="KAIR0S" width="260">
  </picture>
</p>

# Historia del proyecto

[← Volver al inicio](../README.md) · [Módulos](modulos.md)

KAIR0S es una plataforma web y PWA para cuerpos técnicos de fútbol. Junta en una sola app la carga de entrenamiento (RPE, GPS, wellness y asistencia), los partidos, la plantilla y el análisis de vídeo.

Samu (FLK0S) la ha diseñado y desarrollado entre junio y octubre de 2026: 540 commits y más de 4.500 tests automatizados.

La pensó para el día a día real: las jugadoras y jugadores usan el móvil y el staff usa el iPad. Cada club tiene sus datos aislados, y todo está alojado en la Unión Europea.

## Hitos

### Junio 2026: los cimientos y los módulos base

| Fecha | Hito | Qué aporta |
|---|---|---|
| 7–8 jun | Cimientos: cuentas, roles y clubes aislados | Cada club ve solo sus datos, y esto lo impone la base de datos, no la pantalla. Hay tres roles: staff, jugadora o jugador, y administración. |
| 8–9 jun | Primeros módulos: GPS, carga, wellness y partidos | El staff sube el export de su GPS y la app calcula la carga. La plantilla mete su esfuerzo y su wellness desde el móvil. |
| 9–10 jun | Plantilla: ficha, ficha 360, lesiones y alineaciones | Cada jugadora o jugador tiene una ficha completa con carga, wellness, asistencia y partidos. La disponibilidad sale de la lesión activa. Hay un creador de onces de fútbol 11 con 10 sistemas, con arrastrar y soltar. |
| 10–11 jun | Panel de plataforma | Desde ahí se crean y gestionan los clubes y se da de alta al staff sin tocar la base de datos. |
| 12–13 jun | Módulo de vídeo completo | Se etiqueta el partido con atajos de teclado sobre el vídeo local. Después se genera el informe y se cortan los clips en un ZIP con una carpeta por tipo de evento. El vídeo se borra al terminar. |
| 13 jun | Historial de lesiones y marca «Revisar» | Muestra cada lesión activa, las altas y la duración de cada baja, y marca «Revisar» cuando una vuelta está a 7 días o menos o se ha retrasado. |
| 15–16 jun | Zonas de velocidad 1–5 y compatibilidad con iPhone | Aparecen la distancia y el tiempo por zona, y el importador lee los CSV en las codificaciones habituales (las de Excel y Catapult). La app pasa a funcionar en iPhone (Safari de iOS 15 en adelante). |
| 21 jun | Minutos efectivos y carga derivada | Si una sesión no tiene GPS, los minutos los mete el staff. La carga se recalcula siempre, así que no importa que el GPS llegue después que el RPE. |

### Julio y agosto: feedback y producción

| Fecha | Hito | Qué aporta |
|---|---|---|
| 30 jun – 2 jul | Rediseño del inicio, la analítica y la ficha 360 | Vistas de equipo e individual, periodos, comparativas, % frente a partido, mapa corporal de lesiones y semáforo de wellness. Sale de las primeras rondas de feedback de cuerpo técnico. |
| 27–31 jul | Plantilla y partidos con el lenguaje visual nuevo | Listados más claros. Los minutos jugados ya no pueden superar a los disponibles. |
| 10–11 ago | Primer despliegue en producción | La web y los dos servicios van en contenedores. La web pública y la app tienen cada una su dominio, y la app se puede instalar como PWA. |

### Septiembre: de herramienta a producto

| Fecha | Hito | Qué aporta |
|---|---|---|
| 22 sep | Web pública, textos legales y base de calidad | Llegan la landing, el aviso legal, la privacidad y las cookies, las cabeceras de seguridad, los tests en CI y las copias diarias de la base de datos. El ACWR pasa a ser descriptivo y el wellness de cada persona se compara con su propio historial. |
| 27 sep | Invitaciones, entrenamientos y asistencia | El staff invita por un enlace que se comparte por WhatsApp. Puede crear entrenos sin GPS, recibir el RPE de cada entreno y pasar lista por sesión. |
| 28 sep | Primeros pasos y exportación de datos | Hay una guía de primeros pasos, alta rápida de la plantilla y ayuda por rol. Con un clic, el club descarga sus datos en un ZIP de CSV. |
| 28 sep | Cuestionario de wellness por club | Cada club ajusta su cuestionario: oculta o renombra preguntas y añade las suyas. |
| 28 sep | Cuenta multi-club, partidos completos y club demo | Un preparador puede llevar varios clubes con una sola cuenta. Los partidos guardan rival, jornada, campo y resultado. Cada lesión puede quedar ligada a su sesión y cada once a su partido. Hay un club demo con datos ficticios. |
| 28 sep | Importador GPS de varios fabricantes | Lee los exports de Catapult y STATSports, y de cualquier otro sistema asignando columnas. Un fichero puede traer varias sesiones. |
| 28–29 sep | Sistema de diseño v2 y rediseño de toda la app | Un único lenguaje visual: tokens, componentes y una galería interna. Las cifras suben y los gráficos se dibujan al cargar, y se respeta la opción de reducir movimiento. |

### Finales de septiembre y octubre: pulido y marca

| Fecha | Hito | Qué aporta |
|---|---|---|
| 28 sep – 3 oct | Landing con arte 3D hecho en Blender | Una pizarra de partido renderizada en 3D. Una sola toma continua acompaña al scroll y cuenta la semana en cinco historias. |
| 5–6 oct | Auditoría completa y QA en producción | Auditoría de 9 áreas y QA en producción con la cuenta demo (72 pantallas y comprobaciones); se corrigió cada fallo confirmado. |
| 6 oct | Logo «Cero de medio campo» y kit de marca | El cero de KAIR0S es el círculo central del campo. Se hicieron los favicons, iconos de app e imagen para compartir. |
| 6 oct | Experiencia táctil en tablet y móvil | Botones, campos y pestañas a 44 px en pantallas táctiles, la hoja de sesión se ve como tabla en el iPad y la barra de iconos lleva nombres. Se corrigieron 149 hallazgos. |
| 6 oct | Informe del partido en PDF | Un PDF A4 vectorial que se descarga o se comparte desde el iPad o el móvil. |
| 7 oct | Plantilla femenina o masculina por club | Cada club elige cómo se nombra su plantilla y toda la app concuerda: jugadora o jugador, lesionada o lesionado… |
| 7 oct | Escenas de la landing en alta resolución y protección del acceso | Imagen más nítida en pantallas grandes, y protección del inicio de sesión, el registro y la recuperación de contraseña frente a intentos repetidos. |
| 8–9 oct | Recuperación de contraseña por correo y contacto único | Desde el inicio de sesión se puede pedir una contraseña nueva por correo. Hay un solo correo de contacto: info@kair0s.es. |

## Ritmo de trabajo

Commits por mes en la rama principal:

| Mes | Commits | Ritmo |
|---|---:|---|
| Junio 2026 | 48 | `▇▇` |
| Julio 2026 | 19 | `▇` |
| Agosto 2026 | 6 | `▏` |
| Septiembre 2026 | 253 | `▇▇▇▇▇▇▇▇▇▇` |
| Octubre 2026 (hasta el 9) | 214 | `▇▇▇▇▇▇▇▇▇` |
| **Total** | **540** | |

## Cifras

| Cifra | Valor | Fuente |
|---|---|---|
| Commits | 540 (jun 48 · jul 19 · ago 6 · sep 253 · oct 214) | Historial de Git de la rama principal |
| Periodo de desarrollo | 7 jun – 9 oct 2026, unos 4 meses | Primer y último commit |
| Tests de la web | Más de 4.200 | Ejecución de Vitest del 9 oct 2026, 254 ficheros |
| Tests de los servicios Python | 330 (305 de importación GPS y 25 de vídeo) | Recuento de pytest |
| Pruebas de extremo a extremo | 5 suites de Playwright; en la CI corren las que no necesitan cuenta, en Chromium, y la de iPhone, en WebKit | Playwright en GitHub Actions (rama principal y pull requests) |
| Pruebas de permisos y aislamiento entre clubes | Más de 680 comprobaciones en 12 scripts | Resultados registrados de las pruebas de la base de datos |
| Pantallas | 59 (47 de la app, 5 de la web pública y 7 de acceso) | Rutas de la web |
| Tamaño | Unas 143.000 líneas de TypeScript (41.000 de ellas de tests) y unas 22.000 de Python | Recuento sobre los ficheros versionados |
| Plataformas | Web responsive, PWA instalable y uso táctil en iPad, tablet y móvil; compatible con Safari de iOS 15 en adelante: la CI rechaza cualquier código que ese Safari no entienda | Configuración y CI |
| Idioma | Castellano, con plantilla femenina o masculina por club | — |

---

<sub>© 2026 Samu (FLK0S). Todos los derechos reservados. Este repositorio no contiene código fuente.</sub>
