## Questão 1 — Passo 1: vazões globais e sistema linear

Dados da questão: $Q_{01}=5,\text{m}^3/\text{min}$, $Q_{02}=1,\text{m}^3/\text{min}$, $Q_{31}=2,\text{m}^3/\text{min}$, $C_{01}=10,\text{mol}/\text{m}^3$ e $C_{02}=1,\text{mol}/\text{m}^3$ .

As vazões internas são:

$$\
Q_{12}=Q_{01}+Q_{31}=5+2=7\,\text{m}^3/\text{min}\
$$

$$\
Q_{23}=Q_{02}+Q_{12}=1+7=8\,\text{m}^3/\text{min}\
$$

$$\
Q_{33}=Q_{23}-Q_{31}=8-2=6\,\text{m}^3/\text{min}\
$$

### Balanços de NaOH em regime permanente

Tanque $1$:

$$\
Q_{01}C_{01}+Q_{31}C_3-Q_{12}C_1=0\
$$

$$\
5(10)+2C_3-7C_1=0\
$$

$$\
7C_1-2C_3=50\
$$

Tanque $2$:

$$\
Q_{02}C_{02}+Q_{12}C_1-Q_{23}C_2=0\
$$

$$\
1(1)+7C_1-8C_2=0\
$$

$$\
-7C_1+8C_2=1\
$$

Tanque $3$:

$$\
Q_{23}C_2-Q_{31}C_3-Q_{33}C_3=0\
$$

$$\
8C_2-2C_3-6C_3=0\
$$

$$\
8C_2-8C_3=0\
$$

### Forma matricial

$$\
\begin{bmatrix}\
7 & 0 & -2 \\\
-7 & 8 & 0 \\\
0 & 8 & -8\
\end{bmatrix}\
\begin{bmatrix}\
C_1 \\\
C_2 \\\
C_3\
\end{bmatrix}
=============

\begin{bmatrix}\
50 \\\
1 \\\
0\
\end{bmatrix}\
$$

### Solução

Da terceira equação:

$$\
C_2=C_3\
$$

Da segunda:

$$\
-7C_1+8C_2=1\
$$

Da primeira:

$$\
7C_1-2C_3=50\
$$

Como $C_3=C_2$:

$$\
7C_1-2C_2=50\
$$

Resolvendo o sistema:

$$\
C_1=\frac{204}{21}=9{,}7143\,\text{mol}/\text{m}^3\
$$

$$\
C_2=\frac{145}{16}?\
$$

Correção direta pela substituição:

$$\
7C_1-2C_2=50\
$$

$$\
-7C_1+8C_2=1\
$$

Somando:

$$\
6C_2=51\
$$

$$\
C_2=8{,}5\,\text{mol}/\text{m}^3\
$$

Logo:

$$\
C_3=8{,}5\,\text{mol}/\text{m}^3\
$$

E:

$$\
7C_1-2(8{,}5)=50\
$$

$$\
7C_1=67\
$$

$$\
C_1=9{,}5714\,\text{mol}/\text{m}^3\
$$

## Gabarito do passo

$$\
\boxed{C_1=9{,}5714\,\text{mol}/\text{m}^3}\
$$

$$\
\boxed{C_2=8{,}5000\,\text{mol}/\text{m}^3}\
$$

$$\
\boxed{C_3=8{,}5000\,\text{mol}/\text{m}^3}\
$$
