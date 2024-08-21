# 2 Técnicas y herramientas

## 2.5 Tácticas de arquitectura

### 2.5.1 Tácticas para la protección

Las tácticas para [protección](/4_Conceptos/4_Proteccion.md) pueden clasificarse
ampliamente como prevención de estados inseguros, detección de estados inseguros
o remediación de estados inseguros[^1].

[^1]: Bass, L., Clements, P., Kazman, R. (2022). Software Architecture in
      Practice, 4<sup>th</sup> edition. Addison-Wesley.

Una condición previa lógica para evitar o detectar la entrada en un estado
inseguro es la capacidad de reconocer qué constituye un estado inseguro. Esto
implica que se ha realizado un FTA[^2].

[^2]: Dziak, M. (2023). Fault tree analysis (FTA). Salem Press Encyclopedia.
    Disponible
    [aquí](https://research-ebsco-com.proxy.timbo.org.uy/c/wrhwqo/viewer/html/viipaan4lv)
    via [Timbó](https://timbo.org.uy/).

Varias de las tácticas para protección aparecen también como [tácticas para
disponibilidad](/2_Tecnicas_y_herramientas/2_5_1_Tacticas_disponibilidad.md).

La lista a continuación está tomada de [^1]:

* **Sustitución** —o *substitution*—. Esta táctica emplea mecanismos de
  protección —usualmente por hardware— para controlar características
  potencialmente dañinas. Vean por ejemplo [este
  artículo](https://accelconf.web.cern.ch/ica07/papers/WPPB03.pdf) que describe
  el uso de componentes de hardware y software para proteger partes del Super
  Proton Synchrotron en el CERN. Caen dentro de esta categoría componentes como
  *watchdogs*, *interlocks* y monitores.

* **Modelo predictivo** —o *predictive model*—. Vean <a rel="noopener" href="./2_5_1_Tacticas_disponibilidad.md#modelo_predictivo:~:text=Modelo%20predictivo,logs." target="_blank">aquí</a>.

* **Control de cordura** —o *sanity check*. Vean <a rel="noopener" href="./2_5_1_Tacticas_disponibilidad.md#control_cordura:~:text=Control%20de%20cordura,razonables.">aquí</a>.

* **Comparación** —o *comparison*—. Implica verificar los resultados de ciertas
  operaciones comparándolos con los de sistemas redundantes; por lo tanto esta
  táctica se usa junto con las de redundancia mencionadas en [tácticas de
  disponibilidad](./2_5_1_Tacticas_disponibilidad.md). Esto ayuda a detectar
  fallos antes de que causen situaciones inseguras.

* **Tiempo de espera** —o *timeout*—. Un tiempo de espera define un límite
  máximo de tiempo en el que se espera una respuesta de un componente de la
  arquitectura de software. Si no se recibe una respuesta, se asume un fallo y
  se toman medidas para evitar entrar en estados inseguros causados por factores
  relacionados con el tiempo.

* **Monitoreo de condiciones**. Abre <a rel="noopener"
  href="./2_5_1_Tacticas_disponibilidad.md#monitoreo_condiciones:~:text=Monitoreo%20de%20condiciones,táctica.">esta
  página</a> en una nueva solapa o ventana.

* **Timestamp**. Abre <a rel="noopener"
  href="./2_5_1_Tacticas_disponibilidad.md#timestamp:~:text=Timestamp,secuenciales.">esta
  página</a> en una nueva solapa o ventana.

* **Replicación**. Abre <a rel="noopener"
  href="./2_5_1_Tacticas_disponibilidad.md#replicacion:~:text=Voto%E2%80%94Replicaci%C3%B3n,Framework.">esta
  página</a> en una nueva solapa o ventana.

* **Redundancia analítica**. Abre <a rel="noopener"
  href="./2_5_1_Tacticas_disponibilidad.md#redundancia_analitica:~:text=Voto-Redundancia+anal%C3%ADtica,industrial.">esta
  página</a> en una nueva solapa o ventana.

* **Redundancia funcional**. Abre <a rel="noopener"
  href="./2_5_1_Tacticas_disponibilidad.md#redundancia_funcional:~:text=Voto-Redundancia%20funcional,servicio.">esta
  página</a> en una nueva solapa o ventana.

* **Enmascaramiento** —o *masking*—. Oculta un error comparando el resultado de
  varios componentes redundantes usando un criterio de votación en caso de
  diferencias. Para que funcione tiene que ser simple y muy confiable.

* **Abortar**. Consiste en detener una operación que conduce hacia un estado
  inseguro o está en riesgo de conducir a un estado inseguro antes de que cause
  más daño.

* **Degradación**. Es la reducción deliberada de la funcionalidad del sistema en
  respuesta a un fallo, para mantener un nivel mínimo de operación segura.

* **Cortafuegos** —o *firewall*—. Limita el acceso a recursos específicos,
  típicamente procesadores, memoria, o conexiones de red.

* ***Interlock***. Protege contra fallas por la ocurrencia de eventos en un
  orden incorrecto. Vean sustitución más arriba.

* **Rollback**. Abre <a rel="noopener"
  href="./2_5_1_Tacticas_disponibilidad.md#rollback:~:text=Rollback,Framework.">esta
  página</a> en una nueva solapa o ventana.

* **Re-configuración**. Abre <a rel="noopener"
  href="./2_5_1_Tacticas_disponibilidad.md#reconfiguracion:~:text=Re-configuraci%C3%B3n,trabajo.">esta
  página</a> en una nueva solapa o ventana.

* **Reparación del estado** —o *repair state*—. Consiste en tomar acciones para
  volver a un estado seguro.
