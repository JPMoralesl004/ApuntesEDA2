# PriorityQueue

## ¿Qué es una `PriorityQueue`?

Una `PriorityQueue` es una cola con prioridad, lo que significa que los elementos no se procesan en el orden en que se agregan (como en una cola normal), sino según su prioridad natural o definida por un comparador.

Está en el paquete `java.util` y es muy útil cuando necesitas siempre acceder al elemento de mayor (o menor) prioridad de forma eficiente.

## Definición Simple:

`PriorityQueue` es una estructura de datos que organiza automáticamente sus elementos según su prioridad natural o definida por el programador, permitiendo siempre acceder al de mayor prioridad.

## ¿Para qué?

El `PriorityQueue` se utiliza para casos en los que es importante procesar objetos no en el orden en que fueron agregados, sino de acuerdo a algún criterio de prioridad. Sus principales ventajas incluyen:

- **Ordenación automática de elementos:** Al insertar, los elementos se ordenan automáticamente según su prioridad.
- **Acceso eficiente al elemento de mayor prioridad:** Permite acceder rápidamente al elemento de mayor prioridad sin necesidad de ordenar la colección manualmente.
- **Flexibilidad en la definición de prioridades:** La prioridad puede basarse en el orden natural de los elementos o en un `Comparator` definido por el usuario.

Es ideal para tareas de programación como la planificación de tareas, algoritmos de camino más corto, y en cualquier lugar donde el procesamiento de prioridad sea crítico.

## Características principales:

- Los elementos se ordenan según su orden natural (`Comparable`) o un `Comparator` personalizado.

- No permite elementos `null`.

- Implementada como un heap binario mínimo (por defecto).

- No garantiza el orden completo, solo que el elemento con mayor prioridad esté al frente.

### Sintaxis básica:

```java
import java.util.PriorityQueue;

PriorityQueue<Integer> cola = new PriorityQueue<>();
```

### Métodos principales:

```java
cola.offer(20);           // Inserta un elemento (según su prioridad)
cola.add(10);             // Inserta un elemento (lanza excepción si falla)
cola.peek();              // Devuelve el elemento con mayor prioridad sin eliminarlo
cola.poll();              // Elimina y devuelve el elemento con mayor prioridad
cola.remove();            // Igual que poll(), pero lanza excepción si está vacía
cola.isEmpty();           // Verifica si la cola está vacía
cola.size();              // Devuelve la cantidad de elementos
cola.contains(15);        // Verifica si contiene un elemento
```

### Métodos adicionales:

|Método|Descripción|
|-|-|
|`addElement(E obj)`|Añade el elemento especificado al final de este Vector.
|`capacity()`|Devuelve la capacidad actual de este Vector.
|`contains(Object elem)`|Comprueba si el Vector contiene el elemento especificado.
|`copyInto(Object[] anArray)`|Copia los componentes de este Vector en el array especificado.
|`elementAt(int index)`|Devuelve el componente en el índice especificado.
|`elements()`|Devuelve un enumeration de los componentes de este Vector.
|`ensureCapacity(int minCapacity)`|Aumenta la capacidad de este Vector, si es necesario, para asegurar que pueda contener al menos el número de componentes especificado en el argumento minCapacity.
|`firstElement()`|Devuelve el primer componente (el elemento en el índice 0) de este Vector.
|`lastElement()`|Devuelve el último componente del Vector.
|`removeElement(Object obj)`|Elimina la primera (más baja) ocurrencia del argumento del Vector.
|`removeElementAt(int index)`|Elimina el componente en el índice especificado.
|`setElementAt(E obj, int index)`|Establece el componente en el índice especificado de este Vector para ser el elemento especificado.
|`trimToSize()`|Recorta la capacidad de este Vector al tamaño actual del Vector.

### Ejemplo:

```java
import java.util.PriorityQueue;

public class EjemploPriorityQueue {
    public static void main(String[] args) {
        PriorityQueue<Integer> cola = new PriorityQueue<>();

        cola.offer(30);
        cola.offer(10);
        cola.offer(20);

        while (!cola.isEmpty()) {
            System.out.println(cola.poll()); // Imprime: 10, 20, 30
        }
    }
}
```
