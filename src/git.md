# Comandos git

[ Trabajar en local y luego subir a remoto ]

## 1. Iniciar el proyecto

git init [nombre de la carpeta]

>nombre de carpeta es opcional,
>crea un directorio con el git,
>hay que ingresar en la carpeta

## 2. clonar el proyecto

git clone [https://servicio.../proyecto.git]

>Importante: así luego se pueden crear ramas en local
>y también acceder al main branche (rama)

## 3. Crear una rama local

git checkout -b [nombre de la RAMA]

>Para mi es mejor siempre trabajar en una rama y no el main

## 4. Trabajar, copiar archivos, editar, etc.

## 5. Agregar los cambios

git add [.] o [nombre de archivo]

>. agrega todos los archivos
>de lo contrario nombre de cada archivo

## 6. Verificar

git status

## 7. Hacer el commit

git commit -am "mensaje para el git"

## 8. Hacer el push al servidor

git push -u [https://servicio.../proyecto.git] [nombre RAMA]

## 9. De allí en adelante usar

git push // o // git pull

>ATENCION: siempre hay que repetir desde el paso 4

------------------

#### [ Webs ]
https://stackoverflow.com/questions/40643488/upload-files-to-a-branch-in-github
https://codigofacilito.com/articulos/commits-administrar-tu-repositorio
https://victorhckinthefreeworld.com/2018/08/09/6-errores-comunes-al-utilizar-git-y-como-solucionarlos/
https://about.gitlab.com/images/press/git-cheat-sheet.pdf
------------------
[ Gestionar una clave publica SSH ]

## 1. Crear RSA key Pair

ssh-keygen

## 2. Aparecen los siguientes mensajes:

>Generating public/prive rsa key pair.
>Enter File in which to save the key (/your_home/.ssh/id_rsa):

## 3. En ambos casos dar Enter para crear la clave.

## 4. Visualizar la clave

cat ~/.ssh/id_rsa.pub

## 5. Utilizar

>Copiamos la clave y la pegamos en los servidores que la soliciten,
>en mi caso fue gitlab

-------------------------

#### [ Webs ]
https://support.shells.net/hc/en-us/articles/360060692313-How-To-Generate-an-SSH-Key-on-Ubuntu-20-04
https://www.digitalocean.com/community/tutorials/how-to-set-up-ssh-keys-on-ubuntu-20-04

-------------------------

[ fin ]
