# 1 Contenido

## 1.1 Requisitos

El propósito de esta sección es reunir, analizar, definir y especificar las
necesidades del usuario y las funcionalidades del sistema.

### Glosario

Explicar todas las abreviaciones, términos y acrónimos particulares empleados en
el contexto del proyecto y del problema que son utilizados en el documento.

### Posicionamiento del proyecto

Esta subsección da un resumen general del proyecto.

#### Oportunidad de negocio

Describir brevemente la oportunidad de negocio que el cliente trata de alcanzar
con este proyecto, esto es: explicar por qué el negocio del cliente se beneficia
de este proyecto y cómo.

#### Declaración del problema

Sin entrar en detalles, describir el problema que este proyecto intenta resolver.
Opcionalmente se puede utilizar el siguiente formato:

<table>
  <tr><td>El problema</td><td><i>(descripción del problema)</i></td></tr>
  <!-- TODO add link in 'stakeholders' to definition if considered a keyword -->
  <tr><td>Afecta a</td><td><i>(stakeholders afectados)</i></td></tr>
  <tr><td>Cuyo impacto es</td><td><i>(¿cuál es el impacto del problema?)</i></td></tr>
  <tr><td>Una solución exitosa debe tener</td><td><i>(listar algunos beneficios
  clave de una solución exitosa)</i></td></tr>
</table>

#### Declaración del posicionamiento del producto

Dar un resumen general que indique, a alto nivel y sin entrar en detalles,
las características del producto a desarrollar. Algunas cosas a mencionar:

- Organización cliente (opcional, si ya se mencionó antes)

- Categoría del producto y opcionalmente nombre, en caso de tenerlo definido
  **Preguntas disparadoras**: _¿Qué es el producto que voy a desarrollar?_ _¿Cómo
  se llama?_

- Beneficios del producto

- Productos alternativos
  **Pregunta disparadora**: _¿Qué otros productos similares existen actualmente?_

- Diferenciación del producto en comparación con las alternativas
  **Preguntas disparadoras**: _¿Qué tiene de diferente mi producto a desarrollar
  en comparación con las alternativas mencionadas?_ _¿Por qué el cliente no utiliza
  las alternativas?_

#### Objetivos del proyecto

<!-- TODO add links in 'objetivos', 'propósito', 'beneficio' and 'métricas del beneficio'
to definition if considered keywords -->

Mencionar a alto nivel los objetivos del proyecto. Para ello, describir el propósito,
beneficio y métricas del beneficio para cada objetivo.

Se puede usar el siguiente formato:
| Objetivo | Propósito | Beneficio | Métrica del beneficio |
| ------------ | ------------------------------------ | - | -|
| _Título del objetivo_ | _Propósito del objetivo_ | _Beneficio del objetivo_ | _Cuantificación del beneficio_ |
| ... | ... | ... | ... |

### Interesados

<!-- TODO add link in 'interesados' to definition if considered a keyword -->

Esta subsección busca analizar a los interesados en el proyecto. Para ello, se
presenta: el cliente del proyecto, el comprador o consumidor del producto, usuarios
del producto y otros interesados.

#### Cliente del proyecto

<!-- TODO add link in 'cliente' to definition if considered a keyword -->

Mencionar el cliente o clientes del proyecto. Limitarse a mencionar tres como máximo.
Para cada uno mencionar su rol en la organización, rol en el proyecto, perfil técnico,
criterio de éxito (cómo el cliente define el éxito del proyecto o factores clave
para que el cliente considere al proyecto exitoso) y otros comentarios sobre el cliente.

#### Comprador o consumidor del producto

Mencionar el arquetipo del comprador o consumidor del producto. Por ejemplo: Si
el producto a desarrollar fuera una aplicación de gestión de seguimiento de horas
de empleados, el consumidor
podría ser cualquier empresa interesada en hacer un seguimiento de horas de sus empleados.

#### Usuarios

Describir a los usuarios del sistema. Se puede usar el siguiente formato como guía:

<table>
  <tr><td>Descripción</td><td><i>Descripción breve del usuario y la relación que
  tendrá con el sistema.</i></td></tr>
  <!-- TODO add link in 'stakeholders' to definition if considered a keyword -->
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

**Algunas preguntas disparadoras**: _¿Cuántos usuarios tendrá el producto?
¿Cómo se estima que crecerá el número de usuarios? ¿Cuánto dinero gasta el cliente
tratando de satisfacer por otros medios las necesidades que el producto podrá cubrir?_

##### Entornos de los usuarios

Detallar el ambiente de trabajo del usuario objetivo. **Algunas preguntas disparadoras**:

- Número de personas involucradas en la tarea. ¿Es cambiante?

- ¿Cuán extenso es el ciclo de una tarea? ¿Cuánto tiempo se dedica a cada actividad?
  ¿Es cambiante?

- Restricciones ambientales particulares: móviles, exteriores, en vuelo, etc.

- ¿Qué plataformas de sistemas se encuentran en uso actualmente?
  ¿Y plataformas futuras?

- ¿Qué otras aplicaciones están en uso? ¿Precisa esta aplicación ser integrada con
  ellas?

#### Otros interesados

Mencionar otras personas u organizaciones interesadas en el proyecto o afectadas
por él. Estos interesados
pueden formar parte de la organización cliente o trabajar para ella y sus comentarios
pueden ser valiosos para el proyecto, por ejemplo: patrocinadores, expertos del
dominio, usuarios del sistema actual, expertos en legislación, diseñadores, usuarios
encargados del mantenimiento del sistema, encargados del servicio técnico, etcétera.

Para cada uno de ellos, mencionar: rol en el proyecto, rol en la organización,
aporte al proyecto, grado de involucración en el proyecto y nivel de influencia en
el proyecto.

### Identificación de necesidades clave

Listar los problemas clave junto con las soluciones existentes, de acuerdo a la
percepción de los interesados. Aclarar los siguientes elementos de cada problema:

- ¿Cuáles son las razones para este problema?

- ¿De qué manera se lo soluciona ahora?

- ¿Qué soluciones desea el interesado?

Se puede usar el siguiente formato para cada necesidad:

<table>
  <tr><td>Descripción</td><td><i>Breve descripción de la necesidad y sus motivos.</i></td></tr>
  <tr><td>Prioridad</td><td><i>¿Qué nivel de prioridad tiene esta necesidad?</i></td></tr>
  <tr><td>Concierne a</td><td><i>¿A quién concierne esta necesidad?</i></td></tr>
  <tr><td>Solución actual</td><td><i>¿Cuál es la solución actual para esta necesidad?</i></td></tr>
  <tr><td>Solución propuesta</td><td><i>¿Qué solución propone el sistema ante esta
  necesidad?</i></td></tr>
</table>

### Resumen del producto

Esta subsección provee una vista de alto nivel de las capacidades del producto,
interfaces con otras aplicaciones y configuraciones de sistemas.

#### Contexto del producto

Poner al producto en el contexto de la organización cliente y describir su relación
con otros productos relacionados y con el ambiente del usuario. Si el producto es
independiente y totalmente autocontenido, debe ser declarado aquí. Por ejemplo,
si el producto es un componente de un sistema mayor, entonces se debe identificar
las interfaces relevantes entre los sistemas. Una forma sencilla de mostrar los
componentes principales de un sistema mayor, las interconexiones e interfaces externas
es mediante un diagrama de bloques.

#### Resumen de capacidades

Resumir los beneficios y características más importantes que el sistema ha de
proveer.
Por ejemplo, si el sistema en cuestión fuera un sistema de atención al cliente,
en esta parte se abordaría la gestión de documentación de problemas comunes, gestión
de reclamos, telefonistas, etc., sin mencionar la cantidad de detalle que cada
una de estas partes requiere.
Organizar las funciones de forma que la lista resulte comprensible para el cliente
o para cualquier otro que lea el documento por primera vez. Una tabla sencilla
que resuma los beneficios clave y las características que los hacen posibles puede
ser suficiente. Por ejemplo:

| Beneficio para el cliente                                                                                    | Característica que produce el beneficio                                                                                                               |
| ------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| Un nuevo equipo de soporte puede rápidamente ponerse a tono.                                                 | Una base de conocimientos asiste al personal de soporte identificando rápidamente las fallas conocidas y sus soluciones.                              |
| La Administración puede identificar las áreas problema y medir la carga de trabajo del equipo.               | Los reportes de tendencias permiten una vista de alto nivel del estado del problema.                                                                  |
| Los equipos de soporte distribuidos pueden trabajar juntos para resolver problemas.                          | El servidor de replicación permite que la información de la base de datos actual sea compartida a través de la empresa.                               |
| Los clientes se pueden ayudar a sí mismos, bajando los costos de soporte y mejorando el tiempo de respuesta. | La base de conocimientos puede ser habilitada a través de Internet. Incluye capacidades de búsqueda con hipertexto y una máquina de consulta gráfica. |

#### Asunciones y dependencias

Listar los asunciones que, si fueran cambiadas, cambiarían las capacidades del
producto tal como están descritas en este documento. Por ejemplo, una asunción
puede ser que un sistema operativo específico estará disponible para el producto,
de tal forma que si el sistema operativo no está disponible, el documento deberá
ajustarse.

#### Costos y precios

Las características de costo y precio pueden impactar directamente a la definición
e implementación de la aplicación. En esta parte se deben registrar todas las
restricciones de costos y precios que sean relevantes. Por ejemplo, adquisición
de hardware para el sistema.

#### Instalación

Listar las características de instalación, ya que éstas pueden también impactar
directamente al esfuerzo de desarrollo. Por ejemplo, brindar serialización o
seguridad con encriptación requerirá esfuerzos adicionales de desarrollo. Los
requerimientos de instalación también pueden afectar a la codificación, o crear
la necesidad de un software de instalación separado.

#### Alternativas competitivas

Identificar las alternativas que la organización cliente percibe como disponibles.
Éstas alternativas compiten con la realización de este proyecto y pueden incluir
comprar un producto de la competencia, construir una solución internamente o
simplemente mantener el status quo. Listar todas las alternativas competitivas
existentes, o que puedan volverse disponibles, incluyendo los productos existentes
de la competencia. Incluir las debilidades y fortalezas más importantes de cada
una, en el contexto de la organización cliente.

### Restricciones

Esta subsección detalla las diferentes restricciones de diseño o restricciones
externas que se impongan para el desarrollo del producto.

#### Restricciones de diseño y tecnologías

Cada una de las restricciones mencionadas en esta parte debe usar el [template
de requerimiento atómico](../3_Plantillas/3_1_Requerimiento_atomico).

<!-- TODO add link in 'restricciones' to definition if considered a keyword -->

Mencionar las restricciones relacionadas con el diseño de la solución. _(¿La
solución debe ser una aplicación web? ¿debe ser una aplicación mobile? ¿debe
seguir un patrón de arquitectura de software en específico?)_

En caso de existir restricciones sobre las tecnologías a utilizar para el
desarrollo de la solución, detallarlas mencionando —en caso de ser pertinente— la
versión de las mismas.

#### Restricciones de entorno de instalación

Mencionar aquellas restricciones relacionadas el entorno de instalación de la
solución. Estas pueden ser restricciones en cuanto al lugar físico o virtual en
el cual la solución final debe ser instalada.

Suele ser conveniente utilizar un
diagrama para explicar las interacciones del sistema con el entorno y otros
sistemas con los que la solución deba interactuar.

#### Restricciones de utilización de software externo

Utilizando el [template de requerimiento
atómico](../3_Plantillas/3_1_Requerimiento_atomico), mencionar las restricciones
existentes sobre la utilización de software externo. Esto es: la obligación de
que la solución se integre con con un software externo específico.

#### Restricciones organizacionales

Utilizando el [template de requerimiento
atómico](../3_Plantillas/3_1_Requerimiento_atomico), detallar aquellas
restricciones provenientes de las políticas de la organización/empresa cliente.

### Rangos de calidad

Definir los rangos de calidad requeridos para características no funcionales,
por ejemplo: rendimiento, robustez, tolerancia a fallos, usabilidad, y características
similares que no se hayan capturado en el conjunto de funcionalidades.

### Precedencia y prioridad

Definir las prioridades de las diferentes funcionalidades del producto.

### Otros requerimientos del producto

Utilizando el [template de requerimiento
atómico](../3_Plantillas/3_1_Requerimiento_atomico), listar todos los estándares
aplicables, requerimientos de plataformas o hardware, requerimientos de
rendimiento y requerimientos ambientales.

#### Estándares aplicables

Listar los estándares con los cuales el producto debe cumplir, si los hay. Por
ejemplo, legales (FDA, UCC), de comunicaciones, de compatibilidad con plataformas,
calidad y seguridad (UL, ISO, CMM).

#### Requerimientos del sistema

Definir todos los requerimientos de sistema necesarios para soportar la aplicación.
Esto puede incluir plataformas de sistemas operativos, de redes, configuraciones,
memoria, periféricos y software adicional necesario.

#### Requerimientos de rendimiento

Indicar los requerimientos de rendimiento, si los hay. Puede incluir características
tales como factores de carga de usuarios, anchos de banda o capacidad de comunicaciones,
precisión, confiabilidad o tiempos de respuesta bajo condiciones de carga variadas.

#### Requerimientos ambientales

Detallar los requerimientos ambientales necesarios, si los hay. Para sistemas de
hardware, estos requerimientos pueden incluir temperatura, humedad, radiación, etc.
Para aplicaciones de software, los factores ambientales pueden incluir condiciones
de uso, ambiente del usuario, disponibilidad de recursos, mantenimiento, recuperación.

### Requerimientos de documentación

Esta subsección describe la documentación que debe ser desarrollada para soportar
una implantación exitosa del sistema.

#### Manual de usuario

Describir el propósito y contenido del manual de usuario: extensión, nivel de
detalle, índices, glosarios, etcétera. Si hay restricciones de formatos o de impresión,
indicarlo.

#### Ayuda en línea

Muchas aplicaciones proveen un sistema de ayuda en línea para asistir al
usuario. La naturaleza de estos sistemas es específica del desarrollo de la
aplicación debido a que combinan aspectos de programación con aspectos de texto
técnico (organización, presentación). En muchos casos, se ha encontrado que el
desarrollo del sistema de ayuda es un proyecto dentro del proyecto, que
beneficia a la administración del alcance y a las actividades de planificación.
Utilizando el [template de requerimiento
atómico](../3_Plantillas/3_1_Requerimiento_atomico), especificar aquí los
requerimientos de ayuda en línea, si los hay.

#### Guías de instalación y configuración

En una solución completa se debe incluir documentos con las instrucciones de
instalación y configuración. Utilizando el [template de requerimiento
atómico](../3_Plantillas/3_1_Requerimiento_atomico), establecer aquí los
requerimientos para esos documentos.
