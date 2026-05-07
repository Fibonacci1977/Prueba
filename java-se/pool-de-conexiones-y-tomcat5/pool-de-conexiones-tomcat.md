# Page 1



{% embed url="https://youtu.be/pBcWRn1S3rA" %}

Configurar un **DataSource** (pool de conexiones) en Tomcat para **MySQL** implica tres pasos clave: colocar el conector JDBC en `/lib`, definir el recurso en `context.xml` y declarar la referencia en `web.xml`. Esto permite gestionar eficientemente las conexiones y reutilizarlas, mejorando el rendimiento de la aplicación. \[[1](https://programandoointentandolo.com/2013/05/como-crear-un-pool-de-conexiones-en-tomcat), [2](https://loquemeinteresadelared.wordpress.com/2015/02/23/configuracion-de-un-datasource-para-acceder-a-una-base-de-datos-en-tomcat-6-7-y-8/)]**Pasos de Configuración:**

* **Conector JDBC:** Descarga el _mysql-connector-java_.jar y colócalo en la carpeta `$TOMCAT_HOME/lib`.
*   **Archivo `context.xml` (en `conf/` o `META-INF/`):**&#x78;ml

    ```
    <Context>
        <Resource name="jdbc/MiPoolMySQL"
                  auth="Container"
                  type="javax.sql.DataSource"
                  maxActive="20"
                  maxIdle="10"
                  maxWait="10000"
                  username="tuUsuario"
                  password="tuPassword"
                  driverClassName="com.mysql.cj.jdbc.Driver"
                  url="jdbc:mysql://localhost:3306/tuBaseDatos?useSSL=false&amp;serverTimezone=UTC"/>
    </Context>
    ```

    Usa el código con precaución._(Nota: Usa `com.mysql.cj.jdbc.Driver` para versiones modernas de MySQL)._
*   **Archivo `web.xml` (en `WEB-INF/`):**&#x78;ml

    ```
    <resource-ref>
        <description>Conexion MySQL</description>
        <res-ref-name>jdbc/MiPoolMySQL</res-ref-name>
        <res-type>javax.sql.DataSource</res-type>
        <res-auth>Container</res-auth>
    </resource-ref>
    ```

    Usa el código con precaución.\[[1](https://es.stackoverflow.com/questions/21525/problemas-con-datasource-en-un-servidor-tomcat-8), [2](https://www.cablenaranja.com/como-conectar-java-con-mysql-en-netbeans/), [3](https://programandoointentandolo.com/2013/05/como-crear-un-pool-de-conexiones-en-tomcat)]

**Cómo utilizarlo en el código Java (JNDI):**&#x6A;ava

```
Context initContext = new InitialContext();
Context envContext  = (Context)initContext.lookup("java:/comp/env");
DataSource ds = (DataSource)envContext.lookup("jdbc/MiPoolMySQL");
Connection conn = ds.getConnection();
// ... usar la conexión ...
conn.close(); // Devuelve la conexión al pool
```

Usa el código con precaución.**Recomendaciones:**

* Asegúrate de configurar `maxActive` y `maxIdle` según la carga de tu aplicación.
* Si experimentas cierres inesperados de conexión, ajusta los tiempos de espera de MySQL. \[[1](https://groups.google.com/g/javasos/c/8IwHK0lmJ4Y), [2](https://programandoointentandolo.com/2013/05/como-crear-un-pool-de-conexiones-en-tomcat)]

Para personalizar esto, ¿me podrías decir qué versión de Tomcat y MySQL estás usando? Además, ¿te interesa configurar la persistencia de la conexión o la seguridad?

***

La mayoría de las veces, las aplicaciones web que desarrollamos deben estar conectada a una base de datos. Hemos aprendido que con Java podemos lograr una conexión a la base de datos usando estas dos líneas básicas:<br>

```vbnet
Class.forName("clase.driver.Driver");Connection conn=DriverManager.getConnection("url:jdbc","usuario","pass");
```

Funciona correctamente cuando recién nos iniciamos en el mundo del JDBC. Y no está mal. Solo que es para aplicaciones con una sola conexión concurrente a la base de datos.\
\
Una aplicación web puede ser accedida por varios usuarios a la vez, y si nuestra aplicación web utiliza estas sentencias, podremos saturar la conexión a la base de datos. Se podría sobrecargar de conexiones y nuestra aplicación podría caerse. Le ponemos puros .close() por todos lados, y de cuando en cuando aparecerá el error: "La conexión se ha cerrado". Entonces, tendremos que pensar un sistema de semáforo para poder tomar y liberar la base de datos dependiendo de la carga de conexiones. Nuestra aplicación web ya deja de serlo porque nos centramos en la administración del recurso. Y finalmente tiramos la toalla porque se está volviendo muy complejo algo que debería ser simple. Vaya, y solo por esas dos líneas.\
\
Esto no es nada nuevo. Al inicio se encontró esos problemas, y también salieron las soluciones. Es usar un Pool de Conexiones de base de datos.\
\
Lo que se explicará en este post es cómo hacer una aplicación web utilizando una conexión a base de datos de una manera profesional. Ya no con esas dos líneas. Dejaremos que la conexión a la base de datos (usando un pool de conexión) se haga cargo el contenedor web (o de aplicaciones).\
\
Aunque en este post se tratará de ser lo más independientemente posible con lo que respecta a los IDEs, se mencionará a NetBeans 6.01 y Eclipse 3.3 como referencia.<br>

### Nuestra aplicación web

Nuestra aplicación web no será algo fuera de este mundo. Puedes usar una base de datos que ya estés usando. En mi caso usaré una base de datos en MySQL.\
\
La secuencia que usaremos será simple:<br>

1. Al ejecutarse la aplicación, se mostrará el /index.jsp. Este redireccionará al servlet /Listar
2. El servlet /Listar se conectará a la base de datos, obtendrá una consulta, y el resultado lo pondrá en una variable de sesión.<br>
3. El servlet redireccionará la petición a /resultado.jsp quien mostrará el resultado al usuario.

Simple.\
\
El index.jsp es bastante simple:

```php-template
<jsp:forward page="/Listar" />
```

\
\
Y resultado.jsp es este:

```php-template
<%@page contentType="text/html" pageEncoding="UTF-8"%><!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN""http://www.w3.org/TR/html4/loose.dtd"><html><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"><title>JSP Page</title></head><body><h2>Resultado</h2>${resultado}</body></html>
```

\
El servlet será algo como esto. ListarServlet.java:

```java
public class ListarServlet extends HttpServlet {@Overrideprotected void doGet(HttpServletRequest request, HttpServletResponse response)throws ServletException, IOException{try {Context ctx = new InitialContext();DataSource ds=(DataSource) ctx.lookup("java:comp/env/jdbc/TestDB");Connection conn=ds.getConnection();Statement stmt=conn.createStatement();ResultSet rs=stmt.executeQuery("SELECT count(*) as cuenta FROM padron");int result=0;if (rs.next())result=rs.getInt("cuenta");request.setAttribute("resultado", result);RequestDispatcher rd=getServletContext().getRequestDispatcher("/resultado.jsp");rd.forward(request, response);conn.close();} catch (SQLException ex) {ex.printStackTrace();} catch (NamingException ex) {ex.printStackTrace();}}}
```

\
Vemos que las dos lineas de conexión de la base de datos que vimos al inicio de este post, fueron reemplazados por

```java
            Context ctx = new InitialContext();DataSource ds=(DataSource) ctx.lookup("java:comp/env/jdbc/TestDB");Connection conn=ds.getConnection();
```

Como se ve (o no se ve) es que ya no se dice cuál es la base de datos, donde se encuentra, y cuál es el driver del JDBC. Esto lo dejamos al servidor. En este caso, al Tomcat. Ahora bien, ¿dónde?.\
\
Para el caso del Tomcat 5.5 y 6, existe un archivo llamado context.xml ubicando dentro de la carpeta META-INF. Si no existe, lo podemos crear con toda confianza.\
\
Este archivo indica cómo debe desplegarse la aplicación web cuando se cargado al Tomcat. El NetBeans lo crea automáticamente. En el Eclipse lo podemos crear.\
\
La documentación para esta archivo se encuentra aquí:<br>

* Tomcat 5.5: [http://tomcat.apache.org/tomcat-5.5-doc/config/context.html](http://tomcat.apache.org/tomcat-5.5-doc/config/context.html)
* Tomcat 6: [http://tomcat.apache.org/tomcat-6.0-doc/config/context.html](http://tomcat.apache.org/tomcat-6.0-doc/config/context.html)

No nos detendremos para detallar cada atributo y tag del .xml. Solo usaremos lo necesario para que nuestra aplicación se conecte a la base de datos.\
\
Bien, el archivo context.xml deberá tener lo siguiente.<br>

```xml
<?xml version="1.0" encoding="UTF-8"?><Context path="/demoweb"  reloadable="true" crossContext="true"><Resource name="jdbc/TestDB"auth="Container"type="javax.sql.DataSource"maxActive="100"maxIdle="30"maxWait="10000"username="user"password="pass"driverClassName="com.mysql.jdbc.Driver"url="jdbc:mysql://localhost:3306/javatest?autoReconnect=true"/></Context>
```

El atributo path es el nombre de la aplicación web. O sea, cuando se ejecute, el URL será http://localhost:8080/demoweb.\
\
Se pueden identificar algunos atributos como username, password, driverClassName y url. En vez declararse en la clase java (como vimos al inicio de este post), lo colocamos en este .xml. Si necesitácemos cambiar de base de datos (por ejemplo, ya no será localhost, sino se encuentra en otro host) solo editamos el atributo correspondiente.\
\
Con esto, la aplicación funciona (al menos a mi). Pero he leido mucha documentación (incluyendo la del mismo Tomcat) que se debe agregar unos tags al archivo web.xml. Y son los siguientes.

```php-template
    <resource-ref><res-ref-name>jdbc/TestDB</res-ref-name><res-type>javax.sql.DataSource</res-type><res-auth>Container</res-auth><res-sharing-scope>Shareable</res-sharing-scope></resource-ref>
```

Con esto sigue funcionando. Pero nos será útil para nuestro siguiente paso.<br>

### Configurando para que se ejecute en Glassfish.

Ahora, imaginemos que debamos utilizar nuestra aplicación en un contenedor de aplicaciones en el cual ya se tiene configurada la conexión a la base de datos. Y el estándar de la organización en que estamos trabajando es el Glassfish. (Aún no me resulta con JBoss 5, así que lo dejaré para otra ocasión)\
Para comenzar, debemos cambiar el servidor de ejecución de nuestra aplicación. En NetBeans, entramos a las propiedades del proyecto, y en la categoría Run cambiamos a Glassfish.\
\
\
Y si estamos en Eclipse, entramos a las propiedades del proyecto y cambiamos la biblioteca del Runtime Server de Tomcat a Glassfish.\
\
Nota: no olvidemos copiar el .jar del JDBC de la base de datos en $GLASSFISH/domains/domain1/lib\
\
Si usamos NetBeans, el IDE creará automáticamente el archivo WEB-INF/sun-web.xml Si estamos usando Eclipse, lo crearemos utilizando este contenido.<br>

<figure><img src="https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEg19q6CBPCQQOTu8eK4AYixQwIG4U8cSruMjoGwZ4wFHgXoQyVeXbY1v_vctg6w9zSZqdbbefN3WSzLQJCjrF9LmNaGtQvl1ObB3AU1Cdmv0c1r9-LPwe847KuqZuoyV68M1CNqly96od-Z/s320-rw/netbeans-glassfish.jpg" alt=""><figcaption></figcaption></figure>

<figure><img src="https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjDzGEfRndLvq9J-5-F6zbaZeFpFZ1umMzCtH4yseZLVZ_h_DwSV4nKNyvHUykqPpdZ34nwwAOyhbPovNVeK8GKTH8YJNQv1u8wtC8KP95yzB7k-tdehqP-pZzQRM74iC-Il3rGXz2nsEpO/s320-rw/eclipse-glassfish.jpg" alt=""><figcaption></figcaption></figure>

```xml
<?xml version="1.0" encoding="UTF-8"?><!DOCTYPE sun-web-app PUBLIC "-//Sun Microsystems, Inc.//DTD Application Server 9.0 Servlet 2.5//EN" "http://www.sun.com/software/appserver/dtds/sun-web-app_2_5-0.dtd"><sun-web-app error-url=""><context-root>/demoweb</context-root><class-loader delegate="true"/><jsp-config><property name="keepgenerated" value="true"><description>Keep a copy of the generated servlet class java code.</description></property></jsp-config></sun-web-app>
```

Este es el archivo de despligue para Glassfish (análogo del context.xml en el Tomcat). Solo que aquí no le indicamos cuál es la conexión a la base de datos. Eso lo haremos en el mismo servidor.\
\
Para ello entramos a la consola en http://localhost:4848 (por omisión, el usuario es admin y la contraseña adminadmin). Luego, en el panel de la izquierda seleccionamos Resources > JDBC > Connection Pools y hacemos clic en el botón superior "New". Escribimos los valores para identificar nuestro Pool que crearemos a continuación:<br>

<figure><img src="https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhGd_NxkWyiFpzHFfhElWmyg92Z0UMuCE0uBvASxmVTaLuEAyuKBE9SHYwOOG0fPbUvhnVnnW2YxZfiloLxXk5PHa18-ujMuOPWx2VFqrXUgoWFCtSRXu87L0PqwzoZvqz-53kh7atUg6ew/s320-rw/glassfish-pool1.jpg" alt=""><figcaption></figcaption></figure>

Damos clic en Next. Y en la siguiente ventana buscaremos las propiedades necesarias para establacer la conexión a la base de datos. Es decir: url, user, password, ServerName (=localhost), databasename(=DatabaseName). Hacemos clic en Finish.\
\
Podemos hacer clic al Pool recién creado, y le damos clic en el botón "Ping" para ver si está bien configurado.<br>

<figure><img src="https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEheGpiBc78Fs5lxt-6PUd-x6pVtgahtsCq_EHsO6NWeczwNBhVt540NxX9q-y-LOWWz-2qP4vfn6E7j1piCPE_CiwsgCAKwwGrZFYsvSavDodb6WDtgIOw8J0UV_mu2oZ5dFwvU__su0EwG/s320-rw/glassfish-pool2.jpg" alt=""><figcaption></figcaption></figure>

Ahora, debemos crear el Recurso JDBC. Para ello, en el panel izquierdo entramos a Resources > JDBC > JDBC Resources y le damos clic en "New".\
Escribimos los valores que hagan referencia al Pool que acabamos de crear. Recordemos que el nombre del JNDI debe ser ser el mismo que hacemos referencia en web.xml.<br>

<figure><img src="https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEg2pNxrD2h0OSSHpolpyTLPYfXVaxUuMuPaLjgLSiUBsh8QbcwyYDl3-KJeKfSJkFsaySgprGJAtNW5hEwf3TbbZ2c4ySe0-fFJlGKRm5QJxkDOI63_eVM9YHe4Ed1NdVZ4jH1NNErEAxDA/s320-rw/glassfish-pool3.jpg" alt=""><figcaption></figcaption></figure>

Y listo. Lo ejecutamos y veremos que la aplicación funciona normal. ¿Qué hemos modificado en la aplicación? solo hemos creado un archivo de despliegue, pero en la lógica de la aplicación.... nada.<br>

### Para terminar

A partir de ahora, cuando hagamos nuestras aplicaciones web, la tarea de la conexión a la base de datos la delegaremos al servidor. De esta manera, sólo nos preocuparemos en la lógica de la aplicación. Y si deseamos cambiar de servidor (ya sea de host, o a otro motor) solo lo configuraremos el servidor, y la aplicación seguirá siendo la misma. De esta manera será portable, y el upsize que se desee hacer será totalmente transparente.
