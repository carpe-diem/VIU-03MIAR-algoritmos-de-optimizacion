# AG3- Actividad Guiada 3

Desarrollar algoritmos con la técnica de búsqueda aleatoria
Desarrollar algoritmos con la técnica de búsqueda local
Desarrollar algoritmos con la técnica de recocido simulado(simulated annealing)
Desarrollar algoritmos con la técnica de colonia de hormigas(no evaluable)


NOTA: Si. el fichero no se descarga en la celda segunda, utilizar el fichero .tsp aquí adjunto.

AG3-Actividad-Guiada-3/README.MD
Notebook Original: [AG3-Actividad-Guiada-3.ipynb](AG3-Actividad-Guiada-3/AG3-Actividad-Guiada-3.ipynb)<br>
Notebook Mejorado: [Algoritmos_AG3-Alberto_Paparelli.ipynb](AG3-Actividad-Guiada-3/Algoritmos_AG3-Alberto_Paparelli.ipynb)

## Mejoras

### Busqueda Local con Entornos Variables (VNS)

- La busqueda local basica se atasca en minimos locales al usar solo un operador (swap de 2 nodos).
- Se agregan **2 operadores de vecindad adicionales**:
  - **Inversion de sub-ruta** (2-opt clasico): invierte el orden de los nodos entre dos posiciones.
  - **Insercion / Or-opt**: extrae un nodo (o segmento) y lo reinserta en otra posicion.
- El algoritmo **VNS** alterna entre los 3 operadores: cuando uno no mejora, prueba con el siguiente.
  Si encuentra mejora, reinicia al primer operador.
- Esto permite escapar de minimos locales que son optimos para un operador pero no para otro.
