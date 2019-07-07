Curso para entender la forma de trabajo de GitHub
==================================================

Traducción de [Understanding the GitHub Workflow][flow_EN]. `2017.11.30`.

Traducción de [Hello World][hello_EN]. `2016.04.07`.

[hello_EN]: https://guides.github.com/activities/hello-world/
[flow_EN]: http://guides.github.com/overviews/flow/

  - [¿Qué es GitHub?](#¿qué-es-github?)
  - [Flujo trabajo GitHub](#Flujo-de-trabajo-en-GitHub)
    - [Crear una rama](#crear-una-rama)
    - [Agregar commits](#agregar-commits)
    - [Abrir un Pull Request](#abrir-un-pull-request)
    - [Discutir y revisar tu código](#discutir-y-revisar-tu-código)
    - [Desplegar](#desplegar)
    - [Fusionar e implementar](#fusionar-e-implementar)
  - [Comandos Básicos](uso_basico.md)
****

# ¿Qué es GitHub? #

GitHub es una plataforma de alojamiento de código para el control de versiones y la colaboración. Te permite a ti y a otros trabajar juntos en proyectos desde cualquier lugar.

Este tutorial te enseña lo esencial de GitHub como repositorios , sucursales , confirmaciones y solicitudes de extracción . Creará su propio repositorio Hello World y aprenderá el flujo de trabajo de Solicitud de extracción de GitHub, una forma popular de crear y revisar el código.



# Flujo de trabajo en GitHub #

## Introducción ##

La forma de trabajo de GitHub es ligera, su forma de trabajo basado-en-ramas soporta equipos y proyectos donde las asignaciones se realizan regularmente. Esta guía explica como funciona la forma de trabajo de GitHub.



## Crear una rama ##

![1](https://user-images.githubusercontent.com/24251638/60773603-7567fd80-a0cd-11e9-9afa-f288b2cee8be.jpg)

Cuando trabajas en un proyecto, vas a tener en cualquier momento un montón de características o ideas diferentes en el proceso – algunas de ellas en las que ya estás listo para hacer o implementar, y otros en los que no. Hacer ramificaciones existe para ayudarte a manejar este flujo de trabajo.

#### Tip Pro ####

Ramificaciones en un concepto del núcleo de Git, y el Flujo de GitHub está basado siguiendo esto. Sólo hay una regla: cualquier cambio en la rama de `master` siempre es implementado.

Debido a ésto, es extremadamente importante que tu nueva rama sea creada fuera de _master_ cuando trabajas en una función o en hacer una corrección. El nombre de tu rama debe ser descriptiva (ejem., `refactorizar-autorización`, `cache-contenido-usuario`, `hacer-retina-avatars`), así otros pueden ver en lo que estás trabajando.
****
## Agregar _commits_ ##

![2](https://user-images.githubusercontent.com/24251638/60773607-8153bf80-a0cd-11e9-84b0-9e6b010ade85.jpg)

Una vez que tu rama ha sido creada, es tiempo de comenzar a hacer cambios. Cuando agregas, editas o borras un archivo, estás haciendo un _commit_, y agregando eso a tu rama. Este proceso de agregar _commits_ mantiene un registro de tu progreso mientras trabajas en una función de la rama.

Los _commits_ también crean un historial de manera transparente de tu trabajo que otros pueden seguir para entender que has terminado y por qué. Cada _commit_ tiene asociado un mensaje, que es una descripción explicando por qué un cambio en particular fue hecho. Además, cada _commit_ es considerado una unidad separada de cambio. Esto te permite deshacer cambios, si un _bug_ (error) fue encontrado, o si decides ir en una dirección diferente.

#### Tip Pro ####

Los mensajes de _commit_ son importantes, especialmente desde los seguimientos de Git de los cambios, ya que después los despliega dentro de los _commits_ una vez que ellos son enviados al servidor. Escribiendo mensajes de _commit_ claros, puedes hacer fácil para otras personas seguirte a lo largo y proveer retroalimentación.
****

## Abrir un _Pull Request_ ##

![3](https://user-images.githubusercontent.com/24251638/60773608-83b61980-a0cd-11e9-94a4-741b54e8c13d.jpg)

Un _Pull Request_ inicia una discusión acera de tus _commits_. Debido que ellos están estrechamente integrados con el repositorio Git, cualquiera puede ver exactamente que cambios se funcionarían si ellos aceptan tu petición.

Puedes abrir un _Pull Request_ en cualquier punto durante el proceso de desarrollo: cuando tienes un poco o no tanto de código para compartir o alguna idea en general, cuando estás atascado y necesitas ayuda o un consejo, o cuando estás listo para que alguien revise tu trabajo. Utilizando el sistema de @menciones de GitHub en tus mensajes de _Pull Request_, puedes pedir la atención de personas o equipos específicos, ya sea que estén en la oficina de a lado o a diez husos horarios de distancia.

#### Tip Pro ####

Los _Pull Request_ son útiles para contribuir a proyectos de código abierto y para administrar cambios en los repositorios compartidos. Si estás utilizando un Modelo _Fork & Pull_, los _Pull Requests_ te darán una forma de notificar a los encargados del proyecto acerca de los cambios que desean que se consideren. Si estás utilizando el Modelo Repositorio Compartido, los _Pull Requests_ te ayudan a comenzar revisiones de código y conversaciones acerca de proporciones de cambios antes que ellos lo funcionen dentro de la rama _master_.
****

## Discutir y revisar tu código ##

![4](https://user-images.githubusercontent.com/24251638/60773609-857fdd00-a0cd-11e9-951c-49d1d49caac1.jpg)

Una vez que un _Pull Request_ ha sido abierto, la persona o el equipo que reviso tus cambios quizás tengan preguntas o comentarios. Tal vez el estilo de programación no coincide con las directrices del proyecto, el cambio no acepta los _unit testes_, o quizá todo se ve genial y está en orden. Los _Pull Requests_ están diseñados para alentar y capturar este tipo de conversaciones.

Puedes seguir enviando tus cambios a la rama en plena discusión o mientras comentan acerca de tus _commits_. Si alguien comenta que olvidaste hacer algo o que hay un _bug_ en tu código, puedes arreglarlo en tu rama y enviar el cambio. GitHub mostrará tus nuevos _commits_ y cualquier comentario adicional que quizás recibas en la vista unificada de _Pull Request_.

#### Tip Pro ####

Los comentarios _Pull Request_ están escritos en Markdown, así que puedes incluir imágenes y _emoji_, utilizar bloques de texto con formato, y formateo ligero.
****

## Desplegar ##

![5](https://user-images.githubusercontent.com/24251638/60773610-8749a080-a0cd-11e9-9794-248d0bf22711.jpg)
Con GitHub, puede desplegar desde una rama para pruebas finales en producción antes de fusionarse con el maestro.

Una vez que se haya revisado su solicitud de extracción y la rama pase sus pruebas, puede implementar sus cambios para verificarlos en producción. Si su sucursal causa problemas, puede revertirla implementando el maestro existente en producción.


## Fusionar e implementar ##

![6](https://user-images.githubusercontent.com/24251638/60773611-89136400-a0cd-11e9-9d1e-5c0d7656edcf.jpg)

Una vez que tu _Pull Request_ ha sido revisado y la rama paso tus pruebas, es tiempo de funcionar tu código con la rama _master_ para su implementación. Si quieres probar cosas antes de fusionarlo en el repositorio de GitHub, puedes realizar la fusión locamente primero. Esto es algo útil si no tienes acceso para enviar los cambios al repositorio.

Una vez funcionado, los _Pull Requests_ mantiene un registro del historial de cambios de tu código. Debido a esto puedes buscar, regresar a cualquier punto atrás en el tiempo para entender por qué y cómo una decisión fue tomada.

#### Tip Pro ####

Incorporando ciertas claves dentro de tu texto en tus _Pull Request_, puedes asociar _issues_ con tu código. Cuando tu _Pull Request_ es fucionado, el _issue_ relacionado es cerrado. Por ejemplo, ingresando la frase `Closes #32` debería cerrar el _issue_ número 32 en el repositorio. Para más información, da un vistazo a nuestro [articulo de ayuda][ayuda].

[ayuda]: https://help.github.com/articles/closing-issues-via-commit-messages

