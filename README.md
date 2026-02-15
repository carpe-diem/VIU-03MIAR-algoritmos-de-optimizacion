# VIU - Master en Inteligencia Artificial - Algoritmos de Optimización

**Alumno:** Alberto Paparelli
**Asignatura:** 03MIAR - Algoritmos de Optimización
**Universidad:** VIU - Universitat Internacional Valenciana
**Convocatoria:** 10_B 2025-26

---

## Indice

| Actividad | Tema | Notebook |
|-----------|------|----------|
| [AG1 - Actividad Guiada 1](AG1-Actividad-Guiada-1/) | Divide y vencerás, Voraz, Backtracking, Prog. Dinámica | [Notebook](AG1-Actividad-Guiada-1/Algoritmos_AG1-Alberto_Paparelli.ipynb) |
| [AG2 - Actividad Guiada 2](AG2-Actividad-Guiada-2/) | Prog. Dinámica, Ramificación y Poda, Descenso del Gradiente | [Notebook](AG2-Actividad-Guiada-2/Algoritmos_AG2-Alberto_Paparelli.ipynb) |
| [AG3 - Actividad Guiada 3](AG3-Actividad-Guiada-3/) | Búsqueda Aleatoria, Búsqueda Local, Simulated Annealing | [Notebook](AG3-Actividad-Guiada-3/Algoritmos_AG3-Alberto_Paparelli.ipynb) |

---

## Estructura del repositorio

```
VIU-03MIAR-algoritmos-de-optimizacion/
|
|-- AG1-Actividad-Guiada-1/
|   |-- Algoritmos_AG1.ipynb                        # Notebook original del profesor
|   |-- Algoritmos_AG1-Alberto_Paparelli.ipynb       # Notebook con mejoras
|   |-- Algoritmos_AG1-Alberto_Paparelli.html        # Exportación HTML
|   |-- Algoritmos_AG1-Alberto_Paparelli.pdf         # Exportación PDF
|   |-- README.md
|
|-- AG2-Actividad-Guiada-2/
|   |-- Algoritmos_AG2.ipynb                        # Notebook original del profesor
|   |-- Algoritmos_AG2-Alberto_Paparelli.ipynb       # Notebook con mejoras
|   |-- Algoritmos_AG2-Alberto_Paparelli.html        # Exportación HTML
|   |-- Algoritmos_AG2-Alberto_Paparelli.pdf         # Exportación PDF
|   |-- README.MD
|
|-- AG3-Actividad-Guiada-3/
|   |-- Algoritmos_AG3.ipynb                        # Notebook original del profesor
|   |-- Algoritmos_AG3-Alberto_Paparelli.ipynb       # Notebook con mejoras
|   |-- Algoritmos_AG3-Alberto_Paparelli.html        # Exportación HTML
|   |-- Algoritmos_AG3-Alberto_Paparelli.pdf         # Exportación PDF
|   |-- swiss42.tsp                                  # Datos TSP (Swiss 42 ciudades)
|   |-- README.MD
|
|-- .gitignore
|-- .python-version                                  # Python 3.12.7
|-- README.md
```

---

## Detalles de cada actividad

### AG1 - Actividad Guiada 1

**Técnicas:** Divide y vencerás, Algoritmos voraces, Backtracking, Programación dinámica

| Ejercicio | Técnica | Descripción |
|-----------|---------|-------------|
| Torres de Hanoi | Divide y vencerás | Resolución recursiva del problema clásico |
| Sucesión de Fibonacci | Programación dinámica | Cálculo del término n-ésimo |
| Devolución de cambio | Algoritmo voraz | Selección óptima de monedas |
| N-Reinas | Backtracking | Colocación de N reinas sin conflictos |
| Viaje por el río | Programación dinámica | Ruta de coste mínimo entre embarcaderos |

**Mejoras implementadas:**
- **Torres de Hanoi:** Visualización gráfica del estado de las torres con identificación de discos por color tras cada movimiento.
- **Fibonacci:** Versión iterativa con programación dinámica O(N) vs recursiva O(2^N), con comparación de tiempos.
- **N-Reinas:** Poda temprana comparando solo contra reinas anteriores, eliminación de `count()` por comparación directa O(1), y fix del bug de mutable default argument.
- **Viaje por el río:** Reemplazo de magic numbers por `float('inf')`, inicialización clara con `range(N)`, y fix de `calcular_ruta` para retornar lista de paradas.

---

### AG2 - Actividad Guiada 2

**Técnicas:** Programación dinámica, Ramificación y poda, Descenso del gradiente

| Ejercicio | Técnica | Descripción |
|-----------|---------|-------------|
| Viaje por el río | Programación dinámica | Ruta óptima entre embarcaderos |
| Asignación de tareas | Ramificación y poda | Asignación óptima agente-tarea minimizando coste |
| Descenso del gradiente | Optimización continua | Búsqueda de mínimos de funciones |

**Mejoras implementadas:**
- **Descenso del gradiente:** Parada temprana por convergencia basada en la norma del gradiente (`||grad f|| < epsilon`). Con la misma semilla (`random.seed(42)`), converge en ~42 iteraciones en lugar de las 50 fijas del original.

---

### AG3 - Actividad Guiada 3

**Técnicas:** Búsqueda aleatoria, Búsqueda local, Recocido simulado (Simulated Annealing)

**Problema:** TSP (Travelling Salesman Problem) sobre el dataset Swiss 42 ciudades.

| Ejercicio | Técnica | Descripción |
|-----------|---------|-------------|
| Búsqueda aleatoria | Metaheurística | Generación de soluciones aleatorias para TSP |
| Búsqueda local | Metaheurística | Mejora iterativa con operador 2-opt (swap) |
| Simulated Annealing | Metaheurística | Recocido simulado con aceptación probabilística |

**Mejoras implementadas:**
- **Búsqueda Local con Entornos Variables (VNS):** La búsqueda local básica se atasca en mínimos locales al usar solo un operador (swap). Se implementa VNS con 3 operadores de vecindad:
  1. **Swap:** Intercambio de 2 nodos (operador original)
  2. **Inversión (2-opt clásico):** Invierte el orden de una sub-ruta
  3. **Inserción (Or-opt):** Extrae un nodo y lo reinserta en otra posición
- El algoritmo alterna entre operadores: si uno no mejora, prueba el siguiente; si mejora, reinicia al primero. Esto permite escapar de mínimos locales que son óptimos para un operador pero no para otro.
