# 4 Conceptos

## *Repository*

Este documento está basado en el libro "Domain-Driven Design Quickly" [^1].

[^1]: Avram, A; Marinescu, F. Domain-Driven Design Quickly. InfoQ. Disponible
    [aquí](https://www.infoq.com/minibooks/domain-driven-design-quickly/).

En la programación orientada a objetos, uno debe tener referencias a objetos
para poder utilizarlos. Un *Repository* —repositorio, en español— es un concepto
utilizado con el fin de encapsular la lógica de obtener estas referencias a
objetos. El repositorio actúa como el lugar centralizado en el cual obtener
referencias a objetos que son accesibles globalmente.

Para desacoplar la capa del dominio de la capa de infraestructura, el
repositorio provee una interfaz amigable para el dominio, por más que usualmente
esté asociado internamente a la capa de infraestructura para poder recuperar
objetos existentes en la misma, por ejemplo: en la base de datos.

Para implementar un repositorio, puedes seguir los siguientes pasos:

* Para cada tipo de objeto que requiera ser accedido globalmente, crea un objeto
  que provea la ilusión de una colección de objetos en memoria para ese tipo.

* Crea una interfaz independiente para el repositorio, declarando métodos para
  agregar, remover y obtener objetos, los cuales encapsularán la lógica
  relacionada a estas operaciones en el almacén de datos.

* Provee repositorios solamente para las raíces de [agregados](./4_Agregado.md)
  que requieran acceso directo.

Implementando un repositorio, puedes mantener la lógica del cliente enfocada al
modelo, delegando a los repositorios la lógica del almacenamiento y acceso a
objetos.

Hay una relación entre el patrón [*Factory*](./4_Factory.md) y *Repository*, ya
que ambos ayudan a manejar el ciclo de vida de los objetos del dominio, pero no
son lo mismo. El patrón Factory concierne exclusivamente a la **creación** de
objetos, mientras que *Repository* se encarga de la **obtención** de objetos ya
creados. Ejemplificando, al agregar un nuevo objeto a un repositorio, el objeto
debe ser creado primero (usando la fábrica), y luego de ser creado puede ser
almacenado en el repositorio.