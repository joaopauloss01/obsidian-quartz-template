# Tutorial: Resolução Numérica de EDOs de Ordem Superior no MATLAB

#### 1. Fundamentação Teórica: A Redução de Ordem

Os pacotes matemáticos do MATLAB (e da maioria das linguagens de programação científica) são programados para resolver estritamente sistemas de EDOs de **primeira ordem**. Portanto, o passo preliminar essencial para resolver qualquer problema de valor inicial de segunda ordem (ou ordem $n$) é transformá-lo matematicamente em um sistema equivalente de $n$ equações de primeira ordem acopladas.

De acordo com Amos Gilat e Vish Subramaniam (Livro: _Numerical Methods for Engineers and Scientists_, Capítulo 10, Seção 10.9, p. 432-433), esta transformação é feita introduzindo novas variáveis dependentes.

Seja a EDO genérica de segunda ordem: $$ \frac{d^2y}{dt^2} = f\left(t, y, \frac{dy}{dt}\right) $$ Definimos uma nova variável, $w$, que representa a primeira derivada de $y$: $$ w = \frac{dy}{dt} $$ Diferenciando $w$ em relação ao tempo, temos: $$ \frac{dw}{dt} = \frac{d^2y}{dt^2} $$ Substituindo essas definições na equação original, nosso problema de segunda ordem se transforma no seguinte sistema de duas EDOs de primeira ordem:

1. $\frac{dy}{dt} = w$
2. $\frac{dw}{dt} = f(t, y, w)$

#### 2. Funções Embutidas do MATLAB

O MATLAB possui uma suíte robusta de funções embutidas (solvers) para problemas de valor inicial. A escolha da função depende da rigidez ("stiffness") do sistema:

- **`ode45`**: Utiliza o método de Runge-Kutta explícito de 4ª e 5ª ordens (Dormand-Prince). Segundo Gilat (p. 440), é o algoritmo recomendado como "primeira tentativa" para a maioria dos problemas não-rígidos.
- **`ode15s`**: Solver multi-passos baseado em fórmulas de diferenciação numérica, essencial para sistemas rígidos (onde as variáveis dinâmicas apresentam escalas de tempo que variam muito rapidamente em comparação umas com as outras).

**Sintaxe Básica para Sistemas (Gilat, Seção 10.10.2, p. 444-445):** O formato da chamada principal da função é: `[t, y] = ode45(@FuncaoEDO, tspan, y0, options, p1, p2...)` Onde:

- `@FuncaoEDO`: Função que contém as equações do sistema na forma de um vetor coluna.
- `tspan`: Vetor de integração, como `[t_inicial t_final]`.
- `y0`: Vetor coluna com as condições iniciais $[y(t_0); w(t_0)]$.
- `options`: Parâmetros de controle de erro (pode ser deixado vazio `[]` para usar os padrões).
- `p1, p2`: Parâmetros físicos passados para a função da EDO.

---

#### 3. Exemplo Prático em Engenharia Química: Dinâmica de Controle de Processos

Para ilustrar este conceito aos alunos, um exemplo clássico da Engenharia Química é a resposta dinâmica de instrumentos e processos de controle. Conforme Michael E. Cutlip em _Problem Solving in Chemical and Biochemical Engineering with POLYMATH, Excel, and MATLAB_ (Capítulo 13, Seção 13.1, p. 570-571), muitos processos físicos, como sistemas de tanques interagentes ou sensores térmicos encapsulados, são descritos por modelos de segunda ordem.

A equação padrão de um sistema linear de segunda ordem submetido a uma perturbação $\Delta u$ é dada por: $$ \tau^2 \frac{d^2y}{dt^2} + 2\zeta\tau \frac{dy}{dt} + y = K \Delta u $$ Onde:

- $y$: Variável de resposta do processo (ex: nível, temperatura).
- $\tau$: Constante de tempo do sistema.
- $\zeta$: Fator de amortecimento.
- $K$: Ganho do processo.
- $\Delta u$: Perturbação de entrada tipo degrau.

**Passo 1: Modelagem Matricial para o MATLAB** Isolando a derivada de maior ordem e aplicando a redução de variáveis discutida anteriormente ($y_1 = y$ e $y_2 = \frac{dy}{dt}$):

1. $\frac{dy_1}{dt} = y_2$
2. $\frac{dy_2}{dt} = \frac{1}{\tau^2} \left( K \Delta u - y_1 - 2\zeta\tau y_2 \right)$

**Passo 2: Implementação em MATLAB (Script para sua Aula)**

_Arquivo 1: A função que calcula as derivadas (salvar como `SistemaControle.m`)_

```
function dydt = SistemaControle(t, y, tau, zeta, K, du)
    % y(1) representa y (a variável de processo)
    % y(2) representa dy/dt (a taxa de variação)

    dydt = zeros(2,1); % Inicializa o vetor coluna obrigatório

    % Equação 1: dy_1/dt = y_2
    dydt(1) = y(2);

    % Equação 2: dy_2/dt = (K*du - y_1 - 2*zeta*tau*y_2) / tau^2
    dydt(2) = (K*du - y(1) - 2*zeta*tau*y(2)) / (tau^2);
end
```

_Arquivo 2: O Script Principal de Simulação_

```
% Script Principal: Resolução Numérica de EDO de 2ª Ordem
clear; clc; close all;

% 1. Parâmetros do Processo
tau = 3.0;      % Constante de tempo (min)
zeta = 0.5;     % Fator de amortecimento (Subamortecido < 1)
K = 2.0;        % Ganho do processo
du = 1.0;       % Perturbação degrau

% 2. Condições Iniciais e Tempo de Simulação
% Condição inicial: y(0) = 0 e dy/dt(0) = 0
y0 = [0; 0];  
tspan = ; % Integração de t = 0 a t = 30 min

% 3. Solução Numérica com ode45
% Passamos os parâmetros da engenharia após a opção vazia '[]'
[t, Y_result] = ode45(@SistemaControle, tspan, y0, [], tau, zeta, K, du);

% 4. Extração e Plotagem dos Resultados
% Y_result é uma matriz onde a Coluna 1 é y(t) e a Coluna 2 é dy/dt
y_t = Y_result(:, 1);

figure;
plot(t, y_t, 'b-', 'LineWidth', 2);
title('Resposta Dinâmica do Processo de 2ª Ordem');
xlabel('Tempo (min)');
ylabel('Variável de Processo, y(t)');
grid on;
```

#### Dica para interação com a turma:

Ao rodar este código com os alunos, recomendo que você peça para que eles alterem o fator de amortecimento ($\zeta$).

- Mostre a eles que para $\zeta < 1$ (como o $0.5$ do código), o sistema oscila (comportamento subamortecido).
- Para $\zeta > 1$ (ex: $1.5$), a oscilação desaparece (superamortecido).
- Isso mostrará perfeitamente como o método numérico traduz o fenômeno físico estudado nos livros de Engenharia Química.

Este material fornece o referencial teórico embasado com aplicação prática robusta para os seus alunos. Boa aula!