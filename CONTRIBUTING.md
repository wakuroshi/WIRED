---
tags: #docs
---

# CONTRIBUTING

Este documento describe el flujo de trabajo con **Git** y **GitHub** para contribuir al repositorio **WIRED**.  
Aplica a colaboradores internos, contribuyentes externos y usuarios que deseen reportar errores.

# 1. Contribuyentes internos

## 1.1. Clonar el repositorio

### 1.1.1. En Linux

```bash
git clone https://github.com/wakuroshi/WIRED.git
cd WIRED
```

### 1.1.2. En Windows

1. Instalar **Git for Windows** 
2. Abrir **Git Bash** o **PowerShell**
3. Ejecutar los mismos comandos anteriores

## 1.2. Actualizar el repositorio local

Antes de comenzar o enviar cambios:

```bash
git pull origin main
```

Si estás en otra rama:
```bash
git fetch origin
git rebase origin/main
```

## 1.3. Crear una nueva rama

Antes de realizar cambios, crea una **rama descriptiva**:

```bash
git checkout -b nombre-de-rama
```

Ejemplos:

```
git checkout -b correccion-redes
git checkout -b añadido-logica
```

## 1.4. Realizar cambios y confirmarlos

1. Edita o agrega tus archivos [Aqui mas informacion respecto al formato](./FORMATTING.md).  
2. Guarda tus cambios y agrégalos:
 
```bash
git add archivo1.md archivo2.md ... 
```
> Si deseas añadir todos los archivos seria git add .

3. Crea un commit con mensaje descriptivo:

```bash
git commit -m "Corrijo fórmulas de redes de dos puertos"
```

## 1.5. Enviar los cambios a GitHub

Sube la rama al repositorio remoto:
```bash
git push origin nombre-de-rama
```

Esto generará un enlace en la terminal para crear un **Pull Request (PR)**.

## 1.6. Crear un Pull Request

1. Abre el repositorio en GitHub.  
2. Haz clic en **"Compare & pull request"**.  
3. Añade un título y descripción claros.  
4. Envía el PR para revisión.

### Ejemplo:

**Título:** Corrijo condiciones de tabla de parámetros Z y Y  
**Descripción:**
- Se corrige uso del símbolo | en ecuaciones.
- Se ajustan las condiciones de puerto abierto/corto.

## 1.7. Mantener la rama limpia

Después de fusionar tu PR, elimina la rama local y remota:
```bash
git branch -d nombre-de-rama
git push origin --delete nombre-de-rama
```
# 2. Contribuyentes externos

Si no eres colaborador directo del proyecto:

1. Haz un **fork** del repositorio.  
2. Clona tu fork:

```bash
git clone https://github.com/tu-usuario/WIRED.git
```

3. Crea una rama con tus cambios:

```bash
git checkout -b propuesta-tema-nuevo
```

4. Realiza tus cambios y envía un **Pull Request** al repositorio original.

# 3. Usuarios no colaboradores

Si no deseas modificar archivos directamente, puedes contribuir reportando problemas o sugerencias.

Abre un **Issue** en GitHub para:
- Reportar errores o inconsistencias.
- Proponer nuevos temas o correcciones.
- Reportar enlaces o fórmulas rotas.
- Proponer Media como un Banner, scripting, etc.

# 4. Buenas prácticas con Git

| Acción | Comando | Descripción |
|:--|:--|:--|
| Ver estado | `git status` | Revisa cambios pendientes |
| Ver historial | `git log --oneline` | Muestra commits recientes |
| Cancelar cambios | `git restore archivo.md` | Revertir modificaciones locales |
| Actualizar sin conflictos | `git pull --rebase` | Sincroniza tu rama |
| Ver ramas | `git branch -a` | Lista ramas locales y remotas |

---

Gracias por contribuir al desarrollo y mantenimiento de **WIRED**.
