# Comandos con Git y GitHub

## Comandos para ejecutar en Bash o consola de Ubuntu

1. Visualizar ruta actual

    **Comando**.

    `pwd`

    **Resultado:**

        /d/Cursos/Documents/Cursos Platzi/Git

2. Visualizar todos los archivos excepto los ocultos en lista

    **Comando**.

    `ls -l`

    **Resultado:**

        total 3

        drwxr-xr-x 1 {Usuario} 197121   0 Jan 25 19:17 Assets/

        -rw-r--r-- 1 {Usuario} 197121 568 Jan 25 19:29 README.md

3. Visualizar todos los archivos y ocultos en forma de lista

    **Comando**.

    `ls -al`

    **Resultado:**

        total 5

        drwxr-xr-x 1 {Usuario} 197121   0 Jan 25 19:24 ./

        drwxr-xr-x 1 {Usuario} 197121   0 Jan 17 22:00 ../

        drwxr-xr-x 1 {Usuario} 197121   0 Jan 25 19:24 .git/

        drwxr-xr-x 1 {Usuario} 197121   0 Jan 25 19:17 Assets/

        -rw-r--r-- 1 {Usuario} 197121 568 Jan 25 19:29 README.md

4. Direccionar al Home

    **Comando**.

    `cd /`

    **Resultado:**

        {Nombre del usuario actual}@{nombre del equipo} MINGW64 /

5. Visualizar todos los archivos excepto los ocultos

    **Comando**.

    `ls -a`

    **Resultado:**

        ./  ../  .git/  Assets/  README.md

6. Limpiar consola

    **Comando**.

    `clear` o CTRL + L

7. Devolverse entre las carpetas

    **Comando**.

    `cd ..`

8. Crear carpeta

    **Comando**.

    `mkdir {nombre de la carpeta}`

9. Crear un archivo

    **Comando**.

    `touch {nombre del archivo}.{extension}`

    **Ejemplo**.

        touch archivo.txt

10. Visualizar contenido del archivo

    **Comando**.

    `cat {nombre del archivo}`

    **Ejemplo**.

        cat archivo.txt

11. Visualizar historial de comandos

    **Comando**.

    `history`

    **Resultado:**

        1 cd
        2 pwd

12. Dirigirse a un comando corrido

    **Comando**.

    `!{Numero del comando}`

    **Ejemplo**.

        !2

13. Eliminar archivo (Tener cuidado al correr el comando)

    **Comando**.

    `rm {nombre del archivo}`

    **Ejemplo**.

        rm archivo.txt

14. Visualizar opciones de un comando

    **Comando**.

    `rm --help`

## Comandos Git

### Crear repositorio local

Para correr el comando `git init` nos debemos ubicar en la carpeta donde se almacenara todos los archivos del proyecto.

**Comando**.

`git init`

**Resultado:**

    Initialized empty Git repository in C:{Ruta de la carpeta}

### Visualizar estado actual del repositorio

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

### Agregar archivos

**Comando**.

Añade todos los documentos.

`git add .`

Añade un documento especifico

`git add historia.txt`

**Resultado:**

Al correr el comando `git status` se visualiza que se han añadido archivos para enviar al repositorio.

    On branch master

    No commits yet

    Changes to be committed:
    (use "git rm --cached <file>..." to unstage)
            new file:   README.md
            new file:   historia.txt

### Devolver un archivo

**Comando**.

Al correr el siguiente comando se devuelve un archivo el comando `--cached` es para quitar el archivo en memoria RAM.

`git rm --cached {archivo}`

Ejemplo

`git rm --cached historia.txt`

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
