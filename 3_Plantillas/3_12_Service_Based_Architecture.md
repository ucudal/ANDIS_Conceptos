# 3 Plantillas

## 3.12 Estilo de arquitectura basada en servicios

Esta es la plantilla para un estilo de arquitectura basada en servicios o
*service-based architecture*; este es un estilo de arquitectura distribuida.

Esta plantilla está basada en [^1].

Aunque la arquitectura basada en servicios es una arquitectura distribuida, no
tiene el mismo nivel de complejidad y costo que otras arquitecturas
distribuidas, como los microservicios o la arquitectura orientada a eventos.

> [!NOTE]
> En esta plantilla no aparecen los componentes en cada paquete por simplicidad;
> en un diagrama de arquitectura deberían aparecer, además de los paquetes, los
> componentes en ellos.

La figura 1, a continuación, muestra la interfaz de usuario, los servicios, y la
base de datos, desplegados en unidades de despliegue independientes.

![Estilo service-based architecture](/diagrams/Architecture_Service_Based.svg)

#### *Figura 1: Estilo service-based architecture.*

<!-- TODO: Agregar las variantes que aparecen en la referencia abajo -->

[^1]: Richards, M. & Ford, N. (2020). Fundamentals of Software Architecture-An
      Engineering Approach. O'Reilly.
