**QUESTÃO 08 (Discursiva - Balanço Térmico e Dimensionamento de Compressor)**

**Texto de Suporte:** O projeto de um sistema de refrigeração e ar condicionado requer não apenas o balanço de energia no volume de controle de cada trocador de calor e do compressor, mas também a transposição dessa capacidade termodinâmica para a geometria mecânica do equipamento. No ciclo real, o sub-resfriamento na linha de líquido garante que não haja _flash gas_ antes da válvula, aumentando o efeito refrigerante (ER), enquanto o superaquecimento assegura a chegada de vapor seco ao compressor, protegendo-o contra golpes de líquido. Para atender a uma carga térmica específica ($Q_e$), o sistema exige uma vazão mássica ($\dot{m}$) que, ditada pelo volume específico do vapor na sucção ($v_1$) e pela eficiência volumétrica real do compressor ($\eta_{vr}$), define o Deslocamento Volumétrico ($V_z$) necessário. A partir de $V_z$, determina-se a cinemática e a geometria (Curso, Diâmetro e Número de Cilindros) do compressor alternativo.

**Enunciado:** Um engenheiro foi designado para projetar o sistema de climatização de uma câmara de testes que exige uma carga térmica de resfriamento constante no evaporador de **32.000 BTU/h**. O equipamento operará com o fluido refrigerante moderno R-32, submetido às seguintes condições operacionais:

- Temperatura de Evaporação ($T_e$): $5^\circ C$
- Temperatura de Condensação ($T_c$): $45^\circ C$
- Superaquecimento total útil: $5\text{ K}$
- Sub-resfriamento: $5\text{ K}$

A partir do diagrama P-h e tabelas do R-32, foram extraídas as seguintes propriedades termodinâmicas de projeto:

| Temperature (°C) | Pressure (bar) | Density (kg/m³) | Volume (m³/kg)    | Int. Energy (kJ/kg) | Enthalpy (kJ/kg) | Entropy (kJ/kg-K) | Quality (kg/kg) |
| ---------------- | -------------- | --------------- | ----------------- | ------------------- | ---------------- | ----------------- | --------------- |
| 5.00000000000    | 9.51448019691  | 1037.74734890   | 0.000963625685053 | 207.883876179       | 208.800715929    | 1.03144770895     | 0.00000000000   |
| 45.0000000000    | 27.9478102558  | 867.264414471   | 0.00115305088427  | 283.085350103       | 286.307874836    | 1.28472447253     | 0.00000000000   |
| 10.0000000000    | 9.51448019691  | 25.0049389996   | 0.0399920991615   | 484.375131667       | 522.425535218    | 2.15878643119     | Superheated     |
| 40.0000000000    | 27.9478102558  | 896.264031526   | 0.00111574264371  | 272.162904790       | 275.281161160    | 1.24979334224     | Subcooled       |
| 80.2645030093    | 27.9478102558  | 62.3081548677   | 0.0160492635695   | 522.247840823       | 567.102018121    | 2.15878643119     | Undefined       |
| 90.0000000000    | 27.9478102558  | 58.9315976607   | 0.0169688255485   | 532.444466914       | 579.868618583    | 2.19442499767     | Superheated     |


- Entalpia do vapor na sucção do compressor ($h_1$): $520\text{ kJ/kg}$
- Volume específico na sucção do compressor ($v_1$): $0,030\text{ m}^3\text{/kg}$
- Entalpia do vapor na descarga do compressor (compressão ideal) ($h_2$): $565\text{ kJ/kg}$
- Entalpia do líquido sub-resfriado na entrada do dispositivo de expansão ($h_3$): $255\text{ kJ/kg}$

Sabe-se que o compressor alternativo a ser construído deverá operar acoplado a um motor com rotação ($N$) de **2000 RPM** e possui uma eficiência volumétrica real ($\eta_{vr}$) estimada em **85%**. Para o design mecânico do bloco, a engenharia adotou uma geometria "quadrada", onde o curso do pistão ($L$) é exatamente igual ao diâmetro do cilindro ($D$).

Com base nas equações de balanço térmico e parâmetros construtivos, determine detalhadamente: **A)** A vazão mássica requerida pelo ciclo ($\dot{m}_f$, em kg/s) e o Coeficiente de Performance (COP) do sistema. **B)** A potência teórica exigida do compressor ($\dot{W}_c$, em kW). **C)** Para atender ao deslocamento volumétrico exigido pelo sistema, defina o projeto do compressor alternativo especificando o **número de cilindros ($N_c$) adotado na indústria (escolha entre 1, 2 ou 4)** e calcule os valores exatos de **Diâmetro ($D$) e Curso ($L$)** do pistão, em milímetros (mm). _(Adote $1\text{ TR} = 12.000\text{ BTU/h} = 3,52\text{ kW}$)_.

---

**Gabarito e Justificativa (Padrão de Resposta Esperado):**

**A) Cálculo da Vazão Mássica e COP** Primeiramente, deve-se converter a capacidade frigorífica (Carga Térmica, $Q_e$) para o Sistema Internacional (kW): $1\text{ TR} = 12.000\text{ BTU/h} = 3,52\text{ kW}$. $Q_e = 32.000\text{ BTU/h} \times \left( \frac{3,52\text{ kW}}{12.000\text{ BTU/h}} \right) = 9,386\text{ kW}$ (ou kJ/s).

No dispositivo de expansão, a expansão é isoentálpica, logo a entalpia de entrada no evaporador é a mesma da saída do condensador: $h_4 = h_3 = 255\text{ kJ/kg}$. O Efeito Refrigerante (ER) é a energia absorvida no evaporador: $ER = h_1 - h_4 = 520 - 255 = 265\text{ kJ/kg}$.

A vazão mássica ($\dot{m}_f$) é dada pela fórmula $Q_e = \dot{m}_f \times (h_1 - h_4)$: $\dot{m}_f = \frac{Q_e}{h_1 - h_4} = \frac{9,386}{265} \approx \mathbf{0,0354\text{ kg/s}}$.

O Coeficiente de Performance (COP) é a relação entre energia útil (ER) e energia gasta (Trabalho de Compressão, $\Delta h_c$): $\Delta h_c = h_2 - h_1 = 565 - 520 = 45\text{ kJ/kg}$. $COP = \frac{h_1 - h_4}{h_2 - h_1} = \frac{265}{45} = \mathbf{5,88}$.

**B) Cálculo da Potência de Compressão** A potência teórica do compressor ($\dot{W}_c$) é o produto da vazão mássica pela variação entálpica no compressor: $\dot{W}_c = \dot{m}_f \times (h_2 - h_1)$ $\dot{W}_c = 0,0354\text{ kg/s} \times 45\text{ kJ/kg} = \mathbf{1,593\text{ kW}}$.

**C) Geometria do Compressor Alternativo (Deslocamento, D, L e $N_c$)** A vazão volumétrica aspirada real do compressor ($V_{real}$) é: $V_{real} = \dot{m}_f \times v_1 = 0,0354\text{ kg/s} \times 0,030\text{ m}^3\text{/kg} = 0,001062\text{ m}^3\text{/s}$.

Sabe-se que $m_{f\text{ real}} = \frac{V_z \times \eta_{vr}}{v_1}$. Logo, o deslocamento volumétrico teórico exigido ($V_z$) é: $V_z = \frac{V_{real}}{\eta_{vr}} = \frac{0,001062}{0,85} \approx 0,00125\text{ m}^3\text{/s}$.

A equação do deslocamento para projeto de compressor alternativo é: $V_z = \frac{\pi \cdot D^2}{4} \cdot L \cdot N_c \cdot \left(\frac{N}{60}\right)$ Onde $N = 2000\text{ RPM}$ (dividiu-se por 60 para converter a frequência para Hz e deixar a vazão em $\text{m}^3\text{/s}$). Como o design é "quadrado" ($L = D$), a fórmula torna-se: $V_z = \frac{\pi \cdot D^3}{4} \cdot N_c \cdot \left(\frac{2000}{60}\right)$ $0,00125 = D^3 \cdot N_c \cdot \left( \frac{3,1415 \times 33,33}{4} \right)$ $0,00125 = D^3 \cdot N_c \cdot 26,18$

Nesta etapa de projeto, cabe ao aluno adotar um número par/equilibrado de cilindros para otimização da máquina.

- **Adotando um compressor bicilíndrico ($N_c = 2$):** $D^3 = \frac{0,00125}{2 \times 26,18} = \frac{0,00125}{52,36} = 0,00002387\text{ m}^3$ $D = \sqrt{0,00002387} \approx 0,0288\text{ m} = \mathbf{28,8\text{ mm}}$ Consequentemente, o curso será $L = \mathbf{28,8\text{ mm}}$.

_(Nota de avaliação: Caso o aluno opte, de forma justificada, por um compressor monocilíndrico ($N_c = 1$), os valores resultantes serão $D = L = 36,3\text{ mm}$. Para $N_c = 4$, $D = L = 22,8\text{ mm}$. Ambas as abordagens provam domínio integral dos parâmetros de fluxo mecânico abordados em)._