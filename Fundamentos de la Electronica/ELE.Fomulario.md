# Unidad I  Elementos de Redes Electricas

## Corriente Electrica $A$

$$
i(t) = \frac{dq(t)}{dt}
$$

## Tension (Diferencia de Potencial) $V$

$$
V_{ab} = V(t) = V_A - V_B = \frac{dw}{dq}
$$

## Trabajo diferencial $J$

$$
dw=(V_b - V_a)dq
$$

## Potencia Electrica $W$

$$
p(t)= \frac{dw(t)}{dt} = \frac{dw(t)}{dq(t)} \cdot \frac{dq(t)}{dt}=v(t) \cdot i(t)
$$

## Energia

$$
w(t)=\int_{-\infty}^t  p(t)dt
$$

## Ley de Ohm

- **Valor variable**: $v(t) = R \cdot i(t)$
 
- **Valor constante**: $V = I \cdot R$

## Resistencia $\Omega$

- **Potencia en una resistencia**: $P=V \cdot I = \frac{V^2}{R} = I^2 R$

- **En serie**: $R_{eq} = R_1 + R_2 + \cdots + R_n$

- **En paralelo**: $R_{eq} = (\frac{1}{R_1} + \frac{1}{R_2} + \cdots + \frac{1}{R_n})^{-1}$$

## Capacitor o Condensador $F$

$$
C = \frac{\varepsilon A}{d} = \frac{\varepsilon_0 \varepsilon_r A}{d}
$$

Donde:

- $\varepsilon_0$ Es la constante de permisividad en el vacio
- $\varepsilon_r$ Es la permisividad del material especifico 
- $A$ es el area y $d$ es la distancia entre las placas

- Siguen reglas inversas que las resistencias en serie y en paralelo

## Inductancia $H$

$$
\phi_m (t) = L \cdot i(t)
$$

- Siguen el mismo comportamiento que las resistencias en serie y en paralelo

## Divisor de tension y de corriente 

![[ELE.fa.png]]

## Topologia de Redes 

- **Propiedades**: Si se tiene un árbol de r ramas y n nudos, el número de ramas del árbol es igual al de nudos menos 1.
- **Número de ramas del árbol**: Número nudos – 1 = n – 1
- **Número de eslabones** = igual al número de ramas del grafo menos el número de ramas del árbol:
- **Número de eslabones** = r – (n – 1)  = r – n + 1

## Leyes de Kirchoff 

### 1era Ley 

$$
\sum_{k} i_k (t) = 0 \lor \sum_{entrante} i_{e} (t) = \sum_{saliente} i_{s} (t)
$$

### 2da Ley 

$$
\sum_k v_k (t) = 0
$$


## Circuitos equivalentes

### Teorema de Thevenin 

Cualquier circuito que contenga solo resistencias y fuentes puede ser representado por un circuito mas sencillo de una sola fuente $V_{th}$ y una resistencia $R_{th}$
