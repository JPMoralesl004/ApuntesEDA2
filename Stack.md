# Stack

## ¿Qué es un `Stack`?

`Stack` es una estructura de datos tipo LIFO (Last-In, First-Out), es decir, el último elemento que se agrega es el primero que se retira. Funciona como una pila de platos: agregas por encima y retiras también 
desde arriba.

En Java, la clase `Stack` está en el paquete `java.util` y hereda de `Vector`, por lo tanto es sincronizada.

## Definición:

`Stack` es una estructura de datos de tipo LIFO que permite insertar y eliminar elementos desde el tope, implementada como una clase sincronizada que hereda de `Vector` en Java.

## Características principales:

- Sigue la lógica LIFO.

- Permite operaciones básicas como `push`, `pop`, `peek`.

- Es sincronizada (segura para múltiples hilos).

- Hereda todos los métodos de `Vector`, aunque solo algunos son relevantes para el uso como pila.

## ¿Cómo?

### Creación

```java
Stack<String> stack = new Stack<>();
```

### Empujar (agregar) elementos

```java
stack.push("Elemento 1");
stack.push("Elemento 2");
```

### Mirar el elemento superior (sin sacarlo)

```java
String topElement = stack.peek();
```

### Sacar elementos

```java
String poppedElement = stack.pop();
```

### Comprobar si la pila está vacía

```java
boolean isEmpty = stack.isEmpty();
```

### Buscar elementos

```java
int position = stack.search("Elemento 1"); 
```

> Devuelve su posición basada en 1 (o -1 si no se encuentra)

### Sintaxis básica:

```java
import java.util.Stack;

Stack<Integer> pila = new Stack<>();
```

### Métodos principales:

```java
pila.push(10);       // Inserta un elemento al tope de la pila
pila.pop();          // Elimina y devuelve el elemento en el tope
pila.peek();         // Devuelve el elemento en el tope sin eliminarlo
pila.isEmpty();      // Verifica si la pila está vacía
pila.search(10);     // Devuelve la posición del elemento (relativa al tope)
```

### Ejemplo:

```java
import java.util.Stack;

public class EjemploStack {
    public static void main(String[] args) {
        Stack<String> libros = new Stack<>();

        libros.push("Libro A");
        libros.push("Libro B");
        libros.push("Libro C");

        System.out.println("Tope: " + libros.peek());   // Muestra "Libro C"
        libros.pop();                                   // Elimina "Libro C"
        System.out.println("Nuevo tope: " + libros.peek()); // Muestra "Libro B"
    }
}
```

### Métodos adicionales:

|Método|Descripción|
|-|-|
|`push(E item)`|Empuja un elemento hacia la cima de la pila.
|`pop()`|Elimina el objeto en la cima de esta pila y lo devuelve como el valor de esta función.
|`peek()`|Mira el objeto en la cima de esta pila sin sacarlo de la pila.
|`isEmpty()`|Comprueba si la pila está vacía.
|`search(Object o)`|Busca el objeto en la pila y devuelve su posición basada en 1 desde la cima de la pila.
|`size()`|Devuelve el tamaño de la pila (heredado de Vector).
|`capacity()`|Devuelve la capacidad actual de esta pila (heredado de Vector).
|`contains(Object o)`|Verifica si la pila contiene el elemento especificado (heredado de Vector).
|`elementAt(int index)`|Devuelve el componente en el índice especificado (heredado de Vector).
|`ensureCapacity(int minCapacity)`|Aumenta la capacidad de esta pila, si es necesario (heredado de Vector).
|`clear()`|Elimina todos los elementos de la pila (equivalente a removeAllElements heredado de Vector).

## Nota:

**Aunque `Stack` es útil, en código moderno se prefiere usar `Deque` (como `ArrayDeque`) para implementaciones más eficientes de pilas y colas, porque `Stack` hereda de `Vector`, que es menos eficiente y algo anticuado.**
