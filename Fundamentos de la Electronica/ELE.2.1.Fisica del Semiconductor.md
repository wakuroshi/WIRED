# ELE.2.1.Fisica del Semiconductor

Existen 3 tipos de materiales que pueden conducir la electricidad y cada uno tiene un valor de **resistividad** que tiene que ser superado para que pueda conducir la electricidad.

**Resistividad:** $r = (\Omega*m)$

- Aislantes $r > 10^5 \Omega*cm$ 
- Conductores $r < 10^{-3} \Omega *cm$
- Semiconductores $10^{-3} \Omega *cm < r < 10^{5} \Omega *cm$

**Ejemplos:**

- Aislantes: Cerámicas, Plásticos, Varios tipos de óxidos, papel, aire, Entre Otros....

- Conductores: Metales, Óxidos Metálicos y no metales conductivos.

- Semiconductores: Silicio, Germano, Arseniuro de Galio y Carbono

# 1. Bandas de Energía (BE) 

Las BE representan los estados de energía permitidos para los electrones.

- Banda de Valencia: Corresponde a la región llena, donde los electrones están débilmente enlazados al átomo.

- Banda de conducción: Corresponde a la banda(generalmente vacía) donde los electrones no están enlazados a los átomos del cristal, y por tanto pueden moverse libremente a través del cristal.

- Banda Prohibida: Corresponde a la región entre las bandas de valencia y de conducción, donde no existen electrones libres.

![ELE.2.1.fa](ELE.2.1.fa.png)

> Esto es solo una representación gráfica de como se verían las bandas de energía, en realidad la banda prohibida representa cuanta energía necesita el electrón para pasar de la banda de valencia a la banda de conducción.

Por otro parte, el nivel de energía de $E{v}$ representa la máxima energía permisible de un electrón en la banda de valencia y el nivel de energía de $E{c}$ representa la mínima energía disponible en la banda de conducción.

# Movilidad y Conductividad
## Movimiento
Sin campo eléctrico aplicado:
- Movimiento aleatorio de electrones.
- Corriente media cero.

Con un campo eléctrico aplicado:
- Se acelera la partícula, por lo tanto el movimiento de los electrones es coherente al campo aplicado.
- Corriente media distinta de cero.

Ademad la conductividad se ve afectada por: Temperatura, ionización y contaminación o dopado.

## Fuerza 
La fuerza $f$ ejercida por un campo electrico $E$ sobre una carga positiva $q$ : $f = q\varepsilon = ma$ 
Donde: 
$q:$  Carga de la partícula ($1,6*10^{-19}$ culombios),
$\varepsilon:$ intensidad del campo eléctrico (voltio/metro),
$m:$ Masa de la partícula ($9,11*10^{-31}Kg$),
$a:$ Aceleración de la partícula debida a $\varepsilon$ ($m^2/S$).

## Movilidad
La velocidad $v$ de la partícula esta dada por:
 $$v = a*t = \frac{qt}{m}$$
 $$v = \mu\varepsilon$$
 Donde la movilidad de la partícula se define como $\mu = \frac{qt}{m}$ en $m^2/(Volt*Seg)$,
 $t:$ tiempo en segundos($S$),
 $m:$ Masa de la partícula($9,11*10^{-31}Kg$),
 $a:$ Aceleración de la partícula debida a $\varepsilon$.

## Corriente 
El conductor de la figura de sección transversal $A$ y longitud $L$ contiene $N$ electrones: 
![ELE.2.1.fb](ELE.2.1.fb.png)
En presencia de un campo eléctrico, un electrón tarda $T$ segundos para recorrer la distancia $L$, entonces en cualquier sección transversal, la corriente es:
$$I= \frac{Nq}{T}= \frac{Nqv}{L}$$
$$T = \frac{L}{v}$$
Donde:
$v:$Velocidad del electrón.

## Densidad de corriente 
La densidad de corriente por definición es:
$$J=\frac{I}{A}$$
$$J=\frac{Nqv}{LA}$$  Para $A/m^2$ 
## Concentración de Electrones
El termino $\frac{N}{LA}$ (Nro de Electrones por metro cubico) es la concentración de electrones, $n$.
$$n=\frac{N}{LA}$$

Al final la **Densidad de Corriente** se reduce a:
$$J=nqv=\rho v$$
Donde la densidad de carga $\rho$ esta dada por:
$$\rho = nq$$
En culombios/$m^3$ y $v$ esta en metros por segundo.

Ademas la derivación de la densidad de corriente es independiente de la forma del medio conductor.

## Conductividad
Recordando que $v=\mu\varepsilon$ 

La densidad de corriente es: $J=nqv=nq\mu\varepsilon=\rho\mu\varepsilon=\sigma\varepsilon$ 

Donde la conductividad $(\Omega*m)^{-1}$ es: $\sigma = \rho\mu=nq\mu$ 

Al final concluimos con la ecuación: $J=\sigma\varepsilon$ la cual se conoce como la ley de ohm microscópica
