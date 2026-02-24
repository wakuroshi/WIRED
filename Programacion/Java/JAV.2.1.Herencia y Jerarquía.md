---
materia: Programación Java
id: JAV.2.1
tema: Herencia, Modificadores y Diseño de Clases
status: Revision
tags:
  - java
  - oop
  - inheritance
  - encapsulation
---

# JAV.2.1. Herencia y Jerarquía de Clases

> [!abstract]- La Relación "Es-Un" (Is-A)
> La herencia es un pilar de la POO que permite a una clase (subclase) adquirir el estado y comportamiento de otra (superclase). En ingeniería, la herencia no se usa solo para reutilizar código, sino para establecer taxonomías de objetos. Sin embargo, genera un **acoplamiento fuerte**, por lo que su diseño debe ser rígido y seguir principios como el de Sustitución de Liskov.

# 1. Mecánica de la Herencia (`extends`)

Java utiliza la palabra clave `extends` para establecer la jerarquía. A diferencia de otros lenguajes, Java solo permite **herencia simple** (un solo padre) para evitar conflictos de ambigüedad.

## 1.1. El rol de `super` y los Constructores
Los constructores no se heredan. La subclase debe invocar al constructor de la superclase para asegurar que el objeto se inicialice correctamente desde su base.
```java
public class Empleado {
    protected String id;
    public Empleado(String id) { this.id = id; }
}

public class Desarrollador extends Empleado {
    private String lenguaje;
    public Desarrollador(String id, String lenguaje) {
        super(id); // Debe ser la primera instrucción
        this.lenguaje = lenguaje;
    }
}
```

# 2. Modificadores de Acceso y Encapsulamiento

El éxito de una jerarquía depende de cómo se ocultan los datos. El nivel `protected` es la pieza clave:

| Modificador | Clase | Paquete | Subclase | Mundo |
| :--- | :---: | :---: | :---: | :---: |
| **private** | ✅ | ❌ | ❌ | ❌ |
| **(default)** | ✅ | ✅ | ❌ | ❌ |
| **protected** | ✅ | ✅ | ✅ | ❌ |
| **public** | ✅ | ✅ | ✅ | ✅ |

# 3. Clases y Métodos `final`
- **Clase `final`**: Evita que otras clases hereden de ella (ej. `String`). Se usa por seguridad e inmutabilidad.
- **Método `final`**: Evita que una subclase lo sobreescriba. Protege algoritmos críticos.



> [!question]- ¿Herencia o Composición?
> Un error común es heredar para "ahorrar líneas". 
> - **Herencia**: Úsala si la subclase es realmente un tipo de la superclase (Un `Gato` es un `Animal`).
> - **Composición**: Úsala si una clase "tiene un" componente (Un `Coche` tiene un `Motor`). La composición es más flexible y menos acoplada.

---

## Resumen

- **Acoplamiento**: La herencia es el vínculo más fuerte en POO; si el padre cambia, el hijo puede romperse.
- **Protección**: Usa `protected` para exponer métodos a tus herederos sin abrirlos al público.
- **Raíz**: En Java, toda clase que no extiende de nada, extiende implícitamente de `Object`.

## Bibliografía
1. Liskov, B. (1987). *Data Abstraction and Hierarchy*.
2. Bloch, J. (2018). *Effective Java*. Item 18: Favor composition over inheritance.