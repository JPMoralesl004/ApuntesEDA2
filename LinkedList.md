# LinkedList

## ¿Qué es una `LinkedList`?:

Una `LinkedList` en Java es una estructura de datos que representa una lista enlazada, donde cada elemento (llamado nodo) contiene:

1. El dato (elemento).

2. Una referencia al siguiente nodo (y al anterior, si es doblemente enlazada).

Java implementa `LinkedList` como una lista doblemente enlazada, lo que significa que cada nodo apunta al siguiente y al anterior.

Pertenece al paquete `java.util` y implementa las interfaces `List`, `Deque` y `Queue`.

## Definición:

LinkedList es una lista doblemente enlazada que permite almacenar elementos en orden, con eficiencia en inserciones y eliminaciones en cualquier posición, y acceso secuencial a sus elementos.

## Características clave:

- Permite elementos duplicados.

- Mantiene el orden de inserción.

- Acceso rápido al principio o final de la lista.

- Más eficiente que `ArrayList` al insertar o eliminar elementos en posiciones arbitrarias (no requiere mover elementos).

- Más lenta que `ArrayList` al acceder por índice (porque tiene que recorrer la lista nodo por nodo).

## ¿Para qué?

El `LinkedList` se utiliza principalmente cuando se necesita un rendimiento óptimo en operaciones como inserción, eliminación y recorrido de elementos, especialmente en aplicaciones donde estas operaciones son más frecuentes que el acceso aleatorio a los elementos. Sus principales ventajas incluyen:

- **Inserciones y eliminaciones eficientes:** Ideal para aplicaciones que requieren frecuentes operaciones de inserción y eliminación.
- **Implementa tanto `List` como `Deque`:** Ofrece métodos adicionales para actuar como una cola doblemente terminada (deque), permitiendo su uso como una pila (stack) o una cola (queue).
- **Soporte para operaciones de lista enlazada:** Proporciona métodos específicos para operaciones de lista enlazada, como `getFirst()`, `getLast()`, `addFirst(E e)`, y `addLast(E e)`.

Es menos adecuado para escenarios con acceso aleatorio intensivo, ya que el acceso a un elemento específico requiere un recorrido desde el inicio de la lista, lo que puede ser menos eficiente que en un `ArrayList`.

### Sintaxis básica:

```java
import java.util.LinkedList;

LinkedList<String> lista = new LinkedList<>();
```

### Métodos comunes:

```java
lista.add("A");             // Agrega al final
lista.addFirst("Inicio");   // Agrega al principio
lista.addLast("Fin");       // Agrega al final
lista.get(0);               // Obtiene el primer elemento
lista.remove();             // Elimina el primer elemento
lista.removeLast();         // Elimina el último
lista.contains("A");        // Verifica si contiene un elemento
lista.size();               // Tamaño de la lista
```

### Creación

```java
LinkedList<String> list = new LinkedList<>();
```

### Añadir elementos

```java
list.add("Elemento 1");
list.addFirst("Elemento al inicio");
list.addLast("Elemento al final");
```

### Acceder a elementos

```java
String primerElemento = list.getFirst();
String ultimoElemento = list.getLast();
```

### Modificar elementos

No hay un método directo para reemplazar un elemento en una posición específica sin usar el método set(int index, E element), similar al ArrayList.

```java
list.set(1, "Nuevo Elemento");
```

### Eliminar elementos

```java
list.removeFirst();
list.removeLast();
list.remove("Elemento");
```

> El último ejemplo elimina **la primera ocurrencia** de "Elemento"

### Tamaño de la lista

```java
int size = list.size();
```

### Iterar sobre elementos

```java
for (String item : list) {
    System.out.println(item);
}
```
