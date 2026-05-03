## Fator de correção da DTML

Para o trocador casco e tubo com 1 passe no casco, considera-se:

$$
N=1
$$

Logo:

$$
X=S
$$

As temperaturas do problema são:

$$
T_1=390^\circ F
$$

$$
T_2=200^\circ F
$$

$$
t_1=100^\circ F
$$

$$
t_2=170^\circ F
$$

Calculando os parâmetros adimensionais:

$$
R=\frac{T_1-T_2}{t_2-t_1}
$$

$$
R=\frac{390-200}{170-100}=2{,}714
$$

$$
S=\frac{t_2-t_1}{T_1-t_1}
$$

$$
S=\frac{170-100}{390-100}=0{,}241
$$

Como $N=1$:

$$
X=S=0{,}241
$$

O fator de correção é:

$$
F_T=
\frac{
\sqrt{R^2+1}\cdot
\ln\left(\frac{1-X}{1-R\cdot X}\right)
}{
\left(R-1\right)\cdot
\ln\left(
\frac{
2-X\cdot\left(R+1-\sqrt{R^2+1}\right)
}{
2-X\cdot\left(R+1+\sqrt{R^2+1}\right)
}
\right)
}
$$

$$
F_T\approx 0{,}909
$$

Como:

$$
F_T\geq 0{,}85
$$

o arranjo térmico é aceitável.