---
materia: Programación Java
id: JAV.4.1
tema: Excepciones y Robustez del Software
status: Revision
tags:
  - java
  - exceptions
  - error-handling
  - try-catch
---

# JAV.4.1. Manejo de Excepciones

> [!abstract]- Tolerancia a fallos en Ingeniería
> Una excepción es un evento que interrumpe el flujo normal de las instrucciones del programa. En lugar de permitir que la aplicación colapse, Java proporciona un mecanismo para capturar el error, procesarlo y permitir que el sistema se recupere o finalice de forma controlada.

# 1. Jerarquía de Throwable

Todos los objetos de error heredan de la clase `Throwable`. Se dividen en dos ramas principales:

1.  **Error:** Problemas críticos de la JVM (ej. `StackOverflowError`, `OutOfMemoryError`). El programador no debe intentar capturarlos.
2.  **Exception:** Eventos que la aplicación puede manejar.
    * **Checked (Verificadas):** El compilador te obliga a manejarlas (ej. `IOException`, `SQLException`).
    * **Unchecked (Runtime):** Errores de lógica del programador (ej. `NullPointerException`, `ArithmeticException`).



# 2. Bloque Try-Catch-Finally

Es la estructura fundamental para el control de errores.

```java
try {
    int resultado = 10 / 0; // Provoca ArithmeticException
} catch (ArithmeticException e) {
    System.err.println("Error matemático: " + e.getMessage());
} finally {
    // Este bloque se ejecuta SIEMPRE, haya error o no.
    // Ideal para cerrar conexiones o archivos.
    System.out.println("Limpieza de recursos finalizada.");
}
```

# 3. Lanzamiento de Excepciones (`throw` y `throws`)

- **`throw`**: Se usa para disparar una excepción manualmente.
- **`throws`**: Se usa en la firma del método para advertir que dicho método puede generar una excepción que debe ser manejada por quien lo llame.

> [!question]- Buenas Prácticas
> **¿Capturar o lanzar?** Solo captura una excepción si realmente puedes hacer algo para solucionar el problema (ej. pedir el dato de nuevo). Si no puedes hacer nada, usa `throws` para delegar la responsabilidad a la capa superior.

---

## Resumen

- **Robustez**: Un software de calidad es aquel que maneja casos de borde y errores inesperados sin cerrarse.
- **Especificidad**: Captura siempre la excepción más específica posible antes que la genérica (`Exception`).
- **Recursos**: Siempre que abras un flujo (archivo/red), asegúrate de cerrarlo en un bloque `finally`.

## Bibliografía
1. Bloch, J. (2018). *Effective Java*. (Capítulo: Exceptions).
2. Oracle. (2024). *The Java Tutorials: Exceptions*.
