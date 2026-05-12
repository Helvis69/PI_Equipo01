## Clasificación de Imágenes con IA y Comunicación MQTT usando ESP32S3 Sense



## 1. Introducción

Actualmente, la inteligencia artificial aplicada a dispositivos embebidos permite ejecutar modelos de Machine Learning directamente en microcontroladores de bajo consumo. Esto hace posible desarrollar sistemas inteligentes sin necesidad de depender completamente de servidores externos o computadoras potentes.

En este taller se utilizó el dispositivo ESP32S3 Sense, el cual integra conectividad WiFi y una cámara capaz de capturar imágenes en tiempo real. Mediante la plataforma SenseCraft AI, se entrenó un modelo de clasificación de imágenes para identificar diferentes objetos.

El proyecto se enfocó en reconocer tres categorías principales:

- Laptop
- Celular
- Cargador

Una vez entrenado el modelo, este fue cargado al ESP32S3 Sense para ejecutar inferencias localmente (Edge AI). Finalmente, se configuró una comunicación MQTT para transmitir las etiquetas clasificadas hacia un broker externo.

Durante las pruebas se logró establecer correctamente la conexión con el servidor MQTT y el dispositivo era detectado por el sistema principal. Sin embargo, los datos enviados no se mostraban correctamente en la interfaz principal, posiblemente debido a un problema de configuración del topic o del formato del mensaje enviado.

---

## 2. Objetivo de la Actividad

### Objetivo General

Desarrollar un sistema de clasificación de imágenes en tiempo real utilizando técnicas de TinyML con el ESP32S3 Sense y la plataforma SenseCraft AI.

### Objetivos Específicos

- Crear un dataset de imágenes para entrenamiento.
- Entrenar un modelo de clasificación de imágenes.
- Implementar el modelo en el ESP32S3 Sense.
- Configurar comunicación MQTT.
- Enviar resultados de clasificación al broker MQTT.
- Analizar el comportamiento del sistema IoT.

---

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

- Laptop
- Celular
- Cargador

<img width="1600" height="805" alt="image" src="https://github.com/user-attachments/assets/f0640029-fc4b-41c5-a351-ca40aada40f9" />

Para cada categoría se capturaron aproximadamente 100 imágenes utilizando la cámara del ESP32S3 Sense. Se tomó capturas desde diferentes ángulos, distintas posiciones, varción de ilumincación y también los fondos. Estas prácticas permitieron mejorar la capacidad del modelo para reconocer objetos en diferentes condiciones reales.

---

### 4.2 Entrenamiento del Modelo

El entrenamiento se realizó mediante la plataforma SenseCraft. Pasando procesos de creación de categorías, captura de imágenes, organización automática del dataset, entrenamiento en la nube, evaluación del modelo y la exportación del firmware.

El modelo fue entrenado utilizando algoritmos de clasificación de imágenes optimizados para dispositivos embebidos. El objetivo del entrenamiento fue permitir que el sistema aprendiera las características visuales de cada objeto para posteriormente reconocerlos en tiempo real.

<img width="1599" height="899" alt="image" src="https://github.com/user-attachments/assets/a567913d-f639-4dd8-94af-57fca355b918" />

---

### 4.3 Implementación del Modelo en el ESP32S3 Sense

Una vez finalizado el entrenamiento, se descargó el firmware generado automáticamente por SenseCraft AI. Se conectó el ESP32S3 Sense mediante USB, se cargó el firmware al dispositivo, se reinició el microcontrolador y se realizaron pruebas de inferencia. Gracias a esto, el ESP32S3 pudo ejecutar el modelo localmente sin necesidad de utilizar procesamiento externo.

---

## 5. Configuración MQTT

Para transmitir los resultados obtenidos por el modelo se configuró una salida MQTT.

MQTT es un protocolo de mensajería ligero ampliamente utilizado en sistemas IoT debido a su bajo consumo de recursos y facilidad de integración. Usando los parámetros:

| Parámetro | Valor |
|---|---|
| Broker | `rp10.rcr-labs.com` |
| Puerto | `1883` |
| Usuario | `Alumno` |
| Contraseña | `Cayetano2026` |
| SSL | `No` |
| Client ID | `UPCH/Equipo1` |

---

## 6. Envío de Datos

El dispositivo enviaba las etiquetas detectadas mediante MQTT utilizando texto plano o estructuras JSON. Para activar el flujo de inferencia y transmisión de datos se utilizó el siguiente comando:

```text
AT+INVOKE=-1,0,0
```

<img width="1233" height="898" alt="image" src="https://github.com/user-attachments/assets/7fe0fcac-986d-4488-b0ee-758404dc6e6e" />

---

# 7. Problema Encontrado

Durante el desarrollo se presentó un inconveniente relacionado con la visualización de los mensajes MQTT.

Aunque el dispositivo sí se conectaba al broker, el sistema principal detectaba el ESP32S3 y aparentemente se enviaban mensajes, la interfaz principal no mostraba correctamente los datos recibidos.

Se identificó de que el problema se encontraría en la configuración de topic incorrecto, es decir, el ESP32S3 pudo haber publicado en un topic distinto al monitoreado por el sistema principal. Debido a ello se muestra que si se detecto el envió de mensajes de nuestro dispositivo, más no se pudo visualizar la información en el broker principal.

---

# 9. Conclusiones

La integración del ESP32S3 Sense con la plataforma SenseCraft AI representa una solución integral y eficiente para el ecosistema TinyML, permitiendo entrenar y desplegar modelos de visión o IA en tiempo real, cuya precisión depende directamente de la calidad y variedad del dataset utilizado. Para la implementación práctica en IoT, el protocolo MQTT resulta ideal por su ligereza en la transmisión de datos, siempre y cuando se garantice una estructuración rigurosa de topics y payloads para asegurar la correcta comunicación y funcionamiento del sistema.

---

## Bibliografía

- SenseCraft AI  
  https://sensecraft.seeed.cc/ai

- MQTT.org  
  https://mqtt.org

- ESP32 Documentation  
  https://docs.espressif.com

- HiveMQ MQTT Essentials  
  https://www.hivemq.com/mqtt-essentials
