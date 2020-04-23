###### tags: `git` `github`

GIT - GITHUB
============

Aprendiendo git.

## Table of contents
- [GIT - GITHUB](#git---github)
  - [Table of contents](#table-of-contents)
- [Instalando Git](#instalando-git)
- [Flujo de trabajo en Git](#flujo-de-trabajo-en-git)
- [Tu Identidad](#tu-identidad)
- [GITHUB Interface](#github-interface)
  - [1. Crear Repositorio vacio en Github.](#1-crear-repositorio-vacio-en-github)
  - [2. Nombre del repositorio y configuraciones](#2-nombre-del-repositorio-y-configuraciones)
  - [3. Alojando un proyecto local en el repositorio ya creado.](#3-alojando-un-proyecto-local-en-el-repositorio-ya-creado)
    - [Existen 2 opciones](#existen-2-opciones)
  - [4. Clonando un repositorio de Github](#4-clonando-un-repositorio-de-github)
- [Pasos que usualmente se realiza cuando se trabaja con Git.](#pasos-que-usualmente-se-realiza-cuando-se-trabaja-con-git)
  - [1. Obteniendo cambios del remoto](#1-obteniendo-cambios-del-remoto)
  - [2. Editar archivos](#2-editar-archivos)
  - [3. Git diff](#3-git-diff)
  - [4. Git status](#4-git-status)
  - [5. Git add](#5-git-add)
  - [6. Git diff or git diff  --staged](#6-git-diff-or-git-diff---staged)
  - [7. Git Commit](#7-git-commit)
  - [8. Git Log](#8-git-log)
  - [9. Git push](#9-git-push)

# Instalando Git
- En manjaro
```shell=
# Si usamos yay como gestor de paquetes
yay -Sy  # para actualizar las bases de datos de paquetes del servidor
yay -S git

# o si usamos pacman
sudo pacman -Sy
sudo pacman -S git
```
- En Debian/Ubuntu/Kubutu/Lubuntu/Linux Mint/Deepin.
```shell=
sudo apt update
sudo apt install git
```
# Flujo de trabajo en Git

<!-- ![](https://i.imgur.com/CNK97MR.png) -->
![](https://i.imgur.com/cCT6Ime.png)
 
# Tu Identidad

Lo primero que debemos hacer cuando instalamos Git es establecer nuestro nombre de usuario y dirección de correo electrónico. Esto es importante porque los "commits" de Git usan esta información, y es introducida de manera inmutable en los commits que envías:

Un documento para [configurar-Git-por-primera-vez](https://git-scm.com/book/es/v2/Inicio---Sobre-el-Control-de-Versiones-Configurando-Git-por-primera-vez).

```shell=
git config --global user.name "John Doe"
git config --global user.email johndoe@example.com
```


# GITHUB Interface

## 1. Crear Repositorio vacio en Github.
![](https://i.imgur.com/6E0AmD9.png)
## 2. Nombre del repositorio y configuraciones 
 - public repository
 - private repository
 
ELEGIR publico/privado

![](https://i.imgur.com/ReUeFZQ.png)

Ya habiendo creado un repositorio en github, subir un proyecto local al repositorio que se acaba de crear.

## 3. Alojando un proyecto local en el repositorio ya creado.

### Existen 2 opciones

- **Via [SSH](https://techterms.com/definition/ssh)**
Significa "Secure Shell". SSH es un método de comunicación segura con otra computadora. La parte "segura" del nombre significa que todos los datos enviados a través de una conexión SSH están encriptados . Esto significa que si un tercero intenta interceptar la información que se transfiere, parecería codificada e ilegible. La parte "shell" del nombre significa que SSH se basa en un shell Unix , que es un programa que interpreta los comandos ingresados ​​por un usuario.
- **Via [HTTP](https://techterms.com/definition/http)**
Significa "Protocolo de transferencia de hipertexto". HTTP es el protocolo utilizado para transferir datos a través de la web . Es parte del conjunto de protocolos de Internet y define los comandos y servicios utilizados para transmitir datos de la página web .
![](https://i.imgur.com/QyBfzPL.png)

Antes de avanzar veamos un [flujo de trabajo en Git](https://medium.com/laboratoria-how-to/describiendo-el-flujo-de-trabajo-en-git-ede2eee5b589).

1. Iniciar un proyecto git.
`git init`
2. Adicionado todo los archivos con `.` al area de stagin.
`git add .`
4. Commit.
`git commit -m "comentario de los cambios" -m 'otro comentario'`
4. Adicionando al remoto un proyecto en Git.
`git remote add origin git@github.com:<github-user>/<repo-name>.git`
5. Pusheando/Subiendo un proyecto al repositorio de Github. En este caso a la rama `master`.
`git push origin master`
pero, podria ser a cualquier otra rama, por ejemplo: `branch develop`.
`git push origin develop`

## 4. Clonando un repositorio de Github
Hay dos opciones para clonar.
- SSH
![](https://i.imgur.com/vvaCttW.png)

```shell=
git clone git@github.com:github-user/name-project.git
```
- HTTP
![](https://i.imgur.com/XmCtvGm.png)
```shell=
git clone https://github.com/github-user/name-project.git
```
>Personalmente uso la opcion de SSH. 

# Pasos que usualmente se realiza cuando se trabaja con Git.
Esto como Sugerencia...
Esto lo tienes q saber como el padre nuestro.
okno.
1. [Obtener cambios del remoto](#1-Obteniendo-cambios-del-remoto)
2. [editar los archivos](#2-Editar-archivos)
3. [git diff](#3-Git-diff0)
4. [git status](#4-Git-status)
5. [git add](#5-Git-add)
6. [git diff](#6-Git-diff-or-git-diff---staged)
7. [git commit](#7-Git-Commit)
8. [git log](#8-Git-Log)
9. [git push](#9-Git-push)
 
## 1. Obteniendo cambios del remoto

Es necesario tener actualizado los cambios del repositorio remoto, porque cuando se trabaja en equipo es muy comun toparse con conflictos.

**Primera opcion:** Pull
```shell=
git pull
# o 
git pull --rebase
```
**Segunda option:** Fetch y merge
```shell=
git fetch
git merge origin/master
```
>Personalmente prefiero usar `fetch y merge` o `fetch` y [rebase](https://git-scm.com/docs/git-rebase)

Y listo con cualquiera de las 2 opciones ya se tendra los datos actualizado.

## 2. Editar archivos
Aqui trabajas en tu codigo local.

## 3. Git diff
Para ver los cambios que hiciste en tu codigo.
```shell=
git diff
```
## 4. Git status
Para listar que archivos que se agregaron, modificaron o eliminaron.
```shell=
git status
```
## 5. Git add
Luego de haber modificado los archivos necesarios hay que agregarlos al `staging area`.
```shell=
# para agregar todos los archivos que se listan en el status
git add .
# o si solo quiere agregar un archivo en especifico  
git add file_name
```
## 6. Git diff or git diff  --staged
Para ver los cambios que hiciste en tu codigo despues de haber hecho git add.
```shell=
git diff
git diff --staged
```

## 7. Git Commit
Luego de tener los archivos modificados en el `staging area`, estos ya estan listos para realizar una confirmacion. (se creara un historico)

>Agregando un titulo y cuerpo al mensaje del commit con `-m` y `-m`
```shell=
git commit -m "Added new files" -m "Added new files in src folder"
```
En caso de que se haya equivocado con el mensaje del commit, puede renombrarlo con `--amend`
```shell=
git commit --amend -m "Nuevo mensaje"
```
## 8. Git Log
Si quieres listar todos los commits que se hicieron:
```shell=
git log
```
Si quieres ver solo tus commits.
```shell=
git log --author=TuNombre
```
Si quieres ver que archivos modificaste en los commits
```shell=
git log --oneline --stat 
```
Si quieres ver que archivos y lineas modificaste en los commits 
```shell=
git log -p --author=TuNombre
# --author=TuNombre opcional
```
## 9. Git push
Una vez que se realiza git add, git commit se procede a subir los cambios al repositorio remoto.
**Nota:** Puede que tengas conflictos al momento de realizar `push`, para solucionarlo [ver paso 1](#1-Obteniendo-cambios-del-remoto)
```shell=
git push origin master
# or
git push origin
```

3 doritos despues :ghost: empiezas desde el paso 1.
y asi despues codeas, commiteas, pusheas, comes, duermes, despiertas, codeas, commiteas, pusheas, duermes ... XD

Original post: [git basic](https://hackmd.io/@pattty/git-basic)


----
En resumen, el flujo de trabajo en Git luce asi.
![](https://i.imgur.com/JbfKR87.png)





