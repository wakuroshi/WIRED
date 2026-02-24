---
materia: Estructuras Lógicas
id: ESL.4.1
tema: Árboles, Grafos y Big O
status: Revision
tags:
  - EstructurasLogicas
  - árboles
  - grafos
  - complejidad
  - algoritmos
---

# ESL.4.1. Estructuras No Lineales y Complejidad

> [!abstract] Jerarquías y Redes
> Cuando los datos tienen relaciones jerárquicas (jefe-empleado) o de red (ciudades-carreteras), las listas no sirven. Usamos Árboles y Grafos. Además, aprendemos a medir la eficiencia con Big O.

---

# 1. Árboles Binarios de Búsqueda (BST)

Estructura recursiva donde cada nodo tiene 0, 1 o 2 hijos.
- **Regla Maestra del BST:**
    - Subárbol Izquierdo: Solo valores MENORES al nodo.
    - Subárbol Derecho: Solo valores MAYORES al nodo.

### 1.1. Búsqueda Binaria ($O(\log n)$)
Gracias al orden, en cada paso descartas la mitad de los datos.
- En una lista de 1,000,000 de datos, tardas 1,000,000 de pasos en el peor caso.
- En un BST balanceado, tardas solo **20 pasos**.



# 2. Recorridos (Tree Traversal)

A diferencia de la lista (que solo tiene un orden), el árbol se puede leer de varias formas:
1.  **In-Order (Izq-Raíz-Der):** Imprime los números ordenados de menor a mayor.
2.  **Pre-Order (Raíz-Izq-Der):** Útil para duplicar el árbol.
3.  **Post-Order (Izq-Der-Raíz):** Útil para eliminar el árbol (borras hijos antes que al padre).

# 3. Grafos (Graphs)

La estructura más general. Nodos (Vértices) conectados por líneas (Aristas).
- **Dirigidos (Digraph):** Flechas con sentido (A -> B).
- **Ponderados:** Las conexiones tienen "peso" (costo, distancia).

### 3.1. Representación
- **Matriz de Adyacencia:** Tabla gigante de 1s y 0s. Rápida para consultar conexiones, terrible para memoria.
- **Lista de Adyacencia:** Cada nodo tiene una lista enlazada de sus vecinos. Estándar en la industria.

# 4. Complejidad Algorítmica (Big O Notation)

Es el lenguaje de los ingenieros para discutir rendimiento sin depender del hardware. Describe el **peor escenario**.

| Notación | Nombre | Comportamiento | Ejemplo |
| :--- | :--- | :--- | :--- |
| **$O(1)$** | Constante | Instantáneo | Array[i], Push/Pop |
| **$O(\log n)$** | Logarítmico | Muy rápido | Búsqueda en BST |
| **$O(n)$** | Lineal | Proporcional | Recorrer lista |
| **$O(n^2)$** | Cuadrático | Lento | Bucles anidados (Burbuja) |

### 4.1. Por qué importa
Un algoritmo $O(n^2)$ con 10,000 usuarios tardará minutos. Con 100,000 usuarios tardará días. La escalabilidad depende de elegir el algoritmo con el menor Big O posible.

---

## Resumen Técnico
- Los **Árboles** optimizan la búsqueda.
- Los **Grafos** modelan relaciones complejas.
- **Big O** nos dice si el sistema aguantará cuando tenga millones de usuarios.

## Bibliografía
- Cormen, T. H. - *Introduction to Algorithms*.
- Skiena, S. - *The Algorithm Design Manual*.