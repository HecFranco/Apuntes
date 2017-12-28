Documentación
=============
[html2pdf - GitHub](https://github.com/spipu/html2pdf)

Instalación y primer uso 
=========================
Lanzamos en la consola el comando `composer require spipu/html2pdf`.
Dentro de **composer.json**
Modificamos las sigueintes líneas para que aparezca referenciada la ubicación de la librería.
```json
    "autoload": {
        "psr-4": {
            "": "src/"
        },
        "classmap": [ "app/AppKernel.php", "app/AppCache.php" ]
    },
    "autoload-dev": {
        "psr-4": { "Tests\\": "tests/" },
        "files": [ "vendor/symfony/symfony/src/Symfony/Component/VarDumper/Resources/functions/dump.php" ]
    },
```
incluyendo el siguiente código con la ubicación de la librería `"vendor/spipu/html2pdf/src/Html2Pdf.php"` y `"vendor/spipu/html2pdf/src/Html2Pdf.php"`, para que quede así:
```json
    "autoload": {
        "psr-4": {
            "": "src/"
        },
        "classmap": [ "app/AppKernel.php", "app/AppCache.php", "vendor/spipu/html2pdf/src/Html2Pdf.php" ]
    },
    "autoload-dev": {
        "psr-4": { "Tests\\": "tests/" },
        "files": [ "vendor/symfony/symfony/src/Symfony/Component/VarDumper/Resources/functions/dump.php", "vendor/spipu/html2pdf/src/Html2Pdf.php"  ]
    },
```

Dentro del controlador llamaremos al objeto de la siguiente manera:
```php
<?php
/* Indicamos el namespace del Bundle                     ******************************************************/
	namespace AppBundle\Controller;
/* COMPONENTES BÁSICOS DEL CONTROLADOR ************************************************************************/
	use Sensio\Bundle\FrameworkExtraBundle\Configuration\Route;
	use Symfony\Bundle\FrameworkBundle\Controller\Controller;
	use Symfony\Component\HttpFoundation\Request;
	use Spipu\Html2Pdf\Html2Pdf;    // Objeto Base de Html2Pdf

class PruebaController extends Controller {
	public function pdfAction(Request $request){
		$pdf = new Html2Pdf('P','A4','es','true','UTF-8');
		$pdf->writeHTML("<h1>HolaMundo</h1>");
		$pdf->Output('PdfGeneradoPHP.pdf');
		var_dump($pdf);die();
	}
}
```

1.Básico
--------

La clase principal de esta biblioteca es `\Spipu\Html2Pdf\Html2Pdf`.

El constructor de PHP toma los siguientes parámetros:

Variable | Valor predeterminado | Descripción
---------|----------------------|--------------
$orientation | P | La orientación de página predeterminada, puede ser P (portatit) o L (lanscape)
$format | A4 | El formato de página predeterminado utilizado para las páginas. La lista del valor disponible es [aquí](https://github.com/tecnickcom/TCPDF/blob/master/include/tcpdf_static.php#L2097). También puede dar una matriz con 2 valores, el ancho y la altura en mm.
$lang | fr | Lenguaje para usar, para algunas traducciones menores. La lista de los idiomas disponibles es [aquí](https://github.com/spipu/html2pdf/tree/master/src/locale)
$unicode | true | Significa que la cadena HTML de entrada es unicode
$encoding |UTF-8 | Codificación charset de la cadena HTML de entrada
$margins | array(5, 5, 5, 8) | Los márgenes principales de la página (left, top, right, bottom) en mm
$pdfa | false | Si es VERDADERO, configure el documento en modo PDF / A

En la mayoría de los casos, solo usará los 3 primeros parámetros `$html2pdf = new \Spipu\Html2Pdf\Html2Pdf('P', 'A4', 'en');`

2.Gestión de página
--------

Para facilitar el diseño, se han agregado tres etiquetas específicas:
 
  * `<page>`
  * `<page_header>`
  * `<page_footer>`
  
Deben usarse de la siguiente manera:

```html
 <page> 
    <page_header> ... </page_header> 
    <page_footer> ... </page_footer> 
    ...
 </page> 
```

Usted **no debe** usar las etiquetas `<body>` y `<html>`.

## Etiqueta de página

### Atributos

Puede usar los siguientes atributos principales:

Atributo    | Predeterminado | Descripción
------------|----------------|-------------
pageset     | new            | Especifique si queremos usar la definición de página anterior (old) o una nueva (new)
pagegroup   | old            | Especifique si estamos en el mismo grupo de páginas (old) o en uno nuevo (new)
hideheader  |                | Números de página separados por comas en los que queremos ocultar el encabezado
hidefooter  |                | Números de página separados por comas en los que queremos ocultar el pie de página
orientation |                | Portait (P) o Lanscape (L). De forma predeterminada, la orientación especificada en el constructor Html2Pdf
format      |                | Formato para usar La lista de los valores disponibles es [aquí](https://github.com/tecnickcom/TCPDF/blob/master/include/tcpdf_static.php#L2097). De forma predeterminada, la orientación especificada en el constructor Html2Pdf
style       |                | css style
class       |                | css class

Puede usar los siguientes atributos para administrar el margen de la página:

Atributo   | Predeterminado | Descripción
-----------|----------------|-------------
backtop    | 0              | value with unit (mm, px, pt, % )
backbottom | 0              | value with unit (mm, px, pt, % )
backleft   | 0              | value with unit (mm, px, pt, % )
backright  | 0              | value with unit (mm, px, pt, % )

Puede usar los siguientes atributos para administrar el fondo de la página:

Atributo   | Predeterminado | Descripción
-----------|----------------|-------------
backcolor  | transparent    | css color value
backimg    |                | url de la imagen a usar
backimgx   | center         | x posición de la imagen en el fondo de la página: left / center / right / valor con la unidad (mm, px, pt,%)
backimgy   | middle         | y posición de la imagen en el fondo de la página: top / middle / bottom / valor con la unidad (mm, px, pt,%)
backimgw   | 100%           | ancho en la imagen en el fondo de la página: valor con unidad (mm, px, pt, % )

Puede agregar un pie de página ligero al usar el pie de página del atributo. Toma valores separados por coma:

Value| Description
-----|-------------
page | display the current page
date | display the generation date
time | display the generation time
form | display a disclamer about form compatibility

### explanation

It allows to define, for the entire html code included within the layout :

  * margins left, right, top, bottom (backleft, backright, backtop, backbottom)
  * background image, with its position and size (backimg, backimgx, backimgy, backimgw)
  * the background color (backcolor)
  * orientation (orientation) and format (format)
  * simple automatic footer (footer)
  * a header and a footer complex HTML (using tags page_header and page_footer).

It does not limit it-self to one final page of the PDF, but to a set of pages.

Any HTML code will be included automatically within the same layout.

It is possible to reuse the layout of the previous tag page using property pageset = “old.” This also automatically resume the header and the footer. 

## Page Header tag

Its allows you to use complex HTML as the header of the current page.

Its definition must necessarily be located just after the opening of the `<page>` tag.

It can contain any valid HTML.

It is **REQUIRED** to specify the top margin, using the `backtop` attribute on the `<page>` tag. 

You can use ̀`css` and `class` attribute on this specific tag.

## Page Footer tag

Its allows you to use complex HTML as the header of the current page.

Its definition must necessarily be located just after the opening of the `<page>` tag.

It can contain any valid HTML.

It is **REQUIRED** to specify the top margin, using the `backtop` attribute on the `<page>` tag.

You can use `css` and `class` attribute on this specific tag.

## Margin Explanation

Here's a little explanation of different margins:

```html
<page backtop="7mm" backbottom="7mm" backleft="10mm" backright="10mm"> 
    <page_header> 
         Page Header 
    </page_header> 
    <page_footer> 
         Page Footer 
    </page_footer> 

    Page Content 
</page> 
```

```php
$pdf = new \Spipu\Html2Pdf\Html2Pdf('P','A4','en', false, 'UTF-8', array(mL, mT, mR, mB)); 
$pdf->writeHTML($htmlContent); 
$pdf->Output(); 
```

![Margins](https://github.com/spipu/html2pdf/blob/master/doc/res/margins.jpg "Margins")


3.Salida
--------

El método principal para usar es `output`.
 
Toma dos parámetros no requeridos.

## Parámetros

Parámetro | Predeterminado | Descripción
--------- | -------------- | -------------
$name | document.pdf | El nombre del archivo cuando se guarda. Tenga en cuenta que los caracteres especiales se eliminan y los caracteres en blanco se reemplazan con el carácter de subrayado.
$ dest | I | Destino donde enviar el documento. Puede tomar uno de los siguientes valores: <ul> <li> I: envía el archivo en línea al navegador (predeterminado). El complemento se usa si está disponible. El nombre dado por nombre se usa cuando se selecciona la opción "Guardar como" en el enlace que genera el PDF. </ Li> <li> D: enviar al navegador y forzar la descarga de un archivo con el nombre indicado por nombre. </ li> <li> F: guardar en un archivo de servidor local con el nombre indicado. </ li> <li> S: devolver el documento como una cadena (se ignora el nombre). </ li> <li> FI: equivalente a la opción F + I </ li> <li> FD: equivalente a la opción F + D </ li> <li> E: devuelve el documento como base64 mime adjunto de correo electrónico de varias partes (RFC 2045) </ li> < / ul>


## Ejemplos

* Enviar PDF al navegador sin especificar un nombre, `$html2pdf->output();`

* Envíe el documento PDF en el navegador con un nombre específico `$html2pdf->output('my_doc.pdf');`

* Forzar la descarga de PDF a través del navegador web, con un nombre específico `$html2pdf->output('my_doc.pdf', 'D');`

* Escriba el contenido de un archivo PDF en el servidor `$html2pdf->output('/absolute/path/file_xxxx.pdf', 'F');`

* Recupere los contenidos del PDF y luego haga lo que quiera `$pdfContent = $html2pdf->output('', 'S');`

Luego, puede enviarlo por correo electrónico, utilizando un documento adjunto de Bin.


