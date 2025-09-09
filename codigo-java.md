# Código Java

1- [TextCrypt](https://www.lawebdelprogramador.com/codigo/Java/4320-TextCrypt.html)

\
![textCrypt](https://www.lawebdelprogramador.com/usr/176000/176201/5a15e9b3e829c-textCrypt.jpg)\
\
Aplicación que permite encriptar y desencriptar textos.\
Los textos nunca están salvados en claro en el disco duroSe cambia el tipo de encriptación para que sea más robusta frente ataques por fuerza bruta.\
\
La forma de conseguirlo es haciendo computacionalmente mucho más costosa la comprobación de si una contraseña es la buena o no.\
Eso hace que el tiempo para romperla sea mucho mayor, o, si la contraseña es fuerte, se haga inviable un ataque por fuerza bruta.\
\
Se mantiene la compatibilidad hacia atrás, y se permite desencriptar archivos [ encriptados](https://www.lawebdelprogramador.com/codigo/Java/4320-TextCrypt.html) con versiones anteriores de la aplicación.\
Una vez se vuelva a proceder a su guardado, ya se encriptará con el nuevo método.\
\
Este es el enlace para descargar la aplicación y el código fuente:\
[https://www.frojasg1.com:8443/downloads\_web/downloadServletv3?file=textCrypt.v1.7\&origin=lawebdelprogramador\&language=Espanyol](https://www.frojasg1.com:8443/downloads_web/downloadServletv3?file=textCrypt.v1.7\&origin=lawebdelprogramador\&language=Espanyol)



2-[File Encoder Application](https://www.lawebdelprogramador.com/codigo/Java/3151-File-Encoder-Application.html)



Encriptador multiplataforma basado en encriptación simétrica XOR y reordenación pseudoaleatoria de bytes.\
La aplicación incluye una GUI para facilitar la tarea de encriptar y desencriptar.\
Incluye documentación detallada en Castellano, catalán e inglés.\
Artículos de programación

<figure><img src="https://www.lawebdelprogramador.com/usr/176000/176201/55468f14cb7d4-PantallaPrincipal_conPantallaDeFichero.jpg" alt=""><figcaption></figcaption></figure>



Se añade un tipo de encrptación que multplica por un número razonablemente grande el tiempo mínimo medio para comprobar una contraseña en un ataque por fuerza bruta.\
\
Ese tipo de encriptación se aplica por defecto a los archivos pequeños.\
\
Se puede descargar la aplicación junto al código fuente desde este enlace:\
[https://www.frojasg1.com:8443/downloads\_web/downloadServletv3?file=jfe.v1.6\&origin=lawebdelprogramador\&language=Espanyol](https://www.frojasg1.com:8443/downloads_web/downloadServletv3?file=jfe.v1.6\&origin=lawebdelprogramador\&language=Espanyol)



3- [Ejemplo para Windows - Java](https://www.lawebdelprogramador.com/codigo/Java/7571-Ejemplo-para-Windows-Java.html)

\
Ejemplo para Windows\
En este programa se expone cómo debería efectuarse las llamadas a funciones escritas en lenguaje 'C' que el S.O. posee para cualquier aplicación ejecutable.\
Para lograr todo esto en Java se recurre a la librería JNA.\
Las funciones que se utilizan y que son proporcionadas por el S.O. son:\
\* \_putenv()\
\* \_fflushall()\
\* system\
\* printf()\
\* puts()\
\
Estas otras funciones son proporcionadas por la librería de Embarcadero C++ Builder:\
\* clrscr()\
\* getch()\
\
Código fuente\
[https://github.com/torrentelinux/torrentarium/tree/master/base/fuente/Java/EjemploParaWindows](https://github.com/torrentelinux/torrentarium/tree/master/base/fuente/Java/EjemploParaWindows)\
\
Referencias:\
[https://en.wikipedia.org/wiki/Java\_Native\_Access](https://en.wikipedia.org/wiki/Java_Native_Access)\
[https://github.com/java-native-access/jna](https://github.com/java-native-access/jna)\


<figure><img src="https://www.lawebdelprogramador.com/usr/205000/205649/67f2eca76c6e8-EjemploParaWindows-01.png" alt=""><figcaption></figcaption></figure>



4- [Ejemplo para Linux - Java](https://www.lawebdelprogramador.com/codigo/Java/7570-Ejemplo-para-Linux-Java.html)

\
Ejemplo para Linux\
Este es un simple ejercicio en Java que muestra cómo hacer "llamadas al sistema" en S.O. Linux.\
Las funciones del lenguaje C que son invocadas desde el programa EjemploParaLinux.java son:\
\* putenv()\
\* system()\
Es importante conocer que se debe descargar la biblioteca JNA desde GitHub para que sea incorporada al proyecto que Usted debe crear en Apache NetBeans IDE (Linux).\
\
Código fuente:\
[https://github.com/torrentelinux/torrentarium/tree/master/base/fuente/Java/EjemploParaLinux](https://github.com/torrentelinux/torrentarium/tree/master/base/fuente/Java/EjemploParaLinux)\
\
Referencias:\
[https://en.wikipedia.org/wiki/Java\_Native\_Access](https://en.wikipedia.org/wiki/Java_Native_Access)\
[https://github.com/java-native-access/jna](https://github.com/java-native-access/jna)\


<figure><img src="https://www.lawebdelprogramador.com/usr/205000/205649/67f2ad713d90f-EjParaLinux-1.png" alt=""><figcaption></figcaption></figure>



5- [ChessPDFBrowser](https://www.lawebdelprogramador.com/codigo/Java/4319-ChessPDFBrowser.html)

\
\
Aplicación de ajedrez que permite trabajar con las partidas de los libros de ajedrez en PDF (siempre que los libros no sean escaneados y las partidas estén escritas en formato algebraico).\
\
La nueva versión (v1.26), también permite extraer partidas en notación algebraica de figuras\
\
También permite trabajar con listas de partidas leídas/escritas en formato PGN, y modificar los TAGs, NAGs y comentarios.\
\
Los árboles de variantes pueden se modificados realizando movimientos con las piezas situadas en un tablero.\
\
Permite trabajar con partidas incompletas (es decir, que empiecen en un movimiento posterior al inicial)\
\
\- Multi-idioma\
\- Multi-precisión\
\- Modo oscuro\
\- Conexión con motores tipo UCI\
\- OCR que convierte imágenes con una posición en un tablero, en una cadena estándar FEN\
\
Compatible con el JDK-17\
\
Vídeo de demostración de la nueva funcionalidad (v1.26)\
(entrenamiento del reconocedor de figuras para la extracción de partidas en notación algebraica de figuras)\
\
[https://frojasg1.com:8443/resource\_counter/resourceCounter?operation=countAndForward\&url=https%3A%2F%2Ffrojasg1.com%2Fdemos%2Faplicaciones%2FChessPdfBrowser%2Fv1.26.ES.02.extraer.partidas.notacion.algebraica.de.figuras.mp4%3Forigin%3Dlawebdelprogramador\&origin=web](https://frojasg1.com:8443/resource_counter/resourceCounter?operation=countAndForward\&url=https%3A%2F%2Ffrojasg1.com%2Fdemos%2Faplicaciones%2FChessPdfBrowser%2Fv1.26.ES.02.extraer.partidas.notacion.algebraica.de.figuras.mp4%3Forigin%3Dlawebdelprogramador\&origin=web)\


<figure><img src="https://www.lawebdelprogramador.com/usr/176000/176201/5a15e68e11207-chessPDF.jpg" alt=""><figcaption></figcaption></figure>

{% embed url="https://frojasg1.com:8443/downloads_web/downloadServletv3?file=ChessPDFbrowser.v1.30&origin=lawebdelprogramador&language=Espanyol" %}



6- [Llibrería para la extracción de texto y tablas de Pdfs](https://www.lawebdelprogramador.com/codigo/Java/7528-Llibreria-para-la-extraccion-de-texto-y-tablas-de-Pdfs.html)

\
\
La aplicación de línea de comandos es un ejemplo de uso de la librería Java.\
\
La librería se basa en la librería de pdfbox, y funciona buscando el layout de cada página seleccionada del pdf, y buscando estructuras de tabla.\
\
Tras la llamada a la librería (a la que hay que pasar el archivo de pdf, y el rango de páginas), el resultado es una List\<PdfTextElement>.\
\
PdfTextElement es una interfaz que tiene dos implementaciones.\
\* Un texto básico (fuera de las tablas)\
\* Y un PdfTextTabulaElement, para estructura de tablas.\
Esta implementación permite leer las dimensiones de la tabla y el texto de cada celda de la tabla.\
\
Es sólo una versión beta.\
Si no te funciona con alguna tabla de tus PDFs, puedes escribir un comentario, y lo vemos

<figure><img src="https://www.lawebdelprogramador.com/usr/176000/176201/66ce56249aac3-pdf-table-extractor-example.v1.0.png" alt=""><figcaption></figcaption></figure>

{% embed url="https://frojasg1.com:8443/downloads_web/downloadServletv3?file=pdf_table_extractor_lib.v1.0&origin=lawebdelprogramador&language=Espanyol" %}

7- [Conversaciones con la I.A.](https://www.lawebdelprogramador.com/codigo/Java/7526-Conversaciones-con-la-I.A.html)

Aplicación en Java para chatear con la I.A. generativa Llama3.\
\
\* El usuario puede hablar al micrófono (speechToText), editar el texto reconocido y enviárselo a la I.A.\
\
\* La I.A. responde y el servidor va devolviendo esa respuesta en tiempo real, y las frases convertidas a audio (textToSpeech), y la aplicación las emite por el altavoz.\
\
La aplicación está preparada para que únicamente haya un usuario ocupando los recursos del servidor, por lo que si el servidor está ocupado, en teoría no te dejará conectar.\
\
Hay un vídeo de demostración que muestra el funcionamiento:\
\
[https://frojasg1.com:8443/resource\_counter/resourceCounter?operation=countAndForward\&url=https%3A%2F%2Ffrojasg1.com%2Fdemos%2Faplicaciones%2Fchat%2F20240815.Demo.Chat.mp4%3Forigin%3Dlawebdelprogramador\&origin=web](https://frojasg1.com:8443/resource_counter/resourceCounter?operation=countAndForward\&url=https%3A%2F%2Ffrojasg1.com%2Fdemos%2Faplicaciones%2Fchat%2F20240815.Demo.Chat.mp4%3Forigin%3Dlawebdelprogramador\&origin=web)

\


<figure><img src=".gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

8- [Piano](https://www.lawebdelprogramador.com/codigo/Java/6452-Piano.html)

<figure><img src=".gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

{% file src=".gitbook/assets/piano.rar" %}

9- Vector

```
// Code
package arreglos1;

import java.text.DecimalFormat;
import java.util.Scanner;

public class Arreglos1 {

//realizar un program en java donde se ingrrese el nombre de un estudiante en un vector de tamaño ingresado por teclado
//Ingresar la nota de dicho estudainte mostrar el promedio del estudiente en este caso todos los datos deberan ser ingresado
// por teclado y no se podra ingresar numeros negativos, notas negativas ni tampoco, notas sobre 10
public static void main(String[] args) {
Scanner sc = new Scanner(System.in);
String estudiante;
double promedio,suma=0;
int tamaniovector;
DecimalFormat formato = new DecimalFormat("0.00");
System.out.println("Ingrese el nombre del estudiante:");
estudiante = sc.next();
System.out.println("Ingrese el tamaño del arreglo: ");
tamaniovector=sc.nextInt();
double vector[]= new double[tamaniovector];
System.out.println("Ingrese las calificaciones en un rango de (0 - 10)");
for (int i = 0; i<tamaniovector; i++){
System.out.println("Ingrese la calificacion del estudiante: " +estudiante+ " en la posicion: "+(i+1));
vector[i]=sc.nextDouble();
if(vector[i]>= 0 && vector[i]<=10 ){

}else{
System.out.println("La calificacion que ingreso esta fuera del rango establecido. Intentelo de nuevo");
i--;
}
}
System.out.println("Califiaciones del estudiante: "+estudiante);
for(int i = 0; i < tamaniovector;i++){
System.out.print(vector[i]);
System.out.print(" , ");
}
for(int i = 0; i<tamaniovector;i++){
suma += vector[i];
}
promedio = suma/vector.length;
System.out.println("");
System.out.println("Suma: "+suma);
System.out.println("Promedio: "+formato.format(promedio));
}
}
```

{% file src=".gitbook/assets/Arreglos1.rar" %}

```
// Some code
package arreglos1;

import java.text.DecimalFormat;
import java.util.Scanner;



public class Arreglos1 {

//realizar un program en java donde se ingrese el nombre de un estudiante en un vector de tamaño ingresado por teclado
//Ingresar la nota de dicho estudiante mostrar el promedio del estudiante en este caso todos los datos deberan ser ingresado
// por teclado y no se podra ingresar numeros negativos, notas negativas ni tampoco, notas sobre 10
public static void main(String[] args) {
Scanner sc = new Scanner(System.in);
String estudiante;
double promedio,suma=0;
int tamaniovector;
DecimalFormat formato = new DecimalFormat("0.00");
System.out.println("Ingrese el nombre del estudiante:");
estudiante = sc.next();
System.out.println("Ingrese el tamaño del arreglo: ");
tamaniovector=sc.nextInt();
double vector[]= new double[tamaniovector];
System.out.println("Ingrese las calificaciones en un rango de (0 - 10)");
for (int i = 0; i<tamaniovector; i++){
System.out.println("Ingrese la calificacion del estudiante: " +estudiante+ " en la posicion: "+(i+1));
vector[i]=sc.nextDouble();
if(vector[i]>= 0 && vector[i]<=10 ){

}else{
System.out.println("La calificacion que ingreso esta fuera del rango establecido. Intentelo de nuevo");
i--;
}
}
System.out.println("Califiaciones del estudiante: "+estudiante);
for(int i = 0; i < tamaniovector;i++){
System.out.print(vector[i]);
System.out.print(" , ");
}
for(int i = 0; i<tamaniovector;i++){
suma += vector[i];
}
promedio = suma/vector.length;


System.out.println("");
System.out.println("Suma: "+suma);
System.out.println("Promedio: "+formato.format(promedio));
}
}
```

10- [Graficador de Funciones](https://www.lawebdelprogramador.com/codigo/Java/7471-Graficador-de-Funciones.html)

Este programa Grafica en el plano XY cualquier funcion del tipo Y = F(X). Tambien grafica la derivada y la Integral y calcula longitudes de la curva de la función y areas.\


<figure><img src="https://www.lawebdelprogramador.com/usr/389000/389452/6599876b7c020-GraficaFunciones.JPG" alt=""><figcaption></figcaption></figure>



{% file src=".gitbook/assets/graficafunciones.rar" %}
