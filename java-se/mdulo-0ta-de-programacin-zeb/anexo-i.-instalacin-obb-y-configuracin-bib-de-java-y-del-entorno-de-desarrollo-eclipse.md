# ANEXO I. INSTALACIÓN Y CONFIGURACIÓN DE JAVA Y DEL ENTORNO DE DESARROLLO ECLIPSE

## Instalar y Configurar Java Development Kit (JDK)

Descargar las Java Development Kit de la URL [http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html):

En la página de descargas, pulsar en el checkbox _Accept License Agreement_ sobre la última versión de _Java SE Development Kit_:

> **Nota**: Durante la realización de este manual, la última versión de las JDK era la _8u151_.

Existen varias versiones a descargar en función del Sistema Operativo en el que lo vayamos a instalar: para Sistemas Operativos _Windows_, elegir _jdk-8u151-windows-x64.exe_:

Una vez descargado, abrimos un _Explorador de Windows_ y localizamos el fichero descargado. Una vez localizado, para instalarlo pulsamos doble click sobre el fichero:

Se abre un asistente que nos guiará durante el proceso de instalación. Pulsamos el botón _Next_:

En esta ventana se seleccionan los elementos de JDK a instalar. Están marcadas todas las opciones, incluido las _Development Tools_ que es la opción que nos interesa:

* **Development Tools**: incluye herrientas de desarrollo como el compilador de java _javac_ entre otros.
* **Source Code**: Códifo fuente de java.
* **Public JRE**: Java Runtime Environment. Incluye sólo herramientas para ejecutar un programa java.

También se configura la localización donde se instalarán las JDK. La ubicación por defecto es **C:\Program Files\Java\jdk1.8.0\_151**, la dejamos como está. Pulsamos el botón _Next_:

En esta ventana se pide la ubicación donde se instalarán las JRE en nuestro equipo. Si os fijáis, en la ventana anterior, estaba marcada la opción _Public JRE_, esto hace que, aparte de las _JDK_, instale también las _JRE_. La ubicación por defecto es **C:\Program Files\Java\jre1.8.0\_151**, la dejamos como está. Pulsamos el botón _Next_:

Al finalizar el asistente de instalación nos aparecerá la siguiente ventana, eso nos indica que la instalación se ha realizado con éxito. Pulsamos el botón _Close_.

Para comprobar que la instalación se ha realizado correctamente, abrimos un _Explorador de archivos_ y debería existir la carpeta **C:\Archivos de programa\Java\jdk1.8.0\_151**. La carpeta **bin** del directorio de instalación contiene, entre otros, los siguientes ejecutables:

* **java.exe**: Permite ejecutar aplicaciones Java.
* **javac.exe**: Permite compilar código fuente Java (No se instala con las JRE).

### Configurar la variable del sistema PATH

**PATH** es la variable del sistema que utiliza el sistema operativo para buscar los ejecutables necesarios desde la línea de comandos o la ventana Terminal. Debemos añadir a la variable **PATH** la ruta donde se encuentran los ejecutables **java.exe** y **javac.exe**.

Para ello abrimos el _Panel de Control_ de Windows y nos situamos en _Sistemas y seguridad - Sistema_. En el panel de la izquierda, pulsamos en la opción _Configuración avanzada del sistema_:

En el apartado _Variables del sistema_ seleccionamos la variable _Path_ y pulsamos en _Editar_:

Al final de la lista añadimos una nueva entrada y añadimos la ubicación de los ejecutables _java.exe_ y _javac.exe_, en este caso **C:\Archivos de programa\Java\jdk1.8.0\_151\bin** y pulsamos el botón _Aceptar_:

> **Nota**: El sistema va a cambiar la ruta **C:\Archivos de programa\Java\jdk1.8.0\_151\bin** por **C:\Program Files\Java\jdk1.8.0\_151\bin**. Las dos ubicaciones apuntan a lo mismo.

Para comprobar si todo ha ido bien, abrimos la herramienta _Símbolo de sistema_ y ejecutamos el comando **java --version**, debería devolver el siguiente resultado:

**Nota**: Ver la documentación Oficial de Oracle sobre [cómo cambiar la variable del sistema PATH](https://www.java.com/es/download/help/path.xml).

¡Listo! Ya hemos instalado las herramientas de desarrollo de Java _JDK_.

## Instalar Entorno de Desarrollo Eclipse

Descargar Eclipse de la URL [https://www.eclipse.org/downloads/](https://www.eclipse.org/downloads/)

Pulsamos en el bótón de _Download_:

Una vez descargado, abrimos un _Explorador de Windows_ y localizamos el fichero descargado llamado **eclipse-inst-win64.exe**. Una vez localizado, para instalarlo pulsamos doble click sobre el fichero para abrir el asistente de instalación:

Pulsamos sobre la opción _Eclipse IDE for Java Developers_ que trae las herramientas necesarias para desarrollar aplicaciones Java.

> **Nota**: Si quisiéramos desarrollar Aplicaciones Web, necesitaríamos descargar la versión _Eclipse IDE for Java EE Developers_:

Elegimos la ubicación donde vamos a instalar Eclipse. En este caso no vamos a dejar la ubicación que viene por defecto, sino que lo instalaremos en la ubicación **C:\Users\usuario\eclipse\java-oxygen**, donde _usuario_ corresponde al **usuario del sistema con el que hemos iniciado sesión en nuestro equipo**. Posteriormente pulsamos en el botón **INSTALL**:

Una vez finalizado el proceso de instalación debería verse la siguiente pantalla. Pulsamos el botón _X_ situado en la esquina superior derecha.

Abrimos un _Explorador de archivos_ y localizamos la carpeta de instalación **C:\Usuarios\usuario\eclipse\java-oxygen**:

### Configurar Java en Eclipse

Abrimos la aplicación Eclipse descargada en el apartado anterior (Deberíamos tener en el escritorio un enlace a la aplicación).

Modificamos la ubicación para el _Workspace_ que viene por defecto, en este caso **C:\Users\usuario\eclipse\workspace-java**.

> **Nota**: Todas las configuraciones que hagamos y los proyectos que creemos se guardarán en esta carpeta.

Esta es la pantalla principal del IDE eclipse.

Configurar el JDK instalado en el paso anterior, para ello abrimos el menú _Window - Preferences_ y pulsamos _Enter_:

Pulsamos el botón _Add..._ para añadir una nueva instalación de las _JDK_:

En _Installed JRE Types_ seleccionamos _Standard VM_ y pulsamos el botón _Next_:

Pulsamos en el botón _Directory_ y en la ventana del _Explorador de archivos_ que se abre buscamos la ruta donde se encuentra instalada las JDK, en este caso **C:\Archivos de programa\Java\jdk1.8.0\_151**

Vemos que se han completado los campos _JRE home_ con **C:\Archivos de programa\Java\jdk1.8.0\_151** y _JRE name_ con **jdk1.8.0\_151**. Pulsamos el botón _Finish_:

Marcamos la opción **jdk1.8.0\_155**, para que sea la versión JDK por defecto:

Una vez marcada la opción **jdk1.8.0\_155** debe aparecer en negrita y pulsamos el botón _Apply and Close_:

¡Listo! Ya hemos instalado el IDE Eclipse.

### Configurar Java en Eclipse

Abrimos la aplicación Eclipse descargada en el apartado anterior (Deberíamos tener en el escritorio un enlace a la aplicación).

Modificamos la ubicación para el _Workspace_ que viene por defecto, en este caso **C:\Users\usuario\eclipse\workspace-java**.

> **Nota**: Todas las configuraciones que hagamos y los proyectos que creemos se guardarán en esta carpeta.

Esta es la pantalla principal del IDE eclipse.

Configurar el JDK instalado en el paso anterior, para ello abrimos el menú _Window - Preferences_ y pulsamos _Enter_:

Pulsamos el botón _Add..._ para añadir una nueva instalación de las _JDK_:

En _Installed JRE Types_ seleccionamos _Standard VM_ y pulsamos el botón _Next_:

Pulsamos en el botón _Directory_ y en la ventana del _Explorador de archivos_ que se abre buscamos la ruta donde se encuentra instalada las JDK, en este caso **C:\Archivos de programa\Java\jdk1.8.0\_151**

Vemos que se han completado los campos _JRE home_ con **C:\Archivos de programa\Java\jdk1.8.0\_151** y _JRE name_ con **jdk1.8.0\_151**. Pulsamos el botón _Finish_:

Marcamos la opción **jdk1.8.0\_155**, para que sea la versión JDK por defecto:

Una vez marcada la opción **jdk1.8.0\_155** debe aparecer en negrita y pulsamos el botón _Apply and Close_:

¡Listo! Ya hemos instalado el IDE Eclipse.
