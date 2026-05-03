Excelente — isso aqui já sobe o nível da atividade para **engenharia real de processo**. Você sai de “resolver um problema” e entra em **tomada de decisão de operação** (controle térmico de chama), que é exatamente o que acontece em queimadores industriais.

A ideia de comparar:

- excesso de ar  
    versus
    
- injeção de vapor
    

é **didaticamente muito forte**, porque ambos reduzem a temperatura, mas por mecanismos diferentes.

Vou estruturar isso como uma evolução natural do projeto.

---

# 🔥 EXTENSÃO DO PROJETO — Controle de temperatura de chama

## 🎯 Nova proposta

O aluno deve comparar duas estratégias para reduzir a temperatura adiabática de chama:

1. **Excesso de ar**
    
2. **Injeção de vapor d’água**
    

---

# 🧩 PARTE F — Nova modelagem: injeção de vapor

## 🔹 Questão 10 — Nova formulação

Agora considere:

- combustão completa de metano
    
- ar estequiométrico (ou fixo)
    
- injeção de vapor na alimentação
    

A reação fica:

$$  
CH_4 + 2O_2 + 7.52N_2 + n_{H_2O,inj}  
\rightarrow  
CO_2 + (2 + n_{H_2O,inj})H_2O + 7.52N_2  
$$

---

## 🔹 Ponto-chave para o aluno perceber

- O vapor **não participa da reação**
    
- Mas **absorve energia sensível**
    
- Atua como **diluente térmico**, assim como o N₂
    

---

# ⚖️ PARTE G — Novo balanço de energia

Agora o balanço vira:

$$  
\sum n_i \Delta \hat{H}_{sens,i}(T_{ad}) + \Delta \hat{H}_{rxn}^\circ = 0  
$$

Mas agora:

- o número de mols de $H_2O$ é maior
    
- entra um novo termo energético (do vapor injetado)
    

Se o vapor entra a $25^\circ C$:

👉 entra só como carga térmica

Se entrar quente:

👉 entra também com entalpia inicial (nível mais avançado)

---

# 🧮 PARTE H — Nova incógnita

A equação continua sendo:

$$  
f(T_{ad}) = 0  
$$

Mas agora depende de:

$$  
T_{ad} = f(n_{H_2O,inj})  
$$

---

# 📊 PARTE I — Análise de sensibilidade

## 🔹 Questão 11

Variar:

$$  
0 \leq n_{H_2O,inj} \leq 5 \ (\text{mol de vapor por mol de CH₄})  
$$

Plotar:

$$  
T_{ad} \text{ vs } n_{H_2O,inj}  
$$

---

# 🔥 PARTE J — Comparação direta (o ouro do projeto)

## 🔹 Questão 12 — Comparação entre estratégias

Construir dois gráficos:

1. $T_{ad}$ vs excesso de ar
    
2. $T_{ad}$ vs vapor injetado
    

---

## 🔹 Pergunta central (nível engenharia mesmo)

> Qual estratégia é mais eficiente para reduzir a temperatura de chama?

---

# 🧠 PARTE K — Discussão conceitual (ESSENCIAL)

Aqui está onde o aluno realmente aprende.

Peça para discutir:

---

### 1. Mecanismo físico

- Excesso de ar:
    
    - adiciona **O₂ + N₂**
        
    - aumenta muito o número de mols
        
    - reduz temperatura
        
- Vapor:
    
    - adiciona **H₂O**
        
    - tem **alto calor específico**
        
    - absorve energia com mais eficiência
        

---

### 2. Eficiência térmica

Pergunta ótima:

> Para reduzir a mesma temperatura, qual precisa de menos massa adicionada?

---

### 3. Impacto industrial

- excesso de ar:
    
    - reduz eficiência de combustão
        
    - aumenta perdas térmicas
        
- vapor:
    
    - usado em:
        
        - controle de NOx
            
        - controle de temperatura de chama
            
        - reforma a vapor
            

---

### 4. Emissões (nível avançado)

- temperatura menor → menos NOx
    
- vapor é frequentemente usado exatamente por isso
    

---

# 💡 Insight que você quer que o aluno tenha

Essa é a conclusão ideal:

👉 **Nem todo “diluente térmico” é igual**

- N₂ → diluição por quantidade
    
- H₂O → diluição + alta capacidade térmica
    

---

# 📈 Sugestão de gráfico final (muito forte didaticamente)

Plotar no mesmo gráfico:

$$  
T_{ad} \text{ vs variável de controle}  
$$

com:

- curva 1: excesso de ar
    
- curva 2: vapor
    

👉 Isso dá um resultado visual excelente

---

# 🏆 Versão final do enunciado (nível projeto completo)

Você pode colocar assim:

---

## Extensão do Projeto — Estratégias de controle de temperatura de chama

Além do uso de excesso de ar, uma estratégia comum na indústria para controle da temperatura de chama é a injeção de vapor d’água.

1. Modifique o modelo anterior para incluir injeção de vapor na alimentação.
    
2. Recalcule a temperatura adiabática de chama para diferentes quantidades de vapor injetado.
    
3. Compare os resultados com aqueles obtidos variando o excesso de ar.
    
4. Avalie qual estratégia é mais eficiente para reduzir a temperatura.
    
5. Discuta as implicações físicas e industriais dos resultados obtidos.
    

---

# 🎓 Por que essa ideia é excelente (visão de professor)

Você acabou de transformar:

👉 um exercício de balanço de energia  
em  
👉 um problema de **engenharia de operação + otimização + decisão**

Isso está completamente alinhado com o que se espera de formação em métodos numéricos aplicados à engenharia:

- modelar
    
- resolver numericamente
    
- analisar comportamento
    
- interpretar fisicamente
    
- comparar estratégias
    

---

Se quiser, no próximo passo eu posso:

- montar **o código-base em Python** para os alunos (com estrutura pronta),
    
- ou criar uma **rubrica detalhada de correção**,
    
- ou ainda um **gabarito comentado completo** (nível professor).