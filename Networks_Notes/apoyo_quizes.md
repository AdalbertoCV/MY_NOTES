# ADD Attribute Driven Design

- Fue desarrollado por Carnegie Mellon Software Engineering Institute
- Es un método iterstivo incremental
- Provee un detallado paso a paso en las actividades que deben llevarse acabo en cada iteración
- los pasos se pueden organizar en 3 etapas:
	- Planear
		- Establecer el objetivo de la iteracion
		- Elegir uno o mas elementos a refinar
		- Elegir uno o mas conceptos de diseño para satisfacer los drivers
	- Hacer
		- Instanciar elementos arquitecturales, definir responsabilidades e interfaces
		- Esbosar las vistas y registrar las decisiones de diseño
	- Revisar
		-Realizar un analisis de el diseño actual respecto a el objetivo
		
- Terminamos cuando los riesgos han sido mitigados, los dirvers principales fueron satisfacidos, o el tiempo se acabó.

# Patrones

# Pipes and filter

Su proposito es reducir una tarea compleja en una serie de elementos separados que pueden ser reutilizados.
Su estructura permite el procesamiento del flujo de datos. Cada paso del procesamiento se encapsula en un componente 
filtro. Los datos pasan a traves de "tuberias" entre filtros adyacentes.

# Brocker

se utiliza para organizar sistemas distribuidos con componentes desacoplados que interaccionan realizando invocaciones remotas a servicios. 
El broker es el responsable de coordinar la comunicación (reenviar solicitudes & transmitir resultados o excepciones).

# Basado en espacio

está diseñado específicamente para abordar y resolver problemas de escalabilidad y concurrencia. 
También es un patrón de arquitectura útil para las aplicaciones que tienen volúmenes de usuarios concurrentes variables e impredecibles.

# Peer to peer

hacen referencia a un tipo de arquitectura para la comunicación entre aplicaciones que permite a individuos comunicarse y compartir 
información con otros individuos sin necesidad de un servidor central que facilite la comunicación. ( Conexión directa)

# Maestro-esclavo

Se utiliza cuando tiene dos o más procesos que deben ejecutarse de forma simultánea y continua, pero a diferentes velocidades. 
Si estos procesos se ejecutan en un solo bucle, pueden producirse graves problemas de sincronización. 
Estos problemas de sincronización ocurren cuando una parte del ciclo tarda más en ejecutarse de lo esperado. 
Si esto sucede, las secciones restantes del ciclo se retrasan. El patrón maestro / esclavo consta de múltiples bucles paralelos. 
Cada uno de los bucles puede ejecutar tareas a diferentes velocidades. De estos bucles paralelos, uno actúa como maestro y los demás como esclavos.
 El bucle maestro controla todos los bucles esclavos y se comunica con ellos mediante arquitecturas de mensajería.
 
# MVC

Su fundamento es la separación del código en tres capas diferentes, acotadas por su responsabilidad, 
en lo que se llaman Modelos, Vistas y Controladores. 

- Modelo: Es la capa donde se trabaja con los datos
- Vista: Visualización de las interfaces de usuario
- Controlador: Enlace entre las vistas y los modelos, respondiendo a los mecanismos que puedan requerirse para implementar 
	las necesidades de nuestra aplicación.
	
# Cliente - Servidor

Modelo de diseño de software en el que las tareas se reparten entre los proveedores de recursos o servicios, llamados servidores, 
y los demandantes, llamados clientes. Un cliente realiza peticiones a otro programa, el servidor, quien le da respuesta.