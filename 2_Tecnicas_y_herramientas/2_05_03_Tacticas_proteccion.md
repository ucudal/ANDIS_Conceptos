# 2 Técnicas y herramientas

## 2.5 Tácticas de arquitectura

### 2.5.1 Tácticas para la protección

Las tácticas para [protección](/4_Conceptos/4_Proteccion.md) pueden clasificarse
ampliamente como prevención de estados inseguros, detección de estados inseguros
o remediación de estados inseguros[^1].

[^1]: Bass, L.; Clements, P.; Kazman, R. (2022). Software Architecture in
      Practice, 4<sup>th</sup> edition. Addison-Wesley.

Una condición previa lógica para evitar o detectar la entrada en un estado
inseguro es la capacidad de reconocer qué constituye un estado inseguro. Esto
implica que se ha realizado un FTA[^2].

[^2]: Dziak, M. (2023). Fault tree analysis (FTA). Salem Press Encyclopedia.
    Disponible
    [aquí](https://research-ebsco-com.proxy.timbo.org.uy/c/wrhwqo/viewer/html/viipaan4lv)
    via [Timbó](https://timbo.org.uy/).

Varias de las tácticas para protección aparecen también como [tácticas para
disponibilidad](/2_Tecnicas_y_herramientas/2_05_01_Tacticas_disponibilidad.md).

La siguiente tabla —tomada de[^1]— resume las tácticas disponibles, que están
explicadas más abajo.

<table>
  <tr>
    <td rowspan="18">
      Tácticas de protección
    </td>
    <td rowspan="2" colspan="2">
      Evitar los estados desprotegidos
    </td>
    <td>
      <a href="#sustitución">Sustitución</a>
    </td>
  </tr>
  <tr>
    <td>
      <a href="#modelo-predictivo">Modelo predictivo</a>
    </td>
  </tr>
  <tr>
    <td rowspan="5" colspan="2">
      Detección de estados desprotegidos
    </td>
    <td>
      <a href="#control-de-cordura-o-sanity-check">Control de cordura o
      <i>sanity check</i></a>
    </td>
  </tr>
  <tr>
    <td>
      <a href="#comparación">Comparación</a>
    </td>
  </tr>
  <tr>
    <td>
      <a href="#tiempo-de-espera-o-timeout">Tiempo de espera o <i>timeout</i></a>
    </td>
  </tr>
  <tr>
    <td>
      <a href="#monitoreo-de-condiciones">Monitoreo de condiciones</a>
    </td>
  </tr>
  <tr>
    <td>
      <a href="#timestamp"><i>Timestamp</i></a>
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
      <a href="#replicación">Replicación</a>
    </td>
  </tr>
  <tr>
    <td>
      <a href="#redundancia-analítica">Redundancia analítica</a>
    </td>
  </tr>
  <tr>
    <td>
      <a href="#redundancia-funcional">Redundancia funcional</a>
    </td>
  </tr>
  <tr>
    <td rowspan="3">
      Limitar las consecuencias
    </td>
    <td>
      <a href="#enmascaramiento-o-masking">Enmascaramiento o <i>masking</i></a>
    </td>
  </tr>
  <tr>
    <td>
      <a href="#abortar">Abortar</a>
    </td>
  </tr>
  <tr>
    <td>
      <a href="#degradación">Degradación</a>
    </td>
  </tr>
  <tr>
    <td rowspan="2">
      Barreras
    </td>
    <td>
      <a href="#cortafuegos-o-firewall">Cortafuegos o <i>firewall</i></a>
    </td>
  </tr>
  <tr>
    <td>
      <a href="#interlock"><i>Interlock</i></a>
    </td>
  </tr>
  <tr>
    <td colspan="2" rowspan="3">
      Recuperación
    </td>
    <td>
       <a href="#rollback"><i>Rollback</i></a>
    </td>
  </tr>
  <tr>
    <td>
      <a href="#re-configuración">Re-configuración</a>
    </td>
  </tr>
  <tr>
    <td>
      <a href="#reparación-del-estado-o-repair-state">Reparación del estado</a>
    </td>
  </tr>
</table>

#### Sustitución

Esta táctica emplea mecanismos de protección ‑usualmente por hardware‑ para
controlar características potencialmente dañinas. Vean por ejemplo [este
artículo](https://accelconf.web.cern.ch/ica07/papers/WPPB03.pdf) que describe el
uso de componentes de hardware y software para proteger partes del Super Proton
Synchrotron en el CERN. Caen dentro de esta categoría componentes como
*watchdogs*, *interlocks* y monitores.

#### Modelo predictivo

Está explicado [aquí](./2_05_01_Tacticas_disponibilidad.md#modelo-predictivo).

#### Control de cordura o *sanity check*

Está explicado [aquí](./2_05_01_Tacticas_disponibilidad.md#control-de-cordura-o-sanity-check)

#### Comparación

Implica verificar los resultados de ciertas operaciones comparándolos con los de
sistemas redundantes; por lo tanto esta táctica se usa junto con las de
redundancia mencionadas en [tácticas de
disponibilidad](./2_05_01_Tacticas_disponibilidad.md#voto-replicación). Esto ayuda
a detectar fallos antes de que causen situaciones inseguras.

#### Tiempo de espera o *timeout*

Un tiempo de espera define un límite máximo de tiempo en el que se espera una
respuesta de un componente de la arquitectura de software. Si no se recibe una
respuesta, se asume un fallo y se toman medidas para evitar entrar en estados
inseguros causados por factores relacionados con el tiempo.

#### Monitoreo de condiciones

Está explicado
[aquí](./2_05_01_Tacticas_disponibilidad.md#monitoreo-de-condiciones).

#### *Timestamp*

Está explicado [aquí](./2_05_01_Tacticas_disponibilidad.md#timestamp).

#### Replicación

Está explicado [aquí](./2_05_01_Tacticas_disponibilidad.md#voto-replicación).

#### Redundancia analítica

Está explicado
[aquí](./2_05_01_Tacticas_disponibilidad.md#voto-redundancia-analítica).

#### Redundancia funcional

Está explicado
[aquí](./2_05_01_Tacticas_disponibilidad.md#voto-redundancia-funcional).

#### Enmascaramiento o *masking*

Oculta un error comparando el resultado de varios componentes redundantes usando
un criterio de votación en caso de diferencias. Para que funcione tiene que ser
simple y muy confiable.

#### Abortar

Consiste en detener una operación que conduce hacia un estado inseguro, o que
está en riesgo de conducir a un estado inseguro, antes de que cause más daño.

#### Degradación

Es la reducción deliberada de la funcionalidad del sistema en respuesta a un
fallo, para mantener un nivel mínimo de operación segura.

#### Cortafuegos o *firewall*

Limita el acceso a recursos específicos, típicamente procesadores, memoria, o
conexiones de red.

#### *Interlock*

Protege contra fallas por la ocurrencia de eventos en un orden incorrecto. Vean
sustitución más arriba.

#### *Rollback*

Está explicado [aquí](./2_05_01_Tacticas_disponibilidad.md#rollback).

#### Re-configuración

Está explicado [aquí](./2_05_01_Tacticas_disponibilidad.md#re-configuración).

#### Reparación del estado o *repair state*

Consiste en tomar acciones para volver a un estado seguro.
