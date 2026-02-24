---
materia: Programación Java
id: JAV.3.1
tema: Java Collections Framework y Complejidad Algorítmica
status: Revision
tags:
  - java
  - collections
  - list
  - set
  - big-o
---

# JAV.3.1. Java Collections Framework

> [!abstract]- La eficiencia como prioridad en el manejo de datos
> El Java Collections Framework (JCF) es un conjunto de interfaces y clases que permiten manipular grupos de objetos de forma eficiente. Para un ingeniero, la elección entre una colección u otra no es estética, sino una decisión basada en la **Complejidad Temporal ($O$)** y el consumo de memoria del algoritmo.

# 1. Jerarquía de la Interfaz `Collection`

Casi todas las colecciones (excepto los Mapas) heredan de la raíz `java.util.Collection`.

1.  **List (Listas):** Secuencias ordenadas que admiten duplicados.
2.  **Set (Conjuntos):** No admiten elementos duplicados (Abstracción matemática).
3.  **Queue (Colas):** Diseñadas para procesar elementos en un orden específico (FIFO, LIFO).



# 2. Análisis Técnico de Listas

Basándonos en tus notas de TAD, profundicemos en las operaciones de `ArrayList` vs `LinkedList`.

## 2.1. Operaciones de Adición y Acceso
- **add(elemento):** Inserta al final. En `ArrayList` es $O(1)$ amortizado; en `LinkedList` es $O(1)$.
- **add(índice, elemento):** Inserta en posición específica. Desplaza los elementos posteriores. Complejidad $O(n)$.
- **get(índice):** Acceso directo. En `ArrayList` es $O(1)$; en `LinkedList` es $O(n)$ (debe iterar).

## 2.2. ¿Cuándo elegir cuál?
```java
// Preferir ArrayList para búsquedas frecuentes
List<String> listaTareas = new ArrayList<>(); 

// Preferir LinkedList para inserciones/eliminaciones constantes al inicio
List<String> listaProcesos = new LinkedList<>(); 
```

# 3. Conjuntos (Set) y la Magia del Hashing

El `HashSet` utiliza el `hashCode()` de los objetos para encontrarlos casi instantáneamente.

- **Rendimiento:** Las operaciones `add`, `remove` y `contains` son $O(1)$ en promedio.
- **Caso de uso:** Eliminación de duplicados en datasets masivos donde el orden no es prioritario.

> [!question]- Ejercicio de Rendimiento
> Tienes una lista de 1,000,000 de correos y quieres saber si "user@example.com" ya existe.
> - **ArrayList**: `contains()` tardará $O(n)$ (hasta 1 millón de comparaciones).
> - **HashSet**: `contains()` tardará $O(1)$ (1 sola comparación mediante hash).
> **Conclusión**: El uso de Sets es vital para la escalabilidad de sistemas backend.

---

## Resumen

- **Criterio de Selección:** Si la prioridad es la lectura, usa `ArrayList`. Si la prioridad es la integridad sin duplicados, usa `HashSet`.
- **Interface Segregation:** Siempre declara tus colecciones usando la interfaz: `List<T> lista = new ArrayList<>();`. Esto facilita cambiar la implementación sin romper el código.
- **Complejidad:** Ignorar el costo $O(n)$ de las listas en bucles anidados es la causa #1 de cuellos de botella en Java.

## Bibliografía
1. Bloch, J. (2018). *Effective Java*. (Capítulo: Generics and Collections).
2. Oracle. (2024). *The Java Tutorials: Collections Framework*.