---
tags:
  - Logica
---
# 1.Definición
Las pruebas formales son secuencias de sentencias donde cada paso es un axioma que se derivan de las fases anteriores usando las reglas de inferencia, demostrando que una conclusión es necesariamente verdadera si las premisas lo son
# 2.Componentes de las Pruebas Formales
![[LOG.4.1.fa.png]]
## 2.1.Axiomas
Sentencias que se aceptan como verdaderas al inicio de una demostración, sin necesidad de una prueba
## 2.2.Reglas de Inferencia
Regla de reducción que permite derivar nuevas sentencias a partir de la que ya existe
## 2.3.Secuencia de Sentencias
Una prueba es una lista finita de sentencias que culmina en una conclusión deseada, donde cada línea es bien o un axioma o bien un resultado para aplicar una regla de inferencia a las líneas anteriores

# 3.Propósito y Validez
![[LOG.4.1.fb.png]]
## 3.1.Demostrar la Validez
Es el objetivo de demostrar formalmente un argumento que es válido, es decir, si las premisas son verdaderas la conclusión necesariamente tiene que ser verdadera
## 3.2.Independencia del contenido
La prueba se enfoca en la estructura formal del razonamiento, no en el significado de las proposiciones involucradas
## 3.3.Simbolismo y Estructura
La lógica simbólica utiliza los símbolos para representar las proposiciones y las relaciones lógicas, permitiendo un análisis sistemático y riguroso de la inferencia

# 4.Ejercicio
Premisa 1: P; Premisa 2: $P\rightarrow Q$; Conclusión: Q
==Gabriel canta== (P), ==pero== ($\land$) ==no baila== (Q)
**Formalizar:** $\neg(P \land Q)$
$\equiv \neg P \lor \neg Q$
$\equiv \neg Q \land \neg P$
Gabriel o Baila
No canta
**Resp:** Gabriel no canta o baila
# 5.Tabla de Conectores

| El negador                                                                 | El Conjuntor                                              | El Disyuntor debil                 | Disyuntor Fuerte                                     | Condicional Directo                                                                                         | Condiconal Inverso                                                    | El Bicondicional                                                                                       |
| -------------------------------------------------------------------------- | --------------------------------------------------------- | ---------------------------------- | ---------------------------------------------------- | ----------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------ |
| (~, $\neg)$                                                                | $(\land)$                                                 | ($\lor$)                           | $(\Delta, \not\leftrightarrow )$                     | $(\rightarrow)$                                                                                             | $(\leftarrow)$                                                        | $(\leftrightarrow)$                                                                                    |
| No, jamás, no es cierto que, es mentira que, no es falso que, es falso que | Y, así como, tanto como, también, pero, así mismo, además | O, salvo que, o si no, excepto que | O *palabra* o, salvo que solo, a menos que solamente | Si entonces, por consiguiente, de ahí que, por lo tanto, en consecuencia, luego, en conclusión, siempre qué | Puesto que, ya que, si, dado que, para, cada vez que, solo si, cuando | Cuando y solo cuando, entonces y solo entonces, si y solamente sí, por qué y  por qué, es lo mismo que |

# 6.Ejercicio
Jesús trabaja excepto que estudia entonces juega
p: Jesús trabaja
q: Jesús estudia
r: Jesús juega

$p \lor (q \rightarrow r)$

Se determina que la conclusión r es verdadera debido a la proposición
los modelos que se pueden conseguir son:
(q, r)= (1, 1); (0, 1) y en ambos casos es verdadero
si se determina que es verdadero al final depende todo de p, pero siempre es modelo, es decir, puede trabajar o estudiar, por lo que juega o puede no trabajar
modelos: $(p,q\rightarrow r)$ = (1, 1), (0, 1)

$p \land q \equiv q \land p$
$p \lor q \equiv q \lor p$

$\neg ( p \land q) \equiv \neg p \lor \neg q$
$\neg(p \lor q)\equiv \neg p \land \neg q$

$p \Delta q \equiv q \Delta p$
$p\leftrightarrow q\equiv q\leftrightarrow p$

$p \rightarrow q \equiv \neg p \lor q$
$q \rightarrow p \equiv \neg q \rightarrow \neg q$

$\equiv Equidad o Identico$
$\models$ Que lo segundo es verdadero donde lo primero es verdadero. Ej: $A \models B$
$\vdash$ Puede demostrarse que una depende de la otra. Ej: $A \vdash B$
$\uparrow$ Mayor que