# 1 Contenido

## 1.1 Requisitos

<!-- TAG: Must have -->
### 1.1.3 Requerimientos funcionales

En esta tercera parte del análisis de requisitos deben definir el área de
trabajo, alcance del proyecto y los requerimientos funcionales del mismo.

<!-- TAG: Must have -->
## Área de trabajo

<!-- TAG: Must have -->
<!-- SECCIÓN: Situación actual -->
<!-- TODO Agregar definición y link para 'modelo de procesos de negocio' -->
Mediante un modelo de procesos de negocio, denotar los procesos de negocio
pertinentes que existen actualmente y que pueden ser reemplazados o cambiados
por la solución a desarrollar.

<!-- TAG: Must have -->
<!-- SECCIÓN: Interfaces pertinentes al trabajo -->
A alto nivel y mediante un diagrama, explicar las interacciones de la solución
con entidades adyacentes a la misma (otras personas, organizaciones, hardware y
software) y el input/output de estas interacciones.

<!-- TAG: Must have -->
<!-- SECCIÓN: Eventos y casos de uso del negocio -->
A alto nivel, listar todos los [eventos del
negocio](/4_Conceptos/4_Evento_del_negocio.md) a los que el trabajo a
desarrollar responde (es decir, [casos de uso del
negocio](../4_Conceptos/4_Caso_de_uso_del_negocio.md)), indicando: nombre del
evento del negocio, entrada (input) o información proveniente de la entidad
adyacente, salida (output) a la entidad adyacente y una breve descripción del
caso de uso del negocio. Se puede utilizar el siguiente formato:

| Evento del negocio                | Input y output                                 | Descripción del caso de uso del negocio           |
| -------------------------------- | ---------------------------------------------- | ------------------------------------------------- |
| *(Nombre del evento del negocio)* | *(Input y output del caso de uso del negocio)* | *(Breve descripción del caso de uso del negocio)* |

<!-- TAG: Must have -->
<!-- SECCIÓN: Especificación de los casos de uso del negocio -->
Detallar el paso a paso de cómo cada caso de uso del negocio identificado
anteriormente responde al evento del negocio correspondiente. Esto se puede
realizar mediante diagramas de actividad, escenarios de caso de uso del negocio,
diagramas de flujo, diagramas de secuencia o mapas mentales.

<!-- TAG: Must have -->
## Modelo de datos organizacionales y diccionario de datos

> [!NOTE] Cuando estés especificando el modelo de datos organizacionales y el
> diccionario de datos, asegúrate de ser consistente con la subsección de
> [convenciones de denominación y
> términos](#convenciones-de-denominación-y-términos) —es una buena idea que las
> entidades del dominio estén definidas en esa sección. A su vez, es una buena
> práctica el mantener un lenguaje ubicuo a lo largo y ancho del proyecto[^1].

<!-- TAG: Must have -->
<!-- SECCIÓN: Modelo de datos organizacionales -->
<!-- TODO Agregar definición y link a 'Modelo Entidad-Relación' -->
Mediante un [diagrama de clases
UML](../2_Tecnicas_y_herramientas/2_3_1_Diagramas_de_clases_UML.md), Modelo
Entidad-Relación o cualquier otro diagrama de datos, especificar todas las
entidades o clases relevantes al [área del
trabajo](../4_Conceptos/4_Trabajo_y_area_de_trabajo.md). Lo interesante aquí es
mostrar todas las entidades en cuestión y sus atributos o propiedades, además de
mostrar cómo las entidades se relacionan entre sí (para ello es importante
indicar la cardinalidad en las relaciones).

<!-- TAG: Must have -->
<!-- SECCIÓN: Diccionario de datos -->
Definir el contenido o formato de los siguientes items vistos en el modelo de
datos organizacionales:

* Entidades o clases
* Atributos
* Relaciones entre las entidades o clases
* Entradas y salidas de los modelos
* Datos dentro de las entradas y salidas

Se puede utilizar el siguiente formato:

| Nombre | Contenido | Tipo |
|--------|-----------|------|
| *Nombre* | *Contenido de la entidad/clase o formato del atributo* | *Clase/Relación/Atributo* |

> [!NOTE]
> En la columna ***Contenido***, nombrar los atributos de la entidad, y si la
> entrada pertenece a un atributo en vez de a una entidad, mencionar el formato
> del atributo.

Tanto el diccionario de datos como el modelo de datos organizacionales se irán
ampliando junto con el desarrollo de la solución, esto es: a medida que se vayan
haciendo ajustes o adiciones de clases/atributos/datos en el desarrollo de la
solución, reflejar estos cambios en el diccionario de datos y el modelo de datos
organizacionales.

Los términos utilizados en el diccionario de datos son los términos que se han
de usar al definir requerimientos atómicos detallados.

<!-- TAG: Must have -->
## Alcance del proyecto

<!-- TAG: Must have -->
<!-- SECCIÓN: Diagrama o tabla de casos de uso -->
Mediante un [diagrama de casos de
uso](/2_Tecnicas_y_herramientas/2_4_2_Diagramas_de_casos_de_uso_UML.md), definir
los casos de uso del producto.

Una tabla con la misma información que los diagramas de casos de uso —es decir,
nombre de los casos de uso, actores participantes, relación de `extends` o
`includes` con otros casos de uso— suele ser más cómoda cuando la cantidad de
casos de uso es mayor a 20.

<!-- TAG: Must have -->
<!-- SECCIÓN: Detalles de los casos de uso del producto -->
Definir los detalles de cada [caso de uso del
producto](../4_Conceptos/4_Caso_de_uso_del_producto.md). Esto se puede realizar
mediante una de las siguientes opciones:

> [!NOTE]
> El próximo listado está ordenado descendentemente según la formalidad
> de cada alternativa, esto es: la primer opción es la más formal, la última la
> menos. De las cinco opciones presentadas, las tres primeras las consideramos
> formales y las últimas dos informales.

* Un escenario descrito textualmente, paso a paso, incluyendo excepciones y
  alternativas
* Un [diagrama de actividades
  UML](../2_Tecnicas_y_herramientas/2_4_1_Diagramas_de_actividades_UML.md) o un
  [diagrama de procesos
  BPMN](/2_Tecnicas_y_herramientas/2_4_4_Diagramas_BPMN.md)
* Una historia de usuario descrita textualmente
* Un guión gráfico
* Un prototipo de baja o alta fidelidad

> [!WARNING]
> A efectos de entregas de Proyecto, debes utilizar **al menos una
> opción formal**, aunque puedes utilizar de forma adicional opciones informales
> para profundizar en los casos de uso o aclararlos. Para utilizar únicamente
> opciones informales, debes contar con la autorización de tu tutor.

<!-- TAG: Must have -->
## Requerimientos funcionales

En esta subsección se detallan los requerimientos funcionales del producto,
utilizando el [template de requerimiento
atómico](../3_Plantillas/3_1_Requerimiento_atomico.md) para cada uno de ellos.

Estos requerimientos emergen de los casos de uso del producto.

[^1]: Evans, E. (2003). Domain-Driven Design. Addison-Wesley Professional.
