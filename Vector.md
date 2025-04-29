# Vector

## ¿Qué es un `Vector`?

`Vector` es una clase en Java que implementa una lista dinámica, similar a `ArrayList`, pero con una diferencia importante: es sincronizada (es decir, es segura para uso en múltiples hilos).

Pertenece al paquete `java.util` y fue una de las primeras implementaciones de estructuras de datos en Java (antes de que existiera `ArrayList`).

## Definición:

Vector es una lista dinámica sincronizada que almacena objetos en orden, permite acceso por índice y crece automáticamente a medida que se agregan elementos.

## ¿Para qué?

El `Vector` se utiliza para almacenar y acceder a colecciones de objetos de manera dinámica y segura en entornos multihilo. Sus principales ventajas incluyen:

- **Sincronización:** `Vector` es seguro para el uso concurrente sin necesidad de sincronización adicional.
- **Capacidad ajustable:** Al igual que `ArrayList`, `Vector` ajusta su tamaño automáticamente según sea necesario.
- **Acceso a elementos:** Permite el acceso directo a cualquier elemento basado en un índice.

Es ideal para aplicaciones que requieren acceso y modificación seguros de listas en entornos multihilo, pero puede ser menos eficiente en términos de rendimiento que `ArrayList` debido a su naturaleza sincronizada.
