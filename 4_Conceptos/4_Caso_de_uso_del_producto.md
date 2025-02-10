# 4 Conceptos

## Caso de uso del producto

Dado un [caso de uso del negocio](./4_Caso_de_uso_del_negocio.md), es necesario
decidir qué parte del [escenario](./4_Escenario.md) de ese caso de uso
será realizado por el producto de software que estamos diseñando y qué parte
será realizada por un [sistema adyacente](./4_Sistema_adyacente.md). La parte
del caso de uso del negocio que se gestiona a través del sistema automatizado
‑el producto‑ es el caso de uso del producto[^1].

[^1]: Robertson, S. & Robertson, J. (2012). Mastering the Requirements Process:
    Getting Requirements Right, 3<sup>rd</sup> Edition. Addison-Wesley
    Professional.

A veces, el caso de uso del producto coincide con el caso de uso del negocio;
esto ocurre cuando se decide automatizar todo el escenario. La mayoría de las
veces, en cambio, algunos pasos del escenario del caso de uso del negocio no son
parte del caso de uso del producto; esto es porque se decide que es mejor que
las personas u otros sistemas adyacentes realicen esos pasos.

Lo importante es que entiendas que el caso de uso del producto no está dado a
priori, sino que se deriva de la decisión, basado en el análisis, de qué parte
del [trabajo](./4_Trabajo_y_area_de_trabajo.md) es realizada por el producto y
qué parte no.

La siguiente [Figura 1](#figura-1) ilustra lo anterior: El evento del negocio es
un suceso que se produce en el sistema adyacente. El flujo de información
resultante notifica al trabajo del evento y desencadena una respuesta ‑el caso
de uso del negocio‑. Después de analizar esta situación el analista y los
[interesados](/4_Conceptos/4_Interesado.md) deciden qué parte del caso de uso
del negocio debe manejar el producto propuesto ‑el caso de uso del producto‑.
Todo lo que está inmediatamente fuera del alcance del producto se convierte en
un actor, que manipula la funcionalidad del caso de uso del producto dentro del
producto. Se muestra un diagrama de caso de uso UML para fines comparativos[^1].

<a id="figura-1"/>

![Caso de uso del producto](/diagrams/Product_Use_Case.svg)

*Figura 1: Caso de uso del producto*. Tomado de [^1]
