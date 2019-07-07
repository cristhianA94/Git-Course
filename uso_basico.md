# Uso básico de git

## Objetivos

En este apartado veremos cómo se usa git de forma básica para trabajar en modo monousuario y con un repositorio centralizado.

* Mantener un control de cambios sobre nuestros archivos.
* Sincronizar dos o más repositorios.
* Tareas básicas de git.

  - [Instalar Git](#Instalar-Git)
  - [Empezando a usar Git](#Empezando-a-usar-Git)
    - [Crear un repositorio](#Crear-un-repositorio)
    - [Iniciando repositorio](#Iniciando-un-repositorio)
    - [Clonando un repositorio](#Clonando-un-repositorio)
    - [¿Cómo funciona git?](#¿Cómo-funciona-git?)
    - [Configurar](#Configurar)
  - [Comandos Básicos](uso_basico.md)
****


## Instalar git

`git` es software libre y se puede instalar en cualquier sistema
operativo. A continuación, los más populares, empezando por el que
aconsejamos para desarrollar software en general, Linux.

### En Linux

Instalar git en Linux es tan simple como usar tu gestor de paquetes favorito. Por ejemplo (recuerda que normalmente necesitarás privilegios de *root* para instalar cualquier programa):

#### En Arch Linux

```
# pacman -S git
```

#### En sistemas Debian, Ubuntu, Mint...

```
# apt-get install git
```

#### En Gentoo

```
# emerge --ask --verbose dev-vcs/git
```

#### En sistemas Red Hat, Fedora:

```
# yum install git
```

### En Mac

Hay dos maneras de instalar Git en Mac, la más fácil es utilizar el instalador gráfico:

[Git for OS X](https://git-scm.com/download/mac) 

### En Windows

Para instalar git en Windows debemos descargar el programa instalador en su web oficial en [https://git-scm.com/downloads](https://git-scm.com/downloads).

Una vez descargado, solo tenemos que ejecutarlo y se abrirá una ventana que nos irá solicitando paso a paso los datos necesarios para la instalación. Pulsaremos el botón "Next" para comenzar y elegir las opciones por defecto que nos marca el isntalador.

Al finalizar la instalación podemos ir al menú inicio, y ejecutar "Git Bash", lo que abrirá una consola donde podremos interactuar con 'git'.



>Los autores de este libro no somos partidarios del uso de Windows
> para desarrollo de software, aunque git no solo se usa para eso. Por
> ello, si tienes que hacerlo porque no
> te queda otro remedio o porque te gusta, otra alternativa es usar
> [git for Windows o `msysgit`](http://msysgit.github.io/), un entorno
> completo que incluye un intérprete de órdenes y un entorno gráfico
> para trabajar desde él. 


## Clientes GUI para Linux, Windows y Mac

En este curso se seguirá la interfaz de *línea de comandos* (o *línea de órdenes*), pero existen varias aplicaciones para diversos sistemas operativos que permiten interactuar gráficamente (*Interfaz GUI*) con `git` de forma más o menos completa.

[Interfaz gráfico para Mac y Windows](http://desktop.github.com/)

[GUI for Linux, Windows y Mac](https://git-scm.com/downloads/guis# "Clientes gráficos")
****
## Empezando a usar git ##

Git es un programa en línea de comandos, y se te supone un conocimiento básico del manejo de esta (cosas como moverse por el árbol de directorios y poco más). No es necesario saber nada complejo, solo los rudimentos básicos.

### Configurar

Lo primero que hay que hacer antes de empezar a usar git es configurar un par de parámetros básicos que nos identifican como usuario, que son nuestro correo electrónico y nuestro nombre.

Git usará estos datos para identificar nuestros aportes o modificaciones a la hora de mostrarlos en logs, etc.

Configurar estos parámetros es muy fácil. Desde la línea de comandos escribimos las siguientes órdenes:

```
git config --global user.name "Nombre que quieras mostrar"
```

y

```
git config --global user.email "correo@electroni.com"
```

¿Qué acabamos de hacer? Veámoslo, paso a paso:

Todos los comandos de git empiezan con la palabra `git`.

En este caso, el comando en sí mismo es `config`, que sirve para configurar varias opciones de git, en el primer caso `user.name` y en el segundo `user.email`.

Habrás notado que hay un parámetro `--global` en cada uno de los comandos. Este sirve para decirle a git que esos datos se aplican a todos los repositorios que abras.

Si quieres que algún repositorio concreto use unos datos distintos, puedes llamar al mismo comando, desde el directorio de ese repositorio, pero usando el parámetro `--local` en lugar de `--global`.

> Las opciones que configures como `--global` se almacenarán en un archivo de tu carpeta home, llamado `.gitconfig`.
> Las opciones `--local` lo harán en un archivo `config` dentro del directorio .git de tu proyecto.

Hay más opciones que se pueden configurar, puedes verlas (y ver los valores que tienen) con el comando:

```
git config --list
```

Si te has equivocado al escribir alguno de estos datos o quieres cambiarlo, solo tienes que volver a ejecutar el comando correspondiente de nuevo, y sobrescribirá los datos anteriores.

Una opción de configuración muy cómoda es `git config --global color.ui true`, que hace que la interfaz de git use (si es posible) colores para resaltar distintos aspectos en el texto de sus mensajes.

### Crear un repositorio

Para crear un repositorio nos dirigimos a la sección `Repositories` y hacemos click en `New`.

![Create a New Repository](https://user-images.githubusercontent.com/24251638/60774992-2d070a80-a0e2-11e9-96b1-8ffe8c329fc8.jpg)

Ingresamos un nombre a nuestro repositorio, una breve descripción de él, elegimos si nuestro repositorio va a ser `Public` o `Private` (solo admito unos pocos repositorios gratuitos privados) y por último nos permite crear un README automáticamente.

### Iniciando un repositorio

Un repositorio de git no es más que un directorio de nuestro ordenador que está bajo el control de git. En la práctica, esto significa que en el directorio raíz de nuestro proyecto hay otro directorio oculto llamado ".git" donde se guardan, por ejemplo, los archivos para el control de historiales y los cambios.

Para iniciar un repositorio solo hay que situarse en el directorio de nuestro proyecto (el que contiene o va a contener los archivos que queremos controlar) y ejecutar la siguiente orden:

```
git init
```

Si todo va bien, este comando responderá algo parecido a

```
Initialized empty Git repository in /ruta/a/mi/proyecto/.git/
```

que significa que ya tienes creado tu primer repositorio. Vacío, pero por algo hay que empezar.

### Clonando un repositorio

Un repositorio también puede iniciarse copiando (*clonando*) otro ya existente.

```
git clone REPOSITORIO
```

por ejemplo:

```
git clone https://github.com/cristhianA94/Git-Course
```

Git usa su propio protocolo "git" para el acceso remoto (también se puede clonar un repositorio local, simplemente indicando el path), pero también soporta otros protocolos como `ssh`, `http`, `https`...

Al contrario que con `git init`, con `git clone` no es necesario crear un directorio para el proyecto. Al clonar se creará un directorio con el nombre del proyecto dentro del que te encuentres al llamar a la orden.

Clonar un repositorio significa copiarlo completamente. No solo los archivos, sino todo su historial, cambios realizados, etc. Es decir que en tu repositorio local tendrás exactamente lo mismo que había en el repositorio remoto de donde lo has clonado.

Si has clonado el repositorio del ejemplo anterior (y si no, hazlo ahora), podemos ver un par de cosas interesantes. ¿Recuerdas las orden `git config --list`? Entra en el directorio del repositorio (para ello tendrás que hacer algo como `cd repo-ejemplo/`) y lista las opciones de configuración.

Verás, entre otras muchas, las user.name y user.email que ya conoces. Pero hay otra que es importante, y es `remote.origin.url`, que debe contener la dirección original del repositorio del que has clonado el tuyo.

Ahora mismo no nos sirve de mucho pero, cuando más adelante trabajemos en red con otros repositorios, nos va a venir bien recordarlo.

> *IMPORTANTE*  
> En adelante, a menos que se diga lo contrario, todos los comandos y órdenes que se indique se deberán ejecutar en el directorio de nuestro proyecto (o uno de sus subdirectorios, lógicamente). Git reconoce el proyecto con el que está trabajando en función del lugar donde te encuentres al ejecutar los comandos.

## ¿Cómo funciona git?

Antes de continuar, vamos a detenernos un momento para entender el funcionamiento de git.

Cuando trabajas con git, lo haces, evidentemente, en un directorio donde tienes tus archivos, los modificas, los borras, creas nuevos, etc.

Ese directorio es lo que llamamos "Directorio de trabajo", puede contener otros directorios y, de hecho es el que contiene el directorio .git del que hablábamos al principio.

Git sabe que tiene que controlar ese directorio, pero no lo hace hasta que se lo digas expresamente.

Más adelante veremos con algo más de detalle la orden `git add`, pero ya te adelanto que lo que hace es preparar los archivos que le indiques poniéndolos en una especie de lista virtual a la que llamamos el "Index". En Index ponemos los archivos que hemos ido modificando, pero las cosas que están en el "Index" aun no han sido archivadas por git.

Ojo, que algo esté en el index no significa que se borre de tu directorio de trabajo ni nada parecido, el Index es solo una lista de cosas que tendrás que actualizar en el repositorio porque han cambiado.

Por último, la instrucción `git commit`, que también veremos en breve, es la que realmente envía las cosas que hay en el Index al repositorio. Solo que en lugar de "repositorio" lo vamos a llamar "HEAD", porque el lugar exacto al que va puede significar cosas distintas en según que casos, como ya veremos cuando hablemos de ramas y esas cosas.

Lo sé, es todo un poco lioso ahora mismo, pero ya se irá aclarando conforme aprendamos más cosas.

Tú simplemente mantén esta secuencia en la cabeza: Directorio de trabajo -> Index -> HEAD


## Sincronizando repositorios

Como sistema de control de versiones distribuido, una de las principales utilidades de git es poder mantener distintos repositorios sincronizados (es decir, que contengan la misma información), exportando e importando cambios.

> Para importar (o exportar) cambios de un repositorio remoto se necesita, lógicamente, tener acceso de lectura a ese repositorio (en sentido estricto, ya hemos importado el estado de un repositorio cuando lo clonamos al hacer `git clone`). 

Para sincronizar con uno o más repositorios remotos, debemos saber qué repositorios remotos son esos. Para ello tenemos `remote`, que se usa así:

```
git remote
```
Y, seguramente, te retornará algo parecido a `origin`, lo que nos dice que el repositorio es el que le indicamos como "origen" al hacer el `clone` y, la verdad, no es mucha información.

Para obtener algo más útil, prueba a hacerlo con el parámetro `-v` de este modo:

```
git remote -v
```

lo que te retornará algo parecido a esto:

```
origin	https://github.com/oslugr/repo-ejemplo.git (fetch)
origin	https://github.com/oslugr/repo-ejemplo.git (push)
```

Esto te dice que hay un repositorio llamado "origin" que se usará tanto para recibir (fetch) como para enviar (push) los cambios. "origin" es el nombre del repositorio remoto por defecto, pero puedes tener muchos más y sincronizar con todos ellos.

Para añadir otro repositorio remoto se hace con la misma instrucción `remote` de este modo:

```
git remote add ALIAS_DEL_REPOSITORIO DIRECCION_DEL_REPOSITORIO
```

Donde `ALIAS_DEL_REPOSITORIO` es un nombre corto para usar en las
instrucciones de git (el equivalente al "origin" que hemos visto) y
DIRECCION_DEL_REPOSITORIO la dirección donde se encuentra. Por
ejemplo:

```
git remote add personal \
    git://github.com/psicobyte/repo-ejemplo.git
```

Esto añade un repositorio remoto llamado `personal` con la dirección que se indica.

Si ahora hacemos un `git remote -v`, veremos algo como:

```
personal	git://github.com/psicobyte/repo-ejemplo.git (fetch)
personal	git://github.com/psicobyte/repo-ejemplo.git (push)
origin	https://github.com/oslugr/repo-ejemplo.git (fetch)
origin	https://github.com/oslugr/repo-ejemplo.git (push)
```

Para eliminar un repositorio tienes:

```
git remote rm NOMBRE
```

Y para cambiarle el nombre:

```
git remote rename NOMBRE_ANTERIOR NOMBRE_ACTUAL
```

> Nota que git no comprueba si realmente existen los repositorios que
> agregas o si tienes permisos de lectura o escritura en ellos, de
> forma que el hecho de que estén ahí no significa que vayas a poder
> usarlos realmente. 

### Recibiendo cambios (git pull)

Ha llegado el momento de importar cambios desde un repositorio remoto. Para ello tenemos `git pull` que se usa así:

```
git pull REPOSITORIO_REMOTO RAMA
```

El `REPOSITORIO_REMOTO` es uno de los nombres de repositorio que hemos visto antes (si no pones ninguno, se supone "origin"). Sobre las ramas se hablará un poco más adelante, pero baste decir que, si no ponemos ninguna, se supone que es la rama "master").

De este modo, la forma más usual de llamar esta orden es, simplemente:

```
git pull
```

(que significaría lo mismo que `git pull origin master`).

Esta instrucción trae del repositorio remoto indicado (o de "origin" si no indicas nada, como hemos visto), todos los cambios que haya respecto al tuyo (lógicamente, no se molesta en traer los que son iguales).

Si el repositorio del que tratas de importar no existe o no tienes permiso de lectura, te dará un mensaje de error advirtiéndote de ello.

Si hay archivos que tú has modificado pero el otro repositorio no, te quedarás con los tuyos. Cuando se trate de archivos que tú no has cambiado pero que sí son distintos en el remoto, actualizarás los tuyos a este último. Pero, si importas archivos que se han modificado en ambos repositorios ¿qué pasa con las diferencias? ¿Sobrescribirá tus archivos? ¿Perderás los del otro repositorio?

Ahí es donde entra la solución de problemas, y lo veremos dentro de poco.

En realidad, `git pull` es la concatenación de dos acciones distintas, que
son `git fetch`, que trae los cambios remotos creando una nueva rama,
y `git merge`, que une esos cambios con los tuyos. En ocasiones te
convendrá más usarlas por separado pero, como aún no hemos visto el
manejo de las ramas, dejaremos esto por ahora.  

### Enviando cambios

Si con `pull` importamos cambios desde otro repositorio, la instrucción `push` es la que nos permite enviar cambios a un repositorio remoto.

Se usa de un modo bastante parecido:

```
git push REPOSITORIO_REMOTO RAMA
```

Igual que hemos visto con `git pull`, los valores por defecto son "origin" para el repositorio y "master" para la rama, con lo que se puede poner simplemente:

```
git push
```

lo que enviará nuestros cambios al servidor remoto... salvo que algo haya cambiado allí.

Si la versión que hay en el servidor es posterior a la última que sincronizamos (es decir, alguien más ha cambiado algo), git mostrará un error y no nos dejará hacer el push. Antes debemos hacer un pull.

Solo cuando hayamos hecho el pull (y resuelto los conflictos, si es que hubiera alguno), nos dejará hacer el push y enviar nuestra versión.

Al hacer tu push, git te retornará información de los cambios realizados, número de archivos, etc.

### Contraseñas

Naturalmente, como ya hemos comentado, no puedes hacer push a un repositorio en el que no tengas permiso de escritura. Para eso puede ser que sea un repositorio abierto a todo el que conozca la dirección, pero eso sería muy raro (e inseguro). Lo usual es que cuentes con un usuario y contraseña que te permitan acceder (normalmente por [ssh](https://es.wikipedia.org/wiki/Secure_Shell)) al servidor.

En otros repositorios (más raros), también necesitarás usuario y contraseña para acceder a la lectura y, por tanto, para hacer pull.

En ambos casos, git te solicitará el nombre de usuario y la contraseña cada vez que hagas push. No tiene por qué ser muy a menudo, pero puede ser un engorro.

En muchos sitios puedes ahorrarte ese trabajo usando pares de claves ssh. Básicamente consiste en que tu ordenador y el del repositorio se reconozcan entre ellos y no tengas que andar identificándote.

Las instrucciones para hacer esto en github están en [esta página de ayuda](https://help.github.com/articles/generating-ssh-keys#platform-all).

## Comportamiento por defecto de push

Las versiones anteriores de git tenían un comportamiento por defecto a la hora de hacer push llamado 'matching'.

Este consiste en que, al hacer push, se sincronizan todas las ramas del proyecto con sendas ramas en el servidor con el mismo nombre (ya hablaremos en detalle de las ramas más adelante). Si en el servidor no existe una rama con el nombre de alguna local, se crea automáticamente.

La versión 2 de git cambiará ese comportamiento, que pasará a ser `simple`, lo que significa que se sube solo la rama que tienes activa en este momento a la rama de la que has hecho el pull, pero te dará un error si el nombre de esa rama es distinto.

Mientras tanto, actualmente, git te avisa (a cada push) de que se va a hacer este cambio y te avisa de que puedes configurar este comportamiento por defecto con un mensaje [como este](https://git-scm.com/docs/git-config.html):

```
warning: push.default is unset; its implicit value is changing in
Git 2.0 from 'matching' to 'simple'. To squelch this message
and maintain the current behavior after the default changes, use:

git config --global push.default matching

To squelch this message and adopt the new behavior now, use:

git config --global push.default simple

[...]

```

Para elegir el comportamiento que prefieres solo tienes que usar, como ya hemos visto para otras configuraciones, el comando `git config` de este modo:

```
git config --global push.default OPCION
```

Por ejemplo:

```
git config --global push.default matching
```

usaría la opción `matching` en todos tus repositorios, pero:

```
git config --local push.default simple
```

usaría la opción `simple` solo en el repositorio en el que te encuentras. 

Otras opciones posibles son:

* `current`: Sube los cambios de la rama activa a una rama remota del mismo nombre. Si no existe esa rama remota, se crea. 

* `nothing`: Esta opción solo tiene sentido para test, debugs y esas cosas. Al hacer push no se subirá nada a ningún repositorio remoto.

* `upstream`: Al igual que `simple`, sube la rama que tienes activa a la rama de la que has hecho el pull pero, en este caso, *no* te dará error si el nombre de esa rama es distinto.

## El archivo .gitignore

Cuando hacemos `git add .` o algo parecido, preparamos todos los archivos que hayan sido modificados. Esto es, sin duda, mucho más cómodo que ir añadiendo los archivos uno a uno. Pero muy a menudo hay montones de archivos en tu directorio de trabajo que no quieres que se añadan nunca. Archivos de contraseñas, temporales, borradores, binarios compilados, archivos de configuración local...

> Por ejemplo, muchos editores de texto mantienen una copia temporal de los archivos que estás editando, con el mismo nombre pero terminado en el signo "~". Si haces `git add .`, estos archivos se acabarán añadiendo a tu repositorio, cosa que no tiene demasiada utilidad.

Para evitar este problema y facilitarte el trabajo, git nos permite crear un archivo (varios, en realidad, como veremos enseguida) donde describir qué archivos quieres ignorar.

El archivo en cuestión debe llamarse "*.gitignore*" (empezando por un punto) y ubicarse en el directorio raíz de tu proyecto.

En este archivo podemos incluir los nombres de archivos que queramos ignorar. Por ejemplo, imaginemos que nuestro *.gitignore* tiene este (poco útil) contenido:

```
## Los archivos que se llamen "passwords.txt" serán ignorados
passwords.txt
```

> Las líneas de *.gitignore* que comienzan con el signo "#" son comentarios (útiles para quien lo lea), y git las ignora.

Gracias a esto, git ignorará cualquier archivo que se llame passwords.txt, y no lo incluirá en tus adds.

Esto es demasiado simple y no nos va a ser muy útil, pero, afortunadamente, *.gitignore* permite comodines y otras herramientas útiles. Por ejemplo:


```
## Ignoramos todos los archivos que terminen en "~"
*~

## Ignoramos todos los archivos que terminen en ".temp"
*.temp

## Ignoramos todos los archivos que se llamen 
## "passwords.txt", "passwords.c", "passwords.csv"...
passwords.*

```

El archivo *.gitignore* permite hacer cosas mucho más complejas, aunque para la mayoría de los casos con algo como lo visto arriba es suficiente.

Pese a que cada repositorio puede tener su propio *.gitignore*, puede ser útil tener además un archivo general para todos los repositorios.

Git busca por defecto este archivo general en el directorio "*.config/git/ignore*" de tu directorio "Home", pero esto puede cambiarse con la siguiente orden:

```
git config --global core.excludesfile RUTA_AL_ARCHVO_IGNORE
```

Por ejemplo, para usar un archivo llamado "ignorar" en mi directorio personal, pondría algo así:

```
git config --global core.excludesfile ~/ignorar
```

> El símbolo "~" en un *path* o camino significa "El directorio Home del usuario".

Puedes encontrar muchos ejemplos de archivos *.gitignore* en
este [repositorio de GitHub](https://github.com/github/gitignore).

>Las opciones que se establecen con `git config`  para el repositorio local se almacenan permanentemente en el fichero `.git/config`. Por lo pronto no nos preocupemos de este fichero, pero todas las variables anteriores (y alguna más) se pueden poner directamente en este fichero.