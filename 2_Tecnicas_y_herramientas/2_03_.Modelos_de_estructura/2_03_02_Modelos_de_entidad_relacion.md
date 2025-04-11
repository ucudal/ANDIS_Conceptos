# 2 Técnicas y herramientas

## 2.3 Modelos de estructura

### Modelos de entidad relación

Un modelo entidad-relación ‑también llamado MER‑ describe "cosas" de interés
relacionadas entre sí en el dominio de conocimiento del
[trabajo](/4_Conceptos/4_Trabajo_y_area_de_trabajo.md). Un modelo
entidad-relación básico se compone de tipos de entidades con sus atributos y
especifica las relaciones que pueden existir entre instancias de esos tipos de
entidades.

El modelado entidad-relación fue desarrollado por Peter Chen[^1] y la notación
usada por él fue luego extendida por Gordon Everest[^2] ‑conocida habitualmente
como notación "pata de gallo" o "*crow's foot*"‑. Este documento está
basado en esos artículos.

Los diagramas con la notación de Chen de un modelo de entidad-relación pueden
contener:

* Conjuntos de entidades fuertes, que se representan con un rectángulo. El
  rectángulo contiene siempre el nombre de la entidad. Estas entidades pueden
  ser identificadas de forma unívoca por sus atributos.

* Conjuntos de entidades débiles, que se representan con un rectángulo con
  líneas dobles. El rectángulo contiene siempre el nombre de la entidad. Estas
  entidades deben participar en una relación ‑no pueden existir sin la otra
  entidad de la relación‑ y no pueden ser identificadas unívocamente ‑dependen
  de otra entidad en la relación‑.

* Conjuntos de entidades asociativas, que se representan con un rectángulo con
  un rombo dentro. Relacionan las instancias de varios tipos de entidades.
  También contienen atributos específicos de la relación entre esas instancias
  de entidad.

* Conjuntos de relaciones, que se representan con un rombo. El rombo contiene
  siempre el nombre de la relación. Modelan una asociación entre instancias de
  los conjuntos de entidades relacionadas.

* Conjuntos de relaciones débiles, que se representan con un rombo con líneas
  dobles. El rombo contiene siempre el nombre de la relación. Modelan la
  asociación entre instancias de un conjunto de entidades débiles con un
  conjunto de las entidades fuertes relacionado.

* Atributos, que se representan con un óvalo conectado por una línea a la
  entidad correspondiente. El óvalo contiene siempre el nombre del atributo.
  Modelan características de una entidad, de una relación de muchos a muchos o
  de una relación de uno a uno.

* Atributos multi-valuados, que se representan con un óvalo con líneas dobles.
  Un atributo multi-valuado puede tomar más de un valor.

* Atributos derivados, que se representan con un óvalo con líneas punteadas. El
  valor de un atributo derivado puede ser calculado a partir de los valores de
  otros atributos.

Cuando un atributo es clave primaria ‑permite identificar de forma unívoca‑ el
nombre va subrayado.

Además de estos elementos, es posible indicar la cardinalidad de las relaciones.
La siguiente notación fue propuesta por Chen:

* `0`, si cada instancia de la entidad no está obligada a participar de la
  relación.

* `1`, si toda instancia de la entidad está obligada a participar de la
  relación; además participa una sola vez.

* `N`, `M` o `*`, si cada instancia de la entidad no está obligada a participar
  en la relación y puede hacerlo cualquier cantidad de veces.

En la notación de "pata de gallo" las relaciones se representan con líneas que
conectan las entidades ‑y no como rombos‑ y los atributos van uno por línea
dentro de la entidad.

A diferencia de la notación para la cardinalidad propuesta por Chen, la
notación "pata de gallo" tiene dos indicadores; la cardinalidad se indica de los
dos lados de la relación:

* El anillo representa "cero"
  <br><span style="font-size:200%;">ᐤ</span>
* El guión representa "uno"
  <br><span style="font-size:200%;">∣</span>
* La pata de gallo representa "muchos" o "infinito"
  <br><span style="font-size:200%;">⪪</span>

Estos símbolos se utilizan en pares para representar los cuatro tipos de
cardinalidad que puede tener una entidad en una relación. El componente interno
de la notación representa el mínimo y el componente externo representa el
máximo.

* Anillo y guión → mínimo cero, máximo uno (opcional)
* Guión y guión → mínimo uno, máximo uno (obligatorio)
* Anillo y pata de gallo → mínimo cero, máximo muchos (opcional)
* Guión y pata de gallo → mínimo uno, máximo muchos (obligatorio)

<span id="figura-1"/>

![Ejemplos de cardinalidad](/diagrams/Entity_Relationship_Diagram_Cardinality.svg)

*Figura 1: Ejemplos de cardinalidad.*

El ejemplo en la [Figura 2](#figura-2), a continuación, muestra una versión
simplificada de un sistema de reservas de hotel donde los clientes pueden
reservar habitaciones y los hoteles llevan un registro del mantenimiento de las
habitaciones.

<span id="figura-2"/>

![Ejemplo de un diagrama de entidad relación con la notación de
Chen](/diagrams/Entity_Relationship_Model_Example_Chen.svg)

*Figura 2: Ejemplo de un diagrama de entidad relación con la notación de Chen.*

`Hotel` y `Cliente` son entidades fuertes porque tienen atributos que son clave
primaria propios que los identifican de manera única (`RUT` para `Hotel` y
`Cédula` para `Cliente`).

`Habitación` es una entidad débil porque su existencia depende de la entidad
fuerte `Hotel`. La clave primaria de `Habitación` es una combinación de `Número`
‑de `Habitación`‑ y `RUT` ‑de `Hotel`‑.

La relación `Reserva` entre `Cliente` y `Hotel` es una relación fuerte, ya
que ambos, `Cliente` y `Hotel`, son entidades fuertes.

La relación `Mantenimiento` entre `Hotel` y `Habitación` es una relación débil,
ya que involucra la entidad débil `Habitación`.

En la [Figura 3](#figura-3), a continuación, aparece el mismo diagrama, pero en
la notación de "pata de gallo".

<span id="figura-3"/>

![Ejemplo de un diagrama de entidad relación con la notación pata de
gallo](/diagrams/Entity_Relationship_Model_Example_Crows_Foot.svg)

*Figura 3: Ejemplo de un diagrama de entidad relación con la notación pata de
gallo.*

[^1]: Chen, P. (1976). The Entity-Relationship Model-Toward a Unified View of
      Data. ACM Transactions on Database Systems, 1 (1): 9-36. Disponible
      [aquí](https://dl.acm.org/doi/pdf/10.1145/320434.320440).
[^2]: Everest, G. (1976). Basic Data Structure Models Explained with a Common
      Example". Computing Systems 1976, Proceedings Fifth Texas Conference on
      Computing Systems, Austin, TX: 39-46. Disponible
      [aquí](https://www.researchgate.net/publication/291448084_BASIC_DATA_STRUCTURE_MODELS_EXPLAINED_WITH_A_COMMON_EXAMPLE)
