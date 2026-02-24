---
materia: Programación Java
id: JAV.1.2
tema: Arrays Estáticos, Dinámicos y Complejidad
status: Revision
tags:
  - java
  - arrays
  - arraylist
  - big-o
---

# JAV.1.2. Arrays y Estructuras Lineales

> [!abstract]- Estructuras de Datos Contiguas
> En Java, un Array es un **Objeto**. Esto implica que vive en el Heap y tiene propiedades intrínsecas como `.length`. La elección entre un Array nativo (estático) y un `ArrayList` (dinámico) es una decisión técnica que impacta en la velocidad de acceso y la escalabilidad del sistema.

# 1. Arrays Nativos (Estáticos)

Son bloques de memoria contiguos. Su tamaño es inmutable una vez instanciados.

## 1.1. Memoria y Acceso
```java
int[] vector = new int[5]; // Reserva espacio para 5 enteros en el Heap
```
- **Acceso ($O(1)$):** Acceder a `vector[4]` es instantáneo porque se calcula la dirección física directamente.
- **Multidimensional:** Java maneja "Arrays de Arrays", lo que permite matrices irregulares (Jagged Arrays).

# 2. ArrayList (Array Dinámico)

Es una implementación de la interfaz `List` que encapsula un array nativo y gestiona su crecimiento.

## 2.1. El Algoritmo de Crecimiento
1. Inicia con una capacidad predeterminada (usualmente 10).
2. Cuando se llena, el `ArrayList` crea un nuevo array un 50% más grande.
3. Copia los datos del array viejo al nuevo ($O(n)$).

> [!question]- Optimización Proactiva
> Si vas a procesar 100,000 elementos, el ArrayList se redimensionará muchas veces, desperdiciando ciclos de CPU.
> **Mala práctica**: `List<Integer> list = new ArrayList<>();`
> **Ingeniería**: `List<Integer> list = new ArrayList<>(100000);` (Reserva memoria de una vez).

# 3. Complejidad y Rendimiento (Big O)

| Operación | Array Nativo | ArrayList |
| :--- | :--- | :--- |
| **Lectura por índice** | $O(1)$ | $O(1)$ |
| **Inserción (final)** | N/A | $O(1)$ amortizado |
| **Inserción (inicio)** | N/A | $O(n)$ (Debe desplazar todos los elementos) |



---

## Resumen

- **Arrays**: Úsalos cuando la dimensión de los datos es conocida y fija (ej. buffers de red, matrices matemáticas).
- **ArrayList**: Úsalo para la lógica de negocio general donde el volumen de datos es variable.
- **Localidad**: Los arrays nativos de primitivos tienen mejor localidad de caché que las listas de objetos.

## Bibliografía
1. Bloch, J. (2018). *Effective Java*. Addison-Wesley.
2. Sedgewick, R. (2011). *Algorithms*. Pearson.