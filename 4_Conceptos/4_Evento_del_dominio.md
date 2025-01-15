# 4 Conceptos

## Evento del dominio

Este documento está basado en [^2] y [^1].

[^2]: Evans, E. (2015). Domain-Driven Design Reference: Definitions and Pattern
    Summaries. Domain Language, Inc. Disponible
    [aquí](https://www.domainlanguage.com/wp-content/uploads/2016/05/DDD_Reference_2015-03.pdf).

[^1]: Avram, A; Marinescu, F. (2006). Domain-Driven Design Quickly. InfoQ.
    Disponible
    [aquí](https://www.infoq.com/minibooks/domain-driven-design-quickly/).

Una [entidad](./4_Entidad.md) es responsable de conocer y manipular sus datos a
lo largo de su ciclo de vida. Aunque típicamente no son explícitas las causas de
los cambios en el estado de las entidades y puede ser difícil explicar cómo la
aplicación llegó a tener los valores que tiene en un momento dado.

Otro tema diferente, pero relacionado, son las cuestiones que aparecen en los
sistemas distribuidos, en los que el estado no siempre es consistente
—[consistencia eventual](https://en.wikipedia.org/wiki/Eventual_consistency)—.
Mientras que en los [agregados](./4_Agregado.md) se puede mantener la
consistencia internamente, otros cambios deben ser asíncronos y propagarse a
través de la red.

Para definir eventos del dominio, considera lo siguiente:

* Modela la información acerca de una actividad en el [dominio](./4_Dominio.md)
  como una serie de **eventos discretos**.

* Representa cada evento como un objeto del dominio.

Un evento de dominio es una parte completa del modelo de dominio, una
representación de algo que sucedió en el dominio. Compáralo con [evento del
negocio](./4_Evento_del_negocio.md). Ignora la actividad irrelevante del
dominio, mientras haces explícitos los eventos a los que los expertos del
dominio desean responder, o de los que desean recibir notificaciones, o que
están asociados con el cambio de estado en los otros objetos del modelo.

En un sistema distribuido, el estado de una entidad se puede inferir a partir de
los eventos de dominio actualmente conocidos por un nodo particular, lo que
permite un modelo coherente en ausencia de información completa sobre el sistema
en su conjunto.

Mira cómo este concepto interviene en el patrón Event Sourcing
[aquí](https://martinfowler.com/eaaDev/EventSourcing.html) o
[aquí](https://learn.microsoft.com/en-us/azure/architecture/patterns/event-sourcing),
y en el patrón CQRS o *Command Query Responsibility Segregation*
[aquí](https://martinfowler.com/bliki/CQRS.html) o
[aquí](https://learn.microsoft.com/en-us/azure/architecture/patterns/cqrs).
