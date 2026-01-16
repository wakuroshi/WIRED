# 1.Transformaciones Sintácticas
![[WIRED/Media/LOG.5.2.fa.png]]
**Transformaciones Sintácticas.**
>  Fórmulas
>  Axiomas

**Consistencia:**
	Propiedad de decisión de demostración de un sistema
	- Un sistema Formal es consistente si no se puede demostrar una contradicción dentro de el.


TODO: Teorema de Gödel
# 2.Teoremas
## 2.1.Teorema de Gödel
El teorema de incompletitud de Gödel indica que en un sistema axiomático consistente que cumpla con los axiomas de Peano (axiomas de aritmética), es incompleto en esencia, es decir, siempre habrán proposiciones verdaderas que no podrán demostrarse ni refutarse en el propio sistema. Los sistemas no pueden demostrar propia consistencia mediante sus reglas. 

Se  puede concluir que los sistemas requieren verdades axiomáticas sin demostración para poder sustentarse a sí mismos incluso si esas verdades no están demostradas, lo que puede generar contradicciones. Si un sistema Z es autoconsistente, este no puede generar en Z una proposición que afirme la consistencia de Z.

Por ejemplo, el enunciado: Esta proposición es falsa, si es falsa entonces es verdadera, pero si es verdadera entonces es falsa. La proposición se rige desde sus principios, pero estos mismos principios no son demostrables, tanto su certeza como su error; en las matemáticas y la lógica las verdades son relativas, no absolutas, un ejemplo sería la física clásica/newtoniana y la física relativista, al final la clásica es funcional para una gran parte del cálculo, sin embargo, no describe el todo, por lo mismo, la física relativista está incompleta, motivo por el cual es casi imposible encontrar una teoría del todo.

$T: \neg \Box F$
$T \models cons(T) \rightarrow G$
$T \models cons(T) \rightarrow T \Rightarrow F$

# 3.Sistema
## 3.1.Sistema de Lámpara
Atributos:
	- Lámpara
	- Bombillo
	- Electricidad
Acciones:
	- Encender
	- Apagar
	- Dañado
	- Bueno