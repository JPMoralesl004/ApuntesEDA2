### Recursividad vs Iteración

Recursividad vs. Iteración es una comparación común en programación, ya que ambos enfoques se usan para resolver problemas repetitivos, pero tienen diferencias clave en cómo funcionan y 
cuándo conviene usar cada uno.

---

La comparación entre recursividad e iteración surge de una necesidad fundamental en el desarrollo de software: encontrar la forma más efectiva de resolver problemas repetitivos o divisibles. Este análisis comparativo es necesario por diversas razones:

- **Claridad conceptual**: Es imprescindible desmitificar la supuesta superioridad inherente de cualquiera de los dos enfoques, aclarando que ninguno posee capacidades especiales que el otro no pueda replicar.
- **Limitaciones prácticas**: A pesar de su elegancia conceptual, la recursividad presenta restricciones técnicas como el desbordamiento de pila (stack overflow) que pueden hacer inviable su uso en ciertos contextos.
- **Eficiencia computacional**: Se requiere evaluar el rendimiento de ambos enfoques en términos de tiempo de ejecución y consumo de memoria, factores críticos en el desarrollo de software eficiente.
- **Competencia técnica integral**: El conocimiento profundo de ambos paradigmas permite al programador seleccionar la herramienta más adecuada según las características específicas del problema a resolver.
- **Transformación entre paradigmas**: Se necesita comprender los mecanismos mediante los cuales cualquier algoritmo recursivo puede transformarse en uno iterativo y viceversa, ampliando así el repertorio de técnicas de resolución de problemas.

La comparación entre estos dos enfoques no se realiza para determinar cuál es universalmente superior, sino para entender en qué contextos cada uno ofrece ventajas significativas.

---

## Iteración

**Definición:**

Consiste en usar estructuras de control como `for`, `while`, o `do-while` para repetir un bloque de código hasta cumplir una condición.

**Ventajas:**

- Generalmente más eficiente en uso de memoria.

- Fácil de entender para tareas secuenciales simples.

- Mejor rendimiento en lenguajes que no optimizan recursión.

**Desventajas:**

- Menos expresiva para ciertos problemas (como árboles o algoritmos de búsqueda compleja).

- A veces requiere más código para representar estructuras lógicas complejas.

### Ejemplo

La iteración repite un bloque de código usando estructuras como `for`, `while`, etc.

**Ejemplo:** 

```java

public class FactorialIterativo {
    public static int factorial(int n) {
        int resultado = 1;
        for (int i = 1; i <= n; i++) {
            resultado *= i;
        }
        return resultado;
    }

    public static void main(String[] args) {
        System.out.println(factorial(5)); // Salida: 120
    }
}
```

## Recursividad

**Definición:**

Una función se llama a sí misma para resolver subproblemas más pequeños del problema original.

**Ventajas:**

- Más elegante para problemas naturalmente recursivos (como recorridos de árboles, backtracking, algoritmos divide y vencerás).

- Código más limpio y legible en ciertos casos.

**Desventajas:**

- Mayor uso de memoria (pila de llamadas).

- Riesgo de desbordamiento de pila si no se maneja bien.

- Puede ser más lenta si no se optimiza (aunque algunos lenguajes hacen tail-call optimization).


### Ejemplo:

La recursividad es cuando una función se llama a sí misma para resolver subproblemas.

**Ejemplo: Factorial con recursividad** 

```java

public class FactorialRecursivo {
    public static int factorial(int n) {
        if (n == 0) {
            return 1;
        }
        return n * factorial(n - 1);
    }

    public static void main(String[] args) {
        System.out.println(factorial(5)); // Salida: 120
    }
}
```

---

## Comparación

| Criterio            | Recursividad                         | Iteración                        |
|---------------------|--------------------------------------|----------------------------------|
| **Claridad**         | Más elegante para problemas recursivos | Más clara para tareas simples   |
| **Uso de memoria**   | Usa más memoria (pila de llamadas)   | Usa menos memoria               |
| **Velocidad**        | Más lenta (muchas llamadas)          | Más rápida en la mayoría de casos |
| **Riesgo de errores**| StackOverflow si no hay caso base    | Menor riesgo de error           |
| **Casos ideales**    | Estructuras recursivas (árboles, DFS, etc.) | Bucles simples, acumulaciones  |
| **Depuración**       | Más difícil de seguir paso a paso    | Más fácil de depurar            |
| **Complejidad**      | Puede tener complejidad exponencial  | Puede ser lineal o mejor        |

---

## Equivalencia teórica

Existe una equivalencia fundamental entre ambos enfoques:

<div align=center>

|Todo algoritmo iterativo puede convertirse en recursivo|Todo algoritmo recursivo puede implementarse iterativamente|
|-|-|
|Transformando el bucle en llamadas recursivas.|Utilizando un bucle y una estructura de pila explícita.|

</div>

Esta equivalencia significa que la elección entre recursividad e iteración no afecta lo que se puede computar, sino cómo se computa.

## Comparación de características

<div align=center>

|Característica|Recursividad|Iteración|
|-|-|-|
|Uso de memoria|Utiliza la pila de llamadas|Generalmente más eficiente en memoria |
|Claridad conceptual|A menudo más cercana a la definición matemática|Puede ser más intuitiva para operaciones secuenciales |
|Riesgo de errores|Desbordamiento de pila si la recursión es profunda|Bucles infinitos si la condición de salida está mal definida |
|Rendimiento|Puede implicar sobrecarga por múltiples llamadas a funciones|Generalmente más eficiente para problemas simples |
|Mantenimiento|A veces más elegante y concisa|A menudo más directa y fácil de depurar |

</div>

## ¿Para qué?

La comparación entre recursividad e iteración sirve para diversos propósitos prácticos en el desarrollo de software:

## Selección del enfoque adecuado

- **Optimización de rendimiento**: Permite elegir el enfoque más eficiente según las características del problema y las restricciones del sistema.
- **Gestión de recursos**: Facilita la toma de decisiones sobre el uso de memoria y tiempo de procesamiento.
- **Adecuación al dominio**: Ayuda a seleccionar el enfoque que mejor se adapta a la naturaleza del problema.

## Mejora de algoritmos existentes

- **Refactorización**: Ofrece técnicas para transformar código recursivo ineficiente en iterativo, o viceversa cuando sea beneficioso.
- **Eliminación de limitaciones**: Permite superar restricciones como el desbordamiento de pila en algoritmos recursivos profundos.
- **Mejora de legibilidad**: Posibilita reescribir código utilizando el paradigma que resulte más claro para un problema específico.

## Aplicaciones específicas

- **Estructuras jerárquicas**: Para recorrer árboles, grafos y otras estructuras anidadas, donde la recursividad a menudo resulta natural.
- **Algoritmos de dividir y conquistar**: En operaciones como ordenamiento (QuickSort, MergeSort) donde la recursividad puede ser conceptualmente más clara.
- **Cálculos matemáticos**: Para implementar funciones matemáticas definidas recursivamente (factorial, Fibonacci, etc.).
- **Backtracking**: En problemas como recorrido de laberintos o búsqueda de soluciones donde es necesario explorar múltiples caminos.

## Desarrollo de pensamiento algorítmico

- **Perspectivas complementarias**: Fomenta diferentes formas de pensar sobre la solución a un problema.
- **Percepción algorítmica**: A veces, pensar recursivamente puede revelar soluciones más eficientes que luego pueden implementarse iterativamente.
- **Comprensión profunda**: Entender ambos enfoques proporciona una visión más completa de las estructuras de control en programación.

---

## Ejemplos:

1. La serie de Fibonacci es:
```
0, 1, 1, 2, 3, 5, 8, 13, ...
```
Cada número es la suma de los dos anteriores.

### Fibonacci con Iteración

```java
public class FibonacciIterativo {
    public static int fibonacci(int n) {
        if (n <= 1) return n;

        int a = 0, b = 1, resultado = 0;
        for (int i = 2; i <= n; i++) {
            resultado = a + b;
            a = b;
            b = resultado;
        }
        return resultado;
    }

    public static void main(String[] args) {
        System.out.println(fibonacci(7)); // Salida: 13
    }
}
```

###  Fibonacci con Recursividad

```java
public class FibonacciRecursivo {
    public static int fibonacci(int n) {
        if (n <= 1) return n;
        return fibonacci(n - 1) + fibonacci(n - 2);
    }

    public static void main(String[] args) {
        System.out.println(fibonacci(7)); // Salida: 13
    }
}
```
**⚠️ Nota: El enfoque recursivo simple es muy ineficiente para valores grandes porque recalcula muchas veces los mismos resultados. Se puede optimizar con memoización o usando programación dinámica.**

2. Definición de nodo del árbol binario

```java
class Nodo {
    int valor;
    Nodo izquierdo, derecho;

    Nodo(int valor) {
        this.valor = valor;
        izquierdo = derecho = null;
    }
}
```

Recorrido Inorden (Recursivo)

```java

public class ArbolRecursivo {
    public static void inorden(Nodo nodo) {
        if (nodo != null) {
            inorden(nodo.izquierdo);
            System.out.print(nodo.valor + " ");
            inorden(nodo.derecho);
        }
    }

    public static void main(String[] args) {
        Nodo raiz = new Nodo(1);
        raiz.izquierdo = new Nodo(2);
        raiz.derecho = new Nodo(3);
        raiz.izquierdo.izquierdo = new Nodo(4);
        raiz.izquierdo.derecho = new Nodo(5);

        inorden(raiz); // Salida: 4 2 5 1 3
    }
}
```

Recorrido Inorden (Iterativo)

```java

import java.util.Stack;

public class ArbolIterativo {
    public static void inorden(Nodo raiz) {
        Stack<Nodo> stack = new Stack<>();
        Nodo actual = raiz;

        while (actual != null || !stack.isEmpty()) {
            while (actual != null) {
                stack.push(actual);
                actual = actual.izquierdo;
            }

            actual = stack.pop();
            System.out.print(actual.valor + " ");
            actual = actual.derecho;
        }
    }

    public static void main(String[] args) {
        Nodo raiz = new Nodo(1);
        raiz.izquierdo = new Nodo(2);
        raiz.derecho = new Nodo(3);
        raiz.izquierdo.izquierdo = new Nodo(4);
        raiz.izquierdo.derecho = new Nodo(5);

        inorden(raiz); // Salida: 4 2 5 1 3
    }
}
```
