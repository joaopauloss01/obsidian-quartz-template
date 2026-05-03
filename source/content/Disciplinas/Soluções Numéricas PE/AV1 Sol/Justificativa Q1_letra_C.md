---
---
## 🔍 Vamos olhar a equação do tanque 3

Do balanço de massa:

$$  
Q_{23} C_2 - (Q_{31} + Q_{33}) C_3 = 0  
$$

Mas pela definição das vazões:

$$  
Q_{33} = Q_{23} - Q_{31}  
$$

Substituindo:

$$  
Q_{31} + Q_{33} = Q_{31} + (Q_{23} - Q_{31}) = Q_{23}  
$$

Logo a equação vira:

$$  
Q_{23} C_2 - Q_{23} C_3 = 0  
$$

Dividindo por $Q_{23}$:

$$  
C_2 = C_3  
$$

---

## 💥 Conclusão importante

$$  
\boxed{C_2 = C_3 \quad \text{(sempre, independente de } Q_{31})}  
$$

---

## 🧠 Interpretação física (nível engenharia)

Isso acontece porque:

- O tanque 3 **não tem entrada independente**
    
- Ele recebe **exatamente o que sai do tanque 2**
    
- E a saída total dele é **igual à entrada total**
    

Ou seja:

👉 Não há “acúmulo diferencial” de composição  
👉 Não há mistura com outra corrente externa  
👉 Não há geração ou consumo

---

## 🔄 Papel do reciclo

Mesmo com reciclo:

- Parte do fluxo volta para o tanque 1
    
- Mas isso **não altera a igualdade entre $C_2$ e $C_3$**
    

Porque:

👉 O tanque 3 continua sendo apenas um “espelho” do tanque 2

---

## 📊 Então por que parecem constantes no gráfico?

Porque:

- $C_2 = C_3$ (sempre iguais)
    
- E ambos **variam pouco com $Q_{31}$**
    

Ou seja:

- não são exatamente constantes
    
- mas a variação é pequena → gráfico parece plano
    

---

## ⚠️ Insight avançado (nível PHD)

Esse sistema tem uma propriedade estrutural:

👉 **dependência linear entre equações**

A equação do tanque 3 não traz nova informação independente — ela impõe uma restrição:

$$  
C_2 - C_3 = 0  
$$

Isso reduz efetivamente o sistema para **2 graus de liberdade reais**.

---

Se quiser, posso te mostrar:

👉 como reduzir o sistema para 2 equações  
👉 ou provar analiticamente como $C_1$ depende de $Q_{31}$

Isso já entra num nível bem mais avançado de modelagem.