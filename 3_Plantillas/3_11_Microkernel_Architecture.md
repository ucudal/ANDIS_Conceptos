# 3 Plantillas

## 3.11 Estilo de arquitectura micro-kernel

Esta es la plantilla para un estilo de arquitectura micronúcleo o *microkernel
architecture*; esta es un estilo de arquitectura monolítica.

Esta plantilla está basada en [^1].

Este estilo de arquitectura es adecuado para aplicaciones basadas en productos
‑empaquetadas y disponibles para su descarga e instalación como una única
implementación monolítica, generalmente instalada en el sitio del cliente‑.

> [!NOTE]
> En esta plantilla aparecen componentes de ejemplo estereotipados; en
> un diagrama de arquitectura deberían aparecer los componentes propios del
> proyecto, usando estos mismos estereotipos.

La [Figura 1](#figura-1), a continuación, muestra un ejemplo con el núcleo del
sistema con el estereotipo `≪core≫` y los complementos con el estereotipo
`≪plugin≫`.

<a id="figura-1"/>

![Estilo microkernel architecture](/diagrams/Architecture_Microkernel.svg)

*Figura 1: Estilo microkernel architecture.*

[^1]: Richards, M. & Ford, N. (2020). Fundamentals of Software Architecture-An
      Engineering Approach. O'Reilly.
