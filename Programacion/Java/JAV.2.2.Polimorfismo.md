---
materia: Programación Java
id: JAV.2.2
tema: Polimorfismo, Sobrecarga y Sobreescritura
status: Revision
tags:
  - java
  - oop
  - polymorphism
  - dynamic-binding
---

# JAV.2.2. Polimorfismo y Enlace Dinámico

> [!abstract]- Múltiples formas, un solo contrato
> El polimorfismo permite que una referencia de una superclase pueda apuntar a objetos de cualquiera de sus subclases. Es la base del diseño modular: permite escribir código que interactúe con una abstracción (ej. `Forma`) sin conocer la implementación específica (ej. `Circulo` o `Cuadrado`) hasta el tiempo de ejecución.

# 1. Sobreescritura vs. Sobrecarga

Para un ingeniero, la diferencia radica en el **tiempo (Timing)** en que la JVM resuelve el método.

## 1.1. Sobrecarga (Overloading) - Estático
- **Ocurre en**: Tiempo de compilación.
- **Definición**: Métodos con mismo nombre pero distinta firma (parámetros).
```java
public int sumar(int a, int b) { return a + b; }
public double sumar(double a, double b) { return a + b; }
```

## 1.2. Sobreescritura (Overriding) - Dinámico
- **Ocurre en**: Tiempo de ejecución (Runtime).
- **Definición**: Redefinir un método de la superclase en la subclase.
```java
@Override // Obligatorio para validación del compilador
public double calcularSalario() { ... }
```

# 2. El Enlace Dinámico (Dynamic Binding)

Es el mecanismo por el cual la JVM decide qué método ejecutar basándose en el **tipo del objeto real** en el Heap, no en el tipo de la referencia.

```java
Empleado e = new Desarrollador(); 
e.trabajar(); // Ejecutará la versión de Desarrollador, no la de Empleado.
```



# 3. Casting de Objetos y RTTI

- **Upcasting**: (Automático) Tratar a un hijo como padre. Siempre seguro.
- **Downcasting**: (Manual) Tratar a un padre como hijo. Requiere verificar con `instanceof`.

```java
if (e instanceof Desarrollador) {
    Desarrollador d = (Desarrollador) e; 
    d.programar();
}
```

> [!question]- Pattern Matching (Java 16+)
> Modernamente, Java permite simplificar el casting en una sola línea:
> `if (e instanceof Desarrollador d) { d.programar(); }`
> Esto reduce errores de `ClassCastException`.

---

## Resumen

- **Flexibilidad**: El polimorfismo permite que el código sea extensible sin modificar el núcleo (Principio Open/Closed).
- **Contratos**: La referencia define qué métodos puedes llamar; el objeto real define cómo se ejecutan.
- **Rendimiento**: La búsqueda del método en la tabla virtual (VTable) en runtime tiene un costo mínimo frente a la flexibilidad que aporta.

## Bibliografía
1. Gamma, E., et al. (1994). *Design Patterns: Elements of Reusable Object-Oriented Software*.
2. Oracle. (2023). *Java Documentation: Polymorphism*.