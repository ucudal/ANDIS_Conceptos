# 2 Técnicas y herramientas

## 2.8 Patrones de diseño

### *Aggregate*

Este documento está basado en [^2] y [^1].

[^2]: Evans, E. (2015). Domain-Driven Design Reference: Definitions and Pattern
    Summaries. Domain Language, Inc. Disponible
    [aquí](https://www.domainlanguage.com/wp-content/uploads/2016/05/DDD_Reference_2015-03.pdf).

[^1]: Avram, A; Marinescu, F. (2006). Domain-Driven Design Quickly. InfoQ.
    Disponible
    [aquí](https://www.infoq.com/minibooks/domain-driven-design-quickly/).

Un modelo puede contener una gran cantidad de objetos del
[dominio](../4_Conceptos/4_Dominio.md) y una gran cantidad de asociaciones entre estos
objetos, creando una complicada red de referencias entre ellos. El desafío
principal de realizar un buen modelo va de la mano de esta idea, y es que la
labor más complicada no es que el modelo sea completo, sino que el modelo sea lo
suficientemente simple y entendible.

En el contexto de *Domain-Driven Design* ‑DDD, por sus siglas‑, una técnica para
simplificar un modelo es la de utilizar agregados.

<<<<<<< HEAD:2_Tecnicas_y_herramientas/2_8_Aggregate.md
Un agregado es un grupo de objetos asociados ‑[entidades](./2_8_Entity.md) y
[objetos valor](./2_8_Value_Object.md)‑ que son considerados como una unidad a la
=======
Un agregado es un grupo de objetos asociados ‑[entidades](./4_Entidad.md) y
[objetos valor](./4_Objeto_Valor.md)‑ que son considerados como una unidad a la
>>>>>>> main:4_Conceptos/4_Agregado.md
hora de realizar cambios en los datos.

Una de las entidades es denominada la **raíz** del agregado. La raíz puede
mantener referencias a cualquiera de los objetos del agregado, y los otros
objetos del agregado pueden mantener referencias entre ellos, pero un objeto no
perteneciente al agregado solo puede mantener referencias a la raíz del
agregado. En caso de que haya otras entidades dentro del agregado, la identidad
de estas entidades es local al agregado.

Al evitar que objetos externos tengan referencias a objetos internos del
agregado, se asegura la integridad de los datos del agregado, ya que los objetos
externos no pueden modificar los objetos internos del agregado, solo pueden
modificar el objeto raíz o pedirle al objeto raíz que modifique un objeto
interno, lo cual permite que esta operación sea controlable. Al mismo tiempo, si
el objeto raíz es eliminado, el resto de objetos del agregado serán eliminados
también, ya que no hay ningún otro objeto que mantenga una referencia a ellos.

El uso de agregados permite establecer mejores límites para las transacciones y
para la distribución de los datos persistidos de los objetos:

* Dentro del agregado, las actualizaciones son sincrónicas y la consistencia,
  que es fuerte, se logra usando transacciones.

* Fuera del agregado, las actualizaciones son asíncronas y la consistencia es
  eventual.

* Los datos del agregado se mantienen dentro del mismo nodo en el que reside el
  cómputo que gestiona el agregado, por ejemplo, su [repositorio](./2_8_Repository.md).

* Los datos de diferentes agregados pueden estar en nodos diferentes.

Para implementar un agregado, puedes seguir los siguientes pasos:

* Agrupa las entidades y los objetos valor en agregados.

* Elije una entidad del agregado para que sea su raíz y controla todos los
  accesos a los objetos internos del agregado a través de la raíz.

* Permite que los objetos externos al agregado mantengan una referencia a la
  raíz exclusivamente.

* Referencias transitorias a los objetos internos pueden ser pasadas fuera del
  agregado solamente para ser usados dentro de una operación. Una referencia
  transitoria puede ser, por ejemplo, una copia de un objeto valor.
