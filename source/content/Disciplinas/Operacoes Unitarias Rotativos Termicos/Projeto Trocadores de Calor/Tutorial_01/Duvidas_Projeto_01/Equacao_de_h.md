Para o dimensionamento térmico do lado dos tubos (escoamento interno em regime turbulento), a correlação fundamental exigida no projeto e consolidada no Método de Kern é a **Correlação de Sieder e Tate**. Ela consiste em uma evolução da clássica equação de Dittus-Boelter, sendo estritamente necessária para fluidos reais com alta variação de viscosidade sob gradientes de temperatura (como cortes de petróleo, óleos ou xaropes), pois corrige a distorção do perfil hidrodinâmico na camada limite colada à parede metálica.

A correlação matemática exata utilizada para obter o coeficiente de película interno limpo ($h_i$) é:

$$ \frac{h_i D_{it}}{k} = 0,027 Re_t^{0,8} \left( \frac{c_p \mu}{k} \right)^{1/3} \left( \frac{\mu}{\mu_w} \right)^{0,14} $$

Nesta modelagem termodinâmica, os termos adimensionais representam:

* $\frac{h_i D_{it}}{k}$: Número de Nusselt ($Nu_D$) para o escoamento interno.
* $Re_t = \frac{D_{it} G_t}{\mu}$: Número de Reynolds, avaliando o grau de turbulência no tubo a partir da velocidade mássica ($G_t$).
* $Pr = \frac{c_p \mu}{k}$: Número de Prandtl, que relaciona a difusividade de momento com a difusividade térmica.
* $\left( \frac{\mu}{\mu_w} \right)^{0,14}$: Fator de correção de viscosidade (frequentemente denotado por $\phi_t$), onde $\mu$ é a viscosidade dinâmica do fluido avaliada na temperatura calórica global da corrente, e $\mu_w$ é a viscosidade dinâmica da fina camada limite avaliada na temperatura da parede do tubo ($t_w$).

Após o cálculo de $h_i$, aplicamos uma correção geométrica obrigatória. Para que possamos somar todas as resistências térmicas em uma base comum (a área externa do tubo), o coeficiente interno é transposto para o diâmetro externo ($DE_t$) por meio da relação de áreas:

$$ h_{io} = h_i \left( \frac{D_{it}}{DE_t} \right) $$

**Onde você encontra essas equações detalhadas no nosso material:**

1. **No Livro de Transferência de Calor do Kern (PDF):**

   * No arquivo " Procesos_de_Transferencia_de_Calor_kern.pdf", essa correlação de Sieder e Tate é deduzida e justificada na **página 127** (como uma extensão da Equação 3.26).
   * A discussão sobre o uso em projeto e o equacionamento em regime laminar ou turbulento prossegue na **página 133**.
   * _Nota operacional:_ Kern também fornece o atalho de resolução gráfica para essa mesma equação computacional por meio do uso da **Figura 24**, no apêndice de ábacos do livro.

2. **Nos Slides das Aulas:**

   * A equação é a espinha dorsal dos nossos cálculos em sala e está exposta textualmente nos blocos intitulados "Coeficiente de Película / Interior dos tubos (AGR)". Você a encontrará nos arquivos:

     * " Aula 3 - Introdução a Projetos de Trocadores de Calor 2021.1.pptx".
     * " Aula 3 - Introdução a Projetos de Trocadores de Calor.pptx".
     * " Aula 3.pptx".
     * " Aula 6 - OPII - Projetos de Trocadores de Calor Parte 2.pptx".

3. **No Livro do Incropera:**

   * No arquivo de apoio " incropera_escoamento_interno_TC.pdf", que rege a fenomenologia do escoamento interno, esta correlação é referenciada formalmente na **Equação 8.61** da Seção 8.5. O autor enfatiza que as propriedades devem ser estimadas na temperatura média do fluido, exceto $\mu_w$ ($\mu_s$ na notação dele), avaliada na superfície.
