# 30 años

Página web de regalo para celebrar 30 años de matrimonio (5 de octubre de 1996 al 5 de octubre de 2026). Se recorre año por año, con fotos, un video de mensaje y un rosetón final con una vela y una oración.

Es una sola página en HTML, CSS y JavaScript puros. No necesita instalar nada ni compilar nada.

## Qué contiene el repositorio

Todo va en la raíz, sin subcarpetas:

| Archivo | Para qué sirve |
|---|---|
| `index.html` | La página completa. Las fotos van incrustadas dentro. |
| `mensaje-hijo.mp4` | El video de Juan Sebastián. Hay que agregarlo. |
| `README.md` | Este archivo. |
| `musica.mp3` | Opcional. Solo si se activa la música (ver más abajo). |

## Publicar la página

### 1. En GitHub

1. Crea un repositorio nuevo y márcalo como **privado** (ver la sección de privacidad).
2. Entra al repositorio, pulsa **Add file** y luego **Upload files**.
3. Arrastra `index.html`, `mensaje-hijo.mp4` y `README.md`.
4. Pulsa **Commit changes**.

Subir archivos desde el navegador tiene un límite de 25 MiB por archivo. Si el video pesa más, comprímelo (720p alcanza) o súbelo con GitHub Desktop o la línea de comandos, que admiten hasta 100 MiB por archivo.

### 2. En Vercel

1. Entra a Vercel y elige **Add New** y luego **Project**.
2. Importa el repositorio de GitHub. Si no aparece porque es privado, dale acceso a Vercel desde la configuración de la aplicación de GitHub.
3. Si Vercel pide configuración, deja todo vacío: sin comando de compilación, sin directorio de salida. Si pide un tipo de proyecto, elige **Other**.
4. Pulsa **Deploy**.
5. Vercel te da una dirección terminada en `.vercel.app`. Esa es la dirección de la página.

Desde ese momento, cada cambio que guardes en GitHub se publica solo.

## Privacidad

- **Repositorio privado.** Las fotos están dentro de `index.html`. Si el repositorio es público, cualquiera puede verlas.
- **La dirección no tiene contraseña.** Quien la tenga puede abrir la página. La página incluye una etiqueta para que los buscadores no la indexen, pero eso no es seguridad.
- Comparte el enlace solo con quien quieras, y elige un nombre de proyecto poco obvio.

## Cómo editar la página

Abre `index.html` en GitHub con el ícono del lápiz. Busca el bloque que empieza con `CONFIGURACIÓN`, dentro de la etiqueta `<script>`. Ahí está todo lo editable.

| Qué | Dónde |
|---|---|
| Nombre de ella en la portada | `CONFIG.para` (queda vacío por defecto) |
| Recuadros "Aquí irá..." | `CONFIG.mostrarPendientes` (debe estar en `false`) |
| Música de fondo | `CONFIG.musica`, por ejemplo `'musica.mp3'` |
| Duración de cada pantalla en el modo presentación | `CONFIG.segundosPorPantalla` |
| Versículo y su cita | `ROSETON.versiculo` y `ROSETON.referencia` |
| Frase del rosetón | `ROSETON.lineas` |
| Oración de la vela | `ROSETON.oracion` |
| Textos de cada capítulo | `CAPITULOS` |
| Videos de mensaje | `MENSAJES` (nombre, texto y archivo) |
| Fotos y pies de foto | `FOTOS` (son imágenes incrustadas; para cambiarlas, pide una versión nueva) |

Al guardar el cambio con **Commit changes**, Vercel publica la versión nueva.

## El video

- El archivo debe llamarse exactamente `mensaje-hijo.mp4`, en minúsculas y sin espacios, y estar en la raíz del repositorio, junto a `index.html`.
- Formato recomendado: MP4 con video H.264 y audio AAC. Los videos de iPhone en formato `.mov` o HEVC pueden no abrir en todos los navegadores. Conviértelos antes de subirlos.
- El video no empieza solo. Se reproduce cuando ella lo toca.
- Si el archivo no está, al tocar la tarjeta aparece el aviso "Este video todavía no está cargado en la página".
- Para agregar más videos, súbelos a la raíz y suma una entrada en `MENSAJES`.

## Cómo está armada la página

El orden de las pantallas es: portada, boda de 1996, año 1, año 5, año 10, año 15, año 20, año 25, las rosas del 30, año 30, mensajes, rosetón y cierre.

- **Navegación:** línea de tiempo a un lado (o abajo en el celular), deslizar, flechas del teclado y botones.
- **Modo presentación:** botón arriba a la izquierda. Pasa de pantalla solo, para verla juntos en una pantalla grande. Se detiene si hay un video sonando o si el rosetón espera que toquen la vela.
- **Rosetón:** se enciende al tocarlo, pasa por la foto de ustedes, la Virgen y el versículo, y termina con la vela y la oración. Tiene un botón para saltar.
- **Tipografías:** Fraunces y Hanken Grotesk, que se cargan desde Google Fonts. Sin internet se ve con tipografías de reemplazo.
- **Peso:** el `index.html` pesa unos 2,8 MB.

## Lista de revisión antes de entregarla

- [ ] Abrir la dirección de Vercel en el celular, con datos móviles y no solo con wifi.
- [ ] Reproducir el video de Juan Sebastián.
- [ ] Recorrer el rosetón completo, hasta encender la vela.
- [ ] Probar el modo presentación en la pantalla donde se va a ver.
- [ ] Cambiar el versículo por el texto de la Biblia católica.
- [ ] Poner el nombre de ella en `CONFIG.para`, si se quiere.
- [ ] Confirmar que `CONFIG.mostrarPendientes` está en `false`.
- [ ] Confirmar que el repositorio es privado.

## Si algo falla

| Problema | Qué revisar |
|---|---|
| Vercel muestra un error 404 | Que `index.html` esté en la raíz del repositorio y no dentro de una carpeta. |
| El video no se reproduce | El nombre exacto del archivo, que esté en la raíz, que sea MP4 con H.264 y AAC, y que haya subido completo. |
| Cambié algo y no se ve | Que el cambio esté guardado en GitHub, que Vercel haya terminado de publicar y recargar la página sin usar la memoria del navegador. |
| Las letras se ven distintas | Es normal sin internet, porque las tipografías vienen de Google Fonts. |
| El rosetón se traba en un teléfono viejo | Los haces de luz giratorios son lo más pesado. Pide una versión con efectos más simples. |
