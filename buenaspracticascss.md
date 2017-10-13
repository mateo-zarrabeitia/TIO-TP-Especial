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

### Buen estilo ###

9. Declaraciones CSS una por línea.
10. Comentar el código.
11. Organizar el fichero CSS.
12. Indentar tanto como sea necesario.
13. Hacer el código fácil de leer.
14. Usar un sistema común de nombrado.
15. Declaraciones cortas alfabéticamente.
16. Un “;” no es necesario en la última declaración.
17. Si declaras una unidad de 0 px/em/%/… puedes omitir la unidad.
18. Mantener contenedores, propiedades, selectores y CSS Hacks al mínimo.
19. Selectores de grupo te permiten seleccionar varios elementos de una vez.
20. Acortar la notación de colores en hexadecimal.
21. Definir las pseudoclases para enlaces en el orden LoVe/HAte.
22. Definir los márgenes, paddings y bordes de los elementos en el orden TRouBLed.
23. Puedes utilizar selectores hijos.
24. Hacer uso de diferentes tipos de medios.
25. Nombrar a las clases/IDs según su función, no su apariencia.
26. Aprender a explotar la cascada natural de CSS. CSS tiene sofisticadas reglas para la herencia de reglas.
27. Puedes usar selectores de atributos. Los selectores de atributos hacen juego con elementos basados en la presencia o valor de atributos.
28. Cambiar la capitalización con CSS.
29. Ordenar todos los elementos pertenecientes a la cabecera, contenido principal, pie de página… juntos para tener una mejor visión general.
30. Echa un vistazo a las guías de estilo de las grandes compañías.
31. Busca inspiración en los gurús del diseño.
32. Echa un vistazo a BluePrint, un framework de CSS, un montón de grandes ideas se encuentran integradas y documentadas.

### Buenas Practicas ###

* Preferir **`<link>`** sobre **`@import`** para invocar hojas de estilo
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
