# Conceptos

## Seguridad

La seguridad —o *security* en inglés— es un atributo de la calidad de software
que define la capacidad de protección de la información y los datos de manera
que las personas u otros sistemas, productos o componentes tengan el grado de acceso a los datos
adecuado a sus tipos y niveles de autorización, y para defenderse de los
patrones de ataque de agentes malintencionados[^1].

[^1]: ISO/IEC 25010. (2011). ISO/IEC 25010:2011, Systems and software
    engineering—Systems and software Quality Requirements and Evaluation
    (SQuaRE) — System and software quality models.

Esta característica se subdivide a su vez en las siguientes sub-características:

* **Confidencialidad**. Es la capacidad de asegurar que los datos solo son
  accesibles a aquellos con autorización para ello.
* **Integridad**. Es la capacidad de un producto para garantizar que el estado
  de un sistema, producto o componente y sus datos están protegidos frente a
  modificaciones o eliminaciones no autorizadas, ya sea por acciones
  malintencionadas o por errores informáticos.
* **No repudio**. Es la capacidad de demostrar las acciones o eventos que han
  tenido lugar, de manera que dichas acciones o eventos no puedan ser
  repudiados —rechazados, no aceptados— posteriormente.
* **Responsabilidad**. Es la capacidad de rastrear de forma inequívoca las
  acciones de una entidad.
* **Autenticidad**. Es la capacidad de un sistema, producto o componente para
  demostrar que la identidad de un sujeto o recurso es la que dice ser.

La definición es similar en [^2], que define la seguridad como la medida de la
capacidad del sistema para proteger los datos y la información del acceso no
autorizado y, al mismo tiempo, proporcionar acceso a las personas y los sistemas
que están autorizados.

Un ataque, es decir, una acción que se lleva a cabo contra un sistema con la
intención de causar daño, puede adoptar diversas formas. Puede ser un intento no
autorizado de acceder a los datos o servicios o de modificarlos, o puede tener
como objetivo denegar servicios a usuarios legítimos.

El enfoque más simple para caracterizar la seguridad se centra en tres
características: confidencialidad, integridad y disponibilidad —o CIA por las
siglas en inglés de *confidentiality*, *integrity* and *availability*—:

* La **confidencialidad** es la propiedad de que los datos o servicios están
  protegidos contra el acceso no autorizado. Por ejemplo, un pirata informático
  no puede acceder a las declaraciones de impuestos sobre la renta en una
  computadora del gobierno.
* La **integridad** es la propiedad de que los datos o servicios no están
  sujetos a manipulación no autorizada. Por ejemplo, la calificación de un
  estudiante no ha cambiado desde que su profesor la asignó.
* La **disponibilidad** es la propiedad de que el sistema, producto o componente
  estará disponible para un uso legítimo. Por ejemplo, un ataque de denegación
  de servicio no impediría acceder a es repositorio en línea.

Una técnica en el campo de la seguridad es el árbol de ataque o *attack tree* en
inglés. Pueden ver más información sobre qué es y cómo usar un árbol de ataque
[aquí](https://www.ncsc.gov.uk/collection/risk-management/using-attack-trees-to-understand-cyber-security-risk).

## Tácticas para la seguridad

<table>
  <tr>
    <td rowspan="18">
      Tácticas de seguridad
    </td>
    <td rowspan="4">
      Detectar ataques
    </td>
    <td>
      Detectar la intrusión
    </td>
  </tr>
  <tr>
    <td>
      Detectar la denegación del servicio
    </td>
  </tr>
  <tr>
    <td>
      Verificar la integridad de los mensajes
    </td>
  </tr>
  <tr>
    <td>
      Detectar anomalías en la entrega de mensajes
    </td>
  </tr>
  <tr>
    <td rowspan="9">
      Resistir ataques
    </td>
    <td>
      Identificar actores
    </td>
  </tr>
  <tr>
    <td>
      Autenticar actores
    </td>
  </tr>
  <tr>
    <td>
      Autorizar actores
    </td>
  </tr>
  <tr>
    <td>
      Limitar el acceso
    </td>
  </tr>
  <tr>
    <td>
      Limitar la exposición
    </td>
  </tr>
  <tr>
    <td>
      Cifrar los datos
    </td>
  </tr>
  <tr>
    <td>
      Separar entidades
    </td>
  </tr>
  <tr>
    <td>
      Validar la entrada
    </td>
  </tr>
  <tr>
    <td>
      Cambiar la configuración de las credenciales
    </td>
  </tr>
  <tr>
    <td rowspan="3">
      Reaccionar a ataques
    </td>
    <td>
      Revocar el acceso
    </td>
  </tr>
  <tr>
    <td>
      Restringir el ingreso
    </td>
  </tr>
  <tr>
    <td>
      Informar a los actores
    </td>
  </tr>
  <tr>
    <td rowspan="2">
      Recuperarse de los ataques
    </td>
    <td>
      Auditar
    </td>
  </tr>
  <tr>
    <td>
      No-repudio
    </td>
  </tr>
</table>

## Patrones para seguridad

Ver [Cloud design patterns that support
security](https://learn.microsoft.com/en-us/azure/well-architected/security/design-patterns)
en Microsoft Well-Architected Framework.

The Open Group. (2004). Security Design Patterns. Disponible
[aquí](https://pubs.opengroup.org/onlinepubs/9299969899/toc.pdf)


## Referencias adicionales

Microsoft. (2024). Microsoft Security Development Lifecycle. Disponible
[aquí](https://www.microsoft.com/en-us/securityengineering/sdl/)
