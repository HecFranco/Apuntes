¿Como generar entidades a partir de una base de datos ya definida y creada?
---------------------------------------------------------------------------

Primero crearemos la base de datos con la configuración definida dentro de **app\config\parameter.yml**, que incluimos durante la instalación del proyecto **Symfony**, mediante el comando `php bin/console doctrine:database:create`.

Para borrarla, si fuera necesario usaremos `php bin/console doctrine:database:drop --force`.

La configuración del cotejamiento a usar dentro de la nueva base de datos viene definido en **app/config/config.yml**
```yml
doctrine:
    dbal:
        charset: utf8mb4
        default_table_options:
            charset: utf8mb4
            collate: utf8mb4_unicode_ci
```

A continuación incluiremos la base de datos con la siguiente estructura en este caso en nuestro servidor mediante **PhpMyAdmin**.

```sql
CREATE TABLE IF NOT EXISTS `productos` (
  `id` int(255) NOT NULL AUTO_INCREMENT,
  `name` varchar(255) DEFAULT NULL,
  `description` varchar(255) DEFAULT NULL,
  `price` varchar(255) DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB  DEFAULT CHARSET=latin1 AUTO_INCREMENT=58 ;

INSERT INTO `productos` (`id`, `name`, `description`, `price`) VALUES
(1, 'Hola', 'fdasfsa', 'fdasdf'),
(2, 'fasdf', 'fasdfas', 'fdasfsa'),

CREATE TABLE IF NOT EXISTS `usuarios` (
  `id` int(255) NOT NULL AUTO_INCREMENT,
  `name` varchar(255) NOT NULL,
  `surname` varchar(255) NOT NULL,
  `description` text NOT NULL,
  `email` varchar(255) NOT NULL,
  `password` varchar(255) NOT NULL,
  `image` varchar(255) NOT NULL,
  `alternative` varchar(255) NOT NULL,
  PRIMARY KEY (`id`),
  UNIQUE KEY `email` (`email`)
) ENGINE=InnoDB  DEFAULT CHARSET=latin1 AUTO_INCREMENT=18 ;

INSERT INTO `usuarios` (`id`, `name`, `surname`, `description`, `email`, `password`, `image`, `alternative`) VALUES
(3, 'Rasmus', 'Lerdorf PHP', 'Creador de PHP', 'rasmus@lerdorf.com', 'contraseña de prueba', '', ''),
(4, 'Bruce', 'Wayne', 'Soy Batman', 'bruce@wayne.com', 'batman', 'null', 'null'),
```

* Le indicamos a doctrine que mapee convirtiendo a formato **.xml** en la ubicación **/src/AppBundle/Resources/doctrine/metadata/orm/** la base de datos de manera forzada.

`php bin/console doctrine:mapping:convert xml ./src/AppBundle/Resources/doctrine/metadata/orm --from-database --force`

Usaremos `php bin/console doctrine:mapping:import AppBundle yml` para exportar esos metadatos a **.yml**. Esto generará dentro de **src\BackendBundle\Resources\config\doctrine\ ** los mapeos de la base de datos en formato **.orm.yml**

Como dentro de la base dedatos la tabla se llama **productos** habrá que modificar el nombre los archivos ubicados en **src\BackendBundle\Resources\config\doctrine\ **
* **productos.orm.yml** por **producto.orm.yml** y dentro también el nombre de la entidad a `ackendBundle\Entity\producto`
* **usuarios.orm.yml** por **usuario.orm.yml** y dentro también el nombre de la entidad a `ackendBundle\Entity\usuario`

Después usaremos el comando `php bin/console doctrine:generate:entities BackendBundle`, esto generará dentro de **src\BackendBundle\Entity** las entidades en formato **.php** con los **getters** y **setters** necesarios para trabajar con la Base de Datos.

**Nota**: Usaríamos `php bin/console doctrine:generate:entities AppBundle` para generar todas las entidades del **Bundle** definido, en este caso **AppBundle**.
**Nota**:  Usaríamos `php bin/console doctrine:generate:entities Acme` para generar todas las entidades del **namepsace** definido, en este caso **Acme**.


¿Como generar entidades desde cero?
-----------------------------------

Si lanzamos el comando `php bin/console doctrine:generate:entity` iniciaremos un asistente que ayudará a definir la nueva entidad. (así definiremos una nueva tabla desde cero)

El comando `php bin/console doctrine:schema:update --force` generará en la base de datos las tablas defindas por las entidades creadas. Así al igual que en caso anterior dentro de **src\BackendBundle\Resources\config\doctrine\curso.orm.yml** definiremos el nombre de la tabla en plurarl `table: cursos` ya que la tabla definirá cada curso (en singular) y la tabla contendrá el listado de cursos (en plural).

Para borrar la base de datos, si fuera necesario usaremos `php bin/console doctrine:database:drop --force`.