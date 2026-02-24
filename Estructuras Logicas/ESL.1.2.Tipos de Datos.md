---
materia: Estructuras Lógicas
id: ESL.1.2
tema: Tipos de Datos, Memoria y Estructuras
status: Revision
tags:
  - EstructurasLogicas
  - C
  - arrays
  - strings
  - memoria
---

# ESL.1.2. Tipos de Datos: La Arquitectura de la Memoria

> [!abstract] Interpretando Bits
> En la memoria RAM, todo son ceros y unos. Un "Tipo de Dato" es la máscara que le dice al compilador cómo interpretar esos bits (si es un número, una letra o una dirección) y cuánto espacio ocupar.

---

# 1. Tipos Primitivos (Escalares)

Son los bloques indivisibles de información. Su tamaño depende de la arquitectura (32 vs 64 bits), pero en ingeniería se asumen estándares.

### 1.1. Enteros
- **char (1 byte):** Aunque se usa para caracteres ASCII, en realidad es un entero pequeño (-128 a 127).
- **int (4 bytes):** El estándar para contadores.
- **short (2 bytes):** Para ahorro de memoria.
- **long long (8 bytes):** Para cifras astronómicas.
- **unsigned:** Modificador vital en sistemas embebidos. Al eliminar los negativos, duplicamos el rango positivo. Ejemplo: `unsigned char` va de 0 a 255 (ideal para valores RGB).

### 1.2. Punto Flotante (IEEE 754)
Las computadoras no guardan decimales exactos, guardan una aproximación binaria.
- **float (4 bytes):** Precisión simple.
- **double (8 bytes):** Precisión doble.
*Nota de Ingeniería:* Jamás uses `float` para dinero. Los errores de redondeo se acumulan.



# 2. Arreglos (Arrays): Memoria Contigua

Un arreglo es una secuencia de datos del mismo tipo ubicados uno tras otro en la RAM.
- **Declaración:** `int numeros[5];`
- **Acceso:** `numeros[0]` es el primero.
- **Velocidad:** Acceso $O(1)$ (Inmediato). El compilador calcula la dirección así:
  $$Dir = Base + (Indice \times SizeOf(Tipo))$$

### 2.1. El peligro de los Arreglos en C
C no verifica límites. Si escribes en `numeros[10]` de un arreglo de 5, sobrescribirás memoria de otra variable, causando comportamientos impredecibles o ataques de seguridad (Buffer Overflow).

# 3. Cadenas de Caracteres (Strings)

En C, **no existe el tipo String**. Existen arreglos de caracteres terminados en nulo.

### 3.1. El Carácter Nulo (`\0`)
Es un byte con valor 0. Marca el final del texto.
```c
char saludo[5] = {'H', 'o', 'l', 'a', '\0'};
```
Si olvidas el `\0`, funciones como `printf` seguirán leyendo basura de la memoria hasta que el programa colapse.

### 3.2. Funciones de `<string.h>`
- `strcpy(dest, src)`: Copia el contenido. No usar `=` para asignar strings.
- `strcmp(s1, s2)`: Compara strings. Devuelve 0 si son iguales.
- `strlen(s)`: Devuelve la longitud (sin contar el `\0`).

# 4. Estructuras (Structs)

Permiten crear tipos de datos personalizados agrupando variables de distinto tipo.

```c
struct Nodo {
    int id;           // 4 bytes
    char etiqueta[10];// 10 bytes
    float valor;      // 4 bytes
};
```

### 4.1. Alineación de Memoria (Padding)
El procesador lee bloques de 4 u 8 bytes. Si declaras un `char` (1 byte) seguido de un `int` (4 bytes), el compilador insertará 3 bytes vacíos de "relleno" para que el `int` empiece en una dirección alineada. Esto es crucial saberlo al enviar datos por red.

# 5. Casting (Conversión de Tipos)

- **Implícito:** Automático. De `int` a `float`.
- **Explícito:** Manual. De `float` a `int` (truncamiento).
```c
void *ptr;
int *pEntero = (int*)ptr; // Casting de puntero genérico a puntero a entero
```

---

## Resumen Técnico
- Los **Arreglos** son rígidos en tamaño pero rápidos en acceso.
- Las **Cadenas** requieren gestión manual de memoria y precaución extrema con el terminador nulo.
- Las **Estructuras** son la base de la Programación Orientada a Objetos y de las estructuras de datos complejas.

## Bibliografía
- Kernighan, B. & Ritchie, D. - *The C Programming Language*.
- Apuntes de clase Unidad 1.