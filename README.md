# Back-end 101

## Duración

6 sesiones de 2-2.5 horas cada una.

## Lo que sería bueno saber antes del curso

Si bien es un curso introductorio de Back-end, el lenguaje que usaremos será
JavaScript ejecutándose desde el lado del servidor con Node.js. Esto debido a la
gran demanda por programadores Node.js además de que asumimos que quienes toman
el curso se dedican principalmente al desarrollo front-end y/o están relacionadas
con JavaScript. Adicional a esto, conocer las actualizaciones del estándar (ES6+)
será útil para llevar a cabo algunos ejercicios o inclusive el proyecto.

## Lo que veremos

* Ejecutar JavaScript en el servidor a través de Node.js
* Trabajar con módulos de NPM
* Realizar tareas asíncronas
* Leer archivos que se encuentran en tu computador
* Modelar una base de datos relacional y/o NoSQL
* Crear una API REST que pueda ser consumida desde el front-end y que devuelva
  datos de la base de datos
* Desplegar tu API a un servidor PaaS o IaaS
* Trabajar con frameworks de Node.js
* Llevar un enfoque de TDD durante el desarrollo

## Proyecto

El proyecto que trabajaremos en este curso será un e-commerce. Como se darán
cuenta, el tiempo no dará para entrar a detalle en cada punto de lo que implica
un e-commerce, pero implementaremos a grandes rasgos, partes del funcionamiento
principal.

## Contenido

El curso se divide en 6 sesiones:

### Sesión 1: ¿Qué es Back-end y cómo es eso que JavaScript se ejecuta en un servidor?

En esta sesión, entenderemos cuáles son las tareas comunes que realiza un
desarrollador Back-end, además de entender qué es Node y para qué nos servirá.
Una vez que tengamos las cosas claras, veremos más a detalle el entorno de Node:

* Node REPL
* Módulos
* NPM
* APIs nativas de Node.js

### Sesión 2: Creamos el listado de productos

Para mostrar el listado de productos de nuestra aplicación, debemos de tenerlas
almacenadas en algún lugar, para esto, comenzaremos leyendo los datos desde
diversas lugares hasta llegar a una base de datos y exponiéndolos a través de una
API REST.

* ¿Qué es una API REST?
* ¿Cómo crear una API REST con Node.js?
* ¿Cómo crear una API REST con un framework de Node.js?
* Base de datos relacionales vs no relacionales (SQL vs NoSQL)
* Exponiendo los datos desde memoria
* Exponiendo los datos desde un JSON en el servidor
* Exponiendo los datos desde una base de datos

### Sesión 3: Agregamos los productos a un carrito de compras

Una vez listado los productos, debemos de tener la habilidad de agregarlos al
carrito de compras y persistir los datos cuando se recargue la página.

* Crear método de escritura de datos a una API
* Manejo de sesiones
* Caching de listado de productos

### Sesión 4: Autenticamos al usuario

Con el carrito de productos terminado, el usuario quiere proceder a pagar su
pedido, sin embargo, no sabemos quién es el usuario ni a dónde debe llegar su
pedido, para esto necesitamos autenticar al usuario.

* Creación de modelo de usuario
* Agregar registro del usuario
* Login y logout del usuario
* Asociar el pedido al usuario

### Sesión 5: Completamos la compra

Una vez pagado, el usuario no obtiene sus productos instantáneamente, por lo que
se debe crear un pedido, este debe estar modelado y almacenado en la base de
datos. Además, el usuario debe tener la capacidad de consultar dichos pedidos.

* Crear endpoint de consulta de pedidos
* Limpiar la sesión de la compra terminada
* Cambiar los estados del pedido

### Sesión 6: ¿Qué viene luego?

Con las sesiones anteriores, debes tener un comercio electrónico básico
funcionando, además de haber descubierto algunas cosas de back-end y cómo estas
se enlazan al front-end. En esta sesión, desplegaremos nuestro producto terminado
a un servidor en internet y dejaremos de ver las cosas localmente y daremos
recomendaciones de qué cosas podemos hacer en esta versión mínima del proyecto.

* Deploy a un PaaS como Heroku
* Deploy a un IaaS
* Agregar GraphQL?
* Real time?
* Testing all the things?
* Docker?