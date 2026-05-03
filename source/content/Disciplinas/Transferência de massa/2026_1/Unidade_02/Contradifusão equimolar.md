
---

### Parte 1: O Desenvolvimento Analítico e Físico 

O objetivo pedagógico agora é mostrar aos alunos o que acontece quando o meio **não** está estagnado, mas as espécies se movem em sentidos opostos com a mesma magnitude.

**1. O Conceito e os Exemplos de Aplicação** A contradifusão equimolar ocorre quando, para cada molécula de uma espécie A que se move em uma direção, uma molécula da espécie B se move na direção oposta. _Exemplos práticos onde isso ocorre:_

- **Condensação e evaporação simultâneas:** Imagine uma mistura de vapores de benzeno e tolueno (espécies com características físico-químicas semelhantes). Quando essa mistura entra em contato com uma superfície de troca térmica, para cada mol de tolueno que condensa (migrando para o líquido), um mol de benzeno evapora (migrando para o gás).
- **Reservatórios interligados:** Dois tanques isolados contendo misturas binárias de A e B em diferentes concentrações, conectados por um tubo. No tanque 1, A está muito concentrado; no tanque 2, B está muito concentrado. Se abrirmos a válvula, para cada mol de A que difunde do tanque 1 para o 2, um mol de B difunde do tanque 2 para o 1, mantendo a pressão e o número total de mols constantes em ambos os lados.

**2. O Balanço Macroscópico (A Equação da Continuidade)** A base continua sendo a mesma do filme estagnado. Em regime permanente ($\frac{\partial C_A}{\partial t} = 0$), sem reação química homogênea ($R_A''' = 0$) e considerando um fluxo restrito à coordenada cartesiana $z$, a Equação da Continuidade nos garante que o fluxo global é constante: $$ \frac{dN_{A,z}}{dz} = 0 \quad \implies \quad N_{A,z} = \text{Constante} $$

**3. A Fenomenologia (O "Pulo do Gato" da Contradifusão)** É aqui que a mágica acontece. Vamos abrir o fluxo global pela sua definição fundamental (1ª Lei de Fick + Arraste Convectivo): $$ N_{A,z} = \underbrace{-C D_{AB} \frac{dy_A}{dz}}_{\text{Difusão}} + \underbrace{y_A(N_{A,z} + N_{B,z})}_{\text{Convecção}} $$

A condição fundamental que define a _contradifusão equimolar_ é que os fluxos de A e B são iguais em magnitude, mas opostos em sentido: $$ N_{A,z} = -N_{B,z} \quad \text{ou seja,} \quad N_{A,z} + N_{B,z} = 0 $$

Ao substituirmos essa condição na equação fenomenológica, o termo convectivo ($y_A(0)$) é sumariamente **anulado**. O fluxo global passa a ser ditado puramente pela 1ª Lei de Fick: $$ N_{A,z} = -C D_{AB} \frac{dy_A}{dz} \quad \text{ou, em concentração,} \quad N_{A,z} = -D_{AB} \frac{dC_A}{dz} $$

**4. A Equação Governante e o Perfil Linear** Se substituirmos esse fluxo puramente difusivo de volta na equação do balanço ($\frac{dN_{A,z}}{dz} = 0$) e considerarmos $D_{AB}$ constante, obteremos: $$ \frac{d^2 C_A}{dz^2} = 0 $$ Diferente do caso do gás estagnado (que gerava um perfil curvo/logarítmico), a solução matemática de uma derivada segunda igual a zero é uma reta ($C_A(z) = A_1z + A_2$). _Física para o aluno: sem o empuxo convectivo "empurrando" o gás, o perfil de concentração cai de forma estritamente linear ao longo de $z$._

**5. A Expressão Final da Taxa** Integrando o fluxo constante $N_{A,z} = -D_{AB} \frac{dC_A}{dz}$ ao longo da distância $z_1$ até $z_2$, chegamos à equação clássica de projeto para contradifusão equimolar: $$ N_{A,z} = \frac{D_{AB}}{z_2 - z_1} (C_{A_1} - C_{A_2}) $$ Para gases ideais, onde $C_A = P_A/RT$, a equação assume a sua forma mais famosa: $$ N_{A,z} = \frac{D_{AB}}{RT(z_2 - z_1)} (P_{A_1} - P_{A_2}) $$

---
