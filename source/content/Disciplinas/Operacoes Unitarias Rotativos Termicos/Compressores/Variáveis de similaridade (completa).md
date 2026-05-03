
---

# Aplicação conjunta do Teorema de Buckingham aos compressores

## 1. Escolha das variáveis do problema

Para um compressor rotodinâmico, admitindo que seu desempenho seja descrito por:

- vazão volumétrica $Q$,
    
- altura manométrica $H$,
    
- potência $P$,
    
- rotação $N$,
    
- diâmetro característico $D$,
    
- densidade do gás $\rho$,
    
- viscosidade dinâmica $\mu$,
    
- aceleração da gravidade $g$,
    

podemos escrever genericamente:

$$  
f(Q,H,P,N,D,\rho,\mu,g)=0  
$$

Essas são as variáveis que governam o comportamento global da máquina.

---

## 2. Dimensões das variáveis

Escrevendo cada variável em termos de $M$, $L$ e $T$:

$$  
Q \sim L^3T^{-1}  
$$

$$  
H \sim L  
$$

$$  
P \sim ML^2T^{-3}  
$$

$$  
N \sim T^{-1}  
$$

$$  
D \sim L  
$$

$$  
\rho \sim ML^{-3}  
$$

$$  
\mu \sim ML^{-1}T^{-1}  
$$

$$  
g \sim LT^{-2}  
$$

---

## 3. Número de grupos adimensionais

Temos:

- número de variáveis:
    

$$  
n=8  
$$

- número de dimensões fundamentais:
    

$$  
r=3  
$$

Logo, o número de grupos adimensionais será:

$$  
n-r=8-3=5  
$$

Portanto, o problema pode ser reescrito em termos de **cinco grupos adimensionais**:

$$  
\Pi_1,\Pi_2,\Pi_3,\Pi_4,\Pi_5  
$$

---

# 4. Escolha das variáveis repetidas

Escolhemos como variáveis repetidas:

$$  
\rho,\ N,\ D  
$$

Essa escolha é adequada porque:

- $\rho$ contém $M$ e $L$,
    
- $N$ contém $T$,
    
- $D$ contém $L$,
    

e juntas cobrem as três dimensões fundamentais $M$, $L$, $T$.

---

# 5. Construção dos grupos $\Pi$

Vamos formar um grupo para cada variável não repetida:

- $Q$
    
- $H$
    
- $P$
    
- $\mu$
    
- $g$
    

---

## 5.1 Grupo para a vazão $Q$

Assumimos:

$$  
\Pi_1 = Q,\rho^a N^b D^c  
$$

Substituindo as dimensões:

$$  
[L^3T^{-1}],[ML^{-3}]^a,[T^{-1}]^b,[L]^c  
$$

Agrupando:

$$  
M^aL^{3-3a+c}T^{-1-b}  
$$

Para ser adimensional:

$$  
a=0  
$$

$$  
3-3a+c=0 \Rightarrow 3+c=0 \Rightarrow c=-3  
$$

$$  
-1-b=0 \Rightarrow b=-1  
$$

Logo:

$$  
\Pi_1=\frac{Q}{ND^3}  
$$

---

## 5.2 Grupo para o head $H$

Assumimos:

$$  
\Pi_2 = H,\rho^a N^b D^c  
$$

Dimensionalmente:

$$  
[L],[ML^{-3}]^a,[T^{-1}]^b,[L]^c  
$$

Agrupando:

$$  
M^aL^{1-3a+c}T^{-b}  
$$

Impondo adimensionalidade:

$$  
a=0  
$$

$$  
1-3a+c=0 \Rightarrow 1+c=0 \Rightarrow c=-1  
$$

$$  
-b=0 \Rightarrow b=0  
$$

Então:

$$  
\Pi_2=\frac{H}{D}  
$$

---

## 5.3 Grupo para a potência $P$

Assumimos:

$$  
\Pi_3 = P,\rho^a N^b D^c  
$$

Dimensionalmente:

$$  
[ML^2T^{-3}],[ML^{-3}]^a,[T^{-1}]^b,[L]^c  
$$

Agrupando:

$$  
M^{1+a}L^{2-3a+c}T^{-3-b}  
$$

Para ser adimensional:

$$  
1+a=0 \Rightarrow a=-1  
$$

$$  
-3-b=0 \Rightarrow b=-3  
$$

$$  
2-3(-1)+c=0 \Rightarrow 2+3+c=0 \Rightarrow c=-5  
$$

Logo:

$$  
\Pi_3=\frac{P}{\rho N^3D^5}  
$$

---

## 5.4 Grupo para a viscosidade $\mu$

Assumimos:

$$  
\Pi_4 = \mu,\rho^a N^b D^c  
$$

Dimensionalmente:

$$  
[ML^{-1}T^{-1}],[ML^{-3}]^a,[T^{-1}]^b,[L]^c  
$$

Agrupando:

$$  
M^{1+a}L^{-1-3a+c}T^{-1-b}  
$$

Impondo adimensionalidade:

$$  
1+a=0 \Rightarrow a=-1  
$$

$$  
-1-b=0 \Rightarrow b=-1  
$$

$$  
-1-3(-1)+c=0 \Rightarrow -1+3+c=0 \Rightarrow c=-2  
$$

Logo:

$$  
\Pi_4=\frac{\mu}{\rho N D^2}  
$$

Esse grupo é o inverso de um Reynolds rotacional.

---

## 5.5 Grupo para a gravidade $g$

Assumimos:

$$  
\Pi_5 = g,\rho^a N^b D^c  
$$

Dimensionalmente:

$$  
[LT^{-2}],[ML^{-3}]^a,[T^{-1}]^b,[L]^c  
$$

Agrupando:

$$  
M^aL^{1-3a+c}T^{-2-b}  
$$

Impondo adimensionalidade:

$$  
a=0  
$$

$$  
-2-b=0 \Rightarrow b=-2  
$$

$$  
1+c=0 \Rightarrow c=-1  
$$

Logo:

$$  
\Pi_5=\frac{g}{N^2D}  
$$

---

# 6. Resultado do problema completo

Portanto, a formulação adimensional conjunta do compressor pode ser escrita como:

$$  
\Phi\left(  
\frac{Q}{ND^3},  
\frac{H}{D},  
\frac{P}{\rho N^3D^5},  
\frac{\mu}{\rho ND^2},  
\frac{g}{N^2D}  
\right)=0  
$$

ou equivalentemente,

$$  
\frac{Q}{ND^3}=

F\left(  
\frac{H}{D},  
\frac{P}{\rho N^3D^5},  
\frac{\mu}{\rho ND^2},  
\frac{g}{N^2D}  
\right)  
$$

Essa é a forma obtida quando **todas as variáveis são tratadas juntas** no teorema.

---

# 7. Como chegar aos coeficientes clássicos usados em similaridade

Os coeficientes que aparecem em turbomáquinas geralmente são escritos como:

$$  
C_Q=\frac{Q}{ND^3}  
$$

$$  
C_H=\frac{gH}{N^2D^2}  
$$

$$  
C_P=\frac{P}{\rho N^3D^5}  
$$

Observe que, no resultado bruto do Buckingham, apareceram separadamente:

$$  
\Pi_2=\frac{H}{D}  
\qquad \text{e} \qquad  
\Pi_5=\frac{g}{N^2D}  
$$

Mas como o produto de grupos adimensionais também é adimensional, podemos combinar:

$$  
\Pi_2\Pi_5=  
\frac{H}{D}\cdot\frac{g}{N^2D}

\frac{gH}{N^2D^2}  
$$

Assim, o coeficiente de head clássico surge naturalmente como **combinação de dois grupos $\Pi$ independentes**.

---

# 8. Forma final mais usada em compressores

Reorganizando os grupos em uma forma mais conveniente para similaridade:

$$  
\Phi\left(  
\frac{Q}{ND^3},  
\frac{gH}{N^2D^2},  
\frac{P}{\rho N^3D^5},  
\frac{\mu}{\rho ND^2}  
\right)=0  
$$

ou, destacando os nomes usuais:

$$  
\Phi(C_Q,C_H,C_P,\Pi_\mu)=0  
$$

com

$$  
C_Q=\frac{Q}{ND^3}  
$$

$$  
C_H=\frac{gH}{N^2D^2}  
$$

$$  
C_P=\frac{P}{\rho N^3D^5}  
$$

$$  
\Pi_\mu=\frac{\mu}{\rho ND^2}  
$$

---

# 9. Interpretação física

Ao fazer o problema completo, aparecem quatro tipos de efeito:

### efeito de vazão

$$  
\frac{Q}{ND^3}  
$$

### efeito de energia específica

$$  
\frac{gH}{N^2D^2}  
$$

### efeito de potência

$$  
\frac{P}{\rho N^3D^5}  
$$

### efeito viscoso

$$  
\frac{\mu}{\rho ND^2}  
$$

Quando os efeitos viscosos são pequenos ou aproximadamente constantes entre duas condições, a similaridade fica dominada pelos três coeficientes clássicos:

$$  
C_Q,\quad C_H,\quad C_P  
$$

---

# 10. Conclusão didática

Então, fazendo o Buckingham **de forma conjunta**, os coeficientes clássicos de similaridade:

$$  
\frac{Q}{ND^3},\qquad  
\frac{gH}{N^2D^2},\qquad  
\frac{P}{\rho N^3D^5}  
$$

não são escolhidos arbitrariamente. Eles emergem da análise dimensional completa, sendo que o termo do head aparece como uma combinação natural de dois grupos básicos obtidos no processo.

---
