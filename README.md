# HESPE-SPARK: Predicción Escalable del Rendimiento Académico 🚀

## 📝 Contexto del Problema

Este repositorio es una evolución del proyecto **HESPE (Higher Education Student Performance Evaluation)**, diseñado para enfrentar el desafío de analizar grandes volúmenes de datos de rendimiento estudiantil. Dado el éxito de los modelos predictivos iniciales, el estudio se ha expandido para incluir datos históricos masivos y de múltiples instituciones académicas.

El objetivo principal es **portar el modelo predictivo a un entorno de procesamiento distribuido utilizando Apache Spark**, permitiendo así un análisis escalable y eficiente que una máquina individual no podría manejar. El modelo busca predecir el resultado académico (variable "grade") de los estudiantes de ingeniería y ciencias de la Universidad de Wisconsin.

## 📊 Conjunto de Datos

El análisis utiliza un conjunto de datos que incluye:
* **145 instancias** (estudiantes).
* **33 características** que abarcan:
    * Información personal.
    * Entorno familiar.
    * Hábitos de estudio.

## 🚀 Metodología

El proyecto sigue un flujo de trabajo de Machine Learning adaptado para un entorno distribuido con Spark:

1.  **Preparación del Entorno**: Configuración de un entorno de Colab con Java y Spark para permitir el procesamiento de datos a gran escala.
2.  **Análisis Exploratorio de Datos (EDA) con PySpark**: Se realiza una exploración inicial para comprender la estructura de los datos. Esto incluye:
    * **Decodificación de Variables**: Traducción de las columnas y valores codificados a un formato legible para facilitar la interpretación.
    * **Visualización de Datos**: Creación de gráficos para analizar la distribución de variables demográficas y de comportamiento, y su correlación con las calificaciones.
3.  **Preprocesamiento de Datos**: Transformación de las características categóricas en un formato numérico que el modelo pueda procesar, utilizando `StringIndexer` y `VectorAssembler` de Spark ML.
4.  **Modelado Predictivo Escalable**:
    * Se entrenan dos de los modelos de clasificación más robustos y populares en el ecosistema de Spark: **Árbol de Decisión** y **Random Forest**.
    * **Optimización de Hiperparámetros**: Se utiliza `CrossValidator` para realizar una búsqueda exhaustiva de los mejores hiperparámetros, asegurando un rendimiento óptimo del modelo final.
5.  **Evaluación del Modelo**: El rendimiento de los modelos se mide utilizando métricas clave como `Accuracy`, `F1-Score`, `Precision` y `Recall`.

## 🏆 Resultados y Conclusiones

Tras el entrenamiento y la evaluación cruzada, el modelo de **Random Forest** demostró ser el más preciso para predecir el rendimiento académico de los estudiantes en este entorno escalable.

El modelo final ofrece una base sólida para predecir el éxito estudiantil a gran escala, permitiendo a la universidad tomar decisiones informadas y proactivas para apoyar a sus estudiantes.

## 🛠️ Tecnologías Utilizadas

* **Apache Spark**: Para el procesamiento distribuido y el machine learning escalable.
* **PySpark**: La API de Python para Spark.
* **Python 3**: Como lenguaje principal de programación.
* **Pandas & NumPy**: Para la manipulación de datos en la fase de análisis.
* **Matplotlib & Seaborn**: Para la generación de visualizaciones.
* **Spark MLlib**: Para la implementación de los modelos de aprendizaje automático.

## ⚙️ Cómo Replicar el Análisis

1.  **Abrir en Google Colab**:
    La forma más sencilla de ejecutar este proyecto es abrir el notebook directamente en Google Colab usando el siguiente enlace:
    [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](URL_DEL_NOTEBOOK_EN_COLAB)

2.  **Preparar los Datos**:
    Asegúrate de tener el archivo `hespe-data.csv` en tu entorno de Colab y de que la ruta del archivo esté correctamente especificada en el notebook.

3.  **Ejecutar las Celdas**:
    Ejecuta todas las celdas del notebook en orden para replicar el análisis completo, desde la configuración del entorno hasta la evaluación final del modelo.
