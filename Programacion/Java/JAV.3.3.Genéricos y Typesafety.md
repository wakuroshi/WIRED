---
materia: Programación Java
id: JAV.3.3
tema: Programación Genérica y Seguridad de Tipos
status: Revision
tags:
  - java
  - generics
  - typesafety
  - abstraction
---

# JAV.3.3. Genéricos y Typesafety

> [!abstract]- Abstracción de Tipos
> Los genéricos permiten que las clases y métodos operen sobre tipos de datos especificados por el programador al momento de la instanciación. Su objetivo principal es garantizar la **seguridad de tipos en tiempo de compilación**, eliminando la necesidad de castings manuales y previniendo errores de `ClassCastException`.

# 1. El Diamante de Tipos (`<>`)

Antes de Java 5, las colecciones guardaban tipos `Object`, lo que obligaba a hacer conversiones arriesgadas.

```java
// Con Genéricos: El compilador sabe que solo hay Strings
List<String> nombres = new ArrayList<>();
nombres.add("Java");
String s = nombres.get(0); // Sin casting manual
```

# 2. Borrado de Tipos (Type Erasure)
Es fundamental entender que los genéricos solo existen para el programador y el compilador.
1. El compilador verifica que los tipos coincidan.
2. Luego, **borra** los tipos genéricos y los reemplaza por `Object` para mantener compatibilidad con versiones antiguas.
3. Por esto, no puedes crear una instancia de un tipo genérico: `new T()` es ilegal.



# 3. Wildcards (Comodines)
Permiten una flexibilidad mayor en el manejo de jerarquías dentro de colecciones:
- **`<? extends T>`**: Acepta T o cualquier subclase de T (Covarianza - Lectura).
- **`<? super T>`**: Acepta T o cualquier superclase de T (Contravarianza - Escritura).

---

## Resumen

- **Seguridad**: Los genéricos trasladan los errores del tiempo de ejecución al tiempo de compilación.
- **Reutilización**: Permiten escribir algoritmos (como ordenamiento) que funcionan para cualquier tipo de dato sin duplicar código.
- **Legibilidad**: Un código genérico es más fácil de leer al explicitar qué contenido se espera en cada estructura.

## Bibliografía
1. Bloch, J. (2018). *Effective Java*. Items 26-33 sobre Genéricos.
2. Naftalin, M., & Wadler, P. (2006). *Java Generics and Collections*. O'Reilly.