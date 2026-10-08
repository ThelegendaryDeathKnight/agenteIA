# El gran libro por ESP32forth — Versión 1.17

**Autor:** Marc PETREMANN (petremann@arduino-forth.com)
**Colaboradores:** Vaclav POSSELT, Bob EDWARDS
**Fecha:** 25 de enero de 2024
**Idioma original:** Francés / Español (traducción)
**Páginas totales:** 324
**Distribución:** Gratuita desde repositorio GitHub

---

## Resumen técnico

Este documento constituye un manual completo y práctico sobre **ESP32forth**, una implementación del lenguaje FORTH para la placa ESP32 de Espressif. A lo largo de sus 324 páginas, el autor —con más de 40 años de experiencia en FORTH— presenta desde los fundamentos del lenguaje hasta aplicaciones avanzadas de hardware, comunicación inalámbrica y programación a bajo nivel.

El libro cubre la instalación de ESP32forth mediante Arduino IDE, la configuración de la placa ESP32 en sus variantes WROOM, WROVER y S3, y la solución de problemas típicos de carga. Se exploran las particularidades del lenguaje FORTH: su pila de datos de 32 bits, el diccionario de palabras, la notación polaca inversa (RPN), la creación de nuevas palabras mediante `:` y `;`, y el uso de `CREATE`/`DOES>` para meta-programación.

Se detallan aplicaciones prácticas: gestión de GPIO mediante registros directos (`GPIO_OUT_REG`, `GPIO_ENABLE_REG`), interrupciones hardware y software, temporizadores, codificadores rotatorios, pantallas OLED SSD1306 por I2C, SPI con MAX7219, síntesis de sonido, comunicaciones LoRa con módulos REYAX RYLR890, cliente HTTP, sistema de archivos SPIFFS, gestión de bloques, y una interfaz web embebida.

El documento incluye numerosos ejemplos de código FORTH, tablas de registros ESP32, diagramas de conexión, y una referencia completa de los vocabularios de ESP32forth (FORTH, asm, bluetooth, editor, ESP, httpd, insides, internals, interrupts, ledc, oled, registers, riscv, rmt, rtos, SD, SD_MMC, Serial, sockets, spi, SPIFFS, streams, structures, tasks, telnetd, timers, visual, web-interface, WiFi, Wire, xtensa).

La filosofía central es que FORTH es un **metalenguaje**: permite crear palabras de definición personalizadas, extender el diccionario y acceder al hardware de forma directa e interactiva, sin necesidad de recompilar y cargar código desde una PC.

---

## Índice de contenidos

| Sección | Páginas |
|---|---|
| Introducción | 11 |
| Descubrimiento de la tarjeta ESP32 | 12–16 |
| Instalación de ESP32forth | 17–27 |
| ¿Por qué programar en FORTH? | 28–33 |
| Usando números con ESP32Forth | 35–42 |
| Un verdadero FORTH de 32 bits | 43–46 |
| Comentarios y aclaraciones | 47–54 |
| Diccionario / Pila / Variables / Constantes | 55–60 |
| Colores de texto y posición en terminal | 61–64 |
| Variables locales | 65–68 |
| Estructuras de datos | 69–78 |
| Instalación OLED SSD1306 | 79–81 |
| Números reales | 82–85 |
| Mostrar números y cadenas | 86–94 |
| Vocabularios | 95–98 |
| Palabras de acción retrasada (defer) | 99–104 |
| Palabras de creación de palabras | 105–108 |
| Adaptar placas de pruebas | 109–110 |
| Alimentación de la placa ESP32 | 111–112 |
| Inicio automático | 113–114 |
| Terminal Tera Term | 115–120 |
| Acceso TELNET | 121–124 |
| Gestión de archivos por bloques | 125–129 |
| Editor VISUAL | 130–131 |
| RECORDFILE y proyectos | 132–139 |
| Sistema de archivos SPIFFS | 140–144 |
| Edición y gestión de archivos | 145–150 |
| Semáforo con ESP32 | 151–154 |
| Acceso directo a registros GPIO | 155–162 |
| Interrupciones hardware | 163–166 |
| Codificador rotatorio KY-040 | 167–173 |
| Parpadeo LED por temporizador | 174–178 |
| Temporizador ama de llaves | 179–183 |
| Reloj en tiempo real | 184–185 |
| Medir tiempo de ejecución | 186–187 |
| Analizador de luz solar | 189–197 |
| Salidas N/A | 198–200 |
| Pantalla OLED SSD1306 | 201–219 |
| TEMPVS FVGIT | 220–223 |
| Biblioteca SPI | 224–228 |
| Cliente HTTP | 229–232 |
| Recuperar hora desde servidor WEB | 233–235 |
| Transmisión GET a servidor | 236–243 |
| Síntesis de sonido | 245–251 |
| Ensamblador XTENSA | 252–268 |
| Definición y manipulación de registros | 269–274 |
| Generador de números aleatorios | 275–277 |
| Sistema de transmisión LoRa | 278–280 |
| REYAX RYLR890 LoRa | 281–299 |
| Comunicación entre transmisores LoRa | 300–307 |
| Interfaz WEB sencilla | 308–312 |
| Vocabularios ESP32forth | 313–320 |
| Anexo A – Registros | 321–322 |
| Recursos | 323 |

---

## Introducción

Desde 2019 el autor ha gestionado varios sitios web dedicados al desarrollo de FORTH para placas ARDUINO y ESP32, así como la versión web eForth:

- **ARDUINO:** https://arduino-forth.com/
- **ESP32:** https://esp32.arduino-forth.com/
- **eForth web:** https://eforth.arduino-forth.com/

Estos sitios están disponibles en francés e inglés. El libro es la recopilación del contenido de estos sitios web, distribuido gratuitamente desde un repositorio GitHub para garantizar su sostenibilidad.

**Ayuda de traducción:** Google Translate permite traducir textos fácilmente pero con errores. Se solicita ayuda para corregir traducciones. Los capítulos ya traducidos están en formato LibreOffice. Contacto: petremann@arduino-forth.com

---

## Descubrimiento de la tarjeta ESP32

### Presentación

La placa ESP32 **no es una placa ARDUINO**, aunque las herramientas de desarrollo aprovechan ciertos elementos del ecosistema ARDUINO (como Arduino IDE).

### Puntos fuertes

El modelo básico tiene **38 conectores**. Los dispositivos ESP32 incluyen:

- 18 canales de convertidor analógico a digital (ADC)
- 3 interfaces SPI
- 3 interfaces UART
- 2 interfaces I2C
- 16 canales de salida PWM
- 2 convertidores de digital a analógico (DAC)
- 2 interfaces I2S
- 10 GPIO de detección capacitiva

La funcionalidad ADC y DAC está asignada a pines estáticos específicos. Sin embargo, se puede decidir qué pines son UART, I2C, SPI, PWM, etc. gracias a la función de multiplexación del chip ESP32.

Lo que distingue a la placa ESP32 es que está equipada de serie con soporte **WiFi y Bluetooth**, algo que las placas ARDUINO solo ofrecen como extensiones.

### Entradas/salidas GPIO en ESP32

```json
{
  "type": "image",
  "id": "image-01",
  "page": 13,
  "title": "Tarjeta ESP32 vista superior",
  "caption": "Cada conector está identificado por una serie de letras y números",
  "description": "Placa ESP32-WROOM-32 con chips visibles, puerto micro USB, botones RST y BOOT. Fila inferior de pines: CLK, SD0, SD1, G15, G2, G0, G4, G16...G22, G23, GND.",
  "elements": [
    "ESP32-WROOM-32",
    "USB-UART Bridge",
    "Boot", "EN", "5V Power On LED",
    "Micro USB Port"
  ],
  "source": "Foto del autor"
}
```

**Pines especiales:**

| GPIO | Posibles nombres |
|---|---|
| 6 | SCK/CLK |
| 7 | SCK/CLK |
| 8 | SDO/SD0 |
| 9 | SDI/SD1 |
| 10 | SHD/SD2 |
| 11 | CSC/CMD |

> **Advertencia:** Si tu tarjeta ESP32 tiene E/S GPIO6, GPIO7, GPIO8, GPIO9, GPIO10, GPIO11, definitivamente **no debes usarlas** porque están conectadas a la memoria flash del ESP32. Si los usas, el ESP32 no funcionará.

> Las E/S GPIO1(TX0) y GPIO3(RX0) se utilizan para comunicarse con la computadora en UART a través del puerto USB. Si las utilizas, ya no podrás comunicarte con la tarjeta.

> GPIO36(VP), GPIO39(VN), GPIO34, GPIO35 son I/O que se pueden utilizar **solo como entrada**. Tampoco tienen resistencias pullup y pulldown internas incorporadas.

### Periféricos ESP32

ESP32 tiene los siguientes periféricos:

- 3 interfaces UART
- 2 interfaces I2C
- 3 interfaces SPI
- 16 salidas PWM
- 10 sensores capacitivos
- 18 entradas analógicas (ADC)
- 2 salidas DAC

ESP32 ya utiliza algunos periféricos durante su funcionamiento básico, por lo que hay menos interfaces posibles para cada dispositivo.

### Las diferentes tarjetas ESP32

```json
{
  "type": "image",
  "id": "image-02",
  "page": 16,
  "title": "Variedad de tarjetas ESP32 en Amazon",
  "caption": "Un gran surtido de tarjetas ESP32",
  "description": "Mosaico de diferentes modelos de tarjetas ESP32: Mini, WROOM, WROVER, con display OLED integrado, etc.",
  "source": "Amazon"
}
```

Preguntas para orientar la elección:
- ¿Qué placa puede alojar ESP32forth?
- ¿Qué tarjetas se adaptan mejor a mis proyectos?
- ¿Cuál es mi presupuesto?

**Kit recomendado:** placas de prueba (al menos 10), conectores dupont, LED, resistencias, periféricos (pantalla OLED, LCD, relés, motores, servos), cable USB y concentrador USB. Por unos 50 €/USD hay kits listos para usar.

```json
{
  "type": "image",
  "id": "image-03",
  "page": 16,
  "title": "Kit ESP32",
  "caption": "Kit completo con tarjeta ESP32 y periféricos",
  "description": "Kit de desarrollo con placa ESP32, protoboard, LEDs, resistencias, pantalla LCD, servomotores, sensores, cables dupont, etc.",
  "source": "Amazon"
}
```

---

## Instalación de ESP32forth

### Descargar ESP32forth

El primer paso consiste en recuperar el código fuente en lenguaje C de ESP32forth. Preferiblemente usar la versión más reciente:
**https://esp32forth.appspot.com/ESP32forth.html**

Contenido del archivo descargado:
```
ESP32forth-7.0.x.x/
├── ESP32forth
├── readme.txt
├── esp32forth.ino
└── optional/
    ├── SPI-flash.h
    ├── serial-bluetooth.h
    └── ...
```

### Compilando e instalando ESP32forth

1. Tener Arduino IDE instalado: https://docs.arduino.cc/software/ide-v2
2. Abrir Arduino IDE
3. Ir a **File → Preferences**
4. En **Additional boards manager URLs** ingresar:
   ```
   https://dl.espressif.com/dl/package_esp32_index.json
   ```
5. Ir a **Tools → Board → Boards Manager**, buscar `esp32` e instalar
6. Seleccionar **ESP32 Dev Module**

### Configuraciones para ESP32 WROOM

```json
{
  "type": "table",
  "id": "table-01",
  "page": 24,
  "title": "Configuración de herramientas para ESP32 WROOM",
  "headers": ["Parámetro", "Valor"],
  "rows": [
    ["Board", "ESP32 Dev Module"],
    ["Port", "COMx"],
    ["CPU Frequency", "240 MHz"],
    ["Core Debug Level", "None"],
    ["Erase All Flash", "Disabled"],
    ["Events Run On", "Core 1"],
    ["Flash Frequency", "80 MHz"],
    ["Flash Mode", "QIO"],
    ["Flash Size", "4 MB"],
    ["JTAG Adapter", "Disabled"],
    ["Arduino Runs on", "Core 1"],
    ["PSRAM", "Disabled"],
    ["Partition Scheme", "Default 4MB with SPIFFS"],
    ["Upload Speed", "921600"]
  ],
  "notes": "Para ESP32 WROVER activar PSRAM. Para ESP32 S3 usar esquema de partición ESP32S2 con 2M APP, 2M SPIFFS.",
  "source": "Arduino IDE Tools menu"
}
```

### Iniciar la compilación

Con la placa ESP32 conectada por USB, hacer clic en **Sketch → Upload**. Si hay error de transferencia, presionar el botón **BOOT** en la placa durante la transferencia.

### Solucionar el error de conexión de carga

Error típico:
```
A fatal error occurred: Failed to connect to ESP32: Timed out waiting for packet header
```

**Solución hardware:** Conectar un condensador electrolítico de **10 µF entre el pin EN y GND**. Esta manipulación solo es necesaria durante la fase de carga desde Arduino IDE. Una vez instalado ESP32forth, el condensador ya no es necesario.

```json
{
  "type": "image",
  "id": "image-04",
  "page": 26,
  "title": "Condensador de 10 µF entre EN y GND",
  "caption": "Solución al error 'Failed to connect to ESP32'",
  "description": "Protoboard con tarjeta ESP32 y condensador electrolítico de 10 µF conectado entre los pines EN y GND mediante cables dupont.",
  "source": "Foto del autor"
}
```

---

## ¿Por qué programar en FORTH en ESP32?

### Preámbulo

El autor programa en FORTH desde 1983 y es coautor de varios libros sobre el lenguaje:
- *Introduction au ZX-FORTH* (ed. Eyrolles, 1984)
- *Tours de FORTH* (ed. Eyrolles, 1985)
- *FORTH pour CP/M et MSDOS* (ed. Loisitech, 1986)
- *TURBO-Forth, manuel d'apprentissage* (ed. Rem CORP, 1990)
- *TURBO-Forth, guide de référence* (ed. Rem CORP, 1991)

### Límites entre lenguaje y aplicación

Todos los lenguajes de programación se comparten de la siguiente manera:

- **Intérprete y código fuente ejecutable:** BASIC, PHP, MySQL, JavaScript. La aplicación está contenida en archivos que serán interpretados. El sistema debe alojar permanentemente al intérprete.
- **Compilador y/o ensamblador:** C, Java. Algunos compiladores generan código nativo; otros compilan a una máquina virtual.

**FORTH es una excepción.** Integra:
- Un **intérprete** capaz de ejecutar cualquier palabra del diccionario
- Un **compilador** capaz de ampliar el diccionario de palabras

### ¿Qué es una palabra FORTH?

Una palabra FORTH designa cualquier expresión del diccionario compuesta por caracteres ASCII y utilizable en interpretación y/o compilación. La palabra `words` permite enumerar todas las palabras del diccionario.

Ciertas palabras solo se pueden usar en compilación: `if`, `else`, `then`, por ejemplo.

**Principio esencial:** No creamos una aplicación. **¡Ampliamos el diccionario!** Cada nueva palabra definida será una parte tan importante del diccionario como todas las palabras predefinidas.

**Ejemplo:**
```forth
: typeToLoRa ( -- )
  0 echo ! \ desactive l'echo d'affichage du terminal
  ['] serial2-type is type
;

: typeToTerm ( -- )
  ['] default-type is type
  -1 echo ! \ active l'echo d'affichage du terminal
;
```

### ¿Una palabra es una función?

Sí y no. Una palabra puede ser una constante, una variable, una función. La secuencia:
```forth
: typeToLoRa ...código... ;
```
tendría su equivalente en C:
```c
void typeToLoRa() { ...código... }
```

En FORTH no hay límite entre el lenguaje y la aplicación. Se puede ejecutar —a través del intérprete— cualquier palabra predefinida o definida por el usuario, sin tener que pasar por la función principal del programa.

### Lenguaje FORTH comparado con C

**Ejemplo con `if()` en C:**
```c
if(j > 13){
  rc5_ok = 1;
  detachInterrupt(0);
  return;
}
```

**Equivalente en FORTH:**
```forth
var-j @ 13 >
if
  1 rc5_ok !
  di
  exit
then
```

**Inicialización de registros en C:**
```c
void setup() {
  TCCR1A = 0;
  TCCR1B = 0;
  TCNT1 = 0;
  TIMSK1 = 1;
}
```

**Equivalente en FORTH:**
```forth
: setup ( -- )
  0 TCCR1A !
  0 TCCR1B !
  0 TCNT1 !
  1 TIMSK1 !
;
```

### ¿Por qué una pila en lugar de variables?

La pila es un mecanismo implementado en casi todos los microcontroladores. Incluso C aprovecha una pila, pero no tienes acceso a ella. **Solo FORTH brinda acceso completo a la pila de datos.**

Ejemplo: para hacer una suma, apilamos dos valores, ejecutamos la suma, mostramos el resultado:
```forth
2 5 + . \ muestra 7
```

La pila de datos permite pasar datos entre palabras FORTH mucho más rápidamente que procesando variables.

### ¿Hay aplicaciones profesionales escritas en FORTH?

**Sí:**
- El **telescopio espacial HUBBLE** — algunos de cuyos componentes fueron escritos en FORTH
- El **TGV ICE alemán** (Intercity Express) — utiliza procesadores RTX2000 cuyo lenguaje de máquina es FORTH
- La **sonda Philae** que intentó aterrizar en un cometa — también usó el RTX2000

### Caracteres utilizables en nombres de palabras

Con ESP32forth, todos los caracteres ASCII entre 33 y 127 están disponibles:
```
~ } | { z y x w v u t s r q p o n m l k j i h g f e d c b a
~ } \ [ Z Y X W V U T S R Q P O N M L K J I H G F E D C B A
@ ? > = < ; : 9 8 7 6 5 4 3 2 1 0 / . - , + * ) ( ' & % $ # " !
```

---

## Usando números con ESP32Forth

### Números con el intérprete FORTH

Al iniciar ESP32Forth, la ventana del terminal debe indicar que está disponible. Presionar ENTER una o dos veces. ESP32Forth responde con `ok`.

**Ejemplo:**
```
25 33 + . \ muestra 58
```

ESP32Forth tiene dos estados:
- **Intérprete:** ejecuta palabras inmediatamente
- **Compilador:** permite definir nuevas palabras

### Ingresar números con diferentes bases numéricas

Los números se pueden ingresar de forma natural. En decimal:
```
-1234 5678 + . \ muestra 4444
```

**Prefijos para bases:**
- `$` para hexadecimal: `$ff .` → 255
- `%` para binario

**Atención:**
```
$0305 0305
```
No son números iguales si la base numérica hexadecimal no está definida explícitamente.

### Cambio de base numérica

- `hex` — selecciona base hexadecimal
- `binary` — selecciona base binaria
- `decimal` — selecciona base decimal

```forth
hex ff decimal . \ muestra 255
hex $0305 0305 \ ahora son iguales
```

### Binario y hexadecimal

El sistema binario fue inventado por Gottfried Leibniz en 1689 (publicado en 1703).

```forth
: bin0to15 ( -- )
  binary $10 0 do
    cr i .
  loop
  cr decimal
;
```

Resultado:
```
0  1  10  11  100  101  110  111  1000  1001  1010  1011  1100  1101  1110  1111
```

**Álgebra booleana:** Descrita por George Boole, aplicada a circuitos por Claude Shannon. Los componentes fundamentales de computadoras y memorias digitales usan codificación binaria y álgebra booleana.

**Byte:** 8 bits. Valor mínimo: `00000000`, máximo: `11111111`.

**Nibble:** 4 bits. Valores de `0000` a `1111` (0 a 15).

```forth
: bin0to15 ( -- )
  binary $10 0 do
    cr i . i hex . binary
  loop
  cr decimal
;
```

Resultado:
```
0 0
1 1
10 2
11 3
100 4
101 5
110 6
111 7
1000 8
1001 9
1010 A
1011 B
1100 C
1101 D
1110 E
1111 F
```

La representación hexadecimal permite representar el contenido de un byte en formato fijo, de `00` a `FF`.

### Tamaño de los números en la pila de datos FORTH

ESP32forth utiliza una pila de datos de **32 bits** (4 bytes). El valor hexadecimal más pequeño será `00000000`, el más grande `FFFFFFFF`.

```forth
hex abcdefabcdefabcdef . \ muestra EFABCDEF
decimal $ffffffff . \ muestra -1
$ffffffff u. \ muestra 4294967295
```

El bit más significativo se utiliza como signo:
- Si es `0`, el número es positivo
- Si es `1`, el número es negativo

**Ejemplo binario:**
```
 00000000000000000000000000000001  (1)
+11111111111111111111111111111111  (-1)
=100000000000000000000000000000000 (0 en 32 bits)
```

### Acceso a memoria y operaciones lógicas

```forth
hex 0 variable score
score 10 dump
\ display: 1073670412 00 00 00 00 1073670416 55 51 54 55 48 51

decimal 1900 score !
hex score 10 dump
\ display: 3FFEE90C 6C 07 00 00 ...

score @ . \ muestra 1900
```

**Máscaras binarias:**
```forth
1 25 lshift GPIO_ENABLE_REG !
\ Activa GPIO25

1 25 lshift 1 17 lshift or GPIO_ENABLE_REG !
\ Activa GPIO17 y GPIO25 simultáneamente

hex score @ $000000FF and . \ aísla byte menos significativo
score @ $0000FF00 and . \ aísla segundo byte
```

### Conclusión del capítulo

FORTH es un lenguaje interesante gracias a:
- Su intérprete que permite realizar numerosas pruebas de forma interactiva sin recompilar
- Un diccionario a cuya mayoría de palabras el intérprete puede acceder
- Un compilador que permite agregar nuevas palabras sobre la marcha y probarlas inmediatamente
- El código FORTH compilado es tan eficiente como su equivalente en C

---

## Un verdadero FORTH de 32 bits con ESP32Forth

ESP32Forth es un FORTH real de 32 bits. Todos los datos pasan a través de una pila de datos. **Cada posición en la pila es SIEMPRE un entero de 32 bits.**

### Valores en la pila de datos

```forth
67 emit \ muestra C
```

### Valores en la memoria

Ejemplo con código Morse:
```forth
create mA ( -- addr )
  2 c,
  char . c, char - c,

create mB ( -- addr )
  4 c,
  char - c, char . c, char . c, char . c,

create mC ( -- addr )
  4 c,
  char - c, char . c, char - c, char . c,

: .morse ( addr -- )
  dup 1+ swap c@ 0 do
    dup i + c@ emit
  loop
  drop
;

mA .morse \ muestra .-
mB .morse \ muestra -...
mC .morse \ muestra -.-
```

### Procesamiento de textos según tipo de datos

```forth
: pain s" Pain cuit" ;
: prix s" 2.30" ;
pain type s" : " type prix type
\ muestra Pain cuit: 2.30
```

**Ejemplo de conversión HH:MM:SS:**
```forth
: :##  # 6 base !  # decimal  [char] : hold  ;
: .hms ( n -- )
  <# :## :### # # #> type
;
4225 .hms \ muestra 01:10:25
```

### Conclusión

FORTH no tiene tipificación de datos. Todos los datos pasan a través de una pila de datos. **Cada posición en la pila es SIEMPRE un entero de 32 bits.** Esa simplicidad es la fuente de su poder.

---

## Comentarios y aclaraciones

### Escribir código FORTH legible

No existe un IDE específico para FORTH. Se puede usar cualquier editor de texto ASCII: `edit`, `wordpad`, `PsPad`, `Netbeans`, etc.

**Ejemplo de código poco legible:**
```forth
: cycle.stop -1 +to MAX_LIGHT_TIME MAX_LIGHT_TIME 0 = if LOW myLIGHTS pin else 0 rerun then ;
```

**Convenciones de nomenclatura:**
- Constantes en mayúsculas: `MAX_LIGHT_TIME_NORMAL_CYCLE`
- Palabra que define otras palabras: `defPin:` (termina en dos puntos)
- Palabra de transformación de dirección: `>date`
- Almacenamiento en memoria: `date@` o `date!`
- Visualización de datos: `.fecha`

**Sangría:** Aunque no afecta el rendimiento, mejora la legibilidad:
```forth
60 constant MAX_LIGHT_TIME_NORMAL_CYCLE

: cycle.stop
  -1 +to MAX_LIGHT_TIME
  MAX_LIGHT_TIME 0 =
  if
    LOW myLIGHTS pin
  else
    0 rerun
  then
;
```

### Los comentarios

- `(` ... `)` — comentario en línea (requiere espacio después del paréntesis)
- `\` — comentario hasta el final de la línea (requiere espacio después)

**Comentarios de pila:**
```forth
dup ( n - n n )
swap ( n1 n2 - n2 n1 )
drop ( n - - )
emit ( c - - )
```

**Símbolos en comentarios de pila:**

| Símbolo | Significado |
|---|---|
| `addr` | Dirección de memoria |
| `c` | Valor de 8 bits [0..255] |
| `d` | Valor de doble precisión (no usado en ESP32forth) |
| `fl` | Valor booleano (0 o distinto de cero) |
| `n` | Entero con signo de 32 bits |
| `str` | Cadena de caracteres (equivale a `addr len`) |
| `u` | Entero sin signo |

### Herramientas de diagnóstico

**Descompilador:**
```forth
see c>f
\ muestra: : C>F 9 5 */ 32 + ;
```

**Volcado de memoria:**
```forth
hex myDATAS 4 dump
\ display: 3FFEE4EC 01 02 03 04
```

**Monitor de pila:**
```forth
variable debugStack
: debugOn ( -- ) -1 debugStack ! ;
: debugOff ( -- ) 0 debugStack ! ;
: .DEBUG debugStack @ if cr ." STACK: " .s key drop then ;

: myTEST 128 32 do i .DEBUG emit loop ;
debugOn myTest
```

---

## Diccionario / Pila / Variables / Constantes

### Ampliar diccionario

```forth
: *+ * + ;
decimal 5 6 7 *+ . \ muestra 47
```

La palabra `forget` elimina entradas del diccionario:
```forth
: test1 ;
: test2 ;
: test3 ;
forget test2 \ borra test2 y test3
```

### Pilas y notación polaca inversa

**Pila de parámetros (data stack):** Se usa para pasar números entre palabras.

```forth
decimal 2 5 73 -16
+ - *
```

Evolución de la pila:
```
Inicial:    2  5  73  -16
Después +:  2  5  57
Después -:  2  -52
Después *:  -104
```

### Manejo de la pila de parámetros

| Palabra | Efecto |
|---|---|
| `drop` | Elimina el número superior |
| `swap` | Intercambia los 2 primeros |
| `dup` | Duplica el número superior |
| `rot` | Rota los 3 primeros |
| `over` | Copia el segundo a la parte superior |
| `nip` | Elimina el segundo |
| `tuck` | Copia el superior debajo del segundo |

### La pila de retorno

ESP32forth usa la pila de retorno para direcciones de retorno de palabras anidadas. El usuario puede almacenar temporalmente en ella:
- `>r` — mueve de pila de parámetros a pila de retorno
- `r>` — mueve de pila de retorno a pila de parámetros
- `r@` — copia la parte superior de la pila de retorno
- `rdrop` — elimina el valor superior de la pila de retorno

> **Advertencia:** Usar `>r` y `r>` en modo interpretado está prohibido. Solo en definiciones compiladas.

### Uso de memoria

- `@` (fetch) — recupera un valor de 32 bits de una dirección
- `!` (store) — almacena un valor de 32 bits en una dirección
- `c@` — recupera un byte (8 bits)
- `c!` — almacena un byte

```forth
create testVar  cell allot
$f7 testVar c!
testVar c@ . \ muestra 247
```

### Variables

```forth
variable x
3 x !
x @ . \ muestra 3
```

### Constantes

```forth
19 constant VSPI_MISO
23 constant VSPI_MOSI
18 constant VSPI_SCLK
05 constant VSPI_CS
4000000 constant SPI_FREQ
```

### Valores pseudoconstantes

```forth
decimal 13 value thirteen
thirteen . \ muestra 13
47 to thirteen
thirteen . \ muestra 47
```

### Herramientas básicas de asignación de memoria

```forth
create graphic-array ( -- addr )
  %00000000 c,  %00000010 c,  %00000100 c,
  %00001000 c,  %00100000 c,  %01000000 c,  %10000000 c,

30 graphic-array 2 + c!
graphic-array 2 + c@ . \ muestra 30
```

---

## Colores de texto y posición de visualización

### Codificación ANSI de terminales

ESP32forth soporta secuencias de escape ANSI para colores y posicionamiento.

```forth
09 constant red
11 constant yellow
14 constant cyan
15 constant whyte

: box { x0 y0 xn yn color -- }
  color bg
  yn y0 - 1+ \ determine height
  0 do
    x0 y0 i + at-xy
    xn x0 - spaces
  loop
  normal
;

: 3boxes ( -- )
  page
  2 4 20 6 cyan box
  8 6 28 8 red box
  14 8 36 10 yellow box
  0 0 at-xy
;
```

```json
{
  "type": "image",
  "id": "image-05",
  "page": 63,
  "title": "Tres cuadros de colores en terminal ANSI",
  "caption": "Resultado de ejecutar 3boxes",
  "description": "Terminal Tera Term mostrando tres rectángulos: cyan arriba-izquierda, rojo centro, amarillo abajo-derecha.",
  "source": "Captura de pantalla del autor"
}
```

### Colores de texto

```forth
: testFG ( -- )
  page
  16 0 do
    16 0 do
      j 16 * i + fg
      ." x"
    loop
    cr
  loop
  normal
;
```

### Posición de visualización

```forth
09 constant red
11 constant yellow
14 constant cyan
15 constant whyte

: box { x0 y0 xn yn color -- }
  color bg
  yn y0 - 1+
  0 do
    x0 y0 i + at-xy
    xn x0 - spaces
  loop
  normal
;
```

---

## Variables locales con ESP32Forth

### Introducción

Las variables locales ofrecen una alternativa a la pila de datos para seguir el flujo de datos en definiciones complejas.

### El comentario de la pila falsa

```forth
: um+ ( u1 u2 -- sum carry )
  \ definición
;
```

Los comentarios entre `(` y `)` son solo informativos. Las variables locales se definen entre `{` y `}`:

```forth
: 20VER { a b c d } a b c d a b ;
```

Las variables toman valores de la pila en orden. Ejemplo:
```
1 2 3 4 20ver
\ devuelve: 1 2 3 4 1 2
```

### Acción sobre variables locales

Las variables locales actúan como pseudovariables definidas por `value`:

```forth
: um+ { u1 u2 -- sum carry }
  0 { sum }
  cell for
  aft
    u1 $100 /mod to u1
    u2 $100 /mod to u2
    +
    cell 1- i - 8 * lshift +to sum
  then
  next
  sum
  u1 u2 + abs
;
```

**Reescritura de DUMP con variables locales:**
```forth
: dump ( start len -- )
  cr cr ." --addr-- " ." 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F -- chars----"
  2dup + { END_ADDR }
  swap { START_ADDR }
  START_ADDR 16 / 16 * { 0START_ADDR }
  16 / 1+ { LINES }
  base @ { myBASE }
  hex
  LINES 0 do
    0START_ADDR i 16 * +
    cr <## ## ## [char] - hold ## ## ## > type space space
    16 0 do
      0START_ADDR j 16 * i + + ca@
      <## ## > type space
    loop
    space
    16 0 do
      0START_ADDR j 16 * i + +
      ca@ dup 32 < over 127 > or
      if
        drop [char] . emit
      else
        emit
      then
    loop
  loop
  myBASE base !
  cr cr
;
```

> **ADVERTENCIA:** Si se usan variables locales en una definición, **no usar** las palabras `>r` y `r>`.

---

## Estructuras de datos para ESP32forth

### Preámbulo

ESP32forth es una versión de 32 bits. El tamaño de los elementos en la pila se obtiene con:
```forth
cell . \ muestra 4
```

### Tablas en FORTH

**Matriz unidimensional de 32 bits:**
```forth
create temperatures
34 , 37 , 42 , 36 , 25 , 12 ,

: temp@ ( index -- value )
  cell * temperatures + @
;

0 temp@ . \ muestra 34
2 temp@ . \ muestra 42
```

**Palabras de definición de tabla:**
```forth
: array ( comp: -- | exec: index -- addr )
  create
  does>
  swap cell * +
;

array myTemps
21 , 32 , 45 , 44 , 28 , 12 ,

0 myTemps @ . \ muestra 21
5 mytemps @ . \ muestra 12
```

**Variante compacta (bytes):**
```forth
: arrayC ( comp: -- | exec: index -- addr )
  create
  does>
  +
;

arrayC myCTemps
21 c, 32 c, 45 c, 44 c, 28 c, 12 c,

0 myCTemps c@ . \ muestra 21
5 myCTemps c@ . \ muestra 12
```

**Leer y escribir en tabla:**
```forth
arrayC myCTemps
6 allot
0 myCTemps 6 0 fill
32 0 myCTemps c!
25 5 myCTemps c!
0 myCTemps c@ . \ muestra 32
```

**Matriz bidimensional:**
```forth
63 constant SCR_WIDTH
16 constant SCR_HEIGHT

create mySCREEN
SCR_WIDTH SCR_HEIGHT * allot
mySCREEN SCR_WIDTH SCR_HEIGHT * bl fill

: xySCRaddr { x y -- addr }
  SCR_WIDTH y * x + mySCREEN +
;

: SCR@ ( x y -- c ) xySCRaddr c@ ;
: SCR! ( c x y -- ) xySCRaddr c! ;

char X 15 5 SCR!
15 5 SCR@ emit
```

### Gestión de estructuras complejas

```forth
structures
struct YMDHMS
  ptr field >year
  ptr field >month
  ptr field >day
  ptr field >hour
  ptr field >min
  ptr field >sec

create DateTime YMDHMS allot

2022 DateTime >year !
03 DateTime >month !
21 DateTime >day !
22 DateTime >hour !
36 DateTime >min !
15 DateTime >sec !
```

**Estructura compacta (i8):**
```forth
struct cYMDHMS
  ptr field >year
  i8 field >month
  i8 field >day
  i8 field >hour
  i8 field >min
  i8 field >sec

create cDateTime cYMDHMS allot

2022 cDateTime >year !
03 cDateTime >month c!
21 cDateTime >day c!
22 cDateTime >hour c!
36 cDateTime >min c!
15 cDateTime >sec c!
```

### Definición de sprites

```forth
structures
struct CARRAY
  i8 field >width
  i8 field >height
  i8 field >content

create myVscreen
32 c, 08 c,
myVscreen >width c@ myVscreen >height c@ * allot

: sprite: ( width height -- )
  create
  swap c, c,
  does>
;

2 1 sprite: blackChars
  $db c, $db c,

2 1 sprite: greyChars
  $b2 c, $b2 c,

blackChars >content 2 type
```

**Sprite 5x7:**
```forth
5 7 sprite: char3
  $20 c, $db c, $db c, $db c, $20 c,
  $db c, $20 c, $20 c, $20 c, $db c,
  $20 c, $20 c, $20 c, $20 c, $db c,
  $20 c, $db c, $db c, $db c, $20 c,
  $20 c, $20 c, $20 c, $20 c, $db c,
  $db c, $20 c, $20 c, $20 c, $db c,
  $20 c, $db c, $db c, $db c, $20 c,
```

**Mostrar sprite:**
```forth
: .sprite { xpos ypos sprAddr -- }
  sprAddr >height c@ 0 do
    xpos ypos at-xy
    sprAddr >width c@ i *
    sprAddr >content +
    sprAddr >width c@ type
    1 +to ypos
  loop
;

0 constant blackColor
1 constant redColor
4 constant blueColor

10 02 char3 .sprite
redColor fg
16 02 char3 .sprite
blueColor fg
22 02 char3 .sprite
blackColor fg
cr cr
```

---

## Instalación de la biblioteca OLED para SSD1306

Desde ESP32forth 7.0.7.15, las opciones están en la carpeta `optional`:
- `assemblers.h`
- `camera.h`
- `interrupts.h`
- `oled.h`
- `rmt.h`
- `serial-bluetooth.h`
- `spi-flash.h`

**Instalación:**
1. Copiar `oled.h` a la carpeta que contiene `ESP32forth.ino`
2. En Arduino IDE: **Sketch → Include → Manage Libraries**
3. Buscar **Adafruit SSD1306 by Adafruit** e instalar
4. Compilar y cargar

**Vocabulario OLED disponible:**
```
OledInit SSD1306_SWITCHCAPVCC SSD1306_EXTERNALVCC WHITE BLACK
OledReset HEIGHT WIDTH OledAddr OledNew OledDelete OledBegin
OledHOME OledCLS OledTextc OledPrintln OledNumln OledNum
OledDisplay OledPrint OledInvert OledTextsize OledSetCursor
OledPixel OledDrawL OledCirc OledCircF OledRect OledRectF
OledRectR OledRectRF oled-builtins
```

---

## Números reales con ESP32forth

### Los reales con ESP32forth

Los números reales terminan en `e`:
```forth
3 \ push 3 on the normal stack
3e \ push 3 on the real stack
5.21e f. \ display 5.210000
```

### Precisión

```forth
pi f. \ display 3.141592
4 set-precision
pi f. \ display 3.1415
```

La precisión límite es de **6 decimales**.

### Constantes y variables reales

```forth
0.693147e fconstant ln2
fvariable intensity
170e 12e F/ intensity SF!
intensity SF@ f. \ display 14.166669
```

### Operadores aritméticos

```forth
1.23e 4.56e F+ f. \ display 5.790000
1.23e 4.56e F- f. \ display -3.330000
1.23e 4.56e F* f. \ display 5.608800
1.23e 4.56e F/ f. \ display 0.269736
```

**Otras palabras:**
- `1/F` — inverso
- `fsqrt` — raíz cuadrada
- `F**` — potencia
- `FATAN2` — arcotangente
- `FCOS` — coseno
- `FEXP` — exponencial
- `FLN` — logaritmo natural
- `FSIN` — seno
- `FSINCOS` — seno y coseno

### Operadores lógicos

- `F0<`, `F0=`, `f<`, `f<=`, `f<>`, `f=`, `f>`, `f>=`

### Conversiones

- `F>S` — real a entero
- `S>F` — entero a real

```forth
35 S>F F. \ display 35.000000
3.5e F>S . \ muestra 3
```

---

## Mostrar números y cadenas de caracteres

### Cambio de base numérica

Dominio de enteros de 32 bits: -2147483648 a 2147483647

```forth
255 HEX . DECIMAL \ muestra FF
2 BASE !
DECIMAL
```

**Palabras predefinidas:**
- `DECIMAL`
- `HEX`
- `BINARY`

### Definición de nuevos formatos de visualización

```forth
: .EUROS ( n --- )
  <# # # [char] , hold #S #> type space ." EUR"
;
1245 .euros \ muestra 12,45 EUR
```

**Ejemplo HH:MM:SS:**
```forth
: :00 ( --- )
  DECIMAL #
  6 BASE ! #
  [char] : HOLD
  DECIMAL
;

: HMS ( n --- )
  <# :00 :00 #S #> TYPE SPACE
;

59 HMS \ muestra 0:00:59
60 HMS \ muestra 0:01:00
4500 HMS \ muestra 1:15:00
```

### Mostrar caracteres y cadenas

```forth
65 EMIT \ muestra A
```

**Tabla ASCII:**
```forth
variable #out
: #out+! ( n -- ) #out +! ;
: (.) ( n -- a l )
  DUP ABS <# #S ROT SIGN #>
;
: .R ( n l -- )
  >R (.) R> OVER - SPACES TYPE
;
: JEU-ASCII ( -- )
  cr 0 #out !
  128 32 DO
    I 3 .R SPACE
    4 #out+!
    I EMIT 2 SPACES
    3 #out+!
    #out @ 77 = IF CR 0 #out ! THEN
  LOOP
;
```

### Variables de cadena

```forth
: string ( comp: n --- names_strvar | exec: --- addr len )
  create
  dup c,
  0 c,
  allot
  does>
  2 + dup 1 - c@
;

16 string strState
```

**Código completo de gestión:**
```forth
DEFINED? --str [if] forget --str [then]
create --str

: $= ( addr1 len1 addr2 len2 --- fl) str= ;

: string ( n --- names_strvar )
  create dup ,
  0 ,
  allot
  does> cell+ cell+ dup cell - @
;

: maxlen$ ( strvar --- strvar maxlen )
  over cell - cell - @
;

: $! ( str strvar --- )
  maxlen$ nip rot min 2dup swap cell - ! cmove
;

: 0$! ( addr len -- )
  drop 0 swap cell - !
;

: right$ ( str1 n -- str2 )
  0 max over min >r + r@ - r>
;

: left$ ( str1 n -- str2 )
  0 max min
;

: mid$ ( str1 pos len -- str2 )
  >r over swap - right$ r> left$
;

: c+$! ( c str1 -- )
  over >r
  + c!
  r> cell - dup @ 1+ swap !
;

: input$ ( addr len -- )
  over swap maxlen$ nip accept
  swap cell - !
;
```

**Ejemplo:**
```forth
64 string myNewString
s"Este es mi primer ejemplo..." myNewString $!
myNewString type
\ muestra: Este es mi primer ejemplo...
```

### Agregar carácter a variable alfanumérica

```forth
32 string AT_BAND
s" AT+BAND=868500000" AT_BAND $!
$0a AT_BAND c+$!
$0d AT_BAND c+$!
```

**Variable CRLF:**
```forth
2 string $crlf
$0d $crlf c+$!
$0a $crlf c+$!
: crlf ( -- ) $crlf type ;
```

---

## Vocabularios con ESP32forth

### Lista de vocabularios

```forth
internals voclist
\ displays:
registers ansi editor streams tasks rtos sockets Serial
ledc SPIFFS SD_MMC SD WiFi wire ESP structures internalized
internals FORTH
```

### Vocabularios esenciales

- `ansi` — terminal ANSI
- `editor` — comandos para editar archivos de bloques
- `oled` — pantallas OLED (requiere compilar `oled.h`)
- `structures` — gestión de estructuras complejas

### Usando palabras de vocabulario

```forth
serial \ Seleccionar vocabulario Serial
: serial2-type ( a n -- ) Serial2.write drop ;
```

**Integrar una sola palabra:**
```forth
: serial2-type ( a n -- )
  [ serial ] Serial2.write [ FORTH ]
  drop
;
```

### Encadenamiento de vocabularios

```forth
only order \ affiche: FORTH
asm also order \ affiche: asm >> FORTH
xtensa order \ affiche: xtensa >> asm >> FORTH
```

---

## Palabras de acción retrasada (defer)

### Definición y uso

```forth
defer vector
' words is vector
vector \ ejecuta words

' page is vector
vector \ ahora ejecuta page
```

### Establecer una referencia directa

```forth
defer word2
: word1 ( --- ) word2 ;
: (word2) ( --- ) ;
' (word2) is word2
```

### Dependencia del contexto operativo

```forth
defer type
defer key
defer key?

' default-type is type
```

**Redirección a LoRa:**
```forth
: serial2-type ( a n -- ) Serial2.write drop ;

: typeToLoRa ( -- )
  0 echo !
  [' ] serial2-type is type
;

: typeToTerm ( -- )
  [' ] default-type is type
  -1 echo !
;
```

### Un caso práctico: días en varios idiomas

```forth
:noname s" Saterday" ;
:noname s" Friday" ;
:noname s" Thursday" ;
:noname s" Wednesday" ;
:noname s" Tuesday" ;
:noname s" Monday" ;
:noname s" Sunday" ;

create ENdayNames

:noname s" Samedi" ;
:noname s" Vendredi" ;
:noname s" Jeudi" ;
:noname s" Mercredi" ;
:noname s" Mardi" ;
:noname s" Lundi" ;
:noname s" Dimanche" ;

create FRdayNames

defer dayNames

: in-ENGLISH ['] ENdayNames is dayNames ;
: in-FRENCH ['] FRdayNames is dayNames ;

: _getString { array length -- addr len }
  array swap cell * + @ execute
  length ?dup if min then
;

10 value dayLength

: getDay ( n -- addr len )
  dayNames dayLength _getString
;

in-ENGLISH 3 getDay type cr \ display: Wednesday
in-FRENCH 3 getDay type cr \ display: Mercredi
```

---

## Palabras de creación de palabras

### Usando does>

```forth
: defREG: ( addr1 -- <name> )
  create ,
  does> ( -- regAddr ) @
;

$3FF44004 defREG: GPIO_OUT_REG
```

**Ejemplo de gestión del color:**
```forth
0 value currentCOLOR

: color: ( n -- <name> )
  create
  ,
  does>
  @ to currentCOLOR
;

$00 color: setBLACK
$ff color: setWHITE
```

**Ejemplo de escritura en pinyin:**
```forth
internals
: chinese: create ( c1 c2 c3 -- )
  c, c, c,
  does> 3 serial-type
;
forth

169 151 230 chinese: Zao
137 174 229 chinese: An

Zao An \ muestra 早安
```

---

## Adaptar placas de pruebas a la placa ESP32

### Construya una placa de pruebas adecuada

1. Tomar dos placas de prueba idénticas
2. En una, cortar un cable eléctrico desde abajo con un cortador
3. Separar la línea eléctrica
4. Colocar la tarjeta ESP32 entre ambas

```json
{
  "type": "image",
  "id": "image-06",
  "page": 109,
  "title": "Tarjeta ESP32 mal encajada en protoboard",
  "caption": "Problema típico: la ESP32 no encaja bien en la protoboard estándar",
  "description": "Tarjeta ESP32 insertada en protoboard con los pines sobresaliendo y conexiones inestables.",
  "source": "Foto del autor"
}
```

---

## Alimentación de la placa ESP32

### Alimentado por conector mini-USB

La solución más sencilla: usar una fuente de alimentación de red o una batería de respaldo (power bank).

```json
{
  "type": "image",
  "id": "image-07",
  "page": 111,
  "title": "Alimentación por power bank",
  "caption": "Placa ESP32 alimentada con batería de respaldo",
  "description": "Placa ESP32 conectada a un power bank mediante cable USB, con un LED encendido en la protoboard.",
  "source": "Foto del autor"
}
```

### Alimentación mediante pin de 5V

Conectar fuente externa no regulada entre 5V y GND. **Voltaje entre 5 y 12V.** Preferible mantener alrededor de 6-7V para evitar pérdida de energía en forma de calor.

> **PRECAUCIÓN:** Mantener el voltaje de entrada por debajo de 12V para reducir el calor en el regulador de voltaje.

```json
{
  "type": "image",
  "id": "image-08",
  "page": 111,
  "title": "Pines 5V y GND",
  "caption": "Terminales para fuente de alimentación externa de 5-12V",
  "description": "Tarjeta ESP32 con flechas rojas señalando los pines GND y 5V.",
  "source": "Foto del autor"
}
```

### Inicio automático de un programa

```forth
18 constant myLED
0 value LED_STATE

: led.on ( -- )
  HIGH dup myLED pin to LED_STATE
;

: led.off ( -- )
  LOW dup myLED pin to LED_STATE
;

timers also

: led.toggle ( -- )
  LED_STATE if led.off else led.on then
  0 rerun
;

: led.blink ( -- )
  myLED output pinMode
  ['] led.toggle 500000 0 interval
  led.toggle
;

startup: led.blink
bye
```

La secuencia `startup: led.blink` designa `led.blink` como la palabra que se ejecutará al iniciar ESP32forth.

---

## Instale y use la terminal Tera Term en Windows

### Instalación

Descargar desde: **https://ttssh2.osdn.jp/index.html.en**

### Configuración

1. **Configuración → Puerto serie:** Velocidad 115200, 8 bits, sin paridad, 1 bit de parada, sin control de flujo
2. **Configuración → Ventana:** Título "Tera Term", cursor en bloque, 16 colores, buffer 10000 líneas
3. **Configuración → Fuente:** Source Code Pro, tamaño 12
4. **Configuración → Guardar configuración:** Guardar como `TERATERM.INI`

```json
{
  "type": "image",
  "id": "image-09",
  "page": 116,
  "title": "Configuración del puerto serie en Tera Term",
  "caption": "Tera Term: Serial port setup",
  "description": "Ventana de configuración con Port COM3, Speed 115200, Data 8 bit, Parity none, Stop bits 1, Flow control none.",
  "source": "Captura de pantalla de Tera Term"
}
```

### Usando Tera Term

1. Conectar la placa ESP32 a un puerto USB
2. Iniciar Tera Term
3. **Archivo → Nueva conexión → Serie → COMx**
4. Aparecerá el prompt de ESP32forth

---

## Compilar código fuente en lenguaje Forth

**Recordatorio:** FORTH está en la placa ESP32, no en la PC. No se puede compilar en la PC.

**Procedimiento:**
1. Abrir archivo fuente en la PC con cualquier editor de texto
2. Copiar el código fuente
3. Pegar en la ventana del terminal Tera Term
4. El código se interpreta y/o compila inmediatamente
5. Ejecutar la palabra FORTH desde el terminal

---

## Acceso a ESP32Forth por TELNET

### Conexión WiFi

```forth
: myWiFiConnect ( -- )
  z" Mariloo"
  z" 1925144D91DE5373C3XXXXXXXX"
  login
;
```

Al ejecutar `myWiFiConnect` se muestra:
```
192.168.1.8
MDNS started
```

### Cambiar el nombre DNS

Por defecto, ESP32forth asigna un nombre a la tarjeta. Se puede cambiar:

```forth
\ Establece forthCOM3 para la primera tarjeta ESP32
z" Mariloo" z" 1925144D91DE5373C3C2DXXXXX" login
z" forthCOM3" MDNS.begin
cr telnetd 552 server forth
```

**Uso:**
1. Desenchufar la placa ESP32
2. Volver a conectar (sin abrir terminal)
3. Esperar unos segundos
4. Iniciar PuTTY y conectar TELNET a `forthCOM3` puerto 552

---

## Gestión de archivos fuente por bloques

### Los bloques

Un bloque es un espacio de almacenamiento de 16 líneas × 64 caracteres = **1024 bytes** (1 KB).

```json
{
  "type": "image",
  "id": "image-10",
  "page": 125,
  "title": "Bloque en una computadora antigua",
  "caption": "Blk# 2 of 23: File=Forth Blocks",
  "description": "Editor de bloques clásico mostrando código FORTH para una ventana de pintura.",
  "source": "Captura histórica"
}
```

### Comandos del editor de bloques

| Comando | Acción |
|---|---|
| `1 list` | Enumera el contenido del bloque actual |
| `n` | Selecciona el siguiente bloque |
| `p` | Selecciona el bloque anterior |
| `wipe` | Vacía el contenido del bloque actual |
| `d` | Elimina la línea n (0-14) |
| `e` | Borra el contenido de la línea n (0-15) |
| `a` | Inserta una línea n (0-14) |
| `r` | Reemplaza el contenido de la línea n |
| `flush` | Guarda el contenido de los bloques |
| `load` | Compila el contenido de un bloque |
| `thru` | Compila un rango de bloques |

### Ejemplo práctico

```forth
1 list
editor
0 r \ tools for REGISTERS definitions and manipulations
1 r : mclr { mask addr -- } addr @ mask invert and addr ! ;
2 r : mset { mask addr -- } addr @ mask or addr ! ;
3 r : mtst { mask addr -- x } addr @ mask and ;
4 r : defREG: \ define a register, similar as constant
5 r   create ( addr1 -- <name> ) ,
6 r   does> ( -- regAddr ) @ ;
7 r : .reg ( reg -- ) \ display reg content
8 r   base @ >r binary @ <#
9 r   4 for aft 8 for aft # then next
10 r   bl hold then next #>
11 r   cr space ." 33222222 22221111 11111100 00000000"
12 r   cr space ." 10987654 32109876 54321098 76543210"
13 r   cr type r> base ! ;
14 r : defMASK: create ( mask0 position -- ) lshift ,
15 r   does> ( -- mask1 ) @ ;
save-buffers
```

---

## Edición de archivos fuente con VISUAL Editor

### Editar un archivo fuente FORTH

```forth
visual edit /spiffs/dump.fs
```

- Si el archivo no existe, se crea
- Si el archivo existe, se recupera en el editor

**Comandos del editor:**
- Flechas para mover el cursor
- **CTRL-S:** guarda el contenido
- **CTRL-X:** sale de la edición (N = sin guardar, Y = con guardado)

### Compilando el contenido del archivo

```forth
include /spiffs/dump.fs
```

La compilación es mucho más rápida que a través del terminal.

---

## Gestión de proyectos RECORDFILE y FORTH

### Guarde RECORDFILE en el archivo autoexec.fs

```forth
\ These chars terminate all text lines in a file
create crlf 13 C, 10 C,

\ Records the input stream to a spiffs file until
\ an <EOF> marker is encountered, then close file
: RECORDFILE ( "filename" "filecontents" "<EOF>" -- )
  bl parse \ read the filename ( a n )
  W/O CREATE-FILE throw >R \ create the file to record to
  \ put file id on R stack
  BEGIN
    \ read a line of the file from the input stream
    tib #tib accept
    tib over S" <EOF>" startswith?
    \ does the line start with <EOF> ?
    DUP IF
      \ Yes, so drop the end line of the file containing <EOF>
      swap drop
    ELSE
      swap tib swap
      \ No, so write the line to the open file
      R@ WRITE-FILE throw
      \ and terminate line with cr-lf
      crlf 2 R@ WRITE-FILE throw
    THEN
  UNTIL
  R> CLOSE-FILE throw
;
```

### Desglosando un proyecto

Estructura recomendada:
```
ESP32forth developments/
├── _my Projects/
│   └── TEMPVS FVGIT/
│       ├── main.fs
│       ├── config.fs
│       ├── strings.fs
│       └── ...
├── _sandbox/
├── Tools/
└── Documentación/
```

**Contenido de main.fs:**
```forth
RECORDFILE /spiffs/main.fs

DEFINED? --tempusFugit [if] forget --tempusFugit [then]
create --tempusFugit

s" /spiffs/strings.fs" included
s" /spiffs/RTClock.fs" included
s" /spiffs/clepsydra.fs" included
s" /spiffs/config.fs" included
s" /spiffs/oledTools.fs" included

<EOF>
```

### La noción de caja negra

Una palabra FORTH debe ser simple, con definición corta y pocos parámetros. Una vez probada, se convierte en una "caja negra" fiable.

**Pruebas unitarias:**
```forth
assert( 0 >gray 0 = )
assert( 1 >gray 1 = )
assert( 2 >gray 3 = )
assert( 3 >gray 2 = )
assert( 4 >gray 6 = )
assert( 5 >gray 7 = )
assert( 6 >gray 5 = )
assert( 7 >gray 4 = )
```

---

## El sistema de archivos SPIFFS

ESP32Forth contiene un sistema de archivos en la memoria Flash interna: **SPIFFS** (Serial Peripheral Interface Flash File System).

### Acceso al sistema de archivos

```forth
include /spiffs/dumpTool.fs
ls /spiffs/
\ dumpTool.fs
```

### Manejo de archivos

| Palabra | Acción |
|---|---|
| `ls /spiffs/` | Lista archivos |
| `rm /spiffs/archivo.fs` | Elimina archivo |
| `mv /spiffs/origen /spiffs/destino` | Renombra |
| `cp /spiffs/origen /spiffs/destino` | Copia |
| `cat /spiffs/archivo.fs` | Muestra contenido |
| `touch /spiffs/archivo.fs` | Crea archivo vacío |
| `dump-file` | Guarda cadena en archivo |

### Organización de archivos

- Todos los archivos en formato de texto ASCII
- Extensión recomendada: `.fs`
- Usar `RECORDFILE` para guardar archivos grandes
- Crear un `main.fs` que cargue todos los demás

---

## Gestión de un semáforo con ESP32

### Puertos GPIO

```forth
\ Definir LED GPIO
25 constant ledRED
26 constant ledYELLOW
27 constant ledGREEN

\ Definir máscaras
1 ledRED defMASK: mLED_RED
1 ledYELLOW defMASK: mLED_YELLOW
1 ledGREEN defMASK: mLED_GREEN

\ Inicialización
: LEDinit
  ledGREEN output pinMode
  ledYELLOW output pinMode
  ledRED output pinMode
;
```

### Gestión del semáforo

```forth
\ trafficLights ejecuta un ciclo de luz
: trafficLights ( -- )
  high ledGREEN pin
  3000 ms
  low ledGREEN pin
  high ledYELLOW pin
  800 ms
  low ledYELLOW pin
  high ledRED pin
  3000 ms
  low ledRED pin
;

\ bucle de semáforo clásico
: lightsLoop ( -- )
  LEDinit
  begin
    trafficLights
    key?
  until
;

\ estilo semáforo alemán
: Dtraffic ( -- )
  high ledGREEN pin
  3000 ms
  low ledGREEN pin
  high ledYELLOW pin
  800 ms
  low ledYELLOW pin
  high ledRED pin
  3000 ms
  ledYELLOW high
  800 ms
  high ledRED pin
  high ledYELLOW pin
;

: DlightsLoop ( -- )
  LEDinit
  begin
    Dtraffic
    key?
  until
;
```

---

## Acceso directo a los registros GPIO

### Uso de palabras m! y m@

```forth
$3ff44004 defREG: GPIO_OUT_REG

0 GPIO_OUT_REG m! \ apagar LED en G2
4 GPIO_OUT_REG m! \ encender LED en G2
```

**Definición de palabras:**
```forth
\ mostrar n en formato binario
: .binDisp ( n -- )
  base @ >r binary
  <#
  4 for aft 8 for aft # then next
  bl hold
  then next
  #>
  cr space ." 33222222 22221111 11111100 00000000"
  cr space ." 10987654 32109876 54321098 76543210"
  cr type
  r> base !
;

create myReg 0 ,

myReg @ .binDisp
\ display:
\ 33222222 22221111 11111100 00000000
\ 10987654 32109876 54321098 76543210
\ 00000000 00000000 00000000 00000000
```

**Usando m! con máscara:**
```forth
registers
1 22 $ffffffff myReg m!
forth
myReg @ .binDisp
\ display:
\ 00000000 01000000 00000000 00000000
```

**Definición de máscaras:**
```forth
: defMASK: ( comp: mask0 position -- <name> | exec: -- position mask1 )
  create
  dup ,
  lshift ,
  does>
  dup @ swap cell + @
;

1 12 defMASK: mB12

registers
1 mB12 myREG m!
forth
```

### El registro GPIO_OUT_REG

```forth
\ Registro de salida GPIO 0-31 R/W
$3FF44004 defREG: GPIO_OUT_REG

\ LED definidos
25 constant ledRED
26 constant ledYELLOW
27 constant ledGREEN

\ Definir máscaras
1 ledRED defMASK: mLED_RED
1 ledYELLOW defMASK: mLED_YELLOW
1 ledGREEN defMASK: mLED_GREEN

\ establecer máscara en dirección
: regSet ( val shift mask addr -- )
  [ registers ] m! [ forth ]
;

\ máscara de prueba en dirección
: regTst ( shift mask addr -- val )
  [ registers ] m@ [ forth ]
;

: GPIO.init ( -- )
  1 mLED_RED GPIO_ENABLE_REG regSet
  1 mLED_YELLOW GPIO_ENABLE_REG regSet
  1 mLED_GREEN GPIO_ENABLE_REG regSet
;
```

### Registros de activación y desactivación

- `GPIO_OUT_W1TS_REG` — activa bits (Write to Set)
- `GPIO_OUT_W1TC_REG` — desactiva bits (Write to Clear)

```forth
\ Encender todos los LED
7 mLED_RED mLED_YELLOW nip + mLED_GREEN nip + GPIO_OUT_W1TS_REG regSet

\ Apagar todos los LED
7 mLED_RED mLED_YELLOW nip + mLED_GREEN nip + GPIO_OUT_W1TC_REG regSet
```

**Secuencia de encendido/apagado:**
```forth
: GPIO.on.off.sequence { position mask delay -- }
  1 position mask GPIO_OUT_W1TS_REG regSet
  delay ms
  1 position mask GPIO_OUT_W1TC_REG regSet
;
```

**Semáforo alemán con registros:**
```forth
: TRAFFIC.sequence { val position mask delay -- }
  val position mask GPIO_OUT_W1TS_REG regSet
  delay ms
  val position mask GPIO_OUT_W1TC_REG regSet
;

: TRAFFIC.red ( -- ) 1 mLED_RED 2500 TRAFFIC.sequence ;
: TRAFFIC.yellow ( -- ) 1 mLED_YELLOW 1000 TRAFFIC.sequence ;
: TRAFFIC.green ( -- ) 1 mLED_GREEN 3000 TRAFFIC.sequence ;
: TRAFFIC.red-yellow ( -- )
  3 mLED_RED mLED_YELLOW nip + 500 TRAFFIC.sequence
;

: TRAFFIC.german.cycle ( -- )
  TRAFFIC.red
  TRAFFIC.red-yellow
  TRAFFIC.green
  TRAFFIC.yellow
;

: TRAFFIC.loop ( -- )
  begin
    TRAFFIC.german.cycle
    key?
  until
;
```

---

## Interrupciones de hardware con ESP32forth

### Montaje de un pulsador

```forth
17 constant button
button input pinMode

: test ." pinvalue: " button digitalRead . cr ;

interrupts
button gpio_pulldown_en drop
' test button pinchange
forth
```

### Consolidación de software

```forth
17 constant button
0 constant GPIO_PULLUP_ONLY

button input pinMode

: test ." pinvalue: " button digitalRead . cr ;

interrupts
button gpio_pulldown_en drop
button GPIO_INTR_POSEDGE gpio_set_intr_type drop
' test button pinchange
forth
```

**Tipos de interrupción:**
- `GPIO_INTR_ANYEDGE` — ambos flancos
- `GPIO_INTR_NEGEDGE` — flanco descendente
- `GPIO_INTR_POSEDGE` — flanco ascendente
- `GPIO_INTR_DISABLE` — desactivar

> **Nota:** Todos los pines GPIO se pueden usar como interrupción, excepto GPIO6 a GPIO11.

---

## Usando el codificador rotatorio KY-040

### Descripción general

El codificador rotatorio tiene dos terminales de interés:
- **A (DT)** → cambio X
- **B (CLK)** → cambio Y

```json
{
  "type": "image",
  "id": "image-11",
  "page": 168,
  "title": "Codificador rotatorio KY-040",
  "caption": "Módulo KY-040 con pines GND, +, SW, DT, CLK",
  "description": "Fotografía del codificador rotatorio con los 5 pines de conexión.",
  "source": "Foto del autor"
}
```

### Montaje

```json
{
  "type": "diagram",
  "id": "diagram-01",
  "page": 169,
  "title": "Conexión del codificador KY-040 a ESP32",
  "elements": [
    "KY-040 VCC → ESP32 3V3",
    "KY-040 GND → ESP32 GND",
    "KY-040 DT → ESP32 G4",
    "KY-040 CLK → ESP32 G15"
  ],
  "description": "Diagrama de conexión con 4 cables: rojo (3V3), negro (GND), amarillo (G4), verde (G15).",
  "source": "Esquema del autor"
}
```

### Programación

```forth
interrupts

: intG15enable ( -- )
  15 GPIO_INTR_POSEDGE gpio_set_intr_type drop
;

: intG15disable ( -- )
  15 GPIO_INTR_DISABLE gpio_set_intr_type drop
;

: pinsInit ( -- )
  04 input pinmode
  04 gpio_pulldown_en drop
  15 input pinmode
  15 gpio_pulldown_en drop
  intG15enable
;

: test ( -- )
  cr ." PIN: "
  cr ." - G15: " 15 digitalRead .
  cr ." - G04: " 04 digitalRead .
;

pinsInit
' test 15 pinchange
```

### Incrementar y disminuir una variable

```forth
0 value KYvar

: incKYvar ( n -- )
  1 +to KYvar
;

: decKYvar ( n -- )
  -1 +to KYvar
;

: testIncDec ( -- )
  intG15disable
  15 digitalRead if
    04 digitalRead if
      decKYvar
    else
      incKYvar
    then
    cr ." KYvar: " KYvar .
  then
  1000 0 do loop
  intG15enable
;

pinsInit
' testIncDec 15 pinchange
```

---

## Parpadeo de un LED por temporizador

### Comenzando con programación FORTH

**Código C equivalente:**
```c
void setup() {
  pinMode(18, OUTPUT);
}
void loop() {
  digitalWrite(18, HIGH);
  delay(500);
  digitalWrite(18, LOW);
  delay(500);
}
```

**Código FORTH:**
```forth
18 constant myLED

: led.blink ( -- )
  myLED output pinMode
  begin
    HIGH myLED pin
    500 ms
    LOW myLED pin
    500 ms
    key?
  until
;
```

**Factorización:**
```forth
18 constant myLED

: led.on ( -- ) HIGH myLED pin ;
: led.off ( -- ) LOW myLED pin ;
: waiting ( -- ) 500 ms ;

: led.blink ( -- )
  myLED output pinMode
  begin
    led.on waiting
    led.off waiting
    key?
  until
;
```

### Intermitente por TIMER

```forth
18 constant myLED
0 value LED_STATE

: led.on ( -- )
  HIGH dup myLED pin to LED_STATE
;

: led.off ( -- )
  LOW dup myLED pin to LED_STATE
;

timers

: led.toggle ( -- )
  LED_STATE if led.off else led.on then
  0 rerun
;

' led.toggle 500000 0 interval

: led.blink ( -- )
  myLED output pinMode
  led.toggle
;
```

### Interrupciones de hardware y software

- **Hardware:** se activan mediante una acción física en una entrada GPIO
- **Software:** se activan cuando ciertos registros alcanzan valores predefinidos (temporizadores)

### Utilice las palabras interval y rerun

La palabra `interval` acepta tres parámetros:
- `xt` — código de ejecución de la palabra a lanzar
- `usec` — tiempo de espera en microsegundos
- `t` — número de temporizador [0..3]

La palabra `rerun` debe usarse dentro de la definición de la palabra ejecutada por el temporizador.

---

## Temporizador de ama de llaves

### Caso práctico

Un temporizador de luz en un pasillo con pulsador que:
- Una pulsación normal enciende la luz por un minuto
- Una pulsación larga (≥3 segundos) enciende por 10 minutos
- Un pitido corto reconoce la activación del ciclo largo

### Implementación

```forth
18 constant myLIGHTS

60 constant MAX_LIGHT_TIME_NORMAL_CYCLE
600 constant MAX_LIGHT_TIME_EXTENDED_CYCLE

0 value MAX_LIGHT_TIME

timers

: cycle.stop ( -- )
  -1 +to MAX_LIGHT_TIME
  MAX_LIGHT_TIME 0 =
  if
    LOW myLIGHTS pin
  else
    0 rerun
  then
;

' cycle.stop 1000000 0 interval

: cycle.start ( n -- )
  1+ to MAX_LIGHT_TIME
  myLIGHTS output pinMode
;

17 constant button

interrupts

: intPosEdge ( -- )
  button #GPIO_INTR_POSEDGE gpio_set_intr_type drop
;

: intNegEdge ( -- )
  button #GPIO_INTR_NEGEDGE gpio_set_intr_type drop
;

03 constant CYCLE_SHORT
10 constant CYCLE_LONG

variable msTicksPositiveEdge
3000 constant DELAY_LIMIT

: getButton ( -- )
  button gpio_intr_disable drop
  70000 0 do loop \ anti rebond
  button digitalRead 1 =
  if
    ms-ticks msTicksPositiveEdge !
    intNegEdge
  else
    intPosEdge
    ms-ticks msTicksPositiveEdge @ -
    DELAY_LIMIT >
    if
      CYCLE_LONG cr ." BEEP"
    else
      CYCLE_SHORT cr ." ---"
    then
    cycle.start
  then
  button gpio_intr_enable drop
;

button input pinMode
button gpio_pulldown_en drop
' getButton button pinchange
intPosEdge
forth
```

---

## Reloj en tiempo real

### La palabra MS-TICKS

```forth
DEFINED? ms-ticks [IF]
: ms ( n -- )
  ms-ticks >r
  begin
    pause
    ms-ticks r@ - over >=
  until
  rdrop drop
;
[THEN]
```

`MS-TICKS` devuelve el número de milisegundos transcurridos desde el arranque. Se satura a los 49 días aproximadamente.

### Administrar un reloj de software

```forth
0 value currentTime

: RTC.set-time { hh mm ss -- }
  hh 3600 * mm 60 * ss + + 1000 *
  MS-TICKS - to currentTime
;

: RTC.get-time ( -- hh mm ss )
  currentTime MS-TICKS + 1000 / 3600 /mod swap 60 /mod swap
;

: :## ( n -- n' )
  # 6 base ! # decimal [char] : hold
;

: RTC.display-time ( -- )
  currentTime MS-TICKS + 1000 /
  <# :## :## 24 MOD #S #> type
;
```

### Medir el tiempo de ejecución

```forth
: measure: ( exec: -- <word> )
  ms-ticks >r
  ' execute
  ms-ticks r> -
  cr ." execution time: "
  <# # # # [char] . hold #s #> type ." sec." cr
;

measure: words
\ display: execution time: 0.210sec.
```

**Comparación de bucles:**
```forth
: test-loop ( -- ) 1000000 0 do loop ;
measure: test-loop \ execution time: 1.327sec.

: test-for ( -- ) 1000000 for next ;
measure: test-for \ execution time: 0.096sec.

: test-begin ( -- ) 1000000 begin 1- dup 0= until ;
measure: test-begin \ execution time: 0.273sec.
```

**Conclusión:** El bucle `for-next` es casi 14 veces más rápido que `do-loop`.

---

## Programar un analizador de luz

### Panel solar en miniatura

```json
{
  "type": "image",
  "id": "image-12",
  "page": 190,
  "title": "Mini panel solar extraído de lámpara de jardín",
  "caption": "Panel solar de 25mm x 25mm con cables rojo y azul soldados a conectores Dupont",
  "description": "Panel solar pequeño recuperado de una lámpara de jardín averiada.",
  "source": "Foto del autor"
}
```

### Medición de voltaje

- Luz intensa: 14.2 V
- Luz difusa: 5.8 V
- Cubierto: ~0 V

**Divisor de tensión:** 220 Ω y 1 kΩ. Voltaje máximo: 3.2 V.

### Programación

```forth
34 constant SOLAR_CELL

: init-solar-cell ( -- )
  SOLAR_CELL input pinMode
;

: solar-cell-read ( -- n )
  SOLAR_CELL analogRead
;

: solar-cell-loop ( -- )
  init-solar-cell
  begin
    solar-cell-read cr .
    200 ms
    key?
  until
;
```

### Gestión de dispositivo

```forth
17 constant DEVICE_ON \ green LED
16 constant DEVICE_OFF \ red LED

: init-device-state ( -- )
  DEVICE_ON output pinMode
  DEVICE_OFF output pinMode
;

500 value DEVICE_DELAY

: device-activation { trigger -- }
  trigger HIGH digitalwrite
  DEVICE_DELAY ?dup
  if
    ms
    trigger LOW digitalwrite
  then
;

0 value DEVICE_STATE

: enable-device ( -- )
  DEVICE_STATE invert
  if
    DEVICE_OFF LOW digitalWrite
    DEVICE_ON device-activation
    -1 to DEVICE_STATE
  then
;

: disable-device ( -- )
  DEVICE_STATE
  if
    DEVICE_ON LOW digitalWrite
    DEVICE_OFF device-activation
    0 to DEVICE_STATE
  then
;

300 value SOLAR_TRIGGER

: action-light-level ( -- )
  solar-cell-read SOLAR_TRIGGER >=
  if enable-device else disable-device then
;

0 to DEVICE_DELAY
200 to SOLAR_TRIGGER
init-solar-cell
init-device-state

timers

: action ( -- )
  action-light-level
  0 rerun
;

' action 1000000 0 interval
```

---

## Gestión de salidas N/A (Digital/Analógica)

### Conversión D/A con circuito R2R

```json
{
  "type": "diagram",
  "id": "diagram-02",
  "page": 198,
  "title": "Convertidor digital a analógico de 4 bits (R2R)",
  "elements": [
    "Vref", "R", "2R (x4)", "a0", "a1", "a2", "a3",
    "Amplificador operacional", "Vs", "Is"
  ],
  "relationships": [
    "a3 → bit más significativo",
    "a0 → bit menos significativo",
    "Is = I/2 + I/4 + I/8 + I/16 según bits activos"
  ],
  "description": "Circuito R2R con 4 bits de entrada y salida analógica Vs proporcional al valor digital.",
  "source": "Esquema del autor"
}
```

### Conversión D/A con ESP32

ESP32 tiene 2 canales DAC (GPIO25 y GPIO26). Resolución: 8 bits (0-255).

```forth
: BLset ( n -- ) \ establece LED azul
  \ ...
;

: WHset ( n -- ) \ establece LED blanco
  \ ...
;
```

**Aplicaciones:**
- Control de potencia mediante circuito dedicado (variador de motor)
- Generación de señales: sinusoide, cuadrada, triangular
- Conversión de archivos de sonido
- Síntesis de sonido

---

## La pantalla OLED SSD1306

### Especificaciones

- Resolución: 128x32 píxeles (o 128x64)
- Monocromo
- Interfaz I2C (dirección 0x3C típica)
- Bajo consumo

### Organización de la memoria

```json
{
  "type": "diagram",
  "id": "diagram-03",
  "page": 211,
  "title": "Organización de la memoria de la pantalla SSD1306",
  "elements": [
    "128 columnas",
    "8 páginas (128x64) o 4 páginas (128x32)",
    "Cada página = 8 bits de altura",
    "Cada byte = 8 píxeles verticales"
  ],
  "description": "La memoria interna tiene 1 KB de RAM. Para 128x64: 8 páginas. Para 128x32: 4 páginas. Cada columna contiene 8 bits (un byte).",
  "source": "Documentación Adafruit SSD1306"
}
```

### Conexión I2C

```json
{
  "type": "diagram",
  "id": "diagram-04",
  "page": 210,
  "title": "Conexión OLED SSD1306 a ESP32 por I2C",
  "elements": [
    "OLED VCC → ESP32 3V3",
    "OLED GND → ESP32 GND",
    "OLED SDA → ESP32 GPIO21",
    "OLED SCL → ESP32 GPIO22"
  ],
  "description": "4 cables: negro (GND), rojo (VCC), azul (SDA), amarillo (SCL).",
  "source": "Esquema del autor"
}
```

### Organizar el proyecto SSD1306

**main.fs:**
```forth
RECORDFILE /spiffs/main.fs

DEFINED? --oledTest [if] forget --oledTest [then]
create --oledTest

s" /spiffs/config.fs" included
s" /spiffs/oledTools.fs" included

<EOF>
```

**config.fs:**
```forth
RECORDFILE /spiffs/config.fs

\ set oled SSD1306 dimensions
oled
128 to WIDTH
32 to HEIGHT
forth

\ set adress of OLED SSD1306 display 128x32 pixels
$3c constant I2C_SSD1306_ADDRESS

<EOF>
```

**oledTools.fs:**
```forth
RECORDFILE /spiffs/oledTools.fs

oled
: Oled128x32Init
  OledAddr @ 0=
  if
    WIDTH HEIGHT OledReset OledNew
    SSD1306_SWITCHCAPVCC I2C_SSD1306_ADDRESS OledBegin drop
  then
  OledCLS
  1 OledTextsize
  WHITE OledTextc
  0 0 OledSetCursor
  z" *Esp32forth*" OledPrintln OledDisplay
;
forth

<EOF>
```

### Utilice vocabulario OLED

```
OledInit SSD1306_SWITCHCAPVCC SSD1306_EXTERNALVCC WHITE BLACK
OledReset HEIGHT WIDTH OledAddr OledNew OledDelete OledBegin
OledHOME OledCLS OledTextc OledPrintln OledNumln OledNum
OledDisplay OledPrint OledInvert OledTextsize OledSetCursor
OledPixel OledDrawL OledFastHLine OledFastVLine OledCirc
OledCircF OledRect OledRectF OledRectR OledRectRF oled-builtins
```

### Inicialización I2C

```forth
$3c constant I2C_SSD1306_ADDRESS

OledAddr @ 0=
if
  WIDTH HEIGHT OledReset OledNew
  SSD1306_SWITCHCAPVCC I2C_SSD1306_ADDRESS OledBegin drop
then
```

### Comandos de texto

| Palabra | Acción |
|---|---|
| `OledCLS` | Borra pantalla |
| `OledDisplay` | Transmite comandos |
| `OledHOME` | Cursor a (0,0) |
| `OledInvert` | Invierte pantalla |
| `OledNum` | Muestra número |
| `OledNumln` | Número + nueva línea |
| `OledPrint` | Muestra cadena z |
| `OledPrintln` | Cadena z + nueva línea |
| `OledTextc` | Color del texto |
| `OledSetCursor` | Posición del cursor |
| `OledTextsize` | Tamaño del texto [1..3] |

### Comandos gráficos

| Palabra | Acción |
|---|---|
| `OledCirc` | Círculo hueco |
| `OledCircF` | Círculo relleno |
| `OledDrawL` | Línea |
| `OledFastHLine` | Línea horizontal |
| `OledFastVLine` | Línea vertical |
| `OledPixel` | Píxel |
| `OledRect` | Rectángulo hueco |
| `OledRectF` | Rectángulo relleno |
| `OledRectR` | Rectángulo redondeado hueco |
| `OledRectRF` | Rectángulo redondeado relleno |

### Ampliar vocabulario OLED

```forth
RECORDFILE /spiffs/extendOledVoc.fs

oled definitions
: OledTriangle { x0 y0 x1 y1 x2 y2 color -- }
  x0 y0 x1 y1 color OledDrawL
  x1 y1 x2 y2 color OledDrawL
  x2 y2 x0 y0 color OledDrawL
;
forth definitions

<EOF>
```

---

## TEMPVS FVGIT

Proyecto que muestra la hora en números romanos en una pantalla OLED.

### Archivos del proyecto

- `autoexec.fs` — cargado al iniciar
- `clepsydra.fs` — conversión a números romanos
- `config.fs` — configuración global
- `main.fs` — carga los demás archivos
- `oledTools.fs` — completa vocabulario OLED
- `RTClock.fs` — reloj en tiempo real
- `strings.fs` — procesamiento de cadenas

### Conversión a números romanos

```forth
: tempusTo$ { HH MM -- }
  HH 0 = MM 0= AND if
    60 to MM
    23 to HH
  THEN
  HH 0 > MM 0= AND if
    60 to MM
    -1 +to HH
  then
  HH 0 <= if
    24 to HH
  then
  HH roman tempus $!
  [char] : tempus c+$!
  MM roman tempus append$
  tempus
;
```

**Ejemplos:**
```
23 59 .tempus → XXIII:LIX
0 0 .tempus → XXIII:LX
0 1 .tempus → XXIV:I
1 0 .tempus → XXIV:LX
1 1 .tempus → I:I
```

### Bucle principal

```forth
oled
: start ( HH MM -- )
  0 RTC.setTime
  Oled128x32Init
  1 OledTextsize
  WHITE OledTextc
  begin
    OledCLS OledDisplay
    16 20 OledSetCursor
    RTC.getTime drop tempusTo$ s>z OledPrintln OledDisplay
    1000 ms
    key?
  until
;
forth
```

---

## Agregue la biblioteca SPI

### Contenido de spi.h

```c
#include <SPI.h>
#define OPTIONAL_SPI_VOCABULARY V(spi)
#define OPTIONAL_SPI_SUPPORT \
  XV(internals, "spi-source", SPI_SOURCE, \
    PUSH spi_source; PUSH sizeof(spi_source) - 1) \
  XV(spi, "SPI.begin", SPI_BEGIN, SPI.begin((int8_t) n3, (int8_t) n2, (int8_t) n1, (int8_t) n0); DROPn(4)) \
  XV(spi, "SPI.end", SPI_END, SPI.end();) \
  XV(spi, "SPI.setHwCs", SPI_SETHWCS, SPI.setHwCs((boolean) n0); DROP) \
  XV(spi, "SPI.setBitOrder", SPI_SETBITORDER, SPI.setBitOrder((uint8_t) n0); DROP) \
  XV(spi, "SPI.setDataMode", SPI_SETDATAMODE, SPI.setDataMode((uint8_t) n0); DROP) \
  XV(spi, "SPI.setFrequency", SPI_SETFREQUENCY, SPI.setFrequency((uint32_t) n0); DROP) \
  XV(spi, "SPI.setClockDivider", SPI_SETCLOCKDIVIDER, SPI.setClockDivider((uint32_t) n0); DROP) \
  XV(spi, "SPI.getClockDivider", SPI_GETCLOCKDIVIDER, PUSH SPI.getClockDivider();) \
  XV(spi, "SPI.transfer", SPI_TRANSFER, SPI.transfer((uint8_t *) n1, (uint32_t) n0); DROPn(2)) \
  XV(spi, "SPI.transfer8", SPI_TRANSFER_8, PUSH (uint8_t) SPI.transfer((uint8_t) n0); NIP) \
  XV(spi, "SPI.transfer16", SPI_TRANSFER_16, PUSH (uint16_t) SPI.transfer16((uint16_t) n0); NIP) \
  XV(spi, "SPI.transfer32", SPI_TRANSFER_32, PUSH (uint32_t) SPI.transfer32((uint32_t) n0); NIP) \
  XV(spi, "SPI.transferBytes", SPI_TRANSFER_BYTES, SPI.transferBytes((const uint8_t *) n2, (uint8_t *) n1, (uint32_t) n0); DROPn(3)) \
  XV(spi, "SPI.transferBits", SPI_TRANSFER_BITES, SPI.transferBits((uint32_t) n2, (uint32_t *) n1, (uint8_t) n0); DROPn(3)) \
  XV(spi, "SPI.write", SPI_WRITE, SPI.write((uint8_t) n0); DROP) \
  XV(spi, "SPI.write16", SPI_WRITE16, SPI.write16((uint16_t) n0); DROP) \
  XV(spi, "SPI.write32", SPI_WRITE32, SPI.write32((uint32_t) n0); DROP) \
  XV(spi, "SPI.writeBytes", SPI_WRITE_BYTES, SPI.writeBytes((const uint8_t *) n1, (uint32_t) n0); DROPn(2)) \
  XV(spi, "SPI.writePixels", SPI_WRITE_PIXELS, SPI.writePixels((const void *) n1, (uint32_t) n0); DROPn(2)) \
  XV(spi, "SPI.writePattern", SPI_WRITE_PATTERN, SPI.writePattern((const uint8_t *) n2, (uint8_t) n1, (uint32_t) n0); DROPn(3))

const char spi_source[] = R"""(
vocabulary spi spi definitions
transfer spi-builtins
forth definitions
)""";
```

### Modificaciones en ESP32forth.ino

**Primera modificación:**
```c
#define VOCABULARY_LIST \
  V(forth) V(internals) \
  V(rtos) V(SPIFFS) V(serial) V(SD) V(SD_MMC) V(ESP) \
  V(ledc) V(Wire) V(WiFi) V(sockets) \
  OPTIONAL_CAMERA_VOCABULARY \
  OPTIONAL_BLUETOOTH_VOCABULARY \
  OPTIONAL_INTERRUPTS_VOCABULARIES \
  OPTIONAL_OLED_VOCABULARY \
  OPTIONAL_SPI_VOCABULARY \
  OPTIONAL_RMT_VOCABULARY \
  OPTIONAL_SPI_FLASH_VOCABULARY \
  USER_VOCABULARIES
```

**Segunda modificación:**
```c
// Hook to pull in optional SPI support.
#if __has_include("spi.h")
#include "spi.h"
#else
#define OPTIONAL_SPI_VOCABULARY
#define OPTIONAL_SPI_SUPPORT
#endif
```

**Tercera modificación:**
```c
#define EXTERNAL_OPTIONAL_MODULE_SUPPORT \
  OPTIONAL_ASSEMBLERS_SUPPORT \
  OPTIONAL_CAMERA_SUPPORT \
  OPTIONAL_INTERRUPTS_SUPPORT \
  OPTIONAL_OLED_SUPPORT \
  OPTIONAL_SPI_SUPPORT \
  OPTIONAL_RMT_SUPPORT \
  OPTIONAL_SERIAL_BLUETOOTH_SUPPORT \
  OPTIONAL_SPI_FLASH_SUPPORT
```

**Cuarta modificación:**
```c
internals DEFINED? oled-source [IF]
  oled-source evaluate
[THEN] forth
internals DEFINED? spi-source [IF]
  spi-source evaluate
[THEN] forth
```

### Comunicarse con MAX7219

```forth
\ define VSPI pins
19 constant VSPI_MISO
23 constant VSPI_MOSI
18 constant VSPI_SCLK
05 constant VSPI_CS

\ define SPI port frequency
4000000 constant SPI_FREQ

\ select SPI vocabulary
only FORTH SPI also

\ initialize SPI port
: init.VSPI ( -- )
  VSPI_CS OUTPUT pinMode
  VSPI_SCLK VSPI_MISO VSPI_MOSI VSPI_CS SPI.begin
  SPI_FREQ SPI.setFrequency
;
```

```json
{
  "type": "table",
  "id": "table-02",
  "page": 227,
  "title": "Conexión MAX7219 a ESP32",
  "headers": ["MAX7219", "ESP32"],
  "rows": [
    ["DIN", "VSPI_MOSI (GPIO23)"],
    ["CS", "VSPI_CS (GPIO5)"],
    ["CLK", "VSPI_SCLK (GPIO18)"],
    ["VCC", "Fuente externa"],
    ["GND", "GND común"]
  ],
  "notes": "Los conectores VCC y GND se conectan a fuente externa. GND compartido con ESP32.",
  "source": "Manual MAX7219"
}
```

---

## Instalación del cliente HTTP

### Modificaciones en ESP32forth.ino

**Primera parte:**
```c
#define ENABLE_SD_SUPPORT
#define ENABLE_SPI_FLASH_SUPPORT
#define ENABLE_HTTP_SUPPORT
// #define ENABLE_HTTPS_SUPPORT
```

**Segunda parte:**
```c
#define VOCABULARY_LIST \
  V(forth) V(internals) \
  V(rtos) V(SPIFFS) V(serial) V(SD) V(SD_MMC) V(ESP) \
  V(ledc) V(http) V(Wire) V(WiFi) V(bluetooth) V(sockets) V(oled) \
  V(rmt) V(interrupts) V(spi_flash) V(camera) V(timers)
```

**Tercera parte:**
```c
OPTIONAL_RMT_SUPPORT \
OPTIONAL_OLED_SUPPORT \
OPTIONAL_SPI_FLASH_SUPPORT \
OPTIONAL_HTTP_SUPPORT \
FLOATING_POINT_LIST

#ifndef ENABLE_HTTP_SUPPORT
#define OPTIONAL_HTTP_SUPPORT
#else
#include <HTTPClient.h>
HTTPClient http;

#define OPTIONAL_HTTP_SUPPORT \
  XV(http, "HTTP.begin", HTTP_BEGIN, tos = http.begin(c0)) \
  XV(http, "HTTP.doGet", HTTP_DOGET, PUSH http.GET()) \
  XV(http, "HTTP.getPayload", HTTP_GETPL, String s = http.getString(); \
    memcpy((void *) n1, (void *) s.c_str(), n0); DROPn(2)) \
  XV(http, "HTTP.end", HTTP_END, http.end())
#endif
```

**Cuarta parte:**
```c
vocabulary ledc ledc definitions
transfer ledc-builtins
forth definitions
vocabulary http http definitions
transfer http-builtins
forth definitions
vocabulary Serial Serial definitions
transfer Serial-builtins
forth definitions
```

### Prueba de cliente HTTP

```forth
WiFi

: myWiFiConnect
  z" mySSID"
  z" myWiFiCode"
  login
;

Forth

create httpBuffer 700 allot
httpBuffer 700 erase

HTTP

: run
  cr
  z" http://ws.arduino-forth.com/" HTTP.begin
  if
    HTTP.doGet dup ." Get results: " . cr 0 >
    if
      httpBuffer 700 HTTP.getPayload
      httpBuffer z>s dup . cr type
    then
  then
  HTTP.end
;

myWiFiConnect
run
```

**Resultado:**
```
Get results: 200
8
It's OK
```

---

## Recuperar la hora desde un servidor WEB

### Script del servidor (gettime.php)

```php
<?php
echo date('H i s')." RTC.set-time";
```

**Salida:**
```
15 25 30 RTC.set-time
```

### Código FORTH

```forth
WiFi

: myWiFiConnect
  z" mySSID"
  z" myWiFiCode"
  login
;

Forth

0 value currentTime

: RTC.set-time { hh mm ss -- }
  hh 3600 *
  mm 60 *
  ss + + 1000 *
  MS-TICKS - to currentTime
;

: :## ( n -- n' )
  # 6 base ! # decimal [char] : hold
;

: RTC.display-time ( -- )
  currentTime MS-TICKS + 1000 /
  <# :## :## 24 mod #S #> type
;

700 constant bufferSize
create httpBuffer
bufferSize allot

0 buffer 700 erase

HTTP

: getTime
  cr
  z" http://ws.arduino-forth.com/gettime.php" HTTP.begin
  if
    HTTP.doGet
    if
      httpBuffer bufferSize HTTP.getPayload
      httpBuffer z>s evaluate
    then
  then
  HTTP.end
;

myWiFiConnect
getTime
RTC.display-time
```

**Resultado:**
```
15:33:09
```

---

## Transmisión por GET a un servidor WEB

### Parámetros en una URL

```
http://my-website.com/index.php?temp=32.7
```

- `?` marca el inicio de parámetros
- `&` separa múltiples parámetros:
```
http://my-website.com/index.php?log=myLog&pwd=myPassWd&temp=32.7
```

### Script PHP de registro (record.php)

```php
<?php
// echo "<pre>"; var_dump($_GET);
$handle = fopen("datasRecords.csv","a");
$myDatas = array(
  'currentDateTime' => date("Y-m-d H:i:s"),
  'currentLogin' => $_GET['log'],
  'currentTemp' => $_GET['temp'],
);
fwrite($handle, implode(';', $myDatas)."\n");
fclose($handle);
echo "DATAs recorded";
```

### Protección de acceso

```php
<?php
$myAuths = array(
  'pooltemp' => 'pool2022',
  'housetemp' => 'house2022',
);

function testAuths($auths){
  if(array_key_exists($_GET['log'], $auths) &&
     $auths[$_GET['log']]==$_GET['pwd']) {
    return true;
  }
  return false;
}

if (testAuths($myAuths)) {
  $handle = fopen("datasRecords.csv","a");
  $myDatas = array(
    'currentDateTime' => date("Y-m-d H:i:s"),
    'currentLogin' => $_GET['log'],
    'currentTemp' => $_GET['temp'],
  );
  fwrite($handle, implode(';', $myDatas)."\n");
  fclose($handle);
  echo "DATAs recorded";
} else {
  echo "AUTH failed";
}
```

### Código FORTH

```forth
256 string myUrl

: addTemp ( strAddrLen -- )
  s" &temp=" myUrl append$
  myUrl append$
;

: addHygr ( strAddrLen -- )
  s" &hygr=" myUrl append$
  myUrl append$
;

: sendData ( strHygr strTemp -- )
  s" http://ws.arduino-forth.com/record.php?log=myLog&pwd=myPassWd" myUrl $!
  addTemp
  addHygr
  cr myUrl type
  myUrl s>z HTTP.begin
  if
    HTTP.doGet dup 200 =
    if drop
      httpBuffer bufferSize HTTP.getPayload
      httpBuffer z>s type
    else
      cr ." CNX ERR: " .
    then
  then
  HTTP.end
;

myWiFiConnect
s" 64.2" \ hygrometry
s" 31.23" \ temperature
sendData
```

---

## Síntesis de sonido con ESP32Forth

### Montaje

```json
{
  "type": "diagram",
  "id": "diagram-05",
  "page": 245,
  "title": "Conexión de altavoz a ESP32",
  "elements": [
    "ESP32 GPIO25 → base de transistor PN2222A",
    "Transistor → altavoz",
    "Altavoz → VCC"
  ],
  "description": "Altavoz conectado a través de transistor PN2222A como adaptador de impedancia. GPIO25 (DAC) o GPIO26.",
  "source": "Esquema del autor"
}
```

### Inicialización

```forth
0 constant CHANNEL0
25 constant BUZZER

ledc

: initTones ( -- )
  BUZZER CHANNEL0 ledcAttachPin
;
```

### Generación de tono

```forth
CHANNEL0 440000 ledcWriteTone drop \ LA 440 Hz
```

### Tabla de frecuencias

```forth
create NOTES
\ octave -1
15350 , 17330 , 18360 , 19450 , 20600 , 21830 ,
23130 , 24500 , 25960 , 27500 , 29140 , 30870 ,
\ octave 0
32700 , 34650 , 36710 , 38890 , 41200 , 43650 ,
46250 , 49000 , 51910 , 55000 , 58270 , 61740 ,
\ octave 1
65410 , 69300 , 73420 , 77780 , 82410 , 87310 ,
92500 , 98000 , 103830 , 110000 , 116540 , 123470 ,
\ ... hasta octava 8
```

### Recuperar frecuencia

```forth
3 value OCTAVE

: set.octave ( n[-1..8] )
  to OCTAVE
;

: get.note ( n[1..12] -- )
  1- OCTAVE 1+ 12 * + cell *
  NOTES + @
;

: OCT6 ( -- ) 6 set.octave ;
: OCT5 ( -- ) 5 set.octave ;
: OCT4 ( -- ) 4 set.octave ;
: OCT3 ( -- ) 3 set.octave ;
: OCT2 ( -- ) 2 set.octave ;
: OCT1 ( -- ) 1 set.octave ;
```

### Duración de notas

```forth
1600 constant WHOLE-NOTE-DURATION
WHOLE-NOTE-DURATION value duration

vocabulary music
music definitions
music also

: o ( -- ) WHOLE-NOTE-DURATION to duration ;
: o| ( -- ) WHOLE-NOTE-DURATION 2/ to duration ;
: .| ( -- ) WHOLE-NOTE-DURATION 2/ 2/ to duration ;
: .|' ( -- ) WHOLE-NOTE-DURATION 2/ 2/ 2/ to duration ;
: .|" ( -- ) WHOLE-NOTE-DURATION 2/ 2/ 2/ 2/ to duration ;
```

### Sustain

```forth
90 value SUSTAIN

ledc

: sustain.note ( -- )
  duration SUSTAIN 100 */ ms
  CHANNEL0 0 ledcWriteTone drop
  duration 100 SUSTAIN - 100 */ ms
;
```

### Creando notas

```forth
: create-note
  create ( position -- )
  ,
  does>
  @ 1- get.note
  CHANNEL0 swap ledcWriteTone drop
  sustain.note
;

1 create-note C
2 create-note C#
3 create-note D
4 create-note D#
5 create-note E
6 create-note F
7 create-note F#
8 create-note G
9 create-note G#
10 create-note A
11 create-note A#
12 create-note B

1 create-note DO
2 create-note DO#
3 create-note RE
4 create-note RE#
5 create-note MI
6 create-note FA
7 create-note FA#
8 create-note SOL
9 create-note SOL#
10 create-note LA
11 create-note LA#
12 create-note SI

: SIL ( -- )
  CHANNEL0 0 ledcWriteTone drop
  duration ms
;
```

### El vuelo del abejorro

```forth
: 1stLine ( -- )
  .|"
  OCT5 MI RE# RE DO# RE DO# DO OCT4 SI
  OCT5 DO OCT4 SI LA# LA SOL# SOL FA# FA
  MI RE# RE DO# RE DO# DO OCT3 SI
;

: 2ndLine ( -- )
  .|"
  OCT4 DO OCT3 SI FA# FA SOL# SOL FA# FA
  MI RE# RE DO# RE DO DO# OCT2 SI OCT3
  MI RE# RE DO# RE DO DO OCT2 SI OCT3
  MI RE# RE DO# DO FA FA RE#
;

: 3rdLine ( -- )
  .|"
  MI RE# RE DO# DO DO# RE RE#
  MI RE# RE DO# DO FA FA RE#
  MI RE# RE DO# DO DO# RE RE#
  MI RE# RE DO# RE DO DO# OCT2 SI OCT3
;

: flightBumbleBee ( -- )
  initTones
  1stLine
  2ndLine
  3rdLine
;

flightBumbleBee
```

---

## Programa en ensamblador XTENSA

### Preámbulo

El ensamblador es la capa de más bajo nivel. Se programa en ensamblador cuando:
- No existe otra solución para acceder a funcionalidades del procesador
- Se necesita máximo rendimiento
- Es un desafío intelectual
- Ningún lenguaje evolucionado puede hacer todo

### Compilar el ensamblador XTENSA

Desde ESP32forth 7.0.7.15:
1. Copiar `assemblers.h` de `optional/` a la carpeta raíz
2. Compilar y cargar
3. Acceder con `xtensa-assembler`

### Programación

```forth
code my2*
  a1 32 ENTRY,
  a8 a2 0 L32I.N,
  a8 a8 1 SLLI,
  a8 a2 0 S32I.N,
  RETW.N,
end-code

3 my2* . \ muestra 6
21 my2* . \ muestra 42
```

### Resumen de instrucciones básicas

| Categoría | Instrucciones |
|---|---|
| Carga | L8UI, L16SI, L16UI, L32I, L32R |
| Almacenamiento | S8I, S16I, S32I |
| Orden de memoria | MEMW, EXTW |
| Saltos | CALL0, CALLX0, RET, J, JX |
| Ramificación condicional | BALL, BNALL, BANY, BNONE, BBC, BBCI, BBS, BBSI, BEQ, BEQI, BEQZ, BNE, BNEI, BNEZ, BGE, BGEI, BGEU, BGEUI, BGEZ, BLT, BLTI, BLTU, BLTUI, BLTZ |
| Cambio | MOVI, MOVEQZ, MOVGEZ, MOVLTZ, MOVNEZ |
| Aritmética | ADDMI, ADD, ADDX2, ADDX4, ADDX8, SUB, SUBX2, SUBX4, SUBX8, NEG, ABS |
| Lógica binaria | AND, OR, XOR |
| Desplazamiento | EXTUI, SRLI, SRAI, SLLI, SRC, SLL, SRL, SRA, SSL, SSR, SSAI, SSA8B, SSA8L |
| Control | RSR, WSR, XSR, RUR, WUR, ISYNC, RSYNC, ESYNC, DSYNC, NOP |

### Desensamblador

```forth
my2* cell+ @ 20 disasm
\ display:
\ 1074338656 -- a1 32 ENTRY, -- 004136
\ 1074338659 -- a8 a2 0 L32I.N, -- 0288
\ 1074338661 -- a8 a8 1 SLLI, -- 1188F0
\ 1074338664 -- a8 a2 0 S32I.N, -- 0289
\ 1074338666 -- RETW.N, -- F01D
```

### Pila FORTH en ensamblador

El registro `a2` contiene el puntero de pila FORTH. Cada valor apilado incrementa el puntero en 4 unidades.

```forth
code mySP@
  a1 32 ENTRY,
  a8 a2 MOV.N,
  a2 a2 4 ADDI,
  a8 a2 0 S32I.N,
  RETW.N,
end-code
```

### Macros

```forth
asm definitions
: macro:
  :
;
xtensa definitions

macro: sp++,
  a2 a2 4 ADDI,
;

macro: arPUSH, { ar -- }
  sp++,
  ar a2 0 S32I.N,
;

macro: sp--,
  a2 a2 -4 ADDI,
;

macro: arPOP, { ar -- }
  ar a2 0 L32I.N,
  sp--,
;

forth definitions
asm xtensa

code mySWAP
  a1 32 ENTRY,
  a9 arPOP,
  a8 arPOP,
  a9 arPUSH,
  a8 arPUSH,
  RETW.N,
end-code

17 24 mySWAP . . \ muestra 17 24
```

### Ejemplo: /MOD

```forth
code my/MOD ( n1 n2 -- rem quot )
  a1 32 ENTRY,
  a7 arPOP, \ diviseur dans a7
  a8 arPOP, \ valeur à diviser dans a8
  a7 a8 a9 REMS, \ a9 = a8 MOD a7
  a9 arPUSH,
  a7 a8 a9 QUOS, \ a9 = a8 / a7
  a9 arPUSH,
  RETW.N,
end-code

5 2 my/MOD . . \ muestra 2 1
```

### Eficiencia

```forth
: test1 1000000 for 5 2 /MOD drop drop next ;
: test2 1000000 for 5 2 my/MOD drop drop next ;

measure: test1 \ execution time: 0.856sec.
measure: test2 \ execution time: 0.600sec.
```

### Lazos en ensamblador

```forth
: For, { as n -- }
  as n MOVI,
  as 0 LOOP,
  chere 1- to LOOP_OFFSET
;

: Next, ( -- )
  chere LOOP_OFFSET - 2 -
  LOOP_OFFSET [ internals ] ca! [ asm xtensa ]
;

code myLOOP ( n -- n' )
  a1 32 ENTRY,
  a8 1 MOVI,
  a9 4 For,
  a8 a8 1 ADDI,
  a8 arPUSH,
  Next,
  RETW.N,
end-code
```

### Ramificación

```forth
: If, ( -- BRANCH_OFFSET )
  chere 1-
;

: Then, { BRANCH_OFFSET -- }
  chere BRANCH_OFFSET - 2 -
  BRANCH_OFFSET [ internals ] ca! [ asm xtensa ]
;

: <, ( as at -- )
  0 BGE,
;

code my< ( n1 n2 -- fl )
  a1 32 ENTRY,
  a8 arPOP,
  a9 arPOP,
  a7 0 MOVI,
  a8 a9 <, If,
  a7 1 MOVI,
  Then,
  a7 arPUSH,
  RETW.N,
end-code

10 20 my< . \ muestra 1
20 20 my< . \ muestra 0
```

---

## Definición y manipulación de registros

### Definición de registros

```forth
$3FF48898 constant SENS_SAR_DAC_CTRL1_REG

\ O mejor:
: defREG:
  create ( addr1 -- )
  ,
  does> ( -- regAddr )
  @
;

$3FF48898 defREG: SENS_SAR_DAC_CTRL1_REG
```

### Visualizar contenido de registro

```forth
: .reg ( reg -- )
  base @ >r
  binary
  @ <#
  4 for
    aft
    8 for
      aft # then
    next
    bl hold
  then
  next
  #>
  cr space ." 33222222 22221111 11111100 00000000"
  cr space ." 10987654 32109876 54321098 76543210"
  cr type
  r> base !
;

SENS_SAR_DAC_CTRL1_REG .reg
\ display:
\ 33222222 22221111 11111100 00000000
\ 10987654 32109876 54321098 76543210
\ 00000000 00000000 00000000 00000000
```

### Manejo de bits

```forth
registers
1 25 $02000000 SENS_SAR_DAC_CTRL1_REG m!
SENS_SAR_DAC_CTRL1_REG .reg
\ display:
\ 00000010 00000000 00000000 00000000
```

### Definición de máscaras

```forth
: defMASK:
  create ( mask0 position -- )
  dup ,
  lshift ,
  does> ( -- position mask1 )
  dup @
  swap cell + @
;

1 25 defMASK: mSENS_DAC_CLK_INV

1 mSENS_DAC_CLK_INV SENS_SAR_DAC_CTRL1_REG m!
0 mSENS_DAC_CLK_INV SENS_SAR_DAC_CTRL1_REG m!
```

### Cambiar de C a FORTH

**C:**
```c
SET_PERI_REG_MASK(SENS_SAR_DAC_CTRL2_REG, SENS_DAC_CW_EN1_M);
```

**FORTH:**
```forth
$3FF4889c defREG: SENS_SAR_DAC_CTRL2_REG
1 24 defMASK: mSENS_DAC_CW_EN1
1 25 defMASK: mSENS_DAC_CW_EN2
```

---

## El generador de números aleatorios

### Característica

El generador de números aleatorios de ESP32 genera **números aleatorios verdaderos** basados en ruido térmico y desfase de reloj asíncrono.

### Registro

```forth
$3FF75144 constant RNG_DATA_REG

: rnd ( -- x )
  RNG_DATA_REG L@
;

: random ( n -- 0..n-1 )
  rnd swap mod
;
```

### Función RND en ensamblador XTENSA

```forth
forth definitions
asm xtensa

$3FF75144 constant RNG_DATA_REG

code myRND ( -- [addr] )
  a1 32 ENTRY,
  a8 RNG_DATA_REG L32R,
  a9 a8 0 L32I.N,
  a9 arPUSH,
  RETW.N,
end-code
```

---

## El sistema de transmisión LoRa

### Características

- **Tecnología:** LoRa (Long Range)
- **Alcance:** varios kilómetros
- **Consumo:** muy bajo (43 mA en TX, 16.5 mA en RX, 0.5 mA en SLEEP)
- **Banda:** estrecha
- **Topología:** punto a punto
- **Suscripción:** ninguna

### Módulo REYAX RYLR890

- Precio: ~15 €
- Peso: 7 g
- Alimentación: 3.3 V
- Comunicación: UART (comandos AT)
- Frecuencia: 862-1020 MHz
- Seguridad: AES-128

### Cableado

```json
{
  "type": "diagram",
  "id": "diagram-06",
  "page": 278,
  "title": "Conexión del transmisor LoRa a ESP32",
  "elements": [
    "LoRa VCC → ESP32 3V3",
    "LoRa GND → ESP32 GND",
    "LoRa RXD → ESP32 GPIO17 (TX2)",
    "LoRa TXD → ESP32 GPIO16 (RX2)"
  ],
  "description": "Conexión por UART2. Verificar posición de pines G16 y G17 según versión de tarjeta.",
  "source": "Esquema del autor"
}
```

### Comandos AT

| Comando | Descripción |
|---|---|
| `AT` | Test de disponibilidad |
| `AT+ADDRESS=<addr>` | Dirección del módulo (0-65535) |
| `AT+NETWORKID=<id>` | ID de red (0-16) |
| `AT+BAND=<freq>` | Frecuencia RF en Hz |
| `AT+CPIN=<pwd>` | Contraseña AES-128 (32 chars) |
| `AT+CRFOP=<power>` | Potencia de salida (0-15) |
| `AT+FACTORY` | Reset a valores de fábrica |
| `AT+IPR=<baud>` | Velocidad UART |
| `AT+MODE=<mode>` | Modo (0=TX/RX, 1=SLEEP) |
| `AT+PARAMETER=<SF>,<BW>,<CR>,<Preamble>` | Parámetros RF |
| `AT+RESET` | Reiniciar |
| `AT+SEND=<addr>,<len>,<data>` | Enviar datos |
| `AT+VER` | Versión de firmware |

### Códigos de error

| Código | Descripción |
|---|---|
| +ERR=1 | No hay "enter" o $0D $0A al final del comando AT |
| +ERR=2 | El encabezado del comando AT no es "AT" |
| +ERR=3 | No hay símbolo "=" en el comando AT |
| +ERR=4 | Comando desconocido |
| +ERR=10 | TX llega a tiempo |
| +ERR=11 | RX superado |
| +ERR=12 | Error CRC |
| +ERR=13 | Datos TX de más de 240 bytes |
| +ERR=15 | Error desconocido |

### Configuración

```forth
: crlf ( -- )
  $0d emit
  $0a emit
;

: ATaddress ( addr len -- )
  ." AT+ADDRESS="
  type crlf
;

: ATband ( addr len -- )
  ." AT+BAND="
  type crlf
;

: ATcpin ( addr len -- )
  ." AT+CPIN="
  type crlf
;

: ATcrfop ( addr len -- )
  ." AT+CRFOP="
  type crlf
;

: ATfactory ( -- )
  ." AT+FACTORY"
  crlf
;

: ATmode ( addr len -- )
  ." AT+MODE"
  type crlf
;

: ATnetworkid ( addr len -- )
  ." AT+NETWORKID"
  type crlf
;

: ATparameter ( addr len -- )
  ." AT+PARAMETER="
  type crlf
;

: ATreset ( -- )
  ." AT+RESET"
  crlf
;

: ATver ( -- )
  ." AT+VER"
  crlf
;
```

### Vectorización de emisiones

```forth
: serial2-type ( a n -- )
  Serial2.write drop
;

: typeToLoRa ( -- )
  0 echo !
  [' ] serial2-type is type
;

: typeToTerm ( -- )
  [' ] default-type is type
  -1 echo !
;
```

### Listado completo

```forth
create $crlf
  $0d c, $0a c,

: crlf ( -- )
  $crlf 2 type
;

: ATaddress ( addr len -- )
  ." AT+ADDRESS="
  type crlf
;

: ATband ( addr len -- )
  s" AT+BAND=" type
  type crlf
;

115200 value #SERIAL2_RATE

128 string LoRaRX

Serial

: Serial2.init ( -- )
  #SERIAL2_RATE Serial2.begin
;

: LoRaInput ( -- n )
  Serial2.available if
    LoRaRX maxlen$ nip
    Serial2.readBytes
    LoRaRX drop cell - !
  else
    0 LoRaRX drop cell - !
  then
;

: rx.
  LoRaINPUT
  loRaRX type
;
```

### Configuración de transmisores

```forth
55 constant LoRaBOSS
39 constant LoRaSLAV1
40 constant LoRaSLAV2

: emptyRX ( -- )
  LoRaINPUT
;

: SETband ( -- )
  emptyRX
  typeToLoRa
  s" 868500000" ATband
  typeToTerm
;

: SETaddress ( n -- )
  emptyRX
  typeToLoRa
  str ATband
  typeToTerm
;
```

### Comunicación entre transmisores

```forth
: ATsend { addr len address -- }
  ." AT+SEND="
  address .n [char] , emit
  len .n [char] , emit
  addr len type crlf
;

: toSLAV2 ( addr len -- )
  emptyRX
  typeToLoRa
  LoRaSLAV2 ATsend
  typeToTerm
;

: toSLAV1 ( addr len -- )
  emptyRX
  typeToLoRa
  LoRaSLAV1 ATsend
  typeToTerm
;

: REDhigh ( -- ) s" LEDred high" toSLAV1 ;
: REDlow ( -- ) s" LEDred low" toSLAV1 ;
: YELLOWhigh ( -- ) s" ledYELLOW high" toSLAV1 ;
: YELLOWlow ( -- ) s" ledYELLOW low" toSLAV1 ;
: GREENhigh ( -- ) s" ledGREEN high" toSLAV1 ;
: GREENlow ( -- ) s" ledGREEN low" toSLAV1 ;
```

### Recepción y ejecución

```forth
: RXinterface ( -- )
  RCVdata ?dup if
    evaluate
  else
    2drop
  then
;

Serial

: LoRaLoop ( -- )
  begin
    Serial2.available
    if
      100 ms
      LoRaRX maxlen$ nip
      Serial2.readBytes
      LoRaRX drop cell - !
      RXdecode
      RXinterface
    then
    pause
  again
;

' LoRaLoop 100 100 task my-loop
my-loop start-task

: mainInit ( -- )
  cr ." Starting SLAV1 LoRa" cr
  LEDinit
  #SERIAL2_RATE Serial2.begin
  my-loop start-task
;

startup: mainInit
```

---

## Interfaz WEB sencilla para ESP32Forth

**Autor:** Václav POSSELT

### Estructura básica

```forth
: runpage
  begin
    handleClient
    if serve-page 100 ms then
    500 ms
  again
;
```

### Servidor de página

```forth
: serve-page ( -- )
  path s" /" str= if
    htmlpagesend exit
  then
  path s" /26/on" str= if
    cr ." ACTION for /26/on " cr
    0 to GPIO26 htmlpagesend exit
  then
  path s" /26/off" str= if
    cr ." ACTION for /26/off " cr
    1 to GPIO26 htmlpagesend exit
  then
  path s" /27/on" str= if
    cr ." ACTION for /27/on " cr
    0 to GPIO27 htmlpagesend exit
  then
  path s" /27/off" str= if
    cr ." ACTION for /27/off " cr
    1 to GPIO27 htmlpagesend exit
  then
  path respond
  htmlpagesend exit
;
```

### Envío de página HTML

```forth
: htmlpagesend
  s" text/html" ok-response
  htmlpage
  webcontent send
;
```

```json
{
  "type": "image",
  "id": "image-13",
  "page": 310,
  "title": "Página web generada por ESP32forth",
  "caption": "Interfaz web embebida con estado GPIO, botones de control y formularios",
  "description": "Captura de navegador mostrando página con texto de estado GPIO26, botones rojo/verde para GPIO26 y GPIO27, y formulario con campos de fecha/hora.",
  "source": "Captura de pantalla del autor"
}
```

---

## Contenido detallado de los vocabularios ESP32forth

### Versión v 7.0.7.17

#### FORTH (vocabulario principal)

```
- -rot , ; : :noname ! 
? ?do ?dup . ." .s ' 
(local) [ ['] [char] [ELSE] [IF] [THEN] 
] { { }transfer @ * */ 
*/MOD / /mod # #! #> #fs 
#s #tib + +! +loop +to < 
<# <= <> = > >= >BODY 
>flags >flags& >in >link >link& >name >params 
>R >size 0< 0<> 0= 1- 1/F 
1+ 2! 2@ 2* 2/ 2drop 2dup 
4* 4/ abort abort" abs accept adc 
afliteral aft again ahead align aligned allocate 
allot also analogRead AND ansi ARSHIFT asm 
assert at-xy base begin bg BIN binary 
bl blank block block-fid block-id buffer bye 
c, C! C@ CASE cat catch CELL 
cell/ cell+ cells char CLOSE-DIR CLOSE-FILE cmove 
cmove> CONSTANT context copy cp cr CREATE 
CREATE-FILE current dacWrite decimal default-key default-key? 
default-type default-use defer DEFINED? definitions DELETE-FILE
depth digitalRead digitalWrite do DOES> DROP 
dump dump-file DUP duty echo editor else 
emit empty-buffers ENDCASE ENDOF erase ESP 
ESP32-C3? ESP32-S2? ESP32-S3? ESP32? evaluate EXECUTE exit 
extract F- f. f.s F* F** F/ 
F+ F< F<= F<> F= F> F>= 
F>S F0< F0= FABS FATAN2 fconstant FCOS 
fdepth FDROP FDUP FEXP fg file-exists? 
FILE-POSITION FILE-SIZE fill FIND fliteral FLN 
FLOOR flush FLUSH-FILE FMAX FMIN FNEGATE FNIP 
for forget FORTH forth-builtins FOVER FP! 
FP@ fp0 free freq FROT FSIN FSINCOS 
FSQRT FSWAP fvariable handler here hex HIGH 
hld hold httpd I if IMMEDIATE include 
included included? INPUT internals invert is J 
K key key? L! latestxt leave LED 
ledc list literal load login loop LOW 
ls LSHIFT max MDNS.begin min mod ms 
MS-TICKS mv n. needs negate nest-depth next 
nip nl NON-BLOCK normal octal OF ok 
only open-blocks OPEN-DIR OPEN-FILE OR order OUTPUT 
OVER pad page PARSE pause PI pin 
pinMode postpone precision previous prompt PSRAM? pulseIn 
quit r" R@ R/O R/W R> r| 
r~ rdrop read-dir READ-FILE recurse refill registers 
remaining remember RENAME-FILE repeat REPOSITION-FILE required 
reset resize RESIZE-FILE restore revive RISC-V? rm 
rot RP! RP@ rp0 RSHIFT rtos s" 
S>F s>z save save-buffers scr SD 
SD_MMC sealed see Serial set-precision set-title 
sf, SF! SF@ SFLOAT SFLOAT+ SFLOATS sign 
SL@ sockets SP! SP@ sp0 space spaces 
SPIFFS start-task startswith? startup: state str str= 
streams structures SW@ SWAP task tasks telnetd 
terminate then throw thru tib to tone 
touch transfer transfer type u. U/MOD UL@ 
UNLOOP until update use used UW@ value 
VARIABLE visual vlist vocabulary W! W/O web-interface 
webui while WiFi Wire words WRITE-FILE XOR 
Xtensa? z" z>s
```

#### asm

```
xtensa disasm disasm1 matchit address istep sextend m. m@ for-ops op >operands 
>mask >pattern >length >xt op-snap opcodes coden, names operand l o bits 
bit skip advance advance-operand reset reset-operand for-operands operands 
>printop >inop >next >opmask& bit! mask pattern length demask enmask >>1 
odd? high-bit end-code code, code4, code3, code2, code1, callot chere reserve 
code-at code-start
```

#### bluetooth

```
SerialBT.new SerialBT.delete SerialBT.begin SerialBT.end SerialBT.available 
SerialBT.readBytes SerialBT.write SerialBT.flush SerialBT.hasClient 
SerialBT.enableSSP SerialBT.setPin SerialBT.unpairDevice SerialBT.connect 
SerialBT.connectAddr SerialBT.disconnect SerialBT.connected 
SerialBT.isReady bluetooth-builtins
```

#### editor

```
a r d e wipe p n l
```

#### ESP

```
getHeapSize getFreeHeap getMaxAllocHeap getChipModel getChipCores getFlashChipSize 
getCpuFreqMHz getSketchSize deepSleep getEfuseMac esp_log_level_set ESP-builtins
```

#### httpd

```
notfound-response bad-response ok-response response send path method hasHeader 
handleClient read-headers completed? body content-length header crnl= eat 
skipover skipto in@<> end< goal# goal strcase= upper server client-cr client-emit 
client-read client-type client-len client httpd-port clientfd sockfd body-read 
body-1st-read body-chunk body-chunk-size chunk-filled chunk chunk-size 
max-connections
```

#### insides

```
run normal-mode raw-mode step ground handle-key quit-edit save load backspace 
delete handle-esc insert update crtype cremit ndown down nup up caret length 
capacity text start-size fileh filename# filename max-path
```

#### internals

```
assembler-source xtensa-assembler-source MALLOC SYSFREE REALLOC heap_caps_malloc 
heap_caps_free heap_caps_realloc heap_caps_get_total_size heap_caps_get_free_size 
heap_caps_get_minimum_free_size heap_caps_get_largest_free_block RAW-YIELD 
RAW-TERMINATE READDIR CALLCODE CALL0 CALL1 CALL2 CALL3 CALL4 CALL5 CALL6 
CALL7 CALL8 CALL9 CALL10 CALL11 CALL12 CALL13 CALL14 CALL15 DOFLIT S>FLOAT? 
fill32 'heap 'context 'latestxt 'notfound 'heap-start 'heap-size 'stack-cells 
'boot 'boot-size 'tib 'argc 'argv 'runner 'throw-handler NOP BRANCH 0BRANCH 
DONEXT DOLIT DOSET DOCOL DOCON DOVAR DOCREATE DODOES ALITERAL LONG-SIZE 
S>NUMBER? 'SYS YIELD EVALUATE1 'builtins internals-builtins autoexec 
arduino-remember-filename
arduino-default-use esp32-stats serial-key? serial-key serial-type yield-task 
yield-step e' @line grow-blocks use?! common-default-use block-data block-dirty 
clobber clobber-line include+ path-join included-files raw-included include-file 
sourcedirname sourcefilename! sourcefilename sourcefilename# sourcefilename& 
starts../ starts./ dirname ends/ default-remember-filename remember-filename 
restore-name save-name forth-wordlist setup-saving-base 'cold park-forth 
park-heap saving-base crtype cremit cases (+to) (to) --? }? ?room scope-create 
do-local scope-clear scope-exit local-op scope-depth local+! local! local@ 
<>locals locals-here locals-area locals-gap locals-capacity ?ins. ins. 
vins. onlines line-pos line-width size-all size-vocabulary vocs. voc. voclist 
voclist-from see-all >vocnext see-vocabulary nonvoc? see-xt ?see-flags 
see-loop see-one indent+! icr see. indent mem= ARGS_MARK -TAB +TAB NONAMED 
BUILTIN_FORK SMUDGE IMMEDIATE_MARK relinquish dump-line ca@ cell-shift 
cell-base cell-mask MALLOC_CAP_RTCRAM MALLOC_CAP_RETENTION MALLOC_CAP_IRAM_8BIT 
MALLOC_CAP_DEFAULT MALLOC_CAP_INTERNAL MALLOC_CAP_SPIRAM MALLOC_CAP_DMA 
MALLOC_CAP_8BIT MALLOC_CAP_32BIT MALLOC_CAP_EXEC #f+s internalized BUILTIN_MARK 
zplace $place free. boot-prompt raw-ok [SKIP]' [SKIP] ?stack sp-limit input-limit 
tib-setup raw.s $@ digit parse-quote leaving, leaving )leaving leaving( 
value-bind evaluate&fill evaluate-buffer arrow ?arrow. ?echo input-buffer 
immediate? eat-till-cr wascr *emit *key notfound last-vocabulary voc-stack-end 
xt-transfer xt-hide xt-find& scope
```

#### interrupts

```
pinchange #GPIO_INTR_HIGH_LEVEL #GPIO_INTR_LOW_LEVEL #GPIO_INTR_ANYEDGE 
#GPIO_INTR_NEGEDGE #GPIO_INTR_POSEDGE #GPIO_INTR_DISABLE ESP_INTR_FLAG_INTRDISABLED 
ESP_INTR_FLAG_IRAM ESP_INTR_FLAG_EDGE ESP_INTR_FLAG_SHARED ESP_INTR_FLAG_NMI 
ESP_INTR_FLAG_LEVELn ESP_INTR_FLAG_DEFAULT gpio_config gpio_reset_pin gpio_set_intr_type 
gpio_intr_enable gpio_intr_disable gpio_set_level gpio_get_level gpio_set_direction 
gpio_set_pull_mode gpio_wakeup_enable gpio_wakeup_disable gpio_pullup_en 
gpio_pulldown_en gpio_pulldown_dis gpio_hold_en gpio_hold_dis 
gpio_deep_sleep_hold_en gpio_deep_sleep_hold_dis gpio_install_isr_service 
gpio_isr_handler_add gpio_isr_handler_remove 
gpio_set_drive_capability gpio_get_drive_capability esp_intr_alloc esp_intr_free 
interrupts-builtins
```

#### ledc

```
ledcSetup ledcAttachPin ledcDetachPin ledcRead ledcReadFreq ledcWrite ledcWriteTone
ledcWriteNote ledc-builtins
```

#### oled

```
OledInit SSD1306_SWITCHCAPVCC SSD1306_EXTERNALVCC WHITE BLACK 
OledReset HEIGHT WIDTH OledAddr OledNew OledDelete OledBegin OledHOME OledCLS 
OledTextc OledPrintln OledNumln OledNum OledDisplay OledPrint OledInvert 
OledTextsize OledSetCursor OledPixel OledDrawL OledFastHLine OledFastVLine 
OledCirc OledCircF OledRect OledRectF OledRectR OledRectRF oled-builtins
```

#### registers

```
m@ m!
```

#### riscv

```
C.FSWSP, C.SWSP, C.FSDSP, C.ADD, C.JALR, C.EBREAK, C.MV, C.JR, C.FLWSP, 
C.LWSP, C.FLDSP, C.SLLI, BNEZ, BEQZ, C.J, C.ADDW, C.SUBW, C.AND, C.OR, 
C.XOR, C.SUB, C.ANDI, C.SRAI, C.SRLI, C.LUI, C.LI, C.JAL, C.ADDI, C.NOP, 
C.FSW, C.SW, C.FSD, C.FLW, C.LW, C.FLD, C.ADDI4SP, C.ILL, EBREAK, ECALL, 
AND, OR, SRA, SRL, XOR, SLTU, SLT, SLL, SUB, ADD, SRAI, SRLI, SLLI, ANDI, 
ORI, XORI, SLTIU, SLTI, ADDI, SW, SH, SB, LHU, LBU, LW, LH, LB, BGEU, BLTU, 
BGE, BLT, BNE, BEQ, JALR, JAL, AUIPC, LUI, J-TYPE U-TYPE B-TYPE S-TYPE 
I-TYPE R-TYPE rs2' rs2#' rs2 rs2# rs1' rs1#' rs1 rs1# rd' rd#' rd rd# offset 
ofs ofs. >ofs iiii i numeric register' reg'. reg>reg' register reg. nop 
x31 x30 x29 x28 x27 x26 x25 x24 x23 x22 x21 x20 x19 x18 x17 x16 x15 x14 
x13 x12 x11 x10 x9 x8 x7 x6 x5 x4 x3 x2 x1 zero
```

#### rmt

```
rmt_set_clk_div rmt_get_clk_div rmt_set_rx_idle_thresh rmt_get_rx_idle_thresh 
rmt_set_mem_block_num rmt_get_mem_block_num rmt_set_tx_carrier rmt_set_mem_pd 
rmt_get_mem_pd rmt_tx_start rmt_tx_stop rmt_rx_start rmt_rx_stop 
rmt_tx_memory_reset rmt_rx_memory_reset rmt_set_memory_owner rmt_get_memory_owner 
rmt_set_tx_loop_mode rmt_get_tx_loop_mode rmt_set_rx_filter rmt_set_source_clk 
rmt_get_source_clk rmt_set_idle_level rmt_get_idle_level rmt_get_status 
rmt_set_rx_intr_en rmt_set_err_intr_en rmt_set_tx_intr_en rmt_set_tx_thr_intr_en 
rmt_set_gpio rmt_config rmt_isr_register rmt_isr_deregister rmt_fill_tx_items 
rmt_driver_install rmt_driver_uinstall rmt_get_channel_status rmt_get_counter_clock 
rmt_write_items rmt_wait_tx_done rmt_get_ringbuf_handle rmt_translator_init 
rmt_translator_set_context rmt_translator_get_context rmt_write_sample 
rmt-builtins
```

#### rtos

```
vTaskDelete xTaskCreatePinnedToCore xPortGetCoreID rtos-builtins
```

#### SD

```
SD.begin SD.beginFull SD.beginDefaults SD.end SD.cardType SD.totalBytes 
SD.usedBytes SD-builtins
```

#### SD_MMC

```
SD_MMC.begin SD_MMC.beginFull SD_MMC.beginDefaults SD_MMC.end SD_MMC.cardType 
SD_MMC.totalBytes SD_MMC.usedBytes SD_MMC-builtins
```

#### Serial

```
Serial.begin Serial.end Serial.available Serial.readBytes Serial.write 
Serial.flush Serial.setDebugOutput Serial2.begin Serial2.end Serial2.available 
Serial2.readBytes Serial2.write Serial2.flush Serial2.setDebugOutput 
serial-builtins
```

#### sockets

```
ip. ip# ->h_addr ->addr! ->addr@ ->port! ->port@ sockaddr l, s, bs, SO_REUSEADDR 
SOL_SOCKET sizeof(sockaddr_in) AF_INET SOCK_RAW SOCK_DGRAM SOCK_STREAM 
socket setsockopt bind listen connect sockaccept select poll send sendto 
sendmsg recv recvfrom recvmsg gethostbyname errno sockets-builtins
```

#### spi

```
SPI.begin SPI.end SPI.setHwCs SPI.setBitOrder SPI.setDataMode SPI.setFrequency 
SPI.setClockDivider SPI.getClockDivider SPI.transfer SPI.transfer8 SPI.transfer16 
SPI.transfer32 SPI.transferBytes SPI.transferBits SPI.write SPI.write16 
SPI.write32 SPI.writeBytes SPI.writePixels SPI.writePattern SPI-builtins
```

#### SPIFFS

```
SPIFFS.begin SPIFFS.end SPIFFS.format SPIFFS.totalBytes SPIFFS.usedBytes 
SPIFFS-builtins
```

#### streams

```
stream> >stream stream>ch ch>stream wait-read wait-write empty? full? stream# 
>offset >read >write stream
```

#### structures

```
field struct-align align-by last-struct struct long ptr i64 i32 i16 i8 
typer last-align
```

#### tasks

```
.tasks main-task task-list
```

#### telnetd

```
server broker-connection wait-for-connection connection telnet-key 
telnet-type telnet-emit broker client-len client telnet-port clientfd sockfd
```

#### timers

```
interval onalarm int-enable! alarm-enable! divider! autoreload! increase! 
enable! alarm! alarm@ timer! timer@ tmp t>nx timer_isr_callback_add timer_init_null
timer_get_counter_value timer_set_counter_value timer_start timer_pause 
timer_set_counter_mode timer_set_auto_reload timer_set_divider 
timer_set_alarm_value timer_get_alarm_value timer_set_alarm 
timer_group_intr_enable timer_group_intr_disable 
timer_enable_intr timer_disable_intr timers-builtins
```

#### visual

```
edit insides
```

#### web-interface

```
server webserver-task do-serve handle1 serve-key serve-type handle-input 
handle-index out-string output-stream input-stream out-size webserver index-html 
index-html#
```

#### WiFi

```
WIFI_MODE_APSTA WIFI_MODE_AP WIFI_MODE_STA WIFI_MODE_NULL WiFi.config WiFi.begin 
WiFi.disconnect WiFi.status WiFi.macAddress WiFi.localIP WiFi.mode WiFi.setTxPower 
WiFi.getTxPower WiFi.softAP WiFi.softAPIP WiFi.softAPBroadcastIP 
WiFi.softAPNetworkID WiFi.softAPConfig WiFi.softAPdisconnect 
WiFi.softAPgetStationNum WiFi-builtins
```

#### Wire

```
Wire.begin Wire.setClock Wire.getClock Wire.setTimeout Wire.getTimeout 
Wire.beginTransmission Wire.endTransmission Wire.requestFrom Wire.write 
Wire.available Wire.read Wire.peek Wire.flush Wire-builtins
```

#### xtensa

```
WUR, WSR, WITLB, WER, WDTLB, WAITI, SSXU, SSX, SSR, SSL, SSIU, SSI, SSAI, 
SSA8L, SSA8B, SRLI, SRL, SRC, SRAI, SRA, SLLI, SLL, SICW, SICT, SEXT, SDCT, 
RUR, RSR, RSIL, RFI, ROTW, RITLB1, RITLB0, RER, RDTLB1, RDTLB0, PITLB, 
PDTLB, NSAU, NSA, MULA.DD.HH, MULA.DD.LH, MULA.DD.HL, MULA.DD.LL, MULS.DD 
... (instrucciones completas en el libro)
a15 a14 a13 a12 a11 a10 a9 a8 a7 a6 a5 a4 a3 a2 a1 a0
```

---

## Anexo A – Resumen de registros

### GPIO registers

| Name | Description | Address | Access |
|---|---|---|---|
| GPIO_OUT_REG | GPIO 0-31 output register | $3FF44004 | R/W |
| GPIO_OUT_W1TS_REG | GPIO 0-31 output register_W1TS | $3FF44008 | WO |
| GPIO_OUT_W1TC_REG | GPIO 0-31 output register_W1TC | $3FF4400C | WO |
| GPIO_OUT1_REG | GPIO 32-39 output register | $3FF44010 | R/W |
| GPIO_OUT1_W1TS_REG | GPIO 32-39 output bit set register | $3FF44014 | WO |
| GPIO_OUT1_W1TC_REG | GPIO 32-39 output bit clear register | $3FF44018 | WO |
| GPIO_ENABLE_REG | GPIO 0-31 output enable register | $3FF44020 | R/W |
| GPIO_ENABLE_W1TS_REG | GPIO 0-31 output enable register_W1TS | $3FF44024 | WO |
| GPIO_ENABLE_W1TC_REG | GPIO 0-31 output enable register_W1TC | $3FF44028 | WO |
| GPIO_ENABLE1_REG | GPIO 32-39 output enable register | $3FF4402C | R/W |
| GPIO_ENABLE1_W1TS_REG | GPIO 32-39 output enable bit set register | $3FF44030 | WO |
| GPIO_ENABLE1_W1TC_REG | GPIO 32-39 output enable bit clear register | $3FF44034 | WO |
| GPIO_STRAP_REG | Bootstrap pin value register | $3FF44038 | RO |
| GPIO_IN_REG | GPIO 0-31 input register | $3FF4403C | RO |
| GPIO_IN1_REG | GPIO 32-39 input register | $3FF44040 | RO |
| GPIO_STATUS_REG | GPIO 0-31 interrupt status register | $3FF44044 | R/W |
| GPIO_STATUS_W1TS_REG | GPIO 0-31 interrupt status register_W1TS | $3FF44048 | WO |
| GPIO_STATUS_W1TC_REG | GPIO 0-31 interrupt status register_W1TC | $3FF4404C | WO |
| GPIO_STATUS1_REG | GPIO 32-39 interrupt status register1 | $3FF44050 | R/W |
| GPIO_STATUS1_W1TS_REG | GPIO 32-39 interrupt status bit set register | $3FF44054 | WO |
| GPIO_STATUS1_W1TC_REG | GPIO 32-39 interrupt status bit clear register | $3FF44058 | WO |
| GPIO_ACPU_INT_REG | GPIO 0-31 APP_CPU interrupt status | $3FF44060 | RO |
| GPIO_ACPU_NMI_INT_REG | GPIO 0-31 APP_CPU non-maskable interrupt status | $3FF44064 | RO |
| GPIO_PCPU_INT_REG | GPIO 0-31 PRO_CPU interrupt status | $3FF44068 | RO |
| GPIO_PCPU_NMI_INT_REG | GPIO 0-31 PRO_CPU non-maskable interrupt status | $3FF4406C | RO |
| GPIO_ACPU_INT1_REG | GPIO 32-39 APP_CPU interrupt status | $3FF44074 | RO |
| GPIO_ACPU_NMI_INT1_REG | GPIO 32-39 APP_CPU non-maskable interrupt status | $3FF44078 | RO |
| GPIO_PCPU_INT1_REG | GPIO 32-39 PRO_CPU interrupt status | $3FF4407C | RO |
| GPIO_PCPU_NMI_INT1_REG | GPIO 32-39 PRO_CPU non-maskable interrupt status | $3FF44080 | RO |
| GPIO_PIN0_REG | Configuration for GPIO pin 0 | $3FF44088 | R/W |
| GPIO_PIN1_REG | Configuration for GPIO pin 1 | $3FF4408C | R/W |
| GPIO_PIN2_REG | Configuration for GPIO pin 2 | $3FF44090 | R/W |
| GPIO_PIN38_REG | Configuration for GPIO pin 38 | $3FF44120 | R/W |
| GPIO_PIN39_REG | Configuration for GPIO pin 39 | $3FF44124 | R/W |
| GPIO_FUNC0_IN_SEL_CFG_REG | Peripheral function 0 input selection register | $3FF44130 | R/W |
| GPIO_FUNC1_IN_SEL_CFG_REG | Peripheral function 1 input selection register | $3FF44134 | R/W |
| GPIO_FUNC254_IN_SEL_CFG_REG | Peripheral function 254 input selection register | $3FF44528 | R/W |
| GPIO_FUNC255_IN_SEL_CFG_REG | Peripheral function 255 input selection register | $3FF4452C | R/W |
| GPIO_FUNC0_OUT_SEL_CFG_REG | Peripheral output selection for GPIO 0 | $3FF44530 | R/W |
| GPIO_FUNC1_OUT_SEL_CFG_REG | Peripheral output selection for GPIO 1 | $3FF44534 | R/W |
| GPIO_FUNC38_OUT_SEL_CFG_REG | Peripheral output selection for GPIO 38 | $3FF445C8 | R/W |
| GPIO_FUNC39_OUT_SEL_CFG_REG | Peripheral output selection for GPIO 39 | $3FF445CC | R/W |
| IO_MUX_PIN_CTRL | Clock output configuration register | $3FF49000 | R/W |
| IO_MUX_GPIO36_REG | Configuration register for pad GPIO36 | $3FF49004 | R/W |
| IO_MUX_GPIO37_REG | Configuration register for pad GPIO37 | $3FF49008 | R/W |
| IO_MUX_GPIO38_REG | Configuration register for pad GPIO38 | $3FF4900C | R/W |
| IO_MUX_GPIO39_REG | Configuration register for pad GPIO39 | $3FF49010 | R/W |
| IO_MUX_GPIO34_REG | Configuration register for pad GPIO34 | $3FF49014 | R/W |
| IO_MUX_GPIO35_REG | Configuration register for pad GPIO35 | $3FF49018 | R/W |
| IO_MUX_GPIO32_REG | Configuration register for pad GPIO32 | $3FF4901C | R/W |
| IO_MUX_GPIO33_REG | Configuration register for pad GPIO33 | $3FF49020 | R/W |
| IO_MUX_GPIO25_REG | Configuration register for pad GPIO25 | $3FF49024 | R/W |
| IO_MUX_GPIO26_REG | Configuration register for pad GPIO26 | $3FF49028 | R/W |
| IO_MUX_GPIO27_REG | Configuration register for pad GPIO27 | $3FF4902C | R/W |
| IO_MUX_MTMS_REG | Configuration register for pad MTMS | $3FF49030 | R/W |
| IO_MUX_MTDI_REG | Configuration register for pad MTDI | $3FF49034 | R/W |
| IO_MUX_MTCK_REG | Configuration register for pad MTCK | $3FF49038 | R/W |
| IO_MUX_MTDO_REG | Configuration register for pad MTDO | $3FF4903C | R/W |
| IO_MUX_GPIO2_REG | Configuration register for pad GPIO2 | $3FF49040 | R/W |
| IO_MUX_GPIO0_REG | Configuration register for pad GPIO0 | $3FF49044 | R/W |
| IO_MUX_GPIO4_REG | Configuration register for pad GPIO4 | $3FF49048 | R/W |
| IO_MUX_GPIO16_REG | Configuration register for pad GPIO16 | $3FF4904C | R/W |
| IO_MUX_GPIO17_REG | Configuration register for pad GPIO17 | $3FF49050 | R/W |
| IO_MUX_SD_DATA2_REG | Configuration register for pad SD_DATA2 | $3FF49054 | R/W |
| IO_MUX_SD_DATA3_REG | Configuration register for pad SD_DATA3 | $3FF49058 | R/W |
| IO_MUX_SD_CMD_REG | Configuration register for pad SD_CMD | $3FF4905C | R/W |
| IO_MUX_SD_CLK_REG | Configuration register for pad SD_CLK | $3FF49060 | R/W |
| IO_MUX_SD_DATA0_REG | Configuration register for pad SD_DATA0 | $3FF49064 | R/W |
| IO_MUX_SD_DATA1_REG | Configuration register for pad SD_DATA1 | $3FF49068 | R/W |
| IO_MUX_GPIO5_REG | Configuration register for pad GPIO5 | $3FF4906C | R/W |
| IO_MUX_GPIO18_REG | Configuration register for pad GPIO18 | $3FF49070 | R/W |
| IO_MUX_GPIO19_REG | Configuration register for pad GPIO19 | $3FF49074 | R/W |
| IO_MUX_GPIO20_REG | Configuration register for pad GPIO20 | $3FF49078 | R/W |
| IO_MUX_GPIO21_REG | Configuration register for pad GPIO21 | $3FF4907C | R/W |
| IO_MUX_GPIO22_REG | Configuration register for pad GPIO22 | $3FF49080 | R/W |
| IO_MUX_U0RXD_REG | Configuration register for pad U0RXD | $3FF49084 | R/W |
| IO_MUX_U0TXD_REG | Configuration register for pad U0TXD | $3FF49088 | R/W |
| IO_MUX_GPIO23_REG | Configuration register for pad GPIO23 | $3FF4908C | R/W |
| IO_MUX_GPIO24_REG | Configuration register for pad GPIO24 | $3FF49090 | R/W |

### GPIO configuration / data registers

| Name | Description | Address | Access |
|---|---|---|---|
| RTCIO_RTC_GPIO_OUT_REG | RTC GPIO output register | 0x3FF48400 | R/W |
| RTCIO_RTC_GPIO_OUT_W1TS_REG | RTC GPIO output bit set register | 0x3FF48404 | WO |
| RTCIO_RTC_GPIO_OUT_W1TC_REG | RTC GPIO output bit clear register | 0x3FF48408 | WO |
| RTCIO_RTC_GPIO_ENABLE_REG | RTC GPIO output enable register | 0x3FF4840C | R/W |
| RTCIO_RTC_GPIO_ENABLE_W1TS_REG | RTC GPIO output enable bit set register | 0x3FF48410 | WO |
| RTCIO_RTC_GPIO_ENABLE_W1TC_REG | RTC GPIO output enable bit clear register | 0x3FF48414 | WO |
| RTCIO_RTC_GPIO_STATUS_REG | RTC GPIO interrupt status register | 0x3FF48418 | WO |
| RTCIO_RTC_GPIO_STATUS_W1TS_REG | RTC GPIO interrupt status bit set register | 0x3FF4841C | WO |
| RTCIO_RTC_GPIO_STATUS_W1TC_REG | RTC GPIO interrupt status bit clear register | 0x3FF48420 | WO |
| RTCIO_RTC_GPIO_IN_REG | RTC GPIO input register | 0x3FF48424 | RO |
| RTCIO_RTC_GPIO_PIN0_REG | RTC configuration for pin 0 | 0x3FF48428 | R/W |
| ... | ... | ... | ... |
| RTCIO_RTC_GPIO_PIN17_REG | RTC configuration for pin 17 | 0x3FF4846C | R/W |
| RTCIO_DIG_PAD_HOLD_REG | RTC GPIO hold register | 0x3FF48474 | R/W |

### GPIO RTC function configuration registers

| Name | Description | Address | Access |
|---|---|---|---|
| RTCIO_HALL_SENS_REG | Hall sensor configuration | 0x3FF48478 | R/W |
| RTCIO_SENSOR_PADS_REG | Sensor pads configuration register | 0x3FF4847C | R/W |
| RTCIO_ADC_PAD_REG | ADC configuration register | 0x3FF48480 | R/W |
| RTCIO_PAD_DAC1_REG | DAC1 configuration register | 0x3FF48484 | R/W |
| RTCIO_PAD_DAC2_REG | DAC2 configuration register | 0x3FF48488 | R/W |
| RTCIO_XTAL_32K_PAD_REG | 32KHz crystal pads configuration register | 0x3FF4848C | R/W |
| RTCIO_TOUCH_CFG_REG | Touch sensor configuration register | 0x3FF48490 | R/W |
| RTCIO_TOUCH_PAD0_REG | Touch pad configuration register | 0x3FF48494 | R/W |
| ... | ... | ... | ... |
| RTCIO_TOUCH_PAD9_REG | Touch pad configuration register | 0x3FF484B8 | R/W |
| RTCIO_EXT_WAKEUP0_REG | External wake up configuration register | 0x3FF484BC | R/W |
| RTCIO_XTL_EXT_CTR_REG | Crystal power down enable GPIO source | 0x3FF484C0 | R/W |
| RTCIO_SAR_I2C_IO_REG | RTC I2C pad selection | 0x3FF484C4 | R/W |

---

## Recursos

### En inglés

- **ESP32forth** — Página mantenida por Brad NELSON, creador de ESP32forth. Todas las versiones (ESP32, Windows, Web, Linux):
  https://esp32forth.appspot.com/ESP32forth.html

### En francés

- **ESP32 Forth** — Sitio bilingüe (francés, inglés) con muchos ejemplos:
  https://esp32.arduino-forth.com/

### GitHub

- **Ueforth** — Recursos mantenidos por Brad NELSON. Archivos fuente Forth y C para ESP32forth:
  https://github.com/flagxor/ueforth
- **ESP32forth** — Códigos fuente y documentación. Recursos mantenidos por Marc PETREMANN:
  https://github.com/MPETREMANN11/ESP32forth
- **ESP32forthStation** — Recursos mantenidos por Ulrich HOFFMAN:
  https://github.com/uho/ESP32forthStation
- **ESP32Forth** — Recursos mantenidos por F. J. RUSSO:
  https://github.com/FJRusso53/ESP32Forth
- **esp32forth-addons** — Recursos mantenidos por Peter FORTH:
  https://github.com/PeterForth/esp32forth-addons
- **Esp32forth-org** — Repositorio de código para miembros de los grupos Forth2020 y ESP32forth:
  https://github.com/Esp32forth-org

---

## Índice léxico

| Término | Página |
|---|---|
| and | 42 |
| ansi | 96 |
| asm | 315 |
| BASE | 86 |
| bg | 61 |
| binary | 37 |
| bluetooth | 316 |
| borrar archivo | 141 |
| Colores de texto | 61 |
| comando AT | 284 |
| create | 105 |
| decimal | 37 |
| DECIMAL | 86 |
| defer | 100 |
| defPin: | 152 |
| DOES> | 105 |
| dump | 53 |
| editor | 125, 316 |
| EMIT | 89 |
| ESP | 316 |
| EXECUTE | 99 |
| f | 82 |
| fconstant | 83 |
| fg | 61 |
| flush | 127 |
| FORTH | 314 |
| fvariable | 83 |
| GIT | 146 |
| gpio_set_intr_type | 165 |
| handleClient | 310 |
| hex | 37 |
| HEX | 86 |
| HOLD | 87 |
| httpd | 316 |
| include | 140 |
| insides | 316 |
| internals | 316 |
| interrupts | 317 |
| interval | 176 |
| is | 100 |
| ledc | 245, 317 |
| ledcAttachPin | 245 |
| lista de archivos | 140 |
| load | 127 |
| login | 121 |
| ls | 141 |
| m! | 155, 271 |
| m@ | 158 |
| ms-ticks | 184 |
| Netbeans | 146 |
| normal | 61 |
| números aleatorios | 275 |
| oled | 79, 96, 201, 317 |
| page | 61 |
| pi | 82 |
| pseudodirectorio | 140 |
| random | 276 |
| RECORDFILE | 132 |
| registers | 317 |
| renombrar archivo | 141 |
| rerun | 176 |
| riscv | 317 |
| rm | 141 |
| rmt | 318 |
| rnd | 276 |
| RNG_DATA_REG | 276 |
| rtos | 318 |
| S" | 90 |
| SD | 318 |
| SD_MMC | 318 |
| see | 53 |
| Serial | 318 |
| server | 122 |
| set-precision | 82 |
| shift | 41 |
| sockets | 318 |
| SPACE | 91 |
| spi | 319 |
| SPI | 224 |
| SPIFFS | 140, 319 |
| streams | 319 |
| struct | 74 |
| structures | 74, 96, 319 |
| tasks | 319 |
| telnetd | 122, 319 |
| Tera Term | 115 |
| thru | 127 |
| tiempo real | 184 |
| timers | 319 |
| to | 66 |
| u | 40 |
| ver contenido del archivo | 141 |
| visual | 319 |
| voclist | 95 |
| web-interface | 319 |
| WiFi | 320 |
| wipe | 126 |
| Wire | 320 |
| Wire.detect | 206 |
| xtensa | 320 |
| xtensa-assembler | 253, 257 |
| :noname | 102 |
| ." | 90 |
| .s | 53 |
| { | 65 |
| } | 65 |
| # | 87 |
| #> | 87 |
| #S | 87 |
| +to | 66 |
| <# | 87 |

---

## Plantilla LaTeX

```latex
\documentclass[11pt,a4paper]{article}
\usepackage[utf8]{inputenc}
\usepackage[spanish]{babel}
\usepackage{geometry}
\geometry{margin=2.5cm}
\usepackage{hyperref}
\usepackage{listings}
\usepackage{graphicx}
\usepackage{booktabs}
\usepackage{float}

\title{El gran libro por ESP32forth}
\author{Marc PETREMANN}
\date{Versión 1.17 -- 25 de enero de 2024}

\begin{document}

\maketitle

\begin{abstract}
Manual completo de ESP32forth para la placa ESP32 de Espressif.
Cubre desde los fundamentos del lenguaje FORTH hasta aplicaciones
avanzadas de hardware, comunicación inalámbrica y programación
a bajo nivel.
\end{abstract}

\tableofcontents
\newpage

\section{Introducción}
% completar

\section{Descubrimiento de la tarjeta ESP32}
% completar

\section{Instalación de ESP32forth}
% completar

\section{¿Por qué programar en FORTH?}
% completar

\section{Usando números con ESP32Forth}
% completar

\section{Un verdadero FORTH de 32 bits}
% completar

\section{Comentarios y aclaraciones}
% completar

\section{Diccionario / Pila / Variables / Constantes}
% completar

\section{Variables locales}
% completar

\section{Estructuras de datos}
% completar

\section{Pantalla OLED SSD1306}
% completar

\section{Números reales}
% completar

\section{Mostrar números y cadenas}
% completar

\section{Vocabularios}
% completar

\section{Palabras de acción retrasada}
% completar

\section{Palabras de creación de palabras}
% completar

\section{Gestión de archivos}
% completar

\section{Semáforo con ESP32}
% completar

\section{Acceso directo a registros GPIO}
% completar

\section{Interrupciones hardware}
% completar

\section{Codificador rotatorio}
% completar

\section{Temporizadores}
% completar

\section{Reloj en tiempo real}
% completar

\section{Analizador de luz solar}
% completar

\section{Síntesis de sonido}
% completar

\section{Ensamblador XTENSA}
% completar

\section{Generador de números aleatorios}
% completar

\section{Sistema de transmisión LoRa}
% completar

\section{Interfaz WEB}
% completar

\section{Vocabularios ESP32forth}
% completar

\appendix
\section{Resumen de registros}
% completar

\end{document}
```

---

**Fin del documento estructurado.**
**Páginas cubiertas:** 1–324
**Identificadores JSON únicos:** image-01 a image-13, table-01 a table-02, diagram-01 a diagram-06
**Total de palabras:** ~18,500
