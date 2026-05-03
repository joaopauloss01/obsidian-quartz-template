| **Disciplina:** Operações Unitárias Processos Térm. e Rot. | **Unidade do trabalho:** Unidade 01 |
| :--- | :--- |
| **Professor (a):** João Paulo Silva Santos | **Data:** 22/04/2026 |
| **Aluno (a):** ___________________________________________ | **Matrícula:** _________________ |
| **Valor total da avaliação: 10,0** pontos **.** | **Nota:** _______ |

**INSTRUÇÕES NORMATIVAS PARA O TRABALHO (LEIA COM ATENÇÃO)**
1. **Prazo e Formato:** O aluno terá o prazo rigoroso de **1 (uma) semana** a partir da data de recebimento para a entrega deste projeto. A entrega deverá ser feita em formato digital (PDF para o relatório e anexos dos arquivos de cálculo).
2. **Autoria e Consulta:** Este é um trabalho estritamente **INDIVIDUAL**. É permitida (e incentivada) a consulta a livros-texto de mecânica dos fluidos, manuais de engenharia (Perry's, etc.), catálogos de fabricantes na internet e tabelas de tubulações. **É expressamente proibida a consulta ou o compartilhamento de arquivos com colegas.** Projetos que apresentarem planilhas, códigos ou memórias de cálculo idênticas receberão nota zero.
3. **Memória de Cálculo e Ferramentas:** O uso de linguagens de programação (como Python) ou planilhas eletrônicas (como Excel) é **opcional**, porém recomendado para a geração da curva do sistema. **Todas as equações governantes utilizadas devem ser explicitamente apresentadas no relatório.**
4. **Anexos Obrigatórios:** O aluno deverá obrigatoriamente anexar ao trabalho: (a) A memória de cálculo ou os arquivos gerados (planilhas/scripts); e (b) Os recortes (páginas) do catálogo comercial do fabricante mostrando as curvas da bomba escolhida e do NPSH requerido.

***

### 📝 PROJETO PRÁTICO: Dimensionamento e Seleção de Sistema de Bombeamento

**1. Contextualização e Objetivo**
Na engenharia de processos, garantir a confiabilidade operacional de uma linha de transporte de fluidos vai muito além de aplicar a equação de Bernoulli. O objetivo deste trabalho é atuar como um projetista sênior: você deverá dimensionar os diâmetros das linhas de sucção e descarga, calcular a curva do sistema (Head vs. Vazão), selecionar uma bomba centrífuga comercial adequada e, criticamente, garantir que o sistema está a salvo do fenômeno da cavitação através do cálculo do NPSH.

**2. Dados de Projeto e Propriedades**
*   **Fluido:** Água operando a 20 °C ($\rho = 998 \text{ kg/m}^3$, $\mu = 1,002 \times 10^{-3} \text{ kg/m}\cdot\text{s}$, e Pressão de Vapor $P_v = 2,34 \text{ kPa}$).
*   **Pressão Atmosférica Local:** $P_{atm} = 101,325 \text{ kPa}$.
*   **Vazão de Projeto de Demanda ($Q$):** $50 \text{ m}^3/\text{h}$.
*   **Material da Tubulação:** Aço carbono comercial Schedule 40 (rugosidade absoluta $\varepsilon = 0,045 \text{ mm}$).
*   **Limites de Velocidade (Critério de Projeto):** 
    *   Linha de Sucção: $1,0 \text{ m/s} \le V_s \le 1,5 \text{ m/s}$.
    *   Linha de Descarga: $1,5 \text{ m/s} \le V_d \le 2,5 \text{ m/s}$.
*   **Condição dos Reservatórios:** Tanques de sucção e descarga são abertos para a atmosfera ($P_1 = P_2 = P_{atm}$).

**3. Descrição do Isométrico da Instalação**
O layout físico do sistema de transferência é composto pelos seguintes elementos:
*   **Linha de Sucção:**
    *   Tanque de Sucção (T-01) com nível de operação da água em $z_1 = 2,0 \text{ m}$.
    *   O tubo sai pela lateral inferior do tanque (borda viva, $K_L = 0,5$).
    *   Trecho reto horizontal de $3,0 \text{ m}$.
    *   1 Válvula de gaveta totalmente aberta ($K_L = 0,2$).
    *   1 Curva chanfrada de 90° com aletas diretrizes ($K_L = 0,2$).
    *   Trecho reto de descida até o flange de sucção no eixo da bomba ($z_{bomba} = 0,5 \text{ m}$), com comprimento de $1,5 \text{ m}$.
    *   *Comprimento total linear da sucção ($L_s$):* $4,5 \text{ m}$.
*   **Linha de Descarga:**
    *   A tubulação sai do flange de descarga da bomba ($z_{bomba} = 0,5 \text{ m}$).
    *   1 Válvula de retenção tipo batente ($K_L = 2,0$).
    *   1 Válvula de globo para controle, operando totalmente aberta ($K_L = 10,0$).
    *   Trecho reto horizontal de $10,0 \text{ m}$.
    *   3 Cotovelos de 90° de raio longo flangeados ($K_L = 0,3$ cada).
    *   Trecho vertical de elevação com $20,0 \text{ m}$ de altura.
    *   Trecho reto horizontal de $5,0 \text{ m}$ com descarga livre no topo do Tanque de Descarga (T-02) no nível $z_2 = 20,5 \text{ m}$ (perda de saída, $K_L = 1,0$).
    *   *Comprimento total linear da descarga ($L_d$):* $35,0 \text{ m}$.

**4. Roteiro de Memorial de Cálculo e Entregas**

*   **Etapa 1: Especificação dos Diâmetros Comerciais**
    A partir da equação da continuidade, obtenha os diâmetros teóricos necessários para atender aos limites de velocidade estipulados. Consulte tabelas de tubulação Schedule 40 para definir os diâmetros internos comerciais definitivos para a sucção ($D_s$) e para a descarga ($D_d$). Especifique a velocidade real em cada linha.

*   **Etapa 2: Modelagem da Curva do Sistema ($H_{sis}$)**
    Apresente a equação geral da energia de Bernoulli modificada para fluidos reais. Mostre a formulação do cálculo do fator de atrito ($f$) e do somatório de perdas localizadas ($\sum K_L$). Desenvolva uma tabela ou gráfico plotando a Curva do Sistema ($H_{sis} \times Q$) para um intervalo de vazões variando de $0$ a $70 \text{ m}^3/\text{h}$. *(Opcional: utilize o software ou a planilha eletrônica de sua preferência para facilitar a iteração).*

*   **Etapa 3: Seleção Comercial e Ponto de Operação**
    Acesse catálogos de fabricantes reais de bombas centrífugas (ex: KSB, Sulzer, Imbil, Goulds). Selecione o modelo e o diâmetro do rotor que atenda com a melhor eficiência possível ao seu ponto de projeto ($Q = 50 \text{ m}^3/\text{h}$ na altura manométrica calculada). 
    *Análise cruzada:* Sobreponha a curva da bomba selecionada com a sua curva do sistema e determine graficamente ou analiticamente o **Ponto de Operação Real** (Vazão e Head reais que a bomba entregará). 

*   **Etapa 4: Análise de Cavitação (NPSH)**
    O fenômeno da cavitação (vaporização do líquido no olho do rotor seguida de colapso) destrói a máquina. Calcule o Net Positive Suction Head Disponível da sua instalação ($NPSH_{disp}$).
    Equação base: $NPSH_{disp} = \frac{P_1 - P_v}{\rho g} + (z_1 - z_{bomba}) - h_{L,suc}$.
    Leia no catálogo comercial da bomba selecionada qual é o NPSH Requerido ($NPSH_{req}$) no ponto de operação. Conclua tecnicamente e com justificativa: a sua bomba operará de forma segura contra a cavitação?
