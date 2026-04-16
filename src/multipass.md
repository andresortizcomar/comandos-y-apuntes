# Multipass
Una opción para crear VM en Linux/Ubuntu.
Y también en Windows y Mac (puaj).

## 1. Instalación

> sudo snap install multipass

## 2. Listar imágenes
Las imágenes son plantillas de distribuciones

> multipass find

## 3. Crear una VM

> multipass launch -n [nombre]

#### Nota:
[nombre]: nombre de instacia de VM.

## 4. Crear una VM con características específicas

> multipass launch -c [X] -m [X]G -d [XX]G -n [nombre] [imágen]

#### Notas:
[X] son números
-c: cántidad de procesadores
-m: cantidad de memoria
-d: total del disco
[imágen]: alias o nombre de la imágen, por ejemplo 20.04

## 5. ingresar en la VM

> multipass shell [nombre]

### Nota:
Para salir es simplemente 
> exit

## 6. Listar VMs

> multipass list

### 6.1 Información sobre la VM

> multipass info [nombre]

## 7. Encender y detener multipass

> multipass start

> multipass stop

## 8. Borrar una VM

> multipass delete [nombre]

## 9. Purgar una instancia

> multipass purge

## 10. Montar una carpeta en la VM/instancia

> multipass mount ~/[carpeta] [nombreVM]

#### Nota:
Se utiliza la ruta absoluta para el mount

### 10.1 Desmontar la carpeta

> multipass unmount

----
