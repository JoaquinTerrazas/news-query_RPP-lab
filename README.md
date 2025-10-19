# 📄 Sistema de Recuperación de Noticias de RPP con Embeddings

Este proyecto implementa un sistema de recuperación de información (Information Retrieval) que ingesta las últimas 50 noticias del feed RSS de RPP Noticias, genera embeddings semánticos para cada una y permite realizar búsquedas por similitud de texto. Todo el flujo está orquestado con LangChain.

---

###  Características Principales

* **Ingesta de Datos en Tiempo Real:** Se conecta al RSS de `rpp.pe` para obtener las noticias más recientes.
* **Embeddings Semánticos:** Utiliza el modelo `sentence-transformers/all-MiniLM-L6-v2` para convertir el texto de las noticias en vectores numéricos que capturan su significado.
* **Base de Datos Vectorial:** Almacena los documentos y sus embeddings en una base de datos `ChromaDB` en memoria para búsquedas ultra rápidas.
* **Búsqueda por Similitud:** Permite a un usuario ingresar una consulta en lenguaje natural (ej. "noticias de deportes") y devuelve las noticias más relevantes.
* **Orquestación con LangChain:** Todo el pipeline está encapsulado en componentes de LangChain, creando un flujo de trabajo modular y escalable.

---

###  Cómo Ejecutarlo

Sigue estos pasos para poner en marcha el proyecto en tu entorno local.

**1. Clonar el Repositorio**
```bash
git clone [https://github.com/JoaquinTerrazas/news-query_RPP-lab]
cd news-query_RPP-lab
```

**2. Crear y Activar un Entorno Virtual**
Se recomienda encarecidamente usar un entorno virtual para aislar las dependencias del proyecto.
```bash
# Crear el entorno
python -m venv venv

# Activar en Windows
.\venv\Scripts\activate

# Activar en macOS/Linux
source venv/bin/activate
```

**3. Instalar las Dependencias**
El archivo `requirements.txt` contiene todas las librerías necesarias.
```bash
pip install -r requirements.txt
```

**4. Ejecutar el Jupyter Notebook**
Abre el notebook ubicado en la carpeta `/notebooks` y ejecuta todas las celdas en orden.
```bash
jupyter notebook notebooks/rpp_news_retrieval.ipynb
```

---

###  Tecnologías Utilizadas

* **Python 3.10**
* **LangChain:** Para orquestar el pipeline de NLP.
* **ChromaDB:** Como base de datos vectorial en memoria.
* **SentenceTransformers:** Para la generación de embeddings.
* **Feedparser:** Para la lectura del feed RSS.
* **Pandas:** Para la manipulación y visualización de datos.
* **Tiktoken:** Para el análisis de tokens.
