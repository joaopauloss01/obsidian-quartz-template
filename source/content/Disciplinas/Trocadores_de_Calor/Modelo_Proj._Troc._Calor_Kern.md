## Projeto completo de trocador de calor pelo método de Kern

O método de Kern é um procedimento clássico de projeto térmico e hidráulico de trocadores casco e tubo. Ele é bastante usado para uma estimativa inicial de área, coeficiente global, número de tubos, perdas de carga e viabilidade do arranjo. O próprio conteúdo da disciplina inclui “projeto de trocadores de calor” e aplicação dos métodos de $\Delta T_{ML}$ e $\varepsilon$–NUT como parte dos tópicos formativos de trocadores de calor . Além disso, o material de Kern apresenta aplicações industriais de trocadores tubulares, incluindo trocadores 1–2, 2–4 e arranjos multipasse .

---

# 1. Dados de entrada do projeto

Para iniciar o projeto, devem ser conhecidos:

- fluido quente e fluido frio;
    
- vazões mássicas $\dot{m}_h$ e $\dot{m}_c$;
    
- temperaturas de entrada e saída;
    
- propriedades físicas médias;
    
- fatores de incrustação;
    
- pressão admissível de operação;
    
- limites de perda de carga;
    
- material dos tubos;
    
- arranjo geométrico desejado.
    

As temperaturas são representadas por:

$$  
T_{h,i},\quad T_{h,o},\quad T_{c,i},\quad T_{c,o}  
$$

onde $h$ representa o fluido quente, $c$ representa o fluido frio, $i$ representa entrada e $o$ representa saída.

---

# 2. Balanço de energia

A carga térmica pode ser calculada pelo fluido quente ou pelo fluido frio:

$$  
\dot{Q}_h=\dot{m}_h\cdot c_{p,h} \cdot \left(T_{h,i}-T_{h,o}\right)  
$$

$$  
\dot{Q}_c=\dot{m}_c \cdot c_{p,c}\cdot \left(T_{c,o}-T_{c,i}\right)  
$$

Para um projeto sem perdas térmicas relevantes:

$$  
\dot{Q}=\dot{Q}_h=\dot{Q}_c  
$$

Caso uma das temperaturas de saída seja desconhecida, ela pode ser obtida pelo balanço:

$$  
\dot{m}_h \cdot c_{p,h}\cdot \left(T_{h,i}-T_{h,o}\right)=\dot{m}_c\cdot c_{p,c}\cdot \left(T_{c,o}-T_{c,i}\right)  
$$

---

# 3. Diferença de temperatura média logarítmica

Para escoamento contracorrente:

$$  
\Delta T_1=T_{h,i}-T_{c,o}  
$$

$$  
\Delta T_2=T_{h,o}-T_{c,i}  
$$

A diferença de temperatura média logarítmica é:

$$  
\Delta T_{ML}=\frac{\Delta T_1-\Delta T_2}{\ln\left(\frac{\Delta T_1}{\Delta T_2}\right)}  
$$

Para trocadores casco e tubo multipasse, deve-se aplicar o fator de correção $F$:

$$  
\Delta T_{ML,corr}=F \cdot \Delta T_{ML}  
$$

O uso do fator de correção é necessário porque configurações mais complexas se desviam do comportamento ideal de contracorrente, como discutido no material de trocadores de calor ao tratar da LMTD e do fator $F$ .

---

# 4. Estimativa inicial da área de troca térmica

A equação geral de projeto é:

$$  
\dot{Q}=U\cdot A\cdot \Delta T_{ML,corr}  
$$

Logo, a área estimada é:

$$  
A=\frac{\dot{Q}}{U\cdot \Delta T_{ML,corr}}  
$$

Nesta primeira estimativa, usa-se um valor típico de $U$ com base no par de fluidos. Para água–óleo, por exemplo, valores típicos de $U$ ficam na faixa de $100$ a $350\,\text{W}/\text{m}^2\cdot\text{K}$, conforme tabela apresentada no material de Cengel .

---

# 5. Escolha preliminar dos tubos

A área externa de um tubo é:

$$  
A_t=\pi \cdot D_o\cdot L  
$$

O número preliminar de tubos é:

$$  
N_t=\frac{A}{\pi\cdot D_o\cdot L}  
$$

onde:

- $D_o$ é o diâmetro externo do tubo;
    
- $L$ é o comprimento do tubo;
    
- $N_t$ é o número de tubos.
    

Após calcular $N_t$, deve-se escolher um número comercial compatível com o arranjo do feixe tubular.

---

# 6. Área de escoamento nos tubos

A área interna de escoamento por tubo é:

$$  
A_{i,t}=\frac{\pi\cdot D_i^2}{4}  
$$

Para $N_p$ passes nos tubos, o número de tubos por passe é:

$$  
N_{t,p}=\frac{N_t}{N_p}  
$$

A área total de escoamento no lado dos tubos é:

$$  
A_{tubos}=N_{t,p}\cdot \frac{\pi\cdot D_i^2}{4}  
$$

A velocidade no lado dos tubos é:

$$  
v_t=\frac{\dot{m}_t}{\rho_t\cdot A_{tubos}}  
$$

---

# 7. Número de Reynolds no lado dos tubos

O número de Reynolds é:

$$  
Re_t=\frac{\rho_t\cdot v_t\cdot D_i}{\mu_t}  
$$

ou, usando vazão mássica:

$$  
Re_t=\frac{D_i\cdot G_t}{\mu_t}  
$$

em que a velocidade mássica é:

$$  
G_t=\frac{\dot{m}_t}{A_{tubos}}  
$$

---

# 8. Coeficiente convectivo no lado dos tubos

Para escoamento turbulento interno, pode-se usar uma correlação do tipo Dittus-Boelter:

$$  
Nu_t=0{,}023\cdot Re_t^{0{,}8}\cdot Pr_t^n  
$$

com:

$$  
Pr_t=\frac{c_{p,t}\cdot \mu_t}{k_t}  
$$

O expoente $n$ depende da condição térmica:

$$  
n=0{,}4  
$$

para aquecimento do fluido, e:

$$  
n=0{,}3  
$$

para resfriamento do fluido.

O coeficiente convectivo interno é:

$$  
h_i=\frac{Nu_t\cdot k_t}{D_i}  
$$

---

# 9. Diâmetro equivalente no lado do casco

No método de Kern, o lado do casco é tratado com um diâmetro equivalente. Para arranjo triangular, uma forma comum é:

$$  
D_e=\frac{4\left(\frac{\sqrt{3}}{4}\cdot P_t^2-\frac{\pi\cdot D_o^2}{8}\right)}{\frac{\pi\cdot D_o}{2}}  
$$

Para arranjo quadrado:

$$  
D_e=\frac{4\left(P_t^2-\frac{\pi\cdot D_o^2}{4}\right)}{\pi\cdot D_o}  
$$

onde:

- $P_t$ é o passo tubular;
    
- $D_o$ é o diâmetro externo do tubo;
    
- $D_e$ é o diâmetro equivalente do lado do casco.
    

---

# 10. Área de escoamento no lado do casco

A área de escoamento transversal no casco pode ser estimada por:

$$  
A_s=\frac{D_s\cdot C\cdot B}{P_t}  
$$

em que:

$$  
C=P_t-D_o  
$$

onde:

- $D_s$ é o diâmetro interno do casco;
    
- $B$ é o espaçamento entre chicanas;
    
- $C$ é a folga entre tubos;
    
- $P_t$ é o passo tubular.
    

---

# 11. Velocidade mássica e Reynolds no casco

A velocidade mássica no casco é:

$$  
G_s=\frac{\dot{m}_s}{A_s}  
$$

O número de Reynolds no casco é:

$$  
Re_s=\frac{D_e\cdot G_s}{\mu_s}  
$$

---

# 12. Coeficiente convectivo no lado do casco

No método de Kern, uma correlação típica para o lado do casco é escrita como:

$$  
j_H=0{,}36\cdot Re_s^{-0{,}55}  
$$

A partir do fator $j_H$, calcula-se:

$$  
h_o=j_H\cdot G_s\cdot c_{p,s}\cdot Pr_s^{-2/3}\left(\frac{\mu_s}{\mu_{w,s}}\right)^{0{,}14}  
$$

onde:

$$  
Pr_s=\frac{c_{p,s}\cdot \mu_s}{k_s}  
$$

Se a correção de viscosidade na parede for desprezada, pode-se usar:

$$  
\left(\frac{\mu_s}{\mu_{w,s}}\right)^{0{,}14}\approx 1  
$$

---

# 13. Coeficiente global limpo

O coeficiente global limpo baseado na área externa dos tubos pode ser calculado por:

$$  
\frac{1}{U_c}=\frac{1}{h_o}+\frac{D_o}{D_i,h_i}+\frac{D_o\ln\left(\frac{D_o}{D_i}\right)}{2\cdot k_w}  
$$

onde:

- $U_c$ é o coeficiente global limpo;
    
- $h_i$ é o coeficiente convectivo interno;
    
- $h_o$ é o coeficiente convectivo externo;
    
- $k_w$ é a condutividade térmica da parede do tubo.
    

Se a resistência da parede for desprezível:

$$  
\frac{1}{U_c}\approx\frac{1}{h_o}+\frac{D_o}{D_i\cdot h_i}  
$$

---

# 14. Coeficiente global sujo

Incluindo incrustação:

$$  
\frac{1}{U_d}=\frac{1}{h_o}+R_{f,o}+\frac{D_o}{D_i}\cdot R_{f,i}+\frac{D_o}{D_i\cdot h_i}+\frac{D_o\ln\left(\frac{D_o}{D_i}\right)}{2\cdot k_w}  
$$

onde:

- $U_d$ é o coeficiente global de projeto;
    
- $R_{f,i}$ é o fator de incrustação interno;
    
- $R_{f,o}$ é o fator de incrustação externo.
    

---

# 15. Fator de sujeira calculado

Após calcular $U_c$ e $U_d$, o fator de sujeira disponível pode ser avaliado por:

$$  
R_d=\frac{1}{U_d}-\frac{1}{U_c}  
$$

O projeto é aceitável termicamente se:

$$  
R_d\geq R_{d,req}  
$$

---

# 16. Área corrigida

Com o coeficiente global de projeto $U_d$, recalcula-se a área requerida:

$$  
A_{req}=\frac{\dot{Q}}{U_d\cdot \Delta T_{ML,corr}}  
$$

A área disponível é:

$$  
A_{disp}=N_t\cdot \pi\cdot D_o\cdot L  
$$

O critério térmico é:

$$  
A_{disp}\geq A_{req}  
$$

---

# 17. Perda de carga no lado dos tubos

A perda de carga nos tubos pode ser estimada por:

$$  
\Delta P_t=N_p\left(4\cdot f_t\cdot \frac{L}{D_i}+\sum K\right)\frac{\rho_t\cdot v_t^2}{2}  
$$

De forma simplificada:

$$  
\Delta P_t=N_p\cdot 4\cdot f_t\cdot \frac{L}{D_i}\cdot \frac{\rho_t\cdot v_t^2}{2}  
$$

A perda de carga nos retornos pode ser adicionada como:

$$  
\Delta P_{ret}=N_p\cdot K_{ret}\cdot \frac{\rho_t\cdot v_t^2}{2}  
$$

Assim:

$$  
\Delta P_{t,total}=\Delta P_t+\Delta P_{ret}  
$$

---

# 18. Perda de carga no lado do casco

No método de Kern, a perda de carga no casco pode ser estimada por:

$$  
\Delta P_s=f_s\cdot \frac{G_s^2\cdot D_s \cdot (N_b+1)}{2\cdot \rho_s \cdot D_e}\left(\frac{\mu_s}{\mu_{w,s}}\right)^{0{,}14}  
$$

O número de chicanas é estimado por:

$$  
N_b=\frac{L}{B}-1  
$$

onde:

- $N_b$ é o número de chicanas;
    
- $B$ é o espaçamento entre chicanas.
    

---

# 19. Critérios finais de aceitação

O projeto é considerado adequado quando atende simultaneamente aos critérios térmicos e hidráulicos:

$$  
A_{disp}\geq A_{req}  
$$

$$  
R_d\geq R_{d,req}  
$$

$$  
\Delta P_t\leq \Delta P_{t,max}  
$$

$$  
\Delta P_s\leq \Delta P_{s,max}  
$$

Também é desejável verificar se as velocidades estão em faixas adequadas para evitar incrustação excessiva, erosão ou perda de carga elevada.

---

# 20. Sequência resumida do método de Kern

1. Definir os dados de processo.
    
2. Fazer o balanço de energia.
    
3. Calcular $\Delta T_{ML}$.
    
4. Aplicar o fator de correção $F$.
    
5. Estimar $U$ inicial.
    
6. Calcular a área preliminar.
    
7. Escolher diâmetro, comprimento e número de tubos.
    
8. Definir número de passes.
    
9. Calcular $h_i$ no lado dos tubos.
    
10. Calcular $h_o$ no lado do casco.
    
11. Calcular $U_c$ e $U_d$.
    
12. Recalcular a área requerida.
    
13. Verificar a área disponível.
    
14. Calcular perdas de carga.
    
15. Ajustar geometria até atender aos critérios térmicos e hidráulicos.
    

---

# 21. Estrutura geral para implementação em Python

```python
import numpy as np

# =========================
# 1. Dados de entrada
# =========================

# Vazões mássicas
m_h = 1.0      # kg/s
m_c = 2.0      # kg/s

# Temperaturas
T_hi = 120.0   # °C
T_ho = 80.0    # °C
T_ci = 30.0    # °C
T_co = 50.0    # °C

# Propriedades médias
cp_h = 2500.0  # J/kg.K
cp_c = 4180.0  # J/kg.K

rho_t = 1000.0
mu_t = 0.001
k_t = 0.60
cp_t = 4180.0

rho_s = 850.0
mu_s = 0.003
k_s = 0.13
cp_s = 2500.0

# Geometria
Do = 0.01905      # m
Di = 0.01600      # m
L = 4.88          # m
Pt = 1.25 * Do    # m
Ds = 0.30         # m
B = 0.15          # m
Np = 2            # passes nos tubos
kw = 16.0         # W/m.K

# Incrustação
Rf_i = 0.0002
Rf_o = 0.0004

# Fator de correção
F = 0.85

# =========================
# 2. Carga térmica
# =========================

Qh = m_h * cp_h * (T_hi - T_ho)
Qc = m_c * cp_c * (T_co - T_ci)
Q = min(Qh, Qc)

# =========================
# 3. DTML corrigida
# =========================

DT1 = T_hi - T_co
DT2 = T_ho - T_ci

DTML = (DT1 - DT2) / np.log(DT1 / DT2)
DTML_corr = F * DTML

# =========================
# 4. Estimativa inicial da área
# =========================

U_estimado = 250.0
A_estimado = Q / (U_estimado * DTML_corr)

Nt_estimado = A_estimado / (np.pi * Do * L)
Nt = int(np.ceil(Nt_estimado))

# =========================
# 5. Lado dos tubos
# =========================

Nt_passe = Nt / Np
A_tubos = Nt_passe * np.pi * Di**2 / 4

G_t = m_c / A_tubos
v_t = G_t / rho_t

Re_t = Di * G_t / mu_t
Pr_t = cp_t * mu_t / k_t

Nu_t = 0.023 * Re_t**0.8 * Pr_t**0.4
h_i = Nu_t * k_t / Di

# =========================
# 6. Lado do casco
# =========================

C = Pt - Do
A_s = Ds * C * B / Pt

G_s = m_h / A_s

De = 4 * ((Pt**2) - (np.pi * Do**2 / 4)) / (np.pi * Do)

Re_s = De * G_s / mu_s
Pr_s = cp_s * mu_s / k_s

jH = 0.36 * Re_s**(-0.55)
h_o = jH * G_s * cp_s * Pr_s**(-2/3)

# =========================
# 7. Coeficiente global
# =========================

R_parede = Do * np.log(Do / Di) / (2 * kw)

inv_Uc = (1 / h_o) + (Do / (Di * h_i)) + R_parede
Uc = 1 / inv_Uc

inv_Ud = (
    (1 / h_o)
    + Rf_o
    + (Do / Di) * Rf_i
    + (Do / (Di * h_i))
    + R_parede
)

Ud = 1 / inv_Ud

Rd_calc = (1 / Ud) - (1 / Uc)

# =========================
# 8. Área requerida e disponível
# =========================

A_req = Q / (Ud * DTML_corr)
A_disp = Nt * np.pi * Do * L

# =========================
# 9. Resultados
# =========================

print(f"Carga térmica: {Q:.2f} W")
print(f"DTML: {DTML:.2f} °C")
print(f"DTML corrigida: {DTML_corr:.2f} °C")
print(f"Número estimado de tubos: {Nt_estimado:.2f}")
print(f"Número adotado de tubos: {Nt}")
print(f"Re_t: {Re_t:.2f}")
print(f"h_i: {h_i:.2f} W/m².K")
print(f"Re_s: {Re_s:.2f}")
print(f"h_o: {h_o:.2f} W/m².K")
print(f"Uc: {Uc:.2f} W/m².K")
print(f"Ud: {Ud:.2f} W/m².K")
print(f"Rd calculado: {Rd_calc:.6f} m².K/W")
print(f"Área requerida: {A_req:.2f} m²")
print(f"Área disponível: {A_disp:.2f} m²")
```

---

Esse roteiro já organiza o projeto completo pelo método de Kern: balanço térmico, $\Delta T_{ML}$ corrigida, estimativa geométrica, cálculo dos coeficientes convectivos, coeficiente global limpo e sujo, área requerida, área disponível e critérios de verificação.