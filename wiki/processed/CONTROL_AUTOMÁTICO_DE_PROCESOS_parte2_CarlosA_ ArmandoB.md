# Capítulo 4: Sistemas dinámicos de orden superior

En el capítulo anterior se presentaron varios ejemplos de procesos que pueden ser descritos mediante ecuaciones diferenciales ordinarias de primer orden. En este capítulo el interés de la exposición se centra en los procesos que se describen mediante ecuaciones diferenciales de orden superior; en general, los objetivos que se persiguen en este capítulo son bastante cercanos a los del anterior. Se presentan los modelos matemáticos para sistemas más complejos y se explica el significado de los parámetros que describen las características de esos procesos.

## 4-1. TANQUES EN SERIE-SISTEMA NO INTERACTIVO

Los sistemas de orden superior pueden ser interactivos o no; en este capítulo se presentan ejemplos de ambos tipos, mediante la descripción de algunos procesos reales. También se explica el significado de los términos interactivo y no interactivo.

El ejemplo típico de un sistema no interactivo es el sistema de tanques que se muestra en la figura 4-1; se deben determinar las funciones de transferencia que relacionan el nivel del segundo tanque con el flujo de entrada al primer tanque, $q_i(t)$, y el flujo de la bomba, $q_o(t)$.

En este ejemplo todos los tanques están abiertos a la atmósfera y el proceso es isotérmico. La apertura de las válvulas permanece constante y el flujo de líquido a través de las válvulas se expresa mediante:

$$q(t) = \frac{C_v}{7.48}\sqrt{\frac{\Delta P(t)}{G}} = \frac{C_v}{7.48}\sqrt{\frac{\rho gh(t)}{144g_cG}} = C_v'\sqrt{h(t)}$$

donde:
- $C_v$ = coeficiente de la válvula, $\frac{gal/min}{psi}$
- $7.48$ = factor de conversión de gal a pies$^3$

Al escribir el balance de masa de estado dinámico para el primer tanque se tiene:

$$\rho q_i(t) - \rho q_1(t) - \rho q_o(t) = \rho A_1\frac{dh_1(t)}{dt} \quad (4-1)$$

donde:
- $\rho$ = densidad del líquido, lbm/pies$^3$
- $A_1$ = área transversal del tanque 1, pies$^2$

De la expresión de la válvula se obtiene otra ecuación:

$$q_1(t) = C_{v_1}'\sqrt{h_1(t)} \quad (4-2)$$

Con las ecuaciones (4-1) y (4-2) se describe el primer tanque; ahora se procede con el segundo tanque.

El balance de estado dinámico para el segundo tanque da:

$$\rho q_1(t) - \rho q_2(t) = \rho A_2\frac{dh_2(t)}{dt} \quad (4-3)$$

Nuevamente se obtiene otra ecuación a partir de la expresión de la válvula:

$$q_2(t) = C_{v_2}'\sqrt{h_2(t)} \quad (4-4)$$

Con las ecuaciones (4-1) hasta (4-4) se describe el proceso. Debido a que las ecuaciones (4-2) y (4-4) no son lineales, la solución más exacta se obtiene mediante simulación por computadora; sin embargo, puesto que se desea determinar las funciones de transferencia, se deben linealizar las ecuaciones antes de proceder de un modo similar al que se utilizó en el capítulo 3.

De las substituciones de la ecuación (4-2) en la (4-1), de las ecuaciones (4-2) y (4-4) en la (4-3), y la división de cada ecuación resultante entre la densidad, se obtiene:

$$q_i(t) - C_1'\sqrt{h_1(t)} - q_o(t) = A_1\frac{dh_1(t)}{dt} \quad (4-5)$$

Y:

$$C_1'\sqrt{h_1(t)} - C_2'\sqrt{h_2(t)} = A_2\frac{dh_2(t)}{dt} \quad (4-6)$$

De la ecuación (4-5), después de linealizar y definir las variables de desviación, se tiene:

$$Q_i(t) - C_1H_1(t) - Q_o(t) = A_1\frac{dH_1(t)}{dt} \quad (4-7)$$

donde:

$$C_1 = \frac{\partial q_1(t)}{\partial h_1(t)}\bigg|_{ss} = \frac{1}{2}C_1'(\bar{h}_1)^{-1/2}$$

y las variables de desviación:

$$Q_i(t) = q_i(t) - \bar{q}_i$$
$$Q_o(t) = q_o(t) - \bar{q}_o$$
$$H_1(t) = h_1(t) - \bar{h}_1$$

De la ecuación (4-6) se tiene:

$$C_1H_1(t) - C_2H_2(t) = A_2\frac{dH_2(t)}{dt} \quad (4-8)$$

donde:

$$C_2 = \frac{\partial q_2(t)}{\partial h_2(t)}\bigg|_{ss} = \frac{1}{2}C_2'(\bar{h}_2)^{-1/2}$$
$$H_2(t) = h_2(t) - \bar{h}_2$$

De reordenar las ecuaciones (4-7) y (4-8), se tiene:

$$\tau_1\frac{dH_1(t)}{dt} + H_1(t) = K_1Q_i(t) - K_1Q_o(t) \quad (4-9)$$

Y:

$$\tau_2\frac{dH_2(t)}{dt} + H_2(t) = K_2H_1(t) \quad (4-10)$$

donde:

$$\tau_1 = \frac{A_1}{C_1}, \text{ minutos}$$
$$\tau_2 = \frac{A_2}{C_2}, \text{ minutos}$$
$$K_1 = \frac{1}{C_1}, \text{ pies-min/pies}^3$$
$$K_2 = \frac{C_1}{C_2}, \text{ sin dimensiones}$$

De obtener la transformada de Laplace de las ecuaciones (4-9) y (4-10) y reordenar, se obtiene:

$$H_1(s) = \frac{K_1}{\tau_1s + 1}Q_i(s) - \frac{K_1}{\tau_1s + 1}Q_o(s) \quad (4-11)$$
$$H_2(s) = \frac{K_2}{\tau_2s + 1}H_1(s) \quad (4-12)$$

Con la ecuación (4-11) se relaciona el nivel del primer tanque con los flujos de entrada y salida; mediante la (4-12) se relaciona el nivel del segundo con el del primero.

Para determinar las funciones de transferencia que se desean, se substituye la ecuación (4-11) en la (4-12):

$$H_2(s) = \frac{K_1K_2}{(\tau_1s + 1)(\tau_2s + 1)}(Q_i(s) - Q_o(s)) \quad (4-13)$$

o sea que las funciones de transferencia individuales son:

$$\frac{H_2(s)}{Q_i(s)} = \frac{K_1K_2}{(\tau_1s + 1)(\tau_2s + 1)} \quad (4-14)$$

$$\frac{H_2(s)}{Q_o(s)} = \frac{-K_1K_2}{(\tau_1s + 1)(\tau_2s + 1)} \quad (4-15)$$

Las funciones de transferencia que expresan las ecuaciones (4-14) y (4-15) se conocen como **funciones de transferencia de segundo orden o retardos de segundo orden**, y a partir de su desarrollo es bastante simple ver que se "forman" con dos funciones de transferencia de primer orden en serie.

Como se muestra en la figura 4-2, el diagrama de bloques de este sistema se puede representar de diferentes formas. El diagrama de bloques de la figura 4-2a se desarrolló mediante el "encadenamiento" de las ecuaciones (4-11) y (4-12); en el diagrama se muestra que el flujo de entrada y salida afecta inicialmente el nivel en el primer tanque, $H_1(s)$; por lo tanto, el cambio en este nivel afecta al nivel del segundo tanque, $H_2(s)$.

En la figura 4-3 se muestra una forma de extender el proceso mostrado en la figura 4-1 mediante la adición de otro tanque; para este nuevo proceso se determinarán las funciones de transferencia que relacionan el nivel del tercer tanque con el flujo de entrada en el primer tanque y el flujo de la bomba.

Puesto que ya se obtuvieron los modelos para los dos primeros tanques, con las ecuaciones (4-1) a (4-4), ahora se hará el modelo del tercer tanque. De escribir el balance de masa de estado dinámico para el tercer tanque, resulta:

$$\rho q_2(t) - \rho q_3(t) = \rho A_3\frac{dh_3(t)}{dt} \quad (4-16)$$

De la expresión de la válvula se obtiene la otra ecuación que se requiere y es la siguiente:

$$q_3(t) = C_{v_3}'\sqrt{h_3(t)} \quad (4-17)$$

Con las ecuaciones (4-1), (4-2), (4-3), (4-4), (4-16) y (4-17) se tiene el modelo para el nuevo proceso (ver figura 4-3).

Al substituir las ecuaciones (4-4) y (4-17) en la ecuación (4-16) y dividir la ecuación resultante entre la densidad, se obtiene:

$$C_2'\sqrt{h_2(t)} - C_3'\sqrt{h_3(t)} = A_3\frac{dh_3(t)}{dt} \quad (4-18)$$

de la cual se tiene:

$$C_2H_2(t) - C_3H_3(t) = A_3\frac{dH_3(t)}{dt} \quad (4-19)$$

donde:

$$C_3 = \frac{\partial q_3(t)}{\partial h_3(t)}\bigg|_{ss} = \frac{1}{2}C_3'(\bar{h}_3)^{-1/2}$$

y la variable de desviación es $H_3(t) = h_3(t) - \bar{h}_3$.

Al reordenar la ecuación (4-19) y obtener la transformada de Laplace, se tiene:

$$H_3(s) = \frac{K_3}{\tau_3s + 1}H_2(s) \quad (4-20)$$

donde:

$$\tau_3 = \frac{A_3}{C_3}, \text{ minutos}$$
$$K_3 = \frac{C_2}{C_3}, \text{ sin dimensiones}$$

Finalmente, la substitución de la ecuación (4-13) en la (4-20) da:

$$H_3(s) = \frac{K_1K_2K_3}{(\tau_1s + 1)(\tau_2s + 1)(\tau_3s + 1)}(Q_i(s) - Q_o(s)) \quad (4-21)$$

de la cual se determinan las siguientes funciones de transferencia:

$$\frac{H_3(s)}{Q_i(s)} = \frac{K_1K_2K_3}{(\tau_1s + 1)(\tau_2s + 1)(\tau_3s + 1)} \quad (4-22)$$

$$\frac{H_3(s)}{Q_o(s)} = \frac{-K_1K_2K_3}{(\tau_1s + 1)(\tau_2s + 1)(\tau_3s + 1)} \quad (4-23)$$

Estas dos funciones de transferencia se denominan **funciones de transferencia de tercer orden o retardos de tercer orden**. En la figura 4-4 se ilustran tres diferentes maneras de representar la ecuación (4-21) mediante diagramas de bloques.

Nótese que estas funciones de transferencia se obtienen mediante la multiplicación de funciones de transferencia de primer orden; es decir:

$$\frac{H_j(s)}{Q_j(s)} = \frac{H_1(s)}{Q_1(s)}\cdot\frac{H_2(s)}{H_1(s)}\cdot\frac{H_3(s)}{H_2(s)}$$

Este es el caso de los sistemas no interactivos en serie, cuyo enunciado se puede generalizar como sigue:

$$G(s) = \prod_{i=1}^{n}G_i(s) \quad (4-24)$$

donde:
- $n$ = cantidad de sistemas no interactivos en serie
- $G(s)$ = función de transferencia que relaciona la salida del último sistema, el sistema $n$, con la entrada del primer sistema
- $G_i(s)$ = función de transferencia individual para cada sistema

Los procesos que se muestran en las figuras 4-1 y 4-5 se conocen como **sistemas no interactivos**, porque no hay interacción completa entre las variables. El nivel del primer tanque afecta al del segundo; pero el nivel de éste no afecta al del primero; lo mismo es verdad para los niveles del segundo y tercer tanques. En las siguientes secciones se presentan ejemplos de sistemas interactivos.

## 4-2. TANQUES EN SERIE-SISTEMA INTERACTIVO

Si se redistribuyen los tanques de la figura 4-1, el resultado es un sistema interactivo como el mostrado en la figura 4-5.

La interacción entre los tanques se demuestra claramente a partir de la ecuación de flujo de la válvula, $q_1(t)$, es decir:

$$q_1(t) = \frac{C_{v1}}{7.48}\sqrt{\frac{\Delta P(t)}{G}} = \frac{C_{v1}}{7.48}\sqrt{\frac{\rho g(h_1(t) - h_2(t))}{144g_cG}} = C_{v1}'\sqrt{h_1(t) - h_2(t)}$$

En esta ecuación se aprecia que el flujo entre los dos tanques depende del nivel en ambos; el uno afecta al otro.

Ahora se determinarán las mismas dos funciones de transferencia que en el caso del sistema no interactivo:

$$\frac{H_2(s)}{Q_i(s)} \qquad \text{y} \qquad \frac{H_2(s)}{Q_o(s)}$$

Se comienza por escribir el balance de masa de estado dinámico para el primer tanque, mismo que se expresa mediante la siguiente ecuación:

$$\rho q_i(t) - \rho q_1(t) - \rho q_o(t) = \rho A_1\frac{dh_1(t)}{dt} \quad (4-1)$$

De la expresión para la válvula se obtiene la siguiente ecuación:

$$q_1(t) = C_{v1}'\sqrt{h_1(t) - h_2(t)} \quad (4-25)$$

Aún se necesita otra ecuación independiente; el balance de masa de estado dinámico para el segundo tanque ayuda para obtenerla; ésta es la ecuación (4-3):

$$\rho q_1(t) - \rho q_2(t) = \rho A_2\frac{dh_2(t)}{dt} \quad (4-3)$$

El flujo a través de la última válvula se expresa mediante la ecuación (4-4):

$$q_2(t) = C_{v2}'\sqrt{h_2(t)} \quad (4-4)$$

Ahora se tiene la misma cantidad de ecuaciones independientes que de incógnitas, lo cual describe al proceso, es decir, se tiene el modelo; ahora sigue la solución.

Se substituye la ecuación (4-25) en la (4-1) y se divide la ecuación resultante entre la densidad, para obtener:

$$q_i(t) - C_{v1}'\sqrt{h_1(t) - h_2(t)} - q_o(t) = A_1\frac{dh_1(t)}{dt}$$

De la cual se obtiene:

$$Q_i(t) - C_4H_1(t) + C_4H_2(t) - Q_o(t) = A_1\frac{dH_1(t)}{dt} \quad (4-26)$$

donde:

$$C_4 = \frac{\partial q_1(t)}{\partial h_1(t)}\bigg|_{ss} = -\frac{\partial q_1(t)}{\partial h_2(t)}\bigg|_{ss} = \frac{1}{2}C_{v1}'(\bar{h}_1 - \bar{h}_2)^{-1/2}$$

Al reordenar la ecuación (4-26) y obtener la transformada de Laplace:

$$H_1(s) = \frac{K_4}{\tau_4s + 1}Q_i(s) + \frac{1}{\tau_4s + 1}H_2(s) - \frac{K_4}{\tau_4s + 1}Q_o(s) \quad (4-27)$$

donde:

$$K_4 = \frac{1}{C_4}, \text{ pies-min/pies}^3$$
$$\tau_4 = \frac{A_1}{C_4}, \text{ minutos}$$

Se sigue el mismo procedimiento para el segundo tanque y se obtiene:

$$H_2(s) = \frac{K_5}{\tau_5s + 1}H_1(s) \quad (4-28)$$

donde:

$$K_5 = \frac{C_4}{C_4 + C_2}, \text{ sin dimensiones}$$
$$\tau_5 = \frac{A_2}{C_4 + C_2}, \text{ minutos}$$

Finalmente, la substitución de la ecuación (4-27) en la (4-28) da por resultado:

$$H_2(s) = \frac{K_4K_5}{(\tau_4s + 1)(\tau_5s + 1)}(Q_i(s) - Q_o(s)) + \frac{K_5}{(\tau_4s + 1)(\tau_5s + 1)}H_2(s)$$

$$H_2(s) = \frac{K_4K_5}{\tau_4\tau_5s^2 + (\tau_4 + \tau_5)s + (1 - K_5)}(Q_i(s) - Q_o(s))$$

$$H_2(s) = \frac{\frac{K_4K_5}{1 - K_5}}{\left(\frac{\tau_4\tau_5}{1 - K_5}\right)s^2 + \left(\frac{\tau_4 + \tau_5}{1 - K_5}\right)s + 1}(Q_i(s) - Q_o(s)) \quad (4-29)$$

A partir de la cual se obtienen las funciones de transferencia que se desean; es decir:

$$\frac{H_2(s)}{Q_i(s)} = \frac{\frac{K_4K_5}{1 - K_5}}{\left(\frac{\tau_4\tau_5}{1 - K_5}\right)s^2 + \left(\frac{\tau_4 + \tau_5}{1 - K_5}\right)s + 1} \quad (4-30)$$

Y:

$$\frac{H_2(s)}{Q_o(s)} = \frac{-\frac{K_4K_5}{1 - K_5}}{\left(\frac{\tau_4\tau_5}{1 - K_5}\right)s^2 + \left(\frac{\tau_4 + \tau_5}{1 - K_5}\right)s + 1} \quad (4-31)$$

Las funciones de transferencia mostradas aquí son de segundo orden. Los diagramas de bloques para este proceso interactivo se muestran en la figura 4-6.

Son varias cosas las que se pueden aprender de la comparación de las funciones de transferencia para los sistemas interactivos y no interactivos. Al comparar las ecuaciones (4-14) y (4-30) se observa que las ganancias, o sensibilidades, son diferentes en los dos casos; también las constantes de tiempo son diferentes; aún más, para el caso interactivo, la constante de tiempo mayor es más grande que en el caso no interactivo, lo cual da como resultado que el sistema responda más lentamente.

Para probar esta última declaración considérese el caso en que ambas constantes de tiempo individuales son iguales, esto es:

$$\tau_4 = \tau_5 = \tau$$

y para que esto sea cierto:

$$K_5 = 0.5$$

Entonces $K_5 = 0.5$.

Con esta información, la ecuación (4-31) se convierte en:

$$\frac{H_2(s)}{Q_o(s)} = \frac{-\frac{K_4K_5}{(\tau s + 1)^2}}{1 - \frac{K_5}{(\tau s + 1)^2}} = \frac{-K_4K_5}{\tau^2s^2 + 2\tau s + (1 - K_5)}$$

Las raíces del denominador son:

$$\text{Raíces} = \frac{-(1 + \sqrt{K_5})}{\tau}, \frac{-(1 - \sqrt{K_5})}{\tau}$$

de lo cual se obtienen dos constantes de tiempo "efectivas" para este sistema interactivo:

$$\tau_{4ef} = \frac{\tau}{1 + \sqrt{K_5}} = \frac{\tau}{1.707} = 0.58\tau$$
$$\tau_{5ef} = \frac{\tau}{1 - \sqrt{K_5}} = \frac{\tau}{0.293} = 3.41\tau$$

y la relación entre dichas constantes de tiempo "efectivas" es:

$$\frac{\tau_{5ef}}{\tau_{4ef}} = 5.8$$

¡a pesar de que $\tau_4 = \tau_5$! Esto demuestra claramente que la constante de tiempo mayor de un sistema interactivo es más grande que la de un sistema no interactivo.

Otro hecho acerca de los sistemas interactivos es que las constantes de tiempo "efectivas" son reales; para probar tal declaración se iguala el denominador de la ecuación (4-31) a cero:

$$\left(\frac{\tau_4\tau_5}{1 - K_5}\right)s^2 + \left(\frac{\tau_4 + \tau_5}{1 - K_5}\right)s + 1 = 0$$

Con base en la definición de $\tau_4$, $\tau_5$ y $K_5$, se tiene:

$$\left(\frac{A_1A_2}{C_2C_4}\right)s^2 + \left(\frac{A_1(C_2 + C_4)}{C_2C_4} + \frac{A_2C_4}{C_2C_4}\right)s + 1 = 0$$

Las raíces de esta ecuación se obtienen mediante el uso de la expresión cuadrática y, para que éstas sean reales, debe ser cierto lo siguiente:

$$b^2 - 4ac = \frac{[A_1(C_2 + C_4) + A_2C_4]^2}{C_2^2C_4^2} - \frac{4A_1A_2}{C_2C_4} > 0$$

$$(A_1C_2 - A_2C_4)^2 + A_1C_4(A_1C_2 + A_1C_4 + 2A_2C_4) > 0$$

y puesto que todas las constantes son positivas, la desigualdad es siempre verdadera; por lo tanto, se puede decir que las constantes de tiempo de los sistemas interactivos son siempre reales. Esto es importante cuando se estudia la respuesta de tales sistemas a diferentes funciones forzadas.

La gran mayoría de los procesos se describen mediante funciones de transferencia de orden superior. En la industria se encuentran tanto procesos interactivos como no interactivos; de los dos, el interactivo es el más común. En las siguientes secciones se presentan más ejemplos de procesos interactivos.

## 4-3. PROCESO TÉRMICO

Considérese la unidad que se muestra en la figura 4-7, cuyo objetivo es enfriar un fluido caliente que se procesa; el medio de enfriamiento, agua, pasa a través de una camisa. Para este proceso se supone que el agua, en la camisa de enfriamiento, y el fluido, en el tanque, están bien mezclados y que la densidad y capacidad calorífica de ambos no cambia significativamente con la temperatura. Debido a que el fluido procesado sale del tanque por desborde, el nivel y el área de transferencia de calor en el tanque son constantes. Finalmente, se puede suponer también que el tanque está bien aislado.

Se deben determinar las funciones de transferencia que relacionan la temperatura de salida del fluido que se procesa, $T(t)$, con la temperatura de entrada del agua de enfriamiento, $T_{c_i}(t)$, y con el flujo del agua de enfriamiento, $q_c(t)$.

Se escribe el balance de energía de estado dinámico para el fluido que se procesa:

$$q\rho C_pT_i(t) - UA[T(t) - T_c(t)] - q\rho C_pT(t) = V\rho C_v\frac{dT(t)}{dt} \quad (4-32)$$

donde:
- $q$ = flujo del fluido que se procesa, $m^3/s$
- $\rho$ = densidad del fluido que se procesa, $kg/m^3$
- $C_p$ = capacidad calorífica del fluido que se procesa, J/kg-K
- $T_i(t)$ = temperatura de entrada del fluido que se procesa, K
- $T(t)$ = temperatura de salida del fluido que se procesa, K
- $T_c(t)$ = temperatura del agua en la camisa, K
- $U$ = coeficiente global de transferencia de calor, $J/s-m^2-K$
- $A$ = área de transferencia de calor, $m^2$
- $V$ = volumen del fluido en el tanque, $m^3$

Se escribe el balance de energía de estado dinámico para el agua en la camisa:

$$q_c(t)\rho_cC_{p_c}T_{c_i}(t) + UA[T(t) - T_c(t)] - q_c(t)\rho_cC_{p_c}T_c(t) = V_c\rho_cC_{v_c}\frac{dT_c(t)}{dt} \quad (4-33)$$

donde:
- $q_c(t)$ = flujo del agua de enfriamiento, $m^3/s$
- $\rho_c$ = densidad del agua, $kg/m^3$
- $C_{p_c}$ = capacidad calorífica del agua, J/kg-K
- $T_{c_i}(t)$ = temperatura de entrada del agua, K
- $V_c$ = volumen de la camisa, $m^3$
- $C_{v_c}$ = capacidad calorífica a volumen constante del agua, J/kg-K

Las ecuaciones (4-32) y (4-33) constituyen el modelo de este proceso térmico. Nótese que en ambas ecuaciones aparece el término de transferencia de calor $UA[T(t) - T_c(t)]$, lo cual indica que existe interacción entre las dos variables: la temperatura del fluido procesado y la temperatura del agua de enfriamiento.

Para obtener las funciones de transferencia, primero se linealizan las ecuaciones y se definen las variables de desviación:

$$T(t) = T(t) - \bar{T}$$
$$T_i(t) = T_i(t) - \bar{T}_i$$
$$T_c(t) = T_c(t) - \bar{T}_c$$
$$T_{c_i}(t) = T_{c_i}(t) - \bar{T}_{c_i}$$
$$Q_c(t) = q_c(t) - \bar{q}_c$$

Al linealizar y reordenar, se obtienen las siguientes ecuaciones en el dominio de Laplace:

$$T(s) = \frac{1}{\tau_1s + 1}[K_1T_i(s) + K_2T_c(s)] \quad (4-36)$$

$$T_c(s) = \frac{1}{\tau_2s + 1}[K_3T_{c_i}(s) - K_4Q_c(s) + K_5T(s)] \quad (4-37)$$

donde:

$$\tau_1 = \frac{V\rho C_v}{q\rho C_p + UA}, \text{ minutos}$$
$$K_1 = \frac{q\rho C_p}{q\rho C_p + UA}, \text{ sin dimensiones}$$
$$K_2 = \frac{UA}{q\rho C_p + UA}, \text{ sin dimensiones}$$
$$\tau_2 = \frac{V_c\rho_cC_{v_c}}{UA + \bar{q}_c\rho_cC_{p_c}}, \text{ minutos}$$
$$K_3 = \frac{\bar{q}_c\rho_cC_{p_c}}{UA + \bar{q}_c\rho_cC_{p_c}}, \text{ sin dimensiones}$$
$$K_4 = \frac{\rho_cC_{p_c}(\bar{T}_c - \bar{T}_{c_i})}{UA + \bar{q}_c\rho_cC_{p_c}}, \text{ K/m}^3\text{-s}$$
$$K_5 = \frac{UA}{UA + \bar{q}_c\rho_cC_{p_c}}, \text{ sin dimensiones}$$

Por la substitución de la ecuación (4-37) en la (4-36), y después de algún manejo algebraico, se determinan las siguientes funciones de transferencia:

$$\frac{T(s)}{T_i(s)} = \left(\frac{K_1}{1 - K_2K_5}\right)\left[\frac{\tau_2s + 1}{\left(\frac{\tau_1\tau_2}{1 - K_2K_5}\right)s^2 + \left(\frac{\tau_1 + \tau_2}{1 - K_2K_5}\right)s + 1}\right] \quad (4-38)$$

$$\frac{T(s)}{T_{c_i}(s)} = \left(\frac{K_3K_2}{1 - K_2K_5}\right)\left[\frac{1}{\left(\frac{\tau_1\tau_2}{1 - K_2K_5}\right)s^2 + \left(\frac{\tau_1 + \tau_2}{1 - K_2K_5}\right)s + 1}\right] \quad (4-39)$$

$$\frac{T(s)}{Q_c(s)} = \left(\frac{-K_4K_2}{1 - K_2K_5}\right)\left[\frac{1}{\left(\frac{\tau_1\tau_2}{1 - K_2K_5}\right)s^2 + \left(\frac{\tau_1 + \tau_2}{1 - K_2K_5}\right)s + 1}\right] \quad (4-40)$$

En la figura 4-8 se muestra el diagrama de bloques para este sistema, el cual se obtiene mediante el encadenamiento de las ecuaciones (4-36) y (4-37).

Se puede apreciar que estas tres funciones de transferencia, ecuaciones (4-38), (4-39) y (4-40), son de segundo orden. La ecuación (4-38) es un poco diferente de las otras dos; específicamente, ésta tiene el término $(\tau_2s + 1)$ en el numerador. Tal tipo de función de transferencia se trata más adelante en este capítulo, por el momento es importante comprender el significado de las tres funciones de transferencia de segundo orden mencionadas aquí. Por ejemplo, considérese la temperatura de entrada del agua de enfriamiento. Si $T_{c_i}(t)$ cambia, esto afecta primero a la temperatura de la camisa y después a la del fluido que se procesa; aquí hay dos sistemas de primer orden en serie. El mismo comportamiento dinámico también es válido para un cambio en el flujo del agua de enfriamiento, como se puede apreciar en las funciones de transferencia, ecuaciones (4-39) y (4-40), cuyos términos dinámicos son exactamente los mismos. La primera función de transferencia, ecuación (4-38), indica que la dinámica del cambio en la temperatura de entrada del fluido procesado, $T_i(t)$, sobre $T(t)$ es diferente de la de las otras dos perturbaciones y, como se mencionó anteriormente, dichas diferencias se explican más adelante en este capítulo.

En este ejemplo se utilizó la expresión de tasa de transferencia de calor $UA[T(t) - T_c(t)]$, pero al hacerlo se despreció la dinámica de las paredes del tanque, ya que se supuso que, tan pronto como cambia la temperatura del agua de enfriamiento, el fluido procesado experimenta un cambio en la transferencia de calor, sin embargo, esto no es así. Cuando se modifica la temperatura del agua de enfriamiento, también cambia la transferencia de calor en las paredes del tanque y, consecuentemente, empieza a variar la temperatura de las paredes; es entonces cuando cambia la transferencia de calor de las paredes al líquido que se procesa. Por tanto, la pared del tanque representa otra capacitancia en el sistema, y la magnitud de ésta depende, entre otras cosas, del espesor, densidad, capacidad calorífica y otras propiedades físicas del material con que se construye la pared.

Al tomar en cuenta la pared, se tiene un mejor entendimiento de dicha capacitancia. Se puede suponer que ambas superficies de la pared del tanque, la que está cerca del líquido que se procesa y la que está cerca del agua de enfriamiento, tienen la misma temperatura; tal suposición es buena cuando la pared no es muy gruesa y tiene una gran conductividad térmica.

Entonces, el balance de energía en el fluido que se procesa cambia a:

$$q\rho C_pT_i(t) - h_iA_i(T(t) - T_m(t)) - q\rho C_pT(t) = V\rho C_v\frac{dT(t)}{dt} \quad (4-41)$$

donde:
- $h_i$ = coeficiente de transferencia calorífica de la cara interna, se supone constante, $J/m^2-s-K$
- $A_i$ = área interna de transferencia de calor, $m^2$
- $T_m(t)$ = temperatura de la pared de metal, K

Al proceder con un balance de energía de estado dinámico para la pared del tanque, se puede escribir:

$$h_iA_i(T(t) - T_m(t)) - h_oA_o(T_m(t) - T_c(t)) = V_m\rho_mC_{v_m}\frac{dT_m(t)}{dt} \quad (4-42)$$

donde:
- $h_o$ = coeficiente de transferencia de calor de la cara externa, se supone constante, $J/m^2-s-K$
- $A_o$ = área externa de transferencia de calor, $m^2$
- $V_m$ = volumen de la pared de metal, $m^3$
- $\rho_m$ = densidad de la pared de metal, $kg/m^3$
- $C_{v_m}$ = capacidad calorífica del metal de la pared, J/kg-K

Finalmente, con un balance de energía de estado dinámico para el agua de enfriamiento se obtiene la otra ecuación que se necesita:

$$q_c(t)\rho_cC_{p_c}T_{c_i}(t) + h_oA_o(T_m(t) - T_c(t)) - q_c(t)\rho_cC_{p_c}T_c(t) = V_c\rho_cC_{v_c}\frac{dT_c(t)}{dt} \quad (4-43)$$

Aquí se requirieron tres ecuaciones diferenciales para describir completamente el sistema. Para desarrollar la siguiente función de transferencia a partir de la ecuación (4-41) se utiliza el procedimiento que ya se aprendió:

$$T(s) = \frac{K_6}{\tau_3s + 1}T_i(s) + \frac{K_7}{\tau_3s + 1}T_m(s) \quad (4-44)$$

En la figura 4-9 se muestra el diagrama de bloques que representa esta ecuación. De la ecuación (4-42) se obtiene:

$$T_m(s) = \frac{K_8}{\tau_4s + 1}T(s) + \frac{K_9}{\tau_4s + 1}T_c(s) \quad (4-45)$$

y, finalmente, a partir de la ecuación (4-43), se tiene:

$$T_c(s) = \frac{K_{10}}{\tau_5s + 1}T_{c_i}(s) + \frac{K_{11}}{\tau_5s + 1}T_m(s) - \frac{K_{12}}{\tau_5s + 1}Q_c(s) \quad (4-46)$$

donde:

$$\tau_3 = \frac{V\rho C_v}{q\rho C_p + h_iA_i}, \text{ segundos}$$
$$K_6 = \frac{q\rho C_p}{q\rho C_p + h_iA_i}, \text{ sin dimensiones}$$
$$K_7 = \frac{h_iA_i}{q\rho C_p + h_iA_i}, \text{ sin dimensiones}$$
$$\tau_4 = \frac{V_m\rho_mC_{v_m}}{h_iA_i + h_oA_o}, \text{ segundos}$$
$$K_8 = \frac{h_iA_i}{h_iA_i + h_oA_o}, \text{ sin dimensiones}$$
$$K_9 = \frac{h_oA_o}{h_iA_i + h_oA_o}, \text{ sin dimensiones}$$
$$\tau_5 = \frac{V_c\rho_cC_{v_c}}{h_oA_o + \bar{q}_c\rho_cC_{p_c}}, \text{ segundos}$$
$$K_{10} = \frac{\bar{q}_c\rho_cC_{p_c}}{h_oA_o + \bar{q}_c\rho_cC_{p_c}}, \text{ sin dimensiones}$$
$$K_{11} = \frac{h_oA_o}{h_oA_o + \bar{q}_c\rho_cC_{p_c}}, \text{ sin dimensiones}$$
$$K_{12} = \frac{\rho_cC_{p_c}(\bar{T}_c - \bar{T}_{c_i})}{h_oA_o + \bar{q}_c\rho_cC_{p_c}}, \text{ K/m}^3\text{-s}$$

El encadenamiento de las ecuaciones (4-45) y (4-46) con la (4-44) da por resultado el diagrama de bloques que se muestra en la figura 4-10.

Para determinar las funciones de transferencia requeridas se substituye la ecuación (4-46) en la (4-45):

$$T_m(s) = \frac{K_8(\tau_5s + 1)}{(\tau_4s + 1)(\tau_5s + 1) - K_9K_{11}}T(s)$$
$$+ \frac{K_9K_{10}}{(\tau_4s + 1)(\tau_5s + 1) - K_9K_{11}}T_{c_i}(s)$$
$$- \frac{K_9K_{12}}{(\tau_4s + 1)(\tau_5s + 1) - K_9K_{11}}Q_c(s)$$

De la substitución de esta última ecuación en la (4-44), se tiene:

$$T(s) = \frac{K_6}{\tau_3s + 1}T_i(s)$$
$$+ \frac{K_7K_8(\tau_5s + 1)}{(\tau_3s + 1)[(\tau_4s + 1)(\tau_5s + 1) - K_9K_{11}]}T(s)$$
$$+ \frac{K_7K_9}{(\tau_3s + 1)[(\tau_4s + 1)(\tau_5s + 1) - K_9K_{11}]}(K_{10}T_{c_i}(s) - K_{12}Q_c(s))$$

y, después de trabajar algebraicamente, se tiene:

$$T(s) = \frac{K_6(1 - K_9K_{11})}{1 - K_9K_{11} - K_7K_8}\left[\frac{\tau_6^2s^2 + \tau_7s + 1}{\tau_8^3s^3 + \tau_9^2s^2 + \tau_{10}s + 1}\right]T_i(s)$$
$$+ \left(\frac{K_7K_9}{1 - K_9K_{11} - K_7K_8}\right)\left[\frac{1}{\tau_8^3s^3 + \tau_9^2s^2 + \tau_{10}s + 1}\right](K_{10}T_{c_i}(s) - K_{12}Q_c(s))$$

donde:

$$\tau_6 = \left(\frac{\tau_4\tau_5}{1 - K_9K_{11}}\right)^{1/2}, \text{ segundos}$$
$$\tau_7 = \frac{\tau_4 + \tau_5}{1 - K_9K_{11}}, \text{ segundos}$$
$$\tau_8 = \left(\frac{\tau_3\tau_4\tau_5}{1 - K_9K_{11} - K_7K_8}\right)^{1/3}, \text{ segundos}$$
$$\tau_9 = \left(\frac{\tau_4\tau_5 + \tau_3\tau_4 + \tau_3\tau_5}{1 - K_9K_{11} - K_7K_8}\right)^{1/2}, \text{ segundos}$$
$$\tau_{10} = \frac{\tau_3(1 - K_9K_{11}) + \tau_4 + \tau_5 - K_7K_8K_5}{1 - K_9K_{11} - K_7K_8}, \text{ segundos}$$

A partir de la ecuación (4-47) se obtienen las funciones de transferencia que se desean:

$$\frac{T(s)}{T_i(s)} = \frac{K_6(1 - K_9K_{11})}{1 - K_9K_{11} - K_7K_8}\left[\frac{\tau_6^2s^2 + \tau_7s + 1}{\tau_8^3s^3 + \tau_9^2s^2 + \tau_{10}s + 1}\right] \quad (4-48)$$

$$\frac{T(s)}{T_{c_i}(s)} = \left(\frac{K_7K_9K_{10}}{1 - K_9K_{11} - K_7K_8}\right)\left[\frac{1}{\tau_8^3s^3 + \tau_9^2s^2 + \tau_{10}s + 1}\right] \quad (4-49)$$

$$\frac{T(s)}{Q_c(s)} = \left(\frac{-K_7K_9K_{12}}{1 - K_9K_{11} - K_7K_8}\right)\left[\frac{1}{\tau_8^3s^3 + \tau_9^2s^2 + \tau_{10}s + 1}\right] \quad (4-50)$$

Las funciones de transferencia que se expresan mediante las ecuaciones (4-49) y (4-50) son de tercer orden; es decir, el denominador es un polinomio de tercer orden en $s$. En el diagrama de bloques de la figura 4-10 se aprecia gráficamente que, si la temperatura de entrada del agua de enfriamiento cambia, lo primero que se afecta es la temperatura del agua en la camisa de enfriamiento, $T_c(t)$; por lo tanto, esta temperatura afecta, a su vez, a la de la pared de metal, $T_m(t)$; y, finalmente, esta temperatura influye en la del fluido que se procesa, $T(t)$. Aquí hay tres sistemas de primer orden en serie. Las funciones de transferencia son análogas a las expresadas mediante las ecuaciones (4-39) y (4-40); la función de transferencia de la ecuación (4-48), también de tercer orden, es un poco diferente a las ecuaciones (4-49) y (4-50) y semejante a la ecuación (4-38).

Este proceso térmico es otro ejemplo de un proceso interactivo; la interacción se desarrolla mediante la expresión de la tasa de transferencia de calor: $UA[T(t) - T_c(t)]$ en las ecuaciones (4-32) y (4-33); y $h_iA_i[T(t) - T_m(t)]$ y $h_oA_o[T_m(t) - T_c(t)]$, en las ecuaciones (4-41), (4-42) y (4-43). En el diagrama de bloques de las figuras 4-8 y 4-10 se muestra esta interacción gráficamente.

## 4-4. RESPUESTA DE LOS SISTEMAS DE ORDEN SUPERIOR A DIFERENTES TIPOS DE FUNCIONES DE FORZAMIENTO

Hasta aquí se desarrollaron dos tipos de funciones de transferencia de orden superior:

$$G(s) = \frac{Y(s)}{X(s)} = \prod_{i=1}^{n}G_i(s) = \frac{K}{\prod_{i=1}^{n}(\tau_is + 1)} \quad (4-51)$$

$$G(s) = \frac{Y(s)}{X(s)} = \frac{K\prod_{j=1}^{m}(\tau_{id_j}s + 1)}{\prod_{i=1}^{n}(\tau_{i}s + 1)} \quad (4-52)$$

donde $n > m$.

En esta sección se presenta la respuesta de estos sistemas de orden superior a diferentes tipos de funciones de forzamiento, específicamente a las funciones escalón y senoidal; a partir de estos estudios se pueden hacer algunas generalizaciones acerca de las respuestas.

### Función escalón

Primero se muestra la respuesta de los sistemas que se describen mediante la ecuación (4-51). Generalmente, una función de transferencia de segundo orden se escribe de cualquiera de las dos formas siguientes:

$$G(s) = \frac{Y(s)}{X(s)} = \frac{K}{(\tau_1s + 1)(\tau_2s + 1)} = \frac{K}{\tau_1\tau_2s^2 + (\tau_1 + \tau_2)s + 1} \quad (4-53)$$

o:

$$G(s) = \frac{Y(s)}{X(s)} = \frac{K}{\tau^2s^2 + 2\tau\xi s + 1} \quad (4-54)$$

donde:
- $\tau$ = constante de tiempo característica, tiempo
- $\xi$ = tasa de amortiguamiento, sin dimensiones

las relaciones entre los parámetros de las dos formas son:

$$\tau = \sqrt{\tau_1\tau_2} \quad (4-55)$$

Y:

$$\xi = \frac{\tau_1 + \tau_2}{2\sqrt{\tau_1\tau_2}} \quad (4-56)$$

La respuesta de una función de transferencia de segundo orden a un cambio escalón de magnitud unitaria en la función de forzamiento, $X(s) = 1/s$, se obtiene como sigue. A partir de la ecuación (4-54):

$$Y(s) = \frac{K}{s(\tau^2s^2 + 2\tau\xi s + 1)} = \frac{Kr_1r_2}{s(s - r_1)(s - r_2)} \quad (4-57)$$

donde:

$$r_1 = -\frac{\xi}{\tau} + \frac{\sqrt{\xi^2 - 1}}{\tau}$$
$$r_2 = -\frac{\xi}{\tau} - \frac{\sqrt{\xi^2 - 1}}{\tau} \quad (4-58)$$

De las dos últimas ecuaciones se infiere que la respuesta de este sistema depende del valor de la razón de amortiguamiento, $\xi$.

Para un valor de $\xi < 1$, las raíces $r_1$ y $r_2$ son complejas, y la respuesta que se obtiene del sistema, mediante el procedimiento que se estudió en el capítulo 2, se expresa mediante la siguiente ecuación:

$$Y(t) = K\left[1 - \frac{1}{\sqrt{1 - \xi^2}}e^{-\xi t/\tau}\sin\left(\sqrt{1 - \xi^2}\frac{t}{\tau} + \tan^{-1}\frac{\sqrt{1 - \xi^2}}{\xi}\right)\right] \quad (4-60)$$

La respuesta de este tipo de sistema se ilustra gráficamente en la figura 4-11; como se puede ver, la respuesta es oscilatoria y, por tanto, se dice que los sistemas de este tipo son **subamortiguados** (bajoamortiguados).

Para un valor de $\xi = 1$, las raíces son reales e iguales; la respuesta se expresa mediante:

$$Y(t) = K\left[1 - \left(1 + \frac{t}{\tau}\right)e^{-t/\tau}\right] \quad (4-61)$$

En la figura 4-11 se ilustra la respuesta de este sistema, la cual es la aproximación más rápida al valor final, sin sobrepasarlo, y, en consecuencia, no hay oscilación. Los sistemas en que $\xi = 1$ se denominan **críticamente amortiguados**.

Para un valor de $\xi > 1$ las raíces son reales y diferentes, la respuesta del sistema la da:

$$Y(t) = K\left[1 - 0.5e^{-\xi t/\tau}\left(e^{-\frac{\xi t}{\tau}\left(\frac{\xi}{\sqrt{\xi^2 - 1}} - 1\right)} + e^{\frac{\xi t}{\tau}\left(\frac{\xi}{\sqrt{\xi^2 - 1}} + 1\right)}\right)\right] \quad (4-62)$$

La respuesta de este tipo de sistema también se muestra en la figura 4-11. La respuesta jamás sobrepasa al valor final y su aproximación es más lenta que en los sistemas críticamente amortiguados. Se dice que este tipo de sistema está **sobreamortiguado**.

Los tres tipos de sistemas de segundo orden son muy importantes en el estudio del control automático de proceso. Las respuestas de los sistemas de control son semejantes a alguna de las arriba indicadas. La respuesta de circuito abierto de la mayoría de los procesos industriales es similar a la críticamente amortiguada o a la sobreamortiguada; esto es, generalmente no oscilan, sin embargo, puede haber oscilación cuando se cierra el circuito. La respuesta de los sistemas con circuito cerrado se aborda en el capítulo 6.

Es importante reconocer las diferencias entre la respuesta de los sistemas de segundo orden y la de los de primer orden, cuando se les somete a cambios escalón en la función de forzamiento. La diferencia más notable es que, en los sistemas de segundo orden, la pendiente mayor no se presenta al inicio de la respuesta, sino tiempo después; en los sistemas de primer orden, como se demostró en el capítulo anterior, la mayor pendiente ocurre al principio de la respuesta. Otra diferencia es que los sistemas de primer orden no oscilan; mientras que en los de segundo orden sí puede haber oscilación.

Como se ve en la figura 4-11, la cantidad de amortiguamiento en un sistema de segundo orden se expresa mediante la razón de amortiguamiento, y ésta, así como la constante de tiempo característica, $\tau$, depende de los parámetros físicos del proceso. Si cualquiera de los parámetros físicos cambia, el cambio se refleja en una variación en $\xi$, en $\tau$, o en ambas.

El análisis de la respuesta del sistema subamortiguado es de particular interés en el estudio del control automático de proceso, esto se debe al hecho de que, como se mencionó anteriormente, la respuesta de la mayoría de los circuitos cerrados es semejante a la respuesta subamortiguada. A causa de esta semejanza, se deben definir algunos términos importantes en relación con la respuesta subamortiguada; tales términos se definen a continuación, con referencia a la figura 4-12.

**Sobrepaso.** El "sobrepaso" es la cantidad en que la respuesta excede el valor final de estado estacionario; generalmente se expresa como la relación de $B/A$:

$$\frac{B}{A} = e^{-\pi\xi/\sqrt{1 - \xi^2}} \quad (4-63)$$

**Razón de asentamiento.** La razón de asentamiento se define como:

$$\frac{C}{B} = e^{-2\pi\xi/\sqrt{1 - \xi^2}} \quad (4-64)$$

Este es un término importante, ya que sirve como criterio para establecer la respuesta satisfactoria de los sistemas de control.

**Tiempo de elevación, $t_R$.** Es el tiempo que tarda la respuesta en alcanzar por primera vez el valor final.

**Tiempo de asentamiento, $t_S$.** Es el tiempo que tarda la respuesta en llegar a ciertos límites preestablecidos del valor final y permanecer dentro de ellos. Dichos límites son arbitrarios; los valores típicos son $\pm 5\%$ o $\pm 3\%$.

**Período de oscilación, $T$.** El período de oscilación se expresa mediante:

$$T = \frac{2\pi\tau}{\sqrt{1 - \xi^2}}, \text{ tiempo/ciclo} \quad (4-65)$$

Otro término relacionado con el período de oscilación es la **frecuencia cíclica**, $f$, que se define como sigue:

$$f = \frac{1}{T} = \frac{\sqrt{1 - \xi^2}}{2\pi\tau}, \text{ ciclos/tiempo} \quad (4-66)$$

Otros dos términos son el **período natural de oscilación** y la **frecuencia cíclica natural**, cuando $\xi = 0$; se definen como:

$$T_n = 2\pi\tau \quad (4-67)$$

Y:

$$f_n = \frac{1}{2\pi\tau} \quad (4-68)$$

Frecuentemente también se usa la siguiente expresión para una función de transferencia de segundo orden:

$$G(s) = \frac{Y(s)}{X(s)} = \frac{K}{\frac{s^2}{\omega_n^2} + \frac{2\xi}{\omega_n}s + 1} \quad (4-69)$$

El término $\omega_n$ se conoce como **frecuencia natural**. Al comparar la ecuación (4-69) con la (4-54), se ve fácilmente que:

$$\omega_n = \frac{1}{\tau} \quad (4-70)$$

La frecuencia en radianes, $\omega$, se relaciona con la frecuencia cíclica, $f$, mediante:

$$\omega = 2\pi f \quad (4-71)$$

y, por substitución de la ecuación (4-66) en la (4-71), se relaciona la frecuencia en radianes con la frecuencia natural:

$$\omega = 2\pi f = \frac{2\pi\sqrt{1 - \xi^2}}{2\pi\tau} = \frac{\sqrt{1 - \xi^2}}{\tau} = \omega_n\sqrt{1 - \xi^2} \quad (4-72)$$

Toda la exposición anterior se aplica a sistemas de segundo orden. Para los sistemas de tercer orden o de orden superior, cuyas constantes de tiempo son reales y distintas, la respuesta a un cambio escalón de magnitud unitaria la da la ecuación (4-73), como se muestra en la figura 4-13:

$$Y(t) = K\left[1 - \sum_{i=1}^{n}\frac{\tau_i^{n-1}e^{-t/\tau_i}}{\prod_{j=1, j\neq i}^{n}(\tau_i - \tau_j)}\right] \quad (4-73)$$

En el capítulo 2 se presentó el método general para la solución de otros tipos de constantes de tiempo.

Probablemente la característica más importante de las respuestas que se muestran en la figura 4-13 es que parecen muy similares a la respuesta de un sistema de segundo orden sobreamortiguado con alguna cantidad de tiempo muerto. Conforme aumenta el orden del sistema, también aumenta el tiempo muerto aparente, lo cual es importante en el estudio del control automático de proceso, porque la mayoría de los procesos industriales se componen de una cierta cantidad de sistemas de primer orden en serie. Además, a causa de la similitud, la respuesta de un sistema de tercer orden, o de cualquier otro de orden superior, se puede aproximar mediante la respuesta de un sistema de segundo orden más tiempo muerto. Lo anterior se representa matemáticamente como sigue:

$$\frac{Y(s)}{X(s)} = \frac{K}{\prod_{i=1}^{n}(\tau_is + 1)} \approx \frac{Ke^{-t_0s}}{(\tau_1s + 1)(\tau_2s + 1)} \quad (4-74)$$

Matemáticamente esta aproximación es muy buena.

Hasta aquí se ha tratado la respuesta de los procesos que se describen mediante la ecuación (4-51). Ahora se tratará la respuesta a un cambio escalón de magnitud unitaria en la función de forzamiento, $X(s) = 1/s$, de los procesos que se describen mediante la ecuación (4-52). En general, la respuesta para sistemas con raíces reales y distintas se representa mediante la siguiente ecuación:

$$Y(t) = K\left[1 - \sum_{i=1}^{n}\frac{\prod_{j=1}^{m}(\tau_{ld_j} - \tau_i)\tau_i^{m-1}}{\prod_{j=1, j\neq i}^{n}(\tau_j - \tau_i)}e^{-t/\tau_i}\right] \quad (4-75)$$

Para lograr una mejor comprensión del término $(\tau_{ld}s + 1)$, compárese la respuesta de los dos procesos siguientes:

$$Y_1(s) = \frac{1}{s(\tau_{lg_1}s + 1)(\tau_{lg_2}s + 1)(\tau_{lg_3}s + 1)} \quad (4-76)$$

Y:

$$Y_2(s) = \frac{(\tau_{ld}s + 1)}{s(\tau_{lg_1}s + 1)(\tau_{lg_2}s + 1)(\tau_{lg_3}s + 1)} \quad (4-77)$$

En la figura 4-14 se comparan las respuestas; la respuesta para $\tau_{ld} = 0$ corresponde a la ecuación (4-76). El efecto del término $(\tau_{ld}s + 1)$ es "acelerar" la respuesta del proceso, lo cual es opuesto al efecto del término $1/(\tau_{lg}s + 1)$; en el capítulo 3 se hizo referencia al término $1/(\tau_{lg}s + 1)$ como retardo de primer orden y, en consecuencia, al término $(\tau_{ld}s + 1)$ se le conoce como **adelanto de primer orden**; por tal motivo se utiliza la notación $\tau_{lg}s$ para indicar un "retardo" en la constante de tiempo; y $\tau_{ld}s$ para indicar un "adelanto". Nótese que, cuando $\tau_{ld}$ se hace igual a $\tau_{lg}$, la función de transferencia con que se describe la relación entre $Y(s)$ y $X(s)$ se vuelve inferior en un orden, cuando no tiene el término de adelanto.

Un caso interesante e importante es el de la siguiente función de transferencia:

$$\frac{Y(s)}{X(s)} = \frac{\tau_{ld}s + 1}{\tau_{lg}s + 1} \quad (4-78)$$

La respuesta de esta función de transferencia a un cambio escalón unitario se muestra en la figura 4-15. El efecto del término de adelanto es hacer que la respuesta inicial sea mayor que la unidad, y después decae exponencialmente hasta el valor final de estado estacionario.

### Función senoidal

Ahora se estudia la respuesta de un sistema de segundo orden a una función senoidal. Sea la función de forzamiento:

$$X(t) = A\sin \omega t \, u(t) \quad (4-79)$$

En el dominio de Laplace:

$$X(s) = \frac{A\omega}{s^2 + \omega^2}$$

Entonces:

$$Y(s) = \frac{KA\omega}{(s^2 + \omega^2)(\tau^2s^2 + 2\tau\xi s + 1)}$$

Al regresar al dominio del tiempo se tiene:

$$Y(t) = e^{-\xi t/\tau}\left(C_1\cos\sqrt{1 - \xi^2}\frac{t}{\tau} + C_2\sin\sqrt{1 - \xi^2}\frac{t}{\tau}\right) + \frac{KA}{[1 - (\omega\tau)^2]^2 + (2\xi\omega\tau)^2}\sin(\omega t + \theta) \quad (4-80)$$

donde:

$$\theta = -\tan^{-1}\left(\frac{2\xi\omega\tau}{1 - (\omega\tau)^2}\right) \quad (4-81)$$

$C_1, C_2$ = constantes a evaluar

Conforme el tiempo aumenta, el término $e^{-\xi t/\tau}$ se vuelve despreciable y la respuesta alcanza una oscilación estacionaria que se expresa mediante:

$$Y(t)\big|_{t\to\infty} = \frac{KA}{\sqrt{[1 - (\omega\tau)^2]^2 + (2\xi\omega\tau)^2}}\sin(\omega t + \theta) \quad (4-82)$$

Como se verá en el capítulo 7, tal respuesta se vuelve importante en el estudio del control automático de proceso. La oscilación estacionaria se conoce como **respuesta en frecuencia** del sistema, cuya amplitud es igual a la ganancia del sistema multiplicada por la amplitud de la función forzada y la atenúa el factor:

$$\sqrt{[1 - (\omega\tau)^2]^2 + (2\xi\omega\tau)^2}$$

Como se definió en la sección 3-7, la relación de amplitud para este sistema es:

$$\sqrt{[1 - (\omega\tau)^2]^2 + (2\xi\omega\tau)^2}$$

Tanto la relación de amplitud como el retardo de fase, $\theta$, son funciones de $\omega$, frecuencia de la función forzada. En el capítulo 7 se examina también la respuesta en frecuencia de otros sistemas de orden superior.

## 4-5. RESUMEN

En este capítulo se presentó el desarrollo de los modelos matemáticos con que se describe el comportamiento de los procesos de orden superior. Los procesos que se expusieron son más complejos que los del capítulo 3 y, en consecuencia, los modelos son también más complejos. En particular, se desarrollaron funciones de transferencia de segundo y tercer orden; los ejemplos que se utilizaron representan casos de procesos interactivos y no interactivos. También se presentaron las respuestas de estos sistemas de orden superior a un cambio escalón y senoidal en las funciones de forzamiento; asimismo se describieron e hicieron notar las diferencias entre estas respuestas y las de los sistemas de primer orden; probablemente la diferencia más importante sea la respuesta a un cambio escalón en la función de forzamiento; por el contrario para los sistemas de primer orden, la pendiente inicial de la respuesta es la más pronunciada de la curva completa de respuesta; para los sistemas de orden superior éste no es el caso, ya que la pendiente más pronunciada ocurre más tarde en la curva de respuesta.

Los sistemas de orden superior presentados en este capítulo se obtuvieron porque se componen de sistemas de primer orden en serie, es decir, dichos sistemas no son intrínsecamente de orden superior. La mayoría de los procesos industriales son como los expuestos aquí; si existen algunos procesos intrínsecamente de orden superior, son pocos y bastante aislados. Los ejemplos típicos de sistemas intrínsecos de segundo orden que se presentan en los textos de control son elementos de medición tales como los sensores de presión de tubo de Bourdon y los manómetros de mercurio, los cuales son parte del circuito total de control y, sin embargo, las más de las veces su dinámica no es significativa, en comparación con el proceso mismo, por tal motivo no se consideran aquí y se remite al lector a las referencias bibliográficas 1 y 2 para consultas al respecto.

Puesto que la mayoría de los procesos industriales se compone de procesos de primer orden en serie, su respuesta dinámica de circuito abierto es sobreamortiguada, pero una vez que se cierra el circuito de control, mediante la instalación de un controlador en la retroalimentación su respuesta se puede convertir en subamortiguada; este caso se estudia en el capítulo 6.

## BIBLIOGRAFÍA

1. Close, C. M. y D. K. Frederick, *Modeling and Analysis of Dynamic Systems*, Houghton Mifflin, Boston, 1978.
2. Tyner, M. y F. P. May, *Process Engineering Control*, Ronald Press, Nueva York, 1968.

## PROBLEMAS

**4-1.** Considérese el proceso que se muestra en la figura 4-16, la tasa de flujo de líquido, $w$, a través de los tanques tiene un valor constante de 250 lbm/min. Se puede suponer que la densidad del líquido se mantiene constante a 50 lbm/pie$^3$, al igual que la capacidad calorífica, la cual posee un valor de 1.3 Btu/lbm-°F; el volumen de cada tanque es de 10 pies$^3$. Las pérdidas de calor al ambiente son despreciables.

Se debe dibujar el diagrama de bloques donde se muestre la manera en que los cambios de la temperatura de entrada $T_i(t)$ y $q(t)$ afectan a $T_3(t)$. Es necesario también anotar los valores numéricos y las unidades de cada parámetro en todas las funciones de transferencia.

**4-2.** Considérese el proceso que se muestra en la figura 4-17, acerca del cual se sabe lo siguiente:

a) La densidad de todas las corrientes es aproximadamente igual.
b) El flujo a través de la bomba, con velocidad constante, se expresa mediante:

$$q(t) = A(1 + B(p_1(t) - p_2(t))^2), \quad m^3/s$$

donde A y B son constantes.

c) El conducto entre los puntos 2 y 3 es más bien largo, con longitud de $L$, m. El flujo a través de este conducto es altamente turbulento (flujo de acoplamiento); el diámetro del mismo es de $D$, m; la caída de presión entre los dos puntos es bastante constante y vale $\Delta p$ kPa.

d) Se puede suponer que los efectos de energía que se asocian a la reacción (A → B) son despreciables; en consecuencia, la reacción ocurre a una temperatura constante. La tasa de reacción se expresa mediante:

$$r_A(t) = kC_A(t), \quad \frac{kgm}{m^3-s}$$

e) El flujo a través de la válvula de salida lo da:

$$q(t) = C_vvp(t)\sqrt{h_2(t)}$$

Obténgase el diagrama de bloques donde se muestre el efecto de las funciones forzadas $q_2(t)$, $vp(t)$ y $C_{A1}(t)$ sobre las variables de respuesta $h_1(t)$, $h_2(t)$ y $C_{A3}(t)$.

**4-3.** Considérese el proceso que se muestra en la figura 4-18, en el que se mezclan diferentes corrientes. Las corrientes 5, 2 y 7 son soluciones de agua con el componente A; la corriente 1 es de agua pura. En la tabla 8-4 aparecen los valores de estado estacionario para cada corriente. Se deben determinar las siguientes funciones de transferencia con valores numéricos:

$$\frac{X_5(s)}{X_6(s)} \qquad \text{y} \qquad \frac{X_6(s)}{Q_1(s)}$$

**4-4.** Considérese el proceso que se muestra en la figura 4-19; a uno de los tanques entra una corriente de gas, $q_2(t)$, donde se mezcla con otra corriente, $q_1(t)$, la cual es A puro; de este tanque la mezcla gaseosa fluye a un separador en donde el componente A se difunde, a través de una membrana semipermeable, a un líquido puro. Se puede suponer lo siguiente:

a) La caída de presión a través de la válvula es constante, y el flujo de A puro a través de esta válvula se expresa mediante:

$$q_1(t) = k_1vp(t)$$

donde $q_1(t)$ está en scfh. La posición de la válvula, $vp(t)$, se relaciona con la señal neumática, $m(t)$, mediante la siguiente expresión:

$$vp(t) = \frac{1}{12}(m(t) - 3)$$

b) El flujo volumétrico de salida, $q_3(t)$, del tanque es igual a la suma de los flujos de entrada; el gas se comporta como un fluido incompresible.

c) El gas en el interior del tanque está bien mezclado.

d) Se supone que el gas en el separador está bien mezclado, lo mismo se supone para el líquido.

e) La tasa de transferencia de masa a través de la membrana semipermeable la da:

$$N_A(t) = A_XK_A[c_{A_3}(t) - c_{A_4}(t)]$$

donde:
- $N_A(t)$ = tasa de transferencia de masa, lb mol A/h
- $A_X$ = área transversal de la membrana, pies$^2$
- $K_A$ = coeficiente de transferencia global de masa, pies/h

f) La cantidad de componente A que se difunde en el líquido no afecta significativamente al flujo volumétrico de gas y, por lo tanto, se puede considerar que el flujo que sale del separador es igual al que entra.

g) La cantidad de componente A que se difunde en el líquido sí afecta al flujo volumétrico; la densidad del flujo de líquido que sale del separador se expresa mediante:

$$\rho_5(t) = \rho_4 + k_5c_{A_5}(t), \quad \text{lb moles/pies}^3$$

Se debe hacer lo siguiente:

1. Escribir el modelo matemático del tanque.
2. Escribir el modelo matemático del separador.
3. Dibujar el diagrama de bloques donde se muestren las variables de salida $C_{A_4}(t)$ y $C_{A_5}(t)$ con la manera en que las afectan $m(t)$, $q_2(t)$ y $C_{A_2}(t)$. También se deben obtener las funciones de transferencia.

**4-5.** Considérese la unidad de extracción que se ilustra en la figura 4-20; el objeto de la unidad es remover el componente A de un compuesto rico en B. La transferencia de A a un medio acuoso se realiza a través de una membrana semipermeable; en este proceso la concentración de A es una función de la posición a lo largo de la unidad y del tiempo y, por tanto, la ecuación con que se describe la concentración es una ecuación diferencial parcial (EDP) de longitud y tiempo. Los sistemas que se describen mediante EDP se conocen como "sistemas distribuidos"; en el capítulo 9 se presentan más sistemas de este tipo. Una manera común de proceder con las EDP es dividir la unidad en secciones o "estanques" y suponer que en cada "estanque" la mezcla es buena; mediante las líneas punteadas se muestra la división en "estanques". Mediante dicho método se encuentra que las diferenciales de longitud, $dL$, se pueden aproximar mediante $\Delta L$; mientras más pequeños son los "estanques", mejor es la aproximación.

La transferencia de masa del componente A es:

$$N_A(t) = Sk_A\{x_{A_{n,1}}(t) - x_{A_{n,2}}^*(t)\}$$

donde:
- $N_A(t)$ = moles de A que se transfieren por segundo
- $S$ = superficie de la membrana a través de la cual tiene lugar la transferencia, $m^2$
- $k_A$ = coeficiente de transferencia, constante, mol A/$m^2$-s
- $x_{A_{n,1}}(t)$ = fracción de mol de A en la fase líquida 1 (fase rica en componente B); el subíndice $n$ se refiere al número de "estanque"
- $x_{A_{n,2}}^*(t)$ = fracción de mol de A en la fase líquida 2 (fase rica en agua), la cual debe estar en equilibrio con $x_{A_{n,1}}(t)$

Con la ley de Henry se puede relacionar $x_{A_{n,2}}^*(t)$ con la concentración real de A en la fase líquida 2:

$$x_{A_{n,2}}^*(t) = H_Ax_{A_{n,2}}(t)$$

donde:
- $H$ = constante de la ley de Henry
- $x_{A_{n,2}}(t)$ = fracción de mol de A en la fase líquida 2

Ni el componente B ni el agua se transfieren a través de la membrana y el proceso se realiza de manera isotérmica. Obténgase el diagrama de bloque donde se muestre cómo afectan las funciones de forzamiento $x_{A_{i,1}}(t)$, $F_{i,1}(t)$ y $F_{i,2}(t)$ a las variables de salida $x_{A_{2,1}}(t)$ y $x_{A_{2,2}}(t)$; es decir, se deben elaborar los dos primeros "estanques".

---

# Capítulo 5: Componentes básicos de los sistemas de control

En el capítulo 1 se vio que los cuatro componentes básicos de los sistemas de control son los sensores, los transmisores, los controladores y los elementos finales de control; también se vio que tales componentes desempeñan las tres operaciones básicas de todo sistema de control: medición (M), decisión (D) y acción (A).

En este capítulo se hace una breve revisión de los sensores y los transmisores, a la cual sigue un estudio más detallado de las válvulas de control y de los controladores de proceso. En el apéndice C se presentan más ampliamente los diferentes tipos de transmisores, sensores y válvulas de control; en el mismo apéndice se muestran varios diagramas, esquemas y otras figuras que sirven de apoyo para explicar y familiarizar al lector con tantos instrumentos como es posible.

## 5-1. SENSORES Y TRANSMISORES

Con los sensores y transmisores se realizan las operaciones de medición en el sistema de control. En el sensor se produce un fenómeno mecánico, eléctrico o similar, el cual se relaciona con la variable de proceso que se mide; el transmisor, a su vez, convierte este fenómeno en una señal que se puede transmitir y, por lo tanto, ésta tiene relación con la variable del proceso.

Existen tres términos importantes que se relacionan con la combinación sensor/transmisor: la **escala**, el **rango** y el **cero** del instrumento. A la escala del instrumento la definen los valores superior e inferior de la variable a medir del proceso; esto es, si se considera que un sensor/transmisor se calibra para medir la presión entre 20 y 50 psig de un proceso, se dice que la escala de la combinación sensor/transmisor es de 20-50 psig. El **rango** del instrumento es la diferencia entre el valor superior y el inferior de la escala, para el instrumento citado aquí el rango es de 30 psig. En resumen, para definir la escala del instrumento se deben especificar un valor superior y otro inferior; es decir, es necesario dar dos números; mientras que el rango es la diferencia entre los dos valores. Para terminar, el valor inferior de la escala se conoce como **cero del instrumento**, este valor no necesariamente debe ser cero para llamarlo así; en el ejemplo dado más arriba el "cero" del instrumento es de 20 psig.

En el apéndice C se presentan algunos de los sensores industriales más comunes: de presión, de flujo, de temperatura y de nivel. En el mismo apéndice se estudian los principios de funcionamiento tanto de un transmisor eléctrico como de uno neumático.

Como se verá en el capítulo 6, para el análisis del sistema algunas veces es importante obtener los parámetros con que se describe el comportamiento del sensor/transmisor; la ganancia es bastante fácil de obtener una vez que se conoce el rango. Considérese un sensor/transmisor electrónico de presión cuya escala va de 0-200 psig; en el capítulo 3 se definió la ganancia como el cambio en la salida o variable de respuesta entre el cambio en la entrada o función de forzamiento; en el ejemplo citado aquí, la salida es la señal electrónica, 4-20 mA; y la entrada es la presión en el proceso, 0-200 psig; por tanto:

$$K_T = \frac{20\,mA - 4\,mA}{200\,psig - 0\,psig} = \frac{16\,mA}{200\,psig} = 0.08\frac{mA}{psig}$$

Si se considera como otro ejemplo un sensor/transmisor neumático de temperatura, con escala de 100-300°F, la ganancia es:

$$K_T = \frac{15\,psig - 3\,psig}{300°F - 100°F} = \frac{12\,psi}{200°F} = 0.06\frac{psi}{°F}$$

Por tanto, se puede decir que la ganancia del sensor/transmisor es la relación del rango de la entrada respecto al rango de la salida.

En los dos ejemplos se observa que la ganancia del sensor/transmisor es constante, sobre todo el rango de operación, lo cual es cierto para la mayoría de los sensores/transmisores; sin embargo, existen algunos casos en que esto no es cierto, por ejemplo, en el sensor diferencial de presión que se usa para medir flujo, mediante el cual se mide el diferencial de presión, $h$, en la sección transversal de un orificio, mismo que, a su vez, se relaciona con el cuadrado del índice de flujo volumétrico, $F$, es decir:

$$F^2 \propto h$$

Cuando se usa el transmisor electrónico de diferencial de presión para medir un flujo volumétrico con rango de $0 - F_{max}$ gpm, la ecuación con que se describe la señal de salida es:

$$M_F = 4 + \frac{16}{(F_{max})^2}F^2$$

donde:
- $M_F$ = señal de salida en mA
- $F$ = flujo volumétrico

A partir de esta ecuación se obtiene la ganancia del transmisor como sigue:

$$K_T = \frac{dM_F}{dF} = \frac{2(16)}{(F_{max})^2}F$$

La ganancia nominal es:

$$K_T' = \frac{16}{F_{max}}$$

En esta expresión se aprecia que la ganancia no es constante, antes bien, está en función del flujo; tanto mayor sea el flujo, cuanto mayor será la ganancia. Específicamente:

$$K_T = 2K_T'\frac{F}{F_{max}}$$

De manera que la ganancia real varía de cero hasta dos veces la ganancia nominal. De este hecho resulta la no linealidad de los sistemas de control de flujo. Actualmente la mayoría de los fabricantes ofrecen transmisores de diferencial de presión en los que se interconstruye un extractor de raíz cuadrada, con lo que se logra un transmisor lineal. En el capítulo 8 se trata con más detalle el uso de los extractores de raíz cuadrada.

La respuesta dinámica de la mayoría de los sensores/transmisores es mucho más rápida que la del proceso; en consecuencia, sus constantes de tiempo y tiempo muerto se pueden considerar despreciables y, por tanto, su función de transferencia la da la ganancia pura; sin embargo, cuando se analiza la dinámica, la función de transferencia del instrumento generalmente se representa mediante un sistema de primer o segundo orden:

$$G(s) = \frac{K_T}{\tau s + 1} \qquad \text{o} \qquad G(s) = \frac{K_T}{\tau^2s^2 + 2\tau\xi s + 1}$$

Los parámetros dinámicos se obtienen casi siempre de manera empírica, mediante métodos similares a los que se presentan en los capítulos 6 y 7.

## 5-2. VÁLVULAS DE CONTROL

Las válvulas de control son los elementos finales de control más usuales y se les encuentra en las plantas de proceso, donde manejan los flujos para mantener en los puntos de control las variables que se deben controlar. En esta sección se hace una introducción a los aspectos más importantes de las válvulas de control para su aplicación al control de proceso.

La válvula de control actúa como una resistencia variable en la línea de proceso; mediante el cambio de su apertura se modifica la resistencia al flujo y, en consecuencia, el flujo mismo. Las válvulas de control no son más que reguladores de flujo.

En esta sección se presenta la acción de la válvula de control (en condición de falla), su dimensionamiento y sus características. En el apéndice C se presentan diferentes tipos de válvulas de control y sus accesorios. Se recomienda encarecidamente al lector leer el apéndice C junto con esta sección.

### Funcionamiento de la válvula de control

La primera pregunta que debe contestar el ingeniero cuando elige una válvula de control es: ¿Cómo se desea que actúe la válvula cuando falla la energía que la acciona? La pregunta se relaciona con la "posición en falla" de la válvula y el principal factor que se debe tomar en cuenta para contestar esta pregunta es, o debe ser, la seguridad. Si el ingeniero decide que por razones de seguridad la válvula se debe cerrar, entonces debe especificar que se requiere una válvula "cerrada en falla" (CF) (FC por sus siglas en inglés); la otra posibilidad es la válvula "abierta en falla" (AF); es decir, cuando falle el suministro de energía, la válvula debe abrir paso al flujo. La mayoría de las válvulas de control se operan de manera neumática y, consecuentemente, la energía que se les aplica es aire comprimido. Para abrir una válvula cerrada en falla se requiere energía y, por ello, también se les conoce como válvulas de "aire para abrir" (AA) (AO por sus siglas en inglés). Las válvulas abiertas en falla, en las que se requiere energía para cerrarlas, se conocen también como de "aire para cerrar" (AC).

Enseguida se verá un ejemplo para ilustrar la forma de elegir la acción de las válvulas de control; éste es el proceso que se muestra en la figura 5-1, en él la temperatura a la que sale el fluido bajo proceso se controla mediante el manejo del flujo de vapor al intercambiador de calor. La pregunta es: ¿cómo se desea que opere la válvula de vapor cuando falla el suministro de aire que le llega?

Como se explicó anteriormente, se desea que la válvula de vapor se mueva a la posición más segura; al parecer, ésta puede ser aquella con la que se detiene el flujo de vapor, es decir, no se desea flujo de vapor cuando se opera en condiciones inseguras, lo cual significa que se debe especificar una válvula cerrada en falla. Al tomar tal decisión, no se tomó en cuenta el efecto de no calentar el líquido en proceso al cerrar la válvula; en algunas ocasiones puede que no exista problema alguno, sin embargo, en otras se debe tomar en cuenta. Considérese, por ejemplo, el caso en que se mantiene la temperatura de un cierto polímero con el vapor; si se cierra la válvula de vapor, la temperatura desciende y el polímero se solidifica en el intercambiador; en este ejemplo, la decisión puede ser que con la válvula abierta en falla se logra la condición más segura.

Es importante notar que en el ejemplo sólo se tomó en cuenta la condición de seguridad en el intercambiador, que no es necesariamente la más segura en la operación completa; es decir, el ingeniero debe considerar la planta completa en lugar de una sola pieza del equipo; debe prever el efecto en el intercambiador de calor, así como en cualquier otro equipo del que provienen o al cual van el vapor y el fluido que se procesa. En resumen, el ingeniero debe tomar en cuenta la seguridad en la planta entera.

### Dimensionamiento de la válvula de control

El dimensionamiento de la válvula de control es el procedimiento mediante el cual se calcula el coeficiente de flujo de la válvula, $C_V$; el "método $C_V$" tiene bastante aceptación entre los fabricantes de válvulas; lo utilizó por primera vez la Masoneilan International, Inc., en 1944. Cuando ya se calculó el $C_V$ requerido y se conoce el tipo de válvula que se va a utilizar, el ingeniero puede obtener el tamaño de la válvula con base en el catálogo del fabricante.

El coeficiente $C_V$ se define como "la cantidad de agua en galones U.S. que fluye por minuto a través de una válvula completamente abierta, con una caída de presión de 1 psi en la sección transversal de la válvula." Por ejemplo, a través de una válvula con coeficiente máximo de 25 deben pasar 25 gpm de agua, cuando se abre completamente y la caída de presión es de 1 psi.

A pesar de que todos los fabricantes utilizan el método $C_V$ para dimensionamiento de válvulas, las ecuaciones para calcular $C_V$ presentan algunas diferencias de un fabricante a otro. La mejor manera de proceder es elegir el fabricante y utilizar las ecuaciones que recomienda; en esta sección se presentan las ecuaciones de dos fabricantes, Masoneilan y Fisher Controls, para mostrar las diferencias entre sus ecuaciones y métodos. Las mayores diferencias se presentan en las ecuaciones para dimensionar las válvulas utilizadas con fluidos que se comprimen (gas, vapor o vapor de agua). Los dos fabricantes mencionados no son, de ninguna manera, los únicos, en la tabla 5-1 se dan los nombres y direcciones de algunos otros.

```json
{
  "type": "table",
  "id": "table-05-01",
  "page": 182,
  "title": "Tabla 5-1. Fabricantes de válvulas de control",
  "headers": ["Fabricante", "Dirección"],
  "rows": [
    ["Jamesbury Corporation", "640 Lincoln Street, Worcester, MA 01605"],
    ["Jenkins Brothers", "101 Merritt Seven, Norwalk, CO 06851"],
    ["Jordan Valve", "407 Blade Street, Cincinnati, OH 45216"],
    ["Crane Company", "300 Park Avenue, New York, NY 10022"],
    ["DeZurik", "250 Riverside Avenue, North Sartell, MN 50377"],
    ["Fisher Controls Company", "P.O. Box 190, Marshalltown, IA 50158"],
    ["Masoneilan International", "63 Nahatan Street, Norwood, MA 02062"],
    ["Honeywell", "1100 Virginia Drive, Fort Washington, PA 18034"],
    ["Copes-Vulcan, Inc.", "Martin and Rice Avenues, Lake City, PA 14623"],
    ["Valtek", "P.O. Box 2200, Springville, UT 84663"],
    ["The Duriron Company, Inc.", "1978 Foreman Drive, Cookeville, TN 38501"],
    ["Cashco, Inc.", "P.O. Box A, Ellsworth, KS 67439"],
    ["The Foxboro Company", "Foxboro, MA 02035"]
  ],
  "notes": "Lista de fabricantes de válvulas de control",
  "source": "Smith & Corripio, Control Automático de Procesos, Tabla 5-1"
}
```

**Utilización con líquidos.** La ecuación básica para dimensionar una válvula de control que se utiliza con líquidos es la misma para todos los fabricantes:

$$q = C_V\sqrt{\frac{\Delta P}{G_f}} \quad (5-1)$$

o se despeja $C_V$:

$$C_V = q\sqrt{\frac{G_f}{\Delta P}} \quad (5-2)$$

donde:
- $q$ = tasa de flujo, gpm
- $G_f$ = gravedad específica del líquido
- $\Delta P$ = caída de presión a través de la válvula, psi

**Utilización con gases.** Para el dimensionamiento de válvulas que se utilizan con gases, Masoneilan propone las siguientes ecuaciones:

Flujo de gas por volumen:

$$C_V = \frac{Q}{2.8C_fP_1\sqrt{G_f}(y - 0.148y^3)} \quad (5-5)$$

Flujo de gas por peso:

$$C_V = \frac{W}{2.8C_fP_1\sqrt{G_f}(y - 0.148y^3)} \quad (5-6)$$

Vapor (de agua):

$$C_V = \frac{W(1 + 0.0007T_{SH})}{1.83C_fP_1(y - 0.148y^3)} \quad (5-7)$$

donde:
- $Q$ = tasa de flujo de gas en scfh; las condiciones estándar son de 14.7 psia y 60°F
- $G$ = gravedad específica del gas a 14.7 psia y 60°F (aire = 1.0); para los gases perfectos es la relación entre el peso molecular del gas y el peso molecular del aire (29)
- $G_f$ = gravedad específica del gas a la temperatura del flujo, $G_f = G(520/T)$
- $T$ = temperatura en °R
- $C_f$ = factor de flujo crítico, el valor numérico de este factor va de 0.6 a 0.95
- $P_1$ = presión de entrada a la válvula en psia
- $P_2$ = presión de salida de la válvula en psia
- $\Delta P = P_1 - P_2$
- $W$ = tasa de flujo, en lb/hr
- $T_{SH}$ = grados de sobrecalentamiento, en °F

El término $y$ se utiliza para expresar la condición crítica o subcrítica del flujo y se define como:

$$y = \frac{1.63}{C_f}\sqrt{\frac{\Delta P}{P_1}} \quad (5-8)$$

valor máximo de $y = 1.5$; con este valor $y - 0.148y^3 = 1.0$; por tanto, cuando $y$ alcanza un valor de 1.5, se tiene la condición de flujo crítico. A partir de esta ecuación se ve fácilmente que, cuando el término $y - 0.148y^3 = 1.0$, el flujo está en función únicamente de la presión de entrada, $P_1$.

Es importante tener en cuenta que, cuando el flujo es mucho menor que el crítico:

$$y - 0.148y^3 \approx y$$

se cancela el factor $C_f$ (no se necesita) y la ecuación (5-5) se deriva fácilmente de la ecuación (5-2). Lo interesante es que todas estas fórmulas de dimensionamiento se derivan de la definición original de $C_V$, ecuación (5-2), y la única particularidad de las fórmulas para gas es el factor de corrección $C_f$ y la función de compresibilidad $(y - 0.148y^3)$ que se requieren para describir el fenómeno de flujo crítico. De manera semejante, la ecuación (5-6) se deriva fácilmente de la ecuación (5-5).

Fisher Controls define dos nuevos coeficientes para el dimensionamiento de las válvulas que se utilizan con fluidos compresibles: el coeficiente $C_g$, que se relaciona con la capacidad de flujo de la válvula; y el coeficiente $C_1$, que se define como $C_g/C_V$, el cual proporciona una indicación de las capacidades de recuperación de la válvula. El último coeficiente, $C_1$, depende en mucho del tipo de válvula y sus valores generalmente están entre 33 y 38. La ecuación de Fisher para dimensionar válvulas para fluidos compresibles se conoce como Ecuación Universal para dimensionamiento de gases, y se expresa de dos formas:

$$C_g = \frac{Q_{scfh}}{\sqrt{\frac{520}{GT}P_1\sin\left[\left(\frac{59.64}{C_1}\right)\sqrt{\frac{\Delta P}{P_1}}\right]_{rad}}} \quad (5-9)$$

$$C_g = \frac{Q_{scfh}}{\sqrt{\frac{520}{GT}P_1\sin\left[\left(\frac{3417}{C_1}\right)\sqrt{\frac{\Delta P}{P_1}}\right]_{grad}}} \quad (5-10)$$

La condición de flujo crítico se indica mediante el término seno, cuyo argumento se debe limitar a $\pi/2$ en la ecuación (5-9) o 90° en la ecuación (5-10); con estos dos valores límite se indica el flujo crítico. En la figura C-39c y en la C-39d se muestran los valores para $C_g$ y $C_1$.

A partir de la ecuación (5-2) se pueden obtener las ecuaciones (5-9) y (5-10) para la condición de flujo subcrítico. La siguiente aproximación es verdadera sólo bastante abajo del flujo crítico:

$$\sin\left[\frac{59.64}{C_1}\sqrt{\frac{\Delta P}{P_1}}\right]_{rad} \approx \frac{59.64}{C_1}\sqrt{\frac{\Delta P}{P_1}}$$

El término seno se utiliza para describir el fenómeno de flujo crítico.

Es interesante notar la semejanza entre los dos fabricantes, ambos utilizan dos coeficientes para dimensionar válvulas de control para fluidos compresibles; uno de los coeficientes se relaciona con la capacidad de flujo de la válvula, $C_V$ para Masoneilan y $C_g$ para Fisher Controls; el otro coeficiente, $C_f$ para Masoneilan y $C_1$ para Fisher Controls, depende del tipo de válvula. Masoneilan utiliza el término $(y - 0.148y^3)$ para indicar el flujo crítico; mientras que Fisher utiliza el término seno; ambos términos son empíricos y el hecho de que sean diferentes no es significante.

Antes de concluir esta sección sobre dimensionamiento de válvulas de control es necesario mencionar algunos otros puntos importantes. El dimensionamiento de la válvula mediante el cálculo de $C_V$ se debe hacer de manera tal que, cuando la válvula se abra completamente, el flujo que pase sea más del que se requiere en condiciones normales de operación; es decir, debe haber algo de sobrediseño en la válvula para el caso en que se requiera más flujo. Los individuos o las compañías tienen diferentes formas de proceder acerca del sobrediseño en capacidad de la válvula; en cualquier caso, si se decide sobrediseñar la válvula en un factor de 2 veces el flujo que se requiere, el flujo de sobrediseño se expresa mediante:

$$q_{diseño} = 2.0 q_{requerido}$$

Si una válvula se abre alrededor del 3% cuando controla una variable bajo condiciones normales de operación, esa válvula en particular está sobrediseñada; y, de manera similar, si la válvula se abre cerca de un 97%, entonces está subdimensionada. En cualquiera de los dos casos, si la válvula se abre o se cierra casi completamente, es difícil obtener menos o más flujo en caso de que se requiera.

El **ajuste de rango** es un término que está en relación con la capacidad de la válvula. El ajuste de rango, $R$, de una válvula se define como la relación del flujo máximo que se puede controlar contra el flujo mínimo que se puede controlar:

$$R = \frac{q_{máximo\ que\ se\ puede\ controlar}}{q_{mínimo\ que\ se\ puede\ controlar}} \quad (5-11)$$

La definición de flujo máximo o mínimo que se puede controlar es muy subjetiva, algunas personas prefieren definir el flujo que se puede controlar entre el 10% y 90% de abertura de la válvula; mientras que otras lo definen entre el 5 y 95%; no existe regla fija o estándar para esta definición. En la mayoría de las válvulas de control el ajuste de rango es limitado y, generalmente, varía entre 20 y 50. Es deseable tener un ajuste de rango grande (del orden de 10 o mayor), de manera que la válvula tenga un efecto significativo sobre el flujo.

En los dos últimos párrafos se presentaron los temas de sobrediseño y ajuste de rango de las válvulas de control; ambas características tienen efectos definitivos sobre el desempeño de la válvula de control en servicio, lo cual se abordará cuando se presenten las "características de la válvula instalada".

### Selección de la caída de presión de diseño

Es importante reconocer que la válvula de control únicamente puede manejar las tasas de flujo mediante la producción o absorción de una caída de presión en el sistema, la cual es una pérdida en la economía de operación del sistema, ya que la presión la debe suministrar generalmente una bomba o un compresor y, en consecuencia, la economía impone el dimensionamiento de válvulas de control con poca caída de presión. Sin embargo, la poca caída de presión da como resultado mayores dimensiones de las válvulas de control y, por lo tanto, mayor costo inicial, así como un decremento en el rango de control. Estas consideraciones opuestas requieren un compromiso por parte del ingeniero, por lo que toca a la elección de la caída de presión en el diseño; existen varias reglas prácticas que se usan comúnmente como auxiliares en esta decisión. En general tales reglas especifican que la caída de presión que se lee en la sección transversal de la válvula debe ser de 20 a 50% de la caída dinámica de presión total en todo el sistema de conductos. Otra regla usual consiste en especificar la caída de presión de diseño en la válvula al 25% de la caída dinámica total de presión en todo el sistema de conductores, o a 10 psi, la que sea mayor; pero el valor real depende de la situación y del criterio establecido en la compañía. Como se supone, la caída de presión de diseño también tiene efecto sobre el desempeño de la válvula, tal como se verá en la siguiente sección.

**Ejemplo 5-1.** Se debe dimensionar una válvula de control que será utilizada con gas; el flujo nominal es de 25,000 lbm/hr; la presión de entrada de 250 psia; y la caída de presión de diseño de 100 psi. La gravedad específica del gas es de 0.4 con una temperatura de flujo de 150°F y peso molecular de 12. Se debe utilizar una válvula de acoplamiento.

Para utilizar la ecuación (5-6) de Masoneilan, se debe obtener el factor $C_f$. De la figura C-44 se tiene que, para la válvula de acoplamiento, $C_f = 0.92$; entonces, al usar la ecuación (5-8), se tiene:

$$y = \frac{1.63}{C_f}\sqrt{\frac{\Delta P}{P_1}} = \frac{1.63}{0.92}\sqrt{\frac{100}{250}} = 1.12$$

El flujo de diseño es:

$$W_{diseño} = 2W_{nominal} = 50,000 \frac{lbm}{hr}$$

Y:

$$C_V = \frac{W}{2.8C_fP_1\sqrt{G_f}(y - 0.148y^3)}$$
$$= \frac{50000}{2.8(0.92)(250)\sqrt{0.4(1.12 - 0.148(1.12)^3)}}$$
$$C_V = 134.6$$

Si se utiliza la ecuación de Fisher Controls para válvulas, se debe determinar el coeficiente $C_1$ y calcular el índice de flujo en scfh; de la figura C-39d se tiene que, para la válvula de acoplamiento $C_1 = 35$, el flujo volumétrico estándar es:

$$Q_{scfh} = \left(\frac{50000}{12}\right)(379.4) = 1580833$$

De la ecuación (5-10) se tiene entonces:

$$C_g = \frac{Q_{scfh}}{\sqrt{\frac{520}{GT}P_1\sin\left[\left(\frac{3417}{C_1}\right)\sqrt{\frac{\Delta P}{P_1}}\right]_{grad}}}$$
$$= \frac{1580833}{\sqrt{\frac{520}{0.4(610)}(250)\sin\left[\left(\frac{3417}{35}\right)\sqrt{\frac{100}{250}}\right]_{grad}}}$$
$$C_g = 4917.5$$

El coeficiente $C_g$ se puede convertir al equivalente $C_V$ para compararlo con el coeficiente $C_V$ de Masoneilan; con base en la definición de $C_1$, se obtiene:

$$C_1 = \frac{C_g}{C_V}$$

entonces:

$$C_V = \frac{C_g}{C_1} = \frac{4917.5}{35} = 140.5$$

Por lo tanto, es notorio que con ambos métodos se llega a resultados similares: para Masoneilan $C_V = 134.6$ y para Fisher Controls $C_V = 140.5$.

**Ejemplo 5-2.** Considérese el proceso que se muestra en la figura 5-2, en el cual se transfiere un fluido de un tanque de crudo a una torre de separación. El tanque está a la presión atmosférica; y la torre trabaja con un vacío de 4 pulg Hg; las condiciones de operación son las siguientes:

- Flujo: 900 gpm
- Temperatura: 90°F
- Gravedad específica: 0.94
- Presión de vapor: 13.85 psia
- Viscosidad: 0.29 cp

El tubo es de acero comercial y la eficiencia de la bomba es de 75%.

Se desea dimensionar la válvula que aparece con línea punteada, entre la bomba y la torre de separación.

Para dimensionar la válvula primero se debe determinar la caída de presión entre el punto 1, a la salida de la bomba, y el punto 2, a la entrada de la torre; dicha caída dinámica de presión se debe a las pérdidas por fricción en el sistema de tubería. Como se ve en el diagrama, el sistema de tubería consta de 250 pies de tubo de 6 pulgadas, dos codos de 90°, una válvula de bloqueo y una expansión repentina al entrar en la torre. La caída dinámica de presión en este sistema de tubería, $\Delta P_p$, se calcula mediante los principios de flujo de fluidos y se encuentra que es de 6 psi. Cuando ya se conoce la caída dinámica de presión, se puede elegir la caída de presión en la válvula, $\Delta P_v$.

Si, por ejemplo, la norma de una compañía es tener una caída de presión en la válvula igual al 25% de la caída dinámica de presión total, entonces:

$$\frac{\Delta P_v}{\Delta P_p + \Delta P_v} = 0.25 \quad \text{y} \quad \Delta P_v = 2 \text{ psi}$$

Al dimensionar la válvula para dos veces el flujo nominal, se tiene:

$$C_V = \frac{1800}{\sqrt{\frac{2}{0.94}}} = 1234$$

Si, por otro lado, por la norma de la compañía, se requiere una caída de presión de diseño del 25% de la caída dinámica de presión total o 10 psi, lo que sea mayor, entonces:

$$\Delta P_v = 10 \text{ psi}$$

Al dimensionar la válvula para dos veces el flujo nominal se tiene:

$$C_V = \frac{1800}{\sqrt{\frac{10}{0.94}}} = 552$$

### Características de flujo de la válvula de control

Para ayudar a lograr un buen control, el circuito de control debe tener una "personalidad constante", esto significa que en el proceso completo, el cual se define como la combinación de sensor/transmisor/unidad de proceso/válvula; la ganancia; las constantes de tiempo; y el tiempo muerto deben ser tan constantes como sea posible. Otra manera de referirse a que el proceso completo tiene una "personalidad constante" es decir que se trata de un sistema lineal.

Como ya se vio en los capítulos 3 y 4, la mayoría de los procesos son de naturaleza no lineal, lo que hace que el sensor/transmisor/unidad de proceso tampoco sea lineal. Puesto que el "proceso completo" incluye la válvula, mediante la elección de la correcta "personalidad de la válvula de control" se puede lograr que se reduzcan las características no lineales de la combinación sensor/transmisor/unidad de proceso; si esto se hace de manera correcta, se puede conseguir que la combinación sensor/transmisor/unidad de proceso/válvula tenga una ganancia constante. La personalidad de la válvula de control se conoce comúnmente como la "característica de flujo de la válvula de control" y, por tanto, se puede decir que el propósito de la caracterización del flujo es obtener en el proceso completo una ganancia relativamente constante para la mayoría de las condiciones de operación del proceso.

La característica de flujo de la válvula de control se define como la relación entre el flujo a través de la válvula y la posición de la misma conforme varía la posición de 0% a 100%. Se debe distinguir entre la "característica de flujo inherente" y la "característica de flujo en instalación". La primera se refiere a la característica que se observa cuando existe una caída de presión constante a través de la válvula. La segunda se refiere a la característica que se observa cuando la válvula está en servicio y hay variaciones en la caída de presión, así como otros cambios en el sistema. Primero se abordará la característica de flujo inherente.

En la figura 5-3 se muestran tres de las curvas más comunes de característica de flujo inherente. La forma de la curva se logra mediante el contorno de la superficie del émbolo cuando pasa cerca del asiento de la válvula. En la figura 5-4 se muestra el émbolo típico para la válvula lineal y la de porcentaje igual.

La característica de flujo **lineal** produce un flujo directamente proporcional al desplazamiento de la válvula, o posición de la válvula; con un 50% de desplazamiento, el flujo es el 50% del flujo máximo.

La característica de flujo de **porcentaje igual** produce un cambio muy pequeño en el flujo al inicio del desplazamiento de la válvula, pero conforme éste se abre hasta la posición de abertura máxima, el flujo aumenta considerablemente. El término "porcentaje igual" proviene del hecho de que, para incrementos iguales en el desplazamiento de la válvula, el cambio de flujo respecto al desplazamiento de la válvula es un porcentaje constante de la tasa de flujo en el momento del cambio.

La característica de flujo **rápido de abertura** produce un gran flujo con un pequeño desplazamiento de la válvula. Básicamente, la curva es lineal en la primera parte del desplazamiento, con una pendiente pronunciada. Es conveniente mencionar que la válvula de abertura rápida no es buena para la regulación, ya que no afecta el flujo en la mayor parte de su desplazamiento.

La "conciliación" de la característica correcta de la válvula para cualquier proceso requiere un análisis detallado de la dinámica en el proceso completo; sin embargo, para tomar la decisión se pueden usar como ayuda varias reglas prácticas que tienen su fundamento en la experiencia. Brevemente, se puede decir que las válvulas con característica de flujo lineal se usan comúnmente en circuitos de nivel de líquido, y en otros procesos en los que la caída de presión a través de la válvula es bastante constante. Las válvulas con característica de flujo de abertura rápida se usan principalmente en servicios de abierto-cerrado, en los que se requiere un gran flujo tan pronto como la válvula se comienza a abrir. Finalmente, las válvulas con característica de flujo de porcentaje igual son probablemente las más comunes; generalmente se usan en servicios donde se esperan grandes variaciones en la caída de presión; o en aquellos en los que, a través de la válvula, se toma un pequeño porcentaje de la caída total de presión en el sistema.

En la figura 5-3 se observan cosas importantes acerca del ajuste de rango de estos tres tipos de válvulas; nótese que con la válvula de tipo de abertura rápida se tiene la mayor parte del flujo al abrirla, casi un 40%, y a partir de ahí no hay mucho control sobre el flujo, lo cual da por resultado un bajo ajuste de rango (menos de 5 a 1). Al mismo tiempo en la figura 5-3 se ve que con las válvulas del tipo lineal y de porcentaje igual se tiene control del flujo sobre la mayor parte del rango de operación, de lo que resulta un ajuste de rango mayor de 20 a 1. Sin embargo, el lector debe recordar que estos comentarios se refieren únicamente a los "ajustes de rango inherentes", ya que se basan en las características inherentes.

Cuando una válvula está instalada en un sistema de tubería, la caída de presión a través de ella se modifica conforme varía el flujo; en este caso también varían las características de la válvula, las cuales, como se mencionó antes, se conocen como "características en instalación". Para entender mejor las características en instalación considérese el sistema de tubería que se muestra en la figura 5-5.

Sea:
- $\Delta P_o$ = caída dinámica de presión total (se incluye válvula, línea, conexiones, etc.) en el sistema de tubería, psi
- $\bar{q}$ = tasa de flujo de diseño, gpm
- $\Delta P_v$ = caída de presión a través de la válvula que depende del flujo, psi
- $f$ = fracción de caída dinámica de presión que toma la válvula de control
- $\bar{f}$ = fracción de caída dinámica de presión que toma la válvula con el flujo nominal
- $C_V|_{vp=1}$ = coeficiente de la válvula cuando está completamente abierta
- $\bar{F}$ = factor con que se sobredimensiona la válvula
- $\Delta P_p$ = caída de presión dinámica en el sistema de tubería (se excluye la válvula), psi

Por lo tanto, el flujo de diseño a través de la válvula se expresa por:

$$\bar{q} = \frac{C_V|_{vp=1}}{\bar{F}}\sqrt{\frac{\bar{f}\Delta P_o}{G_f}} \quad (5-12)$$

La caída de presión a través de la válvula la da:

$$\Delta P_v = \Delta P_o - \Delta P_p \quad (5-13)$$

Se supone que el balance de la caída dinámica de presión que toma el sistema de tubería es consecuente con la relación de la mecánica de fluidos:

$$\Delta P_p = (1 - f)\Delta P_o = K_LG_fq^2 \quad (5-14)$$

donde $K_L$ es una constante que tiene el siguiente valor:

$$K_L = \frac{(1 - \bar{f})\Delta P_o}{G_f\bar{q}^2} = \frac{(1 - \bar{f})\Delta P_o}{G_f}\cdot\frac{\bar{F}^2G_f}{(C_V|_{vp=1})^2\bar{f}\Delta P_o}$$
$$K_L = \frac{\bar{F}^2(1 - \bar{f})}{\bar{f}(C_V|_{vp=1})^2} \quad (5-15)$$

La caída dinámica de presión para cualquier flujo se expresa mediante:

$$\Delta P_o = \Delta P_v + K_LG_fq^2 \quad (5-16)$$

donde:

$$q = C_V\sqrt{\frac{\Delta P_v}{G_f}}$$

$C_V$ = coeficiente de la válvula en cualquier posición diferente a $vp = 1$

Entonces:

$$\Delta P_o = G_f\left(\frac{q}{C_V}\right)^2 + K_LG_fq^2 = G_f(1 + K_LC_V^2)\left(\frac{q}{C_V}\right)^2$$

de lo cual se obtiene:

$$q = \frac{C_V}{\sqrt{1 + K_LC_V^2}}\sqrt{\frac{\Delta P_o}{G_f}} \quad (5-17)$$

Cuando la válvula se abre completamente, la tasa de flujo es:

$$q_o = \frac{C_V|_{vp=1}}{\sqrt{1 + K_L(C_V|_{vp=1})^2}}\sqrt{\frac{\Delta P_o}{G_f}} \quad (5-18)$$

Después de dividir la ecuación (5-17) entre la (5-18) y substituir la ecuación (5-15) en el resultado, se tiene:

$$\frac{q}{q_o} = \frac{C_V}{C_V|_{vp=1}}\sqrt{\frac{1 + \frac{\bar{F}^2(1 - \bar{f})}{\bar{f}}}{1 + \frac{\bar{F}^2(1 - \bar{f})}{\bar{f}}\left[\frac{C_V}{C_V|_{vp=1}}\right]^2}} \quad (5-19)$$

Esta ecuación es valiosa porque da el flujo a través de la válvula cuando se instala en el sistema de tubería. Se debe recordar que para derivar la ecuación se mantuvo constante la caída total de presión, $\Delta P_o$, sin embargo, se permite que la caída de presión en la válvula, $\Delta P_v$, varíe. En la válvula lineal se puede relacionar el coeficiente $C_V$ con la posición de la válvula, como se verá en la ecuación (5-22), mediante la siguiente relación:

$$C_V = C_V|_{vp=1}(vp)$$

Entonces, al substituir esta relación en la ecuación (5-19), se tiene:

$$\frac{q}{q_o} = vp\sqrt{\frac{1 + \frac{\bar{F}^2(1 - \bar{f})}{\bar{f}}}{1 + \frac{\bar{F}^2(1 - \bar{f})}{\bar{f}}vp^2}} \quad (5-20)$$

Para la válvula de porcentaje igual, la relación entre $C_V$ y la posición de la válvula se expresa por:

$$C_V = (C_V|_{vp=1})\alpha^{vp-1}$$

Al substituir esta relación en la ecuación (5-19) se tiene:

$$\frac{q}{q_o} = \alpha^{vp-1}\sqrt{\frac{1 + \frac{\bar{F}^2(1 - \bar{f})}{\bar{f}}}{1 + \frac{\bar{F}^2(1 - \bar{f})}{\bar{f}}(\alpha^{vp-1})^2}} \quad (5-21)$$

Con las ecuaciones (5-20) y (5-21) se pueden determinar las características de instalación; se supone que se dimensionan las válvulas para tomar un 25% de la caída dinámica de presión total ($f = 0.25$) y que la válvula se sobredimensiona con un factor 2 ($F = 2$); en la figura 5-6 se muestran las características de instalación con las condiciones de diseño bajo esas condiciones.

En la figura se ve que, para el caso que se estudió ($\bar{f} = 0.25$, $F = 2$ y $\alpha = 50$), con la válvula de porcentaje igual se obtienen las características de instalación más lineales. Con la válvula lineal se tienen características de instalación de abertura rápida, con el consecuente ajuste de rango bajo.

Las características de instalación de cualquier válvula dependen de las características inherentes de la válvula, la fracción de caída dinámica de presión total a través de la válvula, $\bar{f}$, y el factor con el que se sobredimensiona la válvula, $\bar{F}$.

### Ganancia de la válvula de control

En la figura 5-3 se muestran las características de flujo inherentes de los tres tipos más comunes de válvulas. Se define como característica inherente al flujo característico que pasa a través de la válvula cuando se mantiene constante la caída de presión en la misma. Si se observa la ecuación (5-1), para el flujo del líquido a través de una válvula:

$$q = C_V\sqrt{\frac{\Delta P}{G_f}}$$

es notorio que, para que $q$ cambie con la posición de la válvula y la caída de presión y la gravedad específica se mantengan constantes, $C_V$ también debe cambiar con la posición de la válvula; por lo tanto, se dice que el coeficiente $C_V$ es una función de la posición de la válvula. La relación funcional entre $C_V$ y la posición de la válvula, $vp$, para la válvula lineal y la de porcentaje igual, es la siguiente:

**Válvula lineal:**

$$C_V = (C_V|_{vp=1})vp \quad (5-22)$$

**Válvula de porcentaje igual:**

$$C_V = (C_V|_{vp=1})\alpha^{vp-1} \quad (5-23)$$

donde $\alpha$ = parámetro de ajuste de la válvula.

A partir de estas relaciones se puede calcular el cambio en la tasa de flujo a través de la válvula, mientras se mantiene constante la caída de presión; es decir, ésta es la ganancia, la cual relaciona el flujo con la posición de la válvula. Considérese la ecuación de flujo para una válvula de porcentaje igual que se usa con líquidos:

$$q = (C_V|_{vp=1})\alpha^{vp-1}\sqrt{\frac{\Delta P}{G_f}}$$

La ganancia de la válvula es:

$$K_V = \frac{\partial q}{\partial vp}\bigg|_{\Delta P} = (C_V|_{vp=1})\ln(\alpha)\sqrt{\frac{\Delta P}{G_f}}\alpha^{vp-1} \quad (5-24)$$

La ecuación de flujo para una válvula lineal que se usa con líquidos es:

$$q = (C_V|_{vp=1})vp\sqrt{\frac{\Delta P}{G_f}}$$

y la ganancia de la válvula es:

$$K_V = \frac{\partial q}{\partial vp}\bigg|_{\Delta P} = (C_V|_{vp=1})\sqrt{\frac{\Delta P}{G_f}} \quad (5-25)$$

Como se ve en las ecuaciones (5-24) y (5-25), la ganancia inherente (con caída de presión constante) varía con la posición de la válvula, para el caso de la válvula de porcentaje igual; mientras que, para la válvula lineal es constante; esto también se puede notar fácilmente por observación de las características de flujo inherentes que se muestran en la figura 5-3; la ganancia es la pendiente de la curva de características del flujo. Para la válvula lineal la pendiente de la curva es constante; mientras que, para la de porcentaje igual varía.

Es importante tener en cuenta que la ganancia de instalación es diferente de la ganancia inherente; en realidad, como se ve en la figura 5-6, la ganancia de instalación de la válvula de porcentaje igual es más constante que la de la válvula lineal.

A partir de la ecuación (5-17) se puede obtener la expresión para la ganancia de instalación:

$$K_V = \frac{dq}{dvp}$$
$$= \sqrt{\frac{\Delta P_v}{G_f}}\left[\frac{\sqrt{1 + K_LC_V^2} - C_V(1 + K_LC_V^2)^{-1/2}K_LC_V}{(1 + K_LC_V^2)}\right]\frac{dC_V}{dvp}$$
$$= \frac{q}{C_V}\left(1 - \frac{K_LC_V^2}{1 + K_LC_V^2}\right)\frac{dC_V}{dvp}$$
$$= \frac{q}{C_V(1 + K_LC_V^2)}\frac{dC_V}{dvp} \quad (5-26)$$

El término $dC_V/dvp$ depende del tipo de válvula; la barra sobre el término indica que se conocen las condiciones de evaluación. Cuando $K_L = 0$, lo cual indica que la caída de presión a través de la válvula es constante, como en el caso de la ecuación (5-16), la ecuación (5-26) da por resultado la ecuación (5-24) o (5-25), según sea el tipo de válvula (la demostración queda por cuenta del lector).

Es importante tener en cuenta que, al dimensionar las válvulas de control, como se vio anteriormente, el $C_V$ que se calcula es el máximo o $C_V|_{vp=1}$.

### Resumen de la válvula de control

En esta sección se hizo la introducción a algunos de los aspectos más importantes acerca de las válvulas de control; sin embargo, existen muchos otros aspectos que se deben tomar en cuenta al especificar una válvula de control, los cuales no se presentaron por falta de tiempo y espacio; algunos de esos aspectos son el dimensionamiento de los actuadores de las válvulas, la estimación de nivel de ruido, el dimensionamiento de válvulas para flujo de dos fases y los casos en que la compresibilidad de un gas es importante, así como el efecto de los reductores de la tubería. Se espera que con la introducción presentada en esta sección y lo que se muestra en el apéndice C, el lector se sienta motivado a leer la selecta bibliografía que aparece en esta sección para entender cómo se deben tomar en cuenta tales aspectos.

## 5-3. CONTROLADORES POR RETROALIMENTACIÓN

En esta sección se presentan los tipos más importantes de controladores industriales y se hace especial énfasis en el significado físico de sus parámetros, como apoyo para la comprensión de su funcionamiento. Lo que se presenta aquí es válido tanto para los controladores neumáticos, electrónicos como para la mayoría de los que se basan en microprocesadores.

En síntesis, el controlador es el "cerebro" del circuito de control. Como se mencionó en el capítulo 1, el controlador es el dispositivo que toma la decisión (D) en el sistema de control y, para hacerlo, el controlador:

1. Compara la señal del proceso que llega del transmisor, la variable que se controla, contra el punto de control y
2. Envía la señal apropiada a la válvula de control, o cualquier otro elemento final de control, para mantener la variable que se controla en el punto de control.

En la figura 5-7 se muestran diferentes tipos de controladores, nótese las diferentes perillas, selectores y botones con los que se hace el ajuste del punto de control, la lectura de la variable que se controla, el cambio entre el modo manual y automático y el ajuste y lectura de la señal de salida del controlador; en la mayoría de los controladores estos selectores se encuentran en el panel frontal, para facilitar la operación.

Un selector interesante es el auto/manual, con este se determina el modo de operación del controlador. Cuando el selector está en la posición auto (automático), el controlador decide y emite la señal apropiada hacia el elemento final de control, para mantener la variable que se controla en el punto de control; cuando el selector está en la posición manual, el controlador cesa de decidir y "congela" su salida, entonces el operador o ingeniero puede cambiar manualmente la salida del controlador mediante el disco, rueda o botón de salida manual; en esta modalidad el controlador sólo proporciona un medio conveniente (y caro) para ajustar el elemento final de control. En la modalidad de automático la salida manual no tiene ningún efecto, únicamente el punto de control tiene influencia sobre la salida. En la modalidad manual el punto de control no tiene ninguna influencia sobre la salida del controlador, solamente la salida manual tiene influencia sobre la salida. Si un controlador se pone en manual, no hay mucha necesidad de tenerlo; solamente cuando el controlador está en automático es cuando se obtienen los beneficios del control automático de proceso.

### Funcionamiento de los controladores

Considérese el circuito de control del intercambiador de calor que se muestra en la figura 5-8; si la temperatura del fluido sobrepasa el punto de control, el controlador debe cerrar la válvula de vapor. Puesto que la válvula es de aire para abrir (AA), se debe reducir la señal de salida del controlador (presión de aire o corriente) (ver las flechas en la figura). Para tomar esta decisión el controlador debe estar en **acción inversa**. Algunos fabricantes designan tal acción como decremento; es decir, cuando hay un incremento en la señal que entra al controlador, entonces se presenta un decremento en la señal que sale del mismo.

Considérese ahora el circuito de control de nivel que se muestra en la figura 5-9; si el nivel del líquido rebasa el punto de fijación, el controlador debe abrir la válvula para que el nivel regrese al punto de control. Puesto que la válvula es de aire para abrir (AA), el controlador debe incrementar su señal de salida (ver las flechas en la figura) y, para tomar esta decisión, el controlador se debe colocar en **acción directa**. Algunos fabricantes denominan a esta acción incremento; es decir, cuando hay un incremento en la señal que entra al controlador entonces existe un incremento en la señal de salida del mismo.

En resumen, para determinar la acción del controlador, el ingeniero debe conocer:

1. Los requerimientos de control del proceso y
2. La acción de la válvula de control u otro elemento final de control.

Ambas cosas se deben tomar en cuenta. Tal vez el lector se pregunte cuál es la acción correcta del controlador de nivel si se utiliza una válvula de aire para cerrar (AC), o si el nivel se controla con el flujo de entrada en lugar del flujo de salida. En el primer caso cambia la acción de la válvula de control; mientras que, en el segundo, cambian los requerimientos de control del proceso.

La acción del controlador se determina generalmente mediante un interruptor en el panel lateral de los controladores neumáticos o electrónicos, como se muestra en la figura 5-7b, mediante un bit de configuración en la mayoría de los controladores que tienen como base un microprocesador.

### Tipos de controladores por retroalimentación

La manera en que los controladores por retroalimentación toman una decisión para mantener el punto de control, es mediante el cálculo de la salida con base en la diferencia entre la variable que se controla y el punto de control. En esta sección se abordarán los tipos más comunes de controladores, por medio del estudio de las ecuaciones con que se describe su operación.

**Controlador proporcional (P).** El controlador proporcional es el tipo más simple de controlador, con excepción del controlador de dos estados, el cual no se estudia aquí; la ecuación con que se describe su funcionamiento es la siguiente:

$$m(t) = \bar{m} + K_c(r(t) - c(t)) \quad (5-27)$$

o:

$$m(t) = \bar{m} + K_ce(t) \quad (5-28)$$

donde:
- $m(t)$ = salida del controlador, psig o mA
- $r(t)$ = punto de control, psig o mA
- $c(t)$ = variable que se controla, psig o mA; ésta es la señal que llega del transmisor
- $e(t)$ = señal de error, psi o mA; ésta es la diferencia entre el punto de control y la variable que se controla
- $K_c$ = ganancia del controlador, $\frac{mA}{mA}$ o $\frac{psi}{psi}$
- $\bar{m}$ = valor base, psig o mA. El significado de este valor es la salida del controlador cuando el error es cero; generalmente se fija durante la calibración del controlador, en el medio de la escala, 9 psig o 12 mA.

Puesto que los rangos de entrada y salida son los mismos (3-15 psig o 4-20 mA), algunas veces las señales de entrada y salida, así como el punto de control se expresan en porcentaje o fracción de rango.

Es interesante notar que la ecuación (5-27) es para un controlador de acción inversa; si la variable que se controla, $c(t)$, se incrementa en un valor superior al punto de control, $r(t)$, el error se vuelve negativo y, como se ve en la ecuación, la salida del controlador, $m(t)$, decrece. La manera común con que se designa matemáticamente un controlador de acción directa es haciendo negativa la ganancia del controlador, $K_c$; sin embargo, se debe recordar que en los controladores industriales no hay ganancias negativas, sino únicamente positivas, lo cual se resuelve con el selector inverso/directo. La negativa se utiliza cuando se hace el análisis matemático de un sistema de control en el que se requiere un controlador de acción directa.

En las ecuaciones (5-27) y (5-28) se ve que la salida del controlador es proporcional al error entre el punto de control y la variable que se controla; la proporcionalidad la da la ganancia del controlador, $K_c$; con esta ganancia o sensibilidad del controlador se determina cuánto se modifica la salida del controlador con un cierto cambio de error. Esto se ilustra gráficamente en la figura 5-10.

Los controladores que son únicamente proporcionales tienen la ventaja de que sólo cuentan con un parámetro de ajuste, $K_c$; sin embargo, adolecen de una gran desventaja, operan con una DESVIACIÓN, o "error de estado estacionario" en la variable que se controla. A fin de apreciar dicha desviación gráficamente, considérese el circuito de control de nivel que se muestra en la figura 5-9; supóngase que las condiciones de operación de diseño son $q_i = q_o = 150$ gpm y $h = 6$ pies; supóngase también que, para que pasen 150 gpm por la válvula de salida la presión de aire sobre ésta debe ser de 9 psig. Si el flujo de entrada se incrementa, $q_i$, la respuesta del sistema con un controlador proporcional es como se ve en la figura 5-11. El controlador lleva de nuevo a la variable a un valor estacionario pero este valor no es el punto de control requerido; la diferencia entre el punto de control y el valor de estado estacionario de la variable que se controla es la desviación. En la figura 5-11 se muestran dos curvas de respuesta que corresponden a dos diferentes valores del parámetro de ajuste $K_c$. En la figura se aprecia que cuanto mayor es el valor de $K_c$, tanto menor es la desviación, pero la respuesta del proceso se hace más oscilatoria; sin embargo, para la mayoría de los procesos existe un valor máximo de $K_c$ más allá del cual el proceso se hace inestable. En los capítulos 6 y 7 se presenta la forma de calcular el valor máximo de la ganancia, el cual se conoce como la **ganancia última**, $K_{c_u}$.

A continuación se explica de manera simple por qué existe la desviación, a reserva de una prueba más rigurosa que se expone en el capítulo 6; considérese el mismo sistema de control de nivel de líquido que aparece en la figura 5-9, con las condiciones de operación que se dieron anteriormente. Se debe recordar que el controlador proporcional, con acción directa ($K_c > 0$), resuelve la siguiente ecuación:

$$m(t) = 9 + (K_c)e(t) \quad (5-29)$$

Supóngase ahora que el flujo de entrada se incrementa a 170 gpm; cuando esto sucede, el nivel del líquido aumenta y el controlador debe, a su vez, incrementar su salida para abrir la válvula y bajar el nivel. Para alcanzar una operación estacionaria el flujo de salida, $q_o$, debe ser ahora de 170 gpm y, para que pase este nuevo flujo, se debe abrir la válvula de salida más que cuando pasaban 150 gpm; puesto que la válvula es de aire para abrir, supóngase que la nueva presión sobre la válvula debe ser de 10 psig; es decir, la salida del controlador, $m(t)$, debe ser de 10 psig. En la ecuación (5-29) se observa que la única manera de que la salida del controlador sea de 10 psig, es que el segundo término del miembro de la derecha tenga un valor de +1 psig y, para que esto se cumpla, el término de error, $e(t)$, no puede ser cero en el estado estacionario; este error de estado estacionario es la desviación. Nótese que el error negativo significa que la variable que se controla es mayor que el punto de control. El nivel real, en pies, se puede calcular a partir de la calibración del transmisor de nivel.

En este ejemplo se debe hacer énfasis en dos puntos: Primero, la magnitud del término de desviación depende del valor de la ganancia del controlador, puesto que el término total debe tener un valor de +1, entonces:

- $K_c = 1$: $e(\infty) = 1$
- $K_c = 2$: $e(\infty) = 0.5$
- $K_c = 4$: $e(\infty) = 0.25$

Como se mencionó anteriormente, cuanto mayor es la ganancia, tanto menor es la desviación; el lector debe recordar que arriba de cierta $K_c$ la mayoría de los procesos se vuelven inestables, sin embargo, esto no lo muestra la ecuación del controlador y lo cual se prueba en el capítulo 6.

Segundo, y como resumen de este ejemplo, tal parece que todo lo que los controladores proporcionales logran es alcanzar una condición de operación de estado estacionario; la cantidad de alejamiento del punto de operación, o desviación, depende de la ganancia del controlador.

Muchos fabricantes de controladores no utilizan el término ganancia para designar la cantidad de sensibilidad del controlador, sino que utilizan el término **Banda Proporcional, PB**. La relación entre la ganancia y la banda proporcional se expresa mediante:

$$PB = \frac{100\%}{K_c} \quad (5-30)$$

y, en consecuencia, la ecuación con que se describe al controlador proporcional, se escribe ahora de la siguiente forma:

$$m(t) = \bar{m} + \frac{100\%}{PB}(r(t) - c(t)) \quad (5-31)$$

Se utiliza el término "100" porque la PB se conoce generalmente como "porcentaje de banda proporcional".

En la ecuación (5-30) se aprecia un hecho bastante importante: una ganancia, $K_c$, grande es lo mismo que una banda proporcional baja o estrecha; y una ganancia baja es lo mismo que una banda proporcional grande o ancha. Esto quiere decir que, antes de empezar a ajustar la perilla del controlador, se debe saber si en el controlador se utiliza ganancia o banda proporcional.

A continuación se ofrece otra definición de banda proporcional: la banda proporcional se refiere al error (expresado en porcentaje de rango de la variable que se controla) que se requiere para llevar la salida del controlador del valor más bajo hasta el más alto. Considérese el circuito de control del intercambiador de calor que se muestra en la figura 5-8; la escala del transmisor de temperatura va de 100°C a 300°C y el punto de control del controlador está en 200°C. En la figura 5-12 se explica gráficamente la definición de PB; en ella se ve que una PB del 100% significa que, cuando la variable que se controla varía en rango un 100%, la salida del controlador varía 100% en rango; una PB de 50% significa que, cuando la variable que se controla varía un 50% en rango, la salida del controlador varía en rango 100%. También se debe notar que, en un controlador proporcional con PB del 200%, la salida del controlador no se mueve sobre el rango completo; una PB del 200% significa muy poca ganancia o sensibilidad a los errores.

Para obtener la función de transferencia del controlador proporcional, la ecuación (5-27) se puede escribir como:

$$m(t) - \bar{m} = K_c(r(t) - c(t))$$

Se definen las dos siguientes variables de desviación:

$$M(t) = m(t) - \bar{m} \quad (5-33)$$
$$E(t) = r(t) - c(t) \quad (5-34)$$

Entonces:

$$M(t) = K_cE(t)$$

Se obtiene la transformada de Laplace, y de ahí resulta la siguiente función de transferencia:

$$\frac{M(s)}{E(s)} = K_c \quad (5-35)$$

Para resumir brevemente, los controladores proporcionales son los más simples, con la ventaja de que sólo tienen un parámetro de ajuste, $K_c$ o PB; la desventaja de los mismos es que operan con una desviación en la variable que se controla, en algunos procesos, por ejemplo, un tanque de mezclado, esto puede no tener mayor consecuencia. En los casos en que el proceso se controla dentro de una banda del punto de control, los controladores proporcionales son suficientes; sin embargo, en los procesos en que el control debe estar en el punto de control, los controladores proporcionales no proporcionan un control satisfactorio.

**Controlador proporcional-integral (PI).** La mayoría de los procesos no se pueden controlar con una desviación, es decir, se deben controlar en el punto de control, y en estos casos se debe añadir inteligencia al controlador proporcional, para eliminar la desviación. Esta nueva inteligencia o nuevo modo de control es la acción integral o de reajuste y, en consecuencia, el controlador se convierte en un controlador proporcional-integral (PI). La siguiente es su ecuación descriptiva:

$$m(t) = \bar{m} + K_c[r(t) - c(t)] + \frac{K_c}{\tau_I}\int_0^t [r(t) - c(t)]dt \quad (5-36)$$

o:

$$m(t) = \bar{m} + K_ce(t) + \frac{K_c}{\tau_I}\int_0^t e(t)dt \quad (5-37)$$

donde $\tau_I$ = tiempo de integración o reajuste, minutos/repetición. Por lo tanto, el controlador PI tiene dos parámetros, $K_c$ y $\tau_I$, que se deben ajustar para obtener un control satisfactorio.

Para entender el significado físico del tiempo de reajuste, $\tau_I$, considérese el ejemplo hipotético que se muestra en la figura 5-13, donde $\tau_I$ es el tiempo que toma al controlador repetir la acción proporcional y, en consecuencia, las unidades son minutos/repetición. Tanto menor es el valor de $\tau_I$, cuanto más pronunciada es la curva de respuesta, lo cual significa que la respuesta del controlador se hace más rápida. Otra manera de explicar esto es mediante la observación de la ecuación (5-37), tanto menor es el valor de $\tau_I$, cuanto mayor es el término delante de la integral, $K_c/\tau_I$, y, en consecuencia, se le da mayor peso a la acción integral o de reajuste.

De la ecuación (5-37) también se nota que, mientras esté presente el término de error, el controlador se mantiene cambiando su respuesta y, por lo tanto, integrando el error, para eliminarlo; recuérdese que integración también quiere decir sumatoria.

Ahora se recurre nuevamente al sistema de control de nivel de líquido que se utilizó para explicar por qué ocurre la desviación. Como se dijo, cuando el flujo de entrada se incrementa a 170 gpm, el flujo de salida se debe incrementar a 170 gpm para alcanzar una condición final de operación de estado estacionario; para que pasen 170 gpm por la válvula de salida se necesita una señal de aire de 10 psig, y la única manera de que la salida de un controlador proporcional sea de 10 psig se logra mediante la conservación del término de error. En un controlador PI, mientras el error está presente, el controlador se mantiene integrándolo y, por lo tanto, añadiéndolo a su salida hasta que el error desaparece; cuando éste es el caso, la salida del controlador se expresa mediante:

$$m(t) = \bar{m} + \frac{K_c}{\tau_I}\int_0^t e(t)dt$$

El hecho de que el error sea cero no significa que el término con la integral sea cero, esto significa que el controlador integra una función de valor cero; o, mejor aún, "añade cero" a su salida, con lo cual ésta se mantiene constante. Para el proceso de nivel de líquido el término con la integral tiene un valor de 1 psig y, por lo tanto, la salida del controlador es de 10 psig, sin ningún error. Lo anterior es una explicación breve de por qué con la acción de reajuste se elimina la desviación; en el capítulo 6 esto se prueba nuevamente desde un punto de vista más riguroso.

Algunos fabricantes no utilizan el término de tiempo de reajuste $\tau_I$ para su parámetro de ajuste, sino que utilizan lo que se conoce como **rapidez de reajuste** $\tau_I^{-1}$; la relación entre estos dos parámetros es:

$$\tau_I^{-1} = \frac{1}{\tau_I}, \text{ repeticiones/min}$$

Por lo tanto, antes de ajustar el parámetro de integración se debe saber si en el controlador se utiliza tiempo de reajuste o rapidez de reajuste, que son recíprocos y, en consecuencia, sus efectos son opuestos.

A continuación se muestran las ecuaciones con que algunos fabricantes describen la operación de sus controladores PI, lo cual refuerza el comentario de que "se debe saber con quién se juega, antes de empezar a jugar".

Foxboro Co.:
$$m(t) = \bar{m} + \frac{100}{PB}e(t) + \frac{100}{PB\cdot\tau_I}\int_0^t e(t)dt \quad (5-39)$$

Fisher Controls:
$$m(t) = \bar{m} + \frac{100}{PB}e(t) + \frac{100\tau_I}{PB}\int_0^t e(t)dt \quad (5-40)$$

Taylor Co., Honeywell, Inc.

Es interesante apuntar que, cuando Honeywell desarrolló su controlador con base en microprocesadores, el TDC20, transformó el controlador PI en el que se describe con la ecuación (5-37). Por otro lado, cuando Fisher Controls desarrolló su sistema de control con base en microprocesadores, el PROVOX, cambió su ecuación para PI, ecuación (5-40), por la ecuación (5-41). La Instrument Society of America (ISA) propone como norma la ecuación (5-37), la cual se utilizará en este libro; lo importante es recordar las relaciones entre ganancia y banda proporcional, y tiempo de reajuste y rapidez de reajuste.

Para obtener la función de transferencia del controlador PI, la ecuación (5-37) se escribe como sigue:

$$m(t) - \bar{m} = K_c\left(e(t) + \frac{1}{\tau_I}\int_0^t e(t)dt\right)$$

Se utilizan las mismas definiciones de variables de desviación que se dan en las ecuaciones (5-33) y (5-34), se obtiene la transformada de Laplace y se reordena para obtener:

$$\frac{M(s)}{E(s)} = K_c\left(1 + \frac{1}{\tau_Is}\right) \quad (5-42)$$

En resumen, los controladores proporcionales-integrales tienen dos parámetros de ajuste: la ganancia o banda proporcional y el tiempo de reajuste o rapidez de reajuste; la ventaja de este controlador es que la acción de integración o de reajuste elimina la desviación. En los capítulos 6 y 7 se prueba nuevamente que con este tipo de controlador se elimina la desviación y la manera en que ello afecta la estabilidad de los circuitos de control. Probablemente el 75% de los controladores en servicio son de este tipo.

**Controlador proporcional-integral-derivativo (PID).** Algunas veces se añade otro modo de control al controlador PI, este nuevo modo de control es la acción derivativa, que también se conoce como rapidez de derivación o preactuación; tiene como propósito anticipar hacia dónde va el proceso, mediante la observación de la rapidez para el cambio del error, su derivada. La ecuación descriptiva es la siguiente:

$$m(t) = \bar{m} + K_ce(t) + \frac{K_c}{\tau_I}\int_0^t e(t)dt + K_c\tau_D\frac{de(t)}{dt} \quad (5-43)$$

donde:
- $\tau_D$ = rapidez de derivación en minutos.

Por lo tanto, el controlador PID tiene tres parámetros, $K_c$ o PB, $\tau_I$ o $\tau_I^{-1}$, y $\tau_D$, que se deben ajustar para obtener un control satisfactorio. Nótese que sólo existe un parámetro para ajuste de derivación, $\tau_D$, el cual tiene las mismas unidades, minutos, para todos los fabricantes.

Como se acaba de mencionar, con la acción derivativa se da al controlador la capacidad de anticipar hacia dónde se dirige el proceso, es decir, "ver hacia adelante", mediante el cálculo de la derivada del error. La cantidad de "anticipación" se decide mediante el valor del parámetro de ajuste, $\tau_D$.

A continuación se utiliza el intercambiador de calor que se muestra en la figura 5-8 para aclarar el significado de "anticipar hacia dónde se dirige el proceso". Si se supone que la temperatura de entrada al proceso disminuye cierta cantidad y la temperatura de salida empieza a bajar de manera correspondiente, como se muestra en la figura 5-14, en el tiempo $t_a$ la cantidad de error es positiva y puede ser pequeña; en consecuencia, la cantidad de corrección de control que suministra el modo proporcional e integral es pequeña, sin embargo, la derivada de dicho error, la pendiente de la curva de error, es grande y positiva, lo que hace que la corrección proporcionada por el modo derivativo sea grande. Mediante la observación de la derivada del error, el controlador sabe que la variable que se controla se aleja con rapidez del punto de control y, en consecuencia, utiliza este hecho para ayudar en el control. En el tiempo $t_b$ el error aún es positivo y mayor que antes; la cantidad de corrección de control que suministran los modos proporcional e integral también es más grande que antes y se añade aún a la salida del controlador para abrir más la válvula de vapor; sin embargo, en ese momento la derivada del error es negativa, lo cual significa que el error empieza a decrecer; es decir, la variable que se controla empieza a bajar al punto de control y, nuevamente, con la utilización de este hecho, en el modo derivativo se comienza a substraer de los otros dos modos, ya que se reconoce que el error disminuye. Al hacer esto, se toma más tiempo para que el proceso regrese al punto de control, pero disminuyen el sobrepaso y las oscilaciones alrededor del punto de control.

Los controladores PID se utilizan en procesos donde las constantes de tiempo son largas. Ejemplos típicos de ello son los circuitos de temperatura y los de concentración. Los procesos en que las constantes de tiempo son cortas (capacitancia pequeña) son rápidos y susceptibles al ruido del proceso, son característicos de este tipo de proceso los circuitos de control de flujo y los circuitos para controlar la presión en corrientes de líquidos. Considérese el registro de flujo que se ilustra en la figura 5-15, la aplicación del modo derivativo sólo da como resultado la amplificación del ruido, porque la derivada del ruido, que cambia rápidamente, es un valor grande. Los procesos donde la constante de tiempo es larga (capacitancia grande) son generalmente amortiguados y, en consecuencia, menos susceptibles al ruido; sin embargo, se debe estar alerta, ya que se puede tener un proceso con constante de tiempo larga, por ejemplo, un circuito de temperatura, en el que el transmisor sea ruidoso, en cuyo caso se debe reparar el transmisor antes de utilizar el controlador PID.

La función de transferencia de un controlador PID "ideal" se obtiene a partir de la ecuación (5-43), la cual se reordena como sigue:

$$m(t) - \bar{m} = K_c\left(e(t) + \frac{1}{\tau_I}\int_0^t e(t)dt + \tau_D\frac{de(t)}{dt}\right)$$

Se usan las mismas definiciones de variables de desviación que aparecen en las ecuaciones (5-33) y (5-34), se obtiene la transformada de Laplace y se reordena para obtener:

$$\frac{M(s)}{E(s)} = K_c\left(1 + \frac{1}{\tau_Is} + \tau_Ds\right) \quad (5-44)$$

Esta función de transferencia se conoce como "ideal" porque en la práctica es imposible implantar el cálculo de la derivada, por lo cual se hace una aproximación mediante la utilización de un adelanto/retardo, de lo que resulta la función de transferencia "real":

$$\frac{M(s)}{E(s)} = K_c\left(1 + \frac{1}{\tau_Is}\right)\left(\frac{\tau_Ds + 1}{\alpha\tau_Ds + 1}\right) \quad (5-45)$$

Los valores típicos de $\alpha$ están entre 0.05 y 0.1.

En resumen, los controladores PID tienen tres parámetros de ajuste: la ganancia o banda proporcional, el tiempo de reajuste o rapidez de reajuste y la rapidez derivativa. La rapidez derivativa se da siempre en minutos. Los controladores PID se recomiendan para circuitos con constante de tiempo larga en los que no hay ruido. La ventaja del modo derivativo es que proporciona la capacidad de "ver hacia dónde se dirige el proceso". En los capítulos 6 y 7 se estudia la manera en que el uso de este controlador mejora el control y cómo afecta la estabilidad de los circuitos de control.

**Controlador proporcional-derivativo (PD).** Este controlador se utiliza en los procesos donde es posible utilizar un controlador proporcional, pero se desea cierta cantidad de "anticipación". La ecuación descriptiva es:

$$m(t) = \bar{m} + K_ce(t) + K_c\tau_D\frac{de(t)}{dt} \quad (5-46)$$

y la función de transferencia "ideal" es:

$$\frac{M(s)}{E(s)} = K_c(1 + \tau_Ds) \quad (5-47)$$

Una desventaja del controlador PD es que opera con una desviación en la variable que se controla; la desviación solamente se puede eliminar con la acción de integración, sin embargo, un controlador PD puede soportar mayor ganancia, de lo que resulta una menor desviación que cuando se utiliza un controlador únicamente proporcional en el mismo circuito.

**Controladores digitales y otros comentarios.** Como se mencionó anteriormente, la ecuación (5-45) es la función de transferencia para los controladores industriales analógicos, sin embargo, la ecuación de los controladores digitales es la forma discreta de la ecuación (5-43). Los métodos para ajustar los controladores digitales no son muy diferentes de los que se utilizan para ajustar los controladores analógicos, lo cual se explica en el siguiente capítulo. Se remite al lector a la referencia bibliográfica 4 para un estudio más profundo acerca de los controladores digitales.

Antes de concluir esta sección son pertinentes algunos otros comentarios. En la ecuación (5-43) se ve que, en cualquier momento en que cambia el parámetro $K_c$, esto afecta las acciones de integración y derivación, ya que $\tau_I$ y $\tau_D$ se dividen o multiplican por dicho parámetro; esto significa que, si únicamente se desea cambiar la acción proporcional pero no la cantidad de reajuste o anticipación, entonces también se deben cambiar los parámetros $\tau_I$ y $\tau_D$ para adaptarlos al cambio $K_c$. Todos los controladores analógicos son de este tipo, y algunas veces se les conoce como "controladores interactivos"; la mayoría de los controladores con base en microprocesadores también son del mismo tipo; sin embargo, existen algunos en los que se evita este problema mediante la substitución del término $K_c/\tau_I$ por el término único $K_I$ y el término $K_c\tau_D$ por $K_D$, lo cual quiere decir que los tres parámetros de ajuste son $K_c$, $K_I$ y $K_D$.

El comentario final se relaciona con la acción derivativa. La forma típica para cambiar el punto de control del controlador es la introducción de un cambio, se muestra en la figura 5-16; cuando esto ocurre, también se introduce un cambio del error en escalón, como se ilustra en la figura 5-16b; y, puesto que el controlador toma la derivada del error, ésta produce un cambio súbito en la salida del controlador, como se ve en la figura 5-16c; el cambio en la salida del controlador es innecesario y, posiblemente, va en detrimento de la operación del proceso. Para sortear este problema se ha propuesto la utilización de la derivada de la variable que se controla, pero con signo contrario, en lugar de la derivada del error; las dos derivadas son iguales cuando el punto de control permanece constante, como se puede ver mediante lo siguiente:

$$\frac{de(t)}{dt} = \frac{dr(t)}{dt} - \frac{dc(t)}{dt} = 0 - \frac{dc(t)}{dt} = -\frac{dc(t)}{dt}$$

En el momento en que se introduce el cambio en el punto de control la "nueva" derivada no ocasiona un cambio súbito, inmediatamente después el comportamiento vuelve a ser el mismo de antes. Esta opción se ofrece en algunos controladores analógicos y en los que tienen como base microprocesadores, y se conoce como **derivada sobre la variable que se controla**.

Otra posibilidad para evitar el problema de derivación se consigue fácilmente mediante la utilización de controladores digitales; en esta opción se cambia el punto de control en forma de rampa; aun cuando el operador lo cambia en escalón, como se observa en la figura 5-16, la pendiente de la rampa la predetermina el personal de operación.

### Reajuste excesivo

Un problema real e importante en el control de proceso es el **reajuste excesivo** y puede ocurrir en cualquier momento cuando el controlador tiene el modo integral de control. Para explicar este problema se utiliza el circuito de control del intercambiador de calor que se muestra en la figura 5-8.

Supóngase que la temperatura de entrada al proceso desciende en una cantidad significativa; este disturbio provoca que baje la temperatura de salida del proceso y, a su vez, el controlador (PI o PID) hace que la válvula de vapor se abra; puesto que la válvula es de aire para abrir, la señal neumática del controlador se incrementa hasta que, a causa de la acción de reajuste, la temperatura de salida se iguala con el punto de control que se desea. Supóngase que en el esfuerzo por reestablecer la ubicación de la variable que se controla en el punto de control, se integra hasta 15 psig en el controlador, punto en el cual la válvula de vapor está completamente abierta y, por lo tanto, el circuito de control ya no puede hacer más; esencialmente el proceso está fuera de control, lo cual se ilustra en la figura 5-17. En la figura se muestra que, cuando la válvula está completamente abierta, la variable que se controla (temperatura de salida) aún no llega al punto de control y, puesto que todavía existe el error, el controlador trata de corregirlo mediante un mayor incremento (integración del error) en su presión de salida, aun cuando la válvula no se puede abrir más allá de 15 psig. En efecto, la salida del controlador se puede integrar hasta la presión de suministro, la cual es generalmente de casi 20 psig; en este punto ya no se puede incrementar la salida del controlador, debido a que la salida está saturada, tal estado del sistema también se muestra en la figura 5-17. La saturación se debe a la acción de integración (reajuste) del controlador; mientras el error esté presente, el controlador continuará cambiando su salida. Dicho estado de saturación se conoce como "reajuste excesivo".

Si ahora se supone que la temperatura de entrada sube nuevamente, la temperatura de salida del proceso, a su vez, empezará a incrementarse, como se muestra también en la figura 5-18, donde se aprecia que la temperatura de salida alcanza y pasa el punto de control y la válvula permanece completamente abierta, aunque, de hecho, debería estar cerrándose, la razón de que no se cierre es porque el controlador debe integrar hacia abajo, desde 20 a 15 psig, antes de que empiece a cerrar la válvula, pero en el momento en que eso sucede, la temperatura de salida ha sobrepasado el punto de control en una cantidad considerable.

Como se mencionó anteriormente, este problema de reajuste excesivo puede ocurrir en cualquier momento en que esté presente la integración en el controlador, y se puede evitar si el controlador se pone en manual tan pronto como su salida alcanza 15 psig, ya que así se detiene la integración; el controlador puede volver a ponerse en automático cuando la temperatura empieza a descender. La desventaja de esta operación es que requiere la atención del operador; sin embargo, la mayoría de los controladores que hay a la venta tienen "protección contra reajuste excesivo", con la cual se detiene la integración automáticamente cuando el controlador alcanza 15 psig (20 mA) o 3 psig (4 mA). Puesto que esta protección es una característica especial del controlador, el ingeniero debe tomar en cuenta si el reajuste excesivo se puede presentar y en ese caso, especificar la protección. En el capítulo 6 se describe la protección contra el reajuste excesivo.

El reajuste excesivo se presenta típicamente en los procesos por lotes, el control en cascada y cuando al elemento final de control se le maneja mediante varios controladores, como es el caso de los controles por sobreposición. En el capítulo 8 se abordan el control en cascada y el control por sobreposición.

### Resumen del controlador por retroalimentación

En esta sección se abordó el tema de los controladores de proceso. Se mencionó cuál es el objetivo de los controladores: tomar decisiones acerca de la manera en que se maneja la variable para mantener la variable que se controla en el punto de control. También se vio el objetivo de los selectores auto/manual y remoto/local, así como la forma de elegir la acción del controlador, inversa/directa. También se estudiaron los diferentes tipos de controladores y se puso especial énfasis en el significado de los parámetros de ajuste: ganancia ($K_c$) o banda proporcional (PB), tiempo de reajuste ($\tau_I$) o rapidez de reajuste ($\tau_I^{-1}$) y rapidez derivativa ($\tau_D$). Finalmente se abordó el tema reajuste excesivo y se explicó su significado.

Aún no se estudia el importante tema de la manera de obtener la afinación óptima de los parámetros de ajuste; lo cual se conoce como "ajuste del controlador" y consiste en ajustar la personalidad del controlador de manera que concuerde con la personalidad del proceso. Esto se presenta en el capítulo 6.

## 5-4. RESUMEN

En este extenso capítulo se presentó parte del equipo (hardware) que se requiere para construir un sistema de control. El capítulo se inició con una breve presentación de algunos términos que se relacionan con los sensores y transmisores, asimismo se estudiaron los parámetros con que se describen tales dispositivos; se continuó con la presentación de algunas consideraciones importantes acerca de las válvulas de control, por ejemplo, acción en caso de falla, dimensionamiento y características. Para mayor información acerca de sensores, transmisores y válvulas se remite al lector al apéndice C.

Después se estudiaron los controladores de proceso por retroalimentación, se presentaron los cuatro tipos más comunes de controladores y se explicó el significado físico de sus parámetros; el ajuste de dichos parámetros se trata en el capítulo 6.

Ahora se pueden utilizar los conocimientos adquiridos en los cinco primeros capítulos de este libro para el diseño de sistemas de control de proceso, que es el tema de los cuatro capítulos siguientes.

## BIBLIOGRAFÍA

1. "Control Valve Handbook," Fisher Controls Co., Marshalltown, Iowa.
2. "Masoneilan Handbook for Control Valve Sizing," Masoneilan International, Inc., Norwood, Mass.
3. "Fisher Catalog 10," Fisher Controls Co., Marshalltown, Iowa.
4. C. L. Smith, *Digital Computer Control*, International Textbook Co., 1972.

## PROBLEMAS

**5-1.** Se utiliza un transmisor electrónico diferencial de presión en combinación con un orificio para medir flujo de manera que la señal de 4-20 mA es proporcional al cuadrado del flujo a través del orificio. El transmisor se calibra para una presión diferencial máxima de 100 pulg de agua y el orificio se dimensiona de manera que el máximo flujo correspondiente es de 750 gpm.

a) Se debe calcular la ganancia del transmisor cuando el flujo es de 500 gpm. Es necesario especificar las unidades.
b) ¿Cuál es la señal de salida del transmisor en porcentaje del rango cuando el flujo es de 500 gpm?

**5-2.** Se necesita dimensionar una válvula de control para regular el flujo de 150 psig de vapor saturado a un calefactor; el flujo normal en estado estacionario es de 1000 lbm/hr, con una presión de entrada de 150 psig y una presión de salida de 50 psig. Se debe obtener la $C_V$ que se requiere para un factor de sobrediseño de 30%.

**5-3.** Se requiere dimensionar una válvula de control que se usará con líquidos; las condiciones de operación son las siguientes:

- Flujo = 52,500 lb/h (normal), 210,000 lb/h (máx)
- $P_1 = 229$ psia
- $P_2 = 124$ psia
- $\mu = 0.2$ cp
- $P_v = 129$ psia
- $T = 104°F$
- $P_c = ?$ psia
- $G_f = 0.92$

Se debe obtener la $C_V$ que se requiere.

**5-4.** Se necesita una válvula para operar con gas en las siguientes condiciones:

- Flujo = 55,000 scfh (normal)
- $G_f = 1.54$
- $T = 40°C$
- $P_1 = 110$ psig
- $P_2 = 11$ psig

Obténgase la dimensión de la válvula para un factor de sobrediseño de 2.

**5-5.** Considérese el proceso que se muestra en la figura 5-19; el benceno fluye a través del conducto con una tasa de 700 gpm a 155°C; la caída de presión entre los puntos 1 y 2, para flujo de estado estacionario, es de 15 psi, esto incluye la caída a través del orificio. A las condiciones de flujo, la densidad del benceno es de 45.49 lbm/pies$^3$, y la viscosidad de 0.17 cp. Se debe obtener la dimensión que requiere la válvula para un factor de sobrediseño de 2.

**5-6.** Considérese el proceso que se muestra en la figura 5-20; se bombea etilbenceno a una tasa de 1000 gpm a 445°F, la caída dinámica de presión entre los puntos 1 y 2 es de 9.36 psi, y entre los puntos 3 y 4 es de 3 psi. Con las condiciones de flujo, la densidad del etilbenceno es de 42.05 lbm/pies$^3$. Obténgase la $C_V$ que se requiere para un factor de sobrediseño del 25%.

**5-7.** Se dimensiona una válvula de control de manera que con las condiciones de diseño el flujo de líquido ($G_f = 0.85$) es de 420 gpm, la caída de presión a través de la válvula es de 3 psi; la válvula está medio abierta. La caída dinámica total de presión en la línea, incluida la caída a través de la válvula, es de 20 psi; la válvula tiene características inherentemente lineales. Se puede suponer que la caída de presión en la línea es proporcional al cuadrado del flujo, pero la caída dinámica de presión total es constante.

a) Calcúlese el factor de capacidad de la válvula $C_V$ (completamente abierta).
b) Calcúlese la ganancia de la válvula para las condiciones de diseño, en gpm por porcentaje de la posición de la válvula.
c) Se debe calcular el flujo cuando se abre la válvula completamente.

**5-8.** Considérese el sistema de control de presión que se muestra en la figura 5-21; el transmisor de presión PT25 tiene una escala de 0-100 psig; el controlador, PIC25, es un controlador proporcional, cuyo valor de base se fija a mitad de la escala y el punto de control es de 10 psig. Se debe obtener la acción correctiva del controlador y la banda proporcional (BP) que se requiere para que, cuando la presión del tanque es de 30 psig, la válvula esté completamente abierta.

**5-9.** Ahora se cambia el sistema de control de presión anterior, el nuevo esquema de control se ilustra en la figura 5-22, el cual se conoce como control en cascada y sus beneficios y principios se estudian en el capítulo 8. En dicho esquema el controlador de presión establece el punto de control del controlador de flujo, por lo tanto, el interruptor remoto/local del controlador de flujo debe estar en remoto. El rango del transmisor de presión es de 0-100 psig; y el del transmisor de flujo, de 0-3000 scfh; ambos controladores son proporcionales. La tasa de flujo nominal a través de la válvula es de 1000 scfh y, para que pase este flujo, se abre un 33%; la válvula de control tiene características lineales.

a) Obténgase la acción de los controladores.
b) Elíjanse los valores de base de ambos controladores, de manera que no haya desviación en ninguno de los dos.
c) Obténgase el ajuste de la banda proporcional del controlador de presión, de manera que, cuando la presión del tanque alcance los 40 psig, el punto de control del controlador de flujo sea de 1700 scfh; el punto de control del controlador de presión es de 10 psig.

**5-10.** Considérese el circuito de nivel que aparece en la figura 5-9; las condiciones de operación de estado estacionario son: $q_i = q_o = 150$ gpm y $h = 6$ pies. Para tal estado estacionario la válvula AA requiere una señal de 9 psig; el rango del transmisor de nivel es de 0-20 pies; y en este proceso se utiliza un controlador proporcional, $K_c = 1$. Se debe calcular la desviación si el flujo de entrada se incrementa a 170 gpm y la válvula requiere 10 psig para que pase éste; la desviación se debe expresar en psig y en pies.

---

# Capítulo 6: Diseño de sistemas de control por retroalimentación con un solo circuito

En los capítulos anteriores se familiarizó al lector con las características dinámicas de los procesos; sensores, transmisores, válvulas de control y controladores. También se expuso la manera de escribir las funciones de transferencia en forma lineal para cada uno de estos componentes, así como la forma de reconocer los parámetros importantes para el diseño de sistemas automáticos de control, a saber: la ganancia de estado estacionario, las constantes de tiempo y el tiempo muerto (retardo de transportación o retardo en tiempo). En este capítulo se aborda la manera de reunir todos esos conceptos para el diseño y ajuste de sistemas de control con un circuito de retroalimentación; primero se analiza un circuito de control por retroalimentación simple y se expone el procedimiento para dibujar su diagrama de bloques y determinar su ecuación característica; a continuación se examina el significado de la ecuación característica, en términos de su utilización para determinar la estabilidad del circuito. Los dos métodos que se emplean en la determinación de la estabilidad del circuito son el de Routh y el de substitución directa. Posteriormente se presentan dos métodos para ajustar el controlador por retroalimentación, es decir, ajustar los parámetros del controlador a las características (o personalidad) de los otros componentes del circuito. También se trata el método de síntesis del controlador, el cual, además de proporcionar algunas relaciones simples del controlador, da cierta visión para la selección de los modos proporcional, integracional y derivativo para varias funciones de transferencia del proceso. Finalmente, se verá la manera de evitar el importante problema de la reposición excesiva, el cual se estudió en el capítulo 5.

Los métodos que se estudian en este capítulo son los que tienen más aplicación en el diseño y ajuste de los circuitos de control por retroalimentación para procesos industriales. Las técnicas de diseño más clásicas de lugar de raíz y el análisis de la respuesta en frecuencia, las cuales se aplican tradicionalmente a los sistemas inherentemente lineales, se estudiarán en el capítulo 7.

## 6-1. CIRCUITO DE CONTROL POR RETROALIMENTACIÓN

El concepto de control por retroalimentación, a pesar de existir desde hace más de dos mil años, no tuvo aplicación práctica en la industria hasta que James Watt lo aplicó en el control de velocidad de su máquina de vapor, hace casi doscientos años; a partir de entonces proliferó la cantidad de aplicaciones industriales de dicho concepto, a tal punto que actualmente en la gran mayoría de los sistemas de control de proceso se incluye al menos un circuito de control por retroalimentación. Ninguna de las técnicas avanzadas de control desarrolladas en los últimos cincuenta años para mejorar el desempeño de los circuitos de control por retroalimentación ha podido reemplazarlo; estas técnicas avanzadas se estudian en un capítulo posterior.

Para revisar el concepto de control por retroalimentación se utiliza el ejemplo del intercambiador de calor que se vio en el capítulo 1; en la figura 6-1 aparece un diagrama del intercambiador.

El objetivo es mantener la temperatura de salida del fluido que se procesa, $T_o(t)$, en el valor que se desea o punto de control, $T_o^{sp}(t)$, en presencia de variaciones en el flujo del fluido que se procesa, $F(t)$ y la temperatura de entrada, $T_i(t)$. La variable que se puede ajustar para controlar la temperatura de salida es el flujo de vapor, $F_s(t)$, ya que determina la cantidad de energía que se suministra al proceso del fluido.

El plan de control por retroalimentación trabaja como sigue: la temperatura de salida o variable controlada se mide con un sensor y transmisor (TT42) que genera una señal $T_o^m(t)$ proporcional a la temperatura; la señal del transmisor o medición se envía al controlador (TIC42), donde se compara contra el punto de control, entonces la función del controlador es generar una señal de salida o variable manipulada, $m(t)$, con base en el error o diferencia entre la medición y el punto de control. La señal de salida del controlador se conecta entonces al actuador de la válvula de control de vapor, mediante un transductor corriente a presión (I/P), esto se debe a que en el presente ejemplo el transmisor y el controlador generan señales de corriente eléctrica, pero el actuador de la válvula se debe operar mediante presión de aire. La función del actuador de la válvula es situar la válvula en proporción con la señal de salida del controlador (ver apéndice C); entonces, el flujo de vapor es una función de la posición de la válvula.

El término "retroalimentación" proviene del hecho de que se mide la variable controlada y dicha medición es "alimentada hacia atrás" para reajustar la válvula de vapor, lo cual ocasiona que las variaciones de la señal se muevan alrededor del circuito como sigue: Las variaciones en la temperatura de salida se captan en el sensor-transmisor y se envían al controlador, donde varía la señal de salida, lo cual, a su vez, ocasiona que la posición de la válvula de control y, consecuentemente, el flujo de vapor, varíen; las variaciones en el flujo de vapor ocasionan que varíe la temperatura de salida, con lo que se completa el circuito.

El desempeño del circuito de control se puede analizar mejor si se dibuja el diagrama de bloques del circuito completo; para esto se dibujan los bloques de cada componente y se conecta la señal de salida de cada bloque con la entrada del siguiente. A continuación se comienza con el intercambiador de calor, como se ve en la figura 6-2; el intercambiador de calor consta de tres bloques, uno para cada una de sus tres entradas.

- $G_T(s)$ es la función de transferencia del proceso, la cual relaciona la temperatura de salida con la de entrada, °C/°C
- $G_F(s)$ es la función de transferencia del proceso que relaciona la temperatura de salida con el flujo del proceso, °C/(kg/s)
- $G_s(s)$ es la función de transferencia del proceso que relaciona la temperatura de salida con el flujo de vapor, °C/(kg/s)

En la figura 6-3 se muestra el diagrama de bloques completo del circuito de control por retroalimentación y la simbología es la siguiente:
- $E(s)$ es la señal de error, mA
- $G_c(s)$ es la función de transferencia del controlador, mA/mA
- $G_v(s)$ es la función de transferencia de la válvula de control, (kg/s)/mA
- $H(s)$ es la función de transferencia del sensor-transmisor, mA/°C
- $K_{sp}$ es el factor de escala para el punto de control de la temperatura, mA/°C

En este punto es necesario notar la correspondencia entre los bloques, o grupos de bloques, en el diagrama de bloques y las componentes del circuito de control; como se esbozó antes, esta comparación se facilita uniformando los símbolos que se utilizan para identificar las diferentes señales. También es importante recordar, según se vio en el capítulo 3, que los bloques en el diagrama representan relaciones lineales entre las señales de entrada y salida, y que las señales son desviaciones de los valores iniciales de estado estable y no valores absolutos de variables.

Con el fin de conservar la simpleza del diagrama, se incluye la ganancia constante del transductor corriente a presión (I/P en la figura 6-1) en la función de transferencia de la válvula de control, $G_v(s)$. La ganancia del transductor es:

$$K_I = \frac{\Delta P}{\Delta I} = \frac{(15 - 3)\,psi}{(20 - 4)\,mA} = 0.75\,psi/mA$$

Se nota que con esto se forman las unidades de $G_v(s)$ (kg/s)/mA; también se supone que la caída de presión a través de la válvula de vapor es constante.

En la señal del punto de control se incluye el término $K_{sp}$ para indicar la conversión de la escala del punto de control, generalmente se calibra en las mismas unidades que la variable controlada, contra la misma base que la señal del transmisor; es decir, °C a mA. Cuando en el controlador se indica la medición y el punto de control en la misma escala, $K_{sp} = K_T$, entonces $K_{sp}$ es numéricamente igual a la ganancia de estado estacionario del transmisor.

### Función de transferencia de circuito cerrado

Mediante la inspección del diagrama de bloques del circuito cerrado (figura 6-3) se ve que en el circuito hay una señal de salida, la variable controlada $T_o(s)$, tres señales de entrada, el punto de control $T_o^{sp}(s)$ y dos perturbaciones, $T_i(s)$ y $F(s)$. Puesto que el flujo de vapor se conecta con la temperatura de salida mediante el circuito de control, se puede esperar que la "respuesta de circuito cerrado" del sistema a las diferentes entradas sea diferente respecto de la respuesta que se tiene cuando el circuito está "abierto". La mayoría de los circuitos de control se pueden abrir mediante el accionamiento de un interruptor en el controlador, de "automático" a "manual" (ver capítulo 5); cuando el controlador está en la posición manual, su salida no responde a la señal de error y, por tanto, es independiente del punto de control y de las señales de medición; por otro lado, cuando está en "automático", la salida del controlador varía cuando varía la señal de medición.

Mediante la aplicación de las reglas del álgebra de los diagramas de bloques que se estudiaron en el capítulo 3, se puede determinar la función de transferencia de circuito cerrado del circuito de salida respecto a cualquiera de sus entradas. Para repasar, se puede suponer que se desea obtener la respuesta de la temperatura de salida $T_o(s)$ a la temperatura de entrada $T_i(s)$; primero se escriben las ecuaciones para cada bloque del diagrama, como sigue:

**Señal de error:**
$$E(s) = K_{sp}T_o^{sp}(s) - T_o^m(s) \quad (6-1)$$

**Variable manipulada:**
$$M(s) = G_c(s)E(s) \quad (6-2)$$

**Flujo de vapor:**
$$F_s(s) = G_v(s)M(s) \quad (6-3)$$

**Temperatura de salida:**
$$T_o(s) = G_s(s)F_s(s) + G_F(s)F(s) + G_T(s)T_i(s) \quad (6-4)$$

**Señal del transmisor:**
$$T_o^m(s) = H(s)T_o(s) \quad (6-5)$$

A continuación se supone que el flujo del proceso y el punto de control no varían, es decir, sus variables de desviación son cero:
$$F(s) = 0 \qquad T_o^{sp}(s) = 0$$

Y todas las variables intermedias se eliminan mediante la combinación de las ecuaciones anteriores, para obtener la relación entre $T_o(s)$ y $T_i(s)$:

$$T_o(s) = G_s(s)G_v(s)G_c(s)[-H(s)T_o(s)] + G_T(s)T_i(s)$$

Esta ecuación se puede reordenar de la manera siguiente:

$$\frac{T_o(s)}{T_i(s)} = \frac{G_T(s)}{1 + H(s)G_c(s)G_v(s)G_s(s)} \quad (6-7)$$

Ésta es la función de transferencia de circuito cerrado entre la temperatura de entrada y la de salida; de manera semejante, si se hace $T_i(s) = 0$ y $T_o^{sp}(s) = 0$ y se combinan de la ecuación (6-1) a la (6-5), se obtiene la función de transferencia de circuito cerrado entre el flujo del proceso y la temperatura de salida:

$$\frac{T_o(s)}{F(s)} = \frac{G_F(s)}{1 + H(s)G_c(s)G_v(s)G_s(s)} \quad (6-8)$$

Finalmente, al hacer $T_i(s) = 0$ y $F(s) = 0$, y combinar de la ecuación (6-1) a la (6-5), se obtiene la función de transferencia de circuito cerrado entre el punto de control y la temperatura de salida:

$$\frac{T_o(s)}{T_o^{sp}(s)} = \frac{G_c(s)G_v(s)G_s(s)K_{sp}}{1 + H(s)G_c(s)G_v(s)G_s(s)} \quad (6-9)$$

Como se vio en el capítulo 3, el denominador es el mismo para las tres entradas, mientras que el numerador es diferente para cada entrada. Se recordará que el denominador es uno más el producto de las funciones de transferencia de todos los bloques del circuito; mientras que el numerador de cada función de transferencia es el producto de los bloques que están sobre la trayectoria directa entre la entrada específica y la salida del circuito. Estos resultados se aplican a cualquier diagrama de bloques que contiene un solo circuito.

A fin de hacerlo más claro, se verifican las unidades del producto de los bloques en el circuito, como sigue:

$$H(s)\cdot G_c(s)\cdot G_v(s)\cdot G_s(s) = \text{sin dimensiones}$$
$$\left(\frac{mA}{°C}\right)\cdot\left(\frac{mA}{mA}\right)\cdot\left(\frac{kg/s}{mA}\right)\cdot\left(\frac{°C}{kg/s}\right)$$

Con esto se demuestra que, como debe ser, el producto de las funciones de transferencia de los bloques en el circuito no tiene dimensiones. También se puede comprobar que las unidades del numerador de cada una de las funciones de transferencia de circuito cerrado son las de la variable de salida entre las unidades de la variable de entrada correspondiente.

### Ecuación característica del circuito

Como se vio en la exposición precedente, el denominador de la función de transferencia de circuito cerrado del circuito de control por retroalimentación es independiente de la ubicación de la entrada en el circuito y, por lo tanto, es característica del circuito. Se recordará, del capítulo 2, que la respuesta sin forzamiento del circuito y su estabilidad dependen de los eigenvalores o raíces de la ecuación que se obtiene cuando el denominador de la función de transferencia del circuito se iguala a cero:

$$1 + H(s)G_c(s)G_v(s)G_s(s) = 0 \quad (6-10)$$

Ésta es la **ecuación característica** del circuito; se observa que la función de transferencia del controlador constituye parte de la ecuación característica del circuito; a esto se debe que se pueda dar forma a la respuesta del circuito mediante el ajuste del controlador. Los otros elementos que forman parte de la ecuación característica son el sensor-transmisor, la válvula de control y aquella parte del proceso que afecta la respuesta de la variable controlada a la variable manipulada, es decir, $G_s(s)$. Por otro lado, las funciones de transferencia del proceso que se relacionan con las perturbaciones [$G_T(s)$ y $G_F(s)$] no son parte de la ecuación característica.

Para demostrar que la ecuación característica determina la respuesta sin forzamiento del circuito, se deriva la respuesta de circuito cerrado a un cambio en la temperatura de entrada, mediante la inversión de la transformada de Laplace de la señal de salida, de la manera en que se estudió en el capítulo 2. Se supone que la ecuación característica se puede reducir a un polinomio de grado $n$ en la variable de la transformada de Laplace, $s$:

$$1 + H(s)G_c(s)G_v(s)G_s(s) = a_ns^n + a_{n-1}s^{n-1} + \ldots + a_0 = 0 \quad (6-11)$$

donde $a_n, a_{n-1}, \ldots, a_0$ son los coeficientes del polinomio. Con un programa de computadora adecuado (como el que se lista en el apéndice D) se pueden encontrar las $n$ raíces de este polinomio y factorizar como sigue:

$$a_ns^n + a_{n-1}s^{n-1} + \ldots + a_0 = a_n(s - r_1)(s - r_2)\ldots(s - r_n) = 0 \quad (6-12)$$

donde $r_1, r_2, \ldots, r_n$ son los eigenvalores o raíces de la ecuación característica, las cuales pueden ser números reales o pares de complejos conjugados; algunas de ellas pueden estar repetidas, como se vio en el capítulo 2.

De la ecuación (6-7), se tiene:

$$T_o(s) = \frac{G_T(s)}{1 + H(s)G_c(s)G_v(s)G_s(s)}T_i(s)$$

A continuación se substituye el denominador por la ecuación (6-12), y se supone que los otros términos aparecen a causa de la función de forzamiento de entrada $T_i(s)$:

$$T_o(s) = \frac{(\text{términos del numerador})}{a_n(s - r_1)(s - r_2)\ldots(s - r_n)(\text{términos de entrada})} \quad (6-14)$$

Entonces se puede expandir esta expresión en fracciones parciales:

$$T_o(s) = \frac{b_1}{s - r_1} + \frac{b_2}{s - r_2} + \ldots + \frac{b_n}{s - r_n} + (\text{términos de entrada}) \quad (6-15)$$

donde $b_1, b_2, \ldots, b_n$ son los coeficientes constantes que se determinan con el método de expansión de fracciones parciales (ver capítulo 2). Al invertir esta expresión con la ayuda de la tabla de transformadas de Laplace (por ejemplo, la tabla 2-1) se obtiene:

$$T_o(t) = b_1e^{r_1t} + b_2e^{r_2t} + \ldots + b_ne^{r_nt} + (\text{términos de entrada})$$
$$\text{Respuesta sin forzamiento} \qquad \text{Respuesta forzada} \quad (6-16)$$

Por tanto, se demostró que cada uno de los términos de la respuesta sin forzamiento contiene una raíz de la ecuación característica; se recordará que los coeficientes $b_1, b_2, \ldots, b_n$ dependen de la función de forzamiento de entrada real, del mismo modo que la respuesta exacta del circuito; sin embargo, la velocidad con que los términos de la respuesta sin forzamiento desaparecen ($r_i < 0$), divergen ($r_i > 0$) u oscilan ($r_i$ es compleja) se determina completamente por las raíces de la ecuación característica. Este concepto se utilizará en la siguiente sección para determinar la estabilidad del circuito.

Con los dos ejemplos siguientes se ilustra el efecto de un controlador puramente proporcional y de uno puramente integral sobre la respuesta de circuito cerrado de un proceso de primer orden; se verá que con el controlador puramente proporcional se acelera la respuesta de primer orden, lo que da por resultado una desviación o error de estado estacionario, como se estableció en el capítulo 5. Por otro lado, con el controlador integral se produce una respuesta de segundo orden que cambia de sobreamortiguada a subamortiguada conforme se incrementa la ganancia del controlador y, como se estableció en el capítulo 4, la respuesta subamortiguada es oscilatoria.

**Ejemplo 6-1. Control proporcional de un proceso de primer orden.** En la figura 6-4a se muestra el diagrama de bloques para un proceso simple; el proceso se puede representar mediante un retardo de primer orden:

$$G(s) = \frac{K}{\tau s + 1}$$

Se debe determinar la función de transferencia de circuito cerrado y la respuesta a un cambio escalón unitario en el punto de control de un controlador proporcional:

$$G_c(s) = K_c$$

**Solución.** La función de transferencia de circuito cerrado se obtiene del álgebra para diagramas de bloques:

$$\frac{C(s)}{R(s)} = \frac{G(s)G_c(s)}{1 + G(s)G_c(s)}$$

Entonces se substituye la función de transferencia del proceso y se simplifica:

$$\frac{C(s)}{R(s)} = \frac{\frac{K}{\tau s + 1}G_c(s)}{1 + \frac{K}{\tau s + 1}G_c(s)}$$
$$= \frac{KG_c(s)}{1 + \tau s + KG_c(s)}$$

Para un controlador proporcional $G_c(s) = K_c$; al substituir, se tiene:

$$\frac{C(s)}{R(s)} = \frac{KK_c}{1 + KK_c + \tau s} = \frac{KK_c/(1 + KK_c)}{[\tau/(1 + KK_c)]s + 1} = \frac{K'}{\tau's + 1}$$

Se ve fácilmente que la ganancia de estado estacionario:

$$K' = \frac{KK_c}{1 + KK_c}$$

siempre es menor que la unidad; y que la constante de tiempo de circuito cerrado:

$$\tau' = \frac{\tau}{1 + KK_c}$$

siempre es menor que la constante de tiempo de circuito abierto $\tau$; en otras palabras, el circuito siempre responde más rápido que el sistema original, pero no coincide completamente con el punto de control, en estado estacionario; es decir, hay una desviación. Para un cambio escalón unitario en el punto de control, de la tabla 2-1, se tiene:

$$R(s) = \frac{1}{s}$$

Se substituye en la función de transferencia y se expande por fracciones parciales para obtener:

$$C(s) = \frac{K'}{s(\tau's + 1)} = \frac{K'}{s} - \frac{K'\tau'}{\tau's + 1}$$

Al invertir, resulta:

$$c(t) = K'(1 - e^{-t/\tau'})$$
$$c(t) = \frac{KK_c}{1 + KK_c}\left[1 - e^{-(1 + KK_c)t/\tau}\right]$$

Aquí se ve que, conforme $t \to \infty$, $c(t) \to KK_c/(1 + KK_c)$.

Puesto que el cambio en el punto de fijación es 1.0 (cambio en escalón unitario), el error se expresa mediante:

$$e(t) = r(t) - c(t) = 1.0 - \frac{KK_c}{1 + KK_c}\left[1 - e^{-(1 + KK_c)t/\tau}\right]$$

Conforme $t \to \infty$:

$$e(t) \to 1 - \frac{KK_c}{1 + KK_c} = \frac{1}{1 + KK_c}$$

Por lo tanto, mientras más alta sea la ganancia del controlador, $K_c$, más se acerca la variable controlada al punto de control de estado estacionario, es decir, la desviación es menor. Con esto se comprueba lo que se estudió en el capítulo 5 y se ilustra en la figura 6-4b.

**Ejemplo 6-2. Control puramente integral de un proceso de primer orden.** Se debe determinar la función de transferencia de circuito cerrado y la respuesta a un cambio escalón unitario en el punto de control del proceso del ejemplo 6-1, con un controlador integral:

$$G_c(s) = \frac{K_I}{s}$$

donde $K_I$ es la ganancia del controlador en min$^{-1}$.

**Solución.** Se substituye la función de transferencia del controlador integracional en la función de transferencia de circuito cerrado del ejemplo 6-1:

$$\frac{C(s)}{R(s)} = \frac{KK_I/s}{1 + \tau s + KK_I/s} = \frac{KK_I}{\tau s^2 + s + KK_I}$$

Por extensión del teorema del valor final a las funciones de transferencia (ver sección 3-3), se substituye $s = 0$, para obtener la ganancia de estado estacionario:

$$\lim_{s \to 0}\frac{C(s)}{R(s)} = \frac{KK_I}{KK_I} = 1$$

Esto significa que, para el controlador integral, la variable controlada siempre coincide con el punto de control de estado estacionario, es decir, no hay desviación.

La ecuación característica del circuito es:

$$\tau s^2 + s + KK_I = 0$$

Las raíces de esta ecuación cuadrática son:

$$r_1, r_2 = \frac{-1 \pm \sqrt{1 - 4KK_I\tau}}{2\tau}$$

Estas raíces son reales para $0 \leq KK_I\tau \leq 1/4$, y complejas conjugadas para $KK_I\tau > 1/4$.

A continuación se determina la respuesta del circuito a un cambio escalón unitario en el punto de fijación para varios valores de $KK_I$. De la tabla 2-1 se tiene que, para un cambio escalón unitario en el punto de control, $R(s) = 1/s$.

Al substituir en la función de transferencia, se tiene:

$$C(s) = \frac{KK_I}{s(\tau s^2 + s + KK_I)}$$

**Caso A. Dos raíces reales y diferentes:** $KK_I\tau < 1/4$

Sean:

$$r_1 = \frac{-1 + \sqrt{1 - 4KK_I\tau}}{2\tau}$$
$$r_2 = \frac{-1 - \sqrt{1 - 4KK_I\tau}}{2\tau}$$

Por expansión de fracciones parciales:

$$C(s) = \frac{1}{s} + \frac{KK_I}{r_1(r_1 - r_2)}\cdot\frac{1}{s - r_1} + \frac{KK_I}{r_2(r_2 - r_1)}\cdot\frac{1}{s - r_2}$$

Al invertir la transformada de Laplace, se tiene:

$$c(t) = 1 + \frac{KK_I}{r_1(r_1 - r_2)}e^{r_1t} + \frac{KK_I}{r_2(r_2 - r_1)}e^{r_2t}$$

Puesto que tanto $r_1$ como $r_2$ son negativas para $K_I$ positiva, en esta respuesta los términos exponenciales tienden a cero conforme el tiempo se incrementa ($t \to \infty$), y entonces el valor de estado estacionario de $c$ es 1.0, o igual al punto de control. Este tipo de respuesta, que se conoce como "sobreamortiguada", se ilustra en la figura 6-5a. Conforme la ganancia $K_I$ del controlador se incrementa, la respuesta se vuelve más rápida, hasta que se torna "críticamente amortiguada" en $KK_I\tau = 1/4$; a continuación se considera este caso.

**Caso B. Raíces reales repetidas:** $KK_I\tau = 1/4$

Entonces:

$$r_1 = r_2 = -\frac{1}{2\tau}$$

Se substituye $KK_I = 1/(4\tau)$ y se sigue el procedimiento de expansión de fracciones parciales para raíces repetidas (capítulo 2):

$$C(s) = \frac{1/(4\tau)}{s(s + 1/2\tau)^2} = \frac{1}{s} - \frac{1}{s + 1/2\tau} - \frac{1/2\tau}{(s + 1/2\tau)^2}$$

Al invertir, con ayuda de una tabla de transformadas de Laplace (tabla 2-1), resulta:

$$c(t) = 1 - \left(1 + \frac{t}{2\tau}\right)e^{-t/2\tau}$$

Esta respuesta críticamente amortiguada se ilustra en la figura 6-5a. Si la ganancia del controlador se incrementa aún más, se obtiene una respuesta "subamortiguada", que es el siguiente y último caso.

**Caso C. Raíces complejas conjugadas:** $KK_I\tau > 1/4$

Entonces:

$$r_1 = -a + iw$$
$$r_2 = -a - iw$$

con:

$$a = \frac{1}{2\tau} \qquad w = \frac{\sqrt{4KK_I\tau - 1}}{2\tau}$$

Se sigue el procedimiento para raíces complejas (ver capítulo 2) y, con la expansión de fracciones parciales, se obtiene:

$$C(s) = \frac{1}{s} - \frac{s + 2a}{s^2 + 2as + (a^2 + w^2)}$$

Al invertir, con ayuda de una tabla de transformadas de Laplace (tabla 2-1), se tiene:

$$c(t) = 1 - e^{-at}\left(\cos wt + \frac{a}{w}\sin wt\right)$$

De este último resultado se observa que, conforme se incrementa la ganancia $K_I$ del circuito, la respuesta oscila alrededor del punto de control (1.0) con frecuencia creciente ($w$); sin embargo, la amplitud de estas oscilaciones siempre decae a cero, a causa del término exponencial $e^{-at}$, lo cual se ilustra en la figura 6-5b.

En los ejemplos anteriores, el circuito de control que se muestra en la figura 6-4a es un circuito por "retroalimentación unitaria", es decir, un circuito en el que no hay elementos en la trayectoria de retroalimentación; en esto se supone que las ganancias del transmisor se incluyen en la función de transferencia del proceso $G(s)$ (también se incluye la ganancia de la válvula), de manera que se puede suponer que todas las señales son porcentajes o fracciones del rango.

En el ejemplo 6-2 se ilustra el punto que se trató en el capítulo 4, referente al hecho de que, a pesar de que la mayoría de los procesos son inherentemente sobreamortiguados, su respuesta puede ser subamortiguada cuando forma parte de un circuito cerrado de control por retroalimentación.

### Respuesta de circuito cerrado en estado estacionario

En el ejemplo precedente se vio que el valor final o estado estacionario (o estático) es un aspecto importante de la respuesta de circuito cerrado, lo cual se debe a que, en la práctica del control de procesos industriales, la presencia del error de estado estacionario o desviación es generalmente inaceptable. En esta sección se estudiará la manera de calcular la desviación cuando está presente y, para hacerlo, se retorna el intercambiador de la figura 6-1, con el correspondiente diagrama de bloques de la figura 6-3, que, como se vio antes, es una representación linealizada del intercambiador de calor. El objetivo es obtener las relaciones de circuito en estado estacionario entre la variable de salida y cada una de las entradas al circuito, mediante la aplicación del teorema del valor final a la función de transferencia de circuito cerrado. En la ecuación (6-8) la función de transferencia de circuito cerrado entre la temperatura de salida y el flujo del fluido que se procesa se expresa mediante:

$$\frac{T_o(s)}{F(s)} = \frac{G_F(s)}{1 + H(s)G_c(s)G_v(s)G_s(s)} \quad (6-8)$$

Se recordará que, en esta expresión, se supone que las variables de desviación para la temperatura de entrada $T_i$ y el punto de control $T_o^{sp}$ son cero cuando estas entradas permanecen constantes. También, como se vio en la sección 3-3, la relación de estado estacionario entre la entrada y la salida, con una función de transferencia, se obtiene al hacer $s = 0$ en la función de transferencia, lo cual se deduce del teorema del valor final de las transformadas de Laplace. Al aplicar este método a la ecuación (6-8), se obtiene:

$$\frac{\Delta T_o}{\Delta F} = \frac{G_F(0)}{1 + H(0)G_c(0)G_v(0)G_s(0)} \quad \text{°C/(kg/s)} \quad (6-17)$$

donde:
- $\Delta T_o$ es el cambio de estado estacionario en la temperatura de salida, °C
- $\Delta F$ es el cambio de estado estacionario en el flujo del fluido que se procesa, kg/s

Si se supone, como generalmente ocurre, que el proceso es estable, entonces:
- $G_F(0) = K_F$ = ganancia de circuito abierto para un cambio en el flujo del fluido que se procesa, °C/(kg/s)
- $G_s(0) = K_s$ = ganancia del proceso a circuito abierto para un cambio en el flujo de vapor, °C/(kg/s)

De manera similar, para la válvula y el sensor-transmisor:
- $G_v(0) = K_v$ = ganancia de la válvula, (kg/s)/mA
- $H(0) = K_T$ = ganancia del sensor-transmisor, mA/°C

Finalmente, si el controlador no tiene acción integrativa:
- $G_c(0) = K_c$ = ganancia proporcional, mA/mA

Al substituir estos términos en la ecuación (6-17), se obtiene:

$$\Delta T_o = \frac{K_F}{1 + K_cK_vK_sK_T}\Delta F \quad \text{°C/(kg/s)} \quad (6-18)$$

Puesto que el cambio en el punto de control es cero, el error de estado estacionario o desviación se expresa mediante:

$$e = \Delta T_o^{sp} - \Delta T_o = -\Delta T_o \quad \text{°C}$$

y, de la combinación de esta relación con la ecuación (6-18), se tiene:

$$e = \frac{-K_F}{1 + K_cK_vK_sK_T}\Delta F \quad \text{°C/(kg/s)} \quad (6-19)$$

Se observa que la desviación se reduce conforme se incrementa la ganancia del controlador, $K_c$.

Para un controlador proporcional-integral-derivativo (PID):

$$G_c(s) = K_c\left(1 + \frac{1}{\tau_Is} + \tau_Ds\right)$$

En este caso, mediante la substitución en la ecuación (6-17), se puede ver que la desviación para cualquier valor de $K_c$ es cero; esto mismo es verdad para el controlador PI ($\tau_D = 0$).

Con la ecuación (6-7) se sigue un procedimiento idéntico para obtener la relación de estado estacionario de la temperatura de salida con la temperatura de entrada, para flujo constante y punto de control:

$$\Delta T_o = \frac{K_T}{1 + K_cK_vK_sK_T}\Delta T_i \quad (6-20)$$

donde:
- $\Delta T_i$ es el cambio de estado estacionario en la temperatura de entrada, °C
- $K_T = G_T(0)$ es la ganancia de circuito abierto en estado estacionario, para un cambio en la temperatura de entrada, °C/°C

Finalmente, la relación de estado estacionario con un cambio en el punto de control a flujo constante del fluido que se procesa, así como temperatura de entrada constante, se obtiene, a partir de la ecuación (6-9):

$$\Delta T_o = \frac{K_cK_vK_sK_{sp}}{1 + K_cK_vK_sK_T}\Delta T_o^{sp} \quad \text{°C/°C} \quad (6-21)$$

donde $\Delta T_o^{sp}$ es el cambio de estado estacionario en el punto de control, °C. En este caso la desviación se expresa mediante (figura 6-3):

$$e = \Delta T_o^{sp} - \Delta T_o$$

Se recordará que, para que el punto de control y las mediciones estén en la misma escala, $K_{sp} = K_T$. De la combinación de estas relaciones con la ecuación (6-21), se tiene:

$$\frac{e}{\Delta T_o^{sp}} = \frac{1}{1 + K_cK_vK_sK_T} \quad \text{°C/°C} \quad (6-22)$$

Nuevamente, mientras más grande es la ganancia del controlador, más pequeña es la desviación, y es cero para cualquier ganancia del controlador, si éste tiene acción integrativa.

**Ejemplo 6-3.** Para el intercambiador de calor de la figura 6-1 se deben calcular, en forma linealizada, las relaciones del error en estado estacionario de la temperatura de salida contra:

a) Un cambio en el flujo del proceso
b) Un cambio en la temperatura de entrada
c) Un cambio en el punto de control

Las condiciones de operación y las especificaciones de los instrumentos son:

- Caudal del fluido en proceso: $F = 12$ kg/s
- Temperatura de entrada: $T_i = 50°C$
- Punto de control: $T_o^{sp} = 90°C$
- Capacidad calorífica del fluido: $C_p = 3750$ J/kg°C
- Calor latente del vapor: $\lambda = 2.25 \times 10^6$ J/kg
- Capacidad de la válvula de vapor: $F_{s,max} = 1.6$ kg/s
- Rango del transmisor: 50 a 150°C

**Solución.** Si se supone que las pérdidas de calor son despreciables, se puede escribir el siguiente balance de energía de estado estacionario:

$$FC_p(T_o - T_i) = F_s\lambda$$

se despeja $F_s$, el flujo de vapor que se requiere para mantener $T_o$ a 90°C con las condiciones de diseño es:

$$F_s = \frac{FC_p(T_o - T_i)}{\lambda} = \frac{(12)(3750)(90 - 50)}{2.25 \times 10^6} = 0.80 \text{ kg/s}$$

El siguiente paso es calcular las ganancias de circuito abierto en estado estacionario para cada uno de los elementos del circuito.

**Intercambiador:** Se despeja $T_o$ del balance de energía de estado estable:

$$T_o = T_i + \frac{F_s\lambda}{FC_p}$$

Se linealiza, como se vio en el capítulo 2, para obtener:

$$K_F = \frac{\partial T_o}{\partial F}\bigg|_{ss} = \frac{-F_s\lambda}{F^2C_p} = \frac{-(0.80)(2.25 \times 10^6)}{(12)^2(3750)} = -3.33 \text{ °C/(kg/s)}$$

$$K_s = \frac{\partial T_o}{\partial F_s}\bigg|_{ss} = \frac{\lambda}{FC_p} = \frac{2.25 \times 10^6}{(12)(3750)} = 50 \text{ °C/(kg/s)}$$

$$K_T = \frac{\partial T_o}{\partial T_i}\bigg|_{ss} = 1.0 \text{ °C/°C}$$

**Válvula de control:** Si se supone que la válvula es lineal, con caída de presión constante y relación lineal entre la posición de válvula, $vp$, y la salida del controlador, $m$, se tiene:

$$F_s = F_{s,max}vp = F_{s,max}\frac{m - 4}{20 - 4}$$

Al linealizar, se obtiene:

$$K_v = \frac{\partial F_s}{\partial m} = \frac{F_{s,max}}{20 - 4} = \frac{1.6}{16} = 0.10 \text{ (kg/s)/mA}$$

**Sensor-transmisor:** El transmisor se puede representar mediante la siguiente relación lineal:

$$T_o^m = 4 + \frac{16(T_o - 50)}{150 - 50}$$

Se linealiza para obtener:

$$K_T = \frac{\partial T_o^m}{\partial T_o} = \frac{16}{150 - 50} = 0.16 \text{ mA/°C}$$

a) Al substituir en la ecuación (6-18), resulta:

$$\Delta T_o = \frac{-3.33}{1 + K_c(0.10)(50)(0.16)}\Delta F = \frac{-3.33}{1 + 0.80K_c}\Delta F$$

b) De substituir en la ecuación (6-20), resulta:

$$\Delta T_o = \frac{1.0}{1 + K_c(0.10)(50)(0.16)}\Delta T_i = \frac{1.0}{1 + 0.80K_c}\Delta T_i$$

c) Al substituir en la ecuación (6-21), resulta:

$$\Delta T_o = \frac{K_c(0.10)(50)(0.16)}{1 + K_c(0.10)(50)(0.16)}\Delta T_o^{sp} = \frac{0.80K_c}{1 + 0.80K_c}\Delta T_o^{sp}$$

Los resultados para diferentes valores de $K_c$ son:

| $K_c$ | $\Delta T_o/\Delta F$ | $\Delta T_o/\Delta T_i$ | $\Delta T_o/\Delta T_o^{sp}$ | $e/\Delta T_o^{sp}$ |
|--------|----------------------|------------------------|----------------------------|-------------------|
| 0 | -3.33 | 1.0 | 0 | 1.0 |
| 0.5 | -2.38 | 0.714 | 0.286 | 0.714 |
| 1.0 | -1.85 | 0.556 | 0.444 | 0.556 |
| 5.0 | -0.67 | 0.200 | 0.800 | 0.200 |
| 10.0 | -0.37 | 0.111 | 0.889 | 0.111 |
| 20.0 | -0.20 | 0.059 | 0.941 | 0.059 |
| 100.0 | -0.04 | 0.012 | 0.988 | 0.012 |

Se observa que el cambio en la temperatura de entrada provocado por las perturbaciones se acerca a cero conforme la ganancia se incrementa, y que el cambio en la temperatura de salida, debido a un cambio en el punto de control, se aproxima a la unidad.

Con los resultados del ejemplo precedente se ilustra la observación que se hizo en el capítulo 5, respecto al hecho de que la desviación decrece cuando se incrementa la ganancia del controlador proporcional y, como se indicó ahí, a la ganancia del controlador la limita la estabilidad del circuito. Esto se verá en la próxima sección.

**Ejemplo 6-4. Control de temperatura para un tanque de calentamiento con agitación continua.**

El tanque con agitación que se ilustra en la figura 6-6 se utiliza para calentar una corriente en proceso, de manera que se logre una composición uniforme de los componentes premezclados. El control de temperatura es importante, porque con una alta temperatura se tiende a descomponer el producto, mientras que, con una temperatura baja, la mezcla resulta incompleta. El tanque se calienta mediante el vapor que se condensa en un serpentín; se utiliza un controlador proporcional-integral-derivativo (PID) para controlar la temperatura en el tanque, mediante el manejo de la posición de la válvula de vapor. Se desea obtener el diagrama de bloques completo y la ecuación característica del circuito para los siguientes datos de diseño.

**Proceso:** La densidad de la alimentación es de 68.0 lb/pies$^3$, y la capacidad calorífica de 0.80 Btu/lb-°F. En el reactor se mantiene constante el volumen, $V$, de líquido a 120 pies$^3$. El serpentín consta de 240 pies de tubo de acero de 4 pulgadas, cédula 40, con un peso de 10.8 lb/pie, capacidad calorífica de 0.12 Btu/lb-°F y diámetro externo de 7.500 pulg; el coeficiente total de transferencia de calor, $U$, se estima que es de 2.1 Btu/min-pie$^2$-°F, con base en el área externa del serpentín. El vapor de que se dispone está saturado y a una presión de 30 psia; se puede suponer que el calor potencial de condensación $\lambda$ es constante, con un valor de 966 Btu/lb.

**Condiciones de diseño:** En las condiciones de diseño, el flujo de alimentación es de 15 pies$^3$/min, a una temperatura $T_i$ de 100°F. El contenido del tanque se debe mantener a una temperatura $T$ de 150°F. Las posibles perturbaciones son cambios en la tasa de alimentación y en la temperatura.

**Sensor y transmisor de temperatura:** El sensor de temperatura se calibra para un rango de 100 a 200°F y una constante de tiempo $\tau_T$ de 0.75 min.

**Válvula de control:** La válvula de control se diseña con una sobrecapacidad del 100%, y las variaciones en la caída de presión se pueden despreciar. La válvula es de porcentaje igual, con un parámetro de ajuste de rango de 50; la constante de tiempo $\tau_v$ del actuador es de 0.20 min.

**Solución:** El método que se utiliza es obtener primeramente las ecuaciones con que se describe el comportamiento dinámico del tanque, la válvula de control, el sensor-transmisor y el controlador; entonces se linealizan y se obtiene su transformada de Laplace, para obtener el diagrama de bloques del circuito.

**Proceso:** Del balance de energía para el líquido en el tanque, si se supone que las pérdidas de calor son despreciables, la mezcla es perfecta y el volumen y las propiedades físicas son constantes, resulta la siguiente ecuación:

$$\rho C_p V\frac{dT(t)}{dt} = \rho C_p F(t)[T_i(t) - T(t)] + UA[T_s(t) - T(t)]$$

donde:
- $A$ es el área de transferencia de calor, pies$^2$
- $T_s(t)$ es la temperatura de condensación del vapor, °F
- los otros símbolos se definieron en el planteamiento del problema

Para el líquido que contiene el tanque, el $C_v$ en términos de acumulación, se aproximó a $C_p$.

El balance de energía en el serpentín, si se supone que el metal del serpentín está esencialmente a la misma temperatura que el vapor que se condensa, resulta:

$$C_M\frac{dT_s(t)}{dt} = w(t)\lambda - UA[T_s(t) - T(t)]$$

donde:
- $w(t)$ es la tasa del vapor, lb/min
- $C_M$ es la capacidad calorífica del metal del serpentín, Btu/°F

Puesto que la tasa de vapor es la salida de la válvula de control y una entrada al proceso, el modelo del proceso está completo.

**Válvula de control:** La ecuación para una válvula de porcentaje igual con presión de entrada y caída de presión constantes, se puede escribir como:

$$w(t) = w_{max}\alpha^{vp(t)-1}$$

donde:
- $w_{max}$ es el flujo máximo a través de la válvula de vapor, lb/min
- $\alpha$ es el parámetro de ajuste en rango de porcentaje igual
- $vp(t)$ es la posición de la válvula en una escala de 0 a 1

La variación en la caída de presión a través de la válvula, a la temperatura de condensación del vapor (y presión), se despreció en este ejemplo simple. El actuador de la válvula se puede modelar mediante un retardo de primer orden:

$$W(s) = \frac{K_v}{\tau_vs + 1}M(s)$$

donde $M(s)$ es la señal de salida del controlador en porcentaje.

**Sensor-transmisor (TT21):** El sensor-transmisor se puede representar mediante un retardo de primer orden:

$$\frac{T_m(s)}{T(s)} = \frac{K_T}{\tau_Ts + 1}$$

donde $T_m(s)$ es la transformada de Laplace de la señal de salida del transmisor, %.

**Controlador con retroalimentación (TIC21):** La función de transferencia del controlador PID es:

$$G_c(s) = \frac{M(s)}{E(s)} = K_c\left(1 + \frac{1}{\tau_Is} + \tau_Ds\right)$$

Con esto se completa la obtención de la ecuación para el circuito de control de temperatura. El siguiente paso es linealizar las ecuaciones del modelo y sus transformadas de Laplace para obtener el diagrama de bloques del circuito.

**Ecuaciones linealizadas y transformadas de Laplace:**

Mediante los métodos que se aprendieron en la sección 2-3, se obtienen las ecuaciones del modelo del tanque en forma lineal y en términos de las variables de desviación:

$$\rho C_p V\frac{dT(t)}{dt} = \rho C_p F T_i(t) + \rho C_p(T_i - T)F(t) + UA T_s(t) - (UA + \bar{F}\rho C_p)T(t)$$

donde $T(t)$, $T_s(t)$, $F(t)$, $T_i(t)$ y $W(t)$ son las variables de desviación.

Se obtiene la transformada de Laplace de estas ecuaciones y se reordena, como se vio en el capítulo 2, para tener:

$$T(s) = \frac{K_T}{\tau s + 1}T_i(s) + \frac{K_F}{\tau s + 1}F(s) + \frac{K_s}{\tau s + 1}T_s(s)$$

donde:

$$\tau = \frac{\rho C_p V}{UA + \bar{F}\rho C_p}$$
$$K_T = \frac{\bar{F}\rho C_p}{UA + \bar{F}\rho C_p}$$
$$K_F = \frac{\rho C_p(\bar{T}_i - \bar{T})}{UA + \bar{F}\rho C_p}$$
$$K_s = \frac{UA}{UA + \bar{F}\rho C_p}$$

De linealizar la ecuación de la válvula, resulta:

$$W(t) = w_{max}(\ln \alpha)\alpha^{\bar{vp}-1}VP(t)$$

donde $VP(t)$ es la variable de desviación de la posición de la válvula.

De la transformada de Laplace de esta ecuación, se tiene:

$$W(s) = K_vVP(s)$$

Al combinar esta ecuación con la función de transferencia del actuador, se puede eliminar $VP(s)$:

$$\frac{W(s)}{M(s)} = \frac{K_v}{\tau_vs + 1}$$

donde:

$$K_v = \frac{w_{max}(\ln \alpha)\alpha^{\bar{vp}-1}}{100}$$

A partir de lo que se aprendió en el capítulo 5, se puede determinar que la ganancia del transmisor es:

$$K_T = \frac{100 - 0}{200 - 100} = \frac{100}{100} = 1.0 \text{ %/°F}$$

En la figura 6-7a aparece el diagrama de bloques completo del circuito; todas las funciones de transferencia del diagrama se obtuvieron arriba.

Se utilizan las reglas para manejo de diagramas de bloques que se aprendieron en el capítulo 3 para simplificar el diagrama a la forma que aparece en la figura 6-7b. Las funciones de transferencia que aparecen en el diagrama son:

$$G_1(s) = \frac{K_T}{\tau s + 1}$$
$$G_2(s) = \frac{K_F}{\tau s + 1}$$
$$G_3(s) = \frac{K_s(\tau_vs + 1)}{(\tau s + 1)(\tau_vs + 1) - K_s}$$
$$G_4(s) = \frac{K_T}{\tau_Ts + 1}$$

Las funciones de transferencia de circuito cerrado para cada una de las entradas son:

$$T(s) = \frac{G_1(s)G_c(s)G_3(s)H(s)}{1 + H(s)G_c(s)G_3(s)G_4(s)}T_o^{sp}(s)$$

$$T(s) = \frac{G_2(s)}{1 + H(s)G_c(s)G_3(s)G_4(s)}F(s)$$

$$T(s) = \frac{G_1(s)}{1 + H(s)G_c(s)G_3(s)G_4(s)}T_i(s)$$

donde:

$$G_c(s) = K_c\left(1 + \frac{1}{\tau_Is} + \tau_Ds\right)$$
$$H(s) = \frac{K_T}{\tau_Ts + 1}$$

La ecuación característica del circuito es:

$$1 + \frac{K_c\left(1 + \frac{1}{\tau_Is} + \tau_Ds\right)K_s(\tau_vs + 1)K_T}{(\tau s + 1)(\tau_vs + 1) - K_s(\tau_Ts + 1)} = 0$$

A continuación se obtienen los valores numéricos:

$$K_T = 1.0 \text{ %/°F}$$
$$\tau_T = 0.75 \text{ min}$$
$$\tau_v = 0.20 \text{ min}$$

De la descripción del serpentín, se tiene:

$$A = 241.5 \text{ pies}^2$$
$$C_M = (205 \text{ pies})(10.8 \text{ lb/pie})(0.12 \text{ Btu/lb-°F}) = 265.7 \text{ Btu/°F}$$
$$\tau = \frac{(12)(68.0)(0.80)}{(2.1)(241.5) + (15)(68)(0.80)} = \frac{652.8}{507.15 + 816.0} = 0.493 \text{ min}$$
$$K_F = \frac{(2.1)(241.5)}{(2.1)(241.5) + (15)(68)(0.80)} = \frac{507.15}{1323.15} = 0.383 \text{ °F/°F}$$
$$K_s = \frac{(2.1)(241.5)}{(2.1)(241.5) + (15)(68)(0.80)} = 0.383 \text{ °F/°F}$$
$$K_v = \frac{(2.1)(241.5)}{966} = 0.525 \text{ °F/(lb/min)}$$

Para dimensionar la válvula de control se aprovecha el hecho de que las condiciones de diseño son, en estado estacionario:

$$T_s = \frac{(15)(68)(0.80)(150 - 100)}{(2.1)(241.5)} + 150 = \frac{40800}{507.15} + 150 = 230.4 \text{ °F}$$
$$w = \frac{(2.1)(241.5)(230.4 - 150)}{966} = \frac{40776}{966} = 42.2 \text{ lb/min}$$

Y:

$$w_{max} = 2w = 84.4 \text{ lb/min}$$

Con estos números la ecuación característica es:

$$0.387s^3 + 3.272s^2 + 7.859s + (6.043 + 1.205K_c\tau_D)s + (0.617 + 1.205K_c) = 0$$

En este ejemplo se muestra la manera en que se pueden utilizar los principios básicos de la ingeniería de proceso para analizar circuitos simples de control por retroalimentación. A partir de la ecuación característica se puede estudiar la estabilidad del circuito y, con base en las funciones de transferencia de circuito cerrado es posible calcular la respuesta del circuito cerrado a varias funciones de forzamiento de entrada, para diferentes valores de los parámetros de ajuste del controlador $K_c$, $\tau_I$ y $\tau_D$.

## 6-2. ESTABILIDAD DEL CIRCUITO DE CONTROL

Como se definió en el capítulo 2, un sistema es estable si su salida permanece limitada para una entrada limitada. La mayoría de los procesos industriales son estables a circuito abierto, es decir, son estables cuando no forman parte de un circuito de control por retroalimentación; esto equivale a decir que la mayoría de los procesos son autorregulables, o sea, la salida se mueve de un estado estable a otro, debido a los cambios en las señales de entrada. Un ejemplo típico de proceso inestable a circuito abierto es el tanque exotérmico de reacción con agitación, en el cual algunas veces existe un punto de operación inestable en el que, al incrementar la temperatura, se produce un incremento en la tasa de reacción, con el consecuente incremento en la tasa de liberación de calor, lo cual, a su vez, ocasiona un mayor incremento en la temperatura.

Aun para los procesos estables a circuito abierto, la estabilidad vuelve a ser considerable cuando el proceso forma parte de un circuito de control por retroalimentación, debido a que las variaciones en las señales se refuerzan unas a otras conforme viajan sobre el circuito, y ocasionan que la salida y todas las otras señales en el circuito se vuelvan ilimitadas. Como se observó en el capítulo 1, el comportamiento del circuito de control por retroalimentación es esencialmente una operación de ensayo y error. En algunas circunstancias, las oscilaciones se pueden incrementar en magnitud, de lo cual resulta un proceso inestable. La ilustración más sencilla de un circuito de retroalimentación inestable es el controlador cuya acción de acción es opuesta a la que debería ser; por ejemplo, en el intercambiador de calor que se esbozó en la sección precedente, si la salida del controlador se incrementara al aumentar la temperatura (controlador de acción directa), el circuito es inestable, porque al abrir la válvula de vapor se provoca un mayor incremento en la temperatura. En este caso, lo que se necesita es un controlador de acción inversa cuya salida se decremente cuando la temperatura se incremente, de manera que se cierre la válvula de vapor y baje la temperatura. Sin embargo, aun con el controlador de acción adecuada, el sistema se puede volver inestable, debido a los retardos en el circuito, lo cual ocurre generalmente cuando se incrementa la ganancia del circuito. En consecuencia, la ganancia del controlador a la que el circuito alcanza el umbral de inestabilidad es de gran importancia en el diseño de un circuito de control con retroalimentación. Esta ganancia máxima se conoce como **ganancia última**, $K_{c_u}$.

En esta sección se determina el criterio de estabilidad para sistemas dinámicos y se exponen dos métodos para calcular la ganancia última: la prueba de Routh y la substitución directa; por lo tanto, aquí se estudiará el efecto de los diferentes parámetros del circuito sobre su estabilidad.

### Criterio de estabilidad

Con anterioridad, se vio que la respuesta de un circuito de control a una cierta entrada se puede representar [ecuación (6-16)] mediante:

$$c(t) = b_1e^{r_1t} + b_2e^{r_2t} + \ldots + b_ne^{r_nt} + (\text{términos de entrada}) \quad (6-23)$$

donde:
- $c(t)$ es la salida del circuito o variable controlada
- $r_1, r_2, \ldots, r_n$ son los eigenvalores o raíces de la ecuación característica del circuito

Si se supone que los términos de entrada permanecen limitados conforme se incrementa el tiempo, la estabilidad del circuito requiere que también los términos de la respuesta sin forzamiento permanezcan limitados conforme se incrementa el tiempo; esto depende únicamente de las raíces de la ecuación característica, y se puede expresar como sigue:

Para raíces reales: Si $r < 0$, entonces $e^{rt} \to 0$ conforme $t \to \infty$
Para raíces complejas: $r = \sigma + i\omega$; Si $\sigma < 0$, entonces $e^{\sigma t}(\cos \omega t + i\sin \omega t) \to 0$ conforme $t \to \infty$

En otras palabras, la parte real de las raíces complejas, así como las raíces reales, deben ser negativas para que los términos correspondientes de la respuesta tiendan a cero. A este resultado no lo afectan las raíces repetidas, ya que únicamente se introduce un polinomio de tiempo en la solución (ver capítulo 2); que no suple el efecto del término exponencial de decaimiento. De todo esto se concluye que, si cualquier raíz de la ecuación característica es un número real y positivo o un número complejo con parte real positiva, en la respuesta [ecuación (6-23)] ese término no estará limitado y la respuesta completa será ilimitada, aun cuando los demás términos tiendan a cero; esto lleva al siguiente enunciado del criterio de estabilidad para un circuito de control:

> Para que el circuito de control con retroalimentación sea estable, todas las raíces de su ecuación característica deben ser números reales negativos o números complejos con partes reales negativas.

Si ahora se define el plano complejo $s$ como una gráfica de dos dimensiones, con el eje horizontal para la parte real de las raíces y el vertical para la parte imaginaria, se puede hacer el siguiente enunciado gráfico del criterio de estabilidad (ver figura 6-8):

> Para que el circuito de control con retroalimentación sea estable, todas las raíces de su ecuación característica deben caer en la mitad izquierda del plano $s$, que también se conoce como "plano izquierdo".

Cabe hacer notar que ambos enunciados del criterio de estabilidad en el dominio de Laplace se aplican en general a cualquier sistema físico, y no solamente a circuitos de control con retroalimentación. En cada caso la ecuación característica se obtiene por igualación a cero del denominador de la forma lineal de la función de transferencia del sistema.

Una vez que se enunció el criterio de estabilidad se puede volver la atención a la determinación de la estabilidad de un circuito de control.

### Prueba de Routh

La prueba de Routh es un procedimiento para determinar el número de raíces de un polinomio con parte real positiva sin necesidad de encontrar realmente las raíces por métodos iterativos. Puesto que para que un sistema sea estable se requiere que ninguna de las raíces de su ecuación característica tenga parte real positiva, la prueba de Routh es bastante útil para determinar la estabilidad.

Con la disponibilidad que se tiene actualmente de programas de computadora y calculadora para encontrar las raíces de los polinomios, la prueba de Routh no sería útil si el problema fuera exclusivamente encontrar si un circuito de retroalimentación es estable o no, una vez que se especifican todos los parámetros del circuito; sin embargo, el problema más importante es determinar los límites de un parámetro específico del circuito -generalmente la ganancia del controlador- dentro de los cuales el circuito es estable, y la prueba de Routh es de lo más útil para resolver dicho problema.

La mecánica de la prueba de Routh se puede presentar como sigue: dado un polinomio de grado $n$:

$$a_ns^n + a_{n-1}s^{n-1} + \ldots + a_1s + a_0 = 0 \quad (6-24)$$

donde $a_n, a_{n-1}, \ldots, a_0$ son los coeficientes del polinomio; se debe determinar cuántas raíces tienen parte real positiva.

Para realizar la prueba, primero se debe preparar el siguiente arreglo:

| Fila | | | | | |
|------|---------|---------|---------|---------|---------|
| 1 | $a_n$ | $a_{n-2}$ | $a_{n-4}$ | $\ldots$ | 0 |
| 2 | $a_{n-1}$ | $a_{n-3}$ | $a_{n-5}$ | $\ldots$ | 0 |
| 3 | $b_1$ | $b_2$ | $b_3$ | $\ldots$ | 0 |
| 4 | $c_1$ | $c_2$ | $c_3$ | $\ldots$ | 0 |
| $\vdots$ | $\vdots$ | $\vdots$ | $\vdots$ | $\ddots$ | $\vdots$ |
| $n+1$ | $e_1$ | 0 | 0 | $\ldots$ | 0 |

en el cual, los datos de la fila 3 a la $n+1$ se calculan mediante:

$$b_1 = \frac{a_{n-1}a_{n-2} - a_na_{n-3}}{a_{n-1}}$$
$$b_2 = \frac{a_{n-1}a_{n-4} - a_na_{n-5}}{a_{n-1}}$$
etc.

$$c_1 = \frac{b_1a_{n-3} - a_{n-1}b_2}{b_1}$$
$$c_2 = \frac{b_1a_{n-5} - a_{n-1}b_3}{b_1}$$
etc.

y así, sucesivamente. El proceso se continúa hasta que todos los términos nuevos sean cero.

Una vez que se completa el arreglo, se puede determinar el número de raíces con parte real positiva del polinomio, mediante el conteo de la cantidad de cambios de signo en la columna extrema izquierda del arreglo; en otras palabras, para que todas las raíces del polinomio estén en el plano $s$ izquierdo, todos los términos en la columna izquierda del arreglo deben tener el mismo signo.

Al fin de ilustrar la utilización de la prueba de Routh, se aplica a continuación para determinar la ganancia última del controlador de temperatura del intercambiador que se presentó en la sección precedente.

**Ejemplo 6-5. Determinación de la ganancia última de un controlador de temperatura mediante la prueba de Routh.**

Se supone que las funciones de transferencia de los diferentes elementos del circuito de control de temperatura de la figura 6-3 son como sigue:

**Intercambiador:** La respuesta del intercambiador al flujo de vapor tiene una ganancia de 50°C/(kg/s) y una constante de tiempo de 30 s:

$$G_s(s) = \frac{50}{30s + 1} \text{ °C/(kg/s)}$$

**Sensor-transmisor:** El sensor-transmisor tiene una escala calibrada de 50 a 150°C y una constante de tiempo de 10 s:

$$H(s) = \frac{1.0}{10s + 1} \text{ %/°C}$$

Nota: en éste y otros ejemplos se utiliza el "porcentaje de rango" (%) como unidades de las señales del transmisor y el controlador. Para señales electrónicas 100% = 16 mA, y para señales neumáticas, 100% = 12 psi.

**Válvula de control:** La válvula de control tiene una capacidad máxima de 1.6 kg/s de vapor, características lineales y constante de tiempo de 3 s:

$$G_v(s) = \frac{0.016}{3s + 1} \text{ (kg/s)/%}$$

(se supone que la caída de presión a través de la válvula es constante.)

**Controlador:** El controlador es proporcional:

$$G_c(s) = K_c \text{ %/%}$$

Entonces, el problema es determinar la ganancia última del controlador, es decir, el valor de $K_c$ al cual el circuito se vuelve marginalmente estable.

**Solución.** La ecuación característica se obtiene de la ecuación (6-10):

$$1 + H(s)G_c(s)G_v(s)G_s(s) = 0$$

$$1 + \frac{1.0}{10s + 1}\cdot\frac{K_c}{1}\cdot\frac{0.016}{3s + 1}\cdot\frac{50}{30s + 1} = 0$$

Ahora se debe reordenar la ecuación en forma polinómica:

$$(10s + 1)(30s + 1)(3s + 1) + 0.80K_c = 0$$
$$900s^3 + 420s^2 + 43s + 1 + 0.80K_c = 0$$

El siguiente paso es preparar el arreglo de Routh:

| Fila | | | |
|------|-----|-----|-----|
| 1 | 900 | 43 | 0 |
| 2 | 420 | $1 + 0.80K_c$ | 0 |
| 3 | $b_1$ | 0 | 0 |
| 4 | $1 + 0.80K_c$ | 0 | 0 |

donde:

$$b_1 = \frac{(420)(43) - 900(1 + 0.80K_c)}{420} = \frac{17160 - 720K_c}{420}$$

Para que el circuito de control sea estable, todos los términos de la columna izquierda deben tener el mismo signo, positivo en este caso, y para esto se requiere que:

$$b_1 \geq 0$$
o:
$$17160 - 720K_c \geq 0$$
$$K_c \leq 23.8$$

$$1 + 0.80K_c \geq 0$$
o:
$$0.80K_c \geq -1$$
$$K_c \geq -1.25$$

En este caso, el límite inferior de $K_c$ es negativo, pero no tiene importancia, puesto que una ganancia negativa indica que la acción del controlador no es la correcta (se abre la válvula de vapor al incrementarse la temperatura). El límite superior de la ganancia del controlador es la ganancia última que se busca:

$$K_{c_u} = 23.8 \text{ %/%}$$

Esto indica que, al ajustar el controlador proporcional para este circuito, la ganancia no debe exceder de 23.8 ni reducirse la banda proporcional por debajo de $100/23.8 = 4.2\%$.

En la sección precedente se vio que la desviación o error de estado estacionario inherente a los controladores proporcionales se puede reducir mediante el incremento de la ganancia del controlador; aquí se ve que la estabilidad impone un límite a la magnitud de la ganancia. Es de interés estudiar la manera en que afectan a la ganancia los otros parámetros del circuito.

### Efecto de los parámetros del circuito sobre la ganancia última

Si se supone que la escala de calibración del sensor-transmisor de temperatura se reduce a 75-125°C, entonces la nueva ganancia y función de transferencia del transmisor es:

$$K_T = \frac{100\%}{(125 - 75)°C} = 2.0 \text{ %/°C}$$
$$H(s) = \frac{2.0}{10s + 1} \text{ %/°C}$$

Si se repite la prueba de Routh con esta nueva ganancia, se obtiene una ganancia última de:

$$K_{c_u} = 11.9 \text{ %/% (PB = 8.4\%)}$$

Ésta es exactamente la mitad de la ganancia última original, con lo que se demuestra que la ganancia última del circuito permanece igual. La ganancia del circuito se define como el producto de las ganancias de todos los bloques del circuito:

$$K_L = K_cK_vK_sK_T \quad (6-25)$$

donde:
- $K_L$ = ganancia del circuito (sin dimensiones)
- $K_T$ = ganancia del sensor transmisor, %/°C
- $K_s$ = ganancia del proceso, °C/(kg/s)
- $K_v$ = ganancia de la válvula de control, (kg/s)/%
- $K_c$ = ganancia del controlador, %/%

Para los dos casos considerados hasta el momento, las ganancias últimas de circuito son:

$$K_{L_u} = 23.8(0.016)(50)(1.0) = 19.04$$
$$K_{L_u} = 11.9(0.016)(50)(2.0) = 19.04$$

De manera semejante, si se duplica el tamaño de la válvula de control y, por tanto, su ganancia, la ganancia última del controlador se reduce a la mitad de su valor original.

A continuación se supone que se instala un sensor-transmisor más rápido, con una constante de tiempo de 5 s para reemplazar al instrumento de 10 s; la nueva función de transferencia se expresa mediante:

$$H(s) = \frac{1.0}{5s + 1} \text{ %/°C}$$

Se repite la prueba de Routh con esta nueva función de transferencia:

$$1 + \frac{1.0}{5s + 1}\cdot\frac{K_c}{1}\cdot\frac{0.016}{3s + 1}\cdot\frac{50}{30s + 1} = 0$$
$$450s^3 + 255s^2 + 38s + 1 + 0.80K_c = 0$$

| Fila | | | |
|------|-----|-----|-----|
| 1 | 450 | 38 | 0 |
| 2 | 255 | $1 + 0.80K_c$ | 0 |
| 3 | $b_1$ | 0 | 0 |
| 4 | $1 + 0.80K_c$ | 0 | 0 |

donde:

$$b_1 = \frac{(255)(38) - (450)(1 + 0.80K_c)}{255} = \frac{9240 - 360K_c}{255}$$

Y la ganancia última del controlador es:

$$K_{c_u} = \frac{9240}{360} = 25.7 \text{ %/%}$$

La reducción en la constante de tiempo del sensor da como resultado un ligero incremento en la ganancia última, debido a que se reduce el retardo de medición en el circuito de control. Si se reduce la constante de tiempo de la válvula de control, se obtiene un resultado similar, sin embargo, el incremento en la ganancia última es aún menor; porque la válvula no es tan lenta como el sensor-transmisor; queda al lector la verificación de esto.

Finalmente, se considera el caso donde un cambio en el diseño del intercambiador da como resultado una constante de tiempo del proceso más corta; a saber, de 30 a 20 s. La nueva función de transferencia es:

$$G_s(s) = \frac{50}{20s + 1} \text{ °C/(kg/s)}$$

Nuevamente se repite el procedimiento de la prueba de Routh:

$$1 + \frac{1.0}{10s + 1}\cdot\frac{K_c}{1}\cdot\frac{0.016}{3s + 1}\cdot\frac{50}{20s + 1} = 0$$
$$600s^3 + 290s^2 + 33s + 1 + 0.80K_c = 0$$

| Fila | | | |
|------|-----|-----|-----|
| 1 | 600 | 33 | 0 |
| 2 | 290 | $1 + 0.80K_c$ | 0 |
| 3 | $b_1$ | 0 | 0 |
| 4 | $1 + 0.80K_c$ | 0 | 0 |

donde:

$$b_1 = \frac{(290)(33) - 600(1 + 0.80K_c)}{290} = \frac{9570 - 480K_c}{290}$$

Entonces la ganancia última es:

$$K_{c_u} = \frac{9570}{480} = 19.9 \text{ %/%}$$

Curiosamente, la ganancia última se reduce con una disminución en la constante de tiempo del proceso, lo cual es contrario al efecto que se obtiene al reducir la constante de tiempo del sensor-transmisor; esto se debe a que, cuando se reduce la constante de tiempo más larga o dominante, el efecto relativo de los otros retardos del circuito se vuelve más pronunciado. En otras palabras, en términos de la ganancia última, reducir la constante de tiempo más larga equivale a incrementar proporcionalmente las otras constantes de tiempo del circuito. Lo que no se puede demostrar mediante la prueba de Routh es que el circuito con la constante de tiempo más corta responde más rápido que el original, pero se puede demostrar mediante el método de substitución directa.

### Método de substitución directa

El método de substitución directa se basa en el hecho de que las raíces de la ecuación característica varían continuamente con los parámetros del circuito; el punto en que el circuito se vuelve inestable, al menos una, y generalmente dos, de las raíces se encuentra en el eje imaginario del plano complejo, es decir, deben existir raíces puramente imaginarias. Otra manera de ver esto es que, para que las raíces se muevan del plano izquierdo al derecho, deben cruzar el eje imaginario; en este punto se dice que el circuito es "marginalmente estable" y el término correspondiente de la salida del circuito en el dominio de Laplace es:

$$\frac{b_i}{s^2 + \omega_u^2} + (\text{otros términos}) \quad (6-26)$$

o, al invertir este término con la tabla 2-1, se ve que es una onda senoidal en el dominio del tiempo:

$$c(t) = b_i\sin(\omega_u t + \theta) + (\text{otros términos}) \quad (6-27)$$

donde:
- $\omega_u$ = frecuencia de la onda senoidal
- $\theta$ = ángulo de fase de la onda senoidal
- $b_i$ = amplitud de la onda senoidal (constante)

Esto significa que, en el punto de estabilidad marginal, la ecuación característica debe tener un par de raíces puramente imaginarias:

$$s = \pm i\omega_u$$

La frecuencia $\omega_u$ con que oscila el circuito es la **frecuencia última**. Justo antes de alcanzar el punto de inestabilidad marginal, el sistema oscila con una amplitud que tiende a decaer, mientras que después de ese punto la amplitud de la oscilación se incrementa con el tiempo. En el punto de estabilidad marginal, la amplitud de la oscilación permanece constante en el tiempo. Esto se ilustra en la figura 6-9, donde la relación entre el período último, $T_u$, y la frecuencia última, $\omega_u$, en rad/s se expresa mediante:

$$\omega_u = \frac{2\pi}{T_u} \quad (6-28)$$

El método de la substitución directa consiste en substituir $s = i\omega_u$ en la ecuación característica, de donde resulta una ecuación compleja que se puede convertir en dos ecuaciones simultáneas:

Parte real = 0
Parte imaginaria = 0

A partir de esto se pueden resolver dos incógnitas: una es la frecuencia última $\omega_u$, la otra es cualquier parámetro del circuito, generalmente la ganancia última. A continuación se ilustra esto mediante el tratamiento del ejemplo de control de temperatura con el método de substitución directa.

**Ejemplo 6-6.** Se debe determinar la ganancia y frecuencia últimas para el controlador de temperatura del ejemplo 6-5, mediante el método de substitución directa.

**Solución.** Del ejemplo 6-5 se toma la ecuación característica para el caso básico, en forma de polinomio:

$$900s^3 + 420s^2 + 43s + 1 + 0.80K_c = 0$$

Ahora se substituye $s = i\omega_u$ y $K_c = K_{c_u}$:

$$900(i\omega_u)^3 + 420(i\omega_u)^2 + 43(i\omega_u) + 1 + 0.80K_{c_u} = 0$$

Entonces se substituye $i^2 = -1$ y se separan la parte real e imaginaria:

$$(-420\omega_u^2 + 1 + 0.80K_{c_u}) + i(-900\omega_u^3 + 43\omega_u) = 0 + i0$$

De esta ecuación compleja se obtienen las dos siguientes, puesto que tanto la parte real como la imaginaria deben ser cero:

$$-420\omega_u^2 + 1 + 0.80K_{c_u} = 0$$
$$-900\omega_u^3 + 43\omega_u = 0$$

Se tienen las siguientes posibilidades de solución para este sistema:

Para $\omega_u = 0$:
$$K_{c_u} = -1.25 \text{ %/%}$$

Para $\omega_u = 0.2186$ rad/s:
$$K_{c_u} = 23.8 \text{ %/%}$$

La primera solución corresponde a la inestabilidad monotónica que causa la acción incorrecta del controlador; en este caso el sistema no oscila, sino que se mueve monotónicamente en una dirección u otra; el cruce con el eje imaginario ocurre en el origen ($s = 0$). La ganancia última que se obtiene para la segunda solución es idéntica a la que se obtiene mediante la prueba de Routh, pero en esta ocasión se obtiene como información adicional que, con esta ganancia, el circuito oscila con una frecuencia de 0.2186 rad/s (0.0348 hertz) o un período de:

$$T_u = \frac{2\pi}{0.2186} = 28.7 \text{ s}$$

A continuación se tabulan los resultados del método de substitución directa para los otros casos que se consideraron antes:

| Caso | $K_{c_u}$ | $\omega_u$ rad/s | $T_u$ s |
|------|----------|------------------|---------|
| 1. Caso básico | 23.8 | 0.2186 | 28.7 |
| 2. $H(s) = 2.0/(10s+1)$ | 11.9 | 0.2186 | 28.7 |
| 3. $H(s) = 1.0/(5s+1)$ | 25.7 | 0.2906 | 21.6 |
| 4. $G_s(s) = 50/(20s+1)$ | 19.9 | 0.2345 | 26.8 |

Se ve que las ganancias últimas son las mismas que se obtienen con la prueba de Routh, sin embargo, en los resultados del método de substitución directa se aprecia que el circuito puede oscilar significativamente más rápido cuando la constante de tiempo del sensor-transmisor se reduce de 10 a 5 s. Estos resultados también indican que el circuito oscila ligeramente más rápido cuando se reduce la constante de tiempo del intercambiador de 30 a 20 s, a pesar de la reducción significativa en la ganancia última. También se puede observar que el cambio de las ganancias de los bloques del circuito no tiene efecto sobre la frecuencia de oscilación.

### Efecto del tiempo muerto

Ya se vio la manera en que la prueba de Routh y la substitución directa permiten estudiar el efecto de los diferentes parámetros del circuito sobre la estabilidad del circuito de control por retroalimentación; desafortunadamente, estos métodos fallan cuando en cualquiera de los bloques del circuito existe un término de tiempo muerto (retraso de transporte o retardo en tiempo), debido a que el tiempo muerto introduce una función exponencial de la variable de la transformada de Laplace en la ecuación característica, lo cual significa que la ecuación ya no es un polinomio y que los métodos que se aprendieron en esta sección ya no se aplican. Un incremento en el tiempo muerto tiende a reducir rápidamente la ganancia última del circuito, este efecto es similar al que resulta de incrementar la constante de tiempo no dominante del circuito, puesto que está en relación con la magnitud de la constante de tiempo dominante. Cuando se estudie el método de la respuesta en frecuencia en el siguiente capítulo, se podrá estudiar el efecto del tiempo muerto sobre la estabilidad del circuito.

Se debe hacer notar que el intercambiador que se utilizó como ejemplo en este capítulo es un sistema de parámetros distribuidos, es decir, la temperatura del fluido que se procesa está distribuida a lo largo del intercambiador. Las funciones de transferencia de tales sistemas generalmente contienen al menos un término de tiempo muerto, el cual se despreció para efectos de simplicidad.

Mediante una aproximación a la función de transferencia de tiempo muerto, se puede obtener una estimación de la ganancia y frecuencia últimas de un circuito con tiempo muerto. Una aproximación usual es la aproximación de Padé de primer orden que se expresa mediante:

$$e^{-t_0s} \approx \frac{1 - \frac{t_0s}{2}}{1 + \frac{t_0s}{2}} \quad (6-29)$$

donde $t_0$ es el tiempo muerto. También existen aproximaciones de orden superior más precisas, pero son muy complejas y no son prácticas. Con el siguiente ejemplo se ilustra la utilización de la aproximación de Padé con el método de substitución directa.

**Ejemplo 6-7. Ganancia y frecuencia últimas de un proceso de primer orden con tiempo muerto.**

La función de transferencia de proceso del circuito en la figura 6-4a se expresa mediante:

$$G(s) = \frac{Ke^{-t_0s}}{\tau s + 1}$$

donde:
- $K$ es la ganancia
- $t_0$ es el tiempo muerto
- $\tau$ es la constante de tiempo

Si el controlador es proporcional, se deben determinar la ganancia y frecuencia últimas del circuito en función de los parámetros del proceso:

$$G_c(s) = K_c$$

**Solución:** Del ejemplo 6-1, se tiene que la ecuación característica del circuito es:

$$1 + G_c(s)G(s) = 0$$

o para las funciones de transferencia consideradas aquí:

$$1 + \frac{K_cKe^{-t_0s}}{\tau s + 1} = 0$$

Al substituir la aproximación de Padé de primer orden, ecuación (6-29), se tiene:

$$1 + \frac{K_cK}{\tau s + 1}\cdot\frac{1 - \frac{t_0s}{2}}{1 + \frac{t_0s}{2}} = 0$$

Se elimina la fracción:

$$(\tau s + 1)\left(1 + \frac{t_0s}{2}\right) + K_cK\left(1 - \frac{t_0s}{2}\right) = 0$$

$$\frac{\tau t_0}{2}s^2 + \left(\tau + \frac{t_0}{2} - \frac{K_cKt_0}{2}\right)s + 1 + K_cK = 0$$

Por el método de substitución directa, $s = i\omega_u$, da:

$$-\frac{\tau t_0}{2}\omega_u^2 + 1 + K_cK + i\left[\left(\tau + \frac{t_0}{2} - \frac{K_cKt_0}{2}\right)\omega_u\right] = 0$$

Después de reordenar, la solución es:

$$(K_cK)_u = 1 + \frac{2\tau}{t_0}$$
$$\omega_u = \frac{2}{t_0}\sqrt{\frac{2\tau}{t_0} + 1}$$

En estas fórmulas se aprecia que la ganancia última del circuito tiende a infinito -sin límite de estabilidad- conforme el tiempo muerto se acerca a cero, lo cual concuerda con el resultado del ejemplo 6-1, sin embargo, cualquier cantidad finita de tiempo muerto impone un límite de estabilidad a la ganancia del circuito. La ganancia última se incrementa cuando el tiempo muerto decrece, y se vuelve muy pequeña conforme se incrementa el tiempo muerto; esto significa que el tiempo muerto hace que la respuesta del circuito sea lenta.

A partir de los resultados del análisis de la substitución directa, del ejemplo precedente se pueden resumir los siguientes efectos generales de los diversos parámetros del circuito:

1. La estabilidad impone un límite a la ganancia total del circuito, de manera que un incremento en la ganancia de la válvula de control, el transmisor o el proceso da como resultado un decremento en la ganancia última del controlador.
2. Un incremento en el tiempo muerto, o en cualquiera de las constantes de tiempo no dominantes (las más pequeñas) del circuito, da como resultado una reducción en la ganancia última del circuito, así como en la frecuencia última.
3. Un incremento en la constante de tiempo dominante (la mayor) del circuito da como resultado un incremento en la ganancia última del circuito y un decremento en la frecuencia última del circuito.

A continuación se aborda la importante tarea del ajuste de los controladores por retroalimentación.

## 6-3. AJUSTE DE LOS CONTROLADORES POR RETROALIMENTACIÓN

El ajuste es el procedimiento mediante el cual se adecúan los parámetros del controlador por retroalimentación para obtener una respuesta específica de circuito cerrado. El ajuste de un circuito de control por retroalimentación es análogo al del motor de un automóvil o de un televisor; en cada caso la dificultad del problema se incrementa con el número de parámetros que se deben ajustar; por ejemplo, el ajuste de un controlador proporcional simple o de uno integral es similar al del volumen de un televisor, ya que sólo se necesita ajustar un parámetro o "perilla"; el procedimiento consiste en moverlo en una dirección u otra, hasta que se obtiene la respuesta (o volumen) que se desea. El siguiente grado de dificultad es ajustar el controlador de dos modos o proporcional-integral (PI), que se asemeja al proceso de ajustar el brillo y el contraste de un televisor en blanco y negro, puesto que se deben ajustar dos parámetros: la ganancia y el tiempo de reajuste; el procedimiento de ajuste es significativamente más complicado que cuando sólo se necesita ajustar un parámetro. Finalmente, el ajuste de los controladores de tres modos o proporcional-integral-derivativo (PID) representa el siguiente grado de dificultad, debido a que se requiere ajustar tres parámetros: la ganancia, el tiempo de reajuste y el tiempo de derivación, lo cual es análogo al ajuste de los haces verde, rojo y azul en un televisor a color.

A pesar de que se planteó la analogía entre el ajuste de un televisor y un circuito de control con retroalimentación, no se trata de dar la impresión de que en ambas tareas existe el mismo grado de dificultad. La diferencia principal estriba en la velocidad de respuesta del televisor contra la del circuito del proceso; en el televisor se tiene una retroalimentación casi inmediata sobre el efecto del ajuste. Por otro lado, a pesar de que en algunos circuitos de proceso se tienen respuestas relativamente rápidas, en la mayoría de los procesos se debe esperar varios minutos, o aun horas, para apreciar la respuesta que resulta del ajuste, lo cual hace que el ajuste de los controladores con retroalimentación sea una tarea tediosa que lleva tiempo; a pesar de ello, éste es el método que más comúnmente utilizan los ingenieros de control e instrumentación en la industria. Para ajustar los controladores a varios criterios de respuesta se han introducido diversos procedimientos y fórmulas de ajuste. En esta sección se estudiarán algunos de ellos, ya que cada uno da una visión acerca del procedimiento de ajuste; sin embargo, se debe tener en mente que ningún procedimiento da mejor resultado que los demás para todas las situaciones de control de proceso.

Los valores de los parámetros de ajuste dependen de la respuesta de circuito cerrado que se desea, así como de las características dinámicas o personalidad de los otros elementos del circuito de control y, particularmente, del proceso. Se vio anteriormente que, si el proceso no es lineal, como generalmente ocurre, estas características cambian de un punto de operación al siguiente, lo cual significa que un conjunto particular de parámetros de ajuste puede producir la respuesta que se desea únicamente en un punto de operación, debido a que los controladores con retroalimentación estándar son dispositivos básicamente lineales. A fin de operar en un rango de condiciones de operación, se debe establecer un arreglo para lograr un conjunto aceptable de parámetros de ajuste, ya que la respuesta puede ser lenta en un extremo del rango, y oscilatoria en el otro. Con lo anterior en mente, a continuación se exponen algunos de los procedimientos propuestos para ajustar los controladores industriales.

### Respuesta de razón de asentamiento de un cuarto mediante el método de ganancia última

Este método, uno de los primeros, que también se conoce como método de circuito cerrado o ajuste en línea, lo propusieron Ziegler y Nichols, en 1942; consta de dos pasos, al igual que todos los otros métodos de ajuste:

**Paso 1.** Determinación de las características dinámicas o personalidad del circuito de control.

**Paso 2.** Estimación de los parámetros de ajuste del controlador con los que se produce la respuesta deseada para las características dinámicas que se determinaron en el primer paso -en otras palabras, hacer coincidir la personalidad del controlador con la de los demás elementos del circuito.

En este método, los parámetros mediante los cuales se representan las características dinámicas del proceso son: la ganancia última de un controlador proporcional, y el período último de oscilación; estos parámetros, que se introdujeron en la sección precedente, se pueden determinar mediante el método de substitución directa, si se conocen cuantitativamente las funciones de transferencia de todos los componentes del circuito, ya que generalmente éste no es el caso. La ganancia y el período últimos se deben determinar frecuentemente de manera experimental, a partir del sistema real, mediante el siguiente procedimiento:

1. Se desconectan las acciones integral y derivativo del controlador por retroalimentación, de manera que se tiene un controlador proporcional. En algunos modelos no es posible desconectar la acción integral, pero se puede desajustar mediante la simple igualación del tiempo de integración al valor máximo -0 de manera equivalente, la tasa de integración al valor mínimo.
2. Con el controlador en automático (esto es, el circuito cerrado), se incrementa la ganancia proporcional (o se reduce la banda proporcional), hasta que el circuito oscila con amplitud constante; se registra el valor de la ganancia con que se produce la oscilación sostenida como $K_{c_u}$, ganancia última. Este paso se debe efectuar con incrementos discretos de la ganancia, alterando el sistema con la aplicación de pequeños cambios en el punto de control a cada cambio en el establecimiento de la ganancia. Los incrementos de la ganancia deben ser menores conforme ésta se aproxime a la ganancia última.
3. Del registro de tiempo de la variable controlada, se registra y mide el período de oscilación como $T_u$, período último, según se muestra en la figura 6-10.

Para la respuesta que se desea del circuito cerrado, Ziegler y Nichols especificaron una razón de asentamiento de un cuarto. La razón de asentamiento (disminución gradual) es la razón de amplitud entre dos oscilaciones sucesivas; debe ser independiente de las entradas al sistema, y depender únicamente de las raíces de la ecuación característica del circuito. En la figura 6-11 se muestran las respuestas típicas de razón de asentamiento de un cuarto para una perturbación y un cambio en el punto de control.

Una vez que se determinan la ganancia última y el período último, se utilizan las fórmulas de la tabla 6-1 para calcular los parámetros de ajuste del controlador con los cuales se producen respuestas de la razón de asentamiento de un cuarto.

```json
{
  "type": "table",
  "id": "table-06-01",
  "page": 268,
  "title": "Tabla 6-1. Fórmulas para ajuste de razón de asentamiento de un cuarto",
  "headers": ["Tipo de controlador", "Ganancia proporcional", "Tiempo de integración", "Tiempo de derivación"],
  "rows": [
    ["P", "Kc = Kcu/2", "-", "-"],
    ["PI", "Kc = Kcu/2.2", "τI = Tu/1.2", "-"],
    ["PID", "Kc = Kcu/1.7", "τI = Tu/2", "τD = Tu/8"]
  ],
  "notes": "Fórmulas de Ziegler-Nichols para ajuste de controladores",
  "source": "Smith & Corripio, Control Automático de Procesos, Tabla 6-1"
}
```

Nótese que, cuando se introduce la acción integral, se fuerza una reducción del 10% en la ganancia del controlador PI, en comparación con la del controlador proporcional. Por otro lado, la acción derivativa propicia un incremento, tanto en la ganancia proporcional como en la tasa de integración (un decremento en el tiempo de integración) del controlador PID, en comparación con las del controlador PI, debido a que la acción integral introduce un retardo en la operación del controlador por retroalimentación, mientras que con la acción derivativa se introduce un avance o adelanto. Esto se trata con más detalle en el capítulo 7.

La respuesta con asentamiento de un cuarto no es deseable para cambios escalón en el punto de control, porque produce un sobrepaso del 50% ($A/A_{punto de control} = 0.5$), debido a que la desviación máxima del nuevo punto de control en cada dirección es un medio de la desviación máxima precedente en la dirección opuesta (ver figura 6-11). Sin embargo, la respuesta de la razón de asentamiento de un cuarto es muy deseable para las perturbaciones, porque se evita una gran desviación inicial del punto de control sin que se tenga demasiada oscilación. La mayor dificultad de la respuesta de razón de asentamiento de un cuarto es que el conjunto de parámetros de ajuste requerido para obtenerla no es único, a excepción del caso del controlador proporcional; en el caso de los controladores PI se puede verificar fácilmente que, para cada valor del tiempo de integración, es posible encontrar un valor de ganancia con el cual se produce una respuesta de razón de asentamiento de un cuarto y viceversa; lo mismo es válido para el controlador PID. Las puestas a punto que proponen Ziegler y Nichols son valores de campo que producen una respuesta rápida en la mayoría de los circuitos industriales.

**Ejemplo 6-8.** A partir de la ecuación característica del tanque de calentamiento con agitación continua que se obtuvo en el ejemplo 6-4, se deben determinar los parámetros de ajuste de razón de asentamiento de un cuarto para el controlador PID, mediante el método de la ganancia última; también se deben calcular las raíces de la ecuación característica cuando el controlador se ajusta con esos parámetros.

**Solución.** En el ejemplo 6-4 se obtuvo la siguiente ecuación característica para el calentador:

$$0.387s^3 + 3.272s^2 + 7.859s + (6.043 + 1.205K_c\tau_D)s + (0.617 + 1.205K_c) = 0$$

Primeramente se utiliza el método de substitución directa para calcular la ganancia y el período de oscilación últimos de un controlador proporcional. Con $\tau_D = 0$ y $\tau_I = 0$, la ecuación característica se reduce a:

$$0.387s^3 + 3.272s^2 + 7.859s + 6.043s + 0.617 + 1.205K_c = 0$$

A continuación se substituye $s = i\omega_u$ y $K_c = K_{c_u}$ para obtener, después de simplificar, el siguiente sistema de ecuaciones:

$$-3.272\omega_u^2 + 6.043\omega_u = 0$$
$$0.387\omega_u^3 - 7.859\omega_u^2 + 0.617 + 1.205K_{c_u} = 0$$

A partir de éste, se pueden obtener la frecuencia y ganancia últimas:

$$\omega_u = \sqrt{\frac{6.043}{3.272}} = 1.359 \text{ rad/min}$$
$$K_{c_u} = \frac{1}{1.205}(-0.387\omega_u^3 + 7.859\omega_u - 0.617) = 10.44 \text{ %/%}$$

El período último es $T_u = \frac{2\pi}{1.359} = 4.62$ min. De acuerdo con la tabla 6-1, los parámetros de ajuste para la respuesta a un cuarto de la razón de asentamiento para un controlador PID son:

$$K_c = K_{c_u}/1.1 = 6.14 \text{ %/%}$$
$$\tau_I = T_u/2 = 2.31 \text{ min}$$
$$\tau_D = T_u/8 = 0.58 \text{ min}$$

Con estos parámetros de ajuste la ecuación característica es:

$$0.387s^3 + 3.272s^2 + 7.858s^2 + 10.34s + 8.017s + 3.20 = 0$$

Con el programa del apéndice D, se encuentra que las raíces de esta ecuación característica son:

- $-0.42 \pm i0.99$
- $-1.03 \pm i0.49$
- $-5.55$

La respuesta de escalón unitario del circuito cerrado tiene la siguiente forma:

$$T(t) = b_0u(t) + b_1e^{-0.42t}\sin(0.99t + \theta_1) + b_2e^{-1.03t}\sin(0.49t + \theta_2) + b_3e^{-5.55t}$$

donde los parámetros $b_0, b_1, \theta_1, b_2, \theta_2$ y $b_3$ se deben evaluar mediante la expansión de fracciones parciales para la entrada particular (punto de régimen, flujo de entrada o temperatura de entrada) considerada. La técnica de expansión de fracciones parciales se abordó en el capítulo 2.

### Caracterización del proceso

El método de Ziegler-Nichols para ajuste en línea que se acaba de presentar es el único con que se caracteriza al proceso mediante la ganancia y período últimos. Con la mayoría de los demás métodos para ajuste del controlador, se caracteriza al proceso mediante un modelo simple de primer o segundo orden con tiempo muerto. Para una mejor comprensión de las suposiciones que entran en tal caracterización, considérese el diagrama de bloques de un circuito de control por retroalimentación que se muestra en la figura 6-12a; los símbolos que aparecen en el diagrama son:

- $R(s)$ = transformada de Laplace de la señal del punto de control
- $M(s)$ = transformada de Laplace de la señal de salida del controlador
- $C(s)$ = transformada de Laplace de la señal de salida del transmisor
- $E(s)$ = transformada de Laplace de la señal de error
- $L(s)$ = transformada de Laplace de la señal de perturbación
- $G_c(s)$ = función de transferencia del controlador
- $G_v(s)$ = función de transferencia de la válvula de control (o elemento final de control)
- $G_p(s)$ = función de transferencia del proceso entre la variable controlada y la variable manipulada
- $G_L(s)$ = función de transferencia del proceso entre la variable controlada y el disturbio
- $H(s)$ = función de transferencia del sensor-transmisor

Para dibujar el diagrama equivalente de bloques que se muestra en la figura 6-12b, se utiliza el álgebra simple de diagramas de bloques que se expuso en el capítulo 3; en este diagrama sólo hay dos bloques en el circuito de control, uno para el controlador y otro para el resto de los componentes del circuito. La ventaja de esta representación simplificada estriba en que se destacan las dos señales del circuito que generalmente se observan y registran: la salida del controlador $M(s)$ y la señal del transmisor $C(s)$. En la mayoría de los circuitos no se puede observar alguna señal o variable, a excepción de esas dos; por lo tanto, la concentración de las funciones de transferencia de la válvula de control, del proceso y del sensor-transmisor, no se hace sólo por conveniencia, sino por razones prácticas; si a esta combinación de funciones de transferencia se le designa como $G(s)$:

$$G(s) = G_v(s)G_p(s)H(s)$$

Es precisamente esta función de transferencia combinada la que se aproxima mediante los modelos de orden inferior con el objeto de caracterizar la respuesta dinámica del proceso. Lo importante es que en el "proceso" caracterizado se incluye el comportamiento dinámico de la válvula de control y del sensor-transmisor. Los modelos que comúnmente se utilizan para caracterizar al proceso son los siguientes:

**Modelo de primer orden más tiempo muerto (POMTM):**

$$G(s) = \frac{Ke^{-t_0s}}{\tau s + 1} \quad (6-31)$$

**Modelo de segundo orden más tiempo muerto (SOMTM):**

$$G(s) = \frac{Ke^{-t_0s}}{(\tau_1s + 1)(\tau_2s + 1)} \quad (6-32)$$

$$G(s) = \frac{Ke^{-t_0s}}{\tau^2s^2 + 2\xi\tau s + 1} \quad (6-33)$$

para procesos subamortiguados ($\xi < 1$), donde:
- $K$ = ganancia del proceso en estado estacionario
- $t_0$ = tiempo muerto efectivo del proceso
- $\tau, \tau_1, \tau_2$ = constantes de tiempo efectivas del proceso
- $\xi$ = razón de amortiguamiento efectiva del proceso

De éstos, el modelo POMTM es en el que se basan la mayoría de las fórmulas de ajuste de controladores. En este modelo el proceso se caracteriza mediante tres parámetros: la ganancia $K$, el tiempo muerto $t_0$ y la constante de tiempo $\tau$. De modo que el problema consiste en la manera en que se pueden determinar dichos parámetros para un circuito particular; la solución consiste en realizar algunas pruebas dinámicas en el sistema real o la simulación del circuito en una computadora; la prueba más simple que se puede realizar es la de escalón.

### Prueba del proceso de escalón

El procedimiento de la prueba de escalón se lleva a cabo como sigue:

1. Con el controlador en la posición "manual" (es decir, el circuito abierto), se aplica al proceso un cambio escalón en la señal de salida del controlador $m(t)$. La magnitud del cambio debe ser lo suficientemente grande como para que se pueda medir el cambio consecuente en la señal de salida del transmisor, pero no tanto como para que las no linealidades del proceso ocasionen la distorsión de la respuesta.
2. La respuesta de la señal de salida del transmisor $c(t)$ se registra con un graficador de papel continuo o algún dispositivo equivalente; se debe tener la seguridad de que la resolución es la adecuada, tanto en la escala de amplitud como en la de tiempo. La graficación de $c(t)$ contra el tiempo debe cubrir el período completo de la prueba, desde la introducción de la prueba de escalón hasta que el sistema alcanza un nuevo estado estacionario. La prueba generalmente dura entre unos cuantos minutos y varias horas, según la velocidad de respuesta del proceso.

Naturalmente, es imperativo que no entren perturbaciones al sistema mientras se realiza la prueba de escalón. En la figura 6-13 se muestra una gráfica típica de la prueba, la cual se conoce también como curva de reacción del proceso; como se vio en el capítulo 4, la respuesta en forma de S es característica de los procesos de segundo orden o superior, con o sin tiempo muerto. El siguiente paso es hacer coincidir la curva de reacción del proceso con el modelo de un proceso simple para determinar los parámetros del modelo; a continuación se hace esto para un modelo de primer orden más tiempo muerto (POMTM).

En ausencia de perturbaciones y para las condiciones de la prueba, el diagrama de bloques de la figura 6-12b se puede redibujar de la manera en que aparece en la figura 6-14. La respuesta de la señal de salida del transmisor se expresa mediante:

$$C(s) = G(s)M(s)$$

Para un cambio escalón de magnitud $\Delta m$ en la salida del controlador y un modelo POMTM, ecuación (6-31), se tiene:

$$C(s) = \frac{Ke^{-t_0s}}{\tau s + 1}\cdot\frac{\Delta m}{s}$$

Al expandir esta expresión en fracciones parciales, se obtiene:

$$C(s) = K\Delta m\left[\frac{1}{s} - \frac{\tau}{\tau s + 1}\right]e^{-t_0s} \quad (6-35)$$

Se invierte, con ayuda de la tabla de transformada de Laplace (tabla 2-1), y se aplica el teorema de la traslación real (ver capítulo 2) para obtener:

$$\Delta c = K\Delta m\, u(t - t_0)[1 - e^{-(t-t_0)/\tau}] \quad (6-36)$$

se incluye la función escalón unitario $u(t - t_0)$, para indicar explícitamente que $\Delta c = 0$ para $t \leq t_0$.

El término $\Delta c$ es la perturbación o cambio de salida del transmisor respecto a su valor inicial:

$$\Delta c = c(t) - c(0) \quad (6-37)$$

En la figura 6-15 se muestra una gráfica de la ecuación (6-36), en ésta el término $\Delta c_{\infty}$ es el cambio en estado estacionario de $c(t)$. De la ecuación (6-36) se tiene que:

$$\Delta c_{\infty} = \lim_{t \to \infty}\Delta c = K\Delta m \quad (6-38)$$

A partir de esta ecuación, y si se tiene en cuenta que la respuesta del modelo debe coincidir con la curva de reacción del proceso en estado estable, se puede calcular la ganancia de estado estacionario del proceso, la cual es uno de los parámetros del modelo:

$$K = \frac{\Delta c_{\infty}}{\Delta m} \quad (6-39)$$

Este resultado también se obtuvo en el capítulo 3.

El tiempo muerto $t_0$ y la constante de tiempo $\tau$ se pueden determinar al menos mediante tres métodos, cada uno de los cuales da diferentes valores.

**Método 1.** En este método se utiliza la línea tangente a la curva de reacción del proceso, en el punto de razón máxima de cambio; para el modelo POMTM esto ocurre en $t = t_0$, como resulta evidente al observar la respuesta del modelo en la figura 6-15. De la ecuación (6-36) se encuentra que esta razón inicial (máxima) de cambio es:

$$\frac{d(\Delta c)}{dt}\bigg|_{t=t_0} = \frac{K\Delta m}{\tau} \quad (6-40)$$

En la figura 6-15 se aprecia que tal resultado indica que la línea de razón máxima de cambio interseca la línea de valor inicial en $t = t_0$, y a la línea de valor final en $t = t_0 + \tau$. De este descubrimiento se deduce el trazo para determinar $t_0$ y $\tau$ que se ilustra en la figura 6-16a; la línea se traza tangente a la curva de reacción del proceso real, en el punto de reacción máxima de cambio. La respuesta del modelo en que se emplean los valores de $t_0$ y $\tau$ se ilustra con la línea punteada en la figura. Evidentemente, la respuesta del modelo que se obtiene con este método no coincide muy bien con la respuesta real.

**Método 2.** En este método $t_0$ se determina de la misma manera que en el método 1, pero con el valor de $\tau$ se fuerza a que la respuesta del modelo coincida con la respuesta real en $t = t_0 + \tau$. De acuerdo con la ecuación (6-36) este punto es:

$$\Delta c(t_0 + \tau) = K\Delta m[1 - e^{-1}] = 0.632\Delta c_{\infty} \quad (6-41)$$

Se observa que la comparación entre la respuesta del modelo y la real es mucho más cercana que con el método 1, figura 6-16b. El valor de la constante de tiempo que se obtiene con el método 2 es generalmente menor al que se obtiene con el método 1.

**Método 3.** Al determinar $t_0$ y $\tau$ con los dos métodos anteriores, el paso de menor precisión es el trazo de la tangente en el punto de razón máxima de cambio de la curva de reacción del proceso. Aun en el método 2, donde el valor de $(t_0 + \tau)$ es independiente de la tangente, los valores que se estiman para $t_0$ y $\tau$ dependen de la línea. Para eliminar esa dependencia, el doctor Cecil L. Smith propone que los valores de $t_0$ y $\tau$ se seleccionen de tal manera que la respuesta del modelo y la real coincidan en la región de alta tasa de cambio. Los dos puntos que se recomiendan son $(t_0 + \frac{1}{3}\tau)$ y $(t_0 + \tau)$, y para localizar dichos puntos se utiliza la ecuación (6-36):

$$\Delta c\left(t_0 + \frac{1}{3}\tau\right) = K\Delta m[1 - e^{-1/3}] = 0.283\Delta c_{\infty}$$
$$\Delta c(t_0 + \tau) = K\Delta m[1 - e^{-1}] = 0.632\Delta c_{\infty} \quad (6-42)$$

Estos dos puntos, en la figura 6-16c, se denominan $t_1$ y $t_2$, respectivamente. Los valores de $t_0$ y $\tau$ se pueden obtener fácilmente mediante la simple resolución del siguiente sistema de ecuaciones:

$$t_0 + \tau = t_2$$
$$t_0 + \frac{1}{3}\tau = t_1$$

Lo cual se reduce a:

$$\tau = \frac{3}{2}(t_2 - t_1) \quad (6-44)$$
$$t_0 = t_2 - \tau$$

donde:
- $t_1$ = tiempo en el cual $\Delta c = 0.283\Delta c_{\infty}$
- $t_2$ = tiempo en el cual $\Delta c = 0.632\Delta c_{\infty}$

Con la experiencia se demostró que los resultados obtenidos con este método son más fáciles de reproducir que los que se obtienen mediante los otros dos y, por lo tanto, se recomienda este método para hacer la estimación de $t_0$ y $\tau$ a partir de la curva de reacción del proceso. Sin embargo, se debe tener en cuenta que algunas correlaciones para los parámetros de ajuste del controlador se basan en diferentes ajustes de modelos POMTM.

En la bibliografía sobre el tema se proponen varios métodos para estimar los parámetros de un modelo de segundo orden más tiempo muerto (SOMTM) para la curva de reacción del proceso, pero por experiencia se sabe que tales métodos son poco precisos, debido a que la prueba con escalón no proporciona suficiente información para obtener el parámetro adicional -constante de tiempo o razón de amortiguamiento- que se requiere para el SOMTM. En otras palabras, la mayor complejidad del modelo requiere una prueba dinámica más elaborada. La prueba con pulsos es un método adecuado para obtener los parámetros de modelos de segundo orden y superiores. Esta prueba se presenta en la sección 7.3.

Puesto que las fórmulas de ajuste del controlador que se presentan a continuación se basan en parámetros de modelos POMTM, se pueden encontrar algunas situaciones donde existen parámetros de un modelo de orden superior y se necesita estimar el equivalente a modelos de primer orden; a pesar de que no existe un procedimiento general para hacer esto, con la siguiente regla práctica se puede obtener una estimación somera para una primera aproximación:

> Si una de las constantes de tiempo del modelo de orden superior es mucho más grande que las otras, es posible estimar que la constante de tiempo efectiva del modelo de primer orden es igual a la constante de tiempo mayor. Entonces, se puede aproximar el tiempo muerto efectivo del modelo de primer orden mediante la suma de todas las constantes de tiempo menores más el tiempo muerto del modelo de orden superior.

**Ejemplo 6-9.** Se deben estimar los parámetros POMTM para el circuito de control de temperatura del intercambiador del ejemplo 6-5. La función de transferencia combinada para la válvula de control, el intercambiador y el sensor-transmisor de este ejemplo se expresa mediante:

$$G(s) = \frac{50}{(30s + 1)(3s + 1)(10s + 1)}\cdot0.016$$

**Solución.** Si se supone que la constante de tiempo de 30 s es mucho mayor que las otras dos, se puede aproximar en más o menos:

$$\tau = 30 \text{ s}$$
$$t_0 = 10 + 3 = 13 \text{ s}$$

naturalmente, la ganancia es la misma; es decir, $K = 0.80$. La función de transferencia del modelo POMTM que resulta es, entonces:

$$G(s) = \frac{0.80e^{-13s}}{30s + 1} \text{ (Modelo A)}$$

Ahora se compara esta aproximación con los parámetros POMTM que se determinan experimentalmente a partir de la curva de reacción del proceso. En la figura 6-17 se ilustra la curva de reacción del proceso para los tres retardos de primer orden en serie, los cuales se supone representan el intercambiador de calor, la válvula de control y el sensor-transmisor. La respuesta de la figura 6-17 se obtiene mediante la simulación de los tres retardos de primer orden en una microcomputadora analógica; se aplicó un cambio escalón de 5% a la señal de salida del controlador y se registró la salida del sensor transmisor contra el tiempo; a partir de este resultado es posible calcular los parámetros POMTM, para lo cual se utilizan los tres métodos presentados anteriormente.

**Método 1:**
$$t_0 = 1.2 \text{ s}$$
$$t_3 = 61.5 \text{ s}$$
$$\tau = 61.5 - 1.2 = 54.3 \text{ s}$$
$$G(s) = \frac{0.80e^{-7.2s}}{54.3s + 1} \text{ (modelo B)}$$

**Método 2:**
$$t_0 = 7.2 \text{ s}$$
$$\Delta c = 0.632(4\Delta c) = 2.53 \text{ °C}$$
$$t_2 = 45.0 \text{ s}$$
$$\tau = 45.0 - 7.2 = 37.8 \text{ s}$$
$$G(s) = \frac{0.80e^{-7.2s}}{37.8s + 1} \text{ (modelo C)}$$

**Método 3:**
$$\Delta c = 0.283(4\Delta c) = 1.13 \text{ °C}$$
$$t_1 = 22.5 \text{ s}$$
$$\tau = \frac{3}{2}(t_2 - t_1) = \frac{3}{2}(45.0 - 22.5) = 33.8 \text{ s}$$
$$t_0 = 45.0 - 33.8 = 11.2 \text{ s}$$
$$G(s) = \frac{0.80e^{-11.2s}}{33.8s + 1} \text{ (modelo D)}$$

Como se verá en las secciones siguientes, en términos de ajuste, un parámetro importante es la relación del tiempo muerto con la constante de tiempo. Los valores para los cuatro modelos de aproximación POMTM son los siguientes:

| Modelo | $t_0$, s | $\tau$, s | $t_0/\tau$ |
|--------|----------|-----------|------------|
| A (aproximado) | 13.0 | 30.0 | 0.433 |
| B (método 1) | 7.2 | 54.3 | 0.133 |
| C (método 2) | 7.2 | 37.8 | 0.190 |
| D (método 3) | 11.2 | 33.8 | 0.331 |

Se supone que la razón $t_0/\tau$ es el parámetro más sensible, y que varía con un factor ligeramente superior a 3:1. A pesar de que con los métodos 2 y 3 se obtienen las aproximaciones más cercanas a la respuesta escalón real, se debe tener en cuenta que algunas correlaciones de ajuste se basan en métodos específicos.

**Ejemplo 6-10.** Para el siguiente proceso de segundo orden:

$$G(s) = \frac{C(s)}{M(s)} = \frac{K}{(\tau_1s + 1)(\tau_2s + 1)}$$

se deben determinar los parámetros de un modelo de primer orden más tiempo muerto (POMTM); se debe utilizar el método tres en función de la relación $\tau_2/\tau_1$.

**Solución:** Primeramente se obtiene la respuesta escalón unitario para el proceso real:

$$M(s) = \frac{1}{s}$$

$$C(s) = \frac{K}{(\tau_1s + 1)(\tau_2s + 1)s}$$

Por expansión de fracciones parciales, para el caso $\tau_1 > \tau_2$:

$$C(s) = K\left[\frac{1}{s} - \frac{\tau_1}{\tau_1 - \tau_2}\cdot\frac{1}{s + 1/\tau_1} + \frac{\tau_2}{\tau_1 - \tau_2}\cdot\frac{1}{s + 1/\tau_2}\right]$$

Se invierte, con ayuda de una tabla de transformada de Laplace (tabla 2-1), para obtener:

$$C(t) = K\left[1 - \frac{\tau_1}{\tau_1 - \tau_2}e^{-t/\tau_1} + \frac{\tau_2}{\tau_1 - \tau_2}e^{-t/\tau_2}\right]$$

Como:

$$t \to \infty$$
$$C \to K$$

y puesto que:

$$\Delta m = 1$$

Para el método 3, en $t_1 = t_0 + \tau/3$:

$$\frac{\Delta c}{K} = 0.283$$

y en $t_2 = t_0 + \tau$:

$$\frac{\Delta c}{K} = 0.632$$

Para el caso en que $\tau_1 = \tau_2$, mediante expansión de fracciones parciales:

$$C(s) = \frac{K}{(\tau_1s + 1)^2s} = \frac{K}{s} - \frac{K\tau_1}{\tau_1s + 1} - \frac{K\tau_1}{(\tau_1s + 1)^2}$$

Se invierte, con ayuda de una tabla de transformadas de Laplace (tabla 2-1), para obtener:

$$C(t) = K\left[1 - \left(1 + \frac{t}{\tau_1}\right)e^{-t/\tau_1}\right]$$

de lo que resulta:

$$\frac{\Delta c}{K} = 0.283 \quad \Rightarrow \quad \left(1 + \frac{t_1}{\tau_1}\right)e^{-t_1/\tau_1} = 0.717$$
$$\frac{\Delta c}{K} = 0.632 \quad \Rightarrow \quad \left(1 + \frac{t_2}{\tau_1}\right)e^{-t_2/\tau_1} = 0.368$$

A partir de las ecuaciones (A) y (B) o (C) y (D), se debe resolver, por ensayo y error, para $t_1$ y $t_2$. Entonces, de la ecuación (6-44):

$$\tau = \frac{3}{2}(t_2 - t_1)$$
$$t_0 = t_2 - \tau$$

Para resolver este problema, Martin utilizó un programa de computadora; los resultados se grafican en la figura 6-18. Como se puede ver en esta figura, el máximo tiempo muerto efectivo tiene lugar cuando las dos constantes de tiempo son iguales:

Para $\tau_1 = \tau_2$:
$$t_0 = 0.505\tau_1$$
$$\tau = 1.641\tau_1$$

Para $\tau_2 \ll \tau_1$:
$$t_0 \to \tau_2$$
$$\tau \to \tau_1$$

Ésta es la base de la regla práctica que se presentó anteriormente. Se puede utilizar la figura 6-18 para mejorar esta regla práctica, y así aplicarla a sistemas que se representan con tres o más retardos de primer orden en serie; por ejemplo, para el intercambiador de calor del ejemplo se puede perfeccionar el modelo de aproximación como sigue:

Se supone:
$$\tau_1 = 30 \text{ s}$$
$$\tau_2 = 10 + 3 = 13 \text{ s}$$

Entonces:
$$\frac{\tau_2}{\tau_1} = \frac{13}{30} = 0.433$$

De la figura 6-18:
$$t_0 = 0.33\tau_1 = 9.9 \text{ s}$$
$$\tau = 1.2\tau_1 = 36 \text{ s}$$

Estos valores son más cercanos a los que se obtienen con el método 3, en el ejemplo 6-9, en comparación con los que se obtuvieron mediante la aproximación (modelo A), debido a que $\tau_2$ no es mucho más pequeña que $\tau_1$.

### Respuesta de razón de asentamiento de un cuarto

Además de sus fórmulas para ajuste en línea, Ziegler y Nichols proponen un conjunto de fórmulas que se basan en los parámetros de ajuste, para un modelo de primer orden, a la curva de reacción del proceso; dichas fórmulas se muestran en la tabla 6-2. A pesar de que los parámetros que utilizaron no son precisamente la ganancia, la constante de tiempo y el tiempo muerto, sus fórmulas se pueden modificar para expresarlas en términos de esos parámetros. Ziegler y Nichols utilizaron el método 1 para determinar los parámetros del modelo.

```json
{
  "type": "table",
  "id": "table-06-02",
  "page": 283,
  "title": "Tabla 6-2. Fórmulas para ajuste para respuesta de razón de asentamiento de un cuarto",
  "headers": ["Tipo de controlador", "Ganancia proporcional", "Tiempo de integración", "Tiempo de derivación"],
  "rows": [
    ["P", "Kc = 3.33τ/(Kt₀)", "-", "-"],
    ["PI", "Kc = 2.0τ/(Kt₀)", "τI = 2t₀", "-"],
    ["PID", "Kc = 1.2τ/(Kt₀)", "τI = 2t₀", "τD = 0.5t₀"]
  ],
  "notes": "Fórmulas de Ziegler-Nichols basadas en la curva de reacción del proceso",
  "source": "Smith & Corripio, Control Automático de Procesos, Tabla 6-2"
}
```

Como se puede ver en la tabla 6-2, las magnitudes relativas de la ganancia, el tiempo de integración y el de derivación en los controladores P, PI y PID, son las mismas que las de las fórmulas de ajuste en línea, las cuales se basan en el período y ganancia últimos (tabla 6-1). En las fórmulas se observa que la ganancia del circuito, $K_cK$, es inversamente proporcional a la razón del tiempo muerto efectivo a la constante de tiempo efectiva.

Para utilizar estas fórmulas se debe tener en cuenta que son empíricas y sólo se aplican a un rango limitado de razones de tiempo muerto contra constante de tiempo, lo cual significa que no se debe extrapolar fuera de un rango de $t_0/\tau$ entre 0.10 y 1.0.

Como se señaló al estudiar el ajuste en línea, la dificultad para especificar el desempeño de los controladores PI y PID con una razón de asentamiento de un cuarto, estriba en que existe un número infinito de conjuntos de valores de los parámetros del controlador que pueden producir ese desempeño. Las fórmulas que se dan son justamente uno de tales conjuntos.

**Ejemplo 6-11.** Se deben comparar los valores de los parámetros de ajuste para controlar la temperatura del intercambiador del ejemplo 6-5, mediante la utilización del ajuste en línea para una razón de asentamiento de un cuarto y los parámetros POMTM que se estimaron en el ejemplo 6-8. En los ejemplos anteriores se encontraron los siguientes resultados para el circuito de control de temperatura del intercambiador:

Por el método de substitución directa (ver ejemplo 6-6):
$$K_{c_u} = 23.8 \text{ %/%}$$
$$T_u = 28.7 \text{ s}$$

Por aproximación con el método 1 (ver ejemplo 6-9):
$$K = 0.80 \text{ °C/%}$$
$$t_0 = 7.2 \text{ s}$$
$$\tau = 54.3 \text{ s}$$

**Solución.** Los parámetros de ajuste para una razón de asentamiento de un cuarto son los siguientes:

**Ajuste en línea (tabla 6-1):**

Proporcional:
$$K_c = \frac{1}{2}(23.8) = 11.9 \text{ %/%}$$

Proporcional-integral:
$$K_c = \frac{23.8}{2.2} = 10.8 \text{ %/%}$$
$$\tau_I = \frac{28.7}{1.2} = 23.9 \text{ s (0.40 min)}$$

Proporcional-integral-derivativo:
$$K_c = \frac{23.8}{1.7} = 14 \text{ %/%}$$
$$\tau_I = \frac{28.7}{2} = 14.3 \text{ s (0.24 min)}$$
$$\tau_D = \frac{28.7}{8} = 3.6 \text{ s (0.06 min)}$$

**Curva de reacción del proceso (tabla 6-2):**

Proporcional:
$$K_c = \frac{3.33(54.3)}{0.80(7.2)} = 31.4 \text{ %/%}$$

Proporcional-integral:
$$K_c = \frac{2.0(54.3)}{0.80(7.2)} = 18.9 \text{ %/%}$$
$$\tau_I = 2.0(7.2) = 14.4 \text{ s (0.24 min)}$$

Proporcional-integral-derivativo:
$$K_c = \frac{1.2(54.3)}{0.80(7.2)} = 11.3 \text{ %/%}$$
$$\tau_I = 2.0(7.2) = 14.4 \text{ s (0.24 min)}$$
$$\tau_D = 0.5(7.2) = 3.6 \text{ s (0.06 min)}$$

La concordancia es evidente, sin embargo, cabe aclarar que esta concordancia depende de la utilización de los parámetros del método 1, los cuales fueron utilizados por Ziegler y Nichols.

### Ajuste mediante los criterios de error de integración mínimo

Puesto que los parámetros de ajuste de la razón de asentamiento de un cuarto no son únicos, en la Universidad del Estado de Louisiana se realizó un proyecto substancial de investigación bajo la dirección de los profesores Paul W. Murrill y Cecil L. Smith, para desarrollar relaciones de ajuste únicas. A fin de caracterizar el proceso se utilizaron parámetros de modelos de primer orden más tiempo muerto (POMTM), la especificación de la respuesta en circuito cerrado es un error o desviación mínima de la variable controlada, respecto al punto de control. Debido a que el error está en función del tiempo que dura la respuesta, la suma del error en cada instante se debe minimizar; dicha suma es, por definición, la integral del error en tiempo y se representa mediante el área sombreada en la figura 6-19. Puesto que la integral del error se trata de minimizar mediante la utilización de las relaciones de ajuste, éstas se conocen como **ajuste del error de integración mínimo**; sin embargo, la integral de error no se puede minimizar de manera directa, ya que un error negativo muy grande se volvería mínimo. Para evitar los valores negativos en la función de desempeño, se propone el siguiente planteamiento de la integral:

**Integral del valor absoluto del error (IAE):**
$$IAE = \int_0^\infty |e(t)|dt \quad (6-45)$$

**Integral del cuadrado del error (ICE):**
$$ICE = \int_0^\infty e^2(t)dt \quad (6-46)$$

Las integrales se extienden desde el momento en que ocurre la perturbación o cambio en el punto de control ($t = 0$), hasta un tiempo posterior muy largo ($t = \infty$), debido a que no se puede fijar de antemano la duración de las respuestas. El único problema con esta definición de la integral, es que se vuelve indeterminada cuando no se fuerza el error a cero, lo cual ocurre únicamente cuando no hay acción de integración en el controlador, debido a la desviación o el error de estado estacionario; en este caso, en la definición se reemplaza el error por la diferencia entre la variable controlada y su valor final de estado estacionario.

La diferencia entre el criterio IAE y el ICE, consiste en que con el ICE se tiene más ponderación para errores grandes, los cuales se presentan generalmente al inicio de la respuesta, y menor ponderación para errores pequeños, los cuales ocurren hacia el final de la respuesta. Para tratar de reducir el error inicial, el criterio de ICE mínima da por resultado una alta ganancia del controlador y respuestas muy oscilatorias (es decir, una razón de asentamiento alta), en las cuales el error oscila alrededor del cero por un tiempo relativamente largo. De este fenómeno se deduce que en tal criterio de desempeño debe existir una compensación para el tiempo que transcurre desde el inicio de la respuesta. En las siguientes integrales de error se incluye dicha compensación mediante la ponderación del tiempo transcurrido.

**Integral del valor absoluto del error ponderado en tiempo (IAET):**
$$IAET = \int_0^\infty t|e(t)|dt \quad (6-47)$$

**Integral del cuadrado del error ponderado en tiempo (ICET):**
$$ICET = \int_0^\infty te^2(t)dt \quad (6-48)$$

Las ecuaciones (6-45) a (6-48) constituyen las cuatro integrales básicas de error que se pueden minimizar para un circuito particular, mediante el ajuste de los parámetros del controlador. Desafortunadamente, el conjunto óptimo de valores paramétricos no está únicamente en función de cuál de las cuatro definiciones de integral se elige, sino que también depende del tipo de entrada, esto es, perturbación o punto de control y de su forma; por ejemplo, cambio escalón, rampa, etc. Respecto a la forma de la entrada, generalmente se elige el cambio escalón, porque es el más molesto de los que se presentan en la práctica; por lo que toca al tipo de entrada, para el ajuste se selecciona el punto de control o perturbación, en función de cuál se espera que afecte al circuito con más frecuencia. Cuando el punto de control, como entrada, es lo más importante, el propósito del controlador es hacer que la variable controlada siga la señal del punto de control y a dicho controlador se le conoce como "servorregulador". Cuando el objeto del controlador es mantener a la variable controlada en un punto de control constante, en presencia de las entradas de perturbaciones, se dice que el controlador es un "regulador". En términos de la integral mínima de error, los parámetros de ajuste óptimos son diferentes para cada caso. La mayoría de los controladores de proceso se consideran como reguladores, a excepción de los controladores esclavos en las estructuras de control en cascada, los cuales son servorreguladores; el control en cascada se estudiará en la sección 8-3.

Cuando se ajusta el controlador para la respuesta óptima a una entrada de perturbación, se debe hacer una decisión adicional respecto a la función de transferencia del proceso para esa perturbación en particular. Esto es complicado, debido a que la respuesta del controlador no puede ser óptima para cada perturbación, si es que existe más de una perturbación que entre en el circuito. Puesto que la función de transferencia del proceso es diferente para cada perturbación y la señal de salida del controlador, los parámetros óptimos de ajuste dependen de la velocidad relativa de respuesta de la variable controlada a la perturbación; mientras más lenta sea la respuesta a la perturbación, con más rigor se puede ajustar el controlador y su ganancia puede ser más alta; en el otro extremo, si la variable controlada responde instantáneamente a la perturbación, el ajuste del controlador será lo menos riguroso posible, lo cual equivale al ajuste para cambios en el punto de control. Lo anterior es evidente cuando se examina el diagrama de bloques para el caso en que la respuesta a la entrada de la perturbación es instantánea. Lo anterior se muestra en la figura 6-20a; como se puede ver, la perturbación entra en el mismo punto del circuito que el punto de control, lo cual hace que las respuestas a cambios escalón en la perturbación y en el punto de control sean idénticas, excepto por el signo; esto se ilustra en la figura 6-20b.

López y asociados desarrollaron fórmulas de ajuste para el criterio de integral mínima de error con base en la suposición de que la función de transferencia del proceso para las entradas de perturbaciones es idéntica a la función de transferencia para la señal de salida del controlador. En la figura 6-21 se muestra el diagrama de bloques del circuito para este caso, y en la tabla 6-3 se dan las fórmulas de ajuste.

En estas fórmulas se aprecia la misma tendencia que en las de razón de asentamiento de un cuarto, con la excepción de que el tiempo de integración depende, hasta cierto punto, de la constante de tiempo efectiva del proceso, y menos del tiempo muerto del proceso. Se debe tener en mente que estas fórmulas son empíricas y no se deben hacer extrapolaciones más allá de un rango de $(t_0/\tau)$ entre 0.1 y 1.0. (Dicho rango de valores es el que utilizó López en sus correlaciones.)

```json
{
  "type": "table",
  "id": "table-06-03",
  "page": 289,
  "title": "Tabla 6-3. Fórmulas de ajuste de integral mínima de error para entrada de perturbaciones",
  "headers": ["Controlador", "Integral de error", "Fórmula de Kc", "Fórmula de τI", "Fórmula de τD"],
  "rows": [
    ["P", "ICE", "Kc = (1.411/K)(t₀/τ)^(-0.917)", "-", "-"],
    ["P", "IAE", "Kc = (0.902/K)(t₀/τ)^(-0.986)", "-", "-"],
    ["P", "IAET", "Kc = (0.984/K)(t₀/τ)^(-1.084)", "-", "-"],
    ["PI", "ICE", "Kc = (1.305/K)(t₀/τ)^(-0.959)", "τI = (0.492τ)(t₀/τ)^(0.739)", "-"],
    ["PI", "IAE", "Kc = (0.984/K)(t₀/τ)^(-0.986)", "τI = (1.02τ)(t₀/τ)^(-0.323)", "-"],
    ["PI", "IAET", "Kc = (0.859/K)(t₀/τ)^(-0.977)", "τI = (1.03τ)(t₀/τ)^(-0.165)", "-"],
    ["PID", "ICE", "Kc = (1.495/K)(t₀/τ)^(-0.945)", "τI = (0.832τ)(t₀/τ)^(0.771)", "τD = (0.560τ)(t₀/τ)^(1.006)"],
    ["PID", "IAE", "Kc = (1.435/K)(t₀/τ)^(-0.921)", "τI = (1.101τ)(t₀/τ)^(0.749)", "τD = (0.482τ)(t₀/τ)^(1.137)"],
    ["PID", "IAET", "Kc = (1.357/K)(t₀/τ)^(-0.947)", "τI = (0.878τ)(t₀/τ)^(0.738)", "τD = (0.381τ)(t₀/τ)^(0.995)"]
  ],
  "notes": "Fórmulas de López et al. para ajuste de controladores con criterio de integral mínima de error",
  "source": "Smith & Corripio, Control Automático de Procesos, Tabla 6-3"
}
```

Como en el caso de las fórmulas de ajuste para la razón de asentamiento de un cuarto, con estas fórmulas se predice que, tanto la acción proporcional como la de integración, tienden a infinito conforme el proceso se acerca a un proceso de primer orden sin tiempo muerto y este comportamiento es típico de las fórmulas de ajuste para entrada de disturbios.

Rovira y asociados desarrollaron las fórmulas de ajuste para cambios del punto de control de la tabla 6-4; ellos consideraron que el criterio de ICE mínima era inaceptable por su naturaleza altamente oscilatoria; también omitieron las relaciones para los controladores proporcionales, con base en la suposición de que el criterio de integral mínima de error no es apropiado para las aplicaciones donde se recomienda el uso de un controlador proporcional; por ejemplo, obtener el flujo promedio mediante el control proporcional de nivel. Estas fórmulas también son empíricas y no se deben extrapolar más allá del rango de $(t_0/\tau)$ entre 0.1 y 1.0; con ellas se predice que, para un proceso con una sola capacitancia y sin tiempo muerto, el tiempo de integración se aproxima a la constante de tiempo del proceso; mientras que la ganancia proporcional del proceso tiende a infinito, y el tiempo de derivación a cero. Estas tendencias son típicas de las fórmulas de ajuste del punto de control.

```json
{
  "type": "table",
  "id": "table-06-04",
  "page": 290,
  "title": "Tabla 6-4. Fórmulas de ajuste de integral mínima de error para cambios en el punto de control",
  "headers": ["Controlador", "Integral de error", "Fórmula de Kc", "Fórmula de τI", "Fórmula de τD"],
  "rows": [
    ["PI", "IAE", "Kc = (0.758/K)(t₀/τ)^(-0.861)", "τI = (1.02τ)(t₀/τ)^(-0.323)", "-"],
    ["PI", "IAET", "Kc = (0.586/K)(t₀/τ)^(-0.918)", "τI = (1.03τ)(t₀/τ)^(-0.165)", "-"],
    ["PID", "IAE", "Kc = (1.086/K)(t₀/τ)^(-0.869)", "τI = (0.740τ)(t₀/τ)^(-0.130)", "τD = (0.348τ)(t₀/τ)^(0.914)"],
    ["PID", "IAET", "Kc = (0.965/K)(t₀/τ)^(-0.855)", "τI = (0.796τ)(t₀/τ)^(-0.147)", "τD = (0.308τ)(t₀/τ)^(0.929)"]
  ],
  "notes": "Fórmulas de Rovira et al. para ajuste de controladores con criterio de integral mínima de error para cambios en el punto de control",
  "source": "Smith & Corripio, Control Automático de Procesos, Tabla 6-4"
}
```

**Ejemplo 6-12.** Se deben comparar los parámetros de ajuste que se obtienen con los diferentes criterios de integral de error para entrada de perturbaciones en el controlador de temperatura del intercambiador de calor; se debe utilizar la función de transferencia del modelo POMTM del ejemplo 6-9. Se considera a) un controlador P, b) un controlador PI y c) un controlador PID.

**Solución.** Los parámetros para el modelo POMTM del ejemplo 6-9 son, para el método 3:

$$K = 0.80 \text{ °C/%}$$
$$\tau = 33.8 \text{ s}$$
$$t_0 = 11.2 \text{ s}$$

Los parámetros de ajuste de integral mínima de error para entrada de perturbaciones se pueden calcular con las fórmulas de la tabla 6-3:

a) **Controlador P:**

ICE:
$$K_c = \frac{1.411}{0.80}\left(\frac{11.2}{33.8}\right)^{-0.917} = 4.9 \text{ %/%}$$

IAE:
$$K_c = \frac{0.902}{0.80}\left(\frac{11.2}{33.8}\right)^{-0.986} = 3.3 \text{ %/%}$$

IAET:
$$K_c = \frac{0.984}{0.80}\left(\frac{11.2}{33.8}\right)^{-1.084} = 2.0 \text{ %/%}$$

b) **Controlador PI:**

| Criterio | $K_c$ | $\tau_I$, s | $\tau_I$, min |
|----------|-------|-------------|---------------|
| ICE | 4.7 | 30.3 | 0.51 |
| IAE | 3.7 | 25.5 | 0.43 |
| IAET | 3.2 | 23.7 | 0.39 |

c) **Controlador PID:**

| Criterio | $K_c$ | $\tau_I$, s | $\tau_I$, min | $\tau_D$, s | $\tau_D$, min |
|----------|-------|-------------|---------------|-------------|---------------|
| ICE | 5.3 | 13.1 | 0.22 | 6.2 | 0.104 |
| IAE | 5.0 | 16.8 | 0.28 | 4.6 | 0.077 |
| IAET | 4.8 | 17.8 | 0.30 | 4.3 | 0.072 |

La primera conclusión que se obtiene al comparar estos parámetros de ajuste es que, de todas estas fórmulas, resultan valores del mismo orden de magnitud o "encajonados". La segunda es que, del criterio de desempeño ICE, resultan parámetros de control más aproximados a lo real (ganancia más alta y tiempo de integración más corto); mientras que con el IAET generalmente se obtienen los resultados menos aproximados a lo real.

**Ejemplo 6-13.** Se deben comparar las respuestas a los cambios de escalón unitario en los disturbios y en el punto de control, que se obtienen cuando se ajusta un controlador PI a IAE mínima, para las entradas de perturbaciones, contra las respuestas que se obtienen con el mismo criterio, pero respecto a cambios en el punto de control. El circuito se puede representar mediante el diagrama de bloques de la figura 6-21, y el proceso mediante el siguiente modelo POMTM:

$$G(s) = \frac{1.0e^{-0.5s}}{s + 1} \text{ %/%}$$

donde los parámetros de tiempo están en minutos.

**Solución.** Los parámetros POMTM son:

$$K = 1.0 \text{ %/%}$$
$$\tau = 1.0 \text{ min}$$
$$t_0 = 0.5 \text{ min}$$

Ahora se pueden calcular los parámetros de ajuste para un controlador PI con las fórmulas de las tablas 6-3 y 6-4:

**Criterio para perturbaciones (tabla 6-3):**
$$K_c = 0.984\left(\frac{0.5}{1.0}\right)^{-0.986} = 1.95 \text{ %/%}$$
$$\tau_I = 1.02(1.0)\left(\frac{0.5}{1.0}\right)^{-0.323} = 1.16 \text{ min}$$

**Criterio IAE para punto de control (tabla 6-4):**
$$K_c = 0.758\left(\frac{0.5}{1.0}\right)^{-0.861} = 1.38 \text{ %/%}$$
$$\tau_I = 1.02(1.0)\left(\frac{0.5}{1.0}\right)^{-0.323} = 1.16 \text{ min}$$

Para calcular las respuestas, se debe resolver para la variable de salida del diagrama de bloques de la figura 6-21.

**Entrada de perturbación:**
$$\frac{C(s)}{U(s)} = \frac{G(s)}{1 + G(s)G_c(s)}$$

**Entrada del punto de control:**
$$\frac{C(s)}{R(s)} = \frac{G(s)G_c(s)}{1 + G(s)G_c(s)}$$

Sin embargo, la presencia de tiempo muerto en la función de transferencia POMTM [$G(s)$] hace impráctico invertir la transformada de Laplace mediante la expansión de fracciones parciales. Un método más práctico es resolver las ecuaciones del circuito con una computadora digital; las ecuaciones diferenciales para este circuito son las siguientes:

**Proceso POMTM:**
$$\tau\frac{dc(t)}{dt} + c(t) = K[m(t - t_0) + u(t - t_0)]$$

**Controlador PI:**
$$m(t) = K_c\left[e(t) + \frac{1}{\tau_I}\int_0^t e(t)dt\right]$$
$$e(t) = r(t) - c(t)$$

**Entrada de disturbio:**
$$u(t) = u(t) \text{ (escalón unitario)}$$

**Entrada del punto de control:**
$$r(t) = u(t) \text{ (escalón unitario)}$$

**Condiciones iniciales:**
$$c(0) = 0$$
$$m(0) = 0$$

Para resolver estas ecuaciones, Rovira utilizó un programa de computadora, con el cual generó las gráficas de respuesta que se muestran en la figura 6-22. La gráfica de la figura 6-22a es para un cambio de escalón unitario en la perturbación; se observa que con los parámetros de ajuste para perturbación se obtiene una desviación inicial ligeramente menor, y un retorno al punto de control más rápido que con los parámetros de ajuste para el punto de control. La figura 6-22b muestra un cambio de escalón unitario en el punto de control, y se observa que con los parámetros de ajuste se obtiene un sobrepaso significativamente menor para el punto de control, menos comportamiento oscilatorio y un tiempo de asentamiento menor que con los parámetros de ajuste para perturbación. Como se esperaba, el desempeño de cada conjunto de parámetros de ajuste es mejor en la entrada para la cual se diseñan. Las respuestas que se obtuvieron son resultado directo de la alta ganancia y del tiempo de reposición corto que se logran con el ajuste para perturbación.

### Ajuste de controladores por muestreo de datos

La tendencia actual de la industria es hacia la implantación de funciones de control mediante la utilización de microprocesadores (controladores distribuidos) o minicomputadoras y computadoras digitales regulares. La característica común de estos equipos es que los cálculos de control se realizan a intervalos regulares de tiempo $T$, el tiempo de muestreo; esto contrasta con los instrumentos analógicos (electrónicos y neumáticos) donde las funciones se realizan continuamente en el tiempo. El muestreo también es característico de algunos analizadores, por ejemplo, los cromatógrafos de gas en línea.

El modo discreto es la característica de operación de las computadoras y, por tanto, se requiere que a cada instante de muestreo se muestre la señal del transmisor, se calcule el valor de la variable manipulada y se actualice la señal de salida del controlador; entonces, las señales de salida se mantienen constantes durante un intervalo completo de muestreo, hasta la siguiente actualización, lo cual se ilustra en la figura 6-23. Como se podría esperar, esta operación de muestreo y mantenimiento tiene efecto sobre el desempeño del controlador y, en consecuencia, sobre sus parámetros de ajuste.

El tiempo de muestreo de los controladores por computadora varía desde, aproximadamente, 1/3 seg hasta varios minutos, en función de la aplicación; una buena regla práctica consiste en que el tiempo de muestreo sea igual a un décimo a un vigésimo de la constante de tiempo efectiva del proceso. Cuando el tiempo de muestreo es de ese orden de magnitud, en las fórmulas de ajuste su efecto se puede compensar con la adición de un medio del tiempo de muestreo al tiempo muerto del proceso; entonces, se utiliza este tiempo muerto corregido en las fórmulas de ajuste para controladores continuos (tablas 6-2, 6-3 y 6-4). En este método, propuesto por Moore y asociados, se expresa que el tiempo muerto utilizado en las fórmulas de ajuste es:

$$t_{0_c} = t_0 + \frac{T}{2}$$

donde:
- $t_{0_c}$ es el tiempo muerto corregido
- $t_0$ es el tiempo muerto del proceso
- $T$ es el tiempo de muestreo

Cabe hacer notar que, con el método de ajuste en línea, se incorpora implícitamente el efecto del muestreo cuando se determinan la ganancia y el período últimos del circuito con el controlador por muestreo de datos en posición de automático.

Chiu y asociados desarrollaron las fórmulas de ajuste específicas para los controladores por muestreo de datos y Corripio las reprodujo.

### Resumen

En esta sección se presentaron dos métodos para medir las características de un proceso con control mediante un circuito de retroalimentación: el de la ganancia última y el de prueba escalón o curva de reacción del proceso. También se presentó un conjunto de fórmulas de ajuste para el método de ganancia última y tres conjuntos de fórmulas para los parámetros del modelo de primer orden más tiempo muerto. Se observó que, para un proceso dado, con los cuatro conjuntos de fórmulas de ajuste se obtienen parámetros del controlador que se encuentran en el mismo "encajonamiento"; estos parámetros de ajuste son únicamente valores iniciales que se deben ajustar en el campo, de manera que el controlador coincida con la "personalidad" verdadera del proceso específico. Se debe recordar una observación que se hizo al principio de esta sección: según se expuso en los capítulos anteriores, la mayoría de los procesos no son lineales, y sus características dinámicas (i.e., ganancia última y frecuencia última, parámetros del modelo POMTM) varían de un punto de operación a otro, de aquí se concluye que, en el mejor de los casos, los parámetros del controlador a los que se llega mediante el procedimiento de ajuste, son un arreglo entre el comportamiento lento en un extremo del rango de operación y el comportamiento oscilatorio en el otro; en resumen, el ajuste no es una ciencia exacta. Sin embargo, también se debe tener en cuenta que con las fórmulas de ajuste se tiene una visión de la manera en que los diferentes parámetros del controlador dependen de los parámetros del proceso, tales como la ganancia, la constante de tiempo y el tiempo muerto.

## 6-4. SÍNTESIS DE LOS CONTROLADORES POR RETROALIMENTACIÓN

En la sección precedente la atención se centró en el ajuste de un controlador por retroalimentación mediante el ajuste de los parámetros en la estructura de control proporcional-integral-derivativa (PID). En esta sección se hará un enfoque diferente del diseño del controlador, la síntesis del mismo:

> Dadas las funciones de transferencia de las componentes de un circuito de retroalimentación, se debe sintetizar el controlador que se requiere para producir una respuesta específica de circuito cerrado.

A pesar de que no se tiene la seguridad de que el controlador resultante del procedimiento de síntesis se pueda construir en la práctica, se espera obtener alguna visión que aporte elementos para la selección de los diferentes modos del controlador y su ajuste.

### Desarrollo de la fórmula de síntesis del controlador

A continuación se considera el diagrama de bloques simplificado de la figura 6-24, en el cual las funciones de transferencia de todas las componentes del circuito, diferentes del controlador, se concentran en un solo bloque, $G(s)$; del álgebra de diagramas de bloques se tiene que la función de transferencia para el circuito cerrado es:

$$\frac{C(s)}{R(s)} = \frac{G_c(s)G(s)}{1 + G_c(s)G(s)} \quad (6-50)$$

Entonces, a partir de esta expresión, para la función de transferencia del controlador se puede resolver:

$$G_c(s) = \frac{1}{G(s)}\cdot\frac{C(s)/R(s)}{1 - C(s)/R(s)} \quad (6-51)$$

Ésta es la **fórmula de síntesis del controlador**, la cual da por resultado la función de transferencia del controlador $G_c(s)$, a partir de la función de transferencia del proceso $G(s)$ y la respuesta de circuito cerrado que se especifique, $C(s)/R(s)$. Para ilustrar la forma en que se utiliza esta fórmula, a continuación se considera la especificación del control perfecto, es decir, $C(s) = R(s)$ o $C(s)/R(s) = 1$; el controlador que resulta es:

$$G_c(s) = \frac{1}{G(s)}\cdot\frac{1}{1 - 1} = \frac{1}{G(s)}\cdot\frac{1}{0} = \infty$$

Esto indica que, para que la salida sea siempre igual al punto de control, la ganancia del controlador debe ser infinita; en otras palabras, el control perfecto no se puede lograr con la retroalimentación, debido a que cualquier corrección por retroalimentación se basa en un error.

De la fórmula de síntesis del controlador, ecuación (6-51), resultan diferentes controladores para diferentes combinaciones de especificaciones de respuesta de circuito cerrado y funciones de transferencia de proceso. A continuación se aborda cada uno de estos elementos a la vez.

### Especificación de la respuesta de circuito cerrado

La respuesta de circuito cerrado más simple que se puede lograr es la de retardo de primer orden, en ausencia de tiempo muerto en el proceso; esta respuesta es la que se muestra en la figura 6-25, y resulta de la función de transferencia de circuito cerrado:

$$\frac{C(s)}{R(s)} = \frac{1}{\tau_cs + 1} \quad (6-53)$$

donde $\tau_c$ es la constante de tiempo de la respuesta de circuito cerrado y, si se ajusta, se convierte en el único parámetro de ajuste del controlador sintetizado; mientras más pequeña es $\tau_c$, el ajuste del controlador es más estricto.

Nota: Dahlin fue quien propuso originalmente esta respuesta y definió el parámetro de ajuste como el recíproco de la constante de tiempo de circuito cerrado, $\lambda = 1/\tau_c$. En este libro se utilizará $\tau_c$.

Al substituir la ecuación (6-53) en la ecuación (6-51), se obtiene:

$$G_c(s) = \frac{1}{G(s)}\cdot\frac{\frac{1}{\tau_cs + 1}}{1 - \frac{1}{\tau_cs + 1}} = \frac{1}{G(s)}\cdot\frac{1}{\tau_cs} \quad (6-54)$$

Se observa que este controlador tiene acción integral, la cual resulta de la especificación de ganancia unitaria en la función de transferencia de circuito cerrado, ecuación (6-53), y asegura la ausencia de desviación.

A pesar de que se pueden especificar respuestas de segundo orden o superiores para el circuito cerrado, rara vez es necesario hacerlo; sin embargo, cuando el proceso contiene tiempo muerto, en la respuesta de circuito cerrado se debe incluir un término de tiempo muerto igual al tiempo muerto del proceso. A continuación se abordará esto brevemente, pero antes se verá la manera en que la síntesis del controlador puede servir de guía al seleccionar los modos del controlador para diferentes funciones de transferencia del proceso.

### Modos del controlador

La síntesis del controlador permite establecer una relación entre la función de transferencia del proceso y los modos de un controlador PID, debido a que, para funciones de transferencia simples, sin tiempo muerto, el controlador sintetizado se puede expresar en términos de los modos proporcional, integral y derivativo. De la síntesis del controlador también se obtienen las relaciones para los parámetros de ajuste del controlador en términos de la constante de tiempo de circuito cerrado, $\tau_c$, y los parámetros de la función de transferencia del proceso. A continuación se derivan estas relaciones, mediante la substitución de funciones de transferencia de proceso cada vez más complejas en la ecuación (6-54).

**Respuesta del proceso:** $G(s) = K$.

$$G_c(s) = \frac{1}{K}\cdot\frac{1}{\tau_cs} \quad (6-55)$$

donde $K$ es la ganancia del proceso.

Éste es un controlador integral puro, el cual es recomendable para procesos muy rápidos, por ejemplo, controladores de flujo, gobernadores de turbinas de vapor y control de la temperatura de salida de hornos de reformación.

**Proceso de primer orden:** $G(s) = K/(\tau s + 1)$.

$$G_c(s) = \frac{\tau s + 1}{K}\cdot\frac{1}{\tau_cs} = \frac{\tau}{K\tau_c}\left(1 + \frac{1}{\tau s}\right) \quad (6-56)$$

donde $\tau$ es la constante de tiempo del proceso.

Éste es un controlador proporcional-integral (PI), con los siguientes parámetros de ajuste:

$$K_c = \frac{\tau}{K\tau_c} \qquad \tau_I = \tau \quad (6-57)$$

o, en otras palabras, el tiempo de integración se iguala con la constante de tiempo de proceso y la ganancia proporcional es ajustable. Se notará que, si se conoce la constante de tiempo del proceso, $\tau$, el ajuste se reduce a ajustar un solo parámetro: la ganancia del controlador, debido a que el parámetro de ajuste $\tau_c$ únicamente afecta a la ganancia del controlador.

**Proceso de segundo orden:** $G(s) = K/[(\tau_1s + 1)(\tau_2s + 1)]$.

$$G_c(s) = \frac{(\tau_1s + 1)(\tau_2s + 1)}{K}\cdot\frac{1}{\tau_cs} = \frac{\tau_1}{K\tau_c}\left(1 + \frac{1}{\tau_1s}\right)(\tau_2s + 1) \quad (6-58)$$

donde:
- $\tau_1$ es la constante de tiempo más larga o predominante del proceso
- $\tau_2$ es la constante de tiempo más corta del proceso

La ecuación (6-58) satisface la función de transferencia del controlador industrial PID que se trató en el capítulo 5, siempre y cuando se desprecie el término de filtro de ruido ($\alpha\tau_Ds + 1$):

$$G_c(s) = K_c\left(1 + \frac{1}{\tau_Is}\right)\left(\frac{\tau_Ds + 1}{\alpha\tau_Ds + 1}\right)$$

Entonces los parámetros de ajuste son:

$$K_c = \frac{\tau_1}{K\tau_c} \qquad \tau_I = \tau_1 \qquad \tau_D = \tau_2 \quad (6-59)$$

Nuevamente, el procedimiento de ajuste se reduce a ajustar la ganancia del proceso con el tiempo de integración, igual a la constante de tiempo más larga; y el tiempo de derivación, igual a la constante de tiempo más corta. Esta elección arbitraria resulta de la experiencia que indica que el tiempo de derivación debe ser siempre menor al de integración. En la práctica industrial se utilizan generalmente los controladores PID en circuitos de control de temperatura, de manera que la acción derivativa compense el retardo del sensor. Como se ve, se llega a este mismo resultado mediante la síntesis del controlador.

Se puede apreciar fácilmente que para un proceso de tercer orden se requiere un segundo término de derivación, en serie con el primero y con su constante de tiempo igual a la tercera constante de tiempo del proceso más larga, y así, sucesivamente. Una razón para no utilizar esta idea en la práctica es que el controlador sería muy complejo y caro; además, los valores de la tercera y subsecuentes constantes de tiempo de proceso son muy difíciles de determinar en la práctica; el procedimiento común es aproximar los procesos de orden superior con modelos de primer orden más tiempo muerto. A continuación se sintetiza el controlador para tal aproximación de la función de transferencia del proceso.

**Proceso de primer orden más tiempo muerto:** $G(s) = (Ke^{-t_0s})/(\tau s + 1)$.

$$G_c(s) = \frac{\tau s + 1}{Ke^{-t_0s}}\cdot\frac{1}{\tau_cs} = \frac{\tau}{K\tau_c}\left(1 + \frac{1}{\tau s}\right)e^{t_0s} \quad (6-61)$$

donde $t_0$ es el tiempo muerto del proceso.

Se aprecia inmediatamente que este controlador es irrealizable, ya que se requiere un conocimiento del futuro, es decir, un tiempo muerto negativo. Esto es aún más obvio cuando la respuesta que se especifica se compara gráficamente con la mejor posible en circuito cerrado, como se ilustra en la figura 6-26; en esta comparación es evidente que la respuesta especificada se debe retardar mediante algún tiempo muerto en el proceso:

$$\frac{C(s)}{R(s)} = \frac{e^{-t_0s}}{\tau_cs + 1} \quad (6-62)$$

De esto resulta la siguiente función de transferencia para el controlador sintetizado:

$$G_c(s) = \frac{\tau s + 1}{K}\cdot\frac{1}{\tau_cs + 1 - e^{-t_0s}} \quad (6-63)$$

Aunque en principio este controlador se puede realizar actualmente, su implementación está lejos de ser una práctica común, debido, sobre todo, a que originalmente los controladores PID se implementaron con componentes analógicos, y el término $e^{-t_0s}$ no se puede implementar en la práctica con dispositivos analógicos. La implementación moderna de los controladores PID con microprocesadores y computadoras digitales hace posible la implantación del término del tiempo muerto; cuando se hace esto, el término se conoce como "predictor" o "compensación de tiempo muerto".

Para convertir el algoritmo de la ecuación (6-63) a la forma PI estándar, se hace la aproximación del término exponencial mediante la expansión de series de Taylor:

$$e^{-t_0s} \approx 1 - t_0s + \frac{t_0^2s^2}{2} - \ldots \quad (6-64)$$

Si se elimina todo, menos los dos primeros términos, se obtiene una aproximación de primer orden:

$$e^{-t_0s} \approx 1 - t_0s \quad (6-65)$$

Al substituir esta expresión en la ecuación (6-63) y simplificar, se tiene:

$$G_c(s) = \frac{\tau s + 1}{K}\cdot\frac{1}{\tau_cs + 1 - (1 - t_0s)} = \frac{\tau s + 1}{K(\tau_c + t_0)s} = \frac{\tau}{K(\tau_c + t_0)}\left(1 + \frac{1}{\tau s}\right) \quad (6-66)$$

Éste es un controlador PI con el siguiente ajuste:

$$K_c = \frac{\tau}{K(\tau_c + t_0)} \qquad \tau_I = \tau \quad (6-67)$$

La aproximación de primer orden por expansión de Taylor sólo es válida mientras el tiempo muerto es pequeño en comparación con la velocidad de respuesta en circuito cerrado; en otras palabras, un controlador PI sin compensación de tiempo muerto es una buena aproximación de un controlador sintetizado, siempre y cuando el tiempo muerto del proceso sea pequeño en comparación con la constante de tiempo. En general, éste es el caso cuando el proceso no tiene un tiempo muerto verdadero; con el tiempo muerto del modelo se toma en cuenta principalmente la parte de orden superior del proceso.

La conclusión más importante que se tiene de las relaciones de ajuste de la ecuación (6-67) es que, al incrementar el tiempo muerto, resulta una reducción en la ganancia del controlador para una cierta especificación de la constante de tiempo en circuito cerrado. Si se comparan las ecuaciones (6-57) y (6-67), se observa que con la presencia del tiempo muerto se impone un límite a la ganancia del controlador; en otras palabras, para el proceso de primer orden sin tiempo muerto, ecuación (6-57), la ganancia se puede aumentar sin límite para obtener respuestas ($\tau_c \to 0$) cada vez más rápidas; sin embargo, para procesos con tiempo muerto efectivo, ecuación (6-67), se tiene el siguiente límite para la ganancia del controlador:

$$K_{c,max} = \lim_{\tau_c \to 0}\frac{\tau}{K(\tau_c + t_0)} = \frac{\tau}{Kt_0} \quad (6-68)$$

Conforme se incrementa la ganancia del controlador, la respuesta en lazo cerrado se desvía de la respuesta de primer orden especificada; esto es, del incremento de la ganancia puede resultar al final un sobrepaso e incluso una inestabilidad de la respuesta de circuito cerrado, debido a que el error de la aproximación de primer orden por expansión de Taylor se incrementa con la velocidad de respuesta, ya que $s$ se incrementa con la velocidad. (Se recordará que $s$, la variable de la transformada de Laplace, está en unidades recíprocas de tiempo o frecuencia y, por lo tanto, mientras más altas son las velocidades de respuesta o frecuencias, mayor es la magnitud de $s$.)

### Modo derivativo para procesos con tiempo muerto

Si se utiliza un modelo de segundo orden más tiempo muerto para aproximar un proceso de orden superior, se sigue un proceso similar al que se utilizó para el modelo de primer orden más tiempo muerto con que se obtuvo el controlador sintetizado, el cual es equivalente a un controlador PID industrial, ecuación (6-59); esta deducción se deja como ejercicio para el lector. Sin embargo, a causa de que es difícil determinar los parámetros de un modelo de segundo orden, es más atractivo derivar las fórmulas de ajuste para un controlador PID con base en los parámetros de un modelo de primer orden más tiempo muerto, lo cual se puede hacer mediante la utilización de una aproximación diferente al término en tiempo muerto de la ecuación (6-63). La aproximación de primer orden de Padé a la exponencial, la cual se presentó anteriormente, se expresa con:

$$e^{-t_0s} \approx \frac{1 - \frac{t_0s}{2}}{1 + \frac{t_0s}{2}} \quad (6-69)$$

Si se efectúa la división indicada en esta expresión, resulta la siguiente serie infinita:

$$\frac{1 - \frac{t_0s}{2}}{1 + \frac{t_0s}{2}} = 1 - t_0s + \frac{1}{2}(t_0s)^2 - \frac{1}{4}(t_0s)^3 + \ldots \quad (6-70)$$

Por comparación con la ecuación (6-64), se notará que esta expresión coincide en los tres primeros términos con la expansión de la exponencial por series de Taylor y, por tanto, es un poco más precisa que la aproximación que se da en la ecuación (6-65). Esto significa que la ecuación (6-69) es más cercana a la expresión exponencial verdadera para procesos con tiempo muerto superior y razón de tiempo constante.

Se substituye la ecuación (6-69) en la (6-63) y se simplifica para obtener el siguiente controlador sintetizado:

$$G_c(s) = \frac{\tau s + 1}{K}\cdot\frac{1 + \frac{t_0s}{2}}{\tau_cs + \frac{t_0s}{2}} = \frac{\tau}{K(\tau_c + t_0/2)}\left(1 + \frac{1}{\tau s}\right)\left(\frac{\frac{t_0}{2}s + 1}{\frac{\tau_c t_0}{2(\tau_c + t_0/2)}s + 1}\right) \quad (6-71)$$

donde:

$$\tau' = \frac{\tau_c t_0}{2(\tau_c + t_0)}$$

Éste es equivalente a un controlador PID industrial, ecuación (6-59), con parámetros de ajuste:

$$K_c = \frac{\tau}{K(\tau_c + t_0/2)} \qquad \tau_I = \tau \qquad \tau_D = \frac{t_0}{2} \quad (6-72)$$

Aunque en la función de transferencia del controlador industrial existe un término de retardo para evitar la amplificación de ruido de alta frecuencia, generalmente la constante de tiempo $\tau'$ es fija y mucho más pequeña que $\alpha\tau_D$. Para interpretar el significado del término $(1 + \tau's)$, primero se debe observar que para tiempos muertos pequeños ($t_0 \ll \tau$):

$$\tau_I = \tau$$
$$\tau_D = \frac{t_0}{2} \quad (6-73)$$

De la substitución de esta ecuación en la (6-71), resulta exactamente el mismo controlador PI que expresa la ecuación (6-66), con lo cual se confirma la conclusión anterior de que el controlador PI es el adecuado cuando el tiempo muerto es corto. Para tiempos muertos largos y control estricto ($\tau_c \to 0$), el valor de $\tau'$ se convierte en:

$$\tau' = \frac{\tau_c t_0}{2(\tau_c + t_0)} \to \frac{t_0}{2} \quad (6-74)$$

Por lo tanto, para tiempos muertos largos, mientras más estricto es el control, más cercano es el algoritmo sintetizado, ecuación (6-71), al controlador industrial PID cuyos parámetros de ajuste son los de la ecuación (6-72).

Es interesante notar que el tiempo de derivación de la ecuación (6-72) es exactamente el mismo que el obtenido mediante las fórmulas de Ziegler-Nichols para razón de asentamiento de un cuarto (ver tabla 6-2). Sin embargo, la ganancia proporcional para razón de asentamiento de un cuarto es 20% más alta que la ganancia máxima por síntesis ($\tau_c = 0$), y el tiempo de integración de la fórmula de síntesis se relaciona con la constante de tiempo del modelo; por su parte, en la fórmula para la razón de asentamiento de un cuarto se relaciona con el tiempo muerto del modelo.

En la tabla 6-5 se resume la selección de modos del controlador y parámetros de ajuste que resulta del procedimiento de síntesis para la respuesta de Dahlin. El hecho de que la ganancia del controlador sea una función del parámetro de ajuste $\tau_c$ es tanto una ventaja como una desventaja de las fórmulas de ajuste que se obtienen con el procedimiento de síntesis. Es una ventaja porque permite al ingeniero lograr una respuesta específica mediante el ajuste de un solo parámetro, la ganancia, sin importar cuántos modos existan del controlador; sin embargo, la ganancia ajustable es una desventaja, porque con las fórmulas no se obtiene un valor "encajonado" para ésta. Para remediar tal situación, se dan las siguientes guías:

- **$\tau_c$ mínima.** Para entrada de perturbaciones, con $\tau_c = 0$ se minimiza aproximadamente la IAE cuando $t_0/\tau$ está entre 0.1 y 3 para los controladores PI ($\tau_D = 0$), y entre 0.1 y 1.5 para los controladores PID.
- Para cambios en el punto de control, con las siguientes fórmulas se obtiene una IAE aproximadamente mínima cuando $t_0/\tau$ está en el rango de 0.1 a 1.5:

```json
{
  "type": "table",
  "id": "table-06-05",
  "page": 306,
  "title": "Tabla 6-5. Modos de controlador y fórmulas de ajuste para síntesis Dahlin",
  "headers": ["Proceso G(s)", "Controlador", "Parámetros de ajuste"],
  "rows": [
    ["G(s) = K", "I", "Kc = 1/(Kτc) ajustable"],
    ["G(s) = K/(τs+1)", "PI", "Kc = τ/(Kτc) ajustable, τI = τ"],
    ["G(s) = K/[(τ1s+1)(τ2s+1)]", "PID", "Kc = τ1/(Kτc) ajustable, τI = τ1, τD = τ2"],
    ["G(s) = Ke^(-t0s)/(τs+1)", "PIDᵃ", "Kc = τ/[K(τc + t0/2)] ajustable, τI = τ, τD = t0/2"]
  ],
  "notes": "ᵃ Este último sistema de fórmulas se aplica tanto a los controladores PID como a los PI (t0 = 0). El controlador PID se recomienda cuando t0 es mayor que τ/4.",
  "source": "Smith & Corripio, Control Automático de Procesos, Tabla 6-5"
}
```

**Precaución:** Los parámetros de ajuste PID de esta tabla son para controladores analógicos [Ec. (5-45)]. Para su utilización con controladores que se basan en microprocesadores [Ec. (5-44)], los parámetros de ajuste de esta tabla se deben convertir mediante las siguientes fórmulas:

**Controlador PI ($\tau_D = 0$):**
$$K_c' = K_c \quad (6-75a)$$

**Controlador PID:**
$$\tau_I' = \tau_I + \tau_D \quad (6-75b)$$
$$\tau_D' = \frac{\tau_I\tau_D}{\tau_I + \tau_D}$$

Estas fórmulas se usan con el último renglón de la tabla 6-5.

**Sobrepaso del 5%.** Para entradas del punto de control es deseable tener una respuesta con sobrepaso de 5% del valor del cambio en el punto de control. Para este tipo de respuesta, Martin y asociados recomiendan que $\tau_c$ se iguale con el tiempo muerto efectivo del modelo POMTM, de lo cual resulta la siguiente fórmula para la ganancia del controlador con que se produce un sobrepaso de 5% de los cambios en el punto de control:

$$K_c = \frac{0.5}{K}\cdot\frac{\tau}{t_0} \quad (6-76)$$

Al comparar esta fórmula con la de la tabla 6-2, se observa que esto es aproximadamente 40% de la ganancia que se requiere en el PID para razón de asentamiento de un cuarto (sobrepaso del 50%).

Un punto interesante acerca del método de síntesis de controladores es que, si los controladores se hubieran diseñado desde un principio de este modo, en la evolución de los modos de los controladores se habría seguido el patrón I, PI, PID, el cual se deduce a partir de la consideración del modelo de proceso más simple hasta el más complejo. Esto contrasta con la evolución real de los controladores industriales: P, PI, PID, es decir, del controlador más simple hasta el más complejo.

Una visión importante que se puede obtener con base en el procedimiento de síntesis del controlador es que el efecto principal de añadir el modo proporcional al modo integral básico, es compensar el retardo más largo o dominante del proceso; mientras que el del modo derivativo es compensar el segundo retardo más largo o el tiempo muerto efectivo del proceso. El procedimiento entero de síntesis se basa en la suposición de que la especificación principal de la respuesta de circuito cerrado tiene como función eliminar la desviación o el error de estado estacionario, lo cual hace que la acción integral sea el modo básico del controlador.

**Ejemplo 6-14.** Para el intercambiador de calor del ejemplo 6-5 se deben determinar los parámetros de ajuste mediante la utilización de las fórmulas que se obtuvieron con el método de síntesis de controlador. Se deben comparar estos resultados con los obtenidos mediante las fórmulas de ajuste de IAE mínima para entradas del punto de control.

**Solución.** Los parámetros POMTM que se obtuvieron para el intercambiador de calor mediante el método 3 en el ejemplo 6-9 son:

$$K = 0.80 \text{ °C/%}$$
$$\tau = 33.8 \text{ s}$$
$$t_0 = 11.2 \text{ s}$$

Mediante la substitución de estos valores en la ecuación (6-71) se obtiene la función de transferencia del controlador sintetizado:

$$G_c(s) = \frac{33.8}{0.80(\tau_c + 11.2)}\left(1 + \frac{1}{33.8s}\right)\left(\frac{5.6s + 1}{\frac{5.6\tau_c}{\tau_c + 11.2}s + 1}\right)$$

Puesto que en este caso el tiempo muerto es mayor que un cuarto de la constante de tiempo, lo recomendable es utilizar un controlador PID. La ganancia de IAE mínima para perturbación se obtiene con $\tau_c = 0$:

$$K_c = \frac{33.8}{(0.80)(11.2)} = 3.8 \text{ %/%}$$

Para IAE mínima de entrada del punto de control, de la ecuación (6-57b), se tiene:

$$\tau_I = \frac{1}{2}(11.2) = 5.6 \text{ s}$$
$$K_c = \frac{33.8}{(0.80)(5.6 + 11.2)} = 2.5 \text{ %/%}$$

Para un sobrepaso de 5% en la entrada del punto de control, de la ecuación (6-76), se tiene:

$$K_c = \frac{(0.5)(33.8)}{(0.80)(11.2)} = 1.9 \text{ %/%}$$

Los tiempos de integración y derivación son:

$$\tau_I = \tau = 33.8 \text{ s (0.56 min)}$$
$$\tau_D = \frac{t_0}{2} = 5.6 \text{ s (0.093 min)}$$

Para la comparación, los parámetros de IAE mínima para las entradas del punto de control se calculan mediante las fórmulas PID de la tabla 6-4:

$$K_c = \frac{1.086}{0.80}\left(\frac{11.2}{33.8}\right)^{-0.869} = 3.5 \text{ %/%}$$
$$\tau_I = 0.740(33.8)\left(\frac{11.2}{33.8}\right)^{-0.130} = 48.9 \text{ s (0.81 min)}$$
$$\tau_D = 0.348(33.8)\left(\frac{11.2}{33.8}\right)^{0.914} = 4.3 \text{ s (0.071 min)}$$

Ambos conjuntos de parámetros están en el mismo encajonamiento.

**Ejemplo 6-15.** En un proceso de segundo orden más tiempo muerto se tiene la siguiente función de transferencia:

$$G(s) = \frac{1.0e^{-0.26s}}{s^2 + 4s + 1}$$

Se deben comparar las respuestas de un controlador PI a un cambio en el punto de control tipo escalón, con ajuste mediante a) la razón de asentamiento de un cuarto de Ziegler-Nichols, b) IAE mínima para cambios en el punto de control, c) síntesis de controlador con ajuste de ganancia para un sobrepaso del 5%. Se utilizará la figura 6-18 para obtener los parámetros del modelo de primer orden más tiempo muerto (POMTM).

**Solución.** El primer paso es aproximar la función de transferencia de segundo orden con un modelo POMTM; se empieza por factorizar el denominador en dos constantes de tiempo:

$$(\tau_1s + 1)(\tau_2s + 1) = \tau_1\tau_2s^2 + (\tau_1 + \tau_2)s + 1 = s^2 + 4s + 1$$

$$\tau_1\tau_2 = 1$$
$$\tau_1 + \tau_2 = 4$$

$$\tau_1^2 - 4\tau_1 + 1 = 0$$
$$\tau_1 = \frac{4 + \sqrt{12}}{2} = 3.73 \text{ min}$$
$$\tau_2 = 4 - 3.73 = 0.27 \text{ min}$$

Entonces, la función de transferencia se puede escribir como:

$$G(s) = \frac{1.0e^{-0.26s}}{(3.73s + 1)(0.27s + 1)}$$

El segundo paso consiste en aproximar el retardo de segundo orden con un modelo POMTM, si se usa la figura 6-18:

$$\frac{\tau_2}{\tau_1} = \frac{0.27}{3.73} = 0.072$$

$$\tau = 1.0\tau_1 = 3.73 \text{ min}$$
$$t_0' = 0.072\tau_1 = 0.27 \text{ min}$$

se notará que la segunda constante de tiempo es lo suficientemente pequeña como para aplicar la simple regla práctica de la sección 6-3, que es $\tau = \tau_1$ y $t_0' = \tau_2$. El tiempo muerto efectivo del modelo POMTM se debe añadir al tiempo muerto del proceso real, para obtener el tiempo muerto total:

$$t_0 = 0.26 + t_0' = 0.53 \text{ min}$$

Entonces, los parámetros POMTM son:

$$K = 1.0$$
$$\tau = 3.73 \text{ min}$$
$$t_0 = 0.53 \text{ min}$$

El tercer paso es calcular los parámetros de ajuste a partir de las fórmulas que se especificaron. Para un controlador PI:

a) **Razón de asentamiento de un cuarto (de la tabla 6-2):**

$$K_c = \frac{3.33(3.73)}{1.0(0.53)} = 23.4 \text{ %/%}$$
$$\tau_I = 3.33t_0 = 3.33(0.53) = 1.76 \text{ min}$$

b) **IAE mínima para cambios en el punto de control (de la tabla 6-4):**

$$K_c = \frac{0.758}{1.0}\left(\frac{0.53}{3.73}\right)^{-0.861} = 4.1 \text{ %/%}$$
$$\tau_I = 1.02(3.73)\left(\frac{0.53}{3.73}\right)^{-0.323} = 3.83 \text{ min}$$

c) **Síntesis del controlador con ajuste para un sobrepaso del 5% (de la ecuación 6-76):**

$$\tau_I = \tau = 3.73 \text{ min}$$

De la ecuación (6-76) se tiene que, para un sobrepaso del 5%:

$$K_c = \frac{0.5(3.73)}{1.0(0.53)} = 3.57 \text{ %/%}$$

El último paso consiste en comparar las respuestas al escalón unitario en el punto de control, mediante la utilización de cada uno de estos tres juegos de parámetros de ajuste. Martín y asociados publicaron la solución a este problema, misma que obtuvieron mediante la utilización de una computadora analógica para simular el siguiente sistema de ecuaciones (ver figura 6-22, donde aparece el diagrama de bloques correspondiente):

$$\frac{d^2c}{dt^2} + 4\frac{dc}{dt} + c(t) = m(t - 0.26)$$
$$c(0) = 0 \qquad \frac{dc}{dt}(0) = 0$$
$$m(t) = K_c\left[e(t) + \frac{1}{\tau_I}\int_0^t e(t)dt\right]$$
$$e(t) = r(t) - c(t)$$
$$r(t) = 1 \text{ para } t > 0$$

Se utilizó una aproximación estándar de Padé para simular el tiempo muerto.

En la figura 6-27 se ilustran las respuestas que resultan. En la comparación de las respuestas se observa que con las fórmulas de síntesis del controlador para un sobrepaso del 5% se obtiene una respuesta muy cercana a la respuesta de IAE mínima para el punto de control. Estas respuestas son superiores a la de razón de asentamiento de un cuarto, en términos de estabilidad y tiempo de asentamiento para cambios en el punto de control.

En esta sección se presentó la técnica de síntesis. De los controladores sintetizados resultantes se obtuvo una nueva visión de las funciones de los modos proporcional, integral y derivativo; también se obtuvo un conjunto de relaciones de ajuste para los controladores PID.

## 6-5. PREVENCIÓN DEL REAJUSTE EXCESIVO

En las secciones precedentes se vio que la acción de integración o de reajuste es necesaria para eliminar la desviación o error de estado estacionario en los controladores por retroalimentación. Como se explicó en el capítulo 5, uno de los perjuicios que se tienen con esta ventaja es el "reajuste excesivo" o sobrepaso excesivo de la variable controlada, cuando la señal de salida del controlador regresa a su rango normal después de un período de saturación; a esto se debe que se requiera cambiar a "manual" los controladores durante el arranque o parada del proceso, ya que bajo esas condiciones es cuando los controladores se saturan con más frecuencia. Se dice que el controlador se satura cuando su señal de salida está en o fuera de los límites de operación de la válvula de control o elemento final de control; cuando esto ocurre, se interrumpe el circuito de control y la variable controlada se desvía del punto de control, como se podría esperar. Como consecuencia de la acción de integración, se puede requerir una gran desviación en la dirección contraria para regresar la salida del controlador a su rango normal de operación. El reajuste excesivo es esta incapacidad para que el controlador se pueda recuperar rápidamente de una condición de saturación.

A fin de repasar el concepto de reajuste excesivo, a continuación se considera el arranque del tanque calentado por vapor que se esboza en la figura 6-28a. Se utiliza un controlador proporcional-integral (PI) con retroalimentación (TIC) para controlar la temperatura en el tanque, mediante el ajuste de la válvula de control del vapor. Los instrumentos son neumáticos con un rango normal de 3 a 15 psi y una presión de alimentación de 20 psig. Si el controlador se deja en automático durante el arranque, su salida se va al valor máximo, 20 psig de la presión de alimentación, a causa de la acción de integración, debido a que la temperatura permanece debajo del punto de régimen durante un largo período. En la figura 6-28b se ilustra el registro de tiempo durante el arranque del proceso. Al inicio la válvula de vapor se abre totalmente, mientras la variable de salida del controlador está al valor de la presión de alimentación, que es de 20 psig. A pesar de que el controlador se satura, la válvula de vapor se mantiene completamente abierta; esta estrategia es la correcta para calentar en tiempo mínimo el contenido del tanque hasta el punto de control. El problema de exceso empieza a aparecer cuando la temperatura del tanque alcanza el punto de control (punto de régimen, referencia o fijación) y en ese instante la salida del controlador es:

$$m(t) = \bar{m} + K_c e(t) + \frac{K_c}{\tau_I}\int_0^t e(t)dt = 20 \text{ psig}$$

Esto se debe a que, con la acción de integración, la salida del controlador se lleva al valor de la presión de alimentación. (Se notará que esto equivale a igualar con 20 psig el valor de desviación y el término de integración a cero.) Puesto que la válvula de control del vapor no se empieza a cerrar sino hasta que la salida del controlador alcanza 15 psig, se requiere un error negativo grande para provocar un descenso de 5 psig en la salida del controlador. Por ejemplo, cuando se tiene únicamente acción proporcional y se supone una banda de proporcionalidad de 25% ($K_c = 4$), el error mínimo requerido para empezar a cerrar la válvula es:

$$M = 20 + K_c e \text{ psig}$$
$$e = \frac{-5}{4} = -1.25 \text{ psig (-10.4\% de rango)}$$

Éste es un error significativo e indica que la temperatura continuará subiendo por arriba del punto de control mientras la válvula de vapor permanezca completamente abierta; parecerá que el controlador no responde a la elevación en la temperatura, entonces se dice que está "excedido".

Con la acción de integración se puede empezar a reducir la salida del controlador tan pronto como el error se hace negativo, de manera que el error puede alcanzar un pico con valor inferior al que se estimó con anterioridad (-10.4%). Sin embargo, si no fuera por la acción de integración, en primer lugar, el valor de desviación $\bar{m}$ no hubiera llegado a 20 psig. Como se vio en el capítulo 5, la fórmula para un controlador proporcional es:

$$m(t) = \bar{m} + K_c e(t)$$

Si se considera un valor de desviación $\bar{m}$ de 9, con el controlador proporcional se empieza a cerrar la válvula de vapor antes de que la temperatura alcance el punto de control. Por lo tanto, la acción de integración es la causa de que exista un gran sobrepaso de temperatura, como se ilustra en la figura 6-28b y, puesto que ese efecto es altamente indeseable, ¿cómo se puede evitar?

Una forma de evitar el gran sobrepaso que ocasiona el reajuste excesivo es mantener el controlador en manual hasta que la temperatura llegue al punto de control, y cambiarlo entonces a automático. En este caso la válvula de vapor se mantiene completamente abierta mediante el ajuste manual de la salida del controlador a 15 psig, con lo cual se garantiza que la válvula de control se comenzará a cerrar tan pronto como el controlador se cambia a automático. Una segunda alternativa es instalar un limitador de la salida del controlador para evitar que llegue a valores más allá del rango de la válvula de control, es decir, arriba de 15 psig o abajo de 3 psig, pero, ¿es que esto funciona? Para responder esta pregunta se divide el diagrama de bloques del controlador en sus respectivas partes. La función de transferencia del controlador PI se expresa mediante:

$$M(s) = K_c\left(1 + \frac{1}{\tau_Is}\right)E(s) = K_cE(s) + M_I(s)$$

donde:

$$M_I(s) = \frac{K_c}{\tau_Is}E(s)$$

En la figura 6-29a se ilustra una construcción directa con base en esta función de transferencia, en diagrama de bloques. En el diagrama se muestra por qué al instalar un limitador a la salida del controlador no se evita el problema de exceso: la salida de la acción de integración, $M_I(s)$, aún se irá más allá de los límites de la salida del controlador y causará el exceso. En otras palabras, para evitar el exceso, se debe limitar de alguna manera la salida de la acción de integración; en los controladores analógicos neumáticos y electrónicos se logra esta limitación de una manera muy ingeniosa: primero, a partir de la definición de $M_I(s)$, se tiene:

$$M_I(s) = \frac{K_c}{\tau_Is}E(s) \quad (6-78)$$

Al resolver para $K_cE(s)$, de la ecuación (6-78), se obtiene:

$$K_cE(s) = \tau_IsM_I(s) \quad (6-79)$$

De combinar las ecuaciones (6-78) y (6-79) y ordenar, resulta:

$$M_I(s) = \frac{1}{\tau_Is + 1}M(s) \quad (6-80)$$

Esta construcción para la acción de integración se representa en el diagrama de bloques de la figura 6-29b, en el cual se puede observar que, si el limitador se coloca como se muestra, $M_I(s)$ se limita automáticamente. Esto se debe a que $M_I(s)$ siempre está en retardo respecto a $M(s)$, con una ganancia de 1 y una constante de tiempo ajustable $\tau_I$; por lo tanto, nunca estará fuera del rango al que se limita $M(s)$. En otras palabras, si $M(s)$ alcanza uno de sus límites, $M_I(s)$ se acercará a ese límite, es decir, 15 psig; entonces, en el momento en que el error se vuelve negativo, la salida del controlador se hace:

$$m(t) = 15 + K_c e(t) < 15 \text{ psig, ya que } e(t) < 0$$

Esto es, la salida del controlador llega fuera del límite y cierra la válvula de control, ¡en el instante en que la variable controlada pasa por el punto de control!

Se observa que en estado estable el error debe ser cero, ya que:

$$m = \bar{m} + K_c e + \frac{K_c}{\tau_I}\int_0^t e(t)dt = \bar{m}$$

Y, por lo tanto, no debe existir desviación.

El limitador que se muestra en la figura 6-29b se conoce algunas veces como "conmutador por lotes" ("batch switch") porque en los procesos por lotes se presentan situaciones de exceso con suficiente frecuencia como para justificar el gasto extra por el limitador. Actualmente, en los controladores que se construyen con microprocesadores, el limitador es una característica de control estándar.

La estructura de "retroalimentación de reajuste" de la figura 6-29b tiene la ventaja que proporciona, de una manera muy limpia y directa, la eliminación del reajuste excesivo en los sistemas de control por superposición y en cascada. En las secciones en que se cubren tales tópicos se hará mención a esto.

## 6-6. RESUMEN

El control por retroalimentación es la estrategia básica del control de procesos industriales. En este capítulo se presentaron métodos para determinar la respuesta linealizada de un circuito de control por retroalimentación y sus límites de estabilidad; también se presentaron varias técnicas para ajustar los controladores con retroalimentación y se abordó el problema del reajuste excesivo y la manera de prevenirlo en circuitos simples.

Hasta el momento se expusieron dos métodos para analizar la estabilidad de un circuito de control, la prueba de Routh y la substitución directa, así como un método para medir la dinámica del proceso: la prueba de escalón. En el capítulo siguiente se estudiarán dos métodos clásicos para analizar las respuestas del circuito de control: el lugar de raíz y la respuesta en frecuencia; también se presentará un método más eficaz para la identificación del proceso: la prueba de pulso.

## BIBLIOGRAFÍA

1. Ziegler, J. G., y Nichols, N. B., "Optimum Settings for Automatic Controllers," *Transactions ASME*, Vol. 64, Nov. 1942, p. 759.
2. Smith, Cecil L., *Digital Computer Process Control*, Intext Educational Publishers, Scranton, Pa., 1972.
3. Martin, Jacob Jr., Ph.D. dissertation, Department of Chemical Engineering, Louisiana State University, Baton Rouge, 1975.
4. Murrill, Paul W., *Automatic Control of Processes*, International Textbook Company, Scranton, Pa., 1967.
5. López, A. M., P. W. Murrill y C. L. Smith, "Controller Tuning Relationships Based on Integral Performance Criteria," *Instrumentation Technology*, Vol. 14, No. 11, Nov. 1967, p. 57.
6. Rovira, Alberto A., Ph.D. dissertation, Department of Chemical Engineering, Louisiana State University, Baton Rouge, 1981.
7. Dahlin, E. B., "Designing and Tuning Digital Controllers," *Instruments and Control Systems*, Vol. 41, No. 6, Junio 1968, p. 77.
8. Martin, Jacob Jr., A. B. Corripio y C. L. Smith, "How to Select Controller Modes and Tuning Parameters from Simple Process Models," *ISA Transactions*, Vol. 15, No. 4, 1976, pp. 314-319.
9. Carlson, A., G. Hannauer, T. Carey y P. J. Holsberg, *Handbook of Analog Computation*, 2nd ed., Electronic Associates, Inc., Princeton, N.J., 1967, p. 226.
10. Moore, C. F., C. L. Smith y P. W. Murrill, "Simplifying Digital Control Dynamics for Controller Tuning and Hardware Lag Effects," *Instrument Practice*, Vol. 23, No. 1, Ene. 1969, p. 45.
11. Chiu, K. C., A. B. Corripio y C. L. Smith, "Digital Control Algorithms. Part III. Tuning PI and PID Controllers," *Instruments and Control Systems*, Vol. 46, No. 12, Dic. 1973, pp. 41-43.
12. Corripio, A. B., "Digital Control Techniques," en Edgar, T. F., Ed., *Process Control*, AIChE MI, Series A. Vol. 3, American Institute of Chemical Engineers, Nueva York, 1982, p. 69.

## PROBLEMAS

**6-1.** En el diagrama de bloques de la figura 6-4a se representa un circuito de control con retroalimentación; en el proceso se puede representar con dos retardos en serie:

$$G(s) = \frac{K}{(\tau_1s + 1)(\tau_2s + 1)}$$

donde la ganancia del proceso es $K = 0.80$ %/% y las constantes de tiempo son $\tau_1 = 1$ min, $\tau_2 = 1$ min. El controlador es un controlador proporcional: $G_c(s) = K_c$.

a) Se debe obtener la función de transferencia de circuito cerrado y la ecuación característica del circuito.
b) ¿Para qué valores de la ganancia del controlador, la respuesta del circuito a un cambio escalón en el punto de control es sobreamortiguada, críticamente amortiguada o subamortiguada? ¿Se puede hacer que el circuito sea inestable?
c) Se debe determinar la respuesta del circuito cerrado a un cambio escalón en el punto de control para $K_c = 0.16$, 0.25, 0.50.

**6-2.** Resolver el problema 6-1 para una función de transferencia:

$$G(s) = \frac{6(1 - s)e^{-0.5s}}{(s + 1)(0.5s + 1)}$$

Las funciones de transferencia como ésta son típicas en los procesos que constan de dos retardos en paralelo con acción opuesta. El controlador es un controlador proporcional, como en el problema 6-1.

**6-3.** En el diagrama de bloques de la figura 6-4a se representa un circuito de control por retroalimentación; el proceso se puede representar mediante un retardo de primer orden y el controlador es proporcional-integral:

$$G_c(s) = K_c\left(1 + \frac{1}{\tau_Is}\right)$$

Sin detrimento de la generalidad, la constante de tiempo del proceso $\tau = 1$ y la ganancia del proceso $K = 1$.

a) Se debe escribir la función de transferencia de circuito cerrado y la ecuación característica del circuito.
b) ¿Existe una ganancia última para este circuito?
c) Se debe determinar la respuesta de circuito cerrado a un cambio de escalón en el punto de control para $\tau_I = \tau$, conforme la ganancia del controlador varía de cero a infinito.

**6-4.** Se tiene el circuito de control con retroalimentación del problema 6-1 y un controlador puramente integral:

$$G_c(s) = \frac{K_I}{s}$$

a) Se debe determinar la ganancia última del controlador por la prueba de Routh.
b) Se debe recalcular la ganancia última del controlador para $\tau_2 = 0.10$ y $\tau_2 = 2$. ¿Los resultados son los que se esperaban?
c) Se deben verificar las ganancias últimas que se calcularon en las partes a) y b), mediante el método de substitución directa, y determinar la frecuencia última de oscilación del circuito.

**6-5.** Para el circuito de control con retroalimentación del problema 6-1 y un controlador proporcional-integral:

$$G_c(s) = K_c\left(1 + \frac{1}{\tau_Is}\right)$$

a) Se debe determinar la ganancia última del circuito $K_{c_u}$ y la frecuencia última de oscilación como funciones del tiempo de integración $\tau_I$.
b) Se debe determinar la respuesta de circuito cerrado a un cambio escalón en el punto de control; el controlador se ajusta para IAE mínima. Se debe utilizar la figura 6-18 para determinar los parámetros del modelo de primer orden más tiempo muerto (POMTM).
c) Se repetirá la parte b) con el controlador ajustado para un sobrepaso del 5%; se utilizarán las fórmulas de síntesis del controlador, ecuaciones (6-67) y (6-76).

**6-6.** Para el circuito de control con retroalimentación que se representa en la figura 6-4a se debe determinar la ganancia última para un controlador proporcional, mediante la prueba de Routh, así como cada una de las siguientes funciones de transferencia del proceso:

a) $G(s) = \frac{1}{(s+1)^2}$
b) $G(s) = \frac{1}{(s+1)^3}$
c) $G(s) = \frac{1}{(3s+1)(2s+1)(s+1)}$
d) $G(s) = \frac{(0.5s+1)}{(3s+1)(2s+1)(s+1)}$
e) $G(s) = \frac{1}{(3s+1)(0.2s+1)(0.1s+1)}$
f) $G(s) = \frac{e^{-0.5s}}{3s+1}$

Cabe anotar que la parte f) es una aproximación de primer orden más tiempo muerto de la parte c), para lo cual se utiliza la regla práctica de la sección 6-3.

**6-7.** Se debe resolver el problema 6-6 por medio de la substitución directa, para determinar la ganancia última del controlador y la frecuencia última de oscilación del circuito.

**6-8.** En el diagrama de bloques de la figura 6-21 se representa un circuito de control por retroalimentación; la función de transferencia del proceso se expresa por:

$$G(s) = \frac{K}{(\tau_1s+1)(\tau_2s+1)(\tau_3s+1)}$$

donde la ganancia del proceso es $K = 2.5$ %/% y las constantes de tiempo son $\tau_1 = 5$ min, $\tau_2 = 0.8$ min, $\tau_3 = 0.2$ min.

Se deben determinar los parámetros de ajuste para la respuesta de asentamiento de un cuarto, mediante el método de la ganancia última para:

a) Un controlador proporcional (P)
b) Un controlador proporcional-integral (PI)
c) Un controlador proporcional-integral-derivativo (PID)

**6-9.** Se utilizarán los parámetros de ajuste que se calcularon para el circuito del problema 6-8, a fin de encontrar la respuesta de circuito cerrado a un cambio escalón en la perturbación, $V(s) = 1/s$.

Nota: El estudiante puede resolver este problema mediante la inversión de la transformada de Laplace o la utilización de uno de los programas de simulación por computadora que se listan en el capítulo 9. En la solución por transformada de Laplace se requiere la utilización del método que se expuso en el capítulo 2 para resolver raíces de polinomios o un programa de computadora como el que se lista en el apéndice D.

**6-10.** Se tiene el circuito de control con retroalimentación de la figura 6-21 y la siguiente función de transferencia del proceso:

$$G(s) = \frac{Ke^{-t_0s}}{(\tau_1s+1)(\tau_2s+1)}$$

donde la ganancia del proceso, las constantes de tiempo y el tiempo muerto son:

$$K = 1.0 \qquad \tau_1 = 1 \text{ min} \qquad \tau_2 = 0.6 \text{ min} \qquad t_0 = 0.20 \text{ min}$$

se deben calcular los parámetros de ajuste de primer orden más tiempo muerto (POMTM), para lo cual se utiliza la figura 6-18. Después se utilizan estos parámetros para comparar los parámetros de ajuste de un controlador proporcional-integral (PI) con la utilización de las siguientes fórmulas:

a) Respuesta de razón de asentamiento de un cuarto
b) IAE mínima para entradas de perturbaciones
c) IAE mínima para entradas del punto de control
d) Síntesis del controlador para un sobrepaso del 5% con un cambio en el punto de control.

**6-11.** Se debe resolver el problema 6-10 para un controlador proporcional-integral-derivativo (PID).

**6-12.** Se debe resolver el problema 6-10 para un controlador por muestreo de datos (computadora) con un tiempo de muestreo $T = 0.10$ min.

**6-13.** Para el lazo de control del problema 6-10 se deben obtener las fórmulas de ajuste para un controlador industrial PID; se utilizará el procedimiento de síntesis de Dahlin y se considerarán dos casos:

a) No hay tiempo muerto, $t_0 = 0$.
b) Hay tiempo muerto.

Las respuestas se deben verificar con la tabla 6-5.

**6-14.** En este problema se utiliza el programa de computadora que se lista en el ejemplo 9-5 para obtener las respuestas a los cambios escalón en el punto de control en la perturbación del circuito de control de los problemas 6-10 y 6-11; se deben utilizar los parámetros de ajuste que se determinaron en los mismos. ¿Se puede mejorar el desempeño del control mediante ajuste por ensayo y error de los parámetros de ajuste? Con el programa se imprime la integral del error absoluto (IAE), el cual se puede utilizar para medir el desempeño del control.

Nota: En los problemas siguientes se requiere que el estudiante aplique los conocimientos que aprendió en los capítulos 1 a 6 de este libro.

**6-15.** Ahora se considera el filtro de vacío que se muestra en la figura 6-30; este proceso es parte de una planta de tratamiento de desperdicios. La mezcla de desechos entra al filtro con casi 5% de sólidos; en el filtro de vacío se elimina el agua de la mezcla, con lo que queda cerca del 25% de sólidos. La capacidad para filtrar la mezcla en el filtro rotatorio depende del pH de la mezcla que entra al filtro. Una forma para controlar la humedad en la mezcla que entra al incinerador es añadir compuestos químicos (cloruro férrico) a la mezcla que entra al proceso, para mantener el pH que se necesita. En la figura 6-30 se ilustra la estructura de control que se usa algunas veces; el rango del transmisor de humedad es de 60 a 95%.

Los siguientes datos se obtuvieron con una prueba de escalón sobre la salida del controlador (MIC70) de +2 mA:

| Tiempo, min | Humedad, % | Tiempo, min | Humedad, % |
|-------------|------------|-------------|------------|
| 0 | 75.0 | 10.5 | 70.9 |
| 1 | 75.0 | 11.5 | 70.3 |
| 1.5 | 75.0 | 13.5 | 69.3 |
| 2.5 | 75.0 | 15.5 | 68.6 |
| 3.5 | 74.9 | 17.5 | 68.0 |
| 4.5 | 74.6 | 19.5 | 67.6 |
| 5.5 | 74.3 | 21.5 | 67.4 |
| 6.5 | 73.6 | 25.5 | 67.1 |
| 7.5 | 73.0 | 29.5 | 67.0 |
| 8.5 | 72.3 | 33.5 | 67.0 |
| 9.5 | 71.6 | | |

Cuando la entrada de humedad al filtro se cambió en 2%, se obtuvieron los siguientes datos:

| Tiempo, min | Humedad, % | Tiempo, min | Humedad, % |
|-------------|------------|-------------|------------|
| 0 | 75 | 11 | 75.9 |
| 1 | 75 | 12 | 76.1 |
| 2 | 75 | 13 | 76.2 |
| 3 | 75 | 14 | 76.3 |
| 4 | 75.0 | 15 | 76.4 |
| 5 | 75.0 | 17 | 76.6 |
| 6 | 75.1 | 19 | 76.7 |
| 7 | 75.3 | 21 | 76.8 |
| 8 | 75.4 | 25 | 76.9 |
| 9 | 75.6 | 29 | 77.0 |
| 10 | 75.7 | 33 | 77.0 |

a) Se debe dibujar el diagrama de bloques del circuito de control para la humedad; se incluirán las posibles perturbaciones.
b) Se aproximarán las funciones de transferencia mediante modelos de primer orden más tiempo muerto y se determinarán los parámetros de los modelos; entonces se redibujará el diagrama de bloques para mostrar la función de transferencia de cada bloque, para lo cual se utiliza el método de cálculo 3.
c) Se debe expresar una idea sobre la capacidad para controlar la humedad a la salida; además, se debe indicar la acción del controlador.
d) Se obtendrá la ganancia de un controlador proporcional para respuesta de IAE mínima. Se deberá calcular la desviación para un cambio del 1% en la humedad de entrada.
e) Se debe obtener la ganancia última y el período último para este circuito de control. El término de tiempo muerto se puede aproximar mediante una aproximación de Padé de primer orden, como se expresa en la ecuación (6-29).
f) Se debe ajustar un controlador PI para una respuesta de razón de asentamiento de un cuarto.

**6-16.** Ahora se considera el absorbedor que aparece en la figura 6-31. Al absorbedor entra un flujo de gas cuya composición es de 90 mol% de aire y 10 mol% de amoniaco (NH₃). Antes de arrojar este gas a la atmósfera es necesario remover la mayor parte de NH₃ del mismo, lo cual se puede hacer mediante absorción en agua. La concentración de NH₃ en el vapor que sale no debe sobrepasar los 200 ppm; el absorbedor se diseñó de manera que el vapor de salida tenga una concentración de 50 ppm de NH₃. Durante el diseño se hicieron varias simulaciones dinámicas, de ellas se obtuvieron los siguientes datos:

**Respuesta a un cambio escalón en el caudal de agua que llega al absorbedor:**

| Tiempo, s | Caudal de agua, gpm | Concentración de NH₃ a la salida, ppm |
|-----------|---------------------|--------------------------------------|
| 0 | 250 | 0 |
| 0 | 250 | 0 |
| 0 | 200 | 0 |
| 10 | 200 | 0 |
| 20 | 200 | 0 |
| 30 | 200 | 50.12 |
| 40 | 200 | 50.30 |
| 50 | 200 | 50.50 |
| 60 | 200 | 51.02 |
| 70 | 200 | 51.20 |
| 80 | 200 | 51.26 |
| 90 | 200 | 51.35 |
| 100 | 200 | 51.41 |
| 110 | 200 | 51.55 |
| 120 | 200 | 51.63 |
| 130 | 200 | 51.70 |
| 140 | 200 | 51.76 |
| 160 | 200 | 51.77 |
| 180 | 200 | 51.77 |
| 200 | 200 | 51.77 |
| 220 | 200 | 51.77 |

a) Se ha de diseñar el circuito de control para mantener la concentración de NH₃ a la salida en un punto de control de 50 ppm y dibujar el diagrama de instrumentos para el circuito. En el mercado se cuenta con algunos instrumentos que se pueden utilizar para tal propósito. Existe un sensor y transmisor de concentración electrónico con calibración de 0-200 ppm, el cual tiene un retardo de tiempo despreciable. También se cuenta con una válvula accionada por aire que, abierta completamente y con la caída de presión de 10 psi de que dispone, permite el paso de 500 gpm; la constante de tiempo del actuador de la válvula es de 5 s. Para completar el diseño se pueden requerir más instrumentos, por lo que se invita al estudiante a utilizar cualquier cosa que se necesite. Se debe especificar la acción de la válvula de control y del controlador.
b) Se debe dibujar el diagrama de bloques de circuito cerrado y obtener la función de transferencia de cada bloque. La respuesta del absorbedor se aproxima con un modelo de primer orden más tiempo muerto, con el método de cálculo 3. Se debe obtener la ganancia y el período últimos del circuito. El tiempo muerto del sistema se puede aproximar con una aproximación de Padé de primer orden, ecuación (6-29).
c) Se debe ajustar un controlador proporcional para una respuesta de razón de asentamiento de un cuarto y obtener la desviación cuando se cambia el punto de control a 60 ppm.
d) Repetir la parte c) para un controlador PID.

**6-17.** En este problema se considera el horno mostrado en la figura 6-32, el cual se utiliza para calentar el aire que se suministra a un regenerador catalítico. El transmisor de temperatura se calibra a 300-500°F. Para un cambio escalón del 5% en la salida del controlador se obtuvieron los siguientes datos de respuesta:

| Tiempo, min | T(t), °F | Tiempo, min | T(t), °F |
|-------------|----------|-------------|----------|
| 0 | 425 | 5.5 | 436.6 |
| 0.5 | 425 | 6.0 | 437.6 |
| 1.0 | 425 | 7.0 | 439.4 |
| 2.0 | 425 | 8.0 | 440.7 |
| 2.5 | 426.4 | 9.0 | 441.7 |
| 3.0 | 428.5 | 10.0 | 442.5 |
| 3.5 | 430.6 | 11.0 | 443.0 |
| 4.0 | 432.4 | 12.0 | 443.5 |
| 4.5 | 434.0 | 14.0 | 444.1 |
| 5.0 | 435.3 | 16.0 | 444.5 |
| | | 19.0 | 445.0 |

a) Se debe especificar la acción del controlador.
b) Dibujar el diagrama de bloques completo con la especificación de unidades para cada señal desde/hacia cada bloque. Se tiene que identificar a cada bloque.
c) Se deben adecuar los datos del proceso mediante un modelo de primer orden más tiempo muerto con el método de cálculo 3; dibujar también el diagrama de bloques donde se ilustre la función de transferencia de cada bloque.
d) Ajustar el controlador proporcional para una respuesta de razón de asentamiento de un cuarto y obtener la desviación para un cambio escalón de +5°F en el punto de control.
e) Se debe ajustar un controlador PI, con el método de síntesis de un controlador, para un sobrepaso del 5%.

**6-18.** El tanque de almacenamiento de la figura 6-33 se utiliza para suministrar a dos procesos un gas con peso molecular de 50. En el primer proceso se recibe un flujo normal de 500 scfm y se opera con una presión de 30 psig; mientras que en el segundo se opera con una presión de 15 psig. El gas que llega al tanque de almacenamiento lo proporciona un proceso en el que se opera a 90 psig, y se envía al tanque a una razón de 1500 scfm; la capacidad del tanque es de 550,000 pies³ y opera a 45 psig y 350°F. Se puede suponer que el transmisor de presión responde instantáneamente con una calibración de 0-100 psig.

a) Se deben dimensionar las tres válvulas con una sobrecapacidad de 50%. Para todas las válvulas se puede utilizar el factor $C_f = 0.9$ (Masoneilan).
b) Se debe dibujar completo el diagrama de bloques del sistema. Se pueden considerar como perturbaciones $P_1(t)$, $P_3(t)$, $P_4(t)$, $vp_2(t)$ y el punto de control del controlador. La constante de tiempo de la válvula de control de presión es de 5 seg.
c) ¿Se puede volver inestable el circuito de retroalimentación? En caso afirmativo, ¿cuál es su ganancia última?
d) Si se utiliza un controlador proporcional con una ganancia de 50 %/%, ¿cuál es la desviación que se tiene con un cambio de +5 psi en el punto de control?

**6-19.** Ahora se considera el sistema de reacción química que se muestra en la figura 6-34. Dentro de los tubos de reacción tiene lugar la reacción catalítica exotérmica A + E → C + D. El reactor se enfría con una corriente de aceite que fluye a través del casquillo del reactor; en cuanto el aceite sale del reactor, se le envía a un hervidor, donde se le enfría mediante la producción de vapor a baja presión. La temperatura en el reactor se controla mediante el manejo del flujo que no pasa por el hervidor.

Se conocen las siguientes condiciones del proceso:

- Temperatura de diseño del reactor en el punto de medición: 275°F
- Flujo de aceite que puede entregar la bomba: 400 gpm (constante)
- Válvula de control de temperatura: caída de presión en las condiciones de diseño: 15 psi
- Flujo a las condiciones de diseño: 200 gpm
- Rango del transmisor de temperatura: 100-400°F
- Densidad del aceite: 55 lbm/pies³

Prueba a circuito abierto: a un decremento de 5% en la posición de la válvula corresponde un cambio de temperatura de -3°F, después de un lapso muy largo.

Prueba de circuito cerrado: con una ganancia del controlador de 7 mA/mA, el circuito de temperatura empieza a oscilar con una amplitud constante y un período de 15 min.

a) La válvula de control de temperatura se debe dimensionar con una sobrecapacidad del 100%. ¿Cuáles son las acciones de la válvula y el controlador que se recomiendan para el circuito de temperatura?
b) Si la caída de presión a través de los tubos del hervidor varía con el cuadrado del flujo, y la válvula es de porcentaje igual con un parámetro de ajuste en rango de 50, ¿cuál es el flujo a través de la válvula cuando se abre completamente? ¿Cuál es la posición de la válvula en las condiciones de diseño?
c) Se debe dibujar el diagrama general de bloques para el circuito de temperatura.
d) Se debe calcular la ganancia del proceso, a las condiciones de diseño, incluyendo la válvula de control y el transmisor de temperatura.
e) Calcular los parámetros de ajuste de un controlador PID para la respuesta de asentamiento de un cuarto. Se deben escribir los parámetros como banda proporcional, repeticiones/minuto y minutos.
f) Se debe ajustar un controlador proporcional para una respuesta de asentamiento de un cuarto y calcular la desviación para un cambio escalón en el punto de control de -10°F.

**6-20.** Ahora se considerará el sistema de control típico para el evaporador de doble efecto que se ilustra en la figura 6-35, estos sistemas de evaporación se caracterizan por su dinámica lenta. La concentración que resulta del efecto final se controla mediante el control del ascenso del punto de ebullición (APE) (BPR por sus siglas en inglés); es decir, al mantener el APE a un cierto valor, la concentración a la salida se mantiene al valor que se desea. Mientras más alta es la concentración del soluto más alto es el APE. El APE se controla mediante el manejo del vapor que entra al primer efecto.

Se dispone de datos de la prueba escalón. En la figura 6-36 se ilustra la respuesta del APE a un cambio de 2.5 lbm/pies³ en la densidad de la solución que entra al primer efecto. En la figura 6-37 se muestra la respuesta del APE para un cambio de +2 psig en la salida del controlador.

El rango del transmisor de APE es de 150-250°F, y la constante de tiempo de 5 s.

a) Se debe dibujar el diagrama de bloques completo, con la función de transferencia de cada bloque.
b) Con base en los datos que se proporcionan, ¿cuál es la acción de la válvula de control en caso de falla? ¿Cuál es la acción correcta del controlador?
c) Se debe ajustar un controlador proporcional para una respuesta de razón de asentamiento de un cuarto y calcular la desviación cuando la densidad de la solución que entra cambia en +2 lbm/pies³.
d) Mediante el método de síntesis del controlador, se debe ajustar un controlador PI para un sobrepaso del 5%.

**6-21.** La temperatura en un tanque de reacción química exotérmica con agitación continua se controla mediante la manipulación de la cantidad de agua para enfriamiento que pasa por el serpentín, tal como se ilustra en la figura 6-38.

Las condiciones de diseño del proceso son las siguientes:

- Temperatura del reactor: 210°F
- Razón de agua para enfriamiento: 350 gal/min
- Caída de presión en el serpentín: 10 psi
- Rango de temperatura del transmisor: 180-230°F
- Características de la válvula: de porcentaje igual, con un parámetro de ajuste de rangos de 50; se requiere aire para cerrar.

Se realizaron las siguientes pruebas en el sistema:

- Sensibilidad de circuito abierto: con un incremento de 10 gal/min en la razón de entrada de agua se obtiene una caída de temperatura de 3°F, después de un lapso largo.
- Prueba de circuito cerrado: con una ganancia del controlador de 5, la temperatura oscila con amplitud constante y período de 12 min.

a) Se debe determinar el coeficiente de la válvula, $C_V$, para un factor de sobrecapacidad de 2.
b) Dibujar el diagrama de bloques para el lazo de control y determinar la ganancia total del proceso; se deben incluir el controlador y la válvula de control.
c) Se deben calcular los parámetros para ajustar un controlador PID a una respuesta de razón de asentamiento de un cuarto; se deben expresar como banda proporcional, repeticiones/minuto y minutos de derivación. ¿Cuál es la acción que se requiere del controlador?

**6-22.** Ahora se considera el proceso que se muestra en la figura 6-39, para sacar granulado de fosfato. La mezcla de granulado y agua se alimenta a la cama del secador mediante una banda alimentadora; en la cama se seca el granulado mediante el contacto directo con gases en combustión. Del secador se lleva el granulado a un silo para su almacenamiento; es muy importante el control de la humedad del granulado que sale del secador; si el granulado está muy seco se puede quebrar y pulverizar, de lo cual resultaría una pérdida de material; si está muy húmedo, se formarían terrones en el silo.

Para controlar la humedad del granulado se propone regular la velocidad de la banda de alimentación, como se muestra en la figura 6-39. La velocidad del alimentador es directamente proporcional a su señal de entrada. La humedad del granulado que entra es generalmente del 14%, y en el secador se reduce al 3%. El rango del transmisor es de 1-6% de humedad. Una perturbación importante en este proceso es la humedad del granulado de entrada.

a) Se debe dibujar el diagrama de bloques completo del circuito de control, con la ilustración de todas las unidades. Se deben incluir las perturbaciones.
b) En la figura 6-40 se ilustra la respuesta de la humedad de salida a un incremento de 1 mA en la salida del controlador; en la figura 6-41 se muestra la respuesta de la humedad de salida a un incremento del 2% en la humedad de entrada.

Se debe hacer una aproximación a cada curva de proceso, mediante un modelo de primer orden más tiempo muerto, y redibujar el diagrama a bloques con las funciones de transferencia de estos modelos de aproximación. Se debe utilizar el método de cálculo 2.

c) Se debe determinar el ajuste de un controlador PID para respuesta de ICE mínima a la entrada de disturbios. La ganancia del controlador se debe expresar en banda proporcional. ¿Cuál es la acción adecuada del controlador?
d) Se debe determinar la ganancia última y el período último del lazo, mediante la utilización de una aproximación Padé de primer orden para el tiempo muerto.
e) Si la humedad del granulado a la entrada desciende en un 2%, ¿cuál es el nuevo valor de estado estacionario de la humedad a la salida? Se supone que el controlador es proporcional con ajuste para respuesta de razón de asentamiento de un cuarto, con base en la información que se obtiene en la parte d).
f) ¿Cuál es la salida del controlador que se requiere (en mA) para evitar la desviación a causa de la perturbación de la parte e)?

Nota: En los siguientes problemas se requiere que el estudiante elabore el modelo del proceso a partir de los principios básicos. Estos problemas son más adecuados para proyectos de fin de curso que para tareas regulares.

**6-23.** Ahora se utiliza el calentador eléctrico que se ilustra en la figura 6-42. En una "te" se unen dos corrientes de líquido con razón de masa variable, $F_A(t)$ y $F_B(t)$, y que pasan a través del calentador en donde se mezclan completamente y se calientan a la temperatura $T(t)$. La temperatura de salida se controla mediante el manejo de la corriente que pasa por una bobina eléctrica. La fracción de masa del componente B en la salida también se controla mediante el manejo del flujo de entrada de la corriente B. Se conoce la siguiente información:

1. La caída de presión a través de las válvulas se puede suponer constante, de manera que el flujo a través de las válvulas se expresa por:
$$F_A(t) = K_{v1}vp_1(t)$$
$$F_B(t) = K_{v2}vp_2(t)$$

Cada una de las dos corrientes es pura en componente A o B, respectivamente.

2. La manera más fácil de controlar la composición en la salida, la fracción de masa de B, es medir la conductividad eléctrica de la corriente que sale. La conductividad de la corriente es inversamente proporcional a la fracción de masa, $x_B$, es decir:
$$\text{conductividad} = \frac{\alpha}{x_B}$$
donde $\alpha$ es una constante, mho-fracción de masa/m.

El rango del transmisor de conductividad es de $C_L$ a $C_H$ mho/m.

3. El calentador siempre está lleno de líquido. En todo momento el caudal de salida es igual al de entrada.

4. La capacidad calorífica y la densidad son constantes.

5. Se puede suponer que el calor que se transfiere, $q$, es directamente proporcional a la salida del controlador. Para una salida de 4 mA, $q = 0$; para 20 mA, $q = q_{max}$.

6. El calentador está bien aislado.

7. Las perturbaciones de este sistema son $vp_1(t)$, $T_i(t)$ y $T_A(t)$.

Se debe hacer lo siguiente:

a) Obtener la acción del controlador de conductividad, si se supone que la válvula de control es de aire para abrir. También se debe obtener la acción del controlador de temperatura.
b) Deducir, a partir de los principios básicos, el sistema de ecuaciones con que se describe al circuito de control de la composición (conductividad).
c) Linealizar las ecuaciones de la parte b) y dibujar completo el diagrama de bloques del lazo de conductividad; se debe anotar la función de transferencia de cada bloque.
d) Deducir, a partir de los principios básicos, el sistema de ecuaciones con que se describe al circuito de control de temperatura.
e) Linealizar las ecuaciones de la parte d) y dibujar el diagrama de bloques completo para el circuito de temperatura; se debe mostrar la función de transferencia de cada bloque.
f) Escribir la ecuación característica de cada lazo de control. ¿Se puede hacer inestable al lazo mediante el incremento de la ganancia del controlador? Se debe hacer una exposición breve al respecto.

**6-24.** Ahora se debe considerar el sistema que se muestra en la figura 6-43. En cada uno de los dos tanques tiene lugar la reacción A → B y la razón de reacción se expresa con:
$$r(t) = k_iC_A(t), \quad \frac{lb\ mol}{gal-min}$$
donde:
- $k_i$ es el coeficiente de la razón de reacción, min$^{-1}$
- $C_A(t)$ es la concentración, lb mol/gal

En este proceso las perturbaciones son $q_i(t)$ y $C_{A_i}(t)$. La concentración que sale del segundo reactor se controla mediante el manejo de la corriente de A pura que llega al primer reactor. La densidad de esta corriente es $\rho_A$ en lb mol/gal.

En el primer reactor el nivel es constante, ya que la corriente de salida se forma por desborde. Se puede suponer que el nivel en el segundo reactor también es constante (control perfecto de nivel) y, por tanto, se ignora el circuito de control de nivel. La temperatura en cada reactor se puede suponer constante.

**DATOS:**
- Volumen de los reactores, gal: $V_1 = 500$, $V_2 = 500$
- Coeficientes de la tasa de reacción, min$^{-1}$: $k_1 = 0.25$, $k_2 = 0.50$
- Propiedades de la corriente A: $\rho_A = 2.0$ lb mol/gal, $MW_A = 25$
- Condiciones de diseño: $C_{A_i} = 0.8$ lb mol/gal; $\bar{q}_i = 50$ gal/min; $\bar{q}_A = 50$ gal/min
- Válvula de control: $\Delta P = 10$ psi (constante). Características lineales.
- El transmisor de concentración tiene un rango de 0.05-0.5 lb mol/gal. La dinámica de este transmisor se puede representar con un retardo de segundo orden cuyas constantes son 0.5 min y 0.25 min.

a) Se debe dimensionar la válvula de control para manejar un caudal del doble de la razón nominal.
b) Se debe deducir, a partir de los principios básicos, el sistema de ecuaciones con que se describe el circuito de control de composición. Se deben exponer todas las suposiciones que se hacen durante la deducción.
c) Se han de linealizar las ecuaciones de la parte b) y dibujar completo el diagrama de bloques del circuito de control de composición. Se deben anotar los valores numéricos y las unidades de todas las ganancias y constantes de tiempo, excepto los del controlador.
d) Se deben obtener las funciones de transferencia de circuito cerrado.
e) Se debe determinar la ganancia y frecuencia últimas del circuito de control y los parámetros de un controlador PID que se ajusta para una respuesta de razón de asentamiento de un cuarto.

**6-25.** Ahora se considera el proceso que se muestra en la figura 6-44. En el primer tanque se mezclan y calientan las corrientes $q_1(t)$ y $q_2(t)$. El medio de calefacción fluye a una razón tan alta que el cambio de temperatura entre la entrada y la salida no es significativo y, por lo tanto, la razón de transferencia de calor se puede describir mediante $UA[T_s(t) - T_1(t)]$. También se puede suponer que el caudal de entrada es igual al de salida (total) y que las densidades y capacidades caloríficas de todas las corrientes son funciones que no dependen demasiado de la temperatura o de la composición.

El caudal que sale del primer tanque entra al segundo tanque, donde se calienta nuevamente, en esta ocasión mediante condensación de vapor. La energía que gana el líquido que se procesa es igual a la que pierde el vapor que se condensa y, por lo tanto, la razón de transferencia de calor se puede describir con $w_s(t)\lambda$, donde $w_s(t)$ es la razón de flujo de masa de vapor y $\lambda$ es el calor latente de la vaporización. Si se supone que la caída de presión en la válvula de vapor es constante, el flujo a través de esta válvula se puede describir como $w_s(t) = K_vvp(t)$; la constante de tiempo de dicha válvula es $\tau_v$.

El rango del transmisor de temperatura es $T_L - T_H$, con una constante de tiempo $\tau_T$.

Si se supone que las pérdidas de calor en ambos tanques son despreciables, y que las perturbaciones importantes son $T_1(t)$, $T_2(t)$, $T_i(t)$ y $q_1(t)$, se debe obtener el diagrama de bloques completo para el circuito de control de temperatura, así como su ecuación característica. En cada bloque se debe anotar la función de transferencia correspondiente.

**6-26.** Ahora se considera el proceso que se muestra en la figura 6-45. El fluido en proceso que entra al tanque es un aceite con densidad de 53 lbm/pies³, capacidad calorífica de 0.45 Btu/lbm-°F y temperatura de entrada de 70°F. El aceite se debe calentar a 200°F, mediante vapor que se suministra a 115 psig. En el tanque se mantiene la presión a 40 psia, encima del nivel del aceite, mediante una capa de gas inerte, N₂.

Se puede suponer que el aislamiento del tanque es bueno; que las propiedades físicas del aceite no son funciones que dependan demasiado de la temperatura; que la mezcla del líquido es buena, y que el nivel está por arriba del serpentín de calefacción. También se conocen los siguientes datos:

- $P_1 = 45$ psig
- $P_3 = 15$ psig
- $h_i$ del lado del vapor = 1500 Btu/h-pies²-°F
- $h_o$ en el lado del aceite = 150 Btu/h-pies²-°F
- Área de la superficie calefactora = 127.5 pies²
- Serpentín calefactor: ½ pulg DE, tubos 20 BWG, 974 pies lineales y con espesor de pared 0.035 pulg.
- Densidad del tubo = 500 lbm/pies³
- $C_{p,tubo} = 0.12$ Btu/lbm-°F
- Diámetro del tanque: 3 pies
- Transmisor de nivel: Rango: 7-10 pies; Constante de tiempo: 0.01 min
- Transmisor de temperatura: Rango: 100-300°F; Constante de tiempo: 0.5 min

a) Las válvulas 1 y 2 se dimensionarán con un factor de sobrecapacidad del 50%; el flujo nominal de aceite es de 100 gpm. La válvula 3, de vapor, se dimensionará con un factor de sobrecapacidad del 50%; se puede suponer que la caída de presión a través de esta válvula es constante.
b) Se debe elaborar el diagrama completo de bloques para el circuito de control de nivel. Se debe utilizar un controlador proporcional.
c) Elaborar el diagrama completo de bloques y obtener la ecuación característica del circuito de control de temperatura. Se debe utilizar un controlador PID y anotar los valores numéricos de todas las ganancias y constantes de tiempo en las funciones de transferencia.

**6-27.** Para este problema se considera el proceso que se muestra en la figura 6-46. Se dispone de la siguiente información:

1. La densidad del líquido es constante.
2. Las dos válvulas de salida permanecen con una abertura constante, y la presión de la corriente también es constante.
3. El caudal de la bomba se expresa por:
$$q_1(t) = q_{max}(1 - e^{-t/\tau_1})$$
4. La bomba de velocidad variable tiene una constante de tiempo en la que se relaciona el caudal con la señal de entrada, $m_1(t)$, de $\tau_p$ s.
5. La válvula de control es lineal y mediante su constante de tiempo se relaciona el caudal con la señal neumática, de $\tau_v$ s. La caída de presión a través de la válvula de control es constante.
6. Los diámetros de los tanques son $D_1$ y $D_2$.
7. Los coeficientes de las válvulas son $C_{v1}$, $C_{v2}$ y $C_{v3}$.
8. El rango del transmisor de nivel es $\Delta h$ y la constante de tiempo es despreciable.

a) Se debe obtener el diagrama de bloques, con las funciones de transferencia correspondientes, para este sistema de control. Las perturbaciones son $q_1(t)$ y $q_2(t)$.
b) Se debe escribir la ecuación característica del circuito de control de nivel y determinar la ganancia y período últimos en función de los parámetros del sistema.

**6-28.** Ahora se considera el proceso que aparece en la figura 6-47. En este proceso se enriquece un gas de desecho con gas natural para su utilización como combustible en un horno pequeño. El gas enriquecido debe tener un cierto valor de calefacción a fin de poder utilizarlo como combustible; por tanto, para la estrategia de control se necesita medir el valor de calefacción del gas que sale del proceso y manejar el flujo del gas natural (con un ventilador de velocidad variable) con la finalidad de mantener el valor de calefacción en el punto de control.

El gas de desecho se compone de metano (CH₄) y algunos combustibles con bajo valor calórico. La composición del gas natural se puede considerar constante y lo constituyen principalmente metano y pequeñas cantidades de otros hidrocarburos. El valor calórico del gas de desecho enriquecido está en relación con la fracción molar del metano, lo cual se expresa mediante la relación:
$$h(t) = c + dx_3(t)$$
donde:
- $h(t)$ es el valor calórico
- $x_3$ es la fracción molar de metano
- $c$, $d$ son constantes

El ventilador de velocidad variable es de naturaleza tal que, a toda velocidad, el flujo es de $q_{2max}$. Se puede suponer que la relación entre el flujo y la señal que entra al conductor del ventilador es lineal; la constante de tiempo del conductor es $T_F$.

La abertura de la válvula de salida es constante y se puede utilizar una ecuación de válvulas Masoneilan para describir el flujo a través de esta válvula. Para controlar el valor calórico se utiliza un controlador proporcional-integral. La constante de tiempo del sensor-transmisor es de $\tau_T$ min.

La relación entre la gravedad específica del gas enriquecido y la fracción molar de metano se establece mediante:
$$G(t) = a + bx_3(t)$$
donde $a$ y $b$ son constantes.

a) Se debe determinar el diagrama de bloques completo para este sistema de control; en el mismo se anotarán todas las funciones de transferencia. Las perturbaciones posibles son $q_1(t)$, $x_1(t)$ y $x_2(t)$.
b) Se debe escribir la ecuación característica del circuito de retroalimentación de control.
c) Se debe determinar la ganancia última y el período de oscilación del circuito (si es que existen).

---

*Continúa en la Parte 3: Capítulos 7-9 y Apéndices*
