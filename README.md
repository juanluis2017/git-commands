### git-commands-basics

``` git status ```


archivos que no deben ser almacenados en el control de carpeta

``` git ignore ```


trae los ultimos cambios del repositorio remoto

``` git pull ```

clona un repositorio remoto

``` git clone ```

sube los cambioss realizados a la rama remoto

```  git push ``` 

``` git fetch ``` 


lista todas las remotas

``` git branch -r ```

lista todas las ramas locales

``` git branch ```


crea una nueva rama y se posiciona en ella

``` git checkout -b ```


permite agregar nuevos archivos 

``` git add  'nombre-archivo'```

permite agregar todos los archivos

``` git add . ```

#### Git log

lista todos los commits generados por el usuario

``` git log -m --name-only --author=usurioGithub```

lista todos los commits generados por el usuario

```git log -Cantidad de commit a visualizar -git log -3 ultimos 3 commits ```



``` git clean -f   ```

#### git reset
------------------------------------------------------------------------
este comando es un poco más complicado. De hecho, hace un par de cosas diferentes dependiendo de cómo se invoca. 
Modifica el índice (el llamado "área de preparación"). O cambia a qué compromiso está apuntando actualmente un ramal. Este comando puede alterar el historial existente (al cambiar la confirmación a la que hace referencia una rama).


vuelve al commit anterior eliminado desde el commit -1 en adelante

``` git reset --hard HEAD~1 ```

vuelve al commit anterior eliminado desde el commit -1 en adelante

``` git reset --soft HEAD~1 ```

se elimina todo el historial hasta el punto que se realiza el rollback


``` git reset --hard 'hash commit especifico'  ```

vuelve un archivo desde staged a untraked
``` git reset HEAD 'nombre del archivo'  ```

otra opcion es


``` git checkout 'hash commit especifico' 
git checkout -b new branch
git push  
```

#### git revert

Este comando crea una nueva confirmación que deshace los cambios de una confirmación previa. 
Este comando agrega un nuevo historial al proyecto (no modifica el historial existente).


------------------------------------------------------------------------
genera un nuevo commit sin perder el historial


``` git reset --soft 'hash commit especifico ```

------------------------------------------------------------------------
Abort operations

``` git revert --abort ```

``` git merge --abort ```

``` git reset --abort ```





