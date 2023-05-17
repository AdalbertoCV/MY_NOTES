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