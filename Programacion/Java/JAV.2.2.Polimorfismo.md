---
tags:
  - Programacion/Java
  - Programacion
---
# 1. Sobreescritura
Se le llama sobreescritura al usarse en la clase hija un mismo método que en la clase padre, el método posee el mismo nombre que el de la clase padre, pero se sobreescritura (denotado con @Override) y permite que se modifique el comportamiento del método en la clase hija. **Ejemplo:**
```java
class CalculadoraBase{
  public int sumar(int a, int b){
    System.out.println("Base: Usando suma estandar de la calculadora base: ");
    return a+b;
    }
}

class CalculadoraAvanzada extends CalculadoraBase{
//sobreescritura
  @Override
  public int sumar(int a, int b){
    System.out.println("Avanzado: Usando suma optimizada de la calculadora avanzada");
    return a + b + 10;
  }
}
//Fin de sobreescritura
```

# 2.Sobrecarga
Se le llama sobrecarga al uso de un mismo método en una clase, pero con diferentes parámetros (tanto el tipo de dato como la cantidad de parámetros) lo que permite que un mismo método pueda realizar distintas funciones dependiendo de los parámetros que se tienen. **Ejemplo:**
```java
class CalculadoraBase{
//Sobrecarga
  public int sumar(int a, int b){
    System.out.println("Base: Usando suma estandar de la calculadora base: ");
    return a+b;
  }
  public double sumar(double a, double b){
    return a+b;
  }
}
//Fin de Sobrecarga
```
## 2.1. Ejemplo completo:
```java
class CalculadoraBase{
//Sobrecarga
  public int sumar(int a, int b){
    System.out.println("Base: Usando suma estandar de la calculadora base: ");
    return a+b;
  }
  public double sumar(double a, double b){
    return a+b;
  }
}
//Fin de Sobrecarga

class CalculadoraAvanzada extends CalculadoraBase{
//sobreescritura
  @Override
  public int sumar(int a, int b){
    System.out.println("Avanzado: Usando suma optimizada de la calculadora avanzada");
    return a + b + 10;
  }
//Fin de sobreescritura
}

public class overloading{
  public static void main(String[] args) {
    CalculadoraBase base=new CalculadoraBase();
    CalculadoraAvanzada avanzada=new CalculadoraAvanzada();
    System.out.println(base.sumar(5,4));
    System.out.println(avanzada.sumar(5,4));
  }
}

```