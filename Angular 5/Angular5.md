ANGULAR
=======

1.Pasos Previos
===============

Para poder trabajar con [Angular](https://angular.io/), es necesario previamente tener instalado

1.1.Instalaciones Previas, CygWin y NodeJs
------------------------------------------

* [CygWin](https://www.cygwin.com/), como emulador de consola de **Linux**. Junto a **CygWin** instalaremos los paquetes de **git** (Devel), que nos premitirá tener un control de versiones; **ssh** (Net) para concetarnos a un servidor; **nano** () como editor de ficheros, y **Wget** ().

**IMPORTANTE** mediante los comandos `git -v` y `ssh -v` podemos ver las versiones instaladas tanto de **git** como de **ssh**.

**IMPORTANTE - Listado de Comandos Linux**  
* `ls -lh` (muestra el contenido de la carpeta junto a todos los detalles de cada archivo, permisos, tamaño, nombre, propietario,...)
* `rm -rf carpeta-a-eliminar` (elimina la carpeta seleccionada junto a su contenido)

* [Node Js](https://nodejs.org/es/)

![Node_Js_instalacion_01](https://github.com/HecFranco/Apuntes/blob/master/capture/Node_Js_instalacion_01.jpg)

Una vez instalado [Node Js](https://nodejs.org/es/), en su consola si ejecutamos el comando `npm -v` (gestor de dependencias) y `node -v` veremos la versiones instaladas de ambas aplicaciones.

Para actualizar **npm** ejecutaremos `npm install -g npm`.

Hoy vamos a instalar Angular 4 paso a paso y desde cero. Angular 4 es la nueva versión de Angular 2, que incluye una mejora importante a nivel interno, aunque no trae muchos cambios a la hora de programar con el framework.

1.2.Como Instalar Angular4 (forma básica)
-----------------------------------------

**IMPORTANTE** *tener de cada herramienta la última versión instalada para evitar errores.*

Para instalar [Angular4](https://angular.io/), debemos:

**Paso 0.** Instalar la última versión de NodeJS desde [aquí](https://nodejs.org/es/download/) (ver aparatdo anterior)

**Paso 1.** Descargar el quickstart de Angular desde su repositorio, [aquí](https://github.com/angular/quickstart).

**Paso 2.** Descomprimir el zip en un directorio.

**Paso 3.** Entrar desde la consola de comandos al directorio donde hemos descomprimido el zip, y ejecutar el comando de consola `cd angular4`.

**Paso 4.** Lanzar el comando para instalar las dependencias necesarias para el framework con el comando `npm install` (dentro de la carpeta).

**Paso 5.** *(Te lo puedes saltar si no tienes una instalación previa de Angular 2)* Actualizar el framework a Angular 4 usando el comando `npm install @angular/{common,compiler,compiler-cli,core,forms,http,platform-browser,platform-browser-dynamic,platform-server,router,animations}@next --save`

**NOTA** Para **desinstalar** el paquete de **Angular/CLI** lanzaremos el comando `npm uninstall -g angular-cli`, y **limpiaremos la caché** usando `npm cache clear`.

Ahora podemos revisar el fichero **package.json** y veremos que tenemos la versión 4 de Angular.

Paso final. Lanzar el comando para arrancar el framework con el comando `npm start`.

Ya tenemos disponible el **hola mundo** de **Angular4** en la url **http://localhost:3000/** que sirve un pequeño servidor que arranca el comando `npm start` para desarrollar con Angular.

![Hello_Angular](https://github.com/HecFranco/Apuntes/blob/master/capture/Hello_Angular.jpg)

**CURIOSIDAD** para cambiar el contenido de la página lanzada, accederíamos dentro de **src/app/app.component.ts**, y cambiaría el contenido, ver archvio a continuación.

```ts
/* src/app/app.component.ts */
import { Component } from '@angular/core'

@Component({
  selector: 'my-app',
  tempalte: '<h1>Hello({name})</h1>',
})
export class AppComponent { name = 'Angular'; }
```
1.2.Como Instalar Angular CLI
-----------------------------
[Angular CLI](https://cli.angular.io/) es una herramienta que nos hace más fácil el proceso de instalación de **Angular4** y nos agiliza el inicio de un proyecto con este framework de Google.

[GitHub Angular CLI](https://github.com/angular/angular-cli)

**¿Que nos ofrece Angular CLI al final?**
1. Instalación y esqueleto básico de **Angular2**
2. Comandos para la generación de código(componentes, servicios, etc)
3. Herramientas de minificación y builds para las webapps
4. Testing

**NOTA** Si tenemos instalada una versión más antigua de [Angular CLI](https://cli.angular.io/) y queremos actualizarlo, primeramente lanzaremos `npm uninstall -g @angular/cli` y `npm cache clean`.

Para **instalar Angular CLI** lanzamos el comando `npm install -g @angular/cli@latest`.

Ahora vamos a crear una aplicación esqueleto base de **Angular4** (instalar Angular4), mediante el comando `ng new proyecto-angular4` (dentro de la carpeta del proyecto).

Dentro de *package.json*, podremos observar la versión instalada de **Angular4** y **TypeScript**.

![Angular_01](https://github.com/HecFranco/Apuntes/blob/master/capture/Angular_01.jpg)

En este momento tenemos un proyecto entero instalado y nosotros tendremos que meter nuestro código y programar dentro del directorio **src**.

Podemos generar algunos componentes del framework, veamos algunos comandos para hacer esto.

Generar un componente, usando `ng generate component nuevo-componente`.
Generar una pipe `ng generate pipe nuevo-filtro`.
Generar un servicio `ng generate service nuevo-servicio`.

También podemos lanzar la aplicación en un servidor web, como el que típicamente usábamos en cualquier app de **Angular4** normal. Usaremos el comando `ng server`.

Ahora tendremos disponible la webapp de **Angular4** en [http://localhost:4200/](http://localhost:4200/)

Con esto ya sabemos usar [Angular CLI](https://cli.angular.io/) de forma básica.
