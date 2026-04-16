# MODELO DE REGRESION LINEAL
## 1. Introducción

La contaminación del aire es un problema ambiental de gran impacto en la salud y los ecosistemas. El monóxido de carbono (CO) es uno de los contaminantes más relevantes, especialmente en zonas urbanas, y puede influir significativamente en la calidad del aire.

El Índice de Calidad del Aire (AQI) permite medir el nivel de riesgo asociado a la contaminación. En este estudio se analiza la relación entre la concentración máxima diaria de CO (promedio móvil de 8 horas) y el valor diario del AQI mediante un modelo de regresión lineal, además de comparar los años 2022 y 2023 para identificar posibles variaciones entre ambos periodos.




## 2. Metodología
### 2.1 Descripción y preparación de los datos
Se emplearon registros correspondientes a los años 2022 y 2023. Ambos conjuntos de datos fueron integrados en una única base con la finalidad de incrementar el número total de observaciones, mejorar la estabilidad estadística del modelo y permitir análisis comparativos entre periodos anuales.
Posteriormente, se seleccionaron específicamente las siguientes variables:
	Variable independiente (X):
Daily Max 8-hour CO Concentration 
	Variable dependiente (y):
Daily AQI Value 
La selección de estas variables responde al interés de evaluar el grado de influencia que la concentración de monóxido de carbono ejerce sobre el índice general de calidad del aire.
Antes del modelamiento, se realizó un análisis estadístico descriptivo utilizando el método describe(), el cual permitió obtener medidas de tendencia central (media), dispersión (desviación estándar), así como valores extremos y cuartiles. Este análisis preliminar facilitó la comprensión del comportamiento y variabilidad de los datos.

### 2.2 División del conjunto de datos
Con el fin de analizar el desempeño predictivo del modelo, el conjunto de datos se dividió en dos partes utilizando la función train_test_split(): el 80% de los registros se destinó al entrenamiento y el 20% restante a la evaluación.

Esta metodología permite ajustar el modelo con una parte de la información disponible y, posteriormente, medir su rendimiento sobre datos que no fueron utilizados durante el entrenamiento, lo que contribuye a disminuir el riesgo de sobreajuste (overfitting) y mejora la validez de los resultados.
________________________________________
### 2.3 Modelo de regresión lineal
Se implementó un modelo de regresión lineal simple utilizando la clase LinearRegression de la biblioteca sklearn.linear_model.  

El modelo se ajusta a la siguiente expresión matemática:

$$
y = \beta_0 + \beta_1 x + \varepsilon
$$

donde:

- $y$ representa el valor del AQI  
- $x$ corresponde a la concentración máxima diaria de CO  
- $\beta_0$ es la ordenada al origen  
- $\beta_1$ es el coeficiente de regresión  
- $\varepsilon$ es el término de error  

Posteriormente, se realizaron predicciones sobre el conjunto de prueba y se evaluó el desempeño del modelo mediante dos métricas:

- Coeficiente de determinación ($R^2$)  
- Error cuadrático medio (MSE)

## 3. Resultados obtenidos

variables que se usaron en el modelo en este caso del 2022

<img width="573" height="338" alt="image" src="https://github.com/user-attachments/assets/9007e93c-3d39-49be-8f1b-b04591e1e3ed" />

este es del 2023

<img width="580" height="363" alt="image" src="https://github.com/user-attachments/assets/b12fbf2c-1778-4eed-8c68-95ef2e5ce325" />

### resultados
<img width="726" height="565" alt="image" src="https://github.com/user-attachments/assets/ce62aa25-2e52-4ffd-9929-02f9b04ce8ab" />

El modelo de regresión lineal arrojó los siguientes resultados:

## R² = 0.9914 
  
## MSE = 0.1078 
  
El coeficiente de determinación obtenido, $R^2 = 0.9914$, señala que aproximadamente el 99.14% de la variación observada en el valor diario del AQI es explicada por la concentración máxima diaria de CO en un promedio móvil de 8 horas. Este resultado evidencia una relación lineal muy sólida entre ambas variables.

Asimismo, el error cuadrático medio ($MSE = 0.1078$) indica que el nivel de error en las predicciones es bajo, lo que implica que las estimaciones del modelo se aproximan considerablemente a los valores reales observados.

Respecto a la comparación entre los años 2022 y 2023, se identificaron tendencias similares en la relación entre las variables analizadas. No obstante, podrían presentarse diferencias en los niveles promedio de concentración y en la variabilidad anual, posiblemente asociadas a factores ambientales, regulatorios u otras condiciones externas.



## 5. Referencias
   


[1] U.S. Environmental Protection Agency, “Outdoor Air Quality Data – Download Daily Data,” AirData, EPA. Available: https://www.epa.gov/outdoor-air-quality-data/download-daily-data


[2] U.S. Environmental Protection Agency, “Data and Tools,” EPA. Available: https://www.epa.gov/data


[3] Q. Xia et al., “Indoor–Outdoor Detection Using Low-Cost Air Quality Sensors,” IEEE Sensors Journal, vol. 26, no. 5, pp. 7692–7705, 2026.
# link del trabajo de regresion en colab



https://colab.research.google.com/drive/1m0cLgGwtvCM67FoJIUW5I7kVDQCrcF-g?usp=sharing



