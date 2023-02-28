# Capa Física

# Frecuencia

- HZ: cantidad de ondas producidas en un segundo.

# Ancho de banda

# unidades de medida

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

# Ejemplo

Asumiendo que se necesitan descargar documentos de textos en con 100 paginas por segundo

- Una pagina es un conjunto de 24 lineas con 80 caracteres en promedio. Y si asumimos que cada caracter vale
  8 bits, la solucion seria:   100 x 24 x 80 x 8 = 1530000 bps = 1.53 Mbps 
  (Es la cantidad de informacion que se va a enviar, por segundo)
  
# Ejemplo 2
 
Un canal de voz, esta creado digitalizado (muestreado) a 4Khz de ancho de banda de señal de voz analoga. Necesitamos samplear la voz
un par de veces con las frecuencias mas altas, si asumimos que cada sample requiere 8 bits entonces
 
- La solucion seria 2 x 8 x 4000 = 64 000 bps -> 64kHZ

# Ejemplo 3

¿Cual es el ancho de banda de una television de alta definicion?

regularmente, estas pantallas se dividen en un ratio 16:9. Son 1920 x 1080 pixeles, la pantalla se renueva
30 veces por segundo, un pixel de color equivale a 24 bits. Entonces:

- La solucion sera 1920 x 1080 x 30 x 24 = 1 492 992 000 bps = 1.5 Gbps

# Muestreo 

tomar muestras para definir una funcion (2 muestras)


# Tipos de datos y sus tamaños

- byte -> 8 bits 
- short -> 16 bits 
- int -> 32 bits
- long -> 64 bits
- float -> 32 bits
- double -> 64 bits

# Notas del ancho de banda

- Para aumentar la valocidad de transferencia, en un medio fisico, debemos aumentar los HZ (la frecuencia)

# Ruido

-EMI: Interferencia electromagnetica
-RFI: Interferencia de Radio Frecuencia

Teorema de shannon: genera ruido
Teorema de Nyquist: no genera ruido

# Ejemplo

Considera un canal sin ruido (nyquist) con un ancho de banda de 3000 hz transmitiendo una señal con dos niveles 
de señal. La tasa maxima de bits se calcula asi:

- 2 x 3000 x log2(2) = 6000 bps

# Ejemplo 2

calculando la tasa mas alta teorica de bits de una linea telefonica, que tiene un ancho de banda de 3000 hz, la relacion
señal ruido es usualmente de unos 3162, entonces

- formula -> B log2 (1+ SNR) 
- Solucion ->  3000 log2(1+3162) -> 34860 bps


# Formulas

- highest bit rate ->  B log2 (1+ SNR) 

# Performance

se refiere al maximo de hz o bps. 

# Throughput

Se refiere a la metrica de a cuanto se esta descargando o transmitiendo en un momento en especifico

# Ejemplo

una red con 10 Mbps puede pasar solo 12000 tramas por minuto, donde se sabe que cada trama equivale a 10000 bits

Throughput = (12000 x 10000) / 60 = 2Mbps 