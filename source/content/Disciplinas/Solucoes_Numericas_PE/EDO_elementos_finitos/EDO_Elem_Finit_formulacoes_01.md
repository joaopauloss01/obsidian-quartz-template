Excelente iniciativa. Preparar material de métodos numéricos exige um equilíbrio fino entre a teoria algébrica e a aplicação algorítmica. O método das Diferenças Finitas funciona muito bem como uma ferramenta para que os alunos visualizem a transformação de um fenômeno físico contínuo em um sistema algébrico, especialmente se você fornecer o contexto físico em formato de passo a passo.

Abaixo, estruturei uma sugestão de roteiro e explicação que você pode levar para os alunos, contextualizando as equações em preparação para a resolução do Exemplo da placa de urânio.

---

## 1. Da Equação Diferencial para as Diferenças Finitas (A Discretização)

A formulação por diferenças finitas consiste basicamente na substituição da resolução de equações diferenciais (ordinárias ou parciais) por equações algébricas. Neste método, as derivadas contínuas são substituídas por aproximações de diferenças calculadas em pontos discretos do domínio.

**Discretização do Domínio:**

- A geometria (como a espessura de uma placa) é dividida em seções uniformes de tamanho $\Delta x$, formando pontos nodais ou simplesmente "nós".
- A coordenada de cada nó é definida por $x_m = m \cdot \Delta x$, e a temperatura nesse ponto específico é $T_m = T(x_m)$.

**Aproximação das Derivadas:**

- A primeira derivada é aproximada pela diferença das temperaturas entre os nós: $\frac{dT}{dx} \cong \frac{T_{m+1} - T_m}{\Delta x}$.
- Consequentemente, a segunda derivada (que rege a condução de calor térmica) é expressa pela diferença central: $\frac{d^2T}{dx^2} \cong \frac{T_{m-1} - 2T_m + T_{m+1}}{\Delta x^2}$.

Isso permite que a equação diferencial $\frac{d^2T}{dx^2} + \frac{\dot{e}}{k} = 0$, que descreve o fenômeno físico continuamente em todo o meio, seja transformada na equação de diferença finita $\frac{T_{m-1} - 2T_m + T_{m+1}}{\Delta x^2} + \frac{\dot{e}_m}{k} = 0$, que é aplicável em pontos pontuais e discretos da malha.

---

## 2. As Equações do Balanço de Calor (Nós Internos)

Uma abordagem muito didática para o aluno derivar a equação algébrica acima é usar o método do balanço de energia, que faz a subdivisão do meio em elementos de volume e avalia as taxas de energia em cada elemento de forma isolada.

**O Balanço em um Elemento (Passo $m$):** Para um regime permanente estacionário, a mudança no conteúdo de energia do elemento é zero. Logo, o somatório das taxas fica: $\dot{Q}_{cond, esq} + \dot{Q}_{cond, dir} + \dot{E}_{ger, elem} = 0$.

Assumindo que a variação da temperatura seja linear entre os nós (uma premissa muito realista para malhas onde a distância entre os nós é pequena), o fluxo de calor transferido por condução que entra e sai do elemento é ditado pela Lei de Fourier:

- $\dot{Q}_{cond, esq} = kA \frac{T_{m-1} - T_m}{\Delta x}$
- $\dot{Q}_{cond, dir} = kA \frac{T_{m+1} - T_m}{\Delta x}$

Incorporando as parcelas da condução e o termo de geração interna do elemento ($\dot{e}_m A \Delta x$) no balanço global, o desenvolvimento resulta na equação clássica do nó interno que servirá para a montagem das linhas da matriz: $$kA \frac{T_{m-1} - T_m}{\Delta x} + kA \frac{T_{m+1} - T_m}{\Delta x} + \dot{e}_m A \Delta x = 0$$

---

## 3. As Equações do Fluxo Especificado (Condições de Contorno)

As formulações de diferenças finitas desenvolvidas até aqui se aplicam apenas aos nós internos, já que o desenvolvimento não engloba os limites e contornos do sistema. Para obter a solução nos contornos, deve-se realizar o balanço em um elemento de volume que possui metade da espessura ($\Delta x / 2$).

**Balanço com Fluxo de Calor Especificado:** A premissa base no contorno é $\sum \dot{Q} + \dot{E}_{ger, elem} = 0$. É importante lembrar aos alunos que o fluxo de calor computado é sempre positivo se a energia entrar no meio, e negativo se sair.

Ao avaliar a extremidade esquerda (nó $m=0$) submetida a um fluxo de calor imposto, a equação de diferenças finitas do balanço fica: $$\dot{Q}_{superficie\ a\ esquerda} + kA \frac{T_1 - T_0}{\Delta x} + \dot{e}_0(A\Delta x/2) = 0$$

Como o fluxo especificado na superfície pode ser trocado por $\dot{q}_0 A$, a equação final para montar as fronteiras da matriz algébrica é: $$\dot{q}_0 A + kA \frac{T_1 - T_0}{\Delta x} + \dot{e}_0(A\Delta x/2) = 0$$

---

### Dica de Ouro para a Aula e para o Exemplo 5-1:

No exercício da placa de urânio (Exemplo 5-1), os alunos terão a oportunidade de praticar esses exatos três passos. Você pode demonstrar como usar uma **Temperatura Especificada** na face esquerda ($T_0=0^\circ C$), aplicar o **Balanço de Calor dos Nós Internos** (Passo 2) para a região central do urânio sujeita à geração $\dot{e} = 5 \times 10^6 \ W/m^3$, e então adaptar o princípio do balanço de extremidade do **Fluxo Especificado** (Passo 3) para a borda direita. Nesta última face, em vez do fluxo $\dot{q}_0$, o contorno estará sujeito à convecção de resfriamento com o ambiente usando o conceito análogo da espessura de $\Delta x /2$ do volume do nó. Assim, a ponte entre o modelo físico termodinâmico e o código $Ax = b$ fica perfeitamente clara!