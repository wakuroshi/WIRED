# 1.Construcción de Demostraciones Formales
Construir secuencia de pasos que nos lleve de las premisas a la conclusión justificando cada caso con una regla de inferencia.
# 2.Estructura
Cada línea de prueba puede tener:
1) **Número de línea:** Para referencia
2) **Fórmula:** La proposición que se está concluyendo en ese paso.
3) **Justificación:** La regla de inferencia utilizada y los números de línea de las fórmulas a las que se aplicó la regla
# 3.Ejemplo de construcción
**Problema lógico:** Demostrar que la conclusión "R" se sigue lógicamente de las premisas
1) $(P \land G \land Q)\rightarrow R$
2) $P \land G$
3) Q
**Objetivo:** Mostrar: $\{(P \land G \land Q)\rightarrow R, P \land G, Q\} \models R$

| Línea | Fórmula                            | Justificación                                               |
| ----- | ---------------------------------- | ----------------------------------------------------------- |
| 1     | $(P \land G \land Q)\rightarrow R$ | Premisa                                                     |
| 2     | $P \land G$                        | Premisa                                                     |
| 3     | Q                                  | Premisa                                                     |
| 4     | $P \land G \land Q$                | $\land I$ (Introducción a la conjunción de la líneas 1 y 2) |
| 5     | R                                  | MP(Modus Ponens) de las líneas 1 y 4                        |
**Resultado:** Se llegó a la línea 5 por lo tanto, la derivación es exitosa y el argumento es válido
# 3.1.Ejemplo de Regla de Implicación
**Problema lógico:** Demostrar que la conclusión $\neg P$ sigue lógicamente las premisas
1. $P \land G \rightarrow Q$
2. $\neg Q$
**Objetivo:** Mostrar $\{P \land G \rightarrow Q, \neg Q\}\models \neg P$

| Línea | Fórmula                   | Justificación                          |
| ----- | ------------------------- | -------------------------------------- |
| 1     | $P \land G \rightarrow Q$ | Premisa                                |
| 2     | $\neg Q$                  | Premisa                                |
| 3     | $\neg P$                  | MT (Modus Tollens) de las líneas 1 y 2 |
**Resultado:** La prueba formal es corta y concluye $\neg P$ demostrando la validez del argumento.