# 4 Conceptos

## Escenario de usuario

Los **escenarios de usuario** son relatos breves y concretos que describen cómo
una [persona](/2_Tecnicas_y_herramientas/2_01_.Relevamiento/2_01_03_Personas.md)
intenta alcanzar un objetivo específico en una situación realista, interactuando
con un producto o servicio, por ejemplo, en un [*customer journey
map*](/2_Tecnicas_y_herramientas/2_01_.Relevamiento/2_01_05_Customer_journey_map.md)
[^1].

[^1]: IxDF-Interaction Design Foundation. (2016, June 3). What are User
    Scenarios? IxDF-Interaction Design Foundation. Disponible
    [aquí](￼https://www.interaction-design.org/literature/topics/user-scenarios).

No describen ≪cómo funciona el sistema≫, sino ≪qué está viviendo y tratando de
lograr la persona≫, en contexto. Conectan decisiones técnicas y de negocio con
necesidades, motivaciones y limitaciones reales de los usuarios.

> [!NOTE]
> Usamos ≪escenario de usuario≫ para diferenciarlo de [≪escenario de caso de
> uso≫](./4_Escenario_de_caso_de_uso.md), aunque en [^1] y [^2] se utiliza
> simplemente ≪escenario≫.

[^2]: IxDF-Interaction Design Foundation. (2020, July 31). Design
    Scenarios-Communicating the Small Steps in the User Experience.
    IxDF-Interaction Design Foundation. Disponible
    [aquí](https://www.interaction-design.org/literature/article/design-scenarios-communicating-the-small-steps-in-the-user-experience).

Un escenario de usuario describe lo que un usuario hace —o debería poder hacer—,
en forma de una narrativa, e incluye[^1][^2]:

* Quién es el participante; por ejemplo, a partir de una
  [persona](/2_Tecnicas_y_herramientas/2_01_.Relevamiento/2_01_03_Personas.md).

* Qué objetivo quiere lograr.

* En qué contexto lo hace: qué dispositivo, dónde lo hace, en qué momento lo
  hace, organización, normas, etc.

* Qué pasos sigue, qué decisiones toma y qué obstáculos encuentra.

* Cómo responde el producto o servicio en cada paso.

Es una descripción suficientemente detallada de lo que hace un usuario en
situaciones realistas y relevantes para el diseño de una solución, que permiten
entender las necesidades y comportamientos prácticos de los usuarios en el
contexto.

Los escenarios utilizan lenguaje cotidiano y sitúan la acción en un entorno
concreto, lo que facilita la empatía y el diálogo entre los interesados del
negocio y los analistas del negocio.

Los escenarios de usuario permiten[^1][^2]:

<!-- cSpell:words frontstage https://www.oed.com/dictionary/frontstage_n -->
<!-- cSpell:words touchpoints https://www.oed.com/dictionary/touchpoint_n -->
<!-- cSpell:words wireframes https://www.oed.com/dictionary/wireframe_adj -->

1. Entender y comunicar la experiencia: por qué la persona hace lo que hace,
  cuáles son los ≪puntos de dolor≫ —*pain points*—; los interesados logran una
  visión compartida más clara de la experiencia deseada.

2. Soportar el diseño de —interfaces de— productos y servicios: ayudan a
  describir la secuencia de interacción entre *frontstage* —lo que ve el
  usuario— y *backstage* —lo que ocurre dentro de la organización—; en
  combinación con los [customer journey
  maps](/2_Tecnicas_y_herramientas/2_01_.Relevamiento/2_01_05_Customer_journey_map.md)
  muestran la coordinación entre distintos *touchpoints*: sitio web, aplicación
  móvil, call center, tienda física, etc. para lograr una experiencia de usuario
  consistente; son la base para construir mapas de navegación y *wireframes*. Un
  escenario de usuario puede poner de manifiesto condiciones especiales qu ele
  producto o servicio debe contemplar, por ejemplo, accesibilidad.

3. Definir pruebas de facilidad de uso: permiten evaluar si la interfaz del
   producto soportan las tareas clave del escenario, si el flujo se percibe como
   natural y acorde a la situación, y dónde aparecen errores, dudas o desvíos
   respecto al comportamiento esperado.

### Cómo crear escenarios de usuario

A partir de [^1] y [^2], se puede proponer un proceso para crear escenarios:

1. **Preparar el contexto**. Reunir un grupo de idealmente no más de 6 o 7
   interesados clave para el escenario. Definir qué parte del servicio o
   producto se va a explorar. Recopilar
   [personas](/2_Tecnicas_y_herramientas/2_01_.Relevamiento/2_01_03_Personas.md),
   investigación de usuarios, datos de uso, métricas, entrevistas, etc.

2. **Definir la persona y el objetivo**. Identificar para cada escenario cuál es la
   [personas](/2_Tecnicas_y_herramientas/2_01_.Relevamiento/2_01_03_Personas.md)
   involucrada, cuál es su objetivo concreto, y el criterio de éxito: qué
   significa, desde la perspectiva de la persona, que la historia terminó bien.

3. **Describir el contexto**. Identificar qué eventos disparan la necesidad,
   cuál es el entorno físico —lugar, dispositivo, conectividad, posibles
   interrupciones—, si hay otros participantes o influencias —familia,
   compañeros, empleados, etc.— y el entorno organizacional y legal —normativas,
   políticas, horarios, restricciones, etc.—. No se trata de agregar detalles
   decorativos, sino aquello que influye en el comportamiento o en el diseño.

4. **Escribir la historia paso a paso**. Un relato en tiempo
   [presente](https://dle.rae.es/presente?m=form#:~:text=m.%20Gram.%20Forma%20verbal%20que%20corresponde%20al%20presente.%20El%20presente%20de%20indicativo%20de%20cantar%20es%20canto.)
   o [pasado
   simple](https://dle.rae.es/pretérito?m=form#:~:text=compuesto.-,pretérito%20perfecto%20simple,es%20pretérito%20perfecto%20simple.,-pretérito),
   en lenguaje natural, siguiendo la secuencia de acciones y reacciones que
   incluya qué hace la persona, qué espera que ocurra, qué responde el producto
   o servicio, dónde aparecen dudas, fricciones o emociones relevantes.

5. **Identificar puntos clave y oportunidades**. Marcar puntos de dolor y
   riesgos —por ejemplo, pasos donde es probable que la persona abandone o se
   equivoque—, momentos de verdad del servicio —interacciones que definen la
   percepción general—, oportunidades de simplificación, automatización o mejora
   de la experiencia.

### Buenas prácticas al redactar escenarios

Algunas recomendaciones:[^1][^2]

* Mantener el foco en tareas y objetivos clave, no intentar cubrir todas las
  posibles interacciones.

* Ser específico y realista: que la historia pueda ocurrir “de verdad”.
* Evitar describir lo que “debería” hacer el usuario; describir lo que
  probablemente hará.

* Usar lenguaje claro, sin jerga técnica innecesaria, para que cualquier perfil
  del equipo pueda entenderlo.

* Revisar y refinar los escenarios a medida que se obtiene nueva evidencia (por
  ejemplo, resultados de pruebas de usabilidad o nuevas entrevistas).
