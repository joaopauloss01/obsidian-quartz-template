#Lupo

# 📘 LEI DE FICK — COEFICIENTES DE DIFUSÃO EM GASES

---

# 🔹 SLIDE 1

## Parâmetros de Lennard-Jones

### 🎯 Objetivo

Apresentar os parâmetros moleculares necessários para cálculo do coeficiente de difusão.

### 🧠 Desenvolvimento

Os modelos baseados na teoria cinética utilizam:

- $\sigma$ → diâmetro de colisão (Å)
    
- $\varepsilon / k$ → energia característica de interação (K)
    

Esses parâmetros são utilizados para calcular a **integral de colisão**.

---

# 🔹 SLIDE 2

## Exemplo 4 — CO₂ no Ar

### 🎯 Problema

Determinar $ D_{AB} $ para:

- CO₂ no ar
    
- $T = 293 , K$
    
- $P = 1 , atm$

---

### 🧮 Procedimento

1. Calcular $\sigma_{AB}$
    
2. Calcular $\varepsilon_{AB}$
    
3. Calcular $T^*$
    
4. Calcular $\Omega_D$
    
5. Aplicar equação geral de difusão
    

---

# 🔹 SLIDE 3

## Integral de Colisão — Correlação de Neufeld (1972)

A integral de colisão é dada por:

$$  
\Omega_D =  
\frac{A}{(T^_)^B}  
+  
\frac{C}{\exp(DT^_)}  
+  
\frac{E}{\exp(FT^_)}  
+  
\frac{G}{\exp(HT^_)}  
$$

Temperatura reduzida:

$$  
T^* = \frac{kT}{\varepsilon_{AB}}  
$$

Constantes:

- $ A = 1.06036 $
    
- $ B = 0.15610 $
    
- $ C = 0.19300 $
    
- $ D = 0.47635 $
    
- $ E = 1.03587 $
    
- $ F = 1.52996 $
    
- $ G = 1.76474 $
    
- $ H = 3.89411 $
    

---

# 🔹 SLIDE 4

## Correlação de Fuller, Schettler e Giddings

Quando não se tem parâmetros de Lennard-Jones:

$$  
D_{AB} =  
\frac{  
10^{-3} T^{1.75}  
\left(  
\frac{1}{M_A}  
+  
\frac{1}{M_B}  
\right)^{1/2}  
}  
{  
P  
\left[  
(\sum \vartheta_A)^{1/3}  
+  
(\sum \vartheta_B)^{1/3}  
\right]^2  
}  
$$

Onde:

- $ \vartheta $ = volume de Fuller (cm³/mol)
    
- $ M_A, M_B $ = massas molares
    
- $ P $ em atm
    
- $ T $ em K
    

---

# 🔹 SLIDE 5

## Moléculas Apolares

Combinação de parâmetros:

$$  
\sigma_{AB} =  
\frac{\sigma_A + \sigma_B}{2}  
$$

$$  
\varepsilon_{AB} =  
\sqrt{\varepsilon_A \varepsilon_B}  
$$

---

### Dependência com T e P

# $$  
D_{AB,T_2,P_2}

D_{AB,T_1,P_1}  
\left(  
\frac{P_1}{P_2}  
\right)  
\left(  
\frac{T_2}{T_1}  
\right)^{3/2}  
\frac{\Omega_{D,T_1}}{\Omega_{D,T_2}}  
$$

---

# 🔹 SLIDE 6

## Exercícios Aplicados

Calcular $ D_{AB} $ para:

- CO₂/ar
    
- Etanol/ar
    
- SO₂/ar
    

Comparar método de Lennard-Jones e Fuller.

---

# 🔹 SLIDE 7

## Compostos Polares — Hirschfelder e Brokaw

Correção da integral de colisão:

$$  
\Omega_D =  
\Omega_{D0}  
+  
\frac{0.169 \delta_{AB}^2}{T^*}  
$$

Onde:

$$  
\delta_{AB} =  
(\delta_A \delta_B)^{1/2}  
$$

e

$$  
\delta =  
\frac{1.94 \times 10^3 \mu_p^2}{V_b T_b}  
$$

Temperatura reduzida:

$$  
T^* =  
\frac{kT}{\varepsilon_{AB}}  
$$

---

# 🔹 SLIDE 8

## Diâmetro de Colisão

$$  
\sigma_{AB} =  
(\sigma_A \sigma_B)^{1/2}  
$$

Correção estrutural:

$$  
\sigma =  
\left(  
\frac{1.585 V_b}{1 + 1.3 \delta^2}  
\right)^{1/3}  
$$

---

## Mistura Multicomponente

Coeficiente efetivo:

# $$  
D_{1,M}

\frac{1 - y_1}  
{  
\sum_{i=2}^{n}  
\frac{y_i}{D_{1,i}}  
}  
$$

Onde:

- $ D_{1,M} $ = difusividade efetiva
    
- $ D_{1,i} $ = difusividade binária
    
- $ y_i $ = fração molar
    

---

# 🔹 SLIDE 9

## Exemplos Multicomponentes

Aplicar:

# $$  
D_{1,M}

\frac{1 - y_1}  
{  
\sum_{i=2}^{n}  
\frac{y_i}{D_{1,i}}  
}  
$$

para sistemas com múltiplos gases.

---

Agora está 100% compatível com renderização em Obsidian/NotebookLM.

Se quiser, posso:

- Reestruturar com ainda mais detalhamento didático
    
- Criar versão com resolução completa dos exemplos
    
- Montar versão com narrativa de aula
    
- Integrar com o capítulo anterior (ligando teoria cinética → Fick → coeficientes)
    

Qual direção você prefere?