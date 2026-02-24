---
materia: Fundamentos de la Electrónica
id: ELE.3.1
tema: Física de Semiconductores y Unión P-N
status: Revision
tags:
  - semiconductores
  - silicio
  - dopaje
  - union-pn
  - fisica-de-estado-solido
---

# ELE.3.1. Física de Semiconductores y la Unión P-N

> [!abstract] Del aislante al conductor
> La electrónica moderna no existiría sin la capacidad de controlar la conductividad de los materiales. Esta lección explora cómo, mediante el dopaje del Silicio, podemos crear la unión P-N, el bloque fundamental de diodos y transistores. Basado en **OCW-CCE (Sesión 7)** y **Sedra & Smith (Cap. 3)**.

---

# 1. Teoría de Bandas y Materiales

Según la física de estado sólido, los electrones en un cristal ocupan bandas de energía permitidas. La diferencia entre conductores, aislantes y semiconductores radica en la **Banda Prohibida (GAP)**:
- **Conductores**: Las bandas de valencia (BV) y conducción (BC) se solapan. Los electrones fluyen libremente.
- **Aislantes**: Poseen un GAP muy grande ($> 5 eV$). Los electrones no pueden saltar a la BC.
- **Semiconductores**: GAP pequeño ($\approx 1.1 eV$ para el Silicio). Con energía térmica, algunos electrones saltan a la BC.

# 2. Semiconductores Intrínsecos y Extrínsecos

### 2.1. El Cristal de Silicio (Intrínseco)
A $0 K$, es un aislante perfecto. A temperatura ambiente, se rompen enlaces covalentes creando pares **electrón-hueco**.
- **Hueco**: Ausencia de electrón que actúa como una carga positiva efectiva.
- **Generación y Recombinación**: Procesos dinámicos que mantienen la concentración intrínseca ($n_i$).

### 2.2. Dopaje (Extrínseco)
Para aumentar la conductividad de forma controlada, se añaden impurezas al cristal de Silicio puro:
- **Tipo N (Negativo)**: Se añaden átomos **Pentavalentes** (Fósforo, Arsénico). Aportan electrones libres.
- **Tipo P (Positivo)**: Se añaden átomos **Trivalentes** (Boro, Galio). Crean huecos al aceptar electrones del cristal.

# 3. La Unión P-N en Equilibrio

Cuando unimos un material tipo P con uno tipo N, ocurre un fenómeno crítico en la interfaz:

1.  **Difusión**: Los electrones de N pasan a P y los huecos de P pasan a N debido al gradiente de concentración.
2.  **Zona de Carga de Espacio (ZCE)**: Cerca de la unión, los portadores se recombinan, dejando iones cargados fijos (positivos en N, negativos en P).
3.  **Barrera de Potencial ($V_0$)**: Estos iones crean un campo eléctrico que se opone a la difusión. En el Silicio, esta barrera es de aproximadamente $0.7 V$.

# 4. Polarización de la Unión P-N

### 4.1. Polarización Inversa (Reverse Bias)
Se conecta el terminal positivo de la fuente al material N y el negativo al P.
- **Efecto**: La ZCE se ensancha, impidiendo el flujo de corriente mayoritaria.
- **Corriente de Saturación ($I_s$)**: Existe una corriente mínima de portadores minoritarios (del orden de los $nA$ o $pA$).

### 4.2. Polarización Directa (Forward Bias)
Se conecta el terminal positivo al material P y el negativo al N.
- **Efecto**: El campo externo vence a la barrera $V_0$. La ZCE se estrecha y los portadores fluyen masivamente.
- **Umbral de Conducción ($V_\gamma$)**: A partir de $\approx 0.6V - 0.7V$, la corriente crece exponencialmente.

---

## Resumen
- **Semiconductores**: Materiales cuya conductividad se altera mediante dopaje (P o N).
- **Unión P-N**: Crea una barrera que solo permite el paso de corriente en un sentido.
- **Variables Clave**: Concentración de dopado ($N_A, N_D$), temperatura y ancho de la ZCE.

> [!Example] Aplicación en Ingeniería en Computación
> La miniaturización de procesadores depende de controlar el ancho de la ZCE. En transistores de nanómetros, si la ZCE es demasiado delgada, ocurre el "efecto túnel" (los electrones saltan la barrera incluso en apagado), lo que genera fugas de corriente y calor excesivo en las CPUs modernas, limitando la Ley de Moore.

## Bibliografía
[**Material de Cátedra (OCW-CCE)** - *Sesión 7: Fundamentos de dispositivos semiconductores*, Págs. 1-15.]
[**Sedra & Smith** - *Circuitos Microelectrónicos*, Cap. 3: Física de Semiconductores.]