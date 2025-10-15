# Razonamiento Inductivo

Siempre va a ser verdadero

## Ejemplo 1:
P1: Vi un cuervo negro
P2: Los cuervos del parque eran negros
P3: Sobre el techo de mi casa se poso un cuervo negro

Se determina entonces por herencia que la PG (Proposicion General) es que todos los cuervos son negros

## Ejemplo 2
A1: EL atardecer llega en la tarde
A2: Los ocasos se dan en el atardecer
A3: El anochecer llega despues del atardecer

PG: Entre el atardecer y el anochecer ocurre el ocaso

Siendo (S) Sal, (A) Agua, (D) Disolver:

## Ejemplo 3
A: Siempre que uno A con S se disuelve (Es proposicion) 
B: La mezcla de A con S es para disolver (No es proposicion) 
C: $A+S=D$ (Es proposicion)
D: Si $A \land S \rightarrow D$ entonces $D+S/A$? (No es proposicion)
E: No quiero que se disuelva la sal con agua (No es proposicion)

Solucion general: Siempre que la sal y el agua se mezcla se disuelve

## Ejemplo 4
P1: $(4*1<2^1) \rightarrow (4<1)$ F
P2: $(4*2<2^2) \rightarrow (8<4)$ F
P3: $(4*3<2^3) \rightarrow (4<8)$ no

PG: $(4>1) \land (4<8)$

## Ejemplo 5

Siendo P:Ingenieria y Q:Ciencia

P1: La ingenieria es una ciencia $(P \rightarrow Q)$ F
P2: La ingenieria esta basada en las ciencias $(Q \rightarrow P)$ V
P3: La ingenieria necesitan la ingenieria $(Q \leftrightarrow P)$ F
P4: La ingenieria es mejor que las ciencias $(P>Q)$ F
P5: No se necesita ser ingeniero para estudiar ciencias (NO es proposicion)
P6: NO es una ciencia tener una ingenieria (NO es proposicion)

Solucion general: La ingenieria depende de la ciencia, pero no es una ciencia

Un cuadrado se parte en 4 cuadritos, uno de los cuadrados se parte en otros 4 cuadros y asi sucesivamente, despues de 69 particiones cuantos cuadros en total hay

A) 276
B) 257
C) 384
D) 387
E) 761

5+(4*68)

2 -> 14 -> 54 -> 128

7*2 = 14

27*2
3*3*3*2 = 54

2^6= 128

Dada la secuencia de la figura hallar x+y

F1:    3
F2:   5-7
F3: 9-11-13
F4:15-17-19-21
X--------------Y

a)804
b)825
c)738
d)729
e)809

Sacando la diferencia entre cada fila:
3->5 hay 2, de 5->9 hay 4...

Entonces:
$5-3=2;9-5=4;15-9=6 \dots 15=9+6=9+8-2$ $$\therefore a_n=a_{n-1} +2n - 2$$
Donde cada paso tiene una separacion de $2n$

Pero no sirve porque tendria que conocer $a_{n-1}$ para cada caso $a_n$, se puede generalizar la formula a terminos n-simos para evitar sucesiones
$$a_n=a_{n-1} +2n - 2 \rightarrow (a_n - a_{n-1} = 2n - 2) \in n \geq 2$$
$$a_n =a_1 \sum_{i=1}^{n-1}(a_{i+1}-a_i)$$ 
Donde $a_{i+1}-a_i$ representa la diferencia entre cada fila, entonces se simplifica a $2i$
$$a_n = 3 + \sum_{i=1}^{n-1}2n=3+2 \cdot \sum_{i=1}^{n-1}i$$
Por sumatoria de Gauss: $$\sum_{i=1}^{n} i= 1+2+3+4+\dots+n=\frac{n(n+1)}{2}$$
$$\therefore \sum_{i=1}^{n-1}i = \frac{(i-1)i}{2} \rightarrow a_n = 3 + 2 \cdot \frac{(i-1)i}{2}=3+(i-1)i$$
Relacion entre primer termino y ultimo termino de cada fila:
$F2=7; 7=5+2$
$F3=13; 13=9+4=9+2+2$
$F4=21; 21=15+6=15+2+2+2$
Entonces $b_n = a_n +2n - 2=3+(n-1)n +2n -2= n^2+n+1$
$x+y=a_n+b_n=3+n^2-n + n^2+n+1$
$$x+y=2n^2 + 4$$

Y despues de probar con todas las opciones la unica que da un numero exacto de fila es la a):
$$x+y=804; 2n^2=804$$
$$2n^2=800$$
$$n^2=400$$
$$n=20$$




