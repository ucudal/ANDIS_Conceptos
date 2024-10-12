# 4 Conceptos

## Entidad

Este documento está basado en el libro "Domain-Driven Design Quickly" [^1].

[^1]: Avram, A; Marinescu, F. Domain-Driven Design Quickly. InfoQ. Disponible
    [aquí](https://www.infoq.com/minibooks/domain-driven-design-quickly/).

Bajo el punto de vista de *Domain-Driven Design* —DDD, por sus siglas—, una
entidad es un objeto cuya identidad se mantiene constante durante los diferentes
estados de un sistema, de hecho, las entidades tienen una identidad que abarca
la vida de un sistema y puede extenderse más allá del mismo.

Así es que implementar entidades en software implica crear identidades, por lo
que la capacidad de identificar estas últimas es crucial. Por ejemplo, si
quisieras implementar la entidad *Persona*, podrías plantearte utilizar algún
atributo en particular como su nombre, o incluso un conjunto de ellos, ya que no
sería suficiente con simplemente usar su nombre y su fecha de nacimiento, por
mencionar una combinación. Tampoco sería suficiente utilizar su lugar de
nacimiento, ya que diferentes personas podrían tener el mismo lugar de
nacimiento; lo importante aquí es encontrar el atributo o combinación de
atributos que garantizan la identidad de la entidad *Persona*, ya que la mala
identificación de una entidad puede llevar a la corrupción de datos.

La cédula de identidad es un atributo que garantiza al identidad de una
*Persona*, por lo que puede ser utilizado para crear la identidad de *Persona*.
Usualmente, la identidad es un atributo del objeto, una combinación de
atributos, un atributo generado automática y específicamente para expresar la
identidad (un atributo **id**, por ejemplo), o incluso un comportamiento. Para
evitar que todo el sistema se vuelva corrupto, es importante que se cumplan las
siguientes dos condiciones:

* Dos objetos con diferentes identidades son considerados diferentes por el
  sistema

* Dos objetos con la misma identidad son considerados el mismo por el sistema

Cuando un objeto es diferenciado por su identidad, debes hacerla primaria en la
definición de la entidad en el modelo. Además, debes estar pendiente a los
requerimientos que necesitan reconocer diferentes objetos como la misma entidad
a través de sus atributos. También es importante tener en cuenta que el modelo
debe definir qué significa ser la misma cosa.

Las entidades son objetos importantes para el modelo del dominio, y deben ser
consideradas desde el comienzo del proceso de modelado.
