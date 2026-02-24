---
materia: Fundamentos de la Electrónica
id: ELE.2.1
tema: Fasores y Dominio Frecuencial
status: Revision
tags:
  - AC
  - fasores
  - frecuencia
  - señales
---

# ELE.2.1. Fasores y Dominio Frecuencial

> [!abstract]- La simplificación del análisis temporal
> En el análisis de circuitos de corriente alterna (CA), las señales varían senoidalmente con el tiempo. Resolver circuitos usando ecuaciones diferenciales e integrales en el dominio del tiempo es extremadamente complejo. El método de los **fasores** nos permite transformar estas ecuaciones en expresiones algebraicas lineales mediante el uso de números complejos, simplificando radicalmente el diseño y análisis de sistemas lineales.

---

# 1. Naturaleza de la Señal Senoidal

Una señal de tensión o corriente alterna se define matemáticamente como una función del tiempo:
$$v(t) = V_m \cos(\omega t + \phi)$$

Donde los parámetros fundamentales son:
1.  **Amplitud Máxima ($V_m$):** El valor pico de la señal.
2.  **Frecuencia Angular ($\omega$):** Velocidad de rotación en rad/s ($\omega = 2\pi f$). Determina qué tan rápido oscila la señal.
3.  **Fase ($\phi$):** El desplazamiento angular en el instante $t=0$. Es crucial para determinar adelantos o retrasos entre señales.
4.  **Valor Eficaz ($V_{rms}$):** El valor equivalente en DC que disiparía la misma energía. Para senos: $V_{rms} = V_m / \sqrt{2}$.

# 2. Transformación Fasorial

El concepto de fasor se basa en la **Identidad de Euler**:
$$e^{\pm j\theta} = \cos \theta \pm j \sin \theta$$

Considerando que $v(t) = \text{Re}\{V_m e^{j(\omega t + \phi)}\}$, el fasor $\mathbf{V}$ es la parte compleja que es independiente del tiempo:
$$\mathbf{V} = V_m e^{j\phi} = V_m \angle \phi$$

### 2.1. Ventajas del Dominio Frecuencial
Al trabajar con fasores, las operaciones de cálculo se simplifican:
* **Derivación en el tiempo:** Se convierte en una multiplicación por $j\omega$.
    $$\frac{dv(t)}{dt} \rightarrow j\omega \mathbf{V}$$
* **Integración en el tiempo:** Se convierte en una división por $j\omega$.
    $$\int v(t) dt \rightarrow \frac{\mathbf{V}}{j\omega}$$



# 3. Relaciones de Fase y Diagramas Fasoriales

El diagrama fasorial es una representación en el plano complejo donde los vectores rotan a una velocidad $\omega$. 
- Si dos señales tienen la misma frecuencia, su posición relativa (ángulo entre ellas) permanece constante.
- **Adelanto:** Una señal está en adelanto si su ángulo de fase es mayor (está más "adelante" en la rotación antihoraria).
- **Retraso:** Si su ángulo es menor.

### 3.1. Operaciones con Números Complejos
Para ingeniería, es vital dominar ambas formas:
1.  **Forma Rectangular ($a + jb$):** Indispensable para sumar y restar (Leyes de Kirchhoff).
2.  **Forma Polar ($A \angle \theta$):** Indispensable para multiplicar y dividir (Ley de Ohm).

$$\mathbf{Z}_1 \cdot \mathbf{Z}_2 = (A_1 \cdot A_2) \angle (\theta_1 + \theta_2)$$
$$\frac{\mathbf{Z}_1}{\mathbf{Z}_2} = \left(\frac{A_1}{A_2}\right) \angle (\theta_1 - \theta_2)$$

---

## Resumen
- El análisis fasorial transforma EDOs en álgebra.
- Solo es aplicable a circuitos **lineales** en **estado estacionario**.
- La frecuencia $\omega$ debe ser constante en todo el análisis.

> [!Exercise] Conversión de dominio
> Dada la corriente $i(t) = 10 \sin(377t - 20^\circ)$ A, exprésela como fasor en forma de coseno.
> 
> **Respuesta**: $\mathbf{I} = 10 \angle -110^\circ$ A.
> **Explicación paso a paso**:
> 1. Pasamos de seno a coseno: $\sin(x) = \cos(x - 90^\circ)$.
> 2. $i(t) = 10 \cos(377t - 20^\circ - 90^\circ) = 10 \cos(377t - 110^\circ)$.
> 3. El fasor toma la amplitud y la fase: $\mathbf{I} = 10 \angle -110^\circ$.

> [!Example] Aplicación en Computación: Jitter y Ruido de Reloj
> En sistemas digitales, el "reloj" es una señal cuadrada. Mediante el análisis de Fourier, sabemos que una señal cuadrada es la suma de infinitos fasores (armónicos). Si los fasores de alta frecuencia se desfasan de forma no lineal al viajar por una pista de la placa base (dispersión), el flanco de subida del reloj se deforma (jitter), provocando errores de sincronización en la CPU.

## Bibliografía
[**Fraile Mora, J.** - *Circuitos Eléctricos*, Cap. 6.]
[**Sedra & Smith** - *Circuitos Microelectrónicos*, Apéndice F.]