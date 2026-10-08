# Fundamentos de Instrumentación

> **Parte 01 de ~10 · Cubre: portada, índices, prólogo, Capítulo 1 y Capítulo 2 (páginas impresas i–xviii y 1–46 · páginas PDF 1–64).**
> Convención de páginas en los JSON: `page` = número impreso en el libro; `pdf_page` = página del archivo PDF (`pdf_page = page + 20` en el cuerpo del libro).
> Convención de IDs: `table-NNN`, `chart-NNN`, `image-NNN`, `diagram-NNN`, numeración continua entre partes (la Parte 02 continúa en `table-008`, `chart-015`, `image-002`, `diagram-014`).
> Leyenda de origen: texto sin marca = contenido extraído del documento (redactado de forma concisa, sin cambiar cifras); bloques marcados **«Síntesis propia»** = contenido generado por el modelo; **«Observación de fidelidad»** = discrepancia detectada en el documento original, conservada sin corregir.

```json
{
  "type": "document_metadata",
  "id": "meta-001",
  "title": "Fundamentos de Instrumentación",
  "author": "Luis Enrique Avendaño M. Sc.",
  "institution": "Universidad Tecnológica de Pereira",
  "language": "es",
  "pdf_title_metadata": "libins2.dvi",
  "pdf_pages": 279,
  "pdf_creation_date": "2006-08-24",
  "document_type": "libro de texto universitario (ingeniería / instrumentación y medida)",
  "text_layer": true,
  "scanned": false,
  "parts_plan": [
    {"part": 1, "content": "Portada, índices, prólogo, Cap. 1 y Cap. 2", "pdf_pages": "1-64"},
    {"part": 2, "content": "Cap. 3 Características dinámicas", "pdf_pages": "65-112 (aprox.)"},
    {"part": 3, "content": "Cap. 4 Análisis estadístico", "pdf_pages": "113-152 (aprox.)"},
    {"part": 4, "content": "Cap. 5 Incertidumbre y Cap. 6 Sensores de parámetro variable (inicio)", "pdf_pages": "153-200 (aprox.)"},
    {"part": 5, "content": "Cap. 6 (resto) a Cap. 8, Parte II (Cap. 9-10) y Apéndices A-D", "pdf_pages": "201-279 (aprox., puede subdividirse)"}
  ],
  "note": "El plan de partes es orientativo; los rangos de páginas se confirmarán al generar cada parte."
}
```

---

## Resumen técnico

*(Síntesis propia basada en el índice, el prólogo y los capítulos 1 y 2. Se actualizará conceptualmente al procesar las partes siguientes.)*

«Fundamentos de Instrumentación» es un texto universitario de la Universidad Tecnológica de Pereira que trata la **medición y la instrumentación de la medida** con enfoque interdisciplinario: el diseño de un sistema experimental o de medición involucra a ingenieros de distintas áreas (químicos, mecánicos, eléctricos, de sistemas, civiles, etc.). El libro se organiza en dos partes: **Parte I «Sensórica»** (elementos captadores de señal: sensores primarios y transductores) y **Parte II «Adecuación de la Señal»** (acondicionamiento de la señal para su transferencia a un sistema de cómputo, donde se procesa o visualiza). El prólogo indica que el texto incorpora prácticas de laboratorio y simulaciones con LabView y Matlab, apoyadas en el Laboratorio de Instrumentación de la UTP.

El **Capítulo 1** define la instrumentación (de medida y de control), clasifica los datos según su naturaleza temporal (estáticos, transitorios, dinámicos, aleatorios), compara información analógica y digital, define transductor/sensor (norma ISA S37.1, 1969), distingue transductores de **lazo abierto** y de **lazo cerrado (servotransductores)** y presenta una clasificación de sensores (analógicos directos: de parámetro variable, generadores de señal y mixtos; e indirectos: moduladores/generadores de frecuencia y digitales).

El **Capítulo 2** desarrolla las **características estáticas** de un elemento de medida: rango, alcance, línea recta ideal, no linealidad, sensibilidad, efectos ambientales (entradas modificadoras e interferentes), histéresis, resolución, envejecimiento y bandas de error; propone un **modelo estático generalizado** (θ = ku + a + N(u) + k_M·u_M·u + k_I·u_I); explica la **calibración** y la **rastreabilidad** de patrones (incluida la escala ITS-90); describe un procedimiento experimental de tres pruebas (θ vs u, efectos ambientales, repetibilidad); y analiza la **precisión del sistema completo** y las **técnicas de reducción de error**: aislamiento, sensibilidad ambiental cero, entradas opuestas, sistemas diferenciales, realimentación negativa de alta ganancia y estimación por computador mediante la ecuación inversa del modelo.

Según el índice, el resto del libro cubre: características dinámicas (funciones de transferencia de primer y segundo orden, errores y compensación dinámica, efectos de carga, ruido); análisis estadístico de datos experimentales (probabilidad, distribuciones, estimación de parámetros, regresión); incertidumbre experimental; sensores de parámetro variable (potenciométricos, termorresistivos/RTD/NTC/PTC, fotorresistivos, extensométricos, capacitivos e inductivos, LVDT); sensores generadores (termopares, piezoeléctricos); medida de presión y humedad; el amplificador operacional; confiabilidad; y apéndices sobre polinomios de termocuplas, unidades SI, prefijos y la escala ITS-90.

---

## Portada y datos editoriales

- **Título:** Fundamentos de Instrumentación
- **Autor:** Luis Enrique Avendaño M. Sc.
- **Institución:** Universidad Tecnológica de Pereira
- La página 2 del PDF (ii) está en blanco salvo la numeración.

---

## Índice general (estructura original)

```json
{
  "type": "toc",
  "id": "toc-001",
  "page": "iii-vii",
  "pdf_page": "3-7",
  "parts": [
    {"part": "I", "title": "Sensórica", "page": 1, "chapters": [
      {"n": 1, "title": "Medidas en sistemas físicos", "page": 3, "sections": [
        {"s": "1.1", "title": "Introducción", "page": 3},
        {"s": "1.2", "title": "Naturaleza de los Datos", "page": 5, "subsections": ["1.2.1 Datos Estáticos (5)", "1.2.2 Datos transitorios (6)", "1.2.3 Datos dinámicos (6)", "1.2.4 Datos aleatorios (7)"]},
        {"s": "1.3", "title": "Información analógica e información digital", "page": 8},
        {"s": "1.4", "title": "Sensores primarios", "page": 10, "subsections": ["1.4.1 Aspectos Generales de los Sensores (10)"]},
        {"s": "1.5", "title": "Estructura de un transductor", "page": 11, "subsections": ["1.5.1 Transductores en lazo abierto (13)", "1.5.2 Transductores de lazo cerrado o servotransductores (15)"]},
        {"s": "1.6", "title": "Clasificación", "page": 17}
      ]},
      {"n": 2, "title": "Características estáticas de un sistema de medida", "page": 19, "sections": [
        {"s": "2.1", "title": "Introducción", "page": 19},
        {"s": "2.2", "title": "Características Sistemáticas", "page": 19},
        {"s": "2.3", "title": "Modelo generalizado de un elemento", "page": 27},
        {"s": "2.4", "title": "Identificación de características estáticas. Calibración", "page": 28, "subsections": ["2.4.1 Patrones de medida (28)"]},
        {"s": "2.5", "title": "Medidas experimentales y evaluación de resultados", "page": 34},
        {"s": "2.6", "title": "Precisión de los sistemas de medida en estado estacionario", "page": 36, "subsections": ["2.6.1 Error en la medida de un sistema con elementos ideales (37)", "2.6.2 Técnicas de reducción de error (38)"]}
      ]},
      {"n": 3, "title": "Características dinámicas de los sistemas de medida", "page": 47, "sections": [
        {"s": "3.1", "title": "Introducción", "page": 47},
        {"s": "3.2", "title": "Función de transferencia para elementos típicos del sistema", "page": 47, "subsections": ["3.2.1 Elementos de primer orden (47)", "3.2.2 Elementos de segundo orden (50)"]},
        {"s": "3.3", "title": "Identificación de la dinámica de un elemento", "page": 53, "subsections": ["3.3.1 Respuesta a un escalón de los elementos de primero y de segundo orden (54)", "3.3.2 Respuesta sinusoidal de elementos de primero y segundo orden (58)"]},
        {"s": "3.4", "title": "Errores dinámicos en sistemas de medida", "page": 61},
        {"s": "3.5", "title": "Técnicas de compensación dinámica", "page": 67},
        {"s": "3.6", "title": "Determinación experimental de los parámetros de un sistema de medida", "page": 70},
        {"s": "3.7", "title": "Efectos de la carga en sistemas de medida", "page": 76, "subsections": ["3.7.1 Carga eléctrica (77)", "3.7.2 Circuito equivalente Thévenin (77)", "3.7.3 Ejemplo del cálculo de un circuito equivalente Thévenin (80)", "3.7.4 Circuito equivalente Norton (81)", "3.7.5 Carga Generalizada (83)", "3.7.6 Efectos de la carga bajo condiciones dinámicas (85)"]},
        {"s": "3.8", "title": "Señales y ruido en los sistemas de medida", "page": 88, "subsections": ["3.8.1 Efectos del ruido y la interferencia en los circuitos de medida (89)", "3.8.2 Fuentes de ruido y mecanismos de acople (91)"]}
      ]},
      {"n": 4, "title": "Análisis Estadístico de Datos Experimentales", "page": 93, "note": "Subsecciones 4.1-4.3.9 y 4.4 constan en el índice; la lista continúa en la Parte 03 (4.6.1 Regresión lineal p.121 ... 4.6.5 Software p.131)."},
      {"n": 5, "title": "Incertidumbre Experimental", "page": 133, "sections": [
        {"s": "5.1", "title": "Introducción", "page": 133},
        {"s": "5.2", "title": "Propagación de las Incertidumbres", "page": 133, "subsections": ["5.2.1 Consideraciones de sesgo y precisión (138)"]}
      ]},
      {"n": 6, "title": "Sensores de parámetro variable", "page": 143, "note": "Detalle en la Parte 04/05 (6.2 Potenciométricos p.143; 6.3 Termorresistivos p.160; 6.4 Fotorresistivos p.180; 6.5 Extensométricos p.185; 6.6 Capacitivos e inductivos p.194; 6.7 Transformador, electrodinámicos, servos y resonantes p.194)."},
      {"n": 7, "title": "Sensores generadores de señal", "page": 203, "sections": [
        {"s": "7.1", "title": "Introducción", "page": 203},
        {"s": "7.2", "title": "Termopares", "page": 203, "subsections": ["7.2.1 Efectos termoeléctricos (203)", "7.2.2 Compensación de la unión de referencia (207)"]},
        {"s": "7.3", "title": "Sensores piezoeléctricos", "page": 209}
      ]},
      {"n": 8, "title": "Medida de presión y humedad", "page": 221, "sections": [
        {"s": "8.1", "title": "Introducción", "page": 221},
        {"s": "8.2", "title": "Medida de presión", "page": 221},
        {"s": "8.3", "title": "Dispositivos de medida de presión", "page": 222},
        {"s": "8.4", "title": "Medida de Temperatura", "page": 234}
      ]}
    ]},
    {"part": "II", "title": "Adecuación de la Señal", "page": 235, "chapters": [
      {"n": 9, "title": "El amplificador operacional", "page": 237},
      {"n": 10, "title": "Confiabilidad", "page": 239}
    ]}
  ],
  "appendices": [
    {"id": "A", "title": "Cálculo de funciones polinómicas para termocuplas", "page": 243},
    {"id": "B", "title": "Definiciones de las Unidades Básicas del SI y del Radian y del Steradian", "page": 249},
    {"id": "C", "title": "Prefijos del Sistema Internacional", "page": 253},
    {"id": "D", "title": "Enlace de unidades básicas del SI a constantes atómicas y fundamentales (incluye ITS-90)", "page": 255}
  ],
  "note": "El índice de esta parte resume capítulos y secciones; los detalles de cada capítulo se desarrollan en la parte donde se procesa. En el PDF el índice del capítulo 4 y del capítulo 6 está cortado entre páginas; el resto se completa en las partes correspondientes."
}
```

### Lista de tablas (estructura original)

```json
{
  "type": "list_of_tables",
  "id": "lot-001",
  "page": "xv",
  "pdf_page": 15,
  "items": [
    {"n": "1.1", "title": "Principios de Transducción Física y Química", "page": 12},
    {"n": "1.2", "title": "Sensores analógicos directos", "page": 16},
    {"n": "1.3", "title": "Sensores indirectos", "page": 18},
    {"n": "2.1", "title": "Escala simplificada de rastreabilidad", "page": 29},
    {"n": "2.2", "title": "Escala de rastreabilidad (Adaptada de Scarr)", "page": 30},
    {"n": "2.3", "title": "Puntos fijos definidos en el ITS-90", "page": 31},
    {"n": "2.4", "title": "Efecto de la presión sobre algunos puntos definidos fijos", "page": 33},
    {"n": "4.1", "title": "Resultados de 60 mediciones de la temperatura en un ducto", "page": 95},
    {"n": "4.2", "title": "Medidas de la temperatura arregladas en intervalos", "page": 96},
    {"n": "4.3", "title": "Valores críticos de la distribución t Student", "page": 112},
    {"n": "4.4", "title": "Valores de los coeficientes de Thompson. Según: ANSI/ASME-86", "page": 118},
    {"n": "4.5", "title": "Valores mínimos del coeficiente de correlación para un nivel de significancia a", "page": 132},
    {"n": "4.6", "title": "Obtención de los coeficientes para una parábola de mínimos cuadrados", "page": 132},
    {"n": "6.1", "title": "Tabla de verdad del control de la lógica de entrada", "page": 158},
    {"n": "6.2", "title": "Valores característicos en el potenciómetro digital", "page": 158},
    {"n": "6.3", "title": "Valores característicos en el potenciómetro digital en modo inverso", "page": 160},
    {"n": "6.4", "title": "Comparación de las resistencias NTC y otros sensores", "page": 172},
    {"n": "6.5", "title": "Características de las galgas extensiométricas metálicas y semiconductoras", "page": 193},
    {"n": "B.1", "title": "Unidades SI derivadas con nombres especiales y símbolos", "page": 252}
  ],
  "note": "La Lista de Figuras (págs. ix-xiii) enumera las figuras 1.1 a 8.13 y D.1; cada figura se registra con su ID JSON en el capítulo donde aparece. Algunas entradas de la lista aparecen sin título en el original (3.27, 7.6, 8.10, 8.13, D.1)."
}
```

---

## Prólogo

El prólogo (p. xvii) plantea que la aplicación del computador a la ciencia y la tecnología ha producido herramientas de software y hardware que permiten conocer directamente el comportamiento de los sistemas físicos, y que la **experimentación** es hoy el medio más adecuado para estudiarlo. En ingeniería se requieren experimentos cuidadosamente diseñados para concebir y verificar conceptos teóricos, desarrollar nuevos métodos y productos, construir sistemas cada vez más complejos y evaluar/optimizar los existentes.

Puntos centrales:

- El diseño de un sistema experimental o de medición es una actividad **interdisciplinaria**. Ejemplos del texto: el sistema de control e instrumentación de una planta procesadora (ingenieros químicos, mecánicos, eléctricos y de sistemas) y la instrumentación para medir terremotos y la respuesta dinámica de estructuras (ingenieros civiles, geólogos, electrónicos, de sistemas).
- Los tópicos se seleccionaron para ser útiles en el diseño de **proyectos experimentales interdisciplinarios** de medición e instrumentación.
- **Parte I:** elementos captadores de señal (elementos primarios o sensores). **Parte II:** sistemas de adecuación de la señal para transferirla a un sistema de cómputo donde se procesa o visualiza.
- Se incluye una parte experimental con prácticas de laboratorio y simulación con herramientas en tiempo real (**LabView** y **Matlab**, marcas registradas de National Instruments y Mathworks), apoyadas en el Laboratorio de Instrumentación de la UTP.

---

# Parte I — Sensórica

## Capítulo 1. Medidas en sistemas físicos

### 1.1 Introducción

- **Instrumentación:** conjunto de técnicas, recursos y métodos relacionados con la concepción de dispositivos que mejoran o aumentan la eficacia de los mecanismos de percepción y comunicación del hombre (cita [23] del documento).
- Comprende dos campos: **instrumentación de medida** (atención en el tratamiento de las señales/magnitudes de *entrada*; dispositivos clave: captadores/sensores y transductores) e **instrumentación de control** (atención en las señales de *salida*; dispositivos clave: accionadores/actuadores).
- La Figura 1.1 muestra un posible sistema de control automático de un proceso. Las magnitudes físicas captadas se convierten en señales eléctricas por grupos de captadores (C₁…Cₙ y C′₁…C′ₘ), conectados a amplificadores que dan salidas de nivel adecuado. Las señales se agrupan en dos bloques:
  1. **S₁…Sₙ:** señales que se transmiten individualmente (número pequeño o instrumentación asociada de bajo costo).
  2. **S′₁…S′ₘ:** señales cuyo tratamiento requiere equipos muy costosos o especiales, o cuyo número es muy elevado (ejemplos del texto: temperatura en muchos puntos con un termómetro digital de alta precisión; medida del tiempo con un reloj atómico en centrales eléctricas para conocer el instante y la duración de un fallo en una subestación o planta remota).

```json
{
  "type": "diagram",
  "id": "diagram-001",
  "page": 4,
  "pdf_page": 22,
  "title": "Figura 1.1: Control automático de un proceso",
  "elements": [
    "SISTEMA FÍSICO",
    "Captadores C1, C2, ..., Cn (señales S1...Sn) con bloque 'Acondicionamiento'",
    "Captadores C'1, C'2, ..., C'm (señales S'1...S'm) con bloque 'Amplificadores'",
    "Registro directo",
    "Aparato de medida / Controlador doble",
    "MEM",
    "AGRUPAMIENTO Y TRANSMISIÓN",
    "UNIDAD DE CÁLCULO",
    "SEPARACIÓN",
    "Registro (indirecto)"
  ],
  "relationships": [
    "Sistema físico -> captadores -> acondicionamiento/amplificadores",
    "Señales acondicionadas -> registro directo y -> agrupamiento y transmisión -> unidad de cálculo",
    "Unidad de cálculo -> flujo de retorno -> separación -> canales de registro/medida y canales de accionamiento hacia el sistema físico"
  ],
  "description": "Diagrama de bloques de un sistema de control automático con captadores, acondicionamiento, transmisión, cálculo y retorno de señales de accionamiento. Los rótulos 'Directo' e 'Indirecto' aparecen en el original.",
  "basis": "pie de figura + texto del documento (no verificado visualmente al detalle)"
}
```

- **Acondicionamiento / Amplificadores:** dispositivos que normalizan las señales a un formato compatible con el sistema de transmisión (pueden incluir filtros, atenuadores, convertidores A/D, etc.). Es frecuente tener señales normalizadas en forma analógica (mismo campo de variación) y digital (mismo número de bits).
- **Registro directo:** posibilidad de registrar magnitudes antes de su transmisión conjunta a una unidad de cálculo.
- **Agrupamiento y transmisión:** reúne los canales de las diferentes señales en un único canal (transmisión secuencial/serie) o en un número menor de canales (transmisión digital en paralelo). El medio puede ser línea(s), equipo de RF, guía de ondas, fibra óptica, etc.; su elección depende de distancia, costo, nivel de interferencias, ancho de banda y número de canales.
- **Unidad de cálculo:** computador analógico o digital, o un conjunto de circuitos que tratan los datos con criterios preestablecidos. Genera un flujo de retorno que puede incluir (a) datos para registro o evaluación y (b) datos o señales de accionamiento y control.
- **Separación:** individualiza esas señales del flujo de retorno (canales de registro/medida y canales de accionamiento).
- **Accionadores:** realizan la función inversa de los captadores (transforman señales eléctricas en magnitudes físicas de acción directa sobre la instalación o máquina); en muchos casos son servosistemas (electromecánicos, electrohidráulicos…) que además deben cumplir requisitos de estabilización automática de la magnitud de salida o de estabilidad propia.

### 1.2 Naturaleza de los datos

Conocer la naturaleza de los datos esperados es de gran importancia para elegir el equipo de captación y medida y definir los métodos de ensayo y control; errores grandes pueden producirse si las especificaciones de los instrumentos no se adaptan a las peculiaridades de los datos. La clasificación base atiende al **modo de variación en el tiempo**, y de ella pueden depender el procedimiento de tratamiento e incluso el costo del sistema.

| Tipo de dato | Características | Implicaciones de medida |
|---|---|---|
| **Estáticos** (1.2.1) | Evolución lenta, sin fluctuaciones bruscas ni discontinuidades. Ej.: temperatura en un punto de un sistema de gran inercia térmica. | Se usan para evaluar funcionamiento y rendimiento; se suelen exigir con **gran precisión** (el límite lo impone más el captador primario que el equipo de medida). Permiten **muestreo con un solo equipo compartido** (un termómetro central, un voltímetro de precisión), conmutando electrónicamente las señales, en general en forma digital. |
| **Transitorios** (1.2.2) | Respuesta de un sistema a un cambio brusco en las variables de entrada. | Se analizan para determinar el comportamiento dinámico. Importa más la **exactitud de la correlación temporal** entre magnitudes que la precisión absoluta (las transitorias ocurren simultáneamente en varios puntos tras una perturbación, frecuentemente provocada). |
| **Dinámicos** (1.2.3) | Periódicos, en funcionamiento estable y continuo. | Interesan en respuesta en régimen permanente a excitación senoidal, vibraciones, etc. Contenido armónico típico entre varios Hz y algunas decenas de kHz (excepto magnitudes eléctricas, sin límite concreto). Pueden ser reacción a excitaciones senoidales (amplitud y fase) o manifestación de funcionamiento periódico propio (dispositivos giratorios, elementos con movimiento alternativo). Con frecuencia interesa más el **análisis espectral** que el registro instantáneo. |
| **Aleatorios** (1.2.4) | Parámetros sujetos a fluctuaciones imprevisibles. | Su análisis es **estadístico/probabilístico**. Tres categorías: (1) datos que interesa registrar de magnitudes aparentemente aleatorias (EEG, ECG, ciertos datos meteorológicos); (2) datos aleatorios indeseables mezclados con la señal (ruido, interferencias); (3) salida aleatoria de un sistema ante una entrada también aleatoria aplicada para caracterizar su respuesta (útil en sistemas complejos o no lineales; ver Fig. 1.6). |

```json
{
  "type": "chart",
  "id": "chart-001",
  "page": 6,
  "pdf_page": 24,
  "title": "Figura 1.2: Señal con evolución muy lenta",
  "chart_type": "line",
  "axes": {"x": {"label": "x", "range": [0, 50], "ticks": [0, 12.5, 25, 37.5, 50]}, "y": {"label": "y", "range": [0, 2.5], "ticks": [0, 0.5, 1, 1.5, 2, 2.5]}},
  "series": [{"name": "señal", "color": "rojo", "values": null, "visual_summary": "curva casi plana, aproximadamente en y≈2 con muy leve ondulación en todo el rango"}],
  "description": "Ilustra un dato estático: señal de variación muy lenta. Valores numéricos exactos no determinados.",
  "basis": "vista rasterizada",
  "source": null
}
```

```json
{
  "type": "chart",
  "id": "chart-002",
  "page": 7,
  "pdf_page": 25,
  "title": "Figura 1.3: Respuesta transitoria de un sistema",
  "chart_type": "line",
  "axes": {"x": {"label": "Tiempo (s)", "range": [0, 20]}, "y": {"label": "Amplitud", "range": [0, 1.4]}},
  "series": [
    {"name": "Y(1)", "color": "azul", "values": null, "visual_summary": "respuesta subamortiguada: sube con sobreimpulso (máximo visual ≈1.2-1.3) y se estabiliza en torno a 1"},
    {"name": "U(1)", "style": "línea discontinua", "values": null, "visual_summary": "entrada escalón con valor final ≈1"}
  ],
  "description": "Respuesta al escalón de un sistema (títulos de eje y de gráfico: 'Respuesta al escalón', 'Amplitud', 'Tiempo (s)'). Valores exactos no determinados.",
  "basis": "texto de la figura + vista rasterizada de baja resolución",
  "source": null
}
```

```json
{
  "type": "chart",
  "id": "chart-003",
  "page": 8,
  "pdf_page": 26,
  "title": "Figura 1.4: Respuesta senoidal en un sistema eléctrico",
  "chart_type": "line",
  "axes": {"x": {"label": "x", "range": [0, 50], "ticks": [0, 12.5, 25, 37.5, 50]}, "y": {"label": "y", "range": [0, 2.5]}},
  "series": [{"name": "señal senoidal", "color": "verde", "values": null, "visual_summary": "tres crestas visibles, con valles cercanos a 0.3-0.5 y crestas cercanas a 2.3 (estimación visual aproximada); periodo ≈ 25 unidades de x"}],
  "description": "Ilustra un dato dinámico (periódico). Valores exactos no determinados.",
  "basis": "vista rasterizada",
  "source": null
}
```

```json
{
  "type": "chart",
  "id": "chart-004",
  "page": 8,
  "pdf_page": 26,
  "title": "Figura 1.5: Respuesta de un ECG",
  "chart_type": "line",
  "axes": {"x": {"label": null, "range": [0, 400]}, "y": {"label": null, "range": [-500, 4500]}},
  "series": [{"name": "ECG", "values": null, "visual_summary": "señal casi periódica con picos agudos (complejo QRS) hasta cerca de 4000 y ondas menores intermedias"}],
  "description": "Ejemplo de dato aleatorio/cuasi-periódico de origen biológico. Unidades de los ejes no indicadas en el documento.",
  "basis": "vista rasterizada",
  "source": null
}
```

```json
{
  "type": "image",
  "id": "image-001",
  "page": 9,
  "pdf_page": 27,
  "title": "Figura 1.6: Proceso con datos seudoaleatorios",
  "caption": "Proceso con datos seudoaleatorios.",
  "description": "No determinado: en la rasterización de baja resolución el área de la figura aparece vacía y la capa de texto no aporta rótulos. Se cita en 1.2.4 como ejemplo de la tercera categoría de datos aleatorios.",
  "elements": [],
  "source": null
}
```

### 1.3 Información analógica e información digital

- Es un tema controvertido si conviene instrumentación analógica o digital. La información **analógica** corresponde a funciones de variación continua que pueden tomar cualquier valor instantáneo; la **digital** a señales con niveles discretos a los que se asignan valores numéricos según convenios.
- Las funciones analógicas siguen fiel e instantáneamente a las magnitudes que representan; prácticamente todas las variables de interés tienen forma original analógica. Por eso el **primer tratamiento es casi siempre analógico** (a la salida de captadores el nivel suele ser muy bajo y puede incluir información no deseada: amplificación, eliminación de ruido e interferencias, filtrado).
- Cuando la señal tiene nivel alto y está depurada, se **prefiere el tratamiento digital** (a veces solo como paso intermedio hacia una presentación analógica), por estas razones del texto:
  1. Las señales analógicas transmitidas son interferidas y distorsionadas, y recuperar la información original es muy difícil; las digitales pueden regenerarse (conformado, detección y corrección de error).
  2. En lo analógico la precisión depende de la calidad de equipos/componentes; en lo digital depende únicamente del grado de cuantificación (número de bits).
  3. Hay gran variedad de circuitos digitales (convencionales y programables) de bajo costo.
- Un sistema moderno de captación y tratamiento incluirá, en general (no exclusivamente):
  - Sensores (mayormente analógicos) con su amplificación y acondicionamiento.
  - Uno o varios convertidores A/D.
  - Un sistema de tratamiento digital (microprocesadores, microcontroladores, DSP), usualmente con archivo de datos.
  - Presentación de datos analógica (requiere segunda conversión), pseudoanalógica (impresora, instrumentación virtual, indicadores de barras) o numérica.
  - Posiblemente canales de tratamiento totalmente analógico con presentación en tiempo real.

### 1.4 Sensores primarios

- Las magnitudes físicas tratadas con sistemas electrónicos deben convertirse en señales eléctricas; los **transductores** llevan a cabo esa transformación e incluyen siempre componentes sensibles (**sensores o captadores**) que reaccionan frente a la magnitud medida y entregan una primera señal eléctrica, que suele requerir tratamiento analógico (amplificación, adaptación de impedancias).
- Los sensores aprovechan (a) propiedades de ciertos materiales que se vuelven **generadores de señal** (termopares, cristales piezoeléctricos) o (b) **elementos pasivos** (resistencias, condensadores…) cuyos valores varían con la magnitud.

#### 1.4.1 Aspectos generales de los sensores

- «Transductor» y «sensor» se usan a menudo indistintamente. La *Instrument Society of America* (ISA) define el sensor como sinónimo de transductor en el Standard **S37.1 (1969)**, *Electrical Transducer Nomenclature and Terminology*: dispositivo que proporciona una salida útil en respuesta a un *measurand* específico. *Measurand*: cantidad física, propiedad o condición que se mide. La *respuesta* (output) se define como cantidad eléctrica (definición específica de transductor eléctrico; en sentido amplio la respuesta puede ser otra cantidad física).

> **Definición 1 (del documento).** Un transductor es un dispositivo o sistema que produce una señal eléctrica, función de una magnitud de entrada, utilizando componentes sensibles que se comportan como elementos variables o como generadores de señal.

- Los sensores también miden propiedades químicas y biológicas. Se agrupan según el tipo de excitación/respuesta:

| Dominio | Ejemplos (del documento) |
|---|---|
| Mecánica | longitud, área, volumen, flujo de masa, fuerza, torque, presión, velocidad, aceleración, posición, longitud de onda acústica, intensidad acústica |
| Térmica | temperatura, calor, entropía, flujo de calor |
| Eléctrica | tensión, corriente, carga, resistencia, inductancia, capacitancia, constante dieléctrica, polarización, campo eléctrico, frecuencia, momento dipolar |
| Magnética | intensidad de campo, densidad de flujo, momento magnético, permeabilidad |
| Radiante | intensidad, longitud de onda, polarización, fase, reflectancia, transmitancia, índice de refracción |
| Química | composición, concentración, oxidación/reducción, tasa de reacción, pH |

- Un sensor usa un **principio de transducción** físico o químico para convertir un tipo de señal de entrada en otro de salida; puede combinar varios. En electrónica industrial se requiere normalmente salida eléctrica. La Tabla 1.1 muestra ejemplos de principios de transducción.

```json
{
  "type": "table",
  "id": "table-001",
  "page": 12,
  "pdf_page": 30,
  "title": "Tabla 1.1: Principios de Transducción Física y Química",
  "headers": ["Entrada \\ Salida", "Mecánica", "Térmica", "Eléctrica", "Magnética", "Radiante", "Química"],
  "rows": [
    ["Mecánica", "Efectos mecánicos y acústicos (fluido): diafragma, balanza de gravedad, ecosonda", "Efectos de fricción (calorímetro de fricción); efectos de enfriamiento; fluómetros térmicos", "Piezoelectricidad; piezorresistividad; efectos R, L, C; efectos acústicos dieléctricos", "Efectos magnetomecánicos (piezomagnético, magnetoelástico, anillo de Rowland)", "Sistemas fotoelásticos (birrefringencia inducida de esfuerzo); interferómetros; efecto Sagnac; efecto Doppler", null],
    ["Térmica", "Expansión térmica (cinta bimetálica, termómetros de gas y de líquido en capilar de vidrio); efecto radiométrico", null, "Efectos termoeléctricos (termorresistencia, emisión termoiónica, superconductividad); efecto Seebeck; piroelectricidad; ruido térmico (Johnson)", "Temperatura de Curie", "Efecto termo-óptico (en cristales líquidos); emisión radiante", "Activación de reacción; disociación térmica"],
    ["Eléctrica", "Efectos electrocinéticos, electrostrictivos y electromecánicos (piezoelectricidad, electrómetros, ley de Ampère)", "Calentamiento Joule (resistivo); efecto Peltier", "Colectores de carga; probeta de Langmuir; electrets", "Ley de Biot-Savart; medidores y registradores electromagnéticos", "Efectos electroópticos (efecto Kerr); efecto Pockels; electroluminiscencia", "Electrólisis; electromigración"],
    ["Magnética", "Efectos magnetomecánicos (magnetostricción, magnetómetro); efectos Joule y Guillemin", "Efecto termomagnético (Righi-Leduc); efecto galvanomagnético (Ettingshausen)", "Efectos termomagnéticos (Ettingshausen-Nernst); efectos galvanomagnéticos (efecto Hall, magnetorresistencia)", "Almacenamiento magnético; efecto Barnett; efecto Einstein-de Haas; efecto de Haas-van Alphen", "Efectos magnetoópticos (efecto Faraday); efectos Cotton-Mouton y Kerr", null],
    ["Radiante", "Presión de radiación; molino de luz de Crookes", "Termopila; bolómetro", "Efectos fotoeléctricos (fotovoltaico, fotoconductivo, fotogalvánico y fotodieléctrico)", "Efecto Curie; metro de radiación", "Efecto fotorrefractivo; biestabilidad óptica", "Fotosíntesis; disociación"],
    ["Química", "Higrómetro; celda de electrodeposición; efecto fotoacústico", "Celda de conductividad térmica", "Potenciometría; conductimetría; amperometría; polarografía; ionización de llama; efecto Volta; efecto de campo sensible a gases", "Resonancia nuclear magnética", "Espectroscopía (emisión y absorción); quimioluminiscencia", null]
  ],
  "notes": "Encabezado original 'Sal / Ent'. La asignación de celdas a filas/columnas se reconstruyó desde la disposición del texto extraído y debe verificarse contra la página 30 del PDF; las celdas vacías se representan con null. Se normalizaron nombres evidentes (p. ej. 'Crooke' -> 'Crookes').",
  "source": null
}
```

### 1.5 Estructura de un transductor

Los transductores se presentan en dos configuraciones fundamentales: **lazo abierto** y **lazo cerrado**.

#### 1.5.1 Transductores en lazo abierto

- La señal de entrada se aplica a una **sonda** en contacto directo con el fenómeno. La sonda puede hacer una primera conversión de magnitud (ejemplos: tubo de Pitot, que transforma velocidad de fluido en diferencia de presiones; masa de inercia, que transforma aceleración en fuerza).
- Tras la sonda, los **elementos intermedios** adaptan su salida al **sensor primario** (el que efectúa la conversión a señal eléctrica). Ejemplos: pistones y resortes antagonistas en transductores de presión; sistemas de palancas que amplifican mecánicamente el movimiento de un palpador. Depende exclusivamente de la sonda y de los elementos intermedios que un mismo sensor primario sirva para magnitudes diferentes.
- La salida del sensor (directa en sensores generadores; dada por un circuito en sensores de parámetro variable) puede amplificarse en un **preamplificador** incorporado al transductor (práctica muy recomendable: mejores prestaciones globales frente a interferencias, sobre todo en transmisión a larga distancia).

```json
{
  "type": "diagram",
  "id": "diagram-002",
  "page": 13,
  "pdf_page": 31,
  "title": "Figura 1.7: Transductor en lazo abierto",
  "elements": ["Sonda", "Elementos intermedios", "Sensor", "Preamp.", "magnitud de entrada ν", "señal de salida ν"],
  "relationships": ["ν -> Sonda -> Elementos intermedios -> Sensor -> Preamp. -> ν (salida)"],
  "description": "Cadena serie de bloques de un transductor en lazo abierto."
}
```

**Análisis del efecto de la interferencia (Fig. 1.8).** Se modela un transductor (impedancia de salida Z_L) conectado a un equipo de tratamiento (impedancia de entrada Z_s) con una fuente de interferencia v_n acoplada por una impedancia Z_n (generalmente capacitiva):

$$v_0=\frac{Z_L Z_n\, v_s + Z_L Z_s\, v_n}{Z_s Z_L + Z_n Z_L + Z_s Z_n}\qquad(1.5.1)$$

Componente debida a la interferencia:

$$v_{no}=\frac{Z_s Z_L}{Z_s Z_L + Z_n Z_L + Z_s Z_n}\; v_n\qquad(1.5.2)$$

Error relativo por interferencia:

$$\varepsilon_i=\frac{v_{no}}{v_0}=\frac{Z_s Z_L}{Z_s Z_L + Z_n Z_L + Z_s Z_n}\cdot\frac{v_n}{v_0}\qquad(1.5.3)$$

Conclusiones del documento: (1) el error relativo de interferencia **disminuye al aumentar la señal de salida del transductor**; (2) **disminuye al bajar la impedancia de salida** del transductor, y es nulo cuando esta es nula. Por tanto conviene preamplificar con la mayor ganancia posible y la menor impedancia de salida posible; la primera está limitada por la saturación de las etapas, la segunda se logra fácilmente con **amplificadores operacionales**, cuya impedancia de salida en lazo cerrado es prácticamente nula (anula virtualmente el error si la interferencia se acopla según este modelo, p. ej. acoplamiento capacitivo en amplificación de señales débiles).

> **Observación de fidelidad.** En el texto, v₀ se describe primero como «tensión de salida del transductor» y v_s como la tensión que llega al equipo, pero después v₀ se llama «señal de entrada al equipo de tratamiento» y v_s «salida del transductor». La notación es inconsistente en el original; se conservan las ecuaciones tal como están.

```json
{
  "type": "diagram",
  "id": "diagram-003",
  "page": 14,
  "pdf_page": 32,
  "title": "Figura 1.8: Circuito equivalente para un transductor incluyendo señal de interferencia",
  "elements": ["Fuente de interferencia vn", "Impedancia de acople Zn", "Transductor (fuente vs con impedancia ZL)", "Equipo de tratamiento (impedancia Zs)", "Tensión vo"],
  "relationships": ["vn acopla a las líneas a través de Zn", "El transductor (vs, ZL) alimenta el equipo (Zs)"],
  "description": "Modelo de circuito usado para deducir las ecuaciones 1.5.1-1.5.3."
}
```

#### 1.5.2 Transductores de lazo cerrado o servotransductores

Configuración de ciertos transductores de alta precisión (Fig. 1.9) con dos sensores primarios: **sensor de captación** y **sensor de lectura**. La magnitud de entrada v_i llega a través de la sonda (salida K_s·v_i) a un acoplamiento diferencial; la salida del sensor de captación se amplifica (ganancia A) y se aplica a un elemento intermedio (función de transferencia β), cuya salida se resta de la de la sonda y, además, se convierte en señal eléctrica en el sensor de lectura (salida del servotransductor).

$$v_0=\frac{\beta A K_s K_c K_l}{1+\beta A K_c}\; v_i\qquad(1.5.4)$$

Para A grande:

$$v_0\cong K_s K_l\, v_i\qquad(1.5.5)$$

La salida es proporcional a la entrada; con alta amplificación, el lazo tiende a anular la diferencia entre la salida de la sonda y la del elemento intermedio. *(Nota: el texto no define K_c y K_l de forma explícita; por el diagrama y el contexto corresponden a las funciones de transferencia del sensor de captación y del sensor de lectura — interpretación del convertidor.)*

```json
{
  "type": "diagram",
  "id": "diagram-004",
  "page": 15,
  "pdf_page": 33,
  "title": "Figura 1.9: Transductor en lazo cerrado",
  "elements": ["Sonda (Ks)", "Sumador diferencial (Σ, + / −)", "Sensor de captación", "Amplificador (A)", "Elemento intermedio (β)", "Sensor de lectura", "entrada ν", "salida ν"],
  "relationships": ["ν -> Sonda -> Σ -> Sensor de captación -> Amplificador -> Elemento intermedio -> Sensor de lectura -> salida", "Salida del elemento intermedio -> realimentación negativa a Σ"],
  "description": "Servotransductor con realimentación mecánica/intermedia."
}
```

**Por qué son muy precisos (según el documento):** la medida no se ve afectada por las imperfecciones del sensor de captación, del amplificador ni del elemento intermedio; la precisión depende solo de la sonda y del sensor de lectura (que trabaja en condiciones muy favorables al recibir una magnitud ya amplificada).

| Ventajas | Desventajas |
|---|---|
| Salida de alto nivel | Costo elevado |
| Gran precisión | Poca robustez |
| Corrección continua de las medidas | Dificultades en la respuesta dinámica |
| Alta resolución | |

### 1.6 Clasificación

Se adopta una clasificación (ref. [23]) según la naturaleza de la señal eléctrica, el modo de obtenerla y los principios físicos; el libro sigue este esquema. **Sensores analógicos directos:** su salida analógica representa directamente la magnitud de entrada sin interpretación adicional. Tipos:

- **De parámetro variable:** componentes pasivos cuyo valor varía con la magnitud; requieren formar parte de circuitos con alimentación externa.
- **Generadores de señal:** generan señales representativas en forma autónoma, sin fuente de alimentación.
- **Mixtos:** doble naturaleza (generador/activo y componente pasivo en circuitos con fuente asociada).

**Sensores indirectos:** el valor instantáneo de salida no representa directamente la magnitud; requiere decodificación posterior. Se exponen los que dan señales periódicas cuya **frecuencia fundamental** contiene la información, y algunos digitales. Muchos sensores indirectos usan células sensibles del grupo de analógicos directos, variando solo el modo de funcionamiento y los circuitos.

```json
{
  "type": "table",
  "id": "table-002",
  "page": 16,
  "pdf_page": 34,
  "title": "Tabla 1.2: Sensores analógicos directos",
  "headers": ["Categoría", "Subcategoría", "Tipos"],
  "rows": [
    ["De parámetro variable", "De resistencia variable", ["Potenciométricos", "Termorresistivos", "Fotorresistivos", "Piezorresistivos", "Extensométricos", "Electroquímicos", "De adsorción"]],
    ["De parámetro variable", "De capacidad variable", ["Geometría variable", "Dieléctrico variable"]],
    ["De parámetro variable", "De inductancia variable", []],
    ["De parámetro variable", "De transformador variable", []],
    ["Generadores de señal", "Fotoeléctricos", ["Fotoemisivos", "Fotocontrolados"]],
    ["Generadores de señal", null, ["Piezoeléctricos", "Fotovoltaicos", "Termoeléctricos", "Magnetoeléctricos", "Electrocinéticos", "Electroquímicos"]],
    ["Mixtos", null, ["De geometría variable", "De efecto Hall", "Bioeléctricos"]]
  ],
  "notes": "Jerarquía reconstruida de la disposición con llaves del original; la correspondencia exacta de 'De geometría variable' (bajo Mixtos) y de 'Fotoemisivos/Fotocontrolados' (bajo Fotoeléctricos) debe verificarse en la p. 16.",
  "source": null
}
```

```json
{
  "type": "table",
  "id": "table-003",
  "page": 18,
  "pdf_page": 36,
  "title": "Tabla 1.3: Sensores indirectos",
  "headers": ["Categoría", "Subcategoría", "Tipos"],
  "rows": [
    ["Moduladores de frecuencia", "De elemento vibrante", ["Gravimétricos", "Tensométricos"]],
    ["Moduladores de frecuencia", "De reactancia variable", ["De condensador", "De inductancia"]],
    ["Generadores de frecuencia", null, ["Electromagnéticos", "Fotoeléctricos", "De efecto Hall"]],
    ["Digitales", null, ["Codificadores angulares", "Codificadores lineales", "Fotoelásticos"]]
  ],
  "notes": "Jerarquía reconstruida de la disposición del original.",
  "source": null
}
```

---

## Capítulo 2. Características estáticas de un sistema de medida

### 2.1 Introducción

- **Características estáticas (estado estacionario):** relaciones entre la salida θ y la entrada u de un elemento cuando u es constante o cambia muy lentamente. El comportamiento del sistema de medida está condicionado por el sensor.
- Dos conceptos: **exactitud** (ligada a las características fundamentales de la estructura de la materia y acotada por el principio de incertidumbre) y **precisión** (ligada al sistema empleado para medir). Toda medida lleva un error inevitable.
- **Error del sistema:** diferencia entre el valor de consigna (*set point*) de la variable controlada y el valor real. Determinar un error supone conocer el valor exacto, que en la práctica se toma de los **patrones de medida**; a veces se usan como «patrones» las curvas de calibración del fabricante cuando no se necesita precisión extrema.

### 2.2 Características sistemáticas

Son las que pueden cuantificarse exactamente por medios gráficos o matemáticos (el texto las contrasta con las «estáticas», que no pueden cuantificarse exactamente).

> **Observación de fidelidad.** La frase original dice que las características sistemáticas «son distintas de las características estáticas, las cuales no pueden ser cuantificadas exactamente»; por el contexto parece referirse a características *estadísticas*. Se conserva sin corregir.

1. **Rango.** Rango de entrada: u_min a u_max; rango de salida: θ_min a θ_max. *Ejemplos:* transductor de presión con entrada 0 a 10⁴ Pa y salida 4 a 20 mA; termocupla con entrada 100 a 250 °C y salida 4 a 10 mV.
2. **Alcance (span).** Máxima variación: entrada u_max − u_min; salida θ_max − θ_min. En los ejemplos: transductor de presión, 10⁴ Pa y 16 mA; termocupla, 150 °C y 6 mV.
3. **Línea recta ideal.** Un elemento es ideal si u y θ siguen una recta que conecta A(u_min, θ_min) con B(u_max, θ_max):

$$\theta-\theta_{min}=\frac{\theta_{max}-\theta_{min}}{u_{max}-u_{min}}\,(u-u_{min})\qquad(2.2.1)$$

$$\theta_{ideal}=ku+a\qquad(2.2.2)$$

$$k=\frac{\theta_{max}-\theta_{min}}{u_{max}-u_{min}}\qquad(2.2.3)\qquad a=\theta_{min}-k\,u_{min}\qquad(2.2.4)$$

   Para el transductor de presión del ejemplo: θ = 1.6×10⁻³·u + 4.0.
4. **No linealidad.** Función N(u) = θ(u) − (ku + a), es decir θ(u) = ku + a + N(u) (2.2.5) (Fig. 2.1). Se cuantifica con la máxima no linealidad N̂ como porcentaje de la deflexión a plena escala (f.s.d.):

$$\text{Máx. no linealidad (\% f.s.d.)}=\frac{\hat N}{\theta_{max}-\theta_{min}}\times100\%\qquad(2.2.6)$$

   Muchas veces θ(u) es un polinomio:

$$\theta(u)=a_0+a_1u+a_2u^2+\dots+a_mu^m=\sum_{i=0}^{m}a_iu^i\qquad(2.2.7)$$

   *Ejemplo del documento (termocupla tipo T, cobre-constantan; E en μV, T en °C):*

$$E(T)=38.74\,T+3.319\times10^{-2}T^2+2.071\times10^{-4}T^3-2.195\times10^{-6}T^4+\mathcal{O}(T)\ \text{hasta }T^8\qquad(2.2.8)$$

   Para 0-400 °C (E = 0 mV a 0 °C; E = 20.869 mV a 400 °C): E_ideal = 52.17·T (2.2.9) y

$$N(T)=-13.43\,T+3.319\times10^{-2}T^2+2.071\times10^{-4}T^3-2.195\times10^{-6}T^4+\mathcal{O}(T)\qquad(2.2.10)$$

   Otro ejemplo (no polinomial): resistencia de un termistor R(T) = 0.04·exp(3300/(T+273)) Ω, con T en °C.
5. **Sensibilidad.** Rapidez de cambio de θ respecto a u:

$$\frac{d\theta}{du}=K+\frac{dN}{du}\qquad(2.2.11)\qquad\text{ideal: }\frac{d\theta}{du}=K\qquad(2.2.12)$$

   Transductor de presión: dθ/du = 1.6×10⁻³ mA/Pa. Termocupla Cu-constantan:

$$\frac{dE}{dT}=38.74+6.638\times10^{-2}T+6.213\times10^{-4}T^2-8.780\times10^{-6}T^3+\mathcal{O}(T)\qquad(2.2.13)$$

   que el documento da como ≈ 50 μV·°C⁻¹ a 200 °C.

> **Observación de fidelidad (cálculo del convertidor, no del documento).** Evaluando solo los cuatro términos listados de (2.2.13) a 200 °C resulta ≈ 6.6 μV/°C, no ≈ 50. El documento omite los términos de orden superior (𝒪(T)), por lo que no puede reproducirse la cifra de 50 μV/°C con lo impreso. Se conserva la cifra original.

6. **Efectos ambientales.** θ depende además de entradas ambientales (temperatura ambiente, presión atmosférica, humedad relativa, fuente de alimentación…). Condiciones «estándar» del documento: 25 °C, 1000 milibars, 80 % de humedad relativa, alimentación de 10 V. Dos tipos:
   - **(a) Entrada modificadora (u_M):** cambia la sensibilidad lineal de k a k + k_M·u_M (Fig. 2.3a). Ej.: variación ΔV_s del voltaje de alimentación en un sensor potenciométrico de desplazamiento (Fig. 2.4).
   - **(b) Entrada interferente (u_I):** cambia el intercepto o sesgo de cero de a a a + k_I·u_I (Fig. 2.3b). Ej.: variaciones de la temperatura de la unión de referencia T₂ de una termocupla.
   - k_M y k_I son **constantes de acoplamiento ambiental** (sensibilidades). La ecuación corregida es:

$$\theta=ku+a+N(u)+k_Mu_Mu+k_Iu_I\qquad(2.2.14)$$

7. **Histéresis.** Para un u dado, θ difiere según u aumente o disminuya:

$$H(u)=\theta(u)_{u\downarrow}-\theta(u)_{u\uparrow}\qquad(2.2.15)\qquad H_{max}\,\%\,\text{f.s.d.}=\frac{\hat H}{\theta_{max}-\theta_{min}}\times100\%\qquad(2.2.16)$$

   Ejemplo: sistema de engranajes que convierte movimiento lineal en rotatorio; por el «juego» entre dientes, la rotación θ para un x dado depende del sentido del movimiento (Fig. 2.6).
8. **Resolución.** Mayor cambio en u que puede ocurrir sin cambio en θ (salida en pasos discretos). Con Δu_R el paso más ancho:

$$\text{Res}\,\%=\frac{\Delta u_R}{u_{max}-u_{min}}\times100\%\qquad(2.2.17)$$

   Ejemplos: potenciómetro de alambre devanado (cada paso = resistencia de una vuelta; uno de **100 vueltas tiene resolución de 1 %**); convertidor A/D (resolución = cambio de tensión que cambia el bit menos significativo).
9. **Uso y envejecimiento.** k y a cambian lenta pero sistemáticamente. Ejemplo: rigidez de resorte k(t) = k₀ − b·t (2.2.18), con k₀ rigidez inicial y b constante; también los coeficientes a₁, a₂… de una termocupla en un horno de fragmentación, por cambios químicos en los metales.
10. **Bandas de error.** Cuando no linealidad, histéresis y resolución son muy pequeñas, el fabricante garantiza que para cualquier u, θ estará dentro de ±h del valor ideal; se pasa a un enunciado estadístico con función densidad de probabilidad p(θ). Para x₁≤x≤x₂, ∫p(x)dx es la probabilidad de que x caiga en ese intervalo. Aquí p es rectangular (Fig. 2.9):

$$p(\theta)=\begin{cases}\dfrac{1}{2h}&\theta_{ideal}-h\le\theta\le\theta_{ideal}+h\\[4pt]0&\theta>\theta_{ideal}+h\\0&\theta<\theta_{ideal}-h\end{cases}\qquad(2.2.19)$$

   El área del rectángulo es 1 (probabilidad de que θ caiga entre θ_ideal − h y θ_ideal + h).

```json
{
  "type": "chart",
  "id": "chart-005",
  "page": 21,
  "pdf_page": 39,
  "title": "Figura 2.1: Definición de no linealidad",
  "chart_type": "conceptual (curva real vs recta ideal)",
  "axes": {"x": {"label": "u", "range": null}, "y": {"label": "θ", "range": null}},
  "series": [{"name": "θ(u) real", "values": null}, {"name": "recta ideal", "values": null}, {"name": "N(u) (diferencia)", "values": null}],
  "labels_in_text_layer": ["θ_max", "θ_min", "u_min", "u_max", "N", "+", "−"],
  "description": "Gráfica conceptual que muestra la no linealidad N(u) como la diferencia entre la curva real y la recta que une los puntos mínimo y máximo.",
  "basis": "pie de figura + rótulos de la capa de texto (no verificado visualmente)"
}
```

```json
{
  "type": "chart",
  "id": "chart-006",
  "page": 22,
  "pdf_page": 40,
  "title": "Figura 2.2: Respuesta en mV de una termocupla tipo T (Cu/CuNi)",
  "chart_type": "line",
  "axes": {"x": {"label": "T (°C)", "range": [0, 400]}, "y": {"label": "E (mV)", "range": [0, 20.869]}},
  "series": [{"name": "E(T) tipo T", "values": null, "known_points": [{"T_C": 0, "E_mV": 0}, {"T_C": 400, "E_mV": 20.869}]}],
  "description": "Curva de la termocupla tipo T con la recta ideal entre 0 y 400 °C. Solo se dan como seguros los dos puntos citados en el texto (ecuación 2.2.9); en la rasterización de baja resolución el área de trazado no es legible.",
  "source": null
}
```

```json
{
  "type": "chart",
  "id": "chart-007",
  "page": 23,
  "pdf_page": 41,
  "title": "Figura 2.3: Efectos de las entradas modificadora e interferente (a) Modificadora (b) Interferente",
  "chart_type": "conceptual (dos paneles θ vs u)",
  "panels": [
    {"panel": "a", "description": "La entrada modificadora cambia la pendiente de la recta (sensibilidad k -> k + k_M·u_M)", "labels": ["Pendiente"]},
    {"panel": "b", "description": "La entrada interferente desplaza la recta (sesgo de cero a -> a + k_I·u_I)", "labels": ["Sesgo de cero"]}
  ],
  "axes": {"x": {"label": "u"}, "y": {"label": "θ"}},
  "series": []
}
```

```json
{
  "type": "diagram",
  "id": "diagram-005",
  "page": 23,
  "pdf_page": 41,
  "title": "Figura 2.4: Potenciómetro",
  "elements": ["potenciómetro", "variación de alimentación ΔVs (rótulo 'Δ' en la capa de texto)"],
  "relationships": [],
  "description": "Esquema del sensor de desplazamiento potenciométrico usado como ejemplo de entrada modificadora (variación del voltaje de alimentación). Detalles no verificados."
}
```

```json
{
  "type": "chart",
  "id": "chart-008",
  "page": 24,
  "pdf_page": 42,
  "title": "Figura 2.5: Histéresis",
  "chart_type": "conceptual (lazo de histéresis θ vs u)",
  "axes": {"x": {"label": "u"}, "y": {"label": "θ"}},
  "series": [{"name": "lazo de histéresis", "values": null}],
  "labels_in_text_layer": ["H"],
  "description": "Muestra dos curvas (u creciente y u decreciente) separadas por H(u); el panel derecho indica H."
}
```

```json
{
  "type": "chart",
  "id": "chart-009",
  "page": 25,
  "pdf_page": 43,
  "title": "Figura 2.6: Juego en engranajes. Ejemplo de histéresis",
  "chart_type": "conceptual (dos paneles θ vs x)",
  "axes": {"x": {"label": "x"}, "y": {"label": "θ"}},
  "series": [],
  "description": "Relación rotación-desplazamiento para un sistema de engranajes con juego; la salida depende del sentido de movimiento."
}
```

```json
{
  "type": "chart",
  "id": "chart-010",
  "page": 25,
  "pdf_page": 43,
  "title": "Figura 2.7: Ejemplo de resolución y de potenciómetro",
  "chart_type": "conceptual (escalones)",
  "axes": {"x": {"label": "u (o x)"}, "y": {"label": "θ (R)"}},
  "labels_in_text_layer": ["Δ", "R", "x"],
  "series": [],
  "description": "Salida en pasos discretos; Δu_R es el paso más ancho (resolución). Incluye la relación R-x de un potenciómetro de alambre devanado."
}
```

```json
{
  "type": "chart",
  "id": "chart-011",
  "page": 26,
  "pdf_page": 44,
  "title": "Figura 2.8: Bandas de error y función de probabilidad",
  "chart_type": "conceptual (banda ±h y densidad rectangular)",
  "axes": {"x": {"label": "u / θ"}, "y": {"label": "θ / p(θ)"}},
  "labels_in_text_layer": ["h", "2h", "1/(2h)", "p(θ)"],
  "series": [],
  "description": "Panel izquierdo: banda de error de ancho ±h alrededor de la recta ideal. Panel derecho: función densidad de probabilidad rectangular de altura 1/(2h) y ancho 2h.",
  "basis": "vista rasterizada de baja resolución + capa de texto"
}
```

```json
{
  "type": "chart",
  "id": "chart-012",
  "page": 27,
  "pdf_page": 45,
  "title": "Figura 2.9: Función densidad de probabilidad",
  "chart_type": "conceptual",
  "axes": {"x": {"label": "x", "ticks": ["1", "2"]}, "y": {"label": "p(x) (Densidad de probabilidad)"}},
  "series": [],
  "description": "Gráfica de la densidad de probabilidad rectangular (área = 1)."
}
```

### 2.3 Modelo generalizado de un elemento

Si hay efectos ambientales y no lineales pero no histéresis ni resolución, la salida de estado estacionario es:

$$\theta=ku+a+N(u)+k_Mu_Mu+k_Iu_I\qquad(2.3.1)$$

La Fig. 2.10 la presenta como diagrama de bloques (parte **estática**) más una función de transferencia **G(s)** que representa la parte **dinámica**.

```json
{
  "type": "diagram",
  "id": "diagram-006",
  "page": 27,
  "pdf_page": 45,
  "title": "Figura 2.10: Modelo general de un elemento",
  "elements": ["Entrada", "Entrada modificadora", "Entrada interferente", "Bloque Estático", "Bloque Dinámico G(s)", "θ", "θ₀ (Salida)"],
  "relationships": ["Entrada + modificadora + interferente -> bloque estático -> θ -> bloque dinámico -> salida θ₀"],
  "description": "Modelo estático-dinámico en cascada de un elemento de medida."
}
```

### 2.4 Identificación de características estáticas. Calibración

#### 2.4.1 Patrones de medida

- Las características estáticas se hallan experimentalmente midiendo u, θ y las entradas ambientales u_M, u_I con u constante o de evolución lenta: eso es la **calibración**. Los instrumentos y técnicas usados para medir esas variables son los **patrones de calibración** (Fig. 2.11).
- **Precisión de una medida:** cercanía al valor verdadero; se cuantifica por el **error** (valor medido − valor verdadero).

> **Definición 2 (del documento).** El valor verdadero de una variable es el valor medido obtenido con un **patrón primario**.

- Un fabricante puede no tener acceso al patrón primario; calibra con un **patrón intermedio de transferencia** (p. ej. probador de peso muerto), que a su vez se calibra contra el primario. Esto da la **escala de rastreabilidad**: el elemento se calibra con patrones de laboratorio; estos con patrones de transferencia; estos con el patrón primario; cada escalón debe ser significativamente más preciso que el anterior.

```json
{
  "type": "diagram",
  "id": "diagram-007",
  "page": 28,
  "pdf_page": 46,
  "title": "Figura 2.11: Calibración de un elemento",
  "elements": ["Instrumento Patrón (entrada)", "Instrumento Patrón (salida)", "Instrumentos Patrón (variables ambientales, dos)", "Elemento o sistema a ser calibrado", "θ"],
  "relationships": ["Los instrumentos patrón miden la entrada, las entradas ambientales y la salida θ del elemento a calibrar"],
  "description": "Esquema de calibración con instrumentos patrón alrededor del elemento a calibrar."
}
```

```json
{
  "type": "table",
  "id": "table-004",
  "page": 29,
  "pdf_page": 47,
  "title": "Tabla 2.1: Escala simplificada de rastreabilidad",
  "headers": ["Nivel", "Ejemplo (v. gr.)"],
  "rows": [
    ["Patrón primario", "patrón de presión del NPL"],
    ["Patrón de transferencia", "probador de peso muerto"],
    ["Patrón de laboratorio", "galga de presión normalizada"],
    ["Elemento a ser calibrado", "transductor de presión"]
  ],
  "notes": "Flecha ascendente en el original: «Incremento de precisión» de abajo (elemento) hacia arriba (patrón primario).",
  "source": null
}
```

**Patrones primarios por magnitud (Reino Unido, según el documento):**

- **SI:** siete unidades básicas y dos suplementarias (Apéndice B). El **N.P.L.** (National Physical Laboratory) realiza físicamente las unidades básicas y muchas derivadas; los patrones secundarios están en el Servicio de Calibración Británico (**B.C.S.**).
- **Longitud:** el metro se definió con la longitud de onda de un láser de helio-neón estabilizado con yodo; reproducibilidad **3 partes en 10¹¹**; calibra interferómetros láser secundarios, que calibran cintas, galgas y barras de precisión (Tabla 2.2).
- **Masa/fuerza:** prototipo internacional del kilogramo de platino-iridio (B.I.P.M., París). El peso es mg; con g local conocido se derivan patrones de fuerza. Máquinas de peso muerto del NPL cubren **450 N a 30 MN** y calibran celdas de carga con galgas extensométricas.
- **Eléctricos:** el amperio se realizaba con la balanza de corriente Ayrton-Jones (limitada por los grandes pesos muertos y las muchas medidas); por eso se escogieron como básicas el **faradio** y el **voltio (o vatio)**, derivando amperio, ohmio, henrio y julio con tiempo o frecuencia y la ley de Ohm. El faradio se realizó con un capacitor calculable (teorema de Thompson-Lampard); con puentes de c.a. se calibran resistores estándar. El patrón primario del voltio se basa en el **efecto Josephson**; los patrones secundarios de voltaje son usualmente las baterías saturadas de cadmio de Weston. El amperio también puede realizarse con una balanza de corriente modificada, igualando fuerzas mecánica y eléctrica:

$$eI=mgu\qquad(2.4.1)$$

  (e: voltaje inducido en la espira al moverse con velocidad u).
- **Temperatura:** idealmente se define con la escala termodinámica, $PV=R\theta$ (2.4.2), gas ideal a volumen fijo. Por la limitada reproducibilidad de los termómetros de gas reales se proyectó la **Escala Práctica Internacional de Temperatura (I.T.P.S.)** (Tabla 2.3), compuesta por (a) puntos fijos muy reproducibles (fusión, ebullición o puntos triples de sustancias puras) y (b) instrumentos patrones con relación salida-temperatura obtenida calibrando en los puntos fijos; se interpola entre ellos. Hay exactamente **100 K entre el punto de congelación (273.15 K) y el de ebullición (373.15 K) del agua**; 1 K equivale a 1 °C: θ_K = T_°C + 273.15. Un termómetro de resistencia de platino por interpolación puede calibrar un segundo termómetro de resistencia de platino.
- **Magnitudes derivadas:** ejemplo, calibración de medidores de flujo de líquidos: el flujo real se halla pesando el agua recolectada en un tiempo dado (depende de los patrones de peso y tiempo); los patrones de presión se derivan de fuerza y área (longitud).

```json
{
  "type": "table",
  "id": "table-005",
  "page": 30,
  "pdf_page": 48,
  "title": "Tabla 2.2: Escala de rastreabilidad (Adaptada de Scarr) — longitud",
  "headers": ["Responsabilidad", "Longitud", "Precisión"],
  "rows": [
    ["BIMP y NPL", "Radiación láser He-Ne de longitud de onda de 633 nm", "3 en 10^11"],
    ["NPL", "Longitud de onda de fuentes láser secundarias", "1 en 10^7"],
    ["NPL o BCS o Industria", "Calibración interferométrica láser de calidad de referencia para patrón de longitud", "1 en 10^6"],
    ["BCS o Industria", "Calibración comparativa de calidad operativa para patrón de longitud", "1 en 10^5"],
    ["BCS o Industria", "Calibración de galgas y de equipos de medida", "1 en 10^4"],
    ["—", "Medida de la pieza de trabajo", null]
  ],
  "notes": "Flechas descendentes entre filas. Leyenda: BIPM = International Bureau of Weights and Measures; NPL = National Physical Laboratory; BCS = British Calibration Service. La primera fila dice «BIMP» en el original, la leyenda dice «BIPM» (se conserva).",
  "source": "Adaptada de Scarr (según el pie de la tabla)"
}
```

```json
{
  "type": "table",
  "id": "table-006",
  "page": 31,
  "pdf_page": 49,
  "title": "Tabla 2.3: Puntos fijos definidos en el ITS-90",
  "headers": ["Número", "T90 (K)", "t90 (°C)", "Sustancia", "Estado", "Wr(T90)"],
  "rows": [
    [1, "3 a 5", "-270.15 a -268.15", "He", "V", null],
    [2, 13.8033, -259.3467, "e-H2", "T", 0.00119007],
    [3, "~17", "~-256.15", "e-H2 (ó He)", "V ó G", null],
    [4, "~20.3", "~-252.85", "e-H2 (ó He)", "V ó G", null],
    [5, 24.5561, -248.5939, "Ne", "T", 0.00844974],
    [6, 54.6584, -218.7916, "O2", "T", 0.09171804],
    [7, 83.8058, -189.3442, "Ar", "T", 0.21585975],
    [8, 234.3156, -38.8344, "Hg", "T", 0.84414211],
    [9, 273.16, 0.01, "H2O", "T", 1.00000000],
    [10, 302.9146, 29.7646, "Ga", "M", 1.11813889],
    [11, 429.7485, 156.5985, "In", "F", 1.60980185],
    [12, 505.078, 231.928, "Sn", "F", 1.89279768],
    [13, 629.677, 419.527, "Zn", "F", 2.56891730],
    [14, 933.473, 660.323, "Al", "F", 3.37600860],
    [15, 1234.93, 961.78, "Ag", "F", 4.28642053],
    [16, 1337.33, 1064.18, "Au", "F", null],
    [17, 1357.77, 1084.62, "Cu", "F", null]
  ],
  "notes": "Las letras de estado (V, T, G, M, F) no están definidas en el texto de esta página; no se interpretan aquí. Wr(T90) en blanco en el original para las filas 1, 3, 4, 16 y 17.",
  "source": null
}
```

> **Observación de fidelidad.** Las Tablas 2.3 y 2.4 no coinciden en dos valores: **oxígeno** (54.6584 K en 2.3; 54.3584 en 2.4) y **zinc** (629.677 K en 2.3; 692.677 en 2.4). Se conservan ambos tal como están impresos. Además el texto menciona la «I.T.P.S.» mientras que la tabla se titula «ITS-90».

```json
{
  "type": "table",
  "id": "table-007",
  "page": 33,
  "pdf_page": 51,
  "title": "Tabla 2.4: Efecto de la presión sobre algunos puntos definidos fijos",
  "headers": ["Substancia", "Valor de asignación de temperatura en equilibrio T90 (K)", "Temperatura con presión, dT/dp (10^-8 K·Pa^-1)", "Variación con profundidad, dT/dλ (10^-3 K·m^-1)"],
  "rows": [
    ["e-Hidrógeno (T)", 13.8033, 34, 0.25],
    ["Neón (T)", 24.5561, 16, 1.9],
    ["Oxígeno (T)", 54.3584, 12, 1.5],
    ["Argón (T)", 83.8058, 25, 3.3],
    ["Mercurio (T)", 234.3156, 5.4, 7.1],
    ["Agua (T)", 273.16, -7.5, -0.73],
    ["Galio", 302.9146, -2.0, -1.2],
    ["Indio", 429.7485, 4.9, 3.3],
    ["Estaño", 505.078, 3.3, 2.2],
    ["Zinc", 692.677, 4.3, 2.7],
    ["Aluminio", 933.473, 7.0, 1.6],
    ["Plata", 1234.93, 6.0, 5.4],
    ["Oro", 1337.33, 6.1, 10.0],
    ["Cobre", 1357.77, 3.3, 2.6]
  ],
  "notes": "Los signos negativos aparecen como guion largo en el original. (T) = punto triple (marca del original; el significado no se define en el texto de la página).",
  "source": null
}
```

### 2.5 Medidas experimentales y evaluación de resultados

El experimento de calibración tiene **tres partes**:

**Parte 1 — θ vs u con u_M = u_I = 0**
1. Idealmente en condiciones ambientales estándar; si no, medir todas las entradas ambientales.
2. Aumentar u lentamente de u_min a u_max y registrar (u, θ) a intervalos del **10 % del alcance (11 lecturas)**, esperando que la salida se estabilice; luego disminuir de u_max a u_min (otras 11 lecturas). Repetir el ciclo **dos veces más** → dos conjuntos: (u_i, θ_i)_{I↑} y (u_j, θ_j)_{I↓}, con n = 33.
3. Ajustar polinomios por **mínimos cuadrados** (paquetes de regresión): con d_i = θ(u_i) − θ_i se minimiza Σd_i²; implica resolver un sistema de ecuaciones lineales (ref. [15]). Se hacen regresiones separadas para detectar histéresis:

$$\theta(u)_{I\uparrow}=\sum_{q=0}^{m}a_q^{\uparrow}u^q\qquad\theta(u)_{I\downarrow}=\sum_{q=0}^{m}a_q^{\downarrow}u^q\qquad(2.5.1)$$

$$H(u)=\theta(u)_{u\downarrow}-\theta(u)_{u\uparrow}\qquad(2.5.2)$$

4. **Criterio:** si la separación entre las dos curvas es mayor que la dispersión de los datos alrededor de cada curva → **histéresis significativa** (Fig. 2.12a). Si la dispersión es mayor que la separación → **no significativa** (Fig. 2.12b) y los dos conjuntos se combinan en un solo polinomio θ(u).
5. Con k y a de la recta ideal (2.2.3) se halla $N(u)=\theta(u)-(ku+a)$ (2.5.3).
6. Sensores de temperatura: pueden calibrarse con **puntos fijos** en lugar de instrumento patrón. Ej.: una termocupla entre 0 y 500 °C midiendo la fem en hielo, vapor y punto del zinc; si E = a₁T + a₂T² + a₃T³, los coeficientes salen de resolver tres ecuaciones simultáneas.

```json
{
  "type": "chart",
  "id": "chart-013",
  "page": 35,
  "pdf_page": 53,
  "title": "Figura 2.12: (a) Histéresis significativa (b) Histéresis no significativa",
  "chart_type": "conceptual (dos paneles θ vs u)",
  "panels": [
    {"panel": "a", "description": "Dos curvas (Arriba y Abajo) claramente separadas respecto a la dispersión de los puntos."},
    {"panel": "b", "description": "Dispersión de los puntos mayor que la separación entre curvas."}
  ],
  "axes": {"x": {"label": "u"}, "y": {"label": "θ"}},
  "labels_in_text_layer": ["Abajo", "Arriba"],
  "series": []
}
```

**Parte 2 — θ vs u_M, u_I con u = constante**
- *Entradas interferentes:* con u = u_min, variar una entrada ambiental en una cantidad conocida (el resto estándar). Si hay Δθ, la entrada interfiere y $k_I=\Delta\theta/\Delta u_I$; si no hay cambio, no es interferente.
- *Entradas modificadoras:* con u en el valor medio del rango, ½(u_min + u_max), variar cada entrada ambiental; si hay Δθ y no es interferente, es modificadora:

$$k_M=\frac{1}{\bar u}\frac{\Delta\theta}{\Delta u_M}=\frac{2}{u_{min}+u_{max}}\frac{\Delta\theta}{\Delta u_M}\qquad(2.5.4)$$

- Si la entrada ya es interferente (k_I conocido) hay que calcular un k_M no nulo antes de afirmar que también es modificadora; como $\Delta\theta=k_I\Delta u_{I,M}+k_M\frac{u_{min}+u_{max}}{2}\Delta u_{I,M}$:

$$k_M=\frac{2}{u_{min}+u_{max}}\left[\frac{\Delta\theta}{\Delta u_{I,M}}-k_I\right]\qquad(2.5.5)$$

**Parte 3 — Prueba de repetibilidad**
- En el ambiente normal de trabajo (planta o cuarto de control, con u_M, u_I variando aleatoriamente), con u constante en un valor medio y θ medida durante un periodo prolongado (idealmente varios días) → θ_k, k = 1…N.

$$\bar\theta=\frac1N\sum_{k=1}^{N}\theta_k\qquad(2.5.6)\qquad\sigma_0=\sqrt{\frac1N\sum_{k=1}^{N}(\theta_k-\bar\theta)^2}\qquad(2.5.7)$$

- Se hace un **histograma** de θ_k para estimar p(θ) y compararla con la gaussiana (Cap. 4).

```json
{
  "type": "chart",
  "id": "chart-014",
  "page": 37,
  "pdf_page": 55,
  "title": "Figura 2.13: Comparación del histograma con una función densidad de probabilidad gaussiana",
  "chart_type": "histogram + curva gaussiana",
  "axes": {"x": {"label": "θ (Voltios)", "range": [0.97, 1.03], "ticks": [0.97, 0.98, 0.99, 1.00, 1.01, 1.02, 1.03]}, "y": {"label": "frecuencia (conteo)", "ticks": [0, 20, 40]}},
  "series": [{"name": "histograma de θ", "values": null}, {"name": "gaussiana ajustada", "values": null}],
  "description": "Valores de θ concentrados alrededor de 1.00 V; las alturas exactas de las barras no son legibles en la capa de texto. El título del eje y no aparece en el original (solo marcas 0, 20, 40).",
  "basis": "capa de texto (no verificado visualmente)"
}
```

### 2.6 Precisión de los sistemas de medida en estado estacionario

La **precisión es una propiedad del sistema de medida completo**, no de un elemento aislado. Error de medición:

$$\varepsilon=\text{valor medido}-\text{valor verdadero}\qquad(2.6.1)\qquad\varepsilon=\text{salida del sistema}-\text{entrada del sistema}\qquad(2.6.2)$$

#### 2.6.1 Error en la medida de un sistema con elementos ideales

Sistema de n elementos ideales en serie (lineales, sin entradas ambientales, a = 0): θ_i = k_i·u_i (2.6.3); θ = θ_n = k₁k₂k₃⋯k_n·u (2.6.4). Con un sistema de medida completo ε = θ − u:

$$\varepsilon=(k_1k_2k_3\cdots k_n-1)\,u\qquad(2.6.5)$$

Si $k_1k_2k_3\cdots k_n=1$ (2.6.6) entonces ε = 0 (sistema perfectamente preciso).

*Ejemplo (Fig. 2.15):* termocupla 40 μV/°C, amplificador 10³ V/V, indicador de bobina móvil 25 °C/V → k₁k₂k₃ = 40×10⁻⁶ × 10³ × 25 = 1, que **parece** perfectamente preciso. Pero ningún elemento es ideal: la termocupla es no lineal (la sensibilidad deja de ser 40 μV/°C) y la temperatura de la unión de referencia cambia la fem; la salida del amplificador depende de la temperatura ambiente; y k₃ del indicador depende de la rigidez del resorte restaurador (afectada por temperatura ambiente y uso), desviándose del valor nominal de 25 °C/V. Por tanto k₁k₂k₃ = 1 no se mantiene siempre y el sistema tiene error, que debe cuantificarse con el modelo general del elemento.

```json
{
  "type": "diagram",
  "id": "diagram-008",
  "page": 37,
  "pdf_page": 55,
  "title": "Figura 2.14: Error en la medida",
  "elements": ["Elemento 1 (k1)", "Elemento 2 (k2)", "Elemento 3 (k3)", "u (valor verdadero)", "θ1 = u2", "θ2 = u3", "θ3 = θ (valor medido)"],
  "relationships": ["Valor verdadero -> 1 -> 2 -> 3 -> Valor medido (cadena en serie)"],
  "description": "Cadena de n elementos en serie usada para deducir el error de un sistema ideal."
}
```

```json
{
  "type": "diagram",
  "id": "diagram-009",
  "page": 38,
  "pdf_page": 56,
  "title": "Figura 2.15: Sistema simple de medida de la temperatura",
  "elements": [
    {"name": "Termocupla", "gain": "40 μV/°C", "output": "f.e.m. (μV)"},
    {"name": "Amplificador", "gain": "1000 V/V", "output": "voltios"},
    {"name": "Indicador", "gain": "25 °C/V"}
  ],
  "relationships": ["Temperatura verdadera -> termocupla -> amplificador -> indicador -> temperatura medida"],
  "description": "Ejemplo numérico donde k1·k2·k3 = 1 sin que el sistema sea realmente exacto."
}
```

#### 2.6.2 Técnicas de reducción de error

Con la calibración se identifican los elementos de comportamiento no ideal más dominante y se diseñan estrategias de compensación.

**Síntesis propia (tabla de problemas y soluciones basada en el documento):**

| Problema | Técnica de compensación | Cómo funciona / ejemplo del documento |
|---|---|---|
| Elemento no lineal | **Elemento de compensación no lineal** C(U) tal que C[U(u)] se acerque a la recta ideal | Puente de deflexión que compensa la no linealidad de un termistor (Fig. 2.16) |
| Entradas ambientales (en general) | **Aislamiento** (u_M = u_I ≈ 0) | Unión de referencia de una termocupla en recinto de temperatura controlada; resorte de elevación que aísla de vibraciones |
| Entradas ambientales | **Sensibilidad ambiental cero** (k_M = k_I = 0) | Aleación con coeficiente de expansión térmica cero para galga extensométrica; en la práctica la galga metálica se ve algo afectada por la temperatura |
| Entradas interferentes / modificadoras | **Entradas ambientales opuestas**: un segundo elemento sometido a la misma entrada produce un efecto que se cancela (Fig. 2.17a) | Termocupla Cu-constantan: k_I·u_I = −38.74·T₂ μV → elemento de compensación con salida +38.74·T₂ μV |
| Interferentes | **Sistema diferencial** (Fig. 2.17b) | Dos galgas extensométricas pareadas en ramas adyacentes de un puente, una en tensión (+f) y otra en compresión (−f): efecto de la carga ×2 y efectos de temperatura ambiente cancelados |
| Entradas modificadoras y no linealidades | **Realimentación negativa de alta ganancia** (Fig. 2.18) | Transductor de fuerza con amplificador de alta ganancia y elemento de realimentación (p. ej. bobina e imán permanente) que genera la fuerza de balanceo |
| Errores sistemáticos residuales | **Estimación por computador** con ecuación inversa del modelo (Fig. 2.19) | Ver más abajo |

```json
{
  "type": "diagram",
  "id": "diagram-010",
  "page": 39,
  "pdf_page": 57,
  "title": "Figura 2.16: Compensación de un elemento no lineal",
  "elements": [
    "Elemento no lineal no compensado: termistor (temperatura θ -> resistencia, Ω)",
    "Compensación: puente de deflexión (resistencia -> voltaje V)",
    "Gráfica R(θ) del termistor (valores en el eje: 12, 2 Ω; θ: 298 a 348, aprox. K)",
    "Gráfica V(R) del puente",
    "Gráfica total V(θ) casi lineal (V de 0 a 1.0)"
  ],
  "relationships": ["Temperatura -> termistor -> puente de deflexión -> voltaje; la combinación es aproximadamente lineal"],
  "description": "Compensación de la no linealidad de un termistor con un puente de deflexión. Rótulos numéricos tomados de la capa de texto; curvas no verificadas visualmente."
}
```

```json
{
  "type": "diagram",
  "id": "diagram-011",
  "page": 40,
  "pdf_page": 58,
  "title": "Figura 2.17: Compensación para entradas interferentes. (a) Usando entradas ambientales opuestas (b) Usando un sistema diferencial",
  "elements": ["Elemento sin compensar", "Elemento de compensación", "entrada ambiental interferente", "sumador (+/−)", "señal de entrada s_i"],
  "relationships": ["(a) el elemento y el de compensación reciben la misma entrada ambiental y sus efectos se cancelan al sumarse con signos opuestos", "(b) configuración diferencial con dos ramas"],
  "description": "Diagramas de bloques de dos esquemas de compensación; la capa de texto contiene solo rótulos parciales."
}
```

**Realimentación negativa de alta ganancia (Fig. 2.18).** Con ΔF = F_i − F_b, V_O = k·k_A·ΔF y F_b = k_F·V_O (2.6.7):

$$V_O=\frac{k\,k_A}{1+k_F\,k\,k_A}\,F_i\qquad(2.6.8)$$

Si $k_Fk\,k_A\gg1$ (2.6.9):

$$V_O\approx\frac{1}{k_F}F_i\qquad(2.6.10)$$

La salida depende solo de la ganancia k_F del elemento de realimentación y no de k ni k_A; los cambios debidos a entradas modificadoras o no linealidades tienen efecto despreciable. Reemplazando k por k + k_M·u_M:

$$V_O=\frac{(k+k_Mu_M)k_A}{1+k_F(k+k_Mu_M)k_A}F_{IN}\qquad(2.6.11)\qquad V_{OUT}\approx\frac{F_{IN}}{k_F}\ \text{si}\ k_F(k+k_Mu_M)k_A\gg1\qquad(2.6.12)$$

Se debe asegurar que k_F no tenga cambios por efectos no lineales o ambientales; como el amplificador entrega la potencia, el elemento de realimentación puede diseñarse para baja capacidad de potencia (mayor linealidad, menor susceptibilidad ambiental). El texto anuncia dos dispositivos que emplean este principio (transmisores de corriente), que se discutirán más adelante.

```json
{
  "type": "diagram",
  "id": "diagram-012",
  "page": 41,
  "pdf_page": 59,
  "title": "Figura 2.18: Transductor de fuerza en lazo cerrado",
  "elements": ["Fuerza de entrada F_i", "Sumador (+/−)", "Elemento sensor", "Amplificador de ganancia alta", "Elemento de retroalimentación", "Fuerza de balanceo F_b", "Tensión de salida"],
  "relationships": ["F_i - F_b -> elemento sensor -> amplificador -> tensión de salida", "Tensión de salida -> elemento de retroalimentación -> F_b (realimentación negativa)"],
  "description": "Transductor de fuerza con balance de fuerzas por realimentación."
}
```

**Estimación por computador del valor medido (Fig. 2.19).** Gracias a la caída de costo de los circuitos digitales integrados, los microcomputadores se usan como elementos procesadores de señal. Requiere un buen modelo del sistema.

- **Ecuación directa:** θ = ku + a + N(u) + k_M·u_M·u + k_I·u_I (en el original aparece con la etiqueta de referencia «(efecamb)» en lugar de un número): θ es la variable dependiente.
- **Ecuación inversa:** u es la variable dependiente; θ, u_I, u_M son independientes:

$$u=k'\theta+N'(\theta)+a'+k'_Mu_M\theta+k'_Iu_I\qquad(2.6.13)$$

  con coeficientes k′, N′(), a′… distintos de los de la ecuación directa. *(En el texto impreso el último término aparece como «k′_I u»; se interpreta como k′_I·u_I por el contexto — interpretación del convertidor.)*
- **Ejemplo (termocupla tipo T, unión de referencia a 0 °C, 0–400 °C; ajuste de mínimos cuadrados con datos de la norma BS 4937, ref. [4]):**
  - Directa: $E=3.845\times10^{-2}T+4.682\times10^{-5}T^2-3.789\times10^{-8}T^3+1.652\times10^{-11}T^4$ mV
  - Inversa: $T=22.55E-0.5973E^2+2.064\times10^{-2}E^3-3.205\times10^{-4}E^4$ °C
  - La directa es más útil para **estimar el error**; la inversa, para **reducirlo**.

> **Observación de fidelidad.** Los coeficientes de la ecuación directa de esta sección (3.845×10⁻² mV/°C = 38.45 μV/°C) no coinciden con los de (2.2.8) (38.74 μV/°C, 3.319×10⁻² μV/°C², …); el documento no explica la diferencia (distinto ajuste o fuente). Se conservan ambos.

**Procedimiento (etapas del documento):**
1. Tratar el sistema sin compensar como un solo elemento y hallar, por calibración, los parámetros k′, a′, N′… de su ecuación inversa (esto ayuda a identificar entradas ambientales u_M, u_I).
2. Conectar el estimador: un computador que almacena los parámetros del modelo, sensores ambientales que le dan estimados u′_M, u′_I y la salida U del sistema sin compensar.
3. El computador calcula un estimado inicial $u'=k'U+N'(U)+a'+k'_Mu_MU+k'_Iu_I$.
4. La presentación muestra el valor medido θ (cercano a u′); en aplicaciones de baja exigencia puede terminar aquí.
5. Si se requiere alta precisión, calibrar el sistema completo: medir θ ante entradas estándar conocidas u y calcular el error ε = θ − u (principalmente aleatorio, con posible componente sistemática corregible).
6. Ajustar por mínimos cuadrados los datos (θ_i, ε_i) a una recta:

$$\varepsilon=k\theta+b\qquad(2.6.14)$$

   (b: error residual de cero; k: escala del error residual).
7. Calcular el coeficiente de correlación entre ε y θ:

$$r=\frac{\sum_{i=1}^{n}\theta_i\varepsilon_i}{\sqrt{\sum_{i=1}^{n}\theta_i^2\times\sum_{i=1}^{n}\varepsilon_i^2}}\qquad(2.6.15)$$

   Si |r| > 0.5: correlación razonable → existe error sistemático (2.6.16: $\bar\varepsilon=\bar\theta-\bar u$) y se puede corregir (paso 8). Si |r| < 0.5: sin correlación → los errores son aleatorios y no se puede corregir.
8. Si es necesario, valor medido mejorado: $\theta'=\theta-\varepsilon=\theta-(k\theta+b)$.

```json
{
  "type": "diagram",
  "id": "diagram-013",
  "page": 46,
  "pdf_page": 64,
  "title": "Figura 2.19: Estimación computacional del valor medido utilizando la ecuación del modelo inverso",
  "elements": [
    "Sistema sin compensación (sensor inductivo no lineal -> oscilador no lineal -> disparador Schmitt)",
    "Estimador: contador de pulsos de 16 bits (0 a 65,535) + computador",
    "Presentación de datos",
    "Medidas de entrada del medio ambiente",
    "Valor real (desplazamiento verdadero, mm) -> valor medido θ (desplazamiento medido)"
  ],
  "relationships": [
    "Desplazamiento verdadero -> sensor inductivo -> oscilador -> disparador Schmitt -> pulsos/s -> contador de pulsos -> computador -> desplazamiento medido",
    "Medidas ambientales -> computador/estimador"
  ],
  "equations": {
    "inverse_model": "x = -264.1 + 0.3882·f - 2.113×10^-4·f^2 + 5.272×10^-8·f^3 - 4.928×10^-12·f^4",
    "variable_f": "frecuencia de la señal de pulsos (pulsos/s)",
    "reconstruction_note": "Los exponentes están reconstruidos desde la capa de texto y la vista rasterizada; la variable independiente se rotula con un símbolo no legible en el original, se interpreta como la frecuencia f (el texto indica que la ecuación inversa relaciona x con f)."
  },
  "description": "Sistema de medida de desplazamiento: el sensor inductivo tiene relación no lineal entre inductancia L y desplazamiento x; el oscilador, no lineal entre frecuencia f e inductancia L. El computador lee el contador al inicio y al final de un intervalo fijo para medir f y calcula x con la ecuación inversa del modelo y coeficientes guardados en memoria.",
  "basis": "texto del documento + vista rasterizada de baja resolución"
}
```

---

## Ejemplo práctico (Capítulo 2)

> **Síntesis propia basada en el documento. No constituye una reproducción literal.** El código implementa el procedimiento de calibración de 2.5 y la detección de histéresis. **No fue ejecutado con datos reales**; solo ilustra el método. Dependencias: Python 3, `numpy`. Los datos de entrada deben proveerse según el procedimiento de 11 puntos subiendo y 11 bajando, repetido 3 veces (n = 33 por sentido).

```python
import numpy as np

def calibrar(u_up, th_up, u_dn, th_dn, grado=3):
    """Ajusta polinomios por mínimos cuadrados (ec. 2.5.1) para las
    trayectorias ascendente y descendente y evalúa histéresis (2.5.2)
    y no linealidad (2.5.3)."""
    c_up = np.polyfit(u_up, th_up, grado)   # θ(u)↑
    c_dn = np.polyfit(u_dn, th_dn, grado)   # θ(u)↓

    # Dispersión de los puntos alrededor de cada curva (desv. estándar de residuos)
    disp_up = np.std(th_up - np.polyval(c_up, u_up))
    disp_dn = np.std(th_dn - np.polyval(c_dn, u_dn))

    u_min = min(u_up.min(), u_dn.min()); u_max = max(u_up.max(), u_dn.max())
    u_eval = np.linspace(u_min, u_max, 200)
    H = np.polyval(c_dn, u_eval) - np.polyval(c_up, u_eval)  # H(u) = θ↓ - θ↑
    H_max = np.max(np.abs(H))

    # Criterio del texto: histéresis significativa si la separación supera la dispersión
    histeresis_significativa = H_max > max(disp_up, disp_dn)

    # Si no es significativa, combinar ambos conjuntos en un solo polinomio
    if histeresis_significativa:
        c = None
    else:
        c = np.polyfit(np.r_[u_up, u_dn], np.r_[th_up, th_dn], grado)

    # Recta ideal (2.2.3, 2.2.4) y no linealidad N(u) = θ(u) - (k·u + a)
    res = {"histeresis_significativa": bool(histeresis_significativa), "H_max": float(H_max)}
    if c is not None:
        th_min, th_max = np.polyval(c, u_min), np.polyval(c, u_max)
        k = (th_max - th_min) / (u_max - u_min)
        a = th_min - k * u_min
        N = np.polyval(c, u_eval) - (k * u_eval + a)
        res.update(k=float(k), a=float(a),
                   N_max_pct_fsd=float(100 * np.max(np.abs(N)) / (th_max - th_min)))
    return res
```

---

## Observaciones de fidelidad acumuladas (Parte 01)

1. Tablas 2.3 vs 2.4: oxígeno (54.6584 vs 54.3584 K) y zinc (629.677 vs 692.677 K).
2. Tabla 2.3: `Wr(T90)` vacío en filas 1, 3, 4, 16, 17; letras de estado sin leyenda en el texto de la página.
3. Sección 1.5.1: notación v₀/v_s invertida entre la presentación y el desarrollo.
4. Sección 1.5.2: K_c y K_l no se definen explícitamente.
5. Sección 2.2: «características estáticas» (probablemente «estadísticas») en la definición de características sistemáticas; ≈50 μV/°C en (2.2.13) no reproducible con los cuatro términos impresos.
6. Sección 2.6.2: ecuación directa de la termocupla tipo T con coeficientes distintos de (2.2.8); ecuación (2.6.13) con término «k′_I u» y referencia «(efecamb)» sin numerar.
7. Figura 1.6 no visible en la rasterización; varias figuras de la Parte 01 se describen solo desde pie de figura y capa de texto (`basis` en cada JSON).

**Fin de la Parte 01.** La **Parte 02** comienza en el Capítulo 3 (*Características dinámicas de los sistemas de medida*, p. impresa 47 / PDF 65).
