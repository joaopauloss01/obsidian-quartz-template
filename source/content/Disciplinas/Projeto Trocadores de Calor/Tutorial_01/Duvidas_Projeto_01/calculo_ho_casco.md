O Passo 6 é onde a geometria intrincada do casco e das chicanas (baffles) entra em cena. Diferente do interior dos tubos, onde o fluido escoa de forma bem comportada e retilínea, o fluido no casco é forçado pelas chicanas a cruzar o feixe tubular transversalmente várias vezes. Isso gera uma turbulência fenomenal, mas exige um equacionamento geométrico muito criterioso.

Vou detalhar o rigor analítico desse passo, as equações governantes e como obtemos os dados.

### As Equações do Passo 6 e Onde Encontrá-las

Todo esse equacionamento está presente nos seus slides de aula (especificamente no arquivo onde é tratada a metodologia do casco) e no detalhamento do método de Kern.

**1. Área de Escoamento Transversal no Casco ($A_c$)** Diferente de um tubo vazio, o casco está cheio de tubos que bloqueiam o fluido. A área real por onde o fluido consegue passar no equador do trocador é calculada por: $$A_c = \frac{DI_c \cdot C' \cdot B}{144 \cdot P_T}$$ _Onde encontramos essas variáveis:_

* $DI_c$: Diâmetro Interno do Casco (obtido no Quadro 9 após você selecionar o número de tubos).
* $C'$: Distância "luz" entre os tubos. É simplesmente o passo menos o diâmetro do tubo ($C' = P_T - DE_t$).
* $B$: Espaçamento entre as chicanas. É um parâmetro de projeto adotado por você (limitado a valores máximos da norma TEMA, que também constam nos seus slides).
* $P_T$: O passo dos tubos (distância entre os centros). _(Nota: O fator 144 no denominador é o fator de conversão clássico do sistema imperial para transformar polegadas quadradas em pés quadrados)_.

**2. Velocidade Mássica no Casco ($G_c$)** Conhecendo a área estrangulada, calculamos o fluxo de massa por unidade de área: $$G_c = \frac{\dot{m}_c}{A_c}$$

**3. Diâmetro Equivalente ($D_e$)** Como o fluido escoa por fora de um feixe de tubos, não temos um diâmetro circular simples. O Método de Kern pondera a área de fluxo transversal pela área molhada. Para um arranjo com passo quadrado, a equação analítica deduzida é: $$D_e = \frac{4 \cdot \left( P_T^2 - \frac{\pi \cdot DE_t^2}{4} \right)}{\pi \cdot DE_t}$$

**4. Número de Reynolds do Casco ($Re_c$)** Com o diâmetro hidráulico equivalente, determinamos o regime de turbulência: $$Re_c = \frac{D_e \cdot G_c}{\mu}$$

### Como foi calculado o $h_o$ (Coeficiente de Película Externo)?

Para o lado do casco, Kern consolidou dados experimentais de escoamento cruzado sobre bancos de tubos com chicanas segmentadas em 25%. A correlação fenomenológica exigida na nossa disciplina para calcular o $h_o$ é:

$$\frac{h_o \cdot D_e}{k} = 0,36 \cdot Re_c^{0,55} \cdot \left(\frac{c_p \cdot \mu}{k}\right)^{1/3} \cdot \left(\frac{\mu}{\mu_w}\right)^{0,14}$$

Isolando o $h_o$, vemos que ele depende fortemente da condutividade térmica ($k$), do calor específico ($c_p$) e do número de Reynolds elevado a 0,55.

**Como Kern calculava isso na prática (A alternativa gráfica):** Na era pré-computador, para evitar a resolução da equação acima à mão, Kern fornecia o atalho através da **Figura 28 (Curva para o lado da coraza com deflectores segmentados 25%)**. O projetista entrava com o $Re_c$ no eixo X e lia diretamente um fator de transferência de calor ($j_H$) no eixo Y. Com esse fator, o cálculo se reduzia a uma álgebra simples, sem os expoentes quebrados. Hoje, com as linguagens de programação, nós programamos a equação exata citada acima e o computador faz o trabalho.

### Há tabelas para obter essas propriedades ou posso extraí-las de qualquer lugar?

Aqui está a regra de ouro de um projeto termodinâmico rastreável: você **pode** obter as propriedades de qualquer banco de dados confiável (como o simulador referenciado nos seus slides, softwares como CoolProp, Aspen HYSYS ou tabelas do Perry's Chemical Engineers' Handbook), **DESDE QUE** você as avalie na temperatura correta.

Nenhum dado termodinâmico pode ser retirado na temperatura de entrada ou de saída, eles devem ser rigorosamente calculados na **Temperatura Calórica ($T_c$)** para a viscosidade de massa ($\mu$), condutividade ($k$) e densidade ($\rho$). A única exceção é a viscosidade da parede ($\mu_w$), que deve ser extraída avaliando o fluido na temperatura calculada para a parede metálica do tubo ($t_w$).

**Onde Kern buscou os dele?** No livro clássico, Kern montou um "Apêndice de Dados" fantástico. Se você for usar estritamente o livro para que os alunos acompanhem os exemplos:

* A viscosidade dinâmica ($\mu$) dos líquidos é lida na **Figura 14**.
* Kern chegou a criar gráficos unificados para as propriedades de hidrocarbonetos. Na **Figura 16**, ele agrupa o termo $k(c_p/k)^{1/3}$, permitindo que você extraia o bloco termodinâmico inteiro de uma vez só apenas entrando com a temperatura e o grau API do óleo.

Portanto, como professor, instrua seus alunos: a geometria construtiva ($DI_c$, $DE_t$) é **obrigatória** sair dos **Quadros 9 e 10** da norma TEMA para garantir padronização mecânica. Já as propriedades físico-químicas ($\mu$, $k$, $c_p$) podem ser interpoladas de bancos de dados computacionais ou simuladores, o que até aumenta a precisão do projeto numérico em relação às antigas leituras dos gráficos do apêndice do Kern.


Parece que estamos mergulhando nos cálculos de **Transferência de Calor**, especificamente no lado do casco (shell side) de um trocador de calor. O cálculo do coeficiente de convecção externo ($h_o$) geralmente segue o **Método de Bell-Delaware** ou o **Método de Kern** (mais simples e comum em graduação).

Vou detalhar o caminho pelo **Método de Kern**, que é o padrão para determinar esse valor.

---

### 1. As Equações para $h_o$

O cálculo do $h_o$ não é direto; ele depende do regime de escoamento, que é definido pelo **Número de Nusselt ($Nu$)**. A sequência lógica é:

#### A. Diâmetro Equivalente ($D_e$)
Como o fluido corre por fora dos tubos, não usamos o diâmetro real, mas um equivalente baseado no arranjo dos tubos (quadrado ou triangular).
* **Arranjo Quadrado:** $D_e = \frac{4(P_t^2 - \pi d_o^2/4)}{\pi d_o}$
* **Arranjo Triangular:** $D_e = \frac{4(P_t^2 \sqrt{3}/4 - \pi d_o^2/8)}{\pi d_o / 2}$

#### B. Área de Fluxo do Casco ($A_s$)
Você precisa saber por quanto espaço o fluido passa:
$$A_s = \frac{D_i \cdot C \cdot B}{P_t}$$
*(Onde $D_i$ é o diâmetro interno do casco, $C$ é o aclaramento entre tubos, $B$ é o espaçamento das chicanas e $P_t$ é o passo dos tubos).*
[[C_aclaramento|Cálculo do aclaramento: C]]
#### C. Número de Reynolds do Casco ($Re_s$)
Calculamos a velocidade mássica ($G_s = \dot{m}/A_s$) e então:
$$Re_s = \frac{G_s \cdot D_e}{\mu}$$

#### D. A Equação Principal ($h_o$)
Para o regime turbulento, usamos frequentemente a correlação de **McAdams** ou a de **Kern**:
$$h_o = \frac{k}{D_e} \cdot 0.36 \cdot Re_s^{0.55} \cdot Pr^{1/3} \cdot \left(\frac{\mu}{\mu_w}\right)^{0.14}$$

---

### 2. Onde encontrar os dados? (Tabelas vs. Fontes Externas)

Você **não** deve pegar esses dados em "qualquer lugar", pois a precisão do cálculo depende da temperatura de referência.

#### Propriedades do Fluido (Viscosidade $\mu$, Condutividade $k$, Calor Específico $C_p$)
* **Temperatura de Filme:** Essas propriedades devem ser avaliadas na temperatura média do fluido no casco: $T_{avg} = \frac{T_{in} + T_{out}}{2}$.
* **Fontes:** Geralmente encontradas nos apêndices de livros como o **Incropera (Fundamentos de Transferência de Calor e Massa)** ou o **Kern (Process Heat Transfer)**. Se estiver usando um simulador ou software, ele puxa de bibliotecas como a DIPPR.

#### Dados Geométricos (Diâmetros e Espessuras)
* **Tabela BWG:** Para o diâmetro dos tubos e espessura da parede, você **precisa** da tabela *Birmingham Wire Gauge* (BWG). Ela define, por exemplo, que um tubo de $3/4"$ BWG 16 tem dimensões exatas diferentes de um tubo comum.



---

### 3. Resumo do que você precisa "caçar":

| Dado | Onde encontrar? |
| :--- | :--- |
| **$\mu, k, C_p, \rho$** | Tabelas de propriedades termofísicas (Ex: Apêndice A do Incropera). |
| **$d_o, d_i$ (Tubos)** | Tabela de tubos padrão **BWG**. |
| **$P_t, C, B$** | Dados de projeto (geralmente fornecidos no enunciado ou normas como TEMA). |
| **$\mu_w$** | Viscosidade do fluido calculada na temperatura da **parede** do tubo. |

**Dica crucial:** O termo $(\mu/\mu_w)^{0.14}$ é uma correção para a diferença de temperatura entre o "grosso" do fluido e a parede. Se você não tiver a temperatura da parede ainda, costuma-se assumir $1.0$ em uma primeira iteração e depois refinar.

