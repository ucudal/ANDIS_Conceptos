# 4 Conceptos

## Calidad de software

> [!NOTE]
> El contenido de este documento no necesariamente está basado en las últimas
> versiones de las fuentes utilizadas en su redacción original; se aceptan
> [contribuciones](/CONTRIBUTING.md).

La calidad de software es definida como el grado en el que un sistema,
componente, o proceso satisface las expectativas de los clientes o usuarios [^1]
y en cierta medida, está relacionada con la calidad del proceso de desarrollo.

La calidad es difícil de medir en términos absolutos, ya que la satisfacción del
cliente es intangible, y más aún en términos de software, que también es
intangible. En su lugar, se puede determinar la calidad relativa, esto es, la
adecuación de la calidad con respecto a consideraciones pragmáticas. Es difícil
encontrar una definición óptima de la calidad en la que todos los involucrados
estén de acuerdo, pero generalmente hay mayor consenso en que ciertas
características deben estar presentes en los productos de software para lograr
la satisfacción de los requerimientos y de las expectativas de los clientes y
usuarios. Esta calidad relativa se captura habitualmente en un modelo de
calidad, que describe estas características y sus relaciones.

### Modelos de calidad

Los modelos de calidad describen las relaciones entre las características de la
calidad en las que estamos interesados y los atributos que pueden ser observados
directamente. Varios modelos adoptan una estructura jerárquica, con varias
características de la calidad de alto nivel, formadas por sub-características y
componentes, hasta llegar a las medidas de los atributos.

Todos los modelos consideran que la calidad está formada por una combinación de
atributos internos y externos. Los atributos externos son percibidos por los
usuarios, mientras que los internos son percibidos por los desarrolladores, en
el entendido de que la presencia de los atributos internos contribuye a la
presencia de los externos.

#### McCall o FCM

El modelo de McCall o modelo FCM tiene una estructura jerárquica de tres
niveles.

El primer nivel es **uso** y los componentes son **operación del producto**,
**revisión de producto** y **transición del producto**.

El segundo nivel es **factor** y cada **uso** del primer nivel está compuesto
por varios **factores** de este segundo nivel. Por ejemplo, el **uso**
**operación del producto** está compuesto por los **factores**: **facilidad de
uso**, **integridad**, **eficiencia**, **confiabilidad** y **corrección**.

El tercer nivel es **criterio** y cada **factor** del segundo nivel está
compuesto por varios **criterios** de este tercer nivel. A diferencia de lo que
sucede con en el segundo nivel, donde cada **factor** es componente de
exactamente un **uso**, los **criterios** del tercer nivel pueden ser
componentes de más de un **factor**. Por ejemplo, el **factor** **corrección**,
está compuesto por los **criterios** **seguimiento de la traza**,
**consistencia** y **completitud**. Finalmente, para cada **criterio**, existe
una lista de verificación con elementos pertinentes a las etapas de
requerimientos, diseño e implementación. La siguiente tabla muestra la lista de
verificación para el **criterio** **completitud**.

|  | Requerimientos | Diseño | Implementación |
|--|--|--|--|
| Referencias no ambiguas: o son entrada, o salida, o función | Sí | Sí | Sí |
| Todas las referencias de datos están definidas, calculadas, o marcadas como externas | Sí | Sí | Sí |
| Todas las funciones definidas son usadas | Sí | Sí | Sí |
| Todas las funciones referenciadas están definidas | Sí | Sí | Sí |
| Todas las condiciones y el procesamiento están definidos para cada punto de decisión | Sí | Sí | Sí |
| Los parámetros definidos y referenciados en todas las secuencias de llamadas coinciden | No | Sí | Sí |
| Todos los problemas informados están resueltos | Sí | Sí | Sí |
| El diseño coincide con los requerimientos | No | Sí | No |
| El código coincide con el diseño | No | No | Sí |

Para obtener la medida de la calidad, sumamos la cantidad de marcas en la lista
de verificación, la normalizamos al intervalo [0, 1] para obtener la medida de
un **criterio** —tercer nivel—; luego sumamos todos los **criterios** de cada
**factor** para obtener la medida de un **factor** —segundo nivel—; luego
sumamos los **factores** de cada **uso** para obtener la medida de todos los
**usos** —primer nivel—; finalmente sumamos los **usos** para obtener la medida
de la calidad [^2].

La siguiente figura muestra el modelo de calidad de McCall:

![Modelo de calidad de McCall](/diagrams/Quality_Model_McCall.svg)

*Figura 1: Modelo de calidad de McCall.*

#### Boehm

El modelo de calidad de Barry Boehm también es un modelo jerárquico de tres
niveles. El primer nivel es el de los **usos primarios**, el segundo es el de
las **construcciones intermedias** y el tercero es el de las **construcciones
primitivas**. El último nivel, al igual que el modelo de McCall, se obtiene a
través de medidas del software.

La Figura 2, a continuación, muestra el modelo de calidad de Boehm. El nivel de
los **usos primarios** está a la izquierda, el de las **construcciones
intermedias** en el centro y el de las **construcciones primitivas** a la
derecha.

![Modelo de calidad de Boehm](/diagrams/Quality_Model_Boehm.svg)

*Figura 2: Modelo de calidad de Boehm*. [^2]

#### ISO 9126

Los modelos de Boehm y McCall sirvieron de base para el modelo de la norma ISO
9126. Esta norma define calidad como el conjunto de prestaciones y
características de un producto de software en las que se basa su capacidad para
satisfacer necesidades establecidas o implícitas. El modelo tiene seis
**factores**, que a su vez tienen varios **atributos**.

La siguiente figura muestra el modelo de calidad de la norma ISO 9126:

![Modelo de calidad de la norma ISO 9126](/diagrams/Quality_Model_ISO_9126.svg)

*Figura 3: Modelo de calidad de la norma ISO 9126.*

### Normas de calidad y de procesos

La Organización Internacional para la Estandarización —o ISO, por sus siglas en
inglés— y el Instituto de Ingenieros Eléctricos y Electrónicos —o IEEE— son dos
de las organizaciones más importantes en la promulgación de estándares y normas
de calidad y de ingeniería de software. A continuación verán algunos estándares
relevantes desarrollados por estas dos entidades.

#### ISO 9001 e ISO 90003

La familia de normas ISO 9000, referente a sistemas de gestión de calidad, es
probablemente una de las normas de calidad más conocida. Incluye las normas ISO
9000:2000 Sistemas de gestión de calidad – Fundamentos y vocabulario, ISO
9001:2000 Sistemas de gestión de calidad – Requerimientos, e ISO 9004:2000
Sistemas de gestión de calidad – Guías para la mejora del desempeño. Como se
trata de una norma que no es específica para software, existe la norma ISO/IEC
90003:2004 Ingeniería de software – Guía para la aplicación de ISO 9001:2000 al
software.

El objetivo de la norma es “asistir a organizaciones de todo tipo y tamaño en la
implantación y operación de sistemas de gestión de la calidad eficaces”, donde
gestión de la calidad refiere a "las actividades coordinadas para dirigir y
controlar una organización en lo relativo a la calidad" [^3].

La norma está basada en principios de la gestión total de la calidad y en
requisitos del sistema de gestión de la calidad. Los principios son los
siguientes:

* Enfoque al cliente. Las organizaciones dependen de sus clientes y por lo tanto
  deberían comprender las necesidades actuales y futuras de los clientes,
  satisfacer los requisitos de los clientes y esforzarse en exceder las
  expectativas de los clientes.

* Liderazgo. Los líderes establecen la unidad de propósito y la orientación de
  la organización. Ellos deberían crear y mantener un ambiente interno, en el
  cual el personal pueda llegar a involucrarse totalmente en el logro de los
  objetivos de la organización.

* Participación del personal. El personal, a todos los niveles, es la esencia de
  una organización y su total compromiso posibilita que sus habilidades sean
  usadas para el beneficio de la organización.

* Enfoque basado en procesos. Un resultado deseado se alcanza más eficientemente
  cuando las actividades y los recursos relacionados se gestionan como un
  proceso.

* Enfoque de sistema para la gestión. Identificar, entender y gestionar los
  procesos interrelacionados como un sistema contribuye a la eficacia y
  eficiencia de una organización en el logro de sus objetivos.

* Mejora continua. La mejora continua del desempeño global de la organización
  debería ser un objetivo permanente de esta.

* Enfoque basado en hechos para la toma de decisiones. Las decisiones eficaces
  se basan en el análisis de los datos y la información.

* Relaciones mutuamente beneficiosas con el proveedor. Una organización y sus
  proveedores son interdependientes y una relación mutuamente beneficiosa
  aumenta la capacidad de ambos para crear valor.

El siguiente diagrama ilustra un modelo de gestión de la calidad basado en los
procesos de la norma ISO 9000:

![Modelo del sistema de gestión de la calidad basado en los procesos de la norma
ISO 9000](/diagrams/Quality_Management_Model_ISO_9000.svg)

*Figura 4. Modelo del sistema de gestión de la calidad basado en los procesos de
la norma ISO 9000.*

#### CMMI

CMMI [^4] es una versión actualizada del clásico CMM de *Software Engineering
Institute* de *Carnegie Mellon University*. Es un modelo que se basa en el
supuesto de que la calidad de un producto está determinada principalmente por la
calidad del proceso que se usa para desarrollarlo y mantenerlo, por un lado, y
en que la gente no puede desarrollar su máxima capacidad si no entiende el
proceso o si el proceso no está operando a su máxima capacidad, por otro [^5].

CMMI define **proceso** como un conjunto de prácticas desarrolladas para
alcanzar un propósito, que puede incluir herramientas, métodos, materiales y
personas. Un **modelo de proceso**, en cambio, es una colección estructurada de
elementos que describen las características de procesos efectivos; los procesos
incluidos son aquellos que la experiencia ha probado que son efectivos. Un
**modelo de madurez de la capacidad** es un modelo de referencia de prácticas
maduras en una disciplina específica usado para evaluar la capacidad de un grupo
para desempeñar esa disciplina.

Los modelos CMMI y CMM se organizan alrededor de áreas de proceso y niveles de
madurez organizacional. Un **área de proceso** es un grupo de prácticas
relacionadas en un área que, cuando se realizan en conjunto, satisfacen un
conjunto de metas considerado importante para realizar mejoras significativas en
esa área. El **nivel de madurez de una organización** provee una forma de
predecir el desempeño futuro de una organización en una disciplina o conjunto de
disciplinas dadas.

Una de las principales novedades de CMMI respecto al CMM clásico reside en
reconocer que la capacidad en las áreas de proceso y la madurez organizacional
son conceptos similares, pero no iguales. La diferencia radica en que la
capacidad en áreas de proceso trata con un conjunto de procesos relacionados con
una sola área de proceso o práctica específica, mientras que la madurez
organizacional pertenece a un conjunto de áreas de proceso a través de la
organización. Este es el fundamento para las dos representaciones del modelo:

* Continua (CMMI 2002a). Provee un camino para implementar grupos de áreas de
  procesos y una secuencia de implementación en niveles de capacidad.

* Por nivel (CMMI 2002b). Provee máxima flexibilidad para concentrarse en un
  área de proceso específica de acuerdo a las necesidades y objetivos del
  negocio.

##### Representación continua de CMMI

Las áreas de procesos de la representación continua de CMMI son:

* Gestión de procesos. Incluye actividades entre proyectos relacionadas con la
  definición, planificación, provisión de recursos, distribución,
  implementación, monitoreo, control, evaluación, medición y mejora de procesos.

* Gestión de proyectos. Cubre las actividades de gestión de proyectos
  relacionadas con la planificación, monitoreo y control de proyectos.

* Ingeniería. Incluye las actividades de desarrollo y mantenimiento, comunes a
  todas las disciplinas de ingeniería —ingeniería de sistemas e ingeniería de
  software—.

* Soporte. Incluye procesos que son usados en el contexto de la ejecución de
  otros procesos.

Los niveles de capacidad de la representación continua son:

* 0 — Incompleto. Un proceso incompleto es un proceso que no es realizado o es
  realizado parcialmente.

* 1 — Realizado. Un proceso realizado es el que satisface los objetivos del área
  de proceso.

* 2 — Gestionado. Un proceso gestionado es un proceso realizado que se planifica
  y ejecuta de acuerdo con una política; que emplea personas capacitadas, que
  tienen los recursos adecuados para producir productos controlados; que incluye
  los involucrados relevantes; es monitoreado, controlado y revisado; y del que
  se evalúa su adherencia a la descripción del proceso.

* 3 — Definido. Un proceso definido es un proceso gestionado que ha sido
  adaptado del conjunto de procesos estándar de la organización, de acuerdo a
  las guías de adaptación de la organización; y que contribuye con productos de
  trabajo, medidas y otra información para la mejora de los procesos y a los
  activos organizacionales de procesos.

* 4 — Administrado cuantitativamente. Un proceso administrado cuantitativamente
  es un proceso definido, controlado mediante estadística y otras técnicas
  cuantitativas.

* 5 — Optimizado. Un proceso optimizado es un proceso administrado
  cuantitativamente que se cambia y adapta para alcanzar los objetivos
  relevantes, actuales y proyectados del negocio.

##### Representación por nivel de CMMI

Los niveles de madurez de la representación por niveles, del más bajo al más
alto, son:

* 1: Inicial. En el nivel de madurez inicial, los procesos son habitualmente ad
  hoc y caóticos. La organización habitualmente no provee un entorno estable. El
  éxito en estas organizaciones depende de la competencia y de los esfuerzos
  heroicos de la gente en la organización y no del uso de procesos probados. A
  pesar de este entorno ad hoc y caótico, las organizaciones en el nivel de
  madurez inicial producen productos y servicios que funcionan; sin embargo,
  frecuentemente exceden el presupuesto y el calendario de sus proyectos. Las
  organizaciones de nivel de madurez inicial están caracterizadas por una
  tendencia a incumplir, abandonar procesos en tiempos de crisis y no ser
  capaces de repetir sus éxitos pasados.

* 2: Administrado. Al alcanzar este nivel de madurez, los proyectos de la
  organización han asegurado que los requerimientos están administrados y los
  procesos son planificados, desarrollados, medidos y controlados. La disciplina
  en los procesos reflejada en el nivel de madurez administrado, ayuda a
  asegurar que las prácticas existentes se conservan en tiempos de estrés.
  Cuando estas prácticas están en su lugar, los proyectos se desarrollan y
  gestionan de acuerdo con sus planes documentados.

* 3: Definido. En este nivel de madurez los procesos están bien caracterizados y
  comprendidos, descritos en estándares, procedimientos, herramientas y métodos.
  El conjunto de procesos estándar de la organización, que es la base de este
  nivel de madurez, fue establecido y mejorado con el correr del tiempo. Estos
  procesos estándar son usados para establecer consistencia a través de la
  organización. Los proyectos establecen sus procesos definidos, adaptando el
  conjunto de procesos estándar de la organización a través de guías de
  adaptación.

* 4: Administrado cuantitativamente. Cuando la organización alcanza este nivel
  de madurez, sus procesos son controlados usando estadística y otras técnicas
  cuantitativas; ha establecido objetivos cuantitativos para la calidad y el
  desempeño de los procesos y los usa como criterio para la gestión de los
  procesos. Los objetivos cuantitativos están basados en las necesidades de los
  clientes, los usuarios finales, la organización y de quienes llevan adelante
  el proceso.

* 5: Optimizado. En este nivel de madurez los procesos mejoran continuamente
  gracias al entendimiento cuantitativo de las causas comunes de variación
  inherentes a los procesos. La organización se enfoca en la mejora continua del
  desempeño de los procesos. Los objetivos cuantitativos de la mejora de
  procesos para la organización son establecidos, continuamente revisados para
  reflejar los cambios en los objetivos del negocio y usados como criterio en la
  gestión de la mejora de procesos.

### Aseguramiento de la calidad

Las actividades de aseguramiento de la calidad buscan generar confianza en la
calidad de los productos de software, ayudando a construir la calidad tanto en
los productos intermedios como en los productos finales, pero también en los
procesos que los producen.

El aseguramiento de la calidad dirige los procedimientos que construyen la
calidad deseada en los productos, gracias a que asegura que los procesos están
bien planificados y se aplican tal como están definidos. El aseguramiento de la
calidad evita que la organización caiga en hábitos y procesos poco efectivos, al
mismo tiempo que provee asistencia en la aplicación de las prácticas actuales [^6].

Las actividades de aseguramiento de la calidad son las siguientes [^7]:

* Implementación de proceso. Consiste en establecer un proceso de aseguramiento
  de la calidad adaptado al proyecto; establecer un plan de aseguramiento de la
  calidad; realizar las actividades de aseguramiento de la calidad planificadas,
  registrando y gestionando los problemas y no conformidad que surjan; asegurar
  que los responsables tienen libertad para realizar las evaluaciones
  requeridas.

* Aseguramiento del producto. Consiste en documentar y ejecutar planes
  consistentes; en asegurar que los productos y la documentación son tal como
  deben; y en asegurar que los productos son aceptables para el consumidor.

* Aseguramiento del proceso. Consiste en asegurar que los procesos de ciclo de
  vida del software funcionan tal como deben; que las prácticas internas de
  ingeniería de software funcionan tal como deben; que los requisitos del
  contratista se transfieren al subcontratista y los productos del
  subcontratista se transfieren al contratista; que se proporciona al cliente el
  soporte requerido; que las mediciones del producto y del proceso de software
  están de acuerdo a lo previsto; que el personal tiene el conocimiento y la
  habilidad necesarios para cumplir con su tarea.

* Aseguramiento de los sistemas de la calidad. Consiste en asegurar la calidad
  tal como está previsto en la norma ISO 9001:2000.

### Validación y verificación

La validación y la verificación son actividades que se concentran más
específicamente en la calidad del producto. Ambas actividades usan la prueba de
software para localizar desvíos y arreglarlos tanto en los productos finales
como en los intermedios.

La validación es el proceso de evaluar un sistema o componente durante o al
final del proceso de desarrollo para determinar que satisface los requerimientos
especificados [^1]. Asegura que un producto final o intermedio es correcto de acuerdo
a las necesidades del usuario o cliente final. Habitualmente se suele mostrar
que la validación es la respuesta a la pregunta “¿se está construyendo el
producto correcto?”.

El estándar ISO/IEC 12207:1995 establece que las actividades de validación son:

* Implementación del proceso. Consiste en determinar el esfuerzo de validación y
  el grado de independencia requerido; establecer un proceso de validación;
  seleccionar los responsables de realizar la validación, garantizando la
  libertad para realizar las evaluaciones requeridas; establecer un plan de
  validación e implementar el plan de validación tal como está planificado.

* Validación. Consiste en preparar las pruebas; realizarlas; comprobar que el
  producto satisface el uso previsto y probar que el producto es apropiado en el
  entorno destino.
  
La verificación es el proceso de evaluar un sistema o componente para determinar
si los productos de una fase de desarrollo determinada satisfacen las
condiciones impuestas al comienzo de la fase (IEEE 610.12 1990). La verificación
asegura que un producto final o intermedio ha sido desarrollado correctamente de
acuerdo a las especificaciones y estándares. La pregunta detrás de la
verificación es: “¿se está construyendo el producto correctamente?”.

Las actividades de verificación son [^7]:

* Implementación del proceso. Consiste en determinar el esfuerzo de verificación
  y el grado de independencia requerido; establecer un proceso de verificación;
  seleccionar los responsables de realizar la verificación, garantizando la
  libertad para realizar las evaluaciones requeridas; establecer un plan de
  verificación; implementar el plan de verificación tal como está planificado.

* Verificación. Consiste en verificación de contratos, procesos, requisitos,
  diseño, código, integración y documentación.

### Revisiones y auditoría

A diferencia de lo que ocurre habitualmente en ingeniería de software, las
normas ISO 9001:2000 e ISO/IEC 12207:1997 consideran revisión y auditoría como
actividades orientadas a la calidad, pero separadas de las de aseguramiento de
la calidad y de validación y verificación.

La revisión es el proceso tendiente a evaluar el estado y los productos de una
actividad de un proyecto, según sea adecuado. Las revisiones están tanto a nivel
de gestión del proyecto como técnico.

Por otro lado, la auditoría es el proceso que determina el cumplimiento de los
requisitos, planes y contrato, según corresponda.

### Error, falta, falla y equivocación

La falta de calidad se asocia a la presencia de errores. El término **error**
tiene varios significados:

* Una acción humana que produce un resultado incorrecto. El término más preciso
para este significado es **equivocación**.

* Una definición incorrecta en un paso, un proceso, o un dato; un defecto en un
dispositivo o componente. El término más preciso para este significado es
**falta**: la manifestación de una equivocación.

* Un comportamiento o resultado incorrecto. La incapacidad de un sistema o
componente de realizar las funciones requeridas con el desempeño especificado.
El término más preciso es **falla**: el resultado de una falta.

* La diferencia entre un valor o condición calculada, observada, o medida y el
valor o condición verdadera, especificada o teórica. El término adecuado es
**error**: la cantidad por la que el resultado es incorrecto.

### Prueba y depuración

La presencia de errores suele ser detectada realizando pruebas y depuración. La
prueba de software es el proceso de analizar una pieza de código para descubrir
errores, es decir, para detectar diferencias entre las condiciones existentes y
las requeridas [^8]. La depuración, en cambio, es el proceso de detectar, localizar,
y corregir faltas.

Las técnicas para las pruebas se pueden agrupar de diversas maneras:

* Según el objeto de la prueba:

  * Dinámicas. El objeto de la prueba es un componente ejecutable.

  * Estáticas. El objeto de la prueba es código fuente o un documento.

* Según la etapa del proceso:

  * De unidad. El objeto de la prueba es un componente o una clase.

  * De integración. El objeto de la prueba es un módulo, un paquete, o una
    prestación completa.

  * De aceptación. El objeto de la prueba es una aplicación completa.

* Según la visibilidad el objeto probado:

  * Caja blanca. Conocemos los detalles internos del objeto probado.

  * Caja negra. No conocemos los detalles internos del objeto probado.

Algunas técnicas para la depuración son:

* *Breakpoints*. Es un punto en un programa de computadora en el cual se puede
  suspender la ejecución para permitir el monitoreo automático o manual de los
  resultados o el desempeño del programa.

* Prueba de escritorio. Es una técnica de análisis estático en la cual se
  examina visualmente listados del código, resultados de las pruebas, u otra
  documentación, habitualmente por la persona que los generó para identificar
  errores, incumplimiento de estándares de desarrollo, u otros problemas.

* Descargas. Consiste en desplegar algún aspecto del estado de la ejecución de
  un programa, habitualmente el contenido del almacenamiento interno.

* Inspección. Es una técnica de análisis estático que depende del examen visual
  de los productos de desarrollo para detectar errores, incumplimientos de
  estándares de desarrollo, u otros problemas.

* Operación paso-a-paso. Es una técnica de depuración que consiste en ejecutar
  una sola instrucción, o parte de una instrucción, en respuesta a una señal
  externa.

* Trazas. Registro de la ejecución de un programa, que muestra la secuencia de
  instrucciones ejecutadas, los nombres y valores de las variables, o ambos;
  además del análisis de ese registro.

[^1]: IEEE 610.12. IEEE STD 610.12-1990 IEEE Standard Glossary of Software
Engineering Terminology. IEEE Standards Collection Software Engineering. The
Institute of Electrical and Electronics Engineers, Inc.; 1990.

[^2]: Fenton, Norman and Pfleeger, Shari. Software Metrics: A Rigorous &
Practical Approach. PWS Publishing Company; 1997.

[^3]: ISO 9000. UNIT-ISO 9000:2000 Sistemas de gestión de la calidad -
Fundamentos y vocabulario. Instituto Uruguayo de Normas Técnicas; 2000.

[^4]: Capability Maturity Model® Integration (CMMISM): Continuous
Representation. Carnegie Mellon University, Software Engineering Institute;
2002a Mar; CMU/ SEI-2002-TR-011.

[^5]: Phillips, Mike, CMMISM Program Manager. CMMISM 1.1 Tutorial. Carnegie
Mellon University, Software Engineering Institute; 2003.

[^6]: SWEBOK. Guide to the software engineering body of knowledgeAbran, Alain
and Moore, James, Executive Editors: IEEE Computer Society; 2001.

[^7]: ISO/IEC 12207. ISO/IEC 12207:1995 Information Technology - Software
lifecycle processes. International Organization for Standarization &
International Electrotechnical Commission; 1995.

[^8]: IEEE 829. ANSI/IEEE STD 829-1983 ANSI/IEEE Standard for Software Test
Documentation. IEEE Standards Collection Software Engineering. The Institute of
Electrical and Electronics Engineers, Inc.; 1983.
