# 4 Conceptos

## Facilidad de despliegue o *deployability*

El **proceso de despliegue de software** se refiere al conjunto de actividades y
prácticas involucradas en la entrega de un sistema de software desde el entorno
de desarrollo hasta el entorno de producción donde será utilizado por los
usuarios finales. Este proceso abarca desde la compilación y prueba del software
hasta su configuración, instalación, y activación en un entorno de
producción[^1].

[^1]: Bass, L.; Clements, P.; Kazman, R. (2022). Software Architecture in
    Practice, 4<sup>th</sup> edition. Addison-Wesley.

Las etapas principales del proceso de despliegue incluyen:

1. **Compilación y empaquetado**. Transformar el código fuente en un formato
   ejecutable que pueda ser instalado y ejecutado en el entorno de
   producción[^2]. Dependiendo del ambiente esto implica generar activos
   binarios ejecutables listo para el despliegue o archivos de secuencias de
   comandos para modificar una base de datos, por ejemplo.
2. **Pruebas**. Asegurar que el software funcione correctamente en un entorno
   que imita al de producción antes de su despliegue real.
3. **Configuración**. Ajustar el software y los sistemas relacionados para que
   funcionen correctamente en el entorno de producción. Dependiendo del ambiente
   esto puede implicar cambiar las cadenas de conexión a bases de datos,
   direcciones IP, direcciones URL, por ejemplo.
4. **Implementación**. Transferir el software empaquetado al entorno de
   producción, configurarlo adecuadamente, y activarlo para que los usuarios
   puedan acceder a él.
5. **Verificación y monitoreo**. Comprobar que el software esté funcionando como
   se esperaba después del despliegue y monitorear su rendimiento para detectar
   posibles problemas.

[^2]: Algunos lenguajes interpretados como Python no necesitan compilación y se
    despliega el código fuente.

Típicamente estos pasos son llevados adelante por diferentes equipos dentro de
una organización. Mientras el primero ‑o el primero y el segundo‑ los realiza el
equipo de desarrollo ‑o *development* en inglés‑, los demás son realizados
habitualmente por el equipo de operaciones ‑u *operations* en inglés‑. De ahí
surge el término *devops*.

La facilidad de despliegue ‑o *deployability* en inglés‑ es un atributo de
calidad de la arquitectura de software que refiere a la capacidad de un sistema,
producto o componente para ser desplegado de manera eficiente y segura en
entornos de producción con un esfuerzo y demora predecibles y aceptables[^1].

Este atributo es crítico en contextos donde las actualizaciones frecuentes y los
despliegues rápidos son necesarios para mantener la competitividad o garantizar
la seguridad y el funcionamiento continuo del sistema.

El modelo de calidad de la norma ISO/IEC 25010[^3] define el concepto de
[facilidad de instalación](./4_Atributos_de_calidad.md#facilidad-de-instalación)
‑que se puede entender como equivalente‑ como la facilidad con la que un sistema,
producto o componente se puede instalar o desinstalar de forma exitosa en un
determinado entorno.

[^3]: ISO/IEC 25010. (2011). ISO/IEC 25010:2011, Systems and software
    engineering‑Systems and software Quality Requirements and Evaluation
    (SQuaRE) ‑ System and software quality models.

La facilidad de despliegue se centra en minimizar el tiempo y los esfuerzos
necesarios para llevar el código desde el desarrollo hasta su puesta en
producción. Dos factores clave influyen en la facilidad de despliegue: el tiempo
de coordinación necesario entre los diferentes
[interesados](/4_Conceptos/4_Interesado.md) antes de la implementación y el
procesamiento del código a través de una cadena de herramientas ‑o *deployment
pipeline*‑ hasta su despliegue final.

Las prácticas de *devops* buscan automatizar y optimizar este proceso para
reducir riesgos y asegurar la consistencia en los despliegues.

Este atributo también incluye consideraciones sobre cómo manejar la trazabilidad
y las versiones del software, garantizar que las actualizaciones no interrumpan
el servicio, y cómo las nuevas versiones pueden ser integradas y revertidas si
es necesario.

### Despliegue continuo

Cuando el proceso de despliegue del software descrito al comienzo se realiza en
forma completamente automática sin intervención de las personas se llama
**despliegue continuo**.

Para acelerar y automatizar el proceso se introduce el concepto de *deployment
pipeline*: La secuencia de herramientas y actividades que comienza cuando se
registra el código en un sistema de control de versiones ‑como GitHub‑ y
finaliza cuando se implementa la aplicación para que los usuarios finales puedan
utilizarla. Entre esos puntos, una serie de herramientas integran y prueban
automáticamente el código recién enviado, prueban la funcionalidad del código
integrado y prueban la aplicación para detectar problemas de rendimiento,
seguridad, etc.

El *deployment pipeline* utiliza diversos ambientes que aseguran que el software
está en condiciones antes de estar disponible para los usuarios finales. Los
cuatro ambientes clave del *deployment pipeline* son[^1]:

1. **Desarrollo** ‑o *development environment*‑. Es el ambiente en el cual los
   desarrolladores trabajan directamente con el código fuente. Aquí se realizan
   las actividades de programación, pruebas de unidad ‑o *unit tests*‑ y
   experimentación. Es un ambiente controlado y flexible donde los
   desarrolladores pueden hacer cambios y probar nuevas características
   rápidamente.
2. **Integración** ‑o *continuous integration environment*‑. En este ambiente los
   cambios realizados en el código son integrados y probados de manera continua.
   Las pruebas automáticas se ejecutan para asegurar que los cambios no rompan
   la funcionalidad existente ‑pruebas de regresión‑. Este ambiente permite
   detectar problemas de integración lo antes posible.
3. **Preproducción** ‑o *staging environment‑*. El ambiente de staging es una
   réplica cercana al ambiente de producción. Aquí se realizan pruebas de
   aceptación y validación de características en condiciones que imitan las del
   ambiente final. Este es el último paso antes del despliegue en producción y
   asegura que el software está listo para ser liberado a los usuarios.
4. **Producción** ‑o *production environment*‑. Este es el ambiente donde el
   software está disponible para los usuarios finales. Es un ambiente crítico
   que debe ser monitoreado y mantenido para asegurar la disponibilidad,
   rendimiento, y seguridad del software en operación.

Estos ambientes permiten un flujo controlado y seguro desde el desarrollo
inicial hasta la entrega final, asegurando que el software funcione
correctamente y cumpla con los requisitos de calidad en cada etapa del proceso.

Pero no todo siempre sale según lo previsto. Si se detectan problemas cuando el
software ya se encuentra en el entorno de producción, suele ser necesario volver
a una versión anterior mientras se soluciona el defecto ‑*rollback*‑.

La calidad del *deployment pipeline* se mide considerando tres factores:

1. **Tiempo de ciclo**. El tiempo que demora el software en atravesar todo el
   *pipeline*.
2. **Trazabilidad**. Es la capacidad de saber exactamente de dónde proviene cada
   artefacto y dónde se genera cada mensaje u error.
3. **Repetibilidad**. Es tener los mismos resultados cuando se realizan las
   mismas acciones sobre los mismos artefactos.

## Tácticas para la facilidad de despliegue

Vean más detalles sobre estas tácticas para la facilidad de despliegue
[aquí](/2_Tecnicas_y_herramientas/2_5_6_Tacticas_facilidad_de_despliegue.md).

<table>
  <tr>
    <td rowspan="6">
      Tácticas para la facilidad de despliegue
    </td>
    <td rowspan="3">
      Gestionar el <i>pipeline</i> de despliegue
    </td>
    <td>
      Despliegue escalonado
    </td>
  </tr>
  <tr>
    <td>
      Usar archivos de secuencias de comandos para la implementación
    </td>
  </tr>
  <tr>
    <td>
      Vuelta atrás ‑o <i>rollback</i>‑
    </td>
  </tr>
  <tr>
    <td rowspan=3>
      Gestionar el sistema desplegado
    </td>
    <td>
      Gestionar las interacciones entre servicios
    </td>
  </tr>
  <tr>
    <td>
      Empaquetar también las dependencias
    </td>
  </tr>
  <tr>
    <td>
      Apagar y encender características
    </td>
  </tr>
</table>

## Patrones para la facilidad de despliegue

Vean [Cloud design patterns that support operational
excellence](https://learn.microsoft.com/en-us/azure/well-architected/operational-excellence/design-patterns)
en Azure Well-Architected Framework.

* Arquitecturas de microservicios<br>
  Microsoft. (2024). Microservice architecture style. Disponible
  [aquí](https://learn.microsoft.com/en-us/azure/architecture/guide/architecture-styles/microservices)<br>
  Lewis, J. & Fowler, M. (2014). Microservices. Disponible
  [aquí](https://martinfowler.com/bliki/BlueGreenDeployment.html)
* Blue/green deployment<br>
  Fowler, M. (2010). Blue Green Deployment. Disponible
  [aquí](https://martinfowler.com/bliki/BlueGreenDeployment.html)
* Rolling upgrade<br>
  Wolski, A. & Laiho, K. (2004). Rolling Upgrades for Continuous Services.
  Disponible
  [aquí](https://link-springer-com.proxy.timbo.org.uy/chapter/10.1007/978-3-540-30225-4_13)
  vía Timbó.
* Canary testing<br>
  Sato, D. (2014). Canary Release. Disponible [aquí](https://martinfowler.com/bliki/CanaryRelease.html?ref=wellarchitected)
* A/B testing
