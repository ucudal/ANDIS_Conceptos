# 2 Técnicas y herramientas

## 2.5 Tácticas de arquitectura

### 2.5.6 Tácticas para la facilidad de despliegue

Las tácticas para lograr satisfacer el atributo de calidad de [facilidad de
despliegue](/4_Conceptos/4_Facilidad_de_despliegue.md) en arquitectura de
software tienen dos propósitos: gestionar el *pipeline* de despliegue y
gestionar el sistema desplegado.

La siguiente tabla —tomada de[^1]— resume las tácticas disponibles, que están
explicadas más abajo.

[^1]: Bass, L.; Clements, P.; Kazman, R. (2022). Software Architecture in
    Practice, 4<sup>th</sup> edition. Addison-Wesley.

<table>
  <tr>
    <td rowspan="6">
      Tácticas para la facilidad de despliegue
    </td>
    <td rowspan="3">
      Gestionar el <i>pipeline</i> de despliegue
    </td>
    <td>
      <a href="#despliegue-escalonado">Despliegue escalonado</a>
    </td>
  </tr>
  <tr>
    <td>
      <a href="#usar-archivos-de-secuencias-de-comandos-o-scripts-para-la-implementación">
      Usar archivos de secuencias de comandos para la implementación</a>
    </td>
  </tr>
  <tr>
    <td>
      <a href="#vuelta-atrás-o-rollback">Vuelta atrás o <i>rollback</i></a>
    </td>
  </tr>
  <tr>
    <td rowspan=3>
      Gestionar el sistema desplegado
    </td>
    <td>
      <a href="#gestionar-las-interacciones-entre-servicios">Gestionar las
      interacciones entre servicios</a>
    </td>
  </tr>
  <tr>
    <td>
      <a href="#empaquetar-también-las-dependencias">Empaquetar también las
      dependencias</a>
    </td>
  </tr>
  <tr>
    <td>
      <a href="#apagar-y-prender-características">Apagar y encender
      características</a>
    </td>
  </tr>
</table>

#### Despliegue escalonado

Consiste en desplegar nuevas versiones de componentes de la arquitectura de
software en forma gradual a un subconjunto controlado de potenciales clientes o
usuarios, mientras el resto de los clientes o usuarios continúa utilizando la
versión anterior. El monitoreo de la nueva versión debe permitir determinar en
forma automática si el funcionamiento del componente es correcto, en cuyo caso
el subconjunto se amplía paulatinamente hasta alcanzar a toda la base de
clientes o usuarios. De esta forma se minimiza el impacto que un problema en la
nueva versión pueda tener.

#### Usar archivos de secuencias de comandos o *scripts* para la implementación

Implica la utilización de *scripts* automatizados para
manejar el proceso de despliegue, incluyendo la configuración del entorno, la
instalación de dependencias y la activación de servicios. De esta forma mejora
la consistencia, se reducen los errores humanos, y se facilita la repetibilidad
del proceso de despliegue.

> [!TIP]
> Vean además [Infrastructure as
> Code](https://www.linode.com/docs/guides/introduction-to-infrastructure-as-code/)
> en el blog de Akamai y [What is infrastructure as
> code?](https://learn.microsoft.com/en-us/devops/deliver/what-is-infrastructure-as-code)
> en el sitio de DevOps de Microsoft.

#### *Rollback*

Está explicado [aquí](./2_05_01_Tacticas_disponibilidad.md#rollback).

#### Gestionar las interacciones entre servicios

Esto es necesario cuando en el contexto de un despliegue escalonado existen
versiones diferentes de diversos componentes y es necesario asegurar la
compatibilidad. Puede ser necesario introducir un mediador que enrute el tráfico
hacia la versión correcta según alguna característica de la solicitud.

#### Empaquetar también las dependencias

Consiste en incluir dentro del mismo
paquete de despliegue todas las dependencias necesarias para que componente
desplegado funcione . Esto asegura que el componente se ejecute de manera
consistente independientemente del entorno en el que se despliegue.

#### Apagar y prender características

Permite habilitar o deshabilitar las nuevas funcionalidades o características
del componente desplegado en tiempo de ejecución, sin necesidad de volver a
desplegar o detener componente. Esto proporciona flexibilidad para activar
nuevas características o desactivar las problemáticas.
