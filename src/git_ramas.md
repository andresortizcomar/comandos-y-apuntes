# GIT Ramas, trabajar en ella

1. Crear la rama y "saltar" a ella
Actualmente estás en main. Vamos a crear una rama llamada experiment-notes y nos pasaremos a ella.

```bash
# Crea la rama y te mueve a ella al mismo tiempo
git checkout -b rama_1
```

2. Hacer cambios en la línea temporal alternativa
Ahora que estás en tu "universo paralelo", crea un archivo nuevo o modifica uno existente.

Ahora, guarda este cambio en el historial de esta rama:

```bash
git add .
git commit -m "docs: agregando apuntes sobre branches"
```

3. El momento "Misterio" (El salto entre dimensiones)
Aquí es donde Git parece magia. Vamos a volver a la rama principal y verás que el archivo que acabas de crear desaparece de tu carpeta.

```bash
# Vuelve a la rama principal
git checkout main
```

Mira tu carpeta src/: El archivo ramas-git.md no está. No entres en pánico, está a salvo en la otra rama.

4. Fusionar (Merge)
Si ya decidiste que esos apuntes están bien y quieres que formen parte de tu bitácora oficial, debes traer los cambios de experiment-notes hacia main.

```bash
# Asegúrate de estar en main (ya lo estamos por el paso anterior)
# Ahora "absorbe" la rama experimental
git merge experiment-notes
```

5. Limpieza y push

Una vez que fusionaste, la rama experimental ya no es necesaria (aunque podrías dejarla si quieres).

```bash
# Borra la rama local (opcional)
git branch -d experiment-notes

# Sube todo a GitHub
git push origin main
```


