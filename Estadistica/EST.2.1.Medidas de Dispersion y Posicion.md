---
tags:
  - Estadistica
---
# 1.Medidas de Dispersión
## 1.1.¿Qué son?
Las medidas de dispersión son las estadísticas utilizadas para describir el grado de dispersión o variación que presentan un conjunto de datos, es decir, una variable estadística, van de la mano con las [medidas de tendencia central](<EST.1.3.Medidas de Tendencia Central.md>), ya que la mayoría de las fórmulas requieren de ellas para ilustrar la variabilidad de los datos, específicamente de la media, esta indica el valor promedio, las medidas de dispersión indican cuanto varían esos valores entre sí; son muy útiles para evaluar el riesgo e incertidumbre, específicamente en ámbitos de inversión o investigación, donde una dispersión alta implica un mayor riesgo al estar esparcidos los datos  
## 1.2.Fórmulas
Para las fórmulas se usará un divisor general, ya que se pueden dividir en 2 casos, datos de una población o de una muestra, en una población se divide entre n (el número de casos encontrados en la población), mientras que en la muestra se divide entre n-1 (se usa n-1 para no subestimar la variabilidad real, llamada corrección de Bessel). Las fórmulas que se encuentran en la medidas de dispersión son cuatro, rango, variación, dispersión estándar y coeficiente de variación.

- **Desviación Media(DM):** Nos indica el promedio de las desviaciones absolutas de cada valor de un conjunto de datos respecto a la media aritmética del conjunto. 

- **Rango (r):** Es el valor numérico que indica la diferencia entre el valor máximo y el mínimo de una población o muestra estadística.

- **Varianza ($\sigma^{2})$:** Es la medida que representa la variabilidad de una serie de datos respecto a su media. Se calcula como la suma de los residuos al cuadrado divididos entre el total de observaciones, representa la variabilidad de una serie de datos alrededor de su media.

- **Desviación Estándar($\sigma$)**: Es otra medida que ofrece una representación de la variación de los datos respecto a su media, pero en las mismas unidades de los datos, lo que permite que se vuelva más fácil de leer. Su cálculo es la raíz cuadrada de la variación. 

- **Coeficiente de variación (Cv):** Es la medida de dispersión relativa, este coeficiente es útil cuando se comparan dos conjuntos de datos que pueden tener diferentes medidas, permite establecer una relación en término de variabilidad relativa. Se calcula dividiendo la desviación estándar entre la media y multiplicándolo por 100 para expresarlo en porcentaje. 
#### 1.2.1.Datos no agrupados
- **Desviación Media (DM):** $\dfrac{\sum_{i=1}^{N}{|x_{i-\bar{X}}|}}{N}$ 
	$x_{i}:$ Observación número i de la variable x, toma los valores entre 1 y n
	$\bar{X}:$ Media de los datos
	N: Número de datos

- **Rango (r):** $$r=Máx_{x}-Min_{x}$$
	r: Rango
	$Máx_{x}:$ Valor máximo de la muestra o población
	$Mix_{x}:$ Valor mínimo de la muestra o población

- **Varianza ($\sigma^{2})$:** $$\sigma^{2}=\dfrac{\sum_{1}^{n}(x_{i}-\bar{X})^{2}}{n}$$
	$\sigma^{2}:$ Varianza
	$x$: Variable donde se calcula la varianza
	$x_{i}$: Observación número i de la variable x, toma los valores entre 1 y n
	$\bar{X}$: Media de los datos
	n: Número de observaciones, en el caso muestral sería n-1

- **Desviación Estándar($\sigma$)**: $$\sigma=\sqrt{\dfrac{\sum_{1}^{n}(x_{i}-\bar{X})^{2}}{n}}\ \ \lor \ \ \sqrt{\sigma^{2} }$$
	$\sigma:$ Desviación Estándar
	$x$: Variable donde se calcula la varianza
	$x_{i}$: Observación número i de la variable x, toma los valores entre 1 y n
	$\bar{X}$: Media de los datos
	n: Número de observaciones, en el caso muestral sería n-1

- **Coeficiente de variación (Cv):** $$Cv=\dfrac{\sigma}{\bar{X}}$$
	$Cv$: Coeficiente de variación
	$\sigma$: Desviación estandar
	$\bar{X}$: Media aritmética

#### 1.2.2.Datos agrupados
- **Desviación media (DM):** $\dfrac{\sum_{i=1}^{N}|X_{i}-\bar{X}|\cdot f_{i}}{N}$
	$x_{i}:$ Marca de clase
	$\bar{X}:$ Media
	$f_{i}:$ Frecuencia relativa
	N: Número de datos

- **Rango (r):** $$r=Máx_{x}-Min_{x}$$
	r: Rango
	$Máx_{x}:$ Valor máximo de la muestra o población
	$Mix_{x}:$ Valor mínimo de la muestra o población

- **Varianza ($\sigma^{2})$:**  n<30 $$\sigma^{2}=\dfrac{\sum_{1}^{n}[(x_{i}-\bar{X})^{2}\cdot f_{i}]}{n}$$
	Para población grande: n>30 $$\sigma^{2}=\dfrac{\sum_{1}^{n}f_{i}\cdot(x_{i}-\mu)^{2}}{n}$$
	$$\mu= \dfrac{\sum_{i=1}^{N}x_{i}\cdot f_{i}}{N}$$
	$\sigma^{2}:$ Varianza
	$x$: Variable donde se calcula la varianza
	$x_{i}$: Marca de clase (promedio entre los dos intervalos) número i de la variable x, toma los valores entre 1 y n
	$f_{i}$: Frecuencia relativa
	$\bar{X}$: Media de los datos
	n: Número de observaciones, en el caso muestral sería n-1

- **Desviación Estándar($\sigma$)**: $$\sigma=\sqrt{\dfrac{\sum_{1}^{n}[(x_{i}-\bar{X})^{2}\cdot f_{i}]}{n}}\ \ \lor \ \ \sqrt{\sigma^{2} }$$
	$\sigma:$ Desviación Estándar
	$x$: Variable donde se calcula la varianza
	$x_{i}$: Marca de clase (promedio entre los dos intervalos) número i de la variable x, toma los valores entre 1 y n
	$f_{i}$: Frecuencia relativa
	$\bar{X}$: Media de los datos
	n: Número de observaciones, en el caso muestral sería n-1

- **Coeficiente de variación (Cv):** $$Cv=\dfrac{\sigma}{\bar{X}}$$
	$Cv$: Coeficiente de variación
	$\sigma$: Desviación estandar
	$\bar{X}$: Media aritmética

## 1.3.Usos
Las medidas de dispersión son cruciales en investigación del mercado, debido a que abarcan todos los aspectos variables del mismo, por ejemplo, las preferencias del consumidor, la cantidad de compras de un producto en diversas regiones, permitiendo identificar si existe una disparidad de opiniones, permitiendo a la empresa identificar las áreas a mejorar.

En el ámbito financiero son esenciales para evaluar los riesgos en una inversión, ya que una desviación alta implica un mercado poco predecible o volátil. Además, en el aspecto académico puede ser útil para evaluar el rendimiento de los estudiantes, una alta varianza indica que hay alumnos a los que se les dificulta el aprendizaje, llevando a las instituciones a realizar reformas en los métodos de enseñanza.

# 2.Medidas de Posición -> (D, C, P)
## 2.1.¿Qué son?
Son herramientas estadísticas que dividen un conjunto de datos ordenados en partes iguales, este es el valor representativo de ese conjunto al dividirlos en segmentos iguales, proporcionando una vista clara de la distribución de los mismos. Las más comunes son: Mediana, cuartil, decil y percentil
## 2.2.Fórmulas
Para obtener las fórmulas y que estas demuestren valor significativo en el conjunto de datos, deben ordenarse, para luego conseguir su posición en la tabla

- **Mediana (Me):** Es el valor de la variable en posición central de un conjunto de datos ordenados, esta es conocida como medida de posición central, mientras que el resto se conoce como medidas de posición no central. 

- **Cuartiles (Q):** Divide la distribución en cuatro partes iguales, estos son: Q1 (25%), Q2 (50%) y Q3 (75%). Q2 coincide con la mediana.

- **Deciles (D):** Divide los datos en diez partes iguales, estas van de D1 hasta D9, cada uno representando 10% del conjunto, el D5 equivale a la mediana.

- **Percentiles (P):** Divide la distribución en cien partes iguales, existen 99 percentiles (desde P1 hasta P99). Estos permiten análisis más detallados de los datos. P50 coincide con la mediana. 
#### 2.2.1.Datos no agrupados
Variables en cuestión:
	$N$: Número de datos
	$k$ : Medida a calcular

- **Mediana (Me):**  
	Fórmula posición datos impares: $\dfrac{N+1}{2}$
	Fórmula posición datos pares: $C_{1}=\frac{N}{2}\ \land\ C_{2}=\frac{N+1}{2}$
		Posición: $\dfrac{C_{1}+C_{2}}{2}$

- **Cuartiles (Q):**
	Posición:
	$\text{N par}\rightarrow \dfrac{kN}{4}$
	 $\text{N impar} \rightarrow \dfrac{k\cdot (N+1)}{4}$
	Fórmula cuando la posición es decimal: $Li + \dfrac{k(Ls-Li)}{4}$    
	(Ls y Li son los dos límites en el que se encuentra la posición del dato, por ejemplo, si posición es 2.75 y los datos son: 1, 4, 6, 8; Li es 4 y Ls es 6)
	 
	Rango cuartil: $Q=L+IC\cdot \dfrac{q-F}{f}$

- **Deciles (D):**
	Posición: 
	$\text{N par}\rightarrow \dfrac{kN}{10}$
	$\text{N impar}\rightarrow \dfrac{k\cdot (N+1)}{10}$
	Fórmula cuando la posición es decimal: $Li + \dfrac{k(Ls-Li)}{10}$    
	(Ls y Li son los dos límites en el que se encuentra la posición del dato, por ejemplo, si posición es 2.75 y los datos son: 1, 4, 6, 8; Li es 4 y Ls es 6)
	 
	Rango decil: $D=L+IC \cdot \dfrac{d-F}{f}$      

- **Percentiles (P):**
	Posición: 
	$\text{N par}\rightarrow \dfrac{kN}{100}$
	$\text{N impar}\rightarrow\dfrac{k\cdot (N+1)}{100}$
	Fórmula cuando la posición es decimal: $Li + \dfrac{k(Ls-Li)}{100}$    
	(Ls y Li son los dos límites en el que se encuentra la posición del dato, por ejemplo, si posición es 2.75 y los datos son: 1, 4, 6, 8; Li es 4 y Ls es 6)
	 
	Rango percentil: $P=L+IC\cdot \dfrac{p-F}{f}$
#### 2.2.2.Datos agrupados		
Variables en cuestión:
	$N$: Número total de datos
	$k$: Valor a buscar (Cuartil del 1 al 3, Decil del 1 al 9, Percentil del 1 al 99)
	$Li$: Límite inferior de la clase que almacena la posición
	$F_{i-1}$: Frecuencia absoluta anterior al intervalo de posición
	$f_{i}$: Frecuencia relativa del intervalo
	$a_{i}$: Amplitud del intervalo

- **Mediana (Me):**  
	Fórmula: $Me=Li+\dfrac{\frac{N}{2} - F_{i-1}}{f_{i}}\cdot a_{i}$

- **Cuartiles (Q):**
	Posición: $\dfrac{k\cdot N}{4}$   Es en donde se buscará el dato, se encuentra en la frecuencia absoluta que contiene el dato 
	Fórmula: $Q_{k}=Li+\dfrac{\frac{k\cdot N}{4} - F_{i-1}}{f_{i}}\cdot a_{i}$

- **Deciles (D):**
	Posición: $\dfrac{k\cdot N}{10}$   Es en donde se buscará el dato, se encuentra en la frecuencia absoluta que contiene el dato 
	Fórmula: $D_{k}=Li+\dfrac{\frac{k\cdot N}{10} - F_{i-1}}{f_{i}}\cdot a_{i}$

- **Percentiles (P):**	
	Posición: $\dfrac{k\cdot N}{100}$   Es en donde se buscará el dato, se encuentra en la frecuencia absoluta que contiene el dato 
	Fórmula: $P_{k}=Li+\dfrac{\frac{k\cdot N}{100} - F_{i-1}}{f_{i}}\cdot a_{i}$

## 2.3.Usos
Se usan para clasificar una observación dentro de una población o muestra, son una herramienta perfecta para observar como se distribuyen estos datos en distintas partes, ya que estas medidas describen el comportamiento típico o representativo de los datos, al dividir la información en partes iguales permiten un análisis modular, no solo permitiendo entender el valor representativo, las medidas de posición no central permiten entender la distribución relativa, lo que ayuda a determinar donde se encuentra un dato en específico, cuanto porcentaje está por debajo de ese dato, encontrar los valores clave (50% por ejemplo) y comparar datos entre diferentes grupos o muestras.

---
#Resumen 
#### **Medidas de dispersión**
- **Datos no agrupados:**
	**Desviación Media (DM):** $\dfrac{\sum_{i=1}^{N}{|x_{i}-\bar{X}|}}{N}$ 
	
	**Rango(r)** $r=máx_{x}-min_{x}$
	
	**Varianza ($\sigma^{2})$:** $\sigma^{2}=\dfrac{\sum_{1}^{n}(x_{i}-\bar{X})^{2}}{n}$
	
	**Desviación Estándar($\sigma$):** $\sigma=\sqrt{\dfrac{\sum_{1}^{n}(x_{i}-\bar{X})^{2}}{n}}\ \ \lor \ \ \sqrt{\sigma^{2} }$
	
	**Coeficiente de Variación(Cv):** $Cv=\dfrac{\sigma}{\bar{X}}$

- **Datos agrupados:** 
	**Rango(r):** $r = máx_{x}-min_{x}$
	
	**Varianza($\sigma^{2}):$** $$\text{N<30} \ \ \ \sigma^{2}=\dfrac{\sum_{1}^{n}[(x_{i}-\bar{X})^{2}\cdot f_{i}]}{n}$$$$\text{N>30}\ \ \ \ \sigma^{2}=\dfrac{\sum_{1}^{n}f_{i}\cdot(x_{i}-\mu)^{2}}{n}$$
	$$\mu= \dfrac{\sum_{i=1}^{N}x_{i}\cdot f_{i}}{N}$$
	
	**Desviación Estándar($\sigma$)**: $\sigma=\sqrt{\dfrac{\sum_{1}^{n}[(x_{i}-\bar{X})^{2}\cdot f_{i}]}{n}}\ \ \lor \ \ \sqrt{\sigma^{2} }$
	
	**Coeficiente de Variación(Cv):** $Cv=\dfrac{\sigma}{\bar{X}}$
#### Medidas de posición
- **Datos no agrupados:**
	**Mediana (Me):**  
	Datos impares: $\dfrac{N+1}{2}$
	Datos pares: $C_{1}=\frac{N}{2}\ \land\ C_{2}=\frac{N+1}{2}$   ->   Posición: $\dfrac{C_{1}+C_{2}}{2}$
	
	**Cuartiles (Q):**
	Posición: $\text{N impar}\rightarrow\dfrac{k\cdot (N+1)}{4}$        $\text{N par}\rightarrow \dfrac{kN}{4}$
	Posición decimal: $Li + \dfrac{k(Ls-Li)}{4}$    
	
	**Deciles (D):**
	Posición: $\text{N impar}\rightarrow\dfrac{k\cdot (N+1)}{10}$        $\text{N par}\rightarrow \dfrac{kN}{10}$
	Posición decimal: $Li + \dfrac{k(Ls-Li)}{10}$    
	
	**Percentiles (P):**
	Posición: $\text{N impar}\rightarrow\dfrac{k\cdot (N+1)}{100}$        $\text{N par}\rightarrow \dfrac{kN}{100}$
	Posición decimal: $Li + \dfrac{k(Ls-Li)}{100}$    

 - **Datos agrupados:**
	**Mediana (Me):** $Me=Li+\dfrac{\frac{N}{2} - F_{i-1}}{f_{i}}\cdot a_{i}$
	
	**Cuartiles (Q):**
	Posición: $\dfrac{k\cdot N}{4}$ -> $Q_{k}=Li+\dfrac{\frac{k\cdot N}{4} - F_{i-1}}{f_{i}}\cdot a_{i}$
	
	**Deciles (D):**
	Posición: $\dfrac{k\cdot N}{10}$ -> $D_{k}=Li+\dfrac{\frac{k\cdot N}{10} - F_{i-1}}{f_{i}}\cdot a_{i}$
	
	**Percentiles (P):**	
	Posición: $\dfrac{k\cdot N}{100}$ ->  $P_{k}=Li+\dfrac{\frac{k\cdot N}{100} - F_{i-1}}{f_{i}}\cdot a_{i}$
