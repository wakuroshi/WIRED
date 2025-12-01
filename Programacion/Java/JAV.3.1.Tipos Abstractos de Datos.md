---
tags:
  - Programacion/Java
  - Programacion
---
# 1.Definición
Tipos de datos a los cuales se asocian operaciones. Ofrecen una interfaz de como acceder a los datos o como manipular.

Comportamiento: Operación que se realizan (TAD/TDA) Lógica
Implementación: Cómo se guardan (GD) Física

### 1.1.Operaciones de Adición
**add:** Añade el elemento al final de la lista
**add(indice, elemento):** Inserta el elemento especificado en el indice posición indicado. Desplaza hacia la derecha los elementos posteriores.
**addAll:** Añade todos los elementos de la colección especificadas al final de la lista
**addAll (indice, elemento):** Inserta todos los elementos de una colección en una posición especificada

### 1.2.Operaciones de Acceso
**get(indice):** Devuelve el elemento en la posición especificada.

### 1.3.Opciones de Eliminación
**remove:** Elimina un elemento en la posición indicada
**Clear():** Elimina todos los elementos de la lista

### 1.4.Ejemplo
```java
// Listas enlazadas (Linkedlist)
import java.util.List;
import java.util.ArrayList;

public class EjemploLista {
  public static void main(String[] args) {
    List<String> listaTareas = new ArrayList<>();

    listaTareas.add("Tarea A"); // Agregar elementos a la lista
    listaTareas.add("Tarea B");
    listaTareas.add("Tarea C");

    System.out.println("Lista inicial: " + listaTareas);

    // Inserción por índice (add) en posición específica
    listaTareas.add(2, "Tarea C nueva");
    System.out.println("Tarea insertada: " + listaTareas);

    // Acceso por índice (get): Obtenemos el elemento de la posición 1
    String tareaPrioritaria = listaTareas.get(1);
    System.out.println("Acceso por índice 1: " + tareaPrioritaria);

    // Eliminaciónpor índice (remove): Removemos el elemento de la posición ()
    listaTareas.remove(0);

    System.out.println("Lista resultante: " + listaTareas);
  }
}
```