# Talleres - Procesamiento del Lenguaje Natural

Repositorio de **talleres** de la materia **Procesamiento del Lenguaje Natural** de la **Maestría en Inteligencia Artificial Aplicada** de la **Universidad Icesi** (Cali, Colombia).

---

## Contenido

Este repositorio agrupa los talleres y entregables prácticos del curso. Cada sesión puede incluir uno o más talleres con notebooks, datos y código listo para ejecutar y extender.

---

## Estructura

```
icesi_nlp/
├── README.md
├── Session 1/
│   └── Taller 1/
│       ├── AnalisisTexto.ipynb                   # Análisis de texto con spaCy
│       ├── 7-taller-sentiment-analysis.ipynb     # Análisis de sentimientos
│       ├── 7-SpamClasificationNLTK.ipynb         # Clasificación spam/ham con NLTK
│       ├── data/                                 # Datos (GameofThrones-mini.txt, sms_spam_collection, etc.)
│       ├── SMSSpamCollection.tsv                 # Dataset SMS Spam Collection
│       └── requirements.txt                      # Dependencias del taller
├── Session 2/
│   └── Taller/
│       └── Taller_NLP_Sesion_2_Emotion_Analysis.ipynb   # Análisis de emociones (LSTM)
└── Session 3/
    └── Taller/
        ├── taller3_transformers_from_scratch.ipynb     # Transformer desde (casi) cero, clasificación de emociones
        └── tokenizer_emotion/                           # Tokenizer guardado (opcional, para reproducibilidad)
```

- **Session N:** corresponde a la sesión del curso.
- **Taller / Taller M:** taller o práctica de esa sesión (notebooks, datos, `requirements` si aplica).

---

## Requisitos

- **Python** 3.10 (recomendado).
- **Jupyter** (o entorno que ejecute notebooks).
- Dependencias por taller: ver `requirements.txt` dentro de cada carpeta de taller (por ejemplo `Session 1/Taller 1/requirements.txt`). **Session 3** instala sus dependencias desde el propio notebook (PyTorch Lightning, `transformers`, `datasets`); también puede ejecutarse en Google Colab.

---

## Cómo empezar

1. Clonar el repositorio:
  ```bash
   git clone <url-del-repo>
   cd icesi_nlp
  ```
2. Crear un entorno virtual (recomendado):
  ```bash
   python -m venv .venv
   .venv\Scripts\activate   # Windows
   # source .venv/bin/activate   # Linux/macOS
  ```
3. Instalar dependencias del taller que vayas a usar, por ejemplo para Session 1 / Taller 1:
  ```bash
   pip install -r "Session 1/Taller 1/requirements.txt"
  ```
4. Descargar recursos NLTK (si el taller usa NLTK): dentro del notebook o en Python:
  ```python
   import nltk
   nltk.download('punkt')
   nltk.download('punkt_tab')
   nltk.download('stopwords')
   nltk.download('vader_lexicon')
  ```
5. Abrir el notebook desde Jupyter o VS Code y ejecutar las celdas en orden.

---

## Session 1 - Taller 1

### AnalisisTexto.ipynb

Análisis de texto con **spaCy**: procesamiento lingüístico, entidades nombradas, análisis sintáctico y más sobre textos de ejemplo. Usa el archivo `GameofThrones-mini.txt` como corpus.

### 7-taller-sentiment-analysis.ipynb

Análisis de sentimientos sobre reseñas o textos.

### 7-SpamClasificationNLTK.ipynb

- **Objetivo:** clasificación binaria (spam vs ham) usando NLTK para features y scikit-learn para el modelo.
- **Dataset:** [SMS Spam Collection](https://archive.ics.uci.edu/dataset/228/sms+spam+collection) (`SMSSpamCollection.tsv`).
- **Contenido:** tokenización, stopwords, FreqDist, bigramas (BigramCollocationFinder), VADER, heurísticas de formato; regresión logística y evaluación (métricas, matriz de confusión).

---

## Session 2 - Taller

### Taller_NLP_Sesion_2_Emotion_Analysis.ipynb

- **Objetivo:** clasificación de emociones en texto (6 clases: ira, miedo, alegría, amor, tristeza, sorpresa) usando un modelo LSTM.
- **Dataset:** Emotion (mensajes de Twitter en inglés), vía Hugging Face `datasets`.
- **Contenido:** preprocesamiento, tokenización, vocabulario, `Dataset`/`DataLoader`, bloque LSTM + clasificador, entrenamiento con PyTorch Lightning, evaluación y análisis de predicciones erróneas.

---

## Session 3 - Taller

### taller3_transformers_from_scratch.ipynb

- **Objetivo:** clasificación de emociones (6 clases: sadness, joy, love, anger, fear, surprise) con una arquitectura **Transformer** implementada desde (casi) cero (codificación posicional, multi-head attention, bloques Transformer, FFN).
- **Dataset:** [dair-ai/emotion](https://huggingface.co/datasets/dair-ai/emotion) (mensajes de Twitter en inglés).
- **Contenido:** tokenizador propio (WordPiece/BPE) entrenado sobre el corpus y guardado para reproducibilidad; embeddings + positional encoding (sinusoidal o aprendible); bloques de atención multicabeza y capas residuales; entrenamiento con PyTorch Lightning (deterministic, early stopping); evaluación con accuracy, F1, matriz de confusión (incl. porcentual) y análisis de errores. Compatible con ejecución local y en **Google Colab** (carga del tokenizer desde el repo sin clonar).
- **Reproducibilidad:** el tokenizer se guarda en `tokenizer_emotion/`; en ejecuciones posteriores se carga desde ahí para obtener resultados consistentes.

---

## Licencia

Ver archivo `LICENSE` en el repositorio, si aplica.

---

## Universidad Icesi

**Maestría en Inteligencia Artificial Aplicada**  
Procesamiento del Lenguaje Natural