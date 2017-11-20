#Readme.md

###Ejercicio 1 - Respuestas a las preguntas.

-
-


- ¿Qué comando utilizaste en el paso 11? ¿Por qué?

	- **11) Deshacer el último commit (perdiendo los cambios realizados en el working copy)**

```
<Command>
git reset --hard HEAD~1

```
####El porque:

Para deshacer el último commit y volver al commit anterior donde estaba el HEAD, es decir, el último commit echo en la rama styled.
>Con el flag **--hard** limpiamos el working area y se eliminan los cambios hechos en ese commit.

-
- ¿Qué comando o comandos utilizaste en el paso 12? ¿Por qué?

	- **12) Rehacer el último commit (el que acabamos de deshacer)**

```
git reflog -> command 1ª

```

```
git checkout 782f1d5 -> command 2ª

```

```
git checkout -b restore -> command 3ª

```

```
git checkout styled -> command 4ª

```

```
git merge restore -> command 5ª
```

```
git branch -d restore -> command 6ª

```

####El porque:
* 1- Para ver el id del commit ha restaurar o donde nos queremos posicionar y copiarlo. Para eso uso **reflog**
* 2 - Para mover el puntero sobre o hacia el commit en el cual deseo posicionarme para en este caso restablecer el último **reset --hard HEAD~1**
* 3 - Creo una rama nueva lamada **restore** en la misma posición donde esta ahora el **HEAD** ya que después de hacer el checkout me ha devuelto un **detached HEAD** informando que puedo tener en mi repo desfaces en cuanto a commit o punteros con respecto al HEAD del repo, es decir, me encuentro con un puntero que tiene **782f1d5** como identificador y no una rama o branch, es por eso que me informa que puedo crear una rama y una vez mergeada *(absorbida)*, con la rama *styled* puedo eliminar y así tener todos los cambios en una rama o puntero correcto.
* 4 - Me posiciono en la rama **styled** desde la cual quiero hacer el merge.
* 5 - Hago el merge hacia la rama donde estoy ahora, que es **styled**.
* 6 - Elimino la rama **restore** que ma ha servido de punto para solucionar el **detached HEAD** anterior.

> Después he hecho un **git status** para ver si todo era correcto y un **git log** para ver que el commit aparece. Todo ok !

-
- El merge del paso 13, ¿Causó algún conflicto? ¿Por qué?
	* **13) Hacer un merge con ‘master’ (styled absorbe a master)**

```
git merge master

```

####El porque:
El merge de la rama **master** por la rama **styled** no produjo ningún error o conflicto. Debido a que el puntero o **HEAD** donde estoy ahora esta o es ascentro del puntero o commit donde esta ahora mismo master, es decir, la rama **styled** tiene ya el último commit que tiene la rama **master** y no se produce ningún cambio.

-
- El merge del paso 19, ¿Causó algún conflicto? ¿Por qué?
	* **19) Hacer un merge de “htmlify” en “styled” (styled absorbe a htmlify)**

```
git checkout styled

```

```
git merge htmlify

```

####Causó algún conflicto:
Si, se dió un conflicto al hacer el merge desde la rama **styled** que absorbio la rama **htmlify** 
####Qué lo provoco:
Se produjo porque en ambas ramas existe un archivo con el mismo nombre **git-nuestro.md** y ambos archivos tienen lineas distintas y no concordantes el uno con el otro, es decir, la linea uno es distinta en ambos archivos *(esto se puede dar en n lineas del archivo)* y git no sabe como dejar, o corregir este diléma, así que deja en manos de nosotros que solucionemos este conflicto editando las lineas que dan el conflicto. 

Una vez resuelto el conflicto entonces debemos hacer un **add** seguido de un **commit**.


-
- El merge del paso 21, ¿Causó algún conflicto? ¿Por qué?
	* **21) Desde “master”, hacer un merge con “styled”**

```
git checkout master

```

```
git merge styled

```

####Causó algún conflicto:
No hubo conflicto. La salida fué la siguente:

```
Updating 20d5379..db1489f
Fast-forward
 git-nuestro.md | 19 +++++++++----------
 1 file changed, 9 insertions(+), 10 deletions(-)

```

Como se puede apreciar se hizo un fast-forward.

####Qué lo provoco:
El **Fast-forward** se produce cuando se hace un merge de una rama, en este caso de **master** que absorbe a la rama **styled**. Y en la rama que absorbe *(master)* no hay ningún commit desde el momento que se creo la rama hija en este caso *(styled)* por lo tanto lo único que se hace es añadir todos los commit de la rama *(styled)* dentro de la rama *(master)* y el **HEAD** pasa a ser el último commit de la rama que se absorbe, en este caso *(styled)*.

```
	master -> (no hay commit en esta rama desde que creamos la rama styled)
O---O
	|
	|		HEAD
	O---O---*O
	styled

---- >> git merge styled from master branch.

	master  HEAD here now, after of merge into 
O---O---O---*O
	|
	|		HEAD
	O---O---*O
	styled


```

-
- ¿Qué comando o comandos utilizaste en el paso 25?
	* **25) Dibujar el diagrama**

```
git log --graph --decorate --pretty=oneline

```

-
- El merge del paso 26, ¿Podría ser fast forward? ¿Por qué?
	* **26) Hacer un merge “no fast-forward” de “title” en “master” (master absorbe a title)**

```
git merge --no-ff title

```
####Podría haber sido un Fast-forward?:
Si.
####Por qué?:
Porque desde que se creo la rama **title** desde la rama **master** en la rama padre *(master)* no se ha hecho ningún commit, por lo tanto todos los commit hechos en la rama *(title)* se hubieran podido añadir a la linea de tiempo de la rama *master* con total certeza que no perjudica en nada el transcurrir de los commit en la linea de tiempo de dicha rama.

-
- ¿Qué comando o comandos utilizaste en el paso 27?
	* **27) Deshacer el merge (sin perder los cambios del working copy)**

```
git reset HEAD~1

```

-
- ¿Qué comando o comandos utilizaste en el paso 28? 
	* **28) Descartar los cambios**

>Para ver la diferencia entre mi working area y el HEAD

```
git diff HEAD

```

```
--- a/git-nuestro.md
+++ b/git-nuestro.md
@@ -1,4 +1,4 @@
-#Git nuestro
+#Git nuestro de cada día en los repor.

```

>Para descartar los cambios.

```
nano git-nuestro.md

```
>Añadir al HEAD de master.

```
git add git-nuestro.md

```

```
git commit -> open with nano edit.

```

-
- ¿Qué comando o comandos utilizaste en el paso 29?
	* **29) Eliminar la rama “title”**

```
git branch -D title

```

>Con el flag -D eliminamos la rama de forma fozosa y se pierden los datos.

-
- ¿Qué comando o comandos utilizaste en el paso 30?
	* **30) Rehacer el merge que hemos deshecho**

```
git reflog

```

```
git reset --hard 208b50a

```

```
git log

```

-
- ¿Qué comando o comandos usaste en el paso 32?
	* **32) Volver al commit inicial cuando se creó el poema**

```
git reflog

```

```
git reset --hard 20d5379

```

```
git log

```

-
- ¿Qué comando o comandos usaste en el punto 33?
	* **33) Volver al estado final, cuando pusimos título al poema**

```
git reflog

```

```
git reset --hard f7fa0f0

```

```
git log

```