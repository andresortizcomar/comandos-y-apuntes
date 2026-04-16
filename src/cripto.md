# Encriptado en Linux/Ubuntu

Necesitamos tener GnuPG o GPG (GNU Privacy Guard).
Generalmente ya está instalado en Ubuntu.

## 1. Instalación

> sudo apt-get install gnupg2

#### Comprobar instalación

> gpg --h
> gpg --v

## 2. Encriptar un archivo

> gpg -c [archivo]

Al encriptar un archivo solicita la clave 2 veces.

#### Atención: 
utilizar el archivo con extensión [archivo].gpg que se generó.

## 3. Desencriptar

> gpg [archivo].gpg

Esto restaura el archivo original.
----
