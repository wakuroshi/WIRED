# 1. Tablas de la Verdad

Las tablas de la verdad son herramientas logicas que muestran todos los posibles valores de verdad de una proposicion compuesta, basandose en los valores de sus componentes atomicos.

## 1.1. Tablas de Conectivos Fundamentales

### 1.1.1. Negacion ($\neg$)

| $P$ | $\neg P$ |
|-----|----------|
| V   | F        |
| F   | V        |

### 1.1.2. Conjuncion ($\wedge$)

| $P$ | $Q$ | $P \wedge Q$ |
|-----|-----|--------------|
| V   | V   | V            |
| V   | F   | F            |
| F   | V   | F            |
| F   | F   | F            |

### 1.1.3. Disyuncion ($\vee$)

| $P$ | $Q$ | $P \vee Q$ |
|-----|-----|------------|
| V   | V   | V          |
| V   | F   | V          |
| F   | V   | V          |
| F   | F   | F          |

### 1.1.4. Condicional ($\rightarrow$)

| $P$ | $Q$ | $P \rightarrow Q$ |
|-----|-----|-------------------|
| V   | V   | V                 |
| V   | F   | F                 |
| F   | V   | V                 |
| F   | F   | V                 |

### 1.1.5. Bicondicional ($\leftrightarrow$)

| $P$ | $Q$ | $P \leftrightarrow Q$ |
|-----|-----|-----------------------|
| V   | V   | V                     |
| V   | F   | F                     |
| F   | V   | F                     |
| F   | F   | V                     |

## 1.2. Metodo para Construir Tablas Complejas

### 1.2.1. Pasos Generales
1. Identificar todas las variables proposicionales
2. **Calcular el numero de filas**: $2^n$ donde n = numero de variables
3. Listar todas las combinaciones posibles
4. Calcular subformulas paso a paso
5. Determinar el valor final de la formula

### 1.2.2. Ejemplo: $(P \wedge Q) \rightarrow R$

| $P$ | $Q$ | $R$ | $P \wedge Q$ | $(P \wedge Q) \rightarrow R$ |
|-----|-----|-----|--------------|-----------------------------|
| V   | V   | V   | V            | V                           |
| V   | V   | F   | V            | F                           |
| V   | F   | V   | F            | V                           |
| V   | F   | F   | F            | V                           |
| F   | V   | V   | F            | V                           |
| F   | V   | F   | F            | V                           |
| F   | F   | V   | F            | V                           |
| F   | F   | F   | F            | V                           |

# 2. Arboles de Formacion

Los arboles de formacion son representaciones graficas jerarquicas que muestran la estructura sintactica de una Formula Bien Formada (FBF).
## 2.1. Componentes de un Arbol
- **Raiz**: Formula completa
- **Nodos internos**: Conectivos logicos
- **Hojas**: Variables proposicionales
- **Ramas**: Conexiones entre componentes

## 2.2. Reglas de Construccion
### 2.2.1. Pasos para Construir
1. Identificar el conectivo principal
2. Colocar el conectivo principal como raiz
3. Dividir la formula en subformulas inmediatas
4. Repetir el proceso recursivamente hasta llegar a formulas atomicas

### 2.2.2. Ejemplo: $\neg(P \vee Q) \rightarrow R$

![LOG.2.3.fa](LOG.2.3.fa.png)

## 2.3. Relacion con FBF (Formulas Bien Formadas)

Un arbol bien formado garantiza que la formula es sintacticamente correcta:
- Todas las hojas son formulas atomicas
- Cada nodo interno tiene la aridad correcta del conectivo
- No hay ramas vacias o incompletas

