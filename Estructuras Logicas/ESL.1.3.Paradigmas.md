---
materia: Estructuras Lógicas
id: ESL.1.3
tema: Paradigmas de Programación
status: Revision
tags:
  - EstructurasLogicas
  - paradigmas
  - OOP
  - funcional
  - estructurada
---

# ESL.1.3. Paradigmas de Programación

> [!abstract] Modelos de Pensamiento
> Un paradigma no es un lenguaje, es una forma de razonar sobre la solución de un problema. Define cómo se estructura el código, cómo se manipulan los datos y cómo se gestiona el estado del programa.

---

# 1. Definición y Clasificación

Un paradigma impone reglas sobre lo que el programador **puede** y **no puede** hacer. Curiosamente, los paradigmas más avanzados (como Funcional) restringen más al programador que los primitivos (como Ensamblador), lo que paradójicamente resulta en software más robusto.

### 1.1. Imperativo vs Declarativo
- **Imperativo (C, Assembly):** Le dices a la máquina **CÓMO** hacer las cosas, paso a paso ("Mueve este dato aquí, suma esto, salta allá").
- **Declarativo (SQL, HTML):** Le dices a la máquina **QUÉ** quieres obtener, sin especificar los pasos internos.

# 2. Programación Estructurada (La base de C)

Nace con el **Teorema de Böhm-Jacopini** (1966), que demostró que cualquier algoritmo puede escribirse usando solo tres estructuras de control, eliminando la necesidad del caótico `GOTO`.

### 2.1. Las Tres Estructuras
1.  **Secuencia:** Ejecución lineal de instrucciones.
2.  **Selección:** Decisiones lógicas (`if`, `switch`).
3.  **Iteración:** Bucles (`for`, `while`).

### 2.2. Modularidad
El problema se divide en funciones pequeñas y reutilizables.
- **Ventaja:** Fácil de entender y depurar.
- **Desventaja:** Los datos suelen ser globales o pasarse constantemente entre funciones, lo que dificulta la seguridad en sistemas grandes.

**Ejemplo en C (Cálculo de Factorial):**
```c
#include <stdio.h>

int factorial(int n) {
    int res = 1;
    for (int i = 1; i <= n; i++) { // Iteración
        res *= i; // Secuencia
    }
    return res;
}
````

# 3. Programación Orientada a Objetos (POO)

Surge para controlar la complejidad. En lugar de tener lógica y datos separados, se unen en una entidad llamada **Objeto**. _Nota de Ingeniería:_ C no tiene objetos nativos, pero se pueden simular usando `structs` y punteros a funciones.

### 3.1. Los 4 Pilares Fundamentales

1. **Encapsulamiento:** Proteger los datos internos. El objeto controla quién modifica sus variables.
    
2. **Abstracción:** Mostrar solo lo esencial. El usuario del objeto no necesita saber cómo funciona por dentro.
    
3. **Herencia:** Crear nuevas clases basadas en otras existentes (Reutilización de código).
    
4. **Polimorfismo:** Capacidad de tratar objetos de diferentes clases de manera uniforme (ej. tratar a un `Círculo` y un `Cuadrado` como `Figura`).
    

### 3.2. Simulación de Objeto en C (Structs)

Aunque C no tiene `class`, así es como los ingenieros crean objetos en sistemas operativos (como Linux):

C

```
// Definición de la "Clase"
typedef struct Coche {
    int velocidad;        // Atributo
    void (*acelerar)(struct Coche*); // "Método" (Puntero a función)
} Coche;

// Implementación del método
void acelerar_impl(Coche *this) {
    this->velocidad += 10;
}

// Uso
int main() {
    Coche miAuto;
    miAuto.velocidad = 0;
    miAuto.acelerar = acelerar_impl; // Enlace
    
    miAuto.acelerar(&miAuto); // Llamada al método
    return 0;
}
```

# 4. Programación Funcional

Trata la computación como la evaluación de funciones matemáticas puras. Evita el **Estado Mutable** (variables que cambian de valor).

### 4.1. Conceptos Clave

- **Inmutabilidad:** Una vez creada una variable, no se puede cambiar. Si quieres modificar algo, creas una copia nueva.
    
- **Funciones Puras:** Para una misma entrada, siempre devuelven la misma salida y no tienen "efectos secundarios" (no tocan variables globales ni imprimen en pantalla).
    
- **Funciones de Orden Superior:** Funciones que pueden recibir otras funciones como parámetros (Callbacks).
    

### 4.2. Ejemplo Conceptual en C (Punteros a Función)


```C
void operar(int a, int b, int (*funcion)(int, int)) {
    printf("Resultado: %d\n", funcion(a, b));
}

int suma(int a, int b) { return a + b; }

int main() {
    operar(5, 3, suma); // Pasamos la función como dato
    return 0;
}
```

# 5. Comparativa Técnica

|Característica|Estructurada|Orientada a Objetos|Funcional|
|---|---|---|---|
|**Unidad base**|Función|Objeto (Clase)|Función Pura|
|**Datos**|Separados de la lógica|Encapsulados con lógica|Inmutables|
|**Estado**|Mutable (Variables)|Mutable (Propiedades)|Inmutable|
|**Ejecución**|Secuencial|Interacción de mensajes|Evaluación matemática|
|**Uso Ideal**|Sistemas Embebidos, Drivers|Sistemas Grandes, UI|Concurrencia, Datos|

---

## Resumen Técnico

- **Estructurada:** Divide y vencerás. Ideal para control de bajo nivel.
    
- **POO:** Modela el mundo real. Ideal para gestionar sistemas complejos con muchas entidades.
    
- **Funcional:** Minimiza errores de estado. Ideal para procesamiento de datos paralelo donde la mutabilidad causa bugs.
    
- C es un lenguaje **multiparadigma** (Imperativo por defecto, pero permite simular POO y Funcional mediante punteros).
    

## Bibliografía

- ESL.1.3.Paradigmas.md (Apuntes originales).
    
- Stroustrup, B. - _The C++ Programming Language_ (Historia de paradigmas).
    
- Martin, R. C. - _Clean Architecture_.