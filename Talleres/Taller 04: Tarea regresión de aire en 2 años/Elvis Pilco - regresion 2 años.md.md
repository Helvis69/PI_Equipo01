# Regresión lineal del índice de calidad del aire (AQI)

## 1. Introducción

La calidad del aire es un factor clave en la salud pública. Uno de los indicadores más utilizados para medirla es el **Air Quality Index (AQI)**, el cual se calcula a partir de la concentración de diversos contaminantes atmosféricos.

En este trabajo se analiza la relación entre la concentración de monóxido de carbono (CO) y el AQI, utilizando datos proporcionados por la Agencia de Protección Ambiental de los Estados Unidos (EPA). El objetivo principal es determinar si existe una relación lineal entre ambas variables mediante un modelo de regresión lineal.

---

## 2. Metodología

### 2.1 Fuente de datos

Los datos fueron obtenidos del portal oficial de la EPA, específicamente de la sección de calidad del aire. Se utilizaron registros correspondientes a los años 2024 y 2025 para distintas ciudades de Estados Unidos.

### 2.2 Variables

* Variable independiente (X):

  * Concentración máxima diaria de CO en 8 horas (ppm)
* Variable dependiente (y):

  * Índice de calidad del aire (AQI)

### 2.3 Preprocesamiento

* Se unieron los datasets de ambos años
* Se renombraron columnas para facilitar el análisis
* Se convirtieron los datos a formato numérico
* Se eliminaron valores nulos

### 2.4 Modelo

Se utilizó un modelo de regresión lineal simple implementado con la librería `scikit-learn`.

El modelo tiene la forma:

AQI = β₀ + β₁ · CO

Se dividieron los datos en:

* 70% para entrenamiento
* 30% para prueba


<img width="696" height="566" alt="image" src="https://github.com/user-attachments/assets/d635b363-0a18-40df-a022-97fdf42dd7b3" />

<img width="699" height="564" alt="image" src="https://github.com/user-attachments/assets/f77b4501-e6e3-4b73-bba7-afe677a313b8" />



## 3. Resultados

El modelo entrenado produjo los siguientes coeficientes:

* Intercepto (β₀): -0.2092
* Coeficiente (β₁): 11.5290

Por lo tanto, la ecuación del modelo es:

AQI = -0.2092 + 11.5290 · CO

### Interpretación

* El coeficiente β₁ indica que, por cada aumento de 1 ppm en la concentración de CO, el AQI aumenta aproximadamente en **11.53 unidades**.
* El intercepto es cercano a cero, lo cual es razonable ya que un valor de CO cercano a cero implicaría un AQI bajo.

---

## 4. Discusión

Los resultados muestran una **relación positiva fuerte** entre la concentración de monóxido de carbono y el índice AQI. Esto es consistente con la teoría, ya que el CO es uno de los contaminantes que contribuyen directamente al deterioro de la calidad del aire.

Sin embargo, es importante considerar que:

* El AQI no depende únicamente del CO, sino también de otros contaminantes como:

  * Ozono (O₃)
  * Material particulado (PM2.5, PM10)
  * Dióxido de nitrógeno (NO₂)

* Por lo tanto, el modelo es una **simplificación** de la realidad.

A pesar de esto, el modelo logra capturar una tendencia clara y puede ser útil para análisis preliminares.

---

## 5. Conclusiones

* Se encontró una relación lineal positiva entre CO y AQI.
* El modelo de regresión lineal permite predecir el AQI de manera aproximada.
* El coeficiente obtenido indica que el CO tiene un impacto significativo en la calidad del aire.
* Para mejorar el modelo, se podrían incluir más variables (regresión múltiple).

---

## 6. Referencias

[1] U.S. Environmental Protection Agency, “Outdoor Air Quality Data,” Disponible en: https://www.epa.gov/outdoor-air-quality-data

---
