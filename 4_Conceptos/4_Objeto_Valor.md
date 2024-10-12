# 4 Conceptos

## Objeto valor

Este documento está basado en el libro "Domain-Driven Design Quickly" [^1].

[^1]: Avram, A; Marinescu, F. Domain-Driven Design Quickly. InfoQ. Disponible
    [aquí](https://www.infoq.com/minibooks/domain-driven-design-quickly/).

Dentro de *Domain-Driven Design* —DDD, por sus siglas—, un objeto valor es un
objeto que, a diferencia de una [entidad](./4_Entidad.md), no tiene identidad ni
continuidad y se utiliza para describir ciertos aspectos del dominio.

Al no tener una identidad, los objetos valor se pueden crear y descartar
fácilmente —a través del *garbage collector* cuando dejan de ser referenciados,
por ejemplo—, lo que simplifica el diseño.

Una cualidad deseable e importante de los objetos valor es que sean inmutables,
esto es, que sean creados a través de un constructor y nunca modificados en su
tiempo de vida. De necesitar un nuevo valor, simplemente se crea un nuevo objeto
valor. Si un objeto valor cumple con esta cualidad de inmutabilidad, el mismo
puede ser compartido.

Los objetos valores pueden contener otros objetos valores, e incluso contener
referencias a entidades. Algo que favorece a la expresabilidad del diseño es
agrupar en un objeto valor atributos que están conceptualmente relacionados, por
ejemplo: un usuario de un sistema podría ser un objeto valor compuesto de su
identificador (`id`), `nombre`, `calle`, `ciudad` y `Estado`, o mejor aún, `id`,
`nombre` y `dirección`, donde este último es otro objeto valor compuesto de
`calle`, `ciudad` y `Estado`. Esto se ilustra en la siguiente figura.

![Objetos valor anidados](../diagrams/Value_Object.svg)

#### *Figura 1 Objetos valor anidados*
