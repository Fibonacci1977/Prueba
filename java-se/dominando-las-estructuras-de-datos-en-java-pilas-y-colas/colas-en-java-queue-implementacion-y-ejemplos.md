# Colas en Java (Queue): implementación y ejemplos

1. [01¿Qué es una cola? El principio FIFO](https://www.ciberaula.com/cursos/java/colas_java.php#que-es-cola)
2. [02Operaciones fundamentales de una cola](https://www.ciberaula.com/cursos/java/colas_java.php#operaciones-fundamentales)
3. [03Definición del interfaz Cola en Java](https://www.ciberaula.com/cursos/java/colas_java.php#interfaz-cola)
4. [04Implementación con nodos enlazados](https://www.ciberaula.com/cursos/java/colas_java.php#implementacion-nodos)
5. [05Implementación con array circular](https://www.ciberaula.com/cursos/java/colas_java.php#implementacion-array)
6. [06La interfaz Queue en Java Collections](https://www.ciberaula.com/cursos/java/colas_java.php#queue-collections)
7. [07Colas de doble extremo (Deque)](https://www.ciberaula.com/cursos/java/colas_java.php#deque-doble)
8. [08Colas de prioridad (PriorityQueue)](https://www.ciberaula.com/cursos/java/colas_java.php#priority-queue)
9. [09Casos de uso reales de las colas](https://www.ciberaula.com/cursos/java/colas_java.php#casos-uso)
10. [10Errores comunes al trabajar con colas](https://www.ciberaula.com/cursos/java/colas_java.php#errores-comunes)
11. [11Ejemplo integrador: sistema de atención al cliente](https://www.ciberaula.com/cursos/java/colas_java.php#ejemplo-integrador)
12. [12Ejercicios prácticos](https://www.ciberaula.com/cursos/java/colas_java.php#ejercicios)
13. [13Preguntas frecuentes (FAQ)](https://www.ciberaula.com/cursos/java/colas_java.php#faq)

### 📦 ¿Qué es una cola? El principio FIFO <a href="#que-es-cola" id="que-es-cola"></a>

Una **cola** (_queue_ en inglés) es una estructura de datos lineal que sigue el principio **FIFO** (_First In, First Out_): el primer elemento que se inserta es el primero en ser extraído. Es, junto con la pila y la lista enlazada, una de las estructuras fundamentales de la informática y una de las más utilizadas en la práctica profesional.

La analogía más intuitiva es una **fila de personas** esperando en un banco o en un supermercado: la primera persona que llega es la primera en ser atendida, y las nuevas personas se incorporan al final de la fila. Esta metáfora captura perfectamente el comportamiento de una cola: los elementos se **insertan por un extremo** (el final o _rear_) y se **extraen por el otro** (el frente o _front_).

**💡 FIFO vs LIFO:** Mientras que una cola sigue el principio FIFO (el primero en entrar es el primero en salir), una [pila](https://www.ciberaula.com/cursos/java/pilas_java.php) sigue el principio LIFO (Last In, First Out — el último en entrar es el primero en salir). Ambas son restricciones del tipo abstracto [lista](https://www.ciberaula.com/cursos/java/listas_java.php), pero con reglas de acceso distintas.

Formalmente, una cola es un **tipo abstracto de datos** (TAD) que define un contrato de operaciones sin especificar cómo se implementan internamente. Esto permite múltiples implementaciones — con nodos enlazados, con arrays, con arrays circulares — todas respetando el mismo contrato FIFO.

#### Terminología esencial

| Término        | Significado                               | Equivalente en inglés |
| -------------- | ----------------------------------------- | --------------------- |
| **Encolar**    | Insertar un elemento al final de la cola  | `enqueue` / `offer`   |
| **Desencolar** | Extraer el elemento del frente de la cola | `dequeue` / `poll`    |
| **Frente**     | El primer elemento (próximo a salir)      | `front` / `head`      |
| **Final**      | La posición donde se inserta el siguiente | `rear` / `tail`       |
| **Cola vacía** | Cola sin elementos                        | `empty queue`         |

### ⚙️ Operaciones fundamentales de una cola <a href="#operaciones-fundamentales" id="operaciones-fundamentales"></a>

Toda implementación de cola debe soportar un conjunto mínimo de operaciones que definen su comportamiento. Estas operaciones constituyen el **contrato** del TAD Cola y deben ejecutarse en tiempo **O(1)** constante para que la estructura sea eficiente:

| Operación    | Descripción                                   | Complejidad |
| ------------ | --------------------------------------------- | ----------- |
| `enqueue(e)` | Inserta el elemento `e` al final de la cola   | O(1)        |
| `dequeue()`  | Extrae y devuelve el elemento del frente      | O(1)        |
| `front()`    | Devuelve el elemento del frente sin extraerlo | O(1)        |
| `isEmpty()`  | Devuelve `true` si la cola no tiene elementos | O(1)        |
| `size()`     | Devuelve el número de elementos en la cola    | O(1)        |

**✅ Regla de oro:** Nunca intentes desencolar de una cola vacía. Siempre verifica con `isEmpty()` antes de llamar a `dequeue()`, o utiliza métodos que devuelvan `null` en lugar de lanzar excepciones.

### 📋 Definición del interfaz Cola en Java <a href="#interfaz-cola" id="interfaz-cola"></a>

Antes de implementar una cola, definimos su contrato mediante un **interfaz Java**. Esto nos permite programar contra una abstracción, no contra una implementación concreta — un principio fundamental de la [programación orientada a objetos](https://www.ciberaula.com/cursos/java/programacion_orientada_objetos.php).

Cola.java — Interfaz del TAD Cola

```
/**
 * Interfaz que define el contrato del TAD Cola (Queue).
 * Principio FIFO: First In, First Out.
 *
 * @param <E> Tipo genérico de los elementos de la cola
 */
public interface Cola<E> {

    /**
     * Inserta un elemento al final de la cola.
     * @param elemento El elemento a insertar
     */
    void encolar(E elemento);

    /**
     * Extrae y devuelve el elemento del frente.
     * @return El elemento del frente
     * @throws NoSuchElementException si la cola está vacía
     */
    E desencolar();

    /**
     * Devuelve el elemento del frente sin extraerlo.
     * @return El elemento del frente
     * @throws NoSuchElementException si la cola está vacía
     */
    E frente();

    /** @return true si la cola no tiene elementos */
    boolean estaVacia();

    /** @return El número de elementos en la cola */
    int tamaño();
}
```

Observa que el interfaz utiliza **genéricos** (`<E>`) para que la cola pueda almacenar cualquier tipo de objeto. Esto es una práctica profesional estándar que proporciona **seguridad de tipos** en tiempo de compilación y evita la necesidad de realizar _casting_ al extraer elementos.

### 🔗 Implementación con nodos enlazados <a href="#implementacion-nodos" id="implementacion-nodos"></a>

La implementación con **nodos enlazados** es la forma más natural de construir una cola. Cada elemento se almacena en un nodo que contiene el dato y una referencia al siguiente nodo. Mantenemos dos referencias: `cabecera` (frente, por donde se desencola) y `cola` (final, por donde se encola).

#### La clase Nodo

Nodo.java — Nodo genérico para la cola enlazada

```
/**
 * Nodo de una estructura enlazada.
 * Almacena un dato y una referencia al siguiente nodo.
 */
class Nodo<E> {
    E dato;
    Nodo<E> siguiente;

    Nodo(E dato) {
        this.dato = dato;
        this.siguiente = null;
    }

    Nodo(E dato, Nodo<E> siguiente) {
        this.dato = dato;
        this.siguiente = siguiente;
    }
}
```

#### La clase ColaEnlazada

ColaEnlazada.java — Implementación completa con nodos

```
import java.util.NoSuchElementException;

/**
 * Implementación del TAD Cola mediante nodos enlazados.
 * Todas las operaciones son O(1).
 */
public class ColaEnlazada<E> implements Cola<E> {

    private Nodo<E> cabecera;  // Frente: por aquí se desencola
    private Nodo<E> cola;      // Final: por aquí se encola
    private int tamaño;

    public ColaEnlazada() {
        this.cabecera = null;
        this.cola = null;
        this.tamaño = 0;
    }

    @Override
    public void encolar(E elemento) {
        Nodo<E> nuevoNodo = new Nodo<>(elemento);
        if (estaVacia()) {
            // Si la cola está vacía, cabecera y cola apuntan al mismo nodo
            cabecera = nuevoNodo;
        } else {
            // El nodo actual del final apunta al nuevo nodo
            cola.siguiente = nuevoNodo;
        }
        cola = nuevoNodo;
        tamaño++;
    }

    @Override
    public E desencolar() {
        if (estaVacia()) {
            throw new NoSuchElementException("La cola está vacía");
        }
        E dato = cabecera.dato;
        cabecera = cabecera.siguiente;
        tamaño--;
        if (estaVacia()) {
            // Si la cola queda vacía, limpiar también la referencia cola
            cola = null;
        }
        return dato;
    }

    @Override
    public E frente() {
        if (estaVacia()) {
            throw new NoSuchElementException("La cola está vacía");
        }
        return cabecera.dato;
    }

    @Override
    public boolean estaVacia() {
        return tamaño == 0;
    }

    @Override
    public int tamaño() {
        return tamaño;
    }

    @Override
    public String toString() {
        StringBuilder sb = new StringBuilder("Cola [frente -> ");
        Nodo<E> actual = cabecera;
        while (actual != null) {
            sb.append(actual.dato);
            if (actual.siguiente != null) sb.append(" -> ");
            actual = actual.siguiente;
        }
        sb.append(" <- final]");
        return sb.toString();
    }
}
```

La clave de esta implementación está en mantener **dos referencias separadas**: `cabecera` para las extracciones y `cola` para las inserciones. Sin la referencia al final, cada inserción requeriría recorrer toda la lista — degradando el rendimiento a O(n). Con ambas referencias, tanto `encolar` como `desencolar` operan en **tiempo constante O(1)**.

**⚠️ Caso especial:** Cuando la cola queda vacía tras desencolar el último elemento, es fundamental establecer `cola = null`. Si se omite esto, la referencia `cola` apuntaría a un nodo que ya no forma parte de la estructura, provocando comportamientos inesperados al encolar de nuevo.

#### Prueba de la cola enlazada

PruebaColaEnlazada.java — Demostración de uso

```
public class PruebaColaEnlazada {
    public static void main(String[] args) {
        Cola<String> cola = new ColaEnlazada<>();

        // Encolar clientes
        cola.encolar("Ana");
        cola.encolar("Pedro");
        cola.encolar("María");
        System.out.println(cola);
        // Cola [frente -> Ana -> Pedro -> María <- final]

        // Consultar quién es el siguiente
        System.out.println("Siguiente: " + cola.frente());
        // Siguiente: Ana

        // Atender al primero
        String atendido = cola.desencolar();
        System.out.println("Atendido: " + atendido);
        // Atendido: Ana

        System.out.println(cola);
        // Cola [frente -> Pedro -> María <- final]

        System.out.println("Tamaño: " + cola.tamaño());
        // Tamaño: 2
    }
}
```

### 🔄 Implementación con array circular <a href="#implementacion-array" id="implementacion-array"></a>

Una alternativa a los nodos enlazados es usar un **array circular** (también llamado _buffer circular_ o _ring buffer_). En esta implementación, los índices `frente` y `final` avanzan circularmente por el array usando la operación **módulo** (`%`), de modo que cuando llegan al final del array, vuelven a la posición 0.

La ventaja del array circular sobre un array lineal es que **reutiliza las posiciones** que quedan libres al desencolar, evitando desperdiciar memoria. Sin el envolvimiento circular, las posiciones del inicio del array se perderían tras cada operación de desencolado.

ColaCircular.java — Implementación con array circular

```
import java.util.NoSuchElementException;

/**
 * Implementación del TAD Cola con un array circular.
 * Capacidad fija con posibilidad de redimensionamiento.
 */
@SuppressWarnings("unchecked")
public class ColaCircular<E> implements Cola<E> {

    private static final int CAPACIDAD_INICIAL = 16;
    private E[] datos;
    private int frente;     // Índice del primer elemento
    private int numElementos;
    private int capacidad;

    public ColaCircular() {
        this(CAPACIDAD_INICIAL);
    }

    public ColaCircular(int capacidad) {
        this.capacidad = capacidad;
        this.datos = (E[]) new Object[capacidad];
        this.frente = 0;
        this.numElementos = 0;
    }

    @Override
    public void encolar(E elemento) {
        if (numElementos == capacidad) {
            redimensionar(capacidad * 2);
        }
        // El índice del final se calcula a partir de frente + numElementos
        int indiceFinal = (frente + numElementos) % capacidad;
        datos[indiceFinal] = elemento;
        numElementos++;
    }

    @Override
    public E desencolar() {
        if (estaVacia()) {
            throw new NoSuchElementException("La cola está vacía");
        }
        E dato = datos[frente];
        datos[frente] = null;  // Permitir recolección de basura
        frente = (frente + 1) % capacidad;
        numElementos--;
        return dato;
    }

    @Override
    public E frente() {
        if (estaVacia()) {
            throw new NoSuchElementException("La cola está vacía");
        }
        return datos[frente];
    }

    @Override
    public boolean estaVacia() {
        return numElementos == 0;
    }

    @Override
    public int tamaño() {
        return numElementos;
    }

    /**
     * Redimensiona el array circular preservando el orden FIFO.
     */
    private void redimensionar(int nuevaCapacidad) {
        E[] nuevoArray = (E[]) new Object[nuevaCapacidad];
        for (int i = 0; i < numElementos; i++) {
            nuevoArray[i] = datos[(frente + i) % capacidad];
        }
        datos = nuevoArray;
        frente = 0;
        capacidad = nuevaCapacidad;
    }
}
```

#### Comparativa: nodos enlazados vs array circular

| Aspecto                   | Cola enlazada                          | Cola circular (array)                      |
| ------------------------- | -------------------------------------- | ------------------------------------------ |
| **Memoria**               | Dinámica (crece/decrece según demanda) | Bloques fijos (redimensionamiento costoso) |
| **Overhead por elemento** | Alto (nodo + referencia siguiente)     | Bajo (solo el dato en el array)            |
| **Localidad de caché**    | Pobre (nodos dispersos en memoria)     | Excelente (datos contiguos)                |
| **enqueue / dequeue**     | O(1) siempre                           | O(1) amortizado (O(n) al redimensionar)    |
| **Capacidad**             | Ilimitada (hasta agotar la memoria)    | Fija (con redimensionamiento opcional)     |

### 📚 La interfaz Queue en Java Collections <a href="#queue-collections" id="queue-collections"></a>

En la práctica profesional, rara vez se implementa una cola desde cero. Java proporciona la interfaz `java.util.Queue` dentro del **Java Collections Framework**, con múltiples implementaciones probadas y optimizadas. Conocerlas es esencial para cualquier desarrollador Java.

La interfaz `Queue` extiende `Collection` y define dos familias de métodos para cada operación — una que **lanza excepción** ante errores y otra que **devuelve un valor especial** (normalmente `null` o `false`):

| Operación     | Lanza excepción | Devuelve valor especial |
| ------------- | --------------- | ----------------------- |
| **Insertar**  | `add(e)`        | `offer(e)`              |
| **Extraer**   | `remove()`      | `poll()`                |
| **Consultar** | `element()`     | `peek()`                |

**✅ Buena práctica:** Prefiere `offer()`, `poll()` y `peek()` en código de producción. Las excepciones son costosas y las colas vacías no suelen ser condiciones excepcionales sino situaciones normales del flujo del programa.

#### Principales implementaciones de Queue

EjemplosQueue.java — Uso del Java Collections Framework

```
import java.util.*;

public class EjemplosQueue {
    public static void main(String[] args) {

        // 1. LinkedList como Queue (la más versátil)
        Queue<String> colaLinked = new LinkedList<>();
        colaLinked.offer("Primero");
        colaLinked.offer("Segundo");
        colaLinked.offer("Tercero");
        System.out.println("Poll: " + colaLinked.poll());   // Primero
        System.out.println("Peek: " + colaLinked.peek());   // Segundo

        // 2. ArrayDeque como Queue (más eficiente que LinkedList)
        Queue<Integer> colaArray = new ArrayDeque<>();
        colaArray.offer(10);
        colaArray.offer(20);
        colaArray.offer(30);
        System.out.println("Poll: " + colaArray.poll());    // 10

        // 3. PriorityQueue (ordenada por prioridad natural)
        Queue<Integer> colaPrioridad = new PriorityQueue<>();
        colaPrioridad.offer(30);
        colaPrioridad.offer(10);
        colaPrioridad.offer(20);
        System.out.println("Poll: " + colaPrioridad.poll()); // 10 (menor)

        // 4. Recorrer una cola sin destruirla
        System.out.println("Contenido colaLinked:");
        for (String elemento : colaLinked) {
            System.out.println("  " + elemento);
        }
    }
}
```

### ↔️ Colas de doble extremo (Deque) <a href="#deque-doble" id="deque-doble"></a>

Una **Deque** (_Double-Ended Queue_, pronunciado «dek») es una generalización de la cola que permite insertar y extraer elementos por **ambos extremos**. Java proporciona la interfaz `java.util.Deque` que extiende `Queue`.

Una Deque puede usarse como cola FIFO (usando `offerLast` y `pollFirst`) o como pila LIFO (usando `offerFirst` y `pollFirst`). La implementación recomendada es `ArrayDeque`, que es más rápida que `Stack` para pilas y más rápida que `LinkedList` para colas.

EjemploDeque.java — Cola de doble extremo

```
import java.util.ArrayDeque;
import java.util.Deque;

public class EjemploDeque {
    public static void main(String[] args) {
        Deque<String> deque = new ArrayDeque<>();

        // Insertar por ambos extremos
        deque.offerFirst("B");    // [B]
        deque.offerFirst("A");    // [A, B]
        deque.offerLast("C");     // [A, B, C]
        deque.offerLast("D");     // [A, B, C, D]

        System.out.println(deque); // [A, B, C, D]

        // Extraer por ambos extremos
        System.out.println("Primero: " + deque.pollFirst()); // A
        System.out.println("Último: " + deque.pollLast());   // D
        System.out.println(deque); // [B, C]

        // Usar como pila (LIFO)
        deque.push("X");          // Equivale a offerFirst
        System.out.println("Pop: " + deque.pop()); // X (pollFirst)
    }
}
```

| Operación     | Extremo inicio  | Extremo final  |
| ------------- | --------------- | -------------- |
| **Insertar**  | `offerFirst(e)` | `offerLast(e)` |
| **Extraer**   | `pollFirst()`   | `pollLast()`   |
| **Consultar** | `peekFirst()`   | `peekLast()`   |

### 🏆 Colas de prioridad (PriorityQueue) <a href="#priority-queue" id="priority-queue"></a>

Una **cola de prioridad** es una variante en la que los elementos no se procesan en orden de llegada sino en **orden de prioridad**. En Java, `PriorityQueue` implementa un **min-heap** binario: el elemento con menor valor (según el orden natural o un `Comparator`) siempre está en el frente.

SistemaUrgencias.java — Cola de prioridad con Comparator

```
import java.util.PriorityQueue;
import java.util.Comparator;

public class SistemaUrgencias {

    record Paciente(String nombre, int gravedad) {}

    public static void main(String[] args) {
        // Mayor gravedad = mayor prioridad (orden descendente)
        PriorityQueue<Paciente> urgencias = new PriorityQueue<>(
            Comparator.comparingInt(Paciente::gravedad).reversed()
        );

        urgencias.offer(new Paciente("Ana", 3));      // Leve
        urgencias.offer(new Paciente("Pedro", 9));     // Crítico
        urgencias.offer(new Paciente("María", 5));     // Moderado
        urgencias.offer(new Paciente("Juan", 10));     // Emergencia

        System.out.println("Orden de atención:");
        while (!urgencias.isEmpty()) {
            Paciente p = urgencias.poll();
            System.out.printf("  %s (gravedad: %d)%n", p.nombre(), p.gravedad());
        }
        // Juan (10), Pedro (9), María (5), Ana (3)
    }
}
```

**⚠️ Importante:** `PriorityQueue` NO garantiza un orden al iterar con un `for-each` o al imprimir con `toString()`. El orden de prioridad solo se garantiza al extraer con `poll()` o `remove()`. Esto es porque internamente la estructura es un heap, no un array ordenado.

| Operación       | PriorityQueue | Cola estándar (LinkedList)  |
| --------------- | ------------- | --------------------------- |
| `offer()`       | O(log n)      | O(1)                        |
| `poll()`        | O(log n)      | O(1)                        |
| `peek()`        | O(1)          | O(1)                        |
| Orden de salida | Por prioridad | FIFO (por orden de llegada) |

### 🌍 Casos de uso reales de las colas <a href="#casos-uso" id="casos-uso"></a>

Las colas son ubicuas en los sistemas informáticos reales. Comprender dónde se aplican es fundamental para elegir la estructura de datos correcta en cada situación:

#### En sistemas operativos

El **planificador de procesos** del sistema operativo utiliza colas para gestionar qué proceso se ejecuta a continuación. Los procesos en estado «listo» esperan en una cola de planificación. Los sistemas con múltiples niveles de prioridad usan colas de prioridad para que los procesos de tiempo real se ejecuten antes que los procesos de usuario.

#### En redes y comunicaciones

Los **routers** usan colas para gestionar paquetes de red cuando la velocidad de entrada supera la de salida. Los **buffers de impresión** son colas donde se almacenan los documentos esperando ser impresos en orden de llegada.

#### En desarrollo web y microservicios

Los **sistemas de mensajería** como RabbitMQ, Apache Kafka y Amazon SQS son esencialmente colas distribuidas. Se usan para desacoplar microservicios: un servicio encola un mensaje (por ejemplo, «procesar pedido #4521») y otro servicio lo desencola y lo procesa de forma asíncrona.

#### En algoritmos

El **recorrido en anchura** (BFS, _Breadth-First Search_) de [grafos](https://www.ciberaula.com/cursos/java/grafos_java.php) y [árboles](https://www.ciberaula.com/cursos/java/exploracion_arboles.php) utiliza una cola como estructura auxiliar para explorar los nodos nivel por nivel. También se usan en algoritmos de Dijkstra (con cola de prioridad) para encontrar caminos mínimos.

**💡 Dato profesional:** Si estás diseñando un sistema donde un componente produce datos más rápido de lo que otro los puede consumir, una cola (en cualquiera de sus variantes) es casi siempre la solución correcta. Este patrón se conoce como **productor-consumidor** y es uno de los más importantes en la arquitectura de software.

### 🚫 Errores comunes al trabajar con colas <a href="#errores-comunes" id="errores-comunes"></a>

| Error                                           | Problema                                                                            | Solución                                                           |
| ----------------------------------------------- | ----------------------------------------------------------------------------------- | ------------------------------------------------------------------ |
| **Desencolar sin verificar**                    | Llamar a `remove()` en cola vacía → `NoSuchElementException`                        | Usar `poll()` que devuelve `null`, o verificar con `isEmpty()`     |
| **No limpiar `cola` al vaciar**                 | En implementación propia, al desencolar el último elemento no se pone `cola = null` | Siempre verificar: `if (estaVacia()) cola = null;` tras desencolar |
| **Iterar PriorityQueue**                        | Esperar orden de prioridad al usar `for-each` → los elementos no salen ordenados    | Usar `poll()` en bucle para extraer en orden de prioridad          |
| **Usar Stack en vez de Deque**                  | La clase `Stack` hereda de `Vector` (sincronizada innecesariamente)                 | Usar `ArrayDeque` como pila: es más rápida y moderna               |
| **Cola circular sin módulo**                    | Los índices crecen sin envolver → `ArrayIndexOutOfBoundsException`                  | Siempre calcular: `(frente + i) % capacidad`                       |
| **No establecer `null` al desencolar en array** | La referencia al objeto permanece en el array → fuga de memoria (_memory leak_)     | Asignar `datos[frente] = null` antes de avanzar el índice          |

### 🏗️ Ejemplo integrador: sistema de atención al cliente <a href="#ejemplo-integrador" id="ejemplo-integrador"></a>

Vamos a combinar varios conceptos en un sistema realista de **atención al cliente** que usa una cola estándar para clientes normales y una cola de prioridad para clientes VIP. Este ejemplo demuestra cómo elegir la implementación correcta según el requisito de negocio.

SistemaAtencionCliente.java — Ejemplo completo

```
import java.util.*;

/**
 * Sistema de gestión de turnos con doble cola:
 * - Cola de prioridad para clientes VIP (ordenados por antigüedad VIP)
 * - Cola estándar FIFO para clientes normales
 * Los clientes VIP siempre se atienden antes que los normales.
 */
public class SistemaAtencionCliente {

    record Cliente(String nombre, boolean esVip, int antiguedadVip) {}

    private final Queue<Cliente> colaNormal;
    private final PriorityQueue<Cliente> colaVip;
    private int turnoActual;

    public SistemaAtencionCliente() {
        this.colaNormal = new ArrayDeque<>();
        // Mayor antigüedad = mayor prioridad
        this.colaVip = new PriorityQueue<>(
            Comparator.comparingInt(Cliente::antiguedadVip).reversed()
        );
        this.turnoActual = 0;
    }

    public void llegarCliente(String nombre, boolean esVip, int antiguedad) {
        turnoActual++;
        Cliente cliente = new Cliente(nombre, esVip, antiguedad);
        if (esVip) {
            colaVip.offer(cliente);
            System.out.printf("[Turno %d] Cliente VIP '%s' (antigüedad: %d años)%n",
                turnoActual, nombre, antiguedad);
        } else {
            colaNormal.offer(cliente);
            System.out.printf("[Turno %d] Cliente '%s'%n", turnoActual, nombre);
        }
    }

    public Cliente atenderSiguiente() {
        // Prioridad: primero VIP, luego normales
        Cliente siguiente;
        if (!colaVip.isEmpty()) {
            siguiente = colaVip.poll();
        } else if (!colaNormal.isEmpty()) {
            siguiente = colaNormal.poll();
        } else {
            System.out.println("No hay clientes en espera.");
            return null;
        }
        String tipo = siguiente.esVip() ? "VIP" : "Normal";
        System.out.printf(">> Atendiendo a %s [%s]%n", siguiente.nombre(), tipo);
        return siguiente;
    }

    public int clientesEnEspera() {
        return colaNormal.size() + colaVip.size();
    }

    public static void main(String[] args) {
        SistemaAtencionCliente sistema = new SistemaAtencionCliente();

        // Llegan clientes en distintos momentos
        sistema.llegarCliente("Laura", false, 0);
        sistema.llegarCliente("Miguel", false, 0);
        sistema.llegarCliente("Elena", true, 5);      // VIP 5 años
        sistema.llegarCliente("Carlos", false, 0);
        sistema.llegarCliente("Sofía", true, 12);      // VIP 12 años

        System.out.println("\nClientes en espera: " + sistema.clientesEnEspera());
        System.out.println("\n--- Orden de atención ---");

        while (sistema.clientesEnEspera() > 0) {
            sistema.atenderSiguiente();
        }
        // Sofía VIP (12 años), Elena VIP (5 años),
        // Laura, Miguel, Carlos (orden FIFO)
    }
}
```

Este ejemplo ilustra un patrón muy común en sistemas reales: combinar diferentes tipos de colas para manejar distintos niveles de prioridad. Los sistemas de _ticketing_ de soporte técnico, las salas de emergencia hospitalarias y los planificadores de tareas del sistema operativo utilizan estrategias similares.

### ✏️ Ejercicios prácticos <a href="#ejercicios" id="ejercicios"></a>

Ejercicio 1: Cola de impresión (Nivel: Básico)

Implementa un simulador de cola de impresión. El programa debe permitir: (a) añadir documentos a la cola indicando nombre y número de páginas, (b) imprimir el siguiente documento (mostrando su nombre y páginas), (c) mostrar cuántos documentos quedan en la cola. Usa `ArrayDeque`.

<details open>

<summary>Ver solución</summary>

ColaImpresion.java

```
import java.util.ArrayDeque;
import java.util.Queue;

public class ColaImpresion {
    record Documento(String nombre, int paginas) {}

    private final Queue<Documento> cola = new ArrayDeque<>();

    public void agregarDocumento(String nombre, int paginas) {
        cola.offer(new Documento(nombre, paginas));
        System.out.printf("Añadido: '%s' (%d páginas). En cola: %d%n",
            nombre, paginas, cola.size());
    }

    public void imprimirSiguiente() {
        Documento doc = cola.poll();
        if (doc == null) {
            System.out.println("No hay documentos en la cola.");
        } else {
            System.out.printf("Imprimiendo: '%s' (%d páginas). Restantes: %d%n",
                doc.nombre(), doc.paginas(), cola.size());
        }
    }

    public static void main(String[] args) {
        ColaImpresion impresora = new ColaImpresion();
        impresora.agregarDocumento("Informe.pdf", 15);
        impresora.agregarDocumento("Factura.pdf", 2);
        impresora.agregarDocumento("Manual.pdf", 120);
        impresora.imprimirSiguiente(); // Informe.pdf
        impresora.imprimirSiguiente(); // Factura.pdf
    }
}
```

</details>

Ejercicio 2: Invertir una cola (Nivel: Intermedio)

Escribe un método estático `invertir(Queue<Integer> cola)` que invierta el orden de los elementos de una cola **usando solo una pila** como estructura auxiliar. No se permite usar ningún otro tipo de colección ni array auxiliar.

<details open>

<summary>Ver solución</summary>

InvertirCola.java

```
import java.util.*;

public class InvertirCola {

    public static void invertir(Queue<Integer> cola) {
        Deque<Integer> pila = new ArrayDeque<>();
        // Paso 1: Vaciar cola en pila (invierte el orden)
        while (!cola.isEmpty()) {
            pila.push(cola.poll());
        }
        // Paso 2: Vaciar pila en cola (ya invertida)
        while (!pila.isEmpty()) {
            cola.offer(pila.pop());
        }
    }

    public static void main(String[] args) {
        Queue<Integer> cola = new LinkedList<>(List.of(1, 2, 3, 4, 5));
        System.out.println("Original: " + cola);  // [1, 2, 3, 4, 5]
        invertir(cola);
        System.out.println("Invertida: " + cola);  // [5, 4, 3, 2, 1]
    }
}
```

</details>

Ejercicio 3: BFS — Recorrido en anchura de un grafo (Nivel: Avanzado)

Implementa el algoritmo de **recorrido en anchura** (Breadth-First Search) de un grafo representado como lista de adyacencia. El método debe recibir el grafo (como `Map<Integer, List<Integer>>`) y un nodo de inicio, y devolver la lista de nodos visitados en el orden en que se descubrieron. Usa una `Queue` como estructura auxiliar.

<details open>

<summary>Ver solución</summary>

RecorridoBFS.java

```
import java.util.*;

public class RecorridoBFS {

    /**
     * Recorrido en anchura (BFS) de un grafo.
     * @param grafo Lista de adyacencia
     * @param inicio Nodo de partida
     * @return Lista de nodos en orden de descubrimiento
     */
    public static List<Integer> bfs(Map<Integer, List<Integer>> grafo, int inicio) {
        List<Integer> ordenVisita = new ArrayList<>();
        Set<Integer> visitados = new HashSet<>();
        Queue<Integer> cola = new ArrayDeque<>();

        cola.offer(inicio);
        visitados.add(inicio);

        while (!cola.isEmpty()) {
            int nodoActual = cola.poll();
            ordenVisita.add(nodoActual);

            // Explorar vecinos no visitados
            for (int vecino : grafo.getOrDefault(nodoActual, List.of())) {
                if (!visitados.contains(vecino)) {
                    visitados.add(vecino);
                    cola.offer(vecino);
                }
            }
        }
        return ordenVisita;
    }

    public static void main(String[] args) {
        //     0 --- 1 --- 3
        //     |     |
        //     2 --- 4
        Map<Integer, List<Integer>> grafo = Map.of(
            0, List.of(1, 2),
            1, List.of(0, 3, 4),
            2, List.of(0, 4),
            3, List.of(1),
            4, List.of(1, 2)
        );

        System.out.println("BFS desde 0: " + bfs(grafo, 0));
        // [0, 1, 2, 3, 4]
    }
}
```

</details>

### ❓ Preguntas frecuentes sobre Colas en Java (Queue): implementación y ejemplos

Las dudas más comunes respondidas de forma clara y directa.

¿Cuál es la diferencia entre una cola (Queue) y una pila (Stack)?¿Qué implementación de Queue es más eficiente en Java: LinkedList o ArrayDeque?¿Cuándo debo usar PriorityQueue en lugar de una cola normal?¿Qué sucede si intento extraer un elemento de una cola vacía en Java?¿Cómo implemento una cola thread-safe en Java para programación concurrente?¿Qué es una cola circular y cuál es su ventaja sobre una cola lineal con array?Valora este artículo¿Útil?👍👎

### 💬 Foro de discusión

¿Tienes dudas sobre Colas en Java (Queue): implementación y ejemplos? Comparte tu pregunta con la comunidad.

¿Tienes cuenta?Iniciar sesiónCrear cuentao comenta como invitado ↓✍️ Escribir un mensaje

Todavía no hay mensajes. ¡Sé el primero en participar!

🔥 Lo más buscado:[Cursos de Inteligencia Artificial](https://www.ciberaula.com/cursos-online-de-inteligencia-artificial)[Cursos de Python](https://www.ciberaula.com/cursos-online-de-programacion-con-python)[Cursos de ChatGPT](https://www.ciberaula.com/cursos-online-de-chatgpt)© 2026 Ciberaula — Todos los derechos reservadosAutor: Ángel Roldán🌙¿Te ayudo?MónicaEn línea✕

#### 👋 Antes de empezar...

Acepto que CiberAula almacene mis datos para atenderme. Puedo revocar este permiso en cualquier momento.Empezar a chatearMónica · Asistente de formación · CiberAula
