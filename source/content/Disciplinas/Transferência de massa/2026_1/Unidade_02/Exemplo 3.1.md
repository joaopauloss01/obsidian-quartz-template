Como professor titular da disciplina de Transferência de Massa, é com grande satisfação que o guiarei pela resolução analítica rigorosa do **Exemplo 3.1**, conforme apresentado nos slides da nossa aula e no livro-texto.

Este é um problema clássico de difusão em filme estagnado (frequentemente associado ao experimento do Tubo de Stefan). O segredo para dominar Fenômenos de Transporte não reside em decorar fórmulas prontas, mas sim em partir da equação fundamental de conservação e, através da interpretação física do sistema, aplicar os cortes matemáticos corretos.

Acompanhe a memória de cálculo e as justificativas fenomenológicas passo a passo.

---

### 1. Definição do Sistema e Equação Geral

O problema descreve um gás (soluto A) que se difunde através de uma película de ar seco (componente B) com 0,5 cm de profundidade até atingir um ácido, onde é instantaneamente absorvido.

O ponto de partida absoluto para qualquer balanço de massa no contínuo é a **Equação da Continuidade Molar para a espécie A**:

$$ \frac{\partial C_A}{\partial t} + \nabla \cdot \vec{N}_A = R_A''' $$

Onde:

- $\frac{\partial C_A}{\partial t}$: Taxa de acúmulo transiente do soluto A.
- $\nabla \cdot \vec{N}_A$: Divergente do fluxo molar global vetorial (transporte líquido nas fronteiras espaciais).
- $R_A'''$: Taxa de geração/consumo de A por reação química _homogênea_ (no seio do fluido).

### 2. Levantamento das Hipóteses Físicas (Simplificação)

Como engenheiros, devemos impor hipóteses realistas para tornar o modelo solucionável:

- **Hipótese I: Regime Permanente.** O enunciado não menciona transitoriedade, pressupondo-se que o perfil de concentração já se estabeleceu no tempo. Logo, não há acúmulo: $$ \frac{\partial C_A}{\partial t} = 0 $$
- **Hipótese II: Ausência de Reação Química Homogênea.** O gás A cruza o ar B (que é inerte) sem reagir com ele no meio do caminho. A absorção ocorre _apenas na fronteira_ (no fundo do recipiente, ao tocar o ácido). Logo: $$ R_A''' = 0 $$
- **Hipótese III: Transporte Unidirecional.** O tubo capilar confina o movimento do gás. Desprezando os efeitos de borda, assumimos que o fluxo vetorial ocorre exclusivamente na direção vertical (eixo $z$), reduzindo o operador divergente a uma derivada ordinária simples: $$ \nabla \cdot \vec{N}_A = \frac{dN_{A,z}}{dz} $$

Aplicando estas três premissas à Equação da Continuidade, chegamos à sua forma simplificada:

$$ \frac{dN_{A,z}}{dz} = 0 $$

_Interpretação Física:_ O fluxo global de A ao longo do eixo $z$ é estritamente constante. Tudo o que entra no topo do capilar atravessa o filme de ar e atinge o ácido.

### 3. Abertura do Fluxo Global (A Fenomenologia)

Para descobrirmos como a concentração varia no espaço, precisamos expandir o termo $N_{A,z}$. Sabemos que o fluxo global de matéria em relação a um referencial estacionário é a soma das contribuições difusiva e convectiva (movimento global da mistura):

$$ N_{A,z} = \underbrace{-C D_{AB} \frac{dy_A}{dz}}_{\text{1ª Lei de Fick}} + \underbrace{y_A(N_{A,z} + N_{B,z})}_{\text{Arrasto Convectivo}} $$

Neste ponto, aplicamos a hipótese mais crítica do problema:

- **Hipótese IV: Ar estagnado (Meio B inerte e insolúvel).** Como o capilar é fechado no fundo pelo ácido e o ar não é absorvido por ele, o ar (B) encontra-se preso. Macroscopicamente, o ar não possui fluxo líquido na direção $z$. Logo: $$ N_{B,z} = 0 $$

Substituindo $N_{B,z} = 0$ na equação do fluxo global:

$$ N_{A,z} = -C D_{AB} \frac{dy_A}{dz} + y_A N_{A,z} $$

Isolando o fluxo de A, passamos o termo convectivo associado ao próprio A para o lado esquerdo:

$$ N_{A,z} (1 - y_A) = -C D_{AB} \frac{dy_A}{dz} $$ $$ N_{A,z} = \frac{-C D_{AB}}{1 - y_A} \frac{dy_A}{dz} $$

### 4. A Equação Diferencial Governante

Retornando à nossa Equação da Continuidade simplificada ($dN_{A,z}/dz = 0$) e inserindo a expressão fenomenológica do fluxo, obtemos a Equação Diferencial de 2ª ordem não-linear que rege o sistema:

$$ \frac{d}{dz} \left( \frac{-C D_{AB}}{1 - y_A} \frac{dy_A}{dz} \right) = 0 $$

Assumindo que a mistura gasosa se encontra sob temperatura e pressão constantes, a concentração total da mistura ($C$) e o coeficiente de difusão ordinário ($D_{AB}$) são propriedades constantes. Eles podem, então, ser retirados do operador diferencial, restando:

$$ \frac{d}{dz} \left( \frac{1}{1 - y_A} \frac{dy_A}{dz} \right) = 0 $$

### 5. Condições de Contorno (Fronteiras do Domínio)

Para resolvermos uma equação diferencial de segunda ordem em $z$, necessitamos de duas condições de contorno de concentração rigorosamente definidas pelas restrições físicas do capilar:

- **Condição de Contorno 1 (Topo do capilar):** O enunciado define explicitamente a composição na entrada. $$ \text{Em } z = 0 \Rightarrow y_A = 0,0025 \quad (0,25% \text{ em mol}) $$
    
- **Condição de Contorno 2 (Interface Gás-Líquido):** Na profundidade de 0,5 cm, o soluto encontra o ácido e reage instantaneamente. O termo "instantaneamente" em cinética/transferência de massa significa que a taxa de reação intrínseca é infinitamente superior à taxa de difusão, atuando como um "sumidouro perfeito". Dessa forma, não sobra nenhuma molécula de A não reagida acumulada na interface. $$ \text{Em } z = 0,5 \text{ cm} \Rightarrow y_A = 0 $$
    

---

### Síntese Final para o Aluno

O Exemplo 3.1 pede fundamentalmente a **modelagem matemática** do fenômeno. Portanto, a resposta rigorosa final é a Equação Diferencial Ordinária:

$$ \frac{d}{dz} \left( \frac{-C D_{AB}}{1 - y_A} \frac{dy_A}{dz} \right) = 0 $$

Sujeita às condições de Dirichlet:

- $y_A(z = 0) = 0,0025$
- $y_A(z = 0,5) = 0$

_(Nota Pedagógica: Se prosseguíssemos com a integração dupla dessa EDO, encontraríamos um perfil de concentração em decaimento logarítmico, característico de sistemas com alta taxa convectiva unidirecional induzida pela própria difusão do soluto. Certifique-se de compreender perfeitamente a origem do termo $(1-y_A)$ no denominador, pois ele é o grande diferenciador entre a difusão diluída ordinária e a difusão através de um filme estagnado concentrado)._