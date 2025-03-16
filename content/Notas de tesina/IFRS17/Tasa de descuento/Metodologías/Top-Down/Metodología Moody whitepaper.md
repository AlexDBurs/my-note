---
title: Metodología Moody whitepaper
draft: false
tags:
  - Nota
---
# Sensibilidad
Cuanto mas grande la tasa, mas grande el CSM porque hay que devengar mas


##### Cost of Capital Approach (paper 1, sub-paper 3)
La idea del paper es explicar un enfoque de CoC  para caluclar el ajuste de riesgo de crédito para descontar en IFRS 17.  Esto es para el método Top-Down de IFRS17. 

Resumen del método Top-Down:
- Se elige una cartera de activos representativos al grupo de contratos de seguro
- Se estima el ajuste por riesgo de crédito, que no es otra cosa que calcularle una PD y una LGD a la cartera.  Se multiplican y se obtiene el Credit Risk Default Spread (CDS).
- Se observa el spread total de la cartera de activos y se le resta el CDS para obtener el ajuste por iliquidez (que debería ser parecido al método Bottom- Up)
- Se resta el CDS a la curva de tasas de la cartera de referencia para obtener la tasa de descuento por IFRS 17.
==El ajuste por solvencia 2 es por TTS. Investigar==

==Investigar el modelos de  Vasicek-Kealhofer (VK) variant of the Merton model ==

==Both the Merton and VK models require an estimate of asset volatility to determine the distance-to-default. Unlike market capitalisation, neither equity, nor asset, volatility are directly observable in the market and the estimation of volatility is therefore an important element of the calibration of the model. Moody’s EDF model uses a weighted average of empirically measured volatility over a historical window and a modelled volatility based on the size, location and business type of the fi rm.==

==Finally, the EDF model removes the assumption of normality for the relationship between distance-to-default (DD) and the probability of default. The distance-to-default gives an ordinal measure of the default risk. Interpreted as a number of standard deviations, the DD can be converted to a PD, using a normal cumulative distribution function==
