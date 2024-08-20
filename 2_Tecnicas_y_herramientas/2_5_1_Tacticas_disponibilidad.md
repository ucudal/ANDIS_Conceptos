# 2 Técnicas y herramientas

## 2.5 Tácticas de arquitectura

### 2.5.1 Tácticas para disponibilidad

Las tácticas para lograr satisfacer el atributo de calidad de
[disponibilidad](/4_Conceptos/4_Disponibilidad.md) en arquitectura de software
tienen uno de tres propósitos: detección de fallas, recuperación de fallas o
prevención de fallas. Estas tácticas a menudo serán proporcionadas por
plataformas, *middleware* u otras infraestructuras de software, por lo que el
arquitecto debe elegir y evaluar —en lugar de implementar— las tácticas de
disponibilidad adecuadas y la combinación correcta de tácticas.

La lista de tácticas está tomada de[^1]:

[^1]: Bass, L., Clements, P., Kazman, R. (2022). Software Architecture in
    Practice, 4<sup>th</sup> edition. Addison-Wesley.

* **Monitoreo**. Refiere a la observación continua del estado de un componente
  de la arquitectura para detectar fallas o anomalías. Esta táctica permite la
  identificación temprana de problemas potenciales, lo que ayuda a prevenir
  fallas o mitigar su impacto. Por ejemplo, es posible monitorear el uso de
  recursos o el desempeño en un servidor para evitar sobrecargas y tomar acción
  antes de que se caiga.

  Ver también [Recommendations for designing a reliable monitoring and alerting
  strategy](https://learn.microsoft.com/en-us/azure/well-architected/reliability/monitoring-alerting-strategy)
  en Azure Well-Architected Framework.

* **Ping/Echo**. Es una técnica para verificar la disponibilidad de un
  componente de la arquitectura de software mediante el envío de un mensaje
  —`ping`— y la espera de una respuesta —`echo`—. Es utilizado frecuentemente
  para comprobar si un servidor o un servicio está activo y respondiendo. Por
  ejemplo, el comando `ping` en sistemas operativos para verificar la
  conectividad con una dirección IP.

* **Heartbeat** -o latido—. Es un mecanismo en el cual un componente de la
  arquitectura de software envía señales periódicas para indicar que está
  funcionando correctamente. Si la señal no es recibida dentro de un tiempo
  establecido, se asume que el sistema ha fallado. Por ejemplo, en los sistemas de alta
   disponibilidad que envían señales de vida entre los nodos de un clúster.

  Ver también [Health modeling for
  workloads](https://learn.microsoft.com/en-us/azure/well-architected/cross-cutting-guides/health-modeling)
  en Azure Well-Architected Framework.

* **Timestamp**. Consiste en asociar una marca de tiempo o *timestamp* a eventos
  o mensajes. Permite rastrear la ocurrencia de eventos en un sistema, para
  identificar cuándo ocurrió una falla. Por ejemplo, todas las entras de un
  sistema de registro —*log*— deben estar marcadas con la fecha y hora para
  facilitar el análisis de errores. En los sistemas distribuidos es complejo
  sincronizar los relojes; si eso no fuera posible, se puede usar números
  secuenciales.

* **Monitoreo de condiciones**. Es verificar condiciones específicas de
  operación para identificar anomalías. Las condiciones en tiempo de ejecución
  deben ser consistentes con las asumidas durante el diseño. Por ejemplo, el uso
  de *checksums* —sumas de verificación— es una implementación de esta táctica.

* **Control de cordura** —o *sanity check*. Es una verificación simple y rápida
  para asegurar que los valores recibidos o calculados por un componente de la
  arquitectura de software, o su estado, son razonables.

* **Voto—Replicación**. La replicación es una táctica de disponibilidad en la
  que se crean copias exactas —instancias o réplicas— de un componente para
  garantizar que, en caso de fallo de una instancia, otra esté disponible para
  tomar su lugar inmediatamente. Este enfoque asegura que la falla de una
  réplica no afecte la disponibilidad del servicio global.

  Hay dos tipos de replicación:
  * **Sincrónica:** Las réplicas están constantemente actualizadas y cualquier
    cambio se replica en tiempo real a todas ellas.
  * **Asíncrona:** Las réplicas se actualizan con un cierto retraso, lo que
    puede ser más eficiente pero introduce un riesgo de pérdida de datos
    recientes en caso de falla.

  Ver también [Recommendations for designing for
  redundancy](https://learn.microsoft.com/en-us/azure/well-architected/reliability/redundancy)
  en Azure Well-Architected Framework.

* **Voto-Redundancia funcional**. La redundancia funcional se refiere a la
  implementación de varias funciones que cumplen la misma tarea, pero de manera
  diferente; es decir, a las mismas entradas producen la misma salida, pero la
  computan de forma diferente. Esto permite que si una función falla, otra pueda realizar la
  misma tarea, garantizando la continuidad del servicio.

* **Voto-Redundancia analítica**. La redundancia analítica implica el uso de
  diferentes métodos o algoritmos para analizar el mismo conjunto de datos y
  obtener un resultado consensuado. Esta táctica es especialmente útil en
  sistemas que requieren alta precisión y fiabilidad, como en análisis de datos
  críticos o en sistemas de control industrial.

* **Detección de excepciones**. Consiste en identificar y manejar condiciones
  excepcionales que podrían causar fallos en los componentes de la arquitectura
  de software. Por ejemplo, el uso de *timeouts* para detectar fallas en otros
  componentes.

* **Auto-diagnóstico** —o *self-test*. Consiste en que un componente realice
  pruebas internas para verificar su correcto funcionamiento. Por ejemplo, un
  servicio puede ejecutar pruebas automáticas de inicio para asegurar
  que todas sus dependencias están funcionando antes de aceptar tráfico. Puede
  implicar el uso de otras tácticas, como chequeos de salud o ping/echo.

* **Repuesto redundante**. Es disponer de componentes de repuesto para
  reemplazar aquellos que fallan. Esta táctica asegura la continuidad del
  servicio en caso de fallas del hardware o software. Por ejemplo, los
  servidores en un clúster de alta disponibilidad que pueden asumir el control
  en caso de que uno falle.

  Ver también [Recommendations for designing for
  redundancy](https://learn.microsoft.com/en-us/azure/well-architected/reliability/redundancy)
  en Azure Well-Architected Framework.

* **Rollback**. Consiste en volver a un estado anterior conocido y correcto en
  caso de error o falla. Es una táctica crucial en la implementación de
  actualizaciones y cambios de los componentes. Por ejemplo, deshacer una
  actualización de software que causó problemas operativos.

  Ver también [Recommendations for designing a deployment failure mitigation
  strategy](https://learn.microsoft.com/en-us/azure/well-architected/operational-excellence/mitigation-strategy)
  en Azure Well-Architected Framework.

* **Manejo de excepciones**. Es la gestión adecuada de condiciones anómalas para
  evitar que el componente se detenga. Implica capturar y manejar excepciones en
  tiempo de ejecución para mantener la estabilidad. Por ejemplo, usar los
  mecanismos `try-catch` en lenguajes de programación para convertir las
  excepciones en mensajes de error en tiempo de ejecución.

* **Actualización de software**. Consiste en la implementación de nuevas
  versiones de software sin interrumpir el servicio. Asegura que un componente
  de la arquitectura de software puede
  seguir operando durante actualizaciones, mejorando la disponibilidad. Esta
  táctica se basa en otras como replicación o repuesto redundante para redirigir
  el tráfico a otras réplicas mientras se actualiza una de ellas, iterativamente
  hasta que se actualizan todas.

* **Re-intentos**. Es repetir una operación que falló con la esperanza de que
  tenga éxito en un segundo intento. Los re-intentos son útiles para manejar
  fallas transitorias.

  Ver también [Recommendations for handling transient
  faults](https://learn.microsoft.com/en-us/azure/well-architected/reliability/handle-transient-faults)
  en Azure Well-Architected Framework.

* **Ignorar el comportamiento fallido**. Consiste en continuar la operación a
  pesar de la ocurrencia de errores, ignorando el componente que falló. Esta
  táctica evita que una falla menor cause una parada total del sistema. Por
  ejemplo, ignorar mensajes corruptos, o fallos en dependencias que no son
  críticas.

* **Degradación elegante**. Es reducir la funcionalidad de un sistema en
  respuesta a una falla en lugar de detenerse por completo. La degradación
  controlada mantiene el servicio disponible, aunque con funcionalidad reducida.
  Por ejemplo, un sitio web puede desactivar funciones avanzadas cuando detecta
  alta carga para seguir funcionando.

* **Re-configuración**. Consiste en ajustar la configuración del sistema
  en forma dinámica para reasignar responsabilidades a otros componentes que todavía
  estén funcionando. La re-configuración puede ser manual o automática, en
  respuesta a fallas o cambios en la carga de trabajo.

* **Sombra** —o *shadow*—. Es ejecutar una instancia o réplica en paralelo
  recién iniciada para probar que funcione correctamente antes de asignarle un
  rol activo y que pueda recibir tráfico.

* **Re-sincronización del estado**. Esta táctica se usa en conjunto con la
  táctica de repuesto redundante o replicación asíncrona y consiste en
  actualizar el estado —los datos— del componente de repuesto antes de asignarle
  un rol activo y que pueda recibir tráfico.

* **Escalamiento del reinicio**. Consiste en reiniciar componentes de forma
  controlada luego de un fallo para manejar nuevos fallos potenciales sin
  afectar los demás componentes o el resto del sistema. Es útil para evitar que
  fallas menores escalen a problemas más grandes. Por ejemplo, reiniciar una
  maquina virtual en lugar de todo el hypervisor.

* **Reenvío sin pausa**. Consiste en separar las responsabilidades de control de
  las de datos, para que las de datos puedan seguir funcionando cuando fallan
  las de control, cuando la comunicación involucra rutas previamente conocidas.

* **Remoción del servicio o rejuvenecimiento de software o reinicio
  terapéutico** Es reiniciar componentes periódicamente para evitar fallas
  debido a degradación o problemas de software como *memory leaks* u *open
  connections*. Por ejemplo, rReiniciar un servidor web cada cierto tiempo para
  evitar problemas de memoria que podrían acumularse.

* **Transacciones**. Es agrupar operaciones en unidades atómicas para asegurar
  que todas se completen o ninguna lo haga. Las transacciones garantizan la
  consistencia del sistema en caso de fallos durante operaciones complejas.

* <span id="modelo_predictivo">**Modelo predictivo**. Es usar técnicas de
  aprendizaje automático y análisis predictivo para anticipar fallas antes de
  que ocurran a partir de los datos de monitoreo. Permite tomar acciones
  proactivas basadas en patrones y tendencias identificadas en los
  *logs*.</span>

* **Prevención de excepciones**. Consiste en implementar medidas para evitar que
  ocurran errores o fallas en primer lugar. El uso de bits de control de paridad
  o la verificación de redundancia cíclica son ejemplos de prevención de
  excepciones.

* **Aumentar el conjunto de competencia**. El conjunto de competencia es el
  conjunto de estados en los que un componente de la arquitectura de software
  puede operar —es competente—. Una excepción es la entrada a un estado fuera
  del conjunto de competencia. Aumentar el conjunto de estados en los que un
  componente puede operar es una forma de aumentar la disponibilidad.
