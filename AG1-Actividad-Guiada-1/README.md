# AG1- Actividad Guiada 1

- Desarrollar algoritmos voraces para resolver problemas
- Desarrollar algoritmos con la técnica de vuelta atrás(backtracking) para resolver problemas
- Desarrollar algoritmos con la técnica de divide y vencerás para resolver problemas

Notebook Original: [AG1-Actividad-Guiada-1.ipynb](AG1-Actividad-Guiada-1/AG1-Actividad-Guiada-1.ipynb)<br>
Notebook Mejorado: [Algoritmos_AG1-Alberto_Paparelli.ipynb](AG1-Actividad-Guiada-1/Algoritmos_AG1-Alberto_Paparelli.ipynb)

## Mejoras

### Torres de Hanoi con Divide y vencerás
Se agrego una representacion visual del estado de las torres despues de cada movimiento.
La funcion principal Torres_Hanoi(N, desde, hasta) mantiene la misma estructura recursiva original,
reemplazando unicamente el print por una llamada a mover_y_dibujar, que realiza:
- Identificacion de fichas por color: Cada disco tiene un color asignado (disco 1 = roja, disco 2 = amarilla, disco 3 = verde),
permitiendo seguir visualmente el recorrido de cada ficha individual a lo largo de la ejecucion.
- Dibujo del estado: Tras cada movimiento se muestra una representacion grafica de las 3 torres con los discos apilados,
lo que facilita la comprension paso a paso del algoritmo.

La complejidad algoritmica no cambia, ya que la mejora es puramente de visualizacion.
