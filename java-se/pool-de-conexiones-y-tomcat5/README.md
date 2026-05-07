# Pool de Conexiones y Tomcat5

Os mostramos como instalar Tomcat5 en vuestro PC y como ejemplo de uso, configuramos un Pool de Conexiones y lo usamos contra MySQL

## Instalación de Tomcat 5 y Pool de Conexiones

Los servidores de aplicaciones están en constante evolución. Aparte de para\
arreglar posibles problemas, también para dar soporte a las nuevas versiones de\
las especificaciones de Java.

<table data-header-hidden><thead><tr><th valign="top"></th><th valign="top"></th></tr></thead><tbody><tr><td valign="top">Especificación<br>Servlet/JSP</td><td valign="top">Versión<br>de Tomcat</td></tr><tr><td valign="top">2.4/2.0</td><td valign="top">5.0.12<br>Beta</td></tr><tr><td valign="top">2.3/1.2</td><td valign="top">4.1.27</td></tr><tr><td valign="top">2.2/1.1</td><td valign="top">3.3.1a</td></tr></tbody></table>

Vamos a descargarnos la última versión disponible de Tomcat y mostraros\
algunas de sus características.

No nos vamos a quedar aquí sino que os vamos a mostrar como se configura\
para utilizar un Pool de conexiones y optimizar de este modo los accesos a la\
base de datos. Como siempre … usaremos MySQL.

Antes que nada, vamos al Web y pinchamos en el botón de descarga.

### Descarga

[http://jakarta.apache.org/tomcat/index.html](http://jakarta.apache.org/tomcat/index.html)

Nos descargamos el ejecutable y lo lanzamos.

<div align="left"><img src="https://adictosaltrabajo.com/wp-content/uploads/tutorial-data/tomcat5/tomcat1.gif" alt="" height="288" width="398"></div>

Arranca la instalación de Tomcat 5

<div align="left"><img src="https://adictosaltrabajo.com/wp-content/uploads/tutorial-data/tomcat5/tomcat2.jpg" alt="" height="386" width="503"></div>

Seleccionamos la configuración normal

<div align="left"><img src="https://adictosaltrabajo.com/wp-content/uploads/tutorial-data/tomcat5/tomcat3.jpg" alt="" height="386" width="503"></div>

Vemos que el directorio tradicional de instalación ha cambiado

<div align="left"><img src="https://adictosaltrabajo.com/wp-content/uploads/tutorial-data/tomcat5/tomcat4.jpg" alt="" height="386" width="503"></div>

Seleccionamos un usuario y password para administración

<div align="left"><img src="https://adictosaltrabajo.com/wp-content/uploads/tutorial-data/tomcat5/tomcat5.jpg" alt="" height="386" width="503"></div>

Elegimos el trayecto de la versión de Java a utilizar.

<div align="left"><img src="https://adictosaltrabajo.com/wp-content/uploads/tutorial-data/tomcat5/tomcat6.jpg" alt="" height="386" width="503"></div>

Finalizamos y leemos las notas de versión

<div align="left"><img src="https://adictosaltrabajo.com/wp-content/uploads/tutorial-data/tomcat5/tomcat7.jpg" alt="" height="386" width="503"></div>

### Comprobación

Ahora probamos que funciona

<div align="left"><img src="https://adictosaltrabajo.com/wp-content/uploads/tutorial-data/tomcat5/tomcat8.jpg" alt="" height="471" width="656"></div>

### Administración

En la parte de administración tenemos unos enlaces para ver el Estado\
(status)

<div align="left"><img src="https://adictosaltrabajo.com/wp-content/uploads/tutorial-data/tomcat5/tomcat9.jpg" alt="" height="662" width="654"></div>

Si pinchamos el segundo enlace, podemos ver la administración

<div align="left"><img src="https://adictosaltrabajo.com/wp-content/uploads/tutorial-data/tomcat5/tomcat10.jpg" alt="" height="585" width="552"></div>

Donde podemos administrar los ficheros de configuración de un modo gráfico

<div align="left"><img src="https://adictosaltrabajo.com/wp-content/uploads/tutorial-data/tomcat5/tomcat11.jpg" alt="" height="738" width="681"></div>

Y la última opción es el Manager … donde podemos desplegar y recargar las\
aplicaciones Web

<div align="left"><img src="https://adictosaltrabajo.com/wp-content/uploads/tutorial-data/tomcat5/tomcat12.jpg" alt="" height="594" width="600"></div>

### Pool de Conexiones

Ahora, no nos vamos a quedar solo en la configuración….. vamos a hacer un\
ejemplo que seguro que os gustará…. la configuración de un Pool de\
conexiones a MySQL.

Debemos&#x20;

* Registrar el Pool en el fichero server.xml
* Dejar a mano las clases del Driver
* Crear nuestro servlet
* Hacer accesible el Pool al servlet
* Crear la tabla en base de datos

Com vereis, es sencillo y rápido

#### Server.xml

Lo primero que hacemos, es modificar el fichero server.xml

C:\Program Files\Apache Software Foundation\Tomcat 5.0\conf\server.xml

| <p>&#x3C;Context path=«/tomcat5»<br>docBase=«tomcat5»<br>debug=«0»</p><p>reloadable=</p><p>«true»<br>><br></p><p>&#x3C;ResourceParams name=«jdbc/tutoriales«><br></p><p>&#x3C;parameter><br></p><p>&#x3C;name>username&#x3C;/name><br></p><p>&#x3C;value>root&#x3C;/value><br></p><p>&#x3C;/parameter><br></p><p>&#x3C;parameter><br></p><p>&#x3C;name>password&#x3C;/name><br></p><p>&#x3C;value>&#x3C;/value><br></p><p>&#x3C;/parameter><br></p><p>&#x3C;parameter><br></p><p>&#x3C;name>driverClassName&#x3C;/name><br></p><p>&#x3C;value>com.mysql.jdbc.Driver&#x3C;/value><br></p><p>&#x3C;/parameter><br></p><p>&#x3C;parameter><br></p><p>&#x3C;name>url&#x3C;/name><br></p><p>&#x3C;value>jdbc:mysql://localhost/tutoriales&#x3C;/value><br></p><p>&#x3C;/parameter><br></p><p>&#x3C;/ResourceParams></p><p>&#x3C;/Context></p> |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

#### Jar del Driver JDBC

Ahora introducimos el Jar del Driver Jdbc de MySQL en el directorio\
adecuado&#x20;

C:\Program Files\Apache Software Foundation\Tomcat 5.0\common\lib\mysql-connector-java-3.0.7-stable-bin.jar

&#x20;

#### El Servlet

Debemos crear nuestra aplicación. Creemos nuestro Servlet (poolBaseDatos.java).

Este código ya tiene mejor pinta….. y le falta muy poquito para ser\
profesional ….. solo faltaría gestionar un poquito mejor los errores y\
…… sobre todo …. separar la lógica de negocio de la de presentación.

<table data-header-hidden><thead><tr><th></th></tr></thead><tbody><tr><td><pre><code> import java.io.*;
import java.sql.*;
import javax.sql.*;
import javax.servlet.*;
import javax.servlet.http.*;
import javax.naming.*;

public class poolBaseDatos extends HttpServlet 
</code></pre><pre><code>{
    private DataSource fuenteDatos = null;

    public void init(ServletConfig config) throws ServletException
    {
        try
        {
            // recuperamos el contexto inicial y la referencia a la fuente de datos
            Context ctx = new InitialContext();
            fuenteDatos = (DataSource) ctx.lookup("java:comp/env/jdbc/tutoriales");
        }
        catch (Exception e)
        {
            throw new ServletException("Imposible recuperar java:comp/env/jdbc/tutoriales",e);
        }
    }

    public void doGet(HttpServletRequest request, HttpServletResponse response)
    throws ServletException, IOException
    {
        Connection con = null; // conexion parcial

        response.setContentType("text/html");   // retornamos el tipo de respuesta
        PrintWriter out = response.getWriter();

        out.println("Prueba del Pool de Objetos");
        out.println("Buscamos tutorial con sentencias preparadas");

        try {

           out.println("Probamos a recuperar conexión");

            synchronized (fuenteDatos)
            {
                con = fuenteDatos.getConnection(); // cogemos la conexion
            }

            if(con == null)
            {
                out.println("Error al recuperar la conexion, es nula");
                throw new ServletException("Problemas con la conexion");
            }

            out.println("Preparamos la consulta");

            PreparedStatement pstmt = con.prepareStatement("SELECT * FROM tutoriales WHERE id &#x3C; ?");
            pstmt.setInt(1,10); // establecemos el entero
            ResultSet results = pstmt.executeQuery();

            while (results.next())
            {
                String id = results.getString(1);
                String titulo = results.getString(2);
                out.println("El titulo es " + titulo + " para id " + id + "");
            }
        }
        catch (Exception e)
        {
            out.println("Error al procesar consulta " + e.getMessage());
        }
        finally  // pase lo que pase retornamos la conexion
        {
            try
            {
                con.close();
            }
            catch (Exception e)
            {
                out.println("Error en proceso " + e.getMessage());
            }
        }
        out.println("-Fin-");  // cerramos la respuesta
         out.close();  // Cerramos buffer
    }
}
    
</code></pre></td></tr></tbody></table>

#### Descriptor de la Web APP

Ahora, necesitamos un fichero descriptor … web.xml

| <p>&#x3C;?xml version=»1.0″ encoding=»UTF-8″?></p><p>&#x3C;!DOCTYPE web-app<br>PUBLIC «-//Sun Microsystems, Inc.//DTD Web Application 2.3//EN»<br>«http://java.sun.com/dtd/web-app_2_3.dtd»></p><p>&#x3C;web-app></p><p>&#x3C;servlet><br>   &#x3C;servlet-name>poolBaseDatos&#x3C;/servlet-name><br>   &#x3C;servlet-class>poolBaseDatos&#x3C;/servlet-class><br>&#x3C;/servlet><br>&#x3C;servlet-mapping><br>   &#x3C;servlet-name>poolBaseDatos&#x3C;/servlet-name><br>   &#x3C;url-pattern>/servlet/poolBaseDatos&#x3C;/url-pattern><br>&#x3C;/servlet-mapping><br>&#x3C;session-config><br> &#x3C;session-timeout>30&#x3C;/session-timeout><br>&#x3C;/session-config><br>&#x3C;welcome-file-list><br>   &#x3C;welcome-file>index.jsp&#x3C;/welcome-file><br>   &#x3C;welcome-file>index.html&#x3C;/welcome-file><br>   &#x3C;welcome-file>index.htm&#x3C;/welcome-file><br>&#x3C;/welcome-file-list><br>&#x3C;resource-ref><br>&#x3C;res-ref-name>jdbc/tutoriales&#x3C;/res-ref-name><br>&#x3C;res-type>javax.sql.DataSource&#x3C;/res-type><br>&#x3C;res-auth>Container&#x3C;/res-auth><br>&#x3C;/resource-ref><br>&#x3C;/web-app></p> |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

#### La tabla en la Base de Datos

Creamos una tabla e insertamos datos de los tutoriales

<div align="left"><img src="https://adictosaltrabajo.com/wp-content/uploads/tutorial-data/tomcat5/tomcat13.jpg" alt="" height="439" width="681"></div>

Ahora solo nos hace falta desplegar la aplicación …… por lo que\
creamos nuestro directorio y copiamos los ficheros

C:\Program Files\Apache Software Foundation\Tomcat 5.0\webapps\tomcat5

| <p>WEB-INF<br>│ web.xml<br>│<br>├───classes<br>│ poolBaseDatos.class<br>│ poolBaseDatos.java<br>│<br>└───lib</p> |
| ---------------------------------------------------------------------------------------------------------------- |

Otra solución es comprimir la estructura anterior en un fichero WAR y\
dejarlo caer en&#x20;

C:\Program Files\Apache Software Foundation\Tomcat 5.0\webapps

#### El resultado

Fijaros bien el la URL ….. y comprobad el rendimiento … os\
sorprendereis.

<div align="left"><img src="https://adictosaltrabajo.com/wp-content/uploads/tutorial-data/tomcat5/tomcat15.jpg" alt="" height="359" width="402"></div>

Ya hemos dado otro pasito ….. aunque el camino cada vez es\
mas largo y con más bifulcaciones ….
