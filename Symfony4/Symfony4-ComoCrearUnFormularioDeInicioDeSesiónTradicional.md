Cómo crear un formulario de inicio de sesión tradicional
========================================================

(Ver fuente [aquí](https://symfony.com/doc/current/security/form_login_setup.html))

**IMPORTANTE!** Si necesita un formulario de inicio de sesión y está almacenando usuarios en algún tipo de base de datos, debería considerar utilizar [FOSUserBundle](https://github.com/FriendsOfSymfony/FOSUserBundle), que le ayuda a construir su objeto Usuario y le ofrece muchas rutas y controladores para tareas comunes como inicio de sesión, registro y contraseña olvidada.


En esta entrada, creará un formulario de inicio de sesión tradicional. Por supuesto, cuando el usuario inicia sesión, puede cargar sus usuarios desde cualquier lugar, como la base de datos. Consulte [B) Configuración de cómo se cargan los usuarios](https://symfony.com/doc/current/security.html#security-user-providers) para obtener más detalles.

Primero, habilite el inicio de sesión de formulario debajo de su firewall:

```yml
# config/packages/security.yaml
security:
    # ...
    firewalls:
        main:
            anonymous: ~
            form_login:
                login_path: login
                check_path: login
```

**IMPORTANTE!** El `login_path` y `check_path` también pueden ser nombres de ruta (pero no pueden tener comodines obligatorios, por ejemplo `/login/{foo}` donde foo no tiene valor predeterminado).

Ahora, cuando el sistema de seguridad inicia el proceso de autenticación, redirigirá al usuario al formulario de inicio de sesión / inicio de sesión. La implementación de este formulario de `login` es su trabajo. Primero, crea un nuevo `SecurityController` dentro de un paquete:

```php
// src/Controller/SecurityController.php
namespace App\Controller;
use Symfony\Bundle\FrameworkBundle\Controller\Controller;
class SecurityController extends Controller
{
}
```


A continuación, configure la ruta que utilizó anteriormente en su configuración `form_login` (`login`):

```yaml
# config/routes.yaml
login:
    path:       /login
    controller: App\Controller\SecurityController::login
```
¡Estupendo! A continuación, agregue la lógica a `login()` que muestra el formulario de inicio de sesión:

```php
// src/Controller/SecurityController.php
use Symfony\Component\Security\Http\Authentication\AuthenticationUtils;

public function login(Request $request, AuthenticationUtils $authUtils)
{
    // get the login error if there is one
    $error = $authUtils->getLastAuthenticationError();

    // last username entered by the user
    $lastUsername = $authUtils->getLastUsername();

    return $this->render('security/login.html.twig', array(
        'last_username' => $lastUsername,
        'error'         => $error,
    ));
}
```


No dejes que este controlador te confunda. Como verá en un momento, cuando el usuario envía el formulario, el sistema de seguridad maneja automáticamente el envío del formulario por usted. Si el usuario envía un nombre de usuario o contraseña no válidos, este controlador lee el error de envío de formularios del sistema de seguridad, de modo que se puede volver a mostrar al usuario.

En otras palabras, su trabajo es **mostrar** el formulario de login y cualquier error de inicio de sesión que pueda haber ocurrido, pero el propio sistema de seguridad se encarga de verificar el nombre de usuario y la contraseña enviados y de autenticar al usuario.

Finalmente, crea la plantilla:

```twig
{# templates/security/login.html.twig #}
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
        If you want to control the URL the user is redirected to on success (more details below)
        <input type="hidden" name="_target_path" value="/account" />
    #}
    <button type="submit">login</button>
</form>
```

.............
