# Instalar y configurar el controlador JDBC de MySQL en JBoss Wildfly.

{% embed url="https://reachmnadeem.wordpress.com/2021/05/13/install-and-configure-mysql-jdbc-driver-on-jboss-wildfly/" %}

Pool de Conexiones Jboss

[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEglCsi_M9KFLkuSNF91tXR9Zbwc0LWO3Kc0FAV67ZXEQGFA3GpgRZNAtFiK3rlY8pnAjJkeOE3c6x7ZsihW8s-Or6JoxeH_dP4afWg7N9e8rGW0U-enEtUXb49oC0_p1IHpWf7FOb0WO5sd/s1600/1.gif)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEglCsi_M9KFLkuSNF91tXR9Zbwc0LWO3Kc0FAV67ZXEQGFA3GpgRZNAtFiK3rlY8pnAjJkeOE3c6x7ZsihW8s-Or6JoxeH_dP4afWg7N9e8rGW0U-enEtUXb49oC0_p1IHpWf7FOb0WO5sd/s1600/1.gif)Un pool de conexiones es un conjunto limitado de conexiones a una base de datos, que es manejado por un servidor de aplicaciones por ejemplo Jboss.\
Usar un pool de conexiones es más efectivo que abrir una nueva conexión cada vez que sea necesario por lo tanto no hay motivo para no usar un pool de conexiones, vamos a ver como configurar un pool de conexiones en Jboss.\
\
Un poco de Teoría\
La forma tradicional de comunicarse con una base de datos generalmente es utilizando un protocolo especializado y establecer una conexión, esta conexión se mantiene abierta un tiempo determinado y es cerrada al finalizar la aplicación.\
Sin embargo este esquema no es muy apropiado para aplicaciones en las que se realizan en paralelo más de una operación sobre la base de datos como es el caso típico de las aplicaciones web. Ya que estas proveen servicios a múltiples usuarios y en ellas el numero de operaciones sobre la base depende de la actividad de los usuarios sobre dicha aplicación web.\
\
Funcionamiento\
El pool de conexiones es un grupo de conexiones que son atribuidos a diferentes hilos de ejecución únicamente el tiempo que dura una transacción con la base de datos, al finalizar su utilización la conexión se pone a disposición de otro hilo de ejecución que lo necesite.\
Cuando todas las conexiones están en uso se crean nuevas conexiones automáticamente. Se puede configurar un número máximo de conexiones y cuando no es posible crear más conexiones se deja el hilo de ejecución en espera de que alguna conexión se libere.\
Si pasa mucho tiempo sin que alguna conexión sea utilizada esta es cerrada automáticamente.\
\
Manos a la Obra\
Vamos a Crear un Pool de Conexiones en Jboss utilizando un Datasource.\
\
paso1.- Crear el datasource y ubicarlo en la ruta de la instancia de Jboss que estén utilizando, en mi caso voy a crear un archivo ejemplo-ds.xml\
%JBOSS\_HOME%/server/default/deploy/ejemplo-ds.xml\
Es importante que el nombre del archivo xml del datasource termine en -ds, caso contrario Jboss no lo tendrá en cuenta.\
Además debe ubicarse los drivers (.jar) respectivos de cada base de datos en la carpeta lib de la instancia de Jboss que es donde el Jboss las va a buscar, en mi caso la ruta es:\
%JBOSS\_HOME%/server/default/lib\
mysql-connector...jar para el caso de Mysql y ojdbc14.jar para el caso de Oracle.\
\
Datasource para una conexión Oracle:\
<br>

```
<?xml version="1.0" encoding="UTF-8"?>
<datasources>
    <local-tx-datasource>
        <jndi-name>ejemplo-ds</jndi-name>
        <connection-url>jdbc:oracle:thin:@ipdelservidor:1521:xe</connection-url>
        <driver-class>oracle.jdbc.driver.OracleDriver</driver-class>

        <user-name>Usuario</user-name>

        <password>Password</password>
        <valid-connection-checker-class-name>org.jboss.resource.adapter.jdbc.vendor.OracleValidConnectionChecker</valid-connection-checker-class-name>
        <metadata>
            <type-mapping>Oracle9i</type-mapping>
        </metadata>
  <min-pool-size>2</min-pool-size>
  <max-pool-size>4</max-pool-size>
  <idle-timeout-minutes>5</idle-timeout-minutes>
    </local-tx-datasource>
</datasources>
```

\
Hay que tener en cuenta que es aquí en el datasource donde se define los parámetros del pool de conexiones, a continuación detallo los más destacables:<br>

* min-pool-size : hace referencia al número mínimo de conexiones con que se crea el pool.
* max-pool-size : hace referencia al máximo número de conexiones que va a crear el pool, si las conexiones llegan a este número, los hilos de ejecución que soliciten una conexión tendrán que esperar a que alguna conexión se libere.
* idle-timeout-minutes : es el tiempo que una conexión espera a ser utilizada antes de cerrarse.
* jndi-name : Nombre con el que se recuperará el Datasource en el código java, no es obligación que se llame igual que el archivo xml. Pero si es muy ordenado tenerlo así.

Estos valores deberán configurarse dependiendo del tráfico del sitio web y la capacidad del servidor de base de datos para manejar un número determinado de peticiones recurrentes.\
Como ejemplo también dejo el Datasource para una conexión Mysql<br>

```
<?xml version="1.0" encoding="UTF-8"?>
<datasources>
    <local-tx-datasource>
    <jndi-name>ecutelmysql-ds</jndi-name>
    <connection-url>jdbc:mysql://ipdelservidor:3306/nombrebasedatos</connection-url>
    <driver-class>com.mysql.jdbc.Driver</driver-class>
    <user-name>usuario</user-name>
    <password>password</password>
    <valid-connection-checker-class-name>org.jboss.resource.adapter.jdbc.vendor.MySQLValidConnectionChecker</valid-connection-checker-class-name>
    <metadata>
    <type-mapping>mySQL</type-mapping>
    </metadata>
 <min-pool-size>2</min-pool-size>
 <max-pool-size>4</max-pool-size>
 <idle-timeout-minutes>5</idle-timeout-minutes>
    </local-tx-datasource>
</datasources>
```

\
Pueden revisar datasources de otras bases de datos [AQUÍ](http://adf.ly/jUzK0)\
\
paso2.- Vamos a realizar una página jsp de prueba que cree una instancia de la clase java.sql.Connection y luego imprimiremos el .toString() de dicha conexión, con eso probaremos que se logró recuperar una conexión a partir del pool de conexiones configurado en ejemplo-ds.xml\
<br>

```
<%@ page import="java.sql.Connection" %>
<%@ page import="javax.naming.Context" %>
<%@ page import="javax.naming.InitialContext" %>
<%@ page import="javax.sql.DataSource" %>

<%
// obtengo el contexto inicial
Context ctx = new InitialContext();
// lookapeo el DataSource         
DataSource ds = (DataSource) ctx.lookup("java:/ejemplo-ds");

out.println(" Tengo el DataSource java:/ejemplo-ds, le pido una conexion <br/>");
Connection con = ds.getConnection();
// la utilizo sea con un select o cualquier query, etc...
out.println(" Muestro el tostring() para ver si se instanció <br/>");
if(con!=null){
    out.println(con);
}else{
    out.println("No se instanció <br/>");
}
// al cerrar la conexion en realidad la estoy devolviendo al pool
out.println("Llamo al con.close que devuelve la conexión al pool. <br/>");
if(con!=null){
   con.close();
}    
%>
```

\
Descargar código de Ejemplo:  [AQUÍ](http://adf.ly/jUw25)<br>
