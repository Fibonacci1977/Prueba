# Palabras de Java

## Palabras de Java

![buzzwords-of-java-0](https://www.java4coding.com/contents/java/images/buzzwords-of-java-0.png)

Los inventores de Java querían diseñar un lenguaje que pudiera ofrecer soluciones a algunos de los problemas encontrados en la programación moderna. Querían que el lenguaje fuera no sólo fiable, portátil y distribuido, sino también sencillo, compacto e interactivo. Los autores de Java han escrito un influyente Libro Blanco que explica las características de la java por todas las siguientes palabras de moda:

* Simple
* Objetos Orientedos
* Plataforma independiente
* Distribuido
* Robusto
* Segura
* Arquitectura Neutral
* Portable
* Interpretado
* Alto rendimiento
* Multihierto
* Dinámica

### Simple

Java es un lenguaje de programación orientado a objetos con sintaxis y palabras clave casi idéntica a C. Al desarrollar Java, sus creadores tostó todas las buenas características de los lenguajes de programación orientados a objetos existentes como C, Ada y Smalltalk, y eliminaron la mayoría de sus defectos y peculiaridades. Hay muchos aspectos del idioma Java que son consistentes y tienen sentido, por lo que es más fácil aprender.

Si usted está familiarizado con Cá usted sabría acerca de características torpe de C: archivos de cabecera, aritmética puntera (o incluso sintaxis de puntero), estructuras, uniones, sobrecarga de operador, clases de base virtual, etcétera. Todas estas características torpe están limpiadas en java haciendo que sea más fácil de aprender.

### Objetos Orientedos

#### Qué es el lenguaje de programación orientado a objetos (OOP)?

Cualquier lenguaje de programación si admite Encapsulation, Abstracción, Herencia, Polimorfismo entonces ese lenguaje de programación orientado a objetivos. Por ejemplo, java, C.

#### Definir conceptos OOP?

Si acabas de empezar a aprender java, definitivamente es muy difícil entender los conceptos de programación orientada a objetos (OOP). Una vez que aprendas java completamente entonces entenderás estos conceptos. Muchos profesionales de java que están usando estos conceptos en su vida diaria no definirán conceptos OOP (Programación Orientada de Objetos). A continuación se encuentran las definiciones de los conceptos OOP que seguramente le ayudarán cuando asista a las entrevistas de java.

Encapsulación : Es el proceso de encuadernación los datos y métodos juntos en una sola unidad. Ejemplo: Encuadernación de variables privadas con métodos de setter y getter.

Abstracción : Mostrar propiedades y métodos esenciales de un objeto escondiendo cosas internas se llama como Abstracción. La abstracción es posible si y sólo si hay encapsulación. Ejemplo: Java es una capa de abstracción sobre el lenguaje binario. Hibernate es una capa de abstracción sobre JDBC

Sucanza:

Polimorfismo:

### Plataforma independiente

Java puede ejecutarse en cualquier ventana de línea del sistema, Linux, mac, etc.

Traducir el programa de java en el código Byte hace mucho más fácil ejecutar un programa en amplia variedad de plataformas/Medio ambiente, porque sólo JVM necesita ser implementado. Una vez que el bytecode esté listo, podemos ejecutarlo en ventanas, Linux, calculadora, móvil, reloj, etc., pero una cosa es que todos los entornos requieren sólo JVM. Los detalles de JVM difieren de un entorno a otro. (Plataforma a Plataforma)

![buzzwords-of-java-1](https://www.java4coding.com/contents/java/images/buzzwords-of-java-1.png)

### Distribuido

* Se dice que una tecnología se distribuye si sus objetos de negocios se dispersan geográficamente en diferentes lugares y todavía se comunican entre sí.
* Las capacidades de red de java son fuertes y fáciles de usar. &#x20;
* Las tareas onerosas como abrir una conexión de enchutus son simples en Java. &#x20;
* Un mecanismo elegante, llamado servlets, hace que el procesamiento del lado del servidor en Java sea extremadamente eficiente. Muchos servidores web populares admiten servicios. &#x20;

### Robusto

El lenguaje de programación es robusto cuando es confiable y fuerte. Las capacidades de abajo hacen que la java robusta:

* Java tiene un colector de basura que limpiará automáticamente objetos y memoria no utilizados. No hay necesidad de perseguir la corrupción de la memoria. &#x20;
* En java no utiliza punteros para acceder a cadenas, matrices, objetos, incluso archivos. Tampoco tienes que preocuparte por la asignación de memoria para ellos. &#x20;
* Java tiene un mecanismo de manejo de excepciones que es muy útil en el manejo de errores de tiempo de compilación y ejecución. Sin errores de manejo y excepciones, toda la aplicación fracasaría. Con la excepción de manejarlo sólo detiene los flujos actuales incluso que son cuando fracasan, pero el descanso todos los flujos todavía funciona. &#x20;

### Segura

El equipo de Java ha dicho que tendrán una tolerancia a los bichos de seguridad e inmediatamente irá a trabajar en la fijación de cualquier bichos encontrados. El programa de Java se compilará primero al código byte. Este código byte será interpretado por Java Virtual Machine (JVM). JVM hace que la java sea segura con los factores siguientes:

* JVM no invadirá la pila de tiempo de ejecución. &#x20;
* JVM no corromperá la memoria fuera de su propio espacio de proceso. &#x20;
* JVM no leerá ni escribirá a los archivos locales cuando se invoque a través de un cargador de clase consciente de seguridad. &#x20;

### Arquitectura Neutral

El compilador genera instrucciones de bytecode neutro de arquitectura que no tienen nada que ver con la arquitectura informática particular. Estas instrucciones de código de bytecode pueden ser ejecutadas sólo por JVM. JVM no es lo mismo para plataformas y arquitecturas. Java le proporcionará diferentes JVMs para diferentes plataformas y arquitecturas. Así que sólo tienes que instalar diferentes JVMs. Un bytecode una vez listo puede ser dirigido por cualquier JVM.

Un programa escrito en sistema operativo de 32 bits puede ser administrado por JVM en sistema operativo de 64 bits.

### Portable

El tamaño de los datos en C/C varía de una plataforma a otra. Por ejemplo, el número entero puede ser un número entero de 16 bits, un número entero de 32 bits, o cualquier otro tamaño que le guste al proveedor de compiladores. En java tiene un tamaño fijo para los datos que elimina un gran dolor de cabeza portado. Los datos binarios se almacenan y transmiten en un formato fijo, eliminando la confusión en el endedio/poca ende. Las cuerdas se guardan en un formato Unicode estándar. Java hace esto por JVM. Java le facilita llevar el código de Java a cualquier plataforma. No requiere escribir un programa diferente para diferentes ventanas de línea de plataformas, Linux, etc...

### Interpretado

Java Virtual Machine (JVM) es el intérprete de java. El intérprete puede ejecutar códigos Java directamente en cualquier máquina a la que el intérprete haya sido portado. Dado que la instalación de JVM es un proceso ligero, el proceso de desarrollo puede ser mucho más rápido y exploratorio.

### Alto rendimiento

Cuando Java todavía era un nuevo idioma, fue criticado por ser lento: Desde Java bytecode fue ejecutado por un intérprete, parecía que los programas de Java bytecode nunca podrían funcionar tan rápido como los programas compilados en lenguaje de máquina nativa (es decir, el lenguaje automático real de la computadora en la que se ejecuta el programa). Sin embargo, este problema se ha visto superado en gran medida por el uso de

JIT

Es importante entender que no es práctico compilar todo un programa Java en el código ejecutable de una vez, porque Java realiza varios controles de ejecución que se pueden hacer sólo en tiempo de ejecución. En su lugar, un compilador JIT compila el código tal como es necesario, durante la ejecución. Además, no todas las secuencias de bytecode se compilan, sólo aquellas que se beneficiarán de la compilación. El código restante se interpreta simplemente. Las partes traducidas del programa pueden ejecutarse mucho más rápidamente de lo que podrían interpretarse. Dado que una parte dada de un programa se ejecuta a menudo muchas veces a medida que el programa se ejecuta, un compilador justo en tiempo puede acelerar significativamente el tiempo de ejecución general.

Aunque la compilación dinámica se aplica al código de bytecode, las características de portabilidad y seguridad todavía se aplican, porque la JVM sigue a cargo del entorno de ejecución.

### Multihilo

Un Se hace para usar tiempo inocuo de la CPU. Un proceso consiste en el espacio de memoria asignado por el sistema operativo que puede contener uno o más hilos. Un hilo no puede existir por sí solo; debe ser parte de un proceso. Siempre que se crea un hilo dentro de un programa no ocupará ningún espacio separado. Comparte el mismo espacio de memoria del programa. Tampoco consumirá más recursos.

Las implementaciones de hilo en las principales plataformas difieren ampliamente, pero Java no hace ningún esfuerzo para ser independiente de la plataforma en este sentido. Sólo el código para llamar a multihilo sigue siendo el mismo entre máquinas; Java descarga la implementación de multihilo al sistema operativo subyacente o una biblioteca de hilos.

### Dinámica

De varias maneras, Java es un lenguaje más dinámico que C o C. Fue diseñado para adaptarse a un entorno en evolución. Las bibliotecas pueden agregar libremente nuevos métodos y variables de instancia sin ningún efecto en sus clientes. En Java, averiguar la información del tipo de tiempo de ejecución es sencillo. Esta es una característica importante en aquellas situaciones en las que el código necesita ser agregado a un programa de ejecución.
