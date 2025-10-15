# ¿Qué es?
Estudio de la **"Forma"**
Estructura de las expresiones lógicas

- Fórmulas Bien Formadas (FBF)
Forma correcta del lenguaje formal

**Alfabeto:**

| Tipo de Símbolo           | Símbolo                                       | Función                                                    |
| ------------------------- | --------------------------------------------- | ---------------------------------------------------------- |
| Variables Proposicionales | P, q, R, ...                                  | Representan la proposición (atómicas)                      |
| Conectivos lógicos        | $\neg,\land,\lor,\rightarrow,\leftrightarrow$ | Operadores que unen o modifican las proposiciones          |
| Símbolos Auxiliares       | (),[],{}                                      | Agrupan, desambiguan y establecen enlaces en los conetivos |
# Reglas de Formación
**1) Regla Base. (Fórmulas atómicas)**
	Cualquier variable proposicional es una fórmula. P: Es una fórmula

**2) Regla de Negación (Operador Unario).**
	Si A es una fórmula, $\neg A$ también lo es.

**3) Reglas Binarias (Operadores Diádicos)**
	Si A y B son fórmulas, entonces ($A\land B$), ($A\lor B$), ($\neg A\land B$) también.

**4) Clausula de Exclusión (Nada más es una fórmula)**
	Esto asegura que solo las expresiones construidas de acuerdo a las reglas son válidas.

**Ejemplos:**
- **No digas** que **no salí** porque **si salí**; se podría expresar como: $\neg(P\rightarrow S)\rightarrow S$
- Di que no saliste si y solo sí saliste; se podría expresar como: $P\leftrightarrow S$
# Ejemplos de Construcción

| Expresión                    | FBF | Razón (Aplicación de Reglas)                       |
| ---------------------------- | --- | -------------------------------------------------- |
| $P\land Q$                   | NO  | Paréntesis envolventes                             |
| $(\neg P\lor Q)$             | SI  | Se unen por $\lor$, se encapsula (Cumple 3 reglas) |
| $P\rightarrow(\neg \land Q)$ | NO  | Operador Unario, no puede ir solo sin un conectivo |
# Convenciones de Escritura
- **Procedencia de los Operadores:** Se establecen reglas para el orden en que se evaluó los operadores. Ejemplo: La negación suele tener mayor procedencia que la conjunción y que la disyunción, esto permite simplificar la fórmula.
- **Notación Abreviada:** Las convenciones pueden incluir el uso de notaciones simplificadas cuando la procedencia de las operaciones es clara.
	- **Convenciones para la Omisión del Paréntesis**
		**a) Jerarquía de los Operadores (Fuerza de Agrupación):** El orden de procedencia

| Rango | Conectivo             | Símbolo           | Fuerza de Agrupación                                            |
|:----- |:--------------------- |:----------------- |:--------------------------------------------------------------- |
| 1°    | Negación              | $\neg$            | Mayor (Solo la variable y la fórmula inmediata)                 |
| 2°    | Disyunción/Conjunción | $\land,\lor$      | Inmediata (Agrupa al más fuerte $\rightarrow, \leftrightarrow$) |
| 3°    | Condicional           | $\rightarrow$     | Menor                                                           |
| 4°    | Bicondicional         | $\leftrightarrow$ | Mínima (Sin paréntesis)                                         |
		$\neg P Q\land R \leftrightarrow (\neg P\land Q)\rightarrow R$ Mal hecho, faltan paréntesis y operadores.
		$\neg P\rightarrow (Q\land R) \leftrightarrow (\neg P\land Q)\rightarrow R$ Mal hecho, no puede estar un condicional con una negación.
		**b) Regla por omisión:** Omisión del paréntesis externo, los que agrupan todas las fórmulas del operador principal se omiten siempre. **Ejemplos:** $((P\lor Q)\rightarrow R)$ no se debería colocar los paréntesis exteriores.
		**c) Omisión de Jerarquía:** Se omiten los paréntesis que agrupan un operador mayor de fuerza a uno de menor fuerza. **Ejemplo:** $(P\lor Q)\rightarrow R$ se puede escribir como $P\lor Q\rightarrow R$
		**d) Alcance de la negación:** La negación siempre tiene el alcance más pequeño, solo afecta a la variable o fórmula inmediata a su derecha. **Ejemplo:** $\neg P\lor Q\rightarrow R$


# Ejercicios
Si por cada 2 chapitas te dan un refresco regalado ¿Cuántos refrescos se podrían tomar con 5 chapitas?
**a)** 2
**b)** 3
**c)** 4
**d)** 5
![[LOG.2.1.fa.png]]
Se tienen 5 chapas, pero cada refrescos tiene 1 chapa, lo que significa que con cada 2 refrescos puedes tener otro refresco más, en el gráfico se observa, se tienen las 4 iniciales (A,B,C,D), luego cada refresco da 1 chapa, por lo que las chapas que te dieron los puntos iniciales se juntan que una chapa que te da otro refresco, es decir, consigues 4 chapas.

Respuesta correcta: **c**