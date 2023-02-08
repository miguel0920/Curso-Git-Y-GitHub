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

[Ir a GitHub >>](GitRemote.md)
