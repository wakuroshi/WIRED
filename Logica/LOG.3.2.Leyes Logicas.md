# 1.¿Qué son?
Son principios fundamentales que proporcionan equivalencias o implicaciones entre fórmulas lógicas, permitiendo simplificar expresiones, estas definen las propiedades básicas de los conectores lógicas y como herramientas simplifican mucho el análisis de las proposiciones.
# 2.Leyes Lógicas
$$
\begin{align*}
\text{Leyes de Absorción:} & [p \vee (p \wedge q)] \Leftrightarrow p \\
& [p \wedge (p \vee q)] \Leftrightarrow p \\
\\
\text{Leyes de Idempotencia:} & p \vee p \Leftrightarrow p \\
& p \wedge p \Leftrightarrow p \\
\\
\text{Leyes de Asociatividad:} & [p \vee (q \vee r)] \Leftrightarrow [(p \vee q) \vee r] \\
& [p \wedge (q \wedge r)] \Leftrightarrow [(p \wedge q) \wedge r] \\
\\
\text{Leyes de Conmutatividad:} & (p \vee q) \Leftrightarrow (q \vee p) \\
& (p \wedge q) \Leftrightarrow (q \wedge p) \\
& (p \leftrightarrow q) \Leftrightarrow (q \leftrightarrow p) \\
\\
\text{Leyes de Complementación:} & (p \vee \neg p) \Leftrightarrow 1 \quad \text{(Tercio Excluso)} \\
& (p \wedge \neg p) \Leftrightarrow 0 \quad \text{(Contradicción)} \\
\\
\text{Leyes de Distributividad:} & [p \vee (q \wedge r)] \Leftrightarrow [(p \vee q) \wedge (p \vee r)] \\
& [p \wedge (q \vee r)] \Leftrightarrow [(p \wedge q) \vee (p \wedge r)] \\
& [p \rightarrow (q \wedge r)] \Leftrightarrow [(p \rightarrow q) \wedge (p \rightarrow r)] \\
& [p \rightarrow (q \vee r)] \Leftrightarrow [(p \rightarrow q) \vee (p \rightarrow r)] \\
\\
\text{Leyes de Identidad:} & (p \vee 0) \Leftrightarrow p \\
& (p \wedge 1) \Leftrightarrow p \\
& p \Rightarrow p \\
\\
\text{Ley de Doble Negación:} & \neg \neg p \Leftrightarrow p \\
\\
\text{Leyes de De Morgan:} & \neg (p \vee q) \Leftrightarrow \neg p \wedge \neg q \\
& \neg (p \wedge q) \Leftrightarrow \neg p \vee \neg q \\
\\
\text{Leyes de Simplificación:} & (p \wedge q) \Rightarrow p \\
& (p \wedge q) \Rightarrow q \\
&\text{Si la conjunción es verdadera, una de las dos proposiciones también lo es}\\
\\
\text{Leyes de Adición:} & p \Rightarrow (p \vee q) \\
& q \Rightarrow (p \vee q) \\
&\text{Si una proposición es verdadera, su disyunción con cualquier otra también lo es}\\
\\
\text{Ley de Transitividad:} & [(p \rightarrow q) \wedge (q \rightarrow r)] \Rightarrow (p \rightarrow r) \quad \text{(Silogismo Hipotético)} \\
\\
\text{Ley de Exportación e Importación:} & [(p \wedge q) \rightarrow r] \Leftrightarrow [p \rightarrow (q \rightarrow r)] \\
\\
\text{Ley del Modus Ponendo Ponens (MPP):} & [(p \rightarrow q) \wedge p] \Rightarrow q \\
\\
\text{Ley del Modus Tolendo Tolens (MTT):} & [(p \rightarrow q) \wedge \neg q] \Rightarrow \neg p \quad \\
\\
\text{Ley de Resolución:} & [(\neg p \vee q) \wedge (p \vee r)] \Rightarrow (q \vee r) 
\\
\text{Ley del Bicondicional:} & (p \leftrightarrow q) \Leftrightarrow [(p \rightarrow q) \wedge (q \rightarrow p)] \\
\\
\text{Leyes del Condicional:} & (p \rightarrow q) \Leftrightarrow (\neg p \vee q) \quad \text{(Condicional Disyuntivo)} \\
& (p \rightarrow q) \Leftrightarrow \neg (p \wedge \neg q) \quad \text{(Reducción al Absurdo)} \\
\\
\text{Leyes de Transposición:} & (p \rightarrow q) \Leftrightarrow (\neg q \rightarrow \neg p) \\
& (p \leftrightarrow q) \Leftrightarrow (\neg q \leftrightarrow \neg p) \\
\end{align*}
$$

# 3.Ejercicios

### 3.1.Ejercicio 1
En cada una de las siguientes formas proposicionales encontrar equivalentes utilizando conectivos $\land$ y $\neg$, simplificando lo más posible
1) $P \lor Q \lor \neg R$
2) $P \lor [(\neg Q \lor R)\rightarrow P]$
3) $P\rightarrow(Q\rightarrow R)$
### 3.2.Ejercicio 2
Simplificar las siguientes expresiones, escribirlas utilizando los conectivos $\lor$ y $\rightarrow$
1) $(P\land \neg Q)\land \neg P$
2) $P \rightarrow (Q\lor R)\land \neg P\land Q$
3) $\neg P\land \neg Q\land(R\rightarrow P)$
### 3.3.Ejercicio 3
Simplificar las formas proposicionales siguientes
1) $[(P \land Q)\land R]\lor [(P\land Q)\land \neg]\lor[\neg P\land Q]$
2) $[P\rightarrow(Q\lor \neg R)] \land \neg P\land Q$