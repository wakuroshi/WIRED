# 1. ¿Qué es?
Es una técnica de programación en la que una función se llama a sí misma para resolver e problema, dividiendolo en subproblemas más pequeños, cada vez que se llama a sí misma, trabaja en un subconjunto más pequeño del problema origina hasta alcanzar un estado base, lo que permite que la recursión termine.

## 1.1. Estructura
```java
public void metodo(){
	bloque instrucciones;
	metodo();
}
```
Es necesario definir un caso base, es crucial para que se determine cuando debe detenerse la función, de lo contrario, continuaría llamándose indefinidamente.

# 2. Ejercicio
```java
//Crear una serie numérica del 1 al 5 en estructura repetitiva

public class Recursividad{
  public static void Imprimir(int x,int limite){
    if(x<x+limite){ // se define el caso base
      System.out.print(x+" ");
      limite-=1;
      x+=1;
      Imprimir(x,limite); // Se utiliza la recursividad
    }
  }
}

public class recursividad{
 public static void main(String[] args) {
  Recursividad.Imprimir(6, 5); // Se llama a la función con los parámetros
 }
}

```