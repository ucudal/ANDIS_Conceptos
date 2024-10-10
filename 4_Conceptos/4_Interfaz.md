# Conceptos

## Interfaz

Las interfaces son un mecanismo de abstracción fundamental necesario para
conectar [componentes](./4_Componente.md) en una arquitectura de software[^1].

[^1]: Bass, L., Clements, P., Kazman, R. (2022). Software Architecture in
    Practice, 4<sup>th</sup> edition. Addison-Wesley.

En este documento usaremos los siguientes términos relacionados con las
interfaces:

* **Clientes**. Son los demás componentes, usuarios o sistemas con los que
  interactúa un componente.

* **Entorno** o —*environment*—. Es el conjunto de clientes con los que
  interactúa un componente.

* **Interacciones**. Aunque pueden tomar múltiples formas, las más relevantes
  son las transferencias de control —*calls*— o de datos. Por ejemplo la
  invocación local de procedimientos, funciones o métodos usando construcciones
  de un lenguaje de programación, la llamada a procedimientos remotos –RPC–,
  flujos de datos, memoria compartida, o envío de mensajes, son formas de
  interacción.

* **Recursos**. Son las construcciones que proveen puntos de interacción directa
  con un componente.

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
  producen eventos salientes que se utilizan para notificar a los oyentes (o
  suscriptores) sobre cosas interesantes que suceden dentro del elemento.