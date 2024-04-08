# Introducción

Antes que nada, gracias por considerar contribuir con esta iniciativa. Son las
personas como tú las que hacen que sea una herramienta útil para estudiantes,
profesores y tutores.

Esta guía está basada [en esta](https://github.com/nayafia/contributing-template)
y [esta otra](https://github.com/valerybriz/contributing-template).

Al seguir estas guías estás comunicando que tú respetas el tiempo de las y los
que estamos involucrados en esta iniciativa. A cambio, ellas y ellos deberían de
forma reciproca resolver tus *issues*, revisar los cambios y ayudarte a finalizar
tus *pull requests*.

¡Mantén la mente abierta! Mejorar la documentación sugiriendo nuevas entradas o
reportar los errores que encuentres son ejemplos de contribuciones que ayudan a
mejorar esta iniciativa.

# Reglas de base

Esperamos que quienes quieran contribuir asuman las siguientes responsabilidades:

* Asegúrate de la compatibilidad entre plataformas para cada cambio aceptado:
Windows, Mac, Linux.
* Crea *issues* para cualquier cambio mayor y mejora que desearías hacer. Discute
las cosas de manera transparente y obtén los comentarios de la comunidad.
* No agregues nuevos archivos a menos de que sea completamente necesario.
* Mantén el versionamiento de las cosas que agregues tan cortos como sea posible.
* Se amable con las y los recién llegados y apoya la diversidad de nuevas y nuevos
contribuidores de todo tipo de antecedente. Revisa el [código de conducta de la
comunidad Python](https://www.python.org/psf/codeofconduct/).

# Tu primera contribución
Ayuda a la gente que es nueva en el proyecto a que entiendan donde pueden ser de apoyo. Este es un buen momento también para dejarle saber a las personas si sigues alguna convención para etiquetar issues para principiantes.

> Aun no sabes como empezar a contribuir con Atom? Puedes empezar revisando los issues con etiquetas principiante (beginner) y se-necesita-ayuda (help-wanted):
> Beginner (principiante) - los issues con esta etiqueta deberían de requerir unicamente unas pocas lineas de código y uno o dos tests.
> Help wanted (se necesita ayuda) - Estos son issues que pueden ser un poco más complicados que los issues de principiantes.
> Ambas listas de issues están ordenadas por la cantidad de comentarios que tienen. Aunque no es perfecto, la cantidad de comentarios es un proxy rasonable para saber el impacto que tendrá el cambio.

[source: [Atom](https://github.com/atom/atom/blob/master/CONTRIBUTING.md#your-first-code-contribution)] **Necesitas más inspiración?** [1] [Read the Docs](http://docs.readthedocs.org/en/latest/contribute.html#contributing-to-development) [2] [Django](https://docs.djangoproject.com/en/dev/internals/contributing/new-contributors/#first-steps) (baja en el scroll hasta "Guidelines" también)

### Puntos de Bonus: Agrega un enlace a recursos para personas que nunca han contribuido anteriormente.
Aquí hay algunos tutoriales que puedes incluir: http://makeapullrequest.com/ y http://www.firsttimersonly.com/

> Trabajando en tu primer Pull Request? Puedes aprender como en esta *free* series, [Cómo contribuir a un proyecto de Código abierto en GitHub](https://egghead.io/series/how-to-contribute-to-an-open-source-project-on-github).

[fuente: [React](https://github.com/facebook/react/blob/master/CONTRIBUTING.md#pull-requests)]

Cómo nota, es bastante util usar lenguaje amigable con las personas recien llegadas en todo el documento. Aquí algunos ejemplos de [Active Admin](https://github.com/activeadmin/activeadmin/blob/master/CONTRIBUTING.md):

>En este punto, ya estas preparada o preparado para hacer cambios! Sientete libre de pedir ayuda; todos fuimos principiantes una vez :smile_cat:
>
>Si un maintainer te pide que hagas un "rebase" al PR, ellos se refieren a que muchisimo código a cambiado y que deberías actualizar la rama para que sea más facil unirla al resto del código.

# Empezando
### Dales un rapido tour de como hacer submit a una contribución.
Cómo escribes esto, depende de tí, pero algunas cosas que debería incluir son:

* Dejales saber si necesitan firmar un CLA, estar de acuerdo con un DCO, o cualquier otra documentación legal que se necesite
* Si los tests son necesarios para las contribuciones, hazles saber y explicales como ejecutar estos tests.
* Si estas usando algo distinto de GitHub para manejar tus issues (ej. JIRA or Trac), hazles saber que herramientas necesitan para contribuir

>Para cualquier cosa que sea mayor a una o dos lineas para corregir:

>1. Crea tu propio fork del código
>2. Haz los cambios en tu fork
>3. Si te gusta el cambio y crees que el proyecto podría utilizarlo:
    * Asegurate de haber seguido el estilo de código del proyecto.
    * Firma el Contributor License Agreement, CLA, con la Fundación jQuery.
    * Revisa el Código de conducta de la Fundación jQuery.
    * Envia un pull request indicando que tienes un archivo con el CLA.

[fuente: [Requirejs](http://requirejs.org/docs/contributing.html)] **Necesitas más inspiración?** [1] [Active Admin](https://github.com/activeadmin/activeadmin/blob/master/CONTRIBUTING.md#1-where-do-i-go-from-here) [2] [Node.js](https://github.com/nodejs/node/blob/master/CONTRIBUTING.md#code-contributions) [3] [Ember.js](https://github.com/emberjs/ember.js/blob/master/CONTRIBUTING.md#pull-requests)

### Si tienes un proceso diferente para correcciones pequeñas u "obvias", hazlo saber.

> Pequeñas contribuciones como errores de ortografía, donde el contenido es lo suficientemente pequeño como para no considerado propiedad intelectual, puede ser agregado como un patch de contribuidor, sin el CLA.
>
>Como regla de oro, los cambios pueden ser considerados "correcciones obvias" si estos no introducen una nueva funcionalidad o pensamiento creativo. Media vez el cambio no afecte la funcionalidad, algunos ejemplos incluyen los siguientes:
>* Correcciones de Ortografía / Gramática
>* Corrección de un error en la escritura de una palabra, espacios en blanco y cambios de formato
>* Limpieza de comentarios
>* Corrección de Bugs que cambian los valores que se retornan o códigos de error guardados en constantes
>* Agregar mensajes de logueo o salidas de debugging
>* Cambios a los archivos de ‘metadata’ como Gemfile, .gitignore, scripts de construcción, etc.
>* Mover archivos con código de un directorio o paquete a otro

[fuente: [Chef](https://github.com/chef/chef/blob/master/CONTRIBUTING.md#chef-obvious-fix-policy)] **Necesitas más inspiración?** [1] [Puppet](https://github.com/puppetlabs/puppet/blob/master/CONTRIBUTING.md#making-trivial-changes)

# Cómo reportar un bug
### Explica primero cuales son las formas de revelación de fallos en seguridad primero!
Como mínimo, incluye la siguiente oración:
> Si encuentras una vulnerabilidad de seguridad, NO abras un issue con la explicación. En vez de eso, envía un email a XXXX.

Si no quieres usar tu información personal, establece una dirección como "seguridad@xxxxx". Proyectos más grandes suelen tener procesos más formales para comunicar cuestiones de seguridad, incluyendo comunicación encriptada. (Disclosure: No soy un experto en seguridad.)

> Cualquier issue de seguridad debe ser enviado directamente a security@travis-ci.org
> Para poder determinar si estas tratando con un error de seguridad, hazte las siguientes preguntas:
> * Puedo accesar a algo que no es mío, o algo que no debería de tener acceso?
> * Puedo deshabilitar algo para otras personas?
>
> Si la respuesta a cualquiera de esas dos preguntas es "Si", entonces probablemente estas lideando con un problema de seguridad. Nota que aún cuando la respuesta es "no" a ambas preguntas, aún podrías estar lideando con un issue de seguridad, si no estas seguro, envianos un email a security@travis-ci.org.

[fuente: [Travis CI](https://github.com/travis-ci/travis-ci/blob/master/CONTRIBUTING.md)] **Necesitas más inspiración?** [1] [Celery](https://github.com/celery/celery/blob/master/CONTRIBUTING.rst#security) [2] [Express.js](https://github.com/expressjs/express/blob/master/Security.md)

### Dile a tus contribuidores como crear un reporte de bug.
También puedes incluir una plantilla para que las personas puedan hacer un copy-paste (de nuevo, menos trabajo para tí).

> Cuando llenas un issue, asegurate de responder estas cinco preguntas:
>
> 1. Qué version de Go estas usando(go version)?
> 2. Qué sistema operativo y que procesador estas usando?
> 3. Qué hiciste?
> 4. Qué esperabas ver?
> 5. Qué viste en lugar de ello?
> Preguntas generales deberían de ir la lista de correos de golang-nuts en vez del issue tracker. Las y los gophers que estén allí te indicarán si es necesario abrir un issue cuando encontraste un bug.

[fuente: [Go](https://github.com/golang/go/blob/master/CONTRIBUTING.md#filing-issues)] **Necesitas más inspiración?** [1] [Celery](https://github.com/celery/celery/blob/master/CONTRIBUTING.rst#other-bugs ) [2] [Atom](https://github.com/atom/atom/blob/master/CONTRIBUTING.md#reporting-bugs) (incluye plantilla)

# Cómo sugerir una nueva característica
### Si tienes un plan en particular, metas, o filosofía de desarrollo, compartela aquí.
Esta información le dara a los contribuidores contexto antes de hacer sugerencias que puede no estén alineadas con lo que el proyecto necesita.

> La filosofía Express se trata de proveer un pequeño pero robusto set de herramientas para servidores HTTP, haciendolo una gran solución para aplicaciones de una sola página, web sites, híbridos, APIs HTTP publicas.
>
> Express no te forza a utilizar ningún ORM específico. Con soporte para al rededor de 14 motores de plantillas vía Consolidate.js, puedes facilmente crear un framework perfecto.

[fuente: [Express](https://github.com/expressjs/express#philosophy)] **Necesitas más inspiración?** [Active Admin](https://github.com/activeadmin/activeadmin#goals)

### Explica tu proceso deseado para sugerir una nueva característica.
Si hay una ida y vuelta o cierre de sesion requerido, dilo. Pideles que escriban el alcance de la nueva caracteristica, con la idea de porque es necesaria y como podría funcionar.

> Si te encuentras desdeando una característica que no existe en Elasticsearch, probablemente no estas solo. Puede ser que otras personas tengan necesidades similares. Muchas de las características que Elasticsearch tiene el día de hoy han sido agregadas gracias a que nuestros usuarios vieron la necesidad. Abre un issue en la lista de issues de GitHub que describa la característica que te gustaría ver, porqué la necesitas y como debería funcionar.

[fuente: [Elasticsearch](https://github.com/elastic/elasticsearch/blob/master/CONTRIBUTING.md#feature-requests)] **Necesitas más inspiración?** [1] [Hoodie](https://github.com/hoodiehq/hoodie/blob/master/CONTRIBUTING.md#feature-requests) [2] [Ember.js](https://github.com/emberjs/ember.js/blob/master/CONTRIBUTING.md#requesting-a-feature)

# Proceso de Revisión del código
### Explica que necesita una contribución para ser aceptada luego de que se hace el submit.
Quién la revisa? Quien necesita firmar antes de que sea aceptada? Cuando debería esperar el contribuidor que le respondas? Cómo puede tener un contribuidor acceso a hacer commits, si fuese necesario?

> El core team revisa los Pull Requests semanalmente en una junta tripartita que se lleva a cabo en un Google Hangout público. El hangout se anuncia en las actualizaciones semanales y son enviados a la lista puppet-dev. Las notas son posteadas en el repo de Puppet Community community-triage e incluye un enlace a la grabacíon del hangout en YouTube.
> Luego de que se da la retroalimentación se esperan respuestas en las siguientes dos semanas. Luego de ello puede que se cierre el pull request debido a la inactividad.

[fuente: [Puppet](https://github.com/puppetlabs/puppet/blob/master/CONTRIBUTING.md#submitting-changes)] **Necesitas más inspiración?** [1] [Meteor](https://meteor.hackpad.com/Responding-to-GitHub-Issues-SKE2u3tkSiH ) [2] [Express.js](https://github.com/expressjs/express/blob/master/Contributing.md#becoming-a-committer)

# Comunidad
Si existen otros canales a demás de Github para discutir las contribuciones, mencionalos aquí. También puedes listar las y los autores, mantenedores y/o contribuidores aquí, o establecer las expectativas de tiempo de respuesta.

> Puedes chatear con el core team en https://gitter.im/cucumber/cucumber. Tratamos de tener horas disponibles los viernes.

[fuente: [cucumber-ruby](https://github.com/cucumber/cucumber-ruby/blob/master/CONTRIBUTING.md#talking-with-other-devs)] **Necesitas más inspiración?**
 [1] [Chef](https://github.com/chef/chef/blob/master/CONTRIBUTING.md#-developer-office-hours) [2] [Cookiecutter](https://github.com/audreyr/cookiecutter#community)

# BONOS: Convenciones de código, mensajes de commit y etiquetado
Estas secciones no son necesarias, pero pueden ayudar a orientar las contribuciones que recibes.

### Explica tu estilo preferido de código, si tienes alguno.

**Necesitas más inspiración?** [1] [Requirejs](http://requirejs.org/docs/contributing.html#codestyle) [2] [Elasticsearch](https://github.com/elastic/elasticsearch/blob/master/CONTRIBUTING.md#contributing-to-the-elasticsearch-codebase)

### Explica si tienes alguna convención de mensajes de commit.

**Necesitas más inspiración?** [1] [Angular](https://github.com/angular/material/blob/master/.github/CONTRIBUTING.md#submit) [2] [Node.js](https://github.com/nodejs/node/blob/master/CONTRIBUTING.md#step-3-commit)

### Explica si usas alguna convención para el etiquetado de issues.

**Necesitas más inspiración?** [1] [StandardIssueLabels](https://github.com/wagenet/StandardIssueLabels#standardissuelabels) [2] [Atom](https://github.com/atom/atom/blob/master/CONTRIBUTING.md#issue-and-pull-request-labels)