```php
// src/BackendBundle/Entity/Product.php
namespace AppBundle\Entity;

class Product
{
    private $name;
    private $price;
    private $description;
}
```
```php
public function createAction()
{
    // you can fetch the EntityManager via $this->getDoctrine()
    // or you can add an argument to your action: createAction(EntityManagerInterface $em)
    $em = $this->getDoctrine()->getManager();

    $product = new Product();
    $product->setName('Keyboard');
    $product->setPrice(19.99);
    $product->setDescription('Ergonomic and stylish!');
    // tells Doctrine you want to (eventually) save the Product (no queries yet)
    $em->persist($product);
    // actually executes the queries (i.e. the INSERT query)
    $em->flush();
    return new Response('Saved new product with id '.$product->getId());
}
```

Tipos de find() en Symfony() ¿Cómo generamos consultas a la base de datos?
--------------------------------------------------------------------------

Para hacer consultas a la base de datos tendremos que realizarlas dentro de método correspondiente en el controlador ejecutado que pertenece al Bundle. (ver documentación oficial aquí)

```php
$repository = $this->getDoctrine()->getRepository(Product::class);
// query for a single product by its primary key (usually "id")
$product = $repository->find($productId);
// dynamic method names to find a single product based on a column value
$product = $repository->findOneById($productId);
$product = $repository->findOneByName('Keyboard');
// dynamic method names to find a group of products based on a column value
$products = $repository->findByPrice(19.99);
// find *all* products
$products = $repository->findAll();
```

Así por ejemplo tendremos:

```php
<?php
// src\PruebaBundle\Controller\DefaultController.php
namespace PruebaBundle\Controller;

use Symfony\Bundle\FrameworkBundle\Controller\Controller;

class DefaultController extends Controller{
   public function indexAction($eventos){
       // Usamos EntityManager ($em)
       $em = $this->getDoctrine()->getManager();
       // Creamos el objeto que obtendrá el listado de productos
       $eventos = $em->getRepository('PruebaBundle:Eventos')->findAll();
       // llama a una vista que se llama por defecto index.html.twig
       return $this->render('PruebaBundle:Default:index.html.twig', array('eventos'=>$eventos));
   }
}
```

Consultas SQL nativo
--------------------

```yml
# src\AppBundle\Resources\config\routing.yml
pruebas_consultaSql:
    path: /consultaSql/
```
```php
public function nativeSqlAction(){
  // Usamos EntityManager ($em)
  $em = $this->getDoctrine()->getManager();
  // Conectamos a la base de datos
  $db = $em->getConnection();
  $query = "SELECT * FROM cursos";
  $stmt = $db->prepare($query);
  // Pasamos los parámetros a la Consultas
  $params = array();
  $stmt->execute($params);
  // almacenamos los resultados
  $cursos = $stmt->fetchAll();
  foreach($cursos as $curso){
    echo $curso ["title"]."<br/>";
  }
}
```
