# Primer ejercicio
En la siguiente secuencia de figuras ¿Cuál es el número total de trapecios rectangulares que conforman la figura 10?
![[LOG.1.2.fa.png|400]]
**a)** 32
**b)** 60
**c)** 81
**d)** 64
**e)** 91

Primero que todo vemos la diferencias de trapecios rectangulares, hay que tener en cuenta que un trapecio rectangular es una figura con 2 lados paralelos y 2 lados no paralelos, con 2 ángulos rectos consecutivos, es decir, las figuras que se visualizan a la derecha no son trapecios.

Primero que todo se cuentan los trapecios, en la primera visiblemente es 1, ahora se dará el ejemplo para la segunda figura para entender el modo de conteo, se tienen 2 como figura individual, si se combinan ambas son 3 y si se combinan y se juntan con el paralelogramo. Es decir, se cuenta individualmente las de la izquierda y sus combinaciones, todas las posibles. Por lo que podría decirse que la diferencia son:

1, 4, 8, 13
1 ->4 = 3 ; 4->8=4, 8->13=5

Se observa una progresión, se podría seguir para tener una diferencia de uno y aplicar el método de encontrar el polinomio p(n)=An² + Bn + C, sin embargo, en este caso se observa que $a_n - a_{n-1}=  n + 1$, porque aumenta cada vez 1, comenzando en 1, por ejemplo, $n=2: a_{2}−a_{1}=4−1=3; n+1=3$.

Entonces se puede decir que la suma de todo los n+1 más un $a_{1}$ da el resultado, o expresado de mejor forma:$$a_{n}=a_{1} + \sum_{k=2}^{n}{k+1}$$
Se puede separar la sumatoria, la sumatoria de K sería $\frac{n(n+1)}{2}-1$, el -1 debido a que empieza en 2, no en 1. 
El término 1 se podría escribir como n-1, debido a que se suma el 1 n veces, pero empieza en 2.

Al final se puede escribir como: $a_{n}=1+\frac{n(n+1)}{2}-1+n-1$. Luego de simplificar todo lo posible queda: $$P(n)= \frac{n(n+3)}{2}-1$$
Que en la figura 10 se traduce como 64, es decir, el resultado es la opción **d**.


# Segundo Ejercicio
Determina el número de círculos en blanco
![[LOG.1.2.fb.png]]
**a)** 900
**b)** 1024
**c)** 929
**d)** 512
**e)** 958

El primer paso es ver cuantos círculos en blanco tiene la figura:
$f_{1}= 5$
$f_{2}= 11$
$f_{3}= 19$
En las diferencias se observa 5->11 = 6; 11->19 = 8, se podría resolver como el primer ejercicio, sin embargo, en este caso se ve conveniente aplicar el polinomio de grado 2.

Una progresión que tiene una diferencia que crece cada vez 2 unidades, podría decirse que su segunda derivada crece en 2 unidades, por ejemplo, de 5->11 se difiere 6, de 11->19=8, no es una progresión lineal, pero el siguiente grado si lo es, con diferencia de 2, es decir, la primera derivada no es una constante, pero la segunda sí, es decir, se tiene un 

$\dfrac{d²}{dn²}An² = 2$
$
La derivada de $Ax^n = nAn^{n-1}$  hasta que el exponente sea 0, multiplicando $n(n-1)(n-2)\dots$ Es decir, sería lo mismo que decir $n!$, por lo que queda que $An!$ =2, o expresado de otra forma $A=\dfrac{ratio\ de\ crecimiento}{n!}$ , en este caso $A=\dfrac{2}{2!} = 1$.

También con esa explicación queda demostrado que es un $P(n)=An²+Bn+C$, sabiendo A y con 2 casos podríamos conocer el valor de B y C con un sistema de ecuaciones, resuelto por el método más conveniente.

$$\begin{cases} 
n²+B+C=5 \\
4+2B+C=11
\end{cases}$$
Resolviendo este sistema de ecuaciones se puede llegar a que $B= 3 \hspace{3mm} \land \hspace{3mm} C=1$.
Por lo que $P(n)$ tiene por resultado: $$P(n)= n²+3n+1$$
Qué reemplazando el caso n por 29 se destaca que $P(29)= 929$, es decir, el resultado es la opción **c**.

# Ejercicio 3
Hallar el triángulo de la figura 225.
![[LOG.1.2.fc.png]]
En la figura se observa como en:
$F_{1}$= 1
$F_{2}$= 3
$F_{3}$= 5
Esta sucesión son todos los números impares, podría escribirse como $F(n)= 2n-1$ porque al empezar n en 1, si o si debe restarse 1 para que sea igual al primer caso, sin embargo, el ejercicio no explica correctamente que debe hallarse, si la suma de todos los triángulos o solo de una fila, ya el caso de una fila está resuelto, el cual es $P(225) = 2(225) - 1 = 457.$ Para el segundo caso, el de sumar todos los triángulos se observa que la sucesión sería.
$F_{1}$= 1
$F_{2}$= 4
$F_{3}=9$
Se ve fácilmente que la suma de todos los impares son todos los cuadrados, es decir, $P(n)=n²$, por lo que $P(225)=255² =50625$.