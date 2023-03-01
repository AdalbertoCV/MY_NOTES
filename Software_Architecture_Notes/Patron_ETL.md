# Patron ETL

Es común tener la necesidad de integrar diferentes fuentes de datos a un proyecto. O bien, 
homogenizar datos que se encuentran en formatos distintos. El patron ETL puede solucionar
muchas de este tipo de problematicas.

Significa extraer, transformar y cargar. Y hace referencia al proceso de extraer datos de
su fuente, transformarlas segun las necesidades del negocio y finalmente cargarlas en su destino final.

Estas tareas son realizadas generalmente por distintos componentes organizados como una arquitectura de flujo 
de datos. Funciona como una secuencia, donde cada componente ejecuta su tarea desde su inicio hasta su
finalizacion, luego se ejecuta la sigueiente tarea por el siguiente componente y asi sucescivamente.

# Elementos 

- Fuente de datos: Componente que permite el acceso a los datos que vamos a procesar
- Extractor de datos: Obtiene los datos a procesar desde el componente de fuente de datos
- Transformador de datos: Obtiene los datos del extractor, realiza algun proceso en ellos,
  y envia los datos al componente Cargador de datos
- Cargador de datos: Toma los datos del trasnportador y los carga en el componente destino de datos.
- Destino de datos: Componente que permite el acceso al conjunto de datos procesados.

# Relaciones

- Lee: Permite a un componente procesador de datos leer un lote de datos desde la fuente de datos.
	Flujo de datos: regula la entrada y salida de datos entre componentes procesadores de datos.
- Escribe: Permite a un componente procesador de datos escribir un lote de datos procesados en el destino.

# Modelo de computación

- Un lote de datos entra al sistema desde una fuente y se mueve a través de los procesadores de datos hasta que llega a un destino.

# Restricciones

- La disponibilidad de los datos controla el procesamiento.
- La ejecución de un procesador de datos empieza una vez que el procesador inmediato anterior en la secuencia termina su ejecución.

# Principios de diseño y atributos de calidad

- Bajo acoplamiento: Bajo acoplamiento entre los procesadores de datos, cada procesador desconoce cual es el procesador del
	cual va a recibir los datos y a cual va a enviarlos al final.
- Cohesion: Cada procesador realiza un procesamiento especifico y relacionado con una unica funcion
- Facilidad de mantenimiento: es fácil realizar cambios en los procesadores de datos ya que están desacoplados.




