---
materia: Fundamentos de la Electrónica
id: ELE.5.1
tema: Implementación de Compuertas Lógicas con Transistores
status: Revision
tags:
  - RTL
  - CMOS
  - lógica-digital
  - compuertas
  - transistores
---

# ELE.5.1. Compuertas Lógicas con Transistores

> [!abstract] Del interruptor a la decisión
> Una compuerta lógica es un circuito que implementa una función booleana. En esta lección veremos cómo la disposición física de los transistores (en serie o paralelo) dicta la lógica del sistema. Basado en **Tanenbaum (Cap. 3)** y **Mano (Cap. 10)**.

---

# 1. Lógica de Resistencia-Transistor (RTL)

Es la forma más sencilla de entender una compuerta. Usamos un BJT como interruptor.

### 1.1. Inversor (NOT) con BJT
- **Configuración**: El emisor a tierra, la salida en el colector.
- **Lógica**: 
  - Si Entrada = 0V ($V_B < 0.7V$): El transistor está en **Corte**. La salida "flota" hasta $V_{CC}$ a través de la resistencia. (0 produce 1).
  - Si Entrada = 5V ($V_B > 0.7V$): El transistor se **Satura**. El colector se conecta a tierra. (1 produce 0).

### 1.2. Compuerta NOR (Paralelo)
Si colocamos dos transistores en paralelo compartiendo la misma resistencia de colector:
- Si **cualquier** entrada es 1, la salida se va a tierra (0). Solo es 1 si ambos son 0.



# 2. Lógica CMOS (El estándar actual)

Como vimos brevemente, CMOS no usa resistencias, usa pares NMOS y PMOS. Esto evita el desperdicio de energía en calor.

- **Compuerta NAND CMOS**: 
  - Los NMOS están en **serie** (ambos deben conducir para llevar la salida a 0).
  - Los PMOS están en **paralelo** (si cualquiera es 0, suben la salida a 1).
- **Compuerta NOR CMOS**: 
  - Los NMOS están en **paralelo**.
  - Los PMOS están en **serie**.



---

## Resumen
- **Serie = AND**: Se requiere que todos los "interruptores" cierren el paso.
- **Paralelo = OR**: Con que uno cierre, hay flujo.
- El silicio procesa información mediante la topología de sus conexiones.

## Bibliografía
[**Tanenbaum, A. S.** - *Structured Computer Organization*, Cap. 3.]
[**M. Morris Mano** - *Diseño Digital*, Cap. 10: Circuitos Integrados Digitales.]