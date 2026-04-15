# 🚀 Git Survival Guide - Flujo de Trabajo Profesional

Este documento sirve como referencia rápida para mantener un historial de código limpio, seguro y organizado.

## 1. Configuración Inicial (Solo una vez)
Antes de empezar, asegúrate de que tus commits tengan tu firma:
```bash
git config --global user.name "Andrés Ortiz"
git config --global user.email "andresortiz.com.ar@gmail.com"

# Alias recomendado para ver el historial visualmente
git config --global alias.adog "log --all --decorate --oneline --graph"

## 2. Preparando un Proyecto Nuevo
1. Si tienes código suelto y quieres profesionalizarlo:

2. Inicializar: git init

3. Ignorar basura: touch .gitignore (Añade aquí .env, node_modules/, dist/, etc.)

### Primer guardado:

'git add .'
'git commit -m "feat: inicializar estructura del proyecto"'

4. Conectar a la nube:

'git remote add origin [https://github.com/usuario/repositorio.git](https://github.com/usuario/repositorio.git)'
'git branch -M main'
'git push -u origin main'

## 3. Flujo Diario (Ramas de Trabajo)

Regla de oro: Nunca trabajes directamente sobre main.

### Paso A: Crear una rama para la tarea

'git checkout -b feature/nombre-de-la-mejora'

### Paso B: Ciclo de cambios (Commits Atómicos)
Haz cambios pequeños y lógicos.

'git status'                    # Revisa qué cambió
'git diff'                      # Mira los cambios línea por línea
'git add <archivo>'             # Prepara el archivo
'git commit -m "fix: mensaje"'  # Guarda con un mensaje descriptivo

### Paso C: Sincronizar con la nube (Backup)

'git push origin feature/nombre-de-la-mejora'

## 4. Finalizar y Fusionar (Merge)

Cuando tu tarea en la rama feature está lista y probada:

Volver a la rama principal: 

'git checkout main'

Actualizar local: 

'git pull origin main' (Por si hay cambios de otra PC)

Fusionar cambios: 

'git merge feature/nombre-de-la-mejora'

Subir cambios: 

'git push origin main'

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

'git adog' (si configuraste el alias)

Me equivoqué en el mensaje del último commit

'git commit --amend -m "nuevo mensaje"'

Arruiné un archivo y quiero volver al último commit:

'git checkout -- nombre_archivo'

Quiero deshacer el último commit (manteniendo los archivos):

'git reset --soft HEAD~1'

