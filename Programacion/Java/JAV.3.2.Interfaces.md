---
tags:
  - Programacion
  - Programacion/Java
---
# 1.Definición
Es una colección de métodos definidos, define el qué, más no el no cómo, asume un contrato, si se va a implementar la interfaz se le obliga a implementar los métodos de la interfaz, si no los implementa no compila. Las clases pueden implementar no solo una interfaz, pueden implementar varias interfaces. El rol de la interfaz no es el como, es el de servir como molde o estructura.
Apunta a un objeto e implementa la interfaz, en la interfaz no existe un constructor, no se crean objetos y no se definen atributos, solo se crearían constantes, las cuales no varían en las clases. 

- **Abstracción:** El diseño de la interfaz no necesita detalles de la implementación. La referencia de la interfaz apunta a cualquier clase que cumple con el contrato.
- **Polimorfismo:** La clase adquiere la forma de lo establecido en la interfaz. Permite que diferentes objetos de diferentes clases sean tratadas como el mismo tipo, cada uno de los objetos se trata como el tipo de la interfaz.

# 2.Ejemplo
### 2.1.Interfaz y Clases que la Implementan
```java
// Calculable.java
public interface Calculable {
  double calcularArea();
}
```

```java
// Circulo.java
public class Circulo implements Calculable {
  private double radio;

  public Circulo(double radio) {
    this.radio = radio;
  }

  @Override
  public double calcularArea() {
    return Math.PI * this.radio * this.radio;
  }
}
```

```java
// Rectangulo.java
  public class Rectangulo implements Calculable {
    private double base;
    private double altura;

    public Rectangulo(double base, double altura) {
      this.base = base;
      this.altura = altura;
    }

    @Override
    public double calcularArea() {
      return this.base * this.altura;
    }
  }
```

### 2.2.Main
```java
public class mainInterfaz {
  public static void main(String[] args) {
    Calculable c = new Circulo(4.0);
    Calculable r = new Rectangulo(4.0, 6.0);
    System.out.println("Área del círculo: " + c.calcularArea());
    System.out.println("Área del rectángulo: " + r.calcularArea());
  }
}
```