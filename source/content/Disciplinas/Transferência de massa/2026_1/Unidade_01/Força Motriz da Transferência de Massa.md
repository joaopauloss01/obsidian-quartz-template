---

# 📘 Força Motriz da Transferência de Massa

## Dedução Formal

---

## 1) Sistema isolado

Entropia total:

$$  
dS = dS_A + dS_B  
$$

---

## 2) Equação fundamental da termodinâmica

$$  
dU = T,dS - P,dV + \sum_i \mu_i,dn_i  
$$

Isolando ( dS ):

$$  
dS = \frac{1}{T}\left(dU + P,dV - \sum_i \mu_i,dn_i \right)  
$$

---

## 3) Volume rígido (( dV = 0 ))

$$  
dS = \frac{1}{T}\left(dU - \sum_i \mu_i,dn_i \right)  
$$

---

## 4) Aplicando aos subsistemas

Para A:

$$  
dS_A = \frac{1}{T}\left(dU_A - \sum_i \mu_{iA},dn_{iA} \right)  
$$

Para B:

$$  
dS_B = \frac{1}{T}\left(dU_B - \sum_i \mu_{iB},dn_{iB} \right)  
$$

---

## 5) Entropia total

$$  
dS = \frac{1}{T}  
\left[  
dU_A + dU_B

- \sum_i \mu_{iA},dn_{iA}
    
- \sum_i \mu_{iB},dn_{iB}  
    \right]  
    $$
    

---

## 6) Sistema isolado

Energia total constante:

$$  
dU_A + dU_B = 0  
$$

ou

$$  
dU_A = -dU_B  
$$

Transferência de matéria:

$$  
dn_{iA} = -dn_{iB}  
$$

---

## 7) Substituindo

$$  
dS =  
\frac{1}{T}  
\sum_i  
dn_{iA}  
\left(  
\mu_{iB} - \mu_{iA}  
\right)  
$$

---

## 8) Condição de equilíbrio

No equilíbrio:

$$  
dS = 0  
$$

Logo:

$$  
\mu_{iA} = \mu_{iB}  
$$

ou

$$  
\Delta \mu_i = 0  
$$

---

## 9) Interpretação física

Se:

$$  
\mu_{iB} > \mu_{iA}  
$$

Então:

$$  
dn_{iA} > 0  
$$

A matéria flui da região de maior potencial químico para menor potencial químico.

---

## 10) Solução ideal

$$  
\mu_i = \mu_i^0 + RT \ln x_i  
$$

Diferenciando:

$$  
d\mu_i = RT, d(\ln x_i)  
$$

Como:

$$  
d(\ln x_i) = \frac{dx_i}{x_i}  
$$

Temos:

$$  
d\mu_i = RT,\frac{dx_i}{x_i}  
$$

Para soluções diluídas:

$$  
d\mu_i = RT,\frac{dC_i}{C_i}  
$$

---

## 11) Conexão com o fluxo

Gradiente de potencial químico:

$$  
\nabla \mu_i \neq 0  
$$

Fluxo proporcional:

$$  
J_i \propto -,\nabla \mu_i  
$$

---

## 12) Forma microscópica

$$  
J_{A,z} = -\frac{1}{3},\Omega,\lambda,\frac{dC_A}{dz}  
$$

Definindo:

$$  
D_{AA} = \frac{1}{3},\Omega,\lambda  
$$

---

## 13) Primeira Lei de Fick

$$  
J_{A,z} = -D_{AA},\frac{dC_A}{dz}  
$$

---

## Resultado conceitual final

$$  
\Delta \mu_i \neq 0  
\Rightarrow  
\nabla \mu_i \neq 0  
\Rightarrow  
J_i \neq 0  
$$

---

