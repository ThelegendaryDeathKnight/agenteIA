# Fundamentos de Instrumentación — Parte 03

> **Parte 03 de ~5 · Cubre: Capítulo 4 completo, «Análisis Estadístico de Datos Experimentales» (páginas impresas 93–132 · páginas PDF 111–150).**
> Continúa de la Parte 02 (terminó en la sección 3.8.2, p. 91). La Parte 04 comienza en el Capítulo 5, «Incertidumbre Experimental» (p. impresa 133 / PDF 151).
> Convenciones: `page` = página impresa; `pdf_page = page + 18`. IDs continuos: esta parte usa `table-008`…`table-015` y `chart-028`…`chart-042`. La Parte 04 continúa en `table-016`, `chart-043`, `diagram-027`, `image-003`.
> Leyenda: texto sin marca = contenido del documento (redactado de forma concisa, sin cambiar cifras); **«Síntesis propia»** = contenido generado por el modelo; **«Observación de fidelidad»** = discrepancia del original, conservada sin corregir.

---

## Capítulo 4. Análisis estadístico de datos experimentales

### 4.1 Introducción

- Prácticamente todo proceso de medición muestra características aleatorias: aun midiendo repetidamente un parámetro fijo con el mismo sistema, los resultados no coinciden. Causas: variables no controladas (o no controlables) que afectan la medida, o falta de precisión del proceso de medición.
- En algunos casos la aleatoriedad es tan dominante que es difícil distinguir los datos de los valores indeseables (común en ciencias sociales y a veces en ingeniería); la estadística ofrece herramientas para separarlos.

### 4.2 Conceptos generales

- Los errores de medición se dividen en **de sesgo** (sistemáticos) y **de precisión** (aleatorios). Los de sesgo son consistentes y a menudo se minimizan por calibración; los de precisión son los que mejor se tratan con métodos estadísticos. La estadística sirve también para **planear experimentos** con muchas variables independientes o parámetros.
- Pasos propuestos: (1) caracterizar los datos con parámetros de tendencia central y dispersión; (2) seleccionar la función de distribución teórica que mejor explique los datos; (3) usarla para predecir propiedades de los datos.

#### 4.2.1 Medidas de tendencia central

Media muestral y poblacional (población finita de N elementos):

$$\bar x=\frac{x_1+x_2+\cdots+x_n}{n}=\sum_{i=1}^{n}\frac{x_i}{n}\ (4.2.1),\qquad\mu=\sum_{i=1}^{N}\frac{x_i}{N}\ (4.2.2)$$

- **Mediana:** valor central de los datos ordenados (si el número es par, promedio de los dos centrales).
- **Moda:** valor correspondiente al pico de probabilidad. En espacio discreto, el de mayor frecuencia; en continuo, el punto medio del intervalo con mayor frecuencia. Puede no existir (p. ej. distribución uniforme) o haber varias (bimodal), no necesariamente con la misma frecuencia.
- Media, mediana y moda suelen ser cercanas, pero en algunos conjuntos difieren significativamente.

#### 4.2.2 Medidas de dispersión

- **Desviación:** $d_i=x_i-\bar x$ (4.2.3). **Desviación media:** $\bar d=\sum|d_i|/n$ (4.2.4).
- **Desviación estándar de la población** (N elementos) y **muestral** (se usa cuando la muestra estima la desviación de la población):

$$\sigma=\sqrt{\sum_{i=1}^{N}\frac{(x_i-\bar x)^2}{N}}\ (4.2.5),\qquad S=\sqrt{\sum_{i=1}^{n}\frac{(x_i-\bar x)^2}{n-1}}\ (4.2.6)$$

- **Varianza:** σ² (población) o S² (muestra) (4.2.7).

```json
{
  "type": "table",
  "id": "table-008",
  "page": 95,
  "pdf_page": 113,
  "title": "Tabla 4.1: Resultados de 60 mediciones de la temperatura en un ducto",
  "headers": ["Número de lecturas", "Temperatura [°C]"],
  "rows": [[1, 1089], [1, 1092], [2, 1094], [4, 1095], [8, 1098], [9, 1100], [12, 1104], [4, 1105], [5, 1107], [5, 1108], [4, 1110], [3, 1112], [2, 1113]],
  "notes": "La suma de lecturas es 60. En el original el encabezado dice «Temperarura».",
  "source": null
}
```

```json
{
  "type": "table",
  "id": "table-009",
  "page": 96,
  "pdf_page": 114,
  "title": "Tabla 4.2: Medidas de la temperatura arregladas en intervalos",
  "headers": ["Intervalo [°C]", "Número de medidas"],
  "rows": [["1085 ≤ T < 1090", 1], ["1090 ≤ T < 1095", 3], ["1095 ≤ T < 1100", 12], ["1100 ≤ T < 1105", 21], ["1105 ≤ T < 1110", 14], ["1110 ≤ T < 1115", 7], ["1115 ≤ T < 1120", 2]],
  "notes": "La suma de medidas es 60.",
  "source": null
}
```

> **Ejemplo 5 (del documento).** Con las mediciones de la Tabla 4.1 (gas recalentado en un ducto): **media x̄ = 1103 °C; mediana = 1104 °C; desviación estándar S = 5.79 °C; varianza S² = 33.49 °C²; moda = 1104 °C.**

> **Observación de fidelidad (cálculo del convertidor).** Calculando con los datos de la Tabla 4.1 (60 lecturas) resulta media ≈ 1102.97, mediana 1104, moda 1104 (12 lecturas), S ≈ 5.66 °C y S² ≈ 32.0 °C². El documento da S = 5.79 y S² = 33.49 (nótese además que 5.79² ≈ 33.52). Se conservan las cifras originales.

### 4.3 Probabilidad

Probabilidad de un evento A: $P(A)=m/n$ (m ocurrencias exitosas sobre n resultados, con n ≫ 1) (4.3.1); se escribe P(x) para variable continua y P(xᵢ) para discreta. **Propiedades** (del documento):

1. 0 ≤ P ≤ 1. 2. Evento seguro: P(A) = 1. 3. Evento imposible: P(A) = 0.
4. Complemento: $P(\bar A)=1-P(A)$ (4.3.2).
5. Mutuamente excluyentes: la probabilidad de A o B es P(A) + P(B) (4.3.3) *(escrito «P(A Y B)» en el texto extraído)*.
6. Independientes: $P(A\cap B)=P(A)\,P(B)$ (4.3.4).
7. $P(A\cup B)=P(A)+P(B)-P(AB)$.
8. $\sum_{i=1}^{n}P(x_i)=1$ (4.3.5).
9. Media (esperanza) de variable discreta: $\mu=\sum x_iP(x_i)=E(x)$ (4.3.6).
10. Varianza: $\sigma^2=\sum(x_i-\mu)^2P(x_i)$ (4.3.7).

#### 4.3.1 Función densidad de probabilidad

Para variable continua, f(x) tal que $f(x_i)dx=P(x_i\le x\le x_i+dx)$ (4.3.8); $P(a\le x\le b)=\int_a^bf(x)dx$ (4.3.9). La probabilidad de un valor único es cero; $P(-\infty\le x\le\infty)=1$.

$$E(x)=\mu=\int_{-\infty}^{\infty}xf(x)dx\ \text{(primer momento)}\ (4.3.10),\qquad\sigma^2=\int_{-\infty}^{\infty}(x-\mu)^2f(x)dx\ \text{(segundo momento)}\ (4.3.11)$$

> **Ejemplo 6 (del documento).** Vida de rodamientos: $f(x)=0$ para x < 10 h y $f(x)=200/x^3$ para x > 10 h (Fig. 4.1). (a) Esperanza de vida: $E(x)=\int_{10}^{\infty}x\frac{200}{x^3}dx=\left.-\frac{200}{x}\right|_{10}^{\infty}=20$ h. (b) P(x < 20) = ∫₁₀²⁰ 200/x³ dx = **0.75**; P(x > 20) = 1 − P(x ≤ 20) = **0.25**; P(x = 20) = **0**.

```json
{
  "type": "chart",
  "id": "chart-028",
  "page": 99,
  "pdf_page": 117,
  "title": "Figura 4.1: Función distribución de probabilidad",
  "chart_type": "line",
  "axes": {"x": {"label": "h", "range": [0, 37.5], "ticks": [0, 12.5, 25, 37.5]}, "y": {"label": "f(x)", "ticks": [0, 0.1, 0.2]}},
  "series": [{"name": "f(x) = 200/x^3 para x > 10", "values": null, "visual_summary": "curva decreciente que parte en x = 10 h (valor 0.2) y tiende a 0; marca vertical cerca de x = 20"}],
  "description": "Densidad de probabilidad de la vida de rodamientos (Ejemplo 6). f(10) = 200/1000 = 0.2 se deduce de la fórmula.",
  "basis": "vista rasterizada de baja resolución + fórmula del texto"
}
```

#### 4.3.2 Función de distribución acumulativa

$$F(x)=P(rv\le x)=\int_{-\infty}^{x}f(x)dx\ (4.3.12),\qquad F(x_i)=\sum_{j=1}^{i}P(x_j)\ (4.3.13)$$

Relaciones: $P(a<x\le b)=F(b)-F(a)$ y $P(x>a)=1-F(a)$ (4.3.14).

> **Observación de fidelidad.** En (4.3.12) la capa de texto muestra el límite superior de la integral como ∞ en lugar de x; el Ejemplo 7 usa ∫₋∞ˣ, que es lo coherente. Se transcribe con x.

> **Ejemplo 7 (del documento).** Para los rodamientos del ejemplo anterior (probabilidad de vida menor que (a) 15 h y (b) 20 h): F(x) = 0 para x ≤ 10 y $F(x)=\int_{10}^{x}\frac{200}{x^3}dx=1-\frac{100}{x^2}$ para x > 10 (Fig. 4.2).
> *Síntesis propia:* el documento deduce F(x) pero no evalúa los valores pedidos; con esa fórmula, F(15) = 1 − 100/225 ≈ **0.556** y F(20) = 1 − 100/400 = **0.75** (coincide con el Ejemplo 6).

```json
{
  "type": "chart",
  "id": "chart-029",
  "page": 100,
  "pdf_page": 118,
  "title": "Figura 4.2: Función de distribución acumulativa",
  "chart_type": "line",
  "axes": {"x": {"label": "x", "range": [0, 50], "ticks": [0, 12.5, 25, 37.5, 50]}, "y": {"label": "F(x)", "range": [0, 1], "ticks": [0, 0.25, 0.5, 0.75, 1]}},
  "series": [{"name": "F(x) = 1 - 100/x^2 para x > 10", "values": null, "visual_summary": "nula hasta x = 10; luego creciente y tendiendo asintóticamente a 1"}],
  "description": "Acumulada del Ejemplo 7.",
  "basis": "vista rasterizada de baja resolución + fórmula del texto"
}
```

#### 4.3.3 Distribución binomial

Variables discretas con dos resultados (éxito/falla); útil en control de calidad. **Condiciones:** (1) cada ensayo tiene solo dos resultados; (2) la probabilidad de éxito p es constante; (3) n ensayos independientes. Probabilidad de exactamente r éxitos en n ensayos, media y desviación:

$$P(r)=\frac{n!}{r!(n-r)!}p^r(1-p)^{n-r}=\binom nr p^r(1-p)^{n-r}\ (4.3.15),\qquad\mu=np\ (4.3.16),\qquad\sigma=\sqrt{np(1-p)}\ (4.3.17)$$

> **Ejemplo 8 (del documento).** Un fabricante afirma que solo 10 % de sus computadores requiere reparación en garantía. Probabilidad de que, en 20 computadores, 5 requieran reparación: éxito = «no requiere reparación», p = 0.9; 15 éxitos de 20: $P=\binom{20}{15}0.9^{15}(0.1)^5=0.032$ (3.2 %).

> **Ejemplo 9 (del documento).** 10 % de bombillas defectuosas; se compran 4 (éxito = «bombilla defectuosa», p = 0.1):

| Defectuosas (r) | 4 | 3 | 2 | 1 | 0 |
|---|---|---|---|---|---|
| P(r) | 0.0001 (0.01 %) | 0.0036 (0.36 %) | 0.0486 (4.86 %) | 0.2916 (29.16 %) | 0.6561 (65.61 %) |

La suma de los cinco resultados es ≈ 1.

#### 4.3.4 Distribución de Poisson

> **Definición 3.** x tiene distribución de Poisson con parámetro α > 0 si $P(x=k)=\dfrac{e^{-\alpha}\alpha^k}{k!},\ k=0,1,\dots,n$ (4.3.18).
>
> **Teorema 1.** E(x) = α y S(x) = α (S(x) denota aquí la varianza). *Prueba (resumen del documento):* $E(x)=\sum_{k\ge1}\frac{e^{-\alpha}\alpha^k}{(k-1)!}=\alpha\sum_{\lambda\ge0}\frac{e^{-\alpha}\alpha^\lambda}{\lambda!}=\alpha$; $E(x^2)=\alpha E(x)+\alpha=\alpha^2+\alpha$; luego $S(x)=E(x^2)-[E(x)]^2=\alpha$.

Propiedad destacada: **esperanza y varianza de Poisson son iguales**. Existen tablas de Poisson (ref. [19]).

#### 4.3.5 Distribución gaussiana (normal)

Describe la dispersión de mediciones cuya variación se debe a factores aleatorios, con desviaciones positivas y negativas igualmente probables. Densidad con media μ y desviación σ:

$$f(x)=\frac1{\sigma\sqrt{2\pi}}\exp\left(-\frac{(x-\mu)^2}{2\sigma^2}\right)\qquad(4.3.19)$$

La Fig. 4.3 muestra f(x) para μ = 2 y σ = 0.5, 0.6, 0.8, 1.0, 2.0: simétrica respecto a la media; a menor σ, mayor pico.

```json
{
  "type": "chart",
  "id": "chart-030",
  "page": 104,
  "pdf_page": 122,
  "title": "Figura 4.3: Función de distribución normal para μ = 2, σ = 0.5, 0.6, 0.8, 1.0, 2.0",
  "chart_type": "line",
  "axes": {"x": {"label": "x", "range": [0, 5], "ticks": [0, 1.25, 2.5, 3.75, 5]}, "y": {"label": "f(x)", "range": [0, 1], "ticks": [0, 0.25, 0.5, 0.75, 1]}},
  "series": [
    {"name": "σ = 0.5", "values": null, "peak": "1/(0.5·√(2π)) ≈ 0.80 (calculado de la fórmula)"},
    {"name": "σ = 0.6", "values": null},
    {"name": "σ = 0.8", "values": null},
    {"name": "σ = 1.0", "values": null},
    {"name": "σ = 2.0", "values": null}
  ],
  "description": "Cinco campanas centradas en x = 2; los picos decrecen al aumentar σ. Las curvas en la figura son de colores distintos, sin leyenda en el original.",
  "basis": "vista rasterizada de baja resolución + capa de texto"
}
```

#### 4.3.6 Propiedades de la distribución normal

1. **∫f = 1.** Con u = (x − μ)/σ, $I=\frac1{\sqrt{2\pi}}\int_{-\infty}^{\infty}e^{-u^2/2}du$ (4.3.20). Se calcula I² como integral doble (4.3.21) y se pasa a coordenadas polares u = r cos θ, v = r sen θ, du dv = r dr dθ (4.3.22-4.3.23); resulta $I^2=\frac1{2\pi}\int_0^{2\pi}d\theta=1$, luego I = 1.
2. **Forma:** campana simétrica respecto a μ, cóncava hacia abajo en x = μ y hacia arriba para valores grandes; **puntos de inflexión en x = μ ± σ**. σ grande → «achatada»; σ pequeño → «aguzada».
3. **Probabilidad en un intervalo** (4.3.24) $P(x_1\le x\le x_2)=\frac1{\sigma\sqrt{2\pi}}\int_{x_1}^{x_2}\exp\!\left(-\frac{(x-\mu)^2}{2\sigma^2}\right)dx$; no tiene primitiva analítica (función de error) y se integra numéricamente. Con la variable estandarizada $z=(x-\mu)/\sigma$ (4.3.25), $f(z)=\frac1{\sqrt{2\pi}}e^{-z^2/2}$ (4.3.26, normal estándar: μ = 0, σ = 1), dx = σ dz y

$$P(x_1\le x\le x_2)=P(z_1\le z\le z_2)=\frac1{\sqrt{2\pi}}\int_{z_1}^{z_2}e^{-z^2/2}dz\ (4.3.27\text{–}4.3.28)$$

   Por simetría: $P(-z_1\le z\le0)=P(0\le z\le z_1)=\tfrac12P(-z_1\le z\le z_1)$ (4.3.29). Con α = suma de las áreas de las dos colas (Fig. 4.4):

$$P[-z_{\alpha/2}\le z\le z_{\alpha/2}]=1-\alpha\ (4.3.30)$$

$$P\!\left[-z_{\alpha/2}\le\frac{\bar x-\mu}{\sigma/\sqrt n}\le z_{\alpha/2}\right]=P\!\left[\bar x-z_{\alpha/2}\frac{\sigma}{\sqrt n}\le\mu\le\bar x+z_{\alpha/2}\frac{\sigma}{\sqrt n}\right]=1-\alpha\ (4.3.31)\ \Rightarrow\ \mu=\bar x\pm z_{\alpha/2}\frac{\sigma}{\sqrt n}\ (4.3.32)$$

   con nivel de confianza 1 − α.
4. **Esperanza:** con z = (x − μ)/σ, $E(x)=\frac{\sigma}{\sqrt{2\pi}}\int ze^{-z^2/2}dz+\frac{\mu}{\sqrt{2\pi}}\int e^{-z^2/2}dz$; la primera integral es cero (integrando impar) y la segunda es 1: **E(x) = μ** (4.3.33-4.3.36).
5. **Varianza:** E(x²) = σ² + μ² (integrando por partes), luego **S(x) = σ²** (4.3.37). Por tanto μ y σ² son la esperanza y la varianza; conocidos ambos, la distribución normal queda completamente especificada.

```json
{
  "type": "chart",
  "id": "chart-031",
  "page": 106,
  "pdf_page": 124,
  "title": "Figura 4.4: Función de distribución normal estándar",
  "chart_type": "line con área sombreada",
  "axes": {"x": {"label": "z", "range": [-2.5, 2.5], "ticks": [-2.5, -1.25, 0, 1.25, 2.5], "marks": ["z1", "z2"]}, "y": {"label": "f(z)", "range": [0, 0.4], "ticks": [0, 0.1, 0.2, 0.3, 0.4]}},
  "series": [{"name": "f(z) = exp(-z²/2)/√(2π)", "values": null, "visual_summary": "campana azul con máximo ≈ 0.4 en z = 0 y área marcada entre z1 y z2"}],
  "description": "Normal estándar; el área entre z1 y z2 es P(z1 ≤ z ≤ z2).",
  "basis": "vista rasterizada de baja resolución + capa de texto"
}
```

#### 4.3.7 Función y distribución gamma

> **Definición 4.** $\Gamma(p)=\int_0^{\infty}x^{p-1}e^{-x}dx,\ p>0$ (4.3.38).

Integrando por partes: Γ(p) = (p − 1)Γ(p − 1) (4.3.39); como Γ(1) = ∫e⁻ˣ dx = 1, para entero n: **Γ(n) = (n − 1)!** (4.3.40).

> **Ejercicio 1.** Verificar que $\Gamma(\tfrac12)=\int_0^{\infty}x^{-1/2}e^{-x}dx=\sqrt\pi$ (4.3.41). *Solución del documento:* con x = u²/2, $\Gamma(\tfrac12)=\sqrt2\int_0^{\infty}e^{-u^2/2}du$ (4.3.42), y por la integral normal $\int_0^{\infty}e^{-u^2/2}du=\sqrt{\pi/2}$ (4.3.43), de donde Γ(½) = √π.

> **Definición 5.** Variable continua x ≥ 0 con distribución gamma si $f(x)=\dfrac{\alpha}{\Gamma(r)}(\alpha x)^{r-1}e^{-\alpha x}$ para x > 0 y 0 en otro caso (4.3.44-4.3.45), con parámetros r > 0 y α > 0.

```json
{
  "type": "chart",
  "id": "chart-032",
  "page": 109,
  "pdf_page": 127,
  "title": "Figura 4.5: Gráfico de la función gamma para diferentes valores de los parámetros r y α",
  "chart_type": "line",
  "axes": {"x": {"label": "x", "range": [0, 10], "ticks": [0, 2.5, 5, 7.5, 10]}, "y": {"label": "f(x)", "range": [0, 1], "ticks": [0, 0.25, 0.5, 0.75, 1]}},
  "series": [
    {"name": "α = 1 (color negro), varios r", "values": null},
    {"name": "α = 1/2 (color azul), varios r", "values": null}
  ],
  "description": "Familia de densidades gamma; los valores de r usados no se indican en el texto.",
  "basis": "vista rasterizada de baja resolución + pie de figura"
}
```

#### 4.3.8 Propiedades de la función gamma

- Si **r = 1**: f(x) = α·e^(−αx) (**distribución exponencial**, caso especial de la gamma).
- Para r entero positivo hay una relación entre la acumulada de la gamma y la de Poisson. Integrando por partes $I=\int_a^{\infty}\frac{y^re^{-y}}{r!}dy$:

$$I=e^{-a}\left[\frac{a^r}{r!}+\frac{a^{r-1}}{(r-1)!}+\cdots+a+1\right]=e^{-a}\sum_{k=0}^{r}\frac{a^k}{k!}=\sum_{k=0}^{r}P(y=k)$$

  donde y tiene distribución de Poisson con parámetro α (así lo escribe el documento; en la expresión aparece «a»).

#### 4.3.9 Distribución t de Student

$$f(t,\nu)=\frac{\Gamma\!\left(\frac{\nu+1}{2}\right)}{\sqrt{\nu\pi}\,\Gamma\!\left(\frac\nu2\right)}\left(1+\frac{t^2}{\nu}\right)^{-\frac{\nu+1}{2}}\qquad(4.3.46)$$

ν = grados de libertad. Curvas simétricas, como la normal; al crecer el número de muestras tiende a la normal. Se usa para estimar el **intervalo de confianza de la media con muestras pequeñas (< 30)**:

$$P[-t_{\alpha/2}\le t\le t_{\alpha/2}]=1-\alpha\ (4.3.47),\qquad P\!\left[\bar x-t_{\alpha/2}\frac S{\sqrt n}\le\mu\le\bar x+t_{\alpha/2}\frac S{\sqrt n}\right]=1-\alpha\ (4.3.48)\ \Rightarrow\ \mu=\bar x\pm t_{\alpha/2}\frac S{\sqrt n}\ (4.3.49)$$

Para no incluir tablas voluminosas se dan solo los **valores críticos** de t (funciones de ν y α) en la Tabla 4.3.

> **Observación de fidelidad.** El texto remite a la «Fig. 5.2.16» para las curvas t de Student; corresponde a la Figura 4.6 de este capítulo.

```json
{
  "type": "chart",
  "id": "chart-033",
  "page": 111,
  "pdf_page": 129,
  "title": "Figura 4.6: Función densidad de probabilidad usando la distribución t Student",
  "chart_type": "line",
  "axes": {"x": {"label": "x", "range": [-2.5, 2.5], "ticks": [-2.5, -1.25, 0, 1.25, 2.5]}, "y": {"label": "y", "range": [0, 0.4], "ticks": [0, 0.1, 0.2, 0.3, 0.4]}},
  "series": [{"name": "curvas t para varios ν (colores distintos, sin leyenda)", "values": null, "visual_summary": "campanas simétricas anidadas; mayor ν, pico más alto (se aproxima a la normal)"}],
  "description": "Los valores de ν de cada curva no se indican en el original.",
  "basis": "vista rasterizada de baja resolución + capa de texto"
}
```

```json
{
  "type": "table",
  "id": "table-010",
  "page": 112,
  "pdf_page": 130,
  "title": "Tabla 4.3: Valores críticos de la distribución t Student",
  "headers": ["ν", "α/2 = 0.100", "α/2 = 0.050", "α/2 = 0.025", "α/2 = 0.010", "α/2 = 0.005"],
  "rows": [
    [1, 3.078, 6.314, 12.706, 31.823, 63.658],
    [2, 1.886, 2.920, 4.303, 6.964, 9.925],
    [3, 1.638, 2.353, 3.182, 4.541, 5.841],
    [4, 1.533, 2.132, 2.776, 3.747, 4.604],
    [5, 1.476, 2.015, 2.571, 3.365, 4.032],
    [6, 1.440, 1.943, 2.447, 3.143, 3.707],
    [7, 1.415, 1.895, 2.365, 2.998, 3.499],
    [8, 1.397, 1.860, 2.306, 2.896, 3.355],
    [9, 1.383, 1.833, 2.262, 2.821, 3.250],
    [10, 1.372, 1.812, 2.228, 2.764, 3.169],
    [11, 1.363, 1.796, 2.201, 2.718, 3.106],
    [12, 1.356, 1.782, 2.179, 2.681, 3.054],
    [13, 1.350, 1.771, 2.160, 2.650, 3.012],
    [14, 1.345, 1.761, 2.145, 2.624, 2.977],
    [15, 1.341, 1.753, 2.131, 2.602, 2.947],
    [16, 1.337, 1.746, 2.120, 2.583, 2.921],
    [17, 1.333, 1.740, 2.110, 2.567, 2.898],
    [18, 1.330, 1.734, 2.101, 2.552, 2.878],
    [19, 1.328, 1.729, 2.093, 2.539, 2.861],
    [20, 1.325, 1.725, 2.086, 2.528, 2.845],
    [21, 1.323, 1.721, 2.080, 2.518, 2.831],
    [22, 1.321, 1.717, 2.074, 2.508, 2.819],
    [23, 1.319, 1.714, 2.069, 2.500, 2.807],
    [24, 1.318, 1.711, 2.064, 2.492, 2.797],
    [25, 1.316, 1.708, 2.060, 2.485, 2.787],
    [26, 1.315, 1.706, 2.056, 2.479, 2.779],
    [27, 1.314, 1.703, 2.052, 2.473, 2.771],
    [28, 1.313, 1.701, 2.048, 2.467, 2.763],
    [29, 1.311, 1.699, 2.045, 2.462, 2.756],
    [30, 1.310, 1.697, 2.042, 2.457, 2.750],
    ["∞", 1.283, 1.645, 1.960, 2.326, 2.576]
  ],
  "notes": "El valor de ν = 15, α/2 = 0.025 aparece como «2.131.» (con punto final) en el original; se transcribe 2.131.",
  "source": null
}
```

> **Ejemplo 10 (del documento).** Un fabricante de circuitos integrados (CI) desea estimar el tiempo medio de falla con 95 % de confianza. Seis sistemas probados (horas): 1250, 1320, 1542, 1464, 1275, 1383. Como n < 30 se usa la t: x̄ = 1372.3 h; $S=\left[\frac15\sum(x_i-\bar x)^2\right]^{1/2}=114$ h. Para 95 %: α = 0.05, ν = 5, α/2 = 0.025 → t = 2.571. Entonces $\mu=1372\pm2.571\times114/\sqrt6=\mathbf{1372\pm120\ h}$. Si aumenta el nivel de confianza, el intervalo también aumenta, y viceversa.

> **Ejemplo 11 (del documento).** Reducir el intervalo de 95 % a ±50 h: ¿cuántos CI adicionales? No se conoce n, así que se procede por ensayo y error. Primera estimación con la normal ($n=(z_{\alpha/2}\sigma/50)^2$, z₀.₀₂₅ = 1.96, S = 114 como estimativo de σ): n = (1.96 × 114/50)² ≈ **20**. Como n < 30 se usa t: para ν = 19, t = 2.093 → n = (2.093 × 114/50)² ≈ **23**; repetir da el mismo valor. Con más pruebas, x̄ también puede cambiar.

### 4.4 Estimación de parámetros

#### 4.4.1 Intervalo de la media de la población

$\mu=\bar x\pm\delta$, es decir $\bar x-\delta\le\mu\le\bar x+\delta$ (4.4.1), con δ la incertidumbre. **Nivel de confianza** = P(x̄ − δ ≤ μ ≤ x̄ + δ) = 1 − α (4.4.2-4.4.3), con α el **nivel de significancia** (probabilidad de que la media caiga fuera del intervalo).

**Teorema del límite central:** de una población con media μ y desviación σ se toman muestras de tamaño n; las medias x̄ᵢ tienden a una distribución normal con desviación estándar (error estándar de la media)

$$\sigma_{\bar x}=\frac{\sigma}{\sqrt n}\qquad(4.4.4)$$

No hace falta que la población sea normal. Requiere n grande (en la mayoría de los casos n > 30). Conclusiones: (a) población normal → x̄ᵢ normales; (b) no normal y n > 30 → x̄ᵢ normales; (c) no normal y n < 30 → solo aproximadamente normales. Con n grande, $z=(\bar x-\mu)/\sigma_{\bar x}$ (4.4.5) y S puede usarse como aproximación de σ.

#### 4.4.2 Intervalo de la varianza de la población

La mejor estimación de σ² es S². Para poblaciones normales se usa la función χ². Con x̄ = μ: $S^2=\frac1{n-1}\sum(x_i-\mu)^2$ (4.4.6), $\chi^2=\frac1{\sigma^2}\sum(x_i-\mu)^2$ (4.4.7), y

$$\chi^2=(n-1)\frac{S^2}{\sigma^2}\qquad(4.4.8)$$

$$f(\chi^2)=\frac{(\chi^2)^{(\nu-2)/2}e^{-\chi^2/2}}{2^{\nu/2}\Gamma(\nu/2)},\ \chi^2>0\qquad(4.4.9)$$

con ν grados de libertad (Fig. 4.7). Intervalo de confianza:

$$P\!\left(\chi^2_{\nu,1-\alpha/2}\le\chi^2\le\chi^2_{\nu,\alpha/2}\right)=1-\alpha\ (4.4.10)\ \Rightarrow\ P\!\left[\chi^2_{\nu,1-\alpha/2}\le(n-1)\frac{S^2}{\sigma^2}\le\chi^2_{\nu,\alpha/2}\right]=1-\alpha\ (4.4.11)$$

$$\frac{(n-1)S^2}{\chi^2_{\nu,\alpha/2}}\le\sigma^2\le\frac{(n-1)S^2}{\chi^2_{\nu,1-\alpha/2}}\qquad(4.4.12)$$

Cada cola tiene área α/2 (Fig. 4.8).

> **Observación de fidelidad.** En (4.4.9) la capa de texto muestra un «2» inicial en el numerador («2(χ²)^((ν−2)/2) …»); la densidad χ² estándar no lo lleva y se transcribe sin él. Verificar con la página impresa 116 (PDF 134). Tampoco se dan en esta parte tablas de χ².

```json
{
  "type": "chart",
  "id": "chart-034",
  "page": 116,
  "pdf_page": 134,
  "title": "Figura 4.7: Distribución f(χ²) ≡ f(z) para algunos valores de ν",
  "chart_type": "line",
  "axes": {"x": {"label": "x", "range": [0, 10], "ticks": [0, 2.5, 5, 7.5, 10]}, "y": {"label": "y", "range": [0, 1], "ticks": [0, 0.25, 0.5, 0.75, 1]}},
  "series": [
    {"name": "ν = 1", "style": "línea continua", "values": null},
    {"name": "ν = 2", "style": "trazos", "values": null},
    {"name": "ν = 3", "style": "puntos", "values": null},
    {"name": "ν = 5", "style": "puntos y trazos", "values": null}
  ],
  "description": "Densidades χ² para cuatro valores de ν; la de ν = 1 y 2 son decrecientes en la zona visible.",
  "basis": "pie de figura + vista rasterizada de baja resolución"
}
```

```json
{
  "type": "chart",
  "id": "chart-035",
  "page": 117,
  "pdf_page": 135,
  "title": "Figura 4.8: Intervalo de confianza para la distribución chi-cuadrado",
  "chart_type": "line con áreas de cola",
  "axes": {"x": {"label": "x", "range": [0, 10], "ticks": [0, 2.5, 5, 7.5, 10]}, "y": {"label": "y", "range": [0, 0.3], "ticks": [0, 0.05, 0.1, 0.15, 0.2, 0.25, 0.3]}},
  "series": [{"name": "f(χ²)", "values": null, "visual_summary": "curva con un solo máximo y cola derecha; se marcan las dos colas de área α/2"}],
  "description": "Ilustra la ecuación (4.4.10).",
  "basis": "vista rasterizada de baja resolución + capa de texto"
}
```

#### 4.4.3 Criterio para el rechazo de datos dudosos

Si un valor medido aparece fuera de línea y se detecta una falla clara, se puede descartar. Si no, existen métodos estadísticos que eliminan valores de baja probabilidad. Criterios simples «sigma-dos» o «sigma-tres» (rechazar lo que se desvía más de 2 o 3 desviaciones) deben modificarse por el tamaño de la muestra; según el criterio, podrían eliminarse datos buenos o incluirse malos.

**Método recomendado (ANSI/ASME 86, ref. [1]): Thompson τ modificada.** Con n medidas, media x̄ y desviación S, se ordenan los datos; los extremos (más alto y más bajo) son candidatos. Se calcula $\delta_i=|x_i-\bar x|$ (4.4.13) y se toma el mayor; de la Tabla 4.4 se obtiene τ. Si

$$\delta>\tau S\qquad(4.4.14)$$

el dato se rechaza. **Solo se elimina un dato por vez**: se recalculan x̄ y S y se repite hasta que no deba eliminarse ninguno.

```json
{
  "type": "table",
  "id": "table-011",
  "page": 118,
  "pdf_page": 136,
  "title": "Tabla 4.4: Valores de los coeficientes de Thompson. Según: ANSI/ASME-86",
  "headers": ["n", "τ"],
  "rows": [
    [3, 1.150], [4, 1.393], [5, 1.572], [6, 1.656], [7, 1.711], [8, 1.749], [9, 1.777], [10, 1.798], [11, 1.815], [12, 1.829], [13, 1.840],
    [14, 1.849], [15, 1.858], [16, 1.865], [17, 1.871], [18, 1.876], [19, 1.881], [20, 1.885], [21, 1.889], [22, 1.893], [23, 1.896],
    [24, 1.899], [25, 1.902], [26, 1.904], [27, 1.906], [28, 1.908], [29, 1.910], [30, 1.911], [31, 1.913], [32, 1.914], [33, 1.916],
    [34, 1.917], [35, 1.919], [36, 1.920], [37, 1.921], [38, 1.922], [39, 1.923], [40, 1.924], [41, 1.925], [42, 1.926]
  ],
  "notes": "En el original la tabla está dispuesta en cuatro bloques de columnas (n, τ) y se aplanó a una sola lista ordenada por n.",
  "source": "ANSI/ASME (1986), ref. [1] del documento"
}
```

> **Ejemplo 12 (del documento).** Nueve medidas de tensión (V): 12.02, 12.05, 11.96, 11.99, 12.10, 12.03, 12.00, 11.95, 12.16. V̄ = 12.03 V, S = 0.07. δ₁ = |12.16 − 12.03| = 0.13; δ₂ = |11.95 − 12.03| = 0.08. Para n = 9, τ = 1.777 → τS = 0.124; como δ₁ = 0.13 > 0.124, **12.16 se rechaza**. Recalculando: S = 0.05, V̄ = 12.02; para n = 8, τ = 1.749, τS = 0.09 y **no se rechaza ningún otro dato**.

> **Observación de fidelidad (cálculo del convertidor).** Sin redondear: tras eliminar 12.16, V̄ = 12.0125 y S = 0.0489, de modo que τS = 1.749 × 0.0489 ≈ 0.0856, y el dato 12.10 tiene δ ≈ 0.0875 > 0.0856 (se rechazaría). El documento redondea τS a 0.09 y concluye que no se rechaza nada. Se conserva la conclusión original.

### 4.5 Correlación de los datos experimentales

La dispersión por errores aleatorios puede ocultar una tendencia. El **coeficiente de correlación lineal** rₓᵧ indica si existe relación funcional entre x e y a partir de n pares (xᵢ, yᵢ):

$$r_{xy}=\frac{\sum_{i=1}^{n}(x_i-\bar x)(y_i-\bar y)}{\left[\sum_{i=1}^{n}(x_i-\bar x)^2\sum_{i=1}^{n}(y_i-\bar y)^2\right]^{1/2}}\ (4.5.1),\qquad\bar x=\frac1n\sum x_i,\ \bar y=\frac1n\sum y_i\ (4.5.2)$$

- r ∈ [−1, +1]: +1 relación lineal perfecta de pendiente positiva; −1 perfecta de pendiente negativa; 0 sin correlación lineal (aun sin correlación es raro que r sea exactamente 0).
- **Valores críticos r_t** (ref. [34]) según n y nivel de significancia α (Tabla 4.5). Por cada r_t hay solo una probabilidad α de que un r_xy experimental lo supere por puro azar. Con 95 % de confianza (α = 0.05): si |r_xy| > r_t, y depende de x de forma no aleatoria y una relación lineal da alguna aproximación; si |r_xy| < r_t no hay confianza en una relación funcional lineal.
- No es necesario que la relación sea realmente lineal para obtener un r significativo (una parábola con poca dispersión puede dar r alto), y relaciones fuertes pero multivaloradas (funciones circulares) dan r muy bajo.
- **Precauciones:** un solo dato mal tomado puede afectar mucho a r; un r significativo **no implica causalidad** (debe determinarse por otro camino).

> **Ejemplo 13 (del documento).** Se sabe que los tiempos por vuelta en una carrera dependen de la temperatura ambiente. Datos (misma pista, mismo carro y piloto): ¿existe relación lineal?

```json
{
  "type": "table",
  "id": "table-012",
  "page": 120,
  "pdf_page": 138,
  "title": "Ejemplo 13: temperatura ambiente y tiempo por vuelta",
  "headers": ["Temperatura ambiente (°C)", "Tiempo por vuelta (s)"],
  "rows": [[4.4, 65.3], [8.3, 66.5], [12.8, 67.3], [16.7, 67.8], [18.9, 67.0], [31.1, 66.6]],
  "notes": "Enunciado del ejemplo.",
  "source": null
}
```

```json
{
  "type": "table",
  "id": "table-013",
  "page": 120,
  "pdf_page": 138,
  "title": "Ejemplo 13: cálculo del coeficiente de correlación",
  "headers": ["x (tiempo, s)", "y (temperatura, °C)", "x − x̄", "(x − x̄)²", "y − ȳ", "(y − ȳ)²", "(x − x̄)(y − ȳ)"],
  "rows": [
    [65.3, 4.4, -1.45, 2.10, -10.967, 120.28, 15.90],
    [66.5, 8.3, -0.25, 0.06, -7.067, 49.94, 1.77],
    [67.3, 12.8, 0.55, 0.30, -2.567, 6.59, -1.41],
    [67.8, 16.7, 1.05, 1.10, 1.333, 1.78, 1.40],
    [67.0, 18.9, 0.25, 0.06, 3.533, 12.48, 0.88],
    [66.6, 31.1, -0.15, 0.02, 15.733, 247.53, -2.36]
  ],
  "totals": {"x": 400.5, "y": 92.2, "sum_(x-xbar)^2": 3.66, "sum_(y-ybar)^2": 438.6, "sum_products": 16.18, "xbar": 66.75, "ybar": 15.367},
  "notes": "En esta tabla la primera columna es el tiempo por vuelta y se llama «x», la segunda es la temperatura y se llama «y» (orden inverso al del enunciado). La suma de los (x − x̄)² de las filas impresas es 3.64; el total impreso es 3.66 (redondeo). Las sumas de las desviaciones no aparecen separadas en el texto extraído.",
  "source": null
}
```

> $r_{xy}=\dfrac{16.18}{[3.66\times438.6]^{1/2}}=0.40383$. Para 95 % (α = 0.05) y n = 6, la Tabla 4.5 da r_t = 0.811. Como r_xy < r_t, la aparente tendencia se debe probablemente al azar.

```json
{
  "type": "chart",
  "id": "chart-036",
  "page": 121,
  "pdf_page": 139,
  "title": "Figura 4.9: Valores gráficos de los pares temperatura-tiempo",
  "chart_type": "scatter",
  "axes": {"x": {"label": null}, "y": {"label": null}},
  "series": [{"name": "pares (temperatura, tiempo por vuelta) del Ejemplo 13", "values": null, "known_points": [[4.4, 65.3], [8.3, 66.5], [12.8, 67.3], [16.7, 67.8], [18.9, 67.0], [31.1, 66.6]]}],
  "description": "Gráfico de dispersión de los seis pares; los ejes no tienen rótulos en la capa de texto. Los puntos conocidos provienen de la tabla del ejemplo, no de la lectura de la figura.",
  "basis": "pie de figura + datos del ejemplo"
}
```

```json
{
  "type": "table",
  "id": "table-014",
  "page": 132,
  "pdf_page": 150,
  "title": "Tabla 4.5: Valores mínimos del coeficiente de correlación para un nivel de significancia α",
  "headers": ["n", "α = 0.2", "α = 0.1", "α = 0.05", "α = 0.02", "α = 0.01"],
  "rows": [
    [3, 0.951, 0.988, 0.997, 1.000, 1.000],
    [4, 0.800, 0.900, 0.950, 0.980, 0.990],
    [5, 0.687, 0.805, 0.878, 0.934, 0.959],
    [6, 0.608, 0.729, 0.811, 0.882, 0.917],
    [7, 0.551, 0.669, 0.754, 0.833, 0.875],
    [8, 0.507, 0.621, 0.707, 0.789, 0.834],
    [9, 0.472, 0.582, 0.666, 0.750, 0.798],
    [10, 0.443, 0.549, 0.632, 0.715, 0.765],
    [11, 0.419, 0.521, 0.602, 0.685, 0.735],
    [12, 0.398, 0.497, 0.576, 0.658, 0.708],
    [13, 0.380, 0.476, 0.553, 0.634, 0.684],
    [14, 0.365, 0.458, 0.532, 0.612, 0.661],
    [15, 0.351, 0.441, 0.514, 0.592, 0.641],
    [16, 0.338, 0.426, 0.497, 0.574, 0.623],
    [17, 0.327, 0.412, 0.482, 0.558, 0.606],
    [18, 0.317, 0.400, 0.468, 0.543, 0.590],
    [19, 0.308, 0.389, 0.456, 0.529, 0.575],
    [20, 0.299, 0.378, 0.444, 0.516, 0.561],
    [25, 0.265, 0.337, 0.396, 0.462, 0.505],
    [30, 0.241, 0.306, 0.361, 0.423, 0.463],
    [35, 0.222, 0.283, 0.334, 0.392, 0.430],
    [40, 0.207, 0.264, 0.312, 0.367, 0.403],
    [45, 0.195, 0.248, 0.294, 0.346, 0.380],
    [50, 0.184, 0.235, 0.279, 0.328, 0.361],
    [100, 0.129, 0.166, 0.197, 0.233, 0.257],
    [200, 0.091, 0.116, 0.138, 0.163, 0.180]
  ],
  "notes": "El número de la tabla está citado como [34] en el texto (fuente de los valores críticos).",
  "source": "ref. [34] del documento"
}
```

### 4.6 Ajuste de curvas

Se estudian métodos para ajustar datos experimentales a una curva dada de forma sistemática.

#### 4.6.1 Regresión lineal

Dados puntos (x₁, y₁)…(xₙ, yₙ) con abscisas distintas, se busca y = f(x) = Ax + B (4.6.1). Si los valores se conocen con varios dígitos significativos, puede usarse interpolación polinomial; de lo contrario no. Se definen los **residuos** $e_k=f(x_k)-y_k$ (4.6.2) y normas:

| Norma | Expresión |
|---|---|
| Máximo error (4.6.3) | $E_\infty(f)=\max_{1\le k\le n}\{|f(x_k)-y_k|\}$ |
| Error promedio (4.6.4) | $E_1(f)=\frac1n\sum|f(x_k)-y_k|$ |
| Error RMS (4.6.5) | $E_2(f)=\left(\frac1n\sum|f(x_k)-y_k|^2\right)^{1/2}$ |
| Error estándar de la estimación (4.6.6) | $E_{yx}=\sqrt{\dfrac{\sum y_k^2-B\sum y_k-A\sum x_ky_k}{n-2}}$ |

**Criterio de mejor ajuste:** la línea de mínimos cuadrados minimiza E₂(f), equivalentemente $n(E_2)^2=\sum(Ax_k+B-y_k)^2$.

> **Teorema 2 (recta por mínimos cuadrados).** Los coeficientes son solución de la **ecuación normal**:
>
> $$\begin{bmatrix}\sum x_k^2&\sum x_k\\\sum x_k&n\end{bmatrix}\begin{bmatrix}A\\B\end{bmatrix}=\begin{bmatrix}\sum x_ky_k\\\sum y_k\end{bmatrix}\qquad(4.6.7)$$
>
> *Prueba:* se minimiza $E(A,B)=\sum(Ax_k+B-y_k)^2=\sum d_k^2$ (4.6.8) con d_k la distancia vertical de cada punto a la recta (Fig. 4.10); igualando a cero ∂E/∂A (4.6.9) y ∂E/∂B (4.6.10) resultan $A\sum x_k^2+B\sum x_k-\sum x_ky_k=0$ (4.6.11) y $A\sum x_k+nB-\sum y_k=0$ (4.6.12), que en forma matricial dan (4.6.7).

```json
{
  "type": "chart",
  "id": "chart-037",
  "page": 123,
  "pdf_page": 141,
  "title": "Figura 4.10: Las distancias verticales entre los puntos {(xk, yk)} y la línea definida con mínimos cuadrados y = Ax + B",
  "chart_type": "scatter + recta",
  "axes": {"x": {"label": "x", "range": [0, 5], "ticks": [0, 1.25, 2.5, 3.75, 5]}, "y": {"label": "y", "range": [0, 4], "ticks": [0, 1, 2, 3, 4]}},
  "series": [{"name": "puntos y recta de mínimos cuadrados", "values": null}],
  "description": "Esquema que muestra las distancias verticales d_k entre cada punto y la recta. Valores no determinados.",
  "basis": "capa de texto (no verificado visualmente)"
}
```

> **Problema 1 (del documento).** Mejor recta para los puntos X = [−1, 0, 1, 2, 3, 4, 5, 6], Y = [10, 9, 7, 5, 4, 3, 0, −1]. El documento da este programa en Matlab (código del documento, no del convertidor; las comillas tipográficas del texto extraído se normalizaron a apóstrofos ASCII):

```matlab
X=[-1,0,1,2,3,4,5,6]';
Y=[10,9,7,5,4,3,0,-1]';
D=length(X)*sum(X'*X)-sum(X)*sum(X);
A=1/D*(length(X)*sum(X'*Y)-sum(X)*sum(Y));
B=1/D*(sum(X'*X)*sum(Y)-sum(X)*sum(X'*Y));
fprintf('A= %12.3f\n',A)
fprintf('B= %12.3f\n',B)
x=-2:0.01:10;
y=A*x+B;
plot(x,y)
hold on
plot(X,Y,'r*')
hold off
grid on
xlabel('x'),ylabel('y')
title('Ajuste de una recta usando mínimos cuadrados')
```

> Resultado: **y = −1.607 x + 8.643**. Error estándar (4.6.6): $E_{yx}=\sqrt{(281-8.643\times37+1.607\times25)/(8-2)}=0.48028$ (sumas del documento: Σy² = 281, Σy = 37, Σxy = 25). Representa la desviación de los datos y alrededor de los valores predichos por la recta (Fig. 4.11).

```json
{
  "type": "chart",
  "id": "chart-038",
  "page": 125,
  "pdf_page": 143,
  "title": "Figura 4.11: Línea y = Ax + B",
  "chart_type": "scatter + línea",
  "axes": {"x": {"label": "x", "range": [-2, 10]}, "y": {"label": "y", "range": [-8, 12], "ticks": [-8, -6, -4, -2, 0, 2, 4, 6, 8, 10, 12]}},
  "series": [
    {"name": "datos (marcadores 'r*')", "values": [[-1, 10], [0, 9], [1, 7], [2, 5], [3, 4], [4, 3], [5, 0], [6, -1]]},
    {"name": "recta ajustada", "formula": "y = -1.607 x + 8.643", "values": null}
  ],
  "description": "Título interno de la figura: «Ajuste de una recta usando mínimos cuadrados». Los puntos de datos provienen del Problema 1.",
  "basis": "capa de texto + datos del problema"
}
```

> **Ejemplo 14 (del documento).** Salida de un LVDT (V) para entradas L (cm):
>
> | L [cm] | 0.00 | 0.50 | 1.00 | 1.50 | 2.00 | 2.50 |
> |---|---|---|---|---|---|---|
> | v [V] | 0.05 | 0.52 | 1.03 | 1.50 | 2.00 | 2.56 |
>
> Con el programa del Problema 1: A = 0.9977, B = 0.0295 → **y = 0.9977 x + 0.0295** (y: tensión, x: desplazamiento). Error estándar (4.6.6): $E_{yx}=\sqrt{(14.137-0.0295\times7.66-0.9977\times13.94)/(6-2)}=0.0278$ (Fig. 4.12).

> **Observación de fidelidad.** El enunciado dice «cinco datos de entrada» pero la tabla tiene seis pares (y el cálculo usa n = 6).

```json
{
  "type": "chart",
  "id": "chart-039",
  "page": 126,
  "pdf_page": 144,
  "title": "Figura 4.12: Aproximación de un conjunto de datos a una línea recta",
  "chart_type": "scatter + línea",
  "axes": {"x": {"label": "L (cm)"}, "y": {"label": "v (V)"}},
  "series": [
    {"name": "datos LVDT", "values": [[0.0, 0.05], [0.5, 0.52], [1.0, 1.03], [1.5, 1.50], [2.0, 2.00], [2.5, 2.56]]},
    {"name": "recta ajustada", "formula": "y = 0.9977 x + 0.0295", "values": null}
  ],
  "description": "La capa de texto no contiene rótulos de ejes; las unidades se toman del Ejemplo 14.",
  "basis": "pie de figura + datos del ejemplo"
}
```

#### 4.6.2 Ajuste a una función potencia y = A·x^M

Con M constante conocida, solo se determina A.

> **Teorema 3.** $A=\dfrac{\sum_{k=1}^{n}x_k^My_k}{\sum_{k=1}^{n}x_k^{2M}}$ (4.6.13). *Prueba:* se minimiza $E(A)=\sum(Ax_k^M-y_k)^2$ (4.6.14); $E'(A)=2\sum(Ax_k^{2M}-x_k^My_k)=0$ (4.6.15-4.6.16) conduce a (4.6.13).

#### 4.6.3 Ajuste aproximado a una curva — linealización de datos para y = C·e^(Ax)

Para $y=Ce^{Ax}$ (4.6.17) se toma el logaritmo: $\ln y=Ax+\ln C$ (4.6.18). Con $Y=\ln y$, $X=x$ y $B=\ln C$ (4.6.19): $Y=AX+B$ (4.6.20). Los puntos (xₖ, yₖ) pasan a (Xₖ, Yₖ) = (xₖ, ln yₖ) (**linealización de datos**) y se ajusta la recta con las ecuaciones normales (4.6.21), análogas a (4.6.7) con X e Y; luego $C=e^B$ (4.6.22).

> **Ejemplo 15 (del documento).** Puntos (0, 1.5), (1, 2.5), (2, 3.5), (3, 5), (4, 7.5). Transformados: (0, 0.40547), (1, 0.91629), (2, 1.25276), (3, 1.60944), (4, 2.01490) (4.6.23). Recta: **Y = 0.391202 X + 0.457367** (4.6.24); C = e^0.457367 = «1. 6» (el valor impreso con espacio; ≈ 1.58). Ajuste exponencial: **y = 1.6 e^(0.391202 x)** (4.6.25).

```json
{
  "type": "chart",
  "id": "chart-040",
  "page": 129,
  "pdf_page": 147,
  "title": "Figura 4.13: Puntos de datos transformados {(Xk, Yk)}",
  "chart_type": "scatter",
  "axes": {"x": {"label": "x", "range": [0, 5], "ticks": [0, 1.25, 2.5, 3.75, 5]}, "y": {"label": "y", "range": [0, 3], "ticks": [0, 0.5, 1, 1.5, 2, 2.5, 3]}},
  "series": [{"name": "(Xk, Yk) = (xk, ln yk)", "values": [[0, 0.40547], [1, 0.91629], [2, 1.25276], [3, 1.60944], [4, 2.01490]]}],
  "description": "Datos linealizados del Ejemplo 15 (valores tomados del texto).",
  "basis": "texto del documento"
}
```

```json
{
  "type": "chart",
  "id": "chart-041",
  "page": 130,
  "pdf_page": 148,
  "title": "Figura 4.14: Ajuste exponencial a y = 1.6·e^(0.391202x) obtenido por el método de linealización de los datos",
  "chart_type": "scatter + curva",
  "axes": {"x": {"label": "x", "range": [0, 5], "ticks": [0, 1.25, 2.5, 3.75, 5]}, "y": {"label": "y", "range": [0, 10], "ticks": [0, 2.5, 5, 7.5, 10]}},
  "series": [
    {"name": "datos originales", "values": [[0, 1.5], [1, 2.5], [2, 3.5], [3, 5], [4, 7.5]]},
    {"name": "ajuste exponencial", "formula": "y = 1.6 exp(0.391202 x)", "values": null}
  ],
  "description": "Curva exponencial ajustada a los puntos del Ejemplo 15.",
  "basis": "pie de figura + datos del ejemplo"
}
```

#### 4.6.4 Ajuste polinomial

Con las funciones $f_j(x)=x^{j-1}$ y j = 1…m+1 se obtiene un polinomio de grado m: $f(x)=c_1+c_2x+\dots+c_{m+1}x^m$ (4.6.26).

> **Teorema 4 (parábola por mínimos cuadrados).** Para y = Ax² + Bx + C (4.6.27), los coeficientes resuelven
>
> $$\begin{aligned}\Big(\sum x_k^4\Big)A+\Big(\sum x_k^3\Big)B+\Big(\sum x_k^2\Big)C&=\sum y_kx_k^2\\\Big(\sum x_k^3\Big)A+\Big(\sum x_k^2\Big)B+\Big(\sum x_k\Big)C&=\sum y_kx_k\\\Big(\sum x_k^2\Big)A+\Big(\sum x_k\Big)B+nC&=\sum y_k\end{aligned}\qquad(4.6.28)$$
>
> *Prueba:* se minimiza $E(A,B,C)=\sum(Ax_k^2+Bx_k+C-y_k)^2$ (4.6.29); las derivadas parciales (4.6.30) iguales a cero llevan a la forma matricial (4.6.31) (el texto dice «la misma expresión dada por la ecuación (4.6.30)», pero corresponde a (4.6.28)).

```json
{
  "type": "table",
  "id": "table-015",
  "page": 132,
  "pdf_page": 150,
  "title": "Tabla 4.6: Obtención de los coeficientes para una parábola de mínimos cuadrados",
  "headers": ["xk", "yk", "xk^2", "xk^3", "xk^4", "xk·yk", "xk^2·yk"],
  "rows": [
    [-3, 3, 9, -27, 81, -9, 27],
    [0, 1, 0, 0, 0, 0, 0],
    [2, 1, 4, 8, 16, 2, 4],
    [4, 3, 16, 64, 256, 12, 48]
  ],
  "totals": {"sum_xk": 3, "sum_yk": 8, "sum_xk^2": 29, "sum_xk^3": 45, "sum_xk^4": 353, "sum_xk·yk": 5, "sum_xk^2·yk": 79},
  "notes": "Los totales figuran en el original como Σ = 3, 8, 29, 45, 353, 5, 79.",
  "source": null
}
```

> **Ejemplo 16 (del documento).** Parábola de mínimos cuadrados para (−3, 3), (0, 1), (2, 1), (4, 3). Sistema (con las sumas de la Tabla 4.6):
>
> $$\begin{bmatrix}353&45&29\\45&29&3\\29&3&4\end{bmatrix}\begin{bmatrix}A\\B\\C\end{bmatrix}=\begin{bmatrix}79\\5\\8\end{bmatrix}$$
>
> Solución: A = 585/3278, B = −631/3278, C = 1394/1639 → **y = 0.17846 x² − 0.1925 x + 0.85052** (Fig. 4.15).

```json
{
  "type": "chart",
  "id": "chart-042",
  "page": 131,
  "pdf_page": 149,
  "title": "Figura 4.15: Ajuste a una parábola usando mínimos cuadrados",
  "chart_type": "scatter + curva",
  "axes": {"x": {"label": "x", "range": [-2.5, 3.75], "ticks": [-2.5, -1.25, 0, 1.25, 2.5, 3.75]}, "y": {"label": "y", "range": [0, 3], "ticks": [0, 0.5, 1, 1.5, 2, 2.5, 3]}},
  "series": [
    {"name": "datos", "values": [[-3, 3], [0, 1], [2, 1], [4, 3]]},
    {"name": "parábola ajustada", "formula": "y = 0.17846 x^2 - 0.1925 x + 0.85052", "values": null}
  ],
  "description": "Los puntos (−3, 3) y (4, 3) quedan fuera del rango de ejes mostrado según las marcas de la capa de texto (−2.5 a 3.75); el rango real de la figura no se pudo verificar.",
  "basis": "capa de texto + datos del ejemplo"
}
```

#### 4.6.5 Software para análisis estadístico de datos experimentales

El análisis estadístico y la presentación de datos son una característica necesaria de muchos proyectos de ingeniería y administración. La mayoría de las hojas de cálculo incluyen funciones estadísticas y algunos programas tienen altas capacidades (v. gr., Matlab, SWP, Stella, Excel — marcas registradas citadas en el texto —, y Simscript). Los mejores incluyen no solo media y dispersión, ordenamiento e histogramas, sino también coeficientes de regresión lineal y no lineal, de correlación y tablas de distribuciones (t, χ², etc.).

---

## Ejemplo práctico (Capítulo 4)

> **Síntesis propia basada en el documento. No constituye una reproducción literal.** Reimplementa en Python los métodos del capítulo (recta por mínimos cuadrados con error estándar, ajuste exponencial por linealización, parábola, rechazo de Thompson, intervalo t). Dependencias: Python 3 y `numpy`. **Se ejecutó con los datos de los Problemas/Ejemplos 1, 10, 12, 15 y 16** y reprodujo A = −1.607, B = 8.643; A = 0.3912 con C ≈ 1.58; la parábola (0.17846, −0.1925, 0.85052); el rechazo de 12.16; y x̄ = 1372.3 h con semiancho ≈ 119 h (el documento da ±120 con S redondeado a 114). No se probó con datos experimentales. Nota: sin redondeos, el criterio de Thompson también elimina 12.10 en el Ejemplo 12 (ver observación de fidelidad arriba).

```python
import numpy as np

def minimos_cuadrados_recta(x, y):
    """Ecuación normal (4.6.7): devuelve A, B de y = A x + B y el error estándar (4.6.6)."""
    x, y = np.asarray(x, float), np.asarray(y, float)
    n = len(x)
    M = np.array([[np.sum(x**2), np.sum(x)], [np.sum(x), n]])
    b = np.array([np.sum(x * y), np.sum(y)])
    A, B = np.linalg.solve(M, b)
    Eyx = np.sqrt((np.sum(y**2) - B * np.sum(y) - A * np.sum(x * y)) / (n - 2))
    return A, B, Eyx

def ajuste_exponencial(x, y):
    """Linealización de datos y = C e^(A x) (4.6.17-4.6.22)."""
    A, B, _ = minimos_cuadrados_recta(x, np.log(y))
    return A, np.exp(B)

def parabola_minimos_cuadrados(x, y, grado=2):
    """Sistema normal del ajuste polinomial (4.6.28 / 4.6.31)."""
    V = np.vander(np.asarray(x, float), grado + 1)       # columnas x^grado ... 1
    return np.linalg.solve(V.T @ V, V.T @ np.asarray(y, float))

def thompson_rechazo(datos, tau_por_n):
    """Thompson tau modificada (4.4.13-4.4.14): elimina un dato por iteración.
    tau_por_n: dict {n: tau} tomado de la Tabla 4.4."""
    d = list(map(float, datos))
    rechazados = []
    while len(d) in tau_por_n:
        m, S = np.mean(d), np.std(d, ddof=1)
        i = int(np.argmax(np.abs(np.array(d) - m)))
        if abs(d[i] - m) > tau_por_n[len(d)] * S:
            rechazados.append(d.pop(i))
        else:
            break
    return d, rechazados

def intervalo_media_t(datos, t_critico):
    """mu = x̄ ± t S/sqrt(n) (4.3.49); t_critico se toma de la Tabla 4.3."""
    d = np.asarray(datos, float)
    return d.mean(), t_critico * d.std(ddof=1) / np.sqrt(len(d))
```

---

## Observaciones de fidelidad acumuladas (Parte 03)

1. Ejemplo 5: S = 5.79 °C y S² = 33.49 °C² no coinciden con los datos de la Tabla 4.1 (S ≈ 5.66, S² ≈ 32.0); media, mediana y moda sí.
2. Ec. (4.3.12): límite superior de integración impreso como ∞ (debería ser x). Ejemplo 7 no evalúa F(15) ni F(20).
3. «Fig. 5.2.16» (t de Student) = Fig. 4.6. Ec. (4.4.9): «2» inicial extra en el numerador en la capa de texto. Teorema 1: S(x) denota varianza; en 4.3.8 aparece «a» en lugar de α.
4. Ejemplo 12: con valores sin redondear, 12.10 también sería rechazado en la segunda iteración.
5. Ejemplo 13: columnas «x» e «y» de la tabla de cálculo invertidas respecto al enunciado; Σ(x − x̄)² impreso 3.66 vs 3.64 por redondeo.
6. Ejemplo 14: «cinco datos» pero hay seis pares. Ejemplo 15: C se imprime «1. 6» (≈ 1.58).
7. Ec. (4.6.19): «X (x)» garbled en el texto extraído (se transcribe X = x); en 4.6.3, el texto lista los puntos como (x₁, y₁), …, (x₁, y₁) (error de impresión evidente); (4.6.31) se remite a «(4.6.30)» en lugar de (4.6.28).
8. Muchas figuras (4.1–4.8) se describen con vista rasterizada de baja resolución; las figuras 4.9–4.15 solo con pie de figura, capa de texto y datos de los ejemplos (campo `basis` en cada JSON).

**Fin de la Parte 03.** La **Parte 04** comienza en el Capítulo 5, *Incertidumbre Experimental* (p. impresa 133 / PDF 151) y continuará con el Capítulo 6, *Sensores de parámetro variable*.
