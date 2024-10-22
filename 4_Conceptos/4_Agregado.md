# 4 Conceptos

## Agregado

Este documento está basado en [^1].

[^1]: Avram, A; Marinescu, F. Domain-Driven Design Quickly. InfoQ. Disponible
    [aquí](https://www.infoq.com/minibooks/domain-driven-design-quickly/).

Un modelo puede contener una gran cantidad de objetos del dominio, lo que
implica una gran cantidad de asociaciones, creando una complicada red de
relaciones. El desafío principal de realizar un buen modelo va de la mano de
esta idea, y es que la labor más complicada no es que el modelo sea completo,
sino que el modelo sea lo suficientemente simple y entendible. Una técnica para
simplificar un modelo es la de utilizar agregados.

Un agregado es un grupo de objetos asociados y que son considerados como una
unidad a la hora de realizar cambios en los datos. Cada agregado está compuesto
por una [entidad](./4_Entidad.md) que es denominada la **raíz** del agregado, y
esta es el único objeto del agregado que es accesible desde fuera del mismo
—esto es, por objetos que no forman parte del agregado—.

La raíz puede mantener referencias a cualquiera de los objetos del agregado, y
los otros objetos del agregado pueden mantener referencias entre ellos, pero un
objeto no perteneciente al agregado solo puede mantener referencias a la raíz
del agregado. En caso de que haya otras entidades dentro del agregado, la
identidad de estas entidades es local al mismo.

Al evitar que objetos externos tengan referencias a objetos internos del
agregado, se asegura la integridad de los datos del agregado, ya que
los objetos externos no pueden modificar los objetos internos del agregado, solo
pueden modificar el objeto raíz o pedirle al objeto raíz que modifique un objeto
interno, lo cual permite que esta operación sea controlable. Al
mismo tiempo, si el objeto raíz es eliminado, el resto de objetos del agregado
serán eliminados también, ya que no hay ningún otro objeto que mantenga una
referencia a ellos.

Para implementar un agregado, puedes seguir los siguientes pasos:

* Agrupa las entidades y los [objetos valor](./4_Objeto_Valor.md) en agregados.

* Denomina una entidad del agregado como la raíz del mismo y controla todos los
  accesos a los objetos internos del agregado a través de la raíz.

* Permite que los objetos externos del agregado mantengan una referencia a la
  raíz exclusivamente.

* Referencias transitorias a los objetos internos pueden ser pasadas fuera del
  agregado solamente para ser usados dentro de una operación. Una referencia
  transitoria puede ser, por ejemplo, una copia de un objeto valor.
