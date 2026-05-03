Bom dia! Montei uma proposta de **AV1 com 8 questões** para **2 horas**, equilibrando **múltipla escolha, resposta única e discursivas**, cobrindo exatamente os tópicos do arquivo **“Conteúdo da Av1”**: bombas, compressores e trocadores de calor. A seleção prioriza classificação, interpretação de curvas, NPSH/cavitação, operação de compressores e aplicação de $\Delta T_{ML}$ e $\varepsilon\text{-}NTU$, em linha com o conteúdo programático e com as apostilas/livros enviados.

Também preparei **3 gráficos** para usar diretamente na prova:  
[Gráfico 1 — Curva da bomba e curva do sistema](sandbox:/mnt/data/grafico_bomba_sistema.png)  
[Gráfico 2 — Mapa esquemático de compressor](sandbox:/mnt/data/mapa_compressor.png)  
[Gráfico 3 — Perfis de temperatura em trocador de calor](sandbox:/mnt/data/perfis_trocador.png)

---

# Avaliação AV1 — Operações Unitárias: Rotativos e Processos Térmicos

## Instruções ao aluno

Esta avaliação contém 8 questões. Leia atentamente os enunciados. Quando necessário, explicite hipóteses adotadas, unidades e raciocínio físico. Em questões discursivas, respostas sem justificativa poderão ter pontuação parcial reduzida.

---

## Questão 1 — Múltipla escolha

**Tema:** classificação e seleção de bombas  
**Suporte:** texto-base

Uma indústria alimentícia precisa bombear um fluido altamente viscoso, sensível ao cisalhamento e contendo pequenas partículas em suspensão. A vazão requerida é moderada, mas a operação exige boa regularidade e baixo dano ao produto.

Assinale a alternativa **mais adequada** quanto ao tipo de bomba a ser selecionado:

A) Bomba centrífuga radial de alta rotação, pois sua eficiência cresce com a viscosidade do fluido.  
B) Bomba axial, pois é a mais indicada para fluidos viscosos e altas pressões.  
C) Bomba rotativa de lóbulos, pois lida bem com fluidos viscosos e sensíveis ao cisalhamento.  
D) Bomba periférica, pois é ideal para suspensões viscosas com sólidos.  
E) Bomba centrífuga de múltiplos estágios, pois evita pulsação e sempre supera bombas de deslocamento positivo em fluidos viscosos.

**Texto de apoio para a prova:**  
Bombas dinâmicas transferem energia principalmente como energia cinética ao fluido, enquanto bombas de deslocamento positivo fornecem energia sob a forma de pressão. Bombas rotativas de lóbulos são recomendadas para fluidos viscosos e sensíveis ao cisalhamento.

---

## Questão 2 — Múltipla escolha

**Tema:** ponto de operação de bombas  
**Suporte:** gráfico

Utilize o gráfico:  
👉 [Curva da bomba e curva do sistema](sandbox:/mnt/data/grafico_bomba_sistema.png)

Considere que o sistema opera inicialmente no ponto de interseção entre as curvas mostradas.

Analise as seguintes modificações independentes:

---

### I. Fechamento parcial de uma válvula na linha de descarga

### II. Aumento da rugosidade interna da tubulação devido à incrustação

### III. Elevação do nível do reservatório de sucção

### IV. Aumento da temperatura do fluido bombeado (redução da viscosidade)

---

Assinale a alternativa correta:

A) Apenas I e II deslocam a curva do sistema para cima, reduzindo a vazão no ponto de operação.  
B) Apenas III altera a curva da bomba, deslocando o ponto de operação para maior vazão.  
C) I e II alteram a curva do sistema; III desloca a curva do sistema para baixo; IV altera a curva da bomba.  
D) Todas as modificações alteram exclusivamente a curva da bomba.  
E) Nenhuma das modificações altera o ponto de operação, apenas o rendimento da bomba.
---

## Questão 3 — NPSH, margem e operação ao longo do ano

A figura abaixo apresenta o comportamento do **NPSH disponível** em função da temperatura do fluido para um sistema de bombeamento operando em sucção.

Além disso, é indicado o valor constante de **$NPSH_{req}$ da bomba**.

---

## (a)

Com base no gráfico, determine:

- A faixa de temperatura em que a bomba opera **sem cavitação**
    
- A temperatura aproximada em que a cavitação se inicia
    

---

## (b)

Explique qualitativamente por que o aumento da temperatura leva à cavitação, mesmo sem alteração no sistema hidráulico.

---

## (c)

Considere agora as seguintes modificações independentes:

### I. Instalação de um medidor de vazão na linha de sucção

### II. Redução do nível do reservatório de sucção

### III. Aumento da rugosidade da tubulação (incrustação)

Para cada caso:

- O que acontece com a curva de **NPSH disponível** (sobe, desce ou não altera)?
    
- O sistema passa a cavitar em temperaturas maiores ou menores?
    

---

## (d)

Uma alternativa de projeto é reduzir a altura de sucção (aproximar a bomba do reservatório).

Explique:

- Como isso afeta o NPSH disponível
    
- Se essa solução amplia ou reduz a faixa segura de operação

---

## Questão 4 — Discursiva

**Tema:** bombas em série e em paralelo  
**Suporte:** prompt de figura

Explique, com base nas curvas características, a diferença entre **associação de bombas em série** e **associação de bombas em paralelo**. Em sua resposta, discuta:

1. qual grandeza é majoritariamente ampliada em cada arranjo;
    
2. como a curva resultante é construída;
    
3. em que tipo de problema de engenharia cada arranjo é mais indicado;
    
4. por que a simples soma algébrica de vazões e heads, sem considerar a curva do sistema, pode levar a erro.
    

**Prompt para gerar figura no Flow do Google:**  
“Diagrama técnico didático, fundo branco, estilo livro de engenharia química, mostrando à esquerda duas bombas centrífugas em série ligadas por tubulação com setas de escoamento e, à direita, duas bombas centrífugas em paralelo alimentando uma mesma linha de descarga. Inserir pequenos gráficos ao lado de cada arranjo: no caso em série, soma vertical de head para mesma vazão; no caso em paralelo, soma horizontal de vazão para mesmo head. Legendas em português: ‘Bombas em série’, ‘Bombas em paralelo’, ‘Curva resultante’, ‘Curva do sistema’, ‘Ponto de operação’.”

A formulação dessa questão está diretamente apoiada na abordagem da apostila sobre acoplamento de bombas, ponto de operação e curva do sistema.

---

## Questão 5 — Múltipla escolha

**Tema:** compressores, surge e stonewall  
**Suporte:** gráfico

Considere o mapa de compressor abaixo:  
**Anexo:** [Mapa esquemático de compressor](sandbox:/mnt/data/mapa_compressor.png)

Assinale a alternativa correta:

A) A região de surge ocorre em altas vazões, próxima ao stonewall.  
B) Stonewall corresponde à reversão periódica do escoamento e destruição imediata do compressor.  
C) Surge é uma condição de instabilidade associada à baixa vazão, podendo causar reversão de fluxo e fortes vibrações.  
D) Compressores centrífugos possuem faixa operacional mais ampla que bombas centrífugas e, por isso, surge raramente é relevante.  
E) Em compressores, a faixa entre surge e stonewall aumenta indefinidamente com o aumento da razão de pressão por estágio.

A teoria e a terminologia usadas aqui seguem o material sobre tipos de compressores, limites operacionais, surge e stonewall.

---

## Questão 6 — Discursiva

**Tema:** classificação e limitações operacionais de compressores  
**Suporte:** prompt de figura

Compare **compressores alternativos**, **centrífugos** e **axiais** quanto a:

- princípio de funcionamento;
    
- faixa típica de vazão e razão de pressão;
    
- sensibilidade a surge/choke;
    
- robustez operacional;
    
- aplicações industriais mais adequadas.
    

Ao final, indique qual tipo seria mais apropriado para:

a) alta vazão com baixa razão de pressão;  
b) baixa vazão com alta razão de pressão;  
c) vazão intermediária com necessidade de operação contínua em processo químico.

**Prompt para gerar figura no Flow do Google:**  
“Infográfico técnico comparativo em português, estilo universitário, fundo claro, três colunas intituladas ‘Compressor Alternativo’, ‘Compressor Centrífugo’ e ‘Compressor Axial’. Em cada coluna, mostrar corte esquemático simples do equipamento, setas de escoamento e caixas-resumo com ‘faixa de vazão’, ‘razão de pressão’, ‘eficiência’, ‘risco de surge’, ‘aplicações’. Visual limpo, didático, semelhante a material de engenharia mecânica/química.”

A questão está alinhada com a classificação dos compressores dinâmicos e alternativos, bem como com a faixa de operação e critérios de seleção apresentados nas fontes.

---

## Questão 7 — Resposta única

**Tema:** método da diferença de temperatura média logarítmica  
**Suporte:** mini-enunciado numérico

Em um trocador de calor em **contracorrente**, as temperaturas terminais são:

- fluido quente: $T_{h,e}=120^\circ\text{C}$ e $T_{h,s}=80^\circ\text{C}$
    
- fluido frio: $T_{c,e}=30^\circ\text{C}$ e $T_{c,s}=70^\circ\text{C}$
    

Calcule a diferença de temperatura média logarítmica, $ \Delta T_{ML} $.

**Resposta esperada:** valor numérico em $^\circ\text{C}$.

**Observação:** use  
$$  
\Delta T_{ML}=\frac{\Delta T_1-\Delta T_2}{\ln\left(\frac{\Delta T_1}{\Delta T_2}\right)}  
$$

A questão se apoia diretamente no desenvolvimento do método $ \Delta T_{ML} $ para análise de trocadores e no contraste entre escoamento paralelo e contracorrente.

---

## Questão 8 — Discursiva

**Tema:** interpretação física de trocadores e seleção entre $\Delta T_{ML}$ e $\varepsilon\text{-}NTU$  
**Suporte:** gráfico

Considere o gráfico:  
**Anexo:** [Perfis de temperatura em trocador de calor](sandbox:/mnt/data/perfis_trocador.png)

Responda, justificando fisicamente:

1. por que o escoamento em contracorrente tende a apresentar melhor desempenho térmico do que o escoamento paralelo;
    
2. em que situação de projeto é mais natural utilizar o método $\Delta T_{ML}$;
    
3. em que situação é mais adequado utilizar o método $\varepsilon\text{-}NTU$;
    
4. como o fator de incrustação afeta o coeficiente global de transferência de calor e a área necessária do equipamento;
    
5. cite ao menos **três critérios de seleção** de trocadores de calor em projeto industrial.
    

A estrutura desta questão segue o conteúdo da apostila sobre tipos de trocadores, fator de incrustação, método $ \Delta T_{ML} $, método $ \varepsilon\text{-}NTU $ e critérios de seleção.

---

# Gabarito resumido

**Q1.** C  
**Q2.** C  
**Q3.**  
$$  
NPSH_{disp}=10{,}3+2{,}0-1{,}2-0{,}3=10{,}8\ \text{m}  
$$  
Como $10{,}8 > 8{,}0$, a operação é segura quanto à cavitação, com margem de $2{,}8\ \text{m}$.  
**Q4.** Série: soma de heads para mesma vazão; paralelo: soma de vazões para mesmo head; sempre avaliar com a curva do sistema.  
**Q5.** C  
**Q6.**

- alternativo: baixa vazão, alta razão de pressão;
    
- centrífugo: vazão intermediária, operação contínua;
    
- axial: altíssima vazão, baixa razão de pressão.  
    **Q7.**  
    Para contracorrente:  
    $$  
    \Delta T_1 = T_{h,e}-T_{c,s}=120-70=50^\circ\text{C}  
    $$  
    $$  
    \Delta T_2 = T_{h,s}-T_{c,e}=80-30=50^\circ\text{C}  
    $$  
    Logo,  
    $$  
    \Delta T_{ML}=50^\circ\text{C}  
    $$  
    **Q8.** Espera-se discussão sobre maior uniformidade do gradiente térmico em contracorrente, uso de $ \Delta T_{ML} $ quando temperaturas terminais são conhecidas, uso de $ \varepsilon\text{-}NTU $ quando área e configuração são conhecidas mas temperaturas de saída não são, redução de $U$ pela incrustação e critérios de seleção como custo, perda de carga, materiais, tipo de fluido, pressão, manutenção e espaço.
    

---

# Distribuição sugerida de pontuação

Para fechar em 10,0 pontos:

- Q1: 1,0
    
- Q2: 1,0
    
- Q3: 1,25
    
- Q4: 1,75
    
- Q5: 1,0
    
- Q6: 1,75
    
- Q7: 1,25
    
- Q8: 2,0
    

---

# Observação didática

A prova ficou com perfil de **rigor elevado**, mas ainda viável em 2 horas, porque mistura:

- reconhecimento conceitual,
    
- leitura de gráficos,
    
- cálculo curto,
    
- e duas discursivas com profundidade.
    

Posso, no próximo passo, transformar isso em uma **versão final formatada como prova pronta para impressão**, com cabeçalho, espaço para respostas e folha de gabarito separada.