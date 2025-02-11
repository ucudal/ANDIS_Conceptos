# 2 Técnicas y herramientas

## 2.1 Relevamiento

### 2.1.2 Diagramas de contexto

Diagrama de contexto es un modelo gráfico del [alcance del
trabajo](/4_Conceptos/4_Trabajo_y_area_de_trabajo.md) que muestra cómo el
trabajo a investigar se conecta con el mundo exterior[^1].

El diagrama de contexto se utiliza para generar ‑y luego mostrar‑ el consenso
entre las partes interesadas sobre el alcance del trabajo. El producto final que
resulta del proyecto se utilizará para realizar parte de este trabajo.

El diagrama de contexto identifica el alcance del trabajo a estudiar. Muestra el
trabajo como una sola actividad, rodeada por los [sistemas
adyacentes](/4_Conceptos/4_Sistema_adyacente.md). Las flechas etiquetadas
representan los flujos de datos entre el trabajo y los sistemas adyacentes. Los
sistemas adyacentes son las actividades que se tomó la decisión de no estudiar.

El contexto de trabajo muestra dónde comienzan y terminan las responsabilidades
del trabajo y las responsabilidades de los sistemas adyacentes.

Aunque no hay una notación estándar para los diagramas de contexto, es posible
usar un [diagrama de casos de uso UML](./2_4_2_Diagramas_de_casos_de_uso_UML.md)
para construirlos. Un diagrama de contexto tiene los siguientes elementos:

* **Trabajo**. Utiliza un caso de uso para modelar el trabajo; el nombre del
  caso de uso es el nombre del producto, del proyecto, o del trabajo.

* **Sistemas adyacentes**. Utiliza actores para modelar los sistemas adyacentes.
  El nombre del actor es el nombre del sistema adyacente. Estereotipos
  opcionales en los actores para modelar sistemas adyacentes, pueden incluir el
  tipo de sistema adyacente: ≪active system≫, ≪autonomous system≫ o
  ≪cooperative system≫.

* **Flujos de datos**. Los flujos de datos los modelamos con asociaciones
  dirigidas. La dirección de la asociación es en el sentido del flujo de datos.
  El nombre de la asociación indica los datos que llegan o salen desde o hacia
  el trabajo.

* Opcionalmente puede haber una frontera rodeando el caso de uso.

La [Figura 1](#figura-1), a continuación, muestra un ejemplo ‑parcial‑ de un
diagrama de contexto para una `Comunidad en línea`. Los sistemas adyacentes son
los `Usuarios de la comunidad`, los `Anunciantes` y los `Creadores de
contenido`. Los datos intercambiados aparecen como las etiquetas de las
asociaciones; por ejemplo, el `Anunciante` recibe de la comunidad `Slots de
publicidad` y envía `Pagos`.

<a id="figura-1"/>

![Ejemplo de diagrama de contexto](/diagrams/Context_Diagram_Example.svg)

*Figura 1: Ejemplo de un diagrama de contexto.*

La [Figura 2](#figura-2), a continuación, muestro otro ejemplo de un diagrama de
contexto para un `Sistema de ventas`. Los sistemas adyacentes `Comprador en
línea` y `Vendedor telefónico` están estereotipados con ≪active system≫ —pues
son humanos que interactúan con el trabajo—, mientras que `Sistema de
mantenimiento de productos`, `Sistema de autorización de crédito` y `Sistema de
gestión del depósito` están estereotipados con ≪cooperative system≫ —pues son
sistemas automatizados que colaboran con el trabajo mediante mensajes y
respuestas—.

<a id="figura-2"/>

![Otro ejemplo de un diagrama de contexto](/diagrams/Context_Diagram_Second_Example.svg)

*Figura 2: Otro ejemplo de un diagrama de contexto*


Con el diagrama de contexto es posible derivar los [eventos del
negocio](/4_Conceptos/4_Evento_del_negocio.md), aunque durante el relevamiento
la identificación de los eventos del negocio puede modificar el diagrama de
contexto y viceversa. Los eventos del negocio se especifican usando la [plantilla
de eventos del negocio](/3_Plantillas/3_17_Eventos_del_negocio.md).

[^1]: Robertson, S. & Robertson, J. (2012). Mastering the Requirements Process:
Getting Requirements Right, 3<sup>rd</sup> Edition. Addison-Wesley Professional.
