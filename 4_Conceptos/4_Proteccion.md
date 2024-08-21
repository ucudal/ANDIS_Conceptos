# 4 Conceptos

## Protección o *safety*

La protección —o *safety* en inglés— es un atributo de la calidad de software
que define la capacidad de un sistema, producto o componente, en condiciones
definidas, de evitar un estado en el que se ponga en peligro la vida humana, la
salud, la propiedad o el medio ambiente[^1].

[^1]: ISO/IEC 25010. (2011). ISO/IEC 25010:2011, Systems and software
    engineering—Systems and software Quality Requirements and Evaluation
    (SQuaRE) — System and software quality models.

Esta característica se subdivide a su vez en las siguientes sub-características:

* **Restricción operativa**. Es la capacidad de un sistema, producto o
  componente para limitar su funcionamiento a unos parámetros o estados seguros
  cuando se enfrenta a un peligro operativo.
* **Identificación de riesgos**. Es la capacidad de un sistema, producto o
  componente para identificar situaciones u operaciones que pueden exponer la
  vida, la propiedad o el medio ambiente a un riesgo inaceptable.
* **Protección ante fallos**. Es la capacidad de un sistema, producto o
  componente para ponerse automáticamente en un modo de funcionamiento seguro o
  para volver a una condición segura en caso de fallo.
* **Advertencia de peligro**.  Es la capacidad de un sistema, producto o
  componente para alertar de riesgos inaceptables, de modo que puedan reaccionar
  con tiempo suficiente para mantener la seguridad de las operaciones.
* **Integración segura**. Es la capacidad de un sistema, producto o componente
  para mantener la seguridad durante y después de la integración con uno o
  varios componentes.

La definición de protección es similar en[^2], que la define como la capacidad
de un sistema para evitar desviarse hacia estados que causen o conduzcan a
daños, lesiones o pérdida de vidas a los actores de su entorno.

[^2]: Bass, L., Clements, P., Kazman, R. (2022). Software Architecture in
    Practice, 4<sup>th</sup> edition. Addison-Wesley.

Estos estados inseguros pueden ser causados ​​por una variedad de factores:

* **Omisión**. El hecho de que un evento no ocurra.
* **Comisión**. La ocurrencia espuria de un evento indeseable. El evento puede
  ser aceptable en algunos estados del sistema, pero indeseable en otros.
* **Tiempo**. Tanto el tiempo temprano —la ocurrencia de un evento antes del
  tiempo requerido— como el tardío —la ocurrencia de un evento después del
  tiempo requerido— pueden ser potencialmente problemáticos.
* **Problemas con los valores del sistema**. Estos se dividen en dos categorías:
  los valores incorrectos gruesos son incorrectos pero detectables, mientras que
  los valores incorrectos sutiles son típicamente indetectables.
* **Omisión y comisión de secuencia**. En una secuencia de eventos, falta un
  evento —omisión— o se inserta un evento inesperado —comisión—.
* **Fuera de secuencia**. Una secuencia de eventos llega, pero no en el orden
  debido.

Una vez que se detecta un estado inseguro, las posibles respuestas del sistema
son similares a las enumeradas para la [disponibilidad](./4_Disponibilidad.md).
Se debe reconocer el estado inseguro y hacer que el sistema sea seguro mediante:

* Continuar las operaciones después de recuperarse del estado inseguro o colocar
  el sistema en un modo seguro, o
* Apagarlo —fallo seguro o *fail safe*—; o
* Transición a un estado que requiera operación manual.

Además, el estado inseguro debe ser registrado e informado.

## Tácticas para la protección

Ver más detalles sobre estas tácticas para la protección
[aquí](/2_Tecnicas_y_herramientas/2_5_3_Tacticas_proteccion.md).

<table>
  <tr>
    <td rowspan="18">
      Tácticas de protección
    </td>
    <td rowspan="2" colspan="2">
      Evitar los estados desprotegidos
    </td>
    <td>
      Sustitución
    </td>
  </tr>
  <tr>
    <td>
      Modelo predictivo
    </td>
  </tr>
  <tr>
    <td rowspan="5" colspan="2">
      Detección de estados desprotegidos
    </td>
    <td>
      Control de cordura
    </td>
  </tr>
  <tr>
    <td>
      Comparación
    </td>
  </tr>
  <tr>
    <td>
      Tiempo de espera
    </td>
  </tr>
  <tr>
    <td>
      Monitoreo de condiciones
    </td>
  </tr>
  <tr>
    <td>
      Estampa de tiempo
    </td>
  </tr>
  <tr>
    <td rowspan="8">
      Contención
    </td>
    <td rowspan="3">
      Redundancia
    </td>
    <td>
      Replicación
    </td>
  </tr>
  <tr>
    <td>
      Redundancia analítica
    </td>
  </tr>
  <tr>
    <td>
      Redundancia funcional
    </td>
  </tr>
  <tr>
    <td rowspan="3">
      Limitar las consecuencias
    </td>
    <td>
      Enmascaramiento
    </td>
  </tr>
  <tr>
    <td>
      Abortar
    </td>
  </tr>
  <tr>
    <td>
      Degradación
    </td>
  </tr>
  <tr>
    <td rowspan="2">
      Barreras
    </td>
    <td>
      Cortafuegos
    </td>
  </tr>
  <tr>
    <td>
      Entrelazado
    </td>
  </tr>
  <tr>
    <td colspan="2" rowspan="3">
      Recuperación
    </td>
    <td>
       Revertir
    </td>
  </tr>
  <tr>
    <td>
      Reconfiguración
    </td>
  </tr>
  <tr>
    <td>
      Reparar el estado
    </td>
  </tr>
</table>

## Patrones para protección

Wu, W. & Kelly, T. (2004). Safety Tactics for Software Architecture Design.
368-375 Vol 1.
[10.1109/CMPSAC.2004.1342860](https://www.researchgate.net/publication/4095499_Safety_Tactics_for_Software_Architecture_Design).

## Referencias adicionales

Ovstedal, E.0. (1991). Using Fault Tree Analysis in Developing Reliable
Software. IFAC Proceedings Volumes, 24(13) 77-82. Disponible
[aquí](https://www.sciencedirect.com/science/article/pii/S1474667017513695).
