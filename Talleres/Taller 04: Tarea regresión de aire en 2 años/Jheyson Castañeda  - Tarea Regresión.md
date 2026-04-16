# REGRESION LINEAL
## 1. Introducción
La contaminación atmosférica constituye uno de los principales problemas ambientales a nivel global, debido a su impacto directo sobre la salud pública y los ecosistemas. Entre los diversos contaminantes presentes en la atmósfera, el monóxido de carbono (CO) destaca por su potencial efecto adverso en la calidad del aire, especialmente en zonas urbanas con alta actividad vehicular e industrial.
El Índice de Calidad del Aire (AQI, Air Quality Index) es un indicador estandarizado que sintetiza la concentración de distintos contaminantes en un valor numérico que refleja el nivel de riesgo para la población. En este contexto, analizar la relación entre la concentración máxima diaria de CO (promedio móvil de 8 horas) y el valor diario del AQI permite comprender en qué medida este contaminante contribuye al deterioro de la calidad del aire.
El objetivo del presente estudio es modelar la relación entre la variable Daily Max 8-hour CO Concentration y el Daily AQI Value mediante un modelo de regresión lineal, así como realizar una comparación entre los años 2022 y 2023 con el fin de identificar posibles variaciones interanuales en el comportamiento de estas variables.

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
Con el propósito de evaluar la capacidad predictiva del modelo, el conjunto de datos fue dividido en dos subconjuntos mediante la función train_test_split():
	80% de los datos para entrenamiento. 
	20% de los datos para prueba. 
Esta estrategia permite entrenar el modelo con una porción de los datos y posteriormente evaluar su desempeño en datos no utilizados durante el proceso de ajuste, reduciendo así el riesgo de sobreajuste (overfitting).
________________________________________
### 2.3 Modelo de regresión lineal
Se implementó un modelo de regresión lineal simple utilizando la clase `LinearRegression` de la biblioteca `sklearn.linear_model`.  

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

## 3. Resultados

variables que se usaron en el modelo en este caso del 2022

<img width="573" height="338" alt="image" src="https://github.com/user-attachments/assets/9007e93c-3d39-49be-8f1b-b04591e1e3ed" />

este es del 2023

<img width="580" height="363" alt="image" src="https://github.com/user-attachments/assets/b12fbf2c-1778-4eed-8c68-95ef2e5ce325" />


<img width="693" height="566" alt="image" src="https://github.com/user-attachments/assets/835bb2b4-3ad3-432f-880f-cf843a6e6de3" />


El modelo de regresión lineal arrojó los siguientes resultados:

	R² = 0.9914 
  
	MSE = 0.1078 
  
El coeficiente de determinación R^2=0.9914indica que aproximadamente el 99.14% de la variabilidad observada en el valor diario del AQI puede explicarse mediante la concentración máxima diaria de CO en 8 horas. Este resultado evidencia una relación lineal extremadamente fuerte entre ambas variables.
Por su parte, el valor de MSE = 0.1078 refleja un error promedio cuadrático reducido, lo que sugiere que las predicciones generadas por el modelo presentan una desviación mínima respecto a los valores reales observados.
En cuanto a la comparación entre los años 2022 y 2023, se observaron patrones de comportamiento similares en la relación entre ambas variables, aunque podrían existir diferencias en los niveles promedio de concentración y en la variabilidad anual, lo cual puede estar asociado a factores ambientales o regulatorios.



5. Referencias
   
[1] Scikit-learn Developers, “LinearRegression,” Scikit-learn Documentation. [Online]. Available: https://scikit-learn.org

[2] U.S. Environmental Protection Agency, “Outdoor Air Quality Data – Download Daily Data,” AirData, EPA. Available: https://www.epa.gov/outdoor-air-quality-data/download-daily-data

[3] U.S. Environmental Protection Agency, “Data and Tools,” EPA. Available: https://www.epa.gov/data



link del trabajo de regresion en colab
https://colab.research.google.com/drive/1m0cLgGwtvCM67FoJIUW5I7kVDQCrcF-g#scrollTo=v_bZd8WPeVcw


