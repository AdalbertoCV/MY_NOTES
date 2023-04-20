# Capa de Red

- Protocolo IP

Direcciones IP: son direcciones lógicas en notacion decimal punteada
de 32 bits en formato x.x.x.x donde x es un byte y donde

  0-255		0-255	0-255	0-255
--------.--------.--------.-------
	x	
	
8 bits = 2^8 = 256 combinaciones

ejemplo=
25.59.221.50

# Clases de IPV4

|clase| rango| No.de bits de red | No. de bits de host |Mascara de subred|
|----|---------------------|------------------|--------------|----------------|
| A  | 0.X.X.X - 127.X.X.X | 8 = 2^8 = 256|  24  = 2^24 = 16777216 - 2| 255.0.0.0 |
| B  | 127.X.X.X - 191.X.X.X| 16 = 2^16 = 65536| 16 = 2^16  = 65536 - 2 | 255.255.0.0 |
| C  | 191.X.X.X - 223.X.X.X|  24 = 2^24 = 16777216 |  8 = 2^8 = 256 - 2 | 255.255.255.0 |

( Clase D Y E estan reservados)

Mascara de subred: Mide que parte de la IP es red, y que parte es host


# Redes especiales


|Bloque de direcciones|	Rango	|Número de direcciones	|Alcance	|Descripción|
|-------------------|------------|--------------------|------------|------------|
|0.0.0.0/8|	0.0.0.0–0.255.255.255|	16.777.216	|Software	|Red actual​ (solo válido como dirección de origen).|
|10.0.0.0/8	|10.0.0.0–10.255.255.255|	16.777.216|	Red privada	|Utilizado para las comunicaciones locales dentro de una red privada.|
|100.64.0.0/10|	100.64.0.0–100.127.255.255|	4.194.304|	Red privada|	Espacio de direcciones compartido​ para las comunicaciones entre un proveedor de servicios y sus suscriptores cuando se utiliza un NAT de nivel de operador.|
|127.0.0.0/8|	127.0.0.0–127.255.255.255|	16.777.216|	Host|	Se utiliza para las direcciones de loopback.|
|169.254.0.0/16|	169.254.0.0–169.254.255.255|	65.536	|Subred|	Se utiliza para las direcciones de enlace local6​entre dos hosts en un solo enlace cuando de otra manera no se especifica una dirección IP, como normalmente se habría recuperado de un servidor DHCP.|
|172.16.0.0/12|	172.16.0.0–172.31.255.255|	1.048.576|	Red privada|	Utilizado para las comunicaciones locales dentro de una red privada.|
|192.0.0.0/24|	192.0.0.0–192.0.0.255|	256|	Red privada|	IETF Protocol Assignments.|
|192.0.2.0/24|	192.0.2.0–192.0.2.255|	256|	Documentación|	Asignada como TEST-NET-1, para documentación y ejemplos.|
|192.88.99.0/24|	192.88.99.0–192.88.99.255|	256|	Internet	Reservada|. Previamente usado para relay IPv6 a IPv4. (incluido el bloque de direcciones IPv6 2002::/16).|
|192.168.0.0/16|	192.168.0.0–192.168.255.255|	65.536|	Red privada|	Utilizado para las comunicaciones locales dentro de una red privada.|
|198.18.0.0/15|	198.18.0.0–198.19.255.255|	131.072|	Red privada	|Se utiliza para pruebas de referencia de comunicaciones entre dos subredes separadas.|
|198.51.100.0/24|	198.51.100.0–198.51.100.255|	256|	Documentación|	Asignado como TEST-NET-2, para documentación y ejemplos.|
|203.0.113.0/24|	203.0.113.0–203.0.113.255|	256	|Documentación|	Asignado como TEST-NET-3, para documentación y ejemplos.|
|224.0.0.0/4|	224.0.0.0–239.255.255.255|	268.435.456|	Internet|	Usado para Multicast IP.​ (previamente una red clase D). (Experimental)|
|240.0.0.0/4|	240.0.0.0–255.255.255.254|	268.435.456|	Internet|	Reservada para usos futuros. (anteriormente una red clase E). (Experimental)|
|255.255.255.255/32|	255.255.255.255	|1|	Subred	Reservada| para destinos multidifusión.

# Tipos de IPV4

- Publicas
	Son enrutables en internet y no repetibles (Proovedores de servicios de internet)
	Publicas = totales - privadas - reservadas
- Privadas
	Son NO enrutables en internet y repetibles
- Reservadas
	Tienen un uso exclusivo


Ruta por defecto

# Configuracion de Red

- Direccion IP
- Mascara de red
- Puerta de enlace o Gateway -> sirve para salir de la red (conectarse a internet)
- Servidor DNS -> Sirve para conectarse a las direcciones IP con un nombre mas legible (mipagina.gob.mx)



# ¿Como una computadora con red privada puede tener internet?

Necesita enlazarse con una direccion publica, normalmente, se encuentra en las tarjetas de red en los enrutadores
los cuales se encargan de enlazar directamente con el proveedor de servicios de internet.

NAT: El enrutador actua como representante o intermediario de todas las computadoras de la red privada. Al realizar peticiones,
se toma la IP del intermediario para la salida a internet.

# ------Actividad------ 


1. Usando la red inalambrica o alambrica identificar la configuracion de red que se tenga en una red a la que
se está conectado: Direccion IP (máscara, DNS, GW), clase ¿La máscara está predeterminada?
Si no es asi, ¿cuantos bits se usan para la parte de red y cuantos para la parte de host?

Red de la escuela:

direccion Ip: 10.2.80.244
Máscara de subred: 255.255.252.0
GW: 10.2.80.1
DNS: uaz.edu.mx

No es la mascara predeterminada, se ocupan 24 bits para red y 8 bits para host.


2. Configurar en red dos computadoras en cable cruzado. Defina un esquema de red diferete al usado en clase.