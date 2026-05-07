# Dominando las Estructuras de Datos en Java: Pilas y Colas

12



<figure><img src="https://miro.medium.com/v2/resize:fit:567/1*WeCTWolXdjSXPn-jR1xbmw.png" alt="" height="271" width="567"><figcaption></figcaption></figure>

### Introducción. <a href="#id-06db" id="id-06db"></a>

Las pilas y las colas son estructuras de datos fundamentales en el mundo de la programación. En este artículo, exploraremos en detalle qué son las pilas y las colas, cómo funcionan, y cómo implementarlas en Java utilizando las clases Stack y \`Queue\`.

### Pilas (Stack) <a href="#f096" id="f096"></a>

Una pila es una estructura de datos en la que los elementos se insertan y eliminan siguiendo el principio “último en entrar, primero en salir” (LIFO). Imagina una pila de libros: el último libro que se coloca en la pila es el primero en ser retirado. En Java, podemos implementar pilas utilizando la clase genérica \`Stack\`.

<figure><img src="https://miro.medium.com/v2/resize:fit:567/1*kBFlPUDr1OpNDdFnx7-BpQ.png" alt="" height="191" width="567"><figcaption><p>Funcionamiento de stack</p></figcaption></figure>

### Métodos mas usados. <a href="#id-5c12" id="id-5c12"></a>

* \`push\`: inserta un elemento en la pila.
* \`pop\`: elimina el elemento superior de la pila.
* \`peek\`: devuelve el elemento superior de la pila sin eliminarlo.
* \`isEmpty\`: verifica si la pila está vacía.
* \`search\`: busca un elemento en la pila y devuelve su distancia desde la parte superior.

### Implementación en Java <a href="#id-8a4a" id="id-8a4a"></a>

_**Ejemplo 01:**_**Pilas con la clase Stack**

```
public class ApplicationMain {
    public static void main(String[] args) {
        //Pilas con la clase Stack
        //Crear una pila de libros
        Stack<String> books = new Stack<>();
        //Agregando elementos a la pila
        books.push("Book 1");
        books.push("Book 2");
        books.push("Book 3");
        //Mostrando la pila
        System.out.println(books);
        //Ver el ultimo elemento
        System.out.println("ultimo elemento: " + books.peek());
        //Eliminar el ultimo elemento
        System.out.println("ultimo elemento eliminado: "+ books.pop());
        //ver luego de eliminar
        System.out.println(books);
        //buscar elemento
        System.out.println("ubicación de Book 1 respecto a la parte superior: "+ books.search("Book 1"));
    }
}
```

_**Ejemplo 02 : Navegador Web Simulado con Pilas**_

En este ejemplo se simula un navegador web básico utilizando una pila para rastrear el historial de navegación. Los usuarios pueden avanzar (forward) y retroceder (backward) a través del historial o salir del navegador (exit).

### Get Amador Quispe H.’s stories in your inbox

Join Medium for free to get updates from this writer.

Subscribe

Remember me for faster sign in

NOTA: Aunque con Stack no seria el mas adecuado, lo haré almacenando el índice del Stack (get)

```
import java.util.Scanner;
import java.util.Stack;

public class NavegadorWebSimulado {

    public static void main(String[] args) {
        stackNavigation();
    }

    public static void stackNavigation() {
        Stack<String> history = new Stack<>();
        Scanner sc = new Scanner(System.in);
        int pointerIndex = 0;

        while (true) {
            if (!history.isEmpty()) {
                System.out.println("-".repeat(15));
                history.forEach(h -> System.out.printf("%s | ", h));
                System.out.println("\n" + "-".repeat(16));
                System.out.print("Ingrese la 'página' o 'forward' para avanzar, 'backward' para retroceder, o 'exit' para salir: ");
            } else {
                System.out.println("Ingrese la página a visitar: ");
            }
            
            String command = sc.next();
            
            switch (command) {
                case "forward":
                    if (pointerIndex < history.size() - 1) {
                        pointerIndex++;
                        System.out.printf("Visualizando la página %s\n\n", history.get(pointerIndex));
                    } else {
                        System.out.println("No hay más historial hacia adelante\n\n");
                    }
                    break;
                    
                case "backward":
                    if (pointerIndex > 0) {
                        pointerIndex--;
                        System.out.printf("Visualizando la página %s\n\n", history.get(pointerIndex));
                    } else {
                        System.out.println("No hay más historial hacia atrás\n\n");
                    }
                    break;
                    
                case "exit":
                    System.out.println("Saliendo del navegador");
                    sc.close();
                    System.exit(0);
                    break;
                    
                default:
                    System.out.printf("Visualizando la página %s\n\n", command);
                    history.add(command);
                    pointerIndex = history.size() - 1;
                    break;
            }
        }
    }
}
```

### Colas (Queue) <a href="#id-5c90" id="id-5c90"></a>

Una cola es una estructura de datos en la que los elementos se insertan al final y se eliminan al principio, siguiendo el principio “primero en entrar, primero en salir” (FIFO). Piensa en una cola de banco: el primer cliente que llega es el primero en ser atendido. En Java, podemos implementar colas utilizando la interfaz \`Queue\`.

<figure><img src="https://miro.medium.com/v2/resize:fit:567/1*6Ze160ZkuWTGnBzx2dtAGQ.png" alt="" height="153" width="567"><figcaption></figcaption></figure>

### Métodos mas usados. <a href="#id-5957" id="id-5957"></a>

* \`add\`: inserta un elemento en la cola.
* \`poll\`: elimina y devuelve el primer elemento de la cola.
* \`peek\`: devuelve el primer elemento de la cola sin eliminarlo.
* \`isEmpty\`: verifica si la cola está vacía.

### Implementación en Java <a href="#id-0cac" id="id-0cac"></a>

_**Ejemplo 01 Colas con la interfaz Queue**_

```
public class ApplicationMain {
    public static void main(String[] args) {        
        //Colas con la clase Dequeue
        Queue<String> colas = new ArrayDeque<>();
        colas.add("Amador");
        colas.add("Alex");
        colas.add("Pedro");

        System.out.println(colas);
        //Eliminar el primer elimento
        System.out.println(colas.poll());

        System.out.println(colas);
    }
}
```

_**Ejemplo 02 Cola de Impresión Simulada**_

En este código se simula una cola de impresión básica en Java, donde los usuarios pueden agregar documentos a la cola (enqueue), imprimir un documento de la cola (print), imprimir todos los documentos de la cola (print-all), mostrar todos los documentos en la cola (show), o salir del programa (exit).

```
import java.util.LinkedList;
import java.util.Queue;
import java.util.Scanner;

public class ColaDeImpresionSimulada {

    public static void main(String[] args) {
        queuePrint();
    }

    public static void queuePrint() {
        Queue<String> jobPrints = new LinkedList<>();
        Scanner sc = new Scanner(System.in);
        
        System.out.println("Ingresa el comando 'enqueue' para agregar un archivo a la cola de impresión");
        System.out.println("Ingresa el comando 'print' para empezar a imprimir un documento de la cola");
        System.out.println("Ingresa el comando 'print-all' para imprimir todos los documentos de la cola");
        System.out.println("Ingresa el comando 'show' para mostrar todos los documentos en la cola");
        System.out.println("*".repeat(20));

        while (true) {
            System.out.print("Ingresa tu comando: ");
            String command = sc.next();
            
            switch (command) {
                case "show":
                    System.out.println("-".repeat(30));
                    System.out.println(String.format("Documentos en cola (%d)", jobPrints.size()));
                    for (String doc : jobPrints) {
                        System.out.println("-> " + doc);
                    }
                    break;
                    
                case "enqueue":
                    System.out.println("-".repeat(30));
                    System.out.print("Ingresa el nombre del documento a encolar: ");
                    String docName = sc.next();
                    jobPrints.add(docName);
                    break;
                    
                case "print":
                    System.out.println("-".repeat(30));
                    if (jobPrints.isEmpty()) {
                        System.out.println("No hay nada para imprimir");
                        break;
                    }
                    System.out.println("Imprimiendo -> " + jobPrints.poll());
                    try {
                        Thread.sleep(3000);
                    } catch (InterruptedException e) {
                        e.printStackTrace();
                    }
                    break;
                    
                case "print-all":
                    System.out.println("-".repeat(30));
                    System.out.println("Imprimiendo todos los documentos de la cola");
                    while (!jobPrints.isEmpty()) {
                        System.out.println("Imprimiendo -> " + jobPrints.poll());
                        try {
                            Thread.sleep(3000);
                        } catch (InterruptedException e) {
                            e.printStackTrace(System.out);
                        }
                    }
                    break;
                    
                case "exit":
                    System.out.println("Apagando impresora");
                    sc.close();
                    System.exit(0);
                    break;
                    
                default:
                    System.out.println("!".repeat(30));
                    System.out.println("Comando no reconocido");
                    break;
            }
        }
    }
}
```

### Conclusión <a href="#id-1f26" id="id-1f26"></a>

Las pilas y las colas son estructuras de datos esenciales en programación, utilizadas en una amplia variedad de aplicaciones. En Java, las implementamos utilizando las clases \`Stack\` y la interfaz \`Queue\`. Esperamos que esta guía te haya ayudado a comprender mejor estas estructuras y cómo utilizarlas en tus proyectos. ¡Explora más y experimenta con pilas y colas para mejorar tus habilidades de programación!
