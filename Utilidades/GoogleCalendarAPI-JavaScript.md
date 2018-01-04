1.Inicio rápido
---------------

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
      // ID de cliente y clave de API de Developer Console
      var CLIENT_ID = '697142729422-vi3qn5jbnfu917qgatbnkt7bte1vg6ki.apps.googleusercontent.com';
      var API_KEY = 'AIzaSyCUan2QBM9lVYkJFRsaHHxh8CV0tWZxInM';
      // Array de URL de documentación de descubrimiento de API para API utilizadas por el inicio rápido
      var DISCOVERY_DOCS = ["https://www.googleapis.com/discovery/v1/apis/calendar/v3/rest"];
      // Los ámbitos de autorización requeridos por la API; 
      // múltiples ámbitos pueden ser incluidos, separados por espacios.
      /* ACCESO ************************************************************************/
        var SCOPES = "https://www.googleapis.com/auth/calendar.readonly"; // acceso de solo lectura a calendarios
        var SCOPES = "https://www.googleapis.com/auth/calendar";          //acceso de lectura / escritura a calendarios
      /* /ACCESO ************************************************************************/
      var authorizeButton = document.getElementById('authorize-button');
      var signoutButton = document.getElementById('signout-button');
      / * En carga, llamado para cargar la biblioteca auth2 y la biblioteca del cliente API. * /
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
## Paso 3: iniciar el ejemplo

Usaremos un servidor local tipo **WAMP** o **XAMPP**.
La primera vez que ejecute la muestra, le pedirá que autorice el acceso:

![GoogleCalendarAPI_JavaScript_12](https://github.com/HecFranco/Apuntes/blob/master/capture/GoogleCalendarAPI_JavaScript_12.jpg)

Haga clic en el botón **Autorizar** para abrir la ventana de autorización.

![GoogleCalendarAPI_JavaScript_13](https://github.com/HecFranco/Apuntes/blob/master/capture/GoogleCalendarAPI_JavaScript_13.jpg)

Si todavía no ha iniciado sesión en su cuenta de Google, se le pedirá que inicie sesión. Si inició sesión en varias cuentas de Google, se le pedirá que seleccione una cuenta para usar para la autorización.

Haga clic en el botón **Aceptar**.

**NOTA** Después de la autorización inicial del usuario, las llamadas a `gapi.auth.authorize` que usan el modo `immediate:true` obtendrán un token de autenticación sin interacción del usuario.


2.Referencia de API
-------------------

Esta referencia de API está organizada por tipo de recurso. Cada tipo de recurso tiene una o más representaciones de datos y uno o más métodos.

2.1.Tipos de recursos
---------------------

**Acl** Para obtener detalles del recurso Acl, consulte la página de representación de recursos.

<table>
  <tr>
    <td>Método</td><td>HTTP request</td><td>Descripción</td>
  </tr>
  <tr><td colspan="3">URIs relative to https://www.googleapis.com/calendar/v3, unless otherwise noted</td></tr>
  <tr>
    <td>delete</td><td>DELETE <br/> /calendars/calendarId/acl/ruleId</td><td>Deletes an access control rule.</td>
  </tr>  
</table>

===============================================

3.Añadir Evento
---------------

(Ver fuente ([aquí](https://developers.google.com/google-apps/calendar/create-events))

Create Events
Imagine an app that helps users find the best hiking routes. By adding the hiking plan as a calendar event, the users get a lot of help in staying organized automatically. Google Calendar helps them to share the plan and reminds them about it so they can get prepared with no stress. Also, thanks to seamless integration of Google products, Google Now pings them about the time to leave and Google Maps direct them to the meeting spot on time.

This article explains how to create calendar events and add them to your users' calendars.

Add an event
To create an event, call the events.insert() method providing at least these parameters:

calendarId is the calendar identifier and can either be the email address of the calendar on which to create the event or a special keyword 'primary' which will use the primary calendar of the logged in user. If you don't know the email address of the calendar you would like to use, you can check it either in the calendar's settings of the Google Calendar web UI (in the section "Calendar Address") or you can look for it in the result of the calendarList.list() call.
event is the event to create with all the necessary details such as start and end. The only two required fields are the start and end times. See the event reference for the full set of event fields.
Specify timed events using the start.dateTime and end.dateTime fields. For all-day events, use start.date and end.date instead.
In order to successfully create events, you need to:

set your OAuth scope to https://www.googleapis.com/auth/calendar.
ensure the authenticated user has write access to the calendar with the calendarId you provided (for example by calling calendarList.get() for the calendarId and checking the accessRole).
Add event metadata
You can optionally add event metadata when you create a calendar event. If you choose not to add metadata during creation, you can update many fields using the events.update(); however, some fields, such as the event ID, can only be set during an events.insert() operation.

Location
Adding an address into the location field enables features such as "time to leave" or displaying a map with the directions.
Event ID
When creating an event, you can choose to generate your own event ID that conforms to our format requirements. This enables you to keep entities in your local database in sync with events in Google Calendar. It also prevents duplicate event creation if the operation fails at some point after it is successfully executed in the Calendar backend. If no event ID is provided, the server generates one for you. See the event ID reference for more information.
Attendees
The event you create appears on all the primary Google Calendars of the attendees you included with the same event ID. If you set sendNotifications to true on your insert request, the attendees will also receive an email notification for your event. See the events with multiple attendees guide for more information.
The following examples demonstrate creating an event and setting its metadata:

```javascript
// Refer to the JavaScript quickstart on how to setup the environment:
// https://developers.google.com/google-apps/calendar/quickstart/js
// Change the scope to 'https://www.googleapis.com/auth/calendar' and delete any
// stored credentials.

var event = {
  'summary': 'Google I/O 2015',
  'location': '800 Howard St., San Francisco, CA 94103',
  'description': 'A chance to hear more about Google\'s developer products.',
  'start': {
    'dateTime': '2015-05-28T09:00:00-07:00',
    'timeZone': 'America/Los_Angeles'
  },
  'end': {
    'dateTime': '2015-05-28T17:00:00-07:00',
    'timeZone': 'America/Los_Angeles'
  },
  'recurrence': [
    'RRULE:FREQ=DAILY;COUNT=2'
  ],
  'attendees': [
    {'email': 'lpage@example.com'},
    {'email': 'sbrin@example.com'}
  ],
  'reminders': {
    'useDefault': false,
    'overrides': [
      {'method': 'email', 'minutes': 24 * 60},
      {'method': 'popup', 'minutes': 10}
    ]
  }
};

var request = gapi.client.calendar.events.insert({
  'calendarId': 'primary',
  'resource': event
});

request.execute(function(event) {
  appendPre('Event created: ' + event.htmlLink);
});
```
