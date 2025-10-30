# 1.¿Qué son?
Los árboles de formación muestran como se construyen una Fórmula Bien Formada (FBF) paso a paso, revelando la jerarquía de los conectores. La raíz (la punta superior) del árbol presenta la fórmula completa y el conector más cercano a la raíz es el conector principal

![Árbol de formación](LOG.2.4.fa.png)
Nos permiten dividir una proposición en distintos módulos que ayudan a visualizar las afirmaciones con mayor peso.
## 2.Identificación de las subfórmulas jerárquicas
La fórmula está dividida por el conector que queda fuera de los paréntesis internos uniendo dos grandes subfórmulas. El conector principal es el que tiene el mayor alcance.
#### 2.1.Árbol de formación simplificado
![Subfórmula de la proposición](LOG.2.4.fb.png)
La conjunción es el conectivo que queda fuera
#### 2.2.Análisis de Propiedad
![Análisis de propiedad con paréntesis FBF](LOG.2.4.fc.png)
#### 2.3.Ejercicio Árbol de formación
[En referencia al ejercicio 3 de la clase 2.2.1](<LOG.2.2.1.Ejercicios Morfologia>)
Siete semanas estudié y siete exámenes rendí. Si hubiese rendido solo tres exámenes, habría podido estudiar con más calma. Si hubiese tenido que rendir nueve exámenes no habría podido estudiar siete semanas. Rendí siete exámenes porque solo de esa manera podría terminar todos mis ramos y si los termino todos, entonces me iré feliz de vacaciones. Estudié siete semanas solo para irme feliz de vacaciones.
A: Siete semanas estudié y siete exámenes rendí.
B: Si hubiese rendido solo tres exámenes, habría podido estudiar con más calma.
C: Si hubiese tenido que rendir nueve exámenes no habría podido estudiar siete semanas.
D: Rendí siete exámenes porque solo de esa manera podría terminar todos mis ramos y si los termino todos, entonces me iré feliz de vacaciones.
E: Estudié siete semanas solo para irme feliz de vacaciones.

P: Estudiar siete semanas 
Q: Rendir siete exámenes
R: Rendí solo tres exámenes
S: Estudiar con más calma
T: Rendir nueve exámenes
U: Terminar todos mis ramos
V: Me iré feliz de vacaciones

$(P\land Q)\land [(R\rightarrow S)\land(T\rightarrow \neg P)]\land [(Q\leftrightarrow U)\land (U\rightarrow V)]\land (P\rightarrow V)$

![Ejercicio Resuelto por Árbol de Formación](LOG.2.4.fd.png)