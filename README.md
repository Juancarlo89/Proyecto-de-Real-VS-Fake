# Real vs Fake Face Detection - Proyecto de Machine Learning

Bienvenido al repositorio oficial del proyecto de clasificación de rostros (Imágenes Reales vs. Deepfakes). Este proyecto utiliza Redes Neuronales Convolucionales (CNN) para analizar y predecir la autenticidad de un dataset masivo de un millón de imágenes.

## 🏁 Sprint 1: Cimientos y Generación Masiva
**Duración:** 4 de mayo al 17 de mayo.
**Objetivo del Sprint:** Establecer el entorno técnico y producir el 60% del dataset equilibrado (50/50).

---

## Estructura y Equipos

### 1. DevOps / Infraestructura
Responsables de mantener la operabilidad del hardware, control de versiones y almacenamiento masivo.
* **Entorno de Desarrollo (Tarea 3):** Estandarizado en **Google Colab** para el aprovechamiento de GPUs en el entrenamiento de la CNN.
* **Almacenamiento (Tarea 2):** Gestión de 100GB-200GB de datos. Se utilizará **Kaggle Datasets** (u otra solución en la nube aprobada) para evitar descargas masivas en entornos locales.
* *Nota Crítica:* Mantener el control estricto del `.gitignore` para evitar saturar el repositorio de GitHub.

### 2. Data Quality (QA)
Responsables de la estandarización y sanidad de los datos.
* **Estándar de Imagen (Tarea 1):** Formato `.jpg` (ligero), resolución exacta de `224x224 px`, evaluando fondos neutros.
* **Limpieza y Filtrado (Tarea 6):** Ejecución de scripts para detección de duplicados o muestras extremadamente similares para evitar el *overfitting*.
* *Nota Crítica:* Auditar que la proporción del dataset se mantenga siempre en un 50% reales y 50% fakes.

### 3. Data Engineering
Responsables de la recolección y creación del volumen de datos.
* **Imágenes Reales (Tarea 5):** Implementación de Web Scraping y descarga de datasets públicos (CelebA, LFW). ¡No se toman fotos manualmente!
* **Imágenes Fake (Tarea 4):** Generación por lotes (*batches*) utilizando IA avanzada como StyleGAN3 o Modelos de Difusión.
* *Nota Crítica:* Trabajar en conjunto con QA para asegurar que las descargas/generaciones nazcan con el formato 224x224 px.

### 4. Model & Research
Responsables de la arquitectura predictiva y evaluación matemática.
* **Arquitectura (Tarea 7):** Diseño e investigación de Redes Neuronales Convolucionales (CNN) especializadas en detección facial.
* **Métricas de Éxito:** Más allá del *Accuracy*, el modelo se evaluará mediante:
  * Matriz de Confusión
  * Curva ROC
  * Precisión por clase
* *Nota Crítica:* Coordinar la arquitectura con DevOps para garantizar que pueda ser entrenada en el hardware disponible.

---

## Estructura del Repositorio (Directorios)

El código debe mantenerse organizado según el equipo y la tarea. Por favor, utilicen la siguiente estructura:

* `/data_pipeline/` -> Scripts de Data Engineering (Scraping, scripts de StyleGAN3).
* `/qa_tools/` -> Scripts de Data Quality (Redimensionado a 224x224, detectores de imágenes duplicadas).
* `/models/` -> Notebooks de Jupyter/Colab del equipo Model & Research (Pruebas de CNN, evaluación de métricas).
* `requirements.txt` -> Dependencias globales del proyecto (TensorFlow, PyTorch, OpenCV, etc.).
* `.gitignore` -> Reglas de exclusión de archivos.

## ⚙️ Reglas del Repositorio (Flujo de Trabajo Git)
1. **NO subir imágenes:** El `.gitignore` bloquea `.jpg`, `.png`, `.h5`, `.pt` y carpetas de datos.
2. **Ramas (Branches):** Trabajar en ramas específicas (ej. `qa/script-duplicados` o `data/scraper-celeba`).
3. **Pull Requests:** Todo código en `main` debe ser revisado antes de fusionarse.
