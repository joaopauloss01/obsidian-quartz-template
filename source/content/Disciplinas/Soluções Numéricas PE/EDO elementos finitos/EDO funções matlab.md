Excelente iniciativa. Preparar material de métodos numéricos exige um equilíbrio fino entre a teoria algébrica e a aplicação algorítmica. Aqui está a explicação técnica que você pode incluir nos seus slides ou roteiro de aula para apresentar as funções computacionais aos seus alunos, utilizando o sistema $3 \times 3$ do Exemplo 5-1 da placa de urânio como contexto prático:

---

### Detalhamento das Funções: MATLAB vs. Python

#### Em MATLAB

O MATLAB foi construído nativamente para álgebra linear e possui duas formas diretas para resolver sistemas de equações lineares. A forma mais eficiente de resolver $Ax = b$ não é invertendo a matriz, mas usando o operador _backslash_ (também chamado de divisão à esquerda).

- **Operador `\` (mldivide):** Utiliza a eliminação de Gauss com pivotamento parcial, sendo capaz de identificar automaticamente se o sistema é esparso, tridiagonal ou simétrico para aplicar a técnica de solução mais rápida e eficiente.
    
    ```
    % Definição da matriz A e vetor b para o Exemplo 5-1
    A = [1 0 0; 1 -2 1; 0 1 -1.0321];
    b = [0; -71.4286; -36.6785];
    
    % Solução
    x = A \ b;
    ```
    
- **`inv(A)*b`:** O MATLAB também possui a função `inv()` para calcular a matriz inversa. No entanto, a própria literatura ressalta que essa abordagem é muito menos eficiente do que o uso do operador `\`.

#### Em Python (NumPy/SciPy)

No ecossistema Python, utilizamos o módulo `linalg` da biblioteca **NumPy** para operações de matriz densa e a biblioteca **SciPy** para matrizes esparsas (comuns em problemas de malhas grandes).

- **`np.linalg.solve(A, b)`:** É o equivalente direto ao _backslash_ do MATLAB. Esta função implementa um algoritmo mais sofisticado e eficiente adaptado do pacote LAPACK (originalmente escrito em Fortran 90). Ele computa a solução exata sem calcular a inversa explicitamente.
    
    ```
    import numpy as np
    
    # Definição das matrizes como arrays do NumPy
    A = np.array([, [1, -2, 1], [0, 1, -1.0321]])
    b = np.array([0, -71.4286, -36.6785])
    
    # Solução
    x = np.linalg.solve(A, b)
    ```
    
- **`np.linalg.inv(A).dot(b)`:** Similar ao MATLAB, o Python pode calcular a inversa da matriz e usar o método `.dot()` ou a função `matmul` para multiplicar pelo vetor $b$. No entanto, tabular o número de cálculos dessa operação revela que ela exige muito mais etapas individuais do que a função `solve`.
- **`scipy.sparse.linalg.spsolve`:** Se a sua matriz de engenharia for muito grande (como no cenário que discutimos de 1000 nós), o sistema será tridiagonal e com muitos zeros. Você deve definir $A$ como uma matriz esparsa e usar esta função para economizar memória RAM e tempo de processamento drásticamente.

---

### Dica de Ouro para a Aula:

Explique aos alunos que **nunca** se deve usar $x = A^{-1} \cdot b$ (`inv(A)*b` ou `np.linalg.inv(A).dot(b)`) em problemas reais de engenharia. O custo computacional da inversão é muito maior e a grande quantidade de cálculos introduz mais erros de arredondamento na máquina do que a eliminação direta via `solve` ou `\`. Mostre a eles que as ferramentas já possuem a inteligência nativa para tratar esses modelos físicos complexos de forma otimizada!