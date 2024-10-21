# 2 Técnicas y herramientas

## 2.3 Modelos de estructura

### Diagramas de componentes UML

Los diagramas de componentes UML muestran la estructura del software, incluyendo
sus [componentes](/4_Conceptos/4_Componente.md) y las interfaces y dependencias
de éstos.

Este documento está basado en UML 2.5.1[^1].

[^1]: OMG. (2017). OMG® Unified Modeling Language®. Disponible
    [aquí](https://www.omg.org/spec/UML/2.5.1/PDF).

Los diagramas de componentes son distintos de los [diagramas de
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

* Paquetes, agrupan elementos del modelo, en este caso componentes, pero también
  otros paquetes.

* Artefactos, que se representan con un rectángulo con el estereotipo
  `≪artifact≫`, y son elementos del modelo que representan las entidades físicas
  en un sistema. Los artefactos representan unidades de implementación físicas,
  como archivos ejecutables, bibliotecas, componentes de software, documentos y
  bases de datos.

* Interfaces, que definen conjuntos de operaciones proporcionadas —en el caso de
  las interfaces provistas— o requeridas —en el caso de las consumidas—. Las
  interfaces provistas se representan con el símbolo de *lollipop* y las
  consumidas por el símbolo de medio círculo o con una flecha punteada, aunque
  también se pueden representar con un rectángulo con el estereotipo
  `≪interface≫`, pues también son clasificadores.

* Relaciones, una relación es una conexión entre elementos del modelo, en este
  caso, que un componente implementa una interfaz, o requiere una interfaz, o es
  parte de un paquete, o se implementa o despliega en una artefacto en
  particular.

<!-- TODO: Agregar diagrama de ejemplo -->

Puedes ver más información sobre diagramas de componentes en las herramientas de
modelado [IBM Software
Architect](https://www.ibm.com/docs/en/rational-soft-arch/9.7.0?topic=diagrams-creating-component),
y [Lucidchart](https://www.lucidchart.com/pages/uml-component-diagram).