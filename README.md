# Trabajos Prácticos - Procesamiento del Lenguaje Natural (NLP)

**Especialización en Inteligencia Artificial - Universidad de Buenos Aires (UBA)**

Este repositorio contiene los cuatro desafíos desarrollados para la materia de Procesamiento del Lenguaje Natural de la Especialización en Inteligencia Artificial de la Universidad de Buenos Aires.

## 📋 Contenido del Repositorio

### 🔍 [Desafío 1: Vectorización de Documentos y Clasificación](./desafio_1/)
**Archivo:** `Desafio_1.ipynb`

**Objetivos:**
- Vectorización de documentos usando TF-IDF
- Análisis de similaridad coseno entre documentos
- Implementación de clasificación por prototipos (zero-shot)
- Entrenamiento de modelos Naïve Bayes (Multinomial y Complement)
- Análisis de similaridad entre palabras mediante matriz término-documento

**Dataset:** 20 Newsgroups de sklearn

**Técnicas implementadas:**
- TF-IDF Vectorization
- Cosine Similarity
- Prototype-based Classification
- Multinomial Naive Bayes
- Complement Naive Bayes
- Document-term matrix transposition

**Resultados destacados:**
- Los documentos se agrupan coherentemente con su categoría temática
- La limpieza de texto mejora significativamente la representación semántica
- Las palabras relacionadas temáticamente aparecen como vecinas en el espacio vectorial

### 🎵 [Desafío 2: Word Embeddings con Gensim](./desafio_2/)
**Archivo:** `Desafio_2.ipynb`

**Objetivos:**
- Creación de embeddings personalizados con Word2Vec
- Análisis de relaciones semánticas en el espacio de embeddings
- Visualización de embeddings en 2D y 3D
- Interpretación de similitudes y diferencias entre palabras

**Dataset:** Corpus de letras de canciones de Eminem

**Técnicas implementadas:**
- Word2Vec (Skip-gram model)
- t-SNE para reducción de dimensionalidad
- Visualización interactiva con Plotly
- Análisis de similitud semántica

**Archivos de visualización generados:**
- `embeddings_2d.html` - Visualización 2D interactiva
- `embeddings_3d.html` - Visualización 3D interactiva

**Hallazgos principales:**
- Los embeddings capturan el uso específico del vocabulario en el contexto musical
- Las palabras se agrupan según el estilo y contexto particular del artista
- La visualización revela clusters temáticos específicos del corpus

### 🔮 [Desafío 3: Predicción de Próxima Palabra](./desafio_3/)
**Archivo:** `Desafio_3.ipynb`

**Objetivos:**
- Implementación de modelo de lenguaje para predicción de secuencias
- Entrenamiento de redes LSTM para generación de texto
- Evaluación con métrica de perplejidad
- Implementación de beam search para generación

**Dataset:** Corpus de letras de canciones de Eminem

**Arquitectura del modelo:**
- Embedding Layer (dimensión 5)
- 2 capas LSTM (64 unidades cada una) con Dropout
- Capa Dense para clasificación multiclase
- Función de pérdida: Sparse Categorical Crossentropy

**Técnicas implementadas:**
- Tokenización y padding de secuencias
- Arquitectura Encoder-Decoder con LSTM
- Teacher forcing durante entrenamiento
- Beam search para generación de texto
- Interfaz interactiva con Gradio

**Resultados:**
- Accuracy de entrenamiento: ~30%
- Accuracy de validación: ~17%
- El modelo captura patrones básicos pero requiere más datos para mejor generalización

### 🌐 [Desafío 4: Traductor Secuencia a Secuencia](./desafio_4/)
**Archivo:** `Desafio_4.ipynb`

**Objetivos:**
- Replicación de modelo traductor en PyTorch
- Experimentación con diferentes arquitecturas LSTM
- Evaluación del impacto del tamaño de capas recurrentes
- Implementación de embeddings pre-entrenados (GloVe)

**Dataset:** Corpus de traducción Español-Inglés (Anki/ManyThings)

**Modelos implementados:**
1. **Modelo Base:** LSTM de 128 unidades, 1 capa
2. **Modelo Expandido:** LSTM de 256 unidades, 1 capa  
3. **Modelo Profundo:** LSTM de 64 unidades, 5 capas

**Arquitectura:**
- **Encoder:** Embedding + LSTM 
- **Decoder:** Embedding + LSTM + Dense + Softmax
- **Embeddings:** GloVe pre-entrenados (50 dimensiones)
- **Optimizador:** Adam con diferentes learning rates

**Resultados comparativos:**
- **LSTM 128 unidades:** Accuracy validation ~71.7%, mejor rendimiento general
- **LSTM 256 unidades:** Accuracy validation ~71.3%, comportamiento estable
- **LSTM 64 unidades (5 capas):** Accuracy validation ~63.9%, no mejora con mayor profundidad

**Conclusiones:**
- El modelo de 128 unidades mostró el mejor balance rendimiento/estabilidad
- Mayor profundidad no necesariamente mejora el rendimiento
- Los embeddings pre-entrenados mejoran significativamente la representación

## 🛠 Tecnologías Utilizadas

### Librerías principales:
- **scikit-learn** - Vectorización, clasificación y métricas
- **gensim** - Word embeddings y Word2Vec
- **tensorflow/keras** - Redes neuronales y procesamiento de secuencias
- **pytorch** - Implementación de modelos seq2seq
- **plotly** - Visualizaciones interactivas
- **gradio** - Interfaces de usuario interactivas
- **numpy, pandas** - Manipulación de datos
- **matplotlib, seaborn** - Visualizaciones estáticas

### Datasets utilizados:
- **20 Newsgroups** (sklearn) - Clasificación de documentos
- **Corpus Eminem** - Word embeddings y generación de texto
- **Español-Inglés Anki** - Traducción automática

## 📊 Métricas y Evaluación

- **F1-Score macro** para clasificación
- **Accuracy** para modelos de secuencia
- **Perplejidad** para modelos de lenguaje
- **Similaridad coseno** para análisis de embeddings
- **Cross-entropy loss** para entrenamiento

## 🚀 Instrucciones de Uso

1. **Clonar el repositorio:**
```bash
git clone https://github.com/MaximilianoBernardo/ceia_nlp_tps.git
cd ceia_nlp_tps
```

2. **Instalar dependencias:**
```bash
pip install scikit-learn gensim tensorflow torch plotly gradio numpy pandas matplotlib seaborn
```

3. **Ejecutar notebooks:**
- Abrir cualquier archivo `.ipynb` en Jupyter Notebook/Lab
- Ejecutar las celdas secuencialmente
- Los datasets se descargan automáticamente

## 📈 Resultados Destacados

### Desafío 1 - Clasificación de Textos
- **Naïve Bayes Multinomial:** Rendimiento superior en clasificación de noticias
- **Similaridad semántica:** Agrupación coherente de documentos por temática

### Desafío 2 - Word Embeddings  
- **Visualización 2D/3D:** Clusters temáticos bien definidos
- **Relaciones semánticas:** Captura del vocabulario específico del artista

### Desafío 3 - Generación de Texto
- **Modelo LSTM:** Captura de patrones básicos del lenguaje
- **Beam Search:** Generación más diversa que greedy search

### Desafío 4 - Traducción Automática
- **Mejor configuración:** LSTM 128 unidades con 72% accuracy
- **Embeddings pre-entrenados:** Mejora significativa en representación

## 🎓 Contexto Académico

**Materia:** Procesamiento del Lenguaje Natural  
**Programa:** Especialización en Inteligencia Artificial  
**Universidad:** Universidad de Buenos Aires (UBA)  
**Autor:** Maximiliano Bernardo  

## 📄 Licencia

Este proyecto está bajo la Licencia Apache 2.0 - ver el archivo [LICENSE](LICENSE) para más detalles.

## 🤝 Contribuciones

Este repositorio es parte de un proyecto académico. Las sugerencias y mejoras son bienvenidas a través de issues o pull requests.

---

*Desarrollado como parte de los trabajos prácticos de la materia Procesamiento del Lenguaje Natural, Especialización en Inteligencia Artificial, Universidad de Buenos Aires.*