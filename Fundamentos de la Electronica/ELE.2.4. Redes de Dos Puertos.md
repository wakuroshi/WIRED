---
materia: Fundamentos de la Electrónica
id: ELE.2.4
tema: Redes de Dos Puertos y Sistemas de Interconexión
status: Revision
tags:
  - AC
  - cuadripolos
  - parámetros
  - interconexión
  - modelado
---

# ELE.2.4. Redes de Dos Puertos (Cuadripolos)

> [!abstract] Abstracción y Modularidad en Ingeniería
> En la ingeniería moderna, un sistema complejo se descompone en bloques funcionales. La teoría de redes de dos puertos permite caracterizar un circuito lineal por su comportamiento externo, sin necesidad de conocer su estructura interna. Según **Fraile Mora (Cap. 12)**, este análisis es fundamental para el estudio de líneas de transmisión, filtros y el modelado de componentes activos como los transistores descritos por **Sedra & Smith**.

---

# 1. Definición y Variables de Estado

Un **puerto** es un par de terminales en el cual la corriente que entra por uno es idéntica a la que sale por el otro. Una red de dos puertos posee un puerto de entrada (puerto 1) y uno de salida (puerto 2). Las variables que definen el sistema son:
- **Tensiones:** $V_1, V_2$ (Fasores en el dominio de la frecuencia).
- **Corrientes:** $I_1, I_2$ (Por convenio, ambas se consideran entrando a la red).

De estas cuatro variables, dos se eligen como independientes y las otras dos como dependientes, lo que da lugar a seis combinaciones posibles de parámetros.

# 2. Matrices de Parámetros Fundamentales

### 2.1. Parámetros de Impedancia ($\mathbf{Z}$)
Se definen expresando las tensiones en función de las corrientes. Son ideales para redes conectadas en **serie**.
$$V_1 = z_{11}I_1 + z_{12}I_2$$
$$V_2 = z_{21}I_1 + z_{22}I_2$$
- $z_{11}, z_{22}$: Impedancias de entrada y salida con el puerto opuesto en circuito abierto.
- $z_{12}, z_{21}$: Impedancias de transferencia.

### 2.2. Parámetros de Admitancia ($\mathbf{Y}$)
Expresan las corrientes en función de las tensiones. Ideales para conexiones en **paralelo**.
$$I_1 = y_{11}V_1 + y_{12}V_2$$
$$I_2 = y_{21}V_1 + y_{22}V_2$$
- Se obtienen mediante ensayos de cortocircuito ($V_k = 0$).

### 2.3. Parámetros Híbridos ($\mathbf{h}$)
Como indica **Sedra & Smith**, estos son los parámetros estándar para modelar el transistor **BJT** en baja frecuencia.
$$V_1 = h_{11}I_1 + h_{12}V_2$$
$$I_2 = h_{21}I_1 + h_{22}V_2$$
- $h_{11}$ ($h_{ie}$): Impedancia de entrada ($\Omega$).
- $h_{21}$ ($h_{fe}$): Ganancia de corriente (Adimensional).

### 2.4. Parámetros de Transmisión ($\mathbf{ABCD}$)
Relacionan las variables del puerto 1 con las del puerto 2. Según **Fraile Mora**, son esenciales para representar cascadas de bloques en líneas de potencia y telecomunicaciones.
$$V_1 = AV_2 - BI_2$$
$$I_1 = CV_2 - DI_2$$

# 3. Propiedades de la Red

### 3.1. Reciprocidad
Una red es recíproca si la relación entre la excitación en un puerto y la respuesta en el otro es la misma al intercambiar los roles.
- En parámetros Z: $z_{12} = z_{21}$.
- En parámetros Y: $y_{12} = y_{21}$.
- En parámetros ABCD: $AD - BC = 1$.

### 3.2. Simetría
Una red es simétrica si sus puertos de entrada y salida pueden intercambiarse sin alterar las corrientes y tensiones externas.
- En parámetros Z: $z_{11} = z_{22}$.
- En parámetros Y: $y_{11} = y_{22}$.
- En parámetros ABCD: $A = D$.

# 4. Modelos Equivalentes en T y $\pi$

Toda red de dos puertos recíproca puede representarse mediante circuitos de tres elementos:
1.  **Modelo en T:** Tres impedancias dispuestas en forma de T, derivadas directamente de los parámetros Z.
2.  **Modelo en $\pi$:** Tres admitancias dispuestas en forma de $\pi$, derivadas de los parámetros Y.


# 5. Interconexión de Redes

Esta es la parte más potente del análisis, ya que permite combinar matrices para hallar el sistema total:
1.  **Cascada:** Se multiplican las matrices de transmisión $\mathbf{T}_{total} = \mathbf{T}_A \cdot \mathbf{T}_B$.
2.  **Serie:** Se suman las matrices $\mathbf{Z}_{total} = \mathbf{Z}_A + \mathbf{Z}_B$.
3.  **Paralelo:** Se suman las matrices $\mathbf{Y}_{total} = \mathbf{Y}_A + \mathbf{Y}_B$.
4.  **Híbrida:** Se suman las matrices $\mathbf{h}_{total} = \mathbf{h}_A + \mathbf{h}_B$.

---

## Resumen
- Los cuadripolos permiten "encapsular" la complejidad de un circuito lineal.
- **Transistores:** Se modelan con parámetros $h$ o $g$ (híbridos inversos).
- **Líneas de transmisión:** Se modelan con parámetros de transmisión $ABCD$ para facilitar el cálculo en cascada.
- **Análisis:** La elección del tipo de parámetro depende de cómo se conecte la red al resto del sistema.

> [!Example] Aplicación en Computación: Modelado de Interconexiones (Interconnects)
> En el diseño de circuitos integrados (VLSI), las pistas que conectan diferentes bloques funcionales dentro de un chip no son conductores ideales. A frecuencias de GHz, una pista se modela como una cascada de cuadripolos (redes RLC). Multiplicando sus matrices $ABCD$, los ingenieros pueden predecir el retardo de propagación y la degradación de la señal de reloj antes de fabricar el silicio.

## Bibliografía
[**Fraile Mora, J.** - *Circuitos Eléctricos*, Cap. 12.]
[**Sedra & Smith** - *Circuitos Microelectrónicos*, Apéndice B.]
[**Material de Cátedra (OCW-CCE)** - Introducción a los transistores y modelos de pequeña señal.]