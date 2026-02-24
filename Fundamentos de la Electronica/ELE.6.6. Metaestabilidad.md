---
materia: Fundamentos de la Electrónica
id: ELE.6.8
tema: Timing, Setup/Hold Time y Fallos de Sincronismo
status: Revision
tags:
  - setup
  - hold
  - metaestabilidad
  - timing
  - clock-skew
---

# ELE.6.6. Tiempo y Metaestabilidad: Los Límites de la Velocidad

> [!abstract] Cuando la física vence a la lógica
> En los libros, los voltajes cambian de 0 a 5V instantáneamente. En un laboratorio, los electrones tienen masa y los cables tienen capacitancia. El tiempo que tarda una señal en estabilizarse dicta qué tan rápido puede correr tu procesador. Basado en **Wakerly (Cap. 7)**.

---

# 1. La Ventana de Captura

Para que un Flip-Flop capture un dato correctamente, este debe estar "quieto" en la entrada $D$ durante un periodo de tiempo alrededor del flanco de reloj.

1.  **Setup Time ($t_{su}$):** Tiempo mínimo que el dato debe estar estable **antes** de que llegue el flanco. Si el dato cambia 1 picosegundo antes del flanco, el FF no lo verá.
2.  **Hold Time ($t_h$):** Tiempo mínimo que el dato debe mantenerse estable **después** del flanco.
3.  **Propagation Delay ($t_{pd}$):** Tiempo que tarda el FF en reflejar el nuevo dato en la salida $Q$.



# 2. El Desastre de la Metaestabilidad

¿Qué pasa si el dato cambia **justo en medio** del flanco de reloj (violando el $t_{su}$ o $t_h$)?
- El Flip-Flop entra en un estado **metaestable**. No es ni 0 ni 1.
- El voltaje interno se queda oscilando en el umbral medio (ej. 2.5V).
- Eventualmente, el ruido térmico hará que caiga a 0 o 1, pero puede tardar mucho más del tiempo de propagación normal.
- **Impacto:** Si la siguiente compuerta lee ese valor "indefinido", el error se propaga por toda la CPU, causando un cuelgue del sistema (BSOD).

# 3. Clock Skew (Desviación de Reloj)

En un chip grande, el cable del reloj es muy largo. El pulso puede llegar al Flip-Flop A unos picosegundos antes que al Flip-Flop B.
- Si el Skew es muy grande, el FF-B podría capturar un dato que aún no debería haber cambiado.
- **Solución de Ingeniería:** Se usan "árboles de reloj" (Clock Trees) con buffers balanceados para que el reloj llegue a todos los rincones del chip exactamente al mismo tiempo.

# 4. Frecuencia Máxima de Trabajo

¿Por qué un i9 no corre a 100 GHz? Por la siguiente fórmula:
$$T_{min} = t_{pd} + t_{comb} + t_{su}$$
Donde:
- $t_{pd}$ es el retraso del FF.
- $t_{comb}$ es el tiempo que tarda la lógica de compuertas (AND, OR) entre dos FF.
- $t_{su}$ es el tiempo de setup.
- **Frecuencia máxima:** $f_{max} = 1 / T_{min}$. 
- Si quieres más velocidad, tienes que reducir el número de compuertas entre Flip-Flops (esta técnica se llama **Pipelining**).

# 5. Sincronizadores de Dos Etapas

Cuando una señal viene de fuera (un teclado o un sensor), no está sincronizada con el reloj de la CPU. Para evitar la metaestabilidad, la pasamos por dos Flip-Flops D en cascada.
- El primer FF puede entrar en metaestabilidad, pero tiene un ciclo completo de reloj para estabilizarse antes de que el segundo FF lo lea. Es la técnica estándar para interfaces de E/S.

---

## Bibliografía
[**John F. Wakerly** - *Diseño Digital: Principios y Prácticas*, Cap. 7.]
[**Sedra & Smith** - *Circuitos Microelectrónicos*, Cap. 14.]