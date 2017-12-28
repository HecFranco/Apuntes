** .orm.yml **
--------------
```yml
# src\BackendBundle\Resources\config\doctrine\User.orm.yml
BackendBundle\Entity\User:
    type: entity       # Nombre de la columna en la BD
    table: users       # Nombre de la columna en la BD
```
Si usamos un Repositorio
```yml
# Para incluir Repositorios
    repositoryClass: BackendBundle\Repository\UserRepository
```
Para indicar las columnas que tienen valores únicos
```yml
# Columnas con valores únicos
    uniqueConstraints:
        users_uniques_fields:
            columns:
                - email # Nombre de la columna en la BD
                - nick  # Nombre de la columna en la BD
```
Para indicar las columnas que son índice
```yml
    indexes:
        fk_emmiter_privates:
            columns:
                - emitter # indica la columna que hará de indice
        fk_receiver_privates:
            columns:
                - receiver # indica la columna que hará de indice
```
La Id de la tabla
```yml
id:
    id:
        type: integer
        nullable: false
        options:
            unsigned: false
        id: true
        generator:
            strategy: IDENTITY
```
Definimos los datos según su columna y su configuración
```yml
fields:
# COLUMNAS SEGÚN EL TIPO DE DATO
    email:
        type: string
        nullable: true
        length: 20
        options:
            fixed: false
    createdAt:
        type: datetime
        nullable: true
        column: created_at
    text:
        type: text
            nullable: true
            length: 16777215
            options:
                fixed: false
    typeId:
        type: integer
            nullable: true
            options:
                unsigned: false
            column: type_id
```
**MANY TO ONE**
```yml
    manyToOne:
        user:
            targetEntity: User # Entidad referenciada
            cascade: {  }
            fetch: LAZY
            mappedBy: null
            inversedBy: null
            joinColumns:
                user_id: # columna de la entidad referenciada
                    referencedColumnName: id
            orphanRemoval: false
    lifecycleCallbacks: {  }
```
