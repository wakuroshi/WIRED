---
tags:
  - Estadistica
---
# 1. Definición
Es el proceso que se utiliza para conocer las características de un parámetro poblacional mediante el conocimiento de la muestra. Esto permite que con una muestra tamaño *n* se pueda inferir en el valor del parámetro de una población.
**Conceptos fundamentales:**
- **Estimador:** Es una **regla o fórmula** (un estadístico) que se aplica a los datos muestrales para proporcionar una aproximación del parámetro poblacional. Por ejemplo, la media muestral ( $\bar{x}$ ) es un estimador de la media poblacional ( $\mu$ ).
   
- **Estimación:** Es el **valor numérico específico** que resulta de aplicar el estimador a una muestra concreta. Si en una muestra de 5 personas sus alturas son \[170, 175, 180, 165, 172] cm, la estimación de $\mu$ sería $\bar{x} = 172.4$ cm.

- **Estadístico:** Es una medida descriptiva obtenida de una muestra. (Media muestral $\bar{x}$, desviación estándar muestral $s$, varianza muestral $s^2$, proporción muestral $\hat{p}$).
   
- **Parámetro:** Es una medida descriptiva fija (pero generalmente desconocida) de una población. (Media poblacional $\mu$, desviación estándar poblacional $\sigma$, varianza poblacional $\sigma^2$, proporción poblacional $p$).

Para ello se requiere:

- **Intervalo de Confianza (IC):** Es un rango de valores (intervalo) que, con un determinado nivel de confianza, se estima que contiene al verdadero parámetro poblacional. La forma incorrecta de expresarlo sería "hay un 95% de probabilidad de que $\mu$ esté en el intervalo", la forma correcta es "el 95% de los intervalos construidos con este método contendrán a $\mu$".

- **Nivel de Confianza (1 - $\alpha$):** Es la probabilidad (usualmente expresada en porcentaje) de que el intervalo de confianza contenga al verdadero parámetro poblacional. Un nivel de confianza del 95% ( $\alpha = 0.05$ ) significa que si tomáramos 100 muestras y construyéramos 100 intervalos, esperaríamos que 95 de ellos contuvieran el parámetro. El valor Z crítico para un 95% es efectivamente $\pm 1.96$.
   
- **Error de Estimación Admisible (E):** Es la **mitad de la amplitud** del intervalo de confianza. Representa la máxima diferencia que estamos dispuestos a aceptar entre el estadístico de la muestra y el parámetro de la población. Es el "margen de error" que vemos en las encuestas.


---

# **2. Tipos de Estimación**

#### **Definición**

- **Estimación Puntual:** Utiliza un único valor (un estadístico) para estimar el parámetro poblacional. Es simple pero no da información sobre la precisión o confiabilidad de la estimación.  
    _Ejemplo: Estimar que la altura promedio de los estudiantes universitarios ( $\mu$ ) es exactamente 1.72 m._

- **Estimación por Intervalos:** Utiliza un rango de valores (intervalo) para estimar el parámetro. Proporciona información sobre la precisión de la estimación a través del nivel de confianza.  
    _Ejemplo: Estimar que la altura promedio de los estudiantes universitarios ( $\mu$ ) está entre 1.68 m y 1.76 m, con un 95% de confianza._


---

# **3. Resolución de Ejercicios, Fórmulas y Aplicación**

#### **3.1.Intervalo de Confianza para la Media Poblacional ( $\mu$ )**

**Caso 1: Cuando se conoce la Desviación Estándar Poblacional ( $\sigma$ ) o $n > 30$**  
Se utiliza la distribución Z.

**Fórmula:**  
$\text{Intervalo de confianza}=\bar{x}±Z_{α/2}⋅\dfrac{σ}{\sqrt{ n }}$
**Valores críticos de Z**

| Nivel de Confianza | α (total) | α/2 (cada cola) | Valor Z crítico |
| ------------------ | --------- | --------------- | --------------- |
| 90%                | 0.10      | 0.05            | ±1.645          |
| 95%                | 0.05      | 0.025           | ±1.960          |
| 99%                | 0.01      | 0.005           | ±2.576          |
| 99.9%              | 0.001     | 0.0005          | ±3.291          |

**Significado**

- $\bar{x}$: Media de nuestra muestra.
- $Z_{\alpha/2}$: Valor crítico de la distribución Z para un nivel de confianza dado. Para 95% es 1.96, para 90% es 1.645, para 99% es 2.576.   
- $\sigma$: Desviación estándar poblacional (si no se conoce y $n > 30$, se usa la desviación estándar muestral $s$).
- $n$: Tamaño de la muestra.
- $\frac{\sigma}{\sqrt{n}}$: **Error Estándar** de la media. Mide la variabilidad de las medias muestrales.


**Ejemplo Práctico:**  
Queremos estimar el peso promedio de los recién nacidos en una ciudad. Se toma una muestra de 50 bebés ($n=50$), obteniendo una media de 3.4 kg ($\bar{x}=3.4$). Por estudios anteriores, se sabe que la desviación estándar poblacional es de 0.5 kg ($\sigma=0.5$). Construye un IC del 95%.

1. **Identifica los datos:** $\bar{x}=3.4$, $\sigma=0.5$, $n=50$, Nivel de Confianza = 95% → $Z_{\alpha/2}=1.96$.
2. **Calcula el Error Estándar:** $\frac{\sigma}{\sqrt{n}} = \frac{0.5}{\sqrt{50}} \approx 0.0707$
3. **Calcula el Margen de Error (E):** $E = Z \cdot \text{Error Estándar} = 1.96 \cdot 0.0707 \approx 0.1386$
4. **Construye el Intervalo:**
    - Límite Inferior: $\bar{x} - E = 3.4 - 0.1386 = 3.2614$
    - Límite Superior: $\bar{x} + E = 3.4 + 0.1386 = 3.5386$

**Conclusión:** Con un 95% de confianza, el peso promedio poblacional de los recién nacidos ( $\mu$ ) se encuentra entre **3.26 kg y 3.54 kg**.

---

**Caso 2: Cuando NO se conoce $\sigma$ y $n < 30$**  
Se utiliza la distribución t de Student.
**Tabla de Distribución t de Student**

| gl  | 80% (0.10) | 90% (0.05) | 95% (0.025) | 98% (0.01) | 99% (0.005) | 99.8% (0.001) | 99.9% (0.0005) |
| --- | ---------- | ---------- | ----------- | ---------- | ----------- | ------------- | -------------- |
| 1   | 3.078      | 6.314      | 12.706      | 31.821     | 63.657      | 318.309       | 636.619        |
| 2   | 1.886      | 2.920      | 4.303       | 6.965      | 9.925       | 22.327        | 31.599         |
| 3   | 1.638      | 2.353      | 3.182       | 4.541      | 5.841       | 10.215        | 12.924         |
| 4   | 1.533      | 2.132      | 2.776       | 3.747      | 4.604       | 7.173         | 8.610          |
| 5   | 1.476      | 2.015      | 2.571       | 3.365      | 4.032       | 5.893         | 6.869          |
| 6   | 1.440      | 1.943      | 2.447       | 3.143      | 3.707       | 5.208         | 5.959          |
| 7   | 1.415      | 1.895      | 2.365       | 2.998      | 3.499       | 4.785         | 5.408          |
| 8   | 1.397      | 1.860      | 2.306       | 2.896      | 3.355       | 4.501         | 5.041          |
| 9   | 1.383      | 1.833      | 2.262       | 2.821      | 3.250       | 4.297         | 4.781          |
| 10  | 1.372      | 1.812      | 2.228       | 2.764      | 3.169       | 4.144         | 4.587          |
| 11  | 1.363      | 1.796      | 2.201       | 2.718      | 3.106       | 4.025         | 4.437          |
| 12  | 1.356      | 1.782      | 2.179       | 2.681      | 3.055       | 3.930         | 4.318          |
| 13  | 1.350      | 1.771      | 2.160       | 2.650      | 3.012       | 3.852         | 4.221          |
| 14  | 1.345      | 1.761      | 2.145       | 2.624      | 2.977       | 3.787         | 4.140          |
| 15  | 1.341      | 1.753      | 2.131       | 2.602      | 2.947       | 3.733         | 4.073          |
| 16  | 1.337      | 1.746      | 2.120       | 2.583      | 2.921       | 3.686         | 4.015          |
| 17  | 1.333      | 1.740      | 2.110       | 2.567      | 2.898       | 3.646         | 3.965          |
| 18  | 1.330      | 1.734      | 2.101       | 2.552      | 2.878       | 3.610         | 3.922          |
| 19  | 1.328      | 1.729      | 2.093       | 2.539      | 2.861       | 3.579         | 3.883          |
| 20  | 1.325      | 1.725      | 2.086       | 2.528      | 2.845       | 3.552         | 3.850          |
| 21  | 1.323      | 1.721      | 2.080       | 2.518      | 2.831       | 3.527         | 3.819          |
| 22  | 1.321      | 1.717      | 2.074       | 2.508      | 2.819       | 3.505         | 3.792          |
| 23  | 1.319      | 1.714      | 2.069       | 2.500      | 2.807       | 3.485         | 3.768          |
| 24  | 1.318      | 1.711      | 2.064       | 2.492      | 2.797       | 3.467         | 3.745          |
| 25  | 1.316      | 1.708      | 2.060       | 2.485      | 2.787       | 3.450         | 3.725          |
| 26  | 1.315      | 1.706      | 2.056       | 2.479      | 2.779       | 3.435         | 3.707          |
| 27  | 1.314      | 1.703      | 2.052       | 2.473      | 2.771       | 3.421         | 3.690          |
| 28  | 1.313      | 1.701      | 2.048       | 2.467      | 2.763       | 3.408         | 3.674          |
| 29  | 1.311      | 1.699      | 2.045       | 2.462      | 2.756       | 3.396         | 3.659          |
| 30  | 1.310      | 1.697      | 2.042       | 2.457      | 2.750       | 3.385         | 3.646          |
| 40  | 1.303      | 1.684      | 2.021       | 2.423      | 2.704       | 3.307         | 3.551          |
| 50  | 1.299      | 1.676      | 2.009       | 2.403      | 2.678       | 3.261         | 3.496          |
| 60  | 1.296      | 1.671      | 2.000       | 2.390      | 2.660       | 3.232         | 3.460          |
| 80  | 1.292      | 1.664      | 1.990       | 2.374      | 2.639       | 3.195         | 3.416          |
| 100 | 1.290      | 1.660      | 1.984       | 2.364      | 2.626       | 3.174         | 3.390          |
| 120 | 1.289      | 1.658      | 1.980       | 2.358      | 2.617       | 3.160         | 3.373          |
| ∞   | 1.282      | 1.645      | 1.960       | 2.326      | 2.576       | 3.090         | 3.291          |

**Fórmula:**  
$\bar{x}\pm t_{\alpha / 2,gl} \cdot \dfrac{s}{\sqrt{ n }}$

**Significado**

- $\bar{x}$: Media de nuestra muestra.
- $t_{\alpha/2, gl}$: Valor crítico de la distribución t. Depende del nivel de confianza y de los **grados de libertad (gl)**, que son $gl = n - 1$. 
- $s$: Desviación estándar de la muestra.
- $n$: Tamaño de la muestra.

**Ejemplo Práctico:**  
Se quiere estimar el tiempo promedio que tarda un algoritmo en ejecutarse. Se realizan 10 mediciones ($n=10$). La media muestral es de 15 ms ($\bar{x}=15$) y la desviación estándar muestral es de 2 ms ($s=2$). Construye un IC del 99%.

1. **Identifica los datos:** $\bar{x}=15$, $s=2$, $n=10$, Nivel de Confianza = 99%.
2. **Calcula los grados de libertad:** $gl = n - 1 = 10 - 1 = 9$.
3. **Busca el valor t crítico:** Para 99% de confianza y $gl=9$, $t_{\alpha/2, 9} \approx 3.250$ (se busca en una tabla t de Student).
4. **Calcula el Error Estándar:** $\frac{s}{\sqrt{n}} = \frac{2}{\sqrt{10}} \approx 0.6325$
5. **Calcula el Margen de Error (E):** $E = t \cdot \text{Error Estándar} = 3.250 \cdot 0.6325 \approx 2.055$
6. **Construye el Intervalo:**
    - Límite Inferior: $15 - 2.055 = 12.945$
    - Límite Superior: $15 + 2.055 = 17.055$

**Conclusión:** Con un 99% de confianza, el tiempo promedio poblacional de ejecución ( $\mu$ ) se encuentra entre **12.95 ms y 17.06 ms**.

---
#### 3.2.Estimación de una Porción Poblacional
Es el proceso de utilizar la información de una muestra para inferir o predecir el valor desconocido de la proporción de la población con la característica del estudio. Se utiliza la fórmula general:
$p\pm(Z\cdot Es)$ = Intervalo de confianza

**Significado**
- Es: Error estándar
- p: Porcentaje de sujetos con la característica del estudio
- q: Porcentaje de sujetos sin la característica del estudio
- n: Tamaño de la muestra
- Z: Valor crítico (se busca en la tabla de área de la curva según nivel de confianza)

$Es=\sqrt{\dfrac{p\cdot q}{n} }$
Por ejemplo:
El investigador encontró que en una muestra de 144 niños, el 7% de ellos presentaba algún grado de desnutrición. Se desea conocer, con el 99% de confianza, ¿Cuál es el porcentaje de niños desnutridos en esa población de escolares?

p: 7%
q:(100%-p)=100%-7%=93%
n: 144
Z: 2,58

$Es=\sqrt{ \dfrac{7\cdot 93}{144} }$
$Es=2.13$

$7\% \pm(2.58 \cdot 2.13)$
$7\%\pm 5.50$
Límite superior 12.50% (7%+5.50)
Límite inferior 1.50% (7%-5.50)

Es decir, el porcentaje de niños en desnutrición no debe ser menor al 1.50% ni mayor al 12.50%, esto con una confianza de 99% y un riesgo de equivocación de 1%

---
#### 3.3.Estimación de Intervalos
Se utilizan datos de una muestra para crear un rango de valores (intervalo) que probablemente contenga el verdadero parámetro de la población.

**Tabla de Área Bajo la Curva**
El lado derecho es el comienzo del número decimal, la parte superior es el segundo dígito o el dígito inmediato de Z, por ejemplo, si Z es 3.54 se busca en el lado izquierdo 3.5 y en el superior 0.04, lo cual sería 0.4998.

| z   | 0      | 0.01   | 0.02   | 0.03   | 0.04   | 0.05   | 0.06   | 0.07   | 0.08   | 0.09   |
| --- | ------ | ------ | ------ | ------ | ------ | ------ | ------ | ------ | ------ | ------ |
| 0.0 | 0.0000 | 0.0040 | 0.0080 | 0.0120 | 0.0160 | 0.0199 | 0.0239 | 0.0279 | 0.0319 | 0.0359 |
| 0.1 | 0.0398 | 0.0438 | 0.0478 | 0.0517 | 0.0557 | 0.0596 | 0.0636 | 0.0675 | 0.0714 | 0.0753 |
| 0.2 | 0.0793 | 0.0832 | 0.0871 | 0.0910 | 0.0948 | 0.0987 | 0.1026 | 0.1064 | 0.1103 | 0.1141 |
| 0.3 | 0.1179 | 0.1217 | 0.1255 | 0.1293 | 0.1331 | 0.1368 | 0.1406 | 0.1443 | 0.1480 | 0.1517 |
| 0.4 | 0.1554 | 0.1591 | 0.1628 | 0.1664 | 0.1700 | 0.1736 | 0.1772 | 0.1808 | 0.1844 | 0.1879 |
| 0.5 | 0.1915 | 0.1950 | 0.1985 | 0.2019 | 0.2054 | 0.2088 | 0.2123 | 0.2157 | 0.2190 | 0.2224 |
| 0.6 | 0.2257 | 0.2291 | 0.2324 | 0.2357 | 0.2389 | 0.2422 | 0.2454 | 0.2486 | 0.2517 | 0.2549 |
| 0.7 | 0.2580 | 0.2611 | 0.2642 | 0.2673 | 0.2704 | 0.2734 | 0.2764 | 0.2794 | 0.2823 | 0.2852 |
| 0.8 | 0.2881 | 0.2910 | 0.2939 | 0.2967 | 0.2995 | 0.3023 | 0.3051 | 0.3078 | 0.3106 | 0.3133 |
| 0.9 | 0.3159 | 0.3186 | 0.3212 | 0.3238 | 0.3264 | 0.3289 | 0.3315 | 0.3340 | 0.3365 | 0.3389 |
| 1.0 | 0.3413 | 0.3438 | 0.3461 | 0.3485 | 0.3508 | 0.3531 | 0.3554 | 0.3577 | 0.3599 | 0.3621 |
| 1.1 | 0.3643 | 0.3665 | 0.3686 | 0.3708 | 0.3729 | 0.3749 | 0.3770 | 0.3790 | 0.3810 | 0.3830 |
| 1.2 | 0.3849 | 0.3869 | 0.3888 | 0.3907 | 0.3925 | 0.3944 | 0.3962 | 0.3980 | 0.3997 | 0.4015 |
| 1.3 | 0.4032 | 0.4049 | 0.4066 | 0.4082 | 0.4099 | 0.4115 | 0.4131 | 0.4147 | 0.4162 | 0.4177 |
| 1.4 | 0.4192 | 0.4207 | 0.4222 | 0.4236 | 0.4251 | 0.4265 | 0.4279 | 0.4292 | 0.4306 | 0.4319 |
| 1.5 | 0.4332 | 0.4345 | 0.4357 | 0.4370 | 0.4382 | 0.4394 | 0.4406 | 0.4418 | 0.4429 | 0.4441 |
| 1.6 | 0.4452 | 0.4463 | 0.4474 | 0.4484 | 0.4495 | 0.4505 | 0.4515 | 0.4525 | 0.4535 | 0.4545 |
| 1.7 | 0.4554 | 0.4564 | 0.4573 | 0.4582 | 0.4591 | 0.4599 | 0.4608 | 0.4616 | 0.4625 | 0.4633 |
| 1.8 | 0.4641 | 0.4649 | 0.4656 | 0.4664 | 0.4671 | 0.4678 | 0.4686 | 0.4693 | 0.4699 | 0.4706 |
| 1.9 | 0.4713 | 0.4719 | 0.4726 | 0.4732 | 0.4738 | 0.4744 | 0.4750 | 0.4756 | 0.4761 | 0.4767 |
| 2.0 | 0.4772 | 0.4778 | 0.4783 | 0.4788 | 0.4793 | 0.4798 | 0.4803 | 0.4808 | 0.4812 | 0.4817 |
| 2.1 | 0.4821 | 0.4826 | 0.4830 | 0.4834 | 0.4838 | 0.4842 | 0.4846 | 0.4850 | 0.4854 | 0.4857 |
| 2.2 | 0.4861 | 0.4864 | 0.4868 | 0.4871 | 0.4875 | 0.4878 | 0.4881 | 0.4884 | 0.4887 | 0.4890 |
| 2.3 | 0.4893 | 0.4896 | 0.4898 | 0.4901 | 0.4904 | 0.4906 | 0.4909 | 0.4911 | 0.4913 | 0.4916 |
| 2.4 | 0.4918 | 0.4920 | 0.4922 | 0.4925 | 0.4927 | 0.4929 | 0.4931 | 0.4932 | 0.4934 | 0.4936 |
| 2.5 | 0.4938 | 0.4940 | 0.4941 | 0.4943 | 0.4945 | 0.4946 | 0.4948 | 0.4949 | 0.4951 | 0.4952 |
| 2.6 | 0.4953 | 0.4955 | 0.4956 | 0.4957 | 0.4959 | 0.4960 | 0.4961 | 0.4962 | 0.4963 | 0.4964 |
| 2.7 | 0.4965 | 0.4966 | 0.4967 | 0.4968 | 0.4969 | 0.4970 | 0.4971 | 0.4972 | 0.4973 | 0.4974 |
| 2.8 | 0.4974 | 0.4975 | 0.4976 | 0.4977 | 0.4977 | 0.4978 | 0.4979 | 0.4979 | 0.4980 | 0.4981 |
| 2.9 | 0.4981 | 0.4982 | 0.4982 | 0.4983 | 0.4984 | 0.4984 | 0.4985 | 0.4985 | 0.4986 | 0.4986 |
| 3.0 | 0.4987 | 0.4987 | 0.4987 | 0.4988 | 0.4988 | 0.4989 | 0.4989 | 0.4989 | 0.4990 | 0.4990 |
| 3.1 | 0.4990 | 0.4991 | 0.4991 | 0.4991 | 0.4992 | 0.4992 | 0.4992 | 0.4992 | 0.4993 | 0.4993 |
| 3.2 | 0.4993 | 0.4993 | 0.4994 | 0.4994 | 0.4994 | 0.4994 | 0.4994 | 0.4995 | 0.4995 | 0.4995 |
| 3.3 | 0.4995 | 0.4995 | 0.4995 | 0.4996 | 0.4996 | 0.4996 | 0.4996 | 0.4996 | 0.4996 | 0.4997 |
| 3.4 | 0.4997 | 0.4997 | 0.4997 | 0.4997 | 0.4997 | 0.4997 | 0.4997 | 0.4997 | 0.4997 | 0.4998 |
| 3.5 | 0.4998 | 0.4998 | 0.4998 | 0.4998 | 0.4998 | 0.4998 | 0.4998 | 0.4998 | 0.4998 | 0.4998 |
| 3.6 | 0.4998 | 0.4998 | 0.4999 | 0.4999 | 0.4999 | 0.4999 | 0.4999 | 0.4999 | 0.4999 | 0.4999 |
| 3.7 | 0.4999 | 0.4999 | 0.4999 | 0.4999 | 0.4999 | 0.4999 | 0.4999 | 0.4999 | 0.4999 | 0.4999 |
| 3.8 | 0.4999 | 0.4999 | 0.4999 | 0.4999 | 0.4999 | 0.4999 | 0.4999 | 0.4999 | 0.4999 | 0.4999 |
| 3.9 | 0.5000 | 0.5000 | 0.5000 | 0.5000 | 0.5000 | 0.5000 | 0.5000 | 0.5000 | 0.5000 | 0.5000 |
| 4.0 | 0.5000 | 0.5000 | 0.5000 | 0.5000 | 0.5000 | 0.5000 | 0.5000 | 0.5000 | 0.5000 | 0.5000 |
Se obtiene los datos restando el límite inferior a calcular menos la media poblacional ($\mu$) y dividirlo todo entre la desviación estandar ($\sigma$) poblacional
$z= \dfrac{x-\mu}{\sigma}$  Luego se ubica en la tabla
**Fórmula:**
$z_{li}+z_{ls}=z_{total}$
se expresa normalmente en porcentaje

**Ejemplo:**
La Fuerza Aérea de Estados Unidos estuvo usando asientos expulsión que se diseñaron para hombres con un peso de entre 63.5 y 95.7 kg. Siendo que el peso de las mujeres se distribuye normalmente, con una media de 64.9 kg y una desviación estándar de 13.15 kg ¿Qué porcentaje de las mujeres tiene pesos que se encuentran dentro de dichos límites?

Población=$\mu$=64.9 kg
$\sigma$=13.15 kg
$x_{li}=63.5$
$x_{ls}=95.7$

$z=\dfrac{x-\mu}{\sigma} \rightarrow \dfrac{63.5-64.9}{13.15}=-0.10$ 

$z=\dfrac{x-\mu}{\sigma} \rightarrow \dfrac{95.7-64.9}{13.15}=2.34$

Ubicando en la tabla 0.10 y 2.34 da igual a 0.0398 y 0.4904 respectivamente

$0.0398 + 0.4904 = 0.5302 \cdot 100 = 53.02\%$

Esto quiere decir que solo el 53.02% de mujeres tienen pesos dentro del rango para los asientos eyectores, excluyendo al 47%.

El diseño tiene como límite inferior prácticamente la media del peso de las mujeres, los datos arrojaron que $z_{li}=0.0398$, el área de 0 a z es solo 3.98%, es decir, solo 3.98% de mujeres están entre 64.9 y 63.5 kg. Mientras que en el límite superior, $z_{ls}=0.4904$ por lo que hay un 49.04% de mujeres entre los pesos de 64.9 y 95.7 kg.

---
#### **3.4.Cálculo del Tamaño Muestral ( $n$ )**
A menudo, se requiere determinar cuán grande debe ser la muestra _antes_ de realizar el estudio para lograr un margen de error deseado.

**Para la Media:**  
$n=\left(\dfrac{z_{\alpha / 2}}{E} \right)^{2}$
  
_Necesitamos una estimación de $\sigma$ (de estudios piloto o literatura)._

**Para la Proporción (El método más relevante):**  
$n=\left(\dfrac{z_{\alpha / 2}}{E} \right)^{2} \cdot \hat{p}(1-\hat{p})$
*Si no tenemos una estimación de $\hat{p}$, (Proporción muestral) se usa $\hat{p} = 0.5$, ya que maximiza el tamaño muestral necesario y asegura que el error no sea mayor al deseado.

**Ejemplo para Proporción:**  
Queremos estimar la proporción de estudiantes que trabajan con un error máximo del 3% (E=0.03) y un 95% de confianza. No tenemos una estimación previa de $\hat{p}$.

1. **Identifica los datos:** $E=0.03$, Nivel de Confianza = 95% → $Z_{\alpha/2}=1.96$. Usamos $\hat{p}=0.5$.
    
2. **Aplica la Fórmula:**  
    $n = \left( \frac{1.96}{0.03} \right)^2 \cdot 0.5 \cdot (1-0.5)$  
    $n = (65.333...)^2 \cdot 0.25$  
    $n \approx 4268.44 \cdot 0.25 \approx 1067.11$
    

**Conclusión:** Necesitamos una muestra de al menos **1068 estudiantes** para cumplir con los requisitos de error y confianza.

---
#Resumen 
#### Intervalo de confianza para la media poblacional

| Nivel de Confianza | α (total) | α/2 (cada cola) | Valor Z crítico |
| ------------------ | --------- | --------------- | --------------- |
| 90%                | 0.10      | 0.05            | ±1.645          |
| 95%                | 0.05      | 0.025           | ±1.960          |
| 99%                | 0.01      | 0.005           | ±2.576          |
| 99.9%              | 0.001     | 0.0005          | ±3.291          |

1) Se conoce desviación estándar poblacional ($\sigma$) n>30
	$\bar{x}±Z_{α/2}⋅\dfrac{σ}{\sqrt{ n }}$
2) No se conoce desviación estándar poblacional (s) n<30
	$\bar{x}\pm t_{\alpha / 2,gl} \cdot \dfrac{s}{\sqrt{ n }}$

| gl  | 80% (0.10) | 90% (0.05) | 95% (0.025) | 98% (0.01) | 99% (0.005) | 99.8% (0.001) | 99.9% (0.0005) |
| --- | ---------- | ---------- | ----------- | ---------- | ----------- | ------------- | -------------- |
| 1   | 3.078      | 6.314      | 12.706      | 31.821     | 63.657      | 318.309       | 636.619        |
| 2   | 1.886      | 2.920      | 4.303       | 6.965      | 9.925       | 22.327        | 31.599         |
| 3   | 1.638      | 2.353      | 3.182       | 4.541      | 5.841       | 10.215        | 12.924         |
| 4   | 1.533      | 2.132      | 2.776       | 3.747      | 4.604       | 7.173         | 8.610          |
| 5   | 1.476      | 2.015      | 2.571       | 3.365      | 4.032       | 5.893         | 6.869          |
| 6   | 1.440      | 1.943      | 2.447       | 3.143      | 3.707       | 5.208         | 5.959          |
| 7   | 1.415      | 1.895      | 2.365       | 2.998      | 3.499       | 4.785         | 5.408          |
| 8   | 1.397      | 1.860      | 2.306       | 2.896      | 3.355       | 4.501         | 5.041          |
| 9   | 1.383      | 1.833      | 2.262       | 2.821      | 3.250       | 4.297         | 4.781          |
| 10  | 1.372      | 1.812      | 2.228       | 2.764      | 3.169       | 4.144         | 4.587          |
| 11  | 1.363      | 1.796      | 2.201       | 2.718      | 3.106       | 4.025         | 4.437          |
| 12  | 1.356      | 1.782      | 2.179       | 2.681      | 3.055       | 3.930         | 4.318          |
| 13  | 1.350      | 1.771      | 2.160       | 2.650      | 3.012       | 3.852         | 4.221          |
| 14  | 1.345      | 1.761      | 2.145       | 2.624      | 2.977       | 3.787         | 4.140          |
| 15  | 1.341      | 1.753      | 2.131       | 2.602      | 2.947       | 3.733         | 4.073          |
| 16  | 1.337      | 1.746      | 2.120       | 2.583      | 2.921       | 3.686         | 4.015          |
| 17  | 1.333      | 1.740      | 2.110       | 2.567      | 2.898       | 3.646         | 3.965          |
| 18  | 1.330      | 1.734      | 2.101       | 2.552      | 2.878       | 3.610         | 3.922          |
| 19  | 1.328      | 1.729      | 2.093       | 2.539      | 2.861       | 3.579         | 3.883          |
| 20  | 1.325      | 1.725      | 2.086       | 2.528      | 2.845       | 3.552         | 3.850          |
| 21  | 1.323      | 1.721      | 2.080       | 2.518      | 2.831       | 3.527         | 3.819          |
| 22  | 1.321      | 1.717      | 2.074       | 2.508      | 2.819       | 3.505         | 3.792          |
| 23  | 1.319      | 1.714      | 2.069       | 2.500      | 2.807       | 3.485         | 3.768          |
| 24  | 1.318      | 1.711      | 2.064       | 2.492      | 2.797       | 3.467         | 3.745          |
| 25  | 1.316      | 1.708      | 2.060       | 2.485      | 2.787       | 3.450         | 3.725          |
| 26  | 1.315      | 1.706      | 2.056       | 2.479      | 2.779       | 3.435         | 3.707          |
| 27  | 1.314      | 1.703      | 2.052       | 2.473      | 2.771       | 3.421         | 3.690          |
| 28  | 1.313      | 1.701      | 2.048       | 2.467      | 2.763       | 3.408         | 3.674          |
| 29  | 1.311      | 1.699      | 2.045       | 2.462      | 2.756       | 3.396         | 3.659          |
| 30  | 1.310      | 1.697      | 2.042       | 2.457      | 2.750       | 3.385         | 3.646          |
| 40  | 1.303      | 1.684      | 2.021       | 2.423      | 2.704       | 3.307         | 3.551          |
| 50  | 1.299      | 1.676      | 2.009       | 2.403      | 2.678       | 3.261         | 3.496          |
| 60  | 1.296      | 1.671      | 2.000       | 2.390      | 2.660       | 3.232         | 3.460          |
| 80  | 1.292      | 1.664      | 1.990       | 2.374      | 2.639       | 3.195         | 3.416          |
| 100 | 1.290      | 1.660      | 1.984       | 2.364      | 2.626       | 3.174         | 3.390          |
| 120 | 1.289      | 1.658      | 1.980       | 2.358      | 2.617       | 3.160         | 3.373          |
| ∞   | 1.282      | 1.645      | 1.960       | 2.326      | 2.576       | 3.090         | 3.291          |

#### Estimación de una porción poblacional
$p\pm(Z\cdot Es)$
$Es=\sqrt{ \dfrac{p\cdot q}{n} }$
$q=100\%-p$

#### Estimación de intervalos
$z=\dfrac{x-\mu}{\sigma}$
$z_{li}+z_{ls}=z_{total}$

| z   | 0      | 0.01   | 0.02   | 0.03   | 0.04   | 0.05   | 0.06   | 0.07   | 0.08   | 0.09   |
| --- | ------ | ------ | ------ | ------ | ------ | ------ | ------ | ------ | ------ | ------ |
| 0.0 | 0.0000 | 0.0040 | 0.0080 | 0.0120 | 0.0160 | 0.0199 | 0.0239 | 0.0279 | 0.0319 | 0.0359 |
| 0.1 | 0.0398 | 0.0438 | 0.0478 | 0.0517 | 0.0557 | 0.0596 | 0.0636 | 0.0675 | 0.0714 | 0.0753 |
| 0.2 | 0.0793 | 0.0832 | 0.0871 | 0.0910 | 0.0948 | 0.0987 | 0.1026 | 0.1064 | 0.1103 | 0.1141 |
| 0.3 | 0.1179 | 0.1217 | 0.1255 | 0.1293 | 0.1331 | 0.1368 | 0.1406 | 0.1443 | 0.1480 | 0.1517 |
| 0.4 | 0.1554 | 0.1591 | 0.1628 | 0.1664 | 0.1700 | 0.1736 | 0.1772 | 0.1808 | 0.1844 | 0.1879 |
| 0.5 | 0.1915 | 0.1950 | 0.1985 | 0.2019 | 0.2054 | 0.2088 | 0.2123 | 0.2157 | 0.2190 | 0.2224 |
| 0.6 | 0.2257 | 0.2291 | 0.2324 | 0.2357 | 0.2389 | 0.2422 | 0.2454 | 0.2486 | 0.2517 | 0.2549 |
| 0.7 | 0.2580 | 0.2611 | 0.2642 | 0.2673 | 0.2704 | 0.2734 | 0.2764 | 0.2794 | 0.2823 | 0.2852 |
| 0.8 | 0.2881 | 0.2910 | 0.2939 | 0.2967 | 0.2995 | 0.3023 | 0.3051 | 0.3078 | 0.3106 | 0.3133 |
| 0.9 | 0.3159 | 0.3186 | 0.3212 | 0.3238 | 0.3264 | 0.3289 | 0.3315 | 0.3340 | 0.3365 | 0.3389 |
| 1.0 | 0.3413 | 0.3438 | 0.3461 | 0.3485 | 0.3508 | 0.3531 | 0.3554 | 0.3577 | 0.3599 | 0.3621 |
| 1.1 | 0.3643 | 0.3665 | 0.3686 | 0.3708 | 0.3729 | 0.3749 | 0.3770 | 0.3790 | 0.3810 | 0.3830 |
| 1.2 | 0.3849 | 0.3869 | 0.3888 | 0.3907 | 0.3925 | 0.3944 | 0.3962 | 0.3980 | 0.3997 | 0.4015 |
| 1.3 | 0.4032 | 0.4049 | 0.4066 | 0.4082 | 0.4099 | 0.4115 | 0.4131 | 0.4147 | 0.4162 | 0.4177 |
| 1.4 | 0.4192 | 0.4207 | 0.4222 | 0.4236 | 0.4251 | 0.4265 | 0.4279 | 0.4292 | 0.4306 | 0.4319 |
| 1.5 | 0.4332 | 0.4345 | 0.4357 | 0.4370 | 0.4382 | 0.4394 | 0.4406 | 0.4418 | 0.4429 | 0.4441 |
| 1.6 | 0.4452 | 0.4463 | 0.4474 | 0.4484 | 0.4495 | 0.4505 | 0.4515 | 0.4525 | 0.4535 | 0.4545 |
| 1.7 | 0.4554 | 0.4564 | 0.4573 | 0.4582 | 0.4591 | 0.4599 | 0.4608 | 0.4616 | 0.4625 | 0.4633 |
| 1.8 | 0.4641 | 0.4649 | 0.4656 | 0.4664 | 0.4671 | 0.4678 | 0.4686 | 0.4693 | 0.4699 | 0.4706 |
| 1.9 | 0.4713 | 0.4719 | 0.4726 | 0.4732 | 0.4738 | 0.4744 | 0.4750 | 0.4756 | 0.4761 | 0.4767 |
| 2.0 | 0.4772 | 0.4778 | 0.4783 | 0.4788 | 0.4793 | 0.4798 | 0.4803 | 0.4808 | 0.4812 | 0.4817 |
| 2.1 | 0.4821 | 0.4826 | 0.4830 | 0.4834 | 0.4838 | 0.4842 | 0.4846 | 0.4850 | 0.4854 | 0.4857 |
| 2.2 | 0.4861 | 0.4864 | 0.4868 | 0.4871 | 0.4875 | 0.4878 | 0.4881 | 0.4884 | 0.4887 | 0.4890 |
| 2.3 | 0.4893 | 0.4896 | 0.4898 | 0.4901 | 0.4904 | 0.4906 | 0.4909 | 0.4911 | 0.4913 | 0.4916 |
| 2.4 | 0.4918 | 0.4920 | 0.4922 | 0.4925 | 0.4927 | 0.4929 | 0.4931 | 0.4932 | 0.4934 | 0.4936 |
| 2.5 | 0.4938 | 0.4940 | 0.4941 | 0.4943 | 0.4945 | 0.4946 | 0.4948 | 0.4949 | 0.4951 | 0.4952 |
| 2.6 | 0.4953 | 0.4955 | 0.4956 | 0.4957 | 0.4959 | 0.4960 | 0.4961 | 0.4962 | 0.4963 | 0.4964 |
| 2.7 | 0.4965 | 0.4966 | 0.4967 | 0.4968 | 0.4969 | 0.4970 | 0.4971 | 0.4972 | 0.4973 | 0.4974 |
| 2.8 | 0.4974 | 0.4975 | 0.4976 | 0.4977 | 0.4977 | 0.4978 | 0.4979 | 0.4979 | 0.4980 | 0.4981 |
| 2.9 | 0.4981 | 0.4982 | 0.4982 | 0.4983 | 0.4984 | 0.4984 | 0.4985 | 0.4985 | 0.4986 | 0.4986 |
| 3.0 | 0.4987 | 0.4987 | 0.4987 | 0.4988 | 0.4988 | 0.4989 | 0.4989 | 0.4989 | 0.4990 | 0.4990 |
| 3.1 | 0.4990 | 0.4991 | 0.4991 | 0.4991 | 0.4992 | 0.4992 | 0.4992 | 0.4992 | 0.4993 | 0.4993 |
| 3.2 | 0.4993 | 0.4993 | 0.4994 | 0.4994 | 0.4994 | 0.4994 | 0.4994 | 0.4995 | 0.4995 | 0.4995 |
| 3.3 | 0.4995 | 0.4995 | 0.4995 | 0.4996 | 0.4996 | 0.4996 | 0.4996 | 0.4996 | 0.4996 | 0.4997 |
| 3.4 | 0.4997 | 0.4997 | 0.4997 | 0.4997 | 0.4997 | 0.4997 | 0.4997 | 0.4997 | 0.4997 | 0.4998 |
| 3.5 | 0.4998 | 0.4998 | 0.4998 | 0.4998 | 0.4998 | 0.4998 | 0.4998 | 0.4998 | 0.4998 | 0.4998 |
| 3.6 | 0.4998 | 0.4998 | 0.4999 | 0.4999 | 0.4999 | 0.4999 | 0.4999 | 0.4999 | 0.4999 | 0.4999 |
| 3.7 | 0.4999 | 0.4999 | 0.4999 | 0.4999 | 0.4999 | 0.4999 | 0.4999 | 0.4999 | 0.4999 | 0.4999 |
| 3.8 | 0.4999 | 0.4999 | 0.4999 | 0.4999 | 0.4999 | 0.4999 | 0.4999 | 0.4999 | 0.4999 | 0.4999 |
| 3.9 | 0.5000 | 0.5000 | 0.5000 | 0.5000 | 0.5000 | 0.5000 | 0.5000 | 0.5000 | 0.5000 | 0.5000 |
| 4.0 | 0.5000 | 0.5000 | 0.5000 | 0.5000 | 0.5000 | 0.5000 | 0.5000 | 0.5000 | 0.5000 | 0.5000 |
#### Cálculo de tamaño muestral
**Para la Media:**  
$n=\left(\dfrac{z_{\alpha / 2}}{E} \right)^{2}$

**Para la Proporción (El método más relevante):**  
$n=\left(\dfrac{z_{\alpha / 2}}{E} \right)^{2} \cdot \hat{p}(1-\hat{p})$
*Si no tenemos una estimación de $\hat{p}$, se usa $\hat{p} = 0.5$