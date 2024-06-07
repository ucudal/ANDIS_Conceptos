# 1 Contenido

## 1.4 Gestión

Este documento describe aspectos de gestión de los proyectos de finales de grado
en particular.

> [!NOTE] A diferencia de otras páginas en este repositorio, ésta está dirigida
> a los equipos que llevan adelante el proyecto final de grado —y no a un lector
> individual— por lo que notarán un cambio en el estilo de redacción —en otras
> páginas hubiéramos dicho "notarás"— :wink:.

La metodología para los proyectos finales de grado ha evolucionado y a partir de
2024 combina algunos aspectos del marco metodológico que usábamos anteriormente
con otros de metodologías ágiles actuales.

La metodología actual está basada en el enfoque [Disciplined Agile®
Delivery](https://www.pmi.org/disciplined-agile/process/introduction-to-dad)
—DAD— del [Project Management Institute](https://www.pmi.org). La elección de
esta metodología se justifica en que es parte del curso de Gestión de proyectos
—por un lado—, y en que aborda todos los aspectos del ciclo de vida completo de
un proyecto como los de final de grado, admitiendo múltiples formas de trabajo,
abarcando todos los aspectos del desarrollo ágil de software de una manera
sólida, pragmática y gobernable —por otro—.

## El ciclo de vida DAD

El [ciclo de vida](https://www.pmi.org/disciplined-agile/lifecycle) del DAD
tiene tres fases, donde se construye gradualmente una solución consumible a lo
largo del tiempo:

* Inicio —o *inception*—

* Construcción

* Transición

Cada una de estas fases puede tener una o más iteraciones o *sprints*.

![El ciclo de vida DAD](/diagrams/DAD_Lifecycle.svg)

*Figura 1: Una vista de alto nivel del ciclo de vida de la entrega en DAD.
Tomado de [PMI](https://www.pmi.org/disciplined-agile/lifecycle).*

> [!TIP] Puedes ver las actividades en cada una de las fases de DAD en el [DA
> Browser](https://dabrowser.pmi.org).

El proyecto final de grado tiene las siguientes etapas, donde algunas de ellas
tienen una entrega formal en webasignatura, según se indica [más
adelante](#correspondencia-entre-el-marco-metodológico-y-el-proyecto-final-de-grado):

* Inicio

* Prueba de concepto

* Primer *release*

* Segundo *release*

* *Delivery* al cliente y tercer *release*

Las siguientes son las diferentes dimensiones en las que los equipos trabajan a
lo largo del proyecto; en algunas etapas trabajan más en una dimensión que en
otras.

* Requerimientos

* Diseño y arquitectura

* Desarrollo

* Aseguramiento de la calidad

* UX/UI

* Gestión y proceso

De la combinación entre las etapas y las dimensiones surgen las actividades y
los productos que se generan a lo largo del proyecto final de grado, como se
detalla más adelante.

A partir de 2024 toda la documentación se entrega en un solo archivo o
repositorio siguiendo la estructura detallada en la sección
[Contenido](/1_Contenido/1__Contenido.md) de este repositorio.

## Correspondencia entre el marco metodológico y el proyecto final de grado

A continuación detallamos la correspondencia entre las etapas y entregas del
proyecto final de grado con las fases de DAD.

Las etapas en el proyecto final de grado sirven para organizar el trabajo del
proyecto; [más adelante](#etapas-del-proyecto-final-de-grado) les mostramos qué
actividades esperamos que realicen en cada etapa. Las entregas son instancias
formales donde presentan el avance del trabajo en webasignatura y reciben
feedback de su tutor; también les mostramos [más
adelante](#entregas-del-proyecto-final-de-grado) qué contenidos deberían
entregar. Tengan en cuenta que las entregas de proyecto ocurren al final de las
etapas incluidas en la entrega.

<table>
  <tr>
    <th>
      Etapas en PFG
    </th>
    <th>
      Entregas en PFG
    </th>
    <th>
      Fases en DAD
    </th>
  </tr>
  <tr>
    <td>
      Anteproyecto
    </td>
    <td>
      Propuesta de proyecto
    </td>
    <td rowspan=2>
      Inicio
    </td>
  </tr>
  <tr>
    <td>
      Inicio
    </td>
    <td rowspan=3>
      Primera entrega
    </td>

  </tr>
  <tr>
    <td>
      Prueba de concepto
    </td>
    <td rowspan=5>
      Construcción
    </td>
  </tr>
  <tr>
    <td>
      Primer <i>release</i>
    </td>
  </tr>
  <tr>
    <td>
      Segundo <i>release</i>
    </td>
    <td>
      Segunda entrega
    </td>
  </tr>
  <tr>
    <td>
      <i>Delivery</i> al cliente y tercer <i>release</i>
    </td>
    <td>
      Entrega final
    </td>
  </tr>
  <tr>
    <td colspan=2 style="text-align:center">
      Defensa
    </td>
  </tr>
  <tr>
    <td colspan=2 style="text-align:center">
      <i>No aplicable</i>
    </td>
    <td>
      Transición
    </td>
  </tr>
</table>

Una parte de las actividades que en DAD ocurren en la fase de inicio tienen
lugar en el anteproyecto, mientras que otras tienen lugar en la etapa de inicio
del proyecto. El resto de las etapas del proyecto corresponden a la fase de
construcción en DAD. La fase de transición en DAD, cuya actividad principal es
el despliegue en producción, no aplica al proyecto final de grado.

## Etapas del proyecto final de grado

### Anteproyecto

La etapa de anteproyecto es un tanto peculiar porque ocurre antes del inicio
formal del proyecto final de grado, aunque la incluimos aquí porque es una parte
importante de todo el proceso. En esta etapa deben elegir o proponer su
proyecto, y formular y presentar la correspondiente propuesta.

Para ello deberán mantener reuniones con la contraparte del proyecto, es decir,
quién actúe como cliente. Esperamos que se familiaricen lo suficiente con la
necesidad que les planteen y con el dominio del problema o del área de trabajo,
<!-- @fmachadopiriz definir "trabajo o área de trabajo" -->
como para formular la propuesta; puedes ver [aquí](#propuesta-de-proyecto) qué
contiene la propuesta a entregar al final de esta etapa.

También deberán determinar qué es lo que se necesita construir para resolver la
necesidad planteada, incluyendo posibles soluciones arquitectónicas de alto
nivel.

Aunque el anteproyecto está organizado como un curso, es sólo a efectos de saber
quiénes están trabajando en una propuesta de proyecto y tener una
[webasignatura](https://webasignatura.ucu.edu.uy/course/view.php?id=6191) con:

* La lista de proyectos disponibles propuestos por empresas u otras entidades.

* Un foro para consultas y armado de equipos de proyecto entre los propios
  estudiantes.

* Una tarea para la entrega de propuestas de proyecto; la fecha de entrega es la
  fecha límite para presentación de propuestas.

Para la inscripción a este curso, consulta la [web de la
carrera](https://webasignatura.ucu.edu.uy/course/view.php?id=3751).

Los productos esperados de esta etapa para cada dimensión son los siguientes:

* **Requerimientos**. Los [eventos de
  negocio](/4_Conceptos/4_Evento_de_negocio.md) más significativos. Incluyan
  para cada evento de negocio al menos su descripción, sus datos, y si es de
  entrada o de salida.

  Los [caso de uso del negocio](/4_Conceptos/4_Caso_de_uso_del_negocio.md) para
  cada evento del negocio identificado en el punto anterior. Del caso de uso del
  negocio incluyan al menos su descripción, el evento de negocio que lo activa,
  el actor o parte interesada —*stakeholder*— activa, y el resultado
  —*outcome*—.

* **Diseño y arquitectura**. Una arquitectura de alto nivel tentativa que define
  qué tipo de solución van a desarrollar en el proyecto: una aplicación web
  cliente—servidor con una base de datos relacional, o una aplicación *mobile*
  con un *backend* REST y un *back-office* web con una base de datos
  no-relacional, o una aplicación de escritorio distribuida con una base de
  datos centralizada, etc.

* **Desarrollo**. No es necesario que desarrollen código en esta etapa.

* **Aseguramiento de la calidad**. Pueden usar la [rúbrica de propuestas de
  proyecto](/1_Contenido/1_4_1_Rubrica_propuesta.md) final de grado para evaluar
  el producto que van a entregar; sin embargo, no es necesario que entreguen
  esta evaluación.

* **UX/UI**. En caso de que el cliente indique que deben seguir ciertos
  estándares, mantener cierto estilo, seguir manuales de marca, etc. deben
  indicarlo aquí.

* **Gestión y proceso**. Cuál de las [seis versiones de ciclos de vida de
  DAD](https://www.pmi.org/disciplined-agile/process/introduction-to-dad/full-delivery-lifecycles-introduction)
  usarán en el proyecto y qué
  [roles](https://www.pmi.org/disciplined-agile/process/introduction-to-dad/people-first-roles-in-dad-introduction)
  tendrá cada miembro del equipo.

### Descubrimiento e inicio

La etapa de descubrimiento e inicio es la primera del proyecto. Dura entre X y X
semanas.

Los objetivos en esta etapa son:

* Terminar de familiarizarte con el dominio del problema; tuviste tu primer
  acercamiento cuando formulaste la propuesta, ahora deberás completar tu
  entendimiento del dominio del problema.

* Completar los eventos del negocio y los casos de uso del negocio; la mayoría
  ya los identificaste para la propuesta durante el anteproyecto.

* Armar un [EDT](/4_Conceptos/4_EDT.md) —o [*WBS*](/4_Conceptos/4_WBS.md)—
  incluyendo el [MVP] y un listado de épicas para el alcance todo el proyecto;
  este será el plan del proyecto.

  TODO: definir el MVP

* Compartir con el cliente el plan del proyecto y validar expectativas sobre el
  alcance del proyecto y las soluciones arquitectónicas que incluiste
  oportunamente en la propuesta de proyecto —si no lo hubieras hecho todavía—.

* Comenzar a escribir el documento entregable; puedes ver a continuación qué
  productos se generan en esta etapa para cada dimensión del proyecto.

Los productos esperados de esta etapa para cada dimensión son los siguientes:

* **Requerimientos**. Todos los eventos del negocio; incluyan para cada evento
  de negocio al menos la misma información que incluyeron en la propuesta.

  Todos los casos de uso del negocio para los eventos del negocio identificados;
  incluyan para cada caso de uso la misma información que incluyeron en la
  propuesta —más el resultado esperado, como se indica más adelante en la
  dimensión de aseguramiento de la calidad—.

  <!-- @fmachadopiriz ver qué más incluir del documento de visión, por ejemplo,
  objetivo del proyecto; revisar con @PaoloMazza1204 -->

* **Diseño y arquitectura**. Actualización de la arquitectura presentada en la
  propuesta, si corresponde; en caso de que haya cambios significativos —pasaron
  de una aplicación web a una aplicación *mobile*, por ejemplo—, incluyan una
  justificación.

* **Desarrollo**. Aunque no es requerido, sí es recomendable tener un esqueleto
  de la arquitectura de la solución en código. Por ejemplo, si el producto final
  será una aplicación *mobile* con un *backend*, puedes tener un servicio web
  REST para el *backend* con un *endpoint* de chequeo de salud[^1] que retorne
  siempre `200 OK` y el cliente *mobile* puede ser simplemente una pantalla de
  bienvenida que muestre el resultado del chequeo de salud del *backend*, todo
  corriendo en ambiente de desarrollo. Aunque esto pueda cambiar en el futuro,
  te obligará a crear los proyectos, ponerlos en un repositorio de control de
  configuración en línea, asignar los permisos, etc.

  > [!IMPORTANT] Todos los miembros del equipo, independientemente de su rol,
  > deberán conocer y estar en condiciones de ejecutar el código desarrollado a
  > lo largo de todo el proyecto.

* **Aseguramiento de la calidad**. Completen la sección de resultado esperado de
  cada caso de uso, y asegúrense de que es verificable.

  Pueden usar la rúbrica de la primera entrega para evaluar lo que hayan
  avanzado del producto que van a entregar, teniendo en cuenta que hay otras
  etapas por completar antes de esa entrega. No es necesario que entreguen esta
  evaluación.

* **UX/UI**. Actualización de la información presentada en la propuesta, si
  corresponde. En caso de que haya cambios significativos, incluyan una
  justificación.

* **Gestión**. Definición de herramientas para la operativa cotidiana del
  proyecto, por ejemplo:

  **Gestión del *backlog***. Recomendamos usar [Azure Devops
  Services](https://azure.microsoft.com/es-es/products/devops) ya que tienen
  acceso a la versión completa de esta herramienta con la cuenta de estudiante
  @correo.ucu.edu.uy; pero en acuerdo con tu tutor pueden usar otras[^2].

  **Repositorio de código**. Habitualmente usamos GitHub y los estudiantes
  pueden tener repositorios privados en la
  [organización](https://github.com/ucudal) de la  universidad. Pídanle a su
  tutor que les gestione la creación de los repositorios que necesiten.

  **Repositorio de documentos**. Pueden usar también [Microsoft
  Teams](https://teams.microsoft.com) para esto; nuevamente, si lo acuerdan con
  su tutor, pueden usar otros[^2].

  **Videoconferencia** —para reuniones remotas con el equipo y ocasionalmente
  con su tutor; las clases son presenciales—. Recomendamos usar [Microsoft
  Teams](https://teams.microsoft.com), que es la herramienta elegida por la
  universidad para colaboración, pero en acuerdo con su tutor, pueden usar
  otras[^2].

### Prueba de concepto

La segunda etapa del proyecto es la prueba de concepto. Dura entre x y x
semanas.

Los objetivos de esta etapa son:

* Relevar y especificar los [casos de uso del
  producto](/4_Conceptos/4_Caso_de_uso_del_producto.md) para los casos de uso
  del negocio más significativos que serán parte del MVP.

* Usando la plantilla de [requerimiento
  atómico](/3_Plantillas/3_1_Requerimiento_atomico.md) especificar la versión
  inicial de los requisitos funcionales y no funcionales de los casos de uso del
  producto.

  Pueden usar [historias de usuario](/4_Conceptos/4_Historia_de_usuario.md) para
  especificar los requerimientos.

* Definir la arquitectura detallada y las tecnologías que vas a utilizar.

* Implementar la mínima cantidad de requerimientos —puede ser uno— que permita
  validar la arquitectura planteada.

* Actualizar el plan de proyecto ajustando el EDT —*WBS*— y asignando
  requerimientos a los *releases* de las próximas entregas.

  Pueden usar [épicas](/4_Conceptos/4_Epica.md) en el plan de proyecto y
  asignarlas a los *releases* de las próximas entregas.

* Compartir con el cliente el plan del proyecto ajustado y obtener
  retroalimentación del cliente.

Los productos esperados de esta etapa para cada dimensión son los siguientes:

* **Requerimientos**. Los casos de uso del producto para los casos del negocio
  más significativos identificados en la etapa anterior. Incluyan en cada caso
  de uso al menos su disparador, su nombre, el actor, el curso básico y el
  resultado esperado; excepto para el o los casos de uso del producto que hayan
  elegido para validar la arquitectura, que tendrán que estar completo.

  Los requerimientos funcionales y no funcionales para el o los casos de uso del
  producto que hayan incluido.

* **Diseño y arquitectura**. La arquitectura detallada y las tecnologías que van
  a utilizar para cada componente.

* **Desarrollo**. El código funcionando que implementa el o los requerimientos
  que hayan escogido para validar la arquitectura. Incluyan instrucciones para
  que su tutor pueda ejecutar la solución en un ambiente de desarrollo.

* **Aseguramiento de la calidad**. Pruebas de unidad para el código entregado.

* **UX/UI**. Maquetas para la interfaz de usuario del o de los casos de uso
  elegidos para validar la arquitectura.

* **Gestión**. El plan de proyecto actualizado y los siguientes indicadores o
  reportes de métricas a lo largo de la etapa[^3]:

  **Velocidad**. La capacidad del equipo de entregar trabajo. El propósito de
  este indicador es mostrar cuánto trabajo tuvo capacidad de entregar el equipo
  durante la etapa.

  **_Burn down_**. La evolución de la cantidad de trabajo entregada. El
  propósito de este indicador es mostrar la cantidad de trabajo realizada por el
  equipo durante la etapa.

  **_Cumulative flow_**. La evolución de la cantidad de trabajo pendiente, en
  progreso y terminada. El propósito de este indicador es entender si hubo
  *scope creep*, demoras en completar items, etc. durante la etapa.

  **_Build status_**. La evolución del estado de compilación de la solución. El
  propósito de este indicador es ver si hubo contribuciones que introdujeron
  inestabilidad en la solución.

  **_Test failures_**. La evolución del estado de los casos de prueba. El
  propósito de este indicador es entender cómo agregan casos de prueba a lo
  largo del tiempo, y cómo la solución pasa o no estos casos de prueba.

### Primer *release*

La tercera etapa del proyecto es el primer *release*. Dura entre X y X semanas.

Más allá de que en cada iteración produzcas una [solución consumible](), en el
primer *release* sí o sí deberías tener una solución similar a la final, aunque
obviamente sólo implementará los requerimientos asignados a esta etapa. Excepto
por el hecho de que no es una solución funcionalmente completa, debería tener
las siguientes características:

* Lo que está implementado es usable

* Lo que entregas tiene alta calidad

* La documentación para el usuario está actualizada

Los objetivos de esta etapa son:

* Actualizar los componentes de diseño y arquitectura del documento entregable.

* Refinar el EDT —o *WBS*—.

* Liberar una primera versión del MVP funcionando.

De nuevo, aunque en cada iteración ya vengas usando una forma de compilación,
despliegue y prueba automatizada, en este *release* sí o sí deberás tenerla.
Esto puede ser implementado con [GitHub
Actions](https://github.com/features/actions), [Azure
Pipelines](https://azure.microsoft.com/es-es/products/devops/pipelines), o
alguna otra herramienta equivalente.

Los productos esperados de esta etapa para cada dimensión son los siguientes:

* **Requerimientos**. Los casos de uso del producto completos que correspondan a
  la funcionalidad incluida en esta etapa; las actualizaciones de los
  previamente entregados si correspondiera.

  Los requerimientos atómicos completos correspondientes a la funcionalidad
  incluida en esta etapa; las actualizaciones que correspondiera de los que
  hayan entregado antes.

* **Diseño y arquitectura**. Los [diagramas de
  despliegue](/2_Tecnicas_y_herramientas/2_2_1_Diagramas_de_despliegue_UML.md)
  completos. Los [diagramas de
  clases](/2_Tecnicas_y_herramientas/2_3_1_Diagramas_de_clases_UML.md) al menos
  con las clases del dominio. En caso de que corresponda, otros [diagramas de
  actividades](/2_Tecnicas_y_herramientas/2_4_1_Diagramas_de_actividades_UML.md)
  o [secuencia](/2_Tecnicas_y_herramientas/2_4_3_Diagramas_de_secuencia_UML.md).

* **Desarrollo**. El código funcionando que implementa requerimientos que hayan
  implementado en este etapa. Nuevamente incluyan instrucciones para que su
  tutor pueda ejecutar la solución en un ambiente de desarrollo.

* **Aseguramiento de la calidad**. Las pruebas de unidad para el código
  entregado.

  Casos de prueba de usuario final para los casos de uso del producto incluidos
  en esta fase. Datos de prueba para esos casos de prueba. Resultados de esas
  pruebas.

  En caso de que corresponda, pruebas de carga para mostrar el funcionamiento
  correcto de la arquitectura.

* **UX/UI**. Maquetas para los casos de uso del producto incluidos en esta
  etapa.

* **Gestión**. El plan de proyecto actualizado y los mismos indicadores de la
  etapa anterior.

### Segundo *release*

La cuarta etapa del proyecto es el segundo *release*. Dura entre X y X semanas.

Los objetivos de esta etapa son:

* Conseguir retroalimentación del cliente respecto del MVP. <!-- @diego es del
  MVP entregado en la etapa anterior? -->

* Liberar una segunda versión del MVP funcionando, con la UX/UI avanzada, y al
  menos tres funcionalidades definidas por el cliente como *nice to have*
  implementadas.
  <!-- @diego deberíamos definir antes la prioridad de las funcionalidades además de
  las nice to have, cuáles van en qué etapa, y qué relación hay entre
  funcionalidades, requerimientos, casos de uso e historias de usuario -->

  Aunque no es obligatorio, recomendamos definir la interfaz de usuario con
  herramientas de creación de prototipos como [Figma](https://www.figma.com),
  para validar con el cliente antes de la implementación en la solución.

* Definir el criterio de ajuste —o criterio de aceptación— de todos los
  requerimientos atómicos especificados.
  <!-- @fmachadopiriz poner que el criterio de ajuste es opcional antes. -->

* Completar la sección de calidad del documento entregable.
  <!-- @fmachadopiriz ver qué de calidad se agrega antes si en este etapa es sólo completar -->

* Actualizar las secciones de arquitectura y diseño si corresponde.

* Obtener y presentar evidencia del feedback del cliente y los próximos pasos
  definidos en acuerdo con él.

* Revisar la gestión del proyecto, con métricas de proceso y puntos de mejora
  encontrados, desvíos y cómo los gestionaron.
  <!-- @diego cuáles serían las métricas que deben recolectar -->

Los productos esperados de esta etapa para cada dimensión son los siguientes:

* **Requerimientos**. Los casos de uso del producto completos que corresponden a
  las funcionalidades incluidas en esta etapa; incluyan actualizaciones de los
  previamente entregados si corresponde.

  Los requerimientos atómicos completos correspondientes a las funcionalidades
  incluidas en esta etapa; incluyan actualizaciones de los previamente
  entregados si corresponde.

* **Diseño y arquitectura**. Los diagramas de despliegue actualizados. Los
  diagramas de clases con todas las clases para las funcionalidades incluidas en
  esta etapa. En caso de que corresponda, diagramas de actividades o secuencia.

* **Desarrollo**. El código funcionando que implementa los requerimientos que
  hayan incluido en esta etapa, incluyendo instrucciones para ejecutar la
  solución en ambiente de desarrollo.

* **Aseguramiento de la calidad**. Las pruebas de unidad para el código
  entregado.

  Actualización de los casos de prueba entregados en la etapa anterior. Pruebas
  de regresión utilizando esos casos de prueba actualizados.

  Casos de prueba de usuario final para los casos de uso del producto incluidos
  en esta etapa. Datos de prueba para esos casos de prueba. Resultados de esas
  pruebas.

* **UX/UI**. Maquetas para los casos de uso del producto incluidos en esta
  etapa.

* **Gestión**. El plan de proyecto actualizado y los mismos indicadores de las
  etapas anteriores.

### *Delivery* al cliente y tercer *release*

Esta es la quinta y última etapa del proyecto. Dura entre X y X semanas.

Los productos esperados de esta etapa para cada dimensión son los siguientes:

* **Requerimientos**. Los casos de uso del producto completos para toda la
  solución.

  Los requerimientos atómicos completos para toda la solución.

* **Diseño y arquitectura**. Los diagramas de despliegue completos. Los
  diagramas de clases completos, al menos con las clases del dominio; idealmente
  incluir otras clases relevantes de la solución, excluyendo clases de
  *frameworks* o generadas por herramientas. Diagramas de actividades o de
  secuencia si corresponde.

* **Desarrollo**. El código completo de la solución.

  El *pipe* de CI/CD actualizado para despliegue en ambientes de pruebas.

* **Aseguramiento de la calidad**. Las pruebas de unidad para el código
  entregado.

  Pruebas de integración para un conjunto significativo de la funcionalidad de
  la solución. Datos de prueba para esas pruebas. Resultados de esas pruebas.

  Casos de prueba de usuario final para un conjunto significativo de la
  funcionalidad de la solución. Datos de prueba para esas pruebas. Resultados de
  esas pruebas.

* **UX/UI**. No es necesario incluir nuevas maquetas en esta etapa.

* **Gestión**. El plan de proyecto actualizado y los mismos indicadores de la
  etapa anterior.

  Retrospectiva.

## Entregas del proyecto final de grado

### Propuesta de proyecto

Notas generales relativas a la propuesta:

* Deberá tener un mínimo de 10 páginas y un máximo de 20.

* Deberá ser entregada en formato PDF.

* Deberá ser entregada vía webasignatura.

* Deberá ser firmada por **todos** los integrantes del grupo.

Contenido de la propuesta:

* Descripción de los integrantes del grupo, junto con su historial laboral y
  competencias claves dentro del proyecto.

* Borrador del [posicionamiento del
  proyecto](/1_Contenido/1_1__Requisitos.md#posicionamiento-del-proyecto).

* [Interesados](/1_Contenido/1_1__Requisitos.md#interesados-stakeholders)
  preliminares. En particular identificar quién de los interesados actuará como
  encargado del proyecto de la contraparte y quién hace las veces de
  patrocinador.

* Borrador de las [necesidades
  clave](/1_Contenido/1_1__Requisitos.md#identificación-de-necesidades-clave).

* El producto de la [etapa de anteproyecto](#anteproyecto) descrita antes.

### Primera entrega

* Carta de confidencialidad

* <!-- TODO: enumerar las secciones aplicables -->

### Segunda entrega

* <!-- TODO: enumerar las secciones aplicables -->

### Entrega final

* Carta de aceptación

* <!-- TODO: enumerar las secciones aplicables -->

[^1]: Ese *endpoint* será la semilla para implementar en el futuro el patrón
    [Health Endpoint
    Monitoring](https://learn.microsoft.com/en-us/azure/architecture/patterns/health-endpoint-monitoring)
    por ejemplo.

[^2]: Ten en cuenta la seguridad y privacidad de la información que almacenes en
    estos repositorios; si tienes un acuerdo de confidencialidad con el cliente,
    deberías usar las herramientas recomendadas. También deberás considerar que
    otras herramientas pueden tener costos asociados o limitar la cantidad de
    usuarios o de archivos en las versiones gratuitas.

[^3]: Estos reportes pueden ser generados automáticamente con la herramienta
    Azure DevOps recomendada, no tienen porqué hacerlos a mano si la usan para
    la gestión del proyecto. Otras herramientas también pueden generarlas.
