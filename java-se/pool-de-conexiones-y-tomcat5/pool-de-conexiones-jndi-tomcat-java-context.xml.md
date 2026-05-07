# pool de conexiones JNDI, Tomcat, JAVA, context.xml

[http://tomcat.apache.org/tomcat-6.0-doc/jndi-datasource-examples-howto.html#Oracle\_8i,\_9i\_&\_10g](http://tomcat.apache.org/tomcat-6.0-doc/jndi-datasource-examples-howto.html#Oracle_8i,_9i_&_10g)

1\. Context configuration\
\<Resource name=»jdbc/myoracle» auth=»Container»\
type=»javax.sql.DataSource» driverClassName=»oracle.jdbc.OracleDriver»\
url=»jdbc:oracle:thin:@127.0.0.1:1521:mysid»\
username=»scott» password=»tiger» maxActive=»20″ maxIdle=»10″\
maxWait=»-1″/>

2\. web.xml configuration\
\<resource-ref>\
\<description>Oracle Datasource example\</description>\
\<res-ref-name>jdbc/myoracle\</res-ref-name>\
\<res-type>javax.sql.DataSource\</res-type>\
\<res-auth>Container\</res-auth>\
\</resource-ref>

3\. Code example\
Context initContext = new InitialContext();\
Context envContext  = (Context)initContext.lookup(«java:/comp/env»);\
DataSource ds = (DataSource)envContext.lookup(«jdbc/myoracle»);\
Connection conn = ds.getConnection();\
//etc.

* JNDI (Java Naming Directory Interface). Configurando recursos en Tomcat.

[http://ambellido.blogspot.com/2012/02/jndi-java-naming-directory-interface.html](http://ambellido.blogspot.com/2012/02/jndi-java-naming-directory-interface.html)

* Setting up a JNDI connection pool with Tomcat

[http://docs.geoserver.org/stable/en/user/tutorials/tomcat-jndi/tomcat-jndi.html](http://docs.geoserver.org/stable/en/user/tutorials/tomcat-jndi/tomcat-jndi.html)

– A Oracle XE install on a Linux system provides the driver at /usr/lib/oracle/xe/app/oracle/product/10.2.0/server/jdbc/lib/ojdbc14.jar, and that file needs to be copied into Tomcat shared libs directory, _TOMCAT\_HOME_/lib

– Once that is done, the Tomcat configuration file _TOMCAT\_HOME_/conf/context.xml needs to be edited in order to setup the connection pool. In the case of a local Oracle XE the setup might look like:

\<Context> … \<Resource name=»jdbc/oralocal» auth=»Container» type=»javax.sql.DataSource» url=»jdbc:oracle:thin:@localhost:1521:xe» driverClassName=»oracle.jdbc.driver.OracleDriver» username=»dbuser» password=»dbpasswd» maxActive=»20″ maxIdle=»3″ maxWait=»10000″ poolPreparedStatements=»true» maxOpenPreparedStatements=»100″ validationQuery=»SELECT SYSDATE FROM DUAL» /> \</Context>

La configuración del pool de muestra es bastante completo hecho y derecho:\
• como máximo 20 conexiones activas (número máximo de conexión que lleguen a utilizarse en paralelo)\
• más de 3 conexiones mantenidas en el pool sin usar\
• declaración preparada el pooling (muy importante para el buen desempeño)\
• más de 100 comandos preparados en el pool\
• Una consulta de validación que comprueba la doble conexión todavía está vivo antes de utilizarlo (esto no es necesario si hay garantizan los enlaces nunca caerá, ya sea debido a que el servidor fuerza cerrándolos, o problemas de red / mantenimiento).

* Hibernate con JDBC o JNDI

[https://groups.google.com/forum/#!msg/javasos/FyBHA9l9gtE/SIQ6G8DUZY8J](https://groups.google.com/forum/#!msg/javasos/FyBHA9l9gtE/SIQ6G8DUZY8J)

Si, en ambos casos es via JDBC, JNDI solo agrega un nivel de indireccion.

Ventajas JNDI:\
– Separación de configuración del JDBC y pool de conexiones de la configuración de Hibernate.\
– Puedes reusar el pool de conexiones (Ya sea Tomcat, tu webapp en código que no requiere Hibernate, u otra webapp ejecutando en el mismo Tomcat.

* **How to Setup Global JNDI Mapping  for Oracle JDBC Connection Pooling with Tomcat**

[http://www.microdeveloper.com/html/JNDI\_Orcl\_Tomcat1p.html](http://www.microdeveloper.com/html/JNDI_Orcl_Tomcat1p.html)

* Universal Connection Pool para Driver JDBC de Oracle

[http://www.javamexico.org/blogs/luxspes/universal\_connection\_pool\_para\_driver\_jdbc\_de\_oracle](http://www.javamexico.org/blogs/luxspes/universal_connection_pool_para_driver_jdbc_de_oracle)

– [connection pooling](http://es.wikipedia.org/wiki/Connection_pool) para hacer un uso adecuado de los recursos de la base de datos.

– Tomcat implementa connection pooling llamado DBCP, pero a menudo falla al cerrar las conexiones por lo que acaba desperdiciando recursos del servidor.

– El Driver JDBC de Oracle cuenta con 2 modos de pooling que si bien son mas confiables a la hora de recuperar recursos tampoco estan libres de problemas:

1. Pooling Explicito (oracle.jdbc.pool.OracleConnectionCacheImpl)Obsoleto. Desventajas: inestabilidad por que no cuenta con capacidad intrinseca para validar conexiones
2. Pooling Implicito (oracle.jdbc.pool.OracleDataSource) :Obsoleto, Ventajas: Compatible con supervisión mediante [LambdaProbe](http://www.lambdaprobe.org/d/index.htm). Desventajas: Sigue sufriendo de inestabilidad, por sigue sin contar con capacidad intrinseca para validar conexiones

– los errores tipicos de los 2 modos originales de pooling: “Conexion Cerrada” para una conexion que acabamos de obtener del pool, o “El cache de conexiones ha caducado” igualmente para cuando reclamamos una conexion del pool que no se habia utilizado desde hace un buen rato.

* [Usando DataSource de Oracle](http://www.tsoracle.com/wparchives/2007/02/22/usando-datasource-de-oracle/)

[http://www.tsoracle.com/wparchives/2007/02/22/usando-datasource-de-oracle/](http://www.tsoracle.com/wparchives/2007/02/22/usando-datasource-de-oracle/)

CONEXIONES ESTANDAR

\<resource name=»jdbc/NombreCoreDS»\
auth=»Container»\
type=»javax.sql.DataSource»\
factory=»org.apache.tomcat.dbcp.dbcp.BasicDataSourceFactory»\
maxActive=»100″\
maxIdle=»30″\
maxWait=»10000″\
username=»Usuario»\
password=»Contraseña»\
driverClassName=»oracle.jdbc.driver.OracleDriver»\
url=»jdbc:oracle:thin:@nombreHost:puerto:NombreSID»\
removeAbandoned=»true»\
removeAbandonedTimeout=»60″\
logAbandoned=»true»\
/>

CONEXIONES ORACLE\
\<Resource name=»jdbc/NombreCoreDS»\
auth=»Container»\
scope=»Shareable»\
type=»oracle.jdbc.pool.OracleDataSource»\
factory=»oracle.jdbc.pool.OracleDataSourceFactory»\
maxActive=»100″\
maxIdle=»30″\
maxWait=»10000″\
user=»Usuario»\
password=»Contraseña»\
driverClassName=»oracle.jdbc.pool.OracleDataSource»\
url=»jdbc:oracle:thin:@nombreHost:puerto:NombreSID»\
removeAbandoned=»true»\
removeAbandonedTimeout=»60″\
logAbandoned=»true»\
/>

* Configuracion de bases de datos en un pool de conexiones JNDI

[https://soporte.enredados.com/index.php?\_m=knowledgebase&\_a=viewarticle\&kbarticleid=49](https://soporte.enredados.com/index.php?_m=knowledgebase&_a=viewarticle\&kbarticleid=49)

\<?xml version=»1.0″ encoding=»UTF-8″?> \<Context path=»» docBase=»CONTEXTO» debug=»0″ reloadable=»true» crossContext=»true»> \<Resource name=»jdbc/NOMBRE\_BD» auth=»Container» type=»javax.sql.DataSource» maxActive=»20″ maxIdle=»10″ maxWait=»200″ username=»USUARIO\_BD» password=»CONTRASENA\_BD» driverClassName=»com.mysql.jdbc.Driver» url=»jdbc:mysql://localhost:3306/NOMBRE\_BD»/> \</Context>

[Pool de conexiones con JNDI en Tomcat](https://businessworldti.wordpress.com/content/pool-de-conexiones-con-jndi-en-tomcat)

[http://www.lelissam.com.ar/content/pool-de-conexiones-con-jndi-en-tomcat](http://www.lelissam.com.ar/content/pool-de-conexiones-con-jndi-en-tomcat)

`<Resource name="jdbc/Database" auth="Container" type="javax.sql.DataSource"`\
`maxActive="100" maxIdle="30" maxWait="10000"`\
`username="myUsername" password="myPassword" driverClassName="com.mysql.jdbc.Driver"`\
`url="jdbc:mysql://localhost:3306/myDatabase"/>`

* Origen de datos JNDI en Tomcat

**Significado de los parámetros**

* **url**:\
  La cadena de conexión de la base de datos
* **driverClassName**:\
  El nombre de la clase del driver JDBC
* **username**:\
  El nombre de usuario para acceder a la base de datos
* **password**:\
  La constraseña del usuario para acceder a la base de datos
* **maxActive**:\
  El número máximo de conexiones en el pool de conexiones (0=ilimitado)
* **maxIdle**:\
  El número máximo de conexiones inactivas a retener en el pool de conexiones (0=ilimintado)
* **maxWait**:\
  El tiempo máximo a esperar para obtener una conexión, en milisegundos (-1=ilimitado)
* **removeAbandoned**:\
  Si removeAbandoned = true entonces cuando haya pocas conexiones disponibles en el pool de conexiones se recuperará y reciclará cualquier conexión abandonada que se encuentre.
* **removeAbandonedTimeout**:\
  El número de segundos que una conexión tiene que estar inactiva hasta que sea considerada abandonada por el pool de conexiones (por defecto 300).
* **logAbandoned**:\
  Si logAbandoned = true el pool de conexiones guardará un seguimiento de pila del código que abandonó un recurso de conexión.
