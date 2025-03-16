---
title: 'IFRS 17 Discount Rates'
draft: false
tags:
  - Nota
---
Fuente:[[content/Notas de tesina/Metodologias/bin papers metodologicos utiles/Tasa de descuento/whitepaper-series-ifrs17-discount-curves.pdf]]
Adicional: [[content/Notas de tesina/Metodologias/bin papers metodologicos utiles/Tasa de descuento/Case study on the top-down approach - Final_20200106_0.pdf]] 
Adicional 2: [[IAA_IAN100_31August2021.pdf]]
Adicional 3: https://www.actuaries.org.uk/system/files/field/document/IFRS%2017%20Publication_Final.pdf
Adicional 4: https://www.soa.org/globalassets/assets/files/resources/research-report/2019/yield-curve-report.pdf
Adicional 5: https://www.iais.org/activities-topics/standard-setting/insurance-capital-standard/
Adicional 6: [[public/Notas-de-tesina/Metodologias/bin-papers-metodologicos-utiles/Tasa-de-descuento/hurdnotes.pdf|hurdnotes]]
Adicional 7: [[public/Notas-de-tesina/Metodologias/bin-papers-metodologicos-utiles/Tasa-de-descuento/hurdnotes2.pdf|hurdnotes2]]




# Resumen
La idea de la Niif17 es que los aseguradores valuen sus activos de forma consistente con el mercado. El tema es que pueden surgir diferencias en la contabilidad en las valuaciones cuando un activo está valuado como fair value por un lado y por costo amortizado por otro. 

Teniendo e cuenta esto, la Aseguradora tiene 2 opciones para armar la curva de tasas de interes para descontar los flujos de los **grupos de contratos**:

- Top-Down: Se arma un portfolio de referencia y se le quita el ECL (Expected Credit Losses o PCE en español), el UCL (Unexpected Credit Loss) y la Prima por el riesgo de crédito.

- Bottom-Up: Aca se agarra una Tasa Libre de Riesgo y se le agrega una prima (tasa) por iliquidez

![[Pasted image 20250210154957.png]]

##### Construyendo la curva libre de riesgo
Uno de los temas comúnes a los 2 es calcular una curva de tasas libres de riesgo que cumpla con las crácterística (Duración y convexidad) del grupo de contrats de seguros. Estos usualmente están conformados por Swaps de tasa de interes o bonos gubernamentales.
Al no estar definida a metodologia, se pueden utilizar metodos no paramétricos como **Boostrapping** o **Splines cubico o cuadrático**. El problema de esto es que no te devuelven curvas suaves/suavizadas. Otro tema es que juntar instrumentos con maturities parecidas, puede generar "saltos" en la curva.
Tambien, se puden utilizar enfoques paramétricos como variantes del [[Método de Nelson-Siegel]] y [[Método Smith-Wilson]]. 
La determinación de la liquidez de un instrumento se asume consideranod siguiente: 
- Disponibilidad de los bonos en el mercado
- Tamaño del spread entre el Bid y el Ask
- Volumen y freuencia de trading

# Bottom-Up

## Cálculo de la tasa libre de riesgo
Encontrar uan curva de tasas libres de riesgo implica que estas tienen que pertenecer a instrumentos practicamente sin riesgo de crédito, con alta liquidez , preciosestables confiables) y que comprenda un rango alto de maturities  (mas allá de la duración del contrato). 
Los intrumento mas comunes son:
- Bonos estatales
	- Lo bueno de esto, es que el ajuste de iliquidez está correlacionado con el rating crediticio del país. Si tiene AAA o AA, se puede considerar sin riesgo e crédito y sin riesgo de liquidez. 
- Inter-bank swap Rates
- Intrest rate swaps
	- Si se toma este intrumento, mas adelante se puede argumentar el uso de las curvas de libres de riesgo extrapoladas que calcula la EIOPA para Solvencia 2. Dicho esto, hay algunos temas a considerar:
		- Si bien poblican las tasas mensualmnente, puede que el reporte esté descalzado con las fechas de reporte de la empesa. Adicionalmente, se tendría que hacer el mismo análisis de liquiez que hace EIOPA para el mercado de bonos (gubernamentales y corporaticos) para mantener la consistencia metodológica con otras carteras de seguros menos líquidos.
		- Se calculan solo para monedas europeas. Habría que replicar el cálculo apra los Pesos Argentinos
		- Se va a tener que considerar el ajuste de riesgo de crédico que calcula EIOPA para Solvencia 2.
		- Se va a tener que considerar la extrapolación de la EIOPA que usan el [[Método Smith-Wilson]], que tiene incorporado un "Ultimate Rate Forward"
Algunas alternativas son:
- Overnight intrest rate swaps (OSI). Esto es el equivalente a las LELIQS de EEUU (?).
- Futuros del tesoro (EEUU)
-  CDS insured goverment debt
- Bonos corporativos de bajo resgo
- Crear una curva según el Adicional 5:
	- Fijar curva según bonos gubernamentales o swaps
	- Extrapolar por [[Método Smith-Wilson]]
	- Mirar que converjan (de forma estable) al Long- Term Forward Rate


==Investigar bases risk-free y risk-neutral de valuación para los dos regimenes regulatorios de Europa (Swiss Solvency Test y Solvencia 2)==

## Cálculo de la prima de liquidez
En rasgos generales, la prima de liquidez se obtiene de la siguiente forma:
$$
Liquidity\ risk\ premium\ =\ yield\ to\ maturity\ on\ a\ reference portfolio\ –\ risk\ free\ rate\ –\ credit\ risk\ premium
$$

Esto implica el cálculo de los siguientes puntos:
### Portfolio de referencia y liquidez de los contratos
La IFRS 17 pide que se considere la liquidez del contrato por sus características que afecten la misma.  De esta forma, habría 2 vertientes:
- Liabilities para la cobertura remanente: Se presume líquida porque el tenedor puede cancelar el contrato en cualquier momento sin sufrir ningún tipo de penalidad, mas allá que, por ejemplo,  retención de las primas pagadas por adelantadas.
- Liabilities para siniestros incurridos: estos son mas dificiles de cobrar para el tenedor antes de la Settlement date (plazo máximo de pago, varía por ramo). Dado este detalle, podría decirse que los cashflows en el corto y mediano plazo, no son muy liquidos.

Lo óptimo es mezclar bonos y armar "Buckets" de liquidez y crear una cartera de referencia para cada bucket. En general, esto es posible porque para formasr un grupo de contratos, las características entre sí deberian ser similares.  Los drivers principales para asumir la liquidez de un bono son:
- Moneda
- Duración (duration)
	- Cuanta mas liquidez, menos duración.
- Rating
	- Cuanto mas liquidez, mas rating
- Volumen (amount issued)
	- Cuanta mas liquidez, mas volúmen
- Time to maturiry

### Ajustes de riesgo de crédito
El ajuste mas comun es el "Credit Adjustment", el cual se basa en remover el riesgo de crédito de la curva. Eso pasa con, por ejemplo, los bonos corporativos o bonos nacionales de baja calidad crediticia.
Este tema se desarrolla en la explicación del enfoque Top-Down 


# Top-Down
Para IFRS 17, la curva de tasas, debería idealmente, replicar el precio del grupo de contratos cuando se lo aplica al portfolio de activos parecidos. No necesariamente el precio de cada contrato individual.  Para esto, se puede:
- Encontrar un portfolio replicante de la cartera de contratos de seguro,
- Remover el riesgo de crédito de la curva de rendimientos de dicha cartera. Este comprende tanto la Pérdida Crediticia esperada como la inesperada.
- Una vez obtenido el ajuste de riesgo de crédito, hay que ajustar por la duración de la curva, y efector de ==alto orden==, como diferencias en la convexidad de las curvas. Esto de puede volver un ajuste estimado la cola probabilistica de pérdidas que resultan de movimientos adversos de la curva. 
	- Cuando hay inflación, se debería utilizar las curvas reales o instrumentos atados a la infalción como: government-issued infl ation linked bonds, or infl ation swaps
- Por ultimo, se extrapola la curva de rendimientos:
	- Para contratos largos como annuities, se tiene que extrapolar la curva a apartir del "Last Liquid Point". Espor se puede hacer:
		- Extrapolando "plano" basado en el ultimo punto de liquidez
		- Extrapolar haia un ultimate o Forward Rate. Este es el enfoque de Solvencia 2
	- Las técnicas para extrapolar peden ser paramétricas (Nelson Siegel o Smith Watson). Smith Watson es la de Solvencia 2

## Cálculo de Riesgo de Crédito

El Riesgo de Crédito se suele estimar utilizando los siguientes.
### Market Based Techniques
 Se usan normalmente los spread de los **Credit Default Swaps** en  bonos de alta liquidez como medida de riesgo crediticio implícito o los **Option Adjusted Spread** para bonos corporativos o de menor liquidez. 
 Se asume que representan ambas pérdidas pero puede sobreestimar el ajuste dado que el mercado es tan vulnerable a efectos de precio (como iliquidez), como los activos en la cartera de referencia. 
#### Option Adjusted Spreads

Mas info: https://thetradinganalyst.com/option-adjusted-spread/

Las Option Adjusted Spread (OAS) se hacen sobre bonos con una opción de compra o venta asociada (y ejecutable) a si mismas. Sirven para medir la diferencia entre la curva del bono con la opción y la curva del bono sin la opción (y su valor de mercado). 
Nota sobre [[Bonds with embeded options]]

Se calcula como:
$$
OAS = Z_{Spread} - Option\ Cost
$$
Donde:
- $OAS$ es el valor de la diferencia de la curva del bono sin arbitraje (==y creo que sin opción==) y una curva libre de riesgo. Es teóricamente el riesgo de crédito que estas asumiendo por no irte a una opción sin riesgo.
- $Z_Spread$ es la diferencia entre la curva del valor de mercado del bono con la opción y una curva libre de riesgo, asumiendo volatilidad 0
- $Option\ Cost$ es la diferencia entre la la curva del valor de mercado del bono con la opción y la curva del bono sin arbitraje (y creo que sin opción). 

El lado malo de esto es que al ser precio de mercado, el riesgo de liquidez y los impuestaos afectan al OAS. La ventaja es que estan disponible en Bloomberg con deriodicidad diaria.
#### Credit Default Swap Spread

Se usa en  bonos de alta liquidez como medida de riesgo crediticio implícito. Se asume que representan ambas pérdidas pero puede sobreestimar el ajuste dado que el mercado es tan vulnerable a efectos de precio (como iliquidez), como los activos en la cartera de referencia. 

Los CDS son derivados financieros que permiten hacer un "swap" del riesgo de crédito de un inversor a otro. Concretamente, el tenedor paga un *premium* al emisor sobre una deuda contraída por el tenedor cosa de que ocurre un default de la deuda, el emisor deberá pagarle al tenedor un monto acordado (usualmente el de la deuda). 

Esto lo que nos permite es tener un estimativo del riego de crédito que se asume al adquirir un bono, impícito en su CDS. Sin embargo, al ser un derivado, está sujeto a las fuerzas del mercado, por lo que no es una medida del riesgo de crédito pura.

El cálculo de la prima por riesgo de crédito es el siguiente:

$$
Credit\ Risk\ Premium = \frac {Mid - (1-iliquidity\ factor)}{10000}
$$
Donde: 
- $Credit\ Risk\ Premium$ es la tasa de descuento que hay que aplicarle a la curva del portfolio de referencia para sacarle el riesgo de crédito.
- $Mid$ es una aproximación del precio de mercado del CDS Spread (vendía a ser como el precio promedio de los CDSs a lo largo de todas la maturities)
- $iliquidity\ factor$ es la tasa que representa la "prima de iliquidez" en la curva de CDS. Se descontará toda la curva por ese factor.
- Se divide sobre 10000 porque todos los números son porcentajes expresados * 10000

Nota:
- La European Insurance and Occupational Pensions Authority (EIOPA) calcula un estimado del Credit Risk Adjustment para Solvencia 2. El tema es que la IFRS 17 te pide una tasa libre de riesgo para un portfolio de activos, no únicamente de swaps, que es lo que representa esta tasa.

#### Inconvenientes o ajustes a la curva
##### Extrapolaciones
Muchas veces, las curvas de CDS no llegan a la duración entera de los bonos (usualmente estatales). Cuando pasa esto, hay que extrapolar las curvas, normalmente con una regresión lineal o logaritmica, y validar que las estimaciones tengan sentido. Por ejemplo, si los CDSs quedan por encima de la curva del bono en algun punto, está mal la estimación.

##### Riesgo de Liquidez
Al ser derivados, tienen su propio riesgo de liquidez por sobre los bonos asociados. Esto hace que no sean una medición pura del riesgo de crédito (como mencioné anteriormente). 
Para solucionar este punto, habría que restarle una prima por iliquidez. Al no haber un método comunmente aceptado, el paper (Adicional), propone lo siguiente:

$$
iliquidity\ factor = \frac {Ask - Bid}{Mid}
$$
Donde:
- $iliquidity\ factor$ es la tasa que representa la "prima de iliquidez" en la curva de CDS. Se descontará toda la curva por ese factor.
- $Ask$ es el precio de venta
- $Bid$ es el precio de compra
- $Mid$ es una aproximación del precio de mercado del CDS Spread (vendía a ser como el precio promedio de los CDSs a lo largo de todas la maturities)
###  Credit mitigation rates y Cumulative default rates
Usa bases de datos historicas de "default transitiones" y LGDs para ver la cola de la distribución de pérdidas + la PCE.  
Ambas suelen tener la misma metodología. Primero estiman la PCE Monetaria a travez del cálculo de la PD, LGY y EAD y luego la vonvierten en un porcentaje de prima de riesgo. Estos ajutes suelen ser Through the Cycle, en vez de Point In Time por lo que pueden no estar ajustados a la situación económica actual o al valor de mercado. Adicionalmente, puede haber problemas en la obtención de las bases y la representatividad de las mismas para el ajuste Forward Looking

Se pueden obsrevar 2 enfoques:
- Credin Mitigation Rate: Es la chance de que el bono se mueva de un grado de rating a otro. Un decaimiento del rating crediticio se refleja en una baja precio del bono, e incremento de rendimientos por el riesgo extra. La idea es que la Prima de riesgo de crédito incorpore las probabilidades de degradación y las de default para estpo. 
- Cumulative Default Rate: Son específicos al rating y reflejan el riesgo acumulado de un default a un horizonte de tiempo futuro asociado a un pago de cupon o principla futuro

Ambos representan la base de los ajustes Volatility and Matching  de Solvencia 2, por lo que pude haber sinergía en ese aspecto.

Un ejemplo de Cumulative Default Rate sería el sigueinte:

Generalmente, el modelo se expresa de la siguiente manera:
$$
ECL_t = EAD_t * PD_t * LGD_t
$$
Donde: 
- $ECL_t$ es el valor actual en "t" de la pérdida esperada de la cartera
- $EAD_t$ es el saldo expuesto al default en el momento "t"
- $PD_t$ es la probabilidad de default para un momento "t"
- $LGD_t$ es la tasa que se estima "irrecuperable" de la $EAD_t$ dado un default en "t"
	- Se estima por su complemento, siendo este, la $Tasa\ de\ recupero$.  :$$LGD(\% ) = (1 - Tasa\ de\ recupero)$$
	- Para bonos, este cálculo lo hacen las agencias de rating como Moody's o S&P. Tambien, se puede calcular a travez de modelos estructurales de PD y LGD para bonos como [[Modelo Estructural PCE Merton]] o [[Modelo Estructural PCE Vasicek-Kealhofer]]
#### Estimaciones de la PD y la LGD
Cuando estimamos esto sobre una cartera de referencia, hay que tener en cuenta que no hay una "talla única". Cada instrumento tiene su manera de medir el PCE, por ejemplo, en el Hull[^1], detalla como se calcula una PD para los CDS spreads:
$$
PD = 1 - e^{\frac{-spread\ *\ t}{1-Tasa\ de\ Recupero}}
$$
Donde:
- $PD$ es la probabilidad de default en el momento "t"
- $spread$ es el spread de la curva del bono contra una curva libre de riesgo. También se puede utilizar lo que denominamos como "$Mid$" anteriormente y ajustado por una prima de iliquidez.
- $t$ es el horizonte de tiempo al cual de analiza la $PD$
- $Tasa\ de\ recupero$ es la proporción de la deuda que se espera recuperar dado un evento de default.

Para obtener la PD Through the Cycle, es el promedio de todos los puntos de la misma.

#### Pase de PCE a Yield to Maturity
El pase de la deducción del valor de mercado de la PCE a una TIR descontada se puede hacer de varias formas. Intuitivamente, se demuestra que:
$$
MV = \sum_{t}\frac{CF_t}{(1+YTM)^t} \approx \frac{Total\ undiscounted\ Cashflow}{(1+YTM)^{Duration}}
$$
Donde:
- $MV$ es el Market Value
-  $CF_t$ es el cashflow del bono en "t"
- $YTM$ es yield to maturity (la TIR)

De forma análoga:
$$
MV^* = \sum_{t}\frac{CF_t}{(1+YTM^*)^t} \approx \frac{Total\ undiscounted\ Cashflow}{(1+YTM^*)^{Duration}}
$$
Donde:
- $MV^*$ es el Market Value ajustado por ECL tal que:
	- $MV^* = MV * (1-ECL)$
- $YTM^*$ Es la YTM correspondiente al activo descontando el riesgo de crédito.

Se demuestra:
$$
MV - MV^* = MV * ECL = \frac{Total\ undiscounted\ Cashflow}{(1+YTM)^{Duration}} - \frac{Total\ undiscounted\ Cashflow}{(1+YTM^*)^{Duration}}
$$

Reordenando en función de $YTM^*$:
$$
YTM^* = (\frac{1}{(1+YTM)^{Duration}}- \frac {MV * ECL}{Total\ undiscounted\ Cashflow})^{\frac{-1}{Duration}} -1
$$

### Modelos Estructurales
Calculan la PD y (algunos) la LGD. Combinados se obtendría algo parecido a una prima de riesgo (que explica las variaciones de precios a lo largo del tiempo).
- Algunos modelos son: [[Modelo Estructural PCE Merton]], [[Modelo Estructural PCE Vasicek-Kealhofer]], Moody’s Analytics EDF™ (Expected Default Frequency), Leland and Toft Model and EDF-Based Model, etc....

### Modelos de regresiones
Técnicas basadas en regresión como en [[Van Loom 2015 LiquidityPremiumPaper.pdf]]
### Simplificaciones del Riesgo de crédito

 Según [[IAA_IAN100_31August2021.pdf]], las aseguradoras, muchas veces simplifican los cálculos de la Pérdida Crediticia ya que son bastante complejos. Algunas aproximaciones son las siguientes:
- $Deduction\ for\ credit\ risk = Expected\ Default\ Rate + X\% \ (Total\ Bond\ Spread\ – Expected\ Default\ Rate)$
- $Deduction\ for\ credit\ risk = X\%\ (Total\ Bond\ Spread)$
- $Deduction\ for\ credit\ risk = Expected\ Default\ Rate * (1+compensation\ risk)$

### Extrapolación del ajuste de riesgo de crédito
Muchas veces pasa que las duraciones del portfolio de referencia no cubren la duración de las liabilities de los contratos, por lo que se deben extrapolar sus tasas y en cunsecuencia, su ajuste de riesgo de crédito.
Para extrapolar, se puede utilizar:
- [[Método de Nelson-Siegel]][^2]. Hay una libreria en R que lo aplica (yield Curve)
- [[Método Smith-Wilson]] (que es el que se usa bajo Solvencia 2 y la EOPIA proporciona un Excel que lo calcula[^3])
- 
## Consideraciones y compatibilidad con Solvencia 2
#### Portfolio de Referencia
Dado que hay que armar un portfolio de referencia con diferentes intrumentos, una estrategia es poner los instrumentos en "buckets" según su liquidez. 
Cuando se consideran *liabilities* muy liquidas (==Buscar ejemplo==), se pueden utilizar swaps de tasas de interés, que tienen un riesgo de crédito positivo y un riesgo de liquidez muy bajo (debería se casi inexistente). Eso a su vez nos permite utilizar la curva de descuento de EIOPA para Solvencia 2, que esta armada con CDSs. Ora opción son los bonos estatales.
Para *liabilities* menos líquidas, se deberían incorporar bonos corporativos, por lo que la curva la tenemos que calcular nosotros.

#### Extrapolaciones

La diferencia principal entre [[Método de Nelson-Siegel]] y [[Método Smith-Wilson]] es el uso de un Ultimate Forward Rate(UFR), que se calcula como un promedio de la suma de la tasa real de mercado anual y la inflación esperada anual. 
- La tasa real es la misma para todos y se calcula como el promedio de 1961 hasta ahora de una canasta de tasas reales de diferentes paises. 
- La inflación esperada anual varía por moneda y se calcula como el promedio del inflation target de los bancos centrales europeos.
- La EIOPA tiene un tope de 15 puntos básicos de diferencia.

Otra cosa a tener en cuenta es el Last Liquid Point(LLP), que tambien se tiene que justificar.  
- Esto impacta mas en el [[Método de Nelson-Siegel]] ya que no usa UFR. Cuanto menor sea el LLP, mas hayq ue extrapolar y va a variar mas con el UFR.
Para portfolios de bonos, el LLP pude ser la duración del portfolio.

#### Matching Adjustment
Para hacer la sinergía con solvencia 2, se le puede aplicar el [[Matching Adjustment]] para las *liabilities* de largo plazo que estan replicadas con instrumentos bajo *hold to maturity*. 
##### Incorporación de escenarios estocásticos
Cuando se utiliza el Variable Free Approach, una solución es utilizar métodos estocásticos para estimar una curva. Las aseguradoras pueden elegir dividir los cashflows determinísticos de los que provienen de movimientos estocásticos del mercado. Para estos últimos, se los pueden valuar con una acción (option based techniques).

### Resumen
![[Pasted image 20250219131508.png]]
Fuente: [[Case study on the top-down approach - Final_20200106_0.pdf]]




[^1]: Hull, J. (2009). Options, futures and other derivatives/John C. Hull, 7th Edition, p.490 – 492

[^2]: Nelson, C. R., & Siegel, A. F. (1987). Parsimonious modeling of yield curves. Journal of Business, 473-489.

[^3]:  https://eiopa.europa.eu/Publications/Standards/Smith-Wilson Risk-Free Interest Rate Extrapolation Tool v1.2.xlsb
