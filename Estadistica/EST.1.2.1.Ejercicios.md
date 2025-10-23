# 1. Ejercicio Compañía
El gerente de una compañía registra el número de unidades de cierto trabajo completadas por lo empleados. 50 empleados realizan el mismo trabajo divididos en 2 grupos de 25 y en salones diferentes. En el salón A el gerente registra el siguiente número de unidades completadas por día.

 **Salón A**
$$
\begin{matrix} \\
21&22&20&15&25 \\
0&28&9&28&30 \\
24&29&27&34&38 \\
24&35&36&31&41 \\
32&43&44&53&50
\end{matrix}$$
**Salón B**
$$
\begin{matrix}
6&21&13&36&18 \\
24&32&16&18&20 \\
28&25&33&26&30 \\
26&29&35&45&59 \\
32&31&30&40&30
\end{matrix}
$$
**a)** Realice el histograma de frecuencia del salón A
**b)** Combine todos los datos y dibuje el histograma de frecuencias con una amplitud de 4 para cada intervalo

Promedio de los datos
$x = \frac{\sum x_i * fi}{\sum N}$

## 1.1.Respuesta a:
Para el histograma de frecuencias del salón a primero se encuentran los datos para construir la tabla:
##### Amplitud de intérvalos ($A$) 
$Amplitud= \text{Valor Mayor}-\text{Valor menor}$.
El valor mayor del salón A es 53, en una app de cálculo se puede encontrar con la función =MAX(celda1:celda2). El valor mínimo es 0, se podría conseguir con =MIN(celda1:celda2)
$Amplitud=53-0=53$

##### # de Clases ($C$) 
$C=1+3,33 \log{N}$
Donde N es la cantidad total de elementos, en este caso trabajadores, el cual en una app de cálculo se consigue con =COUNT(celda1:celda2)
$C=1+3.33\log{}{25}\approx 5.65$
Se redondea al siguiente número más cercano
$C\approx 6$

##### Intervalo de Clases ($IC$)
$IC=\dfrac{\text{Amplitud}}{\text{\#Clases}}$
Teniendo amplitud y # Clases el cálculo es directo
$IC=\frac{53}{6}= 8.8\overline{33}$
$IC \approx 6$

##### Límite Inferior de Clase ($L_{I}$)
Valor menor conseguido a mano o con la función MIN
$L_{I}=0$
$L_{I}=9$
$\vdots$
Se debe calcular el límite inferior para cada clase, así poder conseguir los cálculos de forma correcta.
##### Límite Superior Clase ($L_{S}$)
$L_{S}=\text{Valor Menor} +\text{Amplitud}$
Al igual que el anterior se calcula para cada clase, se toma como límite abierto, es decir, solo cuentan los valores anteriores a él
$L_{S}=9$
$L_{S}=18$
$\vdots$

##### Marca de Clase ($x_{i}$) 
$x_{i}=\dfrac{\text{L.S}+\text{L.I}}{2}$
Es un promedio de cada clase, su cálculo es sencillo al ser con valores ya calculados, se realiza para cada clase
$x_{i}=\dfrac{9+0}{2}=4.5$
$\vdots$

### 1.1.1 Tabla y Gráficas
fi es la frecuencia absoluta
F es la frecuencia absoluta acumulada

| N°  | IC      | LI  | LS  | fi  | F   | xi   |
| --- | ------- | --- | --- | --- | --- | ---- |
| 1   | [0-9)   | 0   | 9   | 1   | 1   | 4.5  |
| 2   | [9-18)  | 9   | 18  | 2   | 3   | 13.5 |
| 3   | [18-27) | 18  | 27  | 6   | 9   | 22.5 |
| 4   | [27-36) | 27  | 36  | 9   | 18  | 31.5 |
| 5   | [36-45) | 36  | 45  | 5   | 23  | 40.5 |
| 6   | [45-54) | 45  | 54  | 2   | 25  | 49.5 |
|     | Total   |     |     | 25  |     |      |
![Histograma Salón A](EST.1.2.1.fa.png)

### 1.1.2 Promedio de los datos
Se calcula con la fórmula mencionada anteriormente en las notas: $x = \frac{\sum x_i * fi}{\sum N}$
Para realizarlo en una hoja de cálculo se puede usar la función =SUMPRODUCT(celda1:celda2,celda3:celda4), se multiplica celda1 por celda 3 hasta que se termine el rango, también se puede usar con una suma matricial, con la funcion =ARRAYS, o más simple aún con =SUMA(celda1:celda2 * celda3:celda4) y al cerrar el paréntesis usas ctrl + shift + enter.
$x=125.25$

## 1.2.Respuesta b
$$
\begin{matrix} \\
21&22&20&15&25 \\
0&28&9&28&30 \\
24&29&27&34&38 \\
24&35&36&31&41 \\
32&43&44&53&50 \\
6&21&13&36&18 \\
24&32&16&18&20 \\
28&25&33&26&30 \\
26&29&35&45&59 \\
32&31&30&40&30
\end{matrix}$$
Esta es la tabla resultante de combinar todos los datos del salón A y salón B, se realizan los mismos cálculos que en el histograma A, pero con la nueva tabla
$Amplitud = 59$
$IC = 4$  // Dato del ejercicio

### 1.2.1.Tabla y Gráfica
Primero se realiza la tabla para saber el número de clases necesarias para contener a todos los datos.

| N°  | IC      | LI  | LS  | fi  | F   | xi  |
| --- | ------- | --- | --- | --- | --- | --- |
| 1   | [0-4)   | 0   | 4   | 1   | 1   | 2   |
| 2   | [4-8)   | 4   | 8   | 1   | 2   | 6   |
| 3   | [8-12)  | 8   | 12  | 1   | 3   | 10  |
| 4   | [12-16) | 12  | 16  | 2   | 5   | 14  |
| 5   | [16-20) | 16  | 20  | 3   | 8   | 18  |
| 6   | [20-24) | 20  | 24  | 5   | 13  | 22  |
| 7   | [24-28) | 24  | 28  | 8   | 21  | 26  |
| 8   | [28-32) | 28  | 32  | 11  | 32  | 30  |
| 9   | [32-36) | 32  | 36  | 7   | 39  | 34  |
| 10  | [36-40) | 36  | 40  | 3   | 42  | 38  |
| 11  | [40-44) | 40  | 44  | 3   | 45  | 42  |
| 12  | [44-48) | 44  | 48  | 2   | 47  | 46  |
| 13  | [48-52) | 48  | 52  | 1   | 48  | 50  |
| 14  | [52-56) | 52  | 56  | 1   | 49  | 54  |
| 15  | [56-60) | 56  | 60  | 1   | 50  | 58  |
|     | Total   |     |     | 50  |     |     |
Se observa que
$\text{\# de clases}=15$
Y ya se tiene $x_{i}$ para todo elemento en la tabla, por lo que solo resta la gráfica

![Histograma Salón A y Salón B](EST.1.2.1.fb.png)

Como último paso, el promedio de todos los datos sería:
$x=98.6\overline{6}$