# Graphics Records – ficha del proyecto

Sitio de **Graphics Records**, estudio de diseño web («Private Digital Atelier»).
Publicado con **GitHub Pages** desde la rama `main` en https://graphicsrecords.github.io/.
Sitio estático: HTML con estilos en línea, sin build, sin dependencias.

## Cómo trabajar con el dueño
- **Siempre en español**, en lenguaje sencillo, sin jerga técnica.
- Flujo: cambios en una rama → commit → push → **pull request** → el dueño hace el merge desde el celular.
  Tras el merge, GitHub Pages publica en 1–2 minutos.
- Al terminar, dar los **links** (pull request y página publicada) y decir qué probar.
- Un **chat por proyecto o tema** (ej. «Músico – KAN Resonance»), para mantener el orden.
- Probar en Chromium con Playwright antes de subir: ancho de móvil (390 px), escritorio y árabe (RTL).
  No hacer envíos reales del formulario ni de WhatsApp: simularlos.

## Páginas
| Ruta | Para qué sirve |
|---|---|
| `index.html` (EN), `es`, `pt`, `de`, `fr`, `ar` (RTL), `zh`, `ja` `.html` | Web comercial en 8 idiomas: servicios, método, contacto. Misma estructura en todos los idiomas. |
| `thanks.html`, `thanks-es.html`, … (uno por idioma) | Página de agradecimiento tras enviar el formulario. `noindex`. Botón «Volver al inicio». |
| `umfrage/` | Encuesta privada en alemán para el cliente Josef (Full Moon, Suiza) sobre una imagen para Google Maps. Respuestas por WhatsApp. |
| `artista/` | Cuestionario privado en español para músicos (brief de su web). Respuestas por WhatsApp. Lo respondió **KAN Resonance** (Techno Jazz). |
| `banner.jpg` | Banner de la marca, también usado como imagen de vista previa (`og:image`). |

**Cualquier cambio en la web comercial se hace en los 8 idiomas** (y en sus 8 páginas de agradecimiento si aplica).

## Formulario de contacto (web comercial)
- Envía con **Web3Forms** (`https://api.web3forms.com/submit`) por `fetch`; llega por correo al dueño.
- Campos: nombre, correo, empresa, **project** (obligatorio), **budget** y **source** (opcionales), mensaje.
  Los textos visibles están traducidos; los *valores* enviados van **siempre en inglés** para que todos los correos sean iguales.
- Si el envío sale bien → redirige a la página `thanks-*.html` de su idioma.
  Campo oculto `redirect` como respaldo sin JavaScript (el script lo quita de su propia petición).
- Si falla → el formulario se queda y muestra «Algo salió mal…».

## Encuestas privadas para clientes (`umfrage/`, `artista/`)
- `noindex,nofollow`, pensadas para el celular; se responden tocando opciones.
- Barra fija abajo con progreso; el botón se activa al completar las obligatorias y abre
  `wa.me/<número>` con las respuestas ya escritas. El número está en la variable `WA_NUMBER` del script.
- Para un cliente nuevo: copiar `artista/index.html` a una carpeta nueva y cambiar preguntas, textos y `og:*`.

## Estilo de marca
- Fondo `#0B0A08`, texto `#EDE6D3`, texto secundario `#A39A82`, dorado `#C9A24B` / `#E6C77A` / `#F3DDA0`, líneas `rgba(201,162,75,0.28–0.5)`.
- Tipografías (Google Fonts): **Cormorant Garamond** (títulos), **Jost** (texto), **IBM Plex Mono** (etiquetas en mayúsculas con letter-spacing).
- Esquinas rectas, bordes finos dorados, monograma «GR» en círculo.
