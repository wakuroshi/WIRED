---
materia: Programación Java
id: JAV.4.2
tema: Interfaces Gráficas de Usuario (GUI) con Swing
status: Revision
tags:
  - java
  - gui
  - swing
  - awt
  - events
---

# JAV.4.2. Ambiente Gráfico (GUI / IGU)

> [!abstract]- Interacción Humano-Computador
> El desarrollo de GUIs en Java permite crear aplicaciones visuales interactivas. Aunque existen librerías modernas como JavaFX, **Swing** sigue siendo el estándar académico y de mantenimiento industrial por su robustez y ligereza sobre la base de AWT.

# 1. Librerías de Interfaz en Java

1.  **AWT (Abstract Window Toolkit):** La librería original. Usa componentes nativos del Sistema Operativo (pesada y poco flexible).
2.  **Swing:** Construida sobre AWT. Es "Pluggable Look and Feel" (los componentes se dibujan en Java), lo que la hace multiplataforma.
3.  **JavaFX:** La evolución moderna con soporte para CSS y aceleración por hardware.

# 2. Los Tres Pilares de Swing

Para construir una interfaz, necesitamos tres elementos trabajando en conjunto:

### 2.1. Contenedores
Son los marcos que sostienen la aplicación.
- `JFrame`: La ventana principal (con botones de cerrar, minimizar).
- `JPanel`: Un contenedor intermedio para organizar elementos dentro del frame.

### 2.2. Componentes (Widgets)
Los elementos con los que el usuario interactúa.
- `JLabel`: Texto estático.
- `JButton`: Botones de acción.
- `JTextField`: Campos de entrada de texto de una línea.

### 2.3. Eventos (Listeners)
La lógica que responde a la interacción. Java utiliza el patrón **Observer** para "escuchar" cuando un usuario hace clic en un botón.



# 3. Ejemplo de Implementación Base

```java
import javax.swing.*;
import java.awt.event.*;

public class MiVentana extends JFrame {
    public MiVentana() {
        // 1. Configuración del contenedor
        setTitle("Sistemas de Ingeniería");
        setSize(300, 200);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        setLayout(null);

        // 2. Creación de componentes
        JButton boton = new JButton("Calcular");
        boton.setBounds(100, 50, 100, 30);

        // 3. Manejo de Eventos
        boton.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                JOptionPane.showMessageDialog(null, "Procesando datos...");
            }
        });

        add(boton);
        setVisible(true);
    }

    public static void main(String[] args) {
        new MiVentana();
    }
}
```

> [!question]- Layout Managers
> En aplicaciones profesionales, no se usa `setLayout(null)`. Se usan **Layout Managers** (`BorderLayout`, `GridLayout`, `BoxLayout`) que ajustan automáticamente el tamaño de los componentes cuando el usuario cambia el tamaño de la ventana.

---

## Resumen

- **Jerarquía**: Los componentes se agregan a paneles, y los paneles a ventanas.
- **Hilos**: Swing no es "thread-safe". Toda actualización de la interfaz debe hacerse en el hilo especial llamado *Event Dispatch Thread (EDT)*.
- **Eventos**: La separación entre la vista (GUI) y la lógica (Eventos) es el primer paso hacia arquitecturas como MVC (Modelo-Vista-Controlador).

## Bibliografía
1. Geary, D. M. (1999). *Graphic Java 2, Volume 2: Swing*. Prentice Hall.
2. Oracle. (2024). *Creating a GUI With JFC/Swing*.