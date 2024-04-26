# Conceptos

## Acoplamiento

El acoplamiento es una de las formas con las que se mide la modularidad en
ingeniería de software —las otras son la [cohesión](./4_Cohesion.md) y la
[co-nascencia o *connascence*](./4_Connascence.md)——. Refiere a la conexión
entre partes de diferentes módulos o entre diferentes módulos, y puede ser
aferente —hacia adentro— o eferente —hacia afuera—[^1]:

* El acoplamiento aferente mide el número de conexiones entrantes a una parte de
un módulo.

* El acoplamiento eferente mide las conexiones salientes con otras partes en
  otros módulos.

Además de los módulos y sus partes es importante la conexión entre las partes de
diferentes módulos y la conexión entre los diferentes módulos; cuando las partes
de diferentes módulos están conectadas, los módulos de esas partes también están
conectados, aunque el tipo de conexión puede ser diferente; veamos algunos
ejemplos:

* Cuando una clase en un espacio de nombres en C# declara una propiedad, un
  parámetro, una variable local, o el resultado de un método de un tipo definido
  en otro espacio de nombres, es necesario incluir la cláusula `using` para
  referenciar este último espacio de nombres; es decir, un espacio de nombres
  **usa** tipos del otro[^2]. El espacio de nombres que usa tipos del otro tiene
  un acoplamiento eferente con el espacio de nombres usado; y éste último un
  acoplamiento aferente con el primero.

* En ese mismo ejemplo, si la primera de esas clases está en un ensamblado y la
  segunda está en otro ensamblado, es necesario agregar una **referencia** en la
  definición del proyecto donde se declara la primera clase al ensamblado donde
  está la segunda clase. El ensamblado referenciado tiene un acoplamiento
  eferente con el ensamblado donde se lo referencia; y este último tiene un
  acoplamiento aferente con el primero.

El acoplamiento es menos discrecional que la cohesión, las conexiones salientes
y entrantes están bien determinadas.

Continuando con los ejemplos anteriores, un ensamblado en C# está altamente
acoplado si referencia a varios otros ensamblados; esto puede ser un problema
porque si hay cambios en los tipos de los otros ensamblados, por ejemplo porque
cambian firmas de métodos o nombres de clases, hay grandes chances de tener que
modificar el primero; cuando desplegamos una nueva versión de los otros
ensamblados, hay grandes chances de tener que desplegar una nueva versión del
primero.

[^1]: Yourdon, E. & Constantine, L. (1979). Structured Design: Fundamentals of a
    Discipline of Computer Program and Systems Design. Prentice-Hall.
[^2]: Es posible evitar esto usando el calificador completo del tipo de datos;
    esto simplifica la escritura de código pero no elimina la conexión —la
    dependencia— entre las clases de los diferentes espacios de nombres.
