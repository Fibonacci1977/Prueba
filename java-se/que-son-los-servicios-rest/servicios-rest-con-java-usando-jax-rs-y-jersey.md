# Servicios REST con JAVA usando JAX-RS y Jersey

Ejemplo de cómo crear una API Java (JAX-RS) con servicios REST usando Jersey con Eclipse en un proyecto MAVEN.

![servicios-rest-con-java-usando-jax-rs-y-jersey](https://www.webtutoriales.com/_astro/rest-java-jersey.D-Yajv4L_Z2rnKi8.webp)

Ejemplo de cómo crear una API Java (JAX-RS) con servicios REST usando Jersey con Eclipse en un proyecto MAVEN.

## Requisitos previos <a href="#requisitos-previos" id="requisitos-previos"></a>

Para completar este tutorial con éxito es necesario tener antes instalado Eclipse, el servidor Tomcat y tener nociones básicas de Java.

## ¿Qué es un servicio REST? <a href="#que-es-un-servicio-rest" id="que-es-un-servicio-rest"></a>

REST son las siglas de _Representational State Transfer_. Es una arquitectura de software para desarrollar servicios Web. Coloquialmente, un servicio web sirve para hacer una llamada a una url (normalmente HTTP) y obtener datos de respuesta del servidor (principalmente en formato JSON o XML).

En los últimos años los servicios web REST se han establecido como el modelo predominante en la Web, desplazando a otras arquitecturas como SOAP.

## JAX-RS y Jersey <a href="#jax-rs-y-jersey" id="jax-rs-y-jersey"></a>

JAX-RS es una API de Java para servicios web REST que forma parte de JAVA EE.

Jersey es un framework que simplifica todavía más el uso de JAX-RS extendiéndola y dándole más funcionalidades para los desarrolladores.

## Creación del proyecto en Eclipse <a href="#creacion-del-proyecto-en-eclipse" id="creacion-del-proyecto-en-eclipse"></a>

El primer paso será crear una aplicación llamada **ApiRest**. En eclipse vamos al menú **File > New > Dynamic Web Project**. Luego sólo escribimos el nombre del proyecto como en la imagen y le damos a finalizar.

<img src="https://www.webtutoriales.com/_astro/step1.vJ2P6IoQ_Z1nRj4P.webp" alt="" height="716" width="589">

## Cambiar el tipo de proyecto a Maven <a href="#cambiar-el-tipo-de-proyecto-a-maven" id="cambiar-el-tipo-de-proyecto-a-maven"></a>

MAVEN sirve para gestionar las dependencias del proyecto. Principalmente servirá para registrar las librerías externas que usa el proyecto con sus respectivas versiones. Para que eclipse trate el proyecto como un proyecto Maven, lo convertiremos. Para nos dirigimos a la ventana de Project Explorer (si no lo tenemos abierto en el menú Window > Show View > Project explorer), en la carpeta principal del proyecto le damos **click al botón derecho > Configure > Convert to Maven Project**. Lo dejamos tal cual está en la imagen y pulsamos finish.

<img src="https://www.webtutoriales.com/_astro/step2.XO3f7BNZ_1OXnUr.webp" alt="" height="434" width="511">

Automáticamente se crea un archivo pom.xml en la raíz del proyecto que es donde manejaremos las librerías. Para este ejemplo usaremos las librerías asm.jar, jersey-bundle.jar, json.jar y jersey-server.jar. Para editar pom.xml podemos clickar encima de el con el botón derecho > Open with > Text editor y pegamos este XML:

4.0.0 ApiRest ApiRest 0.0.1-SNAPSHOT war src maven-compiler-plugin 3.5.1 1.8 1.8 maven-war-plugin 3.0.0 WebContent asm asm 3.3.1 com.sun.jersey jersey-bundle 1.19 org.json json 20140107 com.sun.jersey jersey-server 1.19 com.sun.jersey jersey-core 1.19

## Implementación de un servicio web <a href="#implementacion-de-un-servicio-web" id="implementacion-de-un-servicio-web"></a>

Hasta ahora todo lo que hemos hecho ha sido para crear y configurar el proyecto. Ahora creamos un servicio REST que devuelva, por ejemplo, un listado de usuarios. Pero antes crearemos un package donde almazenar nuestro código. Por convención se suele crear uno llamado com. En la carpeta ApiRest / Java Resources / src botón derecho **New > Package**. Ahora dentro de este package botón derecho > New > Class. Se nos abrirá una ventana y ponemos como nombre de la clase UsersService. Dentro de UsersService.java copiaremos este código:

```
package com;
import java.util.ArrayList;import java.util.List;
import javax.ws.rs.GET;import javax.ws.rs.Path;import javax.ws.rs.Produces;import javax.ws.rs.core.Response;
import org.json.JSONException;
@Path("/users")public class UsersService {  private static final long serialVersionUID = 1L;
  @GET  @Produces("application/json")  public Response getUsers() throws JSONException {    List users = new ArrayList<>();    users.add(new User("admin"));    users.add(new User("john"));    users.add(new User("usuario2"));    return Response.status(200).entity(users.toString()).build();  }}
```

También crearemos un POJO (Plain Old Java Object), una clase para definir el usuario:

```
package com;
import javax.xml.bind.annotation.XmlElement;import javax.xml.bind.annotation.XmlRootElement;
import org.json.JSONException;import org.json.JSONObject;
@XmlRootElementpublic class User {  @XmlElement(name = "username")  String username;
  public User() {  }
  public User(String username) {    this.username = username;  }
  @Override  public String toString() {    try {      return new JSONObject().put("username", username).toString();    } catch (JSONException e) {      return null;    }  }}
```

## Compilar el proyecto <a href="#compilar-el-proyecto" id="compilar-el-proyecto"></a>

Hacemos clic sobre el botón derecho sobre el proyecto y seleccionamos Maven > Update Project. Y le damos a Ok. Luego otra vez el botón derecho sobre la carpeta del proyecto y le damos a Run as > Maven Build (la opción número 5). En el popup que se nos abre en la pestaña Main y el campo Goal escribimos **clean install** y luego pulsamos sobre Run.

Si todo ha ido bien deberías ver un mensaje de éxito parecido a este:

```
[INFO] ------------------------------------------------------------------------[INFO] BUILD SUCCESS[INFO] ------------------------------------------------------------------------[INFO] Total time: 10.046 s[INFO] Finished at: 2016-12-28T17:35:36+01:00[INFO] Final Memory: 17M/132M[INFO] ------------------------------------------------------------------------
```

## Ejecutar el proyecto <a href="#ejecutar-el-proyecto" id="ejecutar-el-proyecto"></a>

Si ya tenemos instalado y configurado el servidor Tomcat para eclipse, podemos ir a la pestaña de Servers y en la instancia de **Tomcat Server at localhost** pulsamos el botón derecho y seleccionamos “Add and Remove…”

<img src="https://www.webtutoriales.com/_astro/step3.CAp42KHL_Z2wowDu.webp" alt="" height="537" width="511">

En la ventana que se abre movemos nuestra aplicación ApiRest de Available a Configured y le damos a Finish.

Ahora hay que configurar un web.xml para que el servidor tomcat. Crearemos un archivo web.xml dentro de la carpeta WebContent/WEB-INF y copiaremos el siguiente código XML:

```
<?xml version="1.0" encoding="UTF-8"?><web-app xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"  xmlns="http://java.sun.com/xml/ns/javaee" xmlns:web="http://java.sun.com/xml/ns/javaee/web-app_2_5.xsd"  xsi:schemaLocation="http://java.sun.com/xml/ns/javaee http://java.sun.com/xml/ns/javaee/web-app_3_0.xsd"  version="3.0">  <display-name>ApiRest</display-name>  <welcome-file-list>    <welcome-file>index.html</welcome-file>    <welcome-file>index.htm</welcome-file>    <welcome-file>index.jsp</welcome-file>    <welcome-file>default.html</welcome-file>    <welcome-file>default.htm</welcome-file>    <welcome-file>default.jsp</welcome-file>  </welcome-file-list>
  <servlet>    <servlet-name>Jersey Web Application</servlet-name>    <servlet-class>com.sun.jersey.spi.container.servlet.ServletContainer</servlet-class>    <load-on-startup>1</load-on-startup>  </servlet>  <servlet-mapping>    <servlet-name>Jersey Web Application</servlet-name>    <url-pattern>/*</url-pattern>  </servlet-mapping></web-app>
```

Para ejecutar la instancia del servidor pulsamos sobre el botón derecho del Tomcat y le damos a start. Al cabo de unos momentos ya podemos abrir el navegador y visitar la url [http://localhost](https://www.webtutoriales.com/articulos/2016/12/29/servicios-rest-con-java-usando-jax-rs-y-jersey/)

[/ApiRest/users/](https://www.webtutoriales.com/articulos/2016/12/29/servicios-rest-con-java-usando-jax-rs-y-jersey/). Si todo ha ido bien deberíamos ver un JSON con el siguiente contenido:

```
[  {    "username": "admin"  },  {    "username": "john"  },  {    "username": "usuario2"  }]
```

Como resumen la estructura de directorios debería quedar así:

```
ApiRest/---- src/-------- com/------------ User.java------------ UsersService.java---- WebContent/--------WEB-INF/------------web.xml---- pom.xml
```
