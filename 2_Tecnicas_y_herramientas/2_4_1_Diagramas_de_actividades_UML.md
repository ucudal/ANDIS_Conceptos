# 2 Técnicas y herramientas

## 2.4 Modelos de comportamiento

### 2.4.1 Diagramas de actividad UML

Los diagramas de actividades UML permiten representar flujos de trabajo o
procesos que incluyen opciones, iteraciones y concurrencia, así como los flujos
de datos que ocurren entre actividades relacionadas.

Este documento está basado en UML 2.5.1[^1].

Los diagramas de actividad tienen típicamente:

* Un nodo inicial[^2], que se representa con un círculo negro; no pueden haber
flujos de control que lleguen al nodo inicial.
* Uno o más nodos finales de actividad, que se representan con un círculo negro
  dentro de otro círculo; no puede haber flujos de control que salgan del nodo
final; los nodos finales de actividad terminan todos los flujos de control en
la actividad modelada en el diagrama.
* Un nodo final de flujo, que se representa con un círculo negro con una cruz
  dentro; los nodos finales de flujo terminan un flujo de control.
* Uno o más nodos de actividades, que se representan con un rectángulo con las
  esquinas redondeadas; puede haber sólo un flujo de control de entrada y sólo
  uno de salida de un nodo de actividad.
* Uno o más flujos de control que conectan los nodos, y se representan con
  líneas que terminan con una flecha en la dirección del flujo de control, es
  decir, desde una actividad a la siguiente.

Además, pueden tener:

* Nodos de bifurcación o *fork nodes*, que se representan con una barra en la
  que entra un y sólo un flujo de control y salen dos o más flujos de control;
  el flujo de control de entrada se separa en varios flujos de ejecución
  concurrentes a la salida, es decir, los nodos de actividad que siguen al nodo
  de bifurcación ocurren simultáneamente, en paralelo.
* Nodos de unión o *join nodes*, que se representan también por una barra pero a
  la que entran dos o más flujos de control y sale un y sólo un flujo de
  control; los flujos de entrada se sincronizan a la salida, es decir, todos los
  nodos de actividad anteriores al nodo de unión deben terminar para que
  comience la ejecución del nodo siguiente.
* Nodos de decisión o *decision nodes*, que se representan con un rombo al que
  entra un y sólo un flujo de control y salen dos o más flujos de control; los
  flujos de salida tienen una condición de guarda, y sólo una de las condiciones
  de guarda puede ser verdadera a la vez.
* Nodos de fusión o *merge nodes*, que se representan también con un rombo, pero
  al que entran dos o más flujos de control y sale un y sólo un flujo de
  control; los flujos de control de entrada no son concurrentes.

En la figura 1, a continuación, hay un nodo inicial, la actividad `Cocinar`, y
el nodo final.

![Diagrama de actividades con inicio, una actividad, y
final](/diagrams/Activity_Diagram_Start_End_Action.svg)

*Figura 1: Un diagrama de actividades con un nodo inicial, uno de actividad, y
un nodo final.*

En la figura 2, a continuación, luego de la actividad `Conseguir ingredientes`,
las actividades `Precalentar horno` y `Preparar receta` ocurren simultáneamente,
es decir, el horno se precalienta mientras se prepara la receta. Cuando ambas
actividades terminan, se realiza la actividad `Hornear receta`, es decir, se
tiene que haber terminado de precalentar el horno y de preparar la receta para
poder hornearla.

![Diagrama de actividades con actividades en
paralelo](/diagrams/Activity_Diagram_Fork_Join.svg)

*Figura 2: Un diagrama con actividades en paralelo entre nodos de bifurcación y
de unión.*

En la figura 3, a continuación, la actividad `Conseguir ingredientes faltantes`
ocurre sólo si la condición de guarda `Faltan ingredientes` es verdadera.

![Diagrama de actividades con actividad
condicional](/diagrams/Activity_Diagram_Decision_Merge.svg)

*Figura 3: Un diagrama con una actividad condicional entre un nodo de decisión y
otro de fusión*

En los diagramas de actividades vemos qué actividades tienen lugar, pero no
quién las realiza; esto no es un problema porque muchas veces alcanza con
modelar qué se hace, sin que sea relevante quién lo hace. Sin embargo, es
posible mostrar el participante que realiza cada actividad, utilizando particiones.

Una partición se representa con dos líneas, generalmente paralelas, ya sea
horizontales o verticales, y un nombre que etiqueta la partición en un cuadro en
un extremo. Los nodos de actividad y los flujos de control colocados entre estas
líneas se consideran contenidos dentro de la partición. Esta notación para una
partición se conoce coloquialmente como andarivel —*swimlane*—, como se muestra
en la figura 4 a continuación.

![Partición](/diagrams/Activity_Diagram_Swimlane.svg)

*Figura 4: Una partición utilizando la notación de andarivel.*

Los andariveles pueden representar una jerarquía entre particiones,
representando las sub-particiones como una partición adicional de una
super-partición, como se muestra en la figura 5 a continuación.

![Sub-particiones](/diagrams/Activity_Diagram_Two_Swimlanes.svg)

*Figura 5: Una partición con dos sub-particiones utilizando la notación de
andarivel.*

Los diagramas también se pueden dividir de forma multi-dimensional, como se
muestra en la figura 6, a continuación, donde cada andarivel es una intersección
de múltiples particiones.

![Sub-particiones matriciales](/diagrams/Activity_Diagram_Multidimensional_Swimlanes.svg)

*Figura 6: Particiones multi-dimensionales utilizando la notación de andarivel.*

La figura 7, a continuación, es un ejemplo de las actividades que tienen lugar
en la restaurante para una cena. Los participantes son el `Cliente`, el `Mozo` y
la `Cocina`. El cliente realiza la actividad `Revisar menú`. Luego el mozo
realiza `Tomar pedido`. Luego la cocina realiza `Preparar pedido`. Luego el mozo
realiza `Llevar pedido a la mesa`. Por último, el cliente realiza la actividad
`Cenar`.

![Diagrama de actividades con
particiones en andariveles](/diagrams/Activity_Diagram_Swimlanes_Example.svg)

*Figura 7: Un ejemplo de diagrama de actividades con particiones en
andariveles.*

Cuando utilizar la notación de andarivel es complejo, es posible agregar el
nombre de la partición entre paréntesis en cada nodo de actividad, como se
muestra en la figura 8, a continuación.

![Diagrama de actividades con particiones entre
paréntesis](/diagrams/Activity_Diagram_Partitions_Example.svg)

*Figura 8: El mismo ejemplo de la figura 7, pero con las particiones entre
paréntesis, en lugar de andariveles.*

Otros elementos que pueden aparecer en los diagramas de actividad son las
acciones, que se utilizan para modelar eventos:

* Recepción de señales, que se representan por un pentágono cóncavo, y se
  utilizan para modelar la recepción de un evento externo, por ejemplo, que
  ocurre en un sistema externo, o en otra parte del mismo sistema, pero que no
  estamos modelando.

* Temporizador, que se representan por un reloj de arena, y pueden ser
  utilizadas para modelar señales periódicas, por ejemplo, un evento que ocurre
  una vez al año; o para modelar esperas entre dos actividades consecutivas.

* Envío de señales, que se representan por un pentágono convexo, y se utilizan
  para modelar el envío de un evento a un sistema externo, o a otra parte del
  mismo sistema que no nos interesa modelar.

La figura 9, a continuación, es un ejemplo de un cliente pidiendo la cena a un
restaurante a través de una aplicación; vean que no se modela cómo el cliente
confirma el pedido al restaurante, ni cómo el restaurante hace llegar la cena al
cliente. El cliente realiza la acción `Revisar menú` a la `Hora de la cena`, que
es una acción temporizada. Luego realiza la actividad `Agregar platos al
carrito`, y cuando termina envía la señal `Confirmar pedido`. El restaurante
recibe la señal `Aceptar pedido`, luego realiza la actividad `Preparar pedido`,
y cuando termina, envía la señal `Enviar pedido`. El cliente recibe la señal
`Recibir pedido`, y luego realiza la actividad `Cenar`.

![Diagrama de actividades con
acciones](/diagrams/Activity_Diagram_Send_Receive_Signals.svg)

*Figura 9: Ejemplo de diagrama de actividades con acciones de recepción de
señales, acciones temporizadas, y acciones de envío de señales.*

Los diagramas de actividades tienen otros elementos que no cubrimos en este
documento; puedes ver las páginas sobre diagramas de actividades de las
herramientas de modelado [IBM Software
Architect](https://www.ibm.com/docs/en/rational-soft-arch/9.7.0?topic=diagrams-activity),
[Visual
Paradigm](https://www.visual-paradigm.com/guide/uml-unified-modeling-language/what-is-activity-diagram/)
y [Lucidchart](https://www.lucidchart.com/pages/uml-activity-diagram).

[^1]: OMG. (2017). OMG® Unified Modeling Language®. Disponible
    [aquí](https://www.omg.org/spec/UML/2.5.1/PDF).
[^2]: Puede haber más de un nodo inicial, en cuyo caso existen flujos de control
concurrentes desde esos nodos iniciales al inicio de la actividad modelada en el
diagrama.
