
---

# Gabarito comentado — Compressor usando **head adiabático**

## Dados

$$  
N_1=8100\ \text{rpm}  
$$

$$  
M=28{,}97\ \text{kg/kmol}  
$$

$$  
Z=1  
$$

$$  
k=1{,}4  
$$

$$  
\eta_p=0{,}76  
$$

$$  
P_{mot,1}=1267{,}6\ \text{kW}  
$$

$$  
T_s=305{,}4\ \text{K}  
$$

$$  
P_s=100\ \text{kPa}  
$$

$$  
P_{d,1}=379\ \text{kPa}  
$$

$$  
P_{d,2}=413{,}7\ \text{kPa}  
$$

Limites operacionais:

$$  
T_{max}=525\ \text{K}  
$$

$$  
P_{max}=450\ \text{kPa}  
$$

$$  
N_{max}=10800\ \text{rpm}  
$$

$$  
N_{min}=4800\ \text{rpm}  
$$

---

## 1) Equação do head adiabático

Para gás ideal, o head adiabático é dado por:

$$  
H_{ad}=  
\frac{k}{k-1}\frac{ZRT_s}{gM}  
\left[  
\left(\frac{P_d}{P_s}\right)^{\frac{k-1}{k}}-1  
\right]  
$$

Como se trata da **mesma máquina**, vale a condição de similaridade:

$$  
H_{ad}\propto N^2  
$$

portanto,

$$  
\frac{H_{ad,2}}{H_{ad,1}}=\left(\frac{N_2}{N_1}\right)^2  
$$

e

$$  
N_2=N_1\sqrt{\frac{H_{ad,2}}{H_{ad,1}}}  
$$

---

## 2) Cálculo do head adiabático inicial

Para a condição inicial:

$$  
H_{ad,1}=  
\frac{1{,}4}{1{,}4-1}\frac{(1)(8314{,}4626)(305{,}4)}{(9{,}80665)(28{,}97)}  
\left[  
\left(\frac{379}{100}\right)^{\frac{0{,}4}{1{,}4}}-1  
\right]  
$$

$$  
H_{ad,1}\approx 14492{,}37\ \text{m}  
$$

---

## 3) Cálculo do novo head adiabático

Para a nova pressão de descarga:

$$  
H_{ad,2}=  
\frac{1{,}4}{1{,}4-1}\frac{(1)(8314{,}4626)(305{,}4)}{(9{,}80665)(28{,}97)}  
\left[  
\left(\frac{413{,}7}{100}\right)^{\frac{0{,}4}{1{,}4}}-1  
\right]  
$$

$$  
H_{ad,2}\approx 15652{,}58\ \text{m}  
$$

---

## 4) Nova rotação do compressor

Aplicando a similaridade:

$$  
N_2=8100\sqrt{\frac{15652{,}58}{14492{,}37}}  
$$

$$  
N_2\approx 8417{,}99\ \text{rpm}  
$$

Assim,

$$  
\boxed{N_2\approx 8418\ \text{rpm}}  
$$

---

## 5) Nova potência motriz

Para a mesma máquina:

$$  
P\propto N^3  
$$

Logo,

$$  
P_{mot,2}=P_{mot,1}\left(\frac{N_2}{N_1}\right)^3  
$$

Substituindo:

$$  
P_{mot,2}=1267{,}6\left(\frac{8417{,}99}{8100}\right)^3  
$$

$$  
P_{mot,2}\approx 1422{,}83\ \text{kW}  
$$

Portanto,

$$  
\boxed{P_{mot,2}\approx 1422{,}8\ \text{kW}}  
$$

---

## 6) Verificação da temperatura de descarga

Para verificar o limite térmico, calcula-se a temperatura real de descarga pelo processo politrópico.

### 6.1 Expoente politrópico

Da relação:

$$  
\eta_p=\frac{(k-1)/k}{(n-1)/n}  
$$

tem-se:

$$  
\frac{n-1}{n}=\frac{(1{,}4-1)/1{,}4}{0{,}76}  
$$

$$  
\frac{n-1}{n}=0{,}37594  
$$

Logo,

$$  
n=\frac{1}{1-0{,}37594}\approx 1{,}6024  
$$

### 6.2 Temperatura de descarga

$$  
T_{d,2}=T_s\left(\frac{P_{d,2}}{P_s}\right)^{\frac{n-1}{n}}  
$$

$$  
T_{d,2}=305{,}4\left(\frac{413{,}7}{100}\right)^{0{,}37594}  
$$

$$  
T_{d,2}\approx 520{,}84\ \text{K}  
$$

Como

$$  
520{,}84<525  
$$

o limite de temperatura é atendido.

---

## 7) Verificação dos demais limites

### Pressão máxima

$$  
P_{d,2}=413{,}7\ \text{kPa}<450\ \text{kPa}  
$$

Atende.

### Rotação máxima

$$  
8418<10800  
$$

Atende.

### Rotação mínima

$$  
8418>4800  
$$

Atende.

---

## 8) Resposta final

A nova rotação requerida para que o compressor atinja a pressão de descarga desejada, usando **head adiabático**, é:

$$  
\boxed{N_2\approx 8418\ \text{rpm}}  
$$

A nova potência motriz é:

$$  
\boxed{P_{mot,2}\approx 1422{,}8\ \text{kW}}  
$$

A nova temperatura de descarga é aproximadamente:

$$  
\boxed{T_{d,2}\approx 520{,}8\ \text{K}}  
$$

### Conclusão sobre os limites operacionais

Todos os limites permanecem válidos na nova condição:

- temperatura: **atende**
    
- pressão: **atende**
    
- rotação máxima: **atende**
    
- rotação mínima: **atende**
    

---

# Código em Python

```python
import math

# Dados
N1 = 8100.0
M = 28.97
Z = 1.0
k = 1.4
eta_p = 0.76
Pmot1 = 1267.6

Ts = 305.4
Ps = 100.0e3
Pd1 = 379.0e3
Pd2 = 413.7e3

Tmax = 525.0
Pmax = 450.0e3
Nmax = 10800.0
Nmin = 4800.0

Ru = 8314.462618
g = 9.80665

# Expoente politrópico
a = ((k - 1.0) / k) / eta_p
n = 1.0 / (1.0 - a)

def head_adiabatico(Pd, Ps, Ts, k, Z, M):
    return (k / (k - 1.0)) * (Z * Ru * Ts) / (g * M) * ((Pd / Ps)**((k - 1.0) / k) - 1.0)

def temperatura_descarga_politropica(Pd, Ps, Ts, n):
    return Ts * (Pd / Ps)**((n - 1.0) / n)

Had1 = head_adiabatico(Pd1, Ps, Ts, k, Z, M)
Had2 = head_adiabatico(Pd2, Ps, Ts, k, Z, M)

N2 = N1 * math.sqrt(Had2 / Had1)
Pmot2 = Pmot1 * (N2 / N1)**3
Td2 = temperatura_descarga_politropica(Pd2, Ps, Ts, n)

print(f"n = {n:.6f}")
print(f"Had1 = {Had1:.2f} m")
print(f"Had2 = {Had2:.2f} m")
print(f"N2 = {N2:.2f} rpm")
print(f"Pmot2 = {Pmot2:.2f} kW")
print(f"Td2 = {Td2:.2f} K")

print("\\nVerificação dos limites:")
print("Temperatura:", "OK" if Td2 <= Tmax else "NÃO OK")
print("Pressão:", "OK" if Pd2 <= Pmax else "NÃO OK")
print("Rotação máxima:", "OK" if N2 <= Nmax else "NÃO OK")
print("Rotação mínima:", "OK" if N2 >= Nmin else "NÃO OK")
```

