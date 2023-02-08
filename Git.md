# Comandos Git

## Visualizar configuración actual

**Comando**.

`git config --list`

**Resultado:**

    diff.astextplain.textconv=astextplain
    filter.lfs.clean=git-lfs clean -- %f
    filter.lfs.smudge=git-lfs smudge -- %f
    filter.lfs.process=git-lfs filter-process
    filter.lfs.required=true
    http.sslbackend=openssl
    http.sslcainfo=C:/Program Files/Git/mingw64/ssl/certs/ca-bundle.crt
    core.autocrlf=true
    core.fscache=true
    core.symlinks=false
    pull.rebase=false
    credential.helper=manager-core
    credential.https://dev.azure.com.usehttppath=true
    init.defaultbranch=master
    filter.lfs.required=true
    filter.lfs.clean=git-lfs clean -- %f
    filter.lfs.smudge=git-lfs smudge -- %f
    filter.lfs.process=git-lfs filter-process
    core.repositoryformatversion=0
    core.filemode=false
    core.bare=false
    core.logallrefupdates=true
    core.symlinks=false
    core.ignorecase=true

## Visualizar ruta de configuración

**Comando**.

`git config --list --show-origin`

**Resultado:**

    file:C:/Program Files/Git/etc/gitconfig diff.astextplain.textconv=astextplain
    file:C:/Program Files/Git/etc/gitconfig filter.lfs.clean=git-lfs clean -- %f
    file:C:/Program Files/Git/etc/gitconfig filter.lfs.smudge=git-lfs smudge -- %f
    file:C:/Program Files/Git/etc/gitconfig filter.lfs.process=git-lfs  filter-process
    file:C:/Program Files/Git/etc/gitconfig filter.lfs.required=true
    file:C:/Program Files/Git/etc/gitconfig http.sslbackend=openssl
    file:C:/Program Files/Git/etc/gitconfig http.sslcainfo=C:/Program Files/Git/    mingw64/ssl/certs/ca-bundle.crt
    file:C:/Program Files/Git/etc/gitconfig core.autocrlf=true
    file:C:/Program Files/Git/etc/gitconfig core.fscache=true
    file:C:/Program Files/Git/etc/gitconfig core.symlinks=false
    file:C:/Program Files/Git/etc/gitconfig pull.rebase=false
    file:C:/Program Files/Git/etc/gitconfig credential.helper=manager-core
    file:C:/Program Files/Git/etc/gitconfig credential.https://dev.azure.com.   usehttppath=true
    file:C:/Program Files/Git/etc/gitconfig init.defaultbranch=master
    file:C:/Users/{usuario}/.gitconfig filter.lfs.required=true
    file:C:/Users/{usuario}/.gitconfig filter.lfs.clean=git-lfs clean -- %f
    file:C:/Users/{usuario}/.gitconfig filter.lfs.smudge=git-lfs smudge -- %f
    file:C:/Users/{usuario}/.gitconfig filter.lfs.process=git-lfs  filter-process
    file:.git/config        core.repositoryformatversion=0
    file:.git/config        core.filemode=false
    file:.git/config        core.bare=false
    file:.git/config        core.logallrefupdates=true
    file:.git/config        core.symlinks=false
    file:.git/config        core.ignorecase=true

## Agregar usuario y correo

**Comando**.

Configurar usuario y correo para identificar quien realiza los cambios

Usuario:

`git config --global user.name "{Nombre del usuario}"`

Correo electrónico:

`git config --global user.email "{Correo del usuario}"`

**Resultado:**

Al correr de nuevo el comando `git config --list`, se visualiza el usuario y correo.

    diff.astextplain.textconv=astextplain
    filter.lfs.clean=git-lfs clean -- %f
    filter.lfs.smudge=git-lfs smudge -- %f
    filter.lfs.process=git-lfs filter-process
    filter.lfs.required=true
    http.sslbackend=openssl
    http.sslcainfo=C:/Program Files/Git/mingw64/ssl/certs/ca-bundle.crt
    core.autocrlf=true
    core.fscache=true
    core.symlinks=false
    pull.rebase=false
    credential.helper=manager-core
    credential.https://dev.azure.com.usehttppath=true
    init.defaultbranch=master
    user.name=Miguel Angel
    user.email=miguel@gmail.com
    filter.lfs.required=true
    filter.lfs.clean=git-lfs clean -- %f
    filter.lfs.smudge=git-lfs smudge -- %f
    filter.lfs.process=git-lfs filter-process
    core.repositoryformatversion=0
    core.filemode=false
    core.bare=false
    core.logallrefupdates=true
    core.symlinks=false
    core.ignorecase=true

## Crear repositorio local

Para correr el comando `git init` nos debemos ubicar en la carpeta donde se almacenara todos los archivos del proyecto.

**Comando**.

`git init`

**Resultado:**

    Initialized empty Git repository in C:{Ruta de la carpeta}

## Visualizar estado actual del repositorio

**Comando**.

Ver estado actual del proyecto y no se realiza ningún cambio si no se añade el o los archivos.

`git status`

**Resultado:**

    On branch master

    No commits yet

        Untracked files:
        (use "git add <file>..." to include in what will be committed)
                README.md
                historia.txt

    nothing added to commit but untracked files present (use "git add" to track)

## Agregar archivos

**Comando**.

Añade todos los documentos de la ruta actual.

`git add .`

Añade un documento especifico.

`git add historia.txt`

**Resultado:**

Al correr el comando `git status` se visualiza que se han añadido archivos para enviar al repositorio.

    On branch master

    No commits yet

    Changes to be committed:
    (use "git rm --cached <file>..." to unstage)
            new file:   README.md
            new file:   historia.txt

## Devolver un archivo

**Comando**.

Al correr el siguiente comando se devuelve un archivo el comando `--cached` es para quitar el archivo en memoria RAM.

`git rm --cached {archivo}`

Ejemplo

`git rm --cached historia.txt`

Al correr el siguiente comando se devuelve el archivo.

`git rm {archivo}`

Ejemplo

`git rm historia.txt`

**Resultado:**

    $  git rm --cached historia.txt
    rm 'historia.txt'

Al correr el comando `git status` se visualiza que un archivo esta listo para proteger y el otro no se añadido.

    On branch master

    No commits yet

    Changes to be committed:
    (use "git rm --cached <file>..." to unstage)
            new file:   README.md

    Untracked files:
    (use "git add <file>..." to include in what will be committed)
            historia.txt

## Enviar cambios al repositorio

**Comando**.

Al correr el comando se enviara al repositorio, el comando `-m` es para agregar un comentario.

`git commit -m 'Primer commit'`

**Resultado:**

    [master (root-commit) 07e0ccf] Primer commit
    2 files changed, 233 insertions(+)
    create mode 100644 README.md
    create mode 100644 historia.txt

## Visualizar historia de un archivo

**Comando**.

`git log {archivo}`

**Resultado:**

*Rama actual y versión más reciente:* (HEAD -> master)

*Hash del commit (Identificador unico por commit):* 637bc508fc645bf979dcfb7049d89b16ce14fbca

*Autor:* Author: Miguel Angel Barahona <miguel@gmail.com>

    commit 637bc508fc645bf979dcfb7049d89b16ce14fbca (HEAD -> master)
    Author: Miguel Angel <miguel@gmail.com>
    Date:   Wed Jan 25 20:40:38 2023 -0500

        Modificación archivo historia y se añade comandos al README.md

    commit 07e0ccf4646907899c0d9e028bd34d2ef9285d0d
    Author: Miguel Angel <miguel@gmail.com>
    Date:   Wed Jan 25 20:37:40 2023 -0500

        Primer commit

## Visualizar cambios del archivo por dentro

**Comando**.

`git show {archivo}`

**Resultado:**

*tomar la versión anterior con la actual:* diff --git a/historia.txt b/historia.txt

*Indicador entre la base de datos de git:* index e69de29..8a22836 100644

*Versión actuales*:

--- a/historia.txt

+++ b/historia.txt

*Indicador de cuantos bytes cambiaron:* @@ -0,0 +1,5 @@

*Cambios realizados entre las dos versiones:*

> +Esta es la historio de Miguel
> +
> +Miguel tiene 27 años y nació en Colombia
> +
> +Hoy hablaremos de su historia.

    commit 637bc508fc645bf979dcfb7049d89b16ce14fbca (HEAD -> master)
    Author: Miguel Angel <miguel@gmail.com>
    Date:   Wed Jan 25 20:40:38 2023 -0500

        Modificación archivo historia y se añade comandos al README.md

    diff --git a/historia.txt b/historia.txt
    index e69de29..8a22836 100644
    --- a/historia.txt
    +++ b/historia.txt
    @@ -0,0 +1,5 @@
    +Esta es la historio de Miguel
    +
    +Miguel tiene 27 años y nació en Colombia
    +
    +Hoy hablaremos de su historia.
    \ No newline at end of file

## Agregar commit sin el comando -m

**Comando**.

`git commit`

**Resultado:**

Se visualiza un editor de comandos llamado *VIM*.

Se agrega el comentario.

![Ejemplo agregando un comentario con VIM](https://github.com/miguel0920/Curso-Git-Y-GitHub/raw/main/Assets/Images/VIM%20-%20Agregar%20comentario.png)

*Para salir de la terminal VIM es:*

    Paso 1: ESC
    Paso 2: SHIFT + Z + Z
    
    Se envia los cambios.

Resultado al salir:

    $ git commit
    [master fc71632] Agregamos un cambio en su personalidad.
    2 files changed, 77 insertions(+), 3 deletions(-)

## Ver la diferencia entre commit de un archivo

**Comando**.

`git diff {hash antiguo} {hash más reciente}`

**Ejemplo**.

Correr el comando `git log {archivo}` para visualizar el id de cada commit

`git diff 637bc508fc645bf979dcfb7049d89b16ce14fbca fc71632a0f9b3fa110151165cdd7c59caf596cbb`

## Volver a un versión anterior (--hard)

**Comando**.

Devolver a un versión anterior, tener cuidado con este comando porque al correr el comando se borrar todo lo realizado desde el hash seleccionado hasta el más reciente y el hash al que se queria devolver queda como el más reciente.

`git reset {versión anterior} --hard`

**Resultado:**

    HEAD is not at fc7163 Agregamos un cambio en su personalidad.

## Visualizar el cambio de archivos

**Comando**.

`git log --stat`

**Resultado:**

README.md    | 76 ++++++++++++ (Tamaño en bytes -> 76)

historia.txt |  4 +++-  (Tamaño en bytes -> 4)

    $ git log --stat
    commit 284fd82c6f17afdc63e66f484026c516d3dc6d52 (HEAD -> master)
    Author: Miguel Angel <miguel@gmail.com>
    Date:   Fri Jan 27 20:42:35 2023 -0500

        Pagina y estilos Blog post

    Assets/css/styles.css |  5 +++++
    README.md             | 12 ++++++++++++
    blogpost.html         | 18 ++++++++++++++++++
    3 files changed, 35 insertions(+)

    commit f5915174f6f14985e4500ec248034a351533c7a2
    Author: Miguel Angel <miguel@gmail.com>
    Date:   Wed Jan 25 21:51:45 2023 -0500

        Se modifica README y a se agrega Imagen

    Assets/Images/VIM - Agregar comentario.png | Bin 0 -> 24942 bytes
    README.md                                  |  39 +++++++++++++++++++++++++++++
    2 files changed, 39 insertions(+)

    commit fc71632a0f9b3fa110151165cdd7c59caf596cbb
    Author: Miguel Angel <miguel@gmail.com>
    Date:   Wed Jan 25 20:56:55 2023 -0500

        Agregamos un cambio en su personalidad.

    README.md    | 76 ++++++++++++++++++++++++++++++++++++++++++++++++++++++++++--
    historia.txt |  4 +++-
    2 files changed, 77 insertions(+), 3 deletions(-)

    commit 637bc508fc645bf979dcfb7049d89b16ce14fbca
    Author: Miguel Angel <miguel@gmail.com>
    Date:   Wed Jan 25 20:40:38 2023 -0500

        Modificación archivo historia y se añade comandos al README.md

    README.md    | 134 +++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
    historia.txt |   5 +++
    2 files changed, 139 insertions(+)

    commit 07e0ccf4646907899c0d9e028bd34d2ef9285d0d
    Author: Miguel Angel <miguel@gmail.com>
    Date:   Wed Jan 25 20:37:40 2023 -0500

        Primer commit

    README.md    | 233 +++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
    historia.txt |   0
    2 files changed, 233 insertions(+)

## Devolverse un archivo a una versión anterior

**Comando**.

`git checkout {hash} 'archivo'`

**Ejemplo**.

Devolverse a una versión anterior del archivo.

`git checkout fc71632a0f9b3fa110151165cdd7c59caf596cbb historia.txt`

Devolverse a la versión actual del archivo.

`git checkout master historia.txt`

**Resultado:**

    $ git checkout 637bc508fc645bf979dcfb7049d89b16ce14fbca historia.txt
    Updated 1 path from 28033b8

## Enviar cambios al repositorio local

**Comando**.

Enviar archivos al *Stage* y enviar al *repositorio local*. Solo sirve para los archivos que estan modificados, los nuevos que se crean se debe manejar con `git add .` o `git add {file.txt}`.

`git commit -am '{Mensaje}'`

**Ejemplo**.

`git commit -am 'Primer commit'`

**Resultado:**

    $ git commit -am 'Cambiar el HTML y agregar estilos'
    [master aa27bee] Cambiar el HTML y agregar estilos
    3 files changed, 42 insertions(+), 4 deletions(-)

## Crear una rama

**Comando**.

Crear una rama desde la rama donde me encuentro

`git branch {nombre de la rama}`

**Ejemplo**.

`git branch cabecera`

## Moverse a una rama

**Comando**.

`git checkout {nombre de la rama}`

**Ejemplo**.

`git checkout cabecera`

## Listar ramas

**Comando**.

`git branch`

**Resultado:**

El * indica la rama actual donde se encuentra.

    git branch
    * cabecera
    master

## Merge Entre ramas

**Comando**.

`git merge {rama a fusionar}`

**Ejemplo**.

Se encuentra en la rama *master* y deseamos fusionar lo que contiene la rama *cabecera*, corremos el siguiente comando.

`git merge cabecera`

**Resultado:**

Se nos visualizara el editor de comando VIM y despues de colocar el comentario correspondiente se nos visualizara que fue correcto el merge.

Nos pide un colocar un mensaje porque cuando se ejecuta el comando *merge* es como ejecutar un **commit**.

    git merge cabecera
    Auto-merging blogpost.html
    Merge made by the 'recursive' strategy.
    Assets/css/styles.css | 34 +++++++++++++++++++++++++++-------
    README.md             | 37 ++++++++++++++++++++++++++++++++++++-
    blogpost.html         |  6 ++++++
    3 files changed, 69 insertions(+), 8 deletions(-)

## Resolviendo conflictos realizando Merge Entre ramas

**Comando**.

`git merge {rama a fusionar}`

**Ejemplo**.

Modificar en las dos ramas y realizar *commit* a un texto o un estilo en la misma ubicación.

**Rama Cabecera:**

![Ejemplo cambiando color de la fuente en Cabecera](https://github.com/miguel0920/Curso-Git-Y-GitHub/raw/main/Assets/Images/CambiarEstilo_ConflictoMerge_Cabecera.png)

Realizamos commit.

**Rama Master:**

![Ejemplo cambiando color de la fuente en Master](https://github.com/miguel0920/Curso-Git-Y-GitHub/raw/main/Assets/Images/CambiarEstilo_ConflictoMerge_Master.png)

Realizamos commit.

Solicitamos merge desde ***cabecera*** a ***master***

Al solicitarlo se nos visualizar el siguiente mensaje. Donde nos dice en que archivo se encuentra el conflicto.

    $ git merge cabecera
    Auto-merging Assets/css/styles.css
    CONFLICT (content): Merge conflict in Assets/css/styles.css
    Automatic merge failed; fix conflicts and then commit the result.

Al ver el codigo en el visual studio sale el siguiente mensaje

![Ejemplo de conflicto realizando un merge](https://github.com/miguel0920/Curso-Git-Y-GitHub/raw/main/Assets/Images/Ejemplo%20de%20conflicto.png)

**Accept Current Change:** Aceptar cambios de la rama Actual, en este ejemplo es master.

**Accept Incoming Change:** Aceptar cambios de la rama que deseamos fusionar, en este ejemplo cabecera.

**Accept Both Changes:** Aceptar ambos cambios.

**Compare Changes:** Comparar los cambios.

**Resultado:**

Una vez resuelto los cambios se realiza commit y queda todo resuelto.

## Visualizar toda la historia del proyecto

**Comando**.

`git log --all --graph --decorate --oneline`

**Resultado:**

![Visualización grafica de la historia del repositorio](https://github.com/miguel0920/Curso-Git-Y-GitHub/raw/main/Assets/Images/Historial_Repositorio.png)

## Crear Tag

**Comando**.

`git tag -a v0.1 -m "{mensaje}" {hash donde se agrega el tag}`

**Ejemplo**.

`git tag -a v0.1 -m "Resultado de las primeras clases del curso" 284fd82`

**Resultado:**

Correr el comando `git tag` y se nos visualizara los tags que estan creados.

## Visualizar Tags detallados

**Comando**.

`git show-ref --tags`

**Resultado:**

    git show-ref --tags
    3e7bc1018e2bffe6c18b0f0d116ff99fbc14a8cc refs/tags/v0.1

## Herramienta de Git para visualizar historial del proyecto

**Comando**.

`gitk`

**Resultado:**

    ![Herramienta grafica de Git](https://github.com/miguel0920/Curso-Git-Y-GitHub/raw/main/Assets/Images/Programa_gitk.png)

## Crear nueva fuente de datos

**Comando**.

`git remote add <nombre_del_remoto> <url_del_remoto>`

**Ejemplo**.

`git remote add upstream https://github.com/freddier/hyperblog`

**Resultado:**

Al correr el siguiente comando visualizamos la nueva fuente de datos `git remote -v`

## Crear un stash

El stashed nos sirve para guardar cambios para después, Es una lista de estados que nos guarda algunos cambios que hicimos en Staging para poder cambiar de rama o branch sin perder el trabajo que todavía no guardamos en un commit.

**Comando**.

Modificamos algo sobre cualquier archivo y corremos el siguiente comando.

`git stash`

**Resultado:**

    Saved working directory and index state WIP on master: 62d3c2e Exp 2

De hay podemos cambiar de rama.

## Listar los stash

**Comando**.

`git stash list`

**Resultado:**

    stash@{0}: WIP on master: 62d3c2e Exp 2

## Obtener el stash donde guarde los cambios de forma temporal

**Comando**.

`git stash pop`

**Resultado:**

Devuelve los cambios que se guardaron de forma temporal.

## Llevar el stash a una nueva rama

**Comando**.

`git stash branch <nombre_de_la_rama>`

**Resultado:**

Se va hacia la nueva rama y se tiene todos los cambios realizados, al correr el comando `git branch` se lista la ramas y la nueva creada.

## Eliminar el stash

**Comando**.

`git stash drop`

**Resultado:**

    Dropped refs/stash@{0} (15da5d56a876bc213244213)

## Listar archivos que quiero quitar de la solución

**Comando**.

Solo se listara los archivos que no omita ***.gitignore***

`git clean --dry-run`

**Resultado:**

Ejemplo:

    Would remove <nombre_del_archivo>.txt

## Eliminar archivos

**Comando**.

`git clean -f`

**Resultado:**

Ejemplo:

    Removing <nombre_del_archivo>.txt

## Obtener un commit de otra rama (mala práctica)

Git Cherry-pick es un comando que permite tomar uno o varios commits de otra rama o branch sin tener que hacer un merge completo. Así, gracias a cherry-pick, podríamos aplicar los commits relacionados con nuestra funcionalidad en la rama master sin necesidad de hacer un merge.

**Comando**.

`git cherry-pick <hash_del_commit>`

**Resultado:**

Creamos 3 commit sobre una rama y cuando se desea obtener un cambio que esta sobre otra rama, buscamos el hash de ese commit o varios, despues nos pasamos a la rama donde se desea tener esos cambios y corremos el comando.

Ejemplo de respuesta al correr el comando:

    [master c66c7a5] Creditos al team Platzi
    Date: Thu Apr 18 12:13:12 2023 -0700
    1 file changed, 1 insertion(+)

Despues obtenemos cambios de la rama remota y enviamos cambios y queda actualizada la rama con solo los cambios requeridos.

## Listar toda la historia completa

**Comando**.

`git reflog`

**Resultado:**

    aa27bee HEAD@{40}: checkout: moving from cabecera to master
    77f9e1f HEAD@{41}: commit: Se agrega cabecera y se modifica el README.md
    aa27bee HEAD@{42}: checkout: moving from master to cabecera
    aa27bee HEAD@{43}: commit: Cambiar el HTML y agregar estilos
    e408936 HEAD@{44}: commit: Reemplazo de versión del archivo historia.txt y se agrega mas comando en README.md
    284fd82 (tag: v0.1) HEAD@{45}: commit: Pagina y estilos Blog post
    f591517 HEAD@{46}: commit: Se modifica README y a se agrega Imagen
    fc71632 HEAD@{47}: commit: Agregamos un cambio en su personalidad.
    637bc50 HEAD@{48}: commit: Modificación archivo historia y se añade comandos al README.md
    07e0ccf HEAD@{49}: commit (initial): Primer commit

## Aplicar git reset --SOFT

**git reset --soft HashDelHEAD**: te mantiene lo que tengas en staging ahí.

**Comando**.

`git reset <cabecera que se quiere volver>`

**Resultado:**

Queda en estado no protegido, pero no devuelve los archivos eliminados o modificados.

## Aplicar git reset --HARD

**git reset --hard HashDelHEAD**: resetea absolutamente todo incluyendo lo que tengas en staging.

**Comando**.

`git reset --HARD <cabecera que se quiere volver>`

**Resultado:**

Elimina todo en el historial y queda en el hash como el más actualizado hasta el momento.

    HEAD is not at c894560 <Comentario del push>.

## Remendar un commit

Remendar un commit con amend puede modificar el commit más reciente (enmendar) en la misma rama.

Este comando sirve para agregar archivos nuevos o actualizar el commit anterior y no generar commits innecesarios. También es una forma sencilla de editar o agregar comentarios al commit anterior porque abrirá la consola para editar este commit anterior.

***Atención***

Usar amend es una mala práctica, sobre todo cuando ya se ha hecho push o pull al repositorio remoto. Al momento de hacer amend con algún commit que esté en remoto, va a generar un conflicto que se va a arreglar haciendo un commit adicional y se perderá el beneficio del amend.

**Comando**.

`git commit --amend`

**Ejemplo**.

1. Aplicamos un cambio sobre el archivo y realizamos un commit.

        $ git commit -am 'cambiar texto del tagline'
        [master 03aa0e1] cambiar texto del tagline
        2 files changed, 25 insertions(+), 1 deletion(-)

2. Se nos olvida aplicar un cambio. aplicamos el cambio y corremos el comando `git add <archivos_modificados>`.

3. corremos el comando, y lo que nos hace es que los cambios realizados los une con el commit anterior sin necesidad de hacer otro commit.

4. Nos dira si deseamos cambiar el mensaje del commit.

5. Visualizamos el resultado.

**Resultado:**

    $ git commit --amend
    [master a4266fd] cambiar texto del tagline se agrega nuevo parrafo.
    Date: Tue Feb 7 21:11:34 2023 -0500
    2 files changed, 38 insertions(+), 1 deletion(-)

## Buscar una palabra en toda la solución

**Comando**.

`git grep <palabra_a_buscar>`

**Ejemplo**.

`git grep color`

**Resultado:**

    Assets/css/styles.css:    color: green;
    Assets/css/styles.css:    color: white;
    Git.md:![Ejemplo cambiando color de la fuente en Cabecera](https://github.com/miguel0920/Curso-Git-Y-GitHub/raw/main/Assets/Images/CambiarEstilo_ConflictoMerge_Cabecera.png)
    Git.md:![Ejemplo cambiando color de la fuente en Master](https://github.com/miguel0920/Curso-Git-Y-GitHub/raw/main/Assets/Images/CambiarEstilo_ConflictoMerge_Master.png)
    GitRemote.md:![Ejemplo cambiando color de la fuente en Cabecera](https://github.com/miguel0920/Curso-Git-Y-GitHub/raw/main/Assets/Images/CopiasUrlRemota.png)

## Buscar una palabra y # de la línea en toda la solución

**Comando**.

`git grep -n <palabra_a_buscar>`

**Ejemplo**.

`git grep -n Lorem`

**Resultado:**

    $ git grep -n Lorem
    blogpost.html:23:            <p>Lorem, ipsum dolor sit amet consectetur adipisicing elit. Fuga maiores quae voluptates error pariatur
    blogpost.html:28:                Lorem ipsum dolor sit amet consectetur adipisicing elit. Quos veniam, eligendi, eveniet tenetur odit
    blogpost.html:33:                Lorem ipsum dolor sit amet consectetur adipisicing elit. Quos veniam, eligendi, eveniet tenetur odit

## Obtener la cantidad que se repite una palabra

**Comando**.

`git grep -c <palabra_a_buscar>`

**Ejemplo**.

`git grep -c Lorem`

Buscar una etiqueta por ejemplo.

`git grep -c "<p>"`

**Resultado:**

    $ git grep -c Lorem
    Git.md:5
    blogpost.html:3

    $ git grep -c "<p>"
    Git.md:2
    blogpost.html:3

## Buscar la cantidad de palabras repetidas en el historial

**Comando**.

`git log -S "<palabra_a_buscar>"`

**Ejemplo**.

`git log -S "blog"`

**Resultado:**

    $ git log -S "blog"
    commit d9f72a096b8c2e814c2b20acde04dd280771af63 (origin/header, header)
    Author: Miguel Angel Barahona <miguelbarahona00@gmail.com>
    Date:   Mon Feb 6 20:57:59 2023 -0500

        Agregar comando para trabajar con diferentes destinos

    commit 8ac0a49e77bf2597165677d990d38071ba4a7623
    Author: Miguel Angel Barahona <miguelbarahona00@gmail.com>
    Date:   Wed Feb 1 20:28:22 2023 -0500

## Buscar cuantos commit a hecho el equipo

**Comando**.

`git shortlog -sn --all`

**Resultado:**

    git shortlog -sn --all
        39  Miguel Angel

## Buscar cuantos commit a hecho el equipo sin el merge

**Comando**.

`git shortlog -sn --all`

**Resultado:**

    $ git shortlog -sn --all --no-merges
        35  Miguel Angel Barahona

`git shortlog -sn --all --no-merges`

**Resultado:**

    git shortlog -sn --all
        39  Miguel Angel

## Crear un alías global

**Comando**.

`git config --global alias.<nombre_del_alías> "<comando>"`

**Ejemplo**.

`git config --global alias.stats "shortlog -sn --all --no-merges"`

**Resultado:**

Una vez creado corremos el comando `git <nombre_del_alías>`, ejemplo `$ git stats`

    $ git stats
    35  Miguel Angel Barahona

## Quien realizo cambios sobre un archivo

**Comando**.

`git blame <nombre_del_archivo>.<extensión>`

**Ejemplo**.

`git blame historia.txt`

**Resultado:**

    $ git blame historia.txt
    637bc508 (Miguel Angel Barahona 2023-01-25 20:40:38 -0500  1) Esta es la historio de Miguel
    637bc508 (Miguel Angel Barahona 2023-01-25 20:40:38 -0500  2)
    637bc508 (Miguel Angel Barahona 2023-01-25 20:40:38 -0500  3) Miguel tiene 27 años y nació en Colombia
    637bc508 (Miguel Angel Barahona 2023-01-25 20:40:38 -0500  4)
    fc71632a (Miguel Angel Barahona 2023-01-25 20:56:55 -0500  5) Hoy hablaremos de su historia.
    fc71632a (Miguel Angel Barahona 2023-01-25 20:56:55 -0500  6)
    e4089360 (Miguel Angel Barahona 2023-01-27 20:59:10 -0500  7) Sus cualidades son:
    e4089360 (Miguel Angel Barahona 2023-01-27 20:59:10 -0500  8)
    e4089360 (Miguel Angel Barahona 2023-01-27 20:59:10 -0500  9) - Honesto
    e4089360 (Miguel Angel Barahona 2023-01-27 20:59:10 -0500 10) - Respetuoso

## Quien realizo cambios sobre un archivo desde una linea a otra

**Comando**.

`git blame <nombre_del_archivo>.<extensión> -L35,60`

**Ejemplo**.

`git blame historia.txt -L2,5`

**Resultado:**

    $ git blame historia.txt -L2,5
    637bc508 (Miguel Angel Barahona 2023-01-25 20:40:38 -0500 2)
    637bc508 (Miguel Angel Barahona 2023-01-25 20:40:38 -0500 3) Miguel tiene 27 años y nació en Colombia
    637bc508 (Miguel Angel Barahona 2023-01-25 20:40:38 -0500 4)
    fc71632a (Miguel Angel Barahona 2023-01-25 20:56:55 -0500 5) Hoy hablaremos de su historia.

[Ir a GitHub >>](GitRemote.md)
