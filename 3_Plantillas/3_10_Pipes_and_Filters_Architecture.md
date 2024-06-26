# Plantillas

## 3.10 Arquitectura tuberías y filtros

Esta es la plantilla para una arquitectura tuberías y filtros o *pipes and
filters*; esta es una arquitectura monolítica.

Esta plantilla está basada en [^1].

> [!NOTE]
> En esta plantilla aparecen componentes de ejemplo estereotipados; en
> un diagrama de arquitectura deberían aparecer los componentes propios del
> proyecto, usando estos mismos estereotipos.

La figura 1, a continuación, muestra un ejemplo de cada uno de los cuatro tipos
típicos de filtros, usando los estereotipos `≪producer≫`, `≪transformer≫`,
`≪tester≫` y `≪consumer≫` para identificarlos, con sus respectivas tuberías
conectando esos filtros.

![Plantilla de la arquitectura pipes and
filters](/diagrams/Architecture_Pipes_And_Filters.svg)

*Figura 1: Plantilla de la arquitectura pipes and filters.*

[^1]: Richards, M. & Ford, N. (2020). Fundamentals of Software Architecture-An
      Engineering Approach. O'Reilly.
