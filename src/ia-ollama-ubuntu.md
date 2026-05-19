# Ollama en Ubuntu

## 1. Instalación

### Instalar Curl

```
sudo apt update && sudo apt install curl
```

### Instalar Ollama

```
curl -fsSL https://ollama.com/install.sh | sh
```

Responder a todo que sí

### Verificar la instalación

Esto da el estatus

```
sudo systemctl status ollama
```
Verás algo como:

* active (running) → está corriendo
* inactive (dead) → no está corriendo
* enabled → arrancará al inicio del sistema

## 2. Cheatsheet para Ollama

### Controlar el servicio

#### Iniciar Ollama
```
sudo systemctl start ollama
```

#### Reiniciar
```
sudo systemctl restart ollama
```

#### Deshabilitar inicio automático (no arrancará al encender PC)
```
sudo systemctl disable ollama
```
#### Habilitar inicio automático (que arranque siempre)
```
sudo systemctl enable ollama
```

### Modo bajo demanda
Para que no este consumiendo recursos

#### Deshabilitar inicio automático
```
sudo systemctl disable ollama
```

#### Apagarlo ahora si está corriendo
```
sudo systemctl stop ollama
```

## 3. Comandos básicos

### Gestión de modelos

ollama pull <modelo>	Descarga un modelo
ollama run <modelo>	Ejecuta chat interactivo
ollama run <modelo>     "prompt" Ejecuta una consulta única
ollama list	        Lista modelos descargados
ollama rm <modelo>	Elimina un modelo
ollama cp <origen> <destino>	Copia un modelo
ollama show <modelo>	 Muestra detalles del modelo

#### Ejemplos prácticos

##### Descargar modelo pequeño (recomendado para empezar)
```
ollama pull llama3.2:3b
```
##### Chat interactivo
```
ollama run llama3.2:3b
```

##### Consulta directa desde terminal
```
ollama run llama3.2:3b "¿Qué es Linux?"
```

##### Ver modelos instalados
```
ollama list
```
##### Eliminar modelo
```
ollama rm llama3.2:3b
```

## 4. Modelos recomendados

Modelo	Tamaño	RAM necesaria	Uso recomendado

llama3.2:3b		3GB	~4GB	Rápido, inglés

llama3.1:8b		8GB	~12GB	Calidad, inglés/español

mistral:7b		7GB	~10GB	Rendimiento balanceado

phi3:3.8b		3.8GB	~5GB	Muy rápido, código

gemma2:9b		9GB	~12GB	Calidad Google

deepseek-coder:6.7b	6.7GB	~9GB	Programación

#### Otros modelos
qwen2.5-coder:1.5b	el campeón de los modelos pequeños

phi3.5			de Microsoft entrenado con datos de alta calidad

qwen2.5-coder:7b	Superior a otros en su clase. Equilibrio velocidad/cerebro

deepseek-coder-v2:16b	Proyectos grandes y complejos

### Modelos para mi stack en VsCode+Ollama (2026-05-19)
```
ollama pull qwen2.5-coder:3b

ollama pull qwen2.5-coder:1.5b

ollama pull qwen2.5-coder:1.5b-base

ollama pull nomic-embed-text:latest
```
