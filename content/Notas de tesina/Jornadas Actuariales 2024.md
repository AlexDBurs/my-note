---
title: 'Jornadas Actuariales 2024'
draft: false
tags:
  - Nota
---

Fuente: https://www.youtube.com/watch?v=MCGv8oA_4pQ&t=500s
Minuto 8:00
Temas a tocar en el video:
- Normas contables de Info Patrimonial (IFRS17)
	- Ajuste por riesgo no financierom, de las partidas de las cuentas, de los pasivos de seguros
- Inteligencia Artificial (Modelos GLM para reservas (?))
- Seguros Personales
- Reaseguro (cartera optima), como gestión de riesgo Empresario del reasegurador
	- Gestión de riesgo empresario ERM 
	- Normas de Basilea
	- Solvencia 2
	- Normas ISO de gestión de riesgo
- Leyes de Mortalidad (Se sigue usando?)
	- Seguridad Social
	- Longevidad
- Propuesta Nuevo Plan de Estudio
Capacitaciones:
- RTICI
- Carteras de inversiones
- Análisis de Previsión por Incobrabilidad (PCE por Niif9)
- Requerimientos de capital o constitucion de pasivos en lo referente a los riesgos (los normales de finanzas)
- Art 16 de la ley 2488 (la que dice qué hace un actuario)
#### Actuarios: una profesión con Propósito
- Riesgos Climáticos y reaseguros
- Normativa Dora (Solvencia 2 de la informática)
#### IFRS17 Antes y Después
- Aspectos claves (8 segmentos)![[Pasted image 20250122162943.png]]
	- Comprensión de la norma
		- Cuando apliocarlo en la realidad. La norma esta diseñada para paises con tasas de interes baja (momentos de coyuntura de las tasas de los tipos de cambio)
		- Dice que hay que hacer pero no como hacerlo
		- Hace falta un gobierno corporativo / comite para traducir lo que hay que hacer a como lo voy a a hacer yo
	- Evaluación del impactoLa siguiente foto es una matriz de evaluación de impacto de los diferentes cambios (incluyendo al NIIF9). Ver las aristas del análisis![[Pasted image 20250122163619.png]]
		- IFRS 17 va por contratos y empieza por la SAL (Separación, Agrupación y Límites de los contratos bajo esta nueva metodología). Separo lo que tengo, vuelvo a agrupar y establezco límites.
	- Modelos Financieros: Tiene que convivr con Solvencia 2. Primero ver Solvencia 2 y luego IFRS 17
		-  Solvencia habla de la aseguradora. Es la parte del balance económico y consumo de capital
		-  IFRS 17 habla de contrato de seguros y se basa en la cuenta de resultados. (Mas que nada para ver si la Entidad es solvente o no)![[Pasted image 20250122164236.png]]
			- El contrato de rea X/L suele dar pérdida (?)
	- Procesos y controles internos
		- Tienen que estar bien documentados
		- Gran problema: Preparar la data
		- ![[Pasted image 20250122165006.png]]
		- Saber contar (Alto Claro y Breve)
			- Saber chamuyar
	- Sistemas de información:
		-  Contabilización y automatizaciones
		-  Antes: Cobro 100 y provisiono en base a 100. Ahora: Cobro 100, el riesgo es del 97%, provisiono en torno al 97.
	- Capacitación del personal
		- Ver como jugar con la norma y explicarselo al auditor de forma que no te observen...
	- Planificación:
		- Como suena
- Lineas de trabajo
	- ![[Pasted image 20250122170127.png]]
	- Veracidad de los contratos, agrupacion, metodologias, etc...
	- ![[Pasted image 20250122174813.png]]
	- Manual:![[Pasted image 20250122175003.png]]
	- Libro recomendado para leer (hobbie). Contra los dioses (La historia de riesgo)
	- Revisar la Normativa Dora y como interactúa con las IFRS
#### Modelos lineales Generalizados
Valores de Shapeley (Esta bueno ver. Esta en 1:30:00 aprox)
- La idea es determinar que variable aporta mas al modelo generando conjuntos de variables (del modelo final) y comparando los resultados estimados para determinar los valores marginales de cada variable depenmdienta de forma aislada
	- Ver que vabiables aportan mas al modelo final
	- Algoritmo muy costoso. Tiene que correr los modelos 2 a la n veces
- Asume que hay independencia entre las variables?
- Utilidad en los modelos no lineales
- Caida de cartera de autos en su compañía (la de los españoles que exponen):![[Pasted image 20250122183913.png]]
- Se Usa para encontrar modelos con menos variables:![[Pasted image 20250122184408.png]]
- Proximas lecturas (diseñadas para redes neuronales):![[Pasted image 20250122184513.png]]

#### Nuevas soluciones en el reaseguro
Nuevas estructuras de reaseguro (Reaseguro estructurado)
- 3 Esquemas 
	- Herramienta de manejo de capital
	- Soluciones de liquidez
	- Soluciones de eficiencia
- Reaseguro Estructurado 
	- Diferencia contra erl tradicional es que ne le tradicional hay mas clausilas estandard, ajustar limites, etc...
	- Aca son soluciones especificas a un problema puntual que tiene la cedente 
		- Problemas de capital.
			- Compañía con un crecimiento muy acelerado
			- Necesita un aporte de capitalm de 20kk
			- Hay una opcion a travez del reaseguro estructurado
			- Reasegurador nos da los aportes de 20KK y nosotros despues nos comprometemos a devolverselo
				- A partir de un % del resultado
				- A partir de un % de la prim,a
				- O de diferentes maneras
			- A partir de esto, se hace un ewsquema a medida.
		- Puede ser por temas de capital, liquidez, reservas, etc...
- Objetivos: 
	- Minimizar necesidades de capital adicional
	- Establecer menos volatilidad con tal de dar mayores garantías de dividendo
- Metodologías:
	- Se parte de los objetivos de la Cedente para dar soluciones al riesgo que estan expuestas
- Tipos:
	- Reaseguro Retroactivo
		- La cedente transfiere los pasivos que haya reservado a cambio del pago de Prima. También finaliza su responsabilidad sobre esas deudas con el pago de la prima al reasegurador
		- El costo del programa es el flujo de las reservas descontadas mas un recargo de seguridad a favor del reasegurador.
		- Ejemplo: Cut-Off. Hay siniestros abiertos, reservas, etc... y se quiere dar un corte de responsabilidad. La cedente le muestra la reserva de todos los sinestros abiertos al reasegurador y este analiza y s pone de acuerdo con la asguradora como van a manejar el quiebre. Dandole reservar descontadas (temporalmente) a la aseguradora par que afronte los eventuales siniestros futuros. Cedente hace 2 cosas. Invierte lo que recibió de la rea e intenta cerrar los casos que tiene abiertos para conseguir que el importe pagado sea menos a lo adelantado por el rea.
			- En este caso, esto es la inversa. La Cedente tiene reservas que transfiere al la rea. Este le hace responsable de los riesgos y recibe una prima de la cedente. Tiene que invertir las reservas e intentar tener un margen de seguridad
		- Se puede aplicar a RSP, IBNR o ambas
		- Se puede aplicar a las Reservas retenidas en caso de que la Cedente tenga un Contrato de Rea preexistente o a las Reservas Brutas en el caso de que la linea de negocios sea 100% Retencion.
		- Ventajas para la Cedente:
			- Evita el incremento de pérdidas por aumento de las reservas
			- Puede liberar Capital al transferir al Reaseguradao. Caso contrario, el mismo debería estar inmobilizado para afrontar responsabilidades
			- El capital librerado se puede invertir (Chchos los CFO)
			- Disminucion de los gastos de liq de stos
		- Para el reasegurador el resultado es la prima que sería Simil a Cut-Off.
			- Va a intentar terminar en resultado positivo
	- XL Multianual (Excess Loss)
		- Mas aplicada a tema de costos y agarrar los costos anticipadamente
		- Transferencia de riesgo: El funcionamiento y estructura es similar a un Exceso de Pérdida
		- Existe previsibilidad: Se fija el costo (o tasa) de la cobertura por un periodo multianuial
		- Existe la participación por utilidades em caso de buena siniestralidad.
		- Tiene un mecanismo de ahjuste
			- Cuando cambia la exposicion de la cartera
			- Permite financiar a travez del tiempo las perdidas esperadas de la Cedente (ya que la tasa 3esta fijada por varios periodos)
			- La Cedente tiene derecho a cancelar el contrato al final de cada año si la cuenta es positiva
		- Ventajas:
			- Ademas de cubrir el risgo de suscreición, cubre el riesgo del tiempo o del interes (riesgo de tasa)
			- Prevision en los costos por fijar la tasa del contrato
			- Posee participacion en la utilidades
			- Posibilidad de cancelar el contrato en caso de que la "Cuenta Experiencia" sea positiva (Comopuesta por Primas, Siniestros Cedidos Y Margen del REasegurador)
	- Retención de Fondos
		- La Cedente retiene una parte o la totalidad de las primas que le corresponde a al reasegurador y las mantiene en una cuenta separada
		- Dichos importes se utilizan para cubrir siniestyros futuros y se pueden invertir. Los intereses generados van al reasegurador
		- Dicha Modalidad, brinda seguridad a la cedente en el cumplimiento de sus obligaciones, alivia problemas de liquidez y simplifica el pago de siniestros, ya que a medida que surjen reclamos, la cedente utiliza los fondos retenidos para pagar los siniestros 
		- Ventajas: 
			- Tema de Liquidez
			- La cedente tiene control sobre toda la prima con cobertura del reaseguro
			- Reduce el riesgo de déficit de flujo de caja por la demora en el recupero de siniestros (si fueran por cuenta trimestralk)
			- Reduce el riesgo de default del reasegurador al no ceder la prima
			- Ayudan a la cedente a cumplir con los requisitos regulatorios (Las primas se cuentan con un activo)
			- Mayor solvencia al reasegurador ya que los fondos retenidos estan en una cuenta separada que devenga intereses y no en forma de reserva
			- Si el reasegurador que contratas, le baja el rating, vos tenes la prima y tenes menos riesgo de que lo pierdas si entra en defaukt
		- Desvntajas:
			- La Cedente tiene Riesgo de Inversipón
			-  Complejidad en ka genstion y administracion de este tipo de esquemas
			- Riesgo de iNflacion:; si la tasa de inflacion aumenta mas de lo esperado. el valor real de los fondos retenidos disminuye, provocando dificultades con los reclamos futuros, ya que, el monto de los rteclamos ne general acompaña a la inflacion
			- Implicancias impositivas: Las primas retenidas no estan sujetas a impuestos, ya que, el reasegurador no las recibe fisicamente. Sin embargo, la cedente retieme los ingresis por inversiones asociados que están sujetas a gravámenes
	- Reaseguro financiero (?)
	- Hay mas pero Christian solo presenta esos 3