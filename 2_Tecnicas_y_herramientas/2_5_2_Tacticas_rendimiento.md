# 2 Técnicas y herramientas

## 2.5 Tácticas de arquitectura

### 2.5.2 Tácticas para rendimiento

El objetivo de las tácticas de [rendimiento](/4_Conceptos/4_Rendimiento.md) es
generar una respuesta a los eventos que llegan al sistema bajo alguna
restricción basada en el tiempo o en los recursos. El evento puede ser un evento
único o una secuencia, y es el disparador para realizar un procesamiento.

La lista de tácticas está tomada de[^1]:

[^1]: Bass, L., Clements, P., Kazman, R. (2022). Software Architecture in
      Practice, 4<sup>th</sup> edition. Addison-Wesley.

* **Gestionar los pedidos de trabajo**. Esta táctica se refiere a cómo un
  componente de la arquitectura reduce la cantidad de solicitudes o de tareas
  que recibe. Incluye dos sub-tácticas:
  * **Gestionar la llegada de eventos**. Controla cómo y cuándo los eventos son
    procesados para evitar sobrecargas. Por ejemplo, estableciendo un SLA para
    limitar la cantidad de eventos por unidad de tiempo.
  * **Gestionar la tasa de muestreo**. Ajusta la frecuencia con la que se
    procesan los eventos. Un ejemplo es reducir la frecuencia de muestreo de
    datos en un sistema IoT para disminuir la carga de procesamiento.

* **Limitar la respuesta a eventos**. Esta táctica busca limitar la cantidad de
  procesamiento que se realiza en respuesta a un evento, lo que puede incluir el
  filtrado de eventos o poner los eventos en una cola hasta que puedan ser
  procesados.

* **Priorizar los eventos**. Asigna diferentes niveles de prioridad a los
  eventos para que los más importantes o críticos se procesen antes que los
  demás. Un ejemplo es un sistema de colas donde las solicitudes de alta
  prioridad son atendidas antes que las de baja prioridad.

  Ver además [Recommendations for prioritizing the performance of critical
  flows](https://learn.microsoft.com/en-us/azure/well-architected/performance-efficiency/prioritize-critical-flows)
  en Azure Well-Architected Framework.

* **Reducir la sobrecarga computacional**. Para los eventos que llegan
  finalmente a ser procesados, reducir la cantidad de trabajo que involucra el
  procesamiento con alguna de las siguientes sub-tácticas:
  * **Reducir la indirección**. Minimiza los niveles de indirección en los
    componentes de la arquitectura, lo que reduce la complejidad y el tiempo de
    procesamiento. Un ejemplo es acceder a los datos directamente en lugar de a
    través de múltiples capas de abstracción.
  * **Co-ubicar recursos comunicados**. Agrupa recursos que se comunican
    frecuentemente para reducir el tiempo de transmisión de datos. Un ejemplo es
    almacenar datos relacionados en la misma ubicación física.
  * **Limpieza periódica**. La memoria o el sistema de archivos fragmentados
    pueden ralentizar operaciones. Reiniciar componentes o realizar tareas de
    mantenimiento para evitar la pérdida de desempeño son parte de esta táctica.

* **Limitar los tiempos de ejecución**. Establece límites en el tiempo que un
  proceso o tarea puede tomar para completar. Si una tarea excede este límite,
  se interrumpe o se maneja de otra manera. Un ejemplo es reducir la cantidad de
  iteraciones de un algoritmo aunque el resultado obtenido sea menos preciso.

* **Incrementar la eficiencia en el uso de recursos**. Optimiza los algoritmos y
  las estructuras de datos para que las tareas se realicen de la manera más
  eficiente posible.

  Ver además [Recommendations for optimizing code and
  infrastructure](https://learn.microsoft.com/en-us/azure/well-architected/performance-efficiency/optimize-code-infrastructure)
  en Azure Well-Architected Framework.

* **Aumentar los recursos**. Agregar más recursos —más y más rápidos
  procesadores, memoria, componentes de red— para mejorar la capacidad de los
  componentes de la arquitectura y reducir el tiempo de respuesta. Un ejemplo es
  escalar horizontalmente añadiendo más servidores a un clúster.

* **Introducir concurrencia**. Permite que múltiples tareas se ejecuten en
  paralelo y al mismo tiempo —en lugar de una después de la otra—, aprovechando
  la capacidad de procesamiento paralelo. Un ejemplo es usar hilos múltiples
  para manejar solicitudes concurrentes en un servidor web.

* **Mantener múltiples copias del cómputo**. Reduce la contención que podría
  ocurrir si todos el procesamiento se realiza en un mismo componente de la
  arquitectura. Servicios replicados en una arquitectura de microservicios o
  servidores web en un *pool* de servidores son ejemplos de réplicas de cómputo.

* **Mantener múltiples copias de los datos**.
  Replica datos en diferentes ubicaciones para disminuir la contención o el
  tiempo de acceso. Hay típicamente dos formas:
  * **Replicación de datos**. Los mismos datos están en más de un lugar para que
    puedan ser accedidos en paralelo y disminuir así la contención. Los datos
    deben estar sincronizados para que sean consistentes, lo cual puede ser un
    problema.
  * **Caché**. Ciertos datos accedidos frecuentemente o que conseguirlos tienen
    cierto costo pueden ser almacenados en repositorios de más rápido acceso
    —por ejemplo, en memoria, o en disco SSD—. Hay dos problemas asociados, uno
    es decidir qué datos van al caché, y el otro es cómo mantener el caché
    consistente con la fuente de datos de origen.

  Ver además [Recommendations for optimizing data
  performance](https://learn.microsoft.com/en-us/azure/well-architected/performance-efficiency/optimize-data-performance)
  en Azure Well-Architected Framework.

* **Limitar los tamaños de las colas**. Controla el tamaño de las colas de
  trabajo para evitar tiempos de espera excesivos. Generalmente se usa junto
  con la táctica de limitar la respuesta a eventos.

* **Calendarizar recursos**. Asigna recursos a los eventos basándose en un algún
  criterio para buscar que estén disponibles cuando se necesiten. Los criterios
  de asignación incluyen *first-in/first/out*, *round robin*, etc.
