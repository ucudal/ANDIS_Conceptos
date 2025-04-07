# 2 Técnicas y herramientas

## 2.2 Arquitectura

### 2.2.3 Ciclo de identificación de componentes

En la medida de que los [componentes](/4_Conceptos/4_Componente.md) representan
un mecanismo genérico para contener código, el código se puede particionar en
componentes de distintas maneras. El ciclo de identificación de componentes [^1]
es un proceso estructurado para descomponer un sistema en componentes
individuales. Estos cinco pasos guían el desarrollo y refinamiento de los
componentes para asegurarse de que estén alineados con los [requerimientos
funcionales](/4_Conceptos/4_Requerimiento_arquitectonicamente_significativo.md)
y los [atributos de calidad](/4_Conceptos/4_Atributo_de_calidad.md).

[^1]: Richards, M.; Ford, N. (2020). Fundamentals of software architecture.
    O'Reilly Media.

<span id="figura-1"/>

![Ciclo de identificación de
componentes](/diagrams/Component_Identification_Cycle.svg)

*Figura 1: Ciclo de identificación de componentes.*

Las etapas del ciclo se definen a continuación.

1. **Identificar los componentes iniciales**. Este es el punto de partida donde
  se toma una vista de alto nivel del sistema y se divide en componentes amplios
  y de gran escala. En esta etapa no es necesario entrar en demasiados detalles
  internos, sino definir la [partición de alto
  nivel](/4_Conceptos/4_Componente.md#partición-de-la-arquitectura-en-componentes)
  ‑tecnológica o por dominio‑.

2. **Asignar requerimientos a los componentes**. Una vez que se han identificado
  los componentes iniciales, se mapean los requerimientos funcionales a estos
  componentes. Esto pueden implicar crear nuevos componentes, consolidar
  componentes existentes, o separar componentes que tienen demasiadas
  responsabilidades.

3. **Analizar roles y responsabilidades**. Al asignar requerimientos funcionales
   a los componentes, el arquitecto también analiza los roles y las
   responsabilidades obtenidos durante el relevamiento de requerimientos para
   asegurarse de que la granularidad coincida. Pensar en los roles y los
   comportamientos que debe admitir la aplicación permite alinear la
   granularidad del componente y del dominio.

4. **Analizar atributos de calidad**. Ahora se asegura que cada componente dé
  soporte las características arquitectónicas, requerimientos no funcionales o
  [atributos de calidad](/4_Conceptos/4_Atributo_de_calidad.md), tales como el
  [rendimiento](/4_Conceptos/4_Rendimiento.md), la
  [seguridad](/4_Conceptos/4_Seguridad.md), la
  [disponibilidad](/4_Conceptos/4_Disponibilidad.md), la [facilidad de
  modificación](/4_Conceptos/4_Facilidad_de_modificacion.md), etc. Las [tácticas
  de arquitectura](/2_Tecnicas_y_herramientas/2_05_.Tacticas_arquitectura.md)
  para lograr estos atributos pueden sugerir nuevos componentes.

5. **Reestructurar los componentes**. Después de analizar los roles,
   responsabilidades y los atributos de calidad, el último paso es reestructurar
   los componentes según sea necesario de los pasos anteriores. Esto puede
   implicar dividir o fusionar componentes, u optimizar las relaciones entre
   ellos.

Este ciclo es iterativo y ayuda a refinar continuamente la arquitectura del
software a medida que surgen nuevos requerimientos o evolucionan las decisiones
arquitectónicas.

Además de estos pasos existen algunos enfoques adicionales para descubrir
componentes[^1]:

* **Actor/Acción**. Es una forma popular para asignar requerimientos a
  componentes. El arquitecto identifica a los actores que realizan actividades
  con la aplicación y las acciones que esos actores pueden realizar. Proporciona
  una técnica para descubrir los usuarios típicos de la aplicación y qué tipo de
  cosas podrían hacer con él.

* ***Event storming***. En el *event storming* el arquitecto asume que el
  proyecto usará mensajes o eventos para comunicarse entre los diversos
  componentes, intenta determinar qué eventos ocurren en función de los
  requerimientos y roles identificados, y construye componentes entorno a esos
  controladores de eventos y mensajes.

* **Workflow**. En el enfoque de *workflow* el arquitecto modela los componentes
  en torno a flujos de trabajo, de forma muy similar a *event storming*, pero
  sin las restricciones explícitas de la construcción de un sistema basado en
  mensajes. Un enfoque de flujo de trabajo identifica los roles clave, determina
  los tipos de flujos de trabajo en los que participan estos roles y construye
  componentes en torno a las actividades identificadas.

* **Entity trap**. Es un anti-patrón que resulta de identificar componentes para
  gestionar las entidades. Vean más información
  [aquí](https://www.developertoarchitect.com/lessons/lesson191.html).
