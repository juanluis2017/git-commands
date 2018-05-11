### git-commands-basics

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




#### Git log

lista todos los commits generados por el usuario

``` git log -m --name-only --author=usurioGithub```

lista todos los commits generados por el usuario

```git log -Cantidad de commit a visualizar -git log -3 ultimos 3 commits ```


vuelve al commit anterior eliminado desde el commit -1 en adelante

``` git reset --hard HEAD~1 ```

vuelve al commit anterior eliminado desde el commit -1 en adelante

``` git reset --soft HEAD~1 ```

git clean -f

#### git reset
------------------------------------------------------------------------
se elimina todo el historial hasta el punto que se realiza el rollback

git reset --hard 'hash commit especifico' 

otra opcion es

git checkout 'hash commit especifico' 
git checkout -b new branch
git push
------------------------------------------------------------------------
genera un nuevo commit sin perder el historial

git reset --soft 'hash commit especifico' 

------------------------------------------------------------------------
Abort operations

``` git revert --abort ```

``` git merge --abort ```

``` git reset --abort ```





