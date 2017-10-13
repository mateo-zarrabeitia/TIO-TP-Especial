# Buenas prácticas y sintaxis de CSS #

## ¿Qué es CSS? ##

Según la WEB:

> CSS es un lenguaje de hojas de estilos creado para controlar el aspecto o presentación de los documentos electrónicos definidos con HTML y XHTML. CSS es la mejor forma de separar los contenidos y su presentación y es imprescindible para crear páginas web complejas.
Como en todo lenguaje hay una serie de buenas y malas prácticas a evitar, como por ejemplo:

### A evitar ###

1. CSS in-line.
2. Tamaños de fuente absolutos.
3. Marcar con comillas simples las rutas de las imágenes.
4. CSS hacks.
5. Redeclarar valores heredados.
6. Aplicar paddings/borders y un ancho fijo a un elemento.
7. !important y position: absolute.
8. Nombrar clases/IDs según su apariencia.


### Buenas Practicas ###

* Preferir **`<link>`** sobre **`@import`** para invocar hojas de estilo
* Comentar el código.
* Organizar el fichero CSS.
* Indentar tanto como sea necesario.
* Nombrar a las clases/IDs según su función, no su apariencia.
* Definir siempre un **`font-size`** al elemento root (**`html`**) y hacerlo en **`px`**
* Usar [**`box-sizing: border-box;`**](http://www.paulirish.com/2012/box-sizing-border-box-ftw/)
* Estandarizar los estilos iniciales de nuestras etiquetas HTML para todos los navegadores
    * [Reset.css](http://meyerweb.com/eric/tools/css/reset/)
    * [Normalize.css](https://necolas.github.io/normalize.css/)
    * o crear uno propio.
* Evitar el uso de selectores de etiquetas e identificadores y trabajar en su mayoria con clases
* Maquetar bajo un enfoque **Mobile First**
* Escribir CSS pensando en reutilizar código (**DRY**)
* Tener precaución con los shorthand de CSS
    * **`padding, margin, font, background, border, border-radius`**
    * preferible **`background-color: #FFF`** que **`background: #FFF`**
* Ordenar el código en cada selector usando la fórmula **PC-TV**:
    * Posicionamiento **`position, top, left, right, bottom, clear, z-index`**
    * Modelo de Caja **`display, float, margin, padding, width, height`**
    * Tipografía **`font-family, font-size, line-height, color, text-align`**
    * Visual **`background-color, border, border-radius, outline, opacity`**
