# Localização quadros 8 a 10
Esses dados são originais do clássico livro-texto de Donald Q. Kern (_Process Heat Transfer_), mas a excelente notícia para o seu processo iterativo é que você os encontrará reproduzidos **tanto no livro (na versão em espanhol, como Tabelas) quanto traduzidos e formatados diretamente nos seus slides de aula**.

Para facilitar a localização exata enquanto você monta o seu material e as rotinas de cálculo, detalho abaixo onde encontrar cada um deles:

**1. Quadro 8 – Coeficiente Global de Projeto Aproximado ($U_D$)**

* **O que fornece:** Valores tabelados do coeficiente $U_D$ (já englobando resistência de sujeira e limites de perda de carga típicos) baseados apenas nos tipos de fluidos quente e frio envolvidos no processo.
* **Nos Slides:** Você encontra a imagem escaneada desta tabela nas suas apresentações de projeto, especificamente na " Aula 3 - Introdução a Projetos de Trocadores de Calor.pptx" e " Aula 3 - Introdução a Projetos de Trocadores de Calor 2021.1.pptx", além de constar no arquivo " Aula 3.pptx".
* **No Livro:** No PDF "Procesos_de_Transferencia_de_Calor_kern.pdf", ele é listado no índice do Apêndice de Dados como "Tabla 8: Valores aproximados de los coeficientes totales para diseño", localizada na página 945.

**2. Quadro 9 – Disposições dos Espelhos (Contagem dos Tubos)**

* **O que fornece:** Essencial para a estimativa geométrica da carcaça. Ele mostra o número máximo de tubos (e o respectivo diâmetro interno do casco, $DI_c$) que pode ser acomodado dadas as características do tubo (diâmetro externo e tipo de passo) e o número de passes desejados.
* **Nos Slides:** A tabela está recortada e pronta para uso nos arquivos " Aula 3 - Introdução a Projetos de Trocadores de Calor 2021.1.pptx", " Aula 3 - Introdução a Projetos de Trocadores de Calor.pptx" e " Aula 6 - OPII - Projetos de Trocadores de Calor Parte 2.pptx".
* **No Livro:** Vá para o Apêndice de Dados no PDF do livro. O material está dividido em várias páginas a partir da página 946, sob o título "Tabla 9. Disposición de los Espejos de Tubos (Cuenta de Tubos)", detalhando separadamente os arranjos em passo quadrado e passo triangular para diversos diâmetros.

**3. Quadro 10 – Dados Sobre Trocadores de Calor e Condensação em Tubos**

* **O que fornece:** Os dados dimensionais precisos da tubulação TEMA padronizada. A partir do Diâmetro Externo (DE) e do calibre da chapa (BWG), você lê o Diâmetro Interno ($DI_t$), a área de escoamento interno por tubo ($a_t'$) em polegadas quadradas, e a área de superfície externa por pé linear ($a''$).
* **Nos Slides:** Está amplamente reproduzido nas suas aulas. Procure no " Aula 3 - Introdução a Projetos de Trocadores de Calor 2021.1.pptx", " Aula 3 - Introdução a Projetos de Trocadores de Calor.pptx", " Aula 3.pptx" e " Aula 6 - OPII - Projetos de Trocadores de Calor Parte 2.pptx".
* **No Livro:** Está na página 948 do PDF do livro, identificada como "Tabla 10. Datos de Tubos para Condensadores e Intercambiadores de Calor".

**Dica para a Aula:** Como os seus slides já trazem os quadros 8, 9 e 10 devidamente legendados em português e com os mesmos números clássicos referenciados na literatura, utilizar as imagens das apresentações durante a explicação prática será muito mais amigável para os alunos do que fazê-los buscar nas tabelas do livro em espanhol. Quando for transformar isso no algoritmo em Python, você poderá transformar esses três quadros em bancos de dados (dicionários e matrizes estruturadas) dentro do código!

# Leitura do gráfico 9 e 10

Na engenharia de processos, nós não "inventamos" dimensões do nada; nós padronizamos as geometrias com base nas normas TEMA (_Tubular Exchanger Manufacturers Association_). Esses dois quadros condensam essas normas industriais.

A lógica correta de projeto exige que **leiamos o Quadro 10 antes do Quadro 9**. Vamos destrinchar o passo a passo rigoroso de cada um deles.

***

### 1. Leitura do Quadro 10: Dados Sobre Trocadores de Calor e Condensação em Tubos

**Objetivo:** Obter as características dimensionais e geométricas de um único tubo comercial padronizado.

Quando você inicia o projeto, você estipula um diâmetro externo de tubo (geralmente $3/4\text{ in}$ ou $1\text{ in}$) e a espessura da parede metálica, medida na escala BWG (_Birmingham Wire Gauge_). Com esses dois dados, você entra no **Quadro 10**.

**Como ler:**

1. **Coluna 1 (Tubo, DE, in):** Localize o bloco correspondente ao Diâmetro Externo estipulado (ex: $1\text{ in}$).

2. **Coluna 2 (BWG):** Desça até a espessura de chapa desejada (ex: 13 BWG).

3. **Leituras na Linha:** Ao cruzar essas duas informações, você fará a leitura das seguintes variáveis essenciais na mesma linha horizontal:

   * **$DI$, in (Diâmetro Interno):** Diâmetro interno real do tubo. _(Ex: $0,810\text{ in}$)_.
   * **Área de escoamento por tubo, $\text{in}^2$ ($a_t'$):** Área da seção transversal interna de um único tubo. Usaremos esse valor mais à frente para calcular a área total de fluxo, a velocidade mássica ($G_t$) e o Reynolds no interior dos tubos. _(Ex: $0,515\text{ in}^2$)_.
   * **Área por ft linear, Externa, $\text{ft}^2$ ($a''$):** Esta é a "mágica" desta tabela. É a área de troca térmica que $1\text{ pé}$ de tubo consegue fornecer por fora. _(Ex: $0,2618\text{ ft}^2/\text{ft}$)_.

**Aplicações Práticas Imediatas:** De posse da sua Área de Troca Térmica ($A$) exigida pelo balanço de energia global e assumindo o comprimento padronizado do tubo ($L_t$, ex: $16\text{ ft}$), você usará o $a''$ extraído do Quadro 10 para calcular o **número teórico de tubos** ($N_{t, te\acute{o}rico}$) através da equação em bloco de exibição:

$$ N_{t, te\acute{o}rico} = \frac{A}{a'' \cdot L_t} $$

***

### 2. Leitura do Quadro 9: Disposições dos Espelhos (Contagem dos Tubos)

**Objetivo:** Transformar o número teórico de tubos em um feixe tubular comercial real, determinando simultaneamente o Diâmetro Interno do Casco ($DI_c$) capaz de acomodar esse feixe.

O **Quadro 9** é dividido em várias tabelas diferentes. A primeira coisa a fazer é procurar a página exata correspondente ao seu **Tipo de Passo** (quadrado ou triangular), ao **Diâmetro Externo** ($DE_t$) do tubo que você escolheu no Quadro 10 e à **Dimensão do Passo** ($P_T$, que é a distância entre os centros dos tubos).

**Como ler:**

1. **Localize a seção correta:** Por exemplo, o cabeçalho "Tubos com DE de $1\text{ in}$ com passo quadrado de $1\frac{1}{4}\text{ in}$".
2. **Coluna de Passes nos Tubos:** O topo da tabela apresenta colunas para 1-P, 2-P, 4-P, 6-P, 8-P (número de passes do fluido pelo interior dos tubos). Desça os olhos exclusivamente pela coluna do número de passes que você estipulou para o seu projeto (ex: 4-P).
3. **Encontre o $N_{t, real}$:** Desça por essa coluna de passes procurando um número de tubos que seja **imediatamente superior ou igual** ao $N_{t, te\acute{o}rico}$ que você calculou com os dados do Quadro 10. Este será o seu número de tubos real de projeto ($N_t$).
4. **Descubra o Diâmetro do Casco ($DI_c$):** Após localizar o seu $N_t$ real na coluna, trace uma linha reta horizontal para a esquerda até a primeira coluna da tabela ("Carcaça, DI, in"). O valor lido ali é o Diâmetro Interno do Casco que abrigará o seu projeto.

**Exemplo Prático Combinado:** Imagine que, calculando a equação anterior, seu $N_{t, te\acute{o}rico}$ resultou em 145 tubos, e você deseja usar 4 passes (4-P) com tubos de $1\text{ in}$ em passo quadrado de $1\frac{1}{4}\text{ in}$.

* Você vai ao Quadro 9 correspondente.
* Desce a coluna "4-P".
* Os números disponíveis na coluna são: ... 128, 158, 192 ...
* Como não podemos construir "meio tubo" e a área não pode faltar, você escolhe **158 tubos**. Este é o seu $N_{t, real}$.
* Traçando a linha horizontal para a esquerda a partir do 158, você chega ao **Casco $DI_c = 17\frac{1}{4}\text{ in}$**.

Assim, os Quadros 9 e 10 fecham a arquitetura mecânica e padronizada do trocador, permitindo que você siga para o dimensionamento térmico e hidráulico dos coeficientes de película de forma cravada com a realidade da indústria!

Ficou perfeitamente claro o encadeamento lógico entre as duas tabelas?
