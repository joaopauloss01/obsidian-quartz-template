Excelente — agora a questão realmente sobe para nível de **engenharia + projeto + análise crítica**, mantendo viável para 2h. Vou te propor uma versão final já refinada, equilibrando **cálculo leve + interpretação + raciocínio físico**.

---

# 🔵 QUESTÃO 3 — (Versão final aprimorada)

A Figura X apresenta a variação do **NPSH disponível** em função da temperatura para um sistema de bombeamento.

Considere os seguintes dados do sistema:

- Pressão atmosférica: $10{,}3\ \text{m}$
    
- Altura geométrica de sucção: $2{,}0\ \text{m}$
    
- Perdas na linha de sucção: $1{,}5\ \text{m}$
    
- $NPSH_{req} = 8{,}0\ \text{m}$
    

---

## (a)

Escreva a equação geral utilizada para calcular o $NPSH_{disp}$ e, a partir dos dados fornecidos, apresente a equação específica do sistema em função da pressão de vapor.

---

## (b)

Com base no gráfico, determine a temperatura máxima de operação **sem cavitação**.

---

## (c)

Considere que o projeto exige uma **margem mínima de segurança de 2 m**, isto é:

$$  
NPSH_{disp} - NPSH_{req} \geq 2  
$$

Determine, a partir do gráfico, a **temperatura máxima de operação segura**.

---

## (d)

Explique como a **vazão do sistema** influencia o $NPSH_{disp}$ e discuta qualitativamente o que ocorre com o risco de cavitação quando a vazão aumenta.

---

## (e)

Considere agora que, ao longo do tempo, ocorre incrustação na tubulação de sucção, aumentando as perdas de carga em **30%**.

1. Estime o novo valor das perdas
    
2. Avalie se a margem de 2 m ainda é atendida para operação a $60^\circ C$
    
3. Discuta se o sistema continua seguro ou se requer intervenção
    

---

# 🎯 Por que essa versão ficou ideal

### ✔ Não ficou trivial

O aluno **não pode só ler o gráfico**:

- precisa entender de onde ele vem
    
- precisa manipular o conceito
    

---

### ✔ Avalia exatamente o que você queria

|Conceito|Avaliado?|
|---|---|
|Equação de NPSH|✔|
|Dependência com temperatura|✔|
|Influência da vazão|✔|
|Perda de carga|✔|
|Margem de projeto|✔✔|
|Incrustação (realismo industrial)|✔✔|

---

### ✔ Nível cognitivo (Bloom)

- (a) → compreensão + formulação
    
- (b) → leitura/interpretação
    
- (c) → análise de projeto
    
- (d) → explicação física
    
- (e) → aplicação + julgamento
    

---

# 💡 (Opcional) Gabarito estruturado (para você)

Se quiser corrigir rápido, você pode esperar:

### (a)

$$  
NPSH_{disp} = \frac{P_{atm}}{\gamma} + z - h_f - \frac{P_v}{\gamma}  
$$

Para o sistema:  
$$  
NPSH_{disp} = 10{,}3 + 2{,}0 - 1{,}5 - P_v = 10{,}8 - P_v  
$$

---

### (d)

- $h_f \propto Q^2$
    
- aumento da vazão → aumenta perda → reduz $NPSH_{disp}$ → maior risco de cavitação
    

---

### (e)

- nova perda: $1{,}5 \times 1{,}3 = 1{,}95\ \text{m}$
    
- reduz diretamente o $NPSH_{disp}$
    
- margem pode deixar de ser atendida → risco operacional
    

---

# 🚀 Resultado final

Essa questão agora está:

- ✔ nível prova de engenharia federal
    
- ✔ alinhada com prática industrial
    
- ✔ avaliando raciocínio real
    

---

Se quiser, no próximo passo posso:

✅ elevar as questões de trocadores para esse mesmo nível  
✅ criar uma questão integradora (bomba + NPSH + trocador)  
✅ ou montar a prova final diagramada pronta pra impressão