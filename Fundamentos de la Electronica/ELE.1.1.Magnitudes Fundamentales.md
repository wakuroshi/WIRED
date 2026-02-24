---
materia: Fundamentos de la Electrónica
id: ELE.1.1
tema: Magnitudes Fundamentales
status: Terminado
tags: [DC, electromagnetismo, electronica]
---

# ELE.1.1. Magnitudes Fundamentales

> [!abstract]- Las variables indispensables en el análisis de circuitos
> Para entender cualquier red eléctrica, primero debemos dominar las magnitudes que "viven" en ella: **carga, corriente, tensión, potencia y energía**. Estas son las herramientas básicas para cuantificar el comportamiento de la electricidad y el intercambio energético en un sistema.

---

# 1. Teoría de Circuitos y Elementos

Un **circuito o red eléctrica** es un modelo matemático que simplifica fenómenos electromagnéticos complejos mediante una interconexión de elementos. Las bases científicas se asientan en las **leyes de Ohm** y los **lemas de Kirchhoff**.

Los componentes se dividen en:
- **Activos (Fuentes)**: Capaces de generar energía eléctrica a largo plazo (**baterías, generadores**).
- **Pasivos**: Elementos que disipan energía (**resistencias**) o la almacenan en campos (**bobinas y condensadores**).

# 2. Variables de Estado Eléctrico

## 2.1. Carga Eléctrica ($q$)

Es la propiedad eléctrica de las partículas atómicas de las que se compone la materia.
- **Cuantización**: $q = n \cdot e$, donde $e = 1,602 \cdot 10^{-19}$ C.
- **Ley de Conservación**: La carga no se crea ni se destruye, solo se transfiere. En un circuito cerrado, la suma algebraica de todas las cargas es constante.

## 2.2. Corriente Eléctrica ($i, I$)

Es la velocidad de cambio de la carga respecto al tiempo a través de un área transversal.
- **Fórmula**: $$i(t) = \frac{dq(t)}{dt} [Amperios]$$
- **Tipos**:
	- **Continua (DC)**: Permanece constante en el tiempo ($I$).
	- **Alterna (AC)**: Varía en el tiempo ($i(t)$).	
- **Sentido Real vs. Convencional**: Aunque los electrones fluyen del terminal negativo al positivo, por convenio usamos el flujo de carga positiva (de $+$ a $-$), igualmente se puede seleccionar de manera arbitraria un sentido cualquiera, y el resultado del análisis da respuesta a si el sentido propuesto fue correcto, o si va al contrario (se obtiene un valor negativo).

## 2.3. Tensión, Voltaje o Diferencia de Potencial ($v, V$)

Es la energía necesaria para mover una carga unitaria a través de un elemento.El nivel cero del potencial eléctrico es arbitrario. Es por eso que se habla de una *diferencia de potencial (d.d.p)*.

- **Fórmula**: $$V_{ab} = V(t) = V_A - V_b = \frac{dw}{dq} [Voltios]$$

Si es constante, se denota $V$ o $u$, si es variable en el tiempo $v(t)$ o $u(t)$

> **Referencia**: Siempre se mide entre dos puntos. El potencial en un punto $V_a$ solo tiene sentido si se compara con un nodo de referencia (Tierra o Ground).

## 2.4. Potencia ($p$) y Energía ($w$)

- **Potencia**: Velocidad de absorción o suministro de energía: $$p = \frac{dw(t)}{dt} = v \cdot i [Vatios]$$

> Para p > 0 se absorbe energia, de lo contrario se produce o entrega

- **Energía**: Capacidad de realizar trabajo. $$w = \int_{t_0}^{t} p(\tau) d\tau [Julios]$$

# 3. Convenio de Signos y Balance de Potencia

Es fundamental para no cometer errores en el análisis de redes complejas:

1. **Convenio Pasivo (Carga)**: La corriente **entra** por el $+$. Si $p > 0$, el elemento consume energía.
2. **Convenio Activo (Fuente)**: La corriente **sale** por el $+$. Si $p < 0$, el elemento entrega energía.

> [!question]- Cálculo de corriente y carga acumulada: La carga que entra en un terminal de un elemento es $q(t) = 5t \sin(4\pi t)$ mC. Calcule la corriente en $t = 0.5$ s.
> 
> **Respuesta**: 31.42 mA
> **Explicación paso a paso**:
> 1. Aplicamos la derivada: $i(t) = \frac{dq}{dt} = \frac{d}{dt} [5t \sin(4\pi t)]$.
> 2. Usamos regla del producto: $i(t) = 5\sin(4\pi t) + 20\pi t \cos(4\pi t)$.
> 3. Evaluamos en $t = 0.5$: $i(0.5) = 5\sin(2\pi) + 10\pi \cos(2\pi) = 0 + 10\pi(1) = 31.42$ mA.

---

## Resumen

- **Carga**: Cuantizada y conservada.($q=n \cdot e$)
- **Corriente**: Derivada de la carga ($i = dq/dt$).
- **Tensión**: Trabajo por unidad de carga ($V = dw/dq$).
- **Potencia**: 
- **Balance Energético**: En un circuito aislado, $\sum p = 0$.

> [!Example]- Ejemplo de aplicación en la Ingeniería en Computación
> En el análisis de **consumo de energía de un SoC** (System on Chip), la corriente $i(t)$ fluctúa violentamente según las instrucciones que ejecute la CPU. Para calcular la duración de la batería, el software de gestión de energía realiza una **integración numérica** de la potencia ($w = \int v \cdot i dt$)

---

## Bibliografía

**Fraile Mora, J.** - *Circuitos Eléctricos*, Cap. 1.1 - 1.2
