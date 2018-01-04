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

![GoogleCalendarAPI_JavaScript_03](https://github.com/HecFranco/Apuntes/blob/master/capture/GoogleCalendarAPI_JavaScript_03.jpg)

3. En la parte superior de la página, selecciona la pestaña de la **pantalla de consentimiento de OAuth (OAuth consent screen)**.

![GoogleCalendarAPI_JavaScript_04](https://github.com/HecFranco/Apuntes/blob/master/capture/GoogleCalendarAPI_JavaScript_04.jpg)

Seleccione una dirección de **correo electrónico**, ingrese un **nombre de Producto** si aún no está configurado y haga clic en el botón **Guardar**.

![GoogleCalendarAPI_JavaScript_05](https://github.com/HecFranco/Apuntes/blob/master/capture/GoogleCalendarAPI_JavaScript_05.jpg)

4. Seleccione la pestaña **Credenciales**, haga clic en el botón **Crear credenciales** y seleccione **ID de cliente OAuth (OAuth client ID)**.

![GoogleCalendarAPI_JavaScript_06](https://github.com/HecFranco/Apuntes/blob/master/capture/GoogleCalendarAPI_JavaScript_06.jpg)

5. Seleccione la aplicación tipo de **aplicación web**.
6. En el campo de **orígenes de JavaScript autorizado (Authorized JavaScript origins)**, ingrese la URL `http: // localhost: 8000`. Puede dejar en blanco el campo de **URI de redirección autorizada (Authorized redirect URIs)**.
7. Haga clic en el botón **Crear**.

![GoogleCalendarAPI_JavaScript_07](https://github.com/HecFranco/Apuntes/blob/master/capture/GoogleCalendarAPI_JavaScript_07.jpg)

8. Tome nota de la identificación del cliente en el cuadro de diálogo resultante. Lo necesitarás en un paso posterior.

![GoogleCalendarAPI_JavaScript_08](https://github.com/HecFranco/Apuntes/blob/master/capture/GoogleCalendarAPI_JavaScript_08.jpg)

* **ID de cliente:** 697142729422-vi3qn5jbnfu917qgatbnkt7bte1vg6ki.apps.googleusercontent.com
* **Secreto de cliente**I8bQR6b_Y49xs9Y8qNTR5LHf

9. Haga clic en **Aceptar** para cerrar el cuadro de diálogo resultante.
10. Haga clic en el botón **Crear credenciales** y seleccione la **clave de API (API Key)**.

![GoogleCalendarAPI_JavaScript_09](https://github.com/HecFranco/Apuntes/blob/master/capture/GoogleCalendarAPI_JavaScript_09.jpg)

![GoogleCalendarAPI_JavaScript_10](https://github.com/HecFranco/Apuntes/blob/master/capture/GoogleCalendarAPI_JavaScript_10.jpg)

11. Tome nota de la clave API en el cuadro de diálogo resultante. Lo necesitarás en un paso posterior.

![GoogleCalendarAPI_JavaScript_11](https://github.com/HecFranco/Apuntes/blob/master/capture/GoogleCalendarAPI_JavaScript_11.jpg)

**key=API_KEY** AIzaSyCUan2QBM9lVYkJFRsaHHxh8CV0tWZxInM

12. Haga clic en el botón **Cerrar** para crear una clave sin restricciones. 

| **MUY IMPORTANTE** En aplicaciones de producción, puede restringir el acceso a la clave API a sitios web, direcciones IP o aplicaciones móviles específicas. |
|---------------------------------------------------------------------------------------------|

## Paso 2: Configure la muestra

Cree un archivo llamado `quickstart.html` y copie en el siguiente código:

```html
<!DOCTYPE html>
<html>
  <head>    <title>Google Calendar API Quickstart</title>    <meta charset='utf-8' />  </head>
  <body>
    <p>Google Calendar API Quickstart</p>

    <!--Add buttons to initiate auth sequence and sign out-->
    <button id="authorize-button" style="display: none;">Authorize</button>
    <button id="signout-button" style="display: none;">Sign Out</button>
    <pre id="content"></pre>
    <script type="text/javascript">
      // Client ID and API key from the Developer Console
      var CLIENT_ID = '697142729422-vi3qn5jbnfu917qgatbnkt7bte1vg6ki.apps.googleusercontent.com';
      var API_KEY = 'AIzaSyCUan2QBM9lVYkJFRsaHHxh8CV0tWZxInM';
      // Array of API discovery doc URLs for APIs used by the quickstart
      var DISCOVERY_DOCS = ["https://www.googleapis.com/discovery/v1/apis/calendar/v3/rest"];
      // Authorization scopes required by the API; multiple scopes can be
      // included, separated by spaces.
      var SCOPES = "https://www.googleapis.com/auth/calendar.readonly";
      var authorizeButton = document.getElementById('authorize-button');
      var signoutButton = document.getElementById('signout-button');
      /* On load, called to load the auth2 library and API client library. */
      function handleClientLoad() {
        gapi.load('client:auth2', initClient);
      }
      /* Initializes the API client library and sets up sign-in state listeners. */
      function initClient() {
        gapi.client.init({
          apiKey: API_KEY,
          clientId: CLIENT_ID,
          discoveryDocs: DISCOVERY_DOCS,
          scope: SCOPES
        }).then(function () {
          // Listen for sign-in state changes.
          gapi.auth2.getAuthInstance().isSignedIn.listen(updateSigninStatus);
          // Handle the initial sign-in state.
          updateSigninStatus(gapi.auth2.getAuthInstance().isSignedIn.get());
          authorizeButton.onclick = handleAuthClick;
          signoutButton.onclick = handleSignoutClick;
        });
      }

      /* Called when the signed in status changes, to update the UI appropriately. After a sign-in, the API is called. */
      function updateSigninStatus(isSignedIn) {
        if (isSignedIn) {
          authorizeButton.style.display = 'none';
          signoutButton.style.display = 'block';
          listUpcomingEvents();
        } else {
          authorizeButton.style.display = 'block';
          signoutButton.style.display = 'none';
        }
      }
      /** Sign in the user upon button click. */
      function handleAuthClick(event) {
        gapi.auth2.getAuthInstance().signIn();
      }
      /* Sign out the user upon button click. */
      function handleSignoutClick(event) {
        gapi.auth2.getAuthInstance().signOut();
      }
      /* Append a pre element to the body containing the given message as its text node. Used to display the results of the API call.
       * @param {string} message Text to be placed in pre element. */
      function appendPre(message) {
        var pre = document.getElementById('content');
        var textContent = document.createTextNode(message + '\n');
        pre.appendChild(textContent);
      }
      /* Print the summary and start datetime/date of the next ten events in the authorized user's calendar. If no events are found an appropriate message is printed. */
      function listUpcomingEvents() {
        gapi.client.calendar.events.list({
          'calendarId': 'primary',
          'timeMin': (new Date()).toISOString(),
          'showDeleted': false,
          'singleEvents': true,
          'maxResults': 10,
          'orderBy': 'startTime'
        }).then(function(response) {
          var events = response.result.items;
          appendPre('Upcoming events:');
          if (events.length > 0) {
            for (i = 0; i < events.length; i++) {
              var event = events[i];
              var when = event.start.dateTime;
              if (!when) {
                when = event.start.date;
              }
              appendPre(event.summary + ' (' + when + ')')
            }
          } else {
            appendPre('No upcoming events found.');
          }
        });
      }
    </script>
    <script async defer src="https://apis.google.com/js/api.js"
      onload="this.onload=function(){};handleClientLoad()"
      onreadystatechange="if (this.readyState === 'complete') this.onload()">
    </script>
  </body>
</html>
```

Al cargar la página veremos...

![GoogleCalendarAPI_JavaScript_12](https://github.com/HecFranco/Apuntes/blob/master/capture/GoogleCalendarAPI_JavaScript_12.jpg)

y podremos loguearnos con nuestra cuenta.

![GoogleCalendarAPI_JavaScript_13](https://github.com/HecFranco/Apuntes/blob/master/capture/GoogleCalendarAPI_JavaScript_13.jpg)
