# 2 Técnicas y herramientas

## 2.2 Arquitectura

### 2.2.2 Modelo C4

El modelo C4 se creó como una forma de ayudar a los equipos de desarrollo de
software a describir y comunicar la arquitectura del software, tanto durante las
sesiones de diseño iniciales como cuando se documenta en forma retrospectiva una
base de código existente. Es una forma de crear mapas del código, con varios
niveles de detalle[^1].

C4 significa "contexto, contenedores, componentes y código" —o *context,
containers, components, and code— y hace referencia a los cuatro diagramas
utilizados para documentar una arquitectura con diferentes nivel de abstracción.

En este modelo, un `sistema de software` está formado por uno o más
`contenedores`[^2], cada uno de los cuales contiene uno o más `componentes`, que
a su vez son implementados por uno o más elementos de `código` —clases,
interfaces, objetos, funciones, etc.—; las `personas` pueden utilizar los
`sistemas de software` que construimos:

* **Sistema de software**. Es el nivel más alto de abstracción y describe algo
  que ofrece valor a sus usuarios, sean humanos o no. Esto incluye el sistema de
  software que están modelando y otros sistemas de software —[sistemas
  adyacentes](/4_Conceptos/4_Sistema_adyacente.md)— de los que éste depende —o
  viceversa—.

* **Contenedor**. Representa una aplicación o un almacenamiento de datos. Un
  contenedor es algo que debe estar ejecutándose para que funcione todo el
  sistema de software. Por ejemplo:

  * Una aplicación web del lado del servidor.
  * Una aplicación web del lado del cliente.
  * Una aplicación de escritorio del lado del cliente.
  * Una aplicación móvil.
  * Una aplicación de consola del lado del servidor.
  * Una función sin servidor —o *serverless function*—.
  * Una base de datos, relacional o no-relacional.
  * Un blob u otro almacenamiento de contenido.
  * Un sistema de archivos, local o de red —NAS—.
  * Un script de shell.
  * Etcétera.

* **Componente**. En este contexto un componente es conjunto de funcionalidades
  relacionadas encapsuladas detrás de una interfaz bien definida —una colección
  de clases de implementación detrás de una interfaz—. Todos los componentes
  dentro de un contenedor normalmente se ejecutan en el mismo espacio de
  proceso. En el modelo C4, los componentes no son unidades que se despliegan
  por separado.

Aunque los diagramas C4 tienen una notación específica, también es posible
utilizar UML. Estos son los diagramas en un modelo C4:

* **Contexto del sistema**. Incluye `personas` —por ejemplo, usuarios, actores,
  roles o personas— y `sistemas de software` —sistemas adyacentes— que están
  directamente conectados al sistema de software dentro del alcance. Es posible
  usar UML para estos diagramas: las personas estarán representadas por actores
  y los sistemas de software por componentes con el estereotipo `≪software
  system≫`.

* **Diagrama de contenedores**. El diagrama de contenedores muestra la forma de
  alto nivel de la arquitectura de software y cómo se distribuyen las
  responsabilidades en ella. También muestra las principales tecnologías y cómo
  los contenedores se comunican entre sí. Es un diagrama sencillo, centrado en
  la tecnología de alto nivel, que resulta útil tanto para los desarrolladores
  de software como para el personal de soporte y operaciones. Este diagrama se
  puede construir con UML: las personas estarán representadas por actores, los
  sistemas de software adyacentes como `≪software system≫`, y los contenedores
  por componentes con el estereotipo `≪container≫`, o los estereotipos más
  específicos `≪container database≫`, `≪container mobile app≫`, `≪container web
  browser≫`; las relaciones entre contenedores se representan como dependencias.

* **Diagrama de componentes**. El diagrama de componentes muestra cómo un
  contenedor se compone de una serie de componentes, cuáles son cada uno de esos
  componentes, sus responsabilidades y los detalles de tecnología
  e implementación. A diferencia de los diagramas anteriores, que son
  recomendados en todos los proyectos, los diagramas de componentes son
  opcionales. Es posible construir este diagrama con UML, con los mismos
  elementos y estereotipos de los diagramas de contenedores, más componentes con
  el estereotipo `≪component≫`, o con los estereotipos más específicos de la
  forma `≪component: 'type'≫` donde `'type'` describe el componente, por
  ejemplo, `MVC Rest Controller`, `Spring Bean`, etc.

* **Diagrama de código**. El diagrama de código muestra cómo los componentes se
  implementan en código. Es posible usar un [diagrama de clases
  UML](/2_Tecnicas_y_herramientas/2_3_1_Diagramas_de_clases_UML.md) para crear
  los diagramas de código. Estos diagramas también son opcionales.

<!-- TODO: Agregar ejemplos de cada uno de estos diagramas, tomados de
https://c4model.com -->

[^1]: Brown, S. (2024). The C4 model for visualizing software architecture-
     Context, Containers, Components, and Code. Disponible
     [aquí](https://c4model.com).

[^2]: No confundir con contenedores en el contexto de Docker.
