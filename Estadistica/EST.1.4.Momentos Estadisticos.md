---
materia: Estadística
id: EST.1.3
tema: Momentos Estadísticos, Dispersión y Morfología
status: Terminado
tags: [momentos, varianza, sesgo, curtosis, bessel, ingeniería]
---

# EST.1.3. Teoría de los Momentos y Forma

> [!abstract] La Caracterización Matemática del Dato
> Un conjunto de datos no está descrito totalmente por su promedio. En ingeniería, la "morfología" de la distribución (su inclinación y el grosor de sus extremos) es lo que define el riesgo. La teoría de momentos permite parametrizar cualquier forma de distribución.

---

# 1. Definición Formal de Momentos

En física, un momento describe la distribución de masa. En estadística, describe la distribución de probabilidad.

### 1.1. Momento respecto al origen de orden $k$ ($m'_k$)
$$m'_k = \frac{\sum x_i^k}{n}$$
El primer momento respecto al origen ($k=1$) es la **Media Aritmética**.

### 1.2. Momento central de orden $k$ ($m_k$)
Se calcula respecto a la media:
$$m_k = \frac{\sum (x_i - \bar{x})^k}{n}$$
El segundo momento central ($k=2$) es la base de la **Varianza**.

# 2. Medidas de Localización (1er Momento)

### 2.1. Media Aritmética ($\bar{x}$)
Es el punto de equilibrio o centro de gravedad.
- **Propiedad Fundamental:** $\sum (x_i - \bar{x}) = 0$.
- **Sensibilidad:** Es altamente inestable ante outliers.

### 2.2. Mediana ($Me$) y Moda ($Mo$)
- **Mediana:** El valor que minimiza la suma de las desviaciones absolutas $\sum |x_i - c|$. Es una medida **robusta**.
- **Moda:** El valor de máxima densidad. Una distribución bimodal en ingeniería suele indicar la mezcla de dos poblaciones (ej. piezas de dos proveedores distintos).

# 3. Medidas de Dispersión (2do Momento)

### 3.1. Varianza y la Corrección de Bessel
Para una muestra, la varianza se define con denominador $n-1$:
$$s^2 = \frac{\sum (x_i - \bar{x})^2}{n-1}$$
- **¿Por qué $n-1$?** Al usar $\bar{x}$ (media muestral) en lugar de $\mu$ (media poblacional), perdemos un **grado de libertad**. Dividir por $n$ produciría un estimador sesgado que subestima la varianza real. La división por $n-1$ es el factor de corrección necesario para que $E[s^2] = \sigma^2$.

### 3.2. Coeficiente de Variación ($CV$)
$$CV = \frac{s}{|\bar{x}|} \times 100\%$$
Es una medida de dispersión relativa. En control de procesos, un $CV > 30\%$ suele indicar que el proceso está fuera de control o que la media no es un representante fiel.

# 4. Medidas de Forma (3er y 4to Momento)

### 4.1. Asimetría o Sesgo (Skewness)
Basado en el 3er momento central estandarizado.
$$g_1 = \frac{m_3}{s^3}$$
- **$g_1 > 0$ (Positiva):** La cola derecha es más larga. Media > Mediana.
- **$g_1 < 0$ (Negativa):** La cola izquierda es más larga. Media < Mediana.



### 4.2. Curtosis o Apuntamiento (Kurtosis)
Basado en el 4to momento central. Mide la concentración en las colas (Outliers).
$$g_2 = \frac{m_4}{s^4} - 3$$
- **Mesocúrtica ($g_2 = 0$):** Similar a la Distribución Normal.
- **Leptocúrtica ($g_2 > 0$):** Colas "pesadas". Los eventos extremos son más probables de lo esperado por una Normal. Riesgo alto.
- **Platicúrtica ($g_2 < 0$):** Distribución aplanada. Colas delgadas.



# 5. Teoremas de Concentración de Datos

### 5.1. Regla Empírica (Solo para Normales)
- $68\%$ dentro de $\pm 1\sigma$
- $95\%$ dentro de $\pm 2\sigma$
- $99.7\%$ dentro de $\pm 3\sigma$ (Base de la metodología Six Sigma).

### 5.2. Teorema de Chebyshev (Universal)
Válido para cualquier distribución, sin importar su forma. Establece que la proporción de datos que cae dentro de $k$ desviaciones estándar es **al menos**:
$$P(|X - \mu| < k\sigma) \geq 1 - \frac{1}{k^2}$$
*Ejemplo:* Al menos el $75\%$ de los datos de cualquier proceso estarán siempre dentro de $\pm 2s$.

---

## Resumen Técnico
- La **Media** es un modelo de localización; la **Varianza** es el error cuadrático de ese modelo.
- El **Sesgo** y la **Curtosis** son críticos en ingeniería financiera y de confiabilidad para predecir fallas catastróficas.
- La **Corrección de Bessel** es la diferencia entre hacer estadística descriptiva (población) e inferencial (muestra).

## Bibliografía
- Casella, G. & Berger, R. L. - *Statistical Inference*.
- Fisher, R. A. - *Statistical Methods for Research Workers*.