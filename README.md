# LLM Repositorio de rueba
repositorio de prueba para implementar llm y una aplicacion web 

## 1. Instalacion de Ollama 

Para instalar ollama debemos acceder a la pagina de [Ollama](https://ollama.com/download/linux), en una terminal se ejecuta el siguiente comando 
````bash 
$ curl -fsSL https://ollama.com/install.sh | sh 
````
## 1.1 para actualizar los datos los comandos son 
 git add .
 git commit -m "UPDATE README.md"
 git push -u origin main

## 2 Ejecutar el servidor 

una vez instalado se ejecuta el servidor ollama con el siguiente comando

````bash
$ ollama serve
````
## 3 Descargar algun modelo 
en la pagina de [modelos](https://ollama.com/library) de Ollama se busca el modelo deseado y de descarga con el siguiente comando:
````bash
$ ollama pull tinyllama
````

## 4 Prueba de request o la API rest 
para realizar una peticion basica a la API de ollama se sigue la siguiente estructura 

````bash
curl -X POST http://localhost:11434/api/generate -d '{
  "model": "tinyllama",
  "prompt": "Why is the sky blue?"
}' 
````


## 4.1 Consulta a la API rest sin stream
prueba de consulta sin stream

````bash
curl -X POST http://localhost:11434/api/generate -d '{
  "model": "tinyllama",
  "prompt": "Why is the sky blue?",
  "stream": false
}' 
````
## 5 realizar request a gruq

````bash
curl "https://api.groq.com/openai/v1/chat/completions" \
  -X POST \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer ${GROQ_API_KEY}" \
  -d '{
         "messages": [
           {
             "role": "user",
             "content": "¿Por qué el cielo es azul?"
           }
         ],
         "model": "gemma-7b-it",
         "stream": false
       }'
  ````