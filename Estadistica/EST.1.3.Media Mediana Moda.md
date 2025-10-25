# 1. Procedimiento
1. Ordena de menor a mayor los datos
2. Ubica la mediana (en el punto medio)
	- $\text{n\ par}\rightarrow c_{1}= \dfrac{n}{2}$ y $c_{2}=\dfrac{n+1}{2}$ Sumo y ubico el valor de los datos, en donde se encuentra $c_{1}$ y $c_{2}$ y se calcula $\dfrac{c_{1}+c_{2}}{2}$ 
	- n impar $\rightarrow \dfrac{n+1}{2}$
3. Moda: El valor que más se repite en los datos
4. Media: $\overline{X}=\dfrac{\sum{x_{i}}}{n}$

## 1.1.Ejercicio impar
Las calificaciones finales de geometría analítica de N estudiantes es:

$$\begin{matrix}
68&84&75&82 \\
73&79&88&73 \\
61&65&62&70 \\
66&86&80 \\
96&78&67 \\
79&78&73
\end{matrix}$$

Media= $\overline{X}=\dfrac{\sum{x_{i}}}{n}=\dfrac{1583}{21}=75,38$
Moda= 73
Mediana= 75

## 1.2.Ejercicio par
Las calificaciones finales de geometría analítica de N estudiantes es:
$$\begin{matrix}
59&60&67&60&55 \\
71&35&38&25&43 \\
75&80&71&25&23 \\
70&25&91&30&07
\end{matrix}$$

Media = $50,5$
Moda = 25
Mediana=57 
## 1.3.Ejercicio Media Ponderada
Las calificaciones finales de geometría analítica de N estudiantes es:
Con la nota 3 hay 5 personas, con la nota 4 hay 6...

| Xi  |     | Fi<br> | XiFi |
| --- | --- | ------ | ---- |
| 3   | ->  | 5      | 15   |
| 4   | ->  | 6      | 24   |
| 5   | ->  | 3      | 15   |
| 6   | ->  | 2      | 12   |
| 7   | ->  | 1      | 7    |
| 8   | ->  | 4      | 32   |
|     |     |        | 105  |
Solo se hace con media ponderada si el número de datos agrupados tiene frecuencia

a) Media = $\dfrac{\sum x_{i}f_{i}}{N}=\dfrac{105}{6}=17,5$
b) Moda= $4$
c) Mediana= $c_{1}=\frac{6}{2}=3$ y $c_{2}=\frac{6+1}{2}=3,5=4$; por lo tanto, $\text{Mediana}=\dfrac{c_{1}+c_{2}}{2} = \dfrac{5+6}{2}=5,5$
## 1.4.Ejercicio empresa
Una empresa de investigación de mercado realiza una encuesta para conocer el número de productos comprados por los consumidores, los datos recolectados corresponder a 30 clientes, donde cada número representa la cantidad de productos adquiridos por un cliente específico. Calcule la medida de tendencia central para datos agrupados.

$$\begin{matrix}
25&18&22&20&15&25 \\
18&35&28&9&28&30 \\
30&8&29&27&34&38 \\
24&40&35&36&31&41 \\
32&36&43&44&53&50
\end{matrix}$$
[Gráficas Estadísitica](<EST.1.2.Graficas Estadisticas>)
fi = Frecuencia
xi= Marcas de clase
F= Frecuencia acumulada
%f= Porcentaje de frecuencia
%F= Porcentaje de frecuencia acumulada
$Mediana = L_{i}+\left[\dfrac{\frac{n}{2}-F_{A-1}}{fi} \right]*A$  $F_{A}$ Es la frecuencia absoluta mediana, la cual se consigue dividiendo los datos (30 en este caso) entre 2, y se observa que contiene el número (el dato 3 en este caso), lo cual implica usar 7 como $F_{A-1}$, la amplitud es la amplitud de clase, en este caso, 8

$\text{\# de clases}=1+3,33\log_{}n$
$IC=\dfrac{Amp}{\text{\# de clases}}$
$\overline{x}=\dfrac{\sum x_{i}f_{i}}{N}$
Moda= valor de $f_{i}$ mayor

\# Intervalos clase

| #   | LI LS   | LI  | LS  | fi  | xi  | %fi     | F   | %F      | xi fi |
| --- | ------- | --- | --- | --- | --- | ------- | --- | ------- | ----- |
| 1   | [8-16)  | 8   | 16  | 3   | 12  | 10.00%  | 3   | 10.00%  | 36    |
| 2   | [16-24) | 16  | 24  | 4   | 20  | 13.33%  | 7   | 23.33%  | 80    |
| 3   | [24-32) | 24  | 32  | 10  | 28  | 33.33%  | 17  | 56.67%  | 280   |
| 4   | [32-40) | 32  | 40  | 7   | 36  | 23.33%  | 24  | 80.00%  | 252   |
| 5   | [40-48) | 40  | 48  | 4   | 44  | 13.33%  | 28  | 93.33%  | 176   |
| 6   | [48-56) | 48  | 56  | 2   | 52  | 6.67%   | 30  | 100.00% | 104   |
|     |         |     |     | 30  |     | 100.00% |     |         | 928   |
Amplitud = 45
\# de clases = 6
IC = 8
Moda = 28
Media = $\frac{\sum x_{i}f_{i}}{n}=30.93$
Mediana= 30,4