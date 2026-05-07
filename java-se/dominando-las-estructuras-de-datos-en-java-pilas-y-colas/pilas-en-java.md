# Pilas en Java

1. [01¿Qué es una pila?](https://www.ciberaula.com/cursos/java/pilas_java.php#que-es-pila)
2. [02Operaciones fundamentales](https://www.ciberaula.com/cursos/java/pilas_java.php#operaciones)
3. [03Interfaz Pila en Java](https://www.ciberaula.com/cursos/java/pilas_java.php#interfaz-pila)
4. [04Implementación con arrays](https://www.ciberaula.com/cursos/java/pilas_java.php#pila-array)
5. [05Implementación con listas enlazadas](https://www.ciberaula.com/cursos/java/pilas_java.php#pila-enlazada)
6. [06La clase Stack del JDK](https://www.ciberaula.com/cursos/java/pilas_java.php#stack-jdk)
7. [07Deque: la alternativa moderna](https://www.ciberaula.com/cursos/java/pilas_java.php#deque-alternativa)
8. [08Aplicaciones prácticas de las pilas](https://www.ciberaula.com/cursos/java/pilas_java.php#aplicaciones)
9. [09Ejemplo integrador: evaluador de paréntesis](https://www.ciberaula.com/cursos/java/pilas_java.php#ejemplo-integrador)
10. [10Errores frecuentes](https://www.ciberaula.com/cursos/java/pilas_java.php#errores-frecuentes)
11. [11Ejercicios prácticos](https://www.ciberaula.com/cursos/java/pilas_java.php#ejercicios)

La **pila** (_stack_ en inglés) es una de las estructuras de datos más fundamentales en ciencias de la computación. Su principio de funcionamiento es sencillo pero extraordinariamente potente: el último elemento que entra es el primero en salir, lo que se conoce como **LIFO** (_Last In, First Out_). Desde la gestión de llamadas a métodos hasta la verificación de paréntesis en compiladores, las pilas están presentes en el corazón de la programación.

En este artículo estudiaremos las pilas en Java de forma completa: desde la teoría y las operaciones básicas, pasando por dos implementaciones propias (con arrays y con listas enlazadas), hasta el uso de las clases del JDK (`Stack` y `Deque`). Cada concepto se acompaña de código ejecutable, diagramas visuales y ejercicios progresivos.

### 📚 ¿Qué es una pila? <a href="#que-es-pila" id="que-es-pila"></a>

Una **pila** es una secuencia de elementos del mismo tipo en la que el acceso se realiza por un único extremo denominado **cima** (_top_). Imagina una pila de libros: solo puedes colocar un libro nuevo encima de la pila o retirar el que está en la parte superior. Los libros del fondo no son directamente accesibles sin retirar primero los que están encima.

Este comportamiento se denomina **LIFO** (_Last In, First Out_): el último elemento insertado es siempre el primero en ser extraído. Es lo opuesto a una cola, que funciona con FIFO (_First In, First Out_).

💡**Analogía cotidiana:** Piensa en una pila de platos en un restaurante: el lavaplatos coloca los platos limpios arriba y el camarero siempre coge el de arriba. El primer plato lavado queda al fondo y es el último en usarse.

#### 🔹 Representación visual

La siguiente tabla muestra cómo evoluciona una pila a medida que se realizan operaciones `push` y `pop`:

| Operación  | Estado de la pila (cima →) | Elemento devuelto |
| ---------- | -------------------------- | ----------------- |
| `push(10)` | \[10]                      | —                 |
| `push(20)` | \[10, **20**]              | —                 |
| `push(30)` | \[10, 20, **30**]          | —                 |
| `pop()`    | \[10, **20**]              | 30                |
| `peek()`   | \[10, **20**]              | 20 (sin eliminar) |
| `pop()`    | \[**10**]                  | 20                |
| `pop()`    | \[] (vacía)                | 10                |

### ⚙️ Operaciones fundamentales <a href="#operaciones" id="operaciones"></a>

Toda implementación de pila debe proporcionar, como mínimo, las siguientes operaciones:

| Operación          | Descripción                                        | Complejidad |
| ------------------ | -------------------------------------------------- | ----------- |
| `push(e)`          | Inserta el elemento `e` en la cima de la pila      | O(1)        |
| `pop()`            | Extrae y devuelve el elemento de la cima           | O(1)        |
| `peek()` / `top()` | Devuelve el elemento de la cima **sin eliminarlo** | O(1)        |
| `isEmpty()`        | Devuelve `true` si la pila no contiene elementos   | O(1)        |
| `size()`           | Devuelve el número de elementos en la pila         | O(1)        |

✅**Rendimiento clave:** Todas las operaciones de una pila bien implementada tienen complejidad **O(1)** — tiempo constante, independiente del número de elementos. Esta eficiencia es una de las principales ventajas de la estructura.

### 📐 Interfaz Pila en Java <a href="#interfaz-pila" id="interfaz-pila"></a>

Antes de implementar la pila, definimos un **interfaz** que establece el contrato que cualquier implementación debe cumplir. Esto nos permite tener múltiples implementaciones (con array, con lista enlazada) intercambiables:

Pila.java

```
/**
 * Interfaz genérica para una estructura de datos tipo Pila (Stack).
 * @param <E> Tipo de los elementos almacenados.
 */
public interface Pila<E> {

    /** Inserta un elemento en la cima de la pila. */
    void push(E elemento);

    /** Extrae y devuelve el elemento de la cima. */
    E pop();

    /** Devuelve el elemento de la cima sin eliminarlo. */
    E peek();

    /** Devuelve true si la pila está vacía. */
    boolean isEmpty();

    /** Devuelve el número de elementos en la pila. */
    int size();
}
```

💡**Genéricos (`<E>`):** Usamos tipos genéricos para que la pila pueda almacenar cualquier tipo de objeto (`Integer`, `String`, `Producto`, etc.) manteniendo la seguridad de tipos en tiempo de compilación.

### 🗃️ Implementación con arrays (PilaArray) <a href="#pila-array" id="pila-array"></a>

La forma más directa de implementar una pila es mediante un **array** (vector) y un índice `top` que indica la posición de la cima. La dimensión del array se establece al crear la pila a través del constructor. Si se usa el constructor por defecto, se asigna una capacidad estándar.

#### ▶️ Código completo

PilaArray.java

```
/**
 * Implementación de Pila usando un array interno.
 * Capacidad fija definida en la construcción.
 */
public class PilaArray<E> implements Pila<E> {

    private static final int CAPACIDAD_DEFAULT = 1000;
    private E[] datos;
    private int top;  // índice de la cima (-1 = vacía)

    /** Constructor con capacidad personalizada. */
    @SuppressWarnings("unchecked")
    public PilaArray(int capacidad) {
        datos = (E[]) new Object[capacidad];
        top = -1;
    }

    /** Constructor por defecto: capacidad de 1000 elementos. */
    public PilaArray() {
        this(CAPACIDAD_DEFAULT);
    }

    @Override
    public void push(E elemento) {
        if (top == datos.length - 1) {
            throw new IllegalStateException("Pila llena: no se puede insertar.");
        }
        datos[++top] = elemento;  // incrementa top y luego inserta
    }

    @Override
    public E pop() {
        if (isEmpty()) {
            throw new IllegalStateException("Pila vacía: no se puede extraer.");
        }
        E elemento = datos[top];
        datos[top] = null;  // ayuda al recolector de basura
        top--;
        return elemento;
    }

    @Override
    public E peek() {
        if (isEmpty()) {
            throw new IllegalStateException("Pila vacía: no hay cima.");
        }
        return datos[top];
    }

    @Override
    public boolean isEmpty() {
        return top == -1;
    }

    @Override
    public int size() {
        return top + 1;
    }

    @Override
    public String toString() {
        StringBuilder sb = new StringBuilder("Pila [cima → ");
        for (int i = top; i >= 0; i--) {
            sb.append(datos[i]);
            if (i > 0) sb.append(", ");
        }
        sb.append("]");
        return sb.toString();
    }
}
```

#### 🔍 Análisis del funcionamiento

El campo `top` comienza en **-1**, indicando que la pila está vacía. Al hacer `push`, primero se incrementa `top` y después se inserta el elemento en esa posición. Al hacer `pop`, se lee el elemento en la posición `top`, se asigna `null` para liberar la referencia y se decrementa `top`.

| Aspecto         | Ventaja                                      | Desventaja                                  |
| --------------- | -------------------------------------------- | ------------------------------------------- |
| Memoria         | Acceso rápido por índice, sin punteros extra | Capacidad fija; puede desperdiciar espacio  |
| Rendimiento     | Todas las operaciones en O(1)                | Redimensionar requiere copiar todo el array |
| Uso recomendado | Cuando se conoce el tamaño máximo            | No ideal para tamaños impredecibles         |

#### ▶️ Ejemplo de uso

Java

```
public class DemoPilaArray {
    public static void main(String[] args) {
        PilaArray<String> pila = new PilaArray<>(5);

        pila.push("Java");
        pila.push("Python");
        pila.push("JavaScript");

        System.out.println(pila);            // Pila [cima → JavaScript, Python, Java]
        System.out.println("Cima: " + pila.peek());   // JavaScript
        System.out.println("Tamaño: " + pila.size()); // 3

        String extraido = pila.pop();
        System.out.println("Extraído: " + extraido);  // JavaScript
        System.out.println(pila);            // Pila [cima → Python, Java]
    }
}
```

### 🔗 Implementación con listas enlazadas (PilaEnlazada) <a href="#pila-enlazada" id="pila-enlazada"></a>

La segunda forma clásica de implementar una pila utiliza **nodos enlazados**. Cada nodo almacena un dato y una referencia al siguiente nodo. La cima de la pila es siempre el primer nodo de la cadena, lo que permite `push` y `pop` en O(1) sin necesidad de un array de tamaño fijo.

#### 🔹 La clase Nodo

Nodo.java

```
/**
 * Nodo genérico para estructuras enlazadas.
 */
public class Nodo<E> {
    private E dato;
    private Nodo<E> siguiente;

    public Nodo(E dato, Nodo<E> siguiente) {
        this.dato = dato;
        this.siguiente = siguiente;
    }

    public E getDato()              { return dato; }
    public Nodo<E> getSiguiente()   { return siguiente; }
    public void setSiguiente(Nodo<E> sig) { this.siguiente = sig; }
}
```

#### ▶️ Código completo de PilaEnlazada

PilaEnlazada.java

```
/**
 * Implementación de Pila usando nodos enlazados.
 * Tamaño dinámico: crece y decrece según las operaciones.
 */
public class PilaEnlazada<E> implements Pila<E> {

    private Nodo<E> top;     // nodo en la cima
    private int longitud;    // número de elementos

    public PilaEnlazada() {
        top = null;
        longitud = 0;
    }

    @Override
    public void push(E elemento) {
        // El nuevo nodo apunta al antiguo top
        top = new Nodo<>(elemento, top);
        longitud++;
    }

    @Override
    public E pop() {
        if (isEmpty()) {
            throw new IllegalStateException("Pila vacía: no se puede extraer.");
        }
        E dato = top.getDato();
        top = top.getSiguiente();  // el siguiente se convierte en nueva cima
        longitud--;
        return dato;
    }

    @Override
    public E peek() {
        if (isEmpty()) {
            throw new IllegalStateException("Pila vacía: no hay cima.");
        }
        return top.getDato();
    }

    @Override
    public boolean isEmpty() {
        return top == null;
    }

    @Override
    public int size() {
        return longitud;
    }

    @Override
    public String toString() {
        StringBuilder sb = new StringBuilder("Pila [cima → ");
        Nodo<E> actual = top;
        while (actual != null) {
            sb.append(actual.getDato());
            if (actual.getSiguiente() != null) sb.append(", ");
            actual = actual.getSiguiente();
        }
        sb.append("]");
        return sb.toString();
    }
}
```

#### 🔍 Cómo funciona el push en la lista enlazada

Al hacer `push`, se crea un nuevo nodo cuyo campo `siguiente` apunta al antiguo nodo cima. Después se actualiza `top` para que apunte al nuevo nodo. El proceso es instantáneo (O(1)) sin importar cuántos elementos tenga la pila.

Al hacer `pop`, se guarda el dato del nodo cima, se actualiza `top` al nodo siguiente (el que estaba justo debajo) y se devuelve el dato. El nodo antiguo queda sin referencias y el recolector de basura de Java lo eliminará automáticamente.

| Aspecto         | Ventaja                          | Desventaja                                               |
| --------------- | -------------------------------- | -------------------------------------------------------- |
| Memoria         | Tamaño dinámico, sin desperdicio | Cada nodo consume memoria extra (referencia `siguiente`) |
| Rendimiento     | Todas las operaciones en O(1)    | Sin acceso aleatorio a elementos internos                |
| Uso recomendado | Cuando el tamaño es impredecible | Mayor _overhead_ por nodo que un array                   |

### ☕ La clase `Stack` del JDK <a href="#stack-jdk" id="stack-jdk"></a>

Java incluye una clase `java.util.Stack` lista para usar. Extiende `Vector` y proporciona los métodos clásicos de una pila. Sin embargo, al heredar de `Vector`, todos sus métodos están **sincronizados**, lo que añade sobrecarga innecesaria en aplicaciones de un solo hilo.

Java

```
import java.util.Stack;

public class DemoStackJDK {
    public static void main(String[] args) {
        Stack<Integer> pila = new Stack<>();

        // push: añadir elementos
        pila.push(10);
        pila.push(20);
        pila.push(30);

        System.out.println("Pila: " + pila);           // [10, 20, 30]
        System.out.println("Cima: " + pila.peek());     // 30
        System.out.println("Tamaño: " + pila.size());   // 3

        // pop: extraer elemento de la cima
        int extraido = pila.pop();
        System.out.println("Extraído: " + extraido);    // 30
        System.out.println("Pila: " + pila);            // [10, 20]

        // search: buscar posición desde la cima (1 = cima)
        int posicion = pila.search(10);
        System.out.println("Posición de 10: " + posicion);  // 2

        // empty: comprobar si está vacía
        System.out.println("¿Vacía? " + pila.empty());  // false
    }
}
```

⚠️**Importante:** La propia documentación de Java (Javadoc) recomienda usar `Deque` en lugar de `Stack`: _«A more complete and consistent set of LIFO stack operations is provided by the Deque interface.»_ Usaremos `Stack` cuando necesitemos compatibilidad con código legado.

### 🚀 Deque: la alternativa moderna <a href="#deque-alternativa" id="deque-alternativa"></a>

La interfaz `java.util.Deque` (_Double-Ended Queue_) proporciona métodos para usar una estructura tanto como pila (LIFO) como cola (FIFO). La implementación recomendada para uso como pila es `ArrayDeque`, que es **más rápida** que `Stack` al no estar sincronizada.

Java

```
import java.util.ArrayDeque;
import java.util.Deque;

public class DemoDeque {
    public static void main(String[] args) {
        Deque<String> pila = new ArrayDeque<>();

        // push: inserta en la cima (equivale a addFirst)
        pila.push("Primero");
        pila.push("Segundo");
        pila.push("Tercero");

        System.out.println("Pila: " + pila);          // [Tercero, Segundo, Primero]
        System.out.println("Cima: " + pila.peek());    // Tercero

        // pop: extrae de la cima (equivale a removeFirst)
        String extraido = pila.pop();
        System.out.println("Extraído: " + extraido);   // Tercero

        // Iterar (desde la cima hacia la base)
        System.out.println("Recorrido:");
        for (String elemento : pila) {
            System.out.println("  → " + elemento);
        }
    }
}
```

#### 📊 Comparativa Stack vs Deque

| Característica        | `Stack`                   | `ArrayDeque`                      |
| --------------------- | ------------------------- | --------------------------------- |
| Hereda de             | `Vector`                  | Implementa `Deque`                |
| Sincronizada          | Sí (todos los métodos)    | No (más rápida)                   |
| Acceso por índice     | Sí (herencia de `Vector`) | No (solo cima y base)             |
| Método `search()`     | Sí                        | No (usar `contains()`)            |
| Permite `null`        | Sí                        | No                                |
| Recomendación oficial | Uso legado                | ✅ **Preferida para código nuevo** |

✅**Regla práctica:** Para código nuevo, usa siempre `Deque<E> pila = new ArrayDeque<>()`. Reserva `Stack` solo para mantener compatibilidad con código existente.

### 🌍 Aplicaciones prácticas de las pilas <a href="#aplicaciones" id="aplicaciones"></a>

Las pilas son omnipresentes en informática. Estas son algunas de sus aplicaciones más importantes:

| Aplicación                    | Descripción                                                                       | Ejemplo                         |
| ----------------------------- | --------------------------------------------------------------------------------- | ------------------------------- |
| **Call Stack**                | La JVM usa una pila para gestionar las llamadas a métodos y sus variables locales | Recursión, `StackOverflowError` |
| **Deshacer/Rehacer**          | Los editores de texto almacenan las acciones en pilas para deshacerlas            | Ctrl+Z en cualquier editor      |
| **Navegación web**            | El historial de páginas funciona como una pila (botón «Atrás»)                    | Navegadores web                 |
| **Paréntesis balanceados**    | Compiladores e intérpretes verifican que los delimitadores estén equilibrados     | `{[()]}` → válido               |
| **Evaluación de expresiones** | Notación postfija (RPN) se evalúa con una pila                                    | `3 4 + 2 *` → 14                |
| **Backtracking**              | Algoritmos como resolver laberintos o el problema de las N reinas                 | Ajedrez, Sudoku                 |

### 🏗️ Ejemplo integrador: evaluador de paréntesis <a href="#ejemplo-integrador" id="ejemplo-integrador"></a>

Uno de los usos clásicos de las pilas es verificar que los **paréntesis, corchetes y llaves** de una expresión estén correctamente balanceados. Este es exactamente el algoritmo que utilizan los compiladores de Java para validar el código fuente.

EvaluadorParentesis.java

```
import java.util.ArrayDeque;
import java.util.Deque;

/**
 * Verifica si los paréntesis, corchetes y llaves de una expresión
 * están correctamente balanceados usando una pila.
 */
public class EvaluadorParentesis {

    /**
     * Verifica si la cadena tiene delimitadores balanceados.
     * @param expresion Cadena a evaluar
     * @return true si está balanceada, false en caso contrario
     */
    public static boolean estaBalanceada(String expresion) {
        Deque<Character> pila = new ArrayDeque<>();

        for (char c : expresion.toCharArray()) {
            // Si es un delimitador de apertura, lo apilamos
            if (c == '(' || c == '[' || c == '{') {
                pila.push(c);
            }
            // Si es un delimitador de cierre, verificamos
            else if (c == ')' || c == ']' || c == '}') {
                if (pila.isEmpty()) {
                    return false;  // cierre sin apertura
                }
                char apertura = pila.pop();
                if (!sonPareja(apertura, c)) {
                    return false;  // no coinciden
                }
            }
            // Cualquier otro carácter se ignora
        }

        return pila.isEmpty();  // no deben quedar aperturas sin cerrar
    }

    /** Verifica si un par de delimitadores coinciden. */
    private static boolean sonPareja(char apertura, char cierre) {
        return (apertura == '(' && cierre == ')')
            || (apertura == '[' && cierre == ']')
            || (apertura == '{' && cierre == '}');
    }

    public static void main(String[] args) {
        String[] pruebas = {
            "{[()]}",           // ✅ balanceada
            "((()))",           // ✅ balanceada
            "{[(])}",           // ❌ cruce de delimitadores
            "((())",            // ❌ falta cierre
            "public static void main(String[] args) {}", // ✅
            "",                 // ✅ cadena vacía = balanceada
        };

        for (String expr : pruebas) {
            boolean resultado = estaBalanceada(expr);
            System.out.printf("%-50s → %s %s%n",
                "\"" + expr + "\"",
                resultado ? "✅" : "❌",
                resultado ? "Balanceada" : "No balanceada");
        }
    }
}

/* Salida esperada:
 * "{[()]}"                                    → ✅ Balanceada
 * "((()))"                                    → ✅ Balanceada
 * "{[(])}"                                    → ❌ No balanceada
 * "((())"                                     → ❌ No balanceada
 * "public static void main(String[] args) {}" → ✅ Balanceada
 * ""                                          → ✅ Balanceada
 */
```

El algoritmo recorre la cadena carácter a carácter. Los delimitadores de apertura se apilan, y cuando aparece un cierre se verifica que coincida con la apertura más reciente (la cima de la pila). Al finalizar, la pila debe estar vacía para que la expresión sea válida.

### ❌ Errores frecuentes <a href="#errores-frecuentes" id="errores-frecuentes"></a>

#### 🔹 Error 1: hacer pop sin verificar si la pila está vacía

El error más común es intentar extraer un elemento de una pila vacía, lo que provoca una excepción.

Java

```
// ❌ Error: pop sin verificar
Deque<Integer> pila = new ArrayDeque<>();
int valor = pila.pop();  // NoSuchElementException

// ✅ Correcto: verificar antes
if (!pila.isEmpty()) {
    int valor = pila.pop();
}
// O usar pollFirst() que devuelve null si está vacía
Integer valor = pila.pollFirst();
```

#### 🔹 Error 2: usar Stack en lugar de Deque en código nuevo

`Stack` permite acceder a elementos por índice (herencia de `Vector`), lo que rompe la abstracción de la pila. Un programador podría accidentalmente acceder a elementos que no son la cima.

Java

```
// ❌ Stack permite acceso por índice (rompe LIFO)
Stack<String> pila = new Stack<>();
pila.push("A");
pila.push("B");
pila.push("C");
String medio = pila.get(1);  // "B" — ¡acceso directo al medio!

// ✅ ArrayDeque no expone acceso por índice
Deque<String> pila2 = new ArrayDeque<>();
pila2.push("A");
pila2.push("B");
pila2.push("C");
// pila2.get(1);  // ¡Error de compilación! No existe el método
```

#### 🔹 Error 3: insertar null en ArrayDeque

A diferencia de `Stack`, `ArrayDeque` no permite elementos `null`. Intentar insertar `null` lanza `NullPointerException`.

Java

```
// ❌ ArrayDeque no acepta null
Deque<String> pila = new ArrayDeque<>();
pila.push(null);  // NullPointerException

// ✅ Si necesitas almacenar null, usa LinkedList como Deque
Deque<String> pila = new java.util.LinkedList<>();
pila.push(null);  // Funciona (pero es mala práctica)
```

### 📝 Ejercicios prácticos <a href="#ejercicios" id="ejercicios"></a>

**Ejercicio 1: ¿Qué imprime este código?**

Analiza el siguiente código y determina la salida **sin ejecutarlo**:

Java

```
Deque<Integer> pila = new ArrayDeque<>();
pila.push(5);
pila.push(10);
pila.push(15);
System.out.println(pila.pop());
pila.push(20);
System.out.println(pila.peek());
System.out.println(pila.pop());
System.out.println(pila.size());
```

Ocultar solución

**Salida:**

`15` — pop extrae la cima (15). Pila queda: \[10, 5]

`20` — peek consulta la cima (20 recién insertado). Pila: \[20, 10, 5]

`20` — pop extrae la cima (20). Pila queda: \[10, 5]

`2` — size devuelve 2 (quedan 10 y 5)

**Ejercicio 2: Invertir una cadena con pila**

Escribe un método `invertir(String texto)` que use una pila para invertir una cadena de texto. Por ejemplo, `invertir("Java")` debe devolver `"avaJ"`.

Ocultar soluciónJava

```
import java.util.ArrayDeque;
import java.util.Deque;

public class InvertirCadena {

    public static String invertir(String texto) {
        Deque<Character> pila = new ArrayDeque<>();

        // Paso 1: apilar cada carácter
        for (char c : texto.toCharArray()) {
            pila.push(c);
        }

        // Paso 2: desapilar para construir la cadena invertida
        StringBuilder resultado = new StringBuilder();
        while (!pila.isEmpty()) {
            resultado.append(pila.pop());
        }

        return resultado.toString();
    }

    public static void main(String[] args) {
        System.out.println(invertir("Java"));          // avaJ
        System.out.println(invertir("Hola Mundo"));    // odnuM aloH
        System.out.println(invertir("12345"));         // 54321
    }
}
```

La clave es que al desapilar, los caracteres salen en orden inverso al que fueron apilados (principio LIFO).

**Ejercicio 3: Calculadora con notación polaca inversa (RPN)**

Implementa un evaluador de expresiones en **notación postfija** (RPN). El método recibe un array de tokens (números y operadores) y devuelve el resultado. Ejemplo: `{"3", "4", "+", "2", "*"}` equivale a `(3 + 4) * 2 = 14`.

Ocultar soluciónJava

```
import java.util.ArrayDeque;
import java.util.Deque;

public class CalculadoraRPN {

    public static double evaluar(String[] tokens) {
        Deque<Double> pila = new ArrayDeque<>();

        for (String token : tokens) {
            switch (token) {
                case "+": case "-": case "*": case "/":
                    // Extraer los dos operandos (ojo: orden importa)
                    double b = pila.pop();  // segundo operando
                    double a = pila.pop();  // primer operando
                    double resultado;
                    if ("+".equals(token)) {
                        resultado = a + b;
                    } else if ("-".equals(token)) {
                        resultado = a - b;
                    } else if ("*".equals(token)) {
                        resultado = a * b;
                    } else {
                        resultado = a / b;
                    }
                    pila.push(resultado);
                    break;
                default:
                    // Es un número: apilarlo
                    pila.push(Double.parseDouble(token));
            }
        }

        return pila.pop();  // el resultado final queda en la cima
    }

    public static void main(String[] args) {
        // (3 + 4) * 2 = 14
        String[] expr1 = {"3", "4", "+", "2", "*"};
        System.out.println("Resultado: " + evaluar(expr1));  // 14.0

        // 5 + ((1 + 2) * 4) - 3 = 14
        String[] expr2 = {"5", "1", "2", "+", "4", "*", "+", "3", "-"};
        System.out.println("Resultado: " + evaluar(expr2));  // 14.0

        // 10 / 3 = 3.333...
        String[] expr3 = {"10", "3", "/"};
        System.out.println("Resultado: " + evaluar(expr3));  // 3.333...
    }
}
```

El algoritmo es elegante: los números se apilan y los operadores extraen dos operandos, calculan el resultado y lo apilan de vuelta. Al terminar, el resultado final queda como único elemento en la pila. Esta es la forma en que muchas calculadoras científicas y máquinas virtuales evalúan expresiones internamente.
