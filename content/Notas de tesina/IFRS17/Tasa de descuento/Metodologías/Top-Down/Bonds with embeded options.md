---
title: 'Bonds with embeded options'
draft: false
tags:
  - Nota
  - Metodología
---
Fuente: https://www.youtube.com/watch?v=5zZuTYmjxW8&t=0s

Sobre los bonos con opciones asociadas:
- Siempre son mas baratos que su contraparte sin opción ya que, el emisor los puede comprar cuando tenga gana o vos lo podes vender cuando quieras (según corresponda)

- El call/put es del lado del emisor. Incluye:
	- Call Provisions: Emisor tiene un call en el bono
		- Puede tener periodo de gracia
	- Put Provisions: Tenedor tiene un call en el bono
		- Puede tener periodo de gracia
		- Puede ser un Put que obliga al emisor extender la duración del bono
	- Conversion Options: Opción de convertir el bono en una acción
	- Caps: Limita la cantidad de rendimientos que tiene que pagar el bono (Es parecido a una call pero con la tasa de interes)
	- Estate Puts: Paga cuando se muere el tenedor
	- Sinking Fund: Tiene un fondo de ahorro. Usualmente tiene una Call Provision tambien para las 2 cosas (fondo + bono)

- La valuación es como tener un portfolio con un bono y una opción. Un bono con una call se puede representar de la siguiente forma:
![[Pasted image 20250218205736.png]]
El gráfico muestra la relación entre un bono con un call y su contraparte sin ficha opción.  El bono con opción tiene convexidad negativa siempre que sea rentable ejecutar el call. 
Esto puede pasar, por ejemplo, cuando tengo un bono de 100$ que paga 10% anual con Call Provision. Si la tasa de interés de referencia baja a 3%, al emisor no le conviene pagarme 10%, asi que ejecuta el call y emite otro bono por 3%.  Ese es el valor de la opción que forma un triángulo a la izquierda del gráfico. 
Esto se da porque 
Si la tasa crece, ambos bonos deberían tener la misma curva porque no se ejecuta el call.
- Para un Put Provisions:
![[Pasted image 20250219000353.png]]
Es igual pero alreves. La opción se ejecuta cuando sube la tasa y el precio queda por debajo del precio inicial. Ejemplo, compras un bono a 100, baja a 90 porque sube la tasa y ejecutas el put ganando 10.

En el video muestra como se valúan con el modelo binomial de 5. Calcula un árbol para el bono sin opción y otro para el que tiene la opción. La diferencia entre ellas en el precio de la opción.