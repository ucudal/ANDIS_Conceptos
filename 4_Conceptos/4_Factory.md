# 4 Conceptos

## *Factory*

Este documento está basado en [^2] y [^1].

[^2]: Evans, E. (2015). Domain-Driven Design Reference: Definitions and Pattern
    Summaries. Domain Language, Inc. Disponible
    [aquí](https://www.domainlanguage.com/wp-content/uploads/2016/05/DDD_Reference_2015-03.pdf).

[^1]: Avram, A; Marinescu, F. (2006). Domain-Driven Design Quickly. InfoQ.
    Disponible
    [aquí](https://www.infoq.com/minibooks/domain-driven-design-quickly/).

Las [entidades](./4_Entidad.md) y los [agregados](./4_Agregado.md) pueden ser
muy complejos como para que sean creados por la entidad raíz; o crear y
ensamblar objetos complejos no es una responsabilidad que pueda ser asignada a
los objetos creados, o puede producir diseños poco elegantes y difíciles de
entender. Hacer que el cliente dirija la construcción de esos objetos enturbia
el diseño del cliente, viola el encapsulamiento del objeto ensamblado o agregado
‑requiere que el cliente conozca la estructura interna y las relaciones con
otros objetos‑ y vincula excesivamente al cliente con la implementación del
objeto creado.

Una *Factory* ‑fábrica, en español‑ es una clase utilizada para encapsular el
conocimiento necesario para la creación de objetos, y es especialmente útil para
la creación de agregados y objetos complejos. En una *Factory* se desplaza la
responsabilidad de crear agregados y objetos complejos a un nuevo objeto que
puede no tener responsabilidad alguna en el modelo del dominio pero aún así
forma parte del diseño del dominio. Provee una interfaz que encapsula la lógica
compleja del ensamblado y crea agregados enteros como una unidad, cumpliendo
entonces con sus invariantes.

Es importante que el proceso de creación de objetos sea atómico ‑todo o nada‑
para evitar que los objetos creados estén incompletos. Para los agregados, esto
significa que cuando la raíz sea creada, todos los objetos también deben ser
creados de forma tal que se cumplan las invariantes que hubiera. Para los
[objetos valor](./4_Objeto_Valor.md), esto significa que todos los atributos son
inicializados en su estado válido. Para evitar que sea creado un valor inválido,
se debe arrojar una excepción cuando un objeto no puede ser creado
apropiadamente.

Existen varios patrones de diseño para implementar *Factories*, por ejemplo:
[*Factory Method*](https://refactoring.guru/design-patterns/factory-method) y
[*Abstract Factory*](https://refactoring.guru/design-patterns/abstract-factory).
*Factory Method* es un método de objeto que encapsula la lógica y el
conocimiento necesarios para crear otro objeto, y es muy útil cuando el objeto
cliente quiere construir un objeto interno a un agregado. La solución consiste
en agregar a la entidad raíz del agregado un método que se encarga de la
creación atómica del objeto y retorna una referencia al objeto o a una copia.

En ocasiones, la creación de un objeto puede ser más compleja e incluso
necesitar la creación de una serie de otros objetos, un claro ejemplo es la
creación de un agregado. En estas ocasiones, se puede crear un objeto fábrica
diferente que se encarga específicamente de esta tarea.

> [!IMPORTANT]
> Al crear una fábrica, se rompe la encapsulación del objeto, con lo cual se
> debe tener cuidado. Cuando se da un cambio en el objeto y se rompen sus reglas
> de creación, es importante que la fábrica se actualice acorde al cambio para
> soportarlo.

Las *Factories* de entidades son diferentes a las de objetos valor. Los objetos
valor son usualmente inmutables, por lo que todos sus atributos deben ser
producidos en el tiempo de creación del objeto, esto implica que cuando el
objeto valor es creado, deber ser válido y final. Por otro lado, las entidades
son mutables y además necesitan una **identidad**.

No siempre es necesario una fábrica, por ejemplo, si se cumple alguna de las
siguientes condiciones:

* La construcción del objeto no es complicada.

* La creación del objeto no implica la creación de otros y todos los atributos
  necesarios se pasan por el constructor.

* El objeto cliente está interesado en la implementación.

* La clase es el tipo. No hay jerarquía involucrada, por lo que no existe la
  necesidad de escoger entre una lista de implementaciones concretas.
