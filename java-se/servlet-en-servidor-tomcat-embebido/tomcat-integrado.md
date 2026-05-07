# Tomcat integrado

En este tutorial, mostramos cómo trabajar con un servidor Tomcat integrado. Tomcat puede ejecutarse en modo integrado; esto significa que no es necesario crear un archivo WAR e implementarlo en un servidor Tomcat independiente. Los ejemplos de este tutorial se compilan con Maven.

### Gato

Apache Tomcat es una implementación de código abierto de las tecnologías Java Servlet, JavaServer Pages, Java Expression Language y Java WebSocket.

Apache Maven es una herramienta de gestión y comprensión de proyectos de software. El proyecto se describe en un archivo XML llamado `pom.xml`. Este archivo contiene las dependencias del proyecto con otros módulos y componentes externos, el orden de compilación, los directorios y los complementos necesarios.

### Creación de un servlet

En el siguiente ejemplo, creamos una aplicación Java de línea de comandos con un servidor Tomcat integrado. La aplicación adjunta un servlet simple.

<figure><img src="https://zetcode.com/img/web/embeddedtomcat/project_structure.png" alt="Estructura del proyecto"><figcaption><p>Figura: Estructura del proyecto</p></figcaption></figure>

La figura muestra la estructura del proyecto en NetBeans. Observe que utilizamos una aplicación de consola Java Maven, no una aplicación web Maven.

pom.xml<i class="fa-copy">:copy:</i>

```
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
         
    <modelVersion>4.0.0</modelVersion>
    <groupId>com.zetcode</groupId>
    <artifactId>TomcatEx incrustado</artifactId>
    <version>1.0-SNAPSHOT</version>
    <packaging>jar</packaging>
    <propiedades>
        <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
        <maven.compiler.source>1.8</maven.compiler.source>
        <maven.compiler.target>1.8</maven.compiler.target>
        <tomcat.version>9.0.0.M6</tomcat.version>
    </propiedades>
    
    <dependencias>
        
        <dependencia>
            <groupId>javax.servlet</groupId>
            <artifactId>javax.servlet-api</artifactId>
            <version>3.1.0</version>
        </dependencia>         
        <dependencia>
            <groupId>org.apache.tomcat.embed</groupId>
            <artifactId>tomcat-embed-core</artifactId>
            <version>${tomcat.version}</version>
        </dependencia>
        <dependencia>
            <groupId>org.apache.tomcat.embed</groupId>
            <artifactId>tomcat-embed-logging-juli</artifactId>
            <version>${tomcat.version}</version>
        </dependencia>
        
       
    </dependencias>    
    
    <construcción>    
        <plugins>
            <plugin>
                <groupId>org.codehaus.mojo</groupId>
                <artifactId>appassembler-maven-plugin</artifactId>
                <version>1.1.1</version>
                <configuración>
                    <assembleDirectory>target</assembleDirectory>
                    <programas>
                        <programa>
                            <mainClass>com.zetcode.embedded.EmbeddedTomcatEx</mainClass>
                            <nombre>aplicación web</nombre>
                        </programa>
                    </programas>
                </configuración>
                <ejecuciones>
                    <ejecución>
                        <fase>paquete</fase>
                        <objetivos>
                            <meta>ensamblar</meta>
                        </objetivos>
                    </ejecución>
                </ejecuciones>
            </plugin>
        </plugins>    
    </build>
    
</proyecto>
```

El archivo Maven `pom.xml`contiene dependencias para el servidor Tomcat integrado y el complemento de ensamblaje, que compila la aplicación. Las dependencias para el contenedor JSP no están incluidas en esta aplicación, ya que solo tenemos un servlet.

EmbeddedTomcatEx.java<i class="fa-copy">:copy:</i>

```
paquete com.zetcode.embedded;

import javax.servlet.ServletException;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import java.io.File;
import java.io.IOException;
import java.io.Writer;
import org.apache.catalina.Context;
import org.apache.catalina.LifecycleException;
import org.apache.catalina.startup.Tomcat;

clase pública EmbeddedTomcatEx {

    public static void main(String[] args) throws LifecycleException,
            InterruptedException, ServletException {

        Tomcat tomcat = nuevo Tomcat();
        tomcat.setPort(8082);

        Context ctx = tomcat.addContext("/", new File(".").getAbsolutePath());

        Tomcat.addServlet(ctx, "Incrustado", new HttpServlet() {
            @Anular
            protected void service(HttpServletRequest req, HttpServletResponse resp)
                    lanza ServletException, IOException {
                
                Escritor w = resp.getWriter();
                w.write("Servlet Tomcat integrado.\n");
                w.flush();
                w.close();
            }
        });

        ctx.addServletMapping("/*", "Incrustado");

        Tomcat.start();
        Tomcat.getServer().await();
    }
}
```

Se `EmbeddedTomcatEx`trata de una aplicación de consola Java que incluye un servidor Tomcat integrado.

```
Tomcat tomcat = nuevo Tomcat();
tomcat.setPort(8082);
```

Tomcat se inicia en el puerto 8082. El puerto predeterminado es el 8080; NetBeans utiliza el 8084 para su servidor Tomcat integrado. Elegimos otro puerto para evitar conflictos.

```
Context ctx = tomcat.addContext("/", new File(".").getAbsolutePath());
```

Cada aplicación se asigna a un contexto. Con este `addContext`método, creamos una aplicación que no admite archivos JSP y no tiene ningún `web.xml` archivo. Usamos una ruta de contexto raíz y un directorio de trabajo actual para la base del documento.

```
Tomcat.addServlet(ctx, "Incrustado", new HttpServlet() {
    @Anular
    protected void service(HttpServletRequest req, HttpServletResponse resp)
            lanza ServletException, IOException {
        
        Escritor w = resp.getWriter();
        w.write("Servlet Tomcat integrado.\n");
        w.flush();
        w.close();
    }
});
```

Se agrega un nuevo servlet con este `addServlet`método. El servlet simplemente responde con un texto ASCII.

```
ctx.addServletMapping("/*", "Incrustado");
```

La configuración del servlet controla cómo se accede al servlet, denominado Embedded. En nuestro ejemplo, cualquier URL termina llamando a nuestro servlet.

```
Tomcat.start();
Tomcat.getServer().await();
```

El servidor Tomcat se ha iniciado.

```
$ curl localhost:8082/
Servlet Tomcat integrado.
```

Ejecutamos la aplicación y la probamos con la `curl`herramienta.

### Archivo JSP

En el segundo ejemplo, utilizamos un servidor Tomcat integrado para servir un archivo JSP.

pom.xml<i class="fa-copy">:copy:</i>

```
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>
    <groupId>com.zetcode</groupId>
    <artifactId>TomcatEx2 integrado</artifactId>
    <version>1.0-SNAPSHOT</version>
    <packaging>jar</packaging>
    <propiedades>
        <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
        <maven.compiler.source>1.8</maven.compiler.source>
        <maven.compiler.target>1.8</maven.compiler.target>
        <tomcat.version>9.0.0.M6</tomcat.version>
    </propiedades>
    
    <dependencias>
        
        <dependencia>
            <groupId>javax.servlet</groupId>
            <artifactId>javax.servlet-api</artifactId>
            <version>3.1.0</version>
        </dependencia>         
        <dependencia>
            <groupId>org.apache.tomcat.embed</groupId>
            <artifactId>tomcat-embed-core</artifactId>
            <version>${tomcat.version}</version>
        </dependencia>
        <dependencia>
            <groupId>org.apache.tomcat.embed</groupId>
            <artifactId>tomcat-embed-logging-juli</artifactId>
            <version>${tomcat.version}</version>
        </dependencia>
        
        <dependencia>
            <groupId>org.apache.tomcat</groupId>
            <artifactId>tomcat-jasper</artifactId>
            <version>${tomcat.version}</version>
        </dependencia>
        
        <dependencia>
            <groupId>org.apache.tomcat</groupId>
            <artifactId>tomcat-jasper-el</artifactId>
            <version>${tomcat.version}</version>
        </dependencia>
        
        <dependencia>
            <groupId>org.apache.tomcat</groupId>
            <artifactId>tomcat-jsp-api</artifactId>
            <version>${tomcat.version}</version>
        </dependencia>        
        
    </dependencias>    
    
    <construcción>
    
        <plugins>
            <plugin>
                <groupId>org.codehaus.mojo</groupId>
                <artifactId>appassembler-maven-plugin</artifactId>
                <version>1.1.1</version>
                <configuración>
                    <assembleDirectory>target</assembleDirectory>
                    <programas>
                        <programa>
                            <mainClass>com.zetcode.embedded.EmbeddedTomcatEx2</mainClass>
                            <nombre>aplicación web</nombre>
                        </programa>
                    </programas>
                </configuración>
                <ejecuciones>
                    <ejecución>
                        <fase>paquete</fase>
                        <objetivos>
                            <meta>ensamblar</meta>
                        </objetivos>
                    </ejecución>
                </ejecuciones>
            </plugin>
        </plugins>    
    </build>
    <name>EmbeddedTomcatEx2</name>
</proyecto>
```

En este `pom.xml`archivo, también incluimos dependencias para el contenedor JSP Tomcat integrado: `tomcat-jasper`, `tomcat-jasper-el`, y `tomcat-jsp-api`.

index.jsp<i class="fa-copy">:copy:</i>

```
<%@page contentType="text/html" pageEncoding="UTF-8"%>
<!DOCTYPE html>
<html>
    <head>
        <title>Archivo JSP</title>
        <meta charset="UTF-8">
    </head>
    <cuerpo>
        <p>
            Este es un archivo JSP simple.            
        </p>
    </body>
</html>
```

Este es un archivo JSP sencillo que será servido por un servidor Tomcat integrado.

EmbeddedTomcatEx2.java<i class="fa-copy">:copy:</i>

```
paquete com.zetcode.embedded;

import javax.servlet.ServletException;
import java.io.File;
import org.apache.catalina.LifecycleException;
import org.apache.catalina.startup.Tomcat;

clase pública EmbeddedTomcatEx2 {

    public static void main(String[] args) throws LifecycleException,
            InterruptedException, ServletException {

        Cadena docBase = "src/main/webapp/";
        
        Tomcat tomcat = nuevo Tomcat();
        tomcat.setPort(8082);

        tomcat.addWebapp("/", nuevo archivo(docBase).getAbsolutePath());

        Tomcat.start();
        Tomcat.getServer().await();
    }
}

```

La aplicación sirve un archivo JSP. El archivo se encuentra en el `src/main/webapp` subdirectorio.

```
tomcat.addWebapp("/", nuevo archivo(docBase).getAbsolutePath());
```

Esta vez usamos esto `addWebapp`para agregar nuestra aplicación al servidor Tomcat.

```
$ curl localhost:8082/

<!DOCTYPE html>
<html>
    <head>
        <title>Archivo JSP</title>
        <meta charset="UTF-8">
    </head>
    <cuerpo>
        <p>
            Este es un archivo JSP simple.            
        </p>
    </body>
</html>
```

Esto nos ocurre cuando accedemos a la aplicación.

Este fue el tutorial de Tomcat integrado. Con Tomcat integrado, servimos un servlet y un archivo JSP. Hemos utilizado Apache Tomcat, Maven y NetBeans. También puedes consultar algunos tutoriales relacionados: [Aplicación Jersey con Jetty integrado](https://zetcode.com/articles/jerseyembeddedjetty/) , [Tutorial de Jetty](https://zetcode.com/java/jetty/) , [Tutorial de Java](https://zetcode.com/lang/java/) o [Tutorial de etiquetas de consulta SQL](https://zetcode.com/java/sqlquerytag/) .
