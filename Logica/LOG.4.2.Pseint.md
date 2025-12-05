# 1.Definición
Pseint es un software educativo para escribir Pseudocódigo y para crear diagramas de flujo en español. Su objetivo es centrarse en los fundamentos de la algoritmia y la lógica de programación, minimizando las dificultades de la sintaxis de un lenguaje real.

## 1.1.Funcionamiento
Se colocan las instrucciones mediante pseudocódigo, el programa lo ejecuta de diferentes formas
- Ejecución normal
- Ejecución paso por paso
- Diagrama de flujo

## 1.2 Ejemplo
Algoritmo para calcular el radio mediante el diámetro
```pseudocodigo
Algoritmo Calculo_radio
	Escribir "Ingrese el diámetro a calcular: "
	Leer  diametro
	// r = radio
	// d = diametro
	// s = resultado
	//
	// r->d/2
	// r->s
	// s->d/2
	
	radio <- diametro/2
	Escribir "El radio es: ",radio
FinAlgoritmo
```

# 2.Ejercicios
Calcular el número de paréntesis de una fórmula bien formada si la fórmula está conformada por:
n número de proposiciones atómicas y n número de proposiciones compuestas siendo los paréntesis la propiedad de realización de la fórmulas bien formadas
$(p\land q)$

**Recursividad**
```pseudocodigo
Funcion resultado <- parentesis(n)
	si n=1 Entonces
		resultado <- 0;
	SiNo
		resultado <- 2+parentesis(n-1);
	FinSi
FinFuncion

Algoritmo parentesis_FBF
	Escribir "Ingrese el número de proposiciones"
	Leer n
	Escribir "El número de paréntesis es: ", parentesis(n)
```
**Sin funciones**
```pseudocodigo
Algoritmo prueba_fbf_sinfuncion
	
	Escribir "Ingrese las proposiciones: "
	leer proposiciones_atom
	n <- proposiciones_atom
	
	Para proposiciones_atom <- 0 Hasta n-1
		si proposiciones_atom <> 0 Entonces
			parentesis= parentesis+2
		FinSi
	FinPara
	
	para proposiciones_atom <- 0 Hasta n-1
		si proposiciones_atom%2 = 0 Y proposiciones_atom<>0 Entonces
			parentesis_sincorchetes=parentesis_sincorchetes+2
		FinSi
	FinPara
	
	Escribir "Los parentesis en crudo: ", parentesis
	Escribir "Los parentesis sin contar corchetes ni llaves: ", parentesis_sincorchetes
FinAlgoritmo
```