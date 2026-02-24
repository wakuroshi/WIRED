---
materia: Fundamentos de la Electrónica
id: ELE.5.3
tema: Circuitos de Cómputo Analógico
status: Revision
tags: [Op-Amp, integrador, derivador, sumador, cálculo-analógico]
---

# ELE.5.3. Circuitos de Cómputo Analógico

> [!abstract] Procesamiento Matemático de Señales
> El Amplificador Operacional permite realizar operaciones matemáticas sobre voltajes de entrada. Mientras que las compuertas lógicas operan con valores discretos (0 y 1), estos circuitos operan en el dominio del tiempo y la amplitud continua. Veremos cómo la ubicación de un condensador transforma una señal en su integral o su derivada. Basado en **Sedra & Smith (Cap. 2)** y **Floyd (Cap. 12)**.

---

# 1. El Integrador de Miller (Configuración Capacitiva)

El integrador acumula el valor de la señal de entrada a lo largo del tiempo. Es, esencialmente, un filtro paso bajo activo con ganancia.

### 1.1. Estructura y Funcionamiento
Se coloca una resistencia $R$ en la entrada y un **condensador $C$ en la trayectoria de realimentación** (entre la salida y la entrada inversora).
- **Análisis**: Debido a la tierra virtual en el pin (-), la corriente de entrada es $I_{in} = V_{in}/R$. Esta misma corriente debe pasar por el condensador, cargándolo proporcionalmente al tiempo.
- **Ecuación de Salida**: 
  $$V_{out}(t) = -\frac{1}{RC} \int_{0}^{t} V_{in}(\tau) d\tau + V_C(0)$$



### 1.2. Aplicación Práctica: Generación de Rampas
Si aplicamos una **onda cuadrada** a un integrador:
- Mientras la entrada es constante positiva, la salida cae linealmente (rampa negativa).
- Mientras la entrada es constante negativa, la salida sube linealmente (rampa positiva).
- **Resultado**: Convertimos pulsos digitales en ondas triangulares, usadas en la modulación PWM de fuentes de poder.

# 2. El Derivador Diferenciador

El derivador responde solo a los **cambios** de la señal de entrada. Funciona como un filtro paso alto activo.

### 2.1. Estructura y Funcionamiento
Se invierten los componentes del integrador: el **condensador $C$ va en la entrada** y la resistencia $R$ en la realimentación.
- **Análisis**: El condensador bloquea la CC (corriente continua). Solo si $V_{in}$ varía, circulará una corriente $I = C \cdot (dV_{in}/dt)$.
- **Ecuación de Salida**: 
  $$V_{out}(t) = -RC \frac{dV_{in}(t)}{dt}$$



### 2.2. Aplicación Práctica: Detección de Flancos
Si aplicamos una onda cuadrada, el derivador producirá "picos" de voltaje (spikes) solo en los momentos donde la señal sube o baja. En computación, esto se usa para extraer la señal de **reloj (clock)** o detectar eventos de cambio de estado en sensores.

# 3. El Sumador Inversor (Mezclador)

Como mencionaste la importancia de las compuertas, el sumador es la "AND" o "OR" analógica de los voltajes.

- **Estructura**: Múltiples entradas conectadas mediante resistencias independientes al mismo nodo de tierra virtual.
- **Ecuación**: $V_{out} = -R_f \left( \frac{V_1}{R_1} + \frac{V_2}{R_2} + ... \right)$
- **Versatilidad**: 
    - Si $R_1 = R_2 = R_f$, la salida es la suma simple.
    - Si las resistencias son diferentes, tenemos un **Sumador Ponderado**, que es el corazón de los convertidores **DAC (Digital-to-Analog)** donde cada bit tiene un peso diferente.



# 4. Limitaciones Reales: El problema de la Deriva (Drift)

En el papel, un integrador es perfecto. En la realidad de la Ingeniería en Computación:
1. **Saturación**: Si integras una señal pequeña pero constante (offset), el condensador se cargará hasta que el Op-Amp se sature en el raíl de alimentación. Se suele poner una resistencia muy grande en paralelo al condensador para "descargarlo" lentamente.
2. **Ruido en el Derivador**: Como el derivador amplifica las frecuencias altas, el ruido electromagnético de alta frecuencia puede dominar la señal de salida. Por eso los derivadores puros rara vez se usan sin un filtro adicional.

---

## Resumen de Comparativa
| Circuito | Ubicación del Capacitor | Función Matemática | Efecto en la Señal |
| :--- | :--- | :--- | :--- |
| **Integrador** | Realimentación ($R_f$) | $\int V_{in} dt$ | Suaviza, elimina ruido, crea rampas. |
| **Derivador** | Entrada ($R_{in}$) | $d V_{in} / dt$ | Resalta picos, detecta cambios bruscos. |
| **Sumador** | Resistivo | $V_1 + V_2$ | Combina señales o crea niveles de voltaje. |

> [!Example] Aplicación en Ingeniería en Computación: Filtros de Anti-Aliasing
> Antes de que un procesador lea una señal con su ADC (Analog-to-Digital Converter), la señal debe pasar por un filtro que elimine frecuencias indeseadas. Los integradores basados en Op-Amps forman parte de los **Filtros Activos de Butterworth**, asegurando que el procesador no reciba "ruido de alias" que corrompa los datos calculados por el software.

## Bibliografía
[**Sedra & Smith** - *Circuitos Microelectrónicos*, Cap. 2: Amplificadores Operacionales.]
[**Floyd, T. L.** - *Dispositivos Electrónicos*, Cap. 12: Integradores y Derivadores.]