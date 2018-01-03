Creación de un Dominio Virtual
==============================

1.Usando Wamp, mediante gestor
---------------------------------

Entro en **localhost**, y selecciono la opción de **Add HostVirtual**

![WAMP - LocalHost](https://github.com/HecFranco/Apuntes/blob/master/capture/WAMP-dominioVirtual_01.jpg)

![WAMP - Add a Host Virtual](https://github.com/HecFranco/Apuntes/blob/master/capture/WAMP-dominioVirtual_02.jpg)

2.Usando Wamp o Xamp, manualmente
---------------------------------

(Ver fuente ![aquí](https://styde.net/creando-virtual-hosts-con-apache-en-windows-para-wamp-o-xampp/))

Nos dirigirnos a **C:\WINDOWS\system32\drivers\etc\** y modificamos el archivo **hosts*, para modificar el archivo necesitamos permisos de administrador por lo que primero abrimos el Bloc de Notas como administrador y abrimos la siguiente dirección **C:\WINDOWS\system32\drivers\etc\hosts**.

![etc-hosts](https://github.com/HecFranco/Apuntes/blob/master/capture/CrearDominioVirtual_etc-hosts.png)

En este archivo agregamos nuestro host virtual, para agregarlo lo hacemos de la siguiente manera: `Nombre de Host`.
Entonces nosotros agregaremos nuestros host apuntado a **127.0.0.1** que es la dirección IPv4 de la maquina local, y después el nombre de nuestro hosts. Podemos agregar los host que deseemos pero siempre apuntando a **127.0.0.1**
**127.0.0.1        misitio.local**

Ahora debemos modificar el archivo de configuración de **Apache**, para incluir el archivo de configuración de virtual host, lo podemos abrir de igual manera con un bloc de notas.

* Si están en **XAMPP**, la ruta será la siguiente: **C:\xampp\apache\conf\httpd.conf**
* Si están en **WAMP**, la ruta será la siguiente: **C:\wamp\bin\apache\Apache2.2.21\conf\httpd.conf**

Lo siguiente es buscar las siguientes dos líneas que están resaltadas:

![virtual-hosts](https://github.com/HecFranco/Apuntes/blob/master/capture/CrearDominioVirtual_virtual-hosts.png)

Eliminen el **#** de la segunda línea.

Además dentro del mismo archivo debemos asegurarnos de que el módulo Rewrite está habilitado, para ello buscamos la siguiente línea:

![httpd.conf_](https://github.com/HecFranco/Apuntes/blob/master/capture/CrearDominioVirtual_httpd.conf_.png)

LoadModule rewrite_module modules/mod_rewrite.so

Y nos aseguramos de que no esté comentada (el signo de numeral # sirve para comentar líneas), si no tiene el signo quiere decir que ya está habilitada.

Realizado esto guardamos los cambios.

Lo siguiente es abrir el archivo de configuración que nos provee XAMPP o WAMP, de igual manera lo podemos editar con un Bloc de Notas.

Si están en XAMPP, la ruta será la siguiente: **C:\xampp\apache\conf\extra\httpd-vhosts.conf**

Si están en WAMP, la ruta será la siguiente: **C:\wamp\bin\apache\Apache2.2.21\conf\extra\httpd-vhosts.conf**

El archivo lucirá de la siguiente manera:

![httpd-vhosts](https://github.com/HecFranco/Apuntes/blob/master/capture/CrearDominioVirtual_httpd-vhosts.png)

Es en este archivo donde alojaremos cada uno de los host virtuales que creemos, lo haremos de la siguiente manera:

Primero agregamos la directiva Directory, es aquí donde activaremos el uso de URL’s amigables, necesarias para el funcionamiento del framework PHP que utilicemos (ejemplo: el poderoso Laravel), lo agregamos antes de la configuración de NameVirtualHost, y es aquí donde debemos recordar el nombre que le establecimos a nuestra carpeta, además de todo usaremos la diagonal convencional y no la invertida para descripción de direcciones:

![virtual-host](https://github.com/HecFranco/Apuntes/blob/master/capture/CrearDominioVirtual_virtual-host.png)

Lo siguiente es agregar nuestro virtual host, y lo agregamos de último a nuestro archivo:

![vhost](https://github.com/HecFranco/Apuntes/blob/master/capture/CrearDominioVirtual_virtual-vhost.png)

Recuerda reemplazar c:\virtualhost\sitiolocal\public con tu directorio en caso de que sea diferente.

Cuando se habilita el uso de Virtual host, Apache desactiva la carpeta raíz del servidor, por lo que antes de todos los virtual hosts debemos agregar la carpeta que nos provee XAMPP o WAMP para alojar nuestras paginas. En este caso yo utilice XAMPP:

Recuerda reemplazar c:\virtualhost\sitiolocal\public con tu directorio en caso de que sea diferente.

Cuando se habilita el uso de Virtual host, Apache desactiva la carpeta raíz del servidor, por lo que antes de todos los virtual hosts debemos agregar la carpeta que nos provee XAMPP o WAMP para alojar nuestras paginas. En este caso yo utilice XAMPP:




...........................


Accedo dentro de **C:\wamp64\bin\apache\apache2.4.27\conf\extra**, siendo **"apache2.4.27"** la versión instalada de **APACHE**, y edito el archivo **httpd-vhost.conf**.
Tambien encontraré el acceso directo a este archivo en el submenú de **[WAMP](http://www.wampserver.com/en/)** del inicio rápido de windows. 

![WAMP-virtualhost-httpd-vhosts.conf](https://github.com/HecFranco/Apuntes/blob/master/capture/WAMP-virtualhost-httpd-vhosts.conf.jpg)

```conf
# Ensure that Apache listens on port 80
Listen 80
<VirtualHost *:80>
    DocumentRoot "/www/example1"
    ServerName www.example.com

    # Other directives here
</VirtualHost>

<VirtualHost *:80>
    DocumentRoot "/www/example2"
    ServerName www.example.org

    # Other directives here
</VirtualHost>
```
