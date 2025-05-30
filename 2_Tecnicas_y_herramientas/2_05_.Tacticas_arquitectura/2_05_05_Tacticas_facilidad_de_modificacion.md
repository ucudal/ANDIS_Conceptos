# 2 Técnicas y herramientas

## 2.5 Tácticas de arquitectura

### 2.5.5 Tácticas para la facilidad de modificación

Las tácticas para lograr satisfacer el atributo de calidad de [facilidad de
modificación](/4_Conceptos/4_Facilidad_de_modificacion.md) en arquitectura de
software tienen como objetivo aumentar la cohesión, reducir el acoplamiento o
diferir el *binding*.

La siguiente tabla —tomada de[^1]— resume las tácticas disponibles, que están
explicadas más abajo.

[^1]: Bass, L.; Clements, P.; Kazman, R. (2022). Software Architecture in
    Practice, 4<sup>th</sup> edition. Addison-Wesley.

<table>
  <tr>
    <td rowspan="15">
      Tácticas para la facilidad de modificación
    </td>
    <td rowspan="2">
      Aumentar la <a href="/4_Conceptos/4_Cohesion.md">cohesión</a>
    </td>
    <td>
      <a href="#separar-módulos">Separar módulos</a>
    </td>
  </tr>
  <tr>
    <td>
      <a href="#redistribuir-las-responsabilidades">Redistribuir las responsabilidades</a>
    </td>
  </tr>
  <tr>
    <td rowspan="4">
      Reducir el <a href="/4_Conceptos/4_Acoplamiento.md">acoplamiento</a>
    </td>
    <td>
      <a href="#encapsulamiento">Encapsulamiento</a>
    </td>
  </tr>
  <tr>
    <td>
      <a href="#usar-un-intermediario">Usar un intermediario</a>
    </td>
  </tr>
  <tr>
    <td>
      <a href="#abstraer-servicios-comunes">Abstraer servicios comunes</a>
    </td>
  </tr>
  <tr>
    <td>
      <a href="#restringir-las-dependencias">Restringir las dependencias</a>
    </td>
  </tr>
  <tr>
    <td rowspan="9">
      Diferir el <i>binding</i>
    </td>
    <td>
      <a href="#reemplazo-de-componentes">Reemplazo de componentes</a>
    </td>
  </tr>
  <tr>
    <td>
      <a href="#parametrización-en-tiempo-de-compilación">Parametrización en
      tiempo de compilación</a>
    </td>
  </tr>
  <tr>
    <td>
      <a href="#aspectos">Aspectos</a>
    </td>
  </tr>
  <tr>
    <td>
      <a href="#binding-en-tiempo-de-configuración"><i>Binding</i> en tiempo de
      configuración</a>
    </td>
  </tr>
  <tr>
    <td>
      <a href="#archivos-de-recursos-o-resource-files">Archivos de recursos o
      <i>resource files</i></a>
    </td>
  </tr>
  <tr>
    <td>
      <a href="#descubrimiento">Descubrimiento</a>
    </td>
  </tr>
  <tr>
    <td>
      <a href="#interpretación-de-parámetros">Interpretación de parámetros</a>
    </td>
  </tr>
  <tr>
    <td>
      <a href="#repositorios-compartidos">Repositorios compartidos</a>
    </td>
  </tr>
  <tr>
    <td>
      <a href="#polimorfismo">Polimorfismo</a>
    </td>
  </tr>
</table>

#### Separar módulos

Consiste en dividir un componente de la arquitectura de software en dos o más
componentes independientes para aumentar la
[cohesión](/4_Conceptos/4_Cohesion.md) y reducir el
[acoplamiento](/4_Conceptos/4_Acoplamiento.md) y la
[co-nascencia](/4_Conceptos/4_Connascence.md).

> [!TIP]
> Vean además [Design for
> evolution](https://learn.microsoft.com/en-us/azure/architecture/guide/design-principles/design-for-evolution)
> en Azure Architecture Center.

#### Redistribuir las responsabilidades

Es mover las responsabilidades relacionadas existentes en diferentes componentes
de la arquitectura de software a un nuevo componente para aumentar la
[cohesión](/4_Conceptos/4_Cohesion.md) y reducir el
[acoplamiento](/4_Conceptos/4_Acoplamiento.md) y la
[co-nascencia](/4_Conceptos/4_Connascence.md).

#### Encapsulamiento

Es ocultar los detalles de la implementación de un componente de la arquitectura
de software detrás de una interfaz bien definida, de modo que los cambios
internos no afecten a otros componentes que dependen de él.

#### Usar un Intermediario

Consiste en introducir un componente intermediario entre otros dos
interdependientes para manejar la interacción entre ellos, facilitando el cambio
de cualquiera de los componentes interdependientes sin afectar al otro.

#### Abstraer servicios comunes

Cuando hay dos componentes con interfaces similares se puede buscar ocultar las
diferencias detrás de otro componente más abstracto pero más general. La
reutilización de este nuevo componente reduce las dependencias de los demás
clientes que tenían que utilizar los componentes originales.

#### Restringir las dependencias

Implica limitar las dependencias entre componentes para reducir el impacto de
los cambios y facilitar el mantenimiento. Por ejemplo, en un sistema de capas,
se asegura que la capa de presentación solo dependa de la capa de negocio y
nunca directamente de la capa de datos, restringiendo así las dependencias y
facilitando cambios en la capa de datos.

#### Reemplazo de componentes

Consiste en diseñar el sistema de manera que los componentes puedan ser
reemplazados fácilmente por otros en tiempo de despliegue mediante un archivo de
secuencias de comandos ‑o *script*‑ por ejemplo.

#### Parametrización en tiempo de compilación

Es cuando se usan directivas de compilación condicional para generar diferentes
versiones de un componente a partir de un mismo código fuente.

#### Aspectos

Es el uso de la programación orientada a aspectos ‑o AOP por las siglas en
inglés de  *aspect oriented programming*‑ para separar las cuestiones
transversales ‑como *logging* o seguridad‑ del código principal, facilitando su
modificación sin alterar la lógica central.

> [!TIP]
> Vean por ejemplo [Aspect Oriented Programming with
> Spring](https://docs.spring.io/spring-framework/reference/core/aop.html).

#### *Binding* en tiempo de configuración

Consiste en configurar mediante parámetros los componentes de la arquitectura de
software cuando se está iniciando la ejecución. Es uso de archivos de
configuración `.appconfig` o archivos `.INI` es un ejemplo de *binding* en
tiempo de configuración.

#### Archivos de recursos o *resource files*

Los recursos ‑como el texto de los mensajes de información o de error, o las
etiquetas de los controles de la interfaz de usuario‑ se almacenan en archivos
externos para facilitar su modificación sin necesidad de volver a compilar y
desplegar los componentes.

#### Descubrimiento

Es la capacidad de localizar y conectarse dinámicamente a servicios o recursos
en tiempo de ejecución a través de un *discovery service* en el cual previamente
fueron registrados los servicios o recursos disponibles.

#### Interpretación de parámetros

Es similar al [*Binding* en tiempo de
configuración](#binding-en-tiempo-de-configuración) pero la configuración se
realiza a través de parámetros recibidos en tiempo de ejecución.

#### Repositorios compartidos

Consiste en utilizar un repositorio común para almacenar configuraciones que son
accesibles por múltiples componentes.

Por ejemplo, el [Windows
Registry](https://learn.microsoft.com/en-us/troubleshoot/windows-server/performance/windows-registry-advanced-users)
es una base de datos jerárquica que almacena configuraciones de las aplicaciones
y del propio sistema operativo.

#### Polimorfismo

El polimorfismo depende de la identificación de las responsabilidades que son
comunes a un conjunto de servicios y de su separación del conjunto total de
responsabilidades de un sistema.

> [!TIP]
> Hay información disponible sobre tácticas para la facilidad de modificación
> [aquí](https://insights.sei.cmu.edu/documents/778/2007_005_001_14858.pdf).
