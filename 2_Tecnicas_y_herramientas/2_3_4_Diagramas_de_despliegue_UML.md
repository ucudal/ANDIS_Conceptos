# 2 Técnicas y herramientas

## 2.3 Modelos de estructura

### 2.3.4 Diagramas de despliegue UML

Los diagramas de despliegue UML modelan la arquitectura física de un sistema.
Estos diagramas muestran las relaciones entre los
[componentes](/4_Conceptos/4_Componente.md) de software y hardware del sistema,
es decir, la disposición física de los nodos en un sistema distribuido, los
artefactos que se almacenan en cada nodo y los componentes y otros elementos que
implementan los artefactos, así como las rutas de comunicación y las relaciones
de implementación entre esos elementos.

Este documento está basado en UML 2.5.1[^1].

Los diagramas de despliegue tienen estos elementos:

* Nodos, que se representan con un cubo con el estereotipo `≪node≫`; ese
  rectángulo contiene el nombre del nodo, que describe la pieza de hardware que
  representa. En lugar de estereotipo `≪node≫` es posible usar estereotipos más
  específicos como `≪mainframe≫`, `≪pc≫`, `≪database server≫`, etc.; además se
  puede usar un ícono para representar visualmente estos estereotipos.

  Los nodos son elementos del modelo que representan los recursos
  computacionales en los que se puede desplegar artefactos ‑la definición de
  artefacto está más abajo‑. Los nodos pueden contener otros nodos. Hay dos
  tipos más específicos de nodo, los ambientes de ejecución y los dispositivos
  ‑que están definidos también más abajo‑.

* Instancias de nodos, que representan una ocurrencia real de un nodo. Las
  instancias de nodo se basan en nodos existentes. El nombre de la instancia va
  delante del nombre del nodo separado por `:` y subrayado.

* Ambientes de ejecución ‑*execution environment*‑, que son un tipo más
  específico de nodo, y que se representan como un nodo pero con el estereotipo
  `≪executionEnvironment≫`; el nombre del nodo, que describe el ambiente de
  ejecución que representa.

  Estos ambientes de ejecución modelan un ambiente de ejecución particular, como
  un sistema operativo o un sistema de gestión de bases de datos. Los entornos
  de ejecución se usan para describir el contexto en el que tiene lugar la
  ejecución de un modelo.

  Los entornos de ejecución generalmente forman parte de otro nodo que modela el
  hardware en el que se ejecuta ese entorno de ejecución. Por ejemplo, un
  entorno de ejecución dentro de un servidor puede proporcionar los servicios a
  nivel de sistema operativo necesarios para soportar una aplicación de base de
  datos instalada en ese entorno.

* Artefactos, que se representan con un rectángulo que tiene el estereotipo
  `«artefacto»`, el icono del artefacto y el nombre del artefacto.

  Un artefacto representa algún elemento de información que se utiliza o produce
  mediante un proceso de desarrollo de software o mediante la operación de un
  sistema. Ejemplos de artefactos incluyen archivos de modelos, archivos fuente,
  scripts, archivos ejecutables, tablas de bases de datos, entregables de
  desarrollo, documentos de procesamiento de textos y mensajes de correo. Los
  artefactos se implementan ‑se despliegan‑ en nodos y se admite la
  implementación de artefactos en varios tipos de nodos.

* Instancias de artefactos, que representan una ocurrencia real de un artefacto.
  Las instancias de artefactos se basan en artefactos existentes. El nombre de
  la instancia va delante del nombre del artefacto separado por `:` y subrayado.

* Dispositivos, que son un tipo más específico de nodo, y que se representan
  también como un nodo pero con el estereotipo `≪device≫`; el nombre del nodo
  describe el dispositivo que representa.

* Especificaciones de despliegue, que se representan con un rectángulo con el
  estereotipo `≪deploymentSpec≫`. Modelan archivos de configuración y sus
  atributos modelan los parámetros de configuración de los componentes o
  artefactos desplegados en un nodo.

* Rutas de comunicación, que son un tipo más específico de asociación entre
  nodos en un diagrama de despliegue, que muestra cómo los nodos intercambian
  mensajes y señales. Al igual que con las asociaciones, es posible definir la
  cantidad de nodos que se pueden conectar en cada extremo. También es posible
  utilizar etiquetas para identificar el tipo de protocolo o red que se utiliza
  en la comunicación.

* Relaciones de despliegue, que son un tipo más específico de dependencia con el
  estereotipo `≪deploy≫`, y no suelen llevar un nombre. Modelan que un nodo
  soporta el despliegue de un artefacto.

* Asociaciones y generalizaciones, con la semántica habitual que tienen en los
  [diagramas de clases](./2_3_1_Diagramas_de_clases_UML.md).

La [Figura 1](#figura-1), a continuación, muestra un ejemplo de diagrama de
despliegue. El nodo `Servidor de aplicación` alberga una instancia de
`WebSphere` en la que se ejecuta la `Aplicación web` y la `API conexión DB`. El
`Navegador web` en el dispositivo `Computadora del usuario` se conecta a la
`Aplicación web` mediante una conexión HTTP sobre Internet. La `API conexión DB`
se conecta mediante una conexión nativa con el `Reporte de datos` en el
`Servidor de base de datos`. La `Aplicación web` se conecta con la `lógica de
negocios` en `Servidor web` mediante una conexión SOAP sobre HTTP.

<a id="figura-1"/>

![Ejemplo de diagrama de despliegue](/diagrams/Deployment_Diagram_Example.svg)

*Figura 1: Ejemplo de diagrama de despliegue.*

La [Figura 2](#figura-2), a continuación, muestra otro ejemplo de diagrama de
despliegue. En este caso el dispositivo `Servidor de aplicación` que contiene un
servidor JSP `Tomcat 5.5` ‑o dicho de otro modo, hay un servidor JSP llamado
`Tomcat 5.5` desplegado en el dispositivo `Servidor de aplicación`. A su vez el
servidor JSP contiene un ambiente de ejecución
`Catalina Servlet 2.4/JSP 2.0 Container` ‑también es posible decir que el
ambiente de ejecución está desplegado en el servidor JSP‑. Ese ambiente de
ejecución tiene un artefacto `book_club_app.war` que está compuesto por otros
dos artefactos `user_services.jar` y `web-tools-lib.jar`. El primer artefacto
`book_club_app.war` es la manifestación del componente `OnlineOrders`, mientras
que el tercer artefacto
`user_services.jar` es la manifestación del componente `UserServices`. La
manifestación se modela como una dependencia estereotipada con
`≪manifest≫` desde el artefacto que es la "manifestación" hacia el componente
que es "manifestado". Hay una especificación de despliegue con el estereotipo
`≪deploymentSpec≫` llamada `web.xml` para el artefacto `book_club_app.war`; la
especificación de despliegue está conectada con el artefacto mediante una
dependencia. Como todos estos elementos están contenidos dentro del nodo
`Catalina Servlet 2.4/JSP 2.0 Container` implica que están desplegados en él.

El dispositivo `Servidor de aplicación` está conectado con el dispositivo
`Servidor de base de datos` mediante una conexión con protocolo `TCP/IP`. Este
segundo dispositivo tiene un sistema de base de datos `Oracle 10g`. Este nodo
contiene a su vez los esquemas `User`, `Orders` e `Inventory`.

<a id="figura-2"/>

![Otro ejemplo de diagrama de
despliegue](/diagrams/Deployment_Diagram_Another_Example.svg)

*Figura 2: Otro ejemplo de diagrama de despliegue.* Tomado de
[aquí](https://www.uml-diagrams.org/deployment-diagrams-overview.html).

Puedes ver más ejemplos de [diagramas de despliegue en UML
Diagrams](https://www.uml-diagrams.org/deployment-diagrams-overview.html).

Puedes ver más información sobre diagramas de despliegue en las herramientas de
modelado [IBM Software
Architect](https://www.ibm.com/docs/en/rational-soft-arch/9.7.0?topic=diagrams-creating-deployment),
[Visual
Paradigm](https://www.visual-paradigm.com/learning/handbooks/software-design-handbook/deployment-diagram.jsp)
y [Lucidchart](https://www.lucidchart.com/pages/uml-deployment-diagram).

[^1]: OMG. (2017). OMG® Unified Modeling Language®. Disponible
    [aquí](https://www.omg.org/spec/UML/2.5.1/PDF).
