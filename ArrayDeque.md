# ArrayDeque

## ¿Qué es ArrayDeque?

`ArrayDeque` (Array Double-Ended Queue) es una cola de doble extremo implementada mediante un arreglo redimensionable. Forma parte del paquete `java.util` y es una de las formas más rápidas y 
flexibles de implementar tanto pilas (stacks) como colas (queues).

## Definición Simple:

`ArrayDeque` es una estructura de datos basada en un arreglo redimensionable que permite operaciones eficientes de inserción y eliminación en ambos extremos, y se puede usar tanto como pila como cola.

## ¿Para qué?

El `ArrayDeque` se utiliza para:

- **Implementar colas y pilas:** Ofrece métodos para su uso como cola (FIFO) o como pila (LIFO), proporcionando una alternativa más eficiente a `LinkedList`.
- **Operaciones de alto rendimiento en ambos extremos:** Es ideal para algoritmos que requieren inserciones, eliminaciones o acceso frecuente a elementos desde ambos extremos de la colección.
- **Uso en aplicaciones de un solo hilo:** Al no estar sincronizado, es adecuado para situaciones donde no se requiere acceso concurrente, ofreciendo un mejor rendimiento que otras estructuras de datos sincronizadas.

## Características principales:

- Permite inserciones y eliminaciones por ambos extremos (inicio y fin).

- Es no sincronizada (no segura para múltiples hilos sin control externo).

- Más eficiente que `Stack` y `LinkedList` para pilas y colas en la mayoría de los casos.

- No permite elementos `null`.

## Usos comunes:

- Como pila (LIFO): usando `push`, `pop`, `peek`.

- Como cola (FIFO): usando `offer`, `poll`, `peek`.

---

### Sintaxis básica:

```Java
import java.util.ArrayDeque;

ArrayDeque<String> deque = new ArrayDeque<>();
```

### Métodos principales

```Java
deque.push("A");           // Inserta un elemento al inicio (modo pila)
deque.pop();               // Elimina y devuelve el primer elemento (modo pila)
deque.peek();              // Devuelve el primer elemento sin eliminarlo (modo pila)
deque.offer("B");          // Inserta un elemento al final (modo cola)
deque.poll();              // Elimina y devuelve el primer elemento (modo cola)
deque.addFirst("X");       // Inserta un elemento al inicio
deque.addLast("Y");        // Inserta un elemento al final
deque.removeFirst();       // Elimina y devuelve el primer elemento
deque.removeLast();        // Elimina y devuelve el último elemento
deque.peekFirst();         // Devuelve el primer elemento sin eliminarlo
deque.peekLast();          // Devuelve el último elemento sin eliminarlo
deque.isEmpty();           // Verifica si la deque está vacía
```

### Ejemplo:

```Java
import java.util.ArrayDeque;

public class EjemploArrayDeque {
    public static void main(String[] args) {
        ArrayDeque<String> deque = new ArrayDeque<>();

        deque.addLast("A");  // cola: A
        deque.addLast("B");  // cola: A, B
        deque.addFirst("C"); // cola: C, A, B

        System.out.println(deque.removeFirst()); // C
        System.out.println(deque.removeLast());  // B
    }
}
```
---

### Métodos adicionales

|Método|Descripción|
|-|-|
|`add(E e)`|Añade el elemento especificado al final de esta deque.
|`offerFirst(E e)`|Inserta el elemento especificado al frente de esta deque.
|`offerLast(E e)`|Inserta el elemento especificado al final de esta deque.
|`getFirst()`|Devuelve el primer elemento de esta deque.
|`getLast()`|Devuelve el último elemento de esta deque.
|`pollFirst()`|Recupera y elimina el primer elemento de esta deque, o retorna null si esta deque está vacía.
|`pollLast()`|Recupera y elimina el último elemento de esta deque, o retorna null si esta deque está vacía.
|`contains(Object o)`|Retorna true si esta deque contiene el elemento especificado.
|`size()`|Devuelve el número de elementos en esta deque.
|`clear()`|Elimina todos los elementos de esta deque.
|`iterator()`|Devuelve un iterador sobre los elementos en esta deque en secuencia correcta.
|`descendingIterator()`|Devuelve un iterador sobre los elementos en esta deque en secuencia inversa.
