# Jar a Exe con JRE incluido

{% embed url="https://youtu.be/aiLrMyA9KPQ" %}

## Convierta archivos JAR a EXE para facilitar su implementación en sistemas Windows.

Escrito por [Alex Marin ](https://www.advancedinstaller.com/authors/alex-marin.html) ·  2 de mayo de 2024  ·  6 min de lectura

Las aplicaciones Java se compilan en archivos JAR, que requieren el Entorno de ejecución de Java (JRE) para ejecutarse. Sin embargo, los archivos JAR no se pueden ejecutar como archivos independientes.

Si bien esto es sencillo para los desarrolladores y entusiastas de Java, puede suponer un desafío para los usuarios finales que no están familiarizados con Java.

Convertir tu archivo JAR en un archivo ejecutable (EXE) puede hacer que tu aplicación sea más accesible y fácil de usar para el público de Windows.

Esta guía le mostrará cómo convertir un archivo JAR en un archivo EXE , utilizando diversos métodos y herramientas.

#### ¿Por qué convertir JAR a EXE?

La conversión de archivos JAR a EXE mejora la experiencia del usuario al simplificar el proceso de inicio de la aplicación en sistemas Windows.

Elimina la necesidad de que los usuarios ejecuten comandos Java manualmente o tengan conocimientos detallados de Java. Además, un archivo EXE se puede configurar para incluir o encontrar automáticamente el entorno Java necesario, lo que agiliza la implementación de la aplicación.

#### Requisitos previos: ¿Qué necesitas antes de comenzar la conversión?

Antes de comenzar, asegúrese de tener lo siguiente:

* El archivo JAR que desea convertir.
* Necesitará tener instalado en su sistema un JDK (Java Development Kit) para probar el archivo JAR.
* Acceso a una de las herramientas de conversión que se mencionan a continuación.

#### Conversión de archivos JAR a EXE con Launch4j

[Launch4j](http://launch4j.sourceforge.net/) es una popular herramienta multiplataforma que convierte archivos JAR en archivos ejecutables de Windows.

Permite especificar la versión mínima de Java necesaria para ejecutar la aplicación. También se puede configurar para usar un JRE incluido o buscar una instalación específica de Java en el sistema.

Si no se encuentra la versión de Java requerida, Launch4j puede configurarse para que dirija al usuario a descargarla. Por lo tanto, la necesidad de instalar Java depende de cómo se configure el proceso de compilación del archivo EXE.

* JRE incluido : No se requiere instalación externa de Java.
* JRE específico/del sistema : Sí, es necesario instalar Java.

Aquí están los pasos para convertir tu archivo JAR a EXE con Launch4j :

1\. Descarga e instala Launch4j : Visita el sitio web de Launch4j y descarga el instalador para Windows. Sigue las instrucciones de instalación.

2\. Configure su proyecto : Abra Launch4j e ingrese los detalles básicos de su aplicación, como el archivo de salida (el nombre de archivo EXE deseado), el JAR de entrada y el archivo de icono si lo tiene.

<figure><img src="https://cdn.advancedinstaller.com/img/convert-jar-files-to-exe/launch4j-tool-gui.png" alt="Interfaz gráfica de usuario de la herramienta Launch4j" height="697" width="886"><figcaption></figcaption></figure>

3\. Configurar opciones de JVM : En la pestaña "JRE", especifique la versión mínima y máxima de Java requerida para su aplicación.

4\. Generar el ejecutable : Haga clic en el botón "Ejecutar". Este proceso generará su archivo EXE en la ubicación especificada.

#### Conversión de archivos JAR a EXE con JSmooth

[JSmooth](http://jsmooth.sourceforge.net/) es otra herramienta que puede crear ejecutables de Windows a partir de archivos JAR. Sin embargo, JSmooth no se ha actualizado desde hace tiempo y es posible que solo se pueda usar para aplicaciones antiguas y en versiones antiguas del sistema operativo.

JSmooth funciona de forma similar a Launch4j: comprueba si Java está instalado en el sistema del usuario y lo utiliza para ejecutar el archivo JAR. También ofrece la opción de descargar e instalar Java automáticamente si no se encuentra, o bien permite incluir un JRE con la aplicación. Por lo tanto, la necesidad de tener Java instalado depende de la configuración del sistema.

* JRE incluido : No es necesario instalar Java externamente.
* Descarga automática de Java o JRE del sistema : Es posible que sea necesario instalar Java si aún no está disponible en el sistema.

Aquí están los pasos para convertir su archivo JAR a EXE con JSmooth:

1. Descarga e instala JSmooth : Ve al sitio web de JSmooth, descarga el instalador y sigue el proceso de configuración.
2. Crea un nuevo proyecto : Inicia JSmooth y crea un nuevo proyecto. Especifica el nombre del proyecto y la ubicación del archivo JAR.
3. Personalizar opciones de ejecución : Puede personalizar varios ajustes, como el icono del ejecutable, la versión de la JVM y el tipo de ventana.
4. Compila el ejecutable : Una vez que hayas configurado tus ajustes, compila el proyecto para crear tu archivo EXE.

#### Conversión de archivos JAR a EXE con WinRun4J

[WinRun4J](http://winrun4j.sourceforge.net/) es una opción más técnica, que ofrece una amplia personalización para la creación y gestión de servicios de Windows.

WinRun4J es más configurable y puede configurarse para incluir un JRE con la aplicación o para detectar y utilizar una instalación de Java existente. Permite un control muy preciso del entorno Java que utiliza la aplicación.

Al igual que con otras herramientas, la necesidad de instalar Java depende de la configuración de su sistema:

* JRE incluido : No se requiere instalación externa de Java.
* Requisitos del sistema JRE : Es necesario instalar Java.

A continuación se detallan los pasos para convertir su archivo jar a EXE con WinRun4J :

1. Descarga WinRun4J : Visita el sitio web de WinRun4J, descarga el archivo binario y extráelo.
2. Cree un archivo de configuración : WinRun4J requiere un archivo de configuración (INI) donde se especifican los detalles sobre el archivo JAR, los argumentos de la máquina virtual y otras opciones.
3. Compile el archivo EXE : Utilice la herramienta WinRun4J para compilar su archivo INI y JAR en un archivo EXE. Este proceso puede requerir operaciones de línea de comandos, detalladas en la documentación de WinRun4J.

<figure><img src="https://cdn.advancedinstaller.com/img/convert-jar-files-to-exe/winrun4j-tool.png" alt="Herramienta WinRun4J" height="276" width="295"><figcaption></figcaption></figure>

#### ¿Necesitas tener Java instalado para ejecutar el archivo EXE?

La necesidad de instalar Java para ejecutar el archivo EXE resultante depende de cómo se configure el ejecutable durante el proceso de conversión:

JRE incluido : Si el ejecutable está configurado para incluir (empaquetar) un JRE, no es necesario instalar Java adicionalmente en el sistema del usuario. Este método es preferible por su facilidad de uso y compatibilidad, pero resulta en un archivo ejecutable de mayor tamaño.

JRE del sistema o específico : Si el ejecutable está configurado para usar la instalación de Java del sistema o una versión específica, entonces Java debe estar instalado en el equipo del usuario. Algunas herramientas pueden configurarse para solicitar al usuario que descargue e instale Java si no se encuentra, lo que facilita el proceso.

#### Buenas prácticas para convertir JAR a EXE

* Pruebas en múltiples sistemas : Asegúrese de que su archivo EXE se ejecute correctamente en diferentes versiones y configuraciones de Windows mediante pruebas exhaustivas.
* Considera la experiencia del usuario : elige un enfoque de conversión que minimice el esfuerzo del usuario, idealmente incluyendo un JRE con tu aplicación.
* Tenga en cuenta la seguridad : actualice periódicamente el JRE incluido para proteger a los usuarios de posibles vulnerabilidades de seguridad.
* Cumpla con las licencias : Si incluye una JRE, asegúrese de cumplir con los requisitos de la licencia de Java.

#### Implementación de su aplicación EXE

Con tu archivo EXE listo, ya puedes distribuir tu aplicación a los usuarios. Considera crear un paquete de instalación para una apariencia profesional y una instalación más sencilla. Si no quieres convertir tu archivo JAR a EXE, puedes usar Advanced Installer para simplificar la implementación de tu producto Java.

Advanced Installer se erige como una herramienta esencial para los desarrolladores, especialmente cuando se trata de implementar productos Java.

Reconociendo las necesidades específicas de las aplicaciones Java, Advanced Installer ofrece un proyecto predefinido diseñado exclusivamente para productos Java . Su interfaz intuitiva está pensada para facilitar su uso, permitiendo a los desarrolladores empaquetar rápidamente aplicaciones Java sin tener que lidiar con complejidades.

[¡Comienza hoy tu prueba gratuita de 30 días!](https://www.advancedinstaller.com/trial.html)

[Este artículo](https://www.advancedinstaller.com/user-guide/tutorial-java.html) proporciona un ejemplo detallado de lo sencilla y eficiente que es para empaquetar productos Java con Advanced Installer.

Si prefiere utilizar un lanzador EXE diferente al incluido en Advanced Installer, aún puede utilizar la solución gratuita que ofrece Advanced Installer.

Crea un paquete MSI fácilmente con la edición gratuita de Advanced Installer. Usa su interfaz intuitiva y añade tus archivos EXE y JAR a la página de Archivos y Carpetas. Para más información, consulta [nuestro artículo aquí](https://www.advancedinstaller.com/user-guide/create-msi-package-video-tutorial.html) .

#### Conclusión

Convertir un archivo JAR a EXE facilita el acceso de los usuarios de Windows a tu aplicación Java, mejorando su distribución y usabilidad. Cada una de las herramientas mencionadas ofrece características y niveles de personalización únicos, así que elige la que mejor se adapte a tus necesidades. Esta guía te ayudará a optimizar la distribución de tu aplicación y a brindar una experiencia de usuario superior.

## Crear Paquete Instalador utilizando la herramienta: Advanced Installer

## ¿CÓMO CREAR UN INSTALADOR DE TU APLICACIÓN JAVA? | FÁCIL Y SENCILLO

{% embed url="https://youtu.be/eeL8ptCq-yU" %}

## Generar o crear Instalador SETUP para programas jar - Java InnoSetup

{% embed url="https://youtu.be/_N4MV7w75Uk" %}

## Crear Setup con Advanced Installer 9.1

{% embed url="https://youtu.be/ESOwlTMV0As" %}

[Crear Paquete Instalador utilizando la herramienta: Advanced Installer](https://www.youtube.com/watch?v=YpjdA3g-Lpg)

{% embed url="https://youtu.be/YpjdA3g-Lpg" %}

Para crear un paquete instalador de C++ con Advanced Installer, primero debes instalar la extensión de [Advanced Installer para Visual Studio](https://www.advancedinstaller.com/create-msi-installer-for-cpp-application-visual-studio.html) en Visual Studio. Luego, abre tu proyecto de C++, crea un nuevo "Setup Project" o usa la extensión directamente desde el IDE, y sigue los pasos de la interfaz de Advanced Installer para añadir los archivos de tu aplicación, definir las opciones de instalación, configurar los componentes y generar el paquete de instalación final (como un archivo .exe o .msi). This video demonstrates how to create an installer package using Advanced Installer:![Miniatura de vídeo relacionado](<.gitbook/assets/Miniatura de vídeo relacionado (1)>)

{% embed url="https://youtu.be/YpjdA3g-Lpg" %}

1. **Instalar la extensión de Advanced Installer**:
   * Abre Visual Studio.
   * Ve a `Extensions` > `Manage Extensions`.
   * En la sección `Online`, busca "Advanced Installer for Visual Studio".
   * Descarga e instala la extensión. Reinicia Visual Studio para completar la instalación.
2. **Crear el proyecto instalador**:
   * Abre tu proyecto de C++ en Visual Studio.
   * Puedes crear un nuevo proyecto de instalación de C++ (por ejemplo, usando el método "Setup Project" de Visual Studio, aunque Advanced Installer suele integrarse directamente).
   * O, de manera más directa, utiliza la integración de Advanced Installer desde el IDE.
3. **Configurar el instalador**:
   * La extensión de Advanced Installer te guiará a través de una interfaz gráfica para configurar el instalador.
   * **Añadir archivos**: Agrega los ejecutables de tu aplicación, bibliotecas y otros archivos necesarios.
   * **Definir componentes**: Organiza los archivos en componentes para una mejor gestión.
   * **Configurar la instalación**: Define el destino de la instalación, las entradas del registro, los accesos directos y otras opciones personalizadas para tu aplicación.
   * **Crear la interfaz**: Personaliza la interfaz de usuario del instalador.
4. **Generar el paquete de instalación**:
   * Una vez configurado, puedes compilar el proyecto para generar el paquete de instalación final.
   * Este paquete puede ser un archivo ejecutable (.exe) o un paquete MSI (Microsoft Installer).&#x20;

You can watch this video to learn how to create an installer in Visual Studio 2017:<br>

<figure><img src=".gitbook/assets/Miniatura de vídeo relacionado (1) (1)" alt=""><figcaption></figcaption></figure>

{% embed url="https://youtu.be/bDlk8uE5YKM" %}

## Herramientas para crear paquetes instalados Windows

No te pierdas la siguiente recopilación con las mejores [ herramientas](https://www.solvetic.com/page/recopilaciones/s/recopilacion/herramientas-para-crear-paquetes-instalados-windows) para crear paquetes instalados [ Windows](https://www.solvetic.com/page/recopilaciones/s/recopilacion/herramientas-para-crear-paquetes-instalados-windows). Mira, compara y selecciona el programa que mejor se adapte a tus necesidades.

<br>

El mundo del software es bastante amplio y una de sus principales y más interesantes opciones radica en la opción de crear paquetes instaladores para sistemas operativos Windows ya que gracias a ello tenemos la posibilidad de [crear aplicaciones](https://www.solvetic.com/tutoriales/article/4175-crear-programa-portable-windows-10-8-7-sin-instalacion/) propias basadas en requisitos propios.

&#x20;

Cada programa puede estar basado en un conjunto de diferente de necesidades, como scripts, DLL, configuraciones de seguridad, etc., por lo que será necesario contar con una [ herramienta](https://www.solvetic.com/page/recopilaciones/s/recopilacion/herramientas-para-crear-paquetes-instalados-windows) que tenga la capacidad de manejar un conjunto complejo de requisitos. Por ello hoy veremos algunas herramientas útiles para llevar a cabo esta tarea de la mejor forma en Windows.

&#x20;

Nullsoft Scriptable Install System (NSIS)<br>

<figure><img src="https://www.solvetic.com/uploads/monthly_11_2017/ccs-7463-0-87291500-1511183535.png" alt=""><figcaption></figcaption></figure>

&#x20;

NSIS (Nullsoft Scriptable Install System) es un sistema de código abierto profesional para crear instaladores de sistemas operativos Windows. Está diseñado para ser lo más pequeño y flexible posible y, por lo tanto, es muy adecuado para la distribución en Internet.

&#x20;

Al ser la primera experiencia de un usuario con este producto, cuenta con un instalador estable y confiable el cual es un componente importante de este software. Con NSIS será posible crear instaladores que sean capaces de hacer todo lo necesario para configurar su software.

&#x20;

NSIS se basa en secuencias de comandos y nos permite crear la lógica para manejar incluso las tareas de instalación más complejas. Muchos complementos y scripts ya están disponibles: será posible crear instaladores web, comunicarse con Windows y otros componentes de software, instalar o actualizar componentes compartidos y más.

&#x20;

Dentro de las diversas características de esta herramienta tenemos

* NSIS puede crear instaladores de Windows que sean capaces de instalar, desinstalar, establecer configuraciones de sistema, extraer archivos, etc.
* NSIS se basa en archivos de script, por lo cual permite crear instaladores simples y avanzados.
* NSIS está creado para ser pequeño, rápido y eficiente. Mientras que otros instaladores a menudo agregan cientos de kilobytes o varios megabytes a los datos de su instalador, un instalador NSIS completo tiene una sobrecarga de solo 34 KB.
* Podemos crear un único instalador que sea compatible con Windows XP, Windows Server 2003, Windows Vista, Windows Server 2008, Windows 7, Windows Server 2008R2, Windows 8, Windows. Servidor 2012, Windows 8.1, Windows 10 y Windows Server 2012R2 o 2016.
* Podremos elegir entre tres métodos de compresión integrados diferentes (ZLib, BZip2, LZMA). La nueva compresión LZMA ofrece mejores resultados que cualquier otro método de compresión común. No será necesario usar grandes módulos de archivo autoextraíbles u otras aplicaciones. El soporte de compresión está incluido en la sobrecarga de 34 KB.
* A diferencia de otros sistemas que solo pueden generar instaladores basados en una lista de archivos y claves de registro, NSIS tiene un potente lenguaje de scripting. Este lenguaje de script está diseñado para instaladores y tiene comandos que nos ayudan a realizar muchas tareas de instalación.
* Un instalador puede soportar múltiples idiomas de interfaz. Ya se incluyen más de 40 traducciones, pero también permite crear nuestros propios archivos de idioma. Los idiomas RTL (de derecha a izquierda) como el árabe y el hebreo son totalmente compatibles.
* El lenguaje de script proporciona comandos que pueden ser usados en el sistema de destino, desde funciones simples como creación de carpeta y edición de registro hasta modificación de archivo de texto / binario, modificación de variables de entorno y reinicios del sistema. Usando los complementos provistos, incluso se puede usar la API de Windows.
* Podemos crear páginas de asistente personalizadas para obtener la entrada del usuario o integrar opciones de configuración. NSIS incluye una interfaz de asistente clásica y moderna, pero incluso es posible crear nuestra propia interfaz personalizada.
* NSIS se puede ampliar con complementos que pueden comunicarse con el instalador. Se pueden escribir en C, C ++, Delphi u otro idioma y se pueden usar para realizar tareas de instalación o ampliar la interfaz del instalador.
* La distribución de NSIS incluye un conjunto de complementos que permiten descargar archivos desde Internet, realizar conexiones a Internet, aplicar parches a archivos existentes y más.
* El compilador NSIS presenta un potente preprocesador. Esto nos permite integrar fácilmente múltiples proyectos en un solo instalador o generar automáticamente compilaciones de instalador.
* El formato de secuencia de comandos de NSIS y el formato utilizado para los cuadros de diálogo de la interfaz son fáciles, documentados y legibles humanamente, por lo que podemos editar los archivos con algún editor favorito.
* El compilador NSIS se puede compilar para plataformas POSIX como Linux y \* BSD. El instalador generado solo se ejecutará en [ Windows](https://www.solvetic.com/page/recopilaciones/s/recopilacion/herramientas-para-crear-paquetes-instalados-windows), pero de esta forma se pueden generar sin Windows o WINE.

&#x20;

Al momento de su ejecución este será el entorno ofrecido:

&#x20;

<figure><img src="https://www.solvetic.com/uploads/monthly_11_2017/ccs-7463-0-94930900-1511183563.png" alt=""><figcaption></figcaption></figure>

&#x20;

Allí podemos seleccionar el tipo de compilador a usar e iniciar todo el proceso de creación de los paquetes.

&#x20;

<figure><img src="https://www.solvetic.com/uploads/monthly_11_2017/ccs-7463-0-44193100-1511183559.png" alt=""><figcaption></figcaption></figure>

&#x20;

Su descarga gratuita está disponible en el siguiente enlace:

&#x20;

[ Nullsoft Scriptable Install System (NSIS)](http://nsis.sourceforge.net/Main_Page)

&#x20;

&#x20;

Advanced Installer<br>

<figure><img src="https://www.solvetic.com/uploads/monthly_11_2017/ccs-7463-0-35484900-1511183531.png" alt=""><figcaption></figcaption></figure>

&#x20;

Advanced Installer es una [ herramienta](https://www.solvetic.com/page/recopilaciones/s/recopilacion/herramientas-para-crear-paquetes-instalados-windows) de creación de instaladores de Windows para instalar, actualizar y configurar los productos de forma segura y confiable.

&#x20;

Una característica única de Advanced Installer es Installer Analytics. Básicamente es un conjunto de [ herramientas](https://www.solvetic.com/page/recopilaciones/s/recopilacion/herramientas-para-crear-paquetes-instalados-windows) para ver cómo los usuarios instalan, usan y desinstalan sus aplicaciones. Podremos ver fácilmente qué tan grande es nuestra base de usuarios, cargar una encuesta cuando un usuario desinstala el programa y obtener información sobre el sistema y la ubicación geográfica del usuario. Todo esto en una interfaz web elegante y moderna que podemos probar nosotros mismos.

&#x20;

Dentro de las características de la versión gratuita tenemos

* Instalador y desinstalador, podemos crear paquetes que se instalen y registren por completo, respectivamente, desinstalen y anulen el registro de la aplicación
* Siempre son válidos los paquetes MSI 2.0 / 3.x / 4.x / 5.0
* Cuenta con un asistente para la creación de proyectos simples
* Podemos agregar o Eliminar personalización en el Panel de control
* Instalaciones por usuario y por máquina, será posible seleccionar qué tipo de instalación se adapta mejor a las necesidades: por usuario o por máquina si el usuario es Administrador
* Soporta formatos en XML
* Podremos crear paquetes que se ejecutan e instalan en procesadores de 32 bits o en las últimas CPU de 64 bits de Intel y AMD
* Opcionalmente permite crear apps que forzen el reinicio, así se solicita al usuario un reinicio incluso después de una instalación exitosa, admitiendo componentes sensibles que lo requieran
* Usar variables y parámetros casi en cualquier parte de las instalaciones
* Edición con formato visual
* Ejecuta y registra MSI
* Permite crear archivos y carpetas, variables de entorno, entradas de registros, registros de fuentes y más.

&#x20;

Este será el entorno ofrecido por Advanced Installer:

&#x20;

<figure><img src="https://www.solvetic.com/uploads/monthly_11_2017/ccs-7463-0-86831000-1511183555.png" alt=""><figcaption></figcaption></figure>

&#x20;

Allí basta con seleccionar que tipo de paquete deseamos crear e iniciar el respectivo proceso.

&#x20;

<figure><img src="https://www.solvetic.com/uploads/monthly_11_2017/ccs-7463-0-34762300-1511183552.png" alt=""><figcaption></figcaption></figure>

&#x20;

Podemos descargar una versión de prueba en el siguiente enlace:

&#x20;

[ Advanced Installer](https://www.advancedinstaller.com/)

&#x20;

&#x20;

&#x20;

Inno Setup<br>

<figure><img src="https://www.solvetic.com/uploads/monthly_11_2017/ccs-7463-0-54511800-1511183527.png" alt=""><figcaption></figcaption></figure>

&#x20;

Inno Setup es un instalador gratuito para programas de ambientes Windows. Fue presentado por primera vez en 1997, y actualmente Inno Setup rivaliza e incluso supera a muchos instaladores comerciales en cuanto a conjunto de características y estabilidad.

&#x20;

Sus características más sobresalientes son

* Compatible con todas las versiones de Windows desde 2000, incluidos: Windows 10, Windows 8.1, Windows 8, Windows Server 2012 / 2016, Windows 7, Windows Server 2008 R2, Windows Vista, Windows Server 2008, Windows XP, Windows Server 2003 y Windows 2000 y Windows 10. (No se requieren paquetes de servicio.)
* Amplia compatibilidad con la instalación de aplicaciones de 64 bits en las ediciones de 64 bits de Windows. Ambas arquitecturas x64 e Itanium son compatibles
* Admite la creación de un único EXE para instalar el programa y facilita la distribución en línea. La extensión de disco también es compatible
* Interfaz de asistente de Windows estándar
* Tipos de configuración personalizables, tales como Completo, Mínimo, Personalizado
* Completa las capacidades de desinstalación
* Instalación de archivos: Incluye soporte integrado para la compresión de archivos "deflate", bzip2 y 7-Zip LZMA / LZMA2. El instalador tiene la capacidad de comparar información de la versión del archivo, reemplazar archivos en uso, usar el conteo de archivos compartidos, registrar DLL / OCX y escribir bibliotecas, e instalar fuentes
* Creación de atajos en cualquier lugar, incluso en el menú Inicio y en el escritorio del sistema
* Creación de entradas de registro
* Ejecución de otros programas antes, durante o después de la instalación
* Soporte para instalaciones multilingües, incluido el soporte de idiomas de derecha a izquierda
* Soporte para instalaciones aprobadas y encriptadas
* Soporte para instalaciones y desinstalaciones firmadas digitalmente, incluyendo doble firma (SHA1 y SHA256)
* Instalación y desinstalación silenciosa
* Unicode se instala automáticamente
* Opción de preprocesador integrado para personalización avanzada en tiempo de compilación
* Opción integrada del motor de scripts de Pascal para la instalación avanzada en tiempo de ejecución y la personalización de desinstalación
* El código fuente completo está disponible (Borland Delphi 2.0-5.0 y 2009).

&#x20;

&#x20;

<figure><img src="https://www.solvetic.com/uploads/monthly_11_2017/ccs-7463-0-84588300-1511183548.png" alt=""><figcaption></figcaption></figure>

&#x20;

Se ofrece de forma gratuita en el siguiente enlace:

&#x20;

[ Inno Setup](http://www.jrsoftware.org/isdl.php)<br>

&#x20;

&#x20;

WIX Toolset<br>

<figure><img src="https://www.solvetic.com/uploads/monthly_11_2017/ccs-7463-0-15743700-1511183524.png" alt=""><figcaption></figcaption></figure>

&#x20;

Ha sido desarrollada para ser el conjunto de [ herramientas](https://www.solvetic.com/page/recopilaciones/s/recopilacion/herramientas-para-crear-paquetes-instalados-windows) más poderoso disponible para crear la experiencia de instalación de [ Windows](https://www.solvetic.com/page/recopilaciones/s/recopilacion/herramientas-para-crear-paquetes-instalados-windows). Es de código libre y abierto desde 2004.

&#x20;

WIX Toolset se basa en el modelo de creación de XML. Si no contamos con Visual Studio, podemos usar las herramientas Wix o MSBuild. Admite la construcción de archivos de instalación de MSI, MSP, MSM y MST. También es compatible con una gran cantidad de características de Windows Installer.

&#x20;

<figure><img src="https://www.solvetic.com/uploads/monthly_11_2017/ccs-7463-0-97704800-1511183544.png" alt=""><figcaption></figcaption></figure>

&#x20;

Su descarga está disponible de forma gratuita en el siguiente enlace:

&#x20;

[ WIX Toolset](https://github.com/wixtoolset/wix3/releases/tag/wix311rtm)

&#x20;

&#x20;

De esta forma tenemos opciones para la creación de paquetes instaladores de Windows.

[Creando Instalador para software Visual Basic 6](https://www.youtube.com/watch?v=fln6PDCZQYo)

Para crear un instalador de una aplicación Visual Basic 6, debes usar el **Asistente de Distribución** dentro del propio IDE. Este asistente se encuentra en el menú "Complementos" y te guiará para empaquetar tu proyecto con el _runtime_ de Visual Basic y las DLLs necesarias. This video demonstrates the process of creating a setup for your Visual Basic 6 application:

<figure><img src=".gitbook/assets/Miniatura de vídeo relacionado" alt=""><figcaption></figcaption></figure>

{% embed url="https://youtu.be/fln6PDCZQYo" %}

1. **Accede al asistente:** Abre tu proyecto en Visual Basic 6 y ve a `Complementos` > `Administrador de complementos`. Asegúrate de que el "Distribución de Aplicaciones" esté habilitado.
2. **Inicia el asistente:** Haz clic en el menú `Complementos` y selecciona la opción del **Asistente de Distribución**.
3. **Selecciona "Empaquetar":** En el diálogo que aparece, elige la primera opción, "Empaquetar", para generar los archivos de instalación.
4. **Configura las opciones:** Sigue los pasos del asistente para configurar el nombre del proyecto, la versión y los detalles de la aplicación.
5. **Genera el paquete:** El asistente creará un archivo ejecutable y otros archivos de soporte que contienen todo lo necesario para instalar tu aplicación en otros ordenadores.&#x20;

Consideraciones adicionales

* **Runtime de Visual Basic 6:** El instalador debe incluir el _runtime_ de Visual Basic 6 para que la aplicación funcione correctamente en otros sistemas.
* **Controles y DLLs:** Si tu aplicación utiliza controles o librerías de enlace dinámico (DLLs) adicionales, asegúrate de incluirlas en el paquete. El asistente de distribución te ayudará con esto.
* **Versiones de Visual Basic:** La última versión oficial de Visual Basic 6 fue lanzada en 1998 y su soporte terminó en 2009.
* **Compatibilidad:** Debido a que es un software antiguo, puede haber problemas de compatibilidad con sistemas operativos modernos, como Windows 10 u 11.
* **Herramientas adicionales:** Puedes encontrar herramientas de terceros que facilitan la creación de instaladores, como la disponible en nuke.vbcorner.net.&#x20;

## Aplicación de escritorio con php

{% embed url="https://youtu.be/21miTEsnIFQ" %}

## Las 10 herramientas imprescindibles para desarrolladores PHP

{% embed url="https://youtu.be/rnBuovSUDck" %}
