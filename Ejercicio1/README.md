# Comandos

Comandos para gestionar cambios en nuestro repositorio.


## Cambios entorno
```
git reset nom_Archivo ->  quita ese archivo del stage (antes de hacer un commit)
    git reset --soft HEAD -> Regresa al ultimo commit realizado
    git reset --soft HEAD^ -> Regresa al antepenultimo commit realizado
    git reset --mixed IDCambio -> Regresa a un cambio dejando los cambios hecho hasta ahora
    git reset --hard IDCambio -> Regresa a un cambio borrando todo lo hecho
    git redlog -> muestra todos los registros hechos
        git reset --hard Id -> para volver

git status
    git status -s -> version corta

git commit -m "log_cambio"
    git commit -a -m "log_cambio" -> solo cuando se haya modificado el archivo ya existente, hace un add a la vez que un commit
    git commit --amend -m "mensaje" -> Edita el ultimo commit hecho

git push -> subir cambios al repositorio web

git pull  -> recibir cambios en el repositiorio

git log -> revisa el log de las subidas


git checkout -- example.html -> Revierte los cambios en un archivo

git diff example.html -> muestra la diferencia de lo que se modifico en un archivo

```

## Alias

```
git config --global alias.sinomino "comando a simplificar"
Examples:
git config --global alias.lg "log --oneline --decorate --all --graph"
git config --global alias.s "status -s -b"
git config --global -l -> muestra el log de las configuraciones
```

## Gestionar archivos

```
git mv archivo archivo_nuevo-> cambia y renombra un archivo
git rm archivo -> elimina un archivo
```
****
Notas git
=========

Notas tomadas leyendo el libro [Aprende Git: ... y, de camino, GitHub](http://amzn.to/2uOSCzX).

## Config

git --global color.ui true

## git add y git commit

- git add: prepara los archivos en una lista virtual que llamamos el index. Todavía no están archivados en git.

- git commit: envía las cosas que hay en index al HEAD.

Secuencia: Directorio de trabajo -> Index -> HEAD

Notas: 

- git add . -> añadirá el contenido del directorio en el que te encuentras incluyendo subdirectorios.
- git add *.txt  -> solo agregara todos los archivos que terminen en esa extension del DIRECTORIO actual
- git add "*.txt" -> agrega todos los archivos .txt de TODO el proyecto 
- git add folder/*.txt -> agrega todos los archivos .txt dentro de esa carpeta
- git add folder/ -> agrega todos los archivos dentro de esa carpeta  
- Si haces git add y luego modificas, en Index no tendrías estas últimas modificaciones. 
- git add -u: añadir al index los archivos que deben ser borrados.
- git add -A: suma de git add -u y git add .
- git add -a: git add -A y commit (aunque mejor hacer por separado add y commit).

## git remote

- git remote -v para ver los repositorios remotos.

- git remote add alias dirección

- git remote rm nombre

- git remote rename anterior actual

## git pull

- git pull: git fetch trae cambios remotos creando una nueva rama y git merge que une esos cambios con los tuyos.

## git log

- git log --oneline para ver la versión compacta.

- git log --graph dibuja árbol.

## git rm

- git rm fichero borra también el index.

- git rm --cached fichero o git reset HEAD fichero: borrar del index pero no del fichero de trabajo.
****
## Rehacer un commit

- git commit --amend: ej. reescribir un comentario si no hay cambios. También puedes añadir cambios al index antes de hacer el amend.

## Deshacer cambios en un archivo

- git checkout -- file: Recuperar versión del HEAD.

## Conflictos

Lo que hay entre HEAD y los iguales es lo que tienes en tu HEAD, a continuación hasta la cadena que indica el número de commit del conflicto lo de la rama remota. Resolver es quitar los menores, mayores e iguales y elegir el código con el que nos quedamos.

## Volver a un commit determinado

- git reset ---hard hash: vuelve al commit y trae al directorio de trabajo los ficheros tal como eran. Guardar cambios que tengas pendientes antes de hacerlo.

## Ver cambios de un commit

- git show hash

- git show hash:ruta_archivo > archivo_copia: tener una copia del archivo como era en ese commit.

## Nueva rama

- git checkout -b nueva-rama

- Es como git branch y git checkout.

## Guardar y recuperar copia

- git stash 

- git stash apply --index 

## Establecer origen

- git push --set-upstream origin rama: establece origen por defecto y asigna un nombre.

## git branch

- git branch para saber la rama en la que estamos.

- git branch -all: muestra todas.

## Borrar rama

- git branch -d rama

## Borrar rama remota

- git push origin : rama


## Travis

- Darse de alta en Travis CI con cuenta GitHub

- Activar hook en perfil travis

- Se añade el fichero .travis.yml en el repositorio

- Hacer push

- Repositorio ejemplo para pasar ortografía a los documentos con travis (con diccionario español): https://github.com/oslugr/repo-ejemplo/blob/master/.travis.yml.

## Otros recursos

- Guía Freecodecamp: https://guide.freecodecamp.org/git/.

- Comandos útiles csswizardry: https://csswizardry.com/2017/05/little-things-i-like-to-do-with-git/.

- Oh, shit, git!: http://ohshitgit.com/.

- Git Flight rules: https://github.com/k88hudson/git-flight-rules/.

- Git rebase: https://dev.to/maxwell_dev/the-git-rebase-introduction-i-wish-id-had.

- Curso git, GitHub, Markdown (Adolfo Sanz de Diego): https://github.com/asanzdiego/curso-git-github-markdown-2016.

- Learnyougit: https://github.com/Karumi/learnyougit.

- Convención commits Git (Angular): https://gist.github.com/stephenparish/9941e89d80e2bc58a153.

## Squash

http://gitready.com/advanced/2009/02/10/squashing-commits-with-rebase.html

Ejemplo combinar 4 commits en 1:

- git rebase -i HEAD~4

pick 01d1124 Adding license
squash 6340aaa Moving license into its own file
squash ebfd367 Jekyll has become self-aware.
squash 30e0ccb Changed the tagline in the binary, too.

- Arreglar conflictos si los hubiera
- git add . (si conflictos)
- git rebase —continue (si conflictos)
- git push origin <branchname> -f

## git workflow con rebase

- Sincronizar remoto con master
git checkout master
git pull

- Actualizar la feature branch con los últimos cambios de master
git checkout <branchname>
git rebase origin/master

- Si no hay conflictos saltar este paso. Si los hay, resolver y continuar el rebase
git add <file1> <file2> ...
git rebase —continue

- Push de la rama con force
git push origin <branchname> -f

- Hacer una pull request
****

[![Build Status](https://travis-ci.org/oslugr/curso-git.svg?branch=master)](https://travis-ci.org/oslugr/curso-git)

Repositorio con el material para el [libro *Aprende git*](http://amzn.to/2uOSCzX). Se escribió originalmente usando
[Markdown en su versión Kramdown](http://kramdown.gettalong.org/quickref.html),
aunque finalmente hemos encontrado que funciona mejor transformándolo
con [Pandoc](http://pandoc.org/).



## Más información

Este repositorio está acompañado de otro
[repositorio de ejemplo](https://github.com/oslugr/repo-ejemplo) sobre
el que se pone en práctica casi todo lo que se muestra en el libro y de una
[plantilla de repositorio](https://github.com/JJ/repo-plantilla) usada
sobre todo para los temas de fontanería; también contiene una serie de
ganchos (*hooks*) de ejemplo que puedes instalar fácilmente en tu repositorio de
forma alternativa a los que se instalan por omisión.

Como alternativa a este libro tienes
[el libro de Git: Pro Git](http://git-scm.com/book/es), que también te
puedes descargar en diferentes formatos. Como ayuda complementaria,
puedes descargarte
la
[chuleta de órdenes](https://elbauldelprogramador.com/mini-tutorial-y-chuleta-de-comandos-git/) de
El Baúl del Programador. 