---
tags:
- Programacion/Java
---

# JAV.1.1.Herencia

# 1. Herencia

Modela un objeto según la clase padre
- Un agente es un empleado
- Un carro es un vehículo
- Un cuadrado es una figura geométrica

## 1.1. Caso de Herencia

![Caso Herencia!](JAV.2.1.fa.png)

## 1.1. Elementos Clave y Sintaxis

| Concepto       | Nombre Común             | Definición                                  | Sintaxis                            |
| -------------- | ------------------------ | ------------------------------------------- | ----------------------------------- |
| Clase Base     | Superclase - Clase padre | Clase que se proporciona atributos, métodos | Public class Empleado{}<br>}        |
| Clase Derivada | Subclase - Clase hija    | Clase que se hereda de la clase base        | Public class extends Empleado{<br>} |
| Palabra Clave  | Extender                 | Palabra clave que establece la herencia     |                                     |

```java
public class Empleado{
  private String id;
  private double salarioBase;

  public Empleado(String id, double salarioBase){
    this.id=id;
    this.salarioBase=salarioBase;
  }

  public double calcularSalario(){
    System.out.println("\n[Empleado] Calcular salario base");
    return this.salarioBase;
  }

  public double getSalarioBase(){
    return salarioBase;
  }
}
```
