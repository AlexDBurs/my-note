---
title: 'IFRS 17'
draft: false
tags:
  - Nota
---
# Introducción
La idea de la Niif17 es la trasparencia al valuar los seguros en los estados contables. Notoriamente el P&L. 

>Definicion de contrato de seguro: 
>Un contrato es un acuerdo entre dos o más partes que crea derechos y obligaciones exigibles. La exigibilidad de los derechos y obligaciones de un contrato es una cuestión del sistema legal.
>Los contratos pueden ser escritos, orales o estar implícitos en las prácticas tradicionales del negocio de una entidad. Los términos contractuales incluyen todos los términos de un contrato, explícitos o implícitos, pero una entidad no considerará los términos que no tengan sustancia comercial (es decir no tengan efecto apreciable sobre la naturaleza económica del contrato).
>Los términos implícitos en un contrato incluyen los que resulten impuestos por ley o regulación. Las prácticas y procesos para establecer contratos con clientes varían entre jurisdicciones legales, sectores industriales y entidades. Además, pueden variar dentro de una entidad (por ejemplo, pueden depender de la clase de cliente o de la naturaleza de los bienes o servicios comprometidos).


##  Alcance
Esta norma se debe aplicar a todo lo que considere un contrato de seguro (y un par de intrumentos financeros):
- Contratos de seguro y reaseguro emitidos
- Contratos de reaseguro cedido
- Instrumentos financieros que incorporen participación en beneficios discrecionales sólo si son emitidos por aseguradores (por ejemplo, la modalidad unit-linked)

Además aclara lo que **No** cubre:
- Garantías de productos emitidos por el fabricante/vendedor. Se aplica IFRS 15.
- Garantías de valor residual proporcionadas por el fabricante/vendedor. Se aplica IFRS 15.
- Derechos/obligaciones contractuales vinculados al uso futuro de activos no financieros.
- Derechos/obligaciones contingentes surgidos de combinaciones de negocios. Se aplica IFRS 3.
- Contratos en los que la entidad sea la tomadora del seguro, salvo que sean contratos de reaseguro mantenidos.

Tambien tiene una parte ambigua que puede pasar por la Niif15 o la Niif17. Esto es cuando se cumple la definicion de seguro pero el objetivo del contrato es prestar un servicio a precio fijo. Por lo que debe tener las siguientes caracteristicas:
- La prima cobrada al tomador no refleja la  valuación del riesgo individualmente
- La prestación consiste en la prestación de un servicio
- El principal riesgo transmitido es el uso del servicioo más que el coste mismo

## Riesgo de seguro

Se define como el riesgo, distinto del riesgo financiero, transferido por el tenedor de un contrato al emisor. Usualemente es el importe de pago atado a la ocurrencia de un suceso asegurado en el comtrato (pago de siniestro).

A grandes rasgos, todo lo que no tenga riesgo de seguro, no es un seguro. El párrafo B27 aclara mas sobre que NO es un seguro pero basicamente:
- Contratos que no transfieren un riesgo significatibvo al emisor
- Contyratos que devuielven todo el riesgo significativo al tenerod de la póliza como consecuencia de pérdidas (contrasegro?)
- Autoseguro
- Contratos que no requieren que el evento afecte de forma adversa al asegurado
- Derivados que paguen caundo vamnia alguna variable financera o no financieras que no especifica para una de las parters del contrato.
- Garantias crediticias que exigen pagos popr mas que no haya pérdida (van valuados por NIIF9)
- Contratos que dependan de variables físicas (climaticas) --> derivados climaticos
- Bonos de catástrofe

## Agrupación de contratos
Primero se agrupa por *Cateras de contratos de seguro* , las cuales comprenden contratos sujetos a riesgos similares (Ramo y segmentaciones pertinentes). 

Luego, pide segmentarlos por onerosidad del contrato:
- Grupo de los que son *onerosos* en el reconocimiento inicial
- Grupo en el que en el reconocimiento inicial no son *onerosos* y no hay probabilidad significativa de que lo fueran posteriormente
- Grupo en el que en el reconocimiento inicial no son *onerosos* pero con probabilidad significativa de que lo fueran posteriormente
Donde, que un contrato sea *oneroso* implica que los siniestros y los gastos supéran a las primas y van a dar pérdida. Cuando es así, la Entidad tiene que ponerlo directamente en el P&L . Los contratos que no se pueden poner en un grupo, se pasan individualmente. Esto para cuando no tiene uinfo razonable o sustentable para definir a que grupo pertenecen.

Por último, pide segmentar los contratos con mas de 1 año de diferencia en su Fecha de Emisión.

Recapitulando, se deben segmentar las *Carterasd e contratos de seguros* en:
- Exposición as riesgos similars
- Tipo de onerosidad
- Fecha de emisión dentro del mismo año

Nota:
El reconocimeitno inicial de un contrato de seguros se dá cuando pasa lo primero de los siguientes eventos:
- Inicia la cobertura del riesgo
- Se devenga la primera prima (recordar que se devenga en el momento, no implica cobro/pago)
- En el caso de los contratos *Onerosos*, la fecha en el que el contrato se vuelva *oneroso*

# Valuacion de provisiones
## Resumen

La norma da 3 métodos para valuar y provisionar los contratos. Van al pasivo y se les incluye las *ganacias no devengadas* (que sería la prima no ganada, eb realidad).

Los 3 métodos son los siguientes:

- Building Block Approach (BBA) o conocido tambien como General Model (GM). Es el que va por defecto y se basa en 4 "bloques" y 2 categorias de "bloque" para su cálculo:
	- Fullfillment Cash Flows (FCF): Comprende los primeros 3 bloques y se centra en conocer el valor actual del contrato de seguros, contemplando un valor actualizado de todos los flujos (entradas y salidas) del mismo. Se divide en 3 bloques:
		 - Cashflows ( - ): Este es lo opuesto a lo que conocemos de Actuarial 2 como  resultado técnico ([[Conceptos de Actuarial 2]] ) sin la varte de reaseguro. Se suman todos los gastos y siniestros incurridos y se le restan las primas.  Este punto esta desarrollado  en <b><ins>Acá</ins></b>
		- Time Value Of Money (TVM): En el segundo bloque se descuenta los Cashflows para llevarlo a un valor actual. Dobla como un "Ajuste de riesgo financiero" y se aplica considerando que no se hayan incluido riesgos financieros dentro de los mismos. El valor presente de los Cashflows, se lo conoce como Best Estimated Liabilities (BEL). Este punto esta desarrollado en <b><ins>Acá</ins></b>
		- Risk Adjustment (RA):  Este es el ajuste de riesgos no financieros. La idea de esto es tener un margen de seguridad para evitar problemas de liquidez ante la incertidumnbre de los flujos de caja (osea, en caso de que agarres la cola de la distribución de siniestros).Este punto esta desarrollado  en <b><ins>Acá</ins></b>
	- Contractual Service Margin (CSM): Representa las ganancias futuras no devengadas. Esto se añade para que el cálculo al inicio del reconocim,iento del contrato de 0 y no negativo.Este punto esta desarrollado  en <b><ins>Acá</ins></b>
	
- Premium Allocation Approach (PAA) o Método Simplificado: Es una simplificación del BBA y es opcional (pero deseable) para la Entidad. Se puede aplicar siempre que el grupo de contyratos cumpla con los siguientes requisitos:
	- Periodo de cobertura no superior al año
	- Contratos no onerosos en el reconocimiento inicial
	- Se debe evaluar la posibilidad significativa de que el contrato se vuelva oneroso
	- La valoración por este ´metodo, no puede ser significativam,ente diferente al método BBA.
	==Investigar mas sobre este método==
	
- Variable Free Approach (VFA): Es una modificación del BBA para contratos con participación directa. Cambia como se calcula el MSC . Es un método obligatorio opera todo lo que cumpla estos requisitos:
	- Sus términos contractuales especifican que el tomador participa en una parte de un conjunto claramente identificado de elementos subyacentes. 
	- La entidad espera pagar al tomador un importe igual a una participación sustancial de la rentabilidad de los elementos subyacentes. 
	- La entidad espera que una proporción sustancial de cualquier cambio en los importes a pagar al tomador varíe con el cambio del valor razonable de los elementos.
		==Investigar mas sobre este método==


> 	 Recordamos:
> 		Los contratos de pariticipación directa sin aquellos que obligan a pagar al asegurado una rentabilidad basada en el valor razonable de los elementos subyacentes menos una comisión variable. 

### Building Block Approach (BBA)
Como se mencionó anteriormente, está comprendido por 2 bloques de cálculo, que a su vez son comprendidos por 3 bloques para el FCF y 1 bloque para el MSC.
#### Best Estimate Liabilities

Best Estimate Liabilities se le llama a los Cashflows descontados sumado al ajuste de riesgo no financiero.
##### Cahflows
Los flujos de los contratos de seguros están compuestos por diversos conceptos. Es aproximadamente el resultado técnico que vemos en Actuarial 2:
$$
RT_{Actuarial\ 2} = Prima_{emitida} - \Delta RRC_{t} - St_{pagados; t} - \Delta RSP_t  - IBNR - Reaseguros - Gastos(ALAE+ULAE) - Amortizaciones
$$
Pero, a diferencia de éste, no se contempla el reaseguro y se calcula de la siguiente forma:

Cashflows =
- ( + ) Premiums
- ( - ) Calims (Sineistros pagados, RSP, IBNR, IBNER y Siniestros futuros (?)) 
- ( + ) Salvage and Subrogations (Cobros por subasta y Cobro de deudas adquiridas por sineistros)
-  ( - ) Transaction Based Taxes (Premium Tax, fire tax, RST, HST, GST, etc...)
-  ( - ) Insurance Acquisition Cost (Gastos de adquisiciónm)
-  ( - ) Claim Handling Cost (Gastos por liquidación de siniestros)
-  ( - ) Policy Administration and mantenience Cosrs (Gastos de gestion y administracion)
-  ( - ) Allocation of Ficed and Variavle Overheads Directly Atributavble (ALAE ==(??)==)
-  ( - ) Paymento to policy holders resulting from optiones / guarantees theat are nos separated from the insuracnce contract
-
Conceptos que no entran:
- -Investment Returns
- Cash Flows Related to Reinsurance Contracts Held (these are presented separately under IFRS 17)
- Cash Flows related to Future Insurance Contracts
- Cash Flows relating to costs that are non-attributable (certain product development costs, training costs – expensed as incurred)
- Cash Flows from Abnormal Amounts of Wasted Labour or Other Resources
- Income Tax Payments and Receipts that the Insurer does not pay or receive in a fiduciary duty
- Cash Flows arising from Components separated from the insurance contract and accounted for under other accounting standards


Las Liabilities se pueden analizar en 2 grupos:
- Liabilities for Incurred Claims (LIC): Esto es el pasivo (y reservas) para cosas que ya pasaron  como  Siniestros pagados, RSP, IBNR, IBNER, Gastos, etc... . Esto se calcula como BEL + RA
- Liabilities for Remaining Coverage (LCR): Esto es el pasivo correspondiente a siniestros que todavia no pasaron. Para no vida, se puede usar BBA o PAA y para vida, dependiento del contrato, es BBA o VFA. El cálculo varía segun el modelo utilizado. ==Ver como se calcula esto solo==


![[Pasted image 20250208131223.png]]
Fuente: [[content/Notas de tesina/bin/insurance-ifrs17-Unpacking-LRC-LIC-Calculations zarasa lic y lrc.pdf]]

##### Time Value of Money (tasa de descuento)

La tasa de descuento tiene que ademas de reflejar el paso del tiempo, tener caracteristicas similares a los flujos y la liquidez del contrato. Tienen que ser consistentes en realción al plazo, la moneda y liquidez.

Da 2 enfoques:
- Top-Down: En este enfoque, se arma una cartera con caracteristicas similares a la de los pasivos de seguro. Luego, sobre la curva de ese activo, se eliminan los spreads no relevantes para esos pasivos (como el riesgo de crédito) y se hace un ajuste por diferencia en el importe, plazo e incertidumbre de los plazos.
- Bottom-Up: Busco una curva libre de riesgo y le agrego un "ajuste por la prima de liquidez"

Para mas infomacion, ver [[IFRS 17 Discount Rates]]

##### Ajuste de riesgo no financiero

Este ajuste depende del apetito al riesgo de la Entidad e intenta reflejar la incertidumbre de los flujos da caja. Se puede ver como los riesgos que no son financieros. 
Ejemplo:  Riesgo de Seguro, de suscripción, de siniestros, etc...

En resumen, el ajuste tiene que cubrir:
- Cumplir con una obligación que tiene un rango de resultados posibles derivados de riesgos no financieros (por ejemplo, que tuviera un 50% de posibilidades de ser 80 y un 50% de ser 120) o,
- Cumplir con una obligación que genera flujos de caja fijos con el mismo valor actual que el contrato de seguro (una obligación fija de 100)

Tiene un par de requisitos para la racionalidad. De la norma (Párrafo B91):

>La NIIF 17 no especifica las técnicas de estimación usadas para determinar el ajuste del riesgo para el riesgo no financiero. Sin embargo, para reflejar la compensación que requeriría la entidad por soportar el riesgo no financiero, el ajuste del riesgo para el riesgo no financiero tendrá las siguientes características:
	(a) riesgos con baja frecuencia y alta gravedad darán lugar a ajustes del riesgo mayores para el riesgo no financiero que riesgos con alta frecuencia y baja gravedad;
	(b) para riesgos similares, los contratos con una larga duración darán lugar a ajustes del riesgo mayores para el riesgo no financiero que contratos con duración más breve;
	(c) riesgos con distribución de probabilidad más amplia darán lugar a ajustes del riesgo para el riesgo no financiero que riesgos con distribución más acotada;
	(d) cuanto menos se conoce sobre la estimación actual y su tendencia, mayor será el ajuste del riesgo para el riesgo no financiero; y
	(e) en la medida en que la experiencia disponible reduce la incertidumbre sobre el importe y calendario de los flujos de efectivo, los ajustes del riesgo para el riesgo no financiero disminuirán y viceversa.

Adicionalemente, tiene un par mas de cosas a tener en cuenta:
- Se tiene que reevaluar cada vez que se calcula ==chequear==
- Se calcula a nivel cartera de seguros
- Tiene que tener en cuenta unicamente los riesgos derivados del contrato de seguro. Se excluyen los riesgos de reinversión, de casamiento y operacional. Normalmente para estimar esta parte, se utiliza el desvío del BeL
- Puede incluir efectos de diversificación del riesgo
- Tiene que estar por separado de los flujos y el descuento.
- Se tiene que mostrar el nivel de confianza utilizado para el ajuste.

Hay 3 metodologías comunmente aceptadas:
- Cost of Capital (el del WACC-CAPM)
- VaR
- T-VaR

==Completar con:==
- [[Maestría Ajuste al riesgo IFRS17.pdf]]
- [[content/Notas de tesina/Metodologias/bin papers metodologicos utiles/RA IFRS 17_An adaptation of Solvency 2 one-year aggregation into super papaer de risk adjustment con formulas.pdf]]
- [[content/Notas de tesina/Metodologias/bin papers metodologicos utiles/Risk adjustment RESUMEN CORTO.pdf]]

#### Contractual Service Margin (MSC)

Estos son los beneficios futuros que se van a reconocer a medida que se preste el servicio del seguro. Esta eliminar la noción de "Resevas negativas".
Ejemplo:
Tenes un contrato con siniestros esperados por 70 y prima a lo largo del contrato por 100. al inicio del contrato, tenes que reserva te puede dar negativa, pero el contrato no es oneroso.

En teoría, es el Valor Presente de las Futuras Ganancias y a medida que pasa el tiempo, dichas ganancias se van "amortizando". La tasa de descuento al inicio del reconocimeinto es algo que se conoce como Locked-in Rate (a tasa fija). 
Se tiene que guardar el CSM y el vector de tasas de interes para cada grupo a cada fecha de reporte con el objetivo de ser utilizados en el Roll-Forward del CSM en fechas posteriores.

El CSM se va a reconocer cuando en el reconocimiento inicial de los grupos de seguros, pase lo siguiente;
$PV(Outflow)-PV(Inflow)+Risk\ Adjustment\lt 0\rightarrow CSM$

Roll Forward para el CSM:
Opening CSM (t-1)
- ( + ) CSM for New Contracts Added to the Group
- ( + ) Interest Accreted on the CSM (ganancias por la tasa de interes fija)
- (+/-) Changes in Fulfilment Cash Flows Relating to Future Service
- (+/-) Effects of Currency Exchange Differences on the CSM
- ( – ) Amount of CSM Recognized into Profit or Loss (amortizacion del CSM que va al P&L del periodo)
Closing CSM (t)

Ejemplo:

| **CSM Beginning of Period:**                                  | **1,000,000** |
| ------------------------------------------------------------- | ------------- |
| (+) CSM from New Business                                     | 600,000       |
| (+) Interest Accretion on CSM                                 | 48,000        |
| (-) Expected Premiums                                         | (250,000)     |
| (+) Actual Premiums                                           | 252,500       |
| (+) Expected Premium Tax                                      | 6,250         |
| (-) Actual Premium Tax                                        | (6,300)       |
| (+) Expected Acquisition Expenses                             | 65,000        |
| (-) Actual Acquisition Expenses                               | (60,000)      |
| (+) Expected Investment Components                            | 30,000        |
| (-) Actual Investment Components                              | (25,000)      |
| (+/-) Experience Adjustments / Assumption Changes on BEL + RA | (160,000)     |
| (+/-) Currency Exchange Differences on CSM                    | 0             |
| (-) CSM Amortized into P&L                                    | (149,000)     |
| **CSM End of Period:**                                        | **1,346,450** |


Sobre contratos Onerosos:


Para los contratos onerosos, el equivalente se llama Loss Component (LC) y se reconoce en el P&L cuando:
$PV(Outflow)-PV(Inflow)+Risk\ Adjustment\gt 0\rightarrow LC$

==Buscar info de esto. Es uno de los temas mas hablados de la IFRS 17 pero al ser 100% contable, no busque metodología==


## Premium Allocation Approach (PAA)

Es una suimplificación del BBA.
Requisitos:
- Cobretura del contrato no superior a 1 año
- Medición del pasivo no sea signifiactivamente diferente que por el método BBA
- En el momento inicial, el contrato tiene que ser oneroso
- Se tiene que evauluar una posibilidad **Significativa** de que el contrato se vuelva no oneroso.

Reconocimiento Inicial:
- Se puede optar por reconocer los gastos de Adquisición directamente en el P&L o diferirlos de forma sistemática a lo largo del tiempo.
$$
Pasivo = Primas\ Recibidas - Gastos\ de\ Adquisicion\ (sol\ reconocimiento\ previo\ en\ P\ y\ L)
$$
- Salvo existencia de financiación significativa, no contempla el valor tiempo dinero y por ende, el riesgo financiero

Reconocimiento Posterior:
$$
Pasivo = Pasivo\ Previo + Primas\ Recibidas - Gastos\ de\ Adquisicion\ + Amort.\ Gastos\ de\ Adquisicion + Ajuste\ Financiero - Ingreso\ Reconocido - Componente\ de\ Inversion\ pagado\ o\ transferido\ al\ pasivo\ por\ reclamaciones\ incurridas
$$

Caso del contrato oneroso:
Si in caulquier momento de la coberture, un grupo de contratos se vuelve oneroso, hay que reconocer la pérdida. De forma:
$$
Perdida = Flujo\ de\ Efectivo\ restante - Pasivo\ por\ cobertura\ restante
$$
En resumen, se hace un BEL sin el ajuste financiero y se le aplica el Ajuste de riesgo no financiero.

## Enfoque Variable Fee Approach (BFA)

Cambia como se calcula el MSC. Viene de la mano de los contratos que obligan a pagar al asegurado una rentabilidad basada en el valor razonable de los elementos subyacentes menos una comisión variable

![[Pasted image 20250207181054.png]]

Requisitos:
- Que los términos del contrato especifiquen que el tomador participa en una parte de un conjunto claramente identificado de elementos subyacentes claramente identificados.
	- No existe un conjunto claramente identificado cuando:
		- La entidad puede cambiar los elementos subyacentes para determinar su obligación con el tomador con carácter retroactivo.
		- No hay elementos subyacentes identificados, incluso si el tomador puede obtener una rentabilidad que refleje el rendimiento de la misma o de un conjunto de activos que esta mantiene. ==?==
- La entidad espera pagar al tomador un importe igual a una participación sustancial de la rentabilidad de los elementos subyacentes.
- La entidad espera que una proporción sustancial de cualquier cambio en los importes a pagar al tomador varíe con el cambio del valor razonable de los elementos

Margen de servicio contractual
La formula inicial es igual que en BBA
El reconocimeinto posterior se trata de la siguiente manera:
$$
MSC_t = MSC_{t-1} + EfNC\ \pm Part_t\ \pm \Delta Cashflow\ \pm EfVc - MSCperdida_t  
$$
Donde:
- $MSC_t$ es el MSC del periodo t
- $EfNC_t$ es el efecto de los nuevos contratos
- $Part_t$ es la participación de la entidad en el cambio del V.R. de los elementos subyacentes
- $\Delta Cashflow$ son los cambios de los flujos de efectivo de cumplimiento relacionados con el servicio futuro
- $EfVc$ es el efecto de las diferencias de cambio (en los contratos viejos)
- $MSCperdida_t$ es la cantidad de MSC reconocida en P&G por los servicios prestados en el periodo

Notas extra:
- El cambio de la obligación de pagar al tenedor un importe igual al valor razonable de los elementos subyacentes no se relacionan con los servicios futuros, por lo que no entran en el MSC
- Los cambios en la participación de la entidad en el valor razonable de los elementos subyacentes, los cambios en los flujos de cumplimiento futuro que no varían sobre la base de las rentabilidades sobre los elementos subyacentes  (EJ: Garantías financieras) y los cambios en los flujos derivados del valor del dinero y riesgos financieros son reconocidos en el MSC como parte de la variabilidad de la tarifa futura. (Modelo general: PYG)


