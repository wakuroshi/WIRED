---
materia: Fundamentos de la Electrónica
id: ELE.4.4
tema: Lógica Complementaria CMOS
status: Revision
tags:
  - CMOS
  - digital
  - inversor
  - bajo-consumo
---

# ELE.4.4. Tecnología CMOS

> [!abstract] La unión de dos mundos
> CMOS (Complementary MOS) combina transistores NMOS y PMOS en un mismo circuito. Es la tecnología que permitió que los ordenadores pasaran de ocupar habitaciones a caber en un bolsillo, gracias a su extrema eficiencia energética. Basado en **Tanenbaum (Cap. 3)** y **Floyd (Cap. 13)**.

---

# 1. El Principio de Complementariedad

En CMOS, para cada función lógica, existe una red de transistores **Pull-Up** (PMOS) que conecta a $V_{DD}$ y una red **Pull-Down** (NMOS) que conecta a Tierra.
- **Regla de Oro**: En estado estable, una red está abierta y la otra cerrada. **Nunca fluye corriente de la fuente a tierra**.

# 2. El Inversor CMOS

Es la unidad básica de toda la lógica digital.
- **Entrada '0'**: NMOS apagado, PMOS encendido $\rightarrow$ Salida = $V_{DD}$ ('1').
- **Entrada '1'**: NMOS encendido, PMOS apagado $\rightarrow$ Salida = GND ('0').

# 3. Ventajas para la Computación

1. **Consumo Estático Nulo**: Solo consume energía durante la conmutación (cuando se cargan/descargan las capacidades de puerta).
2. **Márgenes de Ruido**: Muy elevados, lo que permite miniaturizar sin errores.

---

## Resumen
- CMOS = Eficiencia.
- El calor de un procesador moderno se debe casi exclusivamente a la **Potencia Dinámica** (conmutaciones por segundo).

## Bibliografía
[**Tanenbaum** - *Structured Computer Organization*, Cap. 3.]
[**Floyd** - *Sistemas Digitales*, Cap. 13.]