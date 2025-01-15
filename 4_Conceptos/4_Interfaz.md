# 4 Conceptos

## Interfaz

Las interfaces son un mecanismo de abstracción fundamental necesario para
conectar [componentes](./4_Componente.md) en una arquitectura de software.

Las definiciones y conceptos en este documento están tomados de [^1] a menos que
se indique lo contrario.

[^1]: Bass, L.; Clements, P.; Kazman, R. (2022). Software Architecture in
    Practice, 4<sup>th</sup> edition. Addison-Wesley.

### Términos relacionados

En este documento usaremos los siguientes términos relacionados con las
interfaces:

* **Clientes**. Son los demás componentes, usuarios o sistemas con los que
  interactúa un componente.

* **Entorno** o —*environment*—. Es el conjunto de clientes con los que
  interactúa un componente.

* **Interacciones**. Son las transferencias de control —*calls*— o de
  datos entre componentes. Ver más información [aquí](./4_Interaccion.md).

* **Recursos**. Son las construcciones que proveen puntos de interacción directa
  con un componente. Ver más información [aquí](./4_Recurso.md).

Lo anterior tiene algunas implicaciones clave:

* Todos los componentes tienen interfaces; de lo contrario, ¿cuál es el
  propósito del componente?

* Las interfaces no son sólo lo que un componente provee, sino también lo que
  consume; pues si por ejemplo lo que consume no está disponible, no provee lo
  que se espera.

* Un componente puede interactuar con varios clientes a través de la misma
  interfaz al mismo tiempo.

### Conceptos fundamentales

* **Múltiples interfaces**. Es posible separar una interfaz en múltiples
  interfaces. Aunque el concepto es de programación orientada a objetos, el
  fundamento es el [principio de segregación de
  interfaces](https://web.archive.org/web/20150906155800/http:/www.objectmentor.com/resources/articles/Principles_and_Patterns.pdf)
  enunciado por Robert C. Martin. De esta forma es posible, por ejemplo, proveer
  multiples interfaces al mismo recurso requiriendo cada una diferentes niveles
  de acceso.

* **Sintaxis del recurso**. Es la firma del recurso tal que permite escribir
  el código del componente que usa el recurso de forma tal que la sintaxis sea
  correcta. Incluye el nombre del recurso, nombre y tipo de los argumentos, tipo
  del resultado, etc.

* **Semántica del recurso**. Es el resultado de invocar el recurso. Incluye lo
  siguiente:

  * Asignación de valores a los datos a los que puede acceder el cliente que
    invoca el recurso; puede ser tan simple como obtener un valor o tan complejo
    como una transacción en una base de datos.

  * Asunciones acerca de los valores que pasan a través de la interfaz.

  * Cambios en el estado del componente resultantes de usar el recurso,
    incluyendo además estados excepcionales.

  * Eventos que se señalarán o mensajes que se enviarán como resultado del uso
    del recurso.

  * Cómo otros recursos se comportarán de manera diferente en el futuro como
    resultado del uso de un recurso. Por ejemplo, si se destruye un objeto,
    tratar de accederlo en el futuro podría producir un error.

  * Resultados observables por las personas, si los hubiera. Por ejemplo, en
    sistemas embebidos. , la semántica debería indicar si la ejecución del
    recurso es atómica o si se puede suspender y retomar más tarde.

* **Operaciones**. Las operaciones se invocan para transferir el control o datos
  a un componente para su procesamiento y son parte de la interfaz. La mayoría
  de las operaciones también devuelven un resultado. Como las operaciones pueden
  fallar, la interfaz debe dejar claro cómo hacen los clientes para detectar
  errores —ya sea como parte del resultado, o a través de un mecanismo que
  permita a los cliente consultar el estado de la última operación—.

* **Eventos**. Los eventos normalmente son asíncronos y representan la recepción
  de un mensaje; también son parte de la interfaz. Los elementos activos,
  aquellos que no esperan pasivamente a ser invocados por otros elementos,
  producen eventos salientes que se utilizan para notificar a los observadores,
  *listeners*, o suscriptores sobre cosas interesantes que suceden dentro del
  componente.

* **Metadata**. Además de los datos transferidos vía operaciones y eventos, otro
  aspecto importante de las interfaces es la metadata: permisos de acceso,
  unidades de los parámetros o resultados, formatos —por ejemplo, el punto en
  los decimales—. A esta metadata se le llama también **propiedades**.

* **Evolución de las interfaces**. El componente que está implementando una
  interfaz debería poder evolucionar sin afectar a los demás componentes que
  utilizan esta interfaz para consumir el componente, siempre y cuando la
  interfaz en sí no cambie.

  En algunas situaciones puede llegar a ser necesario cambiar también la
  interfaz. En esos casos es posible usar alguna de las siguientes técnicas:

  * **Deprecación**. Es eliminar la interfaz. Una buena práctica es avisar con
    antelación que una interfaz va a ser deprecada a partir de cierto momento.
    Otra es introducir un código de error que indique que la interfaz va a ser
    deprecada —y cuándo— o que indique que la interfaz ya ha sido deprecada.

  * **Versionado**. Es posible soportar la evolución de una interfaz
    introduciendo una nueva versión manteniendo la anterior. La anterior puede
    ser deprecada luego de cierto tiempo. Esto puede implicar que el actor deba
    indicar qué versión de la interfaz quiere utilizar. También puede implicar
    mantener en simultáneo varias versiones del componente o introducir un
    [adaptador](https://refactoring.guru/design-patterns/adapter) o un
    [mediador](https://refactoring.guru/design-patterns/mediator) para que la
    vieja interfaz pueda permitir el acceso a  un nuevo componente.

  * **Extensión**. Es dejar la interfaz original sin cambios pero agregar nuevos
    recursos con los cambios deseados. En caso de que eso implique
    incompatibilidades con algunos actores, al igual que en el caso anterior,
    puede ser necesario introducir un
    [adaptador](https://refactoring.guru/design-patterns/adapter) o un
    [mediador](https://refactoring.guru/design-patterns/mediator).

### Diseño de una interfaz

Añadir recursos a una interfaz implica un compromiso de mantener esos recursos
como parte de la interfaz mientras el componente esté en uso. La arquitectura
se ve afectada cuando se rompe el contrato de interfaz entre componentes.

Algunos principios para el diseño de interfaces son:

* **Principio de la mínima sorpresa**. Las interfaces deben comportarse de
  manera consistente con las expectativas del actor. Los nombres juegan un
  papel aquí: un recurso con un nombre apropiado les da a los actores una
  buena pista sobre para qué se puede usar el recurso.

* **Principio de interfaces pequeñas**. Cuando dos elementos necesitan
  interactuar, que intercambien la menor cantidad de información posible.

* **Principio de acceso uniforme**. Evitar filtrar detalles de implementación
  a través de la interfaz. Un recurso debe ser accesible para sus actores de
  la misma manera independientemente de cómo se implemente. Un actor no debe
  saber —por ejemplo— si un valor se devuelve desde un caché, desde un cálculo
  o desde una nueva búsqueda del valor desde alguna fuente externa.

* **Principio DRY —*don't repeat yourself*— o principio de no repetirse**. Las
  interfaces deben ofrecer un conjunto de primitivas que se puedan componer en
  lugar de muchas formas diferentes de lograr el mismo objetivo.

La consistencia es un aspecto clave para diseñar interfaces limpias. Algunos
aspectos a tener en cuenta incluyen cómo se asignan nombres a los recursos, cómo
se ordenan los parámetros, o como se notifican los errores.

Para que una interacción con una interfaz sea exitosa es necesario llegar a un
acuerdo sobre los siguientes aspectos:

* **Alcance de la interfaz**. El alcance de una interfaz define el conjunto de
  recursos directamente disponibles para los actores. Todos los actores podrían
  acceder a todos los recursos, o ciertos actores podrían acceder a ciertos
  recursos y no a otros, por cuestiones de seguridad, desempeño o facilidad de
  modificación.

  Un patrón común para limitar y mediar el acceso a los recursos de un
  componente —o un grupo de componentes— es establecer un *gateway* o puerta de
  enlace. Una puerta de enlace traduce las solicitudes de los actores en
  solicitudes a los recursos del componente —o componente— de destino, que de
  esta forma se convierte en un actor para el elemento —o elementos— de destino.
  Las puertas de enlace son útiles por las siguientes razones:

  * La granularidad de los recursos proporcionados por un componente puede ser
    diferente a la que necesita un actor.

  * Una puerta de enlace puede traducir entre elementos y actores.

  * Los actores pueden necesitar acceso a subconjuntos específicos de los
    recursos o estar restringidos a ellos.

  * Los detalles de los recursos pueden cambiar con el tiempo y la puerta de
    enlace puede proporcionar una interfaz más estable.

* **Estilo de interacción**. Las interfaces están pensadas para estar conectadas
  entre sí de modo que los diferentes elementos puedan comunicarse —transferir
  datos— y coordinarse —transferir control—. Hay muchas formas en que se
  producen esas interacciones, dependiendo de la combinación entre
  comunicación y coordinación y de si los elementos estarán ubicados en el
  mismo lugar —co-ubicados— o se implementarán de forma remota.

  * Las interfaces de componentes co-ubicados pueden proporcionar acceso
    eficiente a grandes cantidades de datos a través de memoria compartida
    local.

  * Los componentes que se espera que estén disponibles al mismo tiempo pueden
    utilizar llamadas sincrónicas para invocar las operaciones que requieren.

  * Los elementos implementados en un entorno distribuido no fiable —ver las
    [falacias de la computación
    distribuida](/4_Conceptos/4_Falacias_computacion_distribuida.md)— necesitarán
    depender de interacciones asíncronas basadas en el consumo y la producción de
    eventos, intercambiados a través de colas de mensajes o flujos de datos.

  Los dos estilos de interacción más comunes son [RPC](/4_Conceptos/4_RPC.md) y
  [REST](/4_Conceptos/4_REST.md).

* **Representación y estructura de los datos intercambiados**. Cada interfaz
  ofrece la oportunidad de abstraer la representación de datos interna,
  dependiente de las tecnologías utilizada para implementar el componente detrás
  de la interfaz, en una representación diferente, más adecuada para ser
  intercambiada entre diferentes componentes, implementados eventualmente en
  otras tecnologías, y transmitida a través de la red. La conversión de la
  representación interna a la externa se denomina "serialización",
  "*marshaling*" o "traducción".

  Los estilos de representación de datos más comunes, independientes del
  lenguaje de programación, se pueden dividir entre textuales
  —[XML](https://www.w3.org/TR/xml/) o
  [JSON](https://www.json.org/json-en.html)— y binarias —[*protocol
  buffers*](https://protobuf.dev/reference/protobuf/proto3-spec/)—.

* **Manejo de errores**. Un sistema bien diseñado debe saber cómo tomar las
  medidas adecuadas ante circunstancias no deseadas. Los actores necesitan saber
  si un componente está funcionando correctamente, si su interacción es exitosa
  y si se ha producido un error.

  Las estrategias para hacerlo incluyen las siguientes:

  * Las operaciones fallidas pueden generar una excepción.

  * Las operaciones pueden devolver un indicador de estado con códigos
    predefinidos.

  * Una propiedad se puede utilizar para almacenar un estado que indiquen si la
    última operación fue exitosa o no.

Se pueden activar eventos de error, como un tiempo de espera, para interacciones
asíncronas fallidas. El registro de errores se puede leer conectándose a un
flujo de datos de salida específico. La especificación de qué excepciones, qué
códigos de estado, qué eventos y qué información se utilizan para describir
resultados erróneos se convierte en parte de la interfaz de un elemento.

Las fuentes de error más comunes, que la interfaz debería gestionar
correctamente, incluyen las siguientes:

* Se envió información incorrecta, no válida o ilegal a la interfaz.

* El elemento está en el estado incorrecto para gestionar la solicitud.

* Se produjo un error de hardware o software que impidió que el elemento se
  ejecutara correctamente.

* El elemento no está configurado correctamente.

### Documentación de la interfaz

Mientras que una interfaz comprende todos los aspectos de las interacciones de
un componente con su entorno, lo que se documenta de la interfaz es más
limitado. Documentar todos los aspectos de todas las interacciones no es
práctico y casi nunca sería deseable; en su lugar, la documentación debe incluir
lo que los actores **deben** conocer para interactuar con la interfaz.

Diferentes personas tienen diferentes necesidades de información. Considera los
siguientes [interesados](/4_Conceptos/4_Interesado.md) cuando documentes una
interfaz, probablemente incluyendo información para cada uno en secciones
diferentes de la documentación:

* **Desarrollador del componente**. Debe conocer el contrato que debe cumplir su
  interfaz. Los desarrolladores solo pueden probar la información incorporada en
  la descripción de la interfaz.

* **Mantenedor**. Un tipo especial de desarrollador que realiza cambios
  asignados al componente y su interfaz mientras minimiza la interrupción de los
  actores existentes.

* **Desarrollador de un componente que utiliza la interfaz**. Debe comprender el
  contrato de la interfaz y cómo usarlo. Dichos desarrolladores pueden
  proporcionar información a la interfaz que debe respaldar.

* **Integrador y probador de sistemas**. Une el sistema a partir de sus elementos
  constituyentes y tiene un fuerte interés en el comportamiento del ensamblaje
  resultante. Este rol necesita información detallada sobre todos los recursos y
  la funcionalidad que proporciona y requiere un componente.

* **Analista**. Este rol depende de los tipos de análisis realizados. Para un
  analista de rendimiento, por ejemplo, la documentación de la interfaz debe
  incluir una garantía de acuerdo de nivel de servicio —SLA—, de modo que los
  actores puedan ajustar sus solicitudes de manera adecuada.

* **Arquitecto que busca activos para reutilizar en un nuevo sistema**. A menudo
  comienza examinando las interfaces de los elementos de un sistema anterior.
  El arquitecto también puede buscar en el mercado comercial elementos listos
  para usar que se puedan comprar y que hagan el trabajo. Para ver si un
  elemento es un candidato, el arquitecto se interesa por las capacidades de los
  recursos de la interfaz, sus atributos de calidad y cualquier variabilidad que
  proporcione el elemento.
