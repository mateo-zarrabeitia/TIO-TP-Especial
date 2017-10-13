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
* Todos los componentes que construyas no deben tener anchos (width); deben ser fluidos y su anchura regida por su contenedor o por su grid.

* Nunca se deben aplicar alturas (height) a los elementos. La altura debe ser solo aplicada a los elementos con unas dimensiones dadas antes de introducirse en el layout (Ej: sprites o imágenes). Nunca establezcas altura a 'p', 'ul', 'div', o a cualquier otro elemento. normalmente puedes obtener el efecto deseado con 'line-height' que es de lejos mucho más flexible.

* Los sistemas de grids deben ser pensados como estanterías. Tienen contenido pero no son contenido en si. Tu montas las estanterías y luego las llenas con tus cosas. Configurar nuestras grids separadas de nuestros componentes nos permite mover componentes mucho más fácil que si tienen dimensiones configuradas; esto hace nuestro front-end mucho más adaptable y nos permite trabajarlo más rápido.

* Nunca deberías aplicar estilos a un elemento del sistema de grid, son para efectos de disposición únicamente. Aplica estilos al contenido dentro del elemento del grid. Nunca, bajo ninguna circunstancia, debemos aplicar propiedades al modelo de caja de un elemento del grid.

* NUNCA usar IDs en CSS.

	* Pueden ser usados en tu marcado para referencias de JS, pero usad sólo clases para estilos. No queréis ver una sola ID en ninguna hoja de estilos!

	* Las clases vienen con el beneficio de ser reusables (aún si no queremos, podemos) y tienen un buen y bajo especificado. El especificado es una de las formas más rápidas de afrontar dificultades en proyectos y mantenerlo bajo en todo momento, es imperativo. Una ID es 255 veces más específico que una clase, por ello nunca los uses en CSS.

* Mantén los selectores cortos, eficientes y portables.

* Selectores basados en su posición son malos por una variedad de razones. Por ejemplo, tomemos '.sidebar h3 span{}'. Este selector está basado en la posición y por ello no podemos mover ese 'span' fuera de un 'h3' fuera de un '.sidebar' y mantener el estilo.

* Los selectores que son muy largos también introducen problemas de optimización. Cuantas más verificaciones hay en un selector (Ej: '.sidebar h3 span' tiene tres verificaciones, '.content ul p a' tiene cuatro), más trabajo tiene el navegador.

* Siempre que sea posible nos aseguraremos que los estilos no dependan de la posición en el CSS, así como nos aseguraremos que los selectores son buenos y cortos.

* Los selectores en general deben mantenerse cortos (Ej: una clase de profundidad) pero los nombres de las clases en sí mismas deben ser tan largas como lo necesiten. Una clase de '.user-avatar' siempre es mejor que '.usr-avt'

* Recordad: Las clases no son semánticas o dejan de serlo; ellas son sensibles o insensibles! Dejad de peocuparos por la 'semántica' de los nombres de las clases y elige algo sensato y previsor.