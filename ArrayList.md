# Arralist

Es una lista ordenada y redimensionable que permite almacenar elementos de tipo objeto (no tipos primitivos) y acceder a ellos mediante un índice.

---

## Características principales de `ArrayList`:

- Guarda los elementos en orden de inserción.

- Permite elementos duplicados.

- Se puede acceder a los elementos mediante un índice (como en un arreglo).

- Su tamaño crece automáticamente al añadir elementos.

- No es sincronizada (por defecto no es segura para multiples hilos).

  ---

## ¿Para qué?

El `ArrayList` se utiliza para almacenar datos de forma dinámica. Sus principales ventajas incluyen:

- **Flexibilidad en el tamaño:** A diferencia de los arrays estáticos, el `ArrayList` puede ajustar su tamaño en tiempo de ejecución.
- **Facilidad de manipulación:** Proporciona métodos para realizar operaciones comunes como insertar, actualizar, eliminar y buscar elementos con facilidad.
- **Almacenamiento de objetos:** Permite almacenar cualquier tipo de objeto (excepto tipos primitivos, que se pueden almacenar mediante clases envolventes).

Es ideal para situaciones donde se necesita una colección ordenada que pueda cambiar de tamaño y cuando se desea aprovechar los métodos integrados que simplifican la gestión de los datos almacenados.

---

### Sintaxis básica:
```java
  import java.util.ArrayList;

  ArrayList<String> lista = new ArrayList<>();
```
### Métodos comunes:
```java
lista.add("manzana");         // Agrega un elemento
lista.get(0);                 // Devuelve el elemento en la posición 0
lista.set(0, "pera");         // Reemplaza el elemento en la posición 0
lista.remove(0);              // Elimina el elemento en la posición 0
lista.size();                 // Devuelve el tamaño de la lista
lista.contains("pera");       // Verifica si contiene un elemento
lista.clear();                // Elimina todos los elementos
```

### Creación:

```java
ArrayList<String> myList = new ArrayList<>();
```

### Añadir elementos:

```java
myList.add("Elemento 1");
myList.add("Elemento 2");
```

### Acceder a elementos:

Accede al primer elemento

```java
String element = myList.get(0);
```

### Modificar elementos:

Modifica el primer elemento

```java
myList.set(0, "Nuevo Elemento");
```

### Eliminar elementos:

Por objeto y por índice

```java
myList.remove("Elemento 1"); 
myList.remove(0);
```

### Tamaño de la lista:

```java
int size = myList.size();
```

### Iterar sobre elementos:

```java
for (String item : myList) {
    System.out.println(item);
}
```

### Ejemplo:

```java
import java.util.ArrayList;

public class EjemploArrayList {
    public static void main(String[] args) {
        ArrayList<String> frutas = new ArrayList<>();
        frutas.add("Manzana");
        frutas.add("Banana");
        frutas.add("Mango");

        for (String fruta : frutas) {
            System.out.println(fruta);
        }
    }
}
```
