# 2 Técnicas y herramientas

## 2.9 Patrones de arquitectura

### MVC

El patrón MVC ‑por su sigla en inglés *Model-View-Controller* o
modelo-vista-controlador‑ es un patrón de arquitectura que separa la interacción
a través de la interfaz de usuario de una aplicación en tres roles
diferentes[^1] que se detallan más adelante.

[^1]: Fowler, M. (2002). Patterns of enterprise application architecture.
    Addison-Wesley Professional.

El origen del patrón se remonta al año 1970 en Smalltalk[^2]. Fue creado por
Trygve Reenskaug y puedes ver su versión inicial y posterior evolución aquí[^3].
Aunque hay muchas referencias en línea a MVC y sus variantes, este documento
está basado en [^1]; allí incluso se menciona que MVC es uno de los patrones más
citados pero también más mal citados en la vuelta.

[^2]: Smalltak-80 fue uno de los primeros y más influyentes lenguajes de
    programación orientada a objetos, que también incluía un entorno de
    desarrollo, una máquina virtual y una biblioteca de clases para desarrollo
    de aplicaciones de escritorio. Fue creado por Alan Key, Adele Goldberg y
    otros investigadores del Palo Alto Research Center de Xerox entre 1969 y
    1980.

[^3]: Trygve, M. (1978). MVC. Welcome to the pages of Trygve M. H. Reenskaug.
    Disponible
    [aquí](https://folk.universitetetioslo.no/trygver/themes/mvc/mvc-index.html).

#### Model

El `Model` es un objeto ‑o [componente](/4_Conceptos/4_Componente.md)‑ que
representa cierta información acerca del [dominio](/4_Conceptos/4_Dominio.md).
Es un objeto o componente no-visual que contiene todos los datos y
comportamiento excepto los usados por la interfaz de usuario. En su forma más
pura es un modelo de dominio tal como ha sido más recientemente utilizado en
Domain Driven Design[^4] aunque según [^1] podría ser implementado de otra forma
en la medida que no tenga elementos de interfaz de usuario.

[^4]: Evans, E. (2015). Domain-Driven Design Reference: Definitions and Pattern
    Summaries. Domain Language, Inc. Disponible
    [aquí](https://www.domainlanguage.com/wp-content/uploads/2016/05/DDD_Reference_2015-03.pdf).

#### View

 Las `View` representan la visualización de una parte de los datos del modelo en
 la interfaz de usuario. Pueden ser ventanas con componentes en una aplicación
 de escritorio o páginas HTML en una aplicación web. Las `View` solo muestran
 información; cualquier cambio en los datos o cualquier interacción con la
 aplicación es manejada por el tercer componente de la terna: el `Controller`.

#### Controller

Los `Controller` ‑suele haber uno para cada `View`‑ toman la entrada
del usuario, manipulan el modelo, y logran que la vista se actualice según
corresponda. De esta forma la interfaz de usuario es una combinación de las
vistas y los controladores.

La [Figura 1](#figura-1) a continuación muestra las dependencias entre los tres
elementos descritos:

<span id="figura-1"/>

![Estructura y dependencias en MVC](/diagrams/MVC.svg)

*Figura 1: Estructura y dependencias en MVC*. Tomado de [^1].

#### Cómo funciona

MVC separa dos cosas. Por un lado, separa la presentación del modelo, y por
otro, separa el controlador de la vista.

La separación de la presentación del modelo está basada esencialmente en el
[principio de responsabilidad
única](https://blog.cleancoder.com/uncle-bob/2014/05/08/SingleReponsibilityPrinciple.html).

Esta separación permite, entre otras cosas, tener representaciones diferentes
de los mismos datos, según el contexto. Por ejemplo, una representación podría
ser mediante una página web y otra mediante una API
[REST](/4_Conceptos/4_REST.md); o incluso una página web podría ser la versión
de escritorio y otra la versión para dispositivos móviles.

Por último, el modelo no-visual es más fácil de probar mediante pruebas de
unidad que la vista a través de pruebas automatizadas de la interfaz de usuario.

La otra separación entre la vista y el controlador, aunque también está basada
en el principio de responsabilidad única, es menos importante. Algunos
*frameworks* de interfaz de usuario, incluyendo el mencionado Smalltalk,
implementan la vista y el controlador juntos; aunque la mayoría de los
*frameworks* para aplicaciones web efectivamente implementan la vista y el
controlador por separado[^1].

#### Page Controller

El `Page Controller` es un objeto que maneja una solicitud para una página web o
para una acción específica en un sitio web. Es una variante de MVC para
aplicaciones web donde hay un archivo para procesar cada solicitud recibida por
el sitio web.

<span id="figura-2"/>

![Estructura y dependencias en Page Controller](/diagrams/MVC_Page_Controller.svg)

*Figura 2: Estructura y dependencias en Page Controller*. Tomado de [^1].

Las responsabilidades se distribuyen así:

* `Page Controller`

  * Manejar los pedidos HTTP GET y HTTP POST

  * Decidir qué modelo ‑o parte del modelo‑

  * Decidir qué vista usar

* `Model`

  * Conocer y manejar los datos y la lógica del dominio

* `View`

  * Mostrar la página HTML

La idea es tener un `Page Controller` para cada página de un sitio web; o de
forma más genérica, como las páginas pueden ser dinámicas, un `Page Controller`
por cada acción tal como un vínculo o un botón. El `Page Controller` puede ser
implementado como un *script*
‑[CGI](https://datatracker.ietf.org/doc/html/rfc3875),
[*serverlet*](https://jcp.org/en/jsr/detail?id=340), etc.‑ o como una página de
servidor ‑[ASP](https://learn.microsoft.com/en-us/aspnet/overview),
[PHP](https://www.php.net/manual/es/intro-whatis.php),
[JSP](https://projects.eclipse.org/projects/ee4j.jsp), etc.‑. En este caso se
suele implementar la `View` mediante [Template
View](https://java-design-patterns.com/patterns/templateview/).

Este diseño funciona bien para páginas simples; cuando la lógica es compleja el
`Page Controller` puede quedar demasiado complejo también. En ese caso todavía
es posible usarlo, moviendo la lógica compleja a un objeto `Helper`.

> [!TIP]
> Mira también [Page Controller Pattern in Java: Centralizing Web Page Logic for
> Cleaner Design](https://java-design-patterns.com/patterns/page-controller/)

#### Front Controller

En una aplicación web compleja, en cada solicitud son necesarios comportamientos
similares como autenticación, autorización, localización, etc. Cuando hay un
controlador para cada solicitud ‑como en el caso anterior‑ esta lógica puede
llegar a quedar repetida. `Front Controller` consolida toda la gestión de una
solicitud en un solo objeto ‑o componente‑, que puede ser modificado a través de
[decoradores](https://refactoring.guru/design-patterns/decorator). Este objeto
luego delega el procesamiento de la solicitud a
[comandos](https://refactoring.guru/design-patterns/command) apropiados.

<span id="figura-3"/>

![Estructura y dependencias en Front Controller](/diagrams/MVC_Front_Controller.svg)

*Figura 3: Estructura y dependencias en Front Controller*. Tomado de [^1].

> [!TIP]
> Mira también [Front Controller Pattern in Java: Centralizing Web Request
> Handling](https://java-design-patterns.com/patterns/front-controller/)
