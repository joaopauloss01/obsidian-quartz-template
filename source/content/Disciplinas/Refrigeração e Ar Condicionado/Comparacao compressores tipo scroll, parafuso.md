<img src="https://r2cdn.perplexity.ai/pplx-full-logo-primary-dark%402x.png" style="height:64px;margin-right:32px"/>

# Em relação aos compressores tipo scroll, parafuso e pistão

Gostaria de saber as vantagens e desvantagens de cada um na refrigeração e sobre os problemas que cada um possui na operação e na entrada de líquido, aquecimento. E pra fechar em relação a eficiência volumétrica, energética e relação de custo.
E finalizando, as aplicações mais usuais de cada um.

De forma bem sintética:

- Pistão (alternativo) é barato e robusto para pequenas/médias capacidades, mas ruidoso, menos eficiente e muito sensível à entrada de líquido. [^1][^2]
- Scroll é hoje o “cavalo de batalha” de splits e chillers pequenos: alta eficiência, pouco ruído, boa tolerância operacional, porém com faixa de capacidade individual mais limitada e custo maior que pistão. [^3][^4][^5]
- Parafuso domina aplicações médias/grandes e regime 24/7: excelente para capacidade elevada, boa eficiência (especialmente com inversor), custo inicial alto e dependente de um bom sistema de óleo. [^3][^1][^2][^6]

Abaixo detalho por tipo.

***

## Visão panorâmica comparativa

| Aspecto | Pistão (alternativo) | Scroll | Parafuso (screw) |
| :-- | :-- | :-- | :-- |
| Faixa típica de capacidade | Pequena a média (≈ até 50–60 kW por máquina) [^1] | Pequena a média (≈ até 50–80 kW por unidade) [^3][^5] | Média a grande (dezenas a centenas de kW por máquina) [^3][^1][^6] |
| Regime de operação | Intermitente; não gosta de ciclagem muito rápida [^1] | Bom em ciclagem frequente, ótimo com inversor [^5][^7] | Ideal para operação contínua 24/7 [^1][^2] |
| Eficiência volumétrica | Média, cai com relação de compressão alta [^1][^8] | Alta (pouco volume nocivo, sem reexpansão) [^3][^9] | Alta e relativamente estável na faixa de carga [^1][^8][^6] |
| Eficiência energética (COP) | Menor; perde bastante em carga parcial [^1][^8][^7] | Maior que pistão em HVAC comum [^5][^9][^7] | Alta, especialmente com inversor; muito boa sazonalmente [^1][^10][^11][^6] |
| Custo de aquisição | Mais baixo por kW em baixa capacidade [^1][^2] | Médio (mais caro que pistão, mais barato que screw em mesma faixa) [^4][^5] | Alto CAPEX, porém competitivo por TR em grandes sistemas [^1][^2][^6] |
| Custo de manutenção | Peças baratas, manutenção mais frequente [^1][^2] | Baixa manutenção, mas especializada [^5][^7] | Manutenção menos frequente, porém especializada e cara [^1][^2][^6] |
| Ruído / vibração | Alto ruído e vibração elevados [^1][^2] | Baixo ruído e vibração [^3][^4][^5] | Ruído moderado, vibração baixa para o porte [^3][^1][^2][^6] |
| Tolerância à entrada de líquido | Muito baixa (slugging destrói rápido) [^1][^12] | Melhor que pistão, mas ainda crítica em excesso [^3][^13] | Mais tolerante, mas excesso causa danos ao sistema de óleo/rolamentos [^3][^1][^13][^6] |
| Aplicações típicas | Geladeiras pequenas, freezers, câmara pequena, chillers pequenos antigos [^3][^1][^4][^5] | Splits, VRF pequeno, chillers compactos, câmaras de média temperatura [^3][^4][^5][^7] | Chillers de água gelada, racks grandes de supermercado, câmaras industriais, túnel de congelamento [^3][^1][^2][^6] |


***

## Compressores alternativos (pistão)

### Funcionamento e características gerais

O compressor alternativo utiliza pistão e biela acionados por virabrequim; a sucção ocorre na descida do pistão, e a compressão/descarga na subida, com válvulas de sucção e descarga tipo placa. [^3][^1] Ele pode ser hermético, semi-hermético ou aberto, dependendo do acoplamento motor–compressor. [^3][^1]

A eficiência volumétrica é limitada pelo volume nocivo (clearance) no topo do cilindro e pela reexpansão do gás retido entre um ciclo e outro, além de vazamentos pelas válvulas. [^1] Isso faz a VE cair à medida que a relação de compressão aumenta. [^1][^8]

### Vantagens na refrigeração

- Projeto maduro, robusto, com tecnologia amplamente dominada, inclusive em versões herméticas baratas para refrigeração doméstica e comercial leve. [^3][^1][^4]
- Capaz de trabalhar com uma ampla gama de refrigerantes, incluindo amônia em versões abertas e semi-herméticas. [^1]
- Excelente para sistemas de pequena capacidade, em que o custo inicial é determinante e o ciclo não é 24/7 pesado. [^1][^2]


### Desvantagens e problemas típicos

- Muitos componentes móveis (pistões, anéis, bielas, válvulas), resultando em maior desgaste, necessidade de manutenção periódica e perda gradual de capacidade. [^1][^2]
- Nível de ruído e vibração elevado: o movimento alternado e a descarga pulsante geram pulsação de pressão e ruído em linhas de sucção/descarga. [^1][^2]
- Desempenho ruim em carga parcial: a eficiência cai fortemente quando se descarregam cilindros ou se trabalha muito fora do ponto de projeto. [^1][^8]


### Entrada de líquido e aquecimento

- **Slugging de líquido:** é o mais sensível dos três tipos. A presença de líquido na sucção gera golpes hidrálicos que empenam placas de válvula, quebram bielas, pistões e cabeçotes. [^1][^12][^14]
- O risco aumenta em partidas a frio, ciclos de degelo, retorno de condensado por drenagem inadequada do evaporador e falta de superaquecimento na serpentina. [^1][^12]
- **Temperatura de descarga:** em altas relações de compressão, a temperatura de descarga é muito alta, podendo chegar a 150–200 °C, o que acelera a degradação do óleo e exige resfriamento do cabeçote em aplicações com amônia. [^1][^2][^7]

Por isso usa-se superaquecimento controlado na sucção, acumuladores de sucção em sistemas com grande desnível e separadores de óleo/líquido em baixas temperaturas. [^3][^1]

### Eficiência volumétrica, energética e custo

- **Eficiência volumétrica:** tipicamente em torno de 0,7–0,85 para relações de compressão moderadas; cai à medida que a relação de compressão e as perdas de pressão em sucção aumentam. [^1][^8][^9]
- **Eficiência energética:** em HVAC/refrigeração comercial, o COP de sistemas com alternativos é geralmente inferior a scroll e parafuso, especialmente em operação sazonal com muitas horas em carga parcial. [^1][^2][^5][^7]
- **Custo:**
    - CAPEX mais baixo por kW em sistemas pequenos; equipamentos e peças de reposição baratos. [^1][^2]
    - OPEX maior: rendimento pior e manutenção mais frequente tendem a aumentar custo ao longo da vida útil. [^1][^2][^15]


### Aplicações usuais

- Refrigeradores domésticos e freezers de baixa capacidade (herméticos alternativos ainda são muito usados). [^3][^1][^4]
- Câmaras frigoríficas pequenas, balcões comerciais, pequenos chillers antigos ou de baixo custo. [^3][^1]
- Sistemas industriais com amônia de pequeno porte podem adotar compressores alternativos abertos ou semi-herméticos quando há necessidade de alta pressão e flexibilidade de manutenção local. [^1]

***

## Compressores scroll

### Funcionamento e características gerais

O scroll é formado por duas espiras (caracóis) involutas: uma fixa e outra orbitante. [^3][^1] O movimento orbital da espira móvel cria cavidades de gás que se deslocam da periferia para o centro, com redução progressiva de volume e elevação de pressão até a descarga. [^3][^1][^5]

Não há válvulas de sucção/descarga e o volume nocivo é pequeno, o que reduz reexpansão e perdas internas e aumenta a eficiência volumétrica. [^3][^4][^9]

### Vantagens na refrigeração

- **Alta eficiência volumétrica e mecânica:** ausência de válvulas e redução de volume quase contínua dão VE elevada e boa eficiência global. [^3][^9][^16]
- **Baixo ruído e vibração:** o torque é muito suave; a compressão é quase contínua e a pulsação de pressão é pequena, resultando em baixo ruído, ideal para condicionadores de ar. [^3][^4][^5]
- **Elevado COP e bom desempenho em carga parcial:** scrolls modulares em chillers podem ser ligados/desligados em “steps” finos e, com inversor, modulam capacidade com boa eficiência sazonal. [^5][^9][^7]
- Menos peças móveis, o que se traduz em manutenção menos frequente e boa confiabilidade quando o sistema de óleo e o superaquecimento são bem controlados. [^3][^4][^7]


### Desvantagens e problemas típicos

- Custo de fabricação mais alto que pistões equivalentes (geometria de espira precisa e folgas apertadas). [^4][^5]
- Faixa de capacidade individual relativamente limitada; para grandes capacidades usa-se banco de vários scrolls ou parte-se para parafuso/centrífugo. [^3][^5][^6]
- Tolerância limitada à contaminação: partículas sólidas podem marcar as superfícies de contato das espiras, aumentando folgas e vazamento interno. [^3][^4]


### Entrada de líquido e aquecimento

- **Entrada de líquido:** a ausência de volume de compressão “fechado” com válvulas faz o scroll ser, em geral, mais tolerante que o pistão a pequenos arrastos de líquido, porém slugging severo ainda pode causar forças mecânicas elevadas e danos às espiras ou rolamentos, além de lavagem de óleo. [^3][^1][^13]
- É comum o uso de acumulador de sucção em sistemas com scroll justamente para proteger contra inundação em partidas, degelo e retorno de líquido por má drenagem do evaporador. [^3][^1]
- **Temperatura de descarga:** a compressão contínua e as menores perdas por atrito levam a temperaturas de descarga menores que em alternativos sob mesma relação de compressão, reduzindo risco de superaquecimento e degradação de óleo. [^7][^4]

Ainda assim, em aplicações de baixa temperatura com altas relações de compressão, pode ser necessário resfriamento adicional ou estágios múltiplos para manter a temperatura dentro dos limites do óleo e do motor. [^1][^7]

### Eficiência volumétrica, energética e custo

- **Eficiência volumétrica:** elevada, frequentemente próxima de 0,9 em condições favoráveis de sucção e descarga, devido a pequena folga e ausência de reexpansão significativa. [^3][^9][^16]
- **Eficiência energética:** COP normalmente superior ao de alternativos na mesma faixa de capacidade em HVAC e refrigeração comercial; o ciclo é menos penalizado por perdas internas. [^5][^9][^7]
- **Custo:**
    - CAPEX intermediário: mais caro que uma unidade de pistão equivalente, mas em geral mais barato que um parafuso com todos os sistemas auxiliares, na faixa de pequena/média capacidade. [^4][^5]
    - OPEX menor, dado o melhor rendimento e menor manutenção periódica (desde que a instalação seja bem executada). [^5][^7]


### Aplicações usuais

- Ar condicionado residencial e comercial leve: splits, multi-splits, VRF de menor porte e self-contained compactos. [^3][^4][^5][^7]
- Chillers de água gelada de pequeno e médio porte (tipicamente até algumas dezenas de TR por máquina), muitas vezes em bancos de 2–8 compressores. [^3][^1][^5]
- Refrigeração comercial de média temperatura (balcões, câmaras de resfriados, ilhas), muitas vezes em racks de compressores. [^3][^4][^6]

***

## Compressores de parafuso (screw)

### Funcionamento e características gerais

O compressor de parafuso possui dois rotores helicoidais engrenados (macho e fêmea) que, ao girarem, formam cavidades que se deslocam da sucção para a descarga com redução gradual de volume. [^3][^1][^2] O gás é comprimido de forma praticamente contínua, sem válvulas, com injeção de óleo para vedação, lubrificação e controle de temperatura. [^3][^1]

A relação volumétrica interna é determinada pela geometria dos rotores e pela posição da janela de descarga; controles como “slide valve” ou volume ratio variável ajustam essa relação às condições de operação. [^1][^11][^6]

### Vantagens na refrigeração

- **Capacidade elevada e operação contínua:** ideais para sistemas de médio e grande porte, com operação 24/7 (indústria, supermercados, data centers). [^3][^1][^2][^6]
- **Boa eficiência volumétrica em ampla faixa de operação** e menor queda de desempenho com a relação de compressão em comparação a compressores alternativos. [^1][^8][^6]
- **Excelente controle de capacidade:** via slide valve, bypass interno ou, mais moderno, inversor de frequência com controle de rotação e “variable volume ratio”, mantendo boa eficiência em carga parcial. [^1][^10][^11][^6]
- Ruído e vibração relativamente baixos considerando a alta capacidade, graças ao fluxo mais contínuo de gás. [^3][^1][^2]


### Desvantagens e problemas típicos

- CAPEX alto: rotor usinado com alta precisão, grande carcaça, sistema de óleo (separador, resfriador, filtros, válvulas). [^1][^2][^6]
- Manutenção exige equipe especializada; falhas em separador de óleo, válvulas deslizantes ou rolamentos têm custo elevado. [^1][^2][^6]
- Em versões com controle apenas por slide valve, a eficiência em carga muito baixa (por exemplo < 30% de carga) pode cair bastante, pois há recirculação interna de gás sem redução equivalente de potência; o uso de inversor minimiza esse problema. [^1][^11][^6]


### Entrada de líquido e aquecimento

- **Entrada de líquido:** o parafuso com injeção de óleo é, estruturalmente, mais tolerante a pequena fração de líquido do que um pistão, pois não há volume cilíndrico “fechado” por válvulas; o líquido tende a ser misturado ao óleo e transportado pelo fluxo. [^3][^1][^13]
- Entretanto, grande quantidade de líquido na sucção ou condensação interna excessiva pode sobrecarregar separadores de óleo, diluir o lubrificante e levar a falha de rolamentos e desgaste de rotores. [^1][^13][^6]
- **Temperatura interna:** a injeção de óleo e a natureza rotativa fazem a temperatura de operação típica do “air end” ficar bem abaixo da de compressores de pistão, usualmente na faixa de 80–100 °C em compressores de ar, com ordem de grandeza semelhante em refrigeração. [^2][^6] Isso reduz a severidade térmica sobre o óleo e a máquina, desde que o circuito de óleo seja bem dimensionado. [^1][^11]


### Eficiência volumétrica, energética e custo

- **Eficiência volumétrica:** alta para uma grande faixa de relações de compressão; não sofre com reexpansão em volume nocivo como os alternativos. [^1][^8][^6]
- **Eficiência energética:**
    - Em carga plena, screw é muito eficiente em chillers de média/grande capacidade e refrigeração industrial. [^1][^6]
    - Com inversor, o consumo em carga parcial cai de forma significativa em relação ao screw com apenas slide valve, gerando excelente eficiência sazonal. [^11][^10]
- **Custo:**
    - CAPEX alto, viável economicamente quando se dilui em grandes capacidades ou em sistemas onde a confiabilidade 24/7 é crítica. [^1][^2][^6]
    - OPEX competitivo: bom COP, longa vida útil e intervalos de manutenção mais espaçados, compensando o investimento inicial em muitas aplicações. [^1][^11][^6]


### Aplicações usuais

- Chillers de água gelada de médio e grande porte (climatização de edifícios, indústrias de processo, data centers). [^1][^10][^11][^6]
- Refrigeração industrial: túneis de congelamento, câmaras de grande porte, plantas frigoríficas com amônia ou HFC/HFO em capacidades elevadas. [^3][^1][^2]
- Racks de compressores para redes grandes de supermercados e centros de distribuição. [^3][^6]

***

## Síntese para escolha prática

Se você pensar em critérios de projeto:

- **Até algumas dezenas de kW, foco em baixo custo e simplicidade:** pistão ou scroll, sendo scroll preferível quando há interesse em eficiência, ruído baixo e operação moderna (split, VRF, chillers compactos). [^3][^1][^4][^5]
- **Faixa de pequena a média capacidade com forte ênfase em eficiência e conforto acústico (AC, bombas de calor):** scroll tende a ser a melhor escolha. [^3][^5][^7]
- **Capacidades médias/grandes, operação contínua, exigência de alta confiabilidade e boa modulação de carga:** screw é, em geral, o compromisso ótimo entre eficiência, robustez e flexibilidade. [^3][^1][^2][^6]
- **Suscetibilidade à entrada de líquido (da pior para a melhor):** pistão ≫ scroll > parafuso; ainda assim, em qualquer caso, projeto de linha de sucção, acumuladores, controle de superaquecimento e degelo são críticos para garantir vida longa ao compressor. [^3][^1][^13][^12]

Se quiser, posso montar um quadro de decisão quantitativo (por faixa de capacidade, regime de operação e nível de temperatura de evaporação) para orientar seleção de compressor em projetos de refrigeração comercial/industrial.
<span style="display:none">[^17][^18][^19][^20][^21]</span>

<div align="center">⁂</div>

[^1]: Apostila-Refrigeracao.pdf

[^2]: https://cryo-systems.com/the-difference-between-screw-compressor-and-reciprocating-compressor/

[^3]: livro-refrigeracao-castro.pdf

[^4]: https://www.nenwell.com/news/comparison-reciprocating-compressor-vs-scroll-compressor-pros-and-cons/

[^5]: https://www.smchillers.com/post/scroll-chiller-vs-reciprocating-chiller

[^6]: https://csgcompressors.com/utilizing-screw-compressors-in-chillers-a-technical-overview/

[^7]: https://sprsunheatpump.com/scroll-compressor-vs-reciprocating-compressor.html

[^8]: https://www.youtube.com/watch?v=tZ2snKgaq5Y

[^9]: http://www.hvacrschool.com/what-is-compressor-volumetric-efficiency/

[^10]: https://www.daikinmea.com/en_us/knowledge-center/importance-of-part-load-efficiency.html

[^11]: https://www.rehva.eu/fileadmin/hvac-dictio/01-2013/Improved_energy_efficiency_of_air_cooled_chillers.pdf

[^12]: https://iifiir.org/en/fridoc/liquid-slugging-in-reciprocating-compressor-143310

[^13]: https://www.scribd.com/document/370645150/Liquid-in-Compressofr-Suction

[^14]: https://pubs.aip.org/aip/pof/article/36/2/026104/3261961/Fault-mechanism-and-dynamic-two-phase-flow

[^15]: https://www.atlascopco.com/en-us/compressors/air-compressor-blog/reciprocating-and-rotary-compressor-difference

[^16]: https://docs.lib.purdue.edu/cgi/viewcontent.cgi?article=2175\&context=icec

[^17]: CalendrioAcadmicodeGraduao2026PresencialAtual1.pdf

[^18]: horario_2026_1.pdf

[^19]: f094_RAC-Assinado.pdf

[^20]: GRD-MAN-0085 Refrigeração e Ar Condicionado.docx

[^21]: https://www.frontiersin.org/journals/mechanical-engineering/articles/10.3389/fmech.2023.1226857/full

