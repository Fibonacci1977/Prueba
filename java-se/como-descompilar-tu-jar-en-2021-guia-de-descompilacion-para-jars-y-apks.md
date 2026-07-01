# Cómo descompilar tu JAR en 2021: Guía de descompilación para JARs y APKs

{% embed url="https://youtu.be/fyF_NgKv0_M?si=vnWZST9pZ44gHYR0" %}

En los últimos días, me he divertido intentando comprender el funcionamiento interno de un archivo APK. Anteriormente, solo había usado el legendario [JD-GUI](http://java-decompiler.github.io/) como descompilador para algunos desafíos CTF. Pero al trabajar con código más complejo, descubrí que analizar la salida de diferentes descompiladores puede ser útil. Por lo tanto, investigué un poco para encontrar más descompiladores que utilizan enfoques distintos. Esta publicación sirve como una pequeña referencia sobre cómo crear y usar estas herramientas.

### Introducción <a href="#introduction" id="introduction"></a>

Comencemos por lo que tienen en común los archivos JAR y los archivos APK. Cuando se crea una aplicación para Android, el código fuente se compila primero en bytecode de la JVM. Posteriormente, este bytecode se compila en bytecode de Dalvik. Mientras que el bytecode de la JVM se encuentra en `.class`los archivos dentro de los JAR, el bytecode de Dalvik se encuentra en `.dex`los archivos dentro de los APK.

Esto significa que, para reconstruir el código fuente de un archivo APK, existen dos enfoques:

* o bien encontramos un descompilador que reconstruya directamente el código fuente a partir del código de bytes de Dalvik, o bien
* Traducimos el código de bytes de Dalvik a código de bytes de la JVM y, a partir de ahí, utilizamos un descompilador Java normal.

Para el primer enfoque, [jadx](https://github.com/skylot/jadx) es la mejor opción. Si tu objetivo es un archivo APK, definitivamente deberías probar esta herramienta. He visto que muchos analizadores de APK la utilizan, lo que probablemente significa que funciona bien.

El segundo enfoque requiere algún mecanismo para convertir `.dex`archivos en `.class`otros archivos. [Dex2jar](https://github.com/pxb1988/dex2jar) es sin duda la herramienta más conocida para ello. Sin embargo, me topé con [Enjarify](https://github.com/Storyyeller/enjarify) . Anuncia que funciona mejor para varios casos excepcionales:

> Dex2jar funciona razonablemente bien la mayor parte del tiempo, pero muchas características poco comunes o casos excepcionales pueden provocar fallos o incluso resultados incorrectos sin previo aviso. En cambio, Enjarify está diseñado para funcionar en la mayor cantidad de casos posible, incluso con código donde Dex2jar fallaría.

Encontrará más detalles [en el archivo README del proyecto](https://github.com/Storyyeller/enjarify/blob/master/README.md) .

Enjarify genera, como su nombre indica, un archivo JAR. A partir de ahí, se pueden utilizar varias herramientas populares para reconstruir el código fuente de Java.

En resumen, la siguiente figura ilustra las dos opciones que tenemos.

<figure><img src="https://www.eiken.dev/blog/2021/02/how-to-break-your-jar-in-2021-decompilation-guide-for-jars-and-apks/decompilation.min.svg" alt="Proceso de descompilación de un APK"><figcaption><p>Podemos usar jadx para descompilar directamente el APK, o podemos usar Enjarify, que nos permite utilizar descompiladores de Java más clásicos.</p></figcaption></figure>

### Descompiladores <a href="#decompilers" id="decompilers"></a>

A continuación, les mostraré qué descompiladores me interesaban especialmente y cómo instalarlos.

#### CFR <a href="#cfr" id="cfr"></a>

Cuando vi [la página principal de CFR](https://www.benf.org/other/cfr/) por primera vez, el proyecto rápidamente me convenció. Nada de interfaces sofisticadas basadas en JavaScript, solo un sitio HTML sencillo. La primera frase de la página me llamó la atención de inmediato:

> CFR descompila las características modernas de Java, incluyendo gran parte de Java 9, 12 y 14, pero está escrito completamente en Java 6, ¡así que funcionará en cualquier lugar!

Las versiones se pueden encontrar en [GitHub](https://github.com/leibnitz27/cfr) y otros sitios, aunque no estoy seguro de que sea completamente de código abierto. Al ser un proyecto Java, se compila fácilmente en un único archivo JAR.

Ese archivo JAR se puede utilizar de la siguiente manera:

<table data-header-hidden><thead><tr><th></th><th></th></tr></thead><tbody><tr><td><pre><code>1
</code></pre></td><td><pre class="language-bash"><code class="lang-bash">java -jar ./cfr.jar "$JARFILE" --outputdir "$OUTDIR"
</code></pre></td></tr></tbody></table>

¡Bastante sencillo!

Para archivos JAR de mayor tamaño, he observado que se agota la memoria. Si esto también te ocurre, puedes simplemente ajustar el tamaño del grupo de asignación de memoria de la JVM.

<table data-header-hidden><thead><tr><th></th><th></th></tr></thead><tbody><tr><td><pre><code>1
</code></pre></td><td><pre class="language-bash"><code class="lang-bash">java -Xmx4G -jar ./cfr.jar "$JARFILE" --outputdir "$OUTDIR"
</code></pre></td></tr></tbody></table>

Este ejemplo permitirá asignar un máximo de 4 GB.

En el directorio de salida, encontrará los `.java`archivos descompilados, junto con un resumen de la descompilación.

#### Flor de helecho <a href="#fernflower" id="fernflower"></a>

A continuación, tenemos [Fernflower](https://github.com/JetBrains/intellij-community/tree/master/plugins/java-decompiler/engine) , que forma parte de [IntelliJ IDEA](https://www.jetbrains.com/idea/) . Todos mencionan que es un descompilador _analítico_ (como se indica en la descripción del proyecto), pero nadie explica qué significa esto en realidad. Solo encontré [esta pregunta en Stack Overflow](https://stackoverflow.com/q/62298929) , que lamentablemente sigue sin respuesta hasta el día de hoy.

En cualquier caso, dado que no existen versiones autocontenidas, deberá compilarlo usted mismo. Al ser un proyecto basado en [Gradle](https://gradle.org/) , puede clonarlo y ejecutar el siguiente comando, siempre que Gradle esté instalado en su máquina.

<table data-header-hidden><thead><tr><th></th><th></th></tr></thead><tbody><tr><td><pre><code>1
</code></pre></td><td><pre class="language-bash"><code class="lang-bash">cd ./plugins/java-decompiler/engine &#x26;&#x26; gradle jar
</code></pre></td></tr></tbody></table>

Aquí, primero cambiamos nuestro directorio de trabajo al directorio raíz de Fernflower. Luego, le indicamos a Gradle que compile el archivo `./build/libs/fernflower.jar`.

La invocación de Fernflower es similar a la de CFR.

<table data-header-hidden><thead><tr><th></th><th></th></tr></thead><tbody><tr><td><pre><code>1
</code></pre></td><td><pre class="language-bash"><code class="lang-bash">java -jar ./fernflower.jar "$JARFILE" "$OUTDIR"
</code></pre></td></tr></tbody></table>

Entre los descompiladores descritos aquí, este es el único que genera los `.java`archivos en un archivo JAR. Puede extraer fácilmente los archivos fuente utilizando `unzip`.

#### Krakatoa <a href="#krakatau" id="krakatau"></a>

¿Recuerdan Enjarify de arriba? El mismo autor es también el desarrollador de un descompilador llamado [Krakatau](https://github.com/Storyyeller/Krakatau) .

A diferencia de los demás proyectos, este está escrito en Python. Y creo que esa es la razón por la que es un poco diferente a los demás.

Permítanme citar del [archivo README del proyecto](https://github.com/Storyyeller/Krakatau/blob/master/README.md) .

> A continuación, asegúrese de tener archivos JAR que contengan definiciones (¡sic!) para cualquier clase externa (es decir, bibliotecas) a la que pueda hacer referencia el archivo JAR que está intentando descompilar. Esto incluye las clases de la biblioteca estándar (es decir, JRT).

Según la descripción, estas clases de la biblioteca estándar vienen incluidas con Java hasta la versión 8 en el archivo `rt.jar`. Para versiones posteriores, el autor proporciona [jrt-extractor](https://github.com/Storyyeller/jrt-extractor) , que puede generar este archivo.

Entonces descargamos esa herramienta y ejecutamos los siguientes comandos.

<table data-header-hidden><thead><tr><th></th><th></th></tr></thead><tbody><tr><td><pre><code>1
2
3
</code></pre></td><td><pre class="language-bash"><code class="lang-bash">cd ./jrt-extractor
javac JRTExtractor.java
java -ea JRTExtractor
</code></pre></td></tr></tbody></table>

Esto debería haber escrito un archivo `rt.jar`dentro del directorio.

Dado este archivo, podemos ejecutar Krakatau de la siguiente manera.

<table data-header-hidden><thead><tr><th></th><th></th></tr></thead><tbody><tr><td><pre><code>1
</code></pre></td><td><pre class="language-bash"><code class="lang-bash">./Krakatau/decompile.py -out "$OUTDIR" -skip -nauto -path ./jrt-extractor/rt.jar "$JARFILE"
</code></pre></td></tr></tbody></table>

Para una explicación de los parámetros, consulte el repositorio de GitHub del proyecto. Tenga en cuenta que, para cualquier biblioteca utilizada por su archivo JAR, Krakatau le pedirá que la añada como un archivo JAR a la `-path`configuración.

#### Proción <a href="#procyon" id="procyon"></a>

El último y cuarto descompilador que examiné fue [Procyon](https://github.com/mstrobel/procyon) .

Aunque la wiki del proyecto enlaza con [las descargas en Bitbucket](https://bitbucket.org/mstrobel/procyon/downloads/) , al momento de escribir esto no hay descargas disponibles. Por eso intenté compilarlo yo mismo.

El proyecto también utiliza Gradle para la compilación. Por lo tanto, probemos `gradle jar`.

<table data-header-hidden><thead><tr><th></th><th></th></tr></thead><tbody><tr><td><pre><code> 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11
12
</code></pre></td><td><pre><code>> Task :Procyon.Reflection:compileJava FAILED
/tmp/procyon-develop/Procyon.Reflection/src/main/java/com/strobel/reflection/emit/TypeBuilder.java:1234: error: cannot find symbol
            _generatedClass = (Class&#x3C;T>) getUnsafeInstance().defineClass(
                                                            ^
  symbol:   method defineClass(String,byte[],int,int,ClassLoader,ProtectionDomain)
  location: class Unsafe
Note: Some input files use or override a deprecated API.
Note: Recompile with -Xlint:deprecation for details.
1 error


FAILURE: Build failed with an exception.
</code></pre></td></tr></tbody></table>

¡Oh no! Este no compila correctamente.

Como último recurso, comprobé si había algo en los repositorios y, por suerte, al menos en Debian, está empaquetado y listo para usar.

Una vez instalado, su uso es sencillo.

<table data-header-hidden><thead><tr><th></th><th></th></tr></thead><tbody><tr><td><pre><code>1
</code></pre></td><td><pre class="language-bash"><code class="lang-bash">procyon -jar "$JARFILE" -o "$OUTDIR"
</code></pre></td></tr></tbody></table>

Pero un momento, si Debian incluye Procyon en sus paquetes, debe haber una forma de compilarlo.

Una búsqueda rápida en su sistema de seguimiento de errores reveló el error [n.° 909259. ¡](https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=909259) Los responsables del mantenimiento tenían exactamente el mismo problema!

Veamos cómo modificaron el código fuente para solucionarlo. La discusión en el informe de errores enlaza con [esta diferencia de commit](https://salsa.debian.org/java-team/procyon/commit/6cc3de7e70d327fa597af22d3da08015aabd1620) . Allí podemos ver que se añadió un parche para la compatibilidad con OpenJDK 11.

Tuve que modificar el parche, ya que el código fuente original se había desviado, pero finalmente logré compilarlo. Si quieres compilarlo tú mismo, [aquí tienes el archivo de parche](https://www.eiken.dev/blog/2021/02/how-to-break-your-jar-in-2021-decompilation-guide-for-jars-and-apks/compat.patch) que me funcionó.

Primero, aplique el parche y luego ejecute Gradle para compilar el proyecto.

<table data-header-hidden><thead><tr><th></th><th></th></tr></thead><tbody><tr><td><pre><code>1
2
3
</code></pre></td><td><pre class="language-bash"><code class="lang-bash">cd ./procyon
patch -p1 &#x3C; ../compat.patch
gradle fatJar
</code></pre></td></tr></tbody></table>

Esto debería crear el archivo `./build/Procyon.Decompiler/libs/procyon-decompiler-1.0-SNAPSHOT.jar`, que es su descompilador Procyon recién compilado.

### Descompiladores para ir <a href="#decompilers-to-go" id="decompilers-to-go"></a>

Quizás te estés preguntando: ¿No hay una forma más fácil? Y supongo que depende.

Las herramientas con interfaz gráfica, como [Bytecode Viewer,](https://github.com/Konloch/bytecode-viewer) también utilizan varios descompiladores internamente y permiten visualizar sus resultados de forma clara y comparativa. Sin embargo, prefiero el método manual para ver qué parámetros puedo ajustar. Así se tiene mayor control sobre cómo se ejecuta un descompilador y, probablemente, se aprendan cosas nuevas.

Para que todo sea un poco más accesible, creé una [imagen Docker](https://hub.docker.com/r/eikendev/java-decompiler) donde los cuatro descompiladores están disponibles de forma predeterminada. Visita [la página de GitHub del proyecto](https://github.com/eikendev/java-decompiler) para hacerte una idea de cómo usarlo.

Cabe destacar que también incluye la capacidad de descompilar archivos APK. Como ya se mencionó, Enjarify se utiliza para convertir archivos APK a JAR. Además, descompila los archivos APK mediante jadx.

### Conclusión <a href="#conclusion" id="conclusion"></a>

Este post fue deliberadamente breve y práctico. El objetivo era dejar constancia de mis pasos para consultarlos en el futuro, y pensé que podría ser útil para otros.

Si la descompilación no da resultado, otras herramientas podrían ser útiles. En lugar de intentar reconstruir el código fuente, tal vez baste con ajustar ligeramente el comportamiento del programa objetivo. En ese caso, debería considerar la instrumentación que ofrecen [Frida](https://frida.re/) y [Soot](https://soot-oss.github.io/soot/) .

Bueno, eso es todo. ¡Gracias por leer!

## Explicación del descompilador de Java: cómo funciona, herramientas y casos de uso



<img src="https://www.digitalocean.com/api/static-content/v1/images?src=https%3A%2F%2Fdoimages.nyc3.cdn.digitaloceanspaces.com%2F007BlogBanners2024%2Fcloud-partner-1%28lavender%29.png&#x26;width=1920" alt="Explicación del descompilador de Java: cómo funciona, herramientas y casos de uso" height="376" width="752">

<details open>

<summary><a href="https://www.digitalocean.com/community/tutorials/java-compiler#introduction">Introducción</a></summary>

Si alguna vez te has topado con un `.class`archivo y has deseado poder leer su código fuente original, no eres el único. Ya sea que estés depurando código heredado, realizando auditorías de seguridad o aplicando ingeniería inversa a aplicaciones con fines educativos, un **descompilador de Java** es la herramienta ideal.

En esta guía exhaustiva, te explicaremos todo lo que necesitas saber sobre los descompiladores de Java: desde cómo funciona la compilación de Java hasta las mejores herramientas para descompilar `.class`archivos. Tanto si eres principiante como desarrollador experimentado, este artículo está diseñado para ofrecerte información práctica y un análisis técnico profundo.

</details>

<details open>

<summary><a href="https://www.digitalocean.com/community/tutorials/java-compiler#what-is-a-java-decompiler">¿Qué es un descompilador de Java?</a></summary>

Un **descompilador de Java** es una utilidad que convierte el código de bytes de Java ( `.class`archivos compilados) de nuevo en código fuente Java legible. Básicamente, revierte el proceso de compilación, lo que permite a los desarrolladores reconstruir el código fuente a partir de programas Java compilados.

Piénsalo como el botón de "deshacer" para la compilación de Java: aunque no siempre es perfecto, a menudo proporciona una imagen lo suficientemente clara para que los desarrolladores comprendan la lógica original.

</details>

<details open>

<summary><a href="https://www.digitalocean.com/community/tutorials/java-compiler#how-the-java-compilation-process-works">Cómo funciona el proceso de compilación de Java</a></summary>

Cuando escribes código Java y lo guardas como un `.java`archivo, solo has completado la mitad del proceso. Ese archivo fuente necesita convertirse en bytecode antes de que pueda ejecutarse en la Máquina Virtual de Java (JVM). Así es como funciona:

1. **Código fuente ( `.java`)** : Usted escribe su programa Java.
2. **Compilación ( `javac`)** : El compilador de Java ( `javac`) traduce el código fuente a **bytecode de Java** ( `.class`archivos).
3. **Ejecución (JVM)** : La JVM lee y ejecuta estos archivos de código de bytes en diferentes plataformas.

Este proceso de compilación garantiza la independencia de plataforma de Java: escribe una vez, ejecuta en cualquier lugar.

Si estás empezando, consulta nuestra guía sobre [cómo escribir tu primer programa en Java](https://www.digitalocean.com/community/tutorials/how-to-write-your-first-program-in-java) para obtener una explicación práctica paso a paso.

</details>

<details open>

<summary><a href="https://www.digitalocean.com/community/tutorials/java-compiler#java-compiler-vs-interpreter">Compilador de Java vs. Intérprete</a></summary>

Para los desarrolladores, comprender la distinción entre las fases de compilación e interpretación de Java es fundamental. Si bien ambos procesos trabajan juntos para ejecutar programas Java, cumplen funciones fundamentalmente diferentes en el modelo de ejecución de Java.

| Aspecto                      | Compilador de Java ( `javac`)                      | Intérprete de Java (JVM)                                    |
| ---------------------------- | -------------------------------------------------- | ----------------------------------------------------------- |
| Función                      | Traduce el código fuente a código de bytes.        | Ejecuta código de bytes                                     |
| Producción                   | `.class`archivos                                   | Salida del programa                                         |
| Velocidad                    | Rápido para traducción                             | La ejecución en tiempo de ejecución puede ser más lenta.    |
| Herramienta                  | `javac`                                            | Máquina Virtual de Java (JVM)                               |
| Tiempo de procesamiento      | Fase de compilación única                          | Ejecución continua en tiempo de ejecución                   |
| Detección de errores         | Errores y advertencias en tiempo de compilación    | Excepciones y errores en tiempo de ejecución                |
| Dependencia de la plataforma | Código de bytes independiente de la plataforma     | Ejecución específica de la plataforma                       |
| Uso de memoria               | Mínimo durante la compilación                      | Varía según los requisitos del programa.                    |
| Nivel de optimización        | Optimizaciones básicas en tiempo de compilación    | Optimizaciones avanzadas de JIT y de tiempo de ejecución    |
| Soporte para depuración      | Información de depuración a nivel de código fuente | Depuración y análisis de rendimiento en tiempo de ejecución |
| Despliegue                   | Requiere compilación antes de la ejecución.        | Ejecución directa de código de bytes                        |

Un error común es pensar que Java es puramente compilado o puramente interpretado; en realidad, es ambas cosas. El compilador se encarga de la traducción, mientras que la JVM interpreta o compila justo a tiempo el código de bytes en tiempo de ejecución.

</details>

<details open>

<summary><a href="https://www.digitalocean.com/community/tutorials/java-compiler#what-is-java-bytecode">¿Qué es el código de bytes de Java?</a></summary>

**El bytecode** es la representación intermedia de tu programa Java. Se trata de un conjunto de instrucciones de bajo nivel e independientes de la plataforma que la JVM puede comprender y ejecutar. Piensa en él como un lenguaje universal que sirve de puente entre el código fuente Java legible por humanos y las instrucciones específicas de la máquina.

Ejemplo de fragmento de código de bytes (generado por `javac`):

```
javac HelloWorld.java
```

```
// Decompiled version (simplified)
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

Pero, en realidad, todo se reduce a códigos de operación numéricos que la JVM entiende. Los descompiladores ayudan a convertirlos de nuevo a un formato legible.

</details>

<details open>

<summary><a href="https://www.digitalocean.com/community/tutorials/java-compiler#what-is-the-role-of-the-jvm-java-virtual-machine">¿Cuál es la función de la JVM (Máquina Virtual de Java)?</a></summary>

La **Máquina Virtual de Java (JVM)** desempeña un papel fundamental en la ejecución de programas Java. Su función es:

Para obtener un desglose de las diferencias entre JDK, JRE y JVM, consulte nuestra guía sobre [las diferencias entre jdk, jre y jvm](https://www.digitalocean.com/community/tutorials/difference-jdk-vs-jre-vs-jvm) .

* Carga los archivos compilados `.class`desde el sistema de archivos a la memoria para su ejecución y procesamiento por el entorno de ejecución de la JVM.
* Verifica la integridad del código de bytes mediante comprobaciones de seguridad exhaustivas para garantizar que el código no haya sido manipulado ni corrompido durante la transmisión.
* Ejecuta el programa mediante interpretación o compilación JIT, dependiendo de los requisitos de rendimiento y los patrones de frecuencia de ejecución.
* Proporciona servicios de tiempo de ejecución que incluyen gestión automática de memoria mediante recolección de basura y capacidades de subprocesos múltiples para ejecución concurrente.

Sin la JVM, los `.class`archivos compilados serían ilegibles e imposibles de ejecutar en su sistema.

</details>

<details open>

<summary><a href="https://www.digitalocean.com/community/tutorials/java-compiler#how-java-decompilation-works">Cómo funciona la descompilación de Java</a></summary>

La descompilación en Java implica analizar el código de bytes y reconstruir el código fuente Java equivalente. Si bien rara vez es una reconstrucción perfecta (se pierden los comentarios, los nombres de variables originales y el formato), funciona bastante bien para:

* **Depuración de clases ofuscadas** : Al trabajar con código de bytes Java ofuscado intencionalmente, los descompiladores ayudan a realizar ingeniería inversa de la lógica original al convertir el código de bytes complejo e ilegible de nuevo en código fuente Java comprensible, lo que permite identificar errores, vulnerabilidades de seguridad o comprender el comportamiento del programa a pesar de las técnicas de ofuscación deliberadas.
* **Recuperación de código fuente perdido** : En situaciones en las que el código fuente original se ha eliminado accidentalmente, se ha dañado o ya no está disponible, los descompiladores pueden reconstruir una aproximación funcional del código Java original a partir de `.class`archivos compilados, lo que permite a los desarrolladores restaurar o recrear sus aplicaciones cuando el repositorio de código fuente es inaccesible o incompleto.
* **Análisis de código malicioso** : Los investigadores de seguridad y los analistas de malware utilizan descompiladores para examinar aplicaciones Java potencialmente dañinas, convirtiendo su código de bytes compilado en código fuente legible. Esto permite un análisis detallado del comportamiento del código, la identificación de amenazas de seguridad y la comprensión de cómo funciona el software malicioso para desarrollar contramedidas y parches de seguridad adecuados.
* **Aprender cómo funcionan internamente las bibliotecas** : Los desarrolladores pueden usar descompiladores para explorar la implementación interna de bibliotecas y marcos de trabajo de terceros examinando su código de bytes compilado, obteniendo información sobre patrones de diseño, algoritmos y técnicas de codificación utilizadas por desarrolladores experimentados, lo que ayuda a mejorar sus propias habilidades de programación y su comprensión de arquitecturas de software complejas.

#### [Descripción general del proceso](https://www.digitalocean.com/community/tutorials/java-compiler#process-overview)

1. Analizar `.class`la estructura del archivo (grupo de constantes, métodos, campos)
2. Mapear las instrucciones de código de bytes a sus equivalentes en Java.
3. Generar código Java sintácticamente correcto
4. Código fuente de salida para visualización o edición.

</details>

<details open>

<summary><a href="https://www.digitalocean.com/community/tutorials/java-compiler#best-java-decompiler-tools">Las mejores herramientas de descompilación de Java</a></summary>

| Herramienta         | Tipo                   | Reflejos                                          |
| ------------------- | ---------------------- | ------------------------------------------------- |
| **JD-GUI**          | Herramienta GUI        | Ligero, rápido, ideal para inspección             |
| **Flor de helecho** | Línea de comandos/IDE  | Utilizado en IntelliJ IDEA, de código abierto.    |
| **CFR**             | CLI/GUI                | Maneja bien las características modernas de Java. |
| **Proción**         | CLI/Lib                | Ideal para Java 8+ y expresiones lambda.          |
| **JADX**            | Herramienta de Android | Descompila `.dex`y `.class`archiva                |

> Consejo: Si utilizas IntelliJ IDEA o Eclipse, complementos como Fernflower y Enhanced Class Decompiler facilitan enormemente el proceso.

</details>

<details open>

<summary><a href="https://www.digitalocean.com/community/tutorials/java-compiler#online-java-decompiler-tools">Herramientas de descompilación de Java en línea</a></summary>

¿Necesitas algo rápido y accesible? Los descompiladores de Java en línea te permiten ver el contenido de `.class`los archivos sin descargar ningún software. Estas herramientas son especialmente útiles para inspecciones rápidas, fines educativos o cuando trabajas en un sistema donde no puedes instalar software de escritorio.

Entre las opciones más populares se incluyen:

1. [http://javadecompilers.com/](http://javadecompilers.com/) — Admite múltiples descompiladores y cargas por lotes.
2. [https://bytecodeviewer.com/](https://bytecodeviewer.com/) — Ofrece una interfaz de usuario interactiva y admite archivos de ambos `.class`tipos `.jar`.
3. [https://www.decompiler.com/](https://www.decompiler.com/) — Ligero y rápido, adecuado para una descompilación rápida.

Si bien son prácticas, las herramientas en línea suelen tener dificultades con código de bytes complejo, clases ofuscadas o proyectos de gran tamaño. Para un mejor rendimiento y mayor privacidad, se recomienda el uso de herramientas de descompilación locales.

</details>

<details open>

<summary><a href="https://www.digitalocean.com/community/tutorials/java-compiler#how-to-use-the-javac-command-with-examples">Cómo usar el <code>javac</code>comando (con ejemplos)</a></summary>

El `javac`comando es el compilador oficial de Java que transforma archivos fuente legibles por humanos `.java`en código de bytes independiente de la plataforma ( `.class`archivos .by). Forma parte del Kit de Desarrollo de Java (JDK) y sirve como base para todos los flujos de trabajo de desarrollo de Java.

```
javac MyProgram.java
```

Esto compila un único archivo fuente Java con un nombre específico `MyProgram.java`y genera un archivo de código de bytes correspondiente `MyProgram.class`.

Para compilar varios archivos en el directorio actual:

```
javac *.java
```

Este comando utiliza un comodín para compilar todos `.java`los archivos a la vez, lo cual resulta útil cuando el programa abarca varios archivos fuente.

Para especificar un directorio de salida para los `.class`archivos compilados:

```
javac -d out/ MyProgram.java
```

El `-d`indicador especifica `javac`que se coloque el `.class`archivo compilado en el `out/`directorio, lo que ayuda a organizar los artefactos de compilación.

Para incluir información de depuración (útil para IDE y depuradores):

```
javac -g MyProgram.java
```

Esto genera metadatos adicionales en el `.class`archivo, incluidos números de línea y nombres de variables, lo que permite una depuración avanzada.

Finalmente, para ejecutar el programa compilado usando la JVM:

```
java MyProgram
```

Ejecuta la `MyProgram`clase usando la Máquina Virtual de Java. Asegúrate de estar en el directorio que contiene `MyProgram.class`, o ajusta la ruta de clases según corresponda.

</details>

<details open>

<summary><a href="https://www.digitalocean.com/community/tutorials/java-compiler#common-java-compilation-errors-and-how-to-fix-them">Errores comunes de compilación de Java y cómo solucionarlos</a></summary>

Al compilar código Java, es común encontrar errores. Comprender estos errores y cómo solucionarlos es fundamental para un desarrollo eficiente. A continuación, se presentan algunos errores comunes de compilación de Java, sus causas y los pasos para corregirlos:

| Error                    | Causa                                                  | Arreglar                                               |
| ------------------------ | ------------------------------------------------------ | ------------------------------------------------------ |
| `cannot find symbol`     | Variable/método no declarado                           | Declarar o importar elementos faltantes                |
| `class not found`        | Error tipográfico en el nombre o ruta de la clase.     | Verifique la ruta de clases y los nombres de archivo.  |
| `package does not exist` | Falta importación o biblioteca                         | Incluir `import`la declaración o dependencia correcta. |
| `main method not found`  | No hay punto de entrada                                | Agregar`public static void main(String[] args)`        |
| Errores de sintaxis      | Errores tipográficos o falta de punto y coma/corchetes | Revisa el código                                       |

Estos errores son relativamente fáciles de corregir una vez que se adquiere el hábito de leer atentamente la salida del compilador. Es fundamental comprender los mensajes de error y tomar las medidas necesarias para solucionarlos.

</details>

<details open>

<summary><a href="https://www.digitalocean.com/community/tutorials/java-compiler#java-compiler-in-jdk-vs-ide-based-compilers">Compilador Java en JDK frente a compiladores basados ​​en IDE</a></summary>

Los compiladores de Java se presentan en dos variantes principales: el compilador JDK ( `javac`) y los compiladores basados ​​en IDE, como los que se encuentran en Eclipse o IntelliJ. Cada uno tiene sus ventajas y desventajas, lo que los hace adecuados para diferentes casos de uso. A continuación, se presenta una comparación de estos compiladores:

| Característica           | Compilador JDK ( `javac`)   | Compilador IDE (Eclipse/IntelliJ)                        |
| ------------------------ | --------------------------- | -------------------------------------------------------- |
| Plataforma               | Línea de comandos           | Basado en GUI                                            |
| Velocidad de compilación | Un poco más lento           | Optimizado para la velocidad con almacenamiento en caché |
| Comentario               | Post-compilación            | Verificación de sintaxis en tiempo real                  |
| Integración              | Pasos de compilación manual | Compilaciones y refactorización automatizadas            |

La elección entre `javac`un compilador de línea de comandos y un compilador de IDE depende de las necesidades de tu proyecto. Para tareas de automatización y scripting, el `javac`compilador de línea de comandos es ideal por su interfaz de línea de comandos y flexibilidad. Por otro lado, los compiladores de IDE son más adecuados para la facilidad de uso y la productividad, ya que ofrecen funciones como la verificación de sintaxis en tiempo real y la compilación automatizada.

</details>

<details open>

<summary><a href="https://www.digitalocean.com/community/tutorials/java-compiler#java-compiler-in-ci-cd-pipelines">Compilador Java en pipelines de CI/CD</a></summary>

En los flujos de trabajo de CI/CD, el compilador de Java desempeña un papel fundamental en la creación y el empaquetado de aplicaciones. Paso típico del pipeline:

```
steps:
  - name: Compile Java Code
    run: javac -d build/ src/**/*.java
```

Incluso puedes [compilar y ejecutar un programa Java desde otro programa Java](https://www.digitalocean.com/community/tutorials/compile-run-java-program-another-java-program) para escenarios de automatización avanzados.

Herramientas como Jenkins, GitHub Actions y GitLab CI/CD admiten pipelines de compilación de Java mediante:

* `javac`para compilación
* `JUnit`para pruebas
* `Maven`o `Gradle`para embalaje

También puedes integrar el análisis de código de bytes, los escaneos de seguridad y la firma de artefactos en tu flujo de trabajo.

</details>

<details open>

<summary><a href="https://www.digitalocean.com/community/tutorials/java-compiler#common-mistakes-developers-make">Errores comunes que cometen los desarrolladores</a></summary>

1. **Ignorar indicadores de compilación** : `javac`contiene indicadores para advertencias, depuración y optimizaciones. Úselos. Muchos desarrolladores pasan por alto indicadores importantes como `-Xlint:all`advertencias completas, `-g`información de depuración y `-O`optimizaciones que pueden mejorar significativamente la calidad y el rendimiento del código durante los ciclos de desarrollo.
2. **Olvidar el papel de la JVM** : La compilación no es suficiente. Es fundamental comprender los modelos de memoria e hilos de la JVM. Los desarrolladores suelen centrarse únicamente en la compilación sin considerar cómo la JVM ejecutará su código de bytes, lo que provoca problemas de rendimiento, fugas de memoria y comportamientos inesperados en entornos de producción donde la optimización de la JVM resulta crucial.
3. **No usar control de versiones** : Compilar con versiones de JDK y de tiempo de ejecución incompatibles puede causar problemas. Este error común ocurre cuando los desarrolladores usan versiones de Java diferentes para la compilación y la ejecución, lo que provoca problemas de compatibilidad, funcionalidades faltantes o errores de tiempo de ejecución difíciles de diagnosticar y resolver en escenarios de implementación complejos.
4. **Omitir la descompilación durante la depuración** : Los archivos descompilados `.class`pueden revelar mucha información sobre errores o integraciones de terceros. Por ejemplo, si trabaja con un archivo JAR de código cerrado que genera `NullPointerException`errores inesperados, puede usar un descompilador como **CFR** para inspeccionar la estructura de la clase y las implementaciones de los métodos. Esto puede ayudar a descubrir comprobaciones de nulidad faltantes, variables inicializadas incorrectamente o errores lógicos en código de terceros que no están documentados públicamente. La descompilación puede convertir el código de bytes opaco en información útil.

</details>

<details open>

<summary><a href="https://www.digitalocean.com/community/tutorials/java-compiler#frequently-asked-questions">Preguntas frecuentes</a></summary>

**P1: ¿Para qué se utiliza el compilador de Java?**\
R: El compilador de Java ( `javac`) sirve como la herramienta de traducción principal que convierte el código fuente Java legible por humanos, escrito en `.java`archivos, en código de bytes independiente de la plataforma, almacenado en `.class`archivos. Este código de bytes puede ser ejecutado por la Máquina Virtual de Java (JVM) en cualquier plataforma que admita Java, lo que permite el principio de "escribe una vez, ejecuta en cualquier lugar" que hace que las aplicaciones Java sean portátiles en diferentes sistemas operativos y arquitecturas de hardware.

**P2: ¿Qué comando se usa para compilar un programa Java?**\
R: Para compilar un programa Java, se usa el `javac`comando seguido del nombre del archivo con la `.java`extensión. La sintaxis básica se encuentra `javac <filename>.java`en la terminal o el símbolo del sistema. Por ejemplo, para compilar un archivo llamado `HelloWorld.java`, se ejecutaría `javac HelloWorld.java`. Este comando lee el código fuente, realiza una comprobación de sintaxis y genera los archivos correspondientes `.class`que contienen el código de bytes compilado que la JVM puede ejecutar.

**P3: ¿Puedo usar un compilador de Java en línea?**\
R: Sí, existen numerosos compiladores y entornos de desarrollo de Java en línea que permiten escribir, compilar y ejecutar código Java directamente en el navegador web sin necesidad de instalar ningún software localmente. Algunas opciones populares son JDoodle, [Repl.it](http://repl.it/) , Programiz y [javadecompilers.com](http://javadecompilers.com/) . Estas plataformas ofrecen entornos basados ​​en navegador con resaltado de sintaxis, comprobación de errores y compilación instantánea, lo que facilita el aprendizaje, la prueba de pequeños fragmentos de código o la demostración de conceptos de Java sin necesidad de configurar un entorno de desarrollo local.

**P4: ¿Cuál es la diferencia entre un compilador y un intérprete en Java?**\
R: En Java, el compilador ( `javac`) y el intérprete (JVM) cumplen funciones distintas pero complementarias en el proceso de ejecución. El compilador traduce todo el código fuente de Java a bytecode durante la fase de compilación, realizando análisis sintáctico, comprobación de tipos y optimización. El intérprete, representado por la JVM, lee y ejecuta este bytecode en tiempo de ejecución, ya sea interpretándolo directamente o utilizando la compilación justo a tiempo (JIT) para convertir el bytecode de ejecución frecuente en código máquina nativo para un mejor rendimiento.

**P5: ¿Cómo maneja el compilador de Java las diferentes versiones de Java y la compatibilidad con versiones anteriores?**\
R: El compilador de Java utiliza las banderas `-source`y para controlar la compilación para versiones específicas de Java. La bandera especifica con qué versión del lenguaje Java se debe compilar el código fuente, mientras que determina la versión mínima de JVM necesaria para ejecutar el bytecode compilado. Por ejemplo, compila código compatible con Java 8. Esto permite a los desarrolladores escribir código utilizando características más recientes del lenguaje, al tiempo que garantiza la compatibilidad con versiones anteriores de JVM, aunque algunas características pueden requerir comprobaciones en tiempo de ejecución o implementaciones alternativas para la compatibilidad con versiones anteriores.`-target-source-targetjavac -source 8 -target 8`

**P6: ¿Cuáles son las técnicas clave de optimización que utiliza el compilador de Java?**\
R: El compilador de Java ( `javac`) realiza varias fases de optimización durante la compilación, incluyendo la reducción de constantes (evaluación de expresiones constantes en tiempo de compilación), la eliminación de código muerto (eliminación de código inalcanzable), la inserción de métodos (sustitución de llamadas a métodos con el cuerpo real del método para métodos pequeños) y la optimización de bucles. Sin embargo, la mayoría de las optimizaciones significativas ocurren en tiempo de ejecución a través del compilador Just-In-Time (JIT) de la JVM, que puede realizar optimizaciones avanzadas como el análisis de escape, el desenrollado de bucles y la compilación adaptativa basada en datos de perfilado en tiempo de ejecución.

**P7: ¿Cómo maneja el compilador de Java los genéricos y el borrado de tipos?**\
R: El compilador de Java implementa los genéricos mediante el borrado de tipos, un proceso en el que la información de tipo genérico se elimina durante la compilación y se reemplaza con conversiones de tipo y métodos puente. Por ejemplo, `List<String>`se convierte `List`en en tiempo de ejecución, con el compilador insertando las comprobaciones de tipo adecuadas. Este enfoque mantiene la compatibilidad con versiones anteriores del código Java anterior a los genéricos, a la vez que proporciona seguridad de tipos en tiempo de compilación. El compilador también genera métodos puente sintéticos para garantizar la correcta sobrescritura de métodos cuando los tipos genéricos están involucrados en jerarquías de herencia.

**P8: ¿Qué papel juega el classpath en la compilación de Java y cómo resuelve el compilador las dependencias?**\
R: El classpath es un parámetro crucial que le indica al compilador de Java dónde encontrar clases y paquetes durante la compilación. Se puede configurar usando la bandera `-cp`\` \<classpath>\` o `-classpath`\`\<classpath>\`, o a través de la `CLASSPATH`variable de entorno \`\<classpath>\`. El compilador busca en el classpath para resolver importaciones, relaciones de herencia y llamadas a métodos. Al compilar varios archivos, el compilador debe poder encontrar todas las clases referenciadas, ya sea en los archivos fuente que se están compilando o en el classpath. Esta resolución de dependencias ocurre durante la fase de compilación, y las dependencias faltantes dan como resultado errores de "no se puede encontrar el símbolo".

**P9: ¿Cómo gestiona el compilador de Java el procesamiento de anotaciones y qué implicaciones tiene para las herramientas de compilación?**\
R: El compilador de Java admite el procesamiento de anotaciones mediante la API de la Herramienta de Procesamiento de Anotaciones (APT), lo que permite que los procesadores personalizados generen código, validen anotaciones o realicen otras operaciones en tiempo de compilación. Esta función es ampliamente utilizada por frameworks como Lombok, MapStruct y Spring para la generación de código. El compilador puede ejecutar varias rondas de procesamiento de anotaciones, donde el código generado puede activar un procesamiento adicional. Las herramientas de compilación como Maven y Gradle se integran con este sistema mediante la `-processorpath`bandera y pueden configurar los procesadores de anotaciones como dependencias, lo que los hace esenciales para los flujos de trabajo de desarrollo de Java modernos.

</details>

<details open>

<summary><a href="https://www.digitalocean.com/community/tutorials/java-compiler#conclusion">Conclusión</a></summary>

Los descompiladores de Java son herramientas indispensables para cualquier desarrollador que trabaje con `.class`archivos compilados. Ya sea para depurar, realizar ingeniería inversa o aprender, comprender cómo funcionan la compilación y descompilación de Java te convertirá en un desarrollador más eficaz y con mayor conocimiento.

Para obtener más información, consulta estos tutoriales:

* [Cómo escribir tu primer programa en Java](https://www.digitalocean.com/community/tutorials/how-to-write-your-first-program-in-java)
* [Diferencias entre JDK, JRE y JVM](https://www.digitalocean.com/community/tutorials/difference-jdk-vs-jre-vs-jvm)
* [Compilar y ejecutar un programa Java desde otro programa Java.](https://www.digitalocean.com/community/tutorials/compile-run-java-program-another-java-program)

</details>

## Complemento de descompilación de Java para el IDE Eclipse



En el IDE de Eclipse, podemos usar el complemento [Enhanced Class Decompiler](https://ecd-plugin.github.io/ecd/) para descompilar archivos de clase Java sin necesidad de consultar directamente el código fuente.

Después de instalar y configurar el `Enhanced Class Decompiler`complemento, haga clic en la clase o los métodos, presione `F3`, y el complemento descompilará automáticamente la clase Java.

Tabla de contenido

* [1. ¿Qué es el plugin Enhanced Class Decompiler?](https://mkyong.com/java/java-decompiler-plugin-for-eclipse/#what-is-enhanced-class-decompiler-plugin)
* [2. Cómo instalar el complemento Enhanced Class Decompiler](https://mkyong.com/java/java-decompiler-plugin-for-eclipse/#how-to-install-enhanced-class-decompiler-plugin)
* [3. Cómo configurar las asociaciones de archivos](https://mkyong.com/java/java-decompiler-plugin-for-eclipse/#how-to-configure-file-associations)
* [4. Cómo configurar el descompilador de clases mejorado](https://mkyong.com/java/java-decompiler-plugin-for-eclipse/#how-to-configure-enhanced-class-decompiler)
* [5. Descompilar el código fuente de JDK](https://mkyong.com/java/java-decompiler-plugin-for-eclipse/#decompile-jdk-source-code)
* [6. Referencias](https://mkyong.com/java/java-decompiler-plugin-for-eclipse/#references)

_PS Probado con Enhanced Class Decompiler v3.2.2 y Eclipse IDE 2021-06._

### 1. ¿Qué es el plugin Enhanced Class Decompiler?<br>

El `Enhanced Class Decompiler`complemento puede elegir las siguientes cinco herramientas de descompilación de Java para descompilar la clase Java sin el código fuente.

* [JD](http://java-decompiler.github.io/)
* [Jad](http://www.kpdus.com/jad.html)
* [Flor de helecho](https://github.com/JetBrains/intellij-community/tree/master/plugins/java-decompiler/engine)
* [CFR](https://www.benf.org/other/cfr/)
* [Proción](https://github.com/mstrobel/procyon)

_PD: Elijo esto `FernFlower`porque IntelliJ IDEA también lo usa `FernFlower`para descompilar clases Java._

### 2. Cómo instalar el complemento Enhanced Class Decompiler<br>

A continuación se detallan los pasos para instalar el complemento Enhanced Class Decompiler en el IDE Eclipse.

1. Inicie el IDE de Eclipse.
2. Haz clic `Help -> Eclipse Marketplace...`.
3. Busque "Descompilador de Java" o "Descompilador de clases mejorado".
4. Seleccione "Descompilador de clases mejorado".
5. Haz clic en el `Install`botón.
6. Seleccione todas las funciones y clics `Confirm`.
7. Para obtener una advertencia de seguridad, haga clic aquí `Install anyway`.
8. Listo, reinicie el IDE de Eclipse.

<figure><img src="../.gitbook/assets/image (23).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (22).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (21).png" alt=""><figcaption></figcaption></figure>

### 3. Cómo configurar las asociaciones de archivos<br>

A continuación se detallan los pasos para configurar `class without source`el `Class Decompiler Viewer`.

1. En el IDE Eclipse.
2. Clics `Window -> Preferences -> General -> Editors -> File Associations`.
3. En `File types`la sección, seleccione `*.class without source`.
4. Desplácese hacia abajo hasta la `Associated editors`sección, seleccione `Class Decompiler Viewer`y haga clic en `Default`el botón. Si `Class Decompiler Viewer`falta, haga clic en `Add`el botón para agregar uno nuevo `Class Decompiler Viewer`. La clave es establecerlo como predeterminado.
5. Haz clic en `Apply and Close`el botón.

<figure><img src="../.gitbook/assets/image (20).png" alt=""><figcaption></figcaption></figure>

Listo, haga clic en la clase o método sin el código fuente, presione `F3`y el complemento descompilará automáticamente los archivos de clase.

### 4. Cómo configurar el descompilador de clases mejorado<br>

Haga clic `Window > Preferences > Java > Decompiler`para configurar qué descompilador de clases predeterminado descompilará la clase Java.

<figure><img src="../.gitbook/assets/image (19).png" alt=""><figcaption></figcaption></figure>

### 5. Descompilar el código fuente de JDK<br>

Este `Enhanced Class Decompiler`complemento parece incapaz de descompilar correctamente el código fuente del JDK; no estoy seguro de haberlo configurado correctamente; siempre aparece una página en blanco o un código fuente vacío cuando intento descompilar el código fuente del JDK (Java 11).

El código fuente del JDK está en la ruta `$JAVA_HOME\lib\src.zip`, adjúntelo y no necesitaremos el complemento para descompilarlo.

Terminal

```bash

# JDK source code
C:\opt\jdk-11.0.1\lib\src.zip  
```

{% file src="../.gitbook/assets/jd-eclipse-master.zip" %}

## JD-Eclipse



JD-Eclipse, un complemento descompilador de Java para la plataforma Eclipse.

<figure><img src="https://raw.githubusercontent.com/java-decompiler/jd-eclipse/master/src/website/img/jd-eclipse.png" alt=""><figcaption></figcaption></figure>

* Página principal del proyecto Java Decompiler: [http://java-decompiler.github.io](http://java-decompiler.github.io/)
* Código fuente de JD-Eclipse: [https://github.com/java-decompiler/jd-eclipse](https://github.com/java-decompiler/jd-eclipse)

### Descripción



JD-Eclipse es un complemento para la plataforma Eclipse. Permite visualizar todo el código fuente de Java durante el proceso de depuración, incluso si no se dispone de todos los archivos.

### ¿Cómo compilar JD-Eclipse?



```
> git clone https://github.com/java-decompiler/jd-eclipse.git
> cd jd-eclipse
> ./gradlew build
```

generar _"build/distributions/jd-eclipse-xyzzip"_

### ¿Cómo instalar JD-Eclipse?



1. Compilar o descargar _"jd-eclipse-xyzzip"_ ,
2. Lanzar _Eclipse_ ,
3. Haga clic en _"Ayuda > Instalar nuevo software..."_ ,
4. Arrastra y suelta _"jd-eclipse-xyzzip"_ en las ventanas de diálogo,
5. Compruebe _"Complemento descompilador de Java para Eclipse"_ ,
6. Haz clic en los botones "Siguiente" y "Finalizar".
7. Aparece una ventana de advertencia porque _"org.jd.ide.eclipse.plugin\_x.yzjar"_ no está firmado. Haga clic en el botón "Instalar de todos modos".

<figure><img src="https://raw.githubusercontent.com/java-decompiler/jd-eclipse/master/src/website/img/install_anyway.png" alt=""><figcaption></figcaption></figure>

### ¿Cómo comprobar las asociaciones de archivos?



Haz clic en _"Ventana > Preferencias > General > Editores > Asociaciones de archivos"._

* _"\*.class"_ : _El "Visor de archivos de clase" de Eclipse_ está seleccionado por defecto.
* _"\*.class sin código fuente"_ : _"Visor de archivos de clase JD"_ está seleccionado por defecto.

### ¿Cómo configurar JD-Eclipse?



Haz clic en _"Ventana > Preferencias > Java > Descompilador"_

### ¿Cómo desinstalar JD-Eclipse?



1. Haz clic en _"Ayuda > Acerca de Eclipse > Detalles de la instalación"_ ,
2. Seleccione _"Complemento JD-Eclipse"_ ,
3. Haz clic en _"Desinstalar..."_ .
