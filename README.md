# 🌤️ Proyecto de Predicción Meteorológica (Horaria y Diaria)

Este repositorio contiene un proyecto de predicción meteorológica utilizando datos históricos obtenidos mediante técnicas de **web scrapping** desde la **Agencia Estatal de Meteorología de España (AEMET)** y otras fuentes públicas. El objetivo es realizar predicciones precisas de variables meteorológicas a **nivel horario y diario**, utilizando distintos enfoques de modelado.

---

## 📊 Objetivo del Proyecto

### Predicción **Diaria**:
- **Predicción a 1 día** en el futuro.
- **Predicción a 7 días** en el futuro.

### Predicción **Horaria**:
- **Predicción a 1 hora** en el futuro.
- **Predicción a 24 horas** en el futuro.

---

## 🛠️ Preprocesamiento de los Datos

Antes del modelado, se aplicaron diversas transformaciones para mejorar la calidad de los datos:

- **Tratamiento de outliers** mediante técnicas estadísticas.
- **Imputación de valores faltantes** usando interpolaciones y modelos.
- **Eliminación de columnas innecesarias** o altamente correlacionadas.
- **Conversión de fechas** y generación de variables temporales (hora, día de la semana, estacionalidad).

---

## 🧠 Modelos Utilizados

Se han empleado varios tipos de modelos de predicción, tanto clásicos de series temporales como modelos supervisados:

### 1. **SARIMAX (Seasonal ARIMA with Exogenous Variables)**

SARIMAX es una extensión del modelo ARIMA que permite capturar:

- **Tendencia y estacionalidad** de las series temporales.
- Incorporación de **variables exógenas** (por ejemplo: presión, viento, humedad).
- **Modelado estocástico**, ideal para datos con ruido y patrón periódico.

Especificación del modelo:  
ARIMA(p, d, q) × (P, D, Q, s)

- `p`, `d`, `q`: orden del modelo autoregresivo, diferenciación e innovación.
- `P`, `D`, `Q`, `s`: componentes estacionales.

### 2. **Modelos regresivos con Skforecast**

[Skforecast](https://github.com/JoaquinAmatRodrigo/skforecast) es una librería basada en scikit-learn diseñada para aplicar **modelos de regresión a series temporales**. Sus ventajas incluyen:

- Uso de **lags** como variables predictoras.
- Fácil integración con regresores clásicos (LinearRegression, RandomForest, etc).
- Soporte para predicción **multi-step**.

### 3. **Modelos de Machine Learning**

También se han utilizado modelos supervisados para la predicción de variables meteorológicas:

- **Modelos de regresión lineal** para relaciones simples.
- **Modelos de árboles** como Random Forest y Gradient Boosting para capturar relaciones no lineales y complejas.

---

## 📈 Visualización de Resultados

Para facilitar la interpretación y análisis, se ha desarrollado un **dashboard en Power BI** que permite:

- Visualizar el histórico de datos meteorológicos.
- Explorar resultados de predicción en diferentes ventanas temporales.
- Comparar modelos y métricas de error (MAE, RMSE, etc).
- Analizar patrones estacionales y anomalías.

---

