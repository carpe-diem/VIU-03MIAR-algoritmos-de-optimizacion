# AG2- Actividad Guiada 2

Desarrollar algoritmos con la técnica de programación dinámica para resolver problemas
Desarrollar algoritmos con la técnica de ramificación y poda para resolver problemas
Desarrollar algoritmos con la técnica del descenso del gradiente

Notebook Original: [AG2-Actividad-Guiada-2.ipynb](AG2-Actividad-Guiada-2/AG2-Actividad-Guiada-2.ipynb)<br>
Notebook Mejorado: [Algoritmos_AG2-Alberto_Paparelli.ipynb](AG2-Actividad-Guiada-2/Algoritmos_AG2-Alberto_Paparelli.ipynb)

## Mejoras

### Descenso del gradiente

- Parada temprana por convergencia: Se agrego un criterio de parada basado en la **norma del gradiente**.
Cuando `||grad f|| < epsilon`, el gradiente es tan pequeno que estamos practicamente en un minimo
y no tiene sentido seguir iterando.
- Se agregan metricas de tiempo (`time.perf_counter()`) y conteo de iteraciones en ambas versiones.
