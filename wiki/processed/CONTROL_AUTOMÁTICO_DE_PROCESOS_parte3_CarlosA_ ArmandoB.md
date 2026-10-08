# Capítulo 7: Diseño clásico de un sistema de control por retroalimentación

En el capítulo anterior se inició el estudio de la estabilidad y el diseño de los sistemas de control mediante dos técnicas: la prueba de Routh y la substitución directa. En este capítulo se continúa ese estudio y se presentan dos técnicas adicionales: lugar de raíz y respuesta en frecuencia. El significado y utilización de estas técnicas se aborda desde un punto de vista práctico; finalmente, el capítulo se termina con una presentación de la aplicación de la técnica de respuesta en frecuencia para la identificación del proceso.

Antes de abordar el estudio de las técnicas de lugar de raíz y respuesta en frecuencia, se deben definir algunos términos importantes para tal estudio; con este objeto se considera el diagrama de bloques general de un circuito cerrado que se muestra en la figura 7-1.

Como se vio en el capítulo 6, las funciones de transferencia de circuito cerrado son:

$$\frac{C(s)}{R(s)} = \frac{G_c(s)G_1(s)G_2(s)}{1 + G_c(s)G_1(s)G_2(s)H(s)} \quad (7-1)$$

Y:

$$\frac{C(s)}{L(s)} = \frac{G_3(s)G_2(s)}{1 + G_c(s)G_1(s)G_2(s)H(s)} \quad (7-2)$$

la ecuación característica es:

$$1 + H(s)G_c(s)G_1(s)G_2(s) = 0 \quad (7-3)$$

La **función de transferencia de circuito abierto (FTCA)** (OLTF por sus siglas en inglés) se define como el producto de todas las funciones de transferencia del circuito de control:

$$FTCA = H(s)G_c(s)G_1(s)G_2(s)$$

y, por tanto, la ecuación característica se puede escribir también como:

$$1 + FTCA = 0$$

Ahora se supone que las funciones de transferencia individuales se conocen y que la FTCA tiene la forma siguiente:

$$FTCA = \frac{K(\tau_Ds + 1)}{(\tau_1s + 1)(\tau_2s + 1)(\tau_3s + 1)}$$

donde $K = K_cK_1K_2K_T$.

Se define como **polos** a las raíces del denominador de la FTCA; en este caso los polos son $-1/\tau_1$, $-1/\tau_2$ y $-1/\tau_3$. Los **ceros** se definen como las raíces del numerador de la FTCA; en este caso $-1/\tau_D$.

Para generalizar dichas definiciones la FTCA se escribe como sigue:

$$FTCA = \frac{K'\prod_{i=1}^{m}(s - z_i)}{s^k\prod_{j=1}^{n}(s - p_j)} \quad (7-4)$$

donde:

$$K' = \frac{K\prod_{i=1}^{m}\tau_{D_i}}{\prod_{j=1}^{n}\tau_j} \quad (7-6)$$

De la ecuación (7-6), se observa inmediatamente que los polos son iguales a $-1/\tau_j$, para $j = 1$ a $n$; de manera semejante, los ceros se expresan con $-1/\tau_i$, para $i = 1$ a $m$ y a $s = 0$. Estas definiciones se utilizan frecuentemente en el estudio de las técnicas de lugar de raíz y respuesta en frecuencia.

## 7-1. TÉCNICA DE LUGAR DE RAÍZ

El lugar de raíz es una técnica gráfica que consiste en graficar las raíces de la ecuación característica, esto es, los eigenvalores, cuando una ganancia o cualquier otro de los parámetros del circuito de control cambia. En la gráfica que resulta se puede apreciar de un vistazo si alguna raíz de la ecuación característica cruza el eje imaginario del lado izquierdo del plano $s$ al lado derecho, lo cual sería indicación de alguna posibilidad de inestabilidad en el circuito de control.

A continuación se presentan varios ejemplos de la manera en que se puede dibujar el lugar de raíz; posteriormente, con base en estos ejemplos, se darán las reglas generales para la graficación. Con estos ejemplos se logra que se entiendan mejor los efectos de los diferentes parámetros del circuito de control sobre la estabilidad del mismo; dichos efectos ya se presentaron en el capítulo 6 y, por lo tanto, lo que sigue sirve también como repaso para el lector.

### Ejemplos

**Ejemplo 7-1.** En el diagrama de bloques de un determinado circuito de control como el que se muestra en la figura 7-2, se tiene la siguiente ecuación característica para el sistema:

$$1 + \frac{K_c}{(3s+1)(s+1)} = 0 \quad (7-7)$$

Y:

$$FTCA = \frac{K_c}{(3s+1)(s+1)}$$

Se notará que en esta FTCA existen dos polos, $-1/3$ y $-1$, y que no hay ceros. A partir de la ecuación (7-7) se obtiene el siguiente polinomio en $s$:

$$3s^2 + 4s + (1 + K_c) = 0$$

Puesto que este polinomio es de segundo orden, tiene dos raíces. Se utiliza la fórmula general para resolver ecuaciones cuadráticas, obtener las raíces, y se desarrolla la siguiente expresión:

$$r_{1,2} = \frac{-4 \pm \sqrt{16 - 12(1 + K_c)}}{6} = \frac{-2 \pm \sqrt{1 - 3K_c}}{3} \quad (7-9)$$

En la ecuación (7-9) se observa que las raíces de la ecuación característica dependen del valor de $K_c$, lo cual equivale a decir que la estabilidad del circuito de control depende del ajuste del controlador por retroalimentación. Naturalmente, en el capítulo 6 se vio que también éste era el caso. Los lugares de las raíces se determinan mediante la asignación de valores a $K_c$; en la figura 7-3 se muestra la gráfica de las raíces o lugar de raíz, de la cual, al examinarla, se pueden aprender varias cosas:

1. El punto más importante es que este circuito de control particular nunca se vuelve inestable, no importa qué tan grande se haga el valor de $K_c$. Conforme se incrementa el valor de $K_c$, la respuesta del circuito se hace más oscilatoria o subamortiguada, pero jamás inestable. La respuesta subamortiguada se reconoce porque las raíces de la ecuación característica se alejan del eje real conforme se incrementa $K_c$. El hecho de que un circuito de control con una ecuación pura de segundo orden (o primer orden) no se vuelva inestable, se demostró también en el capítulo 6, mediante los métodos de prueba de Routh y de substitución directa.
2. Cuando $K_c = 0$, los lugares de raíz se originan en los polos de la FTCA: $-1/3$ y $-1$.
3. La cantidad de lugares de raíz o ramas es igual al número de polos de la FTCA, $n = 2$.
4. Conforme se incrementa $K_c$, los lugares de raíz tienden a infinito.

**Ejemplo 7-2.** Si ahora se supone que la combinación de sensor-transmisor en el ejemplo anterior tiene una constante de tiempo de 0.5 unidades de tiempo, el diagrama de bloques es el que se muestra en la figura 7-4, y la nueva ecuación característica y función de transferencia de circuito abierto son:

**Ecuación característica:**
$$1 + \frac{K_c}{(3s+1)(s+1)(0.5s+1)} = 0$$
$$1.5s^3 + 6.5s^2 + 4.5s + (1 + K_c) = 0$$

En este caso la ecuación característica es un polinomio de tercer orden y, por lo tanto, el cálculo de las raíces no es directo, se debe utilizar el método de Newton que se estudió en el capítulo 2, o el programa de computadora del apéndice D; sin embargo, como se verá, existe un método más fácil para trazar el lugar de raíz sin necesidad de calcular ninguna raíz.

En la figura 7-5 se muestra el diagrama de lugar de raíz y, nuevamente, se pueden aprender varias cosas de la simple observación de éste.

1. El aspecto más importante es que este sistema de control se puede volver inestable. Con algunos valores de $K_c$, en este caso $K_c > 14$, los lugares de raíz cruzan el eje imaginario; para valores de $K_c$ mayores de 14, las raíces de la ecuación característica estarán en el lado derecho del plano $s$, lo que ocasiona que el sistema de control sea inestable. El valor de $K_c$ con que el lugar de raíz cruza el eje imaginario se conoce como ganancia última, $K_{c_u}$, lo que da lugar a un sistema condicionalmente estable, tal como se vio en el capítulo 6. La frecuencia última, $\omega_u$, se expresa por la ordenada en que la rama cruza el eje imaginario. Cualquier circuito cuya ecuación característica sea de tercer orden o superior se puede volver inestable; los sistemas puros de primer o segundo orden no se vuelven inestables, como se vio en el ejemplo 7-1. Cualquier sistema con tiempo muerto se puede volver inestable, como se verá en este capítulo.
2. Con $K_c = 0$, los lugares de raíz tienen su origen, nuevamente, en los polos de la FTCA: $-1/3$, $-1$, $-2$.
3. Nuevamente, la cantidad de lugares de raíz es igual al número de polos de la FTCA, $n = 3$.
4. Finalmente, conforme se incrementa $K_c$, nuevamente los lugares de raíz se aproximan a infinito.

**Ejemplo 7-3.** Ahora se supone que en el circuito de control original, ejemplo 7-1, se utiliza un controlador proporcional-derivativo. En la figura 7-6 se muestra el diagrama de bloques; la nueva ecuación característica y la función de transferencia de circuito abierto son de la forma siguiente:

**Ecuación característica:**
$$1 + \frac{K_c(1 + 0.2s)}{(3s+1)(s+1)} = 0$$
$$3s^2 + (4 + 0.2K_c)s + (1 + K_c) = 0$$

$$FTCA = \frac{K_c(1 + 0.2s)}{(3s+1)(s+1)}$$

con polos: $-1/3$, $-1$; $n = 2$; ceros: $-5$; $m = 1$.

Puesto que la ecuación característica es de segundo orden, sus raíces se determinan mediante la fórmula general para resolver ecuaciones cuadráticas:

$$r_{1,2} = \frac{-(4 + 0.2K_c) \pm \sqrt{(4 + 0.2K_c)^2 - 12(1 + K_c)}}{6}$$

Al darle valores a $K_c$ es posible obtener el lugar de raíz para este sistema; como se muestra en la figura 7-7.

Al igual que en los otros ejemplos, se pueden aprender varias cosas de este diagrama:

1. Este circuito de control nunca se hace inestable; aún más, conforme se incrementa $K_c$, los lugares de raíz se alejan del eje imaginario y el circuito de control se vuelve más estable. En efecto, con la acción derivativa se adiciona un término de "adelanto" al circuito de control. Mediante la adición de cualquier término de adelanto (avance) se "añade" estabilidad a los circuitos de control; en cambio, con la adición de un término de retardo se "remueve" la estabilidad de los sistemas de control, como se vio en el ejemplo 7-2.
2. Los lugares de raíz tienen su origen en los polos de la FTCA: $-1/3$ y $-1$, lo cual es similar en los ejemplos anteriores.
3. La cantidad de lugares de raíz es igual al número de polos de la FTCA, $n = 2$. Éste es también el caso en los ejemplos anteriores.
4. Conforme se incrementa $K_c$, uno de los lugares de raíz se aproxima al cero de la FTCA, $-5$, y los otros se aproximan a menos infinito.

### Reglas para graficar los diagramas de lugar de raíz

En los ejemplos anteriores se mostró el desarrollo de los diagramas de lugar de raíz. Mientras la ecuación característica sea de segundo orden, es bastante fácil desarrollar el diagrama, pero en sistemas de orden superior, la obtención de las raíces de la ecuación característica se vuelve bastante tediosa.

Se han desarrollado varias reglas para ayudar al ingeniero a trazar los diagramas de lugar de raíz; para utilizar tales reglas, la ecuación característica y la función de transferencia de circuito abierto se escriben en la siguiente forma:

**Ecuación característica:**
$$1 + \frac{K'\prod_{i=1}^{m}(s - z_i)}{s^k\prod_{j=1}^{n}(s - p_j)} = 0 \quad (7-10)$$

$$FTCA = \frac{K'\prod_{i=1}^{m}(s - z_i)}{s^k\prod_{j=1}^{n}(s - p_j)} \quad (7-11)$$

donde:
- $z_i = -\frac{1}{\tau_i}$ = ceros
- $p_j = -\frac{1}{\tau_j}$ = polos
- $K'$ = ganancia total del lazo; es el producto de todas las ganancias en el circuito.

Las reglas que se presentan aquí se desarrollaron con base en el hecho de que el lugar de raíz debe satisfacer lo que se conoce como condiciones de magnitud y ángulo. Con la finalidad de explicar en qué consisten dichas condiciones, se considera nuevamente la ecuación característica que expresa la ecuación (7-10); la cual también se puede escribir como sigue:

$$\frac{K'\prod_{i=1}^{m}(s - z_i)}{s^k\prod_{j=1}^{n}(s - p_j)} = -1$$

Puesto que la ecuación es de naturaleza compleja, se puede separar en dos partes: magnitud y ángulo de fase; si se realiza la multiplicación y la división en forma polar, como se presentó en la sección 2-3, se obtienen:

$$\frac{K'\prod_{i=1}^{m}|s - z_i|}{|s|^k\prod_{j=1}^{n}|s - p_j|} = 1 \quad (7-12)$$

Y:

$$\sum_{i=1}^{m}\angle(s - z_i) - k\angle s - \sum_{j=1}^{n}\angle(s - p_j) = -180° \pm 360°k \quad (7-13)$$

donde $k$ es un entero positivo con valores $k = 0, 1, 2, \ldots, n-m-1$.

La ecuación (7-12) se conoce como condición de magnitud y la ecuación (7-13) como condición de ángulo. Las raíces o eigenvalores de la ecuación característica deben satisfacer ambos criterios.

La condición de ángulo se utiliza para ubicar los lugares de raíz en el plano $s$; la de magnitud se usa entonces para calcular el valor de $K'$, con el que se le asigna a la raíz un punto específico en el diagrama de lugar de raíz.

Mediante un ejemplo simple se muestra ahora cómo se utilizan las condiciones de magnitud y de ángulo para localizar una raíz, para ello se considera la figura 7-8 en la cual se ilustra un sistema donde hay dos polos de la FTCA, los cuales se marcan con x, y un cero de la FTCA, el cual se marca como o. Se elige un valor de $s$, por ejemplo $s_1$, y se trata de determinar si es una raíz y, por tanto, es parte del lugar de raíz. El primer paso consiste en verificar la condición de ángulo, para esto se trazan segmentos de línea que unen al punto $s_1$ con cada polo y cada cero, como se ve en la figura 7-8; entonces se mide el ángulo que forma cada uno de estos segmentos con el eje real; si se satisface la condición de ángulo, el punto $s_1$ forma parte del lugar de raíz; si no se satisface la condición de ángulo, se debe elegir otro punto en el plano $s$ y probar -éste es un procedimiento de ensayo y error. Con esto se aumenta la importancia de la utilización de las reglas que se presentan. Una vez que se identifica un punto en el plano $s$ como parte del lugar de raíz, entonces se utiliza la condición de magnitud para calcular el valor de $K'$ que corresponde a la raíz. Dicho cálculo se muestra posteriormente en un ejemplo.

En el párrafo precedente se explicó brevemente la manera en que las condiciones de magnitud y ángulo sirven como base para dibujar el lugar de raíz. Las reglas que se desarrollaron a partir de tales condiciones se pueden utilizar para esbozar de manera cualitativa el lugar de raíz; es posible determinar ciertos puntos tales como la ganancia y la frecuencia últimas, así como la ganancia que se requiere para obtener una cierta razón de amortiguamiento. Se debe tener presente que los lugares de raíz siempre son simétricos respecto al eje real, lo cual es consecuencia del hecho de que las raíces de la ecuación característica son reales o complejas conjugadas. A continuación se dan las reglas correspondientes:

**Regla 1.** Sobre el eje real el lugar de raíz existe en el punto en que hay una cantidad impar de polos y ceros a la derecha del punto.

**Regla 2.** Para una ganancia total de lazo = 0, los lugares de raíz se originan siempre en los polos de la FTCA. Los polos repetidos dan origen a lugares de raíz repetidos, es decir, un polo de orden $q$ da origen a $q$ lugares o ramas.

**Regla 3.** La cantidad de lugares o ramas es igual al número de polos de la FTCA, $n$.

**Regla 4.** Conforme se incrementa la ganancia total del lazo, los lugares o ramas se aproximan a los ceros de la FTCA o a infinito. La cantidad de lugares que tienden a infinito la expresa $n-m$. Los ceros repetidos atraen lugares repetidos, esto es, un cero de orden $q$ atrae $q$ lugares o ramas.

**Regla 5.** Los lugares que tienden a infinito lo hacen sobre asíntotas. Todas las asíntotas deben pasar por el "centro de gravedad" de los polos y ceros de la FTCA. La ubicación del centro de gravedad (CG) se calcula como sigue:

$$CG = \frac{\sum_{j=1}^{n}p_j - \sum_{i=1}^{m}z_i}{n - m} \quad (7-14)$$

Estas asíntotas forman los siguientes ángulos con el eje real positivo:

$$\phi = \frac{180° + (360°)k}{n - m} \quad (7-15)$$

donde $k = 1, \ldots, n - m - 1$

**Regla 6.** Los puntos en que los lugares se juntan y separan sobre el eje real, o llegan desde la región compleja del plano $s$, se conocen como "puntos de ruptura", los cuales se determinan, frecuentemente, por ensayo y error, con base en la solución de la ecuación:

$$\sum_{j=1}^{n}\frac{1}{s - p_j} = \sum_{i=1}^{m}\frac{1}{s - z_i} \quad (7-16)$$

En los puntos de ruptura los lugares siempre se alejan o llegan al eje real con ángulos de $\pm 90°$.

Cuando un lugar se aleja de un polo conjugado complejo, $p_k$, el ángulo de alejamiento en relación al eje real se encuentra con base en:

$$\text{ángulo de alejamiento} = 180° + \sum_{i=1}^{m}\angle(p_k - z_i) - \sum_{j=1, j\neq k}^{n}\angle(p_k - p_j)$$

Cuando un lugar llega a un cero conjugado complejo, $z_k$, el ángulo de llegada respecto al eje real se encuentra a partir de:

$$\text{ángulo de llegada} = -180° + \sum_{i=1, i\neq k}^{m}\angle(z_k - z_i) - \sum_{j=1}^{n}\angle(z_k - p_j)$$

A continuación se presenta la utilización de estas reglas para la graficación de los diagramas de lugar de raíz.

**Ejemplo 7-4.** Se considera el circuito de control de temperatura del intercambiador de calor que se presentó en el capítulo 6. El diagrama de bloques de la figura 6-3 se dibuja nuevamente en la figura 7-9, con cada una de las funciones de transferencia.

**Ecuación característica:**
$$1 + \frac{0.8K_c}{(10s+1)(30s+1)(3s+1)} = 0$$

$$FTCA = \frac{0.8K_c}{(10s+1)(30s+1)(3s+1)}$$

Como se observa en la ecuación (7-11), la FTCA se puede escribir también como sigue:

$$FTCA = \frac{K'}{\left(s+\frac{1}{10}\right)\left(s+\frac{1}{30}\right)\left(s+\frac{1}{3}\right)}$$

con polos: $-1/10$, $-1/30$, $-1/3$; ceros: ninguno; $m = 0$;

$$K' = \frac{0.8K_c}{(10)(30)(3)} = 0.000888K_c$$

En la figura 7-10 se muestra la ubicación de los polos (x) en el plano $s$.

- De la regla 1 se tiene que la porción negativa del eje real entre los polos $-1/30$ y $-1/10$, y del polo $-1/3$ a $-\infty$ forma parte del lugar de raíz.
- Con base en la regla 2, se sabe que los lugares de raíz tienen su origen en los polos de la FTCA: $-1/10$, $-1/30$ y $-1/3$.
- Puesto que hay tres polos, $n = 3$, de la regla 3, se tiene que existen tres lugares o ramas.
- Puesto que no hay ceros, $m = 0$, la regla 4 indica que, conforme se incrementa $K_c$, todos los lugares tienden a infinito.
- Con la regla 5 se puede obtener el centro de gravedad a través del cual deben pasar las asíntotas, así como los ángulos que éstas forman con el eje real positivo. Puesto que hay tres ramas que tienden a infinito, también debe haber tres asíntotas, de la ecuación (7-14) se tiene:

$$CG = \frac{-\frac{1}{10} - \frac{1}{30} - \frac{1}{3}}{3} = -0.155$$

y de la ecuación (7-15) se tiene:

$$\phi = \frac{180° + 360°(0)}{3}, \frac{180° + 360°(1)}{3}, \frac{180° + 360°(2)}{3}$$
$$\phi = 60°, 180°, 300°$$

Los ángulos y las asíntotas se muestran en la figura 7-10. Una de las asíntotas coincide con el eje real, $\phi = 180°$; y se mueve del centro de gravedad hacia menos infinito; las otras dos asíntotas se alejan del eje real hacia la región compleja del plano $s$ y cruzan el eje imaginario, lo cual indica que existe la posibilidad de inestabilidad, ya que los lugares se acercan a infinito sobre estas asíntotas.

- La regla 6 se utiliza para calcular los puntos de ruptura; al aplicar la ecuación (7-16), se obtiene:

$$\frac{1}{s + \frac{1}{10}} + \frac{1}{s + \frac{1}{30}} + \frac{1}{s + \frac{1}{3}} = 0$$

de donde se tienen dos posibilidades: $-0.247$ y $-0.063$. El único punto de ruptura válido es $-0.063$, ya que está en la región del eje real donde los dos lugares se acercan el uno al otro.

Antes de dibujar el diagrama final del lugar de raíz es conveniente conocer el punto en que los lugares cruzan el eje imaginario, con el cual se tiene un punto más para dibujar los lugares de raíz, lo que aumenta la precisión del diagrama. Dicho punto es la frecuencia última, $\omega_u$, y se encuentra fácilmente mediante la aplicación del método de substitución directa que se estudió en el capítulo 6. Al aplicar este método al problema, se encuentra que $\omega_u = 0.22$. El método de substitución directa también se puede utilizar para encontrar la ganancia del controlador a la cual se produce este estado de estabilidad condicional; dicho valor es $K_c = 24.0$. En la figura 7-10 se muestra el diagrama completo del lugar de raíz.

Con este ejemplo se demostró que el trazado del lugar de raíz es bastante simple y que no es necesario encontrar ninguna raíz del sistema. Los lugares entre el punto de ruptura y la frecuencia de cruce se dibujaron a mano, lo cual, por lo regular, es suficiente para la mayor parte del trabajo de control de proceso. Al graficar los lugares de raíz, es conveniente utilizar un instrumento de dibujo que se conoce como curvígrafo, el cual es utilizado principalmente por los ingenieros electricistas.

El diagrama que se muestra en la figura 7-10 sirve como ayuda para ilustrar otro uso del lugar de raíz. Se puede suponer que se desea ajustar el controlador por retroalimentación de modo que la respuesta de circuito cerrado del sistema de control sea oscilatoria con una razón de amortiguamiento de 0.707, $\xi = 0.707$.

En el capítulo 4 se definió la razón de amortiguamiento como parámetro de un sistema de segundo orden. Al utilizar tal especificación de desempeño, $\xi$, se supone que el proceso es de segundo orden o que hay dos constantes de tiempo considerablemente más largas que las otras. Estas dos constantes de tiempo pueden "dominar" la dinámica del proceso y son el origen de las raíces que se encuentran $n-k$ hacia la derecha (las más cercanas al eje imaginario) y que se conocen como **raíces dominantes**. El ajustar un controlador por retroalimentación para las especificaciones anteriores significa que con las dos raíces dominantes de la ecuación característica se debe satisfacer la ecuación:

$$\tau^2s^2 + 2\xi\tau s + 1 = 0$$

con $\xi = 0.707$, estas raíces son:

En la figura 7-11 se muestran gráficamente dichas raíces. A partir de esta figura se puede determinar lo siguiente:

$$\cos \theta = \xi$$

entonces, para:

$$\xi = 0.707$$
$$\cos \theta = 0.707 \quad \Rightarrow \quad \theta = 45°$$

En la figura 7-12 se muestra cómo encontrar las raíces, $s$ y $s^*$, del sistema con este factor de amortiguamiento. En tal caso las raíces se localizan, de manera aproximada, en $-0.06 \pm 0.06i$. Ahora se debe calcular la ganancia del controlador con que se obtiene dicho comportamiento de lazo cerrado, para lo cual se utiliza el criterio de magnitud, ecuación (7-12), y, por tanto, se debe medir la distancia entre la raíz $s$, cada polo y cero; la medición se puede hacer simplemente con una regla (utilizando la misma escala de magnitud que en el eje) o mediante el teorema de Pitágoras, se prefiere este último, ya que se minimizan los errores de medición. Para tal sistema, el criterio de magnitud es:

$$K' = \prod_{j=1}^{n}|s - p_j|$$

Puesto que el primer polo se presenta en $p_1 = -0.033 + 0i$, se tiene que, al calcular la distancia $|s - p_1|$ mediante el teorema de Pitágoras, ésta es:

$$|s - p_1| = \sqrt{(0.060 - 0.033)^2 + (0.06 - 0)^2} = 0.066$$

de manera semejante:

$$|s - p_2| = \sqrt{(0.060 - 0.1)^2 + (0.06 - 0)^2} = 0.072$$
$$|s - p_3| = \sqrt{(0.060 - 0.33)^2 + (0.06 - 0)^2} = 0.276$$

entonces:

$$K' = (0.066)(0.072)(0.276) = 0.00131$$

y puesto que:

$$K' = 0.000888K_c$$

la ganancia del controlador es:

$$K_c = 1.475$$

Esta ganancia del controlador da lugar a una respuesta oscilatoria del circuito de control, con un factor de amortiguamiento de 0.707.

A continuación se presenta un ejemplo más detallado.

**Ejemplo 7-5.** Se desea utilizar un controlador PI para controlar el intercambiador de calor del ejemplo 7-4. Grafíquese el diagrama de lugar de raíz para este nuevo sistema de control, para lo cual se utiliza un tiempo de reajuste de 1 min. ¿Cuál es el efecto de añadir la acción de reajuste al controlador?

El diagrama de bloques se muestra en la figura 7-13; se notará que el tiempo de reajuste está dado en segundos (60), en lugar de minutos (1 min), a fin de mantener la consistencia en las unidades.

**Ecuación característica:**
$$1 + \frac{0.8K_c(60s + 1)}{60s(10s+1)(30s+1)(3s+1)} = 0$$

$$FTCA = \frac{K'(s + 1/60)}{s(s + 1/10)(s + 1/30)(s + 1/3)}$$

donde:

$$K' = \frac{0.8K_c}{60(10)(30)(3)} = 0.0000148K_c$$

con polos: $0$, $-1/10$, $-1/30$, $-1/3$; $n = 4$; ceros: $-60$; $m = 1$.

En la figura 7-14 se muestra la ubicación de los polos (x) y los ceros (o) en el plano $s$.

- De la regla 1, se tiene que el eje real negativo forma parte del lugar de raíz, entre el polo en 0 y el cero en $-60$. Éste es también el caso entre los polos en $-1/30$ y $-1/10$, y del polo en $-1/3$ a $-\infty$.
- De la regla 2, se tiene que el origen del lugar de raíz está en $0$, $-1/10$, $-1/30$ y $-1/3$, que son los polos de la FTCA.
- Puesto que hay cuatro polos, $n = 4$, en la regla 3 se establece que existen cuatro lugares o ramas.
- Puesto que existe un cero, $m = 1$, en la regla 4 se establece que una de las ramas debe terminar en este cero; en tal caso, es la rama que se origina en el polo igual a cero. Las otras ramas, $n - m = 3$, tenderán a infinito conforme se incremente $K_c$.
- El centro de gravedad se determina mediante la regla 5, así como los ángulos que forman las asíntotas con el eje real positivo. Puesto que hay tres ramas que se aproximan a infinito, debe haber tres asíntotas. De acuerdo con la ecuación (7-14):

$$CG = \frac{-\frac{1}{10} - \frac{1}{30} - \frac{1}{3} + \frac{1}{60}}{3} = -0.15$$

y, de la ecuación (7-15), se tiene:

$$\phi = \frac{180° + 360°(0)}{3}, \frac{180° + 360°(1)}{3}, \frac{180° + 360°(2)}{3}$$
$$\phi = 60°, 180°, 300°$$

En la figura 7-14 se muestran estas asíntotas y los ángulos; una de las asíntotas coincide con el eje real y se mueve del centro de gravedad hacia menos infinito; las otras dos asíntotas se alejan del eje real, cruzan el eje imaginario y entran en la región compleja del plano $s$, lo cual indica una posible inestabilidad.

- Con la regla 6 se obtienen los puntos de ruptura; al aplicar la ecuación (7-16), se obtiene:

$$\frac{1}{s + 0} + \frac{1}{s + \frac{1}{10}} + \frac{1}{s + \frac{1}{30}} + \frac{1}{s + \frac{1}{3}} = \frac{1}{s + 60}$$

De las cuatro posibilidades que se obtuvieron: $-0.0137 \pm 0.0149i$, $-0.0609$, $-0.245$, el único punto de ruptura válido está en $-0.0609$, ya que es el único que coincide con la región del eje real donde se acercan dos lugares de raíz.

Al aplicar el método de substitución directa a la ecuación característica de este sistema, se determina que la frecuencia de cruce o última es $\omega_u = 0.202$, y la ganancia del controlador con que se produce esta condición es $K_{c_u} = 20.12$. En la figura 7-14 se muestra el diagrama final del lugar de raíz.

Al comparar la figura 7-10 con la 7-14, se observa que, al añadir la acción de reajuste al controlador proporcional, no se afecta significativamente la forma del lugar de raíz. El efecto más importante es el decremento en la ganancia última y en la frecuencia última. Se puede decir que con la acción de reajuste se hace que el circuito de control sea más inestable, ya que no tolera mucha ganancia del controlador antes de que se vuelva inestable. ¿Cuál es el efecto de hacer $\tau_I$ más grande o más pequeña?

### Resumen del lugar de raíz

En esta sección se presentó la técnica de lugar de raíz para el análisis y diseño del control de proceso. Se mostró que el desarrollo del diagrama de lugar de raíz es simple y no se requiere de matemáticas complicadas. Probablemente la mayor ventaja de este método es su naturaleza gráfica; por otro lado, su mayor desventaja es que no se puede aplicar a los procesos donde hay tiempo muerto. En este aspecto es similar a las técnicas que ya se estudiaron: prueba de Routh y substitución directa. En los ejemplos que se utilizaron se mostró también el efecto de las acciones derivativa y de reajuste sobre la estabilidad del circuito de control.

## 7-2. TÉCNICAS DE RESPUESTA EN FRECUENCIA

Las técnicas de respuesta en frecuencia son algunas de las técnicas más populares para el análisis y diseño de sistemas de control de sistemas lineales. En esta sección se presenta el significado de respuesta en frecuencia y la forma en que se utiliza tal técnica para analizar y sintetizar los sistemas de control.

Para empezar, se considera el diagrama de bloques general que se muestra en la figura 7-15; el circuito de control se abre antes de la válvula y después del transmisor. La señal de entrada a la válvula se obtiene de un generador de frecuencia variable, $x(t) = X_0\sin \omega t$; la señal de salida del transmisor y la de entrada a la válvula se registran en un dispositivo de registro; en la figura 7-16 se muestran ambos registros. Después de que cesan los transitorios, la respuesta de la salida del transmisor se hace senoidal, $y(t) = Y_0\sin(\omega t + \theta)$. Este experimento se conoce como "prueba senoidal".

Ahora se "realiza" el mismo experimento, pero se utilizan las funciones de transferencia con que se describe al proceso. Se propone la siguiente función de transferencia simple:

$$G(s) = \frac{Y(s)}{X(s)} = \frac{K}{\tau s + 1} \quad (7-17)$$

Con esta función de transferencia se describe la combinación de válvula, proceso y transmisor. La señal de entrada a la válvula es:

$$x(t) = X_0\sin \omega t$$

o:

$$X(s) = \frac{X_0\omega}{s^2 + \omega^2} \quad (7-18)$$

En consecuencia:

$$Y(s) = \frac{KX_0\omega}{(\tau s + 1)(s^2 + \omega^2)}$$

Para obtener la expresión en el dominio del tiempo se utilizan las técnicas que se estudiaron en el capítulo 2:

$$Y(t) = \frac{KX_0\omega\tau}{\tau^2\omega^2 + 1}e^{-t/\tau} + \frac{KX_0}{\sqrt{1 + \omega^2\tau^2}}[-\cos \omega t + \omega\tau \sin \omega t]$$

Finalmente, se utiliza la identidad:

$$A\cos x + B\sin x = r\sin(x + \theta)$$

donde:

$$r = \sqrt{A^2 + B^2} \qquad \theta = \tan^{-1}\left(\frac{A}{B}\right)$$

para cambiar la expresión de $y(t)$ a:

$$Y(t) = \frac{KX_0\omega\tau}{\tau^2\omega^2 + 1}e^{-t/\tau} + \frac{KX_0}{\sqrt{1 + \omega^2\tau^2}}\sin(\omega t + \theta) \quad (7-19)$$

con:

$$\theta = \tan^{-1}(-\omega\tau) = -\tan^{-1}(\omega\tau) \quad (7-20)$$

En la ecuación (7-19) se observa que, conforme se incrementa el tiempo, el término exponencial se hace cero; éste es el término transitorio que caduca. Cuando esto ocurre, la expresión de salida se convierte en:

$$Y(t)|_{t\to\infty} = \frac{KX_0}{\sqrt{1 + \omega^2\tau^2}}\sin(\omega t + \theta) \quad (7-21)$$

la cual constituye el comportamiento senoidal de la señal de salida. La amplitud de esta salida es:

$$Y_0 = \frac{KX_0}{\sqrt{1 + \omega^2\tau^2}}$$

En la ecuación (7-20), con el signo negativo se indica que la señal de salida "se retarda", respecto a la señal de entrada, en una cantidad $\theta$, que se calcula a partir de la ecuación. En la figura 7-16 se muestra toda esta información en forma gráfica.

Aquí se hace necesaria una advertencia: se debe tener cuidado cuando se calcula el término seno en la ecuación (7-21); el término $\omega$ está dado en radianes/tiempo, y el término $\omega t$, en radianes; por lo tanto, para que el resultado de la operación $(\omega t + \theta)$ esté expresado en las unidades correctas, $\theta$ debe estar en radianes. Si se utilizan grados, el término se debe escribir como:

$$(\omega t + \theta)\text{ en radianes}$$

en breve, se debe estar alerta y ser cuidadoso con estas unidades.

A continuación se definen algunos términos utilizados en el estudio de la respuesta en frecuencia.

**Razón de amplitud (RA)** se define como la razón de la amplitud de la señal de salida respecto a la amplitud de la señal de entrada. Esto es:

$$RA = \frac{Y_0}{X_0}$$

**Razón de magnitud (RM)** se define como la división de la razón de amplitud entre la ganancia de estado estacionario:

$$RM = \frac{RA}{K}$$

**Ángulo de fase ($\theta$)** es la cantidad, en grados o radianes, en que la señal de salida se retarda o adelanta respecto a la señal de entrada. Cuando $\theta$ es positiva, se trata de un ángulo de adelanto; cuando $\theta$ es negativa, se trata de un ángulo de retardo.

De la función de transferencia de primer orden que se vio anteriormente:

$$G(s) = \frac{K}{\tau s + 1}$$

$$|G(i\omega)| = \frac{K}{\sqrt{\tau^2\omega^2 + 1}}$$

$$\angle G(i\omega) = -\tan^{-1}(\omega\tau)$$

Cabe hacer notar que los tres términos están en función de la frecuencia de entrada. Naturalmente, cuando los procesos son diferentes, la forma en que RA (RM) y $\theta$ dependen de $\omega$, también es diferente.

La respuesta en frecuencia es esencialmente el estudio de la manera en que se comportan la RA (RM) y $\theta$ de diferentes componentes o sistemas cuando se cambia la frecuencia de entrada. En los párrafos siguientes se muestra que la respuesta en frecuencia es una técnica eficaz para analizar y sintetizar los sistemas de control. Primero se cubre el desarrollo de la respuesta en cuanto a frecuencia de los sistemas de proceso y se continúa con su utilización para el análisis y la síntesis.

En general, existen dos formas diferentes para generar la respuesta en frecuencia:

1. **Métodos experimentales.** Esto consiste esencialmente en el experimento que se mostró anteriormente, con el generador de frecuencia variable y el dispositivo de registro. La idea es realizar el experimento con diferentes frecuencias, para obtener una tabla de RA vs $\omega$ y de $\theta$ vs $\omega$. Dichos métodos experimentales se cubren posteriormente en este capítulo; con los mismos se tiene también una forma para identificar el sistema de proceso.

2. **Transformación de la función de transferencia de circuito abierto después de una perturbación senoidal.** Este método consiste en utilizar la función de transferencia de lazo abierto para obtener la respuesta del sistema a una entrada senoidal. La amplitud y el ángulo de fase de la salida se pueden determinar a partir de la respuesta. Éstas son esencialmente las manipulaciones matemáticas que se vieron anteriormente y de las que resultan las ecuaciones (7-20) y (7-21).

Afortunadamente, con las matemáticas operacionales se tiene un método muy simple para determinar RA (RM) y $\theta$. Las matemáticas que se necesitan se presentaron en el capítulo 2. Ahora en esta sección se desarrollará el método general para determinar RA (RM) y $\theta$. Si se considera:

$$\frac{Y(s)}{X(s)} = G(s)$$

para $x(t) = X_0\sin \omega t$, con base en la tabla 2-1, se tiene:

$$X(s) = \frac{X_0\omega}{s^2 + \omega^2}$$

Entonces:

$$Y(s) = G(s)\frac{X_0\omega}{s^2 + \omega^2}$$

De la expansión por fracciones parciales, resulta:

$$Y(s) = \frac{A}{s + i\omega} + \frac{B}{s - i\omega} + [\text{términos para los polos de } G(s)] \quad (7-22)$$

Para obtener $A$, se utiliza:

$$A = \lim_{s \to -i\omega}(s + i\omega)X_0\omega\frac{G(s)}{(s + i\omega)(s - i\omega)} = X_0\frac{G(-i\omega)}{-2i}$$

Como se demostró en el capítulo 2, cualquier número complejo se puede representar mediante una magnitud y un argumento, entonces:

$$A = X_0\frac{|G(i\omega)|e^{-i\angle G(i\omega)}}{-2i} = X_0\frac{|G(i\omega)|e^{-i\theta}}{-2i}$$

Para obtener $B$ se utiliza:

$$B = \lim_{s \to i\omega}(s - i\omega)X_0\omega\frac{G(s)}{(s^2 + \omega^2)} = X_0\frac{|G(i\omega)|e^{i\theta}}{2i}$$

Entonces, al substituir las expresiones para $A$ y $B$ en la ecuación (7-22) se obtiene:

$$Y(s) = X_0|G(i\omega)|\left[\frac{e^{-i\theta}}{-2i}\cdot\frac{1}{s + i\omega} + \frac{e^{i\theta}}{2i}\cdot\frac{1}{s - i\omega}\right] + [\text{términos de } G(s)]$$

Al regresar al dominio del tiempo se tiene:

$$y(t) = X_0|G(i\omega)|\left[\frac{-e^{-i\theta}e^{-i\omega t}}{2i} + \frac{e^{i\theta}e^{i\omega t}}{2i}\right] + [\text{términos transitorios}]$$

Después de un tiempo muy largo cesan los términos transitorios y entonces:

$$Y(t) = X_0|G(i\omega)|\frac{e^{i(\omega t + \theta)} - e^{-i(\omega t + \theta)}}{2i}$$

$$Y(t) = X_0|G(i\omega)|\sin(\omega t + \theta) \quad (7-23)$$

Ésta es la respuesta para $G(s)$ después de que cesan los transitorios.

La razón de amplitud es:

$$RA = \frac{Y_0}{X_0} = |G(i\omega)| \quad (7-24)$$

y el ángulo de fase es:

$$\theta = \angle G(i\omega) \quad (7-25)$$

De manera que para obtener la RA y $\theta$, se substituye $i\omega$ por $s$ en la función de transferencia y entonces se calcula la magnitud y el argumento del número complejo que resulta. La magnitud es igual a la razón de amplitud (RA) y el argumento al ángulo de fase ($\theta$).

Inclusive con esto se simplifican tremendamente los cálculos que se requieren.

Ahora se aplican estos resultados al sistema de primer orden que se utilizó anteriormente:

$$G(s) = \frac{K}{\tau s + 1}$$

Ahora se substituye $i\omega$ por $s$:

$$G(i\omega) = \frac{K}{i\omega\tau + 1}$$

de lo que resulta una expresión con números complejos, la cual se compone de la razón de los términos: el numerador es un número real y el denominador un número complejo. Las ecuaciones también se pueden escribir como sigue:

$$G(i\omega) = \frac{K}{1 + i\omega\tau}\cdot\frac{1 - i\omega\tau}{1 - i\omega\tau} = \frac{K(1 - i\omega\tau)}{1 + \omega^2\tau^2} = \frac{K}{1 + \omega^2\tau^2} - i\frac{K\omega\tau}{1 + \omega^2\tau^2} \quad (7-26)$$

Como se vio, la RA es igual a la magnitud de este número complejo:

$$RA = |G(i\omega)| = \frac{K}{\sqrt{1 + \omega^2\tau^2}} \quad (7-27)$$

la cual es la misma RA que se obtuvo anteriormente.

La $\theta$ es igual al argumento del número complejo:

$$\theta = \angle G(i\omega) = \angle G_1 - \angle G_2 = 0 - \tan^{-1}(\omega\tau) = -\tan^{-1}(\omega\tau) \quad (7-28)$$

la cual es también la misma $\theta$ que se obtuvo anteriormente.

A continuación se propondrán varios ejemplos.

**Ejemplo 7-6.** Se considera el siguiente sistema de segundo orden:

$$G(s) = \frac{K}{\tau^2s^2 + 2\xi\tau s + 1}$$

Se deben determinar las expresiones para AR y $\theta$.

El primer paso es substituir $i\omega$ por $s$:

$$G(i\omega) = \frac{K}{\tau^2(i\omega)^2 + 2\xi\tau(i\omega) + 1} = \frac{K}{(1 - \omega^2\tau^2) + i2\tau\xi\omega}$$

Una vez más, resulta una expresión con números complejos, la cual es una razón entre otros dos números.

$$G(i\omega) = \frac{G_1}{G_2} = \frac{K}{(1 - \omega^2\tau^2) + i2\tau\xi\omega}$$

La razón de amplitud es:

$$RA = |G(i\omega)| = \frac{|G_1|}{|G_2|} = \frac{K}{\sqrt{(1 - \omega^2\tau^2)^2 + (2\tau\xi\omega)^2}} \quad (7-29)$$

y el ángulo de fase es:

$$\theta = \angle G(i\omega) = \angle G_1 - \angle G_2 \quad (7-30)$$
$$\theta = 0 - \tan^{-1}\left(\frac{2\tau\xi\omega}{1 - \omega^2\tau^2}\right) = -\tan^{-1}\left(\frac{2\tau\xi\omega}{1 - \omega^2\tau^2}\right)$$

**Ejemplo 7-7.** Se considera la siguiente función de transferencia:

$$G(s) = K(1 + \tau s) \quad (7-31)$$

Esta función de transferencia es una ganancia que multiplica a un adelanto de primer orden. Se deben determinar las expresiones para RA y $\theta$.

De la substitución de $i\omega$ por $s$ resulta la siguiente expresión de número complejo:

$$G(i\omega) = K(1 + i\omega\tau)$$

en la cual también se puede suponer que está formada por otros dos números:

$$G(i\omega) = G_1G_2 = K(1 + i\omega\tau)$$

La razón de amplitud es:

$$RA = |G(i\omega)| = K\sqrt{1 + \omega^2\tau^2} \quad (7-32)$$

y el ángulo de fase es:

$$\theta = \angle G(i\omega) = \angle G_1 + \angle G_2 = 0 + \tan^{-1}(\omega\tau)$$
$$\theta = \tan^{-1}(\omega\tau) \quad (7-33)$$

Los ángulos de fase de los sistemas que se describen mediante las ecuaciones (7-17) y (7-31) se pueden comparar. Los sistemas que se describen por medio de la ecuación (7-17), a los cuales se hizo referencia en el capítulo 3 como retardos de primer orden, tienen ángulos de fase negativos, como se ve en la ecuación (7-28); los sistemas que se describen mediante la ecuación (7-31), a los cuales se hizo referencia en el capítulo 3 como adelantos de primer orden, tienen ángulos de fase positivos, como se aprecia en la ecuación (7-33). Este hecho es importante en el estudio de la estabilidad del control de proceso mediante técnicas de respuesta en frecuencia.

**Ejemplo 7-8.** Se deben determinar las expresiones para RA y $\theta$ cuando hay tiempo muerto:

$$G(s) = e^{-t_0s}$$

Al substituir $i\omega$ por $s$, se tiene:

$$G(i\omega) = e^{-i\omega t_0}$$

Puesto que la expresión ya está en la forma polar, se utilizan los principios estudiados en el capítulo 2, para obtener:

$$G(i\omega) = |G(i\omega)|e^{i\angle G(i\omega)} = e^{-i\omega t_0}$$

lo que significa que:

$$RA = |G(i\omega)| = 1 \quad (7-34)$$

Y:

$$\theta = \angle G(i\omega) = -t_0\omega \quad (7-35a)$$

Se debe recordar, como se aclaró antes respecto a las unidades de $\theta$, que en la ecuación (7-35a) las unidades de $\theta$ son radianes. Si se desea expresar $\theta$ en grados, entonces:

$$\theta = \frac{180°}{\pi}(-t_0\omega) \quad (7-35b)$$

Es interesante, y muy importante, observar que $\theta$ se vuelve cada vez más negativa conforme se incrementa $\omega$. La razón en que cae $\theta$, depende de $t_0$; mientras más grande es $t_0$, más rápido cae $\theta$. Este hecho se vuelve importante en el análisis de los sistemas de control de proceso. El tiempo muerto no afecta la razón de amplitud ni la razón de magnitud.

**Ejemplo 7-9.** Se deben determinar las expresiones de RA y $\theta$ para un integrador:

$$G(s) = \frac{1}{s}$$

Al substituir $i\omega$ por $s$, se tiene:

$$G(i\omega) = \frac{1}{i\omega}$$

del cual se puede pensar que lo constituyen dos números complejos:

$$G_1 = 1 \qquad G_2 = i\omega$$

La razón de amplitud de $G_1$ es 1 y la de $G_2$ es $\omega$, por lo tanto:

$$RA = |G(i\omega)| = \frac{|G_1|}{|G_2|} = \frac{1}{\omega} \quad (7-36)$$

y el ángulo de fase es:

$$\theta = \angle G(i\omega) = \angle G_1 - \angle G_2 = 0 - \frac{\pi}{2} = -\tan^{-1}(\infty)$$
$$\theta = -90° \quad (7-37)$$

De modo que, para un integrador, la razón de amplitud decrece conforme se incrementa la frecuencia; en cambio, el ángulo de fase permanece constante a $-90°$; es decir, con el integrador se obtiene un retardo de fase constante.

En este punto se pueden generalizar las expresiones para RA y $\theta$. Se considera la siguiente FTCA general:

$$FTCA(s) = \frac{K'\prod_{i=1}^{m}(\tau_is + 1)e^{-t_0s}}{s^k\prod_{j=1}^{n}(\tau_js + 1)} \quad (n + k) > m \quad (7-38)$$

Entonces se substituye $s$ por $i\omega$, para obtener:

$$FTCA(i\omega) = \frac{K'\prod_{i=1}^{m}(i\tau_i\omega + 1)e^{-it_0\omega}}{(i\omega)^k\prod_{j=1}^{n}(i\tau_j\omega + 1)}$$

y, finalmente, se llega a:

$$RA = \frac{K'\prod_{i=1}^{m}\sqrt{(\tau_i\omega)^2 + 1}}{\omega^k\prod_{j=1}^{n}\sqrt{(\tau_j\omega)^2 + 1}} \quad (7-39)$$

Y:

$$\theta = \sum_{i=1}^{m}\tan^{-1}(\tau_i\omega) - t_0\omega - k(90°) - \sum_{j=1}^{n}\tan^{-1}(\tau_j\omega) \quad (7-40)$$

Hasta ahora, las expresiones para RA y $\theta$ se desarrollaron como funciones de $\omega$. Existen varias formas para representar gráficamente estas expresiones; las más comunes son los diagramas de Bode, los diagramas de Nyquist y la carta de Nichols. En la siguiente sección se presentan los diagramas de Bode a detalle.

### Diagramas de Bode

El diagrama de Bode es la representación gráfica más común de las funciones RA (RM) y $\theta$. Este diagrama consta de dos gráficas: 1) logaritmo de RA (o logaritmo de RM) contra logaritmo de $\omega$, y 2) $\theta$ contra logaritmo de $\omega$. Algunas veces, en lugar de graficar logaritmo de RA, se grafica 20 logaritmo de RA, lo cual se conoce como decibeles; este término se utiliza extensamente en el campo de la ingeniería eléctrica y algunas veces también en el de control de proceso; en este libro se grafica logaritmo de RA. A continuación se presenta el diagrama de Bode para las funciones de transferencia de proceso más comunes.

**Elemento de ganancia.** En un elemento con ganancia pura se tiene como función de transferencia:

$$G(s) = K$$

Al substituir $i\omega$ por $s$, se obtiene:

$$G(i\omega) = K$$

se utiliza el manejo matemático que se presentó anteriormente para obtener:

$$RA = |G(i\omega)| = K$$

Y:

$$\theta = \angle G(i\omega) = 0°$$

En las figuras 7-17 y 7-18a se muestra el diagrama de Bode para este elemento; en la figura 7-17 se grafica logaritmo de RA; por otra parte, en la figura 7-18a se grafica logaritmo de RM. Se notará que en ambos casos se utiliza papel logarítmico-logarítmico y semilogarítmico.

**Retardo de primer orden.** Para un retardo de primer orden, la RA y $\theta$ se representan mediante las ecuaciones (7-27) y (7-28), respectivamente.

$$RA = \frac{K}{\sqrt{\tau^2\omega^2 + 1}} \quad (7-27)$$
$$\theta = -\tan^{-1}(\omega\tau) \quad (7-28)$$

En la figura 7-18b se muestra el diagrama de Bode para este sistema.

En el diagrama de la razón de magnitud de la figura 7-18b aparecen dos líneas punteadas, que son las asíntotas de la respuesta en frecuencia del sistema, a baja y alta frecuencia. Estas asíntotas son muy importantes en el estudio de la respuesta en frecuencia. Como se puede apreciar en la figura, éstas no se desvían mucho de la respuesta en frecuencia real y, por lo tanto, el análisis de respuesta en frecuencia casi siempre se hace mediante asíntotas, ya que éstas son más fáciles de dibujar y su utilización no implica mucho error. A continuación se muestra el desarrollo de tales asíntotas.

En la ecuación de razón de magnitud se observa que, conforme $\omega \to 0$, $RM \to 1$, de lo cual resulta la asíntota horizontal.

Antes de desarrollar la asíntota de alta frecuencia, se escribe la ecuación de razón de magnitud en forma logarítmica:

$$\log RM = -1/2\log(\tau^2\omega^2 + 1)$$

ahora, conforme $\omega \to \infty$:

$$\log RM \to -1/2\log \tau^2\omega^2 = -\log \tau\omega$$
$$\log RM \to -\log \tau - \log \omega \quad (7-41)$$

la cual es la expresión de una línea recta en una gráfica logaritmo-logaritmo de RM vs $\omega$, la pendiente de esta línea recta es $-1$. Ahora se debe determinar la ubicación de dicha línea en la gráfica; el modo más simple de hacer esto es localizar el lugar donde la asíntota de alta frecuencia interseca a la de baja frecuencia; se sabe que, cuando $\omega \to 0$, $RM \to 1$, de manera que:

$$\log RM = 0$$

Al igualar esta ecuación con la (7-41), se tiene:

$$\omega = \frac{1}{\tau} \quad (7-42)$$

En esta frecuencia, conocida como **frecuencia de vértice** o frecuencia de punto de corte, se juntan ambas asíntotas, como se muestra en la figura 7-18b. También es a esta frecuencia donde se presenta el error máximo entre la respuesta en frecuencia y las asíntotas. La razón de magnitudes verdadera es $\frac{1}{\sqrt{2}}$ y no $RM = 1$, como se aprecia en las asíntotas.

Antes de concluir con el diagrama de Bode de este sistema, vale la pena observar qué sucede con $\theta$ a bajas y altas frecuencias. A bajas frecuencias:

$$\omega \to 0 \quad \Rightarrow \quad \theta \to -\tan^{-1}(0) = 0°$$

A altas frecuencias:

$$\omega \to \infty \quad \Rightarrow \quad \theta \to -\tan^{-1}(\infty) = -90°$$

Estos valores del ángulo de fase, $0°$ y $-90°$, son las asíntotas para el diagrama de ángulo de fase. A la frecuencia de vértice:

$$\omega_c = \frac{1}{\tau} \quad \Rightarrow \quad \theta = -\tan^{-1}(1) = -45°$$

Para resumir, las características más importantes del diagrama de Bode de un retardo de primer orden son las siguientes:

1. **Gráfica de RA (RM).** La pendiente de la asíntota de baja frecuencia es 0, mientras que la de la de alta frecuencia es $-1$. La frecuencia de vértice, donde se juntan estas dos asíntotas, es de $1/\tau$.
2. **Gráfica del ángulo de fase.** A bajas frecuencias el ángulo de fase tiende a $0°$; en cambio, a altas frecuencias tiende a $-90°$. A la frecuencia de vértice, el ángulo de fase es de $-45°$.

**Retardo de segundo orden.** Como se muestra en el ejemplo 7-6, las expresiones de RA y $\theta$ para un retardo de segundo orden las dan las ecuaciones (7-29) y (7-30), respectivamente:

$$RA = \frac{K}{\sqrt{(1 - \omega^2\tau^2)^2 + (2\tau\xi\omega)^2}} \quad (7-29)$$

Y:

$$\theta = -\tan^{-1}\left(\frac{2\tau\xi\omega}{1 - \omega^2\tau^2}\right) \quad (7-30)$$

La expresión de RM se obtiene a partir de la expresión de RA:

$$RM = \frac{1}{\sqrt{(1 - \omega^2\tau^2)^2 + (2\tau\xi\omega)^2}}$$

Al darle valores a $\omega$ para una cierta $\tau$ y $\xi$, la respuesta en frecuencia se determina como se muestra en la figura 7-18d.

Las asíntotas se obtienen de manera similar que en el caso del retardo de primer orden. A bajas frecuencias:

$$RM \to 1$$
Y:
$$\theta \to 0°$$

A altas frecuencias:

$$\log RM \to -1/2\log[(1 - \omega^2\tau^2)^2 + (2\tau\xi\omega)^2]$$
$$\log RM \to -1/2\log(\omega^4\tau^4) = -2\log \tau - 2\log \omega$$

La cual es la expresión de una línea recta con pendiente $-2$. El ángulo de fase a estas altas frecuencias tiende a $-180°$. Para encontrar la frecuencia de vértice, $\omega_c$, a la cual se encuentran las asíntotas, se sigue el mismo procedimiento que para el retardo de primer orden, y se obtiene:

$$\omega_c = \frac{1}{\tau}$$

En la figura 7-18d se observa que la transición de la respuesta en frecuencia de baja a alta frecuencia depende de $\xi$.

A la frecuencia de vértice:

$$\theta = -\tan^{-1}(\infty) = -90°$$

Para resumir, las características importantes del diagrama de Bode para un retardo de segundo orden son las siguientes:

1. **Gráfica de RA (RM).** La pendiente de la asíntota de baja frecuencia es 0; en cambio, la pendiente de la asíntota de alta frecuencia es $-2$. La frecuencia de vértice, $\omega_c$, ocurre a $1/\tau$. La transición de RA de baja a alta frecuencia depende del valor de $\xi$.
2. **Gráfica del ángulo de fase.** A bajas frecuencias, el ángulo de fase tiende a $0°$; por el contrario, a altas frecuencias tiende a $-180°$. A la frecuencia de vértice, el ángulo de fase es de $-90°$.

**Tiempo muerto.** Como se vio en el ejemplo 7-8, las expresiones de RA y $\theta$ para el tiempo muerto se dan mediante las ecuaciones (7-34) y (7-35), respectivamente:

$$RA = RM = 1 \quad (7-34)$$

Y:

$$\theta = -t_0\omega \quad (7-35a)$$
$$\theta = \frac{180°}{\pi}(-t_0\omega) \quad (7-35b)$$

El diagrama de Bode se ilustra en la figura 7-18c; se notará que, conforme aumenta la frecuencia, el ángulo de fase se vuelve más negativo. Tanto más grande es el valor del tiempo muerto cuanto más rápido cae el ángulo de fase (se vuelve cada vez más negativo). El diagrama del ángulo de fase no tiende de manera asintótica a ningún valor final.

**Adelanto de primer orden.** Como se ve en el ejemplo 7-7, las expresiones de RA y $\theta$ para el adelanto de primer orden se tienen en las ecuaciones (7-32) y (7-33), respectivamente:

$$RA = K\sqrt{1 + \omega^2\tau^2} \quad (7-32)$$
$$RM = \sqrt{1 + \omega^2\tau^2}$$

Y:

$$\theta = \tan^{-1}(\omega\tau) \quad (7-33)$$

El diagrama de Bode se muestra en la figura 7-18e. Cabe hacer notar que la pendiente de la asíntota de baja frecuencia es 0; en cambio, la de la asíntota de alta frecuencia es $+1$. A bajas frecuencias, el ángulo de fase tiende a $0°$; por el contrario, a altas frecuencias tiende a $+90°$; a la frecuencia de vértice el ángulo de fase es de $+45°$ y, por lo tanto, en un adelanto de primer orden se tiene "adelanto de fase".

**Integrador.** Como se ve en el ejemplo 7-9, las expresiones de RA y $\theta$ para un integrador se tienen en las ecuaciones (7-36) y (7-37), respectivamente:

$$RA = \frac{1}{\omega} \quad \Rightarrow \quad RM = \frac{1}{\omega} \quad (7-36)$$

Y:

$$\theta = -90° \quad (7-37)$$

El diagrama de Bode se ilustra en la figura 7-18f. Se notará que la gráfica de RM consta de una línea recta cuya pendiente es $-1$, lo cual se demuestra fácilmente al obtener el logaritmo de la ecuación (7-36):

$$\log RM = -\log \omega$$

En esta ecuación también se ve que $RM = 1$, con $\omega = 1$ radián/tiempo.

**Desarrollo del diagrama de Bode para sistemas complejos.** La mayoría de las funciones de transferencia complejas de sistemas de proceso se forman como producto de componentes más simples. El diagrama de Bode para estas funciones de transferencia complejas se puede obtener mediante la adición de los diagramas de Bode de las componentes simples, las cuales se presentaron, en su mayor parte, en las secciones precedentes. Ahora se considera la siguiente función:

$$G(s) = \frac{K(\tau_1s + 1)e^{-t_0s}}{(\tau_2s + 1)(\tau_3s + 1)} \quad (7-43)$$

Se puede considerar que esta función de transferencia se compone de las siguientes cinco funciones de transferencia simples:

$$G(s) = G_1(s)G_2(s)G_3(s)G_4(s)G_5(s)$$

donde:
- $G_1(s) = K$
- $G_2(s) = (\tau_1s + 1)$
- $G_3(s) = e^{-t_0s}$
- $G_4(s) = \frac{1}{\tau_2s + 1}$
- $G_5(s) = \frac{1}{\tau_3s + 1}$

El desarrollo del diagrama de Bode para la ecuación (7-43) es muy simple; para RA y RM se tiene:

$$|G(i\omega)| = |G_1(i\omega)||G_2(i\omega)||G_3(i\omega)||G_4(i\omega)||G_5(i\omega)| \quad (7-44)$$

$$RM = \frac{|G(i\omega)|}{K} = |G_2(i\omega)||G_3(i\omega)||G_4(i\omega)||G_5(i\omega)| \quad (7-45)$$

o, dado que frecuentemente se grafican los logaritmos, se ve que:

$$\log RA = \log|G_1| + \log|G_2(i\omega)| + \log|G_3(i\omega)| + \log|G_4(i\omega)| + \log|G_5(i\omega)| \quad (7-46)$$

$$\log RM = \log|G_2(i\omega)| + \log|G_3(i\omega)| + \log|G_4(i\omega)| + \log|G_5(i\omega)| \quad (7-47)$$

y, para el ángulo de fase, se tiene:

$$\angle G(i\omega) = \angle G_1(i\omega) + \angle G_2(i\omega) + \angle G_3(i\omega) + \angle G_4(i\omega) + \angle G_5(i\omega) \quad (7-48)$$

En las ecuaciones (7-47) y (7-48) se observa que, para obtener el diagrama de Bode compuesto, se suman los diagramas de Bode individuales. Para obtener la asíntota compuesta, se suman las asíntotas individuales.

**Ejemplo 7-10.** Ahora se considera la siguiente función de transferencia:

$$G(s) = \frac{K(s + 1)e^{-0.5s}}{s(2s + 1)(3s + 1)}$$

Se utilizan los principios que se expusieron y se ve que:

$$\log RM = \frac{1}{2}\log(\omega^2 + 1) - \log(\omega) - \frac{1}{2}\log(4\omega^2 + 1) - \frac{1}{2}\log(9\omega^2 + 1)$$

Y:

$$\theta = \tan^{-1}(\omega) - 0.5\omega - 90° - \tan^{-1}(2\omega) - \tan^{-1}(3\omega)$$

Como se muestra en la figura 7-19, el diagrama de Bode se desarrolla a partir de estas dos últimas ecuaciones. Cabe señalar que la asíntota compuesta se obtiene mediante la adición de las asíntotas individuales. A bajas frecuencias, $\omega < 0.33$, la pendiente es $-1$, a causa del término integrador; con $\omega = 0.33$, uno de los retardos de primer orden empieza a contribuir en la gráfica y, entonces, la pendiente cambia a $-2$ con dicha frecuencia; con $\omega = 0.5$, se agrega la contribución del otro retardo de primer orden y la pendiente de la asíntota cambia a $-3$; finalmente, con $\omega = 1$, entra el adelanto de primer orden con una pendiente de $+1$, y la pendiente de la asíntota se hace de nuevo $-2$. El diagrama del ángulo de fase compuesto se obtiene de manera similar, mediante la suma algebraica de los ángulos individuales.

Acerca de la pendiente de las asíntotas de alta y baja frecuencia (pendiente inicial y final) y de los ángulos de los diagramas de Bode, se puede hacer un comentario final: si se considera una función de transferencia general, por ejemplo:

$$G(s) = \frac{K(a_ms^m + a_{m-1}s^{m-1} + \ldots + 1)}{s^k(b_ns^n + b_{n-1}s^{n-1} + \ldots + 1)} \quad (n + k) > m \quad (7-49)$$

La pendiente de la asíntota de baja frecuencia se expresa mediante:

$$\text{pendiente de RA (RM)} \to (-1)k$$
$$\omega \to 0$$

y el ángulo con:

$$\theta \to (-90°)k$$
$$\omega \to 0$$

La pendiente de la asíntota de alta frecuencia se expresa mediante:

$$\text{pendiente de RA (RM)} \to (n + k - m)(-1)$$
$$\omega \to \infty$$

y el ángulo, por medio de:

$$\theta \to (n + k - m)(-90°)$$
$$\omega \to \infty$$

La mayoría de los sistemas siguen estas pendientes y ángulos; tales sistemas se conocen como **sistemas de fase mínima**. Sin embargo, existen tres excepciones, las cuales se conocen como **sistemas de fase no mínima**; las excepciones son:

1. Sistemas con tiempo muerto: $G(s) = e^{-t_0s}$
2. Sistemas con respuesta inversa (ceros positivos): $G(s) = (1 - \tau s)/(1 + \tau s)$
3. Sistemas de circuito abierto inestable (polos positivos), por ejemplo, algunos reactores químicos exotérmicos: $G(s) = 1/(1 - \tau s)$

En cada uno de estos casos, la gráfica de razón de magnitud no cambia, pero la gráfica de ángulo de fase sí; el ángulo de fase siempre se hace más negativo de lo que se predice. El término de tiempo muerto se presentó anteriormente; el diagrama de Bode de los otros dos sistemas es el tema de uno de los problemas que se presentan al final del capítulo.

En la expresión de la pendiente de la asíntota de alta frecuencia también se observa por qué en la función de transferencia debe haber más retardos que adelantos. Si $(n + k - m) < 0$, entonces la pendiente final es positiva y el ruido de una frecuencia muy alta se amplifica con ganancia infinita.

**Criterio de estabilidad de la respuesta en frecuencia.** Ahora se desarrolla el criterio de estabilidad de la respuesta en frecuencia, por medio de un ejemplo, con el fin de facilitar la comprensión del significado del criterio.

Se considera el circuito de control de temperatura del intercambiador de calor que se presentó en el capítulo 6 y que se utilizó en el ejemplo 7-4. Por conveniencia se vuelve a mostrar el intercambiador de calor en la figura 7-20, y el diagrama de bloques en la figura 7-21. La función de transferencia de circuito abierto es:

$$FTCA = \frac{0.8K_c}{(10s + 1)(30s + 1)(3s + 1)} \quad (7-50)$$

Las expresiones de RM y $\theta$ son:

$$RM = \frac{RA}{0.8K_c} = \frac{1}{\sqrt{(10\omega)^2 + 1}\sqrt{(30\omega)^2 + 1}\sqrt{(3\omega)^2 + 1}} \quad (7-51)$$

$$\theta = -\tan^{-1}(10\omega) - \tan^{-1}(30\omega) - \tan^{-1}(3\omega) \quad (7-52)$$

En la figura 7-22 se muestra el diagrama de Bode. En esta figura se ve que la frecuencia a la que $\theta = -180°$ (o $-\pi$ radianes) es de 0.22 rad/s; a esta frecuencia:

$$RA = 0.052$$

La ganancia del controlador con la que se produce $RA = 1$ es:

$$K_c = \frac{1}{0.8(0.052)} = \frac{1}{0.8(0.052)} = 24.0$$

Estos cálculos son altamente significativos. El valor $K_c = 24.0$ es la ganancia del controlador con que se produce $RA = 1$; se recordará que RA se define como la razón de la amplitud de la señal de salida respecto a la amplitud de la señal de entrada, $Y_0/X_0$, lo cual significa que, si el punto de control de entrada al controlador de temperatura se varía como sigue:

$$T_c^{sp}(t) = \sin(0.22t)$$

entonces la señal que sale del transmisor, después de que desaparecen los transitorios, variará de la siguiente manera:

$$T_c^m(t) = \sin(0.22t - 180°) = -\sin(0.22t)$$

Se notará que la señal de retroalimentación se desconecta en el controlador, como se aprecia en el diagrama de bloques de la figura 7-21, y que la frecuencia de oscilación del punto de control es 0.22 rad/s, que es la frecuencia a la cual $\theta = -180° = -\pi$ radianes y $RA = 1$.

Si ahora se supone que en algún tiempo $t = 0$ cesa la oscilación del punto de control, $T_c^{sp} = 0$, y que la señal del transmisor se conecta al controlador, entonces, la señal de error, $E(s)$, dentro del controlador permanece sin alteraciones y las oscilaciones se mantienen. Si en el circuito de control no se cambia nada, las oscilaciones se mantienen indefinidamente.

Si en algún momento la ganancia del controlador se incrementa ligeramente a 25.0, la razón de amplitud se hace de 1.04:

$$RA = 0.052(0.8)K_c$$
$$RA = 0.052(0.8)(25) = 1.04$$

Esto significa que la señal se amplifica conforme pasa a través del circuito de control. Después de la primera vez, la señal de salida del transmisor es $-1.04\sin(0.22t)$; después de la segunda vez, es $-(1.04)^2\sin(0.22t)$, y así, sucesivamente. En caso de que esto no se detenga, la temperatura de salida se incrementa continuamente, lo que produce un circuito de control inestable.

Por otro lado, si la ganancia del controlador se decrementa ligeramente a 23.0, entonces la razón de amplitud se hace de 0.957:

$$RA = 0.052(0.8)(23) = 0.957$$

Esto significa que la señal decrece en amplitud conforme pasa a través del circuito de control. Después de la primera vez, la señal de salida del transmisor es $-0.957\sin(0.22t)$; después de la segunda vez, es $-(0.957)^2\sin(0.22t)$, y así, sucesivamente. El resultado de esto es un circuito de control estable.

En resumen, con base en la respuesta en frecuencia, el criterio de estabilidad se puede enunciar como sigue:

> Para que un sistema de control sea estable, la razón de amplitud debe ser menor a la unidad cuando el ángulo de fase es $-180°$ ($-\pi$ radianes).

Si $RA < 1$, con $\theta = -180°$, el sistema es estable. Sin embargo, si $RA > 1$ con $\theta = -180°$, el sistema es inestable, lo cual se demostró en el ejemplo anterior.

La ganancia del controlador con la que se cumple la condición de que $RA = 1$ y $\theta = -180°$ es la ganancia última, $K_{c_u}$; en el ejemplo anterior $K_{c_u} = 24$. La frecuencia a la que se presenta esta condición es la frecuencia última, $\omega_u$; como se vio en el capítulo 6, el período último se puede calcular a partir de dicha frecuencia.

Antes de proceder con más ejemplos, es conveniente señalar que la frecuencia última y la ganancia última se pueden obtener directamente de la ecuación de RM y $\theta$, ecuaciones (7-51) y (7-52) para este ejemplo, sin que sea necesario el diagrama de Bode, el cual se desarrolló a partir de estas ecuaciones; con la utilización de las mismas se evita el desarrollo del diagrama. Hace muchos años, cuando no había calculadoras manuales (¿recuerda el lector la regla de cálculo?), probablemente era más fácil dibujar el diagrama de Bode mediante las asíntotas de alta y baja frecuencia. En la actualidad, la utilización de las calculadoras hace que la determinación de $\omega_u$ y $K_{c_u}$ sea un procedimiento más fácil. Para determinar $\omega_u$ se requiere un poco de ensayo y error en la ecuación de $\theta$; una vez que se determina $\omega_u$, se utiliza la ecuación de RM para calcular $K_{c_u}$. Este procedimiento completo generalmente es más rápido y se tienen resultados más precisos que cuando se dibuja y utiliza el diagrama de Bode; sin embargo, la utilización de dicho diagrama es muy útil, ya que se observa visualmente la forma en que varían RA y $\theta$ cuando varía la frecuencia.

A continuación se presentan varios ejemplos para que se adquiera más práctica en la utilización de esta eficaz técnica.

**Ejemplo 7-11.** Ahora se considera el mismo intercambiador de calor que se utilizó anteriormente para explicar el criterio de estabilidad de la respuesta en frecuencia, figura 7-20. Se supone que por alguna razón no se puede medir la temperatura a la salida del intercambiador, sino más adelante, en la tubería, como se muestra en la figura 7-23; el efecto de esta nueva ubicación del sensor es que se añade algo de tiempo muerto, cosa de dos segundos, en el circuito de control. En la figura 7-24 se ilustra el diagrama de bloques con la nueva función de transferencia.

La FTCA nueva es:

$$FTCA = \frac{0.8K_c e^{-2s}}{(10s + 1)(30s + 1)(3s + 1)}$$

con:

$$RA = RM = \frac{1}{\sqrt{(10\omega)^2 + 1}\sqrt{(30\omega)^2 + 1}\sqrt{(3\omega)^2 + 1}}$$

Y:

$$\theta = -2\omega - \tan^{-1}(10\omega) - \tan^{-1}(30\omega) - \tan^{-1}(3\omega)$$

Como se explicó anteriormente, estas dos últimas expresiones se pueden utilizar para determinar la frecuencia última y la ganancia última. Al hacer los cálculos, se encuentra que para $\theta = -\pi$ rad:

$$\omega_u = 0.16 \text{ rad/s}$$

Y:

$$K_{c_u} = 12.8$$

El diagrama de Bode se muestra en la figura 7-25.

En los resultados del ejemplo 7-11 se observa el efecto del tiempo muerto sobre la estabilidad y, en consecuencia, también sobre la controlabilidad del circuito de control. Con anterioridad se encontró que la ganancia y el período últimos del intercambiador de calor sin tiempo muerto eran:

$$K_{c_u} = 24 \qquad \omega_u = 0.22 \text{ rad/s}$$

cuando se añadió el tiempo muerto en el ejemplo 7-11, los resultados fueron:

$$K_{c_u} = 12.8 \qquad \omega_u = 0.16 \text{ rad/s}$$

Por lo tanto, es más fácil que el proceso se haga inestable. Con la $\omega_u$ diferente, también se indica que un proceso con tiempo muerto es más lento que uno sin tiempo muerto.

Como se mencionó en los capítulos anteriores, el tiempo muerto es la peor cosa que puede ocurrir en cualquier circuito de control, esto se prueba con el ejemplo 7-11. Con el término de tiempo muerto se "añade retardo de fase" al circuito de control y, en consecuencia, el ángulo de fase cruza el valor de $-180°$ con una frecuencia más baja. Cuanto más grande es el tiempo muerto, tanto más bajas son la frecuencia y la ganancia últimas.

En el ejemplo 7-5 se demostró que, al añadir la acción de reajuste a un controlador proporcional, se decrementan la frecuencia y la ganancia últimas. Esto se puede explicar desde el punto de vista de la respuesta en frecuencia, si se declara que, al añadir la acción de reajuste, se "añade retardo de fase" al circuito de control. En un controlador únicamente proporcional, el ángulo de fase es de $0°$, como se muestra en la figura 7-17. Ahora se considera un controlador proporcional integral:

$$G_c(s) = K_c\left(1 + \frac{1}{\tau_Is}\right) = K_c\frac{\tau_Is + 1}{\tau_Is}$$

La función de transferencia se compone de un término de adelanto, $\tau_Is + 1$, y de un término integrador, $1/\tau_Is$. A bajas frecuencias:

$$\omega \ll \frac{1}{\tau_I}$$

el término de avance no afecta al ángulo de fase, pero el integrador contribuye con $-90°$ y, en consecuencia, añade retardo de fase. A altas frecuencias:

$$\omega \gg \frac{1}{\tau_I}$$

el término integrador se cancela con el término de adelanto y resulta un ángulo de fase de $0°$. En las figuras 7-18f y 7-18e se muestra el diagrama de Bode para un integrador y un adelanto de primer orden, respectivamente.

Sin embargo, el lector debe recordar que la acción de reajuste es la única acción con que se puede eliminar la desviación en un controlador. Por otro lado, es más difícil ajustar el controlador, ya que se tienen dos términos que se deben ajustar, $K_c$ y $\tau_I$, y, como se explicó en el párrafo anterior, es más fácil que el proceso se haga inestable. Tal parece que la segunda ley de la termodinámica se puede aplicar también al control de proceso: No se puede obtener algo de nada.

Con el siguiente ejemplo se muestra el efecto de la acción derivativa sobre la estabilidad de un circuito de control.

**Ejemplo 7-12.** Ahora se considera el mismo circuito de control para el intercambiador de calor, pero sin tiempo muerto y con un controlador proporcional-derivativo. Se supone que la rapidez derivativa es 0.25 min (15 seg). Como se vio en el capítulo 5, la ecuación de un controlador PD "real" es:

$$G_c(s) = K_c\left(1 + \tau_Ds\right)\left(\frac{1}{\alpha\tau_Ds + 1}\right)$$

o para este ejemplo, con $\alpha = 0.1$:

$$G_c(s) = K_c\frac{1 + 15s}{1 + 1.5s}$$

Entonces la FTCA es:

$$FTCA = \frac{0.8K_c(1 + 15s)}{(10s + 1)(30s + 1)(3s + 1)(1 + 1.5s)}$$

con:

$$RA = RM = \frac{\sqrt{(15\omega)^2 + 1}}{\sqrt{(10\omega)^2 + 1}\sqrt{(30\omega)^2 + 1}\sqrt{(3\omega)^2 + 1}\sqrt{(1.5\omega)^2 + 1}}$$

Y:

$$\theta = \tan^{-1}(15\omega) - \tan^{-1}(10\omega) - \tan^{-1}(30\omega) - \tan^{-1}(3\omega) - \tan^{-1}(1.5\omega)$$

El diagrama de Bode para este sistema se muestra en la figura 7-26. Si se compara dicho diagrama con el de la figura 7-22, se observa que el diagrama del ángulo de fase se "movió hacia arriba"; la acción derivativa "añade adelanto de fase". En este sistema se encontró que la ganancia y el período últimos son:

$$K_{c_u} = 33.05 \qquad \omega_u = 0.53 \text{ rad/s}$$

Por tanto, con estos resultados se demuestra que con la acción derivativa el circuito de control se hace más estable y más rápido.

Con los ejemplos que se presentaron en esta sección se ilustró la utilización de la respuesta en frecuencia, en particular de los diagramas de Bode, para el análisis de los circuitos de control, así como el efecto de los diferentes términos, tiempo muerto y acción derivativa sobre la estabilidad de los mismos circuitos.

Con base en el criterio de estabilidad de la respuesta en frecuencia, cualquier circuito de control con una función de transferencia pura (sin tiempo muerto) de circuito abierto, de primer o segundo orden, nunca se hace inestable, debido a que el ángulo de fase nunca es inferior a $-180°$. Una vez que se añade tiempo muerto, sin importar qué tan pequeño sea, el sistema se hace inestable, porque el ángulo de fase siempre cruza el valor de $-180°$.

**Especificaciones de desempeño del controlador.** En el capítulo 6 se presentaron varias formas para ajustar un controlador y obtener el desempeño del circuito que se desea. Los métodos que se presentaron fueron el de Ziegler-Nichols (razón de asentamiento de un cuarto), el criterio de integral de error (IAE, ISE e IAET) y la síntesis del controlador. Con la técnica de respuesta en frecuencia se cuenta aún con otros métodos (en base a las diferentes especificaciones de desempeño) para ajustar los controladores; existen tres de tales métodos.

El primero es el mismo de Ziegler-Nichols. Como se vio en esta sección, con la respuesta en frecuencia se tiene un procedimiento conveniente y preciso para obtener la ganancia y la frecuencia últimas de un circuito de control; una vez que se determinan estos términos, se pueden utilizar las ecuaciones que se presentaron en el capítulo 6 para ajustar el controlador.

El **margen de ganancia (MG)** es una especificación típica del circuito de control que se asocia con la técnica de respuesta en frecuencia. El margen de ganancia representa el factor en que se debe aumentar la ganancia total del lazo para hacer inestable al sistema. La ganancia del controlador con que se produce el margen de ganancia que se desea se calcula como sigue:

$$K_{c,MG} = \frac{K_{c_u}}{MG} \quad (7-53)$$

La especificación típica es $MG > 1.5$.

El **margen de fase (MF)** es otra especificación típica que se asocia comúnmente a la técnica de respuesta en frecuencia, y es la diferencia entre $-180°$ y el ángulo de fase a la frecuencia con que la razón de amplitud (RA) es unitaria. Esto es:

$$MF = 180° + \theta \quad (7-54)$$
$$RA = 1$$

El MF representa la cantidad adicional de retardo de fase que se requiere para hacer inestable al sistema. La especificación típica es $MF > 45°$.

En el ejemplo 7-13 se ilustra la utilización de estas dos últimas especificaciones para el ajuste de un controlador.

**Ejemplo 7-13.** Se considera el intercambiador de calor del ejemplo 7-11. Ahora se debe ajustar un controlador proporcional para: a) $MG = 1.5$ y b) $MF = 45°$.

a) En el ejemplo 7-11 se determinó que la ganancia última del controlador es:

$$K_{c_u} = 12.8$$

En este caso la ganancia total del circuito es:

$$K_{punto} = 0.8K_{c_u} = 10.24$$

Para tener una especificación de MG de 1.5, la ganancia del controlador se fija entonces a:

$$K_{c,MG=1.5} = \frac{12.8}{1.5} = 8.53$$

Entonces la ganancia total del circuito es:

$$K_{punto} = 0.8(8.53) = 6.83$$

b) En el ejemplo 7-11 las expresiones para RM y $\theta$ eran:

$$RM = \frac{1}{0.8K_c}\cdot\frac{1}{\sqrt{(10\omega)^2 + 1}\sqrt{(30\omega)^2 + 1}\sqrt{(3\omega)^2 + 1}}$$

Y:

$$\theta = -2\omega - \tan^{-1}(10\omega) - \tan^{-1}(30\omega) - \tan^{-1}(3\omega)$$

Con base en la definición de margen de fase que se dio anteriormente, para un $MF = 45°$, $\theta = -135°$. Si se utiliza la ecuación para $\theta$, o el diagrama de Bode de la figura 7-25, la frecuencia para este ángulo de fase se puede determinar como:

$$\omega_{MF=45°} = 0.087 \text{ rad/s}$$

Entonces, se substituye en la ecuación de la razón de magnitud para obtener:

$$RA = 0.261$$

$$K_{c,MF=45°} = \frac{RA}{0.8(0.261)} = \frac{1}{0.8(0.261)} = 4.78$$

En el ejemplo 7-13 se muestra cómo obtener el ajuste de un controlador por retroalimentación para ciertos MG y MF. En la parte a) se ajustó el controlador para lograr un lazo de control con un MG de 1.5, lo cual significa que la ganancia total del lazo se debe incrementar (a causa de las alinealidades del proceso o por cualquier otra razón) en un factor de 1.5, antes de que se alcance la inestabilidad. Para elegir el valor de MG, el ingeniero debe entender el proceso para decidir cuánto puede cambiar la ganancia del proceso sobre el rango de operación; entonces, con base en esta comprensión se puede utilizar un valor realista de MG. Mientras más grande es el valor de MG que se utiliza, más grande es el "factor de seguridad" con que se diseña el circuito de control; sin embargo, tanto más grande es el factor de seguridad (MG), cuanto más pequeña es la ganancia resultante del controlador y, en consecuencia, el controlador es menos sensible a los errores. Por lo anterior es importante la elección de un MG realista.

En la parte b) del ejemplo se ajustó el controlador para lograr un MF de 45°. Esto significa que se puede añadir un retardo de fase de $45°$ al circuito de control antes de que se haga inestable. Los cambios en el ángulo de fase del circuito de control se deben principalmente a los cambios en sus términos dinámicos (constantes de tiempo y tiempo muerto), que son producto de las alinealidades del proceso.

El margen de ganancia y el margen de fase son dos criterios distintos de desempeño. La elección de uno de ellos como criterio para un circuito en particular depende del proceso a controlar. Si a causa de las alinealidades del proceso y sus características se espera que la ganancia cambie más que los términos dinámicos, entonces el criterio recomendable es el de MG; si, por el contrario, se espera que los términos dinámicos cambien más que la ganancia, entonces el criterio de MF es el recomendable.

En el ejemplo 7-13 se demostró la forma de calcular un controlador proporcional para producir la especificación de desempeño que se desea. Si se utiliza un controlador PI o PID, se debe fijar primero el tiempo de reajuste y la rapidez derivativa, antes de calcular $K_c$, lo cual significa que el desempeño que se desea se produce con más de un conjunto de parámetros de ajuste, y es responsabilidad del ingeniero decidir cuál considera como el "mejor".

En esta sección se estudió el significado del margen de ganancia y el del margen de fase, así como la forma de ajustar los controladores por retroalimentación con base en estas especificaciones de desempeño. Sin embargo, en los procesos industriales se prefieren las especificaciones de desempeño del capítulo 6.

### Diagramas polares

El diagrama polar es otra forma de graficar la respuesta en frecuencia de los sistemas de control; al contrario del caso de las dos gráficas de los diagramas de Bode, con este método se tiene la ventaja de que sólo se hace una gráfica. El diagrama polar es el de la función compleja $G(i\omega)$ conforme $\omega$ va de 0 a $\infty$; para todo valor de $\omega$ existe un vector en el plano complejo, con cuyo extremo se genera un lugar conforme cambia $\omega$; el principio del vector está en el origen, y su longitud es igual a la razón de amplitud de la función $G(i\omega)$; el ángulo que forma con el eje positivo real es el de fase. En esta sección se presentan los fundamentos de los diagramas polares y la manera de graficarlos. Primeramente se presentan los diagramas polares de algunas de las componentes de proceso más comunes.

**Retardo de primer orden.** La razón de amplitud y el ángulo de fase de un retardo de primer orden se expresan mediante las ecuaciones (7-27) y (7-28), respectivamente:

$$RA = \frac{K}{\sqrt{(\omega\tau)^2 + 1}} \quad (7-27)$$
$$\theta = -\tan^{-1}(\omega\tau) \quad (7-28)$$

Para $\omega = 0$, $RA = K$ y $\theta = 0°$. Para $\omega = 1/\tau$, $RA = K/\sqrt{2}$ y $\theta = -45°$. Para $\omega = \infty$, $RA = 0$ y $\theta = -90°$.

En la figura 7-27 se muestra el diagrama polar para este sistema. Con la línea continua se representa la razón de amplitud y el ángulo de fase cuando la frecuencia va de 0 a $\infty$. Con cada punto de la curva se representa una $\omega$ diferente. La longitud del vector, desde el origen hasta un punto en la curva, es igual a la razón de amplitud con esa $\omega$, y el ángulo que forma el vector con el eje positivo real es igual al ángulo de fase; en la figura 7-27 aparecen dos vectores, con el primero se representa la RA y $\theta$ para $\omega = 0$; con el segundo se representa RA y $\theta$ para $\omega = 1/\tau$. Se notará que, conforme RA se aproxima a cero, $\theta$ tiende a $-90°$, y esto es lo que se señala en las ecuaciones (7-27) y (7-28). Con la curva punteada se representa el diagrama de RA y $\theta$ cuando $\omega$ va de $-\infty$ a 0.

**Retardo de segundo orden.** Las ecuaciones de RA y $\theta$ para un retardo de segundo orden se representan con las ecuaciones (7-29) y (7-30), respectivamente:

$$RA = \frac{K}{\sqrt{(1 - \omega^2\tau^2)^2 + (2\tau\xi\omega)^2}} \quad (7-29)$$
$$\theta = -\tan^{-1}\left(\frac{2\tau\xi\omega}{1 - \omega^2\tau^2}\right) \quad (7-30)$$

Para $\omega = 0$, $RA = K$ y $\theta = 0°$; para $\omega = 1/\tau$, $RA = K/2\xi$ y $\theta = -90°$; para $\omega = \infty$, $RA = 0$ y $\theta = -180°$.

En la figura 7-28 se ilustra el diagrama polar de este sistema, en el cual RA tiende a cero desde el eje real negativo, porque $\theta$ tiende a $-180°$.

**Tiempo muerto.** Las expresiones de RA y $\theta$ para un sistema con tiempo muerto puro se expresan mediante las ecuaciones (7-34) y (7-35):

$$RA = 1 \quad (7-34)$$
$$\theta = -t_0\omega\frac{180°}{\pi} \quad (7-35)$$

Con estas ecuaciones se indica que la magnitud del vector siempre será unitaria y que, conforme se incremente $\omega$, el vector empezará a girar. En la figura 7-29 se muestra que el diagrama polar resultante es un círculo unitario.

**Mapeo de conformación.** Se han mostrado algunos ejemplos de diagramas polares, sin embargo, antes de continuar con este tema, es importante mencionar el mapeo de conformación, ya que los diagramas polares se apoyan bastante en esta teoría. Se presenta una breve introducción al mapeo de conformación para lograr un mejor entendimiento de los diagramas polares.

Ahora se considera la función de transferencia general $G(s)$; como ya se vio, la variable $s$ es la variable independiente, la cual puede ser real, imaginaria o compleja; es decir, en general, $s = \sigma + i\omega$. Esta variable se puede graficar en el plano $s$ de la forma que se muestra en la figura 7-30a. Al substituir el valor de $s$ en la función de transferencia $G(s)$, es posible obtener el valor de dicha función para una cierta $s$. Tal valor de $G(s)$, el cual puede ser real, imaginario o complejo, $G(s) = \sigma + i\gamma$, se puede graficar en el plano $G(s)$, como se muestra en la figura 7-30b. Para todo punto en el plano $s$, existe un punto correspondiente en el plano $G(s)$; es decir, con la función $G$ se puede llevar a cabo el mapeo del plano $s$ en el plano $G(s)$. Con la función $G$ no únicamente se logra el mapeo de los puntos, sino también las trayectorias o regiones.

Se utiliza la palabra "conformación" porque al realizar el mapeo, el plano $G(s)$ se "conforma" con el plano $s$. Para explicar el significado de esto, se supone que una trayectoria del plano $s$ se debe mapear en el plano $G(s)$; además, si en el plano $s$ la trayectoria tiene una vuelta marcada, al mapearla en el plano $G(s)$, también tendrá una vuelta marcada; esto es, el plano $G(s)$ se "conforma" con el plano $s$.

Para que sea más específico el concepto de mapeo de conformación, a continuación se considera la siguiente función de transferencia:

$$G(s) = \frac{10}{(2s + 1)(s + 1)}$$

En la figura 7-31 se muestra el mapeo de una región en el plano $s$, la cual se expresa con los puntos 1-2-3-4-1, y en el plano $G(s)$ por los puntos 1'-2'-3'-4'-1'. En la tabla 7-1 se muestra el manejo matemático con que se produce.

Ésta fue una explicación breve del mapeo de conformación y, como se mencionó antes, los diagramas polares se basan en dicha teoría. El mapeo de conformación también será importante cuando se presente el uso de los diagramas polares en el estudio de la estabilidad del control de proceso.

**Criterio de estabilidad de Nyquist.** Los diagramas polares son muy útiles para analizar la estabilidad de los circuitos de control de proceso. En esta sección se presenta el criterio de estabilidad de Nyquist, en el cual se utilizan tales diagramas. No se da ninguna prueba del teorema, sin embargo, se recomienda que el lector consulte el documento original. Puesto que el presente criterio se basa en la utilización de los diagramas polares, a éstos se les llama frecuentemente diagramas de Nyquist.

El criterio de Nyquist se puede enunciar como sigue:

> Un sistema de control de circuito cerrado es estable si al mapear la región R (la cual consiste en toda la mitad derecha del plano $s$, incluyendo el eje imaginario) en el plano $G(s)$, el plano de la función de transferencia de circuito abierto da por resultado la región R', en la cual no se incluye el punto $(-1,0)$.

El siguiente ejemplo demuestra la aplicación de este criterio.

**Ejemplo 7-14.** Se considera el circuito de control para el intercambiador de calor que se presentó en el capítulo 6 y que se utilizó en el ejemplo 7-4. En la figura 7-9 se muestra el diagrama de bloques de circuito cerrado para el circuito de control en cuestión, y la función de transferencia de circuito abierto es:

$$FTCA = \frac{0.8K_c}{(10s + 1)(30s + 1)(3s + 1)}$$

Con el criterio de Nyquist es preciso mapear todo el plano derecho (PD) del plano $s$, como se muestra en la figura 7-32, en el plano $G(s)$. Para una mejor apreciación el mapeo se divide en tres pasos.

**Paso 1.** La frecuencia $\omega$ va de 0 a $\infty$, sobre el eje imaginario positivo, y, por tanto, $s = i\omega$. Al substituir esta expresión de $s$ en la expresión de $G(s)$, se obtiene:

$$G(i\omega) = \frac{0.8K_c}{(i10\omega + 1)(i30\omega + 1)(i3\omega + 1)}$$

Entonces, el diagrama empieza con $\omega = 0$, sobre el eje real positivo, en el valor $0.8K_c$, y termina con $\omega \to \infty$, en el origen (RA = 0), con un ángulo de fase de $-270°$, como se muestra en la figura 7-33. La frecuencia a la que el lugar cruza el ángulo de $-180°$ se puede encontrar fácilmente mediante la solución de la ecuación (7-52). Una vez que se obtiene el valor de $\omega$, se puede calcular el valor de RA con la ecuación (7-51).

**Paso 2.** En este paso la frecuencia se mueve de $\omega = \infty$ a $\omega = -\infty$, a lo largo de la trayectoria que se muestra en la figura 7-32; en dicha trayectoria $s = re^{i\theta}$, $\theta$ va de $90°$ a $0°$ y a $-90°$. Al substituir tal expresión de $s$ en la expresión de $G(s)$, se tiene:

$$G(s) = \frac{0.8K_c}{(10re^{i\theta} + 1)(30re^{i\theta} + 1)(3re^{i\theta} + 1)}$$

Puesto que $r \to \infty$, entonces se puede despreciar el término $+1$ en cada paréntesis y:

$$\lim_{r \to \infty}G(i\omega) = \frac{0.8K_c}{(10re^{i\theta})(30re^{i\theta})(3re^{i\theta})} = \frac{1}{0.8K_c}\cdot\frac{1}{r^3e^{i3\theta}} \to 0$$

lo cual indica que el semicírculo con $r \to \infty$ se mapea en el plano $G(s)$ como un punto en el origen.

**Paso 3.** En este paso la frecuencia se mueve de $-\infty$ a 0, a lo largo del eje imaginario negativo y, por tanto, $s = -i\omega$. Nuevamente se substituye esta expresión de $s$ en la expresión de $G(s)$, para obtener:

$$G(-i\omega) = \frac{0.8K_c}{(-i10\omega + 1)(-i30\omega + 1)(-i3\omega + 1)}$$

El diagrama empieza en el origen, $\omega = -\infty$, y termina con $\omega = 0$, sobre el eje real positivo, en el valor $0.8K_c$, con un ángulo de fase de $0°$. La trayectoria se muestra en la figura 7-33.

Es interesante notar que el paso 3 es justamente la "imagen de espejo" del paso 1, lo cual es comprensible si se tiene en cuenta que $G(s)$ es una función compleja conjugada, lo que significa que el mapeo es simétrico, respecto al eje de las abscisas, en el plano $G(s)$.

En el paso 1 se explicó cómo se obtiene el valor de $K_{c_u}$ para un ángulo de fase de $-180°$, el cual es la distancia al origen en que la trayectoria cruza el eje real negativo. Si el punto de cruce está antes de $-1$, entonces el sistema es estable [en la región que se mapea no se incluye el punto $(-1,0)$]; si el punto de cruce está más allá de $-1$, entonces el sistema es inestable [en la región que se mapea se incluye el punto $(-1,0)$]. Conforme se incrementa $K_c$, también RA se incrementa, de lo que resulta un sistema menos estable. Esta afirmación es la misma que para el criterio de estabilidad de respuesta en frecuencia.

En esta sección se presentó una breve introducción a los diagramas polares y al criterio de estabilidad de Nyquist. Sin duda el lector notó la equivalencia entre el criterio de estabilidad de Nyquist y el de respuesta en frecuencia.

### Diagramas de Nichols

El diagrama de Nichols es otra manera de representar gráficamente la respuesta en frecuencia de los sistemas. Esencialmente es un diagrama de la razón de amplitud (o de magnitud) contra el ángulo de fase. En la figura 7-34 se muestra este tipo de diagrama para algunos sistemas típicos, en los cuales la frecuencia es el parámetro a lo largo de la curva.

### Resumen de la respuesta en frecuencia

Esta presentación de la respuesta en frecuencia fue más bien extensa y se esperaba mostrar la eficacia de la técnica. Las ecuaciones (7-39) y (7-40) son las ecuaciones generales para determinar RA y $\theta$; con ellas se puede realizar el análisis y diseño de los sistemas de control. Se mostraron diferentes formas de graficar la respuesta en frecuencia de los sistemas.

Una de las aplicaciones más prácticas e importantes de la respuesta en frecuencia es la utilización de la prueba de pulso para determinar la función de transferencia del proceso, instrumentos y otros dispositivos de control. Hougen describe varias aplicaciones de la prueba de pulso en la industria; en esta sección se describe la técnica respectiva y se deducen las fórmulas básicas que se requieren para su aplicación.

## 7-3. PRUEBA DE PULSO

En el capítulo 6 se estudió el método de la prueba escalón para determinar los parámetros del modelo de primer orden más tiempo muerto del proceso. Las ventajas de la prueba escalón son su simplicidad y los requerimientos mínimos de cálculo; su mayor desventaja es que, por precisión, se limita a los modelos de primer orden más tiempo muerto.

Con la técnica de prueba senoidal que se describió en la sección 7-2 es posible determinar, en principio, la función de transferencia de un proceso de cualquier orden. A pesar de que la prueba senoidal se utiliza extensamente en la determinación de las funciones de transferencia de sensores, transmisores y actuadores de válvulas de control, rara vez se utiliza para probar procesos reales, debido a que la mayoría de los procesos son muy lentos para la prueba senoidal. Si se considera un proceso donde la constante de tiempo más larga es de un minuto, en el diagrama de Bode del proceso la frecuencia de ruptura está, con base en la ecuación (7-42), en:

$$\omega_c = \frac{1}{\tau} = 1.0 \text{ rad/min}$$

Para localizar la asíntota de baja frecuencia del proceso se deben hacer al menos dos pruebas a frecuencias más bajas que la de ruptura; sean éstas 0.5 y 0.25 rad/min, el período de la segunda de estas señales senoidales es:

$$T = \frac{2\pi}{\omega} = \frac{2\pi}{0.25 \text{ rad/min}} = 25.1 \text{ min}$$

No sólo es difícil encontrar un generador de onda senoidal capaz de generar consistentemente una señal tan lenta, sino que la prueba tomaría al menos un par de horas, ya que se necesita completar un mínimo de cuatro o cinco ciclos para la prueba. Además, con la prueba se obtendría sólo un punto en el diagrama de Bode y, si la constante de tiempo del proceso fuera de 10 minutos, se tendría que aplicar al proceso una onda senoidal con período superior a 4 horas.

Con la prueba del pulso se produce un diagrama de Bode completo del proceso a partir de una sola prueba cuya duración es considerablemente menor a la de la prueba que se describe en el párrafo anterior. Puesto que no se puede obtener algo de nada, el ahorro de esfuerzo en pruebas se compensa por el esfuerzo adicional de cálculo.

### Realización de la prueba de pulso

El diagrama para la prueba de pulso es idéntico al que se da para la prueba senoidal en la figura 7-15, con la excepción de que, en lugar de la señal y respuesta senoidal de la figura 7-16, la señal de entrada es un pulso como el que aparece en la figura 7-35. Se notará que la duración de la respuesta, $T$, es mayor que la del pulso $T_D$. Los tres parámetros que se seleccionan para realizar la prueba de pulso son la forma del pulso, su amplitud y su duración.

A pesar de que el pulso rectangular de la figura 7-35 es el más fácil de generar y analizar, se utilizan otras formas de pulso, como las que aparecen en la figura 7-36; lógicamente, el pulso más popular es el rectangular, le sigue el pulso rectangular doble de la figura 7-36b. El único requisito para la forma del pulso es que debe regresar al valor inicial de estado estacionario.

Como en el caso de la prueba escalón y la senoidal, la amplitud del pulso, $X_0$, debe ser lo suficientemente grande como para que las mediciones de la respuesta sean exactas, pero no tan grande que la respuesta quede fuera del rango dentro del cual la función de transferencia lineal es una aproximación válida de la respuesta del proceso. Para satisfacer este requisito generalmente se necesita un dispositivo de registro muy sensible o una computadora digital en línea para registrar la respuesta.

La duración $T_D$ del pulso depende completamente de las constantes de tiempo del proceso que se prueba, y no debe ser tan corta como para que no haya tiempo de que el proceso reaccione o tan larga que haya tiempo para que la respuesta alcance el estado estacionario antes de que se complete el pulso. Un pulso tan largo no sólo representa una pérdida de tiempo de prueba, sino que también da por resultado una reducción en la frecuencia más alta para la cual son útiles los resultados de la prueba, como se verá en breve.

### Deducción de la ecuación de trabajo

La respuesta en frecuencia del proceso bajo prueba se determina mediante el cálculo de la función de transferencia compleja $G(i\omega)$, como una función de la frecuencia, de la respuesta del proceso al impulso de entrada. Para esto se utiliza la definición de la transformada de Fourier de una señal:

$$X(i\omega) = \int_{-\infty}^{\infty}x(t)e^{-i\omega t}dt \quad (7-55)$$

Al comparar la ecuación (7-55) con la (2-1), se ve que, con excepción del límite inferior en la integral, al substituir $s = i\omega$ en la definición de la transformada de Laplace, se puede obtener la transformada de Fourier. Puesto que las señales que interesan en el control de proceso son desviaciones del valor inicial de estado estacionario y, en consecuencia, son cero para un tiempo negativo, el límite inferior en la integral de la ecuación (7-55) se puede cambiar a cero. La transformada de Fourier se desarrolló antes que la transformada de Laplace, como una extensión de las series de Fourier para señales no periódicas.

Por definición, de la función de transferencia del proceso (ver capítulo 3):

$$G(s) = \frac{Y(s)}{X(s)} \quad (7-56)$$

donde:
- $Y(s)$ es la transformada de Laplace de la respuesta del proceso (como desviación de su valor inicial de estado estacionario)
- $X(s)$ es la transformada de Laplace del pulso

Se substituye $s = i\omega$ para encontrar:

$$G(i\omega) = \frac{Y(i\omega)}{X(i\omega)} \quad (7-57)$$

y se aplica la ecuación (7-55) a ambas señales para obtener:

$$G(i\omega) = \frac{\int_0^{\infty}y(t)e^{-i\omega t}dt}{\int_0^{\infty}x(t)e^{-i\omega t}dt} \quad (7-58)$$

La ecuación (7-58) es la ecuación de trabajo para calcular la respuesta en frecuencia del proceso bajo prueba. La integral en el numerador y denominador de la ecuación (7-58) se puede calcular con base en la respuesta y(t) y el pulso individual x(t) para cada valor de interés de la frecuencia $\omega$; el resultado del cálculo es un número complejo $G(i\omega)$; por lo tanto, la magnitud de este número es, de la ecuación (7-24), la razón de amplitud y, de la ecuación (7-25), se tiene que su argumento es el ángulo de fase a la frecuencia $\omega$. Se repiten los cálculos para varios valores de $\omega$ a fin de obtener el diagrama de Bode completo, con base en los resultados de una sola prueba.

La integral de la transformada de Fourier de la señal de salida del proceso $y(t)$ se debe calcular numéricamente, como se verá en breve. A pesar de que la integral del pulso, $x(t)$, también se puede calcular numéricamente, de la ecuación (7-55) se puede derivar una fórmula analítica, lo cual se ilustra en el siguiente ejemplo.

**Ejemplo 7-15.** Se debe obtener la transformada de Fourier de un pulso rectangular de amplitud $X_0$ y duración $T_D$ (ver figura 7-35).

**Solución.** Con base en la ecuación (7-55), se sabe que:

$$X(i\omega) = \int_0^{\infty}x(t)e^{-i\omega t}dt$$

Puesto que el pulso es cero en todo momento, excepto entre 0 y $T_D$, se puede decir que:

$$X(i\omega) = \int_0^{T_D}X_0e^{-i\omega t}dt = X_0\int_0^{T_D}e^{-i\omega t}dt$$
$$= -\frac{X_0}{i\omega}[e^{-i\omega T_D} - 1]$$
$$= \frac{X_0}{i\omega}[1 - e^{-i\omega T_D}]$$
$$= \frac{X_0}{i\omega}[\sin \omega T_D - i(1 - \cos \omega T_D)]$$

donde se utilizó la identidad:

$$e^{-i\omega T_D} = \cos \omega T_D - i\sin \omega T_D$$

y $1/i = -i$. La magnitud y argumentos de $X(i\omega)$ son:

$$|X(i\omega)| = \frac{X_0}{\omega}\sqrt{\sin^2 \omega T_D + (1 - \cos \omega T_D)^2}$$
$$= \frac{X_0}{\omega}\sqrt{2(1 - \cos \omega T_D)}$$

Con $\omega = 0$, $X(0) = X_0T_D$.

La magnitud del pulso es máxima en $\omega = 0$ y, por lo tanto, cae a cero conforme la frecuencia se incrementa a infinito; la magnitud también es cero en los valores de la frecuencia $\omega$, que son múltiplos de $\pi/T_D$ radianes/tiempo. Cuanto más larga es la duración del pulso, $T_D$, tanto más frecuentemente ocurren estos valores.

En el ejemplo precedente se observa que la magnitud máxima de la transformada de Fourier de un pulso rectangular es proporcional al área del pulso, $X_0T_D$. Puesto que la transformada de Fourier del pulso aparece en el denominador de la ecuación (7-57), es deseable evitar los valores de $\omega$ donde la transformada es cero, con lo que se impone un límite superior al rango de frecuencias para las cuales, mediante la prueba de pulso, se puede calcular la respuesta en frecuencia. Para el pulso rectangular la frecuencia es $\pi/T_D$, la cual, como se mencionó antes, decrece con la duración del pulso, $T_D$.

### Evaluación numérica de la integral de la transformada de Fourier

Normalmente, la evaluación de la integral del numerador de la ecuación (7-58) se hace de manera numérica, para ello se utiliza una computadora digital. Una técnica eficiente y exacta para lograr la integración numérica es la que tiene como base la regla trapezoidal. Los cálculos se deben realizar con aritmética de números complejos (ver sección 2-4), a causa del término exponencial complejo. Con la mayoría de los lenguajes de programación, como el FORTRAN, es posible realizar operaciones con números complejos.

Para realizar la integración numérica de la función $y(t)$, primero se debe dividir ésta en $N$ incrementos de tiempo de $\Delta t$, como se muestra en la figura 7-37. Se puede suponer que los incrementos son de duración uniforme de $\Delta t$, sin embargo, esto no es necesario en la práctica. La regla trapezoidal para integración numérica consiste en aproximar la función con una línea recta dentro de cada intervalo:

$$Y(i\omega) = \int_0^{T}y(t)e^{-i\omega t}dt \approx \sum_{k=0}^{N-1}\int_{t_k}^{t_{k+1}}y(t)e^{-i\omega t}dt \quad (7-59)$$

donde:
- $y_k$ es la respuesta en el tiempo $k\Delta t$
- $N = T/\Delta t$ es la cantidad de incrementos

Al escribir la ecuación (7-59) se supuso que la respuesta para tiempo negativo era cero y que retornaba a cero después de $N$ incrementos, esto es posible porque $y$ es la desviación del valor inicial de estado estacionario. Al integrar por partes la ecuación (7-59) y simplificar, se obtiene:

$$Y(i\omega) = \frac{1}{\omega^2\Delta t}\sum_{k=0}^{N-1}(y_{k+1} - y_k)(1 - e^{-i\omega\Delta t})e^{-i\omega k\Delta t} \quad (7-60)$$

Esta fórmula se puede simplificar más si se toma en cuenta el hecho de que $y_0$ y $y_N$ son cero:

$$Y(i\omega) = \frac{1}{\omega^2\Delta t}(1 - e^{-i\omega\Delta t})\sum_{k=0}^{N-1}y_ke^{-i\omega k\Delta t} \quad (7-61)$$

De las identidades trigonométricas apropiadas, resulta la siguiente fórmula de trabajo:

$$Y(i\omega) = \frac{e^{-i\omega\Delta t/2}}{\omega^2\Delta t}\left[2i\sin\frac{\omega\Delta t}{2}\right]\sum_{k=0}^{N-1}y_ke^{-i\omega k\Delta t} \quad (7-62)$$

Esta fórmula se puede programar directamente en FORTRAN o en otro lenguaje de computadora de alto nivel. Se ve que la ecuación (7-62) es muy eficiente, ya que para cada frecuencia de interés únicamente se necesita realizar una vez la evaluación de la función seno, la cual consume tiempo.

Cuando se calcula numéricamente la transformada de Fourier tanto de la respuesta de la salida como del pulso de entrada, se hace la substitución en el numerador y denominador de la ecuación (7-57), de lo que resulta la siguiente fórmula para la función de transferencia del proceso:

$$G(i\omega) = \frac{\sum_{k=0}^{N-1}y_ke^{-i\omega k\Delta t}}{\sum_{k=0}^{M-1}x_ke^{-i\omega k\Delta t}} \quad (7-63)$$

donde $M$ es la cantidad de incrementos que se utilizan para integrar el pulso ($M = T_D/\Delta t$).

En la ecuación (7-63) se supone que se utiliza el mismo intervalo de integración para el numerador y el denominador. Cuando la transformada de Fourier de un pulso se puede calcular a partir de una fórmula analítica como la que se dedujo en el ejemplo 7-15, generalmente es mejor utilizar dicha fórmula en lugar de la ecuación (7-63); en tal caso, la transformada de Fourier de la respuesta de la salida se calcula con base en la ecuación (7-62), y la función de transferencia, con base en la ecuación (7-57). Tales cálculos se deben repetir para cierta cantidad de valores de la frecuencia $\omega$, con el fin de generar el diagrama de Bode del proceso. Puesto que se desea que la separación de los puntos en el diagrama de Bode sea igual sobre el eje logarítmico de frecuencia, cada frecuencia que se elija debe ser un factor constante de la anterior:

$$\omega_i = \omega_{min}\left(\frac{\omega_{max}}{\omega_{min}}\right)^{i/N_f}, \quad i = 1, 2, \ldots, N_f$$

donde:
- $\omega_{max}$ es el límite superior del rango de frecuencia en el diagrama de Bode, rad/tiempo
- $\omega_{min}$ es el límite inferior del rango de frecuencia en el diagrama de Bode, rad/tiempo
- $N_f$ es la cantidad de incrementos en que se divide el rango de frecuencia

Mediante el procedimiento que se acaba de describir es posible obtener el diagrama de Bode completo a partir de una sola prueba de pulso, siempre y cuando tanto el pulso de entrada como la respuesta de la salida regresen a sus valores iniciales. Puesto que las variables $y(t)$ y $x(t)$ son desviaciones de las condiciones iniciales de estado estacionario, al inicio valen cero y, para que $y(t)$ vuelva a cero, las condiciones finales de estado estacionario deben ser las mismas que las iniciales. Este último requerimiento no se cumple cuando en el proceso existe un elemento de integración; este caso se verá próximamente.

**Procesos con integración.** En la figura 7-38 se muestra la respuesta a la entrada de un pulso de un proceso con integración. El valor final de estado estacionario de la variable de desviación a la salida es proporcional a la integral del pulso de entrada:

$$Y_{\infty} = K_I\int_0^{T_D}x(t)dt \quad (7-65)$$

Luyben propuso tratar al proceso como si consistiera en un integrador puro con ganancia $K_I$, en paralelo con un proceso ficticio con función de transferencia $G_A(s)$, de manera que la función de transferencia del proceso real es:

$$G(s) = G_A(s) + \frac{K_I}{s} \quad (7-66)$$

La salida del integrador se expresa por:

$$Y_I(t) = K_I\int_0^t x(t)dt \quad (7-67)$$

Entonces, la salida del proceso ficticio se expresa con:

$$Y_A(t) = y(t) - Y_I(t) \quad (7-68)$$

La señal $y_A$ es cero en el tiempo inicial y final, como se ilustra en la figura 7-38; y $y_A(t)$ se puede calcular con base en las ecuaciones (7-67) y (7-68), y entonces se utiliza el resultado en las ecuaciones (7-62) y (7-57) para calcular $G_A(i\omega)$; por lo tanto, a partir de la ecuación (7-66), la función de transferencia del proceso es:

$$G(i\omega) = G_A(i\omega) + \frac{K_I}{i\omega} \quad (7-69)$$

La ganancia $K_I$ del integrador se calcula con la ecuación (7-65).

En esta sección se perfiló el método de prueba de pulso para determinar experimentalmente la función de transferencia de un proceso. Luyben expone un programa de computadora para generar los datos del diagrama de Bode a partir de los datos de respuesta a un pulso, y Hougen presenta varias aplicaciones industriales exitosas de la prueba de pulso.

## 7-4. RESUMEN

En este capítulo se presentaron dos técnicas para el análisis y diseño de sistemas de control por retroalimentación: lugar de raíz y respuesta en frecuencia. Ambas son excelentes para representar gráficamente la respuesta de los sistemas de control; de los dos, la respuesta de frecuencia es con la que se puede manejar la presencia de tiempo muerto sin hacer una aproximación. La respuesta en frecuencia también sirve como base para determinar cuantitativamente los parámetros dinámicos del proceso que se utilizan en el método de prueba de pulso. Como se vio en este capítulo, a partir de los resultados de una sola prueba de pulso es posible determinar la respuesta en frecuencia completa.

Ya que se estudió el diseño y análisis de los sistemas de control por retroalimentación, a continuación se abordarán otras técnicas importantes de control, las cuales se usan comúnmente en la industria. Éste es el tema del próximo capítulo.

## BIBLIOGRAFÍA

1. Nyquist, H., "Regeneration Theory," *Bell System Technical Journal*, Vol. 11 (1932), pp. 126-147.
2. Hougen, Joel O., "Experiences and Experiments with Process Dynamics," *CEP Monograph Series*, Vol. 60, No. 4, AIChE, Nueva York, 1964.
3. Luyben, William L., *Process Modeling, Simulation, and Control for Chemical Engineers*, McGraw-Hill, Nueva York, 1973, sección 9-3.

## PROBLEMAS

**7-1.** Se debe dibujar el diagrama de lugar de raíz para cada una de las siguientes funciones de transferencia de circuito abierto (se utilizará una aproximación de Padé para el término de tiempo muerto):

a) $G(s) = \frac{K}{(s+1)(2s+1)(10s+1)}$
b) $G(s) = \frac{K}{(s+1)(2s+1)(10s+1)}$
c) $G(s) = \frac{K}{(s+1)(2s+1)(10s+1)}$
d) $G(s) = \frac{K(s+1)e^{-s}}{(s+1)(2s+1)(10s+1)}$

**7-2.** Dibujar el diagrama de lugar de raíz para cada una de las siguientes funciones de transferencia de lazo abierto:

a) $G(s) = \frac{K}{s(s+1)(4s+1)}$
b) $G(s) = \frac{K(s+1)}{(2s+1)}$

**7-3.** Ahora se considera la siguiente función de transferencia para un cierto proceso:

$$G(s)H(s) = \frac{1.5}{(s+1)(5s+1)(10s+1)}$$

a) Se debe ajustar un controlador proporcional para un margen de ganancia de 2.
b) Se debe determinar el factor de amortiguamiento, $\xi$, para la respuesta oscilatoria del circuito de control mediante la utilización del parámetro de ajuste que se obtuvo en la parte (a).

**7-4.** Se debe dibujar el diagrama de lugar de raíz para las siguientes dos funciones de transferencia de circuito abierto:

a) Sistema con respuesta inversa:
$$G(s) = \frac{K(1 - 0.25s)}{(2s+1)(s+1)}$$

b) Sistema inestable de circuito abierto:
$$G(s) = \frac{K}{(\tau_1s+1)(1 - \tau_2s)}$$
para los casos:
- $\tau_1 = 2, \tau_2 = 1$
- $\tau_1 = 1, \tau_2 = 1$

**7-5.** Ahora se considera el sistema de control de proceso que se muestra en la figura 7-39; la presión en el tanque se expresa por:

$$\frac{P(s)}{F(s)} = \frac{0.4}{(0.15s+1)(0.8s+1)} \text{ psi/scfm}$$

La descripción de la válvula se puede hacer mediante la siguiente función de transferencia:

$$\frac{F(s)}{M(s)} = \frac{5}{0.1s+1} \text{ scfm/psi}$$

El rango del transmisor de presión es de 0 psig a 30 psig y la dinámica del transmisor es despreciable.

a) Dibujar el diagrama de bloques para este sistema e incluir todas las funciones de transferencia.
b) Se debe esbozar el diagrama de lugar de raíz.
c) Se debe determinar la ganancia del controlador en el punto de ruptura.
d) Se debe determinar la ganancia última y el período último.
e) Calcular el parámetro de ajuste de un controlador P con el que se obtenga un factor de amortiguamiento de 0.707.
f) Explicar gráficamente la forma en que la adición de la acción de reajuste al controlador afecta a la estabilidad del circuito de control.
g) Explicar gráficamente la forma en que afecta a la estabilidad del circuito de control el añadir acción derivativa al controlador PI del inciso f).

**7-6.** Se repite el problema 7-3 con la siguiente función de transferencia:

$$G(s)H(s) = \frac{1.5e^{-0.5s}}{(5s+1)(10s+1)}$$

**7-7.** Para el proceso que aparece en el problema 6-20, se debe elaborar el diagrama de lugar de raíz, para ello se utilizará una aproximación de Padé de primer orden, como se ve en la ecuación (6-29), a fin de aproximar el término de tiempo muerto.

**7-8.** Para las funciones de transferencia del problema 7-1, se deben dibujar las asíntotas del diagrama de Bode de razón de magnitud (o de la razón de amplitud) y graficar a grandes rasgos el diagrama del ángulo de fase.

**7-9.** Se debe repetir el problema 7-8 para las funciones de transferencia del problema 7-2.

**7-10.** Para las siguientes funciones de transferencia:

a) $G(s) = \frac{s+1}{s+1}$
b) $G(s) = \frac{(2s+1)}{(2s+1)(s+1)}$

a) Esbozar las asíntotas de la parte de razón de magnitud del diagrama de Bode, marcando las frecuencias de ruptura.
b) Indicar el retardo de fase (o adelanto) para frecuencias altas ($\omega \to \infty$).

**7-11.** Se debe graficar el diagrama de Bode para las funciones de transferencia que aparecen en el problema 7-4.

**7-12.** En la figura 7-40 se muestra el diagrama de Bode de un sistema de circuito abierto; se debe obtener la función de transferencia de este sistema. ¿Qué ganancia del controlador se puede tolerar si se desea un margen de ganancia de 2? ¿Cuál es el margen de fase con una ganancia de controlador de 0.6?

**7-13.** Ahora se considera el proceso de filtro de vacío que aparece en la figura 6-30. En este proceso se utilizan los datos del problema 6-15 y se aplican las técnicas de respuesta en frecuencia para:

a) Graficar las asíntotas del diagrama de Bode y el diagrama del ángulo de fase.
b) Obtener la ganancia última, $K_{c_u}$, y el período último, $T_u$.
c) Ajustar el tiempo de reajuste de un controlador PI mediante el método de síntesis del controlador y determinar la ganancia del controlador con la cual se logra un margen de ganancia de 2.

**7-14.** Para este problema se considera el absorbedor que se presentó en el problema 6-16; en la parte (a) de ese problema se diseñó un circuito de control por retroalimentación con el fin de controlar la concentración de amoniaco a la salida. Para dicho circuito de control se debe:

a) Dibujar las asíntotas del diagrama de Bode y del diagrama de ángulo de fase.
b) Obtener la ganancia última, $K_{c_u}$, y el período último, $T_u$.
c) Ajustar un controlador P para un margen de fase de $45°$.

**7-15.** Ahora se considera el diagrama de bloques que aparece en la figura 7-41a, en el cual la entrada $N(s)$ representa el ruido con que se contamina a la señal de salida; si tal ruido del proceso es significativo, se puede dificultar el control de proceso. Generalmente, para mejorar el control en procesos ruidosos se filtra la señal que se retroalimenta; una manera típica de filtrar las señales es mediante un dispositivo de filtraje con una función de transferencia de primer orden. Este dispositivo, ya sea neumático, electrónico o digital, se instala entre el transmisor y el controlador, como se muestra en la figura 7-41b; la ganancia del filtro es uno (1) y la constante de tiempo, que se conoce como constante de tiempo del filtro, es $\tau_f$. Se deben utilizar las técnicas de respuesta en frecuencia para explicar la forma en que $\tau_f$ afecta al filtraje de la señal ruidosa y al desempeño del circuito de control. Se debe graficar, específicamente, el margen de ganancia como una función de $\tau_f$.

**7-16.** Ahora se considera un proceso térmico con la siguiente función de transferencia para la salida del proceso contra la señal que sale del controlador:

$$\frac{C(s)}{M(s)} = \frac{0.65e^{-0.35s}}{(5.1s+1)(1.2s+1)}$$

Al proceso se le aplica una onda senoidal de amplitud unitaria y frecuencia 0.80 rad/min; las constantes de tiempo y el tiempo muerto están en minutos. Se debe calcular la amplitud y el retardo de fase de la onda senoidal que sale del proceso después de que cesa la respuesta transitoria.

**7-17.** Con el pulso rectangular simétrico que se muestra en la figura 7-42 se tiene la ventaja de poder promediar el efecto de las alinealidades sobre el resultado de la prueba dinámica.

a) Se debe deducir la transformada de Fourier para el pulso, $Q(i\omega)$.
b) Se deben escribir las fórmulas para la magnitud, $|Q(i\omega)|$, y el ángulo de fase, $\angle Q(i\omega)$, como funciones de la frecuencia.

**7-18.** Para la prueba pulso de un proceso se utiliza un pulso rampa de duración $T_D$ y amplitud final $x_0$. Se debe determinar la integral de la transformada de Fourier del pulso.

**7-19.** En un proceso, el diagrama de razón de amplitud contra frecuencia da por resultado la gráfica que aparece en la figura 7-43. En el diagrama de ángulo de fase no se alcanza una asíntota de alta frecuencia, pero se vuelve más negativo conforme se incrementa la frecuencia. Con una frecuencia de 1.0 rad/min, el ángulo de fase es de -246 grados. Se debe postular una función de transferencia para el proceso y estimar la ganancia, las constantes de tiempo y el tiempo muerto, si lo hay.

**7-20.** El diagrama de Bode que aparece en la figura 7-44 se obtuvo para la función de transferencia de temperatura contra razón de agua para enfriamiento en un reactor tubular, mediante el método de prueba de pulso. Se debe determinar:

a) La ganancia de estado estacionario del proceso.
b) La constante de tiempo.
c) Una estimación del tiempo muerto en el sistema.

**7-21.** Para los cuatro pulsos que aparecen en la figura 7-35, se debe obtener la transformada de Fourier, la razón de magnitud y el ángulo de fase.

---

# Capítulo 8: Técnicas adicionales de control

En los capítulos anteriores se hizo énfasis principalmente en el control de los procesos mediante la técnica que se conoce como control por retroalimentación. En el capítulo 1 se expusieron los principios de dicha técnica, junto con algunas de sus ventajas y desventajas; en el capítulo 5 se presentaron los componentes básicos y el equipo (hardware) necesario para estructurar un sistema de control; finalmente, en los capítulos 6 y 7 se hizo la presentación, estudio y aplicación práctica de las diferentes técnicas para diseñar y analizar los sistemas de control con circuito sencillo de retroalimentación. Como se mencionó en el capítulo 1, el control por retroalimentación es la técnica que más comúnmente se utiliza en las industrias de proceso.

En muchos procesos, mediante la aplicación de otras técnicas de control, es posible y ventajoso mejorar el desempeño logrado con el control por retroalimentación. En este capítulo se tiene como objetivo presentar algunas de las técnicas que se han desarrollado, y frecuentemente utilizado, con el fin de mejorar el desempeño del control que se logra por medio del control por retroalimentación. Para estas técnicas se requiere una mayor cantidad de ingeniería y equipo que en el control por retroalimentación solo y, en consecuencia, es de suponerse que, antes de aplicar tales técnicas, se requiera realizar un estudio de factibilidad técnica económica.

Las técnicas que se presentan en el presente capítulo son: control de razón, control en cascada, control por acción precalculada, control por sobreposición, control selectivo y control multivariable. A lo largo del capítulo se muestran muchos ejemplos industriales reales, a fin de ayudar al lector a comprender los principios y aplicación de las técnicas.

Para la implementación de las técnicas que se presentan en este capítulo se requiere cierta capacidad de cómputo, que en el pasado se obtuvo mediante la utilización de relés de cómputo, ya fuera neumáticos o eléctricos. En los últimos años, con el advenimiento de las micro, mini o computadoras de gran escala, se reemplazaron muchos de estos relés de cómputo analógicos. El capítulo se inicia con el estudio de los relés de cómputo analógicos y de los bloques de cómputo con base en microprocesadores.

## 8-1. RELÉS DE CÓMPUTO

Como ya se mencionó, para estructurar las técnicas que se presentan en este capítulo se requiere cierta capacidad de cómputo, la cual generalmente se obtiene mediante la utilización de relés de cómputo, ya sea neumáticos o eléctricos, o bloques de cómputo con base en microprocesadores. Los relés son cajas negras en las que se realiza algún manejo matemático de las señales; en software, los bloques son el equivalente de los relés. Algunos de los manejos típicos que se pueden realizar con estos relés de cómputo analógicos o bloques de cómputo son los siguientes:

1. **Adición/substracción.** La señal que se obtiene a la salida es la adición o substracción de las señales de entrada.
2. **Multiplicación/división.** La señal de salida es el producto o el cociente de las señales de entrada, o ambos.
3. **Raíz cuadrada.** La señal de salida es la extracción de la raíz cuadrada de la señal de entrada.
4. **Selector de alto/bajo.** La señal de salida es la máxima/mínima de dos o más señales de entrada.
5. **Limitador de alto/bajo.** La señal de salida es la señal de entrada que se limita a un valor máximo/mínimo precalculado.
6. **Generador de función.** La señal de salida es una función de la señal de entrada. Esta función generalmente se aproxima mediante una serie de líneas rectas.
7. **Integrador.** La señal de salida es la integral, en tiempo, de la señal de entrada. Para el integrador se usan otros términos, como el de "totalizador".
8. **Retardo lineal.** La señal de salida es la solución de una ecuación diferencial de primer orden cuya función de forzamiento es la señal de entrada; dicho cálculo se describe en forma matemática como sigue:

$$\tau\frac{dV_0}{dt} + V_0 = V_i$$

Este cálculo se utiliza frecuentemente para filtrar una señal ruidosa; la cantidad de filtración depende de la constante de tiempo $\tau$; mientras más grande es la constante de tiempo, mayor es la filtración que se hace.

9. **Adelanto/retardo.** La señal de salida es la siguiente función de transferencia:

$$\frac{V_0(s)}{V_i(s)} = \frac{\tau_ds + 1}{\tau_ls + 1}$$

Esta ecuación es la misma que la ecuación (4-78), su comportamiento y el significado de $\tau_d$ y $\tau_l$ se explicaron en el capítulo 4. Este cálculo se utiliza frecuentemente en los planes de control como el control con acción precalculada, en el cual se requiere compensación dinámica.

Con el advenimiento de los sistemas de control con base en microprocesadores se incrementó tremendamente la disponibilidad de manejos matemáticos más complejos; en la tabla 8-1 se ilustran algunas de las ecuaciones que se resuelven mediante los relés de cómputo electrónicos de un fabricante; en las tablas 8-2 y 8-3 se muestran algunas de las ecuaciones que se resuelven mediante dos sistemas de control basados en microprocesadores diferentes. Es interesante notar que en todos los casos las constantes se limitan dentro de algunos valores prefijados y, puesto que se limita a las constantes, éstas se deben elegir de modo que el cálculo matemático requerido se realice de manera correcta. En esta sección se muestra la manera de elegir los valores de las constantes, lo cual también se conoce como "escalamiento" y que es necesario para asegurar la compatibilidad entre la señal de entrada y la de salida.

El método que se utiliza para escalar se conoce como **método de escala unitaria**; su utilización es muy simple y se aplica igualmente a los instrumentos analógicos, neumáticos o eléctricos, así como a los sistemas con base en microprocesadores. El método consta de los tres pasos siguientes:

1. La ecuación a resolver se escribe junto con el rango de cada variable del proceso, a cada una de las cuales se le asigna un nombre de señal.
2. Cada variable del proceso se relaciona con su nombre de señal mediante una ecuación normalizada.
3. El sistema de ecuaciones normalizadas se substituye en la ecuación original y se resuelve para la señal de salida.

A continuación se muestra la aplicación de este método mediante un ejemplo típico.

**Ejemplo 8-1.** Se supone que se necesita calcular la razón de flujo de masa de un cierto gas que fluye a través de una tubería de proceso, como se muestra en la figura 8-1, donde se aprecia un orificio en la tubería. En el apéndice C se presenta una ecuación simple para calcular la masa que fluye a través de un orificio, ésta es:

$$\dot{m} = K[hp]^{1/2}$$

donde:
- $\dot{m}$ = flujo de masa, lbm/h
- $h$ = presión diferencial a través del orificio, pulg H₂O
- $p$ = densidad del gas, lbm/pies³
- $K$ = coeficiente del orificio

La densidad del gas próxima a las condiciones de operación se expresa mediante la siguiente ecuación linealizada (ver ejemplo 2-13):

$$p = 0.13 + 0.003(P - 30) - 0.00013(T - 500)$$

Entonces, la ecuación con que se obtiene el flujo de masa es:

$$\dot{m} = K[h(0.13 + 0.003(P - 30) - 0.00013(T - 500))]^{1/2} \quad (8-3)$$

El rango de las variables para este proceso es el siguiente:

| Señal | Variable | Rango | Estado estacionario |
|-------|----------|-------|---------------------|
| S1 | h | 0-100 pulg H₂O | 50 pulg |
| S2 | T | 300-700°F | 500°F |
| S3 | P | 0-50 psig | 30 psig |
| S4 | $\dot{m}$ | 0-700 lbm/hr | 500 lbm/hr |

El coeficiente del orificio es $K = 196.1$ lbm/[h(pulg-lbm/pies³)$^{1/2}$].

La ecuación (8-3) y los rangos anteriores constituyen el paso 1 del método de escala unitaria. Esta información la debe conocer el ingeniero de proceso; se notará que a cada variable del proceso se le asigna un nombre de señal.

En el paso 2 se necesita relacionar, mediante una ecuación normalizada, cada variable de proceso con su nombre de señal, lo cual significa que, conforme la variable de proceso varía entre los valores máximo y mínimo del rango, la señal debe variar entre los valores 0 y 1; una ecuación simple para cumplir con esto es:

$$\text{Señal} = \frac{\text{Variable del proceso} - \text{Valor inferior del rango}}{\text{Rango}} \quad (8-4)$$

Al aplicar esta ecuación, se obtiene:

$$S1 = \frac{h}{100} \quad \Rightarrow \quad h = 100S1 \quad (8-5)$$
$$S2 = \frac{T - 300}{400} \quad \Rightarrow \quad T = 300 + 400S2 \quad (8-6)$$
$$S3 = \frac{P}{50} \quad \Rightarrow \quad P = 50S3 \quad (8-7)$$

Y:

$$S4 = \frac{\dot{m}}{700} \quad \Rightarrow \quad \dot{m} = 700S4 \quad (8-8)$$

Finalmente, de acuerdo con el paso 3, se substituyen las ecuaciones anteriores, de la (8-5) a la (8-8), en la ecuación (8-3) y se resuelve para la señal de salida S4:

$$700S4 = 196.1[100S1(0.13 + 0.003(50S3 - 30) - 0.00013(300 + 400S2 - 500))]^{1/2}$$

Mediante la utilización del álgebra se simplifica esta ecuación a:

$$S4 = 1.08[S1(S3 - 0.35S2 + 0.44)]^{1/2} \quad (8-9)$$

Ésta es la ecuación normalizada que se debe componer con los relés o bloques de cómputo.

Ahora se utilizan los relés de cómputo de la tabla 8-1 para formar la ecuación (8-9). Puesto que esta ecuación no se puede formar con un solo relé, se hace por partes; en la primera se calcula el término entre paréntesis y para ello se utiliza una unidad de adición/substracción, como sigue:

$$V_0' = (S3 - 0.35S2) + 0.44$$

Sea $V_1 = S3$, $V_2 = S2$ y $V_3 = 0$; entonces, al igualar las dos últimas ecuaciones, se obtiene:

$$a_0 = 1; \quad a_1 = 1; \quad a_2 = 0; \quad a_3 = 0.35; \quad B_0 = 0.44$$

El signo que se elige para $a_1$ debe ser positivo, y para $a_3$, negativo. Ahora se multiplica la salida de esta primera unidad por la señal S1 y por el factor $(1.08)^2$:

$$V_0 = a_0(a_1V_1V_2) + B_0$$

O:

$$V_0 = (1.08)^2(S1)V_0'$$

Sea $V_1 = S1$ y $V_2 = V_0'$; entonces, al igualar las dos últimas ecuaciones, se tiene:

$$a_0a_1 = \frac{(1.08)^2}{4} = 0.292; \quad B_0 = 0$$

Finalmente se extrae la raíz cuadrada de la señal que sale de este último relé. En la figura 8-2 se muestra el diagrama de bloques de los instrumentos que se requiere emplear.

La señal que sale de FYSC, el extractor de raíz, se relaciona linealmente con el flujo de masa de gas. Conforme el flujo de masa varíe entre 0 y 700 lbm/h, la señal variará entre 4 y 20 mA; ahora se puede utilizar esta señal para realizar cualquier función de control o de registro.

Se notará que en la figura 8-1 las señales se representan con líneas continuas para hacer énfasis en la aplicación del método de escala unitaria, independientemente del tipo de señal. Cuando se hace el escalamiento, no es necesario especificar si la señal es eléctrica, neumática o digital, el método de escala unitaria se aplica de la misma forma a las tres y en esto estriba la eficacia del mismo.

Para completar el ejemplo, ahora se muestra la implementación en el sistema con base en microprocesadores que aparece en la tabla 8-2. La ecuación que se debe formar también es la (8-9), pero antes de hacer la implementación se notará que en la tabla 8-2 se especifica que las señales de entrada y salida deben estar expresadas en porcentaje de rango; en la ecuación (8-9) las señales S1, S2, S3 y S4 son fracciones de rango que resultan del método de escala unitaria y, por tanto, primero se deben convertir a porcentaje de rango las señales, lo cual se hace fácilmente al multiplicar ambos lados de la ecuación (8-9) por 100%:

$$100(S4) = 1.08(100)[S1(S3 - 0.35S2 + 0.44)]^{1/2}$$
$$100(S4) = 1.08[100S1(100S3 - 0.35(100)S2 + 44)]^{1/2}$$
$$S4' = 1.08[S1'(S3' - 0.35S2' + 44)]^{1/2}$$

Ahora todas las señales, S1', S2', S3' y S4', están en porcentaje de rango.

Al igual que antes, primero se implementa el término entre paréntesis. Se utiliza el bloque sumador:

$$OUT = K_1X + K_2Y + K_3Z + B_0$$

El término es:

$$OUT' = S3' - 0.35S2' + 44$$

Sea $X = S3'$ y $Y = S2'$; la entrada $Z$ no se utiliza. De igualar las dos ecuaciones anteriores se obtiene entonces:

$$K_1 = 1; \quad K_2 = -0.35; \quad K_3 = 0; \quad B_0 = 44\%$$

El siguiente bloque se utiliza para completar la implementación:

$$OUT = K_4\sqrt{XY} + B_0$$

La ecuación que se debe implementar es:

$$S4' = 1.08\sqrt{S1'\cdot OUT'}$$

Sea $X = S1'$ y $Y = OUT'$. Puesto que la entrada $Z$ no se necesita, se le fija manualmente a un valor de 1% y, entonces, se igualan las dos últimas ecuaciones para obtener:

$$K_4 = 1.08; \quad B_0 = 0\%$$

De manera que, al utilizar este sistema con base en microprocesadores, se ahorra una manipulación, únicamente se requieren dos bloques. Como se mencionó anteriormente, los sistemas con base en microprocesadores generalmente cuentan con una capacidad de cómputo mayor que la de los instrumentos analógicos; además, con estos sistemas la fijación de las constantes se hace más rápido y con más precisión.

Como se vio, el método de escala unitaria es simple y eficaz. Es importante subrayar nuevamente que, cuando se utiliza este método, no es necesario considerar si se trabaja con relés analógicos, eléctricos o neumáticos, o con bloques de cómputo; el método se aplica de igual manera a todos ellos como resultado de la normalización. Por ejemplo, en el caso que se presentó anteriormente, el flujo de estado estacionario es una fracción de 0.714 (500/700) del rango de la señal; si se utiliza instrumentación neumática, la salida de estado estacionario del último relé sería de 11.57 psig, lo cual resulta de $3 + 0.714(12)$; si se utiliza instrumentación electrónica, la salida de estado estacionario del último relé, FYSC en la figura 8-2, sería de 15.42 mA; si se utiliza un sistema con base en microprocesadores, la salida de estado estacionario del último bloque sería una fracción de 0.714 del rango más el valor cero.

Antes de concluir esta sección es conveniente un comentario final: siempre es importante revisar la ecuación normalizada, ecuación (8-9), antes de la implementación, lo cual se hace fácilmente si se utilizan los valores de estado estacionario. Por ejemplo, los valores de estado estacionario de las señales, con base en las ecuaciones normalizadas, son:

$$S1 = 0.5; \quad S2 = 0.5; \quad S3 = 0.6; \quad S4 = 0.714$$

Al substituir S1, S2 y S3 en la ecuación (8-9), se obtiene:

$$S4 = 1.08[0.5(0.6 - 0.35(0.5) + 0.44)]^{1/2}$$
$$S4 = 0.710$$

La diferencia entre este valor calculado de S4 y el que se obtiene de la ecuación normalizada es pequeño (5%) y se debe principalmente a error de truncamiento; ciertamente, en procesos de gran volumen aun este error se puede hacer significativo, lo cual puede ser un incentivo para utilizar computadoras, ya que tienen mejor precisión que los instrumentos analógicos. Sin embargo, se debe recordar que, en el campo de la instrumentación, los sensores y transmisores son aun analógicos y con limitaciones de precisión.

En las secciones siguientes se presentan varias técnicas de control con las que se mejora el desempeño de control logrado mediante el control por retroalimentación. En los diagramas con que se ilustra la implementación se utilizan símbolos de instrumentación analógica. Sin embargo, el lector debe recordar que la implementación se puede hacer mediante sistemas con base en microprocesadores; además, con la utilización de estos nuevos sistemas se simplifica en gran medida la implementación. Los principios de las técnicas que se presentan son los mismos, no importa qué tipo de sistema se utilice para implementarlas.

## 8-2. CONTROL DE RAZÓN

Una técnica de control muy común en los procesos industriales es el control de razón. En esta sección se presentan dos casos industriales de control de razón para ilustrar el significado y la implementación. El primer caso es simple, pero con él se explica claramente la necesidad del control de razón.

Para ordenar las ideas expuestas, se supone que se deben mezclar dos corrientes de líquidos, A y B, en cierta proporción o razón, R, esto es:

$$\frac{B}{A} = R$$

El proceso se muestra en la figura 8-3. En la figura 8-4 se expone una manera fácil de cumplir con dicha tarea; cada flujo se controla mediante un circuito de flujo en el cual el punto de control de los controladores se fija de manera tal que los líquidos se mezclan en la proporción correcta. Sin embargo, si ahora se supone que no se puede controlar uno de los flujos (la corriente A), sino únicamente medirlo, flujo que se conoce como "flujo salvaje", se maneja generalmente para controlar alguna otra cosa, por ejemplo, el nivel o la temperatura corriente arriba, y, por lo tanto, ahora la tarea de control es más difícil. De alguna manera, la corriente B debe variar conforme varía la corriente A, para mantener la mezcla en la razón correcta; en la figura 8-5 se muestran dos esquemas posibles de control de razón.

El primer esquema, el cual aparece en la figura 8-5a, consiste en medir el flujo salvaje y multiplicarlo por la razón que se desea (en FY 102B) para obtener el flujo que se requiere de la corriente B. Esto se expresa matemáticamente como sigue:

$$B = RA$$

La salida del multiplicador o estación de razón, FY102B, es el flujo que se requiere de la corriente B y, por lo tanto, ésta se utiliza como punto de control para el controlador de la corriente B, FIC101; de manera que, conforme varía la corriente A, el punto de control del controlador de la corriente B variará en concordancia con aquélla para mantener ambas corrientes en la razón que se requiere. Se notará que, si se requiere una nueva razón entre las dos corrientes, la R nueva se debe fijar en el multiplicador o estación de razón. También se notará que el punto de control del controlador de la corriente B se fija desde otro dispositivo, y no desde el frente del panel del controlador; en consecuencia, como se explicó en la sección 5-3, el controlador debe tener el conmutador remoto/local en la posición de remoto.

El segundo esquema de control de razón, figura 8-5b, consiste en medir ambas corrientes y dividirlas (en FY102B) para obtener la razón de flujo real a través del sistema. La razón que se calcula se envía entonces a un controlador, RIC101, con el cual se manipula el flujo de la corriente B para mantener el punto de control. El punto de control de este controlador es la razón que se requiere, y se fija desde el panel frontal.

En este ejemplo se utilizaron sensores diferenciales de presión para medir los flujos. Como se muestra en el apéndice C, la salida del sensor-transmisor mencionado guarda relación con el cuadrado del flujo y, por tanto, se utilizaron extractores de raíz cuadrada para obtener el flujo; sin embargo, como se menciona en el apéndice C, actualmente la mayoría de los fabricantes incluyen un extractor de raíz cuadrada en sus transmisores diferenciales de presión, por lo cual la señal que sale de dicho transmisor ya está en relación lineal con el flujo y no se necesita el extractor de raíz cuadrada separado. Ambos esquemas de control se pueden implementar sin los extractores de raíz cuadrada, sin embargo, se utilizan para hacer que el circuito de control se comporte de manera más lineal, de lo cual resulta un sistema más estable.

En la industria se utilizan ambos esquemas de control, sin embargo, se prefiere el que aparece en la figura 8-5a, porque es más lineal que el mostrado en la figura 8-5b. Lo anterior se demuestra mediante el análisis de los manejos matemáticos en ambos esquemas; en el primero se resuelve la siguiente ecuación, con FY102B:

$$B = RA$$

La ganancia de este dispositivo, es decir, la cantidad en que cambia la salida por cada modificación en la corriente de entrada A se expresa con:

$$\frac{dB}{dA} = R$$

el cual es un valor constante. En el segundo esquema se resuelve la siguiente ecuación, con FY102B:

$$R = \frac{B}{A}$$

La ganancia se expresa mediante:

$$\frac{dR}{dA} = -\frac{B}{A^2}$$

de manera que, al cambiar el flujo de la corriente A, ésta también cambia, lo cual da lugar a una no linealidad.

Un hecho definitivo acerca de este proceso de mezcla es que, aun cuando se puedan controlar ambos flujos, es más conveniente implementar el control de razón, en comparación con el sistema de control que aparece en la figura 8-4; en la figura 8-6 se muestra un esquema de control de razón para este caso. Si se tuviera que incrementar el flujo total, el operador sólo tiene que cambiar un flujo, el punto de control de FIC101; mientras que en el sistema de control de la figura 8-4 el operador necesita cambiar dos flujos, tanto el punto de control de FIC101 como el de FIC102.

En las figuras 8-5 y 8-6 se empiezan a utilizar puntas de flecha para indicar la dirección de transmisión de las señales (flujo de la información); aun cuando esto no está normalizado, se logra que sea más fácil seguir tales diagramas complejos. También se utiliza la abreviación SP para indicar la señal del punto de control de un controlador; se debe recordar que es necesario colocar en remoto la opción local/remoto del controlador.

El esquema que se ilustra en la figura 8-5a es muy común en la industria de proceso. Los fabricantes han desarrollado, principalmente para los sistemas con base en microprocesadores, un controlador en el que se recibe una señal, se multiplica por un número (razón) y el resultado se utiliza como punto de control, esto significa que la estación de razón, FY102B en la figura 8-5a, se puede incluir en el mismo controlador. De manera similar, en la figura 8-6 FY101C se puede incluir en FIC102.

Como se puede ver, a partir de este sistema de mezclado se inició el desarrollo de esquemas de control más complejos que el simple control por retroalimentación. En el desarrollo de estos planes es útil recordar que toda señal debe tener un significado físico; en las figuras 8-5 y 8-6 se etiquetó cada señal con su significado, por ejemplo, en la figura 8-5a la señal que sale de FT102 se relaciona con el cuadrado del flujo de la corriente A, A², entonces la salida del extractor de raíz cuadrada FY102A es el flujo de la corriente A.

Si ahora se multiplica esta señal por la razón B/A, la señal que sale de FY102B es el flujo que se requiere de la corriente B. A pesar de que esto no es un estándar, en lo sucesivo se etiquetarán las señales con su significado a lo largo del capítulo; se recomienda que el lector haga lo mismo.

**Ejemplo 8-2.** Otro ejemplo común de control de razón que se utiliza en la industria de proceso es el control de la razón aire/combustible que entra a una caldera o a un horno. El aire se introduce en una cantidad superior a la que se requiere estequeométricamente para asegurar la combustión completa del combustible; el exceso de aire que se introduce depende del tiempo de combustible y del equipo que se utilicen; sin embargo, a una cantidad mayor de aire en exceso corresponde una mayor pérdida de energía, debido a los gases de escape; por lo tanto, el control del aire que entra es muy importante para una operación adecuadamente económica.

Generalmente se utiliza el flujo de los combustibles como variable manipulada para mantener en el valor que se desea la presión del vapor que se produce en la caldera. En la figura 8-7 se muestra una forma de controlar la presión de vapor, así como el esquema para controlar la razón de aire/combustible; este esquema se conoce como control por colocación en paralelo con ajuste manual de la razón aire/combustible. La presión de vapor se transmite mediante PT101 al controlador de presión PIC101, con el cual se maneja la válvula de combustible para mantener la presión; simultáneamente, con el controlador se maneja también el regulador de aire a través de la estación de razón FY101C; asimismo, con dicha estación se fija la razón aire/combustible que se requiere.

Con el esquema de control que se muestra en la figura 8-7 no se mantiene realmente una razón de flujo aire/combustible, sino más bien una razón de señales para los elementos finales de control. El flujo a través de dichos elementos depende de estas señales y de la caída de presión a través de ellos; en consecuencia, con cualquier fluctuación de presión a través de la válvula o del regulador de aire, se cambia el flujo aunque no se cambie la abertura, y esto, a su vez, afecta al proceso de combustión y a la presión de vapor. En la figura 8-8 se muestra un esquema de un mejor control, que se conoce como control por medición completa y con el cual se evita este tipo de perturbaciones; la razón aire/combustible todavía se ajusta manualmente. En el esquema mencionado, el flujo de combustible se fija mediante el controlador de presión, y el de aire se raciona a partir del flujo de combustible. Cualquier perturbación en el flujo se corrige por medio de los circuitos de flujo.

Una extensión interesante de estos esquemas de control es la siguiente: puesto que el exceso de aire es tan importante para la operación económica de las calderas, se propone analizar los gases de escape, a los cuales se les conoce también como gases de combustión o desecho, para el exceso de O₂. La razón aire/combustible se puede ajustar o afinar con base en este análisis; en la figura 8-9 se muestra este nuevo esquema de control, donde se aprecia un analizador transmisor, AT101, y un controlador, AIC101, con el cual se mantiene el exceso que se requiere de O₂ en los gases de escape, mediante la derivación (en FY101D) de la señal de la estación de razón, que es el punto de control, al controlador de flujo de aire. Otra forma posible de controlar el exceso de O₂ es permitir que la razón requerida se fije con AIC101; en este caso la salida de FY101A se multiplica por la señal de salida de AIC101. En la figura 8-9 se ilustra también la utilización de los limitadores de máximo y mínimo, FY101E y FY101F; estas dos unidades se utilizan principalmente por razones de seguridad, ya que con ellas se asegura que el punto de control del flujo de aire estará siempre entre un cierto valor superior e inferior prefijado.

En el esquema de control que aparece en la figura 8-8 el flujo de aire siempre sigue al flujo de combustible; esto es, con el controlador de presión se cambia primero el flujo de combustible y, entonces, el flujo de aire sigue al de combustible. En las industrias de proceso la forma más común para implementar el control de razón aire/combustible es por medio del método que se conoce como "control por limitación cruzada"; la implementación mencionada es de forma tal que, cuando la presión de vapor decrece y se requiere más combustible, primero se incrementa el flujo de aire y, posteriormente, le sigue el flujo de combustible; cuando se incrementa la presión de vapor y se requiere menos combustible, primero se decrementa el flujo de combustible y, enseguida el flujo de aire. Con esta estrategia de control se asegura que, durante los transitorios, la mezcla de combustible siempre se enriquezca con aire, con lo cual se logra la combustión completa y se minimiza la probabilidad de "humeo" de los gases de escape y cualquier otra condición peligrosa que resulte de las porciones de combustible puro que entren en la cámara de combustión. La implementación de esta estrategia es el tema de uno de los problemas de ejercicio al final del capítulo.

En esta sección se ilustraron dos aplicaciones del control de razón. Como se mencionó al principio de esta sección, el control de razón es una técnica que se utiliza comúnmente en las industrias de proceso; es simple y fácil de aplicar. Junto con los principios del control de razón, también se ilustró en las aplicaciones la utilización de los relés de cómputo tales como los extractores de raíz cuadrada y los limitadores de máximo y mínimo. En el desarrollo y explicación de estos esquemas de control algunas veces se utilizaron más bloques de los que se requieren en la práctica real; en la figura 8-9 se muestra un ejemplo de esto. Los cálculos matemáticos que se hacen en FY101B y FY101D se pueden realizar totalmente en FY101D. Todo lo que se hace en el primer relé, FY101B, es multiplicar la señal por una constante; posteriormente, la señal resultante se suma a otra señal en el segundo relé, FY101D, y todo esto se puede ejecutar fácilmente con un solo sumador.

## 8-3. CONTROL EN CASCADA

El control en cascada es una técnica de control muy común, ventajosa y útil en las industrias de proceso; en esta sección se presentan sus principios e implementación mediante dos casos prácticos. En la mayoría de los procesos se pueden encontrar ejemplos de sistemas de control en cascada.

**Ejemplo 8-3.** Se considera el proceso de regeneración catalítica que aparece en la figura 8-10. En este proceso, como su nombre lo indica, se regenera el catalizador de un reactor químico. El catalizador se utiliza en un reactor donde se deshidrogena un hidrocarburo; después de un cierto período, el carbón (C) se deposita sobre el catalizador y lo contamina; cuando esto ocurre, el catalizador pierde su actividad y se debe regenerar. La etapa de regeneración consiste en quemar el carbón que se deposita, para lo cual se sopla aire caliente sobre la capa de catalizador; el oxígeno del aire reacciona con el carbón para formar CO₂:

$$C + O_2 \rightarrow CO_2$$

Después de que se quema todo el carbón, el catalizador queda listo para ser utilizado nuevamente. Éste es un proceso por lotes, sin embargo, la quema del carbón puede tardar varias horas.

Durante el proceso de regeneración del catalizador una variable importante que se debe controlar es la temperatura de la capa de catalizador, $T_C$. Con una temperatura muy alta se pueden destruir las propiedades del catalizador; por el contrario, con una temperatura baja el tiempo de combustión resulta largo. La temperatura de la capa se controla mediante el flujo de combustible que llega al calentador de aire (un horno pequeño), como se muestra en la figura 8-10; por razones de simplificación no se muestran los controles de la razón aire/combustible, y por lo mismo sólo se muestra un sensor de temperatura, aunque en la práctica se utilice como variable controlada un promedio de temperatura o la temperatura más alta en la capa. En la sección 8-5 aparece un ejemplo donde se elige la temperatura más alta como variable controlada.

A pesar de que el esquema de control mostrado en la figura 8-10 funciona, se debe reconocer que existen varios retardos de sistema en serie. En el calentador mismo se presentan retardos tales como los de la cámara de combustión y los de los tubos. En el regenerador puede haber una cantidad significativa de retardos en función del volumen y las propiedades del catalizador. Todos estos retardos del sistema dan lugar a un circuito de control por retroalimentación lento (constantes de tiempo grandes y tiempo muerto).

Si se supone que al calentador entra una perturbación tal como un cambio en la temperatura del aire que entra o un cambio en la eficiencia de la combustión, la temperatura con que sale el aire del calentador, $T_H$, se afecta con cualquiera de estas perturbaciones. Al haber un cambio en $T_H$, eventualmente se tiene como resultado un cambio en la temperatura de la capa del catalizador. Con tantos retardos en el sistema, transcurre un tiempo considerable para que en el circuito de control se detecte un cambio en $T_C$. A causa de dichos retardos, en el circuito simple de control de temperatura se tenderá a sobrecompensar, de lo cual resulta un control ineficiente, cíclico y en general lento.

Un mejor método o estrategia de control es aplicar un sistema de control en cascada, como el que se muestra en la figura 8-11. En este esquema de control se mide la temperatura $T_H$ y se utiliza como una variable controlada intermedia; por lo tanto, el sistema consta de dos sensores, dos transmisores, dos controladores y un elemento final de control; de esta instrumentación resultan dos circuitos de control. Con uno de ellos se controla la temperatura con que sale el aire del calentador, $T_H$; con el otro se controla la temperatura de la capa de catalizador, $T_C$. De las dos variables controladas, la temperatura de la capa de catalizador es la más importante; la temperatura de salida del calentador sólo se utiliza como una variable para satisfacer los requerimientos de temperatura de la capa de catalizador.

La forma en que funciona este esquema es la siguiente: con el controlador TIC101 se supervisa la temperatura de la capa de catalizador, $T_C$; y se decide la forma de manejar la temperatura de salida del calentador, $T_H$, para mantener $T_C$ en el punto de control. Esta decisión se envía al controlador TIC102 en forma de un punto de control; este controlador manipula entonces el flujo de combustible para mantener $T_H$ en el valor requerido por TIC101. Si en el calentador se introduce alguna de las perturbaciones que se mencionaron anteriormente, $T_H$ se desvía del punto de control y se inicia una acción correctiva en el controlador TIC102, antes de que cambie $T_C$. Lo que se hace es dividir el retardo total del sistema en dos, para compensar las perturbaciones antes de que se afecte a la variable controlada primaria.

En general, el controlador con que se controla a la variable controlada principal, TIC101 en este caso, se conoce como **controlador maestro, controlador externo o controlador principal**. Al controlador con que se controla a la variable controlada secundaria generalmente se le conoce como **controlador esclavo, controlador interno o controlador secundario**. Comúnmente se prefiere la terminología de primario/secundario, porque para sistemas con más de dos circuitos en cascada la extensión se hace de manera natural.

La consideración más importante al diseñar un sistema de control en cascada es que el circuito interno o secundario debe ser más rápido que el externo o primario, lo cual es un requisito lógico. Esta consideración se puede extender a cualquier cantidad de circuitos en cascada; en un sistema con tres circuitos en cascada, el circuito terciario debe ser más rápido que el secundario, y éste debe ser más rápido que el primario.

Ahora se estudiará la representación en diagrama de bloques de un sistema de control en cascada, lo cual ayudará a entender más esta estrategia tan importante. En la figura 8-12 se muestra la representación en diagrama de bloques para el circuito de control por retroalimentación que se ilustra en la figura 8-10; se eligieron funciones de transferencia simples para representar al sistema. En la figura 8-13 aparece el diagrama de bloques del sistema en cascada que se ilustra en la figura 8-11; como se aprecia en este último diagrama, en el circuito secundario se empieza a compensar cualquier perturbación, o sea, la temperatura de entrada del aire, $T_{ent,air}$, que afecta a la variable controlada secundaria, $T_H$, antes de que su efecto se resienta en la variable controlada primaria, $T_C$.

Se notará que, con la implementación de un esquema de control en cascada, se cambia la ecuación característica del sistema de control de proceso y, en consecuencia, se modifica la estabilidad. A continuación se da un ejemplo para estudiar el efecto de la implementación de un sistema de control en cascada sobre la estabilidad total del circuito. Sean:

$$\tau_1 = 0.2 \text{ min} \qquad \tau_2 = 1 \text{ min} \qquad \tau_3 = 3 \text{ min} \qquad \tau_4 = 4 \text{ min} \qquad \tau_5 = 1 \text{ min}$$
$$K_1 = 0.5 \text{ %TO/°C} \qquad K_2 = 3.0 \text{ gpm/%CO} \qquad K_3 = 1.0 \text{ °C/gpm}$$
$$K_4 = 0.8 \qquad K_5 = 0.5 \text{ %TO/°C}$$

Se supone que todos los controladores son proporcionales.

Se aplica el método de substitución directa que se expuso en el capítulo 6, o las técnicas de respuesta en frecuencia que se expusieron en el capítulo 7, al circuito de control por retroalimentación que aparece en la figura 8-12, para obtener:

$$K_{c_u} = 4.33 \text{ %CO/%TO}$$
$$\omega_u = 0.507 \text{ ciclos/min}$$

donde el porcentaje de salida del transmisor se designa con %TO, y el de la salida del controlador, con %CO.

Para determinar la ganancia y frecuencia últimas del controlador primario del esquema en cascada, primero se debe obtener el ajuste del controlador secundario, lo cual se puede hacer mediante la determinación de la ganancia última del circuito interno de la figura 8-13:

$$K_{c_u} = 17.06 \text{ %CO/%TO}$$

y se utiliza la proposición de Ziegler-Nichols:

$$K_{c_2} = \frac{K_{c_u}}{2} = 8.53 \text{ %CO/%TO}$$

Se utiliza el álgebra de diagramas de bloques para reducir el circuito secundario a un solo bloque, como se muestra en la figura 8-14 (el lector debe verificar la veracidad de esto). Con base en este diagrama de bloques se determina lo siguiente:

$$K_{c_u} = 7.2 \text{ %CO/%TO}$$
$$\omega_u = 1.54 \text{ ciclos/min}$$

Al comparar los resultados se observa que en el esquema de control en cascada la ganancia última o límite de estabilidad es más grande (7.2 %CO/%TO vs 4.33 %CO/%TO) que en el circuito de control por retroalimentación sencillo. También la frecuencia última es más grande en el control en cascada (1.54 ciclos/min vs 0.507 ciclos/min), lo cual indica que la respuesta del proceso es más rápida.

En general, cuando se aplica correctamente el control en cascada, se logra que todo el circuito de control sea más estable y de respuesta más rápida. Los métodos de análisis son los mismos que para los circuitos simples; primero, el circuito interno se reduce a un solo bloque mediante el álgebra de diagramas de bloques y, a partir de ahí, se sigue el procedimiento igual que antes.

Aún quedan dos preguntas: cómo poner el diagrama de cascada en operación automática y cómo ajustar los controladores. La respuesta a ambas es la misma: de adentro hacia afuera; es decir, primero se ajusta el circuito más interno y se pone en automático, mientras que los otros quedan en manual; posteriormente se continúa hacia afuera de la misma manera. Para el proceso que se muestra en la figura 8-11, primero se ajusta TIC102 y se pone en automático, mientras TIC101 queda en manual. Si se hace lo inverso, es decir, se pone primero TIC101 en automático, no ocurre nada, porque TIC102 no es capaz de responder a los requerimientos (punto de control) de TIC101; lo que puede suceder es que, si TIC101 tiene acción de reajuste, se pueda reajustar en exceso, ya que su salida no tendrá efecto sobre la variable que se controla; esto es, el circuito está abierto. Por lo anterior, si en un esquema de cascada cualquier controlador tiene acción de reajuste, se debe agregar protección contra el reajuste excesivo para evitar este problema.

Naturalmente, en los circuitos en cascada el ajuste de los controladores es más complejo que en los sencillos. En los párrafos anteriores se mostró la forma de determinar la ganancia última y el período último para cada circuito; una vez que se obtienen estos términos es posible utilizar el método de Ziegler-Nichols para ajustar los controladores. Sin embargo, el lector debe recordar que se requiere un mínimo de tres retardos o cierta cantidad de tiempo muerto para que en un circuito de control por retroalimentación exista una ganancia última. Los métodos de ajuste para circuito sencillo del capítulo 6 también se pueden aplicar a cada circuito, después de que se ajusta el o los circuitos internos. Se puede obtener la curva de reacción del proceso de cada circuito, pero siempre se debe hacer después de ajustar los circuitos internos; sin embargo, a causa de la interacción entre los circuitos, la curva del proceso puede oscilar, lo cual ocasiona que sea difícil determinar la dinámica del lazo, $\tau$ y $t_0$, y, por lo tanto, los resultados que se obtienen con las fórmulas de ajuste del capítulo 6 pueden no ser satisfactorios en algunos sistemas de control en cascada. La mejor recomendación es tener cuidado y utilizar el sentido común. Un sistema en cascada bien ajustado puede ser muy ventajoso.

**Ejemplo 8-4.** Ahora se considera el sistema de control para el intercambiador de calor que aparece en la figura 8-15. En este sistema la temperatura con que sale el líquido que se procesa se controla mediante la manipulación de la posición de la válvula de vapor. Se notará que no se manipula el flujo de vapor, éste depende de la posición de la válvula de vapor y de la caída de presión a través de la válvula; si se presenta una elevación de presión en la tubería de vapor, es decir, si la presión se incrementa antes de la válvula, se cambia el flujo de vapor; esta perturbación se puede compensar por medio del circuito de control de temperatura que se ilustra, únicamente después de que la temperatura del proceso se desvía del punto de control.

En la figura 8-16 se muestran dos esquemas en cascada con que se puede controlar esta temperatura cuando los cambios en la presión de vapor son importantes. En la figura 8-16a se muestra un esquema de cascada en el que se añadió un circuito de flujo; el punto de control del controlador de flujo se reajusta con el controlador de temperatura, ahora cualquier cambio en el flujo se compensa por medio del circuito de flujo. El significado físico de la señal que sale del controlador de temperatura es el flujo de vapor que se requiere para mantener la temperatura en el punto de control. Con el esquema de cascada que aparece en la figura 8-16b se logra el mismo control, pero ahora la variable secundaria es la presión de vapor en el casquillo del intercambiador; cualquier cambio en el flujo de vapor afecta rápidamente la presión en el casquillo, y cualquier cambio de presión se compensa entonces mediante el circuito de presión. Con el circuito de presión también se compensa cualquier perturbación en el contenido calorífico del vapor (calor latente), ya que la presión en el casquillo se relaciona con la temperatura de condensación y, por lo tanto, con la razón de transferencia de calor en el intercambiador. Si se puede instalar un sensor de presión en el intercambiador, entonces la implementación de este último esquema se hace menos costosa, ya que no se requiere un orificio con sus respectivas guarniciones, lo cual puede resultar caro. Ambos esquemas en cascada son comunes en las industrias de proceso. ¿Puede decir el lector con cuál de los dos esquemas se logra la mejor respuesta inicial a los disturbios de la temperatura de entrada al proceso, $T_i(t)$?

Antes de concluir esta sección es importante mencionar algunas palabras acerca de la acción de los controladores de un sistema en cascada. En el esquema que se ilustra en la figura 8-16a el controlador de flujo es de acción inversa, lo cual se decide de la misma manera que se estudió en el capítulo 5; es decir, por los requerimientos del proceso y la acción de la válvula de control. El controlador de temperatura también es de acción inversa; esta decisión se toma con base en los requerimientos del proceso, esto es, si se incrementa la temperatura de salida, entonces se requiere que el flujo de vapor se decremente y, por lo tanto, se debe disminuir la salida del controlador de temperatura hacia el controlador de flujo.

Finalmente, otro ejemplo muy simple de un sistema de control en cascada es el del posicionador de una válvula de control, el cual actúa como el controlador interno en el esquema de cascada. Los posicionadores se tratan en el apéndice C.

## 8-4. CONTROL POR ACCIÓN PRECALCULADA

En esta sección se presentan los principios y aplicación de uno de los esquemas de control más ventajosos: el control por acción precalculada. En los capítulos anteriores se examinaron las ventajas del control por retroalimentación, técnica muy simple con la que se compensa cualquier perturbación que afecte a la variable controlada. Cada vez que entran al proceso diferentes perturbaciones ($D_1, \ldots, D_n$), la variable controlada se desvía del punto de control; en el sistema de control por retroalimentación esto se compensa mediante la manipulación de otra entrada al proceso, la variable manipulada, como se muestra en la figura 8-17. En el capítulo 6 se estudió la forma de ajustar los sistemas de control por retroalimentación y cómo se comportan éstos bajo condiciones difíciles.

Como se vio en los capítulos anteriores, la principal desventaja de los sistemas de control por retroalimentación es que, para compensar la entrada de perturbaciones, la variable controlada se debe desviar del punto de control. En el control por retroalimentación se actúa sobre un error entre el punto de control y la variable controlada, lo cual significa que, una vez que un disturbio entra al proceso, se debe propagar a lo largo de todo el proceso y forzar a que la variable controlada se desvíe del punto de control antes de que se emprenda una acción correctiva para compensar la perturbación. Entonces, el control perfecto, que se define como aquel donde no hay ninguna desviación de la variable controlada respecto al punto de control a pesar de que existan disturbios, no se puede lograr con el control por retroalimentación.

En muchos procesos se puede tolerar una desviación temporal de la variable controlada, sin embargo, existen otros en los que dicha desviación se debe minimizar en tal cantidad que con el solo control por retroalimentación no se puede obtener el desempeño de control requerido. Para estos casos puede ser muy útil el control por acción precalculada.

En el control por acción precalculada las perturbaciones se compensan antes de que se afecte a la variable controlada. Específicamente, en este tipo de control se miden los disturbios antes de que entren al proceso y se calcula el valor que se requiere de la variable manipulada para mantener la variable controlada en el valor que se desea o punto de control. Si los cálculos se realizan de manera correcta, la variable controlada debe permanecer sin perturbaciones. En la figura 8-18 se ilustra el concepto de control por acción precalculada.

Ahora, mediante el ejemplo de un proceso se enumeran los diferentes pasos que se necesita seguir para diseñar un sistema de control por acción precalculada.

### Ejemplo de un proceso

Se considera la simulación del proceso que se muestra en la figura 8-19. En este proceso se mezclan flujos diferentes en un sistema de tres tanques; en el tanque 1 se mezclan las corrientes $q_5(t)$ y $q_1(t)$; el desborde de este tanque pasa al tanque 2, donde se mezcla con la corriente $q_2(t)$, y el desborde del tanque 2 fluye al tanque 3, donde se mezcla con la corriente $q_7(t)$. En este proceso se requiere controlar la fracción de masa (fm) del componente A, $x_6(t)$, en la corriente que sale del tanque 3. En este proceso la variable manipulada es el caudal $q_1(t)$; el flujo y las fracciones de masa de todas las otras corrientes son posibles perturbaciones. En la tabla 8-4 se presentan los datos del proceso y los valores de estado estacionario de todas las variables. En la figura 8-20a se muestra la respuesta de la variable controlada a un cambio en la corriente $q_2(t)$ de 1000 gpm a 1500 gpm; se utiliza un controlador por retroalimentación PI con ajuste óptimo. Se considera que en este proceso la mayor perturbación es $q_2(t)$. Ahora se verá cómo utilizar las técnicas de acción precalculada para mejorar este control y minimizar la desviación de $x_6(t)$.

El primer paso para diseñar un sistema de control por acción precalculada es desarrollar un modelo matemático de estado estacionario del proceso; dicho modelo es una ecuación mediante la cual se relaciona la variable manipulada con la variable controlada y las perturbaciones. En este ejemplo, la variable manipulada es la corriente $q_1(t)$, la variable controlada es $x_6(t)$, y se supone que $q_2(t)$ es el disturbio mayor. Es importante comprender este último punto; el control por acción precalculada se utiliza para compensar los disturbios mayores, es decir, aquellos que ocurren más frecuentemente y ocasionan grandes desviaciones en la variable controlada; generalmente, la instrumentación y los recursos de ingeniería no justifican la compensación de perturbaciones menores por medio de la acción precalculada. Posteriormente se tratará la compensación de las perturbaciones menores.

El modelo que se requiere de este proceso se obtiene mediante la aplicación del balance de masas al proceso. Al escribir el balance de masa de estado estacionario en todo el proceso, se tiene:

$$q_5\rho + q_1(t)\rho + q_2(t)\rho + q_7\rho - q_6(t)\rho = 0$$

En esta ecuación se utilizaron los valores de estado estacionario de las corrientes $q_5(t)$ y $q_7(t)$ porque se consideran perturbaciones menores. El término $\rho$ es la densidad, masa/gal, de las corrientes, la cual se considera que es la misma para todas las corrientes, por lo tanto:

$$q_6(t) = q_1(t) + q_2(t) + 1000 \quad (8-10)$$

Con el balance de estado estacionario del componente A en todo el proceso se obtiene otra relación que se necesita:

$$q_5x_5 + q_2(t)x_2 + q_7x_7 - q_6(t)x_6 = 0 \quad (8-11)$$

En esta ecuación se utilizaron los valores de estado estacionario de las fracciones de masa $x_5$, $x_7$ y $x_2$ porque también se consideran disturbios menores. De esta última ecuación se tiene:

$$q_6(t) = \frac{1}{x_6}[850 + 0.99q_2(t)] \quad (8-12)$$

Se substituye la ecuación (8-12) en la (8-10) y se obtiene:

$$q_1(t) = \frac{1}{x_6}[850 + 0.99q_2(t)] - q_2(t) - 1000 \quad (8-13)$$

En esta ecuación se remplazó el término $x_6(t)$ por $x_6^{sp}$; mediante esta substitución se calcula el valor de $q_1(t)$ que se requiere para forzar $x_6(t)$ al punto de control $x_6^{sp}$.

En la ecuación (8-13) se relaciona la variable manipulada con la perturbación mayor y la variable controlada; la (8-13) es la ecuación que se debe implementar para el control y constituye lo que se denomina "controlador por acción precalculada". Mediante la solución de dicha ecuación se determina en el controlador el flujo $q_1$ que se requiere para un cierto flujo de perturbación $q_2(t)$ y un cierto punto de control, $x_6^{sp}$.

Antes de implementar el controlador por acción precalculada es conveniente revisar la ecuación, esto es, se substituye el valor de estado estacionario de la perturbación, $\bar{q}_2 = 1000$ gpm, y la variable controlada, $x_6 = 0.4718$ fm, con lo que se obtiene un flujo de:

$$q_1 = 1900 \text{ gpm}$$

el cual es el flujo correcto de estado estacionario y, por lo tanto, se puede tener confianza en el controlador.

En la figura 8-21 se muestra la implementación del sistema de control por acción precalculada; el controlador por acción precalculada propiamente dicho se implementa con FT11, HIC11, FY11A y FY11B. La instrumentación que se utiliza es la que aparece en la tabla 8-3, aun cuando se utilice la convención de señal eléctrica. Se observará que el punto de control que se requiere, $x_6^{sp}$, se genera en HIC11; en esta unidad se genera una señal que el operador fija manualmente y que se relaciona con el punto de control; es decir, el valor inferior del rango de la señal es igual al valor inferior del rango del transmisor de concentración, 0.3 fm. El valor superior del rango de la señal es igual a 0.7 fm y, en consecuencia, el operador puede ajustar el punto de control. Este esquema de control se denomina "control por acción precalculada de estado estacionario".

En la figura 8-20b se muestra la respuesta de un proceso donde se utiliza control por acción precalculada en estado estacionario a un cambio en la corriente $q_2(t)$ de 1000 gpm a 1500 gpm; esta figura se puede comparar con la 8-20a para apreciar la mejoría que se obtiene con la implementación del control con acción precalculada. En la curva de respuesta se aprecia aún que la variable controlada no permanece constante (como se esperaba) sino que más bien se observa un error transitorio, el cual se presenta porque existe un desbalance dinámico entre los efectos de la perturbación, $q_2(t)$, y la variable manipulada, $q_1(t)$, sobre la variable controlada, $x_6(t)$; es decir, la respuesta de la composición de salida es más rápida para un cambio en la corriente $q_2(t)$ que para un cambio en la corriente $q_1(t)$. Uno de los objetivos del control por acción precalculada debe ser establecer un balance de la variable manipulada contra la perturbación. Es deseable hacer más rápida la respuesta de $x_6(t)$ a un cambio en $q_1(t)$, ya que es más lenta que la respuesta a un cambio en $q_2(t)$, lo cual se puede lograr si se utiliza una "unidad de adelanto/retardo". Las unidades de adelanto/retardo se presentan en la siguiente subsección. En la figura 8-22 se muestra el esquema del control después de instalar la unidad de adelanto/retardo; a dicho esquema se le conoce como "control por acción precalculada con compensación dinámica". En la figura 8-20c aparece la respuesta del proceso a un cambio en $q_2(t)$ de 1000 gpm a 1500 gpm; se notará que el error transitorio se reduce significativamente; no se logra el balance perfecto, sin embargo, se alcanza una mejoría notable sobre la respuesta no compensada.

La mejoría de la acción precalculada con compensación dinámica sobre la acción precalculada de estado estacionario se debe a los diferentes modos en que responde la variable manipulada, $q_1(t)$, en cada caso. En la figura 8-23a se muestra la forma en que responde $q_1(t)$ a un cambio en $q_2(t)$; lo cual está determinado por el controlador por acción precalculada, ecuación (8-13). En la figura 8-23b se muestra cómo responde $q_1(t)$ a un cambio en $q_2(t)$ cuando se instala la unidad de adelanto/retardo; inicialmente, $q_1(t)$ cambia en una cantidad superior a la que se necesita para la compensación de estado estacionario, y posteriormente decae exponencialmente hasta el valor final de estado estacionario. Debido a que reacciona en esta forma, se dice que $q_1(t)$ tiene más "fuerza" para mover la variable controlada más rápido. Este tipo de respuesta de $q_1(t)$ a un cambio en $q_2(t)$ se debe a la unidad de adelanto/retardo.

En este momento es importante mencionar que los "ajustes" de la unidad de adelanto/retardo son generalmente empíricos, pero también se pueden obtener analíticamente mediante un análisis matemático en detalle. Posteriormente, en esta sección se dedica un espacio a la explicación de la operación de la unidad de adelanto/retardo y la forma de obtener la información para el ajuste de la unidad.

Antes de proceder con este ejemplo es importante mencionar que no se requiere compensación dinámica en todos los esquemas con acción precalculada y, por lo tanto, se recomienda que, al implementar inicialmente un control con acción precalculada, se pruebe primero la porción de estado estacionario; si se presentan errores transitorios, entonces se necesita compensación dinámica y el ingeniero tiene justificación para implementarla. Ciertamente, con el juicio de ingeniería se puede tener una indicación acerca de la posibilidad de algún error transitorio o no. En el ejemplo presente, la perturbación entra más cerca de la variable controlada que de la variable manipulada; esto es, existe una constante de tiempo (tanque) menos entre la variable controlada y la perturbación que entre la variable controlada y la manipulada, por lo tanto, no debe sorprender que exista un error transitorio, cuya magnitud depende de la diferencia entre los efectos dinámicos.

En el esquema de control por acción precalculada que se implementó hasta ahora sólo se compensan los cambios en $q_2(t)$, ya que en el desarrollo del controlador se supuso que la única perturbación mayor es $q_2(t)$ y que las demás entradas al proceso son perturbaciones menores; es decir, en estas entradas no hay mucho cambio, o no con la suficiente frecuencia como para justificar el esfuerzo y el capital que se necesitan para compensarlas; en consecuencia, si alguno de estos disturbios entra al proceso, no se compensará mediante el esquema de control que aparece en la figura 8-22, y entonces resultará una desviación de la variable controlada. Como ejemplo, en la figura 8-24a se muestra la respuesta del esquema de control por acción precalculada que aparece en la figura 8-22 cuando $q_7(t)$ cambia de 500 gpm a 600 gpm, la variable controlada alcanza un nuevo valor y permanece ahí; en el esquema de control no hay compensación para esta perturbación.

Una manera simple de corregir tal desviación es cambiar manualmente la salida de HIC11; esto es, cuando el operador se da cuenta de que a la salida la composición está arriba del punto de control, toma la decisión de incrementar el caudal de agua pura, lo cual se hace fácilmente disminuyendo la salida de HIC11; al hacer esto, en el controlador por acción precalculada se incrementa el punto de control para el controlador de flujo de agua FIC12 y dicha operación continúa hasta que desaparece la desviación. Con base en lo anterior, el operador puede corregir cualquier perturbación que no se compense mediante el controlador por acción precalculada.

Este procedimiento para compensar cualquier perturbación menor es simple y funciona bien, sin embargo, la desventaja es que requiere la intervención del operador; sería mucho mejor que la compensación se hiciera automáticamente, sin necesidad de que intervenga el operador. En la figura 8-25 se muestra un esquema con el que se logra lo anterior, se le denomina "control con acción precalculada con compensación dinámica y afinación por retroalimentación"; en dicho esquema se substituye al operador con el controlador por retroalimentación CIC11. Se observará que ahora la composición real que se desea a la salida es el punto de control de CIC11; en este controlador se decide qué señal se debe enviar al controlador por acción precalculada $x_6^{sp}$ para mantener el punto de control. En la figura 8-24b se muestra la respuesta de este nuevo esquema de control cuando $q_7(t)$ cambia de 500 a 600 gpm; como se ve, mediante la compensación por retroalimentación se regresa la variable controlada al punto de control.

Para resumir, con el controlador por acción precalculada se compensan los disturbios mayores. La afinación con retroalimentación se necesita por varias razones, entre las cuales están el hecho de que no siempre se miden y compensan todos los disturbios posibles, de que la ecuación del controlador por acción precalculada no es exacta y la derivada de los instrumentos, para citar algunas; por estas razones el control por acción precalculada se implementa con afinación por retroalimentación.

La ubicación de la afinación por retroalimentación es importante y se debe considerar en el esquema de control completo. En la figura 8-25 se observa que la afinación por retroalimentación se introduce después de la unidad de adelanto/retardo; si la unidad de adelanto/retardo se instala después de la afinación por retroalimentación, esta compensación pasa entonces a través de la unidad, de lo que resulta un "rebote" transitorio del proceso, lo cual es innecesario. Puesto que esta compensación por retroalimentación no se necesita compensar dinámicamente contra nada, no es necesario que pase por la unidad de adelanto/retardo.

### Unidad de adelanto/retardo

Antes de continuar con el control por acción precalculada, se hará una revisión rápida de la unidad de adelanto/retardo. En esta unidad se resuelve la siguiente función de transferencia, como se ve en la ecuación (4-78):

$$\frac{Y(s)}{X(s)} = \frac{\tau_{ld}s + 1}{\tau_{lg}s + 1} \quad (4-78)$$

donde:
- $\tau_{ld}$ = constante de tiempo de adelanto; min
- $\tau_{lg}$ = constante de tiempo de retardo; min

Algunas veces se multiplica esta función de transferencia por un factor de ganancia $K$, como se muestra en la tabla 8-3. La expresión con que se describe la respuesta $Y(t)$ a un cambio de escalón unitario en la función de forzamiento, en el dominio del tiempo, se obtiene con la ecuación (4-79):

$$Y(t) = K\left[1 + \left(\frac{\tau_{ld}}{\tau_{lg}} - 1\right)e^{-t/\tau_{lg}}\right] \quad (4-79)$$

En la figura 8-26 se muestra gráficamente la respuesta para el caso donde $\tau_{lg} = 1$ con diferentes razones de $\tau_{ld}/\tau_{lg}$. Es conveniente repetir lo que se mencionó en el capítulo 4 acerca de esta unidad. Lo primero y más importante es que la cantidad inicial de respuesta depende de la razón $\tau_{ld}/\tau_{lg}$; esta respuesta inicial es igual al producto de $\tau_{ld}/\tau_{lg}$ por la magnitud del cambio escalón. En la figura 8-23b se muestra la respuesta de $q_1(t)$ a un cambio en $q_2(t)$ cuando se utiliza control dinámico con acción precalculada; en este ejemplo se utiliza una unidad de adelanto/retardo con razón $\tau_{ld}/\tau_{lg}$ mayor a 1, específicamente, $\tau_{ld}/\tau_{lg} = 3.31/2.29 = 1.44$. Segundo, la cantidad de cambio en la salida de la unidad de adelanto/retardo es igual a la magnitud del cambio en la entrada. Último, la tasa exponencial de disminución o incremento en la salida únicamente es función de la constante de tiempo de retardo, $\tau_{lg}$.

Como se vio en la sección anterior, las unidades de adelanto/retardo se utilizan para compensar los desbalances dinámicos del proceso. Para implementar una unidad de adelanto/retardo se debe especificar la constante de tiempo de adelanto, $\tau_{ld}$, y la constante de tiempo de retardo, $\tau_{lg}$, las cuales son parte de la personalidad del proceso. En la siguiente sección se muestra cómo obtener una estimación inicial de $\tau_{ld}$ y $\tau_{lg}$. Las unidades de adelanto/retardo se pueden adquirir comercialmente en forma de unidades analógicas o de sistemas con base en microprocesadores.

### Diseño del control lineal por acción precalculada mediante diagrama de bloques

El primer paso para implementar el control por acción precalculada es el desarrollo de un modelo o ecuación del proceso, en el cual se establece la relación entre la variable manipulada con la variable controlada y todas las perturbaciones mayores. En el ejemplo de proceso que se presentó al principio de esta sección se ilustró cómo hacer esto para el proceso que aparece en la figura 8-19. Para este proceso el modelo se desarrolló analíticamente; se empezó por la ecuación básica de balance de masa, sin embargo, en caso de que no sea posible desarrollar analíticamente el modelo requerido porque el proceso es muy difícil de describir o existen muchos parámetros desconocidos, ¿qué se hace? Éste es el tema de la presente sección. Para demostrar la técnica se utiliza el proceso que aparece en la figura 8-19; en la figura 8-27a se muestra un diagrama a bloques parcial de este proceso. Puesto que, una vez que se ajusta, el circuito de flujo es rápido y estable, la figura 8-27a se puede simplificar en la forma que se muestra en la figura 8-27b.

Para implementar el control por acción precalculada se debe medir la perturbación, la cual se utiliza para calcular la variable manipulada con que se mantiene constante la variable controlada. En la figura 8-28 se muestra el diagrama de bloques de este esquema de control por acción precalculada; después de utilizar el álgebra de diagramas de bloques:

$$X_6(s) = H_2(s)Q_2(s) + H_1(s)G_A(s)G_{FC}(s)G_1(s)Q_1(s) \quad (8-14)$$

Ahora el objetivo es diseñar el controlador por acción precalculada, $G_A(s)$, de manera que, cuando $q_2(t)$ varíe, $x_6(t)$ permanezca constante; si $x_6(t)$ es constante, entonces $X_6(s) = 0$ y el controlador por acción precalculada se puede obtener a partir de la última ecuación:

$$G_A(s) = -\frac{G_2(s)}{H_2(s)G_1(s)G_{FC}(s)G_1(s)} \quad (8-15)$$

Ésta es la ecuación del controlador por acción precalculada que se debe implementar.

Para tener más visión acerca del método mencionado, se observará este ejemplo con más detalle. Si se supone que en el proceso de la figura 8-19 se coloca el controlador de concentración, CIC11, en manual y se introduce un cambio escalón en el punto de control del controlador de flujo, FIC12, y además se lleva un registro del cambio de fracción de masa, $x_6(t)$, a la salida del último tanque, entonces, a partir de estos datos se desarrolla el siguiente modelo, para lo cual se utiliza el procedimiento que se presentó en el capítulo 6:

$$G_{p_1}(s) = G_1(s)G_{FC}(s)G_{v_1}(s) = \frac{K_1}{\tau_1s + 1} \quad (8-16)$$

A la corriente 2 se le aplica la prueba escalón de la misma manera, y se registra $x_6(t)$ para desarrollar la siguiente función de transferencia:

$$G_{p_2}(s) = \frac{K_2}{\tau_2s + 1} \quad (8-17)$$

Si se supone que la dinámica del sensor-transmisor de flujo es despreciable, se obtiene:

$$H_2(s) = K_{T_2} = \frac{\%TO}{gpm} \quad (8-18)$$

Se substituyen las ecuaciones (8-16), (8-17) y (8-18) en la ecuación (8-15) para obtener:

$$G_A(s) = -\frac{K_2}{\tau_2s + 1}\cdot\frac{1}{K_{T_2}}\cdot\frac{\tau_1s + 1}{K_1} = \left(-\frac{K_2}{K_1K_{T_2}}\right)\left(\frac{\tau_1s + 1}{\tau_2s + 1}\right) \quad (8-19)$$

El primer término entre paréntesis es una ganancia pura con unidades (%CO/%TO) y representa cuánto debe cambiar la salida del controlador con acción precalculada para un cambio en la salida del transmisor de flujo. Naturalmente, con esto cambia la corriente 1 cuando cambia la corriente 2, lo cual es la idea del control por acción precalculada. El segundo término es el compensador dinámico, la unidad de adelanto/retardo; los ajustes están dados por $\tau_{ld} = \tau_1$ y $\tau_{lg} = \tau_2$. Finalmente, el tercer término, que es un término exponencial, es otro compensador dinámico y se puede considerar como un "compensador de tiempo muerto"; sin embargo, existen dos problemas posibles con este término. El primero es que con instrumentos analógicos la implementación de esta compensación es impráctica; con la utilización de computadoras es más simple; en la mayoría de los sistemas con base en microprocesadores que se utilizan actualmente existe un bloque de cómputo de tiempo muerto. El segundo problema consiste en que, si el término $t_{0_2} - t_{0_1}$ es negativo -lo que da origen a un exponente positivo-, como este término ya no es tiempo muerto, se interpretaría como predictor del futuro, lo cual no es posible. Por lo anterior, se elimina generalmente el último término y la ecuación del controlador por acción precalculada queda de la siguiente forma:

$$G_A(s) = \left(\frac{K_2}{K_1K_{T_2}}\right)\left(\frac{\tau_1s + 1}{\tau_2s + 1}\right) \quad (8-20)$$

Con la actual instrumentación mediante computadora se puede implementar el compensador de tiempo muerto si el término $t_{0_2} - t_{0_1}$ es positivo.

Generalmente, la compensación por retroalimentación se añade al esquema de acción precalculada. En la figura 8-29 se muestra el diagrama de bloques del esquema completo, y en la figura 8-30 se muestra el diagrama de instrumentación. En la figura 8-30 se multiplica la señal de FT11 por $\frac{K_2}{K_1K_{T_2}}$ en el multiplicador FY11A y en FY11B se realiza la compensación de adelanto/retardo. En la mayoría de los casos se pueden realizar ambos cálculos en un solo relé de cómputo, como se aprecia en la tabla 8-2; la compensación por retroalimentación se añade al controlador por acción precalculada en FY11C.

En este esquema de control por acción precalculada el significado de la afinación por retroalimentación es diferente del que se tiene cuando se desarrolla el controlador por acción precalculada de manera analítica. En este caso se utiliza la afinación por retroalimentación para desviar (bias) (hacia arriba o hacia abajo) la salida del controlador por acción precalculada y así compensar las perturbaciones menores. Acerca del escalamiento del sumador, FY11C, cabe señalar que el lugar donde se introduce la retroalimentación es importante. En este sumador, al que se denomina algunas veces "estación de derivación", se resuelve la siguiente ecuación:

$$\text{Salida} = \text{señal retroalimentada} + \text{señal de acción precalculada} + \text{derivación}$$

Para más claridad y a fin de mostrar la forma de calcular la derivación, ahora se considera la utilización del sumador que aparece en la tabla 8-2:

$$OUT = K_1X + K_2Y + K_3Z + B_0$$

Sea la entrada $X$ la señal de retroalimentación, y la señal de acción precalculada la entrada $Y$; la entrada $Z$ no se utiliza. En estado estacionario $\bar{q}_1$ es de 1000 gpm, si se supone que la escala del sensor-transmisor con que se mide este flujo es de 0-2500 gpm, entonces el valor del flujo de estado estacionario es el 40% de este rango; bajo tales condiciones, la salida de estado estacionario del controlador con acción precalculada, la cual es la entrada del sumador, es de $(K_2/K_1K_{T_2})\cdot 40\%$; lo que se hace en el sumador es utilizar la derivación ($B_0$) para cancelar la señal precalculada y, por lo tanto, el término de derivación se fija a $-(K_2/K_1K_{T_2})\cdot 40\%$. Puesto que en estado estacionario $\bar{q}_1$ es de 1900 gpm, y la escala del transmisor es de 0-3800 gpm, como se indica en la tabla 8-4, la señal que sale del sumador debe ser del 50% de este rango, con lo cual se fuerza a que la señal de salida del controlador por retroalimentación sea del 50% de su rango en estado estacionario.

En este ejemplo es fácil darse cuenta, mediante los principios de ingeniería, de que el signo de $K_1$ es positivo, mientras que el signo de $K_2$ es negativo, lo cual significa que el término $K_2/K_1$ es una cantidad positiva, lo que, a su vez, indica que si $q_2(t)$ se incrementa, también $q_1(t)$ se debe incrementar.

En el sumador se pueden fijar los valores de los factores de escalamiento $K_1$ y $K_2$ a $+1$, mientras que el valor de la derivación $B_0$ se fija a $-(K_2/K_1K_{T_2})\cdot 40\%$. El signo del factor de escalamiento de la señal precalculada ($K_2$ en este caso) se puede considerar como la "acción" del controlador por acción precalculada. El ingeniero debe cerciorarse que todos los signos sean los correctos antes de poner el sistema completo de control en automático.

Con los nuevos sistemas con base en microprocesadores algunas veces no es necesario utilizar un sumador como derivación. Muchos de los controladores con base en microprocesadores se implementan a manera de permitir que se haga la derivación en el controlador por retroalimentación; esto es, en tales controladores se acepta la señal precalculada como otra entrada y dicha señal se utiliza para derivar la decisión del controlador por retroalimentación; el resultado de dicho manejo se convierte en la salida del controlador. Esta salida es el resultado del esquema de acción precalculada/retroalimentación, con lo que se ahorra un bloque, lo cual es otra de las ventajas de la nueva tecnología.

Como se vio, el diseño de controladores por acción precalculada mediante diagramas de bloques es simple y práctico. Sin embargo, antes de concluir esta sección es deseable hacer énfasis sobre los siguientes puntos:

1. La diferencia entre el método de diagrama de bloques y el de ecuaciones, el cual se presentó al principio de esta sección en el ejemplo de un proceso, es que del primero resulta un controlador por acción precalculada lineal, y en el segundo se obtienen generalmente cálculos no lineales. Siempre que es posible, se prefiere el método de ecuaciones en lugar del de diagrama a bloques, debido a que en el desempeño de los controladores lineales se reducen las condiciones de operación fuera del rango para el cual se evalúan y, cuando esto sucede, en el controlador por retroalimentación se debe compensar con más frecuencia, ya que las no linealidades del proceso actúan como perturbaciones. En los controladores que resultan del método por ecuaciones se pueden compensar las no linealidades. En ambos métodos la compensación dinámica, unidad de adelanto/retardo, es lineal y empírica.
2. Las ganancias que se utilizan en el método de diagrama de bloques se obtienen mediante prueba del proceso; también se pueden obtener mediante linealización de las ecuaciones de balance. Por ejemplo, $K_F$ se puede obtener de reordenar la ecuación (8-11) como sigue:

$$x_6(t) = \frac{1}{q_6(t)}[q_5x_5 + q_2x_2 + q_7x_7]$$

y entonces:

$$\frac{\partial x_6}{\partial q_2} = \frac{x_2}{q_6}$$

3. Debido a que en el método de diagrama de bloques se trabaja con variables de desviación, se añade un término de derivación, el cual no se previó en el diseño. La afinación por retroalimentación generalmente se introduce en la unidad de la que se obtiene la derivación (FY11C en la figura 8-30).

En la figura 8-29 se ilustra un hecho importante e interesante acerca del control por acción precalculada, es notorio que la trayectoria directa $H_2(s)G_A(s)$ no forma parte de la ecuación característica, lo cual significa que, al añadir el control por acción precalculada, no se afecta la estabilidad del circuito de control.

### Dos ejemplos adicionales

**Ejemplo 8-5.** Un proceso interesante en el que se utilizan las técnicas de control que se aprendieron hasta aquí es el control de nivel de líquido en una caldera de tambor. En la figura 8-31 se muestra esquemáticamente una caldera de tambor. El control de nivel en el tambor es muy importante, ya que con un nivel alto puede entrar agua, y tal vez impurezas, en el sistema de vapor; si el nivel es bajo puede haber fallas en el recipiente por sobrecalentamiento, a causa de la falta de agua en las superficies de ebullición.

En la figura 8-31 se muestran las burbujas de vapor que fluyen hacia arriba, a través del agua, lo cual representa un efecto importante, ya que el volumen específico (volumen/masa) de las burbujas es muy grande y, por lo tanto, estas burbujas desplazan al agua; de lo anterior resulta un nivel aparente más alto que el que se debe únicamente al agua. La presencia de estas burbujas también representa un problema bajo condiciones transitorias. Si se considera la situación en que, a causa del incremento de demanda de vapor por parte de los usuarios, cae la presión del vapor en la parte superior; como consecuencia de tal condición, una cierta cantidad de agua se convierte rápidamente en burbujas de vapor, con las cuales se tiende a incrementar el nivel aparente en el tambor; con la caída de presión también se produce una expansión en el volumen de las burbujas existentes y, debido a esto, se incrementa aún más el nivel aparente; dicha elevación de nivel, que resulta de una disminución en la presión, se denomina **expansión**. Con un incremento de presión en el vapor superficial, debido a una disminución en la demanda por parte de los usuarios, se tiene el efecto opuesto sobre el nivel aparente, a lo cual se le denomina **contracción**.

Como se explicó anteriormente, el fenómeno de contracción/expansión, en combinación con la importancia de mantener un buen nivel, provoca que el control del nivel sea aún más crítico. En los siguientes párrafos se desarrollan algunos de los esquemas que se utilizan actualmente en la industria.

El control de nivel en el tambor se logra mediante la manipulación del flujo en el alimentador de agua. En la figura 8-32 se muestra el tipo más simple de control de nivel, el cual se conoce como "control de un solo elemento", en el cual se utiliza un sensor-transmisor de presión diferencial estándar. Este esquema de control se basa en la medición de nivel del tambor y, por lo tanto, ésta debe ser confiable. Bajo transitorios prolongados, el fenómeno de expansión/contracción provoca que no se pueda tener mediciones confiables y, en consecuencia, se requiere un esquema de control donde se compense tal fenómeno.

El nuevo esquema de control se denomina "control de dos elementos", y se ilustra en la figura 8-33; es esencialmente un sistema de control por acción precalculada/retroalimentación. La idea en que se funda este esquema es que la principal razón para que cambie el nivel son los cambios en el flujo de vapor, y que por cada libra de vapor que se produzca debe entrar una libra de agua al tambor, es decir, debe existir un balance de masa. Con la señal de salida de FY101A se obtiene la parte de acción precalculada del esquema; mientras que con LIC101 se obtiene la compensación de cualquier flujo no medido, tal como el colapso.

El esquema de "control de dos elementos" funciona completamente bien en muchas de las calderas industriales de tambor, sin embargo, existen algunos sistemas donde la caída de presión a través de la válvula de alimentación de agua es variable; con el esquema de "control de dos elementos" no se compensa directamente tal perturbación y, en consecuencia, ésta trastorna el balance del control de nivel del tambor al modificar momentáneamente la masa. Con el esquema de "control de tres elementos" que se ilustra en la figura 8-34 se logra la compensación requerida; en este esquema se tiene un control estricto del balance de masa durante los transitorios. Es interesante notar que todo lo que se añadió al esquema de "control de dos elementos" es un sistema de control en cascada.

Con la caldera de tambor se mostró un ejemplo realista de cómo se utilizan los esquemas de control en cascada y por acción precalculada para mejorar el desempeño que se logra con el control por retroalimentación. En este ejemplo particular, la utilización de tales esquemas es casi obligatoria para evitar las fallas mecánicas y de proceso; cada paso que da para mejorar el control es justificado, de otra manera no habría necesidad de complicar las cosas. Se remite al lector a las referencias 11 y 12 para otra exposición completa de este tema.

**Ejemplo 8-6.** Ahora se presenta otro ejemplo realista, el cual es una aplicación industrial del control por acción precalculada. El ejemplo se refiere al control de temperatura en la sección de rectificación de una columna de destilación. En la figura 8-35 se muestra el fondo de la columna y el esquema de control que originalmente se propone e implementa; en esta columna se utilizan dos rehervidores; en uno de los rehervidores, R-10B, se utiliza la condensación de una corriente en proceso como medio de calefacción, y en el otro rehervidor, R-10A, se utiliza la condensación de vapor. Para una operación energéticamente eficiente, en el procedimiento de operación se requiere utilizar, tanto como sea posible, la condensación de la corriente en proceso, la cual se debe condensar de cualquier modo y, por lo tanto, sirve como fuente "gratuita" de energía. La corriente de vapor se utiliza para controlar la temperatura en la columna.

Después de inicializar la columna, se observa que en la corriente en proceso, que sirve como medio de calefacción, se experimentan cambios de flujo y de presión, los cuales actúan como perturbaciones en la columna y, en consecuencia, se necesita compensar continuamente en el controlador de temperatura estas perturbaciones. Con las constantes de tiempo y el tiempo muerto en la columna y los rehervidores se complica el control de la temperatura. Después de estudiar el problema se decidió utilizar control por acción precalculada; para lo cual se instala un transmisor de presión y un transmisor diferencial de presión sobre la corriente en proceso; y con base en los datos que se obtienen con ellos, se puede calcular la cantidad de energía que libera la corriente cuando se condensa. Con esta información también se puede calcular la cantidad de vapor requerida para mantener la temperatura en el punto de control y, por lo tanto, la acción correctiva se puede emprender antes de que la temperatura se desvíe del punto de control. La anterior es una aplicación perfecta del control por acción precalculada.

El procedimiento realizado fue específicamente el siguiente: puesto que la corriente en proceso está saturada, la densidad, $\rho$, únicamente es función de la presión. Por lo tanto, para obtener la densidad, $\rho$, de la corriente se utiliza una correlación termodinámica:

$$\rho = f_1(P) \quad (8-20)$$

La densidad y el diferencial de presión, $h$, que se obtiene del transmisor DPT48, se utilizan para calcular el flujo de masa de la corriente a partir de la ecuación de orificio:

$$\dot{m} = K\sqrt{h\rho}, \text{ lbm/hr} \quad (8-21)$$

También, si se conoce la presión de la corriente y se utiliza otra relación termodinámica, se puede calcular el calor latente de condensación, $\lambda$:

$$\lambda = f_2(P), \text{ Btu/lbm} \quad (8-22)$$

Finalmente, se multiplica la razón de flujo de masa por el calor latente para obtener la energía, $q_1$, que se libera cuando se condensa la corriente en proceso:

$$q_1 = \dot{m}\lambda, \text{ Btu/hr} \quad (8-23)$$

En la figura 8-36 se muestra la implementación de las ecuaciones (8-20) a (8-23), así como el resto del esquema de acción precalculada. En el bloque PY48A se realiza la ecuación (8-20); en el PY48B, la (8-21); en el PY48C, la (8-22); y en el PY48D, la (8-23); por lo tanto, la salida del relé PY48D es $q_1$, o sea, la energía que se libera cuando se condensa la corriente en proceso.

Para completar el esquema, se considera que la salida del controlador de temperatura es la energía total que se requiere, $q_T$, para mantener la temperatura en el punto de control. Se substrae $q_1$ de $q_T$ para determinar la energía que se requiere del vapor, $q_s$:

$$q_s = q_T - q_1 \quad (8-24)$$

Finalmente, se divide $q_s$ entre el calor latente en la condensación del vapor, $h_{fg}$, para obtener el flujo de vapor que se requiere, $m_s$:

$$m_s = \frac{q_s}{h_{fg}} \quad (8-25)$$

En el bloque TY51A se efectúan las ecuaciones (8-24) y (8-25), y su salida es el punto de control del controlador de flujo FIC50. En la ecuación (8-25) se supone que $h_{fg}$ es constante.

En este esquema de control por acción precalculada se deben observar varias cosas. Primera, el modelo del proceso no es una ecuación, antes bien, son varias; para obtener el modelo se utilizaron varios principios de la ingeniería de proceso, lo cual hace que el control de proceso sea divertido, interesante y excitante. Segunda, la afinación por retroalimentación es parte integral de la estrategia de control; esta compensación es $q_T$, o la cantidad total de energía que se requiere para mantener el punto de control de TIC51. Última, en el esquema de control de la figura 8-36 no se muestra la compensación dinámica o unidad de adelanto/retardo, la cual se puede instalar posteriormente si se necesita.

### Respuesta inversa

En la caldera de tambor del ejemplo 8-5 se presenta un fenómeno que se puede observar en varios procesos diferentes. Como se explicó en el ejemplo, el nivel que se puede registrar resulta de la mezcla de agua y burbujas y, por lo tanto, es más alto que el nivel debido únicamente al agua. Ahora se supone que se desea determinar la ganancia, la constante de tiempo y el tiempo muerto en el circuito de nivel, y que, para ello se utilizará el procedimiento de prueba con escalón que se estudió en el capítulo 6. La válvula de alimentación de agua se abre para permitir que entre más agua al tambor, y también se toma el registro de nivel dinámico, lo cual se ilustra en la figura 8-37; en la figura se observa que primero baja el nivel en el tambor y, posteriormente, se incrementa hasta alcanzar una nueva condición de operación; este tipo de respuesta se conoce como "respuesta inversa". Ciertamente, este tipo de respuesta no es mágica; al contrario, existe una explicación física de la misma. Lo que sucede es que, tan pronto como entra agua fría al tambor, cierta cantidad de burbujas se condensa y el espacio que ocupaban queda vacío, con lo cual se reduce el nivel aparente; eventualmente el nivel se incrementa, ya que entra más agua y se forman nuevas burbujas. Ciertamente, esta respuesta es otra de las razones por las que son tan necesarios los esquemas de control de dos o tres elementos que se muestran en las figuras 8-33 y 8-34.

En la literatura existen varios ejemplos de sistemas con respuesta inversa. En el capítulo 9 se presenta la elaboración del modelo para un reactor químico en el que se tiene dicha respuesta.

En la función de transferencia con que se describe este tipo de respuesta se requiere un cero positivo:

$$\frac{H(s)}{M(s)} = \frac{K(-\tau_1s + 1)}{\tau_2s + 1} \quad (8-26)$$

Puesto que la evaluación de $K$, $\tau_1$ y $\tau_2$ no se hace fácilmente, la respuesta se puede aproximar mediante un retardo de primer orden más tiempo muerto:

$$\frac{H(s)}{M(s)} = \frac{Ke^{-t_0s}}{\tau s + 1} \quad (8-27)$$

En la figura 8-38 se ilustra la evaluación de los parámetros. Generalmente este tipo de sistema no es lineal y, en consecuencia, los parámetros $\tau$, $\tau$ y $t_0$ son muy sensibles a las condiciones de operación.

### Resumen del control por acción precalculada

Como se mencionó anteriormente y se demostró en esta sección, el control por acción precalculada es una de las técnicas más eficaces de que se dispone; sin embargo, no es la solución para todos los problemas de control. Para su implementación se requiere más ingeniería que en la retroalimentación simple y, por lo tanto, su costo monetario se debe justificar antes de su implantación. Cuando se aplica correctamente, las compensaciones económicas y la autosatisfacción de un trabajo bien hecho son significativas.

## 8-5. CONTROL POR SOBREPOSICIÓN Y CONTROL SELECTIVO

El control por sobreposición se utiliza generalmente como un control de protección para mantener las variables del proceso dentro de ciertos límites. Otro esquema de protección es el de control entrelazado, el cual se utiliza principalmente como protección contra mal funcionamiento del equipo; cuando se detecta mal funcionamiento, el proceso se detiene mediante el sistema entrelazado. La acción del control por sobreposición no es tan drástica: el proceso se mantiene en operación, pero bajo condiciones más seguras. En esta sección se presenta un ejemplo de control por sobreposición para ilustrar sus principios y utilización; en este texto no se presentan los sistemas por control entrelazado, pero en la bibliografía aparecen referencias (4 y 5) para su estudio.

Ahora se considera el proceso que aparece en la figura 8-39, en el tanque entra un líquido saturado y de ahí nuevamente se bombea, bajo control, al proceso. En operación normal, el nivel del tanque está a la altura $h_1$, como se muestra en la figura; si por cualquier circunstancia el nivel del líquido baja a la altura $h_2$, no se tendrá suficiente volumen positivo neto de succión (VPNS) (NPSH, por sus siglas en inglés), de lo que resulta cavitación (cabeceo) en la bomba. Por lo tanto, es necesario diseñar un sistema de control con el que se evite esa condición; este nuevo esquema de control se muestra en la figura 8-40.

Ahora se mide y controla el nivel en el tanque; es importante observar la acción de los controladores y del elemento final de control. La bomba de velocidad variable funciona de tal manera que, cuando se incrementa la entrada de energía (electricidad en este caso), se bombea más líquido; de lo anterior se tiene que FIC50 es un controlador con acción inversa; en cambio, LIC50 es un controlador con acción directa. La salida de cada controlador se conecta a un relé de selección baja, LS50, y de ahí la salida pasa a la bomba.

Bajo condiciones normales de operación, el nivel está en $h_1$, el cual se encuentra por arriba del punto de control del controlador de nivel y, por lo tanto, desde el controlador se tratará de acelerar a la bomba tanto como sea posible, mediante el incremento de la salida a 20 mA. La salida del controlador de flujo puede ser de 16 mA y, en consecuencia, el conmutador de selección baja elige esta señal para manejar la velocidad de la bomba, la cual es la condición de operación que se desea.

Si ahora se supone que el flujo de líquido saturado caliente disminuye y el nivel del tanque empieza a bajar, tan pronto como el nivel llega abajo del punto de control del controlador de nivel, en este controlador se tratará de hacer más lento el bombeo, mediante la reducción de la salida. Conforme continúa el descenso del nivel, la salida del controlador también sigue en descenso y, cuando llega por debajo de la salida del controlador de flujo, en el relé de selección baja se elige la salida del controlador de nivel para manejar la bomba. Se puede decir que el controlador de nivel "se superpone" al controlador de flujo.

Una consideración importante al diseñar un sistema de control por sobreposición es que, si en cualquiera de los controladores existe modo integral de control, también debe existir protección contra reajuste excesivo; la salida del controlador se debe detener en 20 mA y no a un valor más alto. En la figura 8-40 se muestra una conexión de reajuste por retroalimentación (FB) para el controlador de flujo FIC50, el cual es un método para implementar la protección contra reajuste excesivo, como se explicó en la sección 6-5. En la figura 6-29b se supone que la salida del controlador va a la bomba; en la figura 8-40 la salida que va a la bomba es la del relé de selección baja, por lo tanto, esta señal se utiliza como reajuste por retroalimentación. En el presente ejemplo el controlador de nivel es únicamente proporcional; si fuera un controlador PI, entonces se requeriría también protección contra reajuste excesivo, ya que de otra manera nunca se superpone al controlador de flujo antes de que se inicie la cavitación.

Como se mencionó al inicio de esta sección y se vio en este ejemplo, el control por sobreposición se utiliza como un esquema de protección; tan pronto como el proceso regresa a sus condiciones normales de operación, el esquema de sobreposición regresa automáticamente a su estado de operación normal.

El control selectivo es otro esquema de control interesante que se utiliza en las industrias de proceso, su principio e implementación se exponen mediante dos ejemplos. Primero se considera el reactor catalítico exotérmico de tubo que se muestra en la figura 8-41, en la cual también aparece el perfil típico de la temperatura a lo largo del reactor. Se desea controlar la temperatura del reactor en el punto de mayor temperatura, como se observa en la figura; sin embargo, conforme envejece el catalizador o cambian las condiciones, el punto de mayor temperatura se mueve. En este caso se desea diseñar un esquema de control donde la variable que se mide se "mueva" conforme se mueve el punto de mayor temperatura, lo cual se ilustra en la figura 8-42. Con este esquema, en el selector de altas siempre se elige el transmisor con la salida más alta, y de esta manera la variable de proceso del controlador siempre está en la temperatura más alta.

Una consideración importante al implementar este esquema de control es que el rango de todos los transmisores de temperatura debe ser el mismo para que las señales de salida se puedan comparar sobre una misma base; otra consideración importante es instalar alguna clase de indicador para saber en qué transmisor se tiene la señal más alta. Si el punto de calor se mueve más allá del último transmisor, TT11D, esto puede ser signo de que es tiempo de regenerar o de cambiar el catalizador. La longitud del reactor que queda para la reacción probablemente no es suficiente para obtener la conversión que se desea.

En la figura 8-43 se muestra otro proceso interesante en el que se puede mejorar la operación mediante el control selectivo. En este proceso se calienta aceite (Dowtherm) en un horno, como una fuente de energía para proveer a varias unidades de proceso. En cada unidad individual se manipula el flujo de aceite para mantener la variable controlada en el punto de control; además, la temperatura del aceite que sale del horno también se controla mediante la manipulación del flujo de combustible. Con el fin de simplificar el diagrama, no se muestra el sistema de control de la razón aire/combustible, pero el lector debe recordar que se debe implementar éste. Para asegurar el retorno del aceite al horno se instala un circuito de control de reciclaje, DPC101.

Si se supone que se observa que la válvula de control de temperatura en cada unidad no se abre mucho, es decir, TV101 se abre un 20%, TV102 un 15% y TV103 un 30%, esto indica que la temperatura del aceite que sale del horno es bastante alta y, en consecuencia, no se necesita mucho flujo de aceite, por lo cual la mayor parte de éste no pasa por los usuarios. Esta situación es muy ineficiente energéticamente, ya que para obtener una temperatura elevada del aceite se debe quemar una cantidad grande de combustible, y mucha de la energía que se obtiene del combustible se pierde también en el entorno del sistema de tubería y a través de los gases de escape.

La operación más eficiente es aquella donde la temperatura del aceite que sale del horno es la justa para proporcionar la energía necesaria a los usuarios, con casi nada de flujo a través de la válvula de reciclaje (libramiento); en este caso las válvulas de control de temperatura estarían abiertas casi completamente. En la figura 8-44 se muestra un esquema de control selectivo con el que se logra este tipo de operación; la estrategia consiste en controlar la temperatura del aceite que sale del horno, de manera que sea justamente la necesaria (es decir, el aceite estará tan frío como sea posible) para mantener las válvulas de control de temperatura casi totalmente abiertas. Para hacer esto primero se elige la válvula que tenga mayor abertura con un selector de alta, TY101, y posteriormente se controla ésta mediante el controlador de posición de la válvula, VPC101, según la abertura que se desee de la misma, por ejemplo, 90% de abertura. En el controlador, este trabajo de control se realiza mediante la manipulación del punto de control del controlador de temperatura del horno.

La válvula con mayor abertura se selecciona mediante la comparación de las señales neumáticas que llegan a cada válvula; en consecuencia, para que esta comparación sea correcta, las características de todas las válvulas deben ser las mismas.

En el esquema de control se observa que, con un poco de lógica, se puede mejorar significativamente la operación de un proceso, en este caso mediante la minimización de las pérdidas de energía. En el ejemplo también se demuestra la facilidad de la implementación de la estrategia de control.

## 8-6. CONTROL DE PROCESO MULTIVARIABLE

Hasta este punto, en el estudio del control automático de proceso únicamente se consideraron procesos con una sola variable controlada y manipulada; dichos procesos se conocen como de entrada simple y salida simple (ESSS) (SISO por sus siglas en inglés). Sin embargo, frecuentemente se tienen procesos en los que se debe controlar más de una variable; éstos se denominan **procesos multivariables** o procesos de múltiples entradas y múltiples salidas (MEMS) (MIMO por sus siglas en inglés); en la figura 8-45 se muestran algunos ejemplos de tales procesos.

En la figura 8-45a se describe un sistema de mezcla donde es necesario controlar el flujo de salida y la fracción de masa que sale de un componente A; para lograr tal objetivo se utilizan dos válvulas: una para controlar la corriente A, y otra para la corriente B. En la figura 8-45b se muestra un reactor químico en el cual se necesita controlar la temperatura de salida y la composición; en este proceso las variables manipuladas son el flujo de agua para enfriamiento y el flujo de salida del proceso. En la figura 8-45c se ilustra un evaporador en el que el nivel y la concentración a la salida son las variables controladas, y el flujo de salida del proceso y el flujo de vapor, las variables manipuladas. En la figura 8-45d se muestra una máquina secadora de papel, las variables controladas son la humedad y el peso del producto final (fibras/area), las dos variables manipuladas son el flujo del depósito a la máquina y el flujo de vapor que llega al último grupo de tambores de secado. Por último, en la figura 8-45e se describe una columna típica de destilación con las variables controladas necesarias; presión en la columna, composición del destilado, nivel del acumulador, nivel básico y temperatura de la charola; para completar este control se utilizan cinco variables manipuladas: flujo de agua para enfriamiento -la cual llega al condensador-, flujo del destilado, reflujo, flujo de los sedimentos y flujo de vapor que llega al rehervidor.

En los ejemplos anteriores se observa que el control de estos procesos puede ser completamente complejo y motivante para el ingeniero de proceso. Generalmente, el ingeniero se debe hacer tres preguntas cuando se enfrenta con un problema de control de este tipo:

1. ¿Cuál es la "mejor" agrupación por pares de variables controladas y manipuladas?
2. ¿Cuánta interacción existe entre los diferentes circuitos de control y cómo afecta a la estabilidad de los circuitos?
3. ¿Se puede hacer algo para reducir la interacción entre los circuitos?

En esta sección se muestra cómo responder tales preguntas mediante técnicas simples y probadas. Para empezar se presenta una breve explicación sobre gráficas de flujo de señal (GFS) (SFG por sus siglas en inglés); GFS es un método conveniente y fácil para reducir a funciones de transferencia los diagramas de bloques complicados, y será útil para contestar la pregunta 2. A continuación se analizan las preguntas individualmente.

### Gráficas de flujo de señal (GFS)

Las gráficas de flujo de señal (GFS) son representaciones gráficas de las funciones de transferencia con que se describen a los sistemas de control. Para sistemas complejos es mucho más fácil desarrollar la función de transferencia de circuito cerrado y la ecuación característica mediante la utilización de técnicas GFS que mediante la utilización de los métodos de diagramas de bloques que se estudiaron en el capítulo 3. En esta sección se presenta la técnica GFS, pero para una presentación más detallada se remite al lector a la referencia bibliográfica 6.

En la figura 8-46a se muestra la representación gráfica de una función de transferencia en diagrama de bloques y en gráfica de flujo de señal. La figura 8-46b es la representación de un sistema de control por retroalimentación en ambas formas.

Antes de pasar a las reglas de GFS es importante definir algunos términos.

- La **variable** se representa mediante un **nodo**.
- La **función de transferencia** se representa por medio de una **rama**, una línea con una flecha, la cual relaciona los nodos que une.
- Una **trayectoria** es una sucesión unidireccional y continua de ramas, a lo largo de la cual no se pasa por ningún nodo más de una vez.
- La **función de transferencia de trayectoria** es el producto de las ramas de las funciones de transferencia que se encuentran al recorrer la trayectoria.
- Un **circuito** es una trayectoria que se origina y termina en el mismo nodo.

En la GFS de la figura 8-46b se encuentran los siguientes valores:

Trayectoria:
$$R \rightarrow E \rightarrow M \rightarrow F \rightarrow C$$

Función de transferencia de la trayectoria:
$$= G_c(s)G_v(s)G_p(s)$$

Circuito:
$$E \rightarrow M \rightarrow F \rightarrow C \rightarrow E$$

Función de transferencia del circuito:
$$= -G_c(s)G_v(s)G_p(s)H(s)$$

En la figura 8-47 se muestran algunas de las reglas que se necesitan en el álgebra de las gráficas de flujo de señal.

Con dichas reglas y las definiciones anteriores se puede determinar la función de transferencia que se requiere, a partir de la gráfica de flujo de señal. Con este propósito se utiliza la **fórmula de ganancia de Mason**:

$$T = \frac{\sum_i P_i\Delta_i}{\Delta} \quad (8-27)$$

donde:
- $T$ = factor de transmisión (función de transferencia) entre el nodo de entrada y el de salida.
- $P_i$ = producto de la función de transferencia en la i-ava trayectoria hacia adelante entre el nodo de entrada y el de salida
- $\Delta$ = determinante de la gráfica de flujo de señal o ecuación característica
$$= 1 - (-1)^{j+1}\sum L_j = 1 - \sum L_1 + \sum L_2 - \sum L_3 + \ldots$$
- $L_1$ = producto de todas las funciones de transferencia en el circuito individual $j$
- $L_2$ = producto de todas las funciones de transferencia en el grupo $j$ de 2 circuitos que no se tocan
- $L_3$ = producto de todas las funciones de transferencia en el grupo $j$ de 3 circuitos que no se tocan
- $L_k$ = producto de todas las funciones de transferencia en el grupo $j$ de $k$ circuitos que no se tocan
- $\Delta_i$ = evaluación de $\Delta$ con circuitos que tocan $P_i$ eliminados

Los circuitos que se tocan son aquellos que al menos tienen un nodo en común.

Ahora se verán varios ejemplos acerca de la utilización de GFS para obtener las funciones de transferencia que se desean.

**Ejemplo 8-7.** Se considera el diagrama de bloques que aparece en la figura 8-46b y se utiliza la gráfica de flujo de señal para determinar las funciones de transferencia de circuito cerrado.

$$\frac{C(s)}{R(s)} \qquad \text{y} \qquad \frac{C(s)}{L(s)}$$

En la figura 8-46b se muestra la gráfica de flujo de señal para este diagrama de bloques. Para la primera de las funciones de transferencia que se requieren:

$$T = \frac{C(s)}{R(s)}$$

sólo hay una trayectoria hacia adelante entre el nodo de entrada, $R(s)$, y el nodo de salida, $C(s)$. También existe un solo circuito, por lo tanto:

Trayectoria:
$$P_1 = G_c(s)G_v(s)G_p(s)$$

Circuito:
$$L_{11} = -G_c(s)G_v(s)G_p(s)H(s)$$

$$\Delta = 1 + G_c(s)G_v(s)G_p(s)H(s)$$

Puesto que sólo con un circuito se toca la trayectoria hacia adelante, $\Delta_1 = 1$; entonces, se puede determinar que:

$$\sum_i P_i\Delta_i = G_c(s)G_v(s)G_p(s)$$

Finalmente, se encuentra:

$$\frac{C(s)}{R(s)} = \frac{G_c(s)G_v(s)G_p(s)}{1 + G_c(s)G_v(s)G_p(s)H(s)}$$

el cual es el resultado que se esperaba.

Para la otra función de transferencia que se requiere:

$$T = \frac{C(s)}{L(s)}$$

también en este caso sólo hay una trayectoria entre el nodo de entrada, $L(s)$, y el nodo de salida, $C(s)$, y sólo un lazo de este sistema toca a la trayectoria, de manera que:

Trayectoria:
$$P_1 = G_p(s)$$

Circuito:
$$L_{11} = -G_c(s)G_v(s)G_p(s)H(s)$$

$$\Delta = 1 + G_c(s)G_v(s)G_p(s)H(s)$$
$$\Delta_1 = 1$$

Entonces, se encuentra que:

$$\sum_i P_i\Delta_i = G_p(s)$$

Y, finalmente, se obtiene:

$$\frac{C(s)}{L(s)} = \frac{G_p(s)}{1 + G_c(s)G_v(s)G_p(s)H(s)}$$

el cual es nuevamente el resultado que se esperaba.

**Ejemplo 8-8.** Ahora se considera el diagrama de bloques del sistema de control en cascada que aparece en la figura 8-48a y se debe obtener:

$$\frac{C_2(s)}{R(s)}$$

Para determinar $T = \frac{C_2(s)}{R(s)}$, el primer paso es dibujar la gráfica de flujo de señal, como se muestra en la figura 8-48b.

Sólo existe una trayectoria entre $R(s)$ y $C_2(s)$ con la cual se tocan los dos circuitos del sistema; además, ambos circuitos se tocan entre sí.

Trayectoria:
$$P_1 = G_{c_2}(s)G_{c_1}(s)G_v(s)G_1(s)G_2(s)$$

Circuitos:
$$L_{11} = -G_{c_1}(s)G_1(s)G_v(s)H_1(s)$$
$$L_{12} = -G_{c_2}(s)G_{c_1}(s)G_v(s)G_1(s)G_2(s)H_2(s)$$

$$\Delta = 1 + G_{c_1}(s)G_1(s)G_v(s)H_1(s) + G_{c_2}(s)G_{c_1}(s)G_v(s)G_1(s)G_2(s)H_2(s)$$

Puesto que se toca la trayectoria única con ambos circuitos, $\Delta_1 = 1$, y se encuentra que:

$$\sum_i P_i\Delta_i = G_{c_2}(s)G_{c_1}(s)G_v(s)G_1(s)G_2(s)$$

Y, finalmente, se obtiene:

$$\frac{C_2(s)}{R(s)} = \frac{G_{c_2}(s)G_{c_1}(s)G_v(s)G_1(s)G_2(s)}{1 + G_{c_1}(s)G_1(s)G_v(s)H_1(s) + G_{c_2}(s)G_{c_1}(s)G_v(s)G_1(s)G_2(s)H_2(s)}$$

**Ejemplo 8-9.** Se considera el diagrama de bloques de la figura 8-49a, con el cual se describe un sistema multivariable 2 x 2. Para simplificar el diagrama de bloques se puede definir lo siguiente:

$$G_{p_{11}}(s) = G_{v_1}(s)G_{11}(s)G_{m_1}(s)$$
$$G_{p_{12}}(s) = G_{v_2}(s)G_{12}(s)G_{m_1}(s)$$
$$G_{p_{21}}(s) = G_{v_1}(s)G_{21}(s)G_{m_2}(s)$$
$$G_{p_{22}}(s) = G_{v_2}(s)G_{22}(s)G_{m_2}(s)$$

Por lo tanto, el diagrama de bloques es el que se muestra en la figura 8-49b. Se debe determinar:

$$\frac{C_1(s)}{R_1(s)}, \qquad \frac{C_1(s)}{R_2(s)}$$

Como se hace generalmente, primero se dibuja el diagrama de bloques en forma de gráfica de flujo de señal, como se muestra en la figura 8-50.

Primero se obtiene:

$$T = \frac{C_1(s)}{R_1(s)}$$

En este sistema existen varios circuitos y trayectorias posibles.

Trayectorias:
$$P_1 = G_{c_1}(s)G_{p_{11}}(s)$$

Circuitos:
$$-L_{11} = -G_{c_1}(s)G_{p_{11}}(s)$$
$$L_{12} = -G_{c_2}(s)G_{p_{22}}(s)$$
$$L_{13} = G_{c_1}(s)G_{p_{21}}(s)G_{c_2}(s)G_{p_{12}}(s)$$
$$L_{14} = G_{c_1}(s)G_{p_{11}}(s)G_{c_2}(s)G_{p_{22}}(s)$$

Los circuitos $L_{11}$ y $L_{12}$ son los de retroalimentación que ya se conocen. El circuito $L_{13}$ es más complicado y pasa a través de ambos circuitos de retroalimentación. El circuito $L_{14}$ es el producto de multiplicar los circuitos $L_{11}$ y $L_{12}$, ya que son circuitos que no se tocan. Entonces, se obtiene:

$$\Delta = 1 + G_{c_1}(s)G_{p_{11}}(s) + G_{c_2}(s)G_{p_{22}}(s) - G_{c_1}(s)G_{p_{21}}(s)G_{c_2}(s)G_{p_{12}}(s)$$
$$+ G_{c_1}(s)G_{p_{11}}(s)G_{c_2}(s)G_{p_{22}}(s)$$

Si se utiliza álgebra, la $\Delta$ se puede escribir como sigue:

$$\Delta = [1 + G_{c_1}(s)G_{p_{11}}(s)][1 + G_{c_2}(s)G_{p_{22}}(s)] - G_{c_1}(s)G_{p_{21}}(s)G_{c_2}(s)G_{p_{12}}(s)$$

Este último paso no es necesario, sin embargo, se verá que es útil en el estudio de la estabilidad del control multivariable que se hará posteriormente en este capítulo. Se continúa para encontrar:

$$\Delta_1 = 1 + G_{c_2}(s)G_{p_{22}}(s)$$

De lo anterior, se ve que:

$$\sum_i P_i\Delta_i = G_{c_1}(s)G_{p_{11}}(s)[1 + G_{c_2}(s)G_{p_{22}}(s)]$$

Y, finalmente, se obtiene:

$$\frac{C_1(s)}{R_1(s)} = \frac{G_{c_1}(s)G_{p_{11}}(s)[1 + G_{c_2}(s)G_{p_{22}}(s)]}{[1 + G_{c_1}(s)G_{p_{11}}(s)][1 + G_{c_2}(s)G_{p_{22}}(s)] - G_{c_1}(s)G_{p_{21}}(s)G_{c_2}(s)G_{p_{12}}(s)}$$

Para la otra función de transferencia que se busca:

$$T = \frac{C_1(s)}{R_2(s)}$$

los circuitos son los mismos, pero las trayectorias cambian:

Trayectoria:
$$P_1 = G_{c_2}(s)G_{p_{12}}(s)$$

Por lo tanto, $\Delta_1 = 1$ y:

$$\sum_i P_i\Delta_i = G_{c_2}(s)G_{p_{12}}(s)$$

Finalmente, se ve que:

$$\frac{C_1(s)}{R_2(s)} = \frac{G_{c_2}(s)G_{p_{12}}(s)}{[1 + G_{c_1}(s)G_{p_{11}}(s)][1 + G_{c_2}(s)G_{p_{22}}(s)] - G_{c_1}(s)G_{p_{21}}(s)G_{c_2}(s)G_{p_{12}}(s)}$$

Como se vio en estos ejemplos, la técnica de gráfica de flujo de señal es una herramienta simple y poderosa, la cual representa una manera de obtener las funciones de transferencia de circuito cerrado que serían difíciles de obtener mediante el álgebra de diagramas de bloques.

### Selección de pares de variables controladas y manipuladas

La primera pregunta que se hizo al principio de esta sección se relaciona con la forma de agrupar por pares (parear) las variables controladas y las manipuladas. La mayoría de las veces, la decisión sobre la agrupación por pares es simple, pero algunas veces es más difícil. Ejemplos de casos difíciles son el sistema de mezcla que aparece en la figura 8-45a y el reactor químico que se muestra en la figura 8-45b. Para estos ejemplos existe una técnica con la que se tiene éxito en numerosos procesos industriales; se utiliza un procedimiento 2 x 2 para presentar los fundamentos de la técnica (ver figura 8-51); después de hacer esto, se extiende el método a procesos $n \times n$. En esta notación la primera $n$ es la cantidad de variables controladas, y la segunda $n$ es la cantidad de variables manipuladas.

Para empezar, tiene sentido que cada variable controlada se controle mediante la variable manipulada que ejerce mayor "influencia" sobre aquélla. En este contexto, la influencia y la ganancia tienen el mismo significado y, en consecuencia, para tomar una decisión se deben encontrar todas las ganancias del proceso (4 ganancias para un sistema 2 x 2). Específicamente, las ganancias de estado estacionario de circuito abierto de interés son las siguientes:

$$K_{11} = \frac{\partial c_1}{\partial m_1}\bigg|_{m_2}$$
$$K_{12} = \frac{\partial c_1}{\partial m_2}\bigg|_{m_1}$$
$$K_{21} = \frac{\partial c_2}{\partial m_1}\bigg|_{m_2}$$
$$K_{22} = \frac{\partial c_2}{\partial m_2}\bigg|_{m_1}$$

donde $K_{ij}$ es la ganancia que relaciona la variable controlada $i$ con la variable manipulada $j$.

Las cuatro ganancias se pueden ordenar en forma de matriz, a fin de tener una descripción gráfica de su relación con las variables controlada y manipulada. La matriz se conoce como **matriz de ganancia de estado estacionario (MGEE)** (SSGM por sus siglas en inglés), y se muestra en la figura 8-52.

Con base en esta MGEE, parecería que debiera elegirse la combinación de variable controlada y manipulada con que se obtiene el valor absoluto más grande en cada línea; es decir, si $|K_{12}|$ es mayor que $|K_{11}|$, entonces se debe elegir $m_2$ para controlar a $c_1$; sin embargo, esta manera de elegir el par de variable controlada y manipulada no es completamente correcta, ya que las ganancias $K_{ij}$ pueden tener diferentes unidades y, consecuentemente, no es posible hacer la comparación. Como se ve, la matriz depende de las unidades y, por lo tanto, no es útil para este propósito.

Para normalizar la MGEE y hacerla independiente de las unidades, se propone una técnica que desarrolló Bristol, cuyos resultados probaron ser buenos; dicha técnica se denomina **ganancia relativa de la matriz (GRM)** o medida de interacción.

En la forma en que la propuso Bristol, los términos de la GRM se definen como sigue:

$$\mu_{ij} = \frac{K_{ij}}{K'_{ij}} \quad (8-28)$$

o, en general:

$$\mu_{ij} = \frac{\text{ganancia cuando se abren los demás circuitos}}{\text{ganancia cuando se cierran los demás circuitos}}$$

Para asegurar que se entienda el significado e importancia de todos los términos de la ecuación (8-28), se analizan a continuación. El numerador:

$$K_{ij} = \frac{\partial c_i}{\partial m_j}\bigg|_{m_k, k \neq j}$$

es la ganancia de estado estacionario, $K_{ij}$, que se definió anteriormente; es decir, es la ganancia de $m_j$ sobre $c_i$ cuando todas las demás variables manipuladas se mantienen constantes. El denominador:

$$K'_{ij} = \frac{\partial c_i}{\partial m_j}\bigg|_{\text{todos los demás circuitos cerrados}}$$

es otro tipo de ganancia, $K'_{ij}$; ésta es la ganancia de $m_j$ sobre $c_i$ cuando se cierran todos los demás circuitos, y se supone que los demás controladores tienen acción integral; por lo tanto, todas las demás variables controladas regresan a su punto de control. En consecuencia, se puede escribir:

$$\mu_{ij} = \frac{\text{ganancia cuando se abren los demás circuitos}}{\text{ganancia cuando se cierran los demás circuitos}}$$

Como se aprecia en esta definición, el término de ganancia relativa es una cantidad sin dimensiones, la cual se puede utilizar para decidir la agrupación por pares de las variables controlada y manipulada.

Una vez que se evalúan los términos de ganancia relativa, es posible formar la matriz de ganancia relativa que se muestra en la figura 8-53; a partir de dicha matriz se puede hacer la agrupación por pares de variables controlada y manipulada. Antes de presentar la regla de agrupación por pares se tratará de lograr una mejor comprensión de los términos de ganancia relativa.

Una propiedad de la matriz de ganancia relativa es que la suma de todos los términos en cada columna debe ser igual a uno, lo cual quiere decir que, para un sistema 2 x 2, únicamente se requiere evaluar un término, y los otros se pueden obtener mediante esta propiedad. En un sistema 3 x 3, en el cual existen nueve términos en la matriz, sólo se necesita evaluar cuatro términos independientes, y los otros se obtienen mediante aritmética simple. Esta propiedad se probará posteriormente en la presente sección.

Antes de proceder a la evaluación de $\mu_{ij}$ se debe comprender su significado. A partir de la definición de $\mu_{ij}$, se observa que es una medida del efecto de cerrar todos los demás circuitos sobre la ganancia de proceso para un cierto par de variable controlada y manipulada. Por lo tanto, el valor numérico de $\mu_{ij}$ es una medida de la interacción entre los circuitos.

Si $\mu_{ij} = 1$, esto significa que, cuando se abren todos los demás circuitos, la ganancia del proceso es la misma que cuando se cierran; esto indica que entre el circuito de interés y los demás circuitos no hay interacción o posible interacción que elimine la desviación. Cuanto más se desvía $\mu_{ij}$ de 1, tanto mayor es la interacción entre los circuitos.

Si $\mu_{ij} = 0$, esto puede deberse a dos posibilidades: primera, la ganancia de circuito abierto, $\partial c_i/\partial m_j$, puede ser cero, en este caso $m_j$ no afecta a $c_i$, al menos en términos de lazos abiertos. Segunda, la ganancia de circuito cerrado es tan grande que $\mu_{ij} = 0$, esto significa que los demás interactúan en gran medida con el circuito de interés para mantener constantes las otras variables. En todo caso, cualquiera de las dos posibilidades indica que $c_i$ no se debe controlar con $m_j$.

Si $\mu_{ij} = \infty$, la ganancia de circuito cerrado es cero o muy pequeña, lo cual significa que, cuando los demás circuitos se sitúan en automático, el lazo de interés no se puede controlar, porque $m_j$ afecta a $c_i$ muy poco o nada en absoluto. La única forma de controlar este circuito es colocar los demás circuitos en manual, y ciertamente, esta situación no es deseable.

En los tres últimos párrafos se presentaron los casos extremos del problema de multivariables. En general, los valores de ganancias relativas cercanos a la unidad representan combinaciones de variables controlada y manipulada que se pueden controlar; los valores de las ganancias relativas que tienden a cero representan combinaciones que no se pueden controlar.

Con esta base se puede presentar la regla para parear las variables controlada y manipulada. Bristol presentó primero esta regla de agrupación por pares y, posteriormente, Koppel la modificó como sigue:

> Siempre se agrupan por pares los elementos positivos de la MGR más cercanos a 1.0. La estabilidad de los pares se verifica mediante el teorema de Niederlinski; si el par da origen a un sistema inestable, entonces se elige otro par positivo con valores cercanos a 1.0. Siempre que sea posible, se evitará la agrupación por pares negativa.

El **teorema de Niederlinski** es una forma conveniente de verificar la estabilidad del par que se propone. En la utilización de este teorema se supone que los pares propuestos son los elementos en diagonal, $m_j - c_j$, en la MGEE. Por lo tanto, el enunciado del teorema es:

> El sistema de circuito cerrado que resulta de agrupar por pares $m_1 - c_1, m_2 - c_2, \ldots, m_n - c_n$, es inestable si y sólo si
> $$\frac{|MGEE|}{\prod_{i=1}^{n}K_{ii}} < 0$$
> donde $|MGEE|$ es el determinante de MGEE y $K_{ii}$ son los elementos en diagonal de la matriz.

La regla de agrupación por pares que se propone es conveniente y fácil de utilizar, se observará que únicamente se necesita información de estado estacionario, lo cual es ciertamente una ventaja, ya que esta información se puede obtener durante la etapa de diseño del proceso y, por tanto, no se requiere que la planta o el proceso estén en operación. En la próxima sección se abordarán diferentes formas para obtener las ganancias de estado estacionario. Para una exposición amplia de la regla de agrupación por pares (pareo) y el tema completo de control multivariable, se recomienda al lector leer la monografía de McAvoy.

Para concluir esta presentación, se estudiarán dos MGR posibles y se explicará qué indican los términos $\mu_{ij}$ sobre el sistema de control. Primero se considera la siguiente MGR:

| | $m_1$ | $m_2$ |
|---|---|---|
| $c_1$ | 0.2 | 0.8 |
| $c_2$ | 0.8 | 0.2 |

Los términos $\mu_{11} = \mu_{22} = 0.2 = 1/5$ indican que con este par la ganancia de cada circuito se incrementa en un factor de 5 cuando se cierra el otro circuito. Los términos $\mu_{12} = \mu_{21} = 0.8 = 4/5$ indican que con este par la ganancia se incrementa únicamente en un factor de 1.25. Con esto se explica por qué la agrupación por pares de $c_1 - m_2$ y $c_2 - m_1$ es la correcta.

Ahora se considera otra MGR:

| | $m_1$ | $m_2$ |
|---|---|---|
| $c_1$ | 2 | -1 |
| $c_2$ | -1 | 2 |

Los términos $\mu_{11} = \mu_{22} = 2 = \sqrt{0.5}$ indican que la ganancia de cada circuito se corta a la mitad cuando se cierra el otro circuito. Los términos $\mu_{12} = \mu_{21} = -1$ indican que la ganancia de cada circuito cambia de signo cuando se cierra el otro circuito; ciertamente, este último caso no es deseable, ya que significa que la acción del controlador depende de que el otro lazo se abra o se cierre, con lo cual se explica por qué la agrupación por pares correcta es $c_1 - m_1$ y $c_2 - m_2$.

**Obtención de las ganancias del proceso y de las ganancias relativas.** El proceso de mezcla que se muestra en la figura 8-45a se utiliza para revisar los métodos con que se obtienen las ganancias de circuito abierto y para presentar la evaluación de las ganancias relativas.

Para obtener analíticamente las ganancias de estado estacionario con circuito abierto, primero se escriben las ecuaciones con que se describe el proceso; a partir de estas ecuaciones se evalúan las ganancias, $K_{ij}$. En el sistema de mezclado se debe controlar el flujo de salida, $F$, y la fracción de masa que sale del componente A, $x$. La expresión para el flujo de salida se deriva de un balance de masa total en estado estacionario:

$$F = A + S \quad (8-29)$$

De un balance de masa de estado estacionario del componente A se obtiene la otra expresión que se requiere:

$$Fx = A$$

o:

$$x = \frac{A}{F}$$

Se substituye la ecuación (8-29) en la ecuación para $x$ y se obtiene:

$$x = \frac{A}{A + S} \quad (8-30)$$

En este sistema 2 x 2 hay cuatro ganancias de circuito abierto: $K_{FA}$, $K_{FS}$, $K_{xA}$ y $K_{xS}$. A partir de la ecuación (8-29) se pueden evaluar las primeras dos:

$$K_{FA} = \frac{\partial F}{\partial A}\bigg|_S = 1$$
$$K_{FS} = \frac{\partial F}{\partial S}\bigg|_A = 1$$

A partir de la ecuación (8-30) es posible evaluar las dos últimas ganancias, como:

$$K_{xA} = \frac{\partial x}{\partial A}\bigg|_S = \frac{S}{(A+S)^2} = \frac{1-x}{F}$$
$$K_{xS} = \frac{\partial x}{\partial S}\bigg|_A = -\frac{A}{(A+S)^2} = -\frac{x}{F}$$

En consecuencia, la matriz de ganancia de estado estacionario es:

| | A | S |
|---|---|---|
| F | 1 | 1 |
| x | $\frac{1-x}{F}$ | $-\frac{x}{F}$ |

El desarrollo del sistema de ecuaciones descriptivo y la evaluación de las ganancias fue bastante simple para este proceso de mezclado. En algunos procesos esto no se hace fácilmente, por ejemplo, en la columna de destilación, en la máquina de papel y en el reactor químico que aparecen en la figura 8-45. Para estos procesos el sistema de ecuaciones con que se les describe es complejo y, en consecuencia, la evaluación de las ganancias se convierte en una tarea difícil; afortunadamente, el diseño de muchos procesos se hace generalmente mediante simulaciones de estado estacionario por computadora, a partir de las cuales es fácil evaluar las ganancias que se requieren; cuando se trata de un sistema 2 x 2, bastan tres corridas en la computadora para obtener las cuatro ganancias. En estos casos no se puede utilizar el diferencial de las variables para obtener las ganancias, sino que se utiliza la siguiente aproximación:

$$K_{ij} \approx \frac{\Delta c_i}{\Delta m_j}$$

Si por alguna razón es imposible utilizar el método analítico o el de simulación por computadora, existe otro método para obtener $K_{ij}$ cuando se requiere. Dicho método consiste en obtener los datos necesarios para evaluar las ganancias; la técnica para obtener las ganancias de circuito abierto puede ser cualquiera de las técnicas de identificación que se estudiaron hasta ahora, por ejemplo, la prueba de escalón (capítulo 6).

Una vez que se obtienen las ganancias de circuito abierto, la evaluación de las demás ganancias $K'_{ij}$ y los términos de ganancia relativa es bastante directa. Primero se presenta un método para cualquier sistema 2 x 2 y luego se extiende para cualquier sistema de orden superior.

El efecto de un cambio en las variables manipuladas sobre $c_1$ se puede expresar como sigue:

$$\Delta c_1 = K_{11}\Delta m_1 + K_{12}\Delta m_2 \quad (8-31)$$

De manera semejante, para $c_2$ se tiene:

$$\Delta c_2 = K_{21}\Delta m_1 + K_{22}\Delta m_2 \quad (8-32)$$

Para obtener la ganancia:

$$K'_{11} = \frac{\partial c_1}{\partial m_1}\bigg|_{c_2}$$

En la ecuación (8-32) se iguala $\Delta c_2$ a cero:

$$0 = K_{21}\Delta m_1 + K_{22}\Delta m_2$$
$$\Delta m_2 = -\frac{K_{21}}{K_{22}}\Delta m_1$$

Esta expresión para $\Delta m_2$ se substituye en la ecuación (8-31), con lo que se obtiene:

$$\Delta c_1 = K_{11}\Delta m_1 - \frac{K_{12}K_{21}}{K_{22}}\Delta m_1$$

y, finalmente, se tiene:

$$K'_{11} = \frac{\Delta c_1}{\Delta m_1}\bigg|_{c_2} = \frac{K_{11}K_{22} - K_{12}K_{21}}{K_{22}} \quad (8-33)$$

De manera semejante, para la ganancia:

$$K'_{12} = \frac{\partial c_1}{\partial m_2}\bigg|_{c_1}$$

En la ecuación (8-31) se iguala $\Delta c_1$ a cero:

$$0 = K_{11}\Delta m_1 + K_{12}\Delta m_2$$
$$\Delta m_1 = -\frac{K_{12}}{K_{11}}\Delta m_2$$

Esta expresión para $\Delta m_1$ se substituye en la ecuación (8-32), con lo que se obtiene:

$$\Delta c_2 = -\frac{K_{21}K_{12}}{K_{11}}\Delta m_2 + K_{22}\Delta m_2$$

y, finalmente, se obtiene:

$$K'_{12} = \frac{\Delta c_2}{\Delta m_2}\bigg|_{c_1} = \frac{K_{22}K_{11} - K_{21}K_{12}}{K_{11}} \quad (8-34)$$

Se sigue el mismo procedimiento para evaluar las otras dos ganancias $K'_{21}$ y $K'_{22}$:

$$K'_{21} = \frac{\Delta c_2}{\Delta m_1}\bigg|_{c_2} = \frac{K_{11}K_{22} - K_{12}K_{21}}{K_{12}} \quad (8-35)$$

Y:

$$K'_{22} = \frac{\Delta c_2}{\Delta m_2}\bigg|_{c_1} = \frac{K_{21}K_{12} - K_{11}K_{22}}{K_{21}} \quad (8-36)$$

Es interesante e importante observar que las ganancias $K'_{ij}$ se pueden evaluar de manera simple mediante una combinación de ganancias de circuito abierto. Una vez que se obtienen dichas ganancias, la evaluación de las ganancias relativas se hace como sigue:

$$\mu_{11} = \frac{K_{11}}{K'_{11}} = \frac{K_{11}K_{22}}{K_{11}K_{22} - K_{12}K_{21}} \quad (8-37)$$

$$\mu_{22} = \frac{K_{22}}{K'_{22}} = \frac{K_{11}K_{22}}{K_{11}K_{22} - K_{12}K_{21}} \quad (8-38)$$

Las otras ganancias relativas se obtienen de manera similar:

$$\mu_{12} = \frac{K_{12}}{K'_{12}} = \frac{K_{12}K_{21}}{K_{12}K_{21} - K_{11}K_{22}} \quad (8-39)$$

$$\mu_{21} = \frac{K_{21}}{K'_{21}} = \frac{K_{12}K_{21}}{K_{12}K_{21} - K_{11}K_{22}} \quad (8-40)$$

Finalmente, la matriz de ganancia relativa es:

| | $m_1$ | $m_2$ |
|---|---|---|
| $c_1$ | $\frac{K_{11}K_{22}}{K_{11}K_{22} - K_{12}K_{21}}$ | $\frac{K_{12}K_{21}}{K_{12}K_{21} - K_{11}K_{22}}$ |
| $c_2$ | $\frac{K_{12}K_{21}}{K_{12}K_{21} - K_{11}K_{22}}$ | $\frac{K_{11}K_{22}}{K_{11}K_{22} - K_{12}K_{21}}$ |

La combinación correcta de variables controlada y manipulada se elige con base en esta matriz, mediante la regla de agrupación por pares que se presentó antes.

En la matriz se observa fácilmente que los términos en cada fila y en cada columna suman uno. También se observa fácilmente la consistencia dimensional de cada término.

Al aplicar la matriz de ganancia relativa al ejemplo del proceso de mezcla, se obtiene:

| | A | S |
|---|---|---|
| F | $\frac{1}{1-x}$ | $\frac{x}{1-x}$ |
| x | $-\frac{x}{1-x}$ | $\frac{x}{1-x}$ |

La agrupación por pares depende del valor de $x$; si $x > 0.5$, el par correcto es $F - A$ y $x - S$. Si $x < 0.5$, el par correcto será $F - S$ y $x - A$. Con un valor de $x = 0.5$ se logra que todas las $\mu$ sean iguales a 0.5. En un sistema 2 x 2 esto indica el grado más alto de interacción.

En los pasos que se siguieron para desarrollar la matriz de ganancia relativa para un sistema 2 x 2 se requiere únicamente álgebra simple. Para un sistema de orden superior se puede seguir el mismo procedimiento, sin embargo, se necesitan más pasos algebraicos para llegar a la solución final. En estos sistemas de orden superior se puede utilizar el álgebra de matrices para simplificar el desarrollo de la matriz de ganancia relativa. El procedimiento que propuso Bristol es el siguiente:

> Se calcula la transpuesta de la inversa de la matriz de estado estacionario y se multiplica cada término de la nueva matriz por el término correspondiente en la matriz original. Los términos que se obtienen son los de la "(matriz de) medida de interacción" o matriz de ganancia relativa.

A las personas que no están familiarizadas con el álgebra de matrices este procedimiento puede parecerles fuera de lugar, pero ya que este método es bastante útil, vale la pena superar dicha dificultad; existen computadoras digitales con las que se pueden generar los números necesarios. Con este procedimiento se obtiene la misma matriz de ganancia relativa que se obtuvo con el mostrado anteriormente en la aplicación a cualquier sistema 2 x 2.

**Índice de interacción.** Nisenfeld y Schultz definen el **índice de interacción** para un sistema multivariable en el que se utiliza la variable manipulada $m_j$ para controlar la variable $c_i$ de la siguiente manera:

$$I_{ij} = \left|\frac{K_{ij}K_{ji}}{K_{ii}K_{jj}}\right| \quad (8-41)$$

donde las barras indican el valor absoluto de la cantidad que encierran. Estos autores establecieron que, con un índice de interacción menor a uno, se evita la inestabilidad que se debe a la interacción de los circuitos.

A fin de lograr una mejor comprensión de este índice, se considera el sistema de mezclado que se muestra en la figura 8-54. Con el controlador de flujo se ajusta la corriente A, y con el controlador de composición se ajusta la corriente S.

Un índice de interacción propio de este proceso es:

$$I_{FA} = \left|\frac{K_{FA}K_{AF}}{K_{FF}K_{AA}}\right|$$

Si hay un cambio en el punto de control de la razón de flujo, se detecta una desviación $\Delta F$ en el controlador de flujo; la acción correctiva en este controlador sería $\Delta A = \frac{\Delta F}{K_{FA}}$ (en magnitud), para mover la razón de flujo a un nuevo punto de control; a causa de la interacción, con este cambio en la corriente A se provoca un cambio en la composición expresada por $\Delta x = K_{xA}\Delta A = \frac{K_{xA}}{K_{FA}}\Delta F$; este cambio en la composición se detecta en el controlador de composición, donde se toma una acción correctiva para regresar la composición al punto de control; la magnitud de esta acción sobre la corriente S es $\Delta S = \frac{\Delta x}{K_{xS}} = \frac{K_{xA}}{K_{FA}K_{xS}}\Delta F$. Finalmente, y nuevamente a causa de la interacción, este cambio en la corriente S ocasiona una desviación en la razón de flujo de magnitud $\Delta F' = K_{FS}\Delta S = \frac{K_{FS}K_{xA}}{K_{FA}K_{xS}}\Delta F = I_{FA}\Delta F$. Conforme se continúa, se observa que se completa un ciclo, el cual se repite hasta que todas las desviaciones se terminan. Se notará que, para que esto ocurra, el índice de interacción, $I_{FA}$, debe ser menor a la unidad, a fin de que después de completar un ciclo las desviaciones de flujo, $\Delta F'$, sean menores que la desviación, $\Delta F$, al inicio del ciclo. Si el índice de interacción es mayor que la unidad, las desviaciones se incrementarán después de cada ciclo, hasta que la salida del controlador llegue a la saturación, la cual es una situación altamente indeseable.

En los sistemas de orden superior, se pueden calcular los índices de interacción para cada agrupación por pares posible mediante la ecuación:

$$I_{ij} = \left|\frac{\mu_{ij} - 1}{\mu_{ij}}\right|$$

Aquellas combinaciones con las que se obtengan valores mayores a la unidad se deben descartar.

**Interacción positiva y negativa.** La **interacción positiva** es la interacción que existe cuando todos los términos de ganancia relativa son positivos. Es interesante observar bajo qué condiciones se da este tipo de interacción; se puede aprender mucho de la expresión de $\mu_{11}$ para un sistema 2 x 2:

$$\mu_{11} = \frac{K_{11}K_{22}}{K_{11}K_{22} - K_{12}K_{21}}$$

Si la cantidad de $K$ positivos es impar, entonces el valor de $\mu_{11}$ será positivo y, además, su valor numérico estará entre 0 y 1. La demostración de que ésta es una regla general es bastante simple, queda al lector hacerla.

La interacción positiva es el tipo más común de interacción en los sistemas de control multivariable. En estos sistemas existe "ayuda" de los circuitos de control entre sí; con el fin de explicar lo que esto significa, se considera el sistema de mezclado que aparece en la figura 8-54 y su diagrama de bloques que se muestra en la figura 8-55. En este sistema las ganancias de las válvulas de control son positivas, ya que ambas requieren aire para abrirse. Las ganancias $K_{11}$, $K_{12}$ y $K_{22}$ también son positivas; en cambio, la ganancia $K_{21}$ es negativa. El controlador de flujo, $G_{c_1}(s)$, es de acción inversa, en tanto que el controlador analizador, $G_{c_2}(s)$, es de acción directa. Ahora supóngase que el punto de control del controlador de flujo decrece (↓) y que, a su vez, la salida del controlador de flujo desciende, $G_{c_1}(s)$, con lo cual la salida de $G_{v_1}(s)$ y $G_{11}(s)$ decrece (↓). Puesto que $K_{21}$ es positiva, la salida de $G_{21}(s)$ también decrece (↓) cuando la salida de $G_{v_1}(s)$ decrece, de lo que resulta un descenso en el análisis $X(s)$ (↓); cuando esto sucede, la salida del controlador de análisis, $G_{c_2}(s)$, decrece (↓), lo cual ocasiona que la salida de $G_{v_2}(s)$ y $G_{22}(s)$ decrezca (↓) y que la salida de $G_{12}(s)$ se incremente (↑). En la figura 8-55 se muestran las flechas con que se indica la dirección en que se mueve la salida de cada bloque. En la figura se aprecia claramente que tanto la salida de $G_{11}(s)$ como la de $G_{12}(s)$ decrecen; esto significa que "ambos circuitos se ayudan entre sí".

Cuando existe una cantidad par de valores positivos de $K$ o una cantidad igual de valores positivos y negativos de $K$, el valor de $\mu_{11}$ es mayor de 1 o menor que 0; en cualquier caso, habrá algunas $\mu_{ij}$ con valores negativos en la misma fila y columna. En este caso se dice que la interacción es **negativa**. Es importante tener en cuenta que, para que un término de ganancia relativa sea negativo, los signos de las ganancias de circuito abierto y los de las ganancias de circuito cerrado deben ser diferentes, lo cual significa que la ganancia del controlador por retroalimentación debe ser inversa cuando se cierran los demás circuitos. En este tipo de interacción los circuitos de control se "combaten" entre sí; se deja al lector la demostración de esto.

**Ajuste del controlador en sistemas con interacción.** El ajuste de los controladores en los sistemas con interacción es una labor difícil. Shinskey recomienda ajustar cada controlador con los demás controladores en manual, de modo que, cuando se colocan en automático, se afina el ajuste (se retoca el ajuste); esta afinación se puede hacer con base en el término de ganancia relativa de ese circuito; específicamente, se multiplica la ganancia del controlador por el término de ganancia relativa (se multiplica la banda proporcional por el recíproco del término de la ganancia relativa). Esto se deriva del hecho de que los términos de ganancia relativa son iguales a la razón de la ganancia de circuito abierto respecto a la ganancia de circuito cerrado.

Si en el sistema de mezclado que se estudió anteriormente se desea que la concentración sea $x = 0.6$, los términos de ganancia relativa son $\mu_{FA} = \mu_{xS} = 0.6$ y la agrupación por pares apropiada es $F - A$ y $x - S$. Si con el controlador de composición en manual resulta una ganancia de 0.5 (200% PB) del ajuste del controlador de flujo, ésta se debe reajustar a $(0.6)(0.5) = 0.3$ (333% PB). Para la ganancia del controlador de composición que se obtiene mediante el ajuste con el controlador de flujo en manual se debe hacer una afinación semejante.

Es interesante observar que los términos de la matriz de ganancia relativa son útiles, no sólo como ayuda para decidir sobre la agrupación por pares de las variables controlada y manipulada, sino también para corregir los parámetros de ajuste del controlador que cuentan para la interacción.

### Interacción y estabilidad

Ahora se utiliza el sistema de mezclado de la figura 8-54 para contestar la pregunta acerca de la forma en que la interacción entre los circuitos afecta a la estabilidad de los mismos. La interacción que existe en este proceso se muestra gráficamente en la figura 8-55. Se notará que con cualquier cambio en la salida del controlador 1 no sólo se afecta a $C_1(s)$ sino también a $C_2(s)$, lo cual también es verdad para cualquier cambio en la salida del controlador 2.

Como se explicó en los capítulos 6 y 7, la estabilidad de los circuitos de control se define con las raíces de la ecuación característica. En el sistema de la figura 8-55 las ecuaciones características de cada circuito individual son:

$$1 + G_{c_1}(s)G_{v_1}(s)G_{11}(s)H_1(s) = 0 \quad (8-43)$$

Y:

$$1 + G_{c_2}(s)G_{v_2}(s)G_{22}(s)H_2(s) = 0 \quad (8-44)$$

Como ya se vio, cada circuito es estable si en las raíces de la ecuación característica hay partes reales negativas. Para analizar la estabilidad del sistema de control completo que aparece en la figura 8-55, primero se debe determinar la ecuación característica para el sistema completo; como se ve en el ejemplo 8-9, esta ecuación característica es:

$$[1 + G_{c_1}(s)G_{v_1}(s)G_{11}(s)H_1(s)][1 + G_{c_2}(s)G_{v_2}(s)G_{22}(s)H_2(s)]$$
$$- G_{c_1}(s)G_{v_1}(s)G_{c_2}(s)G_{v_2}(s)G_{12}(s)H_1(s)G_{21}(s)H_2(s) = 0 \quad (8-45)$$

Los términos entre corchetes son las ecuaciones características de los circuitos individuales. Mediante el análisis de esta ecuación se puede llegar a las siguientes conclusiones para un sistema 2 x 2:

1. Las raíces de la ecuación característica de cada circuito individual no son las de la ecuación característica para el sistema completo y, por lo tanto, es posible que el sistema completo sea inestable a pesar de que cada circuito sea estable individualmente. "Sistema completo" significa que ambos circuitos se ponen en automático simultáneamente.
2. Para que la interacción afecte a la estabilidad del sistema completo debe de trabajar de los dos modos; es decir, cada variable manipulada debe afectar a ambas variables controladas. Si $G_{12}(s) = 0$ o $G_{21}(s) = 0$, desaparece el último término de la ecuación característica y, por lo tanto, si cada circuito es estable individualmente, el sistema completo también es estable. Cuando la interacción trabaja de los dos modos, se dice que el sistema es totalmente acoplado; cuando la interacción sólo trabaja de un modo se dice que el sistema está parcialmente acoplado o acoplado a medias. La interacción no causa problemas en un sistema acoplado a medias.
3. El efecto de la interacción sobre un circuito se puede eliminar mediante la interrupción del otro circuito, lo cual se hace fácilmente mediante el "cambio" de un controlador a manual. Si se supone que el controlador 2 se cambia a manual, el efecto de esto es hacer $G_{c_2}(s) = 0$, de lo que resulta la siguiente ecuación característica:

$$1 + G_{c_1}(s)G_{v_1}(s)G_{11}(s)H_1(s) = 0$$

que es la misma en caso de que sólo existiera un lazo. Ésta es una de las razones por las cuales en la industria muchos controladores se ponen manual. Los cambios manuales en la salida del controlador 2 se convierten en simples perturbaciones para el circuito 1.

Sin embargo, generalmente no es necesario ser tan drástico para lograr un sistema estable; se puede lograr el mismo efecto, es decir, la estabilidad del sistema completo, con ambos controladores en automático si se baja la ganancia y se incrementa el tiempo de reajuste de uno de los controladores. El efecto que resulta al hacer esto es que todas las raíces de la ecuación característica se mueven al lado negativo del eje real.

En los párrafos precedentes se describió cómo analizar el efecto de la interacción sobre la estabilidad de los circuitos de control. Esto se puede simplificar bastante una vez que se conoce la ecuación característica del sistema. El lector debe recordar que estos comentarios se hicieron respecto a un sistema 2 x 2, que es probablemente el más común de los sistemas de control multivariable; para los sistemas de orden superior se debe seguir el mismo procedimiento, sin embargo, tal vez no se puedan determinar tan fácilmente las conclusiones que se obtienen a partir de la ecuación característica.

### Desacoplamiento

Todavía queda una pregunta por responder: ¿Se puede hacer algo para reducir o eliminar la interacción entre los circuitos que interactúan? Es decir, ¿se puede construir un sistema de control en que se desacoplen los circuitos que interactúan o acoplados? El desacoplamiento puede ser una posibilidad realista y ventajosa cuando se aplica con cuidado; en la matriz de ganancia relativa se tiene una indicación acerca de cuándo es benéfico el desacoplamiento. Mientras más cercano es el valor de los términos de la matriz entre sí, mayor es la interacción de los circuitos. En cuanto a los sistemas que existen actualmente, por lo general es suficiente la experiencia operativa para tomar una decisión.

Existen varios tipos de desacopladores y formas para diseñarlos, en esta sección se presentan los métodos más fáciles y prácticos.

Ahora se considera el sistema general de control 2 x 2 con interacción que se muestra en la figura 8-56; en este diagrama de bloques se ilustra gráficamente la interacción entre los dos circuitos; para evitar dicha interacción se puede diseñar e instalar un desacoplador como el que se muestra en la figura 8-57. El desacoplador se debe diseñar de tal manera que con la combinación proceso-desacoplador se obtengan dos circuitos de control que parezcan independientes; en términos matemáticos:

$$\frac{\partial c_1}{\partial m_2}\bigg|_{m_1} = 0 \qquad \text{y} \qquad \frac{\partial c_2}{\partial m_1}\bigg|_{m_2} = 0$$

Esto es, el desacoplador se debe diseñar de tal manera que con un cambio en la salida del controlador 1, $M_1(s)$, se produzca un cambio en $C_1(s)$, pero no en $C_2(s)$; de manera semejante, con un cambio en la salida del controlador 2, $M_2(s)$, se debe producir un cambio en $C_2(s)$, pero no en $C_1(s)$.

Otra forma de interpretar el desacoplador es considerarlo como parte de los controladores; de la combinación controlador-desacoplador se obtiene un controlador interactivo y, por lo tanto, la idea es diseñar un controlador interactivo para producir un sistema no interactivo.

En el diagrama de bloques de la figura 8-57 se puede simplificar si se combinan las funciones de transferencia del proceso de la siguiente manera:

$$G_{p_{11}}(s) = G_{v_1}(s)G_{11}(s)$$

El nuevo diagrama de bloques se muestra en la figura 8-58. En la figura 8-59 se muestra el diagrama de bloques de circuito abierto para el desacoplador y el proceso; a partir de este último diagrama se pueden diseñar los desacopladores para un sistema 2 x 2.

La salida del segundo controlador, $M_2(s)$, afecta a la primera variable controlada, $C_1(s)$, de la forma en que se expresa en la siguiente ecuación:

$$C_1(s) = [D_{11}(s)G_{p_{11}}(s) + D_{21}(s)G_{p_{12}}(s)]M_1(s) \quad (8-46)$$

De manera semejante, con $M_1(s)$ se afecta a $C_2(s)$, como se expresa en la siguiente ecuación:

$$C_2(s) = [D_{22}(s)G_{p_{22}}(s) + D_{12}(s)G_{p_{21}}(s)]M_2(s) \quad (8-47)$$

Como se ve, ahora se tienen dos ecuaciones, (8-46) y (8-47), y cuatro incógnitas, $D_{11}(s)$, $D_{21}(s)$, $D_{12}(s)$ y $D_{22}(s)$; por consiguiente, se tienen dos grados de libertad, lo que significa que dos de las incógnitas se deben fijar antes de calcular el resto; un procedimiento común es fijarlas a la unidad. Generalmente los elementos que se eligen son $D_{11}(s)$ y $D_{22}(s)$. De acuerdo con este procedimiento, las dos ecuaciones se hacen:

$$C_1(s) = [G_{p_{11}}(s) + D_{21}(s)G_{p_{12}}(s)]M_1(s) \quad (8-48)$$

Y:

$$C_2(s) = [G_{p_{22}}(s) + D_{12}(s)G_{p_{21}}(s)]M_2(s) \quad (8-49)$$

Ahora el objetivo es diseñar $D_{21}(s)$ de manera que, cuando la salida del segundo controlador cambie, la primera variable controlada permanezca constante. Si la variable controlada tiene que permanecer constante, su variable de desviación es cero, $C_1(s) = 0$; entonces, a partir de la ecuación (8-48), se tiene:

$$0 = G_{p_{11}}(s) + D_{21}(s)G_{p_{12}}(s)$$

y, finalmente, se obtiene:

$$D_{21}(s) = -\frac{G_{p_{11}}(s)}{G_{p_{12}}(s)} \quad (8-50)$$

De manera similar, $D_{12}(s)$ se puede diseñar de modo que, cuando $M_1(s)$ cambie, $C_2(s)$ permanezca en cero; de la ecuación (8-49) se tiene:

$$D_{12}(s) = -\frac{G_{p_{22}}(s)}{G_{p_{21}}(s)} \quad (8-51)$$

Las ecuaciones (8-50) y (8-51) son las ecuaciones de diseño del desacoplador para un sistema 2 x 2. Se debe recordar que $D_{11}(s)$ y $D_{22}(s)$ se fijan a la unidad. Ahora se utilizará un ejemplo para mostrar con más detalle los cálculos y las implementaciones.

**Ejemplo 8-10.** Ahora se considera el evaporador que aparece en la figura 8-60, en el cual una solución acuosa de NaOH se concentra de 0.2 a 0.5 fracciones de masa de NaOH; existen dos variables controladas, el nivel del líquido y la salida de fracción de masa de NaOH, y dos variables manipuladas, el caudal de entrada y el del producto. Los datos que aparecen en la tabla 8-5 se obtuvieron por medio de prueba dinámica. El rango del transmisor de nivel es de 1-5 m, y el del transmisor de concentración, de 0.2-0.8 fracciones de masa de NaOH. Se debe decidir la agrupación por pares correcta de las variables y diseñar el sistema para desacoplamiento; asimismo, es necesario dibujar el diagrama con la instrumentación que se requiere para implementar el desacoplador; toda la instrumentación, con excepción de las válvulas, es electrónica.

Lo primero que se debe hacer es dibujar el diagrama de bloques de circuito abierto general para este sistema, como se muestra en la figura 8-61a. Con base en los datos de que se dispone, se observa que el diagrama se puede simplificar al que se muestra en la figura 8-61b. La información que aparece en la tabla 8-6 se utiliza en conjunto con el método de cálculo 3 que se estudió en el capítulo 6, para determinar las siguientes funciones de transferencia:

$$G_{p_{11}}(s) = \frac{0.072e^{-1.3s}}{2.7s + 1}, \quad \frac{\%\text{ de salida del controlador 1}}{\text{m}}$$
$$G_{p_{12}}(s) = \frac{-0.0033e^{-0.7s}}{1.05s + 1}, \quad \frac{\%\text{ de salida del controlador 1}}{\text{fracción de masa}}$$
$$G_{p_{21}}(s) = \frac{0.036e^{-0.3s}}{2.97s + 1}, \quad \frac{\%\text{ de salida del controlador 2}}{\text{m}}$$
$$G_{p_{22}}(s) = \frac{-0.00144e^{-0.7s}}{1.65s + 1}, \quad \frac{\%\text{ de salida del controlador 2}}{\text{fracción de masa}}$$

Ahora, con esta información se puede decidir sobre la agrupación por pares correcta y el diseño de los sistemas de desacoplamiento. La matriz de ganancia de estado estacionario es la siguiente:

| | $m_1$ | $m_2$ |
|---|---|---|
| $L$ | 0.072 | -0.0033 |
| $x$ | 0.036 | -0.00144 |

Se aplican las ecuaciones (8-37) a (8-40) para obtener la matriz de ganancia relativa:

| | $m_1$ | $m_2$ |
|---|---|---|
| $L$ | 0.47 | 0.53 |
| $x$ | 0.53 | 0.47 |

de lo que resulta la agrupación por pares: $L-m_2$ y $x-m_1$.

Para diseñar el sistema de desacoplamiento se utilizan las ecuaciones (8-50) y (8-51); con el fin de evitar cualquier problema al seguir dichas ecuaciones, se desarrolla el diagrama de bloques de circuito cerrado que se muestra en la figura 8-62. A partir de la ecuación (8-51), se tiene:

$$D_{12}(s) = -\frac{G_{p_{22}}(s)}{G_{p_{21}}(s)} = -\frac{-0.00144e^{-0.7s}/(1.65s + 1)}{0.036e^{-0.3s}/(2.97s + 1)} = 0.04\frac{(2.97s + 1)}{(1.65s + 1)}e^{-0.4s}$$

De la ecuación (8-50) se tiene:

$$D_{21}(s) = -\frac{G_{p_{11}}(s)}{G_{p_{12}}(s)} = -\frac{0.072e^{-1.3s}/(2.7s + 1)}{-0.0033e^{-0.7s}/(1.05s + 1)} = 21.8\frac{(1.05s + 1)}{(2.7s + 1)}e^{-0.6s}$$

Ahora se tienen las ecuaciones de los dos desacopladores; se observa que ambas constan de un término de ganancia, un término de adelanto/retardo y una compensación de tiempo muerto. Como se mencionó al estudiar el control por acción precalculada, la implementación de la compensación de tiempo muerto con instrumentación analógica es difícil; pero, por otro lado, con los controladores actuales con base en microprocesadores, es bastante fácil. Las ecuaciones que generalmente se implementan para desacopladores, son:

$$D_{12}(s) = -0.428 \quad (8-52)$$

Y:

$$D_{21}(s) = -2(6.7s + 1) \quad (8-53)$$

En la figura 8-63 se muestra la implementación de este sistema de desacoplamiento.

Con el ejemplo 8-10 se ilustró la implementación de un sistema de desacoplamiento para un proceso 2 x 2. Si el proceso es completamente desacoplado, el circuito de nivel no debe afectar al de composición, y viceversa; una forma de verificar esto es derivar las funciones de transferencia del sistema de desacoplamiento mediante las gráficas de flujo de señal; éste será el tema de uno de los problemas al final del capítulo.

Hasta aquí se vio cómo diseñar sistemas de desacoplamiento para procesos 2 x 2, pero, ¿qué pasa con los procesos 3 x 3, o más complejos? A continuación se muestra la forma de diseñar tales sistemas.

Se considera un proceso con $n$ variables controladas y $n$ variables manipuladas; la relación de desacoplamiento que se desea entre las variables controladas, $C(s)$, y las salidas del controlador, $M(s)$, se puede escribir en forma de matriz, de la manera siguiente:

$$\begin{bmatrix} C_1(s) \\ C_2(s) \\ \vdots \\ C_n(s) \end{bmatrix} = \begin{bmatrix} N_1(s) & 0 & \ldots & 0 \\ 0 & N_2(s) & \ldots & 0 \\ \vdots & \vdots & \ddots & \vdots \\ 0 & 0 & \ldots & N_n(s) \end{bmatrix}\begin{bmatrix} M_1(s) \\ M_2(s) \\ \vdots \\ M_n(s) \end{bmatrix}$$

donde $N_1(s), N_2(s), \ldots, N_n(s)$ son cualquiera de las funciones que se desean.

Con la primera matriz, a la derecha del signo igual, se representa la combinación proceso-desacoplador; más específicamente, esta matriz es:

$$\begin{bmatrix} N_1(s) & 0 & \ldots & 0 \\ 0 & N_2(s) & \ldots & 0 \\ \vdots & \vdots & \ddots & \vdots \\ 0 & 0 & \ldots & N_n(s) \end{bmatrix}$$

Si se multiplican ambos lados por $\underline{G_p}^{-1}$, se obtiene la matriz del desacoplador:

$$\underline{D} = \underline{G_p}^{-1}\cdot\underline{N} \quad (8-56)$$

En esta ecuación hay $n^2 + n$ parámetros desconocidos, pero solamente $n^2$ ecuaciones; por lo tanto, existen $n$ grados de libertad que se deben fijar antes de calcular los otros parámetros. Como se dijo anteriormente, los grados de libertad que generalmente se eligen son los elementos en diagonal de la matriz de desacoplamiento, $D(s)$; los cuales se igualan a uno.

Antes de concluir con este tema de desacoplamiento es importante subrayar que el diseño del desacoplador es equivalente al diseño de un controlador por acción precalculada en el que cada variable manipulada es la perturbación mayor para los demás circuitos. En el ejemplo que se acaba de presentar, el término $D_{21}(s)$ sirve como controlador con acción precalculada en el circuito de composición; se observa que los términos en $D_{21}(s)$ son exactamente los términos que hay en muchos de los controladores con acción precalculada, una ganancia y un adelanto/retardo; es decir, compensación dinámica y de estado estacionario. El término $D_{12}(s)$ sirve como controlador por acción precalculada para el circuito de nivel.

Finalmente, también es importante tener en cuenta que, a diferencia del control por acción precalculada, los desacopladores forman parte de la ecuación característica de los circuitos de control y, por lo tanto, afectan la estabilidad del circuito de control.

## 8-7. RESUMEN

En este capítulo se presentaron varias técnicas que sirven como auxiliares en el control de procesos. Todas estas técnicas, con excepción del control multivariable, son completamente usuales en la industria actual. Para el control multivariable se requiere un mayor grado de elaboración y comprensión, lo cual ha retrasado su aplicación; se remite al lector a la referencia bibliográfica 15 para una presentación detallada de este tema tan interesante.

Todas las técnicas se presentaron y explicaron sin importar la instrumentación que se utiliza para implementarlas. Se utilizan instrumentos tanto analógicos como digitales, sin embargo, con la creciente utilización de los sistemas con base en microprocesadores, la implementación se torna más fácil y, en consecuencia, la aplicación de estas técnicas se vuelve cada vez más popular. También es importante tener en cuenta que con ninguna de las técnicas se substituye completamente al control por retroalimentación; siempre se requiere algún tipo de control por retroalimentación para completar el control. Como se mencionó al principio del capítulo, para aplicar estas técnicas se requiere una cantidad mayor de ingeniería y equipo, en comparación con el control por retroalimentación simple, y, en consecuencia, debe existir una justificación de su empleo antes de aplicarlas. Además, para aplicar estas técnicas se requiere mayor entrenamiento del personal de operación; si el operario no entiende las técnicas, habrá dificultad en su aplicación. Lo más recomendable es desarrollar la técnica de control más simple, con la que se logre el desempeño de control que se requiere.

## BIBLIOGRAFÍA

1. O'Meara, J. E., "Oxygen Trim for Combustion Control," *Instrumentation Technology*, Marzo 1979.
2. Johnson, M. L., "Dehydrogenation Reactor Control," *Instrumentation Technology*, Diciembre 1976.
3. *Instrument Engineers Handbook-Vol. II*, Bela G. Liptak, Editor, Chilton, 1970.
4. Becker, J. V., y R. Hill, "Fundamentals of Interlock Systems," *Chemical Engineering Magazine*, Octubre 15, 1979.
5. Becker, J. V., "Designing Safe Interlock Systems," *Chemical Engineering Magazine*, Octubre 15, 1979.
6. DiStefano, J. J., A. R. Stubberud, y T. J. Williams, *Feedback and Control Systems*, Schaum, Nueva York.
7. Bristol, E. H., "On a New Measure of Interaction for Multivariable Process Control," *Trans. IEEE*, Enero 1966.
8. Nisenfeld, A. E., y H. M. Schultz, "Interaction Analysis Applied to Control System Design," *Instrumentation Technology*, Abril 1971.
9. Shinskey, F. G., *Energy Conservation through Control*, McGraw-Hill, Nueva York, 1977.
10. Shinskey, F. G., *Process Control Systems*, McGraw-Hill, Nueva York, 1979.
11. Scheib, T. J., y T. D. Russell, "Instrumentation Cuts Boiler Fuel Costs," *Instrumentation and Control Systems*, Noviembre 1981.
12. Congdon, P., "Control Alternatives for Industrial Boilers," *Instrumentation Technology*, Diciembre 1981.
13. Wang, J. C., "Relative Gain Matrix for Distillation Control-A Rigorous Computational Procedure," *Instrument Society of America*, 1979.
14. Hulbert, D. G., y E. T. Woodburn, "Multivariable Control of a Wet Grinding Circuit," *Instrumentation Technology*, Marzo 1983.
15. McAvoy, T., "Interaction Analysis: Principles and Applications," Instrument Society of America, Research Triangle Park, N. C., 1983.
16. Koppel, L. B., "Input-Output Pairing in Multivariable Control," sometido al *AIChE J.*, Enero 1962.
17. Niederlinski, A., "A Heuristic Approach to the Design of Linear Multivariable Control Systems," *Automatica*, Vol. 7, No. 5, Sept. 1971, p. 371.

## PROBLEMAS

**8-1.** Se considera el sistema de tubería que se muestra en la figura 8-64, en la cual fluye gas natural hacia un proceso; se necesita medir el flujo de gas y totalizarlo, de manera que cada 24 horas se sepa la cantidad total. Se propone sumar la salida de ambos transmisores y entonces totalizar (integrar) el resultado. La razón de flujo en cada medidor, como diferencial de presión, se expresa de la siguiente manera:

DPT21: $Q(MSCFH) = 44.73\sqrt{h}$
DPT22: $Q(MSCFH) = 48.10\sqrt{h}$

donde $h$ es el diferencial de presión en pulgadas de H₂O. El rango de ambos transmisores es de 0-100 pulg de H₂O. Se debe especificar la instrumentación que se requiere para calcular la razón total de flujo, para lo cual se utiliza la tabla 8-2. Se deben determinar los factores de escalamiento.

**8-2.** Ahora se considera el intercambiador de calor de la figura 8-15, en el cual se calienta el fluido bajo proceso mediante condensación de vapor. Para el esquema de control se requiere calcular la energía que se transfiere al fluido bajo proceso, mediante la siguiente ecuación:

$$Q = F\rho C_p(T - T_i)$$

Se conoce la siguiente información:

| Variable | Rango | Estado estacionario |
|----------|-------|---------------------|
| F | 0-50 gpm | 30 gpm |
| T | 50-120°F | 80°F |
| $T_i$ | 25-60°F | 50°F |
| Q | 0-300,000 Btu/h | 182,000 Btu/h |

Se supone que la densidad y la capacidad calorífica son constantes, y que se producen 202.3 Btu/gpm-°F-h. Se debe utilizar la tabla 8-1, para especificar la instrumentación que se requiere para calcular la energía que se transfiere. Se deben especificar los factores de escalamiento.

**8-3.** En la figura 8-65 se muestra el reflujo hacia la parte superior de una columna de destilación. En la "computadora de reflujo interno" se calcula el punto de control, $L_i^{sp}$, del controlador de reflujo externo, de modo que se mantenga el reflujo interno, $L_i$, en un valor fijo, $L_i^{fijo}$. El reflujo interno es mayor que el reflujo externo, debido a la condensación de los vapores en la charola superior, los cuales se requieren para llevar hasta su punto de burbujeo, $T_V$, el reflujo subenfriado con temperatura $T_R$. La siguiente ecuación se obtiene a partir del balance de energía para la charola superior:

$$C_pL_R(T_V - T_R) = \lambda(L_i - L_R)$$

Se debe dibujar la instrumentación que se requiere para la computadora de reflujo interno y, además, utilizar la tabla 8-3 para calcular los coeficientes de escalamiento. Las especificaciones de diseño son las siguientes:

$$C_p = 0.76 \text{ Btu/lbm-°F}; \quad \lambda = 285 \text{ Btu/lbm}$$

| Transmisor | Rango | Valor normal |
|------------|-------|--------------|
| FT100(L_R) | 0-5000 lb/h | 3400 lb/h |
| TT102(T_R) | 100-300°F | 195°F |
| TT101(T_V) | 150-250°F | 205°F |

**8-4.** El sistema que aparece en la figura 8-66 se utiliza para diluir una solución al 50% en peso de NaOH y formar una solución al 30% en peso. La válvula de NaOH se manipula mediante un controlador que no se muestra en el diagrama. Puesto que el flujo de la solución al 50% puede variar frecuentemente, se desea diseñar un esquema de control para manipular el flujo de H₂O, de modo que la solución de salida se mantenga en el porcentaje que se requiere. El flujo nominal de la solución de NaOH al 50% es de 200 lbm/h. El elemento de flujo que se utiliza para ambas corrientes funciona de tal manera que la señal que sale de los transmisores se relaciona de manera lineal con el flujo volumétrico. Además, se puede suponer que la densidad de cada corriente es muy constante y, por lo tanto, la salida de cada transmisor también se relaciona con el flujo de masa. Se debe especificar el rango de cada transmisor en unidades de flujo de masa, de modo que el caudal nominal esté a mitad de la escala. Se deben especificar los relés de cómputo, así como las constantes de tiempo correspondientes que se requieren para implementar el esquema de control de razón; se utilizarán los bloques de cómputo que aparecen en la tabla 8-2.

**8-5.** En la fabricación de papel se requiere mezclar algunos componentes en una cierta proporción para formar una pasta base con que se alimenta a una máquina de papel, y de ahí se produce la hoja final con las características que se desean; el proceso se muestra en la figura 8-67. Para una fórmula en especial, la mezcla final debe contener 47% en masa de pulpa de maderas duras, 50% en masa de pulpa de pino, 2% de masa de aglutinante y 1% en masa de colorante. El sistema nominal se debe diseñar para un máximo posible de producción de 2000 lbm/h.

a) Se debe especificar el rango de cada medidor de flujo; los fluxómetros que se utilizan en este caso son magnéticos y su señal de salida se relaciona de manera lineal con la razón de flujo de masa.
b) Se debe diseñar un sistema de control para controlar el nivel en el depósito de mezclado y, a la vez, mantener la fórmula en la proporción correcta. Al final del día también se requiere saber la cantidad total de masa que se añadió de cada corriente al depósito de mezclado. Se debe establecer la instrumentación que se necesita para implementar el esquema de control y con los bloques de cómputo de la tabla 8-3, obtener la graduación de la instrumentación necesaria.

**8-6.** En el ejemplo 8-2 se muestra un esquema de control (figura 8-8) para controlar la razón aire/combustible que entra a una caldera u horno. Como se explicó en el ejemplo, en este esquema el flujo de aire siempre se retrasa respecto al flujo de combustible.

a) Se debe diseñar un esquema de control en el que el flujo de combustible siempre se mueva primero, y que posteriormente lo siga el flujo de aire.
b) La manera más común de implementar este control es mediante el esquema que se conoce como "control por limitación cruzada". Esta implementación se hace de manera tal que, cuando la presión del vapor desciende, por lo que se requiere más combustible, primero se incrementa el flujo de aire y posteriormente le sigue el flujo de combustible. Cuando la presión de vapor se incrementa, y por lo tanto, se requiere menos combustible, primero se disminuye el flujo de combustible, y entonces le sigue el flujo de aire. Se debe diseñar el sistema de control para lograr este objetivo.

Nota: Este problema es muy interesante; se sugiere utilizar selectores de máximo y mínimo para elegir la señal que se debe enviar a los controladores de aire y combustible.

**8-7.** En la figura 8-68 se muestra un sistema de control en cascada. Como se explicó en este capítulo, el ajuste del controlador primario no se hace de manera directa; sin embargo, con las técnicas de respuesta en frecuencia se cuenta con un medio de ajuste del controlador.

a) Se debe ajustar el controlador secundario, P, para obtener un factor de amortiguamiento de 0.707.
b) Se debe ajustar el controlador primario, PI, mediante el método de Ziegler-Nichols.

Nota: Mediante las técnicas de respuesta en frecuencia se puede determinar la ganancia y el período últimos del circuito de control primario.

**8-8.** Ahora se considera el reactor exotérmico que se muestra en la figura 8-69. En el diagrama se ilustra el control de la temperatura del reactor mediante la manipulación de la válvula de agua de enfriamiento.

a) Se debe diseñar el esquema para controlar la entrada de reactivos al reactor. Tanto el flujo A como el B se pueden medir y controlar, la razón que se requiere entre estos flujos es de 2.5 gpm de B/gpm de A. El fluxómetro de A se calibra entre 0 y 40 gpm, y el de B entre 0 y 200 gpm. Se debe utilizar la tabla 8-1 para indicar y señalar la graduación de la instrumentación necesaria.
b) De la experiencia de operación se sabe que la temperatura de entrada del agua para enfriamiento tiene algunas variaciones. Generalmente esta perturbación da por resultado un ciclaje en temperatura del reactor, debido a los retardos en el sistema, es decir, el casquillo de enfriamiento, la pared de metal y el volumen del reactor. El ingeniero a cargo de esta unidad se pregunta si con algún otro esquema de control se puede mejorar el control de temperatura; se debe diseñar un esquema de control para lograrlo.
c) Por la experiencia de operación, también se sabe que bajo ciertas condiciones poco frecuentes no se logra suficiente enfriamiento con el sistema de enfriamiento. En este caso el único medio para controlar la temperatura es disminuir el caudal de los reactivos. Se debe diseñar el esquema de control para hacer lo anterior automáticamente; el esquema debe funcionar de manera tal que, cuando la capacidad de enfriamiento regresa a la normalidad, se restablezca el esquema de la parte b).

**8-9.** En el proceso de secado que aparece en la figura 8-70 se seca el suministro de papel húmedo para producir el producto final. El secado se hace mediante aire caliente, el cual pasa por un calentador en el que se quema combustible para proveer la energía. La variable controlada es la humedad del papel que sale de la secadora. En la figura 8-70 se muestra el esquema de control que se propuso e instaló originalmente.

a) Algunas semanas después de poner en servicio el proceso, el ingeniero observa que, a pesar de que con el controlador de humedad ésta se mantiene dentro de ciertos límites del punto de control, las oscilaciones eran más que las de su agrado. Después de investigar las posibles causas y asegurarse de que el ajuste del controlador de humedad (MIC47) es eficaz, se encontró que la temperatura del aire caliente que sale del calentador varía más de lo que se pensó originalmente en la etapa de diseño; estas variaciones se atribuyen a los cambios diarios en la temperatura ambiente y a posibles perturbaciones en la cámara de combustión del calentador. Se debe diseñar un esquema de control para mantener la temperatura del aire caliente en el valor que se desea, a fin de ayudar a mantener el punto de control de la humedad.
b) Con el esquema de control que se acaba de describir se ayudó significativamente a controlar la humedad, sin embargo, algunas semanas después los operarios se quejan de que de vez en cuando la humedad difiere considerablemente del punto de control, aunque finalmente con el esquema de control se le regrese de nuevo al punto de control. A causa de esta perturbación, se requiere volver a procesar el papel que se produce durante este período, lo que representa pérdidas en la producción. Después de revisar los registros de producción, el ingeniero descubre que la perturbación se debe a cambios en la humedad de entrada. Se debe diseñar un esquema de control con acción precalculada para compensar tales perturbaciones; se dispone de un transmisor de humedad con rango de 5 a 20% de masa para medir la humedad de entrada.

**8-10.** Ahora se considera el esquema de control para el sistema de secado de sólidos que se ilustra en la figura 8-71. La mayor perturbación en este proceso es el contenido de humedad de los sólidos que entran; debido a que el sistema de control responde con bastante lentitud a tal perturbación, se desea implementar un sistema con acción precalculada para mejorar dicho control. Después de algún trabajo inicial, se obtuvieron los siguientes datos:

**Cambio escalón en la humedad de entrada = +2%**

| Tiempo, min | Humedad a la salida, % | Tiempo, min | Humedad a la salida, % |
|-------------|------------------------|-------------|------------------------|
| 0 | 5.0 | 5.0 | 6.6 |
| 0.5 | 5.0 | 5.5 | 6.7 |
| 1.0 | 5.1 | 6.5 | 6.8 |
| 1.5 | 5.2 | 7.0 | 6.9 |
| 2.0 | 5.4 | 7.5 | 7.0 |
| 2.5 | 5.7 | 8.0 | 7.0 |
| 3.0 | 5.9 | 8.5 | 6.9 |
| 3.5 | 6.1 | 9.0 | 7.0 |
| 4.0 | 6.3 | | |
| 4.5 | 6.5 | | |

**Cambio escalón en la señal de salida del controlador de humedad, MIC-10, = +4 mA**

| Tiempo, min | Humedad a la salida, % |
|-------------|------------------------|
| 0 | 5.0 |
| 0.5 | 5.0 |
| 1.0 | 4.95 |
| 1.5 | 4.93 |
| 2.0 | 4.85 |
| 2.5 | 4.70 |
| 3.0 | 4.60 |
| 3.5 | 4.40 |
| 4.0 | 4.20 |
| 4.5 | 4.00 |
| 5.0 | 3.81 |
| 5.5 | 3.70 |
| 6.0 | 3.55 |
| 6.5 | 3.45 |
| 7.0 | 3.35 |
| 7.5 | 3.25 |
| 8.5 | 3.10 |
| 9.5 | 3.03 |
| 10.5 | 2.99 |
| 11.5 | 3.00 |

El rango del analizador de humedad por retroalimentación es de 1 a 7% de humedad; se tiene otro analizador con rango de 10 a 15% de humedad, el cual se puede utilizar para medir la humedad de entrada. Estos analizadores se utilizaron anteriormente para este proceso en particular, y se demostró que son confiables. Los dos sensores-transmisores son electrónicos, con una constante de tiempo de aproximadamente 15 segundos.

a) Con base en los principios de ingeniería de proceso (balances de masa, balances de energía, etc.), se debe desarrollar un esquema de control con acción precalculada. En el planteamiento del problema no se suministró toda la información necesaria; se debe suponer que dicha información se puede obtener del archivo de la planta. Se debe indicar la implementación de este esquema.
b) Se debe dibujar el diagrama de bloques completo para este proceso; se requiere incluir todas las funciones de transferencia conocidas.
c) Se debe desarrollar un esquema de control con acción precalculada mediante el método de diagramas de bloques e ilustrar la implementación de este esquema.

**8-11.** Después de poner en operación el proceso que aparece en la figura 8-10, la experiencia indica que es difícil mantener constante la temperatura de salida del calentador, a causa de los cambios frecuentes en la razón de flujo de masa del aire para regeneración; estos cambios se deben a las variaciones en la presión y temperatura de entrada.

a) Se debe diseñar un esquema de control para compensar los cambios en el flujo de masa de aire de regeneración e indicar la instrumentación necesaria, para lo cual se utilizan los bloques de cómputo que aparecen en la tabla 8-2.
b) El esquema de control con acción precalculada que se diseñó en a) es un compensador de estado estable; se debe explicar qué clase de datos se requieren para aplicar la compensación dinámica y los pasos a seguir para obtener los datos.

Datos:
- Flujo de aire = 10000 lbm/h
- Temperatura de entrada = 70°F
- Temperatura del aire de salida = 600°F
- Presión de entrada = 30 psig
- $C_p$ del aire = 7 Btu/lb mol-°F
- Coeficiente de entrada de aire del orificio: $K = 2085$ lbm/hr (in. H₂O)$^{1/2}$
- Valor calorífico del combustible = 18,000 Btu/lbm

Las condiciones de entrada de aire se medirán con los siguientes sensores-transmisores:
- Temperatura: 25 a 115°F
- Presión: 0 a 45 psig
- Transmisores de diferencial de presión: 0 pulg a 150 pulg

La temperatura de salida del calentador se mide mediante un sensor-transmisor cuyo rango es de 400 a 800°F. La razón de flujo de combustible se mide mediante un sensor-transmisor con un rango de 0-200 lbm/h.

**8-12.** Se debe diseñar un controlador con acción precalculada para controlar la temperatura de salida del horno que se esboza en la figura 8-72. El controlador debe tener compensación para las variaciones en la razón de alimentación y temperatura de entrada mediante la manipulación del punto de control del controlador de flujo de combustible. Para indicar la instrumentación que se requiere se utiliza la tabla 8-3. Se conoce la siguiente información:

- Calor específico de gas: $C_p = 0.24$ Btu/lbm-°F
- Calor de combustión del combustible: $H_c = -22,000$ Btu/lbm
- Temperatura de entrada del gas: $T_i = 70°F$
- Temperatura de salida del gas: $T_o = 930°F$
- Eficiencia del horno = 0.80
- Rango de FT42: 0 a 15000 lbm/h
- Rango de TT42: 0 a 120°F
- Rango de FT43: 0 a 200 lbm/h
- Rango de TT44: 700 a 1100°F

Con la intención de simplificar no se indica el aire para combustión.

**8-13.** Ahora se supone que se ignoran algunos datos del proceso, tales como el calor que genera la combustión del combustible o el calor específico del gas, del horno del problema 8-12; por lo tanto, para diseñar el controlador con acción precalculada se debe utilizar el método de diagramas de bloques. Después de hacer la prueba escalón en el horno, se obtuvieron los siguientes datos:

| Variable | Cambio escalón | Cambio de salida | Constante de tiempo | Tiempo muerto |
|----------|---------------|------------------|---------------------|---------------|
| F | 750 lbm/hr | 50°F | 15 s | 6 s |
| $T_i$ | 20°F | -13°F | 66 s | 6 s |

a) Se debe dibujar el diagrama a bloques completo con todas las funciones de transferencia.
b) Se debe diseñar un control con acción precalculada para compensar las variaciones en la razón de alimentación y en la temperatura de alimentación mediante la manipulación del punto de control del controlador de flujo de combustible; se debe incluir el compensador dinámico.
c) Si se decide compensar solamente una perturbación, ¿cuál se elige y por qué? ¿En qué se modifica el diseño?

**8-14.** En la sección de descortezamiento de una torre de destilación, la cual se muestra en la figura 8-73, se necesita mantener en un cierto valor la pureza de los sedimentos; este objetivo se alcanza comúnmente mediante el control de la temperatura en una de las bandejas (se supone que la presión en la torre es constante), para lo cual se utiliza como variable manipulada el flujo de vapor que llega al rehervidor. Una perturbación mayor común es el flujo con que se alimenta a la torre.

a) Se debe esbozar el esquema de control por acción precalculada/retroalimentación para compensar esta perturbación mayor, la cual se debe describir brevemente.
b) Se describirán brevemente las pruebas dinámicas que se deben realizar en la torre para ajustar el controlador con acción precalculada y el de retroalimentación.

**8-15.** Ahora se considera el filtro de vacío que se expone en el problema 6-15. Se debe utilizar la información que se da en ese problema, a fin de diseñar un esquema de control con el que se compensen los cambios en la humedad de entrada. Se puede suponer que el rango del transmisor de humedad es de 60 a 95%, la dinámica del transmisor es despreciable. Se debe mostrar la implementación completa con los bloques de cómputo de la tabla 8-2 y especificar el factor de escalamiento.

**8-16.** Se considera el sistema de evaporación del problema 6-20, para el cual se debe diseñar un esquema de control por acción precalculada/retroalimentación con el que se compensen los cambios de densidad de la solución que entra al primer efecto. El rango del medidor de densidad con que se mide la densidad de entrada es de 55 a 75 lbm/pies³, y la dinámica es despreciable. Se utilizarán los relés de cómputo de la tabla 8-1 para implementar el esquema.

**8-17.** Ahora se considera el proceso del problema 6-22, en el cual se seca granulado de fosfato. Como se mencionó en este problema, una de las perturbaciones importantes es la humedad con que entra el granulado. Con la información disponible se debe diseñar un esquema de control por acción precalculada/retroalimentación para compensar esta perturbación. Se cuenta con un transmisor de humedad para medir la humedad de entrada; el rango del transmisor es de 12 a 16% y su dinámica es despreciable. Para implementar el esquema se deben utilizar los bloques de cómputo de la tabla 8-3 y especificar los factores de escalamiento.

**8-18.** En el horno que se muestra en la figura 8-74 se debe controlar la temperatura de salida del hidrocarburo, mediante el control del combustible que entra al calentador. Se dispone de dos tipos de combustible: gas de desecho que se produce en otra unidad de proceso, y gas natural. El mejor procedimiento de operación es utilizar la mayor cantidad posible de gas de desecho, con lo cual se conserva el gas natural. El flujo del gas de desecho se utiliza para controlar la presión en la unidad de proceso donde se produce.

Se puede suponer que el valor calorífico neto del gas de desecho es casi la quinta parte del valor del gas natural. Las razones de aire/combustible que se requieren, con base en la masa, son:

$$\frac{\text{aire}}{\text{gas de desecho}} = R_1 \qquad \text{y} \qquad \frac{\text{aire}}{\text{gas natural}} = R_2$$

a) Se debe diseñar un sistema de control simple para controlar la presión en el proceso A.
b) Se debe diseñar un esquema para controlar la temperatura de salida del hidrocarburo. Puesto que todos los combustibles son gases, se recomienda compensar las variaciones de presión y temperatura. Se puede suponer que nunca hay suficiente gas de desecho para calentar el flujo de hidrocarburo; es decir, siempre se necesita algo de gas natural.
c) Por razones de seguridad, se necesita diseñar un esquema de control con el que se suspenda el flujo de gas natural y aire, en caso de que se apague la flama del quemador; el flujo de gas de desecho puede continuar. Para este trabajo, en el quemador se dispone de un interruptor con una salida de 20 mA, mientras existe flama; si la flama se apaga, la salida baja a 4 mA. Este esquema de control se debe diseñar con base en el anterior.

**8-19.** Ahora se considera el reactor que se muestra en la figura 8-75, en el cual se realiza la reacción completa e irreversible de los líquidos A + B → C. El producto C es la materia prima para varias unidades de proceso que están después del reactor. La producción que se requiere del reactor depende de la cantidad de unidades en operación y de su razón de producción, y puede variar entre 4000 y 20,000 kmol/h. El reactivo A se obtiene de dos fuentes; gracias a un contrato a largo plazo, la fuente 1 es la menos cara, sin embargo, en el contrato existen dos limitantes: una razón máxima instantánea de 16,800 kmol/h y un consumo mensual máximo de 3,456 × 10⁶ kmol. Si se excede cualquiera de estas limitantes, se debe pagar una multa muy alta y, en este caso, es menos caro obtener el excedente de la fuente 2. Se puede suponer que la densidad de cada reactivo, A y B, y del producto C no varía mucho y, por tanto, se puede suponer que es constante.

Se debe diseñar un sistema de control con el cual se utilice preferentemente el reactivo A de la fuente 1 y no se exceda ninguna de las limitantes contractuales. La razón de alimentación de A contra B es de 2:1.

**8-20.** En la figura 8-76 se ilustra un sistema para filtrar aceite antes de procesarlo. El aceite entra a un distribuidor donde se controla la presión mediante la manipulación de la válvula de entrada (admisi6n); desde este distribuidor se reparte el aceite a los filtros. Los filtros consisten en un casquillo, en el cual hay tubos, de manera semejante a la del intercambiador de calor; los tubos son el medio de filtraje por el que debe pasar el aceite. El aceite entra al recipiente y fluye a través del medio de filtraje, pero, conforme pasa el tiempo, se acumulan residuos en el filtro y, en consecuencia, se incrementa la presión necesaria para que haya flujo; si la presión se incrementa demasiado, las paredes se pueden romper. Por lo anterior, en algún momento se saca el filtro de servicio y se limpia; bajo condiciones normales, el flujo total de aceite se puede manejar con tres filtros.

a) Se debe diseñar un sistema de control de flujo para fijar el flujo de aceite a través de este sistema.
b) Se debe diseñar un sistema de control tal que, cuando la presión en cada filtro se incremente por arriba de un valor predeterminado, el flujo de aceite hacia ese filtro empiece a disminuir. El flujo total de aceite en el sistema se debe mantener constante.

**8-21.** Para este problema se consideran los diagramas de bloques de las figuras 8-77a y 8-77b; mediante la técnica de gráficas de flujo de señal se debe obtener $C(s)/R(s)$ para cada uno de ellos.

**8-22.** Para el sistema de control en cascada con circuitos interactivos, cuyo diagrama de bloques se muestra en la figura 8-78, se deben determinar las funciones de transferencia $C_2(s)/R(s)$ y $C_1(s)/L(s)$.

**8-23.** Como se vio en la sección 8-6, las columnas de destilación son el ejemplo típico de los sistemas multivariable. En un interesante artículo de Wang, cuya lectura se recomienda, las ganancias de estado estacionario con que se relacionan las variables controladas (composición del destilado, y, y composición de los sedimentos, x) y las variables manipuladas (razón de destilación, D, y razón de ebullición o razón de vapor que entra al rehervidor, V) para una columna en particular, se obtuvieron a partir de una hoja de programa de simulación de flujo; estas ganancias de estado estacionario son las siguientes:

| | D | V |
|---|---|---|
| y | -0.205991 × 10⁻² | 0.912422 × 10⁻² |
| x | 10.272573 × 10⁻³ | -0.644203 × 10⁻² |

Con base en estos datos se debe decidir la agrupación por pares correcta.

**8-24.** En un artículo de D. G. Hulbert y E. T. Woodburn se presenta el control multivariable para un circuito de molido con agua, el cual se muestra de manera esquemática en la figura 8-79. Para este circuito particular, se decidió controlar las siguientes variables: el torque (par) que se requiere para girar el molino (TOR), la densidad del material que se alimenta mediante la tolva (DCF) y la razón del flujo que sale del molino (FML). Como se explica en el artículo, estas variables se eligieron con base en las consideraciones de observación, posibilidad de control e importancia desde el punto de vista metalúrgico. TOR y FML se toman en cuenta para describir las condiciones en el molino y DCF se relaciona con las condiciones en la tolva. TOR y DCF se miden directamente, pero FML se calcula con base en las mediciones de balance de masa en la tina; sin embargo, para simplificar el diagrama de la figura 8-79 se supone que FML se obtiene mediante un transmisor.

En este sistema, las variables manipuladas son la razón de alimentación de sólidos (SF), la razón de alimentación de agua al molino (MW) y la razón de alimentación de agua a la tina (SW). La razón de alimentación de sólidos se manipula por medio de la velocidad de la banda con que se acarrean los sólidos al molino (se utiliza una señal eléctrica).

Las siguientes funciones de transferencia, con que se relacionan las variables controladas y las manipuladas, se obtuvieron mediante la prueba de circuito abierto:

| | SF (kg-s⁻¹) | MW (kg-s⁻¹) | SW (kg-s⁻¹) |
|---|---|---|---|
| TOR (Nm) | 119/(217s+1) | 153/(337s+1) | -21/(10s+1) |
| FML (m³-s⁻¹) | 0.00037/(500s+1) | 0.000767/(33s+1) | -0.00005/(10s+1) |
| DCF (kg-m⁻³) | 930/(500s+1) | -1033/(166s+1) | 47/(47s+1) |

Todas las constantes de tiempo y los tiempos muertos están en segundos. Con base en esta información, se debe elegir la agrupación por pares correcta, diseñar un desacoplador para este sistema y exponer toda la instrumentación que se requiere.

**8-25.** Se debe demostrar que el sistema de la figura 8-60 es desacoplado, lo cual se puede hacer mediante la deducción de la función de transferencia de circuito cerrado, $C_1(s)/R_1(s)$, y la substitución de las funciones de transferencia del diseño de los desacopladores, si se supone que es posible lograr un desacoplamiento perfecto.

**8-26.** Ahora se considera la columna de destilación que aparece en la figura 8-80. Las siguientes funciones de transferencia se determinaron mediante la aplicación de la prueba de pulso a un modelo de computadora de la columna:

$$X_D(s) = G_{p_{11}}(s)R(s) + G_{p_{12}}(s)V(s)$$
$$X_B(s) = G_{p_{21}}(s)R(s) + G_{p_{22}}(s)V(s)$$

donde $X_D$ es la composición superficial, clave principal; $X_B$ es la composición de los sedimentos, clave principal; $R(s)$ es la razón de reflujo y $V(s)$ es la razón de vapor. Ambas razones están en porcentaje de rango.

a) Se debe calcular la medida de interacción de estado estacionario de este sistema. ¿Los circuitos de control de composición se refuerzan o combaten entre sí? ¿Es correcta la agrupación por pares de las variables controladas y manipuladas?
b) Se deben diseñar los desacopladores para este sistema y exponer brevemente cualquier problema que haya en la implementación de dichos desacopladores. ¿Cuáles son las sugerencias del lector?

**8-27.** Para este problema se considera el proceso 2 x 2 que se ilustra en la figura 8-81. Las siguientes funciones de transferencia se determinaron mediante la prueba de pulso:

$$X_1(s) = G_{p_{11}}(s)M_1(s) + G_{p_{12}}(s)M_2(s)$$
$$X_2(s) = G_{p_{21}}(s)M_1(s) + G_{p_{22}}(s)M_2(s)$$

donde:

$$G_{p_{11}}(s) = \frac{0.81}{(1.2s+1)(0.63s+1)}\frac{\%}{\%}$$
$$G_{p_{12}}(s) = \frac{1.2}{(2.3s+1)(1.1s+1)}\frac{\%}{\%}$$
$$G_{p_{21}}(s) = \frac{1.1e^{-0.5s}}{1.2s+1}\frac{\%}{\%}$$
$$G_{p_{22}}(s) = \frac{0.6e^{-0.7s}}{2s+1}\frac{\%}{\%}$$
$$G_{v_1}(s) = \frac{0.5}{2.0s+1}\frac{\%}{\%}$$
$$G_{v_2}(s) = \frac{1.5}{1.8s+1}\frac{\%}{\%}$$

a) Se debe obtener la agrupación por pares correcta para este sistema.
b) Se debe dibujar el diagrama de bloques completo y la gráfica de flujo de señal del sistema.
c) Se deben determinar las funciones de transferencia de circuito cerrado, $C_1(s)/R_1(s)$ y $C_2(s)/R_2(s)$.
d) Se debe diseñar el desacoplador para este sistema y exponer su implementación.

---

# Capítulo 9: Modelos y simulación de los sistemas de control de proceso

Los modelos matemáticos y la simulación por computadora son indispensables en el análisis y diseño de los sistemas de control para procesos complejos no lineales. Con ellas se complementan las herramientas para análisis de sistemas lineales que se estudiaron en los capítulos anteriores de este libro.

Una pregunta que surge en este punto es: ¿Cuándo se debe utilizar la simulación por computadora en el diseño de un sistema de control? En la toma de tal decisión existen varios factores que deben tomarse en cuenta. Primeramente se debe considerar qué tan crítico es el desempeño del sistema de control para la operación segura y rentable del proceso; por ejemplo, el sistema de control para un compresor centrífugo grande es lo suficientemente crítico como para hacer la simulación; en cambio, el de un controlador sencillo de nivel puede no serlo. La segunda consideración es la confiabilidad del desempeño del sistema de control, lo cual generalmente depende de la experiencia y familiaridad que se tenga con una aplicación particular del control; por ejemplo, un ingeniero con experiencia no se molestaría en simular el control de temperatura para un ataque de reacción con agitación continua; en cambio, el mismo proyecto de simulación puede ser bastante interesante e informativo para un estudiante de facultad en su primer curso de control. La tercera consideración es el tiempo y esfuerzo que se requiere para llevar a cabo la simulación, que puede ir desde algunas horas, para un proceso relativamente simple, hasta varios meses-hombre, en un proceso complejo que se simula por primera vez. Entre otras consideraciones se incluyen la disponibilidad de los recursos de cómputo, personal con experiencia y suficientes datos acerca del proceso para realizar la simulación.

Los tres pasos principales para realizar la simulación dinámica de un proceso son:

1. Desarrollo del modelo matemático del proceso y de su sistema de control.
2. Resolución de las ecuaciones del modelo.
3. Análisis de los resultados.

Las primeras tres secciones de este capítulo se dedican al primero de estos pasos; en ellas se incluye el desarrollo de los modelos matemáticos de dos procesos complejos: una torre de destilación de componentes múltiples y un horno de proceso. El resto del capítulo se dedica a la resolución de las ecuaciones del modelo. A pesar de que el tercer paso no se abordará de manera formal, no se exagera en la importancia de analizar apropiadamente los resultados de la simulación, sin lo cual se desperdicia todo el esfuerzo que se hace al realizar la simulación; en este análisis se debe incluir la verificación de los resultados de la simulación siempre que sea posible.

## 9-1. DESARROLLO DE MODELOS DE PROCESO COMPLEJOS

En el capítulo 3 se presentaron los principios básicos para escribir las ecuaciones con que se describe la respuesta de las variables del proceso. En resumen, la forma general de la ecuación fundamental de conservación es:

$$\text{Acumulación} = \text{Entrada} - \text{Salida} \quad (9-1)$$

La cantidad que se conserva puede ser masa total, masa de un componente, energía y momento. Los términos de razón de entrada y salida se deben tomar en cuenta para todos los mecanismos debido a los cuales la cantidad que se conserva entra o sale del volumen de control o porción del universo sobre la que se realiza el "balance"; por ejemplo, todas las cantidades que se conservan enunciadas pueden fluir hacia adentro o hacia afuera del volumen de control (convección); la energía puede entrar y salir mediante conducción de calor y radiación; los componentes se pueden transferir mediante difusión, y el momento se puede generar o destruir mediante fuerzas mecánicas. En el caso de las reacciones químicas, la razón de reacción se debe tomar en cuenta como término de entrada para los productos de la reacción, y como término de salida para los reactivos.

La razón de acumulación de la ecuación (9-1) siempre tiene la forma:

$$\left[\text{Razón de acumulación}\right] = \frac{d}{dt}\left[\text{Cantidad que se conserva}\right] \quad (9-2)$$

donde $t$ es tiempo. Esto significa que los modelos matemáticos consisten en un sistema de ecuaciones diferenciales simultáneas de primer orden o, en su forma más simple, en una sola ecuación diferencial de primer orden cuya variable independiente es el tiempo. Además, en el modelo puede haber ecuaciones algebraicas que resultan de las expresiones para las propiedades físicas y para las razones de entrada y salida, así como de las ecuaciones de balance en las que se desprecia el término de acumulación.

Para expresar la cantidad total que se conserva y las razones de entrada y salida en términos de las variables del proceso (es decir, temperaturas, presiones, composiciones), estas variables deben ser relativamente uniformes en todo el volumen de control; cuando este requerimiento se satisface en un modelo en que el proceso se divide en cierta cantidad de volúmenes de control de tamaño finito o "localidades", se dice que el modelo es un "modelo de parámetros localizados". Por otro lado, los "modelos de parámetros distribuidos" se obtienen cuando las variables del proceso varían continuamente con la posición; en este caso las ecuaciones de balance se deben aplicar a cada punto del proceso y el modelo matemático constará de ecuaciones diferenciales parciales cuyas variables independientes son el tiempo y la posición; aun en este caso, cada ecuación es siempre de primer orden respecto a la variable tiempo. La única forma en que las ecuaciones pueden ser de orden superior al primero es cuando se combinan las ecuaciones para eliminar variables. Aquí se hace énfasis en el hecho de que las ecuaciones son de primer orden respecto al tiempo, porque este sirve de guía para el diseño de los programas de computadora con que se simula el proceso; esto se hace evidente en la sección 9-5.

Para desarrollar el modelo matemático es importante tener en cuenta la cantidad máxima de ecuaciones de balance independientes que se aplican a cada volumen de control (o punto) del proceso; en un sistema con $N$ componentes, éstas se expresan con:

- $N$ balances de masa
- 1 balance de energía
- 1 balance de momentos en cada dirección de interés, que pueden ser hasta tres.

Los $N$ balances de masa independientes pueden ser $N$ balances de componentes o un balance total de masa y $N - 1$ balances de componentes. Generalmente, el balance de momentos no se utiliza en la simulación del proceso, porque con él entran como incógnitas las fuerzas de reacción sobre el equipo y las paredes de la tubería, las cuales rara vez son de interés. Un balance más útil es la ecuación de Bernoulli extendida para incluir la fricción, el trabajo del vástago y la acumulación de energía cinética.

Además de las ecuaciones de balance se escriben otras ecuaciones de manera separada para expresar las propiedades físicas (por ejemplo, densidad, entalpía, coeficientes de equilibrio) y las razones (por ejemplo, de reacción, de transferencia de calor, de transferencia de masa) en términos de las variables del proceso (por ejemplo, temperatura, presión, composición).

A continuación se ilustran los conceptos que se resumieron arriba con el desarrollo de dos modelos; uno es el de una torre de destilación con múltiples componentes y el otro el de un horno de proceso. El primero es un ejemplo del modelo complejo con parámetros localizados, y el segundo es un ejemplo del modelo de parámetros distribuidos. Para que la notación se conserve simple, no se indica explícitamente que las variables son funciones del tiempo, por ejemplo, para $T(t)$ se escribe simplemente $T$.

El método que se utiliza para desarrollar los modelos matemáticos es el que se presentó en el capítulo 3, esto es:

1. Se escriben las ecuaciones de balance.
2. Se contabilizan las nuevas variables (incógnitas) que aparecen en cada ecuación, de manera que se tengan los antecedentes de la cantidad de variables y ecuaciones.
3. Se introducen relaciones hasta que se tiene la misma cantidad de ecuaciones y variables y se toman en cuenta todas las variables de interés.

El orden en que se escriben las ecuaciones de balance es el siguiente:

- Balance total de masa
- Balance de componentes (o elementos)
- Balance de energía
- Balance de energía mecánica (si acaso es importante)

## 9-2. MODELO DINÁMICO DE UNA COLUMNA DE DESTILACIÓN

Los modelos dinámicos de columnas de destilación se encuentran entre los sistemas de control más complejos que hay para una sola unidad de operación. La complejidad del modelo estriba en la gran cantidad de ecuaciones diferenciales no lineales que se deben resolver para estudiar la respuesta dinámica de la temperatura, de la composición en cada bandeja de la columna y la composición de los productos. Por ejemplo, para una columna con 100 bandejas y cinco componentes de alimentación se requiere resolver alrededor de 600 ecuaciones diferenciales -cinco de balance de componentes y una de balance de entalpía para cada una de las 100 bandejas- sin contar las ecuaciones que se requieren para simular el condensador, el rehervidor y el sistema de control. Además, para cada componente de cada bandeja se debe establecer una relación de equilibrio de fase y las relaciones hidráulicas en la bandeja; entalpía, densidad y otras propiedades físicas. En la mayoría de los casos estas relaciones son funcionales no lineales de la temperatura, la presión y la composición.

A continuación se considera la columna de destilación que se esboza en la figura 9-1, con $N$ componentes de alimentación, un condensador total y un rehervidor de termosifón; se tiene interés en la respuesta de la composición de los productos $x_D$ y $x_B$ a lo largo del tiempo. Las dos variables manipuladas son el flujo de vapor que llega al rehervidor y la razón de destilación de producto. La razón de reflujo se maneja en el controlador del nivel del acumulador, y la de producción de sedimentos, con el controlador de nivel de sedimentos; éste es un arreglo usual de controladores. Se supone que la presión en la columna no se controla, y que es esencialmente constante desde la parte baja hasta la parte alta, es decir, la caída de presión de una bandeja a otra es despreciable.

A pesar de que únicamente se tiene interés en la composición y las razones de las corrientes del producto, éstas dependen de las condiciones en las bandejas, el rehervidor y el condensador, lo cual provoca que se divida la columna en cierta cantidad de volúmenes de control, uno por cada bandeja, uno para el rehervidor y uno para el condensador. Para cada uno de estos volúmenes de control se deben escribir los $N$ balances de masa y las ecuaciones de balance de entalpía; todas estas ecuaciones se deben resolver simultáneamente, junto con las ecuaciones adicionales con que se describe el sistema de control.

### Ecuaciones de bandeja

En la figura 9-2 se esboza una bandeja típica, la bandeja $j$, contando de arriba a abajo. La primera ecuación que se escribe es el balance total de masa, el cual, cuando no hay reacciones químicas, se puede escribir en unidades molares. Si se supone que a causa de su baja densidad la acumulación de masa en la fase de vapor es despreciable, en comparación con la de la fase líquida, el balance total de masa es:

$$\frac{dM_j}{dt} = L_{j-1} + V_{j+1} - L_j - V_j \quad (9-3)$$

donde:
- $M_j$ es el líquido residual en la bandeja $j$, kgmol
- $L_j$ es la razón de líquido que sale de la bandeja $j$ en kgmol/s
- $V_j$ es la razón de vapor que sale de la bandeja $j$ en kgmol/s

Para escribir el balance de masa del componente en cada bandeja, se supone que el líquido en la misma está perfectamente mezclado, de manera que las propiedades del líquido que sale de la bandeja son iguales a las del líquido que resta en la misma. Sin esta aproximación de parámetro localizado, sería necesario escribir los balances en cada punto de cada bandeja y las ecuaciones resultantes serían diferenciales parciales. Una cuestión importante es saber qué hacer con el líquido que sigue hacia abajo; se puede suponer que se mezcla perfectamente con el que está en la bandeja y tratar ésta como un tanque con mezclado perfecto (retardo en las propiedades del líquido), como una tubería en la que no hay mezclado (tiempo muerto) o despreciar los dos tipos de tratamiento. Se notará que la única diferencia entre la primera posición y la última consiste en que los moles del líquido que va hacia abajo forman parte o no del que queda en la bandeja ($M_j$). Entonces, el balance del componente $i$ en la bandeja $j$ es:

$$\frac{d(M_jx_{i,j})}{dt} = L_{j-1}x_{i,j-1} + V_{j+1}y_{i,j+1} - L_jx_{i,j} - V_jy_{i,j} \quad (9-4)$$

donde:
- $x_{i,j}$ es la fracción molar del componente $i$ en el líquido de la bandeja $j$
- $y_{i,j}$ es la fracción molar del componente $i$ en el vapor que sale de la bandeja $j$

La ecuación (9-4) se aplica a $N - 1$ componentes, ya que la suma de las fracciones molares debe ser uno:

$$\sum_{i=1}^{N}x_{i,j} = 1 \quad (9-5)$$

En este punto se tienen $N + 1$ ecuaciones para cada bandeja; se incluye la ecuación (9-5), la cual no es una ecuación de balance, y $2N + 3$ variables; es decir, $2N$ composiciones de líquido y vapor, las razones de líquido y vapor y los moles de líquido en la bandeja. Si se desprecian las pérdidas de calor, el balance de energía en la bandeja $j$ se expresa mediante:

$$\frac{d(M_jh_j)}{dt} = L_{j-1}h_{j-1} + V_{j+1}H_{j+1} - L_jh_j - V_jH_j \quad (9-6)$$

donde:
- $h_j$ es la entalpía molar del líquido en la bandeja $j$, J/kgmol
- $H_j$ es la entalpía molar del vapor que sale de la bandeja $j$, J/kgmol

En la ecuación (9-6), así como en los balances de energía que siguen, se supone que la entalpía del líquido, $h_j$, es esencialmente igual a su energía interna. En rigor, en el término de acumulación se debe utilizar la energía interna en lugar de la entalpía.

Ahora se tienen $(N + 2)$ ecuaciones por bandeja y $(2N + 5)$ variables, las dos nuevas variables son la entalpía del líquido ($h_j$) y del vapor ($H_j$). Puesto que se utilizaron ya todas las ecuaciones de conservación de interés, ahora se debe recurrir a la termodinámica y a otras relaciones para calcular las variables que restan; la composición del vapor se puede obtener a partir de la relación de Murphree para la eficiencia en una bandeja:

$$\eta_M = \frac{y_{i,j} - y_{i,j+1}}{y_{i,j}^* - y_{i,j+1}} \quad (9-7)$$

donde:
- $\eta_M$ es la eficiencia de Murphree para la bandeja (se supone constante)
- $y_{i,j}^*$ es la fracción molar del componente $i$ en el vapor, en equilibrio con el líquido que sale de la bandeja $j$

Al aplicar la ecuación (9-7) a cada componente de cada bandeja, se obtienen $N$ ecuaciones adicionales por bandeja, a la vez que se introducen $N$ variables nuevas, las fracciones molares en equilibrio $y_{i,j}^*$. Entonces, de las $N$ relaciones de equilibrio vapor-líquido, se obtiene:

$$y_{i,j}^* = K_i(T_j, P, x_{1,j}, x_{2,j}, \ldots, x_{N,j})x_{i,j} \quad (9-8)$$

donde:
- $K_i$ es el coeficiente de equilibrio para el componente $i$
- $T_j$ es la temperatura en la bandeja $j$, K
- $P$ es la presión en la columna, N/m²

La ecuación (9-8) se puede escribir para cada componente en cada bandeja, con lo que se obtienen $N$ ecuaciones adicionales por bandeja y sólo una nueva variable, la temperatura $T_j$, debido a que la presión es común a todas las bandejas. Con base en el hecho de que la suma de las fracciones molares de vapor debe ser igual a la unidad, se obtiene una ecuación adicional:

$$\sum_{i=1}^{N}y_{i,j} = 1 \quad (9-9)$$

En este punto se tienen $3N + 6$ variables y $(3N + 3)$ ecuaciones para cada bandeja.

A partir de la hidráulica de la bandeja se puede obtener una relación entre los moles del líquido que están en la bandeja y la razón de líquido que sale de la misma; una ecuación popular es la fórmula de Francis para presas:

$$L_j = k\rho_j(M_j - M_{0_j})^{1.5} \quad (9-10)$$

donde:
- $M_{0_j}$ es el líquido que se retiene con flujo cero, kgmol
- $\rho_j$ es la densidad molar del líquido, kgmol/m³
- $A$ es el área transversal de la bandeja, m²
- $k$ es un coeficiente dimensional, m$^{1.5}$/s

Las relaciones finales se obtienen a partir de las correlaciones de las propiedades físicas:

$$h_j = h(T_j, P, x_{1,j}, x_{2,j}, \ldots, x_{N,j}) \quad (9-11)$$
$$H_j = H(T_j, P, y_{1,j}, y_{2,j}, \ldots, y_{N,j}) \quad (9-12)$$
$$\rho_j = \rho(T_j, P, x_{1,j}, x_{2,j}, \ldots, x_{N,j}) \quad (9-13)$$

De esto se obtiene un total de $3N + 7$ ecuaciones con $3N + 7$ variables por bandeja y, por lo tanto, se tiene una ecuación para calcular cada variable. De las ecuaciones, $N + 1$ son ecuaciones diferenciales ordinarias de primer orden, y el resto son ecuaciones algebraicas.

### Bandeja de alimentación y superior

A pesar de que las ecuaciones de bandeja se aplican a todas las bandejas, las ecuaciones para la de alimentación y la superior son ligeramente diferentes. En la bandeja de alimentación se tiene un término adicional de entrada, la alimentación, lo cual significa que en el miembro derecho de las ecuaciones de balance se deben añadir los siguientes términos de razón:

- Masa total: $F$ kgmol/s, en la ecuación (9-3)
- Masa del componente: $Fz_i$ kgmol/s, en la ecuación (9-4)
- Energía: $Fh_F$ J/s, en la ecuación (9-6)

donde:
- $z_i$ es la fracción molar del componente $i$ en la alimentación
- $h_F$ es la entalpía molar de la alimentación, J/kgmol

Para la bandeja superior, las ecuaciones son las mismas que para las demás, con excepción de que el caudal de líquido que entra a la bandeja es el reflujo. En la notación esto significa que el término $L_{j-1}$ es la razón de reflujo, $x_{i,j-1}$ es la fracción de mol del componente $i$ en el reflujo, y $h_{j-1}$ es la entalpía molar del reflujo.

### Rehervidor

En la figura 9-3 se muestra el diagrama de un rehervidor; se supone que la razón de recirculación a través del rehervidor de termosifón es alta, en comparación con la razón de sedimentación, de manera que en la parte baja de la torre el líquido está bien mezclado y tiene la misma composición que el líquido en los tubos del rehervidor. Por lo tanto, el balance de masa total es:

$$\frac{dM_B}{dt} = L_{NT} - V_{NT+1} - B \quad (9-14)$$

donde:
- $M_B$ es el líquido que se retiene en el fondo de la torre, incluyendo el líquido en los tubos del rehervidor, kgmol
- $L_{NT}$ es la razón de líquido de la bandeja $NT$, la última bandeja, kgmol/s
- $B$ es la razón de producción de sedimentos, kgmol/s
- $V_{NT+1}$ es la razón de vapor que entra a la última bandeja, kgmol/s

Los balances de masa del componente para $N - 1$ de los componentes se pueden escribir como sigue:

$$\frac{d(M_Bx_{i,B})}{dt} = L_{NT}x_{i,NT} - V_{NT+1}y_{i,NT+1} - Bx_{i,B} \quad (9-15)$$

donde:
- $x_{i,B}$ es la fracción molar del componente $i$ en el fondo de la torre
- $y_{i,NT+1}$ es la fracción molar del componente $i$ en la corriente de vapor que entra a la última bandeja

Para el componente $N$ se aprovecha el hecho de que la suma de las fracciones de mol debe ser igual a la unidad:

$$\sum_{i=1}^{N}x_{i,B} = 1 \quad (9-16)$$

En el balance de energía se debe considerar la capacidad de transferencia de calor del rehervidor; para ello se expresa la razón de calor como una función de la diferencia de temperatura:

$$\frac{d(M_Bh_B)}{dt} = L_{NT}h_{NT} - V_{NT+1}H_{NT+1} - Bh_B + Q_R \quad (9-17)$$

donde:
- $h_B$ es la entalpía molar del líquido en el fondo de la torre, J/kgmol
- $H_{NT+1}$ es la entalpía molar del vapor que entra a la última bandeja, J/kgmol
- $U_R$ es el coeficiente total de transferencia de calor del rehervidor, J/s-m²K
- $A_R$ es el área de transferencia de calor del rehervidor, m²
- $T_S$ es la temperatura del vapor fuera de los tubos del rehervidor, K
- $T_B$ es la temperatura en el rehervidor y en el fondo de la columna, K

$$Q_R = U_RA_R(T_S - T_B)$$

Se supone que el vapor que sale del rehervidor está en equilibrio con el líquido en el fondo de la torre y, por lo tanto, las fracciones molares de vapor se expresan con las $N$ relaciones de equilibrio:

$$y_{i,NT+1}^* = K_i(T_B, P, x_{1,B}, x_{2,B}, \ldots, x_{N,B})x_{i,B} \quad (9-18)$$

También se puede utilizar el hecho de que la suma de las fracciones de mol de vapor es igual a la unidad:

$$\sum_{i=1}^{N}y_{i,NT+1} = 1 \quad (9-19)$$

En este punto, para el rehervidor se tienen $2N + 3$ ecuaciones y $2N + 7$ variables: $M_B$, $B$, $V_{NT+1}$, $x_{i,B}$, $y_{i,NT+1}$, $h_B$, $H_{NT+1}$, $T_B$ y $T_S$. De la relación entre la razón de producción de sedimentos y la retención de los mismos resulta una ecuación adicional, la cual se establece en el controlador proporcional de nivel (LIC202); se supone que la válvula de control es lineal:

$$B = K_{BC}\left(\frac{M_B - A_B\rho_BM_{B0}}{2}\right)B_{max} \quad (9-20)$$

donde:
- $K_{BC}$ es la ganancia del controlador, sin dimensiones
- $M_{B0}$ es la retención con flujo cero, kgmol
- $\rho_B$ es la densidad molar del líquido, kgmol/m³
- $A_B$ es el área de la sección transversal de la columna, m²
- $B_{max}$ es la razón de sedimentos cuando la salida del controlador de nivel es máxima, kgmol/s
- $R_L$ es el rango del transmisor de nivel, m

Las propiedades físicas se obtienen con relaciones termodinámicas:

$$h_B = h(T_B, P, x_{1,B}, x_{2,B}, \ldots, x_{N,B}) \quad (9-21)$$
$$H_{NT+1} = H(T_B, P, y_{1,NT+1}, y_{2,NT+1}, \ldots, y_{N,NT+1}) \quad (9-22)$$
$$\rho_B = \rho(T_B, P, x_{1,B}, x_{2,B}, \ldots, x_{N,B}) \quad (9-23)$$

Con esto queda una variable más por calcular, la temperatura del vapor, $T_S$, para lo cual es necesario definir un nuevo volumen de control, la cámara de vapor externa a los tubos del rehervidor; para los balances de la cámara de vapor se supone que la condensación no se acumula, es decir, con la trampa de vapor se remueve todo el vapor condensado en la misma razón en que se produce. También se supone que el vapor en la cámara está saturado y que los tubos del rehervidor están casi a la misma temperatura que el vapor que se condensa; es decir, se desprecia la resistencia a la transferencia de calor en el lado de condensación de los tubos del rehervidor. Por lo tanto, la acumulación de energía se concentra en los tubos del rehervidor, debido a que la masa del vapor es pequeña en comparación con la masa de metal de los tubos. Con base en esta suposición, el balance de energía en la cámara de vapor se expresa mediante:

$$C_{MR}\frac{dT_S}{dt} = F_SH_{SS} - F_Sh_S(T_S) - U_RA_R(T_S - T_B) \quad (9-24)$$

donde:
- $C_{MR}$ es la capacitancia calorífica de los tubos del rehervidor, J/K
- $F_S$ es la razón de flujo del vapor, kg/s
- $H_{SS}$ es la entalpía con que entra el vapor, J/kg
- $h_S(T_S)$ es la entalpía del vapor condensado cuando sale a través de la trampa de vapor, J/kg

Se notará que en la ecuación (9-24) la acumulación de vapor en la cámara se hace despreciable mediante la suposición de que la razón de flujo del vapor condensado que sale es igual a la del que entra en la cámara.

La razón de flujo del vapor se calcula a partir del modelo de la válvula de control:

$$F_S = C_{VS}vp_S\sqrt{\frac{P_{SS} - P_S}{G}} \quad (9-25)$$

donde:
- $C_{VS}$ es el factor de capacidad de la válvula de vapor, kg/s (N/m²)$^{1/2}$
- $vp_S$ es la posición de la válvula de vapor en fracción de desplazamiento
- $P_{SS}$ es la presión con que se suministra el vapor, N/m²
- $P_S$ es la presión en la cámara de vapor, N/m²

La posición de la válvula puede ser una variable de entrada a la columna o la variable manipulada que se utiliza para controlar la fracción molar de uno de los componentes en la producción de sedimentos. En este último caso, se calcula con base en el modelo del controlador de composición (ARC202):

$$vp_S = f_{AC}(x_{k,B}, x_{k,B}^{sp}) \quad (9-26)$$

donde:
- $f_{AC}$ es la función del controlador analizador
- $x_{k,B}$ es la fracción molar del componente clave en la producción de sedimentos
- $x_{k,B}^{sp}$ es el punto de control para la fracción molar del componente clave

La presión en la cámara de vapor es una función de la temperatura, si se supone que el vapor está saturado cuando se condensa:

$$P_S = P_S(T_S) \quad (9-27)$$

Con esto se completa el modelo de la cámara de vapor, en el cual se introducen tres variables adicionales: $F_S$, $vp_S$ y $P_S$; una ecuación de balance de entalpía y tres ecuaciones algebraicas para calcular la variable de estado, $T_S$.

### Modelo de condensador

En la figura 9-4 se muestra un diagrama de todo el condensador; la corriente de vapor que entra al condensador es el vapor que sale de la bandeja superior de la columna (bandeja número 1) y el líquido que sale del tambor acumulador se reparte entre el producto destilado ($D$) y el reflujo a la columna ($L_R$), el cual es la entrada de líquido a la bandeja superior. La razón del producto destilado se manipula mediante el controlador de composición del producto superficial (ARC201) y la razón de reflujo se manipula mediante un controlador proporcional de nivel en el tambor del acumulador (LIC201).

En una columna con un condensador total, la presión se determina únicamente mediante el balance de calor; es decir, si al rehervidor se le suministra calor a una razón superior a la razón con que se elimina en el condensador, la presión en la columna aumenta conforme transcurre el tiempo. Lo anterior tiene el efecto de incrementar la temperatura en todas las bandejas y en el condensador, con lo cual se ocasiona un incremento en la razón de calor que se elimina en el condensador; dicho incremento continúa hasta que se satisface nuevamente el balance de calor con una presión (más alta) de estado estacionario. Este mecanismo de autorregulación se presenta aun cuando se controle la presión y, por tanto, la presión de la columna se puede controlar mediante la manipulación de la razón de transferencia de calor en el condensador o en el rehervidor. Con el fin de simplificar, se supondrá que no se controla la presión en la columna y que el condensador está a su máxima capacidad, con lo cual se logra mantener la presión de la columna en el punto más bajo que permite la capacidad del condensador, de lo cual generalmente resulta una mayor separación de los componentes.

Al elaborar el modelo del condensador se despreció la acumulación de masa en la fase de vapor, lo cual significa que el líquido que entra al tambor acumulador tiene la misma composición y razón de flujo que el vapor que entra al condensador y, por tanto, no se requieren balances de material alrededor del volumen de control del condensador. Sin embargo, como la entalpía y la temperatura cambian al haber condensación, se requiere un balance de energía:

$$C_{MC}\frac{dT_C}{dt} = V_1(H_1 - h_C) - U_CA_C(T_C - T_A) \quad (9-28)$$

donde:
- $T_C$ es la temperatura en el condensador, K
- $T_A$ es la temperatura del aire de enfriamiento en el exterior de los tubos del condensador, K
- $h_C$ es la entalpía molar del líquido que sale del condensador, J/kgmol
- $C_{MC}$ es la capacidad calorífica de los tubos del condensador, J/K
- $U_C$ es el coeficiente de transferencia de calor del condensador, J/s-m²-K
- $A_C$ es el área de transferencia de calor del condensador, m²

Al escribir la ecuación (9-28) se hicieron varias consideraciones para simplificar: primera, se supuso que la acumulación de energía únicamente tiene lugar en las paredes de los tubos del condensador como el medio de enfriamiento externo, están a temperaturas uniformes $T_C$ y $T_A$, respectivamente; la tercera suposición es que la resistencia a la transferencia de calor en el lado de condensación de los tubos de condensación es despreciable, en comparación con la resistencia a la transferencia de calor del lado que está en contacto con el aire. La suposición de que el líquido que sale del condensador tiene la misma composición que el vapor que abandona la columna, se utiliza para calcular la entalpía del líquido que sale del condensador:

$$h_C = h(T_C, P, x_{1,1}, x_{2,1}, \ldots, x_{N,1}) \quad (9-29)$$

y la presión en la columna, así como la presión de punto de burbuja de este líquido a la temperatura del condensador, se calcula mediante:

$$P = P_{B}(T_C, y_{1,1}, y_{2,1}, \ldots, y_{N,1}) \quad (9-30)$$

donde:
- $P_B$ es la presión de punto de burbuja en función de la temperatura y la composición, N/m²

Se notará que con la combinación de las ecuaciones (9-28) y (9-30) se elabora el modelo del efecto de regulación de presión del balance de calor que se trató anteriormente. En el modelo, al incrementar la razón de vapor que sale de la columna, $V_1$, se provoca un aumento en la temperatura $T_C$, lo cual, a su vez, causa un incremento en la razón de eliminación de calor, ecuación (9-28), y en la presión de la columna, ecuación (9-30). Si la presión se controlara mediante la manipulación del flujo de aire de enfriamiento a través del condensador, entonces $U_C$ y $T_A$ se convertirían en variables en la ecuación (9-28), por lo que serían necesarios los balances para el lado del condensador en contacto con el aire. El cálculo de $T_A$ queda como ejercicio para el estudiante.

### Tambor acumulador del condensador

Ahora la atención se vuelve al tambor acumulador del condensador de la figura 9-4. En estado estacionario, la razón, composición y entalpía de las corrientes de líquido que salen del acumulador -el reflujo y el producto destilado- son las mismas que las del líquido que sale del condensador; sin embargo, el líquido en el acumulador constituye un retardo de tiempo para los cambios en razón, composición y entalpía; a esto se debe que en el modelo dinámico sea necesario incluir los balances referentes al acumulador. El retardo para los cambios en la razón de vapor se obtiene con base en el balance total de masa:

$$\frac{dM_D}{dt} = V_1 - L_R - D \quad (9-31)$$

donde:
- $M_D$ es el líquido que se retiene en el acumulador, kgmol
- $L_R$ es la razón de reflujo, kgmol/s
- $D$ es la razón del producto destilado, kgmol/s

En la ecuación (9-31) la razón de líquido en el acumulador es la misma que la razón de vapor en el condensador, ya que se desprecia la acumulación de masa en el condensador.

El retardo para los cambios en la composición del vapor se obtiene con base en los $N - 1$ balances de masa de los componentes:

$$\frac{d(M_Dx_{i,D})}{dt} = V_1y_{i,1} - (L_R + D)x_{i,D} \quad (9-32)$$

donde $x_{i,D}$ es la fracción molar del componente $i$ en el líquido del acumulador.

La fracción molar del componente $N$ se obtiene a partir del hecho de que la suma de las fracciones molares debe ser igual a la unidad:

$$\sum_{i=1}^{N}x_{i,D} = 1 \quad (9-33)$$

El modelo para el retardo de los cambios de entalpía se hace con el balance de energía:

$$\frac{d(M_Dh_D)}{dt} = V_1H_1 - (L_R + D)h_D \quad (9-34)$$

donde:
- $h_D$ es la entalpía molar del líquido en el acumulador, J/kgmol

Hasta ahora se tienen $N + 2$ ecuaciones y $N + 4$ variables: $M_D$, $x_{i,D}$, $h_D$, $V_1$, $L_R$ y $D$. La ecuación para la razón de reflujo se obtiene del controlador proporcional del nivel del acumulador (LIC201); en su forma más simple, si se supone que el control del caudal del reflujo es perfecto (FRC201B):

$$L_R = L_{R,max}K_{LC}(M_D - M_{D0}) \quad (9-35)$$

donde:
- $L_{R,max}$ es la razón de reflujo cuando la salida del controlador está al máximo, kgmol/s
- $K_{LC}$ es la ganancia del controlador de nivel (sin dimensiones)
- $M_{D0}$ es el líquido que se retiene en el acumulador cuando la razón de reflujo es cero, kgmol
- $M_{D,max}$ es el líquido que se retiene en el acumulador cuando el nivel es máximo, kgmol

En la ecuación (9-35) se desprecian las variaciones en la densidad del líquido; en cambio, con la ecuación (9-20) se tiene un modelo alternativo para el controlador de nivel, en el cual se consideran las variaciones de densidad. Cualquiera de los modelos se puede utilizar para cualquier controlador de nivel.

La ecuación final que se necesita para completar el modelo del tambor acumulador es la ecuación para la razón de destilación $D$, en la cual se requiere un modelo del circuito de control de la composición del destilado. Con el fin de simplificar, el analizador (AT201) se simula con un retardo de primer orden:

$$\tau_{AT}\frac{d\delta y}{dt} + \delta y = \frac{y_{k,1} - y_0}{y_{max} - y_0} \quad (9-36)$$

donde:
- $\delta y$ es la señal normalizada que sale del analizador
- $y_{k,1}$ es la fracción molar del componente clave en el vapor que sale de la bandeja superior
- $y_0$ es el límite inferior del rango a que se calibra el analizador (fracción molar)
- $y_{max}$ es el límite superior del rango a que se calibra el analizador
- $\tau_{AT}$ es la constante de tiempo del retardo de primer orden, s

Se notará que, conforme la fracción molar varía de $y_0$ a $y_{max}$, la señal $\delta y$ del analizador varía de cero a la unidad.

El controlador analizador (ARC201) se modela como un controlador PID (proporcional-integracional-derivativo) (ver ejemplo 9-4):

$$D^{sp} = f_{AC}(\delta y, y^{sp}, K_{AC}, \tau_{IAC}, \tau_{DAC}) \quad (9-37)$$

donde:
- $D^{sp}$ es la salida del controlador y el punto de control del controlador del caudal del producto destilado (FRC201A), kgmol/s
- $y^{sp}$ es el punto de control del controlador analizador (ARC201)
- $K_{AC}$ es la ganancia del controlador analizador
- $\tau_{IAC}$ es el tiempo de integración del analizador controlador, s
- $\tau_{DAC}$ es el tiempo de derivación del controlador analizador, s

Finalmente, se puede suponer que el controlador de flujo es lo suficientemente rápido como para mantener el destilado igual al punto de control en todo momento:

$$D = D^{sp} \quad (9-38)$$

Sin embargo, se deben fijar límites al destilado para asegurar que siempre sea positivo y menor al caudal máximo que puede controlar el controlador de flujo:

$$0 \leq D \leq D_{max} \quad (9-39)$$

donde:
- $D_{max}$ es el caudal máximo de destilado que se puede medir con el transmisor de flujo (FT201A), kgmol/s

Con esto se completa el modelo de la columna. Para hacer el modelo se dividió la columna en $NT$ volúmenes de control, uno por cada bandeja; para el rehervidor y su cámara de vapor, el condensador y su tambor acumulador se utilizaron volúmenes adicionales. Las diversas ecuaciones diferenciales y algebraicas que se escribieron, incluidas las de física básica y principios de química, son necesarias para calcular las variables del proceso: razones de flujo, composiciones y temperaturas.

### Condiciones iniciales

Para simular la columna se necesitan las condiciones iniciales de todas las variables de estado. Las variables de estado son aquellas que aparecen en las derivadas de las ecuaciones diferenciales; el nombre se origina en el hecho de que con estas variables se define un estado único del modelo en cualquier instante. Puesto que todas las ecuaciones diferenciales son de primer orden, únicamente se requiere una condición inicial por ecuación diferencial. Las variables de estado del modelo son las siguientes:

- Los moles de líquido en cada bandeja: $M_j$, $j = 1, 2, \ldots, NT$
- en el fondo de la columna: $M_B$
- en el tambor del acumulador: $M_D$
- Fracciones molares de líquido por bandeja: $x_{i,j}$, $i = 1, 2, \ldots, N-1$; $j = 1, 2, \ldots, NT$
- en el fondo de la columna: $x_{i,B}$, $i = 1, 2, \ldots, N-1$
- en el tambor del acumulador: $x_{i,D}$, $i = 1, 2, \ldots, N-1$
- Entalpía molar del líquido en cada bandeja: $h_j$, $j = 1, 2, \ldots, NT$
- en el fondo de la columna: $h_B$
- y en el tambor del acumulador: $h_D$
- Temperatura en la cámara de vapor: $T_S$
- y en el condensador: $T_C$
- Salida del transmisor analizador (AT201): $\delta y$
- Salidas de los controladores de composición: $vp_S$ y $D^{sp}$

Las condiciones iniciales de estas variables se determinan por el tipo de corrida que se trate de simular: el comportamiento más común que se analiza en los estudios de control de sistemas continuos es el de la respuesta del sistema a los cambios en las variables de entrada (por ejemplo, perturbaciones y puntos de control), a partir de ciertas condiciones de diseño de estado estacionario. Para este tipo de comportamiento, con los valores iniciales de las variables de estado se deben satisfacer las ecuaciones del modelo en estado estacionario, es decir, todos los términos derivativos se fijan en cero. Para un modelo tan complejo como el que se acaba de presentar, se necesita un programa de computadora para resolver sistemas de ecuaciones algebraicas no lineales y calcular los valores iniciales de estado estacionario de las variables de estado, debido a que, cuando los términos derivativos se fijan en cero, las ecuaciones diferenciales se convierten en ecuaciones algebraicas; en los programas comunes para resolver sistemas de ecuaciones no lineales se incluyen los métodos de Newton-Raphson y cuasi Newton.

Otro tipo de corrida de simulación es el de puesta en operación de la columna. En este caso se puede suponer que las condiciones iniciales son aquellas en que las bandejas, el fondo de la columna y el acumulador están llenos de líquido con la composición y la entalpía de alimentación. Para la retención en la bandeja se suponen razones iniciales de flujo de líquido iguales a cero, es decir, retención mínima. Se puede suponer que la temperatura a lo largo de la columna, rehervidor y condensador es la de alimentación, y que la presión es igual a la presión de punto de burbujeo de la alimentación a esa temperatura; se pueden suponer muchas variaciones de tales condiciones. La mayor dificultad al simular la puesta en operación estriba en decidir e implementar la secuencia en que las diferentes entradas de la columna se llevan a sus valores de diseño; esto puede consumir tiempo si la simulación no se hace de un modo interactivo; es decir, con interacción completa entre el trabajo del ingeniero y la solución de las ecuaciones obtenida mediante la computadora.

### Variables de entrada

Las variables de entrada para el modelo son las siguientes:

- Razón de flujo de alimentación: $F$, fracción molar: $z_i$, $i = 1, 2, \ldots, N-1$, y entalpía: $h_F$
- Razón de flujo del vapor: $F_S$, presión de suministro: $P_{SS}$ y entalpía: $H_{SS}$
- Temperatura del aire para enfriar el condensador: $T_A$
- Puntos de control del controlador de composición: $y^{sp}$ y $x_B^{sp}$

En la corrida de simulación de perturbación se cambia el valor de diseño de cada una de estas variables, generalmente con una función rampa, y se analiza el tiempo de respuesta de la salida y de las variables internas. En algunas corridas se puede cambiar el valor de más de una variable a la vez. En la simulación de la puesta en operación, las variables se llevan a su valor de diseño en una secuencia que se diseña con ayuda de la simulación tendiente a lograr un tiempo de puesta en operación mínimo, consumo de energía mínimo o pérdida mínima de producto fuera de especificación.

### Resumen

En esta sección se desarrolló el modelo matemático de una columna de destilación de múltiples componentes. Entre las características del modelo se incluye la presión variable de la columna, un modelo hidráulico simple de la bandeja y modelos dinámicos simples del rehervidor y el condensador. En el desarrollo paso a paso del modelo se aprecia la utilización de los balances de material y energía, el equilibrio de fase, los modelos hidráulicos, las relaciones termodinámicas y los modelos del sistema de control para llegar al modelo completo de la columna.

## 9-3. MODELO DINÁMICO DE UN HORNO

En el ejemplo precedente se dividió la columna de destilación en un cierto número de volúmenes de control, y se supuso que los compuestos, temperaturas y otras variables son uniformes a lo largo de cada volumen de control; esto significa que las propiedades están "concentradas" en cada volumen de control. En este ejemplo se estudiará el modelo de un horno donde las propiedades se distribuyen y el sistema no se puede dividir de manera conveniente en volúmenes de control con propiedades uniformes, y, por tanto, el presente es un ejemplo de un modelo de parámetro distribuido.

El sistema que se va a modelar es un horno, el cual se muestra en la figura 9-5, que se utiliza para calentar un gas en proceso mediante la combustión en el fogón externo al tubo. Se supondrá que la temperatura en el fogón es uniforme, pero que la temperatura del gas en el tubo y las paredes del mismo son funciones de la posición que se mide como la distancia $Z$ desde la entrada al tubo. La temperatura de salida del proceso se controla mediante un controlador por retroalimentación (TRC42), con el cual se manipula el flujo de combustible a los quemadores, $F_H$. Las perturbaciones posibles son el flujo, $F$, y la temperatura de entrada del fluido que se procesa, $T_i$, así como el contenido calorífico del combustible, $H_F$.

Puesto que en el tubo la temperatura del gas varía continuamente con la distancia $Z$, la cual se mide desde la entrada al tubo, se debe seleccionar como volumen de control una sección de tubo lo suficientemente corta $\Delta Z$, de manera que las propiedades se puedan suponer constantes dentro de sus límites, tal volumen de control se muestra en la figura 9-6. En los balances de masa de este volumen de control se aprecia que el flujo del fluido que se procesa, $F$, es constante, de acuerdo con la posición, si se desprecia la acumulación de masa en el volumen de control; esto se puede hacer con toda seguridad, ya que el interés principal consiste en hacer el modelo de los efectos de transferencia de calor. También se debe despreciar la conducción de calor a lo largo de las paredes del tubo, en la dirección del flujo. Bajo estas restricciones, en el volumen de control de la figura 9-6 el balance de energía del gas se expresa mediante:

$$\frac{\pi D_i^2}{4}\rho C_v\Delta Z\frac{\partial T}{\partial t} = FC_p(T|_{Z} - T|_{Z+\Delta Z}) + \pi D_i\Delta Zh_i(T_m - T) \quad (9-40)$$

donde:
- $T$ es la temperatura del fluido que se procesa, K
- $T_m$ es la temperatura de la pared del tubo, K
- $F$ es el flujo del fluido que se procesa, kgmol/s
- $D_i$ es el diámetro interno del tubo, m
- $h_i$ es el coeficiente de transferencia de calor de la capa interna, J/s-m²-K
- $\rho$ es la densidad molar del fluido y se supone constante, kgmol/m³
- $C_V$ es la capacidad calorífica molar del fluido a volumen constante; se supone constante, J/kgmol-K
- $C_p$ es la capacidad calorífica molar del fluido a presión constante; se supone constante, J/kgmol-K
- $\Delta Z$ es la longitud del volumen de control, m

En la ecuación (9-40) se debe diferenciar el término de la temperatura que entra al volumen de control, $T|_Z$, del de la temperatura que sale del volumen de control, $T|_{Z+\Delta Z}$, en los términos de entalpía, debido a que se toma la diferencia entre estos dos términos; sin embargo, esta diferenciación no se necesita para los términos de las razones de acumulación y transferencia de calor, pues se supone que el elemento es lo suficientemente pequeño como para representar la temperatura del mismo mediante un valor promedio con bastante aproximación; lo mismo se aplica para la temperatura de la pared, $T_m$. La capacidad calorífica a presión constante, $C_p$, se utiliza en los términos de entalpía del flujo, debido a que en ellos se incluye el trabajo del flujo; en cambio, la capacidad calorífica a volumen constante, $C_V$, se utiliza en el término de acumulación, porque no hay trabajo del flujo que se asocie con aquél. Por razones de simplificación, se supone que las propiedades físicas son constantes, pero también se puede suponer que son funciones de la temperatura y evaluarlas mediante $T$.

Con la ecuación (9-40) se representa el balance de energía en un volumen de control de longitud $\Delta Z$, que se ubica a cualquier distancia de la entrada del tubo. Ésta se puede reducir a un balance de energía en cualquier punto del tubo, si se divide entre el volumen del volumen de control y se toman límites cuando $\Delta Z \to 0$. A continuación se puede hacer lo siguiente:

$$\rho C_v\frac{\partial T}{\partial t} = -\frac{1}{A}\frac{\partial}{\partial Z}FC_pT + \frac{\pi D_i}{A}h_i(T_m - T) \quad (9-41)$$

donde la derivada en tiempo se cambia por una parcial, ya que se toma en un punto fijo del tubo y la temperatura es función tanto de la posición como del tiempo. Si se toman límites para la ecuación (9-41) cuando $\Delta Z \to 0$, se obtiene:

$$\rho C_v\frac{\partial T}{\partial t} = -\frac{FC_p}{A}\frac{\partial T}{\partial Z} + \frac{\pi D_i}{A}h_i(T_m - T) \quad (9-42)$$

en esta ecuación se substituyó la identidad:

$$\frac{\partial T}{\partial Z} = \lim_{\Delta Z \to 0}\frac{T|_{Z+\Delta Z} - T|_Z}{\Delta Z} \quad (9-43)$$

La (9-42) es una ecuación diferencial parcial con que se representa el balance de energía por unidad de volumen en cualquier punto del tubo y en cualquier instante. Puesto que se trata de una sola ecuación con dos variables, $T$ y $T_m$, se necesita otra ecuación, la cual se debe obtener a partir del balance de energía de la pared metálica del tubo en el volumen de control de la figura 9-6. Si se desprecia la conducción de calor a lo largo del tubo, se obtiene:

$$\rho_mC_m\frac{\pi}{4}(D_o^2 - D_i^2)\Delta Z\frac{\partial T_m}{\partial t} = \pi D_o\Delta Z\epsilon\sigma(T_R^4 - T_m^4) - \pi D_i\Delta Zh_i(T_m - T) \quad (9-44)$$

donde:
- $\rho_m$ es la densidad del metal del tubo; se supone constante, kg/m³
- $C_m$ es el calor específico del metal; se supone constante, J/kg-K
- $D_o$ es el diámetro externo del tubo, m
- $T_R$ es la temperatura que radia del fogón; se supone uniforme, K
- $\epsilon$ es la emisividad de la superficie del tubo; se supone constante
- $\sigma$ es la constante de Stefan-Boltzman, J/s-m²-K⁴

Al modelar la transferencia de calor mediante radiación en la ecuación (9-44), se supuso que el área del fogón es mucho mayor que la del tubo, y que en el fogón se abarca completamente al tubo. Para convertir la ecuación (9-44) en una ecuación diferencial parcial que se pueda aplicar a un punto del tubo, todo lo que se necesita es dividirla entre el volumen del elemento:

$$\rho_mC_m\frac{\partial T_m}{\partial t} = \frac{4D_o\epsilon\sigma(T_R^4 - T_m^4)}{D_o^2 - D_i^2} - \frac{4D_ih_i(T_m - T)}{D_o^2 - D_i^2} \quad (9-45)$$

Para obtener la ecuación (9-45) se introdujo una nueva variable, $T_R$, para la cual se puede obtener una ecuación a partir del balance de energía en el fogón:

$$M_RC_R\frac{dT_R}{dt} = F_HH_F\eta_F - \int_0^L\pi D_o\epsilon\sigma(T_R^4 - T_m^4)dZ \quad (9-46)$$

donde:
- $M_R$ es la masa efectiva del fogón, kg
- $C_R$ es el calor específico del fogón; se supone constante, J/kg-K
- $F_H$ es la razón de flujo del combustible, kg/s
- $H_F$ es el valor calorífico del combustible, J/kg
- $\eta_F$ es la eficiencia del horno; se supone constante
- $L$ es la longitud constante del tubo del horno, m

Se notará que en la ecuación (9-46) se requirió integrar la razón de transferencia de calor a las paredes del tubo, sobre la longitud del tubo. Con la eficiencia del horno, $\eta_F$, se toman en cuenta las pérdidas de calor a través de las paredes del tubo y de los gases de escape; con esta simplificación se evita el desarrollo de un modelo más detallado del fogón.

La razón del combustible, $F_H$, se calcula a partir de un modelo del sistema de control de temperatura, de la siguiente manera:

**Válvula de control; se desprecia el retardo del actuador**
$$F_{FH} = C_{VH}f_d(m)\sqrt{\Delta P} \quad (9-47)$$

**Controlador de temperatura (TRC42), como en el ejemplo 9-4**
$$m = F_c(T^{sp}, T_T, K_c, \tau_I, \tau_D) \quad (9-48)$$

**Transmisor de temperatura (TT42); se supone un retardo de primer orden**
$$\tau_T\frac{dT_T}{dt} = (T - T_T) \quad (9-49)$$

donde:
- $C_{VH}$ es el factor de capacidad de la válvula, kg/s-Pa$^{1/2}$
- $f_d(m)$ es la función característica de la válvula
- $\Delta P$ es la caída de presión a través de la válvula, Pa
- $T^{sp}$ es el punto de control de la temperatura, K
- $T_T$ es la señal del transmisor, K
- $K_c$ es la ganancia proporcional
- $\tau_I$ es el tiempo de integración, s
- $\tau_D$ es el tiempo de derivación, s
- $\tau_T$ es la constante de tiempo del sensor, s

Con esto se completa el desarrollo del modelo del horno, el cual consta de dos ecuaciones diferenciales parciales, ecuaciones (9-42) y (9-45), una ecuación íntegro-diferencial, ecuación (9-46), y el modelo del circuito de control de temperatura, ecuaciones (9-47) a (9-49). En función de las condiciones inicial y límite se necesita:

- $T_i(t)$: temperatura de entrada como función del tiempo
- $T(0,Z)$: perfil de la temperatura inicial en el horno
- $T_m(0,Z)$: perfil de la temperatura inicial de la pared del tubo
- $T_R(0)$: temperatura inicial del fogón
- $T_T(0)$: señal inicial del transmisor

Las variables de entrada al modelo son, además de $T_i(t)$:
- $F(t)$: flujo del fluido que se procesa
- $H_F(t)$: contenido calorífico del combustible
- $T^{sp}(t)$: punto de control del controlador de temperatura

Ahora se estudiarán los métodos para resolver las ecuaciones del modelo, debido a que se trata de ecuaciones diferenciales parciales.

## 9-4. SOLUCIÓN DE ECUACIONES DIFERENCIALES PARCIALES

A pesar de que existen paquetes de programas con los que se pueden manejar las ecuaciones diferenciales parciales directamente (ver sección 9-6), una manera común de trabajar con ellas es discretizar las variables de posición, de manera que cada ecuación diferencial parcial se convierte en varias ecuaciones diferenciales ordinarias. La ventaja de este procedimiento es que da por resultado un modelo que se puede resolver con programas estándar para ecuaciones diferenciales ordinarias. El procedimiento se demostrará mediante la discretización de las ecuaciones del modelo del horno.

El primer paso consiste en dividir la longitud del tubo, $L$, en $N$ incrementos de longitud $\Delta Z$, donde:

$$\Delta Z = \frac{L}{N}$$

Para simplificar esta presentación, se supondrá que los incrementos son de longitud uniforme, aunque no es forzoso que lo sean.

En la figura 9-7 aparece una sección del tubo en la que se muestran dos incrementos; en este modelo del horno la única derivada respecto a $Z$ que se debe discretizar aparece en la ecuación (9-42). Se tienen tres opciones para hacer la aproximación de la diferencia finita de la derivada en el punto $j$:

**Diferencia hacia adelante**
$$\frac{\partial T}{\partial Z}\bigg|_j \approx \frac{T_{j+1} - T_j}{\Delta Z} \quad (9-51)$$

**Diferencia hacia atrás**
$$\frac{\partial T}{\partial Z}\bigg|_j \approx \frac{T_j - T_{j-1}}{\Delta Z} \quad (9-52)$$

**Diferencia central**
$$\frac{\partial T}{\partial Z}\bigg|_j \approx \frac{T_{j+1} - T_{j-1}}{2\Delta Z} \quad (9-53)$$

De éstas, la diferencia central es la más exacta en términos de error de truncamiento de la expansión de la serie de Taylor de la función $T(Z)$, por lo tanto, primero se probará ésta y se substituirá en la ecuación (9-42):

$$\rho C_v\frac{dT_j}{dt} = -\frac{FC_p}{A}\cdot\frac{T_{j+1} - T_{j-1}}{2\Delta Z} + \frac{\pi D_i}{A}h_i(T_{m_j} - T_j) \quad (9-54)$$

donde:
- $T_j$ es la temperatura del fluido en la interfaz entre el incremento $j$ y el $(j+1)$, K.

En la ecuación (9-54) se tiene una dificultad básica con su capacidad para modelar el fenómeno físico de la transferencia de calor en el horno. Para comprender esta dificultad se debe tener en cuenta que, con el primer término del lado derecho de la ecuación (9-54), se representa la transferencia de calor por convección dentro del incremento de tubo del horno; sin embargo, en el horno real la propagación de la variación de temperatura por convección puede ocurrir únicamente de izquierda a derecha, es decir, en la dirección del flujo. Éste no es el caso en la ecuación (9-54), ya que la temperatura hacia adelante $T_{j+1}$ tiene un efecto sobre la temperatura anterior (upstream) $T_j$ a través del término de convección. Es fácil demostrar que la aproximación de diferencia hacia adelante, ecuación (9-51), también da por resultado un modelo irreal, con lo cual sólo queda la aproximación de diferencia hacia atrás como la única con que se obtiene un modelo físicamente correcto. De substituir la ecuación (9-52) en la (9-42), se obtiene:

$$\rho C_v\frac{dT_j}{dt} = -\frac{FC_p}{A}\cdot\frac{T_j - T_{j-1}}{\Delta Z} + \frac{\pi D_i}{A}h_i(T_{m_j} - T_j) \quad (9-55)$$

La ecuación (9-55) no sólo es una representación más correcta de la propagación de las variaciones de temperatura por convección, sino que también es más estable numéricamente, debido a que el término de convección se suma a la autorregulación de temperatura en el término de transferencia de calor; en otras palabras, con un incremento de $T_j$ se provoca un decremento en la tasa de cambio, $\frac{dT_j}{dt}$, el cual es mayor cuando se calcula con la ecuación (9-55) que cuando se calcula con la ecuación (9-54). Al comparar la ecuación (9-55) con la (9-41), se puede observar que la primera se obtiene directamente al realizar el balance de energía en el incremento $j$ de la longitud del tubo, si se supone que la temperatura es uniforme a lo largo del incremento.

La discretización del modelo del horno se completa al escribir las ecuaciones (9-45) y (9-46) de la manera siguiente:

$$\rho_mC_m\frac{dT_{m_j}}{dt} = \frac{4D_o\epsilon\sigma(T_R^4 - T_{m_j}^4)}{D_o^2 - D_i^2} - \frac{4D_ih_i(T_{m_j} - T_j)}{D_o^2 - D_i^2} \quad (9-56)$$

$$M_RC_R\frac{dT_R}{dt} = F_HH_F\eta_F - \sum_{j=1}^{N}\pi D_o\Delta Z\epsilon\sigma(T_R^4 - T_{m_j}^4) \quad (9-57)$$

donde $T_{m_j}$ es la temperatura de la pared del tubo en la interfaz entre el incremento $j$ y el $(j+1)$. En la ecuación (9-57), la suma de los términos de radiación de calor se aproxima a la integral de la ecuación (9-46).

Si se considera la transferencia de calor mediante la conducción a lo largo del tubo, se obtienen términos con segundas derivadas parciales respecto a $Z$ en las ecuaciones (9-42) y (9-45); en este caso, la aproximación de diferencia central es físicamente correcta para estas derivadas, ya que las variaciones de temperatura se propagan en ambas direcciones mediante los términos de conducción.

En resumen, un modelo de parámetro distribuido se puede convertir en un sistema de ecuaciones diferenciales ordinarias de primer orden mediante la discretización adecuada de las derivadas espaciales. Cada una de las ecuaciones diferenciales parciales originales se convierte mediante este procedimiento en varias ecuaciones diferenciales ordinarias, en las cuales la única variable independiente es el tiempo.

## 9-5. SIMULACIÓN POR COMPUTADORA DE LOS MODELOS DE PROCESOS DINÁMICOS

Una vez que se obtienen las ecuaciones del modelo, el siguiente paso en la simulación de un sistema físico es la solución de las ecuaciones. Cuando se utiliza una computadora digital para resolver las ecuaciones, se pueden aplicar tres métodos generales para programar las ecuaciones del modelo:

1. Se utiliza algún método simple de integración numérica para resolver las ecuaciones.
2. Se utiliza un paquete de subrutinas de propósito general para resolver ecuaciones diferenciales.
3. Se utiliza un lenguaje de simulación para simular sistemas continuos.

Con el fin de proporcionar al estudiante una herramienta para resolver modelos simples sin necesidad de aprender un nuevo paquete o lenguaje de programación, aquí se presenta el primero de los métodos mencionados. Los otros dos métodos son recomendables para la solución de modelos más complejos por parte de estudiantes de cursos avanzados y de profesionales activos en la industria. La utilización de computadoras analógicas para simular procesos no se aborda, ya que para un tratamiento adecuado se requiere más espacio del que se le puede dedicar en este libro, sin embargo, se recomienda a los instructores utilizar simulaciones analógicas preprogramadas en las demostraciones de clase y tareas.

Como se vio en las secciones precedentes, el modelo dinámico de proceso, aun aquel de los sistemas distribuidos, se puede transformar en un sistema de ecuaciones diferenciales ordinarias de primer orden y ecuaciones algebraicas auxiliares. En general, las ecuaciones diferenciales se pueden escribir en la siguiente forma:

$$\frac{dx_i}{dt} = f_i(x_1, x_2, \ldots, x_n, t) \quad \text{para } i = 1, 2, \ldots, n \quad (9-58)$$

donde:
- $x_i$ son las variables de estado del modelo, por ejemplo, temperaturas, composiciones
- $f_i$ son las funciones derivadas que resultan de la solución de las ecuaciones del modelo por medio de derivadas.
- $n$ es la cantidad de ecuaciones diferenciales

En todos los métodos generales para resolver modelos dinámicos, se supone que las ecuaciones del modelo son de la forma de la ecuación (9-58). Para resolver estas ecuaciones se deben conocer los valores iniciales de todas las variables de estado, es decir, $x_i(t_0)$, donde $t_0$ es el tiempo inicial; a pesar de que no se indica explícitamente en la ecuación (9-58), también se necesitan las entradas o funciones de forzamiento que provocan cambios en las variables del modelo. Cuando las funciones derivadas, $f_i$, son muy complejas, frecuentemente es conveniente expresarlas como varias ecuaciones algebraicas más simples, en cuyo caso se genera una variable auxiliar por cada ecuación.

### Ejemplo: Simulación de un tanque de reacción con agitación continua

Para reafirmar los conceptos, se estudiará el modelo relativamente simple de un tanque de reacción con agitación continua (TRAC). En la figura 9-8 se presenta un croquis del reactor con casquillo. Si se supone que el reactor y el casquillo están combinados perfectamente, que los volúmenes y las propiedades físicas son constantes y que las pérdidas de calor se desprecian, las ecuaciones del modelo son:

**Balance de masa del reactivo A**
$$V\frac{dC_A}{dt} = F(C_{A_i} - C_A) - VkC_A^2 \quad (9-59)$$

**Balance de energía en el contenido del reactor**
$$V\rho C_p\frac{dT}{dt} = F\rho C_p(T_i - T) - V(\Delta H_r)kC_A^2 - UA(T - T_c) \quad (9-60)$$

**Balance de energía en el casquillo**
$$V_c\rho_cC_{p_c}\frac{dT_c}{dt} = UA(T - T_c) - F_c\rho_cC_{p_c}(T_c - T_{c_i}) \quad (9-61)$$

**Coeficiente de razón de reacción**
$$k = k_0e^{-E/RT} \quad (9-62)$$

**Retardo en el sensor de temperatura (TT21)**
$$\tau_T\frac{dT_m}{dt} = T - T_m \quad (9-63)$$

**Controlador proporcional-integral con retroalimentación (TRC21)**
$$m = K_c\left(\frac{T^{sp} - T_m}{\Delta T_T}\right) + \frac{K_c}{\tau_I}\int_0^t\left(\frac{T^{sp} - T_m}{\Delta T_T}\right)dt + y \quad (9-64)$$

$$\frac{dy}{dt} = \frac{m - y}{\tau_I} \quad (9-65)$$

**Límites de la señal de salida del controlador**
$$0 \leq m \leq 1 \quad (9-66)$$

**Válvula de control de porcentaje igual (aire para cerrar)**
$$F_c = F_{c,max}\alpha^{m-1} \quad (9-67)$$

donde:
- $C_A$ es la concentración de reactivo en el reactor, kgmol/m³
- $C_{A_i}$ es la concentración del reactivo en la alimentación, kgmol/m³
- $T$ es la temperatura en el reactor, °C
- $T_i$ es la temperatura de alimentación, °C
- $T_c$ es la temperatura del casquillo, °C
- $T_{c_i}$ es la temperatura de entrada del enfriador, °C
- $b$ es la señal del transmisor en una escala de 0 a 1
- $F$ es la razón de alimentación, m³/s
- $V$ es el volumen del reactor, m³
- $k$ es el coeficiente de razón de reacción, m³/kgmol-s
- $\Delta H_R$ es el calor de la reacción; se supone constante, J/kgmol
- $\rho$ es la densidad del contenido del reactor, kgmol/m³
- $C_p$ es la capacidad calorífica de los reactivos, J/kgmol-°C
- $U$ es el coeficiente de transferencia total de calor, J/s-m²-°C
- $A$ es el área de transferencia de calor, m²
- $V_c$ es el volumen del casquillo, m³
- $\rho_c$ es la densidad del enfriador, kg/m³
- $C_{p_c}$ es el calor específico del enfriador, J/kg-°C
- $\Delta T_T$ es el rango calibrado del transmisor, °C
- $F_c$ es la razón de flujo del enfriador, m³/s
- $T_M$ es el límite inferior del rango del transmisor, °C
- $\tau_T$ es la constante de tiempo del sensor de temperatura, s
- $\tau_I$ es el tiempo de integración del controlador, s
- $y$ es la variable de retroalimentación de reajuste del controlador
- $m$ es la señal de salida del controlador en una escala de 0 a 1
- $K_c$ es la ganancia del controlador; sin dimensiones
- $F_{c,max}$ es el flujo máximo a través de la válvula de control, m³/s
- $\alpha$ es el parámetro de ajuste en rango de la válvula
- $k_0$ es el parámetro de frecuencia de Arrhenius, m³/s-kgmol
- $E$ es la energía de activación de la reacción, J/kgmol
- $R$ es la constante de la ley de los gases ideales, 8314.39 J/kgmol-K

En este modelo del reactor y de su controlador de temperatura, las variables de estado son $C_A$, $T$, $T_c$, $b$ e $y$; las variables auxiliares $r_A$, $m$ y $F_c$ se pueden calcular junto con las funciones de derivación, a partir de los valores de las variables de estado en cualquier punto del tiempo. Las variables de entrada al modelo son $F$, $C_{A_i}$, $T_i$, $T_{c_i}$ y $T^{sp}$. Un punto que vale la pena hacer notar es que, para el análisis del comportamiento del controlador, algunas de las variables auxiliares son más importantes que algunas de las variables de estado; por ejemplo, la salida del controlador, $m$, o la razón de enfriador, $F_c$, son de mayor interés que la temperatura del casquillo, $T_c$, y la de retroalimentación, $y$.

El modelo del controlador proporcional-integral (PI) es la implementación "retroalimentación de reajuste" de la acción de integración; para un estudio más detallado se debe consultar la sección 6.5 y el ejemplo 9-4. La señal $b$ del transmisor y la señal $m$ de salida del controlador son normalizadas, es decir, se expresan como fracciones de rango, lo cual hace que el modelo sea válido para instrumentación electrónica, digital y neumática. Se notará que en la ecuación (9-65) se debe normalizar el punto de control del controlador mediante la misma fórmula que se utilizó para normalizar la temperatura en la ecuación del transmisor, ecuación (9-63).

Para hacer la simulación del reactor se deben determinar los parámetros del modelo y las condiciones iniciales. En la práctica, los parámetros del modelo se obtienen a partir de las especificaciones del equipo y de los diagramas de tubería e instrumentación. A continuación se trabaja con los siguientes parámetros del reactor:

- $V = 7.08$ m³
- $\rho = 19.2$ kgmol/m³
- $C_p = 1.815 \times 10^5$ J/kgmol-°C
- $A = 5.40$ m²
- $\rho_c = 1000$ kg/m³
- $k_0 = 0.0744$ m³/s-kgmol
- $T_M = 20$ °C
- $\Delta T_T = 50$ °C
- $\Delta H_R = -9.86 \times 10^7$ J/kgmol
- $U = 3550$ J/s-m²-°C
- $V_c = 1.82$ m³
- $C_{p_c} = 4184$ J/kg-°C
- $E = 1.182 \times 10^7$ J/kgmol
- $F = 0.020$ m³/s
- $T_M = 80°C$
- $\Delta T_T = 20°C$

Si el propósito de la simulación es ajustar el controlador a las condiciones de operación de diseño, las condiciones iniciales se toman en el punto de operación de diseño. Un requisito importante es que con las condiciones iniciales se deben satisfacer las ecuaciones del modelo en estado estacionario; esto es, todas las derivadas que se calculan con base en las ecuaciones del modelo deben ser exactamente cero en los valores iniciales de las variables de estado. Puesto que se tiene una ecuación de modelo para cada variable de estado y auxiliar, el número de especificaciones de diseño no debe exceder el de variables de entrada. En este ejemplo, las variables de entrada y las condiciones de diseño son las siguientes:

- $F = 7.5 \times 10^{-3}$ m³/s
- $C_{A_i} = 2.88$ kgmol/m³
- $T_i = 66°C$
- $T_{c_i} = 27°C$
- $T^{sp} = 88°C$

Ahora se pueden utilizar las ecuaciones del modelo para calcular los demás valores iniciales y variables auxiliares. El orden de los cálculos es el que se muestra en el cuadro de la página siguiente.

Se observará que la única forma de satisfacer las ecuaciones (9-63), (9-64) y (9-65) en estado estacionario es que la temperatura del reactor se mantenga en el punto de control, debido a que el controlador tiene acción de integración.

| De la ecuación número | Calcúlese |
|-----------------------|-----------|
| (9-65) | $b = \frac{T^{sp} - T_M}{\Delta T_T} = 0.40$ |
| (9-63) | $T = b\Delta T_T + T_M = 88.0°C$ |
| (9-62) | $k = 1.451 \times 10^{-3}$ m³/kgmol-s |
| (9-59) | $C_A = 1.133$ kgmol/m³ |
| (9-60) | $T_c = 50.5°C$ |
| (9-61) | $F_c = 7.392 \times 10^{-3}$ m³/s |
| (9-67) | $m = 0.2544$ (sin dimensiones) |
| (9-64) | $y = 0.2544$ (sin dimensiones) |

Una vez que se tienen las ecuaciones del modelo, el valor de los parámetros y las condiciones iniciales, se pueden programar las ecuaciones en la computadora.

### Integración numérica mediante el método de Euler

El método numérico más simple para resolver ecuaciones diferenciales ordinarias es el método de Euler, el cual consiste en suponer que las funciones derivadas son constantes a lo largo de todo el intervalo de integración $\Delta t$. El planteamiento de un programa para resolver el sistema de ecuaciones de la forma de la ecuación (9-58) mediante el método de Euler es el siguiente:

1. **Inicialización:** se hace $t = t_0$ y $x_i = x_i(t_0)$ para $i = 1, 2, \ldots, n$
2. Con las ecuaciones del modelo se calculan todas las funciones derivadas, $f_i$:
$$f_i = f_i(x_1, x_2, \ldots, x_n, t) \quad \text{para } i = 1, 2, \ldots, n \quad (9-68)$$
3. Los valores de las variables de estado se calculan después de un incremento de tiempo $\Delta t$ (fórmula de Euler). Para $i = 1, 2, \ldots, n$ se calcula:
$$x_i|_{t+\Delta t} = x_i|_t + f_i\Delta t \quad (9-69)$$
Sea $t = t + \Delta t \quad (9-70)$
4. Si $t$ es menor que $t_{max}$, se repite a partir del paso 2; de otro modo, se termina la corrida.

Una característica esencial de este programa es que todas las funciones derivadas se calculan en el paso 2, antes de incrementar cualquiera de las variables de estado en el paso 3, con lo cual se garantiza que todas las funciones derivadas corresponden al estado del sistema en el tiempo $t$, como debe ser.

Antes de correr el programa que se planteó arriba, se debe elegir un tiempo inicial $t_0$, un tiempo final $t_{max}$ y un intervalo de integración $\Delta t$. También se debe decidir con qué frecuencia se imprimirán las variables que son de interés en la simulación.

### Duración de las corridas de simulación

La duración en "tiempo de problemas" de cada corrida de simulación es $t_{max} - t_0$; las unidades de esta cantidad las determinan las unidades de la razón y las constantes de tiempo de las ecuaciones del modelo; por ejemplo, en las ecuaciones del modelo del reactor todas las razones son por segundo y todas las constantes de tiempo están dadas en segundos, por lo tanto, las unidades de tiempo son segundos.

En la mayoría de las simulaciones el tiempo inicial $t_0$ se puede fijar a cero, con excepción de los casos muy raros donde los parámetros del modelo son funciones del tiempo; por ejemplo, a causa de viciado de las superficies de transferencia de calor y otras circunstancias parecidas.

Una vez que se fija el valor de $t_0$, la duración de cada corrida de simulación se determina con $t_{max}$; dicha duración debe ser lo suficientemente larga como para que se complete la respuesta del sistema, pero no tanto como para que la respuesta se comprima en una fracción muy pequeña de la duración total de la corrida. Por tanto, el valor correcto de $t_{max}$ depende de la velocidad de respuesta del proceso que se simula; para procesos rápidos se necesita que $t_{max}$ sea de unos cuantos segundos; en cambio, para procesos lentos puede ser del orden de horas. En la figura 9-9 se muestran los tiempos de respuesta para corridas muy largas (comprimido), muy cortas (incompleto) y el apropiado.

¿Con qué se determina la velocidad de respuesta del proceso? Estrictamente hablando, con el eigenvalor dominante, es decir, el recíproco de la constante de tiempo más larga del proceso, se controla el tiempo que se requiere para completar la respuesta. Desafortunadamente, el eigenvalor es difícil de determinar en modelos de procesos complejos no lineales como los que se desarrollaron anteriormente en este capítulo. Por otro lado, algunas veces es posible estimar la constante de tiempo más larga, ya sea con base en la familiaridad con procesos similares o en la intuición ingenieril; por ejemplo, para el reactor que se considera aquí, la constante de tiempo más larga es probablemente del orden de magnitud del tiempo de residencia del reactor, $V/F$, o alrededor de 1000 segundos. Una vez que se tiene la estimulación de la constante más larga, la duración de la corrida se puede fijar en aproximadamente cinco veces la constante de tiempo. Esta regla práctica se basa en el hecho de que, en un proceso de primer orden, la respuesta se completa en cinco constantes de tiempo; en procesos de orden superior se puede esperar que se tome más tiempo, y para los de circuito cerrado, un tiempo más corto. En muchos casos no se dispone de un método conveniente para estimar la duración de la corrida, la cual se debe elegir mediante ensayo y error; al seleccionar $t_{max}$, se debe recordar que:

> Sin importar el método utilizado para estimar la duración de las corridas de simulación, ésta se debe ajustar siempre con base en la observación de las respuestas que se obtienen en las primeras corridas.

### Elección del intervalo de integración

Con el intervalo de integración, $\Delta t$, se afecta la precisión de la integración numérica de las ecuaciones diferenciales y el tiempo de máquina que se requiere para realizar los cálculos. El efecto sobre el tiempo de máquina es simplemente que la cantidad de cálculos es inversamente proporcional al intervalo de integración; esto es, proporcional al número de "pasos" de integración, $N$:

$$N = \frac{t_{max} - t_0}{\Delta t} \quad (9-71)$$

Respecto a la precisión de la integración numérica, un concepto erróneo es que, mientras más corto es el intervalo de integración $\Delta t$, más precisa es la solución; aunque, como se verá a continuación, teóricamente es verdad que el error por truncamiento es mayor para un intervalo de integración mayor, en la práctica, debido a la precisión limitada de los cálculos en la computadora, existe un límite respecto a lo pequeño que puede ser el intervalo de integración; abajo de este límite, conforme decrece el intervalo de integración, aumenta el error de redondeo. El error de redondeo es aquel en el cual se incurre en los cálculos por computadora, debido a que se acarrea un número finito de dígitos significativos. A pesar de que el tamaño mínimo del intervalo de integración se puede reducir mediante la especificación de que los cálculos se realicen con "doble precisión", es decir, de que se duplique la cantidad de dígitos significativos que acarrea la computadora, pocas veces vale la pena desperdiciar el tiempo de máquina para hacer corridas con un intervalo de integración mucho más pequeño de lo que se requiere para el error por truncamiento. En otras palabras, se debe seleccionar un intervalo de integración cercano al máximo permitido por la precisión que se requiera en los cálculos de la integración numérica.

En un procedimiento de integración numérica, el error por truncamiento es aquel en que se incurre cuando las derivadas continuas se aproximan a valores discretos de la variable independiente. Por ejemplo, en el método de Euler se supone que los valores de las derivadas en el tiempo $t$ son una buena aproximación de las derivadas continuas desde $t$ hasta $(t + \Delta t)$, de donde resulta la ecuación (9-69), de la cual se puede pensar que es una expansión por series de Taylor de la función $x_i(t)$ "truncada" después del primer término de derivación. Puesto que la fórmula de Euler es más simple, de ella resulta un error por truncamiento más grande para un cierto intervalo de integración $\Delta t$. Como se mencionó anteriormente, el error por truncamiento se incrementa con el intervalo de integración $\Delta t$; si el intervalo de integración es suficientemente grande, la solución numérica se puede volver inestable, es decir, se producirá una respuesta inestable, aun para un proceso estable. Un riesgo que se relaciona con esto es que, al calcular una respuesta para un proceso inestable, el efecto acumulativo del error por truncamiento puede hacer que los resultados sean inútiles después de unos cuantos pasos de integración.

Cuando se elige la duración de las corridas de simulación, el intervalo de integración se debe ajustar con base en la precisión que se observa en las primeras corridas. Un procedimiento simple es correr el mismo caso con diferentes intervalos de integración y revisar que los resultados estén dentro de un error tolerable, es decir, con una cantidad aceptable de dígitos significativos, por ejemplo, cuatro o cinco. El intervalo más largo con el cual se obtengan resultados aceptables es el que se debe elegir.

Para el método de Euler y un modelo de proceso con buen comportamiento, una estimación de intervalo de integración correcta es aquella donde se requieren de 1000 a 5000 pasos para completar una corrida de simulación. Un modelo con buen comportamiento es aquel donde todos los eigenvalores (constantes de tiempo) tienen casi el mismo orden de magnitud; en cambio, un modelo rígido es aquel donde la razón del eigenvalor mayor al menor (o constantes de tiempo) es grande. La rigidez se tratará en una sección al final del capítulo.

### Despliegue de los resultados de la simulación

Los resultados de una simulación dinámica son generalmente las respuestas en tiempo de las variables del modelo. En una solución numérica, estas respuestas se calculan como los valores de las variables de estado y auxiliares de cada paso del procedimiento de integración numérica; dichos resultados se pueden desplegar en forma tabular o gráfica. La forma gráfica es más informativa para el estudio de la respuesta de los sistemas de control; se puede tener la presentación de gráficas de baja, media o alta resolución. Para las gráficas de baja resolución se requiere únicamente una impresora regular de caracteres con resolución de 6 a 10 puntos por pulgada; en las gráficas de resolución media se requiere una impresora de matriz de puntos o pantalla, con una resolución de casi 80 puntos por pulgada; para las gráficas de alta resolución se requiere un graficador digital especial o una terminal gráfica, con lo cual se obtiene una calidad comparable a la de los dibujos de ingeniería. Para la generación de gráficas por computadora, generalmente se requiere un paquete de subprogramas de trazado. En la figura 9-9 se presentan ejemplos de gráficas de alta resolución, mientras que en la figura 9-10 se muestra un ejemplo de una gráfica de baja resolución.

Cuando los resultados de la simulación se imprimen en forma tabular, no tiene sentido imprimir las variables a cada paso de integración, ya que así no sólo se desperdicia papel y los árboles que se utilizan para producirlo, sino que también se dificulta la lectura e interpretación de los resultados. La solución que se recomienda es imprimir las variables del modelo con intervalos de tiempo $\Delta t_P$, el intervalo de impresión; este intervalo debe ser un múltiplo del intervalo de integración $\Delta t$. El intervalo de impresión se debe elegir de tal manera que se imprima un total de casi 50 entradas para una corrida de simulación completa; en otras palabras:

$$\Delta t_P = \frac{t_{max} - t_0}{50} \quad (9-72)$$

Se elige el número 50 porque una hoja típica de computadora contiene aproximadamente 50 líneas; esta selección es arbitraria y se puede cambiar a 25 ó 100, según sea el grado de resolución que se requiera para la respuesta en tiempo.

Cuando se buscan errores en el programa de la computadora, generalmente se hace necesario imprimir las variables en cada paso de integración; en este caso, $\Delta t_P$ se debe hacer temporalmente igual a $\Delta t$, el intervalo de integración; se puede economizar papel si se hace $t_{max}$ igual a $50\Delta t$ para las corridas de detección de error.

### Muestra de resultados para el método de Euler

En la figura 9-11 se presenta el listado para el programa en FORTRAN con que se simula el tanque de reacción con agitación continua mediante el método de Euler. El intervalo de integración es de 0.25 segundos, la duración de la corrida de 2500 segundos y el intervalo de impresión de 50 segundos. En la figura 9-12 se presenta una tabla con los resultados de la respuesta del reactor a una subida de 2°C en el punto de control. Las gráficas de la figura 9-9 son para la misma corrida. Una ventaja obvia de la tabla sobre las gráficas es que se pueden desplegar más variables. Como se aprecia en la figura 9-9, cuando se analiza el desempeño del sistema de control, las variables importantes para la graficación son la controlada y la manipulada.

El diseño del programa que se lista en la figura 9-11 es para utilizarlo a través de una terminal de tiempo compartido; a esto se debe que se impriman mensajes en la terminal (unidad 6) para alertar al usuario. Los datos se introducen a través de la terminal (unidad 5) y los resultados se despliegan en la terminal y se imprimen en la impresora (unidad 4). El diseño de los demás programas que se listan en este capítulo es similar.

### Método de Euler modificado

El método más simple para programar en una computadora es el de Euler, pero también es el menos eficiente. Con el método de Euler modificado, el cual se basa en la regla trapezoidal de la integración numérica, se tiene una representación más precisa de las derivadas, es decir, un error por truncamiento menor para un cierto intervalo de integración. El planteamiento para el método de Euler modificado es el siguiente:

1. **Inicialización:** se hace $t = t_0$ y $x_i = x_i(t_0)$ para $i = 1, 2, \ldots, n$.
2. **Evaluación de las funciones derivadas:**
   a) Para $i = 1, 2, \ldots, n$, se calcula:
   $$f_i|_t = f_i(x_1, x_2, \ldots, x_n, t) \quad (9-73)$$
   b) Para $i = 1, 2, \ldots, n$, se calcula:
   $$x_i' = x_i|_t + f_i|_t\Delta t \quad (9-74)$$
3. Se calculan las variables de estado en $t + \Delta t$:
   Para $i = 1, 2, \ldots, n$, se calcula:
   $$f_i|_{t+\Delta t} = f_i(x_1', x_2', \ldots, x_n', t + \Delta t) \quad (9-75)$$
   $$x_i|_{t+\Delta t} = x_i|_t + \frac{1}{2}(f_i|_t + f_i|_{t+\Delta t})\Delta t \quad (9-76)$$
   Sea $t = t + \Delta t \quad (9-77)$
4. Si $t$ es menor o igual que $t_{max}$, se repite desde el paso 2; de otro modo, se termina la corrida.

En este procedimiento las funciones derivadas se deben evaluar dos veces para cada paso de integración: una en el tiempo $t$ y otra en el tiempo $(t + \Delta t)$. En la segunda evaluación las variables de estado se incrementan con los valores de las funciones derivadas de la primera evaluación. Finalmente, el incremento en la variable de estado se calcula a partir del promedio aritmético de las dos evaluaciones de las funciones derivadas. Puesto que la evaluación de las funciones derivadas es el paso de los cálculos que consume tiempo, con el método de Euler modificado se tienen dos veces más cálculos por paso de integración que con el método de Euler; la ventaja es que se reduce el error por truncamiento, lo cual permite incrementar el intervalo de integración a más de dos veces el valor que se requiere con el método de Euler y mantener la misma precisión. De aquí resultan menos evaluaciones totales de las funciones derivadas, ya que el número de pasos que resulta es menor de la mitad de los que se requieren con el método de Euler.

Ya que las mismas funciones derivadas se deben evaluar dos veces, es conveniente ubicar los cálculos de las funciones derivadas en una subrutina, la cual es invocada por el método de integración. Una vez que se hace esto, las ecuaciones del modelo se separan de la rutina de evaluación numérica, de manera que esta última se pueda cambiar sin afectar al subprograma que contiene las ecuaciones del modelo; de manera similar, los mismos subprogramas de integración numérica se pueden utilizar con diferentes subprogramas de ecuaciones de algún modelo.

La subrutina para la integración de Euler modificada se muestra en la figura 9-13, con ella se llama a la subrutina DERIV dos veces por paso de integración, una vez por cada evaluación de las funciones derivadas. En la figura 9-14 se lista el programa principal, y la subrutina MODEL se lista en la figura 9-15. La subrutina MODEL consta de tres secciones diferentes, cada una con su propio punto de entrada y retorno; la primera sección se invoca desde el programa principal con el nombre de "MODEL"; en esta sección se leen los parámetros del modelo y se calculan y fijan las condiciones iniciales y el número de ecuaciones diferenciales que se integrarán, asimismo se calculan los términos constantes de las ecuaciones del modelo. Las condiciones iniciales se pasan al programa principal como argumentos. En el programa principal se fija el resto de los parámetros de la corrida y se llama a la subrutina INT para integrar numéricamente las ecuaciones diferenciales.

Desde la subrutina INT se llama a la segunda sección de la subrutina MODEL, bajo el nombre de "DERIV"; el propósito de ésta es evaluar las funciones derivadas a partir de las ecuaciones del modelo cada vez que se le llama desde la subrutina de integración con un nuevo grupo de valores de variable de estado. Éste es el planteamiento para el segundo paso del procedimiento de Euler modificado. Se observará que, a pesar de que únicamente se llama a la subrutina MODEL una vez por corrida en el primer punto de entrada, a DERIV se le llama dos veces por paso de integración durante la corrida; en otras palabras, cuando se llama a DERIV, la ejecución comienza en el enunciado "ENTRY DERIV..." y no al principio de la subrutina MODEL.

A la tercera sección de la subrutina MODEL se le llama desde la subrutina INT con el nombre de "OUTPUT"; el objetivo de esta sección es imprimir las entradas en la tabla de tiempo de respuesta. Desde la subrutina de integración INT se llama a OUTPUT con intervalos de tiempo $\Delta t_P$ (DPRNT), después de que se llama por primera vez a DERIV durante el paso de integración apropiado, porque únicamente en este punto de cada paso de integración es donde las variables de estado y las auxiliares tienen los valores que corresponden al estado real del sistema, ya que a las variables de estado se les asignan valores aproximados para la segunda evaluación; ésta es también la razón por la cual se debe llamar a DERIV antes que a OUTPUT al completar la corrida (en la subrutina INT) para imprimir las condiciones finales.

En esta estructura de programa es de notar que el programa principal y las subrutinas de integración se pueden utilizar con cualquier subrutina de modelo. Todos los enunciados que se especifican para el modelo están aislados en la subrutina MODEL. Al utilizar puntos de entrada múltiples en la subrutina, se pueden transferir los valores de los parámetros y las variables de una sección de la subrutina a otra sin necesidad de utilizar enunciados COMMON o argumentos adicionales.

Para el ejemplo del tanque de reacción con agitación continua se requiere un intervalo de integración de 2.5 segundos para cubrir la precisión de cuatro dígitos significativos en los resultados del método de Euler. Este valor, comparado con los 0.25 segundos que se requieren para el método de Euler, significa que el número total de evaluaciones de la función que se requiere para el método de Euler modificado es la quinta parte del que se requiere para el método de Euler simple.

### Método Runge-Kutta-Simpson

Para la Runge-Kutta de cuarto orden se requieren cuatro evaluaciones de las funciones derivadas por paso de integración. El planteamiento de un programa donde se utiliza el método Runge-Kutta-Simpson es el siguiente:

1. **Inicialización:** se fija $t = t_0$ y $x_i = x_i(t_0)$ para $i = 1, 2, \ldots, n$.
2. **Se evalúan las funciones derivadas:**
   a) Para $i = 1, 2, \ldots, n$, se calcula:
   $$k_{1,i} = \Delta t f_i(x_1, x_2, \ldots, x_n, t) \quad (9-77)$$
   b) Para $i = 1, 2, \ldots, n$, se calcula:
   $$k_{2,i} = \Delta t f_i(x_1 + \frac{1}{2}k_{1,1}, \ldots, x_n + \frac{1}{2}k_{1,n}, t + \frac{1}{2}\Delta t) \quad (9-78)$$
   c) Para $i = 1, 2, \ldots, n$, se calcula:
   $$k_{3,i} = \Delta t f_i(x_1 + \frac{1}{2}k_{2,1}, \ldots, x_n + \frac{1}{2}k_{2,n}, t + \frac{1}{2}\Delta t) \quad (9-79)$$
   d) Para $i = 1, 2, \ldots, n$, se calcula:
   $$k_{4,i} = \Delta t f_i(x_1 + k_{3,1}, \ldots, x_n + k_{3,n}, t + \Delta t) \quad (9-80)$$
3. **Se incrementan las variables de estado:**
   Para $i = 1, 2, \ldots, n$, sea:
   $$x_i|_{t+\Delta t} = x_i|_t + \frac{1}{6}(k_{1,i} + 2k_{2,i} + 2k_{3,i} + k_{4,i}) \quad (9-81)$$
   sea $t = t + \Delta t \quad (9-82)$
4. Si $t$ es menor o igual a $t_{max}$, se repite a partir del paso 2; de otra manera, se finaliza la corrida.

Se notará que el incremento final de las variables de estado es un promedio de las cuatro evaluaciones de las funciones derivadas, una en $t$, dos en $(t + 1/2\Delta t)$ y una en $(t + \Delta t)$. En la figura 9-16 se lista una subrutina para el método Runge-Kutta-Simpson, la cual se puede substituir por la subrutina para Euler modificada de la figura 9-13 sin afectar el programa principal o la subrutina MODEL de las figuras 9-14 y 9-15. Esta modalidad es bastante útil, ya que se ahorra considerable tiempo de reprogramación y el esfuerzo asociado para encontrar y corregir errores de programación.

En el Runge-Kutta de cuarto orden se requiere el doble de evaluaciones de derivadas por paso de integración, en comparación con el de Euler modificado, y, en consecuencia, para economizar tiempo de máquina debe ser posible hacer el intervalo de integración $\Delta t$ algo más del doble del que se necesita para el Euler modificado, a fin de lograr la misma precisión en los resultados. En el caso del tanque de reacción con agitación continua, para el método de Runge-Kutta-Simpson se requiere un intervalo de integración de 25 segundos, del cual resulta un ahorro de 80% en el total de evaluaciones de derivadas respecto a la solución mediante Euler modificado.

### Resumen

Los estudiantes pueden utilizar los métodos numéricos que se presentaron en esta sección para estudiar los sistemas de control de procesos sencillos. Cuando se simulan procesos más complejos probablemente es conveniente utilizar subrutinas más elaboradas, de las cuales se dispone generalmente en la biblioteca de software de la mayoría de las instalaciones de cómputo grandes; en la siguiente sección se describen algunas de éstas.

## 9-6. LENGUAJES Y SUBRUTINAS ESPECIALES PARA SIMULACIÓN

Se dispone de varios lenguajes de simulación y subrutinas de integración numérica de propósito general, los cuales se pueden utilizar para simular el comportamiento dinámico de los sistemas de control de proceso. Con estas subrutinas se substituyen las de Euler modificado y Runge-Kutta-Simpson que se presentaron en la sección precedente. Las principales ventajas que se tienen con éstas son las siguientes:

1. Ajuste automático del intervalo de integración para cumplir con una tolerancia específica del error por truncamiento.
2. Métodos numéricos más eficientes que el Runge-Kutta-Simpson de cuarto orden que se presentó en la sección precedente.
3. En algunos casos se dispone de métodos para manejar eficientemente sistemas rígidos de ecuaciones diferenciales (ver la sección 9-8 para una exposición acerca de la rigidez).

El diseño de estas subrutinas de propósito general es similar al de las subrutinas para Euler modificado y Runge-Kutta-Simpson que se presentaron en la sección anterior; en un programa principal se fijan los parámetros de la corrida y las condiciones iniciales y se llama a la subrutina de integración, la cual a su vez llama a una subrutina de modelo para evaluar las funciones derivadas. Generalmente, el usuario debe ordenar una impresión intermedia de los resultados desde el programa principal -mediante retornos iterativos desde la rutina de integración- o desde la subrutina de modelo.

En la tabla 9-1 se presenta una lista de las subrutinas de integración numérica de las que se dispone comúnmente; para utilizarlos se debe consultar el manual de usuario de cada paquete particular del que forman parte.

```json
{
  "type": "table",
  "id": "table-09-01",
  "page": 587,
  "title": "Tabla 9-1. Subrutinas para resolver ecuaciones diferenciales ordinarias",
  "headers": ["Nombre", "Características"],
  "rows": [
    ["DVERKᵃ", "Ajuste automático del intervalo de integración, método Runge Kutta-Verner"],
    ["LSODEᵇ", "Ajuste automático del intervalo de integración, Algoritmo implícito para sistemas rígidos, Se utiliza el método de Gear"],
    ["LSODIᵇ", "Similar al LSODE, con capacidad adicional para manejar ecuaciones algebraicas implícitas y, a la vez, las ecuaciones diferenciales."],
    ["PDECOLᵇ", "Igual al LSODE, pero para ecuaciones diferenciales parciales con dos variables independientes."]
  ],
  "notes": "ᵃ IMSL, Inc., Edificio de la NBC 60-piso, 7500 Bellair Boulevard, Houston, Tex. ᵇ Hindmarsh, Alan C., Mathematics and Statistics Section, L-300 Lawrence Livermore Laboratories, Livermore, Calif.",
  "source": "Smith & Corripio, Control Automático de Procesos, Tabla 9-1"
}
```

También se desarrollaron varios lenguajes de simulación de propósito general para sistemas cuyos modelos se expresan con ecuaciones diferenciales. Algunos de estos programas se diseñaron para simular la respuesta dinámica de procesos químicos y sus sistemas de control. Además de las ventajas que se enlistaron para las subrutinas de integración, con los lenguajes de simulación se tienen las siguientes:

1. Un conjunto de subprogramas modulares para hacer el modelo de instrumentos específicos y elementos de respuesta dinámica; por ejemplo, interruptores, selectores, tiempo muerto y retardos de primer orden.
2. Subprogramas para resolver de manera iterativa las ecuaciones algebraicas del modelo.
3. Características para facilitar el control de la corrida y para la impresión y graficación de los resultados de la simulación.

En la tabla 9-2 aparece una lista de los lenguajes de simulación de que se dispone comúnmente. Como se puede apreciar en las características, el DSS/2 se diseñó para manejar sistemas de ecuaciones diferenciales parciales; varios programas se orientan a procesos. En los manuales de estos programas aparecen las instrucciones específicas para su utilización.

```json
{
  "type": "table",
  "id": "table-09-02",
  "page": 588,
  "title": "Tabla 9-2. Lenguajes de simulación",
  "headers": ["Lenguaje", "Características"],
  "rows": [
    ["CSMPᵃ", "Precompilador FORTRAN, Módulos para bloques dinámicos y lógicos, Capacidad interconstruida para graficación"],
    ["ACSLᵇ", "Mismas que el CSMP"],
    ["DSS/2ᶜ", "Se pueden resolver ecuaciones diferenciales parciales y ordinarias"],
    ["DYNSYLᵈ", "Orientado al proceso con módulos de control y proceso, Operación interactiva en tiempo real, Salida gráfica, Algoritmo de integración implícito para sistemas rígidos"],
    ["DYFLO2ᵉ", "Orientado al proceso con módulos de proceso y control"],
    ["EPRI-MMSᶠ", "Orientado al proceso con módulos de planta de fuerza y control."]
  ],
  "notes": "ᵃ\"Continuous System Modeling Program,\" IBM Corporation, 1133 Westchester Avenue, White Plains, N.Y. ᵇ\"Advanced Continuous Simulation Language,\" Mitchell and Gauthier, Associates, 1337 Old Marlboro Road, Concord, Mass. ᶜ\"Distributed System Simulator-Version 2,\" W.E. Schiesser, Lehigh University, Bethlehem, Pa. ᵈ\"DYNSYL: A General Purpose Dynamic Simulator for Chemical Processes,\" Chemical Engineering Division, Lawrence Livermore Laboratory, Livermore, Calif. ᵉ\"DYFLO2,\" R.G.E. Franks, E. I. duPont de Nemours and Company, Wilmington, Del. ᶠ\"EPRI-Modular Modeling System,\" Electric Power Research Institute, P.O. Box 10412, Palo Alto, Calif.",
  "source": "Smith & Corripio, Control Automático de Procesos, Tabla 9-2"
}
```

## 9-7. EJEMPLOS DE SIMULACIÓN DE CONTROL

Normalmente, al simular sistemas de control de proceso se encuentran varios elementos dinámicos o módulos que son comunes a muchos sistemas; ejemplos de estos módulos son los retardos de primer y segundo orden, el tiempo muerto, los controladores proporcional-integral-derivativo, compensadores dinámicos de adelanto/retardo, entre otros. En esta sección se presentarán varios ejemplos de tales modelos y después se conjuntarán para simular un circuito de control por retroalimentación.

**Ejemplo 9-1(a). Simulación de los retardos de primer y segundo orden.**

**Retardo de primer orden:**
$$\frac{Y(s)}{X(s)} = \frac{K}{\tau s + 1}$$

donde:
- $Y(s)$ es la salida
- $X(s)$ es la entrada
- $K$ es la ganancia
- $\tau$ es la constante de tiempo

Para simular la función de transferencia, primero se despejan las fracciones:
$$\tau sY(s) + Y(s) = KX(s)$$

Se supone que las condiciones iniciales son cero y se utiliza el teorema de la diferenciación real de la transformada de Laplace, ecuación (2-3), para escribir las ecuaciones en términos de las variables de tiempo:
$$\tau\frac{dy(t)}{dt} + y(t) = Kx(t)$$

Finalmente, se resuelve para la derivada más alta:
$$\frac{dy(t)}{dt} = \frac{1}{\tau}[Kx(t) - y(t)]$$

La forma en que queda la ecuación es la apropiada para incorporarla a un programa de simulación. La variable $x(t)$ es la entrada al retardo de primer orden.

**Ejemplo 9-1(b). Retardo de segundo orden.**
$$\frac{Y(s)}{X(s)} = \frac{K}{\tau^2s^2 + 2\xi\tau s + 1}$$

$\tau$ es la constante de tiempo característica
$\xi$ es la razón de amortiguamiento

**Solución.** Se despejan las fracciones:
$$\tau^2s^2Y(s) + 2\xi\tau sY(s) + Y(s) = KX(s)$$

Se suponen condiciones iniciales cero y se invierte al dominio del tiempo:
$$\tau^2\frac{d^2y(t)}{dt^2} + 2\xi\tau\frac{dy(t)}{dt} + y(t) = Kx(t)$$

Se resuelve para la derivada más alta:
$$\frac{d^2y(t)}{dt^2} = \frac{1}{\tau^2}[Kx(t) - 2\xi\tau\frac{dy(t)}{dt} - y(t)]$$

Ahora se debe transformar esta ecuación en dos ecuaciones diferenciales de primer orden, mediante el siguiente procedimiento:

Sea:
$$y_1(t) = \frac{dy(t)}{dt}$$

Entonces:
$$\frac{dy_1(t)}{dt} = \frac{d^2y(t)}{dt^2}$$

De la combinación de estas tres últimas ecuaciones resultan las siguientes ecuaciones diferenciales de primer orden, las cuales ya se pueden introducir a un programa de simulación:
$$\frac{dy(t)}{dt} = y_1(t)$$
$$\frac{dy_1(t)}{dt} = \frac{1}{\tau^2}[Kx(t) - 2\xi\tau y_1(t) - y(t)]$$

La variable $x(t)$ es la variable de entrada, $y_1(t)$ es una variable intermedia, y $y(t)$ es la salida del retardo de segundo orden.

**Ejemplo 9-1(c). Dos retardos de segundo orden en serie.**
$$\frac{Y(s)}{X(s)} = \frac{K}{(\tau_1s + 1)(\tau_2s + 1)}$$

donde $\tau_1$ y $\tau_2$ son las constantes de tiempo.

Esta función de transferencia es equivalente a la de la parte (b), cuando la razón de amortiguamiento $\xi$ es igual o mayor a uno. Las relaciones entre estos dos grupos de parámetros son:
$$\tau = \sqrt{\tau_1\tau_2}$$
$$\xi = \frac{\tau_1 + \tau_2}{2\sqrt{\tau_1\tau_2}}$$

**Solución.** Una forma conveniente para simular esta función de transferencia es dividir el diagrama de bloques en dos bloques en serie, como se muestra en la figura 9-17. Cada uno de los dos bloques es ahora un retardo de primer orden que se puede simular como en la parte (a) del ejemplo 9-1(a).

En este sistema $x(t)$ es la variable de entrada, $y_1$ es una variable intermedia, y $y(t)$ es la variable de salida. La ganancia $K$ se puede asignar a cualquiera de los dos bloques sin afectar la respuesta de la variable de salida $y(t)$.

La programación de las ecuaciones en el dominio del tiempo para los retardos de primer orden se ilustra en el ejemplo 9-5.

**Ejemplo 9-2. Simulación del tiempo muerto, retardo de transportación o tiempo de retardo.**
$$\frac{Y(s)}{X(s)} = e^{-t_0s}$$

o, en el dominio del tiempo:
$$y(t) = x(t - t_0)$$

donde $t_0$ es el tiempo muerto.

**Solución.** Una manera de simular el tiempo muerto es almacenar la respuesta de entrada $x(t)$ y reproducirla $t_0$ unidades de tiempo más tarde para generar la salida $y(t)$. Puesto que la respuesta almacenada no se necesita después de que se reproduce, sólo se necesita almacenar los valores de la respuesta durante $t_0$ unidades de tiempo; las localidades de almacenamiento se deben refrescar constantemente con valores de entrada. La forma en que funciona el programa para simular el tiempo muerto es la siguiente.

Se supone que el valor de la entrada se debe almacenar en cada intervalo de integración $\Delta t$ y, por lo tanto, el número de valores que se deben almacenar es:
$$k = \frac{t_0}{\Delta t}$$

Para almacenar los valores se utiliza un arreglo dimensional $Z$ con dimensión $k$ o mayor; los pasos del programa son los siguientes:

**Paso 1.** Se inicializan todas las $k$ localidades de $Z$ con el valor inicial de $x$, $x_0$ (generalmente cero):
Para $i = 1, 2, \ldots, k$, sea $Z_i = x_0$.

**Paso 2.** Se inicializa el índice $i$ de la tabla de valores:
Sea $i = 1$.

**Paso 3.** En cada paso de integración:
a) De la tabla se toma el valor $Z_i$ como la salida, y se almacena el valor de la entrada en esa localidad:
Sea $y = Z_i$, $Z_i = x$.
b) Se incrementa el índice:
Sea $i = i + 1$.
c) Cuando el índice excede a $k$, se regresa a uno para volver a utilizar las mismas localidades de almacenamiento:
Si $i$ es mayor que $k$, sea $i = 1$.

Se observará que la segunda vez, y las posteriores, que el programa pasa por las localidades de almacenamiento, se toma el valor que se almacenó ahí $k$ pasos antes; puesto que cada paso representa $\Delta t$ unidades de tiempo, el valor que se utiliza como salida es el de entrada $k\Delta t$ o $t_0$ unidades de tiempo antes. El proceso de almacenamiento y extracción se ilustra gráficamente en la figura 9-18.

La lógica del programa de simulación de tiempo muerto se complica algo cuando se utiliza con una subrutina de integración numérica para Euler modificado o Runge-Kutta, debido a que los enunciados de simulación de tiempo muerto se deben ejecutar junto con la evaluación de las funciones derivadas; esta ejecución se realiza dos o cuatro veces por paso de integración; en cambio, la operación de almacenamiento del programa de tiempo muerto se debe efectuar únicamente una vez por paso de integración. Para eliminar esta dificultad es necesario que en la subrutina de integración se ponga una bandera para indicar al programa de tiempo muerto que se debe almacenar el valor de entrada; la bandera de almacenamiento se debe poner únicamente para la evaluación de la primera derivada, ya que en ese momento las variables de estado tienen el valor más exacto después del paso de integración precedente.

El procedimiento de simulación de tiempo muerto que se describió en el ejemplo precedente se utiliza en el ejemplo 9-5 en la simulación por computador de un circuito de control por retroalimentación.

**Ejemplo 9-3. Simulación de una unidad de compensación dinámica de adelanto/retardo.**
$$\frac{Y(s)}{X(s)} = \frac{\tau_1s + 1}{\tau_2s + 1}$$

donde $\tau_1$ y $\tau_2$ son las constantes de tiempo del adelanto y del retardo, respectivamente.

**Solución.** Se despejan las fracciones:
$$\tau_2sY(s) + Y(s) = \tau_1sX(s) + X(s)$$

Se invierte la transformada de Laplace y se suponen condiciones iniciales cero:
$$\tau_2\frac{dy(t)}{dt} + y(t) = \tau_1\frac{dx(t)}{dt} + x(t)$$

Como es evidente, en esta ecuación se requiere la derivada de la variable de entrada $x(t)$ y, debido a que la diferenciación numérica generalmente es una operación muy imprecisa, se debe evitar siempre que sea posible.

Ahora se regresa a la ecuación en el dominio de Laplace y se agrupan los términos en $s$ después de dividir entre $\tau_2$:
$$sY(s) = \frac{1}{\tau_2}[(\tau_1s + 1)X(s) - Y(s)]$$

Se define:
$$Y_1(s) = Y(s) - \frac{\tau_1}{\tau_2}X(s)$$

y se substituye:
$$sY_1(s) = \frac{1}{\tau_2}[X(s) - Y(s)]$$

Se suponen condiciones iniciales cero y se invierte:
$$\frac{dy_1}{dt} = \frac{1}{\tau_2}[x(t) - y(t)]$$

a partir de la definición de $Y_1$, la variable de salida se expresa mediante:
$$y(t) = y_1(t) + \frac{\tau_1}{\tau_2}x(t)$$

En el ejemplo 9-5, esta ecuación de una unidad de adelanto/retardo se programa en la simulación de un controlador PID.

**Ejemplo 9-4. Simulación de un controlador industrial proporcional-integral-derivativo (PID).**
$$M(s) = K_c\left(1 + \frac{1}{\tau_Is}\right)\left(\frac{\tau_Ds + 1}{\alpha\tau_Ds + 1}\right)E(s)$$

$$E(s) = R(s) - C(s)$$

donde:
- $K_c$ es la ganancia del controlador
- $\tau_I$ es el tiempo de integración
- $\tau_D$ es el tiempo de derivación
- $E(s)$ es la señal de error
- $R(s)$ es la señal del punto de control
- $\alpha$ es el parámetro del filtro para ruido (generalmente 0.05 a 0.10)
- $M(s)$ es la salida del controlador
- $C(s)$ es la variable controlada

Esta función de transferencia se ajusta a la mayoría de los controladores analógicos "fuera de repisa" (off-the-shelf) que se utilizan en la industria.

**Solución.** En la figura 9-19a se muestra un diagrama de bloques del controlador. Como en el caso de los retardos de primer orden en serie [ejemplo 9-1(c)], es conveniente separar las funciones de transferencia en dos bloques, como se ilustra en la figura 9-19b; en la figura es evidente que la sección de derivación es una unidad de adelanto/retardo donde la constante de tiempo de adelanto es el tiempo de derivación, y el retardo es una fracción fija, $\alpha$, del adelanto.

Generalmente se considera indeseable que existan dos acciones de derivación sobre la señal del punto de control, porque ocasionan grandes golpes (kicks) derivativos sobre los cambios que hace el operador en el punto de control. Para evitar estos golpes se instala la unidad de derivación sobre la variable que se mide, antes de que se calcule el error, como se muestra en la figura 9-19c. En este diagrama de bloques también se ilustra la utilización del esquema de retroalimentación de reajuste para realizar la acción de integración. Como se expuso en la sección 6-5, cuando se utiliza la retroalimentación de reajuste es más fácil imponer límites sobre la salida del controlador. Las ecuaciones con que se representa el diagrama de bloques de la figura 9-19c son:

**Unidad derivativa (adelanto/retardo)**
$$\frac{C_1(s)}{C(s)} = \frac{\tau_Ds + 1}{\alpha\tau_Ds + 1} \quad (A)$$

**Cálculo de error**
$$E_1(s) = R(s) - C_1(s) \quad (B)$$

**Acción proporcional**
$$M(s) = K_cE_1(s) + Y(s) \quad (C)$$

**Retroalimentación de reajuste**
$$Y(s) = \frac{1}{\tau_Is}M(s) \quad (D)$$

La ecuación (A) es para una unidad de adelanto/retardo y se puede simular como se explicó en el ejemplo 9-3:
$$\frac{dc_2(t)}{dt} = \frac{1}{\alpha\tau_D}[c(t) - c_1(t)]$$
$$c_1(t) = c_2(t) + \frac{\tau_D}{\alpha\tau_D}c(t)$$

Las ecuaciones (B) y (C) se pueden invertir de una manera directa:
$$e_1(t) = r(t) - c_1(t)$$
$$m(t) = K_ce_1(t) + y(t)$$

La ecuación (D) es un retardo de primer orden con ganancia unitaria y se puede simular de la forma que se expuso en el ejemplo 9-1(a):
$$\frac{dy}{dt} = \frac{1}{\tau_I}[m(t) - y(t)]$$

En este modelo del controlador, $r(t)$ es la señal del punto de control (entrada), $c(t)$ es la señal de la variable controlada (entrada), $m(t)$ es la variable manipulada (salida), $e_1(t)$ es el error y $c_1(t)$, $c_2(t)$ y $y(t)$ son variables intermedias. Se notará que $c_2(t)$ y $y(t)$ son las dos variables de estado del modelo.

La programación de las ecuaciones para el controlador PID se ilustra en el siguiente ejemplo.

**Ejemplo 9-5. Simulación del circuito de control por retroalimentación de la figura 9-20a con las siguientes funciones de transferencia.**

**Proceso**
$$G(s) = \frac{Ke^{-t_0s}}{(\tau_1s + 1)(\tau_2s + 1)}$$

**Controlador PID**
$$G_c(s) = K_c\left(1 + \frac{1}{\tau_Is}\right)\left(\frac{\tau_Ds + 1}{\alpha\tau_Ds + 1}\right)$$

donde los símbolos tienen el mismo significado que en los ejemplos 9-1(c), 9-2 y 9-4, $L(s)$ es una entrada de perturbación.

**Solución.** En la figura 9-20 se separan en componentes de primer orden los bloques del circuito de control por retroalimentación; también se movió el elemento derivativo del controlador, de manera que no actúe sobre la señal del punto de control, y se utiliza la retroalimentación de reajuste para la acción integracional (ver ejemplo 9-4).

El controlador PID se puede simular como en el ejemplo 9-4; debido a que los nombres de las variables son los mismos que en el ejemplo, no se necesita repetir aquí las ecuaciones en el dominio del tiempo. Las ecuaciones para el resto del circuito son las siguientes:

**Proceso**
$$x_1(t) = K[m(t - t_0) + l(t - t_0)]$$

**Retardo de primer orden 1**
$$\tau_1\frac{dx_1(t)}{dt} + x_1(t) = K[m(t - t_0) + l(t - t_0)]$$

**Retardo de primer orden 2**
$$\tau_2\frac{dx_2(t)}{dt} + x_2(t) = x_1(t)$$
$$c(t) = x_2(t)$$

El tiempo muerto se simula mediante el almacenamiento de los valores de $x_2(t)$ y su reproducción $t_0$ unidades de tiempo más tarde, como se explicó en el ejemplo 9-2, ya que:
$$c(t) = x_2(t - t_0)$$

Estas ecuaciones, junto con las del controlador que se dan en el ejemplo 9-4, constituyen el modelo de circuito de control por retroalimentación. En la figura 9-21 se lista una subrutina FORTRAN para hacer el modelo del circuito; esta subrutina se denomina MODEL y se utiliza con el programa principal de la figura 9-14 y las subrutinas de integración numérica de las figuras 9-13 ó 9-16. Se observará que se utiliza el argumento IEVAL en la simulación del tiempo muerto; dicho argumento se fija en la subrutina de integración con el número de secuencia de cada evaluación de derivada, durante cada paso de integración. En los enunciados de simulación del tiempo muerto, el valor de IEVAL se utiliza de manera que los valores se almacenen únicamente durante la primera evaluación de la derivada (IEVAL = 1) de cada paso de integración. Para que el modelo del tiempo muerto funcione de forma apropiada, el intervalo de integración, DTIME ($\Delta t$), debe ser un submúltiplo entero del tiempo muerto, TO($t_0$); además, en la subrutina (como la que se lista en la figura 9-21) el tiempo muerto se limita a un máximo de 100 veces el intervalo de integración.

Con la subrutina de la figura 9-21 se puede lograr que la segunda constante de tiempo, TAU2 ($\tau_2$), y el tiempo de derivación, TD ($\tau_D$), se hagan iguales a cero. El parámetro de derivación del filtro de ruido, ALPHA ($\alpha$), se hace igual a 0.10; el retardo de la unidad derivativa, $\alpha\tau_D$, generalmente es la constante de tiempo más pequeña del modelo; a causa de esto es importante que el intervalo de integración, DTIME ($\Delta t$), sea menor que $\alpha\tau_D$, ya que de otra manera la integración numérica sería inestable.

La subrutina de la figura 9-21 es muy útil para verificar los resultados de lugar de raíz y el análisis de respuesta en frecuencia (capítulo 7), y para probar la respuesta del circuito a varias combinaciones de parámetros de circuito y fórmulas de ajuste (capítulo 6). Se pueden simular las respuestas a entradas del punto de control y de perturbaciones; en esta subrutina particular sólo se consideran cambios de escalón unitario.

La respuesta a la entrada de una perturbación se muestra en la figura 9-22; el ajuste es para una perturbación IAE mínima (tabla 6-3).

Para facilitar el ajuste del controlador, con la subrutina de la figura 9-21 se calculan e imprimen los cuatro errores de integración que se definieron en el capítulo 6: IAE, ICE, IAET e ICET. Para esta estructura se requiere la adición de cuatro variables de estado -una por cada error de integración- a las cuatro variables de estado con que se simula el circuito.

En este ejemplo se ilustró la simulación de los modelos dinámicos que se describieron en los ejemplos precedentes; dichos modelos son útiles en la simulación de sensores, controladores y válvulas de control que se asocian generalmente con el modelo dinámico del propio proceso.

## 9-8. RIGIDEZ

Como se vio en la sección 9-5, se dice que un sistema de ecuaciones diferenciales es rígido si la razón de su eigenvalor mayor respecto al menor es grande. En el capítulo 2, los eigenvalores de un sistema dinámico se definen como las raíces de la ecuación característica de la función de transferencia del sistema. Mientras más grande es la rigidez de un modelo, mayor es la cantidad de pasos de integración y, en consecuencia, el tiempo de computadora que se requiere para simular el sistema en una computadora digital. En esta sección se estudiarán las fuentes de rigidez que se pueden eliminar cuando se hace el modelo de un sistema. También se abordarán brevemente algunos de los métodos de integración numérica que se han diseñado para manejar eficientemente los sistemas rígidos de ecuaciones diferenciales.

### Fuentes de rigidez en un modelo

De un modelo que consta de $n$ ecuaciones diferenciales ordinarias de primer orden, se dice que es de orden $n$, debido a que, en ausencia de los elementos de tiempo muerto, las ecuaciones linealizadas se pueden reducir a una sola función de transferencia total, cuyo denominador es un polinomio de grado $n$ en la variable $s$ de la transformada de Laplace. De aquí se tiene que la ecuación característica de tal sistema tiene $n$ raíces, las cuales son los $n$ eigenvalores del sistema y, por lo tanto, por cada ecuación diferencial ordinaria de primer orden que se escribe para el modelo del sistema, se añade un eigenvalor a la respuesta del modelo.

Debido a la interacción entre las ecuaciones diferenciales que constituyen el modelo de un sistema, en principio la respuesta de cada variable de estado se puede afectar con cada eigenvalor de las ecuaciones del modelo. La respuesta del sistema linealizado se puede representar mediante la siguiente ecuación:

$$x_i(t) = b_1e^{r_1t} + b_2e^{r_2t} + \ldots + b_ne^{r_nt} + (\text{términos de entrada}) \quad (9-83)$$

$x_i(t)$ es la respuesta de la variable de estado $i$
$b_1, b_2, \ldots, b_n$ son los coeficientes que dependen del sistema y de su función de forzamiento de entrada
$r_1, r_2, \ldots, r_n$ son los eigenvalores del sistema, 1/tiempo

y los "términos de entrada" dependen de la función de forzamiento de entrada específica que se aplica al sistema.

Nota: La ecuación (9-83) se puede obtener mediante la transformación de Laplace de las ecuaciones linealizadas del sistema, la eliminación algebraica de todas las variables de estado, excepto $X_i(s)$, y la inversión mediante expansión de fracciones parciales, como se estudió en el capítulo 2.

Si el sistema es estable, las partes reales de todos los eigenvalores son negativas (ver sección 6-2), lo cual significa que, con el tiempo, cada término de la ecuación (9-83) tiende exponencialmente a cero. Cuando más grande es la magnitud de la parte real negativa del eigenvalor, tanto más rápido decae a cero el término correspondiente de la ecuación (9-83); en cambio, el término con el eigenvalor cuya parte real es la más pequeña (en magnitud) es el que tiene el tiempo más largo para tender a cero y, en consecuencia, éste es el eigenvalor "dominante" con el que se controla el tiempo al cual el modelo alcanza el estado estacionario. Como se verá en breve, en las fórmulas de integración explícitas, con el eigenvalor más grande se impone un límite de estabilidad superior para el intervalo de integración; de aquí que el número de pasos de integración (cálculos) necesarios para resolver las ecuaciones diferenciales se incremente con la razón del eigenvalor mayor al menor.

En un sistema rígido de ecuaciones diferenciales, la magnitud de algunos de los eigenvalores es mucho mayor que la del dominante; sin embargo, se observa que los términos de la ecuación (9-83) correspondientes a esos eigenvalores grandes deben tender necesariamente a cero mucho más rápidamente que el eigenvalor dominante y, por lo tanto, su efecto dinámico sobre la respuesta total es de corta duración; de hecho, su duración es una fracción muy pequeña de la duración de la respuesta, y generalmente se puede despreciar. Con esto se sugiere que la rigidez de un modelo se reduce si se eliminan de las ecuaciones del modelo los eigenvalores que en magnitud son mucho mayores que el eigenvalor dominante.

Una suposición mediante la cual se pueden eliminar los eigenvalores del sistema de ecuaciones de un modelo es la suposición de estado cuasi-estacionario, la cual consiste en despreciar el término de acumulación de una ecuación de balance, de manera que ésta se convierta en una ecuación algebraica del modelo, en lugar de una de las ecuaciones diferenciales de primer orden, con lo cual se reduce el orden del sistema en uno; por lo tanto, se elimina uno de los eigenvalores. Sea $x_j$ la variable de estado que se asocia con la ecuación diferencial que se elimina, entonces la suposición de estado cuasiestacionario consiste en la siguiente aproximación de la ecuación del modelo:

$$\frac{dx_j}{dt} = f_j(x_1, x_2, \ldots, x_n, t) = 0 \quad (9-84)$$

donde:
- $f_j$ es la función derivada
- $x_1, x_2, \ldots, x_n$ son las variables de estado

Se notará que la aproximación que se indica en la ecuación (9-84) no afecta a la solución de estado estacionario de las ecuaciones del modelo, sino que únicamente se desprecia el efecto transitorio. También se observa que la variable $x_j$ deja de ser una variable de estado y se convierte en una variable auxiliar del modelo. La situación ideal es aquella donde la variable $x_j$ se puede calcular explícitamente a partir de la ecuación (9-84); sin embargo, aun cuando la ecuación (9-84) se deba resolver iterativamente para $x_j$, se obtiene una ventaja computacional si con la reducción en la rigidez del sistema se logra un incremento significativo en el intervalo de integración. La razón de lo anterior es que, a pesar de que en el método de solución iterativa se requieren unas cuantas evaluaciones de la ecuación (9-84) en cada paso de integración, en el sistema rígido se requiere la evaluación de todas las ecuaciones del modelo, tantas veces como pasos se requieren en el modelo rígido.

Ahora que se sabe que es posible reducir la rigidez mediante la aplicación de la suposición de estado cuasiestacionario a algunas de las ecuaciones diferenciales del modelo, se tiene el problema de reconocer las ecuaciones con que se introducen los eigenvalores grandes que ocasionan la rigidez. La solución de este problema es parte del arte de la simulación; pero antes de proceder a la explicación se debe enfatizar el hecho de que no siempre es posible aislar las ecuaciones con que se produce la rigidez.

En la práctica se encuentra que muchas de las ecuaciones diferenciales de primer orden que constituyen el modelo actúan como retardos de primer orden; es decir, la variable de estado que aparece en el término derivativo retarda a las demás variables del modelo. Si éste es el caso, existirá un eigenvalor que se asocia con la ecuación diferencial bajo consideración, cuya magnitud es del orden del recíproco de la constante de tiempo del retardo; una manera sencilla para estimar tal eigenvalor es derivar parcialmente la función derivada respecto de la variable de estado en el término derivativo. Respecto a la ecuación (9-84), el eigenvalor se estima mediante:

$$r_j \approx \frac{\partial f_j}{\partial x_j} \quad (9-85)$$

donde $r_j$ es el eigenvalor que se asocia con la ecuación en cuestión. El problema de esta estimación es que puede ser lejana cuando el acoplamiento entre las ecuaciones del modelo es alto, como en el caso de las ecuaciones de balance de un equipo de flujo a contracorriente, por ejemplo, las columnas de destilación (ver sección 9-12).

Los siguientes son algunos ejemplos de ecuaciones con las que se pueden introducir eigenvalores grandes en la solución de las ecuaciones del modelo; se observa que en cada caso se sospecha que el efecto dinámico considerado es mucho más rápido que los eigenvalores dominantes del sistema.

1. El retardo de válvula o de transmisor cuya constante de tiempo es de unos cuantos segundos cuando las otras constantes de tiempo son del orden de minutos u horas.
2. La acumulación en la fase de vapor cuando la acumulación en la fase líquida también se considera. La masa de la fase de vapor generalmente es mucho más pequeña que la masa en la fase líquida.
3. La aceleración de un fluido en un conducto corto, en relación con la acumulación de fluido en los tanques. Esto es análogo al efecto de la aceleración sobre un auto subcompacto cuando choca contra un camión de 18 ruedas completamente cargado: se puede suponer que el subcompacto alcanza instantáneamente la velocidad del camión en el momento del impacto.

Con el siguiente ejemplo se ilustra el efecto de la suposición de estado cuasiestacionario sobre la respuesta dinámica de un sistema.

**Ejemplo 9-6. Simulación del drenado de un tanque mediante gravedad, a través de un tubo de descarga vertical.**

Se tiene un tanque cilíndrico (ver figura 9-23) de diámetro $D_t$ y altura $H$, el cual inicialmente está lleno de agua y se descarga a través de un tubo vertical de longitud $L$ y diámetro $D_p$. Tanto el tanque como el tubo de descarga están abiertos a la atmósfera y la fricción de la caída en el tubo, incluyendo pérdidas por contracción y expansión, se expresa mediante:

$$\Delta p_f = \frac{k_f\rho v^2}{2}$$

donde:
- $k_f$ es un coeficiente de fricción = $4f\frac{L}{D_p} + k_c + k_e$
- $\Delta p_f$ es la caída de presión por fricción, N/m²
- $\rho$ es la densidad del agua, kg/m³
- $v$ es la velocidad promedio en el tubo, m/s
- $f$ es el factor de fricción de Fanning y se supone constante
- $k_c$ es el coeficiente de pérdida por contracción
- $k_e$ es el coeficiente de pérdida por expansión (= 1.0)

Se debe determinar el tiempo que toma vaciar el tanque.

**Solución.** Del balance de masa alrededor del tanque resulta la siguiente ecuación:

$$\frac{\pi D_t^2}{4}\frac{dy}{dt} = -\frac{\pi D_p^2}{4}v \quad (B)$$

donde:
- $D_p$ es el diámetro del tubo, m
- $D_t$ es el diámetro del tanque, m
- $y$ es el nivel en el tanque, m

Puesto que la densidad es constante, la ecuación (B) se simplifica a:

$$\frac{dy}{dt} = -\left(\frac{D_p}{D_t}\right)^2v \quad (C)$$

La siguiente ecuación se obtiene del balance de fuerzas en el tubo:

$$\text{suma de fuerzas} = \frac{d(\text{momento})}{dt}$$

$$\frac{\pi D_p^2}{4}(p - p_a) + \rho g\frac{\pi D_p^2}{4}L - \frac{\pi D_p^2}{4}\Delta p_f = \rho\frac{\pi D_p^2}{4}L\frac{dv}{dt} \quad (D)$$

donde:
- $p$ es la presión en el fondo del tanque, N/m²
- $p_a$ es la presión atmosférica, N/m²
- $g$ es la aceleración de la gravedad, 9.8 m/s²
- $L$ es la longitud del tubo, m

La presión en el fondo del tanque se relaciona con el nivel del tanque en cualquier instante, mediante la fórmula:

$$p = p_a + \rho g y \quad (E)$$

Ahora se substituyen las ecuaciones (A) y (E) en (D), para obtener:

$$\frac{dv}{dt} = \frac{g}{L}(y + L) - \frac{k_f}{2L}v^2 \quad (F)$$

Las ecuaciones (C) y (F) son suficientes para determinar la respuesta dinámica del nivel del agua en el tanque y la velocidad en el tubo. Las condiciones iniciales son tanque lleno y velocidad cero en el tubo:

$$y(0) = y_0 = H$$
$$v(0) = 0$$

Se resuelven las ecuaciones (C) y (F) para determinar el tiempo $t_f$ que se requiere para vaciar el tanque:

$$y(t_f) = 0$$

Un posible problema es que el sistema de ecuaciones (C) y (F) sea rígido, lo cual ocurriría si el tiempo requerido para que el líquido en el tubo se acelere hasta un valor de equilibrio, a un cierto nivel en el tanque fuera significativamente menor que el tiempo necesario para vaciar desde ese nivel.

Si el término de aceleración en el miembro derecho de la ecuación (D) es despreciable, entonces:

$$\frac{\pi D_p^2}{4}(p - p_a) + \rho g\frac{\pi D_p^2}{4}L - \frac{\pi D_p^2}{4}\Delta p_f = 0$$

$$p - p_a + \rho gL - \frac{k_f\rho v^2}{2} = 0$$

$$y + L - \frac{k_fv^2}{2g} = 0 \quad (H)$$

Por tanto, si el sistema de ecuaciones (C) y (F) resulta ser severamente rígido, la ecuación (F) se puede substituir por su aproximación, ecuación (H). Físicamente, esto equivale a despreciar la aceleración del fluido en el tubo en la ecuación de balance de fuerzas, ecuación (D); esto es la suposición de estado cuasiestacionario.

Los parámetros son los siguientes:
- Altura del tanque: $H = 0.762$ m (30 pulg)
- Diámetro del tanque: $D_t = 0.1397$ m (5.5 pulg)
- Diámetro del tubo: $D_p = 6.83 \times 10^{-3}$ m (0.269 pulg)
- Longitud del tubo: $L = 0.4572$ m (18 pulg)
- Aceleración de la gravedad: $g = 9.8$ m/s² (32.2 pies/s²)
- Coeficiente de fricción: $k_f = 4.2$ (sin dimensiones)
- Densidad del agua: $\rho = 1000$ kg/m³ (62.3 lb/pies³)

En la figura 9-24 se muestra un listado de la subrutina MODEL en FORTRAN para resolver este problema. Con esta subrutina se simulan los dos modelos del tanque simultáneamente, con la finalidad de comparar las respuestas dinámicas. Las primeras dos variables de estado corresponden a $y$ y $v$ de las ecuaciones (C) y (F); mientras que la tercera corresponde al nivel $y$ ($y_P$) de la ecuación (C) cuando se utiliza la ecuación (H) para calcular la velocidad $v$ ($v_P$).

La subrutina de la figura 9-24 se combina con la subrutina Runge-Kutta-Simpson de la figura 9-16 y el programa principal de la figura 9-24 para producir las respuestas que se tabulan en la figura 9-25. Se tabulan los resultados de dos corridas; en la primera se presenta en detalle la respuesta durante los primeros 0.5 segundos de operación y se observa cómo la velocidad $v$ que se calcula mediante el modelo exacto se inicia en cero, se acelera hasta la velocidad de estado cuasiestacionaria $v_P$ y entonces la retarda; en esto estriba la diferencia entre los dos modelos. En la segunda corrida se observa cómo, a la larga, de los dos modelos se obtienen esencialmente los mismos tiempos de vaciado y niveles; aquí la diferencia consiste en que con el modelo exacto, que es algo rígido, se requiere un intervalo de integración (DTIME) mucho más pequeño que con el modelo de estado cuasiestacionario. En las condiciones iniciales, los eigenvalores para el modelo exacto se calculan mediante la linealización de las ecuaciones (C) y (F); éstos son, respectivamente, $-0.0023$ y $-21.9$ seg⁻¹, y representan un grado de rigidez cercano a 10,000.

En el ejemplo precedente se ilustra que mediante la suposición de estado cuasiestacionario se obtienen esencialmente los mismos resultados dinámicos que con el modelo original; la ventaja de este hecho es que, tanto mayor es el grado de rigidez del sistema, cuanto menor es el error que ocasiona la suposición de estado cuasiestacionario.

### Integración numérica de los sistemas rígidos

Se dice que los tres métodos de integración numérica que se consideraron en la sección 9-5, Euler, Euler modificado y Runge-Kutta-Simpson, son métodos explícitos; esto se debe a que las variables de estado se calculan de manera explícita en cada paso de integración, con base en los valores que resultan en el paso precedente. En esa misma sección se mencionó que, para un paso de integración bastante grande, la solución numérica se puede hacer inestable aun cuando la respuesta de las ecuaciones del modelo es dinámicamente estable. En esta sección se presentará brevemente un tipo de métodos implícitos de integración numérica en los que no hay limitaciones de estabilidad.

Para afirmar las ideas acerca de la estabilidad numérica, a continuación se considera la siguiente ecuación diferencial lineal de primer orden:

$$\frac{dx}{dt} = rx \quad (9-86)$$

donde:
- $x$ es la variable de estado
- $r$ es el eigenvalor, 1/tiempo

La solución analítica de esta ecuación, que está sujeta a alguna condición inicial $x_0$, es:

$$x(t) = x_0e^{rt} \quad (9-87)$$

Evidentemente, esta respuesta es estable si la parte real de $r$ es negativa, o es un número negativo. Ahora se considera la solución numérica de la ecuación (9-86) mediante el método de Euler; de la ecuación (9-69) se obtiene:

$$x|_{t+\Delta t} = x|_t + rx|_t\Delta t = (1 + r\Delta t)x|_t \quad (9-88)$$

donde $\Delta t$ es el intervalo de integración, siempre real y positivo. En la ecuación (9-88) es evidente que, si la magnitud de cada valor de $x$ debe ser menor que el precedente, se debe cumplir la siguiente condición:

$$|1 + r\Delta t| < 1 \quad (9-89)$$

o si $r$ es un número real:

$$-2 < r\Delta t < 0 \quad (9-90)$$

La ecuación (9-89) es la condición de estabilidad numérica para el método de Euler, y la ecuación (9-90) representa los límites de estabilidad de $r\Delta t$ cuando éste es un número real. Para el caso en que $r$ es un número real negativo, los valores de $\Delta t$ para los cuales la solución numérica de Euler es estable son:

$$\Delta t < \frac{2}{|r|} \quad (9-91)$$

Se debe notar que el valor máximo de $\Delta t$ es inversamente proporcional a la magnitud del eigenvalor $r$; sin embargo, se debe tener en cuenta que el valor de $\Delta t$ para el cual la solución numérica es precisa, es decir, coincide con la solución real, ecuación (9-87), con una cierta tolerancia, es generalmente mucho más pequeño que el límite de estabilidad que se obtiene con la ecuación (9-91).

En la sección 9-5 se vio cómo con las fórmulas de Euler modificada y Runge-Kutta-Simpson se obtiene la misma exactitud que con el método de Euler, pero con intervalos de integración cuyo orden de magnitud es mayor. Sin embargo, en términos de los límites de estabilidad de $\Delta t$, los de los métodos explícitos Euler y Runge-Kutta son casi los mismos que los del método de Euler y se expresan con la ecuación (9-91). Esto es significativo porque, para un sistema de ecuaciones diferenciales rígido, el límite de estabilidad del intervalo de integración es menor que el límite total de exactitud, debido a que, como se vio anteriormente, los eigenvalores grandes, los cuales hacen que la solución se vuelva inestable, tienen poco efecto sobre la exactitud total de la respuesta que se calcula. En otras palabras, en términos de los eigenvalores grandes que ocasionan la rigidez, únicamente se necesita que haya estabilidad, no precisión.

Los métodos implícitos de integración numérica se desarrollaron para sistemas rígidos de ecuaciones diferenciales; una propiedad de estos métodos es que no existe limitación de estabilidad en el tamaño del intervalo de integración, lo cual significa que la única consideración para elegir el intervalo de integración es la exactitud de la respuesta total. Para ilustrar uno de los métodos más simples, a continuación se considera la solución numérica de la ecuación (9-86) mediante el método de Euler modificado implícito; la fórmula de la integración numérica es:

$$x|_{t+\Delta t} = x|_t + \frac{1}{2}(rx|_t + rx|_{t+\Delta t})\Delta t \quad (9-92)$$

La diferencia entre esta fórmula y la explícita, ecuación (9-75), consiste en que ésta se encuentra implícita en la variable de estado $x|_{t+\Delta t}$; es decir, la aproximación al término $x|_{t+\Delta t}$ en el miembro derecho no se hace con una fórmula diferente. En este caso simple de una sola ecuación lineal de primer grado, la solución implícita es directa. Al resolver la ecuación (9-92) para $x|_{t+\Delta t}$, se obtiene:

$$x|_{t+\Delta t} = \frac{1 + \frac{1}{2}r\Delta t}{1 - \frac{1}{2}r\Delta t}x|_t \quad (9-93)$$

La condición de estabilidad para esta fórmula es:

$$\left|\frac{1 + \frac{1}{2}r\Delta t}{1 - \frac{1}{2}r\Delta t}\right| < 1 \quad (9-94)$$

Se puede demostrar fácilmente que con todos los valores positivos de $\Delta t$ se satisface esta condición, siempre y cuando la parte real del eigenvalor, $r$, sea negativa; en otras palabras, la solución numérica es estable en tanto que el sistema original es estable.

La forma general de la ecuación de Euler modificada implícita, contraparte real de la ecuación (9-75), es la siguiente:

Para $i = 1, 2, \ldots, n$, se calcula:
$$x_i|_{t+\Delta t} = x_i|_t + \frac{1}{2}[f_i(x_1, x_2, \ldots, x_n, t)|_t + f_i(x_1, x_2, \ldots, x_n, t)|_{t+\Delta t}] \quad (9-95)$$

donde $f_i$ son las funciones derivadas. Es de notar que, para resolver de manera implícita este sistema de $n$ ecuaciones algebraicas no lineales correspondientes a los valores de las variables de estado, $x_i|_{t+\Delta t}$, $i = 1, 2, \ldots, n$, se requiere una solución reiterativa, es decir, la evaluación repetida de todas las ecuaciones del modelo en cada paso de integración. La ventaja de este método estriba en la reducción de la cantidad total de pasos de integración en un factor mayor que el número de evaluaciones de la función por paso; obviamente esta ventaja es mayor conforme más rígido es el sistema, y nula cuando el sistema no es rígido. En la subrutina LSODE, una de la tabla 9-1, se utiliza el método implícito de Gear para sistemas rígidos; éste es un método de orden y tamaño de pasos variables.

## 9-9. RESUMEN

En este capítulo se presentó el desarrollo de los modelos dinámicos de los sistemas de control de proceso y los métodos para simular dichos sistemas en computadoras digitales. También se presentaron los modelos de una columna de destilación de componentes múltiples, de un horno de proceso, de un tanque de reacción química con agitación continua y varios elementos dinámicos que se encuentran comúnmente en los sistemas de control de proceso. En el capítulo se incluye el estudio de la rigidez, su fuente y los métodos para manejarla cuando se resuelven sistemas de ecuaciones diferenciales.

## BIBLIOGRAFÍA

1. Conte, S. D. y C. deBoor, *Elementary Numerical Analysis*, 3rd ed., McGraw-Hill, Nueva York, 1980, capítulos 5 y 8.
2. Broyden, C. G., "A Class of Methods for Solving Nonlinear Simultaneous Equations," *Math. of Comps.*, Vol. 19, No. 92, Oct. 1965, pp. 577-593.
3. Gear, C. W., *Numerical Initial Value Problems in Ordinary Differential Equations*, Prentice Hall, Englewood Cliffs, N.J., 1971.
4. Luyben, W. L., *Process Modeling, Simulation, and Control for Chemical Engineering*, McGraw-Hill, Nueva York, 1973, capítulos 3 y 5.

## PROBLEMAS

**9-1.** Se debe verificar si el circuito de control de concentración del problema 6-24 se puede poner en marcha en automático; esto se puede hacer mediante la programación de las ecuaciones no lineales del modelo en una computadora y la simulación del procedimiento de arranque. Se supone que inicialmente ambos reactores están llenos de la solución de alimentación, a una concentración de 0.80 lbmol/gal, y que la reacción empieza tan pronto como la solución alcanza la temperatura de operación. También se debe ajustar el controlador de concentración; primero se debe simular la operación de los reactores con sus condiciones de diseño. Con esto se tiene la oportunidad de ajustar el controlador y verificar si la simulación cumple con las condiciones de operación de estado estacionario.

a) Se deben escribir las ecuaciones del modelo y programarlas para su resolución en una computadora. Es necesario fijar las condiciones iniciales a las condiciones de operación de diseño, y verificar que con ellas se logre un estado estacionario.
b) El controlador de composición se debe ajustar para IAE mínimo con un cambio escalón del 10% en el flujo de los reactivos.
c) Ahora, con las condiciones de arranque como iniciales, se debe simular la puesta en marcha.

Nota: Para evitar el reajuste excesivo y limitar la salida del controlador a un rango entre 0 y 100%, es necesario utilizar la retroalimentación de reajuste en el controlador por retroalimentación (ver ejemplo 9-4).

d) Se debe observar el efecto del reajuste excesivo cuando la salida del controlador se limita a -25 y 125%.

Precaución: Los límites de la válvula de control se deben fijar de manera que el flujo varíe de cero al máximo, es decir, no debe haber flujo negativo. Los límites del controlador corresponden a 0 y 24 mA, respectivamente, en el rango de 4 a 20 mA.

Los resultados se deben comentar brevemente.

**9-2.** Se necesita que el calentador de aceite del problema 6-26 funcione a la mitad de la razón de producción de diseño, y se debe verificar si es necesario o no reajustar los parámetros de ajuste de los controladores de nivel y temperatura. Se decide hacer esto mediante la simulación de las ecuaciones no lineales del modelo en computadora y el ajuste de los controladores tanto del flujo de diseño como a la mitad del flujo de diseño. Los controladores se ajustarán para IAE mínimo cuando entran perturbaciones.

a) Se deben escribir y programar las ecuaciones del modelo para resolverlas en una computadora, así como verificar que con las condiciones de diseño se logre un estado estacionario.
b) Los controladores se deben ajustar para cambios escalón de 5% en la posición de la válvula de salida con flujo de diseño completo.
c) Se debe reducir el flujo a la mitad, mediante el cierre de la válvula de salida, y observar la respuesta.
d) Ahora se fijarán las condiciones iniciales a las condiciones finales de estado estacionario de la parte (c), o sea, a las condiciones de medio flujo, y se ajustarán los controladores a estas condiciones. ¿Existe alguna diferencia? Los resultados se comentarán brevemente.

**9-3.** Un tanque que contiene 20,000 litros de solución se utiliza para neutralizar una corriente de ácido clorhídrico (HCl) con un reactivo, que consiste en una solución de 0.1 N de hidróxido de sodio. El flujo y la concentración de diseño del HCl son 500 litros/min y 0.01 N.

En la figura 9-26 se presenta un esquema del tanque con el controlador de pH. La señal del transmisor de pH es lineal respecto al pH de la solución en el tanque, el cual se define mediante:

$$pH = -\log_{10}[H^+]$$

donde $[H^+]$ es la concentración de iones de hidrógeno, gmol/litro. El electrodo pH se puede simular mediante un retardo lineal de primer orden de 15 seg; el controlador es proporcional-integral (PI) y el punto de control de diseño del pH es 7. El transmisor se calibra para un rango de pH de 1 a 13. En la válvula de control se tiene una caída constante de presión de 10 psi y un dimensionamiento para una sobrecapacidad del 100%; se tienen características de porcentaje igual con un parámetro de ajuste en rango de 50. Para simular el actuador de la válvula se puede utilizar un retardo de primer orden con una constante de tiempo de 5 seg.

Se puede suponer que la reacción de neutralización alcanza el equilibrio inmediatamente y, por tanto, las concentraciones de iones de hidrógeno e hidróxido se relacionan mediante la constante de disociación del agua:

$$[H^+][OH^-] = 10^{-14}$$

El tanque se encuentra inicialmente en las condiciones de diseño de estado estacionario.

a) Se deben escribir las ecuaciones necesarias para expresar el modelo del tanque si se supone que en él la mezcla de la solución es perfecta y el volumen constante. También se deben calcular las condiciones iniciales.
b) Se deben programar las ecuaciones para resolverlas en una computadora y ajustar el controlador a IAE mínimo (integral del valor absoluto del error) para un cambio escalón en la concentración de HCl de 0.005 gmol/litro.
c) Se deben obtener las respuestas cuando el controlador se ajusta para cambios en el punto de control de ±0.5 unidades de pH y de 10% en el flujo de la solución de HCl.

**9-4.** El evaporador que se ilustra en la figura 9-27 se utiliza para concentrar una solución de azúcar desde una fracción de masa de alimentación $X_f$ hasta una fracción de masa de producto $X_P$. Como medio de calefacción se dispone de vapor saturado a 20 psia; el agua de enfriamiento entra al condensador barométrico con una temperatura $T_w$. Se puede suponer que la presión en el evaporador es la presión de vapor del agua a la temperatura de salida del condensador, $T_c$, que la mezcla del contenido del evaporador es perfecta y que la temperatura de los tubos de calandria es igual a la del vapor que se condensa, $T_s$. Las pérdidas de calor se pueden despreciar.

El área de transferencia del evaporador es de 309.5 pies², y su capacidad es de 4.2 pies³ de solución por pie de nivel. La capacidad calórica de los tubos de calandria es 154 Btu/°F, el coeficiente de transferencia de calor es 150 Btu/h-pie²-°F. El volumen de la solución abajo de los tubos de transferencia de calor es de 4.68 pies³.

Las válvulas de control tienen características lineales, constantes de tiempo de 5 seg y se dimensionan para una sobrecapacidad del 100%. La caída de presión a través de la válvula de control de alimentación es constante a 16 psi, y a través de la válvula de producto es igual a la presión en el evaporador, debido a que con un soporte barométrico se hace que la presión, en el lado "corriente abajo" de la válvula de producto, sea cero absoluto. El sensor de nivel es un flotador con rango de 0 a 2 pies por arriba del fondo de los tubos. El rango del transmisor de concentración (AT20) es de 0.3 a 0.8 unidades de fracción de masa, y la constante de tiempo, de 25 seg. El controlador de nivel (LC20) es proporcional, con un punto de control de 25% del rango, y se ajusta para un control estricto de nivel (banda proporcional entre 1 y 10%). El controlador de concentración (ARC20) es proporcional-integral (PI).

Las condiciones de diseño son:
- Fracción de masa de alimentación: 0.10
- Temperatura de alimentación: 90°F
- Fracción de masa del producto (punto de control): 0.70
- Temperatura de salida del condensador: 105°F
- Temperatura de entrada del agua de enfriamiento: 90°F

Las siguientes correlaciones se pueden utilizar para calcular las propiedades físicas de la solución y del vapor:

- Entalpía de la solución: $H = (1 - 0.7x)(T - T_R)$ Btu/lb
- Densidad de la solución: $\rho = 62.384 + 23.14x + 11.27x^2$ lb/pies³
- Elevación del punto de ebullición: $BPR = 1.13 - 6.59x + 26.9x^2$ °F

donde:
- $x$ es la fracción de masa de azúcar
- $T$ es la temperatura, °F
- $T_R$ es la temperatura de referencia, °F

La capacidad calórica del agua líquida es 1.0 Btu/lb-°F, y la del vapor de agua es 0.46 Btu/lb-°F; estas capacidades se pueden suponer constantes y se utilizan para corregir el calor de vaporización latente del agua por cambios en la temperatura.

La ecuación de Antoine se puede utilizar para calcular la presión de vapor del agua en función de la temperatura, y viceversa:

para agua: $\ln P^0 = 18.3036 - \frac{3816.44}{T + 227}$

donde $P^0$ está en mm de mercurio y $T$ en °C.

El evaporador se encuentra inicialmente a las condiciones de diseño de estado estacionario. Las posibles perturbaciones son la razón del vapor, la fracción de masa de alimentación, la razón de agua para enfriamiento que entra al condensador, la temperatura del agua para enfriamiento y el punto de control de la composición del producto.

a) Se deben escribir las ecuaciones del modelo y calcular las condiciones de diseño de estado estacionario. Se deben programar las ecuaciones para resolverlas en una computadora y verificar que las condiciones iniciales constituyen un estado estacionario.
b) El controlador de nivel se debe ajustar para una respuesta de razón de asentamiento de un cuarto mediante ensayo y error. El controlador de composición se debe ajustar con el método de ganancia última de Ziegler-Nichols.
c) Se deben obtener las respuestas a entradas escalón en el punto de control de la composición y en cada una de las perturbaciones que se listan en el enunciado del problema. Los resultados se deben comentar brevemente.

**9-5.** En la figura 9-28 se muestra el diagrama de un evaporador de efecto triple con alimentación hacia adelante. Las condiciones de entrada y salida y cada uno de los efectos son iguales a los del problema 9-4; los coeficientes de transferencia de calor para cada uno de los efectos son 400, 300 y 130 Btu/h-pie²-°F, respectivamente. En las condiciones de diseño, existe una caída de presión de 1 psi en las líneas de vapor entre los efectos 1 y 2 y entre los efectos 2 y 3. Se puede suponer que esta caída de presión varía proporcionalmente respecto al cuadrado del flujo de vapor en la línea.

Además de los tres controladores de nivel y el controlador de la fracción de masa de producto, se instala un controlador con acción precalculada, con un compensador dinámico de adelanto/retardo para compensar los cambios en la composición de entrada.

a) Se deben escribir las ecuaciones del modelo y programarlas para su resolución en una computadora digital.
b) Se debe simular el arranque suponiendo que las concentraciones y temperaturas iniciales en los efectos son las de la alimentación, para ello se utilizarán los mismos parámetros de ajuste del controlador que se determinaron en el problema 9-4.

Nota: Para evitar el reajuste excesivo se necesita utilizar el reajuste por retroalimentación en el controlador PI (ver ejemplo 9-4) y limitar la salida del controlador a un rango entre 0 y 100%.

c) Se debe realizar la parte (c) del problema 9-4 para el evaporador de efecto múltiple, con las condiciones finales de estado estacionario de la parte (b) como condiciones iniciales; también se debe ajustar el controlador con acción precalculada. Los resultados se deben comentar brevemente.

**9-6.** Se debe vaporizar parcialmente una mezcla de benceno y tolueno mediante un tambor de evaporación calentado por vapor, como el que se ilustra en la figura 9-29.

En el tambor se deben procesar 20,000 lb/h de líquido saturado que contiene 40 mol% de benceno. El diámetro del tambor es de 5 pies; y la altura de 5 pies, normalmente se llena de líquido hasta la mitad; se dispone de vapor a 30 psia, saturado. Se debe diseñar un serpentín de calefacción con un coeficiente total de transferencia de calor de 200 Btu/h-pie²-°F, de manera que se tenga capacidad para evaporar la alimentación total a las condiciones de diseño; el serpentín se hará con tubo de acero de 2 pulgadas, catálogo 40.

a) Se debe diseñar un sistema de control para controlar la presión y el nivel del líquido en el tambor, así como la composición de la corriente de vapor. La interacción entre estos objetivos de control se debe minimizar.
b) Se deben escribir las ecuaciones del modelo, calcular las condiciones iniciales de estado estacionario, simular el tambor, ajustar los controladores y analizar el desempeño del sistema de control cuando hay variaciones en la razón de alimentación, de composición y de temperatura. Se puede suponer que la solución se rige por la Ley de Raoult.

**9-7.** La columna de destilación que se esquematiza en la figura 9-1 se alimenta con una mezcla de benceno y tolueno; en las condiciones de diseño, la razón de alimentación es de 3500 lbmol/h, la composición es de 44 mol% de benceno y es líquida en el punto de burbujeo. La columna se compone de seis bandejas de criba, cada una de las cuales contiene 450 lbmol de líquido y tiene una eficiencia de Murphree de 70%. La alimentación entra por la cuarta bandeja.

Se puede suponer que el rehervidor es una etapa de separación de equilibrio; éste tiene un coeficiente total de transferencia de calor de 350 Btu/h-pie²-°F y un área de transferencia de calor de 2000 pies². Se dispone de vapor saturado a 75 psia. El controlador del nivel de sedimentos (LIC202) es un controlador proporcional con banda proporcional del 100%. El transmisor de nivel (LT202) se calibra de manera que el líquido que se retiene en el rehervidor y el fondo de la columna es de 600 lbmol en el límite inferior y 1000 lbmol en el límite superior. El punto de control está en el 50% de este rango; la válvula de control para la producción de sedimentos es lineal y se dimensiona para una sobrecapacidad del 100% con retardo despreciable.

Se puede suponer que con el condensador la presión en la columna se mantiene constante a 1 atmósfera y el reflujo a su punto de burbujeo. La capacidad del tambor acumulador del condensador varía de 500 a 1500 lbmol de líquido entre los límites superior e inferior del transmisor de nivel (LT201). El controlador de nivel es proporcional con una banda proporcional de 100% y punto de control de 50% del rango. La válvula de control para el reflujo es lineal y se dimensiona para una sobrecapacidad de 100% con retardo despreciable.

A las condiciones de diseño, la composición del producto debe ser de 82 mol% de benceno y los sedimentos que se producen no deben contener más del 15% de benceno. La composición de los sedimentos se debe controlar mediante la manipulación del flujo de vapor al rehervidor, y la composición del destilado mediante la manipulación del flujo del mismo. Para dimensionar las válvulas de control se debe utilizar una razón de reflujo de 2.0.

a) Se deben diseñar dos circuitos de control de composición e incluir el rango de los transmisores, las dimensiones de las válvulas de control y los modos de los controladores. Se puede suponer que ambas composiciones se pueden medir continuamente con un retardo (de primer orden) de un minuto en los transmisores de composición, AT201 y AT202.
b) Se deben escribir las ecuaciones del modelo con la suposición de que el sobreflujo es equimolar; esto es, las razones de líquido y vapor no cambian de bandeja a bandeja. También se puede suponer que en cada bandeja la mezcla es perfecta, al igual que en el rehervidor y el tambor acumulador, y que las propiedades físicas son constantes. Para el benceno-tolueno se puede suponer que a la presión atmosférica la volatilidad relativa es constante a 2.43, es decir,
$$\frac{y^*(1 - x)}{x(1 - y^*)} = 2.43$$
donde $y^*$ es la fracción molar del benceno en el vapor, lo que está en equilibrio con el líquido de la fracción molar $x$.
c) Se debe simular el arranque de la columna con todas las bandejas, con el fondo y el tambor acumulador llenos inicialmente con un líquido de la misma composición y a la misma temperatura que el de alimentación.
d) Las condiciones finales de estado estacionario de la parte (c) se utilizan como condiciones iniciales para estudiar el desempeño del sistema de control con cambios en la razón de alimentación y fracción de mol y en los puntos de control de la composición. Los controladores de composición se deben ajustar mediante el método de síntesis de controladores.

Nota: Puede ser necesario hacer reiteraciones entre las partes (c) y (d) de este problema, ya que la simulación del arranque es una forma conveniente de calcular las condiciones de estado estacionario con el programa, mientras que los controladores se deben ajustar a las condiciones de operación de estado estacionario.

**9-8.** Se debe simular el horno del modelo que se hizo en la sección 9-3. El tubo del horno es de acero, de 4 pulgadas, catálogo 40, con una longitud de 120 pies. El fluido que se calienta es aire con una capacidad calórica de 6.96 Btu/lbmol-°F a presión constante, y de 4.98 Btu/lbmol-°F a volumen constante. El combustible es gas natural con un valor calórico de 990 Btu/pies³ (a 60°F, 30 pulg de Hg), y la eficiencia del horno es de 78%.

En las condiciones de diseño, la temperatura de entrada del aire es de 80°F, y su razón de flujo es 85 lbmol/h. El punto de control para la temperatura de salida es 1000°F. El coeficiente interno de transferencia de calor se puede suponer constante a 100 Btu/h-pie²-°F, y la emisividad de la superficie del tubo como constante a 0.75. La densidad del acero es 480 lb/pie³, y su calor específico 0.12 Btu/lb-°F. La masa efectiva del fogón es de 1750 lb, y su calor específico de 0.32 Btu/lb-°F.

Para el transmisor de temperatura (TT42 en la figura 9-5) se tiene un rango calibrado entre 500 y 1500°F y una constante de tiempo de 50 seg. En la válvula de control se tiene una caída de presión de diseño de 15 psi con características de porcentaje igual y parámetro de ajuste en rango de 50; se dimensiona para una sobrecapacidad del 100% con base en las condiciones de diseño. El tiempo de retardo del actuador de la válvula es despreciable.

Se debe dividir el tubo en 5, 10 y 20 secciones iguales en longitud y comparar los resultados de una respuesta sin control (Kc = 0) a un incremento del 10% en el flujo de aire, a partir de las condiciones iniciales de estado estacionario; entonces se utiliza el número de secciones con que se obtiene una precisión aceptable para ajustar el controlador de temperatura (TRC42 en la figura 9-5) y estudiar la respuesta del controlador a cambios escalón en el flujo de alimentación, la temperatura de entrada y el punto de control de la temperatura. La simulación del arranque se puede utilizar para obtener los perfiles de estado estacionario de temperatura del gas y del tubo, es decir, las condiciones iniciales.

**9-9.** Para el problema 9-8 se debe estudiar el desempeño de un controlador con acción precalculada bien ajustado, el cual consta de un compensador dinámico de ganancia y adelanto/retardo. Con el controlador de acción precalculada se mide el flujo de aire que entra al horno, y su salida se añade a la salida del controlador por retroalimentación.

**9-10.** El calentador de vapor de la figura 9-30 se utiliza para calentar una corriente en proceso que tiene una capacidad calórica de 4200 J/kg-°C y una densidad de 850 kg/m³. El calentador consta de 86 tubos dispuestos en dos pasos (43 tubos por paso). Los tubos son de cobre de 1 pulg (0.0254 m), calibre 18 (densidad = 8920 kg/m³, calor específico = 394 J/kg-°C), de 48 m de largo. El coeficiente de condensación del vapor se puede suponer lo suficientemente grande como para considerar que los tubos están a la misma temperatura del vapor que se condensa; la acumulación por condensación se puede despreciar. Se dispone de vapor saturado a 350 kN/m². El coeficiente interno de transferencia de calor es de 1400 J/s-m²-°C.

A las condiciones de diseño, se deben calentar 25 kg/seg del fluido que se procesa, de 60° a 80°C.

El sistema de control es un circuito en cascada en el cual el controlador de temperatura manipula el punto de control del controlador de presión en el casquillo. La presión en el casquillo es la presión de vapor del agua a la temperatura de condensación del vapor; se puede calcular mediante la ecuación de Antoine para agua (ver problema 9-4).

El rango de calibración del transmisor de temperatura (TT100) es de 50 a 150°C y el del transmisor de presión (PT100) es de 0 a 500 kN/m². El controlador de temperatura (TRC100) es proporcional-integral-derivativo (PID) y el de presión (PIC100) es proporcional-integral (PI). La válvula de control es de porcentaje igual, con un parámetro de ajuste en rango de 50 y se dimensiona para una sobrecapacidad del 100%, con base en las condiciones de diseño; la constante de tiempo del actuador es de 5 seg. La constante de tiempo del sensor de temperatura es de 35 seg y el retardo del sensor de presión es despreciable.

a) Se deben escribir las ecuaciones del modelo, para lo cual se divide el tubo de intercambio de calor en 10 secciones de longitud igual. Las ecuaciones se deben programar para su resolución en una computadora y, además, se debe simular el arranque para obtener los perfiles de diseño correspondientes a la temperatura de estado estacionario.
b) El controlador de presión se debe ajustar para un sobrepaso del 5%, mediante el método de síntesis del controlador; entonces se debe ajustar el controlador de temperatura para un IAE mínimo cuando entren perturbaciones. Se debe observar la respuesta a cambios del ±40% en el flujo del líquido que se procesa.
c) Se debe remover el controlador de presión; por lo tanto, la válvula se opera directamente con la salida del controlador de temperatura; en tales condiciones, se debe ajustar el controlador de temperatura como en la parte (b) y comparar los resultados.

**9-11.** En la recuperación de DMF (dimetil-formamida) de una solución acuosa mediante destilación, se utiliza un vaporizador para separar los componentes pesados que pueden obstruir la columna de destilación. El vaporizador se esboza en la figura 9-31. La alimentación consiste en 5-16% en peso de DMF, 1% de componentes pesados y el balance se completa con agua, la cual es el componente más volátil. En el líquido de purga quedan todos los componentes pesados, ya que no son volátiles; 4% del peso de la alimentación se purga en las condiciones de diseño. Para calentar el termosifón rehervidor se dispone de vapor saturado a 60 psia, y la razón de recirculación es lo suficientemente alta como para suponer que el contenido del vaporizador se mezcla perfectamente. A las condiciones de diseño, la razón de flujo de la solución que entra al vaporizador es de 2000 lb/h a 25°C y 10% en peso de DMF. A continuación se dan las características del equipo y las propiedades físicas; se puede considerar que el vapor está en equilibrio con el líquido.

- Volumen del vaporizador: se diseña para un tiempo de retención de 1 min, con base en la razón de alimentación.
- Área transversal: se diseña para una velocidad de vapor de 2.0 pies/seg
- Rehervidor: el coeficiente de ebullición de transferencia de calor (limitante) es de 240 Btu/h-pie²-°F; el área es de 150 pies²; los tubos son de acero de una pulgada, 16 BWG, y se puede considerar que están a la misma temperatura que el vapor que se condensa.
- Caída de presión del vaporizador a la columna: 0.5 psi, a las condiciones de diseño; proporcional al cuadrado del flujo del vapor. La columna se opera a la presión atmosférica.
- Controlador de nivel: proporcional con una banda proporcional del 100%.
- Transmisor de nivel: rango de 10 pulg con nivel de diseño a 50% del rango; el retardo es despreciable.
- Transmisor de la composición de purga: rango de 0 a 100 de porcentaje en peso; constante de tiempo de 45 seg.
- Controlador de la composición de la purga: proporcional-integral (PI) con un punto de control de 25% en peso de componentes pesados.
- Válvulas de control: se dimensionan para un 100% de sobrecapacidad; características lineales; el retardo del actuador es despreciable.

Propiedades físicas:

| | Agua | DMF | Componentes pesados |
|---|---|---|---|
| Peso molecular | 18 | 73 | 200 (prom) |
| Calor latente de vaporización a 25°C, Btu/lb | 1050 | 261 | - |
| Volatilidad relativa | 54.0 | 1.0 | 0 |
| Calor específico, Btu/lb-°F | Líquido | 1.0 | 0.53 | 0.45 |
| | Vapor | 0.46 | 0.36 | 0.90 |
| Gravedad específica del líquido | | 1.0 | 0.94 | - |

Se puede hacer el modelo del equilibrio vapor-líquido mediante la suposición de que la volatilidad relativa es constante y que la presión parcial del agua obedece la ley de Raoult. La presión de vapor del agua se puede determinar a partir de la ecuación de Antoine que se da en el problema 9-4.

a) Se deben escribir las ecuaciones del modelo, calcular las condiciones de diseño de estado estacionario y dimensionar el vaporizador. Las ecuaciones se programarán para su resolución en computadora y se verificará que con las condiciones iniciales se logra un estado estacionario.
b) Cada uno de los controladores se debe ajustar para una respuesta de razón de decaimiento de un cuarto, mientras se mantiene el otro en control manual. Se debe determinar la medida de interacción entre los dos circuitos (ver capítulo 8) y corregir los parámetros de ajuste, en caso de que sea necesario.
c) Se debe obtener la respuesta para cambios escalón en la razón de alimentación y composición (de los componentes pesados).

---

# Apéndice A: Símbolos y nomenclatura para los instrumentos

En este apéndice se presentan los símbolos y nomenclatura que se utilizan en los diagramas de instrumentación de este libro. La mayoría de las compañías tienen sus propios métodos y, aun cuando son muy semejantes entre sí, no son exactamente iguales. Los símbolos y nomenclatura que se utilizan aquí se apegan a la norma publicada por la Instrument Society of America (ISA); en este apéndice se presenta únicamente la información necesaria para este libro, pero si se desea profundizar más, se remite al lector a la norma de la ISA.

En general, la identificación de los instrumentos se conoce también como número de placa, y es de la forma:

**[Primera letra][Letras sucesivas]-[Número de circuito]**

Por ejemplo: **TIC-101**

- Primera letra: Variable medida
- Letras sucesivas: Función del instrumento
- Número de circuito: Identificación del lazo

En la tabla A-1 se da el significado de algunas de las letras.

```json
{
  "type": "table",
  "id": "table-A-01",
  "page": 628,
  "title": "Tabla A-1. Significado de las letras de identificación",
  "headers": ["Primera letra", "Variable", "Letras sucesivas", "Función"],
  "rows": [
    ["A", "Análisis", "A", "Alarma"],
    ["B", "Flama del quemador", "C", "Control"],
    ["C", "Conductividad", "E", "Elemento primario"],
    ["D", "Densidad o gravedad específica", "H", "Alto"],
    ["E", "Voltaje", "I", "Indicador"],
    ["F", "Razón de flujo", "K", "Estación de control"],
    ["H", "Mano (arranque manual)", "L", "Ligero o bajo"],
    ["I", "Corriente", "M", "Medio o intermedio"],
    ["J", "Potencia", "O", "Orificio"],
    ["K", "Tiempo o tabla de tiempos", "P", "Punto"],
    ["L", "Nivel", "R", "Registro o impresión"],
    ["M", "Humedad", "S", "Interruptor"],
    ["P", "Presión o vacío", "T", "Transmisión"],
    ["Q", "Cantidad o evento", "V", "Válvula, amortiguador o respiradero"],
    ["R", "Radiactividad o razón", "W", "Depósito"],
    ["S", "Velocidad o frecuencia", "Y", "Relevador o computador"],
    ["T", "Temperatura", "Z", "Manejo"],
    ["V", "Viscosidad", "", ""],
    ["W", "Peso o fuerza", "", ""],
    ["Y", "Posición", "", ""]
  ],
  "notes": "Tabla de identificación de instrumentos según norma ISA",
  "source": "Smith & Corripio, Control Automático de Procesos, Tabla A-1"
}
```

Los símbolos que se utilizan para designar la función de los relevadores se escriben generalmente cerca de la placa del instrumento. Algunos de los símbolos más comunes se presentan en la tabla A-2, y en la tabla A-3 se ilustra un resumen de otras abreviaturas especiales; para terminar, en la tabla A-4 se presentan los símbolos de los instrumentos.

```json
{
  "type": "table",
  "id": "table-A-02",
  "page": 629,
  "title": "Tabla A-2. Designación de funciones para relevadores",
  "headers": ["Símbolo", "Función"],
  "rows": [
    ["I-O o ENCENDIDO-APAGADO", "Dispositivo con dos posiciones"],
    ["C o SUMA", "Adición o substracción"],
    ["A o DIFF", "Substracción exclusiva de señales"],
    ["f", "Derivación"],
    ["AVG", "Promedio"],
    ["% o 1:3 o 2:1 (típico)", "Ganancia o atenuación (entrada-salida)"],
    ["×", "Multiplicación"],
    ["÷", "División"],
    ["√ o SQ. RT.", "Raíz cuadrada"],
    ["Xⁿ o X"**", "Elevación a una potencia"],
    ["f(x)", "Caracterización o generador de función"],
    ["1:1", "Multiplicador (Boost)"],
    [">", "Selección alta"],
    ["<", "Selección baja"],
    [">", "Límite superior"],
    ["<", "Límite inferior"],
    ["REV", "Reversa"],
    ["∫", "Integración (integral de tiempo)"],
    ["D o d/dt", "Derivación o razón"],
    ["UL", "Unidad de adelanto/retardo"],
    ["E/P o P/I (típico)", "Para secuencias de entrada/salida: E=Voltaje, I=Corriente, P=Neumático, H=Hidráulico, R=Resistencia, O=Electromagnético o sónico"],
    ["A/D o D/A", "A=Analógico, D=Digital"]
  ],
  "notes": "Símbolos para funciones de relevadores",
  "source": "Smith & Corripio, Control Automático de Procesos, Tabla A-2"
}
```

```json
{
  "type": "table",
  "id": "table-A-03",
  "page": 630,
  "title": "Tabla A-3. Resumen de abreviaturas especiales",
  "headers": ["Abreviatura", "Significado"],
  "rows": [
    ["A", "Analógico"],
    ["AS", "Suministro de aire"],
    ["D", "Control derivativo"],
    ["DIR", "Señal digital"],
    ["DEC", "Acción directa"],
    ["ES", "Decremento"],
    ["FC", "Suministro de electricidad"],
    ["FI", "Cerrado en falla"],
    ["FL", "Indeterminado en falla"],
    ["FO", "Bloqueado en falla"],
    ["GS", "Abierto en falla"],
    ["I", "Suministro de gas"],
    ["INC", "Señal de corriente"],
    ["M", "Interbloqueo"],
    ["NS", "Incremento"],
    ["P", "Actuador de motor"],
    ["R", "Suministro de nitrógeno"],
    ["REV", "Señal neumática"],
    ["RTD", "Control proporcional"],
    ["S", "Purga o dispositivo de desagüe"],
    ["S.P.", "Control de reajuste"],
    ["SS", "Resistencia"],
    ["T", "Acción inversa"],
    ["WS", "Detector de temperatura de resistencia"],
    ["", "Actuador de solenoide"],
    ["", "Punto de control"],
    ["", "Suministro de vapor"],
    ["", "Trampa"],
    ["", "Suministro de agua"]
  ],
  "notes": "Abreviaturas especiales utilizadas en instrumentación",
  "source": "Smith & Corripio, Control Automático de Procesos, Tabla A-3"
}
```

```json
{
  "type": "table",
  "id": "table-A-04",
  "page": 631,
  "title": "Tabla A-4. Símbolos generales de los instrumentos-significado",
  "headers": ["Símbolo", "Descripción"],
  "rows": [
    ["(1) Círculo con línea", "Montaje local o en campo"],
    ["(2) Círculo con línea horizontal", "Montaje en tablero o en cuarto de control"],
    ["(3) Círculo con línea diagonal", "Montaje detrás del tablero"],
    ["(4) Válvula de globo con actuador", "Válvula de control neumática"],
    ["(5) Válvula con posicionador", "Válvula de control con posicionador"],
    ["(6) Válvula de mariposa", "Válvula de mariposa, amortiguador o respiradero con operación neumática"],
    ["(7) Válvula manual", "Válvula de control de acción manual"],
    ["(8) Cilindro de acción simple", "Cilindro de acción simple"],
    ["(9) Cilindro de acción doble", "Cilindro de acción doble"],
    ["(10) Regulador reductor", "Regulador reductor de presión, independiente"],
    ["(11) Regulador de temperatura", "Regulador de temperatura del tipo sistema lleno"],
    ["(12) Válvula de alivio angular", "Válvula de alivio de presión o de seguridad, patrón angular"],
    ["(13) Válvula de alivio directa", "Válvula de alivio de presión o seguridad, patrón directo"],
    ["(14) Placa de orificio con dispersores", "Placa de orificio con dispersores de vena contracta, radiales o de tubo"],
    ["(15) Válvula de tres vías", "Válvula de tres vías, FO a trayectoria A-C"],
    ["(16) Placa de orificio con dispersores en el borde", "Placa de orificio con dispersores en el borde o en las esquinas"],
    ["(17) Placa de orificio conectada a transmisor", "Placa de orificio con dispersores de vena contracta, radiales o tubulares, conectada a un transmisor diferencial de presión"],
    ["(18) Tubo de venturi", "Tubo de venturi o tobera de flujo"],
    ["(19) Medidor de turbina", "Medidor de turbina"],
    ["(20) Medidor magnético", "Medidor magnético de flujo"],
    ["(21) Transmisor de nivel con flotador", "Transmisor de nivel con flotador externo o elemento de desplazamiento de tipo externo"],
    ["(22) Transmisor de nivel diferencial", "Transmisor de nivel con elemento del tipo diferencial de presión"],
    ["(23) Elemento de temperatura", "Elemento de temperatura sin depósito"],
    ["(24) Elemento de temperatura con depósito", "Elemento de temperatura con depósito"]
  ],
  "notes": "Símbolos generales para instrumentos según ISA",
  "source": "Smith & Corripio, Control Automático de Procesos, Tabla A-4"
}
```

En la figura A-1 se ilustra el ejemplo de un circuito de flujo; el elemento de flujo, FE-10, es una placa perforada con espitas en el borde. El elemento se conecta a un transmisor electrónico de flujo, FT-10; la salida del transmisor se envía a un extractor de raíz cuadrada, FY-10A, y de ahí la señal pasa a un controlador indicador de flujo, FIC-10. La señal de FY-10A también se envía a una alarma de flujo bajo, FLA-10. La salida del controlador se manda a un transductor I/P, FY-10B, para convertir la señal electrónica en neumática; entonces, la salida del transductor se envía a la válvula de control de flujo, FCV-10. El controlador y la alarma se montan en el tablero de instrumentos; mientras que el extractor de raíz cuadrada se monta detrás del panel; los demás instrumentos se montan en el campo de operación.

Nota: Con la finalidad de simplificar, en la mayoría de los diagramas de instrumentos del libro se omite la placa de identificación de la válvula de control; por la misma razón, también se omite la del elemento, y únicamente se muestra la del transmisor. El lector puede suponer que con la placa del transmisor se representa también el elemento.

## BIBLIOGRAFÍA

1. "Instrumentation Symbols and Identification," Instrument Society of America, Standard ISA-S5-1, Enero 31, 1975, Research Triangle Park, N.C.

---

# Apéndice B: Casos para estudio

En este apéndice se presenta una serie de casos de diseño para su estudio, con los cuales se da al lector la oportunidad de diseñar sistemas de control de proceso a partir del borrador. Cabe aclarar que el primer paso en el diseño de sistemas de control para plantas de proceso es decidir cuáles de las variables del proceso se deben controlar; tal decisión la deben de tomar, conjuntamente, el ingeniero de proceso que diseña el proceso y el ingeniero de control o de instrumentación que diseña el sistema de control y especifica la instrumentación. Esto implica un verdadero desafío y requiere un trabajo de equipo. El segundo paso es el diseño del sistema de control propiamente dicho; en los casos para estudio que siguen ya se realizó el primer paso, y el segundo es el tema de los presentes casos de estudio. El lector debe recordar que puede existir más de una forma para diseñar un sistema de control.

## Caso I. Sistema de control para una planta de granulación de nitrato de amonio

El nitrato de amonio es uno de los principales fertilizantes; en la figura B-1 se aprecia el proceso para su manufactura: Desde un tanque de alimentación se bombea una solución débil de nitrato de amonio (NH₄NO₃) a un evaporador; en la parte superior del evaporador hay un sistema de expulsión por vacío; el vacío se controla con el aire que entra al sistema. La solución concentrada se bombea a un tanque de agitación, y de ahí se alimenta a la parte superior de una torre de granulación (pulverización). El desarrollo de esta torre es uno de los más importantes en la industria de fertilizantes de la postguerra. En esta torre, la solución concentrada de NH₄NO₃ se lanza desde la parte superior contra una corriente de aire; el aire es suministrado mediante un ventilador situado en el fondo de la torre. Con el aire se enfrían las gotas de forma esférica y se elimina parte de la humedad, con lo cual quedan gránulos húmedos. Después, los gránulos se llevan a un secador rotatorio, donde se secan; entonces se enfrían y se llevan a un mezclador, donde se les añade un agente antiadherente (arcilla o tierra diatomácea) y se empacan para el embarque.

**A.** Se debe dibujar la instrumentación necesaria para:

1. Controlar el flujo de la solución débil de NH₄NO₃ al evaporador.
2. Controlar el nivel en el evaporador.
3. Controlar la presión en el evaporador, lo cual se puede lograr mediante el control del flujo de aire que va al tubo de salida del evaporador.
4. Controlar el nivel en el tanque de agitación.
5. Controlar la temperatura de los gránulos secos que salen del secador.
6. Controlar la densidad de la solución fuerte que sale del evaporador.

Se debe tener la seguridad de que se ilustran todas las alarmas necesarias y que se especifica la acción de todas las válvulas y controladores.

**B.** ¿Cómo se puede controlar la razón de producción de esta unidad?

**C.** Si la producción de esta unidad varía frecuentemente, tal vez también sea conveniente variar el flujo de aire que pasa por la torre de granulación. ¿Cómo se puede lograr esto?

**D.** Uno de los circuitos de difícil ajuste es el de la temperatura de los gránulos secos, por ello se obtuvieron los siguientes datos mediante cambios de +10% en la salida del controlador de temperatura:

| Tiempo (min) | Temperatura (°F) |
|--------------|------------------|
| 0 | 200 |
| 1 | 200 |
| 3 | 202 |
| 5 | 208 |
| 6.5 | 214 |
| 8.5 | 218 |
| 11.0 | 220 |
| 13.0 | 222 |
| 15.0 | 221.8 |
| 17.0 | 223.0 |

El transmisor de temperatura de este circuito tiene un rango de 100 a 300°F. Se debe ajustar un controlador PI mediante el método de síntesis de un controlador, y un controlador PID mediante el método de IAE mínimo.

**Bibliografía**
1. The Foxboro Co. Application engineering data AEC 288-3, Enero, 1972.

## Caso II. Sistema de control para la deshidratación de gas natural

Ahora se considera el proceso que aparece en la figura B-2. El objetivo de este proceso es deshidratar el gas natural que entra al absorbedor, lo cual se logra mediante el empleo de un deshidratante líquido (glicol). El glicol se introduce por la parte superior del absorbedor y fluye hacia abajo, en sentido contrario al gas, a la vez que recoge la humedad del gas. El glicol pasa del absorbedor a un intercambiador de calor y al separador; en el rehervidor, que se encuentra en la base del separador, se extrae la humedad del glicol, la cual se elimina en forma de vapor (de agua). Este vapor sale por la parte superior del separador, se condensa y se utiliza como agua de reflujo, la cual se utiliza para condensar los vapores de glicol que de otra manera saldrían junto con el vapor de agua.

El ingeniero que diseñó el proceso decidió que se debe controlar lo siguiente:

1. El nivel del líquido en el fondo del absorbedor.
2. El reflujo de agua en el separador.
3. La presión en el separador.
4. La temperatura en el tercio superior del separador.
5. El nivel de líquido en el fondo del separador.
6. La operación eficiente del absorbedor con diferentes cargas de producción.

Dibujar el diagrama de instrumentación completo donde aparezca la instrumentación necesaria para lograr el control que se desea. La instrumentación que se debe emplear es electrónica (4-20 mA), con excepción de las válvulas.

## Caso III. Sistema de control para la fabricación de blanqueador de hipoclorito de sodio

El hipoclorito de sodio (NaOCl) se forma por:

$$2NaOH + Cl_2 \rightarrow NaOCl + H_2O + NaCl$$

En el diagrama de flujo de la figura B-3 se ilustra el proceso para una manufactura, la cual es de la forma siguiente.

Se prepara constantemente sosa diluida (NaOH), a una concentración fija, mediante dilución en agua. La solución de sosa diluida se almacena en un tanque intermedio, de éste se bombea al reactor de hipoclorito; para la reacción se inyecta cloro en forma de gas en el reactor.

**A.** Se debe preparar un diagrama detallado de instrumentos para lograr lo siguiente:

1. Controlar el nivel en el tanque de dilución.
2. Controlar el proceso de dilución de la solución cáustica; la concentración de esta corriente se puede medir mediante una celda de conductividad, cuando disminuye la dilución en la solución, aumenta la salida de la celda.
3. Controlar el nivel en el tanque de depósito del blanqueador.
4. Controlar la razón de exceso de NaOH/Cl₂ disponible en la corriente que sale del reactor. Esta razón se mide mediante una técnica de POR (potencial de óxido-reducción), cuando la razón se incrementa, también se incrementa la señal POR.

Se debe tener la seguridad de que se muestran todas las alarmas, registros e indicadores necesarios. Toda la instrumentación (con excepción de las válvulas) es electrónica (4-20 mA). Se debe especificar la acción de las válvulas y los controladores y comentar brevemente el diseño.

**B.** ¿Cómo se puede fijar la razón de producción de esta unidad?

**C.** Por razones de seguridad, cuando no hay flujo de solución de sosa diluida del tanque al reactor, también se debe detener el flujo del cloro; se debe diseñar el control para tal fin y explicarlo.

**D.** Se debe explicar detalladamente, con un ejemplo numérico, cómo se ajustaría el controlador POR mediante el procedimiento de prueba escalón, y de qué manera se ajustaría un controlador PI por medio del método de IAE mínimo.

**BIBLIOGRAFÍA**
1. The Foxboro Co. Application engineering data, Enero de 1972.

## Caso IV. Sistema de control en el proceso de refinación del azúcar

Las unidades de proceso que se muestran en la figura B-4 forman parte del proceso para refinar azúcar. El azúcar cruda se alimenta al proceso a través de un transportador de tornillo y se rocía agua sobre ésta para formar un jarabe, el cual se calienta en el tanque de disolución, de donde fluye al tanque de preparación, en el cual se realiza un mayor calentamiento y la mezcla. Del tanque de preparación el jarabe se envía al tanque de mezclado; conforme el jarabe fluye hacia el tanque de mezclado, se le añade ácido fosfórico y, ya en el tanque, cal. Este tratamiento con ácido, cal y calor tiene dos objetivos: el primero es la clarificación, es decir, con el tratamiento se coagulan y precipitan el color de azúcar cruda. Después del tanque de mezclado se continúa el proceso del jarabe.

Se piensa que es importante controlar las siguientes variables.

1. Temperatura en el tanque de disolución.
2. Temperatura en el tanque de preparación.
3. Densidad del jarabe que sale del tanque de preparación.
4. Nivel en el tanque de preparación.
5. Nivel en el tanque de ácido al 50%; el nivel en el tanque de ácido al 75% se puede suponer constante.
6. La fuerza del ácido al 50%; la fuerza del ácido al 75% se puede suponer constante.
7. El flujo de jarabe y ácido al 50% que entran al tanque de mezclado.
8. El pH de la solución en el tanque de mezclado.
9. La temperatura en el tanque de mezclado.
10. En el tanque de mezclado se requiere únicamente una alarma de nivel alto.

Los medidores de flujo que se utilizan en el proceso son magnéticos. La unidad de densidad que se utiliza en la industria azucarera es el °Brix, la cual equivale aproximadamente al porcentaje, por peso, de sólidos de azúcar en la solución.

Se deben diseñar los sistemas de control necesarios para controlar todas las variables anteriores. ¿Cómo se controlaría la razón de producción? El diseño se debe comentar brevemente y se debe ilustrar la acción de las válvulas de control y de los controladores, así como las alarmas necesarias.

## Caso V. Eliminación de CO₂ de gas de síntesis

Ahora se considera el proceso que se muestra en la figura B-5 para eliminar el CO₂ del gas de síntesis. En la planta se tratan 1646.12 MSCFH de gas que se alimenta. El gas de alimentación se suministra a 1526°F y 223 psig, con la siguiente composición:

| Componente | Volumen (%) |
|------------|-------------|
| Hidrógeno | 50.29 |
| Nitrógeno | 0.16 |
| Dióxido de carbono | 5.60 |
| Monóxido de carbono | 9.94 |
| Metano | 2.62 |
| Vapor de agua | 31.39 |

Los productos de esta planta deben ser:
1. Gas de síntesis a 115°F y 600 psig con una composición volumétrica máxima de 50 ppm de CO.
2. CO₂ a 115°F y 325 psig.

El proceso es el siguiente: el gas de alimentación se introduce en la planta a 1526°F y 223 psig; para eliminar el CO, el gas se debe enfriar a 105°F antes de entrar al absorbedor. El enfriamiento se hace en cuatro etapas: primera, el gas de alimentación se pasa a través de un supercalentador (E-15) y una caldera (E-14), y con el calor que se le extrae se produce una presión media de vapor de 27,320 lb/h. Segunda, el gas de alimentación se pasa a través de un economizador (E-24) y se calienta el agua desmineralizada antes de la aireación. Tercera, el gas de alimentación se pasa a través de un rehervidor (E-11), en el cual el gas proporciona el 84% del rendimiento del rehervidor en operación completa. Finalmente, en el intercambiador de calor (E-12), el gas de alimentación se enfría con el agua de enfriamiento de la planta. Mediante estas cuatro etapas se recupera 75% de los Btu extraídos del gas para las necesidades de calentamiento del proceso.

Los gases ya fríos entran a contracorriente al absorbedor (C-6), donde se separa el CO₂ del gas con etanolamina (MEA). Los gases restantes se comprimen en una compresión centrífuga de dos etapas (B-1A y B); el compresor se acciona mediante una turbina de vapor (M-1). Después del enfriamiento de los gases entre etapas, y a la salida (E-7A y B) se utilizan tambores de expulsión (C-12A y B) para separar cualquier condensación.

El compresor opera con vapor a presión media, del cual el 68% se obtiene de la caldera alimentada por el gas. Noventa y tres por ciento del vapor de baja presión queda disponible para su utilización en la planta, y el 7% restante se utiliza para calentar uno de los rehervidores (E-10) de la columna de regeneración (C-7).

El CO₂ se lleva junto con la MEA al regenerador (C-7), donde se separa de la MEA. El regenerador se opera a baja presión y alta temperatura, con lo cual se provoca que el CO₂ se libere junto con el agua en forma de vapor y salga por la parte superior de la torre, mientras que la MEA recircula (P-1) nuevamente al absorbedor. Antes de que la MEA entre a la parte superior del absorbedor, se pasa por cuatro intercambiadores de calor (E-1, E-2, E-3 y E-4) donde se intercambia en forma cruzada con los sedimentos del absorbedor, mediante lo cual se recuperan 8.8 MM Btu/h; de los intercambiadores, la MEA pasa a través de otro enfriador (E-5) y, finalmente, se introduce al absorbedor.

Los gases de CO₂ que salen del regenerador se comprimen en un compresor de dos etapas (B-2 y 3) accionado mediante motores eléctricos. Los enfriadores entre cada etapa y el de salida (E-9A y B) se proveen con tambores de expulsión (C-13A y B).

En la tabla B-1 se tienen las condiciones de las corrientes que aparecen con número en el diagrama de flujo.

El ingeniero de proceso piensa que se deben controlar las siguientes variables:

1. Temperatura del vapor sobrecalentado que sale de E-15.
2. Presión del vapor sobrecalentado que se produce en E-14/E-15.
3. Nivel en la caldera.
4. Presión en el eliminador de aire.
5. Nivel en el eliminador de aire.
6. Flujo de vapor de ajuste a baja presión para el eliminador de aire.
7. Temperatura del gas de alimentación que sale de E-13 y pasa al rehervidor E-11.
8. Temperatura del gas de alimentación en el absorbedor C-6.
9. Flujo de MEA al absorbedor C-6.
10. Temperatura en el tercio inferior de C-6.
11. Nivel en el regenerador C-7.
12. Temperatura en el fondo del regenerador C-7.
13. Temperatura de los gases de CO₂ que salen de E-8.
14. Presión en el área del regenerador.
15. Temperatura del gas de síntesis entre las dos etapas del compresor y la temperatura de salida.
16. Presión del gas de síntesis que sale del compresor B-1.
17. Temperatura entre las etapas y a la salida de los gases de CO₂ cuando pasan a través del compresor B-2.
18. Nivel en todos los tambores de expulsión.

Probablemente éstos no son todos los circuitos de control que se necesitan para una operación uniforme, sin embargo, son los primeros que propone el ingeniero de proceso; el lector puede proponer además los suyos.

(a) El lector debe diseñar los circuitos de control anteriores y además los que crea necesarios. Se debe especificar la acción de las válvulas y los controladores.
(b) Se deben especificar las válvulas de retención y de bloqueo necesarias, así como las alarmas e indicadores de proceso que se estimen necesarios.

## Caso VI. Proceso del ácido sulfúrico

En la figura B-6 se ilustra el diagrama de flujo simplificado para la manufactura de ácido sulfúrico (H₂SO₄).

El azufre se carga en un tanque de fundición donde se mantiene en estado líquido; de ahí pasa a un quemador, donde reacciona con el oxígeno del aire y se produce SO₂ mediante la siguiente reacción:

$$S_{(l)} + O_{2(g)} \rightarrow SO_{2(g)}$$

Del quemador, los gases pasan a través de una caldera de valor residual, donde se produce vapor mediante la recuperación del calor de la reacción anterior. De la caldera, los gases pasan a través de un convertidor catalítico de cuatro etapas (reactor), en el cual tiene lugar la siguiente reacción:

$$SO_{2(g)} + 1/2 O_{2(g)} \rightleftharpoons SO_{3(g)}$$

Del convertidor, los gases se envían a una columna de absorción, donde los gases de SO₃ se absorben con H₂SO₄ diluido (93%); el agua del H₂SO₄ reacciona con el SO₃ y se produce H₂SO₄:

$$H_2O_{(l)} + SO_{3(g)} \rightarrow H_2SO_{4(l)}$$

El líquido que sale del absorbedor, H₂SO₄ concentrado (98%), pasa a un tanque de circulación, donde se diluye de nuevo al 93% con H₂O. Parte del líquido de este tanque se utiliza entonces como medio de absorción en el absorbedor.

**A.** Se piensa que es importante controlar las siguientes variables.

1. Nivel en el tanque de fundición.
2. Temperatura del azufre en el tanque de fundición.
3. Aire que entra al quemador.
4. Nivel de agua en la caldera de calor residual.
5. Concentración de SO₃ en el gas que sale del absorbedor.
6. Concentración de H₂SO₄ en el tanque de disolución.
7. Nivel en el tanque de disolución.
8. Temperatura de los gases que entran a la primera etapa del convertidor.

Se deben diseñar los sistemas de control necesarios para lograr lo anterior y tener la seguridad de que se muestra toda la instrumentación con la especificación de la acción de las válvulas y los controladores. El diseño se debe comentar brevemente.

**B.** ¿Cómo se podría fijar la razón de producción en esta planta?

---

# Apéndice C: Sensores, transmisores y válvulas de control

En este apéndice se presenta parte del equipo físico necesario en la construcción de sistemas de control, y se relaciona estrechamente con el capítulo 5. Se examinan algunos de los sensores más comunes -de presión, de flujo, de nivel y de temperatura-, así como dos tipos diferentes de transmisores; uno neumático y otro electrónico. Al final del apéndice se presentan los diferentes tipos de válvulas de control y consideraciones adicionales para el dimensionamiento de las mismas.

## SENSORES DE PRESIÓN

El sensor de presión más común es el **tubo de Bourdon**, desarrollado por el ingeniero francés Eugene Bourdon, y el cual se ilustra en la figura C-1; consiste básicamente en un tramo de tubo en forma de herradura, con un extremo sellado y el otro conectado a la fuente de presión. Debido a que la sección transversal del tubo es elíptica o plana, al aplicar una presión el tubo tiende a enderezarse, y al quitarla, el tubo retorna a su forma original, siempre y cuando no se rebase el límite de elasticidad del material del tubo. La cantidad de enderezamiento que sufre el tubo es proporcional a la presión que se aplica, y como el extremo abierto del tubo está fijo, entonces el extremo cerrado se puede conectar a un indicador, para señalar la presión; o a un transmisor, para generar una señal neumática o eléctrica.

El rango de presión que se puede medir con el tubo de Bourdon depende del espesor de las paredes y del material con que se fabrica el tubo. Posteriormente se desarrolló una versión extendida del tubo de Bourdon en forma de helicoide para dar más movimiento al extremo sellado; este elemento se denomina hélice y se ilustra en la figura C-2. Con la hélice se pueden manejar rangos de presión de aproximadamente 10:1, con una exactitud de ±1% de la escala calibrada. Otro tipo común de tubo de Bourdon es el elemento espiral que se muestra en las figuras C-2d y C-3.

Otro tipo de sensor de presión es el **fuelle**, el cual se ilustra en las figuras C-2c y C-4, el cual semeja una cápsula corrugada hecha de algún material elástico, por ejemplo, acero inoxidable o latón; al aumentar la presión, el fuelle se expande (o se contrae), y cuando disminuye, se contrae (o expande). La cantidad de expansión o contracción es proporcional a la presión que se aplica. Un sensor semejante al de fuelle es el de **diafragma** que se muestra en las figuras C-2b y C-5; cuando se incrementa la presión en el proceso, el centro del diafragma se comprime; la cantidad de movimiento es proporcional a la presión que se aplica.

## SENSORES DE FLUJO

El flujo es una de las dos variables de proceso que se miden más frecuentemente, la otra es la temperatura; en consecuencia, se han desarrollado muchos tipos de sensores de flujo. En esta sección se tratan los más utilizados y se mencionan algunos otros; en la tabla C-1 aparecen varias características de algunos de los sensores comunes.

Probablemente el sensor de flujo más popular es el **medidor de orificio**, que es un disco plano con un agujero, como se muestra en la figura C-6. El disco se inserta en la línea de proceso, perpendicular al movimiento del fluido, con objeto de producir una caída de presión, $\Delta P$, la cual es proporcional a la razón de flujo volumétrico a través del orificio. Las ecuaciones para los medidores de flujo de orificio de precisión son complejas, y se presentan en diversas referencias bibliográficas; sin embargo, probablemente en la mayoría de las instalaciones se utiliza la siguiente ecuación simple:

$$q = C\sqrt{\frac{\Delta P}{\rho}} \quad (C-1)$$

donde:
- $q$ = razón de flujo
- $\Delta P$ = caída de presión a través del orificio
- $C$ = coeficiente del orificio
- $\rho$ = densidad del fluido

En las referencias bibliográficas también se indica cómo calcular el diámetro del orificio que se requiere, el cual generalmente varía entre el 10 y el 75% del diámetro del tubo.

Generalmente, la caída de presión a través del orificio se mide con:

1. **Espitas laterales**, figura C-7, las cuales son las más comunes. La técnica consiste en medir la caída de presión en las cejas con que se sostiene al orificio en la línea de proceso.
2. **Espitas de vena contracta**, figura C-8; se indica la caída de presión más grande.
3. Otros tipos en los que se incluyen espitas radiales, angulares y de línea; éstos no son tan populares como los dos anteriores.

La que se coloca antes del orificio se conoce como espíta de alta presión, y la que se coloca después del orificio se denomina espíta de baja presión. En la mayor parte de las espitas el diámetro varía entre 1/4 y 1/2 de pulg. La caída de presión que se mide es función de la ubicación de la espíta y de la razón de flujo.

Se deben enfatizar varios puntos acerca de la utilización de los medidores de orificio para medir flujos; el primero es que la señal que sale de la combinación orificio/transmisor es la caída de presión a través del orificio, no el flujo. Para medir la caída de presión a través del orificio se utiliza un sensor diferencial de presión, figura C-9. En la ecuación C-1 se observa que la caída de presión se relaciona con el cuadrado del flujo, o:

$$\Delta P = \frac{\rho q^2}{C^2} \quad (C-2)$$

En consecuencia, si se desea el flujo, entonces se debe obtener la raíz cuadrada de la caída de presión; en el capítulo 8 se presenta la instrumentación necesaria para hacer lo anterior, sin embargo, varios fabricantes ofrecen la opción de instalar una unidad de extracción de raíz cuadrada junto con el transmisor y, en este caso, la señal que sale del transmisor se relaciona de manera lineal con el flujo volumétrico. Un punto en el que se debe hacer énfasis es que no toda la caída de presión que se mide es pérdida por el fluido en proceso, sino que una cierta cantidad la recupera el fluido en los siguientes tramos de la tubería, conforme se restablece el régimen del flujo. Por último, el alcance en rango del medidor de orificio, la razón del flujo máximo y mínimo que se puede medir, es de casi 3:1, como se indica en la tabla C-1. Es importante saber esto, ya que así se conoce la exactitud que se puede esperar cuando el proceso se ejecuta con cargas altas o bajas.

Existen varias causas posibles para evitar la utilización de los sensores de orificio, algunas de ellas es que no exista suficiente presión para crear una caída de presión, como en el caso del flujo por gravedad y el flujo de fluidos corrosivos, con sólidos en suspensión que puedan bloquear el orificio, o fluidos cercanos a la presión de vapor saturado que puedan sufrir un cambio rápido cuando se sujetan a una caída de presión, en estos casos se requiere otro tipo de sensor para medir el flujo.

Otro tipo común de sensor es el **medidor magnético de flujo**, que se ilustra en la figura C-10. El principio de operación de este elemento es la ley de Faraday; es decir, cuando un material conductor (un fluido) se mueve en ángulo recto a través de un campo magnético, se induce un voltaje, el cual es proporcional a la intensidad del campo magnético y a la velocidad del fluido. Si la intensidad del campo magnético es constante, entonces el voltaje únicamente es proporcional a la velocidad del fluido; además, la velocidad que se mide es la velocidad promedio y, por lo tanto, este sensor se puede utilizar para los dos regímenes: laminar y turbulento. Para la calibración de este medidor de flujo se debe tomar en cuenta el área de la sección transversal del tubo, de manera que con la electrónica que se asocia al medidor sea posible calcular el flujo volumétrico; por tanto, la salida se asocia linealmente con la razón de flujo volumétrico.

Puesto que con él no se restringe el flujo, el medidor magnético de flujo es un dispositivo con caída de presión cero que se puede utilizar para medir flujo por gravedad, flujos con variaciones rápidas y flujo de fluidos próximos a su presión de vapor. Sin embargo, en el fluido se debe tener un mínimo de conductividad de aproximadamente 10 µohm/cm², por lo cual el medidor no es apropiado para medir ni gases ni hidrocarburos líquidos.

En la tabla C-1 se observa que el ajuste en rango del medidor magnético del flujo es de 30:1, el cual es significativamente mayor que el de los medidores de orificio, pero su costo también es mayor. La diferencia en costo aumenta conforme se incrementa el tamaño de la tubería que se utiliza en el proceso.

Finalmente, una consideración importante en la aplicación y mantenimiento de los medidores magnéticos de flujo es el recubrimiento de los electrodos, el cual representa otra resistencia eléctrica, de lo que resultan lecturas erróneas; los fabricantes ofrecen técnicas tales como los limitadores ultrasónicos para mantener los electrodos limpios.

Otro medidor de flujo importante es el **medidor de turbina** que se ilustra en la figura C-11. Es uno de los más precisos de que se dispone comercialmente. Su principio de funcionamiento se basa en un rotor que se hace girar con el flujo del líquido; la rotación de las aspas se detecta mediante una bobina de colección magnética, la cual emite pulsos a una frecuencia que es proporcional a la razón de flujo volumétrico; este pulso se convierte en una señal equivalente de 4-20 mA, de manera que se pueda utilizar con instrumentación electrónica estándar, el convertidor o transductor es generalmente parte integral del medidor. Uno de los problemas que más comúnmente se asocia con los medidores de turbina es el de los cojinetes (rodamientos), por lo que se requiere que los líquidos sean limpios y con algunas propiedades lubricantes.

Hasta aquí se estudiaron tres de los medidores de flujo que se utilizan más comúnmente en la industria de proceso, aunque existen muchos otros tipos, que van desde el rotámetro, toberas de flujo, tubos de venturi, tubos pitot y anubares, los cuales se han utilizado durante muchos años, hasta los desarrollados más recientemente, como son los medidores de vórtice, los ultrasónicos y los medidores de remolino. Por falta de espacio no se tratan estos medidores, pero si desea estudiarlos, se remite al lector a las abundantes referencias bibliográficas que aparecen al principio de esta sección.

## SENSORES DE NIVEL

Los tres medidores de nivel más importantes son el de diferencial de presión, el de flotador y el de burbujeo. El método de **diferencial de presión** consiste en detectar la diferencia de presión entre la presión en el fondo del líquido y en la parte superior del líquido, la cual es ocasionada por el peso que origina el nivel del líquido. Este sensor se ilustra en la figura C-12. El extremo con que se detecta la presión en el fondo del líquido se conoce como extremo de alta presión, y el que se utiliza para detectar la presión en la parte superior del líquido, como extremo de baja presión. Una vez que se conoce el diferencial de presión y la densidad del líquido, se puede obtener el nivel. En la figura C-12 se muestra la instalación del sensor de diferencial de presión en recipientes abiertos y cerrados; si los vapores en la parte superior del líquido no son condensables, entonces la tubería de baja presión, que también se conoce como derivación húmeda, puede estar vacía; sin embargo, si los vapores se condensan, entonces la derivación húmeda se debe llenar con un líquido sellador apropiado. Si la densidad del líquido varía, entonces se debe utilizar alguna técnica de compensación.

Con el **sensor de flotador** se detecta el cambio en la fuerza de empuje sobre un cuerpo sumergido en el líquido. Este sensor se instala generalmente en un ensamble que se monta de manera externa al recipiente, como se muestra en la figura C-13. La fuerza que se requiere para mantener al flotador en su lugar es proporcional al nivel del líquido y se convierte en una señal en el transmisor. Este tipo de sensor es menos caro que la mayoría de los otros sensores de nivel; sin embargo, su mayor desventaja estriba en la incapacidad para cambiar el cero y la escala; para cambiar el cero se requiere la reubicación de la cápsula completa.

El **sensor de burbujeo** es otro tipo de sensor de presión hidrostática, y consiste, como se muestra en la figura C-14, en un tubo con gas inerte que se sumerge en el líquido; el aire o gas inerte que fluye a través del tubo se regula para producir una corriente continua de burbujas, y la presión que se requiere para producir esta corriente continua es una medida de la presión hidrostática o nivel del líquido.

Existen otros métodos nuevos para medir el nivel en los tanques, algunos de éstos son patrones de capacitancia, sistemas ultrasónicos y sistemas de radiación nuclear; los dos últimos sensores también se utilizan para medir el nivel en materiales sólidos. Para ampliar este estudio se recomiendan las referencias bibliográficas que se citan al principio de esta sección.

## SENSORES DE TEMPERATURA

La temperatura, junto con el flujo, es la variable que con mayor frecuencia se mide en la industria de proceso; una razón simple es que casi todos los fenómenos físicos se ven afectados por ésta. La temperatura se utiliza frecuentemente para inferir otras variables del proceso; dos de los ejemplos más comunes son las columnas de destilación y los reactores químicos. Comúnmente, en las columnas de destilación se utiliza la temperatura para inferir la pureza de una de las corrientes existentes; en los reactores químicos la temperatura se utiliza como un indicador de la extensión de la conversión o reacción.

A causa de los múltiples efectos que se producen con la temperatura, se han desarrollado numerosos dispositivos para medirla; con muy pocas excepciones, los dispositivos caen en cuatro clasificaciones generales, como se observa en la tabla C-2. Termómetros de cuarzo, conos pirométricos y pinturas especializadas son algunos de los sensores que no entran en la clasificación de la tabla C-2. En la tabla C-3 se muestran algunas características de los sensores típicos.

Con los **termómetros de vidrio con líquido** se indica el cambio de temperatura que causa la diferencia entre el coeficiente de temperatura de expansión del vidrio y del líquido que se utiliza; los líquidos que se utilizan más ampliamente son mercurio y alcohol. Los termómetros de mercurio que se fabrican con vidrio ordinario son útiles entre -35°F y 600°F, el límite inferior se debe al punto de congelación del mercurio y el superior a su punto de ebullición. Si el espacio que queda arriba del mercurio se llena con un gas inerte, generalmente nitrógeno, para evitar la ebullición, el rango útil se puede extender hasta los 950°F; tales termómetros llevan generalmente la inscripción de "llenado con nitrógeno" ("nitrogen filled"). Para temperaturas por debajo del punto de congelación del mercurio (-38°F) se debe emplear otro líquido; para temperaturas abajo de -80°F se utiliza ampliamente el alcohol; para temperaturas hasta de -200°F se utiliza pentano, y tolueno para temperaturas abajo de -200°F.

Los **termómetros de tira bimetálica** trabajan con base en el principio de que los metales se expanden con la temperatura y que los coeficientes de expansión no son los mismos para todos los metales; en la figura C-15 se ilustra un termómetro de tira bimetálica típico. El elemento sensitivo a la temperatura se compone de dos metales diferentes que se unen en una tira, el coeficiente de expansión de uno de los metales es alto, y el del otro es bajo; una combinación corriente es el invar (64% Fe, 36% Ni), cuyo coeficiente es bajo, y la aleación de níquel-hierro, cuyo coeficiente es alto. Generalmente la expansión con la temperatura es baja, y por esta razón la tira bimetálica se enrolla en forma de espiral; conforme la temperatura se incrementa, la espiral tiende a combarse hacia el lado del metal con bajo coeficiente térmico.

En la figura C-16 se muestran los elementos de un **termómetro de sistema lleno** típico; el líquido del sistema se expande o se contrae con las variaciones de temperatura, lo cual se detecta mediante el resorte de Bourdon y se transmite a un indicador o transmisor. A causa de la simplicidad de su diseño, confiabilidad, bajo costo relativo y seguridad inherente, estos elementos son populares en la industria de proceso. La Scientific Apparatus Manufacturers' Association (SAMA) estableció cuatro clases principales de sistemas llenos, con subclasificaciones, las cuales se listan en la tabla C-4. Las diferencias más significativas entre las clasificaciones son el líquido que se utiliza y la compensación de las diferencias de temperatura entre el bulbo, la capilaridad y el resorte de Bourdon; en la figura C-17 se muestran varios de estos sistemas llenos. Para una descripción más extensa de dichos sistemas se remite al lector a las referencias bibliográficas 2 y 3.

Los **termómetros de dispositivos resistivos (TDR)** son elementos que se basan en el principio de que la resistencia eléctrica de los metales puros se incrementa con la temperatura y, ya que la resistencia eléctrica se puede medir con bastante precisión, esto proporciona un medio para medir la temperatura con mucha exactitud. Los metales que se utilizan más comúnmente son platino, níquel, tungsteno y cobre. En la figura C-18 se muestra el esquema de un TDR típico.

Para la lectura de la resistencia y, en consecuencia, también para la de temperatura generalmente se utiliza un puente de Wheatstone. En la figura C-19 se ilustra el sistema de los puentes de dos y tres hilos que se utilizan.

Con los **elementos termistores** se detectan cambios muy leves de temperatura. Los termistores se fabrican con la combinación sinterizada de material cerámico y alguna clase de óxido metálico semiconductor, como níquel, manganeso, cobre, titanio o hierro. En los termistores se tiene un coeficiente de resistividad térmica muy negativo, o algunas veces positivo. En la figura C-20 se ilustran algunos termistores típicos. Los puentes de Wheatstone de la figura C-19 se utilizan generalmente para medir la resistencia y, por lo tanto, también la temperatura. Algunas de las ventajas son el tamaño pequeño y el bajo costo; sus principales desventajas estriban en que la relación de la temperatura contra la resistencia no es lineal, así como el hecho de que generalmente se requieren líneas de fuerza blindadas.

El último elemento de temperatura que se estudiará es el **termopar**, el cual es el sensor de temperatura industrial más conocido. El principio de funcionamiento del termopar lo descubrió T. J. Seebeck, en 1821; en el efecto de Seebeck, o principio de Seebeck, se establece que hay un flujo de corriente eléctrica en un circuito de dos metales diferentes si las dos uniones están a temperaturas diferentes. En la figura C-21 se muestra el esquema de un circuito simple; M1 y M2 son los dos metales, $T_1$ es la temperatura a medir, y $T_2$ es la temperatura que generalmente se conoce como de unión fría o de referencia. El voltaje que se produce con este efecto termoeléctrico depende de la diferencia de temperatura entre las dos uniones y los metales que se utilicen; en la figura C-22 se muestran los voltajes que se generan con metales típicos. En la figura C-23 se ilustra un esquema más realista de un circuito de medición. Los tipos más comunes de termopares son platino-platino/rodio, cobre-constantan, hierro-constantan, cromel-alumel y cromel-constantan. En la figura C-24 se muestra el ensamblaje de un termopar industrial; el tubo de protección, que también se conoce como depósito térmico, no es necesario en todas las instalaciones; con el depósito térmico se tiende a hacer más lenta la respuesta del sistema sensor. Para un estudio más detallado de los termopares se recomiendan ampliamente las referencias bibliográficas 2 y 3.

## SENSORES DE COMPOSICIÓN

Otra clase importante de sensores son los de composición, los cuales se utilizan en las mediciones y control de calidad de producto. Existen muchos tipos diferentes de sensores de medición, por ejemplo, los de densidad, viscosidad, cromatografía, pH y POR. Debido a la falta de espacio no se presentan estos sensores, sin embargo, se desea que el lector esté consciente de su importancia; se proporcionan referencias bibliográficas para lectura y aprendizaje.

## TRANSMISORES

En esta sección se presentan los ejemplos de un transmisor neumático y de uno eléctrico. El objetivo es presentar al lector los principios de funcionamiento de estos transmisores típicos. Como se mencionó anteriormente en este apéndice, el propósito del transmisor es convertir la salida de un sensor en una señal lo suficientemente intensa como para que se pueda transmitir a un controlador o cualquier otro dispositivo receptor. En general, la mayoría de los transmisores se pueden dividir en dos tipos: de balance de fuerzas y de movimiento-balance, los cuales son los más comunes y se utilizan extensamente en la industria.

### Transmisor neumático

En todos los transmisores neumáticos se utiliza un arreglo de mariposa y boquilla para producir una señal de salida proporcional a la salida del sensor. Para ilustrar los principios de funcionamiento se utilizará un transmisor de diferencial de presión, el cual es de balance de fuerza y se ilustra en la figura C-25.

La cápsula de diafragma gemelo es el sensor con que se detecta la diferencia de presión entre el lado de alta y el lado de baja presión. Ya anteriormente se vio que este tipo de sensor se utiliza para medir el nivel de un líquido y el flujo. El diafragma se une a una barra de fuerza mediante una conexión flexible; la barra de fuerza se conecta al cuerpo del transmisor mediante un diafragma de acero inoxidable, el cual sirve como sello de la cavidad de medición y también como un apoyo firme para la barra de fuerza. La parte superior de la barra de fuerza se conecta a la barra de rango mediante una tira de flexión; la barra de rango se apoya en la rodaja de rango. En la parte inferior de la barra de rango se encuentra un diafragma de retroalimentación y un ajuste a cero. Arriba de la barra de rango se encuentra un arreglo de mariposa-boquilla y un relevador neumático y, como se observa, la mariposa se conecta a la combinación de barra de fuerza y barra de rango.

Cuando en la cápsula del diafragma se detecta una diferencia de presión, se crea una tensión o fuerza en la parte inferior de la barra de fuerza; más específicamente, se puede suponer que la presión en la parte superior se incrementa, con lo que se crea una fuerza que tira de la barra de fuerza, de lo cual resulta un movimiento en el extremo externo de la barra, con lo que la mariposa se acerca a la boquilla, en cuyo caso se incrementa la salida del relevador y con ello se incrementa la fuerza que se ejerce sobre la barra de rango mediante el diafragma de retroalimentación. Con esta fuerza se balancea la fuerza del diferencial de presión presente en la cápsula de diafragma; del balance de estas fuerzas resulta la señal de salida del transmisor, la cual es proporcional a la diferencia de presión.

El suministro de presión que se recomienda para la mayoría de los instrumentos neumáticos es entre 20 y 25 psig, ya que con éste se asegura el funcionamiento adecuado con un nivel de salida de 15 psig. Para calibrar estos instrumentos se requiere ajustar el cero y la escala (o rango); en el instrumento de la figura C-25 esto se hace mediante un tornillo externo de ajuste a cero y con la rodaja de rango.

En los párrafos precedentes se describió el principio de trabajo de un instrumento neumático típico. Como se mencionó al principio, en todos los instrumentos neumáticos se utiliza alguna clase de arreglo de boquilla-mariposa para producir una señal de salida, la cual es una técnica confiable y simple con la que se ha tenido éxito durante muchos años.

### Transmisor electrónico

En la figura C-26 se muestra el diagrama simplificado de un transmisor electrónico de diferencial de presión del tipo movimiento-balance y se utilizará para ilustrar los principios de trabajo de la instrumentación electrónica típica.

Con un incremento en el diferencial de presión se accionan los diafragmas del elemento de medición y se desarrolla una fuerza con la que se mueve la parte inferior de la barra de fuerza hacia la izquierda. Este movimiento se transfiere a la unidad de medición de la fuerza de deformación a través de un alambre de conexión; en la unidad de medición de la fuerza de deformación se tienen cuatro medidores de fuerza que se conectan en configuración puente; con el movimiento de la barra de fuerza se causa un cambio de resistencia en los medidores de fuerza, mediante el cual se produce una señal diferencial proporcional al diferencial de presión que entra, misma que se aplica a las entradas del amplificador de entrada; un lado de la señal se aplica directamente a la entrada del amplificador con inversión, y el otro a la entrada sin inversión, a través de una red de cero, con la cual se obtiene el ajuste a cero del transmisor.

Con la señal que sale del amplificador de entrada se maneja al regulador de corriente de salida, por medio del cual se controla la corriente de salida del transmisor a través de la red de escala y el circuito sensor de corriente de salida. Con la red de escala se obtiene el ajuste de escala del transmisor; la señal de esta red se retroalimenta al circuito de entrada mediante un amplificador con almacenamiento (buffer) y se utiliza para controlar la ganancia del circuito de entrada. Si la corriente de salida del transmisor se incrementa más allá de 20 mA C.D., el voltaje que pasa a través de la resistencia de detección de corriente activa el limitador de corriente de salida, con el cual se limita la salida.

## TIPOS DE VÁLVULAS DE CONTROL

Existen muchos tipos diferentes de válvulas de control en el mercado, casi cada mes se ofrece una "nueva" válvula de control "mejorada" y, en consecuencia, es difícil clasificarlas, sin embargo, aquí se clasificarán en dos categorías principales: de vástago recíproco y de vástago rotatorio.

### Vástago recíproco

En la figura C-27 se muestra una válvula de control de vástago recíproco típica, que en particular se conoce como **válvula de globo con asiento sencillo y vástago deslizable**. Las válvulas de globo son una familia de válvulas que se caracteriza por una parte de cierre que viaja en línea perpendicular al asiento de la válvula, y se utilizan principalmente para propósitos de estrangulamiento y control de flujo en general. En la figura C-27 también se muestran en detalle los diferentes componentes de la válvula; se observa que la válvula se divide en dos áreas generales: el **actuador** y el **cuerpo**. El actuador es la parte de la válvula con que se convierte en movimiento mecánico la energía que entra a la válvula para aumentar o disminuir la restricción de flujo. En la figura C-28 se muestra una válvula de globo con asiento doble y vástago deslizable, con las cuales se pueden manejar presiones de proceso altas; sin embargo, si se requiere un cierre extremo, generalmente se utilizan válvulas de asiento sencillo, ya que con las de doble asiento cerradas se tiende a tener mayor escurrimiento que con las de asiento sencillo.

Otro tipo de válvula que se utiliza comúnmente es la de **cuerpo separable** que se muestra en la figura C-29. Se utiliza frecuentemente en líneas de proceso donde se requiere cambiar con frecuencia el oclusor y el asiento para evitar la corrosión.

Las **válvulas de jaula**, que se ilustran en la figura C-30, el oclusor tiene pasajes internos.

Las **válvulas de tres vías**; éstas se ilustran en la figura C-31 y son también de tipo recíproco. Las válvulas de tres vías pueden ser convergentes o divergentes y, en consecuencia, con ellas se puede separar una corriente en dos o se pueden mezclar dos corrientes en una sola. Comúnmente se utilizan para propósito de control.

Existen algunos otros tipos de válvulas de control con vástago recíproco, la mayoría de ellas se utilizan en servicios especializados. Algunas de éstas son la válvula estilo Y, la cual se utiliza comúnmente en servicio de fundición de metales o criogénico; la válvula de apriete o diafragma, que posee alguna parte flexible, por ejemplo, un diafragma que se puede mover junto con, o abrir, o cerrar el área de flujo y comúnmente se utiliza con fluidos altamente corrosivos, suspensiones y líquidos de alta viscosidad, así como en operaciones de procesamiento de alimentos tales como la elaboración de cerveza y vino. La válvula de compuerta es otro tipo de válvula de vástago recíproco que se utiliza principalmente en servicios donde se necesite una abertura o un cierre completo, sin embargo, por lo regular no se emplea en servicios de estrangulamiento.

### Vástago rotatorio

Existen varios tipos usuales de válvulas de vástago rotatorio; uno de los más comunes es la **válvula de mariposa** que se ilustra en la figura C-32. Estas válvulas constan de un disco que gira alrededor de un eje; se requiere mínimo espacio para su instalación, y se tiene alta capacidad de flujo con caída de presión mínima; se utilizan en servicios de baja presión. Con los discos convencionales se logra controlar el estrangulamiento hasta en 60 grados de giro, pero con discos de nueva patente se puede controlar el estrangulamiento para un giro completo de 90 grados.

Otra válvula común de vástago rotatorio es la **válvula de esfera** que se ilustra en la figura C-33. Con estas válvulas también se logra una alta capacidad de flujo con caída mínima de presión; se utilizan comúnmente para manejar suspensiones o materiales fibrosos; la tendencia a escurrimiento es baja y su tamaño es pequeño.

Hasta aquí se presentó una breve introducción a varios tipos de válvulas de control, sin embargo, éstas no son las únicas; en el mercado existe un gran número de válvulas para cubrir los requerimientos de servicios especializados, así como de seguridad y de otros tipos de regulaciones.

## ACCIONADOR DE LA VÁLVULA DE CONTROL

Como se definió previamente, el accionador (o actuador) es la parte de la válvula de control con que se convierte la energía de entrada, ya sea neumática o eléctrica, en movimiento mecánico para abrir o cerrar la válvula.

### Accionador de diafragma con operación neumática

Éstos son los accionadores más usuales en la industria de proceso. En la figura C-34 se muestra un accionador de diafragma típico; estos accionadores consisten en un diafragma flexible que se coloca entre dos compartimientos; una de las cámaras resultantes de este arreglo debe ser hermética. A la fuerza que se genera con el accionador se opone un resorte de "rango". La señal neumática del controlador entra a la cámara hermética, y con el incremento o decremento de presión se produce una fuerza que se utiliza para vencer la fuerza del resorte de rango del accionador y las del interior del cuerpo de la válvula.

La acción de la válvula, CF o AF, se determina mediante el accionador. En la figura C-34a se muestra una válvula cerrada en falla o aire para abrir, y en la figura C-34b se muestra una válvula abierta en falla o de aire para cerrar.

El tamaño del accionador depende de la presión del proceso contra la cual se debe mover el vástago y de la presión de aire de que se dispone; el rango de presión de aire más común es de 3 a 15 psig, pero también se utilizan rangos de 6 a 30 y de 3 a 27 psig. Estos accionadores de diafragma son de construcción simple, confiables y económicos. El fabricante proporciona las ecuaciones para dimensionar los accionadores.

### Accionador de pistón

Normalmente, los accionadores de pistón se utilizan cuando se requiere máxima confiabilidad junto con una respuesta rápida, lo cual generalmente ocurre cuando es alta la presión de proceso contra la que se trabaja. Estos accionadores operan con un suministro de aire a alta presión, de más de 150 psig. Los mejores diseños son de acción doble, con el fin de brindar máxima confiabilidad en ambos sentidos.

### Accionadores electrohidráulicos y electromecánicos

Aunque no son tan usuales como los dos tipos anteriores, en el futuro el uso de accionadores electrohidráulicos y electromecánicos se hará más común debido a la utilización creciente de señales eléctricas de control. Dichos accionadores se muestran en las figuras C-35 y C-36; requieren energía eléctrica para el motor y una señal eléctrica desde el controlador.

Dentro de esta familia de accionadores, probablemente el más común es el de solenoide. Se puede utilizar una válvula de solenoide para accionar un accionador de pistón de doble acción; mediante la formación o ruptura de una señal de corriente eléctrica se conmuta con el solenoide la salida de una bomba hidráulica para que se conecte a la parte superior o inferior del accionador de pistón. Con esta unidad se obtiene un control preciso sobre la posición de la válvula.

### Accionador manual con volante

Estos accionadores se utilizan cuando no se requiere control automático; en el mercado existen modelos tanto para vástago recíproco como para vástago rotatorio. En la figura C-37 se muestra un accionador de volante típico.

## ACCESORIOS DE LA VÁLVULA DE CONTROL

Existen varios dispositivos que se conocen como accesorios y que generalmente se asocian con las válvulas de control, en esta sección se presenta una breve introducción a algunos de estos accesorios, los más comunes.

### Posicionadores

Un posicionador es un dispositivo cuya acción es muy semejante a la de un controlador; su función es comparar la señal del controlador con la posición del vástago de la válvula. Si el vástago no está en la posición que indica el controlador, con el posicionador se añade o elimina aire de la válvula hasta que se logra la posición correcta; es decir, cuando es importante posicionar el vástago de la válvula con precisión, normalmente se utiliza un posicionador. En la figura C-38 se muestra una válvula con un posicionador donde se aprecia el arreglo de barra de acoplamiento mediante el cual se detecta la posición del vástago en el posicionador. En la figura C-33 se muestra otro posicionador.

Con la utilización de los posicionadores se tiende a minimizar los efectos de:

1. Retardo en los accionadores de gran capacidad.
2. Fricción del vástago debida a cajas de empaque justas.
3. Fricción debida a fluidos viscosos o pegajosos.
4. Cambios de presión en la línea de proceso.

Se recomienda un posicionador cuando la respuesta de la combinación válvula-posicionador es mucho más rápida que el proceso mismo; algunos circuitos de control en que se da este caso son los de nivel de líquido, de temperatura, de concentración y de flujo de gas. Los de flujo y los de presión de líquido son algunos circuitos rápidos en los que se puede eliminar la utilización de posicionadores.

Generalmente, los posicionadores son neumáticos o electroneumáticos. En los neumáticos se recibe una señal neumática como entrada y se emite una señal neumática hacia la válvula; en los electroneumáticos se recibe una señal eléctrica como entrada (1-5 V, 4-20 mA o 10-50 mA) y se emite una señal neumática hacia la válvula. Con los posicionadores también se puede determinar la acción de las válvulas de control (CF o AF).

### Multiplicadores

Los multiplicadores (boosters), que también se conocen como relevadores de aire, se utilizan con los accionadores de las válvulas para acelerar la respuesta de la válvula a un cambio de señal proveniente de un controlador o transductor con baja capacidad de salida. También se debe hacer notar que para los circuitos de control de respuesta rápida, tales como los de flujo o presión de líquidos, en los cuales no es indicada la utilización de posicionadores, la utilización de multiplicadores puede ser la elección adecuada.

Para los multiplicadores se tienen otros posibles usos:

1. Amplificación de una señal neumática; algunas razones típicas de amplificación son 1:2 y 1:3.
2. Reducción de una señal neumática, cuyas razones típicas son 5:1, 2:1 y 3:1.
3. Inversión de una señal neumática, lo cual significa que, conforme se incrementa la señal de entrada, disminuye la señal de salida. Cuando la señal de entrada es de 3 psig, la de salida es de 15 psig; cuando la señal de entrada es de 15 psig, la señal de salida es de 3 psig.

### Interruptores de límite

Estos interruptores se montan a un lado de las válvulas y se disparan mediante la posición del vástago. Con estos interruptores generalmente se manejan alarmas, válvulas de solenoide, luces o cualquier otro de tales dispositivos.

## VÁLVULAS DE CONTROL, CONSIDERACIONES ADICIONALES

En esta sección se presentan varias consideraciones adicionales que se deben tomar en cuenta cuando se dimensiona y elige la válvula de control; por tanto, con esta sección se complementa la sección 5-2.

En las figuras C-39a hasta C-39d se muestran ejemplos de catálogos de fabricantes (Masoneilan y Fisher Controls). Una vez que se calcula el coeficiente $C_V$ mediante las ecuaciones del capítulo 5, se utilizan esas cantidades para determinar las dimensiones de la válvula.

### Correcciones de viscosidad

En la ecuación (5-1) no se considera el efecto de la viscosidad del líquido al calcular el coeficiente $C_V$. Para la mayoría de los servicios de líquidos se puede despreciar la corrección de viscosidad, sin embargo, en algunos otros casos esto puede conducir a errores de dimensionamiento.

Masoneilan propone que se calcule un $C_V$ turbulento y uno laminar y que se utilice como valor mayor el $C_V$ que se requiere.

**Flujo turbulento:**
$$C_V = q\sqrt{\frac{G_f}{\Delta P}} \quad (C-3a)$$

**Flujo laminar:**
$$C_V = \left(\frac{q}{2.13}\right)^{2/3}\left(\frac{\mu}{\Delta P}\right)^{1/3} \quad (C-3b)$$

donde:
- $\mu$ = viscosidad, centipoises

En Fisher Controls se desarrolló una nomografía y un procedimiento con el cual se puede obtener el factor de corrección $F_V$ que es posible aplicar al coeficiente $C_V$ normal para determinar el coeficiente corregido, $C_{V_c}$. En la figura C-40 se muestra la nomografía con las instrucciones para su uso; cuando ya se ha obtenido el factor de corrección, entonces el coeficiente corregido se calcula como sigue:

$$C_{V_c} = F_VC_V \quad (C-4)$$

### Vaporización instantánea y cavitación

El hecho de que en la válvula de control exista vaporización instantánea o cavitación, o ambas, puede tener efectos significativos sobre la operación de la válvula y el procedimiento de dimensionamiento. Es importante comprender el significado e importancia de estos dos fenómenos; en la figura C-41 se muestra el perfil de presión de un líquido que fluye a través de un elemento restrictivo (posiblemente una válvula de control).

Para mantener el flujo en estado estacionario la velocidad del líquido se debe incrementar conforme disminuye el área de la sección transversal para el flujo. La velocidad máxima del líquido se alcanza en un punto inmediatamente posterior al área mínima de la sección transversal (el área de puerto para una válvula de control); el punto de máxima velocidad se conoce como "vena contracta", en este punto se tiene también la presión más baja en el líquido. Lo que ocurre es que el incremento de velocidad (energía cinética) se acompaña por un incremento en la "energía de presión", la energía se transforma de una forma a otra.

Cuando el líquido pasa por la vena contracta, su velocidad disminuye, y entonces se recupera parte de la presión. Las válvulas tales como las de mariposa, de esfera o la mayoría de las válvulas rotatorias tienen características de recuperación de presión altas; en cambio, en las válvulas de vástago recíproco esta característica es baja. En las válvulas de vástago recíproco la trayectoria del flujo es más tortuosa que en las válvulas rotatorias y, por lo tanto, la caída de presión del líquido es mayor a través de esas válvulas que en las de tipo rotatorio.

Ahora se utiliza nuevamente la figura C-41 y se supone que la presión de vapor del líquido a la temperatura de flujo es $P_v$; cuando la presión del líquido cae abajo de esta presión $P_v$, parte del líquido empieza a cambiar de la fase líquida a la de vapor, es decir, el líquido se evapora instantáneamente (flashea). Con la vaporización instantánea se pueden producir serios daños por erosión en el oclusor de la válvula y en el asiento, como se muestra en la figura C-42.

Además del daño físico que se ocasiona a la válvula, la vaporización instantánea tiende a disminuir la capacidad de flujo en la válvula. Conforme se empiezan a formar burbujas, esto tiende a causar una "condición de obstrucción" en la válvula, con lo cual se limita el flujo; además, esta condición de obstrucción puede agravarse al grado de ocasionar "bloqueo" del flujo a través de la válvula; es decir, más allá de esta condición de bloqueo, el incremento en la caída de presión en la válvula no dará por resultado un incremento en el flujo. Es importante reconocer que con la ecuación de la válvula, ecuación (5-3), no se describe esta condición. Conforme se incrementa la caída de presión, con la ecuación se predicen razones de flujo más altas; dicha relación se muestra gráficamente en la figura C-43, junto con la condición de bloqueo de flujo.

En esta figura se observa que para el ingeniero es importante conocer la caída máxima de presión, $\Delta P_{perm}$, la cual es efectiva para producir el flujo. Los fabricantes eligieron indicar esta caída máxima de presión mediante una ecuación para $\Delta P_{perm}$; con caídas de presión superiores a esta $\Delta P_{perm}$ se puede ocasionar un bloqueo del flujo. $\Delta P_{perm}$ depende en mucho no sólo del fluido, sino también del tipo de válvula. Varios fabricantes han realizado investigaciones tendientes a obtener datos y desarrollar una ecuación para predecir $\Delta P_{perm}$; Masoneilan propone la siguiente ecuación:

$$\Delta P_{perm} = C_f^2(P_1 - F_FP_v) \quad (C-5)$$

donde:
- $P_v$ = presión de vapor del líquido, en psia
- $C_f$ = factor de flujo crítico
- $P_1$ = presión de entrada, en psia
- $F_F$ = 0.96 - 0.28$\sqrt{P_v/P_c}$
- $P_c$ = presión crítica del líquido, en psia

En la figura C-44 se muestra el factor de flujo crítico para diferentes tipos de válvulas, $C_f$; estos valores son el resultado de pruebas de flujo sobre las válvulas.

Fisher Controls propone la siguiente ecuación:

$$\Delta P_{perm} = C_f^2(P_1 - r_cP_v) \quad (C-8)$$

donde:
- $C_f$ = coeficiente de recuperación de la válvula
- $r_c$ = razón de presión crítica

El coeficiente $C_f$ depende del tipo de válvula y también es un resultado de las pruebas de flujo. En la última columna de las figuras C-39c y C-39d se muestran los valores de $C_f$ para cada tipo particular de válvula. El término $r_c$ se determina con base en la figura C-45.

Si la recuperación de presión que experimenta el líquido es suficiente como para elevar la presión por arriba de la presión de vapor del líquido, entonces las burbujas de vapor se empiezan a colapsar o a implosionar, lo cual se conoce como "cavitación". La energía que se libera durante la cavitación produce ruido, como si fluyera grava a través de la válvula; en la figura C-46 se muestra el daño típico que se produce en la válvula al desprenderse material por efecto de la cavitación. Ciertamente, en las válvulas de vástago rotatorio, cuya recuperación de presión es alta, se tiende a experimentar cavitación más frecuentemente que en las válvulas de vástago recíproco, las cuales poseen recuperación baja de presión.

Con las pruebas se ha demostrado que, en las válvulas con recuperación de presión baja, el bloqueo de flujo y la cavitación se presentan aproximadamente a la misma $\Delta P$ y, en consecuencia, las ecuaciones (C-5) y (C-8) también se pueden utilizar para calcular la caída de presión a la cual comienza la cavitación. En las válvulas con alta recuperación de presión, la cavitación puede ocurrir a caídas de presión por abajo de $\Delta P_{perm}$; para estos tipos de válvulas, Masoneilan propone la siguiente ecuación:

$$\Delta P_{cav} = K_c(P_1 - P_v) \quad (C-9)$$

donde:
- $K_c$ = coeficiente de cavitación incipiente, el cual se muestra en la figura C-44

Fisher Controls propone la misma ecuación y sus términos $K_c$ se muestran en la figura C-47.

Los fabricantes de válvulas producen dispositivos especiales anticavitación con los que se tiende a incrementar el camino del flujo de la válvula y, por lo tanto, la caída de presión a la cual ocurre la cavitación.

## RESUMEN

En este breve apéndice se tuvo como propósito familiarizar al lector con algunos de los instrumentos que se utilizan comúnmente en los circuitos de control de proceso. Entre la instrumentación que se expone se incluye parte de los instrumentos que se necesitan para medir (M) las variables del proceso (elementos primarios) tales como flujo, temperatura y presión. Se presentaron dos tipos de transmisores y se expusieron sus principios de funcionamiento. Finalmente, también se presentaron algunos tipos muy comunes de válvulas (elementos finales de control) que se utilizan para ejecutar la acción (A), junto con sus características de flujo.

Como se mencionó en la primera frase de este resumen, éste es un apéndice breve. En este libro es imposible presentar y abordar todos los detalles que se relacionan con los diferentes tipos de instrumentos, pero existen manuales completos y colecciones muy exhaustivas de artículos disponibles para este fin. Se remite al lector a la bibliografía que aparece al final de este apéndice. Además de los numerosos tipos diferentes de instrumentos de que se dispone en la actualidad, cada mes se introducen al mercado nuevos y "mejorados" tipos de elementos primarios, transmisores y elementos finales de control. En el área de elementos primarios se desarrollan constantemente nuevos sensores con los que se puede medir variables difíciles con más exactitud, más frecuente y más rápidamente, por ejemplo, la concentración. En el área de transmisores, la última palabra son los "transmisores inteligentes".

Con estos transmisores de hoy en día, en los que se utilizan microprocesadores, se puede entregar la información a los controladores en una forma más comprensible. La de los elementos finales de control es otra área de investigación en la que existe mucha actividad; no solamente se mejoran continuamente las válvulas neumáticas de control, sino que ahora se desarrollan y mejoran los actuadores eléctricos para lograr la interconexión con otros componentes electrónicos, como son los controladores y las computadoras. Además, están en desarrollo otros elementos finales de control, tales como los manejadores para bombas y ventiladores de velocidad variable, cuya razón de desarrollo es la conservación de energía. A causa de la falta de espacio no se presenta en este libro la factibilidad y la justificación para utilizar estos ventiladores y bombas de velocidad variable en la regulación del flujo, sin embargo, el lector puede consultar las referencias bibliográficas 21, 22, 23 y 24 para estudiar este tema.

Ciertamente, en los últimos párrafos, el lector se dará cuenta que se llevan a cabo investigaciones, principalmente por parte de los fabricantes, en el área de instrumentación, cuyos resultados permitirán una mejor medición y un mejor control. Esta es una razón por la cual el control es un campo tan dinámico.

## BIBLIOGRAFÍA

1. Ryan, J. B., "Pressure Control," *Chemical Engineering*, Febrero 3, 1975.
2. Liptak, Bela G., Ed., *Instrument Engineers' Handbook*, Vol. 1, Process Measurement, Chilton Book Co., Nueva York.
3. Considine, D. M., Ed., *Process Instruments and Controls Handbook*, McGraw-Hill Book Co., Nueva York, 1957.
4. Considine, D. M., Ed., *Handbook of Instrumentation and Controls*, McGraw-Hill Book Co., Nueva York, 1961.
5. Smith, C. L., "Liquid Measurement Technology," *Chemical Engineering*, Abril 3, 1978.
6. Zientara, Dennis E., "Measuring Process Variables," *Chemical Engineering*, Septiembre 11, 1972.
7. Kern, R., "How to Size Flowmeters," *Chemical Engineering*, Marzo 3, 1975.
8. "Handbook Flowmeter Orifice Sizing," Handbook No. 10B9000, Fischer Porter Co., Warminster, Pa.
9. Spink, L. K., "Principles and Practice of Flow Meter Engineering," The Foxboro Co., Foxboro, Mass.
10. Kern, R., "Measuring Flow in Pipes with Orifices and Nozzles," *Chemical Engineering*, Febrero 3, 1975.
11. Wallace, L. M., "Sighting in on Level Instruments," *Chemical Engineering*, Febrero 16, 1976.
12. "Process Control Instrumentation," Publicaciones de la Foxboro Co. 105A-15M-4/71, Foxboro, Mass.
13. Taylor Instrument Co., "Differential Pressure Transmitter Manual, IB-12B215."
14. "Control Valve Handbook," Fisher Controls Co., Marshalltown, Iowa.
15. "Masoneilan Handbook for Control Valve Sizing," Masoneilan International, Inc., Norwood, Mass.
16. "Fisher Catalog 10," Fisher Controls Co., Marshalltown, Iowa.
17. Casey, J. A., and D. Hammitt, "How to Select Liquid Flow Control Valves," *Chemical Engineering*, Abril 3, 1978.
18. Chalfin, S., "Specifying Control Valves," *Chemical Engineering*, Octubre 14, 1974.
19. Kern, R., "Control Valves in Process Plants," *Chemical Engineering*, Abril 14, 1975.
20. Hutchison, J. W., Ed., "ISA Handbook of Control Valves," Instrument Society of America.
21. Fischer, K. A., y D. J. Leigh, "Using Pumps for Flow Control," *Instruments and Control Systems*, Marzo, 1983.
22. Jarc, D. A., y J. D. Robechek, "Control Pump with Adjustable Speed Motors Save Energy," *Instruments and Control Systems*, Mayo 1981.
23. Pritchett, D. H., "Energy-Efficient Pump Drive," *Chemical Engineering Progress*, Octubre 1981.
24. Baumann, H. D., "Control Valve VS. Variable Speed Pump," *Chemical Engineering*, Junio 24, 1981.
25. Utterback, V. C., "Online Process Analyzers," *Chemical Engineering*, Junio 21, 1976.
26. Foster, R., "Guidelines for Selecting Outline Process Analyzers," *Chemical Engineering*, Marzo 17, 1975.
27. Ottmers, D. M., et al., "Instruments for Environmental Monitoring," *Chemical Engineering*, Octubre 15, 1979.
28. Creason, S. C., "Selection and Care of pH Electrodes," *Chemical Engineering*, Octubre 23, 1978.

---

# Apéndice D: Programa de computadora para encontrar raíces de polinomios

El programa que se lista en la figura D-1 se puede utilizar directamente para encontrar todas las raíces, reales y complejas, de un polinomio. En dicho programa se utiliza la subrutina MULLER, con la cual se calculan las raíces mediante el método de Müller, con base en la interpolación cuadrática de Lagrange; para una descripción completa del método de Müller el lector debe consultar la bibliografía original de Müller o el texto de Conte y de Boor.

Mientras que el programa principal y la subrutina POLY son específicos para encontrar raíces de polinomios, la subrutina MULLER es general; con ella se pueden encontrar las raíces reales y complejas de cualquier función no lineal, y no necesariamente de un polinomio; en ésta se utiliza la subrutina DEFLAT para reducir numéricamente el polinomio o función, como en la ecuación (2-51), lo cual es una operación que se conoce como deflación y con ella se asegura que no se obtendrá la misma raíz más de una vez, con excepción del caso de raíces repetidas.

En el programa principal se introduce el grado del polinomio y sus coeficientes, en potencias ascendentes de X, y de ahí se pasan a la subrutina POLY, mediante una declaración COMMON; también se introducen el número máximo de reiteraciones por raíz, la tolerancia relativa de error y las aproximaciones iniciales a las raíces, y se pasan a la subrutina MULLER mediante sus argumentos. Müller recomienda fijar las aproximaciones iniciales a las raíces en cero, de manera que las raíces se encuentren en orden creciente de magnitud; aunque esto da por resultado una aproximación más precisa de las raíces, no siempre se encuentran éstas en orden creciente.

En este programa se define la tolerancia relativa de error como la diferencia máxima que se permite entre dos aproximaciones sucesivas de una raíz, dividida entre la magnitud de la misma; por ejemplo, con un valor de 10⁻⁶ se asegura que las dos aproximaciones sucesivas concuerdan en 6 dígitos significativos, independientemente de la magnitud de la raíz.

### Datos de entrada

**Primera línea:** NDEG, MAXIT, RTOL
donde:
- NDEG es el grado del polinomio
- MAXIT es el número máximo de iteraciones que se permite por raíz
- RTOL es la tolerancia relativa de error

**Segunda línea:** A(I), I = 1, NDEG + 1
donde:
- A(I) son los coeficientes del polinomio, en orden ascendente de potencias de $x$, esto es:
$$p(x) = A(1) + A(2)x + A(3)x^2 + \ldots + A(NDEG + 1)x^{NDEG}$$

**Tercera línea:** XS(I), I = 1, NDEG
donde:
- XS(I) son las aproximaciones iniciales a las raíces

Después de que se resuelve cada problema, el programa se regresa al inicio para leer los datos de otro caso. Para detener la ejecución se introduce un valor cero en NDEG.

**Formato.** El formato de los datos de entrada es libre, es decir, las cantidades para cada línea se introducen y separan por espacios o comas. El programa se escribe con señales de entrada (prompts) para que se pueda usar en forma interactiva desde una terminal de tiempo compartido.

**Resultados.** Los resultados consisten en una repetición de los datos de entrada y las aproximaciones finales a las raíces, las cuales aparecen en dos columnas, una para las partes reales y otra para las imaginarias.

**Precaución.** Generalmente se imprime una pequeña parte imaginaria en raíces reales, debido a inexactitudes numéricas; si en varios órdenes de magnitud la parte imaginaria es menor que la parte real, se debe descartar. De manera similar, la parte real se debe descartar si es menor en varios órdenes de magnitud que la parte imaginaria.

**Funciones de la unidad de salida.** A causa de la estructura de tiempo compartido, con el programa se escribe cada línea dos veces, una en la unidad 6, la cual se supone que es la terminal, y otra en la unidad 4 para impresión en papel. Para la utilización en lote (batch), se debe eliminar una de las dos instrucciones WRITE.

**Ejemplo.** Los datos de entrada para encontrar las raíces de la siguiente ecuación polinómica:

$$s^5 + 4s^4 + 16s^3 + 25s^2 + 48s + 36 = 0$$

con 50 reiteraciones por raíz, tolerancia de error relativa de 10⁻⁵ y cero aproximaciones iniciales son:

**Primera línea:** 5, 50, 1E-5
**Segunda línea:** 36, 48, 25, 16, 4, 1
**Tercera línea:** (0,0), (0,0), (0,0), (0,0), (0,0)

Se sabe que las raíces son:
$$-1, \pm i2, -1.5 \pm i2.598$$

En la figura D-2 aparece la salida del programa para este ejemplo.

## BIBLIOGRAFÍA

1. Müller, D. E., "A Method for Solving Algebraic Equations Using an Automatic Computer," *Mathematical Tables and Other Aids to Computation*, Vol. 10, 1956, pp. 208-215.
2. Conte, S. D. y C. de Boor, *Elementary Numerical Analysis*, 3a ed., McGraw-Hill, Nueva York, 1980, pp. 120-127.

---

# Índice

**A**
- Acción, 19
- Accionadores, 680
- Acción precalculada, control por, 447
- Acumulación, 538
- Acumulador del condensador, modelo del, 551-554
- Ajuste:
  - computadoras de control, 294-295
  - de controladores por muestreo de datos, 294
  - de controladores por retroalimentación, 265
  - para cambios del punto de control, 290
  - para error mínimo de integración, 289-290
  - para la razón de asentamiento de un cuarto, 267
  - para perturbaciones, 298
  - para un sobrepaso del 5%, 307
  - por síntesis, 306
  - Ziegler-Nichols, 266, 283
- Ajuste del error de integración mínimo, 289-290
- Ajuste en línea, 266-270
- Aproximación Padé, 263-304
- Argumento de un número complejo, 77
- Asentamiento, tiempo de, 164
- Avance de primer orden, 166, 167
- Avance/retardo, unidad de, 167, 453, 457-459
  - programa, 598
  - simulación, 593

**B**
- Balances independientes, 539
- Bloques de cómputo, 420
- Bourdon, Eugenio, 647
- Bourdon, tubo de, 648

**C**
- Caldera, control de una, 435, 464
- Cámara de vapor, modelo, 547
- Cero:
  - de la función de transferencia, 341
  - del transmisor, 177
- Circuito abierto, control de, 19
- Circuito de control, programa para un, 598
- Circuito de control, simulación de un, 596
- Circuito por retroalimentación unitaria, 187, 238
- Computadora, programa de, ver Programa
- Condensador, modelo de, 549-551
- Condiciones iniciales:
  - en estado estacionario, 554, 567
  - para la operación de la columna, 554
  - para un horno, 560
- Condiciones límite, 560
- Conjugado de un número complejo, 78
- Conmutadores de límite, 688
- Conmutador por lotes, 316
- Conservación, ecuaciones de, 338
- Constante de tiempo, 96
  - característica, 161
  - efectiva, 151
  - estimación, 274-277
- Constante de tiempo dominante, 259
- Control, 20
  - de una caldera, 435, 464
  - en cascada, 111, 439
  - multivariable, 479
  - por acción precalculada hacia adelante, 23
  - por limitación cruzada, 437
  - por retroalimentación, 20
  - por sobreposición, 472
  - razón de, 354
  - regulador, 20
  - selectivo, 472
  - servo control, 20
- Control automático de proceso, 18
  - objetivo, 320
  - razones, 25
- Control de circuito cerrado, 20
- Control de un evaporador, 616
- Control distribuido, 294
- Control en cascada, 439
- Control multivariable, 479
  - desacoplamiento, 505
  - índice de interacción, 500
  - interacción y estabilidad, 503
  - matriz de ganancia relativa, 492
  - pares, agrupación por, 490
  - teorema de Niederlinski, 494
- Control por computadora, ajuste, 293-295
- Control selectivo, 472-477
- Controlador, 18, 19, 198
  - acción, 201
  - ajuste, 20, 265, 297, 299, 311
  - auto/manual, 200
  - con banda proporcional, 207
  - desviación del, 204
  - digital, 215
  - ganancia, 204
  - local/remoto, 200
  - por retroalimentación, 198
  - proporcional, 204
  - proporcional-derivativo (PD), 214
  - proporcional-integral (PI), 209
  - proporcional-integral derivativo (PID), 211
  - rapidez de derivación, 211
  - rapidez de reajuste, 210
  - reajuste excesivo, 216, 311-316
  - tiempo de derivación, 211
  - tiempo de reajuste, 209
  - síntesis, 297
- Controlador esclavo, 286
- Controlador irrealizable, 301
- Controlador por muestreo de datos, 294
- Criterios de error de integración, 285

**D**
- Delta Dirac, función, 30
- Densidad de un gas ideal, 74
- Desacoplador, 703
- Destilación, modelo de, 540-556
- Desviación, 204
  - cálculo de, 238-243
- Desviación, variables de, 65
- Detector de burbujeo, 662
- Diagrama de Bode, 370
  - de prueba de pulso, 410
- Diagramas de bloques, 105
  - reglas, 107
- Diagramas polares, 393
- Diferenciación compleja, teorema de la, 34
- Diferencial de presión, medidor de, 659
- Diferencial de presión, transmisor de, 671
  - electrónico, 674
  - neumático, 671
- Diferencias finitas, 561
- Discretización, 561
- Disturbio, 20
- División sintética, 61
- Dominio, 43
- Dominio del tiempo, 43
- Dominio S, 43
- Duración de las corridas de simulación, 569

**E**
- Ecuación característica, 59, 230
- Ecuación de Antoine, 69
- Ecuación de Arrhenius, 70
- Ecuación diferencial, forma general, 563
- Ecuaciones de balance, 539
- Ecuaciones diferenciales parciales, 558
  - solución, 561-562
- Ecuaciones diferenciales, solución de, 41
- Ecuación lineal, 65
- Eficiencia de Murphree, 543
- Eigenvalor, 59, 343
  - dominante, 596, 602
  - estimación, 604
- Eigenvalor dominante, 569, 602
- Elemento final de control, 18-19
- Entrada, variable de, 41
  - a una columna de destilación, 555
  - a un horno, 560
- Equilibrio, relaciones de, 543
- Error de redondeo, 572
- Error de truncamiento, 571
- Escala, 177
- Escalón unitario, 28
- Especificación de respuesta de circuito cerrado, 298
- Estabilidad, 59
  - criterio, 252
  - de circuito de control por retroalimentación, 251
  - de integración numérica, 611
- Estabilidad marginal, 259
- Estado, variables de, 554
- Euler, integración de, 568
  - estabilidad, 611
- Evaporador de efecto múltiple, 618
- Evaporador de efecto triple, 618
- Expansión de series de Taylor, 67, 71, 118
- Factor cuadrático, 50
- Factorización de polinomios, 44
- Fase, margen de, 391
- Fase mínima, sistemas de, 381
- Fase no mínima, sistemas de, 381
- Flujo, medidor magnético de, 658
- Fórmula de Francis para vertedores, 544
- FORTRAN, programa, ver Programa
- Fourier, transformada de, 405
  - de un pulso rectangular, 406-407
  - evaluación numérica, 407-410
- Fracciones parciales, expansión de, 9-58
- Frecuencia, 164
  - cíclica, 164
  - en radianes, 165
  - natural, 164
- Frecuencia última, 260
- Función de deflación, 703
- Función de forzamiento, 41, 93
- Función de transferencia, 43, 94, 104
  - cero de, 342
  - de circuito abierto, 345
  - de circuito cerrado, 110, 229
  - de primer orden, 95
  - de segundo orden, 143
  - de tercer orden, 145
  - polo de, 342
  - propiedades, 105
- Función de transferencia de circuito cerrado, 229
- Función escalón, 28
- Función seno, 31

**G**
- Ganancia, 99
  - estimación, 274
- Ganancia de circuito, 257
- Ganancia de estado estacionario, 86
- Ganancia última, 252, 266
- Gear, C. W., 613
- Gráficas de flujo de señal, 479

**H**
- Horno, modelo de un, 556-561
- Hougen, Joel O., 402, 410

**I**
- IAE, 286
  - ajuste, 289-290, 305
- ICE, 286
  - ajuste, 289-290
- Ideal, densidad de un gas, 74
- Impulso, 30
- Impulso unitario, 30
- Instrumentación, nomenclatura, 627
- Instrumentación, símbolos de la, 627
- Instrumentación, símbolos para, 672
- Integración de Euler modificada, 576
  - implícita, 612
  - subrutina, 578
- Integración explícita, 609
- Integración implícita, 612
- Integración numérica, 568-584
  - implícita, 612
  - programa principal, 580
- Integración real, teorema de la, 33
- Intervalo de integración, 569
  - selección de, 571
- Inversión de la transformada de Laplace, 44
- ITAE, 286
  - ajuste, 289-290
- ITCE, 287
- Iteración, 60

**L**
- Laplace, dominio de, 42
- Laplace, transformada de, 27
  - de las derivadas, 31
  - de las integrales, 33
  - inversión, 44-58
  - linealidad, 31
  - método de solución, 41-59, 64-65
  - propiedades, 31-36
  - Tabla, 32
  - utilidad, 43
- Linealización, 65, 118
  - de funciones con una sola variable, 67
  - de funciones multivariable, 71
  - por expansión de series de Taylor, 118
  - valor base, 66
- López, A. M., 288
- Lugar de raíz, 343-361
  - criterio de ángulo, 350
  - criterio de magnitud, 350
  - reglas para graficar el, 349
- Luyben, W.L., 410

**M**
- Magnitud, de un número complejo, 77
- Mapeo de conformación, 395
- Margen de ganancia, 391
- Martin, Jacob, 232, 310
- Medición, 19
- Medidor de orificio, 654
- Método 1 de la respuesta escalón, 274
- Método 2 de la respuesta escalón, 276
- Método 3 de la respuesta escalón, 276
- Microprocesador, control por, 307
- Modelo, 25, 540
  - de cámara de vapor, 547
  - de columna de destilación, 540-555
  - de condensador, 549-551
  - de controlador de nivel, 547, 552
  - de horno, 556-560
  - de parámetro localizado, 539
  - de presión en la columna, 549-551
  - de primer orden, 272
  - de radiación de calor, 559
  - de reactor, 563-568
  - desarrollo, 539
  - de segundo orden, 271
  - de tambor acumulador, 551-554
  - distribuido, 539, 555
  - para una bandeja de destilación, 540-545
- Modelo matemático, 539
- Modificada de Euler implícita, 612
- Modo derivativo, 211
  - programa, 598
  - selección, 304-306
  - simulación, 596
- Modo proporcional, función de, 307
- Modos de controlador, selección de, 299-306
- Moore, C. F., 295
- Müller, método de, 59, 703
  - subrutina, 705
- Multiplicaciones anidadas, 61
- Multiplicadores, 688
- Murrill, P. W., 285

**N**
- Newton-Barstow, método de, 59
- Newton, método de, 61
- Nichols, diagramas de, 401
- Nisenfeld, E., 500
- Nivel, modelo de control de, 547, 552
- No linealidad, 120
- Notación polar, 77
- Número imaginario, 76
- Números complejos, 76
  - argumento, 77
  - conjugado, 79
  - magnitud, 77
  - notación polar, 77
  - operaciones, 78
- Nyquist, criterio de estabilidad de, 397

**O**
- Oscilación, período de, 164

**P**
- Parámetro distribuido, modelo de, 539-555
- Parámetro localizado, modelo de, 538
- Período de oscilación, 164
- Período último, 260, 266
- Perturbación, 20
  - ajuste, 289
  - de entrada, 287
  - respuesta, 287
- Perturbación, variables de, 66
- pH, control del, 615
- PID, controlador, 212
  - ajuste, 268, 283, 289-290, 307
  - programa, 598
  - simulación, 594
- Plano complejo, 77
- Plano izquierdo, 253
- Polinomio reducido, 60
- Polinomios:
  - factorización, 45
  - raíces, 45
- Polinomios, raíces de, 45, 703
  - programa, 704
- Polo, 342
- POMTM, 131
  - métodos de la respuesta escalón, 274-277
  - modelo, 272
  - proceso, 301
  - respuesta, 276
- Posición del controlador, 154
- Posicionadores, 682
- Posición manual del controlador, 229
- Presión en la columna, 549, 551
- Presión en una columna de destilación, 550-551
- Primer orden, avance de, 166, 167
- Primer orden más tiempo muerto, ver POMTM
- Primer orden, retardo de, 95
  - proceso de, 95
  - programa, 598
  - simulación, 588
- Principio de sobreposición, 106
- Proceso:
  - acoplado, 125
  - caracterización, 266, 270
  - curva de reacción, 273
  - de orden superior, 139
  - de primer orden, 95
  - estable, 105
  - ganancia, 99, 274
  - interactivo, 125, 147
  - no interactivo, 139
  - no lineal, 120
  - personalidad, 23
- Proceso autorregulado, 152
- Proceso, control del, 17
  - objetivo, 20
  - razones, 25
- Programa:
  - para circuito de control, 598
  - para el drenaje de tanque, 603
  - para el método de Müller, 705
  - para integración general, 580
  - para modificada de Euler, 578
  - para raíces de polinomios, 704
  - para Runge-Kutta-Simpson, 585
  - para un reactor, 574
- Programación modular, 579
- Propiedades físicas, 544
- Prueba de escalón, 272-274
  - POMTM, métodos, 273-277
  - racional, 282
- Prueba del proceso:
  - con escalón, 272
  - por pulso, 402-410
- Prueba de pulso, 402-411
  - amplitud, 403
  - de proceso de integración, 410-411
  - duración, 403
- Prueba senoidal, 361
- Pulso rectangular, 403
- Punto de control, 20
  - ajuste, 290
  - entrada, 287
- Puntos de entrada, 579

**R**
- Radiación, modelo de, 559
- Radianes, 50
- Raíces complejas conjugadas, 48
- Raíces de polinomios, 45
  - cálculo de, 703
  - compleja conjugada, 48
  - determinación, 59
  - reales no repetidas, 46
  - repetidas, 51
- Raíces repetidas, 51
- Rango, 177
- Razón, control de, 430-439
- Razón de amortiguamiento, 161
- Razón de asentamiento de un cuarto, 163
- Razón de asentamiento de un cuarto, ajuste a, 268, 283
- Recuperación excesiva, 216
  - eliminación, 311
- Regla trapezoidal, 576
- Regulador, 287
- Regulador, control, 20
- Rehervidor, modelo, 545-549
- Relés de cómputo, 420
- Respuesta, 126-160
  - críticamente amortiguada, 162
  - inversa, 471
  - sobreamortiguada, 162
  - subamortiguada, 161
- Respuesta en frecuencia, 361
  - ángulo de fase, 364
  - criterio de estabilidad de Bode, 381
  - criterio de estabilidad de Nyquist, 397
  - diagrama de Bode, 381
  - diagramas de Nichols, 401
  - diagramas polares, 393
  - margen de fase, 391
  - margen de ganancia, 391
  - razón de amplitud, 364
  - razón de magnitud, 364
- Respuesta escalón, en dos puntos, 277
- Respuesta inversa, 471
- Retardo:
  - de primer orden, 95
  - de segundo orden, 143
  - de tercer orden, 145
- Retardo de segundo orden, 143
  - simulación, 589
- Retardo de transporte, ver Tiempo muerto
- Retroalimentación, control por, 21, 226
  - programa, 598
  - simulación, 596
  - síntesis, 297
- Retroalimentación de recuperación, 315, 567
  - programa, 598
  - simulación, 595
- Rigidez, 601
  - fuente, 601
  - reducción, 603
- Routh, prueba de, 253
- Rovira, A. A., 290-294
- Runge Kutta-Simpson, integración, 583
  - subrutina, 585

**S**
- Salida, función de, 41
- Saturación, 312
- Schultz, G., 500
- Segundo orden más tiempo muerto, ver SOMTM, modelo
- Sensor, 18, 19, 647
  - cero, 178
  - de composición, 66
  - de flujo, 651
  - de nivel, 659
  - de presión, 647
  - de temperatura, 663
  - escala, 177
  - ganancia, 178
  - rango, 177
- Sensor de flotación, 662
- Señales, 21
  - digital, 21
  - eléctrica, 21
  - neumática, 21
- Servocontrol, 20
- Servorregulador, 287
- Shinskey, F. G., 503
- Simulación, 26, 564-584
  - de drenado de tanque, 604-609
  - del circuito de control, 596
  - del tiempo muerto, 591
  - de retardo de primer orden, 587
  - de unidad de derivación, 596
  - dinámica, 537
- Simulación, corridas de,
  - duración, 569
  - tipos de, 554
- Simulación, lenguajes de, 586-588
- Simulación por computadora, 563-584
- Síntesis, ajuste por, 306
- Síntesis de los controladores, 632
- Sistema de control, 18
- Sistema de segundo orden, respuesta de un, 162
  - críticamente amortiguada, 162
  - sobreamortiguada, 162
  - subamortiguada, 162
- Sistemas:
  - de fase mínima, 381
  - de fase no mínima, 381
  - de orden superior, 139
  - de primer orden, 95
  - interactivos, 125, 147
  - no interactivos, 139
- Sistemas interactivos, 125, 147
- Sistemas no interactivos, 139
- Smith, Cecil L., 277, 285
- Sobrepaso, 164
- Sobreposición, control por, 472
- SOMTM, modelo, 272
- Subrutina:
  - para circuito de control, 598
  - para drenado de tanque, 608
  - para el método de Müller, 705
  - para Runge-Kutta-Simpson, 585
  - para un tanque de reacción, 581
- Subrutinas de integración numérica, 584-587
- Subrutinas de propósito general, 584
- Subrutinas para integración numérica, 586
- Substitución directa, 259
- Superposición, principio de, 106
- Suposición de estado cuasiestacionario, 603

**T**
- Tanque de reacción, modelo de un, 564-568
- Tanque de reacción, programa para un, 574-581
- Tanque, simulación de drenaje de un, 604-609
- Teorema de la diferenciación, real, 32
- Termistor, 668
- Termómetros:
  - de dispositivos resistivos (DRT), 668
  - de líquido encapsulado, 664
  - de sistemas llenos, 666
  - de tira bimetálica, 664
- Termopar, 669
- Tiempo de elevación, 164
- Tiempo de máquina, 571
- Tiempo de muestreo, 295
- Tiempo de respuesta, despliegue del, 572
- Tiempo de retardo, ver Tiempo muerto
- Tiempo final, 569
- Tiempo inicial, 569
- Tiempo muerto, 34, 54, 114
  - efecto sobre la estabilidad, 263
  - estimación, 214, 271
  - simulación, 591
- Tiempo muerto, programa para, 598
- Tolerancia, 703
- Tolerancia de error, 703
- Tolerancia relativa de error, 703
- Transductor, 21
- Transmisor, 18, 19, 671
  - cero, 178
  - electrónico, 674
  - escala, 177
  - ganancia, 178
  - neumático, 671
  - rango, 177
- Traslación de complejos, teorema de la, 36
- Traslación real, teorema de la, 35
- Turbina, medidor de, 659

**U**
- Unidades de tiempo, 569

**V**
- Valor inicial, teorema del, 36
- Valor final, teorema del, 36
- Válvulas, 180-198, 674-700
  - acción de, 180
  - actuadores, 680
  - ajuste de rango, 186
  - caída de presión, 186
  - características del flujo, 190
  - cavitación, 698
  - conmutadores de límite, 688
  - correlación de viscosidad, 688
  - dimensionamiento, 181
  - flujo crítico, 183
  - ganancia de las, 196
  - multiplicadores, 688
  - posicionador, 684
  - tipos, 674
  - vaporización instantánea, 692
- Variable:
  - controlada, 19
  - de desviación, 65-67, 93
  - de entrada, 93
  - de estado, 554
  - dependiente, 41
  - de perturbación, 66
  - de respuesta, 93
  - de salida, 93
  - independiente, 41
  - manipulada, 19
- Variable auxiliar, 564
- Variable controlada, 20
- Variable dependiente, 41
- Variable independiente, 41
- Variable manipulada, 20
- Volatilidad relativa, 69
- Volumen de control, 538

**Z**
- Ziegler-Nichols, ajuste de, 266, 283
