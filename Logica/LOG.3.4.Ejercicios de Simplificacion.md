# 1.Ejercicio 1
Escribe las siguientes expresiones lógicas utilizando los conectivos $\land, \ \lor, \ \neg$ para resolverlos usa tabla de la verdad y/o árboles de formación

a) $p\land q$

| p   | $\land$ | q   |
| --- | ------- | --- |
| V   | V       | V   |
| V   | F       | F   |
| F   | F       | V   |
| F   | F       | F   |

b)$p\downarrow q$
No es una expresión lógica

c)$p\rightarrow q$

| p   | $\rightarrow$ | q   |
| --- | ------------- | --- |
| V   | V             | V   |
| V   | F             | F   |
| F   | V             | V   |
| F   | V             | F   |

d)$p\leftrightarrow q$

| p   | $\leftrightarrow$ | q   |
| --- | ----------------- | --- |
| V   | V                 | V   |
| V   | F                 | F   |
| F   | F                 | V   |
| F   | V                 | F   |

e)$(\neg p \land \neg q)\land (\neg p \land q)$
	$(\neg p \land \neg p) \land ( \neg q \land q)$ Asociativa
	$\neg p \land 0$  Contradicción/Idempotencia
	$0$

f) $(p\rightarrow q)\rightarrow(\neg p\land \neg q)\land (\neg p\land q)\land \neg \neg(p \land q)\leftrightarrow \neg(p\land \neg q)$
	$\{(p\rightarrow q)\rightarrow[(\neg p\land \neg q)\land (p\rightarrow q)\land (p \land q)]\}\leftrightarrow (\neg p\lor q)$ doble negación/condicional disyunción
	$\{(p\rightarrow q)\rightarrow[(\neg p\land \neg q)\land (\neg p \lor q)\land (p \land q)]\}\leftrightarrow (\neg p\lor q)$ condicional disyunción
	$\{(p\rightarrow q)\rightarrow[(\neg p\land \neg q)\land([(p\land q)\land \neg p]\lor[(p\land q)\land q])\}\leftrightarrow (\neg p\lor q)$ Distributiva
	$\{(p\rightarrow q)\rightarrow[(\neg p\land \neg q)\land([(q\land (p\land \neg p)]\lor[p\land (q\land q)])\}\leftrightarrow (\neg p\lor q)$ Asociativa
	$\{(p\rightarrow q)\rightarrow[(\neg p\land \neg q)\land([(q\land 0)]\lor[p\land q)])\}\leftrightarrow (\neg p\lor q)$ Complementación/Identidad
	$\{(p\rightarrow q)\rightarrow[(\neg p\land \neg q)\land(0\lor[p\land q)])\}\leftrightarrow (\neg p\lor q)$ Idempotencia/Identidad
	$\{(p\rightarrow q)\rightarrow[(\neg p\land \neg q)\land(p\land q)]\}\leftrightarrow (\neg p\lor q)$ Identidad
	$\{(p\rightarrow q)\rightarrow[(\neg p\land p) \land( \neg q\land q)]\}\leftrightarrow (\neg p\lor q)$ Asociativa
	$\{(p\rightarrow q)\rightarrow[0 \land0]\}\leftrightarrow (\neg p\lor q)$ Complementación
	$\{(p\rightarrow q)\rightarrow0]\}\leftrightarrow (\neg p\lor q)$ Idempotencia
	$\{\neg(p\rightarrow q)\}\leftrightarrow (\neg p\lor q)$ Equivalencia
	$\{\neg \neg(p\land \neg q)\}\leftrightarrow (\neg p\lor q)$ Condicional disyunción reducción al absurdo
	$\neg(\neg p\lor q)\leftrightarrow (\neg p\lor q)$ De morgan
	0

# 2.Ejercicio 2
Analizar la validez de los siguientes modos 
1) Ningún número impar es divisible por 2
2) Ningún número primo es divisible por 2
3) Algún número primo no es impar

**Modo A**
Término mayor S = Primo (Sujero)
Término menor P = Impar (Predicado)
Término medio M = Divisible entre 2

![[LOG.3.4.fa.png]]
**Modo B**
1) Algunos triángulos son rectángulos
2) Todo triángulo tiene 3 ángulos que suman 180°
3) Algún triángulo cuyos 3 ángulos suman 180° es un triángulo rectángulo

Término mayor S = 180°
Término menor P = Triángulo rectángulo
Término medio M = Triángulo
![[WIRED/Media/LOG.3.4.fb.png]]
**Modo C**
1) Ninguna matriz singular es invertible 
2) Algunas matrices invertibles son triangulares
3) Algunas matrices triangulares no son singulares

Término mayor S = Triangular
Término menor P = Singular
Término medio M = invertible
![[LOG.3.4.fc.png]]