# 2 Técnicas y herramientas

## 2.8 Patrones de diseño

### *Entity*

Este documento está basado en [^2] y [^1].

[^2]: Evans, E. (2015). Domain-Driven Design Reference: Definitions and Pattern
    Summaries. Domain Language, Inc. Disponible
    [aquí](https://www.domainlanguage.com/wp-content/uploads/2016/05/DDD_Reference_2015-03.pdf).

[^1]: Avram, A; Marinescu, F. (2006). Domain-Driven Design Quickly. InfoQ.
    Disponible
    [aquí](https://www.infoq.com/minibooks/domain-driven-design-quickly/).

En el contexto de *Domain-Driven Design* —DDD, por sus siglas—, una entidad es
un objeto que se distingue por su identidad, en lugar de por sus atributos. Es
necesario un mecanismo para diferenciar un objeto de otro independientemente de
su forma[^3] o su historia.

[^3]: Por ejemplo cuando se transforma a una representación para almacenamiento
    persistente o para ser enviado a través de la red.

Así es que implementar entidades en software implica crear identidades, por lo
que la capacidad de identificar estas últimas es crucial. El atributo —o
combinación de atributos— utilizado para lograr la identidad puede ser propio
del objeto, asignado por alguien externo a la aplicación o incluso al
[dominio](../4_Conceptos/4_Dominio.md). Pero a veces no hay ninguna combinación de atributos
que permita identificar los objetos de forma única, por lo que se puede utilizar
un sistema arbitrario creado por la aplicación.

Por ejemplo, para una entidad `Persona`, es casi seguro que ninguna combinación
de los atributos nombre, fecha y lugar de nacimiento, permita identificar en
forma única a una persona, pues diferentes personas pueden tener el mismo
nombre, la misma fecha, y el mismo lugar de nacimiento. En cambio, la cédula de
identidad, asignada por la autoridad de identificación civil, que es externa a
la aplicación, garantiza que no hay dos personas con la misma cédula, por lo que
podría ser utilizado para lograr la identidad.

Una mala elección del mecanismo para lograr identificar a una entidad puede
llevar a la corrupción de datos. Para evitarlo, es importante que se cumplan las
siguientes dos condiciones:

* Dos objetos con diferentes identidades son considerados diferentes

* Dos objetos con la misma identidad son considerados el mismo

Cuando un objeto es diferenciado por su identidad, debes hacerla primaria en la
definición de la entidad en el modelo. Además, debes estar pendiente a los
requerimientos que necesitan reconocer diferentes objetos como la misma entidad
a través de sus atributos. También es importante tener en cuenta que el modelo
debe definir qué significa ser la misma cosa.

Las entidades son objetos importantes para el modelo del
[dominio](../4_Conceptos/4_Dominio.md), y deben ser consideradas desde el comienzo del
proceso de modelado.
