---
materia: Fundamentos de la Electrónica
id: ELE.4.2
tema: Transistor de Unión Bipolar (BJT)
status: Revision
tags:
  - BJT
  - NPN
  - corriente
  - amplificación
---

# ELE.4.2. El Transistor de Unión Bipolar (BJT)

> [!abstract] Control de corriente por corriente
> El BJT fue el primer transistor comercialmente viable. Su funcionamiento depende de la interacción de dos uniones P-N muy cercanas. Es un dispositivo de "corriente" porque una pequeña corriente de base permite el paso de una corriente mucho mayor entre colector y emisor. Basado en **OCW-CCE (Sesión 12)** y **Sedra & Smith (Cap. 5)**.

---

# 1. Estructura y Tipos (NPN y PNP)

El BJT consta de tres capas de semiconductor:
- **NPN**: Una capa P delgada entre dos capas N. Es el más eficiente debido a la mayor movilidad de los electrones.
- **PNP**: Una capa N delgada entre dos capas P.

# 2. El Efecto Transistor en Detalle

En un NPN en **Región Activa**:
1. La unión **Base-Emisor (BE)** está en directa, permitiendo que el emisor inyecte electrones a la base.
2. La unión **Base-Colector (BC)** está en inversa, creando un fuerte campo eléctrico.
3. Como la base es muy estrecha, el 99% de los electrones del emisor no se recombinan y son "succionados" por el colector.

# 3. Ecuaciones y Parámetros

- **Ganancia Beta ($\beta$ o $h_{FE}$)**: $I_C = \beta \cdot I_B$. Define la capacidad de amplificación.
- **Ecuación de Corrientes**: $I_E = I_C + I_B = (\beta + 1)I_B$.
- **Voltaje de Codo ($V_{BE}$)**: Típicamente $0.7 V$ para silicio.

# 4. Regiones de Trabajo

Para análisis de circuitos, clasificamos el estado del BJT según sus uniones:
1. **Corte**: Ambas uniones en inversa. $I_C = 0$. (Interruptor OFF).
2. **Activa**: BE en directa, BC en inversa. $I_C = \beta I_B$. (Amplificador).
3. **Saturación**: Ambas uniones en directa. $V_{CE} \approx 0.2 V$. (Interruptor ON).

---

## Resumen
- El BJT es un amplificador de corriente.
- Su principal desventaja es que requiere una corriente continua en la base ($I_B > 0$) para estar encendido, lo que genera calor.

## Bibliografía
[**OCW-CCE** - *Sesión 12: Transistor Bipolar*.]
[**Sedra & Smith** - *Circuitos Microelectrónicos*, Cap. 5.]