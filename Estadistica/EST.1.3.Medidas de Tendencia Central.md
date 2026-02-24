---
materia: Estadística
id: EST.1.2
tema: Distribuciones de Frecuencia y Visualización de Alta Densidad
status: Terminado
tags: [frecuencias, histogramas, sturges, visualización, ingeniería]
---

# EST.1.2. Distribuciones de Frecuencia y Visualización

> [!abstract] El Análisis Exploratorio de Datos (EDA)
> El primer paso de un ingeniero ante un dataset masivo no es calcular la media, sino entender cómo se distribuyen los datos. La visualización científica permite identificar patrones, lagunas en la recolección y la presencia de valores atípicos que podrían invalidar modelos futuros.

---

# 1. Organización de Datos Agrupados (Discretización)

Cuando el tamaño de la muestra $n$ es considerable, la lista de datos brutos es inmanejable. Agrupamos los datos en **clases** o intervalos para observar la densidad.

### 1.1. Determinación Científica del Número de Clases ($K$)
No debe ser arbitrario. Si $K$ es muy pequeño, perdemos la forma; si es muy grande, vemos ruido.
- **Regla de Sturges:** $K = 1 + 3.322 \log_{10}(n)$. Es la base del software moderno, asumiendo una distribución aproximadamente normal.
- **Regla de Scott:** $h = \frac{3.49s}{n^{1/3}}$ (donde $h$ es el ancho de clase). Más robusta que Sturges para datos con outliers.
- **Regla de Freedman-Diaconis:** Utiliza el rango intercuartílico para definir el ancho, siendo menos sensible a valores extremos que la regla de Scott.

### 1.2. Amplitud e Intervalos
$$A = \frac{R}{K} = \frac{x_{max} - x_{min}}{K}$$
- **Límites de Clase:** Deben definirse para evitar ambigüedad (usualmente cerrados por la izquierda y abiertos por la derecha: $[L_{inf}, L_{sup})$).
- **Marca de Clase ($x_i$):** El punto medio del intervalo. $x_i = \frac{L_{inf} + L_{sup}}{2}$. Es el valor que representa a toda la clase en cálculos algebraicos.

# 2. Tipos de Frecuencias: Formalismo Matemático

Sea una partición del rango en $K$ clases:

1.  **Frecuencia Absoluta ($f_i$):** Conteo de observaciones en el intervalo $i$. Propiedad fundamental: $\sum_{i=1}^{K} f_i = n$.
2.  **Frecuencia Relativa ($h_i$):** Proporción del total. $h_i = \frac{f_i}{n}$. Representa la probabilidad empírica de que un dato caiga en ese rango.
3.  **Frecuencia Acumulada ($F_i$):** Suma parcial $\sum_{j=1}^{i} f_j$. Es la base para el cálculo de la Función de Distribución Acumulada (CDF) empírica.

# 3. Herramientas de Visualización Técnica

### 3.1. Histograma vs. Diagrama de Barras
- El **Histograma** se usa para variables continuas. No hay espacio entre barras porque el eje X representa una escala numérica real.
- **Densidad:** En un histograma riguroso, el eje Y debe representar la densidad ($h_i / A$), no solo la frecuencia, para que el área total del gráfico sea igual a 1.



[Image of Histogram vs Bar Chart comparison]


### 3.2. Ojiva (Gráfico de Frecuencia Acumulada)
Gráfico lineal que une los puntos $(L_{sup, i}, F_i)$. 
- **Utilidad:** Permite interpolar percentiles de forma visual. Es la herramienta principal para análisis de fiabilidad (ej. ¿qué porcentaje de motores fallan antes de las 1000 horas?).

### 3.3. Diagrama de Pareto
Combinación de histograma ordenado de mayor a menor con una ojiva de porcentaje acumulado.
- **Principio de Pareto (80/20):** En ingeniería de calidad, ayuda a identificar el 20% de las causas que generan el 80% de los defectos.

### 3.4. Boxplot (Diagrama de Caja y Bigotes) de Tukey
Representa la distribución mediante cinco estadísticos de posición (mínimo, $Q_1$, mediana, $Q_3$, máximo).
- **Valla de Outliers:** Se define el Rango Intercuartílico $IQR = Q_3 - Q_1$. Cualquier dato $x < Q_1 - 1.5(IQR)$ o $x > Q_3 + 1.5(IQR)$ es un **outlier** candidato a ser investigado.



# 4. Errores de Interpretación Gráfica

Un ingeniero debe evitar:
- **Interpolación lineal en el histograma:** Los datos dentro de una clase se asumen distribuidos uniformemente, lo cual es solo una aproximación.
- **Sesgo de Ancho de Clase:** Alterar $A$ para "forzar" que la distribución parezca normal o bimodal.

---

## Resumen Técnico
- La **Regla de Sturges** es un estándar, pero para muestras muy grandes ($n > 1000$), la regla de **Scott** es matemáticamente superior.
- El **Boxplot** es preferible al histograma para comparar la variabilidad entre diferentes procesos o turnos de trabajo.
- La **Marca de Clase** introduce un error de agrupamiento; a mayor $K$, menor error pero menor síntesis de información.

## Bibliografía
- Tufte, E. R. - *The Visual Display of Quantitative Information*.
- Tukey, J. W. - *Exploratory Data Analysis*.