
# Metodo de Semantica Logica

## 3.1. Estructura

Lista todas las posibles soluciones. Combinaciones de valores de verdad.

## 3.2. Factores Posibles 

Tiene $n$ variables proposiciones distintas, la tabla tendra $2^N$ filas

## 3.3. Tablas

### 3.3.1. Negacion

Invierte el valor de verdad

| $P$ | $\neg P$ | 
| --- | -        |
| V   | F        |
| F   | V        |

### 3.3.2. Conjuncion

| $P$ | $Q$      | $P \land Q$ |
| --- | -------- | ----------- |
| V   | V        | V           |
| V   | F        | F           |
| F   | V        | F           |
| F   | F        | F           |

### 3.3.3. Disyuncion

| $P$ | $Q$      | $P \lor Q$  |
| --- | -------- | ----------- |
| V   | V        | V           |
| V   | F        | V           |
| V   | F        | V           |
| F   | F        | F           |

### 3.3.4. Condicional

| $P$ | $Q$      | $P \lor Q$  |
| --- | -------- | ----------- |
| V   | V        | V           |
| V   | F        | F           |
| V   | F        | V           |
| F   | F        | V           |


# Ejercicio

a) Si la computadora esta encendida o el monitor conectado entonces el usuario puede trabajar 

b) Si El hardware funciona y esta actualizado no es cierto que el programa no tenga errores

c) El sistema esta operativo y el usuario esta autenticado, entonces la aplicaciones esta disponible entonces el programa esta disponible

$P$: La computadora esta encendida
$Q$: El monitor conectado
$R$: El usuario puede trabajar
$S$: El hardware funciona 
$T$: El hardware esta actualizado 
$U$: El programa tiene errores 
$V$: El sistema esta operativo 
$W$: El usuario esta autenticado
$X$: La aplicacion esta disponible

a) $(P \lor Q) \rightarrow R$


| $P$ | $Q$ | $P \lor Q$ | $R$ | $(P \lor Q) \rightarrow R$ |
| -   | -   | -          | -   | -                          |
| V   | V   | V          | V   | V                          |
| F   | V   | V          | V   | V                          |
| V   | F   | V          | V   | V                          |
| V   | V   | V          | F   | F                          |
| F   | V   | V          | F   | F                          |
| F   | F   | F          | V   |                            |

