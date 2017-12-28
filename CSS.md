-------------------------------------------

CSS
===

-------------------------------------------

INDICE
------
1. [FUNDAMENTOS](#1fundamentos)
  1. [IMPORTAR CSS](#11importar-css)
2. [LOS SELECTORES](#2los-selectores)
3. [BOX MODEL](#3box-model)
4. [POSITION](#4position)
5. [FLEXBOX](#5flexbox)
6. [GRID, TABLAS Y COLOR](#6grid,-tablas-y-color)
7. [ANIMACIONES, TRANSFORM y 3D](#7animaciones,-transform-y-3d)

1.FUNDAMENTOS
=============

1.1.Importar CSS
----------------

* Incluir CSS en los elementos HTML
* Incluir CSS en el mismo documento HTML
* Definir CSS en un archivo externo

**Incluir CSS en los elementos HTML**

```html
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml">
  <head>
  <meta http-equiv="Content-Type" content="text/html; charset=iso-8859-1" />
    <title>Ejemplo de estilos CSS en el propio documento</title>
  </head>

  <body>
    <p style="color: black; font-family: Verdana;">Un párrafo de texto.</p>
  </body>
</html>
```
**Incluir CSS en el mismo documento HTML**
```html
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
  <meta http-equiv="Content-Type" content="text/html; charset=iso-8859-1" />
  <title>Ejemplo de estilos CSS en el propio documento</title>
  <style type="text/css">
    p { color: black; font-family: Verdana; }
  </style>
</head>
  <body>
    <p>Un párrafo de texto.</p>
  </body>
</html>
```

**Definir CSS en un archivo externo**

Normalmente, la etiqueta <link> incluye cuatro atributos cuando enlaza un archivo CSS:

* `rel:` indica el tipo de relación que existe entre el recurso enlazado (en este caso, el archivo CSS) y la página HTML. Para los archivos CSS, siempre se utiliza el valor `stylesheet`
* `type:` indica el tipo de recurso enlazado. Sus valores están estandarizados y para los archivos CSS su valor siempre es `text/css`
* `href:` indica la URL del archivo CSS que contiene los estilos. La URL indicada puede ser relativa o absoluta y puede apuntar a un recurso interno o externo al sitio web.
* `media:` indica el medio en el que se van a aplicar los estilos del archivo CSS. Más adelante se explican en detalle los medios CSS y su funcionamiento.

```html
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml">
  <head>
    <meta http-equiv="Content-Type" content="text/html; charset=iso-8859-1" />
    <title>Ejemplo de estilos CSS en un archivo externo</title>
    <link rel="stylesheet" type="text/css" href="/css/estilos.css" media="screen" />
  </head>
  <body>
    <p>Un párrafo de texto.</p>
  </body>
</html>
  ```
Aunque generalmente se emplea la etiqueta `<link>` para enlazar los archivos CSS externos, también se puede utilizar la etiqueta `<style>`. La forma alternativa de incluir un archivo CSS externo se muestra a continuación:

  ```html
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml">
  <head>
    <meta http-equiv="Content-Type" content="text/html; charset=iso-8859-1" />
    <title>Ejemplo de estilos CSS en un archivo externo</title>
    <style type="text/css" media="screen">
      @import '/css/estilos.css';
    </style>
  </head>
  <body>
    <p>Un párrafo de texto.</p>
  </body>
</html>
```

----------------------------------------------------------------

**Nota<sup>1</sup>** Se recomienda usar la definición CSS en un archivo externo, dividiéndolo en dos partes una inicial con estilos genéricos y de la parte inicial de la página y otra posterior que se referenciará en a partir de un punto de la web cargada.

```html
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml">
  <head>
    <meta http-equiv="Content-Type" content="text/html; charset=iso-8859-1" />
    <title>Ejemplo de estilos CSS en un archivo externo</title>
    <link rel="stylesheet" href="/css/style-basic.css"/>
  </head>
  <body>
    <p>Un párrafo de texto.</p>
    <link rel="stylesheet" href="/css/style-complet.css"/>
    <span>Un párrafo de texto.</span>
  </body>
</html>
  ```

----------------------------------------------------------------


En CSS, es posible crear múltiples reglas CSS para definir un mismo concepto. En este caso, la que prevalece ante todas las demás depende de ciertos factores, como es la `«altura»` a la que está colocada la regla:
* El **CSS embebido en un elemento HTML** es el que tiene mayor precedencia, por lo que siempre será el que tenga prioridad sobre otras reglas CSS.
* En segundo lugar, el **CSS interno definido a través de bloques `style`** en el propio documento HTML será el siguiente a tener en cuenta en orden de prioridad.
* Por último, los documentos **CSS externos** son la tercera opción de prioridad a la hora de tomar en cuenta las reglas CSS.

Teniendo esto en cuenta, hay que recordar que las propiedades que prevalecerán serán las que estén en último lugar, siempre respetando la prioridad de la lista anterior.

1.3.Concepto de herencia
------------------------

En primer lugar, debemos saber que algunas propiedades CSS se heredan desde los elementos padres a los elementos hijos, modificando el valor que tienen por defecto:
```css
body {
  color:green;    /* Color de texto verde */
}
```
En el ejemplo anterior, aplicamos a la etiqueta HTML `<body>` el color de texto verde. En principio, esta propiedad aplicará dicho color a los textos que estén dentro de dicha etiqueta `<body>`, sin embargo, si tenemos más etiquetas dentro, como por ejemplo, una etiqueta `<div>` con texto en su interior, veremos que también aparece en color verde. Esto ocurre porque la propiedad color es una de las propiedades **CSS** que hereda el valor de su elemento padre.

Esto no tendría sentido si lo hacemos con otras propiedades **CSS**, como los bordes de un elemento HTML:
```css
body {
  border-width: 2px;
  border-style: solid;
  border-color: red;
}
```
Si esta propiedad aplicara herencia, todos los elementos HTML situados en el interior de `<body>` tendrían un borde rojo, comportamiento que no suele ser el deseado. Por esa razón, la herencia no ocurre con todas las propiedades CSS, sino sólo con algunas propiedades como color o font, donde si suele ser deseable.

Sin embargo, podemos aplicar ciertos valores especiales comunes a la gran mayoría de propiedades, para cambiar el valor de la propiedad respecto a la herencia:

| **Valor	Significado**                                                 |
|:----------------------------------------------------------------------|
| `inherit`	| Hereda el valor de la propiedad del elemento padre.       |
| `initial`	| Establece el valor que tenía la propiedad inicialmente.   |
| `unset`	  | Combinación de las dos anteriores. Hereda el valor de la propiedad del elemento padre, y en caso de no existir, de su valor inicial.   |
Veamos, por ejemplo, el siguiente ejemplo para forzar la herencia:

```css
body {
  border-width: 2px;
  border-style: solid;
  border-color: red;
}

div {
  border:inherit;
}
```

Si tenemos un elemento `<div>` dentro del `<body>`, el primero heredará los estilos del elemento `<body>`, ya que le hemos especificado el valor `inherit` en la propiedad border.


1.4.Cascada
-----------

Además de la [herencia](#13concepto-de-herencia), otro de los conceptos más importantes de **CSS** es el concepto de cascada. Este concepto es un poco más avanzado, por lo que se debe conocer bien el tema de selectores CSS y dominar algo de **CSS** para comprenderlo en su totalidad, por lo que si no es el caso se puede posponer para una lectura posterior.

Antes de continuar, supongamos que nos encontramos ante el siguiente escenario:
```css
div {
    color:red;
    padding:8px
}
div {
    color:blue;
    background-color:grey
}
```
En este caso, ¿cuál de las dos reglas prevalece, si tenemos en cuenta que se refieren al mismo elemento y están al mismo nivel? La respuesta es muy fácil: Prevalece siempre la última regla definida, la cuál mezcla y sobreescribe las propiedades anteriores.

En el caso anterior, el resultado final sería el siguiente:
```css
div {
    color:blue;     /* Se sobreescribe la última */
    padding:8px;
    background-color:grey
}
```
Sin embargo, puede ocurrir que en determinados casos no esté tan claro cuál es el estilo que debería sobreescribir a los anteriores. Ahí es cuando entra en juego el concepto de cascada en **CSS**, que es el que se encarga de eliminar la ambigüedad y determinar el que tiene prioridad. Supongamos el siguiente caso:
```css
div {
    color:red;
}

#nombre {
    color:blue;
}

.clase {
    color:green;
}
```
Tenemos un elemento HTML `<div id="nombre" class="clase">` que encaja con los tres bloques del ejemplo anterior. ¿Cómo sabe CSS que estilo aplicar? ¿Cuál tiene prioridad sobre los demás? Aquí es donde entra en acción el concepto de cascada en **CSS**.

Para saber que bloque de estilos tiene prioridad, **CSS** analiza (por orden) tres conceptos clave del código CSS: su importancia, la especificidad y su orden. Veamos en que se basa cada uno de ellos.

**Importancia**

La importancia de un código CSS se determina dependiendo de las hojas de estilo donde está colocado. Generalmente, no necesitaremos preocuparnos de este factor, pero siempre es una buena idea conocer como funciona. Existen varios tipos de hojas de estilo, de menor a mayor importancia:

Tipo de hojas de estilo	Descripción
Agente de usuario	Son los estilos CSS que aplica el navegador por defecto.
CSS de usuario	Son los estilos CSS que añade el usuario, por razones específicas.
CSS de autor	Son los estilos CSS que coloca el autor de la página.
Aunque no es recomendable utilizarlo frecuentemente (puede convertirse en una mala costumbre), se puede añadir al final de cada regla el texto !important, consiguiendo que la regla en cuestión tenga prioridad sobre las demás, independientemente del nivel o la altura a la que estén:
```css
div {
    color:red!important;
    padding:8px
}
div {
    color:blue;
    background-color:grey
}
```
El resultado final de este código CSS sería:
```css
div {
    color:red;
    padding:8px;
    background-color:grey
}
```
| Otro ejemplo |
|--------------|

Gracias a la Herencia podemos optimizar la cantidad de código que utilizamos ya que de no hacerlo habría que repetir código continuamente.
```css
h1{
  background: black;
  font-size: 50px;
  font-family:sans-serif;
  text-decoration: underline;
  color: white;
}
/*
 * Sin la Herencia habría que
 * repetir el resto de propiedades
 */
h1:nth-child(2){
  color: yellow;
}
```
**Nota<sup>2</sup>**: En el caso de que una misma propiedad del CSS de usuario y una propiedad del CSS de autor tuvieran !important, como caso excepcional tendría prioridad la del CSS de usuario sobre la del CSS de autor.
Especificidad

En segundo caso, y si la importancia no elimina la ambigüedad, se pasa a determinar la especificidad de los selectores CSS. Para ello, se sigue un cálculo matemático basado en 4 componentes: A,B,C,D.

| Componente	  | Descripción                                             |
|:--------------|:--------------------------------------------------------|
| Componente A	| Número de estilos aplicados mediante un atributo style. |
| Componente B	| Número de veces que aparece un id en el selector.       |
| Componente C	| Número de veces que aparece una clase, pseudoclase o atributo en el selector. |

**Componente D**	Número de veces que aparece un elemento o un pseudoelementos en el selector.
Para saber si un bloque de CSS es más específico que otro (y por lo tanto, tiene prioridad) sólo hay que calcular sus componentes. Veamos algunos ejemplos con selectores CSS reales:

```css
div { ... }                     /* Especificidad: 0,0,0,1 */
div div { ... }                 /* Especificidad: 0,0,0,2 */
#pagina div { ... }             /* Especificidad: 0,1,0,1 */
#pagina div:hover { ... }       /* Especificidad: 0,1,1,1 */
#pagina div:hover a { ... }     /* Especificidad: 0,1,1,2 */
#pagina .sel:hover > a { ...}   /* Especificidad: 0,1,2,1 */
```
En [keegan.st](https://specificity.keegan.st/) tienes una excelente [calculadora de especificidad CSS](https://specificity.keegan.st/) donde podrás calcular la especificidad de un selector CSS rápida y cómodamente.

1.5.Sintaxis
------------

**Nota<sup>3</sup>:** Se recomienda usar [CSS Vocabulary](http://apps.workflower.fi/vocabs/css/es) para aprender el vocabulario usado con el CSS.
(Fuente resumen selectores: [Code.tutsplus.com](https://code.tutsplus.com/es/tutorials/the-30-css-selectors-you-must-memorize--net-16048))

1.5.1.Selectores Básicos
------------------------

* `*` **Selector Universal**. El asterisco se centrará en cada uno de los elementos en la página. Muchos desarrolladores usarán éste truco para poner a cero el `margin` y `padding`.

```css
* {
 margin: 0;
 padding: 0;
}
```
* `#X` **Selector id**. Prefijar el símbolo numérico a un selector nos permite seleccionar por `id`. T. Éste es fácilmente el uso más común, sin embargo te cuidado cuando uses selectores `id`.

```css
#container {
 width: 960px;
 margin: auto;
}
```
* `.X` **Selector de Clase**. Éste es un selector de clase `class` La diferencia entre `id` y `class` es que, con el último, puedes seleccionar varios elementos. Usa classes cuando quieras que un estilo aplique a un grupo de elementos. De manera alternativa, usa ids para encontrar una aguja en un pajar y estilizar sólo ése elemento en específico.

```css
.error {
color: red;
}
```
* `x` **Selector de Tipo**. ¿Qué pasa si quieres seleccionar todos los elementos en una página, de acuerdo a su tipo ( type), en vez de un nombre de id o clase. Mantenlo simple, y usa un selector de tipo. Si necesitas seleccionar todas las unordered lists, usa `ul {}``.

```css
a { color: red; }
ul { margin-left: 0; }
```
* `X Y` **Selector Descendiente**. El siguiente selector más común es el selector descendiente. Cuando necesites ser más específico con tus selectores, usas éstos. Por ejemplo, ¿que tal sí, en lugar de seleccionar todas las etiquetas anchor, sólo necesitas los anchors que están dentro de una unordered list?. Aquí es cuando usarías específicamente un selector descendiente.

```css
li a {
  text-decoration: none;
}
```
* `X + Y` **Selector Adyacente**. Este se conoce como un selector adyacente. Seleccionará solamente el elemento que es inmediatamente precedido por el primer elemento. En éste caso, solo el primer párrafo después de cada `ul` tendrá texto rojo.

```css
ul + p {
 color: red;
}
```
* `X > Y` **Selector Hijos Directos**. La diferencia entre el estándar `X Y` y `X > Y` es que el último sólo seleccionará hijos directos. Por ejemplo, considera el siguiente código.

```css
div#container > ul {
border: 1px solid black;
}
```
Un selector de ``#container >`` `ul` solo afectará los `ul`s que sean hijos directos del `div` con `id` de container. No afectará, por ejemplo, el `ul` que sea hijo del primer `li`.<br>Por ésta razón, hay beneficios de desempeño por usar el elemento de hijo. De hecho, es recomendable particularmente cuando se trabaja con motores de selectores CSS basados en JavaScript.

```html
<div id="container">
   <ul>
      <li> List Item
        <ul>
           <li> Child </li>
        </ul>
      </li>
      <li> List Item </li>
      <li> List Item </li>
      <li> List Item </li>
   </ul>
</div>
```
* `X ~ Y` **Selector Hermano**. Este elemento “hermano” es similar a `X + Y`, sin embargo, es menos estricto. Mientras que un selector adyacente (`ul + p`) sólo selecciona el primer elemento que es inmediatamente precedido por el primer selector, éste es más generalizado. Seleccionará, refiriéndonos al ejemplo de arriba, cualquier elemento `p`, siempre y cuando estén después de un `ul`.

```css
ul ~ p {
 color: red;
}
```

1.5.2.Selectores Complejos
--------------------------

* `X:visited and X:link` **Pseudo Clase**. Usamos la pseudo clase `:link` para seleccionar todas las etiquetas anchor a las que aún no se les ha dado click.<br>
De manera alternativa, también tenemos la pseudo-clase `:visited`, la cual, tal como esperabas, nos permite aplicar un estilo específico sólo a las etiquetas anchor en la página a las que se les ha dado click, o han sido visitadas.

```css
a:link { color: red; }
a:visted { color: purple; }
```
* `X[title]` **Selector de Atributos**. Denominado como un selector de atributos, en nuestro ejemplo de arriba, esto sólo seleccionará las etiquetas anchor que tengan un atributo `title`. Las etiquetas anchor que no lo tengan no recibirán éste estilo en particular. Pero,¿ y qué si necesitas ser más específico?

```css
a[title] {
 color: green;
}
```
* `X[href="foo"]` ****. El fragmento de abajo dará estilo a todas las etiquetas `anchor` que enlacen a [http://net.tutsplus.com](http://net.tutsplus.com); estas recibirán nuestro característico color verde. Las demás etiquetas anchor permanecerán sin cambio.<br>Ten en cuenta que estamos encerrando el valor entre comillas. Recuerda hacer esto también cuando uses un motor de selectores CSS JavaScript. Cuando sea posible, siempre usa selectores CSS3 en vez de métodos no oficiales.<br>Esto funciona bien, aunque, es un poco rígido. ¿Que tal si el enlace dirige ciertamente a Nettuts+, pero, tal vez, la dirección es nettuts.com en lugar de la url completa? En esos casos, podemos usar un poco de sintaxis de expresiones regulares.

```css
a[href="http://net.tutsplus.com"] {
  color: #1f6053; /* nettuts green */
}
```

* `X[href*="nettuts"]` ****.
* `X[href^="http"]` ****.
* `X[href$=".jpg"]` ****.
* `X[data-*="foo"]` ****.
* `X[foo~="bar"]` ****.
* `X:checked` ****.
* `X:after` ****.
* `X:hover`
* `X:not(selector)`
* `X::pseudoElement`
* `X:nth-child(n)`
* `X:nth-last-child(n)`
* `X:nth-of-type(n)`
* `X:nth-last-of-type(n)`
* `X:first-child`
* `X:last-child`
* `X:only-child`
* `X:only-of-type` **Pseudo Clase last-child**. Al contrario de `first-child`, `last-child` afectará el último elemento del padre el elemento.
* `X:first-of-type` **Pseudo Clase only-child**.
