---
materia: Fundamentos de la Electrónica
id: ELE.6.3
tema: Latches (Cerrojos) y Realimentación Positiva
status: Revision
tags:
  - latch
  - memoria
  - biestable
  - SR
  - realimentación
---

# ELE.6.3. Latching: El Origen de la Memoria

> [!abstract] El bucle infinito
> Un Latch es la forma más simple de memoria. A diferencia de las compuertas que vimos en la Unidad 4, el Latch usa **realimentación positiva** para "atrapar" un estado eléctrico. Es un dispositivo **sensible al nivel**. Basado en **Floyd (Cap. 7)**.

---

# 1. El Concepto de Biestabilidad

Un circuito biestable tiene dos estados estables (0 y 1). Imagina una pelota en un valle con dos pozos: una vez que cae en uno, se queda ahí hasta que una fuerza externa la saque. En electrónica, esta "fuerza" es la entrada de Set o Reset.

# 2. El Latch S-R (Set-Reset) con Compuertas NOR

Es el diseño clásico. Dos compuertas NOR cruzadas donde la salida de una es la entrada de la otra.

### 2.1. Análisis de Estados
1.  **Estado de Reposo ($S=0, R=0$):** El circuito mantiene el valor que tenía. Si $Q=1$, la realimentación mantiene la entrada de la otra compuerta en 1, forzando a que se mantenga el ciclo.
2.  **Set ($S=1, R=0$):** Fuerza a $Q$ a ser 1.
3.  **Reset ($S=0, R=1$):** Fuerza a $Q$ a ser 0.
4.  **Estado Crítico ($S=1, R=1$):** Es el "Estado Prohibido". Ambas salidas $Q$ y $\bar{Q}$ intentan ser 0. Si ambas entradas vuelven a 0 simultáneamente, el circuito entra en una **condición de carrera** (Race Condition), donde el estado final depende de qué compuerta sea unos picosegundos más rápida. **Inaceptable en computación.**



# 3. El Latch D (Gated D-Latch)

Para solucionar el problema del estado prohibido y controlar *cuándo* se guarda el dato, introducimos la entrada de **Habilitación (Enable)**.

- **Diseño:** Un inversor conecta las entradas S y R de modo que nunca puedan ser iguales.
- **Funcionamiento:**
    - **Enable = 1:** El latch es "transparente". Lo que pongas en $D$ sale por $Q$.
    - **Enable = 0:** El latch se cierra. La salida $Q$ queda congelada en el último valor que tuvo antes de que Enable cayera a 0.

# 4. El Problema de la Transparencia

Aunque el Latch D es útil, tiene un defecto fatal para sistemas de alta velocidad: mientras `Enable` esté en 1, cualquier ruido en la entrada $D$ pasará directo a la salida. Si tienes una cadena de latches, el dato puede "escaparse" a través de varios de ellos en un solo ciclo de reloj. Esto nos obliga a inventar el **Flip-Flop**.

---

## Comparativa Técnica
| Dispositivo | Activación | Comportamiento |
| :--- | :--- | :--- |
| **Compuerta** | Inmediata | No tiene memoria. |
| **Latch** | Nivel (Alto/Bajo) | Transparente mientras está activo. |
| **Flip-Flop** | Flanco ($\uparrow$ / $\downarrow$) | Captura instantánea, bloqueado el resto del tiempo. |

## Bibliografía
[**Floyd, T. L.** - *Fundamentos de Sistemas Digitales*, Cap. 7: Latches, biestables y temporizadores.]