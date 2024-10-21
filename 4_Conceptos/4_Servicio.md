# 4 Conceptos

## Servicio

Este documento está basado en el libro "Domain-Driven Design Quickly" [^1].

[^1]: Avram, A; Marinescu, F. Domain-Driven Design Quickly. InfoQ. Disponible
    [aquí](https://www.infoq.com/minibooks/domain-driven-design-quickly/).

En *Domain-Driven Design* —DDD, por sus siglas—, un servicio es un objeto que, a
diferencia de una [entidad](./4_Entidad.md) y un [objeto
valor](./4_Objeto_Valor.md), no tiene estado y su único propósito es el de
proveer funcionalidad para el dominio. Los servicios actúan como interfaces que
proveen operaciones y si bien son más comunes en *frameworks* técnicos, también
se pueden usar en la capa del dominio.

Un aspecto importante de los servicios es que usualmente actúan como punto de
conexión entre diferentes objetos, y esta es una de las razones por la que el
comportamiento que naturalmente corresponde a un servicio no debe incluirse
dentro de otros objetos del dominio. Si esto pasara, se puede obtener como
resultado una gran red de asociaciones entre objetos, lo cual significa un gran
nivel de [acoplamiento](./4_Acoplamiento.md). Al mismo tiempo, un servicio
tampoco debería reemplazar una operación que normalmente pertenecería a un
objeto del dominio.

Los servicios tienen las siguientes tres características:

* La operación llevada a cabo por el servicio refiere a un concepto del dominio
  que no pertenece naturalmente a una entidad o un objeto valor.

* La operación llevada a cabo por el servicio refiere a otros objetos en el
  dominio.

* La operación llevada a cabo por el servicio no tiene estado.

> [!NOTE]
> Cuando un proceso o transformación significante para el dominio no es una
> responsabilidad natural para una entidad o un objeto valor, agrega una
> operación al modelo como una interfaz independiente declarada como un
> servicio. Define la interfaz en términos del lenguaje del modelo y asegúrate
> de que el nombre de la operación es parte del lenguaje ubicuo y que el
> servicio no tenga estado.

Al utilizar servicios, es importante mantener aislada la capa del dominio; es
fácil confundir servicios que pertenecen a la capa de dominio con servicios que
pertenecen a la capa de infraestructura o incluso a la capa de aplicación.

Usualmente, los servicios de aplicación y de dominio son construidos sobre
entidades y objetos valor y proveen funcionalidad ligada a estos objetos, lo que
dificulta la decisión de a qué capa pertenece el servicio. Cuando el servicio
conceptualmente pertenece a la capa de aplicación, el servicio debe ser situado
en la misma, mientras que si el servicio está estrictamente relacionado con el
dominio y sirve a una necesidad del dominio, entonces pertenece a la capa de
dominio.