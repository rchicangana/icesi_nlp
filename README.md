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
└── Session 1/
    └── Taller 1/
        ├── 7-taller-sentiment-analysis.ipynb   # Análisis de sentimientos
        ├── 7-SpamClasificationNLTK.ipynb        # Clasificación spam/ham con NLTK
        ├── SMSSpamCollection.tsv                # Dataset SMS Spam Collection
        └── requirements.txt                     # Dependencias del taller
```

- **Session N:** corresponde a la sesión del curso.
- **Taller M:** taller o práctica de esa sesión (notebooks, datos, `requirements` si aplica).

---

## Requisitos

- **Python** 3.10 (recomendado).
- **Jupyter** (o entorno que ejecute notebooks).
- Dependencias por taller: ver `requirements.txt` dentro de cada carpeta de taller (por ejemplo `Session 1/Taller 1/requirements.txt`).

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

### 7-taller-sentiment-analysis.ipynb
Análisis de sentimientos sobre reseñas o textos.

### 7-SpamClasificationNLTK.ipynb
- **Objetivo:** clasificación binaria (spam vs ham) usando NLTK para features y scikit-learn para el modelo.
- **Dataset:** [SMS Spam Collection](https://archive.ics.uci.edu/dataset/228/sms+spam+collection) (`SMSSpamCollection.tsv`).
- **Contenido:** tokenización, stopwords, FreqDist, bigramas (BigramCollocationFinder), VADER, heurísticas de formato; regresión logística y evaluación (métricas, matriz de confusión).

---

## Licencia

Ver archivo `LICENSE` en el repositorio, si aplica.

---

## Universidad Icesi

**Maestría en Inteligencia Artificial Aplicada**  
Procesamiento del Lenguaje Natural
