
---

# Teorema das variáveis repetidas de Buckingham

Se um fenômeno depende de $n$ variáveis dimensionais e essas variáveis envolvem $r$ dimensões fundamentais independentes, então o problema pode ser reescrito em termos de

$$  
n-r  
$$

grupos adimensionais independentes.

No caso de compressores rotodinâmicos, as dimensões fundamentais mais comuns são:

$$  
M,\ L,\ T  
$$

---

# 1. Coeficiente de vazão

Queremos obter um grupo adimensional para a vazão volumétrica $Q$.

## Variáveis relevantes

Vamos assumir que a vazão depende de:

$$  
Q,\ N,\ D  
$$

onde:

- $Q$ = vazão volumétrica $[L^3T^{-1}]$
    
- $N$ = rotação $[T^{-1}]$
    
- $D$ = diâmetro característico do rotor $[L]$
    

Temos:

- número de variáveis: $n=3$
    
- dimensões fundamentais: $r=2$ ($L$ e $T$)
    

Logo, existe

$$  
3-2=1  
$$

grupo adimensional.

---

## Montagem do grupo $\Pi_1$

Assumimos:

$$  
\Pi_1 = Q,N^a D^b  
$$

Substituindo as dimensões:

# $$  
[L^3T^{-1}],[T^{-1}]^a,[L]^b

L^{3+b}T^{-1-a}  
$$

Para ser adimensional:

$$  
3+b=0  
$$

$$  
-1-a=0  
$$

Logo:

$$  
b=-3,\qquad a=-1  
$$

Portanto:

$$  
\Pi_1=\frac{Q}{ND^3}  
$$

ou seja,

$$  
\boxed{C_Q=\frac{Q}{N D^3}}  
$$

Esse é o **coeficiente de vazão**.

---

# 2. Coeficiente de head

Agora queremos um grupo adimensional para a altura manométrica $H$.

## Variáveis relevantes

Vamos assumir que o head depende de:

$$  
H,\ g,\ N,\ D  
$$

onde:

- $H$ = altura manométrica $[L]$
    
- $g$ = aceleração da gravidade $[LT^{-2}]$
    
- $N$ = rotação $[T^{-1}]$
    
- $D$ = diâmetro $[L]$
    

Temos:

- $n=4$
    
- $r=2$ ($L$ e $T$)
    

Logo, haverá

$$  
4-2=2  
$$

grupos adimensionais possíveis. Um deles é justamente o grupo do head.

---

## Montagem do grupo $\Pi_2$

Assumimos:

$$  
\Pi_2 = g,H,N^a D^b  
$$

Dimensionalmente:

# $$  
[LT^{-2}],[L],[T^{-1}]^a,[L]^b

L^{2+b}T^{-2-a}  
$$

Impondo adimensionalidade:

$$  
2+b=0  
$$

$$  
-2-a=0  
$$

Então:

$$  
b=-2,\qquad a=-2  
$$

Logo:

$$  
\Pi_2=\frac{gH}{N^2D^2}  
$$

ou seja,

$$  
\boxed{C_H=\frac{gH}{N^2D^2}}  
$$

Esse é o **coeficiente de head**.

---

# 3. Coeficiente de potência

Agora buscamos o grupo adimensional para a potência.

## Variáveis relevantes

A potência em máquinas de fluxo depende de:

$$  
P,\ \rho,\ N,\ D  
$$

onde:

- $P$ = potência $[ML^2T^{-3}]$
    
- $\rho$ = densidade $[ML^{-3}]$
    
- $N$ = rotação $[T^{-1}]$
    
- $D$ = diâmetro $[L]$
    

Temos:

- $n=4$
    
- $r=3$ ($M,\ L,\ T$)
    

Logo existe

$$  
4-3=1  
$$

grupo adimensional.

---

## Montagem do grupo $\Pi_3$

Assumimos:

$$  
\Pi_3=P,\rho^a N^b D^c  
$$

Substituindo as dimensões:

$$  
[ML^2T^{-3}]  
[ML^{-3}]^a  
[T^{-1}]^b  
[L]^c  
$$

Agrupando os expoentes:

- massa:
    

$$  
M^{1+a}  
$$

- comprimento:
    

$$  
L^{2-3a+c}  
$$

- tempo:
    

$$  
T^{-3-b}  
$$

Para ser adimensional:

$$  
1+a=0  
$$

$$  
2-3a+c=0  
$$

$$  
-3-b=0  
$$

Daí:

$$  
a=-1  
$$

$$  
b=-3  
$$

e

$$  
2-3(-1)+c=0  
\Rightarrow 2+3+c=0  
\Rightarrow c=-5  
$$

Portanto:

$$  
\Pi_3=\frac{P}{\rho N^3 D^5}  
$$

ou seja,

$$  
\boxed{C_{pot}=\frac{P}{\rho N^3 D^5}}  
$$

Esse é o **coeficiente de potência**.

---

# 4. Resultado final dos grupos adimensionais

Aplicando Buckingham, obtemos os três grupos clássicos usados em similaridade de compressores:

$$  
\boxed{C_Q=\frac{Q}{ND^3}}  
$$

$$  
\boxed{C_H=\frac{gH}{N^2D^2}}  
$$

$$  
\boxed{C_{pot}=\frac{P}{\rho N^3D^5}}  
$$

---

# 5. Interpretação física

Esses grupos permitem comparar máquinas geometricamente semelhantes e condições operacionais diferentes.

## Coeficiente de vazão

$$  
C_Q=\frac{Q}{ND^3}  
$$

mede a vazão “normalizada” pela escala cinemática da máquina.

## Coeficiente de head

$$  
C_H=\frac{gH}{N^2D^2}  
$$

compara a energia específica fornecida ao fluido com a escala de velocidade periférica do rotor.

## Coeficiente de potência

$$  
C_{pot}=\frac{P}{\rho N^3D^5}  
$$

relaciona a potência consumida com a escala inercial da máquina e do escoamento.

---

# 6. Condições de similaridade

Para máquinas semelhantes operando em regime dinamicamente similar, esses coeficientes permanecem constantes:

$$  
C_Q=\text{constante}  
$$

$$  
C_H=\text{constante}  
$$

$$  
C_{pot}=\text{constante}  
$$

Daí surgem as leis práticas:

$$  
Q \propto N D^3  
$$

$$  
H \propto N^2 D^2  
$$

$$  
P \propto \rho N^3 D^5  
$$

E, para a **mesma máquina** $\left(D=\text{constante}\right)$:

$$  
Q \propto N  
$$

$$  
H \propto N^2  
$$

$$  
P \propto \rho N^3  
$$

---

# 7. Forma didática para colocar no slide

Você pode organizar assim:

## Aplicando Buckingham ao compressor

### Variáveis escolhidas

- Vazão: $Q,\ N,\ D$
    
- Head: $H,\ g,\ N,\ D$
    
- Potência: $P,\ \rho,\ N,\ D$
    

### Grupos adimensionais obtidos

$$  
\frac{Q}{ND^3},\qquad  
\frac{gH}{N^2D^2},\qquad  
\frac{P}{\rho N^3D^5}  
$$

### Interpretação

- vazão normalizada
    
- head normalizado
    
- potência normalizada
    

---

# 8. Observação importante para aula

Se quiser ser ainda mais rigoroso, em compressores de gás também podem aparecer outros grupos, por exemplo:

$$  
\frac{ND}{\sqrt{kRT}}  
$$

que está ligado ao **número de Mach**,

e também grupos envolvendo viscosidade, ligados ao **número de Reynolds**.

Mas, para as **leis clássicas de similaridade em turbomáquinas**, os três grupos que você mostrou são exatamente os principais para:

- vazão,
    
- head,
    
- potência.
    

---

Se quiser, eu posso transformar isso agora em **2 slides prontos em markdown**, com visual mais didático para o NotebookLM.