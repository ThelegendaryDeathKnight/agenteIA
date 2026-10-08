# Manual de Programación Arduino

## Resumen técnico

Este documento constituye una guía rápida de referencia y manual de programación para la plataforma Arduino, traducido y adaptado por José Manuel Ruiz Gutiérrez a partir del "Arduino Notebook: A Beginner's Reference" de Brian W. Evans. El texto introduce al lector en el entorno de programación de Arduino, detallando la estructura básica del lenguaje (basado en C/C++), la declaración de variables, tipos de datos, operadores aritméticos y lógicos, y las estructuras de control de flujo fundamentales como `if`, `for`, `while` y `do...while`. 

Se abordan de manera exhaustiva las funciones de Entrada/Salida (E/S) digitales y analógicas, incluyendo `pinMode()`, `digitalRead()`, `digitalWrite()`, `analogRead()` y `analogWrite()`. Se explica el concepto de Modulación por Ancho de Pulso (PWM) para generar salidas analógicas simuladas, así como el uso de funciones de tiempo (`delay()`, `millis()`), matemáticas (`min()`, `max()`, `random()`) y comunicación serie (`Serial.begin()`, `Serial.print()`, `Serial.read()`).

La obra incluye una sección práctica de apéndices con esquemas de conexionado para componentes comunes (LEDs, pulsadores, potenciómetros, servomotores, motores DC y paso a paso, relés y transistores), así como una guía paso a paso para la creación de librerías propias de Arduino. Finalmente, se profundiza en la comunicación entre Arduino y otros sistemas (como el PC mediante Processing), el conversor Analógico-Digital (A/D) y las señales PWM, proporcionando ejemplos de código funcionales y explicaciones teóricas sobre protocolos de comunicación serie (RS-232, USB).

---

## Introducción y Datos del Documento

**Título original:** Arduino Notebook: A Beginner's Reference
**Autor original:** Brian W. Evans
**Traducción y adaptación:** José Manuel Ruiz Gutiérrez
**Licencia:** Creative Commons Attribution-Noncommercial-Share Alike 3.0 License

El documento se presenta como una guía rápida de referencia para principiantes en la programación de Arduino.

```json
{
  "type": "image",
  "id": "image-01",
  "page": 1,
  "title": "Placa Arduino Diecimila",
  "caption": "Guía rápida de referencia",
  "description": "Fotografía de la placa Arduino Diecimila mostrando sus componentes principales: puerto USB, conector de alimentación, microcontrolador ATmega168, pines de E/S digitales y analógicos, botón de reset y componentes electrónicos superficiales.",
  "elements": [
    "Puerto USB",
    "Conector de alimentación",
    "Microcontrolador ATmega168",
    "Pines digitales (0-13)",
    "Pines analógicos (0-5)",
    "Botón de reset",
    "LEDs indicadores (TX, RX, PWR, L)"
  ],
  "source": "Manual de Programación Arduino, Página 1"
}
```

---

## Estructura Básica del Lenguaje

La estructura básica del lenguaje de programación de Arduino se compone de al menos dos partes fundamentales: `setup()` y `loop()`.

```c
void setup() {
  estamentos;
}

void loop() {
  estamentos;
}
```

*   **`setup()`**: Se ejecuta una sola vez al inicio del programa. Se utiliza para configurar los modos de trabajo de los pines (`pinMode`), inicializar la comunicación serie, etc. Es obligatorio incluirla aunque no tenga código.
*   **`loop()`**: Contiene el programa que se ejecutará cíclicamente (bucle). Es el núcleo del programa y realiza la mayor parte del trabajo.

### Funciones

Una función es un bloque de código con un nombre y un conjunto de estamentos que se ejecutan cuando se llama a la función. Pueden devolver un valor (definido por su tipo, como `int`) o no devolver nada (`void`).

```c
type nombreFuncion(parámetros) {
  estamentos;
}
```

**Ejemplo:**
```c
int delayVal() {
  int v; // crea una variable temporal 'v'
  v = analogRead(pot); // lee el valor del potenciómetro
  v /= 4; // convierte 0-1023 a 0-255
  return v; // devuelve el valor final
}
```

### Uso de Llaves `{}`

Las llaves definen el principio y el final de un bloque de instrucciones (como en `setup()`, `loop()`, `if`, etc.). Una llave de apertura `{` siempre debe ir seguida de una llave de cierre `}`.

### Punto y Coma `;`

Se utiliza para separar instrucciones. Olvidar un punto y coma al final de una línea provocará un error de compilación.

### Comentarios

*   **Bloque de comentarios:** `/* ... */` (pueden abarcar varias líneas).
*   **Línea de comentario:** `// ...` (termina al final de la línea).

---

## Variables y Tipos de Datos

Una variable es una manera de nombrar y almacenar un valor numérico para su uso posterior. Deben declararse antes de ser utilizadas e idealmente tener nombres descriptivos.

### Declaración y Ámbito (Scope)

*   **Variables globales:** Se declaran al inicio del programa, antes de `setup()`. Son visibles para todas las funciones.
*   **Variables locales:** Se definen dentro de una función o bloque (como un bucle `for`). Solo son visibles dentro de ese ámbito.

```c
int value; // 'value' es visible para cualquier función

void setup() { }

void loop() {
  for (int i=0; i<20;) { // 'i' solo es visible dentro del bucle for
    i++;
  }
  float f; // 'f' es visible solo dentro del bucle
}
```

### Tipos de Datos

| Tipo | Tamaño | Rango | Descripción |
|---|---|---|---|
| `byte` | 8 bits | 0 a 255 | Almacena valores numéricos sin decimales. |
| `int` | 16 bits | -32,768 a 32,767 | Enteros. Pueden desbordarse si se supera el rango. |
| `long` | 32 bits | -2,147,483,648 a 2,147,483,647 | Enteros extendidos. |
| `float` | 32 bits | 3.4028235E+38 a -3.4028235E+38 | Números con decimales. Cálculos más lentos y con posibles imprecisiones. |

### Arrays

Un array es un conjunto de valores a los que se accede con un número índice (empezando en 0).

```c
int miArray[] = {valor0, valor1, valor2...};
int miArray[5]; // declara un array de enteros de 5 posiciones (0 a 4)
miArray[3] = 10; // asigna el valor 10 a la posición 4
x = miArray[3]; // x ahora es igual a 10
```

**Ejemplo de uso de array para parpadeo de LED:**
```c
int ledPin = 10;
byte parpadeo[] = {180, 30, 255, 200, 10, 90, 150, 60};

void setup() {
  pinMode(ledPin, OUTPUT);
}

void loop() {
  for(int i=0; i<8; i++) {
    analogWrite(ledPin, parpadeo[i]);
    delay(200);
  }
}
```

---

## Aritmética y Operadores

### Aritmética Básica
`y = y + 3; x = x - 7; i = j * 6; r = r / 5;`
Si los operandos son de diferentes tipos, se utiliza el tipo más grande. Cuidado con el desbordamiento y la precisión de los `float`.

### Asignaciones Compuestas
```c
x ++ // igual que x = x + 1
x -- // igual que x = x - 1
x += y // igual que x = x + y
x -= y // igual que x = x - y
x *= y // igual que x = x * y
x /= y // igual que x = x / y
```

### Operadores de Comparación
```c
x == y // x es igual a y
x != y // x no es igual a y
x < y  // x es menor que y
x > y  // x es mayor que y
x <= y // x es menor o igual que y
x >= y // x es mayor o igual que y
```

### Operadores Lógicos
```c
if (x > 0 && x < 5) // AND (cierto solo si ambas expresiones son ciertas)
if (x > 0 || y > 0) // OR (cierto si una cualquiera de las expresiones es cierta)
if (!x > 0)         // NOT (cierto solo si la expresión es falsa)
```

### Constantes
*   **`TRUE` / `FALSE`**: `FALSE` se asocia con 0, `TRUE` con 1 (o cualquier valor distinto de cero).
*   **`HIGH` / `LOW`**: Niveles de salida. `HIGH` = 5V (o 3.3V), `LOW` = 0V.
*   **`INPUT` / `OUTPUT`**: Modos de trabajo de los pines.

---

## Control de Flujo

### `if` / `if... else`
```c
if (inputPin == HIGH) {
  instruccionesA;
} else {
  instruccionesB;
}

// Anidamiento
if (inputPin < 500) {
  instruccionesA;
} else if (inputPin >= 1000) {
  instruccionesB;
} else {
  instruccionesC;
}
```
*Nota:* Usar `==` para comparar, no `=` (que asigna).

### `for`
```c
for (inicialización; condición; expresión) {
  ejecutaInstrucciones;
}
```
Ejemplo:
```c
for (int i=0; i<20; i++) {
  digitalWrite(13, HIGH);
  delay(250);
  digitalWrite(13, LOW);
  delay(250);
}
```

### `while`
```c
while (unaVariable < 200) {
  instrucciones;
  unaVariable++;
}
```

### `do... while`
Se ejecuta al menos una vez, ya que la condición se prueba al final.
```c
do {
  Instructions;
} while (unaVariable < 100);
```

---

## Entradas y Salidas (E/S)

### E/S Digitales

*   **`pinMode(pin, mode)`**: Configura un pin como `INPUT` o `OUTPUT`. Por defecto son entradas.
    *   Para activar resistencias de pull-up internas (20 kΩ): `pinMode(pin, INPUT); digitalWrite(pin, HIGH);`
*   **`digitalRead(pin)`**: Lee el valor de un pin digital (`HIGH` o `LOW`).
*   **`digitalWrite(pin, value)`**: Escribe `HIGH` o `LOW` en un pin configurado como salida. Proporciona hasta 40 mA.

**Ejemplo:**
```c
int led = 13;
int boton = 7;
int valor = 0;

void setup() {
  pinMode(led, OUTPUT);
  pinMode(boton, INPUT);
}

void loop() {
  valor = digitalRead(boton);
  digitalWrite(led, valor);
}
```

### E/S Analógicas

*   **`analogRead(pin)`**: Lee un pin de entrada analógica (0-5) con una resolución de 10 bits (0 a 1023). No necesitan ser declarados como `INPUT`.
*   **`analogWrite(pin, value)`**: Escribe un valor PWM (0 a 255) en pines marcados como PWM (3, 5, 6, 9, 10, 11 en ATmega168). Genera una onda cuadrada de frecuencia constante.
    *   0 = 0V, 255 = 5V, 128 = 50% del tiempo en 5V.

**Ejemplo:**
```c
int led = 10;
int analog = 0;
int valor;

void setup() { }

void loop() {
  valor = analogRead(analog);
  valor /= 4;
  analogWrite(led, valor);
}
```

---

## Tiempo y Matemáticas

*   **`delay(ms)`**: Detiene la ejecución del programa durante los milisegundos indicados (1000 = 1 segundo).
*   **`millis()`**: Devuelve el número de milisegundos transcurridos desde el inicio del programa. Se desborda a las ~9 horas.
*   **`min(x, y)`**: Devuelve el menor de dos números.
*   **`max(x, y)`**: Devuelve el mayor de dos números.
*   **`randomSeed(seed)`**: Establece una semilla para la generación de números aleatorios.
*   **`random(min, max)`**: Devuelve un número aleatorio entero entre `min` y `max-1`.

---

## Puerto Serie

*   **`Serial.begin(rate)`**: Abre el puerto serie y fija la velocidad en baudios (típicamente 9600). Los pines 0 (RX) y 1 (TX) no pueden usarse simultáneamente.
*   **`Serial.println(data)`**: Imprime datos en el puerto serie seguido de un retorno de carro y salto de línea.
*   **`Serial.print(data, data type)`**: Imprime datos en el puerto serie. Formatos: `DEC`, `HEX`, `OCT`, `BIN`, `BYTE`.
*   **`Serial.available()`**: Devuelve el número de bytes disponibles para leer.
*   **`Serial.read()`**: Lee un byte del puerto serie.

**Ejemplo de lectura y escritura:**
```c
int incomingByte = 0;
void setup() {
  Serial.begin(9600);
}
void loop() {
  if (Serial.available() > 0) {
    incomingByte = Serial.read();
    Serial.print("I received: ");
    Serial.println(incomingByte, DEC);
  }
}
```

---

## Apéndices: Formas de Conexionado de Entradas y Salidas

### Salida Digital (LED)

```json
{
  "type": "diagram",
  "id": "diagram-01",
  "page": 29,
  "title": "Conexión de un diodo Led a una salida de Arduino",
  "elements": [
    "Pin 13 (Arduino)",
    "Resistencia 220R",
    "LED",
    "Tierra (GND)"
  ],
  "relationships": [
    "Pin 13 -> Resistencia 220R -> Ánodo LED -> Cátodo LED -> Tierra"
  ],
  "description": "Circuito básico para encender y apagar un LED conectado al pin 13 de Arduino. Se incluye una resistencia limitadora de corriente de 220 ohmios."
}
```

**Código:**
```c
int ledPin = 13;
void setup() {
  pinMode(ledPin, OUTPUT);
}
void loop() {
  digitalWrite(ledPin, HIGH);
  delay(1000);
  digitalWrite(ledPin, LOW);
  delay(1000);
}
```

### Salida Analógica (PWM)

```json
{
  "type": "diagram",
  "id": "diagram-02",
  "page": 32,
  "title": "Conexión de una salida analógica a un LED",
  "elements": [
    "Pin PWM (Arduino)",
    "Resistencia 220R",
    "LED",
    "Tierra (GND)"
  ],
  "relationships": [
    "Pin PWM -> Resistencia 220R -> Ánodo LED -> Cátodo LED -> Tierra"
  ],
  "description": "Circuito para controlar el brillo de un LED mediante PWM. Se utiliza un pin compatible con PWM."
}
```

**Código:**
```c
int ledPin = 9;
void setup() { }
void loop() {
  for (int i=0; i<=255; i++) {
    analogWrite(ledPin, i);
    delay(100);
  }
  for (int i=255; i>=0; i--) {
    analogWrite(ledPin, i);
    delay(100);
  }
}
```

### Entrada Analógica (Potenciómetro)

```json
{
  "type": "diagram",
  "id": "diagram-03",
  "page": 33,
  "title": "Entrada analógica mediante un potenciómetro",
  "elements": [
    "Pin analógico (Arduino)",
    "Potenciómetro 10k",
    "+5V",
    "Tierra (GND)"
  ],
  "relationships": [
    "Terminal 1 Potenciómetro -> +5V",
    "Terminal 2 (cursor) Potenciómetro -> Pin analógico",
    "Terminal 3 Potenciómetro -> Tierra"
  ],
  "description": "Circuito para leer un valor analógico variable mediante un potenciómetro. El valor leído se utiliza para controlar el tiempo de parpadeo de un LED."
}
```

**Código:**
```c
int potPin = 0;
int ledPin = 13;
void setup() {
  pinMode(ledPin, OUTPUT);
}
void loop() {
  digitalWrite(ledPin, HIGH);
  delay(analogRead(potPin));
  digitalWrite(ledPin, LOW);
  delay(analogRead(potPin));
}
```

### Entrada con Resistencia Variable

```json
{
  "type": "diagram",
  "id": "diagram-04",
  "page": 34,
  "title": "Conexión de un sensor de tipo resistivo (LDR, NTC, PTC)",
  "elements": [
    "Pin analógico (Arduino)",
    "Sensor resistivo",
    "Resistencia fija (divisor de tensión)",
    "+5V",
    "Tierra (GND)"
  ],
  "relationships": [
    "Sensor resistivo -> +5V y Pin analógico",
    "Resistencia fija -> Pin analógico y Tierra"
  ],
  "description": "Configuración de un divisor de tensión para leer sensores resistivos variables."
}
```

### Salida a Servomotor

```json
{
  "type": "diagram",
  "id": "diagram-05",
  "page": 35,
  "title": "Conexión de un servo a una salida analógica",
  "elements": [
    "Pin digital (Arduino)",
    "Resistencia 220R",
    "Servomotor",
    "+6V",
    "Tierra (GND)"
  ],
  "relationships": [
    "Pin digital -> Resistencia 220R -> Señal Servo",
    "Servo Vcc -> +6V",
    "Servo GND -> Tierra"
  ],
  "description": "Circuito para controlar un servomotor estándar de 180 grados. La señal de control se envía desde un pin digital."
}
```

**Código:**
```c
int servoPin = 2;
int myAngle;
int pulseWidth;

void setup() {
  pinMode(servoPin, OUTPUT);
}

void servoPulse(int servoPin, int myAngle) {
  pulseWidth = (myAngle * 10) + 600;
  digitalWrite(servoPin, HIGH);
  delayMicroseconds(pulseWidth);
  digitalWrite(servoPin, LOW);
  delay(20);
}

void loop() {
  for (myAngle=10; myAngle<=170; myAngle++) {
    servoPulse(servoPin, myAngle);
  }
  for (myAngle=170; myAngle>=10; myAngle--) {
    servoPulse(servoPin, myAngle);
  }
}
```

### Conexión de Cargas de Alto Consumo (MOSFET)

```json
{
  "type": "diagram",
  "id": "diagram-06",
  "page": 67,
  "title": "Conexión de una carga inductiva de alto consumo mediante un MOSFET",
  "elements": [
    "Pin digital (Arduino)",
    "MOSFET IRF510",
    "Diodo 1N4001",
    "Motor DC (M)",
    "+5-24V",
    "Tierra (GND)"
  ],
  "relationships": [
    "Pin digital -> Gate MOSFET",
    "Source MOSFET -> Tierra",
    "Drain MOSFET -> Motor DC y Cátodo Diodo",
    "Motor DC -> +5-24V y Ánodo Diodo",
    "Diodo en paralelo con el motor (protección de picos inductivos)"
  ],
  "description": "Circuito de conmutación para controlar cargas inductivas de alto consumo (motores, relés, solenoides) utilizando un transistor MOSFET y un diodo de protección."
}
```

### Conexión de un Pulsador/Interruptor

```json
{
  "type": "diagram",
  "id": "diagram-07",
  "page": 67,
  "title": "Conexión de un pulsador/interruptor",
  "elements": [
    "Pin digital (Arduino)",
    "Pulsador/Interruptor",
    "Resistencia 10kR (Pull-down)",
    "+5V",
    "Tierra (GND)"
  ],
  "relationships": [
    "Pulsador -> +5V y Pin digital",
    "Resistencia 10kR -> Pin digital y Tierra"
  ],
  "description": "Circuito de entrada digital básico con resistencia de pull-down para evitar estados flotantes cuando el pulsador está abierto."
}
```

### Control de Motor DC con Puente H (L293)

```json
{
  "type": "diagram",
  "id": "diagram-08",
  "page": 69,
  "title": "Control de un motor de cc mediante el CI L293",
  "elements": [
    "Arduino",
    "L293_H-BRIDGE",
    "Motor DC",
    "Resistencia 10k",
    "Capacitor 10uF",
    "Fuente de alimentación (+5V, +12V)"
  ],
  "relationships": [
    "Pines de control Arduino -> Pines de entrada L293",
    "Pines de salida L293 -> Motor DC",
    "L293 Vcc1 -> +5V",
    "L293 Vcc2 -> Fuente de motor (hasta 36V)"
  ],
  "description": "Circuito integrado L293 para controlar la dirección y velocidad de un motor DC mediante señales PWM y digitales de Arduino."
}
```

### Control de Motor Paso a Paso (ULN2003)

```json
{
  "type": "diagram",
  "id": "diagram-09",
  "page": 70,
  "title": "Control de un motor paso a paso unipolar",
  "elements": [
    "Salidas Digitales Arduino (E1, E2, E3, E4)",
    "ULN2003A (Darlington Array)",
    "Motor paso a paso unipolar",
    "+Vcc",
    "Tierra (GND)"
  ],
  "relationships": [
    "Salidas Arduino -> Entradas ULN2003A",
    "Salidas ULN2003A -> Bobinas del motor paso a paso",
    "Motor -> +Vcc"
  ],
  "description": "Circuito de control para un motor paso a paso unipolar utilizando un arreglo de transistores Darlington ULN2003A como etapa de potencia."
}
```

### Control mediante Transistor TIP120

```json
{
  "type": "diagram",
  "id": "diagram-10",
  "page": 70,
  "title": "Control mediante transistor TIP120",
  "elements": [
    "Salida digital Arduino",
    "Resistencia 1K",
    "Transistor TIP120",
    "Diodo 1N4004",
    "Carga (Motor DC o Lámpara)",
    "Vcc (+5V)"
  ],
  "relationships": [
    "Salida Arduino -> Resistencia 1K -> Base TIP120",
    "Emisor TIP120 -> Tierra",
    "Colector TIP120 -> Carga y Ánodo Diodo",
    "Carga -> Vcc y Cátodo Diodo"
  ],
  "description": "Circuito de conmutación para cargas inductivas y resistivas utilizando un transistor Darlington TIP120, incluyendo diodo de protección."
}
```

---

## Creación de una Librería para Arduino

El documento explica cómo convertir un programa sencillo (como un código Morse) en una librería reutilizable.

**Estructura de la librería:**
1.  **Archivo de cabecera (`.h`)**: Contiene definiciones, la declaración de la clase y las variables.
2.  **Archivo fuente (`.cpp`)**: Contiene la implementación del código.

### Archivo Morse.h
```cpp
/* Morse.h - Library for flashing Morse code.
   Created by David A. Mellis, November 2, 2007.
   Released into the public domain. */
#ifndef Morse_h
#define Morse_h
#include "WConstants.h"

class Morse {
  public:
    Morse(int pin);
    void dot();
    void dash();
  private:
    int _pin;
};
#endif
```

### Archivo Morse.cpp
```cpp
/* Morse.cpp - Library for flashing Morse code. */
#include "WProgram.h"
#include "Morse.h"

Morse::Morse(int pin) {
  pinMode(pin, OUTPUT);
  _pin = pin;
}

void Morse::dot() {
  digitalWrite(_pin, HIGH);
  delay(250);
  digitalWrite(_pin, LOW);
  delay(250);
}

void Morse::dash() {
  digitalWrite(_pin, HIGH);
  delay(1000);
  digitalWrite(_pin, LOW);
  delay(250);
}
```

### Uso de la Librería
```cpp
#include <Morse.h>

Morse morse(13);

void setup() { }

void loop() {
  morse.dot(); morse.dot(); morse.dot();
  morse.dash(); morse.dash(); morse.dash();
  morse.dot(); morse.dot(); morse.dot();
  delay(3000);
}
```

### Archivo keywords.txt
```text
Morse	KEYWORD1
dash	KEYWORD2
dot	KEYWORD2
```

---

## Señales Analógicas de Salida (PWM)

La Modulación por Ancho de Pulso (PWM) es una técnica para generar una "falsa" salida analógica variando el tiempo que la señal está en alto (ON) o en bajo (OFF).

```json
{
  "type": "chart",
  "id": "chart-01",
  "page": 44,
  "title": "Señales PWM con diferentes Duty Cycles",
  "chart_type": "line",
  "axes": {
    "x": "Tiempo",
    "y": "Voltaje (V)"
  },
  "series": [
    {
      "name": "0% Duty Cycle - analogWrite(0)",
      "values": ["0V constante"]
    },
    {
      "name": "25% Duty Cycle - analogWrite(64)",
      "values": ["5V por 25% del periodo, 0V por 75%"]
    },
    {
      "name": "50% Duty Cycle - analogWrite(127)",
      "values": ["5V por 50% del periodo, 0V por 50%"]
    },
    {
      "name": "75% Duty Cycle - analogWrite(191)",
      "values": ["5V por 75% del periodo, 0V por 25%"]
    },
    {
      "name": "100% Duty Cycle - analogWrite(255)",
      "values": ["5V constante"]
    }
  ],
  "description": "Representación gráfica de cinco señales PWM con diferentes ciclos de trabajo. El eje Y muestra el voltaje (0V a 5V) y el eje X el tiempo. Se observa cómo varía el ancho del pulso activo."
}
```

**Fórmula del Duty Cycle:**
`Duty Cycle = (PW / Periodo) * 100`

### Cálculo de Tonos

```json
{
  "type": "table",
  "id": "table-01",
  "page": 46,
  "title": "Tabla de frecuencias y anchos de pulso para notas musicales",
  "headers": ["Nota musical", "Frecuencia-tono (Hz)", "Periodo (us)", "PW (us)"],
  "rows": [
    ["c", "261", "3830", "1915"],
    ["d", "294", "3400", "1700"],
    ["e", "329", "3038", "1519"],
    ["f", "349", "2864", "1432"],
    ["g", "392", "2550", "1275"],
    ["a", "440", "2272", "1136"],
    ["b", "493", "2028", "1014"],
    ["C", "523", "1912", "956"]
  ],
  "notes": "PW = 1 / (2 * Frecuencia). Asumiendo un Duty Cycle del 50%.",
  "source": "Manual de Programación Arduino, Página 46"
}
```

**Ejemplo 1: Generación de tono con delayMicroseconds**
```c
int digPin = 10;
int PW = 1915;
void setup() {
  pinMode(digPin, OUTPUT);
}
void loop() {
  delayMicroseconds(PW);
  digitalWrite(digPin, LOW);
  delayMicroseconds(PW);
  digitalWrite(digPin, HIGH);
}
```

**Ejemplo 2: Generación de tono con analogWrite (PWM)**
```c
int speakerOut = 9;
int volume = 300;
int PW = 1915;
void loop() {
  analogWrite(speakerOut, 0);
  analogWrite(speakerOut, volume);
  delayMicroseconds(PW);
  analogWrite(speakerOut, 0);
  delayMicroseconds(PW);
}
```

---

## Comunicación con Otros Sistemas

### Comunicación Serie (PC <-> Arduino)

```json
{
  "type": "image",
  "id": "image-02",
  "page": 52,
  "title": "Monitor Serie de Arduino",
  "caption": "Interfaz del Monitor Serie en el IDE de Arduino",
  "description": "Captura de pantalla del Monitor Serie del IDE de Arduino. Se señalan los controles de selección de velocidad (9600 baud), entrada de datos, botón de envío y área de visualización de datos.",
  "elements": [
    "Menú de selección de velocidad",
    "Campo de entrada de datos",
    "Botón 'Send'",
    "Área de visualización de datos"
  ],
  "source": "Manual de Programación Arduino, Página 52"
}
```

```json
{
  "type": "image",
  "id": "image-03",
  "page": 56,
  "title": "Software Terminal para comunicaciones serie",
  "caption": "Software Terminal 1.9b",
  "description": "Captura de pantalla de un software de terminal serie (Terminal 1.9b) mostrando la configuración de puerto COM, velocidad en baudios, bits de datos, paridad y bits de parada.",
  "elements": [
    "Configuración de puerto (COM Port)",
    "Velocidad en baudios (Baud rate)",
    "Bits de datos (Data bits)",
    "Paridad (Parity)",
    "Bits de parada (Stop bits)"
  ],
  "source": "Manual de Programación Arduino, Página 56"
}
```

### Conversor Analógico-Digital (A/D)

```json
{
  "type": "image",
  "id": "image-04",
  "page": 61,
  "title": "Conversor Analógico-Digital",
  "caption": "Diagrama de bloques de un conversor A/D",
  "description": "Ilustración que muestra una señal analógica de entrada (onda senoidal) siendo convertida en una señal digital de salida (tren de pulsos binarios 01100010110).",
  "elements": [
    "Entrada analógica (analog in)",
    "Bloque conversor A/D",
    "Salida digital (digital out)"
  ],
  "source": "Manual de Programación Arduino, Página 61"
}
```

**Fórmula de Resolución:**
`Resolución = Vref / 2^n`
Para Arduino (10 bits, Vref=5V): `Resolución = 5V / 1024 ≈ 4.88 mV`

### Comunicación Serie Asíncrona

```json
{
  "type": "image",
  "id": "image-05",
  "page": 63,
  "title": "Transmisión de un byte por puerto serie",
  "caption": "Secuencia de pulsos para transmitir el número 90 (01011010)",
  "description": "Gráfico de voltaje en el tiempo que muestra los bits de inicio (Start), los 8 bits de datos (0, 1, 0, 1, 1, 0, 1, 0) y el bit de parada (Stop) para la transmisión serie asíncrona.",
  "elements": [
    "Bit de inicio (Start)",
    "Bits de datos (0-7)",
    "Bit de parada (Stop)",
    "Niveles de voltaje (5V y 0V)"
  ],
  "source": "Manual de Programación Arduino, Página 63"
}
```

```json
{
  "type": "image",
  "id": "image-06",
  "page": 64,
  "title": "Puerto serie RS-232 DB-9",
  "caption": "Gráfico de Puerto serie RS-232 en PC (versión de 9 pines DB-9)",
  "description": "Diagrama de un conector DB-9 hembra, mostrando la numeración de los pines y las funciones de los pines 2 (RX), 3 (TX) y 5 (GND).",
  "elements": [
    "Conector DB-9",
    "Pin 2: Microcontroller receive (PC transmit)",
    "Pin 3: Microcontroller transmit (PC receive)",
    "Pin 5: Ground"
  ],
  "source": "Manual de Programación Arduino, Página 64"
}
```

### Ejemplo de Comunicación con Processing

**Arduino:**
```c
int potPin = 2;
int ledPin = 13;
int val = 0;

void setup() {
  Serial.begin(9600);
  pinMode(ledPin, OUTPUT);
  digitalWrite(ledPin, HIGH);
}

void loop() {
  val = analogRead(potPin)/4;
  Serial.print(val, BYTE);
}
```

**Processing:**
```java
import processing.serial.*;

Serial puerto;
byte pot;
int PosX;

void setup() {
  size(400, 256);
  println(Serial.list());
  puerto = new Serial(this, Serial.list()[0], 9600);
  fill(255,255,0);
  PosX = 0;
  pot = 0;
}

void draw() {
  if (puerto.available() > 0) {
    pot = puerto.read();
    println(pot);
  }
  ellipse(PosX, pot, 3, 3);
  if (PosX < width) {
    PosX++;
  } else {
    fill(int(random(255)),int(random(255)),int(random(255)));
    PosX = 0;
  }
}
```

---

## Palabras Reservadas del IDE de Arduino

El documento incluye una lista de palabras reservadas que no deben usarse como nombres de variables.

*   **Constantes:** `HIGH`, `LOW`, `INPUT`, `OUTPUT`, `true`, `false`, `PI`, `HALF_PI`, `LSBFIRST`, `MSBFIRST`, `SERIAL`, `DISPLAY`
*   **Variables y tipos:** `boolean`, `byte`, `char`, `int`, `long`, `float`, `double`, `void`, `word`, `string`
*   **Funciones:** `setup`, `loop`, `pinMode`, `digitalRead`, `digitalWrite`, `analogRead`, `analogWrite`, `delay`, `millis`, `delayMicroseconds`, `min`, `max`, `random`, `randomSeed`, `Serial.begin`, `Serial.print`, `Serial.println`, `Serial.available`, `Serial.read`, `beginSerial`, `serialWrite`, `serialRead`, `printString`, `printInteger`, `printByte`, `printHex`, `printOctal`, `printBinary`, `printNewline`, `pulseIn`, `shiftOut`
*   **Estructuras de control:** `if`, `else`, `for`, `while`, `do`, `switch`, `case`, `break`, `continue`, `return`, `goto`
*   **Operadores:** `=`, `+`, `-`, `*`, `/`, `%`, `==`, `!=`, `<`, `>`, `<=`, `>=`, `&&`, `||`, `!`, `&`, `|`, `^`, `~`, `<<`, `>>`, `++`, `--`, `+=`, `-=`, `*=`, `/=`, `&=`, `|=`
*   **Registros:** `DDRB`, `PINB`, `PORTB`, `DDRC`, `PINC`, `PORTC`, `DDRD`, `PIND`, `PORTD`

---

## Referencias

*   Arduino Notebook: A Beginner's Reference. Written and compiled by Brian W. Evans.
*   Información e inspiración tomada de: http://www.arduino.cc, http://www.wiring.org.co, http://www.arduino.cc/en/Booklet/HomePage, http://cslibrary.stanford.edu/101/
*   Material escrito por: Massimo Banzi, Hernando Barragin, David Cuartelles, Tom Igoe, Todd Kurt, David Mellis y otros.
*   Publicado: First Edition August 2007.
*   Licencia: Creative Commons Attribution-Noncommercial-Share Alike 3.0 License. http://creativecommons.org/licenses/by-nc-sa/3.0/
