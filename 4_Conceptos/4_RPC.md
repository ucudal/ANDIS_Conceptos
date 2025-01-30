# 4 Conceptos

## RPC o *remote procedure call*

RPC ‑o llamada a procedimiento remoto en español‑ es un estilo de interacción
entre [componentes](/4_Conceptos/4_Componente.md) que se basa en las llamadas a
procedimientos ‑sub-rutinas‑ de los lenguajes imperativos, excepto que el
procedimiento llamado se encuentra en otro componente en un espacio de
direccionamiento diferente ‑en otra parte de la red‑.

El programador codifica la llamada al procedimiento como si se estuviera
llamando a un procedimiento local. La llamada se traduce en un mensaje que se
envía al componente remoto donde se invoca el procedimiento real. Finalmente los
resultados se envían como un mensaje al elemento que realizó la llamada.

Los orígenes del concepto de RPC se remontan a los años '80. Existen diferentes
implementaciones del concepto de RPC. DCE/RPC que es un
[estándar](https://publications.opengroup.org/c706) de The Open Group. [Java
RMI](https://docs.oracle.com/javase/8/docs/technotes/guides/rmi/index.html) es
un ejemplo implementación del concepto de RPC para el lenguaje Java.

La implementación más reciente del concepto de RPC es [gRPC](https://grpc.io).
En gRPC los parámetros se transmiten en formato binario, es asíncrono, soporta
autenticación, flujos de datos bi-direccionales, control de flujo, cancelación y
tiempos de espera; usa HTTP 2.0 para transporte.
