# Sistema de RAG con Langchain y Groq

Este proyecto implementa un sistema de Generación Aumentada por Recuperación (RAG) utilizando Langchain, Groq y FAISS para interactuar con documentos PDF.

El sistema permite realizar preguntas sobre el contenido de un documento PDF y obtener respuestas generadas por un modelo de lenguaje (LLM) de Groq, basadas en la información recuperada del documento.

## Contenido del Notebook

El notebook de Jupyter (`nombre_del_notebook.ipynb` - *reemplazar con el nombre real*) guía a través de los siguientes pasos:

1.  **Instalación de Dependencias:** Instala las librerías necesarias como `groq`, `langchain_community`, `pypdf`, `langchain-huggingface`, `faiss-cpu`, y `langchain-groq`.
2.  **Configuración de APIs:** Configura la clave API de Groq.
3.  **Carga y Preprocesamiento del Documento:** Carga un archivo PDF (`gauss_fields.pdf`) utilizando `PyPDFLoader` y lo divide en fragmentos (`chunks`) con `RecursiveCharacterTextSplitter`.
4.  **Creación de Embeddings:** Utiliza un modelo de embeddings de Hugging Face (`sentence-transformers/all-MiniLM-L6-v2`) para crear representaciones vectoriales de los fragmentos de texto.
5.  **Configuración y Población del Vector Store:** Inicializa un vector store FAISS y añade los embeddings de los chunks.
6.  **Configuración del Modelo de Lenguaje:** Carga un modelo de lenguaje de Groq (`llama3-70b-8192`) utilizando `ChatGroq`.
7.  **Creación de la Cadena RAG:** Define una cadena RAG que combina el retriever (para buscar información relevante en el vector store) con el LLM (para generar la respuesta basada en el contexto recuperado).
8.  **Pruebas del Sistema RAG:** Demuestra cómo realizar consultas al sistema RAG y obtener respuestas basadas en el contenido del PDF.
9.  **Interfaz con Gradio (Opcional):** Muestra cómo crear una interfaz web simple utilizando Gradio para interactuar con el sistema RAG.

## Cómo usar el Notebook

1.  **Clonar el Repositorio:** Clona este repositorio en tu entorno local o en Google Colab.
2.  **Abrir el Notebook:** Abre el archivo `nombre_del_notebook.ipynb` en Jupyter Notebook, JupyterLab o Google Colab.
3.  **Obtener Clave API de Groq:** Necesitarás una clave API de Groq. Cárgala de forma segura (por ejemplo, usando Google Colab Secrets o variables de entorno).
4.  **Ejecutar las Celdas:** Ejecuta cada celda del notebook secuencialmente. Asegúrate de cargar tu archivo PDF en la ubicación especificada en el código (`/content/gauss_fields.pdf`).
5.  **Interactuar:** Una vez que la cadena RAG esté configurada, puedes usar las celdas de prueba para hacer preguntas sobre el contenido del PDF o ejecutar la interfaz de Gradio.

## Requisitos

*   Python 3.7+
*   Librerías listadas en las secciones de instalación del notebook.

Este proyecto es un ejemplo básico de cómo construir un sistema RAG. Puede ser extendido para manejar diferentes formatos de documentos, utilizar otros modelos de embeddings o LLMs, e integrarse en aplicaciones más complejas.
