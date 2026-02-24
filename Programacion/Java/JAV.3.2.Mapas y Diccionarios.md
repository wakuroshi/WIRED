---
materia: Programación Java
id: JAV.3.2
tema: Mapas, Tablas de Hash y Gestión de Colisiones
status: Revision
tags:
  - java
  - map
  - hashmap
  - treemap
  - hashtable
---

# JAV.3.2. Mapas y Diccionarios

> [!abstract]- Estructuras Clave-Valor
> Un `Map` representa una estructura asociativa donde cada clave es única y mapea exactamente a un valor. No hereda de `Collection`, pero es una de las estructuras más potentes para indexación y cachés en memoria.

# 1. Arquitectura del `HashMap`

Es la implementación más común. Utiliza una **Tabla de Hash** interna para organizar los datos en "buckets" (cubetas).

## 1.1. Gestión de Colisiones
Cuando dos claves distintas generan el mismo código hash:
1. Java almacena ambos en una **Lista Enlazada** dentro del mismo bucket.
2. Si el bucket crece demasiado (>8 elementos), Java lo transforma automáticamente en un **Árbol Rojo-Negro** para mantener la búsqueda en $O(\log n)$.



# 2. Implementaciones Principales

| Clase | Orden | Complejidad | Uso Ideal |
| :--- | :--- | :--- | :--- |
| **HashMap** | Ninguno | $O(1)$ | Máximo rendimiento. |
| **TreeMap** | Natural/Comparator | $O(\log n)$ | Cuando los datos deben estar ordenados. |
| **LinkedHashMap** | Inserción | $O(1)$ | Implementación de cachés LRU. |

# 3. Ejemplo Práctico de Ingeniería
```java
HashMap<String, Integer> inventario = new HashMap<>();
inventario.put("Resistencia 1k", 500);
inventario.put("Capacitor 10uF", 200);

// Acceso instantáneo por clave
int stock = inventario.get("Resistencia 1k"); // O(1)
```

> [!question]- Inmutabilidad en Claves
> Es una regla de oro usar clases inmutables (como `String` o `Integer`) como claves de un Mapa. Si usas un objeto cuya propiedad cambie después de insertarlo, su `hashCode` cambiará y el objeto se "perderá" dentro del mapa, provocando fugas de memoria.

---

## Resumen

- **Eficiencia**: Los Mapas permiten evitar búsquedas lineales, transformando procesos lentos en operaciones de tiempo constante.
- **Nulls**: `HashMap` permite una clave nula, mientras que `TreeMap` lanzará una excepción si el comparador no lo permite.
- **Iteración**: Para recorrer un mapa de forma eficiente, usa `map.entrySet()` en lugar de iterar por las llaves y luego hacer `get()`.

## Bibliografía
1. Schildt, H. (2022). *Java: The Complete Reference*. McGraw Hill.
2. Goetz, B. (2006). *Java Concurrency in Practice*. (Sección de ConcurrentHashMap).