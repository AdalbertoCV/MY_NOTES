# Capa enlace de datos

- Lo maximo que puede medir una trama son 1500 bytes
- Se encapsula (mete en tramas) y se debe respetar el tamaño del MTU
- Se usa el acuse de recibo (ack) para asegurar que los datos se envian correctamente
	- Se envian tramas y se reciben ACK

# Direcciones fisicas

- Se utilizan en las redes LAN
- Son las direcciones necesarias del emisor y el receptor
- Estan escritas en notacion hexadecimal
- El origen siempre sera una direccion unicast
- El destino puede ser unicast, multicast o broadcast

# Deteccion de colision CSMA

- Si estamos en una red, la computadora debe consultar si hay algun otro equipo enviando tramas o si el
	canal esta libre

- Las colisiones suceden cuando se detecta el canal libre al mismo tiempo por mas o dos computadoras.

- Pueden haber hasta 16 reintentos de envio si hay colisiones.

- El algoritmo de backoff, ayuda a solucionar las colisiones, dando un tiempo a los procesos para revisar si el canal
	ya se encuentra libre.

- RTS - CTS: Es la sincronizacion para enviar y recibir tramas en el estándar 802.11

# Control de flujo

- Se puede utilizar un buffer, para ir guardando las tramas si un error es encontrado, esto evita descartarlas y
	se puede ahorrar tiempo.
	
- El emisor solo esta "ocupado" durante el tiempo de transmision.

- El tamaño de ventana se refiere a cuantas tramas serán enviadas.

# Deteccion de error

- Cyclic redundancy check
- Checksum

#Ejemplo Error detection

- Paso 1: 
		Dataword = 1001
		Polinomio Generador (Divisor): 6(x) = 1011 = x^3 + x + 1
- Paso 2:
		División -> datos + ceros sobre divisor
		 
		         1010
		     __________
		1011 |1001000
		     -
			  1011
			  ____
			   0100
			  -
			   0000
			   ____
			    1000
			   -
			    1011
				____
				 0110
				-
				 0000
				 ____
				  110 -> residuo
				  
n = k + r
n = 1001110 -> Trama

dividor la codeword sobre el divisor:

            1010
        _____________
   1011|1001110
         1011
		  0101
		  0000
		   1011
		   1011
		    0000
			 000 -> Sindrome