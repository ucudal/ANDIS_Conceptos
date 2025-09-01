# Conceptos

## Consistencia fuerte

La consistencia fuerte o *strong consistency*, en el contexto de sistemas
distribuidos, se refiere a que todas las operaciones de lectura devuelven el
valor más reciente escrito, garantizando que todos los nodos o procesos vean los
datos en el mismo orden y estado[^1].

Ver también [consistencia eventual](./4_Consistencia_eventual.md).

[^1]: Lamport, L. (1979). How to make a multiprocessor computer that correctly
    executes multiprocess programs. IEEE Transactions on Computers, 100(9),
    690-691.
