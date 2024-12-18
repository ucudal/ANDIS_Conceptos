# 2 Técnicas y herramientas

## 2.4 Modelos de comportamiento

### 2.4.4 Diagramas BPMN

BPMN significa *business process model and notation* —modelado y notación de
procesos del negocio—. Es un estándar para el modelado de procesos del negocio
que provee una notación gráfica similar a los [diagramas de actividades
UML](/2_Tecnicas_y_herramientas/2_4_1_Diagramas_de_actividades_UML.md).

Este documento está basado en BPMN 2.0.2[^1].

El objetivo de BPMN es dar soporte a la gestión de los procesos del negocio,
pero también proveer una correspondencia entre los gráficos de la notación y las
construcciones subyacentes de los lenguajes utilizados por herramientas de
automatización de procesos como WS-BPEL[^2].

Los diagramas BPMN tienen típicamente los siguientes elementos gráficos:

* **Objeto de flujo**: evento, actividad, pasarela —*gateways*—.

* **Datos**: objeto de datos, entrada de datos, salida de datos,
  almacenamiento de datos.

* **Objeto conector**: flujo de secuencia, flujo de mensajes, asociación,
  asociación de datos.

* **Andarivel**: piscinas y carriles.

Un evento es algo que sucede durante el curso de un proceso o una coreografía.
Estos eventos afectan el flujo del modelo y generalmente tienen una causa
—desencadenante— o un impacto —resultado—. Los eventos se representan con
círculos con centros en blanco para permitir agregar marcadores en el interior
para diferenciar diferentes desencadenantes o resultados. Hay tres tipos de
eventos, según cuándo afectan el flujo: inicio, intermedio y final.

<a id="figura-1"/>

![Eventos de inicio, intermedio y final](/diagrams/BPMN_Diagram_Events.svg)

*Figura 1: Eventos de inicio, intermedio y final.*

Una actividad es un término genérico para el trabajo que realiza el negocio en
un proceso. Una actividad puede ser atómica o no atómica —compuesta—. Los tipos
de actividades que forman parte de un modelo de procesos son sub-procesos y
tareas, que se representan con rectángulos redondeados. Las actividades se
utilizan tanto en procesos estándar como en coreografías.

<a id="figura-2"/>

![Tareas y sub-procesos](/diagrams/BMPN_Diagram_Activities.svg)

*Figura 2: Tareas y sub-procesos.*

Una pasarela —*gateway*— se utiliza para controlar la divergencia y convergencia
de los flujos de secuencia en un proceso y en una coreografía. Por lo tanto,
determinará la ramificación —*branch*—, bifurcación —*fork*—, fusión —*merge*— y
unión —*join*— de caminos. Los marcadores internos indicarán el tipo de
comportamiento.

<a id="figura-3"/>

![Algunas pasarelas](/diagrams/BPMN_Diagram_Gateways.svg)

*Figura 3: Algunas pasarelas.*

Algunos tipos de pasarelas son:

* Pasarela exclusiva —XOR—: Crea caminos alternativos en un flujo de proceso. En
  una pasarela usada como ramificación, una expresión está asociada a los flujos
  de secuencia de salida; el flujo de control pasará por aquél en que la
  expresión sea verdadera; las condiciones son excluyentes —no pueden ser todas
  verdaderas a la vez—; puede haber un flujo sin expresión, que se tomará si no
  se cumple ninguna de las otras expresiones. Cuando esta pasarela es usada como
  fusión, combina el flujo de control previamente separado en ramas por una
  pasarela exclusiva.

* Pasarela inclusiva —OR—: Crea caminos alternativos o paralelos en un flujo de
  proceso. En una pasarela usada como ramificación, una expresión está asociada
  a los flujos de secuencia de salida; el flujo de control pasará en paralelo por
  todas los flujos de secuencia cuyas condiciones se cumplan; puede haber un
  flujo de secuencia sin expresión, que también se ejecuta en paralelo. Cuando
  esta pasarela es usada como fusión, combina el flujo previamente separado por
  una pasarela inclusiva.

* Pasarela paralela: Crea caminos paralelos en un flujo de procesos. En una
  pasarela usada como bifurcación, todos los flujos de salida se ejecutan en
  paralelo. Cuando esta pasarela es usada como unión, combina el flujo
  previamente separado en ramas paralelas.

* Pasarela compleja: Análoga a la inclusiva pero con un estado interno que
  indica si fue activado o si fue reiniciado.

Los flujos de secuencia se utilizan para mostrar el orden en el que se realizan
las actividades en un proceso o en una coreografía.

<a id="figura-4"/>

![Algunos flujos de secuencia](/diagrams/BPMN_Diagram_Sequence_Flows.svg)

*Figura 4: Algunos flujos de secuencia.*

Algunos tipos de flujos de secuencia son:

* Flujo normal: Refiere a caminos de flujo de secuencia que no comienzan desde
  un evento intermedio adjunto al límite de una actividad. Estos flujos se
  representan con una flecha.

* Flujos no controlados: Refiere al flujo que no se ve afectado por ninguna
  condición o que no pasa a través de una pasarela; por ejemplo, un flujo de
  secuencia que conecta dos actividades. También puede aplicarse a múltiples
  flujos de secuencia que convergen o divergen de una actividad.

* Flujo condicional: Un flujo de secuencia puede tener una expresión de
  condición que se evalúa en tiempo de ejecución para determinar si se utilizará
  o no el flujo de secuencia. Cuando el flujo condicional sale de una actividad,
  tendrá un pequeño diamante al comienzo del conector; no tiene ningún símbolo
  adicional si sale de una pasarela.

* Flujo predeterminado: Para puertas de enlace exclusivas basadas en datos o
  puertas de enlace inclusivas, un tipo de flujo es el flujo de condición
  predeterminado —sin expresión asociada—. Este flujo se utilizará solo si el
  resto del flujo condicional saliente no es verdadero en tiempo de ejecución.
  Estos flujos de secuencia tendrán una barra diagonal que se agregará al
  comienzo del conector.

* Flujo de excepción: Este flujo ocurre fuera del flujo normal del proceso y se
  basa en un evento intermedio adjunto al límite de una actividad que ocurre
  durante la ejecución del proceso.

* Flujo de mensaje: Se utiliza para mostrar el flujo de mensajes entre dos
  participantes que están preparados para enviarlos y recibirlos en una
  colaboración.

[^1]: OMG. (2013). Business Process Model and Notation (BPMN). Disponible
    [aquí](https://www.omg.org/spec/BPMN/2.0.2/PDF).
[^2]: OASIS. (2007). Web Services Business Process Execution Language Version
    2.0. Disponible
    [aquí](http://docs.oasis-open.org/wsbpel/2.0/wsbpel-v2.0.pdf).
