# T02-SSOO

Modelación del problema:

- Structs:
```
typedef struct procesos
{
int PID;
char *name;
int prioridad;
Estado estado;
}
```
El estado es un int, porque podría ser más facil compararlo con ontros estados si lo usamos así como dijo el ayudante.
Para eso usamos esto:

```
typedef enum estados
{
NEW, /** este no estoy seguro todavía, pero algo había dicho el ayudante de que había que manejar los estados antes de que existieran por así decirlo*/
RUNNING,
READY,
WAITING,
FINISHED,
}Estado;
```
