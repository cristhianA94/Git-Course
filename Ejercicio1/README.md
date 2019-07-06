## Comandos

Comandos para gestionar cambios en nuestro repositorio.


    Cambios entorno
==============================================================
``
git add .
    git add *.txt  -> solo agregara todos los archivos que terminen en esa extension del DIRECTORIO actual
    git add "*.txt" -> agrega todos los archivos .txt de TODO el proyecto 
    git add folder/*.txt -> agrega todos los archivos .txt dentro de esa carpeta
    git add folder/ -> agrega todos los archivos dentro de esa carpeta

git reset nom_Archivo ->  quita ese archivo del stage (antes de hacer un commit)
    git reset --soft HEAD -> Regresa al ultimo commit realizado
    git reset --soft HEAD^ -> Regresa al antepenultimo commit realizado

git status
    git status -s -> version corta

git commit -m "log_cambio"
    git commit -a -m "log_cambio" -> solo cuando se haya modificado el archivo ya existente, hace un add a la vez que un commit

git push -> subir cambios al repositorio web

git pull  -> recibir cambios en el repositiorio

git log -> revisa el log de las subidas


git checkout -- example.html -> Revierte los cambios en un archivo

git diff example.html -> muestra la diferencia de lo que se modifico en un archivo


``

    Alias
====================================================================
```
git config --global alias.sinomino "comando a simplificar"
Examples:
git config --global alias.lg "log --oneline --decorate --all --graph"
git config --global alias.s "status -s -b"
git config --global -l -> muestra el log de las configuraciones
```
