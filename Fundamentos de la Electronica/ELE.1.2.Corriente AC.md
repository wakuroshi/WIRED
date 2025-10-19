# 1. Corriente Alterna (AC)

La corriente alterna (AC) es una corriente eléctrica cuyo valor varía periódicamente en el tiempo.  
La forma de onda más utilizada es la senoide:

$$
i(t) = I_m \sin(\omega t + \phi)
$$

donde:

| Símbolo           | Significado                      | Unidad  |
| :---------------: | :------------------------------- | :-----: |
| $I_m$             | Amplitud máxima (corriente pico) | A       |
| $\omega = 2\pi f$ | Frecuencia angular               | rad/s   |
| $f$               | Frecuencia                       | Hz      |
| $\phi$            | Ángulo de fase                   | rad o ° |

De forma análoga, la tensión se expresa como:

$$
v(t) = V_m \sin(\omega t + \theta)
$$

## 1.1. Desfase entre tensión y corriente

En circuitos con elementos reactivos, la tensión y la corriente no están en fase.

- Si $\phi = 0$: $v$ e $i$ están en fase → circuito **resistivo puro**.  
- Si $\phi > 0$: la corriente **adelanta** a la tensión → circuito **capacitivo**.  
- Si $\phi < 0$: la corriente **atrasa** respecto a la tensión → circuito **inductivo**.

El **factor de potencia** es $\cos\phi$.

## 1.2. Valor Eficaz (RMS)

El valor eficaz o RMS (Root Mean Square) de una magnitud alterna es el valor de corriente o tensión continua que produciría la misma potencia media en una resistencia.

**Definición general**:

$$
I_{rms} = \sqrt{\frac{1}{T} \int_0^T [i(t)]^2 \, dt}
$$

**Para una onda senoidal**:

$$
I_{rms} = \frac{I_m}{\sqrt{2}}, \qquad V_{rms} = \frac{V_m}{\sqrt{2}}
$$

La potencia media disipada en una resistencia $R$ es:

$$
P_{med} = V_{rms} \, I_{rms} \cos\phi
$$

## 1.3. Representación Fasorial

Una señal senoidal puede representarse como un número complejo denominado **fasor**.  
Esto permite transformar ecuaciones diferenciales en ecuaciones algebraicas.

$$
v(t) = V_m \cos(\omega t + \theta) \quad \Longleftrightarrow \quad \mathbf{V} = V_{rms} \angle \theta
$$

$$\land$$

$$
i(t) = I_m \cos(\omega t + \phi) \quad \Longleftrightarrow \quad \mathbf{I} = I_{rms} \angle \phi
$$

El análisis fasorial permite simplificar el estudio de circuitos en régimen sinusoidal estable.

## 1.3.1. Formas de representación de un fasor

| Forma | Expresión general | Ejemplo |
|:--|:--|:--|
| Trigonométrica | $V = V_m (\cos\theta + j \sin\theta)$ | $10(\cos30° + j\sin30°)$ |
| Polar | $V = V_m \angle \theta$ | $10 \angle 30°$ |
| Exponencial | $V = V_m e^{j\theta}$ | $10 e^{j30°}$ |
| Rectangular | $V = a + jb$, con $a = V_m \cos\theta$, $b = V_m \sin\theta$ | $8.66 + j5$ |

### 1.4. Conversión entre formas

- **De polar a rectangular**:

$$
V = V_m (\cos\theta + j\sin\theta)
$$

- **De rectangular a polar**:

$$
|V| = \sqrt{a^2 + b^2}, \qquad \theta = \tan^{-1}\left(\frac{b}{a}\right)
$$

- **De trigonométrica a exponencial**:

$$
\cos\theta + j\sin\theta = e^{j\theta}
$$

## 1.5. Impedancia $Z$

La impedancia representa la **oposición total** (resistencia + reactancia) al paso de la corriente alterna.

$$
Z = R + jX
$$

donde $R$ es la **resistencia** y $X$ la **reactancia**.  

### 1.5.1. Magnitud y fase:

$$
|Z| = \sqrt{R^2 + X^2}, \qquad \angle Z = \tan^{-1}\left(\frac{X}{R}\right)
$$

| Elemento | Relación fasorial | Reactancia $X$ | Desfase |
|:--|:--|:--:|:--:|
| Resistencia $R$ | $V = I \cdot R$ | $0$ | $0°$ |
| Inductor $L$ | $V = j \omega L I$ | $X_L = \omega L$ | $+90°$ |
| Capacitor $C$ | $V = \frac{I}{j \omega C}$ | $X_C = \frac{1}{\omega C}$ | $-90°$ |

## 1.6. Reactancia y Resonancia

La reactancia total de un circuito serie $RLC$ es:

$$
X = X_L - X_C
$$

Condiciones:

| Tipo de circuito | Condición | Efecto | Desfase |
|:--|:--|:--|:--:|
| Inductivo | $X_L > X_C$ | Corriente atrasada | $\phi < 0$ |
| Capacitivo | $X_C > X_L$ | Corriente adelantada | $\phi > 0$ |
| Resonante | $X_L = X_C$ | Corriente máxima | $\phi = 0°$ |

En resonancia, la impedancia se reduce a un valor puramente resistivo: $Z = R$.

## 1.7. Admitancia $Y$

La admitancia es el **inverso de la impedancia** y mide la facilidad de paso de la corriente:

$$
Y = \frac{1}{Z} = G + jB
$$

donde:
- $G$ es la conductancia (parte real),
- $B$ la susceptancia (parte imaginaria).

Relaciones:

$$
G = \frac{R}{R^2 + X^2}, \qquad B = -\frac{X}{R^2 + X^2}
$$

Magnitud y fase:

$$
|Y| = \frac{1}{|Z|}, \qquad \angle Y = -\angle Z
$$

Al valor $\sqrt{2}Ye^{j \phi}$ Se le denomina **fasor** 
## 1.8. Operaciones con fasores

**Ley de Ohm en forma fasorial:**

$$
\mathbf{V} = \mathbf{I} \cdot \mathbf{Z}
$$

**Suma y resta:** (se realiza en forma rectangular)

$$
\mathbf{V}_T = (a_1 + jb_1) + (a_2 + jb_2) = (a_1 + a_2) + j(b_1 + b_2)
$$

**Multiplicación y división:** (más cómodo en forma polar)

$$
(V_1 \angle \theta_1)(V_2 \angle \theta_2) = (V_1 V_2) \angle (\theta_1 + \theta_2)
$$

$$
\frac{V_1 \angle \theta_1}{V_2 \angle \theta_2} = \frac{V_1}{V_2} \angle (\theta_1 - \theta_2)
$$

## 1.9. Potencias en Corriente Alterna

- **Potencia aparente**:

$$
S = V_{rms} I_{rms}
$$

- **Potencia activa (real)**:

$$
P = V_{rms} I_{rms} \cos\phi
$$

- **Potencia reactiva**:

$$
Q = V_{rms} I_{rms} \sin\phi
$$

- **Relación entre potencias**:

$$
|S| = \sqrt{P^2 + Q^2}
$$

El **factor de potencia** es:

$$
\cos\phi = \frac{P}{|S|} = \frac{R}{|Z|}
$$

| Tipo | Símbolo | Unidad | Significado |
|:--|:--:|:--:|:--|
| Activa | $P$ | W | Energía útil disipada |
| Reactiva | $Q$ | var | Energía almacenada y devuelta |
| Aparente | $S$ | VA | Producto total $V \cdot I$ |

## 1.10. Suma de tensiones $V(t)$ y análisis vectorial

Supongamos dos tensiones sinusoidales con igual frecuencia:

$$
v_1(t) = V_{1m}\cos(\omega t + \theta_1)
$$

$$
v_2(t) = V_{2m}\cos(\omega t + \theta_2)
$$

La suma instantánea es:

$$
v(t) = v_1(t) + v_2(t)
$$

Para sumarlas de manera práctica, se usa la representación fasorial.

1. Convertir cada senoide a su fasor:  
   $\mathbf{V}_{1p} = V_{1m} \angle \theta_1$,  
   $\mathbf{V}_{2p} = V_{2m} \angle \theta_2$.

2. Pasar a forma rectangular:  
   $\mathbf{V} = V_x + jV_y = V(\cos\theta + j\sin\theta)$.

3. Sumar componentes reales e imaginarias.

4. Convertir el resultado a forma polar:
   $|\mathbf{V}| = \sqrt{V_x^2 + V_y^2}$,  
   $\angle \mathbf{V} = \tan^{-1}(V_y/V_x)$.

5. Regresar al dominio temporal:
   $v(t) = V_m \cos(\omega t + \theta)$.

### Ejemplo

Sumar:

$$
v_1(t) = 10\cos(\omega t), \quad v_2(t) = 5\cos(\omega t + 30°)
$$

Fasores (en valor pico):

$$
\mathbf{V}_{1p} = 10\angle 0°, \quad \mathbf{V}_{2p} = 5\angle 30°
$$

Forma rectangular:

$$
\mathbf{V}_{1p} = 10 + j0
$$

$$
\mathbf{V}_{2p} = 5(\cos30° + j\sin30°) = 4.33 + j2.5
$$

Suma:

$$
\mathbf{V}_{sum} = (10 + 4.33) + j(0 + 2.5) = 14.33 + j2.5
$$

Conversión a polar:

$$
|\mathbf{V}_{sum}| = \sqrt{14.33^2 + 2.5^2} = 14.55, \quad \angle\mathbf{V}_{sum} = \tan^{-1}\left(\frac{2.5}{14.33}\right) = 9.9°
$$

Resultado:

$$
v(t) = 14.55\cos(\omega t + 9.9°)
$$

Si se desea en valor RMS:

$$
V_{rms} = \frac{14.55}{\sqrt{2}} = 10.29
$$

### Observaciones

- La suma fasorial solo es válida si las tensiones tienen la misma frecuencia.
- Para más de dos fasores, se suman todos sus componentes rectangulares.
- Es preferible trabajar en forma rectangular para sumas y en forma polar para multiplicaciones o divisiones.

## 1.11. Divisor de tensión en AC

Dado un divisor en serie $Z_1$ y $Z_2$ con tensión de entrada $\mathbf{V}_{in}$:

$$
\mathbf{V}_{Z2} = \mathbf{V}_{in} \cdot \frac{Z_2}{Z_1 + Z_2}
$$

Pasos:
1. Calcular $Z_1$ y $Z_2$ en forma compleja.
2. Sumar $Z_{eq} = Z_1 + Z_2$.
3. Multiplicar $\mathbf{V}_{in}$ por la fracción compleja.
4. Convertir resultado a polar para obtener magnitud y desfase.


