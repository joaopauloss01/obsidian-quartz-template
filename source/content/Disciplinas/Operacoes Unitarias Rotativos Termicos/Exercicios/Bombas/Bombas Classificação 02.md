Para uma **aula de Engenharia Química sobre bombas**, uma forma muito didática é apresentar **três camadas de classificação ao mesmo tempo**:

1. **Princípio de funcionamento**
    
2. **Tipo de fluido**
    
3. **Faixa típica de vazão e pressão**
    

Isso cria um **mapa visual de seleção de bombas**, que é exatamente o que engenheiros fazem no projeto de processos. Em provas e projetos de dimensionamento, geralmente o aluno precisa relacionar **curva da bomba, carga manométrica e vazão** com o sistema hidráulico.

Vou organizar de forma que você consiga **transformar diretamente em slides**.

---

# 1. Classificação geral das bombas (visão de engenharia)

A classificação fundamental é:

```
Bombas
│
├── Deslocamento Positivo
│   ├── Alternativas
│   └── Rotativas
│
└── Bombas Dinâmicas
    ├── Centrífugas
    ├── Axiais
    └── Mistas
```

### Diferença física fundamental

**Bombas de deslocamento positivo**

- deslocam **volume fixo por ciclo**
    
- vazão praticamente independente da pressão
    
- usadas para **altas pressões e baixas vazões**
    

**Bombas dinâmicas**

- transferem energia cinética ao fluido
    
- vazão depende da curva da bomba
    
- usadas para **altas vazões e pressões moderadas**
    

---

# 2. Tabela comparativa (didática para aula)

|Tipo de bomba|Princípio|Vazão típica|Pressão típica|Tipo de fluido|Aplicações|
|---|---|---|---|---|---|
|**Centrífuga**|Energia cinética → pressão|1 – 50.000 m³/h|1 – 200 m|baixa viscosidade|água, solventes|
|**Axial**|Impulsão axial|500 – 200.000 m³/h|1 – 20 m|líquidos limpos|irrigação, drenagem|
|**Fluxo misto**|radial + axial|100 – 50.000 m³/h|5 – 100 m|líquidos pouco viscosos|sistemas industriais|
|**Pistão / êmbolo**|deslocamento alternativo|0.01 – 500 m³/h|até 1000 bar|líquidos limpos|alta pressão|
|**Diafragma**|membrana flexível|0.01 – 200 m³/h|até 80 bar|corrosivos, tóxicos|indústria química|
|**Engrenagem**|deslocamento rotativo|0.1 – 100 m³/h|até 200 bar|viscosos|óleos|
|**Parafuso**|rotor helicoidal|1 – 5000 m³/h|até 150 bar|muito viscosos|petróleo|
|**Lóbulos**|rotores lobulares|1 – 500 m³/h|até 30 bar|fluidos sensíveis|alimentos|

---

# 3. Classificação quanto ao tipo de fluido

### Fluido de baixa viscosidade

( μ < 10 cP )

Bombas recomendadas:

- centrífugas
    
- axiais
    
- fluxo misto
    

Aplicações:

- água
    
- solventes
    
- hidrocarbonetos leves
    

---

### Fluido viscoso

( μ > 100 cP )

Bombas recomendadas:

- engrenagem
    
- parafuso
    
- cavidade progressiva
    

Aplicações:

- óleo lubrificante
    
- polímeros
    
- mel
    
- petróleo pesado
    

---

### Fluidos com sólidos

Bombas recomendadas:

- diafragma
    
- cavidade progressiva
    
- centrífuga especial
    

Aplicações:

- polpas minerais
    
- lodo
    
- efluentes
    

---

### Fluidos sensíveis ao cisalhamento

Bombas recomendadas:

- lóbulos
    
- cavidade progressiva
    
- diafragma
    

Aplicações:

- alimentos
    
- biotecnologia
    
- farmacêutica
    

---

# 4. Mapa visual (excelente para slide)

Uma forma extremamente didática é usar **gráfico Vazão × Pressão**.

```
Pressão
  ↑

  | Pistão
  |      Diafragma
  |           Engrenagem
  |                Parafuso
  |                        Centrífuga multistágio
  |
  |-------------------------------→ Vazão
            Centrífuga
                  Fluxo misto
                         Axial
```

Interpretação:

- **Bombas de deslocamento positivo → alta pressão**
    
- **Bombas dinâmicas → alta vazão**
    

---

# 5. Classificação quanto à aplicação industrial

|Aplicação|Tipo de bomba|
|---|---|
|Abastecimento de água|centrífuga|
|Processos químicos|centrífuga, diafragma|
|Dosagem de reagentes|pistão ou diafragma|
|Indústria alimentícia|lóbulos|
|Petróleo pesado|parafuso|
|Polpas minerais|centrífuga slurry|
|Alta pressão (hidrojateamento)|pistão|

---

# 6. Faixas típicas usadas em engenharia de processos

### Bombas centrífugas

Altura manométrica

$$  
H = 5 ; a ; 200 , m  
$$

Vazão

$$  
Q = 1 ; a ; 50000 , m^3/h  
$$

---

### Bombas de pistão

Pressão

$$  
P = 10 ; a ; 1000 , bar  
$$

Vazão

$$  
Q < 500 , m^3/h  
$$

---

### Bombas de parafuso

Pressão

$$  
P = 5 ; a ; 150 , bar  
$$

Vazão

$$  
Q = 1 ; a ; 5000 , m^3/h  
$$

---

# 7. Fluxograma de seleção de bombas (excelente para aula)

```
Qual é a viscosidade do fluido?

↓ baixa viscosidade
   bomba centrífuga

↓ média viscosidade
   engrenagem ou parafuso

↓ alta viscosidade
   cavidade progressiva

Há sólidos?

↓ sim
   diafragma / slurry

↓ não
   continuar

Pressão requerida > 100 bar?

↓ sim
   pistão

↓ não
   centrífuga
```

---

💡 **Dica pedagógica muito forte**

Uma forma que funciona muito bem em aula é apresentar **este gráfico clássico**:

```
Altura manométrica vs Vazão
```

com:

- centrífuga
    
- pistão
    
- parafuso
    
- axial
    

Isso ajuda o aluno a **visualizar a seleção da bomba em projeto de processo**.

---

✅ Se quiser, posso também te entregar:

1️⃣ **Um slide profissional pronto com gráficos de seleção de bombas**  
2️⃣ **Um gráfico Vazão × Pressão comparando todos os tipos de bomba** (muito usado em livros como Coulson & Richardson e Perry)  
3️⃣ **Uma tabela completa de seleção de bombas usada na indústria química**

que normalmente vira **um dos melhores slides da aula de máquinas de fluxo.**