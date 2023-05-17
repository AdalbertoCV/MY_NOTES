# Capa de red

- cada campo de un paquete tiene cierta longitud, repartiendo asi los 32 bits totales.

- IHL: Longitud del encabezado (en multiplos de 4)

- Tipo de servicio: se mide en 8 bits (sirve para decir si un paquete en particular tiene preferencia sobre otro)
   - bits 0 a 2 Precedencia.
   - bits 3: 
   - bits 4: Solicita una alta velocidad
   - bits 5: Solicita amplia fiabilidad
   - bits 6 a 7: No se usan.

- Longitud total: Es la longitud total del mensaje que debe fragmentarse en la mayoria de los casos para poder enviarlo en MTU maximo de 1500B

- Identificación: Numero unico por transmision. (Para poder distinguir el paquete). 16 bits

- Fragment offset: 
			- DF: no fragmentado
			- MF: Esta fragmentado, indica quien es el ultimo, y quien no es el ultimo. mf=1, hay mas, mf=0, es el ultimo.
			- Offset: es el primer byte de cada fragmento.

- Tiempo de vida: Cuanto vive un paquete. Si el TTL expira, el paquete se va a eliminar.

- Protocolo: Nos dice que hay dentro del paquete.(UDP/TCP son los mas comunes)

- Checksum: 16 bits, nos ayuda a hacer una comprobacion de error en el encabezado del paquete.

# Algoritmos de actualizacion de ruteo (enrutamiento)

- Tabla de enrutamiento
	-Destino: es el destino al que se quieren enviar los paquestes
	-Metrica
	-Linea de Salida
	
Se busca que estos algoritmos tengan ciertas propiedades como Optimizacion, Simplicidad y bajo costo, Solidez, Flexibilidad, Estabilidad y Convergencia Rápida

# Metricas

- Ancho de banda

- Retardo

- Carga

- Confiabilidad

- Numero de saltos

- Costo

# Protocolos representativos de TCP/IP

- Adress resolution Protocol: Es el protocolo mas importante sin el cual, no se podria hacer nada en la red.
	permite conocer la direccion mac del host al que queremos acceder.
	
El arp hace un broadscast para conocer la direccion mac del destino.

- DHCP (Dynamic host configuration protocol): Se basa en broadcast, es el modem de una red de casa normal. Si no hay DHCP
	se asigna automaticamente la red 169.254.x.x
	
- ICMP (Protocolo de control de mensajes de internet): Avisa cuando ciertas cosas pasan en la red.



