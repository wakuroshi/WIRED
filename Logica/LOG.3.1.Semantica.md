# 0. Prólogo
Ejercicio de clase anterior
Hallar la suma de cifras de M:
**a)** 90
**b)** 45
**c)** 80
**d)** 88

$M= (111\dots111)\cdot(222\dots222)$
	10 cifras          9 cifras

La suma de cifras es multiplicar las cifras $10 \cdot 9=90$

se puede hacer por otro método:
$11\cdot 2=22\ cifras=4$
$111\cdot 22 =2442\ \text{cifras=12}$
$1111\cdot 222 = 246642\ \text{cifras=24}$

# 1. Qué es?
La lógica semántica estudia la relación entre el signo (como una fórmula) y la veracidad.

## 1.1.Valoraciones o valuaciones
Asignación de valores de verdad, verdadero o falso a cada proposición atómica de un sistema lógico 

## 1.2.Tablas de verdad
Clases de tablas de verdad:
	[[LOG.2.4.Tablas de Verdad]]
Herramientas sistemáticas para evaluar si una preposición compuesta es una:
- **Tautología $V\phi=\text{Verdadero}$**
	Una proposición que es verdadera en todas las valoraciones posibles. Su valor siempre es verdadero

- **Contradicción $V_{1}\phi0=\text{Verdadero}; V_{2}\phi=\text{Falso}$**
	Una fórmula es una contradicción si y solo si su valor de verdad es falso bajo todas las valuaciones posibles

- **Contingencia $V_{1}\phi=V\ \ V_{1}\phi=\text{Falso /}\ V_{2}\phi=\text{Falsa}\ \ V_{2}\phi=\text{Verdadera}$**
	Una fórmula es una contingencia si y solo si su valor de verdad depende de la valuación: Es verdadera en al menos una valuación y falsa en al menos una valuación


|      | P   | Q   | Resp |
| ---- | --- | --- | ---- |
| T    | V   | V   | V    |
| C    | F   | F   | V    |
| Cont | V/F | V/F | V    |
## 1.3. Satisfacibilidad e Implicación Semántica
- **Satisfacibilidad:** Una preposición que es verdadera en al menos una valoración, si una proposición no es una contradicción, es satisfacible

- **Implicación semántica:** Se dice que un conjunto de premisas implican semánticamente a una fórmula escrito como:
	![Premisa que implica una fórmula](<LOG.3.1.fa.png>)
	  Si no hay valoración que haga verdadera todas las proposiciones

	- **Demostración de las implicaciones semánticas:** Para demostrar que no existe una valoración que haga verdadero las premisas y falsa la conclusión. 

	- **Relación con la validez del argumento:** Un argumento válido si y solo si existe una implicación semántica entre sus premisas y su conclusión. Es válido si es imposible que todas las premisas sean verdaderas y la conclusión sea falsa, la implicación semántica es por lo tanto la definición semántica de la validez del argumento

### 1.3.1. Ejercicio
**Premisas:**
1) Si escoges tus deseos y tus miedos, no existiría para ti ningún tirano. *Epicteto*
2) Quien tiene un porque para vivir puede soportar cualquiera. *Nietzsche*
3) Cuando uno no tiene imaginación, la muerte es poca cosa, cuando uno la tiene, la muerte es demasiado. *Celine*

- Transforma en proposiciones
	**Primera**
	P: Si escoges tus deseos 
	Q: Si escoges tus miedos
	R: No existirá para ti ningún tirano
	$(P\land Q)\rightarrow R$
	**Segunda**
	S: Quien tiene un porque para vivir 
	T: Soportar cualquiera
	$S\rightarrow T$
	**Tercera**
	$\neg U:$ Cuanto uno no tiene imaginación
	V: La muerte es poca cosa
	W: La muerte es demasiado
	$(\neg U \rightarrow V) \land (U\rightarrow \neg V)$ 

- FBF
- Árbol de formación
- Tabla de verdad


## 1.4. Ejercicios de demostración
Analizar la validez de los siguientes argumentos:
1) Ningún número negativo es natural
	$\mathbb{N}=\{1,2,3,4,\dots\}$
	$\forall N \in\mathbb{N}: (N<0 \rightarrow N\not\in \mathbb{N})$
	Para todo N que pertenece a los naturales, se cumple que: si N es menor que 0, implica que N no pertenece a los naturales

2) Ningún número menor que 0 es natural
	El mismo enunciado que el ejercicio 1.
	$\forall N \in\mathbb{N}: (N<0 \rightarrow N\not\in \mathbb{N})$

3) Ningún número natural es entero
	$\mathbb{N}=\{1,2,3,4,\dots\}$
	$\mathbb{Z}=\{\dots, -3, -2, -1, 0, 1, 2, 3, \dots \}$
	$\nexists \mathbb{N}: (N\in \mathbb{N}\land N \notin \mathbb{Z}$
	No existe número natural tal que N pertenezca a los naturales y N no pertenezca a los enteros
		**Hipotesis:** $(5\in \mathbb{N})\rightarrow(5\not\in \mathbb{Z})$
		- 5 pertenece a los naturales por definición $\mathbb{N}=\{1,2,\dots,5,\dots\}$ por lo que $(5\in \mathbb{N})$ es verdadero (V)
		- 5 pertenece a los enteros por definición $\mathbb{Z}=\{\dots, -2, -1, 0, 1, 2, \dots, 5, \dots\}$ por lo que $(5\not\in \mathbb{Z})$ es falso (F)
		- $P\rightarrow Q$, si P es verdadero y Q es falso la proposición es falsa

4) Ningún número impar es divisible por 2
	$K_{impar}= 2k+1\ \  \lor K_{impar}= 2k-1$
	$K_{par}= 2k$
	$I(x)=$ Número impar
	$D(x)$= Número divisible por 2
	$\forall x\in \mathbb{Z}:(I(x)\rightarrow \neg D(x))$
		Por definición un número par con la fórmula $2k$ es divisible por 2, por lo que un número impar $2k+1 \lor 2k-1$ que no cumple la forma de número par no es divisible por 2. Ningún número puede ser par e impar a la vez, por lo que no es divisible entre 2. Si se estudian las proposiciones, si $I(x)$ es verdadero implica que $\neg D(x)$ es falso , y si el número no es impar $I(x)$ es falso, por lo que $\neg D(x)$ es verdadero.  

5) Algún número primo es divisible por 2
	$P(x):$ Número primo
	$D(x):$ Número divisible por 2
	$\exists N \in \mathbb{N}:(P(x)\land D(x))$
		$P(2)= V$ el número 2 es un número primo, el primo más pequeño
		$D(2)=V$ el número 2 tiene la forma $2k$ ya que $2\cdot 1=2$, por lo que es divisible por 2
		$P(x)\land D(x)$  es una preposición verdadero y verdadero, por lo que el resultado es verdadero.