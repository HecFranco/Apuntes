-------------------------------------------

SYMFONY 3
=========

-------------------------------------------

INDICE
------
1.[ENTORNO DE DESARROLLO SYMFONY3](#1entorno-de-desarrollo-symfony-3)
  1. [Instalar Composer](#11instalar-composer)
  2. [Instalar CYGWIN](#12instalar-cygwin)
  3. [Instalar NetBeans](#13instalar-netbeans)
  4. [Instalar Symfony3](#14instalar-symfony3)
  5. [Crear hosts virtuales en Apache](#15crear-hosts-virtuales-en-apache)
      1. [Manualmente](#151manualmente)
      2. [Mediante Gestor](#152mediante-gestor)
  6. [Iniciar el Servidor](#16iniciar-el-servidor)
      1. [Aumentar tamaño subida archivos PhpMyAdmin](#161aumentar-tamaño-subida-archivos-phpmyadmin)
  7. [Actualización de aplicaciones Symfony](#17actualización-de-aplicaciones-symfony)
  8. [Cambiar la visualización del entorno (Producción / Desarrollo)](#18cambiar-la-visualización-del-entorno-producción--desarrollo)
      1. [Cambiar entorno (Producción / Desarrollo)](#181cambiar-entorno-producción--desarrollo)
  9. [Clonar Repositorio de un Proyecto](#19clonar-repositorio-de-un-proyecto)

2.[BÁSICOS EN SYMFONY3](#2bÁsicos-en-symfony3)
  1. [¿Qué es un BUNDLE?](#21qué-es-un-bundle)
      1. [¿Cómo generar un nuevo BUNDLE?](#211como--generar-un-nuevo-bundle)
      2. [¿Qué archivos genera un Bundle?](#212qué-archivos-genera-un-bundle)
      3. [¿Cómo afecta a AppKernel.php?](#213cómo-afecta-a-appkernelphp)
      4. [¿Cómo se gestiona el enrutado/mapeado genérico del Bundle?](#214cómo-se-gestiona-el-enrutadomapeado-genérico-del-bundle)
      5. [¿Cómo se gestiona el enrutado/mapeado del bundle?](#215cómo-se-gestiona-el-enrutadomapeado-del-bundle)
  2. [¿Cómo generar una nueva Página estática?](#22cómo-generar-una-nueva-página-estática)
  3. [¿Cómo pasar parámetros por URL?](#23cómo-pasar-parámetros-por-url)
  4. [¿Cómo crear una plantilla para las Vistas?](#24cómo-crear-una-plantilla-para-las-vistas)
      1. [¿Cómo referenciar los recursos externos conectados a nuestras plantillas (Assets)?](#241cómo-referenciar-los-recursos-externos-conectados-a-nuestras-plantillas-assets)

3.[DOCTRINE EN SYMFONY3](#3doctrine-en-symfony3)
  1. [¿Cómo configurar la Base de Datos?](#31cómo-configurar-la-base-de-datos)
  2. [¿Configurar la Base de Datos con UTF8?](#32configurar-la-base-de-datos-con-utf8)
  3. [¿Cómo generamos las tablas dentro de la Base de Datos (Entities)?](#33cómo-generamos-las-tablas-dentro-de-la-base-de-datos-entities)
      1. [¿Cómo actualizar las Entidades (Entities)?](#331cómo-actualizar-las-entidades-entities)

4.[CRUD EN SYMFONY3](#4crud-en-symfony3)
  1. [¿Cómo generamos consultas a la base de datos?](#41cómo-generamos-consultas-a-la-base-de-datos)
      1. [Ejemplo de Consulta Base de Datos](#411ejemplo-de-consulta-a-la-base-de-datos)
      2. [¿Cómo visualizar una página mediante response?](#412cómo-visualizar-una-página-mediante-response)
      3. [¿Cómo usar redirect, generateUrl y createNotFoundException?](#413cómo-visualizar-una-página-mediante-redirect-generateurl-y-createnotfoundexception)
  2. [¿Cómo generar un CRUD?](#42cómo-generar-un-crud)
      1. [¿Cómo insertar datos en la Base de Datos?](#421cómo-insertar-datos-en-la-base-de-datos)
      2. [¿Cómo buscar registro por su id en la Base de Datos?](#422cómo-buscar-registro-por-su-id-en-la-base-de-datos)
      3. [¿Cómo buscar registro por su nombre en la Base de Datos?](#423cómo-buscar-registro-por-su-nombre-en-la-base-de-datos)

5.[FORMULARIOS EN SYMFONY3](#5formularios-en-symfony3)
  1. [Creación de Formularios](#51creación-de-formularios)
  2. [Tipos de datos en los Formularios](#52tipos-de-datos-en-los-formularios)
  3. [Opciones de datos de Formularios](#53opciones-de-datos-de-formularios)

6.[RELACIONES ENTRE TABLAS EN SYMFONY3](#6relaciones-entre-tablas-en-symfony3)
  1. [Tipos de Relaciones](#61tipos-de-relaciones)
  2. [Relaciones entre Tablas](#62relaciones-entre-tablas)

7.[MOTOR DE CREACIÓN DE PLANTILLAS TWIG EN SYMFONY3](#7motor-de-creación-de-plantillas-twig-en-symfony3).
  1. [¿Qué es Twig?](#71qué-es-twig)
  2. [Tags](#72tags)
      1. [¿Cómo usar IF?](#721cómo-usar-if).
      2. [¿Cómo usar FOR?](#722cómo-usar-for)
      3. [¿Cómo usar los Tags/Bloques?](#723cómo-usar-los-tagsbloques).
  3. [¿Cómo realizar Rutas definiendo idiomas?](#73cómo-realizar-rutas-definiendo-idiomas).

8.[Objeto Request](#8objeto-request)

9.[Security.yml]()

[EXTRA - Resumen de Comandos Consola para Symfony 3](#extra---resumen-de-comandos-consola-para-symfony3)

[EXTRA - Página NotFound. Error404](#extra---pÁgina-notfound-error404)

[EXTRA - Registro de Usuarios](#extra---registro-de-usuarios)
  1. [¿Cómo crear la entidad User?](#1cómo-crear-la-entidad-user)
  2. [¿Cómo modificar la entidad User Cambios Básicos?](#2cómo-modificar-la-entidad-user-cambios-básicos)
      1. [¿Cómo modificar la entidad User, '$plainPassword' ?](#21-cómo-modificar-la-entidad-user-plainpassword-)
      2. [¿Cómo modificar la entidad User, métodos extra necesarios?](#22-cómo-modificar-la-entidad-user-métodos-extra-necesarios)
  3. [¿Cómo crearemos validaciones?](#3cómo-crearemos-validaciones)
  4. [¿Cómo crearemos el Formulario?](#4cómo-crearemos-el-formulario)
  5. [¿Cómo modificar el controlador?](#5cómo-modificar-el-controlador)

----------------------------------

1.ENTORNO DE DESARROLLO SYMFONY3
================================

1.1.Instalar Composer
----------------------

Composer es un manejador de dependencias. Composer es un manejador de dependencias, no un gestor de paquetes. Pero es cierto que trata con paquetes y librerías, la instalación siempre es local para cualquier proyecto, las librerías se instalan en un directorio por defecto (normalmente es /vendor).
* Entramos dentro de dominio de [Composer](https://getcomposer.org/download/) y buscamos el link de descarga de su [setup](https://getcomposer.org/Composer-Setup.exe).
* Durante la instalación habrá que indicar la ubicación del ejecutable **PHP** del servidor local. En este caso al usar **Wamp64** es: ```C:\wamp64\bin\php\php7.0.10\php.exe```.
* Para comprobar que se instaló correctamente hay que introducir dentro de la terminal el comando ```composer -v```, este nos devolverá información sobre la versión instalada de **Composer**.

Para comporbar que [Composer](https://getcomposer.org/download/) se ha instalado correctamente entramos en la terminal de windows (**CMD**), de MAC o Linux y escribimos el comando `composer -v`.

| [Volver al inicio del capítulo](#1entorno-de-desarrollo-symfony3) | [Ver índice](#indice) |
|-------------------------------------------------------------------|-----------------------|


1.2.Instalar CYGWIN
-------------------

Cygwin es una colección de herramientas desarrollada por Cygnus Solutions para proporcionar un comportamiento similar a los sistemas Unix en Microsoft Windows. Su objetivo es portar software que ejecuta en sistemas POSIX a Windows con una recompilación a partir de sus fuentes.
*Nota: terminal tiene toda la potencia de la terminal de Linux pero simulada en Windows.*

* Entramos en el dominio de [CygWin](https://www.cygwin.com/) y buscamos el link de descarga de su [setup](https://cygwin.com/setup-x86_64.exe).
* Se instalará la consola dentro de la carpeta que propone por defecto ```C:\CygWin64\```. En cambio si habrá que indicar dónde se instalaran los **Package**, se recomienda dentro de: ```C:\Cygwin_Packages\```.
* Acontinuación se indicarán los paquetes que más podrían interesarnos instalar (todos instalados usando Bin):
  * *GIT -> Devel Default -> git: Distributed version control system*.
  * *SSH -> Net Default -> opnssh: The Open SSH server and client programs*.
  * *NANO -> Editors Default -> nano: Enhanced clone of Pico editor*.
  * *WGET -> Web Default -> wget: Utility to retrieve files from the WWW via HTTP and FTP*.
Para comprobar el correcto funcionamiento ejecutamos **Cygwin64**, y dentro de la consola escribimos `git -v`, `git --version`, `ssh -v`, `nano -v`,...

| [Volver al inicio del capítulo](#1entorno-de-desarrollo-symfony3) | [Ver índice](#indice) |
|-------------------------------------------------------------------|-----------------------|

1.3.Instalar NetBeans
---------------------
NetBeans es un entorno de desarrollo integrado libre, hecho principalmente para el lenguaje de programación Java. Existe además un número importante de módulos para extenderlo. NetBeans IDE es un producto libre y gratuito sin restricciones de uso.

| [Volver al inicio del capítulo](#1entorno-de-desarrollo-symfony3) | [Ver índice](#indice) |
|-------------------------------------------------------------------|-----------------------|

1.4.Instalar Symfony3
---------------------
* Ejecutamos la consola de **CygWin** o **CMD** para windows.
* Accederemos a la carpeta del servidor local escribiendo: ```cd c:\wamp64\www```.
* Una vez dentro de la carpeta dónde queremos iniciar el proyecto (se encontrará dentro del servidor web **Wamp**) ejecutamos (*Ver documentación oficial [aquí](http://symfony.com/doc/current/setup.html#creating-symfony-applications-with-composer)*):

```composer create-project symfony/framework-standard-edition my_project_name```

Para instalar una versión en concreto de symfony ejecutaremos:

```composer create-project symfony/framework-standard-edition my_project_name/ "3.0.0"```.

*Nota<sup>1</sup>* La primera ubicación indica el directorio desde dónde se recogen los archivos de symfony, es decir dónde se instaló inicialmente. En cambio la segunda ubicación definirá dentro del directorio de ejecución la carpeta dónde se ubicará el proyecto. La parte dónde se escribe `"3.0.0"` especificará la versión de symfony que desea instalarse.

* Después mostrará un asistente de configuración dónde se indicará:

```
database_host (127.0.0.1):    /     /dirección ip del servidor
database_port (null):               // puerto
database_name (symfony): pruebas    //nombre de la base de datos
database_user (root):
database_password (null):
...
```

*Nota<sup>2</sup>* si entramos en la siguiente url `http://localhost/symfony/web/config.php` se comprobará la configuración de la instalación. Si por alguna razón hubiera problemas es en esta dirección dónde se mostrará dicho error.

*Nota<sup>3</sup>* **Modificar php.ini**: *Dentro del archivo: `C:\wamp64\bin\apache\apache2.4.23\bin\php.ini` colocar debajo de `intl.error_level = E_WARNING` la línea `intl.error_level = 0`. Y colocar debajo de la directiva `xdebug.show_local_vars=0` esta otra `xdebug.max_nesting_level=250`*.

*Nota<sup>4</sup>* Se creará un proyecto nuevo con dicha configuración dentro de una carpeta con el nombre del proyecto indicado.
```
c:/>
c:/>cd wamp64
c:/wamp64>cd www
c:/wamp64/www>composer create-project symfony/framework-standard-edition micms
c:/wamp64/www>dir
 El volumen de la unidad C es OS
 El número de serie del volumen es: 204B-0ACF

 Directorio de C:\wamp64\www\micms

11/09/2017  17:45    <DIR>          .
11/09/2017  17:45    <DIR>          ..
11/09/2017  17:42    <DIR>          micms
```
Una vez hechos los cambios anteriores, podemos acceder a la siguiente dirección: `http://localhost/symfony/web/`

--------------------------------------------------------

| [Volver al inicio del capítulo](#1entorno-de-desarrollo-symfony3) | [Ver índice](#indice) |
|-------------------------------------------------------------------|-----------------------|

1.5.Crear hosts virtuales en Apache
-----------------------------------

1.5.1.Manualmente
-----------------

IMPORTANTE: SIEMPRE TENER EL MODULO REWRITE DE APACHE ACTIVADO

**AVISO: Esto es opcional, no es necesario que lo hagas para seguir el curso **

Cuando creamos un virtualhost lo que estamos haciendo es simular en nuestro servidor apache local un dominio real, de forma que en lugar de entrar a [http://localhost/symfony3/web](http://localhost/symfony3/web) entraríamos a [http://symfony3.com.devel](http://symfony3.com.devel).

Vamos a ver como se crean los virtualhost en WampServer, aunque esto es muy similar en cualquier versión de Apache.

**Paso 1.** Entrar al fichero `C:\wamp64\bin\apache\apache2.4.9\conf\httpd.conf` y añadir o descomentar el include del fichero de los hosts virutales:

```php
Include conf/extra/httpd-vhosts.conf
```


**Paso 2.** Entrar al fichero `C:\wamp64\bin\apache\apache2.4.9\conf\extra\httpd-vhosts.conf` y añadir los virtualhosts, en mi caso voy a crear 3 nuevos virtualhosts, uno para localhost, otro para un proyecto de Zend Framework 2 y otro para un proyecto de Symfony 3.

```php
# LOCALHOST
<VirtualHost *:80>
    ServerAdmin webmaster@localhost
    DocumentRoot "c:/wamp/www"
    ServerName localhost
    ErrorLog "logs/localhost-error.log"
    CustomLog "logs/localhost-access.log" common
</VirtualHost>
# VHOST CURSO ZF2
<VirtualHost *:80>    
    DocumentRoot "c:/wamp/www/zend2/public"
    ServerName zend2.com.devel
    ServerAlias www.zend2.com.devel
    <Directory "c:/wamp/www/zend2/public">
        Options Indexes FollowSymLinks        
        AllowOverride All
        Order Deny,Allow
        Allow from all        
    </Directory>    
</VirtualHost>
# VHOST CURSO SYMFONY 3
<VirtualHost *:80>    
    DocumentRoot "c:/wamp/www/symfony3/web
    ServerName symfony3.com.devel
    ServerAlias www.symfony3.com.devel
    <Directory "c:/wamp/www/symfony3/web">
        Options Indexes FollowSymLinks        
        AllowOverride All
        Order Deny,Allow
        Allow from all        
    </Directory>    
</VirtualHost>
```

**Paso 3.** Añadir al fichero hosts de nuestro sistema, en el caso de Windows `C:\Windows\System32\drivers\etc\hosts` (si estas en Windows 8 o 10 ejecuta el programa de edición de código como Administrador para poder guardar los cambios), y añadir las IP y las url.
```
127.0.0.1    localhost
127.0.0.1    zend2.com.devel
127.0.0.1    symfony3.com.devel
Lo que le estamos indicando es que cuando carguemos cualquiera de esos dominios nos llame a la IP que le indicamos en este caso 127.0.0.1 en lugar de la IP original del dominio si es que la tiene.
```
Ahora si entramos a [http://symfony3.com.devel](http://symfony3.com.devel) nos abrirá la web que tenemos en nuestro directorio www.

--------------------------------------------------------

| [Volver al inicio del capítulo](#1entorno-de-desarrollo-symfony3) | [Ver índice](#indice) |
|-------------------------------------------------------------------|-----------------------|

1.5.2.Mediante Gestor
---------------------

* Creamos dentro de *c:/wamp64/www/* una carpeta con el nombre del dominio virtual.
* Dentro de localhost selecionamos la opción de **Add a Virtual Host**.
* Indicamos el nombre del dominio en **Name of the Virtual Host**, la ubicación del dominio en **Complete absolute path of the VirtualHost folder Examples: C:/wamp/www/** y pulsamos en **Start the creation**.

--------------------------------------------------------

| [Volver al inicio del capítulo](#1entorno-de-desarrollo-symfony3) | [Ver índice](#indice) |
|-------------------------------------------------------------------|-----------------------|

1.6.Iniciar el Servidor
-----------------------

Para iniciar el servidor de **symfony** es necesario acceder al directorio del proyecto (`cd my_project_name/`) y posteriormente escribir dentro de la consola (CMD o CygWin) el comando `php bin/console server:run` dentro de la carpeta del proyecto de symfony (*Ver documentación oficial [aquí](http://symfony.com/doc/current/setup.html#running-the-symfony-application)*).

```
cd my_project_name/
php bin/console server:run
```

------------------------------------------------------------

*Nota<sup>1</sup>*: Este comando invocará el método `server:run`dentro del archivo `bin/console` que se encuentra dentro del proyecto *Symfony*.

*Nota<sup>2</sup>*: **Comprobación de la configuración y la configuración de Symfony**

```
http://localhost:8000/config.php
```

------------------------------------------------------------

| [Volver al inicio del capítulo](#1entorno-de-desarrollo-symfony3) | [Ver índice](#indice) |
|-------------------------------------------------------------------|-----------------------|

1.6.1.Aumentar tamaño subida archivos PhpMyAdmin
------------------------------------------------

| XAMPP | Modificar dentro de **php.ini** los límites de la opción `max_execution_time` (tiempo de ejecución), `upload_max_filesize` (tamaño máximo de subida por archivo) y `post_max_size` (tamaño máximo de subida en la base de datos total). |
|:------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|

------------------------------------------------------------

| [Volver al inicio del capítulo](#1entorno-de-desarrollo-symfony3) | [Ver índice](#indice) |
|-------------------------------------------------------------------|-----------------------|

1.7.Actualización de aplicaciones Symfony
-----------------------------------------

En este momento, ha creado una aplicación Symfony completamente funcional. Cada aplicación de Symfony depende de varias bibliotecas de terceros almacenadas en el directorio de proveedores y administradas por [Composer](https://getcomposer.org/download/).

Actualizar esas bibliotecas con frecuencia es una buena práctica para prevenir errores y vulnerabilidades de seguridad. Ejecute el comando update Composer para actualizarlos todos a la vez (puede tardar varios minutos en completarse según la complejidad de su proyecto): (*Ver documentación oficial [aquí](http://symfony.com/doc/current/setup.html#updating-symfony-applications)*).

```
cd my_project_name/
composer update
```

------------------------------------------------------------

*Nota*: Symfony proporciona un mandato para comprobar si las dependencias del proyecto contienen alguna vulnerabilidad de seguridad conocida:

```
php bin/console security:check
```

Una buena práctica de seguridad es ejecutar este comando regularmente para poder actualizar o reemplazar dependencias comprometidas lo antes posible.

------------------------------------------------------------

| [Volver al inicio del capítulo](#1entorno-de-desarrollo-symfony3) | [Ver índice](#indice) |
|-------------------------------------------------------------------|-----------------------|

1.8.Cambiar la visualización del entorno (Producción / Desarrollo)
------------------------------------------------------------------

Podemos cambiar la visualización del entorno a **Producción** o **Desarrollo** simplemente añadiendo detras del dominio que usemos **app.php** (para *producción*) o **app_dev.php** (para *desarrollo*) (Ver documentación oficial [aquí](http://symfony.com/doc/current/configuration/environments.html)) Usando el servidor local desde consola mediante el comando `php bin/console server:run` sería:
* **127.0.0.1:8000/app.php** para producción
* **127.0.0.1:8000/app_dev.php** para desarrollo

Ejemplo:
* **127.0.0.1:8000/app.php/prueba/prueba** para producción
* **127.0.0.1:8000/app_dev.php/prueba/prueba** para desarrollo

------------------------------------------------------------

| [Volver al inicio del capítulo](#1entorno-de-desarrollo-symfony3) | [Ver índice](#indice) |
|-------------------------------------------------------------------|-----------------------|

1.8.1.Cambiar entorno (Producción / Desarrollo)
-----------------------------------------------

(Ver documentación oficial [aquí](http://symfony.com/doc/current/configuration/environments.html)) Para cambiar el entorno es necesario realizar modificaciones en los archivos **web\app.php** y **web\app_dev.php**, tal que así:

| Entorno        | **web\app.php**                           | **web\app_dev.php**                      |
|----------------|-------------------------------------------|------------------------------------------|
| **Desarrollo** | `$kernel = new AppKernel('prod', false);` | `$kernel = new AppKernel('dev', true);`  |
| **Producción** | `$kernel = new AppKernel('prod', true);`  | `$kernel = new AppKernel('dev', false);` |

Además hay que tener en cuenta mientras se usa el entorno de **desarrollo** la correcta configuración del **debugging**

* Activar las notificaciones de **Debugging**

| **web\app_dev.php** |
|---------------------|

```php
/* Extracto de código */
Debug::enable();
/* Fin del Extracto de código */
```

* Carga de los componentes de **Debugging**

| **app\AppKernel.php** |
|-----------------------|

```php
/* Extracto de código */
        if (in_array($this->getEnvironment(), ['dev', 'test'], true)) {
            $bundles[] = new Symfony\Bundle\DebugBundle\DebugBundle();
            $bundles[] = new Symfony\Bundle\WebProfilerBundle\WebProfilerBundle();
            $bundles[] = new Sensio\Bundle\DistributionBundle\SensioDistributionBundle();

            if ('dev' === $this->getEnvironment()) {
                $bundles[] = new Sensio\Bundle\GeneratorBundle\SensioGeneratorBundle();
                $bundles[] = new Symfony\Bundle\WebServerBundle\WebServerBundle();
            }
        }
/* Fin del Extracto de código */
```

------------------------------------------------------------

| [Volver al inicio del capítulo](#1entorno-de-desarrollo-symfony3) | [Ver índice](#indice) |
|-------------------------------------------------------------------|-----------------------|

1.9.Clonar Repositorio de un Proyecto
-------------------------------------

Cuando se trabaja de forma colaborativa en una aplicación Symfony, es poco frecuente crear una nueva aplicación Symfony tal como se explica en las secciones anteriores. En su lugar, alguien más ya lo ha creado y enviado a un repositorio compartido.

Se recomienda no enviar algunos archivos (`parameters.yml`) y directorios (`vendor /`, `cache`, `logs`) al repositorio, por lo que tendrá que hacer lo siguiente al instalar una aplicación Symfony existente:

```
 cd projects/
 git clone ...
```

Dónde detrás de `git clone` inclluiríamos la url del repositorio a clonar. (Ver documentación oficial [aquí](https://symfony.com/doc/current/setup.html))

| [Volver al inicio del capítulo](#1entorno-de-desarrollo-symfony3) | [Ver índice](#indice) |
|-------------------------------------------------------------------|-----------------------|

----------------------------------

| **IMPORTANTE!!**|
|-----------------|

En caso de no recordar los comandos existentes con `php bin/console` sólo es necesario teclear ese mismo comando (`php bin/console`) dentro de la consola para poder ver el listado completo de comandos existentes.

----------------------------------

2.BASICOS SYMFONY3
===================

2.1.Estructura del Framework
----------------------------

**app/** La configuración de la aplicación, plantillas y traducciones.
**bin/** Archivos ejecutables (por ejemplo, bin / console).
**src/** El código PHP del proyecto.
**tests/** Pruebas automáticas (por ejemplo, pruebas unitarias).
**var/** Archivos generados (caché, registros, etc.).
**vendor/** Las dependencias de terceros.
**web/** El directorio raíz web.

| [Volver al inicio del capítulo](#2basicos-symfony3) | [Ver índice](#indice) |
|-----------------------------------------------------|-----------------------|

2.2.Hello World!!
-----------------

Incluiremos dentro de **src\AppBundle\Controller\DefaultController\** el siguiente código. Este incluirá una nueva función denominada **helloWorldAction()** que se activará mediante la ruta url **/hello-world** definida mediante **Anotación**.

```php
<?php
// src\AppBundle\Controller\DefaultController\

public function indexAction(Request $request){...}
/* Extracto de código */

// Definimos la ruta mediante Anotación
/**
 * @Route ("/hello-world", name="helloWorld")
 */
public function helloWorldAction(){
  echo "<h1>Hola Mundo!!"</h1>
  die();
}
```

Para acceder a visualizarlo habrá que tener iniciado el servidor dentro de la consola, mediante el comando `php bin/console server:run`, para posterioemnete escribir en el navegador **127.0.0.1:8000/app_dev.php/hello-world**.

Para usar la ruta normal accederemos dentro de **web\app.php** y colocaremos en `true` la siguiente línea de código `$kernel = new AppKernel('prod', false);`. Este cambio permitirá que la aplicación funcione tanto desde **127.0.0.1:8000/app_dev.php/hello-world** como desde **127.0.0.1:8000/hello-world**.

| [Volver al inicio del capítulo](#2basicos-symfony3) | [Ver índice](#indice) |
|-----------------------------------------------------|-----------------------|

2.3.Rutas básicas, Controladores y Vistas
-----------------------------------------

Crearemos un nuevo controlador dentro de **src\Controller\PruebasController.php** con el siguiente código.
**Controlador**
```php
<?php
// src\Controller\PruebasController.php
namespace AppBundle\Controller;

use Sensio\Bundle\FrameworkExtraBundle\Configuration\Route;
use Symfony\Bundle\FrameworkBundle\Controller\Controller;
use Symfony\Component\HttpFoundation\Request;

/*
 * La clase deberá tener el mismo nombre del archivo seguido de Controller,
 * además de extender de la clase Controller
 */
class PruebasController extends Controller
{
    // Indicamos los parámetros que recibiremos en la función
    public function indexAction(Request $request, $lang, $name, $surname, $page)
    {
        // Indicaremos que la vista se encuentra dentro de src\AppBundle\Resources\views\index.html.twig
        return $this->render('AppBundle:Pruebas:index.html.twig', array(
            /*
             * enviamos a la vista la variable 'Texto' que incluye las dos
             * variables de entrada a la función
             */
            'Texto' => $name." ".$surname." - ".$page
          ));
    }
}
```
**Plantilla**
```twig
{# src\AppBundle\Resources\views\index.html.twig #}
{# Imprimimos la variable 'Texto' que hemos pasado a la vista#}
{{Texto}}
```
**Routing yml global**
```yml
# app\config\routing.yml
rutas_bundle:
    resource: "@AppBundle/Resources/config/routing.yml"
    prefix: /
```
Dentro del **Routing yml específico** incluimos:
* la url de destino `path`
* el controlador `defaults` junto a sus variables con valores predefinidos
* el método de traspaso de información o variables
* los requerimientos, incluidas las **Expresiones regulares** tales como `"[a-zA-Z]*"`.
```yml
# src\AppBundle\Resources\config\routing.yml
pruebas_index:
    # Pasamos a través de la url los parámetros {name} y {surname}
    path: /pruebas/{lang}/{name}/{surname}
    # Junto al controlador, indicamos el valor por defecto que tendrá la variable $surname
    defaults: { _controller: AppBundle:Pruebas:index, lang: es,surname:robles, page:1 }
    # Además podemos indicar el método que usaremos
    methods: [GET]
    # Podemos añaidr unos requerimientos también a la ruta
    requeriments:
        # Name incluirá sólo letras
        name: \w+
        # Surname sólo incluirá letras mayúsculas y minúsculas
        surname: "[a-zA-Z]*"
        # Page incluirá sólo números
        page: \d+
        # Lang (idioma) sólo podrá ser español, inglés o francés.
        lang: es|en|fr
```

| [Volver al inicio del capítulo](#2basicos-symfony3) | [Ver índice](#indice) |
|-----------------------------------------------------|-----------------------|

2.4. Redirecciones
------------------

En el siguiente ejemplo vemos como podemos gestionar las redirecciones dentro de Symfony3.

Existen dos modos de hacerlo:
* `return $this->redirect($this->generateUrl("homepage"));` nos redireccionará a la ruta definida dentro de 'src\AppBundle\Controller\DefaultController\' mediante anotación como "helloWorld".
* otra opción sería `return $this->redirect($this->generateUrl("pruebas_index"));` definida dentro del routing **src\AppBundle\Resources\config\routing.yml** como "pruebas_index".
* mediante `return $this->redirect("pruebas/en/victor/manuel");` que nos redireccionará a una url directamente y sin que esta haya sido definida anteriormente.
* Cuando trabajemos en local habrá que utilizar el siguiente código para poder capturar el dominio desde el cual se trabaja, `return $this->redirect($this->container->get("router")->getContext()->getBaseUrl()."/hello-wolrd?hola=true");`, o usando la opción `return $this->redirect($request->getBaseUrl()."/hello-wolrd?hola=true");`.

```php
<?php
// src\Controller\PruebasController.php

class PruebasController extends Controller
{
    public function indexAction(Request $request, $lang, $name, $surname, $page)
    {
        /* Extracto de código */
        // el siguiente código nos redireccionará a "helloWorld" definida dentro de 'src\AppBundle\Controller\DefaultController\'
        return $this->redirect($this->generateUrl("homepage"));
        // para redireccionar a una url no predefinida dentro del ningun routing usaremos el siguiente método.
        return $this->redirect("pruebas/en/victor/manuel");
```

| [Volver al inicio del capítulo](#2basicos-symfony3) | [Ver índice](#indice) |
|-----------------------------------------------------|-----------------------|

2.5.Recoger variables GET y POST
--------------------------------

* Dentro del enrutador **src\PruebaBundle\Resources\config\routing.yml** indicaremos los parámetros que recibiremos, tal que así:

| src\PruebaBundle\Resources\config\routing.yml |
|-----------------------------------------------|

```yml
prueba_nombre:
    # {nPila} indica el nombre del parámetro a recibir 'nPila'
    path:     /nombre/{nPila}
    # colocando ,nPila:'Manolo' decimos que el valor por defecto será 'manolo'
    defaults: { _controller: PruebaBundle:Default:nombre,nPila:'Manolo' }
```

* Dentro del controlador **src\PruebaBundle\Controller\DefaultController.php** indicaremos los parámetros que enviaremos, tal que así:

| src\PruebaBundle\Controller\DefaultController.php |
|---------------------------------------------------|

```php
<?php

namespace PruebaBundle\Controller;

use Symfony\Bundle\FrameworkBundle\Controller\Controller;

class DefaultController extends Controller
{
    public function nombreAction($nPila)
    {
    // llama a una vista que se llama por defecto nombre.html.twig
        return $this->render('PruebaBundle:Default:nombre.html.twig', array('nPila'=>$nPila));
    }
}
```

* Dentro de la vista **src\PruebaBundle\Resources\views\Default\nombre.html.twig** mostraremos la variable, tal que así:

| src\PruebaBundle\Resources\views\Default\nombre.html.twig |
|-----------------------------------------------------------|

```twig
<h2>Estamos dentro de la página de nombres</h2>
<br>
{{nPila}}
```

| [Volver al inicio del capítulo](#2basicos-symfony3) | [Ver índice](#indice) |
|-----------------------------------------------------|-----------------------|

---------------------------------------------------------------------------------------------------------------

**EXTRA**

Para pasar variable por método **POST** o **GET**, es necesario indicarlo dentro del archivo **routing** que gestione el enrutamiento a través del cual se enviará mediante `methods: [POST]`, `method: [GET]` o `method: [GET, POST]`.
Usando **GET**, sería usando la url por ejemplo **localhost/symfony3/web/pruebas/es/victor/23?hola=contenido**, y el comando `var_dump($request->query->get("hola"));` para verla reflejada en pantalla.
```php
Captaría url como localhost/symfony3/web/pruebas/es/victor/23?hola=contenido
var_dump($request->query->get("hola"));
die();
```

En cambio para el método **POST**
```php
Captaría url como localhost/symfony3/web/pruebas/es/victor/23?hola=contenido
var_dump($request->query->get("hola"));
die();
```

Si usasemos por ejemplo `var_dump($request->get("hola-post"));` extraería cualquier variable independientemente del método usado.

---------------------------------------------------------------------------------------------------------------

2.6.¿Qué es un BUNDLE?
----------------------

Un bundle es como un plugin en cualquier otro software. En Symfony todo es un bundle, desde el núcleo del framework hasta el código que escribes para tu aplicación. Un bundle es un conjunto estructurado de archivos (PHP, CSS, JavaScript, imágenes...) que implementan una funcionalidad individual (un blog, un foro...) y que se puede compartir con otros desarrolladores.

Los bundles permiten la flexibilidad de poder usar funcionalidades de bundles de terceros o distribuir tus propios bundles, así puedes optimizar tu aplicación de la forma que quieras.

| [Volver al inicio del capítulo](#2basicos-symfony3) | [Ver índice](#indice) |
|-----------------------------------------------------|-----------------------|

2.6.1.¿Como  generar un nuevo BUNDLE?
-----------------------------------

Existe un comando para generar el skeleton de un bundle básico,

`php bin/console generate:bundle`

El skeleton genera un controlador básico, template y routing resource que pueden customizarse.

Es importante recordar que siempre que se crea un nuevo bundle o se usa uno de un tercero hay que registrarlo en `registerBundles()`. Cuando se usa el comando esto se hace automáticamente.

Otra opción es usar por ejemplo el siguiente comando de consola, `php bin/console generate:bundle --namespace=PruebaBundle --format=yml` en el cual indicamos el **namespace** que se usará para el nuevo bundle y su tipo de enrutamiento **yml**.

-------------------------------------------------------------

| *Nota* | Se recomienda usar los nombres en **CamelCase**. |
|--------|--------------------------------------------------|

-------------------------------------------------------------

* **Are you planning on sharing this bundle across multiple applications? [no]:** (¿Está planeando compartir este paquete en varias aplicaciones?)
* **Give your bundle a descriptive name, like BlogBundle. Bundle name [PruebaBundle]:** (Dé a su paquete un nombre descriptivo, como BlogBundle. Nombre del paquete [PruebaBundle]:)
* **Target Directory [src/]:** (Carpeta dónde se alojará)
* **Configuration format (annotation, yml, xml, php) [yml]:** (Formato de configuración (anotación, yml, xml, php) [anotación]:) (Se recomienda usar **yml**)

-------------------------------------------------------------

| **Ejemplo de Bundle** |
|:----------------------|
| **Are you planning on sharing this bundle across multiple applications? [no]:**       | no           |
| **Give your bundle a descriptive name, like BlogBundle. Bundle name [BlogBundle]:**   | PruebaBundle |
| **Target Directory [src/]:**                                                          | src/         |
| **Configuration format (annotation, yml, xml, php) [annotation]:**                    | yml          |

-------------------------------------------------------------

| [Volver al inicio del capítulo](#2basicos-symfony3) | [Ver índice](#indice) |
|-----------------------------------------------------|-----------------------|

---------------------------------------------------------

| **POSIBLE FALLO SYMFONY 3.3** |
|-------------------------------|

Puede dar error al ejecutarlo, lanzando el siguiente mensaje **Fatal error: Class 'PruebaBundle' not found in C:\wamp64\www\symfony.test\app\AppKernel.php on line 19** (Ver hilo con solución, [aquí](https://stackoverflow.com/questions/17584041/class-not-found-in-appkernel-php)).

En este caso el error se encontraba dentro de **C:\wamp64\www\symfony.test\composer.json**, dónde había que modificar la siguiente línea

* Dentro de **C:\wamp64\www\symfony.test\composer.json**, buscamos:

```php
"autoload": {
        "psr-4": {
            "AppBundle\\": "src/AppBundle",
            "": "src/"
        },
        "classmap": [ "app/AppKernel.php", "app/AppCache.php" ]
    }
```

y lo sustituimos por:

```php
"autoload": {
        "psr-4": {
            "": "src/"
        },
        "classmap": [ "app/AppKernel.php", "app/AppCache.php" ]
    }
```

| **MUY IMPORTANTE** | ejecutar `composer dump-autoload` para ejecutar la función **autoload**. |                           
|--------------------|--------------------------------------------------------------------------|

---------------------------------------------------------

| [Volver al inicio del capítulo](#2basicos-symfony3) | [Ver índice](#indice) |
|-----------------------------------------------------|-----------------------|

2.6.2.¿Qué archivos genera un Bundle?
-------------------------------------

* Afecta declarándose dentro de **app\appKernel.php**, como `new PruebaBundle\UserBundle(),`, y **app\config\appKernel.php**, como `{ resource: "@PruebaBundle/Resources/config/services.yml" }`.
* Modifica **app\config\routing.yml** indica la ubicación del enrutador del Bundle.
* Crea **src\PruebaBundle\Resources\config\routing.yml** para gestionar el enrutamiento/ mapeado de la aplicación.
```yml
user:
    resource: "@PruebaBundle/Resources/config/routing.yml"
    prefix:   /
```
* Crea un controlador para gestionar la aplicación mediante sus métodos **src\PruebaBundle\Controller\DefaultController.php**
* Genera una nueva vista **src\PruebaBundle\Resources\views\Default\index.html.twig**

Se creará dentro de la carpeta del proyecto src una carpeta que contiene el bundle **Prueba** y así mismo la aplicación PruebaBundle, tal que así **src\PruebaBundle**. Dentro del mismo existirán tres carpetas (controller, Resources, Tests) más el archivo **src\PruebaBundle\PruebaBundle.php**.

------------------------------------------------------------

| [Volver al inicio del capítulo](#2basicos-symfony3) | [Ver índice](#indice) |
|-----------------------------------------------------|-----------------------|

2.6.3.¿Cómo afecta a **appKernel.php**?
---------------------------------------

Se habrán registrado dentro del sistema la existencia del nuevo bundle, dentro de **app\appKernel.php**

| app\appKernel.php |
|-------------------|

```php
<?php

use Symfony\Component\HttpKernel\Kernel;
use Symfony\Component\Config\Loader\LoaderInterface;

class AppKernel extends Kernel
{
    public function registerBundles()
    {
        $bundles = [
            new Symfony\Bundle\FrameworkBundle\FrameworkBundle(),
            new Symfony\Bundle\SecurityBundle\SecurityBundle(),
            new Symfony\Bundle\TwigBundle\TwigBundle(),
            new Symfony\Bundle\MonologBundle\MonologBundle(),
            new Symfony\Bundle\SwiftmailerBundle\SwiftmailerBundle(),
            new Doctrine\Bundle\DoctrineBundle\DoctrineBundle(),
            new Sensio\Bundle\FrameworkExtraBundle\SensioFrameworkExtraBundle(),
            new AppBundle\AppBundle(),
            new PruebaBundle\PruebaBundle(),
        ];
// Continúa el archivo
```

------------------------------------------------------------

| [Volver al inicio del capítulo](#2basicos-symfony3) | [Ver índice](#indice) |
|-----------------------------------------------------|-----------------------|

2.6.4.¿Cómo se gestiona el enrutado/mapeado genérico del Bundle?
----------------------------------------------------------------

Con el comando de consola `php bin/console generate:bundle` que generó el nuevo bundle se habrá creado un enrutador el cual estará referenciado dentro del archivo **app\config\routing.yml**, tal que así

| app\config\routing.yml |
|------------------------|

```yml
prueba:
    resource: "@PruebaBundle/Resources/config/routing.yml"
    prefix:   /

prueba2:
    resource: "@Prueba2Bundle/Resources/config/routing.yml"
    prefix:   /prueba

app:
    resource: '@AppBundle/Controller/'
    type: annotation
```

------------------------------------------------------------

| [Volver al inicio del capítulo](#2basicos-symfony3) | [Ver índice](#indice) |
|-----------------------------------------------------|-----------------------|

2.6.5.¿Cómo se gestiona el enrutado/mapeado del bundle?
-------------------------------------------------------

Aún así el enrutador que se empleará para este plugin será **src\PruebaBundle\Resources\config\routing.yml**, el cual se indicó anteriormente.

| src\PruebaBundle\Resources\config\routing.yml |
|-----------------------------------------------|

```yml
prueba_homepage:
    path:     /
    defaults: { _controller: PruebaBundle:Default:index }
```

Podremos modificar el archivo **routing.yml** por este otro.

| src\PruebaBundle\Resources\config\routing.yml |
|-----------------------------------------------------------|

```yml
prueba_hola_mundo:
    # Indicamos la url 'midominio.es/holamundo'
    path:     /holamundo
    # Defaults -> Apunta a la clase del controlador señalado
    # utilizaremos la siguiente estructura:
    # _controller: nombredelbundle:nombredelcontrolador:clase
    defaults: { _controller: PruebaBundle:Default:index }
```

---------------------------------------

*Nota*: **app\config\routing.yml** define la ruta madre de cada **Bundle** es decir, si fuera:

```yml
prueba:
    resource: "@PruebaBundle/Resources/config/routing.yml"
    prefix:   /prueba
```
y **src\PruebaBundle\Resources\config\routing.yml** fuera:

```yml
prueba_hola_mundo:
    path:     /holamundo
    defaults: { _controller: PruebaBundle:Default:index }
```
La ruta a escribir sería **/prueba/holamundo**.

---------------------------------------

Si abrimos el controlador **src\PruebaBundle\Controller\DefaultController.php** este apunta a la función index (indexAction)

| src\PruebaBundle\Controller\DefaultController.php |
|---------------------------------------------------|

```php
<?php

namespace PruebaBundle\Controller;

use Symfony\Bundle\FrameworkBundle\Controller\Controller;

class DefaultController extends Controller
{
//método por defecto que se ejecuta al llamar a este controlador (indexAction)
    public function indexAction()
    {
    // llama a una vista que se llama por defecto index.html.twig
        return $this->render('PruebaBundle:Default:index.html.twig');
    }
}
```

Para ver la vista entramos en **src\PruebaBundle\Resources\views\Default\index.html.twig**, la cual contiene el texto ** Hola Mundo!!!**

A continuación arrancaríamos el servidor desde la consola y probamos los resultados.

| [Volver al inicio del capítulo](#2basicos-symfony3) | [Ver índice](#indice) |
|-----------------------------------------------------|-----------------------|

2.7.¿Cómo generar una nueva Página estática?
--------------------------------------------

Habría que indicarla dentro de **src\PruebaBundle\Resources\config\routing.yml**

| src\PruebaBundle\Resources\config\routing.yml |
|-----------------------------------------------|

```yml
prueba_nombre:
    path:     /nombre
    defaults: { _controller: PruebaBundle:Default:nombre }
```

Si abrimos el controlador **src\PruebaBundle\Controller\DefaultController.php** este apunta a la función nombre (nombreAction)

| src\PruebaBundle\Controller\DefaultController.php |
|---------------------------------------------------|

```php
<?php

namespace PruebaBundle\Controller;

use Symfony\Bundle\FrameworkBundle\Controller\Controller;

class DefaultController extends Controller
{
    public function nombreAction()
    {
    // llama a una vista que se llama por defecto nombre.html.twig
        return $this->render('PruebaBundle:Default:nombre.html.twig');
    }
}
```

Para ver la vista entramos en **src\PruebaBundle\Resources\views\Default\nombre.html.twig**, la cual contiene el texto **Estamos dentro de la página de nombres**

| [Volver al inicio del capítulo](#2basicos-symfony3) | [Ver índice](#indice) |
|-----------------------------------------------------|-----------------------|

3.VISTAS Y TWIG
===============

3.1.¿Cómo crear una plantilla para las Vistas?
----------------------------------------------

Accederemos al archivo base por defecto accediendo a **app\config\Resources\views\base.html.twig**, esta tendrá el siguiente contenido:

| app\config\Resources\views\base.html.twig |
|-------------------------------------------|

```twig
<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8" />
        <title>{% block title %}Welcome!{% endblock %}</title>
        {% block stylesheets %}{% endblock %}
        <link rel="icon" type="image/x-icon" href="{{ asset('favicon.ico') }}" />
    </head>
    <body>
      {% block body %}{% endblock %}
      {% block javascripts %}{% endblock %}
    </body>
</html>
```

Para cambiar la ubicación de la plantilla a dentro de nuestro bundle (en este caso **AppBundle**) solo hay que ubicarla (por ejemplo dentro de **src\AppBundle\Resources\views\Layout\layout.html.twig**) y al referenciar la nueva vista incluir el siguiente código:

```twig
{# EXTENDEMOS LA PLANTILLA 'AppBundle:Layouts:layout.html.twig'...................... #}
  {% extends "AppBundle:Layouts:layout.html.twig"%}
{# ......................EXTENDEMOS LA PLANTILLA 'AppBundle:Layouts:layout.html.twig' #}

```

| [Volver al inicio del capítulo](#3vistas-y-twig) | [Ver índice](#indice) |
|--------------------------------------------------|-----------------------|

3.2.1.¿Cómo referenciar los recursos externos conectados a nuestras plantillas (Assets)?
----------------------------------------------------------------------------------------

Las templates normalmente hacen referencia a imágenes, JavaScript, hojas de estilo y otros assets. Symfony proporciona una forma dinámica y flexible de cargarlos a través de la función **asset** de **Twig**:

```twig
<img src="{{ asset('images/logo.png') }}" alt="Symfony!" />
<link href="{{ asset('css/blog.css') }}" rel="stylesheet" />
<link rel="icon" type="image/x-icon" href="{{ asset('favicon.ico') }}" />
<script src="{{ asset('js/bootstrap.js')}}"></script>
```

El principal objetivo de la función asset es hacer la aplicación más portable. Si tu aplicación está en el root del host ([http://ejemplo.com](http://ejemplo.com)), entonces los directorios deberían ser `/images/logo.png`. Pero si tu aplicación está en un subdirectorio ([http://example.com/my_app](http://example.com/my_app)), cada directorio de los assets deberá renderizarse en el subdirectorio (`/my_app/images/logo.png`). La función asset se hace cargo de esto determinando cómo está construida y generando los directorios correctos.

Además, si empleas la función asset, Symfony puede añadir automáticamente un query string a tu asset, para garantizar que las actualizaciones de assets estáticos no sean cacheados. Por ejemplo, /images/logo.png puede cambiarse a `/images/logo.png?v2`. La versión de todo el conjunto de assets se puede modificar en la opción de configuración assets_version.

Si necesitas establecer una versión para un asset específico, puedes establecer el argumento version.

```twig
<img src="{{ asset('images/logo.png', version='3.0') }}" alt="Symfony!" />
```

Si no proporcionas una versión o pones null, el paquete de versiones por defecto (el de assets_version) se empleará. Si pones false, la URL versionizada se desactivará para este asset en concreto.

Si necesitas URLs absolutas para assets, puedes establecer el argumento absolute si estás usando Twig a true:

```twig
<img src="{{ absolute_url(asset('images/logo.png')) }}" alt="Symfony!" />
```

| [Volver al inicio del capítulo](#3vistas-y-twig) | [Ver índice](#indice) |
|--------------------------------------------------|-----------------------|

 ----------------------------------

3.2.2.Smarter assets:install command
-------------------------------------

El comando `assets: install` es una de las cosas más difíciles para los recién llegados de Symfony. Este comando se utiliza para instalar los activos web (CSS, JavaScript, imágenes) para la aplicación de producción. Cuando se ejecuta sin opciones, el comando copia en **web/** todos los archivos que se encuentran en los directorios **Resources/public/** de la aplicación y los **bundles**.

Aunque los desarrolladores normalmente ejecutan el comando sin ninguna opción, la mayoría de las veces es mejor ejecutarlo con la opción `--symlink`. Esto hace que un enlace simbólico de sus activos en lugar de copiar realmente sus archivos. Esto significa que cualquier cambio en el contenido de los activos web tendrá efecto inmediato en la aplicación.

El problema es que la opción `--symlink` lanzará una **InvalidArgumentException** si su sistema no admite enlaces simbólicos. Por eso, a partir de Symfony 2.6, **el comportamiento del comando `assets: install` será más inteligente**. Ahora, cuando su sistema no admite enlaces simbólicos o si hay algún otro problema, el comando silenciosamente volverá a hacer una copia impresa de los activos y le informará sobre esto:

```
# make a hard copy of the assets in web/
$ php app/console assets:install

# if possible, make absolute symlinks in web/ if not, make a hard copy
$ php app/console assets:install --symlink

# if possible, make relative symlinks in web/ if not, make a hard copy
$ php app/console assets:install --symlink --relative
```

En resumen, a partir de Symfony 2.6, la mejor práctica es pasar siempre la opción `--symlink` al comando `assets: install`.


| [Volver al inicio del capítulo](#3vistas-y-twig) | [Ver índice](#indice) |
|--------------------------------------------------|-----------------------|

----------------------------------

4.DOCTRINE EN SYMFONY3
======================

4.1.¿Cómo configurar la Base de Datos?
--------------------------------------

Para poder ver la configuración de la base de datos hay que acceder a **app\config\parameters.yml**

| app\config\parameters.yml |
|---------------------------|

```yml
# This file is auto-generated during the composer install
parameters:
    database_host: 127.0.0.1
    database_port: null
    database_name: micms
    database_user: root
    database_password: null
    mailer_transport: smtp
    mailer_host: 127.0.0.1
    mailer_user: null
    mailer_password: null
    secret: ThisTokenIsNotSoSecretChangeIt
```

----------------------------------------------------------------------------

| **IMPORTANTE!!!** |
|-------------------|

Comandos de consola para la gestión de base de datos (ver documentación oficial [aquí](https://symfony.com/doc/current/doctrine.html))

* **Crear una nueva Base de Datos** `php bin/console doctrine:database:create`
* **Borrar una Base de Datos** ` php bin/console doctrine:database:drop`
* **Borrar una Base de Datos (sin cuestionar)** ` php bin/console doctrine:database:drop --force`
* **Actualizar una Base de Datos** `php bin/console doctrine:schema:update `
* **Actualizar una Base de Datos (sin cuestionar)** `php bin/console doctrine:schema:update --force`
* **Crear una tabla dentro de la Base de Datos** `php bin/console doctrine:schema:create`

----------------------------------------------------------------------------

| [Volver al inicio del capítulo](#4doctrine-en-symfony3) | [Ver índice](#indice) |
|---------------------------------------------------------|-----------------------|

4.2.¿Configurar la Base de Datos con UTF8?
------------------------------------------

Para evitar tener futuros problemas durante el uso de la base de datos con los caracteres especiales, se recomienda usar una configuración generalizada **UTF8**, para ello debemos acceder dentro del archivo **my.ini** de la configuración de la base de datos (**mysql**) del servidor que estemos usando y descomentar las siguientes líneas.

```
## UTF 8 Settings
init_connect=\'SET NAMES utf8\'
collation_server = utf8_unicode_ci
character_set_server = utf8
# skip_character_set_client_handshake
```

Nos aseguraremos también que la configuración es la correcta entrando en **app\config\config.yml** para comprobarlo.

```yml
doctrine:
    dbal:
        charset: utf8mb4
        default_table_options:
            charset: utf8mb4
            collate: utf8mb4_unicode_ci
```

| [Volver al inicio del capítulo](#4doctrine-en-symfony3) | [Ver índice](#indice) |
|---------------------------------------------------------|-----------------------|

4.3.¿Cómo generamos las tablas dentro de la Base de Datos (Entities)?
---------------------------------------------------------------------

Las entidades harán de interprete entre el modelo de la aplicación y la **Base de Datos** (Ver documentación oficial [aquí](https://symfony.com/doc/2.7/security/entity_provider.html#content_wrapper)).
Para generar las **entidades** usaremos el comando de consola `php bin/console doctrine:generate:entity`. Después de ejecutar este comando se iniciará el **wizard** que nos guiará en la configuración de la entidad.

* Para el **nombre del método abreviado** (*The Entity shortcut name:*), usaremos : `PruebaBundle:User`.

---------------------------------------------

| **IMPORTANTE!!** |
|------------------|

El **nombre del método abreviado** estará compuesto por el nombre del **Bundle** sobre el cual crearemos el entity (`PruebaBundle`), seguido de `:` (dos puntos) más el tipo de **CRUD** a usar, en este caso al ser para gestionar *usuarios* usaremos `:user`. Finalmente será `PruebaBundle:User`.
Es necesario indicar el nombre de método abreviado de la entidad haciendo referencia al **Bundle** anteriormente isntalado. Es decir, si usamos el comando `php bin/console generate:bundle --namespace=PruebaBundle`, nuestro nombre de método abreviado de entidad será exactamente `PruebaBundle:User`.

---------------------------------------------

* Para el **Formato de configuración (yml,xml,php, o anotación) [anotación]** (*Configuration format (yml,xml,php,or annotation)     [annotation]:*), usaremos : `yml`

* Para el primer **Nuevo nombre de campo** (*New field name*), usaremos: `username`.

| Field type [string] | Field length [255] | Is nullable [false] | Unique [false] |
|---------------------|--------------------|---------------------|----------------|
| string              | 35                 | false               | false          |

* Para el segundo **Nuevo nombre de campo** (*New field name*), usaremos: `password`.

| Field type [string] | Field length [255] | Is nullable [false] | Unique [false] |
|---------------------|--------------------|---------------------|----------------|
| string              | 80                 | false               | false          |

* Para terminar se dejará el tercer **Nuevo nombre de campo** en blanco

Finalmente se crearán los archivos que definen la entidad:

* **src\PruebaBundle\Entity\User.php**, contendrá la información de la entidad la cuál mediante el ORM de Doctrine configurará la tabla de la Base de Datos. Además tendrá los métodos **getter** y **setter**.
* **src\PruebaBundle\Repository\UserRepository.php**
* **src\PruebaBundle\Resources\config\doctrine\User.orm.yml**

Ahora ya podremos empezar a trabajar con ellos.

| [Volver al inicio del capítulo](#4doctrine-en-symfony3) | [Ver índice](#indice) |
|---------------------------------------------------------|-----------------------|

---------------------------------------------

| **IMPORTANTE!!** |
|------------------|

Utilizaremos el comando `php bin/console doctrine:schema:update --force` para actualizar la entidad.

---------------------------------------------

**Otro Ejemplo**
* Escribimos en consola `php bin/console doctrine:generate:entity`
* **The Entity shortcut name:** PruebaBundle:Eventos
* **Configuration format (yml,xml,php,or annotation)[annotation]:** yml
* Para el primer **New field name**, usaremos: `nombreEvento`.

| Field type [string] | Field length [255] | Is nullable [false] | Unique [false] |
|---------------------|--------------------|---------------------|----------------|
| string              | 255                | false               | false          |
* Para el primer **New field name**, usaremos: `fecha`.

| Field type [string] | Is nullable [false] | Unique [false] |
|---------------------|---------------------|----------------|
| datetime            | false               | false          |
* Para el primer **New field name**, usaremos: `ciudad`.

| Field type [string] | Field length [255] | Is nullable [false] | Unique [false] |
|---------------------|--------------------|---------------------|----------------|
| string              | 255                | false               | false          |

* Para terminar se dejará el tercer **Nuevo nombre de campo** en blanco

Finalmente se crearán los archivos que definen la entidad:

* **src\PruebaBundle\Entity\Eventos.php**, contendrá la información de la entidad la cuál mediante el ORM de Doctrine configurará la tabla de la Base de Datos. Además tendrá los métodos **getter** y **setter**.
* **src\PruebaBundle\Repository\EventosRepository.php**
* **src\PruebaBundle\Resources\config\doctrine\Eventos.orm.yml**

Ahora ya podremos empezar a trabajar con ellos.

| [Volver al inicio del capítulo](#4doctrine-en-symfony3) | [Ver índice](#indice) |
|---------------------------------------------------------|-----------------------|

4.3.1.¿Cómo actualizar las Entidades (Entities)?
-------------------------------------------------

Si efectuamos cambios dentro de la entidad (por ejemplo, **src\PruebaBundle\Entity\Eventos.php**) añadimos manualmente nuevos campos podemos actualizar dicha entidad regenerando los **getter** y **setter**. Usaremos el comando `php bin/console doctrine:PruebaBundle:Entity:Eventos` el cual se compone de `php bin/console doctrine:PruebaBundle:Entity:Eventos` más la ubicación de la entidad **src\PruebaBundle\Entity\Eventos.php**.

| [Volver al inicio del capítulo](#3doctrine-en-symfony3) | [Ver índice](#indice) |
|---------------------------------------------------------|-----------------------|

---------------------------------------------

| **IMPORTANTE!!** |
|------------------|

Utilizaremos el comando `php bin/console doctrine:schema:update --force` para actualizar la entidad.

Si modificamos el comando tal que así : `php bin/console doctrine:schema:update --force --dump-sql` se nos mostrará la sentencia que se lanzará y modificará la base de datos.

---------------------------------------------

| [Volver al inicio del capítulo](#4doctrine-en-symfony3) | [Ver índice](#indice) |
|---------------------------------------------------------|-----------------------|

4.CRUD EN SYMFONY3
==================

4.1.¿Cómo generamos consultas a la base de datos?
-------------------------------------------------

Para hacer consultas a la base de datos tendremos que realizarlas dentro de **método** correspondiente en el **controlador** ejecutado que pertenece al **Bundle**. (ver documentación oficial [aquí](http://symfony.com/doc/current/doctrine.html))

```php
$repository = $this->getDoctrine()->getRepository(Product::class);
// query for a single product by its primary key (usually "id")
$product = $repository->find($productId);
// dynamic method names to find a single product based on a column value
$product = $repository->findOneById($productId);
$product = $repository->findOneByName('Keyboard');
// dynamic method names to find a group of products based on a column value
$products = $repository->findByPrice(19.99);
// find *all* products
$products = $repository->findAll();
```

Así por ejemplo tendremos:

| src\PruebaBundle\Controller\DefaultController.php |
|---------------------------------------------------|
```php
<?php

namespace PruebaBundle\Controller;

use Symfony\Bundle\FrameworkBundle\Controller\Controller;

class DefaultController extends Controller
{
   public function indexAction($eventos)
   {
       // Usamos EntityManager ($em)
       $em = $this->getDoctrine()->getManager();
       // Creamos el objeto que obtendrá el listado de productos
       $eventos = $em->getRepository('PruebaBundle:Eventos')->findAll();
       // llama a una vista que se llama por defecto index.html.twig
       return $this->render('PruebaBundle:Default:index.html.twig', array('eventos'=>$eventos));
     }
}
```

| [Volver al inicio del capítulo](#4crud-en-symfony3) | [Ver índice](#indice) |
|-----------------------------------------------------|-----------------------|

-----------------------------------------------

4.1.1.EJEMPLO DE CONSULTA A LA BASE DE DATOS
--------------------------------------------

| src\PruebaBundle\Controller\EventosController.php |
|---------------------------------------------------|

```php
<?php

namespace PruebaBundle\Controller;

use Symfony\Bundle\FrameworkBundle\Controller\Controller;

// La clase usará como nombre el del archivo
class EventosController extends Controller
{
   public function allAction($eventos)
   {
       // Usamos EntityManager ($em)
       $em = $this->getDoctrine()->getManager();
       /*
        * Creamos el objeto que obtendrá el listado de Eventos que se encuentra
        * dentro de 'PruebaBundle' y en la entidad 'eventos'
        */
       $eventos = $em->getRepository('PruebaBundle:Eventos')->findAll();
       /*
        * Llamamos a una vista que se llama por defecto all.html.twig y que se encuentra dentro de \view\Eventos en caso de:
        * return $this->render('PruebaBundle:Eventos:all.html.twig', array('eventos'=>$eventos));       
        * llama a una vista que se llama por defecto all.html.twig y que se encuentra dentro de \view\Default en caso de:
        * return $this->render('PruebaBundle:Default:all.html.twig', array('eventos'=>$eventos));
        */
       return $this->render('PruebaBundle:Default:all.html.twig', array('eventos'=>$eventos));
     }
}
```

*Nota*: **app\config\routing.yml** define la ruta madre de cada **Bundle** es decir, si fuera:

| app\config\routing.yml |
|------------------------|

```yml
prueba:
    resource: "@PruebaBundle/Resources/config/routing.yml"
    prefix:   /prueba
```

*Nota*: **src\PruebaBundle\Resources\config\routing.yml** define la ruta del **controlador + método** a usar es decir, si fuera:

| src\PruebaBundle\Resources\config\routing.yml |
|-----------------------------------------------|

```yml
all_eventos:
    path:     /eventos/all
    # El controlador se encuentra dentro de 'PruebaBundle' se llama 'EventosController' y el método que usaremos es 'allAction()'
    defaults: { _controller: PruebaBundle:Eventos:all }
```

| src\PruebaBundle\views\Eventos\all.html.twig |
|----------------------------------------------|

```twig
<ul id="eventos">
  {% for evento in eventos %}
    <li>{{ eventos.caption }}</li>
  {% endfor %}
</ul>
```

**FIN DEL EJEMPLO**
--------------------

-----------------------------------------------

| [Volver al inicio del capítulo](#4crud-en-symfony3) | [Ver índice](#indice) |
|-----------------------------------------------------|-----------------------|

4.1.2.¿Cómo visualizar una página mediante **response**?
--------------------------------------------------------

Un objeto **response** guarda toda la información que ha de ser devuelta al cliente a partir de un **request** solicitado. El constructor acepta hasta tres argumentos: el contenido de la respuesta, el código de estado y un array de HTTP headers. (Ver documentación oficial [aquí](http://symfony.com/doc/current/controller.html)).

Para utilizar esta función es necesario incluir la librería dentro del controlador que la activa `use Symfony\Component\HttpFoundation\Response;`

| src\PruebaBundle\Controller\DefaultController.php |
|---------------------------------------------------|

```php
<?php

namespace PruebaBundle\Controller;

use Symfony\Bundle\FrameworkBundle\Controller\Controller;
use Symfony\Component\HttpFoundation\Response;

class DefaultController extends Controller
{
   public function nombreAction($nPila)
   {
      return $this->render('PruebaBundle:Default:nombre.html.twig', array('nPila'=>$nPila));
     }
   public function nombreRAction($nPila)
   {
      return new Response('<html><head><body>Hola '.$nPila.'</body></head></html>');
     }
}
```

| src\PruebaBundle\Resources\config\routing.yml |
|-----------------------------------------------|

```yml
prueba_nombre:
    path:     /nombre/{nPila}
    defaults: { _controller: PruebaBundle:Default:nombre, nPila:'manolo' }

prueba_nombreR:
    path:     /nombreR/{nPila}
    defaults: { _controller: PruebaBundle:Default:nombreR }
```

| [Volver al inicio del capítulo](#4crud-en-symfony3) | [Ver índice](#indice) |
|-----------------------------------------------------|-----------------------|

4.1.3.¿Cómo visualizar una página mediante **redirect**, **generateUrl** y **createNotFoundException**?
-------------------------------------------------------------------------------------------------------

La clase **redirect** implementa ContainerAwareInterface, y redirige un request a otra URL. (Ver documentación oficial [aquí](http://symfony.com/doc/current/controller.html)).

Para utilizar esta función es necesario incluir la librería dentro del controlador que la activa `use Symfony\Component\HttpFoundation\Response;`

| src\PruebaBundle\Controller\DefaultController.php |
|---------------------------------------------------|

```php
<?php

namespace PruebaBundle\Controller;

use Symfony\Bundle\FrameworkBundle\Controller\Controller;

class DefaultController extends Controller
{
   public function contactarAction($lugar)
   {
      if($lugar=='vlc'){
      // 'prueba_contactar_vlc' es una ruta definida dentro del 'routing.yml del bundle
        return $this->redirect($this->generateUrl('prueba_contactar_vlc'));
      }elseif{
      // redireccionamos directamente a la dirección
        return $this->redirect('http://www.google.es');
      }elseif{        
        return $this->render('PruebaBundle:Default:index.html.twig');
      }else{
        throw $this->createNotFoundException('The product does not exist');
      }
   }
}
```

| src\PruebaBundle\Resources\config\routing.yml |
|-----------------------------------------------|

```yml
prueba_nombre:
    path:     /nombre/{nPila}
    defaults: { _controller: PruebaBundle:Default:nombre, nPila:'manolo' }

prueba_nombreR:
    path:     /nombreR/{nPila}
    defaults: { _controller: PruebaBundle:Default:nombreR }
```

| [Volver al inicio del capítulo](#4crud-en-symfony3) | [Ver índice](#indice) |
|-----------------------------------------------------|-----------------------|

4.2.¿Cómo generar un CRUD?
--------------------------

Para crear el **ORM** que gestionará la base de datos accedemos a la consola, dónde escribimos `php bin/console doctrine:schema:update --force`. Posteriormente para solicitar la creación del **CRUD** por parte de **Symfony** + escribimos en consola `php bin/console generate:doctrine:crud`.

* Para el primer **nombre de método abreviado de entidad** (*Entity shortcut name*), usaremos: `PruebaBundle:Eventos`.
Seleccionaremos ante la cuestión **The Entity shortcut name:** el nombre del **shortcut** empleado en la instalación del entity asociado al Bundle, en este caso `PruebaBundle:User`.

| Do you want to generate the "write" actions [no]?             | yes         |
|-------------------------------------------------------------------|-------------|
| Configuration format (yml, xml, php, or annotation) [annotation]: | yml         |
| Routes prefix [/user]:                                            | /admin/user |
| Do you confirm generation [yes]?                                  | yes         |

-----------------------------------------

| IMPORTANTE!! |
|--------------|

Como la gestión de usuarios se encontrará en el backend colocamos el prefijo a la ruta /admin/user.

-----------------------------------------

Este generador creará los siguientes archivos **src\PruebaBundle\Controller\UserController.php**, **src\PruebaBundle\Resources\Config\routing.yml**. Además habrá generado dentro de **app\Resources\views\Eventos** las diferentes vistas que son necesarais para el **CRUD**.

| [Volver al inicio del capítulo](#4crud-en-symfony3) | [Ver índice](#indice) |
|-----------------------------------------------------|-----------------------|

4.2.1.¿Cómo insertar datos en la Base de Datos?
-----------------------------------------------

Para insertar datos en la base de datos tendremos que realizarlo mediante el **método** correspondiente en el **controlador** ejecutado que pertenece al **Bundle**. (ver documentación oficial [aquí](http://symfony.com/doc/current/doctrine.html))

Dentro del archivo **src\CursoBundle\Controller\EmpresaController.php** será necesario identificar la **entidad** perteneciente a la tabla de entrada de datos de la BD `use PruebaBundle\Entity\Eventos;`

| src\CursoBundle\Controller\EmpresaController.php |
|--------------------------------------------------|

```php
<?php

namespace CursoBundle\Controller;

use Symfony\Bundle\FrameworkBundle\Controller\Controller; // Contiene el controlador
use CursoBundle\Entity\Empresa; // Contiene la Entidad EMPRESA

class EmpresaController extends Controller
{
  public function crearEmpresaAction()
  {
    // Creamos un nuevo objeto procedente de la Entidad 'Empresa'
    $empresa = new Empresa();
    $empresa->setNombreEmpres("empresa daw");
    $empresa->setNumEmpleados(100);
    $empresa->setUbicacionCiudad("Málaga");
    /*
     * DOCTRINE
     */
    $em = $this->getDoctrine()->getManager();      // Usamos EntityManager ($em)
    $em->persist($empresa);      // Hace persistentes los datos
    $em->flush($empresa);      // actualiza las queries
    return $this->render('CursoBundle:Empresa:crearEmpresa.html.twig',array('empresaId'=>$empresa->getId()));
  }
}
```

| app\config\routing.yml |
|------------------------|

```yml
curso:
    resource:"@CursoBundle/Resources/config/routing.yml"
    prefix:  /curso/
```

| src\CursoBundle\Resources\config\routing.yml |
|----------------------------------------------|

```yml
empresa_crear:
    path:     /empresa/crear
    defaults: { _controller: CursoBundle:Empresa:crearEmpresa }
```

| src\CursoBundle\Resources\views\Empresa\crearEmpresa.html.twig |
|----------------------------------------------------------------|

```yml
creada la empresa {{ empresaId }}
```

| La url para su funcionamiento sería **127.0.0.1:8000/curso/empresa/crear**. (sólo se podrá usar una vez ya que la empresa debe ser única |
|-------------------------------------------------------------------------------------------------------------------------------------------|

| [Volver al inicio del capítulo](#4crud-en-symfony3) | [Ver índice](#indice) |
|-----------------------------------------------------|-----------------------|

4.2.2.¿Cómo buscar registro por su id en la Base de Datos?
----------------------------------------------------------

| src\CursoBundle\Controller\EmpresaController.php |
|--------------------------------------------------|

```php
<?php

namespace CursoBundle\Controller;

use Symfony\Bundle\FrameworkBundle\Controller\Controller; // Contiene el controlador
use CursoBundle\Entity\Empresa; // Contiene la Entidad EMPRESA

class EmpresaController extends Controller
{
  public function buscarEmpresaAction($id)
  {
    // Recuperamos el repositorio
    $em = $this->getDoctrine()->getRepository('CursoBundle:Empresa');
    // Buscamos la coincidencia
    $empresa = $em->find($id);
    return $this->render(
      'CursoBundle:Empresa:empresa.html.twig',
      array("id"=>$empresa->getId(),"nombre"=>$empresa->getNombreEmpresa())
    );
  }
}
```

| src\CursoBundle\Resources\config\routing.yml |
|----------------------------------------------|

```yml
empresa_buscar:
    path:     /empresa/{id}
    defaults: { _controller: CursoBundle:Empresa:buscarEmpresa,id:1 }
```

| [Volver al inicio del capítulo](#4crud-en-symfony3) | [Ver índice](#indice) |
|-----------------------------------------------------|-----------------------|

4.2.3.¿Cómo buscar registro por su nombre en la Base de Datos?
----------------------------------------------------------

| src\CursoBundle\Controller\EmpresaController.php |
|--------------------------------------------------|

```php
<?php

namespace CursoBundle\Controller;

use Symfony\Bundle\FrameworkBundle\Controller\Controller; // Contiene el controlador
use CursoBundle\Entity\Empresa; // Contiene la Entidad EMPRESA

class EmpresaController extends Controller
{
  public function buscarEmpresaPorNombreAction($nombre)
  {
    // Recuperamos el repositorio
    $em = $this->getDoctrine()->getRepository('CursoBundle:Empresa');
    // Buscamos la coincidencia
    $empresa = $em->findOneByNombreEmpres($nombre);
    return $this->render(
      'CursoBundle:Empresa:empresa.html.twig',
      array("id"=>$empresa->getId(),"nombre"=>$empresa->getNombreEmpresa())
    );
  }
}
```

| src\CursoBundle\Resources\config\routing.yml |
|----------------------------------------------|

```yml
empresaPorNombre_buscar:
    path:     /empresaPorNombre/{nombre}
    defaults: { _controller: CursoBundle:Empresa:buscarEmpresaPorNombre,nombre:'Paco' }
```

| [Volver al inicio del capítulo](#4crud-en-symfony3) | [Ver índice](#indice) |
|-----------------------------------------------------|-----------------------|

4.3.EXTRA - Entidad empleada para el CRUD
-----------------------------------------

**Para los ejemplos anteriores hemos utilizado esta entidad:**
* Escribimos en consola `php bin/console doctrine:generate:entity`
* **The Entity shortcut name:** CursoBundle:Empresa
* **Configuration format (yml,xml,php,or annotation)[annotation]:** yml

* Para el primer **New field name**, usaremos: `nombreEmpresa`.

| Field type [string] | Field length [255] | Is nullable [false] | Unique [false] |
|---------------------|--------------------|---------------------|----------------|
| string              | 128                | false               | true           |

* Para el primer **New field name**, usaremos: `ubicacionCiudad`.

| Field type [string] | Field length [255] | Is nullable [false] | Unique [false] |
|---------------------|--------------------|---------------------|----------------|
| string              | 128                | false               | false          |

* Para el primer **New field name**, usaremos: `numEmpleados`.

| Field type [string] |
|---------------------|
| integer             |

* Para terminar se dejará el tercer **Nuevo nombre de campo** en blanco

| [Volver al inicio del capítulo](#4crud-en-symfony3) | [Ver índice](#indice) |
|-----------------------------------------------------|-----------------------|

---------------------------------------------

5.FORMULARIOS EN SYMFONY3
=========================

5.1.Creación de Formularios
---------------------------

(Ver documentación oficial, [aquí](https://symfony.com/doc/current/forms.html)) Para la generación de un nuevo formulario es necesario utilizar la línea de comando `php bin/console doctrine:generate:form` indicando posteriormente la **entidad** a la que haremos referencia, así como su **bundle**. Así en el caso del ejemplo dentro de **CursoBundle** y para la entidad **Empresa**, tendríamos la línea de comando `php bin/console doctrine:generate:form CursoBundle:Empresa`. Posteriormente se habrá generado el archivo **src\CursoBundle\Form\EmpresaType.php**.

Dentro de **src\CursoBundle\Form\EmpresaType.php** hay que incluir:
* El componente `use Symfony\Component\Form\Extension\Core\Type\SubmitType;` para poder incluir el botón de envío.
* El componente `use Symfony\Component\Form\Extension\Core\Type\ResetType;` para poder incluir el botón de borrar.
* El componente `use Symfony\Component\Form\Extension\Core\Type\TextType;` para poder incluir la clase TextType.
* El componente `use Symfony\Component\Form\Extension\Core\Type\DateType;` para poder incluir la clase DateType;.
* incluimos `->add('guardar',SubmitType::class);` dentro del método `public function buildForm(FormBuilderInterface $builder, array $options)` para añadir el botón de envío de formulario.

| src\CursoBundle\Form\EmpresaType.php |
|--------------------------------------|

```php
<?php

namespace CursoBundle\Form;

use Symfony\Component\Form\AbstractType;            //Genera el formulario
use Symfony\Component\Form\FormBuilderInterface;    // Generará la interfaz del formulario
use Symfony\Component\OptionsResolver\OptionsResolver;     // Define los datos por defecto del formulario
/* Añadimos el siguiente componente para poder incluir el botón de envío */
use Symfony\Component\Form\Extension\Core\Type\SubmitType; // Lanza la librería que permite el uso del botón Enviar
use Symfony\Component\Form\Extension\Core\Type\ResetType;  // Lanza la librería que permite el uso del botón eliminar

class EmpresaType extends AbstractType
{
    /**
     * {@inheritdoc}
     */
    public function buildForm(FormBuilderInterface $builder, array $options)
    {
        $builder->add('nombreEmpresa')
        ->add('ubicacionCiudad')
        ->add('numEmpleados')
  /* Opciones incluidas */
        ->add('guardar',SubmitType::class)
  ->add('borrar',ResetType::class);
  /* Fin de opciones incluidas */
    }

    /**
     * {@inheritdoc}
     */
    public function configureOptions(OptionsResolver $resolver)
    {
        $resolver->setDefaults(array(
            'data_class' => 'CursoBundle\Entity\Empresa'
        ));
    }

    /**
     * {@inheritdoc}
     */
    public function getBlockPrefix()
    {
        return 'cursobundle_empresa';
    }
}
```

Dentro de **src\CursoBundle\Controller\EmpresaController.php** hay que incluir:
* El componente `use CursoBundle\Form\EmpresaType;` para poder incluir el formulario creado para **empresa**.
* Crearemos el formulario mediante `$form = $this->createForm(EmpresaType::class,$empresa);`
* El componente `use Symfony\Component\HttpFoundation\Request;` para poder incluir la librería que capturará la información enviada por el formulario, ademáse será necesario añadir el **Request**, mediante `$form->handleRequest($request);`, que capturará los datos enviados.
* Añadiremos un condicional, `if ($form->isSubmitted() && $form->isValid()){}`, para asegurarnos del *envío de datos* y que estos son *Válidos*

| src\CursoBundle\Controller\EmpresaController.php |
|--------------------------------------------------|

```php
<?php

namespace CursoBundle\Controller;

use Symfony\Bundle\FrameworkBundle\Controller\Controller;   // Contiene el controlador
use CursoBundle\Entity\Empresa;     // Contiene la Entidad EMPRESA
use CursoBundle\Form\EmpresaType;     // Contiene el Formulario
use Symfony\Component\HttpFoundation\Request;   // Incluye la librería que capturará la información enviada por el formulario

class EmpresaController extends Controller
{
  public function nuevaEmpresaAction(Request $request)
  {
    $empresa = new Empresa();
    // Creamos el formulario
    $form = $this->createForm(EmpresaType::class,$empresa);
    // añadimos el 'Request' que capturará los datos del formulario
    $form->handleRequest($request);
    if ($form->isSubmitted() && $form->isValid()){
      // Si se envía el formulario y es Válido
      $empresa = $form->getData();
      $em = $this->getDoctrine()->getManager();
      $em->persist($empresa);
      $em->flush();
      // una vez cargado en la BD lanzo la notificación.
      return $this->redirectToRoute('exito_nueva_empresa');
    }
    return $this->render(
      'CursoBundle:Empresa:nuevaEmpresa.html.twig',
      array('form' => $form->createView())
    );
  }
}
```

Dentro de **src\CursoBundle\Resources\config\routing.yml** hay que incluir:
* Hay que indicar las dos url necesarias para el formulario, la propia del formulario (`nueva_empresa`) y a al que se nos enviará tras completarlo (`exito_nueva_empresa`).

| src\CursoBundle\Resources\config\routing.yml |
|----------------------------------------------|

```yml
nueva_empresa:
    path:     /empresa/nueva/
    defaults: { _controller: CursoBundle:Empresa:nuevaEmpresa }

exito_nueva_empresa:
    path:     /empresa/msgExito
    defaults: { _controller: CursoBundle:Empresa:msgExito }
```

| [Volver al inicio del capítulo](#5formularios-en-symfony3) | [Ver índice](#indice) |
|------------------------------------------------------------|-----------------------|

5.2.Tipos de datos en los Formularios
-------------------------------------

(Ver documentación oficial, [aquí](https://symfony.com/doc/current/forms.html)) Para definir los distintos tipos de datos que recogerá el formulario, y así poder usar la valdiación automática, lo indicamos dentro del de **src\CursoBundle\Form\EmpresaType.php**, de la siguiente manera:

Dentro de **src\CursoBundle\Form\EmpresaType.php** hay que incluir:
* El componente `use Symfony\Component\Form\Extension\Core\Type\TextType;` para poder incluir la clase TextType.
* El componente `use Symfony\Component\Form\Extension\Core\Type\DateType;` para poder incluir la clase DateType;.

| src\CursoBundle\Form\EmpresaType.php |
|--------------------------------------|

```php
/* Extracto de código */
use Symfony\Component\Form\Extension\Core\Type\TextType;   // Lanza la librería que permite el uso de la clase TextType
use Symfony\Component\Form\Extension\Core\Type\DateType;   // Lanza la librería que permite el uso de la clase DateType
use Symfony\Component\Form\Extension\Core\Type\IntegerType;   // Lanza la librería que permite el uso de la clase IntegerType

/* Fin de extracto de código */
...
/* Extracto de código */
    public function buildForm(FormBuilderInterface $builder, array $options)
    {
        $builder->add('nombreEmpresa', TexType::class)
        ->add('fechaInscripcion',DateType::class)
        ->add('ubicacionCiudad', TexType::class)
        ->add('numEmpleados',IntegerType:class)
        ->add('guardar',SubmitType::class)
  ->add('borrar',ResetType::class);
    }
/* Fin de extracto de código */
```

| Tipos de datos Formulario: **Text Fields** (TextType, TextareaType, EmailType, IntegerType, MoneyType, NumberType, PasswordType, PercentType, SearchType, UrlType, RangeType), **Choice Fields** (ChoiceType, EntityType, CountryType, LanguageType, LocaleType, TimezoneType, CurrencyType), **Date and Time Fields** (DateType, DateIntervalType, DateTimeType, TimeType, BirthdayType), **Other Fields** (CheckboxType, FileType, RadioType), **Field Groups** (CollectionType, RepeatedType), **Hidden Fields** (HiddenType), **Buttons** (ButtonType, ResetType, SubmitType) y **Base Fields* (FormType) |
|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|


| [Volver al inicio del capítulo](#5formularios-en-symfony3) | [Ver índice](#indice) |
|------------------------------------------------------------|-----------------------|

5.3.Opciones de datos de Formularios
------------------------------------

Además podemos incluir opciones dentro de los tipos de datos usados dentro del formulario de la siguiente manera:

| src\CursoBundle\Form\EmpresaType.php |
|--------------------------------------|

```php
/* Extracto de código */
    public function buildForm(FormBuilderInterface $builder, array $options)
    {
        $builder->add('nombreEmpresa', TextType::class)
        ->add('fechaInscripcion',DateType::class)
        ->add('ubicacionCiudad', TextType::class,
            array(
                    'label'=>'Ubicación de la Empresa',
                    'label_attr'=>array('class'=>'etiqueta'),
                    'attr'=>array('class'=>'etiqueta_elemento')
                )
            )
        ->add('numEmpleados',IntegerType::class)
        ->add('guardar',SubmitType::class)
        ->add('borrar',ResetType::class);
    }
/* Fin de extracto de código */
```

| [Volver al inicio del capítulo](#5formularios-en-symfony3) | [Ver índice](#indice) |
|------------------------------------------------------------|-----------------------|

---------------------------------------------

6.RELACIONES ENTRE TABLAS EN SYMFONY3
=====================================

6.1.Tipos de Relaciones
-----------------------

* **Many-To-One, Unidirectional** (Ver documentación oficial, [aquí](http://docs.doctrine-project.org/projects/doctrine-orm/en/latest/reference/association-mapping.html))
```yml
User:
  type: entity
  manyToOne:
    address:
      targetEntity: Address
      joinColumn:
        name: address_id
        referencedColumnName: id
```

* **One-To-One, Unidirectional** (Ver documentación oficial, [aquí](http://docs.doctrine-project.org/projects/doctrine-orm/en/latest/reference/association-mapping.html))
```yml
Product:
  type: entity
  oneToOne:
    shipment:
      targetEntity: Shipment
      joinColumn:
        name: shipment_id
        referencedColumnName: id
```

* **One-To-One, Bidirectional** (Ver documentación oficial, [aquí](http://docs.doctrine-project.org/projects/doctrine-orm/en/latest/reference/association-mapping.html))
```yml
Customer:
  oneToOne:
    cart:
      targetEntity: Cart
      mappedBy: customer
Cart:
  oneToOne:
    customer:
      targetEntity: Customer
      inversedBy: cart
      joinColumn:
        name: customer_id
        referencedColumnName: id
```

* **One-To-Many, Bidirectional** (Ver documentación oficial, [aquí](http://docs.doctrine-project.org/projects/doctrine-orm/en/latest/reference/association-mapping.html))
```yml
Product:
  type: entity
  oneToMany:
    features:
      targetEntity: Feature
      mappedBy: product
Feature:
  type: entity
  manyToOne:
    product:
      targetEntity: Product
      inversedBy: features
      joinColumn:
        name: product_id
        referencedColumnName: id
```

* **One-To-Many, Unidirectional with Join Table** (Ver documentación oficial, [aquí](http://docs.doctrine-project.org/projects/doctrine-orm/en/latest/reference/association-mapping.html))
```yml
User:
  type: entity
  manyToMany:
    phonenumbers:
      targetEntity: Phonenumber
      joinTable:
        name: users_phonenumbers
        joinColumns:
          user_id:
            referencedColumnName: id
        inverseJoinColumns:
          phonenumber_id:
            referencedColumnName: id
            unique: true
```

* **One-To-Many, Self-referencing** (Ver documentación oficial, [aquí](http://docs.doctrine-project.org/projects/doctrine-orm/en/latest/reference/association-mapping.html))
```yml
Category:
  type: entity
  oneToMany:
    children:
      targetEntity: Category
      mappedBy: parent
  manyToOne:
    parent:
      targetEntity: Category
      inversedBy: children
```

6.2.Relaciones entre Tablas
---------------------------

(Ver documentación oficial, [aquí](https://symfony.com/doc/current/doctrine/associations.html)) El primer paso que dar es el de incluir una tabla nueva con la que relacionar el contenido de la primera tabla (**Empresa**), en este caso (**Ciudad**). Para ello usaremos la línea de comando `php bin/console doctrine:generate:entity --no-interaction --entity="CursoBundle:Ciudad" --fields="ciudad:string(255)"` el cual generará una entidad **Ciudad** con una columna tipo **string.

* **The Entity shortcut name:** CursoBundle:Empresa
* **Configuration format (yml,xml,php,or annotation)[annotation]:** yml

* Para el primer **New field name**, usaremos: `nombreCiudad`.

| Field type [string] | Field length [255] | Is nullable [false] | Unique [false] |
|---------------------|--------------------|---------------------|----------------|
| string              | 255                | false               | true           |


----------------------------------------------------------------

El campo categoria estará enlazado con otra tabla, por lo que habrá que realizarlo manualmente (Ver documentación oficial, [aquí](https://symfony.com/doc/current/doctrine/associations.html#relationship-mapping-metadata)). Para ello accedemos al archivo **src\CursoBundle\Resources\config\doctrine\Empresa.orm.yml** y a **src\CursoBundle\Resources\config\doctrine\Ciudad.orm.yml**

----------------------------------------------------------------

* Indicamos los campos no vinculados **fields**, y los vinculados con otras tablas **manyToOne** o **oneToMany**.
* **targetEntity** indicará la entidad Objetivo a la que se hará referencia.
* **inversedBy** y **mappedBy** indicaran la entidad que se está vinculando.
* Dentro de **joinColumn** indicaremos el nombre de la columna a mostrar y su relación con la tabla objetivo.

| src/CursoBundle/Resources/config/doctrine/Empresa.orm.yml |
|-----------------------------------------------------------|

```yml
CursoBundle\Entity\Empresa:
    type: entity
    table: null
    repositoryClass: CursoBundle\Repository\EmpresaRepository
    id:
        id:
            type: integer
            id: true
            generator:
                strategy: AUTO
    fields:
        nombreEmpresa:
            type: string
            length: 255
        numEmpleados:
            type: integer

        fechaInscripcion:
            type: datetime
# Indicamos los campos Relación Muchos a uno (Cada EMPRESA tiene una CIUDAD)        
    manyToOne:
# Campo ciudad
        ubicacionCiudad:
            type: string
            length: 255
# Entidad Objetivo 'Ciudad'
            targetEntity: Ciudad
# Invertido por (indico la tabla a vincular)
            inversedBy: Empresa
# Relación entre tablas
            joinColumn:
# Nombre de la columna 'ciudad_id' dentro de la tabla Empresa
                name: ciudad_id
# Nombre de la columna referencia 'id' dentro de la tabla ciudad
                referencedColumnName: id
# Fin Relación Muchos a uno  
    lifecycleCallbacks: {  }

```

| src/CursoBundle/Resources/config/doctrine/Ciudad.orm.yml |
|----------------------------------------------------------|

```yml
CursoBundle\Entity\Ciudad:
    type: entity
    table: null
    repositoryClass: CursoBundle\Repository\CiudadRepository
    id:
        id:
            type: integer
            id: true
            generator:
                strategy: AUTO
    fields:
        nombreCiudad:
            type: string
            length: 255
# Indicamos Relación uno a muchos (Cada CIUDAD tiene muchas EMPRESAS)
    oneToMany:
        empresa:
# Entidad Objetivo 'Empresa'
            targetEntity: Empresa
# Mapeado por 'Ciudad'
            mappedBy: ciudad
# Fin Relación Muchos a uno
    lifecycleCallbacks: {  }
```

| Hay que introducir dentro de la Entidad **Ciudad** el campo empresa, su constructor y el método `__toString()` para poder incluir el selector. |
|:----------------------------------------------------------------------------------------------------------------------------------------------------|

| src/CursoBundle/Entity/Ciudad.php |
|-----------------------------------|

```php
    /*
     * Incluimos un método que nos enlace con la tabla empresa
     */

    /**
     * @var \Doctrine\Common\Collections\Collection
     */

    private $empresa;
    /**
     * Constructor
     */
    public function __construct()
    {
        // indicamos la procedencia de la función y la misma función
        $this->empresa = new \Doctrine\Common\Collections\ArrayCollection();
    }
    /**
     * Generates the magic method
     *
     */
    public function __toString(){
        // to show the name of the Category in the select
        return $this->nombreCiudad;
        // to show the id of the Category in the select
        // return $this->id;
    }
/* FIN DEL CÓDIGO */
```

----------------------------------------------------------

| IMPORTANTE!! |
|--------------|

* Actualizaremos las entidades mediante `php bin/console doctrine:generate:entities CursoBundle:Empresa` y `php bin/console doctrine:generate:entities CursoBundle:Ciudad`
* Utilizaremos el comando `php bin/console doctrine:schema:update --dump-sql` para consolidar la entidad mediante la ejecución de la query definida anteriormente.

* Posteriormente lanzaremos el comando de consola `php bin/console doctrine:schema:update --force` para hacer los cambios dentro de la base de datos.

Así, usando la línea de comando `php bin/console doctrine:generate:entities CursoBundle` se generarán también todos los **getters** y **setters**, incluidos los de relaciones entre tablas.

----------------------------------------------------------

6.3.Controlador - Relaciones entre tablas
-----------------------------------------

| src/CursoBundle/Resources/config/routing.yml |
|----------------------------------------------|

```yml
nueva_empresa_ciudad:
    path:     /empresa/nuevoConCiudad/
    defaults: { _controller: CursoBundle:Empresa:nuevoConCiudad }
```

| src\CursoBundle\Controller\EmpresaController.php |
|--------------------------------------------------|

```php
<?php

namespace CursoBundle\Controller;

use Symfony\Bundle\FrameworkBundle\Controller\Controller;   // Contiene el controlador
use CursoBundle\Entity\Empresa;                             // Contiene la Entidad EMPRESA
use CursoBundle\Form\EmpresaType;                           // Contiene el Formulario
use Symfony\Component\HttpFoundation\Request;               // Incluye la librería que capturará la información enviada por el formulario

class EmpresaController extends Controller
{
  public function nuevoConCiudadAction()
  {
    $ciudad = new Ciudad();

    $empresa = new Empresa();
    // Creamos el formulario
    $form = $this->createForm(EmpresaType::class,$empresa);
    // añadimos el 'Request' que capturará los datos del formulario
    $form->handleRequest($request);
    if ($form->isSubmitted() && $form->isValid()){
      // Si se envía el formulario y es Válido
      $empresa = $form->getData();
      $em = $this->getDoctrine()->getManager();
      $em->persist($empresa);
      $em->flush();
      // una vez cargado en la BD lanzo la notificación.
      return $this->redirectToRoute('exito_nueva_empresa');
    }
    return $this->render(
      'CursoBundle:Empresa:nuevaEmpresa.html.twig',
      array('form' => $form->createView())
    );
  }
}
```

| [Volver al inicio del capítulo](#6relaciones-entre-tablas-en-symfony3) | [Ver índice](#indice) |
|------------------------------------------------------------------------|-----------------------|

7.MOTOR DE CREACIÓN DE PLANTILLAS TWIG EN SYMFONY3
==================================================

Ver resumen de TWIG, [aquí](https://github.com/HecFranco/Apuntes/blob/master/Twig.md#1qué-es-twig).

7.1.¿Qué es Twig?
-----------------

Ver resumen de TWIG, [aquí](https://github.com/HecFranco/Apuntes/blob/master/Twig.md#1qué-es-twig).

| [Volver al inicio del capítulo](#7motor-de-creación-de-plantillas-twig-en-symfony3) | [Ver índice](#indice) |
|-------------------------------------------------------------------------------------|-----------------------|

7.2.Tags
--------

Ver resumen de TWIG, [aquí](https://github.com/HecFranco/Apuntes/blob/master/Twig.md#2tags).

| [Volver al inicio del capítulo](#7motor-de-creación-de-plantillas-twig-en-symfony3) | [Ver índice](#indice) |
|-------------------------------------------------------------------------------------|-----------------------|

7.2.1.¿Cómo usar IF?
--------------------

Ver resumen de TWIG, [aquí](https://github.com/HecFranco/Apuntes/blob/master/Twig.md#21cómo-usar-if).

| [Volver al inicio del capítulo](#7motor-de-creación-de-plantillas-twig-en-symfony3) | [Ver índice](#indice) |
|-------------------------------------------------------------------------------------|-----------------------|

7.2.2.¿Cómo usar FOR?
------------------

Ver resumen de TWIG, [aquí](https://github.com/HecFranco/Apuntes/blob/master/Twig.md#22cómo-usar-for).

| [Volver al inicio del capítulo](#7motor-de-creación-de-plantillas-twig-en-symfony3) | [Ver índice](#indice) |
|-------------------------------------------------------------------------------------|-----------------------|

7.2.3.¿Cómo usar los Tags/Bloques?
--------------------------------

Ver resumen de TWIG, [aquí](https://github.com/HecFranco/Apuntes/blob/master/Twig.md#23cómo-usar-los-tagsbloques).

| [Volver al inicio del capítulo](#7motor-de-creación-de-plantillas-twig-en-symfony3) | [Ver índice](#indice) |
|-------------------------------------------------------------------------------------|-----------------------|

7.3.¿Cómo realizar Rutas definiendo idiomas?
--------------------------------------------

Ver resumen de TWIG, [aquí](https://github.com/HecFranco/Apuntes/blob/master/Twig.md#3cómo-realizar-rutas-definiendo-idiomas).

| [Volver al inicio del capítulo](#7motor-de-creación-de-plantillas-twig-en-symfony3) | [Ver índice](#indice) |
|-------------------------------------------------------------------------------------|-----------------------|

8.OBJETO REQUEST
================

La clase `Request` es una representación orientada a objetos del mensaje de solicitud HTTP. Con él, usted tiene toda la información de la petición en sus yemas del dedo (Ver documentación oficial, [aquí](https://symfony.com/doc/current/introduction/http_fundamentals.html)).

```php
use Symfony\Component\HttpFoundation\Request;

$request = Request::createFromGlobals();

// the URI being requested (e.g. /about) minus any query parameters
$request->getPathInfo();

// retrieve $_GET and $_POST variables respectively
$request->query->get('id');
$request->request->get('category', 'default category');

// retrieve $_SERVER variables
$request->server->get('HTTP_HOST');

// retrieves an instance of UploadedFile identified by "attachment"
$request->files->get('attachment');

// retrieve a $_COOKIE value
$request->cookies->get('PHPSESSID');

// retrieve an HTTP request header, with normalized, lowercase keys
$request->headers->get('host');
$request->headers->get('content_type');

$request->getMethod();    // e.g. GET, POST, PUT, DELETE or HEAD
$request->getLanguages(); // an array of languages the client accepts
```

------------------------------------------------
**EJEMPLO REQUEST**
Veamos un ejemplo simple de como recoger los valores que nos llegan desde **GET** y **POST** en Symfony2. Simplemente tendremos que hacer uso de HttpFundation para acceder a diversas variables superglobales entre ellas **GET** y **POST**.

```php
<?php

namespace Ejemplos\PruebasBundle\Controller;

use Symfony\Bundle\FrameworkBundle\Controller\Controller;
use Symfony\Component\HttpFoundation\Response;
//Usar request http fundation
use Symfony\Component\HttpFoundation\Request;


class PruebasController extends Controller
{
    public function indexAction(Request $request){        
        //Recoger GET
        $var=$request->query->get("page");
        var_dump("GET:".$var);

        //Recoger POST
        $var=$request->request->get("page");
        var_dump("POST:".$var);        

        die();
    }
  }
```
Para comprobar esto podemos usar Postman el cual nos permite jugar con las urls, hacer peticiones a APIs y demás sin tener que crear los formularios. Hacemos una petición POST y GET con Postman para ver los resultados.

------------------------------------------------

| [Volver al inicio del capítulo](#8objeto-request) | [Ver índice](#indice) |
|---------------------------------------------------|-----------------------|

------------------------------------------------
**EJEMPLO REQUEST**

| src/CursoBundle/Resources/config/routing.yml |
|----------------------------------------------|

```yml
api_empresa:
    path:     /api/empresa_get/{nombre}
    defaults: { _controller: CursoBundle:Api:empresa, nombre:'Sin definir' }
    methods:  [GET]

api_empresa_crear:
    path:     /api/empresa_post/
    defaults: { _controller: CursoBundle:Api:crearEmpresa, nombre:'Sin definir' }
    methods:  [POST]
```

| src\CursoBundle\Controller\EmpresaController.php |
|--------------------------------------------------|

```php
<?php

/*
 * Extracto de Código
 */
class ApiController extends Controller
{
    //MENSAJES DEFINIDOS PARA USAR COMO MENSAJES
    const BAD_NAME_COMPANY="Falta nombre en la petición de empresa";
    const NO_ALL_ELEMENTS="Falta algún parámetro de la empresa para crearla";
    const NO_CONTENT="No se ha encontrado la empresa";
    const BAD_NAME_COMPANY_HELP="Ejemplo -> http://cursosymfony.com/curso/api/empresa/nombre_empresa";
    //Funcion que utilizamos para devolver una petición incorrecta
    private function badRequest($msg,$help=null)
    {
      return array(
        'mensage'=>$msg,
        'help'=>$help
      );
    }
    //Esta acción devuelve una empresa filtrada por nombre GET
    public function empresaAction($nombre)
    {
      if ($nombre=='Sin definir'){
        $response = new JsonResponse($this->badRequest(self::BAD_NAME_COMPANY,self::BAD_NAME_COMPANY_HELP), 400);
      }else{
        $repository = $this->getDoctrine()->getRepository('CursoBundle:Empresa');
        $empresa = $repository->findOneByNombre($nombre);
        if(isset($empresa)){
          $data['empresa'][] = $this->serializeEmpresa($empresa);
          $response = new JsonResponse($data, 200);
        }else{
          $response = new JsonResponse($this->badRequest(self::NO_CONTENT,"Empresa buscada: ".$nombre), 200);
        }
      }
      return $response;
    }
    //Esta acción inserta una empresa
    public function crearEmpresaAction(Request $request)
    {
      //En primer lugar comprobaremos que todos los campos necesarios
      //para la inserción existen
      if($request->request->get('nombre')==null || $request->request->get('ciudad')==null || $request->request->get('numEmpleados')==null)
        {
          $response = new JsonResponse($this->badRequest(self::NO_ALL_ELEMENTS,""), 400);
        }else{
          //generamos la empresa a partir de los datos
          $empresa = new Empresa();
          $empresa->setNombre($request->request->get('nombre'));
          $empresa->setCiudad($request->request->get('ciudad'));
          $empresa->setNumEmpleados($request->request->get('numEmpleados'));
          //Salvamos la empresa
          $em = $this->getDoctrine()->getManager();
          $em->persist($empresa);
          $em->flush();
          //Devolvemos la empresa en el JsonResponse
          $data['empresa'][] = $this->serializeEmpresa($empresa);
          $response = new JsonResponse($data, 200);
        }
        return $response;
    }
/*
 * Fin Extracto de Código
 */  
```

| [Volver al inicio del capítulo](#8objeto-request) | [Ver índice](#indice) |
|---------------------------------------------------|-----------------------|







9.SECURITY.YML
==============

Desde **app\config\security.yml** podemos gestionar la seguridad de la aplicación ya sea con respecto a los encriptados de contraseñas (veáse [Registro de Usuarios](#extra---registro-de-usuarios)), como los permisos de acceso (Ver documentación oficial, [aquí](https://symfony.com/doc/current/security.html))

9.1.Permisos de acceso
----------------------

Dentro de **app\config\security.yml** podemos añadir el siguiente código para indicar el tipo de encriptado que se usará para almacenar el contenido de la *Entidad User*.

```yml
security:
    encoders:
        UserBundle\Entity\User: bcrypt
```
Dentro de **app\config\security.yml** tenemos también indicada la seguridad de acceso a los archivos durante el modo *developer*.
```yml
    firewalls:
        # disables authentication for assets and the profiler, adapt it according to your needs
        dev:
            pattern: ^/(_(profiler|wdt)|css|images|js)/
            security: false
```
Además **app\config\security.yml** indica por defecto que el contenido es solo accesible al usuario *anonumous*, con el cual entramos siempre por defecto en modo *developer*.
```yml
        main:
            anonymous: ~
```
Posteriormente realizaremos las siguientes modificaciones (ver documentación oficial, [security](http://symfony.com/doc/current/reference/configuration/security.html)):

| app\config\security.yml |
|-------------------------|

```yml
# To get started with security, check out the documentation:
# https://symfony.com/doc/current/security.html
security:
    encoders:
	# Añadimos el encriptador para la entidad User de USerBundle
        UserBundle\Entity\User: bcrypt
	# Añadimos el encriptador de texto plano y su librería
	Symfony\Component\Security\Core\User\User: plaintext
    # https://symfony.com/doc/current/security.html#b-configuring-how-users-are-loaded
    providers:
        in_memory:
            memory:
	        users:
		    ryan:
		        password: ryanpass
			roles: 'ROLE_USER'
		    admin:
		        password: kitten
			roles: 'ROLE_ADMIN'
    firewalls:
        # disables authentication for assets and the profiler, adapt it according to your needs
        dev:
            pattern: ^/(_(profiler|wdt)|css|images|js)/
            security: false
        # Indicamos que el usuario Admin necesitará acceso a través de un formulario 'http_basic'
	# a las urls que empiecen por '/admin/'
	admin:
	    pattern: ^/admin
	    http_basic: ~
	users:
	    pattern: ^/users
	    anonymous: ~
            form_logn:
	    	# dónde se va a generar el controlador
	        login_path: /users/login
		# cuál va a ser el controlador
		check_path: /users/login
        main:
            anonymous: ~
            # activate different ways to authenticate

            # https://symfony.com/doc/current/security.html#a-configuring-how-your-users-will-authenticate
            #http_basic: ~

            # https://symfony.com/doc/current/security/form_login_setup.html
            #form_login: ~
```

9.1.1. Recursos importantes
---------------------------

* Web de expresiones regulares y su significado - [regexr.com](https://regexr.com/)
* Documentación symfony Seguridad. [aquí](https://symfony.com/doc/current/security.html)

9.2.Acceso a roles
------------------


EXTRA - RESUMEN DE COMANDOS CONSOLA PARA SYMFONY3
=================================================

**CREAR PROYECTO - PHP**

* `php symfony new my_project_name` - Crea un nuevo proyecto.

**CREAR PROYECTO - COMPOSER**
* `composer create-project symfony/framework-standard-edition my_project_name` - Instala un nuevo proyecto de Symfony llamado *my_project_name*.
* `composer create-project symfony/framework-standard-edition my_project_name/ "3.0.0"`
* `composer dump-autoload` - Ejecuta la función autoload

**COMANDOS BIN/CONSOLE SISTEMA**

* `php bin/console`
* `php bin/console server:run`
* `php bin/console cache:clear --env=prod`
* `php bin/console security:check`

**COMANDOS BIN/CONSOLE BUNDLE**

* `php bin/console generate:bundle`
* `php bin/console generate:bundle --namespace=PruebaBundle `

--------------------------------------------------------------

Genera dentro del Bundle **Controller\DefaultController.php** y **Resources\views\Default\index.html.twig**

--------------------------------------------------------------

**COMANDOS BIN/CONSOLE ENTIDADES**

* `php bin/console doctrine:generate:entity` - Inicia el Wizard que permite crear un nuevo Bunlde.
* `php bin/console doctrine:generate:entity --format=annotation`
* `php bin/console doctrine:generate:entity --no-interaction --entity="CursoBundle:Ciudad" --fields="ciudad:string(255)"`
* `php bin/console doctrine:generate:entity AcmeBlogBundle:Post -n --fields="title:string(100) body:text" --format=xml`
* `php bin/console doctrine:generate:entity AcmeBlogBundle:Post -n --fields="title:string(100) body:text" --format=xml`
* `php bin/console doctrine:generate:entity --fields="title:string(length=100 nullable=true unique=false) body:text ranking:decimal(precision=10 scale=0)"`
* `php bin/console doctrine:generate:entities CursoBundle` - Actualiza las entidades generadas dentro de CursoBundle (necesario en cada actualización de datos de la entidad), permite crear los **setters** y **getters**
* `php bin/console doctrine:mapping:info` - Lista todas las entidades creadas en el proyecto
* `php bin/console doctrine:mapping:import BackendBundle yml` - Importa la configuración de tablas del bundle **BackendBundle** a sus distintos archivos **orm.yml** dentro de **src\BackendBundle\Resources\config\doctrine\**

--------------------------------------------------------------

Genera dentro del Bundle **Entity\User.php**, **Repository\UserRepository.php** y **Resources\config\doctrine\User.orm.yml**

--------------------------------------------------------------

**COMANDOS BIN/CONSOLE BASE DE DATOS**

* `php bin/console doctrine:database:create` - Crear una nueva Base de Datos a partir de la configuración en **app\config\parameters.yml**
* `php bin/console doctrine:database:drop` - Borrar una Base de Datos
* `php bin/console doctrine:database:drop --force` - Borrar una Base de Datos (sin cuestionar)
* `php bin/console doctrine:schema:update` - Actualizar una Base de Datos
* `php bin/console doctrine:schema:update --force` - Actualizar una Base de Datos (sin cuestionar)
* `php bin/console doctrine:schema:update --dump-sql`
* `php bin/console doctrine:schema:update --force --dump-sql` - Nos mostrará la sentencia que se lanzará y modificará la base de datos.
* `php bin/console doctrine:schema:create` - Crear una tabla dentro de la Base de Datos

**COMANDOS BIN/CONSOLE CRUD**

* `php bin/console generate:doctrine:crud`

--------------------------------------------------------------

Genera dentro del Bundle **Controller\UserController.php**.

--------------------------------------------------------------


**COMANDOS BIN/CONSOLE FORMULARIO**

* `php bin/console doctrine:generate:form CursoBundle:Empresa` - Es necesario indicar la entidad y el Bundle sobre los cuales se elaborará el formulario.

--------------------------------------------------------------

Genera dentro del Bundle **Form\UserType.php**.

--------------------------------------------------------------

| [Volver al inicio del capítulo](#extra---resumen-de-comandos-consola-para-symfony3) | [Ver índice](#indice) |
|-------------------------------------------------------------------------------------|-----------------------|

EXTRA - PÁGINA NOTFOUND. ERROR404
=================================

Para ello lanzaremos la excepción `createNotFoundException()` de forma que podremos indicar el mensaje a mostrar cuando se produzca la **excepción** a nivel de **developer** (entorno de desarrollo).

| src\PruebaBundle\Controller\DefaultController.php |
|---------------------------------------------------|

```php
<?php

namespace PruebaBundle\Controller;

use Symfony\Bundle\FrameworkBundle\Controller\Controller;

class DefaultController extends Controller
{
   public function contactarAction($lugar)
   {
      if($lugar=='vlc'){
      // 'prueba_contactar_vlc' es una ruta definida dentro del 'routing.yml del bundle
        return $this->redirect($this->generateUrl('prueba_contactar_vlc'));
      }else{
        throw $this->createNotFoundException('Te Has Equivocado');
      }
   }
}
```

(Ver documentación oficial [aquí](https://symfony.com/doc/current/controller/error_pages.html)) Las plantillas para la **Excepcion 404** se encuentra dentro de **vendor\symfony\symfony\src\Bundle\TwigBundle\Resource\views\Exception\** tenemos la plantilla **error.html.twig** que es quién nos lanzará la Excepcióna mostrar en producción.

| *Nota*: Se recomienda mover esta plantilla a app\Resources\TwigBundle\views\Exception\ para su modificación y una vez dentro lanzar el comando de consola que limpia la caché en producción `php bin/console cache:clear --env=prod`, lanzar el servidor mediante el comando `php bin/console server:run`y activar la base de datos. |
|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|

| [Volver al inicio del capítulo](#extra---pÁgina-notfound-error404) | [Ver índice](#indice) |
|--------------------------------------------------------------------|-----------------------|

EXTRA - REGISTRO DE USUARIOS
============================

Para el registro de usuarios habrá que actuar sobre la **Entidad** (*User*), **Controller** (*UserController*), **Security** (*security.yml*) y **Form** (*UserType*). (Ver documentación oficial, [aquí](http://symfony.com/doc/current/doctrine/registration_form.html)).

Hay que tener en cuenta que la entidad **Entity User** implementa a **Userinterface**.

* Creamos el proyecto `composer create-project symfony/framework-standard-edition my_project_name`
* Editamos la configuración de **app\config\parameters.yml** y creamos la base de datos mediante `php bin/console doctrine:database:create`.
* Creamos un nuevo bundle para la gestión de usuarios escribiendo en consola `php bin/console generate:bundle`.

| **Are you planning on sharing this bundle across multiple applications? [no]:**       | no           |
|:--------------------------------------------------------------------------------------|--------------|
| **Give your bundle a descriptive name, like BlogBundle. Bundle name [BlogBundle]:**   | UserBundle   |
| **Target Directory [src/]:**                                                          | src/         |
| **Configuration format (annotation, yml, xml, php) [annotation]:**                    | yml          |

| [Volver al inicio del capítulo](#extra---registro-de-usuarios) | [Ver índice](#indice) |
|----------------------------------------------------------------|-----------------------|

1.¿Cómo crear la entidad User?
-------------------------------

* Generamos una nueva entidad mediante `php bin/console doctrine:generate:entity`
    * **The Entity shortcut name:** UserBundle:User
    * **Configuration format (yml,xml,php,or annotation)[annotation]:** yml

* Para el primer **New field name**, usaremos: `userName`.

| Field type [string] | Field length [255] | Is nullable [false] | Unique [false] |
|---------------------|--------------------|---------------------|----------------|
| string              | 255                | false               | true           |

* Para el primer **New field name**, usaremos: `password`.

| Field type [string] | Field length [255] | Is nullable [false] | Unique [false] |
|---------------------|--------------------|---------------------|----------------|
| string              | 64                 | false               | true           |

* Para el primer **New field name**, usaremos: `email`.

| Field type [string] | Field length [255] | Is nullable [false] | Unique [false] |
|---------------------|--------------------|---------------------|----------------|
| string              | 512                | false               | true           |


* Lanzaremos el comando `php bin/console doctrine:schema:update --force` para actualizar la Base de Datos según la entidad generada.

----------------------------------------------

| POSIBLE FALLO SYMFONY 3.3 |
|---------------------------|
Puede dar error al ejecutarlo, lanzando el siguiente mensaje **Fatal error: Class 'PruebaBundle' not found in C:\wamp64\www\symfony.test\app\AppKernel.php on line 19** (Ver hilo con solución, [aquí](https://stackoverflow.com/questions/17584041/class-not-found-in-appkernel-php)).

En este caso el error se encontraba dentro de C:\wamp64\www\symfony.test\composer.json, dónde había que modificar la siguiente línea

```json
"autoload": {
        "psr-4": {
            "": "src/"
        },
        "classmap": [ "app/AppKernel.php", "app/AppCache.php" ]
    }
```

| **MUY IMPORTANTE** ejecutar `composer dump-autoload` para ejecutar la función autoload. |
|-----------------------------------------------------------------------------------------|

| [Volver al inicio del capítulo](#extra---registro-de-usuarios) | [Ver índice](#indice) |
|----------------------------------------------------------------|-----------------------|

2.¿Cómo modificar la entidad User Cambios Básicos?
---------------------------------------------------

* Es necesario incluir una serie de componentes para este tipo de entidad.
```php
// src\UserBundle\Entity\User.php
/* Inicio Extracto de código */
use Symfony\Component\Validator\Constraints as Assert;
use Symfony\Bridge\Doctrine\Validator\Constraints\UniqueEntity;
use Symfony\Component\Security\Core\User\UserInterface;
/* Fin Extracto de código */
```
* La clase incluida dentro de esta entidad **src\UserBundle\Entity\User.php**, `class User{}` deberá implementar a **UserInterface**, quedando así `class User implements UserInterface`.
```php
// src\UserBundle\Entity\User.php
/* Inicio Extracto de código */
class User implements UserInterface
{
/* Fin Extracto de código */
```

| [Volver al inicio del capítulo](#extra---registro-de-usuarios) | [Ver índice](#indice) |
|----------------------------------------------------------------|-----------------------|

2.1. ¿Cómo modificar la entidad User, '$plainPAssword' ?
--------------------------------------------------------

* Además hay que utilizar la variable `$plainPassword` que no estará enlazada con la base de datos.
```php
// src\UserBundle\Entity\User.php
/* Inicio Extracto de código */
 /**
     * @Assert\NotBlank()
     * @Assert\Length(max=4096)
     */
    private $plainPassword;
/* Fin Extracto de código */
```
* E incluir el método `public function getPlainPassword(){}` que no estará enlazada con la base de datos.
```php
// src\UserBundle\Entity\User.php
/* Inicio Extracto de código */
    public function getPlainPassword()
    {
        return $this->plainPassword;
    }

    public function setPlainPassword($password)
    {
        $this->plainPassword = $password;
    }
/* Fin Extracto de código */
```

| *Nota*: Para regenerar los **setters** y **getters** de la variable `$plainPassword` es necesario lanzar la línea de comando `php bin/console doctrine:schema:update --force`. |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|

| [Volver al inicio del capítulo](#extra---registro-de-usuarios) | [Ver índice](#indice) |
|----------------------------------------------------------------|-----------------------|

2.2. ¿Cómo modificar la entidad User, métodos extra necesarios?
---------------------------------------------------------------

* Mediante `public function getSalt(){}`, podremos codificar el **password** (Devuelve el codificador que se utilizó originalmente para codificar la contraseña.) [Crear un usuario personalizado](https://symfony.com/doc/current/security/custom_provider.html) (Ver documentación oficial, [aquí](http://api.symfony.com/3.3/Symfony/Component/Security/Core/User/UserInterface.html#method_getSalt))
```php
// src\UserBundle\Entity\User.php
    public function getSalt()
    {
        // The bcrypt algorithm doesn't require a separate salt.
        // You *may* need a real salt if you choose a different encoder.
        return null;
    }
```
* Mediante `public function getRoles(){}`, podremos obtener el **rol** otorgado al usuario. [Crear un usuario personalizado](https://symfony.com/doc/current/security/custom_provider.html) (Ver documentación oficial, [aquí](http://api.symfony.com/3.3/Symfony/Component/Security/Core/User/UserInterface.html#method_getRoles))
```php
// src\UserBundle\Entity\User.php
    public function getRoles()
    {
        return array('ROLE_USER');
    }
```

* Mediante `public function eraseCredentials(){}`, se eliminan datos sensibles del usuario, esto es importante si, en un punto dado, la información sensible como la contraseña de texto sin formato se almacena en este objeto. [Crear un usuario personalizado](https://symfony.com/doc/current/security/custom_provider.html) (Ver documentación oficial, [aquí](http://api.symfony.com/3.3/Symfony/Component/Security/Core/User/UserInterface.html#method_eraseCredentials))
```php
// src\UserBundle\Entity\User.php
    public function eraseCredentials()
    {
    }
```

| [Volver al inicio del capítulo](#extra---registro-de-usuarios) | [Ver índice](#indice) |
|----------------------------------------------------------------|-----------------------|


3.¿Cómo crearemos validaciones?
--------------------------------

* Para incluir validaciones entraremos dentro de **app/config/config.yml** dónde indicaremos el sistema a utilizar para indicarlas (*Annotation* o *yml*, nosotros elegiremos **yml**):

| app/config/config.yml |
|-----------------------|

```yml
# app/config/config.yml
framework:
# Para sistema yml utlizaremos #
    validation: { enabled: true }
```
```yml
# app/config/config.yml
framework:
# Para anotación (por defecto) utlizaremos #
    validation: { enable_annotations: true }
```

* Posteriormente crearemos el archivo **src/UserBundle/Resources/config/validation.yml**

| src/UserBundle/Resources/config/validation.yml|
|-----------------------------------------------|
```yml
UserBundle\Entity\User:
    properties:
        userName:
            - NotBlank: ~
            - Length:
                min: 2
                max: 16
                minMessage: 'Tu Nombre de Usuario debe ser mayor de {{ limit }} caracteres de longitud.'
                maxMessage: 'Tu Nombre de Usuario no puede ser mayor de {{ limit }} caracteres de longitud.'
        email:
            - Email:
                message: 'El email {{ value }} no es válido.'
                checkMX: true
# El password no es necesario indicarlo, ya que solo queremos que no sea
# blanco y por defecto el formulario inspecciona eso.

UserBundle\Form\Model\ChangePassword:
    properties:
        oldPassword:
            - Symfony\Component\Security\Core\Validator\Constraints\UserPassword:
                message: 'Valor incorrecto para su contraseña actual'
```
En caso de querer utilizar el sistema de *Annotation* para las validacioneslo indicaremos dentro de **app/config/config.yml**, y posteriormente modificaremos **src\UserBundle\Resources\config\Doctrine\User.orm.yml**, añadiendo **Asserts** para gestionar la validación del contenido introducido en cada uno de los campos (Ver documentación relativa a [**Asserts**](https://symfony.com/doc/current/validation.html)).


| [Volver al inicio del capítulo](#extra---registro-de-usuarios) | [Ver índice](#indice) |
|----------------------------------------------------------------|-----------------------|

4.¿Cómo modificar el controlador?
----------------------------------

El siguiente paso consiste en generar el **CRUD** para la entidad **UserBundle:User** mediante el comando de consola `php bin/console generate:doctrine:crud UserBundle:User`.

| The Entity shortcut name:                                         | UserBundle:User |
|:------------------------------------------------------------------|-----------------|
| Do you want to generate the "write" actions [no]?                 | yes             |
| Configuration format (yml, xml, php, or annotation) [annotation]: | yml             |
| Routes prefix [/user]:                                            | user            |

*Nota*: Si se generó el Formulario antes indicará que **UserType** ya se creó y no puede crearse.

Posteriormente añadiremos un nuevo método dentro la clase de **src\UserBundle\Controller\UserController.php** (Ver documentación oficial, [aquí](http://symfony.com/doc/current/doctrine/registration_form.html)).

 ```php
 // src\UserBundle\Controller\UserController.php
/* Añadimos el componente 'Request'                       */
use UserBundle\Entity\User;
use Symfony\Component\HttpFoundation\Request;
use Symfony\Component\HttpFoundation\Response;
use UserBundle\Form\UserType;
use Symfony\Component\Security\Core\Encoder\UserPasswordEncoderInterface;
/**********************************************************/
/* Añadimos el método 'public function registerAction()'  */
    public function registerAction(Request $request)
    {
        // 1) construir el formulario
        $user = new User();
        $form = $this->createForm(UserType::class, $user);

        // 2) manejar el envío (sólo sucederá en POST)
        $form->handleRequest($request); //Necesitaremos el componente Request
        if ($form->isSubmitted()  && $form->isValid()) {
            /* 3) Codifique la contraseña (también podría hacerlo a través
             * del Doctrine listener) */
            // $password = $passwordEncoder->encodePassword($user, $user->getPlainPassword());
            $password = $this->get('security.password_encoder')
                ->encodePassword($user, $user->getPlainPassword());            
            $user->setPassword($password);
            // 4) save the User!
            $em = $this->getDoctrine()->getManager();
            $em->persist($user);
            $em->flush();
            // ... hacer cualquier otro trabajo - como enviarles un correo electrónico, etc
            // quizás establecer un mensaje de "flash" de éxito para el User
            return new Response("Usuario registrado");
        }
        return $this->render(
            'UserBundle:user:register.html.twig',
            array('form' => $form->createView())
        );
    }
/**********************************************************/
```

A continuación creamos la vista para el formulario en **src/UserBundle/Resources/views/registration/register.html.twig**.

```twig
{# src/UserBundle/Resources/views/registration/register.html.twig #}
{{ form_start(form) }}
  {{ form_row(form.userName) }}
  {{ form_row(form.email) }}
  {{ form_row(form.plainPassword.first) }}
  {{ form_row(form.plainPassword.second) }}
  {{ form_row(form.guardar) }}
  {{ form_row(form.borrar) }}
{{ form_end(form) }}
```

```yml
# app/config/security.yml
security:
    encoders:
        UserBundle\Entity\User: bcrypt
```

| [Volver al inicio del capítulo](#extra---registro-de-usuarios) | [Ver índice](#indice) |
|----------------------------------------------------------------|-----------------------|

5.¿Cómo crearemos el Formulario?
---------------------------------

*Nota*: Si previamente se hizo el **CRUD**, no será necesario realizar un formulario

Ejecutaremos la línea de comando `php bin/console generate:doctrine:form UserBundle:User`, el cual generará el archivo **src\UserBundle\Form\UserType** que habrá que modificarlo de la siguiente manera:
* Referenciamos la entidad que se usará incluyendo `use UserBundle\Entity\User;`.
* Además hay que añadir las extensiones de formulario relativas a los tipos de entradas del formulario (Ver documentación oficial, [PasswordType](http://symfony.com/doc/current/reference/forms/types/password.html)).
```php
use Symfony\Component\Form\Extension\Core\Type\EmailType;
use Symfony\Component\Form\Extension\Core\Type\TextType;
use Symfony\Component\Form\Extension\Core\Type\RepeatedType;
use Symfony\Component\Form\Extension\Core\Type\PasswordType;
use Symfony\Component\Form\Extension\Core\Type\SubmitType;   // incluir el botón de envío.
use Symfony\Component\Form\Extension\Core\Type\ResetType;    // incluir el botón de borrar
```
* Dentro de `class UserType extends AbstractType{}` modificaremos el método `public function buildForm(FormBuilderInterface $builder, array $options)` para que quede así (Ver documentación oficial, [aquí](http://symfony.com/doc/current/doctrine/registration_form.html)):
```php
    public function buildForm(FormBuilderInterface $builder, array $options)
    {
        $builder
/* Es necesario indicar el tipo de entrada definiendo
 * la clase                                               */        
            ->add('email', EmailType::class)
            ->add('userName', TextType::class)
/* Comentamos la opción password                          */
//          ->add('password')
/* Añadimos 'plainPassword'                               */
            ->add('plainPassword', RepeatedType::class, array(
                'type' => PasswordType::class,
                'first_options'  => array('label' => 'Contraseña'),
                'second_options' => array('label' => 'Repite Contraseña'),
            ))
/**********************************************************/
/* Añadimos 'submitType' y 'resetType'                    */
            ->add('guardar',SubmitType::class)
            ->add('borrar',ResetType::class)
/**********************************************************/
        ;
    }
```
Finalmente **src\UserBundle\Form\UserType** quedará así:

| src\UserBundle\Form\UserType |
|------------------------------|

```php
<?php

namespace UserBundle\Form;

/* Referenciamos la entidad */
use UserBundle\Entity\User;
/**********************************************************/
use Symfony\Component\Form\AbstractType;
use Symfony\Component\Form\FormBuilderInterface;
use Symfony\Component\OptionsResolver\OptionsResolver;
/* Añadimos las extensiones de formulario relativas a los
 * tipos de entradas                                     */
use Symfony\Component\Form\Extension\Core\Type\EmailType;
use Symfony\Component\Form\Extension\Core\Type\TextType;
use Symfony\Component\Form\Extension\Core\Type\RepeatedType;
use Symfony\Component\Form\Extension\Core\Type\PasswordType;
use Symfony\Component\Form\Extension\Core\Type\SubmitType;   // incluir el botón de envío.
use Symfony\Component\Form\Extension\Core\Type\ResetType;    // incluir el botón de borrar
/**********************************************************/
class UserType extends AbstractType
{
    /**
     * {@inheritdoc}
     */
    public function buildForm(FormBuilderInterface $builder, array $options)
    {
        $builder
/* Es necesario indicar el tipo de entrada definiendo
 * la clase                                               */        
            ->add('email', EmailType::class,
                array('attr' => array('class' => 'form-control','placeholder'=>'email de registro')))
            ->add('userName', TextType::class,
                array('attr' => array('class' => 'form-control','placeholder'=>'nombre de usuario')))
/* Comentamos la opción password                          */
//          ->add('password')
/* Añadimos 'plainPassword'                               */
            ->add('plainPassword', RepeatedType::class,
              array('type' => PasswordType::class,
                'first_options' =>
                  array('label' => 'Contraseña','attr'=>array('class' => 'form-control', 'placeholder'=>'introduce contraseña')),
                'second_options' =>
                  array('label' => 'Repite Contraseña','attr' => array('class' => 'form-control','placeholder'=>'repite contraseña'))
                ))
/**********************************************************/
/* Añadimos 'submitType' y 'resetType'                    */
            ->add('guardar',SubmitType::class, array('attr' => array('class' => 'btn btn-default submit')))
            ->add('borrar',ResetType::class, array('attr' => array('class' => 'btn btn-default submit')))
/**********************************************************/
        ;
    }
    /**
     * {@inheritdoc}
     */
    public function configureOptions(OptionsResolver $resolver)
    {
        $resolver->setDefaults(array(
            'data_class' => 'UserBundle\Entity\User'
        ));
    }
    /**
     * {@inheritdoc}
     */
    public function getBlockPrefix()
    {
        return 'userbundle_user';
    }
}
```

| app\Resources\views\base.html.twig |
|------------------------------------|

```twig
<!DOCTYPE html>
<html>
    <head>
        <meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
        <!-- Meta, title, CSS, favicons, etc. -->
        <meta charset="utf-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1">
        <title>
            {% block title %}
                Gentelella Alela! |
            {% endblock %}
        </title>
        {% block stylesheets %}
            <!-- Bootstrap -->
            <link href="{{ asset('css/bootstrap.min.css') }}" rel="stylesheet">
            <!-- Font Awesome -->
            <link href="{{ asset('css/font-awesome.min.css') }}" rel="stylesheet">
            <!-- NProgress -->
            <link href="{{ asset('css/nprogress.css') }}" rel="stylesheet">
            <!-- Animate.css -->
            <link href="{{ asset('css/animate.min.css') }}" rel="stylesheet">

            <!-- Custom Theme Style -->
            <link href="{{ asset('css/custom.min.css') }}" rel="stylesheet">
        {% endblock %}
        <link rel="icon" type="image/x-icon" href="{{ asset('favicon.ico') }}" />
    </head>

        {% block body %}    
            <body>
            </body>
        {% endblock %}
        {% block javascripts %}{% endblock %}

</html>
```

| src\UserBundle\Resources\views\user\register.html |
|---------------------------------------------------|

```twig
{% extends 'base.html.twig' %}
{% block title %}Registro{% endblock %}
{% block body %}
  	<body class="login">
	  	<div>
			<a class="hiddenanchor" id="signup"></a>
			<a class="hiddenanchor" id="signin"></a>
			<div class="login_wrapper">
		       	<div class="animate form login_form">
		       		<section class="login_content">
						{{ form_start(form) }}
							<div>
					  			{{ form_widget(form.userName)  }}
					  		</div>
							<div>
					  			{{ form_widget(form.email) }}
					  		</div>
							<div>
								{{ form_widget(form.plainPassword.first) }}
					  		</div>
							<div>
					  			{{ form_widget(form.plainPassword.second) }}
					  		</div>
							<div>
					  			{{ form_widget(form.guardar) }}
					  			{{ form_widget(form.borrar) }}
					  		</div>
						{{ form_end(form) }}
					</section>
	        	</div>
		    </div>
	    </div>
  	</body>
{% endblock %}
```

| [Volver al inicio del capítulo](#extra---registro-de-usuarios) | [Ver índice](#indice) |
|----------------------------------------------------------------|-----------------------|

EXTRA - LOGIN DE USUARIOS
=========================

1.Configuración Inicial
-----------------------

* Genero un nuevo **Bundle** mediante la línea de comando `php bin/console generate:bundle` (Ver documentación oficial, [aquí](https://symfony.com/doc/current/security.html)).

| **Are you planning on sharing this bundle across multiple applications? [no]:**       | no            |
|:--------------------------------------------------------------------------------------|---------------|
| **Give your bundle a descriptive name, like BlogBundle. Bundle name [BlogBundle]:**   | AdminBundle   |
| **Target Directory [src/]:**                                                          | src/          |
| **Configuration format (annotation, yml, xml, php) [annotation]:**                    | yml           |

| [Volver al inicio del capítulo](#extra---registro-de-usuarios) | [Ver índice](#indice) |
|----------------------------------------------------------------|-----------------------|

* Modificamos la ruta de acceso a **AdminBundle** dentro de **app\config\routing.yml**.

```yml
# app\config\routing.yml
admin:
    resource: "@AdminBundle/Resources/config/routing.yml"
    prefix:   /admin

user:
    resource: "@UserBundle/Resources/config/routing.yml"
    prefix:   /user
```

```yml
# src\userBundle\Resources\config\routing.yml
user_registration:
    path:     /register
    defaults: { _controller: UserBundle:User:register }

# Es necesario que exista un raiz para que no se produzca un error al redireccionar.
users:
    path:     /
    defaults: { _controller: UserBundle:User:users }

login:
    path:     /login
    defaults: { _controller: UserBundle:User:login }

logout:
    path: /logout
```
----------------------------------------------------------

*Nota*: Para mostrar el **Debug Symfony**, hay que dentro de la plantilla autogenerada por el nuevo Bunle (**AdminBundle**) **src\AdminBundle\Resoureces\views\Default\index.html.twig** colocar unas etiquetas `<body></body>`, tal que así: `
<body>ZONA ADMIN</Body> `

----------------------------------------------------------

* Posteriormente accedemos a **app\config\security.yml** para incluir la configuración que nos permita entrar automáticamnete como **admin*** dentro de la configuración del **firewall** tan sólo entrando a la url **127.0.0.1:8000/admin/**.
```yml
# app\config\security.yml
    firewalls:
        admin:
            anonymous: ~
            pattern: ^/admin
```

1.1.¿Cómo definir los mecanismos de entrada?
--------------------------------------------

* Volvemos a modificar el archivo **app\config\security.yml** para indicar el mecanismo de entrada que se utilizará (Ver documentación oficial, [aquí](https://symfony.com/doc/current/security.html))
```yml
# app\config\security.yml
# extracto de código
firewalls:
        admin:
#            anonymous: ~
            pattern: ^/admin
            http_basic: ~
# extracto de código
```
*Nota*: Si accedieramos a la url **127.0.0.1:8000/admin/** definida anteriormente en **app\config\routing.yml** nos encontraríamos con uns sistema de autentificación externo. (Si colocásemos un loguin no nos dejaría entrar al no estar definido)

1.2.¿Cómo añadir usuarios?
------------------------

* Dentro de **app\config\security.yml** incluiremos el siguiente código que definirá el **provider** de acceso (Ver documentación oficial, [aquí](https://symfony.com/doc/current/security.html))
```yml
# app\config\security.yml
# https://symfony.com/doc/current/security.html#b-configuring-how-users-are-loaded
# extracto de código
providers:
        in_memory:
#            memory: ~
            memory:
                users:
                    ryan:
                        password: ryanpass
                        roles: 'ROLE_USER'
                    admin:
                        password: kitten
                        roles: 'ROLE_ADMIN'
# extracto de código
```

*Nota*: Al acceder a la url **127.0.0.1:8000/admin/** definida anteriormente en **app\config\routing.yml** nos encontraríamos con uns sistema de autentificación externo, en el cual al loguearnos con **ryan** y su password **ryanpass** nos desviará a una página de error en la que se nos advierte que aún no se definión un codificador para la autentificación. (Si colocásemos un loguin no nos dejaría entrar al no estar definido)

* Para definir el encoder (Ver documentación oficial, [aquí](https://symfony.com/doc/current/security.html)) dentro de **app\config\security.yml** añadiremos:

```yml
# app\config\security.yml
# https://symfony.com/doc/current/security.html
# extracto de código
security:
    encoders:
        UserBundle\Entity\User: bcrypt # configura el encriptador del sistema de registro
        Symfony\Component\Security\Core\User\User: plaintext # configura el encoder del login
# extracto de código
```

**FINALMENTE YA NOS HABREMOS LOGUEADO COMO RYAN**

2.Seguridad en LOGIN Y LOGOUT
-----------------------------

* Dentro de **app\config\security.yml** añadiremos el **firewall* que gestionará los accesos (Ver documentación oficial, [aquí](https://symfony.com/doc/current/security/form_login_setup.html))

```yml
    firewalls:
# extracto de código
        user:
            pattern: ^/user #url
            anonymous: ~
            provider: in_memory # definimos los usuarios de acceso al logueo
            form_login:
                login_path: /user/login #dónde se va a generar el formulario
                check_path: /user/login #dónde se encuentra el controlador de chekado
            logout:
                path:   /user/logout
                target: /user
# extracto de código
```
*Nota*: Es importante no olvidar incluir al final del archivo estas líneas para evitar bucles infinitos. (Ver documentación oficial, [aquí](https://symfony.com/doc/current/security/form_login_setup.html))
```yml
# extracto de código
    access_control:
      - {path: ^/user/login,roles: IS_AUTHENTICATED_ANONYMOUSLY}
      - {path: ^/user,roles: ROLE_ADMIN}
# extracto de código
```

3.Controlador y método login
----------------------------

A continuación dentro del controlador del Bundle incluiremos el método que gestionará el acceso:

```php
// src\UserBundle\Controller\UserConroller.php
/* Extracto de código */    
    public function usersAction(Request $request)
    {
        return $this->render('UserBundle:Default:index.html.twig');
    }

    public function loginAction(Request $request)
    {
        $authenticationUtils = $this->get('security.authentication_utils');

        // obtener el error de inicio de sesión si lo hubo
        $error = $authenticationUtils->getLastAuthenticationError();

        // último nombre de usuario introducido por el usuario
        $lastUsername = $authenticationUtils->getLastUsername();

        return $this->render('UserBundle:User:login.html.twig', array(
            'last_username' => $lastUsername,
            'error'         => $error,
        ));
    }
/* Extracto de código */
```

4.Vistas del Formulario
-----------------------

La vista del formulario será **app/Resources/views/security/login.html.twig**.
```twig
<body>
{# app/Resources/views/security/login.html.twig #}
{# ... you will probably extend your base template, like base.html.twig #}

{% if error %}
    <div>{{ error.messageKey|trans(error.messageData, 'security') }}</div>
{% endif %}

<form action="{{ path('login') }}" method="post">
    <label for="username">Username:</label>
    <input type="text" id="username" name="_username" value="{{ last_username }}" />

    <label for="password">Password:</label>
    <input type="password" id="password" name="_password" />

    {#
        If you want to control the URL the user
        is redirected to on success (more details below)
        <input type="hidden" name="_target_path" value="/account" />
    #}

    <button type="submit">login</button>
</form>
</body>
```
Incluiremos el sistema de deslogueo mediante la línea en twig `<a href="{{ path('logout') }}">salir</a>` dentro de **src\UserBundle\Resources\views\Default\index.html.twig**.
```twig
{# src\UserBundle\Resources\views\Default\index.html.twig #}
<body>
PRINCIPAL
<a href="{{ path('logout') }}">salir</a>
</body>
```

5.Roles
-------

El siguiente paso gestionará los roles de usuario, para ello dentro de la entidad **src\UserBundle\Entity\User.php** incluiremos la variable `private $roles = array();` como array ya que almacenará una colección de datos.  
```php
// src\UserBundle\Entity\User.php
/* Extracto de archivo */
/**
     * @var string
     */
    private $roles = array() ;
/* Extracto de archivo */
```

*Nota*: Si se usó el formato **yml** a la hora de definir la entidad habrá que modificar el archivo **src\UserBundle\Resources\config\doctrine\User.orm.yml**, incluyendo las características del nuevo tipo de dato.

```yml
#src\UserBundle\Resources\config\doctrine\User.orm.yml
#Extracto de archivo
fields:
        roles:
            type: json_array
#Extracto de archivo
```

Posteriormente ejecutaremos `php bin/console doctrine:generate:entities UserBundle:User` para actualizar la entidad, y `php bin/console doctrine:schema:update --force` para actualizar la base de datos.

6.Usuarios de la BD
-------------------

Usaremos el método `public function userAction(){}` para introducir los datos del primer usuario logueado en la base de datos (Hay que tener en cuenta que el password estará encriptado)

```php
/* Usamos esta función para cargar los datos de acceso a la base de datos con el password ya encriptado */
/*
El routing.yml que usaremos será esta ruta deberá tener acceso anónimo
user_codificador:
    path: /
    defaults: { _controller: UserBundle:User:user}
    */
    public function userAction(){
        $user = new user();
        $plainPassword = '1234';
        $encoder = $this->container->get('security.password_encoder');
        $encoded = $encoder->encodePassword($user, $plainPassword);

        $user->setPassword($encoded);
        $user->setUserName("paco");
        $user->setEmail("hola@hola.com");
        $roles = ["ROLE_USUARIO"];
        $user->setRoles($roles);

        $em = $this->getDoctrine()->getManager();
        $em->persist($user);
        $em->flush();
        return $this->render('UserBundle:User:user.html.twig');
    }
/*********************************************************************************************************/
```
Dentro de **app\config\security.yml**, indicaremos el proveedor de usuarios que seleccionaremos de la siguiente manera:

```yml
#app\config\security.yml
#Extracto de archivo
security:
    providers:
        my_db_provider: #nombre que le daremos al proveedor de usuarios
            entity:
                class: UserBundle:User # entidad de donde saldrán los usuarios
                property: userName # dato que se tomará como usuario
#Extracto de archivo
```

(Ver documentación oficial, [control de acceso](https://symfony.com/doc/current/security/access_control.html))
