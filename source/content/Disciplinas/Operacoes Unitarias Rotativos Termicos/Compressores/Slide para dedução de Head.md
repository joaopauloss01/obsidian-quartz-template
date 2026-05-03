Abaixo está o material **estruturado diretamente em formato de slides em Markdown**, que funciona bem para gerar apresentações no **NotebookLM, Gamma, Marp ou HackMD**.  
Cada seção corresponde a **um slide**.

---

# Compressores — Dedução da Altura Manométrica

---

# Slide 1 — Compressores em Sistemas Térmicos

## Objetivo da análise

Aplicar a **Primeira Lei da Termodinâmica** ao escoamento em compressores para obter a expressão da **altura manométrica (Head)**.

### Motivação

Assim como em bombas:

- queremos relacionar **trabalho fornecido ao fluido**
    
- com **condições de sucção e descarga**
    

### Diferença fundamental

**Bombas**

- fluido incompressível
    

**Compressores**

- **gases compressíveis**
    

---

# Slide 2 — Primeira Lei para Escoamento Permanente

A equação geral de energia para escoamento permanente é

# $$  
\frac{\dot W}{\dot m g}

\frac{e_{pr}}{g}  
+  
\frac{v_d^2-v_s^2}{2g}  
+  
(z_d-z_s)  
+  
h_f  
$$

onde:

- $\dot W$ → potência do compressor
    
- $\dot m$ → vazão mássica
    
- $e_{pr}$ → termo de energia de pressão
    
- $v$ → velocidade do fluido
    
- $z$ → altura geométrica
    
- $h_f$ → perdas de carga
    

---

# Slide 3 — Diferença entre Bombas e Compressores

### Para líquidos (incompressível)

A densidade é constante:

# $$  
e_{pr} =  
\int_{P_1}^{P_2}\frac{dP}{\rho}

\frac{P_2-P_1}{\rho}  
$$

### Para gases (compressível)

A densidade **varia com a pressão**.

Logo:

$$  
e_{pr} =  
\int_{P_s}^{P_d}\frac{dP}{\rho}  
$$

Essa integral deve ser resolvida usando **relações termodinâmicas do gás**.

---

# Slide 4 — Processos de Compressão

Durante a compressão, podem ocorrer diferentes processos:

### Compressão isotérmica

$$  
PV = \text{constante}  
$$

### Compressão adiabática

$$  
PV^k = \text{constante}  
$$

onde

$$  
k = \frac{c_p}{c_v}  
$$

### Compressão politrópica (caso real)

$$  
PV^\delta = \text{constante}  
$$

Esse modelo descreve melhor **compressores reais**.

---

# Slide 5 — Relação entre Pressão e Densidade

Partindo da relação politrópica:

$$  
PV^\delta = C  
$$

Sabendo que:

$$  
V = \frac{m}{\rho}  
$$

Substituindo:

$$  
P\left(\frac{m}{\rho}\right)^\delta = C  
$$

Como a massa é constante:

$$  
\frac{P}{\rho^\delta} = C  
$$

---

# Slide 6 — Expressão da Densidade

Da relação anterior:

$$  
P = C\rho^\delta  
$$

Logo:

$$  
\rho = \rho_s\left(\frac{P}{P_s}\right)^{1/\delta}  
$$

Assim:

$$  
\frac{1}{\rho} =  
\frac{1}{\rho_s}  
\left(\frac{P_s}{P}\right)^{1/\delta}  
$$

---

# Slide 7 — Substituição na Integral de Pressão

O termo de energia de pressão é:

$$  
e_{pr} =  
\int_{P_s}^{P_d}\frac{dP}{\rho}  
$$

Substituindo a expressão da densidade:

$$  
e_{pr} =  
\frac{P_s^{1/\delta}}{\rho_s}  
\int_{P_s}^{P_d} P^{-1/\delta} dP  
$$

---

# Slide 8 — Integração

A integral é:

# $$  
\int P^{-1/\delta} dP

\frac{P^{1-\frac{1}{\delta}}}{1-\frac{1}{\delta}}  
$$

Como:

$$  
1-\frac{1}{\delta} = \frac{\delta-1}{\delta}  
$$

---

# Slide 9 — Resultado da Integração

Substituindo os limites da integral:

# $$  
e_{pr}

\frac{\delta}{\delta-1}  
\frac{P_s}{\rho_s}  
\left[  
\left(\frac{P_d}{P_s}\right)^{\frac{\delta-1}{\delta}}  
-1  
\right]  
$$

Esse é o **termo de energia de pressão para gases em compressão politrópica**.

---

# Slide 10 — Substituição na Primeira Lei

Substituindo na equação de energia:

# $$  
\frac{\dot W}{\dot m g}

\frac{1}{g}  
\frac{\delta}{\delta-1}  
\frac{P_s}{\rho_s}  
\left[  
\left(\frac{P_d}{P_s}\right)^{\frac{\delta-1}{\delta}}  
-1  
\right]  
+  
\frac{v_d^2-v_s^2}{2g}  
+  
(z_d-z_s)  
+  
h_f  
$$

---

# Slide 11 — Relação com a Equação dos Gases

Para gases reais:

$$  
PV = Z nRT  
$$

Logo:

$$  
\rho_s = \frac{m}{V}  
$$

Resultando em:

$$  
\frac{P_s}{\rho_s} =  
\frac{Z_sRT_s}{M}  
$$

onde:

- $Z_s$ → fator de compressibilidade
    
- $T_s$ → temperatura de sucção
    
- $M$ → massa molar
    

---

# Slide 12 — Equação Geral do Head do Compressor

Substituindo na equação de energia:

# $$  
\frac{\dot W}{\dot m g}

\frac{1}{g}  
\frac{\delta}{\delta-1}  
\frac{Z_sRT_s}{M}  
\left[  
\left(\frac{P_d}{P_s}\right)^{\frac{\delta-1}{\delta}}  
-1  
\right]  
+  
\frac{v_d^2-v_s^2}{2g}  
+  
(z_d-z_s)  
+  
h_f  
$$

---

# Slide 13 — Simplificações Práticas

Na maioria dos compressores industriais:

- variação de energia cinética pequena
    
- variação de altura pequena
    
- perdas relativamente pequenas
    

Assim:

$$  
\frac{v_d^2-v_s^2}{2g} \approx 0  
$$

$$  
z_d-z_s \approx 0  
$$

---

# Slide 14 — Expressão Simplificada do Head

Assim:

# $$  
H =  
\frac{\dot W}{\dot m g}

\frac{\delta}{\delta-1}  
\frac{Z_sRT_s}{gM}  
\left[  
\left(\frac{P_d}{P_s}\right)^{\frac{\delta-1}{\delta}}  
-1  
\right]  
$$

---

# Slide 15 — Interpretação Física

A altura manométrica do compressor:

- aumenta com **razão de compressão**
    

$$  
\frac{P_d}{P_s}  
$$

- aumenta com **temperatura de sucção**
    
- depende do **tipo de compressão**
    

$$  
\delta  
$$

- depende da **não idealidade do gás**
    

$$  
Z  
$$

---

# Slide 16 — Resultado Final

Altura manométrica do compressor:

$$  
H =  
\frac{\delta}{\delta-1}  
\frac{Z_sRT_s}{gM}  
\left[  
\left(\frac{P_d}{P_s}\right)^{\frac{\delta-1}{\delta}}  
-1  
\right]  
$$

Essa equação permite estimar o **trabalho específico necessário para compressão de gases**.

---

💡 Se quiser, posso também fazer **uma versão ainda melhor para aula**, incluindo:

- **slides conceituais**
    
- **diagramas de compressão P–V**
    
- **comparação bomba × compressor**
    
- **exemplo numérico de compressor**
    

que costuma deixar a aula **muito mais didática**.