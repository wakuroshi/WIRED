---
materia: Programación Java
id: JAV.2.3
tema: Clases Abstractas e Interfaces
status: Revision
tags:
  - java
  - oop
  - interface
  - abstraction
---

# JAV.2.3. Abstracción e Interfaces

> [!abstract]- El Qué vs. El Cómo
> La abstracción consiste en capturar las características esenciales de un objeto omitiendo los detalles de implementación. Mientras que una **Clase Abstracta** define una identidad compartida ("qué es algo"), una **Interfaz** define un contrato de comportamiento ("qué puede hacer algo").

# 1. Clases Abstractas (`abstract`)
Son clases que no pueden ser instanciadas. Actúan como un punto medio entre una clase concreta y una interfaz.
- Pueden tener atributos (estado) y métodos con cuerpo.
- Obligan a las subclases a implementar los métodos marcados como `abstract`.

# 2. Interfaces (`interface`)
Representan un contrato 100% puro (aunque Java 8+ permite métodos `default`). Una clase puede implementar múltiples interfaces, superando la limitación de la herencia simple.

```java
public interface Conectable {
    void conectar(); // Abstracto por defecto
    default void log() { System.out.println("Conexión iniciada"); }
}
```

# 3. Matriz de Decisión de Ingeniería

| Característica | Clase Abstracta | Interfaz |
| :--- | :--- | :--- |
| **Propósito** | Compartir estructura y código base. | Definir un protocolo de comunicación. |
| **Relación** | Jerarquía fuerte ("Es un"). | Capacidad ("Actúa como"). |
| **Estado** | Puede tener variables de instancia. | Solo constantes (`static final`). |
| **Herencia** | Simple (Solo una). | Múltiple (Varias). |



# 4. Interfaces Funcionales
Son interfaces con un solo método abstracto. Son el puente hacia la programación funcional en Java.
```java
@FunctionalInterface
public interface Validador {
    boolean validar(String s);
}
// Uso con Lambda:
Validador v = (s) -> s.length() > 5;
```

---

## Resumen

- **Desacoplamiento**: Diseñar para interfaces permite cambiar implementaciones (ej. cambiar una Base de Datos) sin tocar el resto del sistema.
- **Abstracción**: No es una técnica de ahorro de código, es una técnica de organización mental del software.
- **Evolución**: Las interfaces son más fáciles de evolucionar que las jerarquías de clases abstractas.

## Bibliografía
1. Martin, R. C. (2002). *Agile Software Development*. (The Interface Segregation Principle).
2. Eckel, B. (2006). *Thinking in Java*.