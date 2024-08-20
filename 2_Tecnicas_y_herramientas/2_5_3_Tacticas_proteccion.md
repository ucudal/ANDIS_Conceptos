# 2 Técnicas y herramientas

## 2.5 Tácticas de arquitectura

### 2.5.1 Tácticas para protección

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

* **Modelo predictivo** —o *predictive model*—. Ver <a
  href="./2_5_1_Tacticas_disponibilidad.md#modelo_predictivo:~:text=Modelo%20predictivo,logs.">aquí</a>.

* **Control de cordura** —o *sanity check*. Es una verificación simple y rápida
  para asegurar que los valores recibidos o calculados por un componente de la
  arquitectura de software, o su estado, son razonables.

* **Comparación** —o *comparison*—. Implica verificar los resultados de ciertas
  operaciones comparándolos con los de sistemas redundantes; por lo tanto esta
  táctica se usa junto con las de redundancia mencionadas en [tácticas de disponibilidad](./2_5_1_Tacticas_disponibilidad.md). Esto ayuda a
  detectar fallos antes de que causen situaciones inseguras.

* **Tiempo de espera** —o *timeout*—. Un tiempo de espera define un límite
  máximo de tiempo en el que se espera una respuesta de un componente de la
  arquitectura de software. Si no se recibe una respuesta, se asume un fallo y
  se toman medidas para evitar entrar en estados inseguros causados por factores
  relacionados con el tiempo.

* **Monitoreo de condiciones**. Es verificar condiciones específicas de
  operación para identificar anomalías. Las condiciones en tiempo de ejecución
  deben ser consistentes con las asumidas durante el diseño. Por ejemplo, el uso
  de *checksums* —sumas de verificación— es una implementación de esta táctica.

* **Timestamp**. Consiste en asociar una marca de tiempo o *timestamp* a eventos
  o mensajes. Permite detectar inconsistencias en el orden en el que deberían
  arribar los eventos para evitar entrar en estados inseguros causados por
  factores relacionados con el tiempo. En los sistemas distribuidos es complejo
  sincronizar los relojes; si eso no fuera posible, se puede usar números
  secuenciales.

### **Replication (Replicación)**
   - **Descripción:** La replicación se refiere a la duplicación de componentes críticos para garantizar que, si uno falla, otro pueda asumir su función, asegurando así la seguridad del sistema.
   - **Ejemplo:** Un sistema de frenado de un tren podría tener múltiples sensores de velocidad, de modo que si uno falla, otro puede proporcionar la información necesaria para detener el tren de manera segura.

#### **Analytical redundancy (Redundancia analítica)**
   - **Descripción:** La redundancia analítica implica el uso de diferentes métodos para calcular o medir lo mismo y comparar los resultados para detectar y corregir fallos.
   - **Ejemplo:** En un sistema de navegación de un avión, varios algoritmos independientes calculan la posición, y si uno falla o produce un resultado inconsistente, los otros pueden detectar y corregir el error.

#### **Functional redundancy (Redundancia funcional)**
   - **Descripción:** La redundancia funcional consiste en tener múltiples componentes que realizan la misma función crítica, asegurando que si uno falla, otro puede continuar la operación segura.
   - **Ejemplo:** Un sistema de control de vuelo puede tener varios actuadores para los alerones del avión, de modo que si uno falla, otro puede tomar el control.

#### **Masking (Enmascaramiento)**
   - **Descripción:** El enmascaramiento es la técnica de ocultar fallos menores o no críticos para prevenir que se conviertan en condiciones peligrosas, asegurando que el sistema siga operando de manera segura.
   - **Ejemplo:** Si un sensor en un sistema médico tiene un pequeño fallo, el sistema puede enmascararlo temporalmente usando datos de otros sensores hasta que se realice una verificación más exhaustiva.

#### **Abort (Abortar)**
   - **Descripción:** Abortar implica detener una operación que está en peligro de convertirse en insegura, para evitar que el sistema entre en un estado peligroso.
   - **Ejemplo:** En un sistema de lanzamiento de cohetes, si se detecta un fallo crítico durante la cuenta regresiva, se aborta el lanzamiento para evitar un desastre.

#### **Degradation (Degradación)**
   - **Descripción:** La degradación es la reducción deliberada de la funcionalidad del sistema en respuesta a un fallo, para mantener un nivel mínimo de operación segura.
   - **Ejemplo:** Si un motor de un avión falla, el sistema puede degradarse a un modo de operación con un solo motor, permitiendo un aterrizaje seguro en lugar de un fallo catastrófico.

#### **Firewall (Cortafuegos)**
   - **Descripción:** En el contexto de la protección, un firewall puede referirse a un mecanismo que previene la propagación de fallos desde una parte del sistema a otra, manteniendo la integridad y seguridad del sistema global.
   - **Ejemplo:** En un reactor nuclear, las barreras físicas y lógicas evitan que un fallo en una sección se propague a otras, protegiendo la integridad del reactor.

#### **Interlock (Enclavamiento)**
   - **Descripción:** Un enclavamiento es un mecanismo de seguridad que asegura que ciertas condiciones se cumplan antes de permitir una operación, previniendo acciones peligrosas.
   - **Ejemplo:** En un sistema de control industrial, una máquina no puede empezar a operar hasta que todas las protecciones estén en su lugar, como puertas cerradas y sistemas de enfriamiento activos.

#### **Rollback (Retroceso)**
   - **Descripción:** El retroceso es la acción de revertir un sistema a un estado anterior seguro después de que se detecta un fallo, evitando que el sistema opere en un estado inseguro.
   - **Ejemplo:** En un sistema de control de tráfico ferroviario, si se detecta un error en una nueva configuración, se realiza un rollback a la configuración anterior que se sabe que es segura.

#### **Reconfiguration (Reconfiguración)**
   - **Descripción:** La reconfiguración implica cambiar la disposición o la configuración de los componentes del sistema en respuesta a un fallo, con el objetivo de mantener la operación segura.
   - **Ejemplo:** Si un módulo de un sistema de control de procesos falla, el sistema puede reconfigurar automáticamente otros módulos para asumir las funciones del módulo fallido, manteniendo la operación segura.

#### **Repair state (Estado de reparación)**
   - **Descripción:** El estado de reparación se refiere a la capacidad del sistema de entrar en un estado donde se pueden realizar reparaciones sin comprometer la seguridad del sistema o interrumpir operaciones críticas.
   - **Ejemplo:** Un sistema de energía eléctrica que permite la reparación de una línea mientras redirige la carga a otras líneas, asegurando la continuidad del suministro sin riesgo.

Estas tácticas se enfocan en mantener la seguridad operativa de un sistema, incluso en presencia de fallos o condiciones adversas, asegurando que el sistema funcione sin poner en peligro a los usuarios o al entorno.
