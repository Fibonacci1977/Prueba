# Cómo descompilar tu JAR en 2021: Guía de descompilación para JARs y APKs

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
