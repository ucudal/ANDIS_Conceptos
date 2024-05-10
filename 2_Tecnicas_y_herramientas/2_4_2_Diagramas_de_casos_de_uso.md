# 2 Técnicas y herramientas

## 2.4 Modelos de procesos

### 2.4.2 Diagramas de casos de uso UML

Los diagramas de casos de uso permiten mostrar una visión general de los actores
y de los casos de uso de un sujeto —es decir, de un componente, de un artefacto,
de un nodo, de un subsistema, etc.—, así como de la relación entre ellos: qué
actores participan en qué casos de uso, o qué casos de uso incluyen o extienden
a otros.

Este documento está basado en UML 2.5.1[^1].

Tengan en cuenta que este diagrama sólo incluye los nombres de los casos de uso,
así que también va a ser necesario el escenario detallado del [caso de
uso](/3_Plantillas/3_3_Casos_de_uso.md).

Los diagramas de casos de uso tienen:

* Actores, que se representan con un "muñequito de palitos", y modelan un rol
  desempeñado por un usuario, un dispositivo, un sistema, etc. Los actores
  pueden estar relacionados entre ellos, por ejemplo, por relaciones de
  generalización.
* Casos de uso, que se representan con un óvalo, y modelan un comportamiento que
  el sujeto puede realizar con uno o más actores. Los casos de uso pueden estar
  relacionados entre ellos también por relaciones de extensión —*extends*— y de
  inclusión —*includes*—.
* Asociaciones entre actores y casos de uso, que se representan con una línea
  que une el actor con el caso de uso, y modelan la interacción entre ellos. Las
  asociaciones pueden tener cardinalidad en ambos extremos, aunque generalmente
  es uno a uno.
* Límite del sistema o del sujeto que está siendo modelado, que se representa
  con un rectángulo con los casos de uso dentro y los actores fuera de él.

El ejemplo a continuación muestra varios actores y casos de uso. En el caso de
uso `Hacer pedido al restaurante` participan los actores `Cliente` y
`Restaurante`. En el caso de uso `Preparar pedido` participa solamente el actor
`Restaurante`. En el caso de uso `Entregar pedido al delivery` participan los
actores `Restaurante` y `Delivery`. Por último, en el caso de uso `Llevar pedido
al cliente` participan tanto los actores `Delivery` como `Cliente`. El ejemplo
muestra también los límites del sistema.

![Diagrama de casos de uso con actores, casos y de uso, y limite del
sistema](/diagrams/Use_Case_Diagram_Actors_Use_Cases_System_Boundary.svg)

*Figura 1: Un diagrama de casos de uso con casos de uso, actores, y límite del
sistema.*

Aunque los casos de uso en el diagrama de casos de uso no muestran detalle de
cómo se implementan, es posible modelar el comportamiento de un caso de uso
en otro diagrama de comportamiento, por ejemplo, un diagrama de máquina de
estados o un [diagrama de actividades](./2_4_1_Diagramas_de_actividades_UML.md).

Un caso de uso puede estar relacionado con otro mediante *include* y *extends*.
Estas relaciones se modelan como flechas punteadas:

* Inclusión o *include*, modela cuando un caso de uso incluye un comportamiento
  especificado en otro caso de uso. Esto es útil para reutilizar casos de uso.
* Extensión o *extends*, modela cuando un caso de uso agrega comportamiento
  específico a otro; el caso de uso extendido debe tener previsto dónde agregar
  el comportamiento mediante puntos de extensión o *extension points*.

En la figura 2, a continuación, el caso de uso `Hacer pedido al restaurante`
incluye el caso de uso `Pagar el pedido`, es decir, al hacer el pedido al
restaurante se debe también pagar el pedido. En este ejemplo se modela de esta
manera porque el pago del pedido puede ser utilizado en otros casos de uso, no
sólo al hacer el pedido al restaurante.

A su vez, el caso de uso `Pagar el pedido` tiene un punto de extensión llamado
`Forma de pago`, es decir, tiene previsto que la forma de pago pueda variar. Los
casos de uso `Pagar con tarjeta de débito` y `Pagar con transferencia bancaria`
tienen el mismo comportamiento que `Pagar el pedido`, pero en el primer caso el
punto de extensión se reemplaza por el pago con tarjeta de débito, y en el
segundo con el pago por transferencia bancaria; en los casos de uso que
extienden no es necesario repetir el comportamiento del caso de uso extendido,
sólo lo que es diferente en el punto de extensión.

![Diagrama de casos de uso con relaciones de inclusión y
extensión](/diagrams/Use_Case_Diagram_Extends_Includes.svg)

*Figura 2: Un diagrama de casos de uso con relaciones de inclusión y extensión.*

Puedes ver más  información sobre diagramas de casos de uso con ejemplos
adicionales de las herramientas de modelado [Visual
Paradigm](https://www.visual-paradigm.com/guide/uml-unified-modeling-language/what-is-use-case-diagram/)
y [Lucidchart] (https://www.lucidchart.com/pages/uml-use-case-diagram).

[^1]: OMG. (2017). OMG® Unified Modeling Language®. Disponible
    [aquí](https://www.omg.org/spec/UML/2.5.1/PDF).