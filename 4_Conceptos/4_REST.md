# 4 Conceptos

## REST o *representational state transfer*

REST ‑o transferencia de estado representacional‑ es un estilo arquitectónico
creado por [Roy Fielding](https://en.wikipedia.org/wiki/Roy_Fielding) para guiar
el desarrollo y diseño de la arquitectura para la World Wide Web. Está basado en
seis restricciones impuestas sobre las [interacciones](./4_Interaccion.md) entre
los [componentes](/4_Conceptos/4_Componente.md) de una arquitectura distribuida
para un sistema de hipermedia a escala de Internet como el de la web[^1]:

[^1]: Bass, L.; Clements, P.; Kazman, R. (2022). Software Architecture in
    Practice, 4<sup>th</sup> edition. Addison-Wesley.

* [Interfaz](/4_Conceptos/4_Interfaz.md) uniforme. Todas las interacciones son
  de la misma forma, típicamente HTTP. Los [recursos](./4_Recurso.md) provistos
  a través de la interfaz se especifican mediante una URI ‑o *universal resource
  identifier*‑.

* Cliente-servidor. Los actores son clientes y los proveedores de recursos son
  servidores que utilizan el patrón cliente-servidor.

* Sin estado o *stateless*. Todas las interacciones entre el cliente y el
  servidor son sin estado, es decir, el cliente no debe asumir que el servidor
  ha conservado información sobre la última interacción del cliente.

  En consecuencia, por ejemplo, una interacción que requiera que previamente
  haya habido otra de autenticación, implica que de la autenticación resulta un
  token, y que este token se transmite con cada solicitud.

* Uso de caché. Es posible usar un caché para los recursos cada vez que sea
  aplicable. Se puede usar el caché tanto del lado del servidor como del
  cliente. Es necesario disponer de un mecanismos para conocer cuándo la
  respuesta queda desactualizada.

* Arquitectura en capas. El servidor puede dividirse en capas ‑ver por ejemplo
  el [estilo layered architecture](/3_Plantillas/3_9_Layered_Architecture.md)‑
  que se pueden desplegar de forma independiente. El cliente no tiene forma de
  saber si se está comunicando un servidor final o con un servidor intermedio.

* Código a demanda ‑opcional‑. El servidor puede proveer código al cliente para
  que éste ejecute. Javascript en un ejemplo.

Aunque HTTP es el protocolo que más se usa para implementar REST, no es el
único. La asociación de verbos de HTTP a las operaciones CRUD[^2] es una
convención posterior a la definición de REST que hizo Fielding.

[^2]: CRUD es el acrónimo de *create, read, update, delete*.

Habiendo aclarado eso, la tabla a continuación muestra la relación entre verbos
HTTP y las operaciones CRUD equivalentes.

| Verbo HTTP | Operación CRUD       |
| ---------- | -------------------- |
| POST       | *Create*             |
| GET        | *Read*               |
| PUT        | *Update* o *replace* |
| PATCH      | *Update* o *modify*  |
| DELETE     | *Delete*             |
