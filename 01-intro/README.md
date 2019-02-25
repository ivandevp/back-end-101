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

Para empezar a jugar JavaScript sin tener que abrir el navegador, podemos hacer
uso del `REPL` (_Read Evaluate Print Loop_), esto lo logramos escribiendo `node`
en la consola (te darás cuenta que tu _prompt_ cambió).

```bash
$ node
> # El prompt cambió a `>` en vez de `$`
```

Estando con el prompt de ese modo, puedes ejecutar cualquier sentencia de JavaScript,
tal cual lo harías en la consola del Dev Tools de tu navegador.

```bash
> console.log('Hola mundo');
Hola mundo
> 2 + 3
5
>
```

De esta manera ya tienes una forma rápida de probar tu código JavaScript desde tu
terminal sin necesidad de un click derecho a un navegador :wink:.

Para salir de tu terminal interactiva de Node (REPL), puedes escribir `.exit` y
presionar ENTER ó presionar `CTRL+C` 2 veces.

Para mayor información, puedes encontrar la [documentación de Node REPL](https://nodejs.org/api/repl.html).

### ECMAScript en Node.js

A diferencia del navegador, Node.js tiene una programación de releases diferente,
por lo que los nuevos features de ECMAScript pueden tardar un poco en verse
reflejadas en Node.js. Para saber qué features puedes usar y cuándo llegan las
siguientes versiones, puedes ver:

* [Releases de Node.js](https://raw.githubusercontent.com/nodejs/Release/master/schedule.svg?sanitize=true)
* [Node Green](https://node.green/)

### Empezar a jugar en serio con Node.js

Si bien el REPL, nos permite escribir código JavaScript que pueda ser interpretado,
no vamos a estar escribiendo nuestros programas en esta consola interactiva,
necesitamos nuestro kit de herramientas que nos dan superpoderes como los editores
de texto, archivos, sistema de control de versiones y demás tooling que puedas
usar para programar. ¿Cómo replicamos ese workflow para programar con Node.js?

Bien, puedes usar cualquier editor de texto y herramientas que deseas, lo único
que debes de tener en cuenta es que debes crear archivos con extensión `.js` (sí,
igual que tus archivos de front-end) y al momento de ejecutarlo, tendrás que abrir
tu terminal en la ubicación del proyecto y ejecutar `node nombre-archivo.js`.

¿Sencillo, verdad?

Vamos a hacer una prueba. Si tienes el siguiente código:

```js
// primer-proyecto/index.js
console.log('Hola mundo');
```

En tu terminal, escribirías:

```bash
$ primer-proyecto: node index.js
Hola mundo
$ primer-proyecto:
```

### Módulos

En Node.js usamos módulos como una forma de encapsular código de forma distribuida
de tal forma que podamos distribuir y usar librerías de una manera más sencilla,
además de crear una arquitectura de software más escalable y mantenible en el tiempo.

#### Usando módulos

Para usar módulos creados por nosotros, provistos por Node.js o externos (de la
comunidad o privados) podemos hacer uso de la función global `require()`. Esta
viende definida por Node.js y no es necesario instalar nada.

Para hacer una prueba, vamos a hacer uso de una API incluida en Node.js para
saber el sistema operativo sobre la cuál estás trabajando. Esta API está disponible
a travś del módulo `os`.

Hagámoslo :sunglasses: :

```js
// segundo-proyecto/index.js
const os = require('os'); // Requerimos el módulo `os` y lo guardamos en una variable

/**
 * .platform() es un método del módulo os que nos devuelve un string con la
 * identificación del sistema operativo que estamos usando
 * Más info en: https://nodejs.org/api/os.html#os_os_platform
 **/
console.log(`Estoy trabajando desde ${os.platform()}`);
```

Lo ejecutamos:

```bash
$ segundo-proyecto: node index.js
Estoy trabajando desde darwin # En mi caso darwin es identificador de mac OS
$ segundo-proyecto:
```

### Más APIs de Node.js disponibles

Vamos a hacer un ejercicio, usando las APIs de File System y Readline, ambos
con módulos disponibles por defecto en el entorno de Node.js.

El ejercicio constará en pedirle al usuario que ingrese un texto y lo
almacenaremos en un archivo de nuestra computadora. ¿Logras identificar o inferir
qué módulo usaremos para qué acción? :thinking:

#### Usando readline

En Node.js, el [módulo readline](https://nodejs.org/api/readline.html) nos
permite leer datos de un stream línea por línea.
El stream usado para obtener y escribir datos en la terminal lo podemos encontrar
en una variable global que viene con Node.js, llamada [`process`](https://nodejs.org/api/process.html).

##### Configurando readline

```js
// tercer-proyecto/index.js
const readline = require('readline');

const rl = readline.createInterface({
    input: process.stdin,
    output: process.stdout,
});
```

De esta manera estamos creando una interface de readline haciendo uso de `process.stdin`
y `process.stdout` como flujo de datos de entrada y salida respectivamente.

Es así como podremos usar nuestra constante `rl` para interactuar a través de la
terminal con el usuario (similar a lo que hace un prompt en el navegador).

##### Pidiendo datos al usuario

```js
// tercer-proyecto/index.js
// ... -> aquí viene el código anterior

rl.question('Escribe algo que quieras guardar: ', (answer) => {
    console.log(`Escribiste: ${answer}`);

    rl.close();
});
```

El método `.question()` nos permite hacer una pregunta al usuario usando los flujo
de datos de entrada y salida configuradas en la interface. La forma de manejar
la respuesta ingresada por el usuario es a través de `callbacks`. El método
`.question()` nos mandará el texto escrito por el usuario a través del primer
argumento del callback (en nuestro caso, lo nombramos `answer`), una vez obtenido
le hemos indicado a Node.js que haga un `console.log` de lo que escribió y por
último que cierre el flujo de datos para que no se quede esperando a que el usuario
ingrese otro texto o tenga que salir manualmente.

¡Genial! De esta manera ya le podemos interactuar con el usuario a través de la
terminal, ¿Está cool no?

Aquí el código completo:

```js
// tercer-proyecto/index.js
const readline = require('readline');

const rl = readline.createInterface({
    input: process.stdin,
    output: process.stdout,
});

rl.question('Escribe algo que quieras guardar: ', (answer) => {
    console.log(`Escribiste: ${answer}`);

    rl.close();
});
```

#### Usando fs

En Node.js, el [módulo fs](https://nodejs.org/api/fs.html) nos permite interactuar
con el sistema de archivos de nuestro sistema operativo. Las operaciones frecuentes
son: crear y/o leer directorios, crear, editar, leer archivos, entre otros.

##### Escribiendo un archivo

```js
// cuarto-proyecto/index.js
const fs = require('fs');

fs.writeFile('prueba.txt', 'Hola mundo', (err) => {
    if (err) {
        console.error(`Hubo un error ${error.message}`);
        return;
    }

    console.log('El archivo se escribió correctamente');
});
```

En este caso, el módulo fs tiene un método llamado `.writeFile()`, el cual recibe
3 parámetros (la ruta del archivo a escribir, el contenido que se quiere escribir y
un callback que se ejecuta cuando termina la ejecución del método pasando un objeto
de error como argumento del mismo). El callback se ejecutará una vez que el contenido
se ha escrito en el archivo, si el archivo no existe, este lo creará. La condición
que escribimos en el callback es para identificar si ocurrió un error, en caso así
fuera le estamos indicando a Node.js que hagamos un `console.log` del mensaje
de error y luego hacemos un `return;` para salir del callback, si no hacemos
esto, se imprimiría el `console.log` de que el archivo se escribió con éxito.

Si vemos nuestra carpeta del proyecto, veremos el archivo con el texto _'Hola mundo'_
dentro. ¿Qué crees que pase si vuelves a ejecutar el mismo script (archivo) con
un texto diferente? Respuesta: Reemplazará el contenido del archivo.

Este comportamiento puede ser alterado, para que cada vez que se escriba algo
nuevo se agregue y no modifique lo anterior, para lograr esto, el método `.writeFile()`
soporta 4 argumentos, siendo el tercero opcional, el cual es un objeto con una
propiedad llamada [`flag`](https://nodejs.org/api/fs.html#fs_file_system_flags)
que hace referencia a las opciones del sistema de archivos. El flag que usaremos
será `'a'` que hace referencia a _appending_ (agregar al final del archivo).

Agregando ese código, nuestro script quedaría así:

```js
// cuarto-proyecto/index.js
const fs = require('fs');

fs.writeFile('prueba.txt', 'Nuevo texto', { flag: 'a' }, (err) => {
    if (err) {
        console.error(`Hubo un error ${error.message}`);
        return;
    }

    console.log('El archivo se escribió correctamente');
});
```

#### Mezclando readline y fs

Ahora que hemos visto estas 2 APIs (ḿodulos) por separado, podemos hacer nuestro
ejercicio uniendo ambas. En este caso, usaremos `readline` para pedirle que el usuario
escriba un texto y con `fs` guardaremos el texto ingresado en un archivo.

Si pensamos en nuestro código por un momento, lo primero que debemos hacer es
pedirle al usuario que ingrese el texto, y _una vez obtenido_ escribir el archivo.
Eso quiere decir de que el siguiente código no funcionaría:

```js
// quinto-proyecto/index.js
const fs = require('fs');
const readline = require('readline');

const rl = readline.createInterface({
    input: process.stdin,
    output: process.stdout,
});

rl.question('Escribe algo que quieras guardar: ', (answer) => {
    console.log(`Escribiste: ${answer}`);

    rl.close();
});

fs.writeFile('prueba.txt', 'Nuevo texto', { flag: 'a' }, (err) => {
    if (err) {
        console.error(`Hubo un error ${error.message}`);
        return;
    }

    console.log('El archivo se escribió correctamente');
});
```

Esto debido a que ambos métodos que usamos son asíncronos, y la manera de obtener
el resultado del primer método y usarlo en el segundo, lo hacemos a través del
callback, entonces, podemos anidar dichos callbacks algo así:


```js
// quinto-proyecto/index.js
const fs = require('fs');
const readline = require('readline');

const rl = readline.createInterface({
    input: process.stdin,
    output: process.stdout,
});

rl.question('Escribe algo que quieras guardar: ', (answer) => {
    console.log(`Escribiste: ${answer}`);

    fs.writeFile('prueba.txt', answer, { flag: 'a' }, (err) => {
        if (err) {
            console.error(`Hubo un error ${error.message}`);
            return;
        }

        console.log('El archivo se escribió correctamente');
    });

    rl.close();
});
```

Si probamos nuestro código nuevamente, ahora si obtendremos el resultado esperado,
simplemente reemplazando agregando nuestro método de `.writeFile()` dentro del
callback obtenido de `.question()` para tener acceso a la respuesta del primero.

¿Se imaginan si tendríamos que hacer más operaciones asíncronas después de escribir
el archivo? Seguiríamos anidando callbacks tras callbacks. Esto es un problema
conocido como [`callback hell`](http://callbackhell.com/). Debido a que esto es
un problema común y nada nuevo, la especificación de ES6+ ha agregado nuevos features
que permitan manejar de una manera más legible la asincronía. (Ejemplo: Promises).

Para efectos del contenido teórico y demostrativo, esto está bien. Sin embargo,
en el [repositorio de ejercicios](https://github.com/ivandevp/back-end-101-exercises),
podrás encontrar, diversas maneras de como manejar mejor la asincronía en Node.js.

## Reto

Para jugar un poco más con las APIs de Node.js, usando los mismos módulos de
`readline` y `fs`. Crea un script que le pida al usuario ingresar un texto a
buscar dentro de un archivo. Y responder con un mensaje del resultado de la búsqueda,
por ejemplo un mensaje de _encontrado_ o _no existe_.

### Hacker edition

Además de retornar el mensaje, en caso de que se encuentre el texto, indicar
cuántas veces se repite en todo el texto. Ejemplo

Archivo de texto:

```text
Hola hola holA HOLA
```

Texto a buscar: `hola`

Resultado: `El texto 'hola' se encontró 4 veces`.