# Redes Neuronales V - Reconocimiento Facial con Redes Siamesas

Práctica de Deep Learning enfocada en el uso de Redes Neuronales Siamesas y Triplet Loss para la verificación de identidades faciales utilizando TensorFlow/PyTorch.

## 📋 Descripción de la Práctica
Se implementó una red siamesa con un encoder convolucional compartido para transformar imágenes de rostros (64x64, escala de grises) en embeddings de 64 dimensiones. El objetivo es evaluar si las representaciones aprendidas acercan imágenes de la misma persona y separan las de identidades distintas.

Se aplicaron conceptos clave como:
*   **Triplet Loss** (Anchor, Positive, Negative).
*   **Few-shot Learning** mediante el uso de prototipos (promedio de embeddings).
*   **Similitud Coseno** y Distancia Euclidiana.

## 🛠️ Tecnologías Utilizadas
*   Python 3
*   PyTorch (Creación de la red y cálculos de embeddings)
*   NumPy y PIL (Preprocesamiento de imágenes)
*   Matplotlib (Visualización de matrices y similitudes)
*   Google Colab (Entorno de ejecución)
*   python-docx (Generación del informe final)

## 📂 Estructura del Repositorio
*   `notebooks/`: Contiene el cuaderno de Google Colab (`.ipynb`) con todo el código ejecutado paso a paso.
*   `persona_01/`: Imagenes utilizadas para el entrenamiento de la persona 1
*   `persona_02/`: Imagenes utilizadas para el entrenamiento de la persona 2
*   `docs/`: Documento en PDF/Word con el informe detallado de la práctica.
*   `README.md`: Este archivo.

## 🚀 Resultados y Conclusiones
1.  **Preprocesamiento crítico:** La escala de grises y el recorte central (ImageOps) son vitales para estandarizar las fotos antes de la CNN.
2.  **Prototipos:** El enfoque Few-shot (promediar dos fotos de referencia) demostró ser más robusto que comparar contra una sola imagen.
3.  **Diferencia de dominio:** Entrenar con datos sintéticos y probar con fotos reales evidenció limitaciones; el modelo logra clasificar en pruebas pequeñas, pero un sistema real requiere *fine-tuning* con datasets faciales masivos (ej. LFW, CelebA).
