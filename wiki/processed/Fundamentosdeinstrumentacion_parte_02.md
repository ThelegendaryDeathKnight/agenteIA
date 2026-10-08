# Fundamentos de Instrumentación — Parte 02

> **Parte 02 de ~5 · Cubre: Capítulo 3 completo, «Características dinámicas de los sistemas de medida» (páginas impresas 47–92 · páginas PDF 65–110).**
> Continúa de la Parte 01 (que terminó en la Fig. 2.19, p. 46). La Parte 03 comienza en el Capítulo 4, «Análisis Estadístico de Datos Experimentales» (p. impresa 93 / PDF 111).
> Convenciones: `page` = página impresa; `pdf_page = page + 18`. IDs continuos: esta parte usa `chart-015`…`chart-027`, `diagram-014`…`diagram-026` e `image-002`. **No hay tablas numeradas en este capítulo**; la Parte 03 continúa en `table-008`, `chart-028`, `diagram-027`, `image-003`.
> Leyenda: texto sin marca = contenido del documento (redactado de forma concisa, sin cambiar cifras); **«Síntesis propia»** = contenido generado por el modelo; **«Observación de fidelidad»** = discrepancia del original, conservada sin corregir.

---

## Capítulo 3. Características dinámicas de los sistemas de medida

### 3.1 Introducción

- Si la entrada u de un elemento cambia súbitamente, la salida θ no cambia instantáneamente. Ejemplo del texto: si la temperatura de una termocupla pasa de 25 °C a 100 °C, la tensión de salida tarda algún tiempo en pasar de 1 mV a 4 mV.
- La manera en que un elemento responde a un cambio repentino es su **característica dinámica**, que se describe mejor con una **función de transferencia G(s)**.
- Contenido del capítulo: (1) dinámica de elementos típicos y su G(s); (2) identificación de G(s) con señales de prueba estándar; (3) errores dinámicos de un sistema de medida de varios elementos; (4) métodos de compensación dinámica; además (5) efectos de la carga y (6) señales y ruido.

### 3.2 Función de transferencia para elementos típicos del sistema

#### 3.2.1 Elementos de primer orden

*Ejemplo base:* sensor de temperatura de salida eléctrica (termocupla o termistor), desnudo, sumergido en un fluido (Fig. 3.1). En t = 0⁻ la temperatura del sensor es igual a la del fluido: T(0⁻) = T_F(0⁻). Si T_F sube súbitamente en t = 0, el balance de calor es: *tasa de calor entrante − tasa de calor saliente = tasa de cambio del contenido de calor del sensor*. Con T_F > T la tasa saliente es cero y:

$$W = U A\,(T_F - T)\ \text{[W]}\qquad(3.2.1)$$

con U [W·m⁻²·°C⁻¹] el coeficiente global de transferencia de calor y A [m²] el área efectiva; el incremento del contenido de calor del sensor, con masa m [kg] y calor específico C [J·kg⁻¹·°C⁻¹] constantes, es

$$\text{tasa} = mC\,\frac{d}{dt}\left[T-T(0^-)\right]\qquad(3.2.2)$$

Definiendo ΔT = T − T(0⁻) y ΔT_F = T_F − T_F(0⁻):

$$\frac{mC}{UA}\frac{d\Delta T}{dt}+\Delta T=\Delta T_F\qquad(3.2.3)$$

Es lineal, de primer orden (la mayor derivada es dΔT/dt). La cantidad mC/UA tiene dimensión de tiempo (kg·J·kg⁻¹·°C⁻¹ / (W·m⁻²·°C⁻¹·m²) = J/W = s) y es la **constante de tiempo τ**:

$$\tau\frac{d\Delta T}{dt}+\Delta T=\Delta T_F\qquad(3.2.4)$$

Se introduce la transformada de Laplace $\bar f(s)=\int_0^\infty e^{-st}f(t)\,dt$ (3.2.5), con s = σ + jω. Con ΔT(0⁻) = 0:

$$\tau[s\Delta T-\Delta T(0^-)]+\Delta T(s)=\Delta T_F(s)\ (3.2.6)\ \Rightarrow\ (\tau s+1)\Delta T(s)=\Delta T_F(s)\ (3.2.7)$$

$$G(s)=\frac{\Delta T(s)}{\Delta T_F(s)}=\frac{1}{1+\tau s}\qquad(3.2.8)$$

Esa G(s) relaciona solo la temperatura del sensor con la del fluido. La relación global con la señal de salida θ es

$$\frac{\Delta\theta(s)}{\Delta T_F(s)}=\frac{\Delta\theta}{\Delta T}\,\frac{\Delta T(s)}{\Delta T_F(s)}\qquad(3.2.9)$$

donde Δθ/ΔT es la sensibilidad de estado estacionario (para un elemento ideal, la pendiente k; para uno no lineal con pequeñas fluctuaciones, la derivada dθ/dT evaluada en la temperatura de reposo T(0⁻)).

```json
{
  "type": "diagram",
  "id": "diagram-014",
  "page": 48,
  "pdf_page": 66,
  "title": "Figura 3.1: Sensor de temperatura en un fluido",
  "elements": ["sensor de temperatura desnudo", "fluido a temperatura T_F", "señal de salida θ"],
  "relationships": ["El fluido transfiere calor al sensor; el sensor entrega la salida θ"],
  "description": "Esquema del sensor sumergido en un fluido que se usa para deducir el modelo de primer orden. Solo el rótulo 'Salida θ' aparece en la capa de texto.",
  "basis": "pie de figura + capa de texto (no verificado visualmente)"
}
```

> **Ejemplo 1 (del documento).** Termocupla cobre-constantan, fluctuaciones alrededor de 100 °C, τ = 10 s. Se evalúa dE/dT a 100 °C con la ecuación (2.2.13) y el documento obtiene ΔE/ΔT = **46 μV·°C⁻¹**, de modo que
>
> $$\frac{\Delta E(s)}{\Delta T(s)}=46\cdot\frac{1}{1+10s}\qquad(3.2.10)$$

> **Observación de fidelidad (cálculo del convertidor).** Con los cuatro términos de (2.2.13) impresos en la Parte 01, a 100 °C resulta ≈ 42.8 μV/°C, no 46. Igual que en la Parte 01, las diferencias pueden deberse a los términos de orden superior no listados. Se conserva 46.

Para un elemento general con características estáticas (2.2.14) y dinámica G(s), los cambios pequeños y rápidos de Δu se evalúan con el modelo de la Fig. 3.2, donde la sensibilidad en reposo es $(\partial\theta/\partial u)_{u_0}=k+k_Mu_M+(dN/du)_{u_0}$ y u₀ es el valor de reposo.

```json
{
  "type": "diagram",
  "id": "diagram-015",
  "page": 50,
  "pdf_page": 68,
  "title": "Figura 3.2: Modelo de un elemento para cálculo de la dinámica",
  "elements": ["Δu (entrada)", "bloque de sensibilidad en reposo (∂θ/∂u)_u0", "bloque dinámico G(s)", "Δθ (salida)"],
  "relationships": ["Δu -> sensibilidad en reposo -> G(s) -> Δθ"],
  "description": "Modelo de pequeñas variaciones: ganancia estática en el punto de reposo seguida de la dinámica G(s). Rótulos 'Δ' y 'Δθ' en la capa de texto; estructura inferida del texto.",
  "basis": "capa de texto + texto del documento"
}
```

#### 3.2.2 Elementos de segundo orden

*Ejemplo base:* sensor elástico de fuerza (Fig. 3.3), con masa m [kg], resorte k [N·m⁻¹] y amortiguador ν [N·s·m⁻¹], que convierte fuerza F en desplazamiento x. En t = 0⁻: ẋ(0⁻) = 0, ẍ(0⁻) = 0 y F(0⁻) = k·x(0⁻) (3.2.11). Segunda ley de Newton (3.2.12):

$$F-kx-\nu\dot x=m\ddot x\ \ (3.2.13)\ \Rightarrow\ m\ddot x+\nu\dot x+kx=F$$

Con ΔF = F − F(0⁻), Δx = x − x(0⁻) (3.2.14) y usando (3.2.11) queda mΔẍ + νΔẋ + kΔx = ΔF, es decir

$$\frac{m}{k}\frac{d^2\Delta x}{dt^2}+\frac{\nu}{k}\frac{d\Delta x}{dt}+\Delta x=\frac1k\Delta F\qquad(3.2.15)$$

Se definen la **frecuencia natural** y el **coeficiente de amortiguación**:

$$\omega_n=\sqrt{\frac km}\ \text{[rad/s]},\qquad \zeta=\frac{\nu}{2\sqrt{k\,m}}\qquad(3.2.16)$$

(m/k = 1/ωₙ², ν/k = 2ζ/ωₙ). Forma estándar:

$$\frac{1}{\omega_n^2}\frac{d^2\Delta x}{dt^2}+\frac{2\zeta}{\omega_n}\frac{d\Delta x}{dt}+\Delta x=\frac1k\Delta F\qquad(3.2.17)$$

Transformada de Laplace con condiciones iniciales nulas (3.2.18):

$$\left[s^2+2\zeta\omega_ns+\omega_n^2\right]\Delta\bar x(s)=\frac{\omega_n^2}{k}\Delta\bar F(s)\qquad(3.2.19)$$

$$\frac{\Delta\bar x(s)}{\Delta\bar F(s)}=\frac1k\,G(s),\quad\frac1k=K\ (\text{sensibilidad estática}),\quad G(s)=\frac{\omega_n^2}{s^2+2\zeta\omega_ns+\omega_n^2}\qquad(3.2.20)$$

```json
{
  "type": "diagram",
  "id": "diagram-016",
  "page": 51,
  "pdf_page": 69,
  "title": "Figura 3.3: Modelo masa-resorte-amortiguador para un sensor elástico de fuerza",
  "elements": ["Masa m", "Resorte k (fuerza kx)", "Amortiguador ν (fuerza νẋ)", "desplazamiento x"],
  "relationships": ["La fuerza de entrada F actúa sobre la masa; el resorte y el amortiguador se oponen al movimiento"],
  "description": "Modelo conceptual de segundo orden. Rótulos de la capa de texto: 'kx', 'Masa', 'Resorte k', 'vx' (νẋ), 'Amortiguador ν'.",
  "basis": "capa de texto"
}
```

**Analogía eléctrica (Fig. 3.4, circuito serie L-C-R):**

$$V=iR+\frac qC+L\frac{di}{dt},\ i=\frac{dq}{dt}\ \Rightarrow\ L\frac{d^2q}{dt^2}+R\frac{dq}{dt}+\frac1Cq=V\ (3.2.21)\ \Rightarrow\ \frac{d^2q}{dt^2}+\frac RL\frac{dq}{dt}+\frac1{LC}q=\frac1LV\ (3.2.22)$$

Comparando con (3.2.13): q ↔ x, V ↔ F, y L, R, 1/C ↔ m, λ (amortiguación), k. El circuito tiene la misma G(s) con

$$\omega_n=\frac1{\sqrt{LC}}\ (3.2.23),\qquad\zeta=\frac R2\sqrt{\frac CL}\ (3.2.24)$$

```json
{
  "type": "diagram",
  "id": "diagram-017",
  "page": 53,
  "pdf_page": 71,
  "title": "Figura 3.4: Circuito serie RLC",
  "elements": ["fuente V", "resistencia R", "inductancia L", "capacitancia C", "corriente i"],
  "relationships": ["V, R, L y C en serie, con corriente i"],
  "description": "Circuito eléctrico análogo del sensor masa-resorte-amortiguador."
}
```

### 3.3 Identificación de la dinámica de un elemento

Para identificar G(s) se usan señales de excitación normalizadas; las dos más comunes son el **escalón** y la **onda seno**.

#### 3.3.1 Respuesta a un escalón de elementos de primer y segundo orden

Escalón unitario: $\mathcal L\{u(t)\}=1/s$ (3.3.1). Para $G(s)=K/(1+\tau s)$:

$$\bar f_o(s)=G(s)\bar f_i(s)=\frac{K}{s(1+\tau s)}\ (3.3.2)=K\left[\frac1s-\frac1{s+1/\tau}\right]\ (3.3.3)\ \Rightarrow\ f_o(t)=K\left[1-e^{-t/\tau}\right]\ (3.3.4)$$

(fracciones parciales: A = −τ, B = 1). La forma de la respuesta para K = 1 se muestra en la Fig. 3.5.

```json
{
  "type": "chart",
  "id": "chart-015",
  "page": 55,
  "pdf_page": 73,
  "title": "Figura 3.5: Respuesta a un escalón de un sistema de primer orden (K = 1)",
  "chart_type": "line",
  "axes": {"x": {"label": "t", "ticks": [0, 2.5, 5, 7.5]}, "y": {"label": "f_o(t)"}},
  "series": [
    {"name": "τ = 2", "color": "rojo", "values": null, "formula": "1 - exp(-t/2)"},
    {"name": "τ = 1", "color": "negro", "values": null, "formula": "1 - exp(-t/1)"},
    {"name": "τ = 0.5", "color": "azul", "values": null, "formula": "1 - exp(-t/0.5)"}
  ],
  "description": "Tres curvas exponenciales que crecen hacia 1; a menor τ, más rápida la respuesta. Los valores puntuales no se leyeron; las fórmulas son las de la ecuación (3.3.4).",
  "basis": "pie de figura + capa de texto"
}
```

> **Ejemplo 2 (del documento).** Sensor de temperatura, estado inicial 25 °C, final 100 °C (escalón ΔT_F de 75 °C): $T(t)=25+75(1-e^{-t/\tau})$ (3.3.5). En t = τ: T = 25 + 75 × 0.63 = **72.3 °C**; midiendo el tiempo que tarda T en llegar a 72.3 °C se obtiene τ (Fig. 3.6).

```json
{
  "type": "chart",
  "id": "chart-016",
  "page": 56,
  "pdf_page": 74,
  "title": "Figura 3.6: Determinación de τ para un sistema de primer orden",
  "chart_type": "line",
  "axes": {"x": {"label": "t", "range": [0, 5], "ticks": [0, 1.25, 2.5, 3.75, 5]}, "y": {"label": "T (°C)", "range": [0, 100], "ticks": [0, 25, 50, 75, 100]}},
  "series": [{"name": "T(t) = 25 + 75(1 - e^(-t/τ))", "values": null, "known_points": [{"relation": "t = τ", "T_C": 72.3}]}],
  "description": "Curva de subida de la temperatura del sensor; la lectura de τ se hace en T = 72.3 °C. El eje y marca 0, 25, 50, 75 y 100 pero la curva parte de 25 °C según el ejemplo; valores intermedios no leídos.",
  "basis": "capa de texto + texto del documento"
}
```

**Segundo orden.** Para $G(s)=\omega_n^2/(s^2+2\zeta\omega_ns+\omega_n^2)$ con escalón unitario:

$$\bar f_o(s)=\frac1s\,\frac{\omega_n^2}{s^2+2\zeta\omega_ns+\omega_n^2}\ (3.3.6)=\frac1s-\frac{s+2\zeta\omega_n}{s^2+2\zeta\omega_ns+\omega_n^2}\ (3.3.7)$$

(coeficientes de fracciones parciales A = −1/ωₙ², B = −2ζ/ωₙ, C = 1). Tres casos:

| Caso | Condición | Respuesta al escalón unitario |
|---|---|---|
| 1. Amortiguación crítica | ζ = 1 | $f_o(t)=1-e^{-\omega_nt}(1+\omega_nt)$ (3.3.9) |
| 2. Subamortiguado | ζ < 1 | $f_o(t)=1-e^{-\zeta\omega_nt}\left[\cos\omega_n\sqrt{1-\zeta^2}\,t+\dfrac{\zeta}{\sqrt{1-\zeta^2}}\sin\omega_n\sqrt{1-\zeta^2}\,t\right]$ (3.3.10) |
| 3. Sobreamortiguado | ζ > 1 | $f_o(t)=1-e^{-\zeta\omega_nt}\left[\cosh\omega_n\sqrt{\zeta^2-1}\,t+\dfrac{\zeta}{\sqrt{\zeta^2-1}}\sinh\omega_n\sqrt{\zeta^2-1}\,t\right]$ (3.3.11) |

```json
{
  "type": "chart",
  "id": "chart-017",
  "page": 57,
  "pdf_page": 75,
  "title": "Figura 3.7: Respuesta a un escalón de un sistema de segundo orden",
  "chart_type": "line",
  "axes": {"x": {"label": "t", "range": [0, 15], "ticks": [0, 2.5, 5, 7.5, 10, 12.5, 15]}, "y": {"label": "f_o(t)", "range": [0, 1.5], "ticks": [0, 0.25, 0.5, 0.75, 1, 1.25, 1.5]}},
  "series": [
    {"name": "ζ < 1", "color": "rojo", "values": null, "visual_summary": "oscila con sobreimpulso (valores >1) y se estabiliza en 1"},
    {"name": "ζ = 1", "color": "negro", "values": null, "visual_summary": "sube sin sobreimpulso, amortiguación crítica"},
    {"name": "ζ > 1", "color": "azul", "values": null, "visual_summary": "sube más lentamente sin sobreimpulso"}
  ],
  "description": "Respuestas normalizadas de los tres casos de la Tabla anterior. Los parámetros ωn y los valores de ζ usados no se indican.",
  "basis": "pie de figura + capa de texto"
}
```

> **Ejemplo 3 (del documento).** Sensor de fuerza con k = 10³ N/m, m = 0.1 kg, ν = 10 N·s/m. Sensibilidad S = 1/k = 10⁻³ m/N; ωₙ = √(k/m) = 10² rad/s; ζ = 0.5. En reposo F(0⁻) = 10 N → x = 10 mm. Si F pasa de 10 a 12 N en t = 0 (ΔF = 2 N), con Δx(t) = S·ΔF·u(t)·f_o(t) (3.3.12):
>
> $$\Delta x(t)=2\left[1-e^{-50t}\left(\cos86.6\,t+0.58\sin86.6\,t\right)\right]\ \text{mm}\qquad(3.3.13)$$
>
> Cuando t es grande Δx → 2 mm, es decir x se estabiliza en 12 mm.

#### 3.3.2 Respuesta sinusoidal de elementos de primer y segundo orden

Transformada de una onda seno: $\bar f(s)=\omega/(s^2+\omega^2)$. Para entrada de amplitud û a un elemento de primer orden (3.3.14), con fracciones parciales y

$$\cos\varphi=\frac1{\sqrt{1+\tau^2\omega^2}},\quad\sin\varphi=\frac{-\omega\tau}{\sqrt{1+\tau^2\omega^2}}\qquad(3.3.15)$$

la respuesta es la suma de un transitorio y un término sinusoidal:

$$f_o(t)=\frac{\omega\tau\,\hat u}{1+\omega^2\tau^2}e^{-t/\tau}+\frac{\hat u}{\sqrt{1+\omega^2\tau^2}}\sin(\omega t+\varphi)\qquad(3.3.16)$$

> **Nota de transcripción.** La capa de texto del PDF muestra el coeficiente del término transitorio como «ωτ² û / (1+ω²τ²)» (con un «2» adicional sobre τ). La derivación estándar de fracciones parciales da ωτ·û/(1+ω²τ²), que es la forma escrita arriba; verificar con la página impresa 59 (PDF 77).

En un ensayo se espera a que el transitorio decaiga y se mide el estado estacionario:

$$f_o(t)=\frac{\hat u}{\sqrt{1+\tau^2\omega^2}}\sin(\omega t+\varphi)\qquad(3.3.17)$$

Con ωτ = 1 (ω = 1/τ): razón de amplitud 1/√2 y fase φ = −45°, lo que permite hallar τ por frecuencia (Fig. 3.8).

```json
{
  "type": "chart",
  "id": "chart-018",
  "page": 59,
  "pdf_page": 77,
  "title": "Figura 3.8: Respuesta ante una excitación senoidal de un sistema de primer orden",
  "chart_type": "line",
  "axes": {"x": {"label": "x", "range": [0, 25], "ticks": [0, 5, 10, 15, 20, 25]}, "y": {"label": "y", "range": [-0.1, 0.2], "ticks": [-0.1, -0.05, 0, 0.05, 0.1, 0.15, 0.2]}},
  "series": [{"name": "respuesta senoidal con transitorio inicial", "values": null}],
  "description": "Salida sinusoidal de estado estacionario con transitorio inicial decayendo (ecuación 3.3.16). Valores no leídos.",
  "basis": "pie de figura + capa de texto"
}
```

**Caso general** (sensibilidad estática K o ∂θ/∂u, función de transferencia G(s), entrada u = û sen ωt): en estado estacionario (1) θ es una onda seno; (2) de frecuencia ω; (3) con amplitud $\hat\theta=K|G(j\omega)|\hat u$; (4) con diferencia de fase $\varphi=\arg G(j\omega)$ entre θ y u.

Para segundo orden, con $G(j\omega)=\omega_n^2/[(j\omega)^2+2\zeta\omega_n(j\omega)+\omega_n^2]$:

$$|G(j\omega)|=\frac{1}{\sqrt{\left[1-\omega^2/\omega_n^2\right]^2+4\zeta^2\,\omega^2/\omega_n^2}},\qquad\varphi=-\tan^{-1}\!\left[\frac{2\zeta\,\omega/\omega_n}{1-\omega^2/\omega_n^2}\right]\qquad(3.3.18)$$

```json
{
  "type": "chart",
  "id": "chart-019",
  "page": 60,
  "pdf_page": 78,
  "title": "Figura 3.9: Respuesta en frecuencia de la magnitud de un elemento de segundo orden",
  "chart_type": "line (ejes logarítmicos)",
  "axes": {
    "x": {"label": "ω (normalizada)", "scale": "log", "ticks": [0.1353, 0.2231, 0.3679, 0.6065, 1, 1.649, 2.718]},
    "y": {"label": "|G(jω)|", "scale": "log", "ticks": [0.1353, 0.2231, 0.3679, 0.6065, 1, 1.649, 2.718, 4.482]}
  },
  "series": [
    {"name": "ζ = 0.1", "color": "rojo", "values": null},
    {"name": "ζ = 0.3", "color": "azul", "values": null},
    {"name": "ζ = 0.7", "color": "negro", "values": null},
    {"name": "ζ = 1.0", "color": "verde", "values": null},
    {"name": "ζ = 2", "color": "púrpura", "values": null}
  ],
  "description": "Familia de curvas de magnitud; las marcas de los ejes son potencias de e (e^-2 a e^1.5), lo que sugiere escalas logarítmicas naturales. La razón de amplitud y la fase dependen críticamente de ζ.",
  "basis": "pie de figura + capa de texto"
}
```

Para ζ < 0.7, |G(jω)| supera la unidad en un máximo:

$$|G(j\omega)|_{MAX}=\frac1{2\zeta\sqrt{1-\zeta^2}},\qquad\omega_R=\omega_n\sqrt{1-2\zeta^2}\ \ (\zeta<1/\sqrt2)$$

(frecuencia de resonancia ω_R). Midiendo |G|_MAX se pueden hallar ω_R, ζ y ωₙ. Alternativa: graficar decibeles $N=20\log_{10}|G(j\omega)|$ (3.3.19): |G| = 1 → 0 dB; 10 → +20 dB; 0.1 → −20 dB.

### 3.4 Errores dinámicos en sistemas de medida

Sistema de n elementos (Fig. 3.10), cada uno con sensibilidad estática K_i y función G_i(s). Suponiendo sensibilidad estática global igual a 1 (sin error estacionario):

$$G(s)=\frac{\Delta\bar\theta(s)}{\Delta\bar u(s)}=G_1(s)G_2(s)\cdots G_n(s)\qquad(3.4.1)$$

$$\Delta\bar\theta(s)=G(s)\Delta\bar u(s)\ (3.4.2),\qquad\Delta\theta(t)=\mathcal L^{-1}[G(s)\Delta\bar u(s)]\ (3.4.3)$$

El **error dinámico** es la diferencia entre la señal medida y la verdadera:

$$\varepsilon(t)=\Delta\theta(t)-\Delta u(t)\ (3.4.4)=\mathcal L^{-1}[G(s)\Delta\bar u(s)]-\Delta u(t)\ (3.4.5)$$

```json
{
  "type": "diagram",
  "id": "diagram-018",
  "page": 61,
  "pdf_page": 79,
  "title": "Figura 3.10: Sistema de medida con dinámica",
  "elements": ["Entrada: señal real Δu", "elemento 1 (K1, G1)", "elemento 2 (K2, G2)", "...", "elemento i (Ki, Gi)", "...", "Salida: señal medida Δθ"],
  "relationships": ["Δu -> Δθ1 -> Δθ2 -> ... -> Δθ (cascada)"],
  "description": "Cadena de n elementos en serie con dinámica lineal."
}
```

> **Ejemplo (Fig. 3.11).** Sistema de medida de temperatura: termocupla con τ = 10 s, amplificador con τ = 10⁻⁴ s y un elemento final de segundo orden con ωₙ = 200 rad/s y ζ = 1.0; sensibilidad estática global = 1.
>
> $$G(s)=\frac{40\times10^{-6}}{1+10s}\cdot\frac{10^3}{1+10^{-4}s}\cdot\frac{25}{2.5\times10^{-5}s^2+10^{-2}s+1}$$
>
> *Escalón de +20 °C:* $\Delta\bar T_M(s)=20\cdot\dfrac1s\cdot\dfrac1{1+10s}\cdot\dfrac1{1+10^{-4}s}\cdot\dfrac1{(1+s/200)^2}$ (3.4.6) → fracciones parciales con constantes A, B, C, D, E (el documento **no da sus valores numéricos**):
>
> $$\Delta T_M(t)=20\left[u(t)-Ae^{-0.1t}+Be^{-10^4t}-Ee^{-200t}(1+200t)\right],\qquad\varepsilon(t)=-20\left[Ae^{-0.1t}+Be^{-10^4t}+Ee^{-200t}(1+200t)\right]\ (3.4.7)$$
>
> El signo negativo indica una lectura muy baja. El término de B decae a cero tras 5×10⁻⁴ s; el de E tras unos 25 ms; el de A (τ = 10 s de la termocupla) tarda cerca de 50 s y es el que más pesa en el error dinámico.

> **Observación de fidelidad.** En (3.4.7) el signo del término en B es «+B» en ΔT_M(t) y «+B» dentro del corchete de ε(t) (con factor global −20), lo cual no es coherente entre ambas expresiones tal como se imprimen. También, el texto llama «contador» (y la figura «Registrador») al elemento de segundo orden. Se conserva lo impreso.

```json
{
  "type": "diagram",
  "id": "diagram-019",
  "page": 62,
  "pdf_page": 80,
  "title": "Figura 3.11: Sistema de medida de temperatura con dinámica",
  "elements": [
    {"name": "Termocupla", "transfer_function": "40e-6 / (1 + 10 s)", "output": "f.e.m."},
    {"name": "Amplificador", "transfer_function": "1e3 / (1 + 1e-4 s)", "output": "voltios"},
    {"name": "Registrador", "transfer_function": "25 / (2.5e-5 s^2 + 1e-2 s + 1)", "output": "temperatura medida"}
  ],
  "relationships": ["Temperatura real -> termocupla -> amplificador -> registrador -> temperatura medida"],
  "description": "Tres elementos en cascada, ganancia estática total = 40e-6 × 1e3 × 25 = 1."
}
```

**Entrada sinusoidal.** Con Δu = û sen ωt: $\Delta\theta(t)=|G(j\omega)|\hat u\sin(\omega t+\varphi)$ y

$$\varepsilon(t)=\hat u\left[|G(j\omega)|\sin(\omega t+\varphi)-\sin\omega t\right]\qquad(3.4.8)$$

```json
{
  "type": "diagram",
  "id": "diagram-020",
  "page": 63,
  "pdf_page": 81,
  "title": "Figura 3.12: Respuesta de un sistema con dinámica lineal",
  "elements": ["entrada sinusoidal (frecuencia ω)", "sistema lineal G", "salida sinusoidal (frecuencia ω, amplitud θ̂, fase φ)"],
  "relationships": ["Entrada -> sistema -> salida de igual frecuencia con amplitud y fase modificadas"],
  "description": "Esquema de entrada y salida senoidales en un sistema lineal."
}
```

Ejemplo numérico: temperatura sinusoidal de amplitud 20 °C y periodo 6 s (ω = 2π/6 ≈ 1.0 rad/s):

$$G(j\omega)=\frac{1}{(1+10j\omega)(1+10^{-4}j\omega)(1+10^{-2}j\omega+2.5\times10^{-5}(j\omega)^2)}\ (3.4.9)$$

$$|G(j1)|=\frac1{\sqrt{(1+100)(1+10^{-8})[(1-2.5\times10^{-5})^2+10^{-4}]}}\approx0.10\ (3.4.10),\qquad\arg G(j1)\approx-\tan^{-1}(10)-\tan^{-1}(10^{-4})-\tan^{-1}(10^{-2})\approx-85^\circ$$

Los valores en ω = 1 los fija principalmente la constante de 10 s; los otros elementos afectan solo a altas frecuencias. Con T_T(t) = 20 sen t: T_M(t) = 0.1 × 20 sen(t − 85°) y ε(t) = 20[0.1 sen(t − 85°) − sen t]. La forma de onda senoidal se conserva (invariante) aunque cambien amplitud y fase.

**Señales periódicas (análisis de Fourier).** Una señal de periodo T se descompone en armónicos de ω₁ = 2π/T:

$$f(t)=a_0+\sum_{n=1}^{\infty}a_n\cos n\omega_1t+\sum_{n=1}^{\infty}b_n\sin n\omega_1t\qquad(3.4.11)$$

$$a_n=\frac2T\int_{-T/2}^{T/2}f\cos n\omega_1t\,dt,\quad b_n=\frac2T\int_{-T/2}^{T/2}f\sin n\omega_1t\,dt,\quad a_0=\frac1T\int_{-T/2}^{T/2}f\,dt\qquad(3.4.12)$$

Para ∆u(t) (valor d.c. nulo → a₀ = 0) e impar (aₙ = 0): $\Delta u(t)=\sum\hat u_n\sin n\omega_1t$ (3.4.13), con ûₙ = bₙ. Por **superposición** (propiedad de sistemas lineales):

$$\Delta\theta(t)=\sum_{n=1}^{\infty}\hat u_n|G(jn\omega_1)|\sin(n\omega_1t+\varphi_n)\ (3.4.14),\qquad\varepsilon(t)=\sum_{n=1}^{\infty}\hat u_n\left[|G(jn\omega_1)|\sin(n\omega_1t+\varphi_n)-\sin n\omega_1t\right]\ (3.4.15)$$

con φₙ = arg G(jnω₁).

> **Ejemplo 4 (del documento).** Onda cuadrada de amplitud 20 °C y T = 6 s (ω₁ ≈ 1 rad/s):
>
> $$\Delta T_T(t)=\frac{80}{\pi}\left[\sin t+\tfrac13\sin3t+\tfrac15\sin5t+\tfrac17\sin7t+\cdots\right]\ (3.4.16)$$
>
> Se trunca en n = 7. Evaluando |G| y arg G en ω = 1, 3, 5, 7 rad/s (la frecuencia más alta sigue por debajo de ωₙ = 200 rad/s):
>
> $$\Delta T_M(t)=\frac{80}{\pi}\left[0.100\sin(t-85^\circ)+0.011\sin(3t-90^\circ)+0.004\sin(5t-92^\circ)+0.002\sin(7t-93^\circ)\right]\ (3.4.17\text{–}3.4.18)$$
>
> Los armónicos 3.º, 5.º y 7.º quedan muy reducidos respecto a la fundamental; la onda registrada difiere de la de entrada en forma, amplitud y fase. El método se extiende a señales aleatorias, representadas por espectros continuos de frecuencia.

```json
{
  "type": "chart",
  "id": "chart-020",
  "page": 66,
  "pdf_page": 84,
  "title": "Figura 3.13: Cálculo de errores dinámicos con una señal de entrada periódica",
  "chart_type": "multi-panel (espectros de amplitud/fase, respuesta en frecuencia, formas de onda)",
  "panels": [
    {"panel": "Forma de onda de la temperatura de entrada", "labels": ["+20", "0", "3", "6", "-20", "Δ"], "description": "onda cuadrada de ±20 °C, periodo 6 s"},
    {"panel": "Espectro de frecuencia de la temperatura de entrada", "labels": ["80/π", "25.5", "ω = 1, 3, 5, 7"], "description": "líneas de amplitud decreciente en los armónicos impares; amplitud fundamental 80/π ≈ 25.5"},
    {"panel": "Características de la respuesta de la frecuencia en los sistemas de medida", "labels": ["0.1", "0.01", "-80º", "-90º", "-100º", "ω = 1, 3, 5, 7"], "description": "relación de amplitud (≈0.1 en ω=1, decreciendo) y diferencia de fase (≈-85° a ≈-93°)"},
    {"panel": "Forma de onda de la temperatura de salida (registrada)", "labels": ["+2", "0", "-2", "2.6", "3", "6"], "description": "onda registrada de amplitud ≈2.6 °C"},
    {"panel": "Espectro de frecuencia de la temperatura de salida", "labels": ["2.6", "-80º", "-90º", "-100º"], "description": "líneas de amplitud y fase de los armónicos de salida"}
  ],
  "axes": {"x": {"label": "t (s) en formas de onda / ω (rad/s) en espectros"}, "y": {"label": "Δ temperatura (°C) / amplitud / fase"}},
  "series": [],
  "description": "Panel compuesto que resume el Ejemplo 4. Los rótulos numéricos provienen de la capa de texto; 2.6 ≈ 0.1 × 25.5 es coherente con el texto.",
  "basis": "capa de texto (no verificado visualmente)"
}
```

### 3.5 Técnicas de compensación dinámica

Para tener ε(t) = 0 con una señal periódica se requiere (m = orden del armónico significativo más alto):

$$|G(j\omega_1)|=|G(j2\omega_1)|=\cdots=|G(jm\omega_1)|=1,\quad\arg G(j\omega_1)=\cdots=\arg G(jm\omega_1)=0\qquad(3.5.1)$$

Para una señal aleatoria con espectro continuo entre 0 y ω_MAX: $|G(j\omega)|=1$ y $\arg G(j\omega)=0$ para $0<\omega\le\omega_{MAX}$ (3.5.2). Es un ideal difícil de lograr; un criterio práctico limita la variación de |G|:

$$0.98<|G(j\omega)|<1.02\quad\text{para}\ 0<\omega\le\omega_{MAX}\qquad(3.5.3)$$

lo que limita el error dinámico a ≈ ±2 %. *(El texto dice «para una señal que contenga frecuencias mayores a ω_MAX/2π Hz»; por el contexto parecería «menores», pero se conserva lo impreso.)*

**Ancho de banda:** rango de frecuencias donde |G(jω)| > 1/√2 (reducción de 30 % en ω_B; equivale a −3.0 dB, N = 20 log(1/√2)). No se usa mucho como criterio para sistemas completos, pero sí para amplificadores. Un elemento de primer orden tiene ancho de banda de 0 a 1/τ rad/s.

**Estrategia:** si G(s) no cumple (3.5.3), primero se identifican los elementos dominantes (en el ejemplo, la constante de 10 s de la termocupla). Luego:

| Método | Descripción (según el documento) | Limitaciones / observaciones |
|---|---|---|
| **Diseño intrínseco** | Primer orden: minimizar τ = mC/UA reduciendo la razón masa/área (p. ej. termistor de lámina delgada). Segundo orden: maximizar ωₙ = √(k/m) con alta rigidez k y baja masa m. | Aumentar k reduce la sensibilidad estática K = 1/k. Valor óptimo de ζ ≈ **0.7** (tiempo de establecimiento mínimo al escalón y |G| ≈ 1, respuesta plana en la banda pasante; ref. [20]). |
| **Compensación de lazo abierto** (Fig. 3.15) | Se agrega un elemento G_c(s) tal que G(s) = G_u(s)·G_c(s) cumpla la condición. Un circuito de adelanto-atraso con una termocupla reduce la constante de tiempo total a τ₂. | τ puede cambiar con el coeficiente de transferencia de calor U, reduciendo la efectividad. |
| **Lazo cerrado con realimentación negativa de alta ganancia** (Fig. 3.16) | Acelerómetro de lazo cerrado: la fuerza de inercia m·a se equilibra con la fuerza de la bobina en el campo del imán; el desbalance se detecta por el sensor elástico + sensor de desplazamiento potenciométrico; la tensión amplificada genera corriente que pasa por la bobina y por un resistor normalizado. | Ver análisis siguiente. |

```json
{
  "type": "chart",
  "id": "chart-021",
  "page": 68,
  "pdf_page": 86,
  "title": "Figura 3.14: Respuesta en frecuencia de la magnitud de un elemento de segundo orden",
  "chart_type": "line",
  "axes": {"x": {"label": "ω (frecuencia)"}, "y": {"label": "|G(jω)|"}},
  "series": [],
  "description": "Gráfica sin rótulos numéricos en la capa de texto; se cita junto con la respuesta al escalón para justificar ζ ≈ 0.7. No se pudo determinar su contenido.",
  "basis": "pie de figura"
}
```

```json
{
  "type": "diagram",
  "id": "diagram-021",
  "page": 69,
  "pdf_page": 87,
  "title": "Figura 3.15: Compensación dinámica en lazo abierto",
  "elements": [
    "Elemento no compensado: termocupla con función 1/(1+τ s)",
    "Elemento de compensación: circuito de adelanto y atraso con función (1+τ1 s)/(1+τ2 s)"
  ],
  "relationships": ["Termocupla -> circuito de adelanto-atraso en cascada"],
  "labels_in_text_layer": ["1 / (1+τ)", "1+τ1", "1+τ2", "1 / (1+τ2)"],
  "description": "Cadena de la termocupla y un compensador de adelanto-atraso. Las expresiones exactas de los bloques no pueden determinarse con certeza desde la capa de texto; el texto del documento dice que la constante total se reduce a τ₂.",
  "basis": "capa de texto + texto del documento"
}
```

**Función de transferencia del acelerómetro de lazo cerrado** (reconstruida del texto extraído; K_A, K_D, K_F: ganancias del amplificador, del sensor de desplazamiento y del elemento de realimentación; R: resistor normalizado; k, ωₙ, ζ: del elemento elástico):

$$\frac{\Delta\bar V(s)}{\Delta\bar a(s)}=\frac{mR}{K_F}\cdot\frac{1}{\dfrac{k}{K_AK_DK_F\omega_n^2}s^2+\dfrac{2\zeta}{\omega_n}\dfrac{k}{K_AK_DK_F}s+1+\dfrac{k}{K_AK_DK_F}}\qquad(3.5.4)$$

Si K_A es suficientemente grande para que K_AK_DK_F/k ≫ 1:

$$\frac{\Delta\bar V}{\Delta\bar a}=\frac{K_s\,\omega_{ns}^2}{s^2+2\zeta_s\omega_{ns}s+\omega_{ns}^2},\quad K_s=\frac{mR}{K_F},\quad\omega_{ns}=\omega_n\sqrt{\frac{K_AK_DK_F}{k}},\quad\zeta_s=\zeta\sqrt{\frac{k}{K_AK_DK_F}}$$

La frecuencia natural del sistema ωₙₛ es mucho mayor que la del elemento elástico; ζₛ es mucho menor que ζ, pero tomando ζ grande se puede lograr ζₛ ≈ 0.7. La sensibilidad estática depende solo de m, K_F y R, que pueden ser muy constantes.

> **Nota de transcripción.** La expresión (3.5.4) aparece desordenada en la capa de texto; la forma de arriba es una reconstrucción coherente con las fórmulas de K_s, ωₙₛ y ζₛ del propio documento. Verificar con la página impresa 69 (PDF 87).

```json
{
  "type": "diagram",
  "id": "diagram-022",
  "page": 70,
  "pdf_page": 88,
  "title": "Figura 3.16: Esquema y diagrama de bloques de un acelerómetro en lazo cerrado",
  "elements": ["Cápsula", "Imán", "Bobina", "Masa sísmica", "Sensor de fuerza elástica", "Sensor de desplazamiento potenciométrico", "Amplificador", "Bobina e imán (fuerza electromagnética)", "Resistor normalizado", "Fuerza de inercia", "Fuerza no balanceada", "amortiguador ν"],
  "relationships": [
    "Aceleración -> fuerza de inercia sobre la masa sísmica",
    "Fuerza no balanceada -> sensor de fuerza elástica -> sensor de desplazamiento -> amplificador -> corriente",
    "Corriente -> bobina e imán -> fuerza electromagnética que se opone a la fuerza de inercia",
    "Corriente -> resistor normalizado -> tensión de salida"
  ],
  "description": "Esquema mecánico (izquierda) y diagrama de bloques (derecha) de un acelerómetro con servorealimentación de fuerza."
}
```

### 3.6 Determinación experimental de los parámetros de un sistema de medida

El análisis teórico revela relaciones básicas, pero rara vez da valores numéricos precisos de sensibilidad, constante de tiempo, frecuencia natural, etc. (ref. [11]).

**Orden cero:** respuesta instantánea; solo se necesita la sensibilidad estática K (calibración estática).

**Primer orden:** K por calibración estática; el único parámetro dinámico es τ. Métodos:

1. **Escalón, 63.2 %:** τ = tiempo para alcanzar el 63.2 % del valor final. Sensible a imprecisiones en la determinación de t = 0 y no comprueba que el instrumento sea realmente de primer orden.
2. **Escalón en escala semilogarítmica (método mejorado).** De (3.3.4): $\theta/K=1-e^{-t/\tau}$ (3.6.1) → $1-\theta/K=e^{-t/\tau}$ (3.6.2). Con $\xi\triangleq\ln(1-\theta/K)=-t/\tau$ (3.6.3) y $d\xi/dt=-1/\tau$ (3.6.4), el gráfico ξ vs t es una recta de pendiente −1/τ. Usa la mejor línea a través de todos los puntos y, si los puntos caen cerca de la recta, confirma el comportamiento de primer orden; desviaciones grandes indican que no lo es y que el valor del método del 63.2 % sería engañoso.
3. **Respuesta en frecuencia** (verificación más fuerte, pero más costosa si el sistema no es eléctrico, pues los generadores sinusoidales no eléctricos no son comunes ni baratos). Razón de amplitud y fase en escalas logarítmicas: asíntotas típicas de pendiente 0 y −20 dB/década y fase tendiendo a −90°; τ = 1/ω_b en el punto de quiebre (Fig. 3.19). Desviaciones indican otro comportamiento.

```json
{
  "type": "chart",
  "id": "chart-022",
  "page": 71,
  "pdf_page": 89,
  "title": "Figura 3.17: Respuesta normalizada a un escalón",
  "chart_type": "line",
  "axes": {"x": {"label": "t", "range": [0, 10], "ticks": [0, 2.5, 5, 7.5, 10]}, "y": {"label": "θ/K", "range": [0, 1], "ticks": [0, 0.25, 0.5, 0.75, 1]}},
  "series": [{"name": "θ/K = 1 - e^(-t/τ)", "values": null}],
  "description": "Curva exponencial creciente normalizada (ecuación 3.6.1). τ no indicado.",
  "basis": "pie de figura + capa de texto"
}
```

```json
{
  "type": "chart",
  "id": "chart-023",
  "page": 72,
  "pdf_page": 90,
  "title": "Figura 3.18: Prueba de la función escalón para un sistema de primer orden",
  "chart_type": "line (semilogarítmico linealizado)",
  "axes": {"x": {"label": "t", "range": [0, 10], "ticks": [0, 2.5, 5, 7.5, 10]}, "y": {"label": "ξ = ln(1 - θ/K)", "range": [-10, 0], "ticks": [0, -2.5, -5, -7.5, -10]}},
  "series": [{"name": "ξ(t)", "values": null, "visual_summary": "recta de pendiente negativa -1/τ"}],
  "description": "Procedimiento ilustrado en 3.6 (ecuación 3.6.3). Valores de los puntos de datos no leídos.",
  "basis": "capa de texto"
}
```

```json
{
  "type": "chart",
  "id": "chart-024",
  "page": 73,
  "pdf_page": 91,
  "title": "Figura 3.19: Prueba de respuesta frecuencial de un sistema de primer orden",
  "chart_type": "Bode (magnitud y fase)",
  "axes": {"x": {"label": "log ω", "marked": "ω_b = 1/τ"}, "y": {"label": "magnitud (dB) y fase φ", "marked": ["0", "-20 dB/década", "0º", "-45º", "-90º"]}},
  "series": [{"name": "magnitud", "visual_summary": "asíntota plana en 0 dB y asíntota de -20 dB/década tras ω_b"}, {"name": "fase", "visual_summary": "de 0° a -90°, con -45° en ω_b"}],
  "description": "Diagrama de Bode de un sistema de primer orden con el punto de quiebre ω_b = 1/τ.",
  "basis": "capa de texto"
}
```

**Segundo orden:** K por calibración estática; ζ y ωₙ por escalón o respuesta en frecuencia.

- **Subamortiguado** (Fig. 3.20a): 

$$\zeta=\frac{1}{\sqrt{\left[\pi/\ln(a/A)\right]^2+1}}\ (3.6.5),\qquad\omega_n=\frac{2\pi}{T\sqrt{1-\zeta^2}}\ (3.6.6)$$

  (*a*, *A* y *T* se definen en la Fig. 3.20a; el texto no los describe explícitamente.)
- **Ligeramente amortiguado** (respuesta a transitorio rápido, Fig. 3.20b): $\zeta\approx\ln(x_1/x_n)/(2\pi n)$ (3.6.7), que supone √(1−ζ²) ≈ 1 (muy precisa para ζ < 0.1); ωₙ de (3.6.6). Si hay muchos ciclos, conviene promediar el periodo T. En un sistema estrictamente lineal de segundo orden, el valor de ζ debe ser el mismo para cualquier n; si ζ calculado con n = 1, 2, 4 y 6 da valores distintos, el sistema no sigue el modelo.
- **Sobreamortiguado** (ζ > 1, sin oscilaciones): es más fácil usar dos constantes de tiempo:

$$f_0(t)=1-\frac{\tau_2}{\tau_2-\tau_1}e^{-t/\tau_2}+\frac{\tau_1}{\tau_2-\tau_1}e^{-t/\tau_1}\ (3.6.8),\quad\tau_1\triangleq\frac1{(\zeta-\sqrt{\zeta^2-1})\omega_n}\ (3.6.9),\quad\tau_2\triangleq\frac1{(\zeta+\sqrt{\zeta^2-1})\omega_n}\ (3.6.10)$$

  **Procedimiento gráfico (ref. [2]):** (1) definir el porcentaje de respuesta incompleta $R_{pi}=(1-\theta/K)\times100$; (2) graficar R_pi en escala logarítmica contra t lineal; para t grande se aproxima a una recta; prolongarla hasta t = 0 y anotar P₁ (intercepto); τ₁ es el tiempo en que la asíntota vale 0.368·P₁; (3) en la misma gráfica, dibujar la diferencia entre la asíntota y R_pi; si no es una recta, el sistema no es de segundo orden; si lo es, el tiempo en que vale 0.368(P₁ − 100) es τ₂ (Fig. 3.21). Con τ₁ y τ₂ se obtienen ζ y ωₙ de (3.6.9)-(3.6.10).
- **Respuesta en frecuencia** (solo curva de amplitud, Fig. 3.22): $A_p/A_0=1/(2\zeta\sqrt{1-\zeta^2})$ (3.6.11), con A_p el valor máximo de la magnitud (sistema subamortiguado) y A₀ el valor a frecuencia cero (o la mínima, en escala logarítmica). Las curvas de fase sirven de verificación del modelo.

```json
{
  "type": "chart",
  "id": "chart-025",
  "page": 74,
  "pdf_page": 92,
  "title": "Figura 3.20: Pruebas de escalón e impulso para sistemas de segundo orden",
  "chart_type": "dos paneles (a: respuesta al escalón subamortiguada; b: respuesta a impulso ligeramente amortiguada)",
  "panels": [
    {"panel": "a", "labels": ["θ", "Tiempo", "a", "A", "T"], "description": "respuesta al escalón con sobreimpulso; los parámetros a, A y T se usan en (3.6.5)-(3.6.6)"},
    {"panel": "b", "labels": ["θ", "Tiempo", "ciclos", "x1 ... xn", "0", "1"], "description": "oscilación decreciente con amplitudes x1...xn usadas en (3.6.7)"}
  ],
  "axes": {"x": {"label": "Tiempo", "ticks": [0, 0.2, 0.4, 0.6, 0.8, 1.0]}, "y": {"label": "θ", "ticks": [0, 10, 20, 30, 40, 50, 60, 70, 80, 90, 100]}},
  "series": [],
  "description": "Las marcas numéricas de los ejes están en la capa de texto; los valores de las curvas no pudieron leerse.",
  "basis": "capa de texto (no verificado visualmente)"
}
```

```json
{
  "type": "chart",
  "id": "chart-026",
  "page": 75,
  "pdf_page": 93,
  "title": "Figura 3.21: Prueba de la función escalón para sistemas de segundo orden",
  "chart_type": "line (ordenada logarítmica)",
  "axes": {"x": {"label": "t", "range": [0, 7], "ticks": [0, 1, 2, 3, 4, 5, 6, 7]}, "y": {"label": "R_pi (%)", "scale": "log", "ticks": [5, 10, 20, 40, 50, 60, 70, 80, 100, 150]}},
  "series": [{"name": "R_pi", "values": null}, {"name": "asíntota y diferencia"}],
  "annotations": ["P1", "0.368", "0.368[P1 - 100]", "τ2", "τ1"],
  "description": "Ilustra el procedimiento gráfico para hallar τ1 y τ2.",
  "basis": "capa de texto (no verificado visualmente)"
}
```

```json
{
  "type": "chart",
  "id": "chart-027",
  "page": 76,
  "pdf_page": 94,
  "title": "Figura 3.22: Prueba de respuesta en frecuencia de un sistema de segundo orden",
  "chart_type": "magnitud vs frecuencia",
  "axes": {"x": {"label": "frecuencia"}, "y": {"label": "magnitud"}},
  "series": [],
  "description": "La capa de texto no contiene rótulos; se cita para ilustrar la obtención de ζ con (3.6.11). Contenido no determinado.",
  "basis": "pie de figura"
}
```

**Sistemas de forma arbitraria:** se describe el comportamiento dinámico con la respuesta en frecuencia, obtenida con señales sinusoidales, de pulsos o aleatorias. La señal de salida θ₀ del sistema de medida suele servir directamente; la entrada u_i se mide con un sensor separado que actúa como **patrón de calibración y cuya precisión es unas 10 veces mejor que la del sistema a calibrar. La relación (θ₀/u_i)(iω) define el rango de frecuencias donde no se requieren correcciones y da los datos para correcciones dinámicas.

**Síntesis propia — resumen de métodos de identificación (basado en el documento):**

| Orden | Parámetros | Método de escalón | Método de frecuencia | Verificación del modelo |
|---|---|---|---|---|
| 0 | K | — (solo calibración estática) | — | — |
| 1 | K, τ | 63.2 %; **semilogarítmico** (recta ξ vs t) | ω_b = 1/τ en el quiebre; asíntotas 0 y −20 dB/década; fase → −90° | Linealidad del gráfico semilog; asíntotas y fase |
| 2, ζ < 1 | K, ζ, ωₙ | Sobreimpulso (3.6.5), periodo (3.6.6); decremento (3.6.7) | Pico A_p/A₀ (3.6.11) | ζ constante para cualquier n; curvas de fase |
| 2, ζ > 1 | K, τ₁, τ₂ | Gráfico semilog de R_pi (Fig. 3.21) | Curva de amplitud | Que la diferencia con la asíntota sea otra recta |

### 3.7 Efectos de la carga en sistemas de medida

Hasta ahora no se consideró la **carga**. Dos efectos: (1) **carga interna**: un elemento modifica las características de los anteriores (p. ej. drenando corriente) y a su vez es modificado por el siguiente; (2) **proceso de carga** (más fundamental): la introducción del sensor altera la variable medida (ejemplo: un sensor de temperatura en un recipiente con líquido puede hacer descender la temperatura, v. gr., 0.2 °C).

#### 3.7.1 Carga eléctrica

En los diagramas, la transferencia de información entre bloques se representa con una sola variable (p. ej. voltaje en el sistema de la Fig. 2.15), de modo que no se ven las corrientes. Para describir voltaje y corriente en una conexión, cada elemento se representa por un **circuito equivalente de dos terminales**.

#### 3.7.2 Circuito equivalente Thévenin

**Teorema de Thévenin:** una red de impedancias lineales y fuentes de tensión puede reemplazarse por una fuente V_Th en serie con una impedancia Z_Th; V_Th es la tensión de circuito abierto y Z_Th la impedancia vista hacia atrás con las fuentes reducidas a cero (reemplazadas por sus impedancias internas). Con carga Z_L:

$$i=\frac{V_{Th}}{Z_{Th}+Z_L}\ (3.7.1),\qquad V_L=iZ_L=\frac{1}{1+Z_{Th}/Z_L}V_{Th}\ (3.7.2)$$

- **Máxima transferencia de tensión:** Z_L ≫ Z_Th (V_L → V_Th).
- **Máxima transferencia de potencia:** Z_L = Z_Th.

```json
{
  "type": "diagram",
  "id": "diagram-023",
  "page": 77,
  "pdf_page": 95,
  "title": "Figura 3.23: Circuito equivalente de Thévenin",
  "elements": ["red lineal con carga Z_L", "fuente V_Th", "impedancia Z_Th en serie", "carga Z_L", "corriente i", "tensión V_L"],
  "relationships": ["V_Th en serie con Z_Th alimenta Z_L; equivalente a la red lineal cargada por Z_L"],
  "description": "Esquema doble: red lineal con carga (izquierda) y su equivalente de Thévenin (derecha)."
}
```

> **Ejemplo del sistema de la Fig. 2.15.** Termocupla: Z_Th = 20 Ω (resistiva), E_Th = 40·T μV (ignorando no linealidad y unión de referencia). Amplificador (Fig. 3.24): Z_I = R_I = 2×10⁶ Ω, A = 10³ (ganancia de voltaje a circuito abierto), Z_O = R_O = 75 Ω. Indicador: carga resistiva de 10⁴ Ω, con escala 25 °C/V (T_M = 25·V_L).
>
> $$V_I=\frac{2\times10^6}{2\times10^6+20}\,40\times10^{-6}T,\qquad V_L=1000\,V_I\,\frac{10^4}{75+10^4}\ (3.7.3)$$
>
> $$T_M=\left(\frac{2\times10^6}{2\times10^6+20}\right)\left(\frac{10^4}{10^4+75}\right)T=0.9925\,T\ (3.7.4)$$
>
> En cada interconexión aparece el factor Z_L/(Z_Th + Z_L). **Error por carga:** ε_L = −0.0075·T (error de estado estacionario).

```json
{
  "type": "diagram",
  "id": "diagram-024",
  "page": 78,
  "pdf_page": 96,
  "title": "Figura 3.24: Circuito equivalente de un amplificador",
  "elements": ["impedancia de entrada Z_i", "tensión de entrada v_i", "fuente dependiente A·v_i", "impedancia de salida Z_o", "corriente i"],
  "relationships": ["v_i en Z_i; fuente A·v_i en serie con Z_o hacia la salida"],
  "description": "Modelo de dos puertos de un amplificador de tensión."
}
```

```json
{
  "type": "diagram",
  "id": "diagram-025",
  "page": 79,
  "pdf_page": 97,
  "title": "Figura 3.25: Equivalente Thévenin para un sistema de medición de temperatura",
  "elements": ["Termocupla: fuente 40T μV con 20 Ω", "Amplificador: 2 MΩ de entrada, fuente 1000·v_i, 75 Ω de salida", "Indicador: 10 kΩ", "T_M = 25·V_L"],
  "relationships": ["Temperatura verdadera T -> termocupla -> amplificador -> indicador -> temperatura medida T_M"],
  "description": "Circuito equivalente completo del sistema de la Fig. 2.15 con los valores del ejemplo."
}
```

> **Ejemplo de error grande (electrodo de vidrio para pH).** E_Th = 59·pH mV, Z_Th = R_Th = 10⁹ Ω, conectado directamente a un indicador con R_L = 10⁴ Ω y sensibilidad 1/59 pH/mV: $pH_M=59\,pH\cdot\frac{10^4}{10^4+10^9}\cdot\frac1{59}\approx10^{-5}\,pH$ (3.7.5), es decir, un indicador prácticamente en cero. **Solución:** amplificador *buffer* (Z_IN grande, Z_OUT pequeña, A = 1); por ejemplo, un amplificador operacional con entrada FET como seguidor de tensión, Z_IN = 10¹² Ω, Z_OUT = 10 Ω: $pH_M=\frac{10^{12}}{10^{12}+10^9}\cdot\frac{10^4}{10^4+10}\,pH$, con error por carga de **−0.002 pH**.

> **Ejemplo de carga a.c. (Fig. 3.26).** Tacogenerador de reluctancia variable conectado a un registrador. V_Th es a.c. con amplitud V_p = 5.0×10⁻³·ω_r V y ω = 6·ω_r rad/s (ω_r: velocidad angular mecánica). Z_Th = R_Th + jωL_Th (L_Th = 1 H, R_Th = 1.5 kΩ). Con ω_r = 10³ rad/s: V_p = 5 V, ω = 6×10³ rad/s, Z_Th = 1.5 + j6.0 kΩ; con R_L = 10 kΩ:
>
> $$\hat V_L=V_p\frac{R_L}{|Z_{Th}+R_L|}=5\frac{10}{\sqrt{11.5^2+6.0^2}}=3.85\ \text{V}\ (3.7.6)$$
>
> Con sensibilidad del registrador de 1/(5×10⁻³) rad/s por voltio, la velocidad registrada es **770 rad/s** (en lugar de 1000). El error se elimina aumentando la impedancia del registrador o cambiando su sensibilidad; mejor aún, sustituyendo el registrador por un **contador que mida la frecuencia** en vez de la amplitud.

```json
{
  "type": "diagram",
  "id": "diagram-026",
  "page": 80,
  "pdf_page": 98,
  "title": "Figura 3.26: Carga a.c. de un tacogenerador",
  "elements": ["Tacogenerador de reluctancia variable: V_Th = V_p sen ωt, L_th = 1 H, R_th = 1.5 kΩ", "Registrador: R_L = 10 kΩ", "V_L"],
  "relationships": ["V_Th en serie con R_th y L_th alimenta R_L"],
  "description": "Circuito equivalente del tacogenerador con su carga resistiva."
}
```

#### 3.7.3 Ejemplo del cálculo de un circuito equivalente Thévenin (sensor potenciométrico)

Sensor potenciométrico de desplazamientos d; con x = d/d_T (desplazamiento fraccional) la resistencia correspondiente es R_p·x (R_p = resistencia total). Con fuente V_s:

$$E_{Th}=V_sx\ (3.7.7),\qquad\frac1{R_{Th}}=\frac1{R_px}+\frac1{R_p(1-x)}\ \Rightarrow\ R_{Th}=R_p\,x(1-x)\ (3.7.8)$$

Con carga resistiva R_L:

$$V_L=V_s\,x\,\frac{1}{(R_p/R_L)\,x(1-x)+1}\qquad(3.7.9)$$

La relación V_L–x es **no lineal** (depende de R_p/R_L). El error por carga:

$$N(x)=V_s\left\{\frac{x^2(1-x)(R_p/R_L)}{1+(R_p/R_L)x(1-x)}\right\}\qquad(3.7.10)$$

que para R_p/R_L ≪ 1 (situación normal) es N(x) ≈ V_s(R_p/R_L)(x² − x³). Su máximo es $\hat N=\frac{4}{27}V_s\frac{R_p}{R_L}$ en x = 2/3 (dN/dx = 0, d²N/dx² < 0); como porcentaje de la escala completa V_s:

$$\hat N=\frac{400}{27}\frac{R_p}{R_L}\%\approx15\frac{R_p}{R_L}\%\qquad(3.7.11)$$

Los requisitos de no linealidad y de máxima potencia permiten especificar R_p y V_s. *Ejemplo del documento:* un potenciómetro de rango 10 cm conectado a un registrador; si la no linealidad máxima no debe pasar de 2 %, se requiere 15·R_p/R_L ≤ 2, es decir R_p ≤ (20/15)×10³ Ω, de modo que un potenciómetro de 1 kΩ podría ser adecuado. La sensibilidad es dV_L/dx ≈ V_s.

> **Observaciones de fidelidad.** (1) La capa de texto dice que el registrador es de «10 Ω»; el resultado R_p ≤ (20/15)×10³ Ω corresponde a R_L = 10 kΩ, por lo que el valor probablemente es 10 kΩ (verificar en la página impresa 81 (PDF 99)). (2) La última frase de la sección está truncada en el original («la sensibilidad más grande que V_s…»).

#### 3.7.4 Circuito equivalente Norton

**Teorema de Norton:** la red se reemplaza por una fuente de corriente i_N (corriente de cortocircuito) en paralelo con Z_N (impedancia vista con fuentes de voltaje reducidas a cero). Con 1/Z = 1/Z_N + 1/Z_L:

$$V_L=i_NZ=i_N\frac{Z_NZ_L}{Z_N+Z_L}\qquad(3.7.12)$$

Si Z_L ≪ Z_N, V_L → i_N·Z_L: para la **máxima corriente** en la carga, la impedancia de carga debe ser mucho menor que la de Norton.

> **Ejemplo 1 — transmisor de presión diferencial.** Entrega 4–20 mA proporcional a la presión diferencial (rangos típicos de 0 a 2×10⁴ Pa) hacia un registrador a través de un cable:
>
> $$V_L=i_N\frac{R_N(R_C+R_R)}{R_N+R_C+R_R}\ (3.7.13),\qquad V_R=i_NR_R\frac{R_N}{R_N+R_C+R_R}\ (3.7.14)$$
>
> Con los datos de la figura, V_R = 0.9995·i_N·R_R, por lo que el voltaje del registrador se desvía del rango deseado (1 a 5 V) solo en **0.05 %**. *(Los valores de R_N, R_C y R_R están en una figura referida como «Fig.(zz)» que no tiene número ni contenido legible en el documento.)*

> **Ejemplo 2 — cristal piezoeléctrico como sensor de fuerza.** La fuerza F produce un pequeño desplazamiento x ∝ F; la carga es q = K·x, de modo que el cristal es una fuente de corriente de Norton $i_N=dq/dt=K\,dx/dt$ en paralelo con una capacitancia C_N. Conectado mediante un cable capacitivo C_C a un registrador de carga resistiva R_L: V_L = i_N·Z, con $\frac1Z=C_Ns+C_Cs+\frac1{R_L}$:
>
> $$\frac{\Delta\bar V_L(s)}{\Delta\bar i_N(s)}=\frac{R_L}{1+R_L(C_N+C_C)s}\qquad(3.7.15)$$
>
> El efecto de la carga eléctrica es introducir una función de transferencia en el sistema de medición de fuerza, afectando la exactitud dinámica. *(El texto remite a «sección 8.7» y a «figura 5.11», que no corresponden a la numeración de este libro.)*

#### 3.7.5 Carga generalizada

- El voltaje es una variable de **esfuerzo** (a través de) y la corriente una de **flujo** (de traspaso) ẋ; el esfuerzo conduce flujo a través de una **impedancia**. Otros pares esfuerzo-flujo: fuerza-velocidad, torque-velocidad angular, diferencia de presión-flujo de volumen, diferencia de temperatura-flujo de calor. El producto esfuerzo × flujo es potencia en vatios (excepto para temperatura: vatios × temperatura). (El texto se refiere a una «tabla 5.1» adaptada de [2] con las cantidades de impedancia, rigidez, flexibilidad e inertancia; **no está en esta parte del libro**.)
- **Analogías:** sistema mecánico: masa ↔ inductancia, constante de amortiguación ↔ resistencia, 1/rigidez ↔ capacitancia. Sistema térmico: resistencia térmica ↔ resistencia eléctrica; capacitancia térmica ↔ capacitancia eléctrica. Por tanto los equivalentes de Thévenin y Norton se generalizan a sistemas no eléctricos.

**Ejemplo mecánico (proceso masa-resorte-amortiguador medido por sensor elástico de fuerza + sensor potenciométrico).**

Estado estacionario (ẋ = 0, ẍ = 0): proceso F = k_p·x + F_s; sensor F_s = k_s·x (3.7.16):

$$F_s=\frac{k_s}{k_s+k_p}F=\frac1{1+k_p/k_s}F\qquad(3.7.17)$$

Para minimizar el error de carga estacionario: k_s ≫ k_p. En régimen no estacionario (3.7.18-3.7.19): 

proceso: $F-k_px-\lambda_p\dot x-F_s=m_p\ddot x$; sensor: $F_s-k_sx-\lambda_s\dot x=m_s\ddot x$ (el original imprime «rF_s» en lugar de F_s en la segunda ecuación).

Transformadas con condiciones iniciales de reposo (3.7.20) e **impedancias mecánicas** $Z_M(s)=\Delta\bar F/\Delta\dot x$:

$$Z_{MP}(s)=m_ps+\lambda_p+\frac{k_p}{s}\ (3.7.21),\qquad Z_{MS}(s)=m_ss+\lambda_s+\frac{k_s}{s}\ (3.7.22),\qquad\Delta\bar F_s(s)=\frac{Z_{MS}}{Z_{MS}+Z_{MP}}\Delta\bar F(s)\ (3.7.23)$$

Para minimizar la carga dinámica, Z_MS ≫ Z_MP. El sensor completo es una **red de cuatro terminales (dos puertos)**, similar al amplificador, solo que el puerto de entrada implica transferencia de energía mecánica.

**Ejemplo térmico** (cuerpo caliente a T_p medido con termocupla a T_s; M masa, C calor específico, U coeficiente de transferencia, A área):

$$M_pC_p\frac{dT_p}{dt}=W_p-W_s,\ W_p=U_pA_p(T_F-T_p);\qquad M_sC_s\frac{dT_s}{dt}=W_s,\ W_s=U_sA_s(T_p-T_s)\qquad(3.7.24)$$

M·C ↔ capacitancia eléctrica (calor/temperatura); U·A ↔ 1/resistencia. T_F→T_p depende de un divisor con 1/(U_pA_p) y M_pC_p; T_p→T_s de otro con 1/(U_sA_s) y M_sC_s. La termocupla es una red de dos puertos (entrada térmica, salida eléctrica). **Conclusión del documento:** representar los elementos por redes de dos puertos permite cuantificar la carga del proceso y entre elementos.

**Síntesis propia — analogías esfuerzo-flujo (según 3.7.5):**

| Dominio | Esfuerzo | Flujo | Analogía de L / R / C |
|---|---|---|---|
| Eléctrico | tensión | corriente | inductancia / resistencia / capacitancia |
| Mecánico (traslación) | fuerza | velocidad | masa / amortiguación / 1/rigidez |
| Mecánico (rotación) | torque | velocidad angular | no desarrollado en detalle en el texto |
| Fluídico | diferencia de presión | flujo de volumen | no desarrollado en detalle |
| Térmico | diferencia de temperatura | flujo de calor | — / resistencia térmica / capacitancia térmica |

#### 3.7.6 Efectos de la carga bajo condiciones dinámicas

Los resultados estáticos se transfieren al caso dinámico definiendo las cantidades Z, Y, S y C como **funciones de transferencia** (Z(s), Y(s), S(s), C(s) para el método operacional; Z(iω)… para respuesta en frecuencia). Relación entre el valor sin carga y el valor realmente medido en la entrada del dispositivo (la ecuación aplicable depende de la variable):

$$u_{i1m}=\frac{1}{Z_{go}/Z_{gi}+1}u_{i1u}\ (3.7.25),\quad\frac{1}{Y_{go}/Y_{gi}+1}u_{i1u}\ (3.7.26),\quad\frac{1}{S_{go}/S_{gi}+1}u_{i1u}\ (3.7.27),\quad\frac{1}{C_{go}/C_{gi}+1}q_{i1u}\ (3.7.28)$$

Al ser Z, Y… números complejos que varían con la frecuencia (si el sistema es algo no lineal, también dependen de la amplitud de entrada), se calcula amplitud y fase de la señal medida. Función de transferencia **cargada**:

$$Q_o(i\omega)=\frac{1}{Z_{go}(i\omega)/Z_{gi}(i\omega)+1}\frac{\theta_o}{u_i}(i\omega)\,Q_{i1u}(i\omega)\ (3.7.29),\qquad\left(\frac{\theta_o}{u_{i1u}}\right)(i\omega)\triangleq\frac{1}{Z_{go}/Z_{gi}+1}\frac{\theta_o}{u_i}(i\omega)\ (3.7.30)$$

con θ₀ la salida real del dispositivo (sin carga en su salida) y u_i el valor que existiría si el dispositivo no cargara el medio. En forma operacional: (3.7.31) y, por producto cruzado, $[Z_{go}(s)+Z_{gi}(s)]\sum a_is^i\theta_o=[Z_{gi}(s)]\sum b_js^ju_{i1u}$ (3.7.32).

> **Ejemplo: instrumento para medir velocidad de traslación.** Función sin carga: $B_i(\dot x_i-\dot x_0)-K_{is}x_o=M_i\ddot x_o$ (3.7.33):
>
> $$\frac{x_o}{v_i}(s)=\frac{K_i}{s^2/\omega_{ni}^2+2\zeta_is/\omega_{ni}+1}\ (3.7.34),\quad K_i=\frac{B_i}{K_{is}}\ (3.7.35),\quad\zeta_i=\frac{B_i}{2\sqrt{K_{is}M_i}}\ (3.7.36),\quad\omega_{ni}=\sqrt{\frac{K_{is}}{M_i}}\ (3.7.37)$$
>
> Al conectarlo a un sistema vibrante, el instrumento distorsiona la velocidad medida. Como la velocidad es una variable de flujo, se usa la **admitancia**: admitancia de entrada $Y_{gi}(s)=(v/f)(s)$ con f − K_is·x₀ = M_i·ẍ₀ (3.7.38) y f = B_i(v − ẋ₀) (3.7.39):
>
> $$Y_{gi}(s)=\frac{(1/B_i)\left(s^2/\omega_{ni}^2+2\zeta_is/\omega_{ni}+1\right)}{s^2/\omega_{ni}^2+1}\qquad(3.7.40)$$
>
> Admitancia de salida del sistema medido: f − B·ẋ − K_s·x = M·ẍ (3.7.41), $Y_{go}(s)=\dfrac{(1/K_s)\,s}{s^2/\omega_n^2+2\zeta s/\omega_n+1}$ (3.7.42). Entonces

$$\frac{x_o}{v_{i1u}}(s)=\frac{1}{\dfrac{Y_{go}(s)}{Y_{gi}(s)}+1}\,\frac{x_o}{v_i}(s)\ \ (3.7.43)$$

> con el factor de carga explícito en función de ωₙ, ζ, B_i, K_s y ωₙᵢ (el original lo marca como «efecto de la carga»). **Resultado cualitativo:** el efecto de la carga es más severo para frecuencias cercanas a la frecuencia natural del sistema de medida y cercano a cero para frecuencias muy bajas o muy altas; como se expresa en frecuencia, puede tratarse para cualquier entrada con series de Fourier, transformadas o densidad espectral de media cuadrada.

```json
{
  "type": "image",
  "id": "image-002",
  "page": 88,
  "pdf_page": 106,
  "title": "Figura 3.27 (sin título en el original)",
  "caption": null,
  "description": "El pie de figura dice solo «Figura 3.27:» sin descripción. Se refiere al efecto de la carga del ejemplo de velocidad (3.7.6), según el contexto (el texto lo cita como «Fig.()»). Contenido no determinado.",
  "elements": [],
  "source": null
}
```

### 3.8 Señales y ruido en los sistemas de medida

**Representación estadística de señales aleatorias.** Una señal aleatoria observada durante T₀ no se describe con y(t) continua, sino por N muestras y₁…y_N tomadas cada ΔT = T₀/N (la i-ésima en t = i·ΔT), con ΔT que cumpla el **teorema de muestreo de Nyquist**. Con ellas se calculan cantidades estadísticas de la sección observada, que estiman bien el comportamiento futuro si (a) T₀ es suficientemente extenso (N grande) y (b) la señal es **estacionaria** (las cantidades estadísticas a largo plazo no cambian con el tiempo).

#### 3.8.1 Efectos del ruido y la interferencia en los circuitos de medida

Fuente y carga en instalaciones industriales pueden estar a unos 100 m, de modo que aparecen voltajes de ruido o interferencia.

**Transmisión de voltaje con interferencia en modo serie (V_SM).** La interferencia está en serie con E_Th. Con R_c (resistencia del cable):

$$V_L=\frac{Z_L}{Z_{Th}+R_c+Z_L}\left(E_{Th}+V_{SM}\right)\ (3.8.1)\ \xrightarrow{Z_L\gg R_c+Z_{Th}}\ V_L=E_{Th}+V_{SM}\ (3.8.2)$$

Todo V_SM aparece en la carga. **Relación señal/ruido:**

$$\frac SN=20\log_{10}\frac{E_{Th}}{V_{SM}}=10\log_{10}\frac{W_S}{W_N}\ \text{dB}\qquad(3.8.3)$$

(valores rms; W_S y W_N potencias de señal y ruido). Ejemplo: E_Th = 1 V, V_SM = 0.1 V → S/N = +20 dB.

**Transmisión de corriente con la misma interferencia.** La corriente de la fuente i_N se divide entre Z_N y Z_L; la corriente por la carga debida a la fuente es $i=i_N\,Z_N/(Z_N+R_c+Z_L)$, y la debida a la interferencia $i_{SM}=V_{SM}/(Z_N+R_c+Z_L)$:

$$V_L=iZ_L+i_{SM}Z_L\ (3.8.4)=i_NZ_L\frac{Z_N}{Z_N+R_c+Z_L}+V_{SM}\frac{Z_L}{Z_N+R_c+Z_L}\ (3.8.5)\ \xrightarrow{R_c+Z_L\ll Z_N}\ V_L\approx i_NZ_L+\frac{Z_L}{Z_N}V_{SM}\ (3.8.6)$$

Solo una fracción pequeña de V_SM aparece en la carga: la **transmisión de corriente tiene mayor inmunidad** a la interferencia en modo serie. Por eso, en un sistema de temperatura con termocupla, puede ser mejor convertir los milivoltios de la fem en una señal de corriente antes de transmitir.

> **Observación de fidelidad.** El texto afirma «puesto que Z_L/Z_N ≈ 1» en la ecuación (3.8.6), pero la conclusión (fracción pequeña de V_SM) y la condición R_c + Z_L ≪ Z_N implican Z_L/Z_N ≪ 1. Se conserva lo impreso y se señala la discrepancia.

**Interferencia en modo común (V_CM).** Los potenciales de ambos lados del circuito de señal se elevan en V_CM respecto a tierra. Con Z_L ≫ R_c + Z_Th, i → 0 y las caídas iR_c/2 son despreciables: potencial en B = V_CM, en A = V_CM + E_Th, y V_L = V_B − V_A = E_Th (la carga no se ve afectada por V_CM). Sin embargo, existe la posibilidad de **conversión de modo común a modo serie**.

#### 3.8.2 Fuentes de ruido y mecanismos de acople

**Ruido interno.** El movimiento térmico aleatorio de portadores de carga en resistores y semiconductores produce el **ruido térmico o de Johnson**, con densidad espectral de potencia uniforme (**ruido blanco**) y proporcional a la temperatura absoluta θ_K:

$$\phi=4Rk\theta_K\ \text{W/Hz}\ (3.8.7);\qquad W=\int_{f_1}^{f_2}4Rk\theta\,df=4Rk\theta(f_2-f_1)\ (3.8.8);\qquad V_{RMS}=\sqrt{4Rk\theta(f_2-f_1)}\ (3.8.9)$$

con R en ohmios y k = 1.4×10⁻²³ J·K⁻¹ (constante de Boltzmann, valor impreso en el documento). *Ejemplo:* R = 10⁶ Ω, f₂ − f₁ = 10⁶ Hz, θ = 300 K → V_RMS = **130 μV**, comparable con señales de bajo nivel como la salida de un puente de galgas.

El **ruido de disparo** (*shot noise*), similar, ocurre en transistores por fluctuaciones aleatorias en la difusión de portadores a través de una unión; también tiene densidad espectral de potencia en un amplio rango de frecuencias.

> **Nota de estructura.** El capítulo termina de forma abrupta en la página 91: la sección 3.8.2 solo trata ruido interno (térmico y de disparo); el título «mecanismos de acople» no se desarrolla en el texto disponible, y la página 92 está en blanco. Varias referencias cruzadas del capítulo aparecen sin resolver en el original («Fig.(zz)», «Fig.()», «sección ??», «ecuación ????»).

---

## Ejemplo práctico (Capítulo 3)

> **Síntesis propia basada en el documento. No constituye una reproducción literal.** Dependencias: Python 3 y `numpy`. Se comprobó únicamente que el código se ejecuta con datos sintéticos (la linealización semilog recupera τ = 1 de una exponencial ideal y la respuesta del Ejemplo 3 da ≈2 mm al estabilizarse); **no se probó con datos experimentales**.

```python
import numpy as np

def tau_semilog(t, theta, K):
    """Estima tau con la linealización xi = ln(1 - theta/K) = -t/tau (ec. 3.6.3).
    Usar solo puntos con theta < K (el logaritmo requiere 1 - theta/K > 0)."""
    xi = np.log(1.0 - theta / K)
    pend, _ = np.polyfit(t, xi, 1)       # pendiente = -1/tau
    return -1.0 / pend

def respuesta_escalon_2o(t, wn, zeta):
    """Respuesta al escalón unitario de un sistema de segundo orden (ecs. 3.3.9-3.3.11)."""
    if np.isclose(zeta, 1.0):
        return 1 - np.exp(-wn * t) * (1 + wn * t)
    if zeta < 1:
        wd = wn * np.sqrt(1 - zeta**2)
        return 1 - np.exp(-zeta * wn * t) * (np.cos(wd * t) + zeta / np.sqrt(1 - zeta**2) * np.sin(wd * t))
    s = wn * np.sqrt(zeta**2 - 1)
    return 1 - np.exp(-zeta * wn * t) * (np.cosh(s * t) + zeta / np.sqrt(zeta**2 - 1) * np.sinh(s * t))

def zeta_por_decremento(x1, xn, n):
    """Aproximación para sistemas ligeramente amortiguados (ec. 3.6.7)."""
    return np.log(x1 / xn) / (2 * np.pi * n)
```

---

## Observaciones de fidelidad acumuladas (Parte 02)

1. Ejemplo 1: ΔE/ΔT = 46 μV/°C a 100 °C no sale con los cuatro términos impresos de (2.2.13) (≈ 42.8); se conserva 46.
2. Ec. (3.3.16): coeficiente del transitorio impreso como «ωτ²û/(1+ω²τ²)»; derivación estándar da ωτû/(1+ω²τ²); verificar página impresa 59 (PDF 77).
3. Ec. (3.4.7): signo inconsistente del término en B entre las dos expresiones; el elemento final se llama «contador» en el texto y «Registrador» en la figura; no se dan valores de A–E.
4. Criterio (3.5.3): «frecuencias mayores a ω_MAX/2π Hz» (probablemente «menores»).
5. Ec. (3.5.4) desordenada en la capa de texto; reconstruida.
6. Ec. (3.6.5): *a*, *A*, *T* no se definen en el texto, solo en la figura.
7. Sección 3.7.3: registrador de «10 Ω» vs resultado coherente con 10 kΩ; frase final truncada.
8. Referencias sin resolver o con numeración ajena: «Fig.(zz)», «Fig.()», «sección 8.7», «figura 5.11», «tabla 5.1», «sección ??», «ecuación ????».
9. Ec. (3.7.18): «rF_s» en lugar de F_s.
10. Ec. (3.8.6): «Z_L/Z_N ≈ 1» contradice la condición R_c + Z_L ≪ Z_N y la conclusión del texto.
11. Constante de Boltzmann impresa como 1.4×10⁻²³ J/K (se conserva).
12. Figura 3.27 sin título; Sección 3.8.2 incompleta; la página 92 está en blanco.
13. Varias figuras se describen solo desde pie de figura y capa de texto (`basis` en cada JSON): no se rasterizaron en esta parte.

**Fin de la Parte 02.** La **Parte 03** comienza en el Capítulo 4, *Análisis Estadístico de Datos Experimentales* (p. impresa 93 / PDF 111).
