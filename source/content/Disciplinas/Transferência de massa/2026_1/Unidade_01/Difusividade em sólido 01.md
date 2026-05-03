# 🧠 1. Equação utilizada

O código implementa a equação de Arrhenius para difusão:

$$  
D = D_0 e^{-\frac{Q}{RT}}  
$$

onde:

- $D$ → difusividade
    
- $D_0$ → fator pré-exponencial
    
- $Q$ → energia de ativação
    
- $R$ → constante dos gases
    
- $T$ → temperatura em Kelvin
    

---

# 🧱 2. Importação das bibliotecas

```python
import numpy as np
import matplotlib.pyplot as plt
```

### O que cada uma faz:

- `numpy` → cálculos numéricos (vetores, exponencial, etc.)
    
- `matplotlib` → criação do gráfico
    

---

# 📊 3. Definição dos parâmetros físicos

```python
R = 1.987  # cal/mol/K
```

Constante dos gases na unidade correta para combinar com $Q$ (em cal/mol).

---

## Parâmetros dos materiais

```python
params = {
    "C em Fe (ccc)": {"D0": 0.0079, "Q": 18100},
    "C em Fe (cfc)": {"D0": 0.21,   "Q": 33800},
}
```

Aqui definimos:

|Sistema|$D_0$|$Q$|
|---|---|---|
|Fe ccc|0.0079|18100|
|Fe cfc|0.21|33800|

👉 Isso permite comparar os dois comportamentos no mesmo gráfico.

---

# 🌡️ 4. Criação da faixa de temperatura

```python
T_C = np.linspace(500, 1200, 400)
T_K = T_C + 273.15
```

### Explicação:

- `linspace(500, 1200, 400)` → cria 400 pontos entre 500°C e 1200°C
    
- Conversão para Kelvin:
    

$$  
T(K) = T(°C) + 273.15  
$$

👉 Fundamental, pois a equação exige temperatura absoluta.

---

# ⚙️ 5. Cálculo das difusividades

```python
curves = {}
for label, p in params.items():
    D = p["D0"] * np.exp(-p["Q"] / (R * T_K))
    curves[label] = D
```

### O que acontece aqui:

Para cada material:

$$  
D(T) = D_0 \cdot e^{-Q/(RT)}  
$$

- `np.exp(...)` calcula a exponencial
    
- O resultado é um **vetor de valores de D para cada temperatura**
    

👉 Isso gera as curvas do gráfico.

---

# 📍 6. Cálculo específico em 1000°C

```python
T0_C = 1000
T0_K = T0_C + 273.15
```

```python
D_1000 = {
    label: p["D0"] * np.exp(-p["Q"] / (R * T0_K))
    for label, p in params.items()
}
```

### Objetivo:

Calcular valores pontuais para análise:

$$  
D(1000^\circ C)  
$$

👉 Esses pontos são depois marcados no gráfico.

---

# 📈 7. Criação do gráfico

```python
fig, ax = plt.subplots(figsize=(9, 5.5))
```

Define o tamanho da figura.

---

## Plot das curvas

```python
for label, D in curves.items():
    ax.plot(T_C, D, linewidth=2, label=label)
```

- Eixo x → temperatura em °C
    
- Eixo y → difusividade
    

---

# 📍 8. Destaque do ponto em 1000°C

```python
ax.scatter([T0_C], [Dval], s=40)
```

Marca o ponto no gráfico.

```python
ax.annotate(...)
```

Adiciona texto explicativo com o valor numérico.

---

# 📊 9. Escala logarítmica

```python
ax.set_yscale("log")
```

### Por quê?

A difusividade varia exponencialmente:

$$  
D \sim e^{-1/T}  
$$

👉 escala log transforma isso em algo mais visualmente interpretável.

---

# 🧾 10. Ajustes finais

```python
ax.set_xlabel("Temperatura (°C)")
ax.set_ylabel("Difusividade, D (cm²/s)")
ax.set_title("Difusividade do carbono em ferro")
```

```python
ax.grid(True, which="both", alpha=0.3)
ax.legend()
```

---

# 💾 11. Salvando a figura

```python
plt.savefig(out, dpi=200)
```

Salva como imagem para usar em:

- slides
    
- relatórios
    
- aula
    

---

# 🧠 Interpretação física (IMPORTANTE)

O gráfico mostra que:

### 🔹 Fe (ccc)

- menor $Q$ → difusão mais fácil
    
- maior difusividade
    

### 🔹 Fe (cfc)

- maior $Q$ → difusão mais difícil
    
- menor difusividade
    

👉 Isso está ligado à **estrutura cristalina**.

---
