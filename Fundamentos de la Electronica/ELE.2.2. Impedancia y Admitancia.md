---
materia: Fundamentos de la Electrónica
id: ELE.2.2
tema: Impedancia y Admitancia
status: Revision
tags:
  - AC
  - impedancia
  - reactancia
  - filtros
---

# ELE.2.2. Impedancia y Admitancia Compleja

> [!abstract]- La oposición al flujo en CA
> En corriente continua, solo la resistencia se opone al flujo. En corriente alterna, los campos eléctricos y magnéticos reaccionan contra los cambios de la señal, creando una oposición adicional denominada **reactancia**. La combinación de resistencia y reactancia forma la **impedancia**, una magnitud compleja que define totalmente el comportamiento de un componente en el dominio de la frecuencia.

---

# 1. El concepto de Impedancia ($\mathbf{Z}$)

La impedancia es la relación entre el fasor tensión y el fasor corriente:
$$\mathbf{Z} = \frac{\mathbf{V}}{\mathbf{I}}$$
Se mide en Ohmios ($\Omega$) y se compone de:
$$\mathbf{Z} = R + jX$$
- **$R$ (Resistencia):** Parte real. Disipa energía en forma de calor.
- **$X$ (Reactancia):** Parte imaginaria. Almacena y devuelve energía a la red.

# 2. Comportamiento de los Elementos Ideales

### 2.1. Resistencia Pura
En una resistencia, la tensión y la corriente están **en fase** ($\phi = 0^\circ$).
$$\mathbf{Z}_R = R \angle 0^\circ = R$$

### 2.2. Inductor Ideal (Bobina)
La tensión **adelanta** a la corriente $90^\circ$. La oposición crece proporcionalmente con la frecuencia.
$$\mathbf{Z}_L = j\omega L = \omega L \angle 90^\circ$$
* **Baja frecuencia ($\omega \to 0$):** Se comporta como un **cortocircuito**.
* **Alta frecuencia ($\omega \to \infty$):** Se comporta como un **circuito abierto**.

### 2.3. Capacitor Ideal (Condensador)
La corriente **adelanta** a la tensión $90^\circ$. La oposición decrece con la frecuencia.
$$\mathbf{Z}_C = \frac{1}{j\omega C} = -j\frac{1}{\omega C} = \frac{1}{\omega C} \angle -90^\circ$$
* **Baja frecuencia ($\omega \to 0$):** Se comporta como un **circuito abierto** (bloquea DC).
* **Alta frecuencia ($\omega \to \infty$):** Se comporta como un **cortocircuito**.



# 3. Admitancia ($\mathbf{Y}$)

Es el inverso de la impedancia, extremadamente útil para analizar nodos y ramas en paralelo:
$$\mathbf{Y} = \frac{1}{\mathbf{Z}} = G + jB$$
- **$G$ (Conductancia):** Facilidad para disipar energía.
- **$B$ (Susceptancia):** Facilidad para permitir el paso de corriente alterna debido a campos.

# 4. Leyes de Ohm y Kirchhoff en AC

Gracias a la impedancia, las leyes aprendidas en la Unidad 1 siguen siendo válidas:
1.  **Ley de Ohm:** $\mathbf{V} = \mathbf{I} \cdot \mathbf{Z}$.
2.  **Asociación en Serie:** $\mathbf{Z}_{eq} = \sum \mathbf{Z}_i$.
3.  **Asociación en Paralelo:** $\frac{1}{\mathbf{Z}_{eq}} = \sum \frac{1}{\mathbf{Z}_i}$.

> [!Note] Análisis de circuitos mixtos
> Al operar con impedancias, el resultado suele ser un número complejo cuya fase nos indica inmediatamente si el circuito global se comporta de forma inductiva ($\theta > 0$) o capacitiva ($\theta < 0$).

---

## Resumen
- **Resistencia**: No depende de $\omega$. Fase $0^\circ$.
- **Inductancia**: Oposición sube con $\omega$. Fase $+90^\circ$.
- **Capacitancia**: Oposición baja con $\omega$. Fase $-90^\circ$.

> [!Example] Aplicación en Computación: Condensadores de Desacoplo
> Los microprocesadores cambian de estado miles de millones de veces por segundo, creando picos de corriente de alta frecuencia. Debido a la inductancia parásita de los cables, la fuente no puede responder rápido. Se colocan condensadores de desacoplo cerca de los pines del chip. A alta frecuencia, su impedancia $\mathbf{Z}_C$ es casi cero, actuando como una "reserva local" de energía que estabiliza el voltaje.

## Bibliografía
[**Fraile Mora, J.** - *Circuitos Eléctricos*, Cap. 7.]
[**Sedra & Smith** - *Circuitos Microelectrónicos*, Cap. 2 (Análisis de filtros).]