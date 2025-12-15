# Distribución de Variables Discretas

Son aquellas que describen la probabilidad de que una **variable aleatoria discreta** tome valores **contables** (generalmente números enteros).  
La probabilidad siempre está entre **0 y 1** y la suma de todas las probabilidades es **1**.

## 1. Distribución Bernoulli

Modela un experimento con **dos posibles resultados**:

- Éxito con probabilidad $p$
- Fracaso con probabilidad $q = 1 − p$

$N$ población

Variable aleatoria:
- $X \in \{0,1\}$

$$
P(X=1)=p \qquad P(X=0)=q
$$

**Esperanza**
$$
\mu = p
$$

**Varianza**
$$
\sigma^2 = p \cdot q
$$

## 2. Distribución Binomial

Modela el número de éxitos en **N ensayos independientes** con probabilidad de éxito constante **p**.

$$
P(X=x)=\binom{N}{x} p^x q^{N-x}
$$

Donde:
- $N$: número de ensayos  
- $x$: número de éxitos  
- $p$: probabilidad de éxito  
- $q=1-p$: probabilidad de fracaso  

**Esperanza**
$$
\mu = N \cdot p
$$

**Varianza**
$$
\sigma^2 = N \cdot p \cdot q
$$

**Desviación estándar**
$$
\sigma = \sqrt{N p q}
$$

## 3. Distribución Geométrica

Estudia el número de intentos necesarios **hasta obtener el primer éxito**.

$$
P(X=x)=q^{x-1} p
$$

Donde:
- $x = 1,2,3,\dots$

**Esperanza**
$$
\mu=\frac{1}{p}
$$

**Varianza**
$$
\sigma^2=\frac{q}{p^2}
$$

## 4. Distribución Hipergeométrica

Modela experimentos **sin reemplazo** en poblaciones finitas.

$$
P(X=x)=\frac{\binom{K}{x}\binom{N-K}{n-x}}{\binom{N}{n}}
$$

Donde:
- $N$: tamaño de la población  
- $K$: éxitos en la población  
- $n$: tamaño de la muestra  
- $x$: éxitos en la muestra  

## 5. Distribución de Poisson

Estudia el número de éxitos que ocurren en un **intervalo fijo de tiempo o espacio** cuando ocurren de forma aleatoria.

$$
P(X=x)=\frac{\lambda^x e^{-\lambda}}{x!}
$$

Donde:
- $\lambda$: tasa promedio de ocurrencia  
- $x$: número de eventos  

> **Nota:**  
> Cuando el intervalo cambia, **$\lambda$ también cambia** proporcionalmente.

**Esperanza y Varianza**
$$
\mu=\sigma^2=\lambda
$$

## 6. Distribución Uniforme Discreta

Todos los valores posibles tienen la **misma probabilidad**.

$$
P(X=x)=\frac{1}{n}
$$

# Ejercicios

## Ejercicio 1

El **18%** de los artículos fabricados son defectuosos. Se seleccionan **5 artículos**.

Datos:
- $p=0.18$
- $q=0.82$
- $n=5$
- $x=2$

$$
P(X=2)=\binom{5}{2}(0.18)^2(0.82)^3
$$

$$
P(X=2)=0.178
$$

**Respuesta:**  
Existe aproximadamente un **17.8%** de probabilidad de que salgan **2 defectuosos**.

Un tratamiento tiene probabilidad de éxito del **90%** y se aplica a **5 pacientes**.

Datos:
- $p=0.9$
- $q=0.1$
- $n=5$

### a) Probabilidad de que **3 pacientes sanen**

$$
P(X=3)=\binom{5}{3}(0.9)^3(0.1)^2=0.0729
$$

### b) Probabilidad de que **al menos 4 pacientes sanen**

> **Nota:**  
> En estadística, *“al menos n”* se interpreta como:
> $$
> P(X \ge n)
> $$

$$
P(X\ge4)=P(X=4)+P(X=5)=0.918
$$

## Ejercicio 2

La probabilidad de vender un seguro es **25%**. Se contactan **10 clientes**.

Datos:
- $p=0.25$
- $q=0.75$
- $n=10$

$$
P(X\ge1)=1-P(X=0)
$$

$$
P(X=0)=(0.75)^{10}=0.0563
$$

$$
P(X\ge1)=0.9437
$$

## Ejercicio 3 (Poisson)

Los clientes ingresan a una tienda a una tasa de **0.4 clientes por minuto**.

$$
\lambda=0.4
$$

### a) Ningún cliente en 1 minuto

$$
P(X=0)=e^{-0.4}=0.6703
$$

### b) Exactamente 2 clientes

$$
P(X=2)=\frac{0.4^2 e^{-0.4}}{2!}=0.0536
$$

### c) Al menos 2 clientes

$$
P(X\ge2)=1-[P(0)+P(1)]=0.0616
$$

### d) Al menos 2 clientes en 10 minutos

$$
\lambda=4
$$

$$
P(X\ge2)=1-(e^{-4}+4e^{-4})=0.9084
$$


