---
materia: Fundamentos de la Electrónica
id: ELE.6.4
tema: Flip-Flop D (Edge-Triggered)
status: Revision
tags:
  - Flip-Flop
  - D-FF
  - reloj
  - sincronismo
  - registros
---

# ELE.6.4. El Flip-Flop D: Sincronismo Perfecto

> [!abstract] El guardián del tiempo
> Si el Latch es una puerta abierta, el Flip-Flop es una **cámara fotográfica**. Solo captura el valor de la entrada en el instante preciso del flanco de reloj ($Clock$). Es la base de toda la arquitectura síncrona moderna.

---

# 1. ¿Por qué el Flanco? (Edge-Triggering)

En una CPU, miles de millones de operaciones ocurren por segundo. Necesitamos que todas ocurran al unísono. Al disparar por flanco (transición de 0 a 1), nos aseguramos de que el circuito sea inmune al ruido que ocurre entre pulsos.

# 2. Arquitectura Interna: Maestro-Esclavo

Un FF-D no es magia; son dos latches puestos en serie con relojes invertidos.
1.  **Etapa Maestro:** Recibe el dato cuando el reloj está en bajo (0).
2.  **Etapa Esclavo:** Está bloqueada mientras el reloj está en bajo.
3.  **El Disparo:** Cuando el reloj sube (1), el Maestro se bloquea y le pasa el dato al Esclavo, que lo muestra en la salida $Q$.
- **Resultado:** El dato solo puede "saltar" de la entrada a la salida en el momento exacto del flanco.



# 3. Aplicaciones en Ingeniería en Computación

### 3.1. Registros de CPU
Un registro (como el `EAX` en x86) es simplemente un banco de 32 o 64 Flip-Flops D que comparten la misma línea de reloj. Cuando ejecutas una instrucción de suma, el resultado se pone en la entrada $D$ de estos FF y el pulso de reloj lo "ancla" en el registro.

### 3.2. Sincronización de Buses
Cuando un dato viaja por un cable largo (bus), los bits llegan a tiempos ligeramente distintos (Skew). Pasarlos por un FF-D al llegar al destino "realinea" todos los bits para que la CPU los lea correctamente.

# 4. Entradas Asíncronas (PRE y CLR)

A veces necesitamos resetear la computadora sin esperar al siguiente pulso de reloj. Para eso están las entradas **Preset** (Pone a 1) y **Clear** (Pone a 0).
- Estas entradas tienen prioridad absoluta sobre el reloj y el dato $D$. Se usan en el encendido (Power-on Reset) para asegurar que el procesador empiece desde la dirección `0x0000`.

---

## Resumen de Funcionamiento
- **Reloj $\uparrow$:** $Q = D$.
- **Cualquier otro momento:** $Q$ mantiene su valor anterior.
- Es el dispositivo de memoria más robusto y común en el diseño de circuitos integrados (VLSI).

## Bibliografía
[**M. Morris Mano** - *Diseño Digital*, Cap. 5: Lógica Secuencial Síncrona.]
[**Tanenbaum, A. S.** - *Structured Computer Organization*, Cap. 3.]