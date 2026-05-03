A equação mostrada é a **eficiência adiabática (ou isentrópica) do compressor** escrita em função do **expoente politrópico (n)** e do **expoente adiabático (k)**.

A ideia da dedução é **comparar o trabalho real de compressão (politrópico)** com o **trabalho ideal de compressão (isentrópico)** para a **mesma razão de pressões**.

---

# 1. Definição de eficiência adiabática do compressor

Para compressores, a eficiência isentrópica é definida como

$$  
\eta_{ad} = \frac{w_s}{w_{real}}  
$$

onde

- (w_s) = trabalho da compressão **isentropica (ideal)**
    
- (w_{real}) = trabalho da compressão **real (politrópica)**
    

---

# 2. Trabalho de compressão isentrópica

Para gás ideal em compressão isentrópica:

$$  
PV^k = \text{constante}  
$$

O trabalho específico pode ser escrito como

$$  
w_s = \frac{k}{k-1} RT_s  
\left[  
\left(\frac{P_d}{P_s}\right)^{\frac{k-1}{k}} - 1  
\right]  
$$

onde

- (k=\frac{c_p}{c_v})
    

---

# 3. Trabalho de compressão politrópica (processo real)

Para compressão politrópica:

$$  
PV^n = \text{constante}  
$$

o trabalho específico é

$$  
w_{real} =  
\frac{n}{n-1} RT_s  
\left[  
\left(\frac{P_d}{P_s}\right)^{\frac{n-1}{n}} - 1  
\right]  
$$

---

# 4. Substituindo na definição de eficiência

Substituindo os trabalhos:

$$  
\eta_{ad}

\frac{  
\frac{k}{k-1}RT_s  
\left[  
\left(\frac{P_d}{P_s}\right)^{\frac{k-1}{k}} - 1  
\right]  
}{  
\frac{n}{n-1}RT_s  
\left[  
\left(\frac{P_d}{P_s}\right)^{\frac{n-1}{n}} - 1  
\right]  
}  
$$

---

# 5. Cancelando termos comuns

Cancelando (RT_s):

$$  
\eta_{ad}

\frac{\frac{k}{k-1}}{\frac{n}{n-1}}  
\cdot  
\frac{  
\left(\frac{P_d}{P_s}\right)^{\frac{k-1}{k}} - 1  
}{  
\left(\frac{P_d}{P_s}\right)^{\frac{n-1}{n}} - 1  
}  
$$

---

# 6. Simplificando os coeficientes

Sabendo que

$$  
\frac{\frac{k}{k-1}}{\frac{n}{n-1}}

\frac{k(n-1)}{n(k-1)}  
$$

então

$$  
\eta_{ad}

\frac{k(n-1)}{n(k-1)}  
\cdot  
\frac{  
\left(\frac{P_d}{P_s}\right)^{\frac{k-1}{k}} - 1  
}{  
\left(\frac{P_d}{P_s}\right)^{\frac{n-1}{n}} - 1  
}  
$$

---

# 7. Forma apresentada no slide

A forma frequentemente usada em livros de **turbomáquinas e compressores** é

$$  
\eta_{ad} =  
\frac{  
\left(\frac{P_d}{P_s}\right)^{\frac{k-1}{k}} - 1  
}{  
\left(\frac{P_d}{P_s}\right)^{\frac{n-1}{n}} - 1  
}  
$$

que corresponde exatamente à equação da sua figura.

---

# 8. Significado físico

Essa relação mostra que a eficiência depende de:

### razão de compressão

$$  
\frac{P_d}{P_s}  
$$

### comportamento termodinâmico

- (k) → compressão ideal isentrópica
    
- (n) → compressão real
    

Quando

$$  
n \to k  
$$

então

$$  
\eta_{ad} \to 1  
$$

ou seja, o processo real se aproxima do ideal.

---

💡 **Dica para aula:**  
Essa equação fica muito mais clara quando o aluno vê **três curvas no diagrama (P!-!V)**:

- isotérmica
    
- politrópica
    
- adiabática
    

Se quiser, posso também montar **um slide didático mostrando exatamente essas três curvas**, que é uma das figuras mais usadas em aulas de compressores.