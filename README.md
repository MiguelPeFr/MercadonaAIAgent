# Mercadona AI Agent

Un chatbot inteligente diseñado para proporcionar información detallada sobre productos y comidas del supermercado Mercadona (incluye PDF del Dataset de todos los productos scrappeados), utilizando tecnología de procesamiento de lenguaje natural y búsqueda semántica.

## Características Principales

- **Procesamiento de PDFs**: Capacidad para cargar y procesar múltiples documentos PDF.
- **Base de Conocimiento Dinámica**: Creación de una base de conocimiento vectorial a partir de los documentos cargados.
- **Interfaz Intuitiva**: Interfaz de usuario amigable desarrollada con Streamlit.
- **Respuestas Contextuales**: Proporciona respuestas precisas basadas en el contexto de los documentos procesados.
- **Modelo de Lenguaje Avanzado**: Utiliza Deepseek 1.5B para generar respuestas coherentes y naturales.

## Requisitos Técnicos

- Python 3.x
- Ollama (para modelos de lenguaje y embeddings)
- Dependencias listadas en `requirements.txt`

## Instalación

1. Clonar el repositorio:
```bash
git clone [URL del repositorio]
cd MercadonaAIAgent
```

2. Crear y activar un entorno virtual:
```bash
python -m venv .venv
source .venv/bin/activate  # En Windows: .venv\Scripts\activate
```

3. Instalar las dependencias:
```bash
pip install -r requirements.txt
```

4. Asegurarse de tener Ollama instalado y los modelos necesarios:
   - nomic-embed-text (para embeddings)
   - deepseek-r1:7b (para generación de respuestas)

## Uso

1. Iniciar la aplicación:
```bash
streamlit run chatbot.py
```

2. En la interfaz web:
   - Subir documentos PDF relevantes usando el panel lateral
   - Hacer clic en "Create Knowledge Base" para procesar los documentos
   - Comenzar a hacer preguntas sobre los productos de Mercadona

## Arquitectura Técnica

### Componentes Principales

- **Procesamiento de Documentos**: Utiliza PDFPlumberLoader para extraer texto de PDFs
- **Vector Store**: Implementa Chroma DB para almacenamiento y recuperación eficiente de embeddings
- **Embeddings**: Utiliza el modelo nomic-embed-text para generar embeddings de texto
- **Modelo de Lenguaje**: Emplea Deepseek 7B para generar respuestas naturales
- **Interfaz de Usuario**: Desarrollada con Streamlit para una experiencia de usuario fluida

### Flujo de Datos

1. Los documentos PDF se cargan y procesan
2. El texto se divide en chunks manejables
3. Se generan embeddings para cada chunk
4. Los embeddings se almacenan en Chroma DB
5. Las consultas del usuario se procesan mediante búsqueda semántica
6. El modelo de lenguaje genera respuestas basadas en el contexto relevante

## Tecnologías Utilizadas

- **Frontend**: Streamlit
- **Backend**: Python
- **Procesamiento de Lenguaje Natural**: LangChain
- **Base de Datos Vectorial**: Chroma
- **Modelos de IA**: 
  - Deepseek 7B (LLM)
  - Nomic Embed Text (Embeddings)
- **Procesamiento de PDF**: PDFPlumber

## Contribución

Las contribuciones son bienvenidas. Por favor, asegúrate de:

1. Hacer fork del repositorio
2. Crear una rama para tu feature (`git checkout -b feature/AmazingFeature`)
3. Commit de tus cambios (`git commit -m 'Add some AmazingFeature'`)
4. Push a la rama (`git push origin feature/AmazingFeature`)
5. Abrir un Pull Request
