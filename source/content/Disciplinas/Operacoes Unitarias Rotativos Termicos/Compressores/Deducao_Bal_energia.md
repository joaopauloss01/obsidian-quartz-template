# Dedução do Balanço de Energia
---

# Dedução da altura manométrica (_head_) em compressores

## 1. Introdução

Assim como em bombas, a análise de compressores pode ser feita a partir da **Primeira Lei da Termodinâmica aplicada ao escoamento permanente**.

No caso dos compressores, porém, o fluido de trabalho é um **gás compressível**, de modo que o termo de pressão não pode ser simplificado diretamente como em líquidos.

O objetivo é obter uma expressão para a **altura manométrica do compressor**, ou _head_, em função das propriedades do gás e das condições de sucção e descarga.

---

## 2. Relações de compressão de um gás

Na compressão de gases, três transformações aparecem com frequência:

### Compressão isotérmica

$$  
PV = \text{cte}  
$$

### Compressão adiabática

$$  
PV^k = \text{cte}  
$$

onde $k = \dfrac{c_p}{c_v}$.

### Compressão politrópica

$$  
PV^\delta = \text{cte}  
$$

ou, de forma equivalente,

$$  
PV^n = \text{cte}  
$$

Neste desenvolvimento, utilizaremos a forma politrópica, pois ela representa melhor o comportamento real dos compressores.

---

## 3. Caso de referência: fluido incompressível

Para um escoamento incompressível, a equação de energia mecânica pode ser escrita como:

$$  
H_T = \frac{\dot W}{\dot m g}  
= \frac{P_2 - P_1}{\rho g}

- \frac{v_2^2 - v_1^2}{2g}
    
- (z_2-z_1)
    
- h_f  
    $$
    

Nesse caso, como $\rho$ é constante, o termo de pressão pode ser escrito diretamente como:

$$  
\int_{P_1}^{P_2} \frac{dP}{\rho}  
= \frac{P_2-P_1}{\rho}  
$$

Essa simplificação é válida para líquidos, mas **não** para gases em compressão.

---

## 4. Caso do gás compressível

Para gases, deve-se manter o termo de pressão na forma integral:

$$  
e_{pr} = \int_{P_s}^{P_d} \frac{dP}{\rho}  
$$

onde:

- $P_s$ = pressão de sucção
    
- $P_d$ = pressão de descarga
    

Agora precisamos encontrar uma expressão para $\rho$ em função da pressão.

---

## 5. Relação politrópica para a densidade

Partindo da compressão politrópica:

$$  
PV^\delta = \text{cte}  
$$

como $V = \dfrac{m}{\rho}$, então:

$$  
P\left(\frac{m}{\rho}\right)^\delta = \text{cte}  
$$

Como $m$ é constante:

$$  
\frac{P}{\rho^\delta} = \text{cte}  
$$

ou ainda:

$$  
P = C \rho^\delta  
$$

Logo:

$$  
\rho = \rho_s \left(\frac{P}{P_s}\right)^{1/\delta}  
$$

onde $\rho_s$ é a densidade na sucção.

Assim:

$$  
\frac{1}{\rho}  
= \frac{1}{\rho_s}\left(\frac{P_s}{P}\right)^{1/\delta}  
$$

Substituindo na integral do termo de pressão:

$$  
e_{pr}  
= \int_{P_s}^{P_d} \frac{dP}{\rho}  
= \frac{P_s^{1/\delta}}{\rho_s}\int_{P_s}^{P_d} P^{-1/\delta}, dP  
$$

---

## 6. Integração do termo de pressão

A integral é:

$$  
\int P^{-1/\delta}, dP

\frac{P^{,1-\frac{1}{\delta}}}{1-\frac{1}{\delta}}  
$$

Como

$$  
1-\frac{1}{\delta} = \frac{\delta-1}{\delta}  
$$

então:

$$e_{pr}

\frac{P_s^{1/\delta}}{\rho_s}  
\cdot  
\frac{\delta}{\delta-1}  
\left[  
P^{\frac{\delta-1}{\delta}}  
\right]_{P_s}^{P_d}  
$$

Aplicando os limites:

$$  
e_{pr}

= \frac{\delta}{\delta-1}\frac{P_s^{1/\delta}}{\rho_s}  
\left(  
P_d^{\frac{\delta-1}{\delta}}

P_s^{\frac{\delta-1}{\delta}}  
\right)  
$$

Colocando em evidência:

$$  
e_{pr}=

\frac{\delta}{\delta-1}\frac{P_s}{\rho_s}  
\left[  
\left(\frac{P_d}{P_s}\right)^{\frac{\delta-1}{\delta}} - 1  
\right]  
$$

Esse é o resultado central do desenvolvimento do termo de pressão para gás compressível.

---

## 7. Aplicação da Primeira Lei ao compressor

A equação geral da energia em regime permanente pode ser escrita como:

$$  
\frac{\dot W}{\dot m g}

\frac{e_{pr}}{g}  
+  
\frac{v_d^2-v_s^2}{2g}  
+  
(z_d-z_s)  
+  
h_f  
$$

Substituindo a expressão de $e_{pr}$:

$$  
\frac{\dot W}{\dot m g}

\frac{1}{g}  
\cdot  
\frac{\delta}{\delta-1}\frac{P_s}{\rho_s}  
\left[  
\left(\frac{P_d}{P_s}\right)^{\frac{\delta-1}{\delta}} - 1  
\right]  
+  
\frac{v_d^2-v_s^2}{2g}  
+  
(z_d-z_s)  
+  
h_f  
$$

---

## 8. Relação com a equação dos gases reais

Podemos agora usar a expressão para a densidade do gás na sucção:

$$  
P_s V = Z_s nRT_s  
$$

e, como

$$  
\rho_s = \frac{m}{V}  
$$

temos:

$$  
\frac{P_s}{\rho_s}

\frac{Z_sRT_s}{M}  
$$

onde:

- $Z_s$ = fator de compressibilidade na sucção
    
- $R$ = constante universal dos gases
    
- $T_s$ = temperatura absoluta de sucção
    
- $M$ = massa molar do gás
    

Substituindo na equação anterior:

$$  
\frac{\dot W}{\dot m g}=

\frac{1}{g}  
\cdot  
\frac{\delta}{\delta-1}  
\cdot  
\frac{Z_sRT_s}{M}  
\left[  
\left(\frac{P_d}{P_s}\right)^{\frac{\delta-1}{\delta}} - 1  
\right]  
+  
\frac{v_d^2-v_s^2}{2g}  
+  
(z_d-z_s)  
+  
h_f  
$$

---

## 9. Simplificações usuais para compressores

Na prática, em muitos compressores:

- a variação de energia potencial é pequena, então $z_d-z_s \approx 0$;
    
- a variação de energia cinética é pequena, então $\dfrac{v_d^2-v_s^2}{2g} \approx 0$;
    
- as perdas de carga podem ser desprezadas frente ao trabalho de compressão, então $h_f \approx 0$.
    

Assim, a expressão se reduz para:

$$  
H

= \frac{\dot W}{\dot m g}

\frac{1}{g}  
\cdot  
\frac{\delta}{\delta-1}  
\cdot  
\frac{Z_sRT_s}{M}  
\left[  
\left(\frac{P_d}{P_s}\right)^{\frac{\delta-1}{\delta}} - 1  
\right]  
$$

---

## 10. Expressão final do _head_ do compressor

Portanto, a altura manométrica do compressor é dada por:

$$  
H=

\frac{\delta}{\delta-1}  
\cdot  
\frac{Z_sRT_s}{gM}  
\left[  
\left(\frac{P_d}{P_s}\right)^{\frac{\delta-1}{\delta}} - 1  
\right]  
$$

---

## 11. Interpretação física

Essa equação mostra que o _head_ do compressor:

- **aumenta** com a razão de compressão $\dfrac{P_d}{P_s}$;
    
- **aumenta** com a temperatura de sucção $T_s$;
    
- depende do comportamento termodinâmico do processo por meio de $\delta$;
    
- depende da não idealidade do gás por meio de $Z_s$.
    

Diferentemente do caso de bombas, o _head_ em compressores não é governado apenas por diferença de pressão dividida por densidade constante, porque a densidade do gás varia significativamente ao longo da compressão.

---

## 12. Resumo do desenvolvimento

1. Parte-se da Primeira Lei para escoamento permanente.
    
2. Para gases, o termo de pressão deve ser escrito como:
    

$$  
e_{pr} = \int_{P_s}^{P_d} \frac{dP}{\rho}  
$$

3. Usa-se a relação politrópica:
    

$$  
PV^\delta = \text{cte}  
$$

4. Obtém-se $\rho(P)$ e integra-se o termo de pressão.
    
5. Substitui-se $\dfrac{P_s}{\rho_s}$ pela equação dos gases reais:
    

$$  
\frac{P_s}{\rho_s} = \frac{Z_sRT_s}{M}  
$$

6. Desprezam-se, quando apropriado, os termos cinético, potencial e de perda de carga.
    
7. Chega-se à expressão final do _head_ do compressor.
    

---

## 13. Fórmula final em destaque

$$  
H=

\frac{\delta}{\delta-1}  
\cdot  
\frac{Z_sRT_s}{gM}  
\left[  
\left(\frac{P_d}{P_s}\right)^{\frac{\delta-1}{\delta}} - 1  
\right]  
$$

---
