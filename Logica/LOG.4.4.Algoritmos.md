# 1.Algoritmo Colores
Realizar un algoritmo que determine la conclusión de las siguiente premisa:
1) Los colores primarios son puros
2) El blanco no es un color mas, el negro es la ausencia de la luz
3) El negro es un color muy común
4) Si combino azul y rojo entonces tendré un color, pero si no tendré 2
5) Si combino 3 colores puedo obtener fucsia
6) ¿Qué colores combino para obtenerlo?

```pseudocodigo
Algoritmo colores
	coloresParaFucsia = 3
	Dimensionar Color[coloresParaFucsia] // colores para obtener fucsia
	azul = Verdadero // Se tiene azul
 	rojo = Verdadero // Se tiene rojo
	blanco = Falso // Blanco no es un color
	negro = Verdadero // Negro es un color
	fucsia = Verdadero // fucsia es un color
	
	para combinar <- 0 Hasta 1
		si combinar = 0 Entonces
			cond_combinar = Falso
		FinSi
		
		si combinar = 1 Entonces
			cond_combinar = Verdadero
		FinSi
		
		para i<-1 Hasta coloresParaFucsia Hacer // coloca tos los elementos como nada
			Color[i] = "nada"
		FinPara
		
		si combinar = 0 Entonces // Si combinar es falso se tienen 2 colores, rojo y azul
			Color[1] = "azul"
			Color[2] = "rojo"
			
			para i<-1 hasta coloresParaFucsia Hacer // Si no se tienen 3 colores fucsia es falso
				si Color[i] = "Nada"
					fucsia = Falso
				FinSi
				
			FinPara
			
		SiNo
			// Si combinar es verdadero se tiene la combinación de rojo y azul
			Color[1] = "combinación rojo y azul"
		FinSi
		Escribir "Cuando combinar es ", cond_combinar, " se contiene color 1 ", Color[1], ", color 2 ", Color[2], ", color 3 ", Color[3], " por lo que fucsia es: ", fucsia
	FinPara
FinAlgoritmo
```

# 2.Algoritmo premisas
Generar para premisas P, Q, R, S valores únicos que determinen 
- Ecuación de $2^{do}$ grado
- Polinomio
- Función
- Área

# 3.Algoritmo proposiciones
Para las proposiciones P, Q, R
Realizar:
**1)**
	**Ley de Idempotencia**
	**Ley de Asociatividad**
	**Ley de Complementación**
**2)**
	**Ley de Distribución**
	**Ley de Identidad**
	**Ley de Doble Negación**
**3)**
	**Ley De Morgan**
		La ley proporciona reglas para negar proposiciones
		$\neg (P \land Q \land R)\equiv (\neg P \lor \neg Q \lor \neg R)$
		$\neg (P \lor Q \lor R)\equiv (\neg P \land \neg Q \land \neg R)$
	**Ley de Simplificación**
		Permite simplificar expresiones eliminando una de una conjunción cuando esta es verdadera, esto se debe a que si la proposición es verdadera, sus variables lógicas son iguales, es decir, puede elegirse cualquiera como equivalente
		$P\land Q \land R \equiv P\equiv Q\equiv R$ 
		Si P y Q y R son verdaderas, se puede concluir que P, Q y R individualmente son verdaderas
	**Ley de Adición**
		Permite agregar cualquier variable lógica a una conjunción siempre que una variable sea verdadera, esto es debido a que si una variable es verdadera, la conjunción con cualquier otra es verdad
		$P\equiv P \lor Q \lor R$ 
		Si P es verdadera, la conjunción con cualquier variable, como Q o R no cambia el resultado tautológico de la proposición
**4)**
	**Ley de Inferencia**
	**Ley de Silogismo**
	**Ley de Dilema Constructivo**
**5)**
	**Ley del Dilema Destructivo**
	**Ley de Transposición**
	**Ley de Resolució**n