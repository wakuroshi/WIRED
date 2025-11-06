---
tags:
- Programacion/Java
---

# JAV.1.3.Bucles

# 1. Metodos de Busqueda en Java

## 1.1. Busqueda Lineal

- **Implementacion Basica**

```java
public static int busquedaLineal(int[] arreglo, int objetivo) {
    for(int i = 0; i < arreglo.length; i++) {
        if(arreglo[i] == objetivo) {
            return i;  // Retorna indice del elemento encontrado
        }
    }
    return -1;  // Elemento no encontrado
}
```

- **Para Arrays de Objetos**

```java
public static int busquedaLineal(String[] arreglo, String objetivo) {
    for(int i = 0; i < arreglo.length; i++) {
        if(arreglo[i].equals(objetivo)) {
            return i;
        }
    }
    return -1;
}
```

- **Con For-Each (solo valor, no indice)**

```java
public static boolean contiene(int[] arreglo, int objetivo) {
    for(int elemento : arreglo) {
        if(elemento == objetivo) {
            return true;
        }
    }
    return false;
}
```

## 1.2. Busqueda Binaria 

- **Requisito Previo: Ordenamiento**

```java
import java.util.Arrays;

int[] numeros = {5, 2, 8, 1, 9};
Arrays.sort(numeros);  // {1, 2, 5, 8, 9}
```

- **Implementacion Iterativa**

```java
public static int busquedaBinaria(int[] arreglo, int objetivo) {
    int inicio = 0;
    int fin = arreglo.length - 1;
    
    while(inicio <= fin) {
        int medio = inicio + (fin - inicio) / 2;  // Evitar desbordamiento
        
        if(arreglo[medio] == objetivo) {
            return medio;  // Elemento encontrado
        }
        
        if(arreglo[medio] < objetivo) {
            inicio = medio + 1;  // Buscar en mitad derecha
        } else {
            fin = medio - 1;     // Buscar en mitad izquierda
        }
    }
    return -1;  // Elemento no encontrado
}
```

- **Implementacion Recursiva**

```java
public static int busquedaBinariaRecursiva(int[] arreglo, int objetivo, int inicio, int fin) {
    if(inicio <= fin) {
        int medio = inicio + (fin - inicio) / 2;
        
        if(arreglo[medio] == objetivo) {
            return medio;
        }
        
        if(arreglo[medio] < objetivo) {
            return busquedaBinariaRecursiva(arreglo, objetivo, medio + 1, fin);
        } else {
            return busquedaBinariaRecursiva(arreglo, objetivo, inicio, medio - 1);
        }
    }
    return -1;
}

// Metodo wrapper para facilitar uso
public static int busquedaBinaria(int[] arreglo, int objetivo) {
    return busquedaBinariaRecursiva(arreglo, objetivo, 0, arreglo.length - 1);
}
```

## 1.3. Usando Arrays.binarySearch()

- **Para Arrays Nativos**

```java
int[] numeros = {1, 3, 5, 7, 9};
int posicion = Arrays.binarySearch(numeros, 5);  // 2
int noEncontrado = Arrays.binarySearch(numeros, 4);  // Valor negativo
```

- **Para ArrayList y Colecciones**

```java
import java.util.ArrayList;
import java.util.Collections;

ArrayList<Integer> lista = new ArrayList<>();
lista.add(1);
lista.add(3);
lista.add(5);

int pos = Collections.binarySearch(lista, 3);  // 1
```

# 2. Consideraciones de Rendimiento (Cuando Usar Cada Metodo)

```java
// Para arrays pequeños o no ordenados
int pos = busquedaLineal(miArray, valor);

// Para arrays grandes y ordenados  
int pos = busquedaBinaria(miArrayOrdenado, valor);

// Usando libreria estandar
int pos = Arrays.binarySearch(miArrayOrdenado, valor);
```

---

# Resumen 

Busqueda lineal recorre secuencialmente (O(n)), funciona en arrays 
no ordenados. Busqueda binaria requiere array ordenado pero es mas 
eficiente (O(log n)), usando estrategia divide y venceras. Java 
proporciona Arrays.binarySearch() para arrays nativos y 
Collections.binarySearch() para listas.
