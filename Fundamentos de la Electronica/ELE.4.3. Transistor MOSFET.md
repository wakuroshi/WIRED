---
materia: Fundamentos de la Electrónica
id: ELE.4.3
tema: Transistor MOSFET (Metal-Oxide-Semiconductor)
status: Revision
tags:
  - MOSFET
  - NMOS
  - PMOS
  - tension
  - VGS
---

# ELE.4.3. El Transistor de Efecto de Campo (MOSFET)

> [!abstract] Control por campo eléctrico
> El MOSFET es el transistor más importante para la computación. A diferencia del BJT, su puerta está aislada eléctricamente por una capa de óxido ($SiO_2$), por lo que no consume corriente de entrada. Se controla mediante **tensión ($V_{GS}$)**. Basado en **Sedra & Smith (Cap. 4)**.

---

# 1. Estructura y Funcionamiento

El MOSFET (tipo enriquecimiento) no tiene un canal físico inicialmente.
- **Puerta (Gate)**: Placa metálica o de polisilicio sobre un aislante.
- **Substrato**: Cuerpo del semiconductor.
- **Proceso de Inversión**: Al aplicar $V_{GS} > V_t$ (tensión umbral), el campo eléctrico atrae portadores hacia la superficie bajo el óxido, creando un **canal conductor**.

# 2. Regiones de Operación

1. **Corte**: $V_{GS} < V_t$. No hay canal, $I_D = 0$.
2. **Triodo (Ohmica)**: El canal es continuo. El transistor actúa como una resistencia variable.
3. **Saturación**: El canal se estrecha cerca del drenador (*pinch-off*). La corriente $I_D$ se vuelve constante, ideal para lógica digital.

# 3. NMOS vs PMOS

- **NMOS**: Canal de electrones. Se activa con tensiones positivas. Más rápido.
- **PMOS**: Canal de huecos. Se activa con tensiones negativas (respecto a la fuente). Más lento pero esencial para la complementariedad.

---

## Resumen
- Impedancia de entrada infinita (en DC).
- El dispositivo fundamental de las memorias RAM y procesadores.

## Bibliografía
[**Sedra & Smith** - *Circuitos Microelectrónicos*, Cap. 4.]