---
materia: Fundamentos de la Electrónica
id: ELE.7.5
tema: Arquitecturas ADC Flash, Aproximaciones Sucesivas (SAR)
status: Revision
tags:
  - ADC
  - Flash
  - SAR
  - comparadores
---

# ELE.7.5. ADC: Las Arquitecturas de Captura

> [!abstract] La carrera por la velocidad
> No todos los ADC son iguales. Algunos son instantáneos pero caros, otros son lentos pero ultraprecisos. Analizaremos el tipo **Flash** y el **SAR** (el más usado en microcontroladores como Arduino o PIC).

---

# 1. ADC Tipo Flash (El más rápido)

Es el que mencionaste. Se llama así porque la conversión ocurre a "la velocidad de la luz" (bueno, de la propagación en las compuertas).

### 1.1. Arquitectura
Utiliza un divisor de voltaje masivo y un comparador para cada nivel posible.
- Para 3 bits (8 niveles), necesitas $2^3 - 1 = 7$ comparadores.
- Para 8 bits, necesitas 255 comparadores.
- Para 10 bits, ¡necesitas 1023 comparadores!
- **Funcionamiento:** Todos los comparadores analizan la señal a la vez. Un "Priority Encoder" lógico convierte las salidas de los comparadores en un código binario.

### 1.2. Pros y Contras
- **Pros:** Latencia mínima. Un solo ciclo de reloj.
- **Contras:** Consume mucha energía, ocupa mucho espacio en el chip y es muy caro para resoluciones altas (más de 8-10 bits).
- **Uso:** Osciloscopios digitales de alta gama y radares.



# 2. ADC de Aproximaciones Sucesivas (SAR)

Es el "estándar de oro" por su equilibrio entre costo y velocidad.

### 2.1. El Algoritmo de Búsqueda Binaria
El SAR funciona como el juego de "Adivina el número":
1.  Pregunta: "¿Es el voltaje mayor que la mitad de $V_{ref}$?" (MSB).
2.  Si sí, mantiene el bit en 1. Si no, lo pone en 0.
3.  Pregunta sobre la mitad de la mitad, y así sucesivamente.
- **Tiempo de conversión:** Tarda exactamente $n$ ciclos de reloj para $n$ bits. Un ADC de 10 bits tarda 10 ciclos.

### 2.2. Componentes del SAR
- **DAC interno:** Para generar los voltajes de comparación.
- **Comparador:** Para ver si la entrada es mayor que la propuesta del DAC.
- **Registro de Aproximación Sucesiva (SAR):** La lógica que ejecuta el algoritmo.

# 3. ADC Delta-Sigma ($\Delta\Sigma$)

Mención especial para el audio de alta fidelidad. 
- No mide el voltaje directamente, sino el *cambio* de voltaje.
- Usa **Oversampling** (muestrear a MHz para una señal de kHz).
- Logra resoluciones inmensas (24 bits) con muy poco ruido, pero es muy lento para señales que cambian rápido.

---

## Comparativa Final
| Tipo | Velocidad | Resolución | Costo |
| :--- | :--- | :--- | :--- |
| **Flash** | Ultra Rápida | Baja (8 bit) | Muy Alto |
| **SAR** | Media | Media (12 bit) | Bajo |
| **$\Delta\Sigma$**| Lenta | Ultra Alta (24 bit) | Medio |

## Bibliografía
[**Mano, M. M.** - *Diseño Digital*, Cap. 10.]
[**Floyd, T. L.** - *Fundamentos de Sistemas Digitales*, Cap. 12.]