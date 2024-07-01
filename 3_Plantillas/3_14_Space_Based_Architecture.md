# 3 Plantillas

## 3.14 Estilo de arquitectura basada en espacios

Esta es la plantilla para un estilo de arquitectura basada en espacios o
*space-based architecture*; este es un estilo de arquitectura distribuida.

Esta plantilla está basada en [^1].

Con este estilo de arquitectura se logra alta escalabilidad, elasticidad y
rendimiento al eliminar la base de datos central como limitación sincrónica en
el sistema. En su lugar, se utilizan redes replicadas de datos en memoria. Los
datos de la aplicación se mantienen en memoria y se replican entre las unidades
de procesamiento activas.

Las actualizaciones de datos se envían de manera asíncrona a la base de datos a
través de colas persistentes. Las unidades de procesamiento se inician y
detienen según la carga del usuario, logrando una escalabilidad variable.

Al no depender de una base de datos central en el procesamiento transaccional
estándar, se elimina el cuello de botella de la base de datos, permitiendo una
escalabilidad casi infinita en la aplicación.

> [!NOTE]
> En esta plantilla aparecen componentes de ejemplo estereotipados; en
> un diagrama de arquitectura deberían aparecer los componentes propios del
> proyecto, usando estos mismos estereotipos.

En la figura 1, a continuación, aparecen los siguientes elementos:

* `Processing Units` son nodos que tienen la lógica de la aplicación que en la
  plantilla se muestra como el componente `Application Logic` estereotipado como
  `≪service≫`; además de la lógica de la aplicación estos nodos contienen datos
  en memoria en el componente `In Memory Data Grid` estereotipado como `≪cache≫`
  y un motor de replicación de datos `Data Replication Engine` estereotipado
  como `≪engine≫`. Estos nodos pueden ser iniciados a demanda para escalar la
  aplicación.

* `Virtualized Middleware` es el nodo que alberga la infraestructura que
  controla varios aspectos de esta arquitectura: el componente `Messaging Grid`
  estereotipado como `≪proxy≫` recibe los eventos y los direcciona al nodo de
  procesamiento adecuado; además maneja la sesión. El componente `Data Grid`
  estereotipado como `≪cache≫` se encarga de sincronizar los componentes `In
  Memory Data Grid` de los nodos de procesamiento, en caso de que esos caché no
  se sincronicen entre sí —por eso es opcional—. El componente `Processing Grid`
  estereotipado como `≪orchestrator≫` es encargado de orquestar el procesamiento
  de eventos entre varios nodos de procesamiento si fuera necesario —por eso es
  opcional—. El componente `Deployment Manager` estereotipado como `≪agent≫`
  monitorea los nodos de procesamiento e inicia —o detiene— instancias de estos
  nodos si fuera necesario.

* El componente `Write Data Pump` es una cola —por eso está estereotipado con
  `≪queue≫`— utilizada como buffer para enviar pedidos de escritura al
  componente `Data Writer`; este último es el encargado de escribir realmente en
  la base de datos.

* El componente `Read Request` es también una cola —por eso también está
  estereotipado con `≪queue≫`— utilizada como buffer para recibir pedidos de
  lectura consumidos por el componente `Data Reader`; este último es el
  encargado de leer desde la base de datos y poner el resultado en otra cola
  `Reverse Data Pump`.

![Estilo space-based architecture](/diagrams/Architecture_Space_Based.svg)

*Figura 1: Estilo space-based architecture.*

<!-- TODO: Agregar las variantes y ejemplos que aparecen en la referencia abajo -->

[^1]: Richards, M. & Ford, N. (2020). Fundamentals of Software Architecture-An
      Engineering Approach. O'Reilly.
