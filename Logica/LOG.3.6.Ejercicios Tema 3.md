---
tags:
  - Logica
---
# 1.Ejercicios 
## 1.1.Determinar cuáles son las siguientes expresiones son fórmulas proposicionales
1. $p$
	Es una fórmula debido a que cualquier variable proposicional es una fórmula (Regla base)
2. $(p)$
	Es una fórmula debido a que cualquier variable proposicional es una fórmula (Regla base), el paréntesis externo se puede omitir
3. $(p \lor \neg q)$
	Es una fórmula, debido a que si p y q son fórmulas, cualquier expresión con conectores lógicos válidos es una fórmula (Reglas binarias) y el paréntesis externo es completamente omitible
4. $p \lor \neg q$
	Es una fórmula, debido a que si p y q son fórmulas, cualquier expresión con conectores lógicos válidos es una fórmula (Reglas binarias)	
5. $\neg(p \lor p)$
	Es una fórmula, tiene como equivalente $\neg p$ si se aplican las leyes lógicas, si p es una fórmula $\neg p$ también (Regla de negación)
6. $[(p\rightarrow q)\lor (q\rightarrow p)]$
	Es una fórmula, porque si p y q son fórmulas cualquier forma de p con q son una fórmula, si tomamos $p\rightarrow q$ como w y a $q\rightarrow p$ como s, se tiene $w \lor s$, lo que es una fórmula por las reglas binarias
7. $(p \lor \land q)$
	No es una fórmula, debido a que no posee una conexión lógica válida, los conectivos lógicos conectan y modifican las proposiciones, no a otros conectivos lógicos

## 1.2.Definir por recursión sobre formulas las siguientes funciones
1. np(F) que calcula el número de paréntesis de la fórmula F. Por ejemplo, $np((p\rightarrow(\neg q \lor p)))=4$
	**Caso base:**
		si F es una variable proposicional np(F)=0
	**Recursión:**
		Si F es $\neg$G entonces np(F)=np(G)
		Si F es $(G \circ H)$ y $\circ \in \{\lor, \land, \rightarrow, \leftrightarrow\} \therefore np(F)=np(G) + np(H)+2$
	**Ejemplo:**
	$np((p\rightarrow(\neg q \lor p))) = 4$

2. Subf(F) que calcula el conjunto de las subfórmulas de la fórmula F. Por ejemplo, $Subf(p\rightarrow \neg q\lor p) = \{p\rightarrow \neg q \lor p, p, \neg q \lor p, \neg q, q\}$ 
	**Caso base:**
		Si F es una variable proposicional, Subf(F)=F
	**Caso recursivo:**
		Si $F=\neg G$, $Subf(F)=\neg G, Subf(G)$ 
		Si F es $(H \circ S)$ y $\circ \in \{\lor, \land, \rightarrow, \leftrightarrow\} \therefore Subf(F)=F,Subf(H), Subf(S)$
	**Ejemplo:**
	$Subf(p\rightarrow \neg q\lor p) = \{p\rightarrow \neg q \lor p, p, \neg q \lor p, \neg q, q\}$

## 1.3.Demostrar por inducción que todas las fórmulas proposicionales tienen un número par de paréntesis
Se tiene un caso base F es una variable proposicional, el número de paréntesis de F np(F) es 0 por definición, 0 es número par
Se supone que las fórmulas G y H se cumple
	np(G) es par
	np(H) es par

**Casos F es una negación:**
	G es la negación de F
	por lo tanto np(F) = np (G)
	np(G) es par
	$\therefore$np(F) es par    

**Caso 3: F es una fórmula binaria**
	Si $F = (G \circ H)$ donde $\circ \in {\lor, \land, \rightarrow, \leftrightarrow}$
	Por definición: $np(F) = np(G) + np(H) + 2$
    - $np(G)$ es par ⇒ $np(G) = 2k$ para algún $k \in \mathbb{N}$
    - $np(H)$ es par ⇒ $np(H) = 2m$ para algún $m \in \mathbb{N}$
    $\therefore$ $np(F) = 2k + 2m + 2 = 2(k + m + 1)$
    $2(k + m + 1)$ es claramente par ya que 2(k+m+1) es equivalente a 2w si w es k+m+1

En el caso base los paréntesis son par (0 paréntesis), las negaciones preservan esa paridad, las fórmulas binaras suman 2 paréntesis más cada vez, por lo que son pares al obedecer np(F)=2w
**Ejemplo:**
Para $F = ((p \lor q) \land r)$:
- $np(p) = 0$ (par)
- $np(q) = 0$ (par)
- $np(r) = 0$ (par)
- $np((p \lor q)) = 0 + 0 + 2 = 2$ (par)
- $np(F) = 2 + 0 + 2 = 4$ (par)

## 1.4.Para la siguiente fórmula
$p\rightarrow \neg q \lor p$
escribir la fórmula con paréntesis, construir el árbol de análisis y determinar todas sus subfórmulas
**Árbol de análisis**
![Árbol de análisis](LOG.3.6.FA.png)
**Paréntesis**
	$(p\rightarrow (\neg q \lor p))$
**Subfórmulas**
	$Subf(p\rightarrow \neg q \lor p)=\{p\rightarrow \neg q \lor p, p, \neg q \lor p, \neg q, q\}$
## 1.5.Calcular el valor de la fórmula $(p \lor q)\land (\neg q\lor r)$ en las siguientes interpretaciones
1. $I_{1}$ tal que $I_{1}(p) = I_{1}(r)=1,\ I_{1}(q)=0$ 
	$(p \lor q)\land (\neg q\lor r)$

| (1  | $\lor$ | 0)  | $\land$ | ($\neg$ 0 | $\lor$ | 1)  |
| --- | ------ | --- | ------- | --------- | ------ | --- |
|     | 1      |     | $\land$ | (1        | $\lor$ | 1)  |
|     | 1      |     | $\land$ |           | 1      |     |
|     |        |     | 1       |           |        |     |
$I_{1}\models (p \lor q)\land (\neg q\lor r)$

2. $I_{2}$ tal que $I_{_2}(r)=1, \ I_{2}(p)=I_{2}(q)=0$
	$(p \lor q)\land (\neg q\lor r)$

| (0  | $\lor$ | 0)  | $\land$ | ($\neg$ 0 | $\lor$ | 1)  |
| --- | ------ | --- | ------- | --------- | ------ | --- |
|     | 0      |     | $\land$ | 1         | $\lor$ | 1   |
|     | 0      |     | $\land$ |           | 1      |     |
|     |        |     | 0       |           |        |     |
$I_{2}\not\models (p \lor q)\land (\neg q\lor r)$
## 1.6.Demostrar que para toda la fórmula F se tiene que para todo par de interpretaciones $I_{1}, I_{2}$, si $I_{1}(p)=I_{2}(p)$ para todas las variables proposicionales de F, entonces $I_{1}(F)=I_{2}(F)$
$\forall F: (\forall I_{1}\land I_{2}\rightarrow I_{1}(p)= I_{2}(p) \leftrightarrow I_{1}(F)=I_{2}(F))$
Demostración inducción:
**Caso base:**
	P=F
	Si $I_{1}(p)=I_{2}(p)$, $\forall p \in Var(F) \land Var(F)=\{p\} \therefore I_{1}(F)=I_{1}(p)=I_{2}(F)=I_{2}(p)$ Se cumple
	
**Caso inductivo**
	**Caso 1:** $F = \neg G$
	$Var(F)=Var(G)$
	Si $I_{1}(p)=I_{2}(p)$, $\forall p \in Var(F)\therefore I_{1}(G)=I_{2}(G)\therefore I_{1}(\neg G)=\neg I_{1}(G)=I_{2}(\neg G)= \neg I_{2}(G)$ Se cumple
	**Caso 2:** $F=(G\circ H)$
	$Var(F)= Var(G)\circ Var(H)$
	$\circ \in \{\land, \lor \rightarrow, \leftrightarrow\}$
	Si $I_{1}(p)=I_{2}(p)$, $\forall p \in Var(F)\therefore p\in Var(G) \land p \in Var(H)$
	$I_{1}(G)=I_{2}(G)$
	$I_{1}(H)=I_{2}(H)$
	$\therefore I_{1}(G\circ H)=I_{1}(G)\circ I_{1}(H)=I_{2}(G)\circ I_{2}(H) = I_{2}(G \circ H)$ Se cumple
Se demuestra que $\forall F: (\forall I_{1}\land I_{2}\rightarrow I_{1}(p)= I_{2}(p) \leftrightarrow I_{1}(F)=I_{2}(F))$, es cierta

## 1.7.Determinar cuáles de las siguientes interpretaciones es modelo de la fórmula $(p\lor q)\land (\neg q\lor r)$
1. $I_{1}$ tal que $I_{1}(p)=I_{1}(r)=1,\ I_{1}(q)=0$
	$I_{1}\models (p \lor q)\land (\neg q\lor r)$ (Demostrado en la sección 1.5)

2. $I_{2}$ tal que $I_{2}(r)=1,\ I_{2}(p)=I_{2}(q)=0$
	$I_{2}\not\models (p \lor q)\land (\neg q\lor r)$ (Demostrado en la sección 1.5)

## 1.8.Determinar si las siguientes fórmulas son satisfacibles o insatisfacible
1. $(p\rightarrow q)\land (q\rightarrow r)$
	$(p \rightarrow r)$ Ley de transitividad

| (p  | $\rightarrow$ | r)  |
| --- | ------------- | --- |
| V   | V             | V   |
| V   | F             | F   |
| F   | V             | V   |
| F   | V             | F   |
	Es satisfacible, pero no válida

2. $p \land \neg p$
	0 Contradicción
	Es insatisfacible
## 1.9.Demostrar o refutar las siguientes proposiciones
1. F es tautología syss $\neg F$ es insatisfacible
	$I(F)=1$
	$I(\neg F)=0$
	$\forall I(F) =1, \ I(\neg F)$= 0, $\neg F$ es insatisfacible
	$\forall I(\neg F) =0,\ I(F)=1$ es tautología
	
	***Verdadera*** 

2. Si F es tautología, entonces F es satisfacible
	Si F=1
	$I(F)=I(1)=1$ F es satisfacible si existe una interpretación que la satisface
	
	***Verdadera***

3. Si F es satisfacible, entonces $\neg F$ es insatisfacible
	Teniendo un $F = I(p)=1$
	$\neg F= \neg P$, $I(p)=0, I(\neg p)=1$
	F satisfacible no implica $\neg F$ insatisfacible, también, si F es satisfacible, pero no válida, al menos una interpretación será insatisfacible, por lo tanto
	
	**Falsa***
	
## 1.10.En cada caso, determinar todos los modelos de la fórmula proposicional correspondiente
Clasificar las fórmulas anteriores en tautologías, contingentes y contradicciones. ¿Cuáles son satisfacibles? ¿Cuáles son insatisfacibles?
1. $(p\rightarrow q) \lor (q \rightarrow p)$
	$(\neg p \lor q)\lor(\neg q \lor p)$ Condicional disyunción
	$(\neg p \lor p)\lor (\neg q \lor q)$ Conmutativa
	$1 \lor 1$ Tercio exclusivo
	1 Identidad

Tautología, satisfacible

2. $(p\rightarrow q) \land \neg (p \rightarrow q)$
	$0$ contradicción
Contradicción, insatisfacible

3. $p\rightarrow q$

| p   | $\rightarrow$ | q   |
| --- | ------------- | --- |
| V   | V             | V   |
| V   | F             | F   |
| F   | V             | V   |
| F   | V             | F   |
Contingencia, satisfacible

4.  $p \lor \neg p$
	$1$ Complementación
Tautología, satisfacible

5. $p \land \neg p$
	0 Contradicción
Contradicción, insatisfacible

6. $(p\rightarrow q)\lor (q \rightarrow p)$
	$(\neg p \lor q)\lor(\neg q \lor p)$ Condicional disyunción
	$(\neg p \lor p)\lor (\neg q \lor q)$ Conmutativa
	$1 \lor 1$ Tercio exclusivo
	1 Identidad

Tautología, satisfacible

5. $(p \leftrightarrow q) \lor (q \leftrightarrow p)$
	$(p\leftrightarrow q)$

| p   | $\leftrightarrow$ | q   |
| --- | ----------------- | --- |
| V   | V                 | V   |
| V   | F                 | F   |
| F   | F                 | V   |
| F   | V                 | F   |
Contingencia, satisfacible

## 1.11.Demostrar que las fórmulas que aparecen en la transparencia 19 del tema 1 son tautologías:
1. $F \rightarrow F$ Ley de identidad
	$\neg F \lor F$  (Ley de condicional disyunción)

| $\neg$ F | $\lor$ | F   |
| -------- | ------ | --- |
| F        | V      | V   |
| V        | V      | F   |
Tautología

2. $F \lor \neg F$ Ley del tercio excluso

| F   | $\lor$ | $\neg$ F |
| --- | ------ | -------- |
| V   | V      | F        |
| F   | V      | V        |
Tautología

3. $\neg(F \land \neg F)$ Principio de no contradicción
	$\neg F \lor F$

| $\neg$ F | $\lor$ | F   |
| -------- | ------ | --- |
| F        | V      | V   |
| V        | V      | F   |
Tautología

4. $(\neg F \rightarrow F)\rightarrow F$ Ley de Clavius
	$\neg (F \lor F)\lor F$ (Condicional disyunción)
	$\neg F \lor F$ (Idempotencia)

| $\neg$ F | $\lor$ | F   |
| -------- | ------ | --- |
| F        | V      | V   |
| V        | V      | F   |
Tautología

5. $\neg F \rightarrow ( F\rightarrow G)$ Ley de Duns Scoto
	$F \lor \neg F \lor F$ (Condicional disyunción)
	$F \lor \neg F$ (Idempotencia)

| F   | $\lor$ | $\neg$ F |
| --- | ------ | -------- |
| V   | V      | F        |
| F   | V      | V        |
Tautología

6. $((F\rightarrow G)\rightarrow F)\rightarrow F$ Ley de Peirce
	$\neg((F \land \neg G)\lor F)\lor F$ (Condicional disyunción)
	$((\neg F \lor G) \land \neg F) \lor F$ De Morgan
	$[(\neg F \lor G)\lor F]\land [\neg F \lor F]$ Distributiva
	$1 \land 1$ Complementación
	$1$
Tautología

7. $(F \rightarrow G)\land F\rightarrow G$ Modus ponens
	$(\neg F \lor G)\land F \rightarrow G$ (Condicional disyunción)
	$[\neg F \land F] \lor [F \land G]\rightarrow G$ (Distributiva)
	$\neg [F \land G] \lor G$ (Condicional disyunción)
	$\neg F \lor \neg G \lor G$ De Morgan
	$\neg F \lor 1$ Tercio exclusivo
	1
Tautología

8. $(F \rightarrow G) \land \neg G \rightarrow \neg F$ Modus tollens
	$\neg [\neg (F \land \neg G)\land \neg G]\lor \neg F$ (Condicional disyunción)
	$((F \land \neg G) \lor G)\lor \neg F$ (De Morgan)
	$[(F \lor G)\land (\neg G \lor G )]\lor \neg F$ (Distributiva)
	$F \lor G \lor \neg F$ (Tercio exclusivo) 
	$1 \lor G$ (Tercio exclusivo)
	1
Tautología

## 1.12.Demostrar las equivalencias lógicas que aparecen en la transparencia 20 del tema 1
1. Idempotencia: 
	$F \lor F \equiv F$
	$F \land F \equiv F$

| F   | $\circ$ | F   |
| --- | ------- | --- |
| V   | V       | V   |
| F   | F       | F   |
Todas las columnas son iguales

2. Conmutatividad: 
	$F \lor G \equiv G \lor F$
	$F \land G \equiv G \land F$

| F   | G   | $F \lor G$ | $G \lor F$ |
| --- | --- | ---------- | ---------- |
| V   | V   | V          | V          |
| V   | F   | V          | V          |
| F   | V   | V          | V          |
| F   | F   | F          | F          |

| F   | G   | $F \land G$ | $G \land F$ |
| --- | --- | ----------- | ----------- |
| V   | V   | V           | V           |
| V   | F   | F           | F           |
| F   | V   | F           | F           |
| F   | F   | F           | F           |
Iguales las salidas, se demuestra

3. Asociatividad:
	$F \lor (G \lor H) \equiv (F \lor G) \lor H$
	$F \land (G \land H) \equiv (F \land G) \land H$
	

| F   | G   | H   | G∨H | F∨(G∨H) | F∨G | (F∨G)∨H |
| --- | --- | --- | --- | ------- | --- | ------- |
| V   | V   | V   | V   | V       | V   | V       |
| V   | V   | F   | V   | V       | V   | V       |
| V   | F   | V   | V   | V       | V   | V       |
| V   | F   | F   | F   | V       | V   | V       |
| F   | V   | V   | V   | V       | V   | V       |
| F   | V   | F   | V   | V       | V   | V       |
| F   | F   | V   | V   | V       | F   | V       |
| F   | F   | F   | F   | F       | F   | F       |
Columnas iguales, se demuestra

4. Absorción:
	$F \land (F\lor G) \equiv F$
	$F \lor (F \land G) \equiv F$

| F   | G   | F∨G | F∧(F∨G) |
| --- | --- | --- | ------- |
| V   | V   | V   | V       |
| V   | F   | V   | V       |
| F   | V   | V   | F       |
| F   | F   | F   | F       |

| F   | G   | F$\land$G | F$\lor$(F$\land$G) |
| --- | --- | --------- | ------------------ |
| V   | V   | V         | V                  |
| V   | F   | F         | V                  |
| F   | V   | F         | F                  |
| F   | F   | F         | F                  |
Salida igual a F, se demuestra

5. Distributividad:
	$F \land (G \lor H) \equiv (F\land G) \lor (F \land H)$
	$F \lor (G \land H) \equiv (F \lor G) \land (F \lor H)$

| F   | G   | H   | G∨H | Lado izq | F∧G | F∧H | Lado der |
| --- | --- | --- | --- | -------- | --- | --- | -------- |
| V   | V   | V   | V   | V        | V   | V   | V        |
| V   | V   | F   | V   | V        | V   | F   | V        |
| V   | F   | V   | V   | V        | F   | V   | V        |
| V   | F   | F   | F   | F        | F   | F   | F        |
| F   | V   | V   | V   | F        | F   | F   | F        |
| F   | V   | F   | V   | F        | F   | F   | F        |
| F   | F   | V   | V   | F        | F   | F   | F        |
| F   | F   | F   | F   | F        | F   | F   | F        |
Lados iguales, se demuestra

6. Doble negación: 
	$\neg \neg F \equiv F$

| F   | $\neg$ | $\neg$F |
| --- | ------ | ------- |
| V   | V      | F       |
| F   | F      | V       |
Salida igual a F, se demuestra

7. Leyes de De Morgan:
	$\neg (F \land G) \equiv \neg F \lor \neg G$
	$\neg (F\lor G) \equiv \neg F \land \neg G$

| F   | G   | F∧G | ¬(F∧G) | ¬F  | ¬G  | ¬F∨¬G |
| --- | --- | --- | ------ | --- | --- | ----- |
| V   | V   | V   | F      | F   | F   | F     |
| V   | F   | F   | V      | F   | V   | V     |
| F   | V   | F   | V      | V   | F   | V     |
| F   | F   | F   | V      | V   | V   | V     |
Columna 4 y 7 iguales, se demuestra

## 1.13.Demostrar que $F\equiv G$ syss $\models$ $F \leftrightarrow G$
Si F es equivalente a Q, se podría decir que $I(F)=I(G)$
Si $\models F\leftrightarrow G$ significa que es tautología, $F\leftrightarrow G = 1$
Si $I(F)=I(G)=1,\ I(F\leftrightarrow Q)=1$
Si $I(F)=I(G)=0,\ I(F\leftrightarrow Q)=1$
En ambos casos $I(F\leftrightarrow Q)=1$
Es decir, El conector lógico $\leftrightarrow$ es siempre tautología solo si $I(F)=I(G)$
Es una tautología, por lo tanto es cierto el enunciado
## 1.14.Determinar cuáles de las siguientes interpretaciones es modelo del conjunto de fórmulas $S=\{(p\lor q)\land (\neg q \lor r), q\rightarrow r\}$
1. $I_{1}$ tal que $I_{1}(p)=1,\ I_{1}(q)=0,\ I_{1}(r)=1$
**Fórmula 1:**$(p\lor q)\land (\neg q \lor r)$
	$(1 \lor 0)\land (\neg 0 \lor 1)$
	$1 \land 1$
	1
	$I_{1} \models (p\lor q)\land (\neg q \lor r)$
	
**Fórmula 2:** $q\rightarrow r$
	$0\rightarrow 1$
	1 
	$I_{1} \models q\rightarrow r$
$I_{1}$ es modelo de ambas fórmulas

2. $I_{2}$ tal que $I_{2}(p)=0,\ I_{2}(q)=1,\ I_{2}(r)=0$
**Fórmula 1:**$(p\lor q)\land (\neg q \lor r)$
	$(0 \lor 1)\land (\neg 1 \lor 0)$
	$1 \land 0$
	0
	$I_{2} \not\models (p\lor q)\land (\neg q \lor r)$
	
**Fórmula 2:** $q\rightarrow r$
	$1\rightarrow 0$
	0
	$I_{2} \not\models q\rightarrow r$
$I_{2}$ No es modelo de ninguna fórmula

## 1.15.Calcular los modelos de los siguientes conjuntos de fórmulas y decidir cuáles son consistentes
1. $S_{1}=\{(p\lor q)\land(\neg q \lor r),\ p\rightarrow r\}$}
	Caso 1: p = V
	Si p = V, $p\rightarrow r,\ r=V$
	Si ambos son verdaderos, la disyunción con q no afecta al resultado
	Modelo (1, 0, 1); (1, 1, 1)
	
	Caso2: p = F 
	Si p = F, $p\rightarrow r=V$ sin restrincción sobre r
	En la proposición para que de un resultado modelo, q tiene que ser verdadera para que la primera parte $p \lor q$ sea verdadero, q = V
	En la segunda parte, si q es verdadera $(\neg q \lor r)=(\neg V\lor r)=(F \lor r)$, r tiene que ser verdadera
	Modelo (0, 1, 1)
	
	Modelos (p, q, r): (1, 0, 1); (1, 1, 1); (0, 1, 1)

2. $S_{2}=\{(p\lor q)\land(\neg q \lor r),\ p\rightarrow r,\ \neg r\}$
	$\neg r$ fuerza a r = F para que sea satisfacible
	Para que $p\rightarrow r$ sea verdadero con r = F, P tiene que ser falso
	Si p es falso, en $p \lor q$, q tiene que ser verdadero porque deben cumplirse ambas partes de la proposición
	En la segunda parte $(\neg q \lor r)=(\neg V \lor F)=(F \lor F)=F$
	No hay interpretación que satisfaga todo
	
	Modelos (p, q, r): $\varnothing$ 
## 1.16.Decidir cuáles de las siguientes afirmaciones son verdaderas
1. $\{p \rightarrow q,\ q \rightarrow r\} \models p \rightarrow r$
	Por transitividad si hay un modelo I que satisface $p \rightarrow q \land q \rightarrow r$ debe satisfacer $p\rightarrow r$
	Si $I(p)= V,\ I(p\rightarrow q)=V \therefore I(q)=V$
	Con la misma lógica $I(q\rightarrow r)=V$
	Por lo que $I(p\rightarrow r)=V$
	
	Si $I(p)=F \therefore I(p \rightarrow r)= V$
	La afirmación es verdadera, $\{p \rightarrow q,\ q \rightarrow r\} \models p \rightarrow r$

2. $\{p\} \not\models p \land q$
	En las interpretaciones donde p es verdadera, q puede ser verdadera o falsa
	si q es verdadera $p \land q = V$
	si q es falsa $p \land q = F$
	Por lo que la afirmación es verdadera, no todos los modelos de p son modelos de p satisfacen $p \land q$

## 1.17.Demostrar o refutar las siguientes proposiciones
1. Para todo conjunto de fórmula S, $S \models S$
	Pregunta trivial, si existe un $I(S)$ que satisfaga todos los resultados de S, implica que $I(S)=I(S)$
	***Verdadero***
	
2. Para todo conjunto de fórmula $S_{1}$ y toda fórmula F, si $S_{1} \models F$ y $S_{1} \subseteq S_{2}$, entonces $S_{2} \models F$
	$S_{1}\models F$: todo modelo de $S_{1}$ es modelo de F.
	$S_{1}\subseteq S_{2}$​: toda fórmula de $S_{1}$​ está en $S_{2}$​.
	Si $I\models S_{2}$ como $S_{1}\subseteq S_{2}$, $I\models S_{1}$
	Si $S_{1}\models F \therefore S_{2}\models F$
	***Verdadero***
	
3. Para todo conjunto de fórmula $S_{1}$ y todo par de fórmula F, G, si $S \models F$ y $\{F\} \models G$, entonces $S \models G$
	Es la demostración de transitividad, si todo modelo de S es todo modelo de F y todo modelo de F es todo modelo de G
	Entonces existe un $I$ tal que $I\models S,\ I\models F,\ I\models G$
	$S \models G$
	***Verdadero***

## 1.18.Demostrar que las siguientes condiciones son equivalentes
1. $\{F_{1}, \dots, F_{n}\} \models G$
Esto significa: para toda interpretación $I$, si $I\models F_{1}$,…,$I\models F_{n}$​, entonces $I\models G$.
Tiene modelos cuando $\{F_{1}, \dots, F_{n}\}=1, \ I(G)=1$
Cuando $\{F_{1}, \dots, F_{n}\}= 0$ siempre es verdadera
***Verdadero***

2. $\models F_{1} \land \dots \land F_{n} \rightarrow G$
Esto significa que para toda $I$, $I(F_{1} \land \dots \land F_{n} \rightarrow G)=1$
Si $I(F_{1} \land \dots \land F_{n})=1\therefore I(G)=1\rightarrow I(F_{1} \land \dots \land F_{n} \rightarrow G)=1$
Si $I(F_{1} \land \dots \land F_{n})=0$, la afirmación es verdadera.
En todos los casos es verdadera
***Verdadera***

3. $\neg (F_{1} \land \dots \land F_{n} \rightarrow G)$ es insatisfacible
Se demostró que $(F_{1} \land \dots \land F_{n} \rightarrow G)$ es satisfacible, por lo que su negación es insatisfacible
***Verdadera***

4. $(F_{1},\dots, F_{n}, \neg G)$ es inconsistente
$\neg (F_{1} \land \dots \land F_{n} \rightarrow G)\equiv \neg(\neg (F_{1} \land \dots \land F_{n})\lor G)$
$(F_{1} \land \dots \land F_{n} \land \neg G)$  
Si $\neg (F_{1} \land \dots \land F_{n} \rightarrow G)\leftrightarrow \not\exists I: I\models F_{1} \land \dots \land F_{n} \land I \models \neg G$
Es decir,  $(F_{1},\dots, F_{n}, \neg G)$ es inconsistente
***Verdadera***

Todas las condiciones son equivalentes, ya que expresan lo mismo de otras formas
$1\leftrightarrow2\leftrightarrow 3\leftrightarrow 4$

## 1.19.Determinar si los siguientes argumentos son lógicamente correctos.
1. Si el tren llega a las 7 y no hay taxis en la estación, entonces Juan llegará tarde a la reunión. Juan no ha llegado tarde a la reunión. el tren llegó a las 7. Por lo tanto, habían taxis en la estación
	El tren llega a las 7: p
	Hay taxis en la estación: q
	Juan llegará tarde a la reunión: r
	$(p \land \neg q) \rightarrow r$
	$r$
	$\neg r$
	$p$
	$\therefore q$

Por modus tolendo ponens
$[(p \land \neg q)\rightarrow r]\land \neg r$ Arg 1 y arg 3
$p \land \neg q$ Resultado arg 1 y arg 3
$\neg p \lor q$ De Morgan arg 5
$\neg p \lor q, p$ por silogismo disyuntivo si p es verdadera entonces negación de p es falsa, q tiene que ser verdadera
$q$ Argumento lógicamente válido