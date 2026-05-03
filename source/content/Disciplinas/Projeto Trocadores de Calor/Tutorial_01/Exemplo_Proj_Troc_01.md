Como engenheiros, sabemos que a teoria só ganha vida quando sujamos as mãos com os números. Para consolidar a nossa metodologia de Kern, guiarei você por um exemplo prático clássico da indústria do petróleo, detalhando cada cálculo passo a passo.

Vamos dimensionar as condições térmicas de um trocador de calor casco e tubos para resfriar querosene utilizando óleo cru, com base nos rigorosos parâmetros do **Exemplo 7.3 do livro do Kern**.

***

### 🎓 **EXEMPLO PRÁTICO: Resfriador de Querosene com Óleo cru**

**Dados de Processo:**

Um sistema de recuperação de calor em uma refinaria requer o resfriamento de uma corrente de querosene utilizando óleo cru. Verifique se o trocador de calor casco e tubos especificado abaixo é capaz de suprir o serviço térmico exigido, mantendo um fator de incrustação de segurança mínimo e sem ultrapassar os limites de perda de carga das bombas.

**1. Condições Termodinâmicas e de Processo:**

* **Fluido Quente (Lado do Casco):** Querosene a 42° API.

  * Vazão mássica: $43.800 \text{ lb/h}$.
  * Temperatura de entrada: $390^\circ\text{F}$.
  * Temperatura de saída: $200^\circ\text{F}$.

* **Fluido Frio (Lado dos Tubos):** Óleo cru a 34° API.

  * Vazão mássica: $149.000 \text{ lb/h}$.
  * Temperatura de entrada (do tanque): $100^\circ\text{F}$.
  * Temperatura de saída: $170^\circ\text{F}$.

**2. Restrições de Projeto (Critérios de Aceite):**

* **Queda de pressão máxima permitida ($\Delta P$):** $10 \text{ psi}$ para ambas as correntes.
* **Fator de obstrução global mínimo exigido ($R_d$):** $0,003 \text{ (h}\cdot\text{ft}^2\cdot^\circ\text{F)/Btu}$.

**3. Dados Construtivos do Trocador Disponível (Padrão TEMA):**

* **Arranjo de Passes:** Trocador tipo 1-4 (1 passe no casco e 4 passes nos tubos).

* **Casco (Shell):** Diâmetro interno ($DI_c$) de **$21 \frac{1}{4} \text{ polegadas}$** ($21,25 \text{ in}$).

* **Chicanas (Baffles):** Defletores segmentados com corte de 25%, espaçados a cada **$5 \text{ polegadas}$** ($B = 5 \text{ in}$).

* **Feixe Tubular:**

  * Número total de tubos ($N_t$): **$158 \text{ tubos}$**.
  * Diâmetro externo ($DE_t$): **$1 \text{ polegada}$**.
  * Espessura da parede metálica: **$13 \text{ BWG}$** (resultando em um Diâmetro Interno de $0,810 \text{ in}$).
  * Comprimento do feixe ($L_t$): **$16 \text{ pés}$** ($16'0''$).

* **Arranjo Espacial dos Tubos:** Passo quadrado (_square pitch_) de **$1 \frac{1}{4} \text{ polegadas}$** ($P_T = 1,25 \text{ in}$).

* Observação sobre unidades: 16’0” [[Unidades_viscosidade|Unidades e viscosidade]]

***

**Nota Pedagógica para a sua aula:** Ao fornecer esses dados construtivos completos, o raciocínio metodológico fica muito mais claro para o aluno. A missão deles deixará de ser _descobrir_ a área do trocador e passará a ser a verdadeira atribuição do engenheiro de processos operacionais: calcular os coeficientes de película $h_i$ e $h_o$ com base nas velocidades reais dessa geometria imposta, combinar no coeficiente limpo $U_c$ e provar termodinamicamente se $R_{d, calc} \ge 0,003$, validando por fim o atrito gerado contra o teto de $10 \text{ psi}$.

***

#### **PASSO 1: Alocação dos Fluidos**

Pelas nossas regras práticas de projeto, o fluido com maior tendência a incrustar e maior viscosidade deve passar pelo interior dos tubos, facilitando a limpeza mecânica futura. Logo:

* **Tubos:** Óleo cru (Frio).
* **Casco:** Querosene (Quente).

#### **PASSO 2: Balanço de Energia Térmica**

Verificamos se a conservação de energia se sustenta. Utilizando os calores específicos ($C_p$) dos fluidos nas temperaturas médias.
Para a obtenção dos cps usamos o gráfico do Kern (página 911):
[![graficos-exemplo-7-3.jpg](https://i.postimg.cc/28YYrG28/graficos-exemplo-7-3.jpg)](https://postimg.cc/5jsTmwhZ)

![[Ex_7_3_Balanco_Energia]]
#### **PASSO 3: Diferença de Temperatura Média Logarítmica ($\Delta T_{ML}$) e Fator $F_T$**

Para um equipamento puramente em contracorrente, avaliamos os terminais:

* Diferença quente ($\Delta T_1$): $390^\circ\text{F} - 170^\circ\text{F} = 220^\circ\text{F}$.
* Diferença fria ($\Delta T_2$): $200^\circ\text{F} - 100^\circ\text{F} = 100^\circ\text{F}$.
* $\Delta T_{ML} = \frac{220 - 100}{\ln(220 / 100)} = 152,5^\circ\text{F}$.

Para o fator de correção $F_T$ usamos o seguinte cálculo: ![[Ex_7_3_Calc_F_T]]
Esse método é descrito no documento: [[Equacoes_Calculo_FT|Documento cálculo do F_T]]

- **Cálculo do $\Delta T_{ML}$: ![[Ex_7_3_Calc_DT_ML]]

#### **PASSO 4: Estimativa Inicial do Trocador**

As propriedades físicas dos fluidos (viscosidade, densidade, etc.) não devem ser tomadas nos extremos, mas sim na **Temperatura Calórica** ($T_c$ e $t_c$), que reflete a temperatura efetiva da troca de calor ao longo da área.
Como foi calculada a temperatura calórica?
![[calculo_Tc_03]]
Versão complementar: [[calculo_Tc_01|Cálculo de Temperatura Calórica versão 01]]
[[calculo_Tc_02|Cálculo de Temperatura Calórica versão 02 otimizada]]

* Querosene ($T_c$) $= 280^\circ\text{F}$.
* cru ($t_c$) $= 129^\circ\text{F}$.

O projetista agora assume um Coeficiente Global Sujo ($U_D$) da literatura (Quadro 8 de Kern) para orgânicos médios/pesados e estipula uma geometria inicial usando as tabelas TEMA (Quadros 9 e 10).
[[Localizacao_Quadro_8_9_10#Localização quadros 8 a 10|Localizacao_Quadro_8 a 10]]
[[Localizacao_Quadro_8_9_10#Leitura do gráfico 9 e 10|Leitura do gráfico 9 e 10]]

#### **PASSO 5: Dimensionamento Térmico do Lado dos Tubos (Óleo cru)**

Para os tubos que escolhemos, calculamos a velocidade mássica ($G_t = \dot{m}/A_t$) e o Reynolds. Inserindo as propriedades do óleo cru nas correlações convectivas do lado dos tubos, obtemos o coeficiente de película interno limpo. Para poder somar as resistências na mesma base de área (área externa do tubo), o coeficiente é corrigido ($h_{io} = h_i \cdot \frac{DI_t}{DE_t}$).
![[Equacao_de_h|Cálculo do coeficiente de película]]

* No nosso caso de engenharia, o cálculo iterativo atinge: $h_{io} = 135 \text{ Btu/(h}\cdot\text{ft}^2\cdot^\circ\text{F)}$.

#### **PASSO 6: Dimensionamento Térmico do Lado do Casco (Querosene)**

O lado do casco sofre influência direta do espaçamento das chicanas ($B$) que nós definimos. A velocidade do querosene cruzando o feixe tubular dita o Reynolds do casco. Utilizando as propriedades calóricas do querosene:

* Coeficiente de película externo inicial: $h_o = 169 \text{ Btu/(h}\cdot\text{ft}^2\cdot^\circ\text{F)}$.
* ![[calculo_ho_casco|Cálculo do h_o do casco]]

**Cuidado de Ouro:** Observem a genialidade da mecânica dos fluidos! Precisamos avaliar a temperatura da parede metálica ($t_w$) para corrigir o arrasto viscoso da camada limite colada no metal.

* $t_w = t_c + \frac{h_o}{h_{io} + h_o} (T_c - t_c) = 129 + \frac{169}{135 + 169} (280 - 129) = 221^\circ\text{F}$.

A razão das viscosidades do querosene na temperatura global e na parede fornece o fator $\phi = (\mu/\mu_w)^{0,14} = 0,96$.

* Coeficiente corrigido do casco: $h_{o, corr} = 169 \cdot 0,96 = 162 \text{ Btu/(h}\cdot\text{ft}^2\cdot^\circ\text{F)}$.

#### **PASSO 7: Avaliação do Critério de Aceite Térmico**

Temos os dois coeficientes. Calculamos a "pujança" real do equipamento limpo ($U_c$) desprezando a condução da parede fina:

* $U_c = \frac{h_{io} \cdot h_{o, corr}}{h_{io} + h_{o, corr}} = \frac{135 \cdot 162}{135 + 162} = 73,6 \text{ Btu/(h}\cdot\text{ft}^2\cdot^\circ\text{F)}$.

O coeficiente de projeto estipulado no PASSO 4 ($U_D$) ditou a área construída. Calculamos o fator de incrustação resistido pela nossa geometria:

* $R_{d, calc} = \frac{U_c - U_D}{U_c \cdot U_D}$.
* Se $R_{d, calc} \ge 0,003$ (que era a exigência inicial), o projeto **Térmico está APROVADO!**. Caso contrário, voltaríamos ao PASSO 4, adicionando tubos ou aumentando o casco.
* [[Recalculo_Termico_Kern_P7|Dicas para cálculo do passo 7]]

#### **PASSO 8: Verificação Hidráulica ($\Delta P$)**

O último teste é verificar se as bombas suportam empurrar os fluidos.

* Calculamos $\Delta P_{tubos}$ somando o atrito reto com as perdas nos cabeçotes de retorno ($\Delta P_{tampo}$).
* Calculamos $\Delta P_{casco}$ considerando os cruzamentos pelo feixe orientados pelas chicanas, através do diâmetro equivalente $D_e$.
* Ambos resultando menores que o limite de $10 \text{ psi}$ estipulado, o projeto está integralmente comissionado e pronto para a fabricação.
[[calculo_perdas_TC|Cálculo das perdas de carga]]
