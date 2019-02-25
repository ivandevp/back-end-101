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