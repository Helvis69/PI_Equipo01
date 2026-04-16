# Regresión lineal aplicada a datos de calidad del aire (EPA)

## 1. Introducción

La calidad del aire es un factor crítico en la salud pública y en la evaluación de entornos urbanos. El **Air Quality Index (AQI)** es un indicador ampliamente utilizado que sintetiza el impacto de diferentes contaminantes atmosféricos sobre la salud humana.

En este trabajo se analiza la relación entre la concentración de monóxido de carbono (CO) y el AQI utilizando datos de la Agencia de Protección Ambiental de Estados Unidos (EPA). El objetivo es construir un modelo de regresión lineal que permita **predecir el AQI a partir de variables ambientales**, específicamente la concentración de CO.

Este enfoque se alinea con investigaciones recientes que destacan el uso de datos de calidad del aire junto con técnicas de aprendizaje automático para inferir información del entorno. Por ejemplo, Indoor–Outdoor Detection Using Low-Cost Air Quality Sensors demuestra que variables como CO, temperatura y material particulado pueden ser utilizadas eficazmente para caracterizar entornos y realizar predicciones mediante modelos de machine learning.

---

## 2. Objetivo del modelo

El objetivo del modelo es:

 **Predecir el valor del AQI (calidad del aire) a partir de la concentración de CO**

Esto implica:

* Identificar si existe una relación lineal entre CO y AQI
* Cuantificar cuánto influye el CO en el AQI
* Evaluar la capacidad predictiva del modelo

El modelo utilizado es:

AQI = β₀ + β₁ · CO

Donde:

* AQI → variable objetivo
* CO → variable explicativa
* β₀ → intercepto
* β₁ → impacto del CO

---

## 3. Metodología

### 3.1 Datos

Se utilizaron datos de la EPA correspondientes a los años 2024 y 2025, del estado New York de EE.UU.

Variables principales:

* CO (ppm)
* AQI

### 3.2 Preprocesamiento

* Unión de datasets de ambos años
* Conversión de variables a formato numérico
* Eliminación de valores nulos
* Limpieza de columnas irrelevantes

### 3.3 Modelo

Se utilizó un modelo de regresión lineal simple (`LinearRegression`) con:

* 70% datos de entrenamiento
* 30% datos de prueba

---

## 4. Resultados

El modelo entrenado produjo:

* Intercepto (β₀): **-0.2092**
* Coeficiente (β₁): **11.5290**

### Modelo final:

AQI = -0.2092 + 11.5290 · CO

### Interpretación

* Por cada aumento de **1 ppm de CO**, el AQI aumenta aproximadamente en **11.53 unidades**
* Existe una **relación positiva fuerte** entre CO y calidad del aire

---

## 5. Visualización

### 5.1 Relación entre CO y AQI

```python
sns.scatterplot(x=df["CO"], y=df["AQI"])
plt.title("Relación entre CO y AQI")
plt.show()
```

<img width="700" height="559" alt="imagen" src="https://github.com/user-attachments/assets/0de3fa92-a779-47b1-8b2b-79c789ce02ba" />

Muestra una tendencia creciente (relación lineal positiva)

---

### 5.2 Valores reales vs predichos

```python
plt.scatter(y_test, pred)
plt.xlabel("AQI real")
plt.ylabel("AQI predicho")
plt.title("Predicción del modelo")
plt.show()
```

<img width="1465" height="312" alt="imagen" src="https://github.com/user-attachments/assets/5c6e31cb-fc14-41e3-8d34-88e209918da0" />

Permite evaluar qué tan bien el modelo predice

---

### 5.3 Distribución de residuos

```python
sns.histplot(y_test - pred, kde=True)
plt.title("Residuos del modelo")
plt.show()
```

<img width="701" height="557" alt="imagen" src="https://github.com/user-attachments/assets/d5abf24c-b7f1-40e9-a57a-6a264ed13359" />

Idealmente distribución normal centrada en 0

---

## 6. Discusión

Los resultados obtenidos son consistentes con la literatura científica.

El artículo Indoor–Outdoor Detection Using Low-Cost Air Quality Sensors señala que:

* El CO es una de las variables más relevantes en el análisis de calidad del aire
* Las variables ambientales presentan correlaciones significativas con indicadores como AQI
* El uso de modelos de machine learning permite capturar relaciones entre contaminantes y condiciones ambientales

Además, el estudio destaca que:

> Las variables como CO, NO₂ y PM2.5 son altamente informativas para modelar condiciones ambientales.

Esto respalda el enfoque de este trabajo, donde se utiliza CO como predictor principal.

Sin embargo, el modelo presenta limitaciones:

* El AQI depende de múltiples contaminantes, no solo CO
* Existe variabilidad ambiental (clima, tráfico, ubicación)
* El modelo es una simplificación de un sistema complejo

---

## 7. Conclusiones

-  Se encontró una relación lineal positiva entre CO y AQI
- El modelo permite predecir el AQI de manera aproximada
- El CO tiene un impacto significativo en la calidad del aire
- El uso de machine learning en datos ambientales es una herramienta válida y efectiva

---

## 8. Referencias (IEEE)

[1] Q. Xia et al., “Indoor–Outdoor Detection Using Low-Cost Air Quality Sensors,” IEEE Sensors Journal, vol. 26, no. 5, pp. 7692–7705, 2026.

[2] U.S. Environmental Protection Agency, “Outdoor Air Quality Data.” Disponible en: https://www.epa.gov/outdoor-air-quality-data

[3] Link de código: https://colab.research.google.com/drive/1m258hGpFJ7bJ7v7sVHWcP3at2K-Ojxt6#scrollTo=d97106ae 
