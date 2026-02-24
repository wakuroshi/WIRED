---
materia: Estadística
id: EST.1.1
tema: Metodología, Escalas de Medición y Teoría del Muestreo
status: Terminado
tags: [estadística, muestreo, metodología, ingeniería, axiomas]
---

# EST.1.1. Metodología y Teoría del Muestreo

> [!abstract] La Ciencia de la Incertidumbre
> La estadística es la rama de las matemáticas que se ocupa de la recolección, organización, análisis e interpretación de datos. En ingeniería, su propósito fundamental es la **toma de decisiones bajo incertidumbre**, transformando datos brutos en modelos predictivos y descriptivos.

---

# 1. Ontología y Escalas de Medición (Niveles de Stevens)

Antes de procesar un dato, debemos entender su naturaleza. El rigor de un análisis estadístico está limitado por la escala de medición de la variable.

### 1.1. Variables Cualitativas (Atributos)
Representan cualidades que no se pueden medir numéricamente de forma natural.
- **Escala Nominal:** Etiquetas sin orden jerárquico. 
    - *Operaciones permitidas:* Conteo, Moda, Coeficientes de contingencia.
    - *Ejemplo:* Tipo de material de un perno (Acero, Aluminio, Titanio).
- **Escala Ordinal:** Existe un orden lógico, pero la distancia entre valores no es uniforme.
    - *Operaciones permitidas:* Medianas, Percentiles, Correlación de Spearman.
    - *Ejemplo:* Grado de falla de un sistema (Crítico, Mayor, Menor).

### 1.2. Variables Cuantitativas (Métricas)
Expresan cantidades numéricas. Se dividen en **Discretas** (conteo finito) y **Continuas** (medición infinita en un rango).
- **Escala de Intervalo:** El cero es arbitrario y no indica ausencia de la propiedad.
    - *Operaciones permitidas:* Media, Desviación Estándar.
    - *Ejemplo:* Temperatura en Celsius. $20^\circ C$ no es "el doble de calor" que $10^\circ C$.
- **Escala de Razón (Ratio):** Posee un cero absoluto (ausencia total).
    - *Operaciones permitidas:* Todas (incluyendo comparaciones de proporción).
    - *Ejemplo:* Corriente eléctrica ($A$), Resistencia ($\Omega$), Tiempo de latencia ($ms$).


# 2. Población ($N$) y Parámetros ($\theta$)

La **Población** es el conjunto universal de todos los elementos con características comunes que se desean estudiar. 
- **Parámetro:** Es una medida numérica que describe una característica de la población completa. Los parámetros suelen ser constantes fijas pero desconocidas.
- **Notación:** Se representan habitualmente con letras griegas ($\mu$ para la media, $\sigma$ para la desviación).

# 3. Muestra ($n$) y Estimadores ($\hat{\theta}$)

La **Muestra** es un subconjunto representativo de la población. 
- **Estadístico (Estimador):** Es una función de los datos de la muestra. A diferencia del parámetro, el estadístico es una **variable aleatoria**, ya que su valor cambia dependiendo de la muestra seleccionada.
- **Notación:** Se representan con letras latinas ($\bar{x}$ para la media muestral, $s$ para la desviación).

# 4. Teoría del Muestreo Probabilístico

Para que la inferencia sea válida, cada elemento de $N$ debe tener una probabilidad $P > 0$ de ser seleccionado.

### 4.1. Muestreo Aleatorio Simple (MAS)
Es la base de la inferencia. Cada muestra de tamaño $n$ tiene la misma probabilidad de ser elegida.
- **Formalidad:** Se utiliza cuando la población es homogénea y se dispone de un marco muestral completo.

### 4.2. Muestreo Estratificado
La población se divide en subgrupos homogéneos llamados **estratos**.
- **Lógica:** Se busca reducir la varianza global asegurando que cada estrato esté representado.
- **Aplicación:** Si el 30% de los usuarios usan Linux y el 70% Windows, la muestra debe respetar esa proporción para evitar sesgos tecnológicos.

### 4.3. Muestreo Sistemático
Se selecciona un punto de partida aleatorio y luego se elige cada $k$-ésimo elemento.
- **Fórmula:** $k = N / n$.
- **Riesgo:** Si existe una periodicidad oculta en los datos (ej. un sensor que falla cada 10 ciclos), el muestreo sistemático puede capturar solo el error o solo el acierto.

### 4.4. Muestreo por Conglomerados (Clusters)
Se seleccionan grupos enteros (conglomerados) en lugar de individuos.
- **Uso:** Eficiencia logística. Es preferible cuando el costo de alcanzar individuos aislados es prohibitivo.

# 5. Muestreo No Probabilístico: El Riesgo del Sesgo

En estos métodos, la probabilidad de selección es desconocida, lo que impide calcular el margen de error.
- **Muestreo por Conveniencia:** Selección basada en la accesibilidad. Útil solo para pruebas piloto.
- **Muestreo por Cuotas:** Intenta imitar al estratificado pero sin aleatoriedad en la selección final.
- **Bola de Nieve:** Los sujetos reclutan a otros sujetos. Común en estudios de poblaciones marginales o redes sociales ocultas.

# 6. Error Muestral vs. Error No Muestral

Un ingeniero debe distinguir entre:
1.  **Error Muestral:** La diferencia natural entre el estadístico y el parámetro. Se reduce aumentando $n$.
2.  **Error No Muestral (Sesgo):** Defectos en el diseño, errores de transcripción o calibración de instrumentos. **No se reduce aumentando la muestra**; se corrige mejorando la metodología.

# 7. Divisiones de la Ciencia Estadística

### 7.1. Estadística Descriptiva
Su objetivo es la **síntesis de información**. Organiza datos mediante tablas de frecuencias y gráficos para describir "lo que ocurrió" en un conjunto cerrado de datos.

### 7.2. Estadística Inferencial (Probabilística)
Utiliza la teoría de la probabilidad para **extrapolar** los resultados de una muestra a la población total. Permite cuantificar el nivel de confianza y el riesgo de error en una predicción.

---

## Resumen Técnico
- La **Escala de Medición** dicta qué test estadístico es aplicable. Nunca promedies variables ordinales.
- El **Muestreo Aleatorio Simple** es el estándar de oro, pero el **Estratificado** suele ofrecer menor error estándar en poblaciones complejas.
- La estadística no elimina la incertidumbre; la **mide** para que podamos gestionar el riesgo.

## Bibliografía
- Montgomery, D. C. & Runger, G. C. - *Applied Statistics and Probability for Engineers*.
- Navidi, W. - *Statistics for Engineers and Scientists*.