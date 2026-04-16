# Mysql

## Servidor

### Ubuntu

> service mysql [comando]

[Comando] es status, start, restart

### CentOS

> systemctl [comando] myslq

-------------

## Ingresar en mysql

> mysql -u [usuario] -p

-------------
## Respaldos

## Volcado 

### Simple en un archivo sql
Hay que conocer el usuario y la contraseña claro
No hace falta ingresar en mysql

> mysqldump -u [usuario] -p nombre_BBDD > nombre-archivo.sql

### Comprimido

> mysqldump -u [usuario ] -p nombre_BBDD | gzip -c > archivo.gz

## Restaurar

### 1. Ingresar en mysql

> mysql -u [usuario] -p

### 2. Crear la base de datos

> CREATE DATABASE nombre_BBDD;

### 3. Salir de mysql

> exit;

### 4. Volcar el respaldo simple en la BBDD

> mysqldump -u [usuario] -p nombre_BBDD < archivo.sql

#### Volcar respaldo comprimido

> gunzip < archivo.sql.gz | mysql -u [usuario] -p nombre_BBDD


--------
# Borrar una BBDD
Antes hay que ingresar en mysql con usuario y contraseña

> DROP DATABASE nombre_BBDD;

---------
# Usuarios
Se debe siempre ingresar en mysql con usuario y contraseña

## Crear un usuario

> CREATE USER 'usario'@'localhost' IDENTIFIED BY 'contraseña';

La contraseña tiene algunos requisitos, debe tener al menos 8 carácteres.

## Asignar un usuario a una BBDD

> GRANT ALL PRIVILEGES ON nombre_BBDD.* TO usuario@localhost;

y luego

> FLUSH PRIVILEGES;

## Revocar permisos

> REVOKE GRANTS ON nombre_BBDD.* TO usuario@localhost;

y luego

> FLUSH PRIVILEGES;

## Borrar un usuario

> DROP USER 'usuario'@'localhost';

----------

# Obtener info de la BBDD
ingresar en mysql

## 1. Usar la BBDD

> USE nombre_BBDD;

## 2. Obtener la info

> DESCRIBE nombre_TABLA;

--------







