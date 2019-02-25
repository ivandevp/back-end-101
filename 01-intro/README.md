# ¿Qué es Back-end y cómo es eso que JavaScript se ejecuta en un servidor?

## ¿Qué es Back-end development?

![Back-end Developer](https://img.devrant.com/devrant/rant/r_732049_Ab61B.jpg)

El back-end development a diferencia del front-end development está enfocado en
la parte que el usuario final no ve. En muchas ocasiones relacionados con las
base de datos, construcción de APIs y manejo de servidores. A pesar, de que esta
relación viene impuesta sobre todo por las descripciones de trabajo que las
empresas ofertan, recordar que el desarrollo de back-end también puede ampliarse
a la construcción de CLI tools, manejo de sistema de archivos, administración de
procesos del sistema operativo y más.

En mi opinión, el desarrollo back-end cubre las limitancias del navegador, es
decir, el navegador ha evolucionado con el paso de los años y ahora permite hacer
cosas increíbles desde el mismo solo con programación del lado del front-end,
pero aun carece de muchas cosas donde el back-end debido a que su entorno de
ejecución se hace sobre el sistema operativo tiene más poderes. Por ejemplo, si
bien el navegador tiene un _storage_ es limitado como para guardar todos los posts
de Facebook que ocurren diariamente, y necesitamos acceso al hardware del
computador (disco duro) para poder almacenar semejante cantidad de datos, a la
cuál el navegador _aun_ no tiene poder de acceder.

Si deseas tener una idea de los conceptos que se manejan en el desarrollo back-end,
podemos tomar como referencia el [back-end roadmap](https://github.com/kamranahmedse/developer-roadmap#back-end-roadmap)
que se encuentra disponible y open-source en Github.

Cómo bien se menciona en dicho roadmap, lo primero que debemos de hacer, es
escoger un lenguaje, esto debido a que del lado del back-end no hay una especificación
o estándar como tal, la cual en el caso del front-end tenemos esto del lado de la
W3C y ECMA. Debido a ello, en el back-end tenemos un abanico más amplio de lenguajes
de programación y los cuáles presentan pros y contras en diferentes contextos.
Para este curso, aprovecharemos nuestros conocimientos previos de JavaScript para
ejecutarlo desde el back-end a través de [Node.js](https://nodejs.org/).

## ¿Cómo se ejecuta JavaScript en el lado del servidor?

JavaScript fue creado en 1995 por Brendan Eich mientras trabajaba en Netscape
para tener una alternativa al desarrollo de interacciones web (front-end), sin
embargo, también comenzaron a realizar implementaciones de este lenguaje en el
servidor, ninguna de ellas con gran adaptación por parte de la comunidad.

En el 2009, un ingeniero de [Joyent](https://www.joyent.com/), [Ryan Dahl](https://github.com/ry),
decidió mostrar un proyecto en el que había estado trabajando para tener un
entorno de ejecución en el back-end para creación de servidores bajo un paradigma
orientado a eventos y asíncrono por defecto. Esta presentación se dio en la
JSCONF EU del 2009, pueden ver el video en Youtube:

[![Node.js original presentation](https://img.youtube.com/vi/ztspvPYybIY/0.jpg)](https://www.youtube.com/watch?v=ztspvPYybIY)

Entonces, ¿cómo es que JavaScript, un lenguaje orientado al desarrollo front-end
puede ejecutarse en el servidor? Para responder a esto, tenemos que entender
cómo funciona JavaScript realmente.

JavaScript como tal es un estándar especificado a través de la organización ECMA,
ésta a través de un comité (TC39) se encarga de definir la sintaxis del lenguaje.
Por otro lado, quiénes le dan vida, son los navegadores que después de una ardua
batalla, se ha buscado mantener una especificación definida y mantenida por la
W3C. Entonces, ¿quién se encarga en si de que JavaScript funcione? Respuesta:
**los navegadores**. ¿Qué tiene de especial los navegadores para que entiendan
código escrito en JavaScript? **Los JavasScript engines** (motores de JavaScript).

| Browser | JavaScript Engine                                                                           |
| ------- | ------------------------------------------------------------------------------------------- |
| Chrome  | [V8](https://v8.dev/)                                                                       |
| Firefox | [SpiderMonkey](https://developer.mozilla.org/en-US/docs/Mozilla/Projects/SpiderMonkey)      |
| Safari  | [JavaScriptCore](https://developer.apple.com/documentation/javascriptcore)                  |
| MS Edge | [Chakra](https://github.com/Microsoft/ChakraCore)                                           |

Ryan Dahl, inspirado por el lanzamiento del motor de JavaScript open-source, lo
usó para crear una arquitectura entre JavaScript y C++ para poder ejecutar
JavaScript desde cualquier entorno de ejecución.

![Node.js architecture](https://i.stack.imgur.com/fUhaP.png)

## ¿Qué es Node.js?

Node.js no es un lenguaje de programación, ni librería, ni framework. Como dice
en su página oficial, es un entorno de ejecución. Un conjunto de librerías, engine,
bindings y demás mostrado en la imagen anterior, permiten que JavaScript pueda
ser interpretado en cualquier entorno. Esto abrió muchas puertas para un
desarrollo ascendente y muchas librerías y frameworks basados en Node.js, ahora
con JavaScript podemos hacer:

* Cli Tools (Ejemplo: [npm](https://www.npmjs.com/))
* Aplicaciones de escritorio (Ejemplo: [Electron](https://electronjs.org/))
* Bases de datos (Ejemplo: [MongoDB](https://www.mongodb.com/))
* IoT (Ejemplo: [Johnny Five](http://johnny-five.io/))
* Servidores Web (Eejemplo: [Express](https://expressjs.com/))
* Aplicaciones móviles (Ejemplo: [React Native](https://facebook.github.io/react-native/))
* Y mucho más

Por último, un dato importante, [Node.js es **open-source**](https://github.com/nodejs/node)
y tiene releases programados, además de que el crecimiento del runtime está dirigido
por una fundación llamada [_Node.js Fundation_](https://foundation.nodejs.org/).

### ¿Cómo instalar Node.js?

En su [página orficial](https://nodejs.org), podemos encontrar el ejecutable
para cada sistema operativo y opciones para compilarlo desde su código fuente.
Algo muy común cuando se desarrolla con Node.js es que diversos proyectos pueden
usar diversas versiones de Node.js, esto debido a la constante evolución y releases
programados que existen, además del soporte a largo plazo que le dan a cad versión.

Para no sufrir con instalar diferentes versiones de Node.js para cada proyecto,
existen manejadores de versiones que a través de unos comandos simples, pueden
ayudarte a hacer este dolor de cabeza algo llevadero. A continuación se listan
2 de los más populares:

* [nvm](https://github.com/creationix/nvm)
* [n](https://github.com/tj/n)

### Comenzar a probar JavaScript en el servidor