Perfeito — agora ficou mais claro o tipo de entrega que você quer.

Nesse segundo caso, o coração da atividade já não é um sistema linear, mas sim um **problema de balanço de energia com incógnita implícita**, em que o aluno precisa:

- fazer a estequiometria da combustão,
    
- determinar a composição dos produtos,
    
- calcular a entalpia de reação,
    
- calcular as entalpias sensíveis dos produtos,
    
- montar o balanço de energia adiabático,
    
- e encontrar a temperatura de chama, que aparece implicitamente na equação.
    

Esse é exatamente o tipo de problema muito bom para projeto, porque começa como uma questão “fechada” de encontrar uma variável, mas pode ser ampliado para análise paramétrica e implementação computacional. O próprio material de referência trata temperatura adiabática de chama como problema de solução numérica, com o balanço de energia sendo escrito em termos da variação de entalpia dos produtos desde $298 , \text{K}$ até $T_f$ , e a obra de Cutlip e Shacham organiza esse tipo de exercício justamente no contexto de resolução computacional de problemas de engenharia química .

Abaixo eu te proponho uma versão de **projeto avaliativo** muito mais rica a partir do seu exemplo.

---

# Projeto 2 — Temperatura adiabática de chama do metano com excesso de ar

## Contexto

A combustão completa do metano com ar é um dos problemas clássicos de balanço de massa e energia em engenharia química. Quando os reagentes entram a $25^\circ\text{C}$ e o queimador opera adiabaticamente, a temperatura final da chama deve ser obtida a partir do balanço de energia entre a entalpia de reação e as entalpias sensíveis dos produtos. A formulação leva naturalmente a uma equação não linear na temperatura final, o que a torna apropriada para resolução com métodos numéricos .

---

## Enunciado-base do projeto

Considere a combustão completa do metano com ar seco. Os reagentes entram no queimador a $25^\circ\text{C}$ e $1 , \text{atm}$. Inicialmente, admita combustão completa com $10%$ de excesso de ar e operação adiabática.

Pede-se:

### Parte A — Modelagem físico-química

1. Escreva a reação química balanceada da combustão completa do metano com excesso de ar.
    
2. Determine a composição molar dos produtos da combustão para $10%$ de excesso de ar.
    
3. Explique por que, nesse caso, haverá $O_2$ em excesso nos produtos.
    

### Parte B — Balanço de energia

4. Adotando $25^\circ\text{C}$ como estado de referência, determine a expressão do balanço de energia adiabático.
    
5. Calcule a entalpia padrão de reação da combustão do metano.
    
6. Escreva a entalpia sensível de cada espécie dos produtos na forma:
    

$$  
\Delta \hat{H}_i(T) = \int_{T_{ref}}^{T} \hat{C}_{p,i}(T), dT  
$$

7. Monte a equação final cuja incógnita é a temperatura adiabática de chama $T_{ad}$.
    

### Parte C — Solução numérica

8. Resolva numericamente a equação para encontrar $T_{ad}$.
    
9. O aluno pode escolher:
    
    - método da bisseção,
        
    - método de Newton-Raphson,
        
    - secante,
        
    - ou função pronta de Python/MATLAB.
        
10. Compare o resultado obtido por pelo menos dois procedimentos:
    

- um método implementado pelo aluno;
    
- uma rotina pronta.
    

### Parte D — Análise de sensibilidade

11. Varie o excesso de ar em uma faixa, por exemplo:
    

$$  
0% \leq \text{excesso de ar} \leq 100%  
$$

12. Construa o gráfico:
    

$$  
T_{ad} \text{ versus excesso de ar}  
$$

13. Interprete fisicamente a tendência observada.
    

### Parte E — Discussão técnica

14. Discuta:
    

- por que a temperatura adiabática de chama diminui com aumento do excesso de ar;
    
- qual o papel do nitrogênio do ar;
    
- por que a equação precisa ser resolvida numericamente;
    
- quais aproximações foram assumidas no problema.
    

---

# O que essa proposta avalia de fato

Essa atividade fica muito boa porque avalia várias competências ao mesmo tempo:

- **estequiometria de combustão**;
    
- **balanço de energia**;
    
- **uso de propriedades termodinâmicas**;
    
- **montagem de equação não linear**;
    
- **resolução numérica de uma incógnita implícita**;
    
- **análise de sensibilidade e interpretação física**.
    

Ou seja, ela deixa de ser apenas “ache $T_{ad}$” e passa a ser um miniestudo de caso.

---

# Versão mais robusta do enunciado para os alunos

Você pode entregar algo assim, já em formato mais acadêmico:

---

## Questão-Projeto: Combustão adiabática do metano com excesso de ar

A combustão completa do metano é descrita por uma reação exotérmica cuja temperatura final depende da quantidade de ar alimentada. Em um queimador adiabático, reagentes alimentados a $25^\circ\text{C}$ têm sua energia química convertida em aumento de temperatura dos produtos.

Considere a combustão completa do metano com ar seco, inicialmente com $10%$ de excesso de ar. Assuma pressão constante, ausência de perdas térmicas e ausência de dissociação química.

### Solicita-se:

1. Escrever a equação estequiométrica da combustão completa do metano com excesso de ar.
    
2. Determinar a vazão molar de cada espécie nos produtos.
    
3. Calcular a entalpia padrão de reação a $25^\circ\text{C}$.
    
4. Obter a expressão da entalpia sensível de cada produto gasoso.
    
5. Formular o balanço de energia adiabático.
    
6. Resolver numericamente a equação obtida para calcular a temperatura adiabática de chama.
    
7. Desenvolver um código computacional para automatizar o cálculo de $T_{ad}$.
    
8. Repetir os cálculos para diferentes valores de excesso de ar.
    
9. Construir um gráfico de $T_{ad}$ em função do excesso de ar.
    
10. Discutir os resultados obtidos, destacando os efeitos térmicos e físicos do ar em excesso.
    

---

# Como eu recomendaria estruturar a resolução esperada

## 1. Estequiometria

Para excesso de ar de $\epsilon$:

$$  
CH_4 + 2(1+\epsilon)O_2 + 7.52(1+\epsilon)N_2  
\rightarrow  
CO_2 + 2H_2O + 2\epsilon O_2 + 7.52(1+\epsilon)N_2  
$$

Para $\epsilon = 0.10$:

$$  
CH_4 + 2.2 O_2 + 8.272 N_2  
\rightarrow  
CO_2 + 2H_2O + 0.2 O_2 + 8.272 N_2  
$$

---

## 2. Balanço de energia adiabático

Como os reagentes entram a $25^\circ\text{C}$ e esse é o estado de referência:

$$  
\sum n_i \Delta \hat{H}_{sens,i}(T_{ad}) + \Delta \hat{H}_{rxn}^\circ = 0  
$$

ou equivalentemente,

$$  
\sum n_i \Delta \hat{H}_{sens,i}(T_{ad}) = - \Delta \hat{H}_{rxn}^\circ  
$$

---

## 3. Natureza numérica do problema

A temperatura aparece dentro das integrais de capacidade calorífica, ou dentro de correlações de $C_p(T)$. Portanto, a equação final assume a forma:

$$  
f(T_{ad}) = \sum n_i \Delta \hat{H}_{sens,i}(T_{ad}) + \Delta \hat{H}_{rxn}^\circ = 0  
$$

que é uma equação algébrica não linear em $T_{ad}$.

Isso encaixa muito bem no tipo “encontre o valor de uma variável”, mas com um ganho conceitual muito maior do que simplesmente substituir valores em fórmulas.

---

# O melhor ganho pedagógico: sensibilidade ao excesso de ar

Aqui está o grande diferencial da sua ideia.

Em vez de o aluno parar em um único valor para $10%$ de excesso de ar, ele pode estudar:

- $\epsilon = 0.00$
    
- $\epsilon = 0.05$
    
- $\epsilon = 0.10$
    
- $\epsilon = 0.20$
    
- $\epsilon = 0.50$
    
- $\epsilon = 1.00$
    

e depois discutir o comportamento de:

$$  
T_{ad} = f(\epsilon)  
$$

Fisicamente, isso é excelente, porque o aluno percebe que:

- mais ar significa mais massa sendo aquecida;
    
- o nitrogênio funciona como “diluente térmico”;
    
- a energia liberada pela reação passa a ser distribuída entre mais mols de gás;
    
- logo, a temperatura final cai.
    

Essa é exatamente a transição de uma **questão de cálculo** para uma **atividade de engenharia**.

---

# Sugestão de extensões opcionais para alunos fortes

Você pode colocar uma seção “desafio”:

### Desafio 1

Comparar os resultados usando:

- $C_p$ constante;
    
- $C_p(T)$ variável.
    

### Desafio 2

Avaliar a diferença entre:

- ar estequiométrico;
    
- excesso de ar;
    
- deficiência de ar.
    

### Desafio 3

Estudar o efeito da temperatura de entrada dos reagentes, por exemplo:

- $25^\circ\text{C}$,
    
- $100^\circ\text{C}$,
    
- $200^\circ\text{C}$.
    

### Desafio 4

Estimar, qualitativamente, em que condições a hipótese de combustão completa sem dissociação começa a ficar mais questionável.

---

# Critério de avaliação sugerido

|Critério|Peso|
|---|--:|
|Estequiometria e modelagem|20%|
|Formulação correta do balanço de energia|20%|
|Implementação numérica|20%|
|Análise de sensibilidade|20%|
|Discussão física dos resultados|20%|

---

# Minha recomendação como desenho de avaliação

Eu faria essa atividade em **duas camadas**:

**Camada obrigatória**

- cálculo de $T_{ad}$ para $10%$ de excesso de ar;
    
- desenvolvimento do algoritmo;
    
- validação do valor obtido.
    

**Camada de projeto**

- análise paramétrica do excesso de ar;
    
- gráfico e interpretação;
    
- comparação entre modelos simplificados e mais realistas.
    

Assim você consegue:

- manter uma parte objetiva e comparável entre os grupos;
    
- e ao mesmo tempo abrir espaço para profundidade analítica.
    

---

# Formulação final que eu usaria com seus alunos

> “A partir do problema de combustão adiabática do metano com excesso de ar, desenvolva um modelo matemático e computacional para determinar a temperatura adiabática de chama. O estudo deve incluir a formulação estequiométrica, o cálculo das entalpias envolvidas, a resolução numérica da equação não linear resultante e uma análise de sensibilidade da temperatura de chama em função do excesso de ar.”

Essa frase já dá cara de projeto, sem perder o rigor técnico.

Se você quiser, no próximo passo eu posso montar **3 questões-projeto completas nesse mesmo estilo**: uma de dificuldade básica, uma intermediária e uma avançada, todas sobre combustão, energia e métodos numéricos.