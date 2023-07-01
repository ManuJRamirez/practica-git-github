1)  git init --initial-branch=main <br />

2)  notepad git-nuestro.md <br />

3)  git add git-nuestro.md <br />

4)  git commit -m "primera version git-nuestro"<br />

5)  git branch styled<br />

6)  git branch<br />

7)  git checkout styled<br />

8)  git branch<br />

9)  notepad git-nuestro.md<br />

10) git add git-nuestro.md<br />
    git commit -m "segunda version git-nuestro"<br />

**11) git reset --hard HEAD~1 -> He usado este comando para bajar HEAD a la anterior posición cuando no estaba
commit. Además lo he usado con --hard para perder los cambios en el working copy también**

**12) git reflog -> uso reflog para tener un listado de los movimientos y los ids <br />
    git reset --hard 4261f0a-> vuelvo a usar un reset --hard, para incluir las modificaciones tanto en graph(repositorio)
como en el working copy pero en esta ocación añado el id del commit que queremos recuperar<br />**

**13) git merge main -> no me sale ningún conflicto. Lo único es que me muestra "Already up to date" debido a que
después de crear la rama "styled" y no haber realizado ningún commit nuevo en la rama "main", podemos afirmar que "styled" 
tiene toda la información de la rama "main". Es por esto que si queremos que "styled" absorva algo de "main" nos dice que 
ya esta todo actualizado.<br />**

14) git checkout main<br />

15) git branch htmlify<br />

16) git checkout htmlify<br />

17) notepad git-nuestro.md<br />

18) git add git-nuestro.md<br />
    git commit -m "tercera version git-nuestro"<br />

**19) git checkout styled<br />
    git merge htmlify -> nos da un conflicto en git-nuestro.md debido a que los archivos tienen un contenido 
diferente en las mismas líneas y estamos haciendo un merge entre dos ramas paralelas, nos devuelve un conflicto. 
Nos avisa que debemos resolver esta incidencia antes de seguir. En este caso nos quedamos con el contenido de "styled".<br />**

20) notepad git-nuestro.md<br />
    git add git-nuestro.md -> (después de haber modificado el archivo y habernos quedado con la versión de la rama
"styled")<br />
    git commit -> guardar cambios en notepad<br />

**21) git checkout main<br />
    git merge styled -> nos hizo un merge fast-forward y no nos dió ningún conflicto, por el mismo motivo que en el punto "13)"
"main" sigue sin ser modificada con ningún commit desde que se creó la rama "styled", por lo tanto todo lo que hay en  "main", ya lo tiene
"styled", lo unico que hace "main" ahora es absorver los nuevos cambios que hay en "styled", es decir, el segundo commit que
hicimos.<br />**

22) git branch title<br />
    git checkout title<br />

23) notepad git-nuestro.md<br />
    git add git-nuestro.md<br />
    git commit -m "cuarta version git-nuestro con titulo"<br />

24) git checkout main<br />

**25) git log --graph<br />
    git log --graph --oneline (una u otra)<br />**

**26) git merge --no-ff title -> Si podría haber sido fast-forward por el mismo motivo que en el punto 13 y 21. La rama "main"
sigue sin cambios desde que se creó la rama "title", por lo que "title" tiene todo lo de "main". Al hacer el merge en el que "main"
absorve a "title", "main" se queda con todas las modificaciones realizadas en la rama "title" y no se produce ningún conflicto.<br />**

**27) git reset HEAD~1<br />**

**28) git restore git-nuestro.md<br />**

**29) git branch -D title<br />**

**30) git reflog <br />
    git reset --hard 81f6f38<br />**

31) git checkout main  <br />
    git branch -d htmlify<br />
    git branch -d styled<br />

**32) git reflog<br />
    git checkout 6e6f513 -> si sólo queremos mover HEAD<br />
    git reset --hard 6e6f513-> si queremos borrar todo hasta el primer commit<br />**

**33) git checkout main -> si sólo queremos mover HEAD<br />
    git reset --hard 81f6f38-> si hemos hecho un reset en el punto anterior<br />**

34) git reflog<br />
    git checkout 6e6f513<br />
    git tag inicial<br />
    git checkout main<br />
    git tag styled 4261f0a<br />
    git tag htmlify 15fad70<br />
    git tag title 81f6f38<br />
    
35) git checkout htmlify<br />


subir a github:<br />

git remote add practica-git-github https://github.com/ManuJRamirez/practica-git-github.git<br />
git push practica-git-github HEAD:refs/heads/main<br />
