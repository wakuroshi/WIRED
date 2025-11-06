---
tags:
- Programacion/Java
---

# JAV.1.1.Datos

# 1. Tipos de Datos en Java

Para saber mas respecto a los tipos de datos en general, ir a [[../../Estructuras Logicas/ESL.1.2.Tipos de Datos]]

## 1.1 Tipos Primitivos

- **Enteros**

```java
byte edad = 25;        // 1 byte (-128 a 127)
short año = 2024;      // 2 bytes (-32,768 a 32,767)  
int cantidad = 1000;   // 4 bytes (-2^31 a 2^31-1)
long grande = 100000L; // 8 bytes (-2^63 a 2^63-1)
```

- **Decimales**

```java
float precio = 19.99f;   // 4 bytes (6-7 digitos)
double total = 99.99;    // 8 bytes (15-16 digitos)
```

- **Otros Primitivos**

```java
char letra = 'A';        // 2 bytes (caracter Unicode)
boolean activo = true;   // 1 bit (true/false)
```

## 1.2 Tipos Referencia (Compuestos)

- **Strings**

```java
String nombre = "Juan";
String apellido = new String("Perez");
```

- **Arreglos**
 
```java
int[] numeros = {1, 2, 3};
String[] nombres = new String[5];
```
- **Colecciones**

```java
ArrayList<Integer> lista = new ArrayList<>();
HashMap<String, Integer> mapa = new HashMap<>();
```

## 1.3 Conversiones de Tipo (Casting)

- **Implicito (Automatico)**

```java
int entero = 10;
double decimal = entero;  // 10.0
```

- **Explicito (Manual)**

```java
double precio = 19.99;
int entero = (int) precio;  // 19
```

- **Entre String y Numeros**

```java
String texto = "100";
int numero = Integer.parseInt(texto);
String texto2 = String.valueOf(numero);
```

## 1.4 Valores por Defecto

| Tipo                   | Valor Default |
| ---------------------- | ------------- |
| byte, short, int, long | 0             |
| char                   | '\u0000'      |
| boolean                | false         |
| Object                 | null          |

# 2. Operaciones Basicas
# 
## 2.1 Aritmeticas

```java
int suma = a + b;
int resta = a - b;
int multiplicacion = a * b;
double division = a / b;
int modulo = a % b;
```

## 2.2 Comparacion

```java
boolean igual = (a == b);
boolean diferente = (a != b);
boolean mayor = (a > b);
boolean menor = (a < b);
```

## 2.3 Logicas
```java
boolean and = (a && b);
boolean or = (a || b);
boolean not = (!a);
```

---

# Resumen

Java tiene tipos primitivos (byte, int, float, char, boolean) y tipos  referencia (String, arrays, objetos). Los primitivos tienen valores por defecto y se almacenan directamente, mientras las referencias almacenan direcciones a objetos. 

Soporta casting implicito y explicito para conversion entre tipos.
