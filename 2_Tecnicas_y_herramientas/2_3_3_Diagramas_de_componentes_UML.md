# 2 Técnicas y herramientas

## 2.3 Modelos de estructura

### Diagramas de componentes UML

Los diagramas de componentes UML muestran la estructura del software, incluyendo
sus [componentes](/4_Conceptos/4_Componente.md) y las interfaces y dependencias
de éstos.

Este documento está basado en UML 2.5.1[^1].

[^1]: OMG. (2017). OMG® Unified Modeling Language®. Disponible
    [aquí](https://www.omg.org/spec/UML/2.5.1/PDF).

Los diagramas de componentes son distintos de los [diagramas de2_3_4_Diagramas_de_despliegue_UML.md
despliegue](./2_3_4_Diagramas_de_despliegue_UML.md). Un diagrama de componentes
define la composición de los componentes y artefactos en el sistema. Un diagrama
de despliegue muestra los componentes y artefactos en relación con el lugar
donde se utilizan en el sistema implementado.

Los diagramas de componentes tienen principalmente:

* Componentes, que se representan con un rectángulo —pues son
  [clasificadores](/4_Conceptos/4_Clasificador.md)— con un ícono de componente
  dentro o con el estereotipo `≪component≫`, y son elementos del modelo que
  representan partes independientes e intercambiables de un sistema. Un
  componente proporciona comportamiento a través de interfaces provistas y
  consume comportamiento a través de interfaces requeridas.

  ![Componente](/diagrams/Component_Diagram_Component.svg)

* Paquetes, agrupan elementos del modelo, en este caso componentes, pero también
  otros paquetes.

  ![Paquete](/diagrams/Component_Diagram_Package.svg)

* Artefactos, que se representan con un rectángulo con el estereotipo
  `≪artifact≫`, y son elementos del modelo que representan las entidades físicas
  en un sistema. Los artefactos representan unidades de implementación físicas,
  como archivos ejecutables, bibliotecas, componentes de software, documentos y
  bases de datos.

  ![Artefacto](/diagrams/Component_Diagram_Artifact.svg)

* Interfaces, que definen conjuntos de operaciones proporcionadas —en el caso de
  las interfaces provistas— o requeridas —en el caso de las consumidas—. Las
  interfaces provistas se representan con el símbolo de *lollipop* y las
  consumidas por el símbolo de medio círculo o con una flecha punteada, aunque
  también se pueden representar con un rectángulo con el estereotipo
  `≪interface≫`, pues también son clasificadores.

  ![Interfaz](/diagrams/Component_Diagram_Interfaces.svg)

* Relaciones, una relación es una conexión entre elementos del modelo, en este
  caso, que un componente implementa una interfaz, o requiere una interfaz, o es
  parte de un paquete, o se implementa o despliega en una artefacto en
  particular.

<!-- TODO: Agregar diagrama de ejemplo -->

En la [Figura 1](#figura-1), a continuación, aparece un ejemplo de un diagrama
de componentes. En el ejemplo aparecen tres subsistemas —componentes con el
estereotipo `≪subsystem≫`—: `WebStore`, `Warehouses` y `Accounting`. El
subsistema `WebStore` provee o expone las interfaces `ProductSearch`,
`OnlineShopping` y `UserSession` a través de los puertos que aparecen a la
izquierda. A su vez requiere de las interfaces `SearchInventory`, `ManageOrders`
y `ManageCustomers` a través de los puertos que aparecen a la derecha. La
estructura interna de `WebStore` muestra el componente de tipo `SearchEngine`
que provee la interfaz `ProductSearch`, a la que el subsistema `WebStore` delega
la interfaz del mismo nombre. Algo similar ocurre con los componentes de tipo
`ShoppingCart` y `Authentication` que proveen las interfaces `OnlineShopping` y
`UserSession` en las que el subsistema `WebStore` delega sus interfaces del
mismo nombre. En forma análoga los componentes de tipo `SearchEngine`,
`ShoppingCart` y `Authentication` requieren de las interfaces `SearchInventory`,
`ManageOrders` y `ManageCustomers` respectivamente, a través de la delegación de
las interfaces requeridas por `WebStore` con mismo nombre.

Entre la interfaz `SearchInventory` requerida por `WebStore` y provista por
`Warehouses` hay una dependencia; también hay una dependencia entre las
interfaces `ManageOrders` y `ManageCustomers` requeridas y provistas por
`WebStore` y `Accounting` respectivamente. También hay otra dependencia en la
interfaz `ManageInventory` requerida por `Accounting` y provista por
`Warehouses`.

<a id="figura-1"/>

![Ejemplo de diagrama de componentes](/diagrams/Component_Diagram_Example.svg)

*Figura 1: Ejemplo de diagrama de componentes*.


Puedes ver más ejemplos de [diagramas de componentes en UML Diagrams](https://www.uml-diagrams.org/component-diagrams.html).

Puedes ver más información sobre diagramas de componentes en las herramientas de
modelado [IBM Software
Architect](https://www.ibm.com/docs/en/rational-soft-arch/9.7.0?topic=diagrams-creating-component),
y [Lucidchart](https://www.lucidchart.com/pages/uml-component-diagram).
