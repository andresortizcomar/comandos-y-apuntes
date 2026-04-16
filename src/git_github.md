#Github de local a remoto

# 1. Instalación (en Ubuntu/Debian)

```bash
type -p curl >/dev/null || (sudo apt update && sudo apt install curl -y)
curl -fsSL https://cli.github.com/packages/githubcli-archive-keyring.gpg | sudo dd of=/usr/share/keyrings/githubcli-archive-keyring.gpg
sudo chmod go+r /usr/share/keyrings/githubcli-archive-keyring.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null
sudo apt update
sudo apt install gh -y
```

# 2. Autenticación (Solo una vez)
Vincular la cuenta

```bash
gh auth login
```

Sigue las instrucciones: 
elige GitHub.com, HTTPS y la opción de loguearte vía navegador (te pedirá un código de 8 dígitos que aparecerá en la terminal).

# 3. El Comando para crear el repositorio
Para crear el repositorio en GitHub directamente desde tu carpeta local, ejecuta:

```bash
gh repo create nombre-de-tu-repo --public --source=. --remote=origin --push
# si queremos que sea privado
gh repo create nombre-de-tu-repo --private --source=. --remote=origin --push
```

¿Qué hace este comando exactamente?

* nombre-de-tu-repo: El nombre que tendrá en la nube.
* --public: Lo hace público (puedes usar --private si prefieres).
* --source=.: Indica que el código fuente es la carpeta actual.
* --remote=origin: Configura automáticamente el "remoto" en tu Git local.
* --push: Sube tus commits locales inmediatamente después de crear el repo.

# 4. Trabajo normal

Utilizar el habitual
```bash
git push
# o
git pull
```


