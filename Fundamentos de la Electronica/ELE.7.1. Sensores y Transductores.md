---
materia: Fundamentos de la Electrónica
id: ELE.7.1
tema: Sensores, Transductores y Caracterización de Señales
status: Revision
tags:
  - sensores
  - sensibilidad
  - linealidad
  - transductores
---

# ELE.7.1. Sensores: Traduciendo la Naturaleza

> [!abstract] Del átomo al bit
> Un sensor es un dispositivo que detecta una magnitud física (temperatura, presión, luz) y la convierte en una señal eléctrica (voltaje o corriente). Sin ellos, una CPU sería un cerebro en un frasco sin sentidos. Basado en **Pallás Areny** y **Doebelin**.

---

# 1. Definiciones Fundamentales

Es común confundir términos, pero en ingeniería somos precisos:
- **Transductor:** Dispositivo que convierte una forma de energía en otra (ej. presión a voltaje).
- **Sensor:** El elemento sensible que detecta la variación.
- **Actuador:** Lo contrario al sensor; convierte una señal eléctrica en una acción física (un motor, un LED).

# 2. Parámetros Estáticos (Lo que define la calidad)

Cuando eliges un sensor para un proyecto, estos son los números que importan:

### 2.1. Sensibilidad ($S$)
Es la pendiente de la curva de transferencia. Indica cuánto cambia la salida por cada unidad de entrada.
$$S = \frac{\Delta V_{out}}{\Delta Magnitud_{in}}$$
*Ejemplo:* Un sensor de temperatura con $10\text{ mV/°C}$ es más sensible que uno de $1\text{ mV/°C}$.

### 2.2. Linealidad
Un sensor ideal es una línea recta ($y = mx + b$). En la realidad, todos tienen una curva. La no-linealidad se mide como la desviación máxima respecto a la recta ideal. Si no es lineal, la CPU tendrá que hacer cálculos complejos (polinomios) para corregir el dato.

### 2.3. Rango y Alcance (Span)
- **Rango:** Los valores mínimos y máximos de entrada (ej. $-40\text{°C}$ a $+125\text{°C}$).
- **Alcance:** La diferencia entre ellos ($165\text{°C}$).

### 2.4. Resolución
El cambio más pequeño en la magnitud física que el sensor es capaz de detectar. Está íntimamente ligado al ruido eléctrico del sistema.

# 3. Tipos de Sensores Comunes

1.  **Termopares:** Basados en el efecto Seebeck (unión de dos metales distintos). Muy resistentes pero con voltajes de salida diminutos ($\mu V$).
2.  **RTD (PT100):** Resistencias que cambian con el calor. Muy precisas.
3.  **LVDT:** Transformador diferencial para medir desplazamientos lineales con precisión de micras.
4.  **Efecto Hall:** Detectan campos magnéticos. Se usan para medir revoluciones (RPM) en motores sin contacto físico.
5.  **Galgas Extensiométricas:** Resistencias que cambian cuando se estiran. Base de todas las balanzas digitales.



# 4. Acondicionamiento de Señal

La salida de un sensor suele ser "fea": pequeña, con ruido y con un offset. Antes de llegar al ADC, necesitamos:
1.  **Amplificación:** Usualmente con Amplificadores de Instrumentación (In-Amp) para elevar los $mV$ a voltajes de $0-5\text{V}$.
2.  **Filtrado:** Eliminar el ruido de alta frecuencia o el zumbido de $50/60\text{ Hz}$ de la red eléctrica.
3.  **Linealización:** Circuitos analógicos que compensan la curvatura natural del sensor.

---

## Resumen Técnico
- La sensibilidad dicta la ganancia necesaria en el amplificador.
- Sin un buen acondicionamiento, el ADC solo digitalizará ruido.

## Bibliografía
[**Pallás Areny, R.** - *Sensores y Acondicionadores de Señal*.]
[**Doebelin, E. O.** - *Sistemas de Medición*.]