# Creación de Webservice SOAP mediante Anotaciones



Vamos a ver cuáles son los pasos a seguir para implementar un webservice SOAP utilizando la anotaciones que nos brinda la librería JAX-WS de Java. En el blog ya hemos explicado en algún post anterior cómo se creaba el esqueleto de un webservice SOAP, pero en el post actual vamos a ir un poco más allá y a tratar de explicar el uso de las anotaciones más importantes.

[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjzlEHbrWDZPgyY4QmPs0zz-tXyFCPH2PDOy4C_x1BJvxcbIvSiZEFUR7Xi2Zp8pQwRzK9wEI6BwTAbI_wj1CxJRwMA-aDwNsmmrnCQxJ2raq9j5Gct7vmOdCFq8llZ0N-rpVgq4GddJgo/w400-h226/Webservice+Anotaciones+SOAP+v5.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjzlEHbrWDZPgyY4QmPs0zz-tXyFCPH2PDOy4C_x1BJvxcbIvSiZEFUR7Xi2Zp8pQwRzK9wEI6BwTAbI_wj1CxJRwMA-aDwNsmmrnCQxJ2raq9j5Gct7vmOdCFq8llZ0N-rpVgq4GddJgo/s530/Webservice+Anotaciones+SOAP+v5.png)

&#x20;

Dicho lo anterior, toca concretar un poco y procedemos a enumerar las herramientas y tecnologías que vamos a usar para la creación del webservice.<br>

* IDE Eclipse&#x20;
* Java versión 8<br>
* Proyecto Maven<br>
* Servidor Tomcat
* Librería JAX-WS

&#x20;

### Creación de Webservice SOAP mediante Anotaciones

&#x20;

Dicho lo anterior, vamos a entrar en materia y comenzamos a enumerar los pasos necesarios para la creación de un webservice SOAP.

&#x20;

1º) Entramos en Eclipse y nos creamos un proyecto de tipo "Dynamic Web Project". Acto seguido, marcamos el proyecto y hacemos clic con el botón derecho. En el menú seleccionamos la opción CONFIGURE - CONVERT TO MAVEN PROJECT.&#x20;

En la ventana emergente "Maven POM" indicamos el nombre del ARTIFACT ID y del GROUP ID (esto es, del paquete raíz del proyecto, que en nuestro ejemplo será _com.universo.soap_). Pulsamos el botón FINISH.

Nos debería quedar un esqueleto de este tipo.<br>

[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjDsMbxcgkURRRZUGDUDuFnTSQ_6B9E4gWatCYVYMaiWVok26L5eP-PekVBDOgq7A_NpBSIsuuH1vJo5_L6AYP8FSvreWTvTfx-CUp-ShwwrbKn_o6bjQoOZwrK6t9KIpptCufQXmzkKu4/w338-h400/Webservice+Anotaciones+SOAP.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjDsMbxcgkURRRZUGDUDuFnTSQ_6B9E4gWatCYVYMaiWVok26L5eP-PekVBDOgq7A_NpBSIsuuH1vJo5_L6AYP8FSvreWTvTfx-CUp-ShwwrbKn_o6bjQoOZwrK6t9KIpptCufQXmzkKu4/s440/Webservice+Anotaciones+SOAP.png)<br>

<br>

2º) Editamos el fichero pom.xml y le añadimos las propiedades de Java 8. En mi caso realmente no me hacían falta, pues ya las tenía por defecto, pero quizás vosotros sí las necesitéis en vuestro proyecto. A continuación, tenemos que añadir la librería JAXWS-RT, que es la que nos permitirá implementar el webservice de este ejemplo.

El fichero pom.xml debería quedar del siguiente modo:

<br>

\<project xmlns="http://maven.apache.org/POM/4.0.0"

xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"

xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 https://maven.apache.org/xsd/maven-4.0.0.xsd">

&#x20; \<modelVersion>4.0.0\</modelVersion>

&#x20; \<groupId>com.universo.soap\</groupId>

&#x20; \<artifactId>WebserviceSoapApp\</artifactId>

&#x20; \<version>0.0.1-SNAPSHOT\</version>

&#x20; \<packaging>war\</packaging>

&#x20;

&#x20; \<properties>

&#x20;   \<java.version>1.8\</java.version>

&#x20;   \<maven.compiler.target>1.8\</maven.compiler.target>

&#x20;   \<maven.compiler.source>1.8\</maven.compiler.source>

&#x20; \</properties>

&#x20;

&#x20; \<dependencies>

&#x20;      \<dependency>

&#x20;          \<groupId>com.sun.xml.ws\</groupId>

&#x20;          \<artifactId>jaxws-rt\</artifactId>

&#x20;          \<version>2.3.2\</version>

&#x20;      \</dependency>

&#x20; \</dependencies>

&#x20;

&#x20; \<build>

&#x20;   \<plugins>

&#x20;     \<plugin>

&#x20;       \<artifactId>maven-compiler-plugin\</artifactId>

&#x20;       \<version>3.8.1\</version>

&#x20;       \<configuration>

&#x20;         \<source>1.8\</source>

&#x20;         \<target>1.8\</target>

&#x20;       \</configuration>

&#x20;     \</plugin>

&#x20;     \<plugin>

&#x20;       \<artifactId>maven-war-plugin\</artifactId>

&#x20;       \<version>3.2.3\</version>

&#x20;     \</plugin>

&#x20;   \</plugins>

&#x20; \</build>

\</project>

<br>

3º) A continuación, seleccionamos el proyecto y seleccionamos la opción MAVEN - UPDATE PROJECT. En la ventana de "Update Maven Project" que nos saldrá a continuación, pulsamos el botón ACEPTAR. Eclipse procederá a descargar las librerías indicadas en las dependencias de nuestro pom.xml y las dejará asociadas a nuestros proyecto.

Las librerías de nuestro "Maven Dependencies" deberían quedar algo así:

[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjDS2WEOU5P32_KwaV2Xb_38SpG0fffAQ6BCIrJ5OIYyL8mQR1npIbHgHwrQ1BbhoJ72Sya1cGd9zkrZbW0Ys9Yt4quzYgbC8WI_dL9Ep81oXRc8AUGhMyyG8OlEqg5XkpT-gNKX7hFwzM/w276-h400/Webservice+SOAP+v3.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjDS2WEOU5P32_KwaV2Xb_38SpG0fffAQ6BCIrJ5OIYyL8mQR1npIbHgHwrQ1BbhoJ72Sya1cGd9zkrZbW0Ys9Yt4quzYgbC8WI_dL9Ep81oXRc8AUGhMyyG8OlEqg5XkpT-gNKX7hFwzM/s646/Webservice+SOAP+v3.png)

&#x20;

Como se aprecia, ya se ha descargado la librería jaxws-rt-2.3.2.jar, que es la que nos permitirá implementar el webservice de nuestro ejemplo.

<br>

### Implementación de las clases del Webservice SOAP

<br>

4º) Nos creamos la clase servicio _HolaMundo.java_ dentro del paquete _com.universo.soap.server_. Esta clase es la que ejecutará la lógica del webservice.

<br>

// \*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*

package com.universo.soap.server;

&#x20;

import javax.jws.WebMethod;

import javax.jws.WebParam;

import javax.jws.WebResult;

import javax.jws.WebService;

import javax.jws.soap.SOAPBinding;

import javax.jws.soap.SOAPBinding.Style;

&#x20;

//http://localhost:8080/AnotacionSoapApp/ws/hola

@WebService(name="HolaMundoPortType",

&#x20;      targetNamespace="http://server.soap.universo.com/",

&#x20;      serviceName="HolaMundoService",&#x20;

&#x20;      endpointInterface="com.universo.soap.server.HolaMundo",

&#x20;      portName="HolaMundoPortName")

@SOAPBinding(style = Style.RPC)

public class HolaMundo {

&#x20;

&#x20;   @WebMethod

&#x20;   @WebResult(name ="saludo")

&#x20;   public String ciao(@WebParam(name ="nombre") String nombre) throws OperacionFault {

&#x20;     // Validacion de parametro

&#x20;     if (nombre == null || nombre.isEmpty()) {

&#x20;           BaseException be = new BaseException("5000", "Error", "Nombre requerido");

&#x20;           throw new OperacionFault("Nombre requerido", be);

&#x20;     }

&#x20;     // Respuesta

&#x20;     String respuesta = String.format("Ciao %s", nombre);

&#x20;       return respuesta;

&#x20;   }

&#x20; &#x20;

}

// \*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*

<br>

5º) A continuación, nos creamos la clase _OperacionFault.java_. Esta clase es la que gestionará los Fault generados por el webservice.

<br>

// \*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*

package com.universo.soap.server;

&#x20;

import javax.xml.ws.WebFault;

&#x20;

@WebFault(name="operationfault",

&#x20;      targetNamespace = "http://server.soap.universo.com/",

&#x20;      faultBean="com.universo.soap.server.BaseException")

public class OperacionFault extends Exception {

&#x20;   /\*\*

&#x20;      \*

&#x20;      \*/

&#x20;      private static final long serialVersionUID = 1L;

&#x20;    &#x20;

&#x20;      private BaseException be;

&#x20;

&#x20;      public OperacionFault(String mensaje, BaseException be) {

&#x20;       super(mensaje);

&#x20;     &#x20;

&#x20;       this.be = be;

&#x20;   }

&#x20;    &#x20;

&#x20;   public OperacionFault(String message, BaseException faultInfo, Throwable cause) {

&#x20;       super(message, cause);

&#x20;       this.be = be;

&#x20;   }

&#x20;    &#x20;

&#x20;   public BaseException getFaultInfo() {

&#x20;       return this.be;

&#x20;   }

&#x20; &#x20;

}

// \*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*

&#x20;

6º) Creamos la clase _BaseException.java_. Esta será la clase que definirá el contenido de las excepciones generadas por nuestro webservice.

&#x20;

// \*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*

package com.universo.soap.server;

&#x20;

public class BaseException {

&#x20;

&#x20;      private String errorID;

&#x20;      private String errorType;

&#x20;      private String errorDesc;

&#x20;    &#x20;

&#x20;      public BaseException(String errorID, String errorType, String errorDesc) {

&#x20;            this.errorID = errorID;

&#x20;            this.errorType = errorType;

&#x20;            this.errorDesc = errorDesc;

&#x20;      }

&#x20;    &#x20;

&#x20;      public String getErrorID() {

&#x20;            return errorID;

&#x20;      }

&#x20;      public void setErrorID(String errorID) {

&#x20;            this.errorID = errorID;

&#x20;      }

&#x20;      public String getErrorType() {

&#x20;            return errorType;

&#x20;      }

&#x20;      public void setErrorType(String errorType) {

&#x20;            this.errorType = errorType;

&#x20;      }

&#x20;      public String getErrorDesc() {

&#x20;            return errorDesc;

&#x20;      }

&#x20;      public void setErrorDesc(String errorDesc) {

&#x20;            this.errorDesc = errorDesc;

&#x20;      }

&#x20;    &#x20;

}

// \*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*

&#x20;

### Configuración del Webservice SOAP

&#x20;

7º) A continuación, nos creamos el fichero de configuración sun-jaxws.xml dentro de la carpeta WEB-INF de nuestro proyecto. En este fichero hay que indicar la ubicación del servicio que se debe ejecutar y el patrón de la URL en la que quedará publicado.

El contenido del xml será el siguiente:<br>

<br>

\<?xml version="1.0" encoding="UTF-8"?>

\<endpoints xmlns="http://java.sun.com/xml/ns/jax-ws/ri/runtime" version="2.0">

&#x20; \<endpoint

&#x20;    name="HolaWebService"

&#x20;    implementation="com.universo.soap.server.HolaMundo"

&#x20;    url-pattern="/ws/hola"/>

\</endpoints>

&#x20;

8º) Llegados a este punto, hay que modificar el fichero web.xml para indicar la configuración del JAXWSServlet. Habrá que incluir los apartados de \<listener>, \<servlet> y \<servlet-mapping>.

El contenido modificado de web.xml debería quedar algo así.<br>

&#x20;

\<?xml version="1.0" encoding="UTF-8"?>

\<web-app xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"

xmlns="http://xmlns.jcp.org/xml/ns/javaee"

xsi:schemaLocation="http://xmlns.jcp.org/xml/ns/javaee http://xmlns.jcp.org/xml/ns/javaee/web-app\_4\_0.xsd"

id="WebApp\_ID" version="4.0">

&#x20; \<display-name>WebserviceSoapApp\</display-name>

&#x20; \<welcome-file-list>

&#x20;   \<welcome-file>index.html\</welcome-file>

&#x20;   \<welcome-file>index.htm\</welcome-file>

&#x20;   \<welcome-file>index.jsp\</welcome-file>

&#x20;   \<welcome-file>default.html\</welcome-file>

&#x20;   \<welcome-file>default.htm\</welcome-file>

&#x20;   \<welcome-file>default.jsp\</welcome-file>

&#x20; \</welcome-file-list>

&#x20;

&#x20;      \<listener>

&#x20;            \<listener-class>

&#x20;                   com.sun.xml.ws.transport.http.servlet.WSServletContextListener

&#x20;            \</listener-class>

&#x20;      \</listener>

&#x20;

&#x20;      \<servlet>

&#x20;          \<servlet-name>JAXWSServlet\</servlet-name>

&#x20;          \<servlet-class>

&#x20;              com.sun.xml.ws.transport.http.servlet.WSServlet

&#x20;          \</servlet-class>

&#x20;      \</servlet>

&#x20;    &#x20;

&#x20;      \<servlet-mapping>

&#x20;          \<servlet-name>JAXWSServlet\</servlet-name>

&#x20;          \<url-pattern>/ws/\*\</url-pattern>

&#x20;      \</servlet-mapping>

&#x20;    &#x20;

\</web-app>

&#x20;

9º) Tras la inclusión de todos los ficheros anteriores, el proyecto debería quedar estructurado de la siguiente forma.

[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhUryxvhtlGkrGiPmCDMk88b3UlzkRBWDpubMuEy-3wOow6QmNNleYJQ62h8SniI_Hi92LRVqVtie_V0B7FArJ9viw2FQfm3AJxB26QKp1tcO5GaBBHQLFv_yfxWASP8fMK6EtmZiue2Z4/w268-h400/Webservice+Anotaciones+SOAP+v2.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhUryxvhtlGkrGiPmCDMk88b3UlzkRBWDpubMuEy-3wOow6QmNNleYJQ62h8SniI_Hi92LRVqVtie_V0B7FArJ9viw2FQfm3AJxB26QKp1tcO5GaBBHQLFv_yfxWASP8fMK6EtmZiue2Z4/s554/Webservice+Anotaciones+SOAP+v2.png)

\
&#x20;

### Publicación del Webservice SOAP

&#x20;

10º) A continuación, procedemos a arrancar el Tomcat y añadimos nuestro proyecto al servidor. Si hemos creado correctamente la aplicación, no deberíamos tener problemas de arranque.&#x20;

<br>

jul 05, 2021 6:57:17 PM com.sun.xml.ws.server.MonitorBase createRoot

INFORMACIÓN: Metro monitoring rootname successfully set to: com.sun.metro:pp=/,type=WSEndpoint,name=/AnotacionSoapApp-HolaMundoService-HolaMundoPortName

jul 05, 2021 6:57:18 PM com.sun.xml.ws.transport.http.servlet.WSServletDelegate \<init>

INFORMACIÓN: WSSERVLET14: inicializando el servlet de JAX-WS

jul 05, 2021 6:57:18 PM com.sun.xml.ws.transport.http.servlet.WSServletContextListener contextInitialized

INFORMACIÓN: WSSERVLET12: inicializando el listener de contexto de JAX-WS

jul 05, 2021 6:57:18 PM com.sun.xml.ws.transport.http.servlet.WSServletContextListener contextInitialized

INFORMACIÓN: WSSERVLET12: inicializando el listener de contexto de JAX-WS

jul 05, 2021 6:57:18 PM org.apache.coyote.AbstractProtocol start

INFORMACIÓN: Starting ProtocolHandler \["http-nio-8080"]

jul 05, 2021 6:57:18 PM org.apache.catalina.startup.Catalina start

INFORMACIÓN: Server startup in \[7.421] milliseconds

&#x20;

11º) De esta forma, nuestro servicio ha debido quedar publicado correctamente. Ahora debemos tener en cuenta que "_AnotacionSoapApp_" es el nombre de nuestro proyecto y que "_/ws/hola_" es el patrón URL que hemos establecido en el fichero _sun-jaxws.xml_. Por tanto, el endpoint en el que debemos buscar nuestro servicio será el siguiente:

http://localhost:8080/AnotacionSoapApp/ws/hola

<br>

Si ponemos dicho endpoint en un navegador, nos aparecerá la siguiente información (recordad, siempre y cuando el servicio esté correctamente publicado):

[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhKtcwIzovZLgzLnXh9g2Zf3lBkuZ26iBlqz4s3h1pFpctJefPw8NY99-I9mSBNfYHlivLtnPYSUdeEYC8gY_i3dpXqK7RRa255b1nz50HE1Y5tz0euRQ2Shrhb-nhx6pJUHlfGQqXh6Fs/w640-h344/Webservice+Anotaciones+SOAP+v3.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhKtcwIzovZLgzLnXh9g2Zf3lBkuZ26iBlqz4s3h1pFpctJefPw8NY99-I9mSBNfYHlivLtnPYSUdeEYC8gY_i3dpXqK7RRa255b1nz50HE1Y5tz0euRQ2Shrhb-nhx6pJUHlfGQqXh6Fs/s1920/Webservice+Anotaciones+SOAP+v3.png)\
&#x20;

Ahí tendremos la información acerca del endpoint del webservice.

| Punto Final              | Información                                         |
| ------------------------ | --------------------------------------------------- |
| 6K5BsLqrLJz5             | Hkg2VTKHanzS                                        |
| Nombre de Servicio\\:    | {http://server.soap.universo.com/}HolaMundoService  |
| Nombre de Puerto\\:      | {http://server.soap.universo.com/}HolaMundoPortName |
| Dirección\\:             | http://localhost:8080/AnotacionSoapApp/ws/hola      |
| WSDL\\:                  | http://localhost:8080/AnotacionSoapApp/ws/hola?wsdl |
| Clase de Implantación\\: | com.universo.soap.server.HolaMundo                  |

| Dirección\\:             | http://localhost:8080/AnotacionSoapApp/ws/hola      |
| ------------------------ | --------------------------------------------------- |
| WSDL\\:                  | http://localhost:8080/AnotacionSoapApp/ws/hola?wsdl |
| Clase de Implantación\\: | com.universo.soap.server.HolaMundo                  |

| Nombre de Servicio\\: | {http://server.soap.universo.com/}HolaMundoService  |
| --------------------- | --------------------------------------------------- |
| Nombre de Puerto\\:   | {http://server.soap.universo.com/}HolaMundoPortName |

&#x20;<br>

12º) Adicionalmente, podemos ver el contrato WSDL (formato basado en XML) de nuestro servicio SOAP accediendo al siguiente endpoint:

http://localhost:8080/AnotacionSoapApp/ws/hola?wsdl

<br>

Si ponemos dicho endpoint en un navegador, se mostrará lo siguiente:

[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEh2k9B5QF3g-FUJ9XocLCKwKV1IH_DGN9PFBHLBwrc3zW7_kyanBStWwJSUMDoYVaDyc6di3MCsTOV4LwUGnK8VFnw7UKtAT5lShgAci3-aD8VGwJbeV-LplVv6mHDDYIC3iLwl_63LRLQ/w640-h344/Webservice+Anotaciones+SOAP+v4.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEh2k9B5QF3g-FUJ9XocLCKwKV1IH_DGN9PFBHLBwrc3zW7_kyanBStWwJSUMDoYVaDyc6di3MCsTOV4LwUGnK8VFnw7UKtAT5lShgAci3-aD8VGwJbeV-LplVv6mHDDYIC3iLwl_63LRLQ/s1920/Webservice+Anotaciones+SOAP+v4.png)\
&#x20;

Como ya hemos explicado en el blog en ocasiones anteriores, el fichero WSDL es el que nos proporciona toda la información acerca de dónde está publicado nuestro servicio SOAP y con qué datos debe realizarse la invocación para obtener la respuesta esperada. Conocer el WSDL nos permite realizar su invocación desde cualquier proyecto externo.<br>

El contenido de nuestro WSDL es el siguiente:

\<definitions targetNamespace="http://server.soap.universo.com/" name="HolaMundoService">

\<types>

\<xsd:schema>

\<xsd:import namespace="http://server.soap.universo.com/" schemaLocation="http://localhost:8080/AnotacionSoapApp/ws/hola?xsd=1"/>

\</xsd:schema>

\</types>

\<message name="ciao">

\<part name="nombre" type="xsd:string"/>

\</message>

\<message name="ciaoResponse">

\<part name="saludo" type="xsd:string"/>

\</message>

\<message name="OperacionFault">

\<part name="fault" element="tns:operationfault"/>

\</message>

\<portType name="HolaMundoPortType">

\<operation name="ciao">

\<input wsam:Action="http://server.soap.universo.com/HolaMundoPortType/ciaoRequest" message="tns:ciao"/>

\<output wsam:Action="http://server.soap.universo.com/HolaMundoPortType/ciaoResponse" message="tns:ciaoResponse"/>

\<fault message="tns:OperacionFault" name="OperacionFault" wsam:Action="http://server.soap.universo.com/HolaMundoPortType/ciao/Fault/OperacionFault"/>

\</operation>

\</portType>

\<binding name="HolaMundoPortNameBinding" type="tns:HolaMundoPortType">

\<soap:binding transport="http://schemas.xmlsoap.org/soap/http" style="rpc"/>

\<operation name="ciao">

\<soap:operation soapAction=""/>

\<input>

\<soap:body use="literal" namespace="http://server.soap.universo.com/"/>

\</input>

\<output>

\<soap:body use="literal" namespace="http://server.soap.universo.com/"/>

\</output>

\<fault name="OperacionFault">

\<soap:fault name="OperacionFault" use="literal"/>

\</fault>

\</operation>

\</binding>

\<service name="HolaMundoService">

\<port name="HolaMundoPortName" binding="tns:HolaMundoPortNameBinding">

\<soap:address location="http://localhost:8080/AnotacionSoapApp/ws/hola"/>

\</port>

\</service>

\</definitions>

&#x20;

Una vez que tenemos implementado el webservice en el lado del servidor, ahora nos tocaría desarrollar en el lado del cliente el servicio que debe proceder a consumirlo. Para ello, veremos que resultará imprescindible conocer la estructura de su WSDL. Pero eso ya queda para otro post, que será la parte complementaria del que hemos publicado hoy.<br>

&#x20;

Pues nada, eso es todo lo que quería contar en relación con la creación de un Webservice donde se haga uso de diferentes anotaciones JAX-WS. En concreto, hemos visto en funcionamiento las anotaciones @WebService, @SOAPBinding y @WebFault, entre otras. Esto nos ayudará a tener más claro cuál es el alcance de cada una de ellas dentro de un servicio SOAP.<br>

Saludos.
