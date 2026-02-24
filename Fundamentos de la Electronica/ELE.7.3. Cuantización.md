---
materia: Fundamentos de la Electrónica
id: ELE.7.3
tema: Cuantización, Resolución y Error de Cuantización
status: Revision
tags:
  - cuantización
  - bits
  - LSB
  - SNR
---

# ELE.7.3. Cuantización: El Mundo en Niveles

> [!abstract] El precio de la digitalización
> Mientras que el muestreo divide el **tiempo**, la cuantización divide el **voltaje**. Un ADC tiene un número finito de estados (bits). Al obligar a una señal infinita a encajar en niveles discretos, cometemos un error matemático inevitable.

---

# 1. El Bit Menos Significativo (LSB)

El LSB representa el voltaje más pequeño que el convertidor puede distinguir. Es el "tamaño del escalón".
$$LSB = \frac{V_{ref}}{2^n}$$
Donde $n$ es el número de bits del ADC y $V_{ref}$ es el voltaje de referencia.
- *Ejemplo:* Un ADC de 10 bits con $V_{ref} = 5\text{V}$ tiene un $LSB = 5 / 1024 \approx 4.88\text{ mV}$.

# 2. El Error de Cuantización ($e_q$)

Dado que el ADC debe asignar un código binario al voltaje de entrada, siempre habrá un redondeo. El error máximo de cuantización es de $\pm 1/2 LSB$.
- Este error se comporta como un ruido blanco añadido a la señal. Se conoce como **Ruido de Cuantización**.



# 3. Relación Señal-Ruido (SNR) ideal

Existe una fórmula mágica en ingeniería para saber cuánta calidad ganamos al añadir bits:
$$SNR_{dB} = 6.02 \cdot n + 1.76$$
- Cada bit adicional que añades al ADC mejora la fidelidad en unos **6 dB**.
- Un ADC de 8 bits tiene ~50 dB de SNR (calidad de radio vieja).
- Un ADC de 16 bits tiene ~98 dB de SNR (calidad de CD).

# 4. Rango Dinámico
Es la proporción entre el valor más grande y el más pequeño que el sistema puede manejar sin distorsión. En un sistema de 24 bits (audio profesional), el rango dinámico es inmenso, permitiendo capturar desde un susurro hasta una explosión sin cambiar la ganancia.

# 5. Dithering (Ruido Intencional)
Parece contraintuitivo, pero a veces los ingenieros añaden un poco de ruido a la señal antes del ADC. Esto ayuda a que el error de cuantización sea aleatorio y no correlacionado, mejorando la percepción de los detalles pequeños en señales de audio y video.

---

## Bibliografía
[**Lyons, R. G.** - *Understanding Digital Signal Processing*.]