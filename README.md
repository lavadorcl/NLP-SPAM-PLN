
# NLP-SPAM-PLN

## 🌍 Trabajo Práctico: Modelado Secuencial y PLN para Problemas del Mundo Real

### 🌟 Objetivo General
Aplicar herramientas y modelos de procesamiento del lenguaje natural (PLN), tanto clásicos como basados en aprendizaje profundo, en un contexto real, utilizando PyTorch y TensorFlow.

---

## 🚀 Motivación del Problema
El objetivo fue abordar la clasificación de mensajes como *spam* o *no spam* mediante modelos de PLN, lo cual es clave en contextos de ciberseguridad, donde se busca prevenir fraudes y comunicaciones maliciosas.

---

## 📃 Descripción del Dataset
Se trabajó con un conjunto de datos etiquetado como `spam_train.csv`, compuesto por 100 frases anotadas manualmente:
- Etiqueta **0**: HAM (mensaje normal)
- Etiqueta **1**: SPAM

Distribución:
| Clase   | Train | Validation | Train (%) | Validation (%) |
|---------|-------|------------|------------|----------------|
| HAM (0) | 26    | 6          | 32.5%      | 30.0%          |
| SPAM (1)| 54    | 14         | 67.5%      | 70.0%          |

---

## 📚 Parte A: Preprocesamiento y Herramientas de PLN
- Se utilizó **spaCy** para:
  - Tokenización
  - Lematización
  - Extracción de etiquetas morfosintácticas (*POS tags*)
- Se generó una tabla de coincidencia entre las etiquetas obtenidas por spaCy y las extraídas por un modelo BERT especializado en POS en español (`mrm8488/bert-spanish-cased-finetuned-pos`).

---

## 🔬 Parte B: Evaluación con Modelo BERT
- Se utilizó el modelo `mrm8488/bert-spanish-cased-finetuned-pos` de Hugging Face para evaluar el etiquetado POS.
- Se compararon las etiquetas BERT con las de spaCy para medir la coincidencia porcentual.

---

## 📈 Parte C: Modelos Secuenciales con TensorFlow
Se implementaron dos modelos secuenciales:
- **LSTM** (TensorFlow/Keras)
- **GRU** (TensorFlow/Keras)

Resultados:
- Ambos modelos fueron entrenados por 10 épocas con *batch size* de 8.
- Se graficó la evolución de `accuracy` y `loss` para *train* y *validation*.

---

## 🧰 Parte D: Comparación entre Frameworks
- Se reimplementaron los modelos **LSTM** y **GRU** usando **PyTorch**.
- Se replicó el entrenamiento con los mismos datos y parámetros.
- Se graficaron los resultados para comparar rendimiento entre TensorFlow y PyTorch.

---

## 🧮 Análisis de Resultados
- Los modelos **GRU** y **LSTM** alcanzaron altas precisiones en entrenamiento.
- PyTorch mostró mayor estabilidad en las curvas de *validation loss*.
- El uso de `stratify=y` garantizó una división equilibrada entre clases.

---

## 🧠 Reflexión Crítica
- El uso combinado de herramientas clásicas (spaCy) y modernas (BERT, LSTM, GRU) permite una evaluación robusta en tareas de PLN.
- TensorFlow ofrece mayor integración para usuarios nuevos; PyTorch da mejor control y transparencia.
- Los modelos secuenciales son efectivos incluso con corpus reducidos, si se preprocesan correctamente.

---

## 📁 Archivos Incluidos
- `NLP_spam.ipynb`: Notebook completo con todas las partes.
- `spam_train.csv`: Dataset etiquetado.
- Gráficos generados en matplotlib.

---

## 💼 Autor
Trabajo académico realizado con fines educativos para la asignatura de PLN y aprendizaje profundo.
