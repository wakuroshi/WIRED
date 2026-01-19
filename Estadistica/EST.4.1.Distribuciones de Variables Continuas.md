# 1.Definición
La distribuciones de las variables continuas describen la probabilidad de variables que pueden tomar cualquier valor dentro de un rango (altura, peso), no necesariamente son números enteros, se usa la función densidad poblacional representada por la siguiente fórmula:
**Función densidad:** $f(x)=\int_{a}^b \lambda \cdot e^{-\lambda x} dx$
# 2.Tipos
## 2.1.Distribución Normal
Se usa para modelar fenómenos medibles, como la altura, peso, temperatura, tiempo, donde los valores no están restringidos a números enteros y hay un número infinitos de probabilidades dentro de un rango determinado. 
![[EST.4.1.fa.png]]
### 2.1.1.Ejemplo
La estatura de un grupo de personas escogidas al azar tiene una media de 170 cm, con una desviación estándar de 10 cm ¿Cuál es la probabilidad de que una persona mida menos de 165 cm?
$x\sim N(\mu,\sigma )$ x que se reparte uniformemente en N
$x \sim N(170, 10)$
$P(140< x < 200)$
$P(a<x<b)$
$Z=\dfrac{{x-\mu}}{\sigma}$ -> $Z= \dfrac{{165 - 170}}{10} = -0.5$   **Z tabulado:** 0.3085
**Respuesta:** La probabilidad de que salga una persona con estatura menor a 165 cm es de 30.85%
Tabla de Z 
¿Qué porcentaje de la población tiene una estatura menor de 180 cm si la desviación estándar es de 8 cm manteniendo la media de 170 cm?
$x \sim N(\mu, \sigma)$
$x \sim N(170, 8)$
x: % de la población con estatura menor a 180 cm
$Z= \dfrac{{180 - 170}}{8}=\dfrac{5}{4}=1.25$ **Z tambulado:** 0.8944
$P(x<180)=P(z<1.25)$
**Respuesta:** La probabilidad de que salga una persona con estatura menor a 180 es de 89.44%
### 2.1.2.Ejemplo 2
El peso de una caja de manzanas de exportación se distribuye normalmente con una media de 20 kg y una desviación estándar de 0.4. Calcule:
**a)** ¿Qué porcentaje de las cajas pesa más de 20.5 kg
$P(\mu, \sigma)$
$x \sim N(20, 0.4)\to P(20, 0.4)$ 
$Z= 1- \dfrac{{20.5-20}}{0.4}=1.25 \to P(x>0.4)=P(z>0.88)$
P(z>1.25)=1-0.8944= 0.1056
**Probabilidad:** 10.56%
**Respuesta:** La probabilidad de que el peso de una caja de manzanas pese más de 20.5 kg es de 10.56%

**b)** ¿Qué porcentaje de las cajas pesa menos de 19.5 kg
$P(x<19.5)$
$Z=\dfrac{{19.5-20}}{0.4} = -1.25$
$P(z< -1.25)=0.1056$
**Respuesta:** La probabilidad de que el pesa de una caja de manzanas pese menos de 19.5 kg es de 10.56

**c)** Si una caja debe pesar de 19 y 21 kg ¿Qué porcentaje de las cajas cumplen con ese peso 
$P(19<x<21)$
$Z_{1}=\dfrac{{19-20}}{0.4}=-2.5$ Límite a
$Z_{2}=\dfrac{{21-20}}{0.4}=2.5$ Límite b
$P(-2.5 < z < 2.5)$
$P(Z< -2.5)=0.0062$
$P(Z< 2.5)=0.9938$
$P(-2.5<z<2.5)=0.9938 - 0.0062 = 0.9876$
**Respuesta:** La probabilidad de que una caja esté en el intervalo entre 19 kg y 21 kg es de 98.76%
### 2.1.3.Ejercicio 3
Un profesional de la salud tomó la presión arterial a 5000 personas donde obtuvo medidas de la presión sistólica entre 88 y 152. Calcule el porcentaje de población que está en un rango normal (90, 139)
Media ($\mu$): $\dfrac{{152+88}}{2}= 120$
Desviación ($\sigma$): $152-88=64$ esto equivale a $3\sigma$ a la izquierda y $3\sigma$ a la derecha
$(3+3)\sigma = 64 \to \sigma = \dfrac{64}{6}=10.66$
$P(\mu, \sigma)$
$x \sim N(\mu, \sigma)$

$Z=\dfrac{{x-\mu}}{\sigma}$
$Z_{1}=\dfrac{{90 - 120}}{10.66} =-\dfrac{45}{16}=-2.81$ Z tabulada = 0.0025
$Z_{2}=\dfrac{{139-120}}{10.66}=\dfrac{57}{32}=1.78$  Z tabulada = 0.9625
$Porcentaje=Z_{1}-Z_{2}=0.96=96\%$
**Respuesta:** La probabilidad de que la población esté en un rango normal de presión arterial sea normal es del 96% 

Desviación estándar:  
$P()$
-> Z estándar 
-> Z acumulado cola derecha, cola izquierda
-> Z valores tabulador desde la u hacia la cola

## 2.2.Distribución Exponencial
## 2.3.Distribución Uniforme