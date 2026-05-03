O gráfico principal da Figura 17 **não** utiliza o grau API em suas curvas. A leitura correta exige que você utilize o gráfico menor (o inserto no canto superior esquerdo) _antes_ de ir para o gráfico principal.

A Figura 17 foi construída por Colburn para resolver o problema iterativo das temperaturas calóricas em frações de petróleo, permitindo encontrar o coeficiente de variação das resistências ($K_c$) sem precisar calcular os coeficientes globais nos terminais ($U_1$ e $U_2$).

Aqui está o rigoroso passo a passo da leitura, respondendo às suas dúvidas e aplicando ao nosso Exemplo 7.3:

### PASSO 1: O uso do gráfico menor (Inserto de $K_c$)

Aquele pequeno gráfico no canto superior esquerdo serve exclusivamente para encontrar o valor numérico do parâmetro $K_c$. Você deve fazer essa leitura para **ambos os fluidos** separadamente:

1. No eixo vertical esquerdo do gráfico menor, você entra com a **Gravedad API** do fluido.
2. Você traça uma linha horizontal até interceptar a curva paramétrica que representa o **Rango de temperatura** ($\Delta T$, que é a diferença entre a temperatura de entrada e saída daquela corrente específica).
3. Desse ponto de interceptação, você desce uma linha vertical até o eixo horizontal (inferior) do próprio gráfico menor. O valor lido ali é o seu **$K_c$**.

**A Regra de Controle Termodinâmico:** Após ler o $K_c$ para o fluido quente e o $K_c$ para o fluido frio, a termodinâmica determina que o processo é governado pela corrente que sofre a maior variação de propriedades. Portanto, o engenheiro deve selecionar o **maior valor de $K_c$** entre os dois. Esse fluido é chamado de "corrente controladora".

### PASSO 2: A leitura do gráfico principal (Obtenção de $F_c$)

Agora sim você vai para o painel principal da Figura 17:

1. No eixo horizontal (abscissa), você entra com a razão das forças motrizes terminais: $\frac{\Delta t_c}{\Delta t_h}$.
2. Você sobe uma linha vertical até interceptar a curva paramétrica que corresponde ao valor de **$K_c$** que você acabou de eleger como controlador no Passo 1. (Observe que as curvas do gráfico principal são marcadas como $K_c = 0.1, 0.2, 0.5, 1.0$, etc.).
3. Desse ponto, você traça uma linha horizontal para a esquerda e lê no eixo vertical (ordenada) a sua **Fração Calórica ($F_c$)**.

***

### PASSO 3: Aplicação no Exemplo 7.3

No projeto de resfriamento do Querosene com Óleo Crudo, Kern aplicou exatamente essa metodologia. Acompanhe os números:

**1. Avaliação dos Terminais:**

* $\Delta t_h = 390 - 170 = 220^\circ\text{F}$.
* $\Delta t_c = 200 - 100 = 100^\circ\text{F}$.
* Razão = $\frac{100}{220} = \mathbf{0,455}$.

**2. Uso do Gráfico Menor (Encontrando $K_c$):**

* _Para a Kerosena (Casco):_ Entra-se com $42^\circ\text{API}$ no eixo vertical e cruza-se com a curva de $\Delta T = 190^\circ\text{F}$ ($390 - 200$).
* _Para o Óleo Crudo (Tubos):_ Entra-se com $34^\circ\text{API}$ e cruza-se com a curva de $\Delta T = 70^\circ\text{F}$ ($170 - 100$).
* _Decisão:_ Kern fez essa leitura e constatou que o crudo é a corrente controladora (possui a mudança de viscosidade mais drástica). A leitura no eixo horizontal do gráfico menor resultou no valor de **$K_c = 0,20$**.

**3. Uso do Gráfico Principal (Encontrando $F_c$):**

* Entramos no eixo horizontal inferior com o valor de $0,455$.
* Subimos a linha vertical até encostar na curva paramétrica correspondente a $K_c = 0,20$.
* Lemos no eixo vertical à esquerda o valor de **$F_c = 0,42$**.

Com esse fator extraído de forma elegante dos ábacos, Kern pôde calcular as temperaturas definitivas de projeto sem realizar iterações numéricas complexas:

* $T_c$ (Querosene) $= 200 + 0,42 \cdot (190) = \mathbf{280^\circ\text{F}}$.
* $t_c$ (Crudo) $= 100 + 0,42 \cdot (70) = \mathbf{129^\circ\text{F}}$.

Ficou clara a função independente do gráfico menor e como ele fornece o parâmetro curvo que você deve caçar no gráfico principal?
