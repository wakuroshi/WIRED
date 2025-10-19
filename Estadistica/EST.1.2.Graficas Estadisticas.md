# 1. Diagramas de Barras

Un diagrama de barras es una representacion grafica que utiliza barras rectangulares con longitudes proporcionales a los valores que representan. Las barras pueden ser verticales u horizontales y se utilizan para comparar categorias discretas.

## 1.1. Variables
- **Variables categoricas:** Nombre de productos, tipos de elementos, categorias
- **Variables numericas:** Frecuencias, porcentajes, cantidades, valores
- **Escala nominal:** Para etiquetas de categorias
- **Escala de intervalo/razon:** Para valores numericos en las barras

## 1.2. Caracteristicas
- Las barras estan separadas entre si
- Longitud de la barra proporcional al valor
- Puede mostrar frecuencias absolutas o relativas
- Adecuado para comparaciones directas entre categorias

## 1.3. Formulas
Altura de la barra para la categoria $i$:
$$
h_i = \frac{f_i}{\max(f)} \times H_{\text{max}}
$$
donde:
- $f_i$ = frecuencia de la categoria $i$
- $\max(f)$ = frecuencia maxima del conjunto
- $H_{\text{max}}$ = altura maxima del diagrama

Frecuencia relativa:
$$
f_{r} = \frac{f_i}{N} \times 100\%
$$
donde $N$ = total de observaciones

# 2. Poligono de Frecuencia

Un poligono de frecuencia es una grafica de linea que se construye uniendo los puntos medios de cada clase en un histograma. Representa la distribucion de frecuencias de forma suavizada mediante segmentos de recta.

## 2.1. Variables
- **Variable continua:** Tiempo, altura, peso, temperatura
- **Variable discreta:** Puntos medios de intervalos de clase
- **Variable dependiente:** Frecuencia absoluta o relativa
- **Escala de intervalo:** Para el eje horizontal (variable continua)

## 2.2. Construccion
- Se calculan los puntos medios de cada intervalo
- Se grafican puntos en (punto medio, frecuencia)
- Se unen los puntos con segmentos de recta
- Generalmente se conecta con el eje horizontal en los extremos

## 2.3. Formulas
Punto medio del intervalo $i$:
$$
PM_i = \frac{L_i + U_i}{2}
$$
donde:
- $L_i$ = limite inferior del intervalo $i$
- $U_i$ = limite superior del intervalo $i$

Frecuencia acumulada:
$$
F_i = \sum_{j=1}^{i} f_j
$$

Suavizado del poligono:
$$
y(x) = \text{interpolacion lineal entre } (PM_i, f_i) \text{ y } (PM_{i+1}, f_{i+1})
$$

# 3. Diagrama de Caja y Bigotes

El diagrama de caja y bigotes es una representacion grafica que muestra la distribucion de datos numericos a traves de sus cuartiles. Proporciona informacion sobre la mediana, dispersion y valores atipicos de un conjunto de datos.

## 3.1. Variables
- **Variable numerica continua:** Edad, ingresos, puntuaciones
- **Variable de agrupacion:** Categorias para comparar distribuciones
- **Escala de razon:** Para datos cuantitativos
- **Variables categoricas opcionales:** Para multiples diagramas

## 3.2. Componentes
- **Caja:** Representa el rango intercuartilico (Q1 a Q3)
- **Linea central:** Mediana (Q2) dentro de la caja
- **Bigotes:** Lineas que se extienden a los valores minimo y maximo
- **Valores atipicos:** Puntos fuera de los bigotes

## 3.3. Formulas
Cuartiles:
- $Q_1$ = primer cuartil (percentil 25)
- $Q_2$ = segundo cuartil = mediana (percentil 50)
- $Q_3$ = tercer cuartil (percentil 75)

Rango intercuartilico (IQR):
$$
\text{IQR} = Q_3 - Q_1
$$

Limites para bigotes:
$$
\text{Limite inferior} = Q_1 - 1.5 \times \text{IQR}
$$
$$
\text{Limite superior} = Q_3 + 1.5 \times \text{IQR}
$$

Valores atipicos:
$$
\text{Valor atipico si } x < Q_1 - 1.5 \times \text{IQR} \quad \text{o} \quad x > Q_3 + 1.5 \times \text{IQR}
$$

## 3.4. Interpretacion
- La caja contiene el 50% central de los datos
- La mediana muestra el valor central de la distribucion
- Los bigotes indican el rango de datos "normales"
- Los puntos aislados representan valores extremos o atipicos

# 4. Diagrama de Ishikawa (Diagrama de Espina de Pescado)

Herramienta grafica utilizada para identificar y organizar las posibles causas de un problema o efecto.

**Estructura caracteristica:** Tiene una "espina" principal con varias subdivisiones que representan categorias de causas. Las **6M** tradicionales son:

- **Materiales:** Materias primas, componentes, insumos
- **Mano de Obra:** Personal, habilidades, capacitacion
- **Metodos:** Procesos, procedimientos, sistemas de trabajo
- **Maquinas:** Equipos, herramientas, tecnologia
- **Medio Ambiente:** Condiciones fisicas, ubicacion, entorno
- **Mediciones:** Sistemas de medicion, calibracion, precision

**Aplicacion:** Ampliamente utilizado en control de calidad y analisis de problemas en ingenieria y gestion.

# 5. Diagramas Circulares
Se utilizan para presentar los resultados de un estudio en porcentajes. Se emplean los porcentajes de las frecuencias relativas de cada dato llevadas a grados, y se comienza a graficar a **partir de 90° en sentido horario** de las agujas del reloj. Para calcular el angulo de cada sector:
$$
\theta_i = \frac{f_i}{N} \times 360^\circ
$$

donde:
- $\theta_i$ = angulo en grados del sector $i$
- $f_i$ = frecuencia absoluta de la categoria $i$
- $N$ = suma total de todas las frecuencias


# 6. Histogramas
Son gráficos asociados a datos continuos, son muy similares a los diagramas de barras, pero, entre las barras no existe separación, debido a que la frecuencia de la muestra se coloca en intérvalos de clase, siendo uno continuo a otro.

En lo histogramas vamos a encontrar datos no agrupados y datos agrupados: 
**Los datos no agrupados** se ordenaran según su magnitud de menor a mayor, y se contará el número de veces que se repite cada dato llamándolo frecuencia relativa.
**Los datos agrupados** se usan para hallar las medidas de tendencia central (media, mediana, moda, desviación media, varianza, desviación estándar, y todas las medidas de posición) percentil, decil, cuartil. También son la base para los cálculos de probabilidad.
P
Para hacer histogramas se requiere:
**1)** Amplitud de intérvalos ($A$) -> $\text{Valor Mayor}-\text{Valor menor}$.
**2)** # de Clases ($C$) -> $1+3,33 \log{N}$
**3)** Intervalo de Clases ($IC$) -> $\dfrac{\text{Amplitud}}{\text{\#Clases}}$
**4)** Límite Inferior de Clase ($L_{I}$) -> Valor menor
**5)** Límite Superior Clase ($L_{S}$) -> $\text{Valor Menor} +\text{Amplitud}$
**6)** Marca de Clase ($x_{i}$) -> $\dfrac{\text{L.S}+\text{L.I}}{2}$

# Ejercicios
## Ejercicio 1
En la siguiente tabla se muestra los datos de pacientes con problemas dentales de una clínica, se pide elaborar un
**1)** diagrama de barras
**2)** Elaborar un diagrama de torta

| N°  | Problema       | Pacientes | F   | %fi     | Grados  |
| :---: | :-------------- | :---------: | :---: | :-------: | :-------: |
| 1 | Caries         | 181       | 181 | 24.76%  | 89.14°  |
| 2 | Limpieza       | 179       | 360 | 24.49%  | 88.15°  |
| 3 | Extracción     | 138       | 498 | 18.88%  | 67.96°  |
| 4 | Prótesis       | 94        | 592 | 12.86%  | 46.29°  |
| 5 | Reconstrucción | 58        | 650 | 7.93%   | 28.56°  |
| 6 | Carillas       | 41        | 691 | 5.61%   | 20.19°  |
| 7 | Implantes      | 40        | 731 | 5.47%   | 19.70°  |
|     | Total          | 731       |     | 100.00% | 360.00° |

De acuerdo a la gráfica obtenida, 181 pacientes de los 731 de la muestra presentan problemas de caries, con un 24,76% de incidencia, seguida por problemas de limpieza (24,49%) y extracción (18,88%), lo que indica que la población es recurrente en estos problemas dentales.

**a) Gráfico de Torta**

![[EST.1.2.fa.png]]

**b) Gráfico de Barras**

![[EST.1.2.fb.png|600]]

## Ejercicio 2
El gerente de una compañía registra la vida útil en horas de 60 bombillas eléctricas como se muestran a continuación:
**Calcule.**
**a)** La distribución de frecuencias agrupadas con su gráfico.
**b)** ¿Cuál hora es más favorable de los intérvalos?
$$\begin{matrix}
807&811&620&650&817&732&747&823&844&907 \\
660&753&1050&918&857&867&675&880&878&890 \\
881&872&869&841&847&833&829&827&822&811 \\
766&787&923&792&803&933&947&717&817&753 \\
1056&1076&958&970&776&828&831&781&1088&1082 \\
832&863&852&788&980&889&1030&897&775&891
\end{matrix}$$

1) Amplitud=$1088-620 = 468$
2) # Clases = $1+3.33 \log{60} \approx 7$
3) IC = $\dfrac {468}{7} = 67$
4) LI = $620$

Se le suma al valor menor el intervalo de clase, en este caso 67

![[EST.1.2.fc.png]]

---
# Resumen
Las graficas estadisticas son herramientas visuales que facilitan la comprension de los datos:
- **Diagramas de Barras:** Para variables categoricas
- **Graficos Circulares (Torta):** Para mostrar proporciones
- **Histogramas:** Para distribuciones de frecuencia de variables continuas
- **Poligono de Frecuencia:** Linea que une los puntos medios de un histograma
- **Diagrama de Caja y Bigotes:** Muestra mediana, cuartiles y valores extremos
