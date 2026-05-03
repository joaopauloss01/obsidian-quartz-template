
---

# 📘 PROJETO – Sistemas de Mistura com Reciclo e Métodos Numéricos

## 🎯 Objetivo geral

Modelar, analisar e resolver numericamente sistemas de tanques perfeitamente agitados com reciclo, avaliando:

- balanços de massa
    
- resolução de sistemas lineares
    
- análise de sensibilidade
    
- implementação computacional
    

---

# 🧩 PARTE 1 — Modelagem (Base obrigatória)

### 🔹 Questão 1 — Formulação do modelo

A partir do sistema fornecido:

1. Derive os balanços de massa para cada tanque em regime permanente:
    

$$  
\text{Acúmulo} = \text{Entrada} - \text{Saída} = 0  
$$

2. Mostre explicitamente o sistema linear na forma matricial:
    

$$  
A \cdot \mathbf{C} = \mathbf{b}  
$$

onde:

- $\mathbf{C} = [C_1, C_2, C_3]^T$
    

---

### 🔹 Questão 2 — Interpretação física

Explique:

- Por que o sistema é linear?
    
- Qual o efeito físico do reciclo $Q_{31}$?
    
- O sistema teria solução única? Justifique com base em álgebra linear.
    

---

# 🧮 PARTE 2 — Solução Numérica

### 🔹 Questão 3 — Resolução manual (nível básico)

Resolva o sistema linear:

- Por substituição OU eliminação de Gauss (à mão)
    

---

### 🔹 Questão 4 — Implementação computacional

Implemente em Python ou MATLAB:

- Método direto (ex: `numpy.linalg.solve`)
    

Depois:

- Compare com solução manual
    
- Calcule o erro:
    

$$  
\text{erro} = |A\mathbf{C} - \mathbf{b}|  
$$

---

# ⚙️ PARTE 3 — Generalização (nível intermediário)

Agora começa o verdadeiro ganho pedagógico.

### 🔹 Questão 5 — Sistema genérico

Generalize o problema:

- $Q_{01}, Q_{02}, Q_{31}$ quaisquer
    
- $C_{01}, C_{02}$ quaisquer
    

Seu código deve:

- Receber esses valores como entrada
    
- Retornar $C_1, C_2, C_3$
    

---

### 🔹 Questão 6 — Análise paramétrica

Varie:

- $Q_{31}$ de 0 até 10
    

Plote:

- $C_1, C_2, C_3$ vs $Q_{31}$
    

👉 Interprete fisicamente:

- O reciclo aumenta ou diminui a concentração?
    
- Existe limite?
    

---

# 🚀 PARTE 4 — Extensão (nível avançado)

Aqui você diferencia alunos medianos dos excelentes.

---

### 🔹 Questão 7 — Sistema não linear

Agora considere:

- reação no tanque 2:
    

$$  
-r = k C_2^2  
$$

Novo balanço:

$$  
Q_{12}C_1 - Q_{23}C_2 + Q_{02}C_{02} - kV C_2^2 = 0  
$$

👉 Resultado: sistema **não linear**

---

### 🔹 Questão 8 — Método numérico

Resolver usando:

- Newton-Raphson para sistemas OU
    
- `fsolve` (Python/MATLAB)
    

---

### 🔹 Questão 9 — Sensibilidade

Analise efeito de $k$:

- $k \in [0, 2]$
    

Plote:

- $C_2$ vs $k$
    

---

# 💻 PARTE 5 — Boas práticas de programação

Exigir dos alunos:

✔ Funções bem definidas  
✔ Comentários explicativos  
✔ Organização (entrada → processamento → saída)  
✔ Validação de erro

---

# 🧠 PARTE 6 — Discussão conceitual (ESSENCIAL)

Perguntas abertas:

1. Qual método numérico é mais adequado para sistemas lineares grandes?
    
2. Quando evitar inversão de matriz?
    
3. O sistema pode se tornar mal condicionado?
    
4. Qual a interpretação física de um sistema singular?
    

---

# 📊 PARTE 7 — Entregáveis

Os alunos devem entregar:

### 📄 Relatório técnico

- Modelagem
    
- Equações
    
- Resultados
    
- Discussão
    

### 💻 Código

- Comentado
    
- Reprodutível
    

### 📈 Gráficos

- Paramétricos
    
- Sensibilidade
    

---

# 🎓 Critério de avaliação (sugestão)

|Critério|Peso|
|---|---|
|Modelagem correta|20%|
|Implementação numérica|25%|
|Análise de resultados|25%|
|Clareza e organização|15%|
|Extensões/insights|15%|

---

# 💡 Dica pedagógica (nível PhD mesmo)

Esse projeto está excelente porque percorre exatamente o pipeline clássico da engenharia numérica:

1. **Modelo físico → equações**
    
2. **Equações → sistema algébrico**
    
3. **Sistema → algoritmo**
    
4. **Algoritmo → código**
    
5. **Código → interpretação**
    

Esse fluxo é exatamente o defendido em ensino moderno de métodos numéricos aplicados à engenharia .

---
