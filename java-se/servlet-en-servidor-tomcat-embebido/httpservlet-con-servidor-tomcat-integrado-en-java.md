# HttpServlet con servidor Tomcat integrado en Java

> **HttpServlet:** Un servlet es una clase Java que se ejecuta en un servidor. Un servlet HTTP es un tipo especial de servlet que gestiona una solicitud HTTP y proporciona una respuesta HTTP.
>
> **Servidor HTTP:** Utilizaremos **Apache Tomcat integrado, un&#x20;**_**servidor**_ web dinámico y _**contenedor de servlets**_ de código abierto desarrollado por la **Apache Software Foundation (ASF)** . Se utiliza principalmente para desplegar y ejecutar _**servlets Java**_**&#x20;y&#x20;**_**páginas JavaServer (JSP)**_ en aplicaciones web.

### **Consulte la estructura de carpetas que se muestra a continuación antes de continuar.** <a href="#id-502e" id="id-502e"></a>

```

├── src/ 
│ ├── servlets/ 
│ │ └── HelloServlet.java 
│ └── App.java 
├── webapp/ 
│ └── WEB-INF/ 
│ └── web.xml 
├── .vscode/ 
│ └── settings.json 
├── bin/ 
│ ├── servlets/ 
│ │ └── HelloServlet.class 
│ └── App.class
```

### Paso 1: Configuración del proyecto. <a href="#d205" id="d205"></a>

Ve a VS Code y crea un nuevo proyecto Java sin ninguna herramienta de compilación. Podrías crearlo con herramientas de compilación como Maven, Gridle, etc.

### **Paso 2: Instale las siguientes dependencias en la biblioteca de su proyecto.** <a href="#id-6f63" id="id-6f63"></a>

1. tomcat-embed-core-9.0.50 — para servidor Tomcat integrado.
2. tomcat-embed-jasper-9.0.50 — para resolver JSPs para ejecutarlos en el servidor Tomcat.
3. javax.servlet-api-4.0.1 — para crear HttpServlet.
4. javax.annotation-api-1.3.2 — para anotaciones relacionadas con HttpServlet, si las hay.

### Recibe las historias de Sasi Bhumaraju en tu bandeja de entrada.

Regístrate gratis en Medium para recibir actualizaciones de este autor.

Suscribir

Recuérdame para iniciar sesión más rápido.

### Paso 3: Escriba el siguiente código para configurar el servidor Tomcat integrado. <a href="#d99e" id="d99e"></a>

```

import java.io.File; 
import org.apache.catalina.Context; 
import org.apache.catalina.LifecycleException; 
import org.apache.catalina.startup.Tomcat; 
import servlets.HelloServlet; 


public  class  App { 
    public  static  void  main (String[] args)  throws LifecycleException { 
        
        
        Tomcat  tomcat  =  new  Tomcat (); // objeto del servidor Tomcat
         tomcat.setPort( 8080 ); // establecer puerto para Tomcat
         tomcat.getConnector(); // crear conexión HTTP con número de puerto 

        // Agregar URL base para el servidor 
        Context  ctx  =   tomcat.addWebapp( "api/" , new  File ( "build/webapp" ).getAbsolutePath()); 

        // Agregar Servlet
         Tomcat.addServlet(ctx, "HelloServlet" , new  HelloServlet ()); 
        // Agregar patrón de URL al servlet agregado
         ctx.addServletMappingDecoded( "/hello" , "HelloServlet" ); 

        // Iniciar el servidor Tomcat
         tomcat.start(); 

        System.out.println( "Servidor Tomcat iniciado en http://localhost:8080" ); 

        // Bloquea el hilo principal y mantiene Tomcat en ejecución. Si no, el programa se detiene ejecutando las instrucciones restantes inmediatamente y el servidor también deja de funcionar.
         tomcat.getServer().await(); 

    }   
}
```

### **Paso 4: Escriba un HttpServlet para que se ejecute en el servidor Tomcat integrado.** <a href="#id-59eb" id="id-59eb"></a>

```

package servlets; 
import java.io.IOException; 
import javax.servlet.http.HttpServlet; 
import javax.servlet.http.HttpServletRequest; 
import javax.servlet.http.HttpServletResponse; 

// @WebServlet("/hello") 
public  class  HelloServlet  extends  HttpServlet { 
    @Override 
    protected  void  doGet (HttpServletRequest req, HttpServletResponse resp)  throws IOException { 
        resp.setContentType( "text/plain" ); 
        resp.getWriter().println( "Hello, Embedded Tomcat!" ); 
    } 
}
```

### **Paso 5: Escriba el archivo web.xml para proporcionar metadatos al servidor Tomcat integrado.** <a href="#id-7cc3" id="id-7cc3"></a>

Este **`web.xml`**&#x61;rchivo es el **descriptor de despliegue** para **servlets** Java , **JSP** y **aplicaciones web** que se ejecutan en **Tomcat** u otros servidores **Java EE** . Configura **servlets, filtros, oyentes, manejo de errores** y más.

```

<!-- El archivo web.xml es el descriptor de despliegue para Java Servlets, JSP y aplicaciones web que se ejecutan en Tomcat u otros servidores Java EE. 
Configura servlets, filtros, oyentes, manejo de errores y más. --> 

< web-app  xmlns = "http://xmlns.jcp.org/xml/ns/javaee" 
         xmlns:xsi = "http://www.w3.org/2001/XMLSchema-instance" 
         xsi:schemaLocation = "http://xmlns.jcp.org/xml/ns/javaee 
         http://xmlns.jcp.org/xml/ns/javaee/web-app_4_0.xsd" 
         version = "4.0" > 

    < servlet > 
        < servlet-name > HelloServlet </ servlet-name > 
        < servlet-class > servlets.HelloServlet </ servlet-class > 
    </ servlet > 

    < servlet-mapping > 
        < servlet-name > HelloServlet </ servlet-name > 
        < url-pattern > /hello </ url-pattern > 
    </ servlet-mapping > 

</ web-app >
```

**Si no quieres usar web.xml, puedes configurar HttpServlet usando código Java. Como en el Paso 1.**

```

// Agregar Servlet
 Tomcat.addServlet(ctx, "HelloServlet" , new  HelloServlet ()); 
// Agregar patrón de URL al Servlet agregado
 ctx.addServletMappingDecoded( "/hello" , "HelloServlet" );
```

### **Paso 6: Ejecute el proyecto Java y escuche en http://localhost:8080/api/hello** <a href="#id-9c2d" id="id-9c2d"></a>

Pulsa Intro o haz clic para ver la imagen a tamaño completo.

<figure><img src="https://miro.medium.com/v2/resize:fit:700/1*y1s7-mdxiNhyRamtwzNH9w.png" alt="" height="305" width="700"><figcaption></figcaption></figure>

***

Utilizar Tomcat embebido con JSP permite ejecutar aplicaciones web Java sin un servidor externo, empaquetando todo en un JAR ejecutable. Se logra añadiendo dependencias de Tomcat (especialmente `jasper` para JSP) a Maven/Gradle, configurando el motor Jasper, y definiendo el contexto de la aplicación, preferiblemente usando `META-INF/resources` para archivos estáticos/JSP. **Puntos Clave para Tomcat Embebido + JSP:**

* **Motor JSP:** Tomcat utiliza **Jasper** para convertir archivos JSP en servlets Java, el cual debe configurarse en el código de inicio.
* **Empaquetado:** Aunque el estándar es WAR, el JSP funciona en JAR si se colocan en `META-INF/resources`.
* **Dependencias Necesarias:** Para habilitar JSP en un Tomcat embebido, se deben incluir en el `pom.xml` (Maven) las bibliotecas de Tomcat, `tomcat-embed-core` y `tomcat-embed-jasper`.
* **Código de Configuración:** Se requiere crear una instancia de `Tomcat()`, configurar el directorio base, y añadir el contexto web con `addContext`.&#x20;

Este video muestra cómo configurar Apache Tomcat en NetBeans para crear y ejecutar un JSP:Si necesitas un ejemplo de código específico para **iniciar el servidor** o para configurar las **dependencias de Maven**, dímelo y te prepararé un ejemplo completo. \[[1](https://tomcat.apache.org/tomcat-10.1-doc/jasper-howto.html)]
