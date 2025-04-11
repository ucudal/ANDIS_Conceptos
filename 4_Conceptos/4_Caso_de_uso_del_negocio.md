# 4 Conceptos

## Caso de uso del negocio

Un caso de uso[^1] de negocio es una descripción de la forma en la que el
[trabajo](./4_Trabajo_y_area_de_trabajo.md) responde a un [evento del
negocio](./4_Evento_del_negocio.md) ‑que incluye un flujo de datos asociado‑
generado desde un [sistema adyacente](./4_Sistema_adyacente.md). El trabajo
responde mediante el procesamiento de los datos de entrada, la recuperación de
datos almacenados, y almacenamiento de datos procesados[^2].

[^1]: Esta definición de caso de uso no necesariamente coincide con la
    definición de caso de uso "a secas" introducida por Ivar Jacobson que fue
    quién acuñó el término. Jacobson lo define como "una secuencia de acciones
    que uno o más actores realizan en un sistema para obtener un resultado
    significativo"[^3]. En el contexto del relevamiento de requerimientos ‑donde
    todavía no está definido qué parte del trabajo será automatizada por el
    producto de software‑ la definición original de Jacobson no tiene mucho
    sentido. Por eso es importante que los casos de uso del negocio sean
    agnósticos de la solución.

[^2]: Robertson, S. & Robertson, J. (2012). Mastering the Requirements Process:
Getting Requirements Right, 3<sup>rd</sup> Edition. Addison-Wesley Professional.

[^3]: Jacobson, I., Christerson, M., Jonsson, P., & Övergaard, G. (1992).
    Object-Oriented Software Engineering: A Use Case Driven Approach.
    Addison-Wesley.

![BUC](/diagrams/BUC.svg)

Los casos de uso de negocio capturan las actividades y los pasos de un proceso
del negocio de principio a fin, sin enfocarse en detalles de implementación
técnica, sino en las necesidades organizacionales y los objetivos estratégicos.

El proceso en el caso de uso del negocio puede ser especificado utilizando
[escenarios](/4_Conceptos/4_Escenario.md), [diagramas
BPMN](/2_Tecnicas_y_herramientas/2_04_.Modelos_de_comportamiento/2_04_04_Diagramas_BPMN.md)
o [diagramas de actividades
UML](/2_Tecnicas_y_herramientas/2_04_.Modelos_de_comportamiento/2_04_01_Diagramas_de_actividades_UML.md)

Los casos de uso del negocio tienen estas características[^2]:

* Son particiones naturales en el sentido de que cada uno hace una contribución
  obvia y lógica al trabajo.

* Tienen conexiones mínimas con otras partes del trabajo.

* Tienen un alcance y reglas bien definidas.

* Tienen límites observables que pueden ser definidos.

* Se pueden nombrar de forma que los [interesados](./4_Interesado.md) entienden
  de qué se está hablando.

* Se puede constatar su existencia fácilmente.

* Hay uno o más interesados expertos en esa parte del trabajo.
