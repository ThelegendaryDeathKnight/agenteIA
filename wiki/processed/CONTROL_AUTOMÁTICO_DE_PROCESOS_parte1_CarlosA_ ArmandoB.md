# CONTROL AUTOMÁTICO DE PROCESOS
## Teoría y Práctica

**Autores:** Carlos A. Smith (University of South Florida) y Armando B. Corripio (Louisiana State University)

**Versión española:** Sergio D. Manzanares Basurto (Ingeniero en Comunicaciones y Electrónica, ESIME - Instituto Politécnico Nacional de México)

**Revisión:** Carlos A. Smith, Armando B. Corripio

**Editorial:** Noriega Editores / Editorial Limusa

**Edición:** Primera edición, 1991

**ISBN:** 968-18-3791-6

**Título original:** Principles and Practice of Automatic Process Control (John Wiley & Sons, Inc., ISBN 0-471-88346-8)

---

## Resumen Técnico

Esta obra constituye un tratado completo sobre el control automático de procesos industriales, combinando los principios fundamentales de la teoría de control con la práctica industrial. El libro está dirigido a estudiantes de ingeniería química, mecánica, metalurgia, petróleo e ingeniería ambiental, así como a personal técnico de procesos industriales.

El texto se organiza en nueve capítulos que abarcan desde los conceptos básicos hasta técnicas avanzadas de control. Los capítulos 1 y 2 introducen los términos y conceptos matemáticos fundamentales, incluyendo la transformada de Laplace, linealización y variables de desviación. Los capítulos 3 y 4 desarrollan los principios de la respuesta dinámica de procesos, con ejemplos detallados de modelos de proceso simples y sistemas de orden superior (interactivos y no interactivos). El capítulo 5 estudia los componentes básicos del sistema de control: sensores, transmisores, válvulas de control y controladores por retroalimentación.

Los capítulos 6 y 7 se centran en el diseño y análisis de sistemas de control por retroalimentación, incluyendo estabilidad (prueba de Routh, substitución directa), ajuste de controladores (Ziegler-Nichols, error de integración mínimo, síntesis de Dahlin) y técnicas clásicas (lugar de raíz, respuesta en frecuencia). El capítulo 8 presenta técnicas avanzadas: control de razón, control en cascada, control por acción precalculada, control por sobreposición, control selectivo y control multivariable. El capítulo 9 aborda el desarrollo de modelos y simulación por computadora de procesos complejos, incluyendo columnas de destilación, hornos y reactores.

Los apéndices complementan el texto con símbolos y nomenclatura para instrumentos (Apéndice A), casos para estudio (Apéndice B), sensores, transmisores y válvulas de control (Apéndice C), y un programa de computadora para encontrar raíces de polinomios (Apéndice D).

La metodología pedagógica incluye numerosos ejemplos de casos reales, problemas industriales y un proyecto final donde el estudiante diseña desde el principio el sistema de control para un proceso. Los autores enfatizan que, para controlar un proceso, el ingeniero debe entenderlo primero, apoyándose en los principios del balance de materia y energía, flujo de líquidos, transferencia de calor, procesos de separación y cinética de reacción. Se prefiere el uso exclusivo del método de función de transferencia en lugar del método de variable de estado, por considerarlo más didáctico y más cercano a la práctica industrial.

---

## Prólogo

El propósito principal de este libro es mostrar la práctica del control automático de proceso, junto con los principios fundamentales de la teoría del control. Con este fin se incluye en la exposición una buena cantidad de análisis de casos, problemas y ejemplos tomados directamente de la experiencia de los autores como practicantes y como consultores en el área. En opinión de los autores, a pesar de que existen muchos libros buenos en los que se tratan los principios y la teoría del control automático de proceso, en la mayoría de ellos no se proporciona al lector la práctica de dichos principios.

Los apuntes a partir de los cuales se elaboró este libro se han utilizado durante varios años en los cursos finales de ingeniería química y mecánica en la University of South Florida y en la Louisiana State University. Asimismo los autores han utilizado muchas partes del libro para impartir cursos cortos a ingenieros en ejercicio activo en los Estados Unidos y en otros países.

El interés se centra en el proceso industrial y lo pueden utilizar los estudiantes del nivel superior de ingeniería, principalmente en las ramas de química, mecánica, metalurgia, petróleo e ingeniería ambiental; asimismo, lo puede utilizar el personal técnico de procesos industriales. Los autores están convencidos de que, para controlar un proceso, el ingeniero debe entenderlo primero; a ello se debe que todo el libro se apoye en los principios del balance de materia y energía, el flujo de líquidos, la transferencia de calor, los procesos de separación y la cinética de la reacción para explicar la respuesta dinámica del proceso. La mayoría de los estudiantes de los grados superiores de ingeniería tienen las bases necesarias para entender los conceptos al nivel que se presentan. El nivel de las matemáticas que se requieren se cubre en los primeros semestres de ingeniería, principalmente el cálculo operacional y las ecuaciones diferenciales.

En los capítulos 1 y 2 se definen los términos y los conceptos matemáticos que se utilizan en el estudio de los sistemas de control de proceso. En los capítulos 3 y 4 se explican los principios de la respuesta dinámica del proceso. En estos capítulos se utilizan numerosos ejemplos para demostrar el desarrollo de modelos de proceso simples y para ilustrar el significado físico de los parámetros con que se describe el comportamiento dinámico del proceso.

En el capítulo 5 se estudian algunos componentes importantes del sistema de control; a saber: sensores, transmisores, válvulas de control y controladores por retroalimentación. Los principios de operación práctica de algunos sensores, transmisores y válvulas de control comunes se presentan en el apéndice C, cuyo estudio se recomienda a los estudiantes que se interesen en conocer el funcionamiento de los instrumentos de proceso.

En los capítulos 6 y 7 se estudian el diseño y análisis de los sistemas de control por retroalimentación. El resto de las técnicas importantes del control industrial se tratan en el capítulo 8; éstas son: control de razón, control en cascada, control por acción precalculada, control por sobreposición, control selectivo y control multivariable. Se usan numerosos ejemplos para ilustrar la aplicación industrial de dichas técnicas.

Los principios de los modelos matemáticos y la simulación por computadora de los procesos y sus sistemas de control se presentan en el capítulo 9. En este capítulo se presenta una estructura modular de programa muy útil, la cual se puede utilizar para ilustrar los principios de respuesta dinámica, estabilidad y ajuste de los sistemas de control.

De acuerdo con la experiencia de los autores, en un curso de un semestre se deben incluir los primeros seis capítulos del libro, hasta la sección 6-3, así como la sección acerca de control por acción precalculada del capítulo 8; posteriormente, según la disponibilidad de tiempo y las preferencias del instructor, se pueden incluir las secciones sobre relés de cómputo, control de razón, control en cascada, lugar de raíz y respuesta en frecuencia, las cuales son independientes entre sí. Si en el curso se incluye un laboratorio, el material del capítulo 5 y del apéndice C es un excelente apoyo para los experimentos de laboratorio. Los ejemplos del capítulo 9 se pueden usar como guía para "experimentos" de simulación por computadora que complementarán a los experimentos reales de laboratorio. Si se dispone de dos semestres o cuatro trimestres para el curso es posible cubrir todo el texto en detalle. En el curso se debe incluir un proyecto final en el cual se pueden utilizar los problemas de control de proceso del apéndice B, que son problemas industriales reales y proporcionan al estudiante la oportunidad de diseñar desde el principio, el sistema de control para un proceso. Los autores estamos convencidos de que dichos problemas son una contribución importante de este libro.

En la presente obra se prefirió el uso exclusivo del método de función de transferencia en lugar del de variable de estado, por tres razones: primera, consideramos que es más factible hacer comprender los conceptos del control de proceso mediante las funciones de transferencia; segunda, no tenemos conocimiento de algún plan de control cuyo diseño se basa en el método de variable de estado y que actualmente se utilice en la industria; finalmente, el método de variable de estado requiere una base matemática más sólida que las funciones de transferencia.

En una obra de este tipo son muchas las personas que contribuyen, apoyan y ayudan a los autores de diferentes maneras; nuestro caso no fue la excepción y nos sentimos bendecidos por haber tenido a estas personas a nuestro alrededor. En el campo industrial ambos autores deseamos agradecer a Charles E. Jones de la Dow Chemical USA, Louisiana Division, por fomentar nuestro interés en la práctica industrial del control de proceso y por alentarnos a buscar una preparación académica superior. En el campo académico, encontramos en nuestras universidades la atmósfera necesaria para completar este proyecto; deseamos agradecer al profesorado y al alumnado de nuestros departamentos por despertar en nosotros un profundo interés en la instrucción académica, así como por las satisfacciones que hemos recibido de ella. Ser el instrumento para la preparación y desarrollo de las mentes jóvenes en verdad es una labor muy gratificante.

El apoyo de nuestros alumnos de posgrado y de licenciatura (las mentes jóvenes) ha sido invaluable, especialmente de Tom M. Brookins, Vanessa Austin, Sterling L. Jordan, Dave Foster, Hank Brittain, Ralph Stagner, Karen Klingman, Jake Martin, Dick Balhoff, Terrell Touchstone, John Usher, Shao-yu Lin y A. (Jefe) Rovira. En la University of South Florida, Carlos A. Smith desea agradecer al doctor L. A. Scott su amistad y su consejo, que han sido de gran ayuda durante estos últimos diez años. También agradece al doctor J. C. Busot su pregunta constante: "¿Cuándo van a terminar ese libro?", la cual realmente fue de ayuda, ya que proporcionó el ímpetu necesario para continuar. En la Louisiana State University, Armando B. Corripio desea agradecer a los doctores Paul W. Murrill y Cecil L. Smith su intervención cuando él se inició en el control automático de proceso; no sólo le enseñaron la teoría, sino también inculcaron en él su amor por la materia y la enseñanza de la misma.

Para terminar, los autores deseamos agradecer al grupo de secretarias de ambas universidades por el esmero, la eficiencia y la paciencia que tuvieron al mecanografiar el manuscrito. Nuestro agradecimiento para Phyllis Johnson y Lynn Federspeil de la USF, así como para Janet Easley, Janice Howell y Jimmie Keebler de la LSU.

**Carlos A. Smith** — Tampa, Florida

**Armando B. Corripio** — Baton Rouge, Louisiana

---

## Contenido

### Capítulo 1: Introducción
- 1-1 El sistema de control de procesos
- 1-2 Términos importantes y objetivo del control automático de proceso
- 1-3 Control regulador y servocontrol
- 1-4 Señales de transmisión
- 1-5 Estrategias de control
  - Control por retroalimentación
  - Control por acción precalculada
- 1-6 Razones principales para el control de proceso
- 1-7 Bases necesarias para el control de proceso
- 1-8 Resumen

### Capítulo 2: Matemáticas necesarias para el análisis de los sistemas de control
- 2-1 Transformada de Laplace
  - Definición
  - Propiedades de la transformada de Laplace
- 2-2 Solución de ecuaciones diferenciales mediante el uso de la transformada de Laplace
  - Procedimiento de solución por la transformada de Laplace
  - Inversión de la transformada de Laplace mediante expansión de fracciones parciales
  - Eigenvalores y estabilidad
  - Raíces de los polinomios
  - Resumen del método de la transformada de Laplace para resolver ecuaciones diferenciales
- 2-3 Linealización y variables de desviación
  - Variables de desviación
  - Linealización de funciones con una variable
  - Linealización de funciones con dos o más variables
- 2-4 Repaso del álgebra de números complejos
  - Números complejos
  - Operaciones con números complejos
- 2-5 Resumen
- Bibliografía
- Problemas

### Capítulo 3: Sistemas dinámicos de primer orden
- 3-1 Proceso térmico
- 3-2 Proceso de un gas
- 3-3 Funciones de transferencia y diagramas de bloques
  - Funciones de transferencia
  - Diagramas de bloques
- 3-4 Tiempo muerto
- 3-5 Nivel en un proceso
- 3-6 Reactor químico
- 3-7 Respuesta del proceso de primer orden a diferentes tipos de funciones de forzamiento
  - Función escalón
  - Función rampa
  - Función senoidal
- 3-8 Resumen
- Problemas

### Capítulo 4: Sistemas dinámicos de orden superior
- 4-1 Tanques en serie-sistema no interactivo
- 4-2 Tanques en serie-sistema interactivo
- 4-3 Proceso térmico
- 4-4 Respuesta de los sistemas de orden superior a diferentes tipos de funciones de forzamiento
  - Función escalón
  - Función senoidal
- 4-5 Resumen
- Bibliografía
- Problemas

### Capítulo 5: Componentes básicos de los sistemas de control
- 5-1 Sensores y transmisores
- 5-2 Válvulas de control
  - Funcionamiento de la válvula de control
  - Dimensionamiento de la válvula de control
  - Selección de la caída de presión de diseño
  - Características de flujo de la válvula de control
  - Ganancia de la válvula de control
  - Resumen de la válvula de control
- 5-3 Controladores por retroalimentación
  - Funcionamiento de los controladores
  - Tipos de controladores por retroalimentación
  - Reajuste excesivo
  - Resumen del controlador por retroalimentación
- 5-4 Resumen
- Bibliografía
- Problemas

### Capítulo 6: Diseño de sistemas de control por retroalimentación con un solo circuito
- 6-1 Circuito de control por retroalimentación
  - Función de transferencia de circuito cerrado
  - Ecuación característica del circuito
  - Respuesta de circuito cerrado en estado estacionario
- 6-2 Estabilidad del circuito de control
  - Criterio de estabilidad
  - Prueba de Routh
  - Efecto de los parámetros del circuito sobre la ganancia última
  - Método de substitución directa
  - Efecto del tiempo muerto
- 6-3 Ajuste de los controladores por retroalimentación
  - Respuesta de razón de asentamiento de un cuarto mediante el método de ganancia última
  - Caracterización del proceso
  - Prueba del proceso de escalón
  - Respuesta de razón de asentamiento de un cuarto
  - Ajuste mediante los criterios de error de integración mínimo
  - Ajuste de controladores por muestreo de datos
- 6-4 Síntesis de los controladores por retroalimentación
  - Desarrollo de la fórmula de síntesis del controlador
  - Especificación de la respuesta de circuito cerrado
  - Modos del controlador y parámetros de ajuste
  - Modo derivativo para procesos con tiempo muerto
- 6-5 Prevención del reajuste excesivo
- 6-6 Resumen
- Bibliografía
- Problemas

### Capítulo 7: Diseño clásico de un sistema de control por retroalimentación
- 7-1 Técnica de lugar de raíz
  - Ejemplos
  - Reglas para graficar los diagramas de lugar de raíz
  - Resumen del lugar de raíz
- 7-2 Técnicas de respuesta en frecuencia
  - Diagramas de Bode
  - Diagramas polares
  - Diagramas de Nichols
  - Resumen de la respuesta en frecuencia
- 7-3 Prueba de pulso
  - Realización de la prueba de pulso
  - Deducción de la ecuación de trabajo
  - Evaluación numérica de la integral de la transformada de Fourier
- 7-4 Resumen
- Bibliografía
- Problemas

### Capítulo 8: Técnicas adicionales de control
- 8-1 Relés de cómputo
- 8-2 Control de razón
- 8-3 Control en cascada
- 8-4 Control por acción precalculada
  - Ejemplo de un proceso
  - Unidad de adelanto/retardo
  - Diseño del control lineal por acción precalculada mediante diagrama de bloques
  - Dos ejemplos adicionales
  - Respuesta inversa
  - Resumen del control por acción precalculada
- 8-5 Control por sobreposición y control selectivo
- 8-6 Control de proceso multivariable
  - Gráficas de flujo de señal (GFS)
  - Selección de pares de variables controladas y manipuladas
  - Interacción y estabilidad
  - Desacoplamiento
- 8-7 Resumen
- Bibliografía
- Problemas

### Capítulo 9: Modelos y simulación de los sistemas de control de proceso
- 9-1 Desarrollo de modelos de proceso complejos
- 9-2 Modelo dinámico de una columna de destilación
  - Ecuaciones de bandeja
  - Bandeja de alimentación y superior
  - Rehervidor
  - Modelo de condensador
  - Tambor acumulador del condensador
  - Condiciones iniciales
  - Variables de entrada
  - Resumen
- 9-3 Modelo dinámico de un horno
- 9-4 Solución de ecuaciones diferenciales parciales
- 9-5 Simulación por computadora de los modelos de procesos dinámicos
  - Ejemplo: Simulación de un tanque de reacción con agitación continua
  - Integración numérica mediante el método de Euler
  - Duración de las corridas de simulación
  - Elección del intervalo de integración
  - Despliegue de los resultados de la simulación
  - Muestra de resultados para el método de Euler
  - Método de Euler modificado
  - Método Runge-Kutta-Simpson
  - Resumen
- 9-6 Lenguajes y subrutinas especiales para simulación
- 9-7 Ejemplos de simulación de control
- 9-8 Rigidez
  - Fuentes de rigidez en un modelo
  - Integración numérica de los sistemas rígidos
- 9-9 Resumen
- Bibliografía
- Problemas

### Apéndices
- Apéndice A: Símbolos y nomenclatura para los instrumentos
- Apéndice B: Casos para estudio
  - Caso I: Sistema de control para una planta de granulación de nitrato de amonio
  - Caso II: Sistema de control para la deshidratación de gas natural
  - Caso III: Sistema de control para la fabricación de blanqueador de hipoclorito de sodio
  - Caso IV: Sistema de control en el proceso de refinación del azúcar
  - Caso V: Eliminación de CO₂ de gas de síntesis
  - Caso VI: Proceso del ácido sulfúrico
- Apéndice C: Sensores, transmisores y válvulas de control
- Apéndice D: Programa de computadora para encontrar raíces de polinomios

### Índice

---

# Capítulo 1: Introducción

El propósito principal de este capítulo es demostrar al lector la necesidad del control automático de procesos y despertar su interés para que lo estudie. El objetivo del control automático de procesos es mantener en determinado valor de operación las variables del proceso tales como: temperaturas, presiones, flujos y compuestos. Como se verá en las páginas siguientes, los procesos son de naturaleza dinámica, en ellos siempre ocurren cambios y si no se emprenden las acciones pertinentes, las variables importantes del proceso, es decir, aquellas que se relacionan con la seguridad, la calidad del producto y los índices de producción, no cumplirán con las condiciones de diseño.

En este capítulo se presentan asimismo, dos sistemas de control, se examinan algunos de sus componentes, se definen algunos de los términos que se usan en el campo del control de procesos y finalmente, se exponen las bases necesarias para su estudio.

## 1-1. EL SISTEMA DE CONTROL DE PROCESOS

Para aclarar más las ideas expuestas aquí, considérese un intercambiador de calor en el cual la corriente en proceso se calienta mediante vapor de condensación, como se ilustra en la figura 1-1.

El propósito de la unidad es calentar el fluido que se procesa, de una temperatura dada de entrada Tᵢ(t), a cierta temperatura de salida, T(t), que se desea. Como se dijo, el medio de calentamiento es vapor de condensación y la energía que gana el fluido en proceso es igual al calor que libera el vapor, siempre y cuando no haya pérdidas de calor en el entorno, esto es, el intercambiador de calor y la tubería tienen un aislamiento perfecto; en este caso, el calor que se libera es el calor latente en la condensación del vapor.

En este proceso existen muchas variables que pueden cambiar, lo cual ocasiona que la temperatura de salida se desvíe del valor deseado, si esto llega a suceder, se deben emprender algunas acciones para corregir la desviación; esto es, el objetivo es controlar la temperatura de salida del proceso para mantenerla en el valor que se desea.

```json
{
  "type": "image",
  "id": "image-01",
  "page": 18,
  "title": "Figura 1-1. Intercambiador de calor",
  "caption": "Intercambiador de calor con corriente en proceso y vapor de condensación",
  "description": "Diagrama esquemático de un intercambiador de calor de tubos y coraza. La corriente que se procesa entra por el lado izquierdo con temperatura Tᵢ(t) y flujo q(t). El vapor entra por la parte superior derecha a través de una válvula de control. La corriente procesada sale por el lado derecho con temperatura T(t). En la parte inferior hay una trampa de vapor que descarga el condensado.",
  "elements": [
    "Intercambiador de calor (tubos y coraza)",
    "Válvula de control de vapor",
    "Sensor de temperatura T",
    "Trampa de vapor",
    "Corriente de proceso: Tᵢ(t), q(t)",
    "Corriente de salida: T(t)",
    "Vapor de calentamiento"
  ],
  "source": "Smith & Corripio, Control Automático de Procesos, Fig. 1-1"
}
```

Una manera de lograr este objetivo es primero, medir la temperatura T(t), después comparar ésta con el valor que se desea y, con base en la comparación, decidir qué se debe hacer para corregir cualquier desviación. Se puede usar el flujo del vapor para corregir la desviación, es decir, si la temperatura está por arriba del valor deseado, entonces se puede cerrar la válvula de vapor para cortar el flujo del mismo (energía) hacia el intercambiador de calor. Si la temperatura está por abajo del valor que se desea, entonces se puede abrir un poco más la válvula de vapor para aumentar el flujo de vapor (energía) hacia el intercambiador. Todo esto lo puede hacer manualmente el operador y puesto que el proceso es bastante sencillo no debe representar ningún problema. Sin embargo, en la mayoría de las plantas de proceso existen cientos de variables que se deben mantener en algún valor determinado y con este procedimiento de corrección se requeriría una cantidad tremenda de operarios, por ello, sería preferible realizar el control de manera automática, es decir, contar con instrumentos que controlen las variables sin necesidad de que intervenga el operador. Esto es lo que significa el control automático de proceso.

Para lograr este objetivo se debe diseñar e implementar un sistema de control. En la figura 1-2 se muestra un sistema de control y sus componentes básicos. (En el apéndice A se presentan los símbolos e identificación de los diferentes instrumentos utilizados en el sistema de control automático.) El primer paso es medir la temperatura de salida de la corriente del proceso, esto se hace mediante un sensor (termopar, dispositivo de resistencia térmica, termómetros de sistema lleno, termistores, etc.). El sensor se conecta físicamente al transmisor, el cual capta la salida del sensor y la convierte en una señal lo suficientemente intensa como para transmitirla al controlador. El controlador recibe la señal, que está en relación con la temperatura, la compara con el valor que se desea y, según el resultado de la comparación, decide qué hacer para mantener la temperatura en el valor deseado. Con base en la decisión, el controlador envía otra señal al elemento final de control, el cual, a su vez, maneja el flujo de vapor.

```json
{
  "type": "image",
  "id": "image-02",
  "page": 19,
  "title": "Figura 1-2. Sistema de control del intercambiador de calor",
  "caption": "Sistema de control por retroalimentación para el intercambiador de calor",
  "description": "Diagrama de instrumentación y tubería (DI&T) del sistema de control del intercambiador de calor. Se muestran: el intercambiador, la válvula de control de vapor con posicionador, el sensor de temperatura (TT), el transmisor (TT), el controlador (TC) y las señales de interconexión. La corriente de proceso entra con Tᵢ(t) y q(t), y sale con T(t).",
  "elements": [
    "Intercambiador de calor",
    "Sensor de temperatura (TT)",
    "Transmisor (TT)",
    "Controlador (TC)",
    "Elemento final de control (válvula de vapor)",
    "Señal de transmisión",
    "Corriente de proceso"
  ],
  "source": "Smith & Corripio, Control Automático de Procesos, Fig. 1-2"
}
```

En el párrafo anterior se presentan los cuatro componentes básicos de todo sistema de control, éstos son:

1. **Sensor**, que también se conoce como elemento primario.
2. **Transmisor**, el cual se conoce como elemento secundario.
3. **Controlador**, que es el "cerebro" del sistema de control.
4. **Elemento final de control**, frecuentemente se trata de una válvula de control aunque no siempre. Otros elementos finales de control comúnmente utilizados son las bombas de velocidad variable, los transportadores y los motores eléctricos.

La importancia de estos componentes estriba en que realizan las tres operaciones básicas que deben estar presentes en todo sistema de control; estas operaciones son:

1. **Medición (M):** la medición de la variable que se controla se hace generalmente mediante la combinación de sensor y transmisor.
2. **Decisión (D):** con base en la medición, el controlador decide qué hacer para mantener la variable en el valor que se desea.
3. **Acción (A):** como resultado de la decisión del controlador se debe efectuar una acción en el sistema, generalmente ésta es realizada por el elemento final de control.

Como se dijo, estas tres operaciones, M, D y A son obligatorias para todo sistema de control. En algunos sistemas, la toma de decisión es sencilla, mientras que en otros es más compleja; en este libro se estudian muchos de tales sistemas. El ingeniero que diseña el sistema de control debe asegurarse que las acciones que se emprendan tengan su efecto en la variable controlada, es decir, que la acción emprendida repercuta en el valor que se mide; de lo contrario el sistema no controla y puede ocasionar más perjuicio que beneficio.

## 1-2. TÉRMINOS IMPORTANTES Y OBJETIVO DEL CONTROL AUTOMÁTICO DE PROCESO

Ahora es necesario definir algunos de los términos que se usan en el campo del control automático de proceso. El primer término es **variable controlada**, ésta es la variable que se debe mantener o controlar dentro de algún valor deseado. En el ejemplo precedente la variable controlada es la temperatura de salida del proceso T(t). El segundo término es **punto de control**, el valor que se desea tenga la variable controlada. La **variable manipulada** es la variable que se utiliza para mantener a la variable controlada en el punto de control (punto de fijación o de régimen); en el ejemplo la variable manipulada es el flujo de vapor. Finalmente, cualquier variable que ocasiona que la variable de control se desvíe del punto de control se define como **perturbación o trastorno**; en la mayoría de los procesos existe una cantidad de perturbaciones diferentes, por ejemplo, en el intercambiador de calor que se muestra en la figura 1-2, las posibles perturbaciones son la temperatura de entrada en el proceso, Tᵢ(t), el flujo del proceso, q(t), la calidad de la energía del vapor, las condiciones ambientales, la composición del fluido que se procesa, la contaminación, etc. Aquí lo importante es comprender que en la industria de procesos, estas perturbaciones son la causa más común de que se requiera el control automático de proceso; si no hubiera alteraciones, prevalecerían las condiciones de operación del diseño y no se necesitaría supervisar continuamente el proceso.

Los siguientes términos también son importantes. **Circuito abierto o lazo abierto**, se refiere a la situación en la cual se desconecta el controlador del sistema, es decir, el controlador no realiza ninguna función relativa a cómo mantener la variable controlada en el punto de control; otro ejemplo en el que existe control de circuito abierto es cuando la acción (A) efectuada por el controlador no afecta a la medición (M). De hecho, ésta es una deficiencia fundamental del diseño del sistema de control. **Control de circuito cerrado** se refiere a la situación en la cual se conecta el controlador al proceso; el controlador compara el punto de control (la referencia) con la variable controlada y determina la acción correctiva.

Con la definición de estos términos, el objetivo del control automático de proceso se puede establecer como sigue:

> El objetivo del sistema de control automático de proceso es utilizar la variable manipulada para mantener a la variable controlada en el punto de control a pesar de las perturbaciones.

## 1-3. CONTROL REGULADOR Y SERVOCONTROL

En algunos procesos la variable controlada se desvía del punto de control a causa de las perturbaciones. El término **control regulador** se utiliza para referirse a los sistemas diseñados para compensar las perturbaciones. A veces la perturbación más importante es el punto de control mismo, esto es, el punto de control puede cambiar en función del tiempo (lo cual es típico de los procesos por lote), y en consecuencia, la variable controlada debe ajustarse al punto de control; el término **servocontrol** se refiere a los sistemas de control que han sido diseñados con tal propósito.

En la industria de procesos, el control regulador es bastante más común que el servocontrol, sin embargo, el método básico para el diseño de cualquiera de los dos es esencialmente el mismo y por tanto, los principios que se exponen en este libro se aplican a ambos casos.

## 1-4. SEÑALES DE TRANSMISIÓN

Enseguida se hace una breve mención de las señales que se usan para la comunicación entre los instrumentos de un sistema de control. Actualmente se usan tres tipos principales de señales en la industria de procesos. La primera es la **señal neumática** o presión de aire, que normalmente abarca entre 3 y 15 psig, con menor frecuencia se usan señales de 6 a 30 psig o de 3 a 27 psig; su representación usual en los diagramas de instrumentos y tubería (DI&T) (P&ID, por su nombre en inglés) es una línea con doble rayado. La **señal eléctrica o electrónica**, normalmente toma valores entre 4 y 20 mA; el uso de 10 a 50 mA, de 1 a 5 V o de 0 a 10 V es menos frecuente; la representación usual de esta señal en los DI&T es una línea con rayado sencillo. El tercer tipo de señal, el cual se está convirtiendo en el más común, es la **señal digital o discreta** (unos y ceros); el uso de los sistemas de control de proceso con computadoras grandes, minicomputadoras o microprocesadores está forzando el uso cada vez mayor de este tipo de señal.

Frecuentemente es necesario cambiar un tipo de señal por otro, esto se hace mediante un **transductor**, por ejemplo, cuando se necesita cambiar de una señal eléctrica, mA, a una neumática, psig, se utiliza un transductor (I/P) que transforma la señal de corriente (I) en neumática (P), como se ilustra gráficamente en la figura 1-3; la señal de entrada puede ser de 4 a 20 mA y la de salida de 3 a 15 psig. Existen muchos otros tipos de transductores: neumático a corriente (P/I), voltaje a neumático (E/P), neumático a voltaje (P/E), etcétera.

```json
{
  "type": "image",
  "id": "image-03",
  "page": 21,
  "title": "Figura 1-3. Transductor I/P",
  "caption": "Transductor corriente a presión (I/P)",
  "description": "Símbolo de instrumentación para un transductor I/P. Se muestra un círculo con las letras FY (función de cómputo) y el número 10, con la indicación I/P en la parte superior. La señal de entrada es eléctrica (4-20 mA) y la salida es neumática (3-15 psig).",
  "elements": [
    "Transductor I/P",
    "Señal de entrada: 4-20 mA",
    "Señal de salida: 3-15 psig",
    "Identificación: FY-10"
  ],
  "source": "Smith & Corripio, Control Automático de Procesos, Fig. 1-3"
}
```

## 1-5. ESTRATEGIAS DE CONTROL

### Control por retroalimentación

El esquema de control que se muestra en la figura 1-2 se conoce como **control por retroalimentación**, también se le llama circuito de control por retroalimentación. Esta técnica la aplicó por primera vez James Watt hace casi 200 años, para controlar un proceso industrial; consistía en mantener constante la velocidad de una máquina de vapor con carga variable; se trataba de una aplicación del control regulador. En ese procedimiento se toma la variable controlada y se retroalimenta al controlador para que éste pueda tomar una decisión. Es necesario comprender el principio de operación del control por retroalimentación para conocer sus ventajas y desventajas; para ayudar a dicha comprensión se presenta el circuito de control del intercambiador de calor en la figura 1-2.

Si la temperatura de entrada al proceso aumenta y en consecuencia crea una perturbación, su efecto se debe propagar a todo el intercambiador de calor antes de que cambie la temperatura de salida. Una vez que cambia la temperatura de salida, también cambia la señal del transmisor al controlador, en ese momento el controlador detecta que debe compensar la perturbación mediante un cambio en el flujo de vapor, el controlador señala entonces a la válvula cerrar su apertura y de este modo decrece el flujo de vapor. En la figura 1-4 se ilustra gráficamente el efecto de la perturbación y la acción del controlador.

Es interesante hacer notar que la temperatura de salida primero aumenta a causa del incremento en la temperatura de entrada, pero luego desciende incluso por debajo del punto de control y oscila alrededor de éste hasta que finalmente se estabiliza. Esta respuesta oscilatoria demuestra que la operación del sistema de control por retroalimentación es esencialmente una operación de ensayo y error, es decir, cuando el controlador detecta que la temperatura de salida aumentó por arriba del punto de control, indica a la válvula que cierre, pero ésta cumple con la orden más allá de lo necesario, en consecuencia la temperatura de salida desciende por abajo del punto de control; al notar esto, el controlador señala a la válvula que abra nuevamente un tanto para elevar la temperatura. El ensayo y error continúa hasta que la temperatura alcanza el punto de control donde permanece posteriormente.

```json
{
  "type": "image",
  "id": "image-04",
  "page": 22,
  "title": "Figura 1-4. Respuesta del sistema de control del intercambiador de calor",
  "caption": "Respuesta del sistema de control del intercambiador de calor a una perturbación en la temperatura de entrada",
  "description": "Gráfica de tres variables contra tiempo: (1) Tᵢ(t) temperatura de entrada, que muestra un cambio escalón; (2) T(t) temperatura de salida, que muestra una respuesta oscilatoria que finalmente se estabiliza en el punto de control; (3) Fracción de apertura de la válvula, que muestra una respuesta oscilatoria que finalmente se estabiliza.",
  "elements": [
    "Gráfica de Tᵢ(t) vs t",
    "Gráfica de T(t) vs t",
    "Gráfica de fracción de apertura de la válvula vs t"
  ],
  "source": "Smith & Corripio, Control Automático de Procesos, Fig. 1-4"
}
```

La **ventaja** del control por retroalimentación consiste en que es una técnica muy simple, como se muestra en la figura 1-2, que compensa todas las perturbaciones. Cualquier perturbación puede afectar a la variable controlada, cuando ésta se desvía del punto de control, el controlador cambia su salida para que la variable regrese al punto de control. El circuito de control no detecta qué tipo de perturbación entra al proceso, únicamente trata de mantener la variable controlada en el punto de control y de esta manera compensar cualquier perturbación. La **desventaja** del control por retroalimentación estriba en que únicamente puede compensar la perturbación hasta que la variable controlada se ha desviado del punto de control, esto es, la perturbación se debe propagar por todo el proceso antes de que la pueda compensar el control por retroalimentación.

El trabajo del ingeniero es diseñar un sistema de control que pueda mantener la variable controlada en el punto de control. Cuando ya ha logrado esto, debe ajustar el controlador de manera que se reduzca al mínimo la operación de ensayo y error que se requiere para mantener el control. Para hacer un buen trabajo, el ingeniero debe conocer las características o "personalidad" del proceso que se va a controlar, una vez que se conoce la "personalidad del proceso" el ingeniero puede diseñar el sistema de control y obtener la "personalidad del controlador" que mejor combine con la del proceso. El significado de "personalidad" se explica en los próximos capítulos, sin embargo, para aclarar lo expuesto aquí se puede imaginar que el lector trata de convencer a alguien de que se comporte de cierta manera, es decir, controlar el comportamiento de alguien; el lector es el controlador y ese alguien es el proceso. Lo más prudente es que el lector conozca la personalidad de ese alguien para poder adaptarse a su personalidad, si pretende efectuar un buen trabajo de persuasión o de control. Esto es lo que significa el "ajuste del controlador", es decir, el controlador se adapta o ajusta al proceso. En la mayoría de los controladores se utilizan hasta tres parámetros para su ajuste, como se verá en los capítulos 5 y 6.

### Control por acción precalculada

El control por retroalimentación es la estrategia de control más común en las industrias de proceso, ha logrado tal aceptación por su simplicidad; sin embargo, en algunos procesos el control por retroalimentación no proporciona la función de control que se requiere, para esos procesos se deben diseñar otros tipos de control. En el capítulo 8 se presentan estrategias de control que han demostrado ser útiles; una de tales estrategias es el **control por acción precalculada**. El objetivo del control por acción precalculada es medir las perturbaciones y compensarlas antes de que la variable controlada se desvíe del punto de control; si se aplica de manera correcta, la variable controlada no se desvía del punto de control.

Un ejemplo concreto de control por acción precalculada es el intercambiador de calor que aparece en la figura 1-1. Supóngase que las perturbaciones "más serias" son la temperatura de entrada, Tᵢ(t), y el flujo del proceso, q(t); para establecer el control por acción precalculada primero se deben medir estas dos perturbaciones y luego se toma una decisión sobre la manera de manejar el flujo de vapor para compensar los problemas. En la figura 1-5 se ilustra esta estrategia de control; el controlador por acción precalculada decide cómo manejar el flujo de vapor para mantener la variable controlada en el punto de control, en función de la temperatura de entrada y el flujo del proceso.

```json
{
  "type": "diagram",
  "id": "diagram-01",
  "page": 24,
  "title": "Figura 1-5. Intercambiador de calor con sistema de control por acción precalculada",
  "caption": "Sistema de control por acción precalculada para el intercambiador de calor",
  "description": "Diagrama de instrumentación que muestra el controlador por acción precalculada, los transmisores de flujo (FT-11) y temperatura (TT-11), el transductor I/P (FY-11) y la válvula de control de vapor. Las perturbaciones Tᵢ(t) y q(t) se miden y se envían al controlador por acción precalculada, cuya salida maneja la válvula de vapor.",
  "elements": [
    "Controlador por acción precalculada",
    "Transmisor de flujo FT-11",
    "Transmisor de temperatura TT-11",
    "Transductor I/P FY-11",
    "Válvula de control de vapor",
    "Intercambiador de calor",
    "Trampa de vapor"
  ],
  "relationships": [
    "q(t) → FT-11 → Controlador",
    "Tᵢ(t) → TT-11 → Controlador",
    "Controlador → FY-11 → Válvula de vapor"
  ],
  "source": "Smith & Corripio, Control Automático de Procesos, Fig. 1-5"
}
```

En la sección 1-2 se mencionó que existen varios tipos de perturbaciones; el sistema de control por acción precalculada que se muestra en la figura 1-5, sólo compensa a dos de ellas, si cualquier otra perturbación entra al proceso no se compensará con esta estrategia y puede originarse una desviación permanente de la variable respecto al punto de control. Para evitar esta desviación se debe añadir alguna retroalimentación de compensación al control por acción precalculada, esto se muestra en la figura 1-6. Ahora el control por acción precalculada compensa las perturbaciones más serias, Tᵢ(t) y q(t), mientras que el control por retroalimentación compensa todas las demás.

```json
{
  "type": "diagram",
  "id": "diagram-02",
  "page": 24,
  "title": "Figura 1-6. Control por acción precalculada del intercambiador de calor con compensación por retroalimentación",
  "caption": "Sistema de control por acción precalculada con compensación por retroalimentación",
  "description": "Diagrama de instrumentación que muestra el controlador por acción precalculada, los transmisores de flujo (FT-11) y temperatura (TT-11), el transductor I/P (FY-11), la válvula de control de vapor, el controlador por retroalimentación (TIC-10) y el transmisor de temperatura (TT-10). La compensación por retroalimentación se añade al control por acción precalculada.",
  "elements": [
    "Controlador por acción precalculada",
    "Transmisor de flujo FT-11",
    "Transmisor de temperatura TT-11",
    "Transductor I/P FY-11",
    "Válvula de control de vapor",
    "Controlador por retroalimentación TIC-10",
    "Transmisor de temperatura TT-10",
    "Intercambiador de calor"
  ],
  "relationships": [
    "q(t) → FT-11 → Controlador precalculado",
    "Tᵢ(t) → TT-11 → Controlador precalculado",
    "Controlador precalculado → FY-11 → Válvula de vapor",
    "T(t) → TT-10 → TIC-10 → Controlador precalculado"
  ],
  "source": "Smith & Corripio, Control Automático de Procesos, Fig. 1-6"
}
```

En el capítulo 8 se presenta el desarrollo del controlador por acción precalculada y los instrumentos que se requieren para su establecimiento. En el estudio de esta importante estrategia se utilizan casos reales de la industria.

Es importante hacer notar que en esta estrategia de control más "avanzada" aún están presentes las tres operaciones básicas, M, D y A. Los sensores y los transmisores realizan la medición; la decisión la toman el controlador por acción precalculada y el controlador por retroalimentación, TIC-10; la acción la realiza la válvula de vapor.

En general, las estrategias de control que se presentan en el capítulo 8 son más costosas, requieren una mayor inversión en el equipo y en la mano de obra necesarios para su diseño, implementación y mantenimiento que el control por retroalimentación. Por ello debe justificarse la inversión de capital antes de implementar algún sistema. El mejor procedimiento es diseñar e implementar primero una estrategia de control sencilla, teniendo en mente que si no resulta satisfactoria, entonces se justifica una estrategia más "avanzada", sin embargo, es importante estar consciente de que en estas estrategias avanzadas aún se requiere alguna retroalimentación de compensación.

## 1-6. RAZONES PRINCIPALES PARA EL CONTROL DE PROCESO

En este capítulo se definió el control automático de proceso como "una manera de mantener la variable controlada en punto de control, a pesar de las perturbaciones". Ahora es conveniente enumerar algunas de las "razones" por las cuales esto es importante, estas razones son producto de la experiencia industrial, tal vez no sean las únicas, pero sí las más importantes.

1. Evitar lesiones al personal de la planta o daño al equipo. La seguridad siempre debe estar en la mente de todos, esta es la consideración más importante.
2. Mantener la calidad del producto (composición, pureza, color, etc.) en un nivel continuo y con un costo mínimo.
3. Mantener la tasa de producción de la planta al costo mínimo.

Por tanto, se puede decir que las razones de la automatización de las plantas de proceso son proporcionar un entorno seguro y a la vez mantener la calidad deseada del producto y alta eficiencia de la planta con reducción de la demanda de trabajo humano.

## 1-7. BASES NECESARIAS PARA EL CONTROL DE PROCESO

Para tener éxito en la práctica del control automático de proceso, el ingeniero debe comprender primero los principios de la ingeniería de proceso. Por lo tanto, en este libro se supone que el lector conoce los principios básicos de termodinámica, flujo de fluidos, transferencia de calor, proceso de separación, procesos de reacción, etc.

Para estudiar el control de proceso también es importante entender el comportamiento dinámico de los procesos; por consiguiente, es necesario desarrollar el sistema de ecuaciones que describe diferentes procesos, esto se conoce como **modelación**; para desarrollar modelos es preciso conocer los principios que se mencionan en el párrafo precedente y tener conocimientos matemáticos, incluyendo ecuaciones diferenciales. En el control de proceso se usan bastante las transformadas de Laplace, con ellas se simplifica en gran medida la solución de las ecuaciones diferenciales y el análisis de los procesos y sus sistemas de control. En el capítulo 2 de este libro el interés se centra en el desarrollo y utilización de las transformadas de Laplace y se hace un repaso del álgebra de números complejos.

Otro recurso importante para el estudio y práctica del control de proceso es la simulación por computadora. Muchas de las ecuaciones que se desarrollan para describir los procesos son de naturaleza no lineal y, en consecuencia, la manera más exacta de resolverlas es mediante métodos numéricos, es decir, solución por computadora. La solución por computadora de los modelos de proceso se llama **simulación**. En los capítulos 3 y 4 se hace la introducción al modelo de algunos procesos simples y en el capítulo 9 se desarrollan modelos para procesos más complejos, asimismo, se presenta la introducción a la simulación.

## 1-8. RESUMEN

En este capítulo se trató la necesidad del control automático de proceso. Los procesos industriales no son estáticos, por el contrario, son muy dinámicos, cambian continuamente debido a los muchos tipos de perturbaciones y precisamente por eso se necesita que los sistemas de control vigilen continua y automáticamente las variaciones que se deben controlar.

Los principios de funcionamiento del sistema de control se pueden resumir con tres letras M, D, A. M se refiere a la medición de las variables del proceso; D se refiere a la decisión que se toma con base en las mediciones de las variables del proceso. Finalmente, A se refiere a la acción que se debe realizar de acuerdo con la decisión tomada.

También se explicó lo relativo a los componentes básicos del sistema de control: sensor, transmisor, controlador y elemento final de control. Los tipos más comunes de señales: neumática, electrónica o eléctrica y digital, se introdujeron junto con la exposición del propósito de los transductores.

Se expusieron dos estrategias de control: control por retroalimentación y por acción precalculada. Se expusieron brevemente las ventajas y desventajas de ambas estrategias. El tema de los capítulos 6 y 7 es el diseño y análisis de los circuitos de control por retroalimentación. El control por acción precalculada se presenta con más detalle en el capítulo 8, junto con otras estrategias de control.

Al escribir este libro siempre se tuvo conciencia de que, para tener éxito, el ingeniero debe aplicar los principios que aprende. En el libro se cubren los principios necesarios para la práctica exitosa del control automático de proceso. En él abundan los ejemplos de casos reales producto de la experiencia de los autores como ingenieros activos en el control de procesos o como consultores. Se espera que este libro despierte un mayor interés en el estudio del control automático de proceso, ya que es un área muy dinámica, desafiante y llena de satisfacciones de la ingeniería de proceso.

---

# Capítulo 2: Matemáticas necesarias para el análisis de los sistemas de control

Se ha comprobado que las técnicas de transformada de Laplace y linealización son particularmente útiles para el análisis de la dinámica de los procesos y diseño de sistemas de control, debido a que proporcionan una visión general del comportamiento de gran variedad de procesos e instrumentos. Por el contrario, la técnica de simulación por computadora permite realizar un análisis preciso y detallado del comportamiento dinámico de sistemas específicos, pero rara vez es posible generalizar para otros procesos los resultados obtenidos.

En este capítulo se revisará el método de la transformada de Laplace para resolver ecuaciones diferenciales lineales. Mediante este método se puede convertir una ecuación diferencial lineal en una algebraica, que, a su vez, permite el desarrollo del útil concepto de funciones de transferencia, el cual se introduce en este capítulo y se utiliza ampliamente en los subsecuentes. Puesto que las ecuaciones diferenciales que representan la mayoría de los procesos son no lineales, aquí se introduce el método de linealización para aproximarlas a las ecuaciones diferenciales lineales, de manera que se les pueda aplicar la técnica de transformadas de Laplace. Para trabajar con las transformadas de Laplace se requiere cierta familiaridad con los números complejos, por ello se incluye como una sección separada, una breve explicación del álgebra de los números complejos. El conocimiento de la transformada de Laplace es esencial para entender los fundamentos de la dinámica del proceso y del diseño de los sistemas de control.

## 2-1. TRANSFORMADA DE LAPLACE

### Definición

La transformada de Laplace de una función del tiempo, f(t), se define mediante la siguiente fórmula:

$$F(s) = \mathcal{L}[f(t)] = \int_{0}^{\infty} f(t)e^{-st}dt \quad (2-1)$$

donde:
- $f(t)$ es una función del tiempo
- $F(s)$ es la transformada de Laplace correspondiente
- $s$ es la variable de la transformada de Laplace
- $t$ es el tiempo

En la aplicación de la transformada de Laplace al diseño de sistemas de control, las funciones del tiempo son las variables del sistema, inclusive la variable manipulada y la controlada, las señales del transmisor, las perturbaciones, las posiciones de la válvula de control, el flujo a través de las válvulas de control y cualquier otra variable o señal intermedia. Por lo tanto, es muy importante darse cuenta que la transformada de Laplace se aplica a las variables y señales, y no a los procesos o instrumentos.

Para lograr la familiarización con la definición de la transformada de Laplace, se buscará la transformada de varias señales de entrada comunes.

**Ejemplo 2-1.** En el análisis de los sistemas de control se aplican señales a la entrada del sistema (por ejemplo, perturbaciones, cambios en el punto de control, etc.) para estudiar su respuesta. A pesar de que en la práctica, generalmente, es difícil o incluso imposible lograr algunos tipos de señales, estas proporcionan herramientas útiles para comparar las respuestas. En este ejemplo se obtendrá la transformada de Laplace de:

a) Una función de escalón unitario.
b) Un pulso.
c) Una función de impulso unitario.
d) Una onda senoidal.

**Solución:**

**a) Función de escalón unitario**

Este es un cambio súbito de magnitud unitaria en un tiempo igual a cero; dicha función se ilustra gráficamente en la figura 2-1a, y se representa algebraicamente mediante la expresión:

$$u(t) = \begin{cases} 0 & t < 0 \\ 1 & t \geq 0 \end{cases}$$

Su transformada de Laplace está dada por:

$$\mathcal{L}[u(t)] = \int_{0}^{\infty} u(t)e^{-st}dt = \left. -\frac{1}{s}e^{-st} \right|_{0}^{\infty} = -\frac{1}{s}(0 - 1)$$

$$\mathcal{L}[u(t)] = \frac{1}{s}$$

**b) Pulso de magnitud H y duración T**

El pulso se muestra gráficamente en la figura 2-1b y su representación algebraica es:

Su transformada de Laplace está dada por:

$$\mathcal{L}[f(t)] = \int_{0}^{\infty} f(t)e^{-st}dt = \int_{0}^{T} He^{-st}dt$$

$$= -\frac{H}{s}e^{-sT}\bigg|_{0}^{T} = -\frac{H}{s}(e^{-sT} - 1)$$

$$\mathcal{L}[f(t)] = \frac{H}{s}(1 - e^{-sT})$$

**c) Función de impulso unitario**

Esta es un pulso ideal de amplitud infinita y duración cero, cuya área es la unidad, en otras palabras, un pulso de área unitaria con toda ella concentrada en un tiempo igual a cero. Esta función se esboza en la figura 2-1c. Generalmente se usa el símbolo $\delta(t)$ para representarla, y se le conoce como función "delta Dirac". Su expresión algebraica se puede obtener mediante el uso de los límites de la función pulso de la parte (b):

$$\delta(t) = \lim_{T \to 0} f(t)$$

con:
$$HT = 1 \text{ (el área) o } H = 1/T$$

La transformada de Laplace se puede obtener tomando el límite del resultado de la parte b):

$$\mathcal{L}[\delta(t)] = \lim_{T \to 0} \frac{1}{Ts}(1 - e^{-sT}) = \frac{1}{0}(1 - 1) = \frac{0}{0}$$

Ahora se requiere la aplicación de la regla de L'Hopital para límites indefinidos:

$$\mathcal{L}[\delta(t)] = \lim_{T \to 0} \frac{\frac{d}{dT}(1 - e^{-sT})}{\frac{d}{dT}(Ts)}$$

$$= \lim_{T \to 0} \frac{se^{-sT}}{s}$$

$$\mathcal{L}[\delta(t)] = 1$$

Este es un resultado muy significativo, pues indica que la transformada de Laplace del impulso unitario es la unidad.

**d) Onda senoidal de amplitud y frecuencia ω**

La onda senoidal se muestra en la figura 2-1d, y su representación en forma exponencial es:

$$\text{sen }\omega t = \frac{e^{i\omega t} - e^{-i\omega t}}{2i}$$

donde $i = \sqrt{-1}$ es la unidad de los números imaginarios. Su transformada de Laplace está dada por:

$$\mathcal{L}[\sin \omega t] = \int_{0}^{\infty} \sin \omega t \, e^{-st}dt$$

$$= \int_{0}^{\infty} \frac{e^{i\omega t} - e^{-i\omega t}}{2i} e^{-st}dt$$

$$= \frac{1}{2i}\left[\int_{0}^{\infty} e^{-(s-i\omega)t}dt - \int_{0}^{\infty} e^{-(s+i\omega)t}dt\right]$$

$$= \frac{1}{2i}\left[-\frac{e^{-(s-i\omega)t}}{s-i\omega} + \frac{e^{-(s+i\omega)t}}{s+i\omega}\right]_{0}^{\infty}$$

$$= \frac{1}{2i}\left[-\frac{0-1}{s-i\omega} + \frac{0-1}{s+i\omega}\right]$$

$$= \frac{1}{2i}\frac{2i\omega}{s^2 + \omega^2}$$

$$\mathcal{L}[\sin \omega t] = \frac{\omega}{s^2 + \omega^2}$$

Con el ejemplo precedente se ilustra en parte el manejo algebraico que implica la obtención de la transformada de Laplace de una señal. En la mayoría de los manuales de matemáticas e ingeniería aparecen tablas de las transformadas de Laplace; la tabla 2-1 es una breve lista de la transformada de algunas de las funciones más comunes.

```json
{
  "type": "table",
  "id": "table-01",
  "page": 32,
  "title": "Tabla 2-1. Transformada de Laplace de funciones más usuales",
  "headers": ["f(t)", "F(s) = ℒ[f(t)]"],
  "rows": [
    ["δ(t)", "1"],
    ["u(t)", "1/s"],
    ["t", "1/s²"],
    ["tⁿ", "n!/sⁿ⁺¹"],
    ["e⁻ᵃᵗ", "1/(s+a)"],
    ["t e⁻ᵃᵗ", "1/(s+a)²"],
    ["tⁿ e⁻ᵃᵗ", "n!/(s+a)ⁿ⁺¹"],
    ["sen ωt", "ω/(s²+ω²)"],
    ["cos ωt", "s/(s²+ω²)"],
    ["e⁻ᵃᵗ sen ωt", "ω/((s+a)²+ω²)"],
    ["e⁻ᵃᵗ cos ωt", "(s+a)/((s+a)²+ω²)"]
  ],
  "notes": "Tabla de transformadas de Laplace de funciones comunes",
  "source": "Smith & Corripio, Control Automático de Procesos, Tabla 2-1"
}
```

### Propiedades de la transformada de Laplace

En esta sección se explican algunas propiedades importantes de la transformada de Laplace, las cuales son útiles porque permiten obtener la transformada de algunas funciones a partir de las más simples, como las que aparecen en la tabla 2-1; establecer la relación de la transformada de una función con sus derivadas e integrales; así como la determinación de los valores inicial y final de una función a partir de su transformada.

**Linealidad.** Esta propiedad, la más importante, establece que la transformada de Laplace es lineal; es decir, si $k$ es una constante:

$$\mathcal{L}[k f(t)] = k\mathcal{L}[f(t)] = k F(s) \quad (2-2)$$

Puesto que es lineal, la propiedad distributiva también es válida para la transformada de Laplace:

$$\mathcal{L}[f(t) + g(t)] = \mathcal{L}[f(t)] + \mathcal{L}[g(t)] = F(s) + G(s) \quad (2-3)$$

Ambas propiedades se pueden demostrar fácilmente mediante la aplicación de la definición de transformada de Laplace, ecuación (2-1).

**Teorema de la diferenciación real.** Este teorema establece la relación de la transformada de Laplace de una función con la de su derivada. Su expresión matemática es:

$$\mathcal{L}\left[\frac{df(t)}{dt}\right] = sF(s) - f(0) \quad (2-4)$$

**Demostración.** De la definición de transformada de Laplace, ecuación (2-1):

$$\mathcal{L}\left[\frac{df(t)}{dt}\right] = \int_{0}^{\infty} \frac{df(t)}{dt} e^{-st}dt$$

Integrando por partes:
$$u = e^{-st} \qquad dv = \frac{df(t)}{dt}dt$$
$$du = -se^{-st}dt \qquad v = f(t)$$

$$\mathcal{L}\left[\frac{df(t)}{dt}\right] = f(t)e^{-st}\bigg|_{0}^{\infty} - \int_{0}^{\infty} f(t)(-se^{-st}dt)$$

$$= \{0 - f(0)\} + s\int_{0}^{\infty} f(t)e^{-st}dt$$

$$= -f(0) + s\mathcal{L}[f(t)]$$

$$= sF(s) - f(0) \qquad \text{q.e.d.}$$

La extensión a derivadas de orden superior es directa:

$$\mathcal{L}\left[\frac{d^2f(t)}{dt^2}\right] = \mathcal{L}\left[\frac{d}{dt}\left(\frac{df(t)}{dt}\right)\right]$$

$$= s\mathcal{L}\left[\frac{df(t)}{dt}\right] - \frac{df}{dt}(0)$$

$$= s[sF(s) - f(0)] - \frac{df}{dt}(0)$$

$$= s^2F(s) - sf(0) - \frac{df}{dt}(0)$$

En general:

$$\mathcal{L}\left[\frac{d^nf(t)}{dt^n}\right] = s^nF(s) - s^{n-1}f(0) - s^{n-2}\frac{df}{dt}(0) - \ldots - \frac{d^{n-1}f}{dt^{n-1}}(0) \quad (2-5)$$

Para el caso, el más importante, en que la función y sus derivadas tienen condiciones iniciales cero, la expresión se simplifica a:

$$\mathcal{L}\left[\frac{d^nf(t)}{dt^n}\right] = s^nF(s) \quad (2-6)$$

Como se puede ver, para el caso de condiciones iniciales cero, la obtención de la transformada de Laplace de la derivada de una función se hace simplemente mediante la substitución del operador "$d/dt$" por la variable $s$, y la de $f(t)$ por $F(s)$.

**Teorema de la integración real.** Este teorema establece la relación entre la transformada de una función y la de su integral. Su expresión es:

$$\mathcal{L}\left[\int_{0}^{t} f(t)dt\right] = \frac{1}{s}F(s) \quad (2-7)$$

**Demostración.** De la definición de transformada de Laplace, ecuación (2-1):

$$\mathcal{L}\left[\int_{0}^{t} f(t)dt\right] = \int_{0}^{\infty}\left[\int_{0}^{t} f(t)dt\right]e^{-st}dt$$

Integrando por partes:
$$u = \int_{0}^{t} f(t)dt \qquad dv = e^{-st}dt$$
$$du = f(t)dt \qquad v = -\frac{1}{s}e^{-st}$$

$$\mathcal{L}\left[\int_{0}^{t} f(t)dt\right] = -\frac{1}{s}e^{-st}\int_{0}^{t} f(t)dt\bigg|_{0}^{\infty} - \int_{0}^{\infty} f(t)dt\left(-\frac{1}{s}e^{-st}\right)$$

$$= -\frac{1}{s}\left[0 - \int_{0}^{0} f(t)dt\right] + \frac{1}{s}\int_{0}^{\infty} f(t)e^{-st}dt$$

$$= \frac{1}{s}\mathcal{L}[f(t)] = \frac{1}{s}F(s) \qquad \text{q.e.d.}$$

Nótese que en esta derivación se supone que el valor inicial de la integral es cero; en tales condiciones, la integral n de una función es la transformada de la función entre $s^n$.

**Teorema de la diferenciación compleja.** Con este teorema se facilita la evaluación de las transformadas que implican la variable de tiempo $t$, y se expresa mediante:

$$\mathcal{L}[t f(t)] = -\frac{d}{ds}F(s) \quad (2-8)$$

**Demostración.** A partir de la definición de transformada de Laplace, ecuación (2-1), se tiene que:

$$F(s) = \int_{0}^{\infty} f(t)e^{-st}dt$$

Tomando la derivada de esta ecuación respecto a $s$:

$$\frac{dF(s)}{ds} = \int_{0}^{\infty} f(t)(-te^{-st})dt$$

$$= -\mathcal{L}[t f(t)]$$

Al reacomodar este resultado se obtiene la expresión del teorema mencionado.

**Teorema de la traslación real.** En este teorema se trabaja con la traslación de una función en el eje del tiempo, como se ilustra en la figura 2-2. La función trasladada es la función original con retardo en tiempo. Como se verá en el capítulo 3, el retardo de transporte ocasiona retardos de tiempo en el proceso; este fenómeno se conoce comúnmente como **tiempo muerto**.

Puesto que la transformada de Laplace no contiene información acerca de la función original para tiempo negativo, se supone que la función retardada es cero, para todos los tiempos menores al tiempo de retardo (ver figura 2-2). El teorema se expresa mediante la siguiente fórmula:

$$\mathcal{L}[f(t - t_0)] = e^{-st_0}F(s) \quad (2-9)$$

**Demostración.** A partir de la definición de transformada de Laplace, ecuación (2-1), se tiene:

$$\mathcal{L}[f(t - t_0)] = \int_{0}^{\infty} f(t - t_0)e^{-st}dt$$

Sea $\tau = t - t_0$ (o $t = t_0 + \tau$) y substituyendo:

$$\mathcal{L}[f(t - t_0)] = \int_{t_0}^{\infty} f(\tau)e^{-s(\tau + t_0)}d(\tau + t_0)$$

$$= \int_{\tau = -t_0}^{\infty} f(\tau)e^{-s\tau}e^{-st_0}d\tau$$

$$= e^{-st_0}\int_{-t_0}^{\infty} f(\tau)e^{-s\tau}d\tau$$

$$= e^{-st_0}\int_{0}^{\infty} f(\tau)e^{-s\tau}d\tau$$

$$= e^{-st_0}F(s) \qquad \text{q.e.d.}$$

Nótese que en esta demostración se aprovechó el hecho de que:
$$f(\tau) = 0 \text{ para } \tau < 0 \text{ (} \tau < t_0\text{)}$$

```json
{
  "type": "image",
  "id": "image-05",
  "page": 35,
  "title": "Figura 2-2. La función que se traslada en tiempo es cero para todos los tiempos menores al tiempo de retardo t₀",
  "caption": "Traslación real de una función en el tiempo",
  "description": "Gráfica que muestra dos funciones: f(t) y f(t-t₀). La función f(t) comienza en t=0, mientras que f(t-t₀) comienza en t=t₀. Se indica que la función trasladada es cero para t < t₀.",
  "elements": [
    "Eje de tiempo t",
    "Eje de f(t)",
    "Función f(t)",
    "Función f(t-t₀)",
    "Tiempo de retardo t₀"
  ],
  "source": "Smith & Corripio, Control Automático de Procesos, Fig. 2-2"
}
```

**Teorema de la traslación compleja.** Este teorema facilita la evaluación de la transformada de funciones que implican al tiempo como exponente.

$$\mathcal{L}[e^{-at}f(t)] = F(s + a) \quad (2-10)$$

**Teorema del valor inicial.** Este teorema permite determinar el valor de una función en el tiempo cero a partir de su transformada de Laplace:

$$\lim_{t \to 0} f(t) = \lim_{s \to \infty} sF(s) \quad (2-11)$$

**Teorema del valor final.** Este teorema permite determinar el valor de una función cuando el tiempo tiende a infinito a partir de su transformada de Laplace:

$$\lim_{t \to \infty} f(t) = \lim_{s \to 0} sF(s) \quad (2-12)$$

**Ejemplo 2-2.** Obténgase la transformada de Laplace de la siguiente ecuación diferencial:

$$\frac{d^2x(t)}{dt^2} + 2\xi\omega_n\frac{dx(t)}{dt} + \omega_n^2x(t) = K r(t)$$

donde $\xi$, $\omega_n$ y $K$ son constantes. Las condiciones iniciales son cero.

**Solución.** Al aplicar la propiedad de linealidad de la transformada de Laplace, ecuaciones (2-2) y (2-3), se obtiene la transformada de cada término; posteriormente se aplica el teorema de la diferenciación real, ecuación (2-5):

$$\mathcal{L}\left[\frac{d^2x(t)}{dt^2}\right] = s^2X(s) - sx(0) - \frac{dx}{dt}(0) = s^2X(s)$$

$$\mathcal{L}\left[2\xi\omega_n\frac{dx(t)}{dt}\right] = 2\xi\omega_n\mathcal{L}\left[\frac{dx(t)}{dt}\right]$$

$$= 2\xi\omega_n[sX(s) - x(0)]$$

$$= 2\xi\omega_n sX(s)$$

$$\mathcal{L}[\omega_n^2x(t)] = \omega_n^2\mathcal{L}[x(t)] = \omega_n^2X(s)$$

$$\mathcal{L}[Kr(t)] = K\mathcal{L}[r(t)] = KR(s)$$

De la substitución en la ecuación original se obtiene:

$$s^2X(s) + 2\xi\omega_n sX(s) + \omega_n^2X(s) = KR(s)$$

resolviendo para $X(s)$, se tiene:

$$X(s) = \frac{K}{s^2 + 2\xi\omega_n s + \omega_n^2}R(s) \quad (1)$$

En el ejemplo precedente se ilustra el hecho de que la transformada de Laplace convierte la ecuación diferencial original en una ecuación algebraica, en esto estriba la gran utilidad de la transformada de Laplace, ya que el manejo de las ecuaciones algebraicas es mucho más fácil que el de las diferenciales. Sin embargo, el precio de esta ventaja es que es necesario transformar y después invertir la transformada para obtener la solución en el "dominio del tiempo", esto es, con el tiempo como variable independiente.

**Ejemplo 2-3.** Obténgase la transformada de Laplace de la siguiente función:

$$y(t) = te^{-at} \quad (1)$$

donde $a$ es una constante.

**Solución.** La transformada $Y(s)$ se puede obtener con el uso de una de dos propiedades: el teorema de diferenciación compleja o el de traslación compleja.

Aplicando el teorema de diferenciación compleja, ecuación (2-8), se obtiene:

$$f(t) = e^{-at} \qquad F(s) = \frac{1}{s+a} \quad \text{(de la tabla 2-1)}$$

$$Y(s) = \mathcal{L}[te^{-at}] = \mathcal{L}[tf(t)] = -\frac{d}{ds}F(s)$$

$$= -\frac{d}{ds}\left(\frac{1}{s+a}\right) = -\left[\frac{-1}{(s+a)^2}\right]$$

$$Y(s) = \frac{1}{(s+a)^2}$$

Se puede obtener el mismo resultado mediante la aplicación del teorema de la traslación compleja, ecuación (2-10): Sea

$$f(t) = t \qquad F(s) = \frac{1}{s^2} \quad \text{(de la tabla 2-1)}$$

entonces:

$$\mathcal{L}[e^{-at}t] = \mathcal{L}[e^{-at}f(t)] = F(s+a)$$

$$= \frac{1}{(s+a)^2} = \frac{1}{(s+a)^2}$$

Con esto se verifica el resultado anterior.

Ahora se comprueba la validez de la transformada mediante la aplicación de los teoremas del valor inicial y final.

**Valor inicial:**
$$\lim_{t \to 0} y(t) = 0 \cdot e^{-a(0)} = 0$$
$$\lim_{s \to \infty} sY(s) = \lim_{s \to \infty} \frac{s}{(s+a)^2} = \frac{\infty}{\infty}$$

De la regla de L'Hopital:
$$\lim_{s \to \infty} Y(s) = \lim_{s \to \infty} \frac{1}{2(s+a)} = 0 \quad \text{(se comprueba)}$$

**Valor final:**
$$\lim_{t \to \infty} y(t) = \lim_{t \to \infty} \frac{t}{e^{at}} = \frac{\infty}{\infty}$$

De la regla de L'Hopital:
$$\lim_{t \to \infty} y(t) = \lim_{t \to \infty} \frac{1}{ae^{at}} = 0$$
$$\lim_{s \to 0} sY(s) = \lim_{s \to 0} \frac{s}{(s+a)^2} = \frac{0}{a^2} = 0 \quad \text{(se comprueba)}$$

Desafortunadamente cero no es una comprobación muy confiable, ya que no permite la detección de errores de signo.

**Ejemplo 2-4.** Obténgase la transformada de Laplace de la siguiente función en retardo de tiempo:

$$m(t) = u(t-3)e^{-(t-3)}\cos \omega(t-3)$$

donde $\omega$ es una constante.

**Nota:** En esta expresión se incluye el término $u(t-3)$ para aclarar explícitamente que la función vale cero cuando $t < 3$. Recuérdese que $u(t-3)$ es la función de escalón unitario en $t=3$.

**Solución.** Sea:
$$f(t-3) = e^{-(t-3)}\cos \omega(t-3)$$

entonces:
$$f(t) = e^{-t}\cos \omega t$$
$$F(s) = \frac{(s+1)}{(s+1)^2 + \omega^2} \quad \text{(de la tabla 2-1)}$$

Por aplicación del teorema de la traslación real, ecuación (2-9):

$$M(s) = e^{-3s}F(s) = \frac{(s+1)e^{-3s}}{(s+1)^2 + \omega^2}$$

Ahora se verifica la validez de este resultado mediante la aplicación de los teoremas del valor inicial y final.

**Valor inicial:**
$$\lim_{t \to 0} m(t) = u(-3)(e^{+3})\cos(-3\omega) = 0$$
ya que $u(-3) = 0$.

$$\lim_{s \to \infty} sM(s) = \lim_{s \to \infty} \frac{s(s+1)e^{-3s}}{(s+1)^2 + \omega^2} = \frac{\infty \cdot (0)}{\infty}$$

Se puede separar la parte indefinida y aplicar la regla de L'Hopital:

$$\lim_{s \to \infty} sM(s) = \left[\lim_{s \to \infty} \frac{s(s+1)}{(s+1)^2 + \omega^2}\right]\left[\lim_{s \to \infty} e^{-3s}\right] = \left[\frac{\infty}{\infty}\right][0]$$

$$= \left[\lim_{s \to \infty} \frac{2s+1}{2(s+1)}\right]\left[\lim_{s \to \infty} e^{-3s}\right] = \left[\frac{\infty}{\infty}\right][0]$$

$$= \left[\lim_{s \to \infty} \frac{2}{2}\right][0] = 0 \quad \text{(se comprueba)}$$

**Valor final:**
En principio, el teorema del valor final no se puede aplicar a las funciones periódicas, debido a que dichas funciones oscilan siempre, sin llegar a alcanzar un punto estacionario; sin embargo, la aplicación del teorema del valor final a las funciones periódicas da por resultado el valor final alrededor del cual oscila la función.

$$\lim_{t \to \infty} m(t) = (1)(0)\cos(\infty) = 0$$
$$\lim_{s \to 0} sM(s) = \frac{(0)(1)e^0}{1^2 + \omega^2} = 0 \quad \text{(se comprueba)}$$

**Ejemplo 2-5.** Obténgase la transformada de Laplace de la siguiente función:

$$c(t) = [u(t) - e^{-t/\tau}]$$

en la que $\tau$ es una constante.

**Solución.** Aplicando la propiedad de linealidad, ecuación (2-3):

$$C(s) = \mathcal{L}[u(t) - e^{-t/\tau}]$$
$$= \mathcal{L}[u(t)] - \mathcal{L}[e^{-t/\tau}]$$
$$= \frac{1}{s} - \frac{1}{s + 1/\tau} \quad \text{(de la tabla 2-1)}$$
$$C(s) = \frac{1}{s(\tau s + 1)}$$

**Valor inicial:**
$$\lim_{t \to 0} c(t) = 1 - e^0 = 0$$
$$\lim_{s \to \infty} sC(s) = \lim_{s \to \infty} \frac{s}{s(\tau s + 1)} = \frac{1}{\infty} = 0 \quad \text{(se comprueba)}$$

**Valor final:**
$$\lim_{t \to \infty} c(t) = 1 - e^{-\infty} = 1$$
$$\lim_{s \to 0} sC(s) = \lim_{s \to 0} \frac{s}{s(\tau s + 1)} = 1 \quad \text{(se comprueba)}$$

## 2-2. SOLUCIÓN DE ECUACIONES DIFERENCIALES MEDIANTE EL USO DE LA TRANSFORMADA DE LAPLACE

Para ilustrar el uso de la transformada de Laplace en la resolución de ecuaciones diferenciales lineales ordinarias, considérese la siguiente ecuación diferencial de segundo orden:

$$a_2\frac{d^2y(t)}{dt^2} + a_1\frac{dy(t)}{dt} + a_0y(t) = bx(t) \quad (2-13)$$

El problema de resolver esta ecuación se puede plantear como sigue: dados los coeficientes $a_0$, $a_1$, $a_2$ y $b$, las condiciones iniciales apropiadas y la función $x(t)$, encuéntrese la función $y(t)$ que satisface la ecuación (2-13).

La función $x(t)$ se conoce generalmente como "función de forzamiento" o variable de entrada, y $y(t)$ como la "función de salida" o variable dependiente; la variable $t$, tiempo, es la variable independiente. Generalmente, en el diseño de los sistemas de control una ecuación diferencial como la (2-13) representa la forma en que se relaciona la señal de salida, $y(t)$, con la señal de entrada, $x(t)$, en un proceso particular.

### Procedimiento de solución por la transformada de Laplace

La solución de una ecuación diferencial mediante el uso de la transformada de Laplace implica básicamente tres pasos:

**Paso 1.** Transformación de la ecuación diferencial en una ecuación algebraica con la variable $s$ de la transformada de Laplace, lo cual se logra al obtener la transformada de Laplace de cada miembro de la ecuación:

$$\mathcal{L}\left[a_2\frac{d^2y(t)}{dt^2} + a_1\frac{dy(t)}{dt} + a_0y(t)\right] = \mathcal{L}[bx(t)] \quad (2-14)$$

Entonces, al usar la propiedad distributiva de la transformada, ecuación (2-2), y el teorema de la diferenciación real, ecuación (2-5), se ve que:

$$\mathcal{L}\left[a_2\frac{d^2y(t)}{dt^2}\right] = a_2\left[s^2Y(s) - sy(0) - \frac{dy}{dt}(0)\right]$$

$$\mathcal{L}\left[a_1\frac{dy(t)}{dt}\right] = a_1[sY(s) - y(0)]$$

$$\mathcal{L}[a_0y(t)] = a_0Y(s)$$

$$\mathcal{L}[bx(t)] = bX(s)$$

Posteriormente se substituyen estos términos en la ecuación (2-14) y se reordenan:

$$(a_2s^2 + a_1s + a_0)Y(s) - (a_2s + a_1)y(0) - a_2\frac{dy}{dt}(0) = bX(s)$$

Nótese que ésta es una ecuación algebraica y que la variable $s$ de la transformada de Laplace se puede tratar como cualquier otra cantidad algebraica.

**Paso 2.** Se emplea la ecuación algebraica que se resuelve para la variable de salida $Y(s)$, en términos de la variable de entrada y de las condiciones iniciales:

$$Y(s) = \frac{bX(s) + (a_2s + a_1)y(0) + a_2\frac{dy}{dt}(0)}{a_2s^2 + a_1s + a_0} \quad (2-15)$$

**Paso 3.** Inversión de la ecuación resultante para obtener la variable de salida en función del tiempo $y(t)$:

$$y(t) = \mathcal{L}^{-1}[Y(s)] \quad (2-16)$$

En este procedimiento los dos primeros pasos son relativamente fáciles y directos, todas las dificultades se concentran en el tercer paso. La utilidad de la transformada de Laplace en el diseño de sistemas de control tiene como fundamento el hecho de que rara vez es necesario el paso de inversión, debido a que todas las características de la respuesta en tiempo $y(t)$ se pueden reconocer en los términos de $Y(s)$; en otras palabras, el análisis completo se puede hacer en el dominio de Laplace o en el "dominio $s$", sin invertir la transformada en el "dominio del tiempo". En la cláusula precedente se usa el término "dominio" para designar a la variable independiente del campo en el que se realiza el análisis y diseño.

En el paso de inversión se establece la relación entre la transformada de Laplace, $Y(s)$, y su inversa, $y(t)$. El paso de inversión se puede demostrar mediante el método de la expansión de fracciones parciales, sin embargo, primero se generalizará la ecuación (2-15) para el caso de una ecuación de orden $n$.

Para la ecuación diferencial lineal ordinaria de orden $n$ con coeficientes constantes:

$$a_n\frac{d^ny(t)}{dt^n} + a_{n-1}\frac{d^{n-1}y(t)}{dt^{n-1}} + \ldots + a_0y(t) = b_m\frac{d^mx(t)}{dt^m} + b_{m-1}\frac{d^{m-1}x(t)}{dt^{m-1}} + \ldots + b_0x(t) \quad (2-17)$$

en condiciones iniciales cero:

$$y(0) = 0; \quad \frac{dy}{dt}(0) = 0; \quad \ldots; \quad \frac{d^{n-1}y}{dt^{n-1}}(0) = 0$$
$$x(0) = 0; \quad \frac{dx}{dt}(0) = 0; \quad \ldots; \quad \frac{d^{m-1}x}{dt^{m-1}}(0) = 0$$

es fácil demostrar que la ecuación de la transformada de Laplace está dada por:

$$Y(s) = \left[\frac{b_ms^m + b_{m-1}s^{m-1} + \ldots + b_0}{a_ns^n + a_{n-1}s^{n-1} + \ldots + a_0}\right]X(s) \quad (2-18)$$

El caso de condiciones iniciales cero es el más común en el diseño de sistemas de control, ya que las señales se definen generalmente como desviaciones respecto a un estado inicial estacionario (ver sección 2-3). Cuando se hace esto, el valor inicial de la perturbación, por definición, es cero; los valores iniciales de las derivadas del tiempo son también cero, pues se supone que el sistema está inicialmente en un estado estacionario; es decir, no cambia con el tiempo.

**Función de transferencia.** Si las variables $X(s)$ y $Y(s)$ de la ecuación (2-18) son las respectivas transformadas de las señales de entrada y de salida de un proceso, instrumento o sistema de control, el término entre corchetes representa por definición, la función de transferencia del proceso, instrumento o sistema de control. Dicha función es la expresión que, al multiplicarse por la transformada de la señal de entrada, da como resultado la transformada de la función de salida. La función de transferencia proporciona un mecanismo útil para el análisis del comportamiento dinámico y el diseño de sistemas de control. Se tratará con mayor detalle en el capítulo 3.

### Inversión de la transformada de Laplace mediante expansión de fracciones parciales

El último paso en el proceso de solución de una ecuación diferencial mediante la transformada de Laplace es la inversión de la ecuación algebraica de la variable de salida, $Y(s)$, la cual se puede representar mediante:

$$y(t) = \mathcal{L}^{-1}[Y(s)] \quad (2-19)$$

Puesto que este es el paso más difícil del procedimiento de solución, esta sección tiene por objetivo establecer la relación general entre la transformada de la variable de salida $Y(s)$ y su inversa $y(t)$. Con este procedimiento se puede realizar el análisis de la respuesta del sistema mediante el análisis de su función transformada $Y(s)$, sin tener que invertirla realmente. A continuación se establece la relación entre $Y(s)$ y $y(t)$ por medio del método de expansión de fracciones parciales, el cual fue introducido por primera vez por el físico británico Oliver Heaviside (1850-1925) como parte de su revolucionario "cálculo operacional".

Como se vio en la sección precedente, la transformada de Laplace de la salida o variable dependiente de una ecuación diferencial lineal de orden $n$ con coeficientes constantes, se puede expresar mediante:

$$Y(s) = \left[\frac{b_ms^m + b_{m-1}s^{m-1} + \ldots + b_0}{a_ns^n + a_{n-1}s^{n-1} + \ldots + a_0}\right]X(s) \quad (2-18)$$

donde:
- $Y(s)$ es la transformada de Laplace de la variable de salida
- $X(s)$ es la transformada de Laplace de la variable de entrada
- $a_0, a_1, \ldots, a_n$ son los coeficientes constantes de la variable de salida y sus derivadas
- $b_0, b_1, \ldots, b_m$ son los coeficientes constantes de la variable de entrada y sus derivadas

Si se observa la tabla 2-1, se puede ver que la transformada de Laplace de las funciones más comunes es una relación de polinomios en las variables de la transformada de Laplace. Si se supone que este es el caso de $X(s)$, se puede demostrar fácilmente que $Y(s)$ también es la relación de dos polinomios:

$$Y(s) = \frac{(b_ms^m + b_{m-1}s^{m-1} + \ldots + b_0)[\text{numerador de } X(s)]}{(a_ns^n + a_{n-1}s^{n-1} + \ldots + a_0)[\text{denominador de } X(s)]} \quad (2-20)$$

$$= \frac{N(s)}{D(s)}$$

donde:
- $N(s) = \beta_js^j + \beta_{j-1}s^{j-1} + \ldots + \beta_1s + \beta_0$
- $D(s) = s^k + \alpha_{k-1}s^{k-1} + \ldots + \alpha_1s + \alpha_0$
- $\beta_0, \beta_1, \ldots, \beta_j$ son los coeficientes constantes del polinomio numerador $N(s)$ de grado $j$ ($j \geq m$)
- $\alpha_0, \alpha_1, \ldots, \alpha_{k-1}$ son los coeficientes constantes del polinomio denominador $D(s)$ de grado $k$ ($k \geq n$)

Nótese que se supuso que el coeficiente de $s^k$ en $D(s)$ es la unidad, lo cual se puede hacer sin pérdida de la generalidad, ya que siempre es posible dividir el numerador y el denominador entre el coeficiente de $s^k$ y cumplir con la ecuación (2-20).

Se puede demostrar que la ecuación (2-20) también representa el caso en que la variable de salida responde a más de una función de forzamiento de entrada; sin embargo, no representa el caso en que el sistema o la señal de entrada contengan retardos de tiempo (retardos de transporte o tiempos muertos). Con el fin de simplificar, por el momento no se trata este caso tan importante, ya que se considera como especial al final de esta sección.

El primer paso de la expansión de fracciones parciales es la factorización del polinomio denominador $D(s)$:

$$D(s) = s^k + \alpha_{k-1}s^{k-1} + \ldots + \alpha_1s + \alpha_0$$
$$= (s - r_1)(s - r_2)\ldots(s - r_k) \quad (2-21)$$

donde $r_1, r_2, \ldots, r_k$ son las raíces del polinomio, es decir, los valores de $s$ que satisfacen la ecuación:

$$D(s) = s^k + \alpha_{k-1}s^{k-1} + \ldots + \alpha_1s + \alpha_0 = 0 \quad (2-22)$$

Es conveniente recordar que un polinomio de grado $k$ puede tener hasta $k$ raíces distintas y, como se ve, siempre se puede factorizar de la manera que se muestra en la ecuación (2-21); se observa que, al hacer $s$ igual a cualquiera de las raíces resultantes en uno de los factores $(s - r)$, éste se hace cero, y entonces $D(s) = 0$.

La substitución de la ecuación (2-21) en la ecuación (2-20) da como resultado:

$$Y(s) = \frac{N(s)}{(s - r_1)(s - r_2)\ldots(s - r_k)} \quad (2-23)$$

A partir de esta ecuación es posible demostrar que la transformada $Y(s)$ se puede expresar como la suma de $k$ fracciones:

$$Y(s) = \frac{A_1}{s - r_1} + \frac{A_2}{s - r_2} + \ldots + \frac{A_k}{s - r_k} \quad (2-24)$$

donde $A_1, A_2, \ldots, A_k$ son una serie de coeficientes constantes que se evalúan mediante un procedimiento de series. Este paso se conoce como "expansión en fracciones parciales". Una vez que se expande la transformada de la salida, como se hizo en la ecuación (2-24), se puede usar la propiedad distributiva de la transformada inversa para obtener la función inversa:

$$y(t) = \mathcal{L}^{-1}[Y(s)]$$
$$= \mathcal{L}^{-1}\left[\frac{A_1}{s - r_1} + \frac{A_2}{s - r_2} + \ldots + \frac{A_k}{s - r_k}\right]$$
$$= A_1\mathcal{L}^{-1}\left[\frac{1}{s - r_1}\right] + A_2\mathcal{L}^{-1}\left[\frac{1}{s - r_2}\right] + \ldots + A_k\mathcal{L}^{-1}\left[\frac{1}{s - r_k}\right] \quad (2-25)$$

Las inversas individuales generalmente se pueden determinar mediante el uso de una tabla de transformadas de Laplace como la tabla 2-1.

Para evaluar los coeficientes de las fracciones parciales y completar el proceso de inversión, se deben considerar cuatro casos:

1. Raíces reales no repetidas.
2. Pares no repetidos de raíces complejas conjugadas.
3. Raíces repetidas.
4. Presencia de tiempo muerto.

A continuación se expone cada uno de estos casos.

#### Caso 1. Raíces reales no repetidas

Para evaluar el coeficiente $A_i$ de una fracción que contiene una raíz real no repetida $r_i$, se multiplican ambos miembros de la ecuación (2-24) por el factor $(s - r_i)$, lo que da como resultado la siguiente ecuación, después de reordenar:

$$(s - r_i)Y(s) = \frac{A_1(s - r_i)}{s - r_1} + \ldots + A_i + \ldots + \frac{A_k(s - r_i)}{s - r_k} \quad (2-26)$$

Nótese que, como la raíz $r_i$ no se repite, no hay cancelación de los factores, a excepción de los de la fracción $i$. Al hacer $s = r_i$ en la ecuación (2-26), se obtiene la siguiente fórmula para el coeficiente $A_i$:

$$A_i = \lim_{s \to r_i}(s - r_i)Y(s) = \lim_{s \to r_i}(s - r_i)\frac{N(s)}{D(s)} \quad (2-27)$$

Esta fórmula se utiliza para evaluar los coeficientes de todas las fracciones que contienen raíces reales no repetidas. La inversa de los términos correspondientes de $Y(s)$ en la ecuación (2-25) es, según la tabla 2-1:

$$\mathcal{L}^{-1}\left[\frac{A_i}{s - r_i}\right] = A_i e^{r_i t} \quad (2-28)$$

Si todas las raíces de $D(s)$ son raíces reales no repetidas, la función inversa es:

$$y(t) = A_1e^{r_1t} + A_2e^{r_2t} + \ldots + A_ke^{r_kt} \quad (2-29)$$

A continuación se ilustra este procedimiento por medio de un ejemplo.

**Ejemplo 2-6.** De la ecuación diferencial de segundo orden:

$$\frac{d^2c(t)}{dt^2} + 3\frac{dc(t)}{dt} + 2c(t) = 5u(t)$$

en la que $u(t)$ es la función escalón unitario (ver ejemplo 2-1a), encuéntrese la función $c(t)$ que satisface a la ecuación para el caso en el que las condiciones iniciales son cero:

$$c(0) = 0; \quad \frac{dc}{dt}(0) = 0$$

**Solución.**

**Paso 1.** Se obtiene la transformada de Laplace de la ecuación:

$$s^2C(s) + 3sC(s) + 2C(s) = 5U(s)$$

**Paso 2.** Se resuelve para $C(s)$:

$$C(s) = \frac{5}{s^2 + 3s + 2}U(s)$$
$$= \frac{5}{s^2 + 3s + 2}\cdot\frac{1}{s}$$

$U(s) = 1/s$ se obtiene de la tabla 2-1.

**Paso 3.** Se invierte $C(s)$.

Las raíces del polinomio denominador son:

$$s(s^2 + 3s + 2) = 0$$
$$r_1 = 0$$
$$r_{2,3} = \frac{-3 \pm \sqrt{9-8}}{2} = -2, -1$$
$$s(s^2 + 3s + 2) = s(s+1)(s+2)$$

Se expande $C(s)$ en fracciones parciales, lo cual da como resultado:

$$C(s) = \frac{5}{s(s+1)(s+2)} = \frac{A_1}{s} + \frac{A_2}{s+1} + \frac{A_3}{s+2}$$

De la ecuación (2-27) se tiene que:

$$A_1 = \lim_{s \to 0} s\frac{5}{s(s+1)(s+2)} = \frac{5}{(1)(2)} = \frac{5}{2}$$

$$A_2 = \lim_{s \to -1}(s+1)\frac{5}{s(s+1)(s+2)} = \frac{5}{(-1)(1)} = -5$$

$$A_3 = \lim_{s \to -2}(s+2)\frac{5}{s(s+1)(s+2)} = \frac{5}{(-2)(-1)} = \frac{5}{2}$$

$$C(s) = \frac{5/2}{s} - \frac{5}{s+1} + \frac{5/2}{s+2}$$

Al invertir con ayuda de la tabla 2-1, se obtiene:

$$c(t) = \frac{5}{2}u(t) - 5e^{-t} + \frac{5}{2}e^{-2t}$$

#### Caso 2. Pares no repetidos de raíces complejas conjugadas

Como se recordará, si los coeficientes de un polinomio son números reales, sus raíces son números reales o pares de números conjugados complejos; en otras palabras, si $r_i$ es una raíz compleja de $D(s)$, entonces existe otra raíz compleja que es el conjugado de $r_i$, esto es, tiene las mismas partes real e imaginaria, pero de signo contrario. A fin de simplificar, se puede decir que estas dos raíces son $r_1$ y $r_2$:

$$r_1 = r + iw \qquad r_2 = r - iw$$

donde:
- $i = \sqrt{-1}$ es la unidad de los números imaginarios
- $r$ es la parte real de $r_1$ y $r_2$
- $w$ es la parte imaginaria de $r_1$

Por lo tanto, la expansión en fracciones parciales de $Y(s)$ es:

$$Y(s) = \frac{N(s)}{(s - r - iw)(s - r + iw)\ldots(s - r_k)}$$
$$= \frac{A_1}{s - r - iw} + \frac{A_2}{s - r + iw} + \ldots + \frac{A_k}{s - r_k} \quad (2-30)$$

Mediante el uso del álgebra de números complejos (ver sección 2-4), se puede aplicar la ecuación (2-27) para evaluar $A_1$ y $A_2$:

$$A_1 = \lim_{s \to r + iw}(s - r - iw)Y(s) \quad (2-31)$$

$$A_2 = \lim_{s \to r - iw}(s - r + iw)Y(s) \quad (2-32)$$

Se puede demostrar que $A_1$ y $A_2$ son un par de números complejos conjugados:

$$A_1 = B + iC \qquad A_2 = B - iC \quad (2-32)$$

donde $B$ y $C$ son la parte real e imaginaria de $A_1$, respectivamente.

Una vez que se determinó el valor de los coeficientes $A_1$ y $A_2$, se verá el inverso de estos términos; por el momento no se tomará en cuenta que son complejos. El inverso se obtiene mediante la aplicación de la ecuación (2-28):

$$\mathcal{L}^{-1}\left[\frac{A_1}{s - r - iw}\right] = A_1e^{(r+iw)t} = A_1e^{rt}e^{iwt}$$
$$= A_1e^{rt}(\cos wt + i\sin wt) \quad (2-33)$$

$$\mathcal{L}^{-1}\left[\frac{A_2}{s - r + iw}\right] = A_2e^{(r-iw)t} = A_2e^{rt}e^{-iwt} \quad (2-34)$$

Aquí se utilizó la identidad del exponencial de un número imaginario puro:

$$e^{ix} = \cos x + i\sin x \quad (2-35)$$

De la combinación de las ecuaciones (2-33) y (2-34) se obtiene:

$$\mathcal{L}^{-1}\left[\frac{A_1}{s - r - iw} + \frac{A_2}{s - r + iw}\right]$$
$$= e^{rt}[(A_1 + A_2)\cos wt + i(A_1 - A_2)\sin wt]$$
$$= e^{rt}(2B\cos wt - 2C\sin wt) \quad (2-36)$$

en donde se utilizó la ecuación (2-32). Nótese que con esto se demuestra que la solución $y(t)$ únicamente contiene coeficientes reales, ya que $B$ y $C$ son números reales. Una forma más simple de la ecuación (2-36) es:

$$\mathcal{L}^{-1}\left[\frac{A_1}{s - r - iw} + \frac{A_2}{s - r + iw}\right] = 2\sqrt{B^2 + C^2}e^{rt}\sin(wt - \theta) \quad (2-37)$$

donde:
$$\theta = \tan^{-1}\frac{C}{B}$$

Se puede demostrar que las ecuaciones (2-36) y (2-37) son equivalentes, mediante la substitución de las siguientes identidades trigonométricas:

$$\sin(wt - \theta) = \sin wt \cos \theta - \cos wt \sin \theta$$
$$B = \sqrt{B^2 + C^2}\cos \theta$$
$$C = \sqrt{B^2 + C^2}\sin \theta$$

Es importante señalar que el argumento de las funciones seno y coseno en las ecuaciones (2-36) y (2-37) está en radianes, no en grados, debido a que las unidades de $w$ son radianes por unidad de tiempo.

La parte real de las raíces complejas, $r$, aparece en el exponencial de tiempo $e^{rt}$ de la solución final; y la parte imaginaria, $w$, en el argumento de las funciones seno y coseno. Los dos factores complejos conjugados se pueden combinar en un solo factor "cuadrático" (de segundo orden) como sigue:

$$\frac{B + iC}{s - r - iw} + \frac{B - iC}{s - r + iw} = \frac{2B(s - r) - 2Cw}{s^2 - 2rs + r^2 + w^2}$$
$$= \frac{2B(s - r) - 2Cw}{(s - r)^2 + w^2} \quad (2-38)$$

Nótese que el denominador de este factor cuadrático es comparable a uno de los dos últimos de la tabla 2-1, por la igualación de $a = -r$. ¿Cómo se iguala el numerador?

**Ejemplo 2-7.** Dada la ecuación diferencial:

$$\frac{d^2c(t)}{dt^2} + 2\frac{dc(t)}{dt} + 5c(t) = 3u(t)$$

cuyas condiciones iniciales cero son:

$$c(0) = 0, \qquad \frac{dc}{dt}(0) = 0$$

encontrar, mediante el uso de la transformada de Laplace, la función $c(t)$ que satisface a la ecuación.

**Solución.**

**Paso 1.** La transformada de Laplace de la ecuación es:

$$s^2C(s) + 2sC(s) + 5C(s) = 3U(s)$$

**Paso 2.** Se resuelve para $C(s)$ y se substituye $U(s)$ de la tabla 2-1:

$$C(s) = \frac{3}{s^2 + 2s + 5}\cdot\frac{1}{s}$$

**Paso 3.** Se invierte $C(s)$.

Las raíces de $(s^2 + 2s + 5)s = 0$ son:

$$r_{1,2} = \frac{-2 \pm \sqrt{4 - 20}}{2} = -1 \pm i2$$
$$r_3 = 0$$

La expansión en fracciones parciales da:

$$C(s) = \frac{3}{(s+1-i2)(s+1+i2)s} = \frac{A_1}{s+1-i2} + \frac{A_2}{s+1+i2} + \frac{A_3}{s}$$

$$A_1 = \lim_{s \to -1+i2}(s+1-i2)\frac{3}{(s+1-i2)(s+1+i2)s} = \frac{3}{i4(-1+i2)}$$
$$= \frac{3(-2+i)}{4(-2-i)(-2+i)} = \frac{-6+3i}{20}$$

$$A_2 = \lim_{s \to -1-i2}(s+1+i2)\frac{3}{(s+1-i2)(s+1+i2)s} = \frac{3}{-i4(-1-i2)}$$
$$= \frac{-3(2+i)}{4(2-i)(2+i)} = \frac{-6-3i}{20}$$

$$A_3 = \lim_{s \to 0}s\frac{3}{(s+1-i2)(s+1+i2)s} = \frac{3}{5}$$

$$C(s) = \frac{(-6+3i)/20}{s+1-i2} + \frac{(-6-3i)/20}{s+1+i2} + \frac{3/5}{s}$$

Al invertir, con ayuda de las ecuaciones (2-36) y (2-37) y la tabla 2-1, se tiene:

$$c(t) = e^{-t}\left(\frac{-3}{5}\cos 2t - \frac{3}{10}\sin 2t\right) + \frac{3}{5}u(t) = \frac{3\sqrt{5}}{10}e^{-t}\sin(2t - 2.678) + \frac{3}{5}u(t)$$

con $r = -1$, $w = 2$, $B = -3/10$, $C = 3/20$, $\theta = 2.678$ radianes.

#### Caso 3. Raíces repetidas

La fórmula que se dio en los dos primeros casos no se puede utilizar para evaluar los coeficientes de las fracciones que contienen raíces repetidas. El procedimiento que se presenta aquí se aplica tanto para el caso donde las raíces repetidas son reales como para aquel en que son complejas.

La expansión en fracciones parciales de una transformada para la cual una raíz $r_1$ se repite $m$ veces está dada por:

$$Y(s) = \frac{N(s)}{(s - r_1)^m\ldots(s - r_k)}$$
$$= \frac{A_1}{(s - r_1)^m} + \frac{A_2}{(s - r_1)^{m-1}} + \ldots + \frac{A_m}{s - r_1} + \ldots + \frac{A_k}{s - r_k} \quad (2-39)$$

Para evaluar los coeficientes $A_1, A_2, \ldots, A_m$ se aplican en orden las siguientes fórmulas:

$$A_1 = \lim_{s \to r_1}[(s - r_1)^mY(s)]$$
$$A_2 = \lim_{s \to r_1}\frac{d}{ds}[(s - r_1)^mY(s)]$$
$$A_3 = \lim_{s \to r_1}\frac{1}{2!}\frac{d^2}{ds^2}[(s - r_1)^mY(s)] \quad (2-40)$$
$$\vdots$$
$$A_m = \lim_{s \to r_1}\frac{1}{(m-1)!}\frac{d^{m-1}}{ds^{m-1}}[(s - r_1)^mY(s)]$$

Una vez que se evalúan los coeficientes, la inversión de la ecuación (2-39) con el uso de la tabla 2-1 da como resultado lo siguiente:

$$y(t) = \left[\frac{A_1t^{m-1}}{(m-1)!} + \frac{A_2t^{m-2}}{(m-2)!} + \ldots + A_m\right]e^{r_1t} + \ldots + A_ke^{r_kt} \quad (2-41)$$

Para el raro caso de los pares repetidos de raíces complejas conjugadas se puede ahorrar trabajo si se considera que los coeficientes son pares de complejos conjugados. De la ecuación (2-32) se tiene:

$$A_1 = B_1 + iC_1 \qquad A_1^c = B_1 - iC_1$$

donde $A_1^c$ es el conjugado de $A_1$.

Por lo tanto, de la combinación de la ecuación (2-36) y (2-41) se puede escribir:

$$y(t) = e^{rt}\left\{\left[\frac{2B_1t^{m-1}}{(m-1)!} + \frac{2B_2t^{m-2}}{(m-2)!} + \ldots + 2B_m\right]\cos wt\right.$$
$$\left. - \left[\frac{2C_1t^{m-1}}{(m-1)!} + \frac{2C_2t^{m-2}}{(m-2)!} + \ldots + 2C_m\right]\sin wt\right\} + \ldots + A_ke^{r_kt}$$

**Ejemplo 2-8.** Dada la ecuación diferencial:

$$\frac{d^3c(t)}{dt^3} + 3\frac{d^2c(t)}{dt^2} + 3\frac{dc(t)}{dt} + c(t) = 2u(t)$$

con condiciones iniciales cero:

$$c(0) = 0; \quad \frac{dc}{dt}(0) = 0; \quad \frac{d^2c}{dt^2}(0) = 0$$

encontrar, mediante la aplicación del método de transformada de Laplace, la función $c(t)$ que satisface a la ecuación.

**Solución.**

**Paso 1.** Se transforma la ecuación:

$$s^3C(s) + 3s^2C(s) + 3sC(s) + C(s) = 2U(s)$$

**Paso 2.** Se resuelve para $C(s)$ y se substituye $U(s)$ de la tabla 2-1:

$$C(s) = \frac{2}{(s^3 + 3s^2 + 3s + 1)s}$$

**Paso 3.** Se invierte para obtener $c(t)$.

Las raíces son:
$$(s^3 + 3s^2 + 3s + 1)s = 0$$
$$r_{1,2,3} = -1, -1, -1$$
$$r_4 = 0$$

Se expande en fracciones parciales:

$$C(s) = \frac{2}{(s+1)^3s} = \frac{A_1}{(s+1)^3} + \frac{A_2}{(s+1)^2} + \frac{A_3}{s+1} + \frac{A_4}{s}$$

Se evalúan los coeficientes mediante el uso de la ecuación (2-40):

$$A_1 = \lim_{s \to -1}\left[(s+1)^3\frac{2}{(s+1)^3s}\right] = -2$$

$$A_2 = \lim_{s \to -1}\frac{d}{ds}\left[(s+1)^3\frac{2}{(s+1)^3s}\right] = \lim_{s \to -1}\frac{d}{ds}\left[\frac{2}{s}\right]$$
$$= \lim_{s \to -1}\left[-\frac{2}{s^2}\right] = -2$$

$$A_3 = \lim_{s \to -1}\frac{1}{2!}\frac{d^2}{ds^2}\left[(s+1)^3\frac{2}{(s+1)^3s}\right] = \lim_{s \to -1}\frac{1}{2}\frac{d}{ds}\left[-\frac{2}{s^2}\right]$$
$$= \lim_{s \to -1}\frac{1}{2}\left[\frac{4}{s^3}\right] = -2$$

$$A_4 = \lim_{s \to 0}s\frac{2}{(s+1)^3s} = 2$$

$$C(s) = -\frac{2}{(s+1)^3} - \frac{2}{(s+1)^2} - \frac{2}{s+1} + \frac{2}{s}$$

Al invertir, con ayuda de la ecuación (2-41) y de la tabla 2-1, se obtiene:

$$c(t) = -[t^2 + 2t + 2]e^{-t} + 2u(t)$$

Nótese que con el uso de la tabla 2-1 se puede obtener el mismo resultado mediante la inversión directa de cada término.

#### Caso 4. Tiempo muerto

El uso de la técnica de expansión en fracciones parciales se restringe a los casos en que la transformada de Laplace se puede expresar como una relación de dos polinomios. Como se vio en el teorema de traslación real, ecuación (2-9), cuando la transformada de Laplace contiene tiempo muerto (retardo de transporte o tiempo de retraso), en la función transformada aparece el término exponencial $e^{-st_0}$, donde $t_0$ es el tiempo muerto y, puesto que el exponencial es una función trascendental, el procedimiento de inversión se debe modificar de manera apropiada.

Si la función exponencial aparece en el denominador de la transformada de Laplace, no se puede hacer la inversión por expansión en fracciones parciales, porque ya no se tiene un número finito de raíces y, en consecuencia, habrá un número infinito de fracciones en la expansión. Por otro lado, los términos exponenciales en el numerador se pueden manejar, como se verá enseguida.

Considérese primeramente el caso en que la transformada de Laplace consta de un término exponencial que se multiplica por la relación de dos polinomios:

$$Y(s) = \left[\frac{N(s)}{D(s)}\right]e^{-st_0} = Y_1(s)e^{-st_0} \quad (2-43)$$

El procedimiento consiste en expandir en fracciones parciales únicamente la relación de los polinomios:

$$Y_1(s) = \frac{N(s)}{D(s)} = \frac{A_1}{s - r_1} + \frac{A_2}{s - r_2} + \ldots + \frac{A_k}{s - r_k} \quad (2-44)$$

Para esta expansión se requiere la aplicación de alguno de los tres primeros casos; a continuación se invierte la ecuación (2-44) para obtener:

$$y_1(t) = A_1e^{r_1t} + A_2e^{r_2t} + \ldots + A_ke^{r_kt}$$

Para invertir la ecuación (2-43) se hace uso del teorema de traslación real, ecuación (2-9):

$$Y(s) = e^{-st_0}Y_1(s) = \mathcal{L}[y_1(t - t_0)] \quad (2-45)$$

Al invertir esta ecuación resulta:

$$y(t) = \mathcal{L}^{-1}[Y(s)] = y_1(t - t_0)$$
$$= A_1e^{r_1(t-t_0)} + A_2e^{r_2(t-t_0)} + \ldots + A_ke^{r_k(t-t_0)} \quad (2-46)$$

Es importante subrayar el efecto de la eliminación del término exponencial del procedimiento de expansión en fracciones parciales; si se expande la función original, ecuación (2-43), se obtiene:

$$Y(s) = \frac{A_1e^{-r_1t_0}}{s - r_1} + \frac{A_2e^{-r_2t_0}}{s - r_2} + \ldots + \frac{A_ke^{-r_kt_0}}{s - r_k}$$

A pesar de que parece funcionar en ciertos casos, esto es fundamentalmente incómodo. A continuación se considera el caso de múltiples retardos, lo que introduce más de una función exponencial en el numerador de la transformada de Laplace, cuyo procedimiento implica manejar la función algebraicamente como una suma de términos, de manera que cada uno comprenda el producto de un exponencial por la relación de dos polinomios:

$$Y(s) = \left[\frac{N_1(s)}{D_1(s)}\right]e^{-st_{01}} + \left[\frac{N_2(s)}{D_2(s)}\right]e^{-st_{02}} + \ldots$$
$$= [Y_1(s)]e^{-st_{01}} + [Y_2(s)]e^{-st_{02}} + \ldots \quad (2-47)$$

Posteriormente se expande cada relación de polinomios en fracciones parciales y se invierte para obtener un resultado de la forma:

$$y(t) = y_1(t - t_{01}) + y_2(t - t_{02}) + \ldots \quad (2-48)$$

Los retardos múltiples pueden ocurrir cuando el sistema se sujeta a diferentes funciones de forzamiento, cada una con diferente período de retardo.

**Ejemplo 2-9.** Dada la ecuación diferencial:

$$\frac{dc(t)}{dt} + 2c(t) = f(t)$$

con $c(0) = 0$, encontrar la respuesta de salida para:

a) El cambio de un escalón unitario en $t = 1$: $f(t) = u(t-1)$
b) Una función secuencial de escalones unitarios que se repiten cada unidad de tiempo $f(t) = u(t-1) + u(t-2) + u(t-3) + \ldots$

Estas funciones se muestran en la figura 2-3.

**Solución.**

**Paso 1.** Se transforma la ecuación diferencial y la función de entrada:

$$sC(s) + 2C(s) = F(s)$$

Se utilizan el teorema de la traslación real y la tabla 2-1, de donde se obtiene:

(a) $F(s) = \mathcal{L}[u(t-1)] = \frac{e^{-s}}{s}$

(b) $F(s) = \mathcal{L}[u(t-1) + u(t-2) + u(t-3) + \ldots]$
$$= \frac{1}{s}(e^{-s} + e^{-2s} + e^{-3s} + \ldots)$$

**Paso 2.** Se resuelve para $C(s)$:

$$C(s) = \frac{1}{s+2}F(s)$$

**Paso 3.** Se invierte para obtener $c(t)$:

(a) $C(s) = \frac{1}{s+2}\cdot\frac{e^{-s}}{s} = C_1(s)e^{-s}$

$$C_1(s) = \frac{1}{(s+2)s} = \frac{A_1}{s+2} + \frac{A_2}{s}$$

$$A_1 = \lim_{s \to -2}(s+2)\frac{1}{(s+2)s} = \frac{1}{-2} = -\frac{1}{2}$$

$$A_2 = \lim_{s \to 0}s\frac{1}{(s+2)s} = \frac{1}{2}$$

$$C_1(s) = -\frac{1/2}{s+2} + \frac{1/2}{s}$$

Se invierte para obtener:

$$c_1(t) = -\frac{1}{2}e^{-2t} + \frac{1}{2}u(t)$$

Se aplica la ecuación (2-46):

$$c(t) = c_1(t-1) = \frac{1}{2}u(t-1)[1 - e^{-2(t-1)}]$$

Nótese que el escalón unitario $u(t-1)$ se debe multiplicar también por el término exponencial, para indicar que $c(t) = 0$ cuando $t < 1$.

(b) Para la función escalera se ve que:

$$C(s) = \left[\frac{1}{s+2}\cdot\frac{1}{s}\right](e^{-s} + e^{-2s} + e^{-3s} + \ldots)$$
$$= C_1(s)e^{-s} + C_1(s)e^{-2s} + C_1(s)e^{-3s} + \ldots$$

Es notorio que $C(s)$ es la misma de la parte (a) y, por tanto, el resultado de los pasos de expansión e inversión es el mismo. De la aplicación de la ecuación (2-46) a cada miembro resulta:

$$c(t) = c_1(t-1) + c_1(t-2) + c_1(t-3) + \ldots$$
$$= \frac{1}{2}u(t-1)[1 - e^{-2(t-1)}] + \frac{1}{2}u(t-2)[1 - e^{-2(t-2)}]$$
$$+ \frac{1}{2}u(t-3)[1 - e^{-2(t-3)}] + \ldots$$

Si ahora se desea evaluar la función en $t = 2.5$, la respuesta es:

$$c(2.5) = \frac{1}{2}(1)[1 - e^{-2(2.5-1)}] + \frac{1}{2}(1)[1 - e^{-2(2.5-2)}]$$
$$+ \frac{1}{2}(0)[1 - e^{-2(2.5-3)}] + \ldots$$
$$= \frac{1}{2}(0.950) + \frac{1}{2}(0.632) = 0.791$$

Nótese que, después de los dos primeros, todos los términos son cero.

En la tabla 2-2 se resumen los cuatro casos precedentes. Puesto que con todos estos casos se cubren esencialmente todas las posibilidades de solución de ecuaciones diferenciales lineales con coeficientes constantes, la correspondencia uno a uno en la tabla 2-2 hace innecesaria la inversión real de la transformada de Laplace de la variable dependiente, debido a que generalmente se pueden reconocer los términos de la función del tiempo $y(t)$ en la transformada de Laplace $Y(s)$.

```json
{
  "type": "table",
  "id": "table-02",
  "page": 58,
  "title": "Tabla 2-2. Relación entre la transformada de Laplace Y(s) y su inversa y(t)",
  "headers": ["Denominador de Y(s)", "Término de la fracción parcial", "Término de y(t)"],
  "rows": [
    ["1. Raíz real no repetida", "A/(s-r)", "A e^{rt}"],
    ["2. Par de raíces complejas conjugadas", "(B(s-r) + Cw)/((s-r)² + w²)", "e^{rt}(B cos wt + C sen wt)"],
    ["3. Raíz real que se repite m veces", "Σ A_j/(s-r)^j", "e^{rt} Σ A_j t^{j-1}/(j-1)!"],
    ["4. Término de tiempo muerto en el numerador de Y(s)", "Y₁(s)e^{-t₀s}", "y₁(t - t₀)"]
  ],
  "notes": "Resumen de los cuatro casos de expansión en fracciones parciales",
  "source": "Smith & Corripio, Control Automático de Procesos, Tabla 2-2"
}
```

### Eigenvalores y estabilidad

Al revisar la tabla 2-2 es evidente que las raíces del denominador de la transformada de Laplace $Y(s)$ determinan la respuesta $y(t)$; también se puede ver que, de la ecuación (2-20), algunas de las raíces del denominador de $Y(s)$ son las de la siguiente ecuación:

$$a_ns^n + a_{n-1}s^{n-1} + \ldots + a_1s + a_0 = 0 \quad (2-49)$$

donde $a_0, a_1, \ldots, a_n$ son los coeficientes de la variable dependiente y sus derivadas en la ecuación diferencial (2-17). El balance de las raíces del polinomio denominador provienen de la función de entrada o de forzamiento $X(s)$.

Se dice que la ecuación (2-49) es la **ecuación característica** de la ecuación diferencial y del sistema cuya respuesta dinámica representa. Sus raíces se conocen como **eigenvalores** (del alemán eigenvalues, que significa valores "característicos" o "propios") de la ecuación diferencial, y cuyo significado es que son, por definición, característicos de la ecuación diferencial e independientes de la función de forzamiento de entrada. En la tabla 2-2 se puede ver que los eigenvalores determinan si la respuesta en tiempo va a ser monótona (casos 1 y 3) u oscilatoria (caso 2), independientemente de que la función de forzamiento tenga o no tales características. Nótese que en el caso 2 las funciones seno y coseno causan la respuesta oscilatoria (ver figura 2-1). Los eigenvalores también determinan si la respuesta es estable o no es estable.

Se dice que una ecuación diferencial es estable cuando su respuesta en tiempo permanece limitada (finita) para una función de forzamiento limitante. En la tabla 2-2 se ve que para que se cumpla esta condición a fin de mantener la estabilidad, todos los eigenvalores deben tener partes reales $r$ negativas, debido a que el término $e^{rt}$ aparece en cada uno de los términos de la posible respuesta; y, para que este término exponencial permanezca finito conforme se incrementa el tiempo, $r$ debe ser negativa (en cada caso $r$ es, o bien la raíz real o la parte real de la raíz). La estabilidad se tratará con más detalle en el capítulo 6, cuando se estudie la respuesta de los sistemas de control por retroalimentación.

### Raíces de los polinomios

La operación que más tiempo requiere en la inversión es encontrar las raíces del polinomio denominador, $D(s)$, cuando éste es de tercer grado o superior, debido a que el procedimiento para encontrar las raíces es un procedimiento iterativo o de ensayo y error. Como el tiempo es valioso, es importante utilizar métodos eficientes para encontrar las raíces del polinomio; tres de los métodos más eficaces son:

1. Método de Newton para raíces reales.
2. Método de Newton-Bairstow para raíces reales y complejas conjugadas.
3. Método de Müller para raíces complejas y reales.

De éstos, el método de Newton es el más conveniente para el cálculo manual, especialmente cuando se combina con el de multiplicaciones anidadas para evaluar el polinomio y su derivada. Este método funciona mientras no existe más que un par de raíces complejas conjugadas. El método Newton-Bairstow se usa generalmente para encontrar factores cuadráticos (factores polinómicos de segundo grado) del polinomio con calculadoras programables. A partir de los coeficientes de cada factor cuadrático se pueden encontrar dos raíces, que pueden ser reales o un par de complejas conjugadas. El método de Müller es el más eficiente para encontrar las raíces, reales o complejas de cualquier función, sin embargo, el cálculo que implica es complicado, por lo que se debe usar la aritmética de números complejos para encontrar las raíces complejas. Por tal razón este método es recomendable cuando se usa una computadora para calcular las raíces. En el apéndice D se lista un programa en FORTRAN para encontrar las raíces de un polinomio mediante el método de Müller. El algoritmo para el método de Newton-Bairstow se describe en cualquier texto completo de métodos numéricos. Aquí se restringe la presentación al método de Newton.

El problema de encontrar las raíces de un polinomio se puede plantear como sigue: Dado el polinomio de grado $n$

$$f_n(s) = a_ns^n + a_{n-1}s^{n-1} + \ldots + a_1s + a_0 \quad (2-50)$$

encuéntrense todas sus raíces, esto es, todos los valores de $s$ que satisfacen la ecuación $f_n(s) = 0$.

Los tres pasos básicos que se requieren para resolver este problema por iteración de ensayo y error son los siguientes:

1. Se supone una aproximación inicial $s_0$ a la raíz.
2. Se calcula una mejor aproximación $s_k$.
3. Se verifica la convergencia dentro de una tolerancia de error especificado; si no está dentro de la tolerancia, se repiten los pasos 1 y 2 hasta que se alcanza la convergencia.

Después de que el procedimiento converge con el valor $r_1$, se toma este valor como la primera raíz y se determina el polinomio de grado $n-1$ mediante $f_{n-1}(s)$. Entonces se repite el procedimiento iterativo para $f_{n-1}(s)$ y se encuentra la segunda raíz $r_2$; después, para $f_{n-2}(s)$, a fin de encontrar $r_3$; y así, sucesivamente, hasta encontrar las $n$ raíces. El polinomio $f_{n-1}(s)$ se conoce como "polinomio reducido". La diferencia básica entre los diferentes métodos de iteración es la fórmula que se utiliza en el paso 2 del procedimiento de iteración para mejorar la aproximación a la raíz que se busca.

**Método de Newton.** La fórmula de iteración para el método de Newton está dada por:

$$s_{k+1} = s_k - \frac{f(s_k)}{f'(s_k)} \quad (2-52)$$

donde:
- $s_k$ es la aproximación previa a la raíz
- $s_{k+1}$ es la nueva aproximación
- $f(s_k)$ es el valor del polinomio en $s_k$
- $f'(s_k) = \frac{df}{ds}(s_k)$

Esta fórmula es muy eficaz en términos de la cantidad de iteraciones que se requieren para aproximar la raíz con una cierta tolerancia de error; sin embargo, se necesita evaluar el polinomio y su derivada en cada iteración, mientras que en otros métodos sólo se requiere evaluar la función a cada iteración (por ejemplo, secante, Müller). A pesar de todo, el método de Newton puede ser eficaz para polinomios cuando se utiliza el método de multiplicaciones anidadas para evaluar el polinomio y su derivada.

**Multiplicaciones anidadas.** Para evaluar el polinomio de grado $n$ de la ecuación (2-49) y su derivada en $s = s_k$, se utiliza el método de las multiplicaciones anidadas o división sintética, el cual consiste en el siguiente procedimiento; en el que $a_i$ son los coeficientes del polinomio y $b_i$ y $c_i$ son los dos conjuntos de variables que se usan para el cálculo:

1. Para $b_n = a_n$ y $c_n = b_n$.
2. Para $i = n-1, n-2, \ldots, 1, 0$, sea $b_i = a_i + b_{i+1}s_k$.
3. Para $i = n-1, n-2, \ldots, 1$, sea $c_i = b_i + c_{i+1}s_k$.

Entonces:
$$f(s_k) = b_0$$
$$f'(s_k) = c_1$$

Por lo tanto, los valores del polinomio y su derivada se calculan con sólo efectuar $2n-1$ multiplicaciones y sumas; en comparación, en la evaluación directa del polinomio y su derivada se requieren $n^2$ multiplicaciones y $2n-1$ sumas. Para un polinomio de quinto grado, con el método de multiplicaciones anidadas se requieren 9 multiplicaciones por iteración, en lugar de ¡25!

Además del significativo ahorro en cálculo, con el método de multiplicaciones anidadas se tiene la ventaja de que, cuando ya se ha encontrado la raíz, el polinomio reducido de grado $(n-1)$ está dado por:

$$f_{n-1}(s) = b_ns^{n-1} + b_{n-1}s^{n-2} + \ldots + b_1s + b_0 \quad (2-53)$$

Con esto se elimina la necesidad de hacer la división de la ecuación (2-51) después de encontrar cada raíz.

**Ejemplo 2-10.** Dada la ecuación diferencial:

$$\frac{d^3c(t)}{dt^3} + 2\frac{d^2c(t)}{dt^2} + 3\frac{dc(t)}{dt} + 4c(t) = 4\delta(t)$$

donde $\delta(t)$ es la función de impulso unitario en $t=0$; y, dado que todas las condiciones iniciales son cero:

$$c(0) = 0; \quad \frac{dc}{dt}(0) = 0; \quad \frac{d^2c}{dt^2}(0) = 0$$

encuéntrese la respuesta $c(t)$ mediante la transformada de Laplace.

**Solución.**

**Paso 1.** Se transforman la ecuación diferencial y la función de entrada:

$$s^3C(s) + 2s^2C(s) + 3sC(s) + 4C(s) = 4\mathcal{L}[\delta(t)]$$
$$\mathcal{L}[\delta(t)] = 1 \quad \text{(de la tabla 2-1)}$$

**Paso 2.** Se resuelve para $C(s)$:

$$C(s) = \frac{4}{s^3 + 2s^2 + 3s + 4}$$

Para factorizar el polinomio es necesario encontrar sus raíces:

$$f(s) = s^3 + 2s^2 + 3s + 4$$

**Procedimiento de iteración de Newton:**

Aproximación inicial $s_0 = -1$

**Iteración 1:**
$$s_0 = -1$$
$$s_1 = -1 - (2/2) = -2$$

**Iteración 2:**
$$s_1 = -2$$
$$s_2 = -2 - (-2/7) = -1.714$$

**Iteración 3:**
$$s_2 = -1.714$$
$$s_3 = -1.714 - (-0.303/4.958) = -1.653$$

**Iteración 4:**
$$s_3 = -1.653$$
$$s_4 = -1.653 - (-0.012/4.586) = -1.651$$

**Iteración 5:**
$$s_4 = -1.651$$

Puesto que la función del polinomio es cero, no hay necesidad de calcular la derivada después de la última iteración.

Por lo tanto, la primera raíz es $r_1 = -1.651$.

De la ecuación (2-53), se tiene que el polinomio reducido está dado por:

$$f_2(s) = s^2 + 0.349s + 2.423$$

Nótese que los coeficientes son las $b$ que se calculan en la iteración 5. Las raíces de este polinomio se pueden encontrar mediante el uso de la fórmula cuadrática:

$$r_{2,3} = \frac{-0.349 \pm \sqrt{0.1218 - 4(2.423)}}{2} = -0.174 \pm i1.547$$

Entonces:

$$C(s) = \frac{4}{(s+1.651)(s+0.174-i1.547)(s+0.174+i1.547)}$$
$$= \frac{A_1}{s+1.651} + \frac{A_2}{s+0.174-i1.547} + \frac{A_3}{s+0.174+i1.547}$$

$$A_1 = 0.875$$
$$A_2 = -0.437 - i0.417$$
$$A_3 = -0.437 + i0.417$$

$$C(s) = \frac{0.875}{s+1.651} + \frac{-0.437-i0.417}{s+0.174-i1.547} + \frac{-0.437+i0.417}{s+0.174+i1.547}$$

Al invertir se obtiene:

$$c(t) = 0.875e^{-1.651t} + e^{-0.174t}[-0.874\cos(1.547t) + 0.834\sin(1.547t)]$$

### Resumen del método de la transformada de Laplace para resolver ecuaciones diferenciales

El procedimiento para resolver ecuaciones diferenciales mediante la utilización de la transformada de Laplace y de la expansión de fracciones parciales se resume como sigue. Se tiene una ecuación diferencial de orden $n$, de la forma de la ecuación (2-17), con variable de salida $y(t)$ y variable de entrada $x(t)$.

**Paso 1.** Con la transformada de Laplace se convierte la ecuación, término a término, en una ecuación algebraica en $Y(s)$ y $X(s)$.

**Paso 2.** La transformada de Laplace de la variable de salida $Y(s)$ se resuelve algebraicamente y se substituye la transformada de la variable de entrada $X(s)$, para obtener una relación de dos polinomios:

$$Y(s) = \frac{N(s)}{D(s)} \quad (2-20)$$

**Paso 3.** Se invierte mediante la expansión en fracciones parciales, de la siguiente manera:

a) Se encuentran las raíces del denominador de $Y(s)$ mediante un método como el de Newton (subsección anterior) o un programa de computadora (apéndice D).

b) Se factoriza el denominador:

$$D(s) = (s - r_1)(s - r_2)\ldots(s - r_k) \quad (2-21)$$

c) Se expande la transformada en fracciones parciales:

$$Y(s) = \frac{A_1}{s - r_1} + \frac{A_2}{s - r_2} + \ldots + \frac{A_k}{s - r_k} \quad (2-24)$$

donde:
$$A_i = \lim_{s \to r_i}(s - r_i)\frac{N(s)}{D(s)} \quad (2-27)$$

si ninguna de las raíces, reales o complejas, se repite. Si existen raíces repetidas, entonces los coeficientes correspondientes se deben evaluar mediante el uso del sistema de fórmulas que constituye la ecuación (2-40).

d) Se invierte la ecuación (2-24) con ayuda de una tabla de transformadas de Laplace (tabla 2-1 o 2-2). Para raíces no repetidas la solución es de la forma:

$$y(t) = A_1e^{r_1t} + A_2e^{r_2t} + \ldots + A_ke^{r_kt} \quad (2-29)$$

Para el caso de raíces complejas conjugadas, la solución tiene la forma de las ecuaciones (2-36) o (2-37). En cuanto al caso de raíces repetidas, la solución tiene la forma de las ecuaciones (2-41) o (2-42).

Si existe tiempo muerto en el numerador, el procedimiento se altera como se indica en las ecuaciones (2-47) y (2-48).

Afortunadamente, cuando se diseñan sistemas de control se puede evitar la mayor parte de este procedimiento de inversión, porque, como se indica en la tabla 2-2, los términos del tiempo de respuesta se pueden reconocer en los términos del denominador de la transformada de Laplace; sin embargo, para usar la transformada de Laplace, las ecuaciones que representan los procesos y los instrumentos deben ser lineales, pero como generalmente éste no es el caso, a continuación se aborda dicho problema.

## 2-3. LINEALIZACIÓN Y VARIABLES DE DESVIACIÓN

Al analizar la respuesta dinámica de los procesos industriales, una de las mayores dificultades es el hecho de que no es lineal, es decir, no se puede representar mediante ecuaciones lineales. Para que una ecuación sea lineal, cada uno de sus términos no debe contener más de una variable o derivada y ésta debe estar a la primera potencia. Desafortunadamente, con la transformada de Laplace, poderosa herramienta que se estudió en la sección precedente, únicamente se pueden analizar sistemas lineales. Otra dificultad es que no existe una técnica conveniente para analizar un sistema no lineal, de tal manera que se pueda generalizar para una amplia variedad de sistemas físicos.

En esta sección se estudia la técnica de linealización, mediante la cual es posible aproximar las ecuaciones no lineales que representan un proceso a ecuaciones lineales que se pueden analizar mediante transformadas de Laplace. La suposición básica es que la respuesta de la aproximación lineal representa la respuesta del proceso en la región cercana al punto de operación, alrededor del cual se realiza la linealización.

El manejo de las ecuaciones linealizadas se facilita en gran medida con la utilización de las variables de desviación o perturbación, mismas que se definen a continuación.

### Variables de desviación

La variable de desviación se define como la diferencia entre el valor de la variable o señal y su valor en el punto de operación:

$$X(t) = x(t) - \bar{x} \quad (2-54)$$

donde:
- $X(t)$ es la variable de desviación
- $x(t)$ es la variable absoluta correspondiente
- $\bar{x}$ es el valor de $x$ en el punto de operación (valor base)

En otras palabras, la variable de desviación es la desviación de una variable respecto a su valor de operación o base. Como se ilustra en la figura 2-4, la transformación del valor absoluto de una variable al de desviación, equivale a mover el cero sobre el eje de esa variable hasta el valor base.

```json
{
  "type": "image",
  "id": "image-06",
  "page": 66,
  "title": "Figura 2-4. Definición de variable de desviación",
  "caption": "Definición gráfica de la variable de desviación",
  "description": "Gráfica que muestra una variable x(t) que oscila alrededor de un valor base x̄. La variable de desviación X(t) se define como la diferencia entre x(t) y x̄. Se muestran ambas variables en la misma gráfica.",
  "elements": [
    "Eje de tiempo t",
    "Eje de x",
    "Variable x(t)",
    "Valor base x̄",
    "Variable de desviación X(t)"
  ],
  "source": "Smith & Corripio, Control Automático de Procesos, Fig. 2-4"
}
```

Puesto que el valor base de la variable es una constante, las derivadas de las variables de desviación son siempre iguales a las derivadas correspondientes de las variables:

$$\frac{d^nX(t)}{dt^n} = \frac{d^nx(t)}{dt^n} \quad \text{para } n = 1, 2, \text{etc.} \quad (2-55)$$

La ventaja principal en la utilización de variables de desviación se deriva del hecho de que el valor base $\bar{x}$ es generalmente el valor inicial de la variable. Además, el punto de operación está generalmente en estado estacionario; es decir, las condiciones iniciales de las variables de desviación y sus derivadas son todas cero:

$$x(0) = \bar{x} \qquad X(0) = 0$$

También:
$$\frac{d^nX}{dt^n}(0) = 0 \quad \text{para } n = 1, 2, \text{etc.}$$

Entonces, para obtener la transformada de Laplace de cualquiera de las derivadas de las variables de desviación se aplica la ecuación (2-6):

$$\mathcal{L}\left[\frac{d^nX(t)}{dt^n}\right] = s^nX(s)$$

donde $X(s)$ es la transformada de Laplace de la variable de desviación.

Otra característica importante del caso en que todas las variables de desviación son desviaciones de las condiciones iniciales de estado estacionario, es que en las ecuaciones diferenciales linealizadas se excluyen los términos constantes. A continuación se demuestra esto brevemente.

### Linealización de funciones con una variable

Considérese la ecuación diferencial de primer orden:

$$\frac{dx(t)}{dt} = f[x(t)] + k \quad (2-56)$$

donde $f[x(t)]$ es una función no lineal de $x$, y $k$ es una constante. La expansión por series de Taylor de $f[x(t)]$, alrededor del valor $\bar{x}$, está dada por:

$$f[x(t)] = f(\bar{x}) + \frac{df}{dx}(\bar{x})[x(t) - \bar{x}] + \frac{1}{2!}\frac{d^2f}{dx^2}(\bar{x})[x(t) - \bar{x}]^2$$
$$+ \frac{1}{3!}\frac{d^3f}{dx^3}(\bar{x})[x(t) - \bar{x}]^3 + \ldots$$

La aproximación lineal consiste en eliminar todos los términos de la serie, con excepción de los dos primeros:

$$f[x(t)] \doteq f(\bar{x}) + \frac{df}{dx}(\bar{x})[x(t) - \bar{x}] \quad (2-58)$$

y, al substituir la definición de variable de desviación $X(t)$ de la ecuación (2-54):

$$f[x(t)] \doteq f(\bar{x}) + \frac{df}{dx}(\bar{x})X(t) \quad (2-59)$$

En la figura 2-5 se da la interpretación gráfica de esta aproximación. La aproximación lineal es una línea recta que pasa por el punto $\bar{x}, f(\bar{x})$, con pendiente $df/dx(\bar{x})$; esta línea es, por definición, tangente a la curva $f(x)$ en $\bar{x}$. Nótese que la diferencia entre la aproximación lineal y la función real es menor en las cercanías del punto de operación $\bar{x}$, y mayor cuando se aleja de éste. Es difícil definir la región en que la aproximación lineal es lo suficientemente precisa como para representar la función no lineal; tanto más alineal es una función cuanto menor es la región sobre la que la aproximación lineal es precisa.

De la substitución de la ecuación (2-59) de aproximación lineal en la ecuación (2-56) resulta:

$$\frac{dx(t)}{dt} = f(\bar{x}) + \frac{df}{dx}(\bar{x})X(t) + k \quad (2-60)$$

Si las condiciones iniciales son:
$$x(0) = \bar{x} \qquad \frac{dx}{dt}(0) = 0 \qquad X(0) = 0$$

entonces:
$$0 = f(\bar{x}) + \frac{df}{dx}(\bar{x})(0) + k$$
$$f(\bar{x}) + k = 0$$

Al substituir en la ecuación (2-60), se tiene:

$$\frac{dX(t)}{dt} = \frac{df}{dx}(\bar{x})X(t) \quad (2-61)$$

Con esto se demuestra cómo se eliminan los términos constantes de la ecuación linealizada cuando el valor base es la condición inicial de estado estacionario. Nótese que es posible omitir todos los pasos intermedios y llegar directamente de la ecuación (2-56) a la ecuación (2-61).

Los siguientes son ejemplos de algunas funciones no lineales más usuales en los modelos de proceso:

1. Dependencia de Arrhenius de la tasa de reacción de la temperatura:
$$k(T) = k_0e^{-(E/RT)}$$
donde $k_0$, $E$ y $R$ son constantes.

2. Presión de vapor de una substancia pura (ecuación de Antoine):
$$p^0(T) = e^{(A - B/(T+C))}$$
donde $A$, $B$ y $C$ son constantes.

3. Equilibrio vapor-líquido por volatilidad relativa:
$$y(x) = \frac{\alpha x}{1 + (\alpha - 1)x}$$
donde $\alpha$ es una constante.

4. Caída de presión a través de accesorios y tuberías:
$$\Delta P(F) = kF^2$$
donde $k$ es una constante.

5. Razón de transferencia de calor por radiación:
$$q(T) = \epsilon\sigma AT^4$$
donde $\epsilon$, $\sigma$ y $A$ son constantes.

6. Entalpía como función de la temperatura:
$$H(T) = H_0 + AT + BT^2 + CT^3 + DT^4$$
donde $H_0, A, B, C$ y $D$ son constantes.

**Ejemplo 2-11.** Linealizar la ecuación de Arrhenius para la dependencia de las tasas de reacción química de la temperatura:

$$k(T) = k_0e^{-(E/RT)}$$

donde $k_0$, $E$ y $R$ son constantes.

**Solución.** De la ecuación (2-58) se tiene:

$$k(T) = k(\bar{T}) + \frac{dk}{dT}(\bar{T})(T - \bar{T})$$

$$\frac{dk}{dT}(\bar{T}) = k_0e^{-(E/R\bar{T})}\left(\frac{E}{R\bar{T}^2}\right) = k(\bar{T})\frac{E}{R\bar{T}^2}$$

Se substituye para obtener:

$$k(T) \doteq k(\bar{T}) + k(\bar{T})\frac{E}{R\bar{T}^2}(T - \bar{T})$$

En términos de las variables de desviación se ve que:

$$K(T) \doteq \left[k(\bar{T})\frac{E}{R\bar{T}^2}\right]T$$

donde $K(T) = k(T) - k(\bar{T})$ y $T = T - \bar{T}$.

Para mostrar que las únicas variables en la ecuación lineal son $K$ y $T$, considérese el siguiente problema numérico:

$$k_0 = 8 \times 10^9 \, s^{-1}$$
$$E = 22000 \, \text{cal/g mol}$$
$$\bar{T} = 373 \, K \text{ (100°C)}$$
$$R = 1.987 \, \text{cal/g mol K}$$

$$k(\bar{T}) = 8 \times 10^9 e^{-[22000/(1.987)(373)]} = 1.0273 \times 10^{-3} \, s^{-1}$$

$$\frac{dk}{dT}(\bar{T}) = (1.0273 \times 10^{-3})\frac{22000}{(1.987)(373)^2}$$
$$= 8.175 \times 10^{-5} \, s^{-1}K^{-1}$$

Esto da como resultado las siguientes ecuaciones lineales:

$$k(T) = 1.0273 \times 10^{-3} + 8.175 \times 10^{-5}(T - 373)$$
$$K(T) = 8.175 \times 10^{-5}T$$

### Linealización de funciones con dos o más variables

Considérese la función no lineal de dos variables $f[x(t), y(t)]$; la expansión por series de Taylor alrededor de un punto $(\bar{x}, \bar{y})$ está dada por:

$$f[x(t), y(t)] = f(\bar{x}, \bar{y}) + \frac{\partial f}{\partial x}(\bar{x}, \bar{y})[x(t) - \bar{x}]$$
$$+ \frac{\partial f}{\partial y}(\bar{x}, \bar{y})[y(t) - \bar{y}] + \frac{1}{2!}\frac{\partial^2 f}{\partial x^2}(\bar{x}, \bar{y})[x(t) - \bar{x}]^2$$
$$+ \frac{1}{2!}\frac{\partial^2 f}{\partial y^2}(\bar{x}, \bar{y})[y(t) - \bar{y}]^2$$
$$+ \frac{\partial^2 f}{\partial x\partial y}(\bar{x}, \bar{y})[x(t) - \bar{x}][y(t) - \bar{y}] + \ldots \quad (2-62)$$

La aproximación lineal consiste en eliminar los términos de segundo orden o superior, para obtener:

$$f[x(t), y(t)] = f(\bar{x}, \bar{y}) + \frac{\partial f}{\partial x}(\bar{x}, \bar{y})[x(t) - \bar{x}] + \frac{\partial f}{\partial y}(\bar{x}, \bar{y})[y(t) - \bar{y}] \quad (2-63)$$

El error de esta aproximación lineal es pequeño para $x$ y $y$ en la vecindad de $\bar{x}$ y $\bar{y}$. Para ilustrar esto gráficamente, se utilizará un ejemplo; considérese el área de un rectángulo en función de sus lados $h$ y $w$:

$$a(h, w) = hw$$

Las derivadas parciales son:
$$\frac{\partial a}{\partial h} = w \qquad \frac{\partial a}{\partial w} = h$$

La aproximación lineal está dada por:

$$a(h, w) \doteq a(\bar{h}, \bar{w}) + \bar{w}(h - \bar{h}) + \bar{h}(w - \bar{w})$$

Como se muestra gráficamente en la figura 2-6, el error de esta aproximación es un pequeño rectángulo de área $(h - \bar{h})(w - \bar{w})$; tal error es pequeño cuando $h$ y $w$ están cerca de $\bar{h}$ y $\bar{w}$. En términos de las variables de desviación:

$$A(h, w) \doteq \bar{w}H + \bar{h}W$$

donde $A(h, w) = a(h, w) - a(\bar{h}, \bar{w})$.

En general, una función con $n$ variables $x_1, x_2, \ldots, x_n$, se linealiza mediante la fórmula:

$$f(x_1, x_2, \ldots, x_n) \doteq f(\bar{x}_1, \bar{x}_2, \ldots, \bar{x}_n) + \frac{\partial f}{\partial x_1}(x_1 - \bar{x}_1)$$
$$+ \frac{\partial f}{\partial x_2}(x_2 - \bar{x}_2) + \ldots + \frac{\partial f}{\partial x_n}(x_n - \bar{x}_n) \quad (2-64)$$
$$= f(\bar{x}_1, \bar{x}_2, \ldots, \bar{x}_n) + \sum_{k=1}^n \frac{\partial f}{\partial x_k}(x_k - \bar{x}_k)$$

donde:
$$\frac{\partial f}{\partial x_k}$$

designa las derivadas parciales que se evalúan en $(\bar{x}_1, \bar{x}_2, \ldots, \bar{x}_n)$.

**Ejemplo 2-12.** Encuéntrese la aproximación lineal de la función no lineal:

$$f(x, y, z) = 2x^2 + xy^2 - 3\frac{y}{z}$$

en el punto $\bar{x} = 1$, $\bar{y} = 2$, $\bar{z} = 3$.

**Solución.** En la ecuación (2-64) la aproximación lineal está dada por:

$$f(x, y, z) = f(\bar{x}, \bar{y}, \bar{z}) + \frac{\partial f}{\partial x}(x - \bar{x}) + \frac{\partial f}{\partial y}(y - \bar{y}) + \frac{\partial f}{\partial z}(z - \bar{z})$$

Si se toman las derivadas parciales de la función indicadas, se tiene:

$$\frac{\partial f}{\partial x} = 4x + y^2$$
$$\frac{\partial f}{\partial y} = 2xy - \frac{3}{z}$$
$$\frac{\partial f}{\partial z} = \frac{3y}{z^2}$$

Si se evalúa la función y sus derivadas parciales en el punto base resulta:

$$\bar{f} = 2(1)^2 + 1(2)^2 - 3\frac{2}{3} = 4$$
$$\overline{\frac{\partial f}{\partial x}} = 4(1) + (2)^2 = 8$$
$$\overline{\frac{\partial f}{\partial y}} = 2(1)(2) - \frac{3}{3} = 3$$
$$\overline{\frac{\partial f}{\partial z}} = \frac{3(2)}{(3)^2} = \frac{2}{3}$$

Al substituir estos valores, la función linealizada queda dada por:

$$f(x, y, z) \doteq 4 + 8(x - 1) + 3(y - 2) + \frac{2}{3}(z - 3)$$

o, en términos de las variables de desviación $F$, $X$, $Y$ y $Z$:

$$F \doteq 8X + 3Y + \frac{2}{3}Z$$

**Ejemplo 2-13.** La densidad de un gas ideal se expresa mediante la siguiente fórmula:

$$\rho = \frac{Mp}{RT}$$

donde $M$ es el peso molecular y $R$ la constante de los gases perfectos.

Encuéntrese la aproximación lineal de la densidad como función de $T$ y $p$ y evalúense los coeficientes para aire ($M = 29$) a $300K$ y presión atmosférica ($101,300 \, N/m^2$). En unidades del SI la constante de los gases perfectos es $R = 8.314 \, N-m/kg mol-K$.

**Solución.** A partir de la ecuación (2-64), la aproximación lineal se da por:

$$\rho = \bar{\rho} + \overline{\frac{\partial \rho}{\partial T}}(T - \bar{T}) + \overline{\frac{\partial \rho}{\partial p}}(p - \bar{p})$$

Las derivadas parciales de la función densidad son:

$$\frac{\partial \rho}{\partial T} = -\frac{Mp}{RT^2} = -\frac{\rho}{T}$$
$$\frac{\partial \rho}{\partial p} = \frac{M}{RT} = \frac{\rho}{p}$$

Al evaluar en las condiciones de base se obtiene:

$$\bar{\rho} = \frac{M\bar{p}}{R\bar{T}} = \frac{(29)(101300)}{(8314)(300)} = 1.178 \, kg/m^3$$

$$\overline{\frac{\partial \rho}{\partial T}} = -\frac{\bar{\rho}}{\bar{T}} = -\frac{1.178}{300} = -0.00393 \, kg/m^3K$$

$$\overline{\frac{\partial \rho}{\partial p}} = \frac{\bar{\rho}}{\bar{p}} = \frac{1.178}{101300} = 1.163 \times 10^{-5} \, kg/m-N$$

Por substitución, se obtiene la función linealizada:

$$\rho \doteq 1.178 - 0.00393(T - \bar{T}) + 1.163 \times 10^{-5}(p - \bar{p})$$

o, en términos de las variables de desviación $R$, $T$, $P$:

$$R \doteq -0.00393T + 1.163 \times 10^{-5}P$$

**Ejemplo 2-14.** La respuesta de la composición del reactivo A en un tanque de reacción con agitación continua (ver figura 2-7) se puede calcular mediante las siguientes ecuaciones:

$$V\frac{dc_A(t)}{dt} = f(t)[c_{A_i}(t) - c_A(t)] - Vk[T(t)]c_A(t)$$
$$k[T(t)] = k_0e^{-[E/RT(t)]}$$

donde $k_0$, $V$, $E$ y $R$ son constantes. Para derivar estas ecuaciones se supone que el reactor es adiabático y de volumen constante, y que el calor de reacción es despreciable.

Las ecuaciones linealizadas se deben anotar en términos de las variables de desviación, alrededor de las condiciones iniciales de estado estacionario y de las variables de la transformada de Laplace.

**Solución.** De la linealización de cada miembro de la ecuación resulta:

$$f(t)[c_{A_i}(t) - c_A(t)] \doteq \bar{f}(\bar{c}_{A_i} - \bar{c}_A) + \bar{f}[C_{A_i}(t) - C_A(t)] + [\bar{c}_{A_i} - \bar{c}_A]F(t)$$

$$Vk[T(t)]c_A(t) \doteq Vk(\bar{T})\bar{c}_A + V\frac{dk}{dT}(\bar{T})\bar{c}_A T(t) + Vk(\bar{T})C_A(t)$$

Al substituir el resultado del ejemplo 2-11, se obtiene:

$$Vk[T(t)]c_A(t) \doteq Vk(\bar{T})\bar{c}_A + Vk(\bar{T})\frac{E}{R\bar{T}^2}\bar{c}_A T(t) + Vk(\bar{T})C_A(t)$$

Puesto que los valores base representan un estado estacionario, se ve que:

$$0 = \bar{f}(\bar{c}_{A_i} - \bar{c}_A) - Vk(\bar{T})\bar{c}_A$$

Si ahora se substituyen estas dos últimas ecuaciones en la ecuación diferencial original, se obtiene:

$$V\frac{dC_A(t)}{dt} \doteq \bar{f}C_{A_i}(t) + (\bar{c}_{A_i} - \bar{c}_A)F(t) - [\bar{f} + Vk(\bar{T})]C_A(t) - Vk(\bar{T})\frac{E}{R\bar{T}^2}\bar{c}_A T(t)$$

Se aprovecha la ventaja de que los valores base son los iniciales (es decir, $C_A(0) = 0$) y entonces se puede obtener la transformada de Laplace de la ecuación linealizada:

$$VsC_A(s) = \bar{f}C_{A_i}(s) + (\bar{c}_{A_i} - \bar{c}_A)F(s) - [\bar{f} + Vk(\bar{T})]C_A(s) - Vk(\bar{T})\frac{E}{R\bar{T}^2}\bar{c}_A T(s)$$

Al reordenar, se tiene:

$$C_A(s) = \frac{K_A}{\tau s + 1}C_{A_i}(s) + \frac{K_F}{\tau s + 1}F(s) - \frac{K_T}{\tau s + 1}T(s)$$

en donde los parámetros constantes son:

$$K_A = \frac{\bar{f}}{\bar{f} + Vk(\bar{T})}$$
$$K_F = \frac{\bar{c}_{A_i} - \bar{c}_A}{\bar{f} + Vk(\bar{T})}$$
$$K_T = \frac{k(\bar{T})E\bar{c}_A}{R\bar{T}^2[\bar{f} + Vk(\bar{T})]}$$
$$\tau = \frac{V}{\bar{f} + Vk(\bar{T})}$$

Con el resultado de este último ejemplo se prueba que los parámetros de la ecuación linealizada dependen de los valores base de las variables del sistema. Se deduce que, para un sistema no lineal, la respuesta dinámica será diferente en diferentes condiciones de operación; este punto se abordará con mayor detalle en los capítulos 3 y 4.

## 2-4. REPASO DEL ÁLGEBRA DE NÚMEROS COMPLEJOS

En las secciones precedentes se aprendió que la linealización y la transformada de Laplace son herramientas poderosas para establecer las relaciones generales entre las variables y señales que constituyen los sistemas de control de proceso; desafortunadamente, el manejo de la transformada de Laplace requiere familiaridad con el álgebra de números complejos. En esta sección se resumen algunas de las operaciones fundamentales con números complejos, con la finalidad de proporcionar una referencia rápida a los lectores que pudieran tener dificultades en el manejo de números complejos.

### Números complejos

Se dice que un número es complejo cuando no se puede representar como un número real puro o un número imaginario puro; un número imaginario es aquel que contiene la raíz cuadrada de la unidad negativa ($i = \sqrt{-1}$). Una manera de representar un número complejo es la siguiente:

$$c = a + ib \quad (2-65)$$

donde:
- $a$ es la parte real del número complejo
- $b$ es la parte imaginaria

Un número complejo se puede representar gráficamente en un plano en el que la parte imaginaria se sitúa en el eje vertical o imaginario; y la parte real, en el eje horizontal o real. Este plano se conoce como plano complejo y se ilustra mediante la figura 2-8; cada punto en dicho plano representa un número real, si está sobre el eje real; imaginario, si está sobre el eje imaginario; o complejo, si está en cualquier otro lugar.

Una manera alterna para representar un número complejo es la notación polar. Como se observa en la figura 2-8, la distancia del punto $(a, b)$ al origen está dada por:

$$r = \sqrt{a^2 + b^2} = |c| \quad (2-66)$$

Esto se conoce como magnitud del número complejo $c$ que aparece en la ecuación (2-65). La otra parte que se requiere para representar el número $c$ en notación polar es el ángulo $\theta$ (ver figura 2-8), el cual está dado por:

$$\theta = \tan^{-1}\frac{b}{a} = \angle c \quad (2-67)$$

Este es el ángulo formado por la línea que va del origen al punto $(a, b)$ y la parte positiva del eje real; se conoce como argumento del número complejo. Las ecuaciones (2-66) y (2-67) se utilizan para convertir un número complejo, de la forma cartesiana $(a, b)$ a la forma polar $(r, \theta)$. La operación inversa se puede efectuar mediante la utilización de las siguientes ecuaciones, las cuales se pueden comprobar fácilmente mediante la observación de la figura 2-8:

$$a = r\cos \theta \quad (2-68)$$
$$b = r\sin \theta \quad (2-69)$$

Si se substituyen las ecuaciones (2-68) y (2-69) en la ecuación (2-65) y se factoriza la magnitud $r$, se obtiene:

$$c = r(\cos \theta + i\sin \theta) = re^{i\theta} \quad (2-70)$$

aquí se hizo uso de la identidad trigonométrica:

$$e^{i\theta} = \cos \theta + i\sin \theta \quad (2-71)$$

La ecuación (2-70) es la forma polar del número complejo $c$.

### Operaciones con números complejos

Dados dos números complejos:

$$c = a + ib$$
$$p = v + iw$$

La suma se expresa mediante:
$$c + p = (a + v) + i(b + w) \quad (2-72)$$

La resta es:
$$c - p = (a - v) + i(b - w) \quad (2-73)$$

La multiplicación está dada por:
$$cp = (a + ib)(v + iw)$$
$$= av + i^2bw + ibv + iaw$$
$$= (av - bw) + i(bv + aw) \quad (2-74)$$

donde se substituyó $i^2 = -1$.

En consecuencia, para la suma, la resta y la multiplicación de números complejos se siguen las mismas reglas del álgebra general; lo mismo sucede en cuanto a la división, con la excepción de que, para despejar el denominador, se debe usar el conjugado.

El conjugado de un número complejo se define como un número que tiene una parte real y una parte imaginaria de igual magnitud, pero de signo contrario, en otras palabras:

$$\text{conj.}(a + ib) = a - ib \quad (2-75)$$

El producto de un número complejo por su conjugado es un número real que se expresa mediante:

$$(a + ib)(a - ib) = a^2 + b^2 \quad (2-76)$$

Con esto, la división de números complejos se realiza mediante la multiplicación del numerador y el denominador, por el conjugado del denominador:

$$\frac{c}{p} = \frac{a + ib}{v + iw} = \frac{(a + ib)(v - iw)}{(v + iw)(v - iw)}$$
$$= \frac{(av + bw) + i(bv - aw)}{v^2 + w^2}$$
$$= \frac{av + bw}{v^2 + w^2} + i\left(\frac{bv - aw}{v^2 + w^2}\right) \quad (2-77)$$

La multiplicación y la división se pueden realizar con mayor facilidad con la notación polar. Sean $c$ y $p$ que se expresan mediante:

$$c = re^{i\theta}$$
$$p = qe^{i\beta}$$

Entonces el producto se expresa mediante:
$$cp = rq e^{i(\theta + \beta)} \quad (2-78)$$

y el cociente por:
$$\frac{c}{p} = \frac{r}{q}e^{i(\theta - \beta)} \quad (2-79)$$

La elevación a una potencia también es más simple en la notación polar:
$$c^n = r^n e^{in\theta} \quad (2-80)$$

así como la extracción de la raíz enésima. Un número tiene $n$ raíces enésimas cuando se toman en cuenta sus raíces reales y complejas:

$$\sqrt[n]{c} = \sqrt[n]{r}e^{i(\theta + 2k\pi)/n} \qquad k = 0, \pm 1, \pm 2, \ldots \quad (2-81)$$

donde se cambia el valor de $k$ hasta que se calculan $n$ raíces diferentes.

Las anteriores constituyen las operaciones fundamentales del álgebra de números complejos. Es importante tener en mente que, con el FORTRAN y otros lenguajes de programación de computadora, se pueden realizar operaciones y calcular funciones que contienen números complejos.

**Ejemplo 2-15.** Dados los números:

$$a = 3 + i4 \qquad b = 8 - i6 \qquad c = -1 + i$$

a) Conviértanse a la forma polar:

$$|a| = \sqrt{9 + 16} = 5 \qquad |b| = \sqrt{64 + 36} = 10 \qquad |c| = \sqrt{1 + 1} = \sqrt{2}$$

$$\angle a = \tan^{-1}\frac{4}{3} = 0.9273 \qquad \angle b = \tan^{-1}\frac{-6}{8} = -0.6435 \qquad \angle c = \tan^{-1}\frac{1}{-1} = \frac{3\pi}{4}$$

$$a = 5e^{i0.9273} \qquad b = 10e^{-i0.6435} \qquad c = \sqrt{2}e^{i(3\pi/4)}$$

Nótese que $b$ está en el cuarto cuadrante y $c$ en el segundo del plano complejo (ver figura 2-9). Obsérvese también que los ángulos están en radianes.

b) Los siguientes son ejemplos de operaciones con números complejos:

$$ac = (-3 - 4) + i(3 - 4) = -7 - i$$
$$bc = (-8 + 6) + i(8 + 6) = -2 + i14$$

Con lo siguiente se ilustra la propiedad distributiva de la multiplicación:

$$(a + b)c = (11 - i2)(-1 + i) = (-11 + 2) + i(11 + 2) = -9 + i13$$
$$ac + bc = (-7 - i) + (-2 + i14) = -9 + i13$$

A continuación se ejemplifica la división:

$$\frac{a}{b} = \frac{3 + i4}{8 - i6}\cdot\frac{8 + i6}{8 + i6} = \frac{(24 - 24) + i(18 + 32)}{64 + 36} = i0.50$$

En notación polar:

$$ac = 5e^{i0.9273}\sqrt{2}e^{i(3\pi/4)} = 5\sqrt{2}e^{i3.2834}$$
$$= 5\sqrt{2}\cos 3.2834 + i5\sqrt{2}\sin 3.2834 = -7 - i$$

$$\frac{a}{b} = \frac{5e^{i0.9273}}{10e^{-i0.6435}} = 0.50e^{i1.5708}$$
$$= 0.50\cos 1.5708 + i0.50\sin 1.5708 = i0.50$$

Estos resultados coinciden con los que se obtuvieron anteriormente.

c) Encuéntrense las cuatro raíces de 16, en coordenadas polares:

$$16 = 16e^{i0}$$
$$x = \sqrt[4]{16}e^{i0} = \sqrt[4]{16}e^{i(0 + 2k\pi)/4} = 2e^{i(2k\pi/4)}$$

Las raíces son:

$$k = 0: \quad x_1 = 2e^{i0} = 2$$
$$k = 1: \quad x_2 = 2e^{i\pi/2} = 2i$$
$$k = 2: \quad x_3 = 2e^{i\pi} = -2$$
$$k = 3: \quad x_4 = 2e^{i3\pi/2} = -2i$$

Estas raíces se grafican en la figura 2-9.

## 2-5. RESUMEN

En este capítulo se estudiaron las técnicas de transformada de Laplace y linealización; la combinación de estas herramientas permite representar la respuesta dinámica de los procesos y los instrumentos mediante sistemas de ecuaciones algebraicas en la variable de la transformada de Laplace, $s$. Esto conduce, como se verá en el capítulo siguiente, al concepto de función de transferencia, que es una herramienta fundamental en el análisis y diseño de sistemas de control.

Los puntos más importantes que se cubrieron en este capítulo son:

1. La transformada de Laplace convierte ecuaciones diferenciales lineales en ecuaciones algebraicas.
2. Las propiedades de la transformada de Laplace (linealidad, diferenciación real, integración real, traslación real, traslación compleja, valor inicial y valor final) permiten simplificar el análisis.
3. La inversión de la transformada de Laplace se realiza mediante expansión en fracciones parciales, considerando cuatro casos: raíces reales no repetidas, pares complejos conjugados, raíces repetidas y tiempo muerto.
4. Los eigenvalores (raíces de la ecuación característica) determinan la estabilidad y la naturaleza de la respuesta del sistema.
5. La linealización permite aproximar ecuaciones no lineales mediante expansiones de series de Taylor truncadas.
6. Las variables de desviación simplifican el análisis al eliminar los términos constantes de las ecuaciones linealizadas.
7. El álgebra de números complejos es esencial para el manejo de la transformada de Laplace.

La combinación de estas técnicas permite obtener funciones de transferencia que describen completamente el comportamiento dinámico de procesos e instrumentos, lo cual es el tema del siguiente capítulo.

## BIBLIOGRAFÍA

1. Müller, D. E., "A Method for Solving Algebraic Equations Using an Automatic Computer," *Mathematical Tables and Other Aids to Computation*, Vol. 10, 1956, pp. 208-215.
2. Ketter, R. L., y S. P. Prawel, Jr., *Modern Methods of Engineering Computation*, McGraw-Hill, Nueva York, 1969.
3. Conte, Samuel D., y Carl de Boor, *Elementary Numerical Analysis*, 3a. ed., McGraw-Hill, Nueva York, 1980.
4. D'Azzo, John J., y C. H. Houpis, *Feedback Control System Analysis and Synthesis*, 2a. ed., McGraw-Hill, Nueva York, 1966, capítulo 4.
5. Murrill, Paul W., *Automatic Control of Processes*, Intext, Scranton, Pa., 1967, capítulos 4, 5 y 9.
6. Luyben, William L., *Process Modeling, Simulation, and Control for Chemical Engineers*, McGraw-Hill, Nueva York, 1973, capítulos 6 y 7.

## PROBLEMAS

**2-1.** A partir de la definición de transformada de Laplace, obténgase la transformada F(s) de las siguientes funciones:

a) $f(t) = t$
b) $f(t) = e^{-at}$; donde $a$ es constante.
c) $f(t) = \cos \omega t$, donde $\omega$ es constante.
d) $f(t) = e^{-at}\cos \omega t$; donde $a$ y $\omega$ son constantes.

Nota: Para las partes (c) y (d) posiblemente se requiera la identidad trigonométrica:
$$\cos x = \frac{e^{ix} + e^{-ix}}{2}$$

La respuesta se puede verificar con el contenido de la tabla 2-1.

**2-2.** Con el auxilio de una tabla de transformadas de Laplace y las propiedades de la transformada, encuéntrese la transformada F(s) de las siguientes funciones:

a) $f(t) = u(t) + 2t + 3t^2$
b) $f(t) = e^{-2t}[u(t) + 2t + 3t^2]$
c) $f(t) = u(t) + e^{-2t} - 2e^{-t}$
d) $f(t) = u(t) - e^{-t} + te^{-t}$
e) $f(t) = u(t-2)[1 - e^{-2(t-2)}\sin(t-2)]$

**2-3.** Verifique la validez de los resultados del problema 2-2 mediante el uso de los teoremas del valor inicial y del valor final. ¿Estos teoremas se aplican en todos los casos?

**2-4.** Una función útil que se emplea como función de forzamiento en el análisis de los sistemas de control de proceso es la rampa parcial que se ilustra en la figura 2-10. Obténgase la transformada de Laplace de la función rampa parcial, mediante cada uno de los siguientes métodos:

a) La aplicación directa de la definición de transformada de Laplace; se consideran las siguientes secciones de la función:

$$f(t) = \begin{cases} \frac{H}{t_1}t & 0 \leq t \leq t_1 \\ H & t \geq t_1 \end{cases}$$

donde $H$ es la altura y $t_1$ la duración de la rampa.

b) El uso de una tabla de transformadas de Laplace, la propiedad de linealidad y el teorema de la traslación real; la función se considera como la suma o superposición de las siguientes funciones:

$$f(t) = \frac{H}{t_1}t - u(t-t_1)\frac{H}{t_1}t + Hu(t-t_1)$$

Verifique el resultado mediante la aplicación de los teoremas del valor inicial y del valor final.

**2-5.** En el enunciado del teorema de la traslación real se señaló que, para que el teorema se pueda aplicar, la función retardada debe ser cero para todos los tiempos inferiores al tiempo de retardo. Demuéstrese lo anterior mediante el cálculo de la transformada de Laplace de la función $f(t) = e^{-(t-t_0)/\tau}$ donde $t_0$ y $\tau$ son constantes.

a) Se supone que se mantiene para todos los tiempos mayores a cero; esto es, se puede reordenar como $f(t) = e^{t_0/\tau}e^{-t/\tau}$
b) Se supone que es cero para $t \leq t_0$; es decir, se puede escribir de manera apropiada como $f(t) = u(t-t_0)e^{-(t-t_0)/\tau}$

¿Las dos respuestas son iguales? ¿Cuál de las dos concuerda con el teorema de la traslación real?

**2-6.** Encuéntrese la solución $y(t)$ de las siguientes ecuaciones diferenciales, utilizando el método de transformada de Laplace y la expansión en fracciones parciales. Las condiciones iniciales de $y(t)$ y sus derivadas son cero, la función de forzamiento es la función escalón unitario. $x(t) = u(t)$

a) $2\frac{dy(t)}{dt} + y(t) = 5x(t)$
b) $\frac{d^2y(t)}{dt^2} + 9\frac{dy(t)}{dt} + 9y(t) = x(t)$
c) $\frac{d^2y(t)}{dt^2} + 3\frac{dy(t)}{dt} + 9y(t) = x(t)$
d) $\frac{d^2y(t)}{dt^2} + 6\frac{dy(t)}{dt} + 9y(t) = x(t)$
e) $2\frac{d^3y(t)}{dt^3} + 7\frac{d^2y(t)}{dt^2} + 21\frac{dy(t)}{dt} + 9y(t) = x(t)$

**2-7.** Repítase el problema 2-6 (d) usando como función de forzamiento:
a) $x(t) = e^{-3t}$
b) $x(t) = u(t-1)e^{-3(t-1)}$

**2-8.** La forma normal de la ecuación diferencial del retardo de primer orden con tiempo muerto es:

$$\tau\frac{dy(t)}{dt} + y(t) = Kx(t - t_0)$$

donde:
- $\tau$ es la constante de tiempo
- $K$ es la ganancia
- $t_0$ es el tiempo muerto

Si se supone que la condición inicial es $y(0) = y_0$, encuéntrese, mediante la transformada de Laplace, la solución y(t) para cada una de las siguientes funciones de forzamiento:

a) Impulso unitario $x(t) = \delta(t)$
b) Escalón unitario $x(t) = u(t)$
c) Rampa parcial del problema 2-4
d) Onda senoidal de frecuencia $\omega$: $x(t) = \sin \omega t$

**2-9.** Una forma normal de la ecuación diferencial para el retardo de segundo orden se expresa mediante:

$$\tau^2\frac{d^2y(t)}{dt^2} + 2\zeta\tau\frac{dy(t)}{dt} + y(t) = Kx(t)$$

donde:
- $\tau$ es la constante de tiempo característica
- $\zeta$ es la tasa de amortiguamiento
- $K$ es la ganancia

Si se supone que todas las condiciones iniciales son cero, encuéntrese la respuesta de $y(t)$ al escalón unitario, con el método de transformada de Laplace, para los siguientes casos:

a) $\zeta > 1$, se conoce como sobreamortiguado.
b) $\zeta = 1$, se conoce como críticamente amortiguado.
c) $0 < \zeta < 1$, se conoce como subamortiguado.
d) $\zeta = 0$, se conoce como no amortiguado.
e) $\zeta < 0$, se conoce como inestable.

Con base en los resultados, ¿qué términos de la función y son característicos de un retardo subamortiguado y uno no amortiguado? ¿Se puede verificar la definición de estabilidad mediante la observación del resultado de la parte (e)?

**2-10.** Use un programa de computadora para calcular las raíces del polinomio denominador de las siguientes transformadas de Laplace; encuéntrese la $y$ inversa mediante el método de la expansión en fracciones parciales:

a) $Y(s) = \frac{s^2 + 1}{(s^3 + 1)}\cdot\frac{1}{s}$
b) $Y(s) = \frac{2}{24s^4 + 50s^3 + 35s^2 + 10s + 1}\cdot\frac{1}{s}$
c) $Y(s) = \frac{1}{4s^4 + 4s^3 + 17s^2 + 16s + 4}$

En el apéndice D se muestra un programa para encontrar raíces.

**2-11.** Linealícense las siguientes funciones respecto a la variable que se indica; el resultado debe estar en términos de las variables de desviación.

a) Ecuación de Antoine para presión de vapor:
$$p^0(T) = e^{[A - B/(T+C)]}$$
donde A, B y C son constantes.

b) Composición de vapor en equilibrio con líquido:
$$y(x) = \frac{\alpha x}{1 + (\alpha - 1)x}$$
donde $\alpha$, volatilidad relativa, es constante.

c) Flujo en una válvula:
$$f(\Delta p_v) = C_v\sqrt{\frac{\Delta p_v}{G}}$$
donde $C_v$ y $G$ son constantes.

d) Transferencia de calor por radiación:
$$q(T) = \epsilon\sigma AT^4$$
donde $\epsilon$, $\sigma$ y $A$ son constantes.

**2-12.** Como se indicó en el texto, el rango de aplicación de la ecuación linealizada depende del grado de no linealidad de la función original en el punto base. Demuéstrese lo anterior mediante el cálculo del rango de la fracción de mol líquido $x$, en el problema 2-11(b).

**2-13.** Repítase el problema 2-12 para la función de Arrhenius del ejemplo 2-11; calcúlese el rango de valores de temperatura para los cuales la función linealizada cumple dentro de $\pm 5\%$ con el coeficiente de la tasa de reacción $k(T)$. Calcúlese también el rango de valores de $T$ para los cuales el parámetro de la ecuación linealizada permanece dentro de $\pm 5\%$ del valor base. ¿Cuáles serían los resultados si se duplica el valor de $E$?

**2-14.** Evalúense los parámetros de la transformada que se obtuvo en el ejemplo 2-14, mediante la utilización de los parámetros cinéticos del ejemplo 2-11 y los siguientes parámetros de reactivo:

$$V = 2.6 \, m^3 \qquad \bar{f} = 2 \times 10^{-3} \, m^3/s \qquad \bar{c}_{A_i} = 12 \, kgmol/m^3$$

Nótese que el valor de $\bar{c}_A$ se puede calcular a partir de la relación de estado estacionario que se da en el ejemplo 2-14.

**2-15.** Con la ley de Raoult se obtiene la fracción de mol vapor y de un compuesto en equilibrio, mediante la siguiente relación:

$$y(x, T, p) = \frac{p^0(T)}{P}x$$

donde:
- $x$ es la fracción de mol líquido
- $T$ es la temperatura
- $P$ es la presión total

La presión de vapor $p^0(T)$ se obtiene con la ecuación de Antoine, como en el problema 2-11(a).

a) Se debe linealizar la fórmula para la fracción mol vapor y expresar el resultado en términos de las variables de desviación.
b) Evalúense los parámetros de la ecuación lineal para las siguientes condiciones:

**2-16.** Escríbase la aproximación lineal de las siguientes funciones, en términos de las variables de desviación:

a) $f(x, y) = y^2x + 2x + \ln y$
b) $f(x, y) = \frac{3\sqrt{x}}{y} + 2\sin(xy)$
c) $f(x, y) = y^x$

**2-17.** El tanque que se muestra en la figura 2-11 se coloca en una línea de tubería para reducir las variaciones de flujo debido a cambios en la presión de entrada $p_i(t)$ y en la presión de salida $p_o(t)$. En las condiciones base de estado estacionario el flujo a través del sistema es de 25.0 kgmol/h y las presiones son:

$$\bar{p}_i = 2000 \, kN/m^2$$
$$\bar{p} = 1800 \, kN/m^2$$
$$\bar{p}_o = 1600 \, kN/m^2$$

El volumen del tanque es $V = 10 \, m^3$. El balance molar en el tanque, si se supone que el comportamiento es el de un gas perfecto y la temperatura constante a 400 K, se expresa mediante:

$$\frac{V}{RT}\frac{dp(t)}{dt} = f_i(t) - f_o(t)$$

donde $R = 8314 \, N-m/kgmol K$ es la constante de los gases ideales. La tasa de flujo de entrada y de salida se expresa mediante:

$$f_i(t) = k_i\sqrt{p_i(t)}[p_i(t) - p(t)]$$
$$f_o(t) = k_o\sqrt{p(t)}[p(t) - p_o(t)]$$

donde $k_i$ y $k_o$ son los coeficientes de conductancia (constantes) de las válvulas de entrada y de salida, respectivamente; estas válvulas se ajustan para obtener las presiones base a partir del flujo base que se dio arriba. Linealícense las ecuaciones de arriba y resuélvanse para obtener la respuesta de la presión $p(t)$ en el tanque a las siguientes funciones de forzamiento:

a) Escalón unitario en la presión de entrada; la presión de salida es constante:
$$p_i(t) = u(t) \qquad p_o(t) = \text{constante}$$

b) Escalón unitario en la presión de salida; la presión de entrada permanece constante:
$$p_o(t) = u(t) \qquad p_i(t) = \text{constante}$$

Use el método de transformada de Laplace para resolver la ecuación diferencial.

---

# Capítulo 3: Sistemas dinámicos de primer orden

En este capítulo se tienen dos objetivos principales. El primero es presentar una introducción al desarrollo de modelos simples de proceso, los cuales son necesarios siempre que se requiere analizar los sistemas de control. El segundo objetivo, que se deriva del primero, es explicar el significado físico de algunos de los parámetros del proceso que definen la "personalidad" de éste; como se explicó en el capítulo 1, cuando ya se conoce la personalidad del proceso, entonces es posible diseñar el sistema de control que se requiere. También se estudiarán algunos términos nuevos y otros recursos matemáticos importantes para el estudio del control automático de proceso. Las herramientas que se estudiaron en el capítulo 2 se utilizarán ampliamente en éste.

Todo lo anterior se abordará mediante ejemplos de procesos. Se empezará con algunos ejemplos simples, y a partir de éstos se avanzará hacia los más complejos y que se acerquen más a lo real.

Para hacer el modelo de los procesos industriales generalmente se comienza con el balance de una cantidad que se conserva: masa o energía, este balance se puede escribir como:

$$\text{Tasa de acumulación} = \text{Flujo de entrada} - \text{Flujo de salida}$$

Como se puede imaginar, para escribir estos balances y todas las otras ecuaciones auxiliares se deben utilizar casi todas las áreas de la ingeniería de proceso, por ejemplo, la termodinámica, la transferencia de calor, flujo de fluidos, transferencia de masa e ingeniería de reacción; todo esto hace que el diseño de modelos de procesos industriales sea muy interesante y motivante.

## 3-1. PROCESO TÉRMICO

Considérese el tanque con agitación continua ilustrado en la figura 3-1, se tiene interés en conocer la forma en que responde la temperatura de salida, $T(t)$, a los cambios en la temperatura de entrada, $T_i(t)$.

```json
{
  "type": "image",
  "id": "image-07",
  "page": 92,
  "title": "Figura 3-1. Proceso térmico",
  "caption": "Tanque con agitación continua para proceso térmico",
  "description": "Diagrama esquemático de un tanque con agitación continua. La corriente de entrada tiene flujo q (m³/seg) y temperatura Tᵢ(t) (°C). La corriente de salida tiene flujo q (m³/seg) y temperatura T(t) (°C). El tanque tiene un agitador y está aislado térmicamente.",
  "elements": [
    "Tanque con agitación",
    "Corriente de entrada: q, Tᵢ(t)",
    "Corriente de salida: q, T(t)",
    "Agitador"
  ],
  "source": "Smith & Corripio, Control Automático de Procesos, Fig. 3-1"
}
```

En este ejemplo se supone que los flujos volumétricos de entrada y salida, la densidad de los líquidos y la capacidad calorífica de los líquidos son constantes y que se conocen todas estas propiedades. El líquido en el tanque se mezcla bien y el tanque está bien aislado, es decir, el proceso es adiabático.

La relación que se desea entre la temperatura de entrada y la de salida da como resultado un balance de energía en estado dinámico al contenido del tanque:

$$q\rho_i h_i(t) - q\rho h(t) = \frac{d(V\rho u(t))}{dt} \quad (3-1)$$

o, en términos de la temperatura:

$$q\rho_i C_{p_i}T_i(t) - q\rho C_pT(t) = \frac{d(V\rho C_vT(t))}{dt}$$

donde:
- $\rho_i, \rho$ = densidad del líquido a la entrada y a la salida, respectivamente, en $kg/m^3$
- $C_{p_i}, C_p$ = capacidad calorífica a presión constante del líquido a la entrada y a la salida, respectivamente, en $J/kg-°C$
- $C_v$ = capacidad calorífica a volumen constante del líquido, en $J/kg-°C$
- $V$ = volumen del líquido en el tanque, $m^3$
- $h_i, h$ = entalpía del líquido a la entrada y a la salida, respectivamente, $J/kg$
- $u$ = energía interna del líquido en el tanque, $J/kg$

Puesto que se supone que la densidad y la capacidad calorífica permanecen constantes, sobre todo el rango de temperatura de operación, la última ecuación se puede escribir como:

$$q\rho C_pT_i(t) - q\rho C_pT(t) = V\rho C_v\frac{dT(t)}{dt} \quad (3-2)$$

Esta es una ecuación diferencial lineal ordinaria de primer orden que expresa la relación entre la temperatura de entrada y la de salida. Es importante señalar que en esta ecuación sólo existe una incógnita, $T(t)$; la temperatura de entrada, $T_i(t)$, es una variable de entrada y, por tanto, no se considera como incógnita, ya que se puede especificar la forma en que cambia, por ejemplo, un cambio en escalón o en rampa. Para indicar que existe una ecuación con una incógnita se escribe:

$$q\rho C_pT_i(t) - q\rho C_pT(t) = V\rho C_v\frac{dT(t)}{dt} \quad (3-2)$$

Con la solución de esta ecuación diferencial para cierta temperatura de entrada se obtiene la respuesta de la temperatura de salida como función del tiempo. La temperatura de entrada se conoce como **variable de entrada o función de forzamiento**, ya que es la que fuerza el cambio en la temperatura de salida; la temperatura de salida se conoce como **variable de salida o variable de respuesta**, ya que es la que responde a la función de forzamiento.

Antes de resolver la ecuación anterior se hace un cambio de variable, con el que se simplifica la solución; se escribe el balance de energía del contenido del tanque en estado estacionario:

$$q\rho C_p\bar{T}_i - q\rho C_p\bar{T} = 0 \quad (3-3)$$

Al substraer la ecuación (3-3) de la ecuación (3-2) se tiene:

$$q\rho C_p(T_i(t) - \bar{T}_i) - q\rho C_p(T(t) - \bar{T}) = V\rho C_v\frac{d(T(t) - \bar{T})}{dt} \quad (3-4)$$

Ahora se definen las siguientes variables de desviación, como se vio en el capítulo 2:

$$\mathbf{T}(t) = T(t) - \bar{T}$$
$$\mathbf{T}_i(t) = T_i(t) - \bar{T}_i \quad (3-5)$$

donde:
- $\bar{T}_i, \bar{T}$ = valores de estado estacionario de la temperatura de entrada y de salida, respectivamente, °C
- $\mathbf{T}(t), \mathbf{T}_i(t)$ = variables de desviación de la temperatura de entrada y de salida, respectivamente, °C

Se substituyen las ecuaciones (3-5) y (3-6) en la (3-4) y se obtiene:

$$q\rho C_p\mathbf{T}_i(t) - q\rho C_p\mathbf{T}(t) = V\rho C_v\frac{d\mathbf{T}(t)}{dt} \quad (3-7)$$

La ecuación (3-7) es la misma que la ecuación (3-2), con la excepción de que está en términos de las temperaturas de desviación. La solución de esta ecuación da por resultado la temperatura de desviación, $\mathbf{T}(t)$, contra el tiempo, para cierta función de forzamiento $\mathbf{T}_i(t)$. Si se desea la temperatura real de salida, $T(t)$, se debe añadir el valor de estado estacionario $\bar{T}$ a $\mathbf{T}(t)$, debido a la ecuación (3-5).

La definición y utilización de las variables de desviación es muy importante en el análisis y diseño de sistemas de control de proceso. En toda la teoría de control se utilizan casi exclusivamente estas variables y, por tanto, se debe comprender bien el significado e importancia de las variables de desviación. Como se explicó en el capítulo 2, con su uso se tiene la ventaja de que su valor indica el grado de desviación respecto a algún valor de operación de estado estacionario; en la práctica, este valor de estado estacionario puede ser el valor deseado de la variable. Otra ventaja en el uso de estas variables es que su valor inicial es cero, si se supone que se comienza a partir de un estado estacionario, con lo que se simplifica la solución de las ecuaciones diferenciales semejantes a la ecuación (3-7). Como se mencionó, dichas variables se usan ampliamente a lo largo de este libro.

La ecuación (3-7) se puede reordenar como sigue:

$$\frac{V\rho C_v}{q\rho C_p}\frac{d\mathbf{T}(t)}{dt} + \mathbf{T}(t) = \mathbf{T}_i(t)$$

sea:
$$\tau = \frac{V\rho C_v}{q\rho C_p} \quad (3-8)$$

de manera que:
$$\tau\frac{d\mathbf{T}(t)}{dt} + \mathbf{T}(t) = \mathbf{T}_i(t) \quad (3-9)$$

Puesto que ésta es una ecuación diferencial lineal, con la utilización de la transformada de Laplace se obtiene:

$$\tau s\mathbf{T}(s) - \tau\mathbf{T}(0) + \mathbf{T}(s) = \mathbf{T}_i(s)$$

Pero $\mathbf{T}(0) = 0$ y, por tanto, algebraicamente:

$$\mathbf{T}(s) = \frac{1}{\tau s + 1}\mathbf{T}_i(s) \quad (3-10)$$

$$\frac{\mathbf{T}(s)}{\mathbf{T}_i(s)} = \frac{1}{\tau s + 1} \quad (3-11)$$

La ecuación (3-11) se conoce como **función de transferencia**; es una función de transferencia de primer orden porque se desarrolla a partir de una ecuación diferencial de primer orden. Los procesos que se describen mediante esta función se denominan **procesos de primer orden, sistemas de primer orden o retardos de primer orden**; algunas veces también se conocen como sistemas de capacitancia única, porque la función de transferencia es del mismo tipo que la descrita por un sistema eléctrico con una resistencia y un capacitor (R-C).

El nombre de "función de transferencia" proviene del hecho de que con la solución de la ecuación se transfiere la entrada o función de forzamiento, $\mathbf{T}_i(t)$, a la salida o variable de respuesta, $\mathbf{T}(t)$. Las funciones de transferencia se tratan con más detalle en la sección 3-3.

Si se supone que la temperatura de entrada, $T_i(t)$, al tanque se incrementa en $A$ grados C, es decir, sufre un cambio en escalón con $A$ grados de magnitud, esto se expresa matemáticamente como sigue:

$$T_i(t) = \bar{T}_i \qquad t < 0$$
$$T_i(t) = \bar{T}_i + A \qquad t \geq 0$$

o como se vio en el capítulo 2:

$$\mathbf{T}_i(t) = A u(t)$$

Al obtener la transformada de Laplace se tiene:

$$\mathbf{T}_i(s) = \frac{A}{s}$$

De la substitución en la ecuación (3-10) se obtiene:

$$\mathbf{T}(s) = \frac{A}{s(\tau s + 1)}$$

y con el uso de las fracciones parciales para obtener la transformada inversa se llega a:

$$\mathbf{T}(t) = A(1 - e^{-t/\tau}) \quad (3-12)$$

$$T(t) = \bar{T} + A(1 - e^{-t/\tau}) \quad (3-13)$$

En la figura 3-2 se ilustra gráficamente la solución de las ecuaciones (3-12) y (3-13). La ecuación (3-12) expresa el significado físico de $\tau$, la cual se conoce como **constante de tiempo** del proceso. Si se hace $t = \tau$, se tiene:

$$\mathbf{T}(\tau) = A(1 - e^{-\tau/\tau}) = A(1 - e^{-1})$$
$$\mathbf{T}(\tau) = 0.632A$$

Es decir, en una constante de tiempo se alcanza el 63.2% del cambio total, lo cual se ilustra gráficamente en la figura 3-2; en consecuencia, la constante de tiempo guarda relación con la velocidad de respuesta del proceso. Mientras más lenta es la respuesta de un proceso a la función de forzamiento o entrada, más grande es el valor de $\tau$; tanto más rápida es la respuesta del proceso a la función de forzamiento, cuanto más pequeño es el valor de $\tau$. $\tau$ debe estar en unidades de tiempo; de la ecuación (3-8) se ve que:

$$\tau = \frac{[m^3][kg/m^3][J/kg-°C]}{[m^3/s][kg/m^3][J/kg-°C]} \text{ segundos}$$

También es muy importante darse cuenta que la constante de tiempo se compone con las diferentes propiedades físicas y parámetros de operación del proceso, como se observa en la ecuación (3-8); es decir, la constante de tiempo depende del volumen de líquido en el tanque ($V$), de las capacidades caloríficas ($C_p$ y $C_v$) y del flujo del proceso ($q$). Si alguna de estas características cambia, la constante de tiempo también cambia. Otra manera de expresar lo anterior es que, si alguna de las condiciones del proceso cambia, también cambia la "personalidad" del proceso y ello se refleja en la velocidad de respuesta del proceso o constante de tiempo.

Otro punto importante es que en este ejemplo el valor de la constante de tiempo permanece constante en todo el rango de operación de $T(t)$, la cual es una propiedad de los sistemas lineales que no se aplica para el caso de los sistemas no lineales, como se verá de manera separada.

Hasta ahora se supuso que el tanque está bien aislado, lo que propicia un proceso adiabático; es decir, no hay pérdidas de calor hacia la atmósfera y, en consecuencia, no existe término de pérdida de calor en el balance de energía. Si se elimina la suposición de operación adiabática y se toma en cuenta la pérdida de calor en el balance de energía, se llega a la siguiente ecuación:

$$q\rho C_pT_i(t) - Q(t) - q\rho C_pT(t) = V\rho C_v\frac{dT(t)}{dt} \quad (3-14)$$

donde:
$$Q(t) = UA[T(t) - T_s(t)]$$

- $U$ = coeficiente global de transferencia de calor, $J/m^2-K-s$
- $A$ = área de transferencia de calor, $m^2$
- $T_s(t)$ = temperatura ambiente, °C, que es una variable de entrada

El coeficiente global de transferencia de calor, $U$, es una función de diversos factores; uno de ellos es la temperatura que, sin embargo, para este ejemplo en particular, se supone es constante. Puesto que se supone que la masa y la densidad del líquido en el tanque también son constantes, entonces la altura del líquido es constante y, en consecuencia, el área de transferencia de calor, $A$, también es constante.

Para obtener las variables de desviación, primero se escribe el balance de energía de estado estacionario para el proceso:

$$q\rho C_p\bar{T}_i - UA(\bar{T} - \bar{T}_s) - q\rho C_p\bar{T} = 0 \quad (3-15)$$

Al substraer la ecuación (3-15) de la ecuación (3-14), se tiene:

$$q\rho C_p(T_i(t) - \bar{T}_i) - UA[(T(t) - \bar{T}) - (T_s(t) - \bar{T}_s)]$$
$$- q\rho C_p(T(t) - \bar{T}) = V\rho C_v\frac{d(T(t) - \bar{T})}{dt} \quad (3-16)$$

Se define una nueva variable de desviación como:

$$\mathbf{T}_s(t) = T_s(t) - \bar{T}_s \quad (3-17)$$

Con la substitución de las ecuaciones (3-5), (3-6) y (3-17) en la ecuación (3-16), se llega a:

$$q\rho C_p\mathbf{T}_i(t) - UA(\mathbf{T}(t) - \mathbf{T}_s(t)) - q\rho C_p\mathbf{T}(t) = V\rho C_v\frac{d\mathbf{T}(t)}{dt} \quad (3-18)$$

La ecuación (3-18) es la misma que la (3-14), con la excepción de que se escribe en términos de las variables de desviación. La ecuación (3-18) es también una ecuación diferencial lineal de primer orden y, en este caso, aún existe una ecuación con una incógnita, $\mathbf{T}(t)$; la nueva variable, $\mathbf{T}_s(t)$, es otra función de forzamiento. Conforme cambia la temperatura ambiente, $\mathbf{T}_s(t)$, se afecta la pérdida de calor y, en consecuencia, la temperatura del líquido que se procesa. La ecuación (3-18) se puede reordenar como sigue:

$$\frac{V\rho C_v}{q\rho C_p + UA}\frac{d\mathbf{T}(t)}{dt} + \mathbf{T}(t) = \frac{q\rho C_p}{q\rho C_p + UA}\mathbf{T}_i(t) + \frac{UA}{q\rho C_p + UA}\mathbf{T}_s(t)$$

$$\tau\frac{d\mathbf{T}(t)}{dt} + \mathbf{T}(t) = K_1\mathbf{T}_i(t) + K_2\mathbf{T}_s(t) \quad (3-19)$$

donde:
$$\tau = \frac{V\rho C_v}{q\rho C_p + UA} \text{ segundos} \quad (3-20)$$

$$K_1 = \frac{q\rho C_p}{q\rho C_p + UA}, \text{ sin dimensiones (C/C)} \quad (3-21)$$

$$K_2 = \frac{UA}{q\rho C_p + UA}, \text{ sin dimensiones (C/C)} \quad (3-22)$$

En el miembro derecho de la ecuación (3-19) aparecen dos funciones forzadas, $\mathbf{T}_i(t)$ y $\mathbf{T}_s(t)$, que actúan sobre la respuesta o miembro izquierdo de la ecuación, $\mathbf{T}(t)$. La transformada de Laplace de la ecuación (3-19) es:

$$\tau s\mathbf{T}(s) - \tau\mathbf{T}(0) + \mathbf{T}(s) = K_1\mathbf{T}_i(s) + K_2\mathbf{T}_s(s)$$

Pero $\mathbf{T}(0) = 0$, por lo cual, al reordenar esta ecuación, se tiene:

$$\mathbf{T}(s) = \frac{K_1}{\tau s + 1}\mathbf{T}_i(s) + \frac{K_2}{\tau s + 1}\mathbf{T}_s(s) \quad (3-23)$$

Si la temperatura ambiente permanece constante, $\mathbf{T}_s(s) = 0$ y $\mathbf{T}_s(t) = 0$, entonces la función de transferencia que relaciona la temperatura del proceso con la del agua que entra es:

$$\frac{\mathbf{T}(s)}{\mathbf{T}_i(s)} = \frac{K_1}{\tau s + 1} \quad (3-24)$$

Si la temperatura del líquido que entra permanece constante, $T_i(t) = \bar{T}_i$ y $\mathbf{T}_i(t) = 0$, la función de transferencia que relaciona la temperatura del proceso con la temperatura ambiente es:

$$\frac{\mathbf{T}(s)}{\mathbf{T}_s(s)} = \frac{K_2}{\tau s + 1} \quad (3-25)$$

Si tanto la temperatura del líquido que entra como la ambiente cambian, entonces la ecuación (3-23) expresa la relación correcta.

En las tres últimas ecuaciones se encuentra un parámetro nuevo y muy importante, $K_i$, que se conoce como **ganancia del proceso o ganancia de estado estacionario**. Para conocer el significado físico de esta ganancia, supóngase que la temperatura de entrada al tanque se incrementa en $A$ grados C, entonces la respuesta de la temperatura a esta función de forzamiento se expresa mediante:

$$\mathbf{T}(s) = \frac{K_1 A}{s(\tau s + 1)}$$

de lo cual:

$$\mathbf{T}(t) = K_1 A(1 - e^{-t/\tau}) \quad (3-26)$$

o:
$$T(t) = \bar{T} + K_1 A(1 - e^{-t/\tau}) \quad (3-27)$$

La respuesta se ilustra gráficamente en la figura 3-3. $K_1A$ expresa la cantidad total de cambio; la ganancia multiplica el cambio en la función de forzamiento. Se puede decir que la ganancia indica cuánto cambia la variable de salida por unidad de cambio en la función de forzamiento o variable de entrada; es decir, la ganancia define la sensibilidad del proceso.

La ganancia se define matemáticamente como sigue:

$$K = \frac{\Delta O}{\Delta I} = \frac{\Delta \text{variable de salida}}{\Delta \text{variable de entrada}} \quad (3-28)$$

La ganancia es otro parámetro relacionado con la "personalidad" del proceso que se controla y, en consecuencia, depende de las propiedades físicas y los parámetros de operación del proceso, como se muestra mediante las ecuaciones (3-21) y (3-22). Las ganancias de dicho proceso dependen del flujo, de la densidad y capacidad calorífica del líquido que se procesa ($q, \rho, C_p$), del coeficiente global de transferencia de calor ($U$) y del área de transferencia de calor ($A$); si cambia cualquiera de estos factores, la personalidad del proceso cambia y repercute sobre la ganancia. Al igual que la constante de tiempo, en este ejemplo particular las ganancias son constantes, sobre todo el rango de operación.

En este ejemplo existen dos ganancias: $K_1$, que relaciona la temperatura de salida con la temperatura de entrada; y $K_2$, que relaciona la temperatura de salida con la del ambiente. Las unidades de la ganancia deben ser las unidades de la variable de salida, divididas entre las unidades de la función de forzamiento o variable de entrada, lo cual se puede apreciar en la ecuación (3-28).

En la ecuación (3-23) se aprecia que sólo existe una constante de tiempo en el proceso; es decir, el tiempo que se necesita para que la temperatura alcance un cierto porcentaje de su cambio total, debido a un cambio en la temperatura de entrada, es igual al tiempo que se necesita para que alcance el mismo porcentaje cuando es la temperatura ambiente la que cambia. Este caso no siempre es cierto, en el presente ejemplo existe más de una ganancia, hay una por cada función de forzamiento; en algunos procesos puede haber más de una constante de tiempo, probablemente una por cada función forzada. Conforme se avance en el estudio se verán algunos ejemplos de esto.

Durante el análisis del proceso, siempre es importante detenerse en algún punto para verificar si hay errores en el desarrollo. Un punto conveniente se encuentra generalmente después del desarrollo de la ecuación (3-23); se puede realizar una verificación rápida mediante el examen de los signos de las ecuaciones, para comprobar si tienen sentido en el mundo real; en dicha ecuación ambas ganancias son positivas, lo cual indica que si la temperatura de entrada se incrementa, la temperatura de salida también aumenta; lo cual tiene sentido en este proceso. La ecuación (3-23) también muestra que si la temperatura ambiente aumenta, la de salida también se incrementa; esto tiene sentido porque, al aumentar la temperatura ambiente, decrece la tasa de pérdidas de calor del tanque y, por tanto, aumenta la temperatura del contenido del tanque. Con esta verificación rápida se aumenta la confianza y se puede continuar el análisis con la renovada expectativa del posible éxito.

## 3-2. PROCESO DE UN GAS

Considérese el recipiente de gas que se muestra en la figura 3-4, el recipiente actúa como amortiguador o tanque de compensación en un proceso. Se supone que el proceso se desarrolla de manera isotérmica, a una temperatura $T$, y que el flujo a través de la válvula de salida se expresa mediante:

$$q_o(t) = \frac{\Delta p(t)}{R_v} = \frac{p(t) - p_2(t)}{R_v} \quad (3-29)$$

donde $R_v$ = resistencia al flujo en la válvula, psi/scfm. Se tiene interés en conocer la manera en que la presión en el tanque responde a los cambios en el flujo de entrada, $q_i(t)$, y en la presión de salida de la válvula, $p_2(t)$.

Para este proceso la relación que se requiere la da un balance de masa de estado dinámico:

$$\rho q_i(t) - \rho q_o(t) = \frac{dm(t)}{dt} \quad (3-30)$$

donde:
- $m(t)$ = masa del gas en el tanque, lb
- $\rho$ = densidad del gas en condiciones estándar de 14.7 psia y 60°F, $lb/pies^3$

Si la presión en el tanque es baja, la relación entre la masa del gas y la presión se establece con la ecuación de estado de los gases perfectos:

$$p(t) = \frac{RT}{VM}m(t) \quad (3-31)$$

donde:
- $T$ = temperatura absoluta en el tanque, °R
- $V$ = volumen del tanque, $pies^3$
- $M$ = peso molecular del gas
- $R$ = constante de los gases perfectos = $10.73 \frac{pies^3-psia}{lb mol-°R}$

A partir de la expresión que representa el flujo a través de la válvula de salida, ecuación (3-29), se obtiene otra ecuación:

$$q_o(t) = \frac{p(t) - p_2(t)}{R_v} \quad (3-29)$$

Con la substitución de las ecuaciones (3-29) y (3-31) en la ecuación (3-30) se tiene:

$$\rho q_i(t) - \rho\frac{[p(t) - p_2(t)]}{R_v} = \frac{VM}{RT}\frac{dp(t)}{dt} \quad (3-32)$$

Para obtener las variables de desviación y la función de transferencia se sigue el mismo desarrollo que en el ejemplo precedente. La escritura del balance de masa de estado estacionario de la siguiente expresión:

$$\rho\bar{q}_i - \rho\bar{q}_o = 0$$
$$\rho\bar{q}_i - \rho\frac{(\bar{p} - \bar{p}_2)}{R_v} = 0 \quad (3-33)$$

Se substrae la ecuación (3-33) de la (3-32) para obtener:

$$\rho(q_i(t) - \bar{q}_i) - \frac{\rho}{R_v}[(p(t) - \bar{p}) - (p_2(t) - \bar{p}_2)] = \frac{VM}{RT}\frac{d(p(t) - \bar{p})}{dt} \quad (3-34)$$

Las variables de desviación se definen como:

$$Q_i(t) = q_i(t) - \bar{q}_i$$
$$P(t) = p(t) - \bar{p}$$
$$P_2(t) = p_2(t) - \bar{p}_2$$

Al substituir estas variables de desviación en la ecuación (3-34) y reordenar la ecuación algebraicamente, se tiene:

$$\tau\frac{dP(t)}{dt} + P(t) = K_1Q_i(t) + P_2(t) \quad (3-35)$$

donde:
$$\tau = \frac{VM}{RT\rho}R_v, \text{ minutos}$$
$$K_1 = R_v, \text{ psia/scfm}$$

Se obtiene la transformada de Laplace, lo que da la relación entre la respuesta o variable de salida $P(t)$ y las funciones forzadas $Q_i(t)$ y $P_2(t)$:

$$P(s) = \frac{K_1}{\tau s + 1}Q_i(s) + \frac{1}{\tau s + 1}P_2(s) \quad (3-36)$$

A partir de esta ecuación se obtiene la función de transferencia entre $P(s)$ y $Q_i(s)$:

$$\frac{P(s)}{Q_i(s)} = \frac{K_1}{\tau s + 1} \quad (3-37)$$

y entre $P(s)$ y $P_2(s)$:

$$\frac{P(s)}{P_2(s)} = \frac{1}{\tau s + 1} \quad (3-38)$$

Ambas funciones de transferencia son de primer orden.

A estas alturas se empieza a crear las condiciones para la respuesta completa de cualquier sistema de primer orden; por ejemplo, mediante el análisis de la ecuación (3-37) se sabe que si el flujo de entrada al tanque cambia en +10 scfm, la presión en el tanque cambiará en un total de $10K_1$ psi, lo cual es verdad si ninguna otra perturbación afecta al proceso; también se sabe que un cambio de $0.632(10K_1)$ en la presión tiene lugar en una constante de tiempo, $\tau$, como se ilustra gráficamente en la figura 3-5. Recuérdese que $K_1$ es la ganancia que $Q_i(t)$ tiene sobre $P(t)$ y que $\tau$ proporciona la velocidad de respuesta de $P(t)$ una vez que responde al cambio en $Q_i(t)$.

De manera similar, mediante la observación de la ecuación (3-38) se ve que, cuando la presión de salida de la válvula cambia en -2 psi, el cambio total en la presión del tanque es de -2 psi, la ganancia de $P_2(t)$ sobre $P(t)$ es de +1 psi/psi. Si la presión de salida decrece, entonces habrá una mayor caída de presión en la sección de la válvula, lo que da como resultado una salida mayor del tanque y, en consecuencia, una reducción en la presión en el tanque. También se sabe que el 63.2% del cambio total de presión, o $0.632(-2)$ psi, tiene lugar en $\tau$ minutos.

## 3-3. FUNCIONES DE TRANSFERENCIA Y DIAGRAMAS DE BLOQUES

### Funciones de transferencia

El concepto función de transferencia es uno de los más importantes en el estudio de la dinámica de proceso y del control automático de proceso, por lo que es recomendable considerar aquí algunas de sus propiedades y características.

La función de transferencia ya se definió como la relación de la transformada de Laplace de la variable de salida sobre la transformada de Laplace de la variable de entrada.

La función de transferencia se representa generalmente por:

$$G(s) = \frac{Y(s)}{X(s)} = \frac{K(a_ms^m + a_{m-1}s^{m-1} + \ldots + a_1s + 1)}{(b_ns^n + b_{n-1}s^{n-1} + \ldots + b_1s + 1)} \quad (3-39)$$

donde:
- $G(s)$ = representación general de una función de transferencia
- $Y(s)$ = transformada de Laplace de la variable de salida
- $X(s)$ = transformada de Laplace de la función de forzamiento o variable de entrada
- $K$, $a$'s y $b$'s = constantes

En la ecuación (3-39) se muestra la mejor manera de escribir la función de transferencia; cuando se escribe de esta manera, $K$ representa la ganancia del sistema y tiene como unidades las de $Y(s)$ sobre las unidades de $X(s)$. Las otras constantes, las $a_i$ y las $b_i$, tienen como unidades (tiempo)$^i$, donde $i$ es la potencia de la variable de Laplace, $s$, que se asocia con la constante particular, lo que da como resultado un término sin dimensiones dentro del paréntesis, ya que la unidad de $s$ es $1/\text{tiempo}$.

Nota: En general, la unidad de $s$ es el recíproco de la unidad de la variable independiente que se usa en la definición de la transformada de Laplace, ecuación (2-1). En la dinámica y control del proceso la variable independiente es el tiempo y, en consecuencia, la unidad de $s$ es $1/\text{tiempo}$.

Nótese que el coeficiente de $s^0$ es 1.

La función de transferencia define completamente las características de estado estacionario y dinámico, es decir, la respuesta total de un sistema que se describe mediante una ecuación diferencial lineal. Esta es característica del sistema, y sus términos determinan si el sistema es estable o inestable y si su respuesta a una entrada no oscilatoria es oscilatoria o no. Se dice que el sistema o proceso es estable cuando su salida se mantiene limitada (finita) para una entrada limitada. En los capítulos 6 y 7 se trata con más detalle el tema de la estabilidad de los sistemas de proceso.

Las siguientes son algunas propiedades importantes de las funciones de transferencia:

1. En las funciones de transferencia de los sistemas físicos reales, la potencia más alta de $s$ en el numerador nunca es mayor a la del denominador; en otras palabras, $n \geq m$.

2. La función de transferencia relaciona las transformadas de las variables de entrada con las de salida, a partir de algún estado inicial estacionario; de lo contrario, las condiciones iniciales que no son cero originan términos adicionales en la transformada de la variable de salida.

3. Para los sistemas estables, la relación de estado estacionario entre el cambio en la variable de entrada y el cambio en la variable de salida se obtiene con:

$$\lim_{s \to 0}G(s)$$

Lo cual se deriva del teorema del valor final que se presentó en el capítulo 2:

$$\lim_{s \to 0}sY(s)$$
$$= \lim_{s \to 0}sG(s)X(s)$$
$$= \left[\lim_{s \to 0}G(s)\right]\left[\lim_{s \to 0}sX(s)\right]$$
$$= \left[\lim_{s \to 0}G(s)\right]\lim_{t \to \infty}x(t)$$

Esto significa que el cambio en la variable de salida, después de un tiempo muy largo, si está limitado, se obtiene al multiplicar la función de transferencia con $s = 0$ veces el valor final del cambio en la entrada.

### Diagramas de bloques

La representación gráfica de las funciones de transferencia por medio de diagramas de bloques es una herramienta muy útil en el control de proceso. James Watt introdujo por primera vez estos diagramas de bloques cuando aplicó el concepto de control por retroalimentación a la máquina de vapor, como se mencionó en el capítulo 1. La máquina de vapor constaba de varios acoplamientos y otros dispositivos mecánicos lo suficientemente complejos como para que Watt decidiera ilustrar gráficamente en su esquema de control la interacción de todos esos dispositivos. En esta sección se presenta una introducción a los diagramas y al álgebra de bloques.

En general, los diagramas de bloques constan de cuatro elementos básicos: flechas, puntos de sumatoria, puntos de derivación y bloques; en la figura 3-6 se ilustran estos elementos, de cuya combinación se forman todos los diagramas de bloques. Las flechas indican, en general, el flujo de información; representan las variables del proceso o las señales de control; cada punta de flecha indica la dirección del flujo de información. Los puntos de sumatoria representan la suma algebraica de las flechas que entran ($E(s) = R(s) - C(s)$). El punto de bifurcación es la posición sobre una flecha, en la cual la información sale y va de manera concurrente a otros puntos de sumatoria o bloques. Los bloques representan la operación matemática, en forma de función de transferencia, por ejemplo, $G_c(s)$, que se realiza sobre la señal de entrada (flecha) para producir la señal de salida. Las flechas y los bloques de la figura 3-6 representan la siguiente expresión matemática:

$$M(s) = G_C(s)E(s) = G_C(s)(R(s) - C(s))$$

Cualquier diagrama de bloques se puede tratar o manejar de manera algebraica; en la tabla 3-1 se muestran algunas reglas del álgebra de los diagramas de bloques, las cuales son importantes siempre que se requiere simplificar los diagramas de bloques.

A continuación se verán algunos ejemplos del álgebra de los diagramas de bloques.

**Ejemplo 3-1.** Dibújese el diagrama a bloques para las ecuaciones (3-11) y (3-23). La ecuación (3-11) aparece en la figura 3-7; la ecuación (3-23) se puede dibujar de dos maneras diferentes, como se muestra en la figura 3-8.

En los diagramas a bloques de la ecuación (3-23) se ilustra gráficamente que la respuesta total del sistema se obtiene mediante la adición algebraica de la respuesta a que da origen el cambio en la temperatura de entrada y la respuesta debida al cambio en la temperatura ambiente. Esta propiedad de la suma algebraica de las respuestas debidas a varias entradas para obtener la respuesta final es particular de los sistemas lineales y se conoce como **principio de superposición**. Este principio también sirve como base para definir los sistemas lineales; esto es, se dice que un sistema es lineal si obedece al principio de superposición.

**Ejemplo 3-2.** Determínese la función de transferencia que relaciona $Y(s)$ con $X_1(s)$ y $X_2(s)$, a partir del diagrama de bloques de la figura 3-9a; es decir, obténgase:

$$\frac{Y(s)}{X_1(s)} \qquad \text{y} \qquad \frac{Y(s)}{X_2(s)}$$

El diagrama de la figura 3-9a se puede reducir al de la figura 3-9b mediante la regla 4; después se puede reducir aún más, al diagrama de la figura 3-9c, con la aplicación de la regla 2. Entonces:

$$Y(s) = G_3(G_1 - G_2)X_1(s) + (G_4 - 1)X_2(s)$$

a partir de la cual se pueden determinar las dos funciones de transferencia que se desean:

$$\frac{Y(s)}{X_1(s)} = G_3(G_1 - G_2)$$
$$\frac{Y(s)}{X_2(s)} = G_4 - 1$$

Con este ejemplo se ilustra el procedimiento para reducir un diagrama de bloques a una función de transferencia; tal reducción es necesaria en el estudio del control de proceso, como se verá en los capítulos 6, 7 y 8, en los cuales se desarrollarán numerosos ejemplos de diagramas de bloques de sistemas de control por retroalimentación, en cascada y por acción precalculada. A continuación se estudia la reducción de algunos de dichos diagramas a funciones de transferencia.

**Ejemplo 3-3.** En la figura 3-10 se ilustra el diagrama a bloques del sistema típico de control por retroalimentación. A partir de este diagrama se debe determinar:

$$\frac{C(s)}{L(s)} \qquad \text{y} \qquad \frac{C(s)}{C^{flip}(s)}$$

Mediante la aplicación de las reglas 2, 3 y 5 se encuentra que:

$$C(s) = G_CG_2G_3G_4E(s) + G_5G_4L(s) \quad (3-40)$$

También, al aplicar la regla 5 se obtiene:

$$E(s) = G_1C^{flip}(s) - G_6C(s) \quad (3-41)$$

De la substitución de la ecuación (3-41) en la (3-40) resulta:

$$C(s) = G_1G_CG_2G_3G_4C^{flip}(s) - G_CG_2G_3G_4G_6C(s) + G_5G_4L(s)$$

y, después de algún manejo algebraico, se tiene:

$$C(s) = \frac{G_1G_CG_2G_3G_4}{1 + G_CG_2G_3G_4G_6}C^{flip}(s) + \frac{G_5G_4}{1 + G_CG_2G_3G_4G_6}L(s) \quad (3-42)$$

Ahora se obtienen las funciones individuales de transferencia a partir de la ecuación (3-42):

$$\frac{C(s)}{C^{flip}(s)} = \frac{G_1G_CG_2G_3G_4}{1 + G_CG_2G_3G_4G_6} \quad (3-43)$$

y:

$$\frac{C(s)}{L(s)} = \frac{G_5G_4}{1 + G_CG_2G_3G_4G_6} \quad (3-44)$$

En el ejemplo 3-3 se muestra cómo reducir a funciones de transferencia el diagrama de bloques simple de un circuito de retroalimentación de control. Este tipo de diagramas de bloques y de funciones de transferencia serán útiles en los capítulos 6 y 7, cuando se aborde el control por retroalimentación.

Las funciones de transferencia de las ecuaciones (3-43) y (3-44) se conocen como "funciones de transferencia de circuito cerrado", la razón del uso de este término se torna evidente en el capítulo 6. Al observar la ecuación (3-43) es notorio que el numerador es el producto de todas las funciones de transferencia en la trayectoria hacia adelante entre las dos variables que relaciona la función de transferencia $C^{flip}(s)$ y $C(s)$; el denominador de esta ecuación es uno (1) más el producto de todas las funciones en el circuito de control. En la figura 3-11 se muestra el mismo diagrama de bloques de la figura 3-10, pero se indica cuál es el significado del circuito de control. Un análisis de la ecuación (3-44) muestra que el numerador es nuevamente el producto de las funciones de transferencia en la trayectoria hacia adelante entre $L(s)$ y $C(s)$; el denominador es el mismo de la ecuación (3-43).

Con el apoyo de las ecuaciones (3-43) y (3-44) se puede generalizar la forma de la función de transferencia de circuito cerrado que se obtiene a partir de diagramas similares al de la figura 3-10:

$$G(s) = \frac{Y(s)}{X(s)} = \frac{\sum_{i=1}^{L}\left[\prod_{j=1}^{J}G_j\right]}{1 + \sum_{k=1}^{K}\left[\prod_{j=1}^{I}G_j\right]_k} \quad (3-45)$$

donde:
- $L$ = cantidad de trayectorias hacia adelante entre $X(s)$ y $Y(s)$
- $J$ = cantidad de funciones de transferencia en cada trayectoria hacia adelante entre $X(s)$ y $Y(s)$
- $G_j$ = función de transferencia en cada trayectoria hacia adelante
- $K$ = cantidad de circuitos combinados en el diagrama a bloques
- $I$ = cantidad de funciones de transferencia en cada circuito
- $G_i$ = función de transferencia en cada circuito

El término del numerador de la ecuación (3-45) indica que se multiplican juntas las $J$ funciones de transferencia, $G_j$, en cada trayectoria hacia adelante, y entonces se suman las $L$ trayectorias hacia adelante. El denominador es 1 (uno) más la sumatoria de los productos de las $I$ funciones de transferencia, $G_i$, en cada circuito, para los $K$ circuitos.

**Ejemplo 3-4.** Considérese otro diagrama a bloques típico, como el de la figura 3-12; en el capítulo 8 se muestra que con este diagrama de bloques se describe un sistema de control en cascada. Determínense las siguientes funciones de transferencia:

Se puede pensar que el diagrama a bloques de la figura 3-12 está compuesto de dos sistemas de circuito cerrado, uno dentro del otro (en la práctica esto es exactamente lo que sucede). Por lo tanto, el primer paso es reducir el circuito interno; en la figura 3-13 se muestra este circuito por separado. Mediante la ecuación (3-45) se pueden determinar las siguientes dos funciones de transferencia para este circuito interno:

$$\frac{C_1(s)}{R_1(s)} = \frac{G_{C_1}G_1G_2}{1 + G_{C_1}G_1G_2G_5} \quad (3-46)$$

$$\frac{C_1(s)}{L(s)} = \frac{G_3}{1 + G_{C_1}G_1G_2G_5} \quad (3-47)$$

Al substituir en el diagrama de bloques original estas dos funciones de transferencia, ecuaciones (3-46) y (3-47), se obtiene un nuevo diagrama de bloques reducido, como se ilustra en la figura 3-14. Con dicho diagrama de bloques y la ecuación (3-45) se pueden determinar las funciones de transferencia que se desean:

$$\frac{C(s)}{R(s)} = \frac{\frac{G_{C_1}G_{C_2}G_1G_2G_4}{1 + G_{C_1}G_1G_2G_5}}{1 + \frac{G_{C_1}G_{C_2}G_1G_2G_4G_6}{1 + G_{C_1}G_1G_2G_5}} = \frac{G_{C_1}G_{C_2}G_1G_2G_4}{1 + G_{C_1}G_1G_2G_5 + G_{C_1}G_{C_2}G_1G_2G_4G_6} \quad (3-48)$$

$$\frac{C(s)}{L(s)} = \frac{\frac{G_3G_4}{1 + G_{C_1}G_1G_2G_5}}{1 + \frac{G_{C_1}G_{C_2}G_1G_2G_4G_6}{1 + G_{C_1}G_1G_2G_5}} = \frac{G_3G_4}{1 + G_{C_1}G_1G_2G_5 + G_{C_1}G_{C_2}G_1G_2G_4G_6}$$

**Ejemplo 3-5.** A partir del diagrama de bloques de la figura 3-15, determínense las funciones de transferencia $C(s)/R(s)$ y $C(s)/L(s)$.

La primera función de transferencia que se requiere, $C(s)/R(s)$, se puede determinar fácilmente, ya que sólo existe una trayectoria hacia adelante entre las dos variables implicadas:

$$\frac{C(s)}{R(s)} = \frac{G_CG_1G_2G_3}{1 + G_CG_1G_2G_3G_6}$$

Para obtener la segunda función de transferencia es necesario percatarse de que existen dos trayectorias hacia adelante entre $L(s)$ y $C(s)$. Mediante el uso de la ecuación (3-45) se obtiene:

$$\frac{C(s)}{L(s)} = \frac{(G_4 - G_6G_1G_2)G_3}{1 + G_CG_1G_2G_3G_6}$$

Una recomendación útil es escribir cerca de cada flecha las unidades de la variable de proceso o señal de control a la que representa la flecha; si se hace esto, entonces es bastante simple reconocer las unidades de la ganancia en un bloque, las cuales son las unidades de la flecha de salida sobre las unidades de la flecha de entrada. Con este procedimiento también se evita la sumatoria algebraica de flechas con diferentes unidades.

Como se mencionó al principio de esta sección, los diagramas de bloques son una herramienta muy útil en el control de proceso; se aprenderá y practicará más acerca de la lógica y el trazado de los mismos conforme se avance en el estudio de la dinámica y control de proceso. En los capítulos 6, 7 y 8 se utilizan mucho los diagramas de bloques como auxiliares para el análisis y diseño de los sistemas de control.

## 3-4. TIEMPO MUERTO

Considérese el proceso que se muestra en la figura 3-16, que es esencialmente el mismo de la figura 3-1, la diferencia consiste en que, en este caso, lo que interesa es conocer cómo responde $T_1(t)$ a los cambios en la temperatura de entrada y ambiente.

Se hacen las siguientes suposiciones acerca del conducto de salida entre el tanque y el punto 1: Primera, el conducto está bien aislado; segunda, el flujo del líquido a través del conducto es altamente turbulento (flujo de acoplamiento), de tal manera que básicamente no hay mezcla de retorno en el líquido.

Bajo estas suposiciones, la respuesta de $T_1(t)$ a los disturbios $T_i(t)$ será la misma que $T(t)$, con la excepción de que tiene un retardo de cierto intervalo de tiempo, es decir, existe un lapso finito entre la respuesta de $T(t)$ y la respuesta de $T_1(t)$, lo cual se ilustra gráficamente en la figura 3-17, para un cambio en escalón de la temperatura de entrada $T_i(t)$. El intervalo entre el momento en que el disturbio entra al proceso y el tiempo en que la temperatura $T_1(t)$ empieza a responder se conoce como **tiempo muerto, retardo de tiempo o retardo de transporte** y se representa mediante el término $t_0$.

En este ejemplo en particular, el tiempo muerto puede calcularse de la siguiente manera:

$$t_0 = \frac{\text{distancia}}{\text{velocidad}} = \frac{L}{q/A_p} = \frac{A_pL}{q} \quad (3-49)$$

donde:
- $t_0$ = tiempo muerto, segundos
- $A_p$ = área transversal del conducto, $m^2$
- $L$ = longitud del conducto, m

El tiempo muerto es parte integral del proceso y, consecuentemente, se debe tomar en cuenta en las funciones de transferencia que relacionan $T_1(t)$ con $T_i(t)$ y $T_s(t)$. La ecuación (2-9) expresa que la transformada de Laplace de una función con retardo es igual al producto de la transformada de Laplace de la función, sin retardo, por el término $e^{-t_0s}$. El término $e^{-t_0s}$ es la transformada de Laplace del puro tiempo muerto y, por tanto, si lo que interesa es la respuesta de $T_1(t)$ a los cambios en $T_i(t)$ y $T_s(t)$, se deben multiplicar las funciones de transferencia, ecuaciones (3-24) y (3-25), por $e^{-t_0s}$:

$$\frac{T_1(s)}{T_i(s)} = \frac{K_1e^{-t_0s}}{\tau s + 1} \quad (3-50)$$

$$\frac{T_1(s)}{T_s(s)} = \frac{K_2e^{-t_0s}}{\tau s + 1} \quad (3-51)$$

En este ejemplo se desarrolla el tiempo muerto a causa del tiempo que toma que el líquido se mueva desde la salida del tanque hasta el punto 1. Sin embargo, en la mayoría de los procesos el tiempo muerto no se define tan fácilmente, generalmente es inherente y se distribuye a lo largo del proceso, es decir, en el tanque, el reactor, la columna, etc.; en tales casos, el valor numérico no se evalúa tan fácilmente como en el presente ejemplo, sino que se requiere un modelo muy detallado o una evaluación empírica. En el capítulo 6 se ilustra la manera de efectuar la evaluación empírica.

En este punto se debe reconocer que el tiempo muerto es otro parámetro que ayuda en la definición de la personalidad del proceso. En la ecuación (3-49) se aprecia que $t_0$ depende de algunas propiedades físicas y características operativas del proceso, como son $K$ y $\tau$. Si cambia cualquier condición del proceso, esa variación se puede reflejar en un cambio de $t_0$.

Antes de concluir esta sección es necesario mencionar que la presencia de una cantidad significativa de tiempo muerto en un proceso, es la peor cosa que le puede ocurrir a un sistema de control; como se verá en los capítulos 6 y 7, el tiempo muerto afecta severamente el funcionamiento de un sistema de control.

## 3-5. NIVEL EN UN PROCESO

Considérese el proceso que se muestra en la figura 3-18, en éste se tiene interés en conocer cómo responde el nivel, $h(t)$, del líquido en el tanque a los cambios en el flujo de entrada, $q_i(t)$, y a los cambios en la apertura de la válvula de salida, $vp(t)$.

Como se verá en el capítulo 5, el flujo de líquido a través de una válvula está dado por:

$$q(t) = C_v(vp(t))\sqrt{\frac{\Delta P(t)}{G}}$$

donde:
- $q(t)$ = flujo, gpm
- $C_v$ = coeficiente de la válvula, $gpm/(psi)^{1/2}$
- $vp(t)$ = posición de la válvula. Este término representa la fracción de apertura de la válvula; si su valor es 0, eso indica que la válvula está cerrada; si su valor es 1, indica que la válvula está completamente abierta.
- $\Delta P(t)$ = caída de presión a través de la válvula, psi
- $G$ = gravedad específica del líquido que fluye a través de la válvula, sin dimensiones

Para este proceso, la caída de presión a través de la válvula está dada por:

$$\Delta P(t) = P + \frac{\rho gh(t)}{144g_c} - P_2$$

donde:
- $P$ = presión sobre el líquido, psia
- $\rho$ = densidad del líquido, $lb_m/pies^3$
- $g$ = aceleración debida a la gravedad, 32.2 pies/seg$^2$
- $g_c$ = factor de conversión, 32.2 $lb_m-pies/lb_f-seg^2$
- $h(t)$ = nivel en el tanque, pies
- $P_2$ = presión de salida de la válvula hacia adelante, psia

En esta ecuación se supone que las pérdidas por fricción a lo largo del conducto que va del tanque a la válvula son despreciables.

La relación que se desea es posible obtenerla a partir de un balance de masa de estado dinámico alrededor del tanque:

$$\frac{\rho q_i(t)}{7.48} - \frac{\rho q_o(t)}{7.48} = \frac{dm(t)}{dt}$$

o:

$$\frac{\rho q_i(t)}{7.48} - \frac{\rho q_o(t)}{7.48} = A\rho\frac{dh(t)}{dt}$$

donde:
- $A$ = área transversal del tanque, $pies^2$
- $7.48$ = factor de conversión de gal a $pies^3$

Si se supone que la densidad de entrada es igual a la densidad de salida, se tiene:

$$q_i(t) - q_o(t) = 7.48A\frac{dh(t)}{dt} \quad (3-52)$$

Ahora se tiene una ecuación con dos incógnitas y, por tanto, se debe encontrar otra ecuación independiente para describir el proceso; la de la válvula proporciona la otra ecuación que se requiere:

$$q_o(t) = C_v(vp(t))\sqrt{\left(P + \frac{\rho gh(t)}{144g_c} - P_2\right)} \quad (3-53)$$

Con este sistema de ecuaciones, (3-52) y (3-53), se describe al proceso. Para simplificar esta descripción se puede substituir la ecuación (3-53) en la (3-52):

$$q_i(t) - C_v(vp(t))\sqrt{\left(P + \frac{\rho gh(t)}{144g_c} - P_2\right)} = 7.48A\frac{dh(t)}{dt} \quad (3-54)$$

No es posible resolver esta ecuación de manera analítica, a causa de la naturaleza no lineal del segundo término en el lado izquierdo de la misma. La única forma de resolverla analíticamente es linealizando el término no lineal; la otra única manera de resolverla es mediante métodos numéricos (solución por computadora).

En el capítulo 2 se describió la manera de linealizar los términos no lineales mediante la utilización de la expansión de series de Taylor. A continuación se aplica esta técnica para linealizar el término no lineal de la ecuación (3-54). Puesto que este término se debe linealizar respecto a $h$ y $vp$, la linealización se debe hacer alrededor de los valores $\bar{h}$ y $\bar{vp}$, que son los valores nominales de estado estacionario:

$$q_o(t) \approx \bar{q}_o + \frac{\partial q_o}{\partial vp}\bigg|_{ss}\{vp(t) - \bar{vp}\} + \frac{\partial q_o}{\partial h}\bigg|_{ss}(h(t) - \bar{h})$$

Para simplificar la notación, sea:

$$C_1 = C_v\sqrt{\frac{P + \frac{\rho g\bar{h}}{144g_c} - P_2}{G}} \quad (3-55)$$

$$C_2 = \frac{C_v\rho g\bar{vp}}{288Gg_c}\left[\frac{P + \frac{\rho g\bar{h}}{144g_c} - P_2}{G}\right]^{-1/2} \quad (3-56)$$

de manera que:

$$q_o(t) = \bar{q}_o + C_1(vp(t) - \bar{vp}) + C_2(h(t) - \bar{h}) \quad (3-57)$$

Al substituir esta última ecuación en la ecuación (3-54), se obtiene una ecuación diferencial lineal:

$$q_i(t) - \bar{q}_o - C_1(vp(t) - \bar{vp}) - C_2(h(t) - \bar{h}) = 7.48A\frac{dh(t)}{dt} \quad (3-58)$$

No se debe perder de vista el hecho de que, como se explicó en el capítulo 2, ésta es una versión linealizada de la ecuación (3-54). Como se explicó en la sección 2-2, con la ecuación (3-58) se pueden obtener soluciones precisas alrededor del punto de linealización, $\bar{h}$ y $\bar{vp}$; fuera de un cierto rango alrededor de este punto, termina la linealización, lo cual da lugar a resultados erróneos.

Ahora que se tiene una ecuación diferencial lineal, se pueden obtener las funciones de transferencia que se desean, para lo cual se continúa con el proceso anterior. Al escribir el balance de masa de estado estacionario alrededor del tanque se ve que:

$$\rho\bar{q}_i - \rho\bar{q}_o = 0$$
o:
$$\bar{q}_i - \bar{q}_o = 0$$

Al substraer esta ecuación de la (3-58) se obtiene:

$$(q_i(t) - \bar{q}_i) - C_1(vp(t) - \bar{vp}) - C_2(h(t) - \bar{h}) = 7.48A\frac{d(h(t) - \bar{h})}{dt}$$

Y se definen las siguientes variables de desviación:

$$Q_i(t) = q_i(t) - \bar{q}_i$$
$$VP(t) = vp(t) - \bar{vp}$$
$$H(t) = h(t) - \bar{h}$$

Se substituyen estas variables de desviación en la ecuación diferencial linealizada:

$$Q_i(t) - C_1VP(t) - C_2H(t) = 7.48A\frac{dH(t)}{dt} \quad (3-59)$$

y, al reordenar esta ecuación algebraicamente, se tiene:

$$\tau\frac{dH(t)}{dt} + H(t) = K_1Q_i(t) - K_2VP(t)$$

donde:
$$\tau = 7.48A/C_2, \text{ minutos}$$
$$K_1 = 1/C_2, \text{ pies/gpm}$$
$$K_2 = C_1/C_2, \text{ pies/posición de la válvula}$$

Finalmente se obtiene la transformada de Laplace:

$$H(s) = \frac{K_1}{\tau s + 1}Q_i(s) - \frac{K_2}{\tau s + 1}VP(s)$$

a partir de la cual se obtienen las dos funciones de transferencia:

$$\frac{H(s)}{Q_i(s)} = \frac{K_1}{\tau s + 1} \quad (3-60)$$

y:

$$\frac{H(s)}{VP(s)} = \frac{-K_2}{\tau s + 1}$$

El lector debe comprobar por sí mismo que las unidades de la constante de tiempo y las ganancias son las correctas; también debe recordar el significado de estos tres parámetros; $K_1$ es la ganancia o sensibilidad de $Q_i(t)$ en relación a $H(t)$, lo cual da la cantidad de cambio del nivel en el tanque por unidad de cambio de flujo de entrada al tanque. El cambio tiene lugar mientras se mantiene una apertura constante en la válvula de salida; $K_2$ proporciona la cantidad de cambio de nivel en el tanque por unidad de cambio en la posición de la válvula. Nótese que el signo de la ganancia es negativo, lo cual indica que, conforme la posición de la válvula cambia positivamente y se abre la misma, el nivel cambia negativamente o cae, lo cual tiene sentido físicamente.

En la figura 3-19 se muestra el diagrama de bloques de este proceso. En este ejemplo se eligió hacer la linealización del término no lineal alrededor de los valores $\bar{h}$ y $\bar{vp}$, los cuales son los valores nominales de estado estacionario y forman parte de las expresiones de las ganancias y la constante de tiempo; si se elige un valor diferente del estado estacionario para la linealización, supóngase $\bar{h}_1$ y $\bar{vp}_1$, los valores numéricos de las ganancias y la constante de tiempo son diferentes. Esto indica la no linealidad del proceso, los parámetros que describen la "personalidad" del proceso son funciones del nivel de operación o condiciones de operación, lo cual difiere de lo que ocurre en los sistemas lineales, en los cuales estos parámetros son constantes, sobre todo el rango de operación. El hecho de que la mayoría de los procesos sean no lineales por naturaleza es muy importante en el control de proceso; mientras más alineal es un proceso, más difícil es su control. Por el momento es importante comprender el significado de las alinealidades, de dónde provienen y en qué forma afectan la personalidad del proceso.

## 3-6. REACTOR QUÍMICO

El reactor químico es el ejemplo típico de un proceso altamente no lineal. Considérese el reactor que se muestra en la figura 3-20. El reactor es un recipiente en el que ocurre la "muy conocida" y "altamente exotérmica" reacción $A \rightarrow B$; para eliminar el calor de la reacción, se rodea al reactor con un forro en el que se obtiene vapor saturado a partir de líquido saturado. Se puede suponer que la temperatura del forro, $T_s$, es constante, que el forro está bien aislado, que los reactivos y los productos son líquidos y, sus densidades y capacidades caloríficas no varían mucho con la temperatura o la composición.

La tasa de reacción está dada por la siguiente expresión:

$$r_A(t) = k_0e^{-E/RT(t)}c_A(t), \frac{lb\ mol\ producidos\ de\ A}{pies^3\cdot min}$$

El factor de frecuencia $k_0$, y la energía de activación, $E$, son constantes específicas para cada reacción; se considera que el calor de reacción es constante y se expresa por $\Delta H_r$ en Btu/lb mol de A, después de reaccionar.

Se tiene interés en conocer el efecto de los cambios en la concentración de entrada de A, $c_{A_i}(t)$, y de la temperatura de entrada, $T_i(t)$, sobre la concentración de salida de A, $c_A(t)$.

Al escribir el balance molar de estado dinámico para el reactor, se tiene:

$$qc_{A_i}(t) - Vr_A(t) - qc_A(t) = V\frac{dc_A(t)}{dt} \quad (3-62)$$

donde $V$ = volumen del reactor, $pies^3$.

De la tasa de reacción se obtiene otra relación:

$$r_A(t) = k_0e^{-E/RT(t)}c_A(t) \quad (3-63)$$

Aún falta una ecuación independiente para describir completamente este proceso, la relación debe involucrar a la temperatura de reacción. La relación que se requiere es un balance de energía para el reactor:

$$q\rho C_pT_i(t) - Vr_A(t)(\Delta H_r) - UA(T(t) - T_s) - q\rho C_pT(t) = V\rho C_v\frac{dT(t)}{dt} \quad (3-64)$$

donde:
- $\rho$ = densidad de los productos y los reactivos, se supone constante, $lb_m/pies^3$
- $C_p$ = capacidad calorífica a presión constante de los productos y los reactivos, se supone constante, Btu/lb$_m$-°R
- $C_v$ = capacidad calorífica a volumen constante, se supone constante, Btu/lb$_m$-°R
- $U$ = coeficiente global de transferencia de calor, se supone constante, Btu/°R-pies$^2$-min
- $A$ = área de transferencia de calor, pies$^2$
- $\Delta H_r$ = calor de reacción, se supone constante, -Btu/lb mol de reacción de A
- $T_s$ = temperatura del vapor saturado, °R

Las ecuaciones (3-62), (3-63) y (3-64) describen el reactor químico. Este sistema de ecuaciones es completamente alineal, principalmente la ecuación (3-63) y, nuevamente, la solución de las mismas se puede obtener mediante métodos numéricos o mediante la linealización del término no lineal, de manera que se pueda obtener una solución analítica aproximada. A continuación se usa el último método para determinar las funciones de transferencia que se desean.

Al linealizar la ecuación (3-63) alrededor de las condiciones de operación $\bar{T}$ y $\bar{c}_A$, se tiene:

$$r_A(t) = \bar{r}_A + C_1T(t) + C_2C_A(t) \quad (3-65)$$

donde:
$$\bar{r}_A = k_0e^{-E/R\bar{T}}\bar{c}_A$$
$$C_1 = \frac{\partial r_A(t)}{\partial T(t)}\bigg|_{ss} = \frac{k_0E\bar{c}_A}{R\bar{T}^2}e^{-E/R\bar{T}}$$
$$C_2 = \frac{\partial r_A(t)}{\partial C_A(t)}\bigg|_{ss} = k_0e^{-E/R\bar{T}}$$

Y:
$$T(t) = T(t) - \bar{T}$$
$$C_A(t) = c_A(t) - \bar{c}_A$$

Al substituir la ecuación (3-65) en las ecuaciones (3-62) y (3-64), se obtienen dos ecuaciones diferenciales lineales con dos incógnitas:

$$qc_{A_i}(t) - V\bar{r}_A - VC_1T(t) - VC_2C_A(t) - qc_A(t) = V\frac{dc_A(t)}{dt} \quad (3-66)$$

Y:

$$q\rho C_pT_i(t) - V(\Delta H_r)\bar{r}_A - V(\Delta H_r)C_1T(t) - V(\Delta H_r)C_2C_A(t)$$
$$- UA(T(t) - T_s) - q\rho C_pT(t) = V\rho C_v\frac{dT(t)}{dt} \quad (3-67)$$

Se usa el método descrito en los ejemplos anteriores para obtener las dos ecuaciones diferenciales en términos de las variables de desviación:

$$qC_{A_i}(t) - VC_1T(t) - VC_2C_A(t) - qC_A(t) = V\frac{dC_A(t)}{dt} \quad (3-68)$$

Y:

$$q\rho C_pT_i(t) - V(\Delta H_r)C_1T(t) - V(\Delta H_r)C_2C_A(t) - UAT(t) - q\rho C_pT(t) = V\rho C_v\frac{dT(t)}{dt} \quad (3-69)$$

Al reordenar las ecuaciones (3-68) y (3-69) algebraicamente, se tiene:

$$\tau_1\frac{dC_A(t)}{dt} + C_A(t) = K_1C_{A_i}(t) - K_2T(t) \quad (3-70)$$

$$\tau_2\frac{dT(t)}{dt} + T(t) = K_3T_i(t) - K_4C_A(t) \quad (3-71)$$

donde:
$$\tau_1 = \frac{V}{VC_2 + q}, \text{ minutos}$$
$$K_1 = \frac{q}{VC_2 + q}, \text{ sin dimensiones}$$
$$K_2 = \frac{VC_1}{VC_2 + q}, \text{ lb mol de A}$$
$$\tau_2 = \frac{V\rho C_v}{V(\Delta H_r)C_1 + UA + q\rho C_p}, \text{ minutos}$$
$$K_3 = \frac{q\rho C_p}{V(\Delta H_r)C_1 + UA + q\rho C_p}, \text{ sin dimensiones}$$
$$K_4 = \frac{V(\Delta H_r)C_2}{V(\Delta H_r)C_1 + UA + q\rho C_p}, \text{ lb mol de A}$$

De la obtención de la transformada de Laplace de las ecuaciones (3-70) y (3-71), se tiene:

$$C_A(s) = \frac{K_1}{\tau_1s + 1}C_{A_i}(s) - \frac{K_2}{\tau_1s + 1}T(s) \quad (3-72)$$

Y:

$$T(s) = \frac{K_3}{\tau_2s + 1}T_i(s) - \frac{K_4}{\tau_2s + 1}C_A(s) \quad (3-73)$$

En la figura 3-21 se ilustra la representación de bloques de este proceso.

En este proceso de reacción se tiene una nueva característica que no se vio antes. Se trata del primer ejemplo en que existe interacción entre dos variables; se dice que estas dos variables, la concentración de salida, $C_A(t)$, y la temperatura de salida, $T(t)$, están "acopladas" y cualquier perturbación que afecte a una, afecta a la otra. Por ejemplo, si cambia la temperatura de entrada de los reactivos, esto afecta a la temperatura de salida, a través de la función de transferencia:

$$\frac{T(s)}{T_i(s)} = \frac{K_3}{\tau_2s + 1}$$

Pero si la temperatura de salida cambia, esto afecta también a la concentración de salida, a través de la función de transferencia:

$$\frac{C_A(s)}{T(s)} = \frac{K_2}{\tau_1s + 1}$$

Los procesos en que ocurre esto se conocen como **interactivos**, y el control de ambas variables representa un desafío muy interesante para el ingeniero de proceso o control.

Como en el ejemplo anterior, en éste se debe notar que las ganancias y la constante de tiempo dependen del punto de linealización y, en consecuencia, no son constantes sobre todo el rango, debido a la característica no lineal del proceso.

Antes de concluir este ejemplo, el lector debe verificar las unidades y los signos de las ganancias y las constantes de tiempo, ya que, como se mencionó en un ejemplo anterior, esto puede ayudar en la revisión del desarrollo del modelo antes de llegar a la solución.

## 3-7. RESPUESTA DEL PROCESO DE PRIMER ORDEN A DIFERENTES TIPOS DE FUNCIONES DE FORZAMIENTO

Ya se vio que la función de transferencia de un proceso de primer orden sin tiempo muerto es de la forma:

$$G(s) = \frac{Y(s)}{X(s)} = \frac{K}{\tau s + 1}$$

donde:
- $Y(s)$ = transformada de la variable de salida
- $X(s)$ = transformada de la función de forzamiento o variable de entrada

En esta sección se estudiará la respuesta de este tipo de proceso a diferentes tipos de funciones de forzamiento, que son las más comunes en el estudio del control automático de proceso.

### Función escalón

Un cambio en escalón de $A$ unidades de magnitud en la función de forzamiento se expresa en el dominio del tiempo como:

$$X(t) = Au(t) \quad (3-74)$$

y en el dominio de Laplace como:

$$X(s) = \frac{A}{s}$$

Entonces:

$$Y(s) = \frac{KA}{s(\tau s + 1)}$$

Al regresar esta función al dominio del tiempo, se obtiene:

$$Y(t) = KA(1 - e^{-t/\tau}) \quad (3-75)$$

La respuesta se ilustra gráficamente en la figura 3-2. Como se vio en la sección 3-1, en una constante de tiempo la respuesta alcanza el 63.2% del cambio total. La constante de tiempo $\tau$ es el tiempo que tarda la respuesta en alcanzar el 63.2% de su valor final.

### Función rampa

Supóngase que la función de forzamiento del proceso es una función rampa, tal que:

$$X(t) = Atu(t) \quad (3-76)$$

Esto, en el dominio de Laplace, es:

$$X(s) = \frac{A}{s^2}$$

Entonces:

$$Y(s) = \frac{KA}{s^2(\tau s + 1)}$$

Al regresar esta función al dominio del tiempo, se obtiene:

$$Y(t) = KA(t - \tau + \tau e^{-t/\tau}) \quad (3-77)$$

En la figura 3-23 se ilustran gráficamente la función de forzamiento y la variable de respuesta; conforme se incrementa el tiempo, los transitorios desaparecen, $e^{-t/\tau}$ se vuelve despreciable y la respuesta se convierte también en una rampa, esto es:

$$Y(t)\big|_{t \to \infty} = KA(t - \tau) \quad (3-78)$$

### Función senoidal

Supóngase que la función de forzamiento del proceso es una función seno, tal que:

$$X(t) = A\sin \omega t \, u(t) \quad (3-79)$$

Esto, en el dominio de Laplace, es:

$$X(s) = \frac{A\omega}{s^2 + \omega^2}$$

Entonces:

$$Y(s) = \frac{KA\omega}{(\tau s + 1)(s^2 + \omega^2)}$$

Al regresar esta función al dominio del tiempo, se obtiene:

$$Y(t) = \frac{KA\omega\tau}{\tau^2\omega^2 + 1}e^{-t/\tau} + \frac{KA}{\sqrt{\tau^2\omega^2 + 1}}\sin(\omega t + \theta) \quad (3-80)$$

donde:
$$\theta = -\tan^{-1}(\omega\tau)$$

## 3-8. RESUMEN

En este capítulo se presentaron los principios básicos para el desarrollo de modelos de proceso simples, que son la base para el análisis y diseño de sistemas de control. Se desarrollaron modelos de varios procesos típicos: proceso térmico, proceso de un gas, nivel en un proceso y reactor químico.

Los conceptos más importantes que se cubrieron son:

1. **Función de transferencia**: relación entre la transformada de Laplace de la variable de salida y la transformada de Laplace de la variable de entrada.

2. **Procesos de primer orden**: se describen mediante funciones de transferencia de la forma:
$$G(s) = \frac{K e^{-t_0s}}{\tau s + 1}$$

3. **Parámetros de la personalidad del proceso**:
   - **Ganancia ($K$)**: indica cuánto cambia la variable de salida por unidad de cambio en la variable de entrada.
   - **Constante de tiempo ($\tau$)**: tiempo requerido para alcanzar el 63.2% del cambio total.
   - **Tiempo muerto ($t_0$)**: tiempo entre la aplicación de la función de forzamiento y el inicio de la respuesta del proceso.

4. **Variables de desviación**: simplifican el análisis al eliminar los términos constantes de las ecuaciones linealizadas.

5. **Linealización**: permite aproximar ecuaciones no lineales mediante expansiones de series de Taylor truncadas.

6. **Diagramas de bloques**: herramienta gráfica para representar funciones de transferencia y analizar sistemas de control.

7. **Principio de superposición**: la respuesta total de un sistema lineal es la suma de las respuestas individuales a cada entrada.

8. **Sistemas interactivos**: procesos donde las variables están acopladas, de manera que una perturbación en una variable afecta a las otras.

9. **Respuesta a diferentes funciones de forzamiento**: escalón, rampa y senoidal.

Es importante recordar que los parámetros $K$, $\tau$ y $t_0$ definen la "personalidad" del proceso y están en función de los parámetros físicos del proceso. En un sistema lineal estos parámetros son constantes sobre todo el rango de operación; en los procesos no lineales, estos parámetros son funciones de la condición de operación y, en consecuencia, no son constantes.

## PROBLEMAS

**3-1.** Considérese el proceso de mezclado que se ilustra en la figura 3-25, donde se supone que la densidad de la corriente de entrada y la de salida son muy similares y que las tasas de flujo $F_1$ y $F_2$ son constantes. Obténganse las funciones de transferencia que relacionan la concentración a la salida con cada concentración a la entrada; se deben indicar las unidades de todas las ganancias y las constantes de tiempo.

**3-2.** Considérese el reactor isotérmico que se muestra en la figura 3-26, donde la tasa de reacción se expresa mediante:

$$r_A(t) = kC_A(t), \text{ mol de A/pies}^3\text{-min}$$

donde $k$ es una constante.

Se supone que la densidad y todas las otras propiedades físicas de los productos y los reactivos son semejantes, también se puede suponer que el régimen de flujo entre los puntos 2 y 3 es muy turbulento (flujo de acoplamiento), con lo que se minimiza la mezcla hacia atrás.

Obténganse las funciones de transferencia que relacionan:

a) La concentración de A en 2 con la de A en 1.
b) La concentración de A en 3 con la de A en 2.
c) La concentración de A en 3 con la de A en 1.

**3-3.** Considérese el proceso mostrado en la figura 3-27, en el cual el tanque es esférico con un radio de 4 pies; el flujo nominal de entrada y de salida del tanque es de 30,000 lbm/hr; la densidad del líquido es de 70 lbm/pies$^3$; y el nivel de estado estacionario es de 5 pies. El volumen de una esfera es $4\pi r^3/3$, y la relación entre volumen y altura se expresa mediante:

$$V(t) = V_T\left[\frac{h^2(t)(3r - h(t))}{4r^3}\right]$$

El flujo a través de las válvulas es:

$$w(t) = 500C_vp(t)\sqrt{G_f\Delta p}$$

donde:
- $r$ = radio de la esfera, pies
- $V(t)$ = volumen del líquido en el tanque, pies$^3$
- $V_T$ = volumen total del tanque, pies$^3$
- $h(t)$ = altura del líquido en el tanque, pies
- $w(t)$ = tasa de flujo, lbm/hr
- $C_v$ = coeficiente de la válvula, gpm/psi$^{1/2}$
- $C_{v1} = 20.2$ y $C_{v2} = 28.0$
- $\Delta p$ = caída de presión a través de la válvula, psi
- $G_f$ = gravedad específica del fluido
- $vp(t)$ = posición de la válvula, fracción de apertura de la válvula

La presión sobre el nivel del líquido se mantiene al valor constante de 50 psig. Obténganse las funciones de transferencia que relacionan el nivel del líquido en el tanque con los cambios de posiciones de las válvulas 1 y 2. También se deben graficar las ganancias y las constantes de tiempo contra los diferentes niveles de operación cuando se mantiene constante la posición de las válvulas.

**3-4.** Considérese el tanque de calentamiento que se muestra en la figura 3-28. El fluido que se procesa se calienta en el tanque mediante un agente calefactor que fluye a través de los tubos; la tasa de transferencia de calor, $q(t)$, al fluido que se procesa se relaciona con la señal neumática, $m(t)$, mediante la expresión:

$$q(t) = a + b(m(t) - 9)$$

Se puede suponer que el proceso es adiabático, que el fluido se mezcla bien en el tanque y que la capacidad calorífica y la densidad del fluido son constantes. Obténganse las funciones de transferencia que relacionan la temperatura de salida del fluido con la de entrada, $T_i(t)$, la tasa de flujo del proceso, $F(t)$, y la señal neumática, $m(t)$. Se debe dibujar también el diagrama de bloques completo para este proceso.

**3-5.** Considérese el proceso de mezclado que se muestra en la figura 3-29. La finalidad de este proceso es combinar una corriente baja en contenido del componente A con otra corriente de A puro; la densidad de la corriente 1, $\rho_1$, se puede considerar constante, ya que la cantidad de A en esta corriente es pequeña. Naturalmente, la densidad de la corriente de salida es una función de la concentración y se expresa mediante:

$$\rho_3(t) = a_3 + b_3C_{A_3}(t)$$

El flujo a través de la válvula 1 está dado por:

$$F_1(t) = C_{v1}vp_1(t)\sqrt{\frac{\Delta p_1}{G_1}}$$

El flujo a través de la válvula 2 está dado por:

$$F_2(t) = C_{v2}vp_2(t)\sqrt{\frac{\Delta p_2}{G_2}}$$

Finalmente, el flujo a través de la válvula 3 está dado por:

$$F_3(t) = C_{v3}\sqrt{\frac{\Delta p_3(t)}{G_3(t)}}$$

La relación entre la posición de la válvula y la señal neumática se expresa con:

$$vp_1(t) = a_1 + b_1(m_1(t) - d_1)$$
$$vp_2(t) = a_2 + b_2(m_2(t) - d_2)$$

donde:
- $a_1, b_1, d_1, a_2, b_2, d_2, a_3, b_3$ = constantes conocidas.
- $C_{v1}, C_{v2}, C_{v3}$ = coeficientes de las válvulas 1, 2 y 3 respectivamente, $m^3/(s-psi^{1/2})$
- $vp_1(t), vp_2(t)$ = posición de las válvulas 1 y 2 respectivamente, fracción sin dimensiones
- $\Delta p_1, \Delta p_2$ = caída de presión a través de las válvulas 1 y 2, respectivamente, la cual es constante, psi
- $\Delta p_3(t)$ = caída de presión a través de la válvula 3, psi
- $G_1, G_2$ = gravedad específica de las corrientes 1 y 2, respectivamente, la cual es constante y sin dimensiones
- $G_3(t)$ = gravedad específica de la corriente 3, sin dimensiones

Se debe desarrollar el diagrama de bloques para este proceso; en él deben aparecer todas las funciones de transferencia y la forma en que las funciones de transferencia $m_1(t)$, $m_2(t)$ y $C_{A_1}(t)$ afectan a las variables de respuesta $h(t)$ y $C_{A_3}(t)$.

**3-6.** Determínese la función de transferencia $C(s)/R(s)$ para el sistema que se muestra en la figura 3-30.

**3-7.** Determínese la función de transferencia $C(s)/L(s)$ para el sistema que se muestra en la figura 3-31.

**3-8.** Determínese la función de transferencia $C(s)/R(s)$ para el sistema que se muestra en la figura 3-32.

**3-9.** Obténgase la respuesta de un proceso que se describe mediante la función de transferencia de primer orden, más tiempo muerto, a la función de forzamiento que se ilustra en la figura 3-33.

**3-10.** Supóngase que con la siguiente ecuación se describe un cierto proceso:

$$\frac{Y(s)}{X(s)} = \frac{3e^{-0.5s}}{5s + 0.2}$$

a) Obténgase la ganancia de estado estacionario, la constante de tiempo y el tiempo muerto para este proceso.
b) La condición inicial de la variable $y$ es $y(0) = 2$. ¿Cuál es el valor final de $y(t)$ para la función de forzamiento que se muestra en la figura 3-34?

**3-11.** Considérese el reactor químico que se muestra en la figura 3-35; en éste tiene lugar una reacción endotérmica del tipo $A + 2B \rightarrow C$. La tasa de incidencia de A, en $kmol/m^3\cdot s$, se expresa mediante:

$$r_A(t) = -k_0e^{-E/RT(t)}C_A(t)C_B(t)$$

donde:
- $r_A(t)$ = tasa de reacción, $kmol/m^3\cdot s$
- $k_0$ = factor de frecuencia, constante, $m^3/kmol\cdot s$
- $E$ = energía de activación, constante, cal/gmol
- $R$ = constante de los gases, 1.987 cal/gmol-K

La entrada de calor al reactor se relaciona con la señal neumática que llega al calefactor mediante:

$$q(t) = r + s(m_1(t) - 9)$$

donde:
- $q(t)$ = entrada de calor al reactor, J/s
- $s, r$ = constantes

El flujo de B puro a través de la válvula está dado por:

$$F_2(t) = C_{v2}vp_2(t)\sqrt{\frac{\Delta p_2}{G_2}}$$

donde:
- $C_{v2}$ = coeficiente de la válvula, constante, $m^3/s-psi^{1/2}$
- $\Delta p_2$ = caída de presión a través de la válvula, constante, psi
- $G_2$ = gravedad específica de B, constante, sin dimensiones
- $vp_2(t)$ = posición de la válvula, es una fracción

Se puede suponer que la operación es adiabática y que las propiedades físicas de los reactivos y los productos son similares. Se supone que la tasa de flujo $F_1$ es constante.

Se debe desarrollar el diagrama de bloques con todas las funciones de transferencia, para mostrar gráficamente las interacciones de las funciones de forzamiento $m_1(t)$, $m_2(t)$, $C_{A_1}(t)$ y $T_1(t)$ con las variables de respuesta $C_A(t)$, $C_B(t)$ y $T(t)$. Se deben anotar las unidades de todas las ganancias y constantes de tiempo.

**3-12.** Obténgase la respuesta del proceso que se describe mediante una función de transferencia de primer orden a una función de forzamiento impulso.

---

*Continúa en la Parte 2: Capítulos 4-9 y Apéndices*
