| **Disciplina:** Operações Unitárias Processos Térm. e Rot. | **Unidade do trabalho:** Unidade 01 |
| :--- | :--- |
| **Professor (a):** João Paulo Silva Santos | **Data:** 22/04/2026 |
| **Aluno (a):** ___________________________________________ | **Matrícula:** _________________ |
| **Valor total da avaliação: 10,0** pontos **.** | **Nota:** _______ |

**LEIA COM ATENÇÃO AS SEGUINTES INSTRUÇÕES**
Após receber a avaliação, se o aluno desistir de fazê-la não terá direito à segunda chamada.
Assim que receber a folha de questões, o aluno deve preencher o cabeçalho com seu nome completo. Também deve colocar seu nome completo na folha de respostas. Não é permitido utilizar outras folhas de papel além das fornecidas pelo professor, devidamente assinadas. Não é permitido rasgar as folhas.
A prova só poderá ser entregue ao professor após 30 (trinta) minutos do início da avaliação. Da mesma forma, só será permitida a entrada de alunos até 30 (trinta) minutos após o início da avaliação.
As soluções e respostas das questões devem ser feitas apenas no espaço indicado pelo professor. Rasuras nas questões de múltipla escolha anulam a questão.
A folha de questões deve ser devolvida com a folha de respostas.
A avaliação deve ser feita com caneta azul ou preta. Respostas a lápis não serão consideradas nas solicitações de recorreção.
Todas as questões discursivas devem conter todo desenvolvimento necessário para a resolução da questão e serão corrigidas levando em conta: coerência das ideias, capacidade de argumentação, de análise e síntese.
A avaliação é sem consulta e individual. Consultas a material escrito (caderno, apontamentos, livros, papéis etc.), equipamento eletrônico (agendas, arquivos em calculadora, celulares, notebooks, calculadoras gráficas, etc.) e/ou a colegas não são permitidas.
Os celularese equipamentos diversos de telefonia móvel ou eletrônicos, com ou sem acesso a internet,devem permanecer desligados e guardados dentro de bolsas ou na mesa do professor.
Não é permitido utilizar estojos e colocar objetos no colo. As bolsas devem ser guardadas embaixo da carteira. O aluno deve ter em mãos apenas o material necessário (lápis, caneta, borracha).
Caso o aluno seja flagrado portando qualquer aparelho eletrônico, ou descumprindo as regras estabelecidas, sua avaliação será recolhida e atribuída nota zero.

***

### 💡 Nota Pedagógica do Professor:
Colega, observe que as instruções padrão deste *template* institucional foram claramente redigidas para uma **prova teórica presencial e sem consulta** (proibindo rigorosamente o uso de equipamentos eletrônicos, notebooks e materiais escritos). 

Como o nosso trabalho de dimensionamento da bomba exige o uso de catálogos de fabricantes, equacionamento iterativo (como a equação de Colebrook) e a programação da curva do sistema em **Python** (como discutimos anteriormente), essas regras entram em contradição direta com a natureza prática e computacional da avaliação. 

Recomendo fortemente que você mantenha o **cabeçalho oficial** (a tabela superior) para cumprir a burocracia institucional, mas substitua esse bloco de texto de "INSTRUÇÕES" por diretrizes focadas na entrega do projeto (ex: *permitido o uso do Google Colab, obrigatório anexar os recortes dos catálogos de bombas, o código Python deve estar comentado, etc.*). Isso evitará ambiguidades ou contestações por parte dos alunos!

### 📝 PROPOSTA DE TRABALHO PRÁTICO: Dimensionamento e Seleção de Sistema de Bombeamento

**1. Contextualização e Objetivo** O projeto de sistemas de tubulações exige que o engenheiro garanta o transporte do fluido fornecendo a vazão especificada de forma confiável e com o custo total mínimo. O objetivo deste trabalho é dimensionar as linhas de sucção e descarga de um sistema de bombeamento de água, calcular a perda de carga distribuída e localizada, levantar a curva do sistema e selecionar uma bomba centrífuga comercial adequada.

**2. Dados de Projeto**

- **Fluido:** Água a 20 °C ($\rho = 998 \text{ kg/m}^3$ e $\mu = 1,002 \times 10^{-3} \text{ kg/m}\cdot\text{s}$).
- **Vazão de Projeto ($Q$):** $50 \text{ m}^3/\text{h}$.
- **Material da Tubulação:** Aço carbono comercial Schedule 40 (rugosidade absoluta $\varepsilon = 0,045 \text{ mm}$).
- **Limites de Velocidade:**
    - Linha de Sucção: $1,0 \text{ m/s} \le V_s \le 1,5 \text{ m/s}$.
    - Linha de Descarga: $1,5 \text{ m/s} \le V_d \le 2,5 \text{ m/s}$.
- **Condição dos Reservatórios:** Tanques de sucção e descarga abertos para a atmosfera ($P_1 = P_2 = P_{atm}$).

**3. Descrição do Isométrico (Layout da Instalação)**

- **Tanque de Sucção (T-01):** Nível de operação da água em $z_1 = 2,0 \text{ m}$.
- **Linha de Sucção:**
    - A tubulação sai da lateral do tanque (entrada com arestas vivas, $K_L = 0,5$).[^1]
    - Trecho reto horizontal de $3,0 \text{ m}$.
    - 1 Válvula de gaveta totalmente aberta ($K_L = 0,2$).
    - 1 Curva chanfrada de 90° com aletas/suave ($K_L = 0,2$ a $0,3$).
    - Trecho reto de descida até o eixo da bomba em $z_{bomba} = 0,5 \text{ m}$, com comprimento de $1,5 \text{ m}$.
    - _Comprimento total linear da sucção ($L_s$):_ $4,5 \text{ m}$.
- **Linha de Descarga:**
    - A tubulação sai da bomba ($z_{bomba} = 0,5 \text{ m}$).
    - 1 Válvula de retenção tipo batente ($K_L = 2,0$).
    - 1 Válvula de globo totalmente aberta para controle ($K_L = 10,0$) (ou gaveta, a seu critério).
    - Trecho reto horizontal de $10 \text{ m}$.
    - 3 Cotovelos de 90° de raio longo/flangeado ($K_L = 0,3$ cada).
    - Trecho de elevação vertical de $20 \text{ m}$.
    - Trecho reto horizontal de $5,0 \text{ m}$ até a entrada no Tanque de Descarga (T-02).
    - Descarga livre (saída do tubo, $K_L = 1,06$ ou $\alpha$) no nível $z_2 = 20,5 \text{ m}$.
    - _Comprimento total linear da descarga ($L_d$):_ $35,0 \text{ m}$.

**4. Roteiro de Entregas do Aluno**

**Etapa 1: Especificação dos Diâmetros (Uso do Python)** Aplicando a equação da continuidade ($Q = V \cdot A$), os alunos devem escrever um _script_ em Python para iterar sobre um banco de dados (ou dicionário/lista) contendo os diâmetros internos nominais e reais de tubos padrão Schedule 40. O código deve retornar os diâmetros comerciais de sucção ($D_s$) e descarga ($D_d$) que respeitem rigorosamente as restrições de velocidade impostas.

**Etapa 2: Cálculo da Carga Manométrica do Sistema ($H_{sis}$)** Os alunos deverão calcular a perda de carga total ($h_L = h_{L, maior} + h_{L, menor}$) para a vazão de projeto. A equação de Bernoulli, para tanques abertos e sem turbinas, se reduz a: $H_{bomba, u} = (z_2 - z_1) + h_L$. _Rigor exigido:_ O fator de atrito $f$ no regime turbulento deve ser calculado iterativamente pela equação de Colebrook ou de forma explícita com alta precisão (ex: Equação de Swamee-Jain).

**Etapa 3: Levantamento da Curva do Sistema** Usando Python (bibliotecas como `numpy` e `matplotlib`), o aluno deverá gerar vetores de vazão variando de $0$ até $1,5 \times Q_{projeto}$ e plotar a curva $H_{sis} \times Q$. Este gráfico é chamado de curva do sistema (ou de demanda) e reflete como as perdas aumentam quadraticamente com a vazão.

**Etapa 4: Seleção em Catálogo de Fabricante** O aluno buscará em um catálogo industrial real (KSB, Sulzer, Imbil, etc.) uma família de bombas centrífugas e selecionará um modelo cujo rotor atenda ao ponto $(Q_{projeto}, H_{sis, projeto})$. O aluno deve anexar o recorte do catálogo justificando a seleção.

**Etapa 5: Determinação do Ponto de Operação Real** A bomba selecionada fornecerá um ponto operacional que é exatamente a interseção entre a curva característica do equipamento (fornecida no catálogo) e a curva do sistema calculada. O aluno deverá extrair de 4 a 5 pontos da curva do catálogo, realizar uma regressão polinomial em Python, sobrepor com a curva do sistema e encontrar analiticamente o ponto exato de operação (Vazão e Head reais), reportando também o rendimento neste ponto.


---

### 💡 Dicas Pedagógicas para a Avaliação

1. **Rigor com a perda localizada:** Avalie se eles contabilizaram que as perdas localizadas na sucção ocorrem com a energia cinética da sucção ($V_s^2/2g$), enquanto as da descarga ocorrem com a velocidade da descarga ($V_d^2/2g$).
2. **Uso do Software:** A exigência do Python é brilhante. Você pode exigir que eles entreguem o arquivo `.ipynb` (Jupyter Notebook). Isso evita que copiem planilhas de semestres anteriores e força a lógica de programação, construindo funções como `def colebrook(Re, ed):`.
3. **Diâmetros Diferentes:** Como a velocidade de sucção exigida é menor que a de descarga, obrigatoriamente eles encontrarão um $D_s > D_d$. Isso é regra clássica de projeto para mitigar problemas de cavitação e reduzir o NPSH requerido na sucção.

Esta estrutura de projeto não deixa margem para "achismos" e força os estudantes a pensarem não como meros calculistas, mas como Projetistas de Processos.
