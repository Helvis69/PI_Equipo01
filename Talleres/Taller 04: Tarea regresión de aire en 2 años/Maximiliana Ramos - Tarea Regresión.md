# INTRODUCIÓN 

La calidad del aire es un factor clave en la salud ambiental y humana. En este estudio se analizan datos de concentración de material particulado fino (PM2.5) y el índice de calidad del aire (AQI), obtenidos de la página oficial de la Agencia de Protección Ambiental de Estados Unidos (EPA). El objetivo es aplicar un modelo de regresión lineal para analizar la relación entre la concentración de PM2.5, el tiempo y el AQI durante los años 2022 y 2023.

<img width="736" height="492" alt="image" src="https://github.com/user-attachments/assets/e7150b87-bf52-4828-bb3f-b907989347aa" />

Fig.1. Only Puerto Rico Meets WHO Air Standards in the Americas, Study Shows


# METODOLOGÍA

Se utilizaron datasets descargados de la EPA correspondientes a los años 2022, 2023, 2024 y 2025.

### Proceso:

- Integración de múltiples datasets en uno solo
- Conversión de variables a formato numérico
- Eliminación de valores nulos
- Transformación de fechas
- Selección de variables relevantes

### Modelo de regresión lineal simple, dónde:

- Variable independiente: Concentración de PM2.5
- Variable dependiente: AQI

AQI=β0​+β1​(PM2.5)

### División de los datos:

- 70% entrenamiento
- 30% prueba

# RESULTADOS
El modelo de regresión lineal desarrollado muestra una relación positiva clara entre la concentración de PM2.5 y el índice de calidad del aire (AQI), lo que indica que a medida que aumentan los niveles de partículas finas en el aire, también se incrementa el nivel de contaminación. El coeficiente (2.520) obtenido confirma esta tendencia, evidenciando que el PM2.5 es un buen predictor del AQI. Asimismo, el coeficiente de determinación (R²) alcanza un valor alto de 0.813, lo que sugiere que el modelo logra explicar gran parte de la variabilidad de los datos observados. En cuanto a las métricas de error, los valores de MAE (4.767) y RMSE (5.861) se mantienen en rangos aceptables, indicando que las predicciones realizadas por el modelo son cercanas a los valores reales. Finalmente, el análisis gráfico respalda estos resultados, mostrando una tendencia lineal bien definida y una distribución de residuos aproximadamente normal, lo cual valida el cumplimiento de los supuestos del modelo de regresión lineal.


<img width="696" height="564" alt="image" src="https://github.com/user-attachments/assets/7a7ab0dc-105e-4b53-8db2-68415fddf089" />

Fig. 2. Relación entre PM2.5 y AQI



<img width="696" height="574" alt="image" src="https://github.com/user-attachments/assets/bb1eee01-6bbe-4fa7-981c-92bf8b60170c" />

Fig.3 Distribución de errores (residuos)



<img width="694" height="535" alt="image" src="https://github.com/user-attachments/assets/9f916486-2344-4b64-837f-ae0fba9d3630" />

Fig.4. Ajuste del modelo de regresión lineal



# DISCUSIÓN

Los resultados obtenidos evidencian que la concentración de PM2.5 es un factor determinante en la calidad del aire, mostrando una relación directa y significativa con el índice AQI. Esto concuerda con el comportamiento esperado, las partículas finas (PM2.5) son un contaminante atmosférico primario reconocido mundialmente como una grave amenaza para la salud pública, se sabe que las PM2.5, con un diámetro inferior a 2,5 μm, pueden penetrar profundamente en el sistema respiratorio y afectar diversos órganos, estando asociadas a enfermedades cardiovasculares, respiratorias y del sistema nervioso, así como a un incremento en la mortalidad [2]. En este contexto, resulta fundamental analizar su relación con indicadores como el índice de calidad del aire (AQI), con el fin de comprender mejor su impacto y contribuir a la toma de decisiones en materia ambiental. Sin embargo, si bien el modelo presenta un buen ajuste, es importante considerar que la calidad del aire no depende únicamente del PM2.5, sino también de otras variables ambientales como la temperatura, la humedad, la velocidad del viento y la presencia de otros contaminantes [2]. Asimismo, se pueden observar variaciones entre los diferentes años analizados, lo que sugiere la influencia de factores estacionales o cambios en las fuentes de emisión. Por ello, aunque el modelo lineal resulta adecuado para una primera aproximación, se recomienda en futuros estudios incorporar más variables y explorar modelos más complejos que permitan mejorar la precisión y comprensión del fenómeno.


# REFERENCIAS (IEEE)

[1] United States Environmental Protection Agency, “Outdoor Air Quality Data,” EPA, 2023. [Online]. Available: https://www.epa.gov/outdoor-air-quality-daa

[2] HOU, Tianhua, et al. Oxidative stress is the pivot for PM2. 5-induced lung injury. Food and Chemical Toxicology, 2024, vol. 184, p. 114362.

[3] https://colab.research.google.com/drive/1mfNrmoIC1DJXcOpj1PUvGuOM3QureGTf?usp=sharing 
