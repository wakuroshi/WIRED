---
materia: Fundamentos de la Electrónica
id: ELE.7.2
tema: Muestreo, Aliasing y Teorema de Nyquist-Shannon
status: Revision
tags:
  - muestreo
  - Nyquist
  - aliasing
  - DSP
---

# ELE.7.2. Nyquist: Las Reglas del Juego Digital

> [!abstract] ¿Cuánta información es suficiente?
> Para convertir una señal continua en digital, debemos tomar "fotos" (muestras) de su valor. Si tomamos muy pocas, perdemos la forma de la señal. Si tomamos demasiadas, saturamos la memoria. Harry Nyquist definió el límite matemático exacto.

---

# 1. El Proceso de Muestreo (Sampling)

Muestrear es multiplicar la señal analógica $x(t)$ por un tren de pulsos (Delta de Dirac). Esto convierte el tiempo continuo en tiempo discreto $n$.

### 1.1. El Teorema de Nyquist-Shannon
Para poder reconstruir una señal analógica a partir de sus muestras sin perder información, la frecuencia de muestreo ($f_s$) debe ser **estrictamente mayor al doble** de la frecuencia máxima ($f_{max}$) presente en la señal original.
$$f_s > 2 \cdot f_{max}$$

# 2. El Fenómeno del Aliasing (Solapamiento)

Si no respetas a Nyquist y muestreas demasiado lento, ocurre el **Aliasing**. Las frecuencias altas "se disfrazan" de frecuencias bajas.
- *Ejemplo visual:* En las películas antiguas, las ruedas de las carretas parecen girar hacia atrás porque la cámara (muestreador) no es lo suficientemente rápida para seguir el giro.
- En audio, el aliasing suena como distorsión metálica desagradable que no se puede eliminar después.



# 3. El Filtro Antialiasing (Esencial)

En la práctica, ninguna señal del mundo real está "limpia". Siempre hay ruido de alta frecuencia. Si ese ruido supera $f_s/2$, se meterá en tu rango de medida como aliasing.
- **Solución:** Siempre se coloca un **Filtro Pasa-Bajos analógico** antes del ADC. 
- Este filtro "corta" todo lo que esté por encima de la frecuencia de Nyquist para asegurar que el ADC solo vea señales válidas.

# 4. Reconstrucción: El Filtro de Suavizado

Una vez que tenemos los datos en la CPU y queremos volver al mundo analógico (DAC), los datos salen como "escalones". 
- Para recuperar la curva suave original, pasamos la salida del DAC por un filtro de reconstrucción que elimina los bordes abruptos de los escalones digitales.

# 5. Aplicación: ¿Por qué los CD usan 44.1 kHz?
El oído humano escucha hasta los $20\text{ kHz}$. Según Nyquist, necesitaríamos al menos $40\text{ kHz}$. Se eligió $44.1\text{ kHz}$ para dejar un "margen de guarda" que permitiera fabricar filtros antialiasing reales (que no son cortes perfectos).

---

## Resumen de Diseño
1. Definir la frecuencia máxima de interés.
2. Aplicar filtro antialiasing.
3. Muestrear a $f_s \geq 2 \cdot f_{max}$ (usualmente se usa $5x$ o $10x$ por seguridad).

## Bibliografía
[**Oppenheim, A. V.** - *Tratamiento de Señales en Tiempo Discreto*.]