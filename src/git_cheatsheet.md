# 🚀 Git Survival Guide - Flujo de Trabajo Profesional

Este documento sirve como referencia rápida para mantener un historial de código limpio, seguro y organizado.

## 1. Configuración Inicial (Solo una vez)
Antes de empezar, asegúrate de que tus commits tengan tu firma:
```bash
git config --global user.name "Andrés Ortiz"
git config --global user.email "andresortiz.com.ar@gmail.com"
```
# Alias recomendado para ver el historial visualmente

```bash
git config --global alias.adog "log --all --decorate --oneline --graph"
```

## 2. Preparando un Proyecto Nuevo

1. Si tienes código suelto y quieres profesionalizarlo:

2. Inicializar: git init

3. Ignorar basura: touch .gitignore (Añade aquí .env, node_modules/, dist/, etc.)

### Primer guardado:

```bash
git add .
git commit -m "feat: inicializar estructura del proyecto"
```
4. Conectar a la nube:

#### Depreciado
bash
git remote add origin [https://github.com/usuario/repositorio.git](https://github.com/usuario/repositorio.git)

### Correcto

Se debe crear una llave SSH para poder conectar local con github

1. Genera la llave (solo dale a Enter a todo cuando pregunte):

```bash
ssh-keygen -t ed25519 -C "tu@email.com"
```

2. Copia la llave pública generada:
Copia todo el texto que empieza con ssh-ed25519...)

```bash
cat ~/.ssh/id_ed25519.pub
```
3. Pégala en GitHub:

* Ve a GitHub → Settings (tu foto arriba a la derecha) → SSH and GPG keys.
* Click en New SSH key, ponle un nombre (ej: "Mi Notebook") y pega el código.

4. Cambia el "remoto" de tu proyecto a SSH:

```bash
git remote set-url origin git@github.com:tu-usuario/comandos-y-apuntes.git
```

5. Ejecutar el push:

```bash
git branch -M main
git push -u origin main
```

## 3. Flujo Diario (Ramas de Trabajo)

Regla de oro: Nunca trabajes directamente sobre main.

### Paso A: Crear una rama para la tarea

```bash
git checkout -b feature/nombre-de-la-mejora
```

### Paso B: Ciclo de cambios (Commits Atómicos)
Haz cambios pequeños y lógicos.

```bash
git status                    # Revisa qué cambió
git diff                      # Mira los cambios línea por línea
'git add <archivo>'             # Prepara el archivo
'git commit -m "fix: mensaje"'  # Guarda con un mensaje descriptivo
```

### Paso C: Sincronizar con la nube (Backup)

```bash
git push origin feature/nombre-de-la-mejora
```

## 4. Finalizar y Fusionar (Merge)

Cuando tu tarea en la rama feature está lista y probada:

Volver a la rama principal: 

```bash
git checkout main
```

Actualizar local: 

```bash
git pull origin main #(Por si hay cambios de otra PC)
```

Fusionar cambios: 

```bash
git merge feature/nombre-de-la-mejora
```

Subir cambios: 

```bash
git push origin main
```

## 5. Glosario de Mensajes (Conventional Commits)
Usa estos prefijos para que tu historial sea legible:

* feat: Una nueva funcionalidad.
* fix: Corrección de un error.
* docs: Cambios solo en la documentación.
* style: Cambios de formato (espacios, puntos y comas, no afectan al código).
* refactor: Cambio de código que no corrige errores ni añade funciones.

Limpiar: 
'git branch -d feature/nombre-de-la-mejora'

## 6. Comandos de "Emergencia"

SituaciónComando
¿Qué hice? (Historial visual): 

```bash
git adog' (si configuraste el alias)
```

Me equivoqué en el mensaje del último commit

```bash
git commit --amend -m "nuevo mensaje"
```

Arruiné un archivo y quiero volver al último commit:

```bash
git checkout -- nombre_archivo
```

Quiero deshacer el último commit (manteniendo los archivos):

```bash
git reset --soft HEAD~1
```


