**NOTA** [KnpSnappyBundle]() está basado en [WK<html>TOpdf - Descargas](https://wkhtmltopdf.org/downloads.html)
[WK<html>TOpdf, versión 64bits](https://github.com/wkhtmltopdf/wkhtmltopdf/releases/download/0.12.4/wkhtmltox-0.12.4_msvc2015-win64.exe)

Requisitos Previos
==================

1. Tener Instalado [WK<html>TOpdf](https://wkhtmltopdf.org/)
2. Tener Instalado [Composer]()
3. Disponer de Consola o Terminal.
4. Disponer de un proyectos **Symfony 3**


Es necesario instalar el **Componente de Symfony** [KnpSnappyBundle](https://github.com/KnpLabs/KnpSnappyBundle), para ello lanzaremos dentro de la carpeta del proyecto el comando de consola `composer require knplabs/knp-snappy-bundle`.

```php
// app/AppKernel.php
public function registerBundles()
{
    $bundles = array(
        //...
        /* Cargamos el Bundle que imprimirá en PDF ***************************************/
                new Knp\Bundle\SnappyBundle\KnpSnappyBundle(),
        /*********************************************************************************/
        //...
```

Configuración
=============

Si necesita cambiar los binarios, cambiar las opciones de instancia o incluso desactivar uno o ambos servicios, puede hacerlo a través de la configuración.
```yml
# app/config/config.yml
# KNP_SNAPPY HTML TO PDF
knp_snappy:
    pdf:
        enabled:    true
        binary:     "\"C:\\Program Files\\wkhtmltopdf\\bin\\wkhtmltopdf.exe\"" # for Windows users
    #    binary:     "\"/usr/local/bin/wkhtmltopdf\"" # for linux users        
        #/usr/local/bin/wkhtmltopdf #"\"C:\\Program Files\\wkhtmltopdf\\bin\\wkhtmltopdf.exe\"" for Windows users
        options:    []
    image:
        enabled:    true
        binary:     "\"C:\\Program Files\\wkhtmltopdf\\bin\\wkhtmltoimage.exe\"" # for Windows users
    #    binary:     "\"/usr/local/bin/wkhtmltoimage\"" # for linux users
        #/usr/local/bin/wkhtmltoimage #"\"C:\\Program Files\\wkhtmltopdf\\bin\\wkhtmltoimage.exe\"" for Windows users
        options:    []
```
Accedemos dentro de Windows a **Panel de Control >> Editar las variables de entorno de esta cuenta**.

![Symfony3_pdfBundle_01](https://github.com/HecFranco/Apuntes/blob/master/capture/Symfony3_pdfBundle_01.jpg)

Seleccionamos la opción de **PATH C:\Users\Usuario\App\Local\Micrsosoft\....** y añadimos la ubicación de los archivos de instalación **C:\Program Files\wkhtmltopdf\bin** y guardamos.

![Symfony3_pdfBundle_02](https://github.com/HecFranco/Apuntes/blob/master/capture/Symfony3_pdfBundle_02.jpg)

Ahora si accedemos a la consola y lanzamos el comando `wkhtmltopdf` podremos ver que tenemos instalada la aplicación. Mediante `wkhtmltopdf --version` tendremos información sobre la versión instalada.

![Symfony3_pdfBundle_03](https://github.com/HecFranco/Apuntes/blob/master/capture/Symfony3_pdfBundle_03.jpg)

Si desea cambiar la carpeta temporal que es `sys_get_temp_dir()` de manera predeterminada, puede usar

```yml
# app/config/config.yml
knp_snappy:
    temporary_folder: "%kernel.cache_dir%/snappy"
```

También puede configurar el tiempo de espera utilizado por los generadores con `process_timeout`:

```yml
# app/config/config.yml
knp_snappy:
    process_timeout: 20 # In seconds
```

Uso
===

El paquete registra dos servicios:

* el servicio `knp_snappy.image` le permite generar imágenes;
* el servicio `knp_snappy.pdf` le permite generar archivos pdf.

Genera una imagen desde una URL
-------------------------------
`$container->get('knp_snappy.image')->generate('http://www.google.fr', '/path/to/the/image.jpg');`

Genera un documento pdf desde una URL
-------------------------------------
`$container->get('knp_snappy.pdf')->generate('http://www.google.fr', '/path/to/the/file.pdf');`

Genera un documento pdf desde múltiples URL
-------------------------------------------

`$container->get('knp_snappy.pdf')->generate(array('http://www.google.fr', 'http://www.knplabs.com', 'http://www.google.com'), '/path/to/the/file.pdf');`


Genera un documento pdf desde una vista **TWIG**
------------------------------------------------
```php
$this->get('knp_snappy.pdf')->generateFromHtml(
    $this->renderView(
        'MyBundle:Foo:bar.html.twig',
        array(
            'some'  => $vars
        )
    ),
    '/path/to/the/file.pdf'
);
```

Renderizar una imagen como respuesta de un controlador
------------------------------------------------------

```php
use Knp\Bundle\SnappyBundle\Snappy\Response\JpegResponse;
class SomeController{
    public function imageAction(){
        $html = $this->renderView('MyBundle:Foo:bar.html.twig', array(
            'some'  => $vars
        ));

        return new JpegResponse(
            $this->get('knp_snappy.image')->getOutputFromHtml($html),
            'image.jpg'
        );
    }
}
```

Renderiza un documento pdf como respuesta de un controlador
-----------------------------------------------------------

```php
use Knp\Bundle\SnappyBundle\Snappy\Response\PdfResponse;
class SomeController extends Controller{
    public function pdfAction() {
        $html = $this->renderView('MyBundle:Foo:bar.html.twig', array(
            'some'  => $vars
        ));
        return new PdfResponse(
            $this->get('knp_snappy.pdf')->getOutputFromHtml($html),
            'file.pdf'
        );
    }
}
```

Renderiza un documento pdf con una url relativa adentro como archivos css
-------------------------------------------------------------------------

use Knp\Bundle\SnappyBundle\Snappy\Response\PdfResponse;

class SomeController extends Controller
{
    public function pdfAction()
    {
        $pageUrl = $this->generateUrl('homepage', array(), true); // use absolute path!

        return new PdfResponse(
            $this->get('knp_snappy.pdf')->getOutput($html),
            'file.pdf'
        );
    }
}

EJEMPLOS controlador
====================


```php
<?php
/* Indicamos el namespace del Bundle **************************************************************************/
	namespace AppBundle\Controller;
/* COMPONENTES BÁSICOS DEL CONTROLADOR ************************************************************************/
	use Sensio\Bundle\FrameworkExtraBundle\Configuration\Route;
	use Symfony\Bundle\FrameworkBundle\Controller\Controller;
	use Symfony\Component\HttpFoundation\Request;
	use Symfony\Component\HttpFoundation\Response;
/**************************************************************************************************************/
class PruebasController extends Controller{
	public function pdfAction(Request $request){
		$snappy = $this->get('knp_snappy.pdf');
		$snappy->setOption('encoding','UTF-8');
		return new Response('');
	}
}
```

Método para convertir una web a partir de una url en pdf
--------------------------------------------------------

```php
	public function urlToPdfAction(Request $request){
		$snappy = $this->get('knp_snappy.pdf');
		$filename = 'my_first_pdf_with_snappy';
		// Creamos el PDF desde el propio código de la web
		$webSiteUrl = 'https://www.google.es/';
		return new Response(
			$snappy->getOutPut($webSiteUrl),
			// Stado code OK
			200,
			array(
				'Content-Type'=> 'application/pdf',
				'Content-Disposition'=>'inline; filename="'.$filename.'.pdf"'
			)
		);
	}
```

Método para generar PDF a partir de vista TWIG, y guardarlo
------------------------------------------------------------

```php
	public function twigToPdfAction(Request $request){
		$snappy = $this->get('knp_snappy.pdf');
		$html = $this->renderView(
			// src/AppBundle/Resources/views/Pruebas/pruebas_View_pdf.html.twig			
			'AppBundle:Pruebas:pruebas_View_pdf.html.twig',
			// indicamos las variables de entrada a la plantilla
			array('title'=>'awesome PDF')
		);
		// nombre del archivo pdf que se mostrará
		$filename = 'custom_pdf_from_twig';
		return new Response(
			$snappy->getOutPutFromHtml($html),
			// Stado code OK
			200,
			array(
				'Content-Type'=> 'application/pdf',
				'Content-Disposition'=>'inline; filename="'.$filename.'.pdf"'
			)
		);
	}
```

Método para mostrar PDF a partir de vista TWIG, y mostrarlo
------------------------------------------------------------

```php
	public function twigToPdfFileAction(Request $request){
		$snappy = $this->get('knp_snappy.pdf');
		$snappy->generateFromHtml(
			$this->renderView(
				// src/AppBundle/Resources/views/Pruebas/pruebas_View_pdf.html.twig
				'AppBundle:Pruebas:pruebas_View_pdf.html.twig',
				// indicamos las variables de entrada a la plantilla
				array('title'=>'awesome PDF')
			),
			'file.pdf'// guarda el archivo generado referenciado según la carpeta web
		);
		// necesario un return
	}
```
