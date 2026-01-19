# 1.Ejercicios 4.2
## 1.1.Ejercicio Cálculo de Radio
### 1.1.1.Algoritmo
Realizar un algoritmo para calcular el radio mediante el diámetro
```d
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
### 1.1.2.Demostración
Si diametro es D, radio es R y resultado es S, demostrar que S es conclusión de d/2
$R \rightarrow \dfrac{d}{2}$
$R\to S$

| Línea | Fórmula                                                    | Justificación                |
| ----- | ---------------------------------------------------------- | ---------------------------- |
| 1     | $R \rightarrow \dfrac{d}{2}$                               | Premisa                      |
| 2     | $R\to S$<br>                                               | Premisa                      |
| 3     | $R\to \dfrac{d}{2} \land r \to S\equiv \dfrac{d}{2} \to S$ | Ley de Transitividad (1 y 2) |
$\dfrac{d}{2}\to S$   |   S es la conclusión de d/2
## 1.2.Ejercicio Número de Paréntesis
### 1.2.1.Algoritmo
Calcular el número de paréntesis de una fórmula bien formada si la fórmula está conformada por:
n número de proposiciones atómicas y n número de proposiciones compuestas siendo los paréntesis la propiedad de realización de la fórmulas bien formadas
$(p\land q)$

**Recursividad**
```d
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
```d
Algoritmo prueba_fbf_sinfuncion
	
	Escribir "Ingrese las proposiciones: "
	leer proposiciones_atom
	n <- proposiciones_atom
	
	Para proposiciones_atom <- 0 Hasta n-1
		si proposiciones_atom != 0 Entonces
			parentesis= parentesis+2
		FinSi
	FinPara
	
	para proposiciones_atom <- 0 Hasta n-1
		si proposiciones_atom%2 = 0 Y proposiciones_atom!=0 Entonces
			parentesis_sincorchetes=parentesis_sincorchetes+2
		FinSi
	FinPara
	
	Escribir "Los parentesis en crudo: ", parentesis
	Escribir "Los parentesis sin contar corchetes ni llaves: ", parentesis_sincorchetes
FinAlgoritmo
```
### 1.2.2.Demostración
Si se tiene una fórmula con n proposiciones calcular el número de paréntesis (p)
**Axiomas:**
- Si n=0, entonces p=0
- Si n=1, entonces p=0
- Si n>1 entonces p%2=0
**Caso base**
$n=0\lor n=1 \rightarrow p=0$
**Demostración**
$p\%2=0 \to P=2k$
$p=p+2$ 

**Ejemplo**
Si se tiene la siguiente fórmula $(((P\land Q)\land R) \rightarrow W)$
$n=4$
$p=p+2$
si n=0 -> p=0
si n=1 -> p=0
si n=2 -> p=0+2=2
si n=3 -> p=2+2=4
si n=4 -> p=4+2=6
**Resultado** p=6
# 2.Ejercicios 4.3
## 2.1.Ejercicio Resultado de Estudiar Gabriel
a) Si Gabriel no estudian entonces será reprobado.
b) Pero si estudia el puede que pase la materia
c) Si la evaluación es a cuaderno abierto, tiene posibilidades de pasar.
d) De no escribir el va a repetir la materia

Determine si Gabriel pasará o no.
1. ¿Gabriel estudió?
2. ¿La evaluación es a cuaderno abierto?
3. ¿Gabriel escribió?
Si se cumple 1 o 2 tiene posibilidades, si se cumple 1 y 2 pasa, pero si no ocurre 3 no pasa
### 2.1.1.Algoritmo
```d
Funcion Certeza_pasar <- Calcular_certeza(Gabriel_Estudia, Cuaderno_abierto, Escribir_Prueba)
	Certeza_pasar= Falso
	si Gabriel_Estudia y Cuaderno_abierto y Escribir_Prueba Entonces
		Certeza_pasar=Verdadero
	FinSi
FinFuncion

Funcion Posibilidad_Pasar <- Calcular_posibilidad(Gabriel_Estudia, Escribir_Prueba)
	Posibilidad_Pasar= Falso
	si Escribir_Prueba y Gabriel_Estudia Entonces
		Posibilidad_Pasar=Verdadero
	FinSi
FinFuncion

Funcion Escribir_tabla(Gabriel_Estudia, Cuaderno_abierto, Escribir_Prueba, Posibilidad_Pasar, Certeza_pasar)
	Si Gabriel_Estudia Entonces; txtE <- "V"; Sino txtE <- "F"; FinSi
	Si Cuaderno_abierto Entonces; txtC <- "V"; Sino txtC <- "F"; FinSi
	Si Escribir_Prueba Entonces; txtP <- "V"; Sino txtP <- "F"; FinSi
	Si Posibilidad_Pasar Entonces; txtPP <- "V"; Sino txtPP <- "F"; FinSi
	si Certeza_pasar Entonces; txtCP <- "V"; SiNo txtCP <- "F"; FinSi

	Escribir "     ", txtE, "      |          ",txtC, "         |     ",txtP, "     |          ", txtPP, "         |         ", txtCP 
FinFuncion

Algoritmo GabrielEstudia
	Definir Gabriel_Estudia, Cuaderno_abierto, Escribir_Prueba Como Logico
	Definir Posibilidad_Pasar, Certeza_pasar Como Logico
	
	Escribir "--------------------------- Diagnóstico de Casos --------------------------------"
	Escribir "  Estudiar  |  Cuaderno abierto  |  Escribe  |  Posiblidad Pasar  |  Certeza Pasar"
	para estudia <- 0 hasta 1
		para cuaderno <- 0 hasta 1
			para escribe <- 0 hasta 1
				Gabriel_Estudia = (estudia=1)
				Cuaderno_abierto = cuaderno=1
				Escribir_Prueba = (escribe=1)
				Posibilidad_Pasar= Calcular_posibilidad(Gabriel_Estudia, Escribir_Prueba)
				Certeza_pasar=Calcular_certeza(Gabriel_Estudia, Cuaderno_abierto, Escribir_Prueba)
				Escribir_tabla(Gabriel_Estudia, Cuaderno_abierto, Escribir_Prueba, Posibilidad_Pasar, Certeza_pasar)
			FinPara
		FinPara
	FinPara

FinAlgoritmo
```
### 2.1.2.Demostración
Se tiene
- E: Gabriel estudia.
- C: Evaluación a cuaderno abierto.
- S: Gabriel escribe la prueba.
- R: Gabriel es reprobado.
- P: Gabriel pasa la materia.
- $\diamond$P: Es probable/posible que Gabriel pase
**Premisas**
- **Premisa A:** $\neg E\to R$ (Si no estudia, reprueba).    
- **Premisa B:** $E\to \diamond P$ (Si estudia, es posible que pase).
- **Premisa C:** $C\to \diamond P$ (Si es a cuaderno abierto, tiene posibilidades).
- **Premisa D:** $\neg S \to R$ (Si no escribe, reprueba).

| **Línea** | **Fórmula**                 | **Justificación**                             |
| --------- | --------------------------- | --------------------------------------------- |
| 1         | $\neg E \rightarrow R$      | Premisa                                       |
| 2         | $E \rightarrow \diamond P$  | Premisa                                       |
| 3         | $C \rightarrow \diamond P$  | Premisa                                       |
| 4         | $\neg S \rightarrow R$      | Premisa                                       |
| 5         | $E$                         | Premisa (Suposición: Gabriel estudia)         |
| 6         | $S$                         | Premisa (Suposición: Gabriel escribe)         |
| 7         | $C$                         | Premisa (Suposición: Es cuaderno abierto)     |
| 8         | $\lozenge P$                | **MP** (Modus Ponens) entre 2 y 5             |
| 9         | $\lozenge P$                | **MP** (Modus Ponens) entre 3 y 7             |
| 10        | $(\neg E \lor \neg S)\to R$ | Ley de Disyunción de antecedentes entre 1 y 4 |
Se puede tener diversos cálculos según valores lógicos que tomen las variables proposicionales, el comportamiento general es, si no estudia o escribe entonces reprueban, tanto que no escriba como que no estudie implica que reprueba.
## 2.2.Ejercicio Cálculo de Funciones con Números Reales/Irracionales
a) Con números reales puedo hacer ecuaciones
b) Con números irracionales puedo hacer teoremas
c) Con letras puedo hacer funciones
d) Con todos los anteriores puedo resolver un problema
e) Pero no puedo resolver números imaginarios si asigno las mismas letras a los números
### 2.2.1.Algoritmo
```d
Algoritmo Prueba_numeros
	Numeros_reales_ecuaciones = Verdadero // Con números reales puedo hacer ecuaciones
	Numeros_irracionales_teoremas = Verdadero // Con números irracionales puedo hacer teoremas
	Letras_funciones = Verdadero // Con letras puedo hacer funciones
	resolver_numeros_imaginarios = Falso // No puedo resolver números imaginarios si asigno las mismas letras a los números
	
	si Numeros_reales_ecuaciones y Numeros_irracionales_teoremas y Letras_funciones = Verdadero Entonces // Con todos los anteriores puedo resolver un problema
		resolver_problemas = Verdadero
	SiNo
		resolver_problemas = Falso
	FinSi
	
	
	Escribir "Con números reales se puede hacer ecuaciones es ", Numeros_reales_ecuaciones
	Escribir "Con números irracionales se puede hacer teoremas es ", Numeros_irracionales_teoremas
	Escribir "Con letras se puede hacer funciones es ", Letras_funciones
	
	si resolver_problemas = Falso
		Escribir "Contiene alguna contradicción"
	SiNo
		Escribir "Si se cumple, tautología"
	FinSi
	
	Escribir ""
	Escribir "No poder resolver números imaginarios si se asignan las mismas letras a los números ", resolver_numeros_imaginarios
	si resolver_numeros_imaginarios = Falso
		Escribir "No se puede resolver números imaginarios si asigno las mismas letras a los números, tautología, no se resuelve un número"
	SiNo
		Escribir "Si se cumple de alguna forma rara"
	FinSi
FinAlgoritmo
```
### 2.2.2.Demostración
R: Números reales
E: Ecuaciones
I: Números irracionales
T: Teoremas
L: Letras
F: Funciones
P: Problemas
K(x): Resolver
**Demostración**
$R\to E$ Verdadero, si se tiene una función 3x=9 se tienen número reales y se puede resolver
$I\to T$ 
$L\to F$
$([R\to E] \land [I\to T] \land [L \to F]) \to P$
$\neg K(I)\to (L\to R)$

- R: Uso números reales.
- E: Hago ecuaciones.
- I: Uso números irracionales.
- T: Hago teoremas.
- L: Uso letras.
- F: Hago funciones.
- P: Resuelvo un problema.
- M: Resuelvo números imaginarios.
**Premisas**
- Si uso reales, hago ecuaciones $(R\to E)$
- Si uso irracionales, hago teoremas $(I\to T)$
- Si uso letras, hago funciones $(L \to F)$
- Si hago ecuaciones, teoremas y funciones, resuelvo el problema $((E\land T\land F)\to P)$
- R
- I
- L
**Objetivo:** $\{R\to E,I\to T,L\to F,(E\land T\land F)\to P,R,I,L\}\models P$

| Linea | Fórmula                      | Justificación                      |
| ----- | ---------------------------- | ---------------------------------- |
| 1     | $(R\to E)$                   | Premisa                            |
| 2     | $(I \to T)$                  | Premisa                            |
| 3     | $(L \to F)$                  | Premisa                            |
| 4     | $((E \land T \land F)\to P)$ | Premisa                            |
| 5     | R                            | Premisa                            |
| 6     | I                            | Premisa                            |
| 7     | L                            | Premisa                            |
| 8     | E                            | MPP 1 y 5                          |
| 9     | T                            | MPP 2 y 6                          |
| 10    | F                            | MPP 3 y 7                          |
| 11    | $E \land T \land F$          | $\land$ Conjunción entre 8, 9 y 10 |
| 12    | P                            | MPP 4 y 11                         |
Se demuestra que se pueden resolver problemas
# 3.Ejercicios 4.4
## 3.1.Algoritmo Combinar Colores
Realizar un algoritmo que determine la conclusión de las siguiente premisa:
1) Los colores primarios son puros
2) El blanco no es un color mas, el negro es la ausencia de la luz
3) El negro es un color muy común
4) Si combino azul y rojo entonces tendré un color, pero si no tendré 2
5) Si combino 3 colores puedo obtener fucsia
6) ¿Qué colores combino para obtenerlo?
### 3.1.1.Algoritmo
```d
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

### 3.1.2.Demostración
CP: colores primarios
P: Puros
B: Blanco
N: Negro
A: Azul
R: Rojo
C: Combinar
F: Fucsia

**Premisas**
$CP \to P$
$\neg B$
$C_{3}\to F$


| Línea | Fórmula               | Justificación       |
| ----- | --------------------- | ------------------- |
| 1     | $C_{3} \to F$         | Premisa             |
| 2     | A                     | Premisa             |
| 3     | R                     | Premisa             |
| 4     | $A \land R \to C_{2}$ | 2 y 3               |
| 5     | $\neg C_{3}$          | 4 no existe $C_{3}$ |
| 6     | $\neg F$              | MTT 1 y 5           |

## 3.2.Algoritmo Premisas
Generar para premisas P, Q, R, S valores únicos que determinen 
- Ecuación de $2^{do}$ grado
- Polinomio
- Función
- Área
### 3.2.1.Demostración
P: 2
Q: 1
R: 1
S: 2

**Ecuación de 2do grado**
$Q(x)=Px²+Qx+Rx+S$
$Q(x)=2x²+2x+2$

**Polinomio**
$P(x)=Px^3 + Qx^2 + Rx + S$ 
$P(x)=2x^3 + 1x^2 + 1x + 2$

**Función**
$f(x)=P(x)$
$f(x)=2x^3 + x^2 + x + 2$

**Área**
$\int f(x)$

$A=\int(2x^3 + x^2 + x + 2)dx$
$A=\int2x^3 dx + \int x^2 \, dx + \int x \, dx + \int  \, 2dx$
$A= \dfrac{x⁴}{2}+\dfrac{x^3}{3} + \dfrac{x^2}{2}+2x$
$A= \dfrac{{12x + 3x^4 + 2x^3 + 3x^2}}{6}$

