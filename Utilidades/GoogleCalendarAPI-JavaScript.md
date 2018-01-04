1.Navegador de inicio rápido
------------------------------

Complete los pasos que se describen en el resto de esta página, y en aproximadamente cinco minutos tendrá una aplicación de navegador simple que realiza solicitudes a la API de Google Calendar.

1.1.Requisitos previos
-----------------------

Para ejecutar este inicio rápido, necesitarás:
* Python 2.4 o superior (para proporcionar un servidor web).
* Acceso a Internet y un navegador web.
* Una cuenta de Google con Google Calendar habilitada.

## Paso 1: activa la API de Google Calendar

1. Use [este asistente](https://console.developers.google.com/start/api?id=calendar) para crear o seleccionar un proyecto en Google Developers Console y encienda automáticamente la API. 

![GoogleCalendarAPI_JavaScript_01](https://github.com/HecFranco/Apuntes/blob/master/capture/GoogleCalendarAPI_JavaScript_01.jpg)

Haga clic en **Continuar**, luego **vaya a credenciales**.

![GoogleCalendarAPI_JavaScript_02](https://github.com/HecFranco/Apuntes/blob/master/capture/GoogleCalendarAPI_JavaScript_02.jpg)

2. En la página **Agregar credenciales a su proyecto**, haga clic en el botón **Cancelar**.

3. En la parte superior de la página, selecciona la pestaña de la **pantalla de consentimiento de OAuth (OAuth consent screen)**. Seleccione una dirección de **correo electrónico**, ingrese un **nombre de Producto** si aún no está configurado y haga clic en el botón **Guardar**.
4. Seleccione la pestaña **Credenciales**, haga clic en el botón **Crear credenciales** y seleccione **ID de cliente OAuth (OAuth client ID)**.
5. Seleccione la aplicación tipo de **aplicación web**.
6. En el campo de **orígenes de JavaScript autorizado (Authorized JavaScript origins)**, ingrese la URL `http: // localhost: 8000`. Puede dejar en blanco el campo de **URI de redirección autorizada (Authorized redirect URIs)**.
7. Haga clic en el botón **Crear**.
8. Tome nota de la identificación del cliente en el cuadro de diálogo resultante. Lo necesitarás en un paso posterior.
9. Haga clic en **Aceptar** para cerrar el cuadro de diálogo resultante.
10. Haga clic en el botón **Crear credenciales** y seleccione la **clave de API (API Key)**.
11. Tome nota de la clave API en el cuadro de diálogo resultante. Lo necesitarás en un paso posterior.
12. Haga clic en el botón **Cerrar** para crear una clave sin restricciones. En aplicaciones de producción, puede restringir el acceso a la clave API a sitios web, direcciones IP o aplicaciones móviles específicas.

## Paso 2: Configure la muestra

Cree un archivo llamado `quickstart.html` y copie en el siguiente código:
