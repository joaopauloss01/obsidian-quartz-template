Como professor da disciplina, é com satisfação que apresento o gabarito oficial e detalhado da nossa primeira avaliação (AV1). Este documento foi estruturado não apenas para fornecer as respostas corretas, mas para servir como um material de apoio pedagógico, contendo as justificativas termodinâmicas e referências diretas aos conceitos de engenharia que fundamentam cada questão.

Abaixo, detalho o gabarito analítico:

---

### **Gabarito Oficial - Avaliação 1 (AV1): Refrigeração e Ar Condicionado**

#### **QUESTÃO 01**

**Gabarito:** **D** **Justificativa Técnica:** Na engenharia de armazenamento, o resfriamento é caracterizado pela retirada de calor sensível de produtos mantidos em temperaturas ligeiramente acima de seus pontos de congelamento, enquanto o congelamento exige a remoção do calor latente de fusão. Paralelamente, na climatização voltada ao conforto humano, a segurança é inegociável, priorizando-se o uso de fluidos modernos que possuam ODP (Potencial de Destruição do Ozônio) igual a zero, além de baixa toxicidade e ininflamabilidade.

#### **QUESTÃO 02**

**Gabarito:** **E** **Justificativa Técnica:** A alternativa E é a incorreta (e, portanto, a resposta da questão). As misturas azeotrópicas (designadas pela série 500 da ASHRAE) comportam-se termodinamicamente como substâncias puras, ou seja, possuem temperatura de evaporação e condensação constantes para uma dada pressão, não apresentando o fenômeno do _glide_ (escorregamento de temperatura). A alta inflamabilidade citada na alternativa é uma restrição característica dos hidrocarbonetos puros (Série 600, como o isobutano).

#### **QUESTÃO 03**

**Gabarito:** O Coeficiente de Performance (COP) sofre uma **redução drástica**, enquanto o trabalho específico de compressão **aumenta severamente**. **Justificativa Técnica:** A diminuição da temperatura de evaporação ($T_e$) reduz a pressão de sucção, exigindo maior trabalho para atingir a pressão de descarga (aumento da relação de compressão), o que por si só já diminui o COP. O superaquecimento ocorrido fora do espaço refrigerado (sem resfriamento útil) não contribui para a capacidade frigorífica do sistema, mas aumenta o volume específico do vapor aspirado pelo compressor. Consequentemente, o compressor admite uma menor massa de refrigerante a cada ciclo geométrico, reduzindo a capacidade total de refrigeração e elevando o consumo de potência no eixo.

#### **QUESTÃO 04**

**Gabarito:** **B** **Justificativa Técnica:** O _approach_ (aproximação) é o parâmetro fundamental que dita a eficiência de uma torre de resfriamento. Ele é definido como a diferença entre a temperatura da água resfriada na saída da bacia e a Temperatura de Bulbo Úmido (TBU) do ar atmosférico. A TBU representa o limite físico mínimo teórico ao qual a água pode ser resfriada pelo processo de evaporação na torre.

#### **QUESTÃO 05**

**Gabarito:** O compressor mecânico é substituído por um conjunto formado pelo **Absorvedor, Bomba e Gerador**. A principal diferença reside na força motriz: compressão a vapor consome **energia elétrica/mecânica**, enquanto a absorção consome **energia térmica (calor)**. **Justificativa Técnica:** No ciclo de absorção, o fluido refrigerante vaporizado é dissolvido em uma solução no absorvedor, pressurizado como líquido por uma pequena bomba de baixo consumo, e então separado novamente no gerador mediante a adição de calor. Assim, enquanto o ciclo de compressão convencional penaliza a matriz elétrica, o ciclo de absorção é movido a calor (ex: vapor de escape, rejeitos térmicos industriais), tornando-se uma solução eficiente para a recuperação energética.

#### **QUESTÃO 06**

**Gabarito:** **C** **Justificativa Técnica:** O compressor do tipo _Scroll_ realiza a compressão mecânica de forma contínua através do movimento orbital de uma espiral móvel contra uma espiral fixa. Como não depende de válvulas de palheta (admissão/descarga) passíveis de perdas de carga por estrangulamento e inércia como nos alternativos, ele atinge rendimentos volumétricos muito superiores, consolidando-se no mercado de expansão direta comercial e _Chillers_ de pequeno/médio porte.

#### **QUESTÃO 07**

**Gabarito:** A eficiência volumétrica de espaço nocivo cai drasticamente à medida que a relação de compressão ($P_d/P_s$) aumenta, pois o gás residual a alta pressão confinado no volume morto precisa se re-expandir até uma pressão inferior à de sucção para que a válvula de admissão se abra. **Justificativa Técnica:** O volume morto ($V_e$) é inerente ao projeto mecânico do compressor alternativo. O vapor retido nesse espaço no fim da descarga (sob pressão $P_d$) deve sofrer expansão no curso de descida do êmbolo até igualar a pressão da linha de sucção ($P_s$). Quando a relação $P_d/P_s$ é alta, a expansão desse gás residual ocupa uma grande fração do deslocamento do cilindro, roubando espaço do novo fluido que deveria ser aspirado, o que reduz severamente o volume efetivo bombeado pelo compressor.

#### **QUESTÃO 08**

**1. Extração de Dados da Tabela (R-32):** A partir das condições operacionais fornecidas (Superaquecimento e Sub-resfriamento de 5 K), o aluno deveria identificar corretamente os estados termodinâmicos consultando a tabela:

- **Ponto 1 (Sucção do Compressor):** $T_e = 5^\circ C + 5\text{ K (superaquecimento)} = 10^\circ C$.
    - _Linha 3 da tabela:_ $P = 9,51 \text{ bar}$; $h_1 = 522,425 \text{ kJ/kg}$; $v_1 = 0,03999 \text{ m}^3\text{/kg}$; $s_1 = 2,15878 \text{ kJ/kg}\cdot\text{K}$.
- **Ponto 3 e 4 (Saída do Condensador / Entrada do Evaporador):** $T_c = 45^\circ C - 5\text{ K (sub-resfriamento)} = 40^\circ C$.
    - _Linha 4 da tabela:_ $P = 27,94 \text{ bar}$; $h_3 = 275,281 \text{ kJ/kg}$. Como a expansão é isoentálpica, $h_4 = h_3 = 275,281 \text{ kJ/kg}$.
- **Ponto 2 (Descarga Ideal do Compressor):** A compressão teórica é isentrópica ($s_2 = s_1 = 2,15878 \text{ kJ/kg}\cdot\text{K}$).
    - _Linha 5 da tabela:_ Em $P = 27,94 \text{ bar}$ e $s = 2,15878$, temos $h_2 = 567,102 \text{ kJ/kg}$ (temperatura de $80,26^\circ C$).

---

**A) Cálculo da Vazão Mássica ($\dot{m}_f$) e COP**

- **Conversão da Carga Térmica ($Q_e$):** Sabe-se que $1 \text{ TR} = 12.000 \text{ BTU/h} = 3,52 \text{ kW}$. $Q_e = 32.000 \text{ BTU/h} \times \left( \frac{3,52 \text{ kW}}{12.000 \text{ BTU/h}} \right) = \mathbf{9,3867 \text{ kW}}$ (ou kJ/s).
- **Efeito Refrigerante (ER):** $ER = h_1 - h_4 = 522,425 - 275,281 = \mathbf{247,144 \text{ kJ/kg}}$.
- **Vazão Mássica ($\dot{m}_f$):** $\dot{m}_f = \frac{Q_e}{ER} = \frac{9,3867}{247,144} = \mathbf{0,0380 \text{ kg/s}}$ (aproximadamente $0,03798 \text{ kg/s}$).
- **Coeficiente de Performance (COP):** O trabalho de compressão específico é $\Delta h_c = h_2 - h_1 = 567,102 - 522,425 = \mathbf{44,677 \text{ kJ/kg}}$. $COP = \frac{ER}{\Delta h_c} = \frac{247,144}{44,677} = \mathbf{5,53}$.

---

**B) Potência do Compressor ($\dot{W}_c$)** Considerando a potência termodinâmica baseada na compressão isentrópica (já que o problema não fornece eficiência mecânica ou isentrópica extra): $\dot{W}_c = \dot{m}_f \times \Delta h_c$ $\dot{W}_c = 0,03798 \text{ kg/s} \times 44,677 \text{ kJ/kg} = \mathbf{1,697 \text{ kW}}$ (Aproximadamente $1,70 \text{ kW}$).

---

**C) Projeto do Compressor Alternativo ($N_c$, $D$, $L$)**

- **Vazão Volumétrica Real Admitida ($V_{real}$):** $V_{real} = \dot{m}_f \times v_1 = 0,03798 \text{ kg/s} \times 0,03999 \text{ m}^3\text{/kg} = \mathbf{0,001519 \text{ m}^3\text{/s}}$.
    
- **Deslocamento Volumétrico Teórico Exigido ($V_z$):** Considerando a eficiência volumétrica ($\eta_{vr}$) de 85% fornecida: $V_z = \frac{V_{real}}{\eta_{vr}} = \frac{0,001519}{0,85} = \mathbf{0,001787 \text{ m}^3\text{/s}}$.
    
- **Dimensionamento Mecânico (Cinemática):** A equação de deslocamento para compressores é: $V_z = \left( \frac{\pi \cdot D^2}{4} \right) \cdot L \cdot N_c \cdot \left( \frac{N}{60} \right)$ Como prática de engenharia de projeto, se o aluno adotar um bloco de geometria perfeitamente "quadrada" ($L = D$) e converter a rotação de 2000 RPM para Hz ($2000/60 = 33,33 \text{ Hz}$): $0,001787 = \frac{\pi \cdot D^3}{4} \cdot N_c \cdot 33,33$ $0,001787 = D^3 \cdot N_c \cdot 26,18$ $D^3 \cdot N_c = \mathbf{0,00006825 \text{ m}^3}$
    
    **Critério de Correção para as Escolhas do Aluno:** O aluno deve definir o número de cilindros ($N_c$) e encontrar as dimensões:
    
    - **Se $N_c = 2$ (Bicilíndrico):** $D^3 = 0,000034125 \rightarrow D = 0,0324 \text{ m}$. Resposta: **$D = 32,4 \text{ mm}$ e $L = 32,4 \text{ mm}$**.
    - **Se $N_c = 4$ (Tetracilíndrico):** $D^3 = 0,00001706 \rightarrow D = 0,0257 \text{ m}$. Resposta: **$D = 25,7 \text{ mm}$ e $L = 25,7 \text{ mm}$**.
    - **Se $N_c = 1$ (Monocilíndrico):** $D^3 = 0,00006825 \rightarrow D = 0,0408 \text{ m}$. Resposta: **$D = 40,8 \text{ mm}$ e $L = 40,8 \text{ mm}$**.

---

**Critérios de Correção (Dica Pedagógica):** Recomenda-se conferir pontuação integral para qualquer uma das definições de $N_c$ (1, 2 ou 4 cilindros), desde que o aluno tenha deduzido o balanço termodinâmico na Tabela 1 e aplicado a eficiência volumétrica no divisor do cálculo de deslocamento.

#### **QUESTÃO 09**

**Gabarito:** Os arranjos construtivos mais utilizados são os Condensadores tipo Casco e Tubo (_Shell and Tube_), Tubo em Tubo (_Tube-in-tube_) e a Placas Brasadas. A diferença termodinâmica principal sob picos de calor é que a condensação a água oferece pressões de descarga mais baixas e estáveis. **Justificativa Técnica:** Um condensador resfriado a ar é influenciado diretamente pela temperatura de bulbo seco externa, que sobe drasticamente nas tardes de verão, forçando a elevação indesejada da pressão de condensação para que o gradiente térmico de rejeição seja mantido. Os condensadores a água dependem das torres de resfriamento, cuja performance é pautada na Temperatura de Bulbo Úmido (TBU). A TBU é inerentemente menor e mais estável que o bulbo seco ao longo do dia, assegurando pressões de descarga controladas, o que otimiza o COP e protege os mancais mecânicos do compressor contra altas razões de compressão.

#### **QUESTÃO 10**

**Gabarito e Elementos Exigidos no Esboço:** O aluno deve traçar a curva de saturação no diagrama Pressão ($P$) vs. Entalpia ($h$) e indicar:

1. **Compressão (1 -> 2):** Linha subindo no sentido das isoentrópicas (em direção à direita) da pressão de evaporação ($P_s$) até a pressão de condensação ($P_c$) na região de vapor superaquecido.
2. **Condensação com Sub-resfriamento (2 -> 3):** Linha horizontal isobárica ($P_c$) partindo da região superaquecida, cruzando a cúpula de mistura bifásica em temperatura constante, e adentrando a região de líquido sub-resfriado à esquerda da curva de líquido saturado.
3. **Expansão (3 -> 4):** Linha vertical isentálpica (constante em $h$) descendo da alta para a baixa pressão, entrando na região de vapor úmido (mistura líquido-vapor).
4. **Evaporação com Superaquecimento (4 -> 1):** Linha horizontal ($P_s$) cruzando a cúpula de volta para a direita, extraindo o calor latente, transpassando a linha de vapor saturado seco e sofrendo elevação de temperatura na região de vapor superaquecido até atingir a sucção do compressor no ponto 1.

---

_Espero que este material guie perfeitamente a correção e fomente discussões de altíssimo nível em suas devolutivas aos alunos._