# 4 Conceptos

## Sistema adyacente

Los sistemas adyacentes son simplemente eso: sistemas de algún tipo
‑automatizados o humanos‑ que residen adyacentes ‑al lado‑ del
[trabajo](./4_Trabajo_y_area_de_trabajo.md). Se muestran como actores en el
[diagrama de/2_Tecnicas_y_herramientas/2_01_2_Diagramas_de_contexto.md
contexto](/2_Tecnicas_y_herramientas/2_1_02_Diagramas_de_contexto.md) y reciben
datos o servicios del trabajo y, a su vez, suministran datos al trabajo[^1].

El alcance del producto que se construye ‑es decir, la funcionalidad que incluye
en la solución‑ está determinado en parte por los sistemas adyacentes. Es
necesario comprenderlos y comprender su papel potencial en el trabajo.

Es útil pensar que estos sistemas pertenecen a uno de tres tipos:

* **Activos**. Los sistemas adyacentes activos son humanos que pueden
  interactuar con el trabajo o participar en él.

  Aunque el sistema adyacente activo está técnicamente fuera del alcance del
  trabajo, deben considerar si es posible ampliar el alcance del producto para
  incluir parte del sistema adyacente. ¿Puede el producto realizar parte del
  trabajo que realiza actualmente el sistema adyacente? ¿O hay una ventaja para
  el trabajo si el sistema adyacente realiza algunas de las funciones que el
  trabajo realiza actualmente?

* **Autónomos**. Un sistema adyacente autónomo es alguien externo ‑como otra
  empresa, un sistema informático o un cliente‑ que no interactúa directamente
  con el trabajo, sino que actúa independientemente del trabajo pero tiene
  conexiones con él.

  Los sistemas adyacentes autónomos se comunican a través de flujos de datos
  unidireccionales y no es posible una interacción de ida y vuelta.

  Al principio podría parecer que hay pocas oportunidades para involucrar a los
  sistemas adyacentes autónomos pasivos en el trabajo, pero deben asegurarse de
  que el sistema adyacente realmente elige ser autónomo y no que la tecnología
  del trabajo lo obliga a serlo.

  Hay muchas oportunidades para construir mejores productos ‑desde el punto de
  vista del cliente‑ involucrando a los sistemas adyacentes. Todo lo que
  necesitan es familiarizarse lo suficiente con el sistema adyacente autónomo
  para identificar una oportunidad y el deseo de ampliar el alcance del producto
  para involucrar más estrechamente al sistema adyacente en el trabajo.

* **Cooperativos**. Los sistemas cooperativos adyacentes son sistemas
  automatizados que colaboran con el trabajo durante el transcurso de un caso de
  uso del negocio, generalmente mediante un simple diálogo de mensaje-respuesta.
  Un sistema adyacente cooperativo  podría ser un sistema automatizado que
  contenga una base de datos a la que se accede o se escribe durante el trabajo,
  un sistema automatizado que realiza algunos cálculos para el trabajo, o
  cualquier otro sistema automatizado que proporcione un servicio predecible e
  inmediato al trabajo. Debido a que gran parte de lo que hacen las
  organizaciones ha sido automatizado, casi siempre aparecen varios sistemas
  cooperativos adyacentes en el diagrama de contexto.

  Es poco probable que necesites ‑o desees‑ cambiar las interfaces con un
  sistema adyacente cooperativo. Estos sistemas son como cajas negras, sus
  servicios son estables y rara vez pueden ganar mucho intentando cambiarlos.
  Mientras el producto pueda comunicarse correctamente, el sistema cooperativo
  adyacente puede seguir siendo una caja negra. El único motivo para el cambio
  es si el producto necesita un servicio o datos diferentes.

[^1]: Robertson, S. & Robertson, J. (2012). Mastering the Requirements Process:
    Getting Requirements Right, 3<sup>rd</sup> Edition. Addison-Wesley Professional.
    Disponible en
    [biblioteca](https://catalogo.ucu.edu.uy/cgi-bin/koha/opac-detail.pl?biblionumber=121158).
