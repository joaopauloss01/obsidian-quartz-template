Perfeito — vou organizar as **3 questões em formato formal de lista de exercícios/projeto**, com linguagem clara, progressão de dificuldade e coerência entre elas. Você pode praticamente copiar e colar em um documento.

---

# 📘 **Projeto Avaliativo – Métodos Numéricos em Engenharia Química**

## **Instruções gerais**

Este trabalho tem como objetivo integrar conceitos de:

- balanços de massa e energia
    
- modelagem matemática
    
- resolução de sistemas lineares e não lineares
    
- implementação computacional
    
- análise de sensibilidade
    

Os alunos devem apresentar:

- modelagem detalhada
    
- desenvolvimento matemático
    
- código implementado (Python, MATLAB ou similar)
    
- análise e discussão dos resultados
    

---

# 🔹 **Questão 1 — Sistema de tanques com reciclo**

Considere um sistema composto por três tanques perfeitamente agitados operando em regime permanente, conforme ilustrado na figura fornecida.

Os tanques possuem volumes constantes e recebem correntes de entrada com vazões conhecidas. Inicialmente, o sistema opera com água pura. Em um determinado instante, as correntes de entrada passam a conter uma solução de NaOH com concentrações conhecidas.

Há uma corrente de reciclo que retorna do tanque 3 para o tanque 1.

---

## **Dados:**

- Vazões:
    
    - $Q_{01} = 5 , \text{m}^3/\text{min}$
        
    - $Q_{02} = 1 , \text{m}^3/\text{min}$
        
    - $Q_{31} = 2 , \text{m}^3/\text{min}$
        
- Relações:
    
    - $Q_{12} = Q_{01} + Q_{31}$
        
    - $Q_{23} = Q_{02} + Q_{12}$
        
    - $Q_{33} = Q_{23} - Q_{31}$
        
- Concentrações de entrada:
    
    - $C_{01} = 10 , \text{mol/m}^3$
        
    - $C_{02} = 1 , \text{mol/m}^3$
        

---

## **Solicita-se:**

### (a) Modelagem

1. Escreva os balanços de massa para cada tanque.
    
2. Expresse o sistema na forma matricial:
    

$$  
A \cdot \mathbf{C} = \mathbf{b}  
$$

onde:

$$  
\mathbf{C} = [C_1, C_2, C_3]^T  
$$

---

### (b) Solução

3. Resolva o sistema linear para obter as concentrações nos três tanques.
    
4. Implemente a solução computacionalmente.
    

---

### (c) Análise de sensibilidade

5. Avalie o efeito da vazão de reciclo $Q_{31}$ no sistema.
    
6. Considere:
    

$$  
0 \leq Q_{31} \leq 10  
$$

7. Construa gráficos de:
    
    - $C_1$, $C_2$, $C_3$ em função de $Q_{31}$
        
8. Discuta o efeito físico do reciclo sobre o sistema.
    

---

# 🔥 **Questão 2 — Combustão adiabática com excesso de ar e injeção de vapor**

Considere a combustão completa do metano com ar seco em um queimador operando adiabaticamente. Os reagentes entram a $25^\circ C$ e a pressão é constante.

Inicialmente, a combustão ocorre com excesso de ar. Em seguida, avalia-se uma alternativa operacional na qual vapor d’água é injetado na alimentação para reduzir a temperatura da chama.

---

## **Solicita-se:**

### (a) Combustão com excesso de ar

1. Escreva a equação estequiométrica da combustão completa do metano com excesso de ar.
    
2. Determine a composição dos produtos.
    
3. Formule o balanço de energia adiabático:
    

$$  
\sum n_i \Delta \hat{H}_{sens,i}(T) + \Delta \hat{H}_{rxn}^\circ = 0  
$$

4. Resolva numericamente para obter a temperatura adiabática de chama $T_{ad}$.
    

---

### (b) Análise de sensibilidade — excesso de ar

5. Varie o excesso de ar em uma faixa:
    

$$  
0% \leq \text{excesso de ar} \leq 100%  
$$

6. Construa o gráfico:
    

$$  
T_{ad} \text{ vs excesso de ar}  
$$

7. Discuta os resultados.
    

---

### (c) Combustão com injeção de vapor

8. Modifique o modelo para incluir injeção de vapor na alimentação.
    
9. Reescreva a composição dos produtos.
    
10. Reformule o balanço de energia.
    

---

### (d) Análise de sensibilidade — vapor

11. Varie a quantidade de vapor injetado.
    
12. Construa o gráfico:
    

$$  
T_{ad} \text{ vs quantidade de vapor}  
$$

---

### (e) Comparação entre estratégias

13. Compare:
    

- excesso de ar
    
- injeção de vapor
    

14. Discuta:
    

- eficiência térmica
    
- efeito do calor específico
    
- implicações industriais
    

---

# ⚗️ **Questão 3 — Combustão com dissociação química (duas incógnitas)**

Considere novamente a combustão do metano com ar seco em um queimador adiabático. Os reagentes entram a $25^\circ C$.

Agora, admita que ocorre dissociação química nos produtos, segundo a reação de equilíbrio:

$$  
CO_2 \rightleftharpoons CO + \frac{1}{2}O_2  
$$

---

## **Solicita-se:**

### (a) Modelagem

1. Escreva a reação de combustão completa do metano.
    
2. Considere que uma fração $\xi$ do $CO_2$ sofre dissociação.
    
3. Expresse as quantidades molares de:
    
    - $CO_2$
        
    - $CO$
        
    - $O_2$
        

em função de $\xi$.

---

### (b) Equilíbrio químico

4. Escreva a expressão da constante de equilíbrio:
    

$$  
K_p(T) = \frac{P_{CO} \cdot P_{O_2}^{1/2}}{P_{CO_2}}  
$$

5. Expresse essa equação em função de $\xi$ e $T$.
    

---

### (c) Balanço de energia

6. Formule o balanço de energia adiabático considerando a composição dependente de $\xi$.
    

---

### (d) Sistema não linear

7. Mostre que o problema resulta em um sistema:
    

$$  
\begin{cases}  
f_1(T, \xi) = 0 \  
f_2(T, \xi) = 0  
\end{cases}  
$$

---

### (e) Solução numérica

8. Resolva o sistema para determinar:
    
    - temperatura de chama $T$
        
    - grau de dissociação $\xi$
        

---

### (f) Análise de sensibilidade

9. Avalie o efeito da pressão:
    

$$  
1 \leq P \leq 10 , \text{atm}  
$$

10. Construa gráficos de:
    

- $T$ vs $P$
    
- $\xi$ vs $P$
    

---

### (g) Discussão

11. Explique:
    

- por que a dissociação reduz a temperatura
    
- efeito da pressão no equilíbrio
    
- implicações físicas e industriais
    

---
