---
materia: Fundamentos de la Electrónica
id: ELE.1.5
tema: Teoremas de Redes
status: Terminado
tags: [thevenin, norton, superposicion, potencia-maxima]
---

# ELE.1.5. Teoremas de Redes

> [!abstract]- Simplificando la complejidad
> Los teoremas de redes nos permiten aislar una parte del circuito (la "Carga" o "Load") y sustituir todo el resto del universo (miles de componentes) por un circuito equivalente simple. Esto es vital para el diseño modular.

---

# 1. Principio de Superposición

Válido **solo para circuitos lineales**.
> "La respuesta (tensión o corriente) en cualquier rama de un circuito lineal con múltiples fuentes independientes es igual a la suma algebraica de las respuestas debidas a cada fuente actuando por separado".

**Procedimiento:**
1.  Apagar todas las fuentes independientes excepto una.
    * Fuente de Tensión $\rightarrow$ **Cortocircuito** ($0V$).
    * Fuente de Corriente $\rightarrow$ **Circuito Abierto** ($0A$).
2.  Calcular la variable deseada.
3.  Repetir para cada fuente y sumar los resultados.

* **Advertencia**: La superposición **NO** aplica a la potencia ($P = I^2 R$ no es lineal). Se deben sumar corrientes/tensiones primero y luego calcular potencia.

# 2. Teorema de Thévenin

Cualquier red lineal de dos terminales puede sustituirse por una **Fuente de Tensión ($V_{Th}$)** en serie con una **Resistencia ($R_{Th}$)**.

### Algoritmo de Obtención:
1.  **Hallar $V_{Th}$**: Es la tensión de circuito abierto ($V_{oc}$) entre los terminales A y B.
2.  **Hallar $R_{Th}$**: Es la resistencia equivalente vista desde los terminales cuando las fuentes independientes están apagadas.
    * *Caso con Fuentes Dependientes*: No se pueden apagar las dependientes. Se debe colocar una **Fuente de Prueba** ($V_p$ o $I_p$) en los terminales y calcular la relación:
        $$R_{Th} = \frac{V_p}{I_p}$$

# 3. Teorema de Norton

Dual al de Thévenin. Cualquier red lineal se sustituye por una **Fuente de Corriente ($I_N$)** en paralelo con una **Resistencia ($R_N$)**.

* **Relación**:
    * $R_N = R_{Th}$
    * $I_N = I_{sc}$ (Corriente de cortocircuito entre A y B).
    * Transformación de fuente: $V_{Th} = I_N \cdot R_{Th}$.



# 4. Teorema de Máxima Transferencia de Potencia

¿Qué valor debe tener la resistencia de carga ($R_L$) para extraer la máxima potencia posible de un circuito?
> "La máxima potencia se transfiere a la carga cuando la resistencia de carga es igual a la resistencia de Thévenin de la fuente".

$$R_L = R_{Th}$$

* **Potencia Máxima**: $P_{max} = \frac{V_{Th}^2}{4 R_{Th}}$.
* **Eficiencia**: En máxima potencia, la eficiencia es solo del 50% (la otra mitad se pierde en la $R_{Th}$ interna).

---

## Resumen

* **Superposición**: Divide y vencerás (pero cuidado con la potencia).
* **Thévenin/Norton**: Reducen circuitos gigantes a 2 componentes. Indispensable para conectar etapas en cascada.
* **Adaptación de Impedancias ($R_L = R_{Th}$)**: Crítico en comunicaciones y transmisión de señales, aunque en sistemas de potencia (red eléctrica) buscamos eficiencia máxima ($R_L \gg R_{Th}$), no potencia máxima.

> [!Example] Aplicación: Terminación de Buses de Datos
> En un bus de datos de alta velocidad (como en una placa madre), las pistas de cobre actúan como líneas de transmisión con una impedancia característica ($Z_0$). Para evitar "rebotes" (reflexiones) de la señal que corrompan los bits, se coloca una resistencia de terminación en el receptor igual a la impedancia equivalente de Thévenin de la línea.

## Bibliografía
[**Fraile Mora, J.** - *Circuitos Eléctricos*, Cap. 5]
[**Sedra & Smith** - *Circuitos Microelectrónicos*, Teoremas básicos]