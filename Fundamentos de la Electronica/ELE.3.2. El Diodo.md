---
materia: Fundamentos de la Electrónica
id: ELE.3.2
tema: Modelos del Diodo y Rectificación de Señales
status: Revision
tags:
  - diodos
  - rectificadores
  - modelos-equivalentes
  - AC-DC
---

# ELE.3.2. El Diodo y Circuitos de Rectificación

> [!abstract] La válvula eléctrica unidireccional
> El diodo es el componente semiconductor más simple pero esencial. Su función principal es la rectificación: convertir señales de corriente alterna (AC) en continua (DC). En esta lección analizamos sus modelos circuitales y su aplicación en fuentes de alimentación. Basado en **OCW-CCE (Sesión 8)** y **Sedra & Smith (Cap. 4)**.

---

# 1. El Diodo Real vs. Modelos Ideales

Para facilitar el análisis de circuitos, utilizamos diferentes aproximaciones según la precisión requerida:

### 1.1. Diodo Ideal
Se comporta como un interruptor perfecto:
- **Directa ($V_D > 0$)**: Cortocircuito ($V_D = 0$).
- **Inversa ($V_D < 0$)**: Circuito abierto ($I_D = 0$).

### 1.2. Modelo de Tensión de Codo ($V_\gamma$)
Es el modelo más usado en ingeniería práctica. Considera que el diodo no conduce hasta que supera los $0.7 V$.
- **Directa**: Se sustituye por una fuente de tensión de $0.7 V$.
- **Inversa**: Circuito abierto.

### 1.3. Modelo con Resistencia Interna ($r_d$)
Añade una resistencia en serie para modelar la pendiente de la curva en la región de conducción. Útil para análisis de pequeña señal en microelectrónica.

# 2. Análisis Analítico del Diodo

El comportamiento real sigue la **Ecuación de Shockley**:
$$I_D = I_s \left( e^{\frac{V_D}{n V_T}} - 1 \right)$$
Donde $V_T$ es el voltaje térmico ($\approx 26 mV$ a $25^\circ C$). Debido a su naturaleza no lineal, resolver circuitos con diodos requiere:
1.  **Método Gráfico**: Intersección de la curva del diodo con la recta de carga.
2.  **Suposición de Estados**: Suponer si el diodo está ON u OFF, resolver y verificar la coherencia de los resultados.

# 3. Circuitos Rectificadores

La rectificación es el proceso de eliminar o invertir la parte negativa de una señal senoidal.

### 3.1. Rectificador de Media Onda
Consiste en un único diodo en serie con la carga.
- **Resultado**: Solo pasa el semiciclo positivo. La tensión media de salida es $V_{avg} = V_{peak} / \pi$.
- **Desventaja**: Muy ineficiente, desperdicia la mitad de la energía.

### 3.2. Rectificador de Onda Completa (Puente de Graetz)
Utiliza 4 diodos dispuestos en puente para que la corriente siempre fluya en el mismo sentido por la carga.
- **Resultado**: Los semiciclos negativos se "vuelven" positivos. $V_{avg} = 2 V_{peak} / \pi$.
- **Ventaja**: Mayor eficiencia y menor rizado.

### 3.3. Filtrado por Condensador
Se coloca un condensador en paralelo con la carga. El condensador se carga en los picos y se descarga lentamente, manteniendo la tensión casi constante (DC con rizado).

---

## Resumen
- **Modelos**: El modelo de $0.7 V$ es el estándar para análisis manual.
- **Rectificación**: Paso crítico para alimentar dispositivos electrónicos desde la red eléctrica.
- **Rizado**: Pequeña variación de tensión que queda tras el filtrado.

> [!Example] Aplicación en Ingeniería en Computación
> Todas las fuentes de alimentación (PSU) de un servidor o laptop contienen un rectificador de onda completa. Antes de que el procesador reciba sus $1.2 V$ estables, los $220 V/110 V$ de la pared pasan por un puente de diodos y filtros capacitivos para asegurar que no existan fluctuaciones que puedan dañar la lógica CMOS.

## Bibliografía
[**Material de Cátedra (OCW-CCE)** - *Sesión 8: Análisis de circuitos con diodos*, Págs. 2-10.]
[**Sedra & Smith** - *Circuitos Microelectrónicos*, Cap. 4: Diodos.]