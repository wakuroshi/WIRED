---
materia: Fundamentos de la Electrónica
id: ELE.6.1
tema: Operaciones Binarias, Álgebra de Boole y Aritmética Lógica
status: Revision
tags:
  - binario
  - boole
  - De Morgan
  - aritmética
  - bits
  - XOR
  - ALU
---

# ELE.6.1. Operaciones con Bits y Álgebra de Boole

> [!abstract] La arquitectura del pensamiento binario
> Todo lo que sucede en una CPU, desde un renderizado 3D hasta una consulta a base de datos, se reduce a la manipulación de estados lógicos. En esta sección analizamos las leyes que permiten que el hardware realice operaciones matemáticas complejas mediante compuertas simples. Basado en **M. Morris Mano (Cap. 2)** y **Claude Shannon (1938)**.

---

# 1. El Legado de Boole y Shannon

El álgebra de Boole no se diseñó para computadoras, sino para la lógica filosófica. Fue Claude Shannon quien, en su tesis de maestría, demostró que los relés (y luego los transistores) podían implementar estas funciones.

### 1.1. Postulados Fundamentales
Para simplificar circuitos, debemos dominar estos axiomas:
- **Leyes de Identidad:** $A + 0 = A$; $A \cdot 1 = A$. El 0 es el neutro de la suma (OR) y el 1 del producto (AND).
- **Leyes de Nulidad:** $A + 1 = 1$; $A \cdot 0 = 0$. El 1 "domina" la OR y el 0 "domina" la AND.
- **Leyes de Idempotencia:** $A + A = A$; $A \cdot A = A$. En binario, no existen los exponentes ni los coeficientes.
- **Ley de Complemento:** $A + \bar{A} = 1$; $A \cdot \bar{A} = 0$. Una variable o su opuesto siempre cubren el universo de posibilidades.

### 1.2. Teoremas de De Morgan: La Piedra Angular
Estos teoremas son vitales porque permiten a los fabricantes usar un solo tipo de compuerta (NAND o NOR) para todo:
1.  **$\overline{A \cdot B} = \bar{A} + \bar{B}$**: "La negación de un producto es la suma de las negaciones".
2.  **$\overline{A + B} = \bar{A} \cdot \bar{B}$**: "La negación de una suma es el producto de las negaciones".
*Aplicación:* Permite convertir lógica positiva en lógica negativa y viceversa, optimizando el layout del chip.

# 2. Operaciones de Bit (Bitwise Operations)

En la programación de bajo nivel (C, Assembly), operamos directamente sobre los registros:
- **AND ($\&$):** Se usa como **máscara**. Para apagar bits específicos de un registro sin tocar los demás.
- **OR ($|$):** Se usa para **encender** bits.
- **XOR ($\wedge$):** El "comparador de desigualdad". Es 1 si los bits son distintos.
    - *Truco de Ingeniería:* `A XOR A = 0`. Es la forma más rápida en una CPU de limpiar un registro.
- **NOT ($\sim$):** Inversión total (Complemento a 1).

# 3. Aritmética Binaria y la ALU

¿Cómo suma una computadora? No "sabe" sumar, solo sabe aplicar lógica.

### 3.1. El Medio Sumador (Half-Adder)
Suma dos bits ($A, B$):
- **Suma ($S$):** $A \oplus B$ (XOR).
- **Acarreo ($C$):** $A \cdot B$ (AND).


[Image of a Half Adder logic circuit diagram]


### 3.2. Sumador Completo (Full-Adder)
Incluye el acarreo de entrada ($C_{in}$):
$$S = A \oplus B \oplus C_{in}$$
$$C_{out} = (A \cdot B) + (C_{in} \cdot (A \oplus B))$$

### 3.3. Resta mediante Complemento a 2
Para no fabricar un "restador" físico, usamos el sumador:
1.  Invertimos el sustraendo (NOT).
2.  Le sumamos 1 (Complemento a 2).
3.  Sumamos el resultado al minuendo.
- **Fórmula:** $A - B = A + (\bar{B} + 1)$.

# 4. Formas Canónicas: SOP y POS

Antes de minimizar, una función se expresa en su forma "cruda":
- **Suma de Productos (SOP - Minterminos):** Buscamos las filas de la tabla de verdad donde la salida es 1.
- **Producto de Sumas (POS - Maxterminos):** Buscamos las filas donde la salida es 0.
*Nota:* En ingeniería se prefiere **SOP** porque mapea directamente a compuertas NAND-NAND, que son las más rápidas en silicio.

---

## Resumen Técnico
- El álgebra de Boole permite convertir tablas de verdad en ecuaciones.
- De Morgan es la herramienta para la universalidad de compuertas.
- La aritmética es una extensión de la lógica combinacional.

## Bibliografía
[**M. Morris Mano** - *Diseño Digital*, Cap. 2.]
[**Floyd, T. L.** - *Fundamentos de Sistemas Digitales*, Cap. 4.]