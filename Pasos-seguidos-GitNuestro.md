# Practica uno GitNuestro

* 1) Crear un repositorio

```
git init

```* 2) Crear un archivo git-nuestro.md con el contenido:

```
nano git-nuestro.md

```
	Git nuestro
		Git nuestro que estas en los repos  
	Comprimidos sean tus commits 	Venga a nosotros tu log 	En el local como en el remote 	Danos hoy nuestro pull de cada día 	Perdona nuestros conflictos 	Como también perdonamos los de otros geeks  
	No nos dejes caer en detached HEAD	y líbranos de SVN 	git commit --amend

	* 3) Añadir git-nuestro.md al staging area

```
git add git-nuestro.md

```* 4) Mover lo que hay en el staging area al repositorio

```
git commit

```* 5) Crear una rama llamada “styled”

```
git branch styled

```* 6) Listar las ramas que hay en el repositorio

```
git branch

```* 7) Moverse a la rama “styled”

```
git checkout styled

```* 8) Comprobar que se está en la rama correcta

```
git branch

```* 9) Modificar en el archivo git-nuestro.md:

```	*Git* nuestro que estas en los repos
	Comprimidos sean tus *commits*
	Venga a nosotros tu *log*	En el local como en el *remote*
	Danos hoy nuestro *pull* de cada día
	Perdona nuestros *conflictos*	Como también perdonamos los de otros geeks
	No nos dejes caer en *detached HEAD*  y líbranos de *SVN*	`git commit --amend`
	
```* 10) Añadir los cambios al staging área y luego pasarlos al repositorio

```
git add git-nuestro.md

git commit

```* **11) Deshacer el último commit (perdiendo los cambios realizados en el working copy)**

```
<Command>
git reset --hard HEAD~1

```

* **12) Rehacer el último commit (el que acabamos de deshacer)**

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
* **13) Hacer un merge con ‘master’ (styled absorbe a master)**

```
git merge master

```
* 14) Volver a la rama master

```
git checkout master

```
* 15) Crear una nueva rama llamada “htmlify”

```
git branch htmlify

```

* 16) Cambiar a la rama htmlify

```
git checkout htmlify

```
* 17) Modificar en el archivo git-nuestro.md:

```
nano git-nuestro.md

```

```<p><em>Git</em> nuestro que estas en los repos<br /> 
Comprimidos sean tus <em>commits</em><br />  
Venga a nosotros tu <em>log</em><br /> En el local como en el <em>remote</em><br /> Danos hoy nuestro <em>pull</em> de cada día<br />  
Perdona nuestros <em>conflictos</em><br /> Como también perdonamos los de otros geeks<br /> No nos dejes caer en <em>detached HEAD</em><br />  
y líbranos de <em>SVN</em><br /> <code>git commit --amend</code></p>

```
* 18) Hacer un commit

```
git add git-nuestro.md

```

```
git commit -> open with nano edit.

```
* **19) Hacer un merge de “htmlify” en “styled” (styled absorbe a htmlify)**

```
git checkout styled

```

```
git merge htmlify

```
* 20) Si hay conflictos, deberemos resolverlos quedándonos con el contenido de la rama “styled”.

Una vez arreglado el conflicto, añadimos el archivo **git-nuestro.md** al *staging area* y después lo comiteamos.

```
git add git-nuestro.md

```

```
git commit -> open with nano.

```
* 21) Desde “master”, hacer un merge con “styled”

```
git checkout master

```

```
git merge styled

```
* 22) Crear una rama “title” y cambiarse a esa rama

```
git branch title

```

```
git checkout title

```
* 23) Añadir un título (a tu gusto) al archivo git-nuestro.md y hacer un commit.

```
nano git-nuestro.md

```

```
git add git-nuestro.md

```

```
git commit -> open with nano.

```

El título es:

#####Git nuestro de cada día en los repor.

* 24) Volver a la rama master

```
git checkout master

```

* 25) Dibujar el diagrama

```
git log --graph --decorate --pretty=oneline

```
* 26) Hacer un merge “no fast-forward” de “title” en “master” (master absorbe a title) 

```
git merge --no-ff title

```

* 27) Deshacer el merge (sin perder los cambios del working copy)

```
git reset HEAD~1

```
* 28) Descartar los cambios

```
git diff HEAD

```

```
nano git-nuestro.md

```

```
git add git-nuestro.md

```

```
git commit -> open with nano edit.

```
* 29) Eliminar la rama “title”

```
git branch -D title

```
* 30) Rehacer el merge que hemos deshecho

```
git reflog

```

```
git reset --hard 208b50a

```

```
git log

```
* 31) Volver a master y eliminar el resto de ramas

```
git checkout master

```
Eliminar ramas:

```
git branch -d htmlify

```

```
git branch -d styled

```

```
git branch

```
* 32) Volver al commit inicial cuando se creó el poema

```
git reflog

```

```
git reset --hard 20d5379

```

```
git log

```
* 33) Volver al estado final, cuando pusimos título al poema

```
git reflog

```

```
git reset --hard f7fa0f0

```

```
git log

```
* 34) Crear los siguientes tags: 

>inicial: en el primer commit

```
git reflog

```

```
git reset --hard 20d5379

```

```
git log

```

```
git log

```
>styled: modificación del paso 10

```
git reflog

```

```
git reset --hard 782f1d5

```

```
git tag styled

```

>htmlify: modificación del paso 17-18

```
git reflog

```

```
git reset --hard af091ea

```

```
git log

```

```
git tag htmlify

```

>title: modificación del paso 30

```
git reflog

```

```
git reset --hard f7fa0f0

```

```
git log

```

```
git tag title

```
* 35) Ir al tag htmlify

```
git checkout htmlify

```

```
git checkout -b htmlify-restore -> para no perder nada por el detached HEAD.

```

```
git checkout master

```

-
-
		END EJERCICIO 1