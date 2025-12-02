---
tags:
  - Logica
---
# 1.Convertir en proposiciones
Crea las proposiciones atómicas y compuestas
Ej: ==El sol es una estrella (p)== pero ==jamás será un planeta (q)==
$p \rightarrow \neg q$

a) $p\leftrightarrow \neg \neg q$
 **Proposiciones Atómicas:** 
    p: La Tierra gira alrededor del Sol. 
    q: Marte es un planeta gaseoso.
**Proposición Compuesta:**
    La Tierra gira alrededor del Sol si y solo si no es verdad que Marte no es un planeta gaseoso.

b) $[(p \lor q) \lor r]\leftrightarrow [p \lor (q \lor r)]$
 **Proposiciones Atómicas:** 
    p: Voy al gimnasio. 
    q: Leo un libro. 
    r: Salgo con amigos.
       
**Proposición Compuesta:**
	 (Voy al gimnasio o leo un libro) o salgo con amigos si y solo si voy al gimnasio o (leo un libro o salgo con amigos).

c) $(p \rightarrow q)\rightarrow 0$
El símbolo 0 (cero) representa una **contradicción** o un valor de **falso** (F). Por lo tanto, la fórmula (p→q)→0 es equivalente a ¬(p→q).
**Proposiciones Atómicas:**
	p: Estudio mucho.   
    q: Apruebo el examen.   
**Proposición Compuesta:**
	 Si (estudio mucho entonces apruebo el examen), entonces esto es falso (o es una contradicción).   
    (Interpretación más natural: No es verdad que si estudio mucho entonces apruebo el examen).

d) $[(p \land q)\lor r]\leftrightarrow p$
**Proposiciones Atómicas:**
	p: Hace frío.   
    q: Está lloviendo.   
    r: Está nevando.   
**Proposición Compuesta:**
    (Hace frío y está lloviendo) o está nevando si y solo si hace frío.
# 2.Proposiciones
Crea proposiciones a partir de las siguientes formulas; diga que tipo de fórmulas son:
p: Estudiar mucho
q: No tener tiempo
r: Salir bien
s: Mantener vida social
t: Tener nota definitiva
u: Estar preocupado

a) $\neg(\neg p \land q)\land r$ (Contingencia)
	$(p \lor \neg q)\land r$ 
	Puedes estudiar mucho o no tener tiempo. Además de salir bien

| $\neg$ | (p  | $\lor$ | $\neg$q) | $\land$ | r   |
| ------ | --- | ------ | -------- | ------- | --- |
| F      | V   | V      | F        | F       | V   |
| F      | V   | V      | F        | F       | F   |
| F      | V   | V      | V        | F       | V   |
| F      | V   | V      | V        | F       | F   |
| V      | F   | F      | F        | V       | V   |
| V      | F   | F      | F        | F       | F   |
| F      | F   | V      | V        | F       | V   |
| F      | F   | V      | V        | F       | F   |


b) $[p \rightarrow (q \land r) \lor \neg s]\leftrightarrow t$ (Contingencia)
	$[\neg p \lor (q\land r)\lor \neg s]\leftrightarrow t$
	$[\neg (p\land s)\lor (q\land r)]\leftrightarrow t$
	No se puede estudiar mucho y mantener vida social o no tener tiempo y salir bien. A juro se tendría una nota definitiva

| \[p | $\rightarrow$     | (q  | $\land$           | r)                | $\lor$            | $\neg$ s\]        | $\leftrightarrow$ | t   |
| --- | ----------------- | --- | ----------------- | ----------------- | ----------------- | ----------------- | ----------------- | --- |
| p   | $\rightarrow$     | (q  | $\land$           | r)                | $\lor$            | $\neg$s           | $\leftrightarrow$ | t   |
| p   | $\rightarrow$     | q   | $\land$           | r                 | $\lor$            | $\neg$s           | $\leftrightarrow$ | t   |
| p   | $\rightarrow$     | q   | r                 | $\lor$            | $\neg$s           | $\leftrightarrow$ | t                 |     |
| p   | $\rightarrow$     | q   | $\lor$            | $\neg$s           | $\leftrightarrow$ | t                 |                   |     |
| p   | $\rightarrow$     | q   | $\lor$            | s                 | $\leftrightarrow$ | t                 |                   |     |
| p   | $\rightarrow$     | q   | s                 | $\leftrightarrow$ | t                 |                   |                   |     |
| p   | $\rightarrow$     | q   | $\leftrightarrow$ | t                 |                   |                   |                   |     |
| p   | $\leftrightarrow$ | t   |                   |                   |                   |                   |                   |     |
| p   |                   |     |                   |                   |                   |                   |                   |     |

c) $\{[(\neg q \lor r)\land s]\lor t\}\rightarrow u$ (Contingencia)
	Lo contrario a no tener tiempo o el salir bien, además de mantener vida social, se puede diferenciar eso de tener nota definitiva, lo que conlleva estar preocupado

| {\[($\neg$q | $\lor$        | r)            | $\land$       | s]            | $\lor$        | t}            | $\rightarrow$ | u   |
| ----------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | --- |
| {\[$\neg$q  | $\lor$        | r             | $\land$       | s]            | $\lor$        | t}            | $\rightarrow$ | u   |
| {\[$\neg$q  | r             | $\land$       | s]            | $\lor$        | t}            | $\rightarrow$ | u             |     |
| {\[$\neg$q  | $\land$       | s]            | $\lor$        | t}            | $\rightarrow$ | u             |               |     |
| {$\neg$q    | $\land$       | s             | $\lor$        | t}            | $\rightarrow$ | u             |               |     |
| {$\neg$q    | s             | $\lor$        | t}            | $\rightarrow$ | u             |               |               |     |
| {$\neg$q    | $\lor$        | t}            | $\rightarrow$ | u             |               |               |               |     |
| $\neg$q     | $\lor$        | t             | $\rightarrow$ | u             |               |               |               |     |
| $\neg$q     | t             | $\rightarrow$ | u             |               |               |               |               |     |
| $\neg$q     | $\rightarrow$ | u             |               |               |               |               |               |     |
| $\neg$q     |               |               |               |               |               |               |               |     |

d) $u \leftrightarrow [(p \lor q) \lor s] \lor t$ (Contingencia)
	Se puede estar preocupado siempre que estudias mucho o no tienes tiempo o mantener vida social. Puede ocurrir eso o se puede tener nota definitiva

| u   | $\leftrightarrow$ | \[(p | $\lor$ | q)     | $\lor$ | s]     | $\lor$ | t   |
| --- | ----------------- | ---- | ------ | ------ | ------ | ------ | ------ | --- |
| u   | $\leftrightarrow$ | \[p  | $\lor$ | q      | $\lor$ | s      | $\lor$ | t   |
| u   | $\leftrightarrow$ | \[p  | q      | $\lor$ | s]     | $\lor$ | t      |     |
| u   | $\leftrightarrow$ | \[p  | $\lor$ | s]     | $\lor$ | t      |        |     |
| u   | $\leftrightarrow$ | p    | $\lor$ | s      | $\lor$ | t      |        |     |
| u   | $\leftrightarrow$ | p    | s      | $\lor$ | t      |        |        |     |
| u   | $\leftrightarrow$ | p    | $\lor$ | t      |        |        |        |     |
| u   | $\leftrightarrow$ | p    | t      |        |        |        |        |     |
| u   | $\leftrightarrow$ | p    |        |        |        |        |        |     |
| u   |                   |      |        |        |        |        |        |     |

e) $\neg t \rightarrow u$ (Contingencia)
	No tener nota definitiva implica estar preocupado

| $\neg$ | t   | $\rightarrow$ | u   |
| ------ | --- | ------------- | --- |
| F      | V   | V             | V   |
| F      | V   | V             | F   |
| V      | F   | V             | V   |
| V      | F   | F             | F   |
# 3.Modelo de la Fórmula
Determinar si las siguientes interpretaciones es modelo de la tabla

$(p \lor q)\land (\neg p \lor r)$
$I_{1}(p)=I_{1}(r)=1;\ I_{1}(q)=0$

$(1 \lor 0)\land (\neg 1 \lor 1)$
$1 \land 1$
$1$
$I_{1}\models (p \lor q)\land (\neg p \lor r)$ $I_{1}$ es modelo de $(p \lor q) \land ( \neg p \lor r)$

$I_{2}(p)=I_{2}(q)=0;\ I_{1}(r)=1$
$(0 \lor 0)\land (\neg 0 \lor 1)$
$0 \land 1$
$0$
$I_{2}\not \models (p \lor q)\land (\neg p \lor r)$ $I_{2}$ no es modelo de $(p \lor q) \land ( \neg p \lor r)$

En cada caso determinar todos los modelos de fórmula proposicional correspondiente
$(p\rightarrow q) \lor (q\rightarrow p)$ 
$I\models (p\rightarrow q) \lor (q\rightarrow p)$

| (p  | $\rightarrow$ | q)  | $\lor$ | (q  | $\rightarrow$ | p)  |
| --- | ------------- | --- | ------ | --- | ------------- | --- |
| 1   | 1             | 1   | 1      | 1   | 1             | 1   |
| 1   | 0             | 0   | 1      | 0   | 1             | 1   |
| 0   | 1             | 1   | 1      | 1   | 0             | 0   |
| 0   | 1             | 0   | 1      | 0   | 1             | 0   |

$(p \rightarrow q)\land \neg(p\rightarrow q)$ Contradicción
$I \not\models (p\rightarrow q) \lor (q\rightarrow p)$

| (p  | $\rightarrow$ | q)  | $\land$ | $\neg$ | (p  | $\rightarrow$ | q   |
| --- | ------------- | --- | ------- | ------ | --- | ------------- | --- |
| 1   | 1             | 1   | 0       | 0      | 1   | 1             | 1   |
| 1   | 0             | 0   | 0       | 1      | 1   | 0             | 0   |
| 0   | 1             | 1   | 0       | 0      | 0   | 1             | 1   |
| 0   | 1             | 0   | 0       | 0      | 0   | 1             | 0   |
