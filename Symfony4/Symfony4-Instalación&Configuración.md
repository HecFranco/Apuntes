Instalación y configuración de Symfony
=======================================

Para crear su nueva aplicación Symfony, primero asegúrese de usar PHP 7.1 o superior y tener [Composer](https://getcomposer.org/) instalado. Si no lo hace, comience por [instalar Composer globalmente](https://symfony.com/doc/current/setup/composer.html) en su sistema. Si desea utilizar una máquina virtual (VM), consulte [Homestead](https://symfony.com/doc/current/setup/homestead.html).

Crea tu nuevo proyecto ejecutando:

`composer create-project symfony/skeleton my-project`

Esto creará un nuevo directorio my-project, descargará algunas dependencias e incluso generará los directorios y archivos básicos que necesitará para comenzar. En otras palabras, ¡tu nueva aplicación está lista!

| También puede descargar una versión específica de Symfony:                                                    |
|---------------------------------------------------------------------------------------------------------------|
| `composer create-project symfony/skeleton my-project "3.3.*" `                                                |
| `composer create-project symfony/skeleton my-project 3.3.0-BETA1`                                             |
| Algunas versiones son versiones de soporte a largo plazo (LTS). Lea el proceso de publicación de Symfony para obtener más información. |

Running your Symfony Application¶
On production, you should use a web server like Nginx or Apache (see configuring a web server to run Symfony). But for development, it's even easier to use the Symfony PHP web server.

First, move into your new project and install the server:

cd my-project
composer require server --dev
To start the server, run:

 php bin/console server:run
Open your browser and navigate to http://localhost:8000/. If everything is working, you'll see a welcome page. Later, when you are finished working, stop the server by pressing Ctrl+C from your terminal.

TIP
If you're using a VM, you may need to tell the server to bind to all IP addresses:

 php bin/console server:start 0.0.0.0:8000
You should NEVER listen to all interfaces on a computer that is directly accessible from the Internet.

Storing your Project in git¶
Storing your project in git is easy! Just initialize you repository, add everything and commit:

 git init
 git add .
 git commit -m "Initial commit"
Your project already has a sensible .gitignore file. And as you install more packages, a system called Flex will add more lines to that file when needed.

Troubleshooting: The Requirements Checker¶
If you're having any problems running Symfony, your system may be missing some technical requirements. Symfony has a "Requirements Checker" tool that you can use to easily make sure your system is set up. First, move into your project directory and install it:

 composer require req-checker
The req-checker utility adds two PHP scripts to your application: vendor/bin/requirements-checker and  public/check.php. Run the first one from your terminal:

php vendor/bin/requirements-checker
This will check your CLI environment. Run the second one from a browser (e.g. http://localhost:8000/check.php) to check your web server environment.

Once you've fixed any issues, uninstall the requirements checker:

 composer remove req-checker
Setting up an Existing Symfony Project¶
If you're working on an existing Symfony application, you'll just need to do a few things to get your project setup. Assuming your team uses Git, you can setup your project with the following commands:


 cd projects/
 git clone ...


 cd my-project/
 composer install
You'll probably also need to customize your .env and do a few other project-specific tasks (e.g. creating database schema).

Checking for Security Vulnerabilities¶
Symfony provides a utility called the "Security Checker" (or sec-checker) to check whether your project's dependencies contain any known security vulnerability. Run this command to install it in your application:

 cd my-project/
 composer require sec-checker
From now on, this utility will be run automatically whenever you install or update any dependency in the application. If a dependency contains a vulnerability, you'll see a clear message.

The Symfony Demo application¶
The Symfony Demo Application is a fully-functional application that shows the recommended way to develop Symfony applications. It's a great learning tool for Symfony newcomers and its code contains tons of comments and helpful notes.

To check out its code and install it locally, see symfony/symfony-demo.

Start Coding!¶
With setup behind you, it's time to Create your first page in Symfony.