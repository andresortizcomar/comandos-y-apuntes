# [ Carpetas / Directorios ]

## Copiar o mover

Si están en el mismo nivel

> cp -r directorio/ carpeta-destino

Si está en un nivel superior

> cp -r directorio/ ../carpeta-destino

### Copiar archivos

>cp -arf origen/* destino/

### Copiar conservando permisos

> cp -ra /directorio/dir1 /home/destino

Si se utiliza / antes del nombre del directorio se refiere a una dirección absoluta

## Renombrar o Mover

> mv directorio nuevo_nombre

> mv -backup origen destino

## Eliminar

#### A la fuerza

> rm -rf directorio
> rm -rf directorio/*

#### Con preguntas

>rm -r directorio

----------------------
## Tamaño de archivos y carpetas

> du -sh *

-----------------------

# [ Listar ]

### Listado con permisos

> ls -l 

### Listado con ocultos

> ls -a

### Listado con permisos notacion octal

> stat -c "%a %n" *

--------------------------

# Rsync
Sirve para sincronizar.
Es muy poderoso, ya que con las opciones se puede controlar que copiar
Me sirvió porque se puede evitar copiar archivos que ya hayan sido copiados

## rsync simple de todos los archivos de un directorio

> rsync /origen/ /destino/d1/

## rsync simple de un tipo de archivo

> rsync /origen/*.jpg /destino/d1/

Nota: linux diferencia las mayúsculas de las minúsculas en las extensiones

## rsync recursivo, es decir, copia también las sub-carpetas

> rsync -r /origen/ /destino/d1/

## rsync con include y exclude

> rsync -rv --include '*/' --include '*.pdf' --exclude '*' /origen/ /destino/

Usar esto fue mucho muy útil

## rsync que ignora los existentes

> rsync -av --ignore-existing /origen/ /destino/

---------
## RSYNC remotos con SSH

Para sincronizar carpetas locales y remotas

### Rsync de local a remoto

> rsync -a -e "ssh -p 1111" /origen/ usuario@12.12.12.12:/destino-remoto/

### Rsync de remoto a local

> rsync -avP -e "ssh -p 1111" usuario@12.12.12.12:/origen-remoto/ /destino-local/

P permite ver el progreso

Nota: ver las opciones--dry-run --update

------------------------

# [ Permisos ]

## Asignar un usuario

> sudo chown -R usuario:grupo /carpeta

### Ejemplo:

> sudo chown apache:apache /var/www/

## Ver

> sudo chown g+w carpeta

---------------------------

# [ Comprimir y extraer ]

## Extraer

> tar -xf nombre_archivo.tar.gz --directory /carpeta

## Comprimir

> tar -czvf /carpeta/archivo.tar.gz  /origen

## Comprimir con exclude

> tar -czvf /destino/archivo.tar.gz --exclude=\*.{jpg,gif,png,wmv,flv,tar.gz,zip} /origen


