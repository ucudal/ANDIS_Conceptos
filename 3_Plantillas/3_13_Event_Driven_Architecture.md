# 3 Plantillas

## 3.13 Estilo de arquitectura dirigida por eventos

Esta es la plantilla para un estilo de arquitectura dirigida por eventos o
*event-driven architecture*; este es un estilo de arquitectura distribuida.

Esta plantilla está basada en [^1].

El estilo de arquitectura dirigida por eventos es ampliamente utilizado para
crear aplicaciones altamente escalables y de alto rendimiento. Se basa en
componentes de procesamiento de eventos que operan de manera independiente y
procesan eventos de forma asíncrona.

> [!NOTE]
> En esta plantilla aparecen componentes de ejemplo estereotipados; en
> un diagrama de arquitectura deberían aparecer los componentes propios del
> proyecto, usando estos mismos estereotipos.

La [Figura 1](#figura-1), a continuación, muestra un ejemplo con el orquestador
que recibe los eventos con el estereotipo `≪orchestrator≫` y varios procesadores
de eventos con el estereotipo `≪processor≫`.

<span id="figura-1"/>

![Estilo event-driven architecture](/diagrams/Architecture_Event_Driven.svg)

*Figura 1: Estilo event-driven architecture.*

<!-- TODO: Agregar las variantes y ejemplos que aparecen en la referencia abajo -->

[^1]: Richards, M. & Ford, N. (2020). Fundamentals of Software Architecture-An
      Engineering Approach. O'Reilly.
