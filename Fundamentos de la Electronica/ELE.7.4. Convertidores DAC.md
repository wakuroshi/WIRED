---
materia: Fundamentos de la Electrónica
id: ELE.7.4
tema: DAC Red de Resistencias Pesadas y R-2R
status: Revision
tags:
  - DAC
  - R-2R
  - sumador
  - binario
---

# ELE.7.4. DAC: Reconstruyendo el Voltaje

> [!abstract] Sumando potencias de dos
> Un DAC toma un código binario de $n$ bits y genera un voltaje proporcional. Es esencialmente un sistema de suma ponderada. Veremos por qué la red R-2R es la reina de la industria.

---

# 1. DAC de Pesos Binarios (Weighted Resistor)

Es el concepto más intuitivo. Usamos un amplificador operacional en configuración sumadora.
- Cada bit controla un interruptor que conecta una resistencia al operacional.
- Las resistencias tienen valores de $R, 2R, 4R, 8R \dots 2^n R$.
- **Problema:** Para un DAC de 16 bits, la resistencia más grande sería 32,768 veces mayor que la pequeña. Es imposible fabricar resistencias tan precisas en un chip. Por eso, este diseño **casi nunca se usa**.

# 2. La Escalera R-2R (El Estándar)

Este diseño es brillante porque **solo utiliza dos valores de resistencia**: $R$ y $2R$ (usualmente $10\text{k}\Omega$ y $20\text{k}\Omega$).
- **Ventaja:** Es muy fácil fabricar dos resistencias iguales en silicio.
- **Funcionamiento:** Basado en el teorema de Thevenin, la red divide el voltaje de referencia sucesivamente en cada nodo. Cada bit decide si su parte del voltaje se suma a la salida o se deriva a tierra.



# 3. Especificaciones del DAC

1.  **Settling Time (Tiempo de establecimiento):** Cuánto tarda la salida en estabilizarse tras un cambio de bits. Dicta la velocidad máxima (muestras por segundo).
2.  **Glitches:** Durante el cambio de un código a otro (ej. de 0111 a 1000), los interruptores físicos no cambian a la vez. Esto genera picos de voltaje momentáneos que deben filtrarse.
3.  **Monotonicidad:** Un DAC es monotónico si al aumentar el código binario, el voltaje siempre sube (nunca baja por error de fabricación).

# 4. Aplicaciones
- Tarjetas de sonido.
- Generadores de funciones.
- Control de intensidad de LEDs y motores.

---

## Bibliografía
[**Mano, M. M.** - *Diseño Digital*, Cap. 10.]
[**Floyd, T. L.** - *Fundamentos de Sistemas Digitales*, Cap. 12.]