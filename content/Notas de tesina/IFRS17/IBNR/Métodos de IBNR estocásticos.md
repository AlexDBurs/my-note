---
title: Métodos de IBNR estocásticos
draft: false
tags:
  - Nota
  - Metodología
---

Fuente: https://www.revistaespacios.com/a19v40n18/a19v40n18p10.pdf
Lectura Adicional: https://app.mapfre.com/ccm/content/documentos/fundacion/cs-seguro/libros/Metodos_estocasticos_de_estimacion_de_las_provisiones_tecnicas_en_el_marco_de_Solvencia_II.pdf
## Métodos Estocásticos (los del paper principal)
### Distribución libre de Mack (Mack, 1993)
Mack (1993) introdujo este modelo para obtener la desviación típica del método Chain Ladder.

El método propuesto por Mack se basa en la obtención del error cuadrático medio de la reserva, no obstante, presenta como principal limitación la imposibilidad de aplicar este método cuando la estimación de pagos por siniestros en un año de desarrollo es inferior a la estimación de pagos por siniestros en el año de desarrollo anterior, es decir, cuando existen cobros por siniestros por parte de la entidad aseguradora superando estos a los pagos en un mismo año .

> En Criollo,  si el factor de desarrollo es menor a 1, no se puede usar. Esto asumo que pasa cuando tenés algún cobro en el medio del desarrollo del siniestro y este es mayor al desarrollo en sí. Es una anomalía. 

La explicación del método es la siguiente:
Chain Ladder propone las siquientes hipótesis:
1. Existen factores de desarrollo mayores a "0" tal que la multiplicación de los mismos me da el desarrollo promedio de un siniestro para cierto año de ocurrencia
2. Cada sinestro es independiente por año de ocurrencia
A partir de esto, Mack propone 3 supuestos:
1. Supuesto 1 de C-L
2. La estimación de los factores de desarrollo es insesgada  y sin correlación entre ellos. 
	1. Recordar que en estas demostraciones, los  factores de desarrollo se calculan como el cociente entre la sumatoria de los siniestros con x+1 años de desarrollo y la sumatoria de los siniestros con x años de desarrollo. Gráficamente:![[Pasted image 20250119232808.png]], siendo $C_{i,j}$ , La suma de siniestros incurridos para el Accident Year "i" con "j" años de desarrollo.
	2. Vale aclarar, que en el ejemplo del Mapfre, lo hace con Stos. Incurridos
3. La varianza para $C_{i,j+1}$ , condicionado a la info disponible es:![[Pasted image 20250120004516.png]]
	Esto sale de:
	Para estiamar el desvio de la estimación de las reservas, se busca el error asociado a la reserva por AY (Accident Year).  
	
	Utiliza el MSE (error cuadrático medio) definido como la diferencia del cuadrado entre la estimación del siniestro por AY y  su valor real (dado que es un dato observable, etc...).  Demuestra que el MSE para la estimación de siniestros por AY es igual al MSE de la reserva de ese mismo AY.
	
	![[Pasted image 20250119234933.png]]
	![[Pasted image 20250119234944.png]]
	Donde R es la reserva como diferencia del siniestro ultimate y el pagado.
	El problema de esto, es que hay que hacerlo para cada $\hat{C}_{i,j}$ , así que hay que seguir desarrollando la fórmula.  
	Para toda variable aleatoria "X" se verifica que:
	![[Pasted image 20250120001550.png]]
	Donde, 
	- "X"  es una VA
	- "a" es un desvío de la función
	Aplicado a lo que vimos recién:
	![[Pasted image 20250120001724.png]]
	De esta forma, encontramos una forma mas amena de calcular las cosas. El tema de esto es que no sabemos como es la varianza de ${C}_{i,j}$ . Sabemos que los factores individuales de desarrollo  ($\hat{f} \ = \ C_{i,j+1}/C_{i,j}\quad /...$)  son los que ponderan los siniestros hasta el final de su desarrollo, entonces, la varianza para estos, debería ser inversamente proporcional a la de ${C}_{i,j}$.
> 	En criollo,  a medida que te alejas del valor real, la estimación tiene mas varianza. Si el Factor individual de desarrollo es lo que me mueve en el tiempo el sto, y tiende a 1, el resto del cambio del siniestro se explica por la varianza.

Y es acá donde propone la varianza para $C_{i,j+1}$ , condicionado a la info disponible es:![[Pasted image 20250120004516.png]]
El unico problema es que no conoce $\hat{\sigma}^{2}_{j}$  . Para ello, plantea un estimador inssesgado de la varianza:
![[Pasted image 20250120005307.png]]
Al ser insesgado, pierde 1 grado de libertad y no deja estimar el valor de la ultima varianza para el ultimo año de desarrollo. Es decir, funciona para j entre 0 e I-2, pero no para j = I-1 .

Para esto propone 2 soluciones:
1. Si el factor anterior es 1, y esperas que el sto no tenga mas desarrollo, $\hat{\sigma}^{2}_{I-1}=0$
2. Si no se cumple 1. , lo tenes que estimar extrapolandolo como una sucesión de valores de $\hat{\sigma}^{2}_{j}$, que al salir de una división de valores, se debería comportar como una función exponencial (hay que validarlo esto. No se supone).  Asumiendo que esté bien, se plantea una regresión GLM (modelo lineal generalizado) tal que:
	![[Pasted image 20250120010137.png]]
	Para que la varianza no sea explosiva (es decir, que se mantenga el ritmo de la caida), se necesita asumir:
	![[Pasted image 20250120010357.png]]
	Expresado de otra forma:
	![[Pasted image 20250120010509.png]]
	Ya conocida la forma de $\hat{\sigma}^{2}_{j}$ , el resto de los datos ya los tenemos y hay que estimar el MSE de las reservas por AY. 
El libro pone 2 formulas mas que dan el MSE de las reservas directo:
![[Pasted image 20250120010906.png]]
![[Pasted image 20250120010916.png]]
#### Ejempo del mapfre
![[Ejemplo IBNR Mack.pdf#height=300]]






### Método basado en la técnica de Bootstrap 
Resumen: Esto es basicamente ChainLadder pero lo que hace es, una vez que obtiene los FDA (promedio ponderado), los aplica para atras y de la diagonal principal, saca los siniestros acumulados por AY.
Despues, desacumula el triángulo y  arma el residuo de Pearson (supone una distribución de los errores como Poisson Sobredispersada) para cada punto.
Recordando, los residuos se calculan así:
$$
\hat{r}_{i,j} = \frac{c_{i,j}-m_{i,j}}{\sqrt{m_{i,j}}} 
$$
	Donde: 
		|$\hat{r}_{i,j}$ es el residuo de Pearson
		$m_{i,j}$ es el valor desacumulado de los siniestros AY por año de desarrollo
		$c_{i,j}$ es el valor desacumulado de los siniestros AY por año de desarrollo obtenido por los factores FDA
	Ene ste punto tambien hay que sacar el factor de escala para calcular la varianza de la Poisson Sobredimensionada (es la sumatoria de los errores cuadrados sobre observaciones menos parámetros estimados)

El resultado es un triangulo de errores de estimación. 
Ahora entra la diferencia entre Englany y Verral (1999) y England (2002) . Este ultimo, utiliza los residuos ajustados de Pearson, por lo que queda $\hat{rp}_{i,j}=\sqrt{\frac{N}{N-p}}*\hat{r}_{i,j}$ . 
A esto, se le aplica un remuestreo con probabilidades 1/n (si, implica que un error en AY2020, desarrollo 1 puede aparecer en  AY2024, desarrollo 0), se  desarma la formula de los residuos para obtener los valores de $c_{i,j}$ , se calculan los FDA y una nueva reserva. Se hace esto una cantidad suficiente de veces y se observa el error asociado al proceso.
Descripción mas clara (Sacado de la fuente):
![[Boostrapping_fuente.pdf#height=300]]

#### Ejemplo del Mapfre
==Por hacer==

### Metodos basados en regresiones (ML)
Considero que hay dos divisiones relevantes pero no encontré un paper que valide mi categorización. La primera división se basa en :
- Modelización tradicional: Mediante un GLM y mucha matemática, se obtiene la distribución de los siniestros y se proyectan a futuro. Es lo que está explicado en 
