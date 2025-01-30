# 4 Conceptos

## BASE y consistencia eventual

Gracias al [teorema CAP](./4_CAP.md) sabemos que en los sistemas que
proporcionan alta disponibilidad a través de redundancia mediante réplicas,
dadas las propiedades de consistencia, alta disponibilidad y resiliencia a la
partición, sólo es posible cumplir a la vez dos como máximo, nunca las tres al
mismo tiempo.

Los sistemas de este tipo que priorizan la disponibilidad sobre la consistencia
suelen permitir inconsistencias por cierto tiempo, con la expectativa de que se
alcanzará un estado consistente después. Esto da lugar al llamado paradigma
BASE[^1].

[^1]: Vogels, W. (2009). Eventually Consistent. Communications of the ACM,
    January 2009, 52(1). Disponible
    [aquí](https://dl.acm.org/doi/pdf/10.1145/1435417.1435432).

https://dl.acm.org/doi/pdf/10.1145/1466443.1466448

BASE en un acrónimo [acrónimo](https://dle.rae.es/acrónimo) que referencia las
características de este tipo de sistemas: disponibilidad básica ‑***b**asic
**a**vailability* en inglés‑, estado blando ‑***s**oft state* en inglés‑ y
consistencia eventual ‑***e**ventual consistency* en inglés‑. *base* se traduce
como base, lo contrario a ácido en química, por lo que BASE sería lo contrario a
[ACID](./4_ACID.md)‑

Hay dos formas de ver la consistencia:

* Una es desde el punto de vista del desarrollador o del cliente del sistema:
  cómo observan las actualizaciones de datos.

* La otra es desde el lado del servidor: cómo fluyen las actualizaciones a
  través del sistema y qué garantías puede dar con respecto a las
  actualizaciones.

Los componentes del lado del cliente incluyen:

* Un sistema de almacenamiento. Lo trataremos como una caja
  negra, pero asumiendo que en el fondo es algo de gran escala y altamente
  distribuido, y que está construido para garantizar la durabilidad y la
  disponibilidad.

* Un proceso A. Este es un proceso que escribe y que lee desde el sistema de
  almacenamiento.

* Procesos B y C. Estos procesos son independientes del proceso A y escriben y
  leen desde el sistema de almacenamiento.Es irrelevante si estos son realmente
  procesos o sub-procesos dentro del mismo proceso; lo que es importante es que
  son independientes y que necesitan comunicarse para compartir información.

### Consistencia eventual del lado del cliente

La consistencia del lado del cliente tiene que ver con cómo y cuándo los
observadores ‑en este caso los procesos A, B o C‑ ven las actualizaciones
realizadas a los objetos de datos en el sistemas de almacenamiento.

En los siguientes ejemplos que ilustran los diferentes tipos de consistencia, el
proceso A ha realizado una actualización a un elemento de datos:

* **Consistencia fuerte**. Una vez que se completa la actualización, cualquier
  acceso posterior ‑por parte de A, B o C‑ devolverá el valor actualizado.

* **Consistencia débil**. El sistema no garantiza que los accesos posteriores
  devolverán el valor actualizado. Se deben cumplir varias condiciones antes de
  que se devuelva el valor. El período entre la actualización y el momento en el
  que se garantiza que cualquier observador siempre verá el valor actualizado se
  denomina **ventana de inconsistencia**.

* **Consistencia eventual**. Esta es una forma específica de consistencia débil:
  el sistema de almacenamiento garantiza que si no se realizan nuevas
  actualizaciones al elemento de datos, eventualmente todos los accesos devolverán
  el último valor actualizado. Si no se producen fallos, el tamaño máximo de la
  ventana de inconsistencia se puede determinar en función de factores como los
  retrasos en la comunicación, la carga del sistema y la cantidad de réplicas
  involucradas en el esquema de replicación[^2].

[^2]: El sistema más popular que implementa la consistencia eventual es el
    [sistema de nombres de
    dominio](https://datatracker.ietf.org/doc/html/rfc1034) ‑DNS por sus siglas
        en inglés *domain name system*‑. Las actualizaciones de un nombre se
    distribuyen de acuerdo con un patrón configurado y en combinación con cachés
    controlados por tiempo; finalmente, todos los clientes verán la
    actualización.

El modelo de consistencia eventual tiene varias variaciones que es importante
tener en cuenta:

* **Consistencia causal**. Si el proceso A ha comunicado al proceso B que ha
  actualizado un elemento de datos, un acceso posterior por parte del proceso B
  devolverá el valor actualizado y se garantiza que una escritura reemplazará a
  la escritura anterior. El acceso por parte del proceso C que no tiene una
  relación causal con el proceso A está sujeto a las reglas normales de
  consistencia eventual.

* **Consistencia de lectura de escrituras**. Este es un modelo importante en el
  que el proceso A, después de haber actualizado un elemento de datos, siempre
  accede al valor actualizado y nunca ve un valor anterior. Este es un caso
  especial del modelo de consistencia causal.

* **Consistencia de sesión**. Esta es una versión práctica del modelo anterior,
  en el que un proceso accede al sistema de almacenamiento en el contexto de una
  sesión. Mientras exista la sesión, el sistema garantiza la consistencia de
  lectura y escritura. Si la sesión finaliza debido a una falla, se debe crear
  una nueva sesión y las garantías no pasan de una sesión a otra.

* **Consistencia de lectura monótona**. Si un proceso ha visto un valor
  particular para el elemento de datos, cualquier acceso posterior nunca
  devolverá ningún valor anterior.

* **Consistencia de escritura monótona**. En este caso, el sistema garantiza
  serializar las escrituras por el mismo proceso. Los sistemas que no garantizan
  este nivel de consistencia son notoriamente difíciles de programar.

Se pueden combinar varias de estas propiedades. Por ejemplo, se pueden obtener
lecturas monótonas combinadas con consistencia a nivel de sesión. Desde un punto
de vista práctico, estas dos propiedades ‑lecturas monótonas y lecturas de
escrituras‑ son las más deseables en un sistema de consistencia eventual, pero
no siempre son necesarias. Estas dos propiedades hacen que sea más sencillo para
los desarrolladores crear aplicaciones, al tiempo que permiten que el sistema de
almacenamiento relaje la consistencia y proporcione alta disponibilidad.

### Consistencia eventual del lado del servidor

En el lado del servidor, debemos analizar en profundidad cómo fluyen las
actualizaciones a través del sistema para comprender qué impulsa los diferentes
modos que puede experimentar el desarrollador que utiliza el sistema.

Algunas definiciones antes de comenzar:

* $N$ es la cantidad de nodos que almacenan réplicas de los datos.

* $W$ es la cantidad de réplicas que deben confirmar la recepción de la
  actualización antes de que esta se complete.

* $R$ es la cantidad de réplicas que se contactan cuando se accede a un objeto de
  datos a través de una operación de lectura.

Si $W+R>N$, entonces el conjunto de escritura y el conjunto de lectura siempre
se superponen y se puede garantizar la consistencia fuerte.

Por ejemplo, en el escenario de un motor de bases de datos de copia de seguridad
primaria, que implementa la replicación sincrónica ‑[*availability
group*](https://learn.microsoft.com/en-us/sql/database-engine/sql-server-business-continuity-dr?view=sql-server-ver16#availability-groups)
en SQL Server por ejemplo‑, $N=2$, $W=2$ y $R=1$; sin importar desde qué réplica
lea el cliente, siempre obtendrá una respuesta coherente. En el caso de
replicación asíncrona con lectura desde la copia de seguridad habilitada ‑[*log
shipping*](https://learn.microsoft.com/en-us/sql/database-engine/sql-server-business-continuity-dr?view=sql-server-ver16#log-shipping)
en SQL Server por ejemplo‑, $N=2$, $W=1$ y $R=1$; en este caso, $R+W=N$ y no se
puede garantizar la coherencia.

El problema con estas configuraciones es que cuando debido a fallas el sistema
no puede escribir en $W$ nodos, la operación de escritura tiene que fallar, lo
que implica que el sistema no está disponible. Con $N=3$ y $W=3$ y solo dos
nodos disponibles, el sistema tendrá que fallar la escritura.

En sistemas de almacenamiento distribuido que brindan alto rendimiento y alta
disponibilidad, el número de réplicas es en general mayor que dos. Los sistemas
que se enfocan únicamente en la tolerancia a fallas a menudo usan $N=3$ ‑con
configuraciones $W=2$ y $R=2$‑.

Los sistemas que deben atender cargas de lectura muy altas a menudo replican sus
datos más allá de lo que se requiere para la tolerancia a fallas; $N$ puede ser
decenas o incluso cientos de nodos, con $R$ configurado en 1 de modo que una sola
lectura devuelva un resultado. Los sistemas que se preocupan por la consistencia
se configuran en $W=N$ para las actualizaciones, lo que puede reducir la
probabilidad de que la escritura tenga éxito. Una configuración común para estos
sistemas que se preocupan por la tolerancia a fallas pero no por la consistencia
es ejecutar con W=1 para obtener una durabilidad mínima de la actualización y
luego confiar en una técnica perezosa (epidémica) para actualizar las otras
réplicas.

La forma de configurar N, W y R depende de cuál sea el caso común y qué ruta de rendimiento se necesita optimizar. En R=1 y N=W optimizamos para el caso de lectura, y en W=1 y R=N optimizamos para una escritura muy rápida.
Por supuesto, en el último caso, la durabilidad no está garantizada en presencia de fallas, y si W < (N+1)/2, existe la posibilidad de escrituras conflictivas cuando los conjuntos de escritura no se superponen.
La consistencia débil/eventual surge cuando W+R <= N, lo que significa que
existe la posibilidad de que el conjunto de lectura y escritura no se
superpongan. Si esta es una configuración deliberada y no se basa en un caso de
falla, entonces casi no tiene sentido establecer R en algo que no sea 1. Esto
sucede en dos casos muy comunes: el primero es la replicación masiva para el
escalamiento de lectura mencionado anteriormente; El segundo es donde el acceso
a los datos es más complicado. En un modelo clave-valor simple es fácil comparar
versiones para determinar el último valor escrito en el sistema, pero en
sistemas que devuelven conjuntos de objetos es más difícil determinar cuál
debería ser el último conjunto correcto. En la mayoría de estos sistemas donde
el conjunto de escritura es más pequeño que el conjunto de réplicas, existe un
mecanismo que aplica las actualizaciones de manera diferida a los nodos
restantes en el conjunto de la réplica. El período hasta que se hayan
actualizado todas las réplicas es la ventana de inconsistencia discutida
anteriormente. Si W+R <= N, entonces el sistema es vulnerable a la lectura de
nodos que aún no han recibido las actualizaciones.

Ver también
https://learn.microsoft.com/en-us/previous-versions/msp-n-p/dn589800(v=pandp.10)
