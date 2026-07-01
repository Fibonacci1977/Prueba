# Cómo ejecutar applets Java heredados de forma segura con Docker

Los applets de Java heredados aún son comunes en herramientas de proveedores como consolas IPMI, medios virtuales iDRAC y otras interfaces de administración, pero los navegadores modernos ya no los admiten. En lugar de conservar una máquina antigua solo para ejecutar Java obsoleto, puede usar Docker para crear un entorno aislado con todo preconfigurado.

En esta guía, le mostraremos cómo ejecutar applets Java antiguos (ya sean distribuidos como  archivos .jnlp  o  .jar  ) dentro de un contenedor Docker con soporte para [Ubuntu](https://www.bacloud.com/lt/tinklarastis/155/ubuntu-24.04-now-available-with-all-our-vps-and-dedicated-servers.html) , Java 8 e IcedTea-Web. De esta manera, podrá volver a utilizarlos sin sobrecargar ni comprometer su sistema principal.

### ¿Por qué Docker?

Ejecutar applets de Java antiguos directamente en tu máquina puede ser complicado y arriesgado. Las versiones obsoletas de Java suelen tener problemas de seguridad sin parchear, e instalarlas junto con tu configuración moderna puede causar conflictos. Docker resuelve esto de forma eficaz mediante:

* Aislamiento de Java heredado: el contenedor mantiene los entornos de ejecución inseguros separados de su host.
* Evita la saturación del sistema: no es necesario degradar el navegador ni instalar versiones antiguas de Java globalmente.
* Garantizar la reproducibilidad: una vez que se tiene un contenedor que funciona, cualquier persona que use Linux, macOS o Windows puede ejecutar la misma configuración y obtener los mismos resultados.

Con Docker, se obtiene un entorno limpio y desechable que se ejecuta solo cuando es necesario.

### Requisitos previos

Para seguir esta guía, necesitarás:

* Docker instalado: funciona en Linux, macOS (a través de Docker Desktop) o Windows (a través de Docker Desktop/WSL2).
* Conocimientos básicos de terminal: los comandos que se muestran en esta guía son para Linux, pero también funcionan en macOS y Windows con pequeñas diferencias en las rutas.
* Un applet de ejemplo para realizar pruebas, como un archivo .jnlp (Java Web Start) o un archivo .jar.
* Si no tienes uno, no te preocupes; en una sección posterior te mostraremos cómo crear un applet de ejemplo sencillo para realizar pruebas. &#x20;
* Nota sobre Apple Silicon: muchas imágenes antiguas solo son compatibles con x86. En Macs con M1/M2, agregue la opción --platform linux/amd64 al compilar o ejecutar el contenedor.

Este tutorial se ha escrito y probado con servidores VPS NVMe KVM de Bacloud. Implementa un VPS en minutos e instala Docker siguiendo este tutorial.

### Creación de la imagen Docker

Ahora que se cumplen los requisitos previos, el primer paso es crear una imagen de Docker con todas las herramientas necesarias para ejecutar applets de Java heredados.

#### Paso 1: Crear un directorio de trabajo

Elige una carpeta donde almacenarás el Dockerfile, el script de inicio y cualquier archivo de applet. Por ejemplo:

| <p>mkdir ~/legacy-java<br>cd ~/legacy-java</p> |
| ---------------------------------------------- |

(Puedes elegir el nombre de carpeta que quieras).

#### Paso 2: Crear el script de inicio

Dentro de tu  directorio legacy-java  , crea un archivo llamado  start.sh :

| nano start.sh |
| ------------- |

Pegue el siguiente contenido en el archivo:

| <p>#!/usr/bin/env bash<br>set -euo pipefail<br><br>export DISPLAY=: 0<br><br>echo  "[+] Iniciando Xvfb (pantalla virtual)"<br>Xvfb : 0  -screen  0 1280 x800x24 -nolisten tcp &#x26; sleep  1 echo  "[+] </p><p>Iniciando escritorio LXDE" dbus-launch --exit- with -session startlxde &#x26;</p><p> sleep  2 echo  "[+] Iniciando servidor x11vnc" x11vnc -display : 0  -</p><p>forever -nopw -shared -rfbport  5900  -quiet &#x26; echo  "[+] Iniciando noVNC</p><p> (proxy websockify)" websockify --web=/usr/share/novnc/  8080  localhost:</p><p> 5900  &#x26; echo  "[+] Contenedor listo. Manteniéndolo activo..." tail -f</p><p> /dev/null <br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br></p> |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

Guardar y salir.

Luego, hazlo ejecutable:

| chmod +x start.sh |
| ----------------- |

#### Paso 3: Crear el Dockerfile

Dentro de este directorio, crea un archivo llamado  Dockerfile . Puedes hacerlo con:

| Dockerfile nano |
| --------------- |

Pegue el siguiente contenido en el archivo y guárdelo:

| <p>FROM ubuntu: 24.04<br><br>ENV DEBIAN_FRONTEND=noninteractive<br># Corrige problemas de renderizado de fuentes en Swing/AWT<br>ENV _JAVA_OPTIONS= "-Dsun.java2d.xrender=false -</p><p>Dawt.useSystemAAFontSettings=on -Dswing.aatext=true" # Instala Java 8,</p><p> IcedTea-Web (javaws), LXDE y herramientas de escritorio remoto RUN apt-get </p><p>update &#x26;&#x26; \    apt-get install -y \        lxde \        xvfb \ </p><p>       x11vnc \        novnc \        websockify \        dbus-x11 \ </p><p>       openjdk -8 -jdk \        icedtea-netx \        libxext6 libxrender1</p><p> libxtst6 \   fonts-dejavu-core xfonts-base \        x11-apps \</p><p>        wget curl nano ca-certificates &#x26;&#x26; \    apt-get clean &#x26;&#x26; rm -rf</p><p> /var/lib/apt/lists/* # Crear directorio de applets RUN mkdir -p</p><p> /root/applets WORKDIR /root/applets # Copiar script de inicio COPY start.sh /usr/local/bin/start.sh RUN chmod +x /usr/local/bin/start.sh # Exponer VNC</p><p> y noVNC EXPOSE  5900 8080 CMD [ "/usr/local/bin/start.sh" ]<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br> <br><br></p> |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

Esta imagen instala:

* Java 8 JDK (para compilar y ejecutar código Java, incluyendo applets)
* IcedTea-Web (javaws) (para ejecutar aplicaciones Java Web Start .jnlp)
* Un entorno de escritorio LXDE ligero
* Xvfb (servidor X virtual)
* x11vnc + noVNC + websockify (acceso remoto a la interfaz gráfica de usuario desde el navegador o el cliente VNC)
* Bibliotecas de fuentes y X11 (que garantizan la correcta representación del texto Java y las interfaces gráficas de usuario).
* Herramientas básicas (wget, curl, nano, certificados CA)

#### Paso 4: Construir la imagen

Desde el mismo directorio que el Dockerfile, ejecute:

| docker build -t legacy-java . |
| ----------------------------- |

En Apple Silicon (M1/M2), agregue  --platform linux/amd64  para forzar una compilación x86:

| docker build --platform linux/amd64 -t legacy-java . |
| ---------------------------------------------------- |

#### Paso 5: Verificar la imagen

Compruebe que la imagen se haya creado correctamente:

| imágenes de Docker |
| ------------------ |

Debería aparecer legacy-java en la salida.

### Ejecutando el contenedor

Una vez creada la imagen, el siguiente paso es iniciar un contenedor y conectarse a él. Esto le dará acceso al entorno de escritorio LXDE que se ejecuta dentro de Docker.

#### Paso 1: Ejecutar el contenedor

Asegúrate de seguir en la terminal del mismo sistema donde creaste la imagen de Docker. Luego ejecuta:

| <p>docker run -it \<br> -p  5900 : 5900  -p  8080 : 8080  \<br> -v ~/applets:/root/applets \<br> --name legacy-java \<br> legacy-java</p> |
| ----------------------------------------------------------------------------------------------------------------------------------------- |

* -Mantiene  el contenedor conectado a tu terminal para que puedas ver los registros.
* -p 5900:5900  expone el servidor VNC.
* -p 8080:8080  expone la interfaz web de noVNC.
* -v \~/applets:/root/applets  monta el directorio \~/applets de su host   en el contenedor para que  los archivos .jnlp  o  .jar  persistan entre ejecuciones.
* \--name legacy-java  le da al contenedor un nombre fácil de usar.

#### Paso 2: Conéctese al ordenador

Puedes conectarte de dos maneras:

* **Utilizar un navegador (recomendado):**

Si está ejecutando el contenedor en su propio ordenador, abra:

|  http://localhost: 8080/vnc.html |
| -------------------------------- |

Si está ejecutando el contenedor en un VPS remoto, reemplace localhost con la IP del servidor. Por ejemplo:

|  http:// 203.0.113.10 : 8080/vnc.html |
| ------------------------------------- |

* **Utilizando un cliente VNC:**
* En tu máquina local, conéctate a  localhost:5900  si el contenedor se está ejecutando localmente.
* En un VPS, conéctese a \<server-ip>:5900  (por ejemplo,  203.0.113.10:5900 ) utilizando cualquier cliente VNC (Remmina en Linux, RealVNC, TightVNC, etc.).&#x20;

#### Paso 3: Verificar que funciona.

Al conectarte por primera vez, es posible que veas brevemente una pantalla en negro. Esto es normal mientras se inicia el entorno de escritorio LXDE.

En algunos casos, puede aparecer un pequeño mensaje como «no hay sesión para el PID…». Esto no es un error grave; se trata de una advertencia de inicio inofensiva relacionada con la inicialización de LXDE y puede ignorarse sin problema. Simplemente haga clic en «Aceptar».

También verás aparecer un panel lateral:

![](https://www.bacloud.com/images/blog-posts/legacy-java/01.webp)

Haz clic en el icono de pantalla completa para cambiar a pantalla completa.

![](https://www.bacloud.com/images/blog-posts/legacy-java/02.webp)

Esto mostrará la barra de tareas de LXDE en la parte inferior, junto con las aplicaciones predeterminadas como el administrador de archivos y el navegador.

![](https://www.bacloud.com/images/blog-posts/legacy-java/03.webp)

Una vez que el entorno de escritorio sea visible, la configuración estará completa. Podrá abrir una terminal dentro del contenedor y usar javaws para ejecutar sus  applets .jnlp heredados.

#### Creación de un applet de ejemplo (opcional)

Si ya tienes tu propio  archivo .jar  o .jnlp  , puedes omitir esta sección. De lo contrario, vamos a crear un miniaplicativo de prueba sencillo para que puedas confirmar que tu configuración funciona correctamente.&#x20;

#### Paso 1: Crea una carpeta para los applets.

En tu servidor VPS (aún no dentro de Docker), crea la carpeta donde se alojarán tus applets. Esta carpeta se monta en el contenedor para que los archivos permanezcan.

| <p>mkdir -p ~/applets<br>cd ~/applets</p> |
| ----------------------------------------- |

#### Paso 2: Escribe un applet sencillo

Crearemos un pequeño applet de Java que mostrará el mensaje “¡Hola BaCloud desde el Applet de Java!” dentro de una ventana.

| nano HelloApplet.java |
| --------------------- |

Pegue el siguiente código:

| <p>import  java.applet.Applet;<br>import  java.awt.Graphics;<br><br>public  class HelloApplet extends Applet  { public void paint (Graphics g) { g . drawString ( "Hello BaCloud from Java Applet!" ,  20 ,  20 );    } }   <br>     <br>       <br><br></p> |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |

Guardar y salir.

#### Paso 3: Instalar el compilador de Java en el servidor VPS.

Para compilar el  archivo .java  , necesitas el Kit de Desarrollo de Java (JDK). Instálalo:

Primero, actualice la lista de paquetes:

| sudo apt update |
| --------------- |

A continuación, instale el Kit de Desarrollo de Java (JDK):

| sudo apt install openjdk -8 -jdk -y |
| ----------------------------------- |

#### Paso 4: Compilar el applet y crear un cargador HTML.

Compila tu   archivo .java :

| javac HelloApplet.java |
| ---------------------- |

A continuación, crea un archivo HTML sencillo que cargue el applet:

| nano HelloApplet.html |
| --------------------- |

Pegar en:

| <p>&#x3C;html><br> &#x3C;body><br>   &#x3C;applet code= "HelloApplet.class"  width= "300"  height= "100" ><br>   &#x3C;/applet><br> &#x3C;/body><br>&#x3C;/html></p> |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

Guardar y salir.

#### Paso 5: Verificar los archivos compilados

Después de compilar y crear el archivo HTML, lista el contenido de tu  directorio \~/applets :

| ls \~/applets |
| ------------- |

Ahora deberías ver al menos estos archivos:

* HelloApplet.java – el código fuente&#x20;
* HelloApplet.class – el código de bytes compilado&#x20;
* HelloApplet.html  – el contenedor HTML de prueba
* &#x20;
*   #### ¡Suscríbete a nuestro boletín y disfruta de un 10% de descuento recurrente! <a href="#ispasted" id="ispasted"></a>

    Inscribirse

#### Cargando un applet de Java

&#x20;

Ahora vamos a ejecutar el applet dentro del contenedor.

#### Paso 1: Detenga cualquier contenedor antiguo que utilice los mismos puertos.

Si ya tiene un contenedor ejecutándose en los puertos  5900  o  8080 , primero deberá detenerlo.

* Si su terminal sigue "bloqueada" mostrando los registros de contenedores de una ejecución anterior, simplemente presione  Ctrl + C  para detenerla.
* O bien, desde una nueva sesión de terminal, liste los contenedores activos:

| Docker PS |
| --------- |

Esto mostrará una lista de los contenedores activos, incluyendo sus ID y nombres.

Luego, detenga el contenedor ejecutando:

| docker stop \<id\_contenedor> |
| ----------------------------- |

Reemplace \<container\_id> con el ID que se muestra en la lista. &#x20;

A continuación, elimine cualquier contenedor antiguo llamado  legacy-java  para evitar conflictos:

| docker rm legacy-java  2 >/dev/null \|\| true |
| --------------------------------------------- |

(La parte 2>/dev/null || true  simplemente oculta el error si el contenedor aún no existe).&#x20;

#### Paso 2: Comience a llenar el recipiente desde cero.

Ahora ejecuta el contenedor de nuevo, montando tu  carpeta \~/applets  :

| <p>docker run -it \<br> -p  5900 : 5900  -p  8080 : 8080  \<br> -v ~/applets:/root/applets \<br> --name legacy-java \<br> legacy-java</p> |
| ----------------------------------------------------------------------------------------------------------------------------------------- |

#### Paso 3: Abra una terminal en el escritorio VNC.

Una vez conectado al escritorio (a través de VNC o  http://\<dirección IP del servidor>:8080/vnc.html ), abra la terminal LXDE.

![](https://www.bacloud.com/images/blog-posts/legacy-java/04.webp)

#### Paso 4: Utilice appletviewer para cargar el applet.

Dentro de la terminal LXDE, ejecute:

| <p>export DISPLAY=: 0<br>appletviewer /root/applets/HelloApplet.html</p> |
| ------------------------------------------------------------------------ |

Si seguiste nuestro ejemplo, ejecuta el comando exactamente como se muestra con  HelloApplet.html .

Si utilizas tu propio applet, reemplaza  HelloApplet.html  con el nombre de tu archivo HTML contenedor.

* Para  los archivos .class  , el HTML debe apuntar al  archivo .class .
* Para  los archivos .jar  , el HTML debe hacer referencia al archivo .jar .&#x20;

Aparecerá una ventana emergente titulada “Visor de applets: …”.

* Si usaste tus propios archivos, deberías ver lo que tu applet esté programado para mostrar.
* Si usaste el applet de ejemplo, dirá: ¡Hola BaCloud desde Java Applet! Tal como en la imagen a continuación:

| ¡Hola BaCloud  desde  Java Applet! |
| ---------------------------------- |

![](https://www.bacloud.com/images/blog-posts/legacy-java/03.webp)

Si ve una pantalla con este texto, como en la imagen de arriba, ¡su entorno Java Web Start/Applet está funcionando correctamente!

&#x20;

### Consideraciones de seguridad

Los applets de Java son una tecnología obsoleta y deben tratarse como inseguros por defecto. Para minimizar el riesgo:

* Nunca ejecutes applets directamente en tu máquina anfitriona. Utiliza siempre Docker o una máquina virtual para aislar la ejecución.
* Restringir el acceso a la red.
* Utilice  --network none para bloquear todas las conexiones salientes.&#x20;
* Si se requiere acceso a la intranet, configure explícitamente --network host .&#x20;
* Elimine los privilegios innecesarios.  Ejecute el contenedor con:

|  --cap-drop=ALL |
| --------------- |

Esto reduce la superficie de ataque al eliminar las capacidades de Linux.

* Limita el acceso al sistema de archivos.   Monta solo las carpetas que necesites (por ejemplo, \~/applets ) y hazlas de solo lectura siempre que sea posible:&#x20;

|  -v \~/applets:/root/applets:ro |
| ------------------------------- |

* Al combinar estas opciones, te aseguras de que el applet se ejecute en un entorno aislado y estrictamente controlado, protegiendo tanto tu VPS como tu máquina local.

### Solución de problemas

Si encuentras algún problema, aquí tienes algunas soluciones comunes:

* “No se puede abrir la pantalla” → Verifique que el servicio VNC o noVNC esté en ejecución y sea accesible en los puertos correctos.
* El archivo JNLP no se ejecuta → Algunas aplicaciones antiguas requieren versiones anteriores de Java (Java 6/7). Intente ajustar su instalación de Java.
* Errores de permiso denegado → Compruebe los puntos de montaje del volumen y asegúrese de que el usuario del contenedor tenga acceso de lectura/escritura.
* El applet requiere acceso a la intranet → Ejecute el contenedor con --network host o configure un proxy.

Conclusión

Al contenerizar un escritorio Linux ligero con Java 8, LXDE y herramientas de acceso remoto, hemos creado un entorno aislado donde las aplicaciones Java antiguas y las aplicaciones Web Start pueden seguir ejecutándose de forma segura. En lugar de lidiar con navegadores obsoletos o complementos inseguros en su sistema anfitrión, ahora todo está encapsulado dentro de Docker.

Verificamos esta configuración compilando y ejecutando un sencillo applet llamado "Hello BaCloud", pero el mismo método se aplica a tus propios archivos .class, .jar o .jnlp. Ya sea que te conectes mediante VNC o directamente en tu navegador a través de noVNC, ahora tienes una forma reproducible de lanzar y probar applets en infraestructuras modernas.

&#x20;

Si también planeas usar Docker, consulta nuestra guía sobre  [cómo instalar Docker en Ubuntu 24.04](https://www.google.com/url?q=https://www.bacloud.com/en/blog/157/how-to-install-and-set-up-docker-on-ubuntu-24.04.html\&sa=D\&source=editors\&ust=1757591389756340\&usg=AOvVaw0b0a7043M0jPKztQkvHXFO)  para obtener instrucciones paso a paso.
