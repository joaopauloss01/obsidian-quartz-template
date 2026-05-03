
---

### Parte 1: O Desenvolvimento Analítico e Físico

O desafio pedagógico aqui é fazer o aluno entender que $N_{A,z}$ (o fluxo global) ser constante **não significa** que não há convecção ou que o perfil de concentração é uma reta. Para isso, dividimos o raciocínio em duas vertentes que se encontram: o balanço macroscópico e a fenomenologia.

**1. O Balanço Macroscópico (A Equação da Continuidade)** O ponto de partida é a Equação da Continuidade Molar para a espécie A (Equação 3.21 do Cremasco): $$ \frac{\partial C_A}{\partial t} + \nabla \cdot \vec{N}_A = R_A''' $$ Para o cenário de difusão de um vapor (A) através de um filme de gás inerte (B) em um tubo ou capilar (como a evaporação da água no ar estagnado), aplicamos três hipóteses rigorosas:

- **Regime Permanente:** Não há acúmulo de matéria no tempo ($\frac{\partial C_A}{\partial t} = 0$).
- **Meio não reacional:** O gás A não reage com o inerte B no trajeto ($R_A''' = 0$).
- **Fluxo Unidirecional (Coordenada Retangular):** O tubo restringe o movimento às paredes, assumindo-se o fluxo de A apenas na direção vertical $z$ ($\nabla \cdot \vec{N}_A = \frac{dN_{A,z}}{dz}$).

**Conclusão do Balanço:** A equação se reduz a $\frac{dN_{A,z}}{dz} = 0$ (Equação 4.6). _Física para o aluno:_ A derivada de uma função ser zero significa que a função é uma constante. Logo, $N_{A,z} = \text{constante}$. Tudo o que evapora na base do tubo passa por qualquer plano $z$ do filme gasoso sem se perder ou se acumular.

**2. A Fenomenologia (Abrindo o Fluxo Constante)** Sabemos que $N_{A,z}$ é constante, mas do que ele é feito? O fluxo global em relação a eixos estacionários (Equação 2.37) é a soma da contribuição difusiva (Primeira Lei de Fick) com a contribuição convectiva (Arrasto global): $$ N_{A,z} = \underbrace{-C D_{AB} \frac{dy_A}{dz}}_{\text{Difusão}} + \underbrace{y_A(N_{A,z} + N_{B,z})}_{\text{Convecção}} $$ Aqui entra a hipótese definidora do Capítulo 4.2.1: **Filme Inerte e Estagnado**. O componente B (ex: ar) não evapora e não é absorvido pelas extremidades do tubo. Macroscopicamente, ele está parado. Logo, **$N_{B,z} = 0$**.

Substituindo $N_{B,z} = 0$ na fenomenologia, ficamos com: $$ N_{A,z} = -C D_{AB} \frac{dy_A}{dz} + y_A N_{A,z} $$

**3. O Acoplamento e a Equação Governante** Agora, isolamos matematicamente o fluxo de A ($N_{A,z}$): $$ N_{A,z} - y_A N_{A,z} = -C D_{AB} \frac{dy_A}{dz} $$ $$ N_{A,z} (1 - y_A) = -C D_{AB} \frac{dy_A}{dz} $$ $$ N_{A,z} = \frac{-C D_{AB}}{1 - y_A} \frac{dy_A}{dz} $$ _(Equação 4.10 do Cremasco)_

Lembra que o balanço macroscópico provou que $\frac{dN_{A,z}}{dz} = 0$? Se substituirmos a fenomenologia de $N_{A,z}$ dentro da derivada do balanço, chegamos à **Equação Diferencial Governante** do sistema (Equação 4.11): $$ \frac{d}{dz} \left( \frac{-C D_{AB}}{1 - y_A} \frac{dy_A}{dz} \right) = 0 $$ Se a temperatura e a pressão forem constantes (gás ideal), $C$ e $D_{AB}$ saem da derivada (Equação 4.12).

---
