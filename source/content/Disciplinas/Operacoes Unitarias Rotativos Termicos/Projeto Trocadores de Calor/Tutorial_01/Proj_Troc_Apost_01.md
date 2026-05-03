**APOSTILA COMPLETA: METODOLOGIA DE PROJETO DE TROCADORES DE CALOR CASCO E TUBOS (MÉTODO DE KERN)**

O projeto de um trocador de calor casco e tubos é essencialmente um processo iterativo. O engenheiro deve estimar as dimensões iniciais do equipamento e, em seguida, avaliar o desempenho térmico (se a área atende à troca térmica requerida) e o desempenho hidráulico (se a perda de carga gerada é aceitável para as bombas do sistema).

Abaixo, detalho rigorosamente cada etapa desse dimensionamento.

***

### **PASSO 1: Alocação dos Fluidos e Fator de Obstrução ($R_d$)**

Antes de iniciar os cálculos, deve-se decidir qual fluido escoará pelo interior dos tubos e qual escoará pelo casco. Por regra de projeto, deve-se alocar para a passagem nos tubos: o fluido mais corrosivo, fluidos que operam a maiores pressões, o fluido mais sujo, fluidos sob maiores temperaturas, ou a água de resfriamento (que é inerentemente suja e propensa a causar incrustações severas).

Também se deve estabelecer o coeficiente de depósito (sujeira) esperado ($R_d$). O acúmulo de sujeira penaliza a troca térmica, sendo um parâmetro tabelado (ex: vapor d'água = $0,0001 \text{ h.m}^2\text{.}^\circ\text{C/kcal}$; gases = $0,0002$; água de resfriamento = $0,0004$; pentenos = $0,0010$).

***

### **PASSO 2: Balanço de Energia Térmica**

A carga térmica ($Q$) transferida no equipamento é calculada pela conservação de energia, assumindo que todo o calor liberado pelo fluido quente é absorvido pelo fluido frio: $Q = \dot{m}_h \cdot C_{p,h} \cdot \Delta T_h = \dot{m}_c \cdot C_{p,c} \cdot \Delta T_c$

Onde:

* $\dot{m}$: Vazão mássica de projeto.
* $C_p$: Calor específico do fluido avaliado na temperatura calórica.
* $\Delta T$: Variação de temperatura de cada corrente (entrada - saída).

***

### **PASSO 3: Diferença de Temperatura Média Logarítmica ($\Delta T_{ML}$) e Fator $F_T$**

A força motriz para a transferência de calor em contracorrente puro é a $\Delta T_{ML}$, dada por: $\Delta T_{ML} = \frac{\Delta T_1 - \Delta T_2}{\ln(\Delta T_1 / \Delta T_2)}$ Onde $\Delta T_1 = T_{1} - t_{2}$ e $\Delta T_2 = T_{2} - t_{1}$. Letras maiúsculas ($T$) referem-se ao fluido quente e minúsculas ($t$) ao fluido frio.

Como os trocadores industriais costumam ter múltiplos passes nos tubos (ilustrados em arranjos lidos nas Figuras dos limites físicos \`\`), o escoamento é misto (correntes cruzadas e paralelas). Por isso, corrige-se a $\Delta T_{ML}$ com um fator geométrico $F_T$: $\Delta T_{projeto} = \Delta T_{ML} \cdot F_T$

O fator $F_T$ é calculado pelas relações de eficiência térmica $R = (T_1 - T_2) / (t_2 - t_1)$ e de efetividade $S = (t_2 - t_1) / (T_1 - t_1)$, podendo ser obtido por equações literais ou retirado das cartas do livro do Kern. O critério de projeto é implacável: o fator $F_T$ deve ser $\ge 0,85$ para evitar áreas de troca térmica ineficientemente gigantescas ou cruzamentos termodinâmicos inviáveis.

***

### **PASSO 4: Estimativa Inicial do Trocador (Geometria TEMA)**

Estima-se a área inicial assumindo um Coeficiente Global de Projeto ($U_d$) obtido do **Quadro 8 de Kern (Coeficiente global de projeto aproximado)**, mostrado nas imagens \`\`. $A = \frac{Q}{U_d \cdot \Delta T_{ML} \cdot F_T}$

Com a área estipulada (idealmente $3 \text{ m}^2 < A < 1000 \text{ m}^2$), escolhe-se o tipo construtivo baseado nas normas TEMA.

1. **Diâmetro e Espessura:** Seleciona-se o diâmetro externo dos tubos ($DE_t$) – usualmente 3/4" a 1" – e a espessura de parede da chapa em BWG.
2. **Comprimento:** Define-se comprimentos padrão de 8, 10, 12, 16 ou 20 ft ($L_t$).
3. **Tabela 10:** Vai-se ao **Quadro 10 de Kern** (\`\`) para retirar a área externa por pé linear ($a''$) e a área de escoamento interna por tubo ($a_t'$).
4. **Contagem de Tubos:** Calcula-se o número de tubos necessários: $N_t = A / (a'' \cdot L_t)$.
5. **Padronização do Casco:** De posse de $N_t$ e do número de passes estipulado, vai-se ao **Quadro 9 de Kern (Disposições dos espelhos)**, visto em \`\`, selecionando um trocador padrão comercial. Esta tabela informa o número de tubos real e determina o Diâmetro Interno do Casco ($DI_c$).

***

### **PASSO 5: Dimensionamento Térmico do Lado dos Tubos**

Nesta etapa, calculamos o coeficiente convectivo para o fluido interno ($h_i$).

1. **Área de fluxo total ($a_t$):** Divide-se a área total dos tubos pelo número de passes ($n$): $a_t = (N_t \cdot a_t') / (144 \cdot n)$ (o 144 converte in² para ft²).
2. **Velocidade Mássica ($G_t$):** $G_t = \dot{m} / a_t$.
3. **Número de Reynolds ($Re_t$):** $Re_t = (DI_t \cdot G_t) / \mu$, avaliado nas condições da temperatura calórica.
4. **Coeficiente de Película ($h_i$ e $h_{io}$):** Usamos a correlação analítica ou a **Figura 24 de Kern (Curva de transferência de calor lado dos tubos)** apresentada em \`\`. Pela correlação analítica: $\frac{h_i \cdot DI_t}{k} = 0,027 \cdot Re_t^{0,8} \cdot \left(\frac{c_p \cdot \mu}{k}\right)^{1/3} \cdot \left(\frac{\mu}{\mu_w}\right)^{0,14}$ Para unificar o balanço resistivo na área externa do tubo, corrigimos $h_i$ para as condições externas multiplicando pela razão dos diâmetros: $h_{io} = h_i \cdot (DI_t / DE_t)$.

***

### **PASSO 6: Dimensionamento Térmico do Lado do Casco**

As chicanas (baffles) orientam o fluxo transversal e geram forte turbulência.

1. **Arranjo dos Tubos:** Podem ter geometria em passo quadrado ou triangular, definindo a distância luz ($C'$) entre eles, conforme visualizado geometricamente nas figuras \`\`. $C' = P_T - DE_t$, onde $P_T$ é o passo (distância entre centros).
2. **Espaçamento das Chicanas ($B$):** O projeto determina um espaçamento que não deve ultrapassar restrições máximas (tabeladas de acordo com $DI_c$) para garantir que o feixe não flexione e a velocidade se mantenha elevada.
3. **Área de Escoamento Transversal ($A_c$):** $A_c = (DI_c \cdot C' \cdot B) / (144 \cdot P_T)$.
4. **Velocidade Mássica ($G_c$):** $G_c = \dot{m}_c / A_c$.
5. **Diâmetro Equivalente ($D_e$):** Devido à geometria irregular do casco preenchido, calcula-se $D_e$ ponderando o passo quadrado ou triangular. Exemplo para passo quadrado: $D_e = \frac{4 \cdot (P_T^2 - \pi \cdot DE_t^2 / 4)}{\pi \cdot DE_t}$.
6. **Número de Reynolds ($Re_c$):** $Re_c = (D_e \cdot G_c) / \mu$.
7. **Coeficiente de Película ($h_o$):** Obtido diretamente pela **Figura 28 de Kern (Curva para o lado da coraza com deflectores segmentados 25%)** em \`\` ou pela correlação: $\frac{h_o \cdot D_e}{k} = 0,36 \cdot Re_c^{0,55} \cdot \left(\frac{c_p \cdot \mu}{k}\right)^{1/3} \cdot \left(\frac{\mu}{\mu_w}\right)^{0,14}$.

***

### **PASSO 7: Avaliação do Projeto e Critério de Aceite Térmico**

Agora verificamos se o trocador estipulado limpo tem pujança suficiente para atender a condição operando sujo.

1. **Coeficiente Global Limpo ($U_c$):** Combina as resistências convectivas desprezando a condução no metal (que costuma ser finíssima): $U_c = \frac{h_{io} \cdot h_o}{h_{io} + h_o}$.
2. **Fator de Obstrução Global ($R_{d, calculado}$):** A diferença entre a resistência térmica calculada (limpo) e a de projeto exigida (sujo) resulta no fator de sujeira suportável pelo equipamento: $R_d = \frac{1}{U_d} - \frac{1}{U_c} = \frac{U_c - U_d}{U_c \cdot U_d}$.
3. **Aprovação Térmica:** É imperativo que $U_c > U_d$. Mais do que isso, $R_{d, calculado}$ deve ser maior ou igual ao fator de incrustação estipulado no PASSO 1 (margem entre 1,0 e 1,3). Caso reprovado, deve-se voltar ao passo 4, modificar os parâmetros (ex: aumentar o comprimento dos tubos ou assumir uma carcaça maior) e refazer o _loop_ numérico.

***

### **PASSO 8: Dimensionamento Hidráulico e Perda de Carga ($\Delta P$)**

Equipamentos com troca térmica formidável costumam gerar enorme atrito. Caso a queda de pressão limite as bombas, o projeto está mecanicamente reprovado. O limite típico exigido pela maioria das indústrias é de $\Delta P < 0,5 \text{ kgf/cm}^2$ (aprox. $10$ psi).

**8.1. Perda de Carga Lado dos Tubos ($\Delta P_t$):** Formada pelo atrito da parede ($\Delta P_{reto}$) e pelos retornos direcionais dos cabeçotes ($\Delta P_{retorno}$). $\Delta P_{tubos} = \Delta P_{reto} + \Delta P_{tampo}$ O cálculo do atrito contínuo é obtido pela clássica equação fenomenológica com o fator de atrito ($f$) tirado do gráfico de atrito de tubos (Figura 26 de Kern exibida em \`\`): $\Delta P_{reto} = \frac{f \cdot G_t^2 \cdot L \cdot n}{2 \cdot g \cdot \rho \cdot DI_t \cdot \phi_t}$ (Onde $\phi_t$ engloba a correção de viscosidade isotérmica na parede do tubo $(\mu / \mu_w)^{0,14}$).

**8.2. Perda de Carga Lado do Casco ($\Delta P_c$):** O fluido experimenta contração e expansão nas janelas das chicanas cruzando o feixe tubular sucessivas vezes. O número de vezes que o feixe é atravessado é dado por $(N+1) = 12 \cdot L / B$. A perda no casco é: $\Delta P_{casco} = \frac{f \cdot G_c^2 \cdot DI_c \cdot (N+1)}{2 \cdot g \cdot \rho \cdot D_e \cdot \phi_c}$ O fator de atrito $f$ para a geometria irregular do casco segmentado a 25% é obtido na **Figura 29 de Kern (Fatores de fricción lado de la coraza)** em \`\`.

_Se $\Delta P_c$ falhar:_ Aumente o espaçamento das chicanas ($B$), o que diminui o número de cruzes, aliviando o atrito ao custo de queda de coeficiente convectivo.

Com todos estes balanços hidráulicos validados abaixo do limiar estipulado e o perfil térmico confirmando o coeficiente global sujo $U_d$, o projeto se consagra aprovado pela rigorosa metodologia de Kern.
