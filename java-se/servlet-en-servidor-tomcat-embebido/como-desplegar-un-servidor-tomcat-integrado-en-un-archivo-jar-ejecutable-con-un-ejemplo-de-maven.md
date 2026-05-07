# Cómo desplegar un servidor Tomcat integrado en un archivo JAR ejecutable con un ejemplo de Maven

No hay nada mágico en empaquetar aplicaciones web Java en un archivo JAR ejecutable. Este tutorial sobre Tomcat integrado muestra cómo usar el complemento Apache Maven para crear y ejecutar un archivo JAR ejecutable con Tomcat integrado.

Históricamente, las aplicaciones web Java listas para producción se empaquetaban como archivos WAR. Un motor de servlets, como un [servidor IBM WebSphere o Apache Tomcat](https://www.theserverside.com/video/Tomcat-vs-Apache-HTTP-Server-Whats-the-difference) , alojaba varias aplicaciones simultáneamente. Sin embargo, por diversas razones —como la adopción generalizada de microservicios y el deseo de realizar pruebas unitarias altamente aisladas—, la relación de uno a muchos entre la aplicación web Java y el contenedor de servlets se ha consolidado en una relación de uno a uno.

Los días en que era necesario alojar un archivo WAR en un servidor de aplicaciones completo han [dado paso a un nuevo enfoque](https://www.theserverside.com/blog/Coffee-Talk-Java-News-Stories-and-Opinions/Tomcat-vs-WebSphere-How-these-application-servers-compare) . Ahora, integramos Tomcat en un archivo JAR ejecutable y ejecutamos aplicaciones web Java como si fueran aplicaciones Java independientes. La computación nativa en la nube y el modelo de microservicios han revolucionado el modelo de implementación tradicional de Java Platform, Enterprise Edition, convirtiendo al servidor [Tomcat integrado en](https://www.theserverside.com/definition/embedded-Tomcat) Java en la nueva norma. Si desarrollas aplicaciones Java empresariales modernas, necesitas saber cómo crear un servidor Tomcat integrado con Maven que se pueda implementar en los clientes como un archivo JAR o WAR ejecutable.<br>

### Tomcat integrado, Maven y el JDK

Afortunadamente, no es tan difícil crear un archivo JAR ejecutable que aloje aplicaciones web Java en un servidor Tomcat integrado. En este tutorial, demostraremos [lo fácil que es usar Maven](https://www.theserverside.com/video/Step-by-step-Maven-Tomcat-WAR-file-deploy-example) e integrar Tomcat y aplicaciones web Java en un archivo JAR ejecutable.

Este tutorial de Tomcat integrado solo tiene dos requisitos previos:

1. Debe tener [instalado y configurado el Kit de Desarrollo de Java (JDK) . Se ](https://www.theserverside.com/tutorial/How-to-install-JDK-8-and-write-the-Java-Hello-World-application)[recomienda](http://www.oracle.com/technetwork/pt/java/javase/downloads/jdk8-downloads-2133151.html) la versión 8 del JDK o una posterior .
2. Debes tener [Maven 3.5 o posterior instalado](https://www.theserverside.com/tutorial/How-to-install-Maven-and-build-apps-with-the-mvn-command-line) para poder ejecutar el comando Maven de Tomcat integrado.

Eso es todo. Ni siquiera necesitas descargar el servidor Apache Tomcat, ya que el complemento de Maven para Tomcat se encargará de obtener los binarios de Tomcat por ti.

### Cómo crear un servidor Tomcat integrado con Maven<br>

How to embed TomcatHow to embed Tomcat and Java web apps in an executable JAR filePlayMuteCurrent Time 0:00/Duration 3:47 Picture-in-PictureFullscreen

Este tutorial integrado de Tomcat le muestra cómo crear un archivo JAR ejecutable utilizando Apache Maven.

### Crear una nueva aplicación web Java

> La computación nativa en la nube y los servidores Tomcat integrados en Java han revolucionado el modelo tradicional de implementación de Java EE.

Este tutorial sobre Tomcat integrado comienza el desarrollo completamente desde cero y documenta cada paso del proceso, desde el desarrollo de la aplicación web Java hasta la [implementación del archivo JAR ejecutable](https://www.theserverside.com/blog/Coffee-Talk-Java-News-Stories-and-Opinions/How-to-deploy-a-JAR-file-to-Tomcat-the-right-way) en el que integramos Tomcat.

En mi estación de trabajo local, he creado una carpeta llamada _executable-jar-tutorial_ en la que usaré Maven para ayudar a compilar y probar la aplicación. El comando de Maven para crear el proyecto web Java es:

```
<!-- Todo esto va en una sola línea -->
 mvn archetype-generate -DarchetypeArtifactId=maven-archetype-webapp
```

Este comando de Maven se ejecuta en modo interactivo, lo que significa que se le solicitarán los siguientes cinco datos de entrada:

| Parámetros del comando Maven para proyectos Tomcat integrados |                                                                |
| ------------------------------------------------------------- | -------------------------------------------------------------- |
| versión de complemento para usar                              | _Elige la versión más reciente, que probablemente sea la 1.6._ |
| ID de grupo                                                   | com.mcnz.maven                                                 |
| identificador de artefacto                                    | aplicación web Java                                            |
| Versión                                                       | 1.0-integrado                                                  |
| Paquete                                                       | com.mcnz.maven                                                 |

Esto es lo que muestra la ventana del intérprete de comandos [Bash](https://www.techtarget.com/searchdatacenter/definition/bash-Bourne-Again-Shell) cuando ejecutamos el comando Maven:

<pre><code>/c/ ejemplo de archivo JAR ejecutable/ 
<strong>$ mvn archetype:generate -DarchetypeArtifactId=maven-archetype-webapp
</strong> Defina el valor para la propiedad 'groupId': com.mcnz.maven 
Defina el valor para la propiedad 'artifactId': java-web-app 
Defina el valor para la propiedad 'version' 1.0-SNAPSHOT: : 1.0-embedded 
Defina el valor para la propiedad 'package' com.mcnz.maven: : com.mcnz.maven 
Confirme la configuración de propiedades: Y: : Y 
[INFO] ------------------------------------ 
[INFO] COMPILACIÓN EXITOSA: EMBED TOMCAT EXAMPLE 
[INFO] ------------------------------------
</code></pre>

Cuando finalice la compilación de Maven, editaremos un archivo index.jsp de ejemplo, que encontrará en el siguiente directorio:

```
C:\ tutorial del archivo JAR ejecutable \java-web-app\src\main\webapp
```

### Desarrollar aplicaciones web Java

Edita el archivo index.jsp para que, cuando se ejecute la aplicación web Java, podamos identificarla de forma única como nuestra. He actualizado el archivo index.jsp proporcionado para que quede de la siguiente manera:

```
<html> 
  <body> 
    <h2>¡Hola mundo de las aplicaciones web Java!</h2> 
    <p>Tutorial sobre cómo crear un archivo JAR ejecutable.</p> 
    <p>Un ejemplo de integración de Tomcat.</p> 
  </body> 
</html>
```

Guarda el archivo index.jsp y cierra el editor. Con esto finaliza la parte de desarrollo de software de este tutorial sobre archivos JAR ejecutables.

La aplicación web consta de un único archivo JSP (JavaServer Pages), por lo que no es una aplicación compleja, ni tampoco es necesario que lo sea. El objetivo no es dominar la API de Servlets y JSP, sino crear un archivo JAR ejecutable con una aplicación web Java y Tomcat integrados. No es necesario complicar las cosas anotando Servlets ni [creando un componente RESTful](https://www.theserverside.com/video/Use-Tomcat-Eclipse-to-create-a-JAX-RS-REST-web-service) . Se trata de una prueba de concepto, por lo que un simple archivo "Hola Mundo" es suficiente.

### Crear e integrar un archivo JAR de Tomcat con Maven.<br>

El comando mvn archetype que se ejecuta en este paso crea un archivo pom.xml que Maven utiliza para compilar, construir y [desplegar la aplicación](https://www.theserverside.com/blog/Coffee-Talk-Java-News-Stories-and-Opinions/Learn-Maven-and-master-the-build-tools-fundamental-concepts) . Inicialmente, el archivo POM (Project Object Model) es relativamente pequeño, y las únicas partes necesarias son la dependencia de JUnit y el preámbulo del proyecto.

```
<?xml version="1.0" encoding="UTF-8"?> 

<project> <!-- Preámbulo del ejemplo de incrustación de Tomcat -->    <modelVersion>4.0.0</modelVersion>    <groupId>com.mcnz.maven</groupId>    <artifactId>java-web-app</artifactId>    <version>1.0-embedded</version>    <packaging>war</packaging> <!-- Dependencia JUnit del ejemplo de incrustación de Tomcat -->    <dependencies>       <dependency>          <groupId>junit</groupId>          <artifactId>junit</artifactId>          <version>4.11</version>          <scope>test</scope>       </dependency>    </dependencies> <!--Fin del ejemplo de incrustación de Tomcat --> </project>
   






   










       
```

### Cómo usar el complemento Maven integrado de Tomcat<br>

Para crear un archivo JAR ejecutable, es necesario actualizar el archivo pom.xml con una referencia al complemento Maven de Tomcat integrado. Para ello, añadiremos el siguiente descriptor de compilación inmediatamente después de la sección de dependencias:

```

 <build> 
   <!-- complemento para incrustar Tomcat en un archivo JAR de Java --> 
    <finalName>javawebapp</finalName> 
    <pluginManagement> 
      <plugins> 
          <plugin> 
             <groupId>org.apache.tomcat.maven</groupId> 
             <artifactId>tomcat7-maven-plugin</artifactId> 
             <version>2.1</version> 

             <configuration> <!-- raíz de contexto para aplicaciones web Java -->                <path>/tutorial</path> <!-- nombre del archivo JAR ejecutable de Tomcat -->                <finalName>executable.jar</finalName>              </configuration>           </plugin>        </plugins>     </pluginManagement>  </build>
               

               






```

Una vez editado y actualizado el archivo pom.xml con una referencia al complemento de Tomcat para Maven, el último paso consiste en compilar el proyecto y ejecutar el objetivo correspondiente —tomcat7 :exec-war-only— para crear el archivo JAR ejecutable. Al invocar este objetivo de Maven para Tomcat integrado, el complemento de Tomcat para Maven colocará automáticamente el servidor Tomcat integrado dentro del archivo JAR ejecutable.

<pre><code>/c/ ejecutable jar example/javawebapp 
<strong>$ mvn clean install tomcat7:exec-war-only 
</strong><strong>[INFO] --- se está ejecutando el complemento maven de tomcat 
</strong><strong>[INFO] ------------------------------------------- 
</strong><strong>[INFO] COMPILACIÓN EXITOSA: ARCHIVO JAR EJECUTABLE CREADO 
</strong><strong>[INFO] ------------------------------------------- 
</strong><strong>[INFO] Tiempo total: 3.970 s 
</strong><strong>[INFO] -------------------------------------------
</strong>
</code></pre>

Si el comando para crear un archivo JAR ejecutable con un servidor Tomcat integrado se ejecuta correctamente, debería aparecer un nuevo archivo llamado _executable.jar_ en la subcarpeta target del proyecto Maven. Normalmente, una aplicación web Java sencilla como esta no ocuparía más de 10 KB, pero dado que contiene un servidor Tomcat integrado, el tamaño del archivo superará los 8500 KB.

<figure><img src="https://www.theserverside.com/rms/editorial/TSS_tutorial_embed_tomcat_fig1_mobile.png" alt="archivo JAR" height="416" width="520"><figcaption><p>El archivo JAR aparece después de ejecutar correctamente el comando para incrustar Tomcat en un archivo JAR ejecutable.</p></figcaption></figure>

### Cómo ejecutar un archivo JAR ejecutable

Para ejecutar el archivo JAR ejecutable, ejecute el siguiente comando:

```
java -jar ejecutable.jar
```

Este comando activará el inicio del servidor Tomcat integrado y la aplicación web Java alojada estará disponible en la siguiente dirección:

http://localhost:8080/tutorial/index.jsp

<figure><img src="https://www.theserverside.com/rms/editorial/TSS_tutorial_embed_tomcat_fig2_mobile.png" alt="gato" height="309" width="520"><figcaption><p>Al integrar Tomcat en un archivo WAR ejecutable, las aplicaciones web Java serán accesibles a través del navegador.</p></figcaption></figure>

Y eso es todo. Esos son todos los pasos necesarios para crear un archivo JAR ejecutable capaz de alojar una única aplicación web Java en un servidor Tomcat integrado con Java.

### Revisa el POM de Maven

Por cierto, es útil poder ver el archivo pom.xml en su totalidad, así que aquí está el archivo completo del tutorial finalizado:

```
<?xml version="1.0" encoding="UTF-8"?> 
<project> <!-- ejemplo de creación de un archivo jar ejecutable -->   <modelVersion>4.0.0</modelVersion>   <groupId>com.mcnz.maven</groupId>   <artifactId>javawebapp</artifactId>   <version>1.0-embedded</version>   <packaging>war</packaging>     <dependencies> <dependency>   <groupId>       junit</groupId>       <artifactId>junit</artifactId>       <version>4.11</version>       <scope>test</scope>     </dependency>   </dependencies> <!-- Ejemplo de servidor Tomcat integrado de Maven -->    <build>       <finalName>javawebapp</finalName>       <pluginManagement>            <plugins>             <plugin>                <groupId>org.apache.tomcat.maven</groupId>                <artifactId>tomcat7-maven-plugin</artifactId>                <version>2.1</version>                <configuration> <!-- raíz de contexto para aplicaciones web Java -->                  <path>/tutorial</path> <!-- nombre del archivo jar ejecutable -->                  <finalName>executable.jar</finalName>                </configuration>             </plugin>          </plugins>       </pluginManagement>    </build> <!-- fin del tutorial del servidor Tomcat integrado --> </project>

 
  
















  

   






```
