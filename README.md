# Tecnológico de Software  
## Materia: Fundamentos de Álgebra  
## Alumno: Leonardo Torres Téllez  
## Actividad #16 - Matrices  
**Fecha:** 11/11/2025  

---

## Ejercicio 1 - Multiplicación de matrices

### Matrices:


\[
A = \begin{pmatrix} 1 & 2 \\ 3 & 4 \end{pmatrix}, \quad
B = \begin{pmatrix} 2 & 0 \\ 1 & 3 \end{pmatrix}, \quad
C = \begin{pmatrix} 1 & 1 \\ 0 & 2 \end{pmatrix}
\]



### Paso 1: Calcular \( AB \)


\[
AB = \begin{pmatrix}
1 \cdot 2 + 2 \cdot 1 & 1 \cdot 0 + 2 \cdot 3 \\
3 \cdot 2 + 4 \cdot 1 & 3 \cdot 0 + 4 \cdot 3
\end{pmatrix}
= \begin{pmatrix}
4 & 6 \\
10 & 12
\end{pmatrix}
\]



### Paso 2: Calcular \( (AB)C \)


\[
(AB)C = \begin{pmatrix}
4 \cdot 1 + 6 \cdot 0 & 4 \cdot 1 + 6 \cdot 2 \\
10 \cdot 1 + 12 \cdot 0 & 10 \cdot 1 + 12 \cdot 2
\end{pmatrix}
= \begin{pmatrix}
4 & 16 \\
10 & 34
\end{pmatrix}
\]



---

## Ejercicio 2 - Determinantes y propiedades

### Matrices:


\[
A = \begin{pmatrix} 2 & 1 \\ 1 & 3 \end{pmatrix}, \quad
B = \begin{pmatrix} 1 & 2 \\ 3 & 1 \end{pmatrix}
\]



### Determinantes:
- \( \det(A) = 2 \cdot 3 - 1 \cdot 1 = 6 - 1 = 5 \)
- \( \det(B) = 1 \cdot 1 - 2 \cdot 3 = 1 - 6 = -5 \)

### Producto \( AB \):


\[
AB = \begin{pmatrix}
2 \cdot 1 + 1 \cdot 3 & 2 \cdot 2 + 1 \cdot 1 \\
1 \cdot 1 + 3 \cdot 3 & 1 \cdot 2 + 3 \cdot 1
\end{pmatrix}
= \begin{pmatrix}
5 & 5 \\
10 & 5
\end{pmatrix}
\]



### Determinante del producto:
- \( \det(AB) = 5 \cdot 5 - 5 \cdot 10 = 25 - 50 = -25 \)
- Verificación: \( \det(A) \cdot \det(B) = 5 \cdot (-5) = -25 \)

### Transpuesta de A:


\[
A^T = \begin{pmatrix} 2 & 1 \\ 1 & 3 \end{pmatrix}
\]


- \( \det(A^T) = 2 \cdot 3 - 1 \cdot 1 = 6 - 1 = 5 \)
- Se cumple: \( \det(A^T) = \det(A) \)

---

## Ejercicio 3 - Determinante como área geométrica

### Vectores:


\[
\vec{u} = (3, 2), \quad \vec{v} = (1, 4)
\]



### Matriz formada:


\[
A = \begin{pmatrix} 3 & 2 \\ 1 & 4 \end{pmatrix}
\]



### Determinante:
- \( \det(A) = 3 \cdot 4 - 2 \cdot 1 = 12 - 2 = 10 \)

### Interpretación geométrica:
- A) Área del paralelogramo: **10 unidades²**
- B) El área **no cambia** si se rota o refleja
- C) El **signo** del determinante indica la **orientación** (positiva: sentido antihorario)

---




