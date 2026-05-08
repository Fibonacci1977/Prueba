# ¿ Qué son los Servicios REST ?

Tabla de Contenidos



* [Servicios REST y Comunicación](https://www.arquitecturajava.com/servicios-rest/#Servicios_REST_y_Comunicacion)
* [Stateless](https://www.arquitecturajava.com/servicios-rest/#Stateless)
* [Neutralidad Tecnológica](https://www.arquitecturajava.com/servicios-rest/#Neutralidad_Tecnologica)
* [REST Recursos y Uniformidad](https://www.arquitecturajava.com/servicios-rest/#REST_Recursos_y_Uniformidad)
* [Servicios REST y verbos HTTP](https://www.arquitecturajava.com/servicios-rest/#Servicios_REST_y_verbos_HTTP)
* [Otros artículos relacionados](https://www.arquitecturajava.com/servicios-rest/#Otros_articulos_relacionados)

Cada día necesitamos más usar servicios REST . ¿Porque? .Porque cada día nos encontramos con una mayor necesidad de comunicar aplicaciones diferentes y compartir datos entre ellas. Nos guste o no nuestras aplicaciones dependen de otras que publican otra información que nosotros necesitamos.

### Servicios REST y Comunicación <a href="#h-servicios-rest-y-comunicacion" id="h-servicios-rest-y-comunicacion"></a>

Cuando trabajamos con servicios REST estamos trabajando con una arquitectura Cliente Servidor en la cual el servidor publica la información en formato de dato puro . Normalmente en formato JSON estos datos pueden ser accedidos por una aplicación cliente que se encargará de procesarlos y presentar el resultado en un interface de usuario a nuestro Cliente.

<figure><img src="https://www.arquitecturajava.com/wp-content/uploads/serviciosREST.png" alt="servicios REST" height="178" width="655"><figcaption></figcaption></figure>

### Stateless <a href="#h-stateless" id="h-stateless"></a>

Estos servicios no se encargan de mantener ningún tipo de estado entre peticiones y cada una de las peticiones es totalmente independiente de la siguiente. Al no mantener estado nos encontramos que se incrementa la escalabilidad de estos.

### Neutralidad Tecnológica <a href="#h-neutralidad-tecnologica" id="h-neutralidad-tecnologica"></a>

Otra de las grandes ventajas de los Servicios REST es su neutralidad tecnológica ya que permite a prácticamente cualquier tipo de cliente y de lenguaje conectarse a ellos.

<figure><img src="https://www.arquitecturajava.com/wp-content/uploads/clienterest.png" alt="REST y clientes" height="366" width="463"><figcaption></figcaption></figure>

El contenido de los servicios web REST ha se puede cachear de tal forma que una vez realizada la primera petición al servicio el resto puedan apoyarse en la cache si fuera necesario.

### REST Recursos y Uniformidad <a href="#h-rest-recursos-y-uniformidad" id="h-rest-recursos-y-uniformidad"></a>

Otro de los conceptos claves de los servicios REST es el uso URLs orientadas a recursos en donde cada una de ellas gestiona todas las operaciones que un recurso concreto soporta . Ejemplos de recursos pueden ser /facturas /clientes o /libros . Cada una de estas URLs gestiona las operaciones CRUD de cada uno de los recursos . Búsquedas ,inserciones , actualizaciones , borrados etc

<figure><img src="https://www.arquitecturajava.com/wp-content/uploads/facturasurls.png" alt="" height="140" width="340"><figcaption></figcaption></figure>

### Servicios REST y verbos HTTP <a href="#h-servicios-rest-y-verbos-http" id="h-servicios-rest-y-verbos-http"></a>

Para realizar estas operaciones se hace uso de los verbos clásicos del protocolo HTTP

* GET: Verbo que solicita información al servicio
* POST : Verbo que inserta información del servicio
* PUT : Verbo que actualiza la información del servicio
* DELETE : Verbo que borra la información del servicio

<figure><img src="https://www.arquitecturajava.com/wp-content/uploads/serviciosRESTVerbos.png" alt="" height="184" width="340"><figcaption></figcaption></figure>

### Consumiendo Servicios REST en Java

JAX-RS 2.0 (JSR 339) no solo especifica el API para construir un servicio web REST sino que también mejora la API del lado del cliente para facilitar el proceso de escritura de un cliente para un servicio REST.

#### API cliente de JAX-RS

El API del cliente JAX-RS, que es una API basada en Java para la comunicación fluida con los servicios Web REST. Este API estándar, también forma parte de Java EE 7 y está diseñado para que sea muy fácil de consumir un servicio Web expuesto a través del protocolo HTTP y permite a los desarrolladores implementar de forma concisa y eficiente soluciones del lado del cliente portátiles.

#### Resumen sobre el uso del cliente JAX-RS.

Podemos crear un cliente rest y relacionarlo a una URL de destino específico, con parámetros específicos utilizando los siguientes pasos:

Obtener una referencia de cliente mediante la clase `ClientBuilder:`

```bash
 Client client = ClientBuilder.newClient();
```

Bash

Especificar la URL destino del servicio REST utilizando el método `target()`:

```bash
 client.target("http://localhost:8080/myrestservice");
```

Bash

Manejar los parámetros de URL dinámica utilizando `path()` y `resolveTemplate()`:

```bash
 client.target(..).path("{id}").resolveTemplate("id", someId);
```

Bash

Utilice el método `request()` para iniciar la construcción de la solicitud seguido por uno de los métodos, por ejemplo, `post()`, `get()`:

```bash
 client.target(..).request().get();
```

Bash

Cada paso ofrece una variedad de posibles parámetros y opciones de configuración. Puedes consultar este recurso [https://docs.oracle.com/javaee/7/tutorial/jaxrs-client.htm](https://docs.oracle.com/javaee/7/tutorial/jaxrs-client.htm) para conocer más sobre el API.

#### Dependencias

Si estamos trabajando en un proyecto Java EE (7 ó superior) no tenemos que agregar dependencias adicionales. Esto es porque agregaste la dependencia de Java EE 7 en el `pom.xml` del proyecto.

Esto es:

```xml
<dependency>
            <groupId>javax</groupId>
            <artifactId>javaee-web-api</artifactId>
            <version><!--Version Java EE--></version>
            <scope>provided</scope>
  </dependency>
```

XML

En caso de estar trabajando en un proyecto que no sea Java EE (7 ó superior) tenemos que agregar las siguientes dependencias.

```xml
<dependency>
            <groupId>org.glassfish.jersey.core</groupId>
            <artifactId>jersey-client</artifactId>
            <version><!--version más reciente de jersey--></version>
</dependency>

<dependency>
            <groupId>org.glassfish.jersey.media</groupId>
            <artifactId>jersey-media-json-jackson</artifactId>
            <version><!--version más reciente de jersey--></version>
</dependency>
```

XML

`Nota:`\
JAX-RS es el API para la creación y consumo de servicios web y existen varias implementaciones de este API, entre ellas las dos más famosas son Jersey [https://jersey.java.net/documentation/latest/index.html](https://jersey.java.net/documentation/latest/index.html) y REST-Easy [http://resteasy.jboss.org/](http://resteasy.jboss.org/).

Usaremos Jersey en nuestro ejemplo.

```java

Client client = ClientBuilder.newClient();
String baseUri = "http://localhost:8080/jaxrs-basic-demo/rest";

//Consultar todos los paises    
Response resultAll = client.target(baseUri)
				          		.path("/paises/todos")
				          		.request(MediaType.APPLICATION_JSON)
				          		.get(Response.class);

  //Imprimir resultado
  System.out.println(resultAll.readEntity(String.class));


  //Consultar un Pais por una Id
  Response resultForId = client.target(baseUri)
                      .path("/paises/{id}")
                      .resolveTemplate("id", 1)
                      .request(MediaType.APPLICATION_JSON)
                      .get(Response.class);


  //Imprimir resultado
  System.out.println(resultForId.readEntity(String.class));

```

Java

Salida

```
#Todos

{"pais":[{"id":"1","nombre":"República Dominicana"},{"id":"2","nombre":"Venezuela"},{"id":"3","nombre":"Nicaragua"},{"id":"4","nombre":"Uruguay"},{"id":"5","nombre":"Haiti"}]}

#Por Id
{"id":"1","nombre":"República Dominicana"}

```

El ejemplo completo se encuentra aquí [https://github.com/ecabrerar/javaee7-firstcup/tree/master/jaxrs/jaxrs-basic-demo](https://github.com/ecabrerar/javaee7-firstcup/tree/master/jaxrs/jaxrs-basic-demo)

#### Referencias:

* [http://java.dzone.com/articles/whats-new-jax-rs-20](http://java.dzone.com/articles/whats-new-jax-rs-20)
* [http://www.infoq.com/news/2013/06/Whats-New-in-JAX-RS-2.0](http://www.infoq.com/news/2013/06/Whats-New-in-JAX-RS-2.0)

## Web Services con Java (JAX-WS)

<i class="fa-calendar-alt">:calendar-alt:</i> [19 diciembre, 2016](https://www.oscarblancarteblog.com/2016/12/19/web-services-con-java-jax-ws/) <i class="fa-user">:user:</i> [oblancarte](https://www.oscarblancarteblog.com/author/oblancarte/) <i class="fa-folder-open">:folder-open:</i> o

![ReflectionToStringBuilder](http://www.oscarblancarteblog.com/wp-content/uploads/2014/07/google-oracle-java1-150x150.jpg)Los Web Services cada vez son más indispensable a la hora de construir aplicaciones, debido a que ya casi cualquier aplicación empresarial, requiere integrarse o comunicarse con otra. Por este motivo Java ofrece la librería JAX-WS la cual es definida por la especificación [JSR 224](http://jcp.org/en/jsr/detail?id=224). La especificación remplace a la JAX-RCP, la cual era únicamente para llamadas a procedimientos remotos, lo cual es diferente a los Web Services.

&#x20;

Crear Web Services con Java es mucho más fácil de lo que pudiéramos creer, pues ya que tan solo es necesario anotar una clase, para que esta sea expuesta automáticamente como tal por medio del servidor de aplicaciones. Para demostrar esto, desarrollaremos un Servicio para consultar y crear Empleados.

&#x20;

Lo primero que tenemos que hacer, es crear una clase que queremos exponer como WebService, luego la tenemos que anotar con @WebService :

```
@WebService(serviceName = "EmployeeService", targetNamespace = "http://xmlns.oscarblancarte.com/services/v1/EmployeeService")
public class EmployeeServiceImpl
```

Las propiedades utilizadas son las siguientes:

* **serviceName**: Nombre del servicio, que será utilizado para crear la URL del endpoint.
* **targetNamespace**: Define el Namespace del servicio.

&#x20;

Basta decir que las propiedades serviceName  y targetNamespace  son opcionales, ya que, de no colocarlas, serán asignadas de forma automática, tomando el nombre de la clase y el paquete en que se encuentra respectivamente.

&#x20;

En segundo lugar, es necesario crear los métodos que serán expuestos como las operaciones del WebService, estos métodos, deben de ser anotados con @WebMethod , veamos cómo quedaría una clase WebService terminada:

```
package com.osb.jax.ws.services.interfaces;

import com.osb.jax.ws.services.types.Employee;
import java.util.*;
import javax.jws.*;

/**
 * @author Oscar Blancarte
 */
@WebService(serviceName = "EmployeeService", targetNamespace = "http://xmlns.oscarblancarte.com/services/v1/EmployeeService")
public class EmployeeServiceImpl {
    
    private static final List<Employee> EMPLOYEES = new ArrayList<>();
    
    @WebMethod
    @WebResult(name = "employee")
    public List<Employee> getEmployeeList(){
        return EMPLOYEES;
    }
    
    @WebMethod
    public boolean createEmployee(@WebParam(name = "employee") Employee employee){
        EMPLOYEES.add(employee);
        return true;
    }
}
```

&#x20;

La anotación @WebParam  es utilizado para personalizar el nombre del parámetro en el WSDL.

&#x20;

La definición de la clase Employee es la siguiente:

```
package com.osb.jax.ws.services.types;


/**
 * @author Oscar Blancarte
 */
public class Employee {
    
    private Long id;
    private String name;

    public Employee() {
    }
    
    public Employee(Long id, String name) {
        this.id = id;
        this.name = name;
    }
    
    public Long getId() {
        return id;
    }

    public void setId(Long id) {
        this.id = id;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }
    
    
}
```

&#x20;

Finalmente, solo serán necesario deployar en el servidor de aplicaciones nuestro proyecto, en este caso, estamos utilizando Wildfly 9, pero podrías utilizar cualquier servidor que sea de tu preferencia. Una vez deployado, podrás ver el servicio en la URL: [http://localhost:8080/JAX-WS-1.0-SNAPSHOT/EmployeeService?wsdl](http://localhost:8080/JAX-WS-1.0-SNAPSHOT/EmployeeService?wsdl).

&#x20;

Podemos probar el servicio con SOAP-UI para ver el servicio y las dos operaciones:

<img src="http://www.oscarblancarteblog.com/wp-content/uploads/2016/12/soapui.png" alt="Web Services con Java" height="113" width="228">

&#x20;

Observemos que tenemos dos operaciones:

* **createEmployee:** nos permite crear un nuevo Empleado
* **getEmployeeList:** obtener un listado de todos los Empleados registrados.

&#x20;

Primeo ejecutaremos el método **createEmployee**:

<img src="http://www.oscarblancarteblog.com/wp-content/uploads/2016/12/createEmployee.png" alt="Web Services con Java" height="271" width="872">

Con este paso, ya habremos creado un nuevo Empleado llamado Oscar Blancarte.

&#x20;

El segundo paso, será consultar los empleados con el método **getEmployeeList**:

<img src="http://www.oscarblancarteblog.com/wp-content/uploads/2016/12/getEmployeeList.png" alt="Web Services con Java" height="205" width="721">

&#x20;

Como vemos, crear Servicios Web es tan simple como anotar una simple clase y desplegarla en nuestro servidor de aplicaciones.

## Creando servicios REST con JAVA

Actualmente la gran mayoría de aplicaciones cuentan con, por lo menos, un servicio WEB. En los últimos tiempos se ha popularizado una nueva forma de crear y consumir servicios llamado [RESTful](https://blog.bi-geek.com/servicios-web-restful/). Este tipo de servicios ha tenido una gran acogida por su fácil uso y también por los tiempos de respuesta cuando se consumen estos. Dada esta pequeña introducción vamos al grueso del asunto y para ello vamos a utilizar las siguientes herramientas:

1. Eclipse 2018-09 o superior.
2. Maven 3.5.4
3. Jersey 2.27
4. JAXB 2.3.1

### Creando el servicio WEB

Vamos a crear una aplicación WEB y para ello escoge la opción haciendo clic derecho, **New -> Other… -> WEB -> Dynamic WEB Project.** Selecciona la opción **Next**.

<figure><img src="https://soloenbinario.wordpress.com/wp-content/uploads/2019/07/1_0-crearproyectoweb.png?w=531" alt="" height="509" width="531"><figcaption></figcaption></figure>

Ahora dale un nombre a tu aplicación WEB y selecciona la opción **Next**.

<figure><img src="https://soloenbinario.wordpress.com/wp-content/uploads/2019/07/1_1-crearproyectoweb.png?w=529" alt="" height="777" width="529"><figcaption></figcaption></figure>

En la siguiente pantalla no es necesario configurar nada por lo que puedes seleccionar la opción **Next**.

<figure><img src="https://soloenbinario.wordpress.com/wp-content/uploads/2019/07/1_2-crearproyectoweb.png?w=529" alt="" height="778" width="529"><figcaption></figcaption></figure>

En esta pantalla selecciona la opción **Genérate web.xml deployment descriptor**. Es importante que lo selecciones porque en este archivo de configuración vamos definir el API REST y también cuales son las clases que se encargan de publicar los servicios que vamos a definir. Seleccionadas las opciones importantes, ahora selecciona la opción **Finish**.

<figure><img src="https://soloenbinario.wordpress.com/wp-content/uploads/2019/07/1_3-crearproyectoweb.png?w=529" alt="" height="776" width="529"><figcaption></figcaption></figure>

### Configurando Maven

Has clic derecho sobre tu aplicación WEB recientemente creada y selecciona la opción **Configure -> Convert to Maven Project…**

<figure><img src="https://soloenbinario.wordpress.com/wp-content/uploads/2019/07/2_0-convertiramaven.png?w=1024" alt="" height="640" width="1024"><figcaption></figcaption></figure>

En la ventana que aparece puedes configurar los datos que aparecen allí, te recomiendo que el packaging no lo modifiques. Luego, selecciona la opción **Finish**.

<figure><img src="https://soloenbinario.wordpress.com/wp-content/uploads/2019/07/2_1-creacionpom.png?w=532" alt="" height="424" width="532"><figcaption></figcaption></figure>

### Configuración del POM

Ahora vamos a realizar lo siguiente:

1. Vamos a importar las dependencias necesarias para que los servicios WEB funcionen sin problemas, y
2. vamos a configurar el nombre del servicio WEB.

Las dependencias que te recomiendo para la configuración de un servicio WEB RESTful son:

* Glassfish Jersey Core Server.
* Glassfish Jersey Containers Servlet.
* Glassfish Jersey Inject HK2.
* Glassfish Jersey Media JSON Jackson.
* JAXB.

Estas dependencias las puedes encontrar en la pagina [MVNRepository](http://www.mvnrepository.com/), sin embargo aquí te los dejo (Recuerda que el siguiente bloque debe ir después de la etiqueta **\<build>\</build>**):

```
<dependencies>
    <dependency>
        <groupId>org.glassfish.jersey.core</groupId>
	<artifactId>jersey-server</artifactId>
	<version>2.27</version>
    </dependency>
    <dependency>
	<groupId>org.glassfish.jersey.containers</groupId>
	<artifactId>jersey-container-servlet</artifactId>
	<version>2.27</version>
    </dependency>
    <dependency>
	<groupId>org.glassfish.jersey.inject</groupId>
	<artifactId>jersey-hk2</artifactId>
	<version>2.27</version>
    </dependency>
    <dependency>
	<groupId>org.glassfish.jersey.media</groupId>
	<artifactId>jersey-media-json-jackson</artifactId>
	<version>2.27</version>
    </dependency>
    <dependency>
	<groupId>javax.xml.bind</groupId>
	<artifactId>jaxb-api</artifactId>
	<version>2.3.1</version>
    </dependency>
</dependencies>
```

### Creación del servicio WEB

Vamos ahora con la creación de la clase y los métodos de consumo. Lo primero que vas a hacer es crear el package y luego vas a crear la clase que será el servicio WEB como tal. Luego vamos a agregar algunas anotaciones para que nuestro API REST funcione. Para este ejercicio vamos a crear métodos de consumo de tipo **GET** y tipo **POST** que retornaran los siguiente:

1. Datos de tipo String.
2. Datos de tipo XML.
3. Datos de tipo JSON.
4. Objetos
5. Objetos de tipo Response.

Empecemos. Creada la clase vamos a agregarle encima del nombre de la misma la anotación **@Path**.

<figure><img src="https://soloenbinario.wordpress.com/wp-content/uploads/2019/07/4_1-anotacionpath.png?w=223" alt="" height="57" width="426"><figcaption></figcaption></figure>

#### Método que retorna un objeto de tipo String

Dentro de la clase crea una método que retorne datos de tipo String. Cuando lo hayas creado, agrégale las anotaciones **@GET**, **@Path** y **@Produces** quedando de la siguiente manera:

<figure><img src="https://soloenbinario.wordpress.com/wp-content/uploads/2019/07/4_2-metodostring.png?w=229" alt="" height="152" width="397"><figcaption></figcaption></figure>

#### Método que retorna información en formato XML

Crea un método que retorne datos de tipo XML. Lo que vas a realizar a continuación es crear un objeto que va a ser retornado por el método en cuestión. Este objeto debe tener lo siguiente para que el API REST lo transforme a XML:

1. Anotaciones JAXB.
2. Un constructor vacío.

En ese orden de ideas, crea tu clase la cual deberá quedar como el siguiente ejemplo:

<figure><img src="https://soloenbinario.wordpress.com/wp-content/uploads/2019/07/4_3_1-metodoxmlobjetojaxb.png?w=352" alt="" height="582" width="585"><figcaption></figcaption></figure>

Cuando hayas creado el objeto, crea tu método y agrega las anotaciones **@GET**, **@Path**, **@Produces** y dentro de esta última anotación agrega el MediaType **APPLICATION\_XML** quedando de la siguiente manera:

<figure><img src="https://soloenbinario.wordpress.com/wp-content/uploads/2019/07/4_3_2-metodoxml.png?w=279" alt="" height="204" width="441"><figcaption></figcaption></figure>

#### Método que retorna información en formato JSON

Crea un método que retorne datos en formato JSON. La creación es bastante similar al método que retorna datos en formato XML, lo único que cambia es el tipo de MediaType que es **APPLICATION\_JSON**. Entonces, el resultado deberá ser el siguiente:

<figure><img src="https://soloenbinario.wordpress.com/wp-content/uploads/2019/07/5_0-metodojson.png?w=286" alt="" height="197" width="434"><figcaption></figcaption></figure>

#### Método con paso de parámetros mediante PathParam

Crea un método que va a recibir un parámetro por la URL. En este caso será un parámetro que reciba uno o varios argumentos y por cada argumento tienes que anteceder la anotación **@PathParam(\[nombre\_parametro])** donde **nombre\_parametro** será el alias del parámetro que debe ser parte de la URI, así:

<figure><img src="https://soloenbinario.wordpress.com/wp-content/uploads/2019/07/5_1-metodojsonpathparam.png?w=417" alt="" height="171" width="552"><figcaption></figcaption></figure>

Como te comenté, en la anotación **@PathParam** colocamos el alias **p**. Si te das cuenta este alias aparece como parte de la URI dentro de la anotación **@Path**. Entonces, cuando realices el consumo del servicio WEB lo que debe ir en **{p}** es el dato que vas a pasar al método del servicio REST.

#### Método con paso de parámetros mediante QueryParam

Un método con paso de parámetros mediante **QueryParam** sería, por ejemplo, [**http://localhost:8080/SampleREST/rest/WebServiceRest/bienvenida/json\_qp?p=dato**](http://localhost:8080/SampleREST/rest/WebServiceRest/bienvenida/json_qp?p=dato). De este modo, crea un método que retorne un objeto y que este sea retornado en formato JSON y luego agrégale la cantidad de argumentos que necesites pasarle. A cada uno de ellos debes anteponerle la anotación **@QueryParam** que entre paréntesis debe ir el nombre del parámetro que será enviado por Query String. Es decir, que en la URL que mencioné anteriormente estamos enviando un dato a la variable **p**, en la anotación **@QueryParam** debe ir el dato llamado **p**, quedando de la siguiente manera:

<figure><img src="https://soloenbinario.wordpress.com/wp-content/uploads/2019/07/5_2-metodojsonqueryparam.png?w=432" alt="" height="166" width="563"><figcaption></figcaption></figure>

#### Método POST

En la creación de métodos **POST** las variaciones con respecto a un método de tipo **GET** son que, debemos decirle qué tipo de información va a consumir, el tipo de información que va a producir y el retorno será un dato de tipo **Response**. En este orden de ideas créate un método con la anotación **@POST** y la anotación **@Consumes** la cual va a aceptar datos en formato JSON. Como parámetros al método puedes pasarle un objeto y el dato de retorno un objeto de tipo **Response**. De resto las anotaciones **@Path** y **@Produces** siempre van a ser las más comunes en todos los métodos de un servicio REST. El método debería quedar como este:

<figure><img src="https://soloenbinario.wordpress.com/wp-content/uploads/2019/07/5_3-metodopost.png?w=423" alt="" height="192" width="577"><figcaption></figcaption></figure>

### Creando un cliente para el consumo de los servicios

Con pocas líneas de código se pueden crear clientes de consumo de servicios WEB REST en JAVA. Vamos a crear un cliente en JAVA SE para que veas el funcionamiento.

#### Creando el proyecto

En Eclipse, haz clic derecho y selecciona la opción **New -> Other…**

<figure><img src="https://soloenbinario.wordpress.com/wp-content/uploads/2019/07/5_1-creacionclienterest_1.png?w=1024" alt="" height="640" width="1024"><figcaption></figcaption></figure>

Selecciona la opción **Java Project**.

<figure><img src="https://soloenbinario.wordpress.com/wp-content/uploads/2019/07/5_2_creacionclienterest_2.png?w=1024" alt="" height="640" width="1024"><figcaption></figcaption></figure>

Ahora selecciona un nombre para tu nuevo cliente REST y luego selecciona la opción **Finish**.

<figure><img src="https://soloenbinario.wordpress.com/wp-content/uploads/2019/07/5_3_creacionclienterest_3.png?w=1024" alt="" height="640" width="1024"><figcaption></figcaption></figure>

Una vez se haya terminado la creación del cliente, has clic derecho en él y selecciona la opción **Configure -> Convert to Maven Project**.

<figure><img src="https://soloenbinario.wordpress.com/wp-content/uploads/2019/07/5_4_convertiramaven.png?w=750" alt="" height="809" width="750"><figcaption></figcaption></figure>

En la nueva ventana que aparece, lo puedes dejar como lo sugiere el asistente y presionas la opción **Finish**.

Las dependencias que puede usar para la creación de los métodos cliente son:

```
<dependencies>
    <dependency>
        <groupId>org.glassfish.jersey.core</groupId>
        <artifactId>jersey-client</artifactId>
        <version>2.27</version>
    </dependency>
    <dependency>
        <groupId>org.glassfish.jersey.inject</groupId>
	<artifactId>jersey-hk2</artifactId>
	<version>2.27</version>
    </dependency>
    <dependency>
	<groupId>javax.xml.bind</groupId>
	<artifactId>jaxb-api</artifactId>
	<version>2.3.1</version>
    </dependency>
    <dependency>
	<groupId>com.googlecode.json-simple</groupId>
	<artifactId>json-simple</artifactId>
	<version>1.1.1</version>
    </dependency>
</dependencies>
```

#### Creación de la clase cliente

En la carpeta **src** has clic derecho y selecciona la opción **New -> Class**.

<figure><img src="https://soloenbinario.wordpress.com/wp-content/uploads/2019/07/5_5_creacionclasecliente.png?w=528" alt="" height="755" width="528"><figcaption></figcaption></figure>

En la nueva ventana que aparece selecciona un paquete y luego Escribe el nombre de la clase. Si el paquete que escribiste no existe, no hay problema. El asistente lo crea automáticamente. Ahora Selecciona la opción **Finish**.

<figure><img src="https://soloenbinario.wordpress.com/wp-content/uploads/2019/07/5_6_creacionclasecliente2.png?w=538" alt="" height="638" width="538"><figcaption></figcaption></figure>

Ahora vamos a crear los siguientes métodos que van a consumir cada uno de las funciones que creamos para el servicio REST. Haciendo recuento, los métodos son:

1. Método para retornar datos de tipo String.
2. Método para retornar datos de tipo XML.
3. Método para retornar datos de tipo JSON.
4. Método para retornar objetos de tipo Response.

Y los tipos de consumo son:

1. Get
2. Post
3. QueryParam
4. PathParam

**Declarando las instancias para el consumo del servicio**

Empieza con crear una instancia de tipo Client. como aparece a continuación:

<figure><img src="https://soloenbinario.wordpress.com/wp-content/uploads/2019/07/5_10_creacioninstanciaclient.png?w=325" alt="" height="122" width="541"><figcaption></figcaption></figure>

Como puedes observar en la imagen anterior, puedes crear una instancia para toda la clase o bien puedes crear la instancia en cada método donde la vayas a utilizar. La elección es tuya.

**Consumiendo datos de tipo XML, JSON y String**

¿Por qué este apartado abarca tres tipos de datos diferentes? Resulta que lo que vas a ver a continuación es el consumo de servicios de datos de tipo String, JSON y XML con las mismas líneas de código. Es decir que lo único que cambia son los tipos de retorno y las URIs de los servicios WEB. Así pues esta son las líneas de código que deberías usar para consumir los servicios retornando datos String, XML y JSON:

<figure><img src="https://soloenbinario.wordpress.com/wp-content/uploads/2019/07/5_11_stringjsonxml.png?w=804" alt="" height="143" width="804"><figcaption></figcaption></figure>

En esta instancias lo que debes cambiar para este ejemplo es el **target**, el **request**, el **accept** y el **get**. En conclusión los métodos quedarían construidos de la siguiente manera:

<figure><img src="https://soloenbinario.wordpress.com/wp-content/uploads/2019/07/5_12_metodosstringjsonxml.png" alt="" height="508" width="810"><figcaption></figcaption></figure>

**Consumiendo métodos Path Param**

El consumo de este tipo de servicios es muy similar al que vimos para consumir datos de tipo String, JSON y XML. Lo único que debemos agregar es el método **path()** después del método **target()** donde va la URI a consumir, quedando de la siguiente manera:

<figure><img src="https://soloenbinario.wordpress.com/wp-content/uploads/2019/07/5_7_jsonpathparam.png?w=890" alt="" height="202" width="890"><figcaption></figcaption></figure>

**Consumiendo métodos Query Param**

Exactamente igual que consumir métodos de tipo Path Param, así son los que se pasan datos por Query String. Después del método **target()** agrega el método **queryParam()** en el cual el primer argumento es el nombre de la variable Query String y en el segundo argumento colocas el valor para la variable. Recuerda que el nombre de la variable debe ser exactamente igual al que definiste en el método del servicio WEB. Así quedaría:

<figure><img src="https://soloenbinario.wordpress.com/wp-content/uploads/2019/07/5_8_jsonqueryparam.png?w=976" alt="" height="210" width="976"><figcaption></figcaption></figure>

**Consumiendo métodos POST**

Quizá este puede ser el método al cual toca agregarla un poco mas de líneas de código. Pero a la final es un código bastante sencillo de digerir.

<figure><img src="https://soloenbinario.wordpress.com/wp-content/uploads/2019/07/5_9_crearsaludo.png?w=897" alt="" height="256" width="897"><figcaption></figcaption></figure>

Como te puedes dar cuenta se necesita crear lo siguiente:

1. Crear una nueva instancia del objeto que vas a enviar.
2. Luego creamos una instancia de tipo Client.
3. Crear una instancia de tipo WebTarget la cual va a recibir la URI del método del servicio a consumir.
4. Crear una instancia de tipo Builder en la cual vamos a solicitar que el servicio nos retorne la información en formato JSON.
5. Crear una instancia de tipo Response en donde vamos a pasar como parámetro el objeto que instanciaste en el punto No . 1.

Como pudiste observar, entender y practicar a lo largo de este POST, la creación de servicios WEB REST es bastante sencilla por lo cual a futuro no tendrás tanto problema cuando empieces a crearlos en forma.

Espero que este contenido haya sido de gran ayuda para ti. El código fuente de estos ejercicios los puedes encontrar en los siguientes enlaces:

* Servicio REST: [https://github.com/elle184/ScriptsJAVA/tree/master/SampleREST](https://github.com/elle184/ScriptsJAVA/tree/master/SampleREST)
* Cliente del servicio REST: [https://github.com/elle184/ScriptsJAVA/tree/master/SampleRestClient](https://github.com/elle184/ScriptsJAVA/tree/master/SampleRestClient)

Que tengas muchos éxitos y buena programación.

## Crea Servicio REST con JAVA

Posted on [July 4, 2022](https://www.ingeniusworlds.com/crea-servicio-rest-con-java/) by [Polivio Onofa](https://www.ingeniusworlds.com/author/onofapolivio/)[![api\_java\_tomcat\_feature\_image](https://www.ingeniusworlds.com/wp-content/uploads/2022/07/api_java_tomcat_feature_image.jpg)](https://www.ingeniusworlds.com/crea-servicio-rest-con-java/)04\
Jul

> Seguro has trabajado con servicios web utilizando el protocolo Soap en Java , pero en esta ocasión quiero explicar como crear un servicio Web utilizando REST la transferencia de estado representacional, con Java y Tomcat como servidor.

#### JAVA VERSIONES

Para realizar el proyecto estaremos trabajando con la versión de JAVA 1.8.033, en este caso puedes descargar el SDK (Librerías completas de JAVA) o el JRE(De producción o las necesarias para que funcionen los ejecutables)

#### INSTALACIÓN

Si estamos en un ambiente de Windows, recomendaría utilizar el msi, o instalador para que instales el JAVA luego  de instalarlo verifica si lo tienes funcionando como variable de entorno para esto puedes acceder a tu Línea de comandos y colocar java -version.

![servidor\_rest\_java\_tomcat\_java\_version](https://www.ingeniusworlds.com/wp-content/uploads/2022/06/servidor_rest_java_tomcat_java_version.jpg)

Si no encuentra el comando entonces tenemos que configurar para eso ingresamos a las variables de entorno puede ser desde Mi PC – Propiedades – Configuración avanzada del sistema – Opciones avanzadas – Variables de entorno.

En ese lugar buscamos la variable path y ahí colocamos la ruta del JRE descargado que apunte a la carpeta BIN.

![servidor\_rest\_java\_tomcat\_path\_environment\_variable](https://www.ingeniusworlds.com/wp-content/uploads/2022/06/servidor_rest_java_tomcat_path_environment_variable.jpg)

También agreguemos como nueva variable una llamada JAVA\_HOME y agreguemos la ruta a nuestro BIN. Con estas configuraciones reiniciamos la línea de comandos y ejecutamos java -version.

#### ECLIPSE

Como IDE para desarrollar estaremos utilizando un IDE que sea compatible con nuestra versión de JAVA o JRE, en este caso puede ser el Clásico, Juno o Web, eso queda a decisión del que mas se ajusten pero es importante que utilice la versión del JRE para el proyecto.

#### LIBRERÍAS

Para poder crear los servicios utilizaremos las siguientes librerías:

**JERSEY**

Utilizaremos la especificación [JAX-RS](https://github.com/jax-rs) para implementar los servicios REST en JAVA para esto descargaremos la librería Jersey [JAX-RS 2.5 RI Bundle.](https://eclipse-ee4j.github.io/jersey/)

**JACKSON PARSE API**

Para utilizar poder Utilizar comunicación con JSON podemos utilizar la librería Jackson API, ya que Jersey no tiene incluido. Para esto debemos descargar los siguientes paquetes:

![servidor\_rest\_java\_tomcat\_jackson\_libraries\_json](https://www.ingeniusworlds.com/wp-content/uploads/2022/06/servidor_rest_java_tomcat_jackson_libraries_json.jpg)

**IMPLEMENTANDO LAS LIBRERÍAS**

Ahora para configurar las librerías en nuestro eclipse, vamos a agregar como librerías al entorno para esto nos dirigimos al menú:

_Window – Preferences – Java – Build Path_.

![servidor\_rest\_java\_tomcat\_configure\_libraries](https://www.ingeniusworlds.com/wp-content/uploads/2022/06/servidor_rest_java_tomcat_configure_libraries.jpg)

Ahora presionamos en Nueva y vamos a colocarle el nombre JAX-RS-Jersey-Api. Dentro de esta vamos a ir agregando como librerías externas cada .jar que tenemos en las siguientes carpetas:

lib

ext

api.

![servidor\_rest\_java\_tomcat\_jersey\_add\_libraries](https://www.ingeniusworlds.com/wp-content/uploads/2022/06/servidor_rest_java_tomcat_jersey_add_libraries.jpg)

Lo mismo vamos a realizar con la librería Jackson, le colocaremos el nombre Jackson-Parse-Api y agregamos todos los .jar que nos descargamos.

![servidor\_rest\_java\_tomcat\_jackson\_add\_libraries](https://www.ingeniusworlds.com/wp-content/uploads/2022/06/servidor_rest_java_tomcat_jackson_add_libraries.jpg)

**TOMCAT**

Ahora configuremos nuestro servidor, lo realizaremos con Tomcat que nos permite colocar aplicaciones ligeras rápidamente podemos revisar todas sus características en el siguiente [aquí](https://tomcat.apache.org/). En este caso utilizaremos la versión 7 que es compatible con el JRE que estamos utilizando.

El proceso es buscar la versión que vamos a utilizar nos descargamos y seguido de esto la descomprimimos en una carpeta que pueden llamarle c:/tomcat .

![servidor\_rest\_java\_tomcat\_path\_tomcat](https://www.ingeniusworlds.com/wp-content/uploads/2022/06/servidor_rest_java_tomcat_path_tomcat.jpg)

En esta carpeta estarán todas las configuraciones de nuestro servidor, podemos editar archivos de configuración para que el tomcat seleccione que JRE utilizar pero de momento si tenemos instalado 1 solo JRE como lo hicimos utilizará ese para arrancar ahora realizamos las pruebas, ingresemos a línea de comandos a la ruta de nuestro tomcat/bin/ y lo iniciamos con startup.bat start.

![servidor\_rest\_java\_tomcat\_start\_tomcat](https://www.ingeniusworlds.com/wp-content/uploads/2022/06/servidor_rest_java_tomcat_start_tomcat.jpg)

Como podemos ver si no tenemos ningún problema nos abrirá una nueva pantalla y nos mostrará el mensaje _Server startup in 6017 ms_. Con esto podemos ver que ya nuestro server esta ejecutándose.

Ahora configuremos esto dentro de nuestro Eclipse vamos a la opción _Window – Preferences – Server – Runtime Environments_, aquí podemos agregar nuestro nuevo servidor. Para esto presionamos Nuevo.

![servidor\_rest\_java\_tomcat\_eclipse\_server\_configuration](https://www.ingeniusworlds.com/wp-content/uploads/2022/06/servidor_rest_java_tomcat_eclipse_server_configuration.jpg)

Presionamos Add, y seleccionamos la versión de Tomcat y luego de esto el JRE que utilizamos y lo agregamos. Ahora ya tendríamos con esto nuestro servidor dentro de Eclipse. Que ventajas nos trae esto:

_1- Podemos depurar nuestro proyecto._

_2. Podemos enviar a consola mensajes para ver como está funcionando todo._

Bueno en resumen podemos saber que pasa y evitamos estar publicando el proyecto para cada prueba y perder tiempo.

![servidor\_rest\_java\_tomcat\_eclipse\_server\_tomcat\_version](https://www.ingeniusworlds.com/wp-content/uploads/2022/06/servidor_rest_java_tomcat_eclipse_server_tomcat_version.jpg)

**INICIANDO EL PROYECTO WEB**

Ahora podemos comenzar con nuestro proyecto le colocaremos cualquier nombre RestServices por ejemplo:

![servidor\_rest\_java\_tomcat\_new\_dynamic\_web\_project](https://www.ingeniusworlds.com/wp-content/uploads/2022/06/servidor_rest_java_tomcat_new_dynamic_web_project.jpg)

Ahora vamos a crearnos un paquete lo llamaremos _com.restservice.api_ en el cual agregaremos nuestras clases necesarias para el proyecto.

Dentro de este paquete crearemos una clase que nos ayudará haciendo la inyección de las variables necesarias para utilizar Jersey.

En esta clase utilizaremos la anotación @ApplicationPath que nos especificará la url del servicio llamemos a la clase StartJerseyMainClass.

![servidor\_rest\_java\_tomcat\_error\_class\_resource\_config](https://www.ingeniusworlds.com/wp-content/uploads/2022/06/servidor_rest_java_tomcat_error_class_resource_config.jpg)

Si nos presenta errores es porque no tenemos asociadas las librerías a nuestro proyecto recordemos que les configuramos global a nuestro entorno ahora tenemos que utilizarlas. Damos click derecho sobre nuestro proyecto y nos dirigimos a propiedades al ingresar a la pantalla vamos a _Java Build Path – Add Library_.

![servidor\_rest\_java\_tomcat\_add\_libraries\_to\_project](https://www.ingeniusworlds.com/wp-content/uploads/2022/06/servidor_rest_java_tomcat_add_libraries_to_project.jpg)

Presionamos en User Library y agregamos las 2 librerías que configuramos anteriormente.

![servidor\_rest\_java\_tomcat\_add\_libraries\_to\_project\_b](https://www.ingeniusworlds.com/wp-content/uploads/2022/06/servidor_rest_java_tomcat_add_libraries_to_project_b.jpg)

Listo con eso ya tenemos nuestras librerías en el proyecto el código de nuestra primera clase sería:

```
package com.restservice.api;import javax.ws.rs.ApplicationPath;import org.glassfish.jersey.media.multipart.MultiPart;
import org.glassfish.jersey.media.multipart.MultiPartFeature;
import org.glassfish.jersey.server.ResourceConfig;@ApplicationPath("apiservices")
public class StartJerseyMainClass extends ResourceConfig {public StartJerseyMainClass() {packages("com.fasterxml.jackson.jaxrs.json");packages("com.restservice.api");}
}
```

Ahora vamos a crear una nueva clase la cual contendrá nuestros servicios vamos a realizar la prueba una clase con un método del tipo GET, la llamaremos First.java. Y le agregamos el siguiente código.

```

package com.restservice.api;import javax.ws.rs.GET;
import javax.ws.rs.Path;
import javax.ws.rs.PathParam;
import javax.ws.rs.Produces;
import javax.ws.rs.core.MediaType;@Path("first")
public class First {public First(){}@GET@Path("/{name}")@Produces(MediaType.APPLICATION_JSON)public String sayHello(@PathParam("name") String name) {return "Hello World From Jersey Api: "+ name;}}
```

Ahora podemos probar nuestra api la url que necesitamos utilizar es:

http://localhost:8080/RestServices/apiservices/first/polo

Le adjuntamos un nombre al final que es la manera en la que recibiríamos un parámetro y vamos a devolver como resultado ese texo. Para esto ejecutemos nuestro servidor en Eclipse y también podemos dar clic derecho sobre la clase principal y presionar _Run On Server_ esto nos abrirá la consola y podemos ir observando el comportamiento de nuestro proyecto.

![servidor\_rest\_java\_tomcat\_test\_service](https://www.ingeniusworlds.com/wp-content/uploads/2022/06/servidor_rest_java_tomcat_test_service.jpg)

Listo con eso tenemos nuestro servicio Web Rest con Java y Tomcat funcionando tomar en cuenta que se puede recibir parámetros tipo Post y en la url, una nota importante en las pruebas muchas veces el Browser coloca en la ruta https a tu localhost y no va funcionar tu servicio o te mostrará el mensaje Http Header Parsing Error. Espero te sirva esta información si necesitas ayuda o soporte en tus proyectos [contáctanos](https://www.ingeniusworlds.com/contacto).



## JAX-RS Servicios RESTFull en Java



Vamos a construir un servicio REST utilizando los estandares de JAX-RS . Para ello lo primero que tenemos que hacer es comenzar a conocer las distintas anotaciones que el estandar define.

<figure><img src="../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

**@GET :**&#x45;sta anotación marca un método y define  una operación GET  .Es similar a cuando realizamos una petición HTTP GET y solo debe usarse en el caso que de queramos leer información .Nunca a la hora de escribir o modificar el estado del recurso al que estemos accediendo.

**@POST :**&#x45;sta anotación marca un método y define  una operación POST .Es similar a cuando realizamos una petición HTTP POST y se usa para añadir un recurso o modificar un recurso existente.

**@DELETE :**&#x45;sta anotación marca un método y define  una operación DELETE .Como su nombre indica se trata de eliminar un recurso del servidor . No siempre se usa ya que redirecciona a traves de POST cuando trabajamos con HTML plano.

**@PUT :** Esta anotación se encargar de reemplazar un recurso del servidor y como en el caso anterior suele redireccionarse a traves de POST.

**@Path :**&#x45;sta anotación es distinta a las anteriores y se encarga de definir un punto de entrada al servicio.  Puede usarse tanto a nivel de clase como a nivel de método.

**@Produces :**&#x45;sta anotación se encarga de que el contenido del servicio REST sea generado con distintos formatos.En nuestro caso usaremos JSON

Vamos a ver un ejemplo de código sencillo.

```
```

```
package com.arquitecturajava.serviciosexternos;
 
import java.util.ArrayList;
import java.util.List;
 
import javax.ws.rs.GET;
import javax.ws.rs.POST;
import javax.ws.rs.Path;
import javax.ws.rs.Produces;
import javax.ws.rs.core.MultivaluedMap;
 
@Path("/servicioPersonas/")
@Produces("application/json")
public class ServicioPersonas {
 
private static List&amp;amp;lt;Persona&amp;amp;gt; listaPersonas = new ArrayList&amp;amp;lt;Persona&amp;amp;gt;();
 
public ServicioPersonas() {
 super();
 Persona yo = new Persona("pedro", "perez");
 listaPersonas.add(yo);
 }
 
@GET
 @Path("/personas")
 public List&amp;amp;lt;Persona&amp;amp;gt; getPersonas() {
 
return listaPersonas;
 }
 
@POST
 @Path("/personas")
 public void addPersona(MultivaluedMap&amp;amp;lt;String, String&amp;amp;gt; parametros) {
 
Persona p = new Persona(parametros.getFirst("nombre"),
 parametros.getFirst("apellidos"));
 listaPersonas.add(p);
 }
}
```

En este caso hemos utilizado un servicio REST que se encarga de mostrar las personas que tenemos almacenas en una variable “listaPersonas” que al ser estatica se mantiene en memoria. Por lo tanto definir un método GET es suficiente para acceder a la información. Este método se apoya en la anotación @Produces para generar información en formato JSON.

<figure><img src="../../.gitbook/assets/image (1) (1).png" alt=""><figcaption></figcaption></figure>

Una vez hemos invocado la primera vez al servicio  via URL podemos usar un formulario HTML para invocar al metodo /personaa  pasando los parametros por POST y añadiendo nuevas personas a la lista

```
```

```
&amp;amp;lt;html&amp;amp;gt;
&amp;amp;lt;body&amp;amp;gt;
&amp;amp;lt;form method="POST" action="rest/servicioPersonas/personas"&amp;amp;gt;
&amp;amp;lt;input type="text" name="nombre"/&amp;amp;gt;
&amp;amp;lt;input type="text" name="apellidos"/&amp;amp;gt;
&amp;amp;lt;input type="submit"/&amp;amp;gt;
&amp;amp;lt;/form&amp;amp;gt;
&amp;amp;lt;/body&amp;amp;gt;
&amp;amp;lt;/html&amp;amp;gt;
```

Realizada esta operación la lista de personas queda modificada

<figure><img src="../../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>

Aunque el ejemplo es muy sencillo muchas veces es mas complicado configurar algún framework para que pueda construir estos servicios .En el siguiente POST hablaremos de como configurar Apache CXF para que este servicio REST funcione sin problemas.
