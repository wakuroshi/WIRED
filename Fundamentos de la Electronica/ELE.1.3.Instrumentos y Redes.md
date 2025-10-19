# 1. Instrumentos de Medición Eléctrica

Los instrumentos eléctricos permiten medir magnitudes como corriente, voltaje, resistencia, potencia y energía.  
Es fundamental conocer su principio de funcionamiento, sus características y la forma correcta de conexión en el circuito.

## 1.1. Amperímetro

Mide la **intensidad de corriente** que circula por un circuito.

- Se **conecta en serie** con el elemento cuya corriente se desea medir.  
- Posee **resistencia interna muy baja** ($R_A \approx 0$) para no modificar la corriente real del circuito.  
- **Nunca** debe conectarse en paralelo, ya que podría dañarse por exceso de corriente.

**Medición ideal:**

$$
I = \frac{V}{R_{total}}
$$

donde $R_{total} = R + R_A \approx R$.

**Error típico:** Si $R_A$ no es despreciable, la corriente medida será menor que la real.

## 1.2. Voltímetro

Mide la **diferencia de potencial** (tensión) entre dos puntos de un circuito.

- Se **conecta en paralelo** con el elemento a medir.  
- Posee **resistencia interna muy alta** ($R_V \gg R$) para minimizar el flujo de corriente a través del instrumento.  

**Medición ideal:**
$$
V = I \cdot R
$$

**Error típico:** Si $R_V$ no es suficientemente grande, el voltímetro altera la tensión del circuito, entregando un valor menor.

## 1.3. Óhmetro

Mide la **resistencia eléctrica** de un componente.

- El circuito debe estar **desconectado de cualquier fuente** antes de usarlo.  
- El instrumento aplica una **corriente interna conocida** y mide la caída de tensión resultante.  

**Principio de medición:**
$$
R = \frac{V_{int}}{I_{int}}
$$

donde $V_{int}$ es la tensión de la batería interna y $I_{int}$ la corriente medida.

## 1.4. Multímetro

Instrumento que combina las funciones de **voltímetro, amperímetro y óhmetro**, y en versiones más avanzadas, también mide **capacitancia, frecuencia, temperatura o continuidad**.

### Modos de uso

| Modo | Qué mide | Conexión | Precaución |
|:--|:--|:--|:--|
| Voltaje DC/AC | Diferencia de potencial | Paralelo | No exceder el rango de tensión |
| Corriente DC/AC | Intensidad de corriente | Serie | No conectar directamente a una fuente |
| Resistencia | Valor resistivo | Aislado | El circuito debe estar sin tensión |

### Características principales

- **Rango de medida:** valor máximo seguro.  
- **Sensibilidad:** corriente mínima detectable.  
- **Precisión:** diferencia entre el valor real y el medido.  
- **Resolución:** mínima variación observable.  

**Ejemplo:**

Para un resistor de $R = 100\,\Omega$ conectado a $V = 12\,V$:

$$
I = \frac{12}{100} = 0.12\,A
$$

El multímetro se configura en el rango de **corriente continua ≥ 200 mA**, y se coloca **en serie** con el resistor.

## 1.5. Contador de Energía Eléctrica

Mide la **energía total consumida** por un circuito durante un intervalo de tiempo.

$$
E = P_{med} \cdot t
$$

donde $P_{med}$ es la potencia media y $t$ el tiempo (en horas).

En corriente alterna:

$$
P_{med} = V_{rms} I_{rms} \cos\phi
$$

por tanto:

$$
E = V_{rms} I_{rms} \cos\phi \, t
$$

**Unidad:** kilovatio-hora (kWh).  
**Ejemplo:** un dispositivo de $P = 1\,kW$ funcionando durante $3\,h$ consume $3\,kWh$.

# 2. Redes de Un Puerto y Dos Puertos

El análisis de redes eléctricas lineales se realiza mediante **modelos de puertos**, que representan las relaciones entre tensiones y corrientes en los terminales del sistema.

## 2.1. Redes de Un Puerto

Tienen **dos terminales** (un par de entrada/salida).  
Ejemplos: circuitos equivalentes de Thévenin y Norton, filtros simples RC o RL.

### Representación general

$$
Z_{eq} = \frac{V}{I}
$$

donde $Z_{eq}$ es la **impedancia equivalente** del puerto.  
Alternativamente, puede expresarse como admitancia:

$$
Y_{eq} = \frac{I}{V} = \frac{1}{Z_{eq}}
$$

### Asociación de redes

| Tipo de conexión | Relación |
|:--|:--|
| Serie | $Z_T = Z_1 + Z_2 + \dots$ |
| Paralelo | $\dfrac{1}{Z_T} = \dfrac{1}{Z_1} + \dfrac{1}{Z_2} + \dots$ |

## 2.2. Redes de Dos Puertos

Tienen **cuatro terminales**, organizados como dos pares: entrada $(V_1, I_1)$ y salida $(V_2, I_2)$.  
Se utilizan para modelar **amplificadores, filtros, líneas de transmisión, transformadores, etc.**

### Representación matricial general

$$
\begin{bmatrix} V_1 \\ V_2 \end{bmatrix}
=
\begin{bmatrix}
A & B \\
C & D
\end{bmatrix}
\begin{bmatrix} I_1 \\ -I_2 \end{bmatrix}
$$

Los coeficientes $A$, $B$, $C$, y $D$ describen el comportamiento de la red completa.

## 2.3. Tipos de Parámetros

Existen distintas formas de expresar matemáticamente la relación entre $V_1$, $V_2$, $I_1$ e $I_2$.

### 2.3.1. Parámetros de Impedancia ($Z$)

$$
\begin{bmatrix}
V_1 \\ V_2
\end{bmatrix}
=
\begin{bmatrix}
Z_{11} & Z_{12} \\
Z_{21} & Z_{22}
\end{bmatrix}
\begin{bmatrix}
I_1 \\ I_2
\end{bmatrix}
$$

| Parámetro | Condición | Interpretación |
|:--|:--|:--|
| $Z_{11} = \dfrac{V_1}{I_1}\Big\|_{I_2 = 0}$ | Puerto 2 abierto | Impedancia de entrada |
| $Z_{12} = \dfrac{V_1}{I_2}\Big\|_{I_1 = 0}$ | Puerto 1 abierto | Impedancia de transferencia inversa |
| $Z_{21} = \dfrac{V_2}{I_1}\Big\|_{I_2 = 0}$ | Puerto 2 abierto | Impedancia de transferencia directa |
| $Z_{22} = \dfrac{V_2}{I_2}\Big\|_{I_1 = 0}$ | Puerto 1 abierto | Impedancia de salida |

### 2.3.2. Parámetros de Admitancia ($Y$)

$$
\begin{bmatrix}
I_1 \\ I_2
\end{bmatrix}
=
\begin{bmatrix}
Y_{11} & Y_{12} \\
Y_{21} & Y_{22}
\end{bmatrix}
\begin{bmatrix}
V_1 \\ V_2
\end{bmatrix}
$$

| Parámetro | Condición | Interpretación |
|:--|:--|:--|
| $Y_{11} = \dfrac{I_1}{V_1}\Big\|_{V_2 = 0}$ | Puerto 2 en corto | Admitancia de entrada |
| $Y_{12} = \dfrac{I_1}{V_2}\Big\|_{V_1 = 0}$ | Puerto 1 en corto | Admitancia de transferencia inversa |
| $Y_{21} = \dfrac{I_2}{V_1}\Big\|_{V_2 = 0}$ | Puerto 2 en corto | Admitancia de transferencia directa |
| $Y_{22} = \dfrac{I_2}{V_2}\Big\|_{V_1 = 0}$ | Puerto 1 en corto | Admitancia de salida |


### 2.3.3. Parámetros Híbridos ($h$)

$$
\begin{bmatrix}
V_1 \\ I_2
\end{bmatrix}
=
\begin{bmatrix}
h_{11} & h_{12} \\
h_{21} & h_{22}
\end{bmatrix}
\begin{bmatrix}
I_1 \\ V_2
\end{bmatrix}
$$

| Parámetro | Significado | Unidad |
|:--|:--|:--|
| $h_{11}$ | Impedancia de entrada ($V_1/I_1$ con $V_2=0$) | $\Omega$ |
| $h_{12}$ | Ganancia inversa de tensión ($V_1/V_2$ con $I_1=0$) | adimensional |
| $h_{21}$ | Ganancia directa de corriente ($I_2/I_1$ con $V_2=0$) | adimensional |
| $h_{22}$ | Admitancia de salida ($I_2/V_2$ con $I_1=0$) | S |

### 2.3.4. Parámetros de Transmisión ($A$, $B$, $C$, $D$)

$$
\begin{bmatrix}
V_1 \\ I_1
\end{bmatrix}
=
\begin{bmatrix}
A & B \\
C & D
\end{bmatrix}
\begin{bmatrix}
V_2 \\ -I_2
\end{bmatrix}
$$

| Parámetro | Interpretación |
|:--|:--|
| $A$ | Relación de tensión de entrada a salida cuando $I_2=0$ |
| $B$ | Impedancia de entrada con $V_2=0$ |
| $C$ | Admitancia de salida con $I_1=0$ |
| $D$ | Relación de corriente de entrada a salida cuando $V_2=0$ |

## 2.4. Conversiones y Propiedades

### 2.4.1. De impedancia a admitancia:

$$
[Y] = [Z]^{-1}
$$

### 2.4.2. Redes en cascada (transmisión):

Si dos redes de transmisión se conectan en serie:

$$
[T]_{total} = [T]_1 \cdot [T]_2
$$

con

$$
[T] =
\begin{bmatrix}
A & B \\
C & D
\end{bmatrix}
$$

### 2.4.3. Condiciones de reciprocidad y simetría

- **Red recíproca:** $Z_{12} = Z_{21}$ o $AD - BC = 1$.  
- **Red simétrica:** $Z_{11} = Z_{22}$ o $A = D$.
