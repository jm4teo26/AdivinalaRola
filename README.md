# Adivina la Rola 🎵

Juego web: escuchas **unos segundos de una canción real** y adivinas cuál es entre 4 opciones. Entre menos segundos necesites, más puntos ganas.

## ¿Qué API consume?
La **iTunes Search API** de Apple (gratuita, sin API key). Por cada artista del género elegido se hace una búsqueda y se obtiene: título, artista, álbum, año, portada y un **fragmento de audio de 30 s** (`previewUrl`).
Las peticiones se hacen con **JSONP** (parámetro `callback`), así funciona en cualquier hosting estático como GitHub Pages sin necesidad de servidor ni de configurar CORS.

## Cómo se juega
- Escoge un género: Reggaetón, Regional mexicano, Rock en español, Pop en inglés, Clásicos 80s y 90s, o Mezcla.
- Dale play: suena **1 segundo**. Puedes pedir más tiempo (3, 7 y 15 s), pero la canción vale menos puntos: 300 / 200 / 120 / 60.
- Pista: ver la portada del disco borrosa (−50 pts).
- Racha: +25 por cada acierto seguido.
- Al responder se revela la portada en el vinil y suena la canción.

## Reto del día
La fecha se usa como **semilla de un generador de números aleatorios**, así que todos los que jueguen el mismo día y el mismo género escuchan **las mismas 10 canciones** y pueden comparar puntajes, todo sin backend.

## Tecnología
HTML, CSS y JavaScript puro. Audio con el elemento `<audio>`. El récord de cada género se guarda en `localStorage`. El código QR se genera con [qrcode.js](https://github.com/davidshimjs/qrcodejs) a partir de la URL donde esté publicada la página.
Desplegado en GitHub Pages.
