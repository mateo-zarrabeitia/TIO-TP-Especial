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

## Comentarios ##

/**
 * Esto es un comentario estilo docBlock
 *
 * Esta es una descripción más larga del comentario, describiendo el código con más
 * detalle. Limitamos estas líneas a 80 caracteres de longitud
 *
 * Podemos tener etiquetado en el comentario, y de hecho es recomendable:
 *
   <div class=foo>
       <p>Lorem</p>
   </div>
 *
 * No ponemos un asterisco como prefijo en las líneas de código, ya que inhibiría
 * copiar y pegar.
 *
 * /

Deberías documentar y comentar tu código tanto como sea posible, lo que puede parecer transparente y que se explica por sí mismo podría no serlo para otro desarrollador. Escribe un trozo de código y luego escribe sobre él.
Números mágicos y absolutos.

## Números mágicos y absolutos ##
* Un número mágico es un número usado porque 'funciona'. Son malos porque raramente funcionan de verdad y no son muy seguros o flexibles/indulgentes. Tienden a solucionar síntomas y no problemas.

* Por ejemplo, usar '.dropdown-nav li:hover ul{ top:37px; }' para mover un desplegable abajo de la navegación en hover está mal, ya que 37px es un número mágico. 37px sólo funciona aquí porque en este escenario en particular el '.dropdown-nav' tiene 37px de alto.

* En vez de eso, deberías usar '.dropdown-nav li:hover ul{ top:100%; }' que quiere decir que no importa el alto de '.dropdown.nav', el desplegable siempre se colocará a 100% del borde superior.

* Piensa cada vez que escribes un número para que encaje en el layout; si puedes evitarlo usando 'aliases' (Ej: 'top:100%' para indicar 'todo a partir del borde superior') o —aún mejor— sin medida alguna.

* Escribir medidas para que encajen en el layout es un compromiso que no necesariamente querrás mantener.

## '!important' ##
* Está bien utilizar '!important' sólo en clases helper. Añadir '!important' preventivamente es correcto, Ej: '.error{ color:red!important;}', como ya sabrás siempre querrás que esta regla tenga prioridad.

* Usar '!important' sensiblemente, Ej: para salir de malas situaciones de especificación, no es recomendado. Rehaz tu CSS e intenta combatir estos problemas reconstruyendo tus selectores. Mantener tus selectores cortos y evitando IDs ayudará enormemente.

## Depuración ##
* Si te encuentras con un problema de CSS quita código antes de empezar a agregar más en un intento por solucionarlo. El problema existe en el CSS ya escrito, más CSS no es la solución adecuada.

* Borra trozos de CSS y marcado hasta que el problema desaparezca, así puedes determinar en que parte o línea reside el problema.

* Puede ser tentador poner un 'overflow:hidden;' en un elemento para ocultar los efectos de un error en el layout, pero overflow nunca fue probablemente el problema. Arregla el problema, no sus síntomas.

## Selectores universales vs IDs ##
* Por increíble que parezca, los selectores universales son los menos eficientes de todos, mientras que los IDs son los más eficientes. Aquí puedes ver el orden de más a menos rápidos:
  * 1
  ```
   #content  {
     /* ID (el más rápido) */
     }      
  ```        
  * 2
  ```
  * .index #slider {
    /* ID */
    }         
  ```  
  * 3
  ```
  * .footer {
     /* Clase */
  }               
  ```
  * 4
  ```
  * ul li a.nav {
    /* Clase */
  }            
  ```
  * 5
  ```
  * ul {
     /* Etiqueta
  }                    
  ```
  * 6
  ```
  * ul li a {
      /*Etiqueta */
  }              
  ```
  * 7
  ```
  * {
    /* Selector universal (el más lento) */
  }                     
  ```
  * 8
  ```
  * #content [title='index'] {
    /* Selector universal */
  }
  ```

  ## Pseudo-clases ##

Una pseudo-clase CSS consta de una clave precedida de dos puntos (:) que añadiremos al final del selector para indicar que daremos estilo a los elementos seleccionados solo cuando estos se encuentren en un estado determinado. Por ejemplo podríamos querer dar estilo a un elemento cuando este se muestre al pasarle el puntero del ratón, o una caja de selección al estar habilitada o deshabilitada o cuando un elemento es hijo directo de su padre en el árbol DOM.

## Ejemplo de pseudo-clase ##
* Veamos un ejemplo de cómo usarlas. Primero, un fragmento de HTML:

* <a href="https://developer.mozilla.org/" target="_blank">Mozilla Developer Network</a>
* Y las reglas CSS:

* /* Estos estilos cambian los link en todos sus estados */
* a {
*  color: blue;
*  font-weight: bold;
 }

* /* Si queremos los link visitados de los no visitados del mismo color */
*  a:visited {
*  color: blue;
* }

* /* Remarcamos el link cuando pasamos con el mouse sobre él.
   activado o el teclado activado*/
* a:hover,
* a:active,
* + a:focus {
*  color: darkred;
* +  text-decoration: none;
* }

## Longitud y tamaño ##
* Usamos unidades de longitud/tamaño (ver <length> como referencia) muy a menudo en diseños CSS, tipografía y otros. Veamos un ejemplo — primero el HTML:
  <p>Esto es un párrafo.</p>
  <p>Esto es un párrafo.</p>
  <p>Esto es un párrafo.</p>

 Y el CSS:

* p {
*   margin: 5px;
*   padding: 10px;
*   border: 2px solid black;
*   background-color: cyan;
* }
*
* p:nth-child(1) {
*   width: 150px;
*   font-size: 18px;
* }
*
* p:nth-child(2) {
*   width: 250px;
*   font-size: 24px;
* }
*
* p:nth-child(3) {
*   width: 350px;
*   font-size: 30px;
* }

Herencia

La herencia en CSS es la última pieza que necesitamos conocer para tener la información completa y comprender qué estilo se aplicará a un elemento. La idea es que unos elementos se heredarán por los elementos hijos, y otros no.

Por ejemplo, tiene sentido que font-family y color sean heredadas, pues nos facilita establecer un ancho de fuente básico aplicando una familia de fuentes al elemento <html>; después podemos reemplazar las fuentes de elementos individuales si es necesario. Sería realmente molesto tener que establecer la fuente base para cada elemento por separado.
Otro ejemplo: tiene sentido que margin, padding, border, y background-image NO se hereden. Imaginemos el lio de formato/estilo que ocurriría si aplicamos estas propiedades en un elemento y fuera heredado por todos y cada uno de sus hijos, y después tener que "desaplicarlas" a todos los elementos también.
Las propiedades que se heredan por defecto y las que no, viene marcado en gran medida por el sentido común. Pero para estar seguros podemos consultar la Referencia CSS — cada propiedad viene en una página que comienza con una tabla resumen que incluye diversos detalles sobre cada elemento, incluyendo si se hereda o no.
