# Practica uno GitNuestro

* 1) Crear un repositorio

```
git init

```

```
nano git-nuestro.md

```
	Git nuestro
	
	Comprimidos sean tus commits 
	No nos dejes caer en detached HEAD

	

```
git add git-nuestro.md

```

```
git commit

```

```
git branch styled

```

```
git branch

```

```
git checkout styled

```

```
git branch

```

```
	Comprimidos sean tus *commits*
	Venga a nosotros tu *log*
	Danos hoy nuestro *pull* de cada día
	Perdona nuestros *conflictos*
	No nos dejes caer en *detached HEAD*  y líbranos de *SVN*
	
```

```
git add git-nuestro.md

git commit

```

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


```
git merge master

```


```
git checkout master

```


```
git branch htmlify

```

* 16) Cambiar a la rama htmlify

```
git checkout htmlify

```


```
nano git-nuestro.md

```

```
Comprimidos sean tus <em>commits</em><br />  
Venga a nosotros tu <em>log</em><br /> 
Perdona nuestros <em>conflictos</em><br /> 
y líbranos de <em>SVN</em><br /> 

```


```
git add git-nuestro.md

```

```
git commit -> open with nano edit.

```


```
git checkout styled

```

```
git merge htmlify

```


Una vez arreglado el conflicto, añadimos el archivo **git-nuestro.md** al *staging area* y después lo comiteamos.

```
git add git-nuestro.md

```

```
git commit -> open with nano.

```


```
git checkout master

```

```
git merge styled

```


```
git branch title

```

```
git checkout title

```


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


```
git merge --no-ff title

```

* 27) Deshacer el merge (sin perder los cambios del working copy)

```
git reset HEAD~1

```


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


```
git branch -D title

```


```
git reflog

```

```
git reset --hard 208b50a

```

```
git log

```


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
git reflog

```

```
git reset --hard f7fa0f0

```

```
git log

```


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