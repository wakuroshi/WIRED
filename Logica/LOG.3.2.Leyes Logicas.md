# 1.¿Qué son?
Son principios fundamentales que proporcionan equivalencias o implicaciones entre fórmulas lógicas, permitiendo simplificar expresiones, estas definen las propiedades básicas de los conectores lógicas y como herramientas simplifican mucho el análisis de las proposiciones.
# 2.Leyes Lógicas
$$
\begin{align*}
\text{leyes de absorción:} & [p \vee (p \wedge q)] \leftrightarrow p \\
& [p \wedge (p \vee q)] \leftrightarrow p \\
\\
\text{leyes de idempotencia:} & p \vee p \leftrightarrow p \\
& p \wedge p \leftrightarrow p \\
\\
\text{leyes de asociatividad:} & [p \vee (q \vee r)] \leftrightarrow [(p \vee q) \vee r] \\
& [p \wedge (q \wedge r)] \leftrightarrow [(p \wedge q) \wedge r] \\
\\
\text{leyes de conmutatividad:} & (p \vee q) \leftrightarrow (q \vee p) \\
& (p \wedge q) \leftrightarrow (q \wedge p) \\
& (p \leftrightarrow q) \leftrightarrow (q \leftrightarrow p) \\
\\
\text{leyes de complementación:} & (p \vee \neg p) \leftrightarrow 1 \quad \text{(tercio excluso)} \\
& (p \wedge \neg p) \leftrightarrow 0 \quad \text{(contradicción)} \\
\\
\text{leyes de distributividad:} & [p \vee (q \wedge r)] \leftrightarrow [(p \vee q) \wedge (p \vee r)] \\
& [p \wedge (q \vee r)] \leftrightarrow [(p \wedge q) \vee (p \wedge r)] \\
& [p \rightarrow (q \wedge r)] \leftrightarrow [(p \rightarrow q) \wedge (p \rightarrow r)] \\
& [p \rightarrow (q \vee r)] \leftrightarrow [(p \rightarrow q) \vee (p \rightarrow r)] \\
\\
\text{leyes de identidad:} & (p \vee 0) \leftrightarrow p \\
& (p \wedge 1) \leftrightarrow p \\
& p \rightarrow p \\
\\
\text{ley de doble negación:} & \neg \neg p \leftrightarrow p \\
\\
\text{leyes de de morgan:} & \neg (p \vee q) \leftrightarrow \neg p \wedge \neg q \\
& \neg (p \wedge q) \leftrightarrow \neg p \vee \neg q \\
\\
\text{leyes de simplificación:} & (p \wedge q) \rightarrow p \\
& (p \wedge q) \rightarrow q \\
&\text{si la conjunción es verdadera, una de las dos proposiciones también lo es}\\
\\
\text{leyes de adición:} & p \rightarrow (p \vee q) \\
& q \rightarrow (p \vee q) \\
&\text{si una proposición es verdadera, su disyunción con cualquier otra también lo es}\\
\\
\text{ley de transitividad:} & [(p \rightarrow q) \wedge (q \rightarrow r)] \rightarrow (p \rightarrow r) \quad \text{(silogismo hipotético)} \\
\\
\text{ley de exportación e importación:} & [(p \wedge q) \rightarrow r] \leftrightarrow [p \rightarrow (q \rightarrow r)] \\
\\
\text{ley del modus ponendo ponens (mpp):} & [(p \rightarrow q) \wedge p] \rightarrow q \\
\\
\text{ley del modus tolendo tolens (mtt):} & [(p \rightarrow q) \wedge \neg q] \rightarrow \neg p \quad \\
\\
\text{ley de resolución:} & [(\neg p \vee q) \wedge (p \vee r)] \rightarrow (q \vee r) 
\\
\text{ley del bicondicional:} & (p \leftrightarrow q) \leftrightarrow [(p \rightarrow q) \wedge (q \rightarrow p)] \\
\\
\text{leyes del condicional:} & (p \rightarrow q) \leftrightarrow (\neg p \vee q) \quad \text{(condicional disyuntivo)} \\
& (p \rightarrow q) \leftrightarrow \neg (p \wedge \neg q) \quad \text{(reducción al absurdo)} \\
\\
\text{leyes de transposición:} & (p \rightarrow q) \leftrightarrow (\neg q \rightarrow \neg p) \\
& (p \leftrightarrow q) \leftrightarrow (\neg q \leftrightarrow \neg p) \\
\end{align*}
$$

# 3.Ejercicios

### 3.1.Ejercicio 1
En cada una de las siguientes formas proposicionales encontrar equivalentes utilizando conectivos $\land$ y $\neg$, simplificando lo más posible
1) $P \lor Q \lor \neg R$
	$\neg \neg(P\lor Q\lor \neg R)$ Doble negación
	$\neg \neg((P\lor Q)\lor \neg R)$ Asociativa
	$\neg(\neg(P\lor Q)\land R)$ De Morgan
	$\neg(\neg P\land \neg Q\land R)$ De Morgan
**Tabla de la Verdad**

| $\neg$ | ($\neg$ | P   | $\land$ | $\neg$ | Q   | $\land$ | R)  |
| ------ | ------- | --- | ------- | ------ | --- | ------- | --- |
| V      | F       | V   | F       | F      | V   | F       | V   |
| V      | F       | V   | F       | F      | V   | F       | F   |
| V      | F       | V   | F       | V      | F   | F       | V   |
| V      | F       | V   | F       | V      | F   | F       | F   |
| V      | V       | F   | F       | F      | V   | F       | V   |
| V      | V       | F   | F       | F      | V   | F       | F   |
| F      | V       | F   | V       | V      | F   | V       | V   |
| V      | V       | F   | V       | V      | F   | F       | F   |
**Árbol de Formación**

| $\neg$ | ($\neg$ | P   | $\land$ | $\neg$ | Q   | $\land$ | R)  |
| ------ | ------- | --- | ------- | ------ | --- | ------- | --- |
| $\neg$ | $\neg$  | P   | $\land$ | $\neg$ | Q   | $\land$ | R   |
| $\neg$ | $\neg$  | P   | $\land$ | $\neg$ | Q   | R       |     |
| $\neg$ | $\neg$  | P   | $\land$ | $\neg$ | Q   |         |     |
| $\neg$ | $\neg$  | P   | $\neg$  | Q      |     |         |     |
| $\neg$ | $\neg$  | P   |         |        |     |         |     |
|        |         | P   |         |        |     |         |     |

2) $P \lor [(\neg Q \lor R)\rightarrow P]$
	 $P \lor [\neg(Q\lor R)\lor P$] Leyes del condicional
	 $(P \lor P)\lor \neg(Q\lor R)$ Asociativa
	 $P\lor \neg (\neg Q\land \neg R)$ Idempotencia/De Morgan
	 $\neg \neg[P \lor \neg(\neg Q \land \neg R)]$ Doble negación
	$\neg(\neg P \land \neg Q \land \neg R)$ De Morgan
**Tabla de la Verdad**

| $\neg$ | ($\neg$ | P   | $\land$ | $\neg$ | Q   | $\land$ | $\neg$ | R   |
| ------ | ------- | --- | ------- | ------ | --- | ------- | ------ | --- |
| V      | F       | V   | F       | F      | V   | F       | F      | V   |
| V      | F       | V   | F       | F      | V   | F       | V      | F   |
| V      | F       | V   | F       | V      | F   | F       | F      | V   |
| V      | F       | V   | F       | V      | F   | V       | V      | F   |
| V      | V       | F   | F       | F      | V   | F       | F      | V   |
| V      | V       | F   | F       | F      | V   | F       | V      | F   |
| V      | V       | F   | F       | V      | F   | F       | F      | V   |
| F      | V       | F   | V       | V      | F   | V       | V      | F   |
**Árbol de Formación**

| $\neg$ | ($\neg$ | P   | $\land$ | $\neg$ | Q   | $\land$ | $\neg$ | R)  |
| ------ | ------- | --- | ------- | ------ | --- | ------- | ------ | --- |
| $\neg$ | $\neg$  | P   | $\land$ | $\neg$ | Q   | $\land$ | $\neg$ | R   |
| $\neg$ | $\neg$  | P   | $\land$ | $\neg$ | Q   | $\land$ | R      |     |
| $\neg$ | $\neg$  | P   | $\land$ | $\neg$ | Q   | R       |        |     |
| $\neg$ | $\neg$  | P   | $\land$ | $\neg$ | Q   |         |        |     |
| $\neg$ | $\neg$  | P   | $\land$ | Q      |     |         |        |     |
| $\neg$ | $\neg$  | P   | Q       |        |     |         |        |     |
| $\neg$ | $\neg$  | P   |         |        |     |         |        |     |
|        |         | P   |         |        |     |         |        |     |

3) $P\rightarrow(Q\rightarrow R)$
	$\neg P \lor (\neg Q\lor R)$ Leyes del condicional
	$\neg \neg[\neg P \lor (\neg Q\lor R)]$ Doble negación
	$\neg[P \land \neg(\neg Q\lor R)]$ De Morgan
	$\neg(P \land  Q\land \neg R)$ De Morgan

**Tabla de la Verdad**

| $\neg$ | (P  | $\land$ | Q   | $\land$ | $\neg$ | R)  |
| ------ | --- | ------- | --- | ------- | ------ | --- |
|        | V   |         | V   |         | F      | V   |
|        | V   |         | V   |         | V      | F   |
|        | V   |         | F   |         | F      | V   |
|        | V   |         | F   |         | V      | F   |
|        | F   |         | V   |         | F      | V   |
|        | F   |         | V   |         | V      | F   |
|        | F   |         | F   |         | F      | V   |
|        | F   |         | F   |         | V      | F   |

**Árbol de Formación**
### 3.2.Ejercicio 2
Simplificar las siguientes expresiones, escribirlas utilizando los conectivos $\lor$ y $\rightarrow$
1) $(P\land \neg Q)\land \neg P$
	$(\neg Q\land P)\land \neg P$ Conmutativa
	$\neg Q \land (P\land \neg P)$ Asociativa
	$\neg Q \land 0$  Complementación
	$0$ Falsa
**Tabla de la Verdad**

| 0   |
| --- |
| F   |
**Árbol de Formación**

| 0   |
| --- |
| 0   |

2) $P \rightarrow (Q\lor R)\land \neg P\land Q$
	$P \rightarrow (Q\lor R)\land (\neg P \land Q)$  Asociativa
	$P \rightarrow \{[(\neg P \land Q)\land Q] \lor [(\neg P \land Q)\land R]\}$ Distributiva
	$P \rightarrow \{[\neg P \land (Q\land Q)] \lor [\neg P \land Q\land R]\}$ Asociativa
	$P \rightarrow \{[\neg P \land Q] \lor [(\neg P \land Q)\land R]\}$ Idempotencia
	$P \rightarrow \{\neg P \land Q\}$ Absorción
	$(P \rightarrow \neg P) \land (P \rightarrow Q)$ Distributiva
	$\neg(P \land \neg P)\land (P \rightarrow Q)$ Condicional disyuntivo
	$\neg 0 \land (P \rightarrow Q)$ Contradicción
	$1 \land (P\rightarrow Q)$ Negación
	$P\rightarrow Q$  Identidad
**Tabla de la Verdad**

| P   | $\rightarrow$ | Q   |
| --- | ------------- | --- |
| V   | V             | V   |
| V   | F             | F   |
| F   | V             | V   |
| F   | V             | F   |
**Árbol de Formación**

| P   | $\rightarrow$ | Q   |
| --- | ------------- | --- |
| P   |               |     |


3) $\neg P\land \neg Q\land(R\rightarrow P)$
	$(\neg P\land \neg Q)\land(R\rightarrow P)$ Asociativa
	$(\neg P\land \neg Q)\land(\neg R\lor P)$ Condicional disyunción
	$[(\neg P\land \neg Q)\land P]\lor [(\neg P \land \neg Q)\land \neg R]$ Condicional disyunción
	$[(\neg P \land P)\land \neg Q]\lor [(\neg P \land \neg Q)\land \neg R]$ Asociativa
	$[0\land \neg Q]\lor [(\neg P \land \neg Q \land \neg R)]$ Contradicción
	$0 \lor [\neg P \land \neg Q \land \neg R]$ Identidad
	$\neg P \land \neg Q \land \neg R$ Identidad
	$\neg \neg[\neg P \land \neg Q \land \neg R]$ Doble negación
	$\neg [P \lor Q \lor R]$ De morgan
	$[P \lor Q \lor R] \rightarrow 0$ La implicación de una proposición con una falsedad es igual a la negación de esa implicación
**Tabla de la Verdad**

| [P  | $\lor$ | Q   | $\lor$ | R]  | $\rightarrow$ | 0   |
| --- | ------ | --- | ------ | --- | ------------- | --- |
| V   | V      | V   | V      | V   | F             | F   |
| V   | V      | V   | V      | F   | F             | F   |
| V   | V      | F   | V      | V   | F             | F   |
| V   | V      | F   | V      | F   | F             | F   |
| F   | V      | V   | V      | V   | F             | F   |
| F   | V      | V   | V      | F   | F             | F   |
| F   | F      | F   | V      | V   | F             | F   |
| F   | F      | F   | F      | F   | V             | F   |
**Árbol de Formación**

| [P  | $\lor$        | Q             | $\lor$        | R]            | $\rightarrow$ | 0   |
| --- | ------------- | ------------- | ------------- | ------------- | ------------- | --- |
| P   | $\lor$        | Q             | $\lor$        | R             | $\rightarrow$ | 0   |
| P   | $\lor$        | Q             | R             | $\rightarrow$ | 0             |     |
| P   | $\lor$        | Q             | $\rightarrow$ | 0             |               |     |
| P   | Q             | $\rightarrow$ | 0             |               |               |     |
| P   | $\rightarrow$ | 0             |               |               |               |     |
| P   |               |               |               |               |               |     |

### 3.3.Ejercicio 3
Simplificar las formas proposicionales siguientes
1) $[(P \land Q)\land R]\lor [(P\land Q)\land \neg]\lor[\neg P\land Q]$
	No tiene sentido lógico, ya que la morfología es incorrecta.

2) $[P\rightarrow(Q\lor \neg R)] \land \neg P\land Q$
	$[\neg P \lor (Q \lor R)]\land \neg P \land Q$ Condicional disyunción
	$([\neg P \lor (Q \lor R)] \land \neg P) \land Q$ Asociativa
	$\neg P \land Q$ Absorción

**Tabla de la Verdad**

| $\neg$ | P   | $\land$ | Q   |
| ------ | --- | ------- | --- |
| F      | V   | F       | V   |
| F      | V   | F       | F   |
| V      | F   | V       | V   |
| V      | F   | F       | F   |
**Árbol de Formación**

| $\neg$ | P   | $\land$ | Q   |
| ------ | --- | ------- | --- |
| $\neg$ | P   | Q       |     |
| $\neg$ | P   |         |     |

