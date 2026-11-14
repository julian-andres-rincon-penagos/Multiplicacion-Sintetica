# Algoritmo de la Multiplicación Sintética

Proyecto de investigación educativa, desarrollo algorítmico y artículo científico sobre la **Multiplicación Sintética**, un método sistemático e iterativo para construir los coeficientes de una función polinómica a partir de sus raíces conocidas.

## Historia y Motivación

Este algoritmo nació alrededor de **2018** durante la enseñanza del curso de **Cálculo Diferencial** en la **Universidad del Quindío**, ante la necesidad de generar funciones polinómicas aleatorias con raíces reales conocidas para que los estudiantes pudieran practicar el cálculo de cortes con el eje $x$ y la factorización mediante el algoritmo de la **División Sintética**.

En una primera aproximación se emplearon expresiones paramétricas explícitas como la forma cuadrática:

$$f(x) = (x - a)(x - b) = x^2 - (a + b)x + ab, \quad a, b \in [-n, n]$$

Si bien este enfoque resulta práctico para polinomios de grado $2$ y $3$, la expansión simbólica se vuelve engorrosa para funciones de **grado $4$ o superior**. La **Multiplicación Sintética** resuelve este problema ejecutando el algoritmo de la División Sintética en sentido inverso.

## ¿Cómo funciona el algoritmo?

Dada una lista unidimensional de raíces $x = r_1, r_2, \dots, r_n$:

1. Se inicia con el arreglo de coeficientes $[1]$.
2. Para cada raíz $r_k$, se forma el factor lineal $(x - r_k)$ y se utiliza el número $-r_k$ como multiplicador.
3. En cada iteración se multiplican los coeficientes actuales por $-r_k$, ubicando los productos desplazados una posición en la diagonal hacia abajo, y se suman los valores columna a columna.
4. Tras $n$ ciclos, se obtiene el arreglo final con los $n + 1$ coeficientes del polinomio.

### Ejemplo con raíces $x = 2, 3, 5, 7$

| Paso | Factor | Multiplicador | Coeficientes resultantes | Polinomio parcial |
| :---: | :---: | :---: | :--- | :--- |
| Inicio | — | — | $[1]$ | $1$ |
| 1 | $x - 2$ | $-2$ | $[1, -2]$ | $x - 2$ |
| 2 | $x - 3$ | $-3$ | $[1, -5, 6]$ | $x^2 - 5x + 6$ |
| 3 | $x - 5$ | $-5$ | $[1, -10, 31, -30]$ | $x^3 - 10x^2 + 31x - 30$ |
| 4 | $x - 7$ | $-7$ | $[1, -17, 101, -247, 210]$ | $x^4 - 17x^3 + 101x^2 - 247x + 210$ |

Además, al combinar este algoritmo con la **División Sintética**, es posible evaluar cualquier polinomio numéricamente y de forma exacta en un instante, y verificar por deflación sucesiva cada una de las raíces generadas.

## Estructura del Repositorio

- [`Definicion/Definicion.md`](Definicion/Definicion.md): Relato original con la historia y descripción conceptual del algoritmo.
- [`Multiplicacion_Sintetica.ipynb`](Multiplicacion_Sintetica.ipynb): Cuaderno de Jupyter interactivo con la explicación teórica, implementación paso a paso en Python, generador de polinomios aleatorios con raíces en $[-n, n]$ y verificación exacta mediante División Sintética.
- [`Algoritmo-Multiplicacion-Sintetica.lyx`](Algoritmo-Multiplicacion-Sintetica.lyx): Artículo académico completo escrito en formato **LyX 2.4** utilizando la plantilla editorial del proyecto.
- `Plantilla.cls`, `Plantilla.sty`, `Plantilla.layout`: Archivos de clase, estilo y diseño para la compilación del artículo en LyX/LaTeX.

## Autor

**Julián Andrés Rincón Penagos**  
Universidad del Quindío — Facultad de Ciencias Básicas y Tecnologías
