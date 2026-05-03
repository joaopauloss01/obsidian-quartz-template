O **aclaramento** (ou _clearance_), representado por $C$, é a distância livre entre as paredes externas de dois tubos adjacentes. Você não o encontrará em tabelas de propriedades químicas, pois ele é uma **dimensão geométrica** definida pelo projeto do trocador.

Existem duas formas de obtê-lo:

### 1. Se você já tem o Passo dos Tubos ($P_t$)

O cálculo é direto. O Passo ($P_t$) é a distância de centro a centro entre dois tubos. Portanto, o aclaramento é o que sobra quando subtraímos o diâmetro externo do tubo ($d_o$):

$$C = P_t - d_o$$

### 2. Se você está projetando do zero (Normas TEMA)

Se o problema não te deu o $P_t$ nem o $C$, você deve seguir as recomendações da norma **TEMA** (_Tubular Exchanger Manufacturers Association_). As regras de bolso mais comuns são:

* **Regra Geral:** O Passo ($P_t$) deve ser, no mínimo, **$1.25$ vezes** o diâmetro externo do tubo ($d_o$).

  * Exemplo: Se seu tubo tem $d_o = 3/4" (0.75")$, o passo será $P_t = 0.75 \times 1.25 = 0.9375"$.

  * Logo, o aclaramento será: $C = 0.9375 - 0.75 = 0.1875"$.

* **Mínimo Absoluto:** Em situações de limpeza mecânica (arranjo quadrado), recomenda-se que $C$ não seja menor que **$1/4"$ (6.35 mm)** para permitir a passagem de escovas ou jatos de água.

***

### Onde os dados costumam "esconder":

* **Diâmetro Externo ($d_o$):** Você obtém na **Tabela BWG** baseada no diâmetro nominal que o problema forneceu (ex: 3/4", 1", etc).

* **Arranjo (Layout):** O enunciado dirá se é "Triangular" ou "Quadrado". Isso não muda a fórmula do $C$, mas muda como os tubos são distribuídos no casco.

**Resumo prático:** Verifique se o seu exercício mencionou algo como "passo de 1 polegada" ou "arranjo quadrado de 1.25d". Se ele deu o $P_t$, basta subtrair o $d_o$ da tabela BWG. Se não deu nada, use a convenção de $P_t = 1.25 \cdot d_o$.

