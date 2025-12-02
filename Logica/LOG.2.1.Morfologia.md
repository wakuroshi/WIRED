---
tags:
  - Logica
---
# 1. Morfologia
Es la parte de la logica que estudia la **forma y estructura** en como se presentan las proposiciones (Estructuras logicas).

## 1.1. Formulas Bien Formadas (FBF)
Es la forma correcta del lenguaje formal

**Alfabeto**: 

| Tipo de Simbolo           | Simbolo                                | Funcion                                                     |
| ------------------------- | -------------------------------------- | ----------------------------------------------------------- |
| Variables Proposicionales | $P,Q,R,...$                            | Representan la proposion atomica                            |
| Conectivos logicos        | $\neg$, $\land$, $\lor$, $\rightarrow$ | Operadores que unen o modifican a las proposiciones         |
| Simbolos Auxiliares       | (),[],{}                               | Agrupan, desambiguan y establecen enlaces en los conectivos |

> Para mas detalle sobre los conectivos, revisar [LOG.1.Logica](LOG.1.Logica.md)

### 1.1.1. Reglas de Formacion
1) **Regla Base (Formulas Atomicas)**: Cualquier variable proposicional es una formula. $P$: Es una formula
2) **Regla de Negacion (Operador Unario)**: Si $A$ es una formula, entonces $\neg A$ tambien lo es
3) **Reglas Binarias (Operadores Diadicos)**: Si $A$ y $B$ son formulas, entonces ($A\land B$), ($A\lor B$), ($\neg A\land B$) tambien lo son
4) **Clausula de Exclusion**: Esto asegura que solo las expresiones construidas de acuerdo a las reglas son validas

**Ejemplo**
- **No digas** que **no salí** porque **si salí**; se podría expresar como: $\neg(P\rightarrow S)\rightarrow S$

|           Expresion            | FBF | Razon                   |
| :----------------------------: | :-: | :---------------------- |
|           $P \lor Q$           | No  | Rompe la regla 3        |
|       $(\neg P \lor Q$)        | Si  | Cumple todas las reglas |
| $P \rightarrow (\neg \land Q)$ | No  | Rompe la regla 3        |

## 1.2. Convenciones de Escritura
- **Procedencia de los operadores**: Se establecen reglas para el orden en que se evaluan. **Ejemplo**: La negacion $\neg$ suele tener mas procedencia que la conjuncion $()$
- **Notacion Abreviada**: Las convenciones pueden incluir el uso de notaciones simplificadas cuando la procedencia de las operaciones es clara
### 1.2.1. Convenciones para la omision de parentesis
- Jerarquia de los operadores (fuerza de agrupacion):

| Rango | Conectivo               |      Simbolo      | Fuerza de Agrupacion                                                      |
| :---: | ----------------------- | :---------------: | ------------------------------------------------------------------------- |
|  1º   | Negacion                |    $\neg$ y ~     | Mayor (Agrupa solo la variable y la formula inmediata)                    |
|  2º   | Disyuncion y Conjuncion | $\land$ y $\lor$  | Inmediata (Agrupa al mas fuerte $\rightarrow$ y $\leftrightarrow$)        |
|  3º   | Condicional             |   $\rightarrow$   | Menor                                                                     |
|  4º   | Bicondicional           | $\leftrightarrow$ | Minimo (Siempre es el operador principal si esta presente sin parentesis) |

### 1.2.2. Reglas por omision
- **Omision del parentesis externo**: Los que agrupan toda la formula del operador principal se omite siempre. **Ej**: $(p \lor q)$ es igual a $p \lor q$
- **Omision de jerarquias**: Se omiten los parentesis que agrupan un operador mayor de fuerza a uno de menor fuerza. **Ej**: $(p \lor q) \rightarrow r$ Se puede escribir como $p \lor q \rightarrow r$
- **Alcance de la negacion**: La negacion siempre tiene el alcance mas pequeño, solo afecta a la variable o formula inmediata a su derecha. **Ej**: $(\neg P) \lor q \rightarrow r$ Es igual a $\neg p \lor q \rightarrow r$

**Ejercicio**
Si por cada 2 chapitas te dan un refresco regalado. ¿Cuantos refrescos se podrian tomar con 5 chapitas?
a) 2
b) 3
c) 4
d) 5

![LOG.2.1.fa](LOG.2.1.fa.png)

Se tienen 5 chapas, pero cada refrescos tiene 1 chapa, lo que significa que con cada 2 refrescos puedes tener otro refresco más, en el gráfico se observa, se tienen las 4 iniciales (A,B,C,D), luego cada refresco da 1 chapa, por lo que las chapas que te dieron los puntos iniciales se juntan que una chapa que te da otro refresco, es decir, consigues 4 chapas.

Respuesta correcta: **c**
