---

# 📘 A Força Motriz da Transferência de Massa

## O Potencial Químico

---
## 🎯 SLIDE 1

# Transferência de Massa e Segunda Lei

Sistema isolado com dois subsistemas ( A ) e ( B ).

Entropia total:

$$  
dS = dS_A + dS_B  
$$

A transferência de massa ocorre na direção que **maximiza a entropia total**.

---

## 🎯 SLIDE 2

# Equação Fundamental da Termodinâmica

Equação fundamental para sistema multicomponente:

$$  
dU = T,dS - P,dV + \sum_i \mu_i,dn_i  
$$

Isolando ( dS ):

$$  
dS = \frac{1}{T}\left(dU + P,dV - \sum_i \mu_i,dn_i \right)  
$$

---

## 🎯 SLIDE 3

# Volume Rígido

Para ( dV = 0 ):

$$  
dS = \frac{1}{T}\left(dU - \sum_i \mu_i,dn_i \right)  
$$

---

## 🎯 SLIDE 4

# Aplicação aos Subsystems A e B

Para o subsistema ( A ):

$$  
dS_A = \frac{1}{T}\left(dU_A - \sum_i \mu_{iA},dn_{iA} \right)  
$$

Para o subsistema ( B ):

$$  
dS_B = \frac{1}{T}\left(dU_B - \sum_i \mu_{iB},dn_{iB} \right)  
$$

---

## 🎯 SLIDE 5

# Entropia Total

Somando:

$$  
dS = \frac{1}{T}  
\left[  
dU_A + dU_B

- \sum_i \mu_{iA},dn_{iA}
    
- \sum_i \mu_{iB},dn_{iB}  
    \right]  
    $$
    

---

## 🎯 SLIDE 6

# Sistema Isolado

Energia total constante:

$$  
dU_A + dU_B = 0  
$$

ou

$$  
dU_A = -dU_B  
$$

Transferência de matéria:

$$  
dn_{iA} = -dn_{iB}  
$$

---

## 🎯 SLIDE 7

# Substituindo

Substituindo na expressão de ( dS ):

$$  
dS =  
\frac{1}{T}  
\sum_i  
dn_{iA}  
\left(  
\mu_{iB} - \mu_{iA}  
\right)  
$$

---

## 🎯 SLIDE 8

# Condição de Equilíbrio

No equilíbrio:

$$  
dS = 0  
$$

Logo:

$$  
\mu_{iA} = \mu_{iB}  
$$

ou

$$  
\Delta \mu_i = 0  
$$

Equilíbrio ocorre quando não há diferença de potencial químico.

---

## 🎯 SLIDE 9

# Interpretação Física

Se:

$$  
\mu_{iB} > \mu_{iA}  
$$

Então:

$$  
dn_{iA} > 0  
$$

A matéria flui da região de maior potencial químico para a de menor potencial químico.

O potencial químico é a verdadeira força motriz da transferência de massa.

---

## 🎯 SLIDE 10

# Potencial Químico em Solução Ideal

$$  
\mu_i = \mu_i^0 + RT \ln x_i  
$$

Diferenciando:

$$  
d\mu_i = RT\frac{dx_i}{x_i}  
$$

Para soluções diluídas:

$$  
d\mu_i = RT\frac{dC_i}{C_i}  
$$

---

## 🎯 SLIDE 11

# Gradiente de Potencial Químico

Se:

$$  
\nabla \mu_i \neq 0  
$$

Então existe fluxo:

$$  
J_i \propto -\nabla \mu_i  
$$

---

## 🎯 SLIDE 12

# Forma Microscópica

$$  
J_{A,z} = -\frac{1}{3}\cdot\Omega\cdot\lambda\cdot\frac{dC_A}{dz}  
$$

Definindo o coeficiente de difusão:

$$  
D_{A,A} = \frac{1}{3}\cdot\Omega\cdot\lambda  
$$

---

## 🎯 SLIDE 13

# Primeira Lei de Fick

$$  
J_{A,z} = -D_{AA}\cdot\frac{dC_A}{dz}  
$$

A Lei de Fick é a manifestação macroscópica do gradiente de potencial químico.

---
