A teoria cinética dos gases, em sua forma mais rudimentar baseada no modelo de esferas rígidas, fornece uma boa intuição fenomenológica, mas falha quantitativamente ao prever os coeficientes de difusão experimentais. Para contornar essas limitações e descrever com precisão o transporte de massa no estado gasoso a baixas pressões, recorremos a dois grandes marcos da literatura: a formulação teórica rigorosa de Chapman-Enskog e a correlação empírica de Fuller, Schettler e Giddings.

**1. A Equação de Chapman-Enskog**

Desenvolvida de forma independente por Sydney Chapman na Inglaterra e David Enskog na Suécia no início do século XX, esta equação é fruto de um tratamento matemático rigoroso da teoria cinética dos gases acoplada à mecânica estatística [1, 2]. Ela abandona a ideia de que as moléculas colidem como "bolas de bilhar" e introduz a influência do campo de forças intermoleculares, fundamentado primariamente no potencial (6-12) de Lennard-Jones [1, 3]. 

Para pressões moderadas (tipicamente inferiores a 20 atm), a equação clássica de Chapman-Enskog é expressa por [1, 2, 4]:

$$D_{AB} = \frac{1,858 \times 10^{-3} T^{3/2}}{P \sigma_{AB}^2 \Omega_D} \left( \frac{1}{M_A} + \frac{1}{M_B} \right)^{1/2}$$

Onde cada termo carrega um rigoroso significado físico e dimensional:
*   $D_{AB}$: Coeficiente de difusão binária ordinária (em cm²/s) [5-7].
*   $T$: Temperatura absoluta do sistema (em K) [5-7].
*   $P$: Pressão absoluta do sistema (em atm) [6-8].
*   $M_A, M_B$: Massas molares das espécies químicas A e B (em g/mol) [6-8]. O termo $\left( 1/M_A + 1/M_B \right)$ deriva da massa molar reduzida do sistema [9, 10].
*   $\sigma_{AB}$: Diâmetro de colisão médio para o par molecular (em Å) [6-8]. É calculado pela média aritmética dos diâmetros característicos individuais ($\sigma_{AB} = \frac{\sigma_A + \sigma_B}{2}$), representando a distância em que a energia de atração e repulsão se anula no potencial de Lennard-Jones [3, 11].
*   $\Omega_D$: Integral de colisão para a difusão (adimensional). Este é o grande diferencial da equação. A integral de colisão atua como um fator de correção que expressa a dependência da trajetória de colisão com a temperatura [4, 12]. Ela é função exclusiva da temperatura reduzida ($T^* = \frac{kT}{\epsilon_{AB}}$), onde $\epsilon_{AB}$ representa a energia máxima de atração entre as moléculas do par [13, 14].

**2. A Correlação de Fuller, Schettler e Giddings (1966)**

Apesar do forte embasamento termodinâmico da equação de Chapman-Enskog, o cálculo dos parâmetros de Lennard-Jones ($\sigma$ e $\epsilon/k$) frequentemente introduz desvios e requer uma base de dados extensa. Para fins práticos de engenharia, Fuller, Schettler e Giddings propuseram uma formulação empírica que corrige a equação original modificando a potência da temperatura e substituindo o complexo diâmetro de colisão por volumes atômicos de difusão [6, 15].

A equação de Fuller et al. é escrita da seguinte forma [6, 16, 17]:

$$D_{AB} = \frac{1,0 \times 10^{-3} T^{1,75}}{P \left[ (\sum v)_A^{1/3} + (\sum v)_B^{1/3} \right]^2} \left( \frac{1}{M_A} + \frac{1}{M_B} \right)^{1/2}$$

As unidades de $D_{AB}$, $T$, $P$ e $M$ são idênticas às utilizadas em Chapman-Enskog [6, 16]. As particularidades deste modelo são:
*   **Dependência Térmica:** A proporcionalidade térmica foi empiricamente ajustada de $T^{1,5}$ (ou $T^{3/2}$) para $T^{1,75}$ [6, 16, 17].
*   **Volumes Moleculares de Difusão ($\sum v$):** O termo estriado do denominador utiliza o método de contribuição de grupos. O parâmetro $(\sum v)_i$ é o somatório dos "volumes atômicos de difusão de Fuller" para cada átomo que compõe a molécula $i$ (fornecidos em tabelas específicas, juntamente com correções negativas para anéis aromáticos e heterocíclicos) [6, 16, 17].

**Análise Crítica e Pedagógica:**
Como Engenheiro Químico, é crucial que você saiba quando empregar cada modelo. Apesar da equação de Fuller, Schettler e Giddings ser de natureza puramente empírica, ela é vastamente recomendada na literatura (como por Reid, Prausnitz e Poling) por apresentar, frequentemente, os menores desvios relativos quando comparada aos dados experimentais para pares de gases apolares em baixas pressões [18, 19]. No entanto, a de Chapman-Enskog – especialmente quando combinada com a correção de Brokaw para a integral de colisão – torna-se obrigatória caso o seu sistema envolva vapor d'água, amônia ou qualquer mistura gasosa contendo componentes com elevados momentos dipolares (polaridade acentuada) [20, 21]. 