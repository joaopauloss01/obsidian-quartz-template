Sim. Vou resolver assumindo o procedimento padrão para **o mesmo compressor operando com o mesmo gás e mesmas condições de sucção**, usando:

- **eficiência politrópica constante**,
    
- **similaridade de compressores**,
    
- **gás ideal com $Z=1$**.
    

---

# 1. Dados do problema

## Dados de operação inicial

$$  
N_1 = 8100 \ \text{rpm}  
$$

$$  
M = 28{,}97 \ \text{kg/kmol}  
$$

$$  
Z=1  
$$

$$  
k=\frac{c_p}{c_v}=1{,}4  
$$

$$  
P_{mot,1}=1267{,}6 \ \text{kW}  
$$

$$  
\eta_p=0{,}76  
$$

$$  
T_s=305{,}4 \ \text{K}  
$$

$$  
P_s=100 \ \text{kPa}  
$$

$$  
P_{d,1}=379 \ \text{kPa}  
$$

$$  
\dot V_1=311{,}5 \ \text{m}^3/\text{min}  
$$

## Nova condição desejada

$$  
P_{d,2}=413{,}7 \ \text{kPa}  
$$

## Limites operacionais

$$  
T_{max}=525 \ \text{K}  
$$

$$  
P_{max}=450 \ \text{kPa}  
$$

$$  
N_{max}=10800 \ \text{rpm}  
$$

$$  
N_{min}=4800 \ \text{rpm}  
$$

---

# 2. Equações usadas

## 2.1 Relação entre eficiência politrópica e expoente politrópico

Para compressor:

$$  
\eta_p=\frac{(k-1)/k}{(n-1)/n}  
$$

Logo,

$$  
\frac{n-1}{n}=\frac{(k-1)/k}{\eta_p}  
$$

---

## 2.2 Head politrópico

Para gás ideal:

$$  
H_p=  
\frac{n}{n-1}\frac{ZRT_s}{gM}  
\left[  
\left(\frac{P_d}{P_s}\right)^{\frac{n-1}{n}}-1  
\right]  
$$

Como é o **mesmo compressor**, vale a lei de similaridade:

$$  
H_p \propto N^2  
$$

então

$$  
\frac{N_2}{N_1}=\sqrt{\frac{H_{p,2}}{H_{p,1}}}  
$$

---

## 2.3 Potência

Para o mesmo compressor:

$$  
P \propto N^3  
$$

Logo,

$$  
\frac{P_{mot,2}}{P_{mot,1}}=  
\left(\frac{N_2}{N_1}\right)^3  
$$

---

## 2.4 Temperatura de descarga

Na compressão politrópica:

$$  
\frac{T_d}{T_s}=  
\left(\frac{P_d}{P_s}\right)^{\frac{n-1}{n}}  
$$

---

# 3. Resolução em Python

```python
import math

# =========================
# Dados
# =========================
N1 = 8100.0                 # rpm
M = 28.97                   # kg/kmol
Z = 1.0
k = 1.4
eta_p = 0.76
Pmot1 = 1267.6              # kW

Ts = 305.4                  # K
Ps = 100.0e3                # Pa
Pd1 = 379.0e3               # Pa
Pd2 = 413.7e3               # Pa

Q1 = 311.5 / 60.0           # m^3/s

Tmax = 525.0                # K
Pmax = 450.0e3              # Pa
Nmax = 10800.0              # rpm
Nmin = 4800.0               # rpm

Ru = 8314.462618            # J/(kmol.K)
g = 9.80665                 # m/s^2

# =========================
# 1) Calculando n a partir de eta_p
# eta_p = ((k-1)/k) / ((n-1)/n)
# =========================
a = ((k - 1.0) / k) / eta_p     # a = (n-1)/n
n = 1.0 / (1.0 - a)

# =========================
# 2) Funções auxiliares
# =========================
def head_politropico(Pd, Ps, Ts, n, Z, M):
    return (n / (n - 1.0)) * (Z * Ru * Ts) / (g * M) * ((Pd / Ps)**((n - 1.0) / n) - 1.0)

def temperatura_descarga(Pd, Ps, Ts, n):
    return Ts * (Pd / Ps)**((n - 1.0) / n)

# =========================
# 3) Heads na condição inicial e nova
# =========================
H1 = head_politropico(Pd1, Ps, Ts, n, Z, M)
H2 = head_politropico(Pd2, Ps, Ts, n, Z, M)

# =========================
# 4) Nova rotação pela lei H ~ N^2
# =========================
N2 = N1 * math.sqrt(H2 / H1)

# =========================
# 5) Nova potência pela lei P ~ N^3
# =========================
Pmot2 = Pmot1 * (N2 / N1)**3

# =========================
# 6) Temperatura de descarga
# =========================
Td1 = temperatura_descarga(Pd1, Ps, Ts, n)
Td2 = temperatura_descarga(Pd2, Ps, Ts, n)

# =========================
# 7) Vazão nova (opcional), usando Q ~ N
# =========================
Q2 = Q1 * (N2 / N1)         # m^3/s
Q2_min = Q2 * 60.0          # m^3/min

# =========================
# 8) Verificação dos limites
# =========================
ok_temp = Td2 <= Tmax
ok_press = Pd2 <= Pmax
ok_rot_max = N2 <= Nmax
ok_rot_min = N2 >= Nmin

# =========================
# Resultados
# =========================
print(f"Expoente politrópico n = {n:.6f}")
print(f"Head inicial H1 = {H1:.2f} m")
print(f"Head novo    H2 = {H2:.2f} m")
print(f"Nova rotação N2 = {N2:.2f} rpm")
print(f"Nova potência motriz = {Pmot2:.2f} kW")
print(f"Temperatura inicial de descarga = {Td1:.2f} K")
print(f"Temperatura nova de descarga    = {Td2:.2f} K")
print(f"Nova vazão volumétrica = {Q2_min:.2f} m^3/min")
print()
print("Limites operacionais:")
print(f"Temperatura: {'OK' if ok_temp else 'NÃO OK'}")
print(f"Pressão:     {'OK' if ok_press else 'NÃO OK'}")
print(f"Rotação max: {'OK' if ok_rot_max else 'NÃO OK'}")
print(f"Rotação min: {'OK' if ok_rot_min else 'NÃO OK'}")
```

---

# 4. Cálculo passo a passo

## 4.1 Expoente politrópico $n$

Da relação:

$$  
\eta_p=\frac{(k-1)/k}{(n-1)/n}  
$$

temos:

$$  
\frac{n-1}{n}=\frac{(1{,}4-1)/1{,}4}{0{,}76}  
$$

$$  
\frac{n-1}{n}=0{,}37594  
$$

Logo:

$$  
n=\frac{1}{1-0{,}37594}=1{,}6024  
$$

---

## 4.2 Head inicial

$$  
H_{p,1}=  
\frac{n}{n-1}\frac{ZRT_s}{gM}  
\left[  
\left(\frac{P_{d,1}}{P_s}\right)^{\frac{n-1}{n}}-1  
\right]  
$$

Substituindo:

$$  
H_{p,1}\approx 15458{,}06 \ \text{m}  
$$

---

## 4.3 Head novo

$$  
H_{p,2}=  
\frac{n}{n-1}\frac{ZRT_s}{gM}  
\left[  
\left(\frac{P_{d,2}}{P_s}\right)^{\frac{n-1}{n}}-1  
\right]  
$$

$$  
H_{p,2}\approx 16771{,}67 \ \text{m}  
$$

---

## 4.4 Nova rotação

Como

$$  
\frac{N_2}{N_1}=\sqrt{\frac{H_{p,2}}{H_{p,1}}}  
$$

então

$$  
N_2=8100\sqrt{\frac{16771{,}67}{15458{,}06}}  
$$

$$  
N_2\approx 8437{,}15 \ \text{rpm}  
$$

---

## 4.5 Nova potência motriz

Usando

$$  
P \propto N^3  
$$

temos:

$$  
P_{mot,2}=P_{mot,1}\left(\frac{N_2}{N_1}\right)^3  
$$

$$  
P_{mot,2}=1267{,}6\left(\frac{8437{,}15}{8100}\right)^3  
$$

$$  
P_{mot,2}\approx 1432{,}56 \ \text{kW}  
$$

---

## 4.6 Nova temperatura de descarga

Pela relação politrópica:

$$  
\frac{T_{d,2}}{T_s}=  
\left(\frac{P_{d,2}}{P_s}\right)^{\frac{n-1}{n}}  
$$

$$  
T_{d,2}=305{,}4\left(\frac{413{,}7}{100}\right)^{0{,}37594}  
$$

$$  
T_{d,2}\approx 520{,}84 \ \text{K}  
$$

---

# 5. Verificação dos limites operacionais

## Temperatura

$$  
T_{d,2}=520{,}84 \ \text{K} < 525 \ \text{K}  
$$

**Atende**.

## Pressão

$$  
P_{d,2}=413{,}7 \ \text{kPa} < 450 \ \text{kPa}  
$$

**Atende**.

## Rotação máxima

$$  
N_2=8437{,}15 \ \text{rpm} < 10800 \ \text{rpm}  
$$

**Atende**.

## Rotação mínima

$$  
N_2=8437{,}15 \ \text{rpm} > 4800 \ \text{rpm}  
$$

**Atende**.

---

# 6. Resposta final

A nova condição de operação exige aproximadamente:

$$  
\boxed{N_2 \approx 8437 \ \text{rpm}}  
$$

e a nova potência motriz é:

$$  
\boxed{P_{mot,2} \approx 1432{,}6 \ \text{kW}}  
$$

A nova temperatura de descarga é:

$$  
\boxed{T_{d,2} \approx 520{,}8 \ \text{K}}  
$$

Portanto, **todos os limites operacionais permanecem válidos** na nova condição:

- temperatura: **ok**
    
- pressão: **ok**
    
- rotação máxima: **ok**
    
- rotação mínima: **ok**
    

Observação importante: se você calcular a **potência no gás** a partir de $\dot m , w_p$, obterá um valor menor que a potência motriz do motor. Isso é normal, porque a potência motriz inclui perdas mecânicas e eletromecânicas. Por isso, para responder o que foi pedido aqui, a forma mais consistente é escalar a **potência motriz medida** com a lei:

$$  
P \propto N^3  
$$

