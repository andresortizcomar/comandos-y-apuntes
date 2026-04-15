# Estructura Ideal de Proyecto

nombre-del-proyecto/
├── 📁 .git/                # (Invisible) El corazón de Git
├── 📁 src/                 # Código fuente original (el que tú escribes)
├── 📁 assets/              # Recursos estáticos (imágenes, fuentes, iconos)
├── 📁 docs/                # Documentación, diagramas o notas de investigación
├── 📁 tests/               # Scripts de prueba (si los usas)
├── 📁 build/               # (Opcional) Archivos compilados o listos para subir
├── 📄 .env                 # Variables sensibles (¡NUNCA SE SUBE!)
├── 📄 .gitignore           # Lista de archivos que Git debe ignorar
├── 📄 README.md            # La cara del proyecto (instrucciones y qué es)
└── 📄 package.json/main.py # Archivos de configuración de dependencias

## 1. El Directorio src/ (Source)
Es la regla de oro. No dejes tus archivos .js, .py o .html en la raíz. Meterlos en src/ separa la configuración (archivos de la raíz) de la lógica (lo que está en src).

Beneficio Git: Si cambias algo de la lógica, el historial de Git mostrará claramente src/main.js, diferenciándolo de un cambio en el README.md.

## 2. El Directorio assets/
Aquí va todo lo que no es código pero el proyecto necesita para verse bien. Si el proyecto es muy grande, subdivide: assets/img/, assets/css/, assets/fonts/.

## 3. El Directorio docs/
Como vienes de las ciencias sociales, esta carpeta es vital. Aquí puedes guardar:

Borradores de ideas.

Documentación de la API.

Referencias o enlaces de interés.

Tip: Git ignora el contenido de los archivos pero rastrea los cambios. Es un lugar excelente para llevar un "diario de desarrollo".

## 4. Archivos de la Raíz (Root)
En la raíz solo deben vivir archivos de configuración y metadatos:

.gitignore: El portero.

README.md: Describe qué hace el proyecto, cómo se instala y cómo se corre.

LICENSE: Aunque sea privado, es buena práctica decidir bajo qué reglas vive el código.
