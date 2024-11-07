# Servidor LangChain

Este proyecto implementa un servidor FastAPI que utiliza LangChain para proporcionar un servicio de traducción. El servidor expone un único endpoint de API que acepta un texto junto con el idioma de destino y devuelve el texto traducido usando modelos de lenguaje de OpenAI.

## Arquitectura del Proyecto

La aplicación está construida usando FastAPI, LangChain y uvicorn para un servidor API simple pero potente.

## Componentes Clave

1. Servidor FastAPI: FastAPI se utiliza para crear los endpoints de API y manejar las solicitudes HTTP.
2. LangChain: Esta biblioteca permite el uso de procesamiento en cadena para modelos de lenguaje, simplificando el diseño de tareas complejas de lenguaje.
3. Modelo de Lenguaje de OpenAI: El modelo de lenguaje de OpenAI, especificado por ChatOpenAI, realiza la tarea de traducción de texto.
4. Plantilla de Prompt de LangChain: ChatPromptTemplate se usa para definir el prompt de traducción. La plantilla recibe el texto de entrada y el idioma de destin
5. Parser de Salida: StrOutputParser analiza la respuesta del modelo de lenguaje en un formato de cadena para facilitar la interpretación.


## Flujo de Trabajo

El flujo de una solicitud es el siguiente:

1. La Plantilla de Prompt se configura para generar una solicitud de traducción con espacios reservados para el idioma de destino y el texto.
2. El Modelo de Chat (ChatOpenAI) procesa la plantilla del prompt y genera una respuesta.
3. El Parser de Salida convierte la respuesta del modelo en una cadena, que se envía de vuelta al cliente.


## Flujo de la Aplicación

1. Inicialización de la Plantilla de Prompt: Se inicializa ChatPromptTemplate con un prompt que instruye al modelo a traducir el texto al idioma especificado.
2. Configuración de la Cadena: El objeto chain combina el prompt, el modelo y el parser en una secuencia ejecutable.
3. Adición de Rutas: La función add_routes de langserve crea dinámicamente una ruta de API en /chain, manejando solicitudes de traducción mediante HTTP.
4. Ejecución del Servidor: Al ejecutarse directamente, la aplicación inicia un servidor FastAPI en http://localhost:8000.

## Instalación

1. clonar el repositorio:

```
git clone <url_del_repositorio>
cd langchain-server

```
2. Instalar Requerimientos:
```
pip install -r requirements.txt

```

3. Configurar la Clave de API de OpenAI: Actualiza tu entorno con tu clave de API de OpenAI configurándola en el archivo .env o exportándola directamente:
```
export OPENAI_API_KEY='sk-tu-clave-de-api'
```

## Dependencias

* FastAPI: para crear la API.
* LangChain: para manejar prompts y cadenas con modelos de OpenAI.
* Uvicorn: servidor ASGI para ejecutar FastAPI.
* API de OpenAI: para traducción de lenguaje.


![image](https://github.com/user-attachments/assets/f82adef8-711e-4d3b-bd2f-1872ce152e54)


![image](https://github.com/user-attachments/assets/73a8f65c-3f55-4e66-ab13-8b922dec413d)
