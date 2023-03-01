# Capa Fisica (2)

# Latencia 

Es el tiempo que tarda un mensaje (del tamaño que sea) en llegar de un lugar a otro (desde que sale el primer bit, hasta que llega el ultimo).

Latencia = tiempo de propagación (tp) + tiempo de trasmision(tt) + tiempo de encolamiento(te) + tiempo de procesamiento (tpr)

Si los PDUS no se pierden y los tiempos son constantes, se puede decir que la red es estable. (ping)

# Tiempo de propagacion

- Recuerda al concepto de fisica. Tiempo es igual a distacia / velocidad

- Tp = distancia/velocidad de propagacion

- Es el tiempo que tarda 1 SOLO BIT en llegar de un lugar a otro.

- Las unidades base son metros y segundos

- Para transformar una cantidad muy pequeña de segundos (ms) se multiplica por mil

# Tiempo de transmisión

- Es el tiempo entre el primer bit y el ultimo bit. 

- Tt = tamaño del mensaje/ ancho de banda (troughtput)

- las unidades base son Bytes y bps (bits por segundo)

- El multiplo de los bytes es 1024, si se hace x 1000 solamente hay un valor aproximado, no real.

# Tiempo de encolamiento 

- Es el tiempo en que los PDU se quedan en espera en los routers para llegar al destino.

- Este tiempo no se puede calcular con anticipacion, por lo tanto, es un tiempo desconocido.

- Es un tiempo que siempre va a ser inestable y depende de cuantos paquetes hayan en un router cada vez
	que un PDU pase por alli.

- Es un tiempo que varia de segundo a segundo.

# Tiempo de procesamiento

- Es el tiempo en el que los PDU se desencapsulan y se procesan

- Tampoco se puede calcular exactamente, pero se puede promediar.

# Ejercicio, calculando una latencia

¿Cuanto tiempo pasa para poder recibir un ack de mi primer pdu de un archivo con 3 pdus, tomando en cuenta
que, el ack es de un tamaño depreciable (como el ping)

formula = Lvuelta = Tp + Tt + C (constante)

Latencia ida = 50.020 ms
Tp = 50 ms
Tt =  64 B x (8b/ 1 B) / 1000000000 bps 
Tt = 512 b / 1000000000 bps = 0.000512 ms

Latencia vuelta = 50.000512 ms + 50.02 ms  = 100.02512 ms

- Este tiempo es llamado RTT (tiempo de ida y vuelta)