# Servlet en servidor Tomcat embebido

En temas anteriores hemos hablado de tecnologías como [Spring Boot](http://acodigo.blogspot.com/2017/04/spring-boot-crear-una-aplicacion-web.html), [Spark](http://acodigo.blogspot.com/2017/07/spark-tutorial-de-introduccion.html), y otras, que nos facilitan el desarrollo de micro servicios web, los interesante de las mismas, es que, estás utilizan un servidor embebido para contener sus aplicaciones, con esto evitamos la necesidad de crear un archivo WAR y desplegarlo en el servidor para poder ver nuestra aplicación en ejecución, dedicaremos este tutorial a aprender cómo incluir un este tipo de servidores en nuestro proyecto y desplegar un Servlet en él.

Existen muchos servidores que soportan esta característica, [Apache Tomcat](http://tomcat.apache.org/), [Jetty](http://www.eclipse.org/jetty/), etc., para hoy utilizaremos el primero, también aplicaremos los conocimientos adquiridos en el [tutorial Java Servlet](http://acodigo.blogspot.com/2017/07/servlet-java-tutorial-basico.html).

Agregar las dependencias Maven requeridas para utilizar Tomcat Embedded.

```
<dependency>
    <groupId>javax.servlet</groupId>
    <artifactId>javax.servlet-api</artifactId>
    <version>3.1.0</version>
</dependency>
      
<dependency>
    <groupId>org.apache.tomcat.embed</groupId>
    <artifactId>tomcat-embed-core</artifactId>
    <version>${tomcat.version}</version>
</dependency>
<dependency>
    <groupId>org.apache.tomcat.embed</groupId>
    <artifactId>tomcat-embed-logging-juli</artifactId>
    <version>${tomcat.version}</version>
</dependency>
```

El Servlet que utilizaremos para demostración será el siguiente:

```
public class MyServlet extends HttpServlet {

    @Override
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) 
            throws ServletException, IOException {
        
        PrintWriter pw = resp.getWriter();
        pw.println("Este Servlet se ejecuta en un servidor Tomcat Embebido.");
    } 
}
```

Ahora lo importante, iniciar el servidor Apache Tomcat Embebido y registrar nuestro Servlet en él, para esta tarea requerimos el código que vemos a continuación:

```
public class EmbeddedTomcat {

    public static void main(String[] args) throws LifecycleException {
        
        Tomcat tomcat = new Tomcat();
        tomcat.setPort(8888);

        Context ctx = tomcat.addContext("/", new File(".").getAbsolutePath());
        Tomcat.addServlet(ctx, "MyServletName", new MyServlet());      
        ctx.addServletMapping("/*", "MyServletName");

        tomcat.start();
        tomcat.getServer().await();
    }
}
```

Este código Java se explica de este modo:

```
Tomcat tomcat = new Tomcat();
tomcat.setPort(8888);
```

Configurar el servidor para utilizar el puerto 8888 debemos asegurarnos de que el mismo esté disponible, se lanzará una excepción si el puerto está en uso.

```
Context ctx = tomcat.addContext("/", new File(".").getAbsolutePath());
```

Crear el contexto para la aplicación, primero indicamos el context path (ruta de contexto) y luego el directorio de trabajo, en este caso será el directorio raíz de la aplicación.

```
Tomcat.addServlet(ctx, "MyServletName", new MyServlet()); 
ctx.addServletMapping("/*", "MyServletName");
```

Usando el método estático `addServlet(...)` añadimos el Servlet al contexto, luego indicamos la URL que mapeará al Servlet, debemos indicar el nombre del Servlet establecido previamente.

```
tomcat.start();
tomcat.getServer().await();
```

Para finalizar iniciamos el servidor.

Si ejecutamos esta aplicación en nuestro IDE favorito, luego vamos al navegador e ingresamos al host y puerto establecidos, veremos:

[![Servlet en servidor Apache Tomcat Embebido](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjzW93wJuFwell2gt1AI3cXayHhyphenhyphen17KaOIWSPyeNhXUyvkox5mNDiWDmc2Ou1_C4iCwihtCFRc9l8Do23t-AujOPPG-kdPFS1UmtydKxuxefsTwgLs53-wZpuNEq19MdUX0nwjv0scEATc/?imgmax=800)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjAeswojTLawr7e7XuGqpXBZ1zbyPdUTR2MeMv_cun00WDURw8WP42ClDfrbHu4J-CQpsANBfBl9lfGHyn1t2wPAvlt4EQhLEeJCLxEh54GqNDgFmeMTCDtr0LZlLZZIp2-5UBWwh_dKGk/s1600-h/image%5B2%5D)

Si deseamos crear el archivo JAR de nuestra aplicación que contenga el servidor y todo lo necesario para ejecutarse como cualquier otra aplicación Java, agregamos estos plugins.

```
<plugins>
    
    <plugin>
        <groupId>org.apache.maven.plugins</groupId>
        <artifactId>maven-compiler-plugin</artifactId>
        <version>2.3.2</version>
        <inherited>true</inherited>
        <configuration>
            <source>1.8</source>
            <target>1.8</target>
        </configuration>
    </plugin>

    <plugin>
        <groupId>org.apache.maven.plugins</groupId>
        <artifactId>maven-assembly-plugin</artifactId>
        <configuration>
            <descriptorRefs>
                <descriptorRef>jar-with-dependencies</descriptorRef>
            </descriptorRefs>
            <finalName>EmbeddedTomcat-${project.version}</finalName>
            <archive>
                <manifest>
                    <mainClass>carmelo.tutor.EmbeddedTomcat</mainClass>
                </manifest>
            </archive>
        </configuration>
        <executions>
            <execution>
                <phase>package</phase>
                <goals>
                    <goal>single</goal>
                </goals>
            </execution>
        </executions>
    </plugin>

</plugins>
```

Al construir obtendremos el archivo EmbeddedTomcat-1.0-SNAPSHOT-jar-with-dependencies.jar podemos ejecutarlo usando el comando `java –jar` y nuestra aplicación correrá sin problemas.

Descarga el proyecto: [servlet-tomcat-embebido.zip](https://github.com/TutorProgramacion/tutoriales-programacion/raw/master/java/servlet/2017/servlet-tomcat-embedded.zip)
