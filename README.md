# T02-SSOO


Main
Para leer la entrada desde la consola y obtener los argumentos
```
#include "args/args.h"
#include <stdio.h>
#include <stdbool.h>
#include <stdlib.h> // para poder hacer exit

int main(int argc, char**argv)
{
    printf("Pusiste %i argumentos \n", argc);
    int n_arg = argc;
    char * inp = argv[1];
    char * out = argv[2];
    char * n_nucleos;
    printf("input : %s\n",inp);
    printf("output : %s\n",out);
    if (n_arg = 1) 
    {
        printf("ERROR\nNo has ingresado argumentos\n");
        exit();
    }
    else if (n_arg > 3) 
    {
        n_nucleos = argv[3];
        printf("n_nucleos : %s\n", n_nucleos);
    }
    else 
    {
        n_nucleos = "1";
    }
}
```

Modelación del problema:

- Structs:
```
typedef struct procesos
{
int PID;
char *name;
int prioridad;
Estado estado;
int t_inicio;
int deadline;
*** alguna forma de guardar los CPU burst e I/O burst***;
}Process;
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
La cola:

```
typedef struct cola
{
*** alguna forma de hacer la cola (un arreglo para todos los procesos, uno para cada uno o uno solo para los ready, etc.) ***
}Queue;
```


- Pasos a seguir:

1. Leer archivo:
  - Si se lee línea por línea, habrá que hacer un loop y en cada iteración separar la línea por espacios y guardarlo en el struct correspondiente.
    
