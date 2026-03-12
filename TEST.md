# Cuestionario de Evaluación: Comunicación por Sockets 📝

**Nombre del Estudiante:** Axel Navarrete
**Fecha:** 11/03/2026

*Instrucciones: Responde a las siguientes preguntas basándote en la teoría de redes y en el análisis del código de nuestro proyecto. Sube este archivo con tus respuestas a tu repositorio como evidencia de trabajo.*

1. **¿Qué es una Dirección IP y para qué sirve en nuestro proyecto?**
Una dirección IP es un número que identifica a un dispositivo dentro de una red. En nuestro proyecto permite que la computadora encuentre y se conecte al ESP32 para enviar y recibir datos.

2. **¿Qué es un Puerto de red? (Menciona qué puerto estamos usando en el código de la ESP32).**
Un puerto de red es un canal de comunicación dentro de un dispositivo. En el código del ESP32 usamos el puerto 80 para la conexión.

3. **Define con tus propias palabras qué es un Servidor en informática.**
Un servidor es un dispositivo o programa que espera conexiones de otros equipos para enviar datos o prestar un servicio.

4. **¿Cuál es la diferencia entre un "Servidor" (Hardware/Software) y un "Servicio" (Service)?**
El servidor es el dispositivo o programa que ofrece recursos, mientras que el servicio es la función específica que ese servidor proporciona.

5. **Investigación: ¿Cuál es la diferencia técnica entre un "Socket TCP" normal y un "WebSocket"?**
Un socket TCP es una conexión directa para enviar datos entre dispositivos. Un WebSocket permite comunicación en tiempo real sobre internet y se usa mucho en aplicaciones web.

6. **Analizando nuestro código: ¿Quién actúa como Servidor y quién actúa como Cliente? (Justifica tu respuesta mencionando qué funciones del código lo demuestran, ej. `bind()`, `connect()`).**
El ESP32 es el servidor porque usa bind() y listen() para esperar conexiones.
La computadora es el cliente porque usa connect() para conectarse al ESP32.

7. **En el código de la computadora (Python), importamos la librería `threading` (Hilos). ¿Qué pasaría con la ventana de Tkinter si no usáramos hilos para recibir los datos de la red?**
La ventana se congelaría porque el programa estaría ocupado esperando datos de la red.

8. **¿Por qué es necesario usar bloques `try...except` cuando trabajamos con conexiones de red e Internet?**
Porque las conexiones pueden fallar y así evitamos que el programa se cierre por errores.

9. **En la función de encender el LED en Python, enviamos el comando así: `sock.send(b'ON')`. ¿Qué significa esa letra `b` antes de las comillas y por qué no enviamos un texto normal?**
Significa que se envía el mensaje en bytes, que es el formato que usan las conexiones de red para transmitir datos.

10. **Describe brevemente el flujo de datos: ¿Qué camino recorre la información desde que giras el potenciómetro físicamente hasta que la barra se mueve en la pantalla de la computadora?**
Cuando giro el potenciómetro, el ESP32 lee el valor analógico usando el ADC. Ese valor se envía por WiFi a través de un socket TCP hacia la computadora. El programa en Python recibe el dato, lo procesa y actualiza la barra de progreso en Tkinter, haciendo que se mueva según el valor recibido.
