# 4 Conceptos

## *Value Object*

Este documento está basado en [^2] y [^1].

[^2]: Evans, E. (2015). Domain-Driven Design Reference: Definitions and Pattern
    Summaries. Domain Language, Inc. Disponible
    [aquí](https://www.domainlanguage.com/wp-content/uploads/2016/05/DDD_Reference_2015-03.pdf).

[^1]: Avram, A; Marinescu, F. (2006). Domain-Driven Design Quickly. InfoQ.
    Disponible
    [aquí](https://www.infoq.com/minibooks/domain-driven-design-quickly/).

En el contexto de *Domain-Driven Design* ‑DDD, por sus siglas‑, un objeto valor
es un objeto que, a diferencia de una [entidad](./2_08_Entity.md), no tiene
identidad y se utiliza para describir o calcular características de las
cosas que son parte del [dominio](../4_Conceptos/4_Dominio.md).

Al no tener una identidad, los objetos valor se pueden crear y descartar
fácilmente ‑a través del *garbage collector* cuando dejan de ser referenciados,
por ejemplo‑, lo que simplifica el diseño.

Una cualidad deseable e importante de los objetos valor es que sean inmutables,
esto es, que sean creados a través de un constructor y nunca modificados en su
tiempo de vida. De necesitar un nuevo valor, simplemente se crea un nuevo objeto
valor. Si un objeto valor cumple con esta cualidad de inmutabilidad, puede ser
compartido.

Todas las operaciones sobre objetos valor deberían ser funciones sin efectos
colaterales ‑[funciones puras](https://en.wikipedia.org/wiki/Pure_function)‑ que
no dependan de ningún estado mutable.

Los objetos valores pueden contener otros objetos valor, e incluso contener
referencias a entidades. Algo que favorece a la capacidad de expresión del
diseño es agrupar en un objeto valor atributos que están conceptualmente
relacionados, por ejemplo: un usuario de un sistema podría ser un objeto valor
compuesto de su identificador (`id`), `nombre`, `calle`, `ciudad` y `estado`, o
mejor aún, `id`, `nombre` y `dirección`, donde este último es otro objeto valor
compuesto de `calle`, `ciudad` y `estado`. Esto se ilustra en la siguiente
[Figura 1](#figura-1).

<span id="figura-1"/>

![Objetos valor anidados](../diagrams/Value_Object.svg)

*Figura 1: Objetos valor anidados.*
