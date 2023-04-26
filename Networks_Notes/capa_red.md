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

Calcular n y m en la mascara (bits de subred y host) tomando como base el ejemplo anterior

m: 27 +1
ad: 12 +1
c: 24 +1
j: 5 +1 
rh: 1 +1

5 dptos 

2^n >= numero de subredes a crear  n=3
2^m - 2 >= maximo de host de las redes (el que tenga mas computadoras conectadas) m=5

C: 5 + 1

192.168.0.96

|sr|h| red|
|----|----|-----|
|011|00000| .96|
|011|00001|  .97|
|011|00010|  .98|
|011|00100|  .99|
|011|11110|  .126|
|011|11111|  .127|

gw = .97
pcs = de .98 a .102


J: 24+1

192.168.0.128

|sr|h| red|
|----|----|-----|
|100|00000| .128|
|100|00001|  .129|
|100|00010|  .130|
|100|00100|  .131|
|100|11110|  .158|
|100|11111|  .159|

gw = .129
pcs = de .130 a .153

RH: 1+1

192.168.0.160

|sr|h| red|
|----|----|-----|
|101|00000| .160|
|101|00001|  .161|
|101|00010|  .162|
|101|00100|  .163|
|101|11110|  .190|
|101|11111|  .191|

gw = .161
pcs = .162




# ------Actividad------ 


1. Usando la red inalambrica o alambrica identificar la configuracion de red que se tenga en una red a la que
se está conectado: Direccion IP (máscara, DNS, GW), clase ¿La máscara está predeterminada?
Si no es asi, ¿cuantos bits se usan para la parte de red y cuantos para la parte de host?

Red de la escuela:

direccion Ip: 10.2.80.244
Máscara de subred: 255.255.252.0
GW: 10.2.80.1
DNS: uaz.edu.mx

Red de casa:


No es la mascara predeterminada, se ocupan 24 bits para red y 8 bits para host.


2. Configurar en red dos computadoras en cable cruzado. Defina un esquema de red diferete al usado en clase.

4. Diseñar un esquema de subredes en donde se tienen 5 cc en una escuela, con 33, 35, 21, 18 y 22 computadoras respectivamente.
Crear diagrama y especificaciones del ISP

![Diagrama de la red](/figuras/ejemplo1.png)

2^n >= 5
n = 3

2^m - 2 >= 35
m = 6

se necesitan 16 bits de subred y host

para la red se necesian

16 bits de red, 8 bits de subred y 8 bits de host


subred:

0
32
64
96
128
160
192
224

host:

0
32
64
96
128
160
192
224

subred cc 1 33

172.160.32.0

|subred|h|red|
|----|----|----|
|.32| 00000| .0| x
|.32| 00001| .1|
|.32| 11110| .30|
|.32| 11111| .31|


GW = 172.160.32.1
pcs = de 172.160.32.2 a 172.160.32.34

subred cc 2 35

172.160.64.0

|subred|h|red|
|----|----|----|
|.64| 00000| .0| x
|.64| 00001| .1|
|.64| 11110| .30|
|.64| 11111| .31|


GW = 172.160.64.1
pcs = de 172.160.64.2 a 172.160.64.36

subred cc 3 21

172.160.96.0

|subred|h|red|
|----|----|----|
|.96| 00000| .0| x
|.96| 00001| .1|
|.96| 11110| .30|
|.96| 11111| .31|


GW = 172.160.96.1
pcs = de 172.160.96.2 a 172.160.96.22

subred cc 4 18

172.160.128.0

|subred|h|red|
|----|----|----|
|.128| 00000| .0| x
|.128| 00001| .1|
|.128| 11110| .30|
|.128| 11111| .31|


GW = 172.160.128.1
pcs = de 172.160.128.2 a 172.160.96.19

subred cc 5 22

172.160.160.0

|subred|h|red|
|----|----|----|
|.160| 00000| .0| x
|.160| 00001| .1|
|.160| 11110| .30|
|.160| 11111| .31|


GW = 172.160.160.1
pcs = de 172.160.160.2 a 172.160.160.23