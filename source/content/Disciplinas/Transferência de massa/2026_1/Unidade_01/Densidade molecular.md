ref.: [[Equação de Chapman Enskog]]
A **densidade molecular** vem diretamente da **equação de estado do gás ideal**. Vou mostrar o caminho completo partindo de

$$  
PV = nRT  
$$

---

# 1️⃣ Equação do gás ideal

A forma molar da equação é

$$  
PV = nRT  
$$

onde

- $P$ = pressão
    
- $V$ = volume
    
- $n$ = número de mols
    
- $R$ = constante universal dos gases
    
- $T$ = temperatura
    

---

# 2️⃣ Concentração molar

Dividindo a equação por $V$:

$$  
P = \frac{n}{V} RT  
$$

A quantidade

$$  
C = \frac{n}{V}  
$$

é a **concentração molar**.

Então

$$  
C = \frac{P}{RT}  
$$

---

# 3️⃣ Densidade molecular (número de moléculas)

Na teoria cinética não usamos mols, usamos **número de moléculas**.

Sabemos que

$$  
n = \frac{N}{N_A}  
$$

onde

- $N$ = número de moléculas
    
- $N_A$ = número de Avogadro
    

Substituindo na equação dos gases:

$$  
PV = \frac{N}{N_A}RT  
$$

---

# 4️⃣ Isolando a densidade molecular

Dividindo novamente por $V$:

$$  
P = \frac{N}{V} \frac{RT}{N_A}  
$$

A quantidade

$$  
n_m = \frac{N}{V}  
$$

é a **densidade molecular**  
(número de moléculas por volume).

Então

$$  
n_m = \frac{P N_A}{RT}  
$$

---

# 5️⃣ Forma usando constante de Boltzmann

Sabemos que

$$  
R = N_A k_B  
$$

Substituindo:

$$  
n_m = \frac{P}{k_B T}  
$$

onde

- $k_B$ = constante de Boltzmann
    

---

# 6️⃣ Resultado importante

A densidade molecular é

$$  
n_m = \frac{P}{k_B T}  
$$

ou

$$  
n_m = \frac{N_A P}{RT}  
$$

As duas formas são **equivalentes**.

---

# 7️⃣ Interpretação física

A densidade molecular representa

**quantas moléculas existem em um volume unitário**.

Quanto maior a pressão:

- mais moléculas por volume
    
- maior frequência de colisões
    
- menor difusividade
    

Quanto maior a temperatura:

- moléculas mais energéticas
    
- menor densidade molecular
    
- maior difusividade
    

---

# 8️⃣ Conexão com a equação de difusão

Ela aparece quando substituímos na expressão do caminho livre médio:

$$  
\lambda =  
\frac{1}{\sqrt{2} n_m \sigma^2}  
$$

Substituindo

$$  
n_m = \frac{P}{k_B T}  
$$

resulta na dependência:

$$  
D_{AB} \propto \frac{T^{3/2}}{P}  
$$

que aparece na equação de **Chapman–Enskog**.

---

💡 **Observação didática importante**

Esse passo é justamente o que transforma uma equação da **teoria cinética microscópica** em uma expressão **macroscópica em função de $P$ e $T$**.

Sem essa substituição, a equação ficaria em função da **densidade molecular**, que não é uma variável prática de engenharia.

---

Se quiser, também posso montar um **slide visual muito bom** mostrando a cadeia completa:

$$  
PV=nRT  
\rightarrow  
C=\frac{P}{RT}  
\rightarrow  
n_m=\frac{P N_A}{RT}  
\rightarrow  
n_m=\frac{P}{k_B T}  
$$

Esse slide costuma ajudar muito os alunos a entender **onde surge o $P/T$ na difusividade gasosa**.