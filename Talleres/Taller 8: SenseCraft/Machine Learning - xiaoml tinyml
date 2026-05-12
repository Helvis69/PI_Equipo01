# Informe de Actividad: TinyML con XIAO ESP32S3

Este informe documenta el proceso de entrenamiento, despliegue y configuración de un modelo de visión artificial utilizando el kit **XIAO ESP32S3** y la plataforma **SenseCraft**.

---

## 1. Objetivo de la Actividad
Desarrollar un sistema de clasificación de imágenes en tiempo real capaz de reconocer **3 categorías** distintas, utilizando técnicas de Machine Learning embebido (TinyML).

---

## 2. Entrenamiento del Modelo
El proceso se centró en la creación de un dataset robusto directamente desde el hardware:
*   **Categorías:** Laptop, Celular y Cargador.
*   **Dataset:** Se capturaron un mínimo de **100 imágenes por cada categoría** para asegurar la precisión del modelo.
*   **Procesamiento:** El modelo fue entrenado en la nube de SenseCraft, logrando diferenciar los objetos mediante características visuales clave.



---

## 3. Subir el Modelo al XIAO ML (ESP32S3)
Una vez finalizado el entrenamiento, se procedió con el despliegue físico:
*   **Compilación:** Se generó el firmware optimizado para el microcontrolador.
*   **Flash:** El modelo fue cargado al dispositivo mediante conexión USB, permitiendo que la cámara realice inferencias de forma local (Edge AI).

---

## 4. Configuración de Salida MQTT y Etiquetas
Para visualizar los resultados de la clasificación fuera del dispositivo, se configuró la comunicación MQTT con los siguientes parámetros extraídos del laboratorio:

### Detalles de Conexión:
*   **Broker:** `://rcr-labs.com`
*   **Puerto:** `1883` (Standard MQTT) / `8084` (WSS para navegador)
*   **Usuario:** `Alumno`
*   **Contraseña:** `Cayetano2026`
*   **ID de Cliente / Tópico:** `UPCH/Equipo1`

### Envío de Datos:
El dispositivo envía etiquetas de clasificación en formato de texto plano o JSON. Para activar este flujo, se utilizó el comando:
`AT+INVOKE=-1,0,0`

Al recibir los datos, la salida se visualiza en la consola con el formato:
`data: "clase_detectada"`

---

## 5. Documentación y Entrega
*   **Repositorio:** Los archivos de configuración y este informe han sido subidos a **GitHub**.
*   **Evidencias:** Se adjuntan capturas del estado "MQTT Conectado" y de la "Vista previa de resultados" con el modelo en funcionamiento.

---

**Conclusión:** Se logró completar el ciclo de vida de un proyecto TinyML, desde la captura de datos en pizarra hasta la transmisión inalámbrica de resultados mediante un broker MQTT externo.
