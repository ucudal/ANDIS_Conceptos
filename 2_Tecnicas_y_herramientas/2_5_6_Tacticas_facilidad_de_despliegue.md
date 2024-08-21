# 2 Técnicas y herramientas

## 2.5 Tácticas de arquitectura

### 2.5.5 Tácticas para la facilidad de despliegue

Las tácticas para lograr satisfacer el atributo de calidad de [facilidad de
despliegue](/4_Conceptos/4_Facilidad_de_despliegue.md) en arquitectura de
software tienen dos propósitos: gestionar el *pipeline* de despliegue y
gestionar el sistema desplegado.

La lista de tácticas está tomada de [^1]:

[^1]: Bass, L., Clements, P., Kazman, R. (2022). Software Architecture in
    Practice, 4<sup>th</sup> edition. Addison-Wesley.

* **Despliegue escalonado**. Consiste en desplegar nuevas versiones de
  componentes de la arquitectura de software en forma gradual a un subconjunto
  controlado de potenciales clientes o usuarios, mientras el resto de los
  clientes o usuarios continúa utilizando la versión anterior. El monitoreo de
  la nueva versión debe permitir determinar en forma automática si el
  funcionamiento del componente es correcto, en cuyo caso el subconjunto se
  amplía paulatinamente hasta alcanzar a toda la base de clientes o usuarios. De
  esta forma se minimiza el impacto que un problema en la nueva versión pueda
  tener.

* **Usar archivos de secuencias de comandos —*scripts*— para la
  implementación**. Implica la utilización de *scripts* automatizados para
  manejar el proceso de despliegue, incluyendo la configuración del entorno, la
  instalación de dependencias y la activación de servicios. De esta forma mejora
  la consistencia, se reducen los errores humanos, y se facilita la repetibilidad
  del proceso de despliegue .

* **Vuelta atrás** —o *rollback*—. Es la capacidad de revertir un despliegue a
  una versión anterior en caso de que se detecten problemas durante o después
  del despliegue. Esto incluye la restauración de datos y configuraciones a su
  estado previo. Para poder lograr el *rollback* es necesaria una trazabilidad
  detallada de todos los cambios que ocurren durante el despliegue.

* **Gestionar las interacciones entre servicios**. Esto es necesario cuando en
  el contexto de un despliegue escalonado existen versiones diferentes de
  diversos componentes y es necesario asegurar la compatibilidad. Puede ser
  necesario introducir un mediador que enrute el tráfico hacia la versión
  correcta según alguna característica de la solicitud.

* **Empaquetar también las dependencias**. Consiste en incluir dentro del mismo
  paquete de despliegue todas las dependencias necesarias para que componente
  desplegado funcione . Esto asegura que el componente se ejecute de manera
  consistente independientemente del entorno en el que se despliegue.

* **Apagar y encender características**. Permite habilitar o deshabilitar las
  nuevas funcionalidades o características del componente desplegado en tiempo de ejecución, sin
  necesidad de volver a desplegar o detener componente. Esto proporciona
  flexibilidad para activar nuevas características o desactivar las
  problemáticas.
