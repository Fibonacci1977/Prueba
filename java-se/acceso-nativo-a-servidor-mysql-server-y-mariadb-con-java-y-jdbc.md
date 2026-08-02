# Acceso nativo a  servidor MySQL Server y MariaDB con Java y JDBC



![Acceso nativo a servidor MySQL Server y MariaDB con Java y JDBC](https://proyectoa.com/wp-content/uploads/2021/01/imagen-28-1280x640.png)

Explicamos cómo acceder a un servidor de base de datos MySQL o MariaDB de forma nativa (sin instalar [ software](https://proyectoa.com/acceso-nativo-a-servidor-mysql-server-y-mariadb-con-java-y-jdbc/) adicional) usando Java como lenguaje de programación y JDBC como método de conexión. No usaremos los métodos de persistencia y serialización de Java, que explicaremos en otro artículo, únicamente la conexión directa con MySQL o MariaDB de nuestra aplicación. Usaremos el IDE IntelliJ IDEA, aunque también explicamos cómo hacer la aplicación en Eclipse.

Servidores informáticos

* [Descarga del driver JDBC correspondiente para Java](https://proyectoa.com/acceso-nativo-a-servidor-mysql-server-y-mariadb-con-java-y-jdbc/#descarga-driver-jdbc-mysql-mariadb).
* [El servidor de MySQL o de MariaDB](https://proyectoa.com/acceso-nativo-a-servidor-mysql-server-y-mariadb-con-java-y-jdbc/#servidor-mysql-mariadb).
* [Crear aplicación Java con acceso a MySQL o MariaDB de forma nativa con JDBC y con el IDE IntelliJ IDEA](https://proyectoa.com/acceso-nativo-a-servidor-mysql-server-y-mariadb-con-java-y-jdbc/#java-mysql-mariadb-jdbc-sql-intellij).
* [Agregar JAR de driver JDBC en Eclipse](https://proyectoa.com/acceso-nativo-a-servidor-mysql-server-y-mariadb-con-java-y-jdbc/#agregar-jar-libreria-eclipse-jdbc).
* [Consideraciones y sugerencias](https://proyectoa.com/acceso-nativo-a-servidor-mysql-server-y-mariadb-con-java-y-jdbc/#consideraciones-sugerencias).

## Descarga del driver JDBC correspondiente para Java <a href="#descarga-driver-jdbc-mysql-mariadb" id="descarga-driver-jdbc-mysql-mariadb"></a>

En primer lugar descargaremos el fichero .jar del driver JDBC, será este fichero el que contenga los métodos necesarios para interactuar con la base de datos MySQL o MariaDB. Dicho fichero se puede descargar de la web oficial de MySQL, en la URL:

[https://dev.mysql.com/downloads/connector/j/](https://dev.mysql.com/downloads/connector/j/)

Para que nuestro programa no dependa del sistema operativo y funcione correctamente en Windows, Linux o MAC OS, seleccionaremos en «Select Operating System» la opción «Platform Independent»:

Administración de datos



Descargando el fichero _mysql-connector-java-8.0.22.zip_ o el fichero _mysql-connector-java-8.0.22.tar.gz_. Son el mismo pero comprimido con zip o con gz respectivamente.

Por supuesto, es la versión a la fecha de la realización de este artículo, que puede variar conforme pasen los meses. Descargaremos la versión más reciente, a ser posible, del Connector/J (Driver JDBC de MySQL).

Este driver JDBC de MySQL servirá tanto para bases de datos MySQL como MariaDB, pero si vamos a usar el motor de base de datos MariaDB podemos descargar su driver JDBC específico desde:

Software

[https://mariadb.com/kb/en/about-mariadb-connector-j/](https://mariadb.com/kb/en/about-mariadb-connector-j/)

Descomprimiremos el fichero JDBC descargado, que contiene lo siguiente:



En nuestro caso solo nos interesa el fichero _**mysql-connector-java-8.0.22.jar**_, que es el que usaremos en nuestra aplicación, el que contiene todos los métodos de acceso y manipulación de base de datos MySQL o MariaDB.

Programación

## El servidor de MySQL o de MariaDB <a href="#servidor-mysql-mariadb" id="servidor-mysql-mariadb"></a>

Como es lógico, necesitaremos disponer de un servidor de base de datos con MySQL Server o bien con MariaDB. Y necesitaremos, por supuesto, la dirección de este servidor, el puerto de acceso, un usuario y una contraseña con permisos para acceder a las tablas que necesitemos en la aplicación.

En este ejemplo usaremos un servidor instalado localmente, en el mismo equipo en el que ejecutaremos la aplicación Java. Para instalarlo hemos usado XAMPP, que instala MySQL, Apache, PHP y otros componentes de forma automática. Aunque no es necesario usar XAMPP, puede descargarse el instalador de MySQL Server directamente de su web oficial. Por ejemplo, en este artículo, explicamos cómo instalar MySQL Server en Windows:

* [Instalar MySQL Community Server 5.6.12 x64 en equipo con Windows 7 Ultimate](https://proyectoa.com/instalar-mysql-community-server-5612-x64-en-equipo-con-windows-7-ultimate/).

Una vez que tengamos el servidor de MySQL o MariaDB, un usuario y una contraseña, estaremos preparados para «atacar» dicha base de datos con nuestra aplicación Java.

Para nuestro ejemplo tendremos creada una tabla llamada «articulos» en una base de datos llamada «lista\_compra»:

<figure><img src="https://proyectoa.com/wp-content/uploads/2021/01/imagen-20-1024x629.png" alt="El servidor de MySQL o de MariaDB" height="472" width="768"><figcaption></figcaption></figure>

Dicha tabla la hemos creado ejecutando la siguiente sentencia SQL:

Sistemas operativosMySQL

|   | CREATE TABLE articulos (  id int(11) NOT NULL AUTO\_INCREMENT,  nombre varchar(100) NOT NULL,  cantidad int(11) DEFAULT NULL,  PRIMARY KEY (id),  UNIQUE KEY id\_UNIQUE (id),  UNIQUE KEY \`nombre\_UNIQUE\` (nombre)) ENGINE=InnoDB AUTO\_INCREMENT=5 DEFAULT CHARSET=latin1 |
| - | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

## Crear aplicación Java con acceso a MySQL o MariaDB de forma nativa con JDBC y con el IDE IntelliJ IDEA <a href="#java-mysql-mariadb-jdbc-sql-intellij" id="java-mysql-mariadb-jdbc-sql-intellij"></a>

En nuestro caso usaremos el IDE de desarrollo IntelliJ IDEA, pero por supuesto podremos usar cualquier otro como Eclipse o NetBeans, el código de acceso a MySQL será el mismo.

Crearemos un nuevo proyecto Java



Seleccionaremos «Java» en la parte izquierda y pulsaremos «Next»:

Administración de datos



Crearemos una aplicación de consola, por lo que marcaremos «Create project from template» y elegiremos «Command Line App»:

Software



Introduciremos un nombre para nuestro proyecto, por ejemplo «JavaAccesoMySQL» y una ubicación en una carpeta. Pulsaremos «Finish»:



El código que usaremos para acceder al [ servidor](https://proyectoa.com/acceso-nativo-a-servidor-mysql-server-y-mariadb-con-java-y-jdbc/) de MySQL o MariaDB, para ejecutar una consulta SQL sobre una tabla y mostrar los valores devueltos por la consulta SQL por consola, será el siguiente (es importante añadir los _import_ correspondientes para usar el driver JDBC):

Servidores informáticosJava

|   | import java.sql.\*; public class Main {     public static void main(String\[] args) {        //Cargaremos el driver JDBC de acceso a MySQL/MariaDB        try {            Class.forName("com.mysql.cj.jdbc.Driver");        } catch (ClassNotFoundException error) {            System.out.println("Error al cargar el driver JDBC de MySQL: " + error.getMessage());        }         //Realizamos la conexión con el servidor MySQL/MariaDB        //Con los datos de conexión: dirección, puerto, usuario y contraseña        //En este ejemplo suponemos que el servidor MySQL está en localhost, puerto 3306, usuario root, sin contraseña        Connection conBD = null;        try {            conBD = DriverManager.getConnection(                    "jdbc:mysql://localhost:3306/lista\_compra?serverTimezone=UTC",                    "root", "");        } catch (SQLException error) {            System.out.println("Error al conectar con el servidor MySQL/MariaDB: " + error.getMessage());        }         //Creamos una declaración (statement) de la conexión        Statement mStm = null;        try {            mStm = conBD.createStatement();        } catch (SQLException error) {            System.out.println("Error al establecer declaración de conexión MySQL/MariaDB: " + error.getMessage());        }         //Ejecutamos una consulta SQL contra el statement anterior        //El resultado se guardará en el ResultSet        ResultSet mRS = null;        try {            mRS = mStm.executeQuery("Select nombre, cantidad from articulos");            //Recorremos todos los registros del SQL devuelto en el ResultSet            while (mRS.next()) {                System.out.println("Artículo: " + mRS.getString(1) + " Cantidad: " + mRS.getString(2));            }        } catch (SQLException error) {            System.out.println("Error al ejecutar SQL en servidor MySQL/MariaDB: " + error.getMessage());        }         //Cerramos el ResultSet, el Statement y la conexión        try {            mRS.close();            mStm.close();            conBD.close();        } catch (SQLException error) {            System.out.println("Error al cerrar conexión a servidor MySQL/MariaDB: " + error.getMessage());        }    \}} |
| - | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

Si intentamos compilar la aplicación para probarla, veremos que nos muestra este error:

Programación

_Error al cargar el driver JDBC de MySQL: com.mysql.jdbc.Driver_\
_&#x45;rror al conectar con el servidor MySQL/MariaDB: No suitable driver found for jdbc:mysql://localhost:3306/lista\_compra_



Es debido a que no hemos añadido el driver JDBC en su carpeta adecuada. Para solucionar este error solo tendremos que copiar el fichero descargado anteriormente _**mysql-connector-java-8.0.22.jar**_ a la carpeta lib de nuestra aplicación:



Y desde el menú «File» – «Project Structure»

Administración de datos



Seleccionaremos «Modules» \[1] y en la parte derecha pulsaremos en «Dependencies» \[2]. Pulsaremos en el botón «+» \[3]:



Seleccionaremos «JARs or directories…»:

Software



Seleccionaremos la carpeta lib de nuestro proyecto, donde tenemos copiado el fichero JDBC _**mysql-connector-java-8.0.22.jar**_:



Guardaremos los cambios pulsando OK:

Servidores informáticos

<figure><img src="https://proyectoa.com/wp-content/uploads/2021/01/imagen-27-1024x638.png" alt="" height="479" width="768"><figcaption></figcaption></figure>

Y ya podremos compilar y probar nuestra aplicación Java con acceso a MySQL o MariaDB de forma nativa. Ahora sí, la aplicación se ejecutará, usará el driver JDBC y accederá al [ servidor](https://proyectoa.com/acceso-nativo-a-servidor-mysql-server-y-mariadb-con-java-y-jdbc/) MySQL, ejecutando la sentencia SQL, obteniendo los datos de la tabla y mostrándolos en consola:

<figure><img src="https://proyectoa.com/wp-content/uploads/2021/01/imagen-28-1024x570.png" alt="" height="428" width="768"><figcaption></figcaption></figure>

## Agregar JAR de driver JDBC en Eclipse <a href="#agregar-jar-libreria-eclipse-jdbc" id="agregar-jar-libreria-eclipse-jdbc"></a>

En el caso de Eclipse, si queremos agregar el fichero .jar del driver JDBC _**mysql-connector-java-8.0.22.jar**_ a nuestro proyecto, en primer lugar lo copiaremos a la carpeta lib (como hemos hecho anteriormente para IntelliJ IDEA) de nuestro proyecto:

Administración de datos



Si no existiera la carpeta «lib» la crearemos, como es lógico. Una vez que tengamos el fichero _**mysql-connector-java-8.0.22.jar**_ en dicha carpeta, en nuestro caso en:

_D:Mis documentosJavaJavaAccesoMySQLlib_

Pulsaremos con el botón derecho del ratón sobre la carpeta del proyecto en Eclipse \[1] y seleccionaremos «Proporties» \[2] en el menú emergente:

Servidores informáticos



Seleccionaremos «Java Build Path» \[1], pulsaremos en la pestaña «Libraries» \[2] y en el botón «Add JARs…» \[3]:

Programación



Buscaremos el fichero JAR _**mysql-connector-java-8.0.22.jar**_ en la carpeta _lib_ de nuestro proyecto y lo seleccionaremos. Pulsaremos «OK»:



Pulsaremos «Apply an close»:

<figure><img src="https://proyectoa.com/wp-content/uploads/2021/01/imagen-32-1024x432.png" alt="Agregar JAR de driver JDBC en Eclipse" height="324" width="768"><figcaption></figcaption></figure>

Y ya podremos ejecutar la aplicación desde Eclipse, que funcionará correctamente:

Software



## Consideraciones y sugerencias <a href="#consideraciones-sugerencias" id="consideraciones-sugerencias"></a>

Por supuesto, esta no es la forma idónea de realizar una aplicación Java con acceso a base de datos. Lo óptimo es usar persistencia y serialización que independicen los métodos de acceso a la base de datos del resto de la lógica de la aplicación. De esta forma no tendremos que cambiar casi nada en nuestra aplicación si decidimos cambiar el motor de base de datos (Oracle, SQL Server, Firebird, MySQL, MariaDB, PosgreSQL, SQLite, Access, MongoDB, XML, etc.).

Además, es recomendable usar una clase separada para la conexión con la base de datos y los métodos de manipulación y tratamiento de tablas y registros.

Administración de datos

Este ejemplo es una forma de mostrar que con Java se puede acceder nativamente (sin instalar ODBC ni drivers de terceros) a MySQL, a MariaDB o a cualquier otra base de datos, únicamente necesitaremos el fichero JDBC correspondiente, como hemos explicado anteriormente.

En el ejemplo hemos realizado la conexión con el servidor de MySQL o MariaDB mediante una cadena de conexión establecida en el código: servidor, puerto, usuario y contraseña. Como es lógico, este método no es idóneo porque si el servidor de base de datos está ubicado en otro lugar o bien tiene un usuario y contraseña diferentes siempre habría que cambiar el código y volver a generar el JAR de la aplicación, lo cual no es nada recomendable. Lo ideal es almacenar estos datos de conexión en un fichero XML (o de configuración) y que la aplicación los lea antes de realizar la conexión.

Programación
