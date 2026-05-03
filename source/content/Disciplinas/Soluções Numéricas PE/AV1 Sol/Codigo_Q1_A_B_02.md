Vamos separar em **3 gráficos independentes**, um para cada variável.

---

## 💻 Código atualizado (3 gráficos separados)

```python
import numpy as np
import matplotlib.pyplot as plt

# ==============================
# Dados fixos
# ==============================

Q01 = 5.0
Q02 = 1.0

C01 = 10.0
C02 = 1.0

# ==============================
# Range de Q31
# ==============================

Q31_values = np.linspace(0, 10, 100)

C1_vals = []
C2_vals = []
C3_vals = []

# ==============================
# Loop de cálculo
# ==============================

for Q31 in Q31_values:
    
    Q12 = Q01 + Q31
    Q23 = Q02 + Q12
    Q33 = Q23 - Q31

    A = np.array([
        [ Q12,   0.0, -Q31],
        [-Q12,   Q23,  0.0],
        [ 0.0,   Q23, -(Q31 + Q33)]
    ])

    b = np.array([
        Q01 * C01,
        Q02 * C02,
        0.0
    ])

    C = np.linalg.solve(A, b)

    C1_vals.append(C[0])
    C2_vals.append(C[1])
    C3_vals.append(C[2])

# ==============================
# Gráfico C1
# ==============================

plt.figure()
plt.plot(Q31_values, C1_vals)
plt.xlabel("Q31 (m³/min)")
plt.ylabel("C1 (mol/m³)")
plt.title("Variação de C1 com Q31")
plt.grid()
plt.show()

# ==============================
# Gráfico C2
# ==============================

plt.figure()
plt.plot(Q31_values, C2_vals)
plt.xlabel("Q31 (m³/min)")
plt.ylabel("C2 (mol/m³)")
plt.title("Variação de C2 com Q31")
plt.grid()
plt.show()

# ==============================
# Gráfico C3
# ==============================

plt.figure()
plt.plot(Q31_values, C3_vals)
plt.xlabel("Q31 (m³/min)")
plt.ylabel("C3 (mol/m³)")
plt.title("Variação de C3 com Q31")
plt.grid()
plt.show()
```

---

## 🧠 Leitura física refinada (nível prova)

Agora separado fica mais claro:

### 🔹 $C_1(Q_{31})$

- Mostra o impacto direto do reciclo na entrada
    
- Tendência: **queda suave**
    
- Interpretação: diluição por reciclo
    

---

### 🔹 $C_2(Q_{31})$

- Região intermediária do sistema
    
- Influenciada por:
    
    - entrada fresca
        
    - mistura com tanque 1
        
- Tendência: **ajuste gradual**
    

---

### 🔹 $C_3(Q_{31})$

- Diretamente acoplado ao reciclo
    
- Resultado chave:
    

$$  
C_3 \rightarrow C_2  
$$

- Isso aparece claramente no gráfico
    

---

Se quiser, o próximo passo mais avançado seria:

👉 identificar ponto de saturação do reciclo  
👉 ou encontrar limites analíticos para $Q_{31} \to 0$ e $Q_{31} \to \infty$

Só falar 👍