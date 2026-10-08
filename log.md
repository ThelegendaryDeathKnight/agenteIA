# LOG.md — Registro de conversaciones, decisiones y contexto de proyectos

> **Propósito:** conservar de forma estructurada el contexto técnico, académico, económico y de diseño proporcionado en las conversaciones, para poder reutilizarlo posteriormente con otros LLM.
>
> **Criterio:** este documento registra el contenido proporcionado. No se han añadido datos externos para completar vacíos ni se han corregido silenciosamente afirmaciones técnicas existentes.

---

# 1. Contexto general

Este registro reúne conversaciones relacionadas principalmente con:

- Instrumentación industrial.
- Sistemas automáticos de control.
- Electrónica industrial.
- Diseño de sistemas con ESP32.
- Sensores y acondicionamiento de señales.
- Control de motores.
- Bandas transportadoras inteligentes.
- Clasificación automatizada.
- HMI.
- Proyectos de invernadero.
- Circuitos integrados y amplificadores operacionales.
- Compra, venta y valoración de componentes electrónicos.
- Documentación técnica en Markdown y LaTeX.

El objetivo del registro es mantener la continuidad del trabajo y permitir que un LLM posterior pueda comprender decisiones anteriores, componentes seleccionados, alternativas descartadas, reglas de control, requisitos académicos y contexto económico.

---

# 2. Proyecto: Banda transportadora inteligente con clasificación automatizada

## 2.1 Identificación del proyecto

**Nombre:**

> Banda Transportadora Inteligente con Clasificación Automatizada

**Propuesta:**

> Control + Instrumentación — Grupo 2

**Integrantes:**

- Juan Camilo Valenzuela
- Stiven Flórez Quiñonez
- Cristian David Villegas Diaz
- William Salazar Ruiz
- Angel Leandro

**Docente de Control:**

- José David Chiza Ocaña

**Docente de Instrumentación:**

- María Elena Leyes Sánchez

**Asignaturas:**

- Sistemas Automáticos de Control
- Instrumentación Industrial-50

**Fecha indicada:**

- 16 de septiembre de 2026

---

## 2.2 Objetivo

Construir a pequeña escala una banda transportadora inteligente que detecte, mida, clasifique y desvíe cajas de cartón mediante sensores económicos, control en lazo cerrado y panel HMI táctil, sin modificar el sistema de rodamiento ni la tela de la banda.

La propuesta integra los requisitos de control con los cambios de instrumentación exigidos por el curso.

---

# 3. Configuración física de la banda

Se plantearon dos opciones de banda transportadora.

La selección final queda a decisión de las docentes.

## 3.1 Opción 1 — Banda metálica 70 × 10 cm

- Dimensiones: 70 cm × 10 cm.
- Salidas:
  - 2 bifurcaciones laterales.
  - 1 salida central.

## 3.2 Opción 2 — Banda metálica 100 × 10 cm

- Dimensiones: 100 cm × 10 cm.
- Salidas:
  - 1 bifurcación lateral.
  - 1 salida central.

## 3.3 Imágenes mencionadas

- `bandametalica70x10_100x10cm.png`
- `bandapropuesta.png`

La segunda imagen representa la propuesta de bifurcaciones laterales y salida central.

---

# 4. Sensores y actuadores fijos de la banda

Independientemente de la opción de banda seleccionada, se estableció incluir:

- Sensores infrarrojos de posición.
- Servos para topes y compuertas de desvío.
- Sensor de color para clasificación.
- Sensor ultrasónico para medición de altura.

---

# 5. Arquitectura de control y comunicación

## 5.1 ESP32 de control

Funciones:

- Leer sensores:
  - IR.
  - Color.
  - Ultrasónico.
  - Corriente.
  - Encoder.
- Ejecutar el control de velocidad.
- Accionar el driver del motor.
- Accionar servos.

## 5.2 ESP32 con pantalla TFT táctil

Funciones HMI:

- Mostrar métricas.
- Inicio.
- Pausa.
- Parada de emergencia.
- Cambio de modo.
- Mostrar alarmas.
- Supervisar el proceso.

## 5.3 Comunicación

Se contemplaron:

- UART.
- ESP-NOW.

La comunicación utilizará tramas simples y periódicas.

---

# 6. Reglas de control aprobadas

Se establecieron dos rutas posibles de control dependiendo del motor utilizado.

---

## 6.1 Regla 1 — Control por corriente

### Aplicación

Se utiliza cuando se conserva el motor original de la banda, es decir, un motor sin encoder.

### Funcionamiento

- Se regula el PWM aplicado al motor para ajustar la velocidad de la banda.
- Se mide la corriente del motor.
- La corriente se utiliza para detectar:
  - Carga.
  - Atascos.
- Si la corriente supera un umbral:
  - Se reduce el PWM, o
  - Se detiene el motor.
- No existe un lazo cerrado de velocidad.
- Se utiliza protección por corriente y control proporcional básico.

---

## 6.2 Regla 2 — Control con encoder + PID + feedforward por corriente

### Aplicación

Se utiliza cuando se cambia el motor por uno con encoder.

Motores considerados:

- JGA25-370.
- JGB37-520.

### Funcionamiento

- El encoder entrega la velocidad real.
- El ESP32 calcula el error respecto a la referencia.
- El PID ajusta el PWM del driver.
- La corriente del motor se utiliza como feedforward.
- Si aumenta la carga y aumenta la corriente, se puede aumentar el PWM antes de que la velocidad caiga.
- La corriente también se utiliza para detectar atascos.

---

# 7. Velocidad de trabajo

Velocidad lineal deseada:

> Aproximadamente 50 mm/s.

Con:

- Polea: 25 mm.
- Motor: 130 RPM.

Se registró la relación:

\[
v = \frac{RPM \cdot \pi \cdot D}{60}
\]

Con el cálculo indicado:

\[
v \approx 170\text{ mm/s}
\]

Para obtener aproximadamente 50 mm/s:

- Duty cycle aproximado: 29 %.
- Se busca conservar torque y evitar sobrecalentamiento.

---

# 8. Sintonización del PID

La sintonización se planteó como empírica mediante:

- Ziegler-Nichols.
- Prueba y error.

Parámetros:

### Kp

Proporcional a la inercia del sistema según la descripción proporcionada.

### Ki

Integral lenta para eliminar error en estado estable.

### Kd

Derivativo pequeño para amortiguar sobreimpulsos.

### Anti-windup

Se estableció implementar anti-windup en el integrador para evitar saturación cuando el PWM llegue al 100 %.

---

# 9. Detección de atascos

La lógica propuesta es:

1. Calibrar la corriente del motor.
2. Establecer un umbral.
3. Comparar la corriente medida contra dicho umbral.
4. Si la corriente supera el límite:
   - detener el motor;
   - activar una alarma en el HMI.

El umbral debe ajustarse según la corriente nominal del motor con carga máxima.

---

# 10. Máquina de estados

La secuencia definida contempla los siguientes estados:

1. **Reposo**
   - Espera la detección de una caja.

2. **Avance**
   - La banda funciona a velocidad nominal.

3. **Detección**
   - Un sensor IR confirma presencia y posición.

4. **Medición de color**
   - Un tope detiene la caja.
   - El sensor de color realiza la lectura.

5. **Desvío por color**
   - Un servo activa la compuerta correspondiente.

6. **Medición de altura**
   - Un tope detiene la caja.
   - El sensor ultrasónico mide la altura.

7. **Desvío por altura**
   - Un servo activa una segunda compuerta si corresponde.

8. **Salida**
   - Se libera la caja.
   - Se actualiza el conteo.

Los sensores IR confirman la posición de cada caja antes de ejecutar las acciones.

---

# 11. Modos de operación y HMI

## Modo 1 — Control por corriente

Aplicación:

- Motor original.
- Sin encoder.

## Modo 2 — Control de velocidad y torque

Aplicación:

- Motor cambiado.
- Encoder.
- PID.
- Feedforward por corriente.

## Información mostrada en HMI

- Velocidad.
- Corriente.
- Contadores por tipo de caja.
- Estado de topes.
- Alarmas.

## Controles HMI

- Inicio.
- Pausa.
- Parada de emergencia.
- Cambio de modo.

---

# 12. Secuencia de operación

1. Ingreso de la caja a la banda.
2. Sensores IR detectan presencia y posición.
3. Estación de color clasifica.
4. Se activa el primer desvío.
5. Las cajas restantes avanzan a la estación ultrasónica.
6. Se realiza el segundo desvío según altura cuando la configuración lo contempla.
7. El sensor de corriente realimenta el control y detecta atascos.
8. El HMI recibe las métricas y permite supervisión.

---

# 13. Cambios de instrumentación

## 13.1 Fuente principal y regulación

Fuente principal:

- 24 V / 10 A.

Regulador recomendado:

- Mini560.
- Capacidad indicada: 4–5 A.

Distribución planteada:

| Tensión | Aplicación |
|---|---|
| 12 V | Motor + BTS7960 |
| 9 V | Servos |
| 5 V | ESP32 + sensores |

Alternativas:

- XL4015.
- XL4016.
- LM2596 para lógica/sensores.

Regla de instalación:

> Todos los GND deben estar en común para evitar errores de lectura.

---

# 14. Cambio de driver: L298N → BTS7960

Se estableció sustituir:

> L298N → BTS7960

Justificación registrada:

- El L298N se describió como limitado a aproximadamente 2 A por canal.
- Presenta una caída de tensión aproximada de 2 V según el contexto proporcionado.
- Esa caída reduce el torque y genera calor.
- El BTS7960 fue seleccionado por su mayor capacidad de corriente indicada y menor caída de tensión.
- Se busca mejorar eficiencia y reducir calentamiento.

El BTS7960 se integra con:

- Motor original.
- Motor con encoder.
- Sensor de corriente.
- ESP32.

Control:

- PWM.
- Dirección desde ESP32.

Debe considerarse que las cifras nominales de corriente de módulos comerciales dependen del diseño concreto, disipación y condiciones de operación; este punto queda registrado como dato de diseño a verificar antes del montaje físico.

---

# 15. Sensor de corriente

Cambio planteado:

> ACS712 → ACS758

## ACS758

Configuración mencionada:

- 50 A.
- Se considera robusto.
- Uso previsto: medición de corriente del motor.
- Se contempla para trabajar en un rango aproximado de 8–10 A del sistema.

## Alternativa

> INA219 con shunt modificado.

Ventajas planteadas:

- Corriente.
- Voltaje.
- Potencia.

---

# 16. Sensores de posición

Cambio:

> IR básicos → E18-D80NK

Características buscadas:

- Mejor estabilidad.
- Menor interferencia por luz ambiente.
- Salida mediante comparador LM393.

Uso:

- Detección de presencia.
- Confirmación de posición de cajas.

---

# 17. Sensor de color

Cambio:

> Módulo genérico → TCS34725

Interfaz:

- I2C.

Motivo de selección indicado:

- Mayor precisión.
- Menor afectación por iluminación externa.

Uso:

- Clasificación de cajas por color.

---

# 18. Sensor de altura

Cambio:

> HC-SR04 → JSN-SR04T

Características registradas:

- Sensor ultrasónico.
- Resistente a polvo y humedad.
- Rango indicado: 25–450 cm.
- Precisión indicada en el contexto: ±0.3 mm.

Uso:

- Medición de altura de cajas.

Los parámetros exactos deben verificarse contra la versión concreta del sensor antes de documentarlos como especificaciones finales.

---

# 19. Encoder opcional

Se añadirá encoder si se cambia el motor.

Motores considerados:

- JGA25-370.
- JGB37-520.

Objetivo:

- Medir velocidad real.
- Permitir control PID.
- Mejorar estabilidad de velocidad.

---

# 20. Calibración

Se establecieron cuatro elementos principales de calibración:

### ACS758

- Determinar/calibrar umbral de corriente nominal del motor.

### TCS34725

- Utilizar muestras reales de las cajas.

### JSN-SR04T

- Determinar distancia mínima y máxima según las alturas reales de las cajas.

### E18-D80NK

- Ajustar sensibilidad mediante su potenciómetro.

---

# 21. Reglas generales de control e instrumentación

## Seguridad

Limitar:

- Corriente.
- Voltaje.
- Temperatura.

Además:

- Detectar atascos.
- Detener el motor ante sobrecorriente.
- Incorporar parada de emergencia en HMI.

## Estabilidad

- Retroalimentación constante mediante sensores.
- PID cuando se utilice encoder.

## Eficiencia

- Ajustar actuadores únicamente cuando sea necesario.
- Evitar sobreconsumo y calentamiento.

## Prioridad

Debe definirse una variable crítica.

Ejemplo establecido:

> Velocidad.

## Documentación

Registrar:

- Parámetros.
- Calibraciones.
- Cambios de diseño.
- Resultados de pruebas.

---

# 22. Resultados de aprendizaje cubiertos

## RA1 — Conceptos metrológicos

Medición de:

- Corriente.
- Voltaje.
- Altura.
- Color.

## RA2 — Selección de instrumentos

Justificación técnica de:

- Sensores.
- Reguladores.
- Driver.

## RA3 — Calibración y verificación

- Curvas de calibración.
- Incertidumbre.

## RA4 — Documentación del lazo

- P&ID.
- Norma ISA 5.1.
- Potencia.
- Sensores.

## RA5 — Control y protección

- Detección de atascos.
- Protección por corriente.
- PID.

---

# 23. Documentación requerida

Se estableció como documentación del proyecto:

- Calibración básica.
- P&ID simplificado.
- Registro de parámetros.
- Registro de calibraciones.
- Documentación del lazo de control.
- Resultados de pruebas.

---

# 24. Conclusión registrada del proyecto de banda

La propuesta integra las reglas de control aprobadas con los cambios de instrumentación requeridos.

Las dos opciones de banda permiten montar:

- Sensores IR.
- Servos.
- Sensor de color.
- Sensor ultrasónico.

El control puede realizarse mediante:

### Alternativa A

Motor original:

> Control por corriente.

### Alternativa B

Motor cambiado:

> Encoder + PID + feedforward por corriente.

Cambios de instrumentación principales:

- Mini560.
- BTS7960 en lugar de L298N.
- ACS758.
- E18-D80NK.
- TCS34725.
- JSN-SR04T.
- Encoder opcional.
- Calibración.

Estos cambios fueron planteados para cubrir los RA1 a RA5.

---

# 25. Proyecto alternativo/inicial: sistema de monitoreo y control de invernadero

## 25.1 Idea inicial

Combinar:

- Instrumentación Industrial.
- Circuitos Integrados.

Objetivo:

Desarrollar un sistema de monitoreo y control de un invernadero.

Variables principales:

- Temperatura del aire.
- Temperatura del suelo.
- Humedad del suelo.

Actuadores:

- Bomba de riego.
- Ventilador.

---

# 26. Evolución del proyecto de invernadero

Se evaluaron diferentes tecnologías:

- RTD.
- NTC.
- Termopar.
- Galgas.
- LDR.
- LVDT.

Se optó por:

> Sistema analógico simple.

Referencias académicas mencionadas:

- Boylestad — Circuitos Integrados.
- Avendaño — Instrumentación Industrial.

Decisiones:

- Simplificar los circuitos.
- Evitar puentes de Wheatstone complejos.
- Evitar amplificadores de instrumentación complejos.
- Descartar módulo microSD por problemas de compatibilidad.
- Eliminar cronograma debido al tiempo disponible.
- Mantener seis semanas como restricción temporal indicada.
- Utilizar el ESP32 principalmente como ADC y controlador lógico.
- Mantener la cadena analógica como núcleo del proyecto.

---

# 27. Sensores del proyecto de invernadero

| Variable | Sensor | Tipo de salida | Acondicionamiento |
|---|---|---|---|
| Temperatura del aire | LM335 | Analógica, 10 mV/K | Amplificador no inversor con LM324, ganancia aproximada 10 → 100 mV/°C |
| Humedad del suelo | Sensor capacitivo | Analógica, 0–3 V | Seguidor de tensión con LM358 + filtro RC |
| Nivel de agua | XKC-Y25-V | Digital, 5–24 V DC | Divisor 10 kΩ + 20 kΩ para adaptación a 3.3 V |

---

# 28. Acondicionamiento analógico del invernadero

Componentes mencionados:

## LM324

Uso:

- Amplificador no inversor para LM335.

## LM358

Uso:

- Seguidor de tensión.
- Filtro RC para sensor de humedad.

## Divisor de tensión

Uso:

- Adaptar XKC-Y25-V a la lógica de 3.3 V.

## Diodos

- 1N4004.
- 1N5819.

Uso:

- Protección contra picos inductivos.

## Transistores

- 2N3904.

Uso:

- Interruptores auxiliares.

## MOSFET

- IRF520.

Uso:

- Control de potencia de bomba y ventilador.

## Regulador

- MP1584.

Conversión:

> 12 V → 5 V

## Fuente

- 12 V.

---

# 29. Control y potencia del invernadero

El ESP32 se planteó para:

- Leer ADC.
- Convertir lecturas a magnitudes físicas.
- Ejecutar lógica de histéresis.
- Guardar datos en LittleFS.
- Enviar datos por WiFi.

Actuadores:

- Bomba 12 V DC.
- Ventilador 12 V DC.

Controlados mediante:

- Módulos MOSFET.

Protecciones por software:

- Tiempo máximo de riego.
- Tiempo mínimo entre riegos.

Prioridad de seguridad:

> Si el sensor de nivel indica tanque vacío, la bomba no se enciende.

---

# 30. Relación con Circuitos Integrados — Boylestad

Se registró la siguiente relación:

- Capítulos 1–2:
  - Diodos de protección.

- Capítulos 3–5:
  - Transistores BJT como interruptores.

- Capítulos 6–8:
  - MOSFET para potencia.

- Capítulos 10–11:
  - Amplificadores operacionales.
  - No inversor.
  - Seguidor.
  - Filtro.

- Capítulo 15:
  - Fuentes y reguladores.

---

# 31. Relación con Instrumentación Industrial — Avendaño

Conceptos contemplados:

- Transductores de parámetro variable.
- Características estáticas:
  - Sensibilidad.
  - Linealidad.
  - Histéresis.
- Características dinámicas:
  - Constante de tiempo.
- Calibración contra patrones.
- Efecto de carga y corrección.
- Ruido.
- Interferencia.
- Análisis estadístico.
- Propagación de incertidumbres.
- Control con histéresis.

---

# 32. Alcance técnico del proyecto de invernadero

## Incluye

- Diseño y montaje de acondicionamiento analógico.
- Amplificador no inversor.
- Seguidor de tensión.
- Filtro RC.
- Divisor de tensión.
- Caracterización estática.
- Caracterización dinámica.
- Sensibilidad.
- Linealidad.
- Histéresis.
- Constante de tiempo.
- Calibración.
- Lógica de control con histéresis.
- Etapa de potencia.
- MOSFET.
- Diodos de protección.
- Pruebas con bomba y ventilador.

## No incluye

- Modelos termodinámicos avanzados.
- Diseño de PCB.
- Comunicación con PLC industrial externo.
- Análisis económico detallado.

---

# 33. Reglas de diseño del invernadero

## Regla de seguridad

- Limitar corriente.
- Usar fusibles.
- Utilizar diodos de protección.
- Evitar funcionamiento en seco de la bomba mediante XKC-Y25-V.

## Regla de estabilidad

Retroalimentación mediante:

- Temperatura.
- Humedad.

## Regla de eficiencia

Activar:

- Bomba.
- Ventilador.

Solo cuando sea necesario.

## Regla de prioridad

El nivel de agua tiene prioridad sobre el riego.

Si no hay agua:

> La bomba no se enciende aunque la humedad del suelo sea baja.

## Regla de documentación

Registrar:

- Parámetros de calibración.
- Cambios de diseño.
- Resultados de pruebas.

---

# 34. Propuesta LaTeX del invernadero

Se preparó una propuesta técnica en LaTeX con:

1. Proceso seleccionado.
2. Variable de proceso.
3. Alcance del estudio.
4. Justificación.
5. Reglas de diseño aplicadas.
6. Relación con las asignaturas.

El documento se planteó como:

> Sistema de Instrumentación y Control Analógico para Invernadero.

Asignaturas:

- Circuitos Integrados.
- Instrumentación Industrial.

Autores incluidos:

- Juan Camilo Valenzuela.
- Stiven Flórez Quiñonez.
- Cristian David Villegas Diaz.
- William Salazar Ruiz.

La fecha del documento LaTeX utiliza `\today`.

---

# 35. Configuraciones de amplificadores operacionales

Se elaboró material educativo para un Tecnólogo en Electrónica Industrial.

Enfoque:

> Comprender qué hace cada circuito, cómo se comporta y para qué sirve en un tablero de control o sistema de instrumentación industrial.

No se priorizan demostraciones matemáticas complejas.

---

# 36. Amplificador inversor

Función:

- Amplificar una señal.
- Invertir su signo.
- Cambio de fase de 180°.

Fórmula registrada:

\[
V_o=-V_i\left(\frac{R_f}{R_i}\right)
\]

Conceptos:

- La ganancia depende de la relación de resistencias.
- Impedancia de entrada: \(R_i\).

Aplicación industrial:

- Acondicionamiento de señales de sensores.
- Inversión de polaridad para lectura por PLC o ADC.

---

# 37. Amplificador no inversor

Función:

- Amplificar la señal.
- Mantener la fase.

Fórmula:

\[
V_o=V_i\left(1+\frac{R_2}{R_1}\right)
\]

Características:

- Impedancia de entrada alta.
- No carga significativamente al sensor.
- Ganancia mínima: 1.

Aplicaciones:

- Sensores de alta impedancia.
- Sensores piezoeléctricos.
- Sensores de pH.
- Acondicionamiento antes de ADC.

---

# 38. Seguidor de voltaje

También llamado:

> Buffer.

Función:

- Copiar el voltaje de entrada.
- Ganancia = 1.

Fórmula:

\[
V_o=V_{in}
\]

Objetivo:

> Aislar impedancias.

Aplicación:

- Acoplamiento entre etapas.
- Conectar una señal débil a una entrada de microcontrolador evitando cargar el sensor.

---

# 39. Sumador inversor

Función:

- Sumar varias señales.
- Invertir la salida.

Fórmula:

\[
V_o=-R_f
\left(
\frac{V_{i1}}{R_1}
+
\frac{V_{i2}}{R_2}
+
\cdots
+
\frac{V_{in}}{R_n}
\right)
\]

Aplicaciones:

- Mezcla de señales.
- Promediado.
- Inyección de offset.
- Combinación de señales de sensores.

---

# 40. Amplificador diferencial

Función:

- Restar dos señales.
- Amplificar la diferencia.

Fórmula registrada:

\[
V_o=
\left(\frac{R_2}{R_1}\right)
(V_{i2}-V_{i1})
\]

Condición indicada:

> \(R_1=R_3\) y \(R_2=R_4\)

Concepto principal:

- Rechazo de modo común (CMRR).

Aplicaciones:

- Celdas de carga.
- Puentes de Wheatstone.
- Termocuplas.
- Entornos industriales con ruido.

---

# 41. Amplificador integrador

Función:

- La salida es proporcional a la integral de la entrada.

Fórmula:

\[
V_o=-\frac{1}{RC}\int V_{in}(t)\,dt
\]

Aplicaciones indicadas:

- Convertir onda cuadrada en triangular.
- Convertir pulso en rampa.
- Parte integral de controladores PID.
- Conversión frecuencia-voltaje.
- Generación de rampas para arranque suave.

---

# 42. Amplificador derivador

Función:

- La salida es proporcional a la derivada de la entrada.

Fórmula:

\[
V_o=-RC\frac{dV_{in}(t)}{dt}
\]

Características:

- Reacciona a cambios bruscos.
- Es sensible al ruido.
- En aplicaciones industriales se suele combinar con filtrado.

Aplicaciones:

- Detección de flancos.
- Parte derivativa de PID.
- Medición de velocidad desde posición.

---

# 43. Comparador de voltaje

Función:

- Comparar dos voltajes.

Comportamiento indicado:

\[
V_1>V_2 \Rightarrow V_o\rightarrow +V
\]

\[
V_1<V_2 \Rightarrow V_o\rightarrow -V
\]

Características:

- Sin realimentación negativa.
- Trabajo en lazo abierto.
- Saturación.

Aplicaciones:

- Detección de umbrales.
- Alarmas.
- Temperatura.
- Nivel de tanque.

---

# 44. Amplificador logarítmico

Función:

- Obtener una salida proporcional al logaritmo de la entrada.

Fórmula registrada:

\[
V_o=-V_T\ln\left(\frac{V_i}{R_iI_s}\right)
\]

Características:

- Puede utilizar diodo o transistor en realimentación.
- Comprime señales de amplio rango dinámico.

Aplicaciones mencionadas:

- Sensores con respuesta exponencial.
- Luz.
- Presión.
- Multiplicadores analógicos.
- Compresión de audio.

---

# 45. Amplificador exponencial / antilogarítmico

Función:

- Obtener una salida exponencial respecto a la entrada.

Fórmula registrada:

\[
V_o=-RI_s
\left(e^{V_i/V_T}-1\right)
\]

Características:

- Circuito inverso del logarítmico.
- Diodo/transistor colocado en la entrada.

Aplicaciones:

- Cálculos inversos.
- Generación de funciones matemáticas.
- Linealización de sensores.

---

# 46. Consejos técnicos para trabajo industrial

## El mundo real no es ideal

Las fórmulas anteriores suponen amplificadores operacionales ideales.

Parámetros que deben revisarse:

- Slew Rate.
- Ancho de banda.
- GBW.

Una ganancia alta junto con una señal rápida puede superar la capacidad de seguimiento del amplificador.

## Saturación

Un amplificador operacional real no puede superar los límites establecidos por su alimentación.

Ejemplo registrado:

> Con +12 V y -12 V, una salida real puede quedar alrededor de +10.5 V y -10.5 V dependiendo del dispositivo.

## Ruido industrial

Fuentes de ruido mencionadas:

- Motores.
- Relés.
- Variadores.
- Red eléctrica.

Medidas recomendadas en el contexto:

- Cables blindados.
- Filtros pasabajos.
- Cuidado especial con integradores, derivadores y amplificadores de alta ganancia.

---

# 47. Proyecto/estudio: ESP32 CYD 3.5-inch

## Modelo

> ESP32-3248S035C

## Referencia indicada

`https://esp32pins.com/boards/esp32-cyd-3248s035/`

## Imagen mencionada

`esp32display.jpg`

---

# 48. Especificaciones registradas del ESP32 CYD

| Característica | Valor registrado |
|---|---|
| Marca | KS |
| Modelo | ESP32-3248S035C |
| Microcontrolador | ESP32 |
| Voltaje de funcionamiento | 5 V |
| Voltaje de entrada recomendado | 5 V |
| Voltaje de entrada límite | 5 V |
| Frecuencia de reloj | 240 MHz |
| SRAM | 520 KB |
| EEPROM indicada | 448 KB |
| Entradas analógicas indicadas | 0 |
| GPIO digitales libres indicados | 3 |
| Cable USB | Sí |
| Dimensiones | 10.15 × 5.49 × 1 cm |
| Peso | 120 g |
| Pantalla | TFT 3.5", 480×320 |
| Controlador de pantalla | ST7796 |
| Touch | Capacitivo GT911 |
| Conectividad | Wi-Fi 802.11 b/g/n, Bluetooth v4.2 BLE |
| Almacenamiento | MicroSD por SPI |
| USB-UART | CH340C sobre Micro-USB |
| Periféricos | LED RGB, LDR, speaker, BOOT, RESET |

> **Nota de contexto:** estas especificaciones se registraron desde la información proporcionada en la conversación y deben verificarse contra la revisión concreta de la placa antes de utilizarse como documentación definitiva.

---

# 49. Pines de expansión registrados

| Header | GPIO | Tipo | Uso disponible |
|---|---|---|---|
| P3-2 | IO35 | Entrada | Entrada digital |
| P3-3 | IO22 | I/O | Digital, PWM, I2C, UART |
| P3-4 | IO21 | I/O | Digital, PWM, I2C |
| P3-1 / P1-4 / CN1-1 | GND | Power | Tierra |
| P1-1 | VIN | Power | Entrada 5 V |
| CN1-4 | 3V3 | Power | Salida 3.3 V |
| P1-2 | TX | UART | GPIO1 / UART0 TX |
| P1-3 | RX | UART | GPIO3 / UART0 RX |

Advertencia registrada:

> IO21 puede compartirse con la interrupción del GT911 según revisión del modelo C; verificar antes de usarlo.

---

# 50. Pantalla y touch

Pantalla:

- TFT 3.5".
- Resolución: 480×320.
- Controlador: ST7796.
- Comunicación: SPI.

Touch:

- Capacitivo.
- Controlador: GT911.

Uso indicado:

- Pantalla y touch funcionan con librerías estándar para CYD.
- No se requieren modificaciones hardware según el contexto proporcionado.

---

# 51. Sensores compatibles con ESP32 CYD

Se registraron como compatibles:

- TCRT5000.
- TCS3200.
- TCS34725.
- HC-SR04.
- JSN-SR04T.
- Encoder.
- ACS712.
- MPU6050.
- BME280.
- BMP280.
- SHT31.
- OLED.
- PCF8574.
- DS18B20.
- PIR.
- Sensores de nivel.
- Sensores de humedad.
- GPS.
- RFID.

Interfaces:

- Digital.
- I2C.
- SPI.
- UART.
- One-Wire.

Se indicó que los sensores analógicos podrían requerir ADC externo cuando no existan entradas analógicas disponibles en la placa concreta.

---

# 52. Pines recomendados en ESP32 CYD

Según el contexto registrado:

## I2C

- IO22.
- IO21.

Condición:

> Verificar conflicto con touch antes de utilizar IO21.

## Entradas digitales

- IO35.
- IO22.
- IO21.

## Comunicación serial

- TX.
- RX.

---

# 53. Actuadores compatibles con ESP32 CYD

Se mencionaron:

- Motores DC.
- Servomotores.
- Relés.
- Electroválvulas.
- Ventiladores.
- Calentadores.
- Iluminación.
- HMI.
- Alarmas.

Drivers o etapas:

- L298N.
- TB6612.
- DRV8833.
- MOSFET.
- Relés con optoacoplador.
- SSR.

---

# 54. Uso del ESP32 CYD para PID

La placa puede utilizarse como controlador para:

- Temperatura.
- Velocidad.
- Posición.
- Caudal.

Capacidades mencionadas:

- Lectura de sensores digitales.
- I2C.
- SPI.
- UART.
- PWM.
- Temporizadores.
- Comunicación.

Programación contemplada:

- Arduino IDE.
- ESP-IDF.
- PlatformIO.
- MicroPython.

---

# 55. Ejemplo de código PID registrado

El ejemplo proporcionado utilizaba:

- Librería `PID_v1.h`.
- Entrada digital GPIO35.
- PWM en IO22.
- Setpoint = 100.
- Kp = 2.0.
- Ki = 5.0.
- Kd = 1.0.
- Límite de salida: 0–255.
- Tiempo de actualización aproximado: 10 ms.

El ejemplo fue planteado como demostración básica de PID y no debe interpretarse automáticamente como una implementación validada para el proyecto de la banda.

---

# 56. Usos posibles del ESP32 CYD

- Nodo IoT.
- Wi-Fi.
- Bluetooth.
- ESP-NOW.
- MQTT.
- HTTP.
- Data logger.
- MicroSD.
- Control de procesos.
- PID.
- Secuencias.
- Temporizadores.
- UART.
- I2C.
- SPI.
- CAN mediante módulo externo.
- RS485.
- Automatización.
- Riego.
- Alarmas.
- Control de acceso.
- HMI.
- Dashboards.
- Alarmas visuales.
- Alarmas sonoras.

---

# 57. Conclusión registrada del ESP32 CYD

El ESP32 CYD 3.5-inch modelo ESP32-3248S035C fue considerado una plataforma versátil para:

- Control.
- HMI.
- Sensores.
- Actuadores.
- Comunicación.
- IoT.
- Data logging.
- PID.

La principal consideración registrada es la planificación de los GPIO disponibles debido a los periféricos integrados.

---

# 58. Conversación sobre combos de electrónica y precios

## 58.1 Primer combo — 100.000 COP

### Elementos cobrados

- 2 × Módulo WiFi ESP8266 ESP-12E NodeMCU V2.
- 2 × Motor Shield ESP WiFi ESP8266 ESP-12E.
- 1 × Pantalla OLED Display Azul 0.96" I2C.
- 1 × NodeMCU ESP32 WiFi CH340G USB-C + Shield borneras.

### Elementos gratis

- Protoboard MB-102.
- Potenciómetro 100k RV24YN.
- Adaptador AC/DC 12 V 2 A.
- DS18B20.
- Kit de resistencias de 500 piezas.
- Kit de condensadores de 250 piezas.
- MOSFET IRF520.
- BMS 3S 20 A.
- Jumpers.
- 2 × plafones.
- 1 × bombillo.

### Precio

- Precio final: 100.000 COP.
- Ahorro estimado: 90.000 COP.

---

# 59. Ajuste con RTC DS3231

Se añadió:

- RTC DS3231.

Valor indicado:

- 16.000 COP.

Se incorporó como pieza gratis.

Precio final:

> 100.000 COP.

Ahorro estimado:

> 106.000 COP.

---

# 60. Ajuste con NRF24L01

Se añadió:

- NRF24L01 + PA + LNA.

Valor indicado:

- 14.574 COP.

Configuración registrada:

- Uno cobrado.
- Otro gratis.

Precio final:

> 100.000 COP.

Ahorro estimado:

> 120.000 COP.

---

# 61. Balance proporcional

Se ajustó el combo para:

- 110.000 COP cobrados.
- 110.000 COP en productos gratis.

Precio final:

> 110.000 COP.

Ahorro estimado:

> 110.000 COP.

---

# 62. Venta rápida de piezas sueltas

## Incluye

- 2 × NodeMCU ESP8266 V2.
- 2 × Motor Shield ESP8266.
- Kit de resistencias de 500 piezas.
- Kit de condensadores de 250 piezas.
- Potenciómetro 100k.
- Adaptador AC/DC 12 V 2 A.

## Valor real indicado

> 100.000–115.000 COP.

## Precio recomendado registrado

> 80.000 COP.

Descripción:

> Venta justa.

## Precio elegido para venta rápida

> 60.000 COP.

---

# 63. Slogan para Marketplace

> ⚡ COMBO ELECTRÓNICA EXPRESS ⚡
>
> Resistencias y capacitores perfectos para tu materia de circuitos y taller tecnológico, potenciómetro y fuente para control automático que energizan y controlan tu motor 12V, más 2 placas NodeMCU ESP8266 para crear y comunicar tus proyectos.
>
> **Precio rápido: 60.000 COP**

---

# 64. Cambios de instrumentación — resumen consolidado

Este apartado consolida las decisiones principales del proyecto de control:

| Elemento | Antes / opción inicial | Cambio / opción actual |
|---|---|---|
| Driver | L298N | BTS7960 |
| Corriente | ACS712 | ACS758 o INA219 |
| Posición | IR básicos | E18-D80NK |
| Color | Módulo genérico | TCS34725 |
| Altura | HC-SR04 | JSN-SR04T |
| Motor | Motor original | Motor con encoder como alternativa |
| Control | Corriente | Corriente o encoder + PID |
| Alimentación | — | 24 V con regulación a 12 V, 9 V y 5 V |
| Documentación | — | Calibración + P&ID simplificado |

---

# 65. Decisiones de diseño actualmente registradas

## Decisiones principales

1. Mantener dos alternativas de control:
   - Motor original + control por corriente.
   - Motor cambiado + encoder + PID + feedforward.

2. Cambiar el L298N por BTS7960.

3. Utilizar sensores más adecuados para instrumentación:
   - ACS758/INA219.
   - E18-D80NK.
   - TCS34725.
   - JSN-SR04T.

4. Utilizar una fuente principal de 24 V y regulaciones secundarias.

5. Mantener dos ESP32:
   - Uno para control.
   - Uno para HMI.

6. Implementar máquina de estados para coordinar:
   - Sensores.
   - Topes.
   - Servos.
   - Desvíos.
   - Conteo.

7. Implementar detección de atascos mediante corriente.

8. Documentar calibración y P&ID.

---

# 66. Alternativas y elementos descartados o sustituidos

Elementos que aparecen como reemplazados:

- L298N → BTS7960.
- ACS712 → ACS758.
- IR básicos → E18-D80NK.
- Sensor de color genérico → TCS34725.
- HC-SR04 → JSN-SR04T.

En el proyecto de invernadero:

- Se evaluaron RTD, NTC, termopar, galgas, LDR y LVDT.
- Se descartó el módulo microSD por problemas de compatibilidad.
- Se eliminó el cronograma debido a la disponibilidad de seis semanas.
- Se simplificaron circuitos evitando puentes de Wheatstone y amplificadores de instrumentación complejos.

---

# 67. Requisitos de continuidad para futuras conversaciones

Cuando otro LLM utilice este archivo como contexto, debe conservar las siguientes reglas de continuidad:

## No asumir cambios no registrados

No cambiar automáticamente:

- Sensores.
- Motores.
- Drivers.
- Arquitectura.
- Reglas de control.

## Diferenciar alternativas

Mantener claramente separadas:

### Banda

- Opción 70 × 10 cm.
- Opción 100 × 10 cm.

### Motor

- Motor original.
- Motor con encoder.

### Control

- Control por corriente.
- PID + feedforward por corriente.

### Sensores

- Opciones principales.
- Alternativas.

## Diferenciar hechos de propuestas

Cuando una información esté descrita como:

- propuesta;
- recomendación;
- alternativa;
- opción;
- dato pendiente de verificar;

no convertirla automáticamente en una decisión definitiva.

---

# 68. Pendientes técnicos identificables

A partir del contenido registrado, quedan como asuntos susceptibles de verificación o definición:

- Selección final de la banda:
  - 70 × 10 cm o 100 × 10 cm.
- Selección final del motor:
  - original o JGA25-370/JGB37-520.
- Selección final del sensor de corriente:
  - ACS758 o INA219.
- Definición de los umbrales reales de corriente.
- Calibración del TCS34725.
- Calibración del JSN-SR04T.
- Ajuste del E18-D80NK.
- Sintonización real del PID.
- Definición de los parámetros finales de protección.
- Distribución definitiva de GPIO.
- Verificación de conflictos de GPIO del ESP32 CYD.
- Diseño final del P&ID.
- Registro de resultados experimentales.
- Verificación de especificaciones de módulos comerciales concretos.

---

# 69. Regla de documentación futura

Toda modificación futura del proyecto debería registrarse indicando:

```text
Fecha:
Proyecto:
Elemento afectado:
Configuración anterior:
Nueva configuración:
Motivo del cambio:
Ventajas:
Desventajas:
Impacto en control:
Impacto en instrumentación:
Impacto en software:
Impacto en presupuesto:
Estado:
Pendientes:
```

Esto permite mantener trazabilidad del diseño.

---

# 70. Metadatos del registro

**Tipo de documento:** Log técnico y contextual.

**Uso principal:**

- Memoria para LLM.
- Continuidad entre conversaciones.
- Seguimiento de proyectos.
- Recuperación de decisiones.
- Preparación de documentos técnicos.
- Preparación de código.
- Preparación de informes.
- Preparación de presentaciones.
- Seguimiento académico.
- Seguimiento de componentes y presupuesto.

**Idioma principal:** Español.

**Moneda utilizada en compras:** COP.

**Fecha de referencia más reciente proporcionada:** 1 de octubre de 2026.

---

# 71. Nota de integridad

Este archivo fue construido a partir del contexto proporcionado en la conversación.

Cuando existen afirmaciones técnicas, cifras, capacidades de componentes o especificaciones que requieren validación experimental o documental, se conservan como contexto y, cuando corresponde, se señalan como datos a verificar.

No se debe interpretar este `log.md` como una certificación de que todos los valores técnicos registrados hayan sido comprobados experimentalmente.

---

# FIN DEL LOG
