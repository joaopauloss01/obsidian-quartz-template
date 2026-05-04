# Tutorial: Resolução Numérica de EDOs de Ordem Superior 3+ no MATLAB

### 1. Generalização: Redução de EDOs de Ordem $n$

O princípio matemático para resolver qualquer EDO de ordem superior a 1 em pacotes computacionais como o MATLAB é a generalização da redução de variáveis. Segundo Amos Gilat e Vish Subramaniam no livro _Numerical Methods for Engineers and Scientists_ (Capítulo 10, Seção 10.9, p. 436), uma EDO de ordem $n$ genérica descrita por: $$ \frac{d^n y}{dx^n} = f\left(x, y, \frac{dy}{dx}, \frac{d^2 y}{dx^2}, \ldots, \frac{d^{n-1}y}{dx^{n-1}}\right) $$ pode ser transformada num sistema de $n$ EDOs de primeira ordem através da introdução de $n$ novas variáveis dependentes.

O procedimento sistemático define que a primeira derivada de cada nova variável será igual à variável seguinte, até chegarmos à derivada de maior ordem. Definimos as variáveis $w$ da seguinte forma: $w_1 = \frac{dy}{dx}$, $w_2 = \frac{dw_1}{dx} = \frac{d^2y}{dx^2}$, e assim sucessivamente até $w_{n-1} = \frac{dw_{n-2}}{dx} = \frac{d^{n-1}y}{dx^{n-1}}$.

Com isso, o sistema para o MATLAB alimentado na função `ode45` ficará na forma do vetor coluna:

1. $\frac{dy}{dx} = w_1$
2. $\frac{dw_1}{dx} = w_2$ ... $n$.
3. $\frac{dw_{n-1}}{dx} = f(x, y, w_1, w_2, \ldots, w_{n-1})$.

### 2. O Caso Específico da 3ª Ordem

Se tivermos um problema de 3ª ordem, a EDO tem a forma $y''' = f(x, y, y', y'')$. Definindo $y_1 = y$, $y_2 = y'$ e $y_3 = y''$, o sistema de 3 equações de primeira ordem simultâneas exigido pelo MATLAB será:

- $\frac{dy_1}{dx} = y_2$
- $\frac{dy_2}{dx} = y_3$
- $\frac{dy_3}{dx} = f(x, y_1, y_2, y_3)$

---

### 3. Exemplos de Aplicação na Engenharia Química para os Alunos

Para motivar os alunos, é fundamental mostrar onde equações de ordem tão alta surgem na nossa área. A literatura de engenharia química destaca problemas muito clássicos de Fenômenos de Transporte e Reatores que caem exatamente nestes cenários.

#### Exemplo A: Escoamento da Camada Limite de um Fluido Newtoniano sobre Placa Plana (Equação de Blasius)

O autor Michael E. Cutlip no livro _Problem Solving in Chemical and Biochemical Engineering with POLYMATH, Excel, and MATLAB_ (Capítulo 1, p. 9) aponta diretamente que a solução de EDOs de ordem superior é essencial na Mecânica dos Fluidos, especificamente no Problema 8.18 que trata do "Boundary Layer Flow of a Newtonian Fluid on a Flat Plate".

A famosa Equação de Blasius modela o perfil de velocidade do fluido na camada limite e é uma EDO não-linear de **3ª ordem**: $$ 2 \frac{d^3f}{d\eta^3} + f \frac{d^2f}{d\eta^2} = 0 $$ Onde $f$ é a função de corrente adimensional e $\eta$ é a coordenada espacial adimensional.

**Como os alunos devem modelar para o MATLAB:** Definimos o vetor de estados `y` onde $y(1) = f$, $y(2) = f'$, e $y(3) = f''$. A função `ode45` calculará:

```
function dfdeta = Blasius(eta, y)
    dfdeta = zeros(3,1);
    dfdeta(1) = y(2);               % f'
    dfdeta(2) = y(3);               % f''
    dfdeta(3) = -0.5 * y(1) * y(3); % f''' = - (f * f'') / 2
end
```

#### Exemplo B: O [[Metodo_do_Tiro_EDO|Método do Tiro]] (Shooting Method) em Problemas de Contorno (Difusão e Reação)

Muitos problemas de transferência de massa com reação química (como a difusão num pellet de catalisador poroso) ou de transferência de calor em aletas geram EDOs de 2ª ou 3ª ordem onde as condições conhecidas estão em pontos físicos diferentes (ex: concentração conhecida na superfície externa, mas fluxo zero no centro do catalisador). Isso caracteriza um "Problema de Valor de Contorno" (BVP).

Como o `ode45` foi programado para Problemas de Valor Inicial (onde todas as condições são dadas no tempo ou espaço zero), Michael Cutlip (Capítulo 6, Problema 6.5) demonstra que primeiro precisamos converter a EDO de ordem superior em um sistema de primeira ordem. Em seguida, aplicamos o **Método do Tiro**, no qual "chutamos" as condições iniciais desconhecidas que faltam (usando um laço de repetição ou funções como `fzero` combinadas com o `ode45`) e integramos a EDO até o outro extremo do contorno geométrico para verificar se a condição limite real foi atingida.

---

### Dica Pedagógica para a sua Aula

Mostre aos alunos que o algoritmo numérico por trás do `ode45` (Runge-Kutta explícito da família Dormand-Prince) **não se importa com o significado físico das variáveis**. Para o computador, integrar um modelo de 10 reatores CSTR em série (que formam nativamente um sistema de 10 EDOs de 1ª ordem físicas) ou resolver uma única EDO matemática de 10ª ordem (reduzida matematicamente a um vetor de 10 equações) exige rigorosamente a mesma sintaxe computacional e o mesmo tempo de processamento. Dominar a redução de ordem é o que liberta o engenheiro químico para focar exclusivamente na modelagem fenomenológica.