# Tecnológico de Software  
## Materia: Fundamentos de Álgebra  
## Alumno: Leonardo Torres Téllez  
## Actividad #23 - Matrices doc  
**Fecha:** 03/12/2025  

# Resolución de sistemas de ecuaciones lineales

El texto desarrolla la resolución de sistemas de ecuaciones lineales mediante métodos matriciales Gauss, Gauss–Jordan, matriz inversa y regla de Cramer y analiza la clasificación de los sistemas según sus soluciones

---

## Ejercicio 1. Sistema (3x3) con distintos métodos

Se considera el sistema

$$
\begin{cases}
x + y + z = 6\\
2x - y + z = 3\\
x + 2y - z = 2
\end{cases}
$$

En forma matricial:

$$
A =
\begin{pmatrix}
1 & 1 & 1 \\
2 & -1 & 1 \\
1 & 2 & -1
\end{pmatrix}
\quad
\mathbf{x} =
\begin{pmatrix}
x \\
y \\
z
\end{pmatrix}
\quad
\mathbf{b} =
\begin{pmatrix}
6 \\
3 \\
2
\end{pmatrix}
\quad
A\mathbf{x} = \mathbf{b}.
$$

### 1.1 Método de Gauss (eliminación)

Se construye la matriz aumentada:

$$
\left[
\begin{array}{ccc|c}
1 & 1 & 1 & 6 \\
2 & -1 & 1 & 3 \\
1 & 2 & -1 & 2
\end{array}
\right]
$$

1. Eliminar la \(x\) de las filas 2 y 3:

$$
R_2 \leftarrow R_2 - 2R_1, \quad
R_3 \leftarrow R_3 - R_1
$$

$$
\longrightarrow
\left[
\begin{array}{ccc|c}
1 & 1 & 1 & 6 \\
0 & -3 & -1 & -9 \\
0 & 1 & -2 & -4
\end{array}
\right]
$$

2. Intercambio de filas para tener un pivote sencillo en la segunda fila:

$$
R_2 \leftrightarrow R_3
\Longrightarrow
\left[
\begin{array}{ccc|c}
1 & 1 & 1 & 6 \\
0 & 1 & -2 & -4 \\
0 & -3 & -1 & -9
\end{array}
\right]
$$

3. Eliminar la \(y\) de la fila 3:

$$
R_3 \leftarrow R_3 + 3R_2
$$

$$
\longrightarrow
\left[
\begin{array}{ccc|c}
1 & 1 & 1 & 6 \\
0 & 1 & -2 & -4 \\
0 & 0 & -7 & -21
\end{array}
\right]
$$

A partir de la forma escalonada:

$$
-7z = -21 \Rightarrow z = 3,
$$

$$
y - 2z = -4 \Rightarrow y - 6 = -4 \Rightarrow y = 2,
$$

$$
x + y + z = 6 \Rightarrow x + 2 + 3 = 6 \Rightarrow x = 1.
$$

Por tanto:

$$
(x,y,z) = (1,2,3).
$$

---

### 1.2 Método de Gauss–Jordan

Partimos de la matriz escalonada obtenida:

$$
\left[
\begin{array}{ccc|c}
1 & 1 & 1 & 6 \\
0 & 1 & -2 & -4 \\
0 & 0 & -7 & -21
\end{array}
\right]
$$

1. Normalizar el pivote de la tercera fila:

$$
R_3 \leftarrow -\tfrac{1}{7} R_3
\Longrightarrow
\left[
\begin{array}{ccc|c}
1 & 1 & 1 & 6 \\
0 & 1 & -2 & -4 \\
0 & 0 & 1 & 3
\end{array}
\right]
$$

2. Eliminar la variable \(z\) en filas 1 y 2:

$$
R_2 \leftarrow R_2 + 2R_3, \quad
R_1 \leftarrow R_1 - R_3
$$

$$
\longrightarrow
\left[
\begin{array}{ccc|c}
1 & 1 & 0 & 3 \\
0 & 1 & 0 & 2 \\
0 & 0 & 1 & 3
\end{array}
\right]
$$

3. Eliminar \(y\) de la primera fila:

$$
R_1 \leftarrow R_1 - R_2
$$

$$
\Longrightarrow
\left[
\begin{array}{ccc|c}
1 & 0 & 0 & 1 \\
0 & 1 & 0 & 2 \\
0 & 0 & 1 & 3
\end{array}
\right]
$$

Solución final:

$$
x = 1, \quad y = 2, \quad z = 3.
$$

---

### 1.3 Método de la matriz inversa
Se tiene:

$$
A =
\begin{pmatrix}
1 & 1 & 1 \\
2 & -1 & 1 \\
1 & 2 & -1
\end{pmatrix}
$$

Determinante por Sarrus:

$$
\det(A) = 1(-1)(-1) + 1(1)(1) + 1(2)(2)
          - 1(-1)(1) - 1(2)(-1) - 1(1)(2)
        = 7
$$

Como $\det(A)\neq 0$, la inversa existe:

$$
A^{-1} = \tfrac{1}{7}
\begin{pmatrix}
-1 & 3 & 2 \\
3 & -2 & 1 \\
5 & -1 & -3
\end{pmatrix}
$$

Multiplicación $A^{-1}\mathbf{b}$:

$$
A^{-1}\mathbf{b}
= \tfrac{1}{7}
\begin{pmatrix}
-1 & 3 & 2 \\
3 & -2 & 1 \\
5 & -1 & -3
\end{pmatrix}
\begin{pmatrix}
6 \\ 3 \\ 2
\end{pmatrix}
$$

Producto:

$$
\begin{pmatrix}
7 \\ 14 \\ 21
\end{pmatrix}
$$

Aplicar $\tfrac{1}{7}$:

$$
\mathbf{x} =
\begin{pmatrix}
1 \\ 2 \\ 3
\end{pmatrix}
$$

### 1.4 Regla de Cramer

Matrices:

$$
A =
\begin{pmatrix}
1 & 1 & 1 \\
2 & -1 & 1 \\
1 & 2 & -1
\end{pmatrix}, \quad
\mathbf{b} =
\begin{pmatrix}
6 \\ 3 \\ 2
\end{pmatrix}.
$$

Determinante:

$$
D = 7
$$

Matrices modificadas:

$$
A_x =
\begin{pmatrix}
6 & 1 & 1 \\
3 & -1 & 1 \\
2 & 2 & -1
\end{pmatrix},
$$

$$
A_y =
\begin{pmatrix}
1 & 6 & 1 \\
2 & 3 & 1 \\
1 & 2 & -1
\end{pmatrix},
$$

$$
A_z =
\begin{pmatrix}
1 & 1 & 6 \\
2 & -1 & 3 \\
1 & 2 & 2
\end{pmatrix}.
$$

Determinantes:

$$
D_x = 7, \quad D_y = 14, \quad D_z = 21
$$

Solución:

$$
x = 1, \quad y = 2, \quad z = 3.
$$

---

## Ejercicio 2. Clasificación de sistemas

### 2.1 Sistema (a)

$$
\begin{cases}
x + y = 3 \\
2x + 2y = 6
\end{cases}
$$

Matriz aumentada:

$$
\left[
\begin{array}{cc|c}
1 & 1 & 3 \\
2 & 2 & 6
\end{array}
\right]
$$

Resultado:

$$
\left[
\begin{array}{cc|c}
1 & 1 & 3 \\
0 & 0 & 0
\end{array}
\right]
$$

Sistema con infinitas soluciones.

---

### 2.2 Sistema (b)

$$
\begin{cases}
x + y = 3 \\
2x + 2y = 7
\end{cases}
$$

$$
\left[
\begin{array}{cc|c}
1 & 1 & 3 \\
2 & 2 & 7
\end{array}
\right]
$$

$$
\left[
\begin{array}{cc|c}
1 & 1 & 3 \\
0 & 0 & 1
\end{array}
\right]
$$

Sistema incompatible: sin solución.

---

### 2.3 Sistema (c)

$$
\begin{cases}
x + y = 3 \\
x - y = 1
\end{cases}
$$

$$
\left[
\begin{array}{cc|c}
1 & 1 & 3 \\
1 & -1 & 1
\end{array}
\right]
$$

Paso 1:

$$
\left[
\begin{array}{cc|c}
1 & 1 & 3 \\
0 & -2 & -2
\end{array}
\right]
$$

Normalizar:

$$
\left[
\begin{array}{cc|c}
1 & 1 & 3 \\
2 & 2 & 6
\end{array}
\right]
$$
