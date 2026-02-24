---
materia: Programación Java
id: JAV.1.1
tema: Arquitectura de la JVM, Stack vs Heap y Ciclo de Vida del Dato
status: Revision
tags:
  - java
  - jvm
  - memory
  - stack
  - heap
---

# JAV.1.1. Arquitectura de la JVM y Gestión de Memoria

> [!abstract]- La Máquina Virtual y el Costo de la Abstracción
> Java se distingue por ser un lenguaje compilado a **Bytecode** e interpretado/compilado por la **JVM** (Java Virtual Machine). Para un ingeniero, entender Java implica comprender cómo esta máquina virtual gestiona la memoria RAM. Un mal manejo de estas áreas (Stack y Heap) es la causa principal de problemas de rendimiento y fugas de memoria (Memory Leaks) en aplicaciones empresariales.

# 1. El Ciclo de Compilación y Ejecución
A diferencia de lenguajes como C++ que compilan a código máquina nativo, Java sigue este flujo:
1.  **Código Fuente (.java):** Texto plano legible por humanos.
2.  **Compilador (`javac`):** Genera Bytecode (.class), un set de instrucciones intermedio.
3.  **JVM (Runtime):** Carga el bytecode y lo traduce según la plataforma.
4.  **JIT (Just-In-Time Compiler):** Detecta los métodos más usados ("hotspots") y los compila a código máquina nativo en tiempo real para optimizar la velocidad.



# 2. Organización de la Memoria: Stack vs Heap

Esta es la distinción arquitectónica más crítica para el rendimiento de una aplicación.

## 2.1. Stack (Pila de Ejecución)
-   **Naturaleza:** Memoria estática, lineal y extremadamente rápida (LIFO).
-   **Contenido:** Almacena variables locales de los métodos (primitivos) y las **referencias** (punteros) a objetos.
-   **Ciclo de vida:** Cada hilo (thread) tiene su propio stack. Cuando un método termina, su bloque se libera automáticamente.

## 2.2. Heap (Montículo)
-   **Naturaleza:** Memoria dinámica y de mayor tamaño.
-   **Contenido:** Almacena **todos** los objetos y arrays.
-   **Gestión:** Los objetos viven aquí hasta que el **Garbage Collector (GC)** determina que ya no son accesibles y libera el espacio.



# 3. Tipos de Datos y su Impacto en Memoria

## 3.1. Primitivos (Value Types)
Viven directamente en el Stack. Son eficientes y de tamaño fijo.
-   `int` (32 bits), `double` (64 bits), `boolean` (1 bit lógico).

## 3.2. Referencias (Reference Types)
```java
// "persona" es la referencia en el STACK
// "new Persona()" es el objeto creado en el HEAP
Persona persona = new Persona("Juan"); 
```

> [!question]- ¿Por qué String es especial? (String Constant Pool)
> Los Strings en Java son inmutables. Para optimizar, la JVM usa el **String Constant Pool** en el Heap.
>
> **Ejemplo**:
> `String s1 = "Hola";`
> `String s2 = "Hola";`
> Aquí `s1 == s2` es `true` porque ambos apuntan a la misma dirección de memoria en el Pool para ahorrar RAM.

---

## Resumen

- **Stack**: Rápido, pequeño, almacena primitivos y direcciones.
- **Heap**: Grande, gestionado por el GC, almacena los objetos reales.
- **Ingeniería**: Minimizar la creación de objetos innecesarios en bucles críticos reduce la carga del Garbage Collector y mejora la latencia del sistema.

## Bibliografía
1. Lindholm, T., et al. (2014). *The Java Virtual Machine Specification*. Oracle.
2. Oaks, S. (2014). *Java Performance: The Definitive Guide*. O'Reilly Media.