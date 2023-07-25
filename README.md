# ECOMMERCE -VINOS Y LICORES.

## MODELADO DE DATOS

1. #### Identificar las entidades del sistema. ✔️
1. #### Identificar los atributos de las entidades. ✔️
1. #### Identificar las llaves primarias y foráneas. ✔️
1. #### Asignar una nomenclatura adeacuada a las entidades y sus atributos. ✔️
1. #### Identificar las entidades pivote del sistema. ✔️
1. #### Identificar los catálogos del sistema. ✔️
1. #### Identificar los tipos de relaciones del sistema.
1. #### Crear el Modelo Entidad-Relación del sistema.
1. #### Crear el Modelo Relacional de la base de datos del sistema.
1. #### Identificar los tipos de dato de los atributos de las entidades del sistema.
1. #### Identificar los atributos que puedan ser únicos en el sistema.
1. #### Identificar las reglas de negocio (Operaciones CRUD) del sistema.

---

## ENTIDADES

### users

-   **id (PK)**
-   **name**
-   **lastname**
-   **email (UQ)**
-   **password**
-   **photo_id (FK)**

### addresses

-   **id (PK)**
-   **user_id**
-   **neighborhood**
-   **street**
-   **city**
-   **state**
-   **country**
-   **zip_code**
-   **phone_id (FK)**

### phones

-   **id (PK)**
-   **phone**
-   **phone_code_id (FK)**

### phone_codes (EC)

-   **id (PK)**
-   **code (UQ)**
-

### products

-   **id (PK)**
-   **name**
-   **price**
-   **quantity**
-   **discount**
-   **photo_id (FK)**

### orders

-   **id (PK)**
-   **user_id (FK)**
-   **status**
-   **total**

### articles_x_orders (EP)

-   **id (PK)**
-   **order_id (FK)**
-   **product_id (FK)**
-   **quantity**
-   **subtotal**

### photos

-   **id (PK)**
-   **url**

### imageables (EP) | entidad pivote polimorfica (productos, usuarios)

-   **id (PK)**

## RELACIONES

-   usuario _compra_ productos ( _1,N_ ).
-   usuario _tiene_ ordenes ( _1,N_ ).
-   usuario _tiene_ direcciones ( _1,N_ ).
-   usuario _tiene_ foto (_1,1_).
-   direccion _tiene_ telefono (_1,1_).
-   telefono _tiene_ codigo de telefono referente al país (_1,1_)
-   producto _tiene_ fotos (_1,N_).
-   articles x orders _pertenece_ orden (_N,1_).
-   artucles x orders _tiene_ products (_1,N_).

## REGLAS DE NEGOCIO

### users

1. creaer un usuario.
1. leer todos los usuarios.
1. leer un usuario en particular.
1. actualizar un usuario.
1. eliminar un usuario.

### products

1. creaer un producto.
1. leer todos los productos.
1. leer un producto en particular.
1. actualizar un producto.
1. eliminar un producto.
1. cada que haya una venta restar a la cantidad de productos disponibles el numero de articulos que se vendieron.

    ### orders

1. creaer una venta.
1. leer todas las ventas.
1. leer una venta en particular.
1. leer todas las ventas de un cliente.
1. leer todas las ventas de un producto.
1. actualizar una venta.
1. eliminar una venta.

### articles_x_orders

1. crear un articulo.
1. leer todos los articulos.
1. leer un articulo en particular.
1. leer todos los articulos de una venta.
1. leer todos los articulos de un producto.
1. leer todos los articulos de un cliente.
1. actualizar un articulo
1. eliminar todos los articulos

### photos

1. añadir foto.
1. actualizar foto.
1. eliminar foto.

### addresses

1. crear un adireccion
1. leer una direccion
1. leer todas las direcciones de un usuario
1. actualizar una direccion
1.eliminar una direccion
