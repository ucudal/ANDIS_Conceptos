# 2 Técnicas y herramientas

## 2.7 Estilos de arquitectura

### 2.7.1 Estilo de arquitectura en capas, *layered architecture* o *n-tier architecture*

La arquitectura en capas es una forma de organizar los componentes de la
arquitectura en niveles o capas lógicas, cada una con roles bien definidos,
tales como presentación o lógica de negocio. Cada capa solo interactúa con la
capa inmediatamente inferior, lo que facilita la separación de cuestiones —o
*separation of concerns* en inglés—.

Este documento está basado en [^1].

La arquitectura en capas es un estilo de arquitectura monolítica.

El estilo de arquitectura en capas es uno de los estilos de arquitectura más
comunes. Es la elección predeterminada para muchas aplicaciones debido a su
simplicidad, familiaridad y bajo costo.

> [!NOTE]
> En esta plantilla no aparecen los componentes en cada capa por simplicidad; en
> un diagrama de arquitectura deberían aparecer, además de las capas, los
> componentes en ellas.

La [Figura 1](#figura-1), a continuación, combina las capas `Presentation
Layer`, `Business Layer`, `Persistence Layer` y `Database Layer` en una sola
unidad de despliegue; por ejemplo, una aplicación de escritorio con una base de
datos embebida o en memoria.

<span id="figura-1"/>

![Plantilla del estilo layered architecture desplegada en una sola
unidad de despliegue](/diagrams/Architecture_Layered.svg)

*Figura 1: Plantilla del estilo layered architecture desplegada en una sola unidad de despliegue.*

La [Figura 2](#figura-2), a continuación, muestra una variante de despliegue
donde la capa `Database Layer` está físicamente separada en una unidad de
despliegue diferente de la del resto de las capas; por ejemplo, una aplicación
de escritorio que usa un motor de base de datos local.

![Estilo layered architecture con la base de datos desplegada en una unidad de
despliegue físicamente separada del
resto](/diagrams/Architecture_Layered_Variation_1.svg)

<span id="figura-3"/>

*Figura 2: Estilo layered architecture con la base de datos desplegada en una
unidad físicamente separada del resto.*

La [Figura 3](#figura-3), a continuación, muestra otra variante de despliegue,
donde la capa `Presentation Layer` está físicamente separada del resto en una
unidad de despliegue diferente; también está separada del resto la capa
`Database Layer`; por ejemplo, una aplicación de escritorio implementada con un
cliente delgado, librerías, y un motor de base de datos local.

![Estilo layered architecture con la capa de presentación y la de base de datos
desplegadas en una unidad de despliegue físicamente separada del
resto](/diagrams/Architecture_Layered_Variation_2.svg)

*Figura 3: Estilo layered architecture con la capa de presentación y la de base
de datos desplegadas en una unidad de despliegue físicamente separada del
resto.*

La [Figura 4](#figura-4), a continuación, muestra una variante de la
arquitectura en capas donde:

* Las capas pueden ser abiertas o cerradas; si son abiertas las capas superiores
  pueden comunicarse directamente con las inferiores ‑"pasan" a través de la
  capa abierta‑, mientras que por el contrario, si son cerradas, las capas
  superiores se comunican solamente con la capa inmediata.
* Se agrega una capa `Services Layer` abierta que expone componentes
  compartidos para la capa `Business Layer` pero ocultos para la capa
  `Presentation Layer`.

<span id="figura-4"/>

![Estilo layered architecture con una capa `Service Layer` abierta y
cerradas](/diagrams/Architecture_Layered_Variation_3.svg)

*Figura 4: Estilo layered architecture con una capa `Service Layer` abierta y
las demás cerradas.*

[^1]: Richards, M. & Ford, N. (2020). Fundamentals of Software Architecture-An
      Engineering Approach. O'Reilly.
