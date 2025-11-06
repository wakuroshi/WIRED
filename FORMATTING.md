---
tags: 
- docs
---

# FORMATTING

Este documento define como escribir, estructurar y dar formato a las notas de este repositorio.

# 1. Estructura general

Cada nota debe:

- Estar en formato **.md** (markdown)
- Comenzar con el **nombre de la nota en forma de Titulo** para facilitar la busqueda a traves de texto en archivos.
- Luego, comenzar con un **Titulo princpal** (# x. Titulo)
- Organizar el contenido con subtitulos jerarquicos (##x.y. Subtitulo, ###x.y.z Subtitulo 2, etc.)
- Mantener coherencia visual con el resto de las notas.

## 1.1. Estructura de los archivos

### 1.1.1. Nombre de las notas 

**ABC.x.y.z.Titulo**:

- **ABC**: Se refiere a la materia a la que pertenece la nota. Ej: Logica -> LOG.
- **x.y.z**: Se refiere a la jerarquia de la nota, funciona de igual manera que los titulos. Donde:
    - **x**: Representa la unidad.
    - **y**: Representa el tema principal.
    - **z**: Representa un subtema. (preferiblemente usar esto para ejercicios y/o ejemplificaciones del tema)
- **Titulo**: Se refiere al tema concreto de la nota, esto ayuda a que se pueda estudiar temas y sub-temas en profundidad.

### 1.1.2. Nombre de los archivos de media y scripts

Siguen una estructura igual a la de las notas, pero cambiando el Titulo por el descriptor (si es script o archivo media) y su localizacion (primer archivo de media, segundo, etc). ABC.x.y.z.**fa** o ABC.x.y.z.**sa**:

- **fa**: El descriptor **f** hace referencia a *figura*, pero por simplicidad se utiliza para describir el hecho de que el archivo es de media (.png, .gif, .jpg, etc), la letra **a** se refiere a que es la primera *figura* dentro de esa nota, la b seria la segunda, c terca... Similar a como se hace referencia a diagramas en un libro de ciencias. Ej: [Interseccion](./Media/CALI.1.1.fc.png) *CALI.1.1.fc* hace referencia a que la imagen, que representa una Interseccion, esta en la nota **CALI.1.1** y es la **tercera figura** (fc) de esta nota.
- **sa**: Exactamente igual al de media, pero el descriptor **s** indica que es un script, y la letra **a** indica que es el script **usado para generar la primera figura** de esa nota.

> Nota: Por favor dejar un espacio en blanco de por medio entre una imagen y el texto que la rodea, asi la imagen se renderiza sin ningun error por tener el texto justo debajo.

Ejemplo completo de una nota: [LOG.1.1.Logica](./Logica/LOG.1.1.Logica.md) 

# 2. Estilo de escritura

- Frases concisas, claras.  
- No usar emojis ni adornos innecesarios, esto ayuda a mantener la compatibilidad del repositorio.  
- Evitar el uso de primera persona.  
- Usar **negritas** para resaltar conceptos o terminos importantes, e *italicas* para efectos secundarios.  
- Evitar abusar del subrayado, italicas o negritas.  
- No usar algun plugin externos de Obsidian que afecten a la nota, si se quiere insertar graficos, figuras o animaciones ilustrativas, se coloca en un formato soportado por la sintaxis nativa de markdown. Ej: Hacer la figura con Excalidraw, y se adjunta el png generado en la nota para mayor compatibilidad

# 3. Formato matematico y logico

- Escribir simbolos y formulas en formato LaTeX:  
  - Inline: `$A \land B$`  
  - En bloque:  
    
    $$
    \sum{a_{n}}
    $$

# 4. Tablas y listas

## 4.1. Tablas
Usar tablas Markdown para organizar informacion (simbolos, reglas, jerarquias, etc.)  
Mantener encabezados alineados o centrados de ser posible.

| Tipo de Simbolo | Simbolo | Función |
|:----------------:|:--------:|:--------|
| Variable | P, Q | Representa una proposición |

## 4.2. Listas
Usar listas con guiones (`-`) para puntos concisos, y numeradas (`1.`) para pasos secuenciales o conceptos enlistados.

# 5. Media

Usar enlaces relativos o incrustaciones de imagen con sintaxis estándar:

  ```markdown
  ![Diagrama](../Media/nombre-archivo.png)
  ```

Todas las imagenes van a [Media](./Media/)

## 5.1. Scripts

En caso de que el archivo de media sea generado con un script, se hace referencia para facilmente poder modificar la imagen a traves del script. Preferiblemente documentar el script en caso de ser necesario.

```markdown
![Grafica Animada](../nombre-archivo.gif)

*Generado con*: [Script.py](../Scripts/nombre-script.py)
```

# 6. Ejercicios

- Incluir preguntas con opciones claras (si aplica).  
- Destacar la **respuesta correcta** al final.  
- Si el ejercicio tiene explicación, colocarla inmediatamente después.

Ejemplo:

```markdown
**Ejercicio:**
¿Preguntas?

**a)** 2  
**b)** 3  
**c)** 4  
**d)** 5  

**Respuesta:** c 
Explicacion...
```

# 7. Convenciones recomendadas

- Secciones en singular (`Regla`, `Ejemplo`, `Convención`) salvo que agrupen varios puntos.  
- Cada nota debe ser autocontenida (Abordar el tema especificado).  
- Si una nota depende de otra, o se evita redundancia a algo ya explicado en otra nota, referenciar a la misma:
  ```markdown
  Ver también: [LOG.1.2.Operadores.md](LOG.1.2.Operadores.md)
  ```

# 8. Tags y metadata

**WIP**, por ahora solo se incluye como metadata el nombre de la materia a la cual pertenece la nota, o su categoria (Index, docs) posteriormente se deberian ir generando mas. Ej:
**Al inicio del archivo**:

```yaml
---
tags: 
- docs 
---
```

Al colocarse de esta manera la metadata no aparecera ni interferira al leerla en software como Obsidian o similares, siendo igualmente facil de editar y agrupar notas a traves de su metadata.
