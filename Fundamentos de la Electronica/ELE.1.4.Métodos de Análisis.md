---
materia: Fundamentos de la Electrónica
id: ELE.1.4
tema: Métodos de Análisis Sistemático
status: Terminado
tags: [analisis, matrices, sistemas-lineales, LTK]
---

# ELE.1.4. Métodos de Análisis Sistemático

> [!abstract]- Algoritmos de resolución
> KCL y KVL nos dan las leyes, pero aplicarlas al azar en circuitos grandes es caótico. Los métodos de Nodos y Mallas son **algoritmos** que garantizan encontrar la solución con el mínimo número de ecuaciones simultáneas necesarias. Son la base de simuladores como SPICE.

---

# 1. Análisis de Nodos (El método universal)

Este método busca determinar las **tensiones de nodo** (respecto a una referencia o Tierra). Es preferible cuando el circuito tiene muchas fuentes de corriente o circuitos paralelos.

## 1.1. Procedimiento Paso a Paso:

1.  **Seleccionar nodo de referencia**: Se le asigna $V=0$ (Tierra).
2.  **Identificar nodos desconocidos**: Asignar variables $V_1, V_2, ..., V_{n-1}$ a los nodos restantes.
3.  **Aplicar LCK en cada nodo**: Expresar las corrientes en función de las tensiones de nodo usando la Ley de Ohm:
    $$i_{rama} = \frac{V_{origen} - V_{destino}}{R_{rama}}$$
4.  **Resolver el sistema**: Obtendrás un sistema lineal de ecuaciones de la forma $[G][V] = [I]$.

## 1.1. El Supernodo (Caso Especial)

Ocurre cuando hay una **fuente de tensión** (ideal o dependiente) conectada directamente entre dos nodos de no-referencia.
* **Problema**: No podemos escribir $I = V/R$ para la fuente porque $R=0$.
* **Solución**: Tratamos los dos nodos y la fuente como un solo "Supernodo". Aplicamos LCK a todo el bloque y añadimos una ecuación de restricción: $V_a - V_b = V_{fuente}$.

# 2. Análisis de Mallas

Este método busca determinar las **corrientes de malla** (corrientes imaginarias que circulan en lazos cerrados). Solo es aplicable a **circuitos planos**.

### Procedimiento Paso a Paso:
1.  **Identificar mallas**: Asignar corrientes de malla $I_1, I_2, ...$ en sentido horario (convención recomendada).
2.  **Aplicar LTK en cada malla**: Sumar caídas de tensión igual a cero.
    * Si una resistencia es compartida por dos mallas ($I_1$ y $I_2$), la tensión en ella es $R \cdot (I_1 - I_2)$.
3.  **Resolver el sistema**: Obtendrás $[R][I] = [V]$.

### La Supermalla (Caso Especial)
Ocurre cuando hay una **fuente de corriente** en una rama compartida por dos mallas.
* **Problema**: No conocemos la caída de tensión en la fuente de corriente a priori.
* **Solución**: "Abrimos" mentalmente la fuente de corriente para crear un lazo más grande (Supermalla) y aplicamos LTK. Añadimos la ecuación de restricción: $I_{malla1} - I_{malla2} = I_{fuente}$.



# 3. Comparativa para Computación

| Método | Incógnitas | Mejor para... | Equivalente Computacional |
| :--- | :--- | :--- | :--- |
| **Nodos** | $N_{nodos} - 1$ | Fuentes de corriente, paralelo, OP-AMPS | Método preferido en simuladores (SPICE) |
| **Mallas** | $N_{ramas} - (N_{nodos}-1)$ | Fuentes de tensión, serie | Análisis manual rápido en redes simples |

---

## Resumen
* **Nodos** $\rightarrow$ Aplicar LCK y Ohm. Resultado: Tensiones.
* **Mallas** $\rightarrow$ Aplicar LTK y Ohm. Resultado: Corrientes.
* Siempre verifica si hay **fuentes dependientes**: Estas añaden variables extra que deben expresarse en función de las variables de nodo/malla para poder resolver la matriz.

> [!Example] Resolución Matricial
> En ingeniería informática, rara vez resolvemos circuitos de 5 mallas a mano. Planteamos la matriz $A \cdot x = B$ y usamos herramientas numéricas (MATLAB, Python `numpy.linalg.solve`). Entender cómo llenar la matriz es la habilidad clave, no la aritmética.

## Bibliografía
[**Fraile Mora, J.** - *Circuitos Eléctricos*, Cap. 3 y 4]
[**Sedra & Smith** - *Circuitos Microelectrónicos*, Apéndice de Análisis]