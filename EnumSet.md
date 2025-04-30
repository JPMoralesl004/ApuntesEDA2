# EnumSet

## ¿Qué es `EnumSet`?

`EnumSet` es una implementación especial de la interfaz `Set`, diseñada exclusivamente para usarse con valores de un `enum`. Es muy rápida y eficiente en memoria, ya que internamente usa una 
representación basada en bits.

Pertenece al paquete `java.util`.

## Definición Simple:

`EnumSet` es una implementación de conjunto altamente eficiente diseñada para trabajar exclusivamente con tipos `enum`, que permite operaciones rápidas y mantiene el orden de declaración de los elementos.

## ¿Para qué?

`EnumSet` es ideal para casos de uso donde se necesita manejar conjuntos de valores enum de manera eficiente. Sus principales ventajas incluyen:

- **Alto rendimiento:** Al utilizar una representación de vector de bits, las operaciones como adición, eliminación y consulta son extremadamente rápidas.
- **Uso de memoria optimizado:** Al ser altamente optimizado para tipos enum, `EnumSet` utiliza significativamente menos memoria en comparación con otros `Set`.
- **Orden de elementos:** Mantiene los elementos en el orden en que se declaran en la enumeración, lo que puede ser útil para ciertos algoritmos o interfaces de usuario.

Es especialmente útil en contextos donde se requieren operaciones intensivas de conjunto sobre enumeraciones, como filtros de configuración, opciones de aplicación, y más.

## Características principales:

- Solo funciona con tipos `enum`.

- No permite valores `null`.

- Es ordenado: mantiene el orden de declaración de los elementos en el `enum`.

- Es más eficiente que otras implementaciones de `Set` como `HashSet` cuando se trabaja con enums.

- Permite operaciones en conjunto muy rápidas (como un subconjunto, diferencia, unión, etc.).

### Sintaxis básica:

```java

import java.util.EnumSet;

enum Dia { LUNES, MARTES, MIERCOLES, JUEVES, VIERNES }

EnumSet<Dia> diasLaborales = EnumSet.range(Dia.LUNES, Dia.VIERNES);
```

### Creación

```java
EnumSet<DayOfWeek> days = EnumSet.noneOf(DayOfWeek.class);
```

### Métodos principales:

```java

EnumSet<Dia> dias = EnumSet.of(Dia.LUNES, Dia.MIERCOLES); // Crea un set con valores específicos
EnumSet<Dia> todos = EnumSet.allOf(Dia.class);            // Todos los valores del enum
EnumSet<Dia> ninguno = EnumSet.noneOf(Dia.class);         // Conjunto vacío
dias.add(Dia.VIERNES);                                    // Agrega un valor
dias.remove(Dia.LUNES);                                   // Elimina un valor
dias.contains(Dia.MARTES);                                // Verifica si contiene un valor
dias.isEmpty();                                           // Verifica si está vacío
```

### Ejemplo:

```java
import java.util.EnumSet;

public class EjemploEnumSet {
    enum Dia { LUNES, MARTES, MIERCOLES, JUEVES, VIERNES }

    public static void main(String[] args) {
        EnumSet<Dia> diasLaborales = EnumSet.range(Dia.LUNES, Dia.VIERNES);

        for (Dia d : diasLaborales) {
            System.out.println("Día laboral: " + d);
        }

        diasLaborales.remove(Dia.MIERCOLES);
        System.out.println("¿Contiene miércoles? " + diasLaborales.contains(Dia.MIERCOLES));
    }
}
```

### Métodos adicionales:

|Método|Descripción|
|-|-|
|`allOf(Class<E> elementType)`|Crea un EnumSet que contiene todos los elementos del tipo enum especificado.
|`complementOf(EnumSet<E> s)`|Crea un EnumSet que contiene todos los elementos del tipo enum especificado que no están en el conjunto especificado.
|`copyOf(EnumSet<E> s)`|Crea una copia del EnumSet especificado.
|`copyOf(Collection<E> c)`|Crea un EnumSet que contiene los elementos especificados, determinando el tipo enum a partir de los elementos de la primera colección.
|`range(E from, E to)`|Crea un EnumSet que contiene un rango de elementos del tipo enum especificado.
|`noneOf(Class<E> elementType)`|Crea un EnumSet vacío para el tipo enum especificado.
