# Fundamentos de Instrumentación — Parte 04

> **Parte 04 de ~7 · Cubre: Capítulo 5 completo, «Incertidumbre Experimental» (páginas impresas 133–142 · PDF 151–160), y Capítulo 6, «Sensores de parámetro variable», secciones 6.1 y 6.2 «Transductores potenciométricos» completa, hasta el final de 6.2.6 «Potenciómetros digitales» (páginas impresas 143–160 · PDF 161–178).**
> Continúa de la Parte 03 (terminó con la Tabla 4.6 / 4.6.5, p. 132). La Parte 05 comienza en la sección 6.3 «Transductores termorresistivos» (p. impresa 160, PDF 178, tras la ecuación 6.2.15).
> Plan revisado: por la extensión del Capítulo 6 (PDF 161–219), el resto del libro se reparte en las Partes 05–07 (6.3–6.5; 6.6–Cap. 7; Cap. 8–10 y apéndices; los rangos exactos se confirmarán al generarlas).
> Convenciones: `page` = página impresa; `pdf_page = page + 18`. IDs continuos: esta parte usa `table-016`…`table-018`, `chart-043`…`chart-047` y `diagram-027`…`diagram-037`. La Parte 05 continúa en `table-019`, `chart-048`, `diagram-038`, `image-003`.
> Leyenda: texto sin marca = contenido del documento (redactado de forma concisa, sin cambiar cifras); **«Síntesis propia»** = contenido generado por el modelo; **«Observación de fidelidad»** = discrepancia del original, conservada sin corregir.

---

## Capítulo 5. Incertidumbre experimental

### 5.1 Introducción

- El análisis de incertidumbre es parte vital de cualquier programa experimental o diseño de sistemas de medida. El capítulo da métodos para **combinar las incertidumbres de las fuentes** y estimar la del resultado final (propagación de la incertidumbre).
- Causas de incertidumbre: falta de precisión del equipo, variación aleatoria de los elementos de medición (parámetros físicos) y aproximaciones en los datos.
- Se aplica en tres momentos: (1) **diseño** (seleccionar técnicas y dispositivos); (2) **tras la toma de datos** (demostrar o verificar la validez de resultados); (3) **durante o en la validación de experimentos** (identificar acciones correctivas). Referencia normativa: ANSI/ASME (1986), ref. [1].

### 5.2 Propagación de las incertidumbres

Sea un resultado calculado $R=f(x_1,x_2,\dots,x_n)$ (5.2.1) con xᵢ variables medidas independientes. Para pequeños cambios:

$$\delta R=\sum_{i=1}^{n}\frac{\partial R}{\partial x_i}\delta x_i\qquad(5.2.2)$$

(exacta solo para δ infinitesimales). Reemplazando δxᵢ por las incertidumbres wₓᵢ y δR por w_R, y como los términos pueden ser positivos o negativos, se toman todos positivos (**estimación del máximo**):

$$w_R=\sum_{i=1}^{n}\left|\frac{\partial R}{\partial x_i}w_{x_i}\right|\qquad(5.2.3)$$

Es muy improbable que todos los términos sean máximos a la vez, por lo que (5.2.3) sobreestima; un mejor estimativo es la **raíz cuadrada de la suma de los cuadrados (rcs)**:

$$w_R=\sqrt{\sum_{i=1}^{n}\left(\frac{\partial R}{\partial x_i}w_{x_i}\right)^2}\qquad(5.2.4)$$

(bases conceptuales: Coleman y Steele, ref. [9]). Condiciones: (a) el nivel de confianza de w_R es el de las wₓᵢ, por lo que conviene evaluar todas las incertidumbres **al mismo nivel de confianza**; (b) las variables deben ser **independientes** (errores no correlacionados); si no lo son, la formulación difiere (refs. [1] y [9]).

**Método de efectos iguales (diseño inverso).** Si se conoce la precisión total requerida y se buscan las de cada componente, el problema es indeterminado (infinitas combinaciones). Se supone que cada fuente aporta el mismo error: con n términos iguales,

$$w_R=\sqrt n\left(\frac{\partial R}{\partial x}\right)w_x\ (5.2.5)\ \Rightarrow\ w_x=\frac{w_R}{\sqrt n\,(\partial R/\partial x)}\qquad(5.2.6)$$

que da el error admisible para cada medida.

> **Ejemplo 17 (del documento).** Potencia P = V·I con V = 120 ± 2 V e I = 10 ± 0.2 A (mismo nivel de confianza). ∂P/∂V = I = 10 A; ∂P/∂I = V = 120 V.
> - Error máximo (5.2.3): w_P,máx = 10 × 2 + 120 × 0.2 = **44 W** (3.67 % de P = 1200 W).
> - Mejor estimativo (5.2.4): $w_P=\sqrt{(10\times2)^2+(120\times0.2)^2}=$ **31.24 W** (2.60 %).

**Forma producto.** Si $R=C\,x_1^{\lambda_1}x_2^{\lambda_2}\cdots x_n^{\lambda_n}$ (5.2.7), (5.2.4) se simplifica a una relación de errores fraccionales:

$$\frac{w_R}{R}=\sqrt{\sum_{i=1}^{n}\left(\lambda_i\frac{w_i}{x_i}\right)^2}\qquad(5.2.8)$$

Los exponentes λᵢ pueden ser positivos o negativos. Como los términos se elevan al cuadrado antes de sumar, **dominan los de mayor valor**. (5.2.4) también sirve en la fase de diseño para determinar la precisión requerida de instrumentos y componentes.

> **Ejemplo 18 (del documento).** Potencia (hp) transmitida por un eje, medida con dinamómetro:
>
> $$P_{hp}=\frac{2\pi\nu LF}{550\,t}\ (5.2.9)=\kappa\frac{\nu LF}{t}\ (5.2.10),\quad\kappa=\frac{2\pi}{12\times550}=9.5200\times10^{-4}$$
>
> con ν = revoluciones del eje durante el tiempo t, L = longitud del brazo del par, F = fuerza en el extremo del brazo [lbf], t = duración [s]. Datos: ν = 1202 ± 1.0 rev; F = 10.12 ± 0.04 lbf; L = 15.63 ± 0.05; t = 60.00 ± 0.50 s.
>
> | Derivada parcial | Valor |
> |---|---|
> | ∂P/∂ν = κ·L·F/t | 2.5097×10⁻³ |
> | ∂P/∂L = κ·ν·F/t | 0.19301 |
> | ∂P/∂F = κ·ν·L/t | 0.29809 |
> | ∂P/∂t = −κ·ν·L·F/t² | 5.0278×10⁻² (magnitud) |
>
> - P_hp = 9.52×10⁻⁴ × 1202 × 15.63 × 10.12 / 60 = **3.0167 hp**.
> - Error máximo (5.2.3): 2.5097×10⁻³·1.0 + 0.19301·0.05 + 0.29809·0.04 + 5.0278×10⁻²·0.5 = **4.9223×10⁻² hp**. Resultado: **P = 3.017 ± 0.049 hp ≈ ± 1.6 %**.
> - Estimativo rcs (5.2.4): w_hp = **2.9556×10⁻² hp**. «El error es quizá tan grande como 0.049 hp, pero probablemente no mayor que 0.029 hp».
> - **Diseño inverso** (precisión del 0.5 % con n = 4, ec. 5.2.6): w_ν = 3.0167×0.005/(√4 × 2.5097×10⁻³) = **3.005 rev** (5.2.11); w_L = **3.9074×10⁻² pulg** (5.2.12); w_F = **0.0253 lbf** (5.2.13); w_t = **0.15 s** (5.2.14). Si el mejor instrumento disponible para F solo llega a 0.04 lbf (en lugar de 0.025), P_hp no podría medirse al 0.5 %; pero eso no obliga a medir ν, L o t con mayor precisión que la requerida, pues pueden **compensarse** haciendo una o más de esas medidas más precisas.

> **Observación de fidelidad.** El enunciado define L en «pies» (símbolo ´), pero la solución convierte con el factor 12 (2π/(12×550)), es decir, trata L en pulgadas y las incertidumbres de L en «pulg». El resultado 3.017 hp es coherente con L en pulgadas. Se conserva lo impreso.

#### 5.2.1 Consideraciones de sesgo y precisión

- En las primeras fases de diseño no es práctico separar sesgo y precisión: se usa (5.2.4) con las incertidumbres globales. En un análisis detallado se mantienen separados el **límite de sesgo B** (error sistemático) y el **límite de precisión P** (error aleatorio).
- El error de precisión es aleatorio en cada medida y su estimación depende del tamaño de la muestra; el de sesgo **no varía en lecturas repetidas** y es independiente de n.
- **Índice de precisión** (desviación estándar muestral) y **límite de precisión** de una medida simple con la t de Student (nivel de confianza, p. ej. 95 %, y grados de libertad):

$$S_x=\left[\frac1{n-1}\sum(x_i-\bar x)^2\right]^{1/2}\ (5.2.15),\qquad P_{x_i}=t\,S_x\ (5.2.16)$$

- Para la incertidumbre de la **media**: $S_{\bar x}=S_x/\sqrt n$ (5.2.17), $P_{\bar x}=t\,S_{\bar x}$ (5.2.18) y el intervalo de precisión $\Delta P_{\bar x}=\pm\dfrac{tS_x}{\sqrt n}$ (5.2.19). ANSI/ASME 86 aplica la t también a una **medida individual** cuando S proviene de una muestra pequeña (a diferencia del intervalo de la media del Cap. 4).
- El límite de sesgo B permanece constante si se repite la prueba en las mismas condiciones; incluye errores conocidos no eliminados por calibración y otros errores fijos estimables. **Incertidumbre total:**

$$w=\sqrt{P^2+B^2}\qquad(5.2.20)$$

  Se recomienda (ANSI/ASME 86) un **nivel de confianza del 95 %** para el análisis de incertidumbre.
- Errores de sesgo grandes pueden venir de la instalación (ejemplo: medir la temperatura de un gas caliente en un contenedor frío; la transferencia de calor por radiación entre paredes y sensor da una lectura inferior a la verdadera). Errores dinámicos y espaciales también pueden ser grandes. Muchas veces el sesgo se reduce corrigiendo analíticamente los datos, pero la corrección es incierta y **no lo reduce a cero**.

> **Observación de fidelidad.** El texto compara el uso de t aquí con «la desigualdad (4.4.14)», pero esa ecuación es el criterio de Thompson; el intervalo de la media con t es (4.3.49). Además, la frase «El nivel de confianza en la incertidumbre, w, que el nivel de confianza en P» está incompleta en el original.

> **Ejemplo 19 (del documento).** Valor calórico de un campo de gas natural, 10 muestras (kJ/kg): 48530, 48980, 50210, 49860, 48560, 49540, 49270, 48850, 49320, 48680. Sin error de precisión del calorímetro; nivel de confianza 95 % y ν = 9 → t = 2.26. x̄ = **49180 kJ/kg**; S = **566.3 kJ/kg**. (a) Límite de precisión de cada medida: P = 2.26 × 566.3 = **1280 kJ/kg**. (b) De la media: P_x̄ = 2.26 × 566.3/√10 = **404.7 kJ/kg**.

> **Ejercicio 2 (del documento).** El calorímetro tiene una precisión del 1.5 % del rango total 0–100000 kJ/kg. Sesgo B = 0.015 × 10⁵ = 1500 kJ/kg (se supone que la «exactitud» se define solo con el sesgo). (a) Incertidumbre total del valor medio: $w=\sqrt{404.7^2+1500^2}=$ **1553.6 kJ/kg** (3.1 % de la media). (b) Medida individual de 49500 kJ/kg: $w_i=(1280^2+1500^2)^{1/2}=$ **1971.9 kJ/kg** (4 % del valor medido).

> **Ejemplo 20 (del documento).** Un sensor mide la temperatura T_g de un gas caliente en un ducto (Fig. 5.1): lectura T_s = 773 K, pared T_w = 723 K; el sensor se enfría por radiación hacia la pared. Corrección:
>
> $$\Delta T_c=T_g-T_s=\frac{\epsilon}{h}\,\sigma\,(T_s^4-T_w^4)\qquad(5.2.21)$$
>
> con σ = 5.669×10⁻⁸ (constante de Stefan-Boltzmann), h = 50 ± 10 W/(m²·K) el coeficiente de transferencia de calor y ε = 0.9 (+0.1 / −0.2) la emisividad del sensor (temperaturas en K). Se desprecia la incertidumbre de la medición de temperatura.
> - (a) ΔT_c = 5.669×10⁻⁸ × 0.9 × (773⁴ − 723⁴)/50 = **85.506 K** (≈ 86 K).
> - (b) Por (5.2.8) con incertidumbre **asimétrica** de ε: $w^+_{\Delta T}=\left[(0.1/0.9)^2+(10/50)^2\right]^{1/2}=0.22879\Rightarrow0.22879\times86=\mathbf{19.676\ K}$; $w^-_{\Delta T}=\left[(0.2/0.9)^2+(10/50)^2\right]^{1/2}=0.29897\Rightarrow0.29897\times86=\mathbf{25.711\ K}$.
> - Mejor estimativo: **T_g = 773 + 86 = 859 K (+19.7 / −25.7)**. El error de sesgo (86 K) se redujo a un intervalo de +19.7/−25.7 K: el sesgo máximo bajó a menos de un tercio de su valor original.

> **Observación de fidelidad.** La constante σ se imprime con unidades «W/m²-K» (la unidad usual es W/m²·K⁴). El texto cita una «Fig. ??» sin resolver.

```json
{
  "type": "diagram",
  "id": "diagram-027",
  "page": 141,
  "pdf_page": 159,
  "title": "Figura 5.1: Error por radiación",
  "elements": ["Flujo de gas caliente, T_g (dentro del ducto)", "Sensor de temperatura, T_s", "Convección entre el gas y el sensor", "Radiación hacia la pared del ducto frío", "Pared del ducto fría, T_w"],
  "relationships": ["Gas -> sensor por convección", "Sensor -> pared por radiación (el sensor pierde calor)"],
  "description": "Esquema de un ducto con gas caliente, un sensor de temperatura y la pared más fría; ilustra que T_s < T_g por la radiación hacia la pared.",
  "basis": "vista rasterizada de baja resolución + capa de texto"
}
```

**Síntesis propia — cuándo usar cada fórmula del capítulo:**

| Situación | Fórmula | Nota |
|---|---|---|
| Cota superior, peor caso | Suma absoluta (5.2.3) | Sobreestima |
| Estimación habitual, variables independientes | rcs (5.2.4) | Mismo nivel de confianza en todas las wᵢ |
| Resultado = producto de potencias | Errores fraccionales (5.2.8) | Dominan los términos grandes |
| Definir tolerancias de componentes | Efectos iguales (5.2.6) | Supone aportes iguales |
| Combinar sesgo y precisión | w = √(P² + B²) (5.2.20) | 95 % recomendado |

---

# Capítulo 6. Sensores de parámetro variable

### 6.1 Introducción

Los transductores de parámetro variable constituyen un grupo importante de captadores y cubren la mayor parte de las aplicaciones industriales. Se caracterizan por **robustez y simplicidad constructiva**: producen una salida relacionada con la variación de un parámetro eléctrico pasivo (resistencia, capacitancia, inductancia, acoplamiento magnético, etc.) originada por una variación proporcional de la magnitud física a medir.

### 6.2 Transductores potenciométricos

Un potenciómetro es una resistencia fija sobre la que desliza un cursor (rotación, deslizamiento lineal o ambos): elemento de **tres terminales** (dos extremos de la resistencia y el cursor). Parámetros (Fig. 6.1): R resistencia total; x desplazamiento del cursor desde un extremo de referencia; R·f(x) resistencia entre el extremo de referencia y el cursor, con 0 ≤ f(x) ≤ 1. Con tensión vᵢ entre A y B:

$$v_0=R f(x)\frac{v_i}{R}=v_if(x)$$

La salida depende solo de las características constructivas del potenciómetro y del desplazamiento.

```json
{
  "type": "diagram",
  "id": "diagram-028",
  "page": 143,
  "pdf_page": 161,
  "title": "Figura 6.1: Transductor potenciométrico",
  "elements": ["Fuente v_i entre los terminales A y B", "Resistencia total R", "Cursor en la posición x", "Resistencia R·f(x) entre el cursor y B", "Tensión de salida v_o"],
  "relationships": ["v_i alimenta la resistencia R entre A y B", "v_o se toma entre el cursor y el extremo de referencia B"],
  "description": "Esquema de un potenciómetro como divisor de tensión."
}
```

**Tipos según el desplazamiento:** (a) **lineales** (cursor sobre elemento rectilíneo); (b) **angulares** (elemento en sector circular; x = ángulo girado, Fig. 6.2); (c) **multivuelta o helicoidales** (elemento helicoidal de normalmente 10 o 20 pasos; x = ángulo θ, que puede superar 360°); (d) elemento rectilíneo con cursor accionado por **tornillo sin fin** paralelo.

```json
{
  "type": "diagram",
  "id": "diagram-029",
  "page": 144,
  "pdf_page": 162,
  "title": "Figura 6.2: Potenciómetro angular",
  "elements": ["Cursor", "Elemento resistivo en sector circular", "Tensiones v_S y v_O"],
  "relationships": ["El cursor gira alrededor de un punto central sobre el elemento resistivo"],
  "description": "Potenciómetro angular; rótulos de la capa de texto: 'Cursor', 'vS', 'vO'."
}
```

Según la función f(x) se obtienen distintos tipos:

#### 6.2.1 Potenciómetro de función lineal

$$f(x)=Kx\ (6.2.1),\quad f(x_{max})=1\ \Rightarrow\ f(x)=\frac{x}{x_{max}},\quad v_0=\frac{x}{x_{max}}v_i\qquad(6.2.2)$$

#### 6.2.2 Potenciómetros logarítmicos y antilogarítmicos

Función logarítmica $f(x)=M\log\!\left(A\frac{x}{x_{max}}+B\right)$ (6.2.3). Con f(0) = 0 y f(x_max) = 1: B = 1 y M = 1/log(A + 1):

$$f(x)=\frac{\log\!\left(A\frac{x}{x_{max}}+1\right)}{\log(A+1)}\ (6.2.4),\qquad v_0=\frac1{\log(A+1)}\log\!\left(A\frac{x}{x_{max}}+1\right)v_i\ (6.2.5)$$

Hay infinitas funciones variando A; A = 0 da el caso lineal. El carácter es general (no depende de la base del logaritmo). Los **antilogarítmicos** usan la función inversa:

$$f(x)=\frac1A\left[(A+1)^{x/x_{max}}-1\right]\ (6.2.6),\qquad v_0=\frac{(A+1)^{x/x_{max}}-1}{A}v_i\ (6.2.7)$$

con A = 0 → lineal.

```json
{
  "type": "chart",
  "id": "chart-043",
  "page": 146,
  "pdf_page": 164,
  "title": "Figura 6.3: Respuesta de una función logarítmica",
  "chart_type": "line",
  "axes": {"x": {"label": "x (normalizada)", "range": [0, 1], "ticks": [0, 0.25, 0.5, 0.75, 1]}, "y": {"label": "f(x)", "range": [0, 1], "ticks": [0, 0.25, 0.5, 0.75, 1]}},
  "series": [
    {"name": "A = 1", "style": "línea continua", "values": null, "formula": "log(x+1)/log(2)"},
    {"name": "A = 10", "style": "línea de trazos", "values": null, "formula": "log(10x+1)/log(11)"},
    {"name": "A = 100", "style": "línea punteada", "values": null, "formula": "log(100x+1)/log(101)"}
  ],
  "description": "Tres curvas cóncavas hacia abajo de (0,0) a (1,1); a mayor A, más abrupta al inicio y más aplanada después.",
  "basis": "vista rasterizada de baja resolución + fórmulas del texto"
}
```

```json
{
  "type": "chart",
  "id": "chart-044",
  "page": 147,
  "pdf_page": 165,
  "title": "Figura 6.4: Respuesta de una función exponencial (antilogarítmica)",
  "chart_type": "line",
  "axes": {"x": {"label": "x (normalizada)", "range": [0, 1], "ticks": [0, 0.25, 0.5, 0.75, 1]}, "y": {"label": "f(x)", "range": [0, 1], "ticks": [0, 0.25, 0.5, 0.75, 1]}},
  "series": [
    {"name": "A = 1", "style": "línea continua", "values": null, "formula": "((A+1)^x - 1)/A"},
    {"name": "A = 10", "style": "línea de trazos", "values": null},
    {"name": "A = 100", "style": "línea punteada", "values": null}
  ],
  "description": "Tres curvas cóncavas hacia arriba de (0,0) a (1,1); a mayor A, más plana al inicio y más abrupta al final.",
  "basis": "vista rasterizada de baja resolución + fórmula (6.2.6)"
}
```

#### 6.2.3 Potenciómetros trigonométricos

Normalmente giratorios (x = θ); la tensión es proporcional al **seno o coseno** del ángulo (las únicas funciones trigonométricas acotadas). Como seno y coseno toman valores positivos y negativos, se necesita **alimentación de doble polaridad** y una construcción distinta de la de la Fig. 6.1 (Fig. 6.5: potenciómetro senoidal-cosenoidal con dos cursores a 90°). Es en realidad un conjunto de cuatro potenciómetros (un elemento resistivo por cuadrante). Para el cursor a un ángulo θ con la horizontal:

$$v_0=\frac{R(\theta)}{R(\pi/2)}v_i=v_i\sin\theta\ \Rightarrow\ R(\theta)=R\!\left(\tfrac\pi2\right)\sin\theta\ \text{(primer cuadrante)}$$

con resistencias simétricas de la misma ley en los cuatro cuadrantes.

```json
{
  "type": "diagram",
  "id": "diagram-030",
  "page": 148,
  "pdf_page": 166,
  "title": "Figura 6.5: Potenciómetro trigonométrico",
  "elements": ["Elemento resistivo con ley sinusoidal en cuatro cuadrantes", "Dos cursores a 90°", "Alimentación de doble polaridad"],
  "relationships": ["Un cursor entrega sen θ y el otro cos θ"],
  "description": "Conexiones de un potenciómetro senoidal-cosenoidal. Contenido de la figura no verificado visualmente."
}
```

#### 6.2.4 Potenciómetros funcionales

La función F(x) es general, a menudo empírica. Son de interés los **programables o generadores de funciones**: sintetizan F(x) por **aproximación por tramos rectilíneos**; tienen tomas intermedias accesibles a las que se aplican tensiones continuas preajustadas según los valores de la función (p. ej., con potenciómetros convencionales). La tensión del cursor toma esos valores al pasar por cada toma y varía linealmente entre dos adyacentes; así se construye F(x) a través de puntos discretos (x de las tomas, tensión preajustada).

#### 6.2.5 El potenciómetro como elemento del circuito

Con una carga Z_L en la salida (Fig. 6.6) se obtiene la **impedancia de entrada**:

$$Z_i=R[1-f(x)]+\frac{Z_LRf(x)}{Z_L+Rf(x)}=R\,\frac{Z_L+Rf(x)[1-f(x)]}{Z_L+Rf(x)}\qquad(6.2.8)$$

y, por Thévenin, la **impedancia de salida** es el paralelo de R·f(x) y R[1 − f(x)]:

$$Z_o=\frac{R^2f(x)[1-f(x)]}{R}=Rf(x)[1-f(x)]\qquad(6.2.9)$$

Derivando e igualando a cero, dZ/df = R[1 − 2f(x)] = 0 → **f(x) = ½** (6.2.10): la impedancia de salida es máxima cuando las resistencias entre el cursor y los extremos son iguales.

> **Observación de fidelidad.** El texto escribe «dZᵢ/df» al derivar, pero la expresión derivada es Z_o (6.2.9); la conclusión (máximo en f = ½) corresponde a Z_o. También cita una «Fig. ??» sin resolver.

```json
{
  "type": "diagram",
  "id": "diagram-031",
  "page": 149,
  "pdf_page": 167,
  "title": "Figura 6.6: Red con potenciómetro",
  "elements": ["Fuente v_1 en el lado de entrada (+/−)", "Potenciómetro con cursor W (x, f(x)) entre los extremos A y B", "Carga Z_L en la salida"],
  "relationships": ["La fuente alimenta los extremos A y B; Z_L se conecta entre el cursor y B"],
  "description": "Red usada para deducir las impedancias de entrada y salida del potenciómetro."
}
```

> **Ejemplo 21 (del documento).** Potenciómetro lineal de resistencia R cargado con kR; α = proporción del recorrido del cursor (Fig. 6.7). La salida se mide a través de αR en paralelo con kR:
>
> $$H=\frac{E_0}{E_i}=\frac{\dfrac{\alpha R\cdot kR}{\alpha R+kR}}{\dfrac{\alpha R\cdot kR}{\alpha R+kR}+(1-\alpha)R}=\frac{\alpha k}{-\alpha^2+\alpha+k}$$
>
> Para carga muy liviana (k → ∞) H → α, que es la salida sin carga.

> **Observación de fidelidad.** La frase final del ejemplo («la expresión correcta para el potenciómetro sin carga es k = α») está distorsionada en el texto extraído; el resultado es H = α cuando k → ∞.

```json
{
  "type": "diagram",
  "id": "diagram-032",
  "page": 150,
  "pdf_page": 168,
  "title": "Figura 6.7: Potenciómetro cargado con kR",
  "elements": ["Fuente v_i", "Parte superior (1−α)R", "Parte inferior αR", "Carga kR en paralelo con αR", "Salida v_o"],
  "relationships": ["La carga kR se conecta en paralelo con la parte inferior αR del potenciómetro"],
  "description": "Potenciómetro lineal con carga resistiva kR."
}
```

> **Ejemplo 22 (del documento).** Error de no linealidad por la carga (salida teórica sin carga α menos la real):
>
> $$\varepsilon=\alpha-\frac{\alpha k}{-\alpha^2+\alpha+k}=\frac{\alpha^2(1-\alpha)}{\alpha-\alpha^2+k}$$
>
> En aplicaciones de gran precisión el potenciómetro se carga muy ligeramente (**k > 10**): $\varepsilon\simeq\dfrac{\alpha^2(1-\alpha)}{k}$ (6.2.11).

```json
{
  "type": "chart",
  "id": "chart-045",
  "page": 150,
  "pdf_page": 168,
  "title": "Gráfico adimensional del error por unidad del potenciómetro en función de la rotación del eje (figura sin número, antes de la Fig. 6.8)",
  "chart_type": "line",
  "axes": {"x": {"label": "x (α)", "range": [0, 1], "ticks": [0, 0.25, 0.5, 0.75, 1]}, "y": {"label": "y (error)", "range": [0, 0.125], "ticks": [0, 0.025, 0.05, 0.075, 0.1, 0.125]}},
  "series": [{"name": "ε(α)", "values": null, "visual_summary": "cero en α = 0 y α = 1, con un máximo cercano a α = 2/3"}],
  "description": "Aparece en la página 150 con el mismo título que la Figura 6.8 (que se repite en la página 151) y sin numeración propia; el rango del eje y (0–0.125) difiere del de la Fig. 6.8 (0–0.15).",
  "basis": "capa de texto"
}
```

```json
{
  "type": "chart",
  "id": "chart-046",
  "page": 151,
  "pdf_page": 169,
  "title": "Figura 6.8: Gráfico adimensional del error por unidad del potenciómetro en función de la rotación del eje",
  "chart_type": "line",
  "axes": {"x": {"label": "x (α)", "range": [0.25, 1], "ticks": [0.25, 0.5, 0.75, 1]}, "y": {"label": "y (error)", "range": [0, 0.15], "ticks": [0, 0.025, 0.05, 0.075, 0.1, 0.125, 0.15]}},
  "series": [{"name": "ε(α)", "values": null}],
  "description": "El resultado es universal si se grafica kε en lugar de ε (texto del documento).",
  "basis": "capa de texto"
}
```

> **Ejercicio 3 (del documento).** Punto de error máximo con (6.2.11): ε = (α² − α³)/k; dε/dα = (2α − 3α²)/k = 0 → α(2 − 3α) = 0 → α₁ = 0, **α₂ = 2/3**.
> **Ejercicio 4.** Valor máximo: ε = (2/3)²(1 − 2/3)/k = (4/9)(1/3)/k = **4/(27k)**; para k = 10, ε = 4/270 ≈ **1.5 %**. Regla práctica: **ε_máx ≈ 15/k %**.

Para desarrollar **características no lineales**, los potenciómetros pueden cargarse de varias maneras: se requiere gran carga de salida para no linealidades sustanciales.

> **Ejercicio 5 (del documento).** Cargas k₁R (sobre αR) y k₂R (sobre (1−α)R) (Fig. 6.9). Tratando la red como divisor de tensión:
>
> $$H=\frac{k_1\alpha(k_2+1-\alpha)}{-\alpha^2(k_1+k_2)+\alpha(k_1+k_2)+k_1k_2}$$
>
> Funciones de carga separadas: con k₂ = ∞: $H_1=\dfrac{k_1\alpha}{-\alpha^2+\alpha+k_1}$; con k₁ = ∞: $H_2=\dfrac{\alpha(k_2+1-\alpha)}{-\alpha^2+\alpha+k_2}$. La Fig. 6.10 muestra curvas «universales» para varios valores de k₁ y k₂ que permiten investigar posibilidades de modelación no lineal.

```json
{
  "type": "diagram",
  "id": "diagram-033",
  "page": 152,
  "pdf_page": 170,
  "title": "Figura 6.9: Potenciómetro cargado",
  "elements": ["Fuente v_i", "Resistencia (1−α)R con carga k₂R", "Resistencia αR con carga k₁R", "Salida v_o"],
  "relationships": ["Cada tramo del potenciómetro tiene una carga resistiva en paralelo (k₁R abajo, k₂R arriba)"],
  "description": "Potenciómetro con dos cargas, base del Ejercicio 5."
}
```

```json
{
  "type": "chart",
  "id": "chart-047",
  "page": 153,
  "pdf_page": 171,
  "title": "Figura 6.10: Curvas de carga de potenciómetros usados para formar funciones no lineales",
  "chart_type": "line (familia de curvas)",
  "axes": {"x": {"label": "x (ángulo del eje, normalizado)", "range": [0, 1], "ticks": [0, 0.1, 0.2, 0.3, 0.4, 0.5, 0.6, 0.7, 0.8, 0.9, 1]}, "y": {"label": "y (salida normalizada)", "range": [0, 1], "ticks": [0, 0.1, 0.2, 0.3, 0.4, 0.5, 0.6, 0.7, 0.8, 0.9, 1]}},
  "series": [{"name": "curvas H1(α; k1) y H2(α; k2) para varios k1, k2", "values": null, "visual_summary": "familia de curvas entre (0,0) y (1,1), unas por debajo y otras por encima de la diagonal"}],
  "description": "Los valores de k1 y k2 de cada curva no se indican en el texto extraído.",
  "basis": "vista rasterizada de baja resolución + capa de texto"
}
```

> **Ejemplo 23 (del documento).** Red de n potenciómetros con resistencias R₁…Rₙ conectadas a un nodo cero (Fig. 6.11), con carga R_L a tierra. Demostrar que el voltaje del nodo es la suma (ponderada) de los voltajes de entrada. Con V₀ = V₁ − I₁R₁ = … = Vₙ − IₙRₙ, I_k = (V_k − V₀)G_k (G_k = 1/R_k) y la suma de corrientes igual a la corriente a tierra V₀G₀:
>
> $$V_0=V_1\frac{G_1}{G_T}+V_2\frac{G_2}{G_T}+V_3\frac{G_3}{G_T}+\cdots+V_n\frac{G_n}{G_T},\quad G_T=G_1+\dots+G_n\ \ (\text{así lo imprime el documento})\qquad(6.2.12)$$
>
> *(Estrictamente, en la deducción del documento G_T incluye también la conductancia a tierra G₀; el Ejemplo 24 usa G_T = G₁ + G₂ + G₀.)*

```json
{
  "type": "diagram",
  "id": "diagram-034",
  "page": 153,
  "pdf_page": 171,
  "title": "Figura 6.11: Red con potenciómetros",
  "elements": ["n potenciómetros alimentados con ±V cuyos cursores entregan V1…Vn", "Resistencias R1…Rn", "Corrientes I1…In", "Nodo cero (punto nulo)", "Resistencia de carga R_L / R_0 a tierra"],
  "relationships": ["Cada cursor se conecta mediante R_k al nodo cero; el nodo cero se conecta a tierra por R_L (R_0)"],
  "description": "Red sumadora con potenciómetros."
}
```

> **Ejemplo 24 (del documento).** Dos potenciómetros de 1000 Ω (Fig. sin número) alimentados como en la figura; P₁ en +7 V y P₂ ajustado para producir un valor mínimo de 0 en el punto cero. Con (6.2.12): $V_0=V_1\frac{G_1}{G_T}+V_2\frac{G_2}{G_T}$, G_T = G₁ + G₂ + G₀. El documento sustituye G₁ = G₂ = 10⁻⁴, G₀ = 10⁻⁵, G_T = 21×10⁻⁵ → $V_0=\frac{10}{21}(V_1+V_2)$. Para anular el error con V₁ = +7 V, **V₂ = −7 V**. Las cargas son idénticas en ambos potenciómetros, así que en equilibrio **no hay imprecisión en la posición del eje**; **la impedancia de entrada R₀ del amplificador afecta el factor de escalamiento pero no la posición del punto nulo**.

> **Observación de fidelidad.** El enunciado dice potenciómetros de 1000 Ω (G = 10⁻³ S), pero la solución usa G₁ = G₂ = 10⁻⁴ (con unidad «Ω» en lugar de S) y G₀ = 10⁻⁵ sin dar R₀; además, no calcula numéricamente la corriente por el cursor que pide el enunciado.

> **Ejercicio 6 (del documento).** Los potenciómetros desarrollan su salida total (20 V) en 320° de giro. Si P₂ se gira 1° de su posición nula: V₂ = −7 + ΔV con ΔV = 20/320 = 1/16 V por grado (el texto extraído lo imprime «1/116»). Error en el punto cero: $V_0=\frac{10}{21}\cdot\frac1{16}\approx30$ mV → **gradiente ≈ 30 mV/grado**.

#### 6.2.6 Potenciómetros digitales

Potenciómetros programables: **potenciómetros digitales (PD)**, dispositivos resistivos variables (VR) de 2ⁿ posiciones (n = 8 → 256 posiciones), que hacen el mismo ajuste electrónico que los mecánicos. Cada canal consta de: (1) un resistor fijo con toma central (cursor), cuyo valor se fija por un código digital; (2) un **latch** del VR donde se programa la resistencia cursor-extremos (varía linealmente con el código); (3) un **registro de desplazamiento serie-paralelo** que se carga por interfaz serie y actualiza el latch. Ejemplo comercial: **AD5260/AD5262** (Fig. 6.12): dos canales, registro serie de 9 bits cada uno; cada bit se transfiere en el flanco positivo de CLK.

```json
{
  "type": "diagram",
  "id": "diagram-035",
  "page": 156,
  "pdf_page": 174,
  "title": "Figura 6.12: Diagrama de bloques funcionales del AD5262",
  "elements": ["Interfaz serie: CLK, CS (selector), SDI, SDO", "Dos registros serie (9 bits) y dos latches RDAC", "Dos canales con terminales A, W (cursor), B", "Entradas PR (preset) y SHDN (apagado)", "Alimentación y tierra"],
  "relationships": ["SDI/CLK/CS -> registro de desplazamiento -> latch RDAC -> resistor variable (A-W-B)", "SDO -> encadenamiento con el SDI del siguiente circuito"],
  "description": "Diagrama de bloques del potenciómetro digital de dos canales. Detalles de pines no verificados a plena resolución.",
  "basis": "vista rasterizada de baja resolución + texto"
}
```

**Interfaz digital.** Interfaz serial de tres hilos: reloj (CLK), selector de circuito (CS) y datos serie (SDI). CLK sensible al flanco positivo requiere transiciones limpias para evitar transferencias incorrectas. Con CS bajo el reloj carga el dato en el registro serie en cada flanco positivo (Tabla 6.1). La salida de datos serie (SDO) tiene un FET de canal n de drenador abierto y requiere un resistor de *pull-up* (p. ej. R_p = 2 kΩ) para pasar los datos al SDI del siguiente circuito.

```json
{
  "type": "diagram",
  "id": "diagram-036",
  "page": 157,
  "pdf_page": 175,
  "title": "Figura 6.13: Diagrama de bloques de la estructura interna de un potenciómetro digital",
  "elements": ["Registro serie de entrada (8 bits + bit de dirección)", "Decodificación de dirección (A0)", "Latches RDAC #1 y #2", "Redes resistivas con 256 posiciones", "Terminales A1/W1/B1 y A2/W2/B2", "Lógica de preajuste (PR) y apagado (SHDN)"],
  "relationships": ["SDI -> registro serie -> latch seleccionado por A0 -> posición del cursor"],
  "description": "Detalle interno del AD5262; los rótulos específicos no se verificaron a plena resolución."
}
```

```json
{
  "type": "table",
  "id": "table-016",
  "page": 158,
  "pdf_page": 176,
  "title": "Tabla 6.1: Tabla de verdad del control de la lógica de entrada",
  "headers": ["CLK", "CS", "PR", "SHDN", "Register Activity"],
  "rows": [
    ["L", "L", "H", "H", "No SR effect, enables SDO pin"],
    ["P", "L", "H", "H", "Shift one bit in from the SDI pin. The eighth previously entered bit is shifted out of the SDO pin."],
    ["X", "P", "H", "H", "Load SR data into RDAC latch based on A0 decode (A0 = 0, RDAC #1; A0 = 1, RDAC #2)"],
    ["X", "H", "H", "H", "No Operation"],
    ["X", "X", "L", "H", "Sets all RDAC latches to midscale, wiper centered, & SDO latch cleared."],
    ["X", "H", "P", "H", "Latches all RDAC latches to 80H."],
    ["X", "H", "H", "L", "Open circuits all resistor A-terminals, connects W to B, turns off SDO output transistor."]
  ],
  "notes": "NOTE: P = positive edge, X = don't care, SR = shift register. La tabla está en inglés en el original (se conserva).",
  "source": null
}
```

**Programación del resistor variable.** Resistencia nominal R_AB (entre A y B) disponible en **20 kΩ, 50 kΩ y 200 kΩ**; el VR tiene 256 puntos de contacto accesibles al cursor más el terminal B; los datos de 8 bits del latch RDAC se decodifican para seleccionar una de 256 posiciones. Para 20 kΩ: la primera posición (00H) tiene, por la **resistencia de contacto del cursor de 60 Ω**, un mínimo de 60 Ω entre W y B; la segunda (01H) es $R_{WB}=\frac{R_{AB}}{256}+R_W=78\ \Omega+60\ \Omega=138\ \Omega$; la siguiente (02H) 216 Ω (78×2 + 60), y así sucesivamente; el último punto es 19982 Ω (R_AB − 1 LSB + R_W). El cursor no conecta directamente al terminal B (Fig. 6.14).

$$R_{WB}(D)=\frac{D}{256}R_{AB}+R_W\qquad(6.2.13)$$

(D = equivalente decimal del código de 8 bits). Con R_AB = 20 kΩ, V_B = 0 V y A abierto:

```json
{
  "type": "table",
  "id": "table-017",
  "page": 158,
  "pdf_page": 176,
  "title": "Tabla 6.2: Valores característicos en el potenciómetro digital",
  "headers": ["D [decimal]", "R_WB [Ω]", "Estado de salida"],
  "rows": [[256, 19982, "Escala plena"], [128, 10060, "Escala media"], [1, 138, "1 LSB"], [0, 60, "Escala cero"]],
  "notes": "Resultados iguales si el terminal A se conecta a W.",
  "source": null
}
```

> **Observación de fidelidad.** Con (6.2.13), D = 256 daría R_WB = 20060 Ω; el valor 19982 Ω de la fila «256» es el de D = 255 (R_AB − 1 LSB + R_W), consistente con el texto («el último punto se alcanza en 19982 Ω»). En la Tabla 6.3, «D = 0» da 20060 Ω.

**Precaución:** en escala cero la resistencia es muy baja; la corriente entre W y B debe limitarse a **5 mA** o podría destruirse el conmutador interno.

```json
{
  "type": "diagram",
  "id": "diagram-037",
  "page": 159,
  "pdf_page": 177,
  "title": "Figura 6.14: Circuito RDAC equivalente",
  "elements": ["Terminales A, W (cursor) y B", "Escalera de resistores (R_AB/256 cada paso)", "Conmutadores analógicos controlados por el latch/decodificador RDAC", "Entradas D0…D7, SHDN", "Resistencia de contacto R_W"],
  "relationships": ["El decodificador del latch cierra uno de los conmutadores y selecciona el punto de la escalera conectado al cursor W"],
  "description": "Modelo simplificado del RDAC; elementos tomados de la capa de texto y del contexto."
}
```

**Modo inverso (R_WA).** La resistencia cursor-A también se controla digitalmente (B abierto o unido al cursor); empieza en el máximo y **disminuye** al aumentar el código:

$$R_{WA}(D)=\frac{256-D}{256}R_{AB}+R_W\qquad(6.2.14)$$

```json
{
  "type": "table",
  "id": "table-018",
  "page": 160,
  "pdf_page": 178,
  "title": "Tabla 6.3: Valores característicos en el potenciómetro digital en modo inverso",
  "headers": ["D [decimal]", "R_WB [Ω] (según encabezado impreso; corresponde a R_WA)", "Estado de salida"],
  "rows": [[256, 60, "Escala plena"], [128, 10060, "Escala media"], [1, 19982, "1 LSB"], [0, 20060, "Escala cero"]],
  "notes": "El encabezado impreso dice R_WB, pero los valores corresponden a R_WA según (6.2.14).",
  "source": null
}
```

La distribución típica de R_AB de canal a canal está ajustada en ±1 %.

**Programación como divisor de tensión.** El PD genera tensiones W-B y W-A proporcionales a la tensión de entrada A-B. Ignorando la resistencia de contacto: con A a +5 V y B a tierra, la salida W-B va de 0 V hasta 1 LSB menos que +5 V:

$$V_W(D)=\frac{D}{256}V_A+\frac{256-D}{256}V_B\qquad(6.2.15)$$

El modo divisor es **más preciso con la temperatura** que el modo reóstato: la salida depende de la **relación** de los resistores internos R_WA y R_WB y no de sus valores absolutos.

---

## Ejemplo práctico (Capítulo 5 y sección 6.2)

> **Síntesis propia basada en el documento. No constituye una reproducción literal.** Funciones en Python para propagar incertidumbres (suma absoluta y rcs, con derivadas por diferencias finitas), combinar sesgo y precisión, y calcular las resistencias de un potenciómetro digital de 8 bits y la salida de un potenciómetro cargado. Dependencias: Python 3 y `numpy`. **Se ejecutó con los datos de los Ejemplos 17, 18 y del Ejercicio 2, y con las Tablas 6.2/6.3**, y reprodujo 44 W y 31.24 W; 0.0492 hp (máx.) y 0.0296 hp (rcs); 1553.6 kJ/kg; y R_WB = 60, 138.1, 10060, 19981.9 y 20060 Ω para D = 0, 1, 128, 255, 256 (R_WA es la secuencia inversa). No se probó con datos experimentales.

```python
import numpy as np

def propagacion(f, x, w, h=1e-6):
    """Incertidumbre de R = f(x1..xn): suma absoluta (5.2.3) y raíz cuadrada de
    la suma de cuadrados (5.2.4), con derivadas parciales por diferencias finitas."""
    x = np.asarray(x, float); w = np.asarray(w, float)
    d = np.array([(f(*(x + h * np.eye(len(x))[i] * max(1, abs(x[i])))) -
                   f(*(x - h * np.eye(len(x))[i] * max(1, abs(x[i]))))) /
                  (2 * h * max(1, abs(x[i]))) for i in range(len(x))])
    return np.sum(np.abs(d * w)), np.sqrt(np.sum((d * w) ** 2))

def incertidumbre_total(P, B):
    """w = sqrt(P^2 + B^2) (5.2.20)."""
    return np.hypot(P, B)

def rwb_pot_digital(D, Rab=20000.0, Rw=60.0, bits=8):
    """R_WB(D) = D/2^bits * Rab + Rw (6.2.13)."""
    return D / 2**bits * Rab + Rw

def rwa_pot_digital(D, Rab=20000.0, Rw=60.0, bits=8):
    """R_WA(D) = (2^bits - D)/2^bits * Rab + Rw (6.2.14)."""
    return (2**bits - D) / 2**bits * Rab + Rw

def carga_potenciometro(alpha, k):
    """Salida normalizada de un potenciómetro lineal cargado con kR (Ej. 21)."""
    return alpha * k / (-alpha**2 + alpha + k)
```

---

## Observaciones de fidelidad acumuladas (Parte 04)

1. Ejemplo 17: «∂R/∂I» escrito en lugar de ∂P/∂I (error de notación evidente).
2. Ejemplo 18: L definida en pies pero tratada en pulgadas (factor 12).
3. Sección 5.2.1: referencia incorrecta a (4.4.14); frase incompleta sobre el nivel de confianza de w.
4. Ejemplo 20: unidad de σ impresa «W/m²-K»; «Fig. ??» sin resolver.
5. Sección 6.2.5: derivación escrita sobre Zᵢ pero aplicada a Z_o; «Fig. ??» sin resolver; Ejemplo 21: frase final distorsionada; la figura de «error por unidad» aparece dos veces con el mismo título (una sin número).
6. Ecuación (6.2.12): G_T se define sin G₀ en el texto, pero el Ejemplo 24 sí lo incluye.
7. Ejemplo 24: G = 10⁻⁴ frente a potenciómetros de 1000 Ω; no se calcula la corriente pedida; R₀ no se da. Ejercicio 6: «1/116» extraído por «1/16».
8. Tabla 6.2: la fila D = 256 usa 19982 Ω (valor de D = 255); Tabla 6.3: encabezado R_WB en lugar de R_WA.
9. Varias figuras de esta parte (6.1, 6.2, 6.5–6.7, 6.9, 6.11–6.14) se describen solo desde pie de figura, capa de texto y contexto; las figuras 5.1, 6.3, 6.4, 6.10, 6.12, 6.13 y 6.14 se vieron a baja resolución (campo `basis` en cada JSON).

**Fin de la Parte 04.** La **Parte 05** comienza en la sección 6.3 *Transductores termorresistivos* (p. impresa 160 / PDF 178).
