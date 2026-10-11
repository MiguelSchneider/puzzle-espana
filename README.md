# España, pieza a pieza

Un puzle de arrastrar y soltar para aprender las provincias y las comunidades autónomas de España. Cada pieza tiene la forma real de su territorio: si la sueltas cerca de su sitio, encaja, se queda fija y muestra su nombre. Pensado para que una alumna de secundaria practique en un iPad, pero funciona en cualquier navegador moderno.

**Juega aquí:** https://miguelschneider.github.io/puzzle-espana/

## Por qué un puzle

La mayoría de los juegos de mapas te dicen un nombre y te piden que lo señales. Si no tienes ni idea de dónde está, no aprendes nada. Aquí la pieza te dice su nombre y su comunidad mientras la sujetas, así que la tarea es "averigua dónde va", con la forma, el color y la costa como ayuda. Los fallos no se penalizan: se corrigen.

## Modos de juego

- **Puzle**: las piezas salen desordenadas en la bandeja y hay que colocarlas en el mapa. Encajan solas cuando la posición es correcta; si está casi, la pieza tiembla y avisa ("Casi"); si está lejos, avisa de que va en otra parte ("Ahí no").
- **¿Dónde está?**: el mapa aparece completo y sin colorear; el juego pregunta por una provincia y hay que tocarla. Al acertar se pinta con el color de su comunidad. Si fallas, te dice qué has tocado; al segundo fallo revela la correcta y la vuelve a preguntar más adelante.

Ambos modos se juegan con las 52 provincias (50 más Ceuta y Melilla) o con las 19 comunidades autónomas.

## Funcionalidades

- Geometría oficial del Instituto Geográfico Nacional.
- Piezas coloreadas por comunidad autónoma: al montar el mapa de provincias se aprenden también las comunidades.
- Cuatro niveles de pista, de más difícil a más fácil, que se recorren con un botón:
  1. Solo la silueta de España
  2. Bordes de las comunidades
  3. Bordes de comunidades y provincias
  4. Comunidades coloreadas con el mismo color que sus piezas
- Ceuta y Melilla tienen un asa de agarre ampliada, mayor tolerancia de encaje y un anillo guía que se enciende al acercarse a su sitio.
- Cronómetro, contador de fallos y mejor tiempo por modo (guardado en el navegador; nada sale del dispositivo).
- Táctil, ratón y lápiz. En horizontal la bandeja va a ambos lados del mapa; en vertical, debajo.
- Tema claro y oscuro, botón de pantalla completa y etiquetas de web app de iOS para que funcione sin barra del navegador al añadirlo a la pantalla de inicio.

## Cómo ejecutarlo

Es un único archivo `index.html`, autocontenido. Sin compilación ni dependencias en tiempo de ejecución.

- **En local:** `python3 -m http.server 8000` en esta carpeta y abrir `http://localhost:8000/`.
- **iPad a pantalla completa:** abrir la URL en Safari → Compartir → *Añadir a pantalla de inicio*. Al lanzarlo desde el icono desaparecen la barra de direcciones y las pestañas. El Acceso Guiado (Ajustes → Accesibilidad) evita salidas accidentales.

La única petición externa es la tipografía (Google Fonts, Fredoka); sin conexión usa la del sistema.

## Nombres

La interfaz está en castellano y los topónimos usan la forma castellana (Alicante, Álava, Guipúzcoa, Vizcaya, La Coruña, Orense, Lérida, Gerona, Islas Baleares, Comunidad Valenciana), en lugar de las formas oficiales bilingües del conjunto de datos.

## Datos

La geometría procede de [es-atlas](https://github.com/martgnz/es-atlas) (TopoJSON del Instituto Geográfico Nacional, licencia MIT), proyectada una sola vez en tiempo de construcción con `geoConicConformalSpain` de [d3-composite-projections](https://github.com/rveciana/d3-composite-projections), que sitúa las Canarias en un recuadro junto a la península. Los trazados SVG resultantes van incrustados en el HTML, por lo que el navegador no carga ninguna librería de mapas. Gibraltar queda excluido.

## Licencia

Código: MIT. Geometría del mapa: © Instituto Geográfico Nacional, vía es-atlas (MIT).
