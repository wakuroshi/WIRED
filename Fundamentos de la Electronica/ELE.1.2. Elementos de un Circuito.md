---
materia: Fundamentos de la Electrónica
id: ELE.1.2
tema: Elementos de un Circuito
status: Terminado
tags: [DC, fuentes]
---

# ELE.1.2. Elementos de un Circuito

> [!abstract]- Modelado de la realidad física
> En ingeniería, no trabajamos con los componentes físicos reales directamente en el papel, sino con **modelos ideales**. Un elemento de circuito es una abstracción matemática definida por la relación entre la tensión en sus terminales y la corriente que lo atraviesa (característica $i \leftrightarrow v$).

---

# 1. Clasificación General

Los elementos se clasifican según su interacción con la energía del sistema:
1.  **Elementos Activos**: Capaces de suministrar una potencia media mayor a cero al mundo exterior (generadores, baterías, amplificadores operacionales).
2.  **Elementos Pasivos**: Absorben potencia (resistencias) o la almacenan temporalmente en campos (condensadores, bobinas). No pueden suministrar energía neta a largo plazo.

# 2. Fuentes de Energía (Elementos Activos)

Son las excitaciones del circuito. Matemáticamente, imponen restricciones en las variables del sistema.

## 2.1. Fuentes Independientes

Su valor es intrínseco y no se ve afectado por lo que ocurra en el resto del circuito.
* **Fuente de Tensión**: Genera una diferencia de potencial $V_{AB}$ constante entre sus terminales (**DC**) o $v_{AB}$ que varia en el tiempo (**AC**), sin importar la corriente que se le suministre.

> Una fuente ideal teórica podría entregar potencia infinita ($P = V \cdot \infty$). En la realidad, todas tienen una resistencia interna en serie y un límite de corriente máxima.

* **Fuente de Corriente**: Fuerza una corriente $I_s$ fija a través de la rama donde está conectada, sin importar la tensión que se genere en sus extremos.

## 2.2. Fuentes Dependientes (Controladas)

Son fundamentales para la electrónica activa. Modelan dispositivos donde una señal de control regula una salida de potencia (el principio de la amplificación y la lógica digital).
Se representan con un rombo y su ecuación depende de una variable de control ($v_x$ o $i_x$) en otra parte del circuito.

| Tipo | Siglas | Relación Entrada-Salida | Parámetro de Control ($k$) | Unidades de $k$ |
| :--- | :--- | :--- | :--- | :--- |
| **Tensión controlada por Tensión** | FTCT o VCVS | $v_{out} = \mu \cdot v_x$ | Ganancia de Tensión | Adimensional: $\alpha [V/V]$ |
| **Tensión controlada por Corriente** | FTCC o CCVS | $v_{out} = r_m \cdot i_x$ | Resistencia de Trans. | Ohmios: $\beta [\Omega]$ |
| **Corriente controlada por Tensión** | FCCT o VCCS | $i_{out} = g_m \cdot v_x$ | Transconductancia | Siemens: $\gamma[S]$ |
| **Corriente controlada por Corriente** | FCCC o CCCS | $i_{out} = \beta \cdot i_x$ | Ganancia de Corriente | Adimensional: $\delta[A/A]$ |



> [!Note] Nota sobre Transistores
> El parámetro $\beta$ en la fuente FCCC es el mismo $\beta$ (hFE) que encontrarás en las hojas de datos de los transistores BJT, representando cuánto se amplifica la corriente de base.

# 3. Elementos Pasivos Lineales

## 3.1. El Resistor ($R$)

Elemento que disipa energía eléctrica en forma de calor (efecto Joule) debido a las colisiones de los electrones con la red atómica del material conductor.

* **Ley de Ohm**: $v(t) = R \cdot i(t)$.
* **Conductancia ($G$)**: Es el inverso de la resistencia ($G = 1/R$). Se mide en Siemens ($S$).
    * Ley de Ohm con $G$: $i(t) = G \cdot v(t)$.
* **Potencia**: Al ser siempre pasivo, la potencia siempre es positiva (consumida):
    $$P = v \cdot i = i^2 R = \frac{v^2}{R}$$

### 3.1.1 Interruptores (Switches)

Aunque simples, son la base de la computación digital.
* **Abierto (OFF)**: $i = 0$, $v$ puede ser cualquiera (Equivalente a $R = \infty$).
* **Cerrado (ON)**: $v = 0$, $i$ puede ser cualquiera (Equivalente a $R = 0$).

## 3.2. Condensador o Capacitor ($C$)

Almacena energía en un campo electrico. Depende del material (permitividad, $E_{\varepsilon}$ ) y la geometría (area $A$, y separacion entre sus dos placas $d$ ). Se miden en **Faradios** ($F$).

* **Formula**:$$C = \varepsilon \frac{A}{d}$$

## 3.3. Bobina o Inductor ($L$)

Almacena energía en un campo magnético. Representa la autoinductancia: relación entre el flujo magnetico y la corriente que lo crea. Se mide en **Henrios** ($H$)

* **Formula**: $$\frac{L = N^2 \mu S}{l}$$

> $N$ = Número de espiras de la bobina
> $\mu$ = Permeabilidad del núcleo [$\frac{Wb}{A \cdot m}$]
> $S$ = Sección del núcleo [$m^2$]
> $l$ - Longitud de líneas de flujo [$m$]

# 4. Formas de Conexión

## 4.1. Referencias de Polaridad
- **Referencia Activa**: La corriente sale por el terminal positivo del elemento (fuentes).

- **Referencia Pasiva**: La corriente entra por el terminal positivo del elemento (cargas como resistencias).

## 4.2. Conexion de Elementos

- **Serie**: Los elementos se conectan uno tras otro. La misma corriente circula por todos.

- **Paralelo**: Los elementos se conectan entre los mismos dos nodos. La misma tensión en todos.

### 4.2.1. Resistencias:

- **Serie**: La resistencia equivalente es la sumatoria de las resistencias $R_{eq} = R_1 + R_2 + \dots$

- **Paralelo**: El inverso de resistencia equivalente es la sumatoria del inverso de las resistencias $\frac{1}{R_{eq}} = \frac{1}{R_1} + \frac{1}{R_2} + \dots$

### 3.2.2. Condensadores:

- **Serie**: El inverso de la capacitancia equivalente es la sumatoria del inverso de las capacitancias $\frac{1}{C_{eq}} = \frac{1}{C_1} + \frac{1}{C_2} + \dots$

- **Paralelo**: La capacitancia equivalente es la sumatoria de las capacitancias $C_{eq} = C_1 + C_2 + \dots$

### 3.2.3. Bobinas:

Siguen el mismo comportamiento que las resistencias:
- **Serie**: $L_{eq} = L_1 + L_2 + \dots$

- **Paralelo**: $\frac{1}{L_{eq}} = \frac{1}{L_1} + \frac{1}{L_2} + \dots$

---

## Resumen

En el análisis de circuitos, los componentes se tratan como modelos matemáticos ideales y se clasifican principalmente en dos grupos según su interacción con la energía. Los **elementos activos**, como las fuentes de tensión y corriente (ya sean independientes o controladas por otras variables), actúan como las excitaciones del sistema al ser capaces de suministrar potencia neta. En contraste, los **elementos pasivos** no generan energía por sí mismos; estos se limitan a disiparla en forma de calor, como lo hacen las resistencias mediante la Ley de Ohm, o a almacenarla de forma temporal en campos eléctricos (condensadores) o magnéticos (bobinas).

El comportamiento y el análisis matemático de estos elementos cambian significativamente dependiendo de cómo se conecten entre sí, respetando siempre las referencias de polaridad. En una conexión en **serie**, todos los componentes son atravesados por la misma corriente, mientras que en **paralelo** todos comparten la misma tensión en sus terminales. Al momento de simplificar circuitos, las resistencias y las bobinas comparten la misma lógica matemática (se suman directamente en serie y a la inversa en paralelo), mientras que los condensadores operan de forma exactamente opuesta, sumándose de forma directa solo cuando están en paralelo.

> [!Example] Modelado de un Pin de Salida (GPIO)
> Un pin de salida de un microcontrolador (Arduino/FPGA) no es una fuente de tensión ideal de 5V o 3.3V. Se modela mejor como una fuente de tensión ideal en serie con una resistencia interna ($R_{on}$ del MOSFET de salida, aprox 20-50$\Omega$). Si intentas sacar demasiada corriente, la tensión en el pin caerá según $V_{pin} = V_{DD} - I_{load} \cdot R_{on}$.

## Bibliografía
[**Fraile Mora, J.** - *Circuitos Eléctricos*, Cap. 1]
[**Sedra & Smith** - *Circuitos Microelectrónicos*, Introducción a modelos]
