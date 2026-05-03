# 1️⃣ Desenvolvimento da equação de difusividade gasosa

## Slide 1 — Difusão molecular em gases

A difusão molecular em gases pode ser descrita pela **teoria cinética dos gases**.

A difusividade binária é proporcional:

- à velocidade média molecular
    
- ao caminho livre médio
    

$$  
D_{AB} \sim \lambda , \bar{v}  
$$

onde

- $\lambda$ = caminho livre médio
    
- $\bar{v}$ = velocidade molecular média
    

---

# Slide 2 — Caminho livre médio

O caminho livre médio depende da **seção de colisão molecular**.

$$  
\lambda = \frac{1}{\sqrt{2},n,\sigma_{AB}^2}  
$$

onde

- $n$ = densidade numérica molecular
    
- $\sigma_{AB}$ = diâmetro efetivo de colisão
    

---

# Slide 3 — Velocidade molecular média

A velocidade molecular média obtida da teoria cinética é

$$  
\bar{v} = \sqrt{\frac{8k_B T}{\pi m_{AB}}}  
$$

onde

- $k_B$ = constante de Boltzmann
    
- $T$ = temperatura
    
- $m_{AB}$ = massa reduzida
    

---

# Slide 4 — Massa reduzida

A massa reduzida é

$$  
m_{AB} = \frac{m_A m_B}{m_A + m_B}  
$$

Convertendo para massa molar:

$$  
m = \frac{M}{N_A}  
$$

onde

- $M$ = massa molar
    
- $N_A$ = número de Avogadro
    

---

# Slide 5 — Substituindo na equação da difusividade

Substituindo $\lambda$ e $\bar{v}$ em

$$  
D_{AB} \sim \lambda \bar{v}  
$$

obtemos

$$  
D_{AB} =  
\frac{1}{\sqrt{2},n,\sigma_{AB}^2}  
\sqrt{\frac{8k_B T}{\pi m_{AB}}}  
$$

---

# Slide 6 — Relacionando densidade molecular e pressão

A [[Densidade molecular]] é

$$  
n = \frac{P}{k_B T}  
$$

Substituindo:

$$  
D_{AB} =  
\frac{k_B T}{\sqrt{2} P \sigma_{AB}^2}  
\sqrt{\frac{8k_B T}{\pi m_{AB}}}  
$$

---

# Slide 7 — Agrupando constantes

Reorganizando:

$$  
D_{AB} =  
\frac{2}{3\sqrt{2},N_A P \sigma_{AB}^2}  
\left(\frac{RT}{\pi}\right)^{3/2}  
\left(\frac{1}{M_A}+\frac{1}{M_B}\right)^{1/2}  
$$

Esta é a forma obtida pela **teoria cinética simplificada**.

---

# Slide 8 — Correção para interação molecular

A teoria cinética simples assume **moléculas rígidas**.

Na prática, as moléculas interagem via **potencial de Lennard-Jones**.

Para corrigir o efeito das interações, introduz-se a **integral de colisão**:

$$  
\Omega_D  
$$

---

# Slide 9 — Forma final com integral de colisão

A equação se torna

$$  
D_{AB} =  
\frac{3}{16}  
\frac{\sqrt{2\pi (k_B T)^3}}{P \sigma_{AB}^2}  
\sqrt{\frac{1}{m_A}+\frac{1}{m_B}}  
\frac{1}{\Omega_D}  
$$

---

# Slide 10 — Forma prática de Chapman–Enskog

Expressando em unidades práticas:

- $T$ em K
    
- $P$ em atm
    
- $\sigma$ em Å
    

obtemos

$$  
D_{AB} =  
\frac{0.001858,T^{3/2}}  
{P,\sigma_{AB}^2,\Omega_D}  
\left(  
\frac{1}{M_A}+\frac{1}{M_B}  
\right)^{1/2}  
$$

onde

- $D_{AB}$ em $cm^2/s$
    

Esta é a **equação de Chapman–Enskog**.

---

# Slide 11 — Temperatura reduzida

A integral de colisão depende da temperatura reduzida:

$$  
T^* = \frac{k_B T}{\varepsilon_{AB}}  
$$

ou

$$  
T^* = \frac{T}{(\varepsilon/k)_{AB}}  
$$

---

# Slide 12 — Correlação da integral de colisão

Uma correlação comum é

$$  
\Omega_D =  
\frac{1.06036}{{T^{*}}^{0.15610}}  
+  
\frac{0.19300}{e^{0.47635T^{*}}}  
+  
\frac{1.03587}{e^{1.52996T^{*}}}  
+  
\frac{1.76474}{e^{3.89411T^{*}}}  
$$

---

# Slide 13 — Parâmetros de Lennard-Jones

Para mistura binária:

$$  
\sigma_{AB} = \frac{\sigma_A + \sigma_B}{2}  
$$

$$  
(\varepsilon/k)_{AB} =  
\sqrt{(\varepsilon/k)_A (\varepsilon/k)_B}  
$$

---

# Slide 14 — Procedimento de cálculo

Passos para calcular $D_{AB}$:

1. obter $\sigma_A$ e $\sigma_B$
    
2. obter $(\varepsilon/k)_A$ e $(\varepsilon/k)_B$
    
3. calcular parâmetros da mistura
    
4. calcular $T^*$
    
5. calcular $\Omega_D$
    
6. aplicar equação de Chapman–Enskog
    

---

# 2️⃣ Prompt para gerar slides no NotebookLM

Use exatamente este prompt.

---

**PROMPT**

Crie uma sequência de slides didáticos sobre o desenvolvimento da equação de difusividade gasosa a partir da teoria cinética até a equação de Chapman-Enskog.

Estrutura desejada:

- slides progressivos mostrando o desenvolvimento matemático
    
- cada slide deve conter título, explicação curta e equações em LaTeX
    
- equações devem aparecer em bloco $$ $$ para renderização científica
    
- incluir interpretação física entre as etapas
    
- incluir explicação da integral de colisões
    
- incluir definição da temperatura reduzida
    
- incluir expressão da integral de colisões
    
- incluir parâmetros de Lennard-Jones
    
- finalizar com o procedimento de cálculo da difusividade
    

Sequência de conteúdo:

1 Introdução à difusão molecular em gases  
2 Relação entre difusividade, caminho livre médio e velocidade molecular  
3 Caminho livre médio  
4 Velocidade molecular média  
5 Massa reduzida  
6 Substituição na expressão da difusividade  
7 Uso da equação do gás ideal  
8 Forma obtida pela teoria cinética  
9 Limitações da teoria cinética simples  
10 Introdução da integral de colisão  
11 Equação de Chapman-Enskog  
12 Temperatura reduzida  
13 Correlação da integral de colisão  
14 Parâmetros de Lennard-Jones para misturas  
15 Procedimento completo de cálculo

Os slides devem ser pensados para uma aula de **Transferência de Massa em nível de engenharia química**, com explicações concisas e foco físico nas etapas da derivação.

---
