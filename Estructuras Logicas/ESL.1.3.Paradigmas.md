# 1. Paradigmas de Programacion
Un paradigma de programacion es un estilo fundamental para construir programas de computadora. Define como los programadores organizan el codigo y resuelven problemas.
## 1.1. Programacion Estructurada
La programacion estructurada se basa en la organizacion del codigo en bloques logicos mediante funciones y procedimientos. Su principio fundamental es dividir programas complejos en partes mas pequenas y manejables.
**Caracteristicas principales:**
- Uso de tres estructuras de control: secuencia, seleccion, iteracion
- Datos y funciones separados
- Evitar el uso de GOTO
- Facil depuracion y mantenimiento
**Ejemplo en C:**
```c
#include <stdio.h>

// Funcion que calcula el factorial
int factorial(int n) {
    int resultado = 1;
    for (int i = 1; i <= n; i++) {
        resultado *= i;
    }
    return resultado;
}

int main() {
    int numero = 5;
    int fact = factorial(numero);
    printf("Factorial de %d es %d\n", numero, fact);
    return 0;
}
```
## 1.2. Programacion Orientada a Objetos
La programacion orientada a objetos modela el software como una coleccion de objetos que interactuan entre si. Cada objeto encapsula datos y comportamientos relacionados.
### 1.2.1. Los cuatro pilares fundamentales:
- **Abstraccion**: Simplificar la realidad extrayendo caracteristicas esenciales
- **Encapsulamiento**: Ocultar los detalles internos de implementacion
- **Herencia**: Crear nuevas clases basadas en clases existentes
- **Polimorfismo**: Objetos de diferentes tipos que responden al mismo mensaje
**Ejemplo:**
```java
public class Vehiculo {
    private String marca;
    private int velocidad;
    
    public void acelerar() {
        velocidad += 10;
    }
}
```
## 1.3. Programacion Funcional
La programacion funcional trata la computacion como la evaluacion de funciones matematicas, evitando el cambio de estado y los datos mutables.
**Principios clave:**
- Funciones como ciudadanos de primera clase
- Inmutabilidad de datos
- Ausencia de efectos secundarios
- Composicion de funciones
# 2. Comparacion entre Paradigmas
|Aspecto	|Programacion Estructurada	|Programacion Orientada a Objetos|
|-|-|-|
|Enfoque	|Procedimientos y funciones	|Objetos y sus interacciones|
|Datos	|Separados del comportamiento	|Integrados en objetos|
|Reutilizacion	|Funciones y bibliotecas	|Herencia y composicion|
|Modelado|	Basado en procesos|	Basado en entidades del mundo real|
## 2.1. Cuando usar cada paradigma:
- **Estructurada**: Sistemas embebidos, programas de sistema, aplicaciones de rendimiento critico
- **Orientada a Objetos**: Sistemas empresariales, interfaces graficas, aplicaciones complejas
- **Funcional**: Procesamiento de datos, sistemas concurrentes, aplicaciones matematicas
---
#Resumen
La programacion estructurada organiza el codigo en funciones y usa control de flujo lineal. 
La orientada a objetos modela sistemas mediante objetos con datos y comportamiento. 
La programacion funcional se basa  en funciones matematicas inmutables. 
Cada paradigma es adecuado para diferentes tipos de problemas y contextos de desarrollo.
