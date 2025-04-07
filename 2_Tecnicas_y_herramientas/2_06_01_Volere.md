# 2 Técnicas y herramientas

## 2.6 Modelos de proceso

### 2.6.1 Volere

Los [requerimientos](/4_Conceptos/4_Requerimiento.md) definen la esencia de lo
que es y de lo que hace un producto o servicio. Existen independientemente de si
se descubren y de si se documentan o no. El verdadero objetivo del análisis de
requerimientos no es producir documentación, sino entender una necesidad del
negocio y diseñar una solución apropiada para ella. Volere[^1] es un proceso ‑que
puede ser utilizado junto con otros *frameworks* de proceso‑ para descubrir,
verificar y documentar requerimientos[^2].

[^1]: Volere es el término en italiano para ≪desear≫ o ≪querer≫.

[^2]: Robertson, S. & Robertson, J. (2012). Mastering the Requirements Process:
Getting Requirements Right, 3<sup>rd</sup> Edition. Addison-Wesley Professional.

La [Figura 1](#figura-1), a continuación, muestra una representación gráfica del
proceso de requerimientos.

<span id="figura-1"/>

![El proceso de requerimientos de Volere](/diagrams/Volere.svg)

*Figura 1: El proceso de requerimientos Volere*. Adaptado de [^2].

Algunas actividades ‑no necesariamente secuenciales‑ de este proceso son:

* **Lanzamiento del proyecto**. El lanzamiento del proyecto establece las bases
  para posteriormente descubrir los requerimientos y asegura que todos los
  elementos esenciales para el éxito del proyecto estén disponibles. Los
  principales interesados ‑incluyendo el patrocinador, los usuarios clave, el
  analista líder de requerimientos y expertos técnicos y de negocio‑ se reúnen
  para alcanzar acuerdos sobre los aspectos más importantes del proyecto.

  El lanzamiento del proyecto determina el alcance del problema del negocio y
  busca que los [interesados](/4_Conceptos/4_Interaccion.md) coincidan en
  identificar el área de la organización que requiere mejoras. Durante la
  reunión de lanzamiento se confirma qué funcionalidad será incluida en el
  proceso de descubrimiento de requerimientos y cuál será específicamente
  excluida.

  Un [diagrama de contexto](/2_Tecnicas_y_herramientas/2_01_02_Diagramas_de_contexto.md)
  se utiliza para generar un consenso entre los interesados sobre el alcance del
  [trabajo](/4_Conceptos/4_Trabajo_y_area_de_trabajo.md) que se debe mejorar. El
  producto final se utilizará para realizar parte de este trabajo.

* **Relevar los requerimientos**. Los analistas comienzan a relevar[^3] el
  trabajo para aprender y comprender su funcionalidad, fundamentalmente entender
  qué está pasando con la parte del negocio involucrada y qué se está buscando
  resolver. Para mayor comodidad y consistente, dividen el diagrama de contexto
  de trabajo en [casos de uso del
  negocio](/4_Conceptos/4_Caso_de_uso_del_negocio.md).

  Cada caso de uso del negocio es la funcionalidad que necesita el trabajo para
  dar la respuesta correcta a un [evento del
  negocio](/4_Conceptos/4_Evento_del_negocio.md).

  Los analistas utilizan técnicas de relevamiento tales como *apprenticing*,
  *shadowing*, escenarios, talleres de casos de uso y muchas otras para
  descubrir la verdadera naturaleza del trabajo.

  En el relevamiento de requerimientos el mayor desafío radica en identificar la
  verdadera esencia del sistema. Los interesados suelen comunicar sus deseos
  enfocándose en soluciones específicas que tienen en mente o basándose en cómo
  funcionan las cosas actualmente. Sin embargo, lo verdaderamente importante es
  entender el propósito básico del negocio que justifica la existencia del
  producto. Este propósito puede verse como el principio operativo esencial, o
  cómo funcionaría el [trabajo](/4_Conceptos/4_Trabajo_y_area_de_trabajo.md) o
  la regla de negocio si pudiera existir independientemente de cualquier
  tecnología ‑incluyendo las personas‑.

  Después de comprender la naturaleza fundamental del trabajo los analistas
  establecen reuniones con los principales interesados para determinar el mejor
  producto que mejorará ese trabajo. Durante este proceso evalúan qué aspectos
  del trabajo requieren automatización o modificación y analizan el impacto que
  estas modificaciones tendrán en el funcionamiento general. Una vez definidos
  los límites y el alcance del producto, los analistas proceden a documentar
  formalmente los requerimientos correspondientes.

[^3]: Los autores de [^1] utilizan el término *trawling* que significa ≪buscar
    entre una gran cantidad de información o un gran número de personas, de
    lugares, etc. buscando una cosa o persona en particular≫ y también ≪pescar
    con una red de arrastre≫.
    [Fuente](https://www.oxfordlearnersdictionaries.com/us/definition/english/trawl_1?q=trawling)

* **Hacer prototipos**. Aunque los modelos pueden ser usados en cualquier etapa
  de este proceso y existen modelos formales como los diagramas
  [UML](/2_Tecnicas_y_herramientas/2_04_02_Diagramas_de_casos_de_uso_UML.md) o
  [BPMN](/2_Tecnicas_y_herramientas/2_04_04_Diagramas_BPMN.md), muchas veces los
  analistas pueden hacer un uso productivo de *sketches* y diagramas rápidos
  para modelar el trabajo que se está investigando.

  > [!TIP]
  > Puedes ver estos artículos en el sitio de Figma sobre [prototipos de baja
  > fidelidad](https://www.figma.com/resource-library/low-fidelity-prototyping/)
  > y [prototipado
  > rápido](https://www.figma.com/resource-library/what-is-rapid-prototyping/) y
  > esta [lista de recursos](https://sketchbook.cpsc.ucalgary.ca/?page_id=197)
  > sobre *skecthing* de la Universidad de Calgary.

  Un prototipo es un modelo funcional utilizado para obtener retroalimentación
  preliminar sobre el producto esperado antes de construirlo[^4].

  [^4]: PMI. (2021). A Guide to the Project Management Body of Knowledge (PMBOK
    Guide)‑7<sup>th</sup> Edition and The Standard for Project Management.
    Project Management Institute, Inc.

* **Escenarios**. Los escenarios muestran la funcionalidad de un proceso de
  negocio dividiéndolo en una serie de pasos fácilmente reconocibles, escritos
  en lenguaje natural para que sean accesibles a todos los interesados. Una vez
  acordados, los escenarios se convierten en la base de los requerimientos.

  > [!TIP]
  > Existe una [plantilla](/3_Plantillas/3_2_Escenario.md) para escribir los
  > escenarios.

* **Escribir los requerimientos**. Un problema en el desarrollo de software es
  la falta de comprensión de los requerimientos. Para mitigar este problema los
  analistas deben redactar los requerimientos de manera no-ambigua y
  comprobable, asegurándose de que tanto las partes interesadas que originan los
  requerimientos como los desarrolladores que los implementan puedan tener una
  comprensión idéntica de lo que se necesita.

  > [!TIP]
  > Existe una [plantilla](/3_Plantillas/3_1_Requerimiento_atomico.md) para
  > escribir los requerimientos.

* **Portal de calidad**. Los requerimientos constituyen la base sobre la que se
  construye todo el resto de un producto de software: si los requerimientos no
  son correctos, el producto tampoco será correcto. Por eso es crucial que los
  requerimientos sean precisos, completos y estén correctamente definidos antes
  de que sean implementados por los desarrolladores. Entre otras cosas esto
  implica:

  * **Comprobar la consistencia**. Asegurarse de que no existan contradicciones
    entre los diferentes requerimientos.

  * **Comprobar la completitud**. Confirmar que se han cubierto todas las
    necesidades y funcionalidades esperadas del producto.

  * **Analizar la factibilidad**. Evaluar si los requerimientos son técnica y
    económicamente realizables.

  * **Revisar la claridad**. Garantizar que cada requerimiento está expresado de
    manera no-ambigua y de forma que sea comprensible para todos los
    interesados.

  * **Trazabilidad**. Comprobar que cada requisito pueda ser rastreado hasta su
    origen ‑hasta la necesidad del usuario o requerimiento del negocio‑.

  > [!IMPORTANT]
  > Esta lista aparece en [^2] y se incluye aquí por completitud. Una lista más
  > completa de los atributos de calidad de los requerimientos se incluye en la
  > [*checklist* de
  > requerimientos](/2_Tecnicas_y_herramientas/2_01_04_Checklist_requerimientos.md).

* **Reutilizar requerimientos**. Los requerimientos para un producto nunca serán
  completamente originales. Antes de iniciar un nuevo proyecto es recomendable
  examinar las especificaciones documentadas en proyectos previos y buscar
  elementos que potencialmente puedan ser reutilizados. Algunas veces existirán
  requerimientos que podrán ser aprovechados sin necesidad de ser modificados,
  aunque la mayoría de las veces los requerimientos existentes ajustarán
  exactamente a lo que se busca, pero pueden servir como punto de partida para
  algunos de los requerimientos del proyecto.

  Muchos de los [requerimientos
  no-funcionales](/4_Conceptos/4_Requerimiento_no_funcional.md) en una
  organización son bastante estándar, por lo que son un buen punto de partida en
  un nuevo proyecto.

  El motivo para reutilizar requerimientos es que, una vez que un requerimiento
  se ha especificado con éxito para un producto y el producto en sí es exitoso,
  no es necesario reinventar ni redescubrir el requerimiento.

* **Revisar los requerimientos**. El portal de calidad antes mencionado funciona
  como un filtro para evitar que requerimientos incorrectos se incluyan en la
  especificación, evaluándolos uno por uno. Al completar la especificación de
  todos los requerimientos ‑o los suficientes como para pasar a la siguiente
  etapa‑ es necesario realizar una revisión integral. Esta revisión final tiene
  como objetivo verificar la integridad de los requerimientos, asegurar su
  coherencia mutua y confirmar que se han resuelto todos los conflictos
  existentes. En esencia, esta revisión valida que la especificación está
  verdaderamente completa y lista para avanzar a la siguiente etapa del
  desarrollo.

  Esta revisión también proporciona la oportunidad de volver a evaluar los
  costos y los riesgos del proyecto. Con un conjunto completo de requerimientos,
  la comprensión del producto es mucho más profunda que al inicio del proyecto,
  en particular, se logra un entendimiento más preciso del alcance y de la
  funcionalidad del producto, lo que hace que este momento sea ideal para
  evaluar nuevamente su tamaño. Con ese resultado, más el conocimiento de las
  restricciones del proyecto y la arquitectura de la solución, se puede realizar
  una estimación más precisa del costo de desarrollo.

  > [!NOTE]
  > La justificación puede encontrarse en el llamado ≪cono de incertidumbre≫,
  > que muestra que la estimación del tamaño ‑y en consecuencia el tamaño y el
  > costo de un proyecto de software tiene menor margen de error a medida que el
  > proyecto avanza. Mientras que al inicio de un proyecto esas estimaciones
  > pueden ser entre 25% a 400% del valor real, al finalizar el análisis de
  > requerimientos el marge de error se reduce a entre un 67% y un 150%[^5].

  A esta altura también hay una mejor perspectiva sobre qué tipos de
  requerimientos conllevan mayores riesgos, permitiendo obtener una visión más
  realista de las probabilidades de crear exitosamente el producto deseado.

[^5]: McConnell, S. (2006). Software Estimation: Demystifying the Black Art.
    Microsoft Press.

#### Enfoque tradicional en cascada versus iterativo

Un malentendido frecuente en el contexto de análisis de requisitos es la
creencia de que es necesario recopilar todos los requerimientos antes de avanzar
hacia las fases de diseño y construcción. En otras palabras, hay quienes piensan
que trabajar con requerimientos implica necesariamente seguir un proceso
tradicional en cascada. Si bien esto es necesario en algunas circunstancias, no
siempre es el caso.

Por un lado, cuando se trabaja con *outsourcing* ‑es decir, cuando se contrata a
un tercero la construcción del producto‑ o cuando el documento de requerimientos
forma parte de un entregable de contrato, claramente se necesita contar con una
especificación completa de requerimientos. Por otro lado, cuando la arquitectura
general ya está definida, con frecuencia es posible comenzar la construcción y
entrega del producto incluso antes de haber descubierto todos los
requerimientos.

#### Recursos

> [!TIP]
> Este sitio sobre [Volere](https://www.volere.org) incluye varios recursos en
> línea que pueden ser útiles.
