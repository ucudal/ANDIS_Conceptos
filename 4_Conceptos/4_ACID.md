# 4 Conceptos

## ACID

ACID es un [acrónimo](https://dle.rae.es/acrónimo) que referencia las cuatro
propiedades de una transacción: atomicidad, consistencia, aislamiento
—*isolation* en inglés— y durabilidad[^1].

[^1]: Haerder, T.; Reuter, A. (1983). Principles of Transaction-Oriented
    Database Recovery. ACM Computing Surveys (CSUR), 15(4). Disponible
    [aquí](https://dl.acm.org/doi/10.1145/289.291).

Compáralo con [BASE](./4_BASE.md).

La transacción básicamente refleja la idea de que las actividades de un usuario
en particular estén aisladas de todas las demás actividades concurrentes —de
otros usuarios u otros procesos—, pero restringe el grado de aislamiento y la
duración de la transacción. Típicamente una transacción es una secuencia corta
de interacciones con la base de datos, tales como encontrar o modificar un
elemento, que representa una actividad significativa en el contexto del
usuario[^1].

### Atomicidad

Las interacciones en una transacción deben ser indivisibles: o bien todas
se reflejan de forma apropiada en los datos, o bien no ocurre ningún cambio.
Además, el usuario debe saber qué ha ocurrido, en qué estado ha quedado.

La atomicidad garantiza que una transacción se trate como una sola unidad de
trabajo. Puede completarse completamente o no completarse en absoluto como si
nada hubiera ocurrido. En caso de que ocurra una falla durante una transacción,
se revierte —*rollback*— toda la transacción.

### Consistencia

Cada transacción que se completa de forma exitosa produce solamente resultados
correctos, es decir, se cumplen todas las reglas que se hayan definido.

La consistencia garantiza que una transacción mueve el conjunto de datos de un
estado válido a otro estado también válido, lo que garantiza que se cumplan
todas las reglas establecidas sobre los datos —por ejemplo la integridad
referencial—.

### Aislamiento

Los eventos en una transacción deben quedar ocultos a otras transacciones que
estén ejecutándose de forma concurrente.

El aislamiento garantiza que las transacciones se ejecuten de forma
independiente unas de otras. Los distintos motores gestionan el aislamiento a
través de niveles de aislamiento —por ejemplo, [read
committed](https://www.postgresql.org/docs/current/transaction-iso.html#XACT-READ-COMMITTED),
[repeatable
read](https://www.postgresql.org/docs/current/transaction-iso.html#XACT-REPEATABLE-READ),o
[serializable](https://www.postgresql.org/docs/current/transaction-iso.html#XACT-SERIALIZABLE))
para evitar problemas de concurrencia, como lecturas sucias o lecturas fantasma.

### Durabilidad

Una vez que una transacción se ha completado de forma exitosa, sus cambios son
permanentes, aún en el caso de un fallo del sistema.

### ACID más allá de bases de datos

Aunque el concepto surgió inicialmente en el contexto de bases de datos, hoy se
utiliza en otros contextos en los que haya manipulación y acceso a datos o
eventos.

Las plataformas de colas de mensajes garantizan la durabilidad persistiendo los mensajes
recibidos hasta que sean procesados y removidos de la cola. La atomicidad se
logra asegurando que los mensajes se entregan por completo o no se entregan; si
ocurre un error durante la transmisión de un mensaje, no se procesan mensajes
parcialmente recibidos. En algunos casos el aislamiento se logra utilizando
tópicos o múltiples colas, para asegurar que consumidores concurrentes no
interfieren entre ellos.
