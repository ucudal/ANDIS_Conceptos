# 3 Plantillas

## 3.13 Arquitectura dirigida por eventos

Esta es la plantilla para una arquitectura dirigida por eventos o *event-driven
architecture*; esta es una arquitectura distribuida.

Esta plantilla está basada en [^1].

El estilo de arquitectura orientada a eventos es ampliamente utilizado para
crear aplicaciones altamente escalables y de alto rendimiento. Se basa en
componentes de procesamiento de eventos que operan de manera independiente y
procesan eventos de forma asíncrona.

> [!NOTE]
> En esta plantilla aparecen componentes de ejemplo estereotipados; en
> un diagrama de arquitectura deberían aparecer los componentes propios del
> proyecto, usando estos mismos estereotipos.

La figura 1, a continuación, muestra un ejemplo con el orquestador que recibe
los eventos con el estereotipo `≪orchestrator≫` y varios procesadores de eventos
con el estereotipo `≪processor≫`.

![Plantilla de event-driven
architecture](/diagrams/Architecture_Event_Driven.svg)

*Figura 1: Plantilla de event-driven architecture.*

<!-- TODO: Agregar las variantes y ejemplos que aparecen en la referencia abajo -->

[^1]: Richards, M. & Ford, N. (2020). Fundamentals of Software Architecture-An
      Engineering Approach. O'Reilly.
