---
tags:
- EstructurasLogicas
---

# ESL.1.2.Tipos de Datos

# 1. Tipos de Datos en Programacion

Los tipos de datos definen el conjunto de valores que una variable puede almacenar y las operaciones que se pueden realizar con ellas. Son fundamentales para la asignacion de memoria y la validacion de operaciones.

# 2. Clasificacion de Tipos de Datos

## 2.1. Tipos Primitivos

Tipos basicos proporcionados directamente por el lenguaje.

### 2.1.1. Enteros

Almacenan numeros enteros sin parte decimal.

**Ejemplo:**

```c
char c = 'A';
short s = 1000;
int i = 100000;
long l = 1000000L;
```

### 2.1.2. Punto Flotante

Almacenan numeros reales con parte decimal.

**Ejemplo:**

```c
float f = 3.1416f;
double d = 3.1415926535;
```

### 2.1.3. Caracter

Almacenan un solo caracter.

**Ejemplo:**

```c
char letra = 'A';
char numero = '7';
char simbolo = '$';
```

### 2.1.4. Booleano

Almacenan valores verdadero o falso.

**Ejemplo:**

```java
boolean esValido = true;
boolean isEmpty = false;
```

### 2.2. Tipos Compuestos

Estructuras que contienen multiples valores.

### 2.2.1. Arreglos (Arrays)

Coleccion de elementos del mismo tipo.

**Ejemplo:**

```c
int numeros[5] = {1, 2, 3, 4, 5};
char nombre[20] = "Juan";
float temperaturas[7] = {20.5, 22.1, 19.8, 21.3, 23.0, 20.7, 19.5};
```

### 2.2.2. Cadenas (Strings)

Secuencia de caracteres.

**Ejemplo:**

```c
char saludo[] = "Hola Mundo";
char nombre[50];
```

### 2.2.3. Estructuras (Structs)

Agrupan datos de diferentes tipos.

**Ejemplo:**

```c
struct Persona {
    char nombre[50];
    int edad;
    float altura;
};

struct Persona usuario;
strcpy(usuario.nombre, "Maria");
usuario.edad = 25;
usuario.altura = 1.65;
```

## 2.3. Tipos Derivados

Se construyen a partir de otros tipos.

### 2.3.1. Punteros

Almacenan direcciones de memoria.

**Ejemplo:**

```c
int x = 10;
int *ptr = &x;
*ptr = 20;
```

### 2.3.2. Enumeraciones

Conjunto de constantes con nombre.

**Ejemplo:**

```c
enum DiaSemana { LUNES, MARTES, MIERCOLES, JUEVES, VIERNES, SABADO, DOMINGO };
enum DiaSemana hoy = MARTES;
```

## 2.4. Tipos Abstractos de Datos (TAD)

Definen operaciones sin especificar implementacion.

### 2.4.1. Listas

Coleccion ordenada de elementos.

**Ejemplo conceptual:**

```
Operaciones: insertar, eliminar, buscar, recorrer
```

### 2.4.2. Pilas (Stack)

LIFO (Last In, First Out).

**Ejemplo operaciones:**

```java
stack.push(elemento);
stack.pop();
stack.peek();
```

### 2.4.3. Colas (Queue)

FIFO (First In, First Out).

**Ejemplo operaciones:**

```java
queue.enqueue(elemento);
queue.dequeue();
queue.front();
```

# 3. Caracteristicas de los Tipos de Datos

## 3.1. Tamaño en Memoria

**Ejemplo:**

```c
printf("char: %zu bytes\n", sizeof(char));
printf("int: %zu bytes\n", sizeof(int));
printf("float: %zu bytes\n", sizeof(float));
```

## 3.2. Conversion de Tipos

### 3.2.1. Implicita (Automatica)

**Ejemplo:**

```c
int entero = 10;
float decimal = entero;
```

### 3.2.2. Explicita (Casting)

**Ejemplo:**

```c
float precio = 19.99;
int precio_entero = (int)precio;
```

# 4. Eleccion del Tipo Adecuado

## 4.1. Ejemplos Practicos

**Para contadores:**

```c
unsigned int contador = 0;
```

**Para calculos financieros:**

```java
double saldo = 1234.56;
```

**Para banderas/estados:**

```c
bool estadoActivo = true;
```

## 4.2. Buenas Practicas

**Nomenclatura:**

```java
int contadorEstudiantes;
final double PI = 3.1416;
```

**Inicializacion:**

```c
int total = 0;
char buffer[100] = {0};
float promedio = 0.0f;
```

---

# Resumen

## Tipos Primitivos
- **Enteros:** char, short, int, long
- **Punto flotante:** float, double  
- **Caracter:** char
- **Booleano:** bool

## Tipos Compuestos
- **Arreglos:** Coleccion homogenea
- **Cadenas:** Secuencia de caracteres
- **Estructuras:** Agrupacion heterogenea

## Tipos Derivados
- **Punteros:** Direcciones de memoria
- **Enumeraciones:** Constantes con nombre

## Consideraciones Clave
- Elegir tipo segun rango y precision requeridos
- Inicializar siempre las variables
- Usar casting explicito cuando sea necesario
- Considerar el consumo de memoria
- Validar rangos antes de operaciones criticas

## Impacto en el Desarrollo
- **Eficiencia:** Uso optimo de memoria
- **Confiabilidad:** Prevencion de errores
- **Mantenibilidad:** Codigo claro y comprensible
- **Portabilidad:** Compatibilidad entre sistemas
