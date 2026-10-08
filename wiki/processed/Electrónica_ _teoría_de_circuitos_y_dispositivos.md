# Electrónica: Teoría de Circuitos y Dispositivos Electrónicos

**Autor(es):** Robert L. Boylestad, Louis Nashelsky
**Edición:** Décima Edición
**Editorial:** Pearson Educación / Prentice Hall
**Año:** 2009
**ISBN:** 978-607-442-292-4

---

## Resumen Técnico

Este documento constituye una obra de referencia fundamental en el ámbito de la electrónica, abarcando desde los principios de los semiconductores hasta el análisis de circuitos integrados analógicos-digitales. El texto se estructura en 17 capítulos que progresan desde los conceptos más básicos de los materiales semiconductores, diodos y sus aplicaciones, hasta el análisis de transistores de unión bipolar (BJT), transistores de efecto de campo (FET), amplificadores operacionales, amplificadores de potencia, y dispositivos especiales como tiristores y transistores de monounión.

El enfoque pedagógico de la obra se centra en el análisis de circuitos mediante modelos equivalentes, tanto en el dominio de la corriente directa (cd) como en el de la corriente alterna (ca). Se hace un énfasis particular en el uso de aproximaciones prácticas para simplificar el análisis, manteniendo un equilibrio entre precisión y complejidad matemática. El texto incluye una gran cantidad de ejemplos resueltos, problemas propuestos, y análisis por computadora utilizando herramientas como PSpice, Multisim y Mathcad.

Los conceptos clave incluyen: la ecuación de Shockley para el diodo, el análisis de rectificadores y filtros, la polarización y estabilización de transistores BJT y FET, el modelo de señal pequeña (modelo re, híbrido y π híbrido), la respuesta en frecuencia de amplificadores, y las aplicaciones de amplificadores operacionales en filtros activos, osciladores y circuitos de instrumentación.

---

## Prefacio

La décima edición de *Electrónica: Teoría de Circuitos y Dispositivos Electrónicos* incorpora cambios significativos en pedagogía y contenido. Se agregaron objetivos de aprendizaje al inicio de cada capítulo, listas de conclusiones y conceptos importantes, y una tabla de resumen para el análisis de cd de los BJT. Se utiliza el modelo $r_e$ en las primeras secciones de cada capítulo, relegando el modelo de parámetro híbrido a secciones posteriores. Se actualizaron las hojas de componentes, fotografías y datos de ejemplos, y se mantienen los paquetes de software Mathcad 14, Cadence OrCAD 15.7 y Multisim 10.

---

## Tabla de Contenido

1. Diodos semiconductores
2. Aplicaciones del diodo
3. Transistores de unión bipolar
4. Polarización de cd de los BJT
5. Análisis de ca de un BJT
6. Transistores de efecto de campo
7. Polarización de los FET
8. Amplificadores con FET
9. Respuesta en frecuencia de los BJT y los JFET
10. Amplificadores operacionales
11. Aplicaciones del amplificador operacional
12. Amplificadores de potencia
13. Circuitos integrados analógicos-digitales
14. Realimentación y circuitos osciladores
15. Fuentes de alimentación (reguladores de voltaje)
16. Otros dispositivos de dos terminales
17. Dispositivos pnpn y de otros tipos

**Apéndices:**
- A: Parámetros híbridos
- B: Factor de rizo y cálculos de voltaje
- C: Gráficas y tablas
- D: Soluciones a problemas impares seleccionados

---

## Capítulo 1: Diodos Semiconductores

### 1.1 Introducción

El capítulo aborda los materiales semiconductores (Ge, Si, GaAs), la teoría de electrones y huecos, los materiales tipo n y p, y la operación básica del diodo en las regiones de polarización directa e inversa, incluyendo diodos Zener y LED.

### 1.2 Materiales Semiconductores: Ge, Si y GaAs

Los semiconductores son materiales cuya conductividad se encuentra entre la de un conductor y un aislante. Los tres semiconductores más utilizados son:
- **Germanio (Ge)** : estructura cristalina, 32 electrones, 4 electrones de valencia.
- **Silicio (Si)** : estructura cristalina, 14 electrones, 4 electrones de valencia.
- **Arseniuro de Galio (GaAs)** : compuesto, el Ga tiene 3 electrones de valencia, el As tiene 5.

```json
{
  "type": "table",
  "id": "table-1-1",
  "page": 5,
  "title": "Portadores intrínsecos",
  "headers": ["Semiconductor", "Portadores intrínsecos (por centímetro cúbico)"],
  "rows": [
    ["GaAs", "1.7 × 10^6"],
    ["Si", "1.5 × 10^10"],
    ["Ge", "2.5 × 10^13"]
  ],
  "notes": "Comparación del número de portadores intrínsecos por centímetro cúbico."
}
```

```json
{
  "type": "table",
  "id": "table-1-2",
  "page": 5,
  "title": "Factor de movilidad relativa μn",
  "headers": ["Semiconductor", "μn (cm²/V·s)"],
  "rows": [
    ["Si", "1500"],
    ["Ge", "3900"],
    ["GaAs", "8500"]
  ],
  "notes": "Movilidad de los portadores libres en diferentes materiales semiconductores."
}
```

### 1.3 Enlace Covalente y Materiales Intrínsecos

En un cristal de silicio o germanio puros, los cuatro electrones de valencia de un átomo forman un arreglo de enlace con cuatro átomos adyacentes (enlace covalente). Un material intrínseco es un semiconductor cuidadosamente refinado para reducir impurezas a un nivel muy bajo.

### 1.4 Niveles de Energía

Los electrones en la banda de valencia deben absorber energía para saltar a la banda de conducción. La brecha de energía ($E_g$) es diferente para cada material:
- Ge: $E_g \approx 0.67 \text{ eV}$
- Si: $E_g \approx 1.1 \text{ eV}$
- GaAs: $E_g \approx 1.43 \text{ eV}$

### 1.5 Materiales Extrínsecos: Tipo n y Tipo p

**Material tipo n:** Se crea introduciendo impurezas pentavalentes (antimonio, arsénico, fósforo). El quinto electrón está débilmente ligado y es libre para moverse. El electrón es el portador mayoritario.

**Material tipo p:** Se forma dopando con átomos trivalentes (boro, galio, indio). El vacío resultante se llama hueco. El hueco es el portador mayoritario.

```json
{
  "type": "image",
  "id": "image-1-1",
  "page": 8,
  "title": "Enlace covalente del átomo de silicio",
  "caption": "FIG. 1.4 Enlace covalente del átomo de silicio.",
  "description": "Diagrama que muestra los cuatro electrones de valencia de cada átomo de silicio compartidos con átomos adyacentes.",
  "source": "Boylestad, R. L. & Nashelsky, L. (2009). Electrónica: Teoría de Circuitos y Dispositivos Electrónicos (10ª ed.). Pearson."
}
```

```json
{
  "type": "image",
  "id": "image-1-2",
  "page": 9,
  "title": "Impureza de antimonio en un material tipo n",
  "caption": "FIG. 1.7 Impureza de antimonio en un material tipo n.",
  "description": "Diagrama que muestra un átomo de antimonio (pentavalente) en una base de silicio, con un quinto electrón libre.",
  "source": "Boylestad, R. L. & Nashelsky, L. (2009). Electrónica: Teoría de Circuitos y Dispositivos Electrónicos (10ª ed.). Pearson."
}
```

```json
{
  "type": "image",
  "id": "image-1-3",
  "page": 10,
  "title": "Impureza de boro en un material tipo p",
  "caption": "FIG. 1.9 Impureza de boro en un material tipo p.",
  "description": "Diagrama que muestra un átomo de boro (trivalente) en una base de silicio, con un hueco resultante.",
  "source": "Boylestad, R. L. & Nashelsky, L. (2009). Electrónica: Teoría de Circuitos y Dispositivos Electrónicos (10ª ed.). Pearson."
}
```

### 1.6 Diodo Semiconductor

El diodo se crea uniendo un material tipo n con uno tipo p. En condiciones sin polarización, la corriente neta es cero. En polarización directa ($V_D > 0$), la corriente se incrementa exponencialmente. En polarización inversa ($V_D < 0$), solo fluye la corriente de saturación inversa ($I_s$).

**Ecuación de Shockley:**
$$I_D = I_s(e^{V_D/nV_T} - 1)$$

**Voltaje térmico:**
$$V_T = \frac{kT}{q}$$

Donde:
- $k = 1.38 \times 10^{-23} \text{ J/K}$
- $T = 273 + T(^\circ C)$
- $q = 1.6 \times 10^{-19} \text{ C}$

**Valores típicos de $V_K$ (voltaje de rodilla):**
- Si: $0.7 \text{ V}$
- Ge: $0.3 \text{ V}$
- GaAs: $1.2 \text{ V}$

```json
{
  "type": "chart",
  "id": "chart-1-1",
  "page": 17,
  "title": "Comparación de diodos de Ge, Si y GaAs",
  "chart_type": "line",
  "axes": {
    "x": "VD (V)",
    "y": "ID (mA)"
  },
  "series": [
    {"name": "Ge", "data": "Curva característica para germanio"},
    {"name": "Si", "data": "Curva característica para silicio"},
    {"name": "GaAs", "data": "Curva característica para arseniuro de galio"}
  ],
  "description": "Gráfica que compara las curvas de polarización directa e inversa de diodos de Ge, Si y GaAs, mostrando los diferentes voltajes de rodilla y corrientes de saturación inversa.",
  "source": "Boylestad, R. L. & Nashelsky, L. (2009). Electrónica: Teoría de Circuitos y Dispositivos Electrónicos (10ª ed.). Pearson."
}
```

### 1.7 Lo Ideal vs. Lo Práctico

El diodo ideal se comporta como un interruptor mecánico: cortocircuito en polarización directa, circuito abierto en polarización inversa.

### 1.8 Niveles de Resistencia

- **Resistencia de cd o estática:** $R_D = \frac{V_D}{I_D}$
- **Resistencia de ca o dinámica:** $r_d = \frac{\Delta V_d}{\Delta I_d} = \frac{26 \text{ mV}}{I_D}$
- **Resistencia de ca promedio:** $r_{\text{prom}} = \frac{\Delta V_d}{\Delta I_d}$

```json
{
  "type": "table",
  "id": "table-1-5",
  "page": 27,
  "title": "Niveles de resistencia",
  "headers": ["Tipo", "Ecuación", "Características especiales", "Determinación gráfica"],
  "rows": [
    ["CD o estática", "R_D = V_D / I_D", "Definida como un punto en las características", "IDQ pt."],
    ["CA o dinámica", "r_d = ΔV_d / ΔI_d = 26 mV / I_D", "Definida por una línea tangente en el punto Q", "IDQ pt., ΔI_d"],
    ["CA promedio", "r_prom = ΔV_d / ΔI_d", "Definida por una línea recta entre los límites de operación", "ΔV_d, ΔI_d"]
  ],
  "notes": "Tabla que resume los diferentes tipos de resistencia de un diodo."
}
```

### 1.9 Circuitos Equivalentes del Diodo

- **Circuito equivalente lineal por segmentos:** Incluye una batería $V_K$, una resistencia $r_{\text{prom}}$ y un diodo ideal.
- **Circuito equivalente simplificado:** Solo batería $V_K$ y diodo ideal ($r_{\text{prom}} = 0$).
- **Circuito equivalente ideal:** Solo diodo ideal ($V_K = 0$, $r_{\text{prom}} = 0$).

### 1.10 Capacitancias de Difusión y Transición

- **Capacitancia de transición ($C_T$):** Predomina en polarización inversa, depende del voltaje aplicado.
- **Capacitancia de difusión ($C_D$):** Predomina en polarización directa, depende de la velocidad de inyección de carga.

### 1.11 Tiempo de Recuperación en Inversa ($t_{rr}$)

Es el tiempo que tarda el diodo en pasar del estado de conducción al de no conducción. $t_{rr} = t_s + t_r$.

### 1.12 Hojas de Especificaciones de Diodos

Incluyen: $V_F$, $I_F$, $I_R$, PIV, $P_{D_{\text{max}}}$, capacitancias, $t_{rr}$, y rangos de temperatura.

```json
{
  "type": "table",
  "id": "table-1-7",
  "page": 40,
  "title": "Características eléctricas de un diodo Zener de 10 V, 500 mW al 20%",
  "headers": ["Voltaje Zener nominal V_Z (V)", "Corriente de prueba I_ZT (mA)", "Impedancia dinámica máxima Z_ZT con I_ZT (Ω)", "Impedancia de rodilla máxima Z_ZK con I_ZK (Ω)", "Corriente en inversa máxima I_R con V_R (μA)", "Voltaje de prueba V_R (V)", "Corriente máxima de regulador I_ZM (mA)", "Coeficiente de temperatura típico (%/°C)"],
  "rows": [
    ["10", "12.5", "8.5", "700", "0.25", "10", "32", "+0.072"]
  ],
  "notes": "Datos de hoja de especificaciones para un diodo Zener de 10 V."
}
```

### 1.15 Diodos Zener

Operan en la región de ruptura Zener. El voltaje Zener ($V_Z$) es controlado por el nivel de dopado. La corriente de prueba $I_{ZT}$ es la corriente a la cual se especifica $Z_{ZT}$.

### 1.16 Diodos Emisores de Luz (LED)

Emiten luz cuando se polarizan en directa. Materiales: GaAs (infrarrojo), GaAsP (rojo, naranja, amarillo), GaN (azul, blanco). El voltaje de polarización directa varía según el color: rojo $\approx 1.8 \text{ V}$, azul $\approx 5 \text{ V}$, blanco $\approx 4.1 \text{ V}$.

```json
{
  "type": "table",
  "id": "table-1-8",
  "page": 42,
  "title": "Diodos emisores de luz",
  "headers": ["Color", "Construcción", "Voltaje en directa típico (V)"],
  "rows": [
    ["Ámbar", "AlInGaP", "2.1"],
    ["Azul", "GaN", "5.0"],
    ["Verde", "GaP", "2.2"],
    ["Naranja", "GaAsP", "2.0"],
    ["Rojo", "GaAsP", "1.8"],
    ["Blanco", "GaN", "4.1"],
    ["Amarillo", "AlInGaP", "2.1"]
  ],
  "notes": "Características típicas de diferentes colores de LED."
}
```

---

## Capítulo 2: Aplicaciones del Diodo

### 2.1 Introducción

Se analizan configuraciones de diodos en serie, paralelo y serie-paralelo, compuertas AND/OR, rectificación de media onda y onda completa, recortadores, sujetadores, diodos Zener y multiplicadores de voltaje.

### 2.2 Análisis por Medio de la Recta de Carga

La recta de carga se define por la ecuación de la red: $E = V_D + I_D R$. La intersección con la curva del diodo define el punto de operación (punto Q).

**Ejemplo 2.1:**
Para $E = 10 \text{ V}$, $R = 0.5 \text{ k}\Omega$, diodo de Si:
- $V_{D_0} \cong 0.78 \text{ V}$
- $I_{D_0} \cong 18.5 \text{ mA}$

**Ejemplo 2.2:**
Usando el modelo aproximado ($V_K = 0.7 \text{ V}$):
- $V_{D_0} = 0.7 \text{ V}$
- $I_{D_0} = 18.5 \text{ mA}$

### 2.3 Configuraciones de Diodos en Serie

**Ejemplo 2.4:** $E = 8 \text{ V}$, $R = 2.2 \text{ k}\Omega$, diodo de Si.
- $V_D = 0.7 \text{ V}$
- $V_R = 7.3 \text{ V}$
- $I_D = 3.32 \text{ mA}$

**Ejemplo 2.5:** Diodo invertido.
- $V_D = 8 \text{ V}$
- $I_D = 0 \text{ A}$
- $V_R = 0 \text{ V}$

### 2.4 Configuraciones en Paralelo y en Serie-Paralelo

**Ejemplo 2.10:**
- $V_o = 0.7 \text{ V}$
- $I_1 = 28.18 \text{ mA}$
- $I_{D_1} = I_{D_2} = 14.09 \text{ mA}$

### 2.5 Compuertas AND/OR

**Compuerta OR:** Salida alta si cualquier entrada es alta.
**Compuerta AND:** Salida alta solo si todas las entradas son altas.

### 2.6 Entradas Senoidales; Rectificación de Media Onda

$$V_{cd} = 0.318 V_m \quad \text{(media onda)}$$

**Ejemplo 2.16:**
- $V_m = 20 \text{ V}$, diodo ideal: $V_{cd} = -6.36 \text{ V}$
- Diodo de Si: $V_{cd} \cong -6.14 \text{ V}$

### 2.7 Rectificación de Onda Completa

**Rectificador de puente:**
$$V_{cd} = 0.636 V_m$$

**PIV requerido:** $PIV \geq V_m$

**Transformador con derivación central:**
$$V_{cd} = 0.636 V_m$$
$$PIV \cong 2V_m$$

### 2.8 Recortadores

Redes que recortan una parte de la señal de entrada sin distorsionar la parte restante.

### 2.9 Sujetadores

Redes que desplazan una forma de onda a un nivel de cd diferente sin cambiar su apariencia.

**Ejemplo 2.22:**
- $V_C = 25 \text{ V}$
- $v_o = 35 \text{ V}$ (durante $t_2 \rightarrow t_3$)

### 2.10 Diodos Zener

**Ejemplo 2.26:**
Para $R_L = 1.2 \text{ k}\Omega$: diodo apagado.
Para $R_L = 3 \text{ k}\Omega$: diodo encendido, $V_L = 10 \text{ V}$, $I_Z = 2.67 \text{ mA}$, $P_Z = 26.7 \text{ mW}$.

**Ejemplo 2.27:**
- $R_{L_{\text{min}}} = 250 \Omega$
- $I_{R} = 40 \text{ mA}$
- $I_{L_{\text{min}}} = 8 \text{ mA}$
- $R_{L_{\text{max}}} = 1.25 \text{ k}\Omega$

### 2.11 Circuitos Multiplicadores de Voltaje

- **Duplicador de media onda:** $V_{C_2} = 2V_m$
- **Triplicador:** $3V_m$
- **Cuadruplicador:** $4V_m$

---

## Capítulo 3: Transistores de Unión Bipolar

### 3.1 Introducción

El transistor BJT es un dispositivo de tres capas (npn o pnp) con tres terminales: emisor (E), base (B) y colector (C).

### 3.2 Construcción de un Transistor

- Dos capas tipo n y una tipo p (npn) o dos tipo p y una tipo n (pnp).
- La base es muy delgada y ligeramente dopada.
- El emisor está muy dopado.
- El colector está moderadamente dopado.

### 3.3 Operación del Transistor

- La unión base-emisor se polariza en directa.
- La unión base-colector se polariza en inversa.
- $I_E = I_C + I_B$

### 3.4 Configuración en Base Común

- **Alfa ($\alpha$):** $\alpha_{cd} = \frac{I_C}{I_E}$
- **Corriente de saturación inversa:** $I_{CBO}$
- **Región activa:** Unión base-emisor en directa, colector-base en inversa.
- **Región de corte:** Ambas uniones en inversa.
- **Región de saturación:** Ambas uniones en directa.

### 3.6 Configuración en Emisor Común

- **Beta ($\beta$):** $\beta_{cd} = \frac{I_C}{I_B}$
- **Relaciones:** $I_C = \beta I_B$, $I_E = (\beta + 1)I_B$
- **Relación entre $\alpha$ y $\beta$:** $\alpha = \frac{\beta}{\beta + 1}$, $\beta = \frac{\alpha}{1 - \alpha}$
- **Corriente de fuga:** $I_{CEO} = (\beta + 1)I_{CBO} \cong \beta I_{CBO}$

### 3.8 Límites de Operación

$$P_{C_{\text{max}}} = V_{CE} I_C$$

### 3.9 Hojas de Especificaciones del Transistor

Incluyen: $V_{CEO}$, $I_{C_{\text{max}}}$, $P_{C_{\text{max}}}$, $V_{CE_{\text{sat}}}$, $h_{FE}$, $I_{CBO}$, y curvas de reducción.

---

## Capítulo 4: Polarización de cd de los BJT

### 4.1 Introducción

El análisis o diseño de un amplificador transistorizado requiere conocer la respuesta del sistema tanto de cd como de ca. El teorema de superposición permite separar ambos análisis.

### 4.2 Punto de Operación

El punto de operación (punto Q) define el nivel de corriente y voltaje de cd en las características del transistor. Para amplificación lineal, el punto Q debe ubicarse en la región activa, lejos de la saturación y el corte.

**Ecuaciones básicas:**
$$V_{BE} = 0.7 \text{ V}$$
$$I_E = (\beta + 1)I_B \cong I_C$$
$$I_C = \beta I_B$$

### 4.3 Configuración de Polarización Fija

$$I_B = \frac{V_{CC} - V_{BE}}{R_B}$$
$$I_C = \beta I_B$$
$$V_{CE} = V_{CC} - I_C R_C$$
$$I_{C_{\text{sat}}} = \frac{V_{CC}}{R_C}$$

### 4.4 Configuración de Polarización de Emisor

$$I_B = \frac{V_{CC} - V_{BE}}{R_B + (\beta + 1)R_E}$$
$$V_{CE} = V_{CC} - I_C(R_C + R_E)$$
$$I_{C_{\text{sat}}} = \frac{V_{CC}}{R_C + R_E}$$

### 4.5 Configuración de Polarización por Medio del Divisor de Voltaje

**Análisis exacto:**
$$R_{Th} = R_1 \| R_2$$
$$E_{Th} = \frac{R_2 V_{CC}}{R_1 + R_2}$$
$$I_B = \frac{E_{Th} - V_{BE}}{R_{Th} + (\beta + 1)R_E}$$

**Análisis aproximado (si $\beta R_E \geq 10 R_2$):**
$$V_B = \frac{R_2 V_{CC}}{R_1 + R_2}$$
$$V_E = V_B - V_{BE}$$
$$I_E = \frac{V_E}{R_E} \cong I_C$$

### 4.6 Configuración de Realimentación del Colector

$$I_B = \frac{V_{CC} - V_{BE}}{R_B + \beta(R_C + R_E)}$$
$$V_{CE} = V_{CC} - I_C(R_C + R_E)$$

### 4.11 Operaciones de Diseño

Se seleccionan los resistores para establecer un punto de operación específico. Se utilizan valores estándar comerciales.

### 4.12 Circuitos de Espejo de Corriente

$$I = I_X = \frac{V_{CC} - V_{BE}}{R_X}$$

### 4.15 Redes de Conmutación con Transistores

**Inversor:** Cuando $V_i = 5 \text{ V}$, el transistor se satura. Cuando $V_i = 0 \text{ V}$, el transistor se corta.

$$I_{C_{\text{sat}}} = \frac{V_{CC}}{R_C}$$
$$I_B > \frac{I_{C_{\text{sat}}}}{\beta_{cd}}$$

### 4.17 Estabilización de la Polarización

**Factores de estabilidad:**
$$S(I_{CO}) = \frac{\Delta I_C}{\Delta I_{CO}}$$
$$S(V_{BE}) = \frac{\Delta I_C}{\Delta V_{BE}}$$
$$S(\beta) = \frac{\Delta I_C}{\Delta \beta}$$

**Efecto total:**
$$\Delta I_C = S(I_{CO})\Delta I_{CO} + S(V_{BE})\Delta V_{BE} + S(\beta)\Delta \beta$$

---

## Capítulo 5: Análisis de ca de un BJT

### 5.1 Introducción

Se presentan los modelos de señal pequeña para el BJT: modelo $r_e$, modelo híbrido y modelo $\pi$ híbrido.

### 5.2 Amplificación en el Dominio de Ca

La potencia de ca de salida puede ser mayor que la potencia de ca de entrada debido a la potencia de cd aplicada.

### 5.4 Modelo $r_e$ del Transistor

$$r_e = \frac{26 \text{ mV}}{I_E}$$
$$Z_i = \beta r_e$$
$$Z_o = r_o$$

### 5.5 Configuración de Polarización Fija en Emisor Común

$$Z_i = R_B \| \beta r_e$$
$$Z_o = R_C \| r_o \cong R_C$$
$$A_v = \frac{V_o}{V_i} = -\frac{R_C \| r_o}{r_e} \cong -\frac{R_C}{r_e}$$

### 5.6 Polarización por Medio del Divisor de Voltaje

$$Z_i = R_1 \| R_2 \| \beta r_e$$
$$Z_o = R_C \| r_o \cong R_C$$
$$A_v = -\frac{R_C \| r_o}{r_e} \cong -\frac{R_C}{r_e}$$

### 5.7 Configuración de Polarización en Emisor Común (sin puentear)

$$Z_i = R_B \| \beta(r_e + R_E)$$
$$Z_o = R_C$$
$$A_v = -\frac{\beta R_C}{Z_b} \cong -\frac{R_C}{R_E}$$

### 5.8 Configuración en Emisor Seguidor

$$Z_i = R_B \| \beta(r_e + R_E)$$
$$Z_o = r_e$$
$$A_v = \frac{R_E}{R_E + r_e} \cong 1$$

### 5.9 Configuración en Base Común

$$Z_i = R_E \| r_e$$
$$Z_o = R_C$$
$$A_v = \frac{R_C}{r_e}$$

### 5.10 Configuración de Realimentación del Colector

$$Z_i = \frac{r_e}{1/\beta + R_C/R_F}$$
$$Z_o = R_C \| R_F$$
$$A_v = -\frac{R_C}{r_e}$$

### 5.12 Determinación de la Ganancia de Corriente

$$A_i = -A_v \frac{Z_i}{R_L}$$

### 5.13 Efecto de $R_L$ y $R_S$

$$A_{vL} = \frac{R_L}{R_L + R_o} A_{vNL}$$
$$A_{vs} = \frac{Z_i}{Z_i + R_S} A_{vL}$$

### 5.19 Modelo Equivalente Híbrido

**Parámetros híbridos:**
- $h_{ie} = \beta r_e$
- $h_{fe} = \beta$
- $h_{re} \cong 0$
- $h_{oe} = \frac{1}{r_o}$

### 5.22 Modelo $\pi$ Híbrido

$$g_m = \frac{1}{r_e}$$
$$r_\pi = \beta r_e$$
$$r_o = \frac{1}{h_{oe}}$$

---

## Capítulo 6: Transistores de Efecto de Campo

### 6.1 Introducción

El FET es un dispositivo controlado por voltaje. Tipos: JFET, MOSFET (empobrecimiento y enriquecimiento), MESFET.

### 6.2 Construcción y Características de los JFET

**Ecuación de Shockley:**
$$I_D = I_{DSS}\left(1 - \frac{V_{GS}}{V_P}\right)^2$$

**Relaciones importantes:**
- $I_G \cong 0 \text{ A}$
- $I_D = I_S$
- $V_{GS} = V_P \left(1 - \sqrt{\frac{I_D}{I_{DSS}}}\right)$
- $I_D = \frac{I_{DSS}}{4}$ si $V_{GS} = \frac{V_P}{2}$
- $I_D = \frac{I_{DSS}}{2}$ si $V_{GS} \cong 0.3V_P$

**Resistencia controlada por voltaje:**
$$r_d = \frac{r_o}{(1 - V_{GS}/V_P)^2}$$

### 6.7 MOSFET Tipo Empobrecimiento

$$I_D = I_{DSS}\left(1 - \frac{V_{GS}}{V_P}\right)^2$$

### 6.8 MOSFET Tipo Enriquecimiento

$$I_D = k(V_{GS} - V_T)^2$$
$$k = \frac{I_{D(\text{encendido})}}{(V_{GS(\text{encendido})} - V_T)^2}$$

---

## Capítulo 7: Polarización de los FET

### 7.2 Configuración de Polarización Fija

$$V_{GS} = -V_{GG}$$
$$V_{DS} = V_{DD} - I_D R_D$$

### 7.3 Configuración de Autopolarización

$$V_{GS} = -I_D R_S$$
$$V_{DS} = V_{DD} - I_D(R_S + R_D)$$

### 7.4 Polarización por Medio del Divisor de Voltaje

$$V_G = \frac{R_2 V_{DD}}{R_1 + R_2}$$
$$V_{GS} = V_G - I_D R_S$$
$$V_{DS} = V_{DD} - I_D(R_D + R_S)$$

### 7.5 Configuración en Compuerta Común

$$V_{GS} = V_{SS} - I_D R_S$$
$$V_{DS} = V_{DD} + V_{SS} - I_D(R_D + R_S)$$

### 7.14 Curva de Polarización Universal del JFET

$$m = \frac{|V_P|}{I_{DSS} R_S}$$
$$M = m \times \frac{V_G}{|V_P|}$$

---

## Capítulo 8: Amplificadores con FET

### 8.2 Modelo del JFET de Señal Pequeña

$$g_m = g_{m0}\left(1 - \frac{V_{GS}}{V_P}\right)$$
$$g_{m0} = \frac{2I_{DSS}}{|V_P|}$$
$$g_m = g_{m0}\sqrt{\frac{I_D}{I_{DSS}}}$$
$$r_d = \frac{1}{y_{os}}$$

### 8.3 Configuración de Polarización Fija

$$Z_i = R_G$$
$$Z_o = R_D \| r_d \cong R_D$$
$$A_v = -g_m(R_D \| r_d) \cong -g_m R_D$$

### 8.4 Configuración de Autopolarización (con $R_S$ puenteada)

$$Z_i = R_G$$
$$Z_o = R_D \| r_d \cong R_D$$
$$A_v = -g_m(R_D \| r_d) \cong -g_m R_D$$

### 8.5 Configuración del Divisor de Voltaje

$$Z_i = R_1 \| R_2$$
$$Z_o = R_D \| r_d \cong R_D$$
$$A_v = -g_m(R_D \| r_d) \cong -g_m R_D$$

### 8.6 Configuración en Compuerta Común

$$Z_i = R_S \| \left(\frac{r_d + R_D}{1 + g_m r_d}\right) \cong R_S \| \frac{1}{g_m}$$
$$Z_o = R_D \| r_d \cong R_D$$
$$A_v = \frac{g_m R_D + R_D/r_d}{1 + R_D/r_d} \cong g_m R_D$$

### 8.7 Configuración en Fuente-Seguidor

$$Z_i = R_G$$
$$Z_o = r_d \| R_S \| \frac{1}{g_m} \cong R_S \| \frac{1}{g_m}$$
$$A_v = \frac{g_m(r_d \| R_S)}{1 + g_m(r_d \| R_S)} \cong \frac{g_m R_S}{1 + g_m R_S}$$

### 8.10 Configuración por Realimentación de Drenaje del E-MOSFET

$$Z_i = \frac{R_F + r_d \| R_D}{1 + g_m(r_d \| R_D)} \cong \frac{R_F}{1 + g_m R_D}$$
$$Z_o = R_F \| r_d \| R_D \cong R_D$$
$$A_v = -g_m(R_F \| r_d \| R_D) \cong -g_m R_D$$

### 8.11 Configuración del Divisor de Voltaje del E-MOSFET

$$Z_i = R_1 \| R_2$$
$$Z_o = r_d \| R_D \cong R_D$$
$$A_v = -g_m(r_d \| R_D) \cong -g_m R_D$$

---

## Capítulo 9: Respuesta en Frecuencia de los BJT y los JFET

### 9.2 Logaritmos

$$\log_{10} ab = \log_{10} a + \log_{10} b$$
$$\log_{10} \frac{a}{b} = \log_{10} a - \log_{10} b$$
$$\log_{10} \frac{1}{b} = -\log_{10} b$$
$$\log_e a = 2.3 \log_{10} a$$

### 9.3 Decibeles

$$G_{dB} = 10 \log_{10} \frac{P_2}{P_1} = 20 \log_{10} \frac{V_2}{V_1}$$
$$G_{dBm} = 10 \log_{10} \frac{P_2}{1 \text{ mW}}$$

### 9.4 Consideraciones Generales sobre la Frecuencia

- **Frecuencias de corte:** $f_1$ (inferior) y $f_2$ (superior).
- **Ancho de banda:** $BW = f_2 - f_1$.

### 9.6 Análisis en Baja Frecuencia; Gráfica de Bode

$$f_1 = \frac{1}{2\pi RC}$$
$$A_v = \frac{1}{1 - j(f_1/f)}$$
$$A_{v(dB)} = -20 \log_{10} \frac{f_1}{f}$$

### 9.7 Respuesta en Baja Frecuencia; Amplificador con BJT

$$f_{Ls} = \frac{1}{2\pi(R_s + R_i)C_s}$$
$$f_{LC} = \frac{1}{2\pi(R_o + R_L)C_C}$$
$$f_{LE} = \frac{1}{2\pi R_e C_E}$$
$$R_e = R_E \| \left(\frac{R'_s}{\beta} + r_e\right)$$

### 9.9 Capacitancia de Efecto Miller

$$C_{Mi} = (1 - A_v)C_f$$
$$C_{Mo} = \left(1 - \frac{1}{A_v}\right)C_f$$

### 9.10 Respuesta en Alta Frecuencia; Amplificador con BJT

$$f_{Hi} = \frac{1}{2\pi R_{Thi} C_i}$$
$$C_i = C_{Wi} + C_{be} + (1 - A_v)C_{bc}$$
$$R_{Thi} = R_s \| R_1 \| R_2 \| R_i$$
$$f_{Ho} = \frac{1}{2\pi R_{Tho} C_o}$$
$$C_o = C_{Wo} + C_{ce} + C_{Mo}$$
$$R_{Tho} = R_C \| R_L \| r_o$$
$$f_\beta = \frac{1}{2\pi \beta_{\text{med}} r_e (C_{be} + C_{bc})}$$
$$f_T = \beta_{\text{med}} f_\beta$$

### 9.11 Respuesta en Alta Frecuencia; Amplificador con FET

$$f_{Hi} = \frac{1}{2\pi R_{Thi} C_i}$$
$$C_i = C_{Wi} + C_{gs} + C_{Mi}$$
$$C_{Mi} = (1 - A_v)C_{gd}$$
$$R_{Thi} = R_{sig} \| R_G$$
$$f_{Ho} = \frac{1}{2\pi R_{Tho} C_o}$$
$$C_o = C_{Wo} + C_{ds} + C_{Mo}$$
$$C_{Mo} = \left(1 - \frac{1}{A_v}\right)C_{gd}$$
$$R_{Tho} = R_D \| R_L \| r_d$$

### 9.12 Efectos de las Frecuencias Asociadas a Múltiples Etapas

$$f'_1 = \frac{f_1}{\sqrt{2^{1/n} - 1}}$$
$$f'_2 = (\sqrt{2^{1/n} - 1}) f_2$$

### 9.13 Prueba con una Onda Cuadrada

$$BW \cong f_{Hi} = \frac{0.35}{t_r}$$
$$\% \text{ Inclinación} = \%P = \frac{V - V'}{V} \times 100\%$$
$$f_{Lo} = \frac{P}{\pi} f_s$$

---

## Capítulo 10: Amplificadores Operacionales

### 10.4 Fundamentos de Amplificadores Operacionales

**Amplificador inversor:**
$$\frac{V_o}{V_1} = -\frac{R_f}{R_1}$$

**Amplificador no inversor:**
$$\frac{V_o}{V_1} = 1 + \frac{R_f}{R_1}$$

**Seguidor unitario:**
$$V_o = V_1$$

**Amplificador sumador:**
$$V_o = -\left[\frac{R_f}{R_1}V_1 + \frac{R_f}{R_2}V_2 + \frac{R_f}{R_3}V_3\right]$$

**Integrador:**
$$v_o(t) = -\frac{1}{R_1 C_1} \int v_1 dt$$

### 10.6 Especificaciones de Amplificadores Operacionales; Parámetros de Compensación de cd

$$V_{o(\text{compensación})} = V_{IO} \frac{R_1 + R_f}{R_1}$$
$$V_{o(\text{compensación})} = I_{IO} R_f$$
$$|V_{o(\text{compensación})}| = |V_{o(\text{debida a } V_{IO})}| + |V_{o(\text{debida a } I_{IO})}|$$

### 10.7 Especificaciones de Amplificadores Operacionales; Parámetros de Frecuencia

$$SR = \frac{\Delta V_o}{\Delta t} \text{ V/μs}$$
$$f_1 = A_{VD} f_C$$
$$f_{\text{máx}} = \frac{SR}{2\pi K}$$

### 10.9 Operación Diferencial y en Modo Común

$$V_d = V_{i1} - V_{i2}$$
$$V_c = \frac{1}{2}(V_{i1} + V_{i2})$$
$$V_o = A_d V_d + A_c V_c$$
$$CMRR = \frac{A_d}{A_c}$$
$$CMRR(\log) = 20 \log_{10} \frac{A_d}{A_c}$$

---

## Capítulo 11: Aplicaciones del Amplificador Operacional

### 11.1 Multiplicador de Ganancia Constante

$$A = -\frac{R_f}{R_1} \quad \text{(inversor)}$$
$$A = 1 + \frac{R_f}{R_1} \quad \text{(no inversor)}$$

### 11.2 Suma de Voltajes

$$V_o = -\left[\frac{R_f}{R_1}V_1 + \frac{R_f}{R_2}V_2 + \frac{R_f}{R_3}V_3\right]$$

### 11.3 Seguidor de Voltaje o Amplificador de Acoplamiento

$$V_o = V_1$$

### 11.4 Fuentes Controladas

- **Fuente de voltaje controlada por voltaje:** $V_o = k V_1$
- **Fuente de corriente controlada por voltaje:** $I_o = \frac{V_1}{R_1} = k V_1$
- **Fuente de voltaje controlada por corriente:** $V_o = -I_1 R_L = k I_1$
- **Fuente de corriente controlada por corriente:** $I_o = \left(1 + \frac{R_1}{R_2}\right) I_1 = k I_1$

### 11.5 Circuitos de Instrumentación

**Amplificador de instrumentación:**
$$\frac{V_o}{V_1 - V_2} = 1 + \frac{2R}{R_P}$$

### 11.6 Filtros Activos

**Filtro pasobajas:**
$$f_{OH} = \frac{1}{2\pi R_1 C_1}$$
$$A_v = 1 + \frac{R_F}{R_G}$$

**Filtro pasoaltas:**
$$f_{OL} = \frac{1}{2\pi R_1 C_1}$$

**Filtro pasobanda:**
$$f_{OL} = \frac{1}{2\pi R_1 C_1}, \quad f_{OH} = \frac{1}{2\pi R_2 C_2}$$

---

## Capítulo 12: Amplificadores de Potencia

### 12.1 Introducción; Definiciones y Tipos de Amplificador

- **Clase A:** Conduce 360° del ciclo. Eficiencia máxima: 25% (alimentado en serie), 50% (acoplado por transformador).
- **Clase B:** Conduce 180° del ciclo. Eficiencia máxima: 78.5%.
- **Clase AB:** Conduce entre 180° y 360°. Eficiencia entre 25% y 78.5%.
- **Clase C:** Conduce menos de 180°. Usado en circuitos sintonizados.
- **Clase D:** Opera con señales digitales o de pulso. Eficiencia > 90%.

### 12.2 Amplificador Clase A Alimentado en Serie

$$P_{i(cd)} = V_{CC} I_{CQ}$$
$$P_{o(ca)} = \frac{V_{CE(rms)}^2}{R_C} = I_{C(rms)}^2 R_C = V_{CE(rms)} I_{C(rms)}$$
$$\% \eta = \frac{P_{o(ca)}}{P_{i(cd)}} \times 100\%$$
$$\eta_{\text{máx}} = 25\%$$

### 12.3 Amplificador Clase A Acoplado por Transformador

$$P_{o(ca)} = \frac{(V_{CEmáx} - V_{CEmín})(I_{Cmáx} - I_{Cmín})}{8}$$
$$P_{i(cd)} = V_{CC} I_{CQ}$$
$$P_Q = P_{i(cd)} - P_{o(ca)}$$
$$\eta_{\text{máx}} = 50\%$$

### 12.4 Operación de un Amplificador Clase B

$$P_{i(cd)} = V_{CC} I_{cd}$$
$$I_{cd} = \frac{2}{\pi} I_{(p)}$$
$$P_{o(ca)} = \frac{V_{L(p)}^2}{2R_L}$$
$$\% \eta = \frac{\pi}{4} \frac{V_{L(p)}}{V_{CC}} \times 100\%$$
$$\eta_{\text{máx}} = 78.54\%$$
$$P_{2Q} = P_{i(cd)} - P_{o(ca)}$$
$$P_{2Q_{\text{máx}}} = \frac{2V_{CC}^2}{\pi^2 R_L}$$

### 12.6 Distorsión de un Amplificador

$$\% D_n = \frac{|A_n|}{|A_1|} \times 100\%$$
$$\% THD = \sqrt{D_2^2 + D_3^2 + D_4^2 + \dots} \times 100\%$$
$$D_2 = \left| \frac{\frac{1}{2}(I_{Cmáx} + I_{Cmín}) - I_{CQ}}{I_{Cmáx} - I_{Cmín}} \right| \times 100\%$$

### 12.7 Disipación de Calor de un Transistor de Potencia

$$P_D = V_{CE} I_C$$
$$P_D(T_1) = P_D(T_0) - (T_1 - T_0) \times \text{factor de reducción}$$
$$T_J = P_D \theta_{JA} + T_A$$
$$\theta_{JA} = \theta_{JC} + \theta_{CS} + \theta_{SA}$$

---

## Capítulo 13: Circuitos Integrados Analógicos-Digitales

### 13.2 Operación de un Comparador

Compara un voltaje analógico con un voltaje de referencia y produce una salida digital.

### 13.3 Convertidores Digital a Analógico

**Red en escalera:**
$$V_o = \frac{D_0 \times 2^0 + D_1 \times 2^1 + D_2 \times 2^2 + \dots + D_n \times 2^n}{2^n} V_{ref}$$

**Resolución:**
$$\frac{V_{ref}}{2^n}$$

### 13.4 Operación de un Circuito Temporizador (555)

**Astable:**
$$T_{\text{alta}} \cong 0.7(R_A + R_B)C$$
$$T_{\text{baja}} \cong 0.7 R_B C$$
$$f = \frac{1}{T} \cong \frac{1.44}{(R_A + 2R_B)C}$$

**Monoestable:**
$$T_{\text{alta}} = 1.1 R_A C$$

### 13.5 Oscilador Controlado por Voltaje (VCO)

$$f_o = \frac{2}{R_1 C_1} \left(\frac{V^+ - V_C}{V^+}\right)$$

### 13.6 Malla de Enganche de Fase (PLL)

$$f_o = \frac{0.3}{R_1 C_1}$$
$$f_L = \pm \frac{8 f_o}{V}$$
$$f_C = \pm \frac{1}{2\pi} \sqrt{\frac{2\pi f_L}{3.6 \times 10^3 C_2}}$$

---

## Capítulo 14: Realimentación y Circuitos Osciladores

### 14.2 Tipos de Conexiones de Realimentación

**Ganancia con realimentación:**
$$A_f = \frac{A}{1 + \beta A}$$

**Impedancia de entrada (realimentación de voltaje en serie):**
$$Z_{if} = Z_i(1 + \beta A)$$

**Impedancia de salida (realimentación de voltaje en serie):**
$$Z_{of} = \frac{Z_o}{1 + \beta A}$$

**Impedancia de entrada (realimentación de voltaje en derivación):**
$$Z_{if} = \frac{Z_i}{1 + \beta A}$$

**Impedancia de salida (realimentación de corriente en serie):**
$$Z_{of} = Z_o(1 + \beta A)$$

### 14.5 Operación de un Oscilador

**Criterio de oscilación de Barkhausen:**
$$\beta A = 1$$

### 14.6 Oscilador de Corrimiento de Fase

$$f = \frac{1}{2\pi RC\sqrt{6}}$$
$$\beta = \frac{1}{29}$$
$$A > 29$$

### 14.7 Oscilador de Puente de Wien

$$\frac{R_3}{R_4} = \frac{R_1}{R_2} + \frac{C_2}{C_1}$$
$$f_o = \frac{1}{2\pi\sqrt{R_1 C_1 R_2 C_2}}$$
Para $R_1 = R_2 = R$ y $C_1 = C_2 = C$:
$$f_o = \frac{1}{2\pi RC}$$

### 14.8 Circuito Oscilador Sintonizado

**Colpitts:**
$$f_o = \frac{1}{2\pi\sqrt{L C_{eq}}}$$
$$C_{eq} = \frac{C_1 C_2}{C_1 + C_2}$$

**Hartley:**
$$f_o = \frac{1}{2\pi\sqrt{L_{eq} C}}$$
$$L_{eq} = L_1 + L_2 + 2M$$

### 14.10 Oscilador de Monounión

$$f_o \cong \frac{1}{R_T C_T \ln[1/(1 - \eta)]}$$

---

## Capítulo 15: Fuentes de Alimentación (Reguladores de Voltaje)

### 15.2 Consideraciones Generales sobre Filtros

**Rizo:**
$$r = \frac{V_{r(rms)}}{V_{cd}} \times 100\%$$

**Regulación de voltaje:**
$$\%V.R. = \frac{V_{NL} - V_{FL}}{V_{FL}} \times 100\%$$

**Factor de rizo (media onda):**
$$r = 121\%$$
**Factor de rizo (onda completa):**
$$r = 48\%$$

### 15.3 Filtro de Capacitor

$$V_{r(rms)} = \frac{I_{cd}}{4\sqrt{3} f C} = \frac{2.4 I_{cd}}{C}$$
$$V_{cd} = V_m - \frac{I_{cd}}{4 f C}$$
$$r = \frac{2.4 I_{cd}}{C V_{cd}} \times 100\% = \frac{2.4}{R_L C} \times 100\%$$
$$I_{\text{pico}} = \frac{T}{T_1} I_{cd}$$

### 15.4 Filtro RC

$$V'_{cd} = \frac{R_L}{R + R_L} V_{cd}$$
$$X_C = \frac{1.3}{C}$$
$$V'_{r(rms)} \cong \frac{X_C}{R} V_{r(rms)}$$

### 15.5 Regulación de Voltaje con Transistores Discretos

**Regulador en serie:**
$$V_o = V_Z - V_{BE}$$
**Regulador en serie mejorado:**
$$V_o = \frac{R_1 + R_2}{R_2}(V_Z + V_{BE2})$$
**Regulador en serie con amplificador operacional:**
$$V_o = \left(1 + \frac{R_1}{R_2}\right)V_Z$$
**Regulador en derivación:**
$$V_L = V_Z + V_{BE}$$
$$V_o = V_L = V_Z + V_{BE2} + V_{BE1}$$

### 15.6 Reguladores de Voltaje de Circuito Integrado

**Regulador ajustable (LM317):**
$$V_o = V_{ref}\left(1 + \frac{R_2}{R_1}\right) + I_{ajus} R_2$$

---

## Capítulo 16: Otros Dispositivos de Dos Terminales

### 16.2 Diodos de Barrera Schottky (Portadores Calientes)

- Voltaje de umbral bajo ($\approx 0.2 \text{ V}$).
- Tiempo de recuperación en inversa muy bajo.
- Mayor corriente de fuga en inversa.
- Menor PIV que los diodos de unión p-n.

### 16.3 Diodos Varactores (Varicap)

$$C_T = \frac{\varepsilon A}{W_d}$$
$$C_T = \frac{K}{(V_T + V_R)^n}$$
$$C_T(V_R) = \frac{C(0)}{(1 + |V_R/V_T|)^n}$$
$$TCC = \frac{\Delta C}{C_0(T_1 - T_0)} \times 100\% \%/\text{°C}$$

### 16.6 Fotodiodos

$$W = hf$$
$$\lambda = \frac{v}{f}$$
$$1 \text{ lm} = 1.496 \times 10^{-10} \text{ W}$$
$$1 \text{ fc} = 1 \text{ lm/pie}^2 = 1.609 \times 10^{-9} \text{ W/m}^2$$

### 16.7 Celdas Fotoconductoras

La resistencia terminal varía con la intensidad de la luz incidente.

### 16.8 Emisores Infrarrojos

Emiten un haz de flujo radiante cuando se polarizan en directa.

### 16.9 Pantallas de Cristal Líquido (LCD)

Requieren baja potencia, pero necesitan una fuente luminosa interna o externa.

### 16.10 Celdas Solares

$$\eta = \frac{P_o(\text{eléctrica})}{P_i(\text{energía luminosa})} \times 100\% = \frac{P_{\text{máx}}(\text{dispositivo})}{(\text{área en cm}^2)(100 \text{ mW/cm}^2)} \times 100\%$$

### 16.11 Termistores

Resistencia sensible a la temperatura. Coeficiente de temperatura positivo o negativo.

---

## Capítulo 17: Dispositivos pnpn y de Otros Tipos

### 17.2 Rectificador Controlado de Silicio (SCR)

Dispositivo pnpn de cuatro capas. Se enciende aplicando un pulso a la compuerta.

### 17.3 Operación Básica de un SCR

Se puede apagar por interrupción de la corriente en el ánodo o por conmutación forzada.

### 17.4 Características y Valores Nominales del SCR

- **Voltaje de conducción en directa ($V_F$):** Voltaje sobre el cual el SCR entra en conducción.
- **Corriente de mantenimiento ($I_H$):** Corriente por debajo de la cual el SCR se apaga.
- **Regiones de bloqueo en directa e inversa.**

### 17.6 Aplicaciones del SCR

- Interruptor estático.
- Control de fase.
- Regulador de carga de baterías.
- Controlador de temperatura.
- Sistema de iluminación de emergencia.

### 17.7 Interruptor Controlado de Silicio (SCS)

Dispositivo pnpn de cuatro capas con compuerta de ánodo y compuerta de cátodo.

### 17.8 Interruptor de Apagado por Compuerta (GTO)

Se puede encender o apagar aplicando el pulso apropiado a la compuerta de cátodo.

### 17.9 SCR Activado por Luz (LASCR)

Controlado por luz incidente en una capa semiconductora.

### 17.10 Diodo Shockley

Diodo pnpn de cuatro capas con dos terminales.

### 17.11 Diac

Combinación inversa en paralelo de dos terminales de capas semiconductoras que permite la activación en cualquier dirección.

$$V_{BR1} = V_{BR2} \pm 0.1 V_{BR2}$$

### 17.12 Triac

Diac con una terminal de compuerta para controlar las condiciones de encendido en ambas direcciones.

### 17.13 Transistor de Monounión (UJT)

Dispositivo de tres terminales con una unión p-n. Se utiliza en osciladores, circuitos de disparo, generadores de diente de sierra.

$$R_{BB} = (R_{B1} + R_{B2})|_{I_E=0}$$
$$V_{RB1} = \frac{R_{B1}}{R_{B1} + R_{B2}} V_{BB} = \eta V_{BB}$$
$$\eta = \frac{R_{B1}}{R_{B1} + R_{B2}}\bigg|_{I_E=0} = \frac{R_{B1}}{R_{BB}}$$
$$V_P = \eta V_{BB} + V_D$$

### 17.14 Fototransistores

$$I_C \cong h_{fe} I_\lambda$$

### 17.15 Aisladores Optoelectrónicos

Contienen un LED infrarrojo y un fotodetector.

### 17.16 Transistor de Monounión Programable (PUT)

$$V_P = \eta V_{BB} + V_D$$
$$\eta = \frac{R_{B1}}{R_{B1} + R_{B2}}$$
$$V_G = \frac{R_{B1}}{R_{B1} + R_{B2}} V_{BB} = \eta V_{BB}$$

---

## Apéndices

### Apéndice A: Parámetros Híbridos

$$h_{ie} = \frac{\partial v_{be}}{\partial i_b}\bigg|_{V_{CE}=\text{constante}}$$
$$h_{re} = \frac{\partial v_{be}}{\partial v_{ce}}\bigg|_{I_B=\text{constante}}$$
$$h_{fe} = \frac{\partial i_c}{\partial i_b}\bigg|_{V_{CE}=\text{constante}}$$
$$h_{oe} = \frac{\partial i_c}{\partial v_{ce}}\bigg|_{I_B=\text{constante}}$$

### Apéndice B: Factor de Rizo y Cálculos de Voltaje

$$V_{r(rms)} = \sqrt{V^2(rms) - V_{cd}^2}$$
$$V_{cd} = V_m - \frac{V_{r(p-p)}}{2}$$
$$V_{r(p-p)} = \frac{I_{cd} T_2}{C}$$
$$V_{r(rms)} = \frac{V_{r(p-p)}}{2\sqrt{3}}$$
$$\frac{V_m}{V_{cd}} = 1 + \frac{1}{\sqrt{3}r}$$
$$\frac{V_{r(rms)}}{V_m} = \frac{r}{1 + \sqrt{3}r}$$
$$\theta_1 = \text{sen}^{-1}\left(1 - \frac{V_{r(p-p)}}{V_m}\right)$$
$$\theta_2 = \pi - \tan^{-1}\frac{0.907}{(1 + \sqrt{3}r)r}$$
$$\frac{I_{\text{pico}}}{I_{cd}} = \frac{T}{T_1} = \frac{180°}{\theta}$$

### Apéndice C: Gráficas y Tablas

Incluye el alfabeto griego, valores estándar de resistores comerciales y valores de capacitores típicos.

### Apéndice D: Soluciones a Problemas Impares Seleccionados

Proporciona las respuestas a problemas seleccionados de todos los capítulos.

---

## Referencias

Boylestad, R. L. & Nashelsky, L. (2009). *Electrónica: Teoría de Circuitos y Dispositivos Electrónicos* (10ª ed.). México: Pearson Educación.

---

## Plantilla LaTeX

```latex
\documentclass[11pt,a4paper]{article}
\usepackage[utf8]{inputenc}
\usepackage[T1]{fontenc}
\usepackage[spanish]{babel}
\usepackage{amsmath, amssymb}
\usepackage{graphicx}
\usepackage{booktabs}
\usepackage{siunitx}
\usepackage{hyperref}

\title{Electrónica: Teoría de Circuitos y Dispositivos Electrónicos}
\author{Robert L. Boylestad \\ Louis Nashelsky}
\date{Décima Edición, 2009}

\begin{document}

\maketitle

\begin{abstract}
Resumen técnico del documento...
\end{abstract}

\tableofcontents

\section{Diodos Semiconductores}
\subsection{Materiales Semiconductores}
...

\section{Aplicaciones del Diodo}
...

\section{Transistores de Unión Bipolar}
...

\section{Polarización de cd de los BJT}
...

\section{Análisis de ca de un BJT}
...

\section{Transistores de Efecto de Campo}
...

\section{Polarización de los FET}
...

\section{Amplificadores con FET}
...

\section{Respuesta en Frecuencia}
...

\section{Amplificadores Operacionales}
...

\section{Aplicaciones del Amplificador Operacional}
...

\section{Amplificadores de Potencia}
...

\section{Circuitos Integrados Analógicos-Digitales}
...

\section{Realimentación y Circuitos Osciladores}
...

\section{Fuentes de Alimentación}
...

\section{Otros Dispositivos de Dos Terminales}
...

\section{Dispositivos pnpn y de Otros Tipos}
...

\appendix
\section{Parámetros Híbridos}
\section{Factor de Rizo y Cálculos de Voltaje}
\section{Gráficas y Tablas}
\section{Soluciones a Problemas Impares}

\end{document}
```

---

## Notas Finales

Este documento Markdown es una representación estructurada del contenido del PDF original. Se han conservado las secciones principales, tablas, gráficas, imágenes y fórmulas más relevantes. Dado el tamaño del documento original (más de 800 páginas), se ha priorizado la información técnica fundamental y se han utilizado JSON para representar elementos visuales y tablas. Para un análisis más detallado de secciones específicas, se recomienda consultar el documento original.

La estructura del Markdown sigue el orden natural del texto original, facilitando la navegación y el procesamiento posterior por parte de sistemas de inteligencia artificial. Los identificadores JSON son únicos y secuenciales, y se ha mantenido la fidelidad al contenido original en todo momento.
