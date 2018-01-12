DRUPAL 8
========

1.INSTALACIÓN DRUPAL
====================

1.1.INSTALACIÓN BÁSICA DE DRUPAL
--------------------------------

1.1.1.Requisitos Básicos
-------------------------

Para poder instalar Drupal es necesario disponer de los siguientes requerimientos básicos:
* **PHP**, lenguaje sobre el que se escribe Drupal8.
* **MySQL**, lenguaje de gestión de base de Datos.
* **APACHE**, servidor que realice la comunicación entre el navegador y el servidor Virtual.
* **S.O.**, sistema operativo.

Para disponer de todos estos requisitos básicos podré instalar **[WAMP](http://www.wampserver.com/en/)** o **[XAMPP](https://www.apachefriends.org/es/index.html)**

1.1.2.Primeros Pasos
--------------------

* Accedemos a [Drupal.org](https://www.drupal.org/) y hacemos click en [Dowload & Extend](https://www.drupal.org/download)

![Drupal.org-Home](../capture/Drupal8-InstalacionBasica_01.jpg)

* En la siguiente ventana podré descargarme la última versión estable de Drupal, en este caso podré descargar la versión de **Drupal 8.4.3** [descargar aquí](https://www.drupal.org/project/drupal/releases/8.4.3).

![Drupal.org-Version](../capture/Drupal8-InstalacionBasica_02.jpg)

* Podré descargar la versión de Drupal seleccionada con la extensión **[.tar.gz](https://ftp.drupal.org/files/projects/drupal-8.4.3.tar.gz)** o **[.zip](https://ftp.drupal.org/files/projects/drupal-8.4.3.zip)**.

![Drupal.org-Core](../capture/Drupal8-InstalacionBasica_03.jpg)

Además en esta ventana tendré acceso al **Core** que es la versión que estaremos descargando, **Distributions** que son proyectos drupal ya configurados (e-commerce, red social,...), **Modules** y **Themes**

Descomprimo la carpeta y la guardo dentro de nuestra carpeta del proyecto, en este caso hemos elegido **"drupal_new_project"**.
* **C:\wamp64\www\drupal_new_project**, **[WAMP](http://www.wampserver.com/en/)** en windows
* **C:\xampp\htdocs\drupal_new_project**, **[XAMPP](https://www.apachefriends.org/es/index.html)** en windows

...........................................

Por ello debemos tener las herramientas correspondientes instaladas en nuesta computadora, recomendandose usar un entorno linux, (ver manual LinuxVirtual):
* **[curl](https://curl.haxx.se/)**
* **[composer](https://getcomposer.org/)**
* **[git](https://git-scm.com/)**
* **[drush](http://www.drush.org/)**
* **[drupal console](https://drupalconsole.com/)**

1.1.Instalar Git y Curl
-----------------------

Para instalar **curl** usaremos el comando de consola  `sudo apt install curl`, en cambio para instalar **git** usaremos `sudo apt install git`.

1.2.Instalar Composer
---------------------
Cabe destacar que se recomienda tener instalado **curl** previamente para poder instalar **Composer**.

Abre una consola de comandos y ejecuta lo siguiente para descargar la versión más reciente de Composer y convertirla en un comando del sistema:

`curl -sS https://getcomposer.org/installer | php`<br/>
`sudo mv composer.phar /usr/local/bin/composer`

Si por alguna extraña razón no puedes ejecutar curl para descargar Composer, prueba con el siguiente comando alternativo que usa php:

`php -r "readfile('https://getcomposer.org/installer');" | php`

1.3.Crear repositorio Bitbucket
--------------------------------

El siguiente paso consiste en crear el nuevo repositorio con nuestro usuario dentro de Bitbucket, en este caso usando [Bitbucket](https://bitbucket.org/product) como alojamiento para el repositorio. <br/>
Para ello pulsaremos dentro de la **Barra Latera** en el **+**.<br/>

![BitBucket_nuevo_repositorio_01](../capture/BitBucket_nuevo_repositorio_01.jpg)<br/>
Posteriormente seleccionaremos **Repository**.<br/>

![BitBucket_nuevo_repositorio_02](../capture/BitBucket_nuevo_repositorio_02.jpg)<br/>
En la siguiente ventana podremos seleccionar tanto el **Nombre del repositorio**, como si queremos que sea **privado**, la inclusión del archivo **README.MD**, la versión de control **GIT** o **Mercurial** (en nuestro caso **GIT**), la **descripción**, opciones de **Gestión de proyectos** (**Issue tracking** y **Wiki**), y el **Lenguaje**.<br/>

![BitBucket_nuevo_repositorio_03](../capture/BitBucket_nuevo_repositorio_03.jpg)<br/>

**IMPORTANTE** Marcamos los checkbox de **Issue tracking** y **Wiki**, y como lenguaje de uso al ser **Drupal** indicaremos **PHP** |

1.4.Crear estructura de Drupal
-------------------------------

Accederemos mediante la terminal dentro de la carpeta dónde queremos instalar **Drupal**, e iniciaremos el proyecto mediante **Composer** usando el comando `composer create-project drupal-composer/drupal-project:8.x-dev my_site_name_dir --stability dev --no-interaction`.

Este comando generará una carpeta llamada **my_site_name_dir** dónde se ubicará la estructura.

Esto creará una estructura de carpetas para nuestro proyecto. En dicha estructura se encuentra la carpeta llamada **web** donde realizaremos la instalación de drupal con **drush**.

1.5.Instalación de Drupal mediante **Drush**
--------------------------------------------
La instalación de Drupal se realizará con **Drush** (desde la carpeta **web**).

**IMPORTANTE** Antes de la instalación de drupal, debemos crear una base de datos. la cual se la asignaremos a la instalación. **Recomendación** cotejamiento DB: utf-8 general-ci 

No debemos olvidar cambiar las credenciales de acceso para la **base de datos** *(Ej:prueba)*, tu **usuario** *(Ej:root)* y tu **password** *(Ej:root)*.

Así instalaremos mediante **Drush** Drupal usando el comando de consola `../vendor/drush/drush/drush site-install --db-url="mysql://$DBUSER:$DBPWD@localhost/$DBNAME" --account-name=admin --account-pass=admin standard install_configure_form.update_status_module='array(FALSE,FALSE)' -y`

En el cual indicaremos los datos de acceso a la **Base de Datos**, de forma que si nuestra base de datos tuviera la configuración de acceso anteriormnete descrita se accedería usando el comando `../vendor/drush/drush/drush site-install --db-url="mysql://root:root@localhost/prueba" --account-name=admin --account-pass=admin standard install_configure_form.update_status_module='array(FALSE,FALSE)' -y`

1.6.Lanzar Servidor Local mediante **Drupal Console**
------------------------------------------------------

Terminada la instalación, podemos utlizar **Drupal Console** para ejecutar un servidor local provisional. Dentro de la carpeta de nuestro proyecto ejecutamos el siguiente comando `drupal server`

Este comando nos lanzará una **dirección ip**, la cual podremos usar en el navegador para acceder a nuestra instalación.

1.7.Exportación e importación de configuración
-----------------------------------------------

Para no depender de la Base de Datos, y poder realizar **commit** de una manera sencilla, debemos permitir la exportación e importación de la configuración de la web alojada en la Base de datos mediante **staging**.

Primeramente deberemos asegurarnos que se encuentre dentro de la configuración del proyecto, en `sites/default/settings.php`, la siguiente línea `$config_directories['staging'] = '../config_staging';`, la cual permitirá dicha exportación.

Debemos realizar la importación de la configuración de nuestro proyecto con el comando (desde la carpeta web): `../vendor/drush/drush/drush cex staging`
Para la importación el comando sería el siguiente `../vendor/drush/drush/drush cim staging`

1.8.Iniciar Repositorio
------------------------

**IMPORTANTE** Si es la primera vez que iniciamos el repositorio en el PC actual, será necesario identificarse con el mismo.  Para ello usaremos el comando `git config --global user.email "email@usuario.com"` y `git config --global user.name "Cristina"` 

Empezaremos creando nuestro repositorio local, para inicializarloos git con el siguiente comando(carpeta de proyecto):
`git init`
Después de usar este comando se habrá creado una nueva carpeta oculta **.git** y el archivo oculto **.gitignore**.
Con el comando `git status` deberiamos poder ver en consola los archivos modificados en color rojo, puesto que todavía no los hemos añadido todavía a la selección para el commit.
Para agregarlos utilizamos el comando en cambio usaremos `git add .`, o también `git add -A`.

1.9.Primer Commit
-----------------

Ya podemos hacer nuestro primer commit con el comando `git commit -m "primer commit"`, el cual se añadirá a nuestro repositorio local.
Si utilizamos ahora el comando `git status` podremos ver que ahora no estan rojos los archivos, ya que han sufrido un **commit**.

`On branch master nothing to commit (working directory clean)`

Enlazaremos nuestro repositorio local con [Bitbucket](https://bitbucket.org/product) (repositorio remoto) con el comando de consola `git remote add origin git@bitbucket.org:Ejemplo/prueba.git`. Este comando se podrá extraer de [Bitbucket](https://bitbucket.org/product).
Para ello en el repositorio, seleccionaremos la opción **Overview**.<br/>
![BitBucket_nuevo_repositorio_04](../capture/BitBucket_nuevo_repositorio_04.jpg)<br/>
Y según si nos encontramos ante un repositorio ya existente, o uno nuevo seleccionaremos las líneas de comando siguientes:
<br/>

**TENGO UN PROYECTO EXISTENTE** <br/>
![BitBucket_nuevo_repositorio_05](../capture/BitBucket_nuevo_repositorio_05.jpg)<br/>

**ESTOY EMPEZANDO DESDE SCRATH** <br/>
![BitBucket_nuevo_repositorio_06](../capture/BitBucket_nuevo_repositorio_06.jpg)<br/>

**IMPORTANTE** Si es la primera vez que iniciamos el repositorio en el PC actual, será necesario identificarse con el mismo. Para ello usaremos el comando `git config --global user.email "email@usuario.com"` y `git config --global user.name "Cristina"`

Es posible que tengamos que generar nuestras **clave pública y privada de RSA** necesarias para la comunicación con nuestros servidores.

Para generarlas utilizaremos el comando `ssh-keygen -t rsa`. Esto creará unos archivos que se ubicarán en una carpeta oculta llamada **.ssh** dentro de nuestro usuario.
<br/>
![BitBucket_nuevo_repositorio_07](../capture/BitBucket_nuevo_repositorio_07.jpg)<br/>

El archivo en el que se guardará la clave publica es `id_rsa.pub`.

Añadiremos las claves generadas en el Repositorio de [Bitbucket](https://bitbucket.org/product), accediendo a los datos de **perfil >> settings >> SSHKeys** y añadiremos la clave.<br/>

![BitBucket_nuevo_repositorio_08](../capture/BitBucket_nuevo_repositorio_08.jpg)<br/>

![BitBucket_nuevo_repositorio_09](../capture/BitBucket_nuevo_repositorio_09.jpg)<br/>

Recuerda que en nuestro repositorio debemos crear una clave pública para nuestro usuario igual a la creada en nuestro entorno local.

Y subimos los archivos con `git push -u origin master`
