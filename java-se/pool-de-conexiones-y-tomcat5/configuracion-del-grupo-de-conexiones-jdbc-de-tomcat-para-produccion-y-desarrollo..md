# Configuración del grupo de conexiones JDBC de Tomcat para producción y desarrollo.

***

Como se menciona en la publicación [«Instalar Eclipse Kepler de 64 bits en Windows 7 de 64 bits»](https://www.codepedia.org/ama/install-eclipse-kepler-64-bit-on-windows-7-64-bit) , [Podcastpedia.org](https://github.com/CodepediaOrg/podcastpedia) utiliza [Apache Tomcat 7](https://tomcat.apache.org/) como servidor de aplicaciones. Esta publicación muestra cómo se configura el grupo de conexiones JDBC de Tomcat en los entornos de desarrollo y producción de [Podcastpedia.org](https://github.com/CodepediaOrg/podcastpedia) . La base de datos utilizada es MySQL.<br>

Contenido

* [Entorno de producción](https://www.codepedia.org/ama/tomcat-jdbc-connection-pool-configuration-for-production-and-development/#Production_environment)
  * [Dimensionamiento del pozo de conexión](https://www.codepedia.org/ama/tomcat-jdbc-connection-pool-configuration-for-production-and-development/#Sizing_the_conection_pool)
  * [Validar conexiones](https://www.codepedia.org/ama/tomcat-jdbc-connection-pool-configuration-for-production-and-development/#Validate_connections)
  * [fugas de conexión](https://www.codepedia.org/ama/tomcat-jdbc-connection-pool-configuration-for-production-and-development/#Connection_leaks)
  * [El hilo de validación/limpieza](https://www.codepedia.org/ama/tomcat-jdbc-connection-pool-configuration-for-production-and-development/#The_validationcleaner_thread)
* [Entorno de desarrollo](https://www.codepedia.org/ama/tomcat-jdbc-connection-pool-configuration-for-production-and-development/#Development_environment)
* [Cuidado con](https://www.codepedia.org/ama/tomcat-jdbc-connection-pool-configuration-for-production-and-development/#Watch_out_for)
* [Recursos](https://www.codepedia.org/ama/tomcat-jdbc-connection-pool-configuration-for-production-and-development/#Resources)

El pool de conexiones de Tomcat se configura como un **recurso** descrito en la [documentación de JDBC de Tomcat,](https://tomcat.apache.org/tomcat-7.0-doc/jndi-datasource-examples-howto.html) con la única diferencia de que hay que especificar el `factory`atributo y establecer el valor en `org.apache.tomcat.jdbc.pool.DataSourceFactory`. Para [Podcastpedia.org](https://github.com/CodepediaOrg/podcastpedia) , se configura en el archivo _context.xml_ de la aplicación web:\
[![archivo de contexto](https://www.codepedia.org/wp-content/uploads/2013/08/context-file-246x300.png)](https://www.codepedia.org/wp-content/uploads/2013/08/context-file.png)

#### Entorno de producción <a href="#production-environment" id="production-environment"></a>

```
  
    <Resource
    	  name="jdbc/pcmDB"
    	  auth="Container"
    	  type="javax.sql.DataSource"
    	  factory="org.apache.tomcat.jdbc.pool.DataSourceFactory"
    	  initialSize="34"
    	  maxActive="377"
    	  maxIdle="233"
    	  minIdle="89"
    	  timeBetweenEvictionRunsMillis="34000"
    	  minEvictableIdleTimeMillis="55000"
    	  validationQuery="SELECT 1"
    	  validationInterval="34000"
    	  testOnBorrow="true"
    	  removeAbandoned="true"
    	  removeAbandonedTimeout="55"
    	  username="xxx"
    	  password="yyy"
    	  driverClassName="com.mysql.jdbc.Driver"
    	  url="jdbc:mysql://localhost:3306/pcmdb?allowMultiQueries=true"
     />
   
 
```

**Dimensionamiento del pozo de conexión**

* `initialSize = 34`– el número inicial de conexiones que se crean cuando se inicia el grupo.
* `maxActive = 377`– El número máximo de conexiones activas que se pueden asignar desde este grupo al mismo tiempo. Este atributo se utiliza para limitar el número de conexiones que un grupo puede tener abiertas, de modo que se pueda realizar la planificación de capacidad en el lado de la base de datos, en el archivo de configuración de MySQL _my.cnf._`max_connections = 610 (maxActive+maxIdle)`
* `maxIdle = 233`– el número máximo de conexiones inactivas que deben mantenerse en el grupo en todo momento. Las conexiones inactivas se comprueban periódicamente (si está habilitado) y las conexiones que hayan estado inactivas durante más tiempo del `minEvictableIdleTimeMillis`permitido se liberarán.
* `minIdle= 89`– El número mínimo de conexiones establecidas que deben mantenerse en el grupo en todo momento. El grupo de conexiones puede reducirse por debajo de este número si fallan las consultas de validación.
* `timeBetweenEvictionRunsMillis = 34000`– El número de milisegundos de espera entre ejecuciones del hilo de validación/limpieza de conexiones inactivas. Este valor no debe ser inferior a 1 segundo. Determina la frecuencia con la que se comprueban las conexiones inactivas y abandonadas, y la frecuencia con la que se validan las conexiones inactivas.
* `minEvictableIdleTimeMillis = 55000`– el tiempo mínimo que un objeto puede permanecer inactivo en la piscina antes de que pueda ser retirado.

**Validar conexiones**

Al principio evité configurar la validación de la conexión, ya que pensé que afectaría al rendimiento. Sin embargo, varios problemas me obligaron a activarla. Con la siguiente configuración, las conexiones se validan, pero no más de cada 34 segundos:

* `testOnBorrow = true`Al configurar esto, los objetos se validarán antes de tomarlos prestados del grupo. Si un objeto no se valida, se eliminará del grupo y se intentará tomar prestado otro. _NOTA: para que un valor verdadero tenga efecto, el parámetro validationQuery debe ser una cadena no nula._
* `validationInterval = 34000`– Se utiliza para evitar validaciones excesivas; la validación se realiza como máximo con esta frecuencia (tiempo en milisegundos). Si una conexión requiere validación, pero ya se ha validado dentro de este intervalo, no se volverá a validar. Cuanto mayor sea el valor, mejor será el rendimiento, pero aumenta la probabilidad de que se presente una conexión obsoleta a la aplicación.
* `validationQuery= "SELECT 1"`– Consulta SQL de MySQL utilizada para validar las conexiones del pool antes de devolverlas al llamador.

**fugas de conexión**

Existen varias opciones de configuración que ayudan a detectar fugas de conexión:

* `removeAbandoned = true`– Indicador para eliminar las conexiones abandonadas si superan el límite `removeAbandonedTimeout`. Una conexión se considera abandonada y apta para su eliminación si ha estado en uso durante más tiempo que el límite `removeAbandonedTimeout`. De esta forma, las conexiones a la base de datos pueden recuperarse de las aplicaciones que no logran cerrar una conexión.
* `removeAbandonedTimeout = 54`– Tiempo de espera en segundos antes de que se pueda eliminar una conexión abandonada (en uso). El valor debe establecerse según la consulta de mayor duración que puedan tener sus aplicaciones.
* `validationQuery= "SELECT 1"`– Consulta SQL de MySQL utilizada para validar las conexiones del pool antes de devolverlas al llamador.

**El hilo de validación/limpieza**

`timeBetweenEvictionRunsMillis > 0 AND removeAbandoned=true AND removeAbandonedTimeout > 0`significa que el **limpiador de pool** está habilitado. El limpiador de pool es el hilo en segundo plano que puede probar las conexiones inactivas y redimensionar el pool mientras este está activo. El limpiador también es responsable de la detección de fugas de conexión. En este caso, el número de conexiones inactivas puede aumentar más allá de `maxIdle`, pero puede reducirse a `minIdle`si la conexión ha estado inactiva durante más tiempo que `minEvictableIdleTimeMilis`.

#### Entorno de desarrollo <a href="#development-environment" id="development-environment"></a>

```
  
    <Resource
    	 name="jdbc/pcmDB"
    	 auth="Container"
    	 type="javax.sql.DataSource"
    	 factory="org.apache.tomcat.jdbc.pool.DataSourceFactory"
    	 initialSize="5"
    	 maxActive="55"
    	 maxIdle="21"
    	 minIdle="13"
    	 timeBetweenEvictionRunsMillis="34000"
    	 minEvictableIdleTimeMillis="55000"
    	 validationQuery="SELECT 1"
    	 validationInterval="34"
    	 testOnBorrow="true"
    	 removeAbandoned="true"
    	 removeAbandonedTimeout="233"
    	 username="xxx"
    	 password="yyy"
    	 driverClassName="com.mysql.jdbc.Driver"
    	 url="jdbc:mysql://localhost:3307/pcmDB?allowMultiQueries=true"
    />
  
```

&#x20;La configuración del entorno de desarrollo es simplemente una copia de la configuración utilizada en producción, con valores más pequeños para los atributos que dimensionan el grupo y valores más grandes para los atributos que determinan las conexiones con fugas, de modo que pueda permanecer más tiempo en modo de depuración.

#### Cuidado con <a href="#watch-out-for" id="watch-out-for"></a>

Una de las excepciones que he obtenido fue:

```
  
    After mysql server was restarted or connection was lost I got this kind of errors:
    org.springframework.dao.DataAccessResourceFailureException:
    ### Error querying database.  Cause: com.mysql.jdbc.exceptions.jdbc4.MySQLNonTransientConnectionException: No operations allowed after connection closed.Connection was implicitly closed by the driver.
    ### The error may exist in maps/PodcastMapper.xml
    ### The error may involve org.podcastpedia.dao.PodcastDao.getTopRatedPodcasts
    ### The error occurred while executing a query
    ### SQL: SELECT      p.podcast_id,      p.url,   (select sum(rating) / count(rating) from ratings    where podcast_id = p.podcast_id and episode_id=-1) as podcast_rating,   (select count(rating)  from ratings      where podcast_id = p.podcast_id and episode_id=-1) as podcast_number_ratings,      p.number_visitors,      p.description,      p.short_description,      p.podcast_image_url,      p.title,      p.last_episode_url,      p.title_in_url,      p.publication_date       FROM      podcasts p     WHERE      p.availability=200     ORDER BY podcast_rating DESC      limit 0, ?;
    ### Cause: com.mysql.jdbc.exceptions.jdbc4.MySQLNonTransientConnectionException: No operations allowed after connection closed.Connection was implicitly closed by the driver.
    ; SQL []; No operations allowed after connection closed.Connection was implicitly closed by the driver.;
     nested exception is com.mysql.jdbc.exceptions.jdbc4.MySQLNonTransientConnectionException: No operations allowed after connection closed.Connection was implicitly closed by the driver.
   
 
```

&#x20;Esto se solucionó introduciendo los atributos de validación mencionados anteriormente.

Bueno, eso es todo… Gracias de nuevo a la comunidad de código abierto por desarrollar Tomcat, y un agradecimiento especial a [Filip Hanik](https://www.tomcatexpert.com/users/fhanik) por explicar la configuración del pool JDBC con tanta claridad.

Si detecta algún aspecto que podamos mejorar, póngase [en contacto con nosotros](mailto:contact@codingepdia.org?Subject=Apache%20optimization) o déjenos un mensaje.

#### Recursos <a href="#resources" id="resources"></a>

* [Apache Tomcat](https://tomcat.apache.org/)
* [El grupo de conexiones JDBC de Tomcat](https://tomcat.apache.org/tomcat-7.0-doc/jdbc-pool.html)
* [Apache Tomcat 7 – Guía práctica para fuentes de datos JNDI](https://tomcat.apache.org/tomcat-7.0-doc/jndi-datasource-examples-howto.html)
* [Uso del grupo de conexiones JDBC de Tomcat 7 en producción](https://www.tomcatexpert.com/blog/2012/01/24/using-tomcat-7-jdbc-connection-pool-production)
* [Configuración de jdbc-pool para alta concurrencia](https://www.tomcatexpert.com/blog/2010/04/01/configuring-jdbc-pool-high-concurrency)

***





## Pool de conexiones <a href="#firstheading" id="firstheading"></a>

* [Página](https://chuidiang.org/index.php?title=Pool_de_conexiones)
* [Discusión](https://chuidiang.org/index.php?title=Discusi%C3%B3n:Pool_de_conexiones\&action=edit\&redlink=1)
* [Leer](https://chuidiang.org/index.php?title=Pool_de_conexiones)
* [Editar](https://chuidiang.org/index.php?title=Pool_de_conexiones\&action=edit)
* [Ver historial](https://chuidiang.org/index.php?title=Pool_de_conexiones\&action=history)

He metido todos los artículos de esta wiki y de [http://chuidiang.org](http://chuidiang.org/) relativos a Java y JDBC en un pdf [Libro JDBC Java](https://chuidiang.org/index.php?title=Libro_JDBC_Java). A través del enlace puedes comprarlo si tienes interés.

Viene de [Establecer conexión con base de datos desde java](https://chuidiang.org/index.php?title=Establecer_conexi%C3%B3n_con_base_de_datos_desde_java)

### Problema de las conexiones a base de datos

Cuando trabajamos con [_java_](https://chuidiang.org/index.php?title=Categor%C3%ADa:Java) contra una [base de datos](https://chuidiang.org/index.php?title=Categor%C3%ADa:Base_de_datos), es normal encontrar en todos los ejemplos esta forma de [obtener un conexión con la base de datos](https://chuidiang.org/index.php?title=Conectar_java_con_mysql):

```
import java.sql.Connection;
import java.sql.DriverManager;
...
try
{
   Class.forName("com.mysql.jdbc.Driver");
   Connection conexion = DriverManager.getConnection("jdbc:mysql://localhost/agenda", "root", "LA_PASSWORD");
   ...

```

Para una aplicación sencilla y más o menos controlada, puede ser adecuado, pero en una aplicación más compleja es mejor utilizar otras formas. Veamos los problemas de este tipo de conexión:

* Abrir una conexión, realizar cualquier operación con la base de datos y cerrar la conexión puede ser lento. La apertura de las conexiones puede tardar más que la operación que queremos realizar. Es mejor, por tanto, abrir una o más conexiones y mantenerlas abiertas.
* Mantener una única conexión abierta compartida puede traernos problemas de concurrencia de hilos. Si varios hilos intentan hacer una operación con la conexión sin sincronizarse entre ellos, puede haber conflictos.

<br>

### Pedirle a alguien las conexiones : javax.sql.DataSource

Para evitar estos problemas, lo mejor es no abrir nosotros directamente la conexión con el _DriverManager_, sino delegar esta tarea en una clase que implemente la interface _javax.sql.DataSource_ y, por supuesto, elegir una implementación adecuada para nuestros propósitos.

En la API de java no hay ninguna implementación concreta de este _DataSource_, así que tendremos que buscarla fuera. Normalmente los .jar con los conectores a base de datos, como _ojdbc14.jar_ para [_Oracle_](https://chuidiang.org/index.php?title=Categor%C3%ADa:Oracle) o _java-mysql-connector-5.0.5-bin.jar_ para [_Mysql_](https://chuidiang.org/index.php?title=Categor%C3%ADa:MySQL) suelen tener varias implementaciones disponibles. Es cuestión de revisar la API de ellos y elegir la adecuada.

<br>

### Pool de conexiones

Una implementación interesante de estos _DataSource_ son los "Pool" de conexiones. Basicamente, estos "pool" nos facilitan conexiones según se las vamos pidiendo, pero las "reaprovechan" de una petición a otra. La idea es la siguiente: Le pedimos al _pool_ una conexión. Este busca una que esté libre y nos la da, apuntando que la tenemos nosotros y que deja de estar libre. Nosotros realizamos nuestra operación (consulta, inserción, borrado, ...) y cerramos la conexión. El _pool_ recibe esta petición de cierre y NO cierra la conexión, sino que la deja abierta y la vuelve a marcar libre para el siguiente que la pida.

Con esta forma de trabajo, el _pool_ mantiene varias conexiones abiertas que va sirviendo y marcando como usadas según se le piden. Cuando desde fuera se cierran esas conexiones, el pool no las cierra y las marca como libres, para poder reaprovecharlas.

### apache commons-bdcp: BasicDataSource

Un _pool_ de estas características es [BasicDataSource](http://commons.apache.org/dbcp/apidocs/org/apache/commons/dbcp/BasicDataSource.html) de [Apache Commons BDCP](http://commons.apache.org/dbcp/). Este _pool_ es además es configurable para que compruebe si la conexión es correcta antes de servirla al que se la pida, para que las verifique cada cierto tiempo, etc.

Vamos a ver un ejemplo con este _pool_. En primer lugar, necesitamos descargarnos los jar de :

* [apache commons-bdcp](http://commons.apache.org/downloads/download_dbcp.cgi)
* [apache commons-pool](http://commons.apache.org/downloads/download_pool.cgi)
* [apache commons-collections](http://commons.apache.org/downloads/download_collections.cgi)

o bien, si trabajamos con [maven](https://chuidiang.org/index.php?title=Categor%C3%ADa:Maven), nos bastará con añadir la depedencia en el pom.xml y maven se encargará de "tirar del hilo" y bajarse el resto de los jar.

```
   ...
   <dependency>
      <groupId>commons-dbcp</groupId>
      <artifacId>commons-dbcp</artifactId>
      <version>1.2.2</version>
      <scope>compile</scope>
   </dependency>
   ...
```

<br>

#### Uso por defecto de BasicDataSource

El código java es también sencillo. Debemos, en primer lugar, crear el _pool_, que es lo que deberemos pasar al resto del código, como un _DataSource_.

```
import javax.sql.DataSource; // Este es propio de java
import org.apache.commons.dbcp.BasicDataSource;  // Este es específico de Apache
...
BasicDataSource basicDataSource = new BasicDataSource();
// Ejemplo con base de datos MySQL
basicDataSource.setDriverClassName("com.mysql.jdbc.Driver");
basicDataSource.setUrl("jdbc:mysql://localhost:3306/nombre_bd");
basicDataSource.setUsername("usuario");
basicDataSource.setPassword("password");

// Pasamos el DataSource a las clases que lo necesiten.
claseQueHaceLasConsultas.setDataSource(basicDataSource);
```

La clase que haga las consultas debería tener un método setDataSource(DataSource), para recibir este _pool_ de conexiones. DataSource es una interface propia de java, por lo que no estamos metiendo en esa clase ninguna depedencia de Apache commons. Un código simple para esa clase podría ser este

```
import javax.sql.DataSource;

public class ClaseQueHaceLasConsultas() {

   /** El DataSource */
   private DataSource dataSource=null;

   /** Recibe y guarda el DataSource */
   public void setDataSource (DataSource dataSource) {
      this.dataSource = dataSource;
   }

   /** Pide la Connection al DataSource, hace la consulta y
     * cierra la conexión */
   public void hazConsulta () {
      
      Connection conexion = null;
      try {
         conexion = dataSource.getConnection();
         // realización de la consulta
      } catch (Exception e) {
         // tratamiento de error
      } finally {
         if (null != conexion)
            conexion.close();
      }
   }
}
```

Es importante acordarse de cerrar la conexión después de haberla usado porque si no, el _pool_ pensará que todavía la necesitamos y la mantendrá reservada todo el tiempo. Por ello, es buena costumbre poner el _close()_ en el _finally_ del _try-catch_, de forma que se cierre siempre, vaya bien o mal la consulta.

<br>

#### Configuración adicional

En la [API de _BasicDataSource_](http://commons.apache.org/dbcp/apidocs/org/apache/commons/dbcp/BasicDataSource.html) vemos que hay infinidad de métodos que nos permiten configurar el comportamiento del _BasicDataSource_. Algunas de ellas son las siguientes:

Número de conexiones reales

* _setMaxActive()_ : Número máximo de conexiones que se pueden abrir simultáneamente.
* _setMinIdle()_ : Número mínimo de conexiones inactivas que queremos que haya. Si el número de conexiones baja de este número, se abriran más.
* _setMaxIdle()_ : Número máximo de conexiones inactivas que queremos que haya. Si hay más, se irán cerrando.
* _setInitialSize()_ : Número de conexiones que se quiere que se abran en cuanto el _pool_ comienza a trabajar (se llama por primera vez a _getConnection(), setLogwriter(), setLoginTimeout(), getLoginTimeout() o getLogWriter()_. Debe llamarse a _setInitialSize()_ antes de llamar a cualquiera de estos métodos y después no puede cambiarse el valor.

Verificación automática de la conexión

El _pool_ puede verificar que la conexión funciona correctamente cuando se la pasa a alguien, cuando se la devuelven y mientras está inactiva, de forma que intentará la reconexión en caso de fallo. Algunos de los métodos implicados son:

* _setValidationQuery()_ : SQL a usar con la validación. En MySQL suele ser SELECT 1, en Oracle SELECT 1 FROM DUAL.
* _setTestOnBorrow()_ : Indica si se debe testear la conexión antes de pasársela a alguien.
* _setTestOnReturn()_ : Indica si se debe testear la conexión cuando ese alguien la libera.
* _setTextWhileIdle()_ : Indica si se debe testear la conexión mientras está inactiva. El tiempo entre tests se puede fijar con _setTimeBetweenEvictionRunsMillis()_
