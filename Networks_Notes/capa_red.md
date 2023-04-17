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