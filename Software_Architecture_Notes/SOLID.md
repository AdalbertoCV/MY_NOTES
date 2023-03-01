# Principios SOLID

Son un conjuntos de 5 principios de la programación orientada a objetos.

Estos 5 principios son:

- S: Single Responsibility
- O: Open/Closed
- L: Liskov Substitution
- I: Interface Segregation
- D: Dependency Inversion 

# Single Responsibility 

Cada modulo del software debe tener una unica responsabilidad sobre la funcionalidad del mismo.
Debe estar encapsulada en su totalidad por la clase.

# Open/Closed 

Una entidad de software debe permanecer abierta para su extension, pero debe permanecer cerrada 
para su modificacion. Es decir, que debería de poderse extender el comportamiento de una clase, sin
la necesidad de modificar su codigo fuente.

# Liskov Substitution

Se trata sobre el comportamiento buscado en la herencia de clases. Nos indica que cada clase que hereda de otra
clase padre, deberia ser usada de la misma manera sin la necesidad de conocer las diferencias entre ellas.

Es decir, que si se realiza una substitucion de una clase padre con cualquiera de sus subclases, no deberia afectar
el funcionamiento del sistema.

# Interface Segregation

Nos dice que los usuarios finales del sistema, solo deben conocer o saber de la existencia de aquellos metodos
que pueden usar y desconocer los metodos que no usaran directamente.
Es mejor, tener muchas interfaces que definan pocos metodos que seran usados, a tener una interfaz con muchos metodos
de los cuales no todos se usarán

# Dependency Inversion

Se trata de una manera de desacoplar modulos de software. 

- Los modulos de alto nivel no deberian depender de modulos de bajo nivel. ambos deberian depender de abstracciones.
- Las abstracciones no deberian depender de los detalles. Los detalles deben depender de las abstracciones.

Entendemos por abstracciones a la accion de identificar y seleccionar aquellas caracteristicas mas importantes de 
una entidad, para reducir su complejidad y el esfuerzo de programacion.