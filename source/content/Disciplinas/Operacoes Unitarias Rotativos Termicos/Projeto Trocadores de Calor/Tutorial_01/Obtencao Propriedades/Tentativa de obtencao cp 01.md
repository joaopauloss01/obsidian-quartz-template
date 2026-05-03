Podemos sim. Para esse caso, eu testaria em **3 níveis**:

1. **Reproduzir Kern** com $c_p$ médio do livro.
    
2. **Usar CoolProp** para verificar se existe algum fluido incompressível próximo, como querosene ou óleo térmico. O CoolProp fornece $c_p$, $\rho$, $\mu$, $k$ e $h$ para fluidos incompressíveis, mas depende dos fluidos cadastrados ([CoolProp](https://coolprop.org/fluid_properties/Incompressibles.html?utm_source=chatgpt.com "Incompressible Fluids — CoolProp 7.2.0 documentation")).
    
3. **Usar correlação por °API** para frações de petróleo, que provavelmente será o caminho mais adequado para automatizar exercícios do Kern.
    

Começaria com este teste no Colab:

```python
!pip install CoolProp thermo chemicals -q
```

```python
from CoolProp.CoolProp import PropsSI
import CoolProp

# Lista de fluidos incompressíveis disponíveis no CoolProp
try:
    from CoolProp import __incompressibles_pure__
    print(__incompressibles_pure__)
except Exception as e:
    print("Não consegui listar incompressíveis:", e)
```

Depois testamos candidatos parecidos:

```python
from CoolProp.CoolProp import PropsSI

fluidos_teste = [
    "INCOMP::TCO",
    "INCOMP::T66",
    "INCOMP::T72",
    "INCOMP::DowQ",
    "INCOMP::TVP1",
    "INCOMP::Water"
]

T_F = 295  # temperatura média aproximada da querosene: (390 + 200)/2
T_K = (T_F - 32) * 5/9 + 273.15
P = 101325

for fluido in fluidos_teste:
    try:
        cp = PropsSI("C", "T", T_K, "P", P, fluido)  # J/kg.K
        rho = PropsSI("D", "T", T_K, "P", P, fluido)
        mu = PropsSI("V", "T", T_K, "P", P, fluido)
        k = PropsSI("L", "T", T_K, "P", P, fluido)

        cp_btu = cp / 4186.8  # Btu/lb°F

        print(f"\n{fluido}")
        print(f"cp = {cp:.1f} J/kg.K = {cp_btu:.4f} Btu/lb°F")
        print(f"rho = {rho:.1f} kg/m³")
        print(f"mu = {mu:.6f} Pa.s")
        print(f"k = {k:.4f} W/m.K")

    except Exception as e:
        print(f"\n{fluido}: erro -> {e}")
```

E, em paralelo, fazemos a conversão API:

```python
def api_to_sg(API):
    return 141.5 / (API + 131.5)

API_querosene = 42
API_crudo = 34

SG_querosene = api_to_sg(API_querosene)
SG_crudo = api_to_sg(API_crudo)

print("SG querosene:", SG_querosene)
print("SG óleo cru:", SG_crudo)
```

Para comparar com Kern:

```python
m_h = 43800      # lb/h
m_c = 149000     # lb/h

cp_querosene_kern = 0.605  # Btu/lb°F
cp_crudo_kern = 0.49       # Btu/lb°F

Q_h = m_h * cp_querosene_kern * (390 - 200)
Q_c = m_c * cp_crudo_kern * (170 - 100)

print("Q querosene =", Q_h, "Btu/h")
print("Q óleo cru  =", Q_c, "Btu/h")
```

A ideia é verificar se algum fluido do CoolProp dá um $c_p$ próximo de:

$$  
c_{p,\text{querosene}}\approx 0{,}605\ \text{Btu}/\text{lb}\cdot{}^\circ\text{F}  
$$

e:

$$  
c_{p,\text{crudo}}\approx 0{,}49\ \text{Btu}/\text{lb}\cdot{}^\circ\text{F}  
$$

Se o CoolProp não representar bem, seguimos para uma função baseada em °API e temperatura. Isso tende a ser mais fiel ao método do Kern do que tentar forçar um fluido puro.