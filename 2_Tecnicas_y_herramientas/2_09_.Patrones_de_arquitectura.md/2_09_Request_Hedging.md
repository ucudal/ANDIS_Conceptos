
# 2 Técnicas y herramientas

## 2.9 Patrones de arquitectura

### *Request Hedging* o solicitudes protegidas

*Request Hedging* es un patrón de tolerancia a fallos en [sistemas
distribuidos](/4_Conceptos/4_Computacion_distribuida.md) donde se envía la misma
solicitud —o cierto número X de solicitudes iguales— a múltiples servicios
simultáneamente y se utiliza la primera —o las primeras X— respuestas correcta
recibidas; las demás respuestas se se descartan o se cancelan las demás
solicitudes.

Este patrón es mencionado en [^1].

[^1]: Bass, L.; Clements, P.; Kazman, R. (2022). Software Architecture in
    Practice, 4<sup>th</sup> edition. Addison-Wesley.

Este enfoque ayuda a reducir la [latencia de cola
larga](/4_Conceptos/4_Computacion_nube.md#latencia-de-cola-larga) y a mejorar la
confiabilidad del sistema.

#### Cómo funcionan las solicitudes protegidas

En lugar de esperar a que se complete una sola solicitud, lo cual podría ser
lento debido a problemas de red, carga del servidor u otros, se envían
solicitudes idénticas a múltiples réplicas del mismo servicio. En cuanto alguna
de ellas responde correctamente, se utiliza esa respuesta y se descartan o
cancelan las solicitudes restantes.

#### Beneficios

La latencia no aumenta cuando una solicitud a un servicio o una ruta a un
servicio se ralentiza puntualmente —en la medida que haya otras solicitudes
enviadas en paralelo a otros servicios por otras rutas que no se ralenticen—.

La confiabilidad aumenta si uno de los servicios no puede responder la solicitud
pues alcanza con que algún otro lo haga.

Es posible lograr que para el código del cliente que hace la solicitud el uso de
*Request Hedging* sea transparente.

#### Consideraciones de implementación

*Request Hedging* aumenta la carga en los servicios y en la red, ya que se
realizan múltiples llamadas para cada solicitud lógica. Es necesario equilibrar
las ventajas de rendimiento y confiabilidad con el consumo adicional de
recursos.

<!-- cSpell:ignore idempotente idempotentes https://dle.rae.es/idempotente -->

Este patrón funciona mejor con operaciones idempotentes[^2], donde
múltiples ejecuciones no causan efectos secundarios.

[^2]: Una operación idempotente es la que tiene el mismo efecto
    independientemente de la cantidad de veces que se ejecute. Una lectura es
    idempotente, una actualización suele ser idempotente, pero la creación o
    eliminación de un recurso no.

Las solicitudes pueden ser enviadas todas al mismo tiempo o pueden ser enviadas
cada cierto tiempo mientras no se reciba una respuesta.

> [!TIP]
> Vean [aquí](https://grpc.io/docs/guides/request-hedging/) cómo gRPC soporta e
> implementa *Request Hedging*.
