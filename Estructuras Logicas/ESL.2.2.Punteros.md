---
materia: Estructuras Lógicas
id: ESL.2.2
tema: Punteros, Memoria Dinámica y Nodos
status: Revision
tags:
  - EstructurasLogicas
  - punteros
  - malloc
  - nodos
  - C
---

# ESL.2.2. Punteros y Nodos: El Corazón de C

> [!abstract] Acceso Directo
> Un puntero es una variable que no guarda un valor, sino una **dirección de memoria**. Esto permite modificar variables a distancia, compartir datos grandes sin copiarlos y crear estructuras que cambian de tamaño.

---

# 1. Sintaxis y Operadores

### 1.1. Declaración
```c
int *ptr; // Puntero a un entero
```
El asterisco aquí indica "tipo puntero".

### 1.2. Operadores Clave
- **`&` (Ampersand):** "La dirección de". Obtiene dónde vive una variable.
- **`*` (Asterisco):** "Lo que hay en". Accede al valor apuntado (Desreferencia).

```c
int num = 10;
int *p = &num; // p apunta a num
*p = 20;       // num ahora vale 20
```

# 2. Memoria Dinámica (Heap vs Stack)

Las variables normales viven en el Stack y mueren al terminar la función. Si queremos datos que sobrevivan o cuyo tamaño desconocemos al compilar, usamos el Heap.

### 2.1. `malloc` (Memory Allocation)
Pide bytes al sistema operativo.
```c
// Pide espacio para un entero
int *p = (int*)malloc(sizeof(int)); 
```

### 2.2. `free` (Liberación)
Crucial. En C no hay recolector de basura. Si no liberas, creas un **Memory Leak**.
```c
free(p); // Devuelve la memoria al sistema
p = NULL; // Buena práctica para no dejar punteros colgantes
```

# 3. Estructuras de Nodos

Los punteros permiten que un struct referencie a otro struct del mismo tipo.

```c
typedef struct Nodo {
    int dato;
    struct Nodo *siguiente; // Enlace al próximo nodo
} Nodo;
```

Esta es la base de las Listas Enlazadas. Los nodos no están juntos en memoria, están dispersos, pero conectados por estos punteros.

# 4. Aritmética de Punteros

Los punteros son números (direcciones), así que se pueden sumar.
- `ptr + 1`: No suma 1 byte, suma `sizeof(tipo)`.
- Si `ptr` apunta a un `int` (4 bytes) en la dirección 1000, `ptr + 1` será la dirección 1004.
- Esto es exactamente cómo funcionan los arreglos internamente. `arr[i]` es azúcar sintáctica para `*(arr + i)`.

# 5. Errores Mortales en Ingeniería

1.  **Segmentation Fault:** Intentar leer/escribir en memoria que no te pertenece (ej. un puntero `NULL` o no inicializado).
2.  **Dangling Pointer:** Usar un puntero después de haber hecho `free` sobre él.
3.  **Memory Leak:** Perder la referencia a un bloque reservado sin liberarlo. En servidores que corren 24/7, esto tumba el sistema.

---

## Resumen Técnico
- Los punteros dan poder absoluto sobre la memoria, con la responsabilidad absoluta de gestionarla.
- `malloc` devuelve memoria "sucia" (con basura), `calloc` la devuelve limpia (ceros).
- Entender punteros es el requisito previo para entender Estructuras de Datos.

## Bibliografía
- Deitel & Deitel - *C How to Program*.
- Kernighan, B. W. - *The C Programming Language*.