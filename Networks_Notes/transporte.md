# Capa de transporte

- De proceso a proceso

# Sockets

- Nos ayudan a realizar las descargas de contenido multimedia

- Cada socket tiene un puerto diferente y un id para identificarse

- Se ejecuta la primitiva de socket para crear el socket en cuestion

- Debe ejecutarse la primitiva de bind par realizar una asignacion de puerto e identificador

- Debe ejecutarse la primitiva de listen para que se acepte la conexion.

# Estados

- Listening: El servidor esta en estado de escucha

- Established: Es una conexion establecida.

# Formato de segmento TCP

- El encabezado tiene minimo 20 Bytes

- Numero de secuencia y ACK: se utilizan para conexiones y para el fragmentado.

- Las banderas (HLEN-Reserved-CODE BITS) identifican el tipo de segmento.

- Window: Indica cuantos bytes se pueden recibir

- Checksum: Deteccion de errores que garantiza que lo que se envia llegue de forma correcta.

- Puntero de urgencia: Indica a partir de que byte se debe procesas INMEDIATAMENTE

# Conexion TCP

- Syn para conexion, Syn + ACK

- Fin para desconexion, Fin + ACK

# Estados

# Conexión

- Cerrado (El servidor o cliente se encuentran en estado de cerrado)

- Listen (se ejecuta una primitiva de listen y el servidor pasa de el estado de cerrado a el estado de listen).

- SynSent (el cliente envia una sincronizacion al servidor y su estado pasa a synSent).

- SynReceived (el servidor recibe la sincronizacion, pasa a estado de SynReceived y envía un ACK y una sincronizacion
	como respuesta al cliente).
	
- Established (El cliente recibe la confirmacion del servidor y pasa a estado de establecido).
	(por su parte el servidor recibe un ACK del cliente y pasa tambien a estado de establecido).
	
# Desconexión tipo 1

- Fin wait1 (Cuando el cliente esta en estado de establecido, envía un fin al servidor y pasa a estado de fin wait1)

- Close wait (El servidor recibe el fin, y pasa de estado establecido a Close wait, además envía un ACK como confirmación)

- Fin wait2 (El cliente recibe la confirmación del servidor y su estado cambia a fin wait 2, además se envía un ACK).

- Last ACK (El servidor recibe el ACK y pasa a estado de LAST ACK, Posteriormente envía un Fin al cliente).

- Time wait (El cliente recibe el fin del servidor y cambia su estado a time wait, un tiempo establecido para desconexion, Además, envía un ACK).}

- Closed (El servidor recibe el ACK del cliente y cambia su estado a closed).
	(Por su parte el cliente, cambia su estado a closed en cuanto el time wait se agota).

# Desconexion tipo 2

- Fin wait1 (Cuando el cliente esta en estado de establecido, envía un fin al servidor y pasa a estado de fin wait1).

- Close wait/last ACK (El servidor recibe el fin del cliente y cambia su estado a close wait y last ACK.
	Esto hace que la conexion se cierre de manera inmediata. Se envia un fin y un ACK)
	
- Time wait (El cliente recibe el fin del servidor y cambia su estado a time wait, un tiempo establecido para desconexion, Además, envía un ACK).}

- Closed (El servidor recibe el ACK del cliente y cambia su estado a closed).
	(Por su parte el cliente, cambia su estado a closed en cuanto el time wait se agota).
	
# Desconexión tipo 3

- Fin wait1 (El cliente y el servidor envían un fin al mismo tiempo).

- Closing (El cliente recibe el fin del servidor y cambia su estado a Closing. Envía un ACK).

- Close wait/last ACK (El servidor recibe el fin del cliente y pasa a estado e close wait y last ACK, envía un ACK).

- Time wait (El cliente recibe el ACK del servidor y pasa su estado a time wait)

- Closed (El servidor recibe el ACK del cliente y cambia su estado a closed).
	(Por su parte el cliente, cambia su estado a closed en cuanto el time wait se agota).
	
	
# Ejercicio 1

1.-Mostrar en pantalla el resultado de ejecutar netstat an en una terminal. 

2.-Analizar qué conexiones están disponibles(TCP) y especificar en que estado se encuentra cada una de ellas de acuerdo al diagrama de estados de TCP.Explicar. 
3.-Abrir una página de internet cualquiera,y ejecutar posteriormente a que cargue la página,el comando netstat–an y buscar los cambios existentes en la salida del comando.Explicar. 
4.-Analizar los resultados.

# Respuestas

1.- 

![NETSTAT1](https://github.com/AdalbertoCV/MY_NOTES/blob/main/Networks_Notes/figuras/netstat1.png)

2.- Las conexiones que tienen la ip de local y de host como 0.0.0.0, no están conectadas a ningun host remoto,
solo están en estado de escucha de todos los servicios, tarjetas de red locales, etc.

- Las conexiones que tienen como estado "establecido", son conexiones que actualmente en el momento de la ejecución del comando
siguen establecidas. Algunas de ellas como la  34.199.101.34:443 y la 34.199.101.34:443, crearon mas de un socket o proceso en la comunicacion.

- La conexion con 23.65.158.173:80, esta en estado de time wait ya que el cliente (la ip local) solicito la desconexion, y esta esperando a 
que pase un tiempo determinado para cerrar dicha conexion.

3.- 

![NETSTAT2](https://github.com/AdalbertoCV/MY_NOTES/blob/main/Networks_Notes/figuras/netstat2.png)

- Al ejecutar el comando despues de haber realizado la conexion con la pagina holammundo.com, podemos notar inmediatamente que
se crean bastantes conexiones establecidas. Esto quiere decir que por ejemplo la ip de host de 66.96.147.109, es la ip de la pagina en cuestion
y si aparece tantas veces, es porque se crean varios sockets para completar algunos procesos, ya sean descargas de archivos u otro tipo de cominucacion.

- No podemos observar el momento de la desconexion con el sitio, porque al cerrarse las conexiones se eliminan.

4.-

Como ultimo analizis de los resultados, podemos concluir con que antes de visitar algun sitio, si hay ciertas conexiones establecidas
por propios servicios locales, o por algunas conexiones que se esten haciendo con algun host remoto. 

Los estados que tienen varian, ya sea que la conexion este establecida, o bien, que ya se haya solicitado algun tipo de desconexion.

Al momento de visitar alguna pagina, dependiendo de la cantidad de procesos que se requieran para recuperar toda la informacion.
Se crearan varias conexiones o sockets segun sea necesario para la correcta comunicacion del cliente con el servidor.