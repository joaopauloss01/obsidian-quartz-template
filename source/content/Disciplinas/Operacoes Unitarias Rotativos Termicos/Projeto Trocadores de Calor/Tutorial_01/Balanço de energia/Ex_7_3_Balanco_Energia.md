Sim. Pelo balanço, usando os valores do livro:

$$  
\dot{Q}_h=\dot{m}_h\cdot c_{p,h}\cdot \left(T_{h,i}-T_{h,o}\right)  
$$

$$  
\dot{Q}_h=43800\cdot 0{,}605\cdot \left(390-200\right)  
$$

$$  
\dot{Q}_h=5{,}035{,}710\ \text{Btu/h}  
$$

Para o frio:

$$  
\dot{Q}_c=\dot{m}_c\cdot c_{p,c}\cdot \left(T_{c,o}-T_{c,i}\right)  
$$

$$  
\dot{Q}_c=149000\cdot 0{,}49\cdot \left(170-100\right)  
$$

$$  
\dot{Q}_c=5{,}110{,}700\ \text{Btu/h}  
$$

A diferença é:

$$  
\Delta \dot{Q}=5{,}110{,}700-5{,}035{,}710  
$$

$$  
\Delta \dot{Q}=74{,}990\ \text{Btu/h}  
$$

Erro relativo em relação ao quente:

$$  
\varepsilon=\frac{74{,}990}{5{,}035{,}710}\cdot 100  
$$

$$  
\varepsilon\approx 1{,}49%  
$$

Então sim: **não fecha exatamente**, mas a diferença é pequena. Para fechar o balanço, podemos corrigir uma temperatura de saída.

Corrigindo a saída do óleo cru:

$$  
T_{c,o}=T_{c,i}+\frac{\dot{Q}_h}{\dot{m}_c\cdot c_{p,c}}  
$$

$$  
T_{c,o}=100+\frac{5{,}035{,}710}{149000\cdot 0{,}49}  
$$

$$  
T_{c,o}=168{,}97^\circ F  
$$

Então, em vez de $170^\circ F$, usaríamos:

$$  
T_{c,o}\approx 169^\circ F  
$$

Ou corrigindo a saída da querosene:

$$  
T_{h,o}=T_{h,i}-\frac{\dot{Q}_c}{\dot{m}_h\cdot c_{p,h}}  
$$

$$  
T_{h,o}=390-\frac{5{,}110{,}700}{43800\cdot 0{,}605}  
$$

$$  
T_{h,o}=197{,}17^\circ F  
$$

Então, em vez de $200^\circ F$, usaríamos:

$$  
T_{h,o}\approx 197^\circ F  
$$

Para seguir o exemplo do Kern com mínima alteração, eu corrigiria o óleo cru para:

$$  
T_{c,o}=169^\circ F  
$$