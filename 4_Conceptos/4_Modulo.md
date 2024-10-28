# 4 Conceptos

## Módulo en *Domain-Driven Design*

Este documento está basado en [^2] y [^1].

[^2]: Evans, E. (2015). Domain-DrivenDesign Reference: Definitions and Pattern
    Summaries. Domain Language, Inc. Disponible
    [aquí](https://www.domainlanguage.com/wp-content/uploads/2016/05/DDD_Reference_2015-03.pdf).

[^1]: Avram, A; Marinescu, F. (2006). Domain-Driven Design Quickly. InfoQ.
    Disponible
    [aquí](https://www.infoq.com/minibooks/domain-driven-design-quickly/).

Para una aplicación grande y compleja, el modelo tiende a crecer junto a ella,
llegando a un punto en el cual es complicado entender el modelo como un todo.
Por esta razón, es necesario organizar el modelo en módulos que agrupan
conceptos y tareas relacionadas con el fin de reducir la complejidad del modelo.

Los módulos son una forma sencilla y eficaz de manejar la complejidad y se usan
en la mayoría de proyectos. Para entender un modelo con módulos, primero se
obtiene una imagen general observando los módulos y sus relaciones, y luego se
puede entrar en más detalle adentrándose en un módulo específicamente.

Los módulos también favorecen a la calidad del código al proveer mayor
[cohesión](./4_Cohesion.md) y menor [acoplamiento](./4_Acoplamiento.md). Para
lograr esto, se agrupan en módulos las clases altamente relacionadas y se
definen interfaces bien definidas para los módulos, de modo que los módulos
interactúan a través de ellas, en vez de interactuar con varias clases
directamente.

Para definir módulos, puedes considerar las siguientes recomendaciones:

* Elije módulos que cuenten la historia del sistema y contengan un conjunto de
  conceptos cohesivos.

* Busca reducir el acoplamiento entre módulos creando módulos que puedan ser
  razonados de forma independiente entre ellos.

* Refina el modelo hasta que sea particionado en conceptos de alto nivel y su
  código sea desacoplado.

* Nombra los módulos utilizando el lenguaje ubicuo.

* Es recomendado que los módulos sean algo flexibles para que puedan evolucionar
  junto al proyecto.
