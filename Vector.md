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


## Características principales:

- Redimensionable automáticamente, como `ArrayList`.

- Sincronizada, lo que significa que sus métodos están protegidos contra acceso concurrente (aunque esto la hace menos eficiente en entornos de un solo hilo).

- Permite elementos duplicados.

- Mantiene el orden de inserción.

- Permite acceso por índice.

- Internamente usa un arreglo (array) de objetos.

---

### Sintaxis básica:

```java
import java.util.Vector;

Vector<String> vector = new Vector<>();
```

### Métodos comunes:

```java
vector.add("Uno");          // Agrega un elemento
vector.get(0);              // Obtiene el elemento en el índice 0
vector.set(0, "Dos");       // Modifica el elemento
vector.remove(0);           // Elimina el elemento
vector.size();              // Tamaño del vector
vector.contains("Dos");     // Verifica si contiene un elemento
vector.clear();             // Elimina todos los elementos
```

### Creación

```java
Vector<String> vector = new Vector<>();
```

### Añadir elementos

```java
vector.add("Elemento 1");
vector.addElement("Elemento 2");
```

### Acceder a elementos

```java
String elemento = vector.get(0);
```

### Modificar elementos

```java
vector.set(0, "Nuevo Elemento");
```

### Eliminar elementos

```java
vector.remove("Elemento 1");
vector.remove(0);
```

### Tamaño del vector

```java
int size = vector.size();
```

### Iterar sobre elementos

```java
for (String item : vector) {
    System.out.println(item);
}
```

### Ejemplo: 

```Java
import java.util.Vector;

public class EjemploVector {
    public static void main(String[] args) {
        Vector<Integer> numeros = new Vector<>();
        numeros.add(10);
        numeros.add(20);
        numeros.add(30);

        for (int numero : numeros) {
            System.out.println(numero);
        }
    }
}
```

### Métodos adicionales para investigación

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

### Vector vs ArrayList:

| Característica     | `Vector`                          | `ArrayList`                      |
|--------------------|-----------------------------------|----------------------------------|
| Sincronización     | Sí (sincronizado por defecto)     | No (no sincronizado)             |
| Rendimiento        | Más lento en entornos de un solo hilo | Más rápido en uso general     |
| Crecimiento        | Duplica su tamaño automáticamente | Aumenta 50% su capacidad         |
| Uso recomendado    | Aplicaciones con múltiples hilos  | Aplicaciones de un solo hilo     |
| Compatibilidad     | Antigua (desde Java 1.0)          | Más moderna (desde Java 1.2)     |
| Reemplazo sugerido | Obsoleto para la mayoría de casos | Preferido en código moderno      |
