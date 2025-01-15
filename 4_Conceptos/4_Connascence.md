# 4 Conceptos

## Co-nascencia o *connascence*

> [!NOTE]
> El término [nascencia](https://dle.rae.es/nascencia?m=form) se define como la
> acción y efecto de nacer. Por lo tanto, co-nascencia sería algo así como la
> acción y efecto de nacer al mismo tiempo. Sin embargo, este término no es muy
> común en español y en algunos casos se prefiere simplemente usar el término en
> inglés *connascence*.

La co-nascencia es una de las formas con las que se mide la modularidad en
ingeniería de software —las otras son el [acoplamiento](./4_Acoplamiento.md) y
la [cohesión](./4_Cohesion.md)—. Refiere a que dos partes son co-nascentes si
un cambio en una de ellas requiere modificar la otra para mantener la
corrección general del sistema[^1]. La co-nascencia refina los conceptos de
[acoplamiento](./4_Acoplamiento.md) eferente y aferente para los lenguajes de
programación orientada a objetos[^2].

Existen dos tipos de co-nascencia:

* Estática. Refiere al acoplamiento en tiempo de compilación, opuesto al
  acoplamiento en tiempo de ejecución cubierto en la co-nascencia dinámica.
  Puede ser:

  * De nombres. Múltiples partes deben ponerse de acuerdo en el nombre de una
    entidad, por ejemplo, un identificador. Consideren el *refactoring* que
    tienen varios IDE de renombrar identificadores, para que lidiar con este
    tipo de acoplamiento sea trivial.

  * De tipos. Múltiples partes deben ponerse de acuerdo en el tipo de una
    propiedad, un parámetro, una variable local, o del resultado de un método.

  * De significado o de convención. Múltiples partes deben ponerse de acuerdo en
    la semántica de ciertos valores. Por ejemplo, que `true` es `1` y que `false`
    es `0` o que el primer elemento de un vector es `0` o es `1`.

  * De posición. Múltiples partes deben ponerse de acuerdo en el orden de los
    valores. Por ejemplo, en el orden de los parámetros del mismo tipo en la
    firma de un método y en la invocación de ese método.

  * De algoritmos. Múltiples partes deben ponerse de acuerdo en el algoritmo
    utilizado. Por ejemplo, la función [`LOOKUP`](https://support.microsoft.com/en-us/office/lookup-function-446d94af-663b-451d-8251-369d5e3864cb)
    de Excel, que busca un elemento en un vector, requiere que el vector esté
    en orden ascendente; probablemente use internamente un algoritmo de
    [búsqueda binaria](https://en.wikipedia.org/wiki/Binary_search_algorithm).

* Dinámica. Refiere al acoplamiento en tiempo de ejecución. Puede ser:

  * De orden de ejecución. El orden en que se ejecutan diferentes partes es
    importante. Por ejemplo, cuando en un
    [ORM](https://en.wikipedia.org/wiki/Object–relational_mapping), debo asignar
    todas las propiedades de un nuevo objeto, antes de persistirlo en la base de
    datos.

  * De tiempo. El momento de la ejecución de múltiples partes es importantes.
    Por ejemplo, una [condición de carrera](https://en.wikipedia.org/wiki/Race_condition).

  * De valores. Cuando varios valores están relacionados entre sí y deben
    cambiar simultáneamente. Por ejemplo, las transacciones en una base de
    datos, permiten lidiar con este tipo de acoplamiento.

  * De identidad. Cuando varias partes deben referenciar a la misma entidad. Por
    ejemplo, una clave primaria en una base de datos.

La co-nascencia dinámica es más difícil de determinar que la estática,
típicamente por la falta de herramientas que permitan analizar el comportamiento
dinámico de un sistema, a diferencia de las herramientas de análisis estático de
código.

[^1]: Page-Jones, M. (1996). What Every Programmer Should Know About
    Object-Oriented Design. Dorset House.
[^2]: Richards, M. (2020). Fundamentals of Software Architecture. O'Reilly.
