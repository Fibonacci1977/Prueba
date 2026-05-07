# Utilizar Tomcat embebido

Utilizar **Tomcat embebido** (o embebido) es una excelente forma de crear aplicaciones Java autocontenidas, donde el servidor web está dentro de tu aplicación (un archivo `.jar`) en lugar de instalar un servidor Tomcat por separado. Esto es muy común en microservicios. \[[1](https://translate.google.com/translate?u=https://medium.com/@sunil17bbmp/spring-boot-embedded-servers-explained-tomcat-jetty-undertow-3f5514dc525b\&hl=es\&sl=en\&tl=es\&client=sge), [2](https://translate.google.com/translate?u=https://codemia.io/knowledge-hub/path/microservices_embedded_tomcat_vs_standalone_tomcat_difference\&hl=es\&sl=en\&tl=es\&client=sge), [3](https://picodotdev.github.io/blog-bitix/2015/03/aplicacion-web-java-autocontenida-con-tomcat-embedded/), [4](https://picodotdev.github.io/blog-bitix/2015/03/aplicacion-web-java-autocontenida-con-tomcat-embedded/)]Aquí tienes los pasos para utilizarlo:Este video muestra cómo desplegar una aplicación WAR en Tomcat de manera sencilla

1\. Agregar Dependencias (Maven)Necesitas agregar las dependencias de Tomcat embebido en tu archivo `pom.xml`.xml

```
<dependencies>
    <!-- Tomcat Embed Core -->
    <dependency>
        <groupId>org.apache.tomcat.embed</groupId>
        <artifactId>tomcat-embed-core</artifactId>
        <version>10.1.x</version> <!-- Usa la versión más reciente -->
    </dependency>
    <!-- Jasper para JSP (si usas JSPs) -->
    <dependency>
        <groupId>org.apache.tomcat.embed</groupId>
        <artifactId>tomcat-embed-jasper</artifactId>
        <version>10.1.x</version>
    </dependency>
</dependencies>
```

Usa el código con precaución.2. Crear el Servidor Embebido (Código Java)Creas una clase con un método `main` para configurar e iniciar Tomcat programáticamente. \[[1](https://picodotdev.github.io/blog-bitix/2015/03/aplicacion-web-java-autocontenida-con-tomcat-embedded/), [2](https://translate.google.com/translate?u=https://www.codejava.net/servers/tomcat/how-to-embed-tomcat-server-into-java-web-applications\&hl=es\&sl=en\&tl=es\&client=sge)]java

```
import org.apache.catalina.startup.Tomcat;
import java.io.File;

public class AppServidor {
    public static void main(String[] args) throws Exception {
        Tomcat tomcat = new Tomcat();
        tomcat.setPort(8080); // Puerto del servidor

        // Directorio base para la aplicación
        String appBase = ".";
        tomcat.getHost().setAppBase(appBase);

        // Crear contexto y añadir servlets/recursos
        // contextPath "" indica la raíz (http://localhost:8080/)
        tomcat.addWebapp("/", new File("src/main/webapp").getAbsolutePath());

        tomcat.start();
        tomcat.getServer().await(); // Espera conexiones
    }
}
```

Usa el código con precaución.3. Principales Configuraciones

* **Puerto:** `tomcat.setPort(8080);`.
* **Contexto:** `tomcat.addWebapp("/", ...);` define la ruta de la aplicación.
* **Recursos Estáticos:** Puedes definir dónde están tus HTML/CSS/JS con `tomcat.addWebapp`.
* **Servlets:** Puedes añadir servlets manualmente con `tomcat.addServlet`. \[[1](https://translate.google.com/translate?u=https://www.codejava.net/servers/tomcat/how-to-embed-tomcat-server-into-java-web-applications\&hl=es\&sl=en\&tl=es\&client=sge)]

4\. EjecuciónAl ejecutar la clase Java `AppServidor`, Tomcat se inicia y sirve la aplicación configurada. Si empaquetas todo en un JAR ejecutable, puedes correr la aplicación con `java -jar app.jar`.Alternativa: Spring BootLa forma más común y fácil hoy en día es usar **Spring Boot**, que ya incluye y configura automáticamente Tomcat embebido. Solo necesitas la dependencia `spring-boot-starter-web`.Mira este video para aprender a instalar y configurar Apache Tomcat para proyectos web

* **Ventaja de Embebido:** Despliegue rápido, ideal para microservicios y contenedores.
* **Diferencia con Standalone:** No requiere pre-instalar Tomcat, todo va en el JAR. \[[1](https://translate.google.com/translate?u=https://codemia.io/knowledge-hub/path/microservices_embedded_tomcat_vs_standalone_tomcat_difference\&hl=es\&sl=en\&tl=es\&client=sge)]

\-------------------------------------------------------------------------------------------------------



Utilizar Tomcat Embebido (Embedded) permite ejecutar aplicaciones web Java directamente desde un método `main`, sin necesidad de instalar un servidor externo, ideal para microservicios. Se logra añadiendo las dependencias de `tomcat-embed-core` en Maven/Gradle, configurando el puerto y el contexto programáticamente. Spring Boot automatiza este proceso. \[[1](https://picodotdev.github.io/blog-bitix/2015/03/aplicacion-web-java-autocontenida-con-tomcat-embedded/), [2](https://translate.google.com/translate?u=https://www.codejava.net/servers/tomcat/how-to-embed-tomcat-server-into-java-web-applications\&hl=es\&sl=en\&tl=es\&client=sge), [3](https://translate.google.com/translate?u=https://www.linkedin.com/posts/ganesh-rathod-88009822b_how-tomcat-works-with-a-spring-boot-application-activity-7388864368995672064-zR6q\&hl=es\&sl=en\&tl=es\&client=sge), [4](https://picodotdev.github.io/blog-bitix/2015/03/aplicacion-web-java-autocontenida-con-tomcat-embedded/)]Pasos para usar Tomcat Embebido (Java Puro)

1. **Añadir Dependencias (Maven):** Incluye `tomcat-embed-core` y `tomcat-embed-jasper` (si usas JSP) en tu `pom.xml`.
2. **Crear el servidor:** Instancia `org.apache.catalina.startup.Tomcat` en tu clase Java.
3. **Configurar:** Define el puerto, directorio base y el contexto de la aplicación.
4. **Iniciar:** Llama a `tomcat.start()` y `tomcat.getServer().await()`. \[[1](https://doc.viafirma.com/viafirma-inbox/install/latest/es/configuracion.html), [2](https://picodotdev.github.io/blog-bitix/2015/03/aplicacion-web-java-autocontenida-con-tomcat-embedded/), [3](https://translate.google.com/translate?u=https://www.codejava.net/servers/tomcat/how-to-embed-tomcat-server-into-java-web-applications\&hl=es\&sl=en\&tl=es\&client=sge)]

java

```
import org.apache.catalina.startup.Tomcat;
import java.io.File;

public class App {
    public static void main(String[] args) throws Exception {
        Tomcat tomcat = new Tomcat();
        tomcat.setPort(8080);
        
        // Define el directorio webapps y contexto
        String webappDirLocation = "src/main/webapp/";
        tomcat.addWebapp("/", new File(webappDirLocation).getAbsolutePath());
        
        tomcat.start();
        tomcat.getServer().await();
    }
}
```

Usa el código con precaución.Ventajas de Tomcat Embebido

* **Despliegue rápido:** La aplicación es un archivo JAR/WAR autocontenido.
* **Portabilidad:** No requiere configurar servidores en el entorno de destino.
* **Ideal para DevOps:** Perfecto para contenedores Docker y microservicios. \[[1](https://translate.google.com/translate?u=https://codemia.io/knowledge-hub/path/microservices_embedded_tomcat_vs_standalone_tomcat_difference\&hl=es\&sl=en\&tl=es\&client=sge), [2](https://picodotdev.github.io/blog-bitix/2015/03/aplicacion-web-java-autocontenida-con-tomcat-embedded/), [3](https://picodotdev.github.io/blog-bitix/2015/03/aplicacion-web-java-autocontenida-con-tomcat-embedded/)]

Tomcat Embebido en Spring BootSpring Boot utiliza TomcatServletWebServerFactory para configurar automáticamente un Tomcat embebido al iniciar la aplicación (`SpringApplication.run()`). Puedes personalizar el puerto en el archivo `application.properties` con `server.port`. \[[1](https://soyjuanito.medium.com/ejecutar-spring-boot-con-tomcat-embebido-sobre-https-0e972d8d7e1c), [2](https://translate.google.com/translate?u=https://www.linkedin.com/posts/ganesh-rathod-88009822b_how-tomcat-works-with-a-spring-boot-application-activity-7388864368995672064-zR6q\&hl=es\&sl=en\&tl=es\&client=sge)]Si prefieres usar un IDE, herramientas como el plugin "Smart Tomcat" en IntelliJ o "Tomcat for Java" en VS Code facilitan este proceso.&#x20;
