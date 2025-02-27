# 4 Conceptos

## Modularidad

El concepto de modularidad fue introducido por David Parnas para referirse a la
descomposición de un sistema de software en módulos altamente
[cohesivos](./4_Cohesion.md) y poco [acoplados](./4_Acoplamiento.md), donde cada
módulo oculta los detalles de su implementación detrás de una
[interfaz](./4_Interfaz.md) y puede ser modificado independientemente con mínimo
impacto en otros módulos[^1]. Luego Meilir Page-Jones extendió el concepto para
que los módulos tuvieran ‑además‑ poca o nula [co-nascencia ‑o
*connascence*‑](./4_Connascence.md)[^2].

[^1]: Parnas, D. (1972). On the criteria to be used in decomposing systems into
    modules. Communications of the ACM, 15(12), 1053-1058.

[^2]: Page-Jones, M. (1996). What Every Programmer Should Know About
    Object-Oriented Design. Dorset House.

A veces también se usa modularidad para referirse a la técnica en la que se
divide un sistema de software en componentes discretos que se pueden
desarrollar, modificar, reemplazar y reutilizar de forma independiente[^3].

[^3]: Pressman, R. (2010). Ingeniería del software: un enfoque práctico.
    7<sup>a</sup> edición.  McGraw-Hill. Capítulo 5. Disponible en
    [biblioteca](https://catalogo.ucu.edu.uy/cgi-bin/koha/opac-detail.pl?biblionumber=80936).
