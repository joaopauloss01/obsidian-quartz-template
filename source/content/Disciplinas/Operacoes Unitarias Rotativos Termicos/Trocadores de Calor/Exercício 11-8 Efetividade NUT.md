# 🔥 Método da Efetividade–NTU

## 📌 Enunciado

Um trocador de calor de tubo duplo em contracorrente é utilizado  
para aquecer água de $20^\circ C$ até $80^\circ C$ a uma taxa de $1{,}2\ \text{kg/s}$.

O aquecimento é realizado por um fluido geotérmico disponível a $160^\circ C$,  
com vazão mássica de $2\ \text{kg/s}$.

O tubo interno possui parede fina e diâmetro de $1{,}5\ \text{cm}$.

O coeficiente global de transferência de calor é:

$$
U = 640\ \text{W/m}^2\cdot K
$$

As propriedades dos fluidos são:

- Água fria: $c_p = 4{,}18\ \text{kJ/kg·K}$
- Fluido quente: $c_p = 4{,}31\ \text{kJ/kg·K}$

---

## 🎯 Objetivo

Determinar o **comprimento do trocador de calor** utilizando o método da efetividade–NTU.

---

## 📘 Metodologia

1. Calcular as capacidades térmicas:
$$
C = \dot{m} \cdot c_p
$$

2. Determinar:
$$
C_{min}, \quad C_{max}
$$

3. Calcular a razão:
$$
c = \frac{C_{min}}{C_{max}}
$$

4. Calor real:
$$
\dot{Q}_{real} = C_c (T_{c,o} - T_{c,i})
$$

5. Calor máximo:
$$
\dot{Q}_{max} = C_{min}(T_{h,i} - T_{c,i})
$$

6. Efetividade:
$$
\varepsilon = \frac{\dot{Q}_{real}}{\dot{Q}_{max}}
$$

7. NTU (contracorrente):
$$
NTU = \frac{1}{c - 1} \ln\left(\frac{\varepsilon - 1}{\varepsilon c - 1}\right)
$$

8. Relação com área:
$$
NTU = \frac{U A}{C_{min}}
$$

9. Área do trocador:
$$
A = \frac{NTU \cdot C_{min}}{U}
$$

10. Comprimento:
$$
A = \pi D L \quad \Rightarrow \quad L = \frac{A}{\pi D}
$$