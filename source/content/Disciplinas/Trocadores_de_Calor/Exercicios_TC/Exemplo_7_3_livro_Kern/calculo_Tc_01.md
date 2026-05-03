Para calcular o Coeficiente Global de Transferência de Calor ($U$), precisamos das propriedades físicas dos fluidos (como a viscosidade). Para saber as propriedades exatas, precisamos da **Temperatura Calórica**. Mas, pela definição termodinâmica de Colburn, a temperatura calórica depende de $U_1$ e $U_2$!

Como resolvemos isso na etapa de estimativa? Vou destrinchar esse processo com o rigor que a nossa disciplina exige.

***

### 1. O que são $U_1$ e $U_2$ e em quais temperaturas ocorrem?

Em um trocador de calor, o fluido quente e o fluido frio entram e saem em extremidades opostas (assumindo a contracorrente). A viscosidade dos fluidos muda de uma ponta à outra, o que faz com que o coeficiente global $U$ não seja constante.

* **$U_1$ (Terminal Frio):** É o coeficiente global avaliado na extremidade onde ocorre a menor diferença de temperatura ($\Delta t_c$). É a ponta onde o fluido frio entra ($t_1$) e o quente sai ($T_2$).
* **$U_2$ (Terminal Quente):** É o coeficiente global avaliado na extremidade onde ocorre a maior diferença de temperatura ($\Delta t_h$). É a ponta onde o fluido quente entra ($T_1$) e o frio sai ($t_2$).

A variação entre esses dois coeficientes gera uma constante chamada $K_c = (U_2 - U_1) / U_1$.

### 2. Eu consigo calcular isso agora, antes de saber os coeficientes de película?

**Para hidrocarbonetos (cortes de petróleo): SIM!** E aqui entra a genialidade do método de Kern. Para evitar que o engenheiro tivesse que "chutar" um trocador inteiro, calcular os $h_i$ e $h_o$ nas pontas, achar $U_1$ e $U_2$, e só então descobrir a temperatura real para refazer tudo, Colburn e Kern criaram um atalho empírico.

Eles condensaram o comportamento de frações de petróleo em um pequeno gráfico anexo à [[leitura_figura_17_Kern|Figura 17]]. Neste gráfico, você não precisa de $U_1$ e $U_2$. Você entra apenas com o **Grau API** do fluido e a **Variação de Temperatura ($\Delta T$)** da corrente, e ele lhe dá o valor de $K_c$ diretamente!

**Para outros fluidos (não-petróleo): NÃO.** Se os fluidos não forem hidrocarbonetos, você teria que estimar $U_1$ e $U_2$ por tentativa e erro. No entanto, por regra prática de engenharia: se o fluido tiver viscosidade baixa (menor que $1,0\text{ cP}$, como água, álcoois ou gases), a variação de $U$ é quase linear. Nesse caso, ignoramos o cálculo calórico e usamos a simples **Média Aritmética** ($T_m = \frac{T_1 + T_2}{2}$), assumindo $F_c = 0,5$.

### 3. Como foram obtidas as temperaturas no Exemplo 7.3?

No Exemplo 7.3, estamos lidando com Querosene e Óleo Crudo, que são muito viscosos. Logo, a temperatura calórica é obrigatória. O passo a passo (referenciado na analogia do Exemplo 5.6 de Kern) foi o seguinte:

* **Passo A (Avaliar Terminais):**

  * Terminal Quente ($\Delta t_h$): $390^\circ\text{F} - 170^\circ\text{F} = 220^\circ\text{F}$.
  * Terminal Frio ($\Delta t_c$): $200^\circ\text{F} - 100^\circ\text{F} = 100^\circ\text{F}$.
  * Razão: $\Delta t_c / \Delta t_h = 100 / 220 = \mathbf{0,454}$.

* **Passo B (Encontrar $K_c$ controlador):**
  * Lê-se no inserto da Figura 17 o $K_c$ para o Querosene (42 API, resfriando $190^\circ\text{F}$) e para o Crudo (34 API, aquecendo $70^\circ\text{F}$). O fluido que apresentar o maior valor de $K_c$ é a corrente "controladora", e é este valor de $K_c$ que ditará o comportamento do trocador inteiro.

* **Passo C (Encontrar a Fração Calórica $F_c$):**
  * Com o $K_c$ da corrente controladora e a razão de $0,454$, cruza-se as linhas no gráfico principal da **Figura 17**. Para este caso, a leitura resulta em **$F_c \approx 0,42$**.
[![graficos-exemplo-7-3-Kc.jpg](https://i.postimg.cc/KYHYcWYj/graficos-exemplo-7-3-Kc.jpg)](https://postimg.cc/B823MMHf)

* **Passo D (Calcular as Temperaturas Calóricas):**

  * Querosene ($T_c$): $200 + 0,42 \cdot (390 - 200) = \mathbf{280^\circ\text{F}}$.
  * Crudo ($t_c$): $100 + 0,42 \cdot (170 - 100) = \mathbf{129^\circ\text{F}}$.

Essas serão as temperaturas imutáveis nas quais você avaliará a viscosidade ($\mu$), condutividade ($k$) e calor específico ($C_p$) para todos os cálculos de película do equipamento.

### 4. Onde estão essas Figuras 17 e 18?

Elas se encontram no **Apêndice do livro do Kern** (_Process Heat Transfer_ ou _Procesos de Transferencia de Calor_), geralmente localizadas nas últimas páginas da obra, na seção de "Cartas e Ábacos para Cálculo".

* **Figura 17:** Gráfico de "Temperaturas Calóricas" (traz a fração $F_c$ no eixo vertical e a razão das diferenças de temperatura no eixo horizontal, com o pequeno inserto para o $K_c$ de petróleos no canto).
* **Figura 18:** Gráfico do "Fator de Correção $F_T$" para trocadores de 1 passe no casco e múltiplos nos tubos (1-2, 1-4, etc).

### 5. Existe outro modo de obter além da figura? (O Método Analítico)

Sim, absolutamente. O gráfico é apenas a plotagem da dedução analítica de Colburn. Se você estiver programando isso em Python ou Excel para o seu projeto, e tiver paciência iterativa para calcular $U_1$ e $U_2$ exatos nos terminais, a Fração Calórica ($F_c$) pode ser calculada pela equação fenomenológica exata deduzida por ele:

$$F_c = \frac{\frac{1}{K_c} + \frac{R^*}{R^*-1}}{1 + \frac{\ln(K_c + 1)}{K_c}} - \frac{1}{\ln(R^*)}$$

_Onde:_

* $K_c = \frac{U_2 - U_1}{U_1}$
* $R^* = \frac{U_2 \cdot \Delta t_h}{U_1 \cdot \Delta t_c}$

Na era pré-computador, essa iteração era um pesadelo matemático, por isso o uso das figuras virou lei nos escritórios de engenharia. Hoje, com métodos numéricos, essa equação analítica é o padrão ouro para fluidos que não sejam derivados de petróleo.

