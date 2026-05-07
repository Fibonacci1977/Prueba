# Conexión directa vs pool

1. > Hola antes de nada, salud para todos. Escribo esto porque tengo entendido que para establecer una conexión a una base de datos, existen dos modos:\
   > \
   > 1º Conexión directa.\
   > 2º Conexión por pool de conexiones.\
   > \
   > Quisiera saber la diferencia entre ambas, y cómo se implementan cada una de ellas en una aplicación... sobre todo de la 2ª. El lenguaje de programación si puede ser en Java mejor, pues estoy haciendo algo en WebLogic y toda la información que se me proporcione será más que bienvenida.\
   > \
   > Gracias de antemano

> Buenas y bienvenido! La diferencia entre ambas es que en la conexión directa utilizas un driver que te facilita el fabricante del motor de la base de datos para establecer la conexión, y en el pool de conexiones empleas un DataSource.\
> \
> Ambas deben llamar en Java a getConnection(). Pero una lo hace desde el driver y la otra desde el DataSource.\
> \
> En la conexión directa, a través del driver, tu debes encargarte de abrir y cerrar las conexiones, mientras que en el pool, hay un conjunto de conexiones disponibles que se van reutilizando a medida que las transacciones terminan. Normalmente es el servidor quien establece y define ese pool de conexiones abiertas. La aplicación solicita establecer una conexión con la base de datos, y se la pide a éste para que se la asigne.\
> \
> A modo de ejemplo, si tienes un servidor mysql, la forma de implementar ambos métodos en java sería algo así:\
> \
> 1º Conexion directa:\
> Código:
>
> ```
> private static Connection getConexionDirecta() throws Excepcion {
> 	Connection con = null;
> 	String conector = "com.mysql.jdbc.Driver";
>
>         String servidor = "servidorBD";
>         String puerto = "3306";
>         String usuario = "user";
>         String password = "pass";
>         String bd = "esquema_basedatos";
>
>         String cadenaConexion = "jdbc://mysql://"+servidorBD+":"+puerto+"/"+bd;
>
> 	try {
> 		Class.forName(conector);
> 		con = java.sql.DriverManager.getConnection(cadenaConexion, usuario, password);
> 	} catch (final SQLException e) {
> 		throw new Excepcion("Error conexion", e);
> 	} catch (final ClassNotFoundException e) {
> 		throw new Excepcion("Error conexion", e);
> 	}
> 	return con;
> }
> ```
>
> \
> 2º Conexion por pool:\
> Código:
>
> ```
> private static Connection getConexionPool() throws Excepcion {
> 	Connection con = null;
>         String jndi = "miJNDI";
>
> 	try {
>                 Context initContext = new InitialContext();
>                 DataSource ds = (DataSource) initContext.lookup(jndi);
>                 con = ds.getConnection();
> 	} catch (final NamingException e) {
> 		throw new Excepcion("Error configuracion DataSource", e);
> 	} catch (final SQLException e) {
> 		throw new Excepcion("Error conexion", e);
> 	}
> 	return con;
> }
> ```
>
> \
> Observa que en la conexión por pool, no necesitas saber ningún parámetro de conexión (cadena conexión, usuario, clave, etc...) con la base de datos, tal y como se hace en la conexión directa. En su lugar, lo que se pasa es el JNDI (Java Naming and Directory Interface), que es una cadena que identifica el pool a utilizar. Dicho pool, debe ser configurado en el servidor de la aplicación.\
> \
> En tu caso, dices que estás utilizando WebLogic, asi que para configurar un nuevo DataSource, lo que necesitas es crearte o definirte un nuevo "orígen de datos". Esto lo puedes hacer de dos formas, bien a través de la consola que te ofrece WebLogic:\
> \
> Código:
>
> ```
> http://localhost:7001/console
> ```
>
> , suponiendo claro está que el servidor esté en "localhost".\
> \
> O bien, a través del fichero de configuración config.xml.\
> \
> Un saludo.

***

\
&#x20;

***

Configuring JDBC Connection Pools

A connection pool contains a group of JDBC connections that are created when the connection pool is registered—when starting up WebLogic Server or when deploying the connection pool to a target server or cluster. Connection pools use a JDBC driver to create physical database connections. Your application borrows a connection from the pool, uses it, then returns it to the pool by closing it.

Figure 11-1 Connection Pool Architecture

![](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/wwimages/jdbc_arch_cpool.gif)\
&#x20;

All of the settings you make with the Administration Console are static; that is, all settings persist even after you stop and restart WebLogic Server. You can create dynamic connection pools—those that you expect to use and delete while the server is running—using the command line (see [Commands for Managing JDBC Connection Pools](https://docs.oracle.com/cd/E13222_01/wls/docs81b/admin_ref/cli.html#jdbc) in the _WebLogic Server Command Reference_ at ../admin\_ref/cli.html#jdbc) or programmatically using the API (see [Creating a Connection Pool Dynamically](https://docs.oracle.com/cd/E13222_01/wls/docs81b/jdbc/programming.html#dynamic_conn_pool) in Programming WebLogic JDBC).

Connection pool settings are persisted in the config.xml file, including settings for dynamically created connection pools (until you programmatically delete the connection pool). For information about entries in the config.xml file, see the [JDBCConnectionPool](https://docs.oracle.com/cd/E13222_01/wls/docs81b/config_xml/JDBCConnectionPool.html) section of the _Configuration Reference Guide_.

Related Information

* [Creating and Configuring a JDBC Connection Pool](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/jdbc_connection_pools.html#1106131)
* [JDBC DataSources](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/jdbc_datasources.html#1105912)
* Read more about [Connection Pools](https://docs.oracle.com/cd/E13222_01/wls/docs81b/jdbc/programming.html#programming001) in _Programming WebLogic JDBC_.

&#x20;

***

Using the JDBC Connection Pool Assistant

You use the JDBC Connection Pool Assistant to create JDBC connection pools. The JDBC Connection Pool Assistant helps you create and deploy a connection pool by prompting you for database and driver information and then constructing the connection attributes required by your JDBC driver, such as the driver class name and the database URL.

**Notes:** JDBC drivers listed in the JDBC Connection Pool Assistant are not necessarily certified for use with WebLogic Server. In keeping with the goal of the JDBC Connection Pool Assistant, JDBC drivers are listed as a convenience to help you create a connection to many of the database management systems available.

You must install JDBC drivers in order to use them to create database connections in a connection pool. Drivers are listed in the JDBC Connection Pool Assistant with known required configuration options to help you configure a connection pool. The JDBC drivers in the list are not necessarily installed. Driver installation can include setting system Path, Classpath, and other environment variables.

When a JDBC driver is updated, configuration requirements may change. The JDBC Connection Pool Assistant uses known configuration requirements at the time the WebLogic Server software was released. If configuration options for your JDBC driver have changed, you may need to manually override the configuration options displayed in Step 3 of the JDBC Connection Pool Assistant or in the property pages for the connection pool.

Creating and Configuring a JDBC Connection Pool

1. Click to expand the Services and JDBC nodes.
2. Right-click the Connection Pools node and select Configure a New JDBC Connection Pool. The JDBC Connection Pool Assistant opens in the right pane.
3.  In Step 1 - Choose database, follow these steps:

    1. Database type, select the DBMS of the database that you want to connect to. If your DBMS is not listed, select Other.
    2. In Database driver, select the JDBC driver you want to use to connect to the database. The list includes common JDBC drivers for the selected DBMS. Click Continue.

    **Note:** You must install JDBC drivers in order to use them to create database connections in a connection pool. Drivers are listed in the JDBC Assistant with known required configuration options to help you configure a connection pool. Driver installation also includes setting system Path, Classpath, and other environment variables.
4. In Step 2 - Define connection properties, follow these steps:
   1. In Name, enter a name for the new connection pool. The name should be unique within the domain.
   2. Under Connection Properties, provide the information requested. The required attributes vary by the DBMS and JDBC driver you selected in the previous step. Many attributes include a common default value. Verify these values for your environment.
   3. Click Continue.
5.  In Step 3 - Test database connection, verify the connection properties and then click Test Connection. WebLogic Server attempts to ping your database using the connection properties you provided. The JDBC driver must be installed and configured on the server (on the Administration server in multi-server environments) for the test to succeed.

    If the test is successful, Step 4 - Create and deploy is displayed. If the test is unsuccessful, an error message is displayed at the top of the page. Check the values on the page and correct any errors, then test the connection again.

    You can click Skip this Step to skip the test and continue configuring the connection pool. Note that if you create and deploy a connection pool with errors, the connection pool configuration will be created, but the connection pool will not actually be deployed to servers or clusters. Also, when you restart servers, the servers will start with errors.
6. In Step 4 - Create and deploy, select the servers and clusters on which you want to deploy the connection pool. If you only have one server in your domain, the connection pool is automatically deployed to the server. Click Create and Deploy to complete the process.

In most cases, you should create a data source to use with a connection pool. To create a data source, see [Creating and Configuring a JDBC Data Source](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/jdbc_datasources.html#1107735).

Database Passwords in Connection Pool Configuration

When you create a connection pool, you typically include at least one password to connect to the database. If you use an open string to enable XA, you may use two passwords. You can enter the passwords as a name-value pair in the Properties field or you can enter them in their respective fields:

* **Password**. Use this field to set the database password. This value overrides any password value defined in the Properties passed to the tier-2 JDBC Driver when creating physical database connections. The value is encrypted in the config.xml file (stored as the Password attribute in the JDBCConnectionPool tag) and is hidden on the administration console.
* **Open String Password**. Use this field to set the password in the open string that the transaction manager in WebLogic Server uses to open a database connection. This value overrides any password defined as part of the open string in the Properties field. The value is encrypted in the config.xml file (stored as the XAPassword attribute in the JDBCConnectionPool tag) and is hidden on the Administration Console. At runtime, WebLogic Server reconstructs the open string with the password you specify in this field. The open string in the Properties field should follow this format:
* > ```
  > openString=Oracle_XA+Acc=P/userName/+SesTm=177+DB=demoPool+Threads=true=Sqlnet=dvi0+logDir=.
  > ```
* Note that after the userName there is no password.

If you specify a password in the Properties field when you first configure the connection pool, WebLogic Server removes the password from the Properties string and sets the value as the Password value in an encrypted form the next time you start WebLogic Server. If there is already a value for the Password attribute for the connection pool, WebLogic Server does not change any values. However, the value for the Password attribute overrides the password value in the Properties string. The same behavior applies to any password that you define as part of an open string. For example, if you include the following properties when you first configure a connection pool:

> ```
> user=scott;
> password=tiger;
> openString=Oracle_XA+Acc=p/scott/tiger+SesTm=177+db=jtaXaPool+Threads=true+Sqlnet=lcs817+logDir=.+dbgFl=0x15;server=lcs817
> ```

The next time you start WebLogic Server, it moves the database password and the password included in the open string to the Password and Open String Password attributes, respectively, and the following value remains for the Properties field:

> ```
> user=scott;
> openString=Oracle_XA+Acc=p/scott/+SesTm=177+db=jtaXaPool+Threads=true+Sqlnet=lcs817+logDir=.+dbgFl=0x15;server=lcs817
> ```

After a value is established for the Password or Open String Password attributes, the values in these attributes override the respective values in the Properties attribute. That is, continuing with the previous example, if you specify tiger2 as the database password in the Properties attribute, WebLogic Server ignores the value and continues to use tiger as the database password, which is the current encrypted value of the Password attribute. To change the database password, you must change the Password attribute.

**Note:** The value for Password and Open String Password do not need to be the same.

Cloning a JDBC Connection Pool

1. Click to expand the Services, JDBC, and Connection Pool nodes.
2. Right-click the connection pool you want to clone and select Clone _poolname_. A dialog displays in the right pane showing the tabs associated with cloning a connection pool. All attribute values except Name are the same as those in cloned pool, including Connection attributes and deployment targets.
3. Enter a new Name. Optionally, you can modify the URL, Driver Classname, and Properties attribute fields. For more information about connection pool general attributes, see [Attributes](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcconnectionpool_config_general.html#1104722).
4. Click Clone to create a connection pool with the attributes you specified on the General tab and with cloned values on all other tabs. The new connection pool is added under the Connection Pools node in the left pane.
5. Optionally, click the remaining tabs for the connection pool and change the attribute fields. Click Apply to save any changes you make.

Deploying a JDBC Connection Pool to One or More Servers or Clusters

1. In the left pane, click to expand the Services, JDBC, and Connection Pools nodes to display the list of connection pools in the current domain.
2. Click the connection pool that you want to deploy. A dialog displays in the right pane showing the tabs associated with this instance.
3. Click the Target and Deploy tab and select the servers or clusters on which you want to deploy the connection pool. Click Apply to save your changes.

When deploying a JDBC connection pool on a cluster, in most cases you should deploy the connection pool to the entire cluster. You should deploy the related data source to the same targets.

Testing a JDBC Connection Pool

On the JDBC Connection Pool—>Testing tab, you can test a JDBC connection in a connection pool on each server on which the connection pool is deployed.

When you test a connection pool, WebLogic Server reserves and releases a connection from the connection pool.

To make the test more meaningful, make sure that Test Reserved Connections or Test Released Connections is selected on the Configuration—>Connections tab (under Advanced Options). If either of these options is selected, WebLogic Server not only reserves and releases a connection, but also tests the physical database connection. See Test Reserved Connections in [Attributes](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcconnectionpool_config_connections.html#1104722).

To see a description of the information displayed on the JDBC connection Pool—>Testing tab, see [Attributes](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcconnectionpool_testing.html#1105775).

To test a connection in a connection pool, follow these steps:

1. In the left pane, click to expand the Services, JDBC, and Connection Pool nodes to display the list of connection pools in the current domain.
2. Click the connection pool that you want to deploy. A dialog displays in the right pane showing the tabs associated with this instance.
3. Click the Testing tab. The Testing tab displays a list of instances of the selected connection pool. Each server on which the connection pool is deployed is listed. Each server can have only one instance of a connection pool.
4. Click the Test Pool button for each instance of the connection pool. Test results are displayed at the top of the pane.
5. Optionally, click the Test pool on all servers button to test all instances of the connection pool. This button is only available if you have more than one instance of the connection pool in your domain.

Configuring the Statement Cache for a JDBC Connection Pool

On the JDBC Connection Pool—>Configuration—>Connections tab, you can configure statement cache attributes for a connection pool. For more information about the statement cache, see [Increasing Performance with the Statement Cache](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/jdbc_connection_pools.html#1107805). To configure the statement cache, follow these steps:

1. In the left pane, click to expand the Services, JDBC, and Connection Pool nodes to display the list of connection pools in the current domain.
2. Click the connection pool that you want to deploy. A dialog displays in the right pane showing the tabs associated with this instance.
3. Click the Configuration tab, then click the Connections tab.
4. In Statement Cache Type, select one of the following options:
   * LRU - After the statementCacheSize is met, the Least Recently Used statement is removed when a new statement is used.
   * Fixed - The first statementCacheSize number of statements is stored and stay fixed in the cache. No new statements are cached unless the cache is manually cleared.
   * See [Statement Cache Algorithms](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/jdbc_connection_pools.html#1115624) for more information.
5. In Statement Cache Size, enter the number of statements to cache per connection per connection pool instance. The default value is 10. See [Statement Cache Size](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/jdbc_connection_pools.html#1116241) for more information.
6. Click Apply to save your changes.

Adding a Note to a JDBC Connection Pool

1. In the left pane, click to the JDBC node to expand it.
2. Click the Connection Pools node to expand it and show the list of connection pools defined in your domain.
3. Click the connection pool to which you want to add a note. A dialog displays in the right pane showing tabs with attributes for the connection pool.
4. Click the Notes tab. Type the note in the Notes field.
5. Click Apply to save your changes.

&#x20;

***

Application-Scoped JDBC Connection Pools

When you package your enterprise applications, you can include the weblogic-application.xml supplemental deployment descriptor, which you use to configure _application scoping_. Within the weblogic-application.xml file, you can configure JDBC connection pools that are created when you deploy the enterprise application.

An instance of the connection pool is created with each instance of your application. This means an instance of the pool is created with the application on each node that the application is targeted to. It is important to keep this in mind when considering pool sizing.

Connection pools created in this manner are known as _application-scoped connection pools_, _app scoped pools_, _application local pools_, _app local pools_, or _local pools_, and are scoped for the enterprise application only. That is, they are isolated for use by the enterprise application.

For more information about application scoping and application scoped resources, see:

* [Overview of Application Scoping](https://docs.oracle.com/cd/E13222_01/wls/docs81b/xml/xml_appscop.html)
* [weblogic-application.xml Deployment Descriptor Elements](https://docs.oracle.com/cd/E13222_01/wls/docs81b/programming/app_xml.html#app-scoped-pool)
* Packaging Enterprise Applications
* [Two-Phase Deployment](https://docs.oracle.com/cd/E13222_01/wls/docs81b/deployment/concepts.html)

&#x20;

***

Connection Pool and Data Source Configuration Guidelines

Drivers Supported for Local Transactions

JDBC 2.0 drivers that support the JDBC Core 2.0 API (java.sql), such as the WebLogic jDriver for Oracle. The API allows you to create the class objects necessary to establish a connection with a data source, send queries and update statements to the data source, and process the results.

Drivers Supported for Distributed Transactions Using XA

Any JDBC driver that supports JDBC 2.0 distributed transactions standard extension interfaces (javax.sql.XADataSource, javax.sql.XAConnection, javax.transaction.xa.XAResource), such as the WebLogic jDriver for Oracle/XA.

Drivers Supported for Distributed Transactions without XA

Any JDBC driver that supports JDBC 2.0 Core API but does not support JDBC 2.0 distributed transactions standard extension interfaces (non-XA). Only one non-XA JDBC driver can participate in a distributed transaction. See [Configuring Non-XA JDBC Drivers for Distributed Transactions](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/jdbc_connection_pools.html#1120770)

Configuring JDBC Drivers for Local Transactions

To configure JDBC drivers for local transactions, set up the JDBC connection pool as follows:

* Specify the Driver Classname attribute as the name of the class supporting the java.sql.Driver interface.
* Specify the data properties. These properties are passed to the specific Driver as driver properties.

For more information on WebLogic two-tier JDBC drivers, refer to the BEA documentation for the specific driver you are using: [_Using WebLogic jDriver for Oracle_](https://docs.oracle.com/cd/E13222_01/wls/docs81b/oracle/index.html) and [_Using WebLogic jDriver for Microsoft SQL Server_](https://docs.oracle.com/cd/E13222_01/wls/docs81b/mssqlserver4/index.html). If you are using a third-party driver, refer to [Using Third-Party JDBC XA Drivers with WebLogic Server](https://docs.oracle.com/cd/E13222_01/wls/docs81b/jta/thirdpartytx.html) in _Programming WebLogic JTA_ and the vendor-specific documentation. The following tables show sample JDBC connection pool and Data Source configurations using the WebLogic jDrivers.

The following table shows a sample connection pool configuration using the WebLogic jDriver for Oracle.

**Note:** The following configuration examples use a Password attribute. The Password attribute value overrides any password defined in Properties (as a name/value pair). This attribute is passed to the 2-tier JDBC driver when creating physical database connections. The value is stored in an encrypted form in the config.xml file and can be used to avoid storing passwords in clear text in that file.

Table 11-1 WebLogic jDriver for Oracle: Connection Pool Configuration

<table data-header-hidden><thead><tr><th valign="top"></th><th valign="top"></th></tr></thead><tbody><tr><td valign="top"><strong>Attribute Name</strong></td><td valign="top"><strong>Attribute Value</strong></td></tr><tr><td valign="top">General Tab (<a href="https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcconnectionpool_config_general.html#1104829">JDBC Connection Pool --> Configuration --> General</a>)</td><td valign="top"></td></tr><tr><td valign="top">Name</td><td valign="top">myConnectionPool</td></tr><tr><td valign="top">URL</td><td valign="top">jdbc:weblogic:oracle</td></tr><tr><td valign="top">Driver Classname</td><td valign="top">weblogic.jdbc.oci.Driver</td></tr><tr><td valign="top">Properties</td><td valign="top">user=scott;server=localdb</td></tr><tr><td valign="top">Password</td><td valign="top">tiger (This value overrides any password defined in Properties as a name value pair)</td></tr><tr><td valign="top">Connections Tab (<a href="https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcconnectionpool_config_connections.html#1104829">JDBC Connection Pool --> Configuration --> Connections</a>)</td><td valign="top"></td></tr><tr><td valign="top">Initial Capacity</td><td valign="top">1</td></tr><tr><td valign="top">Max Capacity</td><td valign="top">15</td></tr><tr><td valign="top">Capacity Increment</td><td valign="top">1</td></tr><tr><td valign="top">Shrink Period</td><td valign="top">15</td></tr><tr><td valign="top">Test Table Name</td><td valign="top">dual</td></tr><tr><td valign="top">Target and Deploy (<a href="https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcconnectionpool_targetdeploy.html#1106545">JDBC Connection Pool --> Target and Deploy</a>)</td><td valign="top"></td></tr><tr><td valign="top">Targets</td><td valign="top">myserver</td></tr></tbody></table>

The following table shows a sample Data Source configuration using the WebLogic jDriver for Oracle.

Table 11-2 Data Source Configuration

<table data-header-hidden><thead><tr><th valign="top"></th><th valign="top"></th></tr></thead><tbody><tr><td valign="top"><strong>Attribute Name</strong></td><td valign="top"><strong>Attribute Value</strong></td></tr><tr><td valign="top">Configuration Tab (<a href="https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcdatasource_config.html#1104829">JDBC Data Source --> Configuration</a>)</td><td valign="top"></td></tr><tr><td valign="top">Name</td><td valign="top">myDataSource</td></tr><tr><td valign="top">JNDI Name</td><td valign="top">myconnection</td></tr><tr><td valign="top">Pool Name</td><td valign="top">myConnectionPool</td></tr><tr><td valign="top">Row Prefetch Size</td><td valign="top">48</td></tr><tr><td valign="top">Stream Chunk Size</td><td valign="top">256</td></tr><tr><td valign="top">Target and Deploy Tab (<a href="https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcdatasource_targetdeploy.html#1107048">JDBC Data Source --> Target and Deploy</a>)</td><td valign="top"></td></tr><tr><td valign="top">Targets</td><td valign="top">myserver</td></tr></tbody></table>

The following table shows a sample connection pool configuration using the IBM Informix JDBC Driver.

Table 11-3 IBM Informix JDBC Driver: Connection Pool Configuration

<table data-header-hidden><thead><tr><th valign="top"></th><th valign="top"></th></tr></thead><tbody><tr><td valign="top"><strong>Attribute Name</strong></td><td valign="top"><strong>Attribute Value</strong></td></tr><tr><td valign="top">General Tab (<a href="https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcconnectionpool_config_general.html#1104829">JDBC Connection Pool --> Configuration --> General</a>)</td><td valign="top"></td></tr><tr><td valign="top">Name</td><td valign="top">myConnectionPool</td></tr><tr><td valign="top">URL</td><td valign="top">jdbc:informix-sqli:ifxserver:1543</td></tr><tr><td valign="top">Driver Classname</td><td valign="top">com.informix.jdbc.IfxDriver</td></tr><tr><td valign="top">Properties</td><td valign="top">informixserver=ifxserver;user=informix</td></tr><tr><td valign="top">Password</td><td valign="top">informix (Displayed as ******)</td></tr><tr><td valign="top">Connections Tab (<a href="https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcconnectionpool_config_connections.html#1104829">JDBC Connection Pool --> Configuration --> Connections</a>)</td><td valign="top"></td></tr><tr><td valign="top">Initial Capacity</td><td valign="top">1</td></tr><tr><td valign="top">Max Capacity</td><td valign="top">15</td></tr><tr><td valign="top">Capacity Increment</td><td valign="top">1</td></tr><tr><td valign="top">Login Delay Seconds</td><td valign="top">1</td></tr><tr><td valign="top">Shrink Period</td><td valign="top">15</td></tr><tr><td valign="top">Target and Deploy (<a href="https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcconnectionpool_targetdeploy.html#1106545">JDBC Connection Pool --> Target and Deploy</a>)</td><td valign="top"></td></tr><tr><td valign="top">Targets</td><td valign="top">myserver</td></tr></tbody></table>

Configuring XA JDBC Drivers for Distributed Transactions

To allow XA JDBC drivers to participate in distributed transactions, configure the JDBC connection pool as follows:

* Specify the Driver Classname attribute as the name of the class supporting the javax.sql.XADataSource interface.
* Make sure that the database properties are specified. These properties are passed to the specified XADataSource as data source properties. For more information on data source properties for the WebLogic jDriver for Oracle, see [WebLogic jDriver for Oracle/XA Data Source Properties.](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/jdbc_connection_pools.html#1116510) For information about data source properties for third-party drivers, see the vendor documentation.

The following table shows an example of a JDBC connection pool configuration using the WebLogic jDriver for Oracle in XA mode.

Table 11-4 WebLogic jDriver for Oracle/XA: Connection Pool Configuration

<table data-header-hidden><thead><tr><th valign="top"></th><th valign="top"></th></tr></thead><tbody><tr><td valign="top"><strong>Attribute Name</strong></td><td valign="top"><strong>Attribute Value</strong></td></tr><tr><td valign="top">General Tab (<a href="https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcconnectionpool_config_general.html#1104829">JDBC Connection Pool --> Configuration --> General</a>)</td><td valign="top"></td></tr><tr><td valign="top">Name</td><td valign="top">fundsXferAppPool</td></tr><tr><td valign="top">URL</td><td valign="top"><em>(none required)</em></td></tr><tr><td valign="top">Driver Classname</td><td valign="top">weblogic.jdbc.oci.xa.XADataSource</td></tr><tr><td valign="top">Properties</td><td valign="top">user=scott;server=localdb</td></tr><tr><td valign="top">Password</td><td valign="top">tiger (This value overrides any password defined in Properties as a name value pair)</td></tr><tr><td valign="top">Connections Tab (<a href="https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcconnectionpool_config_connections.html#1104829">JDBC Connection Pool --> Configuration --> Connections</a>)</td><td valign="top"></td></tr><tr><td valign="top">Initial Capacity</td><td valign="top">1</td></tr><tr><td valign="top">Max Capacity</td><td valign="top">15</td></tr><tr><td valign="top">Capacity Increment</td><td valign="top">1</td></tr><tr><td valign="top">Shrink Period</td><td valign="top">15</td></tr><tr><td valign="top">Test Table Name</td><td valign="top">dual</td></tr><tr><td valign="top">Target and Deploy (<a href="https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcconnectionpool_targetdeploy.html#1106545">JDBC Connection Pool --> Target and Deploy</a>)</td><td valign="top"></td></tr><tr><td valign="top">Targets</td><td valign="top">myserver</td></tr></tbody></table>

The following table shows an example of a Tx Data Source configuration using the WebLogic jDriver for Oracle in XA mode.

Table 11-5 WebLogic jDriver for Oracle/XA: Tx Data Source

<table data-header-hidden><thead><tr><th valign="top"></th><th valign="top"></th></tr></thead><tbody><tr><td valign="top"><strong>Attribute Name</strong></td><td valign="top"><strong>Attribute Value</strong></td></tr><tr><td valign="top">Configuration Tab (<a href="https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcdatasource_config.html#1104829">JDBC Data Source --> Configuration</a>)</td><td valign="top"></td></tr><tr><td valign="top">Name</td><td valign="top">fundsXferDataSource</td></tr><tr><td valign="top">JNDI Name</td><td valign="top">myapp.fundsXfer</td></tr><tr><td valign="top">Pool Name</td><td valign="top">fundsXferAppPool</td></tr><tr><td valign="top">Target and Deploy Tab (<a href="https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcdatasource_targetdeploy.html#1107048">JDBC Data Source --> Target and Deploy</a>)</td><td valign="top"></td></tr><tr><td valign="top">Targets</td><td valign="top">myserver</td></tr></tbody></table>

You can also configure the JDBC connection pool to use a third-party vendor's driver in XA mode. In such cases, the data source properties are set via reflection on the XADataSource instance using the JavaBeans design pattern. In other words, for property abc, the XADataSource instance must support get and set methods with the names getAbc and setAbc, respectively.

The following attributes are an example of a JDBC connection pool configuration using the Oracle Thin Driver.

Table 11-6 Oracle Thin Driver: Connection Pool Configuration

<table data-header-hidden><thead><tr><th valign="top"></th><th valign="top"></th></tr></thead><tbody><tr><td valign="top"><strong>Attribute Name</strong></td><td valign="top"><strong>Attribute Value</strong></td></tr><tr><td valign="top">General Tab (<a href="https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcconnectionpool_config_general.html#1104829">JDBC Connection Pool --> Configuration --> General</a>)</td><td valign="top"></td></tr><tr><td valign="top">Name</td><td valign="top">jtaXAPool</td></tr><tr><td valign="top">URL</td><td valign="top">jdbc:oracle:thin:@server:port:sid</td></tr><tr><td valign="top">Driver Classname</td><td valign="top">oracle.jdbc.xa.client.OracleXADataSource</td></tr><tr><td valign="top">Properties</td><td valign="top">user=scott</td></tr><tr><td valign="top">Password</td><td valign="top">tiger (This value overrides any password defined in Properties as a name value pair)</td></tr><tr><td valign="top">Connections Tab (<a href="https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcconnectionpool_config_connections.html#1104829">JDBC Connection Pool --> Configuration --> Connections</a>)</td><td valign="top"></td></tr><tr><td valign="top">Initial Capacity</td><td valign="top">1</td></tr><tr><td valign="top">Max Capacity</td><td valign="top">15</td></tr><tr><td valign="top">Capacity Increment</td><td valign="top">1</td></tr><tr><td valign="top">Shrink Period</td><td valign="top">15</td></tr><tr><td valign="top">Test Table Name</td><td valign="top">dual</td></tr><tr><td valign="top">Target and Deploy (<a href="https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcconnectionpool_targetdeploy.html#1106545">JDBC Connection Pool --> Target and Deploy</a>)</td><td valign="top"></td></tr><tr><td valign="top">Targets</td><td valign="top">myserver</td></tr></tbody></table>

The following table shows an example of a Tx Data Source configuration using the Oracle Thin Driver.

Table 11-7 Oracle Thin Driver: Tx Data Source Configuration

<table data-header-hidden><thead><tr><th valign="top"></th><th valign="top"></th></tr></thead><tbody><tr><td valign="top"><strong>Attribute Name</strong></td><td valign="top"><strong>Attribute Value</strong></td></tr><tr><td valign="top">Configuration Tab (<a href="https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcdatasource_config.html#1104829">JDBC Data Source --> Configuration</a>)</td><td valign="top"></td></tr><tr><td valign="top">Name</td><td valign="top">jtaXADS</td></tr><tr><td valign="top">JNDI Name</td><td valign="top">jtaXADS</td></tr><tr><td valign="top">Pool Name</td><td valign="top">jtaXAPool</td></tr><tr><td valign="top">Target and Deploy Tab (<a href="https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcdatasource_targetdeploy.html#1107048">JDBC Data Source --> Target and Deploy</a>)</td><td valign="top"></td></tr><tr><td valign="top">Targets</td><td valign="top">myserver</td></tr></tbody></table>

The following table shows an example of a JDBC connection pool configuration for distributed transactions using the PointBase JDBC driver.

Table 11-8 PointBase: Connection Pool Configuration

<table data-header-hidden><thead><tr><th valign="top"></th><th valign="top"></th></tr></thead><tbody><tr><td valign="top"><strong>Attribute Name</strong></td><td valign="top"><strong>Attribute Value</strong></td></tr><tr><td valign="top">General Tab (<a href="https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcconnectionpool_config_general.html#1104829">JDBC Connection Pool --> Configuration --> General</a>)</td><td valign="top"></td></tr><tr><td valign="top">Name</td><td valign="top">demoXAPool</td></tr><tr><td valign="top">URL</td><td valign="top">jdbc:pointbase:server://localhost/demo</td></tr><tr><td valign="top">Driver Classname</td><td valign="top">com.pointbase.xa.xaDataSource</td></tr><tr><td valign="top">Properties</td><td valign="top"><p>user=public</p><p>DatabaseName=jdbc:pointbase:server://localhost/demo</p><p><br></p></td></tr><tr><td valign="top">Password</td><td valign="top">public (Displayed as ******)</td></tr><tr><td valign="top">Connections Tab (<a href="https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcconnectionpool_config_connections.html#1104829">JDBC Connection Pool --> Configuration --> Connections</a>)</td><td valign="top"></td></tr><tr><td valign="top">Initial Capacity</td><td valign="top">1</td></tr><tr><td valign="top">Max Capacity</td><td valign="top">15</td></tr><tr><td valign="top">Capacity Increment</td><td valign="top">1</td></tr><tr><td valign="top">Supports Local Transaction</td><td valign="top">true</td></tr><tr><td valign="top">Shrink Period</td><td valign="top">15</td></tr><tr><td valign="top">Test Table Name</td><td valign="top">users</td></tr><tr><td valign="top">Target and Deploy (<a href="https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcconnectionpool_targetdeploy.html#1106545">JDBC Connection Pool --> Target and Deploy</a>)</td><td valign="top"></td></tr><tr><td valign="top">Targets</td><td valign="top">myserver</td></tr></tbody></table>

Configure the Tx Data Source for use with a PointBase driver as follows.

Table 11-9 PointBase: Tx Data Source Configuration

<table data-header-hidden><thead><tr><th valign="top"></th><th valign="top"></th></tr></thead><tbody><tr><td valign="top"><strong>Attribute Name</strong></td><td valign="top"><strong>Attribute Value</strong></td></tr><tr><td valign="top">Configuration Tab (<a href="https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcdatasource_config.html#1104829">JDBC Data Source --> Configuration</a>)</td><td valign="top"></td></tr><tr><td valign="top">Name</td><td valign="top">jtaXADS</td></tr><tr><td valign="top">JNDI Name</td><td valign="top">JTAXADS</td></tr><tr><td valign="top">Pool Name</td><td valign="top">demoXAPool</td></tr><tr><td valign="top">Target and Deploy Tab (<a href="https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcdatasource_targetdeploy.html#1107048">JDBC Data Source --> Target and Deploy</a>)</td><td valign="top"></td></tr><tr><td valign="top">Targets</td><td valign="top">myserver</td></tr></tbody></table>

WebLogic jDriver for Oracle/XA Data Source Properties

[Table 11-10](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/jdbc_connection_pools.html#1107323) lists the data source properties supported by the WebLogic jDriver for Oracle. The JDBC 2.0 column indicates whether a specific data source property is a JDBC 2.0 standard data source property (S) or a WebLogic Server extension to JDBC (E).

The Optional column indicates whether a particular data source property is optional or not. Properties marked with Y\* are mapped to the corresponding fields of the Oracle xa\_open string (value of the openString property) as listed in [Table 11-10](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/jdbc_connection_pools.html#1107323). If they are not specified, their default values are taken from the openString property. If they are specified, their values should match those specified in the openString property. If the properties do not match, a SQLException is thrown when you attempt to make an XA connection.

Mandatory properties marked with N\* are also mapped to the corresponding fields of the Oracle xa\_open string. Specify these properties when specifying the Oracle xa\_open string. If they are not specified or if they are specified but do not match, an SQLException is thrown when you attempt to make an XA connection.

Property Names marked with \*\* are supported but not used by WebLogic Server.

Table 11-10 Data Source Properties for WebLogic jDriver for Oracle/XA

<table data-header-hidden><thead><tr><th valign="top"></th><th valign="top"></th><th valign="top"></th><th valign="top"></th><th valign="top"></th><th valign="top"></th></tr></thead><tbody><tr><td valign="top"><strong>Property Name</strong></td><td valign="top"><strong>Type</strong></td><td valign="top"><strong>Description</strong></td><td valign="top"><strong>JDBC 2.0</strong><br><strong>standard/extension</strong></td><td valign="top"><strong>Optional</strong></td><td valign="top"><strong>Default Value</strong></td></tr><tr><td valign="top">databaseName**</td><td valign="top">String</td><td valign="top">Name of a particular database on a server.</td><td valign="top">S</td><td valign="top">Y</td><td valign="top">None</td></tr><tr><td valign="top">dataSourceName</td><td valign="top">String</td><td valign="top">A data source name; used to name an underlying XADataSource.</td><td valign="top">S</td><td valign="top">Y</td><td valign="top">Connection Pool Name</td></tr><tr><td valign="top">description</td><td valign="top">String</td><td valign="top">Description of this data source.</td><td valign="top">S</td><td valign="top">Y</td><td valign="top">None</td></tr><tr><td valign="top">networkProtocol**</td><td valign="top">String</td><td valign="top">Network protocol used to communicate with the server.</td><td valign="top">S</td><td valign="top">Y</td><td valign="top">None</td></tr><tr><td valign="top">password</td><td valign="top">String</td><td valign="top">A database password.</td><td valign="top">S</td><td valign="top">N*</td><td valign="top">None</td></tr><tr><td valign="top">portNumber**</td><td valign="top">Int</td><td valign="top">Port number at which a server is listening for requests.</td><td valign="top">S</td><td valign="top">Y</td><td valign="top">None</td></tr><tr><td valign="top">roleName**</td><td valign="top">String</td><td valign="top">The initial SQL role name.</td><td valign="top">S</td><td valign="top">Y</td><td valign="top">None</td></tr><tr><td valign="top">serverName</td><td valign="top">String</td><td valign="top">Database server name.</td><td valign="top">S</td><td valign="top">Y*</td><td valign="top">None</td></tr><tr><td valign="top">user</td><td valign="top">String</td><td valign="top">User's account name.</td><td valign="top">S</td><td valign="top">N*</td><td valign="top">None</td></tr><tr><td valign="top">openString</td><td valign="top">String</td><td valign="top">Oracle's XA open string.</td><td valign="top">E</td><td valign="top">Y</td><td valign="top">None</td></tr><tr><td valign="top">oracleXATrace</td><td valign="top">String</td><td valign="top">Indicates whether XA tracing output is enabled. If enabled (true), a file with a name in the form of xa_poolnamedate.trc is placed in the directory in which the server is started.</td><td valign="top">E</td><td valign="top">Y</td><td valign="top">true</td></tr></tbody></table>

[Table 11-11](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/jdbc_connection_pools.html#1107486) lists the mapping between Oracle's xa\_open string fields and data source properties.

Table 11-11 Mapping of xa\_open String Names to JDBC Data Source Properties

<table data-header-hidden><thead><tr><th valign="top"></th><th valign="top"></th><th valign="top"></th></tr></thead><tbody><tr><td valign="top"><strong>Oracle xa_open String Field Name</strong></td><td valign="top"><strong>JDBC 2.0 Data Source Property</strong></td><td valign="top"><strong>Optional</strong></td></tr><tr><td valign="top">acc</td><td valign="top">user, password</td><td valign="top">N</td></tr><tr><td valign="top">sqlnet</td><td valign="top">ServerName</td><td valign="top"><br></td></tr></tbody></table>

**Note:** You must specify Threads=true in Oracle's xa\_open string.

For a complete description of Oracle's xa\_open string fields, see your Oracle documentation.

Additional XA Connection Pool Properties

When using connections from a connection pool in distributed transactions, you may need to set additional properties for the connection pool so that the connection pool handles the connection properly within WebLogic Server in the context of the transaction. You set these properties in the configuration file (config.xml) within the JDBCConnectionPool tag. By default, all additional properties are set to false. You set the properties to true to enable them.

In many cases, WebLogic Server automatically sets the proper value for these properties internally so that you do not have to set them manually.

KeepXAConnTillTxComplete

Some DBMSs require that you start and end a transaction in the same physical database connection. In some cases, a transaction in WebLogic Server may start in one physical database connection and end in another physical database connection. To force a connection pool to reserve a physical connection and provide the _same_ connection to an application throughout transaction processing until the transaction is complete, you set KeepXAConnTillTxComplete="true". For example:

> <pre><code><strong>&#x3C;JDBCConnectionPool KeepXAConnTillTxComplete="true" DriverName="com.sybase.jdbc2.jdbc.SybXADataSource" CapacityIncrement="5" InitialCapacity="10" MaxCapacity="25" Name="demoXAPool" Password="{3DES}vIF8diu4H0QmdfOipd4dWA==" Properties="User=dbuser;DatabaseName=dbname;ServerName=server_name_or_IP_address;PortNumber=serverPortNumber;NetworkProtocol=Tds;resourceManagerName=Lrm_name_in_xa_config;resourceManagerType=2" />
> </strong></code></pre>

**Note:** This property is _required_ to support distributed transactions with DB2 and Sybase.

Configuring Non-XA JDBC Drivers for Distributed Transactions

When configuring the JDBC connection pool to allow non-XA JDBC drivers to participate with other resources in distributed transactions, select the Emulate Two-Phase Commit for non-XA Driver attribute (EnableTwoPhaseCommit in the JDBCTxDataSource MBean) for the JDBC Tx Data Source. This parameter is ignored by resources that support the XAResource interface. Note that only one non-XA connection pool may participate in a distributed transaction. See [Emulating Two-Phase Commit](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/jdbc_datasources.html#1107722) for more information.

**Note:** There are risks to data integrity when using the Emulate Two-Phase Commit for non-XA Driver option. BEA recommends that you use an XA-compliant JDBC driver rather than use this option. Make sure you consider the risks below before enabling this option. See [Limitations and Risks](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/jdbc_datasources.html#1107726).

Non-XA Driver/Single Resource

If you are using only one non-XA driver and it is the only resource in the transaction, leave the Emulate Two-Phase Commit for non-XA Driver option unselected in the Console (accept the default EnableTwoPhaseCommit = false). In this case, the Transaction Manager performs a one-phase optimization.

Non-XA Driver/Multiple Resources

If you are using one non-XA JDBC driver with other XA resources, select Emulate Two-Phase Commit in the Administration Console (EnableTwoPhaseCommit = true).

When the Emulate Two-Phase Commit for non-XA Driver option is selected (EnableTwoPhaseCommit is set to true), the non-XA JDBC resource always returns XA\_OK during the XAResource.prepare() method call. The resource attempts to commit or roll back its local transaction in response to subsequent XAResource.commit() or XAResource.rollback() calls. If the resource commit or rollback fails, a heuristic error results. Application data may be left in an inconsistent state as a result of a heuristic failure.

When the Emulate Two-Phase Commit for non-XA Driver option is not selected in the Console (EnableTwoPhaseCommit is set to false), the non-XA JDBC resource causes XAResource.prepare() to fail. This mechanism ensures that there is only one participant in the transaction, as commit() throws a SystemException in this case. When there is only one resource participating in a transaction, the one phase optimization bypasses XAResource.prepare(), and the transaction commits successfully in most instances.

The following table shows configuration attributes for a sample JDBC connection pool using a non-XA JDBC driver.

Table 11-12 WebLogic jDriver for Oracle: Connection Pool Configuration

<table data-header-hidden><thead><tr><th valign="top"></th><th valign="top"></th></tr></thead><tbody><tr><td valign="top"><strong>Attribute Name</strong></td><td valign="top"><strong>Attribute Value</strong></td></tr><tr><td valign="top">General Tab (<a href="https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcconnectionpool_config_general.html#1104829">JDBC Connection Pool --> Configuration --> General</a>)</td><td valign="top"></td></tr><tr><td valign="top">Name</td><td valign="top">fundsXferAppPool</td></tr><tr><td valign="top">URL</td><td valign="top">jdbc:weblogic:oracle</td></tr><tr><td valign="top">Driver Classname</td><td valign="top">weblogic.jdbc.oci.Driver</td></tr><tr><td valign="top">Properties</td><td valign="top">user=scott;server=localdb</td></tr><tr><td valign="top">Password</td><td valign="top">tiger (Displayed as ***** when typed, hidden thereafter; this value overrides any password defined in Properties as a name value pair)</td></tr><tr><td valign="top">Connections Tab (<a href="https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcconnectionpool_config_connections.html#1104829">JDBC Connection Pool --> Configuration --> Connections</a>)</td><td valign="top"></td></tr><tr><td valign="top">Initial Capacity</td><td valign="top">0</td></tr><tr><td valign="top">Max Capacity</td><td valign="top">5</td></tr><tr><td valign="top">Capacity Increment</td><td valign="top">1</td></tr><tr><td valign="top">Shrink Period</td><td valign="top">15</td></tr><tr><td valign="top">Test Table Name</td><td valign="top">dual</td></tr><tr><td valign="top">Target and Deploy (<a href="https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcconnectionpool_targetdeploy.html#1106545">JDBC Connection Pool --> Target and Deploy</a>)</td><td valign="top"></td></tr><tr><td valign="top">Targets</td><td valign="top">myserver</td></tr></tbody></table>

The following table shows configuration attributes for a sample Tx Data Source using a non-XA JDBC driver.

Table 11-13 WebLogic j Driver for Oracle: Tx Data Source Configuration

<table data-header-hidden><thead><tr><th valign="top"></th><th valign="top"></th></tr></thead><tbody><tr><td valign="top"><strong>Attribute Name</strong></td><td valign="top"><strong>Attribute Value</strong></td></tr><tr><td valign="top">Configuration Tab (<a href="https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcdatasource_config.html#1104829">JDBC Data Source --> Configuration</a>)</td><td valign="top"></td></tr><tr><td valign="top">Name</td><td valign="top">fundsXferDataSource</td></tr><tr><td valign="top">JNDI Name</td><td valign="top">myapp.fundsXfer</td></tr><tr><td valign="top">Pool Name</td><td valign="top">fundsXferAppPool</td></tr><tr><td valign="top">Emulate Two-Phase Commit for non-XA Driver</td><td valign="top">selected (EnableTwoPhaseCommit = true)</td></tr><tr><td valign="top">Target and Deploy Tab (<a href="https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcdatasource_targetdeploy.html#1107048">JDBC Data Source --> Target and Deploy</a>)</td><td valign="top"></td></tr><tr><td valign="top">Targets</td><td valign="top">myserver</td></tr></tbody></table>

&#x20;

***

Security for JDBC Connection Pools

You can optionally restrict access to JDBC connection pools. In WebLogic Server, security policies answer the question "who has access" to a WebLogic resource. A security policy is created when you define an association between a WebLogic resource and a user, group, or role. A WebLogic resource has no protection until you assign it a security policy. For instructions on how to set up security for all WebLogic Server resources, see [Protecting WebLogic Resources](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/security_7x.html#1170617).

&#x20;

***

Managing JDBC Connection Pools

From the JDBC Connection Pool property tabs in the Administration Console, you can manage the connections pools in your domain. The following sections provide detailed instructions for manually performing management tasks on JDBC connection pools.

Resetting All Connections in a JDBC Connection Pool

When you reset a connection pool, WebLogic Server shuts down and recreates all database connections in the connection pool.

1. In the left pane, click to expand the Services, JDBC, and Connection Pools nodes to display the list of connection pools in the current domain.
2. Click the connection pool that you want to reset. A dialog displays in the right pane showing the tabs associated with this connection pool.
3. Click the Control tab. The control tab lists each server on which the connection pool is deployed.
4. Click Reset for each server on which you want to reset all connections in the connection pool.

Shrinking a JDBC Connection Pool

If you configure a connection pool so that it can add database connections as demand for connections increases, you can click the Shrink button on the Control tab to manually shrink the connection pool. When you shrink a connection pool, WebLogic Server reduces the number of connections in the pool to the greater of either the initial capacity or the number of connections currently in use.

1. In the left pane, click to expand the Services, JDBC, and Connection Pools nodes to display the list of connection pools in the current domain.
2. Click the connection pool that you want to reset. A dialog displays in the right pane showing the tabs associated with the connection pool.
3. Click the Control tab. The control tab lists each server on which the connection pool is deployed.
4. Click Shrink for each server on which you want to shrink the connection pool instance.

Suspending a JDBC Connection Pool

When you suspend a connection pool, you make the connections in the pool unavailable for applications to use. WebLogic Server provides the following options for suspending a connection pool:

* Suspend—which marks the pool as disabled and blocks any new requests for a connection from the connection pool. If connections are currently in use, the suspend operation will fail and will put the connection pool into an unknown state. To correct that state, you must shut down the pool by undeploying it. See [Shutting Down a JDBC Connection Pool](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/jdbc_connection_pools.html#1115169).
* Force Suspend—which marks the pool as disabled and prevents applications from using connections from the connection pool, including those connections currently in use.

Connections is a suspended connection pool remain intact. The connections are not recreated when you resume the connection pool.

To suspend a connection pool, follow these steps:

1. In the left pane, click to expand the Services, JDBC, and Connection Pool nodes to display the list of connection pools in the current domain.
2. Click the connection pool that you want to suspend. A dialog displays in the right pane showing the tabs associated with the connection pool.
3. Click the Control tab. The control tab lists each server on which the connection pool is deployed.
4. For each server listed, choose one of the following options:
   * Click Suspend to block new requests to reserve a connection from the connection pool and mark the connection pool as disabled. If connections are currently in use, this operation will fail.
   * Click Force Suspend to block new requests to reserve a connection from the connection pool and to stop all current use of connections from the connection pool. This operation also marks the connection pool as disabled.

Resuming a JDBC Connection Pool

After manually suspending a connection pool, you can re-enable it by clicking Resume on the JDBC Connection Pool—>Control tab. You cannot use the Resume functionality to restart a connection pool that failed to start properly.

Follow these instructions.

1. In the left pane, click to expand the Services, JDBC, and Connection Pool nodes to display the list of connection pools in the current domain.
2. Click the connection pool that you want to resume. A dialog displays in the right pane showing the tabs associated with the connection pool.
3. Click the Control tab. The control tab lists each server on which the connection pool is deployed.
4. Click the Resume button for the instance of the connection pool that you want to re-enable. This option is only available for connection pools that were successfully suspended.

Shutting Down a JDBC Connection Pool

To shut down an instance of a connection pool, you can un-deploy the connection pool on the server. This operation closes all physical database connections in the connection pool. To shut down the connection pool on more than on target, you must un-deploy on each deployment target.

Follow these steps:

1. In the left pane, click to expand the Services, JDBC, and Connection Pools nodes to display the list of connection pools in the current domain.
2. Click the connection pool that you want to shut down. A dialog displays in the right pane showing the tabs associated with this instance.
3. Click the Target and Deploy tab.
4. Clear the check box for the servers or clusters on which you want to shut down the connection pool. Click Apply to save your changes.

See the following related information:

* [Resetting All Connections in a JDBC Connection Pool](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/jdbc_connection_pools.html#1115139)
* [Suspending a JDBC Connection Pool](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/jdbc_connection_pools.html#1115153)

Restarting a JDBC Connection Pool

To restart a connection pool after shutting it down by undeploying it (see [Shutting Down a JDBC Connection Pool](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/jdbc_connection_pools.html#1115169)), you re-deploy the connection pool to servers and clusters. See [Deploying a JDBC Connection Pool to One or More Servers or Clusters](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/jdbc_connection_pools.html#1106179) for instructions.

Destroying or Deleting a JDBC Connection Pool

When you destroy a JDBC connection pool, all database connections _in all instances_ of the connection pool are closed and the connection pool configuration is removed from the domain.

**Note:** When you destroy a connection pool, you destroy all instances of the connection pool, not just the instance for which you clicked the Destroy button.

There are two Destroy options for connection pools in WebLogic Server:

* Destroy—Closes all database connections in all instances of the connection pool and permanently deletes the connection pool configuration from the domain. If connections in the connection pool are in use, the operation will fail.
* Force Destroy—Forcibly closes all database connections in all instances of the connection pool, even if connections are in use, and permanently deletes the connection pool configuration from the domain.

To destroy a connection pool, follow these steps:

1. In the left pane, click to expand the Services, JDBC, and Connection Pools nodes to display the list of connection pools in the current domain.
2. Click the connection pool that you want to destroy. A dialog displays in the right pane showing the tabs associated with the connection pool.
3. Click the Control tab. The control tab lists each server on which the connection pool is deployed.
4. For any server listed, choose one of the following options:
   * Click Destroy to close all database connections and delete the connection pool. This action applies to all servers. If a connection is in use, the operation will fail.
   * Click Force Destroy to forcibly close all database connections and delete the connection pool. This action applies to all servers.

Clearing the Statement Cache for a JDBC Connection Pool

To clear the statement cache for all connections in a connection pool, follow these steps:

1. In the left pane, click to expand the Services, JDBC, and Connection Pools nodes to display the list of connection pools in the current domain.
2. Click the connection pool for which you want to clear the statement cache. A dialog displays in the right pane showing the tabs associated with this connection pool.
3. Click the Control tab. The control tab lists each server on which the connection pool is deployed.
4. Click Clear Statement Cache for each server on which you want to clear the statement cache for all connections in the connection pool. Repeat for each instance of the connection pool as required.

For more information about the statement cache for a connection pool, see [Increasing Performance with the Statement Cache](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/jdbc_connection_pools.html#1107805).

&#x20;

***

Monitoring a JDBC Connection Pool

Monitoring Connections in a JDBC Connection Pool

1. In the left pane, click to the JDBC node to expand it.
2. Click the Connection Pools node to expand it and show the list of connection pools defined in your domain.
3. Click the connection pool for which you want to see database connection information. A dialog displays in the right pane showing tabs with attributes for the connection pool.
4. Click the Monitoring tab and then click the Monitor all Active Pools text link. A table displays with information about connections in the selected JDBC connection pool.

For details about the information displayed, see [JDBC Connection Pool --> Monitoring](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcconnectionpool_monitor.html#1104829).

&#x20;

***

Tuning Connection Pools

By properly configuring connection pools in your WebLogic Server domain, you can improve application and system performance.

Increasing Performance with the Statement Cache

When you use a prepared statement or callable statement in an application or EJB, there is considerable processing overhead for the communication between the application server and the database server and on the database server itself. To minimize the processing costs, WebLogic Server can cache statements used in your applications. When an application or EJB calls any of the statements stored in the cache, WebLogic Server reuses the statement stored in the cache. Reusing statements reduces CPU usage on the database server, improving performance for the current statement and leaving CPU cycles for other tasks.

Each connection in a connection pool has its own individual cache of prepared and callable statements used on the connection. However, you configure statement cache options per connection pool. That is, the statement cache for each connection in a connection pool uses the statement cache options specified for the connection pool. Statement cache configuration options include:

* **Statement Cache Type**—The algorithm that determines which statements to store in the statement cache. See [Statement Cache Algorithms](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/jdbc_connection_pools.html#1115624).
* **Statement Cache Size**—The number of statements to store in the cache for each connection. The default value is 10. See [Statement Cache Size](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/jdbc_connection_pools.html#1116241).

You can use the following methods to set statement cache options for a connection pool:

* Using the Administration Console (preferred). See [Configuring the Statement Cache for a JDBC Connection Pool](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/jdbc_connection_pools.html#1116526).
* Using the WebLogic management API. See the following methods in the [Javadocs for WebLogic Classes](https://docs.oracle.com/cd/E13222_01/wls/docs81b/javadocs/weblogic/management/configuration/JDBCConnectionPoolMBean.html):
* getStatementCacheType()
* setStatementCacheType(string type)
* getPreparedStatementCacheSize()
* setPreparedStatementCacheSize(int cacheSize)
* Directly in the configuration file (typically config.xml).

To set the prepared statement cache size for a connection pool using the configuration file, before starting the server, open the config.xml file in an editor, then add an entry for the PreparedStatementCacheSize attribute in the JDBCConnectionPool tag. For example:

> <pre><code>    &#x3C;JDBCConnectionPool CapacityIncrement="5"
>         DriverName="com.pointbase.jdbc.jdbcUniversalDriver"
>         InitialCapacity="5" MaxCapacity="20" Name="demoPool"
>         Password="{3DES}ANfMduXgaaGMeS8+CR1xoA=="
> <strong>        PreparedStatementCacheSize="10" StatementCacheType="LRU"
> </strong>        Properties="user=examples"
>         RefreshMinutes="0" ShrinkPeriodMinutes="15"
>         ShrinkingEnabled="true" Targets="examplesServer"
>         TestConnectionsOnRelease="false"
>         TestConnectionsOnReserve="false"
>         URL="jdbc:pointbase:server://localhost/demo"/>
> </code></pre>

You can also manually clear the statement cache for a connection pool. See [Clearing the Statement Cache for a JDBC Connection Pool](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/jdbc_connection_pools.html#1115180).

Statement Cache Algorithms

The Statement Cache Type (or algorithm) determines which prepared and callable statements to store in the cache for each connection in a connection pool. You can choose from the following options:

* [LRU (Least Recently Used)](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/jdbc_connection_pools.html#1115749)
* [Fixed](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/jdbc_connection_pools.html#1115761)

LRU (Least Recently Used)

When you select LRU (Least Recently Used, the default) as the Statement Cache Type, WebLogic Server caches prepared and callable statements used on the connection until the statement cache size is reached. When an application calls connection.prepare statement, WebLogic Server checks to see if the statement is stored in the statement cache. If so, WebLogic Server returns the cached statement (if it is not already being used). If the statement is not in the cache, and the cache is full (number of statements in the cache = statement cache size), Weblogic Server determines which existing statement in the cache was the least recently used and replaces that statement in the cache with the new statement.

The LRU statement cache algorithm in WebLogic Server uses an approximate LRU scheme.

Fixed

When you select FIXED as the Statement Cache Type, WebLogic Server caches prepared and callable statements used on the connection until the statement cache size is reached. When additional statements are used, they are not cached.

With this statement cache algorithm, you can inadvertently cache statements that are rarely used. In many cases, the LRU algorithm is preferred because rarely used statements will eventually be replaced in the cache with frequently used statements.

Statement Cache Size

El atributo Tamaño de caché de sentencias determina la cantidad total de sentencias preparadas y ejecutables que se almacenan en caché para cada conexión en cada instancia del grupo de conexiones. Al almacenar sentencias en caché, puede mejorar el rendimiento de su sistema. Sin embargo, debe considerar cómo su sistema de gestión de bases de datos (DBMS) maneja las sentencias preparadas y ejecutables abiertas. En muchos casos, el DBMS mantendrá un cursor para cada sentencia abierta. Esto se aplica a las sentencias preparadas y ejecutables en la caché de sentencias. Si almacena demasiadas sentencias en caché, podría exceder el límite de cursores abiertos en su servidor de base de datos.

Por ejemplo, si tiene un grupo de conexiones con 10 conexiones implementadas en 2 servidores, si establece el tamaño de la caché de sentencias en 10 (el valor predeterminado), puede abrir 200 (10 x 2 x 10) cursores en su servidor de base de datos para las sentencias almacenadas en caché.

Restricciones de uso para la caché de sentencias

El uso de la caché de sentencias puede mejorar drásticamente el rendimiento, pero debe tener en cuenta sus limitaciones antes de decidir utilizarla. Tenga en cuenta las siguientes restricciones al usar la caché de sentencias preparadas.

Es posible que existan otros problemas relacionados con el almacenamiento en caché de sentencias que no se mencionan aquí. Si observa errores en su sistema relacionados con sentencias preparadas o invocables, debería establecer el tamaño de la caché de sentencias preparadas en 0 , lo que desactiva el almacenamiento en caché de sentencias preparadas, para comprobar si el problema se debe al almacenamiento en caché de sentencias preparadas.

Llamar a una instrucción almacenada después de un cambio en la base de datos puede provocar errores.

Las sentencias preparadas almacenadas en la caché hacen referencia a objetos específicos de la base de datos en el momento en que se almacenan en caché. Si realiza operaciones DDL (lenguaje de definición de datos) sobre objetos de la base de datos a los que se hace referencia en las sentencias preparadas almacenadas en la caché, estas podrían fallar la próxima vez que las ejecute. Por ejemplo, si almacena en caché una sentencia como \`select \* from emp\` y luego elimina y vuelve a crear la tabla \`emp\` , la próxima vez que ejecute la sentencia almacenada en caché, esta podría fallar porque la tabla \`emp\` que existía cuando se preparó la sentencia ya no existe.

Asimismo, las sentencias preparadas están vinculadas al tipo de datos de cada columna de una tabla en la base de datos en el momento en que se almacenan en caché. Si se agregan, eliminan o reorganizan columnas en una tabla, es probable que las sentencias preparadas almacenadas en la caché fallen al ejecutarse nuevamente.

Estas limitaciones dependen del comportamiento de su sistema de gestión de bases de datos (DBMS).

Uso de setNull en una instrucción preparada

Al usar el jDriver de WebLogic para Oracle para conectarse a la base de datos, si almacena en caché una sentencia preparada que usa una variable de enlace setNull , debe establecer la variable al tipo de datos correcto. Si usa un tipo de datos genérico, como en el siguiente ejemplo, la sentencia podría fallar al ejecutarse con un valor distinto de null.

> ```
> java.sql.Types.Long sal=null
> ```

> ```
> . 
> . 
> .
> ```

> <pre><code>if (sal == null) 
> <strong>    setNull(2, int )//Esto es incorrecto 
> </strong>else 
>     setLong(2,sal)
> </code></pre>

En su lugar, utilice lo siguiente:

> ```
> if (sal == null) 
>     setNull(2,long)//Esto es correcto 
> else 
>     setLong(2,sal)
> ```

Este problema se presenta de forma constante al usar el controlador jDriver de WebLogic para Oracle. También puede ocurrir al usar otros controladores JDBC.

Las instrucciones en la caché pueden reservar cursores de la base de datos.

Cuando WebLogic Server almacena en caché una sentencia preparada o ejecutable, esta puede abrir un cursor en la base de datos. Si almacena demasiadas sentencias en caché, podría superar el límite de cursores abiertos para una conexión. Para evitar superar este límite, puede modificarlo en su sistema de gestión de bases de datos o reducir el tamaño de la caché de sentencias preparadas para el grupo de conexiones.\
&#x20;

***

Configuring JDBC Connection Pools

A connection pool contains a group of JDBC connections that are created when the connection pool is registered—when starting up WebLogic Server or when deploying the connection pool to a target server or cluster. Connection pools use a JDBC driver to create physical database connections. Your application borrows a connection from the pool, uses it, then returns it to the pool by closing it.

Figure 11-1 Connection Pool Architecture

![](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/wwimages/jdbc_arch_cpool.gif)\
&#x20;

All of the settings you make with the Administration Console are static; that is, all settings persist even after you stop and restart WebLogic Server. You can create dynamic connection pools—those that you expect to use and delete while the server is running—using the command line (see [Commands for Managing JDBC Connection Pools](https://docs.oracle.com/cd/E13222_01/wls/docs81b/admin_ref/cli.html#jdbc) in the _WebLogic Server Command Reference_ at ../admin\_ref/cli.html#jdbc) or programmatically using the API (see [Creating a Connection Pool Dynamically](https://docs.oracle.com/cd/E13222_01/wls/docs81b/jdbc/programming.html#dynamic_conn_pool) in Programming WebLogic JDBC).

Connection pool settings are persisted in the config.xml file, including settings for dynamically created connection pools (until you programmatically delete the connection pool). For information about entries in the config.xml file, see the [JDBCConnectionPool](https://docs.oracle.com/cd/E13222_01/wls/docs81b/config_xml/JDBCConnectionPool.html) section of the _Configuration Reference Guide_.

Related Information

* [Creating and Configuring a JDBC Connection Pool](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/jdbc_connection_pools.html#1106131)
* [JDBC DataSources](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/jdbc_datasources.html#1105912)
* Read more about [Connection Pools](https://docs.oracle.com/cd/E13222_01/wls/docs81b/jdbc/programming.html#programming001) in _Programming WebLogic JDBC_.

&#x20;

***

Using the JDBC Connection Pool Assistant

You use the JDBC Connection Pool Assistant to create JDBC connection pools. The JDBC Connection Pool Assistant helps you create and deploy a connection pool by prompting you for database and driver information and then constructing the connection attributes required by your JDBC driver, such as the driver class name and the database URL.

**Notes:** JDBC drivers listed in the JDBC Connection Pool Assistant are not necessarily certified for use with WebLogic Server. In keeping with the goal of the JDBC Connection Pool Assistant, JDBC drivers are listed as a convenience to help you create a connection to many of the database management systems available.

You must install JDBC drivers in order to use them to create database connections in a connection pool. Drivers are listed in the JDBC Connection Pool Assistant with known required configuration options to help you configure a connection pool. The JDBC drivers in the list are not necessarily installed. Driver installation can include setting system Path, Classpath, and other environment variables.

When a JDBC driver is updated, configuration requirements may change. The JDBC Connection Pool Assistant uses known configuration requirements at the time the WebLogic Server software was released. If configuration options for your JDBC driver have changed, you may need to manually override the configuration options displayed in Step 3 of the JDBC Connection Pool Assistant or in the property pages for the connection pool.

Creating and Configuring a JDBC Connection Pool

1. Click to expand the Services and JDBC nodes.
2. Right-click the Connection Pools node and select Configure a New JDBC Connection Pool. The JDBC Connection Pool Assistant opens in the right pane.
3.  In Step 1 - Choose database, follow these steps:

    1. Database type, select the DBMS of the database that you want to connect to. If your DBMS is not listed, select Other.
    2. In Database driver, select the JDBC driver you want to use to connect to the database. The list includes common JDBC drivers for the selected DBMS. Click Continue.

    **Note:** You must install JDBC drivers in order to use them to create database connections in a connection pool. Drivers are listed in the JDBC Assistant with known required configuration options to help you configure a connection pool. Driver installation also includes setting system Path, Classpath, and other environment variables.
4. In Step 2 - Define connection properties, follow these steps:
   1. In Name, enter a name for the new connection pool. The name should be unique within the domain.
   2. Under Connection Properties, provide the information requested. The required attributes vary by the DBMS and JDBC driver you selected in the previous step. Many attributes include a common default value. Verify these values for your environment.
   3. Click Continue.
5.  In Step 3 - Test database connection, verify the connection properties and then click Test Connection. WebLogic Server attempts to ping your database using the connection properties you provided. The JDBC driver must be installed and configured on the server (on the Administration server in multi-server environments) for the test to succeed.

    If the test is successful, Step 4 - Create and deploy is displayed. If the test is unsuccessful, an error message is displayed at the top of the page. Check the values on the page and correct any errors, then test the connection again.

    You can click Skip this Step to skip the test and continue configuring the connection pool. Note that if you create and deploy a connection pool with errors, the connection pool configuration will be created, but the connection pool will not actually be deployed to servers or clusters. Also, when you restart servers, the servers will start with errors.
6. In Step 4 - Create and deploy, select the servers and clusters on which you want to deploy the connection pool. If you only have one server in your domain, the connection pool is automatically deployed to the server. Click Create and Deploy to complete the process.

In most cases, you should create a data source to use with a connection pool. To create a data source, see [Creating and Configuring a JDBC Data Source](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/jdbc_datasources.html#1107735).

Database Passwords in Connection Pool Configuration

When you create a connection pool, you typically include at least one password to connect to the database. If you use an open string to enable XA, you may use two passwords. You can enter the passwords as a name-value pair in the Properties field or you can enter them in their respective fields:

* **Password**. Use this field to set the database password. This value overrides any password value defined in the Properties passed to the tier-2 JDBC Driver when creating physical database connections. The value is encrypted in the config.xml file (stored as the Password attribute in the JDBCConnectionPool tag) and is hidden on the administration console.
* **Open String Password**. Use this field to set the password in the open string that the transaction manager in WebLogic Server uses to open a database connection. This value overrides any password defined as part of the open string in the Properties field. The value is encrypted in the config.xml file (stored as the XAPassword attribute in the JDBCConnectionPool tag) and is hidden on the Administration Console. At runtime, WebLogic Server reconstructs the open string with the password you specify in this field. The open string in the Properties field should follow this format:
* > ```
  > openString=Oracle_XA+Acc=P/userName/+SesTm=177+DB=demoPool+Threads=true=Sqlnet=dvi0+logDir=.
  > ```
* Note that after the userName there is no password.

If you specify a password in the Properties field when you first configure the connection pool, WebLogic Server removes the password from the Properties string and sets the value as the Password value in an encrypted form the next time you start WebLogic Server. If there is already a value for the Password attribute for the connection pool, WebLogic Server does not change any values. However, the value for the Password attribute overrides the password value in the Properties string. The same behavior applies to any password that you define as part of an open string. For example, if you include the following properties when you first configure a connection pool:

> ```
> user=scott;
> password=tiger;
> openString=Oracle_XA+Acc=p/scott/tiger+SesTm=177+db=jtaXaPool+Threads=true+Sqlnet=lcs817+logDir=.+dbgFl=0x15;server=lcs817
> ```

The next time you start WebLogic Server, it moves the database password and the password included in the open string to the Password and Open String Password attributes, respectively, and the following value remains for the Properties field:

> ```
> user=scott;
> openString=Oracle_XA+Acc=p/scott/+SesTm=177+db=jtaXaPool+Threads=true+Sqlnet=lcs817+logDir=.+dbgFl=0x15;server=lcs817
> ```

After a value is established for the Password or Open String Password attributes, the values in these attributes override the respective values in the Properties attribute. That is, continuing with the previous example, if you specify tiger2 as the database password in the Properties attribute, WebLogic Server ignores the value and continues to use tiger as the database password, which is the current encrypted value of the Password attribute. To change the database password, you must change the Password attribute.

**Note:** The value for Password and Open String Password do not need to be the same.

Cloning a JDBC Connection Pool

1. Click to expand the Services, JDBC, and Connection Pool nodes.
2. Right-click the connection pool you want to clone and select Clone _poolname_. A dialog displays in the right pane showing the tabs associated with cloning a connection pool. All attribute values except Name are the same as those in cloned pool, including Connection attributes and deployment targets.
3. Enter a new Name. Optionally, you can modify the URL, Driver Classname, and Properties attribute fields. For more information about connection pool general attributes, see [Attributes](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcconnectionpool_config_general.html#1104722).
4. Click Clone to create a connection pool with the attributes you specified on the General tab and with cloned values on all other tabs. The new connection pool is added under the Connection Pools node in the left pane.
5. Optionally, click the remaining tabs for the connection pool and change the attribute fields. Click Apply to save any changes you make.

Deploying a JDBC Connection Pool to One or More Servers or Clusters

1. In the left pane, click to expand the Services, JDBC, and Connection Pools nodes to display the list of connection pools in the current domain.
2. Click the connection pool that you want to deploy. A dialog displays in the right pane showing the tabs associated with this instance.
3. Click the Target and Deploy tab and select the servers or clusters on which you want to deploy the connection pool. Click Apply to save your changes.

When deploying a JDBC connection pool on a cluster, in most cases you should deploy the connection pool to the entire cluster. You should deploy the related data source to the same targets.

Testing a JDBC Connection Pool

On the JDBC Connection Pool—>Testing tab, you can test a JDBC connection in a connection pool on each server on which the connection pool is deployed.

When you test a connection pool, WebLogic Server reserves and releases a connection from the connection pool.

To make the test more meaningful, make sure that Test Reserved Connections or Test Released Connections is selected on the Configuration—>Connections tab (under Advanced Options). If either of these options is selected, WebLogic Server not only reserves and releases a connection, but also tests the physical database connection. See Test Reserved Connections in [Attributes](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcconnectionpool_config_connections.html#1104722).

To see a description of the information displayed on the JDBC connection Pool—>Testing tab, see [Attributes](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcconnectionpool_testing.html#1105775).

To test a connection in a connection pool, follow these steps:

1. In the left pane, click to expand the Services, JDBC, and Connection Pool nodes to display the list of connection pools in the current domain.
2. Click the connection pool that you want to deploy. A dialog displays in the right pane showing the tabs associated with this instance.
3. Click the Testing tab. The Testing tab displays a list of instances of the selected connection pool. Each server on which the connection pool is deployed is listed. Each server can have only one instance of a connection pool.
4. Click the Test Pool button for each instance of the connection pool. Test results are displayed at the top of the pane.
5. Optionally, click the Test pool on all servers button to test all instances of the connection pool. This button is only available if you have more than one instance of the connection pool in your domain.

Configuring the Statement Cache for a JDBC Connection Pool

On the JDBC Connection Pool—>Configuration—>Connections tab, you can configure statement cache attributes for a connection pool. For more information about the statement cache, see [Increasing Performance with the Statement Cache](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/jdbc_connection_pools.html#1107805). To configure the statement cache, follow these steps:

1. In the left pane, click to expand the Services, JDBC, and Connection Pool nodes to display the list of connection pools in the current domain.
2. Click the connection pool that you want to deploy. A dialog displays in the right pane showing the tabs associated with this instance.
3. Click the Configuration tab, then click the Connections tab.
4. In Statement Cache Type, select one of the following options:
   * LRU - After the statementCacheSize is met, the Least Recently Used statement is removed when a new statement is used.
   * Fixed - The first statementCacheSize number of statements is stored and stay fixed in the cache. No new statements are cached unless the cache is manually cleared.
   * See [Statement Cache Algorithms](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/jdbc_connection_pools.html#1115624) for more information.
5. In Statement Cache Size, enter the number of statements to cache per connection per connection pool instance. The default value is 10. See [Statement Cache Size](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/jdbc_connection_pools.html#1116241) for more information.
6. Click Apply to save your changes.

Adding a Note to a JDBC Connection Pool

1. In the left pane, click to the JDBC node to expand it.
2. Click the Connection Pools node to expand it and show the list of connection pools defined in your domain.
3. Click the connection pool to which you want to add a note. A dialog displays in the right pane showing tabs with attributes for the connection pool.
4. Click the Notes tab. Type the note in the Notes field.
5. Click Apply to save your changes.

&#x20;

***

Application-Scoped JDBC Connection Pools

When you package your enterprise applications, you can include the weblogic-application.xml supplemental deployment descriptor, which you use to configure _application scoping_. Within the weblogic-application.xml file, you can configure JDBC connection pools that are created when you deploy the enterprise application.

An instance of the connection pool is created with each instance of your application. This means an instance of the pool is created with the application on each node that the application is targeted to. It is important to keep this in mind when considering pool sizing.

Connection pools created in this manner are known as _application-scoped connection pools_, _app scoped pools_, _application local pools_, _app local pools_, or _local pools_, and are scoped for the enterprise application only. That is, they are isolated for use by the enterprise application.

For more information about application scoping and application scoped resources, see:

* [Overview of Application Scoping](https://docs.oracle.com/cd/E13222_01/wls/docs81b/xml/xml_appscop.html)
* [weblogic-application.xml Deployment Descriptor Elements](https://docs.oracle.com/cd/E13222_01/wls/docs81b/programming/app_xml.html#app-scoped-pool)
* Packaging Enterprise Applications
* [Two-Phase Deployment](https://docs.oracle.com/cd/E13222_01/wls/docs81b/deployment/concepts.html)

&#x20;

***

Connection Pool and Data Source Configuration Guidelines

Drivers Supported for Local Transactions

JDBC 2.0 drivers that support the JDBC Core 2.0 API (java.sql), such as the WebLogic jDriver for Oracle. The API allows you to create the class objects necessary to establish a connection with a data source, send queries and update statements to the data source, and process the results.

Drivers Supported for Distributed Transactions Using XA

Any JDBC driver that supports JDBC 2.0 distributed transactions standard extension interfaces (javax.sql.XADataSource, javax.sql.XAConnection, javax.transaction.xa.XAResource), such as the WebLogic jDriver for Oracle/XA.

Drivers Supported for Distributed Transactions without XA

Any JDBC driver that supports JDBC 2.0 Core API but does not support JDBC 2.0 distributed transactions standard extension interfaces (non-XA). Only one non-XA JDBC driver can participate in a distributed transaction. See [Configuring Non-XA JDBC Drivers for Distributed Transactions](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/jdbc_connection_pools.html#1120770)

Configuring JDBC Drivers for Local Transactions

To configure JDBC drivers for local transactions, set up the JDBC connection pool as follows:

* Specify the Driver Classname attribute as the name of the class supporting the java.sql.Driver interface.
* Specify the data properties. These properties are passed to the specific Driver as driver properties.

For more information on WebLogic two-tier JDBC drivers, refer to the BEA documentation for the specific driver you are using: [_Using WebLogic jDriver for Oracle_](https://docs.oracle.com/cd/E13222_01/wls/docs81b/oracle/index.html) and [_Using WebLogic jDriver for Microsoft SQL Server_](https://docs.oracle.com/cd/E13222_01/wls/docs81b/mssqlserver4/index.html). If you are using a third-party driver, refer to [Using Third-Party JDBC XA Drivers with WebLogic Server](https://docs.oracle.com/cd/E13222_01/wls/docs81b/jta/thirdpartytx.html) in _Programming WebLogic JTA_ and the vendor-specific documentation. The following tables show sample JDBC connection pool and Data Source configurations using the WebLogic jDrivers.

The following table shows a sample connection pool configuration using the WebLogic jDriver for Oracle.

**Note:** The following configuration examples use a Password attribute. The Password attribute value overrides any password defined in Properties (as a name/value pair). This attribute is passed to the 2-tier JDBC driver when creating physical database connections. The value is stored in an encrypted form in the config.xml file and can be used to avoid storing passwords in clear text in that file.

Table 11-1 WebLogic jDriver for Oracle: Connection Pool Configuration

<table data-header-hidden><thead><tr><th valign="top"></th><th valign="top"></th></tr></thead><tbody><tr><td valign="top"><strong>Attribute Name</strong></td><td valign="top"><strong>Attribute Value</strong></td></tr><tr><td valign="top">General Tab (<a href="https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcconnectionpool_config_general.html#1104829">JDBC Connection Pool --> Configuration --> General</a>)</td><td valign="top"></td></tr><tr><td valign="top">Name</td><td valign="top">myConnectionPool</td></tr><tr><td valign="top">URL</td><td valign="top">jdbc:weblogic:oracle</td></tr><tr><td valign="top">Driver Classname</td><td valign="top">weblogic.jdbc.oci.Driver</td></tr><tr><td valign="top">Properties</td><td valign="top">user=scott;server=localdb</td></tr><tr><td valign="top">Password</td><td valign="top">tiger (This value overrides any password defined in Properties as a name value pair)</td></tr><tr><td valign="top">Connections Tab (<a href="https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcconnectionpool_config_connections.html#1104829">JDBC Connection Pool --> Configuration --> Connections</a>)</td><td valign="top"></td></tr><tr><td valign="top">Initial Capacity</td><td valign="top">1</td></tr><tr><td valign="top">Max Capacity</td><td valign="top">15</td></tr><tr><td valign="top">Capacity Increment</td><td valign="top">1</td></tr><tr><td valign="top">Shrink Period</td><td valign="top">15</td></tr><tr><td valign="top">Test Table Name</td><td valign="top">dual</td></tr><tr><td valign="top">Target and Deploy (<a href="https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcconnectionpool_targetdeploy.html#1106545">JDBC Connection Pool --> Target and Deploy</a>)</td><td valign="top"></td></tr><tr><td valign="top">Targets</td><td valign="top">myserver</td></tr></tbody></table>

The following table shows a sample Data Source configuration using the WebLogic jDriver for Oracle.

Table 11-2 Data Source Configuration

<table data-header-hidden><thead><tr><th valign="top"></th><th valign="top"></th></tr></thead><tbody><tr><td valign="top"><strong>Attribute Name</strong></td><td valign="top"><strong>Attribute Value</strong></td></tr><tr><td valign="top">Configuration Tab (<a href="https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcdatasource_config.html#1104829">JDBC Data Source --> Configuration</a>)</td><td valign="top"></td></tr><tr><td valign="top">Name</td><td valign="top">myDataSource</td></tr><tr><td valign="top">JNDI Name</td><td valign="top">myconnection</td></tr><tr><td valign="top">Pool Name</td><td valign="top">myConnectionPool</td></tr><tr><td valign="top">Row Prefetch Size</td><td valign="top">48</td></tr><tr><td valign="top">Stream Chunk Size</td><td valign="top">256</td></tr><tr><td valign="top">Target and Deploy Tab (<a href="https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcdatasource_targetdeploy.html#1107048">JDBC Data Source --> Target and Deploy</a>)</td><td valign="top"></td></tr><tr><td valign="top">Targets</td><td valign="top">myserver</td></tr></tbody></table>

The following table shows a sample connection pool configuration using the IBM Informix JDBC Driver.

Table 11-3 IBM Informix JDBC Driver: Connection Pool Configuration

<table data-header-hidden><thead><tr><th valign="top"></th><th valign="top"></th></tr></thead><tbody><tr><td valign="top"><strong>Attribute Name</strong></td><td valign="top"><strong>Attribute Value</strong></td></tr><tr><td valign="top">General Tab (<a href="https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcconnectionpool_config_general.html#1104829">JDBC Connection Pool --> Configuration --> General</a>)</td><td valign="top"></td></tr><tr><td valign="top">Name</td><td valign="top">myConnectionPool</td></tr><tr><td valign="top">URL</td><td valign="top">jdbc:informix-sqli:ifxserver:1543</td></tr><tr><td valign="top">Driver Classname</td><td valign="top">com.informix.jdbc.IfxDriver</td></tr><tr><td valign="top">Properties</td><td valign="top">informixserver=ifxserver;user=informix</td></tr><tr><td valign="top">Password</td><td valign="top">informix (Displayed as ******)</td></tr><tr><td valign="top">Connections Tab (<a href="https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcconnectionpool_config_connections.html#1104829">JDBC Connection Pool --> Configuration --> Connections</a>)</td><td valign="top"></td></tr><tr><td valign="top">Initial Capacity</td><td valign="top">1</td></tr><tr><td valign="top">Max Capacity</td><td valign="top">15</td></tr><tr><td valign="top">Capacity Increment</td><td valign="top">1</td></tr><tr><td valign="top">Login Delay Seconds</td><td valign="top">1</td></tr><tr><td valign="top">Shrink Period</td><td valign="top">15</td></tr><tr><td valign="top">Target and Deploy (<a href="https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcconnectionpool_targetdeploy.html#1106545">JDBC Connection Pool --> Target and Deploy</a>)</td><td valign="top"></td></tr><tr><td valign="top">Targets</td><td valign="top">myserver</td></tr></tbody></table>

Configuring XA JDBC Drivers for Distributed Transactions

To allow XA JDBC drivers to participate in distributed transactions, configure the JDBC connection pool as follows:

* Specify the Driver Classname attribute as the name of the class supporting the javax.sql.XADataSource interface.
* Make sure that the database properties are specified. These properties are passed to the specified XADataSource as data source properties. For more information on data source properties for the WebLogic jDriver for Oracle, see [WebLogic jDriver for Oracle/XA Data Source Properties.](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/jdbc_connection_pools.html#1116510) For information about data source properties for third-party drivers, see the vendor documentation.

The following table shows an example of a JDBC connection pool configuration using the WebLogic jDriver for Oracle in XA mode.

Table 11-4 WebLogic jDriver for Oracle/XA: Connection Pool Configuration

<table data-header-hidden><thead><tr><th valign="top"></th><th valign="top"></th></tr></thead><tbody><tr><td valign="top"><strong>Attribute Name</strong></td><td valign="top"><strong>Attribute Value</strong></td></tr><tr><td valign="top">General Tab (<a href="https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcconnectionpool_config_general.html#1104829">JDBC Connection Pool --> Configuration --> General</a>)</td><td valign="top"></td></tr><tr><td valign="top">Name</td><td valign="top">fundsXferAppPool</td></tr><tr><td valign="top">URL</td><td valign="top"><em>(none required)</em></td></tr><tr><td valign="top">Driver Classname</td><td valign="top">weblogic.jdbc.oci.xa.XADataSource</td></tr><tr><td valign="top">Properties</td><td valign="top">user=scott;server=localdb</td></tr><tr><td valign="top">Password</td><td valign="top">tiger (This value overrides any password defined in Properties as a name value pair)</td></tr><tr><td valign="top">Connections Tab (<a href="https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcconnectionpool_config_connections.html#1104829">JDBC Connection Pool --> Configuration --> Connections</a>)</td><td valign="top"></td></tr><tr><td valign="top">Initial Capacity</td><td valign="top">1</td></tr><tr><td valign="top">Max Capacity</td><td valign="top">15</td></tr><tr><td valign="top">Capacity Increment</td><td valign="top">1</td></tr><tr><td valign="top">Shrink Period</td><td valign="top">15</td></tr><tr><td valign="top">Test Table Name</td><td valign="top">dual</td></tr><tr><td valign="top">Target and Deploy (<a href="https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcconnectionpool_targetdeploy.html#1106545">JDBC Connection Pool --> Target and Deploy</a>)</td><td valign="top"></td></tr><tr><td valign="top">Targets</td><td valign="top">myserver</td></tr></tbody></table>

The following table shows an example of a Tx Data Source configuration using the WebLogic jDriver for Oracle in XA mode.

Table 11-5 WebLogic jDriver for Oracle/XA: Tx Data Source

<table data-header-hidden><thead><tr><th valign="top"></th><th valign="top"></th></tr></thead><tbody><tr><td valign="top"><strong>Attribute Name</strong></td><td valign="top"><strong>Attribute Value</strong></td></tr><tr><td valign="top">Configuration Tab (<a href="https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcdatasource_config.html#1104829">JDBC Data Source --> Configuration</a>)</td><td valign="top"></td></tr><tr><td valign="top">Name</td><td valign="top">fundsXferDataSource</td></tr><tr><td valign="top">JNDI Name</td><td valign="top">myapp.fundsXfer</td></tr><tr><td valign="top">Pool Name</td><td valign="top">fundsXferAppPool</td></tr><tr><td valign="top">Target and Deploy Tab (<a href="https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcdatasource_targetdeploy.html#1107048">JDBC Data Source --> Target and Deploy</a>)</td><td valign="top"></td></tr><tr><td valign="top">Targets</td><td valign="top">myserver</td></tr></tbody></table>

You can also configure the JDBC connection pool to use a third-party vendor's driver in XA mode. In such cases, the data source properties are set via reflection on the XADataSource instance using the JavaBeans design pattern. In other words, for property abc, the XADataSource instance must support get and set methods with the names getAbc and setAbc, respectively.

The following attributes are an example of a JDBC connection pool configuration using the Oracle Thin Driver.

Table 11-6 Oracle Thin Driver: Connection Pool Configuration

<table data-header-hidden><thead><tr><th valign="top"></th><th valign="top"></th></tr></thead><tbody><tr><td valign="top"><strong>Attribute Name</strong></td><td valign="top"><strong>Attribute Value</strong></td></tr><tr><td valign="top">General Tab (<a href="https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcconnectionpool_config_general.html#1104829">JDBC Connection Pool --> Configuration --> General</a>)</td><td valign="top"></td></tr><tr><td valign="top">Name</td><td valign="top">jtaXAPool</td></tr><tr><td valign="top">URL</td><td valign="top">jdbc:oracle:thin:@server:port:sid</td></tr><tr><td valign="top">Driver Classname</td><td valign="top">oracle.jdbc.xa.client.OracleXADataSource</td></tr><tr><td valign="top">Properties</td><td valign="top">user=scott</td></tr><tr><td valign="top">Password</td><td valign="top">tiger (This value overrides any password defined in Properties as a name value pair)</td></tr><tr><td valign="top">Connections Tab (<a href="https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcconnectionpool_config_connections.html#1104829">JDBC Connection Pool --> Configuration --> Connections</a>)</td><td valign="top"></td></tr><tr><td valign="top">Initial Capacity</td><td valign="top">1</td></tr><tr><td valign="top">Max Capacity</td><td valign="top">15</td></tr><tr><td valign="top">Capacity Increment</td><td valign="top">1</td></tr><tr><td valign="top">Shrink Period</td><td valign="top">15</td></tr><tr><td valign="top">Test Table Name</td><td valign="top">dual</td></tr><tr><td valign="top">Target and Deploy (<a href="https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcconnectionpool_targetdeploy.html#1106545">JDBC Connection Pool --> Target and Deploy</a>)</td><td valign="top"></td></tr><tr><td valign="top">Targets</td><td valign="top">myserver</td></tr></tbody></table>

The following table shows an example of a Tx Data Source configuration using the Oracle Thin Driver.

Table 11-7 Oracle Thin Driver: Tx Data Source Configuration

<table data-header-hidden><thead><tr><th valign="top"></th><th valign="top"></th></tr></thead><tbody><tr><td valign="top"><strong>Attribute Name</strong></td><td valign="top"><strong>Attribute Value</strong></td></tr><tr><td valign="top">Configuration Tab (<a href="https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcdatasource_config.html#1104829">JDBC Data Source --> Configuration</a>)</td><td valign="top"></td></tr><tr><td valign="top">Name</td><td valign="top">jtaXADS</td></tr><tr><td valign="top">JNDI Name</td><td valign="top">jtaXADS</td></tr><tr><td valign="top">Pool Name</td><td valign="top">jtaXAPool</td></tr><tr><td valign="top">Target and Deploy Tab (<a href="https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcdatasource_targetdeploy.html#1107048">JDBC Data Source --> Target and Deploy</a>)</td><td valign="top"></td></tr><tr><td valign="top">Targets</td><td valign="top">myserver</td></tr></tbody></table>

The following table shows an example of a JDBC connection pool configuration for distributed transactions using the PointBase JDBC driver.

Table 11-8 PointBase: Connection Pool Configuration

<table data-header-hidden><thead><tr><th valign="top"></th><th valign="top"></th></tr></thead><tbody><tr><td valign="top"><strong>Attribute Name</strong></td><td valign="top"><strong>Attribute Value</strong></td></tr><tr><td valign="top">General Tab (<a href="https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcconnectionpool_config_general.html#1104829">JDBC Connection Pool --> Configuration --> General</a>)</td><td valign="top"></td></tr><tr><td valign="top">Name</td><td valign="top">demoXAPool</td></tr><tr><td valign="top">URL</td><td valign="top">jdbc:pointbase:server://localhost/demo</td></tr><tr><td valign="top">Driver Classname</td><td valign="top">com.pointbase.xa.xaDataSource</td></tr><tr><td valign="top">Properties</td><td valign="top"><p>user=public</p><p>DatabaseName=jdbc:pointbase:server://localhost/demo</p><p><br></p></td></tr><tr><td valign="top">Password</td><td valign="top">public (Displayed as ******)</td></tr><tr><td valign="top">Connections Tab (<a href="https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcconnectionpool_config_connections.html#1104829">JDBC Connection Pool --> Configuration --> Connections</a>)</td><td valign="top"></td></tr><tr><td valign="top">Initial Capacity</td><td valign="top">1</td></tr><tr><td valign="top">Max Capacity</td><td valign="top">15</td></tr><tr><td valign="top">Capacity Increment</td><td valign="top">1</td></tr><tr><td valign="top">Supports Local Transaction</td><td valign="top">true</td></tr><tr><td valign="top">Shrink Period</td><td valign="top">15</td></tr><tr><td valign="top">Test Table Name</td><td valign="top">users</td></tr><tr><td valign="top">Target and Deploy (<a href="https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcconnectionpool_targetdeploy.html#1106545">JDBC Connection Pool --> Target and Deploy</a>)</td><td valign="top"></td></tr><tr><td valign="top">Targets</td><td valign="top">myserver</td></tr></tbody></table>

Configure the Tx Data Source for use with a PointBase driver as follows.

Table 11-9 PointBase: Tx Data Source Configuration

<table data-header-hidden><thead><tr><th valign="top"></th><th valign="top"></th></tr></thead><tbody><tr><td valign="top"><strong>Attribute Name</strong></td><td valign="top"><strong>Attribute Value</strong></td></tr><tr><td valign="top">Configuration Tab (<a href="https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcdatasource_config.html#1104829">JDBC Data Source --> Configuration</a>)</td><td valign="top"></td></tr><tr><td valign="top">Name</td><td valign="top">jtaXADS</td></tr><tr><td valign="top">JNDI Name</td><td valign="top">JTAXADS</td></tr><tr><td valign="top">Pool Name</td><td valign="top">demoXAPool</td></tr><tr><td valign="top">Target and Deploy Tab (<a href="https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcdatasource_targetdeploy.html#1107048">JDBC Data Source --> Target and Deploy</a>)</td><td valign="top"></td></tr><tr><td valign="top">Targets</td><td valign="top">myserver</td></tr></tbody></table>

WebLogic jDriver for Oracle/XA Data Source Properties

[Table 11-10](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/jdbc_connection_pools.html#1107323) lists the data source properties supported by the WebLogic jDriver for Oracle. The JDBC 2.0 column indicates whether a specific data source property is a JDBC 2.0 standard data source property (S) or a WebLogic Server extension to JDBC (E).

The Optional column indicates whether a particular data source property is optional or not. Properties marked with Y\* are mapped to the corresponding fields of the Oracle xa\_open string (value of the openString property) as listed in [Table 11-10](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/jdbc_connection_pools.html#1107323). If they are not specified, their default values are taken from the openString property. If they are specified, their values should match those specified in the openString property. If the properties do not match, a SQLException is thrown when you attempt to make an XA connection.

Mandatory properties marked with N\* are also mapped to the corresponding fields of the Oracle xa\_open string. Specify these properties when specifying the Oracle xa\_open string. If they are not specified or if they are specified but do not match, an SQLException is thrown when you attempt to make an XA connection.

Property Names marked with \*\* are supported but not used by WebLogic Server.

Table 11-10 Data Source Properties for WebLogic jDriver for Oracle/XA

<table data-header-hidden><thead><tr><th valign="top"></th><th valign="top"></th><th valign="top"></th><th valign="top"></th><th valign="top"></th><th valign="top"></th></tr></thead><tbody><tr><td valign="top"><strong>Property Name</strong></td><td valign="top"><strong>Type</strong></td><td valign="top"><strong>Description</strong></td><td valign="top"><strong>JDBC 2.0</strong><br><strong>standard/extension</strong></td><td valign="top"><strong>Optional</strong></td><td valign="top"><strong>Default Value</strong></td></tr><tr><td valign="top">databaseName**</td><td valign="top">String</td><td valign="top">Name of a particular database on a server.</td><td valign="top">S</td><td valign="top">Y</td><td valign="top">None</td></tr><tr><td valign="top">dataSourceName</td><td valign="top">String</td><td valign="top">A data source name; used to name an underlying XADataSource.</td><td valign="top">S</td><td valign="top">Y</td><td valign="top">Connection Pool Name</td></tr><tr><td valign="top">description</td><td valign="top">String</td><td valign="top">Description of this data source.</td><td valign="top">S</td><td valign="top">Y</td><td valign="top">None</td></tr><tr><td valign="top">networkProtocol**</td><td valign="top">String</td><td valign="top">Network protocol used to communicate with the server.</td><td valign="top">S</td><td valign="top">Y</td><td valign="top">None</td></tr><tr><td valign="top">password</td><td valign="top">String</td><td valign="top">A database password.</td><td valign="top">S</td><td valign="top">N*</td><td valign="top">None</td></tr><tr><td valign="top">portNumber**</td><td valign="top">Int</td><td valign="top">Port number at which a server is listening for requests.</td><td valign="top">S</td><td valign="top">Y</td><td valign="top">None</td></tr><tr><td valign="top">roleName**</td><td valign="top">String</td><td valign="top">The initial SQL role name.</td><td valign="top">S</td><td valign="top">Y</td><td valign="top">None</td></tr><tr><td valign="top">serverName</td><td valign="top">String</td><td valign="top">Database server name.</td><td valign="top">S</td><td valign="top">Y*</td><td valign="top">None</td></tr><tr><td valign="top">user</td><td valign="top">String</td><td valign="top">User's account name.</td><td valign="top">S</td><td valign="top">N*</td><td valign="top">None</td></tr><tr><td valign="top">openString</td><td valign="top">String</td><td valign="top">Oracle's XA open string.</td><td valign="top">E</td><td valign="top">Y</td><td valign="top">None</td></tr><tr><td valign="top">oracleXATrace</td><td valign="top">String</td><td valign="top">Indicates whether XA tracing output is enabled. If enabled (true), a file with a name in the form of xa_poolnamedate.trc is placed in the directory in which the server is started.</td><td valign="top">E</td><td valign="top">Y</td><td valign="top">true</td></tr></tbody></table>

[Table 11-11](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/jdbc_connection_pools.html#1107486) lists the mapping between Oracle's xa\_open string fields and data source properties.

Table 11-11 Mapping of xa\_open String Names to JDBC Data Source Properties

<table data-header-hidden><thead><tr><th valign="top"></th><th valign="top"></th><th valign="top"></th></tr></thead><tbody><tr><td valign="top"><strong>Oracle xa_open String Field Name</strong></td><td valign="top"><strong>JDBC 2.0 Data Source Property</strong></td><td valign="top"><strong>Optional</strong></td></tr><tr><td valign="top">acc</td><td valign="top">user, password</td><td valign="top">N</td></tr><tr><td valign="top">sqlnet</td><td valign="top">ServerName</td><td valign="top"><br></td></tr></tbody></table>

**Note:** You must specify Threads=true in Oracle's xa\_open string.

For a complete description of Oracle's xa\_open string fields, see your Oracle documentation.

Additional XA Connection Pool Properties

When using connections from a connection pool in distributed transactions, you may need to set additional properties for the connection pool so that the connection pool handles the connection properly within WebLogic Server in the context of the transaction. You set these properties in the configuration file (config.xml) within the JDBCConnectionPool tag. By default, all additional properties are set to false. You set the properties to true to enable them.

In many cases, WebLogic Server automatically sets the proper value for these properties internally so that you do not have to set them manually.

KeepXAConnTillTxComplete

Some DBMSs require that you start and end a transaction in the same physical database connection. In some cases, a transaction in WebLogic Server may start in one physical database connection and end in another physical database connection. To force a connection pool to reserve a physical connection and provide the _same_ connection to an application throughout transaction processing until the transaction is complete, you set KeepXAConnTillTxComplete="true". For example:

> <pre><code><strong>&#x3C;JDBCConnectionPool KeepXAConnTillTxComplete="true" DriverName="com.sybase.jdbc2.jdbc.SybXADataSource" CapacityIncrement="5" InitialCapacity="10" MaxCapacity="25" Name="demoXAPool" Password="{3DES}vIF8diu4H0QmdfOipd4dWA==" Properties="User=dbuser;DatabaseName=dbname;ServerName=server_name_or_IP_address;PortNumber=serverPortNumber;NetworkProtocol=Tds;resourceManagerName=Lrm_name_in_xa_config;resourceManagerType=2" />
> </strong></code></pre>

**Note:** This property is _required_ to support distributed transactions with DB2 and Sybase.

Configuring Non-XA JDBC Drivers for Distributed Transactions

When configuring the JDBC connection pool to allow non-XA JDBC drivers to participate with other resources in distributed transactions, select the Emulate Two-Phase Commit for non-XA Driver attribute (EnableTwoPhaseCommit in the JDBCTxDataSource MBean) for the JDBC Tx Data Source. This parameter is ignored by resources that support the XAResource interface. Note that only one non-XA connection pool may participate in a distributed transaction. See [Emulating Two-Phase Commit](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/jdbc_datasources.html#1107722) for more information.

**Note:** There are risks to data integrity when using the Emulate Two-Phase Commit for non-XA Driver option. BEA recommends that you use an XA-compliant JDBC driver rather than use this option. Make sure you consider the risks below before enabling this option. See [Limitations and Risks](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/jdbc_datasources.html#1107726).

Non-XA Driver/Single Resource

If you are using only one non-XA driver and it is the only resource in the transaction, leave the Emulate Two-Phase Commit for non-XA Driver option unselected in the Console (accept the default EnableTwoPhaseCommit = false). In this case, the Transaction Manager performs a one-phase optimization.

Non-XA Driver/Multiple Resources

If you are using one non-XA JDBC driver with other XA resources, select Emulate Two-Phase Commit in the Administration Console (EnableTwoPhaseCommit = true).

When the Emulate Two-Phase Commit for non-XA Driver option is selected (EnableTwoPhaseCommit is set to true), the non-XA JDBC resource always returns XA\_OK during the XAResource.prepare() method call. The resource attempts to commit or roll back its local transaction in response to subsequent XAResource.commit() or XAResource.rollback() calls. If the resource commit or rollback fails, a heuristic error results. Application data may be left in an inconsistent state as a result of a heuristic failure.

When the Emulate Two-Phase Commit for non-XA Driver option is not selected in the Console (EnableTwoPhaseCommit is set to false), the non-XA JDBC resource causes XAResource.prepare() to fail. This mechanism ensures that there is only one participant in the transaction, as commit() throws a SystemException in this case. When there is only one resource participating in a transaction, the one phase optimization bypasses XAResource.prepare(), and the transaction commits successfully in most instances.

The following table shows configuration attributes for a sample JDBC connection pool using a non-XA JDBC driver.

Table 11-12 WebLogic jDriver for Oracle: Connection Pool Configuration

<table data-header-hidden><thead><tr><th valign="top"></th><th valign="top"></th></tr></thead><tbody><tr><td valign="top"><strong>Attribute Name</strong></td><td valign="top"><strong>Attribute Value</strong></td></tr><tr><td valign="top">General Tab (<a href="https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcconnectionpool_config_general.html#1104829">JDBC Connection Pool --> Configuration --> General</a>)</td><td valign="top"></td></tr><tr><td valign="top">Name</td><td valign="top">fundsXferAppPool</td></tr><tr><td valign="top">URL</td><td valign="top">jdbc:weblogic:oracle</td></tr><tr><td valign="top">Driver Classname</td><td valign="top">weblogic.jdbc.oci.Driver</td></tr><tr><td valign="top">Properties</td><td valign="top">user=scott;server=localdb</td></tr><tr><td valign="top">Password</td><td valign="top">tiger (Displayed as ***** when typed, hidden thereafter; this value overrides any password defined in Properties as a name value pair)</td></tr><tr><td valign="top">Connections Tab (<a href="https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcconnectionpool_config_connections.html#1104829">JDBC Connection Pool --> Configuration --> Connections</a>)</td><td valign="top"></td></tr><tr><td valign="top">Initial Capacity</td><td valign="top">0</td></tr><tr><td valign="top">Max Capacity</td><td valign="top">5</td></tr><tr><td valign="top">Capacity Increment</td><td valign="top">1</td></tr><tr><td valign="top">Shrink Period</td><td valign="top">15</td></tr><tr><td valign="top">Test Table Name</td><td valign="top">dual</td></tr><tr><td valign="top">Target and Deploy (<a href="https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcconnectionpool_targetdeploy.html#1106545">JDBC Connection Pool --> Target and Deploy</a>)</td><td valign="top"></td></tr><tr><td valign="top">Targets</td><td valign="top">myserver</td></tr></tbody></table>

The following table shows configuration attributes for a sample Tx Data Source using a non-XA JDBC driver.

Table 11-13 WebLogic j Driver for Oracle: Tx Data Source Configuration

<table data-header-hidden><thead><tr><th valign="top"></th><th valign="top"></th></tr></thead><tbody><tr><td valign="top"><strong>Attribute Name</strong></td><td valign="top"><strong>Attribute Value</strong></td></tr><tr><td valign="top">Configuration Tab (<a href="https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcdatasource_config.html#1104829">JDBC Data Source --> Configuration</a>)</td><td valign="top"></td></tr><tr><td valign="top">Name</td><td valign="top">fundsXferDataSource</td></tr><tr><td valign="top">JNDI Name</td><td valign="top">myapp.fundsXfer</td></tr><tr><td valign="top">Pool Name</td><td valign="top">fundsXferAppPool</td></tr><tr><td valign="top">Emulate Two-Phase Commit for non-XA Driver</td><td valign="top">selected (EnableTwoPhaseCommit = true)</td></tr><tr><td valign="top">Target and Deploy Tab (<a href="https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcdatasource_targetdeploy.html#1107048">JDBC Data Source --> Target and Deploy</a>)</td><td valign="top"></td></tr><tr><td valign="top">Targets</td><td valign="top">myserver</td></tr></tbody></table>

&#x20;

***

Security for JDBC Connection Pools

You can optionally restrict access to JDBC connection pools. In WebLogic Server, security policies answer the question "who has access" to a WebLogic resource. A security policy is created when you define an association between a WebLogic resource and a user, group, or role. A WebLogic resource has no protection until you assign it a security policy. For instructions on how to set up security for all WebLogic Server resources, see [Protecting WebLogic Resources](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/security_7x.html#1170617).

&#x20;

***

Managing JDBC Connection Pools

From the JDBC Connection Pool property tabs in the Administration Console, you can manage the connections pools in your domain. The following sections provide detailed instructions for manually performing management tasks on JDBC connection pools.

Resetting All Connections in a JDBC Connection Pool

When you reset a connection pool, WebLogic Server shuts down and recreates all database connections in the connection pool.

1. In the left pane, click to expand the Services, JDBC, and Connection Pools nodes to display the list of connection pools in the current domain.
2. Click the connection pool that you want to reset. A dialog displays in the right pane showing the tabs associated with this connection pool.
3. Click the Control tab. The control tab lists each server on which the connection pool is deployed.
4. Click Reset for each server on which you want to reset all connections in the connection pool.

Shrinking a JDBC Connection Pool

If you configure a connection pool so that it can add database connections as demand for connections increases, you can click the Shrink button on the Control tab to manually shrink the connection pool. When you shrink a connection pool, WebLogic Server reduces the number of connections in the pool to the greater of either the initial capacity or the number of connections currently in use.

1. In the left pane, click to expand the Services, JDBC, and Connection Pools nodes to display the list of connection pools in the current domain.
2. Click the connection pool that you want to reset. A dialog displays in the right pane showing the tabs associated with the connection pool.
3. Click the Control tab. The control tab lists each server on which the connection pool is deployed.
4. Click Shrink for each server on which you want to shrink the connection pool instance.

Suspending a JDBC Connection Pool

When you suspend a connection pool, you make the connections in the pool unavailable for applications to use. WebLogic Server provides the following options for suspending a connection pool:

* Suspend—which marks the pool as disabled and blocks any new requests for a connection from the connection pool. If connections are currently in use, the suspend operation will fail and will put the connection pool into an unknown state. To correct that state, you must shut down the pool by undeploying it. See [Shutting Down a JDBC Connection Pool](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/jdbc_connection_pools.html#1115169).
* Force Suspend—which marks the pool as disabled and prevents applications from using connections from the connection pool, including those connections currently in use.

Connections is a suspended connection pool remain intact. The connections are not recreated when you resume the connection pool.

To suspend a connection pool, follow these steps:

1. In the left pane, click to expand the Services, JDBC, and Connection Pool nodes to display the list of connection pools in the current domain.
2. Haga clic en el grupo de conexiones que desea suspender. En el panel derecho aparecerá un cuadro de diálogo con las pestañas asociadas al grupo de conexiones.
3. Haz clic en la pestaña Control. En la pestaña Control se muestra cada servidor en el que está implementado el grupo de conexiones.
4. Para cada servidor de la lista, elija una de las siguientes opciones:
   * Haz clic en Suspender para bloquear las nuevas solicitudes de reserva de conexión del grupo de conexiones y marcar dicho grupo como deshabilitado. Si hay conexiones en uso, esta operación fallará.
   * Haz clic en Forzar suspensión para bloquear las nuevas solicitudes de reserva de conexiones del grupo de conexiones y para detener el uso actual de las conexiones del grupo. Esta operación también desactiva el grupo de conexiones.

Reanudando un grupo de conexiones JDBC

Tras suspender manualmente un grupo de conexiones, puede volver a habilitarlo haciendo clic en Reanudar en la pestaña Control del grupo de conexiones JDBC . No puede utilizar la función Reanudar para reiniciar un grupo de conexiones que no se haya iniciado correctamente.

Siga estas instrucciones.

1. En el panel izquierdo, haga clic para expandir los nodos Servicios, JDBC y Grupo de conexiones para mostrar la lista de grupos de conexiones en el dominio actual.
2. Haga clic en el grupo de conexiones que desea reanudar. En el panel derecho aparecerá un cuadro de diálogo con las pestañas asociadas al grupo de conexiones.
3. Haz clic en la pestaña Control. En la pestaña Control se muestra cada servidor en el que está implementado el grupo de conexiones.
4. Haz clic en el botón Reanudar para la instancia del grupo de conexiones que deseas reactivar. Esta opción solo está disponible para grupos de conexiones que se hayan suspendido correctamente.

Cierre de un grupo de conexiones JDBC

Para cerrar una instancia de un grupo de conexiones, puede desinstalar dicho grupo en el servidor. Esta operación cierra todas las conexiones físicas a la base de datos en el grupo de conexiones. Para cerrar el grupo de conexiones en más de un destino, debe desinstalarlo en cada destino de implementación.

Sigue estos pasos:

1. En el panel izquierdo, haga clic para expandir los nodos Servicios, JDBC y Grupos de conexiones para mostrar la lista de grupos de conexiones en el dominio actual.
2. Haga clic en el grupo de conexiones que desea cerrar. En el panel derecho aparecerá un cuadro de diálogo con las pestañas asociadas a esta instancia.
3. Haz clic en la pestaña Destino e implementación.
4. Desactive la casilla de verificación de los servidores o clústeres en los que desee desactivar el grupo de conexiones. Haga clic en Aplicar para guardar los cambios.

Consulte la siguiente información relacionada:

* [Restablecimiento de todas las conexiones en un grupo de conexiones JDBC](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/jdbc_connection_pools.html#1115139)
* [Suspensión de un grupo de conexiones JDBC](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/jdbc_connection_pools.html#1115153)

Reiniciar un grupo de conexiones JDBC

Para reiniciar un grupo de conexiones después de haberlo desactivado (consulte la [sección "Desactivar un grupo de conexiones JDBC](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/jdbc_connection_pools.html#1115169) "), vuelva a implementarlo en los servidores y clústeres. Consulte la sección " [Implementar un grupo de conexiones JDBC en uno o más servidores o clústeres"](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/jdbc_connection_pools.html#1106179) para obtener instrucciones.

Destrucción o eliminación de un grupo de conexiones JDBC

Al destruir un grupo de conexiones JDBC, se cierran todas las conexiones a la base de datos _en todas las instancias_ del grupo de conexiones y se elimina la configuración del grupo de conexiones del dominio.

**Nota:** Al destruir un grupo de conexiones, se destruyen todas las instancias de dicho grupo, no solo la instancia para la que se hizo clic en el botón Destruir.

En WebLogic Server existen dos opciones para destruir grupos de conexiones:

* Destruir: Cierra todas las conexiones de base de datos en todas las instancias del grupo de conexiones y elimina permanentemente la configuración del grupo de conexiones del dominio. Si hay conexiones en uso en el grupo de conexiones, la operación fallará.
* Destrucción forzada: cierra de forma forzada todas las conexiones de base de datos en todas las instancias del grupo de conexiones, incluso si hay conexiones en uso, y elimina permanentemente la configuración del grupo de conexiones del dominio.

Para destruir un grupo de conexiones, siga estos pasos:

1. En el panel izquierdo, haga clic para expandir los nodos Servicios, JDBC y Grupos de conexiones para mostrar la lista de grupos de conexiones en el dominio actual.
2. Haga clic en el grupo de conexiones que desea eliminar. En el panel derecho aparecerá un cuadro de diálogo con las pestañas asociadas al grupo de conexiones.
3. Haz clic en la pestaña Control. En la pestaña Control se muestra cada servidor en el que está implementado el grupo de conexiones.
4. Para cualquier servidor de la lista, elija una de las siguientes opciones:
   * Haz clic en Destruir para cerrar todas las conexiones de la base de datos y eliminar el grupo de conexiones. Esta acción se aplica a todos los servidores. Si hay una conexión en uso, la operación fallará.
   * Haz clic en Forzar destrucción para cerrar forzosamente todas las conexiones a la base de datos y eliminar el grupo de conexiones. Esta acción se aplica a todos los servidores.

Borrar la caché de sentencias para un grupo de conexiones JDBC

Para borrar la caché de sentencias para todas las conexiones en un grupo de conexiones, siga estos pasos:

1. En el panel izquierdo, haga clic para expandir los nodos Servicios, JDBC y Grupos de conexiones para mostrar la lista de grupos de conexiones en el dominio actual.
2. Haga clic en el grupo de conexiones para el que desea borrar la caché de sentencias. En el panel derecho aparecerá un cuadro de diálogo con las pestañas asociadas a este grupo de conexiones.
3. Haz clic en la pestaña Control. En la pestaña Control se muestra cada servidor en el que está implementado el grupo de conexiones.
4. Haga clic en Borrar caché de sentencias para cada servidor en el que desee borrar la caché de sentencias para todas las conexiones del grupo de conexiones. Repita el proceso para cada instancia del grupo de conexiones según sea necesario.

Para obtener más información sobre la caché de sentencias para un grupo de conexiones, consulte el artículo " [Aumento del rendimiento con la caché de sentencias"](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/jdbc_connection_pools.html#1107805) .

&#x20;

***

Supervisión de un grupo de conexiones JDBC

Supervisión de conexiones en un grupo de conexiones JDBC

1. En el panel izquierdo, haga clic en el nodo JDBC para expandirlo.
2. Haga clic en el nodo Grupos de conexión para expandirlo y ver la lista de grupos de conexión definidos en su dominio.
3. Haga clic en el grupo de conexiones del que desea ver la información de conexión a la base de datos. En el panel derecho aparecerá un cuadro de diálogo con pestañas que muestran los atributos del grupo de conexiones.
4. Haz clic en la pestaña "Monitorización" y, a continuación, en el enlace "Monitorizar todos los grupos activos". Se mostrará una tabla con información sobre las conexiones en el grupo de conexiones JDBC seleccionado.

Para obtener detalles sobre la información mostrada, consulte [JDBC Connection Pool --> Monitoring](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/domain_jdbcconnectionpool_monitor.html#1104829) .

&#x20;

***

Ajuste de los grupos de conexiones

Al configurar correctamente los grupos de conexiones en su dominio de WebLogic Server, puede mejorar el rendimiento de la aplicación y del sistema.

Aumento del rendimiento con la caché de sentencias

Al utilizar sentencias preparadas o invocables en una aplicación o EJB, se genera una considerable sobrecarga de procesamiento debido a la comunicación entre el servidor de aplicaciones y el servidor de base de datos, así como en el propio servidor de base de datos. Para minimizar estos costos, WebLogic Server puede almacenar en caché las sentencias utilizadas en las aplicaciones. Cuando una aplicación o EJB invoca alguna de las sentencias almacenadas en la caché, WebLogic Server reutiliza dicha sentencia. La reutilización de sentencias reduce el uso de la CPU en el servidor de base de datos, lo que mejora el rendimiento de la sentencia actual y libera ciclos de CPU para otras tareas.

Cada conexión en un grupo de conexiones tiene su propia caché individual de sentencias preparadas y ejecutables que se utilizan en la conexión. Sin embargo, las opciones de caché de sentencias se configuran por grupo de conexiones. Es decir, la caché de sentencias para cada conexión en un grupo de conexiones utiliza las opciones de caché de sentencias especificadas para dicho grupo. Las opciones de configuración de la caché de sentencias incluyen:

* **Tipo de caché de sentencias** : el algoritmo que determina qué sentencias se almacenarán en la caché de sentencias. Consulte [Algoritmos de caché de sentencias](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/jdbc_connection_pools.html#1115624) .
* **Tamaño de la caché de sentencias** : número de sentencias que se almacenarán en la caché para cada conexión. El valor predeterminado es 10. Consulte [Tamaño de la caché de sentencias](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/jdbc_connection_pools.html#1116241) .

Puede utilizar los siguientes métodos para configurar las opciones de caché de sentencias para un grupo de conexiones:

* Utilizar la consola de administración (opción preferida). Consulte [Configuración de la caché de sentencias para un grupo de conexiones JDBC](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/jdbc_connection_pools.html#1116526) .
* Uso de la API de administración de WebLogic. Consulte los siguientes métodos en la [documentación Javadoc para las clases de WebLogic](https://docs.oracle.com/cd/E13222_01/wls/docs81b/javadocs/weblogic/management/configuration/JDBCConnectionPoolMBean.html) :
* obtenerStatementCacheType()
* setStatementCacheType(tipo de cadena)
* getPreparedStatementCacheSize()
* establecerPreparedStatementCacheSize(int cacheSize)
* Directamente en el archivo de configuración (normalmente config.xml ).

Para establecer el tamaño de la caché de sentencias preparadas para un grupo de conexiones mediante el archivo de configuración, antes de iniciar el servidor, abra el archivo config.xml en un editor y, a continuación, añada una entrada para el atributo PreparedStatementCacheSize en la etiqueta JDBCConnectionPool . Por ejemplo:

> <pre><code>    &#x3C;JDBCConnectionPool CapacityIncrement="5" 
>         DriverName="com.pointbase.jdbc.jdbcUniversalDriver" 
>         InitialCapacity="5" MaxCapacity="20" Name="demoPool" 
>         Password="{3DES}ANfMduXgaaGMeS8+CR1xoA==" 
> <strong>        PreparedStatementCacheSize="10"  StatementCacheType="LRU"
> </strong>         Properties="user=examples" 
>         RefreshMinutes="0" ShrinkPeriodMinutes="15" 
>         ShrinkingEnabled="true" Targets="examplesServer" 
>         TestConnectionsOnRelease="false" 
>         TestConnectionsOnReserve="false" 
>         URL="jdbc:pointbase:server://localhost/demo"/>
> </code></pre>

También puede borrar manualmente la caché de sentencias para un grupo de conexiones. Consulte [Borrar la caché de sentencias para un grupo de conexiones JDBC](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/jdbc_connection_pools.html#1115180) .

Algoritmos de caché de sentencias

El tipo de caché de sentencias (o algoritmo) determina qué sentencias preparadas y ejecutables se almacenarán en la caché para cada conexión en un grupo de conexiones. Puede elegir entre las siguientes opciones:

* [LRU (Menos usado recientemente)](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/jdbc_connection_pools.html#1115749)
* [Fijado](https://docs.oracle.com/cd/E13222_01/wls/docs81b/ConsoleHelp/jdbc_connection_pools.html#1115761)

LRU (Menos usado recientemente)

Cuando selecciona LRU (menos usado recientemente, por defecto) como tipo de caché de sentencias, WebLogic Server almacena en caché las sentencias preparadas y ejecutables utilizadas en la conexión hasta que se alcanza el tamaño de la caché de sentencias. Cuando una aplicación llama a connection.prepare statement , WebLogic Server comprueba si la sentencia está almacenada en la caché de sentencias. Si es así, WebLogic Server devuelve la sentencia almacenada en caché (si no se está utilizando). Si la sentencia no está en la caché y esta está llena (número de sentencias en la caché = tamaño de la caché de sentencias), WebLogic Server determina cuál de las sentencias existentes en la caché fue la menos usada recientemente y la reemplaza con la nueva.

El algoritmo de caché de sentencias LRU en WebLogic Server utiliza un esquema LRU aproximado.

Fijado

Cuando selecciona FIJO como tipo de caché de sentencias, WebLogic Server almacena en caché las sentencias preparadas y ejecutables utilizadas en la conexión hasta que se alcanza el tamaño de la caché de sentencias. Si se utilizan sentencias adicionales, estas no se almacenan en caché.

Con este algoritmo de caché de sentencias, puede almacenar inadvertidamente en caché sentencias que se usan con poca frecuencia. En muchos casos, se prefiere el algoritmo LRU porque las sentencias poco utilizadas acabarán siendo reemplazadas en la caché por sentencias de uso frecuente.

Tamaño de la caché de la declaración

El atributo Tamaño de caché de sentencias determina la cantidad total de sentencias preparadas y ejecutables que se almacenan en caché para cada conexión en cada instancia del grupo de conexiones. Al almacenar sentencias en caché, puede mejorar el rendimiento de su sistema. Sin embargo, debe considerar cómo su sistema de gestión de bases de datos (DBMS) maneja las sentencias preparadas y ejecutables abiertas. En muchos casos, el DBMS mantendrá un cursor para cada sentencia abierta. Esto se aplica a las sentencias preparadas y ejecutables en la caché de sentencias. Si almacena demasiadas sentencias en caché, podría exceder el límite de cursores abiertos en su servidor de base de datos.

Por ejemplo, si tiene un grupo de conexiones con 10 conexiones implementadas en 2 servidores, si establece el tamaño de la caché de sentencias en 10 (el valor predeterminado), puede abrir 200 (10 x 2 x 10) cursores en su servidor de base de datos para las sentencias almacenadas en caché.

Restricciones de uso para la caché de sentencias

El uso de la caché de sentencias puede mejorar drásticamente el rendimiento, pero debe tener en cuenta sus limitaciones antes de decidir utilizarla. Tenga en cuenta las siguientes restricciones al usar la caché de sentencias preparadas.

Es posible que existan otros problemas relacionados con el almacenamiento en caché de sentencias que no se mencionan aquí. Si observa errores en su sistema relacionados con sentencias preparadas o invocables, debería establecer el tamaño de la caché de sentencias preparadas en 0 , lo que desactiva el almacenamiento en caché de sentencias preparadas, para comprobar si el problema se debe al almacenamiento en caché de sentencias preparadas.

Llamar a una instrucción almacenada después de un cambio en la base de datos puede provocar errores.

Las sentencias preparadas almacenadas en la caché hacen referencia a objetos específicos de la base de datos en el momento en que se almacenan en caché. Si realiza operaciones DDL (lenguaje de definición de datos) sobre objetos de la base de datos a los que se hace referencia en las sentencias preparadas almacenadas en la caché, estas podrían fallar la próxima vez que las ejecute. Por ejemplo, si almacena en caché una sentencia como \`select \* from emp\` y luego elimina y vuelve a crear la tabla \`emp\` , la próxima vez que ejecute la sentencia almacenada en caché, esta podría fallar porque la tabla \`emp\` que existía cuando se preparó la sentencia ya no existe.

Asimismo, las sentencias preparadas están vinculadas al tipo de datos de cada columna de una tabla en la base de datos en el momento en que se almacenan en caché. Si se agregan, eliminan o reorganizan columnas en una tabla, es probable que las sentencias preparadas almacenadas en la caché fallen al ejecutarse nuevamente.

Estas limitaciones dependen del comportamiento de su sistema de gestión de bases de datos (DBMS).

Uso de setNull en una instrucción preparada

Al usar el jDriver de WebLogic para Oracle para conectarse a la base de datos, si almacena en caché una sentencia preparada que usa una variable de enlace setNull , debe establecer la variable al tipo de datos correcto. Si usa un tipo de datos genérico, como en el siguiente ejemplo, la sentencia podría fallar al ejecutarse con un valor distinto de null.

> ```
> java.sql.Types.Long sal=null
> ```

> ```
> . 
> . 
> .
> ```

> <pre><code>if (sal == null) 
> <strong>    setNull(2, int )//Esto es incorrecto 
> </strong>else 
>     setLong(2,sal)
> </code></pre>

En su lugar, utilice lo siguiente:

> ```
> if (sal == null) 
>     setNull(2,long)//Esto es correcto 
> else 
>     setLong(2,sal)
> ```

Este problema se presenta de forma constante al usar el controlador jDriver de WebLogic para Oracle. También puede ocurrir al usar otros controladores JDBC.

Las instrucciones en la caché pueden reservar cursores de la base de datos.

Cuando WebLogic Server almacena en caché una sentencia preparada o ejecutable, esta puede abrir un cursor en la base de datos. Si almacena demasiadas sentencias en caché, podría superar el límite de cursores abiertos para una conexión. Para evitar superar este límite, puede modificarlo en su sistema de gestión de bases de datos o reducir el tamaño de la caché de sentencias preparadas para el grupo de conexiones.

&#x20;

&#x20;
