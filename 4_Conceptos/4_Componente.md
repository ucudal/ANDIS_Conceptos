# Conceptos

## Componentes

Existen varias definiciones de **componente** en arquitectura de software y
todas ellas son relativamente consistentes en que los componentes son unidades
modulares con interfaces bien definidas, que encapsulan funciones específicas y
pueden interactuar con otros componentes, permitiendo la reutilización y la
independencia en la construcción y el despliegue.

### Definiciones

**Richards**

Un **componente** es la manifestación física de un módulo, el empaquetado físico
de un módulo, como los `.jar` en Java, `.dll` en .NET, `.gem` en Ruby, etc. Un
**módulo** es una agrupación lógica de código relacionado[^1].

[^1]: Richards, M.; Ford, N. (2020). Fundamentals of software architecture.
    O'Reilly Media.

**Bass, Clements, Kazman**

Un **componente** es un módulo de software que tiene una interfaz claramente
definida, que interactúa con otros componentes a través de conexiones
explícitas, y que encapsula un comportamiento bien especificado y controlado.
Los componentes pueden ser reutilizados y, en muchos casos, desplegados de
manera independiente[^2].

[^2]: Bass, L.; Clements, P.; Kazman, R. (2022). Software Architecture in
    Practice, 4<sup>th</sup> Edition. Addison-Wesley Professional.

**ISO/IEC/IEEE 42010**

Un **componente** es una parte de un sistema que interactúa con otras partes a
través de interfaces. Es la unidad que implementa una función específica dentro
de un sistema más grande[^3].

[^3]: IEEE. (2O22). ISO/IEC/IEEE 42010:2022 Software, systems and enterprise —
    Architecture description. ISO.

**Rozanski & Woods**

Un **componente** es una unidad de software que encapsula una funcionalidad y
que puede ser reemplazada, reutilizada o modificada independientemente dentro de
un sistema. Los componentes interactúan a través de interfaces bien
definidas[^4].

[^4]: Rozanski, N; Woods, E. (2012). Software Systems Architecture: Working with
    Stakeholders Using Viewpoints and Perspectives, 2<sup>nd</sup> Edition.
    Addison-Wesley

**Fielding**

En el contexto de arquitecturas REST, un **componente** es una
unidad abstracta que interactúa con otros componentes a través de una interfaz
uniforme, facilitando la comunicación y la reutilización de comportamientos[^5].

[^5]: Fielding, R.T. (2000). Architectural Styles and the Design of
Network-based Software Architectures. University of California, Irvine.
Disponible [aquí](https://ics.uci.edu/~fielding/pubs/dissertation/top.htm).

### Alcance de los componentes

Los componentes pueden ser definidos en múltiples factores, algunos de los
cuales aparecen a continuación[^1]:

* El componente envuelve el código a un nivel superior de
  [modularidad](/4_Conceptos/4_Modularidad.md) que las clases en los lenguajes
  de programación orientada a objetos o las funciones y procedimientos en otros
  lenguajes.

  Habitualmente nos referimos a este envoltorio como biblioteca o *library* y
  los diferentes elementos del código que contiene se ejecutan en el mismo
  espacio de memoria y se comunican mediante llamados a funciones del lenguaje.

* Un componente agrupa el código de cada una de las capas de una [layered
  architecture](/2_Tecnicas_y_herramientas/2_7_1_Layered_architecture.md), de
  cada una de los filtros en una [pipes and filter
  architecture](/2_Tecnicas_y_herramientas/2_7_2_Pipes_and_Filters_Architecture.md),
  o como el núcleo y cada uno de los complementos en una [microkernel
  architecture](/2_Tecnicas_y_herramientas/2_7_3_Microkernel_Architecture).

* Un componente también puede ser un servicio en una [service based
  architecture](/2_Tecnicas_y_herramientas/2_7_4_Service_Based_Architecture), un
  micro—servicio en una [microservices
  architecture](/2_Tecnicas_y_herramientas/2_7_8_Microservices_Architecture.md),
  o en cualquier otro arquitectura distribuida.

  En este caso cada componente ejecuta habitualmente en su propio espacio de
  memoria y se comunica con los demás componentes mediante protocolos de red de
  bajo nivel como TCP/IP o mediante mensajes de más alto nivel como llamados
  REST o colas de mensajes, por ejemplo.

### Componentes y su relación con la arquitectura y el rol de arquitecto

Los componentes forman el bloque de construcción modular fundamental en la
arquitectura, por eso es importante identificar correctamente los componentes de
una arquitectura. De hecho, una de las decisiones principales que debe tomar
un arquitecto se refiere a la partición de alto nivel de los componentes en la
arquitectura[^1].

Habitualmente el componente es el nivel más bajo con el que interactúa
directamente un arquitecto —exceptuando tal vez métricas que afectan [atributos
de calidad](/4_Conceptos/4_Atributos_de_calidad.md) en las bases del código. Las
clases o funciones y procedimientos dentro de un componente son responsabilidad
de los desarrolladores[^1].

### Partición de la arquitectura en componentes

En la medida de que los componentes representan un mecanismo genérico para
contener código, el código se puede particionar en componentes de distintas
maneras, cada una de ellas con diferentes compromisos en la satisfacción de los
[atributos de calidad](./4_Atributos_de_calidad.md) de la arquitectura de
software resultante. Sin embargo, el reparto de componentes de alto nivel merece
un tratamiento especial, pues condiciona más que los demás la arquitectura del
software.

Existen dos grandes formas de comenzar a particionar los componentes en una
arquitectura de software:

* Partición técnica: El criterio para particionar los componentes de alto nivel
  está basado en capacidades técnicas y es independiente del domino del
  problema. Un ejemplo típico es cuando los componentes de alto nivel
  corresponden a las capas de presentación, lógica de negocio, servicios y
  persistencia, por ejemplo; de hecho, esta es la partición predeterminada en
  diferentes organizaciones, frameworks, etc.

  ![Partición técnica](/diagrams/Components_Technical_Partitioning.svg)

  #### *Figura 1: Partición técnica*

* Partición por el dominio: El criterio para repartir los componentes de alto
  nivel está inspirado en la metodología de Domain Driven Design de Eric Evans,
  donde el criterio para particionar los componentes está basado en dominios o
  flujos del trabajo, en lugar de capacidades técnicas.

  ![Partición por el dominio](/diagrams/Components_Domain_Partitioining.svg)

  #### *Figura 2: Partición por el dominio*

<!-- TODO: Cambiar todos a este nuevo estilo y aclararlo en el CONTRIBUTING.md -->

Como los componentes pueden estar a su vez compuestos por componentes, los
componentes correspondientes a los dominios en la [Figura
2](#figura-2-reparto-por-el-dominio) pueden estar implementados internamente con
los componentes de la [Figura 1](#figura-1-reparto-técnico) —pero no al revés—.

La partición por el domino es la apropiada para un estilo de arquitectura de
[microservicios](/2_Tecnicas_y_herramientas/2_7_8_Microservices_Architecture.md);
cada componente será un micro-servicio, aunque en ese caso, a diferencia de la
[Figura 2](#figura-2-reparto-por-el-dominio), cada micro-servicio tiene su
propia base de datos.

En el caso de la partición técnica, la implementación de una funcionalidad
típica de los sitios de comercio electrónico como es el carrito de compras, por
ejemplo, aparece en todos los componentes; mientras que en la partición por el
dominio queda contenida por completo en el componente `Catalog Checkout`, tal
como se muestra en la siguiente [Figura
3](/diagrams/Components_Domain_vs_Technical_Partitioining.svg).

![Reparto por el domino vs reparto
técnico](/diagrams/Components_Domain_vs_Technical_Partitioining.svg)

#### Figura 3: Funcionalidad en reparto por el dominio versus en reparto técnico

A continuación aparece un resumen de las ventajas y desventajas de ambos
enfoques para definir las particiones de alto nivel[^1]:

#### Partición de dominio

Las arquitecturas particionadas de dominio separan los componentes de nivel
superior por flujos de trabajo y/o dominios.

Ventajas:

* El modelado es más cercano a cómo funciona el negocio en lugar de un detalle de
  implementación
* Es más fácil armar equipos multidisciplinarios alrededor de los dominios.
* Está más alineada con los estilos de arquitectura monolítica modular y de
  microservicios.
* El flujo de mensajes coincide con el dominio del problema.
* Es fácil de migrar datos y componentes a la arquitectura distribuida

Desventajas:

* El código de personalización aparece en múltiples lugares.

#### Partición técnica

Las arquitecturas particionadas técnicamente separan los componentes de nivel
superior según las capacidades técnicas en lugar de flujos de trabajo discretos.
Esto puede manifestarse como capas inspiradas en la separación
MVC o alguna otra partición técnica ad hoc.

Ventajas:

* Separa claramente el código de personalización.

* Está más alineada con el estilo de arquitectura en capas.

Desventajas:

* Mayor grado de acoplamiento global.

* Los cambios en un componente pueden afectar a todos los demás componentes que
  dependen del él.

* Los desarrolladores pueden tener que duplicar conceptos de dominio —por
  ejemplo, validación de reglas del negocio— en diferentes componentes.

* Habitualmente el acoplamiento es mayor en el nivel de datos. Los arquitectos
  de aplicaciones y datos probablemente colaborarían para crear una única base
  de datos. Eso, a su vez, genera dificultades para aislar las relaciones de
  datos si los arquitectos luego quieren migrar esta arquitectura a un sistema
  distribuido.

Ninguna de las alternativas es mejor que la otra, aunque la elección inicial
tiene consecuencias: por ejemplo, si es necesario tener componentes redundantes
para alcanzar atributos de calidad tales como
[disponibilidad](./4_Disponibilidad.md) o [rendimiento](./4_Rendimiento.md) de
ciertas funcionalidades o flujos de trabajo —como el carrito de compras en las
fiestas—, es más fácil lograrlo con la partición por dominio —asumiendo que esas
funcionalidades o flujos de trabajo están contenidas en un componente—, pero no
así con la partición técnica.

### Flujo de identificación de componentes

Una forma iterativa de identificar los componentes de la arquitectura de
software es el [Ciclo de identificación de/2_Tecnicas_y_herramientas/2_2_2_Ciclo_identificacion_componentes.md
componentes](/2_Tecnicas_y_herramientas/2_2_3_Ciclo_identificacion_componentes.md)
definido en [^1].
