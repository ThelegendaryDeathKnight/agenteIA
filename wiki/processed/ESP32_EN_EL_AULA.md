# ESP32 EN EL AULA

**Actividades para realizar con el Kit ESP32 + TDR STEAM**

**Fuente:** CATEDU (Centro Aragonés de Tecnologías para la Educación). *ESP32 en el Aula*. Copyright 2026.

---

## Resumen técnico

El documento *ESP32 en el Aula* es una guía didáctica completa para la utilización del kit robótico TDR STEAM ESP32 en entornos educativos, desde primaria hasta secundaria. El objetivo principal es capacitar a los docentes y estudiantes en el desarrollo de retos STEAM (Ciencia, Tecnología, Ingeniería, Arte y Matemáticas) mediante el uso de la placa ESP32 Plus STEAMakers de Innova Didactic, junto con la placa de sensores y actuadores Imagina TDR STEAM.

El manual se estructura en varios bloques temáticos. Comienza con una introducción al pensamiento computacional y una explicación detallada de qué es el ESP32, sus características técnicas (microcontrolador Tensilica Xtensa 32-bit LX6 a 160MHz, WiFi 802.11 b/g/n, Bluetooth 4.2, 14 entradas/salidas digitales, 16 canales ADC, 2 DAC, etc.) y su comparación con Arduino. Se describe el hardware de la placa ESP32 Plus STEAMakers, incluyendo sus conectores, sensores internos (Hall y temperatura), medidor de tensión e intensidad, y zócalo para tarjeta microSD.

Posteriormente, se presenta la plataforma STEAMAKERBLOCKS (antes Arduinoblocks), un entorno de programación por bloques basado en la web que permite programar el ESP32 sin necesidad de escribir código. Se explica cómo crear una cuenta, gestionar cuentas de alumnos, instalar el Connector y comenzar un proyecto. El manual ofrece una guía completa sobre los diferentes tipos de proyectos disponibles: ESP32 STEAMakers, ESP32 STEAMakers + Imagina TdR STEAM, etc.

El núcleo del documento son las 18 actividades prácticas organizadas en cuatro categorías: prácticas con sensores digitales (LED, LEDs rojo y azul, parpadeo intermitente, LED RGB, zumbador, pulsadores), prácticas con sensores analógicos (potenciómetro, LDR, LM35D, DHT-11, emisor/receptor de infrarrojos), prácticas con otros elementos del kit (LCD I2C, sensor de sonido, sensores internos del ESP32) y prácticas avanzadas (multitarea, interrupciones, memoria Flash, tarjeta SD). Cada actividad incluye enunciado, teoría, montaje, programación en STEAMAKERBLOCKS y retos de ampliación.

Finalmente, se abordan las comunicaciones inalámbricas: Bluetooth (clásico y BLE), IoT con WiFi y Telegram (creación de bots, envío/recepción de mensajes), IoT con Blynk.io (creación de dashboards y datastreams) y Blynk Legacy local (instalación en Raspberry Pi, configuración de servidor, creación de cuentas). El manual concluye con un muro Padlet, enlaces a recursos adicionales y los créditos de autoría.

---

## Índice de contenidos

1. **Introducción**
   - Objetivos y Contenidos
   - Kit ESP32 en el Aula
   - Pensamiento computacional
   - ¿Qué es ESP32?
   - Hardware ESP32 Plus STEAMakers
   - Sensores
   - Actuadores y otras salidas
   - Sensores y actuadores de la placa Imagina TDR STEAM
   - Sensores en la placa ESP32 plus STEAMakers
   - Software

2. **STEAMAKERBLOCKS**
   - ¿Qué es Steamakerblocks?
   - Crear cuenta en STEAMAKERBLOCKS
   - Cuentas alumnos
   - Connector
   - Empezando un proyecto

3. **Prácticas con sensores digitales**
   - Actividad-01. LED
   - Actividad-02. LEDs rojo y azul
   - Actividad-03. Parpadeo intermitente. Multitarea
   - Actividad-04. LED RGB
   - Actividad-05. Zumbador
   - Actividad-06. Pulsadores

4. **Prácticas con sensores analógicos**
   - Actividad-07. El potenciómetro y Plotter
   - Actividad-08. La fotorresistencia o LDR
   - Actividad-09. El sensor de temperatura LM35D
   - Actividad-10. El sensor de temperatura y humedad DHT-11
   - Actividad-11. Emisor y receptor de infrarrojos

5. **Prácticas con otros elementos del kit**
   - Actividad 12. Puerto de expansión I2C. La LCD de 2x16
   - Actividad 13. Sensor de sonido o micrófono
   - Actividad 14. Sensores internos de ESP32
   - Avanzado: Multitarea, interrupciones, memoria Flash y tarjeta SD

6. **Bluetooth**
   - Un poco de teoría Bluetooth
   - APP Serial Bluetooth Terminal
   - Actividad 15 APP->ESP32
   - Actividad 15 con otra APP: Arduino Bluetooth Control
   - Actividad 16 APP<->ESP32
   - Actividad 16 con la APP Serial Bluetooth Terminal
   - Actividad 16 con APP INVENTOR

7. **Qué es IoT**

8. **IoT-Wifi-Telegram**
   - Crear bot en Telegram
   - Encontrar tu ID en Telegram
   - Código para enviar y recibir
   - Actividad 17 Telegram

9. **IoT-Wifi-Blynk IoT**
   - ¿Qué es Blynk.io?
   - Crear DASHBOARD en Blynk.io
   - Crear programa en STEAMAKERBLOCKS
   - Actividad 18 Blynk IoT

10. **Avanzado: Blynk Legacy local**
    - Raspberry: Qué hay que hacer para empezar
    - Raspberry: Poner un Sistema Operativo
    - Raspberry: Cambiar usuario y contraseña
    - Raspberry: Conectarlo a la red
    - Raspberry: Conexión SSH
    - Raspberry: Apagar
    - Raspberry: VNC
    - Raspberry: Instalar Java 8
    - Raspberry: Instalar y ejecutar el servidor Blynk local
    - En Windows: Instalar Java 11
    - En Windows: Instalar Blynk local
    - En Windows: Ejecutar Blynkserver
    - En Linux: Instalar Blynk Legacy local
    - Blynk Legacy: La APP
    - Blynk Legacy: Crear cuentas
    - Blynk Legacy: El panel de control
    - Blynk Legacy: En la APP
    - Blynk Legacy: Poner el TOKEN en Steamakerblocks
    - Blynk Legacy: 1programa: Encender los pines rojo y verde
    - Blynk Legacy: 2programa RGB y el potenciómetro
    - Blynk Legacy: 3programa Medir la luz del LDR
    - Blynk Legacy: 4programa: Medir T y H con el DHT11
    - Blynk Legacy: 5programa: Lectura sensor LM35 y receptor IR
    - Blynk Legacy: 6programa Leer eventos del TDR Steam
    - Blynk Legacy: 7programa: El timbre
    - Blynk Legacy: ¿Todo junto?

11. **Muro**

12. **Para saber más ...**

13. **Créditos**

---

## 1. Introducción

### Objetivos y Contenidos

**Objetivos:**

- Capacidad de desarrollar retos STEAM con un amplio nivel educativo: primaria hasta secundaria
  - Retos STEAM de nivel principiante con manejo de sensores
  - Retos STEAM de nivel medio adentrándose en las comunicaciones Bluetooth y wifi almacenamiento de datos
  - Retos STEAM de nivel avanzado con prácticas IoT
- Realizar retos STEAM en un entorno ARDUINOBLOKS amigable, sin complicaciones técnicas, multiplataforma y con lenguaje gráfico por bloques
  - Conocer ARDUINOBLOCKS una plataforma web que permite programar por bloques gráficos
  - Conocer las diferentes posibilidades de la programación por bloques de ARDUINOBLOCKS
  - Conocer las posibilidades didácticas de ARDUINOBLOCKS y su gestión de proyectos en el aula
- Conocer el kit robótico TDR STEAM ESP32 que se propone, con un coste económico bajo pero de calidad para que un centro educativo lo pueda asumir para su aplicación en el aula (mínimo 12 por aula)
  - Conocer la placa TDR STEAM ESP32, sus sensores y actuadores
  - Aplicaciones prácticas del TDR STEAM ESP32

**Contenidos:**

- PLACA ESP32
  - Placa ESP32, hardware y software
  - Sensores
  - Actuadores
  - Shield TDR Steam
- ArduinoBlocks
  - Retos
  - Telecomunicaciones
  - Bluetooth
  - IOT-WIFI
  - MQTT
  - BLYNK IOT
  - BLYNK LEGACY
  - Blynk en una raspberry local

---

### Kit ESP32 en el Aula

Se ha buscado un kit entre todos los comerciales que cumpla los siguientes objetivos:

- Que sea fácil de utilizar en el aula, sin necesidad de utilizar excesivo cableado, con el objetivo de realizar el máximo número de retos.
- Utilizar un lenguaje de programación por bloques fácil de desarrollar y sin complejidades técnicas multiplataforma.
- Con buena relación calidad/precio.
- Con un amplio abanico de prácticas y niveles educativos, desde primaria hasta secundaria.
- Facilidad de crear actividades en entorno IoT

El equipo pedagógico de CATEDU ha elegido para este curso el Kit TDR STEAM ESP32 de Innovadidactic, con el objetivo de alcanzar prácticas más avanzadas dentro del mundo del Internet de las cosas IoT.

El kit está pensado para utilizar dentro del aula y se ha establecido un número de 12 grupos, consideramos que es un número óptimo para llegar a la ratio del aula y que el profesor llegue a atender correctamente a todos los grupos.

```json
{
  "type": "image",
  "id": "image-01",
  "page": 9,
  "title": "Partes del kit Imagina TdR STEAM",
  "caption": "Componentes del kit TDR STEAM ESP32 de Innovadidactic",
  "description": "Fotografía del kit completo que incluye la placa Imagina TdR STEAM, la placa ESP32 Plus STEAMakers, mando de control remoto por infrarrojos, pantalla LCD 1602 IIC, sensor de sonido analógico con potenciómetro, cable USB y cables de conexión.",
  "elements": [
    "Placa Imagina TdR STEAM",
    "Placa ESP32 Plus STEAMakers",
    "Mando de control remoto por infrarrojos",
    "Pantalla LCD 1602 IIC (I2C)",
    "Sensor de sonido analógico con potenciómetro",
    "Cable USB",
    "Cables de conexión"
  ],
  "source": "CATEDU - ESP32 en el Aula"
}
```

---

### Pensamiento computacional

¿Dónde se encaja este robot? ¿Se puede comparar este robot con otros robots de otros cursos que hacemos desde CATEDU?

Esta es la hoja de ruta que proponemos, no se tiene que tomar al pie de la letra, pero intenta ayudar al profesorado que tenga una visión global de tanta oferta robótica:

Como se puede ver ESP32 EN EL AULA tiene la ventaja de tener un precio razonable, y dentro del rango de programación en bloques y de prácticas avanzadas IoT con la ventaja que es un kit muy amigable sin apenas conexiones y con muchas posibilidades.

Guía orientativa: https://docs.google.com/presentation/d/e/2PACX-1vQHiZvv1cGHet7eXVy-QcECY4Lj0k017ntDi8MevRWHQX-9myA0bfR5lofMeuGZkWDOHw-Ob-MGoco/embed?start=true&delyams=3000

Tenemos un grupo Telegram Robótica Educativa en Aragón: https://t.me/roboticaeducativaaragon

---

### ¿Qué es ESP32?

#### Primero: ¿Qué es Arduino?

Arduino es una tarjeta electrónica que integra básicamente a un microcontrolador y un conjunto de pines de conexión de entradas y salidas que permiten, mediante un determinado programa, interaccionar con el medio físico mediante sensores y actuadores electrónicos. De esta forma podrás crear tus propios proyectos tecnológicos, dotarlos de sensores que detecten magnitudes físicas como luz, calor, fuerza, etc… y en base a esa información, escribiendo un programa, activar otros dispositivos (actuadores) como pequeñas bombillas, ledes, servomotores, pequeños motores DC, relés, etc… Los sensores se conectan a los pines de entrada y los actuadores a los de salida.

¿Sabías que…? Uno de los co-creadores de Arduino es Español, de Zaragoza: David Cuartielles +info

#### Segundo: ¿Qué es un microcontrolador?

Es un circuito integrado que se puede programar, o sea que puede ejecutar las órdenes que tenga almacenadas en su memoria. Tiene las tres funciones principales de un computador: la unidad central de proceso, memoria y entradas y salidas.

Arduino utiliza la marca ATMEL, y el modelo de microcontrolador depende del tipo de tarjeta, por ejemplo la tarjeta Arduino Uno utiliza el micro ATMEL MEGA 328P.

#### Tercero: ¿Arduino tiene wifi?

Arduino (el clásico) no tiene wifi, y es importante esto para conseguir hacer prácticas IoT. Hay shields que permiten una conexión Ethernet o Wifi pero resultan caras. Otra opción es utilizar la versión del Arduino MKR1000 pero también resulta cara. A partir del 2023 lanzaron Arduino R4 Wifi pero realmente era un ESP32. Lo mejor es utilizar el ESP8266 para que a través de él nuestro Arduino pueda volcar o recibir datos a través de una Wifi.

Resumiendo brevemente, el ESP8266 es un chip microcontrolador, es decir, no es un sensor, no es un actuador, no es una entrada/salida del Arduino sino que es, igual que el Arduino, es una placa electrónica montado en un módulo que tiene un microcontrolador (Tensilica L106 de 32bits) capaz de hacer cosas pero que tiene una característica importante: Que tiene Wifi, pero no lo veas como un módulo Wifi para Arduino, sino como una placa electrónica completa, como el Arduino, incluso es su competencia.

El chip ESP8266 se vende montado en un módulo, el más vendido es el ESP01 y es el que se proporciona en el kit del curso Arduinoblocks en el aula de CATEDU.

```json
{
  "type": "image",
  "id": "image-02",
  "page": 16,
  "title": "Módulo ESP8266 ESP01",
  "caption": "Módulo ESP8266 ESP01",
  "description": "Fotografía del módulo ESP8266 en su versión ESP01, mostrando la parte frontal y trasera con los pines de conexión.",
  "elements": [
    "Módulo ESP8266 ESP01"
  ],
  "source": "Luis Llamas CC-BY-NC-SA"
}
```

Su bajo precio y su software libre permitió al mundo maker utilizar este chip. No sólo se puede utilizar para que el Arduino tenga acceso a Internet, sino también se han desarrollado multitud de módulos con el ESP8266, como veremos más adelante, el más interesante en su evolución es el módulo ESP-12E o el ESP32.

Pero sigamos con el ESP8266 montado en el módulo ESP01. Tiene unas pegas... no se diseñó para montarlo en el Arduino: PRIMERO La alimentación es 3V a 3.6V con picos de 200mA por lo que no puede conectarse directamente a la alimentación 3.3V y 50mA de Arduino. SEGUNDO Consecuencia del máximo de 3.6V es que las entradas y salidas del ESP8266 no conviene conectarlas directamente a las entradas y salidas del Arduino que van a 5V.

#### Cuarto: ¿El ESP32 es ....?

Es una placa sucesora del ESP8266 de bajo coste y consumo que tiene el microprocesador Tensilica 32bits (variante el Xtensa LX6) que tiene Wifi y Bluetooth integrados. Como dice Luis Llamas en https://www.luisllamas.es/esp32/ el ESP32 es el hermano mayor del ESP8266 con Wifi y Bluetooth.

```json
{
  "type": "image",
  "id": "image-03",
  "page": 17,
  "title": "Módulo ESP32",
  "caption": "Módulo ESP32",
  "description": "Fotografía del módulo ESP32, mostrando el chip ESP32-WROOM-32 con sus antenas integradas y pines de conexión.",
  "elements": [
    "Módulo ESP32-WROOM-32"
  ],
  "source": "Luis Llamas CC-BY-NC-SA"
}
```

Es posible programarlo usando código IDE de Arduino, pero también se puede programar con MicroPython.

Su principal característica es su potencial de uso en aplicaciones IoT.

---

### Hardware ESP32 Plus STEAMakers

Esta placa está basada en el ESP32 que hemos visto que tiene:

- Wifi integrado
- Bluetooth integrado
- Puede trabajar con el código IDE de Arduino

Pero, esta versión de Innova Didactic además incorpora:

- Zócalo para tarjetas microSD para almacenamiento de datos.
- Conexiones iguales que cualquier tarjeta Arduino UNO

Esto permite usar cualquier Shield de Arduino, como la TDR STEAM Imagina de este curso.

```json
{
  "type": "image",
  "id": "image-04",
  "page": 18,
  "title": "Placa ESP32 Plus STEAMakers",
  "caption": "Placa ESP32 Plus STEAMakers de Keyestudio",
  "description": "Fotografía de la placa ESP32 Plus STEAMakers, mostrando el módulo ESP32-WROOM-32, los conectores de alimentación, USB, y las hileras de pines de entrada/salida.",
  "elements": [
    "Placa ESP32 Plus STEAMakers",
    "Módulo ESP32-WROOM-32",
    "Puerto USB",
    "Conector de alimentación DC",
    "Botón Reset",
    "Zócalo microSD",
    "Pines de entrada/salida"
  ],
  "source": "CATEDU - ESP32 en el Aula"
}
```

La placa ESP32 Plus STEAMakers nos ofrece una gran cantidad de prestaciones al estar basada en un microcontrolador de 32 bits con conectividad WiFi y Bluetooth integradas en la propia placa y también un zócalo para tarjetas μSD para el almacenamiento de datos. También dispone de conexiones para todas las entradas y salidas con posibilidad de tener la alimentación adjunta y puertos de expansión I2C para poder conectar diferentes dispositivos directamente en la placa.

La placa está basada en el microcontrolador ESP32-WROOM-32 y sus principales especificaciones técnicas son:

- Microcontrolador Tensilica Xtensa 32-bit LX6 a 160MHz.
- Conectividad WiFi 802.11 b/g/n/e/i.
- Conectividad Bluetooth 4.2 y modo BLE.
- Zócalo para tarjetas μSD.
- 14 entradas y salidas digitales con alimentación.
- Conector serie hembra con alimentación.
- Conector I2C para conectar hasta 5 dispositivos a la vez sobre la misma placa.
- Conector hembra I2C para conexión de una pantalla OLED.
- Botón de Reset.
- Conector de 5V
- Conector de 3.3V
- Interruptor 3.3-5V para cambiar entre estas dos tensiones en algunos pines de alimentación.
- Entradas y salidas analógicas.
- Sensor Hall y de temperatura integrado.
- 2 convertidores Digital-Analógico (DAC) de 8 bits.
- 16 convertidores Analógico-Digital (ADC) de 12 bits.
- 16 canales PWM.
- 2 UART.
- 2 canales I2C.
- 4 canales SPI.
- 448Kb ROM.
- 520 KB SRAM.
- 8KB+8KB SRAM en RTC.
- 1kbit eFUSE.
- 512 bytes Memoria Flash (EEPROM).
- 10 sensores táctiles.
- 4 temporizadores internos de 64 bits.

No están disponibles todas las características del controlador ESP-WROOM-32, ya que algunos pines tienen funciones dobles y se utilizan en la placa de forma específica (como, por ejemplo, para controlar la tarjeta SD). Pero la mayoría de funciones se pueden utilizar, además de disponer la placa ESP32 Plus STEAMakers de una mejor conexión de elementos debido a los pines para conectores tipo Dupont de entrada y salida, de I2C y de alimentación. Además, algunos pines de alimentación pueden cambiar su valor (3,3V o 5V) mediante un interruptor en función de nuestras necesidades.

```json
{
  "type": "image",
  "id": "image-05",
  "page": 21,
  "title": "Elementos de la placa ESP32 Plus STEAMakers",
  "caption": "Diagrama de la placa ESP32 Plus STEAMakers con etiquetas",
  "description": "Diagrama que muestra los elementos de la placa ESP32 Plus STEAMakers: botón RESET, puerto USB tipo B, bus I2C, conector de alimentación DC 7V-12V, medidor de corriente y tensión, tarjeta SD, módulo ESP32-WROOM-32, pines de alimentación, entradas analógicas, etc.",
  "elements": [
    "Botón RESET",
    "Puerto USB tipo B",
    "Bus I2C (GND-3.3V/5V-SDA-SCL)",
    "Conector de Alimentación DC 7V-12V",
    "Medidor de corriente y tensión",
    "Tarjeta SD (CS-CMD-SCK-D0)",
    "Módulo ESP32-WROOM-32",
    "Pines de alimentación",
    "Entradas analógicas",
    "Salida alimentación 3.3V y 5V",
    "IO0",
    "Reset"
  ],
  "source": "Federico Coca - Notas sobre ESP32 STEAMakers CC-BY-SA"
}
```

Las conexiones de la placa Imagina TDR STEAM con la placa ESP32 Plus STEAMakers son las mismas que si utilizamos cualquier placa compatible con Arduino UNO.

**Importante:** Todos los pines IOxx son entradas y salidas digitales, algunas con más funciones. Utilizando la comunicación WiFi no funciona el ADC2.

En la tabla siguiente tenemos relacionados todos los pines entre los tipos de placas UNO, Imagina TdR STEAM y ESP32 STEAMakers.

```json
{
  "type": "table",
  "id": "table-01",
  "page": 22,
  "title": "Relación de pines entre UNO, TdR STEAM y ESP32 STEAMakers",
  "headers": ["UNO Pin", "Función", "TdR STEAM Pin", "Función", "ESP32 Pin", "Ampliación"],
  "rows": [
    ["D0", "Rx", "IO03", "Rx", "UART 0 RX", ""],
    ["D1", "Tx", "IO01", "Tx", "UART 0 TX", ""],
    ["D2", "Pulsador SW1", "IO26", "ADC2 CH9", "DAC2", ""],
    ["D3", "Libre", "IO25", "ADC2 CH8", "DAC1", ""],
    ["D4", "DHT11", "IO17", "UART 2 TX", ""],
    ["D5", "Libre", "IO16", "UART 2 RX", ""],
    ["D6", "Color rojo del LED RGB", "IO27", "ADC2 CH7", "ADC2-7 / TOUCH7"],
    ["D7", "Pulsador SW2", "IO14", "ADC2 CH6", "ADC2-6 / TOUCH6"],
    ["D8", "Zumbador o buzzer", "IO12", "ADC2 CH5", "ADC2-5 / TOUCH5"],
    ["D9", "Color verde del LED RGB", "IO13", "ADC2 CH4", "ADC2-4 / TOUCH4"],
    ["D10", "Color azul del LED RGB", "IO05", "VSPI CS0", ""],
    ["D11", "Sensor IR", "IO23", "VSPI MOSI", ""],
    ["D12", "LED rojo", "IO19", "VSPI MISO", ""],
    ["D13", "LED azul", "IO18", "VSPI CLK", ""],
    ["GND", "GND", "", "", ""],
    ["AREF", "Reset", "", "", ""],
    ["SDA", "I2C", "IO21", "", ""],
    ["SCL", "I2C", "IO22", "", ""],
    ["A0", "Potenciómetro", "IO02", "ADC2 CH2", ""],
    ["A1", "Sensor de luz (LDR)", "IO04", "ADC2 CH0", ""],
    ["A2", "Sensor de temperatura (LM35)", "IO36", "ADC1 CH0", ""],
    ["A3", "Libre", "IO34", "ADC1 CH6", ""],
    ["A4", "I2C", "IO38", "", ""],
    ["A5", "I2C", "IO39", "ADC1 CH3", ""],
    ["VIN", "VIN", "", "", ""],
    ["GND", "GND", "GND", "GND", ""],
    ["5V", "5V", "5V", "", ""],
    ["3.3V", "3.3V", "3.3V", "", ""],
    ["RST", "Reset", "5V", "5V", ""],
    ["", "", "IO00", "¡ No conectar !", ""],
    ["", "", "IO32", "D0 - uSD", ""],
    ["", "", "IO15", "CLK - uSD", ""],
    ["", "", "IO33", "CMD - uSD", ""],
    ["", "", "IO35", "IOUT Medidor de corriente", ""],
    ["", "", "IO37", "VOUT Medidor de tensión", ""]
  ],
  "notes": "Para saber más: Notas sobre ESP32 STEAMakers https://fgcoca.github.io/ESP32-STEAMakers/hsteamakers/",
  "source": "Federico Coca - Notas sobre ESP32 STEAMakers CC-BY-SA"
}
```

---

### Sensores

Esta sección es una visión rápida de las posibles entradas de los robots. NO LEAS TODOS SINO LOS QUE TIENE TU ROBOT.

#### Un poco de teoría…

Cualquier sistema de control podríamos decir que funciona de una manera similar a un ser humano, salvando las distancias. Nosotros recibimos la información del mundo exterior gracias a nuestros sentidos (oído, olfato, gusto, vista y tacto), nuestro cerebro procesa esa información y a través de nuestros músculos o de nuestra voz realizamos diferentes acciones. Pues lo mismo sucede con los sistemas de control, reciben información del exterior gracias a los diferentes SENSORES, procesan esa información en sus PLACAS CONTROLADORAS (sus cerebros) tales como Arduino y dan una respuesta utilizando sus diferentes ACTUADORES.

```json
{
  "type": "image",
  "id": "image-06",
  "page": 24,
  "title": "Bloques de sensores en STEAMAKERBLOCKS",
  "caption": "Menú de sensores en STEAMAKERBLOCKS",
  "description": "Captura de pantalla del menú de sensores en STEAMAKERBLOCKS mostrando bloques como Potenciómetro, Pulsador, Pulsador (filtrado), Pulsador táctil, Detector de movimiento (PIR), DHT-11, DHT-22, etc.",
  "elements": [
    "Potenciómetro Pin A0",
    "Pulsador Pin 2 Lógica invertida",
    "Pulsador (filtrado) Pin 0-RX se ha pulsado Lógica invertida",
    "Pulsador táctil Pin 2",
    "Detector de movimiento (PIR) Pin 2",
    "DHT-11 Temperatura ºC Pin 2",
    "DHT-22 Temperatura ºC Pin 2"
  ],
  "source": "CATEDU - ESP32 en el Aula"
}
```

Un sensor es un objeto capaz de detectar magnitudes físicas o químicas y transformarlas en variables eléctricas. Los sensores o periféricos de entrada nos permiten obtener información del mundo real para utilizarla desde el programa de Arduino.

En la actualidad la cantidad de sensores disponibles es tan extensa como las variables que queramos medir, desde sensores de temperatura, humedad, luminosidad,... hasta acelerómetros, giroscopios, GPS,... pasando por detectores de gases, de pulsos cardíacos, sensores de efecto HALL,...

#### Tipos de sensores

- **DIGITAL:** un sensor digital sólo tiene dos estados: activado/desactivado, ON/OFF, 1/0, Alto/Bajo, ... En este caso conectaremos el sensor a una de las entradas digitales de Arduino para leer el estado.

  *Ejemplo:* un pulsador es un tipo de sensor sencillo que sólo nos da dos estados, "pulsado o no pulsado". Conectado a la placa Arduino debe generar 0v en reposo y 5v al pulsarlo. De esta forma desde el programa de Arduino podremos leer el estado del botón.

- **ANALÓGICO:** el sensor nos puede dar un rango de valores, normalmente se traduce en un valor de tensión o de corriente variable en función de la señal captada al sensor. En este caso conectaremos el sensor a una de las entradas analógicas de Arduino (A0,..., A5). El rango de entrada será una tensión entre 0v (GND) y 5v.

  *Ejemplo:* Una fotorresistencia es un componente electrónico cuya resistencia disminuye con el aumento de intensidad de luz incidente. Su valor varía entre 0 y 5 v. la cantidad de valores que pueden leer las entradas analógicas de Arduino son de 10 bits es decir 1024 valores. De tal modo que 0 = 0 v. y 1023 = 5V.

- **DATOS:** el sensor ofrece su información a través de una interfaz de comunicación. La forma de comunicación puede ser por sistemas estándar como I2C o SPI o algunos sensores usan su propio protocolo para codificar la información y debemos realizar desde el software la decodificación correcta para interpretar los datos del sensor (normalmente los desarrolladores de este tipo de sensores ofrecen una librería software para Arduino que hace todo el trabajo).

  *Ejemplo:* el sensor DHT11. Por un solo pin envía los datos de temperatura y humedad.

#### Sensores modulares

En la actualidad existen infinidad de sensores que los fabricantes presentan en forma modular. Esto hace que su conexión y utilización sea mucho más sencilla que la tradicional, olvidándonos de resistencias, polaridades, cableados,... para su correcto funcionamiento.

**Sensor pulsador**

Es un sensor digital, que presenta dos estados; cuando se presiona el botón, emite una señal de bajo (0V), cuando suelta el botón, emite una señal de bajo alto (5V).

```json
{
  "type": "image",
  "id": "image-07",
  "page": 26,
  "title": "Módulo pulsador",
  "caption": "Módulo pulsador para Arduino",
  "description": "Fotografía de un módulo pulsador con botón verde, mostrando los pines de conexión GND, VCC y SIG.",
  "elements": [
    "Módulo pulsador",
    "Pines: GND, VCC, SIG"
  ],
  "source": "CATEDU - ESP32 en el Aula"
}
```

Otra manera más "barata" de sustituir este módulo pulsador es poner un pulsador normal y una resistencia (±10k), al pulsar se produce una entrada en el Arduino, hay dos configuraciones, que al pulsar se emita un 0 lógico (configuración Pull up) o que al pulsar emita un 1 lógico.

Lo "normal" es que al pulsar se emita un '1' configuración Pull down, pero hay pulsadores que funcionan Pull up y los llaman lógica invertida, por eso en la programación por bloques podemos encontrar esto:

```json
{
  "type": "image",
  "id": "image-08",
  "page": 27,
  "title": "Bloques de pulsador con lógica invertida",
  "caption": "Bloques de pulsador en STEAMAKERBLOCKS",
  "description": "Captura de pantalla mostrando los bloques Pulsador, Pulsador (filtrado) y Pulsador táctil con la opción de Lógica invertida resaltada.",
  "elements": [
    "Pulsador Pin 2 Lógica invertida",
    "Pulsador (filtrado) Pin 2 se ha pulsado Lógica invertida",
    "Pulsador táctil Pin 2"
  ],
  "source": "CATEDU - ESP32 en el Aula"
}
```

**Sensor Táctil Capacitivo**

Este pequeño sensor puede "sentir" a las personas y el tacto y la retroalimentación de metales a un nivel de voltaje alto / bajo. Incluso aislado por alguna tela y papel, todavía puede sentir el tacto. Su sensibilidad disminuye a medida que la capa de aislamiento se hace más gruesa. En nuestra opinión lo preferimos frente al Sensor pulsador pues es muy económico, duradero y fiable.

**Potenciómetro y joystick**

Un potenciómetro es una resistencia variable, es decir, cambia de valor mecánicamente, lo tenemos en multitud de dispositivos. El joystick es internamente dos potenciómetros con un pulsador integrado en un solo mando.

```json
{
  "type": "image",
  "id": "image-09",
  "page": 28,
  "title": "Potenciómetro y joystick",
  "caption": "Potenciómetro en la placa TdR STEAM y módulo joystick",
  "description": "Fotografía mostrando el potenciómetro integrado en la placa Imagina TdR STEAM (señalado con un círculo rojo) y un módulo joystick externo.",
  "elements": [
    "Potenciómetro en TdR STEAM (Rotation A0)",
    "Módulo joystick"
  ],
  "source": "CATEDU - ESP32 en el Aula"
}
```

**Sensor Fotocélula LDR**

El uso de fotocélulas es muy común en nuestras vidas, las encontramos en el encendido automático de farolas, apertura de puertas,... La fotocélula es un semiconductor. Es ampliamente utilizado en campos de interruptores de control automático como cámaras, luces solares de jardín, lámparas de césped, detectores de dinero, relojes de cuarzo, tazas de música, cajas de regalo, mini luces nocturnas, interruptores de control de luz y sonido, etc. Es un sensor analógico dando valores entre 0 y 5V y como entrada analógica de un Arduino se traduce en un rango de 0 a 1023 valores.

Una manera más económica de montar este sensor es utilizar una resistencia y un LDR:

- El LDR cuando más oscuridad, más resistencia
- En una configuración PULL DOWN, cuanto más luz, la resistencia del LDR baja, por lo tanto más tensión en A6

Los módulos LDR que se venden suelen esta configuración Pull down, es decir, cuanto más luz, más tensión.

La instrucción con Arduinoblocks ya cuenta con esta configuración Pull downUp de que cuando más luz, más valor tiene la entrada analógica.

```json
{
  "type": "image",
  "id": "image-10",
  "page": 30,
  "title": "Bloque Nivel de luz (LDR)",
  "caption": "Bloque de sensor LDR en STEAMAKERBLOCKS",
  "description": "Captura de pantalla del bloque 'Nivel de luz (LDR)' con Pin A0 y unidad en porcentaje.",
  "elements": [
    "Nivel de luz (LDR) Pin A0 %"
  ],
  "source": "CATEDU - ESP32 en el Aula"
}
```

**Sensor de Ultrasonidos**

Es un sensor digital de distancias por ultrasonidos capaz de detectar objetos y calcular la distancia a la que se encuentra en un rango de 2 a 350 cm. Su uso es tan sencillo como enviar el pulso de arranque y medir la anchura del pulso de retorno.

No es un sensor preciso, con una ligera inclinación de la superficie ya da lecturas erróneas pero es muy barato.

El más común es el HC-SR04 que tiene 4 pines de conexión: VCC, Trig (Disparo del ultrasonido), Echo (Recepción del ultrasonido) y GND aunque en algunos modelos como el de Elecfreaks tiene 3 pines. Integra Trig y Echo en uno sólo.

La distancia se calcula con esta fórmula:

Distancia en cm = {(Tiempo en segundos entre Trig y el Echo) * (V.Sonido 34000 en cm/s)} / 2

Si programas en código, tienes que utilizar la fórmula anterior, previamente tienes que programar.

**Sensor DHT11 (Temperatura y Humedad)**

Este sensor de temperatura y humedad DHT11 nos permite determinar las zonas de confort para un rango de temperaturas entre 0ºC y 50ºC con un error de ± 2ºC y un rango de humedad entre 20 y 90 % ± 5%. Una salida digital para dos variables ¿cómo lo hace? Tiene dentro un pequeño microprocesador que lanza por el bit de datos 40 bits en serie, los 16 primeros son la humedad (en BCD) y los 16 restantes es la temperatura (en BCD) los 8 restantes son de comprobación Checksum (en binario) como la letra del DNI. Por ejemplo 0100 0111 0000 0011 0001 1001 0000 0000 0001 1000 es 0100 0111 0000 0011 = 47.03% de humedad y 0001 1001 0000 0000 = 19.00ºC y la comprobación es la suma de 4+7+0+3+1+9+0+0=24=11000.

No es un sensor con gran sensibilidad, pero para propósitos educativos cumple sus funciones. Por dentro tiene una resistencia NTC que decrementa su resistencia si aumenta la temperatura. Hay otros que van al revés, los PTC. Tanto los NTC como los PTC se llaman thermistores. Para la humedad, mide la capacidad de un condensador que es sensible a la humedad, o sea, un sensor capacitivo.

Tenemos dos opciones comerciales: Encapsulado que lo tienes preparado para conectar la alimentación y leer por el pin de datos, o sin encapsular, que hay que colocar una resistencia de aproximadamente 10k entre Vcc y Data.

Si queremos mejorar la sensibilidad, podemos utilizar el DHT22 que es igual pero de color blanco y más caro. Si lo que queremos es sólo la temperatura es mejor utilizar el LM35D que tiene un rango de temperaturas desde 0ºC a 100ºC con una sensibilidad de 2mV/ºC.

```json
{
  "type": "image",
  "id": "image-11",
  "page": 34,
  "title": "Bloque Temperatura ºC (LM35)",
  "caption": "Bloque de sensor LM35 en STEAMAKERBLOCKS",
  "description": "Captura de pantalla del bloque 'Temperatura ºC (LM35)' con Pin A0.",
  "elements": [
    "Temperatura ºC (LM35) Pin A0"
  ],
  "source": "CATEDU - ESP32 en el Aula"
}
```

**Sensor IR**

Es un sensor para distancias cortas hasta 2cm y no da la distancia, simplemente si hay o no hay obstáculo, pero son muy baratos, unos 0.30€.

**Sensor llama**

Este sensor de llama se puede utilizar para detectar fuego u otras luces cuya longitud de onda se encuentra entre 760 nm ~ 1100nm.

**Sensor de Gas (MQ2)**

Detecta gases inflamables: GLP, I-butano, propano, metano, alcohol, hidrógeno, humo... con más sensibilidad en algunos que en otros. Siempre detecta el conjunto. Son usados en electrónica de consumo y mercados industriales.

- Sensibilidad: Tiene alta sensibilidad y se puede ajustar girando el potenciómetro.
- Tiempo de respuesta: Internamente posee un calentador para aumentar su temperatura y que estos gases reaccionen con la resistencia interna que tiene, por lo tanto tardan algo en responder la primera vez que se conectan, incluso horas en algunos modelos. Una vez calentados son rápidos en la respuesta.
- Tipo de salida: Analógico pero si tiene 4 pines como el de la figura, incorpora un pin digital.

**Sensor de humedad de suelo**

Un higrómetro de suelo FC-28 es un sensor que mide la humedad del suelo. Son ampliamente empleados en sistemas automáticos de riego para detectar cuando es necesario activar el sistema de bombeo. El FC-28 es un sensor sencillo que mide la humedad del suelo por la variación de su conductividad. No tiene la precisión suficiente para realizar una medición absoluta de la humedad del suelo, pero tampoco es necesario para controlar un sistema de riego. Los valores obtenidos van desde 0 sumergido en agua, a 1023 en el aire (o en un suelo muy seco). Un suelo ligeramente húmero daría valores típicos de 600-700. Un suelo seco tendrá valores de 800-1023.

Se puede utilizar este sensor para hacer un dispositivo de riego automático, puede detectar si las plantas "tienen sed" y evitar que se marchiten.

La corriente de trabajo del sensor es menor de 20mA. El voltaje de salida es de 0V (en el aire) a 2,3V (totalmente sumergido en agua).

**Sensor de humedad**

Este sensor analógico está diseñado para identificar y detectar la presencia de agua y su cantidad. Puede servir para detectar el nivel de agua, para disparar una alarma en caso de una fuga de agua, también para hacer un limpiaparabrisas automático...

**Sensor de efecto Hall**

Este es un sensor de inducción magnética. Detecta los materiales magnéticos dentro de un rango de detección de hasta 3 cm. El rango de detección y la fuerza del campo magnético son proporcionales. La salida es digital.

Edwin Helbert Hall descubrió en 1879 que en presencia de un campo magnético, un conductor que conduzca una corriente se le producía un campo eléctrico porque las cargas eléctricas se desviaban de su trayectoria principal, nuestro sensor simplemente mide ese campo eléctrico.

El sensor tiene un led de color rojo que indica que hay una lectura de campo magnético.

**Sensor inclinación**

Este sensor funciona al hacerle vibrar, emitiendo una señal digital de todo o nada. El módulo del sensor viene provisto de un potenciómetro para poder regularlo.

**Sensor de golpe**

Es un sensor digital que al ser golpeado este sensor envía una señal momentánea.

**Sensor de pulso cardíaco**

Este módulo utiliza un LED infrarrojo (IR) ultrabrillante y un fototransistor para detectar el pulso en el dedo. Principio de funcionamiento: Se debe colocar el dedo entre el LED infrarrojo ultrabrillante (parte superior) mientras que el fototransistor, que queda en el otro lado, recoge la cantidad de luz transmitida. La resistencia del fototransistor variará levemente a medida que la sangre pase a través de su dedo.

**Sensor de Alcohol**

Este sensor de gas analógico MQ-3 es adecuado para detectar alcohol. Se puede usar en un analizador de aliento. También tiene una alta sensibilidad al alcohol y baja sensibilidad a la bencina (éter de petróleo). La sensibilidad se puede ajustar con el potenciómetro.

**Sensor de CO2**

Hay sensores que utilizan el protocolo I2C, este protocolo permite conexiones serie y pueden compartir el mismo cable pues cada elemento tiene una dirección diferente. Esto lo veremos en el Display LCD. Se identifican por los pinen SDA y SCL.

**Resistencia Flex**

Es una resistencia que cuanto más se dobla más resistencia ofrece, desde 25k hasta 125k.

Para utilizar esta resistencia haremos un DIVISOR DE TENSIÓN que consistirá en poner dos resistencias en serie y repartirá la tensión total entre 0V y 5V en las dos resistencias, el punto medio será un punto que tendrá una tensión variable en función de las dos resistencias, como la es variable, esa tensión es variable y ya tenemos la entrada analógica.

Es decir:

- La resistencia entre masa GND del ARDUINO (cable negro) y un punto en la placa protoboard
- ese punto medio conectarlo a una entrada analógica, por ejemplo A0 (cable amarillo)
- Una resistencia de valor parecida a la Flex de decenas de K entre ese punto y +5V (cable rojo en la foto)

Este sensor tiene posibilidades para usarlo en "ropa inteligente".

**Sensor de movimiento**

Los sensores infrarrojos pasivos (PIR) son dispositivos para la detección de movimiento. Son baratos, pequeños, de baja potencia, y fáciles de usar. Por esta razón son frecuentemente usados en juguetes, aplicaciones domóticas o sistemas de seguridad.

Los sensores PIR se basan en la medición de la radiación infrarroja. Todos los cuerpos (vivos o no) emiten una cierta cantidad de energía infrarroja, mayor cuanto mayor es su temperatura. Los dispositivos PIR disponen de un sensor piro eléctrico capaz de captar esta radiación y convertirla en una señal eléctrica. En realidad cada sensor está dividido en dos campos y se dispone de un circuito eléctrico que compensa ambas mediciones. Si ambos campos reciben la misma cantidad de infrarrojos la señal eléctrica resultante es nula. Por el contrario, si los dos campos realizan una medición diferente, se genera una señal eléctrica.

De esta forma, si un objeto atraviesa uno de los campos se genera una señal eléctrica diferencial, que es captada por el sensor, y se emite una señal digital.

El otro elemento restante para que todo funcione es la óptica del sensor.

Básicamente es una cúpula de plástico formada por lentes de fresnel, que divide el espacio en zonas, y enfoca la radiación infrarroja a cada uno de los campos del PIR.

De esta manera, cada uno de los sensores capta un promedio de la radiación infrarroja del entorno. Cuando un objeto entra en el rango del sensor, alguna de las zonas marcadas por la óptica recibirá una cantidad distinta de radiación, que será captado por uno de los campos del sensor PIR, disparando la alarma.

Más sensibles son los sensores de microondas. Son un radar que por efecto Doppler pueden captar cualquier objeto en movimiento dentro de un alcance de 5-7 metros en cualquier dirección e independiente de su temperatura. Es un buen sensor para alarmas, activación de luz por presencia.

Su conexión es muy sencilla, es un detector digital que hay que alimentarlo como el resto de sensores.

> Curiosamente, la gran ventaja técnica de los de microondas es un gran inconveniente para usarlo en el aula, con cualquier movimiento se dispara, luego para clase es mejor el sensor PIR.

---

### Actuadores y otras salidas

Esta página es un repaso rápido de las posibles salidas de los robots NO LEAS TODOS SÓLO LOS QUE TIENE TU ROBOT.

#### ¿Qué es un actuador?

Un actuador es el nombre genérico que empleamos para cualquier dispositivo capaz de realizar acciones en el mundo físico y que podremos controlar desde un autómata o procesador como Arduino. En particular, usamos el nombre actuador para los dispositivos que son capaces de generar movimiento.

#### ACTUADORES

**Motores baja potencia**

Con el Arduino podemos usar motores de corriente continua de juguete como en la figura, aptos para poner un ventilador.

**Motores con algo de potencia**

Si quieres usar un motor para mover unas ruedas, ya pide más corriente, no se puede conectar directamente al la placa (Arduino, esp32 etc..). El de la figura es típico en robótica y lleva reductores dentro para bajar la velocidad.

Necesita una alimentación extra, como el LM298N y las pilas., o el B6612FNG o una shield específica.

Los motores pueden (y deben) de estar conectados a salidas PWM de tal manera que se pueda regular la potencia y por lo tanto la velocidad.

**Servos**

Un servo convencional es un motor donde fijamos el ángulo desde 0º a 180º, pero si queremos una rotación, existen servos rotatorios que simplemente tienen su velocidad de rotación controlada.

**Relés**

Un relé es un interruptor activado por un electroimán, lo que permite independizar los circuitos. En el dibujo se ve que el circuito rojo de 220V esta separado del verde, de sólo 1.5V. Pero es el circuito verde que al funcionar, hace que el electroimán mueva el interruptor del relé y encienda la bombilla. El objetivo es que he podido encender una bombilla de 220V sin tocar los 220V peligrosos. En el circuito verde, el interruptor puede ser un Arduino.

**Electroimán**

El electroimán no se puede conectar directamente, utilizaremos una etapa de potencia, por ejemplo el transistor el IRF520N que amplifique la señal del Arduino, pues las salidas de Arduino no tienen potencia para mover el electroimán. Para dar esa potencia utilizaremos otra fuente externa, unas pilas.

Las conexiones son:

- SIG del IRF520N a una salida digital por ejemplo D13
- VCC del IRF5020N al 5V del ARDUINO
- Los dos GND del IRF520N a GND del ARDUINO
- V+ y V- del IRF5020N al solenoide, da igual qué cable pues no tiene polaridad.
- VIN del IRF520N al VIN del ARDUINO (son los voltios de la pilas)

**Motor paso a paso**

Igual que el electroimán, necesitamos un controlador que nos de la potencia necesaria para mover el motor, el ULN2003.

También igual que el electroimán, necesitamos una potencia extra con las pilas.

#### OTRAS SALIDAS

No son actuadores pues no representan movimiento pero son también salidas del Arduino como los actuadores, luego lo vemos en esta página.

**Buzzer activo**

Reproduce un tono de una frecuencia determinada por el fabricante cuando recibe un '1' digital. Su conexión es muy simple:

- GND a GND y VCC a 5V (ojo que están a los dos extremos, marcados en rojo y en negro)
- OUT o también señalado como I/O a un pin digital, por ejemplo D13

**Buzzer pasivo**

La diferencia de un buzzer activo con el pasivo es que el pasivo hay que mandar la onda que se tiene que reproducir, como Arduino no puede reproducir onda puras (senoidales analógicas), se le envía ondas cuadradas con la frecuencia que se pretende reproducir. Como se puede ver en la figura, no tiene elementos auxiliares para reproducir un tono, es simplemente un altavoz.

#### LEDS Y OTROS ELEMENTOS VISUALIZADORES

**Led normal**

Un diodo es la unión de dos semiconductores P-N que sólo permite la corriente en un sentido. Un diodo LED es un diodo, que al pasar esta corriente emite una luz. Hay de 3mm y de 5mm de grosor, transparentes, traslúcidos y de colores (realmente son traslúcidos tintados).

Tenemos pues que respetar su polaridad para que funcione.

Si alimentamos el LED con una tensión inferior a su tensión de polarización directa Vd ±1,4V-3,8V el led no luce. si alimentamos con una tensión superior, la corriente que circula se dispara por lo que se rompe. Conclusión: Hay que poner una resistencia limitante.

Se puede conectar directamente pues las salidas de Arduino tienen una limitación interna de 20mA.

Los LEDS igual que los motores pueden se encendidos o todo o nada con salidas digitales 0 y 1 o salidas PWM de esta manera conseguimos luminosidades medias, en esta práctica con el potenciómetro se regula la intensidad de la luz de un LED.

**Led RGB**

Se trata de un encapsulado que integra 3 leds de los tres colores básicos. Cada color básico se puede regular desde 0 a 255 de intensidad, luego tenemos 16 millones de tonalidades diferentes.

Existen LEDS RGB que se comunican unos a otros, como las tiras de leds RGB que cambian de color todos simultáneamente.

**Neopixel**

La cinta LED RGB se basa en el chip controlador WS2812B de Neopixel con el cual podemos tener el control de cada pixel y de cada color, ya sea rojo, verde y azul a través de un solo cable de datos.

Los WS2811, WS2812 y WS2812B son LED que disponen de lógica integrada, por lo que es posible variar el color de cada LED de forma individual (a diferencia de las tiras RGB convencionales en las que todos los LED cambian de color de forma simultánea). Están basados en el LED 5050, llamado así porque tiene un tamaño de 5.0 x 5.0 mm.

Es un LED de bajo consumo y alto brillo, que incorpora en un único encapsulado los 3 colores RGB. La genial novedad del WS2812B (y resto de familia) es añadir un integrado dentro de cada LED, que permite acceder a cada pixel de forma individual. Por este motivo este tipo de LED se denominan "individual addressable". Esto abre la puerta a un sinfín de aplicaciones y combinaciones, que van desde dotar de iluminaciones distintas zonas con una única tira, animaciones complejas, o incluso generar pantallas enteras de alta luminosidad....

A los LED WS2812B también se les denomina NeoPixel.

**Láser**

El diodo láser es un elemento motivador, barato y fácil de usar con el Arduino pues se activa digitalmente, si enviamos un 1 emite un rayo láser.

> Si tienes que comprar uno, es importante que no sea superior a 5mW, pues puede dañar permanentemente la retina del ojo. El modelo que proponemos es de 1mW, no obstante, EVITA SIEMPRE QUE EL LÁSER APUNTE A LOS OJOS especialmente con niños.

**Display LCD**

Si queremos visualizar datos de forma independiente del ordenador, existen matrices de led que puedes ver en los cursos de mBot o mClon pero lo mejor es una pantalla Liquid Crystal Display y la mejor forma de conectar esta interfaz es en serie utilizando el protocolo I2C.

No confundas Display LCD con matriz de LEDs, o una OLED.

**Aclarando conceptos: Protocolo I2C**

Es un protocolo de emitir los datos con sólo dos cables SDA (los datos) y SCL (reloj) y además pueden compartir varios dispositivos SLAVE) para ello la placa Arduino ESP32, microbit... (MASTER) tiene que saber qué dirección tiene cada dispositivo IMPORTANTE.

**Aclarando conceptos: Lógica invertida**

Igual que vimos en sensores, con las configuraciones Pull up y Pull down, las salidas de cualquier actuador PUEDEN SER LÓGICA INVERTIDA, mira en este NodeMCU (básicamente es un Arduino con wifi, aquí está conectado con el servidor Blynk) como funciona al revés, cuando apretamos, por lo tanto enviamos un uno a la salida, se apaga la salida !!

---

### Sensores y actuadores de la placa Imagina TDR STEAM

> **ATENCIÓN, ANTES DE SUBIR UN PROGRAMA A TU PLACA TIENES QUE:**
> - TENER EL POTENCIÓMETRO (8) A CERO, DE LO CONTRARIO PUEDE DAR ERROR AL SUBIRLA. LA FLECHA DEL POTENCIÓMETRO QUE APUNTE AL PUNTO ROJO.
> - El interruptor del Bluetooth tiene que estar hacia al borde.

El motivo es que el potenciómetro comparte la conexión A0 (GPIO02) con el sistema de grabación del programa y si el mismo no está en su posición de cero resistencia se producirá un error en el envío del programa a la placa porque se entenderá que los pines de transmisión están ocupados con otra tarea. (Federico Coca Notas sobre ESP32 STEAMakers CC-BY-SA)

El interruptor del Bluetooth tiene que estar hacia al borde de lo contrario no se comunica con el puerto COM.

La placa Imagina TDR STEAM es una placa didáctica desarrollada por el equipo ROBOLOT que presenta la gran ventaja de tener una gran cantidad de sensores, actuadores y conexiones de expansión incorporados directamente en ella. Únicamente hay que conectar esta placa a una placa Arduino UNO (en nuestro caso, una placa compatible llamada Keyestudio UNO) y ya está todo listo para empezar a programar.

```json
{
  "type": "image",
  "id": "image-12",
  "page": 60,
  "title": "Placa Imagina TdR STEAM",
  "caption": "Placa Imagina TdR STEAM con elementos numerados",
  "description": "Diagrama de la placa Imagina TdR STEAM con círculos rojos numerados que señalan cada uno de sus componentes: pulsadores, LEDs, LED RGB, sensor DHT11, zumbador, puertos digitales, receptor IR, potenciómetro, sensor de luz LDR, sensor de temperatura LM35, conector I2C, puerto analógico A3, conector Bluetooth/WiFi y botón de reset.",
  "elements": [
    "1. Dos pulsadores (SW1, SW2)",
    "2. Dos leds (Azul Led3 y Rojo Led4)",
    "3. Led RGB",
    "4. Módulo DHT11 Sensor de Temperatura y Humedad",
    "5. Zumbador o Piezoelectrico",
    "6. Dos puertos (Entradas/Salidas) digitales",
    "7. Módulo receptor de infrarrojos (IR)",
    "8. Módulo potenciómetro giratorio",
    "9. Sensor de luminosidad (LDR)",
    "10. Sensor de temperatura (LM35)",
    "11. Interface I2C compatible con sensores y módulos Keyestudio",
    "12. Puerto Entrada Analógico A3",
    "13. Conexión de comunicaciones Bluetooth y Wifi (Swich On/Off)",
    "14. Botón de reinicio"
  ],
  "source": "CATEDU - ESP32 en el Aula"
}
```

Tabla con la relación de elementos que hay en la placa Imagina TDR STEAM y sus conexiones:

```json
{
  "type": "table",
  "id": "table-02",
  "page": 61,
  "title": "Elementos de la placa Imagina TDR STEAM y sus conexiones",
  "headers": ["Nº", "Sensor/Actuador/Módulo", "Pin de conexión"],
  "rows": [
    ["1", "Dos pulsadores (SW1, SW2)", "D2 y D7"],
    ["2", "Dos leds (Azul Led3 y Rojo Led4)", "D13 y D12"],
    ["3", "Led RGB", "D6-D9-D10"],
    ["4", "Módulo DHT11 Sensor de Temperatura y Humedad", "D4"],
    ["5", "Zumbador o Piezoelectrico", "D8"],
    ["6", "Dos puertos (Entradas/Salidas) digitales", "D3 y D5"],
    ["7", "Módulo receptor de infrarrojos (IR)", "D11"],
    ["8", "Módulo potenciómetro giratorio", "A0"],
    ["9", "Sensor de luminosidad (LDR)", "A1"],
    ["10", "Sensor de temperatura (LM35)", "A2"],
    ["11", "Interface I2C compatible con sensores y módulos Keyestudio", "SDA-A4, SCL-A5"],
    ["12", "Puerto Entrada Analógico", "A3"],
    ["13", "Conexión de comunicaciones Bluetooth y Wifi (Swich On/Off)", "Rx - Tx"],
    ["14", "Botón de reinicio", "-"]
  ],
  "notes": "ATENCIÓN: EN LA PLACA ESP32, SI SE UTILIZA LA COMUNICACIÓN WIFI DEJA DE FUNCIONAR A0 Y A1 ES DECIR EL POTENCIÓMETRO Y EL LDR",
  "source": "Equipo de Innova Didàctic y Robotol Team. Licencia CC-BY-NC-ND"
}
```

---

### Sensores en la placa ESP32 plus STEAMakers

Página extraída de Federico Coca Notas sobre ESP32 STEAMakers CC-BY-SA

La placa ESP32 Plus STEAMakers se basa en el microcontrolador ESP32-WROOM-32 que dispone de dos sensores internos. Se trata de un sensor de efecto hall y un sensor de temperatura.

La placa ESP32 Plus STEAMakers lleva implementado un medidor de tensión e intensidad con el que podemos saber la tensión de alimentación en todo momento. Si la tensión de alimentación baja de aproximadamente 4,8V la placa no funcionará correctamente (sobre todo la transmisión WiFi). Es recomendable realizar una verificación de la tensión que está entregando el puerto USB del ordenador. Si la tensión no es próxima a 5V deberemos cambiar el cable USB, alimentar el puerto USB de forma externa o alimentar la placa con una fuente de alimentación. Es decir, dispone de un sistema para poder medir el consumo de energía.

Los bloques para trabajar con estos sensores están en 'Sensores', entrada 'Integrados', y son los que vemos en la figura siguiente:

```json
{
  "type": "image",
  "id": "image-13",
  "page": 64,
  "title": "Bloques de sensores integrados",
  "caption": "Bloques de sensores integrados en STEAMAKERBLOCKS",
  "description": "Captura de pantalla del menú de sensores integrados en STEAMAKERBLOCKS, mostrando opciones como Tiempo, Entrada/Salida, Sensores, Integrados, Receptor IR.",
  "elements": [
    "Tiempo",
    "Entrada/Salida",
    "Sensores",
    "Integrados",
    "Receptor IR"
  ],
  "source": "Federico Coca - Notas sobre ESP32 STEAMakers CC-BY-SA"
}
```

---

### Software

Hemos visto que el ESP32 acepta código IDE Arduino, por lo tanto puede programarse como un Arduino, (acepta microPython, mBlock, etc… ) pero nuestra recomendación es programarlo con bloques gráfico con dos opciones:

- **STEAMAKERSBLOCKS** (antes ARDUINOBLOCKS) es el programa que se usa en este tutorial
  - es lento cargando el programa y hay que tener bien instalado Connector
  - Sólo online
  - permite programas IoT
  - tiene una buena gestión de alumnado ideal para envío de proyectos y corregirlos
  - tiene un canal de Telegram de apoyo al docente: https://t.me/innovadidactic_comunidad

- **MICROBLOCKS** El tutorial recomendado es: https://pedroruizf.github.io/steamakersmicroblocks
  - no permite muchos programas IoT
  - es muy rápido al ejecutar y no da problemas de configuración
  - local o online
  - https://docs.google.com/presentation/d/e/2PACX-1vQb1Dv9wN9QK-F6V7yvwDoyzquqwWIGvlvYlIr83Yk56kAoYD7bXLnYDmtCQkeAqq/pubembed?start=falseLoop=false&delayms=3000

---

## 2. STEAMAKERBLOCKS

Esto no pretende ser un tutorial exhaustivo de STEAMAKERSBLOCKS, sino una guía rápida. STEAMAKERSBLOCKS es un programa que tiene muchas posibilidades. Si quieres saber más sobre ARDUINOBLOCKS tutoriales, ejemplos, foro.... te recomendamos http://arduinoblocks.didactronica.com/ o el libro Arduino blocks - libros y tutoriales.

> **IMPORTANTE SABERLO: TENEMOS UN CHAT DE Ayuda en STEAMAKERSBLOCKS**
> hay chat de Telegram con una comunidad de profesores y técnicos de la empresa que apoya Arduinoblocks donde puedes encontrar proyectos, enlaces interesantes y lo más importante: Puedes preguntar tus dudas o problemas
> https://t.me/innovadidactic_comunidad

#### ¿Por qué una programación con bloques?

Arduino se programa en lenguaje C++ (con algunas variaciones para simplificarlo). Para programar normalmente se utiliza el IDE ("Integrated Development Environment"/"Entorno de Desarrollo Integrado") de Arduino, que permite escribir el código, compilar el programa (crear el programa binario para el procesador Arduino) y grabarlo en la placa Arduino a través del puerto USB. El IDE de Arduino se puede descargar desde la web oficial. Es totalmente libre.

Sin embargo pensando en edades más tempranas se han desarrollado formas más sencillas e intuitivas de programar Arduino como son los lenguajes de programación por bloques. De todos estos lenguajes cabe destacar STEAMAKERSBLOCKS.

Gracias a este lenguaje visual podemos programar las placas Arduino sin necesidad de escribir ni una sola línea de código, de esta forma podemos empezar a realizar proyectos con Arduino de una forma muy rápida y a edades más tempranas. La única desventaja es que el lenguaje por código tiene todo el potencial que requiere la programación de un experto.

Mismo programa creado con el IDE de Arduino en C++ (imagen de la izquierda) y con Arduinoblocks (imagen de la derecha).

```cpp
void setup() {
  pinMode(13, OUTPUT);
}
void loop() {
  digitalWrite(13, HIGH);
  delay(500);
  digitalWrite(13, LOW);
  delay(500);
}
```

```json
{
  "type": "image",
  "id": "image-14",
  "page": 68,
  "title": "Comparación de código Arduino y bloques",
  "caption": "Mismo programa en IDE Arduino y en Arduinoblocks",
  "description": "Captura de pantalla que muestra el mismo programa (parpadeo de LED) escrito en código Arduino C++ y en bloques de Arduinoblocks.",
  "elements": [
    "Código Arduino: void setup() { pinMode(13, OUTPUT); } void loop() { digitalWrite(13, HIGH); delay(500); digitalWrite(13, LOW); delay(500); }",
    "Bloques Arduinoblocks: BucLe -> Escribir digital Pin 13 ON -> Esperar 500 milisegundos -> Escribir digital Pin 13 OFF -> Esperar 500 milisegundos"
  ],
  "source": "José Andrés Echevarría @cantabRobots CC-BY-NC-SA"
}
```

Para trabajar con Arduinoblocks debemos ir a su página web http://www.arduinoblocks.com/ desde cualquier navegador y para cualquier sistema operativo (Windows, Linux, Mac).

#### STEAMAKERSBLOCKS (antes Arduinoblocks)

STEAMAKERSBLOCKS es un programa creado por el profesor Juanjo López. Gracias a su entorno gráfico facilita la programación de placas Arduino a todos los niveles. Esta herramienta permite programar a personas sin conocimientos previos de programación, pero su versatilidad y potencia es tan grande que expertos programadores también pueden utilizarlo.

La programación en STEAMAKERSBLOCKS se realiza con bloques al estilo AppInventor o Scratch, se puede utilizar a partir de 8 años. No tenemos que escribir líneas de código y no nos permitirá unir bloques incompatibles evitando así posibles errores de sintaxis. La plataforma STEAMAKERSBLOCKS genera, compila y sube el programa a la placa Arduino por medio de la conexión USB. Una vez subido el programa, la placa el Arduino no necesitará de la conexión al PC para funcionar pudiendo alimentarla con baterías o una fuente de alimentación para que funcione de forma autónoma.

STEAMAKERSBLOCKS actualmente funciona con todos los navegadores de última generación: Mozilla Firefox, Google Chrome, Opera, Safari,...

Por otro lado, tal y como se describe en la Wiki de Vitalinux, STEMAKERSBLOCKS funciona perfectamente con todos los sistemas operativos, pudiendo ser fácilmente instalable en equipos individuales y a nivel de centro dentro del soporte de Vitalinux.

### Crear cuenta en STEAMAKERBLOCKS

Registrándonos como usuarios de la plataforma Steamakerblocks podemos aprovechar todas estas posibilidades:

- Guardar tus proyectos en la nube de Steamakerblocks.
- Añadir información al proyecto: descripción, componentes utilizados, imágenes, etc.
- Añadir archivos adjuntos relacionados con el proyecto: esquemas, fotos, archivos para impresión 3D, aplicaciones, etc.
- Compartir proyectos con el resto del mundo.
- Importar proyectos compartidos por otros usuarios.
- Valorar y comentar proyectos.
- Programar directamente Arduino desde el propio navegador (con la aplicación: Steamakerblocks -Connector).
- Utilizar la consola serie desde el propio navegador.

Entramos en https://www.steamakersblocks.com/ e iniciamos sesión.

```json
{
  "type": "image",
  "id": "image-15",
  "page": 71,
  "title": "Página de inicio de STEAMAKERBLOCKS",
  "caption": "Página de inicio de STEAMAKERBLOCKS",
  "description": "Captura de pantalla de la página de inicio de STEAMAKERBLOCKS mostrando las secciones 'Por donde empezar...', 'Libros & Documentación' y 'Enlaces', con botones para 'Probar ahora' e 'Iniciar sesión'.",
  "elements": [
    "Botón 'Probar ahora'",
    "Botón 'Iniciar sesión'",
    "Sección 'Por donde empezar...'",
    "Sección 'Libros & Documentación'",
    "Sección 'Enlaces'"
  ],
  "source": "CATEDU - ESP32 en el Aula"
}
```

Y rellenamos el formulario.

### Cuentas alumnos

Tal y como dice el tutorial de Juanjo López: Permite a un usuario registrado con email, crear y administrar nuevas cuentas de usuario dentro de una organización, centro educativo o institución.

- Permite crear usuarios alumnos sin necesidad de ceder ningún tipo de datos
- https://www.youtube.com/embed/zdzK0NX60Y

- Si lo quieres en papel, te recomendamos el tutorial de Juanjo López son 12 diapositivas muy bien explicados
  - Repositorio Github
  - Repositorio en steamakerblocks.com

- Prueba con Catedu:
  - https://www.steamakersblocks.com/
  - usuario alumnos.catedu donde x de 1 a 20
  - contraseña [donde esta catedu en minúsculas]

### Connector

#### PRIMER PASO: Descargar e instalar Connector

Para poder usar la herramienta Steamakerblocks tenemos que ejecutar antes Connector. Lo descargamos de la misma página de Steamakerblocks según el sistema operativo que usemos: Windows (W7 E INFERIORES NO FUNCIONA), Linux ....

Entra en https://www.steamakersblocks.com/ y en Recursos, tienes la web para descargar este programa.

Lo descargamos y lo instalamos.

En el caso de tener equipos Vitalinux, es fácilmente accesible e instalable desde la aplicación Vitalinux Play o si se desea una instalación masiva en el centro a través de su página de soporte:

#### SEGUNDO PASO: INSTALAR LOS DRIVERS

Si no hacemos estos pasos, cuando conectamos la placa, siempre sale en el COM1, le damos a subir y sale error.

En http://www.arduinoblocks.com/web/site/abconnector5 tenemos abajo ARDUINO SERIAL DRIVERS.

RECOMENDAMOS EL PRIMER ENLACE Y EL TERCERO.

En el primero el instalador está en este enlace: https://cdn.sparkfun.com/assets/learn_tutorials/7/4/CDM21228_Setup.exe

#### COMPROBAR QUE DETECTA LA PLACA

Ahora conectamos la placa (ESP32, Arduino, NodeMCU, KeyStudio TDR STEAM...) a nuestro ordenador, y observamos si lo detecta, en Windows entramos en Administrador de dispositivos:

Y vemos que en los puertos COM se ha detectado correctamente la placa:

En el caso de que no aparezca, es que no se han instalado correctamente los drivers de Arduino. Entonces vamos a la página oficial de Arduino y descargamos el programa ARDUINO IDE: https://www.arduino.cc/en/software y lo instalamos. Al instalar este programa se instalan los drivers en nuestro ordenador. No hace falta ejecutarlo.

En el caso de equipos con sistema operativo Linux (como Vitalinux) el puerto serie tiene la forma /dev/XXXX

#### YA PUEDES EJECUTAR ARDUINOBLOCKS CONNECTOR

Ahora buscamos el programa ArduinoBlocks connector que hemos descargado e instalado en el primer paso y lo ejecutamos.

> **ATENCIÓN:** No podemos cerrar la ventana mientras utilizamos Arduinoblocks, la minimizamos simplemente.
> En caso contrario, Arduinoblocks no se puede comunicar con nuestra placa Arduino, NodeMCU, KeyStudio, etc ....

#### YA PUEDES EJECUTAR ARDUINOBLOCKS

Entramos en la web ARDUINOBLOCKS http://www.arduinoblocks.com/ nos logueamos e iniciamos un proyecto, Vemos que en el editor que aparece ya los puertos COM (si no te aparece, dale a la rueda actualizar).

Aparecen varios COM, elegir el último que tiene que coincidir con el que has visto en el segundo paso, no necesariamente es el COM más alto.

Si se queda una ruleta de espera demasiado tiempo, entonces, actualizar la página o darle a actualizar el botón.

Una vez elegido el COM ya puedes darle al botón amarillo SUBIR cuando has realizado tu proyecto pero antes de subir, por si acaso dale a guardar el proyecto que has realizado.

En el caso de equipos con Linux veremos algo así:

¿Tengo que hacer los cuatro pasos cada vez? No, sólo la primera vez para asegurar los drivers del Arduino, las siguientes veces que te conectes lo único que tienes que hacer es el tercer y cuarto paso.

> **IMPORTANTE: TENER EL SOFTWARE ARDUINOBLOCKS ACTUALIZADO** para que funcionen los nuevos bloques que se incorporan en Arudinoblocks.

### Empezando un proyecto

Entramos en Proyectos y podemos ver nuestros proyectos creados como también empezar uno.

Y nos aparece tres opciones:

- **Proyecto Personal:** Iniciar un nuevo proyecto que sólo será accesible para el usuario. Posteriormente se puede compartir al resto de la comunidad si se desea.
- **Proyecto Profesor:** Iniciar un proyecto como profesor. De esta forma no se inicia un proyecto como tal, sino que se especifican los datos del proyecto y se genera un código para que los alumnos se puedan suscribir al proyecto. El profesor podrá supervisar y valorar los proyectos de sus alumnos.
- **Alumno:** De esta forma nos unimos a un proyecto planteado por el profesor.

Nosotros realizaremos el proyecto como si de un proyecto personal se tratara, pero el profesor podrá supervisar y valorar nuestro trabajo.

Lo primero que tenemos que elegir es para qué tipo de placa se hace el proyecto.

- En el caso de que estés con el kit de CATEDU **Rover marciano con Arduinoblocks** el tipo de proyecto es para **ESP8266 / NodeMCU**
- En el caso de que estés con el kit de CATEDU **Arduino con Arduinoblocks** el tipo de proyecto es para **Arduino UNO**
- En el caso de que estés con el kit de CATEDU **STEAMAKERSBLOCKS en el aula** tienes dos opciones totalmente válidas:
  - **ArduinoUno**
  - **ArduinoUno + Imagina TdR STEAM**
- En el caso de que estés con el kit de CATEDU **ESP32 en el aula** tienes dos opciones totalmente válidas:
  - **ESP32 STEAMakers**
  - **ESP32 STEAMakers + Imagina TdR STEAM**
- En el caso de que estés con el kit de CATEDU **SMARTHOME ESP32** tienes que elegir:
  - **ESP32 STEAMakers**

> **ATENCIÓN:** luego NO se puede cambiar. Es decir, un proyecto realizado para un tipo de placa, no se puede cambiar a otro tipo de placa (la razón es simple: las instrucciones cambian).

Luego el nombre y el resto de campos es optativo pero importante y buena costumbre rellenarlos, sobre todo si el proyecto lo compartimos:

- Descripción
- Componentes
- Comentarios

#### Área de programación del proyecto

Este es el área sobre el que se trabaja en Arduinoblocks. En esta área arrastraremos y colocaremos los bloques que vamos a utilizar para crear nuestro programa.

En el área de trabajo hay un Zoom (2) para ampliar o reducir la imagen, un icono para centrar (1) y un icono donde podremos borrar los bloques que no utilicemos (3).

Las principales secciones del área de programación son las siguientes:

- **Herramientas:** Lógica, Control, Matemáticas, Texto, Variables, Listas, Funciones, Entrada/Salida, Tiempo, Puerto serie, Bluetooth, Sensores, Actuadores, Pantalla LCD, Memoria, Motor, Motor-Shield, Keypad, Reloj RTC, GPS
- **Área de programa:** Bloque de iniciación, Bloque de bucle, Opciones, Puerto de conexión de la placa Arduino, Mostrar la consola serie, Ver el código

#### Ver el código

ArduinoBlocks genera el código de Arduino a partir de los bloques. El programa se puede compilar y subir directamente a la placa Arduino gracias a la aplicación ArduinoBlocks-Connector, sin embargo si deseamos ver o descargar el código podemos realizarlo desde el área de bloques.

Siempre, desde un lenguaje de programación en bloques podemos obtener su equivalente a Código de Arduino IDE (de hecho es lo que hacen los programas), y luego con las funciones de Código de Arduino IDE el software lo pasa a lenguaje máquina que es la que se graba el Arduino, pero no al revés es decir, no existen programas que dado un código máquina o código Arduino IDE lo pasen a bloques gráficos, (igual que no hay programas que lean el código máquina que hay grabado en un Arduino y lo pasen a código Arduino IDE). Esto no es del todo 100% verdadero pues la Ingeniería inversa en informática trata pues de eso: obtener la fuente aunque sea parcial, pues si obtienes el código legible, puedes alterar lo que quieras.

Cuando compras un programa comercial, te dan el lenguaje máquina ilegible. Mientras que los programas de software libre se publica el código fuente legible para que todo el mundo pueda mejorarlo.

#### Con Imagina TdR STEAM ¿Qué tipo de proyecto elijo?

Para aclarar, las dos opciones son válidas para nuestros proyectos, pero la específica con Imagina TdR STEAM es más cómoda:

- La placa sola (ESP32 STEAMakers) donde te aparecerán todos los sensores y salidas con todas las posibilidades de entradas y salidas (E/S) de la placa (Arduino o ESP32)
- La placa (ESP32 STEAMakers) + Imagina TdR STEAM donde aparecen:
  - Los sensores y salidas específicas de la placa TdR STEAM ya conectadas en sus respectivos pines E/S del ESP32.
  - En contra, algunos sensores ya no aparecen todas las E/S del Arduino que están ocupadas por los elementos de la placa TdR STEAM.

**Vamos a poner un ejemplo: Hacer una intermitencia con el LED AZUL del TdR STEAM**

Si lo hacemos con el tipo de proyecto ESP32 STEAMaker tenemos que poner el Actuador LED y en el pin elegir el 13 porque el led Azul está conectado en el 13. Fíjate que en el desplegable del Pin están todas las E/S del ESP32.

En cambio si elegimos un proyecto tipo ESP32 STEAMaker+ Imagina TdR STEAM veremos que tenemos añadidos unos actuadores específicos para esta placa TDR STEAM que es más fácil usarlos, donde en el desplegable sólo aparece ROJO o AZUL y el alumno no necesita recordar que ROJO es el 12 y AZUL es el 13.

Pero si elegimos un led del desplegable de actuadores, veremos que en su desplegable de pines sólo aparece los números 3, 5 y A3 porque son los que tiene libres, el resto están ocupados por la placa TdR STEAM.

Está claro que el tipo de proyecto **ESP32STAMaker+ Imagina TdR STEAM** es más cómodo porque los bloques ya tienen fijados qué pines tienen cada sensor y si eliges un sensor no incluido en la placa, ya no muestra los pines que están ocupados.

> Si eliges **ESP32STEAMaker + Imagina TdR STEAM** es muy cómoda la programación y se evitan muchos errores.
>
> Si eliges **ESP32STEAMaker** utilizas un entorno de programación como si la placa Imagina TdR STEAM no existiera y los alumnos se acostumbran a usar los elementos propios de ESP32, los pines, etc.... pero tienen que saber en cada momento qué pin utilizar.
> Aconsejamos en este caso que los alumnos tengan impresa la página Componentes de la placa TdR STEAM.

En los apuntes de este libro vamos a utilizar el proyecto indistintamente las dos formas de trabajar.

---

## 3. Prácticas con sensores digitales

### Actividad-01. LED

Página extraída de Federico Coca Notas sobre ESP32 STEAMakers CC-BY-SA

#### Enunciado

Realizar un programa que encienda y apague el LED rojo conectado al pin D12 DE LA PLACA STEAMAKER.

#### Teoría

El diodo LED (Light Emitting Diode) es un diodo semiconductor capaz de emitir luz, lo más usuales dentro del espectro visible aunque también pueden ser de infrarrojos, laser, etc. Su uso más habitual es como indicador y, últimamente cada vez más frecuentes en iluminación. Sus principales ventajas frente a luces incandescentes son:

- Menor consumo de energía
- Mayor vida útil
- Menor tamaño
- Gran durabilidad y fiabilidad

El color de la cápsula es simplemente orientativo de la longitud de onda que define realmente el color de la luz emitida. Por ello el LED con la cápsula transparente puede emitir en cualquiera de los colores del espectro visible.

El LED es un dispositivo que tiene polaridad siendo su comportamiento el siguiente: En polarización directa (ánodo a positivo y cátodo a negativo) el LED emite luz y en polarización inversa (ánodo negativo y cátodo positivo) se comporta prácticamente como un interruptor abierto.

Para su correcto funcionamiento el diodo LED se polariza poniéndole en serie una resistencia que limita la corriente que pasa a través del mismo y, por tanto, determina el nivel de brillo de la luz emitida.

Sin entrar en detalles en la tabla siguiente se dan los valores de tensión directa (VF) y corriente directa (IF) para los colores más habituales de LEDs. A partir de estos valores y el valor de tensión de alimentación de nuestro LED podemos calcular el valor de la resistencia serie sin más que aplicar la formula indicada.

```json
{
  "type": "table",
  "id": "table-03",
  "page": 93,
  "title": "Valores típicos de tensión directa y corriente directa para LEDs",
  "headers": ["Color del LED", "Tensión directa (VF)", "Corriente directa (IF)"],
  "rows": [
    ["Rojo", "1,5 V", "15 mA"],
    ["Verde", "1,8 V", "15 mA"],
    ["Amarillo", "1,8 V", "15 mA"],
    ["Azul", "3 V", "20 mA"],
    ["Blanco", "2,7 V", "20 mA"]
  ],
  "notes": "Fórmula: R = (Vcc - VF) / IF",
  "source": "Federico Coca - Notas sobre ESP32 STEAMakers CC-BY-SA"
}
```

#### En la TdR STEAM

La placa Imagina TDR STEAM dispone de un LED rojo conectado al pin D12 tal y como se indica en la serigrafía de la propia placa.

#### Programando la Actividad

Entramos en ArduinoBlocks y nos identificamos convenientemente. Vamos a crear un nuevo proyecto para la placa ESP32 STEAMakers + TdR STEAM.

Escogemos el bloque LED de TDR STEAM y lo colocamos en el bucle, quedando algo similar a la imagen siguiente:

Bloque LED de TDR STEAM

Podemos comprobar haciendo clic sobre las flechas como podemos cambiar de LED y también como podemos cambiar de estado al LED. Si solamente dejamos este bloque el LED permanecerá encendido de forma permanente y para que se acabe debemos ponerlo en estado OFF.

Pero este programa no nos permite ver el efecto de encendido y apagado del LED debido a la velocidad de procesamiento que tiene la placa UNO que típicamente trabaja a 16 MHz. Esto supone que el micro tarda en ejecutar una instrucción algo más de 0,06 microsegundos que es mucho menor que la persistencia visual humana de 0,1 segundo aproximadamente. Es decir, en realidad el LED se enciende y se apaga, pero nuestro ojo no puede apreciarlo y lo verá siempre encendido debido a la persistencia visual.

Tenemos por tanto que dejar el diodo un tiempo encendido y otro apagado (pueden ser el mismo tiempo) y para ello vamos a colocar un bloque Esperar desde el bloque de Tiempo. Si dejamos el tiempo por defecto en 100 milisegundos el diodo se encenderá y apagará cada segundo (1000 ms = 1s).

El programa final queda como vemos en la imagen siguiente y lo tenemos disponible en el enlace ESP32-SM-Actividad-01.

Coloca la placa Imagina TDR STEAM encima del ESP32.

Conectamos nuestra placa a un puerto USB del ordenador, ponemos en marcha el programa Connector y cargamos el programa. Podemos observar como el diodo LED rojo parpadea con un intervalo de un segundo.

De esta forma el programa queda grabado en la memoria de programa del microcontrolador y el ciclo se repetirá por tiempo indefinido o hasta que quitemos la alimentación a la placa. Si alimentamos la placa externamente con una fuente de alimentación se ejecutará el programa en memoria.

#### Retos de ampliación

**R1.A1.** Cambiar los tiempos para que el parpadeo sea más rápido, más lento y que los tiempos de encendido y apagado no coincidan.

**R2.A1.** Repetir el ejercicio A1 utilizando el LED azul conectado al pin D13.

---

### Actividad-02. LEDs rojo y azul

Página extraída de Federico Coca Notas sobre ESP32 STEAMakers CC-BY-SA

#### Enunciado

Como ya hemos visto anteriormente la placa dispone de dos LED (uno rojo y otro azul). Vamos a realizar un programa para que se vayan alternando en su encendido y apagado.

#### Teoría

Vamos a ver como se hacen los ciclos de repetición o bucles en ArduinoBlocks.

- **Repetir.** Lo que pongamos en hacer se va a repetir tantas veces como indiquemos en el número de veces, que por defecto estará a 10.

  En realidad lo que estamos haciendo es lo que en programación se conoce como bucle for.

- **Repetir según condición.** Vemos dos bloques que repiten su interior mientras, o hasta, que se cumpla una condición.

- **Contador.** Realiza un bucle contando con una variable índice (normalmente i o j). Se define un valor de inicio, un valor de fin y los incrementos que se realizarán en cada iteración del bucle. Dentro del bucle podremos usar esta variable índice.

#### En la TdR STEAM

Los dos LEDs de la TdR-STEAM

#### Programando la Actividad

Vamos a hacer que ambos diodos se enciendan y apaguen de forma simultánea con un programa como el siguiente, que lo tenemos disponible en Actividad-02. LED-rojo-azul.

#### Retos de ampliación

**A2.R1.** Hacer que los LEDs rojo y azul se enciendan simultáneamente con tiempos de espera de 300ms y 150ms respectivamente.

**A2.R2.** Realizar 4 intermitencias de 500ms con el LED azul y cuando estas acaben dejar el LED rojo encendido durante 1.5 segundos. Esperar un segundo para iniciar de nuevo el proceso.

**A2.R3.** Realiza 5 intermitencias de 500ms con el LED azul cada vez que el LED rojo lo hace 3 veces a intervalos de 150ms. Esperar un segundo para iniciar de nuevo el proceso.

#### Solución A22.R2

El Programa es el de la imagen siguiente:

#### Solución A2.R3

El Programa es el de la imagen siguiente:

---

### Actividad-03. Parpadeo intermitente. Multitarea

Página extraída de Federico Coca Notas sobre ESP32 STEAMakers CC-BY-SA

#### Enunciado

Ya hemos visto como hacer funcionar a los LEDs de diferentes formas, pero ahora vamos a introducir un concepto que nos puede resultar bastante útil en el futuro, se trata de la multitarea en ArduinoBlocks.

#### Teoría

Este apartado se extrae de ArduinoBlocks - FreeBook disponible en Free Book (online & updated).

ArduinoBlocks nos permite utilizar una capa para implementar un sistema multitarea avanzado basado en FreeRTOS (del inglés Real Time Operating System), que es un sistema operativo de tiempo real kernel para dispositivos embebidos para plataformas de microcontrolador que se distribuye bajo licencia MIT. Este sistema permite crear tareas que se ejecutarán de forma paralela (virtualmente). En microcontroladores modestos como el Arduino UNO, Nano o incluso MEGA la multitarea con FreeRTOS es bastante limitada y consume gran parte de los recursos de nuestro Arduino, en caso de necesitar de un sistema multitarea más potente podemos optar por usarlo en placas basadas en ESP8266 o ESP32 con mucha más potencia y recursos (especialmente el ESP32 con doble núcleo y gran potencia de procesamiento y memoria interna)

Los sistemas software de multitarea utilizan un planificador o scheduler que se encarga de repartir el tiempo de procesamiento entre las distintas tareas, de forma que a cada una le toca un tiempo de microcontrolador para ejecutar un poquito de su parte de programa.

#### Conceptos básicos de multitarea

Un procesador convencional como el de Arduino UNO solo puede ejecutar una tarea a la vez, pero al cambiar rápidamente entre tareas, un sistema operativo multitarea puede hacer que parezca que cada tarea se ejecuta simultáneamente.

#### Programación

El programador es quien debe decidir qué tarea debe ejecutarse en un momento determinado. El kernel o núcleo puede suspender y luego reanudar una tarea muchas veces durante el tiempo de vida de la tarea.

Además de ser suspendida involuntariamente por el núcleo o kernel, una tarea puede optar por suspenderse a sí misma. Hará esto si desea retrasar (dormir) por un período fijo o esperar (bloquear) a que un recurso (por ejemplo, un puerto serie) esté disponible, o que ocurra un evento (por ejemplo, presionar una pulsador). Una tarea bloqueada o inactiva no se puede ejecutar y no se le asignará ningún tiempo de procesamiento.

#### Planificadores

Los planificadores de multitarea permiten asignar a cada tarea una prioridad, para así darle preferencia a las tareas más críticas o que necesitan más tiempo de procesamiento. Si creamos muchas tareas con "alta" prioridad puede que afectemos a las demás dejando poco tiempo de procesamiento para ellas.

Cada tarea tiene su propio espacio de memoria, por lo que crear demasiadas tareas también puede dejarnos el procesador sin memoria. Si la memoria asignada a las tareas tampoco es suficiente para almacenar los datos se podría reiniciar de forma inesperada el Arduino, o funcionar incorrectamente, es decir que como siempre, hay que ser consciente de los limitados recursos de los que disponemos.

#### Semáforos

Con la introducción teórica a la multitarea vista, debemos hacernos otra pregunta: ¿Qué pasa si una tarea accede a un recurso o variable, y el sistema multitarea le da el control a otra tarea y por tanto ese proceso falla o quizás otra tarea acceda al mismo recurso y se solapen?

Para ese problema de convivencia entre tareas se inventaron los "semáforos", en concreto el que más nos interesa es el semáforo "mutex" o de exclusión mutua, que permite que bloqueemos el sistema multitarea, hagamos lo que tengamos que hacer crítico, y luego liberemos el control. Por supuesto estas tareas críticas deben ser lo más cortas y atómicas posibles: una escritura crítica en una variable, un envío de un dato, una actualización de una pantalla LCD,… siempre cosas simples. Los semáforos debemos usarlos en casos que tengamos claro que se pueden crear conflictos, pues su abuso puede hacer que el sistema multitarea empiece a fallar.

#### En la ESP32 STEAMakers

Una ventaja que posee la ESP32 Plus STEAMakers es que, al estar basado en un ESP32 con dos microcontroladores internos, podemos hacer que cada microcontrolador trabaje en una tarea y esto si sería multitarea real, o en varias tareas mezclando la multitarea real con la simulada. Esto también se puede hacer en las placas Arduino UNO, pero con el ESP32 tenemos más potencia para realizar estas tareas.

#### Bloques esperar

¿Qué pasa con los bloques tipo "esperar" que estaban tan prohibidos en la programación de Arduino cuando queríamos simular una multitarea antes de tener estos bloques? Pues seguimos teniéndoles bastante tirria. Aunque en teoría podríamos usarlos, un bloque esperar hace pensar al microcontrolador que está haciendo algo útil, cuando en realidad no es así, por lo que el sistema multitarea querrá asignarle tiempo de procesamiento a la tarea, aunque sea para eso, ¡para no hacer nada!

Tenemos una solución, tenemos un nuevo bloque de esperar "task friendly" que en lugar de esperar sin hacer nada le dice al sistema: ¡voy a estar un rato sin hacer nada, permite ejecutar otras tareas mientras y luego vuelves! ....Mucho más "friendly", claro que sí.

#### Bloques

Con toda esta información pasamos a ver los bloques disponibles para poner todo ésto en marcha.

```json
{
  "type": "table",
  "id": "table-04",
  "page": 108,
  "title": "Bloques de multitarea en ArduinoBlocks",
  "headers": ["Bloque", "Descripción"],
  "rows": [
    ["Bloque ejecutar tarea", "Permite crear una nueva tarea con su bloque de 'inicializar' y su 'bucle' al igual que la tarea original de Arduino. Debemos asignar una prioridad a cada tarea, por defecto dejaría todas a 'baja' y luego iría ajustando si hace falta. Para gestionar mejor las prioridades, es recomendable en algunos casos no utilizar el 'inicializar' y 'bucle' propio de Arduino que suele tener preferencia sobre todas estas tareas y es más difícil de equilibrar las prioridades."],
    ["Bloque esperar en esta tarea", "El bloque esperar óptimo para tareas, pues deja funcionar al resto de tareas de forma más óptima mientras se espera en ésta. Este bloque tiene menos precisión que el bloque 'esperar' original, si necesitamos hacer esperas muy precisas (o de menos de 20 ms) debemos usar el 'esperar' tradicional. Pero nos servirá en la mayoría de casos."],
    ["Bloque bloqueo exclusivo", "Si tenemos que hacer alguna acción crítica que no queremos que sea interrumpida internamente por el planificador del sistema multitarea podemos poner este bloque y dentro los bloques críticos. (no utilizar si no es estrictamente necesario)"],
    ["Bloque establecer memoria", "Cada tarea tiene su propio espacio de memoria reservado, esta es la cantidad por defecto para las tareas (192 bytes), si necesitamos ajustarla podemos utilizar este bloque en el 'inicializar' principal y se ajustará para todas las tareas. Un mal ajuste puede provocar reinicios del microcontrolador o mal funcionamiento."],
    ["Bloque y destruir tarea", "Las tareas en principio, igual que el bucle de Arduino, están pensadas para ejecutarse de forma indefinida, si en un caso una tarea deja de ser necesaria la forma de terminarla es con este bloque que parará la ejecución y liberará la memoria de la tarea en la que se ejecuta."]
  ],
  "notes": "Imágenes Federico Coca - Notas sobre ESP32 STEAMakers CC-BY-SA",
  "source": "CATEDU - ESP32 en el Aula"
}
```

---

### Actividad-04. LED RGB

Página extraída de Federico Coca Notas sobre ESP32 STEAMakers CC-BY-SA

#### Enunciado

La actividad básica consistirá en ver los colores primarios y su mezcla mediante el uso del LED RGB y también habrá una actividad secundaria sobre el control de intensidad mediante PWM.

#### Teoría

**LED RGB**

Un LED RGB es en realidad un encapsulado que incorpora tres diodos LED, uno por cada color fundamental. Los colores primarios en óptica son el rojo, el verde y el azul y la correcta combinación, en términos de intensidad, de ellos originará cualquiera de los colores secundarios. Las siglas RGB son el acrónimo de Red, Green y Blue. En el caso de la TDR-STEAM se utiliza un LED RGB con los tres LEDs unidos por su cátodo o terminal negativo, es decir es un LED RGB de cátodo común.

Teóricamente en Arduino, cada uno de esos LEDs podría adoptar 256 (valores entre 0 y 255) colores diferentes, es decir, un total de 16.777.216 posibles colores diferentes con un LED RGB.

**PWM**

PWM son siglas en inglés que significan Pulse Width Modulation y que lo podemos traducir a español como Modulación de ancho de pulso. Los pines PWM permiten generar una señal analógica mediante una salida digital mapeada con 8 bits, o lo que es lo mismo, valores del 0 al 255, es decir mediante una salida PWM podemos emular una señal analógica.

En realidad una placa tipo UNO no es capaz de generar una salida analógica y lo que se hace es emplear un truco que consiste en activar una salida digital durante un tiempo y el resto del tiempo del ciclo mantenerla desactivada. El valor promedio de la salida es el valor analógico. En el tipo de modulación PWM mantendremos constante la frecuencia, o lo que es lo mismo, el tiempo entre pulsos y lo que se hace es variar la anchura del pulso.

La proporción de tiempo que está encendida la señal, respecto al total del ciclo, se denomina ciclo de trabajo o Duty cycle, y generalmente se expresa en tanto por ciento.

#### En la TdR STEAM

El bloque superior permite asignar el color a partir de la paleta que se despliega al hacer clic sobre el cuadrado de color y en el inferior debemos introducir el valor numérico (entre 0 y 255) correspondiente a cada color primario en cada uno de los tres colores RGB. Con estos bloques no tenemos que preocuparnos por saber las conexiones de cada diodo ya que están asignadas internamente en el bloque.

También hemos visto que el LED RGB tiene asociados tres pines y por tanto podemos tratar a cada LED de forma individual. Pero para poder hacerlo debemos crear un tipo de proyecto "ESP32 STEAMakers" y no como hasta ahora "ESP32 STEAMakers + Imagina TdR STEAM". Esto nos va a permitir disponer del bloque LED que está dentro de "Actuadores" con todos los pines digitales configurables.

De esta forma un programa como el de la imagen siguiente nos va a permitir activar de forma individual cada diodo LED. La solución a esta actividad la tenemos disponible en Actividad-04.

#### Retos de ampliación

**A4.R1.** A partir de la idea del reto realizar un programa que muestre sucesivamente los siguientes colores: magenta o violeta, cian o azul claro, amarillo y blanco. Ayúdate del gráfico que muestra el modelo aditivo de colores que hemos puesto al principio de la teoría.

**A4.R2.** Realizar un programa que nos muestre los tres colores primarios a partir de un proyecto tipo "ESP32 STEAMakers + Imagina TdR STEAM" y el bloque con la paleta de colores.

**A4.R3.** Realizar un programa que nos muestre los tres colores primarios a partir de un proyecto tipo "ESP32 STEAMakers + Imagina TdR STEAM" y el bloque con el valor numérico de cada color.

**A4.R4.** Realizar un programa que muestre de manera secuencial los colores del arcoíris en el orden que vemos en la imagen siguiente.

#### Solución A4.R2

El Programa es el de la imagen siguiente:

#### Solución A4.R3

El Programa es el de la imagen siguiente:

---

### Actividad-05. Zumbador

Página extraída de Federico Coca Notas sobre ESP32 STEAMakers CC-BY-SA

#### Enunciado

Trabajaremos con el buzzer o zumbador partiendo de la reproducción de sonidos básicos hasta llegar a la reproducción de melodías completas.

#### Teoría

El buzzer, zumbador o altavoz es un transductor electroacústico (convierte una señal eléctrica en una onda de sonido) que produce un determinado zumbido o sonido. Existen de dos tipos:

- Pasivos: no disponen de electrónica interna, por lo que tenemos que proporcionar una señal eléctrica para conseguir el sonido deseado.
- Activos: disponen de un oscilador interno, por lo que únicamente tenemos que alimentar el dispositivo para que se produzca el sonido.

El zumbador que incorpora la placa TdR STEAM es de tipo pasivo y está conectado al pin D8.

Una de los parámetros que caracterizan a un sonido es su frecuencia de emisión, siendo la frecuencia el número de veces que se repite por unidad de tiempo (segundo). La transmisión del sonido se realiza por ondas a través en cualquier medio (sólido, líquido o gaseoso) excepto en el vacío. La frecuencia de un sonido nos indica cuantos ciclos por segundo tiene una onda.

#### Zumbador activo

Cuando está nuevo se distingue del zumbador pasivo o altavoz por la pegatina de protección que lo acompaña, pero esta hay que quitarla para oir el zumbido y sin ella es difícil distinguir un tipo del otro, así que en este caso deberemos crear un programa con alguna melodía y si no se reproduce correctamente es que tenemos conectado el zumbador activo en lugar del pasivo. Lo mejor es marcar alguno de los dos cuando podemos distinguirlos. Una buena idea puede ser utilizar la propia pegatina en el lateral del mismo.

#### Programando la actividad

Los cuatro bloques destinados a trabajar con el zumbador los vemos en la imagen siguiente:

#### Retos de ampliación

**A5.R1.** Reproducir la escala musical con las notas básicas utilizando los bloques Zumbador y Tono

**A5.R2.** Reproducir la melodía de la imagen siguiente sabiendo que las negras tienen una duración de 500ms, las negras con un puntito 750ms y las blancas 1000ms.

**A5.R3.** Reproducir diferentes melodías a partir de los bloques RTTTL (Ring Tone Text Transfer Language o lenguaje de tonos de llamada).

**A5.R4.** Reproducir alguna otra melodía que descarguemos de las páginas web propuestas.

---

### Actividad-06. Pulsadores

Página extraída de Federico Coca Notas sobre ESP32 STEAMakers CC-BY-SA

#### Enunciado

Utilizaremos uno, o ambos pulsadores, para llevar a cabo determinadas tareas como respuesta al accionamiento de los mismos.

#### Teoría

**El pulsador**

Se trata de un dispositivo que es capaz de abrir o cerrar el paso de la corriente eléctrica mientras permanece accionado, es decir, su función no queda anclada como por ejemplo en los interruptores de la luz de casa, en donde el accionamiento permanece hasta que no se vuelve a accionar. En un pulsador, por contra, su activación dura mientras lo mantenemos pulsado y vuelve a su estado de reposo en cuanto dejemos de pulsarlo.

Esto lo hemos dado en Sensores, son dos configuraciones: la primera PULL DOWN o lógica normal y la segunda PULL UP o lógica inversa. Los pulsadores Tdr Steam son PULL DOWN o lógica normal.

En el caso de la TdR STEAM los pulsadores se han configurado para que en reposo pongan a cero su entrada digital correspondiente y que se ponga a uno cuando son accionados.

**Concepto de variable y de contador**

El concepto de variable en programación consiste simplemente en asignarle un nombre significativo a un espacio de memoria donde almacenar determinada información durante la ejecución normal del programa. El concepto es muy amplio y complejo y en nuestro caso no vamos a entrar en detalles sobre el mismo, pero si indicar que no se debe confundir con el concepto de variable matemática, ya que una expresión como x = x + 1 que es una aberración en matemáticas tiene todo el sentido en programación. Lógicamente en matemáticas no se puede cumplir pero en programación significa que a la variable x se le sume uno y el resultado se vuelva a guardar en la misma variable.

En ArduinoBlocks podemos crear tres tipos de variables, numéricas, de texto o booleanas.

En programación, llamamos contador a una variable cuyo valor se incrementa o decrementa en un valor fijo para cada iteración del bucle para el que se ha definido. El uso habitual de un contador es simplemente contar el número de veces que itera un bucle en general o de forma más extensa contar, solamente, aquellas iteraciones en las que se cumpla una determinada condición.

Por ejemplo, supongamos que tenemos una variable de nombre Estado de valor inicial cero y que se incremente cada vez que accionamos un pulsador, de esta forma si en un bucle vamos incrementando la variable de uno en uno, tenemos:

- Estado = 0 // valor inicial
- Estado = 1 // Estado = Estado + 1
- Estado = 2 // Estado = Estado + 1
- ...

**Condicionales**

Las sentencias condicionales son aquellas que nos permiten tomar decisiones en función de si ocurre o no ocurre determinada cosa. En el caso de ArduinoBlocks estas las podemos encontrar en el bloque lógica. Este bloque contiene los elementos que vemos en la imagen siguiente:

El funcionamiento es el siguiente: se evalúa la condición que ponemos en "si" y si el resultado es verdadero, o sea condición cierta, se realizan las acciones que pongamos en "hacer" y si no es cierta dichas acciones no se realizan. En el apartado condición se pueden poner infinidad de factores como pueden ser el estado de sensores, realizar comparaciones, hacer operaciones matemáticas, etc. Lógicamente el resultado de evaluar la condición debe ser verdadero o falso lo que se resuelve en el caso de la programación en Arduino diciendo que si el resultado es 0, el resultado de la evaluación es falso y si es 1 o cualquier otro valor es verdadero.

Si hemos sido observadores hemos visto en los bloques "si" de "Lógica" un signo mas (+) en la parte superior izquierda tanto del condicional "if" como del "if ... else" tal y como se destaca en la imagen siguiente.

Cada vez que pulsemos sobre el signo mas se añadirá una cláusula "else if" a la principal y podemos añadir tantas como necesitemos. Esta cláusula nos va a permitir establecer una nueva condición. En la imagen siguiente vemos añadidas dos para el caso de "if ... else". En la imagen observamos el código equivalente y las distintas condiciones que se pueden establecer.

El signo menos (-) que aparece en la imagen sirve para eliminar la correspondiente cláusula "else if".

#### En la TdR STEAM

La placa TdR STEAM dispone de dos pulsadores denominados SW1 y SW2 y conectados a los pines digitales D2 y D7 respectivamente.

#### Programando la actividad

La aplicación de un pulsador para hacer algo requiere saber si este esta pulsado o no lo está y para ello vamos a necesitar de las sentencias condicionales que hemos visto anteriormente.

Vamos a hacer un programa en el que preguntemos si el pulsador SW1 (D2) está o no pulsado y si lo está que se encienda el LED rojo (D12) y si no lo pulsamos que permanezca apagado. La solución al reto la tenemos disponible en Actividad-06. A modo de comentario se ha colocado otra forma de realizar la misma programación que podemos probar simplemente arrastrando el bloque que hay en bucle fuera del mismo y colocando el otro en su lugar.

#### Ampliación sobre programación de la actividad

Ya se ha explicado el funcionamiento del signo mas (+) de la parte superior izquierda tanto del condicional "if" como del "if ... else". Cada vez que pulsemos sobre el signo mas se añadirá una cláusula "else if" a la principal y podemos añadir tantas como necesitemos. Esta cláusula nos va a permitir establecer una nueva condición. El signo menos (-) que aparece en la imagen sirve para eliminar la correspondiente cláusula "else if".

Vamos a hacer un programa similar a la Actividad-06 para hacer que si pulsamos SW2 se encienda el LED azul y si no está pulsado permanecerá apagado. La solución la tenemos disponible en Actividad-06-ampliación-1.

El siguiente programa hará que se encienda el LED azul al pulsar SW1 y el LED rojo al pulsar SW2 se encienda el rojo permaneciendo apagados si no están pulsados. Obsérvese la primera condición AND (Y) que impide que si pulsamos ambos pulsadores al mismo tiempo se enciendan los LEDs. La solución la tenemos disponible en Actividad-06-ampliación-2.

#### Retos de ampliación

**A6.R1.** Hacer un programa que encienda el LED rojo cuando NO se pulse SW1.

**A6.R2.** Hacer un programa que encienda el LED azul cuando se pulse SW1 y NO se pulse SW2. Y además se apague cuando se pulse SW2 y NO se pulse SW1.

**A6.R3.** Hacer un programa que emita, usando SW1 como si fuese un telégrafo, el código Morse universal de solicitud de socorro, SOS.

**A6.R4.** Hacer un programa que al pulsar SW1 encienda el LED azul y que este permanezca encendido hasta que no pulsemos SW1 dos veces mas (3 pulsaciones en total), en cuyo caso se apagará.

#### Solución A6.R1

La solución está en utilizar el operador NOT. El Programa es el de la imagen siguiente:

#### Solución A6.R2

La solución en esta ocasión está en utilizar el operador NOT y el operador AND. El Programa es el de la imagen siguiente:

#### Solución A6.R3

El alfabeto Morse lo vemos en la imagen siguiente, donde podemos observar que la S son tres puntos o pulsaciones cortas y la O son tres rayas o pulsaciones largas. Sin entrar en más detalles daremos la solución considerando SOS como una palabra (es lo universalmente adoptado) de forma que no haremos pausas entre letras.

#### Solución A6.R3

El Programa es el de la imagen siguiente:

---

## 4. Prácticas con sensores analógicos

### Actividad-07. El potenciómetro y Plotter

Página extraída de Federico Coca Notas sobre ESP32 STEAMakers CC-BY-SA

#### Enunciado

Introducir el uso de las entradas analógicas para visualizar los cambios que hagamos con el potenciómetro en el terminal serie o consola serie. Cuando hablamos de lecturas analógicas suele ser muy útil el uso del mapeo, concepto que también vamos a introducir y que veremos en la segunda parte del reto.

#### Teoría

Antes de nada ya hemos indicado que el potenciómetro va conectado a un pin analógico y es en este momento cuando vamos a establecer la diferencia entre los conceptos de analógico y de digital.

Una clasificación de los circuitos electrónicos es dividirlos en dos grandes categorías: digitales y analógicos.

- La electrónica digital utiliza magnitudes con dos valores discretos conocidos como 0 - 1, alto - bajo, on - off, etc, y que se corresponden con la presencia o no de tensión en un determinado punto.
- La electrónica analógica emplea magnitudes con valores continuos. En concreto en las placas En la ESP32 Plus STEAMakers, las entradas analógicas pueden tener 2^12 valores (12 bits de resolución = 4.096 valores), es decir, valores comprendidos entre 0 y 4.095. Estos valores se pueden expresar de forma numérica o de forma porcentual, correspondiendo el 0 a un 0% y el 4.095 al 100%.

**El potenciómetro**

En la imagen siguiente vemos el aspecto de un modelo concreto de potenciómetro así como los símbolos habituales del mismo. La numeración indica lo siguiente:

- Terminales 1 y 3 son los contactos unidos a los extremos de la resistencia fija o resistencia total del potenciómetro.
- Terminal 2 es el contacto que va unido al cursor o parte móvil que se desliza sobre la resistencia fija haciendo que la resistencia entre un terminal y el cursor varíe en función de la posición de este.

La posición del cursor se determina de forma mecánica y son adecuados para usarlos como elementos de control de tensión (conexión en serie) o de corriente (conexión en paralelo). Los potenciómetros del tipo que estamos viendo (existen de otros muchos tipos) tienen un funcionamiento en forma de rotación con un ángulo de unos 270 grados entre los puntos más extremos.

**El terminal o consola serie**

Sirve para visualizar en un ordenador los datos recibidos a través del puerto serie y en realidad es una aplicación que controla las comunicaciones bidireccionales a través de la UART integrada en el microcontrolador.

Es muy importante tener siempre presente que el puerto serie es el que se utiliza para "subir" el firmware o programa a la placa, tarea que se realiza a través de una aplicación pregrabada en el microcontrolador y que se denomina "bootloader".

En ArduinoBlocks es posible usar la consola serie solamente si tenemos instalada y en funcionamiento la aplicación ArduinoBlocks-Connector que es la encargada de establecer las comunicaciones locales de nuestra placa con las remotas de la aplicación.

A la hora de establecer una conexión serie los dos extremos que intervienen en la conexión (placa ESP32 STEAMakers y ordenador) deben establecer el mismo valor en la velocidad de la conexión. Por defecto esta velocidad es de 115200 baudios o bits por segundo en el bloque inicializar y otras velocidades comúnmente utilizadas son: 4800, 9600, 19200, 38400, 57600. Es por lo tanto imprescindible incluir en el bloque "Inicializar" el bloque "Iniciar" y establecer la velocidad de comunicación.

**Serial Plotter - Datalogger**

Es otra funcionalidad relacionada con la comunicación serie que nos permite visualizar información en forma de gráfica en tiempo real. Además el "Serial Plotter" implementa un sencillo datalogger con el que podremos ir grabando los datos para exportarlos posteriormente. En ArduinoBlocks existen bloques que nos permiten trabajar con el serial plotter. El serial plotter + datalogger se activa haciendo clic en la flecha a la derecha de Consola.

**Mapeo**

Hemos indicado que las entradas analógicas trabajan con 12 bits, o sea valores comprendidos entre 0 y 4095 (2^12) y también que las salidas digitales trabajan con 8 bits, o sea valores entre 0 y 255 (2^8), por lo que si queremos combinar en nuestro programa entradas analógicas con salidas digitales debemos realizar un ajuste de escala en los datos. A este ajuste se le conoce como "mapear" y es un bloque disponible en el menú Matemáticas.

#### En la TdR STEAM

#### Programando la actividad

**Parte 1.** Vamos a guardar los datos leídos del potenciómetro en una variable y mostrarlos a través de la consola serie. La solución la tenemos disponible en Actividad-07: Parte 1 que es el programa que vemos en la imagen siguiente:

Si cargamos el programa en nuestra placa y posteriormente activamos la consola y conectamos ArduinoBlocks con nuestro ordenador podemos ver un resultado similar al de la imagen siguiente que se corresponde con variaciones de extremo a extremo del potenciómetro.

Para entender el significado del check "salto de linea" del bloque "Enviar" podemos desactivarlo y volver a hacer el mismo proceso.

> **¡MUY IMPORTANTE!** cuando terminemos de manipular el potenciómetro que el mismo esté totalmente girado a la posición izquierda (hacia el reset), ya que comparte la conexión A0 (GPIO02) con el sistema de grabación del programa. Si no está en esa posición se producirá un error en el envío del siguiente programa.

**Parte 2.** Vamos a modificar el programa de la parte 1 del reto para mapear los datos antes de enviarlos a la consola serie. La solución la tenemos disponible en Actividad-07: Parte 2 que es el programa que vemos en la imagen siguiente:

El resultado ahora lo vemos en la imagen siguiente:

#### ENVIO DE DATOS SERIE PERO EN VEZ DE CONSOLA POR PLOTTER

(Autor Javier Quintana)

Ahora vamos a cambiar el "Enviar" serie por "Plotter".

Y además vamos a mapear el valor del potenciómetro de 0-4095 a 0-255 y lo almacenaremos en una variable "brillo" que nos servirá para que el RGB se ilumine más o menos:

Es importante poner un retardo (en este caso 1000 mseg) si no lo ponemos, saturamos el puerto serie.

Abrimos el plotter y jugamos.

> **¡MUY IMPORTANTE!** cuando terminemos de manipular el potenciómetro que el mismo esté totalmente girado a la posición izquierda (hacia el reset), ya que comparte la conexión A0 (GPI002) con el sistema de grabación del programa. Si no está en esa posición se producirá un error en el envío del siguiente programa.

#### Retos de ampliación

- **A7.R1.** Utilización del bloque "crear texto con ..." del menú "Texto". Utilizaremos cualquiera de los programas vistos en la actividad y configuraremos el nuevo bloque para que en cada línea nos muestre el mensaje "El valor del potenciometro es: ", a continuación nos muestre el valor y tras el mismo el símbolo % porque configuraremos la lectura en porcentaje. Dejaremos transcurrir un tiempo de 3s entre cada muestra de salida por consola.
- **A7.R2.** Control del LED RGB con el potenciómetro. Vamos a dividir el rango total en 8 partes y asignarle a cada una de ellas uno de los colores RGB según vemos en la tabla siguiente:

```json
{
  "type": "table",
  "id": "table-05",
  "page": 150,
  "title": "Asignación de colores RGB según rango del potenciómetro",
  "headers": ["Color", "Rango", "R", "G", "B"],
  "rows": [
    ["Rojo", "0 a 512", "255", "0", "0"],
    ["Verde", "513 a 1023", "0", "255", "0"],
    ["Azul", "1024 a 1536", "0", "0", "255"],
    ["Amarillo", "1537 a 2048", "255", "255", "0"],
    ["Cian", "2049 a 2560", "0", "255", "255"],
    ["Magenta", "2561 a 3072", "255", "0", "255"],
    ["Blanco", "3073 a 3584", "255", "255", "255"],
    ["Naranja", "3584 a 4096", "255", "127", "0"]
  ],
  "source": "CATEDU - ESP32 en el Aula"
}
```

- **A7.R3.** Repetir el reto 2 de esta actividad pero ahora además mostrando por consola el valor del potenciómetro.

---

### Actividad-08. La fotorresistencia o LDR

**Interruptor Crepuscular**

Para ver cómo funciona, qué mejor ejemplo que hacer un interruptor crepuscular, es decir "Que se encienda la luz cuando se haga de noche".

Para ello ponemos el nivel de luz en % y definimos qué es día y qué es noche con un valor umbral, en este ejemplo hemos puesto 50%.

Página extraída de Federico Coca Notas sobre ESP32 STEAMakers CC-BY-SA

#### Enunciado

Utilizaremos la consola serie para mostrar los valores de luz detectados por la resistencia LDR o fotocélula.

#### Teoría

Una fotorresistencia o fotorresistor es un componente electrónico cuya resistencia disminuye de forma exponencial con el aumento de la intensidad de luz incidente. Las siglas LDR vienen de su nombre en inglés, que es Light Dependent Resistor.

#### En la TdR STEAM

#### Programando la actividad

Dado que en el menú TDR STEAM de ArduinoBlocks tenemos disponible un bloque que nos devuelve el nivel de luz en porcentaje o de forma numérica, resolver la actividad es sumamente sencillo. La solución la tenemos disponible en ESP32-SM-Actividad-08 que es el programa que vemos en la imagen siguiente:

Esto nos generará algo como lo de la imagen siguiente en la consola:

#### Opción Plotter gráfico

Es más visual y dinámico.

- Descarga desde libros.catedu.es Manual Actividades ESP32 SteaMakers 2022 Junio.pdf
- Descarga desde el drive del autor tutorial Manual de Actividades ESP32 SteamMaker 2022 Junio

#### Retos de ampliación

**A8.R1.** Detectar el nivel de iluminación de la sala y condiciones de iluminación en las que estemos utilizando la LDR y enviar el resultado a la consola.

**A8.R2.** Programar un interruptor crepuscular utilizando la LDR y uno de los LEDs para simular el farol. El nivel de luz mínimo permitido antes de encender el farol dependerá del resultado obtenido en el reto 1, de forma que con un valor menor o igual se encienda el LED y con un valor mayor permanezca apagado.

**A8.R3.** Hacer el interruptor crepuscular utilizando como farol en LED RGB que se encenderá en color blanco.

---

### Actividad-09. El sensor de temperatura LM35D

Página extraída de Federico Coca Notas sobre ESP32 STEAMakers CC-BY-SA

#### Enunciado

Utilizaremos este sensor de temperatura para medir la temperatura de la habitación en la que estemos resolviendo el reto mostrando el resultado en la consola.

#### Teoría

**LM35**

El LM35 es un circuito integrado de medida de temperatura de precisión con una tensión de salida lineal y proporcional a la temperatura en grados centígrados. Algunas de las características que se pueden extraer de la hoja de datos del LM35 son:

- Directamente calibrado en grados Celsius (Centígrados)
- Factor de escala lineal de +10-mV/°C
- Resolución asegurada de 0.5°C
- Rango de medida de –55°C a 150°C

**Bloques de tiempo**

Para esta actividad vamos a explicar los bloques de tiempo que se implementan en ArduinoBlocks. Las funciones de tiempo o retardo nos permiten realizar pausas y obtener información sobre el tiempo transcurrido dentro del microcontrolador.

1.- Bloques esperar. Realizan una pausa del tiempo que establezcamos hasta seguir con la ejecución del siguiente bloque. Se corresponden con las instrucciones delay(1000) y delayMicroseconds(1000). Tenemos disponibles los dos de la imagen siguiente:

2.- Tiempo transcurrido. Obtiene un valor con el tiempo transcurrido desde el inicio o reset del microcontrolador de la placa ESP32 STEAMakers. Se trata de las funciones millis() y micros(). El valor puede ser en milisegundos o microsegundos, tal y como vemos en la imagen siguiente:

---

### Actividad-10. El sensor de temperatura y humedad DHT-11

**Visualización humedad y temperatura por el display LCD**

El clásico es visualizar por el LCD la temperatura y la humedad instantánea.

- Más adelante veremos el LCD y por qué hay que inicializarlo con la dirección 0x27
- Fíjate que hay que formatear el valor que devuelve la función DHT-11 como decimal, la explicación lo vimos aquí en sensores DHT11

> **Haz un pequeño experimento:**
> Sustituye la instrucción de temperatura DHT11 por el LM35 ¿Sale el mismo valor? ¿Cuál crees que es el verdadero?

> **Convierte el ESP32 EN ESTACIÓN METEOROLÓGICA**
> En la página 158 del Manual actividades ESP32 tienes un ejemplo de grabar la temperatura y la humedad en un fichero texto en una tarjeta microsim (la placa ESP32 incorpora un lector)

- Descarga desde libros.catedu.es Manual Actividades ESP32 SteaMakers 2022 Junio.pdf
- Descarga desde el drive del autor tutorial Manual de Actividades ESP32 SteamMaker 2022 Junio

Página extraída de Federico Coca Notas sobre ESP32 STEAMakers CC-BY-SA

#### Enunciado

Realizar un programa básico de medida de temperatura y humedad relativa de la habitación en la que estamos trabajando con nuestra TdR STEAM.

#### Teoría

**DHTxx**

El DHT11 es un modelo de sensor que permiten realizar la medición simultánea de temperatura y humedad. Dispone de un procesador interno que es el encargado de realizar la medición entregando la información mediante una señal digital.

Se presenta en un encapsulado plástico típico de color azul. Sus principales características son:

- Rango de temperatura: 0 a 50ºC
- Precisión de la medida de temperatura: ±2ºC
- Rango de humedad: 20 a 80%
- Precisión en la medida de humedad: ±5%.
- Frecuencia de muestreo: 1 muestra por segundo (1 Hz)

El DHT11 es un sensor bastante limitado que podemos usar con fines de formación, pruebas, o en proyectos que realmente no requieran una medición precisa.

Si necesitamos mayor precisión y rango podemos recurrir al DHT22 que es de la misma familia y lo único que cambia es sus características y el precio. Sus características son:

- Rango de temperatura: -40 a 125ºC
- Precisión de la medida de temperatura: ±0.5ºC
- Rango de humedad: 0 a 100%
- Precisión en la medida de humedad: ±2 a 5%
- Frecuencia de muestreo: 2 muestras por segundo (2 Hz)

**Estado de confort**

En la web ARQUITECTURA & ENERGÍA podemos encontrar un artículo donde se nos explica con bastante profundad el tema del confort térmico.

Puede definirse confort térmico, o más propiamente comodidad higrotérmica, como la ausencia de malestar térmico. En fisiología, se dice que hay confort higrotérmico cuando no tienen que intervenir los mecanismos termorreguladores del cuerpo para una actividad sedentaria y con una indumentaria ligera. Esta situación puede registrarse mediante índices que no deben ser sobrepasados para que no se pongan en funcionamiento los sistemas termorreguladores (metabolismo, sudoración y otros).

Sobre el gráfico vamos a delimitar zonas de temperatura y humedad para establecer su color. Por motivos de simplicidad lo vamos a hacer delimitando zonas rectangulares, pero comprobamos que no cometemos grandes errores y para nuestro propósito nos sirve.

1.- Zona Roja: en la imagen siguiente tenemos delimitadas las zonas:

- Humedad Relativa: superior al 85% e inferior al 20%
- Temperatura: superior a 27oC e inferior a 16oC

2.- Zona Amarilla: en la imagen siguiente tenemos delimitadas las zonas:

- Humedad Relativa: entre el 20% y el 40% y entre el 65% y el 85%
- Temperatura: entre 16ºC y 18ºC y entre 24ºC y 27ºC

3.- Zona Verde, rojo y amarillo: en la imagen siguiente tenemos delimitadas todas las zonas, correspondiendo a la verde los siguientes datos:

- Humedad Relativa: entre el 40% y el 65%
- Temperatura: entre 18ºC y 24ºC

Con este enlace al archivo colores-A10.svg puedes descargarte el archivo vectorial, editarlo con Inkscape y ver como se han realizado estos gráficos.

#### En la TdR STEAM

#### Programando la actividad

De nuevo realizaremos la programación como en las actividades anteriores, utilizando el monitor serie para mostrar los datos. El programa ESP32-SM-Actividad-10 lo vemos en la imagen siguiente:

#### Retos de ampliación

**A10.R1.** Realizar un programa que nos muestre el estado de confort según las explicaciones vista y la idea de un semáforo que utilice el LED RGB para componer esos colores rojo, verde y amarillo.

Para resolver la actividad vamos a necesitar varios bloques del menú "Lógica" y especialmente combinando funciones AND y OR múltiples. Si necesitamos, por ejemplo, aumentar el número de operadores AND dentro de un bloque simplemente tenemos que combinarlo como vemos en la imagen siguiente, donde se han combinado cuatro bloques AND.

El Programa es el de la imagen siguiente y está disponible en ESP32-SM-Reto-1-A10.

**A10.R2.** Idear un método para probar de forma completa la funcionalidad del programa anterior, aunque se requiera modificarlo. También se pide explicar la misión de la función "limite-confort" creada en el reto 1 de la actividad 10.

---

### Actividad-11. Emisor y receptor de infrarrojos

Página extraída de Federico Coca Notas sobre ESP32 STEAMakers CC-BY-SA

#### Enunciado

Enviaremos códigos desde el control remoto por infrarrojos que serán recibidos por el LED de infrarrojos para actuar según el código recibido.

#### Teoría

**¿Qué son los infrarrojos?**

Son una clase de radiación electromagnética con una longitud de onda que resulta superior a la longitud de onda de la luz visible, siendo su frecuencia superior a las microondas. Dentro del espectro electromagnético, la radiación infrarroja se encuentra comprendida entre el espectro de luz visible y las microondas. Tiene longitudes de onda mayores o más largas que el rojo.

Como podemos observar en la imagen, los rayos infrarrojos son clasificados, de acuerdo a su longitud de onda, del siguiente modo:

- infrarrojo cercano, con longitud de onda entre 0.7 μm y 1.1 μm, es la parte del espectro infrarrojo que ese encuentra más próximo a la luz visible.
- infrarrojo medio, con longitud de onda entre 1,1 μm y 15 μm.
- infrarrojo lejano o región más cercana a las microondas, con longitud de onda entre 15 μm y 100 μm

Todos los cuerpos emiten una cierta cantidad de radiación, y aunque esta resulta invisible para el ojo humano, existen dispositivos electrónicos capaces de "verla" por estar diseñados para ello.

**Receptor de infrarrojos**

Uno de los receptores más universal utilizado en placas tipo Arduino es el receptor de infrarrojos universal TL1838, VS1838B o simplemente 1835 de 38KHz, que es el que lleva montado la placa TdR STEAM y cuyo aspecto podemos ver en la imagen siguiente:

En el datasheet TL1838 del dispositivo tenemos toda la información sobre el mismo destacando las siguientes características:

- Voltaje de funcionamiento: 2.7V a 5.5V
- Frecuencia: 37.9KHz
- Ángulo de recepción: 90°
- Rango de recepción: 18m

El dispositivo genera una señal de salida que sirve para controles remotos universales y utiliza la codificación NEC. El receptor de infrarrojos permite codificar los protocolos de señales de pulsos infrarrojos utilizados por los mandos a distancia. Los protocolos detectados son los siguientes: RC5, RC6, NEC, SONY, PANASONIC, JVC, SAMSUNG, WHYNTER, AIWA, LG, SANYO, MITSUBISHI y DENON. Es decir, detectaría cualquier señal emitida por cualquiera de esos mandos.

**Emisor de infrarrojos**

En nuestro caso como emisor de infrarrojos vamos a utilizar el control remoto de Keyestudio que vemos en la imagen siguiente:

El mini control remoto tiene 17 teclas de función y tiene las siguientes especificaciones:

- Batería: pilas de botón CR2025
- Distancia de transmisión: hasta 8 m
- Ángulo efectivo: 60°

El control remoto, o mando a distancia, por IR funciona emitiendo trenes de pulsos de luz infrarroja. Diferentes señales corresponden a botones diferentes La señal infrarroja transmite el código correspondiente al botón del mando a distancia pulsado al dispositivo en forma de una serie de impulsos de luz infrarroja. El receptor recibe la serie de impulsos de infrarrojos y los pasa a un procesador que decodifica y activarán una determinada función del dispositivo. En el reto y las actividades del mismo obtendremos estos códigos. En ArduinoBlocks se han asignado los siguientes nombres a las teclas:

> **TRUCO** En las prácticas con Infrarrojos, cuando las cosas no van, es muy útil saber si el problema es que el emisor de infrarrojos funciona o no funciona para descartar otros problemas.
> El truco es simple, y sirve para cualquier mando: Como las cámaras de los móviles si detectan el Infrarrojo no visible, utiliza la cámara de tu móvil hacia el led del emisor del infrarrojos y aprieta cualquier botón, si se enciende el led (visto desde la cámara de tu móvil) el emisor funciona.

**Bloques en ArduinoBlocks**

El sensor receptor de infrarrojos permite obtener la cadena de texto con el código en formato hexadecimal correspondiente al tren de pulsos de IR generado al pulsar una determinada tecla. El bloque es el que vemos en la imagen siguiente:

El valor devuelto por el bloque de recepción será una cadena de texto con valor vacío en caso de no detectar ningún código. Al devolver el bloque una cadena de texto debemos recordar que lo tenemos que almacenar en una variable de tipo texto.

Si utilizamos mandos genéricos RC5 como el modelo de Keyestudio, podemos usar el bloque de la imagen siguiente para comparar los códigos recibidos y así identificar fácilmente cada tecla.

#### En la TdR STEAM

#### Programando la actividad

Vamos a realizar un programa en el que si pulsamos la tecla Ok del control remoto se nos encienda el diodo LED rojo. La solución la tenemos disponible en ESP32-SM-Actividad-11 que es el programa que vemos en la imagen siguiente:

Sabemos que el diodo IR está recibiendo un código porque junto al mismo hay un diodo LED rojo que parpadea.

#### Retos de ampliación

- **A11.R1.** Realizar un programa que encienda el LED RGB en los colores establecidos a continuación y según la tecla flecha pulsada.
  - Flecha arriba = Rojo
  - Flecha izquierda = Verde
  - Flecha derecha = Amarillo
  - Flecha abajo = azul
- **A11.R2.** Realizar un programa que nos muestre por consola el código hexadecimal correspondiente a cada una de las teclas pulsadas junto a un texto descriptivo indicador de la tecla pulsada en cada caso, es decir, que mantenga una estructura del tipo: El CODIGO se corresponde con la tecla TECLA pulsada.

---

## 5. Prácticas con otros elementos del kit

### Actividad 12. Puerto de expansión I2C. La LCD de 2x16

Página extraída de Federico Coca Notas sobre ESP32 STEAMakers CC-BY-SA

#### Enunciado

Utilizaremos las comunicaciones I2C para mostrar textos en la pantalla LCD I2C incluida en el kit.

#### Teoría

**Las comunicaciones I2C**

Dado que la placa TdR STEAM dispone de un puerto de expansión I2C (del inglés Inter-Integrated Circuit = Circuito inter-integrado) vamos a explicar un poco en que consiste este sistema de conexionado.

Bus conocido por las siglas I2C, IIC o I2C, es un bus serie de datos desarrollado en 1982 por Philips Semiconductors (hoy NXP Semiconductors, parte de Qualcomm). Se utiliza principalmente internamente para la comunicación entre diferentes partes de un circuito, por ejemplo, entre un controlador y circuitos periféricos integrados. Posteriormente fue adoptado progresivamente por otros fabricantes hasta convertirse en un estándar del mercado con miles de circuitos integrados de diferentes fabricantes.

I2C también se denomina TWI (Two Wired Interface) únicamente por motivos de licencia, denominación introducida por Atmel. No obstante, la patente caducó en 2006, por lo que actualmente no hay restricción sobre el uso del término I2C.

El bus I2C requiere únicamente dos cables o lineas de señal para su funcionamiento, uno para la señal de reloj (SCL, Serial Clock) y otro para el envío de datos (SDA, Serial Data). Ambas líneas precisan resistencias de pull-up hacia Vcc. Cualquier dispositivo conectado a estas líneas es de drenador o colector abierto (Open Collector), lo cual en combinación con las resistencias pull-up, crea un circuito Wired-AND.

Para ser reconocido en el bus, cada dispositivo dispone de una dirección física, que se emplea para acceder a cada uno de ellos de forma individual. Esta dirección puede ser fijada por hardware, en cuyo caso se pueden modificar los últimos 3 bits mediante "jumpers" o microinterruptores (ejemplo de la matriz de 8x8), o por software.

En general, cada dispositivo conectado al bus debe tener una dirección única. Si tenemos varios dispositivos similares tendremos que cambiar la dirección o, en caso de no ser posible, implementar un bus secundario.

El bus I2C tiene una arquitectura de tipo master-slave, lo que indica que el master es el encargado de controlar al resto de dispositivos tipo slave con los que se comunica y que se comunican con el, teniendo siempre el marte prioridad absoluta. El dispositivo master es el que inicia la comunicación con los slaves. Los slaves no pueden iniciar la comunicación (el master tiene que preguntarles), ni hablar entre si directamente.

El bus I2C debe ser por lo tanto síncrono, es decir debe existir una señal de reloj que controle las comunicaciones. Es el master el que proporciona la señal de reloj, que mantiene sincronizados a todos los dispositivos del bus. De esta forma, se elimina la necesidad de que cada dispositivo tenga su propio reloj, de tener que acordar una velocidad de transmisión y mecanismos para mantener la transmisión sincronizada como en UART o SPI.

El protocolo de comunicación I2C sigue la siguiente secuencia:

- Primero, el master genera la señal de reloj del bus (SCL).
- Se inicia la comunicación por orden del master al establecer la condición de START, que se produce cuando SDA pasa de uno a cero y se mantiene en cero durante un tiempo.
- El master direcciona a los slaves.
- El master indica si se va a leer o escribir.
- El slave direccionado responde con una señal de conformidad ACK (acknowledge).
- Se transmite los datos byte a byte desde SDA al receptor. Por cada pulso desde SCL se transmite un bit de información.
- El destinatario de la información responde con una señal de conformidad ACK.
- Se acaba la comunicación cuando el master establece la condición de STOP, que se produce cuando SDA, por orden del master pasa de cero a uno y se mantiene en uno durante un tiempo.

Son muchos los dispositivos I2C que se pueden direccionar por este bus I2C, siendo lo más común en los dispositivos para I2C que utilicen direcciones de 7 bits, aunque existen dispositivos de 10 bits, pero es un caso raro. Una dirección de 7 bits implica que se pueden poner hasta 128 (27) dispositivos sobre un bus I2C. Hemos visto que las direcciones son de 8 bits y esto es porque el bit extra de los 7 de la dirección lo emplea el master para informar al slave si va a leer o escribir. Si el bit de lectura/escritura es cero, el dispositivo master está escribiendo en el slave. Si el bit es 1 el master está leyendo desde el slave. La dirección de 7 bit se coloca en los 7 bits más significativos del byte y el bit de lectura/escritura es el bit menos significativo.

**La LCD 1602**

Una pantalla LCD (del ingés, Liquid Cristal Display) de 2 líneas de 16 caracteres tiene el aspecto y la distribución de pines que vemos en la imagen siguiente.

Es evidente que deberíamos utilizar bastantes patillas de nuestra placa tipo UNO (es el formato que tiene la ESP32 STEAMakers) para su control. En la imagen siguiente se muestra el conexionado mínimo necesario en una pantalla de este tipo: 4 bits para datos y dos señales de control En (Enable) y Rs (Register select). La conexión RW la ponemos a GND. Además se debe añadir una resistencia ajustable o un potenciómetro para regular el contraste de la pantalla.

Es preferible utilizar alguna de las que tienen el aspecto que vemos en la imagen siguiente:

En realidad el conjunto que vemos en la imagen anterior no es más que una LCD 2x16 a la que se ha incorporado un módulo adaptador de LCD a I2C. Este modulo está especialmente diseñado para poder soldarlo directamente a la LCD y convertirla así en un dispositivo I2C que además ya lleva incorporado el potenciómetro de ajuste de contraste en alguno de los casos.

Este tipo de pantalla requiere cuatro cables para establecer las conexiones, dos cables SDA (datos) y SCL (reloj) para el bus de comunicaciones I2C y los dos cables de alimentación VCC y GND.

La dirección I2C por defecto de este tipo de módulos puede ser 0x3F o en otros casos 0x27, e incluso hay modelos en los que se puede cambiar. Para un correcto control es muy importante identificar correctamente la dirección I2C de nuestro modulo pues de otra forma nuestro programa no funcionará correctamente.

Una LCD 1602 I2C es muy sencilla de controlar a partir de los bloques que nos proporciona ArduinoBlocks. En la imagen siguiente ponemos como ejemplo los bloques para imprimir un texto o variable en un par fila-columna determinado.

En la siguiente figura se muestra el sistema de distribución de filas y columnas.

**Escanear dispositivos I2C**

Si no conocemos la dirección específica de nuestro módulo podemos utilizar un pequeño programa que llamaremos Escaner-I2C y que se encargará de identificar la dirección I2C y todos los dispositivos I2C conectados a nuestra placa. Debemos crear un proyecto, en esta ocasión, de tipo "Arduino UNO" para tener disponible el menú I2C que nos de acceso al bloque "Escanear dispositivos I2C..." tal y como vemos en la imagen siguiente:

Un sencillo programa como el de la imagen siguiente nos permite ver los dispositivos I2C conectados y su dirección física asociada. El programa está disponible como Escaner-I2C.

**Definición de símbolos en la LCD**

Dentro de los bloques del menú Visualización -> Pantalla LCD está el de "definir símbolo", que permite definir uno de los 8 símbolos personalizables que puede almacenar el micro de la pantalla LCD. El símbolo se define por un mapa de bits (unos y ceros indicando cada píxel del símbolo). Los símbolos tienen una resolución de 5x8 píxeles (blanco o negro).

En ArduinoBlocks disponemos de una herramienta que nos ayuda a definir nuestros propios símbolos y podemos acceder a ella desde herramientas o haciendo clic derecho sobre el bloque, desplegándose en cualquier caso un editor muy sencillo de usar.

Para tener el símbolo disponible simplemente copiamos la cadena generada en el lugar correspondiente del bloque.

#### En la TdR STEAM

En la placa TdR STEAM tenemos el conector I2C con los mismo pines de conexión que la LCD y debemos respetar el orden de conexionado indicado en la siguiente tabla:

```json
{
  "type": "table",
  "id": "table-06",
  "page": 194,
  "title": "Conexionado del conector I2C de la TdR STEAM",
  "headers": ["TdR STEAM", "LCD 1602", "Color cable"],
  "rows": [
    ["GND", "GND", "Negro"],
    ["Vcc", "Vcc", "Rojo"],
    ["SDA", "SDA", "Amarillo"],
    ["SCL", "SCL", "Blanco"]
  ],
  "source": "CATEDU - ESP32 en el Aula"
}
```

La ubicación del conector I2C en la TdR STEAM lo vemos en la imagen siguiente:

Recordemos que en el caso de la LCD con micro interruptores o LCD direccionable dispone de un pequeño hub I2C que permite conectar dos dispositivos I2C más. El término direccionable no me parece una denominación muy correcta dado que el otro tipo también es direccionable, aunque tengamos que soldar.

#### Programando la actividad

Como primer ejemplo de uso vamos a mostrar una determinada información en la pantalla LCD, en concreto vamos a mostrar una serie de seis textos en ambas filas que se irán alternando cada tres segundos en la pantalla. El programa de la imagen siguiente lo tenemos disponible en ESP32-SM-Actividad-inicial.

#### Retos de ampliación

**LCD.R1.** Corregir el error ortográfico en la palabra "Robotica" de la actividad anterior. Para ello tenemos que definir nuestro propio símbolo de "ó" (o acentuada).

Definimos el símbolo requerido tal y como vemos en la imagen siguiente:

El programa resuelto es el de la figura siguiente:

**LCD.R2.** Realizar un control de iluminación del LED RGB mediante PWM y mostrar por pantalla el valor de la iluminación en cada instante. Se realizará el control desde el mínimo de iluminación a máximo y cuando se alcance el máximo bajamos otra vez a mínimo.

El programa resuelto es el de la figura siguiente:

Se ha resuelto con un contador ascendente y otro descendente sobre el LED rojo. Se pueden probar diferentes opciones de LEDs o incluso combinación de ellas. También se anima al lector a comprobar que ocurre si quitamos la opción "Número entero" y ponemos directamente la variable del bucle y buscar la explicación.

---

### Actividad 13. Sensor de sonido o micrófono

**Actividad 13 Visualización del nivel sonoro**

Vamos a hacer este programa:

vernivelsonoro.abp

https://www.youtube.com/embed/u3ipwFAjf9Y

Página extraída de Federico Coca Notas sobre ESP32 STEAMakers CC-BY-SA

#### Actividad 13 bis. Enunciado

Realizaremos pruebas básicas de detección de nivel de sonido añadiendo esta opción externa al pin analógico A3 disponible en el conector correspondiente.

#### Teoría

Un micrófono es un transductor (dispositivo que convierte energía de una forma a otra) que convierte la energía sonora en señales eléctricas. Micrófonos hay una amplia diversidad tanto en formas como tamaños. Dependiendo de la aplicación, un micrófono puede utilizar diferentes tecnologías para convertir sonidos en señales eléctricas.

Para el caso de aplicaciones con placas tipo Arduino suelen usarse sensores basados en el micrófono de condensador electret que es un condensador de placas paralelas y trabaja como una capacitancia variable. Se forma con una placa fija (placa trasera) y una movible (diafragma) con una pequeña separación entre ellas. Cuando el sonido golpea al diafragma este se mueve cambiando así la capacitancia entre las placas.

El sensor microfónico de keystudio se utiliza normalmente para detectar el nivel de ruido en el ambiente. El pin S del mismo es una salida analógica, es decir, una tensión de salida en tiempo real del micrófono. El sensor viene con un potenciómetro que permite ajustar la ganancia de la señal dentro de un determinado rango.

#### En la TdR STEAM

El conector micrófono externo en A3.

Como programa sencillo inicial vamos simplemente a enviar a la consola el nivel de sonido que detecte nuestro micrófono. El programa de la imagen siguiente esta disponible como ESP32-SM-micro-inicial.

#### Programando la actividad

Actividad inicial con el micro.

#### Retos de ampliación

**Micro.R1.** Modificar el programa de la actividad inicial para que muestre los datos por la LCD.

**Micro.R2.** Partiendo del programa del reto 2 de la actividad LCD (LCD.R2) modificarlo para que muestre los datos del micrófono tanto al final de la cuenta ascendente como de la descendente.

---

### Actividad 14. Sensores internos de ESP32

Ya vimos en SENSORES ESP32 que esta placa tiene internamente unos sensores que podemos utilizar.

Nuestra propuesta para experimentar es con los sensores de potencia. Vamos a ver este experimento consistente en encender y apagar diferentes elementos de TDR STEAM Imagina y ver las variaciones:

experimentoenergia.abp

Se puede observar las variaciones de tensión cuando se apaga y se enciende.

Y también se puede ver como el consumo va aumentando cada ver que encendemos y apagamos.

Un programa para verificar la tensión de alimentación de la placa ESP32 Plus STEAMakers lo vemos en la figura siguiente:

**Medir la tensión de alimentación**

Que nos arroja un resultado en la consola como el que vemos en la figura siguiente:

¿No tendría que subir linealmente? Pues por lo visto el consumo en los cambios es mucho mayor y los sensores lo detectan y en los estados estacionarios o los sensores no lo detectan.

Página extraída de Federico Coca Notas sobre ESP32 STEAMakers CC-BY-SA

**A1. Leer valor de tensión de alimentación**

El programa SP-medidor-energia de la figura siguiente realiza la captura en variables de los cuatro parámetros disponibles y los envía al Serial Plotter. Para modificar el valor de los mismos se han creado las funciones encender y apagar que encienden y apagan los diodos LEDs de la TdR STEAM y de la tira de 8 LEDs (NO PROPORCIONADO POR CATEDU).

**A.2. Graficar todos los parámetros del 'Medidor de energía'**

Programa Serial Plotter.

En la figura siguiente vemos el resultado de forma gráfica.

Un programa como el de la figura siguiente nos va a mostrar por consola los valores leídos por los sensores internos.

**A.3. Sensores internos**

Sensores internos.

El resultado en consola lo vemos en la figura siguiente:

#### Retos

**R1.** Realizar la actividad A2 mostrando los datos por consola.

**R2.** Realizar la actividad A2 mostrando los datos en la LCD.

**R3.** Hacer una captura de datos en formato CSV de alguno de los parámetros del 'Medidor de energía'.

---

### Avanzado: Multitarea, interrupciones, memoria Flash y tarjeta SD

Las placas convencionales y ordenadores antiguos que sólo tienen un núcleo en el microprocesador, sólo pueden hacer una tarea. Se puede hacer por software que el microprocesador realice varias tareas simplemente dando tiempo a cada una de ellas e ir saltando de una a otra, es decir, no es una programación en paralelo, y si el micro no es potente, acaba por saturarse.

ESP32 Plus Steammaker tiene un microprocesador pero tiene dos núcleos. Tiene capacidad para hacer algunas tareas en paralelo.

Como estos conceptos pertenecen a un perfil más avanzado, se escapa de los propósitos de este curso. Si se quiere trabajar con ellos recomendamos el siguiente Descarga desde el drive del autor tutorial Manual de Actividades ESP32 SteamMaker 2022_Junio.

Aquí están las páginas y los retos para más información:

**Multitarea**

7.17 Reto A17. Multitarea. ..................................................... 177
7.17.1 Reto A17.1. Multitarea I. .................................................... 182
7.17.2 Reto A17.2. Multitarea II. ................................................... 183
7.17.3 Reto A17.3. Multitarea III. .................................................. 184
7.17.4 Reto A17.4. Multitarea IV. .................................................. 185
7.17.5 Reto A17.5. Multitarea V. ................................................... 188

**Interrupciones**

Una interrupción es un evento (por ejemplo pulsar un pulsador) y hace que el micro deje lo que estaba haciendo y salte a realizar una tarea concreta. En la placa TDR STEAM hay dos pulsadores, en D3 y en D5 que pueden realizar interrupciones al ESP32.

Aquí están los retos y las páginas en Descarga desde libros.catedu..es Manual Actividades ESP32 SteaMakers 2022_Junio.pdf

Descarga desde el drive del autor tutorial Manual de Actividades ESP32 SteamMaker 2022_Junio

7.18 Reto A18. Interrupciones. ............................................... 189
7.18.1 Reto A18.1. Control de interrupciones. ................................... 190

**Memoria Flash**

El ESP32 Plus STEMaker tiene una memoria Flash que puede mantener los datos incluso después de apagar la placa. Su capacidad es muy limitada y no se almacenan eternamente.

Descarga desde el drive del autor tutorial Manual de Actividades ESP32 SteamMaker 2022_Junio

7.19 Reto A19. Memoria FLASH/EEPROM. ................................... 192
7.19.1 A19.1. Lectura/escritura en la memoria EEPROM I. .................... 195
7.19.2 A19.2. Lectura/escritura en la memoria EEPROM II. .................... 198

**Tarjeta SD**

El ESP32 Plus STEAMaker tiene un zócalo para insertar tarjetas microSD. Tiene que estar formateada a FAT32 y admite hasta 2 Teras con archivos máximos de 2G.

Aquí están los retos y las páginas en Descarga desde el drive del autor tutorial Manual de Actividades ESP32 SteamMaker 2022_Junio

7.13 Reto A13. Tarjeta SD. ..................................................... 155
7.13.1 Reto A13.1. Almacenar datos: Datalogger. ............................... 157
7.13.2 Reto A13.2. Leer datos almacenados. ..................................... 159
7.13.3 Reto A13.3. Escribir y leer datos. .......................................... 160

---

## 6. Bluetooth

### Un poco de teoría Bluetooth

**ONDAS**

Una onda es una señal que se propaga por un medio. Por ejemplo el sonido, que es una onda mecánica que viaja usando el aire o cualquier otro material. Pero en el caso de las señales eléctricas pueden ser enviadas por el cable o a través del vacío (no necesitan un medio para transmitirse).

Dependen de 3 parámetros principalmente:

- Amplitud: altura máxima de la onda. Hablando de sonido representaría el volumen. Si nos referimos a una onda eléctrica estaríamos representando normalmente el voltaje.
- Longitud de onda λ: distancia entre el primer y último punto de un ciclo de la onda (que normalmente se repite en el tiempo).
- Frecuencia f: Número de veces que la onda repite su ciclo en 1 segundo (se mide en hertzios).
- Periodo T es simplemente es la inversa de la frecuencia. T=1/f

La relación entre ellas es muy fácil pues las ondas electromagnéticas viajan a la velocidad de la luz c y si velocidad es espacio/tiempo luego c = λ/T luego c = λ*f

Dentro del espectro electromagnético encontramos diferentes tipos de señales dependiendo de las características de su onda.

**TRANSMISIÓN INALÁMBRICA: BLUETOOTH**

Hoy en día, este grupo está formado por miles de empresas y se utiliza no sólo para teléfonos sino para cientos de dispositivos.

Bluetooth es una red inalámbrica de corto alcance pensada para conectar pares de dispositivos y crear una pequeña red punto a punto, (sólo 2 dispositivos).

Utiliza una parte del espectro electromagnético llamado "Banda ISM", reservado para fines no comerciales de la industria, área científica y medicina. Dentro de esta banda también se encuentran todas las redes WIFI que usamos a diario. En concreto funcionan a 2,4GHz. (Un G son 10^9) luego entre FM y Microondas.

Hay 3 clases de bluetooth que nos indican la máxima potencia a la que emiten y por tanto la distancia máxima que podrán alcanzar.

¿Sabías que? Su curioso nombre viene de un antiguo rey Noruego y Danés, y su símbolo, de las antiguas ruinas que representan ese mismo nombre.

También es muy importante la velocidad a la que pueden enviarse los datos con este protocolo.

**¿Bluetooth clásico o Bluetooth Low Energy = BLE?**

Es un protocolo similar al clásico Bluetooth pero diseñado a consumir menos potencia manteniendo funcionalidad. Su popularidad ha crecido en multitud de dispositivos.

En robótica, el clásico device que utiliza BLE es la Micro:bit. Aunque la Micro:bit no tiene Wifi integrada, posee una radiofrecuencia que podemos configurar para Bluetooth (hay que elegir, o utilizar sus comandos de Radio o utilizar comandos de Bluetooth).

Por eso a la hora de elegir la APP tienes que tener en cuenta:

- Si acepta Bluetooth clásico o BLE
- Que la APP acepte leer datos desde el robot como enviar

Nosotros hemos elegido uno sencillo que cumple las dos condiciones (hay muchas APPs) Serial Bluetooth Terminal.

### APP Serial Bluetooth Terminal

Esta APP es muy sencilla y la puedes descargar aquí. Tiene las siguientes ventajas:

- Enviar / Recibir mensajes
- Permitir conexiones tanto BLUETOOTH CLÁSICO por ejemplo HC06 de Arduino, Echidna, ESP32 ... como BLUETOOTH LE (Low emision) por ejemplo para la MICRO:BIT

Si no esta emparejado con el móvil NO TE PUEDES CONECTAR, para ello entramos en Devices.

**DESCARGA LA APP**

**EMPAREJAR DISPOSITIVOS**

- Microbit: Entramos en Devices y en Bluetooth LE y nos conectamos a la Micro:bit
- HC06 para Arduino Echidna ESP32.... igual pero en Bluetooth clásico

Aquí puedes ver dos capturas de dispositivos en Bluetooth clásico y Bluetooth BLE. LOS QUE ESTAN EN VERDE SON LOS QUE TIENES EMPAREJADOS Y PUEDES CONECTARTE.

**CONECTARTE**

Una vez seleccionado el dispositivo emparejado ya puedes conectarte:

1. Menú
2. Entras en Terminal
3. Enchufe
4. Sale conectado, ya estas preparado para enviar y recibir

¿Y si no aparece o no esta emparejado? Entras en el diálogo de Android de Bluetooth y lo emparejas.

### Actividad 15 APP->ESP32

**Preliminar**

A diferencia del Arduino que necesita un módulo exterior el HC06, el ESP32 tiene el Bluetooth integrado.

Para inicializar el Bluetooth, STEAMAKERBLOCKS tiene instrucciones específicas, lo primero es definir un nombre a la señal Bluetooth para que los otros dispositivos (tu móvil) lo encuentre, por ejemplo en la figura ESP32 STEAMakers.

El bloque Fijar timeout significa que fijamos el tiempo en la transmisión de datos por bluetooth. Por defecto está fijado en 1000 ms pero podemos reducirlo a 100 ms como en la figura para que funcione más fluido.

**Enunciado**

Si recibe un código, que encienda un led. Por ejemplo:

- si recibe un 1 que se encienda el led rojo.
- si recibe otro código, apaga el led rojo

Este enunciado parecido a este programa en Arduino con Bluetooth.

**Programa**

El programa es sencillo: http://www.arduinoblocks.com/web/project/1013787

https://www.youtube.com/embed/GaB3B9wSA8s

**Opción con texto**

Podemos poner en vez de una variable numérica un texto, pero el Bluetooth añade un carácter al final que no siempre se lee bien por lo que recomendamos usar en la condicional "empieza con" en vez de "=".

Con la palabra ROJO se enciende pero también con cualquiera que empiece con R.

### Actividad 15 con otra APP: Arduino Bluetooth Control

Esta APP es para comunicación PLACA->APP es decir, el Bluetooth será como receptor de datos nuestra placa electrónica (slave) y el móvil (master) como emisor de datos.

Esta APP permite enviar datos pero de distintas formas.

**La APP Arduino Bluetooth Control**

Esta APP es muy completa y configurable, aquí para descargarla de Google Play.

El código de programa que tenemos que cargar en la placa se basa en escuchar de forma continua el puerto serie. Cuando llegue el dato, se ejecutará la acción que le indiquemos. ¡¡así de sencillo!!

Hay que vincular nuestro móvil y nuestra APP de Android con el Arduino, para ello sigue este sencillo tutorial:

https://docs.google.com/presentation/d/e/2PACX-1vT0vG1z61MuZXKmdiw4ga7z15FlQfeussqDNYzMauJSZUU2G2NlL7M-JjXb4PFT4YTigj9Yal8PzHmR/embed?start=falseloop=false&delayms=3000

**Vincular móvil**

Recuerda que para que funcione el Bluetooth tienes que poner el interruptor alejado del borde.

Ver https://libros.catedu.es/books/esp32-en-el-aula/page/bluetooth-en-el-esp32

**El resultado**

https://www.youtube.com/embed/e3y4DSwCQBQ

**Reto**

¿Te atreves a hacerlo con voz? Por ejemplo si dices AZUL que encienda el led AZUL si dices ROJO que encienda el ROJO y si dices APAGAR que los apague.

### Actividad 16 APP<->ESP32

**Enunciado y programa STEAMAKERBLOCKS**

Ahora vamos a realizar la comunicación bidireccional. El propósito es que si recibe un código, que encienda y apague los leds, pero además vamos añadir comunicación hacia la APP del móvil, que nos envíe información de los sensores. Un ejemplo de enunciado sería:

APP->ESP32:

- si recibe un R que se encienda el led rojo y apague el led azul.
- si recibe un A que se encienda el led azul y apague el led rojo.

APP<-ESP32:

- Que envíe a la APP el valor de la temperatura del DHT11.
- Que envíe a la APP el valor de la humedad del DHT11.
- Que envíe a la APP el valor de la luz del LDR.

Además lo vamos a complicar un poco más: que visualice los valores de temperatura y luz en el display LCD para que se vea que corresponden a los que muestra en la APP (no se muestra el de la humedad pues no cabe en el LCD).

Este enunciado parecido al programa en Arduino https://libros.catedu.es/books/arduinoblocks-en-el-aula/page/app-tdr-steam-arduinoblocks

El programa ya es más complejo: http://www.arduinoblocks.com/web/project/1050441

**Enunciado**

**Programa**

https://www.youtube.com/embed/c89tMSy4V6s

### Actividad 16 con la APP Serial Bluetooth Terminal

**Actividad 16 con APP INVENTOR**

La comunicación con la placa en este caso no es tan sencilla como en el caso anterior, no nos vale las APPs que hay en Google Play que envían un código y en paz, ahora tenemos que tener una APP que si reciben un código que hagan algo. Esto ya es exclusivo por lo tanto hay que programar una APP que cumpla los requisitos. En nuestro caso lo hemos hecho en APP INVENTOR.

https://appinventor.mit.edu/

**La APP en el móvil**

En la parte de DESIGNER.

NO ES EL OBJETIVO DE ESTE CURSO FORMARTE EN APP INVENTOR.

Pero si no conoces el programa, te recomendamos que vayas a estos contenidos que de una manera muy fácil aprenderás a crear programas con APP INVENTOR y exportarlos al móvil.

https://libros.catedu.es/books/app-inventor

En la parte de Blocks.

ATENCIÓN: A partir de Android 12 hay que dar permisos a la aplicación para que pueda visualizar los dispositivos bluetooth disponibles, para ver la explicación.

Hay que añadir este código:

Puedes descargarte la APP en este enlace pero tienes que permitir en el móvil instalar APPs desconocidas.

Otra forma es en este código QR utilizando la APP de Google Play MIT AI2 Companion y poner el código sxbbnv.

Aquí tienes los pasos de su realización:

https://docs.google.com/presentation/d/e/2PACX-1vS3LG1KflZ_hr17TpJ3kOsPfX9E4Cq85Q3tfL0VTGExQzr_QpOFsVHYvbS0oUTIwXS_kuiSYftWGthX/embed?start=falseloop=false&delayms=3000

https://www.youtube.com/watch?v=MNLzS-MOXAg

El programa lo tienes aquí: https://gallery.appinventor.mit.edu/?galleryid=e4780fa4-3252-4d73-b846-b2a0935c6d01

Tienes dos opciones:

- **EN VIVO CONNECT - AI COMPANION** esta opción es la más rápida, y realmente lo simula a través de la APP INVENTOR.
  - Tienes que tener instalada la APP MIT AI2 COMPANION
  - Se le pasa el código de tu APP a la APP

- **OTRAS OPCIONES**
  - Ver https://appinventor.mit.edu/explore/ai2/setup
  - Instalas la APP MIT AI2 COMPANION
  - En APP INVENTOR
  - Y sale un código y un QR asociado al código

**La APP a tu móvil**

**OPCIÓN EN VIVO AI COMPANION**

Abrimos la APP MIT AI2 COMPANION y metemos el código anterior (o lo escaneamos con el QR).

En APP INVENTOR verás que sale una barra de progreso enviando tu APP a tu móvil. Cuando termina automáticamente lo ejecuta.

https://www.youtube.com/embed/fAnqXJSY4tY

**El resultado**

---

## 7. Qué es IoT

Fuente Wikipedia IoT Internet de las cosas CC-BY-SA

De Drawed by Wilgengebroed on FlickrTranslated by Prades97 CC BY-SA 3.0

Estamos hablando de dispositivos que se conectan a internet de forma desatendida, por vía hardware (o mejor dicho firmware) a diferencia de un ordenador, tablet o móvil, donde tienes que configurar por software el dispositivo y hay un diálogo entre usuario y dispositivo sobre el uso de Internet (el software solicita tal página web, tales datos etc por voluntad del usuario o por diálogo con el usuario) Aquí los dispositivos están ya configurados de los datos que se comunican. Es decir "conectar y olvidar".

El Internet de las cosas (Internet of Thing IoT) describe objetos físicos —o grupos de estos— con sensores, capacidad de procesamiento, software y otras tecnologías que se conectan e intercambian datos con otros dispositivos y sistemas a través de internet u otras redes de comunicación.​ El Internet de las cosas se ha considerado un término erróneo porque los dispositivos no necesitan estar conectados a la Internet pública. Sólo necesitan estar conectadas a una red y ser direccionables individualmente.

Piensa en la diferencia entre un enchufe inteligente y un ordenador, el primero es lo que se considera dentro de IoT.

- **Blynk:** lo que nos gusta de esta herramienta es que es casi "instantánea" o "síncrona". Esto es imprescindible con ciertos robots como el Rover Marciano con Arduino. Necesitamos que "gire" para evitar un obstáculo, no podemos esperar !!!. Veremos con BLYNK un protocolo que entre el dispositivo electrónico (nuestro robot) y nosotros (en ordenador, en una APP en el móvil) la comunicación es instantánea, gracias a un servidor que hará de intermedio, que puede ser local (BLYNK LEGACY) o en Internet (BLYNK IoT).
  - Blynk legacy es la que se va a trabajar en Rover Marciano con Arduino, Arduinoblocks en el aula, ESP32 en el aula
  - Blynk IoT es la que se va a trabajar con En ESP32 en el aula, En Smart Home ESP32

- **ThinkSpeak y SmartioSpace:** Smart Agriculture Kit para Micro:bit

- **MQTT:** El emisor envía datos, se almacenan en un servidor, y cuando puede, lo vuelca al cliente. Cliente y emisor pueden ser el dispositivo electrónico y nosotros o viceversa. Veremos que esto es lo que hace el protocolo MQTT y está tremendamente extendido por lo barato y fácil que es. Hace que los servidores no estén tan ocupados, por lo tanto hay varios proveedores que ofrecen este servicio gratuitamente. Hay robots como los que tienen la placa TDR STEAM IMAGINA que envía datos de temperatura, humedad, .. y pueden recibir datos pero no precisan de esta exigencia instantánea como un rover.
  - ESP32 EN EL AULA
  - En Smart Home ESP32

- **TELEGRAM:**
  - ESP32 EN EL AULA
  - En Smart Home ESP32

Desventajas: El acceso a Internet de dispositivos caseros puede generar problemas a nivel mundial:

- el caso Mirai
- aspiradores que nos espían

**IoT en los cursos de Aularagón**

- Arduino cloud IoT
- Arduino Alvik
- Cyberpi y mBot2
- Iot con Cyberpi

---

## 8. IoT-Wifi-Telegram

### Crear bot en Telegram

Entramos en nuestro Telegram y chateamos con el creador de los bots: @BotFather y nos saldrá esta pantalla:

Si tecleamos /start nos sale las diferentes opciones.

Para crear un nuevo bot, tecleamos /newbot y nos preguntará el nombre del bot. Por cierto, el nombre tiene que acabar con las letras bot, NOS PROPORCIONARÁ EL TOKEN DEL ROBOT, QUE TOMAREMOS NOTA.

Si tecleamos /mybots nos sale los diferentes bots creados y al pulsar en uno de ellos nos salen sus opciones.

### Encontrar tu ID en Telegram

En este caso para que mi Bot me envié mensajes a mi usuario de Telegram directamente busco mi ID.

Vamos a chatear con @myidbot y le preguntamos por nuestro identificador con /getid.

**Buscar tu ID: chat privado**

TOMAMOS NOTA DE NUESTRO IDENTIFICADOR ID.

**Buscar ID de un grupo**

En este caso tendríamos que añadir a @myidbot al grupo y ejecutar el comando en el chat del grupo /getgroupid saldrá un identificador negativo.

Una vez conseguido el ID podemos eliminar @myidbot del grupo.

### Código para enviar y recibir

1. Lo primero es conectar con la wifi
2. Y lo segundo conectar con el Bot que hemos creado, gracias al TOKEN con la instrucción INICIAR API TOKEN
3. Enviamos al ID un mensaje de bienvenida con las instrucción Enviar a Chat ID .... Mensaje ... Formato ....

Hemos añadido algunos elementos de control, como el LCD y un zumbador.

En el evento TELEGRAM - NUEVO MENSAJE RECIBIDO se puede utilizar el comando TELEGRAM MENSAJE en el siguiente programa se puede ver como en la pantalla del LCD aparecerá quien es el remitente y qué mensaje.

Luego envía la temperatura si el usuario de Telegram envía la palabra temp.

**Bucle Inicio**

> ATENCIÓN si en el mensaje a enviar pones carácteres no standard, puede ser que no funcione. Por ejemplo a mi no me ha funcionado enviar ºC.

**Enviar y recibir**

### Actividad 17 Telegram

Este es el resultado:

https://youtube.com/shorts/Uaan2VYEHcM?feature=share

https://www.youtube.com/embed/Uaan2VYEHcM

Puedes probarlo en t.me/JavierArduinobot

Puedes hacer que ante un evento, te envíe un mensaje por ejemplo el pulsador 1.

**Ampliemos con avisos de alarma**

El resultado es:

https://www.youtube.com/embed/-UopsDIMKsc

Imagina que el pulsador está conectado a una ventana, entonces por Telegram te puede avisar si ha entrado un ladrón.

> **RETO AVISO TEMPERATURA ELEVADA** Suponte que tienes vacunas en una nevera, y quieres se te avise de forma remota que se supera un valor determinado para tomar medidas antes de que se estropeen. Haz un programa que te envíe un aviso por Telegram si la temperatura alcanza un determinado valor.

---

## 9. IoT-Wifi-Blynk IoT

Blynk nació como software libre como Blynk legacy y en Catedu aprovechamos este servicio para realizar Rober Marciano con Arduino. La idea era sencilla: Programabas en STEAMAKERBLOCKS y el robot se comunicaba con el servidor Blynk legacy y con escritorio Dashboard via web (Panel Web) o APP BLYNK ponías Gadgets y controlabas el robot:

En junio 2022 Blynk legacy deja de dar servicio y pasa a Blynk.io, una plataforma de pago pero que tiene Gadgets gratuitos suficientes para nivel educativo.

Entramos en la página https://blynk.io/ de y nos registramos en LOG IN.

### ¿Qué es Blynk.io?

Sabías que...? Blynk legacy al ser software libre te lo puedes descargar y montar tu propio servidor Blynk legacy con lo que tendrías recursos y gadgets ilimitados. Esto lo trataremos en un capítulo aparte.

**Registro en Blynk.io**

Nos pide un email. Cuando lo ponemos, nos llega este mensaje que tenemos que dar al botón "Complete setup". Nos saldrá un diálogo para elegir la contraseña, una pequeña encuesta.

**CONCEPTOS CLAROS**

En BLYNK se crea el Dispositivo o Device ESP32 que contendrá el programa realizado en STEAMAKERBLOCKS y en el programa se insertan estos datos que nos proporciona BLYNK:

- ID DE LA PLANTILLA
- NOMBRE DE LA PLANTILLA
- TOCKEN

Se definen en BLYNK las variables de flujo, flujo de datos o Datastream que son variables virtuales V1 V2, ..... tú en tu programa de STEAMAKERBLOCKS almacenas o recoges la información.

Y finalmente nuestro objetivo: un Panel Web o Dashboard que es un panel donde controlas online tu ESP32 y cada gadjet que pones esa asociado a una variable virtual.

### Crear DASHBOARD en Blynk.io

Vamos a crear un DASHBOARD o PANEL DE CONTROL para controlar nuestro ESP32.

**AÑADIR DEVICE**

1. Vamos a Devices
2. Create New
3. Buscamos ESP32
4. Elegimos Quick start

Nos saldrá un código que tiene tres cosas importantes que tienes que guardar (En download te lo baja en formato .ino que lo puede leer el bloc de notas)

1. ID DE LA PLANTILLA
2. NOMBRE DE LA P LANTILLA
3. TOCKEN

Una vez creado el Device, le damos dos clicks y nos sale el Template. Al darle a EDIT tenemos opción de ir añadiendo las variables asociadas a los pines virtuales, TE RECOMIENDO BORRAR LAS QUE TE PONE Y AÑADIR TÚ LOS PINES VIRTUALES por ejemplo en este caso DE ESP32 KEYSTUIDIO TDR STEAM IMAGINA.

**DATASTREAMS O FLUJO DE DATOS**

| NOMBRE | PIN VIRTUAL | TIPO | UNIDAD | MIN | MAX |
|--------|-------------|------|--------|-----|-----|
| LED ROJO | V1 | entero | | 0 | 1 |
| SIMPSON | V2 | entero | | 0 | 1 |
| LCD | V3 | CADENA | | | |
| PULSADOR | V4 | entero | | 0 | 1 |
| TEMPERATURA LM35 | V5 | entero | ºC | 0 | 100 |
| TEMPERATURA DHT11 | V6 | entero | ºC | 0 | 100 |
| HUMEDAD | V7 | entero | % | 0 | 100 |
| SONIDO | V8 | entero | | 0 | 4095 |

Una vez creado el Device, le damos dos clicks.

Ves añadiendo las variables que quieras visualizar o gobernar, dándoles las unidades, valores min, max correspondientes.

> No utilices ni el potenciómetro ni el sensor de luz, tal y como vimos en Sensores y actuadores de la placa Imagina TDR STEAM, cuando hay comunicación Wifi, están inutilizados.

**TEMPLATE PANEL WEB**

Si le damos dos clicks sale el Template.

En los tres puntos horizontales le podemos cambiar el nombre.

En el Edit podemos poner nuestros elementos.

Vamos a ir añadiendo WIDGETS ASOCIADOS A ESOS DATASTREAMS para crear tu panel de control, algunos son de pago.

Los puedes redimensionar, borrar, etc... En el botón de la rueda dentada vas asociando el Widget con el pin virtual V1, V2, ... V8.

Fuente https://blynk.io/

**APP BLYNK IOT**

Hay una APP sencilla, que al loguearse YA APARECE EL DEVICE lo único que hay que hacer es el TEMPLATE asociado, y es muy sencillo.

Podemos visualizar y crear las plantillas en el móvil, para ello sigue las instrucciones.

**ESP32 SMARTHOME**

he puesto de pines virtuales:

- TEMPERATURA asociado al pin virtual V1 entero unidades ºC minimo 0 máximo 100 (por ejemplo)
- VENTILADOR asociado al pin virtual V2
- HUMEDAD asociado al pin virtual V3

Podemos poner multitud de widgets, vamos a simplificar con ESP32 al Template: Temperatura y humedad. Template al ESP32 un botón para encender y apagar el ventilador.

### Actividad 18 Blynk IoT

**Crear programa en STEAMAKERBLOCKS**

Tiene que cargar los siguientes datos de la Wifi y de la conexión con Blynk.io:

- El nombre de la red wifi y su contraseña para conectarse
- El ID de la plantilla creada
- El nombre del Device
- El token para dar acceso a esa plantilla y device

De paso hemos inicializado el LDC para que nos muestre datos.

**Programa Steamakerblocks: Al inicializar...**

Si no te acuerdas de los tres últimos, mira más abajo cómo puedes localizarlos.

Vamos a hacer que si se pulsa en el dashboard el interruptor asociado al pin virtual V1 que se encienda el led rojo.

Luego si se pulsa en el dashboard el pin 2 que suene los simpsons.

**A programar de Dashboard -> ESP32.**

Luego si se introduce texto en V3 que en la pantalla LCD lo diga.

Vamos a crear un programa que vaya recogiendo los valores de ESP32 cada 3 segundos (para no agobiar al servidor Blynk) y los vuelque al Dashboard.

**A programar de ESP32 -> Dashboard.**

- V4 tiene los valores 0 o 1 según el valor del pulsador 1 de la placa TDR SteaMaker por lo tanto enciende el LED del dashboard de Blynk.io si se pulsa.
- V5 capta la temperatura del LM35, da un valor más exacto que es que visualiza el DHT11
- V6 copia la temperatura del DHT11
- V7 tiene los datos de la humedad del DHT11
- V8 registra los datos del nivel de sonido del sensor micrófono incorporado y conectado en el A3

Para ver que realmente los valores de V8 no siguen fielmente a los reales, vamos a poner en el bucle esta instrucción para que visualice los valores de sonido registrados:

https://www.youtube.com/embed/nCK1QpBMfLI

**ESTE ES EL RESULTADO**

**No me acuerdo de estas tres cosas: TOKEN - ID PLANTLLA - NAME PLANTILLA ¿Dónde puedo encontrarlo?**

Primero Entras en Blynk.io y Te logueas Log in y luego:

1. Entras en Depeloper Zone/Zona de desarrollador
2. My Templates/Mis plantillas
3. Haz dos clicks en la plantilla

Con dos cliks en Authtoken ya se queda copiado en el portapapeles para que lo pegues en tu programa STEAMAKERBLOCKS.

Más a la derecha hay una ventana Firmware configuration/Configuración de firmware donde puedes encontrar el ID de la plantilla y su nombre: Copiar y pegar el trozo de código, pegarlo en un editor y copiar sólo el ID y el NAME para pegarlo en tu código STEAMAKERBLOCKS.

---

## 10. Avanzado: Blynk Legacy local

Lo primero que tenemos que conseguir es:

- Tener una Raspberry con el sistema operativo propio de la raspberry instalado, antes se llamaba Raspbian, ahora Raspberry Pi OS
- Comunicarnos con la Raspberry por comandos SSH
- Una vez hecho esto que es lo básico instalaremos el servidor Blynk

Ahora vamos a ver unas páginas para:

- Instalar un sistema operativo en una Raspberry
- Una vez instalado hay que conectarlo a la red wifi y ponerle una IP FIJA
- Para comunicarse vía comandos SSH, aconsejamos hacerlo de forma remota, pues lo contrario implica tener siempre una pantalla, teclado y ratón conectado en la Rasperry

### Raspberry: Qué hay que hacer para empezar

**¿Qué Rasberry habría que comprar?**

Aconsejamos una que tenga la Wi-fi incorporada, nosotros hemos hecho pruebas con la Raspberry Pi 3B+ y con la Raspberry Pi4 y no encontramos diferencias de velocidad para estos propósitos de robótica, luego por la mitad de precio aconsejamos la Raspberry Pi 3B.

### Raspberry: Poner un Sistema Operativo

**¿Es el único sistema operativo que se puede instalar?**

No, podemos instalar otros sistemas operativos en nuestra Raspbery (evidentemente uno sólo cada vez, poner dos a la vez en la rasp sería forzarlo demasiado). Por ejemplo:

- Podemos instalar un Linux-Ubuntu ligero pero que se puede usar en una aula de informática (ver libro del curso de Aularagon Monta tu aula de informática con Raspberry).
- Si no podemos vivir sin Windows, hay un Windows 10 especial gratis (sí has leído bien, los de Microsoft van entendiendo eso de si no puedes con ellos únete a ellos, pero no te hagas ilusiones, sólo vale para la Raspberry y no esperes una máquina que sustituya a tu PC va lentísimo).
- Sistemas operativos para aplicaciones concretas:
  - Video juegos: Recalbox.
  - Dómótica y control Home Assitant

Nuestro sistema operativo de este curso (y el mejor que "rula en la Rasp") pues está adaptado a la arquitectura ARM de la Raspberry es RASPBIAN o actualmente lo llaman RASPBERRY PI OS.

Hay dos opciones, elige la que quieras (nuestra preferida es la A):

**Opción A: Instalar el sistema operativo en la tarjeta sin NOOBS**

Con esta opción no tienes que encender la Rasbperry.

https://docs.google.com/presentation/d/e/2PACX-1vQoxDLLHMvB-mCQwm2en9cBgb1faamFG0YJIiFDFuNrGH8TuH8U-4zCDg_K9CkM4gFl-Wy6TxBNLg9j/embed?start=falseloop=false&delayms=3000

**Opción B: Instalar la Raspbian en la tarjeta con NOOBS**

Con esta opción SI que tienes que encender la Rasbperry con pantalla, teclado y ratón.

https://docs.google.com/presentation/d/e/2PACX-1vR4wwk8BwdSEgk-aTQ_xgvrQYJ-cr2QhN_35Q-mYJxYedhT5P-vF6UkDbSsHJ5I_zLS7IqBirdNfI4t/embed?start=falseloop=false&delayms=3000

Esto es válido para cualquier ordenador: Descargar la ISO de un Sistema Operativo, grabarlo en un pincho de forma autoarrancable, pero por curiosidad, no es tan fácil como en la RASPBERRY.

Se añade esta presentación como curiosidad:

https://docs.google.com/presentation/d/e/2PACX-1vSvr4JxqRNkTwI0mcFJdfbIe5BtDpSGyLO4ucyAyk65f3zXsFa3zxIyFZiPcqRuv_2YEfrGY39SFVi0/embed?start=falseloop=false&delayms=3000

### Raspberry: Cambiar usuario y contraseña

El usuario por defecto es pi y su contraseña es raspberry pero lo podemos cambiar perfectamente.

**Opción A: remota con SSH**

Entramos por SSH como hemos aprendido, y tecleamos:

```bash
sudo passwd pi
```

y nos pide enseguida la contraseña, la tenemos que insertar dos veces no se puede ver.

**Opción B: local por pantalla**

Entramos por VNC o conectamos una pantalla, teclado y ratón a la raspberry y en Preferencias-RaspberryPi configuration.

Y entramos en System.

### Raspberry: Conectarlo a la red

**Opción A: La Raspberry con pantalla, teclado y ratón**

Esta es más fácil, pero tienes que encender la Raspberry con teclado, pantalla y ratón:

https://docs.google.com/presentation/d/e/2PACX-1vQShQenHWgn0_axlCmlKpIX6kqQOHHzaIHhy7SxTtXjLOXZip40JO5B-UB7KRx6g1Z8M1LsUg2N8fi8/embed?start=falseloop=false&delayms=3000

**Opción B: La Raspberry sin pantalla, teclado y ratón**

Con esta opción es más difícil, pero no tienes que encender la Rasbperry para la configuración, sólo manipular los ficheros de la tarjeta micro SD.

https://docs.google.com/presentation/d/e/2PACX-1vSuE389RRI67Vi1LGxySj5rWjhfNMjV9t27FbO80BOqMqDJyKcH7hFZWdOXubwsuO8NtnwXtaTQfg4p/embed?start=falseloop=false&delayms=3000

Texto que hay que poner en interfaces:

```
auto wlan0
iface wlan0 inet static
address 192.168.1.xxx
gateway 192.168.1.1
netmask 255.255.255.0
wpa-ssid el_nombre_tu_red_wifi
wpa-psk la_contraseña_de_tu_wifi
dns-nameservers 8.8.8.8 188.244.82.1
```

Texto que hay que poner en wpa_supplicant.conf:

```
# /etc/wpa_supplicant/wpa_supplicant.conf
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1
network={
    ssid="nombre de tu router o SSID"
    psk="tu contraseña del wi-fi"
    key_mgmt=WPA-PSK
}
```

### Raspberry: Conexión SSH

Controlar Raspberry pi de forma remota y de forma textual es muy rápido y eficaz, sobre todo para la robótica con AlphaBot.

SSH (Secure Shell) según Wikipedia es el nombre de un protocolo y del programa que lo implementa, y sirve para acceder servidores privados a través de una puerta trasera. Te recomiendo visitar esta página de Luis Llamas.

Recuerda que lo que hemos hecho es:

- Hemos conectado la Raspberry a la Wifi
- Hemos activado el protocolo SSH y VNC en la raspberry
- Hemos fijado una IP y la sabemos para poder acceder a él.

Ya podemos trabajar por SSH con la Raspberry, no nos hace falta que conectemos la raspberry a una pantalla, teclado, etc....

**YA PODEMOS ENCENDER LA RASPBERRY** si has elegido las opciones A de 3.-Raspbian y 4.-Conectando aún no habrás encendido la Raspberry.

**Si trabajas con Windows**

No lo tiene nativo, tenemos que instalar Putty.

Y rellenamos los campos de la IP (la que hayas determinado, en la imagen es 192.168.1.111), puerto y el protocolo SSH, es recomendable grabar la sesión para tenerlo en futuras entradas.

Se abre una ventana pidiendo el usuario pi y contraseña por defecto rasbperry.

**Si trabajas con Linux**

Linux tiene de forma nativa el protocolo SSH, lo activamos en el icono en negro que es el Terminal:

Supongamos que la IP fija que le hemos asignado a la Rasbperry la IP 192.168.1.131 Tecleamos:

```bash
ssh pi@192.168.1.131
```

Te pide usuario y contraseña, por defecto es usuario pi y la contraseña raspberry, la tecleas no la puedes ver, te tiene que salir algo así en la pantalla:

```
pi@raspberrypi:~ $
```

Cuando te sale `pi@raspberrypi:` es que ya está preparado para recibir órdenes.

Si después de un intento fallido, o realizar la conexión con otra computadora.... te sale este error al intentar conectarte por ssh:

```
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@ WARNING: REMOTE HOST IDENTIFICATION HAS CHANGED! @
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
IT IS POSSIBLE THAT SOMEONE IS DOING SOMETHING NASTY!
Someone could be eavesdropping on you right now (man-in-the-middle attack)!
It is also possible that the RSA host key has just been changed.
The fingerprint for the RSA key sent by the remote host is
Please contact your system administrator.
Add correct host key in /home/user/.ssh/known_hosts to get rid of this message.
Offending key in /home/user/.ssh/known_hosts:1
RSA host key for ras.mydomain.com has changed and you have
requested strict checking.
Host key verification failed.
```

Entonces antes de intentar conectarte por ssh, hay que obligar a la Raspberry que reinicie las claves de conexión de ssh, ejecuta esta orden:

Supongamos que la IP fija que le hemos asignado a la Rasbperry en el punto 4 es 192.168.1.131 Tecleamos:

```bash
ssh-keygen -R 192.168.1.131
```

### Raspberry: Apagar

Apagar de forma caliente (es decir simplemente quitando de la fuente de alimentación la corriente) daña al sistema operativo Rasbpian dejando ficheros corruptos.

**7.1 Opción de forma remota con SSH**

Muy fácil, teclea:

```bash
sudo poweroff
```

**7.2 Opción local de forma gráfica**

Igual que en otros sistemas operativos Windows o Linux tenemos que apagar desde el menú Shutdown.

### Raspberry: VNC

VNC es un programa que nos permite la conexión remota con los servidores pero de forma gráfica. Es el sistema elegido por RASPBIAN pues ya lo tiene incorporado, pero no activado.

Hay que tener claro que son dos programas:

- **VNC SERVER** que es el programa que se ejecuta en la RASPBERRY y que aunque viene instalado, hay que activarlo. Es el programa que lanza el escritorio para que lo lea:
- **VNC VIEWER** es el programa que tenemos que tener en nuestro ordenador para ver lo que lanza VNC SERVER.

En la imagen podemos ver un pantallazo de mi ordenador, el escritorio negro es mi escritorio y el de la carretera es el de la Raspberry:

### Raspberry: Instalar Java 8

Una vez que tenemos la Raspberry funcionando y accesible por SSH o por VNC es el momento de instalar el servidor Blynk, primero hay que, para instalar Blynk, se necesita la versión 8 de Java.

Seguimos las instrucciones de https://github.com/Peterkn2001/blynk-server#blynk-server

Entramos en la ventana de comandos SSH y ejecutamos las siguientes órdenes, si en algún momento nos pide confirmación [Y/n] es porque faltan descargar paquetes o confirmación de instalación, por lo tanto aceptamos.

Con esta orden busca las actualizaciones:

```bash
sudo update
```

y ya ejecutamos que instala la versión 8 de java (curiosamente no funciona con la versión 64 bits de Raspberry OS sino con la de 32 bits):

```bash
sudo apt install openjdk-8-jdk
```

Por último una vez finalizado, comprobamos la versión que coge por defecto:

```bash
java –version
```

Tiene que salir Openjdk version 1.8.0 etc...

Suele pasar que tenga ya instalado la versión 11, tenemos que obligar a que sea la 8 por defecto, para ello ejecutamos:

```bash
sudo update-alternatives --config java
```

**Si no sale esa versión...**

Si seleccionamos el 2 nos lo pondrá como por defecto (sale con un (*). Podemos comprobar que ya nos sale la versión con la orden:

```bash
java –version
```

Pero esto no nos sirve, pues al reiniciar la Raspberry volverá a la versión 11.

Para ponerlo por defecto, edita el fichero environment:

```bash
sudo nano /etc/environment
```

Y si en la orden `sudo update-alternatives --config java` salía que la carpeta donde está la versión 8 es `/usr/lib/jvm/java-8-openjdk-armhf/jre/bin/java` luego tenemos que poner en el fichero environment:

```
JAVA_HOME="/usr/lib/jvm/java-8-openjdk-armhf/jre/bin/java"
```

Guardar, reiniciar:

```bash
sudo reboot
```

Y comprueba:

```bash
java –version
```

Y tiene que salir:

### Raspberry: Instalar y ejecutar el servidor Blynk local

**1 Descarga Blynk**

Crea una carpeta en tu directorio home, por ejemplo Blynk:

```bash
mkdir Blynk
```

Y descarga Blynk:

```bash
wget "https://github.com/Peterkn2001/blynk-server/releases/download/v0.41.16/server-0.41.16-java8.jar"
```

El enlace https://github.com/Peterkn2001/blynk-server/releases/download/v0.41.16/server-0.41.16-java8.jar conviene actualizarlo, recomendamos visitar la página https://github.com/Peterkn2001/blynk-server#blynk-server y coger la última versión de aquí.

**2 Configurar server.properties**

Necesitamos crear un fichero de configuración para las diferentes opciones que queremos en nuestro servidor Blynk.

Entra en la carpeta creada Blynk y crea el fichero server.properties:

```bash
cd Blynk
sudo nano server.properties
```

A continuación se muestra un posible contenido de server.properties:

```
initial.energy=1000000
allow.reading.widget.without.active.app=false
user.message.quota.limit=100
logs.folder=./logs
user.dashboard.max.limit=100
lcd.strings.pool.size=6
server.ssl.key=./server_embedded.key
webhooks.response.size.limit=96
hardware.mqtt.port=8440
table.rows.pool.size=100
terminal.strings.pool.size=25
admin.email=admin@blynk.cc
admin.rootPath=/admin
user.widget.max.size.limit=20
listen.address=
blocking.processor.thread.pool.limit=6
stats.print.worker.period=60000
enable.db=false
force.port.80.for.csv=false
enable.raw.db.data.store=true
restore.host=blynk-cloud.com
csv.export.data.points.max=43200
restore=false
user.profile.max.size=256
allow.store.ip=true
allowed.administrator.ips=0.0.0.0/0,::/0
net.interface=eth
webhooks.frequency.user.quota.limit=1000
http.port=8080
web.request.max.size=524288
user.devices.limit=50
async.logger.ring.buffer.size=2048
user.tags.limit=100
server.ssl.key.pass=
admin.pass=admin
hard.socket.idle.timeout=10
product.name=Blynk
data.folder=/Path
map.strings.pool.size=25
profile.save.worker.period=60000
https.port=9443
log.level=info
server.ssl.cert=./server_embedded.crt
force.port.80.for.redirect=true
notifications.queue.limit=2000
notifications.frequency.user.quota.limit=5
server.host=192.168.137.1
app.ssl.port=8443
hardware.default.port=8442
hardware.ssl.port=8441
hardware.mqtt.port=8440
```

Para la explicación de cada línea, aconsejo consultar esta página en el apartado Configuración avanzada del servidor local.

**3 Ejecutar el servidor Blynk local**

En la Raspberry por comandos SSH, entramos en la carpeta donde hemos creado el servidor Blynk:

```bash
cd Blynk
```

Y ejecutamos el servidor Blynk instalado, pero que cargue la configuración de server.properties que en nuestro caso como el la Raspberry el usuario se llama catedu la carpeta es catedu:

```bash
java -jar server-0.41.16-java8.jar -dataFolder /home/catedu/Blynk -serverConfig /home/catedu/Blynk/server.properties
```

Curiosamente la primera vez que ejecutas esta instrucción te sale los datos del usuario admin@blynk.cc y su contraseña sin encriptar que por defecto es admin. Si no has tomado nota, ejecutar la instrucción anterior no sirve de nada pues ya ha creado el fichero texto de este usuario.

La única forma de que te vuelva a mostrar la contraseña es borrar el fichero texto y ejecutar otra vez la orden java -jar server....

**4 Que la orden de ejecución se haga automáticamente cada vez que se reinicie la Raspberry**

Para no repetir estos dos comandos cd Blynk y java -jar server-0.41.16-java8.jar -dataFolder /home/catedu/Blynk -serverConfig /home/catedu/Blynk/server.properties cada vez qye reiniciamos la Raspberry puedes generar un script para que lo ejecute automáticamente, puedes ver buenos tutoriales en Internet.

En internet puedes ver varios métodos:

Método1 es entrar en /etc y editar el fichero rc.local y añadir esta línea:

```
java -jar server-0.41.16-java8.jar -dataFolder /home/catedu/Blynk -serverConfig /home/catedu/Blynk/server.properties &
```

Método 2 usar el comando crontab -e y poner al final la siguiente línea:

```
@reboot java java -jar server-0.41.16-java8.jar -dataFolder /home/catedu/Blynk -serverConfig /home/catedu/Blynk/server.properties
```

**5 Probarlo**

Si la IP de la Raspberry es 192.168.1.112 entonces entramos en:

https://192.168.1.112:9443/admin

Seguramente te saldrá la siguiente advertencia por el certificado SSL, dale a Configuración avanzada y luego a Acceder a (la IP del servidor Blynk Legacy) sitio no seguro.

**Vale, ya estoy ¿y ahora qué?**

Tienes que entrar con el usuario y contraseña fijada en server.properties:

```
# Default admin name and password. Will be created on initial server start
admin.email=admin@blynk.cc
admin.pass=admin
```

Si quieres cambiar la contraseña, tienes que hacerlo como un usuario normal en la página de administración tal y como hemos visto en el capítulo Entrando en el Blynk local: El panel de control.

**6 Para saber más:**

https://github.com/Peterkn2001/blynk-server#blynk-server

Intalación de Blynk: How to Install a Blynk Local Server on Raspberry Pi

Configuración de server.properties.

**7 Para saber más: Configurar mail.properties**

Este apartado ya comentamos que no lo aconsejamos, pues los alumnos no suelen tener email y la APP ya no permite crear usuarios con email, pero si queremos que envíe los tokens por email, hay que crear este fichero para que el servidor envíe por email los tokens de los proyectos.

Entra en la carpeta creada Blynk y crea el fichero mail.properties:

```bash
cd Blynk
sudo nano mail.properties
```

A continuación se muestra una muestra del posible contenido de mail.properties:

```
mail.smtp.auth=true
mail.smtp.starttls.enable=true
mail.smtp.host=smtp.gmail.com
mail.smtp.port=587
mail.smtp.username=Your EMAIL ID
mail.smtp.password=Password
```

Utilizando Your EMAIL ID y Password los datos de una cuenta de gmail tuya. En esa cuenta tienes que permitir accesos no seguros.

**Para saber más**

Configuración mail

### En Windows: Instalar Java 11

Entramos en la web de Oracle - Java - Technologies - JavaSE y descargamos e instalamos el servidor Java 11, si nuestro ordenador no es viejo, seguro que soportará la versión 64.

https://www.oracle.com/es/java/technologies/javase/jdk11-archive-downloads.html

Instalamos el servidor Java descargado.

Para que Windows encuentre la ruta del Java instalado cuando ejecutemos comandos, le tenemos que decir en qué camino está la carpeta del java instalado está. Para ello vamos a C -> Archivos de programa -> Java -> Jdk11...-> carpeta bin y copiamos la ruta:

> Seguramente para la descarga Oracle nos pide que nos registremos. No entendemos el por qué pero efectivamente es necesario proporcionar un email y a ese email envía un enlace para el registro, Una vez registrado ya permite la descarga.

Nos vamos al sistema.

Y configuración avanzada del sistema - variables de entorno- path - editar - nueva y pegamos la ruta que hemos copiado anteriormente.

### En Windows: Instalar Blynk local

Descargamos el servidor Blynk server desde:

https://github.com/blynkkk/blynk-server/releases

o desde https://drive.google.com/file/d/1nPZxn-9Q9q0ceUhCiZGd4WRC1c8pufEQ/view?usp=sharing

y lo pegamos en una carpeta, por ejemplo en c:\Blynk_server

Creamos mail.properties y server.properties como ficheros nuevos, los editamos con un procesador de texto y pegamos el código que hemos explicado aquí.

> Ojo: Ten en cuenta que Windows le gusta colocar sus propias extensiones. Si editas un fichero con un procesador de textos, por ejemplo el bloc de notas, le añadirá .txt, si lo editas con Word le añadirá la extensión .docx, tienes que asegurarte que no se añada ninguna extensión, que los nombres de los ficheros sean mail.properties y server.properties y no otros. Ten activo la visualización de las extensiones para asegurarte que windows no añada las suyas.

### En Windows: Ejecutar Blynkserver

Entramos en comandos de windows como administrador.

Y ejecutamos esta instrucción:

```bash
java -jar server-0.41.17.jar -dataFolder /Path
```

de esta manera se crean las carpetas logs y static que nos dicen los errores que podemos encontrar.

La primera pantalla nos dirá el nombre la url, el nombre de usuario y la contraseña para entrar en el servidor blynk.

### En Linux: Instalar Blynk Legacy local

Seguimos las instrucciones de https://github.com/Peterkn2001/blynk-server#blynk-server

Pero si tu centro tiene Vitalinux, ponte en contacto con nosotros soportecatedu@educa.aragon.es para instalar en un ordenador Vitalinux el servidor Blynk de forma local.

### Blynk Legacy: La APP

La APP de BLYNK LEGACY no la encontramos en el buscador de Google Play de forma tradicional, pues está sin mantenimiento, tenemos varias opciones para descargar la APP.

**OPCIÓN A: Desde Google Play**

En este enlace aún tiene la APP antigua, pero es de propiedad de Blynk Inc luego no es de extrañar que desaparezca.

https://play.google.com/store/apps/details?id=cc.blynk

> OJO no confundir Blynk (legacy) que es el que vamos a trabajar con Bynk IoT que sí que lo encuentras en el buscador de Google Play.

**OPCIÓN B: Fuera de Google Play**

No nos tenemos que fiar de descargar APK de repositorios fuera de Google Play, luego una vez descargado, pasamos el fichero por una página de Antivirus, por ejemplo https://www.virustotal.com/gui/home/upload

**OPCIÓN B: ANTES DE LA INSTALACIÓN**

No nos tiene que dar ningún virus.

Para instalarlo en tu móvil:

Primero, tenemos que llevar el fichero .apk a tu dispositivo, recomendamos usar email, por ejemplo enviándote a ti mismo un correo electrónico y lo consultas desde el móvil.

Segundo, tenemos que instalarlo y para ello hay que decirle que confiamos con apps instaladas fuera del repositorio oficial (Google Play), como depende las pantallas del modelo de tu móvil, puedes encontrar cualquier tutorial en internet cómo se hace pero prácticamente es llegar a la misma pantalla en seguridad/privacidad- permitir apps de orígenes desconocidos.

Tercero instalarlo.

Cuarto, deshacer el segundo paso.

Puedes buscar en un navegador esta APP, encontraras varios sitios para descargarla, por ejemplo aquí:

https://blynk.uptodown.com/android/descargar
https://blynk.en.uptodown.com/android/download/3921223
Github: https://github.com/BlynkMobile
Desde este repositorio nuestro.

**OPCIÓN B DESCARGA**

### Blynk Legacy: Crear cuentas

Antes se creaban cuentas en Blynk usando el correo electrónico: Cada usuario en la APP de Blynk podía crearse una cuenta, enviando un email. El servidor local Blynk puede enviar correos electrónicos si tiene configurado un fichero que se llama mail.properties y se envía el correo con las credenciales. No obstante esta opción de crear cuenta ha desaparecido de la APP (En CATEDU ya barruntábamos esto, que Blynk Inc al quitar crear nuevos usuarios es que pensaba quitar este servicio Blynk legacy).

No obstante, la creación de usuarios mediante emails era un problema pues menores de 16 años no pueden tener emails ni redes sociales, ni whatsapps (¿oigo risas?).

En este caso necesitarás tener un servidor Blynk legacy local que tal y como lo explicamos en los siguiente capítulos, montado en una Raspberry.

Entramos en la carpeta de Blynk en nuestra Raspberry, ya sea por VNC, o con una pantalla, teclado y ratón o por SSH y lo que hay que hacer es crear unos ficheros texto que se llamen emailusuario.Blynk.user los emails de los usuarios pueden ser inventados, por ejemplo en la figura puedes ver que en la raspberry hay dos usuarios user1@yo.es user2@yo.es luego los ficheros textos son user1@yo.es.Blynk.user y el otro es user2@yo.es.Blynk.user.

**Entrando por VNC o pantalla, teclado y ratón:**

En el curso vas a utilizar los servidores de CATEDU luego tendrás asignado 12 cuentas de alumnos + un profesor.

Recibirás un email con los nombres de usuario y las contraseñas.

**¿Y fuera del curso?**

**Entrando por SSH**

El contenido por ejemplo del fichero user2@yo.es.Blynk.user es:

```json
{"name":"user2@yo.es","email":"user2@yo.es","appName":"Blynk","region":"local","ip":"ip_local_raspberry","pass":"uffzlHwvejaeZZz2PzqmKuB22OACUDRLWvKEl7RCDQI=","lastModifiedTs":1663010486621,"lastLoggedIP":"192.168.1.73","lastLoggedAt":1635057921978,"profile":{},"isFacebookUser":false,"isSuperAdmin":false,"energy":99600,"id":"user2@yo.es-Blynk"}
```

Luego lo único que tienes que hacer para crear nuevos usuarios es crear ficheros texto que se llamen userx@yo.es.Blynk.user y con contenido igual que el anterior pero cambiando el numero 2 por x (si quieres respetar userx@yo.es pero puedes inventarte cualquier email ficticio).

+información aquí

**¿Por qué puede ser que el contenido de un fichero pueda tener más información o menos que otros?**

Porque en esos ficheros txt tiene la información de los proyectos creados por el usuario.

**¿Entonces si el fichero user1@yo.es.Blynk.user tiene toda la información del usuario y todas sus proyectos... si ese usuario quiere llevarse sus proyectos a otro servidor Blynk sólo tiene que copiar y pegar es fichero texto?**

Respuesta: SI, así de sencillo, ese fichero texto (por lo tanto libre de virus) tiene toda la información.

**¿En la APP no se almacena ningún proyecto?**

Ninguno, todos los proyectos están almacenados en esos ficheros txt si no hay conexión con el servidor, en la APP no aparece NADA.

**Vale, ya sé crear los nombres de usuarios ¿Y las contraseñas?**

En teoría están encriptadas en el fichero texto, como puedes ver, sale uffzlHwvejaeZZz2PzqmKuB22OACUDRLWvKEl7RCDQI= eso significa alcorisa.

Pero tranquilo, luego veremos en el panel de control cómo se pueden poner las contraseñas sin encriptar.

### Blynk Legacy: El panel de control

**Como entro en el panel de control**

En el curso de CATEDU:

Habrás recibido un email con la URL para entrar en la administración web del Blynk Legacy, con usuario y contraseña.

Fuera del curso de CATEDU usando tu servidor local:

Desde cualquier ordenador conectado en la misma red local que la raspberry, ejecutas en un navegador la siguiente dirección:

Si la IP de la Raspberry es 192.168.1.112 entonces entramos en:

https://192.168.1.112:9443/admin

Seguramente te saldrá la siguiente advertencia por el certificado SSL, dale a Configuración avanzada y luego a Acceder a (la IP del servidor Blynk Legacy) sitio no seguro.

**Vale, ya estoy ¿y ahora qué?**

Luego entramos con el usuario y contraseña que nos han proporcionado.

Y podemos ver los usuarios creados con los ficheros textos mencionados anteriormente.

**Cambiando las contraseñas de los alumnos**

Entrando en un usuario PODEMOS GENERARLE UNA CONTRASEÑA, por supuesto la pones normal, sin encriptar.

También puedes borrar el usuario si no nos interesa este usuario.

### Blynk Legacy: En la APP

**Conectar con el nuevo usuario**

Entramos en la APP de Blynk que hemos visto anteriormente como descargarla e instalara y entramos en Log In.

Y ponemos el nombre de usuario que hemos creado anteriormente, y la contraseña, la que hayamos definido en el panel de control.

IMPORTANTE: Entra en CUSTOM y pon LA DIRECCIÓN IP DEL SERVIDOR BLYNK LEGACY.

Si es dentro del curso de CATEDU habrás recibido un email de las IPs y de los puertos que hay que poner en esta APP de Blynk Legacy.

Si es fuera del curso, la IP DE LA RASPBERRY, O SEA DEL SERVIDOR LOCAL BLYNK y puerto 9443.

Podemos ver los proyectos que hay ya almacenados, vamos a crear un nuevo proyecto:

**Crear un nuevo proyecto**

Nos preguntará por el DEVICE:

En Arduinoblocks en el Aula, la placa es el TDR STEAM colocado en un Arduino con el ESP01 conectado, luego DEVICE Arduino Uno CONNECTION TYPE Wifi.

En Rover con Arduino, la placa es un NodeMCU v2, luego DEVICE NodeMCU CONNECTION TYPE Wifi.

En ESP32 en el Aula, la placa es un ESP32 con el Imagina TDR STEAM, luego DEVICE ESP32 DevBoard CONNECTION TYPE Wifi.

Empieza un nuevo proyecto, tienes un montón de energía y widgets para hacerlo:

Crea un nuevo proyecto, y así se crea en el servidor Blynk local un TOKEN que ahora veremos qué es.

Aquí tienes la captura de un proyecto o dashboard creado para el kit Imagina TDR Steam.

### Blynk Legacy: Poner el TOKEN en Steamakerblocks

**¿Cómo conseguir el TOKEN?**

**OPCION A: QUE LO HAGA EL ALUMNO En la APP**

Es la opción más sencilla, entrar en Devices pulsar en el Token y se copiará en el portapapeles del móvil, luego ir a cualquier aplicación para poder enviarla al PC (email, whatsapp...) y pegarla en Arduinoblocks en la instrucción que luego veremos.

**OPCION B: QUE LO HAGA EL PROFESOR En el panel de control**

Entramos en el panel de control del servidor Blynk y podemos ver en los usuarios creados los tokens.

Entrando en un usuario PODEMOS VER SUS PROYECTOS Y LOS TOKENS.

RECUERDA: UN PROYECTO UN TOKEN.

¿Qué se hace con ese TOKEN? Se pone en ARDUINOBLOCKS:

Entramos en ArduinoBlocks y vamos al bloque de comunicaciones IoT - Blynk legacy.

Tenemos que poner los datos de la IP servidor BLYNK LOCAL, y el TOKEN del proyecto.

DENTRO DEL CURSO CATEDU Habrás recibido un email con las IPs y los puertos a poner en Arduinobloks.

SI ES EN TU SERVIDOR BLYNK LOCAL Hay que poner la IP de la Raspberry o tu servidor local y EL PUERTO 8080.

En el caso de que es un proyecto con ARDUINO o TDR-STEAM- ARDUINO con ESP01 sale:

En el caso de sea un proyecto con NodeMCU o ESP32 como en el curso del Rover con Arduino o IoT en el aula sale:

> ATENCIÓN: ARDUINOBLOCKS CONNECTOR tiene que estar actualizado, al menos v5 (octubre 2022).

### Blynk Legacy: 1programa: Encender los pines rojo y verde

Vamos a ver un primer programa de la APP al TDR STEAM.

Una vez dentro del proyecto de la App aparece todo un panel si nada, añadimos controles apretando al + que hay en la parte superior.

Seleccionamos el botón.

Nos aparece el botón.

Pulsamos sobre él para entrar en sus propiedades, le decimos que vaya de 0 a 1 (es decir que cuando se apriete, que envíe un 1) que sea tipo switch (no pulsador, sino interruptor), le ponemos un color rojo para indicar que es el led rojo, y como el TDR-STEAM el led rojo lo tiene en el D12 le decimos que el pin es DIGITAL y D12.

Hacemos lo mismo con el azul pero D13.

En Arduinoblocks dejamos el token tal y como hemos aprendido anteriormente.

**¿Nada más?**

Nada más !! así de sencillo. Le damos a subir (teniendo el programa Arduinoblocks conector minimizado, eso lo podemos ver enseguida pues detecta en que COM está conectado, en la figura sale COM5).

Vamos a la APP de BLYNK, Pulsamos al botón de play ▶ de arriba arriba y vemos el estado NO TIENE QUE APARECER UN PUNTO ROJO si aparece es que nuestra placa no está conectada.

En ARDUINO BLOCKS.

Hay que tener algo de paciencia hasta que se comunica con la Raspberry, cuando no aparece el punto rojo, pulsamos en los botones y tienen que encenderse y apagarse correctamente los leds rojo y azul de nuestro TDR Steam.

Para usuarios del servidor Blynk de CATEDU y la placa ARDUINO CON ESP32 WIFI: No sabemos por qué pero al darle al Play, el icono de la placa de arriba sale en rojo, como si no estuviera conectado, pero el proyecto funciona perfectamente. Si sabes por qué por favor ponte en contacto con nosotros https://catedu.es/informacion/

### Blynk Legacy: 2programa RGB y el potenciómetro

**LED RGB**

En la APP de Blynk ponemos el gadget "Cebra".

Y lo configuramos según sus pines. El led RGB en el TDR Steam está conectado a los siguientes pines:

- Red D6
- Green D9
- Blue D10

**Potenciómetro**

El potenciómetro está conectado en A0 podemos insertar un gadget Label y lo configuramos como tal:

**¿En Arduinoblocks no hay que añadir nada?**

Nada !!! cuando son gadgets que leen directamente de los pines (digitales o analógicos) NO HACE FALTA MÁS CÓDIGO que el de conectar el servidor Blynk.

### Blynk Legacy: 3programa Medir la luz del LDR

Nuestro segundo programa será al revés del TDR Steam a la APP.

Ahora añadimos otro control level H.

Elegimos de PIN el analógico, el LDR está conectado al pin analógico A1 y como el LDR aumenta según la oscuridad vamos a poner que vaya de 1023 en formato negro.

Sin modificar nada del programa de ARDUINOBLOCKS vamos a darle al PLAY y ¡¡ Y FUNCIONA !!!

### Blynk Legacy: 4programa: Medir T y H con el DHT11

Este caso es distinto, pues:

- En el Rover marciano con Arduino el DHT22 está conectado al pin D5 digital del NodeMCU
- En el Arduinobloks en el aula, el DHT11 de la placa Imagina TDR Steam está conectado al pin D4 digital del Arduino
- En el IoT en el Aula el DHT11 de la placa Imagina TDR Steam está conectado al pin D4 digital del ESP32

Solución PINES VIRTUALES: si, has leído bien, vamos a utilizar pines virtuales.

Vamos a ARDUINOBLOCKS y establecemos dos pines virtuales, uno para la temperatura y otro para la humedad, arbitrariamente he puesto V2 y V3 pero puede ser cualquiera.

Para el kit de ROVER MARCIANO CON ARDUINO poner pin D5. Si el sensor es AZUL entonces DHT11 si el sensor es BLANCO entonces DHT22.

Para el kit que tenga la placa TDR STEAM IMAGINA es decir los cursos ARDUINO BLOCKS EN EL AULA y ESP32 EN EL AULA poner pin D4. Si el sensor es AZUL entonces DHT11 si el sensor es BLANCO entonces DHT22.

Fíjate que hay dos maneras de programar estos eventos:

- en el primero, utilizamos un bucle propio de Blynk que simplemente cada segundo lee el sensor y los almacenan los pines virtuales V2 y V3
- en el segundo no se ha utilizado ese bucle propio de Blynk sino simplemente dentro de Bucle hemos puesto otro bucle que se ejecuta cada 2 segundos, y dentro una funciona que se llama LECTURAS. dentro de lecturas esta la lectura de los pines virtuales V2 y V3

Y en Blynk incorporamos un Gauge que sea al PIN VIRTUAL V2. Modificamos también los límites, pues por defecto sale 0 a 1023 y se vería muy bajo la temperatura, ponemos -10 a 30. Si es para el Rover marciano de Arduino, allí se puede llegar a -50ºC y si es para el TDR Steam será en Aragón, el récord lo tiene Fuentes Claras con -30ºC. Da igual. Nosotros tenemos preferencia por el segundo método, nos parece más elegante y más controlable.

**En la APP de Blynk**

Para la humedad hacemos lo mismo:

- Pin virtual V3
- Límites 0% a 100%

Resultado:

### Blynk Legacy: 5programa: Lectura sensor LM35 y receptor IR

Podríamos hacer una lectura de estos sensores, sin necesidad de tratamiento ninguno, tal y como hemos hecho en la lectura de la luz con LDR, simplemente se añade un gadget a la APP de Blynk que:

- Lea el pin D11 que es donde está el sensor de infrarrojos
- Lea el pin A2 que es donde está el sensor de temperaturas LM35

Los resultados serían totalmente incorrectos !!!

- El sensor de infrarrojos lanza un código que al leerlo el pin D11 en la APP aparecería encendidos y apagados sin poder leer qué código es lo que dice
- En el sensor de temperaturas, es un sensor conectado al A2 por lo que en la APP mediría desde 0 hasta 1023, y esto no sólo habría que mapearlo a temperaturas, sino tratarlo correctamente pues el LM35 da lecturas de dos decimales.

En Arduinoblocks tenemos dos bloques específicos para tratar estas lecturas, las llevamos a pines virtuales y que los gadgets de la APP visualicen los valores de estos pines virtuales. Otro uso de los pines virtuales.

Ponemos dentro de la función LECTURAS los siguientes dos bloques:

**En Arduinobloks**

Como vemos, Arduinoblocks procesa la lectura de estos dos sensores, y simplemente se almacenan en los pines virtuales V7 y V8.

Ponemos para la lectura de la temperatura, un display que visualice el número V7.

**En la APP de Blynk**

Para el sensor de infrarrojos igual pero que visualice V8.

Lo subimos el programa Arduinoblocks al Arduino TDR Steam, pulsamos el play en la APP, esperamos a que se conecte y el sensor de temperatura muestra su valor perfectamente.

Para ver los códigos que se leen en Infrarrojos, hay que pulsar los números del mando a distancia.

Curiosamente dan unas lecturas algo diferentes el DHT11 y el LM35, el correcto es el LM35 pues el DHT11 no es un sensor muy preciso.

### Blynk Legacy: 6programa Leer eventos del TDR Steam

Hasta ahora hemos enviado eventos al TDR Steam, y leer sensores del TDR Steam pero .... ¿y leer un evento? por ejemplo leer si se pulsa los pulsadores D2 y D7.

Añadimos un gadget que se llama LED.

**En la APP de Blynk**

y leerá de un pin virtual pin V4 y otro gadget para V5.

Pondremos el siguiente código, simplemente lee que si se pulsa pues que encienda el led en el APP.

**En ARDUINOBLOCKS**

### Blynk Legacy: 7programa: El timbre

El timbre es algo especial, si ponemos una música, el Arduino está tan ocupado y el código engorda que da muchas desconexiones, si es el ESP32 lo aguanta bien.

En la APP ponemos un slider asociado a un pin virtual, por ejemplo a V9.

Y en Arduinoblocks añadimos un bucle que lea ese pin virtual V9 y que lo almacene en una variable numérica, que lo hemos llamado timbre.

Si esta variable, ha cambiado el valor, que haga un tono. si te fijas el valor máximo del slider se ha puesto a 2000, el máximo tono audible es 20.000, pero el slider no lo permite, por lo tanto, el truco es multiplicarlo por 10.

### Blynk Legacy: ¿Todo junto?

Si que se puede pero con la placa Arduino alguna vez se desconecta, pues no tiene un microprocesador muy potente. Con ESP32 sí que lo aguanta bien.

En la APP el dashboard o proyecto queda:

Y en ARDUINOBLOCKS.

---

## 11. Muro

https://padlet.com/embed/nnk8myhkdoze1cn8

Hecho con Padlet.

---

## 12. Para saber más ...

- https://content.innovadidactic.com/
- https://pedroruizf.github.io/steamakersmicroblocks
- App Ardutaller WB Control y manual en https://www.ardutaller.com.es/apps-by-ardutaller/manuales-app-ardutaller-wb-control
- Tarjeta micro SD, HID, servidor HTTP, cliente HTTP, Alexa, Telegram Bot, Wifimesh ...
- https://drive.google.com/file/d/1XZrXIEV3WdbZwsugKRka3MhwACDJvYUg/view
- https://drive.google.com/file/d/11OVVUzdMhZLwt6nxMWmzSioArvtdOict/view
- https://fgcoca.github.io/ESP32-STEAMakers/
- Descarga desde el drive del autor tutorial Manual de Actividades ESP32 SteamMaker 2022_Junio
- ESP32 PLUS STEAMMaker Imagina TDR STeam ArduinoBlocks
- Carpeta con los programas, circuitos, etc... https://drive.google.com/file/d/1HObvv4gBn-TB4pDG4W-JYIBScPXaXpMs/view
- Servidor HTTP, cliente HTTP, WifiMesh... https://docs.google.com/document/u/1/d/e/2PACX-1vQSrOKHpbLQHVbGFdAvp7DcndoftoHDI20nvwGMaxu_7bGc1bUCmi4U6DZrJWRSudc2iXBg43QMuzCT/pub#h.35h2u46mzlaq
- En este manual, puedes encontrar prácticas de MQTT usando THINGSPEAK Y THINGVIEW
- Arduino Free Book
- Manuales EducaconTic
- https://sites.google.com/view/educacont/documentaci%C3%B3n/hist%C3%B3rico/manuales?pli=1

---

## 13. Créditos

**Federico Coca** GitHub Twitter Instagram Más información.

Autor de los siguientes capítulos con licencia Creative Commons Atribución-CompartirIgual 4.0 International ("CC BY-SA"). Ver Notas sobre ESP32 STEAMakers - Miscelanea-Licencias https://fgcoca.github.io/ESP32-STEAMakers/Miscelanea/lic/

- Prácticas con sensores digitales
- Prácticas con sensores analógicos
- Prácticas con otros elementos del kit

**Javier Quintana Peiró** CATEDU.

Maquetador de todo el libro y autor de los siguientes capítulos con licencia Attribution-NonCommercial-ShareAlike 4.0 International (CC BY-NC-SA 4.0)

- Introducción
- Bluetooth
- IoT-Wifi-MQTT
- IoT-Wifi - Blynk
- IoT-Wifi - Blynk Legacy
- Cómo montar un servidor Blynk Legacy Local

Cualquier observación o detección de error en soporte.catedu.es

---

## Notas del procesamiento

- El documento original presenta algunas páginas con caracteres ilegibles o corruptos. Se ha conservado el texto legible y se ha reconstruido el contenido a partir del contexto cuando ha sido posible.
- Las tablas 1 a 6 han sido convertidas a JSON conservando su estructura y contenido.
- Las figuras y diagramas más relevantes han sido representados mediante JSON de tipo `image` o `diagram` con descripciones detalladas de sus elementos.
- No se ha inventado información. Los datos no determinables se han marcado como `null` o se han omitido.
- El código de los programas se ha transcrito tal como aparece en el documento original, con comentarios explicativos.
- Los enlaces y referencias se conservan tal como aparecen en el documento original.
- El documento es extenso (368 páginas) y se ha procurado mantener la estructura original, priorizando la información factual, los procedimientos, las tablas y los códigos.

---

**Fin del documento convertido.**
