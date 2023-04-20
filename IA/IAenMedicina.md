# IA en la medicina

Puede ayudar en áreas como:

- Diagnostico de enfermedades con imágenes médicas
- Robots Quirúrgicos
- Maximización de la efiiencia hospitalaria

Se espera que el mercado de la salud de la IA alcance los 45.2 mil millones de dolares
para 2026 a partir de la valoracion actual de 4.9 mil millones de dolares

# Contexto caso de estudio

- Necesitamos mejorar la velocidad y precisión de la detección y localización de tumores
cerebrales en funcion de imagenes por resonancia magnetica.

- Esto reduciria drasticamente el coste del diagnostico de cancer y ayudaría en el diagnóstico 
temprano de tumores, lo que especialmente salvaría la vida.

# Redes neuronales convolucionales

Es un tipo de red neuronal con aprendizaje supervisado que procesa sus capas imitando al cortex
visual del ojo humano para identificar distintas caracteristicas en las entradas que en definitiva hacen que se 
pueda identificar imagenes y "ver".

Las capas ocultas se van especializando, es decir, primero pueden detectar lineas, fromas, curvas, etc..
y despues detectar cosas más especificas.

La red neuronal debe aprender por si sola a reconocer una diversidad de objetos dentro de imagenes
y para ello necesitaremos una gran cantidad de las mismas, para que la red pueda captar sus caracteristicas
unicas de cada objeto y a su vez poder generalizarlo.

- Capas de entrada: Donde se ingresan los parametros
- Capas ocultas: Donde se realzia el procesamiento de los datos
- Capas de salida: Donde nos dice el resultado de la clasificacion.

La red toma como entrada los pixeles de una imagen.
Si tenemos una imagen con 28x28 pixeles de alto, equivale a 784 neuronas, y eso en solo un color (escala de grises)
Si tenemos una imagen a color tenemos una entrada de la forma 28x28x3 (3 canales de color)

Convolusiones: Se toman grupos de pixeles cercanos y se aplican procesamiento matematico, supongamos
un tamaño de kernel de 3x3 pixeles que recorre todas las neuronas de entrada de izquierda a derecha y de arriba a abajo y 
genera una nueva matriz de salida.

Subsamplig: Segun los resultados de una funcion de activacion, se desprecian algunos valores para rescatar la informacion
relevante y reducimos el tamaño de nuestra matriz para optimizarla.

# Resnet

- Funciona agregando asignaciones de identidad en la parte superior de la RNC
- Contiene 11 millones de imagenes con 11000 categorias

# Aprendizaje por transferencia

Es una tecnica de aprendizaje automatico en la que una red que ha sido entrenada para realizar una tarea especifica
se reutiliza como punto de partida para otra tarea similar.

Se usa ampliamente ya que a partir de modelos previamente entrenados puede reducir drasticamente el tiempo
de calculo requerido si el entrenamiento se realiza desde cero.

pasos:

- congelar los pesos de la red entrenada de las primeras capas
- Entrenar solo las capas densas recien agregadas.

# Segmentacion

El objetivo de segmentar la imagen es comprender y extraer informacion de las imagenes a nivel pixel.
Se puede utilizar para el reconocimiento y la localizacion de objetos, lo que ofrece un valor tremendo en 
muchas aplicaciones, como imagenes medicas y automoviles autonomos, etc.

Las tecnicas modernas de segmentacion de imagenes se basan en un enfoque de aprendizaje profundo que hace uso 
de arquitecturas comunes como RNC, RCT y codificafores-decodificadores profundos.

# Mascaras

La salida producida por el modelo de segmentacion de imagenes se denomina mascara de la imagen.
Se pueden representar asociando valores de pixeles con coordenadas.