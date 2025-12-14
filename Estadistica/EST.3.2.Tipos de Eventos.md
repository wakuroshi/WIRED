# 1.Eventos Mutuamente Excluyentes
$P(A\cup B)= P(A)+P(B)$
En los eventos mutuamente excluyentes, siendo A y B subconjuntos del espacio muestral E de cierto experimento aleatorio, son mutuamente excluyentes si y solo si los eventos no ocurren al mismo tiempo (La probabilidad de que me salga A y B es la suma de sus probabilidades)
![[EST.3.2.fa.png]]
# 2.Eventos no Excluyentes
$P(A \cup B)= P(A)+P(B)-P(A \cap B)$
Los no excluyentes también llamados solapados son aquellos que tienen puntos muestrales en común, pueden ocurrir al mismo tiempo (La probabilidad de que me salga A o B es la suma de sus probabilidades menos la probabilidad de A o B)
![[EST.3.2.fb.png]]
# 3.Eventos Complementarios $\Rrightarrow A^c$
$P(A)=1-P(A^c)$
$P(A)+P(A^c)=1$
El complemento de un evento A es el evento de que A no ocurra
# 4.Eventos Independientes
$P(A \cap B)=P(A)\cdot P(B)$
Los eventos independientes siempre estarán relacionados con los reemplazos y se definen como la multiplicación de ambas probabilidades no excluyentes
# 5.Eventos Condicionales
$P(A / B)=\dfrac{P(A \cap B)}{P(A)}$ (La probabilidad de A dado B es la probabilidad de A o B entre la probabilidad de A)
$P(B / A)=\dfrac{P(B \cap A)}{P(B)}$ (La probabilidad de B dado A es la probabilidad de B o A entre la probabilidad de B)
# 6.Eventos Dependientes
$P(A \cap B)=P(A) \cdot P(B / A)$
$P(B \cap A) = P(B) \cdot P(A / B)$

# 7.Ejercicios
## 7.1.Ejercicio 1
En una clase de 30 estudiantes, se recopilan datos sobre 2 asignaturas favoritas, matemática y literatura. 15 estudiantes dicen que les gusta matemática, 10 estudiantes les gusta literatura, y 5 estudiantes les gustan las 2 materias. Calcule:

**Espacios muestrales (E)**
E={# de estudiantes que prefieren 02 asignaturas favoritas}

M: Matemática | M={# de estudiantes que les gusta matemática}
L: Literatura | L={# de estudiantes que les gusta literatura}
$M \cup L$={# de estudiantes que les gustan ambas materias}

**a) Si selecciona un estudiante al azar ¿Cuál es la probabilidad de que le guste matemática o literatura?**
	 $P(M)=\dfrac{15}{30}=0.5 \rightarrow 50\%$ La probabilidad de sacar a un estudiantes al azar y le guste matemática es del 50%
	 $P(L)=\dfrac{10}{30}=0.3\bar{3} \rightarrow 33.3\bar{3}\%$ La probabilidad de sacar a un estudiante al azar y le guste matemática es del 33.33%

**b) ¿Cuál es la probabilidad de que le gusten ambas?**
	$M \cup L=\dfrac{5}{30}=\dfrac{1}{6}=0.1\bar{6}\rightarrow 16.6\bar{6}\%$ La probabilidad de que a un estudiante al azar le gusten ambas materias es de 16.66%

**c) ¿Cuál es la probabilidad de que le guste matemática o literatura?**
	$P(M \cup L)= P(M)+P(L)-P(M \cap L)$
	$P(M \cup L)= 0.5 + 0.3\bar{3}-0.1\bar{6}=0.6\bar{6}=66.6\bar{6}\%$

## 7.2.Ejercicio 2
En una fábrica se inspeccionan 100 bombillas y se registran 2 tipos de defectos:
**Defecto a.** Fallo en el filamento, se queman rápidamente (8)
**Defecto b.** Fallo en el casquillo no encajan bien (6)
Se encuentra 3 con ambos defectos
Calcule:
**a) Probabilidad de que una bombilla seleccionada al azar tenga un fallo en el filamento o un fallo en el casquillo**
E={# de bombillas}
F={# de bombillas con defecto de filamento}
C={# de bombillas con defecto de casquillo}

$P(F)=\dfrac{8}{100}=0.08\rightarrow 8\%$
$P(C)=\dfrac{6}{100}=0.06 \rightarrow 6\%$
$F \cup C=\dfrac{3}{100}=0.03\rightarrow 3\%$

No excluyentes
$P(F \cup C)=P(F)+P(C)-P(F \cap C)$
$P(F \cup C)=0.08+0.06-0.03=0.11\rightarrow 11\%$ 
Existe un 11% de probabilidad de que una bombilla al azar tenga un fallo en filamento o en el casquillo

## 7.3.Ejercicio 3
Se lanza un dado 2 veces y se anota el número que sale en el mismo orden de lanzamiento.
$$\begin{matrix}
1,1&1,2&1,3&1,4&1,5&1,6\\
2,1&2,2&2,3&2,4&2,5&2,6\\
3,1&3,2&3,3&3,4&3,5&3,6\\
4,1&4,2&4,3&4,4&4,5&4,6\\
5,1&5,2&5,3&5,4&5,5&5,6\\
6,1&6,2&6,3&6,4&6,5&6,6\\
\end{matrix}$$
Calcule
**a)La probabilidad de que el primer lanzamiento salga un número par y en el segundo lanzamiento salga un 5 o un 6**
	A={# de veces que salga par en el primer lanzamiento}
	B={# de veces que salga 5 o 6 en el segundo lanzamiento}
	$P(A)=\dfrac{{36}/{2}}{36}=\dfrac{1}{2}=0.5\rightarrow 5\%$
	$P(B)=\dfrac{12}{36}=0.3\bar{3}\rightarrow 33.3\bar{3}\%$
	$(A \cup B)=\{\text{\# de lanzamientos que salga par en el primero y 5 - 6 en el segundo}\}$
	$P(A\cup B)=0.5\cdot 0.3\bar{3}=0.1\bar{6}=16.6\bar{6}\%$

## 7.4.Ejercicio 4
Una caja contiene bolitas rojas y verdes, además, cada una tiene grabada una letra E y una letra M.

|           | Rojas | Verdes | Total |
| --------- | ----- | ------ | ----- |
| **E**     | 3     | 4      | 7     |
| **M**     | 5     | 3      | 8     |
| **Total** | 8     | 7      | 15    |
Calcule:
**a) La probabilidad de seleccionar una bolita verde de la caja y que tenga grabada la letra E**
S={# de bolitas en la caja}
V={# de bolitas verdes}
E={# de bolitas con la letra E}
R={# de bolitas rojas}
M={# de bolitas con la letra M}

$P(V)=\dfrac{7}{15}=0.4\bar{6}\rightarrow 46.6\bar{6}\%$
$(V \cup E)=\dfrac{4}{7}=0.57$
$P(V \cap V \cup E)=\dfrac{7}{15} \cdot \dfrac{4}{7}=0.2\bar{6}=26.6\bar{6}\%$