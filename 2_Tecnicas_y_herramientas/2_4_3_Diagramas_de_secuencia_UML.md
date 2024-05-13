# 2 Técnicas y herramientas

## 2.4 Modelos de comportamiento

### 2.4.2 Diagramas de secuencia UML

Los diagramas de secuencia se utilizan para mostrar las interacciones entre
instancias de [clasificadores](/4_Conceptos/4_Clasificador.md), incluyendo la
secuencia en que ocurren esas interacciones, para implementar algún
comportamiento. Las interacciones ocurren mediante el intercambio de mensajes.

Este documento está basado en UML 2.5.1[^1].

Los diagramas de secuencia típicamente tienen:

* Líneas de vida o *lifelines*, que se representan por un rectángulo y una línea
  vertical —opcionalmente punteada—, y modelan lo que ocurre en la vida de una
  instancia, con el tiempo transcurriendo desde arriba hacia abajo. Dentro del
  rectángulo van dos puntos y el nombre del
  [clasificador](/4_Conceptos/4_Clasificador.md) de la instancia; los dos puntos
  se utilizan para indicar que es una instancia, y no un clasificador. En caso
  de que sea relevante el nombre de la instancia —para identificar instancias
  del mismo clasificador— se escribe el nombre de la instancia antes de los dos
  puntos.
* Mensajes, que se representan con una flecha desde la línea de vida del emisor
  hasta la del receptor, y modelan el transporte de información de una instancia
  a otra, con la expectativa que se origine una actividad, ya sea una operación
  o una señal. El mensaje incluye el nombre de la operación o de la señal que el
  emisor quiere que el receptor ejecute o reciba. El orden en el que se envían
  los mensajes es de arriba hacia abajo, y la distancia entre los mensajes no es
  significativa, excepto en los sistemas en tiempo real.
* Activaciones, que se representan con un rectángulo delgado sobre una línea de
  vida, para modelar cuándo la instancia está activa y puede enviar mensajes.

En la figura 1, a continuación, hay tres líneas de vida con instancias de
`Cliente`, `Carrito` y `Stock`. El cliente podría ser un actor y el carrito y el
stock podrían ser componentes, por ejemplo. El primer mensaje desde `Cliente` a
`Carrito` es un mensaje de creación, por eso va a la cabecera de la línea de
vida. Luego `Cliente` envía un mensaje `Agregar artículo` con parámetro `id` a
`Carrito` para indicar que el carrito debe agregar un producto. Luego `Carrito`
envía un mensaje `Comprobar disponibilidad` con el mismo parámetro `id` a
`Stock`. Luego `Stock` retorna la disponibilidad en un mensaje de respuesta a
`Carrito`. A continuación `Carrito` se envía a sí mismo un mensaje `Agregar
producto`, con parámetro `id`, para agregar el producto al carrito. Luego envía
el mensaje de respuesta `Carrito actualizado` a `Cliente`. Por último, `Cliente`
envía el mensaje `Guardar` a `Carrito`.

![Un diagrama se secuencia con líneas de vida y
mensajes](/diagrams/Sequence_Diagram_Lifelines_Messages.svg)

*Figura 1: Un diagrama de secuencia con tres instancias y varios mensajes*

Existen varios tipos de mensajes:

* Asíncronos, que se dibujan con una flecha con las puntas abiertas:

![](/diagrams/Sequence_Diagram_Async_Message.svg)

* Sincrónicos, que se dibujan con una fecha con un triángulo relleno:

![](/diagrams/Sequence_Diagram_Sync_Message.svg)

* Respuesta, que se dibujan con una línea punteada; estos mensajes son
  opcionales:

![](/diagrams/Sequence_Diagram_Reply_Message.svg)

* Perdido —*lost*—, que se dibujan con un círculo al final del mensaje, en el
  lugar en el que estaría el receptor, y que se utilizan para modelar un mensaje
  enviado por un emisor pero se desconoce o no interesa modelar el receptor.

![](/diagrams/Activity_Diagram_Lost.svg)

* Encontrado —*found*—, que se dibujan con un círculo al inicio del mensaje, en
  el lugar en el que estaría el emisor, y que se utiliza para modelar un mensaje
  recibido por un receptor pero que se desconoce o no interesa modelar el
  emisor.

![](/diagrams/Activity_Diagram_Found.svg)

Los diagramas de secuencia pueden tener regiones, que contienen un subconjunto
de los mensajes del diagrama. Las regiones se representan con un rectángulo con
el nombre de la región en la esquina superior izquierda, y pueden ser usados
para modelar:

* Bucles —*loop*, *foreach*—: los mensajes en la región se ejecutan en un bucle
  controlador por una condición de guarda —*guard condition*— o para todos los
  elementos de una colección; la condición de guarda se indica también en la
  esquina superior izquierda.

* Condicionales —*alt*, *alt-else*, *case*: Los mensajes en la región se
  ejecutan si se cumple una condición de guarda. En el caso de *alt-else* la
  región se divide con una línea horizontal, y los mensajes en la parte superior
  se ejecutan si la condición de guarda se cumple, de lo contrario se ejecutan
  los mensajes en la parte inferior. En el caso de *case* la región se divide
  también mediante una línea horizontal, y los mensajes en cada una de las
  partes en las que queda dividida la región se ejecuta si se cumple una
  condición de guarda. Las condiciones de guarda se indican también en la
  esquina superior izquierda.

* Referencias —*ref*—: La parte dentro de la región se omite en este diagrama,
  pero se detalla en otro diagrama cuyo nombre coincide con el de la región.

En la figura 2, a continuación, el ejemplo es similar al de la figura 1,
agregando una región `foreach` con la guarda `artículo` para indicar que los
mensajes dentro de esa región ocurren para cada artículo; en la región `alt` se
utiliza el valor `disponible` retornado por el mensaje `Comprobar
disponibilidad` para la condición de guarda de la parte superior de la región, y
la condición de guarda contraria `[!disponible]` para la inferior.

![Un diagrama de secuencia con regiones foreach y
alt](/diagrams/Sequence_Diagram_Loop_Alt.svg)

En los diagramas de secuencia se suele poner a la izquierda los clasificadores
que desencadenan la secuencia, pero esto no es obligatorio, es sólo una
convención para facilitar la lectura.

A veces los mensajes no corresponden con operaciones, sino que describen el
significado general del mensaje.

Puedes ver más información sobre diagramas de secuencia en las herramientas de
modelado [IBM Software
Architect](https://www.ibm.com/docs/en/rational-soft-arch/9.7.0?topic=diagrams-sequence),
[Visual
Paradigm](https://www.visual-paradigm.com/learning/handbooks/software-design-handbook/sequence-diagram.jsp)
y [Lucidchart](https://www.lucidchart.com/pages/uml-sequence-diagram).

[^1]: OMG. (2017). OMG® Unified Modeling Language®. Disponible
    [aquí](https://www.omg.org/spec/UML/2.5.1/PDF).