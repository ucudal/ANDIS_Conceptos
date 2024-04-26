# 2 Técnicas y herramientas

## 2.4 Modelos de procesos

### 2.4.1 Diagramas de actividad UML

Los diagramas de actividad UML permiten representar flujos de trabajo o
procesos que incluyen opciones, iteraciones y concurrencia, así como los flujos
de datos que ocurren entre actividades relacionadas.

Los diagramas de actividad tienen típicamente:

* Un nodo inicial[^1], que se representa con un círculo negro; no pueden haber
flujos de control que lleguen al nodo inicial.
* Uno o más nodos finales de actividad, que se representan con un círculo negro
  dentro de otro círculo; no puede haber flujos de control que salgan del nodo
inicial; los nodos finales de actividad, termina todos los flujos de control en
la actividad modelada en el diagrama.
* Un nodo final de flujo, que se representa con un círculo negro con una cruz
  dentro; los nodos finales de flujo terminan un flujo de control.
* Uno más nodos de actividades, que se representan con un rectángulo con las
  esquinas redondeadas; puede haber sólo un flujo de control de entrada y sólo
  uno de salida de un nodo de actividad.
* Uno o más flujos de control que conectan los nodos, y se representan con
  líneas que terminan con una flecha en la dirección del flujo.

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
* Nodos de fusión o *merge nodes*, que se representan con un rombo, al que
  entran dos o más flujos de control y sale un y sólo un flujo de control; los
  flujos de control de entrada no son concurrentes.
* Nodos de decisión, que se representan también con un rombo pero al que entra
  un y sólo un flujo de control y salen dos o más flujos de control; los flujos
  de salida tienen una condición de guarda, y sólo una de las condiciones de
  guarda puede ser verdadera.

![Diagrama de actividades con inicio, una actividad, y
final](/diagrams/Activity_Diagram_Start_End_Action.svg)

[^1]: Puede haber más de un nodo inicial, en cuyo caso existen flujos de control
concurrentes al inicio de la actividad modelada en el diagrama.
