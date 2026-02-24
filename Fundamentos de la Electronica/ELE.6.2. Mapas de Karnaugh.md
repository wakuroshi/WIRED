---
materia: Fundamentos de la Electrónica
id: ELE.6.2
tema: Simplificación de Funciones Mediante Mapas de Karnaugh
status: Revision
tags:
  - Karnaugh
  - K-Map
  - Gray
  - simplificación
  - lógica
---

# ELE.6.2. Mapas de Karnaugh: Simplificación Extrema

> [!abstract] Optimizando el Silicio
> Minimizar una función booleana no es un ejercicio estético; es una necesidad económica. Menos compuertas significan menos área de silicio, menor consumo de energía y menor retardo de propagación ($t_{pd}$). El Mapa de Karnaugh (K-Map) es el método visual por excelencia para lograrlo. Basado en **Maurice Karnaugh (1953)**.

---

# 1. El Código Gray: La base del K-Map

Un K-Map no usa binario estándar. Usa **Código Gray**, donde entre una celda y su vecina solo cambia **un bit**.
- Orden para 2 variables: `00, 01, 11, 10`.
- **¿Por qué?** Si dos celdas adyacentes tienen un '1', y solo cambia una variable (ej. de $A\bar{B}$ a $AB$), esa variable ($B$) se puede eliminar mediante el postulado $A(B + \bar{B}) = A \cdot 1 = A$.

# 2. Reglas de Agrupamiento (Cruciales)

Para que la simplificación sea válida y óptima, se deben seguir estas leyes:
1.  **Potencias de 2:** Los grupos deben contener $1, 2, 4, 8$ o $16$ celdas. No se permiten grupos de 3 o 6.
2.  **Celdas Adyacentes:** Los grupos deben ser rectángulos o cuadrados.
3.  **Maximización:** Un grupo de 4 celdas elimina dos variables. Uno de 8 elimina tres. Siempre hay que buscar el grupo más grande posible.
4.  **Cobertura Total:** Todos los '1' deben estar en al menos un grupo.
5.  **Adyacencia Cilíndrica:** El mapa se "envuelve". La columna de la extrema izquierda es adyacente a la de la derecha. Las esquinas son adyacentes entre sí.


# 3. Implicantes Primos y Esenciales

- **Implicante Primo:** Un grupo que no puede ser contenido dentro de otro grupo más grande.
- **Implicante Primo Esencial:** Un grupo que contiene al menos un '1' que no está cubierto por ningún otro implicante primo. **Estos deben aparecer obligatoriamente en la función simplificada.**

# 4. Condiciones "Don't Care" (X)

En muchos sistemas de computación, hay combinaciones de entrada que son físicamente imposibles.
- *Ejemplo:* En un decodificador BCD (Binary Coded Decimal), las entradas 1010 a 1111 (10 al 15) nunca ocurrirán.
- **Estrategia:** En el K-Map, estas se marcan con una 'X'. 
    - Si la 'X' ayuda a expandir un grupo de 4 a 8, la tratamos como un '1'.
    - Si no ayuda a simplificar, la ignoramos como si fuera un '0'.

# 5. Mapas de 5 y 6 Variables

Cuando el número de variables crece, el mapa se vuelve tridimensional.
- Para 5 variables, usamos dos mapas de 4 variables "superpuestos". Un grupo puede formarse entre celdas que ocupan la misma posición en ambos mapas.

# 6. Implementación Universal (NAND-NAND)

Una vez obtenida la suma de productos (SOP) del mapa:
- Paso 1: Implementar con compuertas AND y una OR al final.
- Paso 2: Aplicar De Morgan.
- Resultado: El circuito se convierte en dos niveles de compuertas NAND. Esto es el estándar en la industria CMOS porque las NAND son más pequeñas y rápidas que las AND u OR.

---

## Bibliografía
[**M. Morris Mano** - *Diseño Digital*, Cap. 3: Simplificación a nivel de compuertas.]
[**Floyd, T. L.** - *Fundamentos de Sistemas Digitales*, Cap. 4.]