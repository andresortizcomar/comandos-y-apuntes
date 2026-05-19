# Configurar Ollama para VSCode
### Debería funcionar también para VsCodium

## 1. Tener instalado Ollama y los modelos necesarios

```
ollama pull qwen2.5-coder:3b

ollama pull qwen2.5-coder:1.5b

ollama pull qwen2.5-coder:1.5b-base

ollama pull nomic-embed-text:latest
```

## 2. En VsCode instalar la extesión 'Continue'

Una vez instalada se debe abrir la configuración de la extensión: en la rueda dentada esquina superior derecha.

Elegir en la barra vertical de la izquierda de Continue la opción "Configs" (el icono de una hoja).

Se abre el archivo "config.yaml"

Allí escribir esto:

```
name: Local Config
version: 1.0.0
schema: v1

models:
  - name: Qwen 3B Chat
    provider: ollama
    model: qwen2.5-coder:3b

  - name: qwen2.5-coder 1.5b
    provider: ollama
    model: qwen2.5-coder:1.5b
    roles:
      - apply
      - autocomplete
      - chat
      - edit  

tabAutocompleteOptions:
  debounceDelay: 500
  maxPromptTokens: 1024
  multilineCompletions: auto
```

## 3. Verificar la ventana de configuración de Continue

En la barra de configuración de Continue clic en "Models" (el icono de un cubo, es el primero).

Allí podremos ver los modelos que hemos configurado.

Desde config.yaml podremos agregar más modelos.