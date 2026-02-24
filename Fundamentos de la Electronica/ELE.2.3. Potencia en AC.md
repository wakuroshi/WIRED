---
materia: Fundamentos de la Electrónica
id: ELE.2.3
tema: Potencia en AC
status: Revision
tags:
  - AC
  - potencia
  - fasores
  - factor-de-potencia
---

# ELE.2.3. Potencia en Circuitos de Corriente Alterna

> [!abstract]- El flujo de energía en sistemas oscilantes
> A diferencia de DC, donde la potencia es simplemente $V \cdot I$, en AC la potencia fluctúa periódicamente. La presencia de elementos que almacenan energía ($L$ y $C$) crea una diferencia entre la energía que realmente realiza un trabajo y la energía que simplemente oscila entre la fuente y la carga.

---

# 1. Potencia Instantánea y Potencia Media

La potencia instantánea $p(t) = v(t) \cdot i(t)$ oscila al doble de la frecuencia de la red. Lo que realmente nos interesa para dimensionar sistemas es la **Potencia Media (Activa)**.

### 1.1. Potencia Activa ($P$)
Es la potencia real que se transforma en trabajo útil (calor, movimiento). Se mide en **Vatios (W)**.
$$P = V_{rms} I_{rms} \cos(\theta_v - \theta_i)$$
El término $\cos(\phi)$ se denomina **Factor de Potencia**.

### 1.2. Potencia Reactiva ($Q$)
Representa la energía que se intercambia entre la fuente y los campos reactivos sin consumirse. Se mide en **Volt-Amperios Reactivos (VAR)**.
$$Q = V_{rms} I_{rms} \sin(\theta_v - \theta_i)$$
- **$Q > 0$:** Inductiva (absorbe reactiva).
- **$Q < 0$:** Capacitiva (entrega reactiva).

# 2. Potencia Compleja ($\mathbf{S}$)

Es la herramienta definitiva para el balance de potencias. Se define como el producto del fasor tensión por el conjugado del fasor corriente:
$$\mathbf{S} = \mathbf{V} \cdot \mathbf{I}^* = P + jQ$$
Su magnitud $|\mathbf{S}|$ es la **Potencia Aparente**, medida en **Volt-Amperios (VA)**. Es la que determina el grosor de los conductores y la capacidad de los transformadores.



# 3. El Factor de Potencia ($fp$) y su Corrección

El factor de potencia ($fp = P/S$) indica qué fracción de la energía entregada es aprovechada.
- Un $fp$ bajo implica que circula mucha corriente (aumentando pérdidas por efecto Joule en los cables) para realizar poco trabajo real.
- **Corrección:** Para corregir un $fp$ bajo debido a motores (inductivos), se conectan bancos de capacitores en paralelo que suministran la potencia reactiva localmente, descargando a la línea principal.

# 4. Teorema de Máxima Transferencia de Potencia en AC

Para que una carga $\mathbf{Z}_L = R_L + jX_L$ reciba la máxima potencia de una red con impedancia de Thévenin $\mathbf{Z}_{Th} = R_{Th} + jX_{Th}$:
1.  **Resistencia:** $R_L = R_{Th}$
2.  **Reactancia:** $X_L = -X_{Th}$ (La carga debe ser el **conjugado complejo** de la fuente).
$$\mathbf{Z}_L = \mathbf{Z}_{Th}^*$$

---

## Resumen
- **P (Activa):** Trabajo real (Watts).
- **Q (Reactiva):** Intercambio de campos (VAR).
- **S (Aparente):** Capacidad total del sistema (VA).
- **Factor de Potencia:** $\cos(\phi)$. Idealmente tendiendo a 1.

> [!Exercise] Cálculo de potencia compleja
> Una carga consume $P=10kW$ con un $fp=0.8$ inductivo. Halle $S$ y $Q$.
> 
> **Respuesta**: $S = 12.5 kVA$, $Q = 7.5 kVAR$.
> **Explicación paso a paso**:
> 1. $S = P / fp = 10k / 0.8 = 12.5 kVA$.
> 2. Hallamos el ángulo: $\phi = \arccos(0.8) \approx 36.87^\circ$.
> 3. $Q = S \cdot \sin(\phi) = 12.5k \cdot 0.6 = 7.5 kVAR$.

> [!Example] Aplicación en Computación: UPS y PSUs
> Las fuentes de alimentación de los servidores (PSUs) y los Sistemas de Alimentación Ininterrumpida (UPS) se especifican en **VA** y en **W**. Un UPS de 1000VA no necesariamente soporta una carga de 1000W si el factor de potencia de los servidores es bajo. Por eso, los ingenieros de sistemas deben calcular la potencia aparente total del rack para evitar que los interruptores térmicos salten por exceso de corriente reactiva.

## Bibliografía
[**Fraile Mora, J.** - *Circuitos Eléctricos*, Cap. 8.]
[**Sedra & Smith** - *Circuitos Microelectrónicos*, Cap. 1.]