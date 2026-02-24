---
materia: Fundamentos de la Electrónica
id: ELE.6.7
tema: Flip-Flops JK, T y División de Frecuencia
status: Revision
tags:
  - JK
  - FF-T
  - toggle
  - contador
  - divisor
---

# ELE.6.5. Flip-Flops JK y T: Los Motores del Conteo

> [!abstract] Versatilidad pura
> Mientras el FF-D es para almacenar, el JK y el T son para **actuar**. Su capacidad de invertir su estado (Toggle) los hace indispensables para crear relojes, temporizadores y contadores binarios. Basado en **Floyd (Cap. 7)**.

---

# 1. El Flip-Flop JK: El "Todo Terreno"

El JK se inventó para solucionar el estado inválido del SR. Si pones ambas entradas en 1, el circuito simplemente cambia de estado.

### 1.1. Tabla de Verdad (Síncrona)
| J | K | CLK | $Q_{next}$ | Descripción |
| :---: | :---: | :---: | :---: | :--- |
| 0 | 0 | $\uparrow$ | $Q$ | Memoria (No cambio) |
| 0 | 1 | $\uparrow$ | 0 | Reset |
| 1 | 0 | $\uparrow$ | 1 | Set |
| 1 | 1 | $\uparrow$ | $\bar{Q}$ | **Toggle** (Inversión) |

# 2. El Flip-Flop T (Toggle)

Es una simplificación del JK donde las entradas $J$ y $K$ están unidas en una sola entrada $T$.
- **Si $T=0$:** Mantiene estado.
- **Si $T=1$:** Invierte estado en cada pulso.

### 2.1. Aplicación: Divisor de Frecuencia
Si dejas $T=1$ fijo y aplicas un reloj de 1 GHz:
- La salida $Q$ estará en 1 durante un ciclo y en 0 durante el siguiente.
- El ciclo completo de $Q$ dura el doble que el del reloj.
- **Resultado:** La frecuencia de salida es **la mitad** de la entrada ($f_{out} = f_{in}/2$).
- *Ingeniería:* Así es como tu PC genera los 100 MHz del bus del sistema a partir del cristal principal de varios GHz.



# 3. Diseño de Contadores

Un contador de 3 bits (0 a 7) se construye con 3 Flip-Flops. 
- **Contador Asíncrono (Ripple):** La salida $Q$ del primero es el reloj del segundo. Es fácil de hacer pero tiene mucho retraso.
- **Contador Síncrono:** Todos comparten el reloj. Usamos lógica AND en las entradas $T$ para que un bit solo cambie si todos los anteriores son 1.
    - Ejemplo: El Bit 2 solo hace "Toggle" si Bit 0 y Bit 1 están en 1 (estado 011 -> 100).

# 4. Tablas de Excitación

Cuando diseñamos una **FSM (Máquina de Estados)**, necesitamos saber qué poner en J y K para lograr un cambio específico. Esta tabla es la biblia del diseñador digital:

| Transición ($Q \to Q_{next}$) | J | K |
| :---: | :---: | :---: |
| $0 \to 0$ | 0 | X (Don't care) |
| $0 \to 1$ | 1 | X |
| $1 \to 0$ | X | 1 |
| $1 \to 1$ | X | 0 |

---

## Resumen Técnico
- El FF-JK es universal: puede ser SR, D o T.
- El modo Toggle es la base de la aritmética de conteo y la división de reloj.

## Bibliografía
[**M. Morris Mano** - *Diseño Digital*, Cap. 6.]
[**Floyd, T. L.** - *Fundamentos de Sistemas Digitales*, Cap. 8.]