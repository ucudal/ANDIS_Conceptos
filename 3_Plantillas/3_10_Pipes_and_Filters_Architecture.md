# Plantillas

## 3.10 Estilo de arquitectura tuberías y filtros

Esta es la plantilla para un estilo de arquitectura tuberías y filtros o *pipes
and filters*; este es un estilo de arquitectura monolítica.

Esta plantilla está basada en [^1].

Tiene entidades independientes llamadas filtros ‑*filters*‑ que realizan
transformaciones en los datos y procesan la entrada que reciben, y tuberías
‑*pipes*‑ que sirven como conectores para el flujo de datos que se está
transformando. Transforma datos, desde la entrada hasta la salida. Es deseable
crear estas partes como componentes independientes y reutilizables.

> [!NOTE]
> En esta plantilla aparecen componentes de ejemplo estereotipados; en
> un diagrama de arquitectura deberían aparecer los componentes propios del
> proyecto, usando estos mismos estereotipos.

La [Figura 1](#figura-1), a continuación, muestra un ejemplo de cada uno de los
cuatro tipos típicos de filtros, usando los estereotipos `≪producer≫`,
`≪transformer≫`, `≪tester≫` y `≪consumer≫` para identificarlos, con sus
respectivas tuberías conectando esos filtros.

<span id="figura-1"/>

![Estilo pipes and filters
architecture](/diagrams/Architecture_Pipes_And_Filters.svg)

*Figura 1: Estilo pipes and filters architecture.*

[^1]: Richards, M. & Ford, N. (2020). Fundamentals of Software Architecture-An
      Engineering Approach. O'Reilly.
