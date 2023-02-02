# Comandos en Terminal Git Bash

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

15. Crear un alias

    **Comando**.

    `alias {nombre del alias}="git log --all --graph --decorate --oneline"`

    **Ejemplo**.

    `alias historialProject1="git log --all --graph --decorate --oneline"`

    **Resultado**.

    Corremos el nombre del alias que se coloco a nuestro comando y lo corremos.

    `historialProject1`

[Ir a Git >>](Git.md)
