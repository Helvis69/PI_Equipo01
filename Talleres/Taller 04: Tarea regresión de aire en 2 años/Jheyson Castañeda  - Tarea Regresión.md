## regresion lineal
## 1. Introducción
La calidad del aire constituye un indicador clave para evaluar tanto el impacto ambiental como los posibles efectos adversos en la salud pública. Dentro de los contaminantes atmosféricos más significativos se encuentra el monóxido de carbono (CO), cuya concentración tiene una influencia directa en el Índice de Calidad del Aire (AQI).
El objetivo del presente estudio es construir un modelo de regresión lineal a partir de datos correspondientes a los años 2022 y 2023, con el propósito de examinar la relación entre la concentración máxima diaria de CO y el valor diario del AQI. Para ello, se consolidaron ambos conjuntos de datos en un único dataset, lo que permitió realizar un análisis integrado, consistente y metodológicamente más sólido

2. Metodología
2.1 Recolección y preparación de datos
Se utilizaron dos datasets independientes correspondientes a los años 2022 y 2023. Ambos conjuntos contenían las mismas variables
Luego se realizó:
•	Eliminación de valores nulos. 
•	Selección de variables relevantes. 
•	División del conjunto de datos en entrenamiento (80%) y prueba (20%). 
2.2 Variables utilizadas
•	Variable dependiente (Y): 
o	Daily AQI Value 
•	Variable independiente (X): 
o	Daily Max 8-hour CO Concentration 
2.3 Modelo aplicado
Se empleó el modelo de Regresión Lineal utilizando la librería sklearn de Python.
Para evaluar el desempeño del modelo se utilizaron las siguientes métricas:
•	Coeficiente de determinación (R²) 
•	Error cuadrático medio (MSE) 

3. Resultados

Los resultados obtenidos fueron:
•	R² = 0.9914 
•	MSE = 0.1078 
El valor de R² indica que el modelo explica aproximadamente el 99.14% de la variabilidad del AQI, lo que evidencia una relación lineal extremadamente fuerte entre la concentración de CO y el índice de calidad del aire.
El valor bajo del MSE demuestra que el modelo presenta un error de predicción mínimo, lo que confirma su alta precisión.

4. Discusión
El alto valor de R² puede explicarse debido a que el AQI se calcula directamente a partir de la concentración del contaminante atmosférico. En este sentido, la fuerte correlación observada es coherente desde el punto de vista matemático y ambiental.
Si bien el modelo presenta un excelente ajuste, es importante considerar que el AQI no depende únicamente del CO, sino también de otros contaminantes. Por ello, futuros trabajos podrían incluir variables adicionales para un análisis multivariable más completo.


Referencias (Formato IEEE)
Ejemplo en formato IEEE:
[1] U.S. Environmental Protection Agency, “Air Quality Index (AQI) Basics,” EPA, 2023. [Online]. Available: https://www.epa.gov/aqi
[2] F. Pedregosa et al., “Scikit-learn: Machine Learning in Python,” Journal of Machine Learning Research, vol. 12, pp. 2825–2830, 2011.
[3] W. McKinney, “Data Structures for Statistical Computing in Python,” Proc. of the 9th Python in Scien

link del colab
https://colab.research.google.com/drive/1m0cLgGwtvCM67FoJIUW5I7kVDQCrcF-g#scrollTo=v_bZd8WPeVcw


