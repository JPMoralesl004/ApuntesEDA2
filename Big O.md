# Notación Big O

## ¿Qué es la notación Big O?

La notación Big O es una herramienta matemática utilizada en ciencias de la computación para describir la complejidad de un algoritmo, expresando cómo el tiempo de ejecución o el espacio de memoria requerido por un algoritmo crece en relación con el tamaño de la entrada.

Se enfoca en el crecimiento a largo plazo, permitiendo comparar la eficiencia de diferentes algoritmos de una manera que es independiente de las variaciones de hardware o implementación específica. Permite pues:

<div align=center>

|Describir el crecimiento|Comparar algoritmos|Identificar el peor caso|
|-|-|-|
|Cómo aumenta el tiempo de ejecución o uso de memoria cuando crece el tamaño de la entrada|De manera independiente del hardware o implementación específica|Enfocando en el comportamiento del algoritmo en su escenario más desfavorable|

</div>

## ¿Para qué sirve?

- **Comparar algoritmos:** Un algoritmo O(n log n) es más eficiente que uno O(n²) para entradas grandes.

- **Detectar cuellos de botella.**

- **Diseñar sistemas escalables.**

<div align=center>

|Eficiencia|Rendimiento|Escalabilidad|
|-|-|-|
|Facilita la comparación entre algoritmos para elegir el más adecuado basado en su comportamiento esperado con grandes volúmenes de datos.|Identifica cuellos de botella y guía el proceso de optimización al mostrar dónde se ganará más reduciendo la complejidad.|Ayuda a entender cómo un algoritmo manejará un aumento en el tamaño de los datos, lo cual es vital para sistemas que deben ser capaces de escalar.|

</div>

## ¿Cómo?

El análisis de complejidad mediante Big O se realiza siguiendo un proceso sistemático que involucra tres pasos principales:

1. **Evaluar el peor caso**: Analizar el escenario más desfavorable en términos de tiempo o espacio.
2. **Simplificar la expresión**: Identificar el [término dominante](terminoDominante.md) - aquel componente de la fórmula que crece más rápidamente con el tamaño de la entrada.
3. **Clasificar la complejidad**: Usar la notación para categorizar el algoritmo (O(1), O(n log n), O(n²), etc.).

### Identificación en la práctica

Para identificar la complejidad de un algoritmo en la práctica, consideramos:

- Conteo de operaciones
  - Si el número de operaciones se duplica al añadir un elemento → O(2^N).
  - Si el crecimiento se relaciona con el cuadrado del tamaño → O(N²).
  - Si el crecimiento se relaciona con el cubo del tamaño → O(N³).
- Estructura del algoritmo
  - Bucles anidados.
  - Llamadas recursivas múltiples.
  - Patrones de división del problema.
- Divide y vencerás
  - Algoritmos que parten el problema en mitades suelen ser O(log N).
  - Especialmente si se resuelve una mitad a la vez.
  - O si la combinación de soluciones es lineal o logarítmica.
 
### Ejemplos Comunes:

<div align=center>

| Notación   | Nombre                   | Ejemplo                                      |
|------------|--------------------------|----------------------------------------------|
| O(1)       | Tiempo constante          | Acceder a un elemento en un array            |
| O(log n)   | Tiempo logarítmico        | Búsqueda binaria                             |
| O(n)       | Tiempo lineal             | Recorrer una lista                           |
| O(n log n) | Tiempo log-linear         | Merge sort, Quick sort (promedio)            |
| O(n²)      | Tiempo cuadrático         | Doble bucle anidado                          |
| O(2ⁿ)      | Tiempo exponencial        | Algoritmo de fuerza bruta (como para la mochila) |
| O(n!)      | Tiempo factorial          | Permutaciones, algoritmos de backtracking    |

</div>

### Ejemplos en Java:

**1. O(1) - Tiempo constante**

*Acceder a un elemento en un arreglo.*

```java

public class EjemploO1 {
    public static int accesoElemento(int[] arr, int index) {
        return arr[index];  // Operación O(1)
    }

    public static void main(String[] args) {
        int[] arr = {1, 2, 3, 4, 5};
        System.out.println(accesoElemento(arr, 2)); // Salida: 3
    }
}

```

**2. O(log n) - Tiempo logarítmico**

*Búsqueda binaria en un arreglo ordenado.*

```java

public class EjemploOlogN {
    public static int busquedaBinaria(int[] arr, int target) {
        int low = 0, high = arr.length - 1;
        while (low <= high) {
            int mid = low + (high - low) / 2;
            if (arr[mid] == target) return mid;
            if (arr[mid] < target) low = mid + 1;
            else high = mid - 1;
        }
        return -1; // No encontrado
    }

    public static void main(String[] args) {
        int[] arr = {1, 3, 5, 7, 9, 11, 13};
        System.out.println(busquedaBinaria(arr, 7)); // Salida: 3
    }
}

```

**3. O(n) - Tiempo lineal**

*Recorrer una lista.*

```java

public class EjemploOn {
    public static void recorrerLista(int[] arr) {
        for (int i = 0; i < arr.length; i++) {
            System.out.println(arr[i]);
        }
    }

    public static void main(String[] args) {
        int[] arr = {1, 2, 3, 4, 5};
        recorrerLista(arr); // Salida: 1, 2, 3, 4, 5
    }
}

```

**4. O(n log n) - Tiempo log-lineal**

*Algoritmo Merge Sort (ordenación eficiente).*

```java

public class EjemploOnLogN {
    public static void mergeSort(int[] arr) {
        if (arr.length <= 1) return;
        int mid = arr.length / 2;
        int[] left = new int[mid];
        int[] right = new int[arr.length - mid];
        
        System.arraycopy(arr, 0, left, 0, mid);
        System.arraycopy(arr, mid, right, 0, arr.length - mid);
        
        mergeSort(left);
        mergeSort(right);
        merge(arr, left, right);
    }

    private static void merge(int[] arr, int[] left, int[] right) {
        int i = 0, j = 0, k = 0;
        while (i < left.length && j < right.length) {
            if (left[i] <= right[j]) {
                arr[k++] = left[i++];
            } else {
                arr[k++] = right[j++];
            }
        }
        while (i < left.length) arr[k++] = left[i++];
        while (j < right.length) arr[k++] = right[j++];
    }

    public static void main(String[] args) {
        int[] arr = {5, 3, 8, 4, 2};
        mergeSort(arr);
        for (int num : arr) {
            System.out.print(num + " "); // Salida: 2 3 4 5 8
        }
    }
}

```

**5. O(n²) - Tiempo cuadrático**

*Doble bucle anidado.*

```java

public class EjemploOn2 {
    public static void imprimirCombinaciones(int[] arr) {
        for (int i = 0; i < arr.length; i++) {
            for (int j = 0; j < arr.length; j++) {
                System.out.println(arr[i] + ", " + arr[j]);
            }
        }
    }

    public static void main(String[] args) {
        int[] arr = {1, 2, 3};
        imprimirCombinaciones(arr); // Salida: (todas las combinaciones)
    }
}

```

**6. O(2ⁿ) - Tiempo exponencial**
*Algoritmo de fuerza bruta (por ejemplo, para resolver el problema de la mochila).*

```java

public class EjemploO2n {
    public static int fuerzaBruta(int[] valores, int[] pesos, int capacidad) {
        return fuerzaBrutaAux(valores, pesos, capacidad, 0);
    }

    private static int fuerzaBrutaAux(int[] valores, int[] pesos, int capacidad, int index) {
        if (index == valores.length) return 0;
        if (pesos[index] > capacidad) return fuerzaBrutaAux(valores, pesos, capacidad, index + 1);
        int incluir = valores[index] + fuerzaBrutaAux(valores, pesos, capacidad - pesos[index], index + 1);
        int excluir = fuerzaBrutaAux(valores, pesos, capacidad, index + 1);
        return Math.max(incluir, excluir);
    }

    public static void main(String[] args) {
        int[] valores = {60, 100, 120};
        int[] pesos = {10, 20, 30};
        int capacidad = 50;
        System.out.println(fuerzaBruta(valores, pesos, capacidad)); // Salida: 220
    }
}

```

**7. O(n!) - Tiempo factorial**

*Generación de todas las permutaciones de un conjunto de elementos.*

```java

import java.util.*;

public class EjemploOnFactorial {
    public static void permutar(String str) {
        permutarAux(str, 0, str.length() - 1);
    }

    private static void permutarAux(String str, int l, int r) {
        if (l == r) {
            System.out.println(str);
        } else {
            for (int i = l; i <= r; i++) {
                str = intercambiar(str, l, i);
                permutarAux(str, l + 1, r);
                str = intercambiar(str, l, i); // Deshacer el cambio
            }
        }
    }

    private static String intercambiar(String str, int i, int j) {
        char temp;
        char[] charArray = str.toCharArray();
        temp = charArray[i];
        charArray[i] = charArray[j];
        charArray[j] = temp;
        return String.valueOf(charArray);
    }

    public static void main(String[] args) {
        String str = "ABC";
        permutar(str); // Salida: todas las permutaciones de "ABC"
    }
}

```

**8.** `sumArray` **– Complejidad O(n)**

*Suma todos los elementos de un arreglo.*

```java

public class SumArray {
    public static int sumArray(int[] arr) {
        int sum = 0;
        for (int num : arr) {
            sum += num;  // Se ejecuta una vez por elemento => O(n)
        }
        return sum;
    }

    public static void main(String[] args) {
        int[] arr = {1, 2, 3, 4, 5};
        System.out.println("Suma: " + sumArray(arr)); // Suma: 15
    }
}

```

**9.** `binarySearch` **– Complejidad O(log n)**

*Búsqueda binaria en un arreglo ordenado.*

```java

public class BinarySearch {
    public static int binarySearch(int[] arr, int target) {
        int low = 0, high = arr.length - 1;
        while (low <= high) {
            int mid = low + (high - low) / 2;
            if (arr[mid] == target) return mid;
            else if (arr[mid] < target) low = mid + 1;
            else high = mid - 1;
        }
        return -1; // No encontrado
    }

    public static void main(String[] args) {
        int[] arr = {1, 3, 5, 7, 9, 11, 13};
        System.out.println("Índice: " + binarySearch(arr, 7)); // Índice: 3
    }
}

```

**10.** `findMax` **– Complejidad O(n)**

*Encuentra el valor máximo en un arreglo.*

```java

public class FindMax {
    public static int findMax(int[] arr) {
        int max = arr[0];
        for (int num : arr) {
            if (num > max) {
                max = num;
            }
        }
        return max;
    }

    public static void main(String[] args) {
        int[] arr = {3, 7, 2, 9, 5};
        System.out.println("Máximo: " + findMax(arr)); // Máximo: 9
    }
}
```
