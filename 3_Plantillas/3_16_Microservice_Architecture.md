# 3 Plantillas

## 3.13 Estilo de arquitectura de microservicios

Esta es la plantilla para un estilo de arquitectura de microservicios o
*microservices architecture*; este es un estilo de arquitectura distribuida.

Esta plantilla está basada en [^1].

En este estilo de arquitectura cada servicio opera como una unidad separada con
su propia base de datos y demás recursos. Estos servicios se comunican entre sí
a través de API bien definidas, generalmente mediante protocolos ligeros como
HTTP o colas de mensajes.

Esta comunicación desacoplada permite que los servicios evolucionen y escalen de
manera independiente sin afectar a la aplicación completa.

![Estilo microservices architecture](/diagrams/Architecture_Microservices.svg)

*Figura 1: Estilo microservices architecture.*

Cada servicio suele implementar el patrón
[Sidecar](https://learn.microsoft.com/en-us/azure/architecture/patterns/sidecar)
tal como se muestra en la figura 2, a continuación:

![Sidecar](/diagrams/Architecture_Microservices_Sidecar.svg)

*Figura 2: Sidecar.*

[^1]: Richards, M. & Ford, N. (2020). Fundamentals of Software Architecture-An
      Engineering Approach. O'Reilly.
