## Gabarito: Sistemas Rotativos e Térmicos

[[Lista de exercícios bombas]]Questão 1: Balanço de Energia e Altura Manométrica

- **Dados**: $\rho = 997 \, \text{kg/m}^3$; $z_s = 2 \, \text{m}$; $z_d = 15 \, \text{m}$; $h_L = 4,5 \, \text{m}$; $Q = 20 \, \text{m}^3\text{/h}$.
    
- **Altura Manométrica ($H_{man}$)**:
    
    $$H_{man} = (z_d - z_s) + \frac{P_d - P_s}{\rho g} + h_L = (15 - 2) + 0 + 4,5 = \mathbf{17,5 \, \text{m}}$$
    
    .
    
- **Potência Hidráulica ($P_h$)**:
    
    $$P_h = \rho \cdot g \cdot Q \cdot H_{man} = 997 \cdot 9,81 \cdot \left(\frac{20}{3600}\right) \cdot 17,5 = \mathbf{950,4 \, \text{W}}$$
    
    .
    

Questão 2: Influência da Pressurização

- **Dados**: $P_s = 150 \, \text{kPa}$; $P_d = 300 \, \text{kPa}$; Sistema da Q1.
    
- **Novo $H_{man}$**:
    
    $$H_{man} = (15 - 2) + \frac{(300 - 150) \cdot 10^3}{997 \cdot 9,81} + 4,5 = 13 + 15,34 + 4,5 = \mathbf{32,84 \, \text{m}}$$
    
    .
    
- **Impacto**: O aumento da pressão de descarga em relação à sucção exige que a bomba forneça mais energia (carga) para vencer o gradiente de pressão.
    

Questão 3: Perda de Carga (Etanol)

- **Dados**: $L = 50 \, \text{m}$; $D_{nom} = 3 \, \text{pol}$ (Sch 40 $\rightarrow D_{int} = 0,0779 \, \text{m}$); $\epsilon = 0,045 \, \text{mm}$; $v = 2,5 \, \text{m/s}$; $\rho = 789 \, \text{kg/m}^3$; $\mu = 1,2 \, \text{cP} = 0,0012 \, \text{Pa}\cdot\text{s}$.
    
- **Reynolds**: $Re = \frac{789 \cdot 2,5 \cdot 0,0779}{0,0012} \approx 128.051$.
    
- **Haaland ($f$)**: $\frac{1}{\sqrt{f}} = -1,8 \log \left[ \left( \frac{\epsilon/D}{3,7} \right)^{1,11} + \frac{6,9}{Re} \right] \rightarrow \mathbf{f \approx 0,0192}$.
    
- **Perda de Carga Total ($h_L$)**:
    
    $$h_L = \left[ f \cdot \frac{L}{D} + \sum K \right] \cdot \frac{v^2}{2g} = \left[ 0,0192 \cdot \frac{50}{0,0779} + (3 \cdot 0,9 + 10) \right] \cdot \frac{2,5^2}{2 \cdot 9,81} = \mathbf{7,97 \, \text{m}}$$
    
    .
    

Questão 4: NPSH (Benzeno)

- **Dados**: $P_{atm} = 101,3 \, \text{kPa}$ (assumido); $P_v = 36 \, \text{kPa}$; $z_s = -3 \, \text{m}$; $h_{Ls} = 1,2 \, \text{m}$.
    
- **NPSH Disponível**:
    
    $$NPSH_{disp} = \frac{P_{atm} - P_v}{\rho g} + z_s - h_{Ls} = \frac{(101,3 - 36) \cdot 10^3}{850 \cdot 9,81} - 3 - 1,2 = 7,83 - 4,2 = \mathbf{3,63 \, \text{m}}$$
    
    .
    
- **Análise**: Como $NPSH_{disp} (3,63 \, \text{m}) > NPSH_{req} (2,5 \, \text{m})$, a bomba **não** irá cavitar. Se a temperatura subir para $70^{\circ}C$, $P_v$ aumenta, o que reduz o $NPSH_{disp}$, aumentando o risco de cavitação.
    

Questão 5: Ponto de Operação

- **Igualdade**: $40 - 0,05 Q^2 = 10 + 0,15 Q^2$.
    
- **Cálculo**: $30 = 0,20 Q^2 \rightarrow Q^2 = 150 \rightarrow \mathbf{Q = 12,25 \, \text{m}^3\text{/h}}$.
    
- **Altura**: $H = 40 - 0,05(150) = \mathbf{32,5 \, \text{m}}$.
    

Questão 6: Efeito da Incrustação

- **Nova Vazão**: $40 - 0,05 Q^2 = 10 + 0,25 Q^2 \rightarrow 30 = 0,30 Q^2 \rightarrow \mathbf{Q = 10 \, \text{m}^3\text{/h}}$.
    
- **Impacto**: A vazão de operação diminui devido ao aumento da resistência ao escoamento (curva do sistema mais íngreme), reduzindo a eficiência global.
    

Questão 7: Mudança de Fluido

- **Dados**: $\rho = 1200 \, \text{kg/m}^3$; $\mu = 150 \, \text{cP} = 0,15 \, \text{Pa}\cdot\text{s}$; $Q = 15 \, \text{m}^3\text{/h}$.
    
- **Reynolds**: Com a viscosidade 150 vezes maior que a da água, o Reynolds será drasticamente reduzido.
    
- **Análise Qualitativa**: O aumento da viscosidade aumenta o fator de atrito e as perdas internas na bomba, elevando significativamente a potência elétrica consumida.
    

Questão 8: Modificação da Linha de Sucção

- **Explicação**: Aumentar o diâmetro reduz a velocidade ($v \propto 1/D^2$), o que diminui drasticamente a perda de carga na sucção ($h_{Ls} \propto v^2$). Isso aumenta o $NPSH$ disponível, afastando o sistema da zona de cavitação.
    

Questão 9: Altura de Sucção Crítica

- **Dados**: $P_{atm} = 101,3 \, \text{kPa}$; $P_v \approx 2,34 \, \text{kPa}$ (água $20^{\circ}C$); $h_{Ls} = 0,8 \, \text{m}$; $NPSH_{disp} = 3,0 \, \text{m}$.
    
- **Cálculo**: $3,0 = \frac{101,3 - 2,34}{1 \cdot 9,81} + z_s - 0,8 \rightarrow 3,0 = 10,08 + z_s - 0,8 \rightarrow \mathbf{z_s = -6,28 \, \text{m}}$.
    
- **Resposta**: A bomba pode ser instalada no máximo **6,28 m** acima do nível do tanque.
    

Questão 10: Integração Térmica e Potência

- **Dados**: $\Delta P = 150 \, \text{kPa}$; $\Delta z = 2 \, \text{m}$; $Q = 100 \, \text{m}^3\text{/h}$; $\eta = 65\%$.
    
- **Carga total ($H_{man}$)**:
    
    $$H_{man} = 2 + \frac{150 \cdot 10^3}{1000 \cdot 9,81} = 2 + 15,29 = \mathbf{17,29 \, \text{m}}$$
    
    
- **Potência Elétrica ($P_e$)**:
    
    $$P_e = \frac{\rho \cdot g \cdot Q \cdot H_{man}}{\eta} = \frac{1000 \cdot 9,81 \cdot (100/3600) \cdot 17,29}{0,65} = 7247,6 \, \text{W} \approx \mathbf{9,72 \, \text{HP}}$$