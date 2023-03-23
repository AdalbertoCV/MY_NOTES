# Disponibilidad

Es una propiedad del software que indica que está listo para resolver las tareas en el momento en el que
quiera realizarlas.

A su definición se agrega la capacidad que tiene el software, de fallar, y poder recuperarse o volverse a levantar 
por su propia cuenta.

Considera la habilidad del sistema de reparar errores, para que los mismos no se conviertan en fallos como tal.

La diferencia principal de fault y failure, es que una fault es basicamente la razon o la causa por las que las fallas o los 
errores suceden en el sistema.

Esta estrechamente relacionado con seguridad y desempeño, ya que una ataque directo a la seguridad del sistema, siempre
tiene como objetivo derrumbarlo, lo cual lo hace no-disponible, y en cuanto a desempeño, será dificil cumplir con las tareas
o decir que el sistema esta disponible ccon respuestas lentas del mismo.

MTBF = tiempo promedio entre fallas
MTTR = tiempo promedio para reparacion

La formula MTBF/(MTBF + MTTR) nos permite calcular en que porcentaje, el sistema esta disponible o cual es la posibilidad de que falle.

# Escenario de disponibilidad

recurso -> Estímulo (fallo) -> Artefacto | Ambiente -> Respuesta -> Metrica de respuesta

# Tacticas para prevenir fallos

El funcionamiento ideal con el uso de las tacticas es el siguiente:

Fallo -> Tactica para control -> Fallo prevenido o reparado.


Los principales objetivos de las tacticas son 

- Detectar errores
	- Monitor: Monitorea las partes del sistema y su estado
	- Ping: Envia mensajes cada cierto tiempo para confirmar que el servicio siga disponible
	- Heartbeat: Se emplea como un intercambio de mensajes entre un monitor y una parte del sistema que esta siendo monitoreada
	- Timestamp: Se utiliza para detectar secuencias incorrectas de eventos
	- Condition monitoring: Se utiliza para revisar las condiciones o validaciones durante el diseño
	- Sanity checking: Revisa las salidas o las operaciones de los componentes
	- Voting: compara resultados computacionales que deben reflejarse de la misma manera y si no es asi, se decide que resultados usar
	- Excepcion detection: Detecta las condiciones que alteran el flujo normal del sistema
	- self-test: los componentes se prueban a si mismos para su correcto funcionamiento
- Recuperarse de errores
	- Redundant spare: Varios componentes pueden dedicarse a la misma tarea, y si uno falla hay otro que toma su lugar
	- Rollback: Permite al sistema volver a un estado previo
	- Exception handling: Una ves que una excepcion se detecta, el sistema tiene algunas maneras de manejarla
	- Software upgrade: se actualiza y se mejoran las clases, componentes del sistema para corregir o parchar los errores
	- Retry: Se reintenta la operacion una vez falla, para realizar un intento exitoso posteriormente
	- Ignore faulty behavior: Se ignoran los mensajes de error de componentes que no afecten directamente a otras tareas o no generen un fallo en si
	- Graceful degradation: se eliminan algunas tareas criticas o riesgosas para mantener al sistema funcionando correctamente
	- Reconguration: El sistema se reconfigura y se reasignan operaciones mientras se intenta dejar la mayor funcionalidad posible
	- Shadow: Se corrige un fallo previo "en las sombras" para regresar el componente a su estado activo
	- State resynchronization: apoya a la reintroduccion de la redundancia activa y pasiva
	    Cuando se usa junto con la táctica de redundancia activa, la resincronización de estado ocurre orgánicamente (es decir, paso a paso).
	- Escalating restart: El sistema se reinicia por niveles de prioridad, pero en tiempos distintos para mantener el sistema funcionando mientras el reinicio se lleva a cabo
	- Nonstop forwarding: Se evita que el sistema se detenga usando varios routers por si alguno falla, mientras el protocolo de enrutamiento es revalidado
- Prevenir errores
	- Removal from service: Se refiere a desactivar temporalmente un componente para prevenir fallas
	- Transactions: se usan para garantizar que los mensajes asíncronos intercambiados entre los componentes distribuidos son atómicos, consistentes, aislados y duraderos
	- Predictive model: es empleado para monitorear el estado de salud de un proceso del sistema para asegurar que el está operando dentro de sus parámetros operativos nominales, y tomar acción correctiva
	- Exception prevention: Prevenimos las excepciones usando clases de excepcion para que el sistema pueda recobrarse de las mismas.
	- Increase competence set: se denomina cuales son los componentes "competentes" para operar, si alguno da una excepcion, se marca como no competente.

