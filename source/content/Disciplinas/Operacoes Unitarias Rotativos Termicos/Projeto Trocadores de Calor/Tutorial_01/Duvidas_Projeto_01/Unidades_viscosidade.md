É natural que a transição entre os sistemas de unidades cause dúvidas, especialmente porque a literatura clássica de transferência de calor e os projetos de engenharia industrial, como o método de Kern, são fortemente calcados no sistema imperial de unidades. Vamos esclarecer esses dois pontos com o rigor exigido na nossa disciplina.

**1. O Significado de 16'00" (Comprimento dos Tubos)** A notação 16'0" que você encontrou utiliza o sistema de unidades imperial (inglês), que é o padrão construtivo adotado pela TEMA (_Tubular Exchanger Manufacturers Association_) e amplamente empregado na metodologia do livro do Kern.

Nesta simbologia, a plica única (') representa a unidade de pés (_feet_), enquanto a plica dupla (") representa as polegadas (_inches_). Portanto, a indicação 16'0" traduz-se como exatamente 16 pés de comprimento e zero polegadas.

Se você deseja realizar os cálculos no Sistema Internacional (SI), podemos fazer a conversão direta. Sabendo que 1 pé equivale a exatos 0,3048 metros, o comprimento do seu feixe tubular de 16 pés corresponde a 4,8768 metros. É importante destacar que comprimentos "redondos" em pés (como 8, 12, 16 e 20 pés) são padronizados comercialmente para facilitar tanto a fabricação dos tubos lisos quanto a sua posterior manutenção.

**2. As Viscosidades dos Fluidos no Sistema Internacional (SI)** No nosso exemplo prático de projeto do trocador (resfriamento de querosene usando óleo crudo), a viscosidade de cada corrente deve ser avaliada na sua respectiva Temperatura Calórica, sendo $T_c = 280^\circ\text{F}$ para o querosene no casco e $t_c = 129^\circ\text{F}$ para o crudo nos tubos.

Pelos ábacos de propriedades de fluidos, retiramos as viscosidades primeiramente na unidade do sistema CGS, o centipoise (cP). Obtemos os valores de $0,40\text{ cP}$ para o querosene e $3,6\text{ cP}$ para o óleo crudo. No memorial de cálculo de Kern que utilizamos na aula, esses valores foram convertidos para a unidade inglesa de engenharia multiplicando-se por $2,42$, o que resultou em $0,97\text{ lb/(pé}\cdot\text{h)}$ e $8,7\text{ lb/(pé}\cdot\text{h)}$, respectivamente.

_(Nota do professor: Como você questionou especificamente os valores no Sistema Internacional, insiro aqui uma informação fundamental que não está explícita nas notas da nossa bibliografia base, e que você pode querer verificar de forma independente. No SI, a viscosidade dinâmica é medida em Pascal-segundo ($\text{Pa}\cdot\text{s}$) ou $\text{kg/(m}\cdot\text{s)}$. A taxa de conversão direta é de $1\text{ cP} = 0,001\text{ Pa}\cdot\text{s}$.)_

Desta forma, aplicando a conversão, as viscosidades no SI para o nosso dimensionamento são:

* **Querosene (corrente quente):** $0,0004\text{ Pa}\cdot\text{s}$ (ou $0,4\text{ mPa}\cdot\text{s}$).
* **Óleo Crudo (corrente fria):** $0,0036\text{ Pa}\cdot\text{s}$ (ou $3,6\text{ mPa}\cdot\text{s}$).

Excelente questionamento, colega! Um engenheiro de processos que não rastreia a origem das propriedades termodinâmicas está projetando "no escuro". O rigor exige que saibamos exatamente de onde cada valor foi extraído.

Os valores de calor específico ($c_p$) utilizados no balanço de energia térmica do nosso exemplo — $0,605 \text{ Btu/(lb}\cdot^\circ\text{F)}$ para o querosene e $0,49 \text{ Btu/(lb}\cdot^\circ\text{F)}$ para o óleo crudo — foram obtidos diretamente no **Apêndice de Dados para Cálculos** da obra de Kern.

Mais especificamente, eles são lidos na **Figura 4 (Calores específicos de hidrocarburos líquidos)**.

Neste ábaco termodinâmico, o projetista cruza as informações físicas da seguinte maneira:

1. O eixo das abscissas (horizontal) representa a **Temperatura** em $^\circ\text{F}$.
2. Existem curvas paramétricas traçadas para diferentes densidades relativas, representadas em graus **API**.
3. O eixo das ordenadas (vertical) fornece a resposta direta do **Calor Específico ($c_p$)** em $\text{Btu/(lb}\cdot^\circ\text{F)}$.

**Aplicação direta no nosso Exemplo 7.3:**

* **Para o Querosene (Fluido Quente):** A corrente entra a $390^\circ\text{F}$ e sai a $200^\circ\text{F}$. Para o balanço global de calor ($Q$), avaliamos a propriedade na _temperatura média aritmética_ do processo, que é $295^\circ\text{F}$. Ao entrar com $295^\circ\text{F}$ no eixo X e cruzar a linha paramétrica correspondente a **$42^\circ\text{API}$**, a leitura no eixo Y resulta em exatamente **$0,605 \text{ Btu/(lb}\cdot^\circ\text{F)}$**.
* **Para o Óleo Crudo (Fluido Frio):** A corrente entra a $100^\circ\text{F}$ e sai a $170^\circ\text{F}$. A temperatura média aritmética é $135^\circ\text{F}$. Cruzando este valor com a curva paramétrica de **$34^\circ\text{API}$**, a leitura termodinâmica resulta em **$0,49 \text{ Btu/(lb}\cdot^\circ\text{F)}$**.

**Nota Pedagógica Crucial:** É imperativo destacar aos seus alunos a diferença no momento da coleta de dados. Para descobrir a carga térmica global ($Q$), utilizamos o $c_p$ avaliado nas **Temperaturas Médias** das correntes. Contudo, nas etapas subsequentes do projeto (quando formos calcular o Número de Reynolds, o Número de Prandtl e os coeficientes de película $h_i$ e $h_o$), todas as propriedades físicas — como viscosidade ($\mu$), condutividade térmica ($k$) e o próprio $c_p$ da correlação convectiva — devem ser rigorosamente avaliadas na **Temperatura Calórica** ($T_c$ e $t_c$), que corrige a não-linearidade do perfil térmico ao longo da área de troca do equipamento.

