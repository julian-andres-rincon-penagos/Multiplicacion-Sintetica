# Multiplicación Sintética

Cuando empece a dar clases de cálculo diferencial en la Universidad del Quindío, cerca del 2018 vi la necesidad de generar funciones polinómicas aleatorias para los estudiantes con el fin de que ellos pudieran encontrar las raíces, cortes con el eje $x$ y para ello usar el algoritmo de la División Sintética.

Mi primera idea consistio en definir parámetros generales, por ejemplo para la función cuadrática $$f(x) = (x=a)(x=b)$$ Lo que resulta en $$f(x) = (x-a)(x-b)$$ Obteniendo la función cuadrática $$f(x) = x^2-(a+b)x+ab$$ Este resultado es muy bueno para generar funciones cuadráticas aleatorias poniendo los valores de $a$ y $b$ dentro de una lista de números aleatorios enteros por ejemplo $a,b\in[-n,n]$

Este método funciona muy bien para funciones cuadrática y depronto para cúbicas. El problema se acrecenta cuando queremos generar funciones de grado cuatro o superior.

Mi idea para resolver esto consistio en usar el algoritmo de la División Sintética al revez. Por ejemplo si mis raíces son $x=2,3,5,7$ entonces empezamos con un coeficiente $1$ y al frente de la tabla $x-2$, término que sale de $x=2$, transponiendo el $2$ al lado de la $x$. Para la multiplicación usamos únicamente el número $-2$. Decimos $-2$ por $1$ y el resultado en la diagonal bajando, lo que resulta en: $1,-2$. El siguiente factor es $x-3$, entonces decimos $-3$ por $1$ es $-3$, resultado en la diagonal abajo, luego $-3$ por $-2$ es $6$, resultado en al diagonal abajo, luego se suman los números en cada columna y tenemos los coeficientes $1,-5,6$. Este proceso se repite hasta terminar con la última raíz.

Como podemos observar este proceso es cíclico y ordenado. Si tenemos las raíces en un arreglo unidimensional haciendo un ciclo de $n$ pasos donde $n$ es la cantidad de raíces obtendremos al final un arreglo con los coeficientes del polinomio.

Esto además resulta muy interesante porque usando el algoritmo de la División Sintética podemos evaluar un polinomio numéricamente y de forma exacta en un instante.