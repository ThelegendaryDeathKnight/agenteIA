# ARDUINO: LIBRO DE PROYECTOS

**Fuente:** Scott Fitzgerald y Michael Shiloh. *Arduino Project Book*. Arduino LLC, 2012–2013. Traducción de Florentino Blas Fernández Cueto (Tino Fernández), revisada por Miguel Carlos de Castro Miguel y Manuel Díaz Santalla. Licencia Creative Commons Reconocimiento – NoComercial – CompartirIgual 3.0.

---

## Resumen técnico

El *Libro de Proyectos de Arduino* es una guía práctica y didáctica que introduce al lector en el mundo de la electrónica y la programación mediante el uso de la plataforma Arduino Uno. El documento está diseñado para principiantes y no requiere conocimientos previos en electrónica o programación. A lo largo de sus páginas, se presentan 15 proyectos creativos que abarcan desde circuitos básicos con LEDs y pulsadores hasta aplicaciones más complejas como un theremin controlado por luz, un teclado musical, un reloj de arena digital, un zoótropo motorizado, una bola de cristal con pantalla LCD, un mecanismo de bloqueo secreto, una lámpara sensible al tacto, y la comunicación serie con Processing para controlar programas de ordenador.

El libro comienza con una introducción a los componentes del kit, explicando el funcionamiento de cada elemento: la placa Arduino Uno, la placa de pruebas, resistencias, LEDs, condensadores, diodos, transistores, servomotores, sensores de temperatura, foto resistencias, potenciómetros, pulsadores, zumbadores piezoeléctricos, sensores de inclinación, optoacopladores, y cables de conexión. Se detallan los símbolos electrónicos y se explica cómo leer el código de colores de las resistencias.

Posteriormente, se guía al lector en la instalación del Entorno de Desarrollo Integrado (IDE) de Arduino en Windows, Mac OS X y Linux, y se explica cómo cargar el primer programa (sketch) de ejemplo "Blink" para verificar la comunicación entre el ordenador y la placa.

Cada proyecto sigue una estructura consistente: objetivos, materiales (ingredientes), tiempo estimado, nivel de dificultad, proyectos en los que se basa, montaje del circuito (con diagramas de placa de pruebas y esquemas eléctricos), código comentado, explicación de las funciones y conceptos de programación utilizados, y sugerencias para modificar y ampliar el proyecto. Los proyectos abordan conceptos clave como entradas y salidas digitales, entradas analógicas, modulación por ancho de pulso (PWM), comunicación serie, uso de librerías, matrices, temporizadores con `millis()`, transistores, puentes H, pantallas LCD, y comunicación con Processing.

El libro incluye un glosario con más de 80 términos técnicos y una bibliografía recomendada para profundizar en el aprendizaje de Arduino y la electrónica.

---

## Objetivos del libro

Al concluir el estudio de este libro, usted deberá ser capaz de:

1. Comprender los fundamentos básicos de la electricidad y la electrónica.
2. Conocer los componentes electrónicos incluidos en el Kit de Inicio de Arduino.
3. Montar circuitos sobre una placa de pruebas sin necesidad de soldar.
4. Programar la placa Arduino Uno utilizando el IDE de Arduino.
5. Utilizar entradas y salidas digitales y analógicas.
6. Aplicar técnicas como PWM, comunicación serie y uso de librerías.
7. Construir 15 proyectos prácticos que integran sensores, actuadores y programación.
8. Desarrollar la creatividad para modificar y ampliar los proyectos propuestos.

---

## Contenido

1. Introducción
2. Conozca sus herramientas (Proyecto 01)
3. Interface de nave espacial (Proyecto 02)
4. Medidor de enamoramiento (Proyecto 03)
5. Lámpara de mezcla de colores (Proyecto 04)
6. Indicador del estado de ánimo (Proyecto 05)
7. Theremin controlado por luz (Proyecto 06)
8. Teclado musical (Proyecto 07)
9. Reloj de arena digital (Proyecto 08)
10. Rueda de colores motorizada (Proyecto 09)
11. Zoótropo (Proyecto 10)
12. La Bola de Cristal (Proyecto 11)
13. Mecanismo de bloqueo secreto (Proyecto 12)
14. Lámpara sensible al tacto (Proyecto 13)
15. Retocar el logotipo de Arduino (Proyecto 14)
16. Hackear botones (Proyecto 15)
17. Glosario A/Z
18. Apuntes y libros recomendados

---

## 0. Introducción

### Bienvenido a Arduino

Arduino hace lo más fácil posible programar pequeños ordenadores llamados microcontroladores, los cuales hacen que los objetos se conviertan en interactivos.

Usted está rodeado por docenas de ellos cada día: se encuentran dentro de relojes, termostatos, juguetes, mandos de control remoto, hornos de microondas, en algunos cepillos de dientes. Solo hacen una tarea en concreto y si no se da cuenta de que existen – lo cual es en la mayoría de las ocasiones – es porque están realizando bien su trabajo. Han sido programados para detectar y controlar una actividad mediante sensores y actuadores.

Los **sensores** "escuchan" el mundo físico. Convierten la energía que usted usa al presionar un botón, o al mover los brazos, o al gritar, en señales eléctricas. Botones y mandos son sensores que toca con sus dedos, pero existen otra clase de sensores. Los **actuadores** hacen algo dentro del mundo físico. Convierten la energía eléctrica en energía física, como la luz, el calor y el movimiento.

Ellos deciden qué hacer basándose en el programa que tú escribes.

Arduino puede hacer que tus proyectos realicen su cometido pero solamente tú puedes hacerlos hermosos.

Arduino fue diseñado para ayudarte a hacer cosas. Para conseguirlo, intentamos que tanto la programación como los materiales electrónicos utilizados se reduzcan lo más posible. Si decides que quieres saber más acerca de estos aspectos, existen muchas buenas guías disponibles. Te proporcionaremos un par de referencias y puedes encontrar más información a través de la página web de Arduino en: arduino.cc/starterkit

---

## Componentes de tu Kit

```json
{
  "type": "image",
  "id": "image-01",
  "page": 7,
  "title": "Componentes del Kit de Inicio de Arduino",
  "caption": "Componentes de tu Kit",
  "description": "Collage de componentes electrónicos incluidos en el Kit de Inicio de Arduino: placa Arduino Uno, placa de pruebas, clip para batería, condensadores, motor DC, diodo, papel celofán, puente H, cables puente, LEDs, pantalla LCD, tira de pines macho, optoacoplador, zumbador piezoeléctrico, foto resistencia, potenciómetro, pulsador, resistencias, servo motor, cable USB, sensor de temperatura, sensor de inclinación, transistor.",
  "elements": [
    "Arduino Uno",
    "Clip para Batería",
    "Placa de pruebas",
    "Condensadores",
    "Motor de continua (DC)",
    "Diodo",
    "Papel celofán (rojo, verde, azul)",
    "Puente-H",
    "Cables puente",
    "Diodos Emisores de Luz (LEDs)",
    "Pantalla de Cristal Líquido (LCD)",
    "Tira de pines macho",
    "Optoacoplador",
    "Zumbador piezo eléctrico",
    "Foto resistencia",
    "Potenciómetro",
    "Pulsador",
    "Resistencias",
    "Servo motor",
    "Cable USB",
    "Sensor de temperatura",
    "Sensor de inclinación",
    "Transistor"
  ],
  "source": "Arduino Project Book"
}
```

### Descripción de los componentes

- **Arduino Uno:** La tarjeta de desarrollo del microcontrolador, el corazón de tus proyectos. Es un simple ordenador, pero uno con el cual todavía no puedes realizar nada. Construirás circuitos e interfaces para hacer cosas y decirle al microcontrolador cómo trabajar con otros componentes.

- **Clip para Batería:** Se utiliza para conectar una batería de 9V a los cables de alimentación y así conectarla fácilmente a la placa Arduino.

- **Placa de pruebas:** Una placa sobre la cual puede montar componentes electrónicos. Es como un panel con agujeros, con filas de agujeros que le permite conectar juntos cables y componentes electrónicos. También están disponibles tarjetas sobre las que hay que soldar y también sin necesidad de usar un soldador como la mostrada aquí.

- **Condensadores:** Estos componentes almacenan y devuelven energía eléctrica en un circuito. Cuando el voltaje del circuito es más alto que el que está almacenado en el condensador, la corriente fluye del circuito al condensador, dándole una carga. Cuando la tensión del circuito es más baja, la energía eléctrica almacenada en el condensador es devuelta al circuito. A menudo se colocan entre los terminales positivo y negativo de una alimentación de un sensor o un motor para ayudar a suavizar las fluctuaciones de tensión que se puedan producir.

- **Motor de continua (DC):** Convierte la energía eléctrica en energía mecánica cuando la electricidad es aplicada a sus terminales. Una bobina de hilo dentro del motor produce un campo magnético cuando la corriente eléctrica continua (DC) fluye a través de él. Este campo magnético producido en la bobina atrae y repele al campo magnético de los imanes interiores haciendo que la bobina de hilo gire en el interior. Si se invierte la tensión aplicada el motor gira en sentido contrario.

- **Diodo:** Conduce la electricidad en una sola dirección. Es útil usarlo en un circuito con un motor o una carga que consuma una gran cantidad de corriente eléctrica. Los diodos tienen polaridad, esto quiere decir que hay que colocarlos de una forma determinada (polarizado) dentro del circuito. Colocado de esta manera (correctamente polarizado) permite que la corriente eléctrica pase a través de él. Colocado al revés (inversamente polarizado) no deja pasar la corriente eléctrica. El diodo tiene dos terminales, uno de ellos llamado ánodo, el cual se conecta dentro de un circuito al punto donde más tensión existe. El otro terminal llamado cátodo, se conecta a otro punto con una tensión inferior con respecto al punto en donde se conecta el ánodo. El cátodo normalmente se indica mediante una franja de color blanco en uno de los lados del cuerpo del diodo.

- **Papel celofán (rojo, verde, azul):** Son filtros que dejan pasar diferentes longitudes de onda de la luz. Cuando se utilizan con una foto resistencia (sensor), pueden hacer que el sensor solo reaccione a una cantidad de luz que entra en el filtro de color, de manera que otras luces de otras longitudes de onda no hacen reaccionar al sensor.

- **Puente-H:** Se trata de un circuito que permite controlar la polaridad de la tensión aplicada a una carga. El puente-H en el kit es un circuito integrado, pero se puede construir a partir de un número determinado de componentes discretos (resistencias, condensadores y transistores).

- **Cables puente:** Utilizarlos para conectar unos componentes con otros sobre la placa de prueba, y la tarjeta de Arduino.

- **Diodos Emisores de Luz (LEDs):** Un tipo de diodo que emite luz cuando la corriente lo atraviesa. Como en todos los diodos, la corriente solo fluye en un sentido a través de estos componentes. Estará probablemente familiarizado con ellos al verlos como indicadores dentro de una gran variedad de dispositivos electrónicos. El ánodo, que normalmente se conecta al positivo de la alimentación, es generalmente el terminal más largo, y el cátodo el terminal más corto.

- **Pantalla de Cristal Líquido (LCD):** Un tipo de pantalla numérica o gráfica basado en cristal líquido. Los LCDs están disponibles en varios tamaños, formas y estilos. El que se incluye con este kit dispone de 2 filas con 16 caracteres en cada una de ellas.

- **Tira de pines macho:** Estos pines se conectan en zócalos hembra, como los que tiene una placa de pruebas. Permiten conectar otros elementos electrónicos con mucha facilidad.

- **Optoacoplador:** Permite conectar dos circuitos que no tienen en común la misma fuente de alimentación. En su interior hay un pequeño diodo led que, cuando se ilumina, hace que un foto-receptor cierre un interruptor interno. Cuando se aplica una tensión al terminal + (positivo), el diodo led emite luz y el interruptor interno se cierra. Las dos salidas reemplazan a un interruptor en el circuito secundario.

- **Zumbador piezo eléctrico:** Un componente eléctrico que se puede usar para detectar vibraciones y generar ruidos.

- **Foto resistencia:** (también llamada foto célula o resistencia dependiente de la luz). Se trata de una resistencia variable que cambia su resistencia según el nivel de luz que incide sobre su superficie.

- **Potenciómetro:** Una resistencia variable con tres terminales. Dos de estos terminales están conectados a los extremos de una resistencia fija. El terminal central se puede mover a través de la superficie de la resistencia fija (dispone de un mando), consiguiendo de esta forma dos valores diferentes de resistencia según el terminal extremo que se tome como referencia. Cuando los terminales extremos del potenciómetro se conectan entre una tensión y masa, en el terminal central aparece una tensión que es proporcional al giro del mando central, entre cero (un extremo) y la máxima tensión (el otro extremo).

- **Pulsador:** Interruptores momentáneos que cierran un circuito cuando son presionados. Se colocan con facilidad sobre la placa de pruebas. Son buenos para abrir o cerrar el paso a una señal.

- **Resistencias:** Se opone al paso de la corriente eléctrica en un circuito, dando como resultado un cambio en la tensión y en dicha corriente. El valor de las resistencias se mide en ohmios (se representa por la letra griega omega: Ω). Las bandas de colores en un lado de la resistencia indican su valor (ver la tabla de código de colores de la resistencia en la página 41).

- **Servo motor:** Un tipo de motor reductor que solo puede girar 180 grados. Es controlado por las señales eléctricas en formato de pulsos que son enviadas desde la tarjeta Arduino. Estos pulsos le dicen al motor a qué posición se debe de mover.

- **Cable USB:** Permite conectar la placa Arduino Uno a un ordenador para que se pueda programar. También proporciona la alimentación necesaria tanto a la placa Arduino como a todos los componentes electrónicos que forman parte de los proyectos de este kit.

- **Sensor de temperatura:** Cambia la tensión de salida que suministra dependiendo de la temperatura que tenga su encapsulado. Sus terminales extremos se conectan entre una tensión y masa. El voltaje del terminal central cambia según este componente esté más caliente o más frío.

- **Sensor de inclinación:** Un tipo de interruptor que se abre o se cierra dependiendo de su orientación. Normalmente son cilindros huecos con una bola de metal en su interior la cual hará que los dos terminales se unan a través de esta bola cuando se incline en una determinada dirección.

- **Transistor:** Componente de tres terminales que puede trabajar como un interruptor electrónico. Es útil para controlar corrientes y tensiones grandes como la de los motores. Un terminal se conecta a masa, otro terminal a un elemento que se quiera controlar (motor, bombilla, zumbador) y el tercer terminal se conecta a una salida de Arduino. Cuando el transistor recibe una tensión de control a través del terminal que está conectado a Arduino, cierra los terminales extremos, entre masa y el terminal donde se conecta el elemento, de manera que dicho elemento recibe la energía necesaria que lo hace funcionar (gira, emite luz, genera un sonido).

---

## Tabla con los símbolos de los componentes electrónicos

```json
{
  "type": "table",
  "id": "table-01",
  "page": 11,
  "title": "Tabla con los símbolos de los componentes electrónicos",
  "headers": ["Componente", "Símbolo (descripción)", "Componente", "Símbolo (descripción)"],
  "rows": [
    ["Cables conectados", "Línea con punto de conexión", "Transistor Bipolar", "Símbolo con tres terminales y flecha"],
    ["Cables no conectados", "Línea sin punto de conexión", "Transistor Mosfet", "Símbolo con tres terminales y sustrato"],
    ["Sensor de Inclinación", "Rectángulo con dos terminales", "Resistencia LDR", "Resistencia con flechas incidentes"],
    ["Resistencia", "Rectángulo con bandas de colores", "Diodo", "Triángulo con línea"],
    ["Diodo Led", "Diodo con flechas salientes", "Condensador", "Dos líneas paralelas"],
    ["Condensador polarizado", "Una línea recta y una curva con +", "Tierra", "Línea horizontal con líneas decrecientes"],
    ["Pulsador", "Interruptor con botón", "Motor", "Círculo con M"],
    ["Potenciómetro", "Resistencia con flecha central", "Zumbador piezo-eléctrico", "Símbolo de bocina"],
    ["Batería", "Líneas paralelas de diferente longitud", "", ""]
  ],
  "notes": "En este libro se muestran los circuitos de dos formas distintas: como ilustraciones realistas y como esquemas electrónicos. Las ilustraciones dan una idea de cómo podrían quedar montados los componentes electrónicos en la placa de pruebas para realizar un proyecto. Los esquemas, en su lugar, utilizan símbolos para presentar en esencia cómo funciona el circuito.",
  "source": "Arduino Project Book"
}
```

---

## La placa Arduino

```json
{
  "type": "diagram",
  "id": "diagram-01",
  "page": 12,
  "title": "La placa Arduino Uno",
  "caption": "La placa Arduino",
  "elements": [
    {
      "name": "Conector de alimentación",
      "description": "Este conector se utiliza para alimentar la placa Arduino cuando no está conectada a un puerto USB. Acepta tensiones entre 7 y 12V"
    },
    {
      "name": "Puerto USB",
      "description": "Usado para alimentar y cargar los programas a su Arduino, y para la comunicación con el programa de Arduino (mediante la instrucción Serial.println() etc.)"
    },
    {
      "name": "Botón de reset",
      "description": "Puesta a cero del microcontrolador ATmega"
    },
    {
      "name": "LEDs TX y RX",
      "description": "Estos diodos LEDs indican cuándo se realiza una comunicación entre Arduino y el ordenador. Parpadean rápidamente cuando se carga el programa así como durante la comunicación serie. Útil para la depuración."
    },
    {
      "name": "Pins Digitales",
      "description": "Usar estos pins con las instrucciones digitalRead(), digitalWrite(), y analogWrite(). La instrucción analogWrite() solo trabaja con los pins con el símbolo PWM"
    },
    {
      "name": "Pin 13 LED",
      "description": "El único componente que actúa como dispositivo de salida incorporado a su Arduino Uno. Lo usará cuando ejecute su primer programa. Este LED es muy útil para la depuración."
    },
    {
      "name": "Microcontrolador ATmega",
      "description": "El corazón de la placa Arduino Uno"
    },
    {
      "name": "Led de Encendido",
      "description": "Indica que la placa Arduino está siendo alimentada. Útil para la depuración."
    },
    {
      "name": "Pines GND y 5V",
      "description": "Usar estos pins para proporcionar una tensión de +5V y masa para los circuitos externos a la placa."
    },
    {
      "name": "Entradas Analógicas",
      "description": "Usar estos pins con la instrucción analogRead()"
    }
  ],
  "description": "Diagrama de la placa Arduino Uno con etiquetas señalando cada uno de sus componentes principales.",
  "source": "Arduino Project Book"
}
```

---

## Montaje de la base de madera

```json
{
  "type": "diagram",
  "id": "diagram-02",
  "page": 13,
  "title": "Montaje de la base de madera",
  "caption": "Montaje de la base de madera del Kit de Inicio",
  "elements": [
    "Separar con cuidado en piezas el tablero de madera",
    "Presionar hasta separar todas las piezas",
    "Colocar las piezas marcadas con una 'A' dentro de los agujeros de las esquinas, con la finalidad de crear el soporte para la base",
    "Sujetar la placa Arduino Uno a la base de madera usando tres tornillos. Tener cuidado al apretarlos.",
    "Retire con cuidado el papel protector de la placa de pruebas",
    "Pegar la placa de pruebas sobre la base de madera, próxima a la Arduino Uno"
  ],
  "description": "Secuencia de pasos ilustrados para montar la base de madera precortada que aloja la placa Arduino Uno y la placa de pruebas.",
  "source": "Arduino Project Book"
}
```

---

## Otras cosas que va a necesitar

- Batería de 9 voltios
- Una caja a la que le ha perforado unos agujeros
- Una pequeña fuente de luz como una linterna
- Herramientas básicas como un destornillador
- Material conductor como papel de aluminio o malla de cobre
- Un conector con cable para la batería de 9V
- Papel de color
- Cualquier conector con cable que tenga por lo menos un interruptor o un pulsador, y que esté dispuesto a usar, valdrá para realizar este trabajo
- Tijeras
- Soldador de estaño y estaño
- Un viejo CD o DVD (solo es necesario en el Proyecto 15)
- Cinta y goma

---

## La preparación: Instalación del IDE de Arduino

Antes de que comience a controlar el mundo a su alrededor, necesita descargar el Entorno Integrado de Desarrollo (IDE) de Arduino para poder programarlo.

El IDE de Arduino le permite escribir los programas y cargarlos a su placa Arduino.

Descargar la última versión del IDE desde: arduino.cc/download

Coloque la placa Arduino y el cable USB cerca de su ordenador. Todavía no los conecte.

### Instalación en Windows

1. Después de finalizar la descarga hacer doble click sobre el fichero "Install Arduino". Si se abre una ventana emergente de seguridad de Windows, pulsar sobre "Ejecutar" o "Permitir" y aceptar los términos de la licencia al pulsar sobre el botón "I Agree". Pulsar sobre "Next" para seleccionar la carpeta en donde se va a instalar el IDE y entonces pulsar sobre el botón "Install".

2. Después de que el software de Arduino se haya instalado, conectar la placa Arduino al ordenador a través del cable USB. La placa se alimenta automáticamente a través de esta conexión USB del ordenador, en ese momento el LED verde (etiquetado como ON) en la placa Arduino se encenderá.

3. Windows inicia el proceso de instalación del controlador cuando la placa se conecta. El ordenador no podrá encontrar el controlador sin ayuda, es necesario indicarle en qué carpeta se localiza.

   a) Windows XP: Si el programa de actualización de Windows pregunta acerca de la ruta del controlador, seleccionar "Sí, sólo esta vez" y después "Instalar desde una lista o una ubicación específica (recomendado)";

   b) Vista o Windows 7: En Windows 7 si se abre una ventana emergente en donde le pide si instalar el controlador automáticamente o buscarlo en el ordenador escoger buscar el controlador en el ordenador. En Vista, continuar con el paso siguiente al escoger la opción recomendada.

4. Si la instalación no comienza automáticamente, pulsar sobre el botón de Inicio y abrir el Panel de Control. Entonces, dirigirse al Administrador de Dispositivos siguiendo estos pasos:

   a) Windows XP: Cambiar a Vista Clásica → Sistema → Hardware → Administrador de Dispositivos

   b) Windows Vista: Vista Clásica → Administrador de Dispositivos

   c) Windows 7: Sistema y Seguridad → Sistema → Administrador de Dispositivos

   d) Buscar el dispositivo Arduino dentro de la categoría "Otros Dispositivos" o "Dispositivos Desconocidos" y seleccionar "Actualizar Controlador" o "Actualizar Controlador del programa" al pulsar el botón derecho del ratón.

5. Pulsar sobre "Examinar" y seleccionar la carpeta "Controladores" (no la carpeta de los controladores USB FTDI) de la carpeta de Arduino. Presionar "OK" y "Siguiente". Si se abre una ventana emergente con el logo de Windows, pulsar sobre "Continuar de todas formas". Ahora Windows instala el controlador.

6. Dentro de la ventana de Administración de Dispositivos, bajo la categoría de "Puertos (COM & LPT)" podrá ver un puerto similar a "Arduino UNO (COM4)".

### Instalación en Mac OS X 10.5 y posteriores

1. Si usted está usando la versión 10.8 (Mountain Lion) o posterior, dirigirse a las "Preferencias del Sistema" y abrir el panel de "Seguridad & Privacidad". En la pestaña "General" bajo el encabezado "Permitir descargar aplicaciones desde", hacer click en "Desde cualquier lugar".

2. Una vez que el IDE de Arduino se ha descargado, hacer doble click sobre el fichero zip para descomprimirlo.

3. Copiar la aplicación Arduino a la carpeta de Aplicaciones, o cualquier otro sitio en donde desee instalar el software.

4. Conectar la placa Arduino al ordenador a través del cable USB. La placa se alimenta automáticamente a través de esta conexión USB del ordenador, en ese momento el LED verde (etiquetado como ON) en la placa Arduino se encenderá.

5. No necesita instalar ningún controlador para trabajar con la placa.

6. Dependiendo de la versión del sistema operativo OS X que se esté ejecutando, podría aparecer una ventana emergente con un mensaje pidiéndole si desea abrir las "Preferencias del Sistema". Hacer click sobre el botón de "Preferencias de Red" y después en "Aplicar".

7. El gestor de ventanas Uno de Mac mostrará "No configurado", pero el entorno IDE ya está listo. Puede salir de "Preferencias del Sistema".

### Instalación en Linux

Si usted está usando Linux, por favor visite la página web para ver cómo se hace: arduino.cc/linux

### Cargar el primer programa: Blink

1. Hacer doble click sobre la aplicación de Arduino para abrirla. Si el entorno IDE está en un lenguaje que no es el suyo, puede cambiarlo al seleccionar el menú "Archivo" y escoger "Preferencias". En la ventana que se abre y dentro del "Editor de idioma" escoger el lenguaje que desee. Reiniciar el programa para que tenga efecto.

2. Navegar para abrir un sketch de ejemplo que hace que el diodo led de la placa Arduino parpadee (la palabra 'sketch' es como se llama a los programas en Arduino). Seleccionar el menú "Archivo" escoger "Ejemplos" a continuación "01.Basics" y por último "Blink".

3. Debería de abrirse una nueva ventana con un texto dentro. Dejar la ventana como está por ahora, y seleccionar su placa Arduino desde: Herramientas > Placa.

4. Escoger el puerto serie en donde su placa Arduino está conectada desde el menú de: Herramientas > Puerto.

   a) En Windows: Probablemente aparecerá con el número más alto de puerto COM. No pasará nada si se equivoca al escoger este número de puerto, simplemente no funcionará.

   b) En Mac: Deberá aparecer algo parecido a /dev/tty.usbmoderm en este sistema. Por lo general aparecen dos, seleccionar uno cualquiera de ellos.

5. Para cargar el Sketch que hace que el diodo led parpadee a su Arduino, presionar el botón Subir en la esquina superior izquierda de la ventana.

6. Debe de ver una barra indicando el progreso de carga del sketch cerca de la esquina inferior derecha del IDE de Arduino, y los diodos led de la placa Arduino con las etiquetas TX y RX estarán parpadeando en el momento de la carga. Si la carga se ha realizado correctamente, el IDE mostrará el mensaje SUBIDO en la esquina inferior izquierda.

7. A los pocos segundos de completar la carga del Sketch, debe de ver como el diodo led amarillo, con la etiqueta L cerca, comienza a parpadear. Si es así, ¡felicidades! Acaba de conseguir programar Arduino para que el diodo led de la placa parpadee.

A veces su nuevo Arduino está ya programado con el Sketch de parpadeo, así que no puede saber si realmente lo acaba de programar. En este caso, cambiar dentro de la instrucción "delay" el tiempo que aparece entre paréntesis a 100, y volver a subir de nuevo el sketch de parpadeo. Ahora el diodo led de la placa debe de parpadear más rápido.

---

## Proyecto 01: Conozca sus herramientas

**Descubra:** La teoría básica de la electricidad, cómo se trabaja con una placa de prueba y cómo se conectan componentes en serie y en paralelo.

**Tiempo:** 30 MINUTOS

**Nivel:** bajo

### Introducción

La electricidad es un tipo de energía, como el calor, la gravedad o la luz. La energía eléctrica fluye a través de los conductores, como los cables. Puede transformar la energía eléctrica en otras formas de energía para hacer algo interesante, como encender una luz o hacer algo de ruido a través de un altavoz.

Los componentes que podría usar para hacer esto, como altavoces o bombillas, son transductores eléctricos. Los transductores transforman otros tipos de energía en energía eléctrica y viceversa. Los componentes que transforman otras formas de energía en energía eléctrica son a menudo llamados sensores, y los componentes que convierten la energía eléctrica en otras formas de energía se conocen algunas veces con el nombre de actuadores. Construirá circuitos para hacer que la electricidad circule a través de diferentes componentes. Se trata de circuitos en bucles cerrados mediante cables con una fuente de energía (como una batería) y algún componente que haga algo útil con la energía; este componente se suele llamar carga.

En un circuito, la electricidad fluye desde un punto con el potencial de energía más alto (normalmente se conoce como el positivo o + de la fuente de energía) a un punto con el potencial de energía más bajo. La masa (a menudo representado con el signo "-" o GND) es normalmente el punto con el menor potencial de energía en un circuito. En los circuitos que va a construir la corriente eléctrica solo circula en una dirección. Este tipo de circuitos se llaman de corriente directa o DC. Por otro lado en los circuitos con corriente alterna (AC) la electricidad cambia de dirección 50 o 60 veces por segundo (dependiendo de donde usted viva). Este es el tipo de electricidad que puede encontrar en un enchufe de la pared de una habitación.

Existen una serie de términos con los cuales debe de familiarizarse cuando trabaje con circuitos eléctricos. **Corriente** (medida en amperios, o amps; con el símbolo A) es la cantidad de carga eléctrica que circula a través de un determinado punto de un circuito. **Tensión** (medido en voltios; con el símbolo V) es la diferencia de energía entre un punto de un circuito y otro que se toma como referencia. Y por último, **resistencia** (medida en ohmios; con el símbolo Ω) representa cuánto se opone un componente a que la energía eléctrica fluya a través de él.

```json
{
  "type": "diagram",
  "id": "diagram-03",
  "page": 23,
  "title": "Analogía del acantilado para entender la electricidad",
  "caption": "Figura 1. Analogía del acantilado con rocas para explicar tensión, corriente y resistencia.",
  "elements": [
    "Acantilado (Tensión V)",
    "Rocas deslizándose (Corriente I)",
    "Arbustos en la pendiente (Resistencia R)"
  ],
  "description": "Diagrama que utiliza la analogía de un acantilado con rocas deslizándose para explicar los conceptos de tensión, corriente y resistencia. La altura del acantilado representa la tensión, el número de rocas representa la corriente, y los arbustos que frenan las rocas representan la resistencia.",
  "source": "Arduino Project Book"
}
```

### Un par de cosas sobre los circuitos

- En un circuito es necesario que exista un camino desde la fuente de energía (alimentación) hasta el punto de menor energía (masa). Si no existe un camino por donde la energía se pueda mover, el circuito no funcionará.
- Toda la energía eléctrica es utilizada por los componentes que forman parte de un circuito. Cada componente convierte parte de esa energía en otra forma de energía. En cualquier circuito, todas las tensiones se convierten en otra forma de energía (luz, calor, sonido, etc.).
- El flujo de corriente en un punto específico en un circuito siempre será el mismo que entra y que sale.
- La corriente eléctrica siempre busca el camino de menor resistencia hacia masa. Si existen dos caminos posibles, la mayoría de la corriente eléctrica circulará por el camino con menor resistencia. Si dispone de una conexión en donde se conectan los puntos de alimentación y masa juntos directamente y sin resistencia, se producirá un cortocircuito; la corriente será demasiado grande al no disponer de una resistencia que reduzca su valor. En un cortocircuito, la fuente de alimentación y los cables convierten la energía eléctrica en luz y calor, se producirán chispas y/o una explosión. Si alguna vez ha cortocircuitado una batería y ha visto chispas sabrá lo peligroso que un cortocircuito puede ser.

### ¿Qué es una placa de pruebas?

La placa de pruebas es el primer lugar en donde montará sus circuitos. La que se incluye en el kit no necesita soldar nada para montar los componentes encima, es como un juego de LEGO en formato electrónico. Las filas verticales y horizontales de la placa de pruebas, como se muestra en la figura 3, conducen la electricidad a través de los conectores de metal fino que hay debajo del plástico con agujeros.

```json
{
  "type": "diagram",
  "id": "diagram-04",
  "page": 24,
  "title": "Anatomía de una placa de pruebas",
  "caption": "Figura 3. Partes de una placa de pruebas",
  "elements": [
    "Filas horizontales (conexión eléctrica)",
    "Filas verticales (buses de alimentación)",
    "Canal central (separación entre los dos lados)",
    "Buses de alimentación (+) y (-)",
    "Área de montaje"
  ],
  "description": "Diagrama que muestra la estructura interna de una placa de pruebas, incluyendo las tiras metálicas conductoras que conectan los agujeros en filas horizontales y verticales.",
  "source": "Arduino Project Book"
}
```

### Sus primeros componentes

```json
{
  "type": "image",
  "id": "image-02",
  "page": 26,
  "title": "LED, resistencia y pulsador",
  "caption": "Componentes básicos: LED (cátodo y ánodo), resistencia y pulsador.",
  "description": "Ilustración de un LED rojo con sus terminales etiquetados (cátodo y ánodo), una resistencia con bandas de colores, y un pulsador de cuatro patillas.",
  "elements": [
    "LED (Diodo Emisor de Luz)",
    "Resistencia",
    "Pulsador"
  ],
  "source": "Arduino Project Book"
}
```

- **LED:** Un LED, o diodo emisor de luz, es un componente que convierte la energía eléctrica en energía luminosa. Los LEDs son componentes que tienen polaridad, esto quiere decir que solo circula corriente a través de ellos en una sola dirección. El terminal más largo del LED es llamado ánodo, se conectará a la alimentación. El terminal más corto es el cátodo y se conectará a masa. Cuando la tensión es aplicada al ánodo del led y el cátodo está conectado a masa, el LED emite luz.

- **Resistencia:** Una resistencia es un componente que se opone al paso de la energía eléctrica. Transforma parte de la energía eléctrica en calor. Si se coloca una resistencia en serie con un componente como un LED, el resultado será que el diodo led recibe menos energía al consumir la resistencia esa energía que el LED no recibe. Esto permite poder alimentar a los componentes con la cantidad de energía que necesitan. Puede usar una resistencia en serie con un LED para evitar que reciba demasiada tensión. Sin la resistencia, el led podría brillar con gran intensidad durante unos momentos, pero rápidamente se quemará.

- **Pulsador:** Un interruptor interrumpe la circulación de la electricidad, abriendo el circuito cuando se abre. Cuando un interruptor está cerrado, permite que el circuito se alimente. Hay muchos tipos de interruptores. Algunos de los que se incluye en el kit se llaman interruptores momentáneos, o pulsadores, porque solo se cierran cuando son presionados.

### Montando el circuito

```json
{
  "type": "diagram",
  "id": "diagram-05",
  "page": 27,
  "title": "Circuito con pulsador, resistencia y LED",
  "caption": "Figura 8. Montaje del primer circuito interactivo con pulsador, resistencia y LED.",
  "elements": [
    "Arduino Uno (como fuente de alimentación)",
    "Pulsador",
    "Resistencia de 220Ω",
    "LED"
  ],
  "description": "Diagrama de montaje en placa de pruebas de un circuito con un pulsador, una resistencia de 220 ohmios y un LED. Arduino se utiliza solo como fuente de alimentación.",
  "source": "Arduino Project Book"
}
```

**Pasos:**

1. Va a usar la placa Arduino en este proyecto, pero solo como una fuente de alimentación. Cuando la conecte a un puerto USB o a una batería de 9V, Arduino suministrará una tensión de 5V entre su terminal de 5V y su terminal de masa los cuales puede usar. 5V = 5 voltios, lo verá escrito de esta forma muchas veces.

2. Si la placa Arduino está conectada a una batería o a un ordenador vía USB, ¡desconectarla antes de montar el circuito!

3. Conectar un cable rojo al terminal de 5V de Arduino y conectar el otro extremo de este cable en una de las columnas del bus de la placa de pruebas marcada con el símbolo +. Conectar el terminal de masa de Arduino con un cable negro a la línea adyacente en donde se ha conectado el cable rojo y en la columna marcada con el símbolo -. Es útil para guardar una relación entre los colores de los cables (rojo para la alimentación y negro para la masa) a lo largo del circuito.

4. Ahora que ha alimentado la placa, coloque el pulsador en el centro de la placa de pruebas. El pulsador se sitúa en el centro en una dirección. La parte curva de los terminales del pulsador apuntan hacia el centro de la placa.

5. Usar una resistencia de 220 ohmios para conectar la alimentación (columna marcada con +) a uno de los lados del pulsador. Las ilustraciones de las resistencias en este libro son con 4 bandas. Su kit puede tener una mezcla de resistencias con 4 y 5 bandas. Usar la ilustración adjunta para verificar que está usando la resistencia adecuada en este proyecto. Mirar la página 41 para obtener más información sobre el código de colores de las resistencias. En el otro lado del pulsador, conectar el ánodo (terminal largo) del diodo LED. Con un cable conectar el cátodo (terminal corto) del LED a masa. Cuando esté todo listo, enchufar el cable USB a la placa Arduino.

**ÚSALO:** Una vez que todo está preparado, presionar el botón. El diodo LED deberá encenderse. ¡Le felicito, acaba de conseguir que el circuito funcione! Una vez que se haya cansado de presionar el botón para encender la luz, es el momento de mejorar las cosas añadiendo un segundo botón.

### Circuito en serie

**LOS COMPONENTES EN SERIE SE CONECTAN UNO DESPUÉS DE OTRO**

Una vez que ha desconectado la fuente de alimentación añadir un pulsador cerca del que ya está montado en la placa de pruebas. Conectar un cable para conectarlos en serie como se muestra en la figura 10. Conectar el ánodo (terminal largo) del LED al segundo pulsador. Conectar el cátodo del LED a masa. Alimentar de nuevo la placa Arduino: ahora para encender el LED, necesita presionar los dos pulsadores a la vez. Puesto que están en serie, ambos deben ser cerrados para que el circuito funcione.

```json
{
  "type": "diagram",
  "id": "diagram-06",
  "page": 29,
  "title": "Circuito en serie con dos pulsadores",
  "caption": "Figura 10. Dos pulsadores en serie.",
  "elements": [
    "Arduino Uno",
    "Pulsador 1",
    "Pulsador 2",
    "Resistencia de 220Ω",
    "LED"
  ],
  "description": "Diagrama de un circuito en serie con dos pulsadores. Ambos deben ser presionados simultáneamente para que el LED se encienda.",
  "source": "Arduino Project Book"
}
```

### Circuito en paralelo

**LOS COMPONENTES EN PARALELO SE CONECTAN UNO AL LADO DEL OTRO**

Ahora que ha dominado el arte de las cosas en serie, es el momento de conectar los pulsadores en paralelo. Dejar los pulsadores y el diodo LED donde están, pero quitar la conexión entre los dos pulsadores. Colocar un cable desde cada pulsador a la resistencia. Unir el otro extremo de cada pulsador al diodo LED, como muestra la figura 12. Ahora cuando se presiona cualquier botón, el circuito funciona y el diodo led se enciende.

```json
{
  "type": "diagram",
  "id": "diagram-07",
  "page": 30,
  "title": "Circuito en paralelo con dos pulsadores",
  "caption": "Figura 12. Dos pulsadores en paralelo.",
  "elements": [
    "Arduino Uno",
    "Pulsador 1",
    "Pulsador 2",
    "Resistencia de 220Ω",
    "LED"
  ],
  "description": "Diagrama de un circuito en paralelo con dos pulsadores. Presionar cualquiera de los dos pulsadores enciende el LED.",
  "source": "Arduino Project Book"
}
```

### Entendiendo la Ley de Ohm

```json
{
  "type": "diagram",
  "id": "diagram-08",
  "page": 31,
  "title": "Círculo de la Ley de Ohm",
  "caption": "Círculo mnemotécnico para recordar las relaciones entre voltaje, corriente y resistencia.",
  "elements": [
    "V (Tensión)",
    "I (Corriente)",
    "R (Resistencia)"
  ],
  "description": "Círculo dividido en tres partes: V arriba, I abajo a la izquierda, R abajo a la derecha. Permite recordar las fórmulas: V = I × R, I = V / R, R = V / I.",
  "source": "Arduino Project Book"
}
```

Corriente, voltaje y resistencia están todos relacionados. Cuando cambia uno de estos parámetros en un circuito, afecta a los demás. La relación que existe entre ellos se conoce como ley de Ohm, en honor a Georg Simon Ohm quien la descubrió.

**TENSIÓN (V) = CORRIENTE (I) × RESISTENCIA (R)**

Al medir intensidad (amperios) en los circuitos que vaya a montar, los valores serán del rango de miliamperios. Un miliamperio vale la milésima parte de un amperio.

En el circuito de la figura 5 se aplica una tensión de 5 voltios. La resistencia tiene un valor de 220 ohmios. Para averiguar la corriente que usa el LED, reemplazar los valores en la ecuación de la Ley de Ohm. Por tanto I = V / R ; I = 5 / 220 = 0.023 amperios, este valor equivale a la 23 milésima parte de un amperio, o 23 miliamperios (23mA) que consume el diodo LED. Este valor es casi el máximo con el cual puede trabajar con seguridad este tipo de diodo LED, es por eso que se utiliza una resistencia de 220 ohmios.

---

## Proyecto 02: Interface de nave espacial

**Descubra:** entrada y salida digital, su primer programa, las variables

**Tiempo:** 45 MINUTOS

**Proyecto en el que se basa:** 1

**Nivel:** bajo

### Introducción

Ahora que tiene los fundamentos de la electricidad bajo control, es el momento de pasar a controlar cosas con su Arduino. En este proyecto, va a construir algo que podría ser una interface de una nave espacial de una película de ciencia ficción de los años 70. Va a montar un panel de control con un pulsador y luces que se encienden cuando presiona el pulsador. Puede decidir que indican las luces "Activar hiper-velocidad" o "¡Disparar los rayos laser!". Un diodo LED verde permanecerá encendido hasta que pulse el botón. Cuando Arduino reciba la señal del botón pulsado, la luz verde se apaga y se encienden otras dos luces que comienzan a parpadear.

Los terminales o pins digitales de Arduino solo pueden tener dos estados: cuando hay voltaje en un pin de entrada y cuando no lo hay. Este tipo de entrada es normalmente llamada digital (o algunas veces binaria, por tener dos estados). Estos estados se refieren comúnmente como HIGH (alto) y LOW (bajo). HIGH es lo mismo que decir "¡aquí hay tensión!" y LOW indica "¡no hay tensión en este pin!". Cuando pone un pin de SALIDA (OUTPUT) en estado HIGH utilizando el comando llamado digitalWrite(), está activándolo. Si mide el voltaje entre este pin y masa, obtendrá una tensión de 5 voltios. Cuando pone un pin de SALIDA (OUTPUT) en estado LOW, está apagándolo.

Los pins digitales de Arduino pueden trabajar como entradas o como salidas. En su código, los configurará dependiendo de cuál sea su función dentro del circuito. Cuando los pins se configuran como salidas, entonces podrá encender componentes como los diodos LEDs. Si se configuran como entradas, podrá verificar si un pulsador está siendo presionado o no. Ya que los pins 0 y 1 son usados para comunicación con el ordenador, es mejor comenzar con el pin 2.

### Montando el circuito

```json
{
  "type": "diagram",
  "id": "diagram-09",
  "page": 35,
  "title": "Circuito de la Interface de Nave Espacial",
  "caption": "Figura 2. Esquema del circuito de la Interface de Nave Espacial.",
  "elements": [
    "Arduino Uno",
    "Pulsador (SW1) - Activar",
    "LED Verde (D1) - Pin 3",
    "LED Rojo (D2) - Pin 4",
    "LED Rojo (D3) - Pin 5",
    "Resistencia R1 10KΩ",
    "Resistencias R2, R3, R4 220Ω"
  ],
  "description": "Esquema eléctrico del circuito con un pulsador conectado al pin 2 y tres LEDs conectados a los pins 3, 4 y 5 a través de resistencias de 220 ohmios.",
  "source": "Arduino Project Book"
}
```

**Pasos:**

1. Conectar la placa de pruebas a las conexiones de 5V y masa de Arduino, igual que en el proyecto anterior. Colocar los dos diodos LED rojos y el LED verde sobre la placa de pruebas. Conectar el cátodo (patilla corta) de cada LED a masa a través de una resistencia de 220 ohmios. Conectar el ánodo (patilla larga) del LED verde al pin 3 de Arduino. Conectar los ánodos de los LEDs rojos a los pins 4 y 5 respectivamente.

2. Colocar el pulsador sobre la placa de pruebas como hizo en el proyecto anterior. Conectar un extremo a la alimentación y el otro terminal del pulsador al pin 2 de Arduino. También necesita añadir una resistencia de 10K ohmios desde masa al pin del interruptor que va conectado a Arduino. Esta resistencia de puesta a cero conecta el pin a masa cuando el pulsador está abierto, así que Arduino lee LOW cuando no hay tensión en ese pin del pulsador.

### El código

```cpp
int switchState = 0;

void setup() {
  pinMode(3, OUTPUT);
  pinMode(4, OUTPUT);
  pinMode(5, OUTPUT);
  pinMode(2, INPUT);
}

void loop() {
  switchState = digitalRead(2);
  // Esto es un comentario

  if (switchState == LOW) {
    // el pulsador no está presionado
    digitalWrite(3, HIGH); // LED verde
    digitalWrite(4, LOW);  // LED rojo
    digitalWrite(5, LOW);  // LED rojo
  }
  else { // el pulsador está presionado
    digitalWrite(3, LOW);
    digitalWrite(4, LOW);
    digitalWrite(5, HIGH);

    delay(250); // en pausa un cuarto de segundo
    // cambiar el estado de los LEDs
    digitalWrite(4, HIGH);
    digitalWrite(5, LOW);
    delay(250); // en pausa un cuarto de segundo
  } // Volver al comienzo de la instrucción loop
}
```

**Conceptos clave:**

- **Mayúsculas y minúsculas:** Poner atención a la hora de escribir en mayúsculas y minúsculas dentro del código. Por ejemplo, `pinMode` es el nombre de una instrucción, pero `pimnode` producirá un error.
- **Comentarios:** Si alguna vez quiere usar el lenguaje natural dentro del programa, puede escribir un comentario. Los comentarios son notas que se dejan para recordar lo que hace el programa, además el microcontrolador ignora estos comentarios. Para añadir un comentario escribir antes dos líneas inclinadas `//` y a continuación escribir lo que se desee anotar.
- **if()...else:** Un estamento `if()` en programación compara dos cosas, y determina si la comparación es verdadera o falsa. Dependiendo de este resultado se lleva a cabo una acción u otra. Cuando en programación se comparan dos cosas hay que usar dos signos de igual `==`. Si solo se usa un signo de igual, simplemente se le asigna un valor a una variable en lugar de compararla con algo.
- **digitalWrite():** Es la instrucción que permite poner +5V o 0V en un pin de salida. `digitalWrite()` tiene dos argumentos: el número del pin a controlar y qué valor se coloca en ese pin, HIGH o LOW.
- **delay():** Permite que Arduino deje de ejecutar cualquier cosa que esté haciendo durante un periodo de tiempo. Dentro del argumento de la instrucción `delay()` se establece el número de milisegundos que Arduino estará parado antes de ejecutar la siguiente parte del código. Hay 1000 milisegundos en un segundo. `delay(250)` producirá una pausa de un cuarto de segundo.

**Pseudo código:**

```
Si el switchState esta LOW:
  encender el LED verde
  apagar los LEDs rojos
Si el switchState esta HIGH:
  apagar el LED verde
  encender los LEDs rojos
```

---

## Proyecto 03: Medidor de enamoramiento

**Descubra:** entrada analógica, usando el monitor serie

**Tiempo:** 45 MINUTOS

**Proyectos en los que se basa:** 1, 2

**Nivel:** bajo

### Introducción

Aunque los pulsadores e interruptores son útiles, existen muchas más cosas en el mundo físico que solo encender y apagar algo. Aunque Arduino es una herramienta digital, es posible adquirir con él información de sensores analógicos para medir parámetros físicos como la temperatura o el nivel de iluminación. Para poder hacerlo, Arduino dispone en su interior de un Convertidor Analógico - Digital (ADC), el cual transforma una señal analógica presente en su entrada en una señal digital. Las entradas analógicas de Arduino son los pins A0 - A5 las cuales pueden proporcionar un valor entre 0 y 1023, que equivale a un rango de 0 voltios a 5 voltios, por ejemplo, si la tensión de una de las entradas analógicas vale 2.5V el valor que proporciona el convertidor ADC vale 512.

Va a usar un medidor de temperatura para medir la temperatura de la piel. Este componente varía su tensión de salida dependiendo de la temperatura que detecta. Dispone de tres terminales: uno se conecta a masa, otro se conecta a la alimentación y el tercero produce una tensión de salida variable que se aplica a Arduino. En el sketch de este proyecto, se va a leer la tensión de salida del sensor y usarla para encender o apagar unos diodos LEDs, como indicadores de la temperatura de su piel (lo enamorado que está). Existen varios modelos de sensores de temperatura. Este modelo, el TMP36, es utilizado porque los cambios de la tensión de salida son directamente proporcionales a la temperatura en grados Celsius.

El IDE de Arduino incorpora una herramienta llamada monitor serie el cual le proporciona información de lo que el microcontrolador está haciendo. Utilizando el monitor serie, se puede conseguir información acerca del estado de sensores, y así tener una idea de lo que sucede en un circuito y en el código cuando se está ejecutando.

### Montando el circuito

```json
{
  "type": "diagram",
  "id": "diagram-10",
  "page": 46,
  "title": "Circuito del Medidor de Enamoramiento",
  "caption": "Figura 2. Montaje del sensor de temperatura TMP36 y LEDs indicadores.",
  "elements": [
    "Arduino Uno",
    "Sensor de temperatura TMP36 (pin central a A0)",
    "LEDs en pins 2, 3, 4",
    "Resistencias de 220Ω"
  ],
  "description": "Diagrama de montaje del sensor de temperatura TMP36 conectado a la entrada analógica A0, y tres LEDs conectados a los pins digitales 2, 3 y 4 a través de resistencias de 220 ohmios.",
  "source": "Arduino Project Book"
}
```

**Pasos:**

1. Tal como lo ha estado haciendo en proyectos anteriores, conectar la placa de pruebas a la alimentación y a masa.

2. Conectar el cátodo (terminal corto) de cada diodo LED a masa a través de una resistencia en serie de 220 ohmios. Conectar los ánodos de los LEDs a los terminales 2, 3 y 4 respectivamente. Estos diodos serán los indicadores de este proyecto.

3. Colocar el sensor de temperatura TMP36 sobre la placa de pruebas con la parte curvada de su cuerpo mirando hacia el lado contrario de la placa Arduino (la colocación de los terminales es importante). Conectar el terminal de la izquierda de la cara plana del cuerpo a la alimentación y el terminal derecho a masa. Conectar el pin central al pin A0 de la placa Arduino. Este pin es la entrada analógica 0.

### El código

```cpp
const int Pin_del_Sensor = A0;
const float Temperatura_de_Referencia = 20.0;

void setup() {
  Serial.begin(9600); // Abrir el puerto serie
  for(int NumeroPin=2; NumeroPin<5; NumeroPin++){
    pinMode(NumeroPin,OUTPUT);
    digitalWrite(NumeroPin,LOW);
  }
}

void loop() {
  int Valor_del_Sensor = analogRead(Pin_del_Sensor);
  Serial.print("Valor del sensor: ");
  Serial.print(Valor_del_Sensor);

  // Convertir la lectura ADC a tensión
  float Tension = (Valor_del_Sensor/1024.0) * 5.0 ;
  Serial.print(", Voltios: ");
  Serial.print(Tension);
  Serial.print(", grados C: ");

  // Convertir la tensión en temperatura en valores en grados
  float Temperatura = (Tension - 0.5) * 100;
  Serial.println(Temperatura);

  if(Temperatura < Temperatura_de_Referencia){
    digitalWrite(2, LOW);
    digitalWrite(3, LOW);
    digitalWrite(4, LOW);
  }
  else if(Temperatura >= Temperatura_de_Referencia && Temperatura < Temperatura_de_Referencia + 2){
    digitalWrite(2, HIGH);
    digitalWrite(3, LOW);
    digitalWrite(4, LOW);
  }
  else if(Temperatura >= Temperatura_de_Referencia + 2 && Temperatura < Temperatura_de_Referencia + 4){
    digitalWrite(2, HIGH);
    digitalWrite(3, HIGH);
    digitalWrite(4, LOW);
  }
  else{
    digitalWrite(2, HIGH);
    digitalWrite(3, HIGH);
    digitalWrite(4, HIGH);
  }
  delay(1);
}
```

**Conceptos clave:**

- **Constantes:** Las constantes son similares a las variables (guardar información) las cuales permiten usar un único nombre con los datos del programa, pero a diferencia de las variables su contenido no se puede cambiar. Se define una constante con un nombre para la entrada analógica (`Pin_del_Sensor`) y otra para la temperatura de referencia (`Temperatura_de_Referencia`).
- **float:** Tipo de variable en coma flotante. Este tipo de número tiene un punto decimal, y es usado para números que pueden ser expresados como fracciones o para expresar números con decimales.
- **Serial.begin():** Inicializa el puerto serie para establecer la velocidad de comunicación con el ordenador. El argumento 9600 establece la velocidad a la que Arduino se comunica con el ordenador, 9600 bits por segundo.
- **for():** La instrucción `for()` define algunos de los pins como salidas digitales dentro de un bucle. Se utiliza para ahorrar tiempo y líneas de código si es necesario definir las propiedades de muchos pins a la vez.
- **analogRead():** Lee la información del sensor. Toma un argumento: de qué pin se va a tomar la información de lectura del sensor. El valor leído está comprendido entre 0 y 1023, y representa indirectamente la tensión que existe en ese pin.
- **Serial.print():** Envía información desde Arduino al ordenador al que está conectado.
- **Serial.println():** Similar a `Serial.print()`, pero añade un salto de línea al final.
- **Operador &&:** Significa "Y" en una sentencia lógica, equivale a la multiplicación. Se utiliza para verificar múltiples condiciones.
- **map():** Cambia la escala de un número de un rango a otro.

**ÚSALO:** Una vez cargado el programa dentro de la tarjeta Arduino, hacer click sobre el icono del monitor serie. Debe de ver que aparece un listado de valores en el siguiente formato: `Valor del sensor: 200, Voltios: .70, grados C: 17`. Coloque sus dedos sobre el sensor mientras está colocado sobre la placa de pruebas y ver qué valores aparecen en el monitor serie. Tomar nota de la temperatura que el sensor detecta cuando está al aire. Cerrar el monitor serie y cambiar el valor de la constante de la temperatura de referencia en el programa al mismo valor que se muestra en el monitor serie cuando el sensor está al aire. Cargar el código de nuevo a la tarjeta Arduino y a continuación poner los dedos sobre el sensor. Como la temperatura aumenta al colocar los dedos, debe de ver como los LEDs se van encendiendo uno a uno. ¡Felicitaciones, el proyecto funciona!

---

## Proyecto 04: Lámpara de mezcla de colores

**Descubra:** salida analógica, cambio de escala de rango

**Tiempo:** 45 MINUTOS

**Proyectos en los que se basa:** 1, 2, 3

**Nivel:** bajo-medio

### Introducción

Hacer que los diodos LEDs parpadeen puede ser divertido, pero ¿se pueden usar para atenuar suavemente la luz que emiten o para producir una mezcla de colores? Se podría pensar que es solo cuestión de disminuir la tensión que se le aplica a un LED para conseguir que su luz se desvanezca.

Arduino no puede variar la tensión de salida de sus pins, solo puede suministrar 5V. Por lo tanto es necesario usar una técnica llamada Modulación por Ancho de Pulso o PWM (en inglés) para desvanecer suavemente la luz de los LEDs. PWM consigue que un pin de salida varíe rápidamente su tensión de alto a bajo (entre 5 y 0V) durante un periodo fijo de tiempo. Este cambio de tensión se realiza tan rápido que el ojo humano no puede verlo. Es similar a la forma en las que se proyectan las películas de cine, se pasan rápidamente un número de imágenes fijas durante un segundo para crear la ilusión de movimiento.

Cuando la tensión del pin cambia rápidamente de alto (HIGH) a bajo (LOW) durante un periodo fijo de tiempo, es como si se pudiese variar el nivel de la tensión de ese pin. El porcentaje de tiempo que un pin está en estado HIGH con respecto al tiempo total (periodo) se conoce con el nombre de relación cíclica. Cuando el pin está en HIGH durante la mitad del periodo y en estado LOW durante la otra mitad, la relación cíclica es del 50%. Una relación cíclica baja hace que el diodo LED tenga una luz mucho más tenue que con una relación cíclica más alta.

La tarjeta Arduino Uno dispone de seis pins que se pueden usar con PWM (los pins digitales 3, 5, 6, 9, 10 y 11), los cuales se pueden identificar por el símbolo ~ que aparece junto a su número sobre la tarjeta.

Para las entradas en este proyecto, se usarán foto resistencias (sensores que cambian su resistencia dependiendo de la cantidad de luz que llegue a su superficie, también se conocen con el nombre de foto células o resistencias dependientes de la luz LDR). Si conecta uno de sus pins a Arduino, se puede medir el cambio de resistencia al analizar los cambios de tensión en ese pin.

### Montando el circuito

```json
{
  "type": "diagram",
  "id": "diagram-11",
  "page": 55,
  "title": "Circuito de la Lámpara de Mezcla de Colores",
  "caption": "Figura 3. Esquema del circuito con foto resistencias y LED RGB.",
  "elements": [
    "Arduino Uno",
    "3 Foto resistencias LDR (A0, A1, A2)",
    "3 Resistencias de 10KΩ",
    "LED RGB (cátodo común)",
    "3 Resistencias de 220Ω",
    "Papel celofán rojo, verde y azul"
  ],
  "description": "Esquema eléctrico del circuito con tres foto resistencias conectadas a las entradas analógicas A0, A1 y A2 a través de divisores de tensión con resistencias de 10K, y un LED RGB conectado a los pins PWM 9, 10 y 11 a través de resistencias de 220 ohmios.",
  "source": "Arduino Project Book"
}
```

**Pasos:**

1. Tal como lo ha estado haciendo en proyectos anteriores, conectar la placa de pruebas a la alimentación y a masa.

2. Colocar las tres foto resistencias en el centro que divide la placa de pruebas. Conectar un terminal o pin de cada foto resistencia directamente al positivo de la alimentación. El otro extremo se conecta a una resistencia de 10 Kiloohmios la cual se conecta a masa. Esta resistencia está en serie con la foto resistencia y juntos forman un divisor de tensión. La tensión que aparece en el punto de unión de estos dos componentes es proporcional a la relación entre sus resistencias, según la Ley de Ohm. Como el valor de la foto resistencia cambia cuando la luz incide en ella, la tensión en este punto de unión también cambia. Conectar el punto de unión entre la foto resistencia y la resistencia de 10K al pin de entrada analógico A0, A1 y A2 respectivamente usando un cable para realizar la conexión.

3. Coger las tres láminas de papel celofán y colocar cada una sobre cada foto resistencia. Colocar el celofán rojo sobre la foto resistencia conectada a la entrada A0, el verde sobre la que se conecta a la entrada A1, y el azul sobre la conectada a la entrada A2. Cada uno de estos papeles de colores actúan como filtros de luz y solo dejan pasar una determinada longitud de onda (color) hacia el sensor sobre el que están encima.

4. El LED con cuatro pins es un diodo LED RGB de cátodo común. Este diodo LED tiene los elementos rojo, verde y azul separados en su interior, y una masa común (el cátodo). Al aparecer una diferencia de tensión entre el cátodo y las tensiones de salida de los pins de Arduino en formato PWM (los cuales se conectan a los ánodos del LED a través de unas resistencias de 220 ohmios), será posible hacer que el LED varíe la iluminación de sus tres colores. Observar que el pin más largo del LED, insertado en la placa de pruebas, se conecta a masa. Conectar los otros tres pins del LED a los pins digitales 9, 10 y 11 de Arduino y en serie con cada uno de ellos una resistencia de 220 ohmios.

### El código

```cpp
const int PinLedVerde = 9;
const int PinLedRojo = 11;
const int PinLedAzul = 10;
const int PinEntradaLDR_Rojo = A0;
const int PinEntradaLDR_Verde = A1;
const int PinEntradaLDR_Azul = A2;

int ValorSensorRojo = 0;
int ValorSensorVerde = 0;
int ValorSensorAzul = 0;
int ValorRojo = 0;
int ValorVerde = 0;
int ValorAzul = 0;

void setup(){
  Serial.begin(9600);
  pinMode(PinLedVerde,OUTPUT);
  pinMode(PinLedRojo,OUTPUT);
  pinMode(PinLedAzul,OUTPUT);
}

void loop(){
  ValorSensorRojo = analogRead(PinEntradaLDR_Rojo);
  delay(5);
  ValorSensorVerde = analogRead(PinEntradaLDR_Verde);
  delay(5);
  ValorSensorAzul = analogRead(PinEntradaLDR_Azul);

  Serial.print("Mapa de valores sensores \t Rojo: ");
  Serial.print(ValorSensorRojo);
  Serial.print("\t Verde: ");
  Serial.print(ValorSensorVerde);
  Serial.print("\t Azul: ");
  Serial.print(ValorSensorAzul);

  ValorRojo = ValorSensorRojo/4;
  ValorVerde = ValorSensorVerde/4;
  ValorAzul = ValorSensorAzul/4;

  Serial.print("Mapa de valores de los sensores \t Rojo: ");
  Serial.print(ValorRojo);
  Serial.print("\t Verde: ");
  Serial.print(ValorVerde);
  Serial.print("\t Azul: ");
  Serial.print(ValorAzul);

  analogWrite(PinLedRojo, ValorRojo);
  analogWrite(PinLedVerde, ValorVerde);
  analogWrite(PinLedAzul, ValorAzul);
}
```

**Conceptos clave:**

- **analogWrite():** La instrucción que cambia el brillo del diodo LED a través de PWM. Necesita dos argumentos, el pin sobre el que se escribe y un valor comprendido entre 0 y 255. Este segundo número representa la relación cíclica que aparecerá en el pin que se especifique como salida en Arduino. Un valor de 255 colocará en estado alto (HIGH) el pin de salida durante todo el tiempo de esta señal, haciendo que el diodo LED que está conectado a este pin brille con su máxima intensidad luminosa. Para un valor de 127 colocará el pin a la mitad del tiempo que dura la señal (periodo), haciendo que el diodo LED brille menos que con 255. O se puede fijar el pin en estado bajo (LOW) durante todo el periodo, de manera que el diodo LED no alumbrará. Los valores de lectura del sensor de 0 a 1023 hay que convertirlos a valores de 0 a 255 para trabajar dentro del rango de PWM. Por tanto los valores de lectura del sensor hay que dividirlos por 4.
- **\t:** Equivale a presionar la tecla "tab" del teclado para realizar una tabulación al comienzo de la línea.

**ÚSALO:** Una vez que Arduino ha sido programado y conectado, abrir el monitor serie. El diodo LED probablemente mostrará un color blanco apagado, dependiendo del color de la luz predominante en la habitación donde esté montado este proyecto. Fijarse en los valores de los sensores que aparecen en el monitor serie, si se encuentra en un entorno con una iluminación que no varía, los números que aparecen apenas van a variar, se mantendrán en valores bastante constantes. Apagar la luz de la habitación en donde está el circuito con Arduino montado y ver cómo varían ahora los valores de los sensores en el monitor serie. Usando una linterna, iluminar cada sensor (LDR) individualmente y observar cómo los valores cambian en el monitor serie, además de ver cómo cambia el color que emite el diodo LED.

---

## Proyecto 05: Indicador del estado de ánimo

**Descubra:** mapa de valores, servomotores, utilización de librerías incorporadas

**Tiempo:** 1 HORA

**Proyectos en los que se basa:** 1, 2, 3, 4

**Nivel:** bajo-medio

### Introducción

Los servomotores son un tipo especial de motores que no giran alrededor de un círculo continuamente, sino se mueven a una posición específica y permanecen en ella hasta que se les diga que se muevan de nuevo. Los servos solo suelen girar 180 grados (la mitad de un círculo). Combinando uno de estos motores con un pequeño cartón hecho a mano, será capaz de decirle a la gente si deberían venir y preguntar si necesita o no ayuda para su próximo proyecto.

De la misma forma que se ha usado PWM y los LEDs en el proyecto anterior, los servomotores necesitan un número de impulsos para saber qué ángulo deben de girar. Los impulsos siempre tienen los mismos intervalos (periodo), pero el ancho de estos impulsos puede variar entre 1000 y 2000 micro segundos. Si bien es posible escribir código para generar estos impulsos, el software de Arduino incluye una librería que permite controlar el motor con facilidad.

Ya que el servomotor solo gira 180 grados y la entrada analógica varía de 0 a 1023, es necesario usar una función llamada `map()` para cambiar la escala de los valores que produce el potenciómetro.

### Montando el circuito

```json
{
  "type": "diagram",
  "id": "diagram-12",
  "page": 65,
  "title": "Circuito del Indicador del Estado de Ánimo",
  "caption": "Figura 2. Esquema del circuito con potenciómetro y servomotor.",
  "elements": [
    "Arduino Uno",
    "Potenciómetro (P1) 10K",
    "Servomotor (M1)",
    "Condensador C1 100uF",
    "Condensador C2 100uF"
  ],
  "description": "Esquema eléctrico del circuito con un potenciómetro conectado a la entrada analógica A0 y un servomotor conectado al pin digital 9. Se incluyen condensadores de desacoplo de 100uF.",
  "source": "Arduino Project Book"
}
```

**Pasos:**

1. Conectar la tensión de +5V y la masa a un lado de las tiras verticales de la placa de pruebas desde la placa de Arduino.

2. Conectar el potenciómetro sobre la placa de pruebas y conectar uno de los pins extremos a +5V y el otro extremo a masa. Un potenciómetro es un tipo de divisor de tensión. Cuando se gira el mando del potenciómetro, se cambia la relación de tensión entre el terminal central y el terminal conectado al positivo de alimentación. Es posible leer el valor de este cambio usando una entrada analógica de Arduino. Conectar por tanto el terminal central a la entrada analógica A0. De esta forma se controlará la posición del servomotor.

3. El servo tiene tres cables que salen de su interior. Uno de ellos es la alimentación (color rojo), otro es la masa (color negro), y el tercero (blanco) es el cable de control a través del cual recibirá la información desde Arduino. Conectar tres pins macho de la tira de pins al conector hembra de los cables del servomotor. Conectar estos pins machos a la placa de prueba de manera que cada pin se conecte a una fila diferente. Conectar la alimentación de +5V al cable rojo, la masa al cable negro y el cable blanco al pin 9 de Arduino.

4. Cuando el servomotor empieza a moverse, consume mucha más corriente que si ya estuviese moviéndose. Esto producirá una pequeña caída de tensión en la placa. Si se coloca un condensador de 100uF entre el positivo y la masa cerca del conector del servomotor, se podrá atenuar cualquier caída de tensión que se pueda producir. También se puede colocar un condensador de la misma capacidad entre los extremos del potenciómetro, entre positivo y la masa. Estos condensadores son llamados condensadores de desacoplo porque reducen, o desacoplan, los cambios causados en la línea de alimentación por los componentes del resto del circuito. Hay que tener mucho cuidado al conectar estos condensadores ya que tienen polaridad. Hay que fijarse que uno de los pins del condensador está indicado con un signo menos (-), por tanto deberá conectarse a masa y el otro pin a positivo. Si se equivoca y coloca algún condensador con la polaridad contraria podría explotar.

### El código

```cpp
#include <Servo.h>
Servo MiServo;
int const PinPot= A0;
int ValorPot;
int Angulo;

void setup(){
  MiServo.attach(9);
  Serial.begin(9600);
}

void loop(){
  ValorPot = analogRead(PinPot);
  Serial.print("Posicion del potenciometro: ");
  Serial.print(ValorPot);
  Angulo = map(ValorPot, 0, 1023, 0, 179);
  Serial.print(", Angulo: ");
  Serial.println(Angulo);
  MiServo.write(Angulo);
  delay(100);
}
```

**Conceptos clave:**

- **#include <Servo.h>:** Para usar la librería del servomotor primero tiene que importarla. Esto añade nuevas funciones al sketch desde la librería.
- **Servo MiServo:** Para referirse a la librería servo, es necesario crear un nombre de esta librería en una variable (MiServo). Esto se conoce con el nombre de un objeto.
- **MiServo.attach():** Dentro de la función `setup()` es necesario decirle a Arduino qué pin está unido al servomotor.
- **map():** Para crear valores a partir de la entrada analógica que se puedan usar con el servomotor, se puede hacer de una forma muy fácil usando la instrucción `map()`. Esta instrucción trabaja con escalas de números. En este caso cambia la escala de valores entre 0-1023 a valores entre 0-179. Necesita cinco argumentos: el número que debe de ser escalado, el valor mínimo de la entrada (0), el valor máximo de la entrada (1023), el valor mínimo de la salida (0) y el valor máximo de la salida (179).
- **MiServo.write():** El comando `MiServo.write(Angulo)` mueve el servomotor al ángulo que se indica dentro de la variable Angulo del argumento de esta instrucción.

**ÚSALO:** Una vez que Arduino ha sido programado y alimentado, abrir el monitor serie desde el IDE de Arduino. Deberá de mostrar una serie de valores similares a estos:

```
Posicion del potenciometro: 137 , Angulo: 23
Posicion del potenciometro: 242 , Angulo: 42
```

Cuando se gira el potenciómetro se debe de ver como estos números cambian, además también el servomotor debe de girar a una nueva posición.

---

## Proyecto 06: Theremin controlado por luz

**Descubra:** generar sonido con la función tone(), calibrar sensores analógicos

**Tiempo:** 45 MINUTOS

**Nivel:** bajo-alto

**Proyectos en los que se basa:** 1, 2, 3, 4

### Introducción

Un Theremin es un instrumento que genera sonidos mediante el movimiento de las manos de un músico alrededor de este instrumento. Probablemente habrá oído alguno de ellos en películas de terror. El Theremin detecta dónde se produce el movimiento de la mano del artista en relación a dos antenas al poder leer la variación de la carga capacitiva de estas antenas. Las antenas se conectan a un circuito analógico que crea los sonidos. Una de las antenas controla la frecuencia del sonido y la otra controla el volumen. Aunque Arduino no puede producir de una forma exacta los misteriosos sonidos de este instrumento, sí que es posible emularlos usando la función `tone()`.

```json
{
  "type": "diagram",
  "id": "diagram-13",
  "page": 72,
  "title": "Comparación de señales PWM y tone()",
  "caption": "Figura 1. Comparación entre las señales PWM (analogWrite) y las señales de tone().",
  "elements": [
    "PWM 50: analogWrite (50) - Relación cíclica baja, frecuencia constante",
    "PWM 200: analogWrite (200) - Relación cíclica alta, frecuencia constante",
    "TONE 440: tone(9, 440) - Relación cíclica del 50%, frecuencia 440Hz",
    "TONE 880: tone(9, 880) - Relación cíclica del 50%, frecuencia 880Hz (el doble)"
  ],
  "description": "Diagrama que compara las señales PWM generadas por analogWrite() con las señales de tono generadas por tone(). PWM varía la relación cíclica manteniendo la frecuencia, mientras que tone() varía la frecuencia manteniendo la relación cíclica del 50%.",
  "source": "Arduino Project Book"
}
```

En lugar de usar sensores capacitivos con Arduino, se utilizará una foto resistencia LDR para detectar la cantidad de luz. Al mover las manos sobre el sensor, se variará la cantidad de luz que llega a la superficie de la LDR, como se hizo en el proyecto número 4 (lámpara de mezcla de colores). El cambio de tensión en el pin de una entrada analógica de Arduino (A0) determinará la frecuencia de la nota que se va a escuchar.

La foto resistencia LDR se conectará a Arduino usando un divisor de tensión tal y como se hizo en el proyecto número 4. Probablemente se habrá dado cuenta de que en el proyecto 4 la lectura que se obtenía al usar `analogRead()` no cubría todo el rango de 0 a 1024. La resistencia fija conectada a masa limita la parte baja del rango y el brillo de la luz sobre la LDR limita la parte superior de este rango. En lugar de configurar el circuito para limitar el rango, se calibran las lecturas del sensor entre los valores alto y bajo, convirtiendo estos valores a frecuencias sonoras usando la función `map()` y de esta forma conseguir el mayor rango posible del Theremin.

Un zumbador piezoeléctrico es un componente electrónico que vibra cuando recibe electricidad. Cuando se mueve desplaza el aire a su alrededor, creando ondas de sonido.

### Montando el circuito

```json
{
  "type": "diagram",
  "id": "diagram-14",
  "page": 73,
  "title": "Circuito del Theremin controlado por luz",
  "caption": "Figura 3. Esquema del circuito con foto resistencia LDR y zumbador piezoeléctrico.",
  "elements": [
    "Arduino Uno",
    "Foto resistencia LDR (R1)",
    "Resistencia R2 10KΩ",
    "Zumbador piezoeléctrico (AV1) - Pin 8"
  ],
  "description": "Esquema eléctrico del circuito con una foto resistencia LDR conectada a la entrada analógica A0 a través de un divisor de tensión con resistencia de 10K, y un zumbador piezoeléctrico conectado al pin digital 8.",
  "source": "Arduino Project Book"
}
```

**Pasos:**

1. Sobre la placa de pruebas, conectar los cables de alimentación y masa desde la placa Arduino.

2. Coger el zumbador y conectar uno de sus pins a masa, el otro pin conectarlo al pin digital 8 de Arduino.

3. Colocar la foto resistencia LDR en la placa de pruebas, conectar uno de sus pins a la columna de alimentación de +5V a través de un cable rojo. Conectar el otro extremo de la LDR al pin analógico A0 de Arduino y a masa a través de una resistencia de 10 Kilo ohmios. Este circuito es el mismo que el divisor de tensión del proyecto número 4.

### El código

```cpp
int ValordelSensor;
int ValorMinimoSensor = 1023;
int ValorMaximoSensor = 0;
const int PinLed = 13;

void setup() {
  pinMode(PinLed, OUTPUT);
  digitalWrite(PinLed, HIGH);
  while(millis() < 5000) {
    ValordelSensor = analogRead(A0);
    if(ValordelSensor > ValorMaximoSensor) {
      ValorMaximoSensor = ValordelSensor;
    }
    if(ValordelSensor < ValorMinimoSensor) {
      ValorMinimoSensor = ValordelSensor;
    }
  }
  digitalWrite(PinLed, LOW);
}

void loop() {
  ValordelSensor = analogRead(A0);
  int tono = map(ValordelSensor, ValorMinimoSensor, ValorMaximoSensor, 50, 4000);
  tone(8, tono, 20);
  delay(10);
}
```

**Conceptos clave:**

- **Calibración:** Crear variables para calibrar el sensor. Se establece un valor inicial de 1023 para el valor mínimo y un valor de 0 para el valor máximo. Cuando se ejecute el programa por primera vez, se comparan estos números con los valores obtenidos en la LDR, para encontrar de esta forma los valores máximo y mínimo del rango y poder así calibrar el sensor.
- **while():** Los siguientes pasos calibrarán los valores máximo y mínimo del sensor. Se utiliza la instrucción `while()` para ejecutar otras instrucciones varias veces durante 5 segundos. `while()` ejecuta las instrucciones que contiene durante este tiempo hasta que ciertas condiciones se cumplen.
- **millis():** Junto con la instrucción `while()` se utiliza otra instrucción, `millis()`, para saber el tiempo actual. Esta instrucción informa del tiempo que Arduino lleva funcionando desde que ha sido encendido o desde que se hizo un reset.
- **tone():** La función `tone()` necesita tres argumentos: el número de pin de salida que producirá el sonido, la frecuencia que se va a generar, y durante cuánto tiempo va a sonar esta nota (probar con 20 mili segundos para comenzar).
- **noTone():** Para silenciar el zumbador cuando no se presiona un pulsador se utiliza la función `noTone()`, el cual necesita el número del terminal en donde dejar de reproducir el sonido.

**ÚSALO:** Nada más alimentar la placa Arduino se genera una ventana de 5 segundos para calibrar el sensor; esto se indica porque el diodo LED amarillo de la placa se enciende durante todo este tiempo. En este momento acercar la mano a la foto resistencia, a continuación alejar la mano para no hacer sombra a dicha foto resistencia, de esta manera el programa establece los límites del rango de trabajo en función de la iluminación ambiente. Los movimientos de la mano en el momento de realizar la calibración deberán ser lo más parecidos a los movimientos que se van a realizar después de la calibración para generar los sonidos. Después de 5 segundos, la calibración estará completada, y el diodo LED de la placa Arduino se apagará. Cuando esto suceda, ¡se debe escuchar un sonido a través del zumbador piezoeléctrico! Ahora si se mueve la mano sobre la foto resistencia deberá de variar la frecuencia de la nota que se escucha y de esta forma se podrán generar notas con diferentes frecuencias. El efecto final será parecido a la música de fondo que se suele escuchar en las películas de miedo.

---

## Proyecto 07: Teclado musical

**Descubra:** circuito mixto con resistencias, matrices

**Tiempo:** 45 MINUTOS

**Nivel:** medio-alto

**Proyectos en los que se basa:** 1, 2, 3, 4, 6

### Introducción

Al utilizar en este proyecto varias resistencias y pulsadores conectados a una entrada analógica de Arduino para generar diferentes tonos, se está construyendo algo que se conoce con el nombre de circuito mixto con resistencias.

```json
{
  "type": "diagram",
  "id": "diagram-15",
  "page": 80,
  "title": "Circuito mixto con resistencias",
  "caption": "Figura 1. Circuito mixto con resistencias como entrada analógica.",
  "elements": [
    "Arduino Uno",
    "Pulsadores SW1, SW2, SW3, SW4",
    "Resistencias R1 220Ω, R2 10KΩ, R3 1MΩ, R4 10KΩ",
    "Zumbador piezoeléctrico (AV1)"
  ],
  "description": "Esquema eléctrico del circuito mixto con resistencias. Cada pulsador tiene una resistencia en serie diferente conectada al positivo de alimentación, de modo que al presionar cada pulsador se obtiene una tensión diferente en la entrada analógica A0.",
  "source": "Arduino Project Book"
}
```

### Montando el circuito

**Pasos:**

1. Conectar el cable de alimentación y la masa a la placa de pruebas como se hizo en proyectos anteriores. Conectar un pin del zumbador a masa. Conectar el otro pin al terminal 8 (salida digital) de Arduino.

2. Conectar los pulsadores en la placa de prueba tal y como se muestra. La disposición de las resistencias y los pulsadores conectados a esta entrada analógica se conoce con el nombre de circuito mixto. Conectar el primer pulsador directamente a la alimentación positiva. Conectar el segundo, el tercero y el cuarto pulsador a la alimentación positiva a través de una resistencia de 220 ohmios, 10 kilo ohmios y 1 mega ohmio respectivamente. Conectar todas las salidas de los pulsadores entre sí, en un solo punto de unión. Conectar este punto de unión a masa a través de una resistencia de 10Kilo ohmios, y también conectarla a la entrada analógica 0 de Arduino. Cada pulsador junto con la resistencias se comportan como un divisor de tensión en el momento de que un pulsador se presiona.

### El código

```cpp
int notas[] = {262, 294, 330, 349};

void setup() {
  Serial.begin(9600);
}

void loop() {
  int ValorTeclaPulsada = analogRead(A0);
  Serial.println(ValorTeclaPulsada);

  if(ValorTeclaPulsada == 1023) {
    tone(8, notas[0]);
  }
  else if(ValorTeclaPulsada >= 990 && ValorTeclaPulsada <= 1010) {
    tone(8, notas[1]);
  }
  else if(ValorTeclaPulsada >= 505 && ValorTeclaPulsada <= 515) {
    tone(8, notas[2]);
  }
  else if(ValorTeclaPulsada >= 5 && ValorTeclaPulsada <= 10) {
    tone(8, notas[3]);
  }
  else {
    noTone(8);
  }
}
```

**Conceptos clave:**

- **Matriz:** Es una forma de almacenar diferentes valores que están relacionados unos con otros, como las frecuencias de una escala musical, usando un solo nombre. Para declarar una matriz se hace igual que con una variable, pero escribiendo a continuación del nombre corchetes cuadrados: `[]`. En la línea `int notas[] = {262,294,330,349};` se declara una matriz de cuatro valores. Para leer o cambiar los valores de las variables de una matriz, se accede individualmente a cada una de estas variables usando el nombre de la matriz y a continuación el número de posición que ocupa dentro de esta matriz. La primera variable ocupa la posición 0, la segunda la posición 1, etc. Por ejemplo, en la matriz `notas[] = {262,294,330,349}`, el valor de la variable `notas[2]` vale 330.
- **if()...else if()...else:** Se utiliza para determinar qué nota deberá de sonar. Como las resistencias tienen una tolerancia, al presionar el pulsador Arduino puede leer un valor diferente al esperado, por tanto se establecen unos márgenes (por ejemplo, de 505 a 515) para saber que este pulsador ha sido presionado.
- **Operador &&:** Se utiliza para verificar múltiples condiciones.

**ÚSALO:** Si los valores de las resistencias del circuito montado son los mismos que los mostrados en este proyecto, se deberá oír un sonido a través del zumbador cuando se presione un pulsador. Si no es así, mirar a través del monitor serie el valor que aparece al presionar un pulsador para verificar que se encuentran dentro de los rangos establecidos en las instrucciones `if()...else`. Si se oye un sonido intermitente, incrementar un poco el rango de valores de la instrucción cuyo valor se encuentra cerca del valor mostrado al presionar el pulsador que produce este sonido intermitente.

---

## Proyecto 08: Reloj de arena digital

**Descubra:** datos de tipo largo, creación de un temporizador

**Tiempo:** 30 MINUTOS

**Proyectos en los que se basa:** 1, 2, 3, 4

**Nivel:** medio

### Introducción

Hasta ahora, cuando se ha querido que suceda algo al pasar un intervalo de tiempo específico con Arduino se ha usado la instrucción `delay()`, la cual es útil pero un tanto limitada. Cuando se ejecuta `delay()` Arduino se paraliza hasta que se termine el tiempo especificado dentro de esta instrucción. Esto significa que no es posible trabajar con las señales de entrada y salida mientras está paralizado. Delay tampoco es muy útil para llevar un control del tiempo transcurrido. Resulta un tanto engorroso hacer algo cada 10 segundos utilizando para ello delay junto con este tiempo de retraso.

La función `millis()` ayuda a resolver estos problemas. Realiza un seguimiento del tiempo que Arduino ha estado funcionando en mili segundos. Se ha utilizado esta función en el proyecto número 6 (Theremin controlado por luz) para establecer un tiempo de 5 segundos que permita calibrar los niveles de iluminación del sensor.

Hasta ahora se han declarado variables del tipo int. Una variable int (entero) es un número de 16 bit, esto significa que puede guardar números decimales entre -32768 y 32767. Estos valores numéricos pueden parecer muy grandes, pero si Arduino cuenta 1000 veces por segundo usando la función `millis()`, llegará a superar el rango de valores entre -32768 y 32767 (65536 números) en 65.5 segundos. Los datos de tipo largo o long pueden guardar números de 32 bits (entre -2147483648 y 2147483647). Ya que no es posible contar el tiempo hacia atrás usando números negativos, la variable para guardar el tiempo que hay que usar en la función `millis()` se llama `unsigned long`. Cuando un tipo de datos es llamado unsigned (sin signo), solo trabaja con números positivos. Esto posibilita realizar cuentas mucho mayores. Una variable del tipo `unsigned long` puede contar más de 4294 millones de números. Son bastantes números para ser contados con `millis()` ya que le llevaría hacerlo más de 50 días. Al poder comparar el tiempo que cuenta `millis()` con un tiempo en concreto, es posible determinar la cantidad de tiempo que ha transcurrido con respecto a ese tiempo.

Cuando se gira el reloj de arena sobre sí mismo, el interruptor de inclinación cambia de estado, y comenzará un nuevo ciclo de encendido de los diodos LED.

El interruptor de inclinación trabaja igual que un interruptor normal, pero en esta aplicación se comporta como un sensor de encendido/apagado. Aquí se usará como una entrada digital, ya que proporciona dos niveles lógicos diferentes, "0" y "1". Los interruptores de inclinación son únicos a la hora de detectar la orientación o inclinación de un objeto. En su interior disponen de una pequeña cavidad con una bola de metal. Cuando el interruptor se gira la bola de metal se mueve en su interior rodando hasta uno de los extremos de la cavidad, haciendo que dos terminales se conecten entre sí de forma que se cierra el circuito que está conectado a la placa de pruebas. En ese momento el reloj de arena digital comenzará a contar un tiempo de 60 segundos encendiendo un LED, de los 6 de que dispone, cada 10 segundos.

### Montando el circuito

```json
{
  "type": "diagram",
  "id": "diagram-16",
  "page": 89,
  "title": "Circuito del Reloj de Arena Digital",
  "caption": "Figura 2. Esquema del circuito con interruptor de inclinación y 6 LEDs.",
  "elements": [
    "Arduino Uno",
    "Interruptor de inclinación (SW1)",
    "6 LEDs (D1-D6) en pins 2-7",
    "Resistencia R1 10KΩ",
    "Resistencias R2-R7 220Ω"
  ],
  "description": "Esquema eléctrico del circuito con un interruptor de inclinación conectado al pin 8 y seis LEDs conectados a los pins 2 al 7 a través de resistencias de 220 ohmios.",
  "source": "Arduino Project Book"
}
```

**Pasos:**

1. Conectar el cable de alimentación positivo y negativo (cables rojo y negro) a la placa de pruebas.

2. Conectar el ánodo de cada uno de los seis LEDs a los pins digitales de 2 a 7. Conectar el otro pin de los LED a masa y a través de una resistencia de 220 ohmios.

3. Conectar un pin del interruptor de inclinación al positivo de alimentación +5V de Arduino. Conectar el otro pin a masa usando una resistencia de 10 kilo ohmios. Conectar el punto de unión de esta resistencia con el terminal del interruptor al pin digital número 8.

### El código

```cpp
const int PinInterruptor = 8;
unsigned long TiempoPrevio = 0;
int EstadodelInterruptor = 0;
int EstadoPreviodelInterruptor = 0;
int Led = 2;
long TiempoIntervalocadaLed = 10000;

void setup() {
  for(int x = 2; x < 8; x++)
    pinMode(x, OUTPUT);
  pinMode(PinInterruptor, INPUT);
}

void loop() {
  unsigned long TiempoActual = millis();

  if(TiempoActual - TiempoPrevio > TiempoIntervalocadaLed) {
    TiempoPrevio = TiempoActual;
    digitalWrite(Led, HIGH);
    Led++;
    if(Led == 7) {
      // Todos los LEDs encendidos
    }
  }

  EstadodelInterruptor = digitalRead(PinInterruptor);

  if(EstadodelInterruptor != EstadoPreviodelInterruptor) {
    for(int x = 2; x < 8; x++) {
      digitalWrite(x, LOW);
    }
    Led = 2;
    TiempoPrevio = TiempoActual;
  }

  EstadoPreviodelInterruptor = EstadodelInterruptor;
}
```

**Conceptos clave:**

- **unsigned long:** Tipo de variable que puede guardar números muy grandes (32 bits, hasta 4294 millones). Se utiliza para almacenar el tiempo que devuelve `millis()`.
- **millis():** Realiza un seguimiento del tiempo que Arduino ha estado funcionando en mili segundos.
- **for():** Se utiliza para crear un bucle que define en solo tres líneas de código los seis pins como salidas OUTPUT.
- **Comparación de tiempo:** Utilizando una instrucción `if()`, se verifica si se ha pasado el intervalo establecido para encender un diodo LED. Restando el valor de la variable `TiempoActual` del valor de la variable `TiempoPrevio` se comprueba si este resultado es mayor que el valor de la variable `TiempoIntervalocadaLed`.

**ÚSALO:** Una vez que se ha programado la tarjeta Arduino, comprobar el tiempo de un minuto usando un reloj. Después de que hayan pasado 10 segundos se debe de encender el primer diodo LED. Cada 10 segundos debe de encenderse un LED. Al final de los 60 segundos todos los diodos LEDs deberán de estar encendidos. Si se mueve el circuito en cualquier momento y se consigue que el sensor de inclinación cambie de estado, todos los diodos LEDs se apagarán y comenzará un nuevo ciclo de encendido de los LEDs cada 10 segundos.

---

## Proyecto 09: Rueda de colores motorizada

**Descubra:** transistores, cargas de gran corriente y tensión

**Tiempo:** 45 MINUTOS

**Nivel:** medio

### Introducción

El controlar motores con Arduino es más complicado que simplemente encender y apagar diodos LEDs por un par de razones. Primero, los motores necesitan más cantidad de corriente que los pins de salida de Arduino pueden suministrar, y segundo, los motores pueden generar su propia corriente a través de un proceso llamado inducción, la cual puede dañar el circuito si no se tiene en cuenta y no se corrige. Sin embargo, los motores hacen posible mover objetos físicos, haciendo de esta forma los proyectos más interesantes. Por tanto, aunque son más complicados merece la pena usarlos.

Mover cosas consume gran cantidad de energía. Los motores normalmente necesitan una corriente muy superior a la que Arduino puede suministrar. Además algunos motores también necesitan una mayor tensión para funcionar. El motor para comenzar a funcionar, así como para mover una carga pesada unida a él, consumirá tanta corriente como pueda necesitar. Arduino solo puede suministrar una corriente máxima de 40 mili amperios (40 mA) desde sus terminales digitales, es decir, una corriente mucho menor que la mayoría de los motores necesitan para funcionar.

Los transistores son componentes que permiten controlar grandes cantidades de corriente y altas tensiones a partir de una corriente pequeña (muy inferior a 40mA) de una salida digital de Arduino. Hay muchas clases de transistores, pero todos trabajan bajo el mismo principio. Se puede pensar en los transistores como interruptores digitales, es decir, no se cierran ni se abren usando un dedo, sino mediante el control de un parámetro eléctrico (tensión o corriente). En los transistores del tipo Mosfet, como el que se utiliza en este proyecto, se aplica una tensión al pin de control del transistor, llamado puerta, de manera que el transistor se cierra entre sus dos terminales extremos llamados fuente y surtidor, tal y como lo haría un interruptor real. Este tipo de transistores se conoce con el nombre de unipolares y siempre funcionan por una tensión aplicada a su terminal de control, esto equivale a usar un dedo cuando se cierra o se abre un interruptor real. Así que de esta manera es posible suministrar una gran corriente y tensión a un motor para encenderlo o apagarlo usando Arduino.

Los motores son un tipo de dispositivo de inducción. La inducción es un proceso por el cual la circulación de una corriente eléctrica a través de un cable (bobina) genera un campo magnético alrededor de este cable. Cuando a un motor se le aplica electricidad, el cable que se enrolla en su interior formando una bobina produce un campo magnético. Este campo hace que el eje (el cilindro que sobresale del motor) comience a dar vueltas.

Al revés también funcionan: un motor puede producir electricidad cuando se hace girar su eje. Intentar unir un diodo LED entre los dos terminales del motor y a continuación girar el eje de este motor a mano. Si no sucede nada, volver a girar el eje pero en sentido contrario a como se hizo antes. El diodo LED debe de alumbrar. Acaba de realizar un pequeño generador con el motor.

Cuando se deja de suministrar energía a un motor, continuará girando, debido a la inercia que posee. Cuando el motor está girando produce una tensión de sentido contrario a la dirección de la corriente que se le aplica para que funcione. Esta tensión inversa inducida puede dañar el transistor que lo controla. Por esta razón es necesario colocar un diodo en paralelo con el motor, de manera que la tensión inducida pase a través del diodo y no afecte al transistor. El diodo solo permite el paso de la corriente en una sola dirección, protegiendo de esta forma al resto del circuito.

### Montando el circuito

```json
{
  "type": "diagram",
  "id": "diagram-17",
  "page": 97,
  "title": "Circuito de la Rueda de Colores Motorizada",
  "caption": "Figura 2. Esquema del circuito con transistor MOSFET y motor DC.",
  "elements": [
    "Arduino Uno",
    "Pulsador (SW1) - Pin 2",
    "Transistor MOSFET IRF520 (T1)",
    "Motor DC (L1)",
    "Diodo 1N4007 (D1)",
    "Resistencia R1 10KΩ",
    "Pila de 9V (V1)"
  ],
  "description": "Esquema eléctrico del circuito con un pulsador conectado al pin 2, un transistor MOSFET IRF520 controlado desde el pin 9, un motor DC alimentado por una pila de 9V, y un diodo de protección 1N4007 en paralelo con el motor.",
  "source": "Arduino Project Book"
}
```

**Pasos:**

1. Conectar los cables de alimentación positivo y negativo a la placa de pruebas desde la tarjeta Arduino.

2. Añadir un pulsador a la placa de pruebas, conectar uno de sus terminales al positivo de alimentación y el otro terminal al pin digital 2 de Arduino. Añadir una resistencia de 10 kilo ohmios conectada a masa por un extremo y por el otro conectada al punto de unión del pulsador con este pin 2 de Arduino.

3. Cuando se utilizan circuitos alimentados con diferentes tensiones, es necesario conectar las masas de ambos circuitos juntas para así tener una masa común. Conectar la pila de 9V a la placa de pruebas usando el clip para este tipo de pilas. Conectar la masa de la batería (cable negro) a la masa de Arduino en la placa de pruebas mediante un cable que hace de puente. Conectar el cable rojo de la pila a la placa de pruebas en la segunda columna, columna de la derecha, siendo esta conexión la que alimenta al motor directamente.

4. Conectar el transistor IRF520 sobre la placa de pruebas de manera que la cara con una mayor superficie metálica quede mirando hacia la derecha (al lado contrario de la placa Arduino). Conectar el pin digital 9 de Arduino al terminal superior del transistor. Este terminal recibe el nombre de puerta. Un cambio en la tensión que se aplica al terminal de puerta hace que el transistor conecte entre sí sus otros dos terminales (se comporta como un interruptor cerrado). Conectar el cable negro del motor al terminal central del transistor, el cual recibe el nombre de drenador. Cuando Arduino activa el transistor al suministrar una tensión al terminal de puerta, este terminal (drenador) se conectará a un tercer terminal llamado fuente, el cual a su vez está conectado a masa. De esta forma al conectar el drenador y el surtidor entre sí se conecta el cable negro del motor directamente a masa y a través de este transistor, comenzando en ese momento el motor a girar.

5. Lo siguiente, conectar los cables de alimentación del motor a la placa de pruebas. El último componente que hay que añadir es el diodo. El diodo es un componente que tiene polaridad, solo se puede montar de una forma determinada en el circuito. Observar que el diodo en uno de sus extremos tiene una franja blanca. Este extremo del diodo es el negativo y se conoce con el nombre de cátodo (por donde sale la corriente). El otro extremo es el positivo o ánodo (por donde entra la corriente). Conectar el ánodo del diodo al cable negro del motor (masa) y el cátodo de este diodo al cable rojo del motor (alimentación positiva). Parece que el diodo está conectado al revés, en realidad sí que es así. El diodo ayuda a eliminar cualquier tensión inversa inducida producida por el motor y que pueda retornar al transistor estropeándolo. Recordar, la tensión inversa inducida siempre aparece con una polaridad contraria a la tensión que se aplica para producirla.

### El código

```cpp
const int PindelPulsador = 2;
const int PindelMotor = 9;
int EstadodelPulsador = 0;

void setup() {
  pinMode(PindelPulsador, INPUT);
  pinMode(PindelMotor, OUTPUT);
}

void loop() {
  EstadodelPulsador = digitalRead(PindelPulsador);
  if (EstadodelPulsador == HIGH) {
    digitalWrite(PindelMotor, HIGH);
  }
  else {
    digitalWrite(PindelMotor, LOW);
  }
}
```

**Conceptos clave:**

- **Transistor MOSFET:** Componente de tres terminales (puerta, drenador, fuente) que puede trabajar como un interruptor electrónico controlado por tensión.
- **Diodo de protección:** Se coloca en paralelo con el motor para eliminar la tensión inversa inducida y proteger el transistor.

**MUY IMPORTANTE (Nota del traductor):** El motor consume del orden de 100 mA sin carga cuando está funcionando, y más de 280 mA cuando tiene montada la plantilla, así que no es nada recomendable usar una pila normal de 9V, ya que se descargará en seguida. La mejor solución es usar una batería de 9V de 1.2 amperios/hora del tipo gel-sodio. En caso de hacerlo no es necesario usar el clip para pila de 9V, dos simples cables conectados a la batería y a la placa de pruebas y en los mismos lugares en donde se colocan los cables del clip.

---

## Proyecto 10: Zoótropo

**Descubra:** puentes en H

**Tiempo:** 30 MINUTOS

**Proyectos en los que se basa:** 1, 2, 3, 4, 9

**Nivel:** alto

### Introducción

Antes de que llegase Internet, la televisión e incluso antes de las películas de cine, algunas de las primeras imágenes en movimiento fueron creadas con una herramienta llamada zoótropo. Los zoótropos crean la ilusión de movimiento a partir de un grupo de imágenes fijas las cuales tienen pequeños cambios entre ellas. Se compone de un tambor circular con unos cortes en su superficie. Cuando el tambor gira se mira a través de los cortes y los ojos perciben las imágenes fijas de su interior como si se estuviesen moviendo. Las ranuras ayudan a evitar que las imágenes se conviertan en una gran mancha borrosa cuando se mueven, además la velocidad a la cual estas imágenes aparecen crean la sensación de una única imagen que se está moviendo. Originalmente, estos tambores se giraban a mano o con un mecanismo de arranque. En este proyecto, usted montará su propio zoótropo el cual producirá la animación de una planta carnívora. Se producirá el movimiento usando un motor. Para hacer este sistema aún más avanzado, se añadirá un pulsador para controlar la dirección de giro del motor, además de otro pulsador para encender y apagar el circuito y un potenciómetro para controlar la velocidad del motor.

En el proyecto anterior de la rueda de colores motorizada se consiguió hacer girar el motor en una sola dirección. Si se aplica un cable de alimentación positiva y otro para la masa el motor girará en una dirección, si se invierten estos cables el motor girará en la dirección contraria. Esto no es muy práctico de hacer cada vez que se quiera cambiar el sentido de giro, así que se va a usar un componente llamado puente H para invertir la polaridad de la tensión aplicada al motor y así hacerlo girar en una dirección o en otra.

Los Puentes H son un tipo de componentes conocidos con el nombre de circuitos integrados. Los circuitos integrados o ICs son componentes que tienen en su interior circuitos muy grandes (formado a su vez por cientos o miles de componentes electrónicos) pero que ocupan muy poco espacio dentro de su encapsulado. Estos circuitos integrados ayudan a simplificar los circuitos más complejos al poderlos colocar como componentes individuales que se pueden reemplazar (se suelen montar sobre un soporte o zócalo que permite el cambiarlos con facilidad, como en el caso del microcontrolador de Arduino Uno Rev3). Por ejemplo, el puente H que se va a usar en este proyecto dispone en su interior de un determinado número de transistores en su interior.

```json
{
  "type": "diagram",
  "id": "diagram-18",
  "page": 104,
  "title": "Identificación de pines en un circuito integrado",
  "caption": "Figura 1. Numeración de pines en un circuito integrado DIP.",
  "elements": [
    "Pines 1-16",
    "Muesca de orientación en la parte superior"
  ],
  "description": "Diagrama que muestra cómo identificar el número de pin en un circuito integrado tipo DIP. Se cuenta desde la parte superior izquierda en forma de U.",
  "source": "Arduino Project Book"
}
```

### Montando el circuito

```json
{
  "type": "diagram",
  "id": "diagram-19",
  "page": 105,
  "title": "Circuito del Zoótropo",
  "caption": "Figura 3. Esquema del circuito con puente H L293D, motor DC, potenciómetro y pulsadores.",
  "elements": [
    "Arduino Uno",
    "Puente H L293D (IC2)",
    "Motor DC (L1)",
    "Potenciómetro (P1) 10K",
    "Pulsadores SW1 (Encendido) y SW2 (Dirección)",
    "Resistencias R1, R2 10KΩ",
    "Pila de 9V (V1)"
  ],
  "description": "Esquema eléctrico del circuito con el puente H L293D controlando un motor DC. Los pulsadores de encendido y dirección están conectados a los pins 5 y 4, el potenciómetro a A0, y el motor se conecta a las salidas del puente H.",
  "source": "Arduino Project Book"
}
```

**Pasos:**

1. Conectar los cables de alimentación positivo y negativo a la placa de pruebas desde la tarjeta Arduino.

2. Añadir dos pulsadores (normalmente abiertos) a la placa de pruebas, conectando un extremo de sus terminales al positivo de la alimentación. Añadir una resistencia de 10 Kilo ohmios en serie con cada resistencia conectando su otro extremo a masa. El punto de unión de uno de estos pulsadores con una resistencia se conecta al terminal digital número 4 de Arduino, se usará como control de dirección, mientras que el otro pulsador se conecta al terminal 5, y se usará para encender y apagar el motor.

3. Conectar el potenciómetro a la placa de pruebas. Conectar uno de sus terminales extremos a +5V y el otro a masa. Unir el terminal central al pin de entrada analógico 0 de Arduino. Este potenciómetro se usará como control de velocidad del motor.

4. Colocar el circuito integrado (puente en H) en el centro de la placa de pruebas. Conectar el terminal 1 del integrado al terminal número 9 de Arduino. Este es el terminal de activación del integrado. Cuando recibe una tensión de +5V hace que el motor funcione, en cambio cuando no recibe tensión hace que el motor se pare. Se usará este terminal para modular el ancho de pulso de este puente en H y de esta forma variar la velocidad del motor.

5. Conectar el terminal número 2 del integrado al pin digital 3 de Arduino. Conectar el pin 7 al pin digital 2. Estos terminales se usarán para comunicarse con el puente en H, indicando en qué dirección deberá de girar el motor. Si el pin 3 está LOW y el pin 2 está HIGH, el motor girará en una dirección. Si el pin 2 está LOW y el pin 3 está HIGH el motor girará en la dirección contraria. Si estos dos terminales están en estado LOW o en estado HIGH a la vez el motor parará de girar.

6. Este circuito integrado recibe su tensión de alimentación de +5V mediante el terminal 16. Los terminales 4 y 5 se conectan los dos a masa.

7. Conectar el motor a los terminales 3 y 6 del integrado. Estos dos terminales encenderán o apagarán el motor dependiendo de las señales que reciba el integrado en los terminales 2 y 7.

8. Colocar el conector para la pila de 9V (sin conectar la pila) a las columnas de positivo y de masa de la placa de pruebas. Conectar la masa de Arduino a la columna del extremo derecho de la placa de pruebas en donde se conecta el cable negro del conector de la pila (masa). Conectar el terminal 8 del integrado (puente en H) a la columna donde se conecta el cable de alimentación positiva de la pila. Este es el terminal a través del cual el integrado alimenta el motor cuando funciona. Asegurarse de que las alimentaciones de +9V y de +5V no están juntas (error de conexión), ya que deben de estar separadas. Solo las masas de ambas alimentaciones deberán de estar conectadas entre sí.

### El código

```cpp
const int PindeControl1 = 2;
const int PindeControl2 = 3;
const int PindeActivation = 9;
const int PinDirectionGiro = 4;
const int PinEncendidoApagado = 5;
const int PinPotenciometro = A0;

int EstadoPulsadorArranque = 0;
int EstadoPrevioPulsadorArranque = 0;
int EstadoPulsadorDireccion = 0;
int EstadoPrevioPulsadorDireccion = 0;
int ActivarMotor = 0;
int VelocidadMotor = 0;
int DireccionMotor = 1;

void setup() {
  pinMode(PinDireccionGiro, INPUT);
  pinMode(PinEncendidoApagado, INPUT);
  pinMode(PindeControl1, OUTPUT);
  pinMode(PindeControl2, OUTPUT);
  pinMode(PindeActivation, OUTPUT);
  digitalWrite(PindeActivation, LOW);
}

void loop() {
  EstadoPulsadorArranque = digitalRead(PinEncendidoApagado);
  delay(1);
  EstadoPulsadorDireccion = digitalRead(PinDirectionGiro);
  VelocidadMotor = analogRead(PinPotenciometro)/4;

  if(EstadoPulsadorArranque != EstadoPrevioPulsadorArranque) {
    if(EstadoPulsadorArranque == HIGH) {
      ActivarMotor = !ActivarMotor;
    }
  }

  if(EstadoPulsadorDireccion != EstadoPrevioPulsadorDireccion) {
    if(EstadoPulsadorDireccion == HIGH) {
      DireccionMotor = !DireccionMotor;
    }
  }

  if(DireccionMotor == 1) {
    digitalWrite(PindeControl1, HIGH);
    digitalWrite(PindeControl2, LOW);
  }
  else {
    digitalWrite(PindeControl1, LOW);
    digitalWrite(PindeControl2, HIGH);
  }

  if(ActivarMotor == 1) {
    analogWrite(PindeActivacion, VelocidadMotor);
  }
  else {
    analogWrite(PindeActivacion, 0);
  }

  EstadoPrevioPulsadorDireccion = EstadoPulsadorDireccion;
  EstadoPrevioPulsadorArranque = EstadoPulsadorArranque;
}
```

**Conceptos clave:**

- **Puente H:** Circuito integrado que permite invertir la polaridad de la tensión aplicada a un motor para hacerlo girar en ambas direcciones.
- **Operador !:** Operador de inversión lógica. `DireccionMotor = !DireccionMotor` cambia el estado de la variable al contrario.
- **Detección de cambio de estado:** Se comparan los estados actuales de los pulsadores con los estados previos para detectar cuándo han sido presionados.

---

## Proyecto 11: La Bola de Cristal

**Descubra:** Pantallas LCD, instrucciones switch/case, random()

**Tiempo:** 1 HORA

**Nivel:** alto

**Proyectos en los que se basa:** 1, 2, 3

### Introducción

La bola de cristal le puede ayudar a "adivinar" el futuro. Le hace una pregunta a la bola que todo lo sabe y a continuación deberá de moverla para obtener la respuesta. Las respuestas estarán guardadas con anterioridad, pero podrá redactarlas como más le guste. Se usará Arduino para escoger una respuesta de un total de 8 respuestas guardadas. El sensor de inclinación que se incluye en el kit imita el movimiento de la bola cuando se frota para obtener las respuestas.

La pantalla LCD se puede usar para mostrar caracteres alfanuméricos. El de este kit dispone de 16 columnas y de 2 filas, para un total de 32 caracteres. Su montaje sobre la placa de circuito impreso incluye un gran número de conexiones. Estos terminales se utilizan para la alimentación y comunicación, además de indicar lo que tiene que escribir sobre la pantalla, pero no es necesario conectar todos sus terminales, algunos se dejan al aire.

### Montando el circuito

```json
{
  "type": "diagram",
  "id": "diagram-20",
  "page": 117,
  "title": "Circuito de la Bola de Cristal",
  "caption": "Figura 3. Esquema del circuito con pantalla LCD y sensor de inclinación.",
  "elements": [
    "Arduino Uno",
    "Pantalla LCD 16x2 (IC2)",
    "Sensor de inclinación (SW1)",
    "Potenciómetro (P1) 10K para contraste",
    "Resistencia R1 10KΩ",
    "Resistencia R2 220Ω"
  ],
  "description": "Esquema eléctrico del circuito con una pantalla LCD conectada en modo de 4 bits (pins D4-D7 a pins 5, 4, 3, 2 de Arduino), RS al pin 12, EN al pin 11, y un sensor de inclinación conectado al pin 6.",
  "source": "Arduino Project Book"
}
```

**Pasos:**

1. Conectar los cables de alimentación y masa tal y como se muestra en la ilustración, en un extremo de la placa de pruebas.

2. Colocar el sensor de inclinación en la placa de pruebas y conectar uno de sus terminales a +5V. Conectar el otro terminal a masa y a través de una resistencia de 10K ohmios, el punto central de unión de esta resistencia y el terminal del sensor se unen al pin número 6 de la placa Arduino.

3. El terminal de selección de registro (RS) de la pantalla LCD controla cuándo los caracteres aparecerán sobre la pantalla. El terminal de lectura/escritura (R/W) coloca la pantalla en modo de lectura o de escritura. En este proyecto se usará el modo de escritura. El terminal de activación (enable) (EN) le dice a la pantalla que va a recibir una instrucción. Los terminales de datos (D0-D7) se utilizan para enviar caracteres de datos a la pantalla. Solo se usarán 4 (D4-D7) de estos 8 terminales. Finalmente, la pantalla dispone de un terminal a través del cual se puede ajustar el contraste de la misma (V0). Se usará un potenciómetro para realizar este control del contraste.

4. La librería de la pantalla LCD que se incluye con el software de Arduino maneja toda la información de estos terminales y simplifica el proceso de escribir software para mostrar los caracteres. Los dos terminales externos del LCD (Vss y LED-) hay que conectarlos a masa. También se conecta a masa el terminal R/W, el cual coloca al LCD en modo de escritura. El terminal de alimentación del LCD (Vcc) se conecta directamente a +5V. El terminal LED+ de la pantalla se conecta a través de una resistencia de 220 ohmios también a +5V.

5. Conectar: El terminal digital 2 de Arduino al terminal D7 del LCD, el terminal digital 3 al D6 del LCD, el terminal digital 4 al D5 del LCD y el terminal digital 5 al D4 del LCD. Todos son terminales de datos que le dicen a la pantalla qué carácter debe de mostrar.

6. Conectar el terminal EN (activación) de la pantalla al terminal 11 de Arduino. El terminal RS de la pantalla se conecta al terminal 12 de Arduino. Este terminal habilita la escritura del LCD.

7. Colocar el potenciómetro en la placa de pruebas, conectando uno de sus terminales extremos a la alimentación de 5V y el otro a masa. El terminal central debe de conectarse al terminal V0 de la pantalla LCD. Este potenciómetro permitirá cambiar el contraste de la pantalla.

### El código

```cpp
#include <LiquidCrystal.h>
LiquidCrystal lcd(12, 11, 5, 4, 3, 2);
const int PindelSensor = 6;
int EstadodelSensor = 0;
int EstadoPreviodelSensor = 0;
int Contestar;

void setup() {
  lcd.begin(16, 2);
  pinMode(PindelSensor, INPUT);
  lcd.print("Preguntame");
  lcd.setCursor(0, 1);
  lcd.print("Bola de Cristal");
}

void loop() {
  EstadodelSensor = digitalRead(PindelSensor);
  if(EstadodelSensor != EstadoPreviodelSensor) {
    if(EstadodelSensor == LOW) {
      Contestar = random(8);
    }
  }

  lcd.clear();
  lcd.setCursor(0,0);
  lcd.print("La bola dice:");
  lcd.setCursor(0,1);

  switch(Contestar) {
    case 0:
      lcd.print("Si");
      break;
    case 1:
      lcd.print("Es probable");
      break;
    case 2:
      lcd.print("Ciertamente");
      break;
    case 3:
      lcd.print("Buenas perspectivas");
      break;
    case 4:
      lcd.print("No es seguro");
      break;
    case 5:
      lcd.print("Pregunta de nuevo");
      break;
    case 6:
      lcd.print("Ni idea");
      break;
    case 7:
      lcd.print("No");
      break;
  }
  EstadoPreviodelSensor = EstadodelSensor;
}
```

**Conceptos clave:**

- **LiquidCrystal:** Librería que simplifica el control de pantallas LCD basadas en el chip HD44780.
- **lcd.begin():** Inicializa la pantalla LCD indicando el número de columnas y filas.
- **lcd.print():** Escribe texto en la pantalla LCD.
- **lcd.setCursor():** Mueve el cursor a una posición específica (columna, fila).
- **lcd.clear():** Limpia la pantalla y mueve el cursor a la posición 0,0.
- **random():** Genera un número aleatorio dentro del rango especificado. `random(8)` genera un número entre 0 y 7.
- **switch()...case:** Ejecuta diferentes partes del código dependiendo del valor de una variable. Cada caso se identifica con `case` y termina con `break`.

---

## Proyecto 12: Mecanismo de bloqueo secreto

**Descubra:** entrada con un zumbador, escribir sus propias funciones

**Tiempo:** 1 HORA

**Nivel:** alto

**Proyectos en los que se basa:** 1, 2, 3, 4, 5

### Introducción

El zumbador usado para reproducir sonidos en los proyectos del theremin y del teclado también se puede usar como un dispositivo de entrada o sensor. Cuando se le aplica una tensión de 5V, este sensor puede detectar las vibraciones las cuales pueden ser leídas por las entradas analógicas de Arduino. Es necesario conectar una resistencia de un valor alto (del orden de 1 Mega ohmio) entre la salida y masa para que funcione correctamente, es decir, se realiza el montaje del zumbador en serie con una resistencia de 1 Mega ohmio conectada a masa, de manera que el conjunto forma un divisor de tensión.

Cuando un zumbador piezoeléctrico es presionado contra una superficie plana puede vibrar, como por ejemplo sobre una mesa de madera, siendo Arduino capaz de detectar la intensidad de esta vibración. Usando esta información puede comprobar si el número de vibraciones detectadas se encuentran dentro del rango de trabajo establecido. En el código puede contabilizar el número de vibraciones y ver si coinciden con el número de vibraciones almacenadas.

Un pulsador permite bloquear el motor en una posición. Algunos diodos LEDs aportan información: un LED rojo indicará que la caja está bloqueada, un LED verde indicará que la caja no está bloqueada, y un LED amarillo permite saber si se ha recibido el número correcto de vibraciones.

También escribirá su propia función la cual le permitirá saber si una vibración es demasiado fuerte o demasiado débil. El escribir sus propias funciones le ayuda a ahorrar tiempo de programación al llamar siempre a una misma parte del código sin necesidad de volverlo a escribir cada vez que se use. Las funciones pueden usar argumentos y devolver valores a través de estos argumentos.

### Montando el circuito

```json
{
  "type": "diagram",
  "id": "diagram-21",
  "page": 127,
  "title": "Circuito del Mecanismo de Bloqueo Secreto",
  "caption": "Figura 2. Esquema del circuito con zumbador como sensor, servo, LEDs y pulsador.",
  "elements": [
    "Arduino Uno",
    "Zumbador piezoeléctrico (AV1) como sensor - A0",
    "Servomotor (M1) - Pin 9",
    "Pulsador (SW1) - Pin 2",
    "LED Amarillo - Pin 3",
    "LED Verde - Pin 4",
    "LED Rojo - Pin 5",
    "Resistencia R1 1MΩ",
    "Resistencia R2 10KΩ",
    "Resistencias R3, R4, R5 220Ω",
    "Condensador C1 100uF"
  ],
  "description": "Esquema eléctrico del circuito con un zumbador usado como sensor de vibraciones conectado a A0, un servomotor en el pin 9, un pulsador en el pin 2, y tres LEDs indicadores en los pins 3, 4 y 5.",
  "source": "Arduino Project Book"
}
```

**Pasos:**

1. Conectar los cables de alimentación y masa a ambos lados de la placa de pruebas. Colocar el pulsador sobre la placa de pruebas conectando uno de sus terminales a +5V. El otro extremo del pulsador conectarlo a masa a través de una resistencia de 10Kilo ohmios. Conectar la unión de la resistencia y el terminal del pulsador al pin digital número 2 de Arduino.

2. Colocar el zumbador sobre la placa de pruebas y a continuación conectar un cable desde uno de sus terminales al positivo de la alimentación. Si el zumbador tiene un cable de color rojo o el símbolo "+", este será el terminal que se conecte al positivo. Si en el zumbador no se indica la polaridad se podrá conectar de cualquier forma. Conectar el otro terminal del zumbador al terminal Analog 0 de Arduino. Colocar una resistencia de 1 Mega ohmio entre masa y este terminal conectado a Arduino. Valores de resistencia más bajos harán que el zumbador sea menos sensible a las vibraciones.

3. Cablear los LEDs, conectando los cátodos (patilla corta) a masa, y colocar una resistencia de 220 ohmios en serie con los ánodos. A través de sus respectivas resistencias, conectar el LED amarillo al pin digital 3 de Arduino, el LED verde al pin digital 4, y el LED rojo al pin digital 5.

4. Insertar el conector macho de tres terminales dentro del conector hembra del servomotor. Conectar el cable rojo a la alimentación y el cable negro a masa. Colocar un condensador electrolítico de 100 micro faradios en las líneas de alimentación de la placa de pruebas para suavizar las variaciones bruscas de corriente y evitar variaciones de tensión, además asegurarse que el condensador se ha conectado con la polaridad correcta. Conectar el terminal de datos del servomotor, el cable blanco, al terminal 9 de Arduino.

### El código

```cpp
#include <Servo.h>
Servo miServo;
const int zumbador = A0;
const int PinPulsador = 2;
const int LedAmarillo = 3;
const int LedVerde = 4;
const int LedRojo = 5;

int ValorGolpe;
int ValorPulsador;
const int GolpesSuaves = 10;
const int GolpesFuertes = 100;
boolean bloqueado = false;
int NumeroGolpes = 0;

void setup() {
  miServo.attach(9);
  pinMode(LedAmarillo, OUTPUT);
  pinMode(LedRojo, OUTPUT);
  pinMode(LedVerde, OUTPUT);
  pinMode(PinPulsador, INPUT);
  Serial.begin(9600);
  digitalWrite(LedVerde, HIGH);
  miServo.write(0);
  Serial.println("La caja esta desbloqueada!");
}

void loop() {
  if(bloqueado == false) {
    ValorPulsador = digitalRead(PinPulsador);
    if(ValorPulsador == HIGH) {
      bloqueado = true;
      digitalWrite(LedVerde, LOW);
      digitalWrite(LedRojo, HIGH);
      miServo.write(90);
      Serial.println("La caja esta bloqueada!");
      delay(1000);
    }
  }

  if(bloqueado == true) {
    ValorGolpe = analogRead(zumbador);
    if(NumeroGolpes < 3 && ValorGolpe > 0) {
      if(VerificarGolpes(ValorGolpe) == true) {
        NumeroGolpes++;
      }
      Serial.print(3 - NumeroGolpes);
      Serial.println(" golpes para abrir");
    }

    if(NumeroGolpes >= 3) {
      bloqueado = false;
      miServo.write(0);
      delay(20);
      digitalWrite(LedVerde, HIGH);
      digitalWrite(LedRojo, LOW);
      Serial.println("La caja esta desbloqueada!");
      NumeroGolpes = 0;
    }
  }
}

boolean VerificarGolpes(int valor) {
  if(valor > GolpesSuaves && valor < GolpesFuertes) {
    digitalWrite(LedAmarillo, HIGH);
    delay(50);
    digitalWrite(LedAmarillo, LOW);
    Serial.print("Golpe valido de valor ");
    Serial.println(valor);
    return true;
  }
  else {
    Serial.print("El valor del golpe no es valido ");
    Serial.println(valor);
    return false;
  }
}
```

**Conceptos clave:**

- **Funciones personalizadas:** Permiten encapsular código que se puede reutilizar. Se declaran con un tipo de retorno (void, boolean, int, etc.) y pueden recibir argumentos.
- **boolean:** Tipo de variable que solo puede tomar dos valores: true o false.
- **return:** Devuelve un valor desde una función y termina su ejecución.
- **Zumbador como sensor:** Un zumbador piezoeléctrico puede usarse como sensor de vibraciones cuando se conecta formando un divisor de tensión con una resistencia de alto valor.

---

## Proyecto 13: Lámpara sensible al tacto

**Descubra:** instalación de bibliotecas de terceros, creación de un sensor táctil

**Tiempo:** 45 MINUTOS

**Proyectos en los que se basa:** 1, 2, 5

**Nivel:** medio-alto

### Introducción

Se va a utilizar la biblioteca CapacitiveSensor de Paul Badger en este proyecto. Esta biblioteca le permitirá medir la capacidad de su cuerpo.

La capacidad es una medida que indica la cantidad de carga eléctrica que un cuerpo puede almacenar. La biblioteca comprueba dos terminales de Arduino (uno es un emisor, el otro es un receptor), y mide el tiempo que tardan en alcanzar el mismo estado. Estos terminales se conectarán a un objeto metálico como pueda ser una lámina de aluminio. A medida que se acerque al objeto metálico, su cuerpo absorberá alguna carga eléctrica, haciendo que transcurra más tiempo para que los dos terminales tengan el mismo estado.

### Preparando la librería

La versión más reciente de la biblioteca CapacitiveSensor está aquí: arduino.cc/capacitive. Descargar este fichero en el ordenador y descomprimirlo. Abrir la carpeta de las bibliotecas de Arduino (por defecto se localiza dentro de la carpeta de C:\Archivos de programa\Arduino\libraries). Dentro de esta carpeta crear una carpeta llamada CapacitiveSensor y copiar dentro de ella los archivos que se han descomprimido (localizados dentro de la carpeta arduino-libraries-CapacitiveSensor-7684dff) además de cerrar el IDE de Arduino si está abierto.

Abrir el IDE de Arduino y dentro del menú "Archivos" seleccionar "Ejemplos", al hacerlo se podrá ver en la parte inferior de la ventana que aparece una nueva entrada con el nombre "CapacitiveSensor". La biblioteca que se ha añadido contiene un proyecto de ejemplo. Abrir el ejemplo CapacitiveSensorSketch y compilarlo. Si no se produce ningún error sabrá que la biblioteca la ha instalado correctamente.

### Montando el circuito

```json
{
  "type": "diagram",
  "id": "diagram-22",
  "page": 141,
  "title": "Circuito de la Lámpara Sensible al Tacto",
  "caption": "Esquema del circuito con sensor capacitivo y LED.",
  "elements": [
    "Arduino Uno",
    "LED - Pin 12",
    "Resistencia de 220Ω",
    "Resistencia de 1MΩ entre pins 2 y 4",
    "Lámina de aluminio (sensor)"
  ],
  "description": "Esquema eléctrico del circuito con un LED conectado al pin 12 a través de una resistencia de 220 ohmios, y un sensor capacitivo formado por una resistencia de 1MΩ entre los pins 2 y 4 y una lámina de aluminio conectada al pin 2.",
  "source": "Arduino Project Book"
}
```

**Pasos:**

1. Conectar el diodo LED al pin 12 y conectar el cátodo a masa a través de una resistencia de 220 ohmios.

2. Conectar el pin digital 2 y el 4 a la placa de pruebas. Conectar estos dos pines entre sí mediante una resistencia de 1 Mega ohmio. En la misma línea de pines de la placa de pruebas en donde se conecta el terminal 2 insertar un cable largo (como mínimo entre 8 y 10 centímetros) que salga fuera de la placa de pruebas. El otro extremo conectarlo a una lámina de aluminio como pueda ser un trozo de papel de aluminio. Este será el sensor.

No es necesario suministrar una tensión de +5V a la placa de pruebas en este proyecto. El pin digital 4 suministra la energía al sensor.

### El código

```cpp
#include <CapacitiveSensor.h>
CapacitiveSensor capSensor = CapacitiveSensor(4,2);
int Umbral = 1000;
const int PinLed = 12;

void setup() {
  Serial.begin(9600);
  pinMode(PinLed, OUTPUT);
}

void loop() {
  long ValorSensor = capSensor.capacitiveSensor(30);
  Serial.print(ValorSensor);
  if(ValorSensor > Umbral) {
    digitalWrite(PinLed, HIGH);
  }
  else {
    digitalWrite(PinLed, LOW);
  }
  delay(100);
}
```

**Conceptos clave:**

- **CapacitiveSensor:** Librería de terceros que permite medir la capacidad eléctrica de un objeto.
- **capSensor.capacitiveSensor():** Devuelve el valor de capacidad medido. Toma un argumento que identifica el número de muestras que se van a leer (30 es un buen valor).
- **Umbral:** Valor a partir del cual se considera que el sensor ha sido tocado.

---

## Proyecto 14: Retocar el logotipo de Arduino

**Descubra:** comunicación serie con un programa de ordenador, Processing

**Tiempo:** 45 MINUTOS

**Proyectos en los que se basa:** 1, 2, 3

**Nivel:** alto

### Introducción

Se han realizado un montón de cosas interesantes con el mundo físico, ahora es el momento de controlar un ordenador usando Arduino. Cuando se programa Arduino, se está abriendo una conexión entre el ordenador y el microcontrolador de la placa Arduino. Se puede usar esta conexión para enviar datos de ida y vuelta a otras aplicaciones.

Arduino tiene un chip que convierte la comunicación USB del ordenador en una comunicación serie que Arduino puede usar. La comunicación serie permite que dos equipos electrónicos, una tarjeta Arduino y un PC, puedan intercambiar bits de información en serie, es decir, uno tras otro en el tiempo.

Para poder establecer una comunicación serie entre dos dispositivos es necesario que la velocidad de transmisión de uno a otro, y al revés, sea la misma. Probablemente habrá observado cuando ha usado el monitor serie que en la parte inferior derecha de la ventana aparece un número. Ese número, 9600 bits por segundo, o baudios, es el mismo valor que se ha declarado usando la instrucción `Serial.begin()`. Esa es la velocidad a la cual Arduino y el ordenador intercambian datos. Un bit es la unidad mínima de información que un ordenador puede entender.

Se ha usado el monitor serie para examinar los valores de las entradas digitales; se usará un método similar para obtener valores con un programa que es un entorno de programación diferente al IDE de Arduino y que se conoce con el nombre de Processing. Processing está basado en Java, el entorno de programación de Arduino está basado en Processing. Ambos son muy similares, así que no debería tener ningún problema para usarlo.

Antes de comenzar con el proyecto, descargar la última versión de Processing de la página processing.org.

### Montando el circuito

```json
{
  "type": "diagram",
  "id": "diagram-23",
  "page": 148,
  "title": "Circuito del Retoque del Logotipo de Arduino",
  "caption": "Figura 3. Esquema del circuito con potenciómetro.",
  "elements": [
    "Arduino Uno",
    "Potenciómetro (P1) 10K - A0"
  ],
  "description": "Esquema eléctrico del circuito con un potenciómetro conectado a la entrada analógica A0. Se utiliza para enviar valores a Processing a través de la comunicación serie.",
  "source": "Arduino Project Book"
}
```

**Pasos:**

1. Conectar los cables de alimentación y de masa a la placa de pruebas.

2. Conectar un terminal extremo del potenciómetro a masa y el otro al positivo de la alimentación. El terminal central conectarlo al pin analógico 0 de la placa Arduino.

### El código de Arduino

```cpp
void setup() {
  Serial.begin(9600);
}

void loop() {
  Serial.write(analogRead(A0)/4);
  delay(1);
}
```

### El código de Processing

```processing
import processing.serial.*;
Serial miPuerto;
PImage logotipo;
int colordefondo = 0;

void setup() {
  colorMode(HSB, 255);
  logotipo = loadImage("http://arduino.cc/logo.png");
  size(logotipo.width, logotipo.height);
  println("Puertos serie disponibles:");
  println(Serial.list());
  miPuerto = new Serial(this, Serial.list()[0], 9600);
}

void draw() {
  if (miPuerto.available() > 0) {
    colordefondo = miPuerto.read();
    println(colordefondo);
  }
  background(colordefondo, 255, 255);
  image(logotipo, 0, 0);
}
```

**Conceptos clave:**

- **Serial.write():** Envía valores entre 0 y 255 como un grupo de bytes. Es más eficiente que `Serial.print()` para enviar datos a Processing.
- **Processing:** Entorno de programación de código abierto basado en Java. El IDE de Arduino está basado en Processing.
- **Serial.list():** Función de Processing que devuelve una lista de los puertos serie disponibles.
- **colorMode(HSB, 255):** Cambia el modo de color a Matiz, Saturación y Brillo.
- **background():** Establece el color de fondo de la ventana.
- **image():** Dibuja una imagen en la ventana.

---

## Proyecto 15: Hackear botones

**Descubra:** optoacoplador, conexión con otros componentes

**Tiempo:** 45 MINUTOS

**Proyectos en los que se basa:** 1, 2, 9

**Nivel:** alto

**Advertencia:** Ya no será más un principiante si está realizando este proyecto. Abrirá un dispositivo electrónico (mando a distancia, teclado, etc.) y lo modificará. Perderá la garantía al abrirlo, y si no tiene cuidado podría estropearlo. Debe de asegurarse de que todos los conceptos básicos de la electricidad y de la electrónica que se han visto en los proyectos anteriores le resultan familiares antes de realizar este proyecto. Le recomendamos que utilice componentes y dispositivos electrónicos baratos en los proyectos que realice, y que no le importe estropear, hasta que adquiera la experiencia y confianza necesaria en el montaje de proyectos electrónicos.

### Introducción

En tanto que Arduino puede controlar un montón de cosas, algunas veces es más fácil usar herramientas que han sido creadas para propósitos específicos. Quizás quiera controlar una televisión o un reproductor de música, o conducir un coche de control remoto. Muchos de los dispositivos electrónicos disponen de un mando de control con botones, y muchos de esos botones se pueden hackear de manera que pueda "presionarlos" usando Arduino. El control de una grabadora de sonido es un buen ejemplo. Si quiere grabar y después reproducir el sonido grabado, le podría costar un gran esfuerzo conseguir que Arduino haga esto. Es mucho más fácil obtener un pequeño dispositivo que grabe y reproduzca sonidos, y reemplazar sus botones por las salidas controladas por Arduino.

Los optoacopladores son circuitos integrados que permiten controlar un circuito desde otro circuito diferente y sin ninguna conexión eléctrica directa entre los dos. Interiormente un optoacoplador de este tipo dispone de un diodo LED (circuito de control) y un foto transistor que actúa como un detector de luz (circuito a controlar). Cuando el diodo LED interno del optoacoplador se enciende mediante Arduino, el detector de luz cierra un interruptor interno (transistor). El interruptor interno está conectado a dos terminales de salida del optoacoplador (terminales 4 y 5). Cuando este interruptor está cerrado, los dos terminales de salida se conectan entre sí. Cuando el interruptor está abierto, los terminales 4 y 5 están desconectados. De esta manera, es posible cerrar interruptores de otros dispositivos sin una conexión eléctrica directa con Arduino, usando siempre un optoacoplador.

### Montando el circuito

```json
{
  "type": "diagram",
  "id": "diagram-24",
  "page": 159,
  "title": "Circuito del Hackeo de Botones",
  "caption": "Figura 2. Esquema del circuito con optoacoplador 4N35.",
  "elements": [
    "Arduino Uno",
    "Optoacoplador 4N35 (IC2)",
    "Resistencia R1 220Ω",
    "Circuito externo (módulo de sonido) - Contactos del botón"
  ],
  "description": "Esquema eléctrico del circuito con un optoacoplador 4N35 conectado al pin 2 de Arduino a través de una resistencia de 220 ohmios. Los terminales 4 y 5 del optoacoplador se conectan a los contactos del botón del dispositivo externo.",
  "source": "Arduino Project Book"
}
```

**Pasos:**

1. Conectar la masa a la placa de pruebas a través de Arduino.

2. Colocar el optoacoplador sobre la placa de pruebas de manera que quede colocado en el centro de la placa.

3. Colocar el pin 1 del optoacoplador al terminal 2 de Arduino en serie con una resistencia de 220 ohmios (recordad, se alimenta un diodo LED en el interior así que hay que conectarle una resistencia para que no se queme). Conectar el pin 2 del optoacoplador a masa.

4. Sobre la placa del módulo de sonido hay un determinado número de componentes electrónicos, incluyendo el botón de reproducción. Para controlar el interruptor del módulo de sonido, es necesario quitar el botón. Darle la vuelta al circuito y encontrar las lengüetas que sujetan al botón en su lugar. Doblar con cuidado las lengüetas y quitar el botón de la placa.

5. Debajo del botón hay dos pequeñas láminas metálicas. Este diseño es típico de muchos dispositivos electrónicos que tienen botones que se presionan. Las dos "horquillas" de este diseño son los dos lados del interruptor. Un pequeño disco de metal en el interior del botón de presión conecta estas dos horquillas metálicas cuando se presiona el botón.

6. Cuando las horquillas metálicas se conectan entre sí, el interruptor está cerrando el circuito de la placa. Se cerrará este interruptor usando el optoacoplador. Este método, cerrar un interruptor usando un optoacoplador, trabaja solo si uno de los dos lados del interruptor del pulsador de presión está conectado a masa del módulo de sonido. Si no está seguro de que su módulo esté conectado de esta forma, usar un polímetro y medir la tensión entre una de las pestañas y masa de su dispositivo. Es necesario hacer esto con el circuito alimentado, así hay que tener cuidado de no hacer un cortocircuito con las puntas del polímetro al tocar en algún lugar de la placa. Una vez que sepa qué horquilla está conectada a masa, podrá quitarle alimentación al circuito.

7. Lo siguiente que debe de hacer es conectar un cable a cada una de las pequeñas láminas metálicas u horquillas. Si va a soldar unos cables, tenga cuidado de no unir accidentalmente estas dos pestañas con un punto de estaño, de manera que el interruptor quede permanentemente cerrado. Si no va a soldar y va a usar pegamento, asegurarse que las conexiones están bien realizadas, ya que si no el interruptor no se cerrará. Al final puede probar con un polímetro en la escala de resistencia que el valor en ohmios entre los cables unidos a las horquillas es prácticamente infinito. En caso de que se obtenga un valor inferior a 1 ohmio significa que existe un cortocircuito entre las láminas metálicas.

8. Conectar los dos cables unidos a las láminas metálicas de su módulo de sonido a los terminales 4 y 5 del optoacoplador. Conectar el cable del interruptor que está conectado a masa al terminal 4 del optoacoplador. Conectar el otro cable al terminal 5 del optoacoplador.

### El código

```cpp
const int PinOpto = 2;

void setup() {
  pinMode(PinOpto, OUTPUT);
}

void loop() {
  digitalWrite(PinOpto, HIGH);
  delay(15);
  digitalWrite(PinOpto, LOW);
  delay(21000);
}
```

**Conceptos clave:**

- **Optoacoplador:** Circuito integrado que permite controlar un circuito desde otro sin conexión eléctrica directa. Contiene un LED interno y un fototransistor.
- **Aislamiento eléctrico:** Los dos circuitos están eléctricamente separados, lo que protege a Arduino de posibles daños.

---

## Glosario A/Z

```json
{
  "type": "table",
  "id": "table-02",
  "page": 163,
  "title": "Glosario de términos",
  "headers": ["Término", "Definición"],
  "rows": [
    ["Acelerómetro", "Sensor que mide la aceleración. Algunas veces también se usan para detectar la orientación o la inclinación."],
    ["Actuador", "Un tipo de componente electrónico que convierte la energía eléctrica en movimiento. Los motores son un tipo de actuador."],
    ["Aislante", "Un tipo de material que evita que la corriente eléctrica pueda circular. Los materiales conductores como los cables se cubren con materiales aislantes como el plástico."],
    ["Amperaje (amperios)", "La cantidad de carga eléctrica que circula por un circuito de un punto a otro del mismo. Indica la cantidad de intensidad (corriente por unidad de tiempo) que fluye a través de un conductor, como pueda ser un cable."],
    ["Analógico", "Algo que puede variar continuamente en el tiempo entre sus valores máximo y mínimo tomando cualquier valor entre estos extremos. Por ejemplo, una tensión que varía de 0 a 5V se puede tomar cualquier valor intermedio (1,2V, 3.123V, etc)."],
    ["Ánodo", "El terminal positivo de un diodo (recordar que un LED es un tipo de diodo)."],
    ["Argumento", "Un tipo de dato que se le suministra a una función como una entrada. Por ejemplo, al usar digitalRead() hay que indicar qué pin se va a chequear, en este caso se le suministra el argumento con el formato de un número digitalRead(7), o una variable numérica, digitalRead(PinPulsador)."],
    ["Baudio", "Término que se refiere a 'bits por segundo', indicando la velocidad a la cual un ordenador se comunica con otro."],
    ["Binario", "Un sistema que solo dispone de dos estados, como verdadero/falso o sin tensión/con tensión o '0'/'1'."],
    ["Bit", "La pieza más pequeña de información que un ordenador puede enviar o recibir. Tiene dos estados, 0 y 1. Cero quiere decir que no tiene tensión y 1 que tiene tensión."],
    ["Booleano (boolean)", "Variables que indican si algo es verdadero o falso."],
    ["Buffer serie", "Un lugar de la memoria de un ordenador o de un microcontrolador donde la información recibida en una comunicación serie es guardada hasta que es leída por un programa."],
    ["Byte", "Son 8 bits de información. Un byte puede almacenar cualquier número entre 0 y 255. También se conoce con el nombre de palabra digital."],
    ["Calibración", "El proceso por el cual se realizan ajustes en algunos números o en algunos componentes (potenciómetros, resistencias ajustables, etc) para conseguir que un programa o un circuito electrónico funcione mejor. En los proyectos de Arduino esto se hace a menudo cuando se usan sensores para medir parámetros físicos en diferentes circunstancias, por ejemplo, al usar una foto resistencia que mide el nivel de luminosidad de una habitación."],
    ["Capacidad", "La habilidad de algo para almacenar energía eléctrica (carga eléctrica). Esta carga se puede medir con la librería del Sensor Capacitivo, como en el proyecto número 13. Los componentes electrónicos que usan principalmente esta propiedad son los condensadores."],
    ["Carga", "Cualquier dispositivo o componente electrónico que transforme la energía eléctrica en calor, luz, movimiento, sonido, etc. Por ejemplo, una resistencia transforma la energía eléctrica en calor."],
    ["Cátodo", "El terminal de un diodo que normalmente se conecta a masa."],
    ["Circuito", "El conjunto de componentes electrónicos a través de los cuales la intensidad de la corriente eléctrica circula, saliendo del positivo de la alimentación y volviendo al negativo de esta alimentación y a través de los componentes que forman el circuito. Para que la intensidad circule el circuito deberá de estar cerrado, si existe un interruptor en serie con la alimentación y está abierto el circuito no estará cerrado y la intensidad no circulará."],
    ["Circuito integrado (IC)", "Se trata de un componente electrónico que ha sido creado sobre una pequeña oblea de silicio e integrada dentro de un encapsulado plástico. Los pins, patillas o terminales que sobresalen del encapsulado permiten la interacción con el circuito interno. Muchas veces es muy sencillo usar un IC simplemente sabiendo la función de cada uno de sus terminales sin necesidad de saber cómo funciona el integrado a nivel interno."],
    ["Comunicación serie", "El sistema por el cual Arduino se comunica con ordenadores y otros dispositivos. Se trata de enviar un bit de información a la vez en un orden secuencial. La placa Arduino dispone de un convertidor USB a serie el cual permite que se pueda comunicar con otros dispositivos que no tengan un puerto serie dedicado."],
    ["Condensadores de desacoplo", "Los condensadores que se colocan cerca de los actuadores (relés, transistores, etc) y que son usados para atenuar las variaciones y caídas de tensión que se producen en el momento que los actuadores funcionan. Se colocan cerca de los sensores y actuadores."],
    ["Conductor", "Algo que permite que la intensidad de la corriente eléctrica pueda circular, como un cable."],
    ["Constante (const)", "Un modificador que convierte a una variable en una constante y que no puede cambiar su valor en un programa, por ejemplo, const float pi = 3.1415, la variable (constante con decimales) es pi."],
    ["Convertidor Analógico a Digital (ADC)", "Un circuito que convierte una tensión de una entrada analógica (cualquier valor entre su valor mínimo y máximo) en un número digital que representa esa tensión. Este circuito está integrado dentro del microcontrolador de Arduino, y está conectado a los pins de entrada analógica A0-A5. Convertir una tensión analógica en un número digital le lleva un poco de tiempo, por eso después de usar la instrucción analogRead() se usa un pequeño retraso para que le dé tiempo a hacerlo. Con la instrucción delay() se introduce el retraso."],
    ["Copia (instance)", "Una copia de un objeto de software. Se han usado copias de la librería Servo en los proyectos 5 y 12, en cada caso, se ha creado un nombre para la copia de la librería Servo para usar en el proyecto."],
    ["Corriente", "El movimiento de las cargas eléctricas (electrones) a través de un circuito cerrado. Se mide en columbios. La intensidad (corriente por unidad de tiempo) se mide en amperios."],
    ["Corriente alterna", "Un tipo de corriente en el cual las cargas eléctricas están cambiando el sentido de circulación periódicamente, primero en un sentido y un tiempo después en el contrario, volviendo de nuevo al sentido inicial. Este es el tipo de electricidad que se encuentra en los enchufes de una vivienda."],
    ["Corriente continua", "Un tipo de corriente en el cual las cargas eléctricas siempre circulan en el mismo sentido. Cuando se conecta una bombilla de 9V en paralelo con una pila de 9V se produce este tipo de corriente. En todos los proyectos de Arduino se ha consumido una corriente continua."],
    ["Cortocircuito", "Cuando se produce un problema en un circuito eléctrico o electrónico de manera que la intensidad que necesita para funcionar es muy superior a la que fuente de alimentación puede proporcionar y por tanto el circuito deja de funcionar o se quema."],
    ["Depuración", "El proceso de buscar errores en un circuito o en un código (también referidos como 'bugs'), hasta que se consigue que funcione según se espera."],
    ["Digital", "Un sistema de valores discretos. Como Arduino es un tipo de dispositivo digital, solo trabaja con dos estados discretos, apagado o encendido. Digital significa siempre solo dos estados, binario, cero o uno."],
    ["Divisor de voltaje o tensión", "Un tipo de circuito, normalmente formado por dos componentes, que suministra una tensión que es una fracción de la tensión de alimentación a la cual está conectado."],
    ["Drenador", "Terminal de un transistor el cual se conecta a una carga (bombilla, altavoz, etc) para ser controlada por este transistor."],
    ["Electricidad", "Un tipo de energía producida por las cargas eléctricas. Se pueden usar componentes electrónicos para transformar la electricidad en otras formas de energía como luz y calor."],
    ["Encapsulado en doble línea (DIP)", "Un tipo de encapsulado usado con los circuitos integrados que permite que estos componentes se puedan insertar con facilidad en una placa de pruebas o en un zócalo montado sobre una PCB."],
    ["Flotante (float)", "Un tipo de variable que se puede expresar como una fracción. Esto implica el uso de decimales para los números con coma flotante."],
    ["Foto célula", "Componente que convierte la energía luminosa en energía eléctrica."],
    ["Foto resistencia", "Resistencia cuyo valor óhmico varía según la cantidad de luz que recibe, a mayor luz menor resistencia y viceversa. También se conocen con el nombre de Resistencias Dependientes de la Luz o L.D.R."],
    ["Foto transistor", "Transistor que además de poderse controlar mediante una corriente de base también se puede controlar por luz, ya que dispone de una superficie de cristal que deja pasar la luz a su interior."],
    ["Fuente (transistor)", "El terminal de un transistor del tipo Mosfet que se conecta a masa. Cuando el terminal de control o puerta de este transistor recibe una tensión, la fuente y el drenador se conectan, como si fuese un interruptor, y de esta forma se cierra el circuito que está siendo controlado."],
    ["Fuente de alimentación", "Una fuente de energía, generalmente una batería, un transformador, o también un puerto USB de un ordenador. Puede ser de varios tipos, estabilizada o no estabilizada, de tensión alterna o de tensión continua."],
    ["Función", "Un bloque de código que ejecuta una tarea concreta cuando es llamada por el programa principal."],
    ["Hoja de datos", "Un documento escrito por ingenieros para otros ingenieros o técnicos en electricidad o electrónica que describe el diseño, los parámetros principales, las curvas características y los circuitos típicos de los componentes electrónicos."],
    ["IDE", "Significa 'Integrated Development Environment' o 'Entorno de Desarrollo Integrado'. El IDE de Arduino es el lugar donde se escribe el programa que se va a cargar a la tarjeta Arduino."],
    ["Index", "El número suministrado en una matriz que indica a qué elemento se está refiriendo. Los ordenadores están indexados desde cero, lo cual significa que comienzan a contar desde 0 en lugar de 1."],
    ["Inducción", "El proceso de usar energía eléctrica para crear un campo magnético. Se usa en los motores para hacerlos girar."],
    ["Int", "Un tipo de variable que puede guardar un número entre -32.768 y 32.767."],
    ["Interruptor", "Un componente que puede abrir o cerrar un circuito eléctrico. Existen varios tipos de interruptores; los que se incluyen en el kit no son exactamente interruptores sino pulsadores, ya que solo cierran el circuito en el momento de presionarlos."],
    ["LED de cátodo común", "Un tipo de LED que dispone de varios led en su interior para generar varios colores, con un solo cátodo y un ánodo por cada led interno (normalmente tres)."],
    ["Ley de Ohm", "Una ecuación matemática que demuestra la relación entre resistencia, intensidad y tensión. Siendo esta ecuación V(tensión) = I (intensidad) × R (resistencia)."],
    ["Librería", "Una pieza de código que aumenta la funcionalidad de un programa. En el caso de las librerías de Arduino, se utilizan para activar la comunicación con un componente electrónico en particular (por ejemplo un display) o se usan para manipular datos."],
    ["Long", "Un tipo de variable que puede guardar números muy grandes, de -2.147.483.648 a 2.147.483.647."],
    ["Masa", "El punto de un circuito donde normalmente hay cero voltios y que se conecta a las carcasas metálicas de los equipos cuando es posible. Normalmente se suele considerar la masa como el negativo de la fuente de alimentación o de una pila."],
    ["Matriz", "Son un grupo de variables que se identifican con un único nombre dentro de un programa, y se accede a estas variables dentro de la matriz mediante un índice numérico o index."],
    ["Microcontrolador", "El cerebro de Arduino, se trata de un circuito integrado que se puede programar para recibir, enviar, procesar y visualizar información."],
    ["Mili segundo", "La milésima parte de un segundo 1/1000 segundos. Arduino ejecuta sus programas muy rápido al ejecutar muchas instrucciones cada mili segundo. Cuando se utiliza delay() u otras funciones que se basan en tiempo se indican en mili segundos."],
    ["Modificador", "Son palabras reservadas por el programa para modificar el comportamiento de las variables. Por ejemplo, const int PinSalida = 13; indica que se trata de una variable constante que no se puede modificar."],
    ["Modulación por Ancho de Pulso (PWM)", "Se trata de una forma de simular una salida analógica cuando se utiliza una salida digital. PWM hace que un terminal cambie su valor entre el estado bajo y el estado alto a un ritmo muy rápido."],
    ["Monitor serie", "Un circuito que está incorporado dentro de la tarjeta de Arduino y que permite enviar y recibir información usando el IDE a dicha tarjeta."],
    ["Objeto", "Una copia de una librería. Cuando usando la librería Servo, se ha creado una copia llamada MiServo, MiServo sería el objeto."],
    ["Ohm", "Unidad de medida de las resistencias. Representada por la letra omega (Ω)."],
    ["Onda cuadrada", "Un tipo de forma de onda que se identifica por tener solo dos estados, alto y bajo. Cuando se usa para generar tonos, los sonidos generados con esta onda pueden resultar poco naturales."],
    ["Optoacoplador", "También se conoce como un opto-aislador, foto-acoplador, foto-interruptor y opto-interruptor. Un diodo LED de infrarrojos es combinado con un foto transistor sensible a la luz infrarroja dentro de un encapsulado sellado. Se utiliza para proporcionar un alto grado de aislamiento entre el circuito de control del LED y el circuito de salida del foto transistor."],
    ["Paralelo", "Los componentes de un circuito que están conectados a través de los mismos dos puntos se dicen que están en paralelo. Los componentes conectados en paralelo tienen siempre la misma tensión entre ambos."],
    ["Parámetro", "Al declarar una función se nombra un parámetro que sirve de puente entre las variables locales de la función, y los argumentos que recibe cuando se llama a esta función."],
    ["Periodo", "Tiempo durante el cual se repite la misma forma de onda. Si se varía el periodo de una onda también se varía la frecuencia de la misma, ya que la frecuencia es igual a 1/Periodo."],
    ["Polarizado", "Los terminales de los componentes polarizados (por ejemplo diodos LED, condensadores electrolíticos, transistores, etc) tienen diferentes funciones y hay que conectarlos de una forma determinada."],
    ["Processing", "Un entorno de programación que se basa en el lenguaje java. Usado como una herramienta para introducir a todo aquel que quiera trabajar con Arduino en conceptos de programación, y en entornos de producción."],
    ["Pseudo código", "Un puente entre la escritura en un lenguaje de programación y el uso de términos que el ser humano puede entender al leerlos."],
    ["Puerta (transistor)", "El terminal a través del cual se controla a un transistor del tipo Mosfet y que se conecta a una salida de Arduino. Cuando a la puerta del transistor se le aplica una tensión de +5V (estado alto), se comporta como un interruptor cerrado entre los terminales drenador y surtidor."],
    ["Relación cíclica", "Una relación que indica la cantidad de tiempo que una parte de una onda se encuentra en estado alto con respecto al periodo. Cuando se utiliza un valor de PWM de 127 (de un total de 256), se produce una relación cíclica en la onda que se genera del 50%."],
    ["Resistencia", "La propiedad que presentan muchos materiales al paso de una corriente eléctrica a través de ellos y que sirve para indicar si es un conductor de la electricidad. La resistencia de un material se puede calcular a partir de varios parámetros físicos del mismo, pero también se puede usar la ley de Ohm para calcular la resistencia en un circuito: R = V/I."],
    ["Sensor", "Componente que mide un tipo de energía (como luz o calor o energía mecánica) y la convierte en energía eléctrica, la cual Arduino puede procesar."],
    ["Sin signo", "Término que se utiliza para describir los datos que pueden guardar algunos tipos de variables, indicando que no puede guardar un número negativo. Es útil tener un número sin signo cuando es necesario contar en una sola dirección. Por ejemplo, cuando se hace un seguimiento del tiempo con la instrucción millis(), es aconsejable usar una variable que guarde un dato de tipo long (grande) sin signo."],
    ["Sketch", "Término que se le da a los programas que han sido escritos dentro del IDE de Arduino."],
    ["Tensión inversa", "Tensión que aparece cuando una corriente atraviesa una bobina, la cual se opone a esta corriente que lo ha creado. Puede ser creada por los motores cuando giran y puede dañar el circuito de control del motor si no se protege mediante un diodo en paralelo con el motor y colocado en sentido inverso."],
    ["USB", "Puerto de un ordenador que utiliza el estándar del Bus Universal en Serie (en inglés USB). Se trata de un puerto genérico que es un estándar en la mayoría de los ordenadores de hoy en día (2015). Con un cable USB conectado a un puerto USB de un ordenador el posible alimentar y programar una placa Arduino."],
    ["Variable", "Un lugar de la memoria de un ordenador o de un microcontrolador en donde se almacena información para ser usada por un programa. Las variables almacenan valores los cuales pueden cambiar a medida que un programa se ejecuta. Las variables son de varios tipos según la clase de información que almacena y el tamaño máximo de esa información."],
    ["Variable global", "Aquella a la cual se puede acceder desde cualquier parte de un programa. Se declara siempre antes de la función setup()."],
    ["Variable local", "Un tipo de variable que se usa durante un periodo corto de tiempo, para después olvidarla. Una variable declarada dentro de la función setup() de un programa será local, después de ejecutar la función setup() Arduino deja de considerarla, es decir, no la tiene en cuenta."],
    ["Voltaje", "Una medida de energía potencial, la cual produciría el movimiento de las cargas eléctricas si estuviese dentro de un circuito cerrado. Por ejemplo, una pila de 9V tiene un voltaje de 9 voltios, esto quiere decir que si se conecta una bombilla del mismo voltaje en paralelo con esta pila se producirá un movimiento de las cargas eléctricas (corriente eléctrica) a través de la bombilla y esta se encenderá cuando las cargas la atraviesen. Al moverse las cargas en este circuito se produce un trabajo debido a la tensión o potencial de la pila. También se conoce con el nombre de tensión."]
  ],
  "notes": "Glosario extraído del libro original.",
  "source": "Arduino Project Book"
}
```

---

## Apuntes y libros recomendados

- **Prácticas con Arduino 2 EDUBÁSICA** por Pablo E. García, Manuel Hidalgo, Jorge L. Loza, Jorge Muñoz. Libro gratuito disponible en: http://www.practicasconarduino.com/

- **Arduino Práctico** por Joan Ribas Lequerica. Editorial Anaya. ISBN: 978-84-415-3419-3. Precio: 27.5 euros con IVA. Enlace: http://www.anayamultimedia.es/libro.php?id=3273803

- **12 Proyectos Arduino + Android** por Simon Monk. Editorial Estríbor. ISBN: 978-84-940030-4-2. Precio: 25 euros. Enlace: http://www.superrobotica.com/S370530.htm

- **ARDUINO. Curso práctico de formación** de Oscar Torrente Artero. Editorial RC libros. Precio: 28 euros. Enlace: http://www.amazon.es/ARDUINO-pr%C3%A1ctico-formaci%C3%B3n-Torrente-Artero/dp/8494072501

---

## Notas del procesamiento

- El documento original presenta algunas páginas con caracteres ilegibles o corruptos (páginas 9, 23, 29, 45, 49, 59, 67, 83, 97, 107, 111, 129, 149, 159, 165, 166, 167, 168, 169, 170). Se ha conservado el texto legible y se ha reconstruido el contenido a partir del contexto cuando ha sido posible.
- Las tablas 1 (símbolos de componentes) y 2 (glosario) han sido convertidas a JSON conservando su estructura y contenido.
- Las figuras y diagramas más relevantes han sido representados mediante JSON de tipo `diagram` o `image` con descripciones detalladas de sus elementos.
- No se ha inventado información. Los datos no determinables se han marcado como `null` o se han omitido.
- El código de los proyectos se ha transcrito tal como aparece en el documento original, con comentarios explicativos.
- La bibliografía y los libros recomendados se conservan tal como aparecen en el documento original.
- Los proyectos se han organizado en el orden original del libro (01 al 15).
- Los casos de estudio y ejemplos prácticos se han transcrito íntegramente cuando ha sido posible.

---

**Fin del documento convertido.**
