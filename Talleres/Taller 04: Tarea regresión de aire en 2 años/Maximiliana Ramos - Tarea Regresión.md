# INTRODUCIÓN 

La calidad del aire es un factor clave en la salud ambiental y humana. En este estudio se analizan datos de concentración de material particulado fino (PM2.5) y el índice de calidad del aire (AQI), obtenidos de la página oficial de la Agencia de Protección Ambiental de Estados Unidos (EPA). El objetivo es aplicar un modelo de regresión lineal para analizar la relación entre la concentración de PM2.5, el tiempo y el AQI durante los años 2022 y 2023.

<img width="736" height="492" alt="image" src="https://github.com/user-attachments/assets/e7150b87-bf52-4828-bb3f-b907989347aa" />

Fig.1. Only Puerto Rico Meets WHO Air Standards in the Americas, Study Shows


# METODLOGÍA

Se utilizaron dos datasets correspondientes a los años 2022 y 2023, ambos fueron integrados en un solo conjunto de datos para su análisis y se realizaron los siguientes pasos:
- Conversión de variables a formato adecuado (fechas y valores numéricos)
- Eliminación de valores nulos
- Creación de una variable temporal en días
- Selección de variables:
- Variables independientes: tiempo (Days) y concentración de PM2.5
- Variable dependiente: AQI
- Aplicación de regresión lineal múltiple
- División del dataset en entrenamiento (70%) y prueba (30%)

# RESULTADOS

El modelo de regresión lineal mostró una relación positiva entre la concentración de PM2.5 y el índice AQI, lo cual es consistente con la teoría ambiental.

El coeficiente de determinación R
2
 obtenido indica el nivel de ajuste del modelo, mostrando una adecuada capacidad predictiva.

Las métricas de error (MAE y RMSE) reflejan un margen de error aceptable considerando la variabilidad natural de los datos ambientales.



# DISCUSIÓN

Los resultados evidencian que el PM2.5 es un predictor significativo del AQI, lo cual coincide con estudios previos sobre calidad del aire.

Sin embargo, el modelo presenta limitaciones, ya que no incluye otras variables relevantes como condiciones meteorológicas (temperatura, viento, humedad), que pueden influir en la dispersión de contaminantes.

Para mejorar el modelo, se recomienda incorporar más variables y evaluar modelos más complejos.

📚 Referencias (IEEE)
[1] United States Environmental Protection Agency, “Outdoor Air Quality Data,” EPA, 2023. [Online]. Available: https://www.epa.gov/outdoor-air-quality-data
