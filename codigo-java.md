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
