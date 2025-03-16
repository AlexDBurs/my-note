---
title: 'Modelo Estructural PCE Merton'
draft: false
tags:
  - Nota
  - Metodología
---

#####  Estimación de la PD por Merton (metodo estructural basico)
La idea del método es que la equity (la acción) de las empresas, se puede interpretar como una opción donde el precio es la totalidad de activos y el strike son los pasivos. Esto hace que la estructura del capital sea la siguiente: Assets = Debt + Equity
**Se asume que el precio sigue una distribución log-normal y que el default ocure cuando el precio cae por debajo de la deuda**.
Si se asume una posición neutral al riesgo, el proceso estocástico tiene la siguiente forma:
$$
dA_t = r_f\ A dt + \sigma_A\ A\ dW^Q
$$
Donde:
$A$ es el precio de la acción
$r_f$ es la tasa libre de riesgo
$\sigma_A$ es la volatilidad del precio de la acción
$dW^Q$ es un proceso de Weiner (el movimiento Browniano de Black-Scholes)

Bajo esta formula, siendo análogo a laformula de opciones de B-S, podemos decir que el valor de una call
, que en este caso es la deuda, tiene que estar dada por esta función:
$$
D = A N(-d_1) + K * e^{-r_fT} * N(d_2)
$$
Donde:
$D$ es el valor de la deuda (o el strike del call)
$K$ es el valor actual de la deuda. (Recordar que un call es $max(0,A-K)$)
$$
d_1 =\frac {ln(\frac {A}{K}) + (r_f + \frac{\sigma _A ^2}{2} * T)}{\sigma_A * \sqrt T}
$$
$$
d_2 = d_1 - \sigma_A \sqrt T
$$
Tambien definimos el valor de la deuda como su valor actual de mercado, de forma:
$$
D = K* e^{-(r_f + S)T}
$$
Combinando las 2 formulas se puede llegar a:
$$
S = - \frac{1}{T} * ln(\frac {A}{K}*e^{r_fT} N(-d_1) + N(d_2))
$$
Donde se pude derivar que la probabilidad de default esta dada por 
$$
PD^Q = N(-d_2)
$$

Reemplazando la tasa libre de riesgo por el asset expected return de la cartera, quedaría
$$
PD^P = N(-d_2)
$$
Donde:
$$
d_2 =\frac {ln(\frac {A}{K}) + (r_A - \frac{\sigma _A ^2}{2})T}{\sigma_A * \sqrt T}
$$

