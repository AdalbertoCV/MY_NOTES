# Ejercicios de la capa Física

Ejercicios para segundo examen de redes de computadoras.

# Conversiones

# hz
- 1000 hz -> 1kHZ
- 1000000 hz -> 1mHZ
- 1000000000 hz -> 1GHZ

# bps
- 1000 bps -> 1kbps
- 1000000 bps -> 1mbps
- 1000000000 bps -> 1Gbps

# bytes 
- 1024 B -> 1KB
- 1024 X 1024 B -> 1MB
- 1024 X 1024 X 1024 -> 1GB
- 1 B -> 8 bits

# Formulas

# BitRate en Nyquist Theorem

Tasa de transferencia maxima (BitRate) = 2  Log2 L  (bits/seg)

	- L: Numero de niveles 
	
	- Bits/seg: Ancho de banda
	
# BitRate en Shannon Theorem

Tasa de transferencia maxima (BitRate) = B Log2(1 + SNR)

	- B: Ancho de banda
	
	- SNR: relación señal ruido
	

# Troughput 

Troughput =  (numero de frames x ancho de banda) / 60 segundos


# Formulas Latencia

Latencia = Tiempo de propagacion + tiempo de transferencia + C (tiempo de procesamiento y encolamiento)

Tiempo de propagacion = distancia / velocidad de propagacion

Tiempo de transmision = tamaño del mensaje / ancho de banda

# Problemas

# 1.- Si se tiene un canal sin ruido con un ancho de banda de 500MHz, determine el máximo teórico de las tasas de transferencia del canal con un número de niveles de 3.


ancho de banda = 500Mhz
niveles = 3

Br = 2 x Log2(3) x (500Mhz (1000000 hz/ 1 Mhz)) =  2 x 1.58 x 500000000 b

Br = 1.58 Gbps


# 2.- Si se tiene un canal sin ruido con un ancho de banda determinado por el medio físico de UTP cat 5e, determine el máximo teórico de las tasas de transferencia del canal con un número de niveles de 2.

ancho de banda UTP5e = 100Mhz
niveles = 2

Br = 2 x Log2(2) x (100Mhz (1000000 hz / 1 Mhz)) = 2 x 1 x 100000000 b

Br = 200 Mbps


# 3.- Si se tiene un canal con un medio físico de cable coaxial,  determine la tasa de transferencia del canal contemplando una relación señal ruido de 35 db.

ancho de banda cable coaxial = 500Mhz
SNR = 35

Br = 500Mhz x Log2(1 + 35) =  500Mhz (1000000 hz/ 1 Mhz) x Log2(36) = 500000000 b x 5.17

Br = 2.58 Gbps


# 4.- Si se tiene un canal con una frecuencia mínima de 200MHz y una frecuencia máxima de 4700MHz,  determine la tasa de transferencia del canal contemplando una relación señal ruido de 51 db.

ancho de banda = (4700 Mhz - 200Mhz) = 4500Mhz
SNR = 51

Br = 4500Mhz x Log2(1 + 51) = 4500Mhz (1000000 hz/ 1 Mhz) x Log2(52) = 4500000000 b x 5.7

Br = 25.6 Gbps


# 5.- Si tengo un mensaje de 110 MB sobre una línea de comunicación de 10000Km de distancia. Determine el tiempo necesario para “mandar” dicho mensaje si se tiene un performance de la línea de 20Mbps y un troughput de 10Mbps,y una velocidad de propagación de la señal de 300 000 m/s. Determine también el tiempo de propagación de la señal con base en estos datos. Al final mencione ¿qué proporción  del canal se está aprovechando?.
 
tamaño de mensaje = 110 MB
distancia = 10000Km
Troughput = 10Mbps
velocidad de propagacion = 300 000 m/s

 
Latencia = Tiempo de propagacion + tiempo de transmision 

Tiempo de propagacion = 10000Km / 300000 m/s  = 10000Km (1000 m / 1Km) / 300000 m/s = 10000000 m / 300000 m/s

Tiempo de propagacion = 33.3 seg

Tiempo de transmision = 110MB / 10Mbps  = 110MB(1024 KB/ 1MB)(1024B/1KB)( 8 b/ 1B) / 10 Mbps (1000000 b / 1Mb)
                      = 922746880 b / 10000000 bps = 92.27 seg
					  
Latencia = 33.3 seg + 92.27 seg = 125.6 seg = 2.09 minutos


# 6.- Si tengo un archivo  de 9GB sobre una línea que proporciona una velocidad de 40Mbps, y tengo un RTT (Round trip time o RTD round trip delay)  de 500ms en un solo bit. Determine ¿cuántos bytes puedo enviar en el retardo de ida?, ¿en cuánto tiempo recibiré un ACK (asumiendo que se envía en un tamaño despreciable)?

velocidad = 40000000 bps
tamaño de archivo = 9gb
RTT = 500ms

Tiempo de ida = RTT/2 = 250ms

cantidad de bytes ida = 9GB(1024 MB/1GB) x 0.25 s = 2304MB = 2.25 GB en el retardo de ida

el ack se recibe en 0.5 segundos debido al RTT


# 7.- Por el momento se están mandando 2000 tramas de 10kB por minuto. ¿Cuál es el throughput de la red si el ancho de banda es ideal es de 20Mbps?

numero de tramas = 2000
tamaño de trama = 10kB
ancho de banda = 20Mbps

Troughput = (2000 x 10kB(1024 B / 1KB)(8 b / 1B)/ 60 s = 2000 x 81920 b / 60 s = 2.73 Mbps


# 8.- Si tengo un mensaje de 550MB sobre una línea de comunicación de 20000 Km de distancia. Determine el tiempo necesario para que “llegue completo” dicho mensaje si se tiene un performance de la línea de 40Mbps,y una velocidad de propagación de la señal de 300 000 m/s. Al final mencione ¿qué valor del throughput existe y qué significa este valor?

tamaño del mensaje = 550MB
distancia = 20000Km
velocidad de propagacion = 300000 m/s
Troughput = 40Mbps 


Latencia = Tiempo de propagacion + tiempo de transmision 

Tiempo de propagacion = 20000Km / 300000 m/s  = 20000Km (1000 m / 1Km) / 300000 m/s = 20000000 m / 300000 m/s

Tiempo de propagacion = 66.6 seg

Tiempo de transmision = 500MB / 40Mbps  = 500MB(1024 KB/ 1MB)(1024B/1KB)( 8 b/ 1B) / 40 Mbps (1000000 b / 1Mb)
                      = 4194304000 b / 40000000 bps = 104.9 seg
					  
Latencia = 66.6 seg + 104.9 seg = 171.5 seg = 2.86 minutos


# 9.- Si tengo un archivo  de 21GB sobre una línea que proporciona una velocidad de 60Mbps, y tengo un RTT (Round trip time o RTD round trip delay) de 900 ms para un solo bit. Determine ¿cuántos bytes puedo enviar en el retardo de ida?. ¿en cuanto tiempo recibiré el último ACK (asumiendo que se envía en un tamaño despreciable)?

tamaño de archivo = 21GB
velocidad = 60Mbps
RTT= 900ms

Tiempo de ida = RTT/2 = 0.45 s

cantidad de bytes ida = 21GB(1024 MB/1GB) x 0.45 s = 9676.8MB = 9.45 GB en el retardo de ida

el ack se recibe en 0.9 segundos debido al RTT

# 10.- Si en este momento estoy mandando tramas de 1500 bytes a razón de 50000 por minuto. ¿En cuánto tiempo podría mandar un archivo de 22GB? ¿Qué significa este valor obtenido?

numero de tramas = 50000 
tamaño de trama = 1500 B

Troughput = 50000 x 1500B(8 b/1B) / 60 s = 10Mbps

tiempo de transferencia = 22GB(1024MB/1GB)(1024KB/1MB)(1024 B/1kB)(8 b/1B) / 10Mbps (1000000 b / 1Mb) =
						188978561000 b / 10000000 bps = 18817 seg = 5.25 h
						

# 11. Encontrar la tasa de transferencia de un canal que transporta 20000 elementos de señal por segundo, sabiendo que cada elemento de señal porta 7 bits.

BitRate (sin formula) =  20000 x 7 x 1s = 140000 b = 0.14 Mbps
						
						
# 12.- Si en una línea de comunicación serial tenemos 96000 baudios, ¿qué tasa de transferencia se puede alcanzar sabiendo que el método de codificación usado tiene plasmado 1 bit por 2 elementos de señal? ¿Cuántos baudios necesitaría para alcanzar, en ese mismo enfoque de codificación, una tasa de transferencia de 10Mbps


formula de relacion 

S = N X e/r baud 

r = 1
e = 2
N = ?
S = 96000

N (tasa de transferencia) = S / (e/r) = 96000 / 2 = 48000 bps

para una N de 10Mbps

S = 10000000 bps x 2 = 20000000 bauds
