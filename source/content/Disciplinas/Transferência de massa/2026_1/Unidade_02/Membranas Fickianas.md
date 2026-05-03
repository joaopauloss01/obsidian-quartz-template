
---

### Parte 1: O Desenvolvimento Analítico e Físico (Roteiro do Professor)

**1. O que são Membranas Fickianas e Não Fickianas?** Para que o aluno compreenda a modelagem, ele precisa primeiro entender as premissas físicas do material.

- **Membranas Fickianas:** São matrizes poliméricas densas (sem macroporos contínuos) onde a difusão do gás obedece estritamente à Lei Ordinária da Difusão (1ª Lei de Fick). Fenomenologicamente, três condições **obrigatórias** devem ser satisfeitas:
    1. A mobilidade do soluto penetrante é muito menor do que a mobilidade térmica dos segmentos da cadeia polimérica (o soluto "espera" o polímero vibrar para abrir um volume livre e saltar).
    2. O coeficiente efetivo de difusão na membrana ($D_{Ame}$) é **independente da concentração** do penetrante.
    3. **Não ocorre variação de volume da matriz** (o polímero não incha ou relaxa significativamente com a passagem do gás).
- **Membranas Não Fickianas (ou de Transporte Anômalo):** Ocorrem quando as premissas acima falham. Se o gás interage fortemente com o polímero, ele pode causar o inchamento ( _swelling_) da matriz. Nesse caso, o volume da membrana varia, a mobilidade do soluto se equipara à relaxação das cadeias do polímero, e o coeficiente de difusão passa a ser fortemente dependente da concentração local e do tempo. A Lei de Fick clássica falha e exige modelos reológicos complexos.

**2. O Mecanismo Fenomenológico (Os 3 Estágios)** Para modelar uma membrana Fickiana, dividimos o transporte em três etapas:

- **A) Adsorção (Solubilização):** O gás entra em contato com a face da membrana e se dissolve na superfície do polímero.
- **B) Difusão:** O gás dissolvido migra pelo interior do polímero (região amorfa) impulsionado pelo gradiente de concentração.
- **C) Dessorção:** O gás atinge a outra face e volta para o estado gasoso no ambiente de menor pressão.

**3. O Balanço Macroscópico e a Termodinâmica de Interface** No interior da membrana (sólido denso), a mistura não escoa. Logo, a contribuição convectiva é nula. O fluxo global é governado puramente pela difusão e é constante (regime permanente): $$ N_{A,z} = -D_{Ame} \frac{dC_A}{dz} $$ A força motriz global é a diferença de pressão do gás entre os dois lados da membrana ($P_{A_1}$ na alimentação e $P_{A_2}$ na saída). Mas a Lei de Fick usa concentração no sólido ($C_A$). Como relacioná-las? Usamos a analogia da Lei de Henry para a solubilidade do gás no polímero: $$ C_{A,s} = S \cdot P_{A,s} $$ Onde $S$ é o coeficiente de solubilidade termodinâmica do soluto na membrana.

**4. A Equação Governante e de Projeto** Integrando o fluxo constante ao longo da espessura $\ell$ da membrana ($z_1 = 0$ até $z_2 = \ell$): $$ N_{A,z} = \frac{D_{Ame}}{\ell} (C_{A_1} - C_{A_2}) $$ Substituindo as concentrações pelas relações de equilíbrio termodinâmico nas interfaces ($C_{A_1} = S P_{A_1}$ e $C_{A_2} = S P_{A_2}$): $$ N_{A,z} = \frac{D_{Ame} S}{\ell} (P_{A_1} - P_{A_2}) $$ Como os parâmetros $D_{Ame}$ (cinético) e $S$ (termodinâmico) são propriedades da interação soluto-polímero, os engenheiros os aglutinam em um único macropârametro chamado **Permeabilidade ($P_E$)**: $$ P_E = S \cdot D_{Ame} $$ Chegando à elegante equação final de projeto para membranas Fickianas: $$ N_{A,z} = \frac{P_E}{\ell} (P_{A_1} - P_{A_2}) $$

_(Física para o aluno: Uma boa membrana precisa ter alto $D_{Ame}$ (o gás passa rápido) e alto $S$ (o gás gosta de se dissolver nela). A Permeabilidade é o produto da termodinâmica pela cinética!)_

---
