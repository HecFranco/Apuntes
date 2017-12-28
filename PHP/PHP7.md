-------------------------------------------

PHP 7
=====

-------------------------------------------

INDICE
------
1. [ESTRUCTURA Y CARACTERÍSTICAS](#1estructura-y-caracterÍsticas)
	1. [PHP y HTML](#11php-y-html)
		* [Diferencias entre echo, print, print_r() y var_dump()](#111diferencias-entre-echo-print-print_r-y-var_dump)
	2. [Los Caractéres de Escape](#12los-caractéres-de-escape)
	3. [Comentarios en PHP](#13comentarios-en-php)
2. [VARIABLES](#2variables)
	1. [Concepto de Variables](#21concepto-de-variables)
	2. [Variables Dinámicas](#22variables-dinámicas)
3. [TIPOS DE DATOS](#3tipos-de-datos)
	1. [Introducción a los tipos de datos](#31introducci%C3%B3n-a-los-tipos-de-datos)
	2. [gettype()](#32gettype)
	3. [Boleanos](#33boleanos)
	4. [Entero](#34entero)
	5. [Coma Flotante](#35coma-flotante)
	6. [Cadena](#36cadena)
	7. [Matrices](#37matrices)
	8. [Constantes](#38constantes)
4. [HACIENDO CÁLCULOS EN PHP: EXPRESIONES ARITMÉTICAS Y OPERADORES](#4haciendo-c%C3%81lculos-en-php-expresiones-aritm%C3%89ticas-y-operadores)
	1. [Introducción a los operadores](#41introducci%C3%B3n-a-los-operadores)
	2. [Operadores de asignación](#42operadores-de-asignaci%C3%B3n)
	3. [Operadores para concatenar cadenas](#43operadores-para-concatenar-cadenas)
	4. [Operadores aritméticos](#44operadores-aritm%C3%A9ticos)
	5. [Incremento y decremento](#45incremento-y-decremento)
	6. [Operadores de Comparación](#46incremento-y-decremento)
	7. [Operadores Lógicos](#47operadores-l%C3%B3gicos)
5. [ESTRUCTURAS DE CONTROL](#5estructuras-de-control)
	1. [Instrucción condicional If](#51instrucci%C3%B3n-condicional-if)
		* [Operadores de igualdad (==) y Asignación (=)](#511operadores-de-igualdad--y-asignaci%C3%B3n-)
	2. [Else y Elseif](#52else-y-elseif)
	3. [Switch](#53switch)
	4. [Operador Ternario](#54operador-ternario)
	5. [For](#55for)
	6. [While y Do While](#56while-y-do-while)
		* [El Bucle While](#el-bucle-while)
		* [Do...While](#do--while)
	7. [Break y Continue](#57break-y-continue-salir-de-un-bucle)
6. [ARRAYS](#6arrays)
	1. [Array Escalar](#61array-escalar)
	2. [Array Asociativo](#62array-asociativo)
	3. [Array Bidimensional y Multidimensonal](#63bidimensional-y-multidimensional)
	4. [Buble Foreach](#64bucle-foreach)
7. [FUNCIONES](#7funciones)
	1. [Funciones que trabajan con Variables](#71funciones-que-trabajan-con-variables)
	2. [Funciones que trabajan con Cadenas](#72funciones-que-trabajan-con-cadenas)
	3. [Funciones que trabajan con Arrays](#73funciones-que-trabajan-con-arrays)
	4. [Funciones que trabajan con Fechas](#74funciones-que-trabajan-con-fechas)
8. [FUNCIONES PROPIAS](#8funciones-definidas-por-el-usuario)<br>
	1. [Crear funciones propias](#81como-crear-funciones-propias)<br>
	2. [Funciones definidas en un archivo externo](#82funciones-definidas-en-un-archivo-externo)<br>
	3. [Parámetros](#83parámetros)<br>
		* [Parámetros por Valor](#831parámetros-por-valor)
		* [Parámetros por Referencia](#832parámetros-por-referencia)
		* [Parámetros porDefecto](#833parámetros-por-defecto)
		* [Número Variable de Parámetros](#834número-variable-de-parámetros)
9. [PROGRAMACIÓN ORIENTADA A OBJETOS](#9programaciÓn-orientada-a-objetos)
	1. [Clases](#91clases)
	2. [Instancias](#92instancias)
	3. [Valores por Defecto](#93valores-por-defecto)
	4. [Herencia de Clases](#94herencia-de-clases)
	5. [Clase Abstracta](#95clase-abstracta)
	6. [Clase Final](#96clase-final)
	7. [Modificadores de acceso y visibilidad](#97modificadores-de-acceso-y-visibilidad)
	8. [Acceso a los Objetos](#98acceso-a-los-objetos)
	9. [Métodos Mágicos](#99métodos-mágicos)
		* [Constructores](#991constructores)
		* [Destructor](#992destructor)
	10. [Interfaces](#910interfaces)
10. [MÉTODO GET Y POST](#10mÉtodo-get-y-post)
	1. [Método GET](#101método-get)
	2. [Método POST](#102método-post)
	3. [Gestionar Archivos](#103gestionar-archivos)
		* [Subir Ficheros](#1031subir-ficheros)
		* [Acceso a archivos](#1032acceso-a-archivos)
11. [COOKIES & SESIONES](#11cookies--sesiones)
	1. [Cookies](#111cookies)
		* [11.1.1.Creacion y lectura de cookies](#1111creacion-y-lectura-de-cookies)
		* [Escritura y Borrado de Cookies](#1112escritura-y-borrado-de-cookies)
		* [Ejemplos Prácticos](#1113ejemplos-prácticos)
	2. [Cookies](#112sesiones)
12. [BASE DE DATOS - MySQLi](#12base-de-datos---mysqli)
	1. [Sobre MySQLi](#121sobre-mysqli)
	2. [Conexión con la Base de Datos](#122conexión-con-la-base-de-datos)
	3. [Insertar Registros en una Base de Datos desde la Web](#123insertar-registros-en-una-base-de-datos-desde-la-web)
	4. [Consultas a la Base de Datos](#124consultas-a-la-base-de-datos)
	5. [Actualizar Tablas](#125actualizar-tablas)
	6. [Eliminar Registros de las Tablas](#126eliminar-registros-de-las-tablas)
	7. [Trabajando con varias Tablas](#127trabajando-con-varias-tablas)

----------------------------------

1.ESTRUCTURA Y CARACTERÍSTICAS
==============================

1.1.PHP y HTML
--------------

PHP es un lenguaje cuya función básica es la de **producir HTML**, que no deja de ser el lenguaje en el que realiza las páginas web. Sin embargo, como PHP es un lenguaje de programación, gracias a él tenemos la capacidad de analizar las diferentes situaciones (entrada del usuario, datos contenidos en una base de datos) y decidir producir código HTML condicional sobre los resultados del procesado.
El código PHP que incluimos en nuestra página debe estar **entre etiqueta de apertura y de cierre** adecuado, que son los siguientes:
```php
<?php // etiqueta de apertura
?> // etiqueta de cierre
```
Todo lo que está contenido entre estas etiquetas **debe coincidir con las reglas de sintaxis de PHP**, y es el código que será ejecutado por el intérprete y no se envía directamente al navegador. Para generar una salida de información al navegador se puede utilizar la función `echo`.
Veamos un ejemplo sencillo, que consiste en código HTML y PHP (recuerda que código PHP está entre `<?php` y `?>` ):
```php
<html>
	<head>
		<title>
		 	<?php echo "Pagina de prueba PHP"; ?>
		</title>
	</head>
	<body>
		<?php echo "Que tengas un buen día!"; ?>
	</body>
</html>
```

-----------------------

short_open_tag boolean
----------------------
Indica a PHP si debería permitirse la forma abreviada de las etiquetas de apertura de PHP (<? ?>). Además, si está desactivada, se debe usar siempre la forma no abreviada de la etiqueta de apertura de PHP (<?php ?>).

Nota:
Esta directiva también afecta a la abreviatura <?= en versiones anteriores a PHP 5.4.0, la cual es lo mismo que <? echo. El uso de esta abreviatura requería que **short_open_tag** estuviese activada. Desde PHP 5.4.0, <?= siempre está disponible.
```php
<?php echo "Pagina de prueba PHP"; ?>
<?= "Pagina de prueba PHP"; ?>
//Ambas líneas son equivalentes siempre que se active short_open_tag en php.ini
```
| php.ini |
|---------|

```php
; short_open_tag
;   Default Value: On
;   Development Value: Off
;   Production Value: Off
;

;
; This directive determines whether or not PHP will recognize code between
; <? and ?> tags as PHP source which should be processed as such. It is
; generally recommended that <?php and ?> should be used and that this feature
; should be disabled, as enabling it may result in issues when generating XML
; documents, however this remains supported for backward compatibility reasons.
; Note that this directive does not control the <?= shorthand tag, which can be
; used regardless of this directive.
; Default Value: On
; Development Value: Off
; Production Value: Off
; http://php.net/short-open-tag
; short_open_tag = Off
short_open_tag = On

```
-----------------------

Este código sencillo **producirá un archivo HTML** cuyo contenido será simplemente:
```php
<html>
	<head>
		<title> Pagina de prueba PHP </title>
	</head>
	<body> Que tengas un buen día!</body>
</html>
```

**Ejercicio 1.** Primera página en PHP - Confecciona un programa que muestre una serie de mensajes en diferentes líneas en la página empleando el comando `echo`
Este es el código que resuelve el ejercicio:
```php
<!DOCTYPE html>
<html>
 	<head>
 		<meta charset="utf-8" />
 		<title>Ejercicio</title>
 	</head>
 	<body>
 		<?php
 			echo "Mi nombre es Juan.<br>";
 			echo "Bienvenido a mi página web.";
		?>
 	</body>
</html>
```

| [Volver al inicio del capítulo](#11php-y-html) | [Ver índice](#indice) |
|------------------------------------------------|-----------------------|

1.1.1.Diferencias entre echo, print, print_r y var_dump
-------------------------------------------------------
**echo**
* Muestra una o más cadenas separadas por comas
* No tiene un valor de retorno
```php
echo "Cadena 1", "Cadena 2";
```
**print**
* Muestra solo una simple cadena
* Devuelve 1, por lo cual puede ser usada en una expresión
```php
print "Hello";
if($expresion && print "Cadena"){
    // Hacer algo
}
```
**print_r()**
* Muestra una representación más entedible de un solo valor cualquiera
* No solo acepta cadenas, también acepta arreglos y objetos formateandolos para ser visualizados de una forma más entendible
* Puede devolver su valor de salida como un valor de retorno si le pasa true como su segundo argumento
* Útil para la depuración

Ejemplo: Si tenemos el siguiente arreglo:
```php
$a = array ('a' => 'manzana', 'b' => 'banana', 'c' => array ('x', 'y', 'z'));
print_r ($a);
```
Nuestro `print_r($a);` nos devolverá algo como esto:
```php
Array
(
    [a] => manzana
    [b] => banana
    [c] => Array
        (
            [0] => x
            [1] => y
            [2] => z
        )
)
```
**var_dump()**
* Muestra una representación más entedible de un valor cualquiera o más separados por comas
* No solo acepta cadenas, también acepta arreglos y objetos formateandolos para ser visualizados de una forma más entendible
* Usa un formato diferente al anterior print_r(), por ejemplo, también muestra el tipo del valor
* Útil para la depuración
* No tiene un valor de retorno

Ejemplo: Si tenemos el siguiente arreglo:
```php
$a = array(1, 2, array("a", "b", "c"));
var_dump($a);
```
Nuestro `var_dump($a);` nos devolverá algo como esto: (notese que nos muestra el tipo de valor de cada elemento en nuestro arreglo)
```php
array(3) {
  [0]=>
  int(1)
  [1]=>
  int(2)
  [2]=>
  array(3) {
    [0]=>
    string(1) "a"
    [1]=>
    string(1) "b"
    [2]=>
    string(1) "c"
  }
}
```
**NOTAS**
* `echo` es mucho más rápido que print
* `echo` y `print` son constructores de lenguaje
* `print_r()` y `var_dump()` son funciones
* `echo` y `print` puedes recibir sus argumentos mediante parentesis como una función `echo("Hello", "world");` ó `print("Hello World");`

| [Volver al inicio del capítulo](#11php-y-html) | [Ver índice](#indice) |
|------------------------------------------------|-----------------------|

1.2.Los Caractéres de Escape
-----------------------------
Los datos se envía al navegador que sigue al comando echo se pueden encerrar entre paréntesis. y la cadena puede usar comillas simples (`''` ) o dobles (`""` ). Hay que tener en cuenta también que el comando `<br />` de HTML no generará un salto de línea en el código PHP (aunque si en el navegador, de la forma clásica). Aquí podemos utilizar el carácter de escape `/n`. Veamos un ejemplo práctico:
```php
<?php
	echo "primera linea\n";
	echo "segunda linea<br />";
	echo "tercera linea";
?>
```
Se verá de la siguiente forma en el código HTML:
```php
primera linea
segunda linea<br>tercera linea
```
Mientras que en el navegador se verá así:
```php
primera linea segunda linea
tercera linea
```
Hay que tener en cuenta también que al final de cada declaración PHP ponemos un punto y coma (;): Se espera que que el punto y coma cierre cada afirmación de forma obligatoria en casi todas las ocasiones. No hacerlo provocará un error.
Hemos visto que los bloques de código en PHP se marcan con las etiquetas `<?php ... ?>`.
También es posible hacerloo con la etiqueta `<script language = "php"> ... </script>` o incluso simplificando la primera que hemos visto: `<? ... ?>`, siempre y cuando en el servidor no se hayan desactivado las etiquetas cortas. El archivo php.ini de nuestro servidor guarda esta configuración. Debido a esta causa, es una buena práctica usar siempre la primera de las estructuras que te hemos mencionado.

**Ejemplo**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>

		<?php

			echo "Primera Línea<br />\n\t\t";
			echo "Segunda Línea<br />\n\t\t";
			echo "Tercera Línea<br />\n\t\t";

		?>

	</body>
</html>
```

| [Volver al inicio del capítulo](#11php-y-html) | [Ver índice](#indice) |
|------------------------------------------------|-----------------------|

1.3.Comentarios en PHP
----------------------

En PHP, como en otros lenguajes de programación, es posible **insertar comentarios** en el código. Los comentarios desempeñan un papel importante en esta fase de mantenimiento del código, ya que pueden facilitar en gran medida la comprensión de los pasajes aparentemente oscuros. Aunque hay varias formas de hacerlos, la notación más frecuente para los comentarios de una sola línea son aquellos que van precedidos por dos barras:
```php
<?php
 	// Esto es un comentario
?>
```
Si deseamos recurrir a los comentarios de varias líneas, la notcación sería la siguiente, similar a Java y C:
```php
<? php
 	/ *
 	Esto es un comentario
 	multilínea
 	usando la misma sintaxis
 	utilizada en Java y C
 	* /
?>
```

**Ejemplo**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>

		<?php

			// esto es un comentario

			echo "Primera Línea<br />\n\t\t";
			echo "Segunda Línea<br />\n\t\t";
			echo "Tercera Línea<br />\n\t\t";

			/*  esto un comentario
				multilínea
				Hola
			*/
		?>

	</body>
</html>
```

| [Volver al inicio del capítulo](#11php-y-html) | [Ver índice](#indice) |
|------------------------------------------------|-----------------------|

1.4.Mostrar los errores de PHP en tiempo de ejecución
-----------------------------------------------------

En bastantes servidores no se muestran los errores PHP por defecto, de ahí que muchas veces al no obtener el resultado o funcionamiento esperado nos rompemos la cabeza revisando líneas y líneas de PHP ignorando que verdaderamente el script nos está dando error.

Con las siguientes funciones colocadas en el comienzo de nuestros ficheros PHP haremos que los errores PHP salgan a la luz:

```php
<?php
error_reporting(E_ALL);
ini_set('display_errors', '1');
?>
```

Adicionalmente os aquí se muestra más código de ejemplo para mostrar o no mostrar los errores de PHP:

```php
<?php
// Motrar todos los errores de PHP
error_reporting(-1);

// No mostrar los errores de PHP
error_reporting(0);

// Motrar todos los errores de PHP
error_reporting(E_ALL);

// Motrar todos los errores de PHP
ini_set('error_reporting', E_ALL);
?>

<?php
// Motrar todos los errores de PHP
error_reporting(-1);

// No mostrar los errores de PHP
error_reporting(0);

// Motrar todos los errores de PHP
error_reporting(E_ALL);

// Motrar todos los errores de PHP
ini_set('error_reporting', E_ALL);
?>
```

| [Volver al inicio del capítulo](#11php-y-html) | [Ver índice](#indice) |
|------------------------------------------------|-----------------------|

----------------------------------

2.VARIABLES
============

2.1.Concepto de Variables
---------------------
Las variables son componentes fundamentales de cualquier lenguaje de programación, ya que nos permite tratar los datos de nuestro programa sin conocer a priori cuál será su valor. Podemos imaginar una variable como una especie de **contenedor en el que se almacena el valor que nos interesa**, y que puede cambiar cuando sea necesario.
En PHP podemos elegir el nombre de las variables utilizando **letras, números y el carácter de subrayado o el guión bajo ( _ )**. El primer carácter del nombre debe, sin embargo, ser una letra o un guión bajo (no un número).
También debemos recordar que el nombre de las variables **es sensible al uso de mayúsculas y minúsculas**, y por lo tanto, si se escribe dos veces el nombre de una variable usando letras mayúsculas y minúsculas de una manera diferente, para PHP serán dos variables distintas.
En PHP, los nombres de variables **están precedidos por un signo de dólar ($)**. PHP tiene una característica que hace que sea mucho más flexible que otros lenguajes de programación, y es que no se requiere que las variables se declaran antes de su uso. Por tanto, podemos darnos el lujo de hacer referencia a una variable directamente cuando la necesitamos:
```php
<?php
	$a = 5;
?>
```
En esta línea de código hemos definidos la variable a, asignándole el valor 5. En la parte final de la declaración vemos el punto y coma, que, como vimos anteriormente, debe cerrar todas las instrucciones PHP. La utilidad de una variable se vuelve crucial en un momento en que puede ser utilizado en expresiones matemáticas o lógicas. Veamos un ejemplo sencillo:
```php
<?php
	$a = 9;
	$b = 4;
	$c = $a * $b;
	echo "El resultado de la operación es: ";
	echo $c;
?>
```
En este fragmento de código, se utilizaron tres variables: *a*, a la que hemos dado el valor *9*, *b*, *a* la que hemos asignado el valor *4*, y *c*, que debe tener el valor del producto de *a* y *b*. Al terminar el código imprimimos el resultado. Evidentemente, después de la ejecución del código, *c* tendrá un valor de *36*.
Si hacemos referencia a **una variable que no existe**, por ejemplo, `$z`, obtendremos un mensaje de error

**Ejercicio 2.** Crea dos variables cuyo nombre sea “uno” y “dos” he imprímelas por pantalla. Pon un comentario con el tipo de dato que contienen.
```php
$frist = "Variable's content 1"; // String
$second = 245; // Integer
echo "FRIST VARIABLE: ".$frist."<br/>";
echo "SECOND VARIABLE: ".$second."<hr/>";
?>
```

| [Volver al inicio del capítulo](#21concepto-de-variables) | [Ver índice](#indice) |
|-----------------------------------------------------------|-----------------------|

2.2.Variables Dinámicas
-----------------------
A veces es conveniente tener nombres de **variables dinámicas**. Dicho de otro modo, son nombres de variables que se pueden establecer y usar de forma variable. Una variable normal se establece con una sentencia como:
```php
<?php
	$a = "hola";
?>
```
Una variable dinámica toma el valor de una variable y lo trata como el nombre de una variable. En el ejemplo anterior, hola, se puede usar como el nombre de una variable utilizando dos signos de dolar. p.ej
```php
<?php
	$$a = "mundo";
?>
```
En este momento se han definido y almacenado dos variables en el árbol de símbolos de PHP: `$a`, que contiene `"hola"`, y  `$hola`, que contiene `"mundo"`. De esta forma, esta sentencia:
```php
<?php
	echo "$a ${$a}";
?>
```
produce el mismo resultado que:
```php
<?php
	echo "$a $hola";
?>
```

**Ejemplo**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>
		<?php
			$a = 5;
			$b = 3;
			$c = $a + $b;

			echo "El resultado de la suma es ";
			echo $c;
		?>
	</body>
</html>
```

| [Volver al inicio del capítulo](#21concepto-de-variables) | [Ver índice](#indice) |
|-----------------------------------------------------------|-----------------------|

----------------------------------

3.TIPOS DE DATOS
=================

3.1.Introducción a los tipos de datos
-------------------------------------

Una variable puede contener diferentes tipos de valores, cada uno de los cuales tiene un comportamiento diferente y utilidad. Vamos a verlo en el siguiente tema.

----------------------------------

**MODO ESTRICTO** Para usar el modo estricto en un archo es necesario declararlo al principio del archivo incluyendo la instrucción `declare(strict_types=1);`, como en el siguiente ejemplo:
```php
<?php declare(strict_types=1);
function suma (int $x, int$y){
	return $x + $y;
}
var_dump(suma('2',6);
```
*Nota* este archivo dará error al introducir dentro de la función suma un dato tipo `string` en el primer parámetro cuando sólo admitía `int`.

| [Volver al inicio del capítulo](#31introducción-a-los-tipos-de-datos) | [Ver índice](#indice) |
|-----------------------------------------------------------------------|-----------------------|

3.2.Gettype()
-------------
Devuelve el tipo de la variable PHP var.
```php
<?php
$data = array(1, 1., NULL, new stdClass, 'foo');
foreach ($data as $value) {
    echo gettype($value), "\n";
}
```
Los posibles valores para la cadena devuelta son: "boolean", "integer", "double" (por razones históricas "double" es devuelto en caso de que un valor sea de tipo float, y no simplemente "float"), "string", "array", "object", "resource", "NULL" y "unknown type"

Para la comprobación de tipos, utilice las funciones `is_*`.
```php
$boolean=true;
is_boolean($boolean);
// imprimirá "true"
```

| [Volver al inicio del capítulo](#31introducción-a-los-tipos-de-datos) | [Ver índice](#indice) |
|-----------------------------------------------------------------------|-----------------------|

3.3.Boleanos
------------
Los tipos de datos booleanos se utilizan para indicar los valores `true` o `false` (verdadero o falso) en expresiones lógicas. El tipo Boolean se asocia a variables que contienen el resultado de una expresión booleana o los valores verdaderos y falsos. Veamos un ejemplo rápido:
```php
<?php
	$verdadero = true;
	$falso = false;
	var_dump($verdadero);
	//imprimirá bool(true)
?>
```
**Ejemplo**
```php
html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>
		<?php
			$alta = true;
			$pagado = false;
		?>
	</body>
</html>
```

| [Volver al inicio del capítulo](#31introducción-a-los-tipos-de-datos) | [Ver índice](#indice) |
|-----------------------------------------------------------------------|-----------------------|

3.4.Entero
----------
Otro tipo de datos es el número entero, positivo o negativo, cuyo valor del máximo (absoluto) puede variar dependiendo del sistema operativo que se ejecuta en PHP, pero que por lo general es, aproximadamente 2 mil millones (2 a la potencia 31a). Veamos ejemplos de algunas variables que definen números enteros:
```php
<?php
	$int1 = 129;
	$int2 = -715;
	$int3 = 5 * 8; // $int3 vale 40
?>
```

**Ejemplo**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>
		<?php
			$ent1 = 129;
			$ent2 = -129;
			$ent3 = 8*5;

			$dec = 4.153;

			$num1 = 332e5; // 3.2 * 10^5 -> 320.000
			$num2 = 4E-8;  // 4*10^8 -> 4/100.000.000 = 0.00000004
		?>
	</body>
</html>
```

**Ejercicio 3.1.** Define una variable de los siguientes tipos: integer, double, string y boolean.
A continuación, imprímelas en la página, una por línea
```php
<!DOCTYPE html>
<html>
 	<head>
 		<meta charset="utf-8" />
 		<title>Ejercicio</title>
 	</head>
 	<body>
 		<?php
 		// Definimos las variables
 			$edad = 30;
 			$peso = 75.50;
 			$nombre = "Juan";
 			$socio = true;
 		// Las imprimimos en pantalla
 			echo "Variable integer:";
 			echo $edad;
 			echo "<br>";
 			echo "Variable double:";
 			echo $peso;
 			echo "<br>";
 			echo "Variable string:";
 			echo $nombre;
 			echo "<br>";
 			echo "Variable boolean:";
 			echo $socio;
 		?>
 	</body>
</html>
```

| [Volver al inicio del capítulo](#31introducción-a-los-tipos-de-datos) | [Ver índice](#indice) |
|-----------------------------------------------------------------------|-----------------------|

3.5.Coma Flotante
-----------------
Este tipo de datos es un número decimal (a veces nos referiremos a él como *"doble"* o *"real"*). Para separar los decimales no usaremos la coma, si no el punto. Esta es la sintaxis que usaremos:
```php
<?php
	$numero1 = 4.153; // 4,153
	$numero2 = 3.2e5; // 3,2 * 10^5, es decir, 320.000
	$numero3 = 4E-8; // 4 * 10^-8, es decir, 4/100.000.000 = 0,00000004
?>
```

**Ejercicio 3.2.** En primer lugar definiremos tres variables con números enteros. A continuación, crearemos una cadena en la que incorporaremos estas tres variables, por ejemplo, ("Las notas del examen han sido...").
```php
<!DOCTYPE html>
<html>
 	<head>
 		<meta charset="utf-8" />
 		<title>Ejercicio</title>
 	</head>
 	<body>
 		<?php
 		// Variables
 			$nota1 = 10;
 			$nota2 = 7;
 			$nota3 = 8;
 		// Cadena a la que incorporamos las variables
 			echo "Las notas del examen han sido $nota1, $nota2 y $nota3";
 		?>
 	</body>
</html>
```

| [Volver al inicio del capítulo](#31introducción-a-los-tipos-de-datos) | [Ver índice](#indice) |
|-----------------------------------------------------------------------|-----------------------|

3.6.Cadena
-----------
Una cadena es **cualquier conjunto de caracteres**, sin limitación normalmente, contenida dentro de un par de comillas dobles o simples. Las cadenas delimitadas por comillas simples son la forma más simple. Este es un ejemplo:
```php
<?php
	$frase = 'Ana dijo: "Hola, pero nadie respondió"';
	echo $frase;
?>
```
Las comillas dobles nos permiten usar cadenas de una manera más sofisticada, de manera que si en la cadena delimitada por comillas dobles, PHP reconoce un nombre de variable, lo reemplaza por el valor de la variable. Veamos algunos ejemplos:
```php
<?php
	$nome = 'Ana';
	echo "$nome es simpatica... a veces";
	// imprime: Ana es simpatica... a veces
	echo '$nome es simpatica... a veces';
	// imprime: $nome es simpatica... a veces
	echo "{$nome} es simpatica... a veces";
	// sintaxis alternativa, con el mismo efecto que la primera
?>
```
Debes tener en cuenta un par de reglas muy importantes cuando se utilizan cadenas delimitadas por **comillas simples o dobles**: Debido a que puede ocurrir que una cadena debe contener en su interior un apóstrofe o un par de comillas, necesitamos un sistema para que sea claro para PHP delimitar que carácter es parte de la cadena y cual su delimitador. En este caso utilizamos el llamado "carácter de escape", es decir, la barra invertida. He aquí algunos ejemplos en italiano, donde usaremos apóstrofes:
```php
<?php
	echo "Torniamo un'altra volta"; // imprime: Torniamo un'altra volta
	echo 'Torniamo un'altra volta'; // Provoca un error
	echo 'Pedro dijo "Adios" y se marchó';
	// imprime: Pedro dijo "Adios" y se marchó
	echo "Pedro dijo "Adios" y se marchó"; // Provoca un error
?>
```
A partir de estos ejemplos podemos ver que la barra invertida debe ser utilizado como un carácter de escape en la cadena cuando queremos incluir el mismo tipo de carácter que delimita.

**Ejemplo**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>
		<?php
			$dia = 15;
			$hoy = "Hoy es el día $dia <br/>";
			$hoy2 = 'Hoy es el día $dia <br/>';

			echo $hoy;
			echo $hoy2;
		?>
	</body>
</html>
```

**Ejercicio 3.3.** Vamos a definir dos variables, una con un nombre y otra con una edad y los insertaremos en la frase "Mi nombre es ____ y tengo ____ años"
```php
<!DOCTYPE html>
<html>
 	<head>
 		<meta charset="utf-8" />
 		<title>Ejercicio</title>
 	</head>
 	<body>
 		<?php
 			$nombre = "Juan";
 			$edad = "25";
 			echo 'Mi nombre es '.$nombre.' y tengo '.$edad.' años.';
 		?>
 	</body>
</html>
```

| [Volver al inicio del capítulo](#31introducción-a-los-tipos-de-datos) | [Ver índice](#indice) |
|-----------------------------------------------------------------------|-----------------------|

3.7.Matrices
------------
Podemos considerar una matriz como una variable compleja, que **contiene una serie de valores**, cada uno de los cuales se caracteriza por una clave, o índice que lo identifica de manera única. Veamos un primer ejemplo, que muestra la definición de un conjunto compuesto por cinco valores:
```php
$color = array('blanco', 'negro', 'azul', 'verde', 'rojo');
```
Cada uno de los cinco colores se caracteriza por un **número de índice**, que PHP asigna automáticamente a partir de 0 para recuperar un valor particular de la variable que contiene la matriz. Así haríamos referencia a ellos:
```php
echo $color[1]; // imprime 'negro'
echo $color[4]; // imprime 'rojo'
```
Por supuesto, veremos las matrices (o **arrays**) en profundidad en un futuro tema.

**Ejemplo**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>
		<?php
			$color = array ('blanco','rojo','azul','verde','amarillo');

			echo $color[1];
			echo '<br/>';
			echo $color[3];
		?>
	</body>
</html>
```

| [Volver al inicio del capítulo](#31introducción-a-los-tipos-de-datos) | [Ver índice](#indice) |
|-----------------------------------------------------------------------|-----------------------|

3.8.Constantes
--------------
Algo constante es algo que no cambia o no varía, esto es exactamente lo que se busca con las constantes en PHP. Las constantes son lo opuesto a las variables en PHP, ya que una vez que se le define su valor este no cambia.
En PHP las constantes se manejan un poco diferente a las variables. Para la asignación de su valor no se utiliza el signo (=), si no que se hace uso de la función `define('NOMBRE','VALOR')` aceptando como primer parámetro el nombre de la constante y como segundo parámetro el dato a asignar. El nombre de la constante no lleva un (`$`) como prefijo y normalmente por convención va todo en mayúsculas.
```php
<?php
    define('URL', 'codehero.co');
    define('FECHA_CREACION', 2013);
    echo URL;			//imprimirá "codehero.co"
    echo FECHA_CREACION; 	//imprimirá "2013"
    ?>
```

| [Volver al inicio del capítulo](#31introducción-a-los-tipos-de-datos) | [Ver índice](#indice) |
|-----------------------------------------------------------------------|-----------------------|

----------------------------------

4.HACIENDO CÁLCULOS EN PHP: EXPRESIONES ARITMÉTICAS Y OPERADORES
================================================================

4.1.Introducción a los operadores
---------------------------------
Los operadores son otro de los elementos básicos de cualquier lenguaje de programación, ya que nos permiten no sólo para realizar las operaciones aritméticas tradicionales, sino además, **manipular los contenidos de nuestras variables**. El operador más clásico y conocido es el de **asignación**.

| [Volver al inicio del capítulo](#41introducción-a-los-operadores) | [Ver índice](#indice) |
|-------------------------------------------------------------------|-----------------------|

4.2.Operadores de asignación
----------------------------
Un ejemplo de operador de asignación lo tendríamos en la expresión `$nombre = "Juan";`
El símbolo `=` se utiliza para asignar a la variable `$nombre` el valor `'Juan'`. En general, podemos decir que con el operador de asignación tomamos lo que está a la derecha del signo del signo de igual y le asignarmos el valor que lo sigue. No solo trabajamos con valores. También es posible asignar a una variable otra variable:
```php
$a = 5;
$b = $a;
```
Con la primera declaración asignamos a `a$` el valor `5`, y con el segundo asignamos a `$b` el mismo valor que tenga `$a`.

**Ejemplo - Operadores de asignación**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
		<link rel="styleshett" href="style.css">
	</head>
	<body>
		<?php
			$a = 4;
			$b = $a + 5;
			$b = ($a = 4);
		?>
	</body>
</html>
```

**Ejemplo - Operadores de asignación**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
		<link rel="styleshett" href="style.css">
	</head>
	<body>
		<?php
			$a = 3;
			$b += 5;
		?>
	</body>
</html>
```

**Ejemplo - Operadores de asignación**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
		<link rel="styleshett" href="style.css">
	</head>
	<body>
		<?php
			$a = 3;
			$b -= 7;
		?>
	</body>
</html>
```

**Ejemplo - Operadores de asignación**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
		<link rel="styleshett" href="style.css">
	</head>
	<body>
		<?php
			$b = "Pedro ";
			$b .= "Pérez";  // "Pedro Pérez"
		?>
	</body>
</html>
```

| [Volver al inicio del capítulo](#41introducción-a-los-operadores) | [Ver índice](#indice) |
|-------------------------------------------------------------------|-----------------------|

4.3.Operadores para concatenar cadenas
--------------------------------------
Dentro de los operadores que se emplean para trabajar con cadenas de caracteres, uno de los más comunes es elpunto, que se emplea para concatenar, unir cadenas.
```php
$nombre = "Juan";
$cadena = "Hola ".$nombre; // $cadena equivale a 'Hola Juan'
```

| [Volver al inicio del capítulo](#41introducción-a-los-operadores) | [Ver índice](#indice) |
|-------------------------------------------------------------------|-----------------------|

4.4.Operadores aritméticos
--------------------------
Otros operadores muy fáciles de entender son los que permiten realizar operaciones aritméticas con los datos: **suma, resta, división, multiplicación o módulo**.
```php
	$a = 3 + 7; // suma
	$b = 5 - 2; // resta
	$c = 9 * 6; // multiplicación
	$d = 8 / 2; // divisioón
	$e = 7 % 4; // modulo (el módulo es el resto de la división entera, en este caso 3)
```
Con el operador de asignación también puede usar una variable para hacer un cálculo cuyo resultado debe ser asignado a la variable. Por ejemplo, supongamos que tenemos una variable a la que queremos aumentar el valor:
```php
	$a = $a + 10; // el valor de $a aumenta en 10
```
Con esta instrucción, se realiza el cálculo, que está a la derecha del signo `=` y el resultado se almacena en la variable que se muestra a la izquierda.
Resultados como los que hemos visto también se puede lograr con los operadores de asignación combinados, que nos permiten hacer el código más compacto:
```php
	$x += 4; // incrementa $x en 4 (equivale a $x = $x + 4)
	$x -= 3; // decrementa $x en 3 (equivale a $x = $x - 3)
	$x .= $a;
// el valor de la cadena $a se concatena a $x (equivale a $x = $x . $a)
	$x /= 5; // equivale a $x = $x / 5
	$x *= 4; // equivale a $x = $x * 4
	$x %= 2; // equivale a $x = $x % 2
```
De esta manera, le decimos a PHP que queremos asignar a la variable especificada a la izquierda el resultado de la operación que está delante del signo igual y el valor especificado a la derecha.

**Ejemplo - Operadores aritméticos**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
		<link rel="styleshett" href="style.css">
	</head>
	<body>
		<?php

			$a = 5;
			$b = 9;

			echo "Suma: ";
			echo $a + $b;

			echo "<br/>Resta: ";
			echo $a - $b;

			echo "<br/>Multiplicación: ";
			echo $a * $b;

			echo "<br/>División: ";
			echo $a / $b;

			echo "<br/>Módulo: ";
			echo $a % $b;

		?>
	</body>
</html>
```

**Ejemplo - Operadores aritméticos**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
		<link rel="styleshett" href="style.css">
	</head>
	<body>
		<?php

			$a = 4;
			$b = 5;
			$c = 3;

			echo $a-$b*$c;
			echo '<br/>';
			echo ($a-$b)*$c;

		?>
	</body>
</html>
```
**Ejercicio 4.1.** Vamos a crear una función que calcule el 25% de 325 y lo muestre en pantalla.
```php
<!DOCTYPE html>
<html>
 	<head>
 		<meta charset="utf-8" />
 		<title>Ejercicio</title>
 	</head>
 	<body>
 		<?php
 			$porcentaje = (25 * 325) / 100;
 			echo 'El porcentaje 25% de 325 es: '.$porcentaje;
 		?>
 	</body>
</html>
```

**Ejercicio 4.2.** Calcularemos el IVA del 21%de un producto que vale 43.90 y lo mostraremos por pantalla
```php
<!DOCTYPE html>
<html>
 	<head>
 		<meta charset="utf-8" />
 		<title>Ejercicio</title>
 	</head>
 	<body>
 		<?php
 			$iva = (21 * 43.90) / 100;
 			echo 'El IVA del producto de 43,90 es: '.$iva;
 		?>
 	</body>
</html>
```

| [Volver al inicio del capítulo](#41introducción-a-los-operadores) | [Ver índice](#indice) |
|-------------------------------------------------------------------|-----------------------|

4.5.Incremento y decremento
---------------------------
Si necesitas aumentar y disminuir una variable en una unidad, una buena solución es usar los operadores de incremento y decremento:
```php
	$a++; // incrementa en 1
	++$a; // incrementa en 1
	$a--; // decrementa en 1
	--$a; // decrementa en 1
```
La diferencia entre el prefijo y posponer el incremento o decremento es crucial cuando se utilizan estos operadores en expresiones, como ya veremos.

**Ejemplo - Incremento y decremento**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
		<link rel="styleshett" href="style.css">
	</head>
	<body>
		<?php

			$a = 15;
			$b = 15;

			echo --$a;
			echo '<br/>';
			echo $b--;
			echo '<br/>';
			echo $b;
		?>
	</body>
</html>
```
**Ejemplo - Incremento y decremento**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
		<link rel="styleshett" href="style.css">
	</head>
	<body>
		<?php

			$a = 15;
			$b = 15;

			echo ++$a;
			echo '<br/>';
			echo $b++;
			echo '<br/>';
			echo $b;
		?>
	</body>
</html>
```

**Ejercicio 4.3** Vamos a definir dos variables numéricas enteras, $a y $b. Asígnales el valor que quieras. Realiza los cálculos y muestra en pantalla su suma, su resta, su multiplicación y su división. A continuación, incrementa las dos variables en una unidad y muestra en pantalla el resultado.
```php
<!DOCTYPE html>
<html>
 	<head>
 		<meta charset="utf-8" />
 		<title>Ejercicio</title>
 	</head>
	<body>
 		<?php
 		// Definimos las variables
 			$a = 8;
 			$b = 3;
 		// Suma, resta, multiplicación y división
 			echo $a + $b, "<br>";
 			echo $a - $b, "<br>";
 			echo $a * $b, "<br>";
 			echo $a / $b, "<br>";
 		// Incrementamos y mostramos las variables
 			$a++ ;
 			echo $a,"<br>";
 			$b++;
 			echo $b,"<br>";
 		?>
 	</body>
</html>
```

| [Volver al inicio del capítulo](#41introducción-a-los-operadores) | [Ver índice](#indice) |
|-------------------------------------------------------------------|-----------------------|


4.6.Operadores de Comparación
-----------------------------
Los operadores de comparación, como su nombre lo indica, permiten comparar dos valores. Puede también estar interesado en ver las tablas de comparación de tipos, ya que muestran ejemplos de las varias comparaciones relacionadas con tipos.

| **Ejemplo**	|**Nombre**            | **Resultado**                                                      |
|---------------|----------------------|--------------------------------------------------------------------|
|$a == $b	|Igual	               |TRUE si $a es igual a $b después de la manipulación de tipos.       |
|$a === $b	|Idéntico	       |TRUE si $a es igual a $b, y son del mismo tipo.                     |
|$a != $b	|Diferente	       |TRUE si $a no es igual a $b después de la manipulación de tipos.    |
|$a <> $b	|Diferente	       |TRUE si $a no es igual a $b después de la manipulación de tipos.    |
|$a !== $b	|No idéntico	       |TRUE si $a no es igual a $b, o si no son del mismo tipo.            |
|$a < $b	|Menor que	       |TRUE si $a es estrictamente menor que $b.                           |
|$a > $b	|Mayor que	       |TRUE si $a es estrictamente mayor que $b.                           |
|$a <= $b	|Menor o igual que     |TRUE si $a es menor o igual que $b.                                 |
|$a >= $b	|Mayor o igual que     |TRUE si $a es mayor o igual que $b.                                 |
|$a <=> $b	|Nave espacial	       |Un integer menor que, igual a, o mayor que cero cuando $a es respectivamente menor que, igual a, o mayor que $b. Disponible a partir de PHP 7.                                                      |
|$a ?? $b ?? $c	|Fusión de null	       |El primer operando de izquierda a derecha que exista y no sea NULL. NULL si no hay valores definidos y no son NULL. Disponible a partir de PHP 7.                                              |

| [Volver al inicio del capítulo](#41introducción-a-los-operadores) | [Ver índice](#indice) |
|-------------------------------------------------------------------|-----------------------|

4.7.Operadores Lógicos
----------------------
| **Ejemplo**	|**Nombre**        | **Resultado**                             |
|---------------|------------------|-------------------------------------------|
| $a and $b	| And (y)	   | TRUE si tanto $a como $b son TRUE.        |
| $a or $b	| Or (o inclusivo) | TRUE si cualquiera de $a o $b es TRUE.    |
| $a xor $b	|Xor (o exclusivo) | TRUE si $a o $b es TRUE, pero no ambos.   |
| ! $a	        | Not (no)	   | TRUE si $a no es TRUE.                    |
| $a && $b	| And (y)	   | TRUE si tanto $a como $b son TRUE.        |
| $a || $b	| Or (o inclusivo) | TRUE si cualquiera de $a o $b es TRUE.    |

| [Volver al inicio del capítulo](#41introducción-a-los-operadores) | [Ver índice](#indice) |
|-------------------------------------------------------------------|-----------------------|


----------------------------------

5.ESTRUCTURAS DE CONTROL
========================

5.1.Instrucción condicional If
------------------------------

Las estructuras de "control de flujo" nos presentan un aspecto fundamental de la programación: la capacidad de realizar diferentes operaciones, y si lo deseamos, ejecutarlas varias veces, sobre la base de la evaluación de determinadas condiciones.
La instrucción If es la más representativa de las estructuras de control de flujo: nos permite realizar o no ciertas porciones de código. Veamos la sintaxis más básica:

```php if (<condicion>) <instruccion> ```

Después del if se indica en la expresión entre paréntesis que debe ser evaluada condición). Esta expresión se evaluará en el sentido booleano, es decir, su valor se considera verdadero o falso.
Por lo tanto, si la condición es verdadera, se ejecuta la siguiente instrucción, de lo contrario, se ignora.
A menudo el cumplimiento de la condición puede derivar no en una, si no en varias instrucciones. Esto es perfectamente posible, siempre y cuando encerremos ese código entre llaves, como podemos ver en el siguiente ejemplo:
```php
if ($nombre == 'Juan') {
 	echo "Hola Juan!<br>";
 	echo "¿Quieres ver tus nuevas fotos?<br />";
}
echo "Hola a todo el mundo!";
```

Si la variable $nombre tiene el valor `'Juan'` se cumplirán las instrucciones posteriores incluidas en las llaves. Después de evaluar la condición y si es oportuno, ejecutar las dos instrucciones propuestas, el script continuará con lo que está fuera de las llaves. Así, en nuestro ejemplo, la frase "hola a todos ustedes" se producirá en todos los casos.
**NOTA :** Es una buena idea usar las llaves para delimitar el código condicional siempre, aun cuando conste de una sola sentencia: de hecho, esto hace que el código sea más legible, y también puede ayudar a evitar errores si deseamos añadir instrucciones al bloque condicional en el futuro y nos olvidamos de las llaves.
Debemos tener en cuenta una particularidad sobre la sintaxis de esta instrucción: por primera vez en el curso vemos que en esta estructura no termina con punto y coma.

**[Regresar al índice](#indice)**

----------------------------------

5.1.1.Operadores de igualdad (==) y Asignación (=)
--------------------------------------------------

Veamos un caso que a menudo crea problemas si no se entiende desde el principio. Veamos este código, por ejemplo:
```php
$a = 7;
$b = "7";
var_dump($a == 4);
// imprimirá bool(false)
var_dump($a == 7);
// imprimirá bool(true)
var_dump($a != 4);
// imprimirá bool(true)
var_dump($a == $b);
// imprimirá bool(true)
var_dump($a === $b);
// imprimirá bool(false)
var_dump($a !== $b);
// imprimirá bool(true)
if ($a != 4) echo '$a es igual a 4!';
```
A primera vista, podemos ser engañados por estas instrucciones, especialmente tienes experiencia con lenguajes de programación en los que una expresión como `$a = 4` puede ser tanto una asignación como una comparación. Si pensamos que este bloque de código no se cumplirá, seremos sorprendidos al ver en el navegador la frase '$a es igual a `4'`.
La expresión que hemos puesto entre paréntesis es una asignación: es decir, se asigna un valor a la variable `$a`. La siguiente declaración se ejecuta a continuación considera que el valor de nuestra expresión es `4`, que PHP equivalente a una verdad booleana. Si en lugar de `if ($a = 4)` hubiesemos escrito `if ($a = 0)`, la siguiente declaración se habría perdido, porque nuestra condición tendría un valor de `0`, lo que sería falso.
Para obtener el resultado correcto debemos utilizar el operador de comparación que es un doble signo de igual (==):
```php
$a = 7;
if ($a == 4) echo '$a es igual a 4!';
```
Recordemos siempre utilizar correctamente el operador condicional de igualdad, el doble igual ( `==` ) para comparaciones.

**Ejemplo - Condicional If**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
		<link rel="stylesheet" href="style.css">
	</head>
	<body>
		<?php

			$nota = 10;
			if ($nota == 10) echo"Eres muy bueno!!";

			echo "<br/>Tienes una nota de $nota";
		?>
	</body>
</html>
```

**Ejemplo - Condicional If**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>
		<?php

			$nombre = 'Juan';
			if ($nombre == 'Juan') {
				echo "Hola $nombre<br/>";
				echo "Quieres ver tus fotos más recientes?<br/>";
				echo "Gracias por tu visita<br/>";
				$a = 5;
				$b = $a * 50;
			}

			echo "Hola a todos";
		?>
	</body>
</html>
```

**Ejemplo - Condicionale If**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>
		<?php

			$a = 9;
			$b = 9.0;
			$c = 3;

			if ($a != $c) { echo "ES VERDADERO!"; }

		?>
	</body>
</html>
```

**Ejemplo - Condicionale If**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>
		<?php

			$a = 'Mario';
			$b = 'Juanazo';
			$c = 'Juanito';
			$d = 'antonio';
			$e = '4gatos';

			if ($a > $e) { echo"es VERDADERO"; }

		?>
	</body>
</html>
```

**Ejercicio 5.1.** Una variable llamada $precio contendrá el precio de un artículo. Crea una estructura condicional para que en caso de que el precio sea mayor o igual a 100, aparezca en pantalla el rótulo "Este artículo es muy caro!"
```php
<!DOCTYPE html>
<html>
 	<head>
 		<meta charset="utf-8" />
		 <title>Ejercicio</title>
 	</head>
 	<body>
 		<?php
 			$precio = 150;
 			if ($precio >= 100) echo 'Este artículo es muy caro!';
 			?>
 	</body>
</html>
```

**Ejercicio 5.2.** Vamos a crear dos variables numéricas, $a y $b, con las cifras que desees. A
continuación, realiza las siguientes tareas:
* Haz que ambas variables aparezcan en pantalla con sus correspondientes valores
* Si $a es mayor que $b, haremos que aparezca en pantalla el mensaje "A es mayor que B"
* Si $b es mayor que $a, el mensaje que aparecerá es "B es mayor que A".
* Si ambas son iguales, se mostrará el mensaje "A y B son iguales".
```php
<!DOCTYPE html>
<html>
 	<head>
 		<meta charset="utf-8" />
 		<title>Ejercicio</title>
 	</head>
 	<body>
 		<?php

 			$a = 2;
 			$b = 9;
 			echo "Valor de a: ".$a." y el valor de b:".$b."<br>";
 			if ($a < $b){ echo "B es mayor que A"; }
 			if ($a > $b) { echo "A es mayor que B"; }
 			if ($a == $b) { echo "A y B son iguales"; }
 		?>
 	</body>
</html>
```

**Ejercicio 5.3.** Una variable guardará un valor numérico entero. El programa deberá mostrar un mensaje si el número es par y otro si es impar. También debes prever el caso de que el número no sea un entero positivo.
```php
<html>
 	<head>
 		<title>Ejercicio</title>
 	</head>
 	<body>
		<?php
			$numero=154;
 			if($numero > 0){
 				if($numero % 2 == 0) {echo("El numero $numero es par");}
 				if($numero % 2 == 1) { echo("El numero $numero es impar");}
			}
 			if($numero <= 0) { echo("El numero $numero no es entero positivo");
 		?>
	</body>
</html>
```

**Ejercicio 5.4.** Operadores Lógicos: AND, OR, XOR...
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>
		<?php

			$a = 1;
			$b = 8;
			$c = 3;
			$d = 1;

			if ($a == $d and $b > $c and $c > $d) { echo "Es Verdadero!!"; }

		?>
	</body>
</html>
```

**Ejercicio 5.5.** Operadores Lógicos: AND, OR, XOR...
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>
		<?php

			$a = 1;
			$b = 8;
			$c = 3;
			$d = 1;

			if ($a == $d xor $d > $c) { echo "Es Verdadero!!"; }

		?>
	</body>
</html>
```

**Ejercicio 5.6.** Operadores Lógicos: AND, OR, XOR...
| index.php |
|------------|
```php
<!DOCTYPE html>
<html lang="en">
<body>
	<form name="input" action="acceso.php"method="get">
		Nombre:<input type="text" name="nombre"><br>
		Password:<input type="text" name="pass"><br>
		<inpute type="submit" value="Enviar">
	</form>
</body>
</html>

```
| acceso.php |
|------------|
```php
<?php
//Base de datos simulada
$user = "david";
$password = "1234";
?>
<?php
$nombre = $_GET['nombre'];
$pass = $_GET['pass'];
//Solución
if($user == $nombre && $password == $pass){
	echo "Los datos son corrector";
}else{
	echo "los datos NO son incorrectos";
}
?>
```

**[Regresar al índice](#indice)**

----------------------------------

5.2.Else y Elseif
-----------------
|Else |
|-----|
Vamos con un análisis un poco más profundo de la instrucción if: nos permite no sólo indicar la instrucción que queremos ejecutar si la condición es verdadera, sino también un bloque de código que se ejecuta cuando la condición es falsa. He aquí cómo:
```php
If (<condición>) {
 <código>
} else {
 <código>
}
```
La palabra clave else, que significa **'en otro caso'**, debe colocarse **inmediatamente después de la llave de cierre** del código proporcionado por el caso `'true'`. Para else se aplican las mismas reglas que vimos en el caso del `if`: no hay punto y coma, las llaves son obligatorias si tenemos más de una instrucción. Obviamente, el bloque de código especificado para else es ignorado cuando la condición es verdadera, y se ejecuta sólo si la condición es falsa.
Las instrucciones `if` pueden ser anidadas una dentro de otras, lo que nos permite crear código de una cierta complejidad. Ejemplo:
```php
if ($nombre == 'Juan') {
 	if ($apellido == 'Lopez') {
 		print "Juan Lopez, bienvenido a nuestra página";
 	} else {
 		print "Tenemos un nuevo Juan entre nosotros!";
 	}
} else {
 	print "Hola $nombre!";
}
```
En este caso, tenemos un ejemplo de anidado dentro del primer caso, en el que $nombre tiene el valor `'Juan'`. De hecho, esperábamos un mensaje diferente, dependiendo del valor de la variable `$nombre`.

**Ejemplo - Else y Elseif**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>
		<?php

			$nota = 6;

			if ($nota <5) { echo "estás suspendido"; } else { echo "estás APROBADO!!"; }

		?>
	</body>
</html>
```

**Ejemplo - Else**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>
		<?php

			$nombre = 'Pedro';
			$apellido = 'Alonso';

			if ($nombre == 'Pedro') {

				if ($apellido == 'Alonso') { echo "Hola, cómo estás querido amigo!!"; } else { echo "Hola Pedro, cómo te va?"; }

			} else { echo "Hola $nombre"; }


		?>
	</body>
</html>
```

**Ejemplo - Else**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>
		<?php

			$nota = 10;

			if ($nota >= 5) {

				if ($nota == 10) { echo "MATRICULA DE HONOR!!";
			} else { echo "Estás Aprobado"; }

			} else { echo "Estás Suspendido"; }

		?>
	</body>
</html>
```

**Ejercicio 5.7.** La variable $num contendrá un valor entero entre 1 y 3. Deberemos crear una estructura condicional que haga aparecer en pantalla el nombre del número con letras (por ejemplo, si el número es 3, deberá verse "tres").
```php
<!DOCTYPE html>
<html>
 	<head>
 		<meta charset="utf-8" />
 		<title>Ejercicio</title>
 	</head>
 	<body>
 		<?php
 			$num = 2;
 			if ($num == 1) {
 				echo "uno";
 			}  else  {
 				if($num == 2)	{
 					echo "dos";
 				} else {
 					echo "tres";
 				}
 			}
 		?>
 	</body>
</html>
```

**Ejercicio 5.8.** Para realizar este ejercicio, en primer lugar deberemos conocer una nueva función matemática que no hemos tratado en el tema.
La función rand() genera un número aleatorio. Admite dos parámetros, que serán el número inicial y final entre los que queremos ese número al azar.
Usando esta función, vamos a crear un número entre 1 y 100, es decir, rand(1,100);
Crearemos una estructura condicional que nos diga cuantos dígitos tiene ese número, uno, dos o tres.
```php
<!DOCTYPE html>
<html>
 	<head>
 		<meta charset="utf-8" />
 		<title>Ejercicio</title>
 	</head>
 	<body>
 		<?php
 			$valor = rand(1,100);
 			echo "El valor sorteado es $valor<br>";
 			if ($valor <= 9){
 				echo "Tiene un dígito";
			 } else {
 				if ($valor < 100) {
 					echo "Tiene 2 dígitos";
				} else {
 					echo "Tiene 3 dígitos";
 				}
 			}
 		?>
 	</body>
</html>
```

**Ejercicio 5.9.** Partimos de tres variables numéricas enteras, a las que llamaremos $a, $b y $c. Debemos elaborar un programa que indique cual es el mayor y cual el menor.
```php
<!DOCTYPE html>
<html>
 	<head>
 		<meta charset="utf-8" />
 		<title>Ejercicio</title>
 	</head>
 	<body>
 		<?php
 			$a = 10;
 			$b = 12;
 			$c = 23;

 			if ($a > $b) {
 				$mayor = 'a';
 				$menor = 'b';
 				if ($b > $c) {	$menor = 'c'; }
 				if ($c > $a) { $mayor = 'c'; }
			} else {
				$mayor = $b;
 				$menor = $a;
				if ($b > $c) { $menor = 'c'; }
				if ($c > $a) { $mayor = 'c'; }
 			}
			echo 'la mayor es: '.$mayor.'<br>';
			echo 'la menor es: '.$menor.'<br>';
 		?>
 	</body>
</html>
```

**[Regresar al índice](#indice)**

----------------------------------

|Elseif |
|-------|
Otra posibilidad que nos da la instrucción if en PHP es utilizar la palabra clave elseif. A través de ella podemos indicar una segunda condición, que se evaluará sólo en el caso en que el anterior resulte ser falsa.
```php
if ($nombre == 'Juan') {
	print "Bienvenido Juan!";
} elseif ($apellido == 'Lopez') {
	print "Bienvenido, señor Lopez";
} else {
	print "Hola $nombre!";
}
```
En este caso, tenemos una instrucción a ejecutar cuando $nombre es `'Juan'`; en el caso de que no sea cierto, hay una segunda instrucción si `$apellido` es `'Lopez'`; incluso si esta se cumple, se pondrá en funcionamiento la tercera condición. Ten en cuenta que si $nombre es `'Juan'` y `$apellido` es `'Lopez'`, está siendo ejecutada solo la primera declaración, ya que después de comprobar el estado, todos los demás casos se omiten.
Si quieres ver más casos prácticos, recuerda que en nuestra sección de ejercicio podrás ver mucho más donde practicar esta y otras lecciones.

**Ejemplo - Elseif**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>
		<?php

			$a = 5;
			$b = 5;

			if ($a > $b) { echo "A es mayor que B";
			} elseif ($a == $b) { echo "A es igual a B";
			} else { echo "B es mayor que A";
		}

		?>
	</body>
</html>
```

**Ejemplo - Elseif**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>
		<?php

			$edad = 80;

			if ($edad >= 18) {echo"Mayor de 18";
		}	elseif ($edad >= 35) {echo"Mayor de 35";
		}	elseif ($edad >= 65) {echo"Mayor de 65";
		}	else { echo"Eres menor de edad";
		}

		?>
	</body>
</html>
```
**Ejercicio 5.10.**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>
		<?php

			$sexo = 'M';
			$idioma = 'inglés';

			if ($sexo == 'H') {
				if ($idioma == 'español') { echo"Eres hombre y hablas español";
				} elseif ($idioma == 'francés') {echo"Eres hombre y hablas francés";
				} else { echo"Eres hombre y hablas inglés";}
			} else {
				if ($idioma == 'español') { echo"Eres mujer y hablas español";
				} elseif ($idioma == 'francés') {echo"Eres mujer y hablas francés";
				} else { echo"Eres mujer y hablas inglés";}
			}



		?>
	</body>
</html>
```

**Ejercicio 5.11.**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>
		<?php

			$sexo = 'H';
			$idioma = 'español';

			if ($sexo == 'H' and $idioma == 'español') { echo"eres hombre y hablas español";
		} elseif ($sexo == 'H' and $idioma == 'francés') {echo"eres hombre y hablas francés";
		} elseif ($sexo == 'H' and $idioma == 'inglés') {echo "eres hombre y hablas inglés";
		} elseif ($sexo == 'M' and $idioma == 'español') { echo"eres mujer y hablas español";
		} elseif ($sexo == 'M' and $idioma == 'francés') {echo"eres mujer y hablas francés";
		} else {echo "eres mujer y hablas inglés";
		}

		?>
	</body>
</html>
```

**Ejercicio 5.12.** Tabla de notas usando las instrucciones If, Else y Elseif
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>
		<?php

			$nota = 3;

			if ($nota == 10) { echo "Matrícula de Honor";
		} elseif ($nota >= 7) { echo "Notable";
		} elseif ($nota >= 6) { echo "Bien";
		} elseif ($nota >= 5) { echo "Aprobado";
		} else { echo "Suspendido";
		}

		?>
	</body>
</html>
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejercicio 5.13.** Escribe un programa que compruebe si una variable esta vacía y si está vacía, rellenarla con texto en minúsculas y mostrarlo convertido a mayúsculas en negrita.
```php
<?php
$string="";
if ( empty($string)){
	$string=strtoupper("Texto de relleno");
	echo "<strong>{$string}</strong>";
}else{
	echo "Esta rellena";
}
?>
```

**[Regresar al índice](#indice)**

----------------------------------

5.3.Switch
-----------

Vamos a estudiar ahora una segunda instrucción que nos permite **evaluar diversos valores y ejecutar un código determinado en cada caso**:
```php
switch (<condición>) {
	case <valor 1>:
		<código>
		break;
	case <valor 2>:
		<código>
		break;
	....
	default:
		<código>;
		break;
	}
```
La instrucción switch requiere que le indiquemos, entre paréntesis, una **expresión que se evaluará por su valor** (esta vez no es necesariamente un valor booleano, como pasaba en if). A continuación detallaremos una serie de expresiones que serán comparadas con la
dada anteriormente: en el momento en que encuentra un valor igual, PHP ejecutar el código que le sigue, hasta que encuentra la instrucción `break`. Como podemos ver en el ejemplo, las expresiones que deben compararse con la primera está precedida por la palabra clave case y seguido de dos puntos. La instrucción default está indicada como "último caso", que se considera verificada cuando ninguno de los casos anteriores se cumple. Esta indicación al valor por defecto, default, puede estar ausente si lo consideramos correcto.
Es muy importante entender el funcionamiento de la instrucción break en este entorno: al comprobar PHP la validez uno de los casos, se lleva a cabo no sólo el código que se encuentra inmediatamente después, sino también **todo lo que está por debajo**, incluyendo el correspondiente a los casos siguientes si nada le para. Es decir, hasta que la encuentra una instrucción break. Si no colocamos la instrucción **break** al final de un bloque de código la ejecución continuaría al siguiente caso, cosa que nos puede interesar o no, según nuestras intenciones. Veamos un ejemplo práctico

```php
switch ($nombre) {
	case 'Juan':
	case 'Pedro':
	case 'Maria':
		print "Hola, viejos amigos!";
		break;
	case 'Mario':
		print "Hola, Mario!";
		break;
	case 'Laura':
		print "Bienvenida, Laura!";
		break;
	default:
		print "Bienvenido, seas quien seas!";
}
```

En este caso, nos esperaba un solo mensaje para el caso en que la variable `$nombre` sea `'Juan'`, `'Pedro'`, o `'María'`.

**[Regresar al índice](#indice)**

----------------------------------

**Ejemplo - Switch**

```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>
		<?php

		$quiniela = '3';

		switch ($quiniela) {

			case '1':
				echo "Ha ganado el equipo de casa, enhorabuena!!";
				break;

			case 'X':
				echo "Ha habido un empate";
				break;

			case '2':
				echo "Ha ganado el equipo visitante!!";
				break;

			default:
				echo "Eso no está bien, no admitimos como valor $quiniela";
		}


		?>
	</body>
</html>
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejercicio 5.14.** Utilizando switch, crearemos un programa que en base al valor de una variable numérica que puede estar entre 1 y 7, nuestre el nombre del día de la semana asociado. Por ejemplo 1 -> Domingo, 2 -> Lunes.

```php
<!DOCTYPE html>
<html>
	<head>
 		<meta charset="utf-8" />
 		<title>Ejercicio</title>
 	</head>
 	<body>
 		<?php
 			$dia = 2;
 			switch ($dia) {
 				case 1:
 					echo 'Domingo';
 				break;
 				case 2:
 					echo 'Lunes';
 				break;
 				case 3:
 					echo 'Martes';
 				break;
 				case 4:
 					echo 'Miércoles';
 				break;
 				case 5:
					echo 'Jueves';
 				break;
				case 6:
 					echo 'Viernes';
 				break;
 				case 7:
 					echo 'Sábado';
 				break;
 				default:
 					echo 'Ese número no se corresponde con ningún día de la semana!';
 				break;
 			}
 		?>
 	</body>
</html>
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejercicio 5.15.** La variable $color guardará uno de los colores del arco iris, a tu elección (son rojo, naranja, amarillo, verde, azul, añil y violeta)
En función del color que se haya guardado en la variable, el programa mostrará un verso representativo (no importa su contenido, solo es para practicar)

```php
<!DOCTYPE html>
<html>
 	<head>
 		<meta charset="utf-8" />
 		<title>Ejercicio</title>
 	</head>
 	<body>
 		<?php
 			$color = "naranja";
 			echo "El color elegido es ".$color."<br>";
 			switch($color){
 				case "rojo":
 					echo "Como me gusta el color colorado!!";
 				break;
 				case "naranja":
 					echo "El color del butano!!";
 				break;
 				case "amarillo":
 					echo "Tan amarillo como los limones!!";
 				break;
 				case "verde":
 					echo "Verde que te quiero verde!!";
 				break;
				case "azul":
 					echo "Como el azul del cielo!!";
 				break;
 				case "añil":
 					echo "Alguien sabe cómo se ve el añil? ;-)";
 				break;
 				case "violeta":
 					echo "Un ramillete de hermosas florecillas!!";
 				break;
 				default:
 					echo "Qué color es ese? :-O";
 			}
 		?>
 	</body>
</html>
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejemplos prácticos**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>
		<?php

			$variable = 54;

			switch ($variable) {

				case 1:
					echo '$variable es igual a 1';
					break;
				case 2:
					echo '$variable es igual a 2';
					break;
				case 3:
					echo '$variable es igual a 3';
					break;
				default:
					echo '$variable no es ni 1, ni 2, ni 3';
			}

		?>
	</body>
</html>
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejemplo práctico - Tabla de edades construida con la instrucción switch**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>
		<?php

			$edad = 25;

			switch ($edad) {

				case ($edad < 18):
					echo "Eres menor de edad, fuera!";

				case ($edad >= 18) and ($edad <= 35):
					echo "Eres mayor de edad, bienvenido!";

				case ($edad > 35) && ($edad < 65):
					echo "Eres un madurito";

				default:
					echo "Eres de la tercera edad";

			}

		?>
	</body>
</html>
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejemplo práctico - Horoscopo Chino**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>
		<?php

			$year = 2014;
			echo "Tu año de nacimiento es $year y te corresponde en el horóscopo chino el ";

			switch ($year%12) {
				case 0:
					echo "Mono";
					Break;
				case 1:
					echo "Gallo";
					Break;
				case 2:
					echo "Perro";
					Break;
				case 3:
					echo "Jabalí";
					Break;
				case 4:
					echo "Rata";
					Break;
				case 5:
					echo "Buey";
					Break;
				case 6:
					echo "Tigre";
					Break;
				case 7:
					echo "Conejo";
					Break;
				case 8:
					echo "Dragon";
					Break;
				case 9:
					echo "Serpiente";
					Break;
				case 10:
					echo "Caballo";
					Break;
				case 11:
					echo "Caballo";
					Break;

			}


		?>
	</body>
</html>
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejemplo práctico - Cómo usar break**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>
		<?php

			$nombre = "kjklklj";

			switch ($nombre) {

				case "Juan":
				case "María":
				case "Ana":
					echo "Bienvenidos, queridos amigos VIP";
					echo "<br/>Cuanto tiempo sin veros!!";
					break;

				case "Mario":
					echo "Que pasa, Mario";
					break;

				case "Luisa":
				case "Maribel":
					echo "Hola, hermanas Sánchez";
					break;

				default:
					echo "Hola, cómo estás!!";
					break;
			}

		?>
	</body>
</html>
```

**[Regresar al índice](#indice)**

----------------------------------

5.4.Operador Ternario
---------------------

El operador ternario es llamado así porque se compone de tres expresiones: el valor devuelto son la segunda o tercera de estas expresiones, dependiendo de si la primera es
verdadera o falsa. En la práctica, se puede considerar una manera muy concisa para hacer una sentencia if.
```php
($altura >= 180) ? 'alto' : 'normal';
```
Esta expresión toma el valor "alto" si la variable $altura es mayor o igual a 180, y "normal" en el caso contrario. Como vemos, la expresión condicional se encuentra en paréntesis y seguida por un signo de interrogación, mientras que dos puntos separan a la segunda expresión de la tercera. Esta construcción se puede utilizar, por ejemplo, dando valor a una variable rápidamente sin recurrir a if:
```php
$tipologia = ($altura >= 180) ? 'alto' : 'normal';
```
equivaldría a escribir:
```php
if ($altura >= 180) $tipologia = 'alto';
else
$tipologia = 'normal';
```
Como se puede ver, en términos de ahorro de espacio es bastante significativa. Pero hay que tener cuidado de abusar de esta forma, ya que a veces puede hacer que sea más difícil legibilidad de nuestro códigod, aunque es sin duda útil en caso de que necesite hacer el código más compacto.

**Ejemplo**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>
		<?php

			$hora = date('G');

			$mensaje = ($hora >= 12) ? "Buenas Tardes" : "Buenos Días";
			echo "Son las $hora, $mensaje";

		?>
	</body>
</html>
```

**Ejemplo**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>
		<?php

		$nota = 4;

		$mensaje = ($nota >= 5) ? "Eres muy bueno, has aprobado" : "Has suspendido";
		echo "Has sacado un $nota, $mensaje";

		?>
	</body>
</html>
```

**[Regresar al índice](#indice)**

----------------------------------

5.5.For
--------

Comencemos con un ejemplo (como de costumbre bastante trivial). Supongamos que deseamos mostrar de 1 a 10 múltiplos de un número, por ejemplo de 5. La primera solución es utilizar un bucle de la siguiente forma:
```php
for ($mul = 1; $mul <= 10; ++$mul) {
 $ris = 5 * $mul;
 echo "5 * $mul = $ris <br>";
}
```
Este construcción, similar a la utilizada en otros lenguajes de programación, comienza con la palabra clave for, seguida, entre paréntesis, por las instrucciones para definir el ciclo; a continuación, se incluyen entre llaves todas las instrucciones que deben ejecutarse en varias ocasiones.
Las tres instrucciones que se incluyen entre paréntesis y separadas por puntos y comas se tratan de esta manera:
1. la primera se ejecuta sólo una vez, al comienzo del ciclo, en nuestro caso $mul = 1.
2. la tercera se realiza al final de cada iteración del bucle, en nuestro ejemplo,
```php
++$mul;
```
3. la segunda debe ser una condición, en nuestro caso $mul <= 10, y es evaluada antes de cada repetición del bucle, y cuando es falsa la ejecución del ciclo se interrumpe, y el control pasa a las instrucciones que puedan seguir a las llaves.
Cuando es verdadera, se ejecutan las instrucciones incluidas entre las llaves. Por supuesto, es posible que esta condición sea falsa desde la primera vuelta: en este caso, las instrucciones entre las llaves no se ejecutarán ni siquiera una vez.
Es muy importante tener cuidado de no crear una situación en la que el ciclo nunca llega a un final (el llamado "bucle sin fin"): en este caso, de hecho, la secuencia de comandos se ejecutaría indefinidamente.
En muchos casos de programación clásica, un error de este tipo podría obligarnos a forzar el cierre del programa, o incluso para apagar el ordenador: en el caso de PHP esto generalmente no sucede, debido a que los scripts PHP tienen un límite de tiempo para la su ejecución, más allá del cual se detienen. Este límite es normalmente 30 segundos.

**[Regresar al índice](#indice)**

----------------------------------

**Ejercicio 5.16.** Vamos a crear una tabla de conversión de divisas, de euros a pesetas. En concreto, la tabla mostrará la conversión desde 1 hasta 10 euros. Recuerda que la equivalencia Euro pesetas era: 1€ = 166.386 pts.
```php
<html>
  <head>
    <title>Ejercicio</title>
  </head>
  <body>
    <?php
      $euro = 166.386;
      for ($i=1; $i<=10; $i++){
        print ("$i € = " . $i*$euro . " pts <br>\n");
      }
    ?>
  </body>
  </html>
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejercicio 5.17.** Bucles For. Vamos a crear un programa que construya una estructura en HTML para diseñar una tabla con 20 filas y 10 columnas. Para realizar esta tarea recurriremos a dos bucles for. Dentro de cada una de las celdas de la tabla puedes colocar cualquier letra, para que sea más visible.
```php
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>Ejercicio</title>
  </head>
  <body>
    <table>
      <?php for ($i=1; $i<=20; $i++) { ?>
      <tr>
        <?php for ($s=1; $s<=10; $s++) { ?>
          <td>O</td>
        <?php } ?>
      </tr>
      <?php }  ?>
    </table>
  </body>
</html>
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejemplo**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>
		<?php

			for ($f=1; $f<=100;$f++) {
				echo "$f - ";
			}

		?>
	</body>
</html>
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejercicio - listados de números**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>

		<?php

			for($f = 0; $f <= 200; $f+=2) {
				echo "$f - ";
			}

		?>

	</body>
</html>
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejercicio - Tabla de multiplicar**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>

		<?php

			$tabla = 7;

			echo "<p>Vamos a ver la tabla de multiplicar del $tabla</p>";

			for ($f = 1 ; $f<=10 ; $f++){
				echo "$f por $tabla es igual a ".$f*$tabla."<br/>";
			}

		?>

	</body>
</html>
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejercicio - Todas las tablas de multiplicar**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>

		<?php

		for ($tabla = 1; $tabla<=10 ; $tabla++){

			echo "<p>Vamos a ver la tabla de multiplicar del $tabla</p>";

			for ($f = 1 ; $f<=10 ; $f++){
				echo "$f por $tabla es igual a ".$f*$tabla."<br/>";
			}
		}

		?>

	</body>
</html>
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejercicio - Coloreando tablas**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>

		<table style="width:100%">

		<?php

			for ($f=1 ; $f<=10 ; $f++) {

				if ($f % 2 == 0) { echo'<tr style="background-color:#CCC;"><td>Esto es una fila de mi tabla</td></tr>'; }
				else { echo'<tr style="background-color:#FF0000;"><td>Esto es una fila de mi tabla</td></tr>'; }
			}

		?>

		</table>

	</body>
</html>
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejercicio 5.18.** Escribe un programa que imprima por pantalla los cuadrados (el número multiplicado por sí mismo) de los 30 primeros números naturales.
```php
<?php
for($i = 1; $i <= 30; $i++){
	echo "The square of ".$i." is ".($i*$i)."<br/>";
}
?>
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejercicio 5.19.** Modifica el ejercicio anterior para que muestre al lado de cada cuadrado si es un número par o impar.
```php
for($i = 1; $i <= 30; $i++){
	$cuadrado = $i*$i;
	echo "The square of ".$i." is ".$cuadrado;
	if($cuadrado%2 == 0){
		echo " and is even";
	}else{
		echo " and is odd";
	}
	echo "<br/>";
}
?>
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejercicio 5.20.** Crear un array llamado meses y que almacene el nombre de los doce meses del año. Recorrerlo con FOR para mostrar por pantalla los doce nombres.
```php
<?php
$months = array( "Enero", "Febrero", "Marzo", "Abril", "Mayo", "Junio", "Julio", "Agosto", "Septiembre", "Octubre", "Noviembre", "Diciembre" );
for($i = 0; $i < count($months); $i++ ){
	echo $months[$i]."<br/>";
}
?>
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejercicio 5.21.** Mostrar todos los números pares que hay entre el 1 y el 100.
```php
<?php
for($i = 1; $i <= 100; $i++){
	if($i%2 == 0){
		echo $i." is even<br/>";
	}
}
?>
```

**[Regresar al índice](#indice)**

----------------------------------

5.6.While y Do While
--------------------

El bucle while
-------------------

Veamos ahora otro tipo de ciclo, más simple en su construcción: el ciclo while. Puede considerarse como una especie de **if repetido varias veces**: de hecho, su sintaxis requiere la palabra clave while y entre paréntesis, la condición a ser evaluada, y dentro de las llaves, **el código debe ser repetido hasta que se cumpla esta condición**. Veamos con un ejemplo de cómo obtener el mismo resultado que el ejemplo anterior:
```php
$mul = 1;
while ($mul <= 10) {
 $ris = 5 * $mul;
 print("5 * $mul = $ris<br>");
 $mul++;
}
```
El ciclo while que en comparación con el `if`, **no proporciona instrucciones para inicializar y incrementar el contador**: tenemos que poner estas declaraciones en el flujo general del código, así que pusimos la inicialización antes del bucle, y el aumento en wl interior del bucle. En este caso la ejecución del bucle termina cuando la condición entre llaves ya no es verificada: una vez más es posible que el ciclo no se ejecute en caso en que la condición sea falsa desde el principio.

**[Regresar al índice](#indice)**

----------------------------------

**Ejemplo**
```php
<html lang="es">
	 <head>
		 <title>Ejercicio</title>
		 <meta charset = "UTF-8" />
	 </head>
	 <body>
   <?php
    $f = 1;
			 while ($f <= 100) {
				 echo "$f - ";
				 $f++;
			 }
   ?>
  </body>
</html>
```

**[Regresar al índice](#indice)**

----------------------------------

Do ... while
------------

Sin embargo tenemos otro método, similar a la instrucción while, con el que podemos estar seguros de que el código que se incluye en las llaves se ejecuta al menos una vez: es el do ... while
```php
$mul = 11;
// ponemos el valor inicial muy alto para intentar no conseguir
cumplir la condición
do {
 $ris = 5 * $mul;
 print("5 * $mul = $ris<br>");
 $mul++;
} while ($mul <= 10)
```
Con esta sintaxis, **el bucle while se mueve después de que el código que se ejecuta**, lo que indica que la evaluación de la condición se realiza después de la ejecución de código entre llaves. En el caso de nuestro ejemplo, hemos inicializado `$mul` con el valor `11`, para crear una situación en la que, con los ciclos antes vistos, que no conseguiríamos ninguna salida. A pesar de todo, con el uso del do ... whlie se ejecuta el código una vez a pesar de que la condición indicada en paréntesis es falsa desde el principio.

**[Regresar al índice](#indice)**

----------------------------------

**Ejercicio 5.22.** Vamos a crear tres programas distintos que realicen la misma tarea, para practicar un poco: uno con for, otro con while y el tercero con do/while. El programa en cuestión debe ofrecernos la tabla de multiplicar del 2.
```php
<!DOCTYPE html>
<html>
 <head>
  <meta charset="utf-8" />
  <title>Ejercicio</title>
 </head>
 <body>
 <?php
 echo "Tabla del 2 con el for";
 echo "<br>";
 for($f=2; $f<=20; $f=$f+2)
 {
 echo $f;
 echo "-";
 }
 ?>
 </body>
</html>
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejercicio 5.23.** Vamos a crear un programa que calcule los números primos entre 1 y 50 y los muestre por pantalla. Recuerda que un número primo es un número entero que sólo es divisible por 1 y por sí mismo.
```php
<!DOCTYPE html>
<html>
 <head>
 <meta charset="utf-8" />
 <title>Ejercicio</title>
 </head>
 <body>
 <?php
 for ($i=1; $i<=50; $i++) {
 $div = 2;
 $primo = true;
 do {
 if ($i % $div == 0)
 $primo = false;

 $div++;
 } while(($i >= $div*2) && ($primo == TRUE));

 if ($primo == TRUE )
 echo $i.' ';
 }
 ?>
 </body>
</html>
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejemplo**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>

		<?php

			$f = 1;

			do {
				echo "$f - ";
				$f++;
			} while ($f <= 100);

		?>


	</body>
</html>
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejercicio - Comparación While y Do While**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>

		<?php

			$f = 11;

			echo "ESTO ES LO QUE PASA CON WHILE...<br/>";
			while ($f <= 10) {
				echo "ME VES?";
				$f++;
			}

			echo "ESTO ES LO QUE PASA CON DO WHILE<BR/>";

			$d = 11;
			do {
				echo "ME VES?";
				$d++;
			} while ($d <= 10);

		?>


	</body>
</html>
```
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>

		<?php

			$tabla = 5;

			$f = 1;
			while ($f <= 10) {
				echo "$f x $tabla = ".$f*$tabla."<br/>";
				$f++;
			}

			$d = 1;
			do {
				echo "$d x $tabla = ".$d*$tabla."<br/>";
				$d++;
			} while ($d <= 10);

		?>


	</body>
</html>
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejercicio 5.24.** Diferenciar números pares e impares con While y Do While
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>
		<?php
			$numero = 15;
			$par = 0;
			$impar = 0;
			while ($numero > 0) {
				if($numero % 2 == 0) {
					 echo "el número $numero es PAR<BR/>";
					 $par++;
				} else {
					 echo "el número $numero es IMPAR<BR/>";
					 $impar++;
				}
			$numero--;
			}
			echo "<br/>";
			echo "Se han encontrado $par números pares y $impar números impares";
		?>
	</body>
</html>
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejercicio 5.25.** Escribe un programa que multiplique los 20 primeros números naturales. Utiliza el bucle While.
```php
<meta charset="utf-8" />
<?php
$number = 1;
$counter = 1;
$limit=4;
while($counter <= $limit){
	// $number = $number * $counter;
	$number *= $counter;
	echo $number."<br/>";
	$counter++;
}
echo "The result of multiplying the first ".$limit." numbers is: ".$number;
?>
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejercicio 5.26.** Escribe un programa que recoja un número pasado en un parámetro GET por la URL, y lo multiplique por todos los números naturales anteriores a él. Utiliza el bucle While.
```php
<meta charset="utf-8" />
<?php
if(isset($_GET["limit"]) && is_numeric($_GET["limit"])){
	$limit = $_GET["limit"];
}
$number = 1
$counter = 1;
while($counter <= $limit){
	// $number = $number * $counter;
	$number *= $counter;
	echo $number."<br/>";
	$counter++;
}
echo "The result of multiplying the first ".$limit." numbers is: ".$number;
?>
```

**[Regresar al índice](#indice)**

----------------------------------

5.7.Break y continue, Salir de un bucle
-----------------------------------

Hemos visto que PHP finaliza la ejecución de un ciclo cuando la condición a la que se le somete ya no se verifica. Sin embargo, tenemos otras herramientas para cambiar el comportamiento de nuestro script dentro del bucle: de hecho podemos decir a PHP que no termine lo que está haciendo y vaya a la siguiente iteración o que detenga permanentemente la ejecución del ciclo. Vamos a ver un ejemplo:
```php
for ($ind = 1; $ind < 500; $ind++) {
 if ($ind % 100 == 0) {
 break;
 } elseif ($ind % 25 == 0) {
 continue;
 }
 echo "valor: $ind <br>";
}
```
Este código configura un bucle que se ejecuta 500 veces, con valores para $ind que van de 1 a 500. Las instrucciones que hemos colocado dentro de él implican que $ind no se ejecuten hasta que $ind sea múltiplo de 25 (en la práctica, la declaración 'continue' significa que PHP debe saltar el 'print' y pasar directamente a la siguiente iteración, el aumento de la variable). El ciclo se interrumpe por completo cuando $ind llega al valor 100.

**[Regresar al índice](#indice)**

----------------------------------

**Ejemplo - Break**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>

		<?php

			$salida = 4;

			for ($f=0; $f <= 10; $f++) {

				echo "esta es la vuelta número $f<br/>";

				if ($f == $salida) {
					break;
				}

			}

			echo "Hemos Terminado!!";

		?>

	</body>
</html>
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejemplo - Continue**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>

		<?php

			$salida = 4;

			for ($f=0; $f <= 10; $f++) {

				if ($f == $salida) {
					continue;
				}

				echo "esta es la vuelta número $f<br/>";

			}

			echo "Hemos Terminado!!";

		?>

	</body>
</html>
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejemplo - Continue**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>

		<?php

			for ($f=0; $f<=10;$f++){

				if ($f % 2 == 1) {
					continue;
				}

				echo "Estamos en la vuelta $f <br/>";

			}

		?>

	</body>
</html>
```

**[Regresar al índice](#indice)**

----------------------------------
----------------------------------

6.ARRAYS
========

6.1.Array Escalar
-----------------

Anteriormente mencionamos el tipo de datos array con el siguiente ejemplo:
```PHP
$color = array ('blanco', 'negro', 'amarillo', 'verde', 'rojo');
```
Usando este tipo de definición, **asociamos a cada uno de los valores que hemos enumerado un índice numérico**, partiendo de 0 Así que, en este caso, 'blanco' asumen el índice 0, 'negro' el índice 1, y así sucesivamente hasta 'rojo', que es el índice de 4. Para hacer referencia a un solo elemento de la matriz indicaremos el nombre de la matriz seguido por el índice entre corchetes:
```PHP
echo $color[2]; // imprime 'amarillo"'
```
También hay un método para **agregar un valor a la matriz existente**; este método también se puede utilizar, como alternativa la anterior, para definir una matriz:
```PHP
$color[] = 'azul';
```
Este código crea un nuevo elemento en la matriz `$color`, que contará con el índice 5. Este comando puede ser "traducido" como "añadir un elemento en la parte inferior de la matriz $color". Como hemos dicho, esta sintaxis también es válida para definir una matriz nueva, como una alternativa a la utilizada antes: de hecho, si suponemos que el array $color aún no está definido, esta declaración le habría llevado al crear el elemento con el índice 0.
También **se puede especificar directamente el índice**, aunque sea de forma no consecutiva:
```PHP
$ color[3] = 'naranja';
$ color[7] = 'púrpura';
```
Después de esta instrucción, el elemento con el índice 3, que antes era 'verde', tendrá el valor "naranja". También tendremos un nuevo elemento, con índice 7, con el valor de 'púrpura'. Cabe señalar que, siguiendo estas instrucciones, nuestra matriz tiene un "agujero" porque el código 5 salta directamente al código 7. Si definimos un nuevo elemento con corchetes vacíos tendrá el índice 8. En la práctica, como ves, cuando se propone una instrucción de este tipo, PHP va en busca del elemento con el índice más alto, y aumenta en 1 para crear uno nuevo

**[Regresar al índice](#indice)**

----------------------------------

**Ejemplo - arrays**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>
		<?php
			$nombres = array ("juan", "maría", "pedro", "ana", "lola", "carmen");
			$nombres[10]= "antonio";
			echo $nombres [8];
		?>
	</body>
</html>
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejemplo - Arrays Escalares**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>
		<?php
			$nombre = "pedro";
			$cosas = array (1, 2, 3, "casa", $nombre);
			echo $cosas[4];
		?>
	</body>
</html>
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejemplo - Arrays Escalares**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>
		<?php
			$nombre = "pedro";
			$cosas = array (1, 2, 3, "casa", $nombre);
			$longitud = count($cosas);
			for ($f = 0 ; $f < $longitud ; $f++) {
				echo $cosas[$f].'<br/>';
			}
		?>
	</body>
</html>
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejemplo - Arrays Escalares**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>

		<?php

			$dias[] = "Lunes";

			echo $dias[0];

			$dias[] = "Martes";
			$dias[] = "Miércoles";
			$dias[] = "Jueves";

			echo $dias[2];


		?>

	</body>
</html>
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejercicio 6.1.** Vamos a definir un array que contenga los nombres de los días de la semana. Mostrar en pantalla el nombre del primer y último elemento.
```php
<!DOCTYPE html>
<html>
 	<head>
 		<meta charset="utf-8" />
 		<title>Ejercicio</title>
 	</head>
 	<body>
 		<?php
 			$diaSemana[]="Lunes";
 			$diaSemana[]="Martes";
 			$diaSemana[]="Miércoles";
 			$diaSemana[]="Jueves";
 			$diaSemana[]="Viernes";
 			$diaSemana[]="Sábado";
 			$diaSemana[]="Domingo";

 			echo "Primer elemento:".$diaSemana[0];
 			echo "<br>";
 			echo "Ultimo elemento:".$diaSemana[6];
 		?>
 	</body>
</html>
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejercicio 6.2.** Crearemos un array de 5 elementos, y asignaremos a cada uno de ellos un valor numérico. Calcularemos el promedio de cada uno de ellos y lo mostraremos en pantalla. Haremos aparecer en pantalla un mensaje que indique si el promedio es, por ejemplo, mayor o menor que 6.
```php
<!DOCTYPE html>
<html>
 	<head>
 		<meta charset="utf-8" />
 		<title>Ejercicio</title>
 	</head>
 	<body>
 		<?php
 			$numeros = array (5,7,3,6,4);
 			$promedio = ($numeros[0] + $numeros[1] + $numeros[2] + $numeros[3] + $numeros[4])/5;
 			echo 'El promedio es '.$promedio.'<br>';
 			($promedio > 6)? echo 'El promedio es mayor que 6': echo 'El promedio es menor que 6';
 			?>
 	</body>
</html>
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejercicio 6.3.** Comenzaremos creando un array compuesto por treinta números diferentes, que serán las ventas diarias de nuestra tienda. A partir de estos datos, calcularemos el promedio de ventas y lo mostraremos por pantalla. Puedes usar un bucle for para ayudarte en la suma.
```php
<!DOCTYPE html>
<html>
 	<head>
 		<meta charset="utf-8" />
 		<title>Ejercicio</title>
 	</head>
 	<body>
 		<?php
 			$ventas_dia = array (34,32,50,40,24,76,54,80,46,76,32,74,64,54,66,84,87,24,64,32,87,54,84,32,58,25,65,84,65,25);
			$total = 0;
 			for ($i=0; $i<=count($ventas_dia)-1; $i++) {
 				$total += $ventas_dia[$i];
 			}
			$promedio = $total / count($ventas_dia);
			echo 'El promedio de ventas es: '.$promedio;
 		?>
 	</body>
</html>
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejercicio 6.4.** Partiremos de un array compuesto por 10 elementos numéricos enteros. Deberemos construir un programa que encuentre el más alto de ellos y lo muestre por pantalla.
```php
<!DOCTYPE html>
<html>
 	<head>
 		<meta charset="utf-8" />
 		<title>Ejercicio</title>
 	</head>
 	<body>
 		<?php
 			$numeros = array (10, 2, 3, 14, 15, 1, 7, 9, 8, 11);
 			$paso = 0;
			while ($paso <= count($numeros)-1) {
				if ($paso == 0) {
 					$maximo = $numeros[0];
				}else {
					($numeros[$paso] > $maximo)? $maximo = $numeros[$paso];
				}
 				$paso++;
 			}
 			echo 'El maximo es: '.$maximo;
 			?>
 </body>
</html>
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejercicio 6.5.** Igual que en el ejercicio anterior, partiremos de un array compuesto por 10 elementos numéricos enteros. En este caso debemos construir un programa que localice el número más bajo.
```php
<!DOCTYPE html>
<html>
 	<head>
 		<meta charset="utf-8" />
 		<title>Ejercicio</title>
 	</head>
 	<body>
 		<?php
 			$numeros = array (10, 2, 3, 14, 15, 1, 7, 9, 8, 11);
 			$paso = 0;
			while ($paso <= count($numeros)-1) {
				if ($paso == 0){
 					$minimo = $numeros[0];
 				} else {
					($numeros[$paso] < $minimo) ? $minimo = $numeros[$paso];
 					$paso++;
				}
 			}
 			echo 'El minimo es: '.$minimo;
 		?>
 </body>
</html>
```

**[Regresar al índice](#indice)**

----------------------------------

6.2.Array Asociativo
--------------------

Sin embargo, el argumento array no se limita a esto: de hecho, los índices de los elementos **no son necesariamente numérico**. También pueden ser cadenas:
```php
$persona['nombre'] = 'Juan';
```
Con esta declaración, hemos definido una matriz llamada $persona , creando un elemento cuya clave es "nombre" y cuyo valor es 'Juan'. Hay que recordar que las claves numéricas y de cadena puedan coexistir en la misma matriz. Vemos un ejemplo sencillo, asumiendo la formación de un equipo de fútbol:
```php
$seleccion[1] ='Casillas';
$seleccion[2] ='Torres';
$seleccion[3] ='Iniesta';
$seleccion[4] ='Costa';
$seleccion[5] ='Ramos';
$seleccion[6] ='Piqué';
$seleccion[7] ='Fábregas';
$seleccion[8] ='Silva';
$seleccion[9] ='Mata';
$seleccion[10] ='Alba';
$seleccion[11] ='El Haddani';
$seleccion['res'] ='Valdes';
```
En este caso hemos creado una matriz con doce elementos, de los cuales once son numéricos, y uno tiene una **clave asociativa**. Si más adelante desea agregar un elemento usando corchetes vacíos, el nuevo elemento se llevará el índice de 12. Podríamos crear la misma matriz utilizando la sentencia declaración de array, así:
```php
$seleccion = array(1
=> 'Casillas"', 'Torres"', 'Iniesta"', 'Costa"', 'Ramos"', 'Piq
ué"', 'Fábregas"', 'Silva"', 'Mata"', 'Alba"', 'El
Haddani"', 'res"' => 'Valdes"');
```
En primer lugar, hemos creado el primer elemento, asignando explícitamente el índice 1.
Como podemos ver, la manera de hacer esto es especificar el índice, seguido del símbolo => y el valor del elemento. Si no hubiésemos indicado el índice como 1, PHP le asignaría al primer elemento el índice 0. Para los siguientes elementos, nos limitamos a enumerar los valores y PHP crea un incremento de 1 a partir del existente más alto. Así 'Torres' toma el índice 2 'Iniesta' el 3 y así, sucesivamente. Al llegar al último elemento, ya que queremos asignar una clave asociativa, estamos obligados a indicarla explícitamente.
Cabe señalar que cuando se utilizaron las llaves asociativas hemos de hacer uso de las comillas: es necesario para mantener la "limpieza" del código, ya que si no usáramos comillas (como se ve a menudo a hacer), PHP generaría de error, aunque el programa funcionase igualmente (ya que el valor se convertiría automáticamente en una cadena).
Vamos a ver algunos ejemplos de la creación e impresión de valores en una matriz:
```php
$persona['nombre'] = 'Juan"'; // correcto
$persona[apellido] = 'Lopez"'; // funciona, pero genera un
error
echo $persona['apellido']; // muestra "Lopez": Correcto
echo "Hola $persona[nombre]";
// imprime "Hola Juan" (no se usan comillas dentro de comillas)*/
echo "Hola $persona['nombre']";
// NO FUNCIONA Y GENERA UN ERROR
echo "Hola {$persona['nombre']}";
// correcto: para el uso de comillas simples debemos rodearlo
todo con llaves
echo "Hola ". $persona['nombre'];
// correcto: podemos usar el punto para concatenar
```
Ahora que hemos visto la manera de crear y asignar valores a una matriz, utilizando un índice numérico o uno asociativo, estableciendo explícitamente los índices o dejando que PHP lo haga, vamos a ver cómo podemos crear estructuras de datos complejas, a través de matrices de varias dimensiones.

**[Regresar al índice](#indice)**

----------------------------------

**Ejemplo - Arrays Asociativos**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>
		<?php
			$coche["color"] = "rojo";
			$coche["tamaño"] = "grande";
			$coche["marca"] = "seat";
			$coche["precio"] = 10000;
			$texto = "El vehículo de la marca ".$coche["marca"]." es de color ".$coche["color"];
			$texto .= " tiene un precio de ".$coche["precio"];
			$texto .= " y tiene un tamaño ".$coche["tamaño"];
			echo $texto;
		?>
	</body>
</html>
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejemplo - Arrays Asociativos**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>
		<?php
			$menu = array (
				"primer_plato" => "ensalada",
				"segundo_plato" => "solomillo",
				"postre" => "manzana"
			);
			echo $menu["segundo_plato"];
		?>
	</body>
</html>
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejemplo - Arrays Asociativos**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>
		<?php
			$notas = array (
				"matemáticas" => 6,
				"historia" => 4,
				"inglés" => 8,
				"filosofía" => 5
			);
			$promedio = ($notas["matemáticas"]+$notas["historia"]+$notas["inglés"]+$notas["filosofía"])/4;
			echo $promedio;
		?>
	</body>
</html>
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejemplo - Arrays Asociativos**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>
		<?php
			$clave['ana'] = "abc";
			$clave['pedro'] = "sdafasdf34";
			$clave['laura'] = "$/&34sdfase";
			$clave['pedro'] = "dsfsd";
			echo "La contraseña de Laura es ".$clave['laura'];
		?>
	</body>
</html>
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejemplo - Arrays Asociativos**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>
		<?php
			$capitales = array ("españa" => "madrid", "francia" => "paris", "portugal" => "lisboa", "alemania" => "berlín");
			echo $capitales["francia"];
		?>
	</body>
</html>
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejercicio 6.6.** Vamos a crear un array asociativo en el que se guarden las contraseñas de cinco usuarios de un sistema. A cada uno de los usuarios se accederá por su nombre. Deberemos hacer que se muestre en pantalla la contraseña de uno de esos usuarios.
```php
<!DOCTYPE html>
<html>
 	<head>
 		<meta charset="utf-8" />
 		<title>Ejercicio</title>
 	</head>
 	<body>
 		<?php
 			$clave['ana']="abc123";
 			$clave['luis']="z67yui";
 			$clave['carlos']="sdf3sdf";
 			$clave['laura']="dsf3k32";
 			$clave['pedro']="axldds23";
			echo "La clave de luis es:".$clave['luis'];
 		?>
 	</body>
</html>
```

**[Regresar al índice](#indice)**

----------------------------------

6.3.Bidimensional y Multidimensional
------------------------------------

Una **matriz multi-dimensional** es una matriz en la que **uno o más elementos de las matrices es a su vez otra matriz**. Suponga que desea recopilar datos personales de más de una persona, y que por cada persona registrará su nombre, fecha de nacimiento y ciudad de residencia.
```php
$persona = array(
		array(
			'nombre' => 'Juan',
			'apellido'=> 'Lopez',
			'fecha_nacimiento' => '1973/06/15',
			'residencia'=> 'Madrid'),
		array(
			'nombre' => 'Maria',
			'apellido'=> 'Flores',
			'fecha_nacimiento' => '1968/04/05',
			'residencia'=> 'Sevilla'),
		array(
			'nombre' => 'Ana',
			'apellido'=> 'Garrido',
			'fecha_nacimiento' => '1964/11/26',
			'residencia'=> 'Barcelona')
		);
print $persona[0]['apellido']; // imprime 'Lopez"'
print $persona[1]['residencia']; // imprime 'Sevilla"'
print $persona[2]['nombre']; // imprime 'Ana"'
```
Con este código, hemos definido un array **formado a su vez por tres arrays**, numerados separados por comas, cada uno de ellos ha recibido el índice numérico a partir de 0.
Dentro de cada serie, en cambio, todos los índices han sido referidos como asociativo. Tenga en cuenta que, aunque en este caso cada una de las tres matrices tenía la misma estructura 'interna' es posible dar a cada conjunto una estructura autónoma. Tomemos otro ejemplo:
```php
$persona= array(
		1 => 	array(
			'nombre' => 'Juan Lopez',
			'residencia'=> 'Madrid',
			'trabajo' => 'funcionario'),
		2 => array(
			'nombre"'=> 'Maria Flores',
			'fecha_nacimiento' => "'1968/04/05',
			'residencia'=> 'Sevilla'),
		'total_elementos' => 2);
print $persona[1]['residencia']; // imprime 'Sevilla'
print $persona['total_elementos']; // imprime '2'
```
En este caso, nuestra gama está formada por dos conjuntos, a los que hemos asignado los índices 1 y 2, y por un tercer elemento, que no es una matriz sino una variable entera, con la clave asociativa 'total_elementos'. En los dos conjuntos los dos primeros elementos tienen una estructura diferente: mientras que el primero está formado por 'nombre', 'residencia' y 'trabajo', el segundo está formado por 'nombre', 'fecha_nacimiento' y 'residencia'.

**[Regresar al índice](#indice)**

----------------------------------

**Ejemplo - Arrays Bidimensionales y Multidimensionales**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>
		<?php
			$animal = array (
				array ("perro", "ladra"),
				array ("abeja", "zumba"),
				array ("burro", "rebuzna"),
				array ("buho", "ulular"),
				array ("ballena", "canta"),
				array ("cabra", "bala")
			);
			echo $animal [4][0];
			echo "<br/>";
			echo $animal [4][1];
		?>
	</body>
</html>
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejemplo - Arrays Bidimensionales y Multidimensionales**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>
		<?php
			$liga = array (
				array ("A Coruña", "Deportivo", 15),
				array ("Zaragoza", "Zaragoza", 21),
				array ("Sevilla", "Betis", 15),
				array ("Sevilla", "Sevilla", 15),
				array ("Valencia", "Valencia", 10)
			);
			echo $liga[0][1]." - ".$liga[0][2]."<br/>";
			echo $liga[1][1]." - ".$liga[1][2]."<br/>";
			echo $liga[2][1]." - ".$liga[2][2]."<br/>";
			echo $liga[3][1]." - ".$liga[3][2]."<br/>";
			echo $liga[4][1]." - ".$liga[4][2]."<br/>";
		?>
	</body>
</html>
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejemplo - Arrays Bidimensionales y Multidimensionales**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>
		<?php
			$liga = array (
				array ("A Coruña", "Deportivo", 15),
				array ("Zaragoza", "Zaragoza", 21),
				array ("Sevilla", "Betis", 15),
				array ("Sevilla", "Sevilla", 15),
				array ("Valencia", "Valencia", 10)
			);
			for ($f = 0; $f < 5; $f++) {
				echo $liga[$f][1]." - ".$liga[$f][2]."<br/>";
			}
		?>
	</body>
</html>
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejemplo - Arrays Bidimensionales y Multidimensionales**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>
		<?php
			$libros = array (
				'comic' => array (
					'titulo' => 'superman',
					'autor' => 'Jerry Siegel and Joe Shuster',
					'fecha' => '1938'
				),
				'sfi' => array (
					'titulo' => 'dune',
					'autor' => 'frank Herbert',
					'fecha' => '1965'
				),
				'fantasia' => array (
					'titulo' => 'El Hobbit',
					'autor' => 'J.R.R Tolkien',
					'fecha' => '1937'
				),
				'terror' => array (
					'titulo' => 'Carrie',
					'autor' => ' Stephen King',
					'fecha' => '1974'
				)
			);
				echo $libros ["terror"]["fecha"];
		?>
	</body>
</html>
```
6.4.Bucle Foreach
-----------------
El constructor foreach proporciona un modo sencillo de iterar sobre arrays. foreach funciona sólo sobre arrays y objetos, y emitirá un error al intentar usarlo con una variable de un tipo diferente de datos o una variable no inicializada. Existen dos sintaxis:
```PHP
foreach (expresión_array as $valor)
    sentencias
foreach (expresión_array as $clave => $valor)
    sentencias
```
La primera forma recorre el array dado por expresión_array. En cada iteración, el valor del elemento actual se asigna a $valor y el puntero interno del array avanza una posición (así en la próxima iteración se estará observando el siguiente elemento).
La segunda forma además asigna la clave del elemento actual a la variable $clave en cada iteración.

**[Regresar al índice](#indice)**

----------------------------------

**Ejemplo - Bucle Foreach**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>
		<?php
			$semana = array ("lunes", "martes", "miercoles", "jueves", "viernes", "sabado", "domingo");
			foreach ($semana as $dia) {
				echo "$dia, ";
			}
		?>
	</body>
</html>
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejemplo - Bucle Foreach**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>
		<?php
			$capital = array ("cantabria" => "santander", "euskadi" => "vitoria", "aragon" => "zaragoza", "navarra" => "pamplona");
			foreach ($capital as $clave => $ciudad) {
				echo "$ciudad es la capital de $clave.<br/>";
			}
		?>
	</body>
</html>
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejercicio 6.7.** Recorrer un array de notas y calcular su promedio con **Foreach**
| OPCIÓN A |
|----------|

```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>
		<?php
			$total = 0;
			$notas = array (3, 6, 5, 8, 4, 2, 6, 3, 9, 2, 8, 7);
			foreach ($notas as $n) {
				$total += $n;
			}
			$promedio = $total / count($notas);
			echo $promedio;
		?>
	</body>
</html>
```
| OPCIÓN B |
|----------|
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>

		<?php

			$notas = array (3, 6, 5, 8, 4, 2, 6, 3, 9, 2, 8, 7);

			$promedio = array_sum($notas)/count($notas);
			echo $promedio;

		?>

	</body>
</html>
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejercicio 6.8.**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>
		<?php
 			 $luis = array ("Luis García", "111111111", "Trabajo");
			 $paco = array ("Paco Martínez", "22222222", "Amigo");
			 $sofia = array ("Sofía López", "3333333", "Cliente");
			 $pilar = array ("Pilar Martínez", "45454545", "Familia");
			 $agenda = array ($luis, $paco, $sofia, $pilar);
			 echo '<table border="1" width="60%" cellspacing="0">';
			foreach ($agenda as $fila) {
				echo "<tr>";
					foreach ($fila as $celda) {
						echo "<td> $celda </td>";
					}
				echo "</tr>";
			}
			echo '</table>';
 		?>
	</body>
</html>
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejercicio 6.9.** Crear un array llamado meses y que almacene el nombre de los doce meses del año. Recorrerlo con FOREACH para mostrar por pantalla los doce nombres.
```php
<?php
$months = array( "Enero", "Febrero", "Marzo", "Abril", "Mayo", "Junio", "Julio", "Agosto", "Septiembre", "Octubre", "Noviembre", "Diciembre" );
foreach ($months as $month) {
	echo $month."<br/>";
}
?>
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejercicio 6.10.** Hacer un programa que tenga un array de 5 números enteros y hacer lo siguiente con él:
1. Recorrerlo y mostrarlo.
2. Ordenarlo y mostrarlo.
3. Mostrará su longitud.
4. Buscar en el vector.
```php
<meta charset="utf-8" />
<?php
$numeros = array(30,20,40,50,10,5);
echo "<h2>Recorrer y mostrar:</h2>";
foreach ($numeros as $numero) {
	echo $numero."<br/>";
}
echo "<h2>Ordenar y mostrar</h2>";
//ordenar
sort($numeros);
foreach ($numeros as $numero) {
	echo $numero."<br/>";
}
echo "<h2>Longitud del array o número de elementos: ".sizeof($numeros)."</h2>";
echo "<h2>Buscar en el array:</h2>";
if(!array_search(11, $numeros)){
	echo "<p>El número no existe en el array</p>";
}else{
	echo "<p>El número SI EXISTE en el array</p>";
}
?>
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejercicio 6.11.** Escribe un programa que añada valores a un array mientras que su longitud sea menor a 100 y después que se muestre la información del array por pantalla.
```php
<?php
$array=[1,3,"hola",4];
echo "El array incluye inicialmente: ".var_dump($array)."</br>";
$length=count($array);
echo $length;
for ($length;$length<=(100-1);$length++){
	if($length%2==0){
   		array_push($array,"valor número {$length}");
	}else{
   		$array[$length]="valor número {$length}";
	}
}
var_dump($array);
?>
```

**[Regresar al índice](#indice)**

----------------------------------

----------------------------------

7.FUNCIONES
===========

Aunque la versión 5 de PHP trajo un gran apoyo a la programación orientada a objetos (que veremos más adelante) las funciones siguen siendo la parte fundamental del lenguaje de programación PHP y muchos desarrolladores todavía siguen esta filosofía de programación.
Una función es un conjunto de instrucciones que tienen un propósito, llevar a cabo ciertas operaciones. La función nos evitar tener que volver a escribir cualquier código cada vez que necesitamos para llevar a cabo estas operaciones: sólo necesitaremos llamar a la función apropiada, y proporcionarle los parámetros que necesita para su ejecución.
Las funciones pueden estar integradas en el lenguaje o ser definidas por el usuario.
En ambos casos, el modo de recuperación es el mismo.
La sintaxis básica con la que se llama a una función es muy simple:
```php
funcion();
```
Simplemente debemos indicar el nombre de la función, seguido de paréntesis. Estos paréntesis deben contener los parámetros que pasamos a la función, y deben aparecer incluso aunque no haya parámetros, en cuyo caso quedan vacíos como vimos en el ejemplo. En un caso en el que la función devuelva un valor, podemos indicar la variable en la que lo almacenaremos:
```php
$valor = funcion();
```
De esta manera, la variable $valor recibirá el resultado de la función. Las funciones también se pueden ser usadas dentro de expresiones: en este caso, el valor devuelto será utilizado durante la evaluación de la expresión:
```php
$ejemplo = (10 * funcion()) - otro_numero();
```
Hemos dicho que las funciones pueden ser integradas en el lenguaje de programación, o definidas por el usuario: En esta lección vamos a repasar algunas de las funciones más utilizadas incorporadas a PHP, pero ten en cuenta que estas funciones son numerosas, dirigidas a los más variados fines, y por lo tanto que no vamos a ser demasiados exhaustivos. Consulta el manual en línea de PHP para un estudio más completo de las características y casos especiales en www.php.net

**[Regresar al índice](#indice)**

----------------------------------

7.1.Funciones que trabajan con Variables
----------------------------------------
Vamos a empezar con las principales funciones que operan sobre las variables en
general:

**empty (valor)** comprueba si la variable que pasamos está vacía o no. Por "vacío" entendemos que la variable puede contener una cadena vacía o un valor numérico de 0, pero también puede ser definido como NULL (que indica que variable no está definida, y en este caso, no genera aviso de error). Devuelve un valor booleano (true o false).
```php
<?php
  $a = false;
	$empty=(empty($a)) ? "Esta variable está VACIA, cumplimentala correctamente" : "La variable tiene el siguiente contenido: $a";
	echo $empty;
?>
```
**isset (valor)** se produce si se define la variable. Una variable está indefinida cuando no se ha inicializado o se ha establecido en el valor NULL. Devuelve un valor booleano.
```php
<?php
	$a = 34343;
	$isset=(isset($a)) ? "La variable existe y tiene buena pinta" : "La variable NO EXISTE";
	echo $isset;
?>
```
**is_null (valor)** comprueba si la variable es igual a NULL, pero arroja un error si se ejecuta en una variable no definida. Devuelve un valor booleano.
```php
<?php
  if (isset($_POST["enviar"])){
			echo "Formulario Enviado!!";
	} else {
			echo '<form action="formulario.php" method="post">';
			echo 'Dime tu nombre: <input type="text" name="nombre">';
			echo '<input type="submit" name="enviar" value="Ya!">';
			echo '</form>';
	}
?>
```
**is_int (valor), is_integer (valor), is_long (valor)** comprueba si la variable es de tipo entero. Las tres funciones son equivalentes. Devuelve un valor booleano.
```php
<?php
	$a = 5;
	$is_int=(!is_int($a)) ? "$a NO ES número entero" : "$a es un número entero";
	echo $is_int;
?>
```
```php
<?php
	$a = array (3, 5, 8, 4.6, 2.3, 5, 7, 3.2);
	foreach ( $a as $numero ) {
		$is_int=(is_int($numero)) ? "$numero ES número entero<br/>" :  "$numero NO ES un número entero<br/>";
	  	echo $is_int;
  	}
?>
```
**is_float (valor), is_double (valor), is_real (valor)** comprueba si la variable es numérica double (o float). Las tres funciones son equivalentes. Devuelve un valor booleano.

**is_string (valor)** comprueba si la variable es una cadena. Devuelve un valor booleano.
```php
<?php
	$cadena = array (
			false,
			'casa',
			4,
			5.6,
			'4',
			'5.6'
		);
	foreach ($cadena as $a) {
		$is_string=(is_string($a)) ? "$a es una cadena</br>" : "$a NO ES UNA CADENA<br/>";
		echo  $is_string;
	}
?>
```
**is_array (valor)** comprueba si la variable es una matriz. Devuelve un valor booleano.
```php
<?php
	$a = 478;
	echo is_array($a) ? "Es un array" : "No es un array" ;
?>
```
**is_numeric (valor)** se produce si la variable contiene un valor numérico. Es muy importante distinción entre esta función y is_int() o is_float() , ya que esta última, en el caso de una cadena que contenga valores numéricos, devolverá false, mientras is_numeric() devolverá true. Devuelve un valor booleano.
```php
<?php
	$a = array (3,5);
	$is_numeric=(is_numeric($a)) ? "$a es un número" : "$a NO ES UN NUMERO";
	echo $is_numeric;
?>
```
**gettype (valor)** comprueba qué tipo de datos hemos pasado. Devuelve una cadena que representa el tipo de datos, por ejemplo: boolean, integer, double, string, array. De todas formas, es mejor no basarnos en estos valores para deducir el tipo de datos, ya que en las futuras versiones de PHP algunas de estas cadenas se podría cambiar. Mejor usar las funciones antes vistas.

**print_r (valor)** imprimir (directamente en el navegador) información sobre el contenido de la variable que pasamos. Es útil en la depuración, nuestros programas provocan comportamientos 'extraña' y queremos comprobar el contenido de ciertos datos. Si el valor pasado es un array, la función muestra las claves y sus valores. Devuelve un valor booleano.

**unset (valor)** destruye las variables especificadas. En realidad no es una función, sino una construcción del lenguaje. Después de unset(), la ejecución de empty() o is_null() en la misma variable devolverá true, mientras que isset() devolverá falso. No devuelve valores.

Vamos a ver algunos ejemplos para aclarar el uso de estas funciones:
```php
$b = empty($a); // $a aún no está definida, entonces $b es verdadera
$a = 5;
$b = isset($a); // verdadero
$b = is_float($a); // falso: $a es un número entero
$b = is_string($a); // falso
$a = '5';
$b = is_int($a); // falso: $a es ahora una cadena
$b = is_string($a); // verdadero
$b = is_numeric($a); // verdadero: la cadena tiene contenido numérico
$c = gettype($b); // $c toma el valor 'booleano'
unset($a); // eliminamos la variable $ a,
$b = is_null($a); // cierto, pero genera error
```
En estos ejemplos siempre hemos asignado a la variable $b valores booleanos devueltos por las funciones. En la práctica, es más frecuente que estos valores no se almacenen en variables, si no que se utilizan directamente como condiciones, por ejemplo, de instrucciones de tipo if.
```php
(empty($a)) ?  print ('$a está vacío o incompleto!') :  print ('$a contiene un valor');
(is_numeric($a)) ? print ('$a contiene un valor numérico') : print ('$a no contiene un valor numérico');
```

**[Regresar al índice](#indice)**

----------------------------------

7.2.Funciones que trabajan con cadenas
--------------------------------------
Examinemos ahora algunas funciones que operan sobre cadenas (la indicación de un parámetro entre corchetes indica que este parámetro es opcional, siendo no necesario cuando se invoca la función):
**strlen (cadena)** Comprueba la longitud de la cadena, es decir, el número de caracteres que la forman. Devuelve un entero.
```php
<?php
	$cadena = "";
	echo strlen($cadena); //imprime '0'
?>
```
```php
<?php
	$cadena = "Esto es una cadena de caracteres";
	$length=strlen($cadena);
	$message=($length>15)?"La cadena es demasiado larga, tiene ".$length:"La cadena tiene la longitud correcta";
	echo $message;
?>
```
**trim (cadena)** Eliminar espacios al principio y al final de la cadena. Devuelve la cadena modificada.
```php
<?php
	$a = "---Juan Martínez///";
	echo $a.'<br/>';
	echo trim($a,"-/");
?>
```
**ltrim (cadena)** Eliminar espacios al principio de la cadena. Devuelve la cadena modificada.
**rtrim (cadena)** Eliminar espacios al final de la cadena. Devuelve la cadena modificada.
**substr (cadena, entero [entero])** Devuelve una porción de la cadena, de acuerdo con el segundo parámetro (que indica el comienzo de la parte a ser extraído), y un posible tercer parámetro, que indica cuántos caracteres deben ser extraídos. Si no se especifica el tercer parámetro, devuelve el resto de la cadena a partir del carácter especificado.
Los caracteres se cuentan desde cero, de forma que si se llama a la función `substr(cadena, 4)` devolverá todos los caracteres a partir de la quinta. También podemos indicar un número negativo como el primer carácter: en este caso, el carácter inicial de la porción de la cadena devuelta se contará a partir de la parte final.
```php
<?php
	$a = "abcdef";
	echo substr ($a,-4,-4);
?>
```
Por ejemplo, con `substr (cadena, -5, 3)` se obtendrán tres caracteres a partir de quintultimo (tenga en cuenta que, en este caso, el recuento no empieza de cero, sino a partir de 1: es decir, -1 indica el último carácter, -2 el penúltimo y así sucesivamente).
Por último, si se especifica un número negativo como tercer parámetro, el parámetro ya no se utiliza como el número de caracteres devuelto, sino como el número de caracteres a mostrar de la parte final. Ejemplo: `substr (cadena, 3, -2)` devuelve los caracteres de la cuarta a la tercera posición.
**str_replace (cadena, cadena, cadena)** Hace una sustitución de la primera cadena con la segunda dentro de la tercera. Por ejemplo: `str_replace ('p', 't', 'plato')` sustituye a 'p' con la 't' en 'plato', y devuelve 'plapo'.
También hay una función `str_ireplace()` , que es equivalente, pero que busca la primera cadena en la tercera, sin tener en cuenta la diferencia entre mayúsculas y minúsculas.
```php
<?php
	$a = "Esta cadena es mi cadena preferida, te gusta mi cadena?";
	echo str_replace("cadena", "CADENA", $a, $contador);
	echo '<br> Has reemplazado '.$contador.' veces';
?>
```
```php
<?php
	$a = "Me gusta mucho la fruta";
	echo str_replace ("fruta","pizza",$a);
?>
```
**strpos (cadena, cadena)** Busca la posición de la segunda cadena dentro de la primera. Por ejemplo:
`strpos('Lorenzo', 're')` devuelve 2, lo que indica la tercera posición. Devuelve un entero que representa la posición desde 0 de la cadena de búsqueda. Si la segunda cadena no está presente en la primera, devuelve el valor booleano FALSE.
La función `stripos()` hace la misma búsqueda sin tener en cuenta la diferencia entre mayúsculas y minúsculas.
**strstr (cadena, cadena)** Buscar la segunda cadena en la primera, y devuelve la primera cadena a partir del punto donde se encontró el segundo. `strstr ('Lorenzo', 're')` devuelve 'renzo'. Como vemos, devuelve una cadena que si la búsqueda es exitosa, y de lo contrario el valor FALSE. La función stristr() funciona de la misma manera, pero no tiene en cuenta la diferencia entre
mayúsculas y minúsculas.
**strtolower (cadena)** Convierte todos los caracteres alfabéticos en las letras minúsculas correspondientes. Devuelve la cadena modificada.
```php
<?php
	$a = "hola. ¿Cómo estás?";
	echo strtolower($a).'<br/>';
?>
```
**strtoupper (cadena)** Convierte todos los caracteres alfabéticos en las letras mayúsculas correspondientes. Devuelve la cadena modificada.
```php
<?php
	$a = "hola. ¿Cómo estás?";
	echo strtoupper($a).'<br/>';
?>
```
**ucfirst (cadena)** Transformar en mayúscula la primera letra de la cadena. Devuelve la cadena modificada.
```php
<?php
	$a = "hola. ¿Cómo estás?";
	echo ucfirst($a).'<br/>';
?>
```
**ucwords (cadena)** Transformar en mayúscula la primera letra de cada palabra de la cadena. Devuelve la cadena modificada.
```php
<?php
	$a = "hola. ¿Cómo estás?";
	echo ucwords($a).'<br/>';
?>
```
**explode (cadena, cadena [, entero])** Transformar la segunda cadena en una matriz, usando el primero para separar los
elementos. El tercer parámetro puede utilizarse para indicar el número máximo de elementos que la matriz puede contener (si la división de la cadena da lugar a un número más alto, la parte final de la cadena será totalmente contenida en el último elemento).
Por ejemplo: `explode(' ', 'hola Juan')` devuelve un array de dos elementos: primero es 'hola' y el segundo 'Juan'. Como vemos, devuelve una matriz.

**[Regresar al índice](#indice)**

----------------------------------

**Ejemplo - Función Explode**
```php
<?php
	$a = "Ana García López";
	$nombre = explode (" ",$a);
	echo $nombre[1];
?>
```
**Ejemplo - Función Explode**
```php
<?php
	$a = "C/ Cosa 25, 08015 Barcelona";
	$direccion = explode ("," , $a);
	echo $direccion[0];
?>
```


**[Regresar al índice](#indice)**

----------------------------------

**Ejercicio 7.1.** Partiremos de la siguiente cadena de caracteres: `$texto = "uno-dos-tres-cuatro-cinco";`
Crear una página que, a partir de esta cadena, muestre una lista con los elementos de la misma que resultan de partirla usando como carácter separador el guion '-' de la siguiente forma:
* uno
* dos
* tres
* cuatro
* cinco
Te sugerimos que para realizar esta práctica recurras a las funciones explode y count.
```php
<html>
 	<head>
 		<title>Ejercicio</title>
 	</head>
 	<body>
		<?php
			$texto = "uno-dos-tres-cuatro-cinco";
 			$lineas = explode ("-", $texto);
			$n_lineas = count ($lineas);
			print ("<ul>");
			for ($i=0; $i<$n_lineas; $i++){
 				print (" <li>$lineas[$i]</li>");
			}
  			print ("</ul>");
 		?>
	</body>
</html>
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejercicio 7.2.** Recibe una cadena de texto y conviertela en los distintos formatos de salida (UpperCase, LowerCase, CamelCase, TitleCase)
```php
<?php
$string= '¿cómo están ustedes?';
echo mb_strtolower($string)."</br>"; //¿cómo están ustedes?
echo mb_strtoupper($string)."</br>"; //¿CÓMO ESTÁN USTEDES?
echo strtolower($string)."</br>";    //¿cómo están ustedes?
echo strtoupper($string)."</br>";    //¿CóMO ESTáN USTEDES?
echo ucfirst($string)."</br>";       //¿cómo están ustedes?
echo ucwords($string)."</br>";       //¿cómo Están Ustedes?
?>
```

**[Regresar al índice](#indice)**

----------------------------------

**En general**
Tenemos que hacer una puntualización sobre todas estas funciones, en particular las que tienen por objeto modificar una cadena: la cadena modificada es el resultado de la función, y tendremos que asignarla a una variable específica. Las variables originalmente pasadas "‹"‹a la función no han cambiado. Vamos a ver algunos ejemplos del uso de estas funciones:
```php
$a = 'AYER FUE DOMINGO';
$b = strtolower($a); // $b se convierte en 'ayer fue domingo' , pero $a permanece como 'AYER FUE DOMINGO'
strlen('abcd'); // devuelve 4
trim(' Saludos a todos '); // devuelve 'Saludos a todos'
substr('Saludos a todos', 4); // 'dos a todos' (inicia en el quinto)
substr('Saludos a todos', 4, 6); // 'dos a '(6 caracteres a partir del quinto)
substr('Saludos a todos', -4); // 'odos' (últimos cuatro)
substr('Saludos a todos', -4, 2); // ' t' (2 caracteres a partir del cuarto por el final)
substr('Saludos a todos', 4, -2); // 'dos a to' (del quinto al tercero por el final)
str_replace('Saludos', 'Adios', 'Saludos a todos'); // 'Adios a todos'
str_replace('dem', 'x', 'Demasiado nunca es demasiado'); // 'Demasiado nunca es xasiado'
str_ireplace('dem', 'x', 'Demasiado nunca es demasiado'); // 'xasiado nunca es xasiado'
strstr('Saludos a todos', 'l'); // 'ludos a todos' (a partir de la primera 'l')
strtoupper('Saludos a todos'); // 'SALUDOS A TODOS'
ucfirst('Saludos a todos'); // 'Saludos a todos';
ucwords('Saludos a todos'); // 'Saludos A Todos';
/ * Divide la cadena en una matriz, que separa un elemento
* cada vez que encuentre una coma, tendremos una matriz
* Tres elementos: ('Pedro', 'Mario', 'Juan') * /
explode(',','Pedro,Mario,Juan');
/ * En este caso, la matriz puede contener un máximo de dos elementos,
* por lo cual el primer elemento será 'Pedro' y en el segundo la
* el resto de la cadena: 'Mario, Juan'* /
explode(',','Pedro,Mario,Juan',2);
```

**[Regresar al índice](#indice)**

----------------------------------

7.3.Funciones que trabajan con Arrays
-------------------------------------
Vamos en este tema a repasar algunas de las funciones que operan sobre matrices más importantes:
**count (array)** Cuenta el número de elementos de la matriz. Devuelve un entero.
```php
<?php
	$a[10] = 5;
	$a[21] = 9;
	$a[32] = 1;
	$a[43] = 5;
	echo count($a);
?>
```
```php
<?php
	$a[0][0][0] = 5;
	$a[0][1][0] = 5;
	$a[0][2][0] = 5;
	$a[0][3][0] = 5;
	$a[0][3][1] = 5;
	$a[0][3][2] = 5;
	$a[0][3][3] = 5;
	$a[1][0][0] = 5;
	$a[1][1][0] = 5;
	$a[1][1][1] = 5;
	echo count($a,1);
?>
```
```php
<?php
	$menu = array (
		'PrimerP' => array ('sopa', 'ensalada', 'pasta'),
		'SegundoP' => array ('carne', 'pescado', 'paella')
		);
	$a = count($menu['PrimerP']);
	$b = count($menu['SegundoP']);
	$total = $a + $b;
	echo $total;
?>
```
**array_reverse (array, [boolean])** Invierte el orden de los elementos en la matriz. Si queremos mantener las claves de la matriz introducida, tenemos que pasar el segundo parámetro con un valor de TRUE. Devuelve la matriz entrada con los elementos invertidos.
**sort (array)** Ordena los elementos de la matriz. Debemos tener cuidado, porque esta función, a diferencia de muchos otras, cambia directamente la matriz que se pasa como entrada, de manera que se perderá en su composición original.
Los valores se disponen en orden ascendente de acuerdo a los criterios que vimos cuando hablamos de operadores aritméticos, y los índices se pierden: después de la ordenación, la matriz tendrán índices numéricos a partir 0 de acuerdo con el nuevo orden. Esta función no devuelve nada.
```php
<?php
	$nombre = array ('ana', 'pedro', 'luís', 'marta', 'Ana', 'Pedro');
	sort($nombre, SORT_NATURAL | SORT_FLAG_CASE);
	foreach ($nombre as $persona) {
		echo $persona.'<br/>';
	}
?>
```
**rsort (array)** Ordena los elementos de la matriz en orden descendente. Esta función también cambia la matriz pasadaa y vuelve a asignar los índices numéricos desde 0. no devuelve nada.
**asort (array)** Funciona como sort(), con la diferencia de que retiene los índices de elementos originarios. No devuelve nada.
**arsort (array)** como rsort(), en orden descendente; pero conserva los índices originales. No devuelve nada.
**in_array (valor, array)** Encuenta unvalor dentro de la matriz. Devuelve un valor booleano: verdadero o falso dependiendo de si el valor buscado está o no presente en la matriz.
```php
<?php
	$nombre = array ('ana', 'pedro', 'maría', 'luisa');
	if (in_array('Ana', $nombre)){
		echo 'Hemos encontrado el elemento';
	}
?>
```
```php
<?php
	$numeros = array (1, 3, 6, 9, '5', '0');
	if(in_array('5',$numeros, true)) {
		echo"Se ha encontrado el elemento";
	}
?>
```
**array_key_exists (valor, array)** Busca el valor de los índices (y no entre los valores) de la matriz. Devuelve un valor
booleano.
**array_search (valor, array)** Busca el valor de la matriz y se indica su clave. Devuelve el índice del valor encontrado, o si la búsqueda no tiene éxito, el valor FALSE.
**array_merge (array matriz [, array ...])** Fusiona los elementos de dos o más matrices. Los elementos con índices numéricos de un array se anexan a los del otro y se vuelven a reenumerar. Los índices asociativos son retenidos, y si hay más elementos en diferentes matrices con los mismos indices asociativos, los últimos sobrescriben los anteriores. Devuelve la matriz resultante de la fusión.
**array_pop (array)** Extrae el último elemento de la matriz, acortando el array con un elemento menos. Devuelve el elemento situado en la parte inferior de la matriz, y cambiar simultáneamente la matriz de entrada quitando ese elemento.
**array_push (array, valor [, valor ...])** Añade valores especificados en la matriz. Equivale a usar la instrucción $array[] = $valor, con la ventaja de que nos permite anexar varios valores a la vez. Devuelve el número de elementos de la matriz después tras añadir los elementos.
**array_shift (array)** Extrae un elemento, como array_pop(), pero en este caso es al principio. También en este caso, la matriz se "acorta", y también los índices numéricos se vuelven a numerar. Permanece sin cambios los índices asociativos. Devuelve el elemento extraido de la matriz.
**array_unshift (array, valor [, valor ...])** Insertar valores al principio de la matriz. Devuelve el número de elementos de la matriz después de la inserción.
**implode (cadena, array)** Es la función opuesta de explode(), y sirve para reunir en una única cadena los valores del array. La cadena especificada como el primer parámetro se interpone entre todos los elementos de la matriz. Devuelve la cadena resultado de la agregación. Su sinónimo es join().

**[Regresar al índice](#indice)**

----------------------------------

He aquí algunos ejemplos que utilizan estas funciones:
```php
$arr= array('Lucas', 'Juan', 'Mateo', 'Pablo', 'Antonio', 'Marcos', 'Jose');
$n = count($arr); // $n devuelve 7
$arr1 = array_reverse($arr); // $arr1 tendrá los elementos invertidos, desde 'Jose' a 'Lucas'
echo $arr[1], '<br>'; // 'Juan'
echo $arr1[1], '<br>'; // 'Marcos'
/* Ahora $arr será: 'Antonio', 'Juan', 'Jose', 'Lucas', 'Marcos', ' Mateo', 'Pablo' */
sort($arr);
$a = in_array('Juan', $arr); // $a es verdadero (TRUE)
$a = in_array('Francisco', $arr); // $a es falso (FALSE)
$ultimo = array_pop($arr); // $ultimo es 'Pablo'
$ultimo = array_pop($arr); // ahora $ultimo es 'Mateo', y en $arr quedan 5 elementos
$primero = array_shift($arr); // $primero es 'Antonio'
/* 'Mateo' e 'Antonio' se vuelven a colocar en la cabeza del array; $a tiene 6 valores */
$a = array_unshift($arr, $ultimo, $primo);
$cadena = implode(' ', $arr); // $cadena se convierte en 'Mateo Antonio Juan Jose Lucas Marcos' */
/* $new_arr contendra 13 elementos:
* 'Mateo', 'Antonio', 'Juan',
* 'Jose', 'Lucas', 'Marcos' (estos son los seis provinientes de $arr),
* 'Jose', 'Marcos',' Antonio', 'Pablo',
* 'Mateo', 'Juan', 'Lucas' (estos son los 7 de $arr1). Los índices irán de 0 a 12.
*/
$new_arr = array_merge($arr, $arr1);
// Preparamos un array con claves asociativas:
$famila = array(
		'padre' => 'Claudio',
		'madre' => 'Paula',
		'hijo'=> 'Marcos',
		'hija' => 'Elisa');
// Creamos una copia de nuestro array para poder hacer experimentos
$fam1 = $familia;
// ahora $fam1 será 'Paula', 'Marcos', 'Elisa', 'Claudio', con índices de 0 a 3
rsort($fam1);
$fam1 = $familia; // restauramos la matriz original
/* de nuevo $fam1 será 'Paula', 'Marcos', 'Elisa', 'Claudio',
* Pero cada uno con su llave original
* ('madre', 'hijo', 'hija', 'padre')
*/
arsort($fam1);
$a = array_key_exists('hija', $fam1); // $a es TRUE
$a = array_key_exists('tio', $fam1); // $a es FALSE
$a = array_search('Claudio', $fam1); // $a es 'padre'
$a = array_search('Mateo', $fam1); // $a es FALSE
```

**[Regresar al índice](#indice)**

----------------------------------

7.4.Funciones que trabajan con fechas
-------------------------------------
Concluimos este resumen de las funciones de PHP con algunas funciones dedicadas al manejo de fechas y horas. Antes de comenzar debemos hacer una mención del timestamp, en el que se basa en estas características. El timestamp es un entero, en uso desde los primeros tiempos de los sistemas UNIX, lo que le lleva a estar representado de forma interna como el número de segundos transcurridos desde el 1 de enero 1970 . Por ejemplo, la marca de tiempo en relativo a 15:56:20 del 24 de abril de 2003 fue 1,051,192,580.
Vamos a verlas en detalle:
**time ()** Este es el más simple de todos, ya que proporciona el timestamp del momento en el que se ejecuta. Devuelve un entero (fecha y hora).
**date (formato [, timestamp])** Se considera el timestamp dado en la función (y si no se especifica, se considera la actual), y proporciona una fecha formateada de acuerdo con las especificaciones que figuran en el primer parámetro. Estas especificaciones se basan en una tabla de valores que resumimos a continuación:

| Código | Descripción |
|:--------:|:-------------|
|Y|año con 4 digitos |
|y|año con 2 digitos |
|n|número del mes (1-12) |
|m|número del mes con 2 dígitos (01-12) |
|F|mes textual (de 'January' a 'December')|
|M|mes textual con 3 letras ('Jan' a 'Dec')|
|d|día del mes en dos dígitos (01-31)|
|j|día del mes (1-31)|
|w|día de la semana, numérico (0 = domingo, 6 = sabado)|
|l|día de la semana, en texto ('Sunday' - 'Saturday')|
|D|día de la semana de 3 letras ('Sun' - 'Sat')|
|H|hora en 2 dígitos (00-23)|
|G|hora (0-23)|
|i|minutos en dos dígitos (00-59)|
|s|segundos en dos dígitos (00-59)|

**date()** La función date() devuelve una cadena con formato que representa la fecha.
**mktime (hora, minuto, segundo, mes, día, año)** Es una característica muy útil, pero debe manejarse con cuidado, ya que los parámetros que requieren entradas (todos números enteros) tienen un fin muy particular, que puede fácilmente conducir a errores.
Sobre la base de estos parámetros, mktime() calcula la fecha y hora, pero lo más interesante es que podemos usarla para hacer cálculos sobre fechas. De hecho, si por ejemplo, en el parámetro mes pasamos 14, PHP lo interpretará como 12 + 2 , es decir, "febrero del año siguiente", y considerará el mes de febrero del año siguiente.
Obviamente, el mismo tipo de cálculos se pueden hacer sobre todos los demás parámetros. Devuelve un entero (fecha y hora).
**checkdate (mes, día, año)** Comprueba si los valores transmitidos representan una fecha válida. Devuelve un valor booleano.
Vamos a ver algunos ejemplos de estas funciones:
```php
// $a obtiene la fecha y hora (timestamp) del 24/4/2003 a las 15.56.20
$a = mktime(15,56,20,4,24,2003);
// $b será "24 Apr 03 - 15:56"
$b = date('d M y - H:i', $a);
// timestamp a las 14 horas 60 días después del 24/4/2003
$a = mktime(14,0,0,4,24+60,2003);
$c = checkdate(5,1,2003); // verdadero
$c = checkdate(19,7,2003); // falso (19 no es un mes)
$c = checkdate(4,31,2003); // falso (31 de abril no existe)
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejemplo con fechas, sus diferentesformatos y la función Date
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>
		<?php
			$fecha = strtotime("05/14/23");
			echo date('M/Y', $fecha);
		?>
	</body>
</html>
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejercicio 7.3.** En primer lugar, deberemos crear una variable que guarde el número de día de hoy.
A continuación, haremos que, si la fecha es o está por debajo del día 10, aparecerá el mensaje "Periodo de pago activo".
Si el día es superior al 10, el mensaje que aparecerá es "Fuera del periodo de pago"
```php
<!DOCTYPE html>
<html>
 	<head>
 		<meta charset="utf-8" />
 		<title>Ejercicio</title>
 	</head>
 	<body>
 		<?php
 			$dia=date("d");
 			echo ($dia<=10)? "Periodo de pago activo" : "Fuera del periodo de pago";
		?>
 	</body>
</html>
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejercicio 7.4.** Crearemos una página que muestre un mensaje de bienvenida que dependa de la hora
actual, de la siguiente manera:
* Si la hora se encuentra entre las 8 y las 13, mostrará ‘Buenos días’
* Si la hora se encuentra entre las 14 y las 20, mostrará ‘Buenas tardes’
* Si la hora se encuentra entre las 21 y las 7, mostrará ‘Buenas noches’
```php
<!DOCTYPE html>
<html>
 	<head>
 		<meta charset="utf-8" />
 		<title>Ejercicio</title>
 	</head>
 	<body>
 		<?php
			$nombre = "Pedro";
 			$hora = date ("H");
 			echo "Ahora mismo son las ".$hora."<br>";
			if ($hora >= 8 && $hora < 14)
 				$saludo = "Buenos días, ";
 			}else if ($hora >= 14 && $hora <= 20){
 				$saludo = "Buenas tardes, ";
 			}else {
 				$saludo = "Buenas noches, ";
			}
			$saludo = $saludo . $nombre;
			print ($saludo);
 		?>
 	</body>
</html>
```

**[Regresar al índice](#indice)**

----------------------------------
----------------------------------

8.FUNCIONES DEFINIDAS POR EL USUARIO
====================================

8.1.Como crear funciones propias
--------------------------------

Como hemos visto en lecciones anteriores, además de las numerosas funciones integradas en PHP, disponemos de la capacidad de **definir funciones que nos permiten realizar ciertas tareas en diferentes partes de nuestro script**, o mejor aún, **en distintos scripts**, simplemente recordando la porción del código relacionado, a los que hemos asignado un nombre que identifica la función en sí. Vamos a ver ahora cómo definir una función.
Veamos un ejemplo sencillo. Queremos construir una función que, dados tres números, devuelva el mayor de los tres. Veamos el código:
```php
function el_mayor($num1, $num2, $num3){
	if (! is_numeric($num1)) { return false; }
	if (! is_numeric($num2)) { return false; }
	if (! is_numeric($num3)) { return false; }
	if ($num1 > $num2){
 		if ($num1 > $num3){
			return $num1;
 		} else {
 			return $num3;
 		}
	} else {
		if ($num2 > $num3) {
 			return $num2;
 		} else {
 			return $num3;
 		}
	}
}
```
Como vemos, la definición de la función es a través de la palabra clave function, seguido por el nombre que hemos creado para la función y los paréntesis contienen los parámetros (o argumentos) que deben ser pasados "‹"‹a la función. A continuación, entre llaves, tenemos el código que se ejecuta cada vez que se invoca la función. El nombre de la función debe ser necesariamente único, esto significa que no se pueden definir dos funciones con el mismo nombre.
Dentro de la función, vemos la declaración **return:** Esta declaración es muy importante, ya que termina la función (es decir, devuelve el control al script en el punto donde la función fue llamada) y al mismo tiempo determina que el valor será devuelto por la función.
En nuestro ejemplo, en primer lugar los tres datos recibidos en la entrada se comprueban, uno tras otro, para asegurarse de que son numéricos: (los examina anteponiendo a la función `is_numeric()` el símbolo `!` de negación). Si no son numéricos la función devuelve el valor booleano falso.
Una vez verificado que los tres valores son numéricos, se comparan los dos primeros, y luego el mayor de los dos se compara con el tercero, de modo que se obtiene el mayor de los tres, que se devuelve entonces como el resultado de la función. Cuando llegue el momento de realizar esta función, podemos utilizar este código:
```php
$a = 9;
$b = 8;
$c = 15;
$m = el_mayor($a, $b, $c); // $m será 15
```
Como habrás visto, hemos llamado a la función utilizando nombres de variables diferentes de los utilizados en la propia función: en la función hemos usado `$num1`, `$num2` y `$num3` , mientras que el script hemos utilizado `$a`, `$b` y `$c` . Es muy importante recordar que no existe una relación definida entre los nombres de los argumentos que la función utiliza y los que se indique en la llamada. Lo que determina la correspondencia entre los argumentos es, de hecho, sólo la posición en la que se enumeran: en nuestro caso, $a se convierte en `$num1` dentro de la función, `$b` en `$num2` y `$c` en `$num3`.
Podríamos usar nuestra función también pasándole directamente los valores afectados, sin necesidad de utilizar las variables:
```php
$m = el_mayor(9, 8, 15); // $m será 15
/* $m se convierte en FALSE, debido a que el tercer argumento es no numérico y, por tanto,
* el control que hemos establecido al principio de la función la bloquea
$m = el_mayor(9, 8, 'hola');

```
**Ejemplo**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>
		<?php
			function mensaje(){
				echo ("Esta es nuestra página de prueba,bienvenido");
			}
			mensaje();
		?>
	</body>
</html>
```
**Ejemplo**
```php
<?php
	function diez(){
		for ($i=1; $i<=10;$i++){
			echo $i."<br/>";
		}
	}
	diez();
?>
```

**[Regresar al índice](#indice)**

----------------------------------

8.2.Funciones definidas en un archivo externo
---------------------------------------------
**Ejemplo**

|Funciones.php |
|--------------|

```php
<?php
	function mensaje(){
		echo ("Esta es nuestra página de prueba,bienvenido");
	}
	function diez(){
		for ($i=1; $i<=10;$i++){
			echo $i."<br/>";
		}
	}
?>
```

|Ejemplo |
|--------|

```php
<?php include('funciones.php'); ?>
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>
		<?php
			mensaje();
			echo"Aquí hay más cosas<br/><br/>";
			diez();
			diez();
		?>
	</body>
</html>
```

**[Regresar al índice](#indice)**

----------------------------------

8.3.Parámetros
--------------
**El alcance de las variables** Pasemos ahora a otro tema muy importante, que es el alcance (scope) de las variables. Existen variables utilizadas en una función que **existen sólo dentro de la función**, en tanto no se definen ni en otras funciones ni en el script principal.
Del mismo modo, las variables utilizadas por el script principal **no son vistas** por las funciones. Esta es una característica muy importante del PHP, ya que nos permite definir funciones con la máxima libertad a la hora de crear los nombres de las variables, sin tener que preocuparnos de que en nuestra secuencia de comandos (o alguna otra función) existan variables con el mismo nombre cuyo valor puede verse alterado. Esto significa, para volver al ejemplo anterior, si hubiéramos escrito print $num2 fuera de la función el_mayor() no conseguiríamos ningún resultado, y de hecho habríamos recibido un aviso de error, ya que la variable $num2, en ese ámbito, no está definida.
Las variables utilizadas en una función se llaman **variables locales**. Las variables utilizadas por el script principal son las **variables globales**.
Normalmente si una función necesita un cierto dato, es suficiente incluirlo entre los parámetros que se deben pasar. Sin embargo, existe la posibilidad de permitir que una función vea una variable global: declararándola a través de la **instrucción global**.
```php
function imprime($var1, $var2) {
	global $a;
	print $a;
}
$a = 'hola a todos';
$b = 'saludos';
$c = 'adios';
imprime($b, $c);
```
Este código, después de haber definido la función imprime() , asigna un valor a tres variables globales: $a , $b y $c . A continuación, llama a la función imprime(), pasando los valores de $b y $c , que en la función se llaman $var1 y $var2 pero en el interior no se utilizan. En lugar de ello, se declaró la variable global $a, que se ve definida con la cadena 'hola a todos', y esto es lo que se imprime. Si no existiera la instrucción "global $a", la variable $a no estaría definida dentro de la función, y la impresión generaría un error.
Sin embargo, **no se recomienda utilizar las variables globales de esta manera, porque el script y la propia función pierden claridad**.

**Fin de la función y el valor devuelto** Vimos anteriormente que la función termina con una sentencia return, que también se puede utilizar para devolver un valor. En el caso en que no exista el propósito de que la función devuelva un valor, basta con utilizar return. Por el contrario, en el caso de queramos devolver más de un valor, como la sintaxis de PHP nos permite devolver una sola variable, podemos usar una matriz.
Veamos un ejemplo, imaginemos una función cuyo propósito es recibir un número y devolver su doble, su triple y su quíntuple:
```php
function multiplos($num) {
	$doble = $num * 2;
	$triple = $num * 3;
	$quintuple = $num * 5;
	$ris = array($doble, $triple, $quintuple);
	return $ris;
}
```
Con este sistema hemos sido capaces de devolver los tres valores de una función, respetando la sintaxis que implica sólo una. Obviamente, cuando vamos a llamar a la función, debemos saber que el resultado va a recibir una matriz:
```php
$a = 7;
$mul = multiplos($a); // $mul será un array de tres elementos
```
Si nos interesa, también podemos utilizar un constructor del lenguaje para desplegar de inmediato los tres valores en tres variables distintas.
```php
list($doble, $triple, $quintuple) = multiplos($a);
```
El constructor list() se utiliza para asignar valores de una matriz (la señalada a la derecha del signo igual) a una serie de variables que pasamos entre paréntesis. Evidentemente, es posible usarlo no sólo para "recoger" el resultado de una función, sino con cualquier matriz:
```php
$arr = array('Marcos','Pablo','Lucas');
list($primero, $segundo, $tercero) = $arr;
```
En este caso, $primero tomar el valor 'Marcos', $segundo 'Pablo', $tercero, el valor 'Lucas'.
Una aclaración: acabamos de ver que la función termina con la declaración return. En realidad esto no es necesario: de hecho, en el caso que no haya valores devueltos, podemos omitir la instrucción return, y la ejecución de la función termina cuando llegue al final del código en cuestión, devolviéndose el control al script principal (u otra función eventualmente llamada).

**[Regresar al índice](#indice)**

----------------------------------

8.3.1.Parámetros por Valor
--------------------------

**Ejemplo de parámetros por valor**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>
		<?php
			function cuadrado($numero) {
				echo $numero*$numero;
			}
			cuadrado(125);
		?>
	</body>
</html>
```

**Ejercicio 8.1.** Paso de parámetros por valor.
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>
		<?php
			function mayor($a,$b){
				if ($a > $b) {
					echo "el número mayor es $a";
				}
				elseif ($a < $b) {
					echo "el número mayor es $b";
				}
				else { echo "los dos números son iguales!"; }
			}
			mayor(5,5);
		?>
	</body>
</html>
```

**[Regresar al índice](#indice)**

----------------------------------

8.3.2.Parámetros por Referencia
-----------------------------

**Ejemplo parámetros por referencia**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>
		<?php
			$valor = "Esto es un texto";
			function cambio (&$valor) {
				$valor = "CAMBIADO!!";
				echo $valor;
			}
			cambio ($valor);
			echo "<br/>";
			echo $valor;
		?>
	</body>
</html>
```

**Ejemplo parámetros por referencia**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>
		<?php
			$numero = 8;
			function cuadrado($numero){
				$numero = $numero*$numero;
				echo $numero;
				echo"<br/>";
			}
			cuadrado($numero);
			echo $numero."<br/>";
			function cuadrado_total(&$numero){
				$numero = $numero*$numero;
				echo $numero;
				echo"<br/>";
			}
			cuadrado_total($numero);
			echo $numero."<br/>";
		?>
	</body>
</html>
```

**Ejemplo parámetros por referencia**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>
		<?php
			$a = 8;
			function incremento($a) {
				$a = $a+10;
				echo $a;
				echo "<br/>";
			}
			incremento($a);
			echo $a."<br/>";
			function incremento_total(&$a) {
				$a = $a+10;
				echo $a;
				echo "<br/>";
			}
			incremento_total($a);
			echo $a;
		?>
	</body>
</html>
```
**[Regresar al índice](#indice)**

----------------------------------

8.3.3.Parámetros por Defecto
--------------------------
**Ejemplo parámetros por defecto**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>
		<?php
			function cafe($tipo = "solo"){
				echo "Has elegido un café $tipo... Buen provecho!!";
			}
			cafe();
		?>
	</body>
</html>
```

**Ejemplo parámetros por defecto**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>
		<?php
			function incrementar($a = 1){
				echo ++$a;
			}
			incrementar ();
		?>
	</body>
</html>
```

**Ejemplo parámetros por defecto**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>
		<?php
			function suma($a=0,$b=0){
				$total = $a + $b;
				echo "El total de la suma de $a y $b es $total";
			}
			suma(3);
		?>
	</body>
</html>
```

**[Regresar al índice](#indice)**

----------------------------------

8.3.4.Número Variable de Parámetros
--------------------------------
**Argumentos opcionales** En ciertas situaciones, podemos crear funciones en las que **no es obligatorio que todos los argumentos presentados sean usados**. Hemos visto, en la lección anterior, que algunas funciones de PHP proporcionan **parámetros opcionales**. Lo mismo ocurre con las funciones definidas por nosotros: si, en el momento en el que se define la función, disponemos de un valor predeterminado para un parámetro, el parámetro se convierte en opcional cuando se llama a la función, y, si falta, la función utilizará el valor predeterminado.
Como ejemplo, consideremos una función que imprime los datos personales de una persona:
```php
function personal($nombre, $direccion, $nif='no disponible')
 print "Nombre: $nombre<br>"•;
 print "Direccion: $direccion<br>"•;
 print "N.I.F.: $cf<br>"•;
}
```
Esta función tiene tres parámetros de entrada, pero para el tercero hay un valor por defecto (la cadena "no disponible"). Así que, si la función es llamada con sólo dos argumentos, la variable $nif tendrá precisamente ese valor; pero si se especifican los tres argumentos, el valor predeterminado será ignorado. Veamos dos ejemplos de llamada a esta función:
```php
personal('Mario Lopez', 'C/ Goya 2', '4458545458J');
personal('Maria Sanchez", 'C/ Balmes 9');
```
En el primer caso tenemos esta salida en pantalla:
```php
Nombre: Mario Lopez
Dirección: C/ Goya 2
Código Postal: 4458545458J
Mientras que en el segundo
Nombre: Maria Sanchez
Dirección: C/ Balmes 9
Código Postal: no disponible
```
En el segundo caso no se ha indicado NIF, así que la función utiliza el valor por defecto.

**Ejemplo parámetros opcionales**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>
		<?php
			phpinfo();
		?>
	</body>
</html>
```

**Ejemplo parámetros opcionales**
```php
<html lang="es">
	<head>
		<title>Ejercicio</title>
		<meta charset = "UTF-8" />
	</head>
	<body>
		<?php
			function suma(){
				$total = 0;
				foreach(func_get_args() as $n){
					$total += $n;
				}
				echo "El total es $total";
			}
			suma(4,3,6,7,5);
		?>
	</body>
</html>
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejercicio 8.2.** Elabora una función que devuelva un array separado por comas (*,*), menos el último elemento separado por *y*.
```php
<?php
$numbers=[1, 3, 4, 7, 8, 9];
function return_list_elements ($array){
	if(!isset($array) || !is_array($array)){
		echo "Error return_list_elements: no se ha introducido un array.</br>";
	}
	$array_elements_number=count($array);
	echo "El array contiene ".$array_elements_number." elementos, que son: ";
	foreach ($array as $i=>$numbers){
		if($i ==($array_elements_number-2)){
			$next=" y ";
		}elseif($i ==($array_elements_number-1)){
			$next=".";
		}else{
			$next=", ";
		}
		echo $numbers.$next;
	}
}
return_list_elements($number);
?>
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejercicio 8.3.** Crea un script PHP que tenga tres variables, una tipo array, otra tipo string y otra boleana y que imprima un mensaje según el tipo de variable que sea.
```php
<?php
$data="Hola";
function data_type($data){
	echo "El tipo de dato es: ";
$data_type=gettype($data);
switch ($data_type){
	case integer:
		echo "NÚMERO ENTERO";
		break;
	case string:
		echo "CADENA";
		break;
        case boolean:
		echo "BOOLEANO";
		break;
	case double:
		echo "NÚMERO FLOTANTE";
		break;
	}
};
$is_number=is_numeric($data);
if($is_number){
	echo "El dato introducido es un número, ";
}else{
	echo "El dato introducido NO es un número, ";
};
data_type ($data);
?>
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejercicio 8.4.** Crea un array con el contenido de la siguiente tabla:

| Frutas   | Deportes   | Idiomas   |
|----------|------------|-----------|
| Manzana  |Futbol      |Español    |
| Naranja  |Tenis       |Inglés     |
| Sandia   |Baloncesto  |Francés    |
| Fesa     |Beisbol     |Italiano   |

Recórrelo y muestra la tabla en HTML con el contenido del array.
```php
<?php
$table= array(
    "Fruits"=>array("Apple","Orange","Watermelon","Strawberry"),
    "Sports"=>array("Futbol","Tennis","Basket","Beisbol"),
    "Languages"=>array("Spanish","English","French","Italian")
);
function file_column_max($array_multi){
    $i=0;
    foreach ($array_multi as $key => $category){
        $file_colum_max[$i]=count($array_multi);
        $i++;
    }
    return $file_colum_max;
}
function column_name($array_multi){
    $i=0;
    foreach ($array_multi as $key => $category){
        $column_name[$i]=$key;
        $i++;
    }
    return $column_name;
}
$max_column=max(file_column_max($table));
echo "<table><tr>";
$column_name=column_name($table);
//Imprime los títulos
foreach($column_name as $key=>$content){
    echo "<th>{$content}</th>";
}
echo "</tr>";
for ($i=0;$i<=$max_column-1;$i++){
    echo "<tr>";
    foreach($column_name as $key=>$content){
        echo "<th>".$table[$content][$i]."</th>";
    }
    echo "</tr>";
}
echo "</table>";
?>
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejercicio 8.5.** Crea una función a la que le pases un número y te saque su tabla de multiplicar.
```php
<?php
function tabla($numero){
	$tabla = "";
	for($i = 1; $i <= 10; $i++){
		$cuenta = $i*$numero;
		$tabla .= "{$i} x {$numero} = {$cuenta} <br/>";
	}

	return $tabla;
}

echo "<h1>Tablas de multiplicar</h1>";

for($i = 1; $i <= 10; $i++){
	echo "<h3>Tabla del {$i}</h3>";
	echo tabla($i);
}
?>
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejercicio 8.6.** Modifica el ejercicio anterior para pasarle un parámetro opcional que nos permita imprimir directamente la tabla en HTML.
```php
<?php
function tabla($numero, $html=null){
	$tabla = "";
	if($html!=null){
		$tabla.="<h3>Tabla del {$numero}</h3>";
	}
	for($i = 1; $i <= 10; $i++){
		$cuenta = $i*$numero;

		$tabla .= "{$i} x {$numero} = {$cuenta} <br/>";
	}
	if($html!=null){
		echo $tabla;
	}
	return $tabla;
}
echo "<h1>Tablas de multiplicar</h1>";
for($i = 1; $i <= 10; $i++){
	tabla($i,true);
}
?>
```

**[Regresar al índice](#indice)**

----------------------------------
----------------------------------

9.PROGRAMACIÓN ORIENTADA A OBJETOS
==================================
La POO es un paradigma de programación que utiliza objetos e interacciones en el diseño de un sistema.
Compuesta por varios elementos y características.
**ELEMENTOS DE LA POO CLASE** Es un modelo que se utiliza para crear objetos que comparten un mismo comportamiento, estado e identidad.

* **OBJETO** Es una entidad provista de **Métodos** (comportamientos a los cuales responde) y **Atributos** con valores concretos (estados) y propiedades (identidad).

**ELEMENTOS DE LA POO**
* **MÉTODO** Es el algoritmo asociado a un objeto que indica la capacidad de lo que éste puede hacer (acciones)
* **ATRIBUTO** Los atributos, son variables que contienen datos asociados a un objeto (propiedades)

**CARACTERÍSTICAS DE LA POO**
La POO debe guardar ciertas características que la identifican y diferencian de otros paradigmas de programación.
* **ABSTRACCIÓN** Aislación de un elemento de su contexto. Define las características esenciales de un objeto
* **ENCAPSULAMIENTO** Reúne al mismo nivel de abstracción, a todos los elementos que puedan considerarse pertenecientes a una misma entidad
* **MODULARIDAD** Característica que permite dividir una aplicación en varias partes más pequeñas, independientes unas de otras
* **OCULTACIÓN (AISLAMIENTO)** Los objetos están aislados del exterior, protegiendo a sus propiedades para no ser modificadas por aquellos que no tengan derecho a acceder a las mismas
* **POLIMORFISMO** Es la capacidad que da a diferentes objetos, la posibilidad de contar con métodos y atributos de igual nombre, sin que los de un objeto interfieran con el de otro
* **HERANCIA** Es la relación existente entre dos o más clases, donde una es la principal (madre) y otras son secundarias y dependen (heredan) de ellas (clases hijas), donde a la vez, los objetos heredan las características de los objetos de los cuales dependen
* **RECOLECCIÓN DE BASURA** Es la técnica que consiste en destruir aquellos objetos cuando ya no son necesarios, liberándolos de la memoria


**[Regresar al índice](#indice)**

----------------------------------

9.1.Clases
----------
*Las clases son para POO lo que para los arquitectos son los planos.*
Para definir una clase usamos la palabra reservada `class`. Las clases tienen propiedades, atributos, variables internas y funciones o métodos.

| Producto.php  |
|---------------|
```php
class Producto {
    // Declaración de propiedades
   var $nombre;
   var $talla;
   var $precio;
}
```

**[Regresar al índice](#indice)**

----------------------------------

9.2.Instancias
--------------
Las instancias permiten crear objetos a partir de las clases ya generadas. Para crear la instancia generamos una nuev variable que mediante la palabra reservada `new` instanciará la clase creando un nuevo objeto con ese patrón ya generado anteriormente.

| Producto.php  |
|---------------|
```php
class Producto {
    // Declaración de propiedades
   var $nombre;
   var $talla;
   var $precio;
}
```

| instancia.php  |
|----------------|
```php
<?php
require_once 'Producto.php';
// Crea una nueva instancia de Producto
$producto = new Producto;

// Setea las propiedades
$producto->nombre = 'Camiseta de CSS';
$producto->talla = 'L';
$producto->precio = 12;

// Acceder a las propiedades
echo "Acceder a las propiedades";
echo $producto->nombre." ";
echo $producto->talla." ";
echo $producto->precio." ";
echo "<br>";
```
**Nota:** se puede instanciar la clase mediante `new`, y setearla o darle valores referenciándolas mediante el operador flecha `->`, como se puede ver en el siguiente ejemplo `$producto->nombre`. Así mismo podremos referenciar dicha propiedad usando también el operadorflecha `->`, de la siguiente manera: `echo $producto->precio." ";`.

**Ejemplo**

| Producto.php  |
|---------------|
```php
class Producto {

    // Declaración de propiedades
    public $nombre;
    public $talla;
    public $precio = 12;

    function __construct($nombre, $talla)
    {
        //echo "He sido construido.n";
        $this->nombre = $nombre;
        $this->talla = $talla;
    }

    function resumen()
    {
        echo $this->nombre." ";
        echo $this->talla." ";
        echo $this->precio." ";
    }
}
```

| instancia.php  |
|----------------|
```php
require_once 'Producto.php';
// Crea una nueva instancia de Producto
$producto = new Producto;

// Setea las propiedades
$producto->nombre = 'Camiseta de CSS';
$producto->talla = 'L';
$producto->precio = 12;

// Acceder a las propiedades
echo "Acceder a las propiedades";
echo $producto->nombre." ";
echo $producto->talla." ";
echo $producto->precio." ";
echo "<br>";

// Crea otra instancia de Producto
echo "Crea otra instancia de Producto";
$producto2 = new Producto;

$producto2->nombre = 'Camiseta de JS';
$producto2->talla = 'S';
$producto2->precio = 11;

echo "Otro producto: {$producto2->nombre}<br>";
echo "El precio de {$producto->nombre} es {$producto->precio}<br>";
echo "El precio de {$producto2->nombre} es {$producto2->precio}<br>";
$producto->resumen();
echo "<br>";
$producto2->resumen();
```

**[Regresar al índice](#indice)**

----------------------------------

9.3.Valores por defecto
-----------------------

Los valores por defecto permiten añadir a una variable declarada un valor por defecto que tendrá la misma cuando no se facilite al instanciar la clase.

| Producto.php  |
|---------------|
```php
class Producto {
    // Declaración de propiedades
   var $nombre;
   var $talla;
   var $precio=12;
}
```

**[Regresar al índice](#indice)**

----------------------------------

9.4.Propiedad static
--------------------
Declarar propiedades o métodos de clases como estáticos los hacen accesibles sin la necesidad de instanciar la clase. Una propiedad declarada como **static** no puede ser accedida con un objeto de clase instanciado (aunque un método estático sí lo puede hacer).

```php
class coches {
	public $nombre = "Nombre del modelo";
	public $precio = 00;
	static $terreno = "Agrícola";
	function __construct ($nombre, $precio){
		$this->nombre = $nombre;
		$this->precio = $precio;
	}
	public function fichaCoche(){
		return "Modelo: ".$this->nombre." Precio: ".$this->precio;
	}
}
echo coches::$terreno;
```

**[Regresar al índice](#indice)**

----------------------------------

9.5.Herencia de Clases
------------
Los objetos pueden heredar propiedades y métodos de otros, mediante la extensión (herencia) de clases, cuya característica representa la relación existente entre diferentes objetos. Para definir una clase como extención de otra se utiliza la palabra clave extends.
```php
<?php
class NombreDeMiClaseMadre {
	//...
}
class NombreDeMiClaseHija extends NombreDeMiClaseMadre {
	/* esta clase hereda todos los métodos y propiedades de la clase madre NombreDeMiClaseMadre	*/
}
```

**Ejemplo**

| Producto.php  |
|---------------|
```php
class coches {
	public $nombre = "Nombre del modelo";
	public $precio = 00;
	function __construct ($nombre, $precio){
		$this->nombre = $nombre;
		$this->precio = $precio;
	}
	public function fichaCoche(){
		return "Modelo: ".$this->nombre." Precio: ".$this->precio;
	}
}

class industrial extends coches{
	public $licencia;
	function __construct ($nombre, $precio, $licencia){
		parent::__construct($nombre, $precio);
		$this->licencia = $licencia;
	}
	public function fichaCoche(){
		return "Modelo: ".$this->nombre." Precio: ".$this->precio. " Licencia: ".$this->licencia;
	}
}
$turismo1 = new coches ('Seat Ibiza', 5780);
$turismo2 = new coches ('Ford Focus', 7790);
$industrial2 = new industrial ('Iveco', 19580, 'B');

echo $turismo2->fichaCoche()."<br>";
echo $industrial2->fichaCoche()."<br>";

```

**[Regresar al índice](#indice)**

----------------------------------

9.5.Clase Abstracta
-------------------
Las **Clases abstractas** son aquellas que no necesitan ser instanciadas pero sin embargo, serán heredadas en algún momento. Su finalidad, es la de declarar clases genéricas que necesitan ser declaradas pero a las cuales, no se puede otorgar una definición precisa.
También se pueden declarar métodos abstractos.
```php
<?php

abstract class NombreDeMiClaseAbstracta {
	var $un_atributo_abstracto;
	function un_metodo_abstracto();
}
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejemplo Clase Abstracta**
```php
<?php
class Fruta {
    private $color;
    public function comer() {
        //Comer la fruta
    }
}
class Naranja extends Fruta {
    public function comer() {
        // código para comer la naranja
    }
}
class Patilla extends Fruta {
    public function comer() {
        // código para comer la patilla
    }
}
$naranja = new Naranja();
$naranja->comer();
$fruta = new Fruta();
$fruta->comer();
?>
```
Vamos a analizar el ejemplo anterior, primero creamos una Naranja que extiende de Fruta y la comemos. Al crear la Naranja le estamos dando mas sentido a la clase de Fruta. En las ultimas lineas estamos creando una Fruta y la comemos también ¿pero a que sabe una Fruta? En este punto estamos haciendo algo que no tienen sentido y aquí es donde entran las clases y métodos abstractos. Veamos este ejemplo de nuevo pero Fruta sera una clase abstracta.

```php
<?php
// podemos observar que nuestra clase ahora es abstracta, por lo tanto podrá tener métodos y propiedades abstractos y no podrá ser instanciada directamente
// Para declarar una clase abstracta debemos utilizar la palabra reservada abstract antes de la declaración de la clase
absctract class Fruta {
    private $color;
    // nuestro método comer ahora es abstracto y debe ser implementado por la clase que herede Fruta
    // Para declarar un método abstracto debemos utilizar la palabra reservada abstract antes de la declaración normal del método y en vez de utilizar llaves para colocar el código utilizamos un punto y coma (;) ya que no vamos a tener código en la función.
    abstract public function comer();
}
// para extender una clase abstracta usamos la misma nomenclatura que para extender una clase normal.
class Naranja extends Fruta {
    public function comer() {
        // código para comer la naranja
    }
}
class Patilla extends Fruta {
    public function comer() {
        // código para comer la patilla
    }
}
$naranja = new Naranja();
$naranja->comer();
// Ahora estas dos lineas de código darán error y que no podemos instanciar una clase Fruta
$fruta = new Fruta();
$fruta->comer();
?>
```
Podemos ver como ahora tiene un poco mas de sentido el concepto de Fruta. Es una clase que solo puede ser extendida ya que una Fruta como tal no significa nada. Haciéndola una clase abstracta estamos obligados a extenderla y no instanciarla directamente.

**[Regresar al índice](#indice)**

----------------------------------

9.6.Clase Final
---------------
DEFINICIÓN DE CLASE FINAL
NO pueden ser heredadas por otra. Se definen anteponiendo la palabra clave final
```php
<?php
final class NombreDeMiClaseFinal {
	var $un_atributo_final;
	function un_metodo_final() {
	}
}
```

**¿QUÉ TIPO DE CLASE DECLARAR?**

| **Necesito una clase qué pueda... **                 		|Instanciable	| Abstracta	 | Heredada	| Final |
|---------------------------------------------------------------|:-------------:|:--------------:|:------------:|:-----:|
| Ser instanciada y/o heredada	                           	| ✔		| ☓    		| ☓	       | ☓     |
| Guardar relación con métodos y atributos de otra		| ☓		| ☓		| ✔	       | ☓     |
| Servir de modelo para otras, sin que pueda instanciarse	| ☓		| ✔		| ☓	       | ☓     |
| Instanciarse pero que no pueda ser heredada			| ☓		| ☓		| ☓	       | ✔     |


**[Regresar al índice](#indice)**

----------------------------------

9.7.Modificadores de acceso y visibilidad
-----------------------------------------
Los métodos y atributos de una clase pueden tener diferentes níveles de acceso, los cuáles pueden ser:
* **PÚBLICOS** Se definen anteponiendo la palabra clave `public` al nombre del atributo o método. Éstas, pueden ser accedidas desde cualquier parte de la aplicación, sin restricción.
```php
<?php
class NombreDeMiClase {
	public $un_atributo_publico;
	public function un_metodo_publico() {
	}
}
<?p
```
* **PRIVADOS** Se definen anteponiendo la palabra clave `private` al nombre del atributo o método. Éstos solo pueden ser accedidos por la clase que los definión.
```php
<?php
class NombreDeMiClase {
	private $un_atributo_privado;
	private function un_metodo_privado() {
	}
}
```
* **PROTEGIDOS** Se definen anteponiendo la palabra clave `protected` al nombre del atributo o método. Pueden ser accedidos por la propia clase que los definió, así como por las clases que la heredan, pero no, desde otras partes de la aplicación.
```php
<?php
class NombreDeMiClase {
	protected $un_atributo_protegido;
	protected function un_metodo_protegido() {
	}
}
```
* **ESTÁTICOS** Se definen anteponiendo la palabra clave static al nombre del atributo o método. Pueden ser accedidos sin necesidad de instanciar un objeto y su valor es estático (es decir, no puede variar ni ser modificado).
```php
<?php
class NombreDeMiClase {
	public static $un_atributo_estatico;
	public static function un_metodo_estatico() {
	}
}
```
*Resumiento* ¿Cuál es la diferencia entre public, private y protected en las aplicaciones PHP? ¿Cuándo y por qué debería utilizar cada una de ellas? Ejemplos de variables y funciones de cada tipo:
* **public** hace que la variable/función se pueda acceder desde cualquier lugar, como por ejemplo otras clases y otras instancias de esa misma clase.
* **private** hace que la variable/función solamente se pueda utilizar desde la misma clase que las define.
* **protected** hace que la variable/función se puede acceder desde la clase que las define y también desde cualquier otra clase que herede de ella.
En otras palabras: *private = solo tú*, *protected = tú y tus descendientes*, *public = cualquiera*.

**Ejemplo Clase Pública**
```php
<?php
class prueba{
    public $abc = 'Variable publica';
    public function xyz(){
        echo 'Funcion publica';
    }
}
$objA = new prueba();
echo $objA->abc;//variable accesible desde todos lados
$objA->xyz();//metodo accesible desde todos lados
?>
```

**Ejemplo Clase Private**
```php
<?php
Class prueba {
    public $abc = 'variable publica';
    private $xyz = 'variable privada';
    public function pubDo($a){
        echo $a;
    }
    private function privDo($b){
        echo $b;
    }
    public function pubPrivDo(){
        $this->xyz = 'utilizando la variable privada desde adentro de la clase ';
        $this->privDo('llamando a la función privada desde adentro de la clase');
    }
}
$objT = new prueba();
//Esto funciona bien porque la variable es publica
$objT->abc = 'cambiando variable publica';
//Esta linea dara error porque la variables es privada
// y por lo tanto no se puede acceder a ella desde un objeto
$objT->xyz = 'cambiando variable privada';
// esta función se ejecutara sin ningún problema ya que es publica
$objT->pubDo("prueba");
// esta función no se podrá ejecutar ya que es privada
$objT->privDo(1);
// esta función se podrá ejecutar
// aunque en su interior llama a dos funciones privada.
// Esto ocurre ya que las funciones privadas se están llamando
// desde adentro de la clase y desde afuera se llama a la publica.
$objT->pubPrivDo();
?>
```

**Ejemplo Clase Protected**
```php
<?php
class pruebaPadre
{
    protected function funcionProtegida(){
        echo 'llamando al a funcion protegida del padre';
    }
}
class pruebaHijo extends pruebaPadre{
    public function funcionPublica (){
        $this->funcionProtegida();
    }
}
$objPadre = new pruebaPadre();
// este llamado a la funcion dara error,
// ya que esta funcion protegia solo se puede llamar
// desde adentro de la clase
$objPadre->funcionProtegida();
$objHijo = new pruebaHijo();
// esta funcion publica llama a la funcion protegida de
// la clase padre y no dara error porque el llamado
// a la funcion protegia se hace desde adentro de la clase
$objHijo->funcionPublica();
```

**[Regresar al índice](#indice)**

----------------------------------

9.8.Acceso a los objetos
------------------------
Para acceder a los métodos y atributos de un objeto, existen diferentes maneras de hacerlo. Todas ellas, dependerán del ámbito desde el cual se les invoque así como de su condición y visibilidad

* **DENTRO DE LA CLASE Y NO SIENDO ESTÁTICO** Utilizando la pseudo-variable $this, siendo esta una referencia al objeto mismo:
```php
<?php
class NombreDeMiClase {
	$this->atributo;
	$this->metodo();
}
```

* **DENTRO DE LA CLASE Y SIENDO ESTÁTICO** Se accede mediante el operador de resolución de ámbito, (doble dos puntos ::) anteponiendo la palabra clave self o parent según se trate de una propiedad de la misma clase o de otra heredada
```php
<?php
class NombreDeMiClase {
	self::atributo_estatico_de_esta_clase;
	parent::atributo_estatico_de_clase_madre;
	self::metodo_estatico_de_esta_clase();
	parent::metodo_estatico_de_clase_madre();
}
```

* **FUERA DE LA CLASE Y NO SIENDO ESTÁTICO** Se necesita instanciar un objeto de la clase y sólo se pueden acceder a métodos y atributos públicos.
```php
<?php
$objeto = new Clase();
$objeto->atributo_publico;
$objeto->metodo_publico();
```

* **FUERA DE LA CLASE Y SIENDO ESTÁTICO** No es necesario instanciar la clase. Sólo se pueden acceder a métodos y atributos públicos
```php
<?php
Clase::atributo_publico;
Clase::metodo_publico();
```
* **CONSTANTES** Mantienen su valor de forma permanente y sin cambios. A diferencia de las propiedades estáticas, las constantes solo pueden tener una visibilidad pública
```php
<?php
const MI_CONSTANTE = 'Este es el valor de mi constante y no cambiará';
```

**[Regresar al índice](#indice)**

----------------------------------

9.9.Métodos Mágicos
-------------------
(Métodos con funciones específicas pre definidas por PHP)

9.9.1.Constructores
-------------------
Los constructores se encargan de resumir las acciones de inicialización de los objetos. Cuando se instancia un objeto, se tienen que realizar varios pasos en su inicialización, por ejemplo dar valores a sus atributos y eso es de lo que se encarga el constructor. Los constructores pueden recibir unos datos para inicializar los objetos como se desee en cada caso.

La sintaxis para la creación de constructor varía con respecto a la de PHP 3 y 4, pues debe llamarse con un nombre fijo: __construct(). (Son dos guiones bajos antes de la palabra "construct")

A lo largo de los ejemplos de este manual vamos a ir creando un código para gestión de un videoclub. Vamos a empezar definiendo una clase cliente, que utilizaremos luego en nuestro programa.

**Ejemplo Uso constructor**
```php
class cliente{
   	public $nombre;
   	public $numero;
   	public $peliculas_alquiladas;

   	function __construct($nombre,$numero){
      	$this->nombre=$nombre;
      	$this->numero=$numero;
      	$this->peliculas_alquiladas=array();
   	}

   	function dame_numero(){
      	return $this->numero;
   	}
}
```
El constructor en esta clase recibe el nombre y número que asignar al cliente, que introduce luego en sus correspondientes propiedades. Además inicializa el atributo películas_alquiladas como un array, en este caso vacío porque todavía no tiene ninguna película en su poder.

----------------------------

*Nota:* En programación orientada a objetos $this hace referencia al objeto sobre el que se está ejecutando el método. En este caso, como se trata de un constructor, $this hace referencia al objeto que se está construyendo. Con $this->nombre=$nombre; estamos asignando al atributo `nombre` del objeto que se está construyendo el valor que contiene la variable $nombre, que se ha recibido por parámetro.

----------------------------

Luego hemos creado un método muy sencillo para poder utilizar el objeto. Vamos a ver unas acciones simples para ilustrar el proceso de instanciación y utilización de los objetos.
```php
//instanciamos un par de objetos cliente
$cliente1 = new cliente("Pepe", 1);
$cliente2 = new cliente("Roberto", 564);

//mostramos el numero de cada cliente creado
echo "El identificador del cliente 1 es: " . $cliente1->dame_numero();
echo "El identificador del cliente 2 es: " . $cliente2->dame_numero();
```
Este ejemplo obtendría esta salida como resultado de su ejecución:

El identificador del cliente 1 es: 1
El identificador del cliente 2 es: 564

**[Regresar al índice](#indice)**

----------------------------------

**Ejemplo Constructor**
```php
<?php
class calculadoraEuro{
    public $dolar_euro;
    // el constructor tiene que ser un metodo publico
    public function __construct(){
        $this->dolar_euro = 0.74;
        echo 'El valor del euro es: '. $this->dolar_euro;
    }
    public function dolaresEuros( $dolares){
        return $dolares.' dolares son '. ($dolares * $this->dolar_euro) .' euros';
    }
}
$calculadora = new calculadoraEuro();
echo $calculadora->dolaresEuros(5);
?>
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejemplo Constructor**

| producto.php  |
|---------------|
```php
class Producto {

    // Declaración de propiedades
    public $nombre;
    public $talla;
    public $precio = 12;

    function __construct($nombre, $talla)
    {
        //echo "He sido construido.n";
        $this->nombre = $nombre;
        $this->talla = $talla;
    }

    function resumen()
    {
        echo $this->nombre." ";
        echo $this->talla." ";
        echo $this->precio." ";
    }
}
```

| constructor.php  |
|------------------|
```php
require_once 'Producto.php';

$producto1 = new Producto('Camiseta de HTML', 'L');
$producto2 = new Producto('Camiseta de JS', 'S');
$producto3 = new Producto('Camiseta de CSS', 'M');
$producto4 = new Producto('Camiseta de PHP', 'L');

echo $producto1->nombre . PHP_EOL;
echo $producto2->nombre . PHP_EOL;
echo $producto3->nombre . PHP_EOL;
echo $producto4->nombre . PHP_EOL;
```

**[Regresar al índice](#indice)**

----------------------------------

9.9.2.Destructor
----------------
Es el encargado de liberar de la memoria, al objeto cuando ya no es referenciado. Se puede aprovechar este método, para realizar otras tareas que se estimen necesarias al momento de destruir un objeto.
```php
<?php
class NombreDeMiClase {
	function __destruct() {
	}
}
```

**[Regresar al índice](#indice)**

----------------------------------

**OTROS MÉTODOS MÁGICOS** __call, __callStatic, __get, __set, __isset, __unset, __sleep, __wakeup, __toString, __invoke, __set_state y __clone.  Para ver su descripción y ejemplos, remitirse a la documentación

**[Regresar al índice](#indice)**

----------------------------------

9.10.Interfaces
--------------

Las **interfaces** de objetos son contratos que han de cumplir las **clases** que las implementan. Contienen **métodos vacíos** que obligan a una clase a emplearlos, promoviendo así un **estándar de desarrollo**.

Si una clase implementa una _**interface**_, está obligada a usar todos los métodos de la misma (y los mismos tipos de argumentos de los métodos), de lo contrario dará un **error fatal**. Pueden emplearse **más de una interface en cada clase**, y pueden **extenderse** entre ellas mediante _extends_. Una interface puede extender una o más interfaces.

Todos los métodos declarados en una interface deben ser públicos.

Para definir una interface se utiliza la parabra _**interface**_, y para extenderla se utiliza _**implements**_.

```php
interface Automovil {
    public function getTipo();
    public function getRuedas();
}
class Coche implements Automovil {
    public function getTipo(){
        echo "Coche";
    }
    public function getRuedas(){
        echo "4";
    }
}
class Moto implements Automovil {
    public function getTipo(){
        echo "Moto";
    }
    public function getRuedas(){
        echo "2";
    }
}
```

Las clases **Coche** y **Moto** están obligadas a definir las funciones _getTipo()_ y _getRuedas()_. Así se crea un modelo para todas las **clases** de automóviles que deben aportar o definir unos métodos mínimos. Si por ejemplo _getTipo()_ tuviera un argumento de tipo _**Array**_: _getTipo(Array $tipos)_, las clases que implementen la interface deberán importar un argumento del mismo tipo.

Las interfaces también pueden definir **constantes**, que funcionan igual que las **constantes en clases**, pero no pueden ser sobreescritas por sus descendientes, ya sean clases o interfaces.

Se utilizan cuando se tienen muchas clases que tienen en común un comportamiento, pudiendo asegurar así que ciertos métodos estén disponibles en cualquiera de los objetos que queramos crear. Son especialmente importantes para la **arquitectura de aplicaciones complejas**.

**[Regresar al índice](#indice)**

----------------------------------

**Ejemplo Inbterface**
```php
<?php

interface InterfaceA {
	public function un_metodo_publico();
}

interface InterfaceB {
	public function otro_metodo_publico();
}

class NombreDeMiClase implements InterfaceA, InterfaceB {
	/* esta clase implementa todos los métodos
		de la Interfaces invocadas */
}
```

**[Regresar al índice](#indice)**

----------------------------------

**Ejemplo Interface**
```php
<?php

// para declarar una interfaz se utiliza la palabra reservada interface en vez de la palabra class
interface Interaccion {

    // los métodos de la interface se declaran como en una clase normal pero sin implementación
    public function encender();
    public function apagar();
}

interface Direccion {
    public function girarDerecha();
    public function girarIzquierda();
}

// para hacer uso de una interfaz se deben declarar después de el nombre de la clase y anteponiendo la palabra implements.
// si se tienen varias interfaces entonces se separan con coma (,)
class Televisor implements Interaccion {

    public function encender() {
        // este metodo es heredado desde la interfaz
    }

    public function apagar() {
        // este metodo es heredado desde la interfaz
    }
}

class Carro implements Interaccion, Direccion {

    public function encender() {
        // este metodo es heredado desde la interfaz Interaccion
    }

    public function apagar() {
        // este metodo es heredado desde la interfaz Interaccion
    }

    public function girarDerecha(){
        // este método es heredado desde la interfaz Direccion
    }
    public function girarIzquierda(){
        // este método es heredado desde la interfaz Direccion
    }
}

?>
```

**[Regresar al índice](#indice)**

----------------------------------

**DIFERENCIA ENTRE INTERFACES Y CLASES ABSTRACTAS**
Las clases abstractas, no dejan de ser clases, las cuales representan la abstracción de un objeto siguiendo un orden de relación jerarquíca entre ellas.
Clase B hereda de Clase A y Clase C hereda de Clase B, pero no puede tener herencias múltiples, es decir no puede heredar de más de una clase, ya que guardan una relación de orden jerárquico entre sí.
Las interfaces son solo un conjunto de métodos característicos de diversas clases, independientemente de la relación que dichas clases mantengan entre sí.
Una misma clase, puede implementar múltiples interfaces

**CARACTERÍSTICAS DE LAS INTERFACES**
* No pueden tener el mismo nombre que una clase
* No pueden instanciarse porque no tienen referencias asociadas a objetos
* No pueden definir propiedades
* Los métodos de una interfaz deben ser públicos, sólo estar definidos y sin cuerpo
* Las clases que implementan una interfaz deben utilizar todos los métodos de la misma
* Diferentes interfaces no pueden tener nombres de métodos idénticos si serán implementadas por una misma clase.

**[Regresar al índice](#indice)**

----------------------------------

9.11.Excepciones en PHP
-----------------------

Una excepción puede ser lanzada ("thrown") y opcionalmente capturada ("catched"). El código debe estar dentro de un bloque try para capturar las excepciones. Cada bloque try debe tener al menos un bloque catch o finally.

* **Catch**. Pueden usarse múltiples bloques catch para atrapar diferentes clases de excepciones. Si se lanza una excepción en el bloque try, el código siguiente a la declaración no se ejecutará, y PHP buscará un primer bloque catch. Si no se captura una excepción se emititá un error fatal `"Uncaught Exception..."` (a no ser que se haya definido un manejador con `_set_exception_handler()_)`.
* **Finally**. Puede especificarse después o en lugar de bloques catch. El código dentro de un bloque finally siempre se ejecutará después de los bloques try y catch, independientemente de si se ha lanzado una excepción, y antes de que se continúe con el flujo normal del script.
El objeto lanzado debe ser siempre una instancia de la clase Exception o una subclase de Exception (sino PHP emite error fatal).

Lo que ocurre cuando se dispara una excepción es lo siguiente:

* El **estado actual del código** se guarda.
* La **ejecución del código cambia** a una función **exception handler** predefinida.
* **Dependiendo de la situación**, el handler podría entonces resumir la ejecución desde el estado de código guardado, terminar la ejecución del script o continuar con el script desde una parte distinta del código.
Cuando se lanza una excepción desde una función o método de clase, va hasta la función o método que lo llamó. Continúa así hasta que alcanza el primer nivel o la **excepción es capturada**. Si llega hasta el primer nivel sin ser capturada, se produce un **error fatal**. Por ejemplo, tenemos una función que lanza una excepción, llamamos a ésta desde otra y finalmente llamamos a esta segunda desde el script principal:
```php
function unaFuncion(){
    throw new Exception('Mensaje desde unaFuncion().');
}
function otraFuncion(){
    unaFuncion();
}
try {
    otraFuncion();
} catch (Exception $e){
    echo 'Excepción capturada: '.$e->getMessage()."<br>";
}
// Devuelve: Excepción capturada: Mensaje desde unaFuncion().
```
Cuando hemos llamado a otraFuncion(), intentamos calcular **cualquier excepción**. Aunque otraFuncion() no lance una de forma directa, sí lo hace unaFuncion(). Ocurriría lo mismo si se añadiera otro nivel, y unaFuncion() llamara a otra que lanzara una excepción. Este funcionamiento puede producir que no se sepa de donde viene la excepción exactamente, por eso existe la función Exception::getTraceAsString, que devuelve la pila de una excepción como una cadena de caracteres.
```php
// Clase Exception propia
class MyCustomException extends Exception {}
// Función cualquiera
function hacerAlgo() {
    try {
        // Lanzamos excepción InvalidArgumentException
        throw new InvalidArgumentException("Lo estás haciendo mal", 112);
    } catch(Exception $e) {
        // Lanzamos excepción propia
        throw new MyCustomException("Algo ha ocurrido", 911, $e);
    }
}
try {
    hacerAlgo();
    } catch(Exception $e) {
    do {
        printf("%s:%d %s (%d) [%s]\n", $e->getFile(), $e->getLine(), $e->getMessage(),
            $e->getCode(), get_class($e));
    } while($e = $e->getPrevious());
}
```
En el ejemplo anterior, hacerAlgo() lanza una primera excepción InvalidArgumentException desde un try, que es capturada. La propia captura lanza otra excepción, esta vez de una clase propia MyCustomException. Ahora sí es capturada desde el try en hacerAlgo(), y se imprimen los datos de esta última excepción MyCustomException: getFile(), getLine(), getMessage(), etc. El while devuelve true porque hay un Exception error anterior, el InvalidArgumentException, por lo que continúa el loop e imprime los datos de éste. Finaliza porque no ha habido más Exception errors.

**[Regresar al índice](#indice)**

----------------------------------

**Ejercicio 1. ENCAPSULAMIENTO, GETTERS Y SETTERS**
```php
<?php
class Person {
/* TIPOS DE VISIBILIDAD PROPIEDADES: public, protected, private */
//No pueden ser modificados directamente necesitan de un método
	protected $firstName;
	protected $lastName;
	protected $birthdayDate;
	protected $changedFirstName=0;
//Pueden ser modificados directamente NO necesitan de un método
	public $nickName;

/* MÉTODOS */
//Método Constructor
	public function __construct (string $firstName, string $lastName, string $birthdayDate){
		$this->firstName=strtolower($firstName);
		$this->lastName=strtolower($lastName);
		$this->birthdayDate=new DateTime($birthdayDate);
	}

/* MÉTODOS SETTER */
	public function setFirstName (string $firstName){
		if($this->changedFirstName <2){
			$this->firstName=strtolower($firstName);
			$this->changedFirstName++;
		}else{
			throw new Exception("You can't change a firstName more then 2 times");
		}
	}

	public function setNickName (string $nickName){
    //contiene dos caracteres y es una cadena de texto
		if(strlen($nickName)>2 && is_string($nickName)){
			$this->nickName;
		}else{
			throw new Exception("You nickName must be text and have more than two characters");
		}
	}

/* MÉTODOS GETTER */
	public function getFirstName () :string {
		return ucfirst($this->firstName);
	}

	public function getLastName () :string {
		return ucfirst($this->lastName);
	}

	public function getFullName() :string{
		return ucwords(($this->firstName).' '.($this->lastName));
	}

	public function getAge(){
		$birthdayDate=$this->birthdayDate;
 		$now = new DateTime();
		$interval = $now->diff($birthdayDate);
		return $interval->y;
	}
}

/* PRUEBAS CLASE GENERADA */
$person1 = new Person ('duilio' , 'palacios', '10-10-2010');
// print_r($person1);
$person1->setFirstName('Pepe Luis');
$person1->setFirstName('josé manuel');
/*
Lanzaría un error al ser la tercera vez que se cambia la PROPIEDAD
$person1-> setFirstName('lolo');
*/
// echo var_dump($person1)."<br>";
echo "<strong>".$person1->getFullName()."</strong><br>";
/*
Lanzaría un error al no ser cadena de texto mayor de dos caracteres
$person1->setNickName('p');
*/
$person1->nickName='Pedro';
echo "nickName introducido inicialmente: "."<strong>".($person1->nickName)."</strong>"."<br>";
$person1->nickName='Nuevo Pedro';
echo "nickName modificado: "."<strong>".($person1->nickName)."</strong>"."<br>";
echo "La Persona: ".$person1->getFullName()."tiene ".$person1->getAge()." años.";
?>
```

**Ejercicio 2. HERENCIA Y ABSTRACCIÓN**
```php
<?php
/* CLASE ABSTRACTA */
abstract class Unit {
	protected $alive=true;
	protected $name;

	public function __construct (string $name){
		$this->name=strtolower($name);
	}
// Método Estándar
	public function move($direction){
		$name=ucfirst($this->name);
		echo "<p>$name avanza hacia $direction</p>";
	}

// Método Abstracto
	abstract public function attack($opponent);
}

/* CLASE EXTENDIDA */
class Soldier extends Unit {
// Ampliamos el Método Abstracto de la Clase Abstracta
	public function attack($opponent){
		$name=ucfirst($this->name);
		echo "<p>$name corta al $opponent en dos.</p>";
	}
}

class Archer extends Unit {
	public function attack($opponent){
		$name=ucfirst($this->name);
		echo "<p>$name dispara una flecha a $opponent.</p>";
	}
}

/*
//Devolvería error al ser una clase abstracta,
//habría que instanciar una clase no abstracta
$silence = new Unit('Silence');
*/
$silence = new Soldier('Silence');

$silence->move('el norte');

//Devolvería error al ser una función abstracta heredada
//$silence->attack('Ramm');
```
**Ejercicio 3. INTERACCIÓN ENTRE OBJETOS**
```php
<?php
//Ejercicio: Unidades que reciben una tercera o cuarta parte del daño

function show($message){
	echo "<p>$message</p>";
}

/* CLASE ABSTRACTA */
abstract class Unit {
	protected $hp=40;
	protected $name;

	public function __construct (string $name){
		$this->name=strtolower($name);
	}
// Método Abstracto
	// Indicamos que en la siguiente función debe pasarse
	// un parámetro de la clase Unit
	abstract public function attack(Unit $opponent);
// Método GETTER
	public function getName(){
		return ucfirst($this->name);
	}
	public function getHp(){
		return $this->hp;
	}

// Método Estándar
	public function move($direction){
		$name=ucfirst($this->name);
		show("$name avanza hacia $direction");
	}
	public function Die(){
		$name=ucfirst($this->name);
		show("$name muere.");
	}

	public function takeDamage($damage){
		$this->setHp($this->hp - $damage);
		if($this->hp <=0){
			$this->Die();
		}
	}
// Método SETTER
	private function setHp($points){
		$this->hp=$points;
		$name=ucfirst($this->name);
		show("$name ahora tiene {$this->hp} puntos de vida.");
	}
}

/* CLASE EXTENDIDA */
class Soldier extends Unit {
	protected $damage=40;
// Ampliamos el Método Abstracto de la Clase Abstracta
	public function attack(Unit $opponent){
		$name=ucfirst($this->name);
		show("$name corta al {$opponent->getName()} en dos.");
		$opponent->takeDamage($this->damage);
	}
	public function takeDamage($damage){
		return parent::takeDamage($damage / 2);
	}
}

class Archer extends Unit {
	protected $damage=20;
	public function attack(Unit $opponent){
		$name=ucfirst($this->name);
		show("$name dispara una flecha a {$opponent->getName()}.");
		$opponent->takeDamage($this->damage);
	}
	public function takeDamage($damage){
		if (rand(0,1)==1){
			return parent::takeDamage($damage);
		}
	}
}


$ramm=new Soldier('Ramm');
$silence = new Archer('Silence');

$silence->attack($ramm);
$silence->attack($ramm);
$ramm->attack($silence);
?>
```
