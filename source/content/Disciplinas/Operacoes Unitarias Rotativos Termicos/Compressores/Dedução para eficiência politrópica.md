Sim — essa relação vem da **comparação entre o trabalho de compressão adiabática (isentrópica)** e o **trabalho de compressão politrópica**, para um **gás ideal** submetido à **mesma razão de pressões**.

A relação mostrada é:

$$  
\eta_{pol}=\frac{(k-1)/k}{(n-1)/n}  
$$

ou, de forma equivalente,

$$  
\eta_{pol}=\frac{k-1}{k}\cdot\frac{n}{n-1}  
$$

em que:

- $k=\dfrac{c_p}{c_v}$ é o expoente adiabático (ou isentrópico),
    
- $n$ é o expoente politrópico.
    

---

# De onde essa dedução vem?

Ela nasce de três ideias:

1. **compressão de gás ideal**
    
2. **equação politrópica**  
    $$  
    PV^n=\text{cte}  
    $$
    
3. **comparação entre duas compressões com a mesma razão de pressão**  
    $$  
    \frac{P_2}{P_1}  
    $$
    

---

# 1. Trabalho de compressão politrópica

Para um processo politrópico:

$$  
PV^n=\text{cte}  
$$

O trabalho específico é:

$$  
w_{pol}=\int v,dP  
$$

ou, usando o desenvolvimento conhecido da compressão politrópica de gás ideal:

$$  
w_{pol}=\frac{n}{n-1}RT_1\left[\left(\frac{P_2}{P_1}\right)^{\frac{n-1}{n}}-1\right]  
$$

---

# 2. Trabalho de compressão adiabática (isentrópica)

Para uma compressão adiabática reversível:

$$  
PV^k=\text{cte}  
$$

e o trabalho específico fica:

$$  
w_s=\frac{k}{k-1}RT_1\left[\left(\frac{P_2}{P_1}\right)^{\frac{k-1}{k}}-1\right]  
$$

Esse é o trabalho ideal de compressão, também chamado de **isentrópico**.

---

# 3. Definição de eficiência politrópica

A forma mais usada dessa dedução parte da ideia de que a eficiência politrópica representa a eficiência de um **pequeno estágio diferencial** de compressão.

Para um incremento infinitesimal, define-se:

$$  
\eta_{pol}=\frac{dw_s}{dw_{real}}  
$$

No desenvolvimento clássico, isso leva à comparação entre a variação de temperatura isentrópica e a politrópica para um mesmo incremento de pressão.

---

# 4. Relações diferenciais de temperatura e pressão

Para um gás ideal em compressão politrópica:

$$  
PV^n=\text{cte}  
$$

Usando também:

$$  
PV=RT  
$$

podemos obter a relação entre temperatura e pressão:

$$  
\frac{T_2}{T_1}=\left(\frac{P_2}{P_1}\right)^{\frac{n-1}{n}}  
$$

No formato diferencial:

$$  
\frac{dT}{T}=\frac{n-1}{n}\frac{dP}{P}  
$$

Para a compressão isentrópica:

$$  
\frac{T_2}{T_1}=\left(\frac{P_2}{P_1}\right)^{\frac{k-1}{k}}  
$$

e, diferencialmente:

$$  
\frac{dT_s}{T}=\frac{k-1}{k}\frac{dP}{P}  
$$

---

# 5. Ligando isso à eficiência politrópica

Para um pequeno estágio de compressão, o trabalho específico é proporcional à variação de entalpia:

$$  
dw=c_p,dT  
$$

Para o caso isentrópico diferencial:

$$  
dw_s=c_p,dT_s  
$$

Para o caso real/politrópico:

$$  
dw_{pol}=c_p,dT  
$$

Logo, pela definição de eficiência politrópica:

$$  
\eta_{pol}=\frac{dw_s}{dw_{pol}}=\frac{c_p,dT_s}{c_p,dT}  
=\frac{dT_s}{dT}  
$$

Substituindo as relações diferenciais anteriores:

$$  
dT_s=T\frac{k-1}{k}\frac{dP}{P}  
$$

$$  
dT=T\frac{n-1}{n}\frac{dP}{P}  
$$

Então:

#
$$  
\eta_{pol}=\frac{dT_s}{dT}

\frac{T\frac{k-1}{k}\frac{dP}{P}}  
{T\frac{n-1}{n}\frac{dP}{P}}  
$$

Cancelando os termos comuns:

$$  
\eta_{pol}=  
\frac{(k-1)/k}{(n-1)/n}  
$$

que é exatamente a relação da sua imagem.

---

# 6. Resultado final

$$  
\boxed{  
\eta_{pol}=  
\frac{(k-1)/k}{(n-1)/n}  
}  
$$

ou ainda:

$$  
\boxed{  
\eta_{pol}=\frac{k-1}{k}\cdot\frac{n}{n-1}  
}  
$$

---

# 7. Interpretação física

Essa expressão mostra como o expoente politrópico $n$ se relaciona com a eficiência do processo:

- se $n \to k$, o processo se aproxima do adiabático reversível;
    
- quanto maior a irreversibilidade, maior tende a ser o afastamento entre $n$ e $k$;
    
- a eficiência politrópica mede quão próximo o processo real está de um processo ideal infinitesimal.
    

---

# 8. Observação importante

Essa dedução vale sob hipóteses como:

- gás ideal,
    
- $c_p$ aproximadamente constante,
    
- comparação entre compressão real e isentrópica para o mesmo incremento de pressão.
    

Por isso ela aparece muito em **turbomáquinas**, **compressores centrífugos** e **axiais**.

---

# 9. Forma útil para isolar $n$

Às vezes é útil rearranjar a equação para encontrar $n$ a partir de $\eta_{pol}$ e $k$:

$$  
\eta_{pol}=\frac{(k-1)/k}{(n-1)/n}  
$$

então:

$$  
\frac{n-1}{n}=\frac{k-1}{k,\eta_{pol}}  
$$

e daí pode-se obter $n$.

---
