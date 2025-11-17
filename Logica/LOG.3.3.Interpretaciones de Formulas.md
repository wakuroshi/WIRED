# 1.Interpretaciones de Fórmulas
Ej: Sea $F=(p\lor q)\land(\neg q\lor R)$
	Valor de F en interpretación $I_{1}$ tal que
	$I_{1}(p)=I_{1}(R)=1. I_{1} (q)=0$
	$(p\lor q)\land(\neg q\lor R)$
	$(1\lor 0)\land(\neg 0\lor 1)$
	$1\land(1\lor 1)$
	1

- Valor de F en una interpretación $I_{2}$ tal que 
	$I_{2}=1,\ I_{2}(p)=I_{2}\ (q)=0$
	$(p\lor q)\land(\neg q\lor R)$
	0 0 0  0  10 1 1

**Proposición:** Sea F una fórmula y $I_{1}$ ; $I_{2}$ dos interpretaciones
	Si $I_{1}(p)=I_{2}(p)$ para todas las variables proposicionales de F entonces $I_{1}(F)=I_{2}F$

# 2.Modelos y Satisfacibilidad
### 2.1.Modelo de una fórmula
$I$ es Modelo $F$ si $I(F)=1$
Notación: $I\models F$

Ej: (Continuación del anterior.)

Si $I_{1}(p)=I_{1}(R)=1,\ I_{1}(q)=0,$ entonces.
$I \models(p\lor q)\land(\neg q\lor R)$
Si $I_{2} (R)=1, \ I_{2} (q)=0, entonces$
$I_{2}\not\models (p\lor q)\land(\neg q\lor R)$

### 2.2.Fórmulas Satisfacibles e Insatisfacibles
F es satisfacible si F tiene algún modelo
Ej: $(p\rightarrow q)\land (q\rightarrow R)$ es satisfacible
$I(p)=I(q)=I(R)=0$
F es Insatisfacible si F no tiene ningún modelo
Ej: $p\land \neg p$ es Insatisfacible

| P   | $\neg P$ | $p\land \neg p$ |
| --- | -------- | --------------- |
| 1   | 0        | 0               |
| 0   | 1        | 0               |

# 3.Tautología y Contradicciones
- F es una tautología (o válida) si toda la interpretación es modelo de F. Si representa $\models F$
- F es una contradicción si ninguna interpretación es modelo de F
- F es contingente si no es tautología ni contradicción

1) $(p\rightarrow q)\lor(q\rightarrow p)$ es tautología
2) $(p\rightarrow q)\land \neg(p\rightarrow q)$ es contradicción
3) $p\rightarrow q$ es contingente

| p   | q   | $p\rightarrow q\ \ (q\rightarrow p)$ | $(p\rightarrow q)\lor(q\rightarrow p)$ | $\neg(p\rightarrow q)$ | $(p\rightarrow q)\land \neg(p\rightarrow q)$ |
| --- | --- | ------------------------------------ | -------------------------------------- | ---------------------- | -------------------------------------------- |
| 1   | 1   | 1                 1                  | 1                                      | 0                      | 0                                            |
| 1   | 0   | 0                1                   | 1                                      | 1                      | 0                                            |
| 0   | 1   | 1                 0                  | 1                                      | 0                      | 0                                            |
| 0   | 0   | 1                 1                  | 1                                      | 0                      | 0                                            |
