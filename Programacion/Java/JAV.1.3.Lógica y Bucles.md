---
materia: Programación Java
id: JAV.1.3
tema: Control de Flujo y Eficiencia de Bucles
status: Revision
tags:
  - java
  - algoritmos
  - control-flow
  - loops
---

# JAV.1.3. Lógica Algorítmica y Control

> [!abstract]- El flujo de ejecución del procesador
> Las estructuras de control determinan el orden en que las instrucciones llegan a la unidad aritmética lógica (ALU). En ingeniería, buscamos reducir la **complejidad ciclomática** y optimizar la evaluación de condiciones para evitar desperdicio de ciclos de reloj.

# 1. Condicionales y Cortocircuito

Java utiliza **Evaluación de Cortocircuito** para los operadores `&&` (AND) y `||` (OR).

- **Principio**: Si el primer operando de un `&&` es `false`, el segundo no se evalúa (el resultado será `false` de todos modos).
- **Impacto**: Esto se usa para evitar errores de puntero nulo:
  ```java
  if (obj != null && obj.getValor() > 10) { ... } 
  // Si obj es null, obj.getValor() nunca se ejecuta, evitando el crash.
  ```

# 2. Bucles y Complejidad Temporal

## 2.1. For-Each vs For Tradicional
- **For-Each**: `for(Tipo e : coleccion)` es más limpio y evita errores de "off-by-one" (índice fuera de rango).
- **For Tradicional**: Necesario cuando se requiere el índice `i` para modificar el array o recorrerlo en pasos distintos a 1.

## 2.2. El Peligro del Anidamiento ($O(n^2)$)
Un bucle dentro de otro sobre la misma colección escala de forma cuadrática. Para 1,000 elementos, realizas 1,000,000 de operaciones.
**Solución**: Usar estructuras de datos como `HashMap` para convertir búsquedas $O(n)$ en $O(1)$.

# 3. Métodos de Búsqueda Fundamental

## 3.1. Búsqueda Lineal
- **Uso**: Datos desordenados.
- **Eficiencia**: $O(n)$.

## 3.2. Búsqueda Binaria
- **Requisito**: Los datos **deben** estar ordenados previamente (`Arrays.sort()`).
- **Eficiencia**: $O(\log n)$.
- **Ejemplo**: En un array de 1 millón de datos, la búsqueda binaria solo requiere ~20 comparaciones, contra el millón de la búsqueda lineal.



---

## Resumen

- **Lógica**: Coloca siempre la condición más probable de fallar primero en un `&&` para aprovechar el cortocircuito.
- **Rendimiento**: Evita bucles anidados siempre que sea posible; busca alternativas con mapas o sets.
- **Standard**: Prefiere `Arrays.binarySearch()` y `Arrays.sort()` antes que implementar versiones propias, ya que están altamente optimizadas.

## Bibliografía
1. McConnell, S. (2004). *Code Complete*. Microsoft Press.
2. Knuth, D. (1997). *The Art of Computer Programming*.