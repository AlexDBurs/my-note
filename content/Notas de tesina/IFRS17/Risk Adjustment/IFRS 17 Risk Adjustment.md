---
title: IFRS 17 Risk Adjustment
draft: false
tags:
  - Nota
---
Adicional 1: https://www.cia-ica.ca/publications/222090e/
# Intro
La idea de esta nota es Armar un resumen comprensivo de el ajuste de riesgos no financieros

En esta parte, se espera cuantificar y revelar el nivel de riesgos no financieros subyacentes a los pasivos contraídos por los contratos de seguros. La IFRS 17 define el Ajuste de Riesgos no financieros (de ahora en mas,. RA) como la estimación del valor actual de los flujos de fondos que refleja el márgen que requiere la empresa para aforntar la incertidumbre relacionada a la variabilidad de la cantidad y tiempo de pago que salen de riesgos no financieros.

# Segmentos para incorporar en otras notas
La idea de la norma es estandarizar las prácticas de medición de seguros, con un enfoque en la transparencia , calidad,  rendición de cuentas de la información financiera. Este anfoque ayuda a la reducción de "gaps" y mejores estrategias de inversion, las cuales, a su vez, ayudan a una colocación mas eficiente del capital.

El concepto de Fullfullment Cashflows se define como el promedio ponderado de los flujos de fondos futuros de los contratos de seguros, descontados a valor presente y ajustados por el riesgo no financiero.
Está comuesto por 3 elementos:
- Flujos de fondos esperados
- Tasas de descuiento
- RA
## Flujos de fondos
Son el valor esperado de las salidas de caja futuras menos las entradas de caja futuras producto del cumplimiento del contrato de seguros (y dentrode los límites del mismo). Se pueden calcular en un nivel de agregación mas alto., como por ejemplo, por linea de negocio. 
Se tiene que necesariamente excluir todos los riesgos financieros y no financieros de los mimso y se suelen tomar a fin del periodo y contienen algunos de los siguientes elementos:
$$
{CF}_t = {Surr}_t + {Claim}_t + {Mat}_t + {Comm}_t + {Exp}_t - {Prem}_t + {Inv}_t
$$
Donde:
- $CF_t$ es el flujo de fondo esperado en el momento "t"
- $Surr_t$ es el valor esperado de las cancelaciones de pólizas en el momeno "t"
- $Calim_t$ es el valor esperado de los pagos de siniestros (incluyendo IBNR e IBNER)
- $Mat_t$ el el valor esperado de los pagos por maturities en el momento "t" (Pagos resultantes del final del periodo de la póliza, ej. Capitales diferidos de vida)
- $Comm_t$ es el valor esperado de las comisiones en el momento "t"
- $Exp_t$ es el valor esperado de los gastos (ALAE+ULAE) en el momento "t"
- $Prem_t$ es el valor esperado de la prima en el momento "t"
- $Inv_t$ es el valor esperado de los rendimientos por inversión en el momento "t".

## Tasas de descuento
Las tasas de descuento son para ajustar los flujos de fondo respetando el valor tiempo del dinero y riesgos financieros. 
La principal característica es que tiene que espejar las caracteristicas de los flujos, tanto en moneda, como liquidez y duración. Las tasas tiene que ser consistente con los precios de mercado pero pueden excluir de las misma, aquellos factores que afectan al precio pero no a los siniestros del contrato (como riesgo de crédito).

Para mas info. [[IFRS 17 Discount Rates]]

## Risk Adjustm,ento for non-financial risks

Se refienre a la compensacipón atada a la incertidumbre de la cantidad t el tiempo de los flujos. Si bien no hay un método prescrito, la norma requiere que se revele el nivel de confianza utilizado para el cálculo y la metodolgía del mismo.

Los Flujos de complimiento son la suma del valor presente de las estimaciones de los flujos de caja y el RA.

## Margen de servicio contractual
Se refienre a la ganancia todavía no reconocida por el servicio prestado por el contrato de seguros.
Para determinar el CSM, se tienen que definir "unidades de covertura" , que son valores ilustrativos que representan los patrones de cobertura del riesgo.
La norma especifica que estos tiene que reflejar la cantidad de beneficios  y el periodo de cobertura esperado, incluyendo cancelaciones, terminacionesy y las probabilidades de eventos que puedan afectar la duración del contrato.

## Medición de los pasivos (liabilities)
Ambos métodos (los 3), separan la medición d las liabilities en:
- Libaility for Remaining Coverage (LCR)
	- Corresponde  a la parte inesperada del periodo del cobertura
- Liabilities for Incurred Claim (LIC)
	- Corresponde a la parte que ya pasó

# Teoría
De cierta forma, se puede ver el RA como el resultado extra que puede surgir de desvios en los flujos de fondos en caso de shock.

## Criterios y requerimientos.
La norma especifica 2 requerimientos para el RA:
- Que se tenga en cuenta el grado de diversificación del portfolio y el riesgo que se contempla realmente por eso.
	- Basicamente, que se contemple que hay activos con riesgos correlacionados en el portfolio, y cuanto mas diversificado, menos riesgo hay.
- Que sea racional, teniendo así, eventos favorables y desfavorables que reflejen la aversión al riesgo de la Entidad. El siguiente criterio se tiene que cumplir:![[Pasted image 20250226195149.png]]
- Que sea consistente con los prcios y variables de mercado. Por ejemplo, tiene que haber una correlación positiva entre el ratio de cancelaciones y la tasa de interés (pensar en el concepto de prima de liquidez)
- Que sea comparable con otras entidades. 
- Que sea calculado solo para riesgos no fiancieros. A continuación algunos riesgos por producto:![[Pasted image 20250226200755.png]]
# Estimación del RA
## Métodos de distribuciones de probabilidad

El primer método es utilizar intervalos de confianza para estimar el RA. Esto se hace, definiendo un perfil de riesgo  (se genera una distribución de probabilidad de los flijos descontados) y aplicandole una medición a ese riesgo.

Para generar una destribución de probabilidad se utilizan técnicas de simulaciópn como *Boostrapping* y se pueden resumir en los siguientes pasos:
- Construir un modelo para una variable aleatoria X, que dependa de otras variables aleatorias (Y y Z) con distribuciones y dependencias conocidas
- Se generan pseudo-aleatoriamente valores para $y_j$ y $z_j$ donde $j = 1,...,n$
- Se aproxima una función de probabilidad dada por $F_n(x)$ , la cual es una función basada en la distribución de probabilidades empirica dada por $x_1,...,x_n$ 
- Se calculan los cuantiles de interés (media, varianza, etc...)
Hay varios enfoque estocásticos que se pueden utilizar para estimar los FCF:
- Simulaciones de Monte Carlo
	- Ejemplo: para un seguro de vida, se pueden simular los decrementos por mortalidad o cancelación para un determinado año.  Dado un grupo de contratos, se simula si vive o no con la tasa de mortalidad corespondiente y si cancela o no con la tasa de cancelaciones. Esto se hace un numero suficientemente grande de veces y se obtiene una distribución de los valores resultantes, que vendría a ser la distribución del riesgo para esa cartera
- Método Boostrap.
- Remuestreo de Mack (ver Chail Ladder con Dist. libre de Mack)
- Cadenas de Markov con Monte Carlo
El paper habla del método Bosstrap. Este método de remuestreo es usado para generar escenarios estocásticamente. En vez de suponer una distribución para Y y Z, utiliza la data historica para generar una posible distribución y estimar valores futuros.
El método da una buena aproximación de la distribución de probabilidades reales para una muestra grande de observaciones, sin embargo, cuando la muestra es pequeña, es mejor utilizar otro método. Depende mayormente en que las variables pseudo-aleatoreas calculadas sean independientes entre sí. Adicionalmente, las observaciones históricas puede que no sean representativas de la volatilidad actual de los FCF. Esto pasa en general cuando la severidad es alta y la frecuencia es baja.

Esto se aplica usualmente para el cálculo de reservas de riesgo para seguros de no vida (IBNR) a trazes de tri´zndulos de siniestros pagados o incurridos. Al estar utilizando FCF, se incluyen primas y gastos a la ecuación, lo que puede distorcionar la volatilidad de las liabilities subyacentes. Una posible resolución a esto es calcular las reservas para los siniestros y luego, ajustar por primas y gastos.

Alternativamente, se puede utilizar unm triangulo de los FCF por grupo de contratos y aplizar las técnicas de reservas. Sino, se puede intentar determinar la distribución de cada componente de los FCF y combinarlas a una esdtructura de dependencia apropiada (como las copulas)

## Medidas de riesgo como métodos de selección
Si se obtiene la distribucin de probabilidades de los FCF, el riesgo se puede medir por medidas de riesgo dado un nivel de confianza. El RA va a ser la resta entre la el valor obtenido en el cuantil de la distribución y la media de la misma.

Para que una medida de riesgo sea coherente, tiene que tener las siguientes características:
![[Pasted image 20250227183438.png]]

### Value-At-Risk (VaR)
Se usa para calcular el SCR de Solvencia 2. Es el cuantil p-ésimo de una distribución de probabilidades para una variable aleatoria X.

En este caso, el ajuste de riesgo está dado por:
$$
RA = VaR_p(X) - \mu
$$
Donde:
- RA es el ajuste de riesgo no financieros
- $VaR_p(X)$ es el valor al riesgo de una variable aleatoria X en el percentil 'p'
- $\mu$ es la media de la distribución (es decir,. $VaR_{0,5}(X)$)
Para el caso puntual, los valores de la variable X son los flujos descontados. En cuanto a coherencia, no tiene la propiedad de sub-aditividad, por lo que no es una medida coherente (las otras las cumple).

## Tail-Value-At-Risk (TVaR)
Parecido al VaR, el TVaR es el área bajo la curva a partir de un percentil 'p' en la distribución probabilistica de una variable aleatorea X. En términos financieros, es el valor esperado de la pérdida dado un evento con masa probabilística menos a 1-p . Es una medida coherente y su fórmula es la sigueinte:
$$
TVaR = \frac{\int_{p}^{1}VaR_u(X)\ du}{1-p}
$$
Dodne:
- La expresión del numerador es la integral de todos los percentiles del VaR(X) partiendo de 'p' hasta 1.
- La expresión del denominador es la probabilidad de que X sea menor al $Var_p(X)$
El RA se calcula análoga con el VaR y se representa de la siguiente manera:
$$
RA = TVaR_p(X) - \mu
$$

### Proportiona Hazard Transform

El PHT se puede interpretar como un caso particular del cálculo de las primas ajustadas al riesgo. 
Dado $p\geq 1$ :
$$
Prima\ Ajustada\ al\ riesgo = \int_{0}^{\inf}[1 - F_x(u)]^{1/p}\ du
$$
Donde:
- Prima Ajustada al Riesgo son todos los cashflows futuros en caso de shock
- $F_x(u)$ es la función de distribución para la variable X
El ajuste de riesgo, tomaría la siguietne forma:
$$
RA = Prima\ Ajustada\ al\ riesgo - \mu
$$
Ejemplo:
Producto el cual se puede representar como uan distribución de Pareto tal que:
$$
 X\sim Pareto(\alpha ,\theta)
$$
$$
E(X) = \frac{\theta}{\alpha-1}
$$
$$
Var(X) = \frac{\theta ^2\ \alpha}{(\alpha - 1)^2\ (\alpha - 2)}
$$
$$
F_X(X) = 1 - (\frac{\theta}{\theta + x})^\alpha
$$
Pol lo tanto, dado un nuvel de significancia 1-p:
$$
Prima\ Ajustada\ al\ riesgo = \int_{0}^{\inf}(\frac{theta}{\theta + x})^{\alpha / p}\ dx\ = \frac{\theta}{\frac{\alpha}{p}-1}
$$
Cundo se utiliza este método, es necesario revelar en nivel 'p' y a que percentil equivaldría si se utilizara un método de percentiles

## Cost of Capital (CoC) method
Una alternativa a los métodos que requieren un nivel de confianza, es el CoC. Esta medida está basada en estimar los requerimientos de capital de las obligaciones de un producto durante toda su vida.
En este caso, el RA se define como la compensación que la Entidad requerirá para obtener el rendimiento esperado sobre ese capital. Los elementos requeridos para calcular este ajuste son los siguientes:
- La cantidad de capital estimada para cada uno de los riesgos no financieros duirnate la duración de las liabilities
- El CoC rate, que refleja la compensación relativa que una Entidad requiere para adquirir el capital al riesgo.
- Tasas de descuento para traer todo a valor presente.

La formula es la siguiente:
$$
RA = \Sigma_{t \geq 0}\frac{r_t*C_t}{(1+d_t)^t}
$$
Donde:
- $r_t$ es el CoC rate para el momento 't'
- $C_t$ es la cantidad de capital estimada para el periodo 't'
- $d_t$ es la tasa de descuento para el periodo 't'
En este caso, el numerador de la fórmula representa la compensaqción necesaria para una Entidad que tiene el capital al riesgo en el momento 't'.
### Elementos del cálculo
#### Capital Amount $(C_t)$
Esto se calcula por 'imulations-based capital modelling' en Solvencia 2. Basicamente, se aplica la fórmula estandard para egnerar cashflows con shocks dado el riesgo del producto y tomar la mejor estimacipon de la diferenfcia entre los cashflows shockeados y los estimados (https://www.cia-ica.ca/publications/222090e/)

Luego, para obtener las estimaciones futuras, se elige un driver, como es el patrón de la 'mejor estimación', y se estiman.
Este método es operacionalmente simple, pero puede ser menos preciso. Requeriría que no haya ningun error es las provisiones técnicas utilizadas en la estimación.

Alternativamente, se puede utilizar el modelo para el primer número (la fórmula Estandard de Solvencia 2) e ir cambiando los supuestos a medida que las reservas se van consumiendo. Este método es notoriamente mas dificil de implementar.

#### Cost of capital rate ($r_t$)
Usualmente es la WACC (Weighted-Average Cost of Capital) que refleja la tasa a la que la Entidad está dispuesta a invertir su capital. Tiene que reflejar la aversión al riesgo de la compañía.

#### Discount Rate ($d_t$)
Tiene que ser la tasa a la que se descontaron los flujos de fondos. Ver mas en [[IFRS 17 Discount Rates]]

## Comparasión entre la técnicas de estimación
![[Pasted image 20250227232834.png]]
Resumen: CoC es el mas práctico para las aseguradoras que vienen de Solvencia 2, pero tienen que revelar el nivel de confianza. TVaR es la mas eficiente para medir el riesgo porque tiene en cuenta la forma de la cola pero el VaR es mas facil de calcular, explicar y lo usan mas empresas por Solvencia 2.

# Diversificación y correlaciones
La norma dice que se el RA se tiene que medir a nivel grupo de contrato y que tiene que contener los beneficios de diversificación de riesgos. 
La idea de la diversificación de riesgos en agruparlos de tal forma que la suma de los riesgos agrupados sea menor a la suma de todos los riesgos. Esto pasa porque existe correlación tal entre los riesgos que si pasa 1, no pasa el otro.

De la niif 17 salen 2 requerimientos sobre esto: 
- Que las Entidades tenag un método  de caluclar el beneficio por diversificaicón
- Que las Entidades tengan un método para incorpora esos beneficios al RA
El método elegido no debe conllevar inestabilidad de la RA para periodos posteriores.
Existen 2 enfoques sobre esto.
### Bottom-Up
Este enfoque se basa en calcular el RA para grupos de contrato como la agregación de RA calulados a un nivel menos (como a nicel riesgo). Se puede hacer por:
#### Suma Simple
Es el método mas simple pero no considera un beneficio por diversificación. Por ejemplo, si tengo un grupo de productos afectados por riesgo de mortalidad, longevidad y cancelación, el RA queda dado de la siguiente menra:
$$
RA = RA_{mort} + RA_{long} + RA_{canc}
$$
#### Correlaciones
Otra forma es juntarlos a travez de matricas. Para esto, se pueden utilizar las correlaciones dadar por Solvencia 2 y aplicar:
![[Pasted image 20250228160204.png]]

#### Copulas
Tambien se pueden utilizar cópulas que modeloan la dependencia entre diferentes variables aleatorias. 
Ver Koetsier (2018) Optimising choices with respect to the risk adjustment in IFRS 17, master thesis, Science, Management & Innovation master specialisation, Faculty of Science, Radboud University Nijmegen, Netherlands

### Top-Down
Esto se usa en el caso de que el RA s calcule como una combinación de diferentes grupos de contratos. Basicamente se calcula aun nivel mas alto y luego se aplican proxies o márgenes para aplicar el RA a cada producto.
#### Scalar Allocation
Tambien conocido como alocación pro.rata y se basa en determinar una medida de referencia que refleje el tamaño relatico de cada riesgo no financiero a nivel grupod e contrato. Un ejemplo de esta medida puede ser el peso del valor presente de los cashflows futuros. Hay que ver si se validan los supuestos cada vez que se calcule, ya que la incertidumbre con los FCF puede variar con el tiempo. En lo posible, deberías estar relacionado a las *unidades de cobertura* del CSM y debería tener compatibilidad entre grupos de contratos de diferentes tipos de productos (y ser interpretable)

# Presentación en Estados financieros
El RA se presenta para cada periodo de presentación (decidido por la Entidad)
La idea es que a medida que pase el tiempo, el RA baje dado que va a bajar el riesgo en los contratos hasta que expiren. Esto hace que la compañía tenga que reconocer la variación como 'Insurance Revenue' para el periodo donde se ajustó el RA, excluyendo:
- Por cambios encluidos en el ingreso o egreso de las finanzas de los seguros
- Por cambios en el ajuste de CSM que se relacione a un servicio futuro
- Cantidades que se hayan puesto en el Loss Component de la cobertura remandente de la suma asegurada
La norma también dice, que las cantidades se deben desglozar en el 'insurance service result' (que es la suma del 'insurance revenue' y el 'insurance service expense') y el IFIE (insurance finance income or expenses).
La Entidad puede decidir si quiere desagregar el RA en el 'insurance service result' y el IFIE en el Estado financiero. Si se elige no desglozar, no se pone le RA en el IFIE y el 'insurance service result' va a tener todo el cambio del RA para eol periodo.