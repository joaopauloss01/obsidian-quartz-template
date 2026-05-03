Segue o código em Python para resolver o sistema linear da Questão 1.

```python
import numpy as np

# ==============================
# Dados do problema
# ==============================

Q01 = 5.0   # m³/min
Q02 = 1.0   # m³/min
Q31 = 2.0   # m³/min

C01 = 10.0  # mol/m³
C02 = 1.0   # mol/m³

# ==============================
# Cálculo das vazões internas
# ==============================

Q12 = Q01 + Q31
Q23 = Q02 + Q12
Q33 = Q23 - Q31

print("Vazões calculadas:")
print(f"Q12 = {Q12:.4f} m³/min")
print(f"Q23 = {Q23:.4f} m³/min")
print(f"Q33 = {Q33:.4f} m³/min")

# ==============================
# Montagem do sistema linear
# A @ C = b
# ==============================

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

# ==============================
# Solução do sistema
# ==============================

C = np.linalg.solve(A, b)

C1, C2, C3 = C

print("\nMatriz A:")
print(A)

print("\nVetor b:")
print(b)

print("\nConcentrações nos tanques:")
print(f"C1 = {C1:.4f} mol/m³")
print(f"C2 = {C2:.4f} mol/m³")
print(f"C3 = {C3:.4f} mol/m³")
```

Resultado esperado:

```text
Vazões calculadas:
Q12 = 7.0000 m³/min
Q23 = 8.0000 m³/min
Q33 = 6.0000 m³/min

Concentrações nos tanques:
C1 = 9.5714 mol/m³
C2 = 8.5000 mol/m³
C3 = 8.5000 mol/m³
```

Portanto:

$$  
\boxed{C_1 = 9{,}5714 ,\text{mol}/\text{m}^3}  
$$

$$  
\boxed{C_2 = 8{,}5000 ,\text{mol}/\text{m}^3}  
$$

$$  
\boxed{C_3 = 8{,}5000 ,\text{mol}/\text{m}^3}  
$$