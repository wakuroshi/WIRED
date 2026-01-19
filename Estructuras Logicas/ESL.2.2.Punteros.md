# 1.Definición
Es una variable especial que almacena la dirección de memoria de otra variable en lugar de guardar un valor directamente, actuando como una referencia que apunta a ese lugar en la memoria para manipular el dato original de forma eficiente. Cada dato posee una dirección en la memoria, un número, el puntero guarda ese dato. 
Se declara con el tipo de dato seguido con un asterisco. Ej: int \*ptr; se usa & para obtener la dirección de una variable y se usa * sobre el puntero para modificar o leer el valor. Ej. \*ptr = 67;.
# 2.Diferencia entre Punteros y Variables
Una variable es un dato que se le asigna a una variable, un puntero es una variable que se le asigna a un espacio de memoria. Esto permite modificar ese espacio de memoria, reservar espacio de memoria y generar estructuras dinámicas mediante punteros que referencien a la estructura, como listas enlazadas.
# 3.Reglas de Punteros
1) El símbolo * se usa para definir tipo de puntero
2) El símbolo & se usa para indicar la dirección de memoria de una variable
3) El símbolo * se usa para acceder al valor de un puntero
4) El símbolo & se usa para invocar a la función (se antepone a los parámetros de la función)
5) En el cuerpo de la función los argumentos se usan con * (Puntero)
6) El & solo se usa en el programa principal
# 4.Ejemplo
## 4.1.Algoritmo sin punteros
```C
#include <stdio.h>
void intercambio(int x, int y) {
  int z;
  z = y; // No usa punteros, usa variables locales
  x = y;
  y = z;
}

int main(void) {
  int a = 7, b = 8;
  printf("a = %d, b = %d\n", a, b);
  intercambio(a, b);
  printf("a = %d, b = %d\n", a, b);
  return 0;
}
```
---
```Consola
a = 7, b = 8
a = 7, b = 8
```
No se modifica el valor debido a que la función intercambio usa variables locales, es decir, la función crea variables y las modifica, pero no afecta a las variables globales. 
## 4.2.Algoritmo con punteros
```C
#include <stdio.h>
void intercambio(int *x, int *y) {
  int z; 
  z = *x; // el asterisco referencia al valor de x
  *x = *y; 
  *y = z;
}

int main(void) {
  int a = 7, b = 8;
  printf("a = %d, b = %d\n", a, b);
  intercambio(&a, &b);
  printf("a = %d, b = %d\n", a, b);
  return 0;
}
```
---
```Consola
a = 7, b = 8
a = 8, b = 7
``` 
Cuando se utilizan punteros en los argumentos de la función, cuando se modifican los valores, al final se está modificando ese espacio de memoria, es decir, el valor cambia de las variables globales debido a que es el espacio de memoria donde se encuentran alojadas.

# 5.Lista Enlazada
Esta es un tipo de estructura de datos lineal, poseen elementos llamados nodos y no se conectan de manera continua, estos elementos se conectan mediante punteros, referencias que apuntan al siguiente nodo formando una cadena, cada nodo contiene un dato y la dirección del siguiente mediante crecimiento dinámico facilitando inserciones y eliminaciones, sin embargo, recorrerla desde el inicio tiene un tiempo algorítmico de O(n).
## 5.1.Estructura de la Lista Enlazada
```C
#include <stdio.h>
#include <stdlib.h>

int main(void) {
  typedef struct Nodo {
    int dato;
    struct Nodo *siguiente;
  } Nodo;

  Nodo *nuevoNodo = (Nodo *)malloc(sizeof(Nodo));

  if (nuevoNodo == NULL) {
    printf("Error al asignar memoria.\n");
  }
  nuevoNodo->dato = 10;
  nuevoNodo->siguiente = NULL;
  return 0;
}
```
Declara la estructura con struct llamada Nodo, se crea un alias de la estructura con typedef, si no se hiciera en cada que se menciona Nodo se debería usar la palabra "struct", es una estructura como colección de variables, similar a una plantilla.
La estructura contiene espacio para un espacio entero y una referencia al siguiente valor como un puntero a otra estructura de tipo nodo.
## 5.2.Algoritmo Nodos
```C
#include <stdio.h>
#include <stdlib.h>
typedef struct Nodo {
  int dato;
  struct Nodo *sig;
} Nodo;

int main() {
  // Inicializamos los nodos
  Nodo *frente = NULL;
  Nodo *segundo = NULL;
  Nodo *tercero = NULL;

  // Reservamos memoria
  frente = (Nodo *)malloc(sizeof(Nodo));
  segundo = (Nodo *)malloc(sizeof(Nodo));
  tercero = (Nodo *)malloc(sizeof(Nodo));

  // asignamos valores
  frente->dato = 2;
  segundo->dato = 4;
  tercero->dato = 6;

  // Enlazar los nodos
  frente->sig = segundo;
  segundo->sig = tercero;
  tercero->sig = NULL;

  // Imprimir lista recorriendo nodos
  Nodo *n = frente;
  while (n != NULL) {
    printf("%i\t", n->dato);
    n = n->sig;
  }
  return 0;
}
 ```
---
 ```Consola
 2   4   6
 ```
 Se crea la estructura nodo, luego se definen 3 punteros, (frente, segundo y tercero), se declaran los punteros con un casting o conversión explícita como una dirección a Nodo reservando dinámicamente el tamaño del nodo, luego se definen los valores dato de cada nodo y apuntan al siguiente nodo. Por último, se crea un puntero llamado n que es el primer nodo, como todos los nodos apuntan a un valor, n va a recorrer todos los valores imprimiendo el dato hasta que encuentre un nodo cuyo valor sea nulo.