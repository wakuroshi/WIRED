---
materia: Fundamentos de la Electrónica
id: ELE.3.3
tema: Diodos Zener, LED y Circuitos de Limitación
status: Revision
tags:
  - zener
  - LED
  - clippers
  - reguladores
  - señales-digitales
---

# ELE.3.3. Diodos Especiales y Circuitos de Protección

> [!abstract] Más allá de la rectificación
> No todos los diodos sirven solo para rectificar. Algunos se diseñan para trabajar en la zona de ruptura (Zener) o para emitir luz (LED). En computación, estos componentes son vitales para la regulación de voltaje y la protección de entradas lógicas. Basado en **OCW-CCE (Sesión 8)** y **Floyd (Cap. 1)**.

---

# 1. El Diodo Zener

A diferencia del diodo convencional, el Zener se diseña para trabajar en **Polarización Inversa** dentro de la zona de ruptura sin destruirse.

- **Voltaje Zener ($V_Z$)**: Tensión constante que mantiene el diodo cuando se alcanza la ruptura.
- **Regulación**: Se usa para mantener un voltaje estable a pesar de variaciones en la fuente o en la carga.
- **Condición**: Requiere una resistencia limitadora ($R_s$) para no superar la potencia máxima disipable.

# 2. Circuitos Recortadores (Clippers) y Sujetadores (Clampers)

### 2.1. Recortadores (Clippers)
Circuitos que "cortan" la señal por encima o por debajo de un nivel de tensión determinado.
- **Aplicación**: Protección de pines de entrada en microcontroladores (ej. Arduino o ESP32) para que señales externas no superen los $3.3 V$ o $5 V$, evitando quemar los transistores internos.

### 2.2. Sujetadores (Clampers)
Desplazan el nivel de DC de una señal alterna sin cambiar su forma. Útiles en sistemas de video y transmisión de datos.

# 3. Dispositivos Optoelectrónicos

### 3.1. Diodo Emisor de Luz (LED)
Emite fotones cuando los portadores se recombinan en la unión P-N.
- **Materiales**: No se usa Silicio, sino compuestos como Arseniuro de Galio (GaAs) para obtener diferentes colores.
- **Uso**: Indicadores de estado, retroiluminación y comunicación por fibra óptica.

### 3.2. Fotodiodo
Funciona de forma inversa al LED: genera corriente cuando inciden fotones sobre la unión P-N. [cite_start]Es el sensor básico de luz en dispositivos automáticos[cite: 6].

# 4. Transducción y Sensores de Proximidad

Según el trabajo de **Lozada et al. (2026)**, los diodos infrarrojos son la base de los sensores de proximidad:
- [cite_start]**Sensor de Ranura**: Un LED y un fototransistor detectan interrupciones físicas (contaje de eventos)[cite: 6].
- [cite_start]**Reflexión**: Miden la luz rebotada para detectar distancias[cite: 6].

---

## Resumen
- **Zener**: Estabiliza voltajes en fuentes de alimentación.
- **Clippers**: Protegen circuitos digitales de picos de tensión.
- [cite_start]**Optoelectrónica**: Puente entre el mundo físico (luz) y el digital (señal eléctrica)[cite: 6].

> [!Exercise] Cálculo de Zener
> Si tienes una fuente de $12 V$ y necesitas alimentar un sensor que solo admite $5.1 V$, ¿cómo conectarías un Zener?
> **Respuesta**: Zener de $V_Z = 5.1 V$ en paralelo con la carga y una resistencia en serie calculada para limitar la corriente total.

## Bibliografía
[**Material de Cátedra (OCW-CCE)** - *Sesión 8: Análisis de circuitos con diodos*, Págs. 11-18.]
[**Floyd, T. L.** - *Fundamentos de Sistemas Digitales*, Cap. 1: Introducción a semiconductores.]
[cite_start][**Hernández, Hernandez, Lozada, Vivas (2026)** - *Diseño de Sistema de Monitoreo Digital*, Sección 4: Sensores.] [cite: 6]