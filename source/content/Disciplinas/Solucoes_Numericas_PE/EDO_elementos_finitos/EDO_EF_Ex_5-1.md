### Parâmetros do Problema (Exemplo 5-1)

Primeiro, vamos organizar os dados fornecidos no enunciado para a placa de urânio:

- **Espessura da placa ($L$):** $4 \text{ cm} = 0,04 \text{ m}$.
- **Condutividade térmica ($k$):** $28 \text{ W/m}\cdot\text{K}$.
- **Taxa de geração de calor ($\dot{e}$):** $5 \times 10^6 \text{ W/m}^3$.
- **Malha de discretização:** 3 pontos (nós 0, 1 e 2). Logo, $\Delta x = \frac{0,04}{2} = 0,02 \text{ m}$.
- **Condição no Nó 0 (Esquerda):** Temperatura especificada pela água gelada, $T_0 = 0^\circ\text{C}$.
- **Condição no Nó 2 (Direita):** Convecção com o ambiente, $T_\infty = 30^\circ\text{C}$ e $h = 45 \text{ W/m}^2\cdot\text{K}$.

---

### Passo a Passo: Equacionamento Nó a Nó

**1. Nó 0: Contorno à Esquerda (Temperatura Especificada)** Este é o caso mais simples. Como a temperatura da superfície já está fixada pela água gelada, a equação algébrica direta é: $$T_0 = 0$$ _(Na linha da matriz, os coeficientes serão: $1 \cdot T_0 + 0 \cdot T_1 + 0 \cdot T_2 = 0$)_

**2. Nó 1: Nó Interno Central (Balanço com Geração de Calor)** Para o nó 1, aplicamos a formulação padrão de diferenças finitas para nós internos: $$\frac{T_0 - 2T_1 + T_2}{\Delta x^2} + \frac{\dot{e}}{k} = 0$$

Multiplicando toda a equação por $\Delta x^2$ e isolando os termos de temperatura no lado esquerdo, temos a equação da linha 1 da matriz: $$1 \cdot T_0 - 2 \cdot T_1 + 1 \cdot T_2 = -\frac{\dot{e} \Delta x^2}{k}$$

Substituindo os valores numéricos: $$1 \cdot T_0 - 2 \cdot T_1 + 1 \cdot T_2 = -\frac{5 \times 10^6 \cdot (0,02)^2}{28} = -71,4286$$

**3. Nó 2: Contorno à Direita (Convecção + Geração em Meio Volume)** Para a extremidade exposta à convecção, o balanço de energia é feito em um elemento de volume com metade da espessura ($\Delta x / 2$). Somando o calor que entra por condução (vindo do nó 1), o calor que entra por convecção (do ambiente) e a geração interna: $$kA \frac{T_1 - T_2}{\Delta x} + hA(T_\infty - T_2) + \dot{e} A \frac{\Delta x}{2} = 0$$

Dividindo tudo pela área $A$ e por $(k / \Delta x)$ para agrupar os coeficientes de $T$, chegamos à equação: $$T_1 - \left(1 + \frac{h \Delta x}{k}\right) T_2 = -\frac{h \Delta x}{k} T_\infty - \frac{\dot{e} \Delta x^2}{2k}$$

Substituindo os valores numéricos:

- Termo $\frac{h \Delta x}{k} = \frac{45 \cdot 0,02}{28} = 0,03214$
- Geração reduzida à metade $\frac{\dot{e} \Delta x^2}{2k} = \frac{71,4286}{2} = 35,7143$

A equação final para o Nó 2 fica: $$0 \cdot T_0 + 1 \cdot T_1 - 1,0321 \cdot T_2 = - (0,03214 \cdot 30) - 35,7143$$ $$0 \cdot T_0 + 1 \cdot T_1 - 1,0321 \cdot T_2 = -36,6785$$

---

### Montagem da Matriz $Ax = b$

Agora, basta organizar os coeficientes das três equações que desenvolvemos no formato matricial para que os alunos visualizem o sistema linear completo:

$$ \begin{bmatrix}
1 & 0 & 0 \\ 
1 & -2 & 1 \\ 
0 & 1 & -1,0321 
\end{bmatrix} 
\begin{bmatrix} T_0 \\ 
T_1 \\ 
T_2 
\end{bmatrix}

\begin{bmatrix}
0 \\
-71,4286 \\
-36,6785 
\end{bmatrix} 
$$

(Opcional na aula)_: Como $T_0 = 0$, você pode mostrar aos alunos que o sistema pode ser reduzido a uma matriz $2 \times 2$ resolvendo apenas para $T_1$ e $T_2$: 
$$\begin{bmatrix} 
-2 & 1 \\ 
1 & -1,0321 
\end{bmatrix} 
\begin{bmatrix}
T_1 \\ 
T_2 
\end{bmatrix}

\begin{bmatrix}
-71,4286 \\ 
-36,6785 
\end{bmatrix}
$$

---