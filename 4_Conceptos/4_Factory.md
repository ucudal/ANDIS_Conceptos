# 4 Conceptos

## *Factory*

Este documento está basado en el libro "Domain-Driven Design Quickly" [^1].

[^1]: Avram, A; Marinescu, F. Domain-Driven Design Quickly. InfoQ. Disponible
    [aquí](https://www.infoq.com/minibooks/domain-driven-design-quickly/).

Las [entidades](./4_Entidad.md) y los [agregados](./4_Agregado.md) pueden ser
muy complejos como para que sean creados por la entidad raíz, y dejar en la raíz
la responsabilidad de crear un agregado complejo va usualmente en contradicción
de lo que pasa en el dominio. Además, cuando el proceso de crear otro objeto es
laborioso, involucra tener conocimiento sobre la estructura interna del objeto a
crear y sus relaciones con otros objetos, rompiendo el encapsulamiento de los
objetos y agregados del dominio.

Una *Factory* —fábrica, en español— es un concepto utilizado para encapsular el
conocimiento necesario para la creación de objetos, y es especialmente útil para
la creación de agregados.

Es importante que el proceso de creación de objetos sea atómico para evitar que
los objetos creados estén incompletos. Para los agregados, esto significa que
cuando la raíz sea creada, todos los objetos del agregado sujetos a invariantes,
deben ser creados también para que las mismas se puedan cumplir. Para los
[objetos valor](./4_Objeto_Valor.md), esto significa que todos los atributos son
inicializados en su estado válido. Para evitar que un valor inválido sea creado,
se debe arrojar una excepción cuando un objeto no puede ser creado
apropiadamente.

> [!NOTE]
> Desplaza la responsabilidad de crear agregados y objetos complejos a un nuevo
> objeto que puede no tener responsabilidad alguna en el modelo del dominio pero
> aún así forma parte del diseño del dominio. Provee una interfaz que encapsula
> la lógica compleja del ensamblado y crea agregados enteros como una unidad,
> cumpliendo entonces sus invariantes.

Existen varios patrones de diseño para implementar *Factories*, por ejemplo:
*Factory Method* y *Abstract Factory*. *Factory Method* es un método de objeto
que encapsula la lógica y el conocimiento necesarios para crear otro objeto, y
es muy útil cuando el objeto cliente quiere construir un objeto interno a un
agregado. La solución consiste en agregar a la entidad raíz del agregado un
método que se encarga de la creación atómica del objeto y retorna una referencia
al objeto o a una copia.

En ocasiones, la creación de un objeto puede ser más compleja e incluso
necesitar la creación de una serie de otros objetos, un claro ejemplo es la
creación de un agregado. En estas ocasiones, se puede crear un objeto fábrica
diferente que se encarga específicamente de esta tarea.

> [!IMPORTANT]
> Al crear una fábrica, se rompe la encapsulación del objeto, con lo cual se
> debe tener cuidado. Cuando se da un cambio en el objeto y se rompen las reglas
> de creación del mismo, es importante que la fábrica se actualice acorde al
> cambio para soportarlo.

Las *Factories* de entidades son diferentes a las de objetos valor. Los objetos
valor son usualmente inmutables, por lo que todos los atributos del mismo deben
ser producidos en el tiempo de creación del objeto, esto implica que cuando el
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
