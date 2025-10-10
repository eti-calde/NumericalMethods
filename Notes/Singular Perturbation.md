# Objetivo/ Motivación
Tenemos una ecuación que describe algun fenomeno, una de las variables esta multiplicada por un factor $\epsilon$ pequeño, lo cual nos da la idea de despreciar esa variable de la ecuación.

La perturbación singular nos ayuda a averiguar si realmente ese termino es despreciable.

la diferencia con [[Perturbación Regular]] es que el factor epsilon puede estar multiplicando una variables con varias raices, por ejemplo, $\epsilon x^2$
# Procedimiento

## 1. Hacer una [[Perturbación Regular]]
ejemplo:

$$
x = (x_0+ \epsilon x_1 + \epsilon^2 x_2 + \dots)
$$

## 2. Agrupar los términos según ordenes
- Utilizando la expansión se llega a una nueva ecuación donde podemos agrupar los terminos de mismo orden y llegar a nuevas ecuaciones
- Agrupar por orden $O(1),O(\epsilon),O(\epsilon^2),\dots$
- Eso nos va a llevar a encontrar los valores de $x_0,x_1,x_2,\dots$
- con lo cual podemos formar: 
 $$
x = (x_0+ \epsilon x_1 + \epsilon^2 x_2 + \dots)
$$
- llegamos a una solución, pero sabemos que x tiene más de 1.

## 3. Análisis de magnitudes
- Se toman los grupos de los términos que componen la ecuacion original y se asume que un grupo es mucho menor al otro, por ejemplo:
$$
1,2x << \epsilon x^2
$$
lo cual no lleva a poder eliminar los terminos pequeños y por ende, llegar a una nueva solución, la cual puede ser incongruente con la suposición inical.
- Hasta llegar a un supoción que nos lleve a una solución nueva a priori congruente
## 4. Comprobar si realmente es congruente
- se define una nueva escala para la variable:
$$
\begin{align*}
y &= \frac{x}{new\;solution} \\
x &= y * \;new\;solution
\end{align*}
$$

- se reemplaza la nueva variable en la ec original
- se aplica una [[Perturbación Regular]] con la nueva variable

$$
y = (y_0+ \epsilon y_1 + \epsilon^2 y_2 + \dots)
$$
- se repite el procedimiento de agrupar por ordenes de magnitud y llegar a una nueva solución


# Ejercicio
