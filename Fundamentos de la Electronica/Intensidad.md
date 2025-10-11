# 1. Conceptos
## 1.1. Corriente Electrica
Es el flujo de carga electrica por unidad de tiempo
- **Corriente Continua (DC, $I$):** Valor constante en el tiempo.
- **Corriente Alterna (AC, $i$ o $i(t)$):** Valor varía en el tiempo.

Materiales según su Conductividad:
- **Conductores:** Permiten el flujo de corriente con facilidad (ej: cobre).
- **Semiconductores:** Conductividad intermedia, base de la electrónica moderna (ej: silicio).
- **Aislantes:** Oponen alta resistencia al flujo de corriente (ej: goma, plástico).

## 1.2 Potencial Electrico y Tension
**La diferencia de potencial o tension** entre dos puntos A y B en un circuito es el trabajo realizado para mover la carga entre estos 2 punto.

> 	La notacion es $V$, o $u$ en Europa

### 1.2.a. Calculo del Trabajo
El trabajo diferencial $dw$ (en Joules) para mover un diferencial de carga $dq$ entre dos puntos A y B, cuyos potenciales electricos son $V_a$ y $V_b$ respectivamente. es: $$dw=(V_b - V_a)dq$$
## 1.3. Potencia y Energia Electrica
- **Potencia Instantanea ($p(t)$):** es la cantidad de energia intercambiada en la unidad de tiempo. Se mide con los Vatio($W$) $$p(t)= \frac{dw(t)}{dt} = \frac{dw(t)}{dq(t)} \cdot \frac{dq(t)}{dt}=u(t) \cdot i(t)$$
- **Energia ($w(t)$):** Integral de la potencia a lo largo del tiempo $$w(t)=\int_{-\infty}^t  p(t)dt$$
# 2. Elementos de Circuitos Electricos
Un circuito es un conjunto de elementos interconectados que a, ante una excitacion (entrada), generan una respuesta (salida), con el fin de entregar o recibir energia.
Sus elementos pueden ser activa o pasiva:
- **Activos:** Ceden potencia al circuito (ej: fuentes, baterias, generadores)
- **Pasivos:** Absorben y almacenan o disipan potencia (ej: resistencias, condensadores, bobinas)

## 2.1. Elementos Activos
### 2.1.a. Independientes:
Generan tension o corriente de manera autonoma:
- **Fuente de tension continua, DC (pila, bateria)**: Generan una diferencia de potencial $V_AB$ constante enre sus terminales.
- **Fuente de tension alterna:, AC**: Igualmente generan diferencia de potencial, pero variable en el tiempo $v_{AB}$ o $v_{ab}$
- **Fuente de corriente (AC o DC)**: Genera una corriente electrica en el sentido indicado por la flecha.

### 2.1.b. Dependientes:
Se identifican generalmente con un rombo, tienen la particularidad de que su salida (tension o corriente) depende de otra tension o corriente en el circuito:

- **Fuente de Tensión controlada por Tensión (FTCT)**: Constante $\alpha$ (adimensional).
    
- **Fuente de Tensión controlada por Corriente (FTCC)**: Constante $\beta$ (Ohms $\Omega$).
    
- **Fuente de Corriente controlada por Tensión (FCCT)**: Constante $\gamma$ (Siemens, $S$ o Mho, $\mho$).
    
- **Fuente de Corriente controlada por Corriente (FCCC)**: Constante $\delta$ (adimensional).

## 2.2. Elementos pasivos:
### 2.2.a. Resistencia ($R$)
Oposicion del material al paso de la corriente a traves de el. Disipa energía en forma de calor. Se mide en **Ohmios** ($\Omega$).

**Ley de Ohm**:
    - **Valor variable**: $v(t) = R \cdot i(t)$
    - **Valor constante**: $V = I \cdot R$

**Potencia Disipada**: $$P = V \cdot I = \frac{V^2}{R} = I^2 R$$
### 2.2.b. Condensador o Capacitor ($C$)
Almacena energía en un campo electrico. Depende del material (permitividad, $E_{\epsilon}$) y la geometría (area $A$, separación $d$). Se miden en **Faradios** ($F$).

### 2.2.c. Bobina o Inductor ($L$)
Almacena energía en un campo magnético. Representa la autoinductancia: relación entre el flujo magnetico y la corriente que lo crea. Se mide en **Henrios** ($H$)

# 3. Formas de conexion 
## 3.1. Referencias de Polaridad
- **Referencia Activa**: La corriente sale por el terminal positivo del elemento (fuentes).

- **Referencia Pasiva**: La corriente entra por el terminal positivo del elemento (cargas como resistencias).

## 3.2. Conexion de Elementos
- Serie: Los elementos se conectan uno tras otro. La misma corriente circula por todos.

- Paralelo: Los elementos se conectan entre los mismos dos nodos. La misma tensión en todos.

### 3.2.a. Resistencias:
- Serie: La resistencia equivalente es la sumatoria de las resistencias $R_{eq} = R_1 + R_2 + \dots$

- Paralelo: El inverso de resistencia equivalente es la sumatoria del inverso de las resistencias $\frac{1}{R_{eq}} = \frac{1}{R_1} + \frac{1}{R_2} + \dots$

### 3.2.b. Condensadores:
- Serie: El inverso de la capacitancia equivalente es la sumatoria del inverso de las capacitancias $\frac{1}{C_{eq}} = \frac{1}{C_1} + \frac{1}{C_2} + \dots$

- Paralelo: La capacitancia equivalente es la sumatoria de las capacitancias $C_{eq} = C_1 + C_2 + \dots$

### 3.2.c. Bobinas:
Siguen el mismo comportamiento que las resistencias:
- Serie: $L_{eq} = L_1 + L_2 + \dots$

- Paralelo: $\frac{1}{L_{eq}} = \frac{1}{L_1} + \frac{1}{L_2} + \dots$

### 3.3. Divisores
- **Divisor de Tensión**: Para resistencias en serie: $$V_{R_x} = V_{fuente} \cdot \frac{R_x}{R_{total}}$$

- **Divisor de Corriente**: Para resistencias en paralelo, $$I_{R_x} = I_{total} \cdot \frac{R_{total}}{R_x}$$

> Tip: La suma paralela de una resistencia con su doble sera 1/3 del doble

# 4. Topologia de Redes 
## 4.1. Definiciones
- **Nodo o Nudo**: Punto de unión de tres o más elementos.

- **Rama**: Conexion (elemento o conjunto en serie) entre dos nodos.

- **Lazo**: Cualquier camino cerrado en el circuito.

- **Malla**: Lazo que no contiene ningun otro lazo en su interior.

- **Grafo**: Representacion esquematica de la red, mostrando solo nodos y ramas.

- **Arbol**: Subconjunto del grafo que conecta todos los nodos sin formar lazos.

- **Eslabon o Rama de Enlace**: Rama que no pertenece al arbol. El numero de eslabones es igual al numero de mallas independientes.

## 4.2. Propiedades de un grafo
Se tiene un arbol de $r_a$ ramas y n nudos, en un grafo de $r_g$ ramas

- Ramas del arbol: $r_a = r_g - 1$

- Numero de Eslabones (Mallas Independientes): $r_e = r_g - (n - 1)$

# 5. Leyes de Kirchhoff y Teoremas de Reduccion

## 5.1. Primera Ley (LCK - Ley de Corrientes):
"La suma algebraica de las corrientes que entran a un nodo es cero."
$$\sum I_{entran} = \sum I_{salen} \therefore \sum I_k = 0$$ 
> (Convenio: entrantes +, salientes -).

## 5.2 Segunda Ley (LTK - Ley de Tensiones):
"La suma algebraica de las tensiones alrededor de cualquier lazo cerrado es cero."
$$\sum V_k = 0$$ 
> (Se debe definir un sentido de recorrido para el lazo).

## 5.3 Teoremas de Reducción y Circuitos Equivalentes
Condiciones para el Análisis:

- No pueden haber 2 fuentes de corriente ideales en serie.
- No pueden haber 2 fuentes de tension ideales en paralelo.

### 5.3.a Teorema de Thevenin
Cualquier red lineal de elementos y fuentes (independientes) con dos terminales de salida (A y B) puede ser reemplazada por un circuito equivalente formado por:

- **Una fuente de tension** ($V_{Th}$): Tensión en circuito abierto entre A y B.

- **Una resistencia en serie** ($R_{Th}$): Resistencia equivalente vista desde A y B, con todas las fuentes independientes anuladas.

- Fuentes de tensión → Cortocircuito.

- Fuentes de corriente → Circuito abierto.

### 5.3.a Teorema de Norton
La misma red puede ser reemplazada por un circuito equivalente formado por:

- **Una fuente de corriente** ($I_N$): Corriente de  cortocircuito entre A y B.

- **Una resistencia en paralelo** ($R_N$): Es la misma $R_{Th}$.

Relación: $V_{Th} = I_N \cdot R_{Th}$ y $R_N = R_{Th}$.

6. Circuitos de Corriente Senoidal Alterna (CA)
La corriente y tensión varían sinusoidalmente en el tiempo.

Se introduce el concepto de Impedancia ($Z$): Generalización de la resistencia para CA. Mide la oposición total (resistencia + reactancia) al paso de la corriente.

Admitancia ($Y$): Recíproco de la impedancia ($Y = \frac{1}{Z}$). Mide la facilidad al paso de la corriente.

Ángulo de Carga o Fase ($\phi$): Diferencia de fase entre la tensión y la corriente. Determina el factor de potencia.
