---
materia: Fundamentos de la Electrónica
id: ELE.5.2
tema: Comparadores, Histéresis y Buffers de Aislamiento
status: Revision
tags:
  - Op-Amp
  - comparador
  - buffer
  - Schmitt-Trigger
  - histéresis
  - impedancia
---

# ELE.5.2. El Op-Amp como Comparador y Buffer

> [!abstract] De la conmutación al aislamiento
> Mientras que en las compuertas lógicas usamos transistores para decisiones binarias fijas, el Op-Amp nos permite crear umbrales de decisión precisos y dinámicos. En esta lección analizamos el Op-Amp en sus dos estados más puros: sin realimentación (Comparador) y con realimentación total (Buffer). Basado en **Sedra & Smith (Cap. 2 y 12)** y **Floyd (Cap. 12)**.

---

# 1. El Op-Amp en Lazo Abierto: El Comparador

Un comparador es un dispositivo cuya salida es un nivel lógico que indica cuál de sus dos entradas tiene un potencial mayor. En lazo abierto, la ganancia es tan alta ($A_{OL} \approx 200,000$) que el Op-Amp casi siempre está saturado.

### 1.1. Principio de Operación
- **Entrada No Inversora ($V^+$) > Entrada Inversora ($V^-$)**: La salida se dispara a $+V_{sat}$ (Lógico '1').
- **Entrada No Inversora ($V^+$) < Entrada Inversora ($V^-$)**: La salida se dispara a $-V_{sat}$ o GND (Lógico '0').

### 1.2. El Problema del Ruido y la Oscilación
En una comparación simple, si la señal de entrada tiene un pequeño ruido y está cerca del voltaje de referencia, la salida oscilará violentamente entre '0' y '1'. Esto puede "volver loca" a una interrupción de CPU o dañar un actuador.

# 2. El Trigger de Schmitt (Comparador con Histéresis)

Para solucionar la oscilación por ruido, aplicamos **Realimentación Positiva**. Esto crea dos umbrales distintos: uno para la subida ($V_{UT}$) y otro para la bajada ($V_{LT}$).

### 2.1. Funcionamiento de la Histéresis
1. Cuando la salida está en $+V_{sat}$, una fracción del voltaje vuelve a la entrada (+) a través de un divisor resistivo. Esto sube el umbral de disparo.
2. La señal de entrada ahora debe superar este "nuevo umbral más alto" para cambiar la salida.
3. Una vez que cambia a $-V_{sat}$, el umbral baja automáticamente.
- **Resultado**: El ruido pequeño no tiene la amplitud suficiente para cruzar ambos umbrales, produciendo una señal digital limpia y cuadrada.

# 3. El Buffer o Seguidor de Tensión

Es el extremo opuesto al comparador: usamos **Realimentación Negativa total** conectando la salida directamente a la entrada inversora ($V^-$).

### 3.1. Las Leyes del Buffer
- **Ganancia de Tensión Unitario ($A_v = 1$):** $V_{out} = V_{in}$.
- **Impedancia de Entrada ($Z_{in} \to \infty$):** Al no entrar corriente al Op-Amp, el buffer no "carga" el circuito anterior. 
- **Impedancia de Salida ($Z_{out} \to 0$):** Puede entregar corriente a una carga sin que el voltaje de la señal caiga.

### 3.2. ¿Por qué es vital en computación?
Si conectas un sensor de alta impedancia (como un electrodo médico o un sensor capacitivo) directamente a un pin de un microcontrolador, el voltaje se "desinfla" debido a la corriente que consume el ADC. El Buffer actúa como un **aislador de potencia**, manteniendo la fidelidad de la señal analógica.

# 4. Parámetros Críticos en Aplicaciones de Alta Velocidad

Cuando el Op-Amp actúa como comparador en un bus de datos o un ADC, aparecen limitaciones reales:

1. **Tiempo de Respuesta (Response Time):** El tiempo que tarda la salida en cambiar de $-V_{sat}$ a $+V_{sat}$ tras un cambio en la entrada.
2. **Slew Rate ($SR$):** La pendiente máxima de voltaje en el tiempo ($\Delta V / \Delta t$). Si intentas generar una onda cuadrada de alta frecuencia y el SR es bajo, obtendrás un trapecio o un triángulo.
3. **Voltaje de Offset de Entrada ($V_{OS}$):** Un error interno que puede hacer que el comparador "crea" que $V_{in}$ es mayor de lo que realmente es. En sistemas de 8 o 10 bits, esto puede causar errores de digitalización.

# 5. Comparadores Integrados vs. Op-Amps
Aunque un Op-Amp (como el 741) puede comparar, existen integrados específicos como el **LM311** o **LM339** (Comparadores dedicados).
- **Diferencia**: Los comparadores dedicados tienen una salida de **Colector Abierto**, lo que permite conectarlos directamente a circuitos de 3.3V o 5V (lógica CMOS/TTL) mediante una resistencia de *pull-up*, sin importar el voltaje de alimentación del chip.

---

## Resumen Técnico
- **Comparador Simple**: Lazo abierto, sensible al ruido.
- **Trigger de Schmitt**: Realimentación positiva, elimina ruido mediante histéresis (dos umbrales).
- **Buffer**: Realimentación negativa unitaria, acoplamiento de impedancias ($Z_{in}$ alta, $Z_{out}$ baja).
- **Velocidad**: Limitada por el Slew Rate y el tiempo de propagación.

> [!Example] Aplicación en Ingeniería en Computación: El Botón de Encendido
> Cuando presionas un botón físico, los contactos metálicos "rebotan" mecánicamente generando decenas de pulsos antes de estabilizarse. Si conectas esto directo a la CPU, contará 20 pulsos en vez de uno. Usamos un **Trigger de Schmitt** para "limpiar" esa señal analógica ruidosa y convertirla en un único pulso digital perfecto de 0 a 5V.

## Bibliografía
[**Sedra & Smith** - *Circuitos Microelectrónicos*, Cap. 2 (Buffers) y Cap. 12 (Comparadores).]
[**Floyd, T. L.** - *Dispositivos Electrónicos*, Cap. 12 y 13.]
[**Tanenbaum, A. S.** - *Structured Computer Organization*, Cap. 3: I/O y Señales.]