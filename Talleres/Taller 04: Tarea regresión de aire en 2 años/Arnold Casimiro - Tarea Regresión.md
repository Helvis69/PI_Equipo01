## INTRODUCCIÓN:

La contaminación del aire, por la presencia de partículas finas PM2.5, representa un significativo riesgo para la saludo humana. Estas partículas pueden penetrar profundamente en el sistema respiratorio y están asociadas a enfermedades cardiobasculares y respiratorias.(1,2)

Este trabajo analiza la concentración de PM2.5 utilizando datos correspondientes a los años 2024-2025 en la región de Washington. El objetivo principal es aplicar técnicas de ciencia de datos y aprendizaje automático para identificar tendencias temporales y evaluar la capacidad de un modelo de regresión lineal para predecir los niveles de contaminación. La relevancia de este estudio radica en la importancia de monitorear el Índice de Calidad del Aire (AQI) para la salud pública

Además, se realiza una clasificación básica de la calidad del aire en categorías (bueno y no saludable),lo cual es fundamental para la toma de decisiones en salud ambiental. 

## METODOLOGÍA:

Se utilizaron dos conjuntos de datos correspondientes a los años 2024 y 2025, los cuales fueron concatenados para formar un único dataset.

pm24= pd.read_csv('/kaggle/input/datasets/brigitteadhar49/pm24-washington/2024_PM25.csv')
pm25 = pd.read_csv('/kaggle/input/datasets/brigitteadhar49/pm-components-air/2025_PM25.csv')

Concatenación:

df = pd.concat([pm24, pm25], ignore_index=True)

La fase experimental se dividió en tres etapas: 
- procesamiento
- modelado
- evaluación.

Se seleccionaron variables críticas como:
- concentración de PM2.5
- AQI
- Factor de completitud.

El preprocesamiento incluyó la conversión a formatos adecuados y la eliminación de registros con baja calidad (completitud < 75%). Los datos fueron ordenados cronológicamente.

Debido a la existencia de múltiples mediciones por día, se realizó una agregación por fecha, calculando el promedio diario de PM2.5. Además, se generó una variable numérica basada en la fecha (fecha ordinal) para representar el tiempo.

Se aplicó un modelo de regresión lineal simple, donde la variable independiente fue la fecha ordinal y la variable dependiente la concentración de PM2.5. Los datos se dividieron en un conjunto de entrenamiento (80%) y prueba (20%).

Finalmente, el modelo fue evaluado mediante el coeficiente de determinación (R²). Adicionalmente, se realizó una clasificación binaria utilizando un umbral de 12 µg/m³ y se evaluó mediante una matriz de confusión. Para el análisis visual, se generó una gráfica de la evolución temporal de la concentración de PM2.5 junto con el límite recomendado.

## RESULTADOS:

La evaluación del modelo mediante la matriz de confusión revela un sesgo significativo hacia la clase dominante ("Bueno"). Si bien el algoritmo muestra una alta eficacia para identificar condiciones de aire saludable (siendo 135 aciertos), presenta una omisión total de los eventos de contaminación crítica, clasificando erróneamente los 11 casos "No Saludables" como "Buenos".

<img width="991" height="583" alt="image" src="https://github.com/user-attachments/assets/39e9ac2f-e9de-4d46-88af-ccd42d0048b4" />

Este fenómeno, conocido como subestimación de valores extremos, confirma que una regresión lineal basada únicamente en el tiempo es insuficiente para gestionar la naturaleza estocástica del PM2.5. En términos prácticos, el modelo actúa se inhabilita como herramienta de alerta temprana, ya que es incapaz de capturar los picos de contaminación identificados previamente en el análisis de la serie temporal.

<img width="1163" height="610" alt="image" src="https://github.com/user-attachments/assets/a6ecbdbd-e77d-481c-bd8a-df563b4455ae" />


La siguiente gráfica muestra la evolución de la concentración de PM2.5 entre 2024 y 2025. En general, los valores se mantienen por debajo del umbral de 12 µg/m³, lo que indica una calidad del aire mayormente aceptable bajo los términos de la Organización Mundial de la salud, que dicta que los niveles aceptables de concentración de PM2.5 son del 15µg/m³. 

Sin embargo, se observan picos aislados, incluyendo un valor extremo cercano a 55 µg/m³, lo que sugiere eventos puntuales de alta contaminación. Esto indica que la serie presenta variabilidad y posibles eventos no lineales, lo cual dificulta su modelado mediante regresión lineal simple.

## DISCUSIÓN:

Aunque la regresión lineal ofrece una visión general de la tendencia temporal, los niveles de PM2.5 presentan un comportamiento estacional y multivariado, influenciado por factores como condiciones meteorológicas y actividad urbana. Por ello, el uso de una única variable independiente (tiempo) limita la capacidad predictiva del modelo.

Además, el filtrado de datos basado en el porcentaje de completitud (≥ 75%) permitió asegurar la calidad de las mediciones, reduciendo el impacto de posibles fallos en los sensores.

Sin embargo, los resultados obtenidos evidencian una limitación importante: el modelo no logra identificar correctamente los casos de contaminación no saludable, como se observa en la matriz de confusión. Esto sugiere un sesgo hacia la clase mayoritaria y una baja capacidad para detectar eventos críticos.

En consecuencia, aunque el modelo es útil para describir tendencias generales, no resulta adecuado para aplicaciones que requieran una predicción precisa o la detección de episodios de alta contaminación.

## FUENTES:
[1] U.S. Environmental Protection Agency, “Particulate Matter (PM2.5) Basics,” 2023.
[2] World Health Organization, “Air Quality Guidelines,” 2021.

### LINK DE LA INFORMACIÓN DEL DATA (2024 - 2025, PM2.5) Washington-Arlington-Alexandria,DC-VA-MD-WV) Monitor Site (110010043)
https://www.epa.gov/outdoor-air-quality-data/download-daily-data

### LINK DEL CÓDIGO:
https://www.kaggle.com/code/arnoldcasimiro/arnold-proyecto
