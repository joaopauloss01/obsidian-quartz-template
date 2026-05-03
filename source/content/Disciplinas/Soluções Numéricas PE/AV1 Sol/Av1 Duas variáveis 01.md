Perfeito — isso fecha o projeto com um nível **excelente de sofisticação** 👏

Agora você quer um problema onde o aluno precise encontrar **duas incógnitas simultaneamente**, o que naturalmente leva a:

- sistema **não linear**
    
- necessidade de **método iterativo**
    
- interpretação física mais rica
    

Vou te propor um problema clássico, muito usado em engenharia química, que encaixa perfeitamente com tudo que você já construiu:

---

# 🔥 QUESTÃO-PROJETO FINAL — Combustão com dissociação (2 incógnitas)

## 🎯 Ideia central

Agora o aluno não vai mais assumir combustão “perfeita”.

👉 Em altas temperaturas, ocorre **dissociação química**:

$$  
CO_2 \rightleftharpoons CO + \frac{1}{2}O_2  
$$

Isso faz com que:

- a temperatura final **caia**
    
- a composição **mude**
    
- o problema deixe de ser direto
    

---

# 📘 ENUNCIADO PROPOSTO

## Questão — Temperatura de chama com dissociação química

Considere a combustão do metano com ar seco em um queimador adiabático. Os reagentes entram a $25^\circ C$ e a pressão é constante.

Diferentemente do caso anterior, admita agora que, devido às altas temperaturas, ocorre dissociação do dióxido de carbono segundo o equilíbrio:

$$  
CO_2 \rightleftharpoons CO + \frac{1}{2}O_2  
$$

Assuma combustão completa do metano seguida de equilíbrio químico dessa reação.

---

## 🔹 Solicita-se:

### Parte A — Modelagem

1. Escreva a reação global de combustão do metano com ar estequiométrico.
    
2. Considere que uma fração $\xi$ de $CO_2$ sofre dissociação.
    
3. Escreva a composição molar dos produtos em função de $\xi$.
    

---

### Parte B — Equilíbrio químico

4. Escreva a expressão da constante de equilíbrio:
    

$$  
K_p(T) = \frac{P_{CO} \cdot P_{O_2}^{1/2}}{P_{CO_2}}  
$$

5. Expresse $K_p$ em função de $\xi$ e da temperatura $T$.
    

---

### Parte C — Balanço de energia

6. Escreva o balanço de energia adiabático:
    

$$  
\sum n_i \Delta \hat{H}_{sens,i}(T) + \Delta \hat{H}_{rxn}^\circ = 0  
$$

7. Note que agora:
    
    - as quantidades de espécies dependem de $\xi$
        
    - a temperatura é desconhecida
        

---

# 🚨 Resultado importante

Você terá um sistema com **duas incógnitas**:

$$  
\begin{cases}  
f_1(T, \xi) = 0 & \text{(balanço de energia)} \  
f_2(T, \xi) = 0 & \text{(equilíbrio químico)}  
\end{cases}  
$$

---

# 🧮 PARTE D — Solução numérica

8. Resolva o sistema não linear para obter:
    
    - temperatura de chama $T$
        
    - grau de dissociação $\xi$
        

Métodos possíveis:

- Newton-Raphson para sistemas
    
- `fsolve` (Python/MATLAB)
    

---

# 📊 PARTE E — Análise de sensibilidade

9. Avalie o efeito da pressão:
    

$$  
1 \leq P \leq 10 \ \text{atm}  
$$

10. Plote:
    

- $T$ vs $P$
    
- $\xi$ vs $P$
    

---

# 🧠 PARTE F — Discussão física

Peça para discutir:

---

### 🔹 1. Por que a dissociação reduz a temperatura?

👉 Parte da energia vai para quebrar ligações químicas

---

### 🔹 2. Por que aumenta com temperatura?

👉 Equilíbrio favorece produtos (Le Chatelier)

---

### 🔹 3. Efeito da pressão

- alta pressão → favorece menos mols → menos dissociação
    

---

# 💡 Por que essa questão é perfeita

Ela fecha o curso com:

### ✔ Sistema não linear acoplado

- duas equações
    
- duas incógnitas
    

### ✔ Integra:

- balanço de energia
    
- equilíbrio químico
    
- métodos numéricos
    

### ✔ Introduz fenômeno real:

- combustão real ≠ combustão ideal
    

---

# 🔥 Alternativa (caso queira algo mais “processo”)

Se quiser algo menos termoquímico e mais “engenharia de processo”, outra excelente opção:

---

## 💧 Mistura + reação com duas incógnitas

### Problema:

Reator CSTR com reação:

$$  
A \rightarrow B  
$$

Cinética:

$$  
r = k C_A e^{-E/RT}  
$$

Incógnitas:

- $T$ (temperatura)
    
- $C_A$ (concentração)
    

---

Sistema:

$$  
\begin{cases}  
\text{Balanço de massa} \  
\text{Balanço de energia}  
\end{cases}  
$$

👉 Esse também dá um sistema não linear acoplado clássico

---

# 🏆 Minha recomendação

Para fechar com chave de ouro MESMO:

👉 use a **combustão com dissociação**

Porque:

- conecta com o problema anterior (chama)
    
- mostra limitação do modelo ideal
    
- exige mais maturidade matemática
    

---

# 🚀 Se quiser ir ainda mais longe

Posso montar pra você:

- gabarito completo com desenvolvimento
    
- código base em Python (com `fsolve`)
    
- versão simplificada para alunos mais fracos
    
- versão hardcore com múltiplas reações (CO, H₂, etc.)
    

Só me dizer o nível da turma 👨‍🏫