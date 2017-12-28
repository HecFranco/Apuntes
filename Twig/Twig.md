1.¿Qué es Twig?
===============
Para ver toda la información relativa al lenguaje [Twig](https://twig.symfony.com/).

Tenemos tres formas de incluir información:
* `{{ ... }}` Imprime por pantalla. Imprime variables o expresiones.
* `{{% ... %}}` Bloques de código. Estructuras de control o de repetición.
* `{{# ... #}}` Comentarios.

2.Tags
======

2.1.¿Cómo usar If?
------------------

La sentencia `if` en [Twig](https://twig.symfony.com/) es comparable con las declaraciones `if` de PHP. En la forma más sencilla se puede usar para probar si una expresión se evalúa como `true`:
```twig
{% if online == false %}
    <p>Our website is in maintenance mode. Please, come back later.</p>
{% endif %}
```

También puede probar si una matriz no está vacía:
```twig
{% if users %}
    <ul>
        {% for user in users %}
            <li>{{ user.username|e }}</li>
        {% endfor %}
    </ul>
{% endif %}
```

También puede utilizar para no comprobar los valores que se evalúan como `false`:
```twig
{% if not user.subscribed %}
    <p>You are not subscribed to our mailing list.</p>
{% endif %}
```
Para las condiciones múltiples, `and`y `or` se puede utilizar:
```twig
{% if temperature > 18 and temperature < 27 %}
    <p>It's a nice day for a walk in the park.</p>
{% endif %}
```

Para las ramas múltiples `elseif` y `else` se puede utilizar como en PHP. También puede utilizar expresiones más complejas:
```twig
{% if kenny.sick %}
    Kenny is sick.
{% elseif kenny.dead %}
    You killed Kenny! You bastard!!!
{% else %}
    Kenny looks okay --- so far
{% endif %}
```

----------------------------------------------
**EJEMPLO CON IF**
```twig
{{# Resto de Palntilla... #}}
  {{if usuario is defined}}
    {% if nPila=="Paco" %}
        Paco está muy loco
    {% elseif nPila=="Paco" %}
        María es un nombre de chica
    {% else %}
        {{nPila}}
    {% endif %}
  {% endif %}
{{# Resto de Palntilla... #}}
```
----------------------------------------------

2.2.¿Cómo usar For?
-------------------

`for`realiza un loop sobre cada elemento en una secuencia. Por ejemplo, para mostrar una lista de usuarios proporcionada en una variable llamada `ùsers`:
```twig
<h1>Members</h1>
<ul>
    {% for user in users %}
        <li>{{ user.username|e }}</li>
    {% endfor %}
</ul>
```
Si se necesita iterar sobre una secuencia de números, puede usar el operador `..`:
```twig
{% for i in 0..10 %}
    * {{ i }}
{% endfor %}
```
El fragmento de código anterior imprimirá todos los números de `0` a `10`. También puede ser útil con letras:
```twig
{% for letter in 'a'..'z' %}
    * {{ letter }}
{% endfor %}
```
El operador `..` puede tomar cualquier expresión en ambos lados:
```twig
{% for letter in 'a'|upper..'z'|upper %}
    * {{ letter }}
{% endfor %}
```

----------------------------------------------
**EJEMPLO CON FOR**
```php
// src\CursoBundle\Controller\DefaultController.php
public function nombresAction()
{
    $nombres=[
        "Paco"=>["nombre"=>"Paco","activo"=>true],
        "Maria"=>["nombre"=>"Maria","activo"=>false],
        "José"=>["nombre"=>"José","activo"=>true]
    ]
}
```
```twig
<ul>
    {% for nombre in nombres if nombre.activo %}
        <li>{{ nombre.nombre }}</li>
    {% endfor %}
</ul>
```
----------------------------------------------

2.3.¿Cómo usar los Tags/Bloques?
--------------------------------

| app\Resources\views\base.htm.twig |
|-----------------------------------|
```twig
<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8"/>
        <title>{% block title %}Welcome{% endblock %}</title>
        {% block stylesheets %}
            <link href="{{ asset('css/estilos.css') }}" rel="stylesheet" />
        {% endblock %}
        <link rel="icon" type="image/x-icon" href="{{ asset('favicon.ico') }}" />
    </head>
    <body>
        {% block body %}{% endblock %}
        {% block javascripts %}(% endblock %}
    </body>
</html>
```

| app\Resources\views\dosColumnas.htm.twig |
|------------------------------------------|
```twig
<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8"/>
        <title>{% block titulo %}Proyecto Symfony{% endblock %}</title>
    </head>
    <body>
        {% block contenido %}Contenido{% endblock %}
    </body>
</html>
```

| src\Resources\views\default\nombres.htm.twig |
|--------------------------------------|
```twig
{% extends 'default\dosColumnas.html.twig' %}
{# Bucará ese archivo dentro de app\Resources\views\ #}
{# Para extender la plantilla base                   #}
{% block contenido %}
    <ul>
        {% for nombre in nombres if nombre.activo %}
            <li>{{ nombre.nombre }}</li>
        {% endfor %}
    </ul>
{% endblock %}
```

Mostrará la extensión de **app\Resources\views\dosColumnas.htm.twig** incluyendo la parte de **app\Resources\views\base.htm.twig** que no aparezca en el primero.

--------------------------------------------------------
**EJEMPLOS DE RUTAS DENTRO DE BUNDLE**

* `{% extends '::dosColumnas.html.twig' %}` lo buscaría dentro de **src\PruebaBundle\Resources\views\dosColumnas.html.twig** (*hace referencia al bundle propio de la vista*).
* `{% extends 'PruebaBundle::dosColumnas.html.twig' %}` lo buscaría dentro de **src\PruebaBundle\Resources\views\dosColumnas.html.twig**.
* `{% extends 'PruebaBundle:Eventos:dosColumnas.html.twig' %}` lo buscaría dentro de **src\PruebaBundle\Resources\views\Eventos\dosColumnas.html.twig**.
* `{% extends 'PruebaBundle:Templates:dosColumnas.html.twig' %}` lo buscaría dentro de **src\PruebaBundle\Resources\views\Templates\dosColumnas.html.twig**.

--------------------------------------------------------

3.¿Cómo realizar Rutas definiendo idiomas?
--------------------------------------------

Una buena solución para incluir la configuración regional en la URL consiste en incluir parámetro `_locale especial` (Ver documentación oficial, [aquí](http://symfony.com/doc/current/translation/locale.html)).

```yml
# app/config/routing.yml
contact:
    path:     /{_locale}/contact
    # por defecto damos el valor ESPAÑOL a '_locale' 
    defaults: { _controller: AppBundle:Contact:index, _locale:es }
    requirements:
        _locale: en|fr|de|es
```

Para recoger la información sobre el lenguaje usaríamos dentro del método el siguiente código:

```php
use Symfony\Component\HttpFoundation\Request;

public function indexAction(Request $request)
{
    $locale = $request->getLocale();
}
```
