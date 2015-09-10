- ¿Qué comando utilizaste en el paso 11? ¿Por qué?

  # Para deshacer el ultimo commit y con --hard restaura el working copy con lo que hay en el repositorio.
  git reset --hard HEAD~1


- ¿Qué comando o comandos utilizaste en el paso 12? ¿Por qué?

  # Primero localizar el hash del commit anterior con git reflog 
  git reflog 
  # restaurando el working copy con —-hard, moviendo la rama htmlify y el HEAD.
  git reset --hard <hash_commit_anterior>


- El merge del paso 13, ¿Causó algún conflicto? ¿Por qué?

  # No hay conflicto porque htlmlify (que es quien absorbe) ya tiene en su primer commit el mismo contenido 
  # de poem.md en la rama master que ahora estamos haciendo merge. La rama htmlify no pierde informacion, es 
  # decir sigue pudiendo ver todos los commit que veía antes del merge.
  git merge master


- El merge del paso 19, ¿Causó algún conflicto? ¿Por qué? 

  # Si que causo conflicto, ya que en este caso estamos tratando de juntar dos versiones diferentes de poem.md
  # con diferencias en las mismas lineas, que git no sabe cual elegir para no perder informacion en el merge.

 
- El merge del paso 21, ¿Causó algún conflicto? ¿Por qué? 

  # No hubo conflicto, ya que al igual que en el merge del paso 13, master absorbe todos los cambios de la 
  # de la rama htmlify. Ambas ramas partieron del mismo punto y ahora están a la par.
  # La rama master no pierde informacion, por el contrario asume todos los cambios de la rama htmlify.


- ¿Qué comando o comandos utilizaste en el paso 25?

  git log --graph --decorate --pretty=oneline


- El merge del paso 26, ¿Podría ser fast forward? ¿Por qué? 

  # Si que podría ser fast forward ya que la rama master no pierde informacion, es decir, puede seguir viendo los mismos
  # commit que veia antes del merge.

 
- ¿Qué comando o comandos utilizaste en el paso 27?

  git reset HEAD~1


- ¿Qué comando o comandos utilizaste en el paso 28? 

  git reset —-hard HEAD


- ¿Qué comando o comandos utilizaste en el paso 29? 

  # Desde la rama master
  git branch -D title


- ¿Qué comando o comandos utilizaste en el paso 30? 

  # Con git reflog se obtiene el ultimo commit de la rama title
  git reflog

  # Con git checkout nos posesionamos en el commit en donde se incluyo el titulo al poema.
  git checkout <hash_commit_title>

  # Con git branch title se vuelve a crear la rama title
  git branch title

  # Con git checkout master volvemos a la rama master y se obtiene con git reflog el commit del merge con title que queremos recuperar.
  git checkout master

  # Con git reset —-hard avanzamos la rama master y el HEAD hasta el commit del merge que realizamos anteriormente, actulizando
  # el working copy.
  git reset —-hard <hash_commit_merge>

  
- ¿Qué comando o comandos usaste en el paso 32?

  # Con git reset —-hard HEAD~3 podemos actualizar el working copy con el repositorio, pero entiendo que no es lo que se pide. 
  git reset HEAD~3


- ¿Qué comando o comandos usaste en el punto 33?

  # Con git reflog obtenemos el hash del commit ultimo de la rama master donde tenemos el poema con el titulo.
  git reflog

  # Movemos la rama master y el HEAD hasta el commit. 
  git reset <hash_commit_merge_title> 

  # He entendido que lo que se pide es moverse solo al estado final, es decir, al commit de la rama master en donde tenemos el
  # el poema con titulo. Si se quisiera rehacer todas las ramas habría que ir posicionándose git checkout en los commit últimos
  # de cada una de ellas y con git branch <nombre> volver a crear cada rama. 



  