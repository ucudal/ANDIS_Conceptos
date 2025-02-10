
# 4 Conceptos

## Evento del negocio

Los eventos del negocio son cosas que suceden y ‑a su vez‑ hacen que el
[trabajo](/4_Conceptos/4_Trabajo_y_area_de_trabajo.md) responda de alguna
manera[^1]. Compáralo con [evento del dominio](./4_Evento_del_dominio.md).

Un evento puede ocurrir fuera del alcance del trabajo ‑un evento
externo‑, o puede suceder porque es el momento de que el trabajo haga algo ‑un
evento desencadenado por el tiempo‑.

En el primer caso ‑un evento externo‑ una comunicación al trabajo desde el
exterior ‑representada por los [sistemas
adyacentes](/4_Conceptos/4_Sistema_adyacente.md)‑ le permite al trabajo saber
que el evento ha ocurrido. En el otro caso ‑el evento desencadenado por el
tiempo‑ el resultado es siempre un flujo hacia el mundo exterior.

En cualquier situación, cada vez que ocurre un evento del negocio, debe haber al
menos un flujo de datos para mostrarlo en el [diagrama de/2_Tecnicas_y_herramientas/2_01_2_Diagramas_de_contexto.md
contexto](/2_Tecnicas_y_herramientas/2_1_2_Diagramas_de_contexto.md).

Cada uno de los flujos de datos que entran o salen del trabajo es resultado de
un evento del negocio; no puede haber otra razón para que exista una
comunicación externa. Al observar cada flujo, se puede determinar el evento de
negocio que lo provocó. En algunos casos podrán adjuntarse varios flujos a un
mismo evento del negocio.

Para cada evento del negocio, existe una respuesta predefinida del trabajo,
conocida como [caso de uso del
negocio](/4_Conceptos/4_Caso_de_uso_del_negocio.md).

[^1]: Robertson, S. & Robertson, J. (2012). Mastering the Requirements Process:
Getting Requirements Right, 3<sup>rd</sup> Edition. Addison-Wesley Professional.
