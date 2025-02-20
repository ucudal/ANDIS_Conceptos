# 2 Técnicas y herramientas

## 2.1 Relevamiento

### 2.1.9 *Brown Cow Model*

El *Brown Cow Model* es un modelo con cuatro vistas del
[trabajo](/4_Conceptos/4_Trabajo_y_area_de_trabajo.md), cada una de las cuales
proporciona al analista y a los [interesados](/4_Conceptos/4_Interesado.md)
información que es útil en diferentes etapas del proceso de descubrimiento de
requisitos.

Este documento está basado en [^1].

[^1]: Robertson, S. & Robertson, J. (2012). Mastering the Requirements Process:
Getting Requirements Right, 3<sup>rd</sup> Edition. Addison-Wesley Professional.

> Hay algo peor que no resolver el problema y es resolver el problema
> equivocado
>
> Peter Drucker[^2]

[^2]: Peter Drucker (1909-2005), es conocido como el padre de la administración
moderna. El contexto de su cita se relaciona con su énfasis en que los tomadores
de decisión a menudo se apresuran a implementar soluciones sin haber definido
adecuadamente el problema central.

> Un problema bien planteado es un problema medio resuelto.
>
> Charles Kettering[^3]

[^3]: Charles Kettering (1876-1958), como inventor y director de General Motors,
trabajaba frecuentemente en el desarrollo de nuevas tecnologías. La cita refleja
su experiencia en investigación y desarrollo, donde observó que la claridad en
la definición del problema era crucial para el éxito de cualquier proyecto.

> La parte más difícil de resolver un problema es describir el problema con
> precisión. Una solución incorrecta a un problema bien definido es mucho mejor
> que una buena solución a un problema mal definido
>
> Jimmy Soni[^4]

[^4]: Jimmy Soni es un premiado escritor que entre otras obras escribió The
Founders: The Story of PayPal and the Entrepreneurs Who Shaped Silicon Valley y
A Mind at Play: How Claude Shannon Invented the Information Age.

La inclusión de estas citas intentan demostrar la importancia de definir
correctamente un problema como requisito previo a resolver correctamente un
problema.

El modelo *brown cow* permite llegar al verdadero problema mediante la
abstracción, centrándose en las ideas en lugar de en las soluciones, o dicho de
otro modo, la abstracción implica pensar en la esencia del tema descartando los
componentes tecnológicos y físicos.

Probablemente conozcas la historia de Blockbuster y Netflix. Blockbuster nació
en 1985 y expandió sus locales por todo el mundo ofreciendo un servicio de
alquiler de películas para ver en casa. En 1997 nació Netflix con un servicio
similar pero con la diferencia que te mandaban las películas por correo. Mucho
antes de que Netflix se convirtiera en un servicio de *streaming* la posición
dominante de Blockbuster ya estaba amenazada y sus ganancias estaban bajando. El
resto es historia. ¿La moraleja? El problema no era que la gente quería ver
películas, sino que no quería salir de su casa para conseguir la película que
quería ver.

El *Brown Cow Model* utiliza cuatro perspectivas —o *viewpoints*— acerca del
[trabajo](/4_Conceptos/4_Trabajo_y_area_de_trabajo.md): un eje horizontal separa
el ≪qué≫ del ≪cómo≫ y otro eje vertical separa el ≪ahora≫ del ≪futuro≫, dando
lugar a cuatro cuadrantes —que exploraremos a continuación—, uno para cada
perspectiva del trabajo, como se muestra en la [Figura 1](#figura-1).

<span id="figura-1"/>

![Brown Cow Model](/diagrams/Brown_Cow_Model.svg)

*Figura 1: Brown Cow Model*. Tomado de [^1].

* **Cómo-Ahora**. Este es casi siempre —pero no siempre— el punto de partida. La
  perspectiva ≪cómo-ahora≫ muestra la implementación del trabajo tal como existe
  actualmente, incluyendo artefactos, personas y procesos utilizados. Se usa
  esta perspectiva cuando necesitas una base suficiente para comenzar a formular
  otras preguntas.

  Al construir un nuevo producto, no se intenta simplemente duplicar lo que
  existe, porque eso no generaría ningún beneficio. En cambio, al eliminar los
  fósiles tecnológicos y procedimientos organizacionales obsoletos de la
  situación actual, se comienza a ver el problema del negocio puro y sin
  adulterar.

  El modelado del estado actual debe terminar tan pronto como sea posible: un
  modelo útil es un modelo que funciona, en el sentido de que permite mostrar
  cómo el negocio obtiene resultados a partir de los insumos. No tiene sentido
  modelar en detalle algo que va a ser reemplazado en breve.

* **Qué-Ahora**. La perspectiva abstracta ≪qué-ahora≫ revela la verdadera
  esencia del trabajo. Esta visión es completamente neutral en términos
  tecnológicos y muestra el negocio como si no existieran máquinas, personas o
  estructura organizacional. Esta perspectiva se usa para purificar las ideas
  sobre lo que el negocio realmente está haciendo, sin mencionar procesadores y
  artefactos que podrían no formar parte de una implementación futura.

* **Qué-Futuro**. La perspectiva ≪qué-futuro≫ muestra el negocio como el dueño
  desea tenerlo, pero aún sin la tecnología que podría utilizarse para
  implementarlo. Es la versión más pura del estado futuro propuesto para el área
  de negocio.

  El valor de esta perspectiva es que muestra —para poder discutir con los
  interesados— exactamente lo que el dueño quisiera hacer, sin preocuparse por
  cómo la tecnología podría llevarlo a cabo.

* **Cómo-Futuro**. Esta es la última perspectiva, donde se toma la vista
  idealizada de las futuras políticas del negocio, y se aumentan con la
  tecnología y las personas necesarias para traerla al mundo real.

El *Brown Cow Model* puede ser utilizado junto con la [*Benefits Dependency
Network*](./2_1_10_Benefits_Dependency_Network.md) para mostrar —en línea con
las perspectivas mencionadas— cómo los cambios en el futuro del negocio y las
inversiones para el producto de software están alineadas con los objetivos del
negocio.
