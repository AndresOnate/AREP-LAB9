# TALLER LLM 

En este taller se implementaron programas en Python desarrollados para los desafíos de LangChain utilizando LangChain, Pinecone y OpenAI.


## Guía de Inicio

Las siguientes instrucciones le permitirán descargar una copia y ejecutar la aplicación en su máquina local.

### Prerrequisitos

- Python
- Git

1. Ubíquese sobre el directorio donde desea realizar la descarga y ejecute el siguiente comando:

```shell script
  git clone https://github.com/AndresOnate/AREP-LAB9.git
```
2. Navegue al directorio del proyecto:

```shell script
  cd AREP-LAB9
```

3. Ejecute el siguiente comando para instalar los paquetes de Python requeridos:

```shell script
  pip install -r requirements.txt
```

4. Cada programa puede ejecutarse directamente utilizando Python. Por ejemplo:
```shell script
  python prompt_chatgpt.py
```

5. En la mayoría de los programas debe suministrar un OPENAI_API_KEY.


## Challenges

### Enviar mensajes a Chatgpt y recuperar respuestas.

En este desafío, implementamos un programa en Python para interactuar con el modelo de lenguaje GPT de OpenAI a través de la plataforma `LangChain`. Utilizaremos la biblioteca langchain para configurar un modelo de cadena (LLMChain) y enviar consultas al modelo de OpenAI. Nuestro objetivo es enviar preguntas al modelo y recuperar las respuestas generadas.
El programa comienza estableciendo la clave de API de OpenAI en la variable de entorno OPENAI_API_KEY. Luego, creamos un template de prompt que contiene una plantilla con el formato de la pregunta y la respuesta esperada. Utilizaremos esta plantilla para estructurar nuestras consultas y respuestas.Después de configurar el prompt y el modelo de OpenAI, creamos una instancia de LLMChain con estos componentes. Esta cadena nos permite enviar preguntas al modelo y obtener respuestas generadas.

Para el experimento enviamos la pregunta "¿Qué es el problema de los tres cuerpos?" al modelo utilizando el método run() de la cadena. El modelo procesa la pregunta y genera una respuesta, que luego se imprime en la consola.

![image](https://github.com/AndresOnate/AREP-LAB9/assets/63562181/f435d253-fe11-4832-a252-7326fe162fb7)

### RAG simple utilizando una base de datos de vectores en memoria.

En este desafío, cargamos una página web (`https://lilianweng.github.io/posts/2023-06-23-agent/`) para extraer documentos relevantes que sirven como contexto. Utilizamos estos documentos para construir una base de datos de vectores en memoria y luego implementamos un sistema de generación de respuestas asistido por recuperación (RAG) utilizando ChatGPT. Este sistema permite generar respuestas coherentes basadas en el contexto proporcionado por los documentos extraídos.

Para el experimento enviamos la pregunta "What is Task Decomposition?". La cadena recupera documentos relevantes, genera una respuesta utilizando ChatGPT y la imprime en la consola.

![image](https://github.com/AndresOnate/AREP-LAB9/assets/63562181/1755c4bb-e7de-4ed9-9fbe-ca07cc802f2b)

### RAG Utilizando Pinecone para almacenamiento de vectores


En este desafío, hemos implementado un programa en Python que utiliza un archivo de texto llamado `Conocimiento.txt` como fuente de información . Primero, el script carga este archivo de texto utilizando la función `loadText()`, la cual utiliza un cargador de documentos de texto de LangChain para obtener los documentos relevantes. Luego, los documentos se dividen en fragmentos de texto y se convierten en representaciones vectoriales utilizando embeddings de OpenAI. Posteriormente, construimos un índice en Pinecone para almacenar y recuperar eficientemente estos vectores:

![image](https://github.com/AndresOnate/AREP-LAB9/assets/63562181/491b0a0c-3f77-4c4b-ac2a-4cf45fa4e7ef)


La función `search()` se encarga de realizar consultas  utilizando Pinecone para recuperar documentos relevantes. Finalmente, el contenido del documento más relevante se muestra como respuesta a la pregunta planteada. De esta manera, el script utiliza el archivo de texto en conjunto con Pinecone para mejorar la eficiencia y precisión del proceso de generación de respuestas.

Para este experimento, enviamos la pregunta `What role did H.P. Lovecraft play in popularizing cosmic horror, and how has he influenced other writers and artists in the genre?` al sistema.

![image](https://github.com/AndresOnate/AREP-LAB9/assets/63562181/22c300cd-8a91-4253-8dc7-8aba4b198731)

### RAG para código

En este desafío, hemos implementado un programa en Python que utiliza `LangChain` para realizar análisis de código y generar respuestas automáticas a partir de consultas sobre el código fuente. El programa comienza clonando un repositorio de GitHub que contiene la base de conocimiento. Luego, carga los documentos del repositorio y los divide en fragmentos de texto. Utiliza Chroma para crear una base de datos de vectores a partir de estos fragmentos de texto y configura un recuperador para buscar en la base de datos. Se emplea un modelo de lenguaje ChatOpenAI para analizar las conversaciones. Se establecen plantillas de prompts para interactuar con el modelo de lenguaje y el recuperador. Finalmente, se crea una cadena de recuperación de información y se realizan preguntas específicas sobre el código cargado:

Para este experimento, enviamos las preguntas:

`What classes are derived from the Runnable class?`
`What one improvement do you propose in code in relation to the class hierarchy for the Runnable class?`

![image](https://github.com/AndresOnate/AREP-LAB9/assets/63562181/04b0c849-4523-429c-9be0-75dbd26276e5)

## Autores 

- Andrés Camilo Oñate Quimbayo

## Versión
1.0.0
