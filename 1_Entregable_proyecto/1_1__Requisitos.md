# 1 Contenido

## 1.1 Requisitos

El propósito de esta sección es reunir, analizar, definir y especificar las
necesidades del usuario y las funcionalidades del sistema.

### Glosario

Explicar todas las abreviaturas, términos y acrónimos particulares empleados en
el contexto del proyecto y del problema que son utilizados en el documento.

### Posicionamiento del proyecto

Esta subsección da un resumen general del proyecto.

#### Oportunidad de negocio

Describir brevemente la oportunidad de negocio que el cliente trata de alcanzar
con este proyecto, esto es: explicar por qué el negocio del cliente se beneficia
de este proyecto y cómo.

#### Declaración del problema

Sin entrar en detalles, describir el problema que este proyecto intenta
resolver. Opcionalmente se puede utilizar el siguiente formato:

<table>
  <tr><td>El problema</td><td><i>(descripción del problema)</i></td></tr>
  <!-- TODO Agregar definición y link para 'stakeholders' -->
  <tr><td>Afecta a</td><td><i>(stakeholders afectados)</i></td></tr>
  <tr><td>Cuyo impacto es</td><td><i>(¿cuál es el impacto del problema?)</i></td></tr>
  <tr><td>Una solución exitosa debe tener</td><td><i>(listar algunos beneficios
  clave de una solución exitosa)</i></td></tr>
</table>

#### Declaración del posicionamiento del producto

Dar un resumen general que indique, a alto nivel y sin entrar en detalles, las
características del producto a desarrollar. Algunas cosas a mencionar:

* Organización cliente (opcional, si ya se mencionó antes)

* Categoría del producto y opcionalmente nombre, en caso de tenerlo definido.
  **Preguntas disparadoras**: *¿Qué es el producto que voy a desarrollar?
  ¿Cómo se llama?*

* Beneficios del producto

* Productos alternativos. **Pregunta disparadora**: *¿Qué otros productos
  similares existen actualmente?*

* Diferenciación del producto en comparación con las alternativas. **Preguntas
  disparadoras**: *¿Qué tiene de diferente mi producto a desarrollar en
  comparación con las alternativas mencionadas? ¿Por qué el cliente no utiliza
  las alternativas?*

#### Objetivos del proyecto

<!-- TODO Agregar definiciones y links para 'objetivos', 'propósito', 'beneficio'
y 'métricas del beneficio' -->

Mencionar a alto nivel los objetivos del proyecto. Para ello, describir el
propósito, beneficio y métricas del beneficio para cada objetivo.

Se puede usar el siguiente formato:

| Objetivo              | Propósito                | Beneficio                | Métrica del beneficio          |
| --------------------- | ------------------------ | ------------------------ | ------------------------------ |
| *Título del objetivo* | *Propósito del objetivo* | *Beneficio del objetivo* | *Cuantificación del beneficio* |
| ...                   | ...                      | ...                      | ...                            |

### Interesados (*stakeholders*)

<!-- TODO Agregar definición y link para 'interesados' -->

Esta subsección busca analizar a los interesados en el proyecto. Para ello, se
presenta: el cliente del proyecto, el comprador o consumidor del producto,
usuarios del producto y otros interesados.

#### Cliente del proyecto

<!-- TODO Agregar definición y link para 'cliente' -->

Mencionar el cliente o clientes del proyecto. Limitarse a mencionar tres como
máximo. Para cada uno, mencionar su rol en la organización, rol en el proyecto,
perfil técnico, criterio de éxito (cómo el cliente define el éxito del proyecto
o factores clave para que el cliente considere al proyecto exitoso) y otros
comentarios sobre el cliente.

#### Comprador o consumidor del producto

Mencionar el arquetipo del comprador o consumidor del producto. Por ejemplo: Si
el producto a desarrollar fuera una aplicación de gestión de seguimiento de
horas de empleados, el consumidor podría ser cualquier empresa interesada en
hacer un seguimiento de horas de sus empleados.

#### Usuarios

Describir a los usuarios del sistema. Se puede usar el siguiente formato como
guía:

<table>
  <tr><td>Descripción</td><td><i>Descripción breve del usuario y la relación que
  tendrá con el sistema.</i></td></tr>
  <!-- TODO Agregar definición y link para 'stakeholders' -->
  <tr><td>Representado por</td><td><i>Stakeholders que representan en el proyecto
  a este tipo de usuario. Por ejemplo, el usuario “telefonista” podría estar
  representado por el stakeholder “Encargado del Call Center”</i></td></tr>
  <tr><td>Rol en la organización</td><td><i>Descripción del rol que desempeña en
  la organización cliente.</i></td></tr>
  <tr><td>Rol en el sistema</td><td><i>Descripción del rol que tendrá con respecto
  a la operación del sistema. Por ejemplo: “este usuario ingresará los datos de
  ventas”.</i></td></tr>
  <tr><td>Perfil técnico</td><td><i>Describir el nivel técnico a efectos del uso
  de un sistema de software. Por ejemplo: usuario común, técnico avanzado, experto
  del negocio, experto en tecnologías.</i></td></tr>
  <tr><td>Criterio de éxito</td><td><i>¿Cómo el usuario define el éxito del
  proyecto? ¿Qué factores determinan el éxito del proyecto según el usuario?</i></td></tr>
  <tr><td>Comentarios</td><td><i>Comentarios sobre el usuario.</i></td></tr>
</table>

##### Estadísticas del mercado o usuarios

Resumir los datos demográficos clave que motivan las decisiones del producto.

**Algunas preguntas disparadoras**: *¿Cuántos usuarios tendrá el producto? ¿Cómo
se estima que crecerá el número de usuarios? ¿Cuánto dinero gasta el cliente
tratando de satisfacer por otros medios las necesidades que el producto podrá
cubrir?*

##### Entornos de los usuarios

Detallar el ambiente de trabajo del usuario objetivo. **Algunas preguntas
disparadoras**:

* Número de personas involucradas en la tarea. ¿Es cambiante?

* ¿Cuán extenso es el ciclo de una tarea? ¿Cuánto tiempo se dedica a cada
  actividad? ¿Es cambiante?

* Restricciones ambientales particulares: móviles, exteriores, en vuelo, etc.

* ¿Qué plataformas de sistemas se encuentran en uso actualmente? ¿Y plataformas
  futuras?

* ¿Qué otras aplicaciones están en uso? ¿Precisa esta aplicación ser integrada
  con ellas?

#### Otros interesados

Mencionar otras personas u organizaciones interesadas en el proyecto o afectadas
por él. Estos interesados pueden formar parte de la organización cliente o
trabajar para ella y sus comentarios pueden ser valiosos para el proyecto, por
ejemplo: patrocinadores, expertos del dominio, usuarios del sistema actual,
expertos en legislación, diseñadores, usuarios encargados del mantenimiento del
sistema, encargados del servicio técnico, etcétera.

Para cada uno de ellos, mencionar: rol en el proyecto, rol en la organización,
aporte al proyecto, grado de involucración en el proyecto y nivel de influencia
en el proyecto.

### Identificación de necesidades clave

Listar los problemas clave junto con las soluciones existentes, de acuerdo a la
percepción de los interesados. Aclarar los siguientes elementos de cada
problema:

* ¿Cuáles son las razones para este problema?

* ¿De qué manera se lo soluciona ahora?

* ¿Qué soluciones desea el interesado?

Se puede usar el siguiente formato para cada necesidad:

<table>
  <tr><td>Descripción</td><td><i>Breve descripción de la necesidad y sus motivos.</i></td></tr>
  <tr><td>Prioridad</td><td><i>¿Qué nivel de prioridad tiene esta necesidad?</i></td></tr>
  <tr><td>Concierne a</td><td><i>¿A quién concierne esta necesidad?</i></td></tr>
  <tr><td>Solución actual</td><td><i>¿Cuál es la solución actual para esta necesidad?</i></td></tr>
  <tr><td>Solución propuesta</td><td><i>¿Qué solución propone el sistema ante esta
  necesidad?</i></td></tr>
</table>

### Contexto del trabajo

Esta subsección busca determinar los límites del trabajo a realizar y cómo
encaja en su entorno.

#### Situación actual

<!-- TODO Agregar definición y link para 'modelo de procesos de negocio' -->

Mediante un modelo de procesos de negocio, denotar los procesos de negocio
pertinentes que existen actualmente y que pueden ser reemplazados o cambiados
por la solución a desarrollar.

#### Interfaces pertinentes al trabajo

A alto nivel y mediante un diagrama, explicar las interacciones de la solución
con entidades adyacentes a la misma (otras personas, organizaciones, hardware y
software) y el input/output de estas interacciones.

#### Eventos y casos de uso del negocio

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

#### Especificación de los casos de uso del negocio

Detallar el paso a paso de cómo cada caso de uso del negocio identificado
anteriormente responde al evento del negocio correspondiente. Esto se puede
realizar mediante diagramas de actividad, escenarios de caso de uso del negocio,
diagramas de flujo, diagramas de secuencia o mapas mentales.

#### Resumen de capacidades

Resumir los beneficios y características más importantes que el sistema ha de
proveer. Por ejemplo, si el sistema en cuestión fuera un sistema de atención al
cliente, en esta parte se abordaría la gestión de documentación de problemas
comunes, gestión de reclamos, telefonistas, etc., sin mencionar la cantidad de
detalle que cada una de estas partes requiere. Organizar las funciones de forma
que la lista resulte comprensible para el cliente o para cualquier otro que lea
el documento por primera vez. Una tabla sencilla que resuma los beneficios clave
y las características que los hacen posibles puede ser suficiente. Por ejemplo:

| Beneficio para el cliente                                                                                    | Característica que produce el beneficio                                                                                                               |
| ------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| Un nuevo equipo de soporte puede rápidamente ponerse a tono.                                                 | Una base de conocimientos asiste al personal de soporte identificando rápidamente las fallas conocidas y sus soluciones.                              |
| La Administración puede identificar las áreas problema y medir la carga de trabajo del equipo.               | Los reportes de tendencias permiten una vista de alto nivel del estado del problema.                                                                  |
| Los equipos de soporte distribuidos pueden trabajar juntos para resolver problemas.                          | El servidor de replicación permite que la información de la base de datos actual sea compartida a través de la empresa.                               |
| Los clientes se pueden ayudar a sí mismos, bajando los costos de soporte y mejorando el tiempo de respuesta. | La base de conocimientos puede ser habilitada a través de Internet. Incluye capacidades de búsqueda con hipertexto y una máquina de consulta gráfica. |

#### Asunciones y dependencias

Listar los asunciones que, si fueran cambiadas, cambiarían las capacidades del
producto tal como están descritas en este documento. Por ejemplo, una asunción
puede ser que un sistema operativo específico estará disponible para el
producto, de tal forma que si el sistema operativo no está disponible, el
documento deberá ajustarse.

#### Costos y precios

Las características de costo y precio pueden impactar directamente a la
definición e implementación de la aplicación. En esta parte se deben registrar
todas las restricciones de costos y precios que sean relevantes. Por ejemplo,
adquisición de hardware para el sistema.

#### Instalación

Listar las características de instalación, ya que estas pueden también impactar
directamente al esfuerzo de desarrollo. Por ejemplo, brindar serialización o
seguridad con encriptación requerirá esfuerzos adicionales de desarrollo. Los
requerimientos de instalación también pueden afectar a la codificación, o crear
la necesidad de un software de instalación separado.

#### Alternativas competitivas

Identificar las alternativas que la organización cliente percibe como
disponibles. Éstas alternativas compiten con la realización de este proyecto y
pueden incluir comprar un producto de la competencia, construir una solución
internamente o simplemente mantener el status quo. Listar todas las alternativas
competitivas existentes, o que puedan volverse disponibles, incluyendo los
productos existentes de la competencia. Incluir las debilidades y fortalezas más
importantes de cada una, en el contexto de la organización cliente.

### Modelo de datos organizacionales y diccionario de datos

> [!NOTE]
> Cuando estés especificando el modelo de datos organizacionales y el
> diccionario de datos, asegúrate de ser consistente con el
> [glosario](#glosario) —es una buena idea que las entidades del dominio estén
> definidas en el glosario—. A su vez, es una buena práctica el mantener un
> lenguaje ubicuo a lo largo y ancho del proyecto[^1].

Esta subsección consiste de la especificación a alto nivel de entidades
esenciales para el proyecto. Esta especificación se realiza mediante el diagrama
de modelo de datos organizacionales y el diccionario de datos.

#### Modelo de datos organizacionales

<!-- TODO Agregar definición y link a 'Modelo Entidad-Relación' -->

<!-- TODO Cuando esté definido qué termino usar para contexto del trabajo,
actualizarlo acá también -->

Mediante un [diagrama de clases UML](../2_Tecnicas_y_herramientas/2_3_1_Diagramas_de_clases_UML.md)
, Modelo Entidad-Relación o cualquier otro diagrama de datos, especificar todas
las entidades o clases relevantes al contexto del trabajo. Lo interesante aquí
es mostrar todas las entidades en cuestión y sus atributos o propiedades, además
de mostrar cómo las entidades se relacionan entre sí (para ello es importante
indicar la cardinalidad en las relaciones).

#### Diccionario de datos

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

### Restricciones

<!-- TODO Agregar definición y link para 'Restricción' -->

Esta subsección detalla las diferentes restricciones de diseño o restricciones
externas que se impongan para el desarrollo del producto.

#### Restricciones de diseño y tecnologías

Cada una de las restricciones mencionadas en esta parte debe usar el [template
de requerimiento atómico](../3_Plantillas/3_1_Requerimiento_atomico.md).

Mencionar las restricciones relacionadas con el diseño de la solución. *(¿La
solución deberá ser una aplicación web? ¿deberá ser una aplicación mobile?
¿deberá seguir un patrón de arquitectura de software en específico?)*

En caso de existir restricciones sobre las tecnologías a utilizar para el
desarrollo de la solución, detallarlas mencionando —en caso de ser pertinente—
la versión de las mismas.

#### Restricciones de entorno de instalación

Mencionar aquellas restricciones relacionadas al entorno de instalación de la
solución. Estas pueden ser restricciones en cuanto al lugar físico o virtual en
el cual la solución final deberá ser instalada.

Suele ser conveniente utilizar un diagrama para explicar las interacciones del
sistema con el entorno y otros sistemas con los que la solución deba
interactuar.

#### Restricciones de utilización de software externo

Utilizando el [template de requerimiento
atómico](../3_Plantillas/3_1_Requerimiento_atomico.md), mencionar las
restricciones existentes sobre la utilización de software externo. Esto es: la
obligación de que la solución se integre con con un software externo específico.

#### Restricciones organizacionales

Utilizando el [template de requerimiento
atómico](../3_Plantillas/3_1_Requerimiento_atomico.md), detallar aquellas
restricciones provenientes de las políticas de la organización/empresa cliente.

#### Restricciones de calendario

Mencionar las restricciones temporales o *deadlines* del proyecto. En caso de
existir alguna ventana temporal de oportunidad, mencionarla también.

Para cada restricción de calendario, detallar el momento o fecha claramente,
explicar el grado de importancia de la restricción y por qué es importante.
Además, explicar las consecuencias de no cumplir con la restricción.

#### Restricciones de presupuesto

Mencionar el presupuesto del proyecto expresado en términos monetarios o
recursos disponibles.

Los requerimientos no deben exceder el presupuesto, así que esta restricción
determina qué requerimientos son incluidos en el producto.

### Casos de uso del producto

En esta subsección se definen los [casos de uso del
producto](../4_Conceptos/4_Caso_de_uso_del_producto.md) y se detallan
individualmente.

#### Diagrama de casos de uso

Mediante un [diagrama de casos de
uso](/2_Tecnicas_y_herramientas/2_4_2_Diagramas_de_casos_de_uso_UML.md), definir
los casos de uso del producto.

Una tabla con la misma información que los diagramas de casos de uso —es decir,
nombre de los casos de uso, actores participantes, relación de `extends` o
`includes` con otros casos de uso— suele ser más cómoda cuando la cantidad de
casos de uso es mayor a 20.

#### Detalles de los casos de uso del producto

Definir los detalles de cada caso de uso del producto. Esto se puede realizar
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

### Requerimientos funcionales

En esta subsección se detallan los requerimientos funcionales del producto,
utilizando el [template de requerimiento
atómico](../3_Plantillas/3_1_Requerimiento_atomico.md) para cada uno de ellos.

Estos requerimientos emergen de los casos de uso del producto.

### Requerimientos no funcionales

En esta subsección se detallan los diferentes tipos de requerimientos no
funcionales del producto, utilizando el [template de requerimiento
atómico](../3_Plantillas/3_1_Requerimiento_atomico.md) en cada caso.

#### Requerimientos de apariencia

Detallar los requerimientos asociados a la apariencia del sistema, por ejemplo:
guías de UX/UI a utilizar —quizá brindadas por el cliente—, marca corporativa de
la organización cliente, qué colores utilizar, etcétera. Si el sistema no cuenta
con ninguna interfaz gráfica de usuario, indicarlo.

#### Requerimientos de usabilidad y humanidad

Esta subsección trata con los requerimientos que hacen al producto usable y
aceptable para los usuarios finales.

##### Requerimientos de facilidad de uso

Detallar los requerimientos del cliente en cuanto a la facilidad de uso del
sistema por parte de los usuarios finales. Ten en cuenta que esta facilidad es
derivada de: la habilidad de los previstos usuarios finales y la complejidad del
producto y sus funcionalidades. Algunas características a tener en cuenta pueden
ser:

<!-- TODO Agregar ejemplos de cada tipo de requisito incluyendo además criterio
de aceptación -->

* Eficiencia de uso: Qué tan rápido o con qué precisión el usuario puede usar el
  producto.
* Facilidad de memorización: Qué tanto se espera que el usuario casual memorice
  en cuanto a usar el producto.
* Tasa de errores: Qué tantos errores sería aceptable que el usuario cometa.
  Para algunos productos, es crucial que el usuario cometa muy pocos errores, o
  en ocasiones, ninguno.
* Satisfacción general al usar el producto: Para productos que tienen cierta
  competencia, es esencial que los usuarios se sientan muy satisfechos al usar
  el producto. De ser el caso, es valioso registrar esto como un requerimiento.
* Retroalimentación: Qué tanta retroalimentación el usuario necesita para
  sentirse confiado en cuanto a que el producto está haciendo precisa y
  correctamente lo que se espera de él. Productos de seguridad o tareas críticas
  suelen necesitar un alto nivel de retroalimentación.

##### Requerimientos de personalización e internacionalización

Especificar los requerimientos asociados a las preferencias de los usuarios.

Estos requerimientos indican cómo el sistema puede ser modificado o configurado
por los usuarios para tener en cuenta sus preferencias y selección de lenguaje
utilizado por el sistema.

En otras culturas, se usan diferentes sistemas de unidades —sistema métrico,
anglosajón, etcétera—, unidades monetarias,

idiomas, etcétera.

En caso de que el cliente no esté interesado en definir este tipo de
requerimientos, indicarlo.

##### Requerimientos de aprendizaje

Detallar las expectativas del cliente en cuanto a qué tanto esfuerzo deberán
emplear los usuarios finales para poder utilizar el sistema de una forma
productiva.

Algunos sistemas deben ser muy fáciles de utilizar y por ende intuitivos, otros
se pueden permitir determinada curva de aprendizaje debido a la complejidad del
problema. La idea aquí es cuantificar la cantidad de tiempo o esfuerzo que los
usuarios finales necesitan para aprender a usar el sistema y que esta
cuantificación sea aceptable para el cliente. Esta clarificación puede incluir
un plan de capacitación para los usuarios, e incluso un manual de usuario, por
ejemplo: "Los usuarios deberán ser capaces de usar el sistema tras una semana de
capacitación" o, "Los usuarios deberán ser capaces de utilizar el sistema tras
leer el manual de usuario".

##### Requerimientos de accesibilidad

Especificar los requerimientos asociados a la accesibilidad del sistema.
Dependiendo del problema y el producto, este tipo de requerimientos puede ser
más necesario.

##### Requerimientos de protección crítica

Detallar los requerimientos que cuantifican el riesgo de daño percibido a
personas, propiedad y entorno. Estos pueden estar relacionados a estándares de
seguridad o protección.

#### Requerimientos de *performance*

En esta subsección se especifican los requerimientos relacionados al rendimiento
esperable del producto.

##### Requerimientos de velocidad y latencia

Detallar la cantidad de tiempo disponible para el producto al realizar
diferentes tareas. Un ejemplo de latencia: "El sistema deberá responder a
cualquier interacción en un tiempo menor a dos segundos". Un ejemplo de
velocidad: "El sistema deberá refrescar el estado de cuenta cada 5 minutos".

##### Requerimientos de precisión

Especificar los requerimientos asociados a la precisión de los resultados
mostrados por el producto, por ejemplo: "El sistema deberá mostrar las unidades
monetarias con una precisión de tres decimales".

##### Requerimientos de confiabilidad y disponibilidad

<!-- TODO Mencionar MTBF, MTTF y SLA, agregarlos bajo la carpeta de Conceptos y
referenciarlos -->

Definir los requerimientos de confiabilidad y disponibilidad del sistema, esto
es: ¿qué tanto tiempo deberá estar disponible el sistema? ¿en qué momentos del
día o qué días ha de estarlo? ¿qué porcentaje de tiempo de actividad deberá
cumplir? ¿qué tasa de fallos del sistema es aceptable?

##### Requerimientos de robustez

Indicar los requerimientos de robustez del sistema, esto es, la capacidad del
sistema de continuar funcionando de forma aceptable bajo condiciones anormales.
Por ejemplo: "El sistema deberá seguir proveyendo la funcionalidad X al no tener
conexión a Internet".

##### Requerimientos de capacidad

Especificar la cantidad de volumen de datos o usuarios que el sistema deberá
soportar. ¿Qué tantos usuarios en simultáneo deberá soportar el sistema? ¿este
número cambia para determinado momento del día?

##### Requerimientos de escalabilidad

Detallar aquellos requerimientos relacionados a la escalabilidad del sistema.

##### Requerimientos de longevidad

Especificar los requerimientos que definen la longevidad del producto, esto es,
la cantidad de tiempo que estará operativo.

#### Requerimientos operacionales y de entorno

##### Requerimientos de entorno físico

Detallar los requerimientos del entorno físico en el cual el sistema operará.

En algunos productos, las diferentes condiciones especiales bajo las que operará
el sistema generan requerimientos que se deben tener en cuenta.

##### Requerimientos de interfaz con sistemas adyacentes

Definir los requerimientos que establecen las interacciones necesarias entre el
sistema y otras aplicaciones o software. Tener en cuenta el versionado del
software con el cual el sistema va a interactuar, por ejemplo: "El sistema
deberá poder utilizar datos de la aplicación X en su versión 4.0".

##### Requerimientos de distribución

Indicar los requerimientos necesarios para que el sistema sea distribuido o
vendido como producto. Indicar también las tareas necesarias para que sea
instalado, en caso de ser pertinente. Por ejemplo: "La aplicación debe ser
distribuida en la App Store y Google Play Store en Uruguay" o, "La aplicación
debe ser descargable desde el sitio web de la organización".

##### Requerimientos del ciclo de *releases*

En caso de establecer con el cliente un ciclo de releases durante un determinado
período, indicarlo aquí como un requerimiento.

#### Requerimientos del sistema

Definir todos los requerimientos de sistema necesarios para soportar la
aplicación. Esto puede incluir plataformas de sistemas operativos, de redes,
configuraciones, memoria, periféricos y software adicional necesario.

#### Requerimientos de mantenimiento y soporte

##### Requerimientos de mantenimiento

Especificar aquellos requerimientos relacionados al mantenimiento del sistema
por parte de los usuarios finales, administradores e incluso otros futuros
desarrolladores. Por ejemplo: "El código debe ser escrito en inglés para que sea
legible internacionalmente" o, "Un administrador de la aplicación debe ser capaz
de agregar un recurso X en menos de 15 minutos para que sea visible por los
usuarios" o, "Se debe entregar junto al producto un documento con notas de
arquitectura del sistema que explique cómo está estructurado".

##### Requerimientos de soporte

En caso de que el sistema incluya soporte o ayuda en línea de alguna forma
específica —un chatbot, por ejemplo—, detallarlo aquí mediante requerimientos.
En caso contrario, indicarlo.

##### Requerimientos de adaptabilidad

Especificar los entornos o plataformas que el sistema deberá soportar, por
ejemplo: "El sistema deberá ser capaz de correr en Android y iOS".

##### Manual de usuario

Describir el propósito y contenido del manual de usuario: extensión, nivel de
detalle, índices, glosarios, etcétera. Si hay restricciones de formatos o de
impresión, indicarlo.

En caso de que no haya manual de usuario, indicarlo.

##### Guías de instalación y configuración

En una solución completa se debe incluir documentos con las instrucciones de
instalación y configuración. Establecer aquí los requerimientos para esos
documentos.

#### Requerimientos de seguridad

##### Requerimientos de acceso

Detallar quiénes tienen acceso a las diferentes partes del producto (tanto en
términos de funcionalidades como en términos de datos) y bajo qué
circunstancias.

##### Requerimientos de integridad

Especificar la integridad requerida por la base de datos, archivos del sistema y
el sistema en sí mismo. Por ejemplo: "El sistema deberá prevenir el ingreso de
datos incorrectos" o, "El sistema deberá protegerse a sí mismo del uso
malintencionado".

##### Requerimientos de privacidad

Describir aquellos requerimientos que definen qué debe hacer o con qué debe
cumplir el sistema para asegurar la privacidad de los datos compartidos por los
usuarios. Por ejemplo: "El sistema debe notificar a los usuarios sobre el uso
de sus datos personales" o, "El sistema debe notificar sobre cambios en la
política de privacidad de los datos".

##### Requerimientos de auditoría

Especificar lo que el sistema debe de hacer (usualmente, mantener información
persistida) para permitir controles de auditoría. Por ejemplo: "El sistema debe
mantener datos sobre X para que sean auditados periódicamente".

##### Requerimientos de inmunidad

Mencionar qué es lo que tiene que hacer el sistema para protegerse de
infecciones de software como viruses, gusanos, *malware*, *spyware*, etcétera.

#### Requerimientos culturales

Especificar los requerimientos de carácter sociológico que afectan la
aceptabilidad del sistema. Estos son de particular interés al desarrollar un
sistema para el mercado extranjero. Por ejemplo: "El sistema deberá ser capaz de
distinguir entre el enumerado de calles utilizado en Italia e Inglaterra", o,
"El sistema deberá contemplar los feriados de la Unión Europea".

#### Requerimientos legales

##### Requerimientos de cumplimiento normativo

Detallar los requerimientos asociados a normas y regulaciones que el proyecto y
tú como desarrollador del sistema deberán cumplir.

##### Requerimientos de estándares aplicables

Detallar los estándares con los cuales el producto deberá cumplir, si los hay.
Por ejemplo, legales (FDA, UCC), de comunicaciones, de compatibilidad con
plataformas, calidad y seguridad (UL, ISO, CMM).

[^1]: Evans, E. (2003). Domain-Driven Design. Addison-Wesley Professional.