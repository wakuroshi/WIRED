---
materia: Estructuras Lógicas
id: ESL.2.1
tema: Recursividad y Gestión del Stack
status: Revision
tags:
  - EstructurasLogicas
  - recursividad
  - algoritmos
  - stack
---

# ESL.2.1. Recursividad: El Bucle Infinito Controlado

> [!abstract] Definición
> La recursividad es una técnica donde una función se invoca a sí misma para resolver una instancia más pequeña del problema. Es elegante matemáticamente pero costosa computacionalmente.

---

# 1. Anatomía de la Función Recursiva

Para evitar el desastre (colgar la máquina), toda recursión necesita dos partes obligatorias:

### 1.1. El Caso Base (Base Case)
Es la condición que detiene la recursión. Generalmente es el problema trivial (ej. factorial de 0 es 1, lista vacía, árbol nulo).
- **Sin caso base:** Stack Overflow garantizado.

### 1.2. El Caso Recursivo
Es la llamada a la función misma.
- **Regla de Oro:** El argumento pasado a la llamada recursiva **debe ser diferente** y debe **acercarse** al caso base.

# 2. Gestión de Memoria: El Stack Frame

Cada vez que llamas a una función, el sistema operativo reserva un bloque en la memoria **Stack** (Pila).
- **Contenido del Frame:**
    - Dirección de retorno (dónde volver al terminar).
    - Valor de los parámetros.
    - Variables locales.



### 2.1. El riesgo del Stack Overflow
La memoria Stack es limitada (usualmente 1MB - 8MB). Si tienes una recursión de 100,000 niveles, llenarás la pila y el programa abortará (Segmentation Fault).

# 3. Ejercicio Práctico en C

*Objetivo:* Imprimir una serie de números y luego regresar (efecto rebote).

```c
#include <stdio.h>

void funcionRecursiva(int n) {
    // 1. Caso Base
    if (n <= 0) {
        return;
    }

    // Acción PREVIA (en la ida)
    printf("Ida: %d\n", n);

    // 2. Llamada Recursiva
    funcionRecursiva(n - 1);

    // Acción POSTERIOR (en el regreso/desapilado)
    printf("Vuelta: %d\n", n);
}

int main() {
    funcionRecursiva(3);
    return 0;
}
```
**Salida:**
Ida: 3 -> Ida: 2 -> Ida: 1 -> Vuelta: 1 -> Vuelta: 2 -> Vuelta: 3.

# 4. Recursividad de Cola (Tail Recursion)

Es una optimización. Si la llamada recursiva es *lo último* que hace la función, el compilador puede reutilizar el mismo Stack Frame, convirtiendo la recursión en un bucle `while` internamente. Esto ahorra memoria infinita.

# 5. Comparativa: Recursión vs Iteración

| Característica | Recursividad | Iteración (Bucles) |
| :--- | :--- | :--- |
| **Complejidad Ciclómatica** | Baja (Código simple) | Media |
| **Uso de Memoria** | Alto ($O(n)$ Frames) | Bajo ($O(1)$) |
| **Rendimiento** | Menor (Overhead de llamadas) | Mayor |
| **Uso ideal** | Árboles, Grafos, QuickSort | Listas simples, Contadores |

---

## Resumen Técnico
- La recursividad cambia complejidad de código por consumo de memoria.
- Siempre verifica que tu caso recursivo converja al caso base.
- Para problemas lineales profundos (listas de 1 millón de ítems), prefiere siempre la iteración.

## Bibliografía
- Sedgewick, R. - *Algorithms in C*.
- Joyanes Aguilar, L. - *Fundamentos de Programación*.