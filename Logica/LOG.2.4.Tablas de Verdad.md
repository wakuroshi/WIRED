# 1. Definición
Método de semántica lógica
- **Estructura:** Lista todas las posibles soluciones. Combinaciones de valores de verdad.
- **Fórmulas Posibles:** Si una fórmula tiene n variables proposicionales distintas, la tabla tendrá $2^n$ Filas.
	1) **Variable(P):** $2¹$ = 2 filas
	2) **Variable(P, Q):** $2²$ = 4 filas
	3) **Variables(P, Q, R):** $2³$ = 8 filas

Si un dato tiene solo implicaciones verdaderas es una tautología
Si un dato tiene solo implicaciones falsas es una contradicción
Si un dato tiene tanto implicaciones falsas como verdaderas es una contingencia 
## 2. Tablas
1. **Negación ($\neg$):** Invierte el valor de verdad

| P   | $\neg P$ |
| --- | -------- |
| V   | F        |
| F   | V        |
2. **Conjunción ($\land$):** "y" solo es verdadera si ambas P son verdaderas.

| P   | $\land$ | Q   |
| --- | ------- | --- |
| V   | V       | V   |
| F   | F       | V   |
| V   | F       | F   |
| F   | F       | F   |
3. **Disyunción ($\lor$):** "o" solo es falsa si alguna P es falsa.

| P   | $\lor$ | Q   |
| --- | ------ | --- |
| V   | V      | V   |
| V   | V      | F   |
| F   | V      | V   |
| F   | F      | F   |
4. **Condicional ($\rightarrow$):** "Si entonces" solo es falsa si el antecedente (P) es verdadero el consecuente (Q) es falso.

| P   | $\rightarrow$ | Q   |
| --- | ------------- | --- |
| V   | V             | V   |
| V   | F             | F   |
| F   | V             | V   |
| F   | V             | F   |
5. **Bicondicional($\leftrightarrow):$** "Sí y solo si" es verdadera si ambas p tienen el mismo valor de verdad.

| P   | $\leftrightarrow$ | Q   |
| --- | ----------------- | --- |
| V   | V                 | V   |
| V   | F                 | F   |
| F   | F                 | V   |
| F   | F                 | V   |
## 2.1. Ejercicios
##### 2.1.1.Primer ejercicio
Sí la computadora está encendida o el monitor conectado entonces el usuario puede trabajar. El hardware funciona y el software está actualizado. No es cierto que el programa no tenga errores. El sistema está operativo y el usuario está autenticado, entonces la aplicación está disponible, de lo contrario no lo está

P: La computadora está encendida
Q: El monitor está conectado
U: El usuario puede trabajar
$((P\lor Q)\rightarrow U)$

| (P  | $\lor$ | Q)  | $\rightarrow$ | U   |
| --- | ------ | --- | ------------- | --- |
| V   | V      | V   | V             | V   |
| V   | V      | F   | V             | V   |
| F   | V      | V   | V             | V   |
| F   | F      | F   | V             | V   |
| V   | V      | V   | F             | F   |
| V   | V      | F   | F             | F   |
| F   | V      | V   | F             | F   |
| F   | F      | F   | V             | F   |
R: El hardware funciona
S: El software está actualizado
$R\land S$

| R   | $\land$ | S   |
| --- | ------- | --- |
| V   | V       | V   |
| V   | F       | F   |
| F   | F       | V   |
| F   | F       | F   |

T: El programa no tiene errores
$\neg T$

| $\neg$ | T   |
| ------ | --- |
| F      | V   |
| F      | V   |
| V      | F   |
| V      | F   |

V: El sistema está operativo
W: El usuario está autenticado
X: La aplicación está disponible
$((V\land W)\rightarrow X)\leftrightarrow \neg X$

| ((V | $\land$ | W)  | $\rightarrow$ | X)  | $\leftrightarrow$ | $\neg$ | X   |
| --- | ------- | --- | ------------- | --- | ----------------- | ------ | --- |
| V   | V       | V   | V             | V   | F                 | F      | V   |
| V   | F       | F   | V             | V   | F                 | F      | V   |
| F   | F       | V   | V             | V   | F                 | F      | V   |
| F   | F       | F   | V             | V   | F                 | F      | V   |
| V   | V       | V   | F             | F   | F                 | V      | F   |
| V   | F       | F   | V             | F   | V                 | V      | F   |
| F   | F       | V   | V             | F   | V                 | V      | F   |
| F   | F       | F   | V             | F   | V                 | V      | F   |

##### 2.1.2.Segundo ejercicio
Demostrar la desigualdad
$P(1)=4\cdot 1<2^{1}=4<1$
$P(2)=4\cdot 2<2^{2}=8<4$
$P(1)=4\cdot 3<2^{3}=4<8$
$P(4)=4\cdot 4<2^{4}=16<16$
P(k)? Demuestra que P(k+1) es verdadero o falso

$P(k)=4\cdot k<2^{k}$
Se demuestra con P(4+1) al pedirse la demostración con k+1 después de 4, 
P: $4\cdot 5<2^{5}$
Q: $20<32$
$4\cdot 5 <2^{5}=20<32$

| P   | $\leftrightarrow$ | Q   |
| --- | ----------------- | --- |
| V   | V                 | V   |
| V   | F                 | F   |
| F   | F                 | V   |
| F   | V                 | F   |
El resultado es verdadero, así que se demuestra que es verdadero

##### 2.1.3.Tercer Ejercicio
$(P\land Q)\lor[(\neg P)\lor(\neg Q)]$

| (P  | $\land$ | Q)  | $\lor$ | [($\neg$ | P)  | $\lor$ | ($\neg$ | Q)] |
| --- | ------- | --- | ------ | -------- | --- | ------ | ------- | --- |
| V   | V       | V   | V      | F        | V   | F      | F       | V   |
| V   | F       | F   | V      | F        | V   | V      | V       | F   |
| F   | F       | V   | V      | V        | F   | V      | F       | V   |
| F   | F       | F   | V      | V        | F   | V      | V       | F   |
Es una tautología

$[(\neg P)\land Q]\lor [P\land(\neg Q)]$

| [($\neg$ | P)  | $\land$ | Q]  | $\lor$ | [P  | $\land$ | ($\neg$ | Q)] |
| -------- | --- | ------- | --- | ------ | --- | ------- | ------- | --- |
| F        | V   | F       | V   | F      | V   | F       | F       | V   |
| F        | V   | F       | F   | V      | V   | V       | V       | F   |
| V        | F   | V       | V   | V      | F   | F       | F       | V   |
| V        | F   | F       | F   | F      | F   | F       | V       | F   |
Es una contingencia