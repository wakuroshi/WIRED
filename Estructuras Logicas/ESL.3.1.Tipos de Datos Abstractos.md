---
materia: Estructuras Lógicas
id: ESL.3.1
tema: Tipos de Datos Abstractos (TDA) Lineales
status: Revision
tags:
  - EstructurasLogicas
  - listas
  - pilas
  - colas
  - TDA
---

# ESL.3.1. Listas, Pilas y Colas (TDAs)

> [!abstract] Abstracción Lógica
> Un TDA define QUÉ se puede hacer con los datos (Interfaz), ignorando CÓMO se guardan (Implementación). Veremos las tres estructuras lineales dinámicas fundamentales.

---

# 1. Listas Enlazadas

Colección de nodos donde cada uno apunta al siguiente.
- **Ventaja:** Crecimiento dinámico. No hay límite fijo como en los arrays.
- **Desventaja:** Acceso lento. Para llegar al 5to elemento, debes pasar por los 4 anteriores ($O(n)$).

### 1.1. Tipos de Listas
- **Simple:** Navegación en un sentido (->).
- **Doble:** Navegación bidireccional (<- ->). Requiere más memoria por el puntero extra.
- **Circular:** El último apunta al primero. Útil para buffers cíclicos.

# 2. La Pila (Stack)

Estructura **LIFO** (Last In, First Out).
- El último elemento en entrar es el primero en salir.
- **Operaciones:** `Push` (Meter), `Pop` (Sacar), `Peek` (Mirar cima).

### 2.1. Implementación en C (con Punteros)
```c
void push(Nodo **top, int valor) {
    Nodo *nuevo = malloc(sizeof(Nodo));
    nuevo->dato = valor;
    nuevo->sig = *top; // El nuevo apunta al antiguo top
    *top = nuevo;      // Actualizamos el top
}
```

### 2.2. Usos Reales
- **Deshacer/Rehacer (Undo):** Los editores guardan estados en una pila.
- **Evaluación de Expresiones:** Convertir `3 + 4` en notación que la CPU entienda.
- **Backtracking:** Algoritmos que buscan salidas en laberintos.

# 3. La Cola (Queue)

Estructura **FIFO** (First In, First Out).
- El primero en llegar es el primero en ser atendido.
- **Operaciones:** `Enqueue` (Encolar al final), `Dequeue` (Sacar del frente).



### 3.1. Implementación Eficiente
Se necesitan dos punteros: `frente` (para sacar) y `final` (para meter). Así ambas operaciones son $O(1)$. Si solo tuvieras un puntero al inicio, insertar al final costaría $O(n)$.

### 3.2. Usos Reales
- **Spooler de Impresión:** Los documentos se imprimen en orden de llegada.
- **Servidores Web:** Las peticiones de usuarios se encolan para ser procesadas.
- **Buffers de Audio:** Los datos se encolan para reproducirse suavemente.

---

## Resumen Técnico
- **Arrays:** Lectura rápida, tamaño fijo.
- **Listas:** Lectura lenta, tamaño dinámico.
- **Pilas/Colas:** Son listas con restricciones de acceso estrictas para modelar comportamientos lógicos específicos.

## Bibliografía
- Tenenbaum, A. - *Data Structures Using C*.
- Weiss, M. A. - *Data Structures and Algorithm Analysis*.