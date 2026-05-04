# 1. Modelo de Blasius

A equação adimensional é:

$$  
f''' + \frac{1}{2}\cdot f\cdot f'' = 0  
$$

com condições de contorno:

$$  
f(0)=0  
$$

$$  
f'(0)=0  
$$

$$  
f'(\infty)=1  
$$

Fisicamente:

$$  
\frac{u}{U_\infty}=f'(\eta)  
$$

onde $\eta$ é a coordenada de similaridade.

Como não podemos integrar até $\eta=\infty$, usamos um valor grande, por exemplo:

$$  
\eta_{\max}=8  
$$

## 2. Redução para sistema de 1ª ordem

Defina:

$$  
y_1=f  
$$

$$  
y_2=f'  
$$

$$  
y_3=f''  
$$

Então:

$$  
y_1'=y_2  
$$

$$  
y_2'=y_3  
$$

$$  
y_3'=-\frac{1}{2}\cdot y_1\cdot y_3  
$$

As condições ficam:

$$  
y_1(0)=0  
$$

$$  
y_2(0)=0  
$$

$$  
y_2(\eta_{\max})=1  
$$

O valor desconhecido é:

$$  
y_3(0)=f''(0)=s  
$$

O método de tiro consiste em ajustar $s$ até que:

$$  
f'(\eta_{\max})-1=0  
$$

## 3. Código MATLAB usando `ode45` + `fzero`

```matlab
clear; clc; close all

etamax = 8;

% Chute inicial para f''(0)
s0 = 0.3;

% Encontra s tal que f'(etamax) = 1
s = fzero(@(s) residuo_blasius(s, etamax), s0);

fprintf("f''(0) = %.8f\n", s)

% Resolve novamente com o valor correto de s
eta_span = [0 etamax];
y0 = [0; 0; s];

[eta, y] = ode45(@blasius_ode, eta_span, y0);

f      = y(:,1);
fp     = y(:,2);
fpp    = y(:,3);

figure
plot(eta, fp, 'LineWidth', 2)
grid on
xlabel('\eta')
ylabel("f'(\eta) = u/U_\infty")
title('Perfil de velocidade da camada limite de Blasius')

figure
plot(eta, fpp, 'LineWidth', 2)
grid on
xlabel('\eta')
ylabel("f''(\eta)")
title('Derivada segunda da solução de Blasius')

function dydeta = blasius_ode(eta, y)

    dydeta = zeros(3,1);

    dydeta(1) = y(2);
    dydeta(2) = y(3);
    dydeta(3) = -0.5*y(1)*y(3);

end

function R = residuo_blasius(s, etamax)

    eta_span = [0 etamax];
    y0 = [0; 0; s];

    [~, y] = ode45(@blasius_ode, eta_span, y0);

    fp_final = y(end,2);

    R = fp_final - 1;

end
```

O resultado esperado é aproximadamente:

$$  
f''(0)\approx 0{,}33206  
$$

Esse valor é importante porque está diretamente ligado ao cisalhamento na parede.

## 4. Interpretação física

A condição $f'(0)=0$ representa não deslizamento na parede:

$$  
u=0  
$$

A condição $f'(\infty)=1$ representa que longe da placa o fluido recupera a velocidade externa:

$$  
u=U_\infty  
$$

A função $f'(\eta)$ é o perfil adimensional de velocidade.

## 5. Alternativa com `bvp4c`

Como Blasius é naturalmente um problema de valor de contorno, também podemos resolver com `bvp4c`:

```matlab
clear; clc; close all

etamax = 8;
eta = linspace(0, etamax, 100);

solinit = bvpinit(eta, @chute_inicial);

sol = bvp4c(@blasius_ode, @blasius_bc, solinit);

eta_plot = linspace(0, etamax, 300);
y = deval(sol, eta_plot);

figure
plot(eta_plot, y(2,:), 'LineWidth', 2)
grid on
xlabel('\eta')
ylabel("f'(\eta) = u/U_\infty")
title('Solução de Blasius com bvp4c')

fprintf("f''(0) = %.8f\n", y(3,1))

function dydeta = blasius_ode(eta, y)

    dydeta = zeros(3,1);

    dydeta(1) = y(2);
    dydeta(2) = y(3);
    dydeta(3) = -0.5*y(1)*y(3);

end

function res = blasius_bc(ya, yb)

    res = [ ya(1);
            ya(2);
            yb(2) - 1 ];

end

function y = chute_inicial(eta)

    y = [ eta;
          1 - exp(-eta);
          exp(-eta) ];

end
```

## 6. Qual método usar?

Para fins didáticos, eu começaria com `ode45` + `fzero`, porque mostra claramente como uma EDO de 3ª ordem vira um sistema de EDOs de 1ª ordem.

Para aplicação direta em problemas de contorno, `bvp4c` é mais natural. O próprio Chapra organiza EDOs em problemas de valor inicial, métodos adaptativos e problemas de valor de contorno, incluindo método de tiro e `bvp4c`.