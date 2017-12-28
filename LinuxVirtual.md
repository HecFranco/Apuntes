LINUX Máquina Virtual
=======================
Para poder trabajar de una manera más eficiente, se recomienda utilizar [Linux Ubuntu Mate Virtual](http://cdimage.ubuntu.com/).

Para ello habrá que:
1. Instalar y configurar [VirtualBox](https://www.virtualbox.org/).
2. Descargar la vesión ISO de [Linux Ubuntu Mate Virtual](http://cdimage.ubuntu.com/), para cargarla.


1.VirtualBox
============

Accedemos a la web de [VirtualBox](https://www.virtualbox.org/), dónde descargamos la última versión (en nuestro caso [VirtualBox 5.2.4 platform packages, Windows hosts](http://download.virtualbox.org/virtualbox/5.2.4/VirtualBox-5.2.4-119785-Win.exe)), la instalamos y la ejecutamos (descargar [VirtualBox](https://www.virtualbox.org/) [aquí](https://www.virtualbox.org/wiki/Downloads)).

1. Indicamos el nombre de la máquina virtual a instalar en este caso **Ubuntu_Mate**.

![Instalación_nueva_máquina_virtual_01](https://github.com/HecFranco/Apuntes/blob/master/capture/Instalación_nueva_máquina_virtual_01.jpg)

2. Seleccionamos el tamaño de la memoria RAM que vamos a dedicar a la instalación virtual, en nuestro caso será de **4GB**.

![Instalación_nueva_máquina_virtual_02](https://github.com/HecFranco/Apuntes/blob/master/capture/Instalación_nueva_máquina_virtual_02.jpg)

3. Tenemos dos opciones en este punto, crear un nuevo disco duro virtual o reutilizar uno ya generado anteriormente. **Nosotros hemos creado uno nuevo**. 

![Instalación_nueva_máquina_virtual_03](https://github.com/HecFranco/Apuntes/blob/master/capture/Instalación_nueva_máquina_virtual_03.jpg)

4. El archivo que contendrá el sistema virtual estará ubicado en una imagen **ISO** en nuestro caso, por lo que usaremos la opción de **VDI (VirtualBox Disk Image)**.

![Instalación_nueva_máquina_virtual_04](https://github.com/HecFranco/Apuntes/blob/master/capture/Instalación_nueva_máquina_virtual_04.jpg)

5. El almacenamiento del disco duro que se usará para la instalación será **Reservado dinámicamente**, es decir, que se irá reservando según sea necesario. 

![Instalación_nueva_máquina_virtual_05](https://github.com/HecFranco/Apuntes/blob/master/capture/Instalación_nueva_máquina_virtual_05.jpg)

6. Indicamos el espacio real de disco duro a usar, en este caso para la instalación básica de Drupal serán **300MB**. 

![Instalación_nueva_máquina_virtual_06](https://github.com/HecFranco/Apuntes/blob/master/capture/Instalación_nueva_máquina_virtual_06.jpg)

7. Una vez finalizada la instalación de la unidad virtual, instalaremos el sistema a partir de la versión de **Linux** descargada ([ver apartado siguiente](#12linux-ubuntu-mate-virtual)) 

![Instalación_nueva_máquina_virtual_07](https://github.com/HecFranco/Apuntes/blob/master/capture/Instalación_nueva_máquina_virtual_07.jpg)
8. Para la configuración interna de la instalación virtual deberemos indicar dentro de **General >> Avanzado**, el sistema **Bidireccional** tanto para compratir portapapeles como para arrastrar y soltar elementos. <center>![Instalación_nueva_máquina_virtual_08](capture\Instalación_nueva_máquina_virtual_08.JPG)</center>
9. Además habrá que dentro de **Sistema >> Procesador** indicar el número de núcleos a utilizar por el sistema.
<center>![Instalación_nueva_máquina_virtual_09](capture\Instalación_nueva_máquina_virtual_09.JPG)</center>
Para una nueva instalación de sistema operativo virtual, accederemos a la opción de **BH >> Nueva**


2. Linux Ubuntu Mate Virtual
============================

2.1. Descargar Versión de Linux Ubuntu
--------------------------------------

Accedemos a la web de Instalación de [Linux Ubuntu Mate Virtual](http://cdimage.ubuntu.com/), dentro de [Download](https://ubuntu-mate.org/download/) descargo la última versión estable (link [aquí](http://cdimage.ubuntu.com/ubuntu-mate/releases/17.10/release/ubuntu-mate-17.10-desktop-amd64.iso)).

![Linux Ubuntu Mate Virtual Capture](https://github.com/HecFranco/Apuntes/blob/master/capture/Ubuntu_Mate_Descktop.jpg)

2.2. Instalando Linux Ubuntu
----------------------------

Para evitar la instalación real de Linux, y poder usar el sistema operativo en modo Virtual se recomienda usar [VirtualBox](https://www.virtualbox.org/).

![Instalación__Ubuntu_Mate_01](https://github.com/HecFranco/Apuntes/blob/master/capture/Instalación__Ubuntu_Mate_01.jpg)

![Instalación__Ubuntu_Mate_02](https://github.com/HecFranco/Apuntes/blob/master/capture/Instalación__Ubuntu_Mate_02.jpg)

![Instalación__Ubuntu_Mate_03](https://github.com/HecFranco/Apuntes/blob/master/capture/Instalación__Ubuntu_Mate_03.jpg)

![Instalación__Ubuntu_Mate_04](https://github.com/HecFranco/Apuntes/blob/master/capture/Instalación__Ubuntu_Mate_04.jpg)

![Instalación__Ubuntu_Mate_05](https://github.com/HecFranco/Apuntes/blob/master/capture/Instalación__Ubuntu_Mate_05.jpg)

![Instalación__Ubuntu_Mate_06](https://github.com/HecFranco/Apuntes/blob/master/capture/Instalación__Ubuntu_Mate_06.jpg)

![Instalación__Ubuntu_Mate_07](https://github.com/HecFranco/Apuntes/blob/master/capture/Instalación__Ubuntu_Mate_07.jpg)

![Instalación__Ubuntu_Mate_08](https://github.com/HecFranco/Apuntes/blob/master/capture/Instalación__Ubuntu_Mate_08.jpg)

![Instalación__Ubuntu_Mate_09](https://github.com/HecFranco/Apuntes/blob/master/capture/Instalación__Ubuntu_Mate_09.jpg)

Finalmente pulsaremos **ENTER** para terminar la instalación.

![Instalación__Ubuntu_Mate_10](https://github.com/HecFranco/Apuntes/blob/master/capture/Instalación__Ubuntu_Mate_10.jpg)


2.3. Configurando Linux Ubuntu
------------------------------

Una vez iniciado el sistema, para colocar en pantalla completa accederemos a **BM >> Ver >> Modo Pantalla Completa**.
A continuación, **insertar la imagen de CD de las << Guest Addittions >>**, para ello **Menú inferior >> Dispositivos >> insertar la imagen de CD de las << Guest Addittions >>**.

![Configuracion_Ubuntu_Mate_Descktop_01](https://github.com/HecFranco/Apuntes/blob/master/capture/Configuracion_Ubuntu_Mate_Descktop_01.jpg)

A continuación ejecutaremos *VBox_GAs*.

![Configuracion_Ubuntu_Mate_Descktop_02](https://github.com/HecFranco/Apuntes/blob/master/capture/Configuracion_Ubuntu_Mate_Descktop_02.jpg)

Accederemos mediante el **password** de administrador que se indicó durante la instalación.

![Configuracion_Ubuntu_Mate_Descktop_03](https://github.com/HecFranco/Apuntes/blob/master/capture/Configuracion_Ubuntu_Mate_Descktop_03.jpg)

Finalmente pulsaremos **ENTER** para instalarlo.

![Configuracion_Ubuntu_Mate_Descktop_04](https://github.com/HecFranco/Apuntes/blob/master/capture/Configuracion_Ubuntu_Mate_Descktop_04.jpg)

2.4. Carpetas Compartidas con Windows
-------------------------------------

Para poder enviar documentos desde **Windows** a **Linux Virtual** accederemos dentro de la **BH >> Dispositivos >> Carpetas Compartidas**.

![Configuracion_Ubuntu_Mate_Descktop_05](https://github.com/HecFranco/Apuntes/blob/master/capture/Configuracion_Ubuntu_Mate_Descktop_05.jpg)

2.5. Comandos Importantes de Linux
----------------------------------
* Para entrar en una carpeta usaremos `cd` seguido del nombre de la carpeta, ejemplo `cd prueba`.
* Para retroceder un nivel en la estructura de carpetas usaremos `../`.
* Se mostrará un listado de los archivos existentes dentro de una carpeta mediante `ls - l`.
* Usaremos `ls - la` para ver además los archivos ocultos de la carpeta.
* `cex` permite exportar
* `cim` permite importar
* `-m` nombrar
* Para limpiar la caché, usaremos `cr`.
