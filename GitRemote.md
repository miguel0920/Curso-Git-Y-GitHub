# Git Remoto

## Agregar origen remoto (HTTPS)

**Comando**.

`git remote add origin {url del repositorio}`

**Ejemplo**.
Copiamos la url del repositorio remoto que se encuentra en HTTPS.

![Ejemplo cambiando color de la fuente en Cabecera](https://github.com/miguel0920/Curso-Git-Y-GitHub/raw/main/Assets/Images/CopiasUrlRemota.png)

`git remote add origin https://github.com/miguel0920/Curso-Git-Y-GitHub.git`

**Resultado:**

No se visualiza nada pero al correr el comando `git remote`, se visualiza lo nuevo creado llamado origin

    $ git remote
    origin

## Visualizar conexión Remota en local

**Comando**.

`git remote -v`

**Resultado:**

    $ git remote -v
    origin  https://github.com/miguel0920/Curso-Git-Y-GitHub.git (fetch)
    origin  https://github.com/miguel0920/Curso-Git-Y-GitHub.git (push)

Se visualizar dos opciones:

**(fetch):** Traer codigo remoto.

**(push):** Enviar codigo al remoto.

## Enviar cambios a la rama local

**Comando**.

Se coloca **master:main** porque master significa la rama local y main es la rama remota donde queremos enviar, si enviamos solo **master** nos creara una rama nueva en GitHub.

`git push origin master:main`

**Resultado:**

***Nota: puede que le solicite las credenciales si es la primera vez.***

De lo contrario se visualiza el siguiente mensaje, del cual nos dice que debemos integrar los cambios remotos antes de enviarlos.

    git push origin master:main
    To https://github.com/miguel0920/Curso-Git-Y-GitHub.git
    ! [rejected]        master -> main (fetch first)
    error: failed to push some refs to 'https://github.com/miguel0920/Curso-Git-Y-GitHub.git'
    hint: Updates were rejected because the remote contains work that you do
    hint: not have locally. This is usually caused by another repository pushing
    hint: to the same ref. You may want to first integrate the remote changes
    hint: (e.g., 'git pull ...') before pushing again.
    hint: See the 'Note about fast-forwards' in 'git push --help' for details.

## Obtener cambio de la rama remota

**Comando**.

`git pull origin {rama remota}`

**Ejemplo**.
`git pull origin main`

**Resultado:**

Se nos visualiza un error que se reúsa a realizar el merge con mi rama local por son dos historias distintas.

    remote: Enumerating objects: 3, done.
    remote: Counting objects: 100% (3/3), done.
    remote: Compressing objects: 100% (2/2), done.
    remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
    Unpacking objects: 100% (3/3), 639 bytes | 71.00 KiB/s, done.
    From https://github.com/miguel0920/Curso-Git-Y-GitHub
    * branch            main       -> FETCH_HEAD
    * [new branch]      main       -> origin/main
    fatal: refusing to merge unrelated histories

## Obtener cambio de la rama remota con su historia

**Comando**.

`git pull origin {rama remota} --allow-unrelated-histories`

**Ejemplo**.
`git pull origin main --allow-unrelated-histories`

**Resultado:**

Si salen conflictos se resuelven de lo contrario nos pedira ingresar un mensaje del cual ingresamos y queda listo para enviar los cambios a la rama remota.

## Configurar conexión SSH con GitHub

Nos ubicamos en el home de nuestra ruta con `cd`, una vez ubicado en el home (~) revisamos que el correo que tenemos configurado localmente sea el mismo al del repositorio de GitHub con el comando `git config -l`, de no estar lo realizar el cambio.

Ahora corremos el siguiente comando para crear una llave publica y privada en Windows.

**Comando**.

`ssh-keygen -t rsa -b 4096 -C "{email}"`

**Ejemplo**.

`ssh-keygen -t rsa -b 4096 -C "miguelbarahona00@gmail.com"`

**Resultado:**

**Enter file in which to save the key (/c/Users/{user}/.ssh/id_rsa)**: Nos solicitara la carpeta en donde almacenar las llave damos enter.

**Enter passphrase (empty for no passphrase)**: No solicita una clave con espacios para este ejemplo damos enter.

**Enter same passphrase again**: Nos solicita repetir la clave con espacios, pero en este caso damos enter.

Por último se genera las llaves.

    Generating public/private rsa key pair.
    Enter file in which to save the key (/c/Users/{user}/.ssh/id_rsa):
    Enter passphrase (empty for no passphrase):
    Enter same passphrase again:
    Your identification has been saved in /c/Users/{user}/.ssh/id_rsa
    Your public key has been saved in /c/Users/{user}/.ssh/id_rsa.pub
    The key fingerprint is:
    SHA256:e5Ijq2CI2iiWUjjjY417g9nENVGHw34ggFwKyqKD7U miguelbarahona00@gmail.com
    The key's randomart image is:
    +---[RSA 4096]----+
    |+.+o. o...       |
    | +   o =..       |
    |o     + o        |
    |o    o . .       |
    |o.o . . S        |
    |Oo.+     o       |
    |A+E   . = .      |
    |+/ *   o +       |
    |A.* o..          |

## Revisar agente SSH este corriendo

Con el siguiente comando revisamos que el agente SSH este prendido el cual nos permite que las llaves esten corriendo y puedan comunicarse con cualquier servicio por ejemplo GitHub.

**Comando.**

`eval $(ssh-agent -s)`

**Resultado.**

Si se nos visualiza el siguiente mensaje significa que esta corriendo el agente.

    Agent pid 1656

## Agregar llave publica al entorno (Windows, Linux)

**Comando.**

`ssh-add {ruta del home}/{carpeta alojada de las llaves}/{llave privada}`

**Ejemplo**.

Se utiliza `~` por que es el shortcut de nuestro home.

`ssh-add ~/.ssh/id_rsa`

**Resultado.**

    Identity added: /c/Users/{user}/.ssh/id_rsa (mbarahona00@gmail.com)

Una vez realizado agregar la llave publica en el servicio que deseamos que se conecten.

## Cambiar conexión remoto HTTPS a SSH

Revisamos la conexión actual con el comando `git remote -v` una vez se identique cambiamos la conexión.

**Comando.**

`git remote set-url origin {url ssh}`

**Ejemplo**.

`git remote set-url origin git@github.com:miguel0920/Curso-Git-Y-GitHub.git`

**Resultado.**

1. Al corre el comando `git remote -v` se visualiza la nueva conexión.
2. Corremos el comando `git pull` para obtener los cambios de la rama remota.
3. Se nos visualizara el siguiente mensaje y damos es aceptar (yes).

        The authenticity of host 'github.com ({ip})' can't be established.
        ED25519 key fingerprint is SHA256:+DiY3wvvV6TuJJhbpZisF/zLDA0zPMSvHdkr4UvCOqU.
        This key is not known by any other names
        Are you sure you want to continue connecting (yes/no/[fingerprint])?
4. Obtener cambios desde remoto `git pull origin {nombre de la rama}`
5. Proteger cambios y sube los cambios que se tengan en local `git push origin {nombre de la rama remota}`.
