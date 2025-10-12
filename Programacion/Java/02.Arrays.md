# 1. Arreglos en Java
## 1.1. Arreglos unidimensionales
En Java hay tres Formas de crear arreglos (arrays)
```java
// 1. Con valores iniciales
int[] numeros1 = {1, 2, 3, 4, 5};

// 2. Con new y tamaño
int[] numeros2 = new int[5];

// 3. Con new y valores
int[] numeros3 = new int[]{1, 2, 3};
```
## 1.2. Arreglos Multidimensionales
```java
// Matriz 2x3
int[][] matriz = {{1,2,3}, {4,5,6}};

// Matriz vacia 3x3
int[][] tabla = new int[3][3];
```
# 2. Propiedades y Metodos Utiles
## 2.1. Propiedad length
```java
int[] edades = {25, 30, 35};
int tamaño = edades.length;  // 3
```
## 2.2. Clase Arrays
```java
import java.util.Arrays;

int[] numeros = {3, 1, 2};

// Ordenar
Arrays.sort(numeros);  // {1, 2, 3}

// Busqueda binaria
int pos = Arrays.binarySearch(numeros, 2);

// Comparar
boolean iguales = Arrays.equals(arr1, arr2);

// Convertir a String
String texto = Arrays.toString(numeros);
```
# 3. Operaciones Comunes
## 3.1. Recorrido con For
```java
int[] valores = {10, 20, 30};

// For tradicional
for(int i = 0; i < valores.length; i++) {
    System.out.println(valores[i]);
}

// For-each
for(int valor : valores) {
    System.out.println(valor);
}
```
## 3.2. Busqueda Lineal
```java
public static int buscarLineal(int[] arr, int objetivo) {
    for(int i = 0; i < arr.length; i++) {
        if(arr[i] == objetivo) {
            return i;  // Retorna indice
        }
    }
    return -1;  // No encontrado
}
```
## 3.3. Insercion
```java
public static int[] insertarElemento(int[] arr, int elemento, int posicion) {
    if(posicion < 0 || posicion > arr.length) {
        return arr;  // Posicion invalida
    }
    
    int[] nuevo = new int[arr.length + 1];
    
    // Copiar elementos antes de la posicion
    for(int i = 0; i < posicion; i++) {
        nuevo[i] = arr[i];
    }
    
    // Insertar nuevo elemento
    nuevo[posicion] = elemento;
    
    // Copiar elementos despues de la posicion
    for(int i = posicion; i < arr.length; i++) {
        nuevo[i + 1] = arr[i];
    }
    
    return nuevo;
}
```
## 3.4. Eliminacion
```java
public static int[] eliminarElemento(int[] arr, int posicion) {
    if(posicion < 0 || posicion >= arr.length) {
        return arr;  // Posicion invalida
    }
    
    int[] nuevo = new int[arr.length - 1];
    
    // Copiar elementos antes de la posicion
    for(int i = 0; i < posicion; i++) {
        nuevo[i] = arr[i];
    }
    
    // Copiar elementos despues de la posicion
    for(int i = posicion + 1; i < arr.length; i++) {
        nuevo[i - 1] = arr[i];
    }
    
    return nuevo;
}
```
# 4. Arreglos vs ArrayList
Los arreglos normales (no clase) son mucho mas simples en Java, su tamaño es fijo una vez se declara y se puede acceder facilmente a sus indices y declarar el valor de cada uno. Mientras que el ArrayList (clase) tiene tamaño dinamico y añade al final del array

- **Arreglos Normales**
```java
int[] fixed = new int[5];  // Tamaño fijo
fixed[0] = 10;            // Acceso rapido
```
- **ArrayList**
```java
import java.util.ArrayList;

ArrayList<Integer> dynamic = new ArrayList<>();  // Tamaño dinamico
dynamic.add(10);          // Agrega al final
dynamic.get(0);           // Acceso por indice
dynamic.remove(0);        // Elimina elemento
```
# 5. Casos Especiales
- **Arreglo de Objetos**
```java
String[] nombres = new String[3];
nombres[0] = "Ana";
nombres[1] = "Juan";
```
- **Arreglo como Parametro**
```java
public static void modificarArreglo(int[] arr) {
    arr[0] = 100;  // Modifica el original
}

public static int[] crearArreglo() {
    return new int[]{1, 2, 3};  // Retorna nuevo arreglo
}
```
---
# Resumen
Los arreglos en Java son de tamaño fijo y se declaran con [] o new.
Tienen propiedad length y se pueden manipular con clase Arrays.
Soportan operaciones como recorrido, busqueda, insercion y eliminacion.
ArrayList ofrece version dinamica con metodos add, get, remove.


