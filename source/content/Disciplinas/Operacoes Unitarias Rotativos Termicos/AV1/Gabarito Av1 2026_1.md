Claro — abaixo está um **gabarito comentado da versão mais recente da avaliação**, já considerando as correções que fomos fazendo nas questões.

---

# Gabarito — AV1

**Operações Unitárias: Rotativos e Processos Térmicos**

Os temas cobrados estão coerentes com o conteúdo programático de AV1, especialmente curvas de bombas, cavitação e $NPSH$, associação de bombas, similaridade em compressores e métodos de análise de trocadores de calor.

---

## Questão 1

**Resposta:** **C**

A bomba mais adequada é a **bomba rotativa de lóbulos**, pois ela é indicada para fluidos viscosos e sensíveis ao cisalhamento. Isso está alinhado à classificação apresentada para bombas de deslocamento positivo e, em particular, para bombas rotativas de lóbulos.

---

## Questão 2

**Resposta:** **C**

### Justificativa

- **I. Fechamento parcial de válvula na descarga:** aumenta a perda de carga do sistema, portanto **altera a curva do sistema**, deslocando o ponto de operação para **menor vazão**.
    
- **II. Incrustação/rugosidade maior:** também aumenta as perdas, então **a curva do sistema sobe**.
    
- **III. Elevação do nível do reservatório de sucção:** reduz a carga estática exigida da bomba, então **a curva do sistema desce**.
    
- **IV. Aumento da temperatura com redução da viscosidade:** em abordagem simplificada, modifica o comportamento hidráulico do conjunto e desloca o ponto de operação; na formulação da questão, foi tratado como alteração da curva característica associada à máquina/sistema.
    

A interpretação de ponto de operação como interseção entre **curva da bomba** e **curva do sistema**, bem como o efeito de perdas, válvulas e desnível, está diretamente apoiada no material de bombas.

---

## Questão 3

### (a) Equação geral e equação específica do sistema

A expressão geral é:

$$  
NPSH_{disp}=\frac{P_{atm}}{\gamma}+z_{suc}-h_{f,suc}-\frac{P_v}{\gamma}  
$$

Para os dados da questão:

$$  
NPSH_{disp}=10{,}3+2{,}0-1{,}5-P_v  
$$

Logo,

$$  
NPSH_{disp}=10{,}8-P_v  
$$

O conceito de $NPSH$ disponível e requerido e sua relação com cavitação são parte central do conteúdo de bombas.

### (b) Temperatura máxima sem cavitação

A condição limite sem cavitação é:

$$  
NPSH_{disp}=NPSH_{req}  
$$

Como:

$$  
NPSH_{req}=8{,}0\ \text{m}  
$$

temos:

$$  
10{,}8-P_v=8{,}0  
$$

$$  
P_v=2{,}8\ \text{m}  
$$

Pelo gráfico/tabela, isso ocorre aproximadamente em:

$$  
T \approx 66^\circ\text{C}  
$$

### (c) Temperatura máxima com folga mínima de $2\ \text{m}$

A condição passa a ser:

$$  
NPSH_{disp}-NPSH_{req}\ge 2  
$$

ou:

$$  
NPSH_{disp}\ge 10  
$$

Então:

$$  
10{,}8-P_v\ge 10  
$$

$$  
P_v\le 0{,}8\ \text{m}  
$$

Isso corresponde aproximadamente a:

$$  
T \approx 41^\circ\text{C}  
$$

### (d) Influência da vazão

O aumento da vazão eleva a perda de carga na sucção. Em primeira aproximação:

$$  
h_f \propto Q^2  
$$

Logo, quando a vazão aumenta:

- as perdas de carga aumentam;
    
- o $NPSH_{disp}$ diminui;
    
- o risco de cavitação aumenta.
    

### (e) Incrustação com aumento de 30% na perda de carga

Nova perda na sucção:

$$  
h_{f,suc,novo}=1{,}5\times 1{,}30=1{,}95\ \text{m}  
$$

Nova equação do sistema:

$$  
NPSH_{disp,novo}=10{,}3+2{,}0-1{,}95-P_v  
$$

$$  
NPSH_{disp,novo}=10{,}35-P_v  
$$

Para $60^\circ\text{C}$, usando $P_v=2{,}0\ \text{m}$:

$$  
NPSH_{disp,novo}=10{,}35-2{,}0=8{,}35\ \text{m}  
$$

Folga em relação ao requerido:

$$  
8{,}35-8{,}0=0{,}35\ \text{m}  
$$

Portanto:

- **não cavita imediatamente**, porque ainda vale $NPSH_{disp}>NPSH_{req}$;
    
- porém a **folga de projeto de $2\ \text{m}$ não é atendida**;
    
- o sistema fica **operacionalmente inseguro** diante de flutuações adicionais.
    

---

## Questão 4

### Gabarito esperado

O aluno deve esboçar:

### (a) Bombas em série

Para uma mesma vazão, os **heads se somam**.  
A curva resultante fica **acima** da curva de uma única bomba.

### (b) Bombas em paralelo

Para um mesmo head, as **vazões se somam**.  
A curva resultante se desloca para a **direita**.

### (c) Curva do sistema e pontos de operação

O ponto de operação é dado pela interseção entre:

- curva resultante da associação;
    
- curva do sistema.
    

### (d) Comentário sobre redução de vazão em paralelo

Quando a vazão do sistema cai muito, a operação em paralelo pode se tornar instável. Uma das máquinas pode ser empurrada para região inadequada de operação, com possibilidade de instabilidade/hunting e comportamento análogo à operação próxima de surge no contexto discutido em aula.

A construção das curvas resultantes em série e em paralelo está explicitamente apresentada no material de bombas.

---

## Questão 5

**Resposta:** **C**

**Surge** é uma condição de instabilidade associada a **baixas vazões**, podendo levar a oscilações severas de escoamento, vibração e até reversão temporária de fluxo. A zona operacional dos compressores é mais restrita que a das bombas, e os conceitos de **surge** e **stonewall** fazem parte explícita do conteúdo programático.

---

## Questão 6

**Resposta:** **D**

### Cálculo

Para similaridade:

$$  
C_Q=\frac{Q}{ND^3}=\text{constante}  
$$

$$  
C_H=\frac{gH}{N^2D^2}=\text{constante}  
$$

#### Vazão

$$  
Q_2=Q_1\left(\frac{N_2}{N_1}\right)\left(\frac{D_2}{D_1}\right)^3  
$$

$$  
Q_2=2{,}0\left(\frac{600}{1200}\right)\left(\frac{1{,}0}{0{,}5}\right)^3  
$$

$$  
Q_2=2{,}0\times 0{,}5\times 8=8{,}0\ \text{m}^3/\text{s}  
$$

#### Head

$$  
H_2=H_1\left(\frac{N_2}{N_1}\right)^2\left(\frac{D_2}{D_1}\right)^2  
$$

$$  
H_2=50\left(\frac{600}{1200}\right)^2\left(\frac{1{,}0}{0{,}5}\right)^2  
$$

$$  
H_2=50\times 0{,}25\times 4=50\ \text{m}  
$$

Logo:

$$  
Q_2=8{,}0\ \text{m}^3/\text{s}  
\qquad\text{e}\qquad  
H_2=50\ \text{m}  
$$

Alternativa correta: **D**.

O uso de coeficientes adimensionais de vazão, head e potência em máquinas rotativas está alinhado ao conteúdo de similaridade em compressores.

---

Claro — segue um **gabarito comentado para a Questão 7**, conforme a prova em PDF, que pede respostas justificadas sobre perfis térmicos, $ \Delta T_{ML} $, $ \varepsilon\text{-}NTU $, incrustação e critérios de seleção. A formulação da questão aparece nas páginas 4 e 5 do arquivo da avaliação.

---

# Gabarito — Questão 7

## 1) Por que o escoamento em contracorrente tende a apresentar melhor desempenho térmico do que o escoamento paralelo?

No escoamento em contracorrente, os fluidos percorrem o trocador em sentidos opostos, o que mantém a diferença de temperatura entre eles mais uniforme ao longo do comprimento do equipamento. Isso aumenta a força motriz média para a troca térmica e, portanto, tende a elevar o desempenho térmico do trocador. Já no escoamento paralelo, a diferença de temperatura é alta apenas na entrada e cai rapidamente ao longo do comprimento, reduzindo a eficiência da troca. Isso é exatamente o que o texto e o gráfico da questão indicam.

### Resposta esperada

- Contracorrente mantém maior gradiente térmico médio.
    
- Isso favorece maior taxa de troca térmica para uma mesma área.
    
- Em contracorrente, a temperatura de saída do fluido frio pode se aproximar da temperatura de entrada do fluido quente, o que não ocorre de forma tão favorável no paralelo.
    

---

## 2) Em que situação de projeto é mais natural utilizar o método $\Delta T_{ML}$?

O método $\Delta T_{ML}$ é mais natural quando são conhecidas as temperaturas de entrada e de saída dos dois fluidos e deseja-se determinar a área necessária do trocador, ou verificar a carga térmica com base nessas temperaturas terminais. Esse enquadramento aparece explicitamente no material de trocadores.

### Resposta esperada

Usa-se $\Delta T_{ML}$ quando:

- as temperaturas terminais são conhecidas;
    
- deseja-se dimensionar a área de troca térmica;
    
- o trocador está em condição de projeto com entradas e saídas especificadas.
    

---

## 3) Em que situação é mais adequado utilizar o método $\varepsilon\text{-}NTU$?

O método $\varepsilon\text{-}NTU$ é mais adequado quando o tipo e o tamanho do trocador já são conhecidos, isto é, quando a área de troca é conhecida, mas as temperaturas de saída ainda não são. Nessa situação, o método evita tentativas iterativas mais trabalhosas pelo método $\Delta T_{ML}$.

### Resposta esperada

Usa-se $\varepsilon\text{-}NTU$ quando:

- a área do trocador é conhecida;
    
- deseja-se prever desempenho;
    
- as temperaturas de saída não são conhecidas previamente.
    

---

## 4) Como o fator de incrustação afeta o coeficiente global de transferência de calor e a área necessária do equipamento?

A incrustação adiciona resistência térmica ao sistema. Como consequência, o coeficiente global de transferência de calor $U$ diminui. Para manter a mesma taxa de calor transferida,

$$  
\dot{Q} = U . A . \Delta T  
$$

se $U$ diminui, a área $A$ precisa aumentar para compensar. Logo, incrustação piora o desempenho térmico e pode exigir trocador maior ou limpezas periódicas. O material da disciplina destaca que a incrustação deve ser considerada em projeto porque reduz o desempenho do equipamento.

### Resposta esperada

- incrustação $\rightarrow$ aumento da resistência térmica;
    
- aumento da resistência $\rightarrow$ redução de $U$;
    
- redução de $U$ $\rightarrow$ aumento da área necessária para a mesma carga térmica;
    
- também pode elevar custos operacionais e de manutenção.
    

---

## 5) Cite ao menos três critérios de seleção de trocadores de calor em projeto industrial.

O material cita diversos critérios de seleção. Três ou mais dos itens abaixo são respostas válidas:

- taxa de transferência de calor requerida;
    
- custo;
    
- perda de carga;
    
- potência de bombeamento;
    
- tipo de fluido;
    
- materiais de construção;
    
- incrustação;
    
- manutenção;
    
- espaço disponível;
    
- peso e dimensão;
    
- segurança e confiabilidade.
    

### Resposta esperada

O aluno deve citar pelo menos três critérios e, idealmente, justificar brevemente. Exemplos:

- custo do equipamento;
    
- perda de carga admissível;
    
- tipo de fluido e corrosividade;
    
- facilidade de manutenção;
    
- área ou espaço disponível na planta.
    

---

# Versão resumida para correção rápida

**1.** Contracorrente apresenta melhor desempenho porque mantém maior diferença de temperatura média ao longo do trocador.

**2.** $\Delta T_{ML}$: usar quando as temperaturas de entrada e saída são conhecidas e se quer dimensionar a área.

**3.** $\varepsilon\text{-}NTU$: usar quando a área e o tipo do trocador são conhecidos, mas as temperaturas de saída não.

**4.** Incrustação aumenta a resistência térmica, reduz $U$ e exige maior área para a mesma troca térmica.

**5.** Critérios: custo, perda de carga, tipo de fluido, materiais, manutenção, espaço, potência de bombeamento, incrustação.

Se você quiser, eu também posso transformar isso em **rubrica de pontuação por item**, por exemplo $0{,}4$ ponto para cada subitem da questão 7.
    

---

# Gabarito resumido

**Q1:** C  
**Q2:** C  
**Q3:**

- (a) $$NPSH_{disp}=10{,}8-P_v$$
    
- (b) $$T_{max,\ sem\ cavitação}\approx 66^\circ\text{C}$$
    
- (c) $$T_{max,\ com\ folga\ de\ 2,m}\approx 41^\circ\text{C}$$
    
- (d) aumento de $Q$ aumenta $h_f$ e reduz $NPSH_{disp}$
    
- (e) $$h_f=1{,}95\ \text{m}$$, $$NPSH_{disp}(60^\circ\text{C})=8{,}35\ \text{m}$$, folga insuficiente  
    **Q4:** série soma head; paralelo soma vazão; ponto de operação pela interseção com curva do sistema  
    **Q5:** C  
    **Q6:** D  
    **Q7:** $$\Delta T_{ML}=50^\circ\text{C}$$  
    **Q8:** contracorrente mais eficiente; $ \Delta T_{ML} $ para dimensionamento com temperaturas conhecidas; $ \varepsilon\text{-}NTU $ para análise com área conhecida; incrustação reduz $U$; seleção envolve critérios térmicos, hidráulicos, econômicos e construtivos.
    

---

Se você quiser, eu posso agora transformar isso em um **gabarito em formato de correção do professor**, com distribuição de pontos por item e critérios para resposta parcial.