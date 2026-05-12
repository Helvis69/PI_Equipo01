## Clasificación de Imágenes con IA y Comunicación MQTT usando ESP32S3 Sense

Integrantes:
- Jheyson Castañeda
- Maximiliana Ramos


## 1. Introducción

Hoy en día, la inteligencia artificial incorporada en sistemas embebidos permite que los modelos de Machine Learning funcionen directamente en microcontroladores de bajo consumo energético. Gracias a ello, es posible crear dispositivos inteligentes que procesen información de manera local, sin depender totalmente de servidores externos o equipos de alto rendimiento.

En este taller se trabajó con el dispositivo ESP32S3 Sense, que cuenta con conexión WiFi y una cámara integrada capaz de capturar imágenes en tiempo real. Utilizando la plataforma SenseCraft AI, se desarrolló y entrenó un modelo de clasificación de imágenes orientado al reconocimiento de distintos objetos.

El proyecto estuvo centrado en la identificación de tres categorías principales:

- Lapiceros
- Celular
- mouse


Después de completar el entrenamiento del modelo, este se implementó en el dispositivo ESP32S3 Sense con el objetivo de realizar inferencias directamente en el microcontrolador mediante tecnología Edge AI. Posteriormente, se habilitó una comunicación a través del protocolo MQTT para enviar las etiquetas obtenidas hacia un broker externo.

En las pruebas realizadas, la conexión con el servidor MQTT se estableció de manera satisfactoria y el dispositivo logró ser reconocido por el sistema principal. No obstante, la información transmitida no aparecía adecuadamente en la interfaz principal. Esto podría estar relacionado con una configuración incorrecta del topic utilizado o con inconsistencias en la estructura del mensaje enviado.


## 2. Objetivo de la Actividad

### Objetivo General

Desarrollar un sistema de clasificación de imágenes en tiempo real utilizando técnicas de TinyML con el ESP32S3 Sense y la plataforma SenseCraft AI.


<img width="720" height="623" alt="WhatsApp Image 2026-05-12 at 6 01 43 PM" src="https://github.com/user-attachments/assets/ef13f7fd-e01c-49c1-bca8-adf15926fc35" />

### Objetivos Específicos

Elaborar un conjunto de imágenes destinado al entrenamiento del modelo.
Desarrollar y entrenar un sistema de clasificación de imágenes.
Integrar el modelo entrenado en el dispositivo ESP32S3 Sense.
Establecer la comunicación mediante el protocolo MQTT.
Transmitir las etiquetas generadas por la clasificación hacia el broker MQTT.
Evaluar el funcionamiento y desempeño del sistema IoT implementado.


## 3. Materiales Utilizados

| Material | Descripción |
|---|---|
| XIAO ESP32S3 Sense | Microcontrolador con cámara integrada |
| Computadora | Configuración y entrenamiento |
| SenseCraft AI | Plataforma de entrenamiento TinyML |
| Red WiFi | Comunicación del dispositivo |
| Broker MQTT | Recepción de mensajes |
| Cable USB | Programación del ESP32S3 |

---


## 4. Desarrollo del Proyecto

### 4.1 Recolección de Datos

El primer paso consistió en crear un dataset de imágenes para entrenar el modelo de inteligencia artificial.

Se definieron tres categorías:

- lapiceros
- Celular
- Cmouse

<img width="1280" height="562" alt="image" src="https://github.com/user-attachments/assets/dd4fc234-c19c-45f9-b48c-90fd2875729c" />



